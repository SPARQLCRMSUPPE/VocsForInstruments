

- [x] [Klangbeispiel anpassen in Anwendungsmodell

- [ ] insg. die Anschlussfähigkeit für gemeinsame Entwicklung stärker betonen

- [x] ebenso Person a

- [x] höchster /tiefster Ton falsch transponiert

- [ ] *genaue Entsprechung* und *ungefähre Entsprechung* in Anwendungsmodell einpflegen

- [x] in ERM  "Label" rausnehmen [<- warum eigtl.?]

- [ ] allgemein: es muss "Stimmton" statt "Kammerton" heißen -> Klasse vgl. MGG "Stimmton":
ma:Stimmton ma:hat_Ton ma:a' ;
                      ma:hat_Frequenz ma:415Hz .

- [x] Stimmungskonzepte überprüfen / überarbeiten (insb. Grundstimmung / obertonreine Stimmung / relative Stimmung bleibt?)
- [ ] "relative Stimmung" muss ersetzt werden (durch?)

- [ ] Es muss eine Oberklasse "Ton" eingeführt werden – entsprechende Anpassung in Vokabular / ERM <- in Protegé schon drin

- [ ] Evtl. für Frequenz doch Datatype?

- [ ] Interpret + Ereignis muss auch mit Objekt verbunden werden! (oder?)

- [x] ERM "bezeichnung" bei Klassifikation rausnehmen. Allgemein am Ende: "Label"? <- Anpassen in ma und MA !!!

- [ ] skos:exactMatch anpassen in Grafik (4_2?)

- [ ] Klären: kann man RDF statements überhaupt in MEI embedden? Wie ist das z.B. bei Weber-Gesamtausgabe? Werden die Tripel außerhalb gespeichert und nur aus der MEI Datei referenziert?

- [ ] Änderung der Gliederung: "3.0 Vorarbeiten" oder "Erfassung[/Modellierung?] mit RDF" und "4.0 Integration Semantic Web" oder so.

- [x] ERM: nicht Kammerton!

- [x] ERM: statt hat Stimmung (relativ) gleich hat Stimmung (Pedalton)

- [ ] Datenmodell insg. eigentlich könnte auch das Objekt an Ereignis gekoppelt sein – muss nicht m it Werk verknüpft sein – irgendwo erwähnen (Schluss?)

- [ ] Literals in Vokabular = alles mit Anführungszeichen. Ändern! (_ _)

- [ ] **das muss in das endgültige Vokabular eingepflegt werden.**!!°!!!!!!!!!

``<wdt:musical_instrument>	<ma:hat_Stimmung>	<ma:Kammerton>	.``\
 
 ``<ma:Kammerton>	<rdf:subject>	<ma:Ton>	.``\
 
``<ma:Kammerton>	<rdf:predicate>	<rdf:value>	.``\

``<ma:Kammerton>	<rdf:object>	<wdt:pitch>	.``\

sowie

``<ma:Kammerton>	<rdf:type>	<rdf:statement>	.``

- [x] Alles, was domänenspezifisch ist, muss ausgelagert werden.

- [ ] Barockhorn muss irgendetwas anderes werden(?) nein! sagen, dass man da noch geografische Herkunft darndingsen könnte.

- [ ] Ambitus könnte auch für Objekt wichtig sein!

- [ ] deprezierte Namespaces wegschmeißen -> im Text Links in den Müllhaufen umleiten.