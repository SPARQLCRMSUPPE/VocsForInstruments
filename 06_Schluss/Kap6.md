Anwendungsfälle:

* Johann Dings spielt UA Weißenfells 1713 auf ähnlichem Instrument, wie Objekt – Horn in F, Stimmung 415 Hz – Ambitus ...
* Jemand spielt auf Orgel in St. Wenzel
* jemand spielt Objekt?, spielt 4'33 - auf Aufnahme - in pythagoreischer Stimmung mit dis' = 346 Hz
* jemand spielt auf historischem Instrument (B-Klarinette?) - a' = 440 Hz



Diese Sachen müssen definiert sein:

``domaene:BWV208    domaene:hatUraufführung   domaene:UrauffuehrungBWV208   .

#\ In einem externen Vokabular ist das Ereignis der Uraufführung mit dem uraufgeführten Werk verknüpft.[^1]

domaene:BWV208    domaene:hatBesetzung    domaene:corDaCaccia   .




domaene:UrauffuehrungBWV208   a   ma:Auffuehrung(Domaene)   .

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

#\ Ein Beispiel für den Typ "Barockhorn" ist das Großwindige Waldhorn etc. <- Problem, weil alle Aussagen zum Typ jetzt auf Objekt übertragen werden (wegen Mapping) z.B. in F etc. Lösung: anderes, nicht-symmetrisches Property für Mapping?

domaene:corDaCaccia   ma:hatStimmung(notierte)    ma:F_(Tonkomplex)   .

#\ Das Horn in BWV ist in F notiert (es handelt sich um ein F-Horn).

domaene:corDaCaccia   ma:hatStimmungssystem   ma:obertonreineStimmung   .

#\ Das Horn hat die Stimmung "Obertonrein". 

domaene:corDaCaccia   ma:hatStimmhoehe    ma:Stimmhoehe   .

ma:Stimmhoehe   rdf:subject   wdt:118819    .

ma:Stimmhoehe   rdf:predicate   rdf:value   .

ma:Stimmhoehe   rdf:object    ma:415Hz    .

#\ die Absolute Stimmhöhe des Horns ist a' = 415 Hz.

domaene:corDaCaccia   ma:hatAmbitus   ma:Ambitus    .

ma:Ambitus    ma:hat_tiefsten_Ton   ma:c'   .

ma:Ambitus    ma:hat_tiefsten_Ton   ma:a''    .

#\ Der Ambitus des Horns umspannt die Töne c' und a'' (notiert!)

#\ Folgende Informationen können darüber hinaus inferriert werden:``

[^1]: Denkbar wäre es – sofern sinnvoll – noch weitere Anreicherungsmöglichkeiten in das Metadatenprofil zu integrieren: bspw. Ort und Zeit. Fraglich ist jedoch, ob diese Informationen nicht bereits im Ereignisdatensatz vorhanden sind.
[^2]: Die Objektebene scheint nicht mit Aufführung und Person verknüpfbar. ODER????!!