# Einleitung

Ziel dieser Arbeit ist es, einen Ansatz für ein semantisches Framework zu entwickeln, das seine Anwender in die Lage versetzt, musikinstrumentenbezogene Ressourcen aus Einrichtungen unterschiedlicher Sparten des Kulturerbes zueinander in Beziehung zu setzen, zu verbinden und dabei zugleich – mittelbar – bereits vorhandenes Vokabular um wichtige Aspekte anreichert. 

Musikinstrumente sind schwer zu fassende Phänomene, deren "Wesen" situativ und je nach Blickwinkel[^8] sehr unterschiedlich – etwa materiell, immateriell, medial oder performativ – sich ergeben kann.[^2] Hinzu kommt, dass sie (zumeist primär) in Abhängigkeit zu einem gleichermaßen immateriellen, hochgradig ambivalenten und damit für Kulturerbeinstitutionen ohnehin außerordentlich schwierig fassbaren Gegenstand – die Musik – stehen.[^1] Trotzdem spielen Musikinstrumente in verschiedenen solcher Einrichtungen eine Rolle – sei es als Museumsobjekt, als Besetzungsangabe einer Quelle, als Instrument in einer Aufnahme oder als Term in einem Vokabular etc. 

Es liegt dabei auf der Hand, dass sich das Konzept "Musikinstrument" eingedenk seines eingangs beschriebenen, sparten- oder gar institutionsspezifischen Blickwinkels unterscheiden muss: Eine "Objekt-zentrierte Herangehensweise" wird womöglich ganz andere Aspekte jenes Konzepts hervorheben – etwa physische oder ereignisbezogene – als eine bibliographische.[^6] Und so mag es denn auch nicht verwundern, wenn konzeptuelle Modelle und Vokabulare verschiedener Kulturerbesparten – etwa Museen, Archive, Bibliotheken etc. – mitunter nicht unmittelbar miteinander kompatibel sind.

Dabei bärge vor dem Hintergrund eines digitalisierten *GLAM*-Bereichs[^5] eine Vernetzung von Beständen, dessen Prämisse jene Kompatibilität bildet, bekanntermaßen einiges an Potential: So könnten etwa Bestandsmetadaten durch Kontextualisierung nach außen zusätzlich in Wert gesetzt werden, die Übernahme von Fremddaten zur Anreicherung eigener Datensätze erleichtert werden,[^3] neue – womöglich bestandsübergreifende – Suchmöglichkeiten und -Einstiege für den Nutzer geschaffen[^7] und Bestände virtuell zusammengeführt und sichtbarer werden.[^4] Für Forscher, etwa Editionswissenschaftler oder Digital Humanists, ergibt sich neben der Nutzung und Auswertung von hochwertigen Metadaten die Möglichkeit, eigene Forschungsdaten in diesem Austausch beizutragen. Die Aktualität und Relevanz dieses Anliegens im geisteswissenschaftlichen Bereich zeigt sich dabei etwa darin, dass mit den Projekten GND4C[^266] sowie im NFDI4Culture-Konsortium (insb. "Task Area 2")[^267] gleich zwei Projekte von nationaler Größenordnung die Vernetzung und Standardisierung im Kulturerbebereich angehen.

Ein weiteres zentrales Problem im Zusammenhang mit musikalischen Quellen besteht zudem darin, dass vorhandene, meist generische Vokabulare im Bereich der Musikinstrumente mithin starke Defizite (Konsistenz, Detailtiefe, Präzision) aufweisen. Die Möglichkeit, diese um wichtige Konzepte zu ergänzen, erscheint daher ebenfalls außerordentlich fruchtbar. Der praktische Nutzen einer solchen Möglichkeit wurde im Vorfeld dieser Arbeit in zahlreichen persönlichen Gesprächen mit Vertretern verschiedener Sparten sowie Forschenden verifiziert.

So ergeben sich zwei Hauptanliegen für diese Arbeit:

1) die Möglichkeit einer Vernetzung von musikinstrumentenbezogenen Daten verschiedener Sparten zu erproben.
2) auszuloten, in welcher Weise eine Anreicherung der vorhandenen Vokabulare möglich ist.

Einen technischen Lösungsansatz hierfür halten die sog. "Semantic Web-Technologien"[^265] bereit, indem sie es ermöglichen, Daten auch unabhängig von ihrem ursprünglichen Kontext miteinander in Beziehung zu setzen und interoperabel zu machen. Dank des ihnen zugrundeliegenden *RDF*-Modells (*Research Description Framework*) ist es bei Nutzung verschiedener etablierter Technologien des Internets möglich, im Netz gespeicherte Daten in semantische Beziehungen der Form 

*Subjekt – Prädikat – Objekt*

zueinander zu setzen und maschinenlesbar zu machen. Aus der Gesamtheit der an dieses semantische Netz angeschlossenen Daten, dem *Linked Data Cloud* lässt sich so ein eigenes anwendungsbezogenes Vokabular, ein sog. *Metadatenprofil*[^264] erzeugen, das imstande ist, als Schema für Vernetzung und Anreicherung musikinstrumentenbezogener Metadaten herzuhalten. Es könnte dabei als gedankliche Vorarbeit für eine anschließende Weiterentwicklung und Ausarbeitung durch die Fachcommunity fungieren.

[weiterentwickelbar – nicht abgeschlossen]

---

