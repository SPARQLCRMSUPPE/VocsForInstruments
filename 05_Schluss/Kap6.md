# Schluss

## Wrap-up

## Anwendungssimulation

Nach erfolgter Modellierung liegt es nahe, die Kohärenz sowie die Praxistauglichkeit des Metadatenprofils zu verifizieren. Doch anhand welcher Kriterien und mit welcher Methode lässt sich der Erfolg prüfen? Wären die Datensätze bereits in einem Triple Store publiziert, ließe sich mithilfe verschiedener Abfragen über eine API oder eine SPARQL-Schnittstelle die Konsistenz des Datenmodells feststellen, indem eine Abfrage einer Kataloganwendung simuliert würde. Da dies nun nicht der Fall ist, erscheint der Ansatz sinnvoll, eine Nachmodellierung des "Anwendungsszenarios" aus #Kapitel anhand dem Metadatenprofil vorzunehmen. Diese Modellierung simuliert denn zwar nicht die Schnittstellenabfrage an sich, wohl aber das erfolgreiche Retrieval relevanter Informationen. Gelingt die Nachmodellierung, ist davon auszugehen, dass das Metadatenprofil den spezifischen Anforderungen des Szenarios genügt. 

Diese Vorgehensweise, anhand eines gewünschten Szenarios eine Simulation in Form einer Modellierung vorzunehmen und dabei semantische Inkompatibilitäten und Modellierungsfehler zu identifizieren, erschiene auch im Falle einer zukünftigen Weiterentwicklung des Metadatenprofils geeignet.



### Modellierung

[hier fehlen noch die ganzen Namespaces]

Das Szenario sah vor, dass im Bereich der Domäne die folgenden Zuhammenhänge bereits vordefiniert sind:\

```
dom:BWV208    dom:hatUraufführung   dom:UrauffuehrungBWV208   ,

		              					dom:hatBesetzu	ng    	dom:corDaCaccia   .

###\ In einem externen Vokabular ist das Ereignis der Uraufführung mit dem uraufgeführten Werk verknüpft und die Besetzung ist mit dem Domänenvokabular bezeichnet. [^1]
```
\
Eingedenk dieser gesetzten Prämisse voranschreitend ist die Modellierung mit dem Vokabular des Metadatenprofils in folgender Weise möglich:


```
@prefix mo: <http://purl.org/ontology/mo/#> .
@prefix wc: <https://commons.wikimedia.org/wiki/File:> .
@prefix wd: <https://www.wikidata.org/wiki/Property:> .
@prefix crm: <http://purl.org/NET/cidoc-crm/core#> .
@prefix gnd: <http://d-nb.info/gnd/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix wdt: <https://www.wikidata.org/wiki/> .
@prefix mimo: <https://mimo-international.com/MIMO/doc/IFD/#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix wumms: <https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/wumms#> .
@prefix litmus: <https://itma.ie/litmus/ontology#> .



dom:UrauffuehrungBWV208   rdf:type   wumms:Auffuehrung   .

###\ Externen Ereignis-Datensatz als Ereignis im Sinne des Metadatenprofils definiert.

dom:UrauffuehrungBWV208   mo:performer    wdt:Q97621186   .

###\ Die Uraufführung fand unter Mitwirkung von Johannes Zedelmayer statt.

dom:UrauffuehrungBWV208   mo:instrument   dom:Barockhorn_(Mitteldeutschland)    .

###\ Die Uraufführung fand mit einem Barockhorn statt.

dom:Barockhorn_(Mitteldeutschland)    litmus:L58i   wdt:Q97621186   .

###\ Ein Instrument des Typs "Barockhorn" wurde gespielt von Johannes Zedelmayer.

dom:Barockhorn_(Mitteldeutschland)    owl:sameAs    dom:corDaCaccia   .

###\ Der Typ "Barockhorn" entspricht dem Typ "cor da caccia".

dom:Barockhorn_Mitteldeutschland    crm:P137    mimo:MIMUL_Inv.-Nr._1661    .

###\ Ein Beispiel für den Typ "Barockhorn" ist das Großwindige Naturwaldhorn etc.

mimo:MIMUL_Inv.-Nr._1661	wumms:KlangbeipsielMediumOfPerformance	wc:File:4m33s.mid	.

###\ Ein Klangbeispiel des Großwindigen Naturwaldhorn findet sich in den Wikimedia Commons.

dom:corDaCaccia   wumms:hatNotierteStimmung    wumms:F_Tonkomplex   .

###\ Das Horn in BWV ist in F notiert (es handelt sich um ein F-Horn). Hier wird abermals das Problem des Mappings deutlich – tatsächlich existiert keinerlei Information, ob es sich bei MIMUL 1663 um ein Horn in F handelt. Durch Vererbung kraft des symmetrischen Property's crm:P137 ist dies nun jedoch nahegelegt.

dom:corDaCaccia   mwumms:hatStimmungssystem   wumms:obertonreineStimmung   .

###\ Das Horn hat die Stimmung "Obertonrein". 

dom:corDaCaccia   wumms:hatStimmhoehe    wumms:Stimmhoehe   .

wumms:Stimmhoehe   rdf:subject   wdt:118819    .

wumms:Stimmhoehe   rdf:predicate   rdf:value   .

wumms:Stimmhoehe   rdf:object    ma:415Hz    .

###\ die absolute Stimmhöhe des Horns ist a' = 415 Hz.

dom:corDaCaccia   wumms:hatAmbitus   wumms:Ambitus    .

wumms:Ambitus    wumms:hatTiefstenTon   wumms:c'   .

wumms:Ambitus    wumms:hatHoechstenTon   wumms:a''    .

###\ Der Ambitus des Horns umspannt die Töne c' und a'' (notiert!)

###\ Folgende Informationen können darüber hinaus durch das Wissen um Referenzton, Stimmungston und notierte Stimmung inferiert werden:
```





Zwei Erkenntnisse können bereits festgehalten werden:

* Das Problem des "Mappings" zwischen Vokabular und Objekt ist – dies wurde bereits in #Kapitel festgestellt – nicht bestmöglich gelöst. Die Vererbung von Eigenschaften der je einen auf die je andere Entität, wie sie momentan der Fall ist, ist nicht wünschenswert. Dies wurde bei der Modellierung nochmals sehr deutlich. So ist beispielsweise die Option, verschiedenartig gestimmte Instrumente miteinander in Beziehung zu setzen, prinzipiell nicht möglich. Hier ist weitere Arbeit bei der Relationierung durch Properties angezeigt, wobei etwa auch Möglichkeiten der Prädikatenlogik zu prüfen, ein interessanter Ansatz sein könnte.
* Das Metadatenprofil eignet sich – soweit es sich hier feststellen lässt – grundsätzlich zur Modellierung des Anwendungsszenarios und ähnlich komplexer musikalischer/organologischer Sachverhalte, die Entitäten verschiedener Kulturerbedomänen miteinander in Beziehung setzen und verknüpfen. Dieses Anliegen der Arbeit kann somit nun als weitestgehend erfüllt betrachtet werden.



## Fazit












[^1]: Denkbar wäre es – sofern sinnvoll – noch weitere Anreicherungsmöglichkeiten in das Metadatenprofil zu integrieren: bspw. Ort und Zeit. Fraglich ist jedoch, ob diese Informationen nicht bereits im Ereignisdatensatz vorhanden sind.