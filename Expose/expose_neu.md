# Exposé Masterarbeit Alan Riedel
## Beziehungen von Musikinstrumenten im Semantic Web - Versuch eines Metadatenprofils

Bei der näheren Betrachtung musikinstrumentenbezogener Vokabulare fallen eine Reihe von Defiziten auf:
* Es erweisen sich die gebräuchlichen Vokabulare[^036d] hinsichtlich Präzision, Darstellungstiefe und Konsistenz oftmals als unzureichend.
* Es existiert – gerade hinsichtlich der Klassifikation von Musikinstrumenten – kein interdisziplinär anerkannter Standard.
* Standardbildung wird durch die Heterogenität von sparten- oder disziplinspezifischer Bedürfnisse und etablierter historisch gewachsener Praktiken (etwa in der Erschließung) erschwert.[^0455]

Aus diesen Defiziten ergeben sich zwei vornehmliche Anknüpfungsbereiche:
* Zum einen erscheint eine spartenübergreifende und interdisziplinäre Ausbildung einer Standardklassifikation von Musikinstrumenten geboten.
* Zum anderen stellt die Weiterentwicklung der zur Verfügung stehenden musikinstrumentenbezogenen Terminologie ein wichtiges Desiderat dar.

Aus der Überzeugung heraus, dass Standardbildung ein Unterfangen darstellt, das notwendig seine Verankerung innerhalb einer Fachgemeinschaft unterhalten muss, klammert diese Arbeit Fragen im Bereich der Klassifikation von Musikinstrumenten aus[^9db5] und verschreibt sich stattdessen der Erweiterung bestehender Terminologie. Doch auch hierbei gilt die notwendige Bedingung einer fachgemeinschaftlichen Einbettung in gleichem Maße – den Versuch präskriptive Verbindlichkeit zu schaffen, maßt sich diese Arbeit keineswegs an. Vielmehr versteht sie sich als Impuls, durch dokumentierte, wissenschaftlich fundierte terminologische Vorarbeiten das Feld für eine kooperative, fachgebundene Weiterentwicklung zu bereiten.[^eb9a] Die Validität und Anschlussfähigkeit der in dieser Arbeit entwickelten Ansätze sollen zudem in Form eines *Proof of Concepts* erprobt und erörtert werden.[^b58d]

Eine besondere Herausforderung liegt in der bereits erwähnten enormen Heterogenität potentieller Anwenderkreise sowie ihrer spezifischen Nutzungsszenarien und Bedürfnisse.[^670b] Hinter diesen verbergen sich ganz und gar individuell ausgestaltete konzeptuelle Bezugnahmen auf Musikinstrumente.[^8e5b] Diese Bezüge terminologisch kontrolliert zu erfassen und referenzierbar zu machen, bietet die große Chance, ein semantisches Netz aus Beziehungen zu knüpfen. Dieses ist imstande, empirisch erfasste Entitäten aus dem Musikdokumentationswesen im weitesten Sinne miteinander zu verbinden.[^5637]

Als technischer Standard empfiehlt sich hierfür insbesondere das sog. *Research Description Framework*.[^263b] Er erlaubt die Repräsentation hochkomplexer, multidimensionaler Beziehungen bei größtmöglicher Interoperabilität und konzeptueller Erweiterbarkeit. Zugleich wird das Vokabular – oder genauer: das Metadatenprofil[^5cb5] – kraft seiner Ausstattung mit *Uniform Ressource Identifiern* und seiner Publikation im Internet maschinenlesbar in das sog. *Semantic Web* integriert. Um dies umzusetzen, müssen zunächst bestehende einschlägige Ontologien auf ihr semantisches Potential für die Darstellung treffender Bezüge (sog. *Properties*) ausgewertet werden.[^d6e8] Auf Grundlage der gewonnenen Erkenntnisse erfolgt anschließend die Modellierung des Applikationsprofils, wobei bis dato fehlende Properties ebenfalls anzulegen sein werden.

Es entsteht so als wissenschaftliches Beiprodukt neben dem eigentlichen *Proof of Concept* auch ein Leitfaden zur technischen Implementierung eines *Linked Open Data*-basierten Normvokabulars.



---

[^9db5]: Zugleich exisitieren durch das DOREMUS-Projekt (link) bereits Mappings zwischen unterschiedlichen gebräuchlichen Klassifikationen und Vokabularen, sodass viele gängige Klassifikationen bereits miteinander verlinkt sind (vgl. Pierre Choffé und Françoise Leresche, Art. "DOREMUS: Connecting Sources, Enriching Catalogues and User Experience", (= 24th IFLA World Library and Information Congress, Columbus, OH 2016, <http://library.ifla.org/1322/2/093-choffe-en.pdf>eingesehen am 28.01.2020).

[^036d]: Neben den einschlägigen Vokabularen – allen voran UNIMARC Medium of Performance (http://metadataregistry.org/vocabulary/show/id/380.html), Gemeinsame Normadatei (https://www.dnb.de/DE/Professionell/Standardisierung/GND/gnd_node.html;jsessionid=EABF103A6BB5F1F3BB106566B1CEDA98.internet571), Library of Congress Subject Headings (http://id.loc.gov/authorities/subjects.html) – betrifft dies ab

[^eb9a]: Flankiert werden soll diese Arbeit bestenfalls von koordinatorischen Maßnahmen, die diesen Prozess ebenfalls in Gang setzen und begleiten, jedoch kein Teil dieser Arbeit darstellen.

[^670b]: Es liegt auf der Hand, dass die sehr weiten Bedürfnisse vieler öffentlicher Musikbibliotheken von den außerordentlich spezifischen Bedürfnissen des wissenschaftlichen Editionswesens oder des Museumswesens differieren.

[^8e5b]: Etwa materiell, immateriell, referentiell, unmittelbar etc.

[^263b]: Vgl. etwa die Dokumentation des W3C (https://www.w3.org/RDF/).

[^5cb5]: Zur Begriffserklärung s.: Stefanie Rühle, *Kleines Handbuch Metadaten. Metadatenprofile*, o.O. o.J., S.2-3.

[^d6e8]: Dies meint sowohl sehr generische Vokabulare, wie RDFS, OWL, sowie domänen- und spartenspezifische Vokabulare, wie die MusicOntology, die GND-Ontology, CIDOC-CRM, EAD etc.

[^5637]: Etwa eine Musik-CD mit Orgelmusik mit dem physischen Objekt, der spezifischen Orgel (ganz zu schweigen etwa von Besonderheiten, wie die Stimmung d. Instruments, die Registrierung etc.).

[^b58d]: Etwa in Form exemplarischer und individueller Anwendungen an bestimmte Beziehungen etwa zwischen Werk, Besetzung und Objekt (= Instrument) etc.