In methodischer Hinsicht ist die Entwicklung eines solchen Profils jedoch mit einigen Herausforderungen verbunden:

In RDF strukturierte Vokabulare existieren gewöhnlich als Endprodukt – Rückschlüsse auf die Modalitäten ihrer Genese (und somit methodische Ansätze für die Entwicklung eigener) bleiben dem Betrachter in der Regel verwehrt. Zudem ist der Vorgang der Modellierung stark prozessual und mitunter zirkulär geprägt, was das Gießen dieses Prozesses in die chronologische Form wissenschaftlicher Stringenz in Form einer wissenschaftlichen Arbeit sehr erschwert. (Da nicht jede Iteration dieser Genese umfassend im Rahmen dieser verschriftlichten Arbeit nachgezeichnet werden kann, wurde ein *GitHub*-Repositorium[^269] angelegt, in dem jeder Schritt dokumentiert und offen nachvollziehbar ist.)

Eine zusätzliche Herausforderung liegt in den auszuwertenden Quellen selbst begründet: Die Quellen, aus deren Termen sich das Metadatenprofil potentiell zusammensetzen könnte, umfasst die Gesamtheit der im Semantic Web enthaltenen. Eine philologische Auswertung ist daher schlichtweg unmöglich, und es werden alternative heuristische Lösungen gefunden werden müssen.
Umso schwerer wiegt es da, dass es an einführender Literatur, die imstande wäre – insbesondere Nicht-Informatikern –, einen Kompass im Prozess des Modellierens und Publizierens von Linked Data an die Hand zu geben, mangelt.[^268] 

Diese besonderen Rahmenbedingungen machen es erforderlich, dass sich die Arbeit in großen Teilen deduktiv vorantastet, wobei die Methodik anlassbezogen anhand der in der Praxis vorgefundenen jeweiligen Problemstellung zu entwickeln sein wird, so dass der methodische Faden im Laufe der Arbeit immer wieder aufzugreifen zu sein wird.

Eine weitere methodische Besonderheit, die gewissermaßen bereits im Wesen des Semantic Webs begründet liegt, ergibt sich aus der ihm eigenen sonderbaren Verschmolzenheit von Konzepten intellektueller Wissensrepräsentation und der Umstände ihrer technischen Manifestation, was eine losgelöste Betrachtung eines einzelnen dieser beiden Bestandteile nachgerade unmöglich macht. Dennoch erscheint es angesichts des hier behandelten konkreten Anwendungsfalls sinnvoll, im Folgenden einen gewissen inhaltlichen Schwerpunkt auf die intellektuelle Modellierung zu legen und technische Belange, wo immer möglich, auszuklammern.

Metadatenstandards werden nicht im Rahmen von studentischen Qualifikationsarbeiten verfasst, sondern entstehen etwa als wandelbare Ergebnisse langwieriger Community-getriebener diskursiver Prozesse.[^270] Das Ergebnis dieser Arbeit ist daher keineswegs das Fertigstellen einer umfassenden Ontologie der Musikinstrumente, ihrer Eigenschaften und ihrer ontologischen Beziehungen zur Welt. Vielmehr besteht ihr möglicher Sinn darin, einige Vorüberlegungen für eine potentielle anschließende Entwicklung eines ausdrucksstärkeren Vokabulars vorwegzunehmen, dabei gangbare methodische Wege zu kartieren und zuletzt einige – wenige – konkrete inhaltliche musikwissenschaftliche Vorarbeiten vorauszuschicken – welche insbesondere aber zur Illustration und zu Verifikationszwecken für die Stimmigkeit des Arbeitsansatzes bestimmt sind.

























Methodik (2 Ebenen):
    1. Semantic Web (<- kann man das hier abhandeln, oder sollte das ein eigenes Kapitel haben?)
    2. verwendete Terminologie
    3. eigentliche Methodik
        * Vorlage, systemisch inhärente Unvollendetheit






































































[^1]: [@van_der_meer_instrumentenkunde_nodate]
[^2]: [@Musicalinstrument]
[^3]: [@hyvonen_publishing_2012, S. 7–8.]
[^4]: [@gobel_gnd_2017, S.2.]
[^5]: Akronym blabla
[^6]: [@tomasi_modellieren_2018, S. 175.]
[^7]: Eine sehr umfassende Auseinandersetzung mit Chancen für Einrichtungen und Nutzer findet sich in: @waibel_think_2009.
[^8]: Eine phänomenologisch fundierte Thematisierung der Beziehung zwischen Wahrnehmungssubjekt und Musikinstrument findet sich in: [@de_souza_music_2017, S. 20–23.]

[^264]: [@alma99244375602586]
[^265]: [@noauthor_semantic_nodate]

[^266]: [@gobel_gnd_2017]
[^267]: [@altenhoner_nfdi4culture_2020]
[^268]: Einführende Werke zum Semantic Web und einzelner Vokabulare finden sich in @allemang_semantic_2011, @TN_libero_mab21631588, sowie @noy_ontology_nodate zur Modellierung von Ontologien. @hyvonen_publishing_2012 beinhaltet zudem gute Hinweise für die Publikation von Linked Data in Kulturerbeeinrichtungen.
[^269]: [@sparqlcrmsuppe_sparqlcrmsuppevocsforinstruments_2020]
[^270]: So bspw. die Prozesse zur Standardbildung des *W3C*, vgl.: @noauthor_world_nodate