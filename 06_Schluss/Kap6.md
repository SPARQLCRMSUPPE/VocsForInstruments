Anwendungsfälle:

* Johann Dings spielt UA Weißenfells 1713 auf ähnlichem Instrument, wie Objekt – Horn in F, Stimmung 415 Hz – Ambitus ...
* Jemand spielt auf Orgel in St. Wenzel
* jemand spielt Objekt?, spielt 4'33 - auf Aufnahme - in pythagoreischer Stimmung mit dis' = 346 Hz
* jemand spielt auf historischem Instrument (B-Klarinette?) - a' = 440 Hz



Diese Sachen müssen definiert sein:

domaene:BWV208 domaene:hatUraufführung domaene:UrauffuehrungBWV208

#\ In einem externen Vokabular ist das Ereignis der Uraufführung mit dem uraufgeführten Werk verknüpft.[^1]

domaene:BWV208 domaene:hatBesetzung domaene:corDaCaccia




domaene:UrauffuehrungBWV208 a ma:Auffuehrung(Domaene)

#\ Externen Ereignis-Datensatz als Ereignis im Sinne des Metadatenprofils definiert.

domaene:UrauffuehrungBWV208 mo:performer wdt:Q97621186 .

#\ Die Uraufführung fand unter Mitwirkung von Johannes Zedelmayer statt.

domaene:Barockhorn_Mitteldeutschland litmus:L58i wdt:Q97621186 .

#\

domaene:Barockhorn_Mitteldeutschland cidoc:P137 domaene:corDaCaccia.

#\ Durch das Mappen zwischen "objektseitigem" Instrumententyp und "werkseitigem" Vokabular durch ein "symmetric property" sowie dank der (domänenverankerten) Besetzungsangabe müsste inferierbar sein, dass Johannes Zedelmayer bei der Uraufführung ein Barockhorn spielte.[^2]

#\ Hier müsste eigentlich die UA mit verknüpft sein!!!! Von wegen: bei der UA spielte er … Hier muss nachmodelliert werden.

domaene:corDaCaccia ma:hatStimmhoehe ma:Stimmhoehe

ma:Stimmhoehe rdf:subject wdt:118819

ma:Stimmhoehe rdf:predicate rdf:value

ma:Stimmhoehe rdf:object ma:415Hz

#\ Hier müsste eigentlich die UA mit verknüpft sein!!!! Von wegen: bei der UA spielte er … Hier muss nachmodelliert werden.


domaene:corDaCaccia ma:hatStimmungssystem

domaene:corDaCaccia ma:hatStimmung(notierte)



domaene:BWV208 domaene:hatBesetzung

[^1]: Denkbar wäre es – sofern sinnvoll – noch weitere Anreicherungsmöglichkeiten in das Metadatenprofil zu integrieren: bspw. Ort und Zeit. Fraglich ist jedoch, ob diese Informationen nicht bereits im Ereignisdatensatz vorhanden sind.
[^2]: Die Objektebene scheint nicht mit Aufführung und Person verknüpfbar. ODER????!!