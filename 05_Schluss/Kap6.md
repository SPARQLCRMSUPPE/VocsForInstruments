# Schluss

## Wrap-up

## Anwendungssimulation

Nach erfolgter Modellierung liegt es nahe, die Kohärenz sowie die Praxistauglichkeit des Metadatenprofils zu verifizieren. Doch anhand welcher Kriterien und mit welcher Methode lässt sich der Erfolg prüfen? Wären die Datensätze bereits in einem Triple Store publiziert, ließe sich mithilfe verschiedener Abfragen über eine API oder eine SPARQL-Schnittstelle die Konsistenz des Datenmodells feststellen, indem eine Abfrage einer Kataloganwendung simuliert würde. Da dies nun nicht der Fall ist, erscheint der Ansatz sinnvoll, eine Nachmodellierung des "Anwendungsszenarios" aus #Kapitel anhand dem Metadatenprofil vorzunehmen. Diese Modellierung simuliert denn zwar nicht die Schnittstellenabfrage an sich, wohl aber das erfolgreiche Retrieval relevanter Informationen. Gelingt die Nachmodellierung, ist davon auszugehen, dass das Metadatenprofil den spezifischen Anforderungen des Szenarios genügt. 

Diese Vorgehensweise, anhand eines gewünschten Szenarios eine Simulation in Form einer Modellierung vorzunehmen und dabei semantische Inkompatibilitäten und Modellierungsfehler zu identifizieren, erschiene auch im Falle einer zukünftigen Weiterentwicklung des Metadatenprofils geeignet.


### Modellierung

[hier fehlen noch die ganzen Namespaces]

Das Szenario sah vor, dass im Bereich der Domäne die folgenden Zuhammenhänge bereits vordefiniert sind:\

```
domaene:BWV208    domaene:hatUraufführung   domaene:UrauffuehrungBWV208   .

domaene:BWV208    domaene:hatBesetzung    domaene:corDaCaccia   .

#\ In einem externen Vokabular ist das Ereignis der Uraufführung mit dem uraufgeführten Werk verknüpft und die Besetzung ist mit dem Domänenvokabular bezeichnet. [^1]
```
\
Eingedenk dieser gesetzten Prämisse voranschreitend ist die Modellierung mit dem Vokabular des Metadatenprofils in folgender Weise möglich:


```
domaene:UrauffuehrungBWV208   rdf:type   ma:Auffuehrung(Domaene)   .

#\ Externen Ereignis-Datensatz als Ereignis im Sinne des Metadatenprofils definiert.

domaene:UrauffuehrungBWV208   mo:performer    wdt:Q97621186   .

#\ Die Uraufführung fand unter Mitwirkung von Johannes Zedelmayer statt.

domaene:UrauffuehrungBWV208   mo:instrument   domaene:Barockhorn_Mitteldeutschland    .

#\ Die Uraufführung fand mit einem Barockhorn statt.

domaene:Barockhorn_Mitteldeutschland    litmus:L58i   wdt:Q97621186   .

#\ Ein Instrument des Typs "Barockhorn" wurde gespielt von Johannes Zedelmayer.

domaene:Barockhorn_Mitteldeutschland    owl:sameAs    domaene:corDaCaccia   .

#\ Der Typ "Barockhorn" entspricht dem Typ "cor da caccia".

domaene:Barockhorn_Mitteldeutschland    crm:P137    domaene:MIMUL_Inv.-Nr.\_1663    .

#\ Ein Beispiel für den Typ "Barockhorn" ist das Großwindige Waldhorn etc.

domaene:corDaCaccia   ma:hatStimmung(notierte)    ma:F_(Tonkomplex)   .

#\ Das Horn in BWV ist in F notiert (es handelt sich um ein F-Horn). Hier wird abermals das Problem des Mappings deutlich – tatsächlich existiert keinerlei Information, ob es sich bei MIMUL 1663 um ein Horn in F handelt. Durch Vererbung kraft des symmetrischen Property's crm:P137 ist dies nun jedoch nahegelegt.

domaene:corDaCaccia   ma:hatStimmungssystem   ma:obertonreineStimmung   .

#\ Das Horn hat die Stimmung "Obertonrein". 

domaene:corDaCaccia   ma:hatStimmhoehe    ma:Stimmhoehe   .

ma:Stimmhoehe   rdf:subject   wdt:118819    .

ma:Stimmhoehe   rdf:predicate   rdf:value   .

ma:Stimmhoehe   rdf:object    ma:415Hz    .

#\ die absolute Stimmhöhe des Horns ist a' = 415 Hz.

domaene:corDaCaccia   ma:hatAmbitus   ma:Ambitus    .

ma:Ambitus    ma:hat_tiefsten_Ton   ma:c'   .

ma:Ambitus    ma:hat_tiefsten_Ton   ma:a''    .

#\ Der Ambitus des Horns umspannt die Töne c' und a'' (notiert!)

#\ Folgende Informationen können darüber hinaus durch das Wissen um Referenzton, Stimmungston und notierte Stimmung inferiert werden:
```





Zwei Erkenntnisse können bereits festgehalten werden:

* Das Problem des "Mappings" zwischen Vokabular und Objekt ist – dies wurde bereits in #Kapitel festgestellt – nicht bestmöglich gelöst. Die Vererbung von Eigenschaften der je einen auf die je andere Entität, wie sie momentan der Fall ist, ist nicht wünschenswert. Dies wurde bei der Modellierung nochmals sehr deutlich. So ist beispielsweise die Option, verschiedenartig gestimmte Instrumente miteinander in Beziehung zu setzen, prinzipiell nicht möglich. Hier ist weitere Arbeit bei der Relationierung durch Properties angezeigt, wobei etwa auch Möglichkeiten der Prädikatenlogik zu prüfen, ein interessanter Ansatz sein könnte.
* Das Metadatenprofil eignet sich – soweit es sich hier feststellen lässt – grundsätzlich zur Modellierung des Anwendungsszenarios und ähnlich komplexer musikalischer/organologischer Sachverhalte, die Entitäten verschiedener Kulturerbedomänen miteinander in Beziehung setzen und verknüpfen. Dieses Anliegen der Arbeit kann somit nun als weitestgehend erfüllt betrachtet werden.



## Fazit













[^1]: Denkbar wäre es – sofern sinnvoll – noch weitere Anreicherungsmöglichkeiten in das Metadatenprofil zu integrieren: bspw. Ort und Zeit. Fraglich ist jedoch, ob diese Informationen nicht bereits im Ereignisdatensatz vorhanden sind.