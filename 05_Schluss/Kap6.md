# Schluss


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
@prefix wumms: <http://purl.org/wumms#> .
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


Ausgehend von einem exemplarischen Anwendungsszenario, dem Horn im Kontext von J. S. Bachs sog. "Jagdkantate" BWV 208, wurde die Modellierung eines Metadatenprofils, *wumms:* (**S**e**M**antic **MU**sical instrument **W**eb), das auf den Prinzipien von *Linked Open Data* basiert, vorgenommen und im Netz publiziert.[^2] Dabei galt es insbesondere zu prüfen, in wie weit es in diesem Szenario möglich ist, mit den Mitteln des *Semantic Web* musikinstrumentenbezogene Entitäten und Ressourcen aus unterschiedlichen Sparten des Kulturerbes miteinander semantisch zu verknüpfen und dabei  Anreicherungen der bisherigen Ausdrucksmöglichkeiten bei der Erschließung solcher Entitäten und Ressourcen zu schaffen. 
Dazu wurde das Szenario zunächst in ein *Entity Relationship Modell* überführt, das die Grundlage für eine anschließende RDF-Klassierung bildete. Die Bestandteile dieses semantischen Grundgerüsts wurden im Anschluss mit etablierten Vokabularen nachmodelliert und so das Profil eng in das *Semantic Web* eingewoben. Ließen sich gewünschte Sachverhalte mit dem im *Semantic Web* vorhandenen Vokabular nicht adäquat nachbilden – dies war insbesondere im Kontext von "Stimmung" der Fall –, wurden eigene Konzepte geschaffen und durch Subklassierung unter etablierte externe Konzepte gleichfalls an das *Semantic Web* semantisch anschlussfähig.

Die Ziele dieser Arbeit konnten weitestgehend erreicht werden. Die anfangs entworfenen Szenarien konnten zum Schluss erfolgreich modelliert und so eine Verbindung zwischen verschiedenen spartenspezifischen Ressourcen hergestellt werden. Sowohl methodische Grundlage in Form dieser Arbeit als auch konzeptuelle Grundlage in Form einer *lightweight ontology* sind somit für eine weitere Ausarbeitung geschaffen. 
Dies gilt jedoch nur eingeschränkt für das objekt- und quellenseitige "Mapping": Hier weist das jetzige Modell noch Defizite auf, die im Zuge einer Weiterentwicklung anzugehen wären. Dies vermag jedoch nicht weiter zu verwundern, liegt doch das Defizitäre in der Natur eines Modells, das den Ausgangspunkt eines diskursiven Prozesses markieren soll.
Ähnliches gilt für die Schaffung von komplexeren Inferenzierungsmöglichkeiten: Im Bereich der "Stimmungen" konnte die Sinnhaftigkeit solcher Möglichkeiten bei der automatisierten Transposition von Tönen demonstriert werden. Jedoch erforderte eine Implementierung fundiertere Informatikkenntnisse (zumindest gegenüber denen des Verfassers). Induktiv gesehen liegt somit der Schluss nahe, dass Ontologieentwicklung idealerweise ab einem gewissen Punkt als Kooperation zwischen Fachwissenschaftlern und Informatikern geschieht.
Operative Schritte wären für eine weitere Ausarbeitung die Bildung einer entsprechenden Community und das Schaffen einer Plattform für die kooperative Weiterentwicklung. Hierfür verspricht etwa die Software *Wikibase*[^3] eine außerordentlich vielversprechende Plattform bieten zu können.
Wünschenswert wäre schließlich die technische Möglichkeit, in RDF strukturierte Daten gegenüber dem Metadatenprofil zu validieren, wie man es etwa von in XML strukturierten Datensätzen her gewohnt sein mag. Dies ermöglichen die Sprachen *ShEX* ("Shape Expressions" – in *Wikibase* "enthalten")[^4] und *SHACL* ("Shapes Constraints Language")[^5]. Während im Zuge dieser Arbeit nicht, wie ursprünglich geplant, der Versuch unternommen werden konnte, eine Beschreibung des Metadatenprofils mit einer dieser Sprachen zu unternehmen, würde eine solche Validierungsmöglichkeit ein außerordentlich nützliches Produkt darstellen,[^6] das insbesondere auch die eine niedrigschwellige Verwendung ermöglichen könnte. 






Auch hier gilt: learning by doing.


viele Dinge, Szenarien gar nicht einbezogen

bei gegenüberstellung deutlich gewordenn, welche darstellungsmöglichkeiten mit lod.
**insb. auch für die eigenen bedürfnisse relativ schnell lösbar (da ich das ja jetzt hier selbst schnell gemacht hab) <- man muss nicht auf die dnb warten
anschlussfähigkeit! <- das muss auch mehr in die Einleitung!!!!!!!**



Insgesamt war immer wieder festzustellen, dass es vielerorts im *Semantic Web* noch an elementaren Ausdrucksmöglichkeiten im Bereich der Musikinstrumente im Speziellen und der Musik im Allgemeinen sehr mangelt. Dies betrifft sowohl Normdaten (etwa ein authoritatives Verzeichnis von Orgeln), Ontologien (etwa "Stimmung", Musiktheorie, Akustik) aber auch Best Practices zur Modellierung teils einfacher musikbezogener Sachverhalte (etwa Klangbeispiele). 
Weitere Arbeit in diesen Bereichen – ob als große Ontologie, oder doch besser als viele vernetzte kleinere – birgt somit enormes Potential.

Sehr deutlich wurde dabei der Mehrwert de

Dabei wurde deutlich, dass die Modellierung von Ontologien und die Publikation von Linked Open Data eine gewisse Lernkurve voraussetzt. Doch demonstriert die Publikation von *wumms:*, die auch ganz ohne eine solche auskam, dass auch für einzelne Wissenschaftler oder Institutionen ohne starke Informatikabteilung diese Vorgänge durchaus leistbar sind – auch hier gilt wohl: *learning by doing*. Dabei sind die Vorteile, die sich bieten – etwa die Unabhängigkeit gegenüber den beschränkten Ausdrucksmöglichkeiten herkömmlicher etablierter Vokabulare – und die Anschlussfähigkeit in einer zunehmend vernetzten Wissenschaftswelt, deren Indikator etwa die Rolle von Linked Open Data in den NFDI und GND4C-Projekten ist, enorm.

Diese Anschlussfähigkeit gilt dabei mitnichten lediglich für den geisteswissenschaftlichen-/Kulturerbebereich: Innerhalb einer Nationalen Forschungsdateninfrastruktur könnten bisherige Gräben zu weiteren Disziplinen, etwa zur Akustik, zur Materialwissenschaft etc. aufgeschüttet werden, und so weitere Schritte in Richtung einer künftig interdisziplinär vernetzten Wissenschafts- und Forschungsdatenlandschaft unternommen werden.





zu einer vernetzten interdisziplinarität oder so

Erkenntnisse:

funktioniert prinzipiell
könnte ein großer Zugewinn sein für Vernetzung von Beständen, wenn man die Möglichkeiten mit den jetzigen vergleicht.

Lücken im relevanten Vokabular (und das gilt nicht nur für Instrumente)
-> man sollte also weiterentwickeln. Wie? Eine große Ontologie, oder viele kleine?
(auch erwähnen, dass interdisziplinärer Anschluss nicht nur GW, z.B. Akustik, Materialforschung, Anwendungsgebiete, die noch überhaupt nicht einfallen)

wie kann weiter gehen?











fazit

kurze zusammenfassung – 1/2 Seite
bewertung

das funktioniert
lücken – nicht allzusehr rechtfertigen rechtfertigungsschrift – zu thematisieren

2–3 Seiten




kurzzussammenfassung je kapitel höcht 1/2 seite








[^1]: Denkbar wäre es – sofern sinnvoll – noch weitere Anreicherungsmöglichkeiten in das Metadatenprofil zu integrieren: bspw. Ort und Zeit. Fraglich ist jedoch, ob diese Informationen nicht bereits im Ereignisdatensatz vorhanden sind.
[^2]: 

[^3]: [@pintscher_strategy_nodate]
[^4]: [@noauthor_shape_nodate]
[^5]: [@noauthor_shapes_nodate]
[^6]: Hier fehlt es noch sehr an verständlichen Anleitungen und Lernmöglichkeiten für Nichtinformatiker. 