**[Musikinstrumente im Semantic Web]{.smallcaps}**

[Entwicklung eines spartenübergreifenden Metadatenprofils]{.smallcaps}

Masterarbeit

an der

Hochschule für Technik Wirtschaft und Kultur Leipzig

Fakultät Informatik und Medien

Studiengang *Bibliotheks- und Informationswissenschaft*

vorgelegt von

Alan K. Riedel

*Leipzig 2020\
*

Kurzreferat der Arbeit:

Ziel dieser Arbeit ist es, einen Ansatz für ein semantisches Framework zu entwickeln, das seine Anwender in die Lage versetzt, musikinstrumentenbezogene Ressourcen aus Einrichtungen unterschiedlicher Sparten des Kulturerbes zueinander in Beziehung zu setzen, miteinander zu verbinden und dabei zugleich -- mittelbar -- bereits vorhandenes Vokabular um wichtige Aspekte anzureichern. Dies erfolgt -- ausgehend von einem relevanten Anwendungsszenario -- in Form einer Reihe eskalativer Modellierungen, im Zuge derer das Szenario in formale Sprachen aus dem Kontext des *Semantic Web* übersetzt wird. Dabei werden vorhandene semantische Lücken identifiziert und durch die Neuanlage und Publikation neuer Terminologie geschlossen. Es entstehen so eine Methodik und ein vorläufiges Vokabular (*www.purl.org/wumms*) als Grundlage für eine anschließende Community-basierte Ausarbeitung.

*Riedel, Alan: Musikinstrumente im Semantic Web : Entwicklung eines spartenübergreifenden Metadatenprofils \| Alan Riedel. -- Leipzig, 2020. --89 Bl. + 1 CD-ROM\
Masterarbeit, Hochschule für Technik, Wirtschaft und Kultur Leipzig, 2020*

***„Klassifikatorische Arbeiten sind allgemein etwas anrüchig."***

*(erster Satz in: Erich von Hornbostel, Curt Sachs: Systematik der Musikinstrumente, 1914)*

Inhaltsverzeichnis {#inhaltsverzeichnis .list-paragraph .TOC-Heading}
==================

[1 Einleitung 3]

[1.1 Vorbemerkungen 7]

[1.1.1 *Semantic Web*: Konzept 7]

[1.1.2 Terminologie 8]

[2 Ausgangssituation 11]

[2.1 Erschließung von Instrumentalbesetzungen -- Beispiel: RISM 11]

[2.2 Zielstellung 14]

[2.3 Anwendungsbeispiel 16]

[3 Modellierung mit RDF 18]

[3.1 Anwendungsmodellierung 18]

[3.1.1 Ausführungen zum Anwendungsmodell 20]

[3.1.2 „Domäne" 20]

[3.1.3 Mapping 21]

[3.1.4 Anreicherung 21]

[3.2 Formalisierte Modellierung 23]

[*3.2.1* *Entity Relationship Model* 24]

[3.2.2 Transformation mit *RDF*, *RDFS* und *OWL* 27]

[3.2.2.1 Vorgehensweise 29]

[3.2.3 Vokabular 30]

[3.2.3.1 Bemerkungen zum Vokabular 30]

[3.2.3.1.1 Namensraum und Benennung 30]

[3.2.3.1.2 Instanzen (owl:namedIndividuals) und Klassen (owl:class, rdfs:subClassOf) 31]

[3.2.3.1.3 Identifier 32]

[3.2.3.1.4 Attribute und Properties 33]

[3.2.3.1.5 Weitere Anmerkungen 33]

[3.2.4 Spezifizierung von Relationen mit *rdfs:range* und *rdfs:domain* 33]

[3.2.5 Vom Vokabular zur „Lightweight Ontology" 36]

[*4* Anbindung an- / Integration in das *Semantic Web* 37]

[4.1 Vorüberlegungen 37]

[4.1.1 Hintergrund 37]

[4.1.2 Semantische Verknüpfungsmöglichkeiten mit dem *Semantic Web* 38]

[4.1.2.1 1) Mapping 39]

[4.1.2.2 2) Integration von bereits etablierten externen Konzepten 40]

[4.1.3 Vorgehensweise 41]

[4.1.3.1 Terminologische Kontrolle / Modellierung / Methodik 42]

[4.2 Erfassung und Modellierung mit externen Vokabularen 43]

[4.2.1 Interpret und Aufführung 43]

[4.2.1.1 Interpret und Aufführung -- Relation 44]

[4.2.1.2 Personennormdaten 46]

[4.2.1.3 Modellierung von Zusammenhängen zwischen Musikinstrumenten, Interpreten und Aufführungen 46]

[4.2.2 Mapping und Klassifikation 48]

[4.2.2.1 „Medium of Performance" 48]

[4.2.2.2 Herausforderungen 51]

[4.2.2.3 Mapping 52]

[4.2.2.3.1 Szenario 1: Mapping über Klassifikation 52]

[4.2.2.3.1.1 Klassifikation 53]

[4.2.2.3.2 Szenario 2: direktes Mapping 53]

[4.2.2.3.3 Erkenntnisse aus der Modellierung 57]

[4.2.3 Klangbeispiel 57]

[4.3 Erfassung des Komplexes „Stimmungen" 61]

[4.3.1 Problemstellung 61]

[4.3.2 Stimmton 62]

[4.3.3 Stimmungssystem 62]

[4.3.4 Stimmung 63]

[4.3.5 Töne 65]

[4.3.5.1 Ton als Abstraktum 65]

[4.3.5.2 Ton als normativ fixiertes Zeichen 66]

[4.3.5.2.1 Taxonomie 66]

[4.3.5.2.2 Stimmton 67]

[4.3.5.3 Ton als physikalisches Phänomen 68]

[4.3.5.3.1 Modellierung Stimmhöhe / Referenzton 68]

[4.3.5.4 Tonraum (Ambitus) 69]

[4.3.5.5 Inferenzmöglichkeiten 70]

[4.4 Technische Nachbereitung / The Rise of wumms: 71]

[5 Schluss 73]

[5.1 Anwendungssimulation 73]

[5.1.1 Modellierung 73]

[5.2 Fazit 77]

[6 Verwendete Literatur 80]

[6.1 Externes Bildmaterial 89]

Einleitung {#einleitung-1}
==========

Musikinstrumente sind schwer zu fassende Phänomene, deren „Wesen" sich situativ und je nach Blickwinkel[^1] sehr unterschiedlich -- etwa materiell, immateriell, medial oder performativ -- ergeben kann.[^2] Hinzu kommt, dass sie mit ihrem Bezugspunkt „Musik" (zumeist primär) in Abhängigkeit zu einem gleichermaßen immateriellen, hochgradig ambivalenten und damit für Kulturerbeinstitutionen ohnehin außerordentlich schwierig fassbaren Gegenstand stehen.[^3] Trotzdem spielen Musikinstrumente in verschiedenen solcher Einrichtungen eine Rolle -- sei es als Museumsobjekt, als Besetzungsangabe einer Quelle, als Instrument in einer Aufnahme oder als Term in einem Vokabular etc.

Es liegt dabei auf der Hand, dass sich das Konzept „Musikinstrument" eingedenk der sparten- und institutionsspezifischen Betrachtungsweise unterscheiden muss: Eine „Objekt-zentrierte Herangehensweise" wird womöglich ganz andere Aspekte jenes Konzepts hervorheben -- etwa physische oder ereignisbezogene -- als eine bibliographische. Und so ist es nicht verwunderlich, wenn konzeptuelle Modelle und Vokabulare verschiedener Kulturerbesparten -- etwa Museen, Archive, Bibliotheken etc. -- mitunter inkompatibel sind.

Dabei bärge vor dem Hintergrund eines digitalisierten *GLAM*-Bereichs[^4] eine Vernetzung von Beständen, dessen Prämisse jene Kompatibilität bildet, bekanntlich einiges an Potential: So könnten etwa Bestandsmetadaten durch Kontextualisierung nach außen zusätzlich in Wert gesetzt werden, die Übernahme von Fremddaten zur Anreicherung eigener Datensätze erleichtert werden,[^5] neue -- womöglich bestandsübergreifende -- Suchmöglichkeiten und -Einstiege für den Nutzer geschaffen,[^6] Bestände virtuell zusammengeführt und sichtbarer gemacht werden.[^7] Für Forscher, etwa Editionswissenschaftler oder Digital Humanists, ergibt sich neben der Nutzung und Auswertung von hochwertigen Metadaten die Möglichkeit, eigene Forschungsdaten in diesem Austausch beizutragen. Die Aktualität und Relevanz dieses Anliegens im geisteswissenschaftlichen Bereich offenbart sich dabei etwa darin, dass mit den Projekten GND4C[^8] sowie im NFDI4Culture-Konsortium (insb. „Task Area 2")[^9] gleich zwei Projekte von nationaler Größenordnung die Vernetzung und Standardisierung im Kulturerbebereich angehen.

Ein weiteres zentrales Problem im Zusammenhang mit musikalischen Quellen besteht zudem darin, dass vorhandene, meist generische Vokabulare im Bereich der Musikinstrumente mithin starke Defizite (Konsistenz, Detailtiefe, Präzision) aufweisen. Eine Möglichkeit, diese möglichst einfach um wichtige Konzepte zu ergänzen, erscheint daher ebenfalls außerordentlich nützlich. Der praktische Nutzen einer solchen Möglichkeit wurde im Vorfeld dieser Arbeit in zahlreichen persönlichen Gesprächen mit Vertretern verschiedener Sparten sowie Forschenden eruiert. Dabei wurde deutlich, dass kleinere Institutionen und Forschungsprojekte oftmals spezielle Bedürfnisse bei der Erschließung oder Publikation ihrer Forschung besitzen -- ihnen die Teilhabe an der Entwicklung von Standardvokabular jedoch verwehrt ist. Für sie ist es wichtig, Möglichkeiten zu finden, diese Teilhabe dennoch niederschwellig zu ermöglichen.

So ergeben sich zwei übergeordnete Anliegen für diese Arbeit:

1)  Diese Arbeit soll die Möglichkeit einer Vernetzung von musikinstrumentenbezogenen Daten verschiedener Sparten erproben.

2)  Sie soll dabei ausloten, in wie weit eine Nachnutzung vorhandener Vokabulare möglich ist und dabei erörtern, an welchen Stellen noch Defizite bestehen.

Technisch gesehen versprechen die *Semantic-Web*-Technologien[^10] eine Handhabe, um diese Anliegen zu verwirklichen. Dank des ihnen zugrundeliegenden *RDF*-Modells (*Research Description Framework*) ist es bei Nutzung verschiedener bereits etablierter Technologien des Internets möglich, im Netz gespeicherte Daten in semantische Beziehungen zueinander zu setzen und dabei interoperabel und maschinenlesbar zu machen. Aus der Gesamtheit der an dieses semantische Netz angeschlossenen Daten, der *Linked Data Cloud*, lässt sich so ein eigenes anwendungsbezogenes Schema, ein sogenanntes „*Metadatenprofil"*[^11], erzeugen, das imstande ist, als Schema für Vernetzung und Anreicherung musikinstrumentenbezogener Metadaten zu dienen. Dieses könnte dabei als gedankliche Vorarbeit für eine anschließende Weiterentwicklung und Ausarbeitung durch eine Fachcommunity fungieren. Dank der semantischen und technischen Offenheit des *Semantic Web* ist dabei terminologische Anschlussfähigkeit und die Darstellung sehr spezifischer Sachverhalte möglich.

\*\*\*

In methodischer Hinsicht ist die Entwicklung eines solchen Profils jedoch mit einigen Herausforderungen verbunden:

Nach *RDF* strukturierte Vokabulare liegen gewöhnlich „als Endprodukt" vor -- Rückschlüsse auf die Modalitäten ihrer Genese (und somit methodische Ansätze für die Entwicklung eigener) bleiben dem Betrachter in der Regel verwehrt. Zudem ist der Vorgang der Modellierung dynamisch und mitunter zirkulär geprägt, was das Gießen dieses Prozesses in eine chronologische Form sehr erschwert. (Da nicht jede Iteration der Genese umfassend im Rahmen der verschriftlichten Variante dieser Arbeit nachgezeichnet werden kann, wurde in einem *GitHub*-Repositorium[^12] jeder Schritt nebenbei dokumentiert und offen nachvollziehbar gemacht.)

Eine zusätzliche Herausforderung liegt in den auszuwertenden Quellen selbst begründet: Die Quellen, aus deren Termen sich ein Metadatenprofil zusammensetzen könnte, umfasst potentiell das gesamte *Semantic Web*. Eine philologische Auswertung ist somit ausgeschlossen, und es werden im Laufe der Arbeit alternative heuristische Lösungen vorgeschlagen.[^13]

Diese besonderen Rahmenbedingungen machen es erforderlich, dass sich die Arbeit in großen Teilen deduktiv vorantastet, wobei die Methodik anlassbezogen anhand der in der Praxis vorgefundenen jeweiligen Problemstellung entwickelt wird.

Eine weitere methodische Besonderheit, die gewissermaßen bereits im Wesen des *Semantic Webs* begründet liegt, ergibt sich aus der ihm eigenen sonderbaren Verschmolzenheit von repräsentiertem Wissen und dessen technischer Manifestation im Netz, was eine losgelöste Betrachtung eines einzelnen dieser beiden Bestandteile nachgerade unmöglich macht. Dennoch erscheint es angesichts des hier behandelten konkreten Anwendungsfalls sinnvoll, einen gewissen inhaltlichen Schwerpunkt auf die Modellierung zu legen.

Metadatenstandards entstehen als wandelbare Ergebnisse langwieriger diskursiver, Community-getriebener Prozesse.[^14] Der Sinn dieser Arbeit liegt daher insbesondere darin, Vorüberlegungen für die potentielle Entwicklung eines ausdrucksstärkeren Vokabulars anzustellen, dabei gangbare methodische Wege zu kartieren und zuletzt den entworfenen Ansatz anhand konkreter musikwissenschaftlicher Vorarbeiten zu illustrieren und zu verifizieren.

\*\*\*

Nachdem in Kapitel 1.1 einige wichtige Grundlagen in Form einer kurzen Einführung in das Grundprinzip des *Semantic Web* (1.1.1) und einiger terminologischer Vorüberlegungen (1.1.2) geschaffen sind, erfolgt in Kapitel 2 eine Beschreibung von Problemstellung und Ziel dieser Arbeit. Dabei werden, ausgehend von der Erschließung der Hörner im *RISM*-Datensatz zu J. S. Bachs Kantate BWV 208, Möglichkeiten und Grenzen der gebräuchlichen Terminologie aufgezeigt und kritisch bewertet (2.1). Aus diesen Erkenntnissen lassen sich terminologische Potentiale definieren (2.2), die imstande sind, komplexe Sachverhalte wiederzugeben und dabei kraft der Möglichkeiten des *Semantic Web* Ressourcen spartenübergreifend miteinander zu vernetzen (2.3). Vom diesem in 2.3 skizzierten, noch recht vagen praktischem Anwendungsszenario ausgehend, folgt in Kapitel 3 eine eskalative Reihe von Formalisierungen, an deren Anfang eine Fokussierung des Szenarios und ihre Überführung in ein „Anwendungsmodell" steht (3.1). Diesem folgt die formale Fixierung in Form eines *Entity Relationship Model* (3.2.1), das seinerseits die Grundlage für die anschließende *RDF*-Modellierung bietet (ab 3.2.2). Durch die Erfassung mit den formalen Sprachen *RDF*, *RDFS* und *OWL* entsteht dabei ein erstes Vokabular (3.2.3) in Form einer *lightweight ontology* (3.2.4, 3.2.5). In Kapitel 4 erfolgt die systematische „Übersetzung" des so geschaffenen Vokabulars in im *Semantic Web* etablierte Terminologie, wodurch eine Anschlussfähigkeit auf semantischer Ebene erreicht wird. Dies betrifft insbesondere die Bereiche „Interpret und Aufführung" (4.2.1), „Mapping und Klassifikation" (4.2.2) und „Klangbeispiel" (4.2.3). Da im Folgenden jedoch auf keine weiteren etablierten Vokabulare zurückgegriffen werden kann, gilt es im Bereich der „Stimmungen" (4.3) eigene Terminologie zu schaffen. Dazu erfolgt eine Kartierung und Modellierung der relevanten Konzepte (4.3.1--4.3.5). Einen besonderen Raum nimmt dabei der Komplex „Ton" ein (4.3.5), vereint er doch in sich als Klasse Konzepte ganz unterschiedlicher (im)materiellen Beschaffenheit. Die Publikation des geschaffenen Metadatenprofils ***SeMantic MUsical instrument Web*** (*wumms:*) bildet den Schluss des Modellierungsprozesses, indem nun auch eine technische Anbindung ans *Semantic Web* (4.4) geschaffen wird. Im folgenden Schlussteil der Arbeit (Kapitel 5) erfolgt zunächst anhand einer Nachmodellierung des in Kapitel 2.2 und 2.3 entworfenen Szenarios eine probeweise Anwendung des entstandenen Metadatenprofils (5.1). Zuletzt fasst das Kapitel (5.2) die Erkenntnisse der vorhergehenden Arbeit zusammen und zeigt mögliche Ansatzpunkte für eine Community-basierte Weiterentwicklung des Metadatenprofils auf.

Vorbemerkungen {#vorbemerkungen-1}
--------------

### *Semantic Web*: Konzept

Das *W3C* erklärt die Grundidee des *Semantic Webs* folgendermaßen: „The Semantic Web provides a common framework that allows data to be shared and reused across application, enterprise, and community boundaries."[^15][^16] Dabei wird das Grundprinzip des Internet --mittels *HTML*-Links miteinander *vernetzte* Seiten --, dem *Web of Documents*, auf den Inhalt dieser Seiten übertragen und erweitert. Das herkömmliche *Web of Documents* ist lediglich ein „\[...\] set of interlinked documents with heterogeneous syntax and semantics and uncontrolled content\[...\]":[^17] Dessen Inhalt ist also nicht einheitlich und somit nicht interoperabel und maschinenlesbar. Im *Web of Data* hingegen können auch einzelne „Sinnträger" innerhalb einer Seite (also „Data" innerhalb eines „Documents") dank einer standardisierten „Syntax", dem *Ressource Description Framework* (*RDF*), in vielfältige semantische Beziehung zu „Sinnträgern" auf anderen Seiten gesetzt werden.

Die vormals auf die Beziehung

*Seite A* - *verlinkt auf* - *Seite B*

beschränkte Aussagekraft von HTML wird durch *RDF* um komplexe Aussagemöglichkeiten erweitert. *RDF* charakterisiert die Beziehungen von Daten zueinander durch sogenannte „Tripel" mit semantischem Gehalt in der Form

*Subjekt* - *Prädikat* - *Objekt*.

Dabei können die Bestandteile dieser Aussagen sowohl Subjekt oder Objekt neuer Aussagen werden. Dank der Verwendung von *RDF* und bereits etablierter Webinfrastruktur und -Standards sind *Semantic Web*-konform strukturierte und publizierte Daten als *Linked Data* maschinenlesbar und interoperabel und können in beliebige Beziehungen gesetzt werden.

### Terminologie

Aufgrund der inkonsistenten Verwendung von Begriffen im Kontext des *Semantic Web* sollen einige grundlegende Begriffe für die Verwendung in dieser Arbeit kurz definiert werden. Für ausführlichere terminologische Betrachtungen wird auf weiterführende Literatur[^18] verwiesen.

-   Die Elemente *Subjekt* → *Prädikat* → *Objekt* ergeben einen gerichteten Graphen. Der Oberbegriff für die einzelnen, nun kontextuell losgelöst gedachten Elemente lautet in dieser Arbeit gemäß Stuckenschmidt *Konzepte*.[^19]

-   Die „Kanten" des Graphen, die also je nach Kontext *Subjekt* oder *Objekt* sein können, heißen im Folgenden *Entitäten*, wobei diese *Entitäten* sowohl „Dinge", als auch „Mengen von Dingen" sein können.[^20]

-   Etwas weniger einheitlich wird mit dem Element *Prädikat* verfahren: er wird, je nach Kontext, als *Property,* *Relation* oder *Eigenschaft* bezeichnet.

-   Kaum ein anderer Begriff ist in derartige Ambivalenz gehüllt, wie der Begriff „Ontologie",[^21] sodass eine Definition für diese Arbeit höchstens näherungsweise erfolgen kann.

> Oftmals werden im Kontext des *Semantic Web* in der englischsprachigen Literatur die Begriffe *Ontologie* und *Vokabular* synonym verwendet.[^22] Diese Arbeit hebt diese prinzipielle Synonymität für sich auf und nimmt eine qualitative Unterscheidung der Begriffe anhand Funktion und Struktur vor, wie sie auch in der deutschsprachigen Bibliothekswelt geläufig erscheint: Ihr zufolge handelt es sich beim Begriff *Vokabular* um „\[...\]die Verzeichnung aller (allgemeinen oder fachspezifischen) Benennungen zur Nutzung als Wissensordnung \[...\]."[^23] Ihre Funktion besteht im Augenblick ihrer Nutzung darin, kontrolliertes Vokabular vorzuhalten. Für diese spezielle Nutzung kann nach Auffassung dieser Arbeit eine Ontologie mitunter ebenfalls verwendet werden. Als Charakteristika von Ontologien gegenüber anderen Systemen der Wissensorganisation werden in dieser Arbeit hingegen vor allem die folgenden Aspekte aufgefasst:

-   formalisierte Sprachlichkeit und Maschinenlesbarkeit[^24] bzw. die Möglichkeit automatisches Schlussfolgern (*Reasoning*) zu vollziehen.[^25]

-   Vieldimensionalität und inhärente größtmögliche Flexibilität als Ordnungssystem in Bezug auf Beziehungsmöglichkeiten[^26]

-   ein hohes Maß an Komplexität (das etwa durch die Existenz einer „light"-Variante, der sog. *lightweight ontology* nahegelegt wird (s. Kapitel 3.2.5))

```{=html}
<!-- -->
```
-   Die Bezeichnung *Metadatenprofil* (auch „Anwendungsprofil", „Applikationsprofil") impliziert -- ähnlich wie im Falle von „Vokabular" -- insbesondere eine funktionale Qualität für eine bestimmte Anwendung. Es handelt sich beim *Metadatenprofil* um ein Metadatenschema,[^27] in dem typischerweise Elemente von bereits existierenden Modellen und Standards kombiniert werden und so ein für einen bestimmten Anwendungsfall optimiertes Metadatenschema geschaffen wird.[^28] Da in dieser Arbeit gelegentlich auch eigene Terminologie geschaffen und anschließend im Metadatenprofil vorgehalten wird, weist das hier entwickelte Metadatenprofil auch Eigenschaften eines Vokabulars auf.

-   Das *Semantic Web* in seiner ursprünglichen visionären Konzeption[^29] wird oftmals als gescheitert betrachtet.[^30] Der Begriff wird hier daher als Bezeichnung für den *de facto* Ist-Zustand verlinkter Daten im Netz verwendet. Der Begriff *Linked Data* wird hingegen als qualitative Bezeichnung für jene Art von Daten verwendet, die gemäß den Beschreibungen in Kapitel 1.1.1 strukturiert und veröffentlicht sind. Diese Verwendung erfolgt dahingehend in Abgrenzung zum Begriff *Linked Open Data*, indem letzterer als insbesondere auf rechtliche Aspekte der Nachnutzbarkeit bezogen verstanden wird.

Ausgangssituation
=================

Erschließung von Instrumentalbesetzungen -- Beispiel: *RISM*
------------------------------------------------------------

*Im folgenden Kapitel soll exemplarisch die derzeitige Situation* bei der Erschließung von Quellen mit musikinstrumentenbezogenen Metadaten untersucht und anhand dieser Untersuchung zu einer Problemstellung gefunden werden. Die Kenntnis dieser Problemstellung bildet wiederum die Grundlage für das Entwickeln denkbarer Lösungsansätze in Form des Metadatenprofils.

Als Grundlage für diesen Prozess dient J. S. Bachs sog. *Jagdkantate* BWV 208[^31] als Beispiel, wobei die Demonstration grundlegender ontologischer Strukturen eine spätere Übertragung des in der Arbeit entwickelten Modells als zulässig erscheinen lässt.

Die Untersuchung wählt dabei eine Datensatz von *RISM* (*Répertoire International des Sources Musicales*) -- „\[...\] ein länderübergreifendes, gemeinnützig orientiertes Unternehmen mit dem Ziel, die weltweit überlieferten Quellen zur Musik umfassend zu dokumentieren"[^32] -- als ihren Ausgangspunkt. Diese Wahl erscheint naheliegend, stellt *RISM* doch für die Musikwissenschaft das wichtigste Nachweissystem von historischem musikalischem Quellenmaterial (insb. bis etwa 1850) dar.

Es finden sich im Datensatz zu BWV 208[^33] an drei Stellen Informationen zur Besetzung: Zum einen unter „Quellenbeschreibung / Originaler Titel" (MARC-Feld \#245\$a (Title))[^34] der String „Cantata â 4 Voci. 2 Corni di Caccia. 2 Violini una Viola è Cont.\[?\]". Hinzu kommt ein sehr allgemeiner Besetzungshinweis, der hier angesichts seiner Funktion als Kurzform aber ausgeklammert werden kann.

![Besetzung1]

Abbildung 1: Angabe der Besetzung von BWV 208 beim RISM[^35]

Zum anderen unter „Weitere Angaben und Bemerkungen" im Unterfeld „Besetzung" (MARC-Feld \#594\$a (freies Feld))[^36].

![Besetzung2]

Abbildung 2: Angabe der Besetzung von BWV 208 beim RISM

Bei diesen Bezeichnungen handelt es sich um ein kontrolliertes Vokabular.[^37] Mehreres fällt an dieser Stelle auf:

1)  Die Bezeichnungen der Instrumente in Originaltitel und im Feld „Besetzung" weichen voneinander ab (etwa „Corn\[o\] da Caccia" vs. "cor da caccia").

2)  Die Besetzungsangaben in den *MARC/XML*- bzw. *RDF/XML*-Dateien ist als String nicht „maschinenverstehbar".[^38]

3)  Auch auf der Benutzeroberfläche sind die (teils kryptischen) Abkürzungen nicht mit einem Vokabular oder einer disambiguierenden Seite verlinkt.

4)  Die Bezeichnung *cor da caccia*[^39] ist ungebräuchlich und somit als normierter Term -- zumal ohne Disambiguierung -- wenig geeignet.

Die Vieldeutigkeit des Terms *cor da caccia* lässt sich dabei auch durch eine Internetrecherche nicht einfach lösen: Die Google-Suche[^40] ergibt neben Treffer zum *Corno da caccia* vor allem Treffer zu Oboen-Instrumenten wie der *Oboe da Caccia*, dem *Englischhorn* oder zu einem modernen trompetenartigen *Corno da Caccia* mit Ventilen.[^41]

Tatsächlich handelt es sich bei der Frage um die Verwendung von Blechblasinstrumenten in der Musik Bachs um auch in der Musikwissenschaft umstrittene Fragestellungen.[^42] Doch lassen sich durch Konsultation des autographen Quellenmaterials[^43] durchaus gewisse verbindliche Aussagen treffen:

![Ein Bild, das Text enthält. Automatisch generierte Beschreibung]

Abbildung 3: Autograph des Anfangs von BWV 208

-   Die Instrumente sind in F gestimmt -- das in F-notierte „eingestrichene *c"* (*c'*) entspricht, dies wird im Bezug zum Basso Continuo deutlich, dem klingenden „kleinen *f"* (*f*).

-   Es handelt sich aufgrund der stereotypen Stimmführung zwischen den Instrumenten keineswegs um oboenartige Instrumente, sondern um Blechblasinstrumente.

-   Angesichts der Lage und der Stellung der Naturtöne lässt sich eine Aussage zu Länge des Instruments und spielbarem Ambitus treffen -- der trompetenartige Typ des *Corno da caccia* scheidet aus.

-   Eingedenk der raumzeitlichen Dimension in der das Stück entstanden ist, ließen sich Verbindungen zu ähnlichen erhaltenen Instrumenten herstellen.

Gleichwohl eine solche Erschließungstiefe nicht notwendigerweise bei der bibliothekarischen Katalogisierung vorausgesetzt werden kann, handelt es sich bei diesen Schlüssen doch um wesentliche Informationen, die eine Disambiguierung -- eigentlich Sinn und Zweck eines kontrollierten Vokabulars -- in diesem Fall überhaupt erst ermöglichen. Doch auch eine alternative Benennung als „Corno da Caccia" würde wenig zur eigentlichen Begriffsbestimmung beitragen können. Es wird deutlich, dass sich die semantische Eindeutigkeit der hier untersuchten Entität vor allem durch ihre Eigenschaften (Stimmung, Lage etc.) und ihrer Beziehungen zu anderen Entitäten (etwa dem historischen Instrumententyp, der sich in einem Objekt manifestieren könnte) ergibt. Mit diesen Bezügen versehen, hätte der Term *cor da caccia* trotz der Uneindeutigkeit seiner Bezeichnung eine aussagekräftige Bedeutung.

Zugleich existieren weitere Informationen, deren Abbildung im Digitalisat für den Nutzer zwar relevant sein könnten, sich aber mit den etablierten herkömmlichen Mitteln der Erschließung nicht nachbilden ließen.

Zielstellung
------------

Mit Blick auf die am Beispiel des *RISM*-Datensatzes identifizierten Mängel und Chancen lassen sich mehrere Schlüsse ziehen:

1)  Neben der aufgezeigten Unschärfe ist das Vokabular nicht öffentlich einsehbar -- eine terminologische Kontrolle ist somit nicht nachvollziehbar. Um die Möglichkeit einer Verwendung von alternativem Vokabular auszuloten, wäre eine philologische Auswertung verfügbarer Klassifikationen und Taxonomien bzw. entsprechender Crosskonkordanzen hinsichtlich ihrer Präzision und Anwendbarkeit erfolgsversprechend.[^44]

2)  Es lassen sich noch eine Vielzahl weiterer -- wie gezeigt wurde: durchaus signifikanter -- Aussagen zum verwendeten Instrumentarium treffen.

3)  Standardisiertes, maschinenlesbares Vokabular würde ermöglichen, solcherlei Aussagen in eindeutiger Weise treffen zu können.

4)  Eine spartenübergreifende Verlinkung -- etwa zu einem Beispielobjekt -- ist derzeit nicht möglich, jedoch erstrebenswert.

Somit birgt das Fehlen von Ausdrucksfähigkeit in Bezug auf bestimmende Eigenschaften von Musikinstrumenten und deren Vernetzung enormes Potential und bildet mangels entsprechender Vorarbeiten ein wichtiges Desiderat.

In Kapitel 2.1. waren dabei einige Eigenschaften benannt worden, die als bestimmende Eigenschaften des *cor da caccia* (und zwar jenes Typs, der in BWV 208 Verwendung finden sollte) identifiziert worden waren. Dies waren etwa[^45]:

-   Stimmung[^46]

    -   sowohl Pedalton[^47]

    -   als auch Stimmhöhe[^48]

    -   als auch Temperatur[^49]

-   Instrumententyp (also etwa als Mapping zur Hornbostel und Sachs-Systematik[^50])

-   Ambitus

-   historische Äquivalente, oder, falls bekannt, Objekt -- etwa in der Datenbank von *Musical Instrument Museums Online* (*MIMO*).[^51]

Darüber hinaus wären -- je nach Verwendungskontext -- weitere Eigenschaften denkbar, wie:

-   Verwendung in BWV 208

-   Interpret

-   etc.

Die kontrollierte, maschinenlesbare Darstellbarkeit dieser Eigenschaften in Bezug zu einer ohne sie allzu undifferenzierten und unspezifischen Entität *cor da caccia* wird es sein, die als Indikator für ein Gelingen des Ziels dieser Arbeit auf praktischer Ebene fungiert. Zugleich trägt die gemeinsame Anwendung von Aspekten aus unterschiedlichen Domänen, wie sie oben abgebildet sind[^52], eine implizite vorläufige Aussage zur Vernetzbarkeit und den Chancen, die diese birgt, in sich.

Anwendungsbeispiel {#anwendungsbeispiel-1}
------------------

Mit dem RISM-Datensatz als exemplarischer Ausgangspunkt wäre etwa das folgende Szenario denkbar: Entweder innerhalb des Datensatzes eingeblendet, oder als Verlinkung aus dem String *cor da caccia* (mit oder ohne den beschriebenen zusätzlichen Informationen) heraus ließe sich, kraft *Semantic-Web*-Technologien, die Kombination geeigneter Eigenschaften aufrufen. Möglich wären weitere Verlinkungen etwa zu ähnlichen Sammlungsobjekten, zu disambiguierenden Normdaten oder zu weiteren nützlichen Informationen, wie relevanten Personennormdatensätzen, Klangbeispielen, historischen Abbildungen (etwa in der *RIdIM*[^53] Datenbank[^54] oder in der *Deutschen Digitalen Bibliothek*[^55]), lizenzfreies Notenmaterial (beispielsweise auf *IMSLP*[^56]) etc. Umgekehrt erzielt eine Suche mit einer entsprechenden Kombination indizierter Terme -- etwa über die RISM SPARQL-Schnittstelle[^57] -- zumindest den erwähnten Datensatz als Treffer. Eine wesentlich differenziertere und vielfältigere Suche über Spartengrenzen hinweg wäre somit ermöglicht. Zugleich böten auch Ressourcen aus Einrichtungen anderer Sparten Zugangspunkte, die ihrerseits wiederum -- etwa ausgehend von einem Museumsobjekt -- aufeinander und auf die Bestände von *RISM* zeigte und zueinander in semantische Beziehung setzte.

![Ein Bild, das Text, Karte enthält. Automatisch generierte Beschreibung]

Abbildung 4: Spartenverbindender Sucheinstieg und Möglichkeiten der Informationsanreicherung\
am Beispiel RISM

Modellierung mit RDF
====================

Anwendungsmodellierung
----------------------

Bevor eine Formulierung in *RDF* vorgenommen werden kann, ist es sinnvoll, die in Kapitel 2.2 lediglich angerissenen Anforderungen nochmals zu schärfen und aus ihnen ein Modell zu generieren, das als diskursive Grundlage für die spätere Ausarbeitung herhalten kann. Dies soll in einem zweistufigen Prozess geschehen, währenddessen zunächst ein informelles Anwendungsmodell generiert wird, aus dem anschließend ein formalisiertes Datenmodell in Form eines *ERM*s (*Entity Relationship Model*) abgeleitet werden kann. Dieses wiederum wird die Grundlage für die *RDF*-Modellierung bilden. Dieses Vorgehen gewährleistet, dass sich das Anwendungsprofil zunächst ausschließlich an den tatsächlichen in der Praxis vorgefundenen Erfordernissen ausrichtet und sich nicht etwa „in vorauseilendem Gehorsam" anhand im *Semantic Web* bereits vorhandener Darstellungsmöglichkeiten bildet und dabei selbst zensiert. (In Vorgriff auf die terminologische Ausarbeitung (ab Kapitel 4.2) heißt dies etwa: domänenspezifische Vokabulare dahingehend zu untersuchen, ob sie in der Lage sind, das Geforderte abzubilden und andernfalls nach Möglichkeiten zu suchen, diese Darstellungsmöglichkeiten selbst zu schaffen.) Jedoch darf diese initiale scheinbare Übersimplifizierung, die zunächst also jederlei Eindeutigkeit -- etwa in Form von Normdaten -- vermeidet, keineswegs als solche missverstanden werden. Vielmehr bildet sie die eigentliche Prämisse für spätere grundsätzliche terminologische Anschlussfähigkeit und Interoperabilität, indem sie sich nicht auf bestimmte gebräuchliche Datenstrukturen oder eine bestimmte Domäne fixiert.

![Datenmodell -- Beziehungen ausgedrückt als Verbindungslinien zwischen den umkreisten Entitäten]

Abbildung 5: Datenmodell -- Beziehungen ausgedrückt als Verbindungslinien zwischen den umkreisten Entitäten. (Eigene Grafik, CC0)

### Ausführungen zum Anwendungsmodell

### „Domäne"[^58]

1)  Dies wird etwa im Falle der Entität *BWV 208* deutlich: Das „Label" „BWV 208" referenziert im Anwendungsmodell die Kantate auf Werkebene und fungiert als Platzhalter[^59] für eine Expression[^60] (etwa der in RISM beschriebenen Quelle),[^61] eine Manifestation[^62] (etwa eine Edition), oder aber auch eines Exemplars[^63] (etwa einer, freilich verdammenswerterweise, mit Bleistift eingerichteten Ausgabe in einer Bibliothek).

2)  Über die Beziehung „Besetzung" mit der Entität Werk verbunden ist die Entität *Corno da caccia*, im Modell mit dem -- willkürlichen -- Label „cor da caccia", der Terminologie von RISM folgend, versehen. Auch an dieser Stelle ist das Label völlig flexibel -- analog also zur Entität *BWV 208*.

3)  Bei der Entität *MIMUL Inv.-Nr. 1663*[^64] handelt es sich um ein Objekt, das in dieser Arbeit exemplarisch als materielles Gegenpart zum Term „cor da caccia" geführt wird.[^65]

Die Entitäten dieses Bereichs sind institutions-, sparten- und domänenspezifisch bereits etabliert und stehen daher für dieses Metadatenprofil nicht zur Disposition. Das spätere Datenmodell wird daher an dieser Stelle keinen präskriptiven Charakter für sich beanspruchen können. Jedoch werden entsprechende Beispielentitäten aus der Kulturerbe-Domäne im Folgenden angelegt, um Anschlussfähigkeit des Metadatenprofils an diese Domäne simulieren und prüfen zu können.

### Mapping

Beim Mapping-Anteil steht einerseits die Vernetzung zwischen Objekt und Werk im Vordergrund, zum anderen kann hier die Disambiguierung unklarer Terminologie erfolgen. Die Anbindung der Besetzungsentität *Corno da caccia* an die Objekt-Entität kann in zweierlei Weise erfolgen:

-   durch ein direktes In-Beziehung-Setzen zwischen Term und Objekt. Hier sind mehrere Arten der Beziehung denkbar:

```{=html}
<!-- -->
```
-   Einerseits könnte es sich beim Objekt um exakt jenes handeln, das Bach für das Werk besetzt hatte.[^66].

-   In den meisten Fällen jedoch wird eine dermaßen eindeutige Beziehung nicht nachzuvollziehen sein. Vielmehr wird -- wie ja auch im Falle von BWV 208 -- auf ein ungefähres Äquivalent zu verweisen sein.

4)  durch das Mapping über eine zwischengelagerte Klassifikation. Dieses erscheint etwa im hier verwendeten Falle sinnvoll, um den Term „cor da caccia" weiter zu disambiguieren.

### Anreicherung

Nachdem die Besetzungsentität durch Verknüpfung mit einem Objekt bzw. einer Klassifikation eindeutig bestimmt worden ist, ist es wünschenswert, sie durch weitere Aussagen anzureichern und dadurch noch aussagekräftiger zu machen.

5)  Die Hörner sind im Autograph „in F" notiert -- der tatsächliche Klang der in F notierten Töne der Hornstimme liegt also eine Quinte tiefer. Dies wird durch die Beziehung der Besetzungsentität zu ihrer relativen Stimmung „in F" ausgedrückt. Auch für das Objekt könnte bekannt sein, dass es in F gestimmt ist (= das Instrument produziert Töne der sog. *Naturtonreihe* über dem Ton *f*).

> Aus diesem Umstand lassen sich -- zumindest für die Zeit bis zur Erfindung des Ventilhorns -- sehr facettierte Aussagen zum vorgesehenen Instrument treffen (Länge, Mensur etc.), deren Darstellung jedoch für den begrenzten Rahmen dieser Arbeit keine Rolle spielen kann. Außerdem liefert die Angabe der Stimmung der Hörner -- ebenfalls begrenzt auf die Zeit bis zur Erfindung des Ventilhorns -- einen Indikator für die Bestimmung der Tonart (wie auch im Fall von BWV 208: Die Kantate steht in F-Dur).

6)  Der Besetzungsentität ist in ihrer Eigenschaft als Besetzung für *BWV 208* ein bestimmter Tonvorrat zu eigen, der sich durch die Entität *Ambitus* ausdrückt. Diese Tonmenge kann implizit durch die beiden Entitäten des höchsten und des tiefsten Tons ausgedrückt werden.

> Die Kenntnis des Ambitus' lässt in wissenschaftlicher Hinsicht vielerlei Rückschlüsse zu: etwa auf die Länge des Instruments (Faustregel: kürzer = Tonvorrat liegt höher). Für Musiker (etwa Anfänger) könnte diese Information außerdem etwa bei der Suche nach Noten nützlich sein.

7)  Das Bestimmen historisch verwendeter Stimmungssysteme ist in vielen Fällen nicht eindeutig möglich. Aus physikalischen Gründen ist das Stimmungssystem des *Corno da caccia* jedoch eindeutig und kann hier berücksichtigt werden.[^67]

8)  Über die Stimmhöhe der ursprünglich vorgesehenen Instrumente, wie auch für das Objekt *MIMUL 1663*, lässt sich keine eindeutige Aussage treffen. Gleichwohl ist diese Entität grundsätzlich durchaus als aufschlussreich für die Wissenschaft anzusehen.[^68] Somit handelt es sich bei der Angabe *a'* = 415 Hz (diese Arbeit verwendet die sog. *Helmholtz*-Notationsweise[^69] für Tonbezeichnungen) um einen vermuteten Wert, und es ergibt sich für den Fortgang der Arbeit die Frage, ob es in einem späteren Datenmodell möglich sein wird, auch Ambivalenzen und Unsicherheiten dieser Art abzubilden.

9)  Über die Beziehung „Klangbeispiel" ist es möglich, die Objektentität oder die Typ-Entität mit einem Klangbeispiel zu verknüpfen. Selbstverständlich wäre dies im gleichen Maße auch für eine Werkentität denkbar.

10) Denkbar ist, dass eine Person -- etwa im Rahmen einer Audioaufnahme -- auf einem bestimmbaren Instrument spielt. Hier wäre also eine Verknüpfung zwischen Besetzung (evtl. Werk), Person und Objekt wünschenswert.

Tatsächlich sind den potentiellen Anwendungsszenarien eines solchen Modells keine Grenzen gesetzt. Angesichts der Komplexität und der vielfältigen spezifischen Anforderungen, die trotz der Beschränkung auf BWV 208 und das *Corno da caccia* erarbeitet wurden, lässt sich bestenfalls erahnen, welches Darstellungspotential eine Erweiterung des Modells für andere Instrumente und Instrumentengruppen bergen könnte: Es ließe sich etwa die Skordatur von Saiten ausdrücken. Oder verschiedene Sing- und Spieltechniken -- vom Jodeln bis zum Spiel *con sordino* etc.

Formalisierte Modellierung
--------------------------

Das folgende Kapitel bildet den Ausgangspunkt dafür, den Weg von einem auf dem Reißbrett entworfenen Anwendungsszenario zu einem formalisierten, *Semantic-Web*-kompatiblen Metadatenprofil zu beschreiten. Gemäß Noy und McGuinness[^70] steht dabei ganz zu Beginn des Prozesses hin zur Ontologie zunächst eine Klassierung[^71] der benötigten Typen nach folgendem Schema:

> „Define the classes and the class hierarchy"[^72]
>
> „Define the properties of classes \[...\]"[^73]
>
> „Create instances"[^74]

Tatsächlich hat sich im Verlauf dieser Arbeit ganz organisch eine andere Reihenfolge ergeben: Nach dem exemplarischen Auffinden eines Defizits wurde ein spezifisches Szenario entworfen, um dieses zu beheben: Einige wichtige Instanzen[^75] wurden bereits im vorhergehenden Kapitel identifiziert und aufgeführt.

Das Produkt dieses Kapitels bildet eine zunächst auf den Anwendungsbereich beschränkte „Ontologie", die auf sehr elementarer Ebene imstande ist, das Anwendungsszenario mit formalisierten Sprachen wiederzugeben.

### *Entity Relationship Model*

Ein erster möglicher Schritt in Richtung einer Modellierung mit *RDF* ist die Überführung des Anwendungsmodells in ein *Entity Relationship Model* (*ERM*). Wichtig ist gleich eingangs darauf hinzuweisen, dass auch das *ERM* zunächst lediglich eine Eskalationsstufe auf dem Weg zur *RDF*-„Ontologie" darstellt, das wohl, wie auch das „Anwendungsszenario" dynamischen Veränderungen unterliegen wird. Hierbei sollen die anwendungsspezifischen Szenarien strukturiert und auf eine allgemeine Ebene gesetzt werden, auf der übergeordnete Entitätsklassen und ihre Eigenschaften in Beziehung zueinander stehen.[^76] So werden Klassen definiert und erste einfache hierarchische Relationen zwischen Klassen und untergeordneten, „beschreibenden" Klassen (Eigenschaften) hergestellt.

Beziehungen wiederum können in diesem *ERM* ebenfalls zunächst als potentielle zukünftige „Eigenschaftsklassen" verstanden werden, die zukünftig Container für weitere „Untereigenschaften" darstellen können.[^77] Im *ERM* fungieren besondere Schlüsseleigenschaften („Primärschlüssel") als eindeutige Identifier einer Entität. Es ist zu erwarten, dass diese in einer *RDF*-Modellierung keine Rolle spielen werden, da dort eindeutige Referenzierbarkeit bereits dank sog. *Universal Ressource Identifier* (*URI*) (gegeben ist.[^78] Mengenverhältnisse zwischen Entitäten werden im *ERM* zudem durch „Kardinalitäten" miteinbezogen und dadurch fixierbar.[^79]

![Entity Relationship Modell: farbige Markierung externer Entitäten. Entitäten sind in Rechtecken, Eigenschaften in Ovalen, Beziehungen in Rauten eingefasst. Schlüsseleigenschaften sind durch Unterstreichung gekennzeichnet.]

Abbildung 6: Entity Relationship Model: farbige Markierung externer Entitäten. Entitäten sind in Rechtecken, Eigenschaften in Ovalen, Beziehungen in Rauten eingefasst. Schlüsseleigenschaften sind durch Unterstreichung gekennzeichnet.

Einige wesentlichen Entwicklungen gegenüber dem Anwendungsmodell sowie weitere Überlegungen sind es wert, nochmals kurz erläutert und erörtert zu werden.

-   Den Entitäten des *ERM* sind gegenüber denen der Anwendungsmodellierung weitere beschreibende Eigenschaften hinzugefügt worden (etwa *Name* zu *Person*).

-   Neben dem verwendeten Instrument *Instrument nach Vokabular* muss die Entität *Interpret* auch immer an ein Ereignis, in der Regel eine *Aufführung* geknüpft sein (diesem Umstand wurde durch die Zusätze im linken Domänenbereich Rechnung getragen). Dabei sind folgende Szenarien berücksichtigt: ein Instrument kann sowohl mehrfach („n Mal") mit beliebig vielen *Interpreten* besetzt sein (entspricht beispielsweise der Bezeichnung „2 Oboen" oder „Celli" in einer Partitur) als auch gesondert aufgeführt werden (entspricht etwa dem Sachverhalt „Musiker a und Musiker b spielen vierhändig Klavier").

-   Die Verknüpfung zwischen Ereignis und Werk kann in gleichem Maße auch für Ereignis und Objekt gelten -- etwa, wenn ein bestimmtes Objekt in einer Aufführung verwendet wird. Dieser Sachverhalt ist zur besseren Übersichtlichkeit im *ERM* **nicht** dargestellt! Es wird an späterer Stelle umgesetzt.

-   Ein *Instrument nach Vokabular* kann innerhalb eines Werks beliebig viele notierte *Stimmungen* besitzen.[^80]. Die Bedeutung der Entität *Stimmung* -- etwa mit dem Wert „F" -- weicht dabei in der Kombination mit *Instrument* von der der Verwendung in Kombination mit *Objekt (Domäne)* ab: In dieser Kombination bezieht sich die Entität *Stimmung* auf die mögliche „Grundstimmung" eines Objekts (z.B. F-Horn), sofern es eine besitzt (s. auch Kapitel 4.3.4).[^81]

-   Mithilfe einer Kombination gegebener Informationen zu *Stimmung* und notiertem *Ambitus* sollte es im Zuge eines späteren Schrittes möglich sein, Informationen zu den *klingenden Tönen* maschinell abzuleiten (s. Kapitel 4.3.5.5).

-   Im *ERM* ist definiert, dass ein *Instrument nach Vokabular (Domäne)* nur eine (variable) *Stimmhöhe* besitzen kann. Denkbar wären jedoch auch z.B. Sachverhalte -- Konzerte, Aufnahmen etc. -- in deren Verlauf mehrmals umgestimmt wird. In diesen Fällen wäre auch eine Verknüpfung mit der Entität *Aufführung* angebracht. Um den Umfang dieser Arbeit jedoch in Grenzen zu halten, kann nicht jedem denkbaren Szenario in ihr Rechnung getragen werden. Vielmehr würden sich solche tiefergehenden Überlegungen im Rahmen einer Weiterentwicklung des Metadatenprofils empfehlen.

-   Grundsätzlich ist wünschenswert -- wie im Fall des *Interpreten* oder dem Umstimmen von Instrumenten -- bestimmte Entitäten mit Ereignissen verknüpfen zu können. Dies gilt insbesondere für die Entitäten *Stimmungssystem* (wird mit historisch akkurater oder wohltemperierter Stimmung gespielt?), *Stimmhöhe* (wird mit den heute üblichen 440 Hz musiziert, oder mit einer historischen Stimmung, z.B. gemäß dem sog. *Cornettton*[^82]?), *Klangbeispiel* (Das Klangbeispiel stammt aus der Aufnahme x) und *Instrument (Klassifikation)* (bei der Uraufführung fand Instrument a Verwendung, in der Aufnahme x ein Typ-verschiedenes).

Für die Zwecke dieser Arbeit genügt es, die zuletzt genannten Anwendungsszenarien im *ERM* einmal exemplarisch im Kontext des *Interpreten* umzusetzen.

### Transformation mit *RDF*, *RDFS* und *OWL*

Das zuletzt ausgearbeitete Modell befindet sich gewissermaßen noch jenseits der durch das *Semantic Web abgesteckten Wissensstrukturen*. Diesen Erkenntnishorizont zu überwinden und eine minimale semantische Anschlussfähigkeit zu erreichen, ist das Anliegen dieses Kapitels. Für diesen Zweck ist es erforderlich, die Konzepte des *ERM* nochmals zu hinterfragen.

Der Vorgehensweise im weiteren Verlauf liegt zugrunde, dass im *RDF* bereits bestimmte Klassen angelegt sind, die in Folgevokabularen[^83] ergänzt wurden. Diese Klassen können verwendet werden, um Konzepte zu klassifizieren.[^84] Angesichts der zuvor ausgearbeiteten Anwendungsmodellierung sind die allgemein gebräuchlichsten drei Klassen[^85] für diese Arbeit zweckmäßig. Diese sind:

1.  Klassen

2.  Instanzen

3.  Relationen (im Folgenden auch „Properties", „Eigenschaften")

Gegenüber dem *ERM* bildet im *RDF* das Konzept von Attributen keine ausgezeichnete eigene Entitätsklasse mehr, kann doch jede *RDF*-Entität auch als Subjekt eines Tripels agieren (somit erscheint das von seiner Bezugsentität abhängige und auf ihn verweisende Attribut mit *RDF* inkompatibel). Durch die Aufteilung in (theoretisch also gleichgestellte) Entitäten und Beziehungen lassen sich bereits vollwertige *RDF*-Tripel bilden. Zusätzlich gelingt es dank der qualitativen Unterscheidung in Instanz und Klasse, einfache hierarchische Sachverhalte nachzubilden. In den folgenden Unterkapiteln wird es nun darum gehen, eine entsprechende Klassierung am Gegenstand der erarbeiteten Konzepte vorzunehmen.

Doch worin besteht an dieser Stelle der tiefere Sinn einer Klassifikation?

Bertram beschreibt eine „erkenntnisvermittelnde Aufgabe" von Klassifikationen, die in der „Aufhellung von Zusammenhängen anhand geordneten Wissens"[^86] besteht (im Gegensatz also zur gewohnten „pragmatische\[n\] Aufgabe"[^87] von Klassifikationen zur Ordnung und zum Retrieval von Ressourcen). Diese hermeneutische Dimension ist ein zentraler Aspekt der *RDF*-Klassifizierung: Das Modell, das in seiner gegenwärtigen Form auf einem subjektiv geprägten Verständnis, Wertesystem und persönlichen Denkstrukturen des Autors beruht, wird in ein objektives, standardisiertes System überführt. Gewissermaßen findet so eine Übersetzung statt, die den Erkenntnishorizont zwischen Mensch und -- einer gemäß formalisierter Strukturen „denkenden" Instanz -- der „Maschine" überwindet. Das eigene Denkmodell wird dabei mithilfe der formalsprachlichen Ausdruckmittel des *Semantic Web* erfasst und ausgezeichnet, und so in das von *RDF*-vorgegebene „Erkenntnisschema" einsortiert. Die dem Modell inhärente Semantik wird dadurch objektiviert und gemeinhin auslegbar.

#### Vorgehensweise

Diese Übersetzung wird mithilfe entsprechend standardisierter, sich ergänzender Modellierungssprachen, den sogenannten „Ontologiesprachen", realisiert.[^88] Die durch den W3C standardisierten „Grundpfeiler" des *Semantic Web* bilden dabei insbesondere die Sprachen *RDF*,[^89] *RDF Schema* (*RDFS*)[^90] und der *Web Ontology Language* (*OWL*)[^91], der „inzwischen \[...\] meistbenutzen Ontologiesprache aller Zeiten"[^92]).

Die formale Interpretierbarkeit der durch die Sprache ausgedrückten semantischen Komponenten wird durch eine Syntax, also einer „Menge von Regeln, um Programme oder Dokumente mit bestimmten Eigenschaften \[...\] zu erzeugen",[^93] ermöglicht. Die Entscheidung für eine bestimmte Syntax kann dabei im Falle nach *RDF* strukturierter Daten arbiträr erscheinen -- bilden sie doch im übertragenen Sinne gewissermaßen lediglich „Verpackung und Beipackzettel" für den eigentlichen semantischen Inhalt -- doch hat die (weiter-)Entwicklung der Syntaxen bedarfsorientierte, nuancierte Eigenschaften hervorgebracht. Aufgrund seiner Einfachheit und Übersichtlichkeit fällt die Wahl in dieser Arbeit auf die sogenannte *Terse RDF Triple Language* (*Turtle*)[^94].

Dabei erfolgt die Disambiguierung der Konzepte analog zur Klassifizierung in folgender Form (s. auch Kapitel 3.2.3.1.2):

-   „Typ ist eine Klasse"

-   „Typ ist eine Instanz"

-   „Typ ist eine Eigenschaft"[^95]

Durch die klassifikatorische Erfassung der Instanzen, Entitäten und Beziehungen aus der Anwendungsmodellierung bzw. der Klassen, Eigenschaften und Beziehungen des *ERM* ergibt sich ein sehr einfaches kontrolliertes Vokabular. Durch die Zuordnung von Instanzen zu Klassen ergeben sich zudem erste taxonomische Beziehungen.[^96] Mithilfe der Klassifizierung mit der Eigenschaft `rdf:type` werden zudem ontologische Aussagen zu den Einzelkonzepten getroffen. So werden alle konzeptuell-kategorialen Verhältnisse innerhalb des Erkenntnishorizonts des *Semantic Web* formalsprachlich übersetzt und verstehbar.

### Vokabular

Das gemäß den eben beschriebenen Maßgaben strukturierte und ausgezeichnete Vokabular ist durch Publikation im Online-Repositorium dieser Arbeit[^97] im Netz referenzierbar und kann dort abgerufen werden.

#### Bemerkungen zum Vokabular

##### Namensraum und Benennung

Auch wenn keine abschließenden Definitionen der hier geschaffenen Terme erstellt worden sind, lässt sich bereits jetzt die Aussage treffen, dass ihr semantischer Gehalt sich darin ausdrückt, wie sie in dieser Arbeit Verwendung finden. Es ist möglich, diese freilich bislang nicht außerordentlich aussagekräftige, doch trotzdem insofern definierte und abgrenzbare semantische Reichweite von Vokabular im Bezug zu sogenannten *Namensräumen*[^98] -- referenzierbare kontrollierte Vokabulare -- festzulegen. Die Namensraumzugehörigkeit der Terme dieser Arbeit wird im Folgenden zunächst durch das Präfix *ma:* gekennzeichnet. Der Namensraum ist unter

https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma,

hinterlegt.

Eine menschenlesbare Definition der einzelnen Terme, wie sie als gute Praxis gemäß dem W3C (*World Wide Web Consortium*) nahegelegt wird,[^99] wäre aufgrund der zu erwartenden Dynamik, der die Terminologie noch unterworfen sein muss, zum gegenwärtigen Zeitpunkt noch verfrüht.[^100]

##### Instanzen (owl:namedIndividuals) und Klassen (owl:class, rdfs:subClassOf)

Die bei der Differenzierung zwischen Klasse und Instanz (owl:namedIndividual)[^101] oftmals vorgeschlagene Vorgehensweise,[^102] bei der die niedrigste Entität eines aus Klassen bestehenden hierarchischen Strangs als Instanz zu werten ist, bei der Modellierung in sich abgeschlossenen Ontologie sinnvoll. Im Fall einer -- wie hier beabsichtigten -- Anwendung als verbindendes Metadatenprofil muss sie auch auf potentielle Anknüpfungspunkte erweitert werden. Dazu gehören insbesondere auch die Anwendungsfälle und Vokabulare, die „außerhalb" des Profils liegen. Die Frage also, ob etwas eine als Instanz oder eine Klasse zu verstehen ist, liegt nicht notwendigerweise in der hierarchischen Ebene begründet. Im Falle des *Barockhorns* wird dies insbesondere deutlich:

    ma:Barockhorn_(Mitteldeutschland)	rdf:type	owl:Class ;
                                 rdfs:subClassOf ma:Instrument_(Klassifikation) .

Es ist einleuchtend, dass die Bestimmung einer Klasse (Barockhorn) als Instanz, auch wenn sie sich auf der untersten hierarchischen Ebene befindet, nicht zweckmäßig ist.[^103]

##### Identifier

Während in einer relationalen Datenbank das Schlüsselattribut einer Entität variabel sein kann, erfolgt die eindeutige Referenzierung von Konzepten -- darunter auch Entitäten -- im *Semantic Web* grundsätzlich anhand von *URI*s (*Uniform Ressource Identifier*).[^104] Eine konzeptuelle Trennung zwischen Entität und seinem eindeutigen Identifier, wie im *ERM*, ist im *Semantic Web* nicht denkbar: Die URI selbst erscheint vielmehr gewissermaßen als digitale Manifestation des durch sie repräsentierten nichtdigital existierenden Konzepts. URIs sind also im Gegensatz zur Repräsentation im *ERM* keine eigenständigen Informationen (in Form von Attributen) mehr, sondern sie „sind" die Konzepte:

Bei den syntaktischen Elementen der Aussage

    ma:Klangbeispiel rdf:type owl:Class .

etwa sind die Konzepte mit ihrem jeweiligen Namensraum präfigiert und über den Header der Datei zu vollständigen URIs auflösbar:[^105]

Header:

    @\prefix ma: <https://github.com/SPARQLCRMSUPPE/VocsForInstruments/blob/master/namespaces/ma#> .
    @\prefix owl: <http://www.w3.org/2002/07/owl#> .
    @\prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#&gt> .

löst auf zu den URIs:

    https://github.com/SPARQLCRMSUPPE/VocsForInstruments/blob/master/namespaces/ma#klangbeispiel,
    http://www.w3.org/2002/07/owl#class und 
    http://www.w3.org/1999/02/22-rdf-syntax-ns#type

##### Attribute und Properties

-   Ein Nebeneffekt der Transformation des *ERM* nach *RDF* ist, dass Attribute von Entitäten von diesen als nunmehr eigenständige Entitäten entkoppelt sind, und somit dem *ERM* entsprechende Tripelbeziehungen nicht möglich sind. Dieses Problem lässt sich in der Regel einfach lösen, indem entsprechende Entitäten und Properties erschaffen werden.

##### Weitere Anmerkungen

-   Analog zur Definition von Klassen (owl:Class) und Unterklassen (rdfs:subclassOf) ist es mit *RDFS* möglich, Untereigenschaften (rdfs:subPropertyOf) zu Eigenschaften zu bilden.[^106] Dies ist im Falle der Eigenschaften *genaue Entsprechung* und *ungefähre Entsprechung* nützlich, indem sie der Eigenschaft *Entsprechungsgrad* subsumiert werden.

-   Aus Gründen der Kohärenz und der klassifikatorischen Konsolidierung wurde eine Oberklasse `ma:Ton` eingeführt.

### Spezifizierung von Relationen mit *rdfs:range* und *rdfs:domain*

Eines der zentralen Konzepte des *Semantic Web* ist die sog. *open world assumption*.[^107] Gemäß dem vielzitierten Leitsatz „Anyone can say anything about anything"[^108] besagt sie, dass eine Aussage, die in einem Modell nicht explizit verankert ist, nicht notwendigerweise falsch sein muss, sondern dass lediglich keine Aussage über ihre Richtigkeit getroffen werden kann.[^109] Es muss somit im Interesse eines *RDF*-Vokabulars liegen, sein semantisches Ausdruckspotential fort von der Summe alles Möglichen (und somit Willkürlichen) hin zum eigentlich Aussagekräftigen zu fokussieren, indem es Hinweise zur sinnhaften Verwendung seiner Terme bereithält. Die Möglichkeit einer solchen Fokussierung bieten Ontologiesprachen wie *RDFS* und *OWL*, indem sie in *RDF* formalisierte und somit direkt integrierbare „Anwendungsregeln" zu Properties anbieten.[^110] Es liegt dabei auf der Hand, dass für ein Applikationsprofil, dessen Sinn darin besteht, schematische Rahmenbedingungen zu schaffen, entlang derer sich Anwender ausrichten und orientieren können, ein hohes Maß an semantischer Starrheit unabdingbar ist.

Doch wird kraft dieser Schemata keineswegs lediglich Wirkungspotential -Grenzen von Relationen abgesteckt. Vielmehr entsteht durch sie eine weitere Bedeutungsdimension, die die Grundlage dafür bietet, auch maschinell inhärente logische Schlussfolgerungen (Inferenzen) ziehen zu können (*Reasoning)*.[^111]

Während im Vokabular *Properties* in Form kontingenter, semantisch ungerichteter Bestandteile einer Liste aufgezählt wurden, kann im Folgenden ihre Anwendung in Abhängigkeit zu den durch sie in Relation gesetzten Entitäten näher beschrieben werden.[^112] Diesen Schritt zu vollziehen, ermöglichen die Properties *rdfs:range*[^113] und *rdfs:domain*[^114].[^115]

1)  Die Wirkung dieser begrenzenden *Properties* wird im folgenden Beispiel verdeutlicht:

Obwohl die Aussage

    ma:Person_a	 ma:hat_Frequenz	ma:Lizenz .

angesichts der *open world assumption* legitim ist, ist es sinnvoll die Anwendung von `ma:hat_Frequenz` gemäß Anwendungsmodell nur auf bestimmte Subjekte und Objekte auszurichten. Im Szenario

    ma:a'	ma:hat_Frequenz	ma:415Hz .

bezieht sich `ma:hat_Frequenz` auf ein Subjekt aus der Klasse `ma:Ton` -- zum anderen auf ein Objekt der Klasse Frequenz (mit weiteren möglichen Instanzen, wie 415 Hz etc.). Somit lässt sich mit der Zuweisung

    ma:hat_Frequenz 		rdfs:domain 	ma:Ton .
    ma:hat_Frequenz 		rdfs:range 		ma:Frequenz .

bestimmen, dass im Profil das Property mit einem Subjekt aus der Klasse `ma:Ton` und einem Objekt aus der Klasse `ma:Frequenz` verwendet werden sollte.

Diese Beschränkungen werden dabei, wie bereits kurz angedeutet, in folgender Form direkt in das Vokabular integriert (dabei wird das Property `ma:hat_Frequenz` zum Subjekt folgender dreier Tripel):

    ma:hat_Frequenz	rdf:type		owl:ObjectProperty ;
    rdfs:domain		ma:Ton ;

>     rdfs:range 		ma:Frequenz .

2)  Durch die Bestimmung der Wirkungsweise von `ma:hat_Frequenz` ist es im Folgenden möglich aus einer Aussage mehrere weitere Aussagen zu inferieren: Aus dem Tripel

```{=html}
<!-- -->
```
    example:x ma:hat_Frequenz example:y

wäre es für eine *Reasoning*-Applikation nun möglich, abzuleiten, dass es sich bei `example:x` um eine Entität der Klasse `ma:Ton` und bei der Entität `example:y` um eine Entität der Klasse `ma:Frequenz` handeln muss.

-   Eine direkte Überführung des *ERM* mit `rdfs:domain` und `rdfs:range` ist nur im Falle bestimmter Properties -- nämlich derjenigen, die in Bezug zu nur einem einzigen Subjekt und Objekt stehen (etwa `ma:hat_Ambitus`) -- möglich. Das Property `ma:Interpret` etwa bezieht sich auf mehrere Subjekte. Eine Aussage in der folgenden Form ist jedoch problematisch:

```{=html}
<!-- -->
```
    ma:Interpret	rdf:type		owl:ObjectProperty ;
    rdfs:domain		ma:Instrument_nach_Vokabular_(Domäne) ;

>     rdfs:domain		ma:ma:Objekt_(Domäne) ;
>
>     rdfs:domain		ma:Aufführung_(Domäne) ;
>
>     rdfs:range		ma:Person      		.

Aus diesem Sachverhalt scheint sich inferieren zu lassen, dass jede Instanz der Klasse `ma:Person` immer auch einer Instanz von `ma:Objekt`, `ma:Instrument_nach_Vokabular` sowie `ma:Aufführung` zugleich zugeordnet ist.[^116] Eine Aussage, wie

„Person a ist an dem Ereignis 'Uraufführung' beteiligt (spielt jedoch nicht auf dem Museumsobjekt b)"

wäre demnach nicht möglich.

Eine Lösung bietet die Möglichkeit, eine übergeordnete Klasse für die Entitäten `ma:Instrument_nach_Vokabular` sowie `ma:Objekt` zu erschaffen und die Verwendung von `ma:Interpret` mit `rdfs:domain` auf diese Oberklasse (`ma:Instrument`) zu beschränken.[^117] Die Koppelung von Person und Ereignis ist hingegen eine allgemein gültige. Somit lautet die neue Definition von `ma:Interpret`:

    ma:Interpret	rdf:type		owl:ObjectProperty	;
        				rdfs:domain		ma:Instrument	;
        				rdfs:domain		ma:Aufführung	;
        				rdfs:range       	ma:Person      .

Bezugnahme auf die neue Superklasse `ma:Instrument` kann nun auch auf analoge Sachverhalte im Falle von `ma:hat_Stimmung_(absolut)`, `ma:hat_Stimmungssystem` sowie `ma:hat_Klangbeispiel` angewendet werden.

### Vom Vokabular zur „Lightweight Ontology"

Die *open world assumption* bringt es mit sich, dass eine Validierung von in *RDF* strukturierten Daten nicht vorgesehen ist.[^118] Hieran ändert auch -- trotz des Namens -- *RDFS* kaum etwas: „Unlike XML Schema, RDF Schema is generally interpreted as supplementing rather than validating RDF data."[^119] Dennoch sind die Möglichkeiten von *RDFS* -- etwa gegenüber dem sehr viel mächtigeren, dafür aber umso komplexeren *OWL DL* -- für die Belange dieses Metadatenprofils angemessen,[^120] nicht zuletzt da es gilt, Überkomplexität aufgrund seiner Anwendungs- und Anwenderorientiertheit zu vermeiden.[^121] Man spricht in solchen Fällen von sogenannten „lightweight ontologies", die „in der Regel nur aus einer Konzepthierarchie sowie Relationen, für die jeweils Domain und Range Einschränkungen \[sic!\] angegeben werden\[, bestehen\]."[^122]

Anbindung an- / Integration in das *Semantic Web*
=================================================

Vorüberlegungen
---------------

### Hintergrund

In den vorangegangenen Kapiteln wurde ein Modell in eine strukturell auf *RDF* basierende Ontologie „übersetzt". Deren „Grammatik" orientierte sich zwar an der im *Semantic Web* standardisierten (*RDF*, *RDFS*, *OWL*) mit dem Ziel einer anschließenden Integration im *Semantic Web*. Doch bleiben die in dieser Ontologie verwahrten Konzepte, durch die Brille eines fiktiven „*Semantic-Web*-Subjekts" betrachtet, diffus: es handelt sich lediglich um eine Menge arbiträrer Entitäten, die in bestimmten, jedoch außerordentlich allgemeinen Beziehungen stehen. Es gilt insofern an dieser Stelle abermals einen hermeneutischen Prozess zu durchlaufen, in dessen Zuge die nicht-explizierten Konzepte im Namespace `ma:` dermaßen erschlossen werden, dass sie für ein erkennendes Subjekt -- gleich welcher Art -- interpretierbar werden. Abermals stellt sich, wie bereits in Kapitel 3.2.2 die Frage, in welcher Weise das bisherige Modell dessen Verständnisdimension zugeführt werden kann. Dies ist für ein menschliches Subjekt relativ einfach zu beantworten, etwa indem Konzepte mit sinnvollen Namen und Erklärungen versehen werden. Doch wie verhält es sich mit einem Subjekt, das nur die Sprache des *Semantic Web* beherrscht („things not strings")?[^123]

Hier erscheint ein kurzer Seitenblick in die philosophische Ontologie hilfreich: Eine zentrale Idee der Heidegger'schen Philosophie ist, dass das „eigentliche Wesen" von „Zeug"[^124] (im Gegensatz etwa zu Platons Ideenlehre) keineswegs diesem a priori inhärent ist, sondern sich in der Welt erst in seiner kontextuellen habituellen Funktionalität und Materialität gegenüber einem erkennenden Subjekt äußert.[^125] Diese Annahme erscheint auch hier aufschlussreich: Kontext -- im Sinne von Beziehungen zwischen Konzepten -- bildet im *Semantic Web* die Prämisse von Semantik. Das „Wesen" der Konzepte liegt keineswegs in ihrer textuellen Beschreibung („strings") begründet, sondern in ihrer Rolle als Sinnträger innerhalb eines Bedeutungsgefüges und gegenüber einem „besorgenden" Wahrnehmungssubjekt.

So ist etwa das Wesen des Konzepts „Klavier" in den folgenden *RDF*-Tripeln ein je anderes:

1)  „Mann" „spielt auf" „Klavier"

2)  „Klavier" „fällt auf" „Mann"

Neben dem offensichtlichen, hier variablen grammatikalischen „Wesen", Subjekt und Objekt, liegt im ersten Beispiel das Wesen des Klaviers darin begründet, dass es „der Gegenstand" ist, „mit dem man musiziert". Im zweiten ist es jedoch „das gigantische Ding, das durch Kollision existentielle Grenzerfahrungen auslöst". Exakt analog hierzu erscheint das "Wesen\" einer Entität innerhalb einer formalen Welt dadurch bestimmt, in welchen Relationen sie zu der sie umgebenden, wechselwirkenden Welt steht. Und umgekehrt: löst man Konzepte aus diesem Gefüge heraus (wie es bislang in dieser Arbeit der Fall ist), entbindet man sie ihrer semantischen Kraft, und sie werden, im schlimmsten Fall, zu nichts weiterem als zu kontingenten URIs, jedenfalls aber -- zumindest nach Heidegger -- zu einem trivialen lediglich „Vorhandenen".[^126]

### Semantische Verknüpfungsmöglichkeiten mit dem *Semantic Web*

Es stellt sich nun die Frage, wie diese Kontextualisierung konzeptionell umzusetzen ist. Orientierte sich diese Arbeit bislang insbesondere an den Texte *Ontology Development 101*[^127] und Stuckenschmidts *Ontologien*[^128] für die Erstellung von Ontologien im Sinne abstrakter formalisierter Wissensrepräsentationen, so finden sich in der Literatur kaum Hinweise zur semantischern Kontextualisierung eigener Ontologien im *Semantic Web*.

Einen Hinweis liefert Hyvönen, indem er drei Bestandteile einer (*Semantic-Web*)-"Ontologieinfrastruktur" ausmacht:

-   *Domain independent vocabularies are needed for facilitating cross-domain interoperability. For example, thesaurus standards and the W3C Semantic Web recommendations RDF(S), SKOS, and OWL fall into this category, as well as generic metadata schemas, such as Dublin Core.*

-   *Domain specific ontologies \[...\]. For example, the Getty Vocabularies (AAT, TGN, and ULAN), the Library of Congress Subject Headings (LCSH), and other vocabularies used for annotating contents fall in this category.*

```{=html}
<!-- -->
```
-   *Institution specific ontologies are needed for concepts that may be relevant for a particular organization only or cannot be shared for some reason with a larger community\[...\].*[^129]

Anhand dieser Bestandsaufnahme lassen sich mehrere Aussagen schlussfolgern: Neben der auf technischer Ebene wichtigen Information, dass eine im *Semantic Web* integrierte Ontologie sich aus verschiedenen Vokabularen aus verschiedenen Bereichen zusammensetzt (ja zusammensetzen sollte),[^130] halten diese Informationen auch Hinweise auf die Frage nach semantischer Kontextualisierung bereit: Eine Ontologie erhält ihre Aussagekraft indem sie sich in den Kontext bereits etablierter Vokabulare stellt. Dabei sind die etabliertesten diejenigen, die das höchste Maß an Verständlichkeit anbieten -- domänen- und institutionsspezifische die, die das höchste Maß an semantischer Spezifität zu erreichen imstande sind.

Freilich ist hierdurch nur wenig über den eigentlichen semantischen Prozess der Verknüpfung eigener Ontologien im *Semantic Web* ausgesagt. Die Empfehlung der *Semantic Web*-Pioniere Bizer, Heath und Berners-Lee[^131] hingegen, „\[to s\]et RDF links to other data sources on the Web, so that clients can navigate the Web of Data as a whole by following RDF links\[...\]",[^132] bietet einige konkrete Hinweise für diese Umsetzung:

#### 1) Mapping

In etwa analog zur Klassifizierung von Konzepten in Kapitel 3.2.2 können eigene Konzepte in Relation zu externen, etablierten Konzepten gesetzt werden, und diese Relationen als Eigenschaft in der *RDF*-Beschreibung des Konzepts fixiert werden. Der bisherige Verständnishorizont wäre somit für eine Anwendung, die das Metadatenprofil parsed, überwunden, und ein Konnex zwischen Metadatenprofil und *Semantic Web* geschaffen.\
Ein *vorläufiges* Beispiel:

`ma:Klangbeispiel  rdfs:subclassOf <http://d-nb.info/gnd/4052020-1> .`

In Worten: Der Term „Klangbeispiel" im `ma:`-Namespace wird als Unterklasse des in der *Gemeinsamen Normdatei* (*GND*) definierten Schlagworts „Schallaufzeichnung" verstanden.

Das Property `rdfs:subclassOf` verlinkt dabei die Entität `ma:Klangbeispiel` in eine externe, bereits im *Semantic Web* eingebundene und semantisch etablierte „Ontologie", die Gemeinsame Normdatei, sodass nun also auch die Entität `ma:Klangbeispiel` (freilich erst nach Publikation im Netz) in das *Semantic Web* integriert ist.

Neben Integration durch hierarchische Relation (bspw. `rdfs:subclassOf`) kommen auch Äquivalenzrelationen für diesen Verlinkungsvorgang infrage. Insbesondere das Vokabular SKOS („Simple Knowledge Organization System")[^133] hat sich etabliert, um etwa Thesauri in *RDF* zu überführen,[^134] jedoch insbesondere auch um Vokabulare und Ontologien aufeinander zu beziehen[^135] (*ontology alignment*,[^136] Mapping). Hierfür sind etwa die Properties

`skos:exactMatch`, `skos:narrowMatch`, `skos:broadMatch`, `skos:closeMatch`

besonders geeignet. Deutlich wird aber zugleich, dass die Ambivalenz dieser Properties (ausgenommen `skos:exactMatch`) groß ist und daher womöglich keine endgültig befriedigende semantische Eindeutigkeit ermöglichen kann.

#### 2) Integration von bereits etablierten externen Konzepten

Während für die Integration ins *Semantic Web* das Mapping zu äquivalenten Termen anderer Vokabulare generell sinnvoll ist, erscheint es angesichts von Funktionsweise und Architektur des *Semantic Web* im Falle des Metadatenprofils als nicht erstrebenswert. Obwohl die Produktion von Doubletten (und anschließendem Mapping) im Sinne der *open world assumption* nicht „falsch" ist,[^137] so sind redundante Datensätze doch eingedenk der Konzeption des *Semantic Web* als offene, ins Netz ausgelagerte „Datenbank", in dem jeder Datensatz für jeden zugänglich und referenzierbar ist, unsinnig, ist doch Kontextualisierung durch den Rekurs auf semantisch etablierte und somit aussagekräftige Konzepte, wie bereits mehrfach betont, sogar außerordentlich wünschenswert. Diese Aussagekraft erhöht sich weiter durch Wiederverwendung etablierter Konzepte und der Vermeidung von konkurrierenden Redundanzen: „it is considered good practice to reuse terms from well-known *RDF* vocabularies \[...\] wherever possible in order to make it easier for client applications to process Linked Data. Only if these vocabularies do not provide the required terms should data publishers define new, data source-specific terminology \[...\]."[^138] Zu guter Letzt wird so „\[...\]die Einheitlichkeit und Interoperabilität der Beschreibungen sicher\[gestellt\]."[^139]

So erfolgte also die semantische Verknüpfung des Konzepts `ma:Ton` mit dem *Semantic Web* nicht nach dem in Kapitel 4.1.2.1 erwähnten Schema `ma:Ton  skos:exactMatch gnd:Ton .,` sondern besser einfach durch Übernahme des Konzepts `gnd:Ton` anstelle von `ma:Ton`.

### Vorgehensweise

Für den Fortgang dieser Arbeit erscheint die folgende allgemeine Vorgehensweise sinnvoll:

1)  Das verbleibende, institutionsübergreifende Vokabular im Namespace `ma:` ist daraufhin zu untersuchen, ob sich seine Semantizität auch adäquat mit externen Konzepten abbilden lässt, und eigene Terme in diesem Fall durch sie zu ersetzen. Dabei wird es gelten, eine ausgewogene Balance zwischen semantisch festen, jedoch vermutlich eher unspezifischen, domänenübergreifend verwendeten Konzepten, und spezifischen, jedoch womöglich weniger etablierten Konzepten auszutarieren. Dieser Vorgang birgt einige methodische Herausforderungen, auf die an entsprechender Stelle eingegangen wird.

2)  Eigene Terme, für die sich keine vorexistierenden Entsprechungen finden lassen, werden nochmals fokussiert und einer terminologischen Kontrolle unterzogen. Anschließend werden sie gemäß 1) im vorhergehenden Kapitel in Beziehung zu externen Vokabularen gesetzt und so im *Semantic Web* durch Verknüpfung aussagekräftig referenzierbar gemacht. Sie werden anschließend gemäß der guten Praxis bei Namespaces[^140] auch mit menschenlesbaren Informationen und Bezeichnungen („Labels") angereichert.[^141]

#### Terminologische Kontrolle / Modellierung / Methodik

Mit „terminologischer Kontrolle" sind im Sinne Bertrams „alle Maßnahmen \[...\], die direkt oder indirekt der Definition und Abgrenzung von Begriffen und der eindeutigen Zuordnung von Bezeichnungen zu Begriffen dienen \[...\]"[^142] gemeint. Während dieser Prozess in einem herkömmlichen Thesaurus insbesondere introspektiv auf die Arbeit mit internen Termen gerichtet sein dürfte, so umfasst der hier miteinzubeziehende Thesaurus nichts Geringeres als die Gesamtheit aller im *Semantic Web* eingebundenen Daten. Es liegt somit auf der Hand, dass dieser Vorgang sich in vielem von der herkömmlichen Erstellung von Vokabularen unterscheiden muss.

Für diese Arbeit erscheinen die folgenden Schritte und Abwägungen sinnvoll:

1)  Eine Grundbeschaffenheit des *Semantic Web* liegt in seiner Qualität als Hypertext[^143] aller in ihm verwobenen Modellierungen und Ontologien. Dieser Umstand schließt eine -- eigentlich wünschenswerte -- initiale vollständige philologische Auswertung einzelner Textteile (Vokabulare) aus, und es muss mit einem heuristischen Ansatz vorliebgenommen werden. Dieser besteht darin, unter Zuhilfenahme geeigneter Suchwerkzeuge, fallspezifisch nach terminologischen Lösungen zu suchen.

2)  Verwendung von Standards, wie *RDF*, *RDFS*, *SKOS*, *OWL*, aber auch etwa *Dublin Core*. Ihre Verwendung ist gut dokumentiert, und es existiert eine vergleichbar große Menge einführender Literatur, die als Leitfaden zu Rate gezogen werden kann.[^144]

Hinsichtlich der Recherche nach domänenspezifischen Vokabularen und deren Anwendung sind verschiedene Strategien vorstellbar, die in dieser Arbeit jeweils anzuwenden sein werden:

3)  Es erscheint naheliegend, die Verwendungsweise von Terminologie im Rahmen solcher domänenspezifischen Projekte zu untersuchen, die ihre Daten als *Linked Open Data* zur Verfügung stellen. Entsprechend der spartenübergreifenden Zielsetzung dieser Arbeit sind dies Akteure aus dem gesamten Spektrum des musikbezogenen Kulturerbebereichs.[^145]

4)  Einen Sucheinstieg für Vokabulare bietet das *Basel Register of Thesauri, Ontologies and Classifikations*[^146], in dem auch fachspezifische Suchen möglich sind.

5)  Das Portal *Linked Open Vocabularies*[^147] ist eine Metasuchmaschine, mit der eine große Zahl von *Triplestores* -- Repositorien, in denen Daten des *Semantic Web* wohnen -- durchsucht werden kann. Suchergebnisse können wiederum nach unterschiedlichen Kriterien (Disziplin, Konzept etc.) gefiltert werden.

6)  Zumindest erwähnenswert ist die technische Möglichkeit, eigene referenzierbare und semantisch kontextualisierte Datensätze -- etwa in *Wikidata* -- zu erstellen.

Erfassung und Modellierung mit externen Vokabularen
---------------------------------------------------

### Interpret und Aufführung

In diesem Bereich spielen drei Konzepte eine Rolle:

1)  *Interpret*

2)  *Aufführung*

3)  Das Verhältnis dieser beiden Entitäten zueinander, welches durch ein Property ausgedrückt wird.

Während *Interpret* und *Aufführung* jeweils im Bereich der „Domäne" und somit in deren Ermessen liegen, muss die Relation zwischen den beiden Entitäten verbindlich definiert sein und somit einen Bestandteil des Metadatenprofils bilden.

#### Interpret und Aufführung -- Relation

-   CIDOC CRM verfügt über das Property `P14`: „This property describes the active participation of an instance of E39 Actor in an instance of E7 Activity."[^148] Diese Definition erscheint für den vorliegenden Anwendungsfall allzu allgemein gefasst und daher unpassend.

-   Ähnlich verhält es sich mit den Properties des *Europeana Data Models*, die in Verbindung mit der Klasse `edm:agent` Verwendung finden.[^149]

-   *Wikidata* verfügt über das Property `wd:P175` („performer")[^150]. Während *Wikidata* aufgrund der potnenitellen Instabilität seiner Terme zwar in der Regel keine Verwendung im Rahmen dieser Arbeit findet, verweist *Wikidata* in seiner Eigenschaft als *Data Hub* unter anderem auf den folgenden Datensatz:

-   Auf *schema.org* findet sich das Property `schema:byArtist`.[^151] mit möglichen Objekten `schema:musicGroup` und `schema:person`. Als Subjekte kommen `schema:musicAlbum`` `oder `schema:musicRecording` infrage. Während die Objekte geeignet erscheinen, anwendungsrelevante Sachverhalte wiederzugeben, sind die Subjekte offenbar auf Audioaufnahmen beschränkt: Somit könnten Aufführungen, die nicht in Form einer Aufnahme vorliegen, durch diese Entitäten nicht repräsentiert werden.

-   In der *DOREMUS Ontology*[^152] finden sich die Properties `mus:U54`[^153] („is performed expression of") und `mus:U81`[^154] („had performer status"). Jedoch scheint ersteres durch die implizit starke Konzentration auf *FRBR* (*Functional Requirements for Bibliographic Records*)[^155] für eine generische Anwendung zu eingeschränkt und nicht sachgemäß. Letzteres ist offenbar auf eine Verwendung bei der Erfassung von Konzertprogrammen semantisch ausgerichtet und somit für das vorliegende Anwendungsszenario ebenfalls unsachgemäß.

-   Die *GND Ontology* verfügt über das Property `gnd:instrumentalist`[^156] mit der Domain `gnd:work` und Range `gnd:differentiatedPerson`. Während diese Verwendungsspezifikationen dem Zweck einer Verbindung von Instrumenten und Werken in prinzipieller Weise gerecht werden könnte, würde die Anwendung des Property die Darstellung einiger vorstellbarer angrenzender Sachverhalte erschweren. So bezöge das Property etwa vokale Äußerungen jeder Form nicht mit ein. Diese Einschränkung wirft gerade im Bereich der Musik des letzten Jahrhunderts etliche Probleme auf -- wie wäre etwa mit gesampleten Stimmen mit anschließender Verzerrung, oder instrumentell-imitatorischen Äußerungen des Vokaltrakts, etwa dem sog. *Vocal Percussion* zu verfahren?[^157]

-   Im Rahmen des *Body&Soul*-Projekts[^158] findet das Property `mo:performer` der *Music Ontology* Verwendung. Seine Domain ist mit `mo:performance`[^159] und dem Range `foaf:agent`[^160] sehr allgemein gehalten, sodass hohe Anschlussfähigkeit zu erwarten ist.

Allerdings entspricht die Klasse `foaf:agent` nicht der vorgesehenen Klasse `ma:Person`, welche besser durch die Klasse `foaf:person`[^161] dargestellt würde. Diese Inkonsistenz ist jedoch keineswegs als Defizit aufzufassen, eröffnet doch die Klasse `foaf:agent` recht eigentlich das Modell für weitere Szenarien: So lässt sich das Darstellungsspektrum um Instanzen in Form von Personen, wie auch „Körperschaften", die dieser Klasse subsumiert werden, erweitern: In Folge werden Aussagen der Form

„\<Das Werk *Soundso*\> \<wird gespielt von\> \<Blockflötenensemble *Schlingenfittich*\> ."

ermöglicht. Diese Darstellungstiefe ist dabei nicht nur im „Werk-Ereignisbereich", sondern auch im Bereich der Musikinstrumente wichtig. Auch Aussagen der folgenden Form sind entsprechend möglich:

„\<Klavierduo *Soundso*\> \<spielt auf\> \<dem Klavier „Objekt *Schlagmichtot*"\>"

Soll `foaf:agent` Verwendung finden, muss das Datenmodell dergestalt ummodelliert werden, dass `foaf:person` zur Unterklasse von `foaf:agent` wird. Dies geschieht mit dem bereits bekannten Property `rdfs:subclassOf`. Zugleich tritt anstelle des Propertys `ma:Interpret` das Property `mo:performer`. Dessen Range wiederum muss auf `foaf:agent` bezogen werden. Da das Property `rdfs:subclassOf` transitiv ist[^162], wird die Range-Beschränkung auch auf mögliche Unterklassen von `foaf:agent` „vererbt" und gilt somit auch für `foaf:person`.

#### Personennormdaten

Die Instanz `ma:Person_a` stellt eine Variable dar, die je nach Bedarf mit entsprechenden Normdaten aus beliebigen externen Domänenvokabularen befüllt werden kann (*GND*, *LCNAF*[^163], *VIAF*[^164], *Wikidata* etc.). So hat der Verfasser beispielsweise zur Illustration für die Arbeit Personendatensätze auf *Wikidata* der angeblich an der Uraufführung der Kantate BWV 208 beteiligten Hornisten des Weißenfelser Hofs,[^165] Johann Zedelmayer (`wdt:Q97621186`)[^166] und Anton Fischer (`wdt:Q97621343`)[^167] angelegt.

Da die Entitäten `ma:hat_Name` und `ma:hat_Lebensdaten`, ursprünglich ja als Attribute im *ERM* eingeführt, in der Regel Bestandteil von Personennormdatensätzen sind, können erstere als obsolet betrachtet werden und aus dem Vokabular `ma:` entfernt werden.

#### Modellierung von Zusammenhängen zwischen Musikinstrumenten, Interpreten und Aufführungen

Während Aussagen gemäß dem Schema

„\<das Klavier „Objekt *Schlagmichtot*"\> \<wird bespielt von\> \<Klavierduo *Soundso*\> ."

nun in Bezug auf das Objekt dank `foaf:agent` ermöglicht worden sind, ist aufgrund der Beschränkungen von `mo:performer` eine Verbindung mit einem Subjekt, welches kein „Agent" ist (etwa ein Musikinstrument), nicht möglich.

Während die Modellierung im *ERM* kraft der einfachen Eigenschaft „Interpret" erfolgte, wird spätestens zu diesem Zeitpunkt deutlich, dass dieses an äußere Vorgaben ungebundene, monodimensionale Modell der vorgefundenen Realität des *Semantic Web* nicht mehr gerecht werden kann. Es gilt daher, Um- und Neumodellierungen vorzunehmen.

1) Den zentralen Verbindungsknoten bei der Modellierung von Instrument und Interpret bildet das Ereignis in Form einer Aufführung -- durch die nun einzuführende Klasse `mo:performance`[^168] vertreten --, unter den domänenspezifische Ereignisse (also Instanzen von `ma:Aufführung_Domäne)` fallen. Durch die Einführung dieser Oberklasse wird die Klasse `ma:Aufführung_Domäne` typisiert und in das *Semantic Web* eingebettet. Eine Verbindung zwischen Instrumenten und Aufführungen kann dabei mit dem Property `mo:instrument` erfolgen: „\[The property r\]elates a performance to a musical instrument involved \[.\]"[^169]

Diese Verbindung ist zum einen zum Objektbereich zu knüpfen:

`mo:performance mo:instrument   ma:Objekt_Domäne .`

Zum anderen muss eine Verknüpfung „werkseitig" erfolgen. Hier bietet es sich an, angesichts der ohnehin angedachten Normierung durch Mapping zu einer Klassifikation, direkt eine Verbindung zwischen entsprechender Klasse und Aufführung zu schaffen:

`mo:performance mo:instrument   ma:Instrument_(Klassifikation) .`

2) Während es nun möglich ist, sowohl die Beteiligung eines Musikinstruments, wie auch der einer Person an einer Aufführung darzustellen, befinden sich beide Entitäten noch in kontingentem Verhältnis zueinander. Noch besteht kein Konnex zwischen Instrument und Person: die Aussage, jemand spiele ein Instrument, ist noch nicht ermöglicht.

Erstaunlicherweise findet sich in den großen etablierten Vokabularen keine Terminologie, um diesen scheinbar banalen Sachverhalt abzubilden. Fündig wird man jedoch in der *Linked Irish Traditional Music Ontology*.[^170] Das Property L58[^171] („played on instrument") und das inverse Property L58i[^172] („instrument played by") geben den hier gewünschten Sachverhalt in geeigneter Weise wieder.

![Ein Bild, das Text, Karte enthält. Automatisch generierte Beschreibung][1]

Abbildung 7: Verknüpfung von Personen, Instrumenten und Aufführungen. (Eigene Grafik, CC0)

### Mapping und Klassifikation

#### „Medium of Performance"

Ein zentrales Anliegen dieser Arbeit ist eine Maximierung der Anschlussfähigkeit des entwickelten Metadatenprofils. An diese Maximierung geknüpft, befindet sich die Offenheit seiner Konzepte, deren Fokussierung erst möglicher Endpunkt eines diskursiven Community-Verfahrens darstellen könnte. Somit muss an dieser Stelle die Schärfung des Konzepts „Musikinstrument" zum einen nicht vorweggenommen werden, zum anderen gilt es sogar, dieses Konzept möglichst weit zu fassen und somit integrativ zu gestalten. Bei diesen Überlegungen bietet die Vorstellung vom „Medium of Performance" -- in *RDA* 6.15.1.1 als „\[a\]n instrument, voice, and/or ensemble for which a musical work was originally conceived\[...\]",[^173] definiert -- einen recht guten Anfangspunkt.

Während dieses Konzept erfreulicherweise Musikinstrumente im herkömmlichen Sinne um weitere Medien musikalischer Äußerung ergänzt, erscheint jedoch die dieser Definition inhärente deterministische Qualität sowie die eindimensionale Ausrichtung auf die Entität „Werk" hier fehl am Platz. Diese Arbeit nimmt vielmehr eine phänomenologische Perspektive ein, indem sie davon ausgeht, dass jede Entität, die in der Lage ist, Klang zu erzeugen, das situative Potential besitzt, die Funktion „Musikinstrument" einzunehmen. So kann beispielsweise auch eine zufällig vor- (bzw. „zu-")handene Flasche[^174] oder jeder andere beliebige Gegenstand situationsbezogen zum Musikinstrument werden. Selbst beispielsweise Boethius' im Mittelalter außerordentlich einflussreiche und fest im sog. *Quadrivium* verankerte Idee „kosmischer Musik", die *musica mundana*,[^175] findet als Zusammenspiel verschiedener „Medien", der Himmelskörper, Raum in diesem Verständnis.

Anhand letzteren Beispiels wird dabei auch deutlich, dass in dieser Arbeit auch das Konzept *performance* in einem sehr allgemeinen Verständnis Verwendung findet. Prämisse einer solchen „Performance" bildet also nicht etwa eine wie auch immer geartete artifizielle „Performativität"[^176].\
Zugleich besteht -- im Gegensatz etwa zu *RDA* -- kein notwendiger und schon gar kein hierarchischer Zusammenhang zwischen Medium und Werk. Auch ein Museumsobjekt gilt -- kraft seines Potentials, Medium einer musikalischen Äußerung (gewesen) zu sein -- nach diesem Verständnis als „Medium of Performance".

Gleichzeitig wird der Begriff „Musik" ebenfalls zum außerordentlich integrativen Konzept, demzufolge -- man denke an Boethius -- genau dasjenige als Musik aufzufassen ist, das als solches wahrgenommen wird -- und dies selbst ganz und gar unabhängig von einer (nicht-)vorhandenen „Klanglichkeit". So liegt denn also „Musik" gewissermaßen im Auge des Betrachters, und das Medium dieser Wahrnehmung ist ein -- im eigentlichen Wortsinne -- „instrumentales" Werkzeug -- ein (Musik-)Instrument.

Bislang wurde in dieser Arbeit das Konzept `ma:Instrument_Klassifikation` als Platzhalter verwendet. Im Sinne einer Anbindung ans *Semantic Web* sollte jedoch nach einem etablierten Term gesucht werden. Zwar findet sich in der *Performed Music Ontology* -- einer Ontologie,[^177] die für den Gebrauch im Rahmen von *BIBFRAME* entwickelt worden ist --[^178] die Klasse `pmo:mediumOfPerformance`.[^179] Jedoch ist davon auszugehen, dass sie durch ihre Ausrichtung auf *FRBR* keinen Raum für Nutzungsszenarien, wie die eben skizzierten, bietet.

Vielversprechender erscheint das Konzept `mus:M14`[^180] („medium of performance") der *DOREMUS*-Ontologie, weil es keinerlei inhärente Einschränkungen seiner Verwendung gibt. Entsprechend wird im Folgenden das Konzept `ma:Instrument_Klassifikation` mit dem Konzept `mus:M14` ersetzt.

Jedoch erschiene es sinnvoll, im Nachgang dieser Arbeit -- etwa im Rahmen jenes Community-basierten Diskurses -- die Neuanlage eines Konzepts zu prüfen, um ein höheres Maß an Offenheit, Anschlussfähigkeit und Unabhängigkeit gegenüber bibliographisch-"gedachten" Modellen wie insbesondere *FRBR* und dem *International Federation of Library Associations and Institutions Library Reference Model* (*IFLA-LRM*)[^181] erzielen zu können.

#### Herausforderungen

Dieser Option lag das Anliegen zugrunde, „werkseitig" fallspezifisch unsaubere oder unspezifische Vokabulare durch In-Beziehung-Setzen zu Musikinstrumenten -- entweder über eine Klassifikation oder direkt gegenüber einem Objekt -- zu disambiguieren. Diese Fallspezifität birgt jedoch auch Herausforderungen: Kehrte man die Perspektive zu einer „objektseitigen" um, so mündete ein Suchvorgang unter Umständen in eine mit ambiguösem Vokabular indexierte Treffermenge und somit in übermäßig viele *False Positives*. Dieses Problem ist nicht einfach lösbar, und es scheint, dass eine wirklich symmetrische Lösung auf terminologischer Basis nur Ergebnis eines gründlichen Standardisierungsprozesses zu schaffen sein wird. Allerdings existieren bereits Ansätze, die aus „umgekehrter Richtung" hin zu einer Verbindung zwischen Objekt und Werk vorstoßen: Im Artikel „A Timeline Metaphor for Analyzing the Relationships between Musical Instruments and Musical Pieces",[^182] einer Publikation aus dem *MusiXplora*-Umfeld,[^183] wird beschrieben, wie anhand eines statistischen Abgleichverfahrens zwischen Objekt- und Werkmetadaten (*Similarity Measure*) eine gute Trefferquote bei der maschinellen Herstellung von Objekt-/Werkbeziehungen zwischen *MIMO*- und *RISM*-Einträgen erzielt wird.

Der Umstand, dass bereits auf Verfahren verwiesen werden kann, die die „objektseitige" Verlinkung abdecken, lässt das eingangs beschriebene Defizit als zunächst verschmerzbar erscheinen. Angesichts dessen jedoch, dass die Ergebnisse der Verlinkung laut Artikel noch einen intellektuellen Redaktionsprozess erfordern[^184] bzw. soweit bekannt nicht mit *Semantic-Web*-Technologien erschlossen sind, erschiene vielmehr ein synergetischer hybrider Ansatz, der die erzielbare hohe intellektuelle Qualität mittels der hier vorgeschlagenen Methodik mit der im Artikel beschriebenen maschinellen Effizienz koppelt, als verfolgenswerter Ansatz.

#### Mapping

Zum Mappen hat sich insbesondere das ebenfalls durch die W3C standardisierte Vokabular *Simple Knowledge Organization System* (*SKOS*)[^185] etabliert.[^186]

Das in dieser Arbeit entwickelte Modell sieht zwei Anwendungsszenarien vor:

##### Szenario 1: Mapping über Klassifikation

Verbindungen zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` werden über eine Unterklasse von `mus:M14` („Medium of Performance") hergestellt (s. Abbildung 8). Dabei ist der jeweilige Vertreter der Klasse `ma:Objekt_(Domäne)` eine Instanz der Klasse `mus:M14`. Dieser Sachverhalt kann mit `rdf:type`, wie auch bereits in Kapitel 3.2.2 geschehen, wiedergegeben werden (das Property `ma:Typ` kann entsprechend entfernt werden):

`ma:Objekt_(Domäne) rdf:type    mus:M14 .`

Die Entität `ma:Instrument_nach_Vokabular_(Domäne)` findet ihre fallspezifische exakte Entsprechung in der Instanz der Entität `mus:M14` (vgl. Abbildung 8), sodass mit `skos:exactMatch` eine Äquivalenzrelation dargestellt werden kann:

`ma:Instrument_nach_Vokabular_(Domäne)  skos:exactMatch mus:M14 .`

Eine Verwendung weiterer, vagerer SKOS-Relationen erscheint -- da von einem „werkseitigen" Mappen ausgegangen wird -- an dieser Stelle nicht angebracht, soll doch das uneindeutige Domänenvokabular durch Mappen dismabiguiert, also exakt gemapped, werden.

![Ein Bild, das Text, Karte enthält. Automatisch generierte Beschreibung][2]

Abbildung 8: Verknüpfung von Vokabular und Objekten über eine Klassifikation (Eigene Grafik, CC0)

###### Klassifikation

Die Entscheidung für eine Klassifikation wäre Gegenstand eines Standardisierungsprozesses durch die Community. In Form einer systematischen kritischen Untersuchung vorhandener Klassifikationen eine Grundlage für diesen Prozess zu schaffen, birgt daher großes Potential für zukünftige Arbeiten. Vorläufig lässt sich jedoch feststellen, dass insbesondere der sog. *MIMO Thesaurus*[^187] eine sehr tragfähige klassifikatorische Infrastruktur bietet. Weitere Möglichkeiten, insbesondere für die Verwendung von Vokalstimmen,[^188] finden sich im *IAML Medium of Performance Vocabulary*.[^189] Vor allem erscheint denkbar, ähnlich zum hier gewählten Vorgehen, ein Metadatenprofil zu entwickeln, das die Darstellungstiefen verschiedener Klassifikationen und Vokabulare kombiniert und zueinander in Beziehung setzt.

##### Szenario 2: direktes Mapping

Bei der Herstellung einer direkten Relation zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` sind verschiedene Bezugsszenarien je nach Ähnlichkeit von Term und Objekt vorstellbar. Es erscheint daher sinnvoll, eine Relation als sog. *Superproperty* zu definieren, unter das alle weiteren Relationen (*Subpropertys*) subsumiert werden.[^190] Als *Superproperty* ist dabei das Property `dc:relation`[^191] der *Dublin Core Metadata Initiative* als besonders standardisiert zu betrachten. Unter ihn können mit dem Property `rdfs:subpropertyOf`[^192] Subproperties für die folgenden Szenarien eingeordnet werden:

1) Zur Exemplifizierung eines Terms wird auf ein beispielhaftes Objekt verwiesen. Dies ist auch im hier behandelten Anwendungsbeispiel der Fall: dem Term `rism:cor_da_caccia` kann aufgrund bestehender Gemeinsamkeiten hinsichtlich Region (Herstellungs-/Kompositionsort: Mitteldeutschland) und Zeit (erste Hälfte 18. Jahrhundert) ein Objekt zugewiesen werden, das als beispielhaft für den Typ des etwa bei der Uraufführung verwendeten Instruments gelten könnte. SKOS, die erste Anlaufstelle, wenn es um Mapping geht, bietet dabei das Property `skos:example`[^193], dessen Zweck jedoch nicht im Verlinken mit beispielhaften Instanzen zu bestehen, sondern darin zu liegen scheint, beispielhafte Verwendung von Termen zu illustrieren.[^194]

m CIDOC CRM findet sich das Property `crm:P137`[^195] mit dem Label „exemplifies (is exemplified by)". Die Domain des Propertys ist dabei auf `crm:E1`[^196] (Entity) bezogen -- die Range auf `crm:E55` (Type).[^197] Beim Konzept `crm:E55` handelt es sich um „CIDOC CRM's interface to domain specific ontologies and thesauri",[^198] indem die domänenspezifischen Terme etwa mit dem Property `crm:P127`[^199] „has broader term (has narrower term)" zu Unterklassen von `crm:E55` deklariert werden (s. \#Abbildung).[^200] Mehreres erscheint daher sinnvoll: - Das Property `crm:P137` darf für die Relation „Beispiel" zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` eingeführt werden. Bemerkenswert ist zudem, dass diese Property als eine sog. *symmetric property* definiert werden kann, bei der also Domain und Range variabel sind.[^201] Sie wird dabei durch die Eigenschaft `owl:symmetricProperty`[^202] als solche klassifiziert. - Anstelle der Entität `ma:Instrument_nach_Vokabular_(Domäne)` kann die Entität `crm:E55` (Type) als Schnittstelle zwischen domänenspezifischem Vokabular und dem Metadatenprofil verwendet werden. - Das Konzept `crm:E19`[^203] („physical object") kann, als Unterklasse von `crm:E1`, dabei anstelle von `ma:Objekt_(Domäne)` verwendet werden, um den gleichen Effekt zu erzielen. - Indem `crm:E55` mit `rdf:type` als Musikinstrument gekennzeichnet wird, kann festgelegt werden, dass es sich bei allen Unterklassen und Instanzen von `crm:E55` um Musikinstrumente handelt (s. Abbildung 9). Dies kann anstelle der Klasse `ma:Instrument_(Domäne)` geschehen und macht diese somit obsolet. Obwohl die „großen" Domänenvokabulare (*GND*, *LCSH* etc.) vielfältige Terme bereithalten, fallen auch hier spartenunspezifische Terme aus Vokabularen in die engere Auswahl, die ein hohes Maß an Verbreitung versprechen: Der Datensatz `wd:Q34379` „musical instrument" in *Wikidata*[^204] weist eine Vielzahl von Mappings zu anderen Vokabularen auf und ist somit außerordentlich aussagekräftig. Obwohl *Wikidata*-Datensätze grundsätzlich manipulierbar sind und daher semantische Persistenz nicht garantieren können, handelt es sich bei „musical instrument" wohl um ein sehr zentrales Konzept, das nicht ohne weiteres zu verändern sein wird. Und tatsächlich ist die „maschineninterpretierbare", kontextuell-hergestellte Semantik nicht weniger persistent als bei anderen, angeblich persistenteren Vokabularen. Eine Übernahme in das Metadatenprofil erscheint daher möglich und sinnvoll.

2) Einen gängigen Anwendungsfall stellt das Szenario dar, dass eine Äquivalenzrelation zwischen Domänenvokabular und Objekt dargestellt werden soll. Beispielhafte Sachverhalte wären -- etwa im Falle einer Audioaufnahme: „Anne-Sophie Mutter spielt auf ihrer Stradivari *Lord Dunn-Raven*"[^205], oder „J. S. Bach nimmt die *Hildebrandt Orgel* von *St. Wenzel* in Naumburg ab".[^206] Es müsste also eine Verknüpfung zwischen einem domänenspezifischen Vokabular -- etwa der *GND* -- und einem Objekt hergestellt werden, die besagt, dass beide Datensätze ein identisches Instrument bezeichnen. Dies kann etwa mithilfe des Property `owl:sameAs`,[^207] im Übrigens ebenfalls eine *symmetric property* (s.o.), geschehen. Analog zu den bereits beschriebenen Herausforderungen beim Mappen über eine Klassifikation ergibt sich jedoch auch hier beim Mappen zwischen einer Entität des Typs *Instanz* (Objekt) und einer des Typs *Klasse* (Vokabular) ein Problem: Während das ambiguöse Domänenvokabular durch den Verweis auf ein spezifisches Objekt disambiguiert wird, folgt „objektseitig" die logische Aussage, mit der „werkseitigen" Verwendung eines (eigentlich generischen) Terms sei immer genau jenes Objekt gemeint.

Einen möglichen Ausweg böte unter Umständen die Verwendung von `rdf:type`, um dieses hierarchische Problem zu umgehen. In diesem Fall müsste jedoch die Superproperty `dc:relation` entfernt werden, würde doch andernfalls jede `rdf:type`-Beziehung -- also auch etwa die, die festlegt, dass `dc:relation` ein Property ist -- zu einer Subproperty von `dc:relation`; logisch falsch.

Daher soll `owl:sameAs` „als Krücke", im Bewusstsein seiner Unzulänglichkeit vorläufig beibehalten werden, wäre aber im Rahmen einer Community-Nachbereitung zu thematisieren.

![blablablub -- fett markiert: übergeordnete Klassen und deren Beziehungen zueinander]

Abbildung 9: Verschiedene Mappingszenarien zwischen „werkseitigem" Vokabular und Objekt. Fett markiert: übergeordnete Klassen und deren Beziehungen zueinander. (Eigene Grafik, CC0)

##### Erkenntnisse aus der Modellierung

Das -- ursprünglich immerhin recht zentrale -- Anliegen dieser Arbeit, eine „werk- und objektseitig symmetrische" Verbindung zwischen Vokabularen und Objekten zu schaffen, konnte im Vorhergehenden nur sehr bedingt erfüllt werden. Insbesondere die spartenübergreifende Tragweite der Implikationen dieser Verbindung bringen es mit sich, dass diese Arbeit nun zum ersten Mal an einen Punkt gerät, an dem deutlich wird, dass die Lösung eines Problems erst im Rahmen eines anschließenden gemeinschaftlichen Prozesses möglich sein wird. Initiale gedankliche Vorarbeiten leisteten dabei die in diesem Kapitel ausgebreiteten Ausführungen.

### Klangbeispiel

Widererwarten stellt sich bei der Sichtung anwendbarer Vokabulare heraus, dass gerade die Verknüpfung eines Klangbeispiels mit einem Instrument ein Szenario ist, das momentan im *Semantic Web* noch nicht abgedeckt ist. Um eine solche Verknüpfung umzusetzen, liegt die größte Herausforderung darin, dass Properties, die sich auf Aufnahmen Art beziehen, in der Regel mit `rdfs:range` oder `rdfs:domain` an Ereignis-Entitäten gebunden sind.[^208] Zwar lässt sich der Ereignis-Kontext laut Weigl für die Beziehung zwischen Werk und Aufnahme mit einer relativ komplex modellierten, auf der *Music Ontology* basierenden „Volte"[^209] oder evtl. etwas einfacher, mit *schema.org*, vermeiden[^210]. Allerdings sind auch diese Lösungen auf den Werk-Kontext beschränkt und somit für die Verknüpfung von *Musikinstrument* mit *Klangbeispiel* ungeeignet.

*Wikidata* hält zwar mit den Properties `wdt:P4733` („produced sound")[^211] und `wdt:P51` („audio")[^212] Properties bereit, mit denen man Klangbeispiele verlinken kann. Allerdings beziehen sich diese auf Medien aus den *Wiki Commons*. Dennoch scheint im Verlinken in den Wikimedia-Kosmos, eine Chance zu liegen, die prinzipiell nicht ausgeschlossen werden sollte, stellt doch der dieser Kosmos eine riesige, stetig wachsende, intern wie extern verknüpfte Wissensdatenbank dar. Daher erscheint es sinnvoll, `wdt:P51` als Verbindungsglied in diese Welt in das Applikationsprofil zu übernehmen (vgl. Abbildung 10).

Für andere Szenarien scheint das Property `ma:hat_Klangbeispiel` nicht mit externem Vokabular ersetzbar zu sein. Es ergibt sich somit erstmalig im Zug dieser Arbeit, dass ein neuer Term -- `ma:hat_Klangbeispiel` -- im Rahmen des Applikationsprofils in das *Semantic Web* eingeführt werden muss. Bei diesem Schritt sind einige Dinge zu beachten:

-   Momentan bezieht sich `ma:hat_Klangbeispiel` vermittels `rdfs:domain` auf `wd:Q34379` (Musikinstrument) -- und ist somit explizit auf Musikinstrumente im eigentlichen Sinne beschränkt. Eine Verlinkung mit Musikinstrumenten im offenen Verständnis dieser Arbeit (s. Kapitel 4.2.2.1) ist daher nicht möglich. Diese Inkompatibilität lässt sich jedoch recht einfach lösen, indem `rdfs:domain` auf `mus:M14` („Medium of Performance") bezogen wird. Noch wird jedoch `mus:M14` nur im Kontext des Mappings verwendet: Eine direkte Verknüpfung mit Objekten oder Vokabularen, wie sie im Anwendungsszenario dieser Arbeit vorgesehen war, ist nicht möglich. Dies lässt sich jedoch lösen, indem `wd:Q34379` mit `rdfs:subclassOf` zur Unterklasse von `mus:M14` erklärt wird (s. \#Abbildung). So wäre es denn also möglich, auch Klangbeispiele mit Instrumenten -- verstanden im aller weitesten Sinne -- zu verknüpfen.

-   Es gehört zur guten Praxis im *Semantic Web*, Konzepte mit `rdfs:label`[^213] mit einer menschenlesbaren Bezeichnung in Form eines „Strings" zu annotieren.[^214] Um ein größtmögliches Maß an Verständlichkeit im Netz zu gewährleisten, geschieht dies idealerweise auf Englisch. Diese Bezeichnung lautet hier: „audio example medium of performance". Es macht darüber hinaus Sinn, diese Bezeichnung ebenfalls in der URI zu verwenden, um auch diese menschenlesbar zu gestalten. So wird denn aus `ma:hat_Klangbeispiel` das Property `ma:audio_example_medium_of_performance`.

-   Zudem gehört es zur guten Praxis, mit `rdfs:comment`[^215] einen menschenlesbaren Kommentar zur Verwendung eines Properties ebenfalls als String zu hinterlegen.[^216] In diesem Fall heißt er: „\[The property r\]elates audio files to: musical instrument terms in vocabularies, physical objects used for musical performance."

Nachdem ein passendes Property kreiert worden ist, darf noch das dazugehörige Objekt, bislang `ma:Klangbeispiel`, durch einem etablierten Term ersetzt werden. Hier bietet sich etwa die Klasse `schema:track`[^217] an.

Bei *schema.org* handelt es sich dabei um ein überaus mächtiges Vokabular, das von den einschlägigen Suchmaschinengiganten unterhalten und verwendet wird. Schon allein auch aus Gründen der Suchmaschinenvisibilität sowie der „mitgelieferten" einfachen Implementierbarkeit von *RDF* in *HTML* handelt es sich um eine „Anwendung", die zuletzt auch als potentiell außerordentlich performant für den Kulturerbebereich wahrgenommen worden ist.[^218] Eine weitere Prüfung, in wie weit das hier entwickelte Anwendungsprofil von einer Erschließung mit den Mitteln von *Schema.org*[^219] profitieren könnte bzw. ob überhaupt eine Kompatibilität besteht, würde aus genannten Gründen sicherlich im Zuge einer Fortentwicklung des Anwendungsprofils Sinn machen.

Denkbar wäre es, wie im *ERM* skizziert, weitere Szenarien darzustellen (etwa Lizenz, Format, Album, Dauer etc.), in das Applikationsprofil zu integrieren. Dies im Rahmen dieser Arbeit durchzuführen ist jedoch nicht möglich. Stattdessen kann zum einen auf Vokabulare verwiesen werden (etwa *Schema.org* oder die *Music Ontology*), andererseits würde eine Ausarbeitung vom eigentlichen Ziel dieser Arbeit -- nämlich das spartenübergreifende Verbinden von musikinstrumentalen Daten -- allzu sehr weglenken. Daher bleibt auch dies ein mögliches Desiderat im Rahmen einer Weiterentwicklung des Metadatenprofils. Entsprechende, bereits vorhandene Terme können somit aus dem Applikationsprofil entfernt werden.

![blablablub -- fett umrandet: Klassen, dünn umrundet: Instanzen]

Abbildung 10: Verknüpfung von Vokabular und Objekt mit einem Klangbeispiel -- fett umrandet: Klassen, dünn umrandet: Instanzen. (Eigene Grafik, CC0)

Erfassung des Komplexes „Stimmungen"
------------------------------------

Nachdem es zuletzt möglich gewesen war, bei der Modellierung ontologischer Sachverhalte auf nachnutzbare, bereits im *Semantic Web* verankerte Vokabulare zurückzugreifen, ergibt sich für diese Arbeit nun die Situation, dass eine solche Datengrundlage nicht mehr zur Verfügung steht. Dies ist gleichermaßen Herausforderung wie Chance: So entfällt zwar die aufwendige Suche nach- und Auswertung von Vokabularen im Netz, doch ergeben sich nun zwangsläufig Fragen in Bezug auf die konzeptuelle Anlage und technische Bereitstellung eigener Datensätze. Dabei wird es abermals nicht anders möglich sein, als technische Aspekte weitestgehend auszuklammern und sich auf die konzeptuelle Arbeit zu fokussieren. Angesichts der Komplexität im Bereich der musikalischen Stimmungen, die im Spannungsfeld von Musikästhetik, Musiktheorie, Organologie aber auch etwa der Physik angesiedelt ist, wird es fortan notwendig sein, vermehrt musiktheoretische Fragestellungen im weitesten Sinne bei der terminologischen Arbeit Platz einzuräumen.

### Problemstellung

Eine zentrale Herausforderung stellt die Vieldeutigkeit der mit dem Komplex „Stimmung" assoziierten Begriffe dar. Da eine umfassende Disambiguierung an dieser Stelle nicht möglich ist, wird hier vor allem auf einen wichtigen Umstand hingewiesen, der das Verständnis für die folgenden Ausführungen erleichtern soll.

Prinzipiell muss nämlich einer streng physikalisch basierten und messbaren Definition von Stimmung und Klang und einem ideellen Konzept unterschieden werden, das sich insbesondere etwa in Formen ihrer (scheinbaren) Repräsentierungen äußert. Diese beiden Kategorien stehen durchaus in Beziehung zueinander, dürfen jedoch keineswegs pauschal gleichgesetzt werden. So mag etwa die Aussage, ein Instrument sei in A gestimmt, dazu verleiten, Rückschlüsse auf verschiedene klangliche Verhältnisse gemäß heute gültiger (aber arbiträrer) Konventionen (*a'* = 440 Hz) zu ziehen. Es ist wichtig, sich immer wieder vor Augen zu führen, dass diese Festlegung keine naturgegebene, sondern eine recht eigentlich willkürliche ist:

Die Frequenz 440 Hz ist keineswegs dasselbe wie „der Ton *a*'", sondern ein in der Natur vorkommendes Phänomen, das anhand einer normalisierten Einheit, *Hertz*, gemessen wird. Und umgekehrt handelt es sich beim Ton *a* nicht um einen Klang mit der Frequenz 440 Hz, sondern um ein lediglich ideell existierendes Konzept, das innerhalb eines Ordnungsgefüges in (ebenfalls theoretischer) Relation zu anderen theoretischen Konzepten (also anderen „Tönen") steht. Dieses Konzept erfährt seine reale Manifestation dabei zunächst lediglich in semiotischer Form als graphischer (Note) oder sprachlicher Darstellung als „Label" „der Ton *a*'". Ein klangliches Potential existiert für dieses Konzepts höchstens implizit (dank dessen ist etwa eine Partitur als Medium dazu imstande, dieses inhärente Potential auch ohne klangliche Äußerung in abstrahierter Repräsentation zu transportieren). Kurz gesagt: Signifikant und Signifikat sind nicht a priori gekoppelt. Ihr Verhältnis muss zuerst festgelegt werden: -- eben etwa durch die Definiton „*a'* = 440 Hz". Es wird bei der Modellierung darauf zu achten sein, dass diese beiden konzeptuellen Ebenen nicht vermischt werden, und es erscheint sinnvoll, die benötigten Entitäten und Properties nochmals semantisch zu schärfen und gegeneinander abzugrenzen.

### Stimmton

Die Entität `ma:Stimmhöhe` definiert, wie eben bereits skizziert, den Bezug zwischen *theoretischem* Tonkonzept und *realem* Klang in der Form „Stimmton hat Festlegung Klangfrequenz" (etwa: „*a'* = 440 Hz)".[^220] Dabei liegt die Relevanz des Stimmtons für diese Arbeit nicht in seiner Funktion als Ton für das gemeinsame Stimmen von Instrumenten, sondern darin, dass in ihm ein Referenzpunkt festgelegt ist, an dem weitere Töne intervallisch ausgerichtet sind (s. 4.3.3).

### Stimmungssystem

Die Entität `ma:Stimmungssystem` definiert das Gefüge, das festlegt, in welchem Verhältnis Töne zueinander stehen. Anhand eines absolut definierten Stimmtons als Referenzton und in Kenntnis eines zugrundeliegenden Stimmungssystems ließen sich Frequenzen und somit absolute Tonhöhen für beliebige weitere Töne -- etwa die des Ambitus -- ableiten. Hier bietet die *GND* mit der Entität `gnd:4122368-8` („Stimmung \<Musik\>")[^221] einen Datensatz, der behelfsmäßig genutzt werden kann. Um die scheinbare Redundanz dieser Entität und der Entität `ma:Stimmung` aufzulösen, wird das Label für den Gebrauch in diesem Metadatenprofil durch das Property `rdfs:label`[^222] wieder zu „Stimmungssystem" verändert, welches sich aber auf die in der *GND* hinterlegte Bedeutung bezieht.

### Stimmung

Bei dieser Entität handelt es sich um das komplexeste der hier zu fokussierenden, da in ihm jene eingangs beschriebenen Ebenen Gefahr laufen, übermäßig zu verschwimmen. Zu differenzieren sind vor allem zwei Konzepte:

1)  Ein „werk-" oder „quellenseitiges" Konzept von Stimmung, das vor allem die Notation betrifft und somit abstrakt und ideell bleibt (jedoch in gewisser Weise mit 2) in Beziehung steht).

2)  Ein Konzept von Stimmung, das aus instrumentenbaulichen Zusammenhängen zustande kommt und sowohl (wiederum nicht notwendigerweise gekoppelte) abstrakte als auch physikalische Aspekte beinhaltet.

Diese beiden Punkte sollen nun anhand des Anwendungsbeispiels näher ausgeführt werden.

zu 1): Bereits zu Beginn dieser Arbeit wurde erwähnt, dass die Hörner im Autograph der Kantate BWV 208 in F notiert sind, wobei alle weiteren Stimmen in C notiert sind. Dies bedeutet, dass die Töne der Hornstimmen eine Quinte tiefer „klingen",[^223] als sie notiert sind. Dieses Konzept von Stimmung hat dabei eine lediglich auf die Erschließung von Notenmaterial begrenzte Relevanz, da etwa bereits im Falle von Audioaufnahmen Notation keine Rolle spielt. Wichtig ist hierbei festzuhalten, dass das hier gemeinte Stimmungskonzept nicht notwendigerweise einen Rückschluss auf ein verwendetes Horn zulässt: eine in F notierte Stimme ist auf einem (mit Ventilen versehenen) Horn gleich welcher Stimmung (siehe 2) ) spielbar.[^224]

zu 2): Blasinstrumente verfügen kraft ihrer baulichen Charakteristika sowie der Methode der Tonerzeugung[^225] über eine Art „Grundton", den sog. „Pedalton". Über diesem baut sich durch Veränderung des in Schwingung versetzten Luftstroms -- das sog. „Überblasen" -- eine Folge von Tönen mit einer festen Intervallstruktur auf -- die sog. „Naturtonreihe".

![][3]

Abbildung 11: Naturtonreihe über dem „Pedalton" *c*. (Eigene Grafik, CC0)[^226]

Dies bedeutet also, dass Blasinstrumente bereits qua Konstruktion über eine festgelegte Stimmung verfügen. Diese wird anhand jenes Pedaltons, dem „ersten Naturton" benannt: so bedeutet etwa die Bezeichnung „F-Horn" oder „Horn in F" bezogen auf ein Instrument (und also nicht einen Notentext), dass es sich beim ersten Naturton um ein *f* handelt, und dass sich die Naturtonreihe mit ihrer festgelegten Intervallik über diesem Ton aufbaut. Doch auch hier ist die Aussage „in F" keineswegs auf einen absoluten Ton mit definierter Frequenz bezogen und ist somit nicht ultimativ aussagekräftig, sondern kann nur in Bezug zu einem Frequenz-mäßig definierten Stimmton identifiziert werden. Jedenfalls ergibt sich bei der Modellierung die Schwierigkeit, dass der Bezeichnung „Horn in F" je nach Bezugspunkt -- Objekt oder Quelle -- eine unterschiedliche Bedeutung zukommen kann, jedoch nicht muss. Tatsächlich kann diese Bezeichnung im Fall der Modellierung von Autograph und *Großwindigem Naturwaldhorn* als synonym gelten -- eine Differenzierung zwischen Notation und Horn ist nicht nötig. Ein „Naturhorn" (also ein ventilloses Horn) mit Pedalton *f* muss in diesem Kontext alleine schon deshalb gemeint sein, da im 18. Jahrhundert nur dessen Naturtonreihe das in der Stimme vorgesehene Tonmaterial bereithalten konnte -- die Notation ist also bloß eine logische Folge dieses Umstands. Anders sieht es bei neueren Sachverhalten aus. Dort ist Notation keineswegs an den Instrumententyp gekoppelt: Für ein diatonisch spielbares Horn kann auch ein „virtuell-gestimmtes" Horn notiert werden.[^227]

Ein Umgang mit dieser Herausforderung könnte darin bestehen, zwei neue Stimmungsentitäten zu schaffen -- eine, die sich auf die Notation bezieht und eine, die sich auf die „Grundstimmung" eines Instruments bezieht. Allerdings würde dies eine artifizielle Trennung des eben skizzierten Sachverhalts bewirken. Um einiges sinnvoller erscheint es, das Konzept der `ma:Stimmung` in seiner bisherigen Form beizubehalten und -- wie dies auch vorgesehen war -- durch Properties Relationen zu einem jeweiligen Bezugspunkt, Quelle oder Objekt, auszudrücken.

### Töne

Töne spielten im vorhergehenden Kapitel bereits eine Rolle:

1)  als eine Art Schlüssel zum Verständnis eines Notentexts („'in F' bedeutet, man muss alles eine Quinte tiefer denken")

2)  als ein Bezeichner, der Rückschlüsse auf den physikalisch prädisponierten intervallischen Aufbau der Naturtonreihe bei Blechblasinstrumenten erlaubt

3)  ![][4]als Klangfrequenz (440 Hz)

4)  als „Zeichen" („*f'*" oder )

5)  als Oktavidentität der „F-Töne", die alle Oktav-verwandten, also im Schwingungsverhältnis 1:2, 2:4 etc. stehenden Töne, in sich vereint.

Abermals wird deutlich, dass die Beschaffenheit des Konzepts „Ton" eine sehr ambige ist, die durchaus hohe Herausforderungen an die kontextuelle Modellierung stellt, ergeben sich doch zugleich konzeptuelle Überschneidungen sowie Differenzen zwischen den zu modellierenden Konzepten.

Es erscheint sinnvoll, zunächst eine Klassifikation der relevanten Konzepte vorzunehmen:

#### Ton als Abstraktum

1\) und 2) beziehen sich auf ein Tonkonzept, das große Ähnlichkeit mit dem 5) inhärenten aufweist: Es liegt ihm eine sehr allgemeine und zugleich sehr abstrakte Vorstellung einer Tonentität „F" zugrunde. Um nicht zu sehr ins Philosophisch-Musiktheoretische abzuschweifen (dies könnte Thema einer Anschlussuntersuchung sein), genügt es, diese Entität zunächst rein hierarchisch als allgemeinste Oberklasse von „F-Tönen" zu verstehen. Entsprechend nachnutzbare Terminologie ließ sich online nicht finden -- es erscheint offensichtlich, dass die Repräsentation musiktheoretischer Zusammenhänge noch ein großes Desiderat darstellt. So ist -- beispielhaft betrachtet -- eine Nutzung der *Wikidata*-Entität `wdt:Q775617`(„F"[^228]) wegen ihrer Koppelung an die gleichstufige Stimmung ausgeschlossen. Daher wird eine neue Entität `ma:F (Tonkomplex)` als Unterklasse von `ma:Ton` angelegt werden. Diese erhält -- wie im letzten Kapitel geschildert -- durch Verbindung mit einer Property `ma:hat Stimmung (notierte)` oder `ma:Stimmung (Instrument)` eine semantische Spezifikation. Infolgedessen können auch die bisherigen Entitäten `ma:Stimmung` sowie `ma:in_F` entfernt werden und die neuen beiden Properties durch `rdfs:range` auf `ma:Ton` und seine Unterklassen bezogen werden.

![Ein Bild, das Text, Karte enthält. Automatisch generierte Beschreibung][5]

Abbildung 12: Anknüpfungspunkte eines abstrakten Tonkonzepts. (Eigene Grafik, CC0)

#### Ton als normativ fixiertes Zeichen

##### Taxonomie

Eine Eskalationsstufe weiter in der Konkretisierung des Konzepts „Ton" liegt seine Manifestation als Zeichen jeglicher Form (vgl. 4.3.5, 4)). In dieser Form ist er stets nur innerhalb eines Musikalischen Bezugs- und Ordnungssystems (also etwa in einem Notensystem) verständlich, in dessen Kontext er als Bedeutungsträger auftritt. Doch auch hier bleibt er ein abstraktes Phänomen, dessen „Klang-Werdung" ihm lediglich als Potential innewohnt.

Dieses Konzept von Ton begegnet selbstverständlich insbesondere in Hinsicht auf den Notentext, wie er etwa im Umfeld der Entität `ma:Ambitus` auftritt.

Es ergeben sich die folgenden taxonomischen Beziehungen:

![Ein Bild, das Text enthält. Automatisch generierte Beschreibung][6]

Abbildung 13: Taxonomische Beziehungen zwischen Tönen (Eigene Grafik, CC0)

Dabei ist jedoch weiter zwischen Notation und „Klang" -- etwa bei transponierenden Instrumenten -- zu differenzieren. Dieser Faden wird an späterer Stelle wieder aufzunehmen sein (vgl. 4.3.5.5).

##### Stimmton

Zugleich aber findet sich dieses Tonkonzept im Zusammenhang mit der bisherigen Entität `ma:Stimmhoehe`, indem jene „symbolische", tonsystemisch-relative Tonhöhe durch die Zuweisung einer Frequenz definiert wird und als Referenzton Verwendung finden kann.

Angesichts der zuletzt vorgenommenen Anpassung im Bereich der Töne gilt es, das bestehende Modell nochmals zu überdenken: Es liegt dabei auf der Hand, dass die bisherige Entität `ma:a'``_``=``_``415``_``Hz` sehr viel aussagekräftiger, multidimensionaler und semantisch anschlussfähiger würde, wenn man jeden Bestandteil dieser Entität als separates Konzept auffassen würde (dieser Schritt wird in Kapitel 4.3.5.3 vollzogen).

Dabei existiert sogar bereits ein separater Bestandteil in Form der Entität `ma:a'`, durch deren Nachnutzung auch in diesem Kontext die Kohärenz des gesamten Datenmodells weiter gestärkt wird.

#### Ton als physikalisches Phänomen

In der realen Welt erfolgt die Etablierung eines Referenztons durch „das Mappen" eines relativen Tonkonkonzepts (etwa in Form eines Buchstabens) mit der realen Naturerscheinung akustischer Schwingungsfrequenzen. Soll nun also diese „Konkordanz" ebenfalls in eine Tripelstruktur gebracht werden, muss ein Property sowie ein Objekt definiert werden. Dies kann an dieser Stelle nur prophylaktisch erfolgen, erfordert doch die Modellierung mit etablierten *Semantic-Web*-Sprachen solide(re) Kenntnisse im Bereich der Akustik. Daher soll zunächst mit der *Wikidata*-Entität „pitch" (`wdt:Q118819`) vorliebgenommen werden, die als Klasse eingeführt werden kann. Ihr ist die zu erstellende Frequenz-Entität `ma:415Hz`` `als Instanz zugeordnet. Eine weitere Ausdifferenzierung der Bestandteile in Datentypen (etwa „natürliche Zahlen") und Einheitswerte (Hz) wäre ebenfalls ein Anschlusspunkt für künftige Bestrebungen.[^229]

##### Modellierung Stimmhöhe / Referenzton

1) Es ergibt sich also der folgende Zusammenhang: Die Entität `ma:Stimmhoehe` integriert in sich die allgemeine, freilich durch Instanzen dieser Klassen weiter zu spezifizierende Aussage:

`ma:Ton    rdf:value   wdt:Q118819`

Dabei wurde `wdt:Q118819` durch das neue Property `rdf:value`[^230] in Relation zu `ma:Ton`, etwa `ma:a'`, gesetzt.

2) Durch die so erfolgte Modellierung der Entität `ma:Stimmhoehe` als RDF-Tripel ergibt sich eine Schwierigkeit, die bislang keine Rolle gespielt hat: Das Objekt (`die Stimmung`) der Aussage

`<ein Musikinstrument> <hat Stimmung>  <die Stimmung>  .`

beinhaltet selbst ein Tripel, nämlich:

`<a'>  <ist gleich>    <415 Hertz> .`

Die Lösung dieses Problems liegt in der sogenannten *Reification*,[^231] indem „eine Aussage über eine Aussage" gemäß dem folgenden Schema gemacht wird:

`<ein Musikinstrument> <hat Stimmung>  <die Stimmung>  .`

`<die Stimmung>    <hat Subjekt>   <a'>    .`

`<die Stimmung>    <hat Prädikat>  <ist gleich>    .`

`<die Stimmung>    <hat Objekt>    <415 Hertz> .`

Zudem könnte definiert werden:

`<die Stimmung>``	``<ist eine>``	``<Tripel-Aussage>    .`

Dies kann mithilfe der Properties `rdf:subject`,[^232] `rdf:predicate`[^233] und `rdf:object`[^234] geschehen. Zudem kann das Objekt durch Klassifizierung als Aussage durch die Verbindung über das Property `rdf:type` zur Entiät `rdf:statement`[^235] definiert werden:[^236]

Es ergibt sich somit der folgende analoge Zusammenhang:

`<wdt:musical_instrument> <ma:hat_Stimmhoehe> <ma:Stimmhoehe> .`

`<ma:Stimmhoehe>  ``	``<rdf:subject>   <ma:Ton>    .`

`<ma:Stimmhoehe>   <rdf:predicate> <rdf:value> .`

`<ma:Stimmhoehe>   <rdf:object>    <wdt:pitch> .`

sowie

`<ma:Stimmhoehe>   <rdf:type>  <rdf:statement> .`

#### Tonraum (Ambitus)

Ein weiteres Anliegen der Arbeit war es, eine Darstellungsmöglichkeit für den Ambitus (bislang `ma:Ambitus`) von Stimmen zu schaffen. Auch hier halten die auffindbaren Vokabulare keine Patentrezepte bereit. So bietet zwar *DOREMUS* das Property `mus:has_Ambitus`[^237] scheinbar einen Ansatzpunkt, allerdings wird durch die Erklärung „this property allows for describing the tessitura of a character, as can be drawn from the score\[...\]" die Benutzung letztlich auf Vokalpartien beschränkt. *Wikidata* hält das Property `wdt:ambitus`(`P2279`)[^238] bereit, das aufgrund seiner Beschreibung „étendue d'une mélodie, d'une voix ou d'un instrument, entre sa note la plus grave et sa note la plus élevée"[^239] vielversprechend erscheint. Jedoch ist er semantisch auf eine Entität bezogen, deren Beschreibung unzulänglich ist,[^240] und zugleich scheint jener Ambitus ausschließlich als Intervall und nicht als definierter Tonraum darstellbar. Aus diesen Gründen werden die eigens definierten Konzepte beibehalten:

`<ma:Instrument_nach_Vokabular_(Domäne)>   <ma:hatAmbitus> <ma:Ambitus>    .`

Dabei gilt für `ma:Ambitus`:

`<ma:Ambitus>  <ma:hat_höchsten_Ton>   <ma:Ton>    .`

`<ma:Ambitus>  <ma:hat_tiefsten_Ton>   <ma:Ton>    .`

#### Inferenzmöglichkeiten

Weiteres Potential des Metadatenprofils liegt in der automatischen Deduktion von Schlussfolgerungen dank formallogischer Zusammenhänge.[^241] Beispielsweise könnten künftig durch entsprechende weitaus komplexere Modellierung inferiert werden:

1)  anhand der Information über die notierte Stimmung könnten die dermaßen notierte Töne -- etwa die des Ambitus -- automatisch zu „klingenden" Tönen werden. (Die Möglichkeit, diese Transposition künftig maschinell zu implementieren macht die ursprünglich im *ERM* vorgesehene Explikation „klingender" Äquivalente zu notierten Tönen hinfällig.)

2)  mit dem Kammerton als Referenzton und in Kenntnis des zugrundeliegenden Stimmungssystems wären einzelne Frequenzen von Tönen exakt bestimmbar.

> Diese Modellierung würde ein fundierteres Verständnis mathematischer Logik und ihrer Modellierung etwa mit OWL erfordern.

Technische Nachbereitung / The Rise of *wumms:*
-----------------------------------------------

-   Gemäß der guten Praxis für *Linked-Open-Data*-Datensätze erhalten die Konzepte des Vokabulars mit dem Property `rdfs:label` einen Namen und eine Sprachbezeichnung („label everything")[^242].

-   Dasselbe gilt für `rdfs:comment`.

-   Schreibweisen wurden vereinheitlicht, Sonderzeichen entfernt.

-   Das Domänenvokabular, das bislang in *ma:* ebenfalls mitgeführt wurde, wurde in das neue Vokabular *domaene:*[^243] ausgelagert.

-   Der behelsfmäßig eingeführte Namespace *ma:* sollte durch einen neuen, prägnanteren Namespace ersetzt werden. Daher wird *ma:* an dieser Stelle in *wumms:* (***SeMantic MUsical instrument Web***) umbenannt.

-   Eine entsprechende Domain wurde auf purl.org registriert, sodass *wumms:* nun über die persistente URL purl.org/wumms im Netz verankert ist und referenziert werden kann („cool uris don't change")[^244]. Diese löst derzeit auf das Vokabular im *GitHub*-Repositorium auf.

-   Allerdings wurde *wumms:* durch den Zusatz `owl:versionInfo`` ``"draft"` als instabiler Entwurf gekennzeichnet. Dasselbe gilt für die einzelnen Konzepte. Somit ist dem Hinweis genüge getan, die Nutzung erfolge einstweilen auf eigene Gefahr, und eine weitere, ändernde Bearbeitung ist somit statthaft.

![Ein Bild, das Tisch, Luft, haltend, fliegend enthält. Automatisch generierte Beschreibung]

Abbildung 14: Visualisierung von *wumms:* Blaugrau: originäre *wumms:*-Konzepte, bunt: externe Komponenten von *wumms:* (Eigenes Bild, CC0)[^245]

Schluss {#schluss-1}
=======

Anwendungssimulation
--------------------

Nach erfolgter Modellierung liegt es nahe, die Kohärenz sowie die Praxistauglichkeit des Metadatenprofils zu verifizieren. Wären die Datensätze bereits in einem Triple Store publiziert, ließe sich mithilfe verschiedener Abfragen über eine *API* oder eine *SPARQL*-Schnittstelle die Konsistenz des Datenmodells feststellen, indem die Abfrage einer Kataloganwendung simuliert würde. Da dies nun nicht der Fall ist, erscheint der Ansatz sinnvoll, eine Nachmodellierung des „Anwendungsszenarios" aus Kapitel 3.1 anhand des Metadatenprofils vorzunehmen. Diese Modellierung simuliert denn zwar nicht die Schnittstellenabfrage an sich, wohl aber das erfolgreiche Retrieval relevanter Informationen. Eine wünschenswerte Anwendung des Profils auf ein anderes spezifisches Szenario ist angesichts der zu erwartenden Neuanlage von fehlendem Vokabular hier leider nicht durchführbar. Jedoch ist die Nachmodellierung des Anwendungsszenarios keineswegs trivial: gelingt sie, ist davon auszugehen, dass das Metadatenprofil den spezifischen Anforderungen des Szenarios genügt. Eine belastbare Grundlage für eine Weiterentwicklung wäre gelegt.

### Modellierung

Das Szenario sah vor, dass im Bereich der Domäne die folgenden Zusammenhänge bereits vordefiniert sind:

\@prefix dom: \<https://raw.githubusercontent.com/SPARQLCRMSUPPE/

> VocsForInstruments/master/namespaces/domaene\>

    dom:BWV208  dom:hatUraufführung   	dom:UrauffuehrungBWV208   ,
     		dom:hatBesetzung		dom:corDaCaccia   .

    ###\ In einem externen Vokabular ist das Ereignis der Uraufführung mit dem uraufgeführten Werk verknüpft und die Besetzung ist mit dem Domänenvokabular bezeichnet.

    Eingedenk dieser gesetzten Prämisse voranschreitend ist die Modellierung mit dem Vokabular des Metadatenprofils in folgender Weise möglich:

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

    dom:UrauffuehrungBWV208   mo:instrument   dom:Barockhorn_(Mitteldeutschland).

    ###\ Die Uraufführung fand mit einem Barockhorn statt.

    dom:Barockhorn_(Mitteldeutschland)    litmus:L58i   wdt:Q97621186   .

    ###\ Ein Instrument des Typs "Barockhorn" wurde gespielt von Johannes Zedelmayer.

    dom:Barockhorn_(Mitteldeutschland)    owl:sameAs    dom:corDaCaccia   .

    ###\ Der Typ "Barockhorn" entspricht dem Typ "cor da caccia".

    dom:Barockhorn_Mitteldeutschland    crm:P137    mimo:MIMUL_Inv.-Nr._1661    .

    ###\ Ein Beispiel für den Typ "Barockhorn" ist das Großwindige Naturwaldhorn etc.

    mimo:MIMUL_Inv.-Nr._1661    wumms:KlangbeipsielMediumOfPerformance  wc:File:4m33s.mid   .

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

    wumms:c'	wumms:klingt	wumms:f	.
    wumms:a''	wumms:klingt	wumms:d‘	.

Zwei Erkenntnisse können bereits festgehalten werden:

1)  Das Problem des Mappings zwischen Vokabular und Objekt ist -- dies wurde bereits in Kapitel 4.2.2.3 festgestellt -- nicht bestmöglich gelöst. Die Vererbung von Eigenschaften der je einen auf die je andere Entität, wie sie momentan der Fall ist, ist nicht wünschenswert. Dies wurde bei der Modellierung nochmals sehr deutlich. So ist beispielsweise die Option, verschiedenartig gestimmte Instrumente miteinander in Beziehung zu setzen, prinzipiell nicht möglich. Hier ist weitere Arbeit bei der Relationierung durch Properties angezeigt, wobei etwa auch Möglichkeiten der Prädikatenlogik zu prüfen, ein interessanter Ansatz sein könnte.

2)  Das Metadatenprofil eignet sich -- soweit es sich hier feststellen lässt -- grundsätzlich zur Modellierung des Anwendungsszenarios und ähnlich komplexer musikalischer-/organologischer Sachverhalte, die Entitäten verschiedener Kulturerbe-Domänen miteinander in Beziehung setzen und verknüpfen. Dieses Anliegen der Arbeit kann somit nun als weitestgehend erfüllt betrachtet werden.

Fazit {#fazit-1}
-----

Ausgehend von einem exemplarischen Anwendungsszenario, dem Horn im Kontext von J. S. Bachs sog. „Jagdkantate" BWV 208, wurde die Modellierung eines Metadatenprofils ***SeMantic MUsical instrument Web*** (*wumms:*), das auf den Prinzipien von *Linked Open Data* basiert, vorgenommen und im Netz publiziert.[^246] Dabei galt es insbesondere zu prüfen, in wie weit es in diesem Szenario möglich ist, mit den Mitteln des *Semantic Web* musik-instrumentenbezogene Entitäten und Ressourcen aus unterschiedlichen Sparten des Kulturerbes miteinander semantisch zu verknüpfen und dabei Anreicherungen der bisherigen Ausdrucksmöglichkeiten bei der Erschließung solcher Entitäten und Ressourcen zu schaffen. Dazu wurde das Szenario zunächst in ein *Entity Relationship Model* überführt, das die Grundlage für eine anschließende *RDF*-Klassierung bildete. Die Bestandteile dieses semantischen Grundgerüsts wurden im Anschluss mit etablierten Vokabularen nachmodelliert und so das Profil eng in das *Semantic Web* eingewoben. Ließen sich gewünschte Sachverhalte mit dem im *Semantic Web* vorhandenen Vokabular nicht adäquat nachbilden -- dies war insbesondere im Kontext von „Stimmung" der Fall --, wurden die Defizite aufgezeigt und eigene Konzepte geschaffen, und durch Subklassierung unter etablierte externe Konzepte gleichfalls gegenüber dem *Semantic Web* semantisch anschlussfähig.

Die Ziele dieser Arbeit konnten weitestgehend erreicht werden: Die anfangs entworfenen Szenarien konnten zum Schluss erfolgreich modelliert und so eine Verbindung zwischen verschiedenen spartenspezifischen Ressourcen hergestellt werden. Sowohl methodische Grundlage in Form dieser Arbeit als auch konzeptuelle Grundlage in Form einer *lightweight ontology* sind somit für eine weitere Ausarbeitung geschaffen. Dies gilt jedoch nur eingeschränkt für das objekt- und quellenseitige Mapping: Hier weist das jetzige Modell noch Defizite auf, die im Zuge einer Weiterentwicklung anzugehen wären. Dies vermag jedoch nicht weiter zu verwundern, liegt doch das Defizitäre in der Natur eines Modells, das den Ausgangspunkt eines diskursiven Prozesses markieren soll.

Ähnliches gilt für die Schaffung von komplexeren Inferenzierungsmöglichkeiten: Im Bereich der „Stimmungen" konnte die Sinnhaftigkeit solcher Möglichkeiten bei der automatisierten Transposition von Tönen demonstriert werden. Jedoch erforderte eine Implementierung fundiertere Informatikkenntnisse (zumindest gegenüber denen des Verfassers). Induktiv gesehen liegt somit der Schluss nahe, dass Ontologieentwicklung idealerweise ab einem gewissen Punkt als Kooperation zwischen Fachwissenschaftlern und Informatikern geschieht. Operative Schritte wären dabei im Falle von *wumms:* die Bildung einer entsprechenden Community und das Schaffen einer Plattform für die kooperative Weiterentwicklung. Hierfür verspricht etwa die Software *Wikibase*[^247] eine geeignete Plattform bieten zu können.

Wünschenswert wäre schließlich die technische Möglichkeit, in *RDF* strukturierte Daten gegenüber dem Metadatenprofil zu validieren, wie es etwa von in XML strukturierten Datensätzen her geläufig ist. Dies ermöglichen die Sprachen *Shape Expressions* (*ShEX* -- in *Wikibase* „enthalten")[^248] und *Shapes Constraints Language* (*SHACL*)[^249]. Während im Zuge dieser Arbeit nicht, wie ursprünglich geplant, der Versuch unternommen werden konnte, eine Beschreibung des Metadatenprofils mit einer dieser Sprachen zu unternehmen,[^250] würde eine solche Validierungsmöglichkeit eine außerordentlich nützliche Möglichkeit bieten, die eine gleichermaßen niedrigschwellige wie akkurate Verwendung und einfache Entwicklungsarbeit leisten könnte.

Der Vorgang der Entwicklung selbst könnte dabei situativ erfolgen: Anhand eines standardisierten Grundgerüsts, dem Metadatenprofil, könnten, je nach Bedarf, weitere Ausdrucksmöglichkeiten in Form von Vokabular erschaffen und direkt eingebunden werden. Durch die Auslagerung in eine Anwendercommunity könnte so optimal der akute Eigenbedarf des jeweiligen Anwenders mit dem Bedarf aller Nutzer in Einklang gebracht werden.

Insgesamt war immer wieder festzustellen, dass es vielerorts im *Semantic Web* noch an elementaren Ausdrucksmöglichkeiten im Bereich der Musik im Allgemeinen und der Musikinstrumente im Speziellen sehr mangelt. Dies betrifft sowohl Normdaten (etwa ein autoritatives Verzeichnis von Orgeln), Ontologien (etwa der Bereiche „Stimmung", Harmonik, Akustik) aber auch *Best Practices* zur Modellierung teils einfacher musikbezogener Sachverhalte (etwa Klangbeispiele). Weitere Arbeit in diesen Bereichen -- ob als große Ontologie, oder doch besser als viele vernetzte kleinere -- birgt somit enormes Potential. Es konnte in diesem Zusammenhang demonstriert werden, dass es prinzipiell möglich ist, jedes erdenkliche Szenario im *Semantic Web* bei Bedarf zu modellieren und anschlussfähig zu publizieren (wobei wiederum Dritte etwa bei Beachtung der FAIR-Richtlinien[^251] und der Publikation von *Linked Open Data*[^252] von publizierten Daten profitieren können).

Im Zuge der Ausarbeitung wurde deutlich, dass die Modellierung von Ontologien und die Publikation von *Linked Open Data* eine gewisse Lernkurve voraussetzt. Doch demonstriert die Publikation von *wumms:*, dass auch für einzelne Wissenschaftler oder Institutionen ohne starke Informatikabteilung diese Vorgänge durchaus leistbar sind -- auch hier galt: *learning by doing*. Dabei sind die Vorteile, die sich auch für kleinere Forscher und Einrichtungen bieten, enorm -- etwa die Unabhängigkeit gegenüber den beschränkten Ausdrucks-möglichkeiten herkömmlicher etablierter Vokabulare oder die Anschlussfähigkeit in einer zunehmend vernetzten Wissenschaftswelt, als deren Gradmesser etwa die Rolle von *Linked Open Data* in den Projekten wie der *NFDI* gelten kann.

Diese Anschlussfähigkeit gilt dabei mitnichten lediglich für geisteswissenschaftliche Gebiete bzw. den Kulturerbebereich: Innerhalb der besten aller forschungsdateninfrastrukturellen Welten könnten bisherige Gräben zu weiteren Disziplinen, etwa zur Akustik, zur Materialwissenschaft etc. mit Brücken versehen werden, und so weitere Schritte in Richtung einer künftig interdisziplinär vernetzten Wissenschafts- und Forschungsdatenlandschaft unternommen werden.

Verwendete Literatur
====================

Allemang, Dean und Hendler, James: *Semantic Web for the Working Ontologist. Effective Modeling in RDFS and OWL*, Waltham, MA ^2^2011.

Altenhöner, Reinhard u. a.: „NFDI4Culture - Consortium for Research Data on Material and Immaterial Cultural Heritage", in: *Res. Ideas Outcomes* 6 (2020), DOI: https://doi.org/10.3897/rio.6.e57036.

Arbeitsstelle für Standardisierung (Hrsg.): *Funktionelle Anforderungen an bibliografische Datensätze. Abschlussbericht der IFLA Study Group on the Functional Requirements for Bibliographic Records*, Den Haag, Leipzig, Frankfurt 2006.

Auhagen, Wolfgang: Art. „Stimmung und Temperatur", in: *MGG Online*, Kassel, Stuttgart, New York 2016, online: https://www-mgg-online-com.wwwdb.dbod.de/article?id=mgg16098&v=1.0&rs=id-41932d6d-11fc-3f8c-2d92-74829fd97f5e&q=stimmung (abgerufen am 7. Februar 2020).

Baader, Franz u. a. (Hrsg.): *The Description Logic Handbook: Theory, implementation, and applications*, Cambridge u.a. ^2^2007, DOI: https://doi.org/10.1017/CBO9780511711787 (abgerufen am 26. August 2020).

Bach, Johann Sebastian: *Was mir behagt, ist nur die muntre Jagd*, D-B Mus.ms. Bach P 42, Faszikel 3.

Basel University Library (Hrsg.): *BARTOC.org. Basel Register of Thesauri, Ontologies & Classifications*, online: https://bartoc.org/ (abgerufen am 28. Juli 2020).

Bechhofer, Sean u. a.: *OWL Web Ontology Language Reference*, online: https://www.w3.org/TR/owl-ref/ (abgerufen am 31. März 2020).

Beckett, David u. a.: *RDF 1.1 Turtle. Terse RDF Triple Language*, online: https://www.w3.org/TR/2014/REC-turtle-20140225/ (abgerufen am 3. April 2020).

Berners-Lee, Tim u. a.: *Architecture of the World Wide Web. Volume One*, online: https://www.w3.org/TR/webarch/\#pr-namespace-documents (abgerufen am 9. Mai 2020).

Berners-Lee, Tim: „Cool URIs Don't Change", online: https://www.w3.org/Provider/Style/URI (abgerufen am 13. August 2020).

Berners-Lee, Tim: „Linked Data", online: https://www.w3.org/DesignIssues/LinkedData.html (abgerufen am 27. August 2020).

Berners-Lee, Tim, Hendler, James und Lassila, Ora: „A new form of Web Content", in: *Sci. Am.*, (2002), S. 24--30.

Bertram, Jutta: *Einführung in die inhaltliche Erschließung. Grundlagen, Methoden, Instrumente* (= Content and communication. Terminology, Language Resources and Semantic Interoperability 2), Würzburg 2005.

Bicher, Katrin und Wiermann, Barbara: „Normdaten zu ‚Werken der Musik' und ihr Potenzial für die digitale Musikwissenschaft", in: *Bibl. Forsch. Prax.* 42/2 (2018), S. 222--235, DOI: https://doi.org/10.1515/bfp-2018-0043.

Bizer, Christian, Heath, Tom und Berners-Lee, Tim: „Linked Data - The Story So Far", in: *Int. J. Semantic Web Inf. Syst.* 5 (2009), S. 1--22.

Bizer, Christian, Cyganiak, Richard und Heath, Tom: „How to publish Linked Data on the Web", online: http://wifo5-03.informatik.uni-mannheim.de/bizer/pub/LinkedDataTutorial/ (abgerufen am 20. Mai 2020).

Bock, Conrad u. a.: *OWL 2 Web Ontology Language. Structural Specification and Functional-Style Syntax (Second Edition)*, online: https://www.w3.org/TR/owl2-syntax/\#Named\_Individuals (abgerufen am 30. März 2020).

van Boer, Bertil Hermann: „Observations on Bach's Use of the Horn. Part I", in: *Bach* 11/2 (1980), S. 21--28.

Brickley, Dan und Miller, Libby: *Friend of a Friend Ontology*, online: http://xmlns.com/foaf/spec/ (abgerufen am 27. August 2020).

Busse, Johannes u. a.: „Was bedeutet eigentlich Ontologie? Ein Begriff aus der Philosophie im Licht verschiedener Disziplinen", in: *Inform.-Spektrum* 37/4 (2014), S. 286--297, DOI: https://doi.org/10.1007/s00287-012-0619-2.

Cagle, Kurt: „Why the Semantic Web Has Failed", online: https://www.linkedin.com/pulse/why-semantic-web-has-failed-kurt-cagle (abgerufen am 22. April 2020).

Choffé, Pierre, Troncy, Raphael und Lisena, Pasquale: „DOREMUS Ontology", in: *GitHub*, online: https://github.com/DOREMUS-ANR/doremus-ontology (abgerufen am 25. Mai 2020).

Csiba, Gisela und Csiba, Jozsef: *Die Blechblasinstrumente in Johann Sebastian Bachs Werken*, Kassel u.a. 1994.

Deutsche Nationalbibliothek (Hrsg.): „Bach, Johann Sebastian: Was mir behagt, ist nur die muntre Jagd, BWV 208", in: *Gemeinsame Normdatei*, online**:**

http://d-nb.info/gnd/300009178 (abgerufen am 11. Juni 2020).

Deutsche Nationalbibliothek (Hrsg.): „Mozart, Leopold \[und Eberlin, Johann Ernst -- Anm. d. Verf.\]: Der Morgen und der Abend", in: *Gemeinsame Normdatei*, online**:**

http://d-nb.info/gnd/1096212412 (abgerufen am 11. Juni 2020).

Deutsche Nationalbibliothek (Hrsg.): „Weber, Carl Maria von: Der Freischütz. Ouvertüre", in: *Gemeinsame Normdatei*, online**:** http://d-nb.info/gnd/300171528 (abgerufen am 11. Juni 2020).

Deutsche Nationalbibliothek (Hrsg.): *Gemeinsame Normdatei*, online: <https://d-nb.info/> (abgerufen am 11. Juni 2020).

Deutsche Nationalbibliothek: „IFLA Library Reference Model (IFLA LRM)", online: https://www.dnb.de/DE/Professionell/Standardisierung/Standards/\_content/ifla\_lrm\_akk.html (abgerufen am 28. August 2020).

Dodds, Leigh und Davis, Ian: *Linked Data Patterns. A Pattern Catalogue for Modelling, Publishing, and Consuming Linked Data*, 2012, online: https://patterns.dataincubator.org/book/ (abgerufen am 13. April 2020).

Doerr, Martin u. a.: *Definition of the CIDOC Conceptual Reference Model* A, 2020 (= CIDOC Conceptual Reference Model, online: http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM\_v6.2.9%2030-4-2020%20.pdf.

Doing Reusable Musical Data (Hrsg.): *DOREMUS Ontology*, online: http://data.doremus.org/ontology/ (abgerufen am 25. Mai 2020).

Dublin Core Metadata Initiative: „DCMI Metadata Terms", online: https://www.dublincore.org/specifications/dublin-core/dcmi-terms/\#relation (abgerufen am 2. Juni 2020).

Ernst, Hartmut, Schmidt, Jochen und Beneken, Gerd: *Grundkurs Informatik. Grundlagen und Konzepte für die erfolgreiche IT-Praxis - Eine umfassende, praxisorientierte Einführung*, Wiesbaden ^5^2015.

Fischer, Peter und Hofer, Peter: *Lexikon der Informatik*, Berlin, Heidelberg 2008, DOI: https://doi.org/10.1007/978-3-540-72550-3\_10 (abgerufen am 25. März 2020).

Focht, Josef (Hrsg.): *musiXplora*, online: https://home.uni-leipzig.de/mim/about/ (abgerufen am 26. Mai 2020).

Freire, Nuno, Charles, Valentine und Isaac, Antoine: „Evaluation of Schema.org for Aggregation of Cultural Heritage Metadata", in: *The Semantic Web. 15th International Conference, ESWC 2018, Heraklion, Crete, Greece, June 3--7, 2018. Proceedings* (= Lecture Notes in Computer Science 10843), hrsg. von Aldo Gangemi u. a., Cham 2018 (= Lecture Notes in Computer Science 10843), S. 225--239, DOI: https://doi.org/10.1007/978-3-319-93417-4\_15 (abgerufen am 11. Juni 2020).

Gängler, Thomas: *Semantic Federation of Musical and Music-Related Information for Establishing a Personal Music Knowledge Base*, Dresden 2011, online: https://tud.qucosa.de/api/qucosa%3A25670/attachment/ATT-0/.

Go Fair International Support and Coordination Office: „FAIR Principles", in: *GO FAIR*, online: https://www.go-fair.org/fair-principles/ (abgerufen am 15. August 2020).

Gyrard, Amelie: *SemWeb Best Practices for Dummies with PerfectO*, 2017, online: http://perfectsemanticweb.appspot.com/documentation/SemanticWebBestPracticesForDummies.pdf.

Haffner, Alexander: *GND Ontology*, online: https://d-nb.info/standards/elementset/gnd (abgerufen am 27. August 2020).

Haslhofer, Bernhard und Klas, Wolfgang: „A survey of Techniques for Achieving Metadata Interoperability", in: *ACM Comput. Surv.*, 42/2 (2010), S. 7:1-7:37, DOI: https://doi.org/10.1145/1667062.1667064.

Haynes, Bruce: Art. „Stimmton", in: *MGG Online*, Kassel, Stuttgart, New York 2016, online: https://www.mgg-online.com/mgg/stable/14734 (abgerufen am 30. März 2020).

Heath, Tom und Bizer, Christian: *Linked Data. Evolving the Web into a Global Data Space*, o. O. 2011 (= Synthesis Lectures on the Semantic Web: Theory and Technology), online: https://doi.org/10.2200/S00334ED1V01Y201102WBE001 (abgerufen am 21. April 2020).

Heidegger, Martin: *Sein und Zeit*, Tübingen ^19^2006.

Helmholtz, Hermann von: *Die Lehre von den Tonempfindungen als physiologische Grundlage für die Theorie der Musik*, Braunschweig 1863, online: http://digbib.ubka.uni-karlsruhe.de/volltexte/wasbleibt/27162822/27162822.pdf.

Hitzler, Pascal u. a.: *Semantic Web. Grundlagen* (= eXamen.press), Berlin und Heidelberg 2008.

Hocker, Jürgen: Art. „Mechanische Musikinstrumente, Repertoire, Freistehende Walzenorgeln", in: *MGG Online*, Kassel, Stuttgart, New York 2016, online: https://www.mgg-online.com/mgg/stable/55716 (abgerufen am 28. März 2020).

Hornbostel, Erich von und Sachs, Curt: „Systematik der Musikinstrumente. Ein Versuch", in: *Z. Für Ethnol.* 46/4 und 5 (1914), S. 553--590.

Hyvönen, Eero: *Publishing and Using Cultural Heritage Linked Data on the Semantic Web*, o. O. 2012 (= Synthesis Lectures on the Semantic Web: Theory and Technology).

Janetzky, Kurt und Brüchle, Bernhard: *Das Horn. Eine kleine Chronik seines Werdens und Wirkens* (= Unsere Musikinstrumente 6), Mainz u.a. 1984.

International Association of Music Libraries, Archives and Documentation Centres (Hrsg.), Doing Reusable Music Data (Hrsg.), „List of Media of Performances according to IAML", online: http://data.doremus.org/vocabulary/iaml/mop/ (abgerufen am 2. Juni 2020).

Irish Traditional Music Archive (Hrsg.), *Linked Irish Traditional Music Ontology*, online: https://www.itma.ie/litmus/ontology (abgerufen am 26. Mai 2020).

Képéklian, Gabriel, Curé, Olivier und Bihanic, Laurent: „From the Web of Documents to the Linked Data", in: *Business Intelligence. 4th European Summer School, eBISS 2014, Berlin, Germany, July 6-11, 2014, Tutorial Lectures* (= Lecture Notes in Business Information Processing 205), hrsg. von Esteban Zimányi und Ralf-Detlef Kutsche, Cham u.a. 2015, S. 60--87, DOI: https://doi.org/10.1007/978-3-319-17551-5\_3 (abgerufen am 20. Mai 2020).

Kusnick, Jakob u. a.: „A Timeline Metaphor for Analyzing the Relationships between Musical Instruments and Musical Pieces", in: *Proceedings of the 15th International Joint Conference on Computer Vision, Imaging and Computer Graphics Theory and Applications*, o. Hrsg., Valletta 2020, S. 240--251, DOI: https://doi.org/10.5220/0008990502400251 (abgerufen am 26. Mai 2020).

Libin, Laurence: Art. „Musical Instrument", in: *Grove Music Online*, 2018, online: https://www.oxfordmusiconline.com/grovemusic/view/10.1093/gmo/9781561592630.001.0001/omo-9781561592630-e-3000000097.

Library of Congress (Hrsg.): *Library of Congress Names*, online: http://id.loc.gov/authorities/names.html (abgerufen am 25. Mai 2020).

Lisena, Pasquale u. a.: „Controlled Vocabularies for Music Metadata", in: *Proceedings* of the *19th International Society* for *Music Information Retrieval Conference* *ISMIR 2018,* hrsg. v. Emilia Gómez u.a., Paris 2018, 7 ungezählte Seiten.

Lisena, Pasquale u. a.: „Improving (Re-) Usability of Musical Datasets. An Overview of the DOREMUS Project", in: *Bibl. Forsch. Prax.* 42/2 (2018), S. 194--205, DOI: https://doi.org/10.1515/bfp-2018-0023.

Lorimer, Nancy u. a.: *Performed Music Ontology*, online: https://github.com/LD4P/PerformedMusicOntology (abgerufen am 2. Juni 2020).

Lorimer, Nancy u. a.: *Performed Music Ontology*, online: https://wiki.lyrasis.org/display/LD4P/Performed+Music+Ontology (abgerufen am 2. Juni 2020).

Mariana, Curado Malta, Baptista, Ana Alice, Walk, Paul (Hrsg.): *Developing Metadata Application Profiles* (= Advances in Web Technologies and Engineering), Hershey PA, USA 2017, online: https://core.ac.uk/download/pdf/83044379.pdf.

van der Meer, John Henry: Art. „Instrumentenkunde. Definition", in: *MGG Online*, Kassel, Stuttgart, New York 2016.

Meghini, Carlo u. a.: *Europeana Data Model v5.2.8*, 2017, online: https://pro.europeana.eu/files/Europeana\_Professional/Share\_your\_data/Technical\_requirements/EDM\_Documentation//EDM\_Definition\_v5.2.8\_102017.pdf.

Miles, Alistair, Rogers, Nikki und Beckett, Dave: „SKOS-Core 1.0 Guide", online: https://www.w3.org/2001/sw/Europe/reports/thes/1.0/guide/20040504/\#3.5 (abgerufen am 30. Mai 2020).

Münnich, Stefan: „Ontologien in der Praxis. Möglichkeiten und Herausforderungen für die Modellierung musikwissenschaftlicher/musikeditorischer Wissensstrukturen", in: *Mf*, 71/4 (2018), S. 319--337.

Museum Digital: „Hornbostel-Sachs-Systematik", in *md:term*, online: https://term.museum-digital.de/hornbostel/tag/84 (abgerufen am 26. August 2020).

Musical Instrument Museums Online: *MIMO Thesaurus*, online: http://www.mimo-db.eu/InstrumentsKeywords (abgerufen am 2. Juni 2020).

Musical Instrument Museums Online: *Database*, online: <http://www.mimo-db.eu/> (abgerufen am 28. August 2020).

*The* *Music Ontology*, online: http://musicontology.com/ (abgerufen am 26. Mai 2020).

Neovesky, Anna und Vlahovits, Frederic von: „Interconnecting Music Repositories with Semantic Web Technologies. An RDF- and Schema.org-based Approach", in: *Digit. Scholarsh. Humanit.* (2020), DOI: https://doi.org/10.1093/llc/fqaa019.

Network Development and MARC Standards Office (Hrsg.): *MARC 21 Format for Bibliographic Data*, online: https://www.loc.gov/marc/bibliographic/bd245.html (abgerufen am 31. Januar 2020).

Niewerth, Dennis: *Dinge-Nutzer-Netze. Von der Virtualisierung des Musealen zur Musealisierung des Virtuellen* (= Edition Museum 30), Bielefeld und Wetzlar 2018.

Niggemann, Elisabeth u. a.: *GND für Kulturdaten (GND4C). 1. Projektphase*, \[Frankfurt\] 2017.

Noy, Natalya und McGuinness, Deborah: *Ontology Development 101. A Guide to Creating Your First Ontology*, online: https://protege.stanford.edu/publications/ontology\_development/ontology101.pdf.

Manfred Pfister, Art. „Performance/Performativität", in: *Metzler Lexikon Literatur- und Kulturtheorie. Ansätze - Personen - Grundbegriffe*, Stuttgart u.a. ^4^2008, S. 562--564.

Nurmikko-Fuller, Terhi u. a.: „In Collaboration with In Concert. Reflecting a Digital Library as Linked Data for Performance Ephemera", in: *Proceedings of the 3rd International Workshop on Digital Libraries for Musicology - DLfM 2016*, o. Hrsg., New York 2016, S. 17--24, DOI: https://doi.org/10.1145/2970044.2970049 (abgerufen am 25. Mai 2020).

Nurmikko-Fuller, Terhi u. a.: „Building Prototypes Aggregating Musicological Datasets on the Semantic Web", in: *Bibl. Forsch. Prax.* 42/2 (2018), S. 206--221, DOI: https://doi.org/10.1515/bfp-2018-0025.

Online Computer Library Center (Hrsg.): *Virtual International Authority File*, online: http://viaf.org/ (abgerufen am 25. Mai 2020).

Ontology Engineering Group -- UPM (Hrsg.): *Linked Open Vocabularies (LOV)*, online: https://lov.linkeddata.es/dataset/lov/ (abgerufen am 3. Juni 2020).

Pintscher, Lydia u. a.: „Strategy for the Wikibase Ecosystem" (2019), online: https://upload.wikimedia.org/wikipedia/commons/c/cc/Strategy\_for\_Wikibase\_Ecosystem.pdf.

RDA Steering Committee (Hrsg.): „6.15.1.1 Scope", in: *RDA-Toolkit*, online: https://access.rdatoolkit.org/ (abgerufen am 2. Juni 2020).

RDF Core Working Group: *Resource Description Framework (RDF). Concepts and Abstract Data Model*, online: https://www.w3.org/TR/2002/WD-rdf-concepts-20020829/ (abgerufen am 11. Mai 2020).

RDF Core Working Group: *Resource Description Framework (RDF) Schema Specification 1.0*, online: https://www.w3.org/2001/sw/RDFCore/Schema/20010913/ (abgerufen am 25. Mai 2020).

RDF Core Working Group: *RDF Primer*, online: https://www.w3.org/TR/rdf-primer/\#rdfvalue (abgerufen am 26. Juli 2020).

RDF Data Shapes Working Group: *Shapes Constraint Language (SHACL)*, online: https://www.w3.org/TR/shacl/ (abgerufen am 15. August 2020).

RDF Working Group: *RDF-Schema*, online: http://www.w3.org/2000/01/rdf-schema\# (abgerufen am 10. Mai 2020).

RDF Working Group: *RDF Schema 1.1*, online: https://www.w3.org/TR/rdf-schema/ (abgerufen am 11. Juni 2020).

RDF Working Group: *RDF 1.1 Primer*, online: https://www.w3.org/TR/2014/NOTE-rdf11-primer-20140624/\#2.\_Why\_Use\_RDF? (abgerufen am 17. März 2020).

Répertoire Internationale des Sources Musicales (Hrsg.): „Bach, Johann Sebastian (1685--1750), Was mir behagt ist nur die muntre Jagd", in: *RISM Katalog*, online: https://opac.rism.info/search?id=467004203&View=rism (abgerufen am 31. Januar 2020).

Répertoire Internationale des Sources Musicales: „Unternehmen", online: http://www.rism.info/de/unternehmen.html\#c17 (abgerufen am 21. März 2020).

Répertoire Internationale des Sources Musicales: „Hilfe. Anleitungen und Tutorials", in: *RISM Katalog*, online: https://opac.rism.info/de/hauptmenu/kachelmenu/hilfe\#c52

Riedel, Alan: „\#Musicology \#SemanticWeb experts, I humbly ask your counsel: are you aware of vocabulary to model audio examples? For instance: \<track a\> \<is an audio example of\> \<work a\>", in: *Twitter*, online: https://twitter.com/SPARQLCRMSUPPE/status/1270298014519869440 (abgerufen am 11. Juni 2020).

Semantic Web Deployment Working Group: *SKOS Simple Knowledge Organization System*, online: https://www.w3.org/2004/02/skos/ (abgerufen am 23. August 2020).

Semantic Web Deployment Working Group: *SKOS Simple Knowledge Organization System Reference*, online: https://www.w3.org/TR/skos-reference/ (abgerufen am 26. Mai 2020).

Shape Expressions Community Group: *Shape Expressions (ShEx) 2.1 Primer*, online: https://shex.io/shex-primer/ (abgerufen am 15. August 2020).

Singhal, Amit: „Introducing the Knowledge Graph. Things, not Strings", online: https://blog.google/products/search/introducing-knowledge-graph-things-not/ (abgerufen am 18. Mai 2020).

De Souza, Jonathan: *Music at Hand* (= Oxford Studies in Music Theory), New York 2017, DOI: https://doi.org/10.1093/acprof:oso/9780190271114.001.0001 (abgerufen am 11. August 2020).

Stock, Wolfgang und Stock, Mechthild: *Wissensrepräsentation. Informationen auswerten und bereitstellen*, München 2008.

Stuckenschmidt, Heiner: *Ontologien. Konzepte, Technologien und Anwendungen* (= Informatik im Fokus), Heidelberg u.a. ^2^2011.

Szeredi, Péter u. a.: *The Semantic Web Explained. The Technology and Mathematics Behind Web 3.0*, Cambridge 2014.

Taruskin, Richard: *The Earliest Notations to the Sixtenth Century* (= The Oxford History of Western Music 1), Oxford u.a. 2005.

Waibel, Günter und Erway, Ricky: „Think Globally, Act Locally. Library, Archive, and Museum Collaboration", in: *Mus. Manag. Curatorship*, 24/4 (2009), S. 323--335, DOI: https://doi.org/10.1080/09647770903314704.

Weigl, David: „Music ontology offers one way \-- see slide 20 in

\@music\_enfanthen and my slide deck here: http://tinyurl.com/LinkedDataESS. tl;dr: a performance of a musical work is recorded as a signal which is published as a musical manifestation that is available as an audio file. ", in: *Twitter*, online: https://twitter.com/MusiCog/status/1270301139293155333 (abgerufen am 11. Juni 2020).

Weigl, David: „ Small follow-up, you could also use schema:recordingOf (from a schema:MusicComposition to a schema:MusicRecording). This may be more appropriate if the audio you\'re linking is published (e.g. as a track on a CD), rather than, say, a field recording", in: *Twitter*, online: https://twitter.com/MusiCog/status/1270301139293155333 (abgerufen am 11. Juni 2020).

Wikimedia (Hrsg.): *wikidata*, online: https://www.wikidata.org/ (abgerufen am 27. August 2020).

Wogram, Klaus: *Ein Beitrag zur Ermittlung der Stimmung von Blechblasinstrumenten*, Braunschweig 1972.

World Wide Web Consortium (Hrsg.): *Examples of RDF Validation*, online: https://www.w3.org/2012/12/rdf-val/SOTA (abgerufen am 13. Mai 2020).

World Wide Web Consortium (Hrsg.): „Semantic Web", online: https://www.w3.org/standards/semanticweb (abgerufen am 12. August 2020).

World Wide Web Consortium (Hrsg.): „Vocabularies", online: https://www.w3.org/standards/semanticweb/ontology (abgerufen am 13. August 2020).

World Wide Web Consortium (Hrsg.): *W3C Semantic Web Frequently Asked Questions*, online: https://www.w3.org/2001/sw/SW-FAQ\#whrules (abgerufen am 22. April 2020).

W3C Schema.org Community Group: *Schema.org*, online: https://schema.org/ (abgerufen am 11. Juni 2020).

The W3C Technical Architecture Group: *Associating Resources with Namespaces*, online: https://www.w3.org/2001/tag/doc/nsDocuments/\#div.semwebNSDoc (abgerufen am 31. März 2020).

Ziku, Marina: „Digital Cultural Heritage and Linked Data. Semantically-Informed Conceptualisations and Practices with a Focus on Intangible Cultural Heritage", in: *Liber Q.* 30/1 (2020), S. 1--16, DOI: https://doi.org/http://doi.org/10.18352/lq.10315.

Externes Bildmaterial
---------------------

Brühl, Johann Benjamin: *Bildnis des Herzogs Christian von Sachsen-Weißenfels*, online: http://www.portraitindex.de/documents/obj/33201240, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Deutsche Digitale Bibliothek: „Logo der Deutschen Digitalen Bibliothek, dem zentralen Portal für Kultur und Wissen in Deutschland.", online: https://upload.wikimedia.org/wikipedia/commons/thumb/5/50/Logo\_Deutsche\_Digitale\_Bibliothek.svg/1000px-Logo\_Deutsche\_Digitale\_Bibliothek.svg.png, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Erigena: „Image of a Saxtubist from ,Le Monde Illustré of 1867'", online: https://commons.wikimedia.org/wiki/Category:Saxtuba\#/media/File:Saxtuba1867.jpg, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Frankee 67: „Windows Media Player 6.01.05.0217 under Windows 95", online: https://commons.wikimedia.org/wiki/File:MediaPlayer601Info.png;MediaPlayer601Info.png, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Hartwig, Maja: „Example of Figured Bass", online: https://github.com/music-encoding/sample-encodings/blob/master/MEI\_4.0/Musical-features/snippets/Figured\_Bass.mei, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Rism Zentralredaktion Ffm: „This is the official logo of the Répertoire International des Sources Musicales (RISM) ", online: https://commons.wikimedia.org/wiki/File:RISM\_Organization\_Logo.jpg;RISM\_Organization\_Logo.jpg, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Rezonansowy: „IMSLP logo, used since 2016.", online: https://commons.wikimedia.org/wiki/Category:IMSLP\#/media/File:IMSLP\_logo\_(2016).png, Lizenz: Public Domain, (abgerufen am 27. August 2020).

Planemad: „The Wikidata Logo with English Text", online: https://upload.wikimedia.org/wikipedia/commons/thumb/6/66/Wikidata-logo-en.svg/500px-Wikidata-logo-en.svg.png, Lizenz: Public Domain, (abgerufen am 27. August 2020).

[^1]: Jonathan De Souza, *Music at Hand* (= Oxford Studies in Music Theory), New York 2017, S. 20--23, DOI: https://doi.org/10.1093/acprof:oso/9780190271114.001.0001 (abgerufen am 11. August 2020).

[^2]: Laurence Libin, Art. „Musical Instrument", in: *Grove Music Online*, 2018, online: https://www.oxfordmusiconline.com/grovemusic/view/10.1093/gmo/9781561592630.001.0001/omo-9781561592630-e-3000000097.

[^3]: John Henry van der Meer, Art. „Instrumentenkunde. Definition", in: *MGG Online*, Kassel, Stuttgart, New York 2016.

[^4]: Akronym für *Galleries, Libraries, Archives, Museums*.

[^5]: Eero Hyvönen, *Publishing and Using Cultural Heritage Linked Data on the Semantic Web*, o. O. 2012 (= Synthesis Lectures on the Semantic Web: Theory and Technology), S. 7--8.

[^6]: Eine sehr umfassende Auseinandersetzung mit Chancen für Einrichtungen und Nutzer findet sich in: Günter Waibel, Ricky Erway, „Think Globally, Act Locally. Library, Archive, and Museum Collaboration", in: *Mus. Manag. Curatorship* 24/4 (2009), S. 323--335, hier S. 323--335, DOI: https://doi.org/10.1080/09647770903314704.

[^7]: Elisabeth Niggemann u. a., *GND für Kulturdaten (GND4C). 1. Projektphase*, \[Frankfurt\] 2017, S. 2.

[^8]: Niggemann u. a., *GND für Kulturdaten (GND4C). 1. Projektphase*.

[^9]: Reinhard Altenhöner u. a., „NFDI4Culture - Consortium for Research Data on Material and Immaterial Cultural Heritage", in: *Res. Ideas Outcomes* 6 (2020), DOI: https://doi.org/10.3897/rio.6.e57036.

[^10]: World Wide Web Consortium (Hrsg.), „Semantic Web", online: https://www.w3.org/standards/semanticweb/ (abgerufen am 12. August 2020).

[^11]: Für weitere Informationen s.: Mariana Curado Malta, Ana Alice Baptista, Paul Walk (Hrsg.), *Developing Metadata Application Profiles* (= Advances in Web Technologies and Engineering), Hershey PA, USA 2017, online: https://core.ac.uk/download/pdf/83044379.pdf.

[^12]: https://github.com/SPARQLCRMSUPPE/VocsForInstruments

[^13]: Einführende Werke zum Semantic Web und einzelner Vokabulare finden sich in: Dean Allemang, James Hendler, *Semantic Web for the Working Ontologist. Effective Modeling in RDFS and OWL*, Waltham, MA ^2^2011; Pascal Hitzler u. a., *Semantic Web. Grundlagen* (= eXamen.press), Berlin und Heidelberg 2008; sowie Natalya Noy, Deborah McGuinness, *Ontology Development 101. A Guide to Creating Your First Ontology*, online: https://protege.stanford.edu/publications/ontology\_development/ontology101.pdf; zur Modellierung von Ontologien. Hyvönen, *Publishing and Using Cultural Heritage Linked Data on the Semantic Web* beinhaltet zudem gute Hinweise für die Publikation von Linked Data in Kulturerbeeinrichtungen; Leigh Dodds, Ian Davis, *Linked Data Patterns. A Pattern Catalogue for Modelling, Publishing, and Consuming Linked Data*, 2012, online: https://patterns.dataincubator.org/book/ (abgerufen am 13. April 2020) zu technischen Fragen.

[^14]: Stefan Münnich, „Ontologien in der Praxis. Möglichkeiten und Herausforderungen für die Modellierung musikwissenschaftlicher/musikeditorischer Wissensstrukturen", in: *Mf*, 71/4 (2018), S. 319--337, hier S. 337.

[^15]: World Wide Web Consortium (Hrsg.), *W3C Semantic Web Frequently Asked Questions*, online: https://www.w3.org/2001/sw/SW-FAQ\#whrules (abgerufen am 22. April 2020).

[^16]: Eine sehr gute Einführung bieten die *Semantic Web-*Pioniere Tim Berners-Lee, James Hendler und Ora Lassila, in: Tim Berners-Lee, James Hendler, Ora Lassila, „A new form of Web Content", in: *Sci. Am.*, (2002), S. 24--30.

[^17]: Péter Szeredi u. a., *The Semantic Web Explained. The Technology and Mathematics Behind Web 3.0*, Cambridge 2014, S. 21.

[^18]: Heiner Stuckenschmidt, *Ontologien. Konzepte, Technologien und Anwendungen* (= Informatik im Fokus), Heidelberg u.a. ^2^2011.

[^19]: Ebd., S. 10.

[^20]: Peter Fischer, Peter Hofer, *Lexikon der Informatik*, Berlin, Heidelberg 2008, S. 275, DOI: https://doi.org/10.1007/978-3-540-72550-3\_10 (abgerufen am 25. März 2020).

[^21]: Sehr Interessant ist in diesem Zusammenhang: Johannes Busse u. a., „Was bedeutet eigentlich Ontologie? Ein Begriff aus der Philosophie im Licht verschiedener Disziplinen", in: *Inform.-Spektrum* 37/4 (2014), S. 286--297, hier S. 286--297, DOI: https://doi.org/10.1007/s00287-012-0619-2., in dem eine interdisziplinäre Annäherung an den Begriff erfolgt.

[^22]: World Wide Web Consortium (Hrsg.), „Vocabularies", online: https://www.w3.org/standards/semanticweb/ontology (abgerufen am 13. August 2020).

[^23]: Wolfgang Stock, Mechthild Stock, *Wissensrepräsentation. Informationen auswerten und bereitstellen*, München 2008, S. 188. Stock spricht von „Nomenklaturen" statt von „Vokabularen".

[^24]: Busse u. a.: „Was bedeutet eigentlich Ontologie?", S. 289.

[^25]: Stock/Stock, *Wissensrepräsentation*, S. 257.

[^26]: Jutta Bertram, *Einführung in die inhaltliche Erschließung. Grundlagen, Methoden, Instrumente* (= Content and communication. Terminology, Language Resources and Semantic Interoperability 2), Würzburg 2005, S. 261.

[^27]: „A metadata schema is simply a set of elements with a precise semantic definition, optionally connected by some structure." Vgl.: Bernhard Haslhofer, Wolfgang Klas, „A survey of Techniques for Achieving Metadata Interoperability", in: *ACM Comput. Surv.*, 42/2 (2010), S. 7:1-7:37, hier S. 7:8, DOI: https://doi.org/10.1145/1667062.1667064.

[^28]: Ebd., S. 7:25.

[^29]: Vgl. Insb.: Tim Berners-Lee, James Hendler, Ora Lassila, „A new form of Web Content", in: *Sci. Am.*, (2002), S. 24--30.

[^30]: Vgl. etwa: Kurt Cagle, „Why the Semantic Web Has Failed", online: https://www.linkedin.com/pulse/why-semantic-web-has-failed-kurt-cagle (abgerufen am 22. April 2020).

[^31]: Vgl. Werkdatensatz in der Gemeinsamen Normdatei (GND): http://d-nb.info/gnd/300009178.

[^32]: Répertoire Internationale des Sources Musicales, „Unternehmen", online: http://www.rism.info/de/unternehmen.html\#c17 (abgerufen am 21. März 2020).

[^33]: Répertoire Internationale des Sources Musicales (Hrsg.), „Bach, Johann Sebastian (1685--1750), Was mir behagt ist nur die muntre Jagd", in: *RISM Katalog*, online: https://opac.rism.info/search?id=467004203&View=rism (abgerufen am 31. Januar 2020).

[^34]: Network Development and MARC Standards Office (Hrsg.), „245 -- Title Statement", in: *MARC 21 Format for Bibliographic Data*, online: https://www.loc.gov/marc/bibliographic/bd245.html (abgerufen am 31. Januar 2020).

[^35]: Répertoire Internationale des Sources Musicales: „Bach, Johann Sebastian (1685--1750), Was mir behagt ist nur die muntre Jagd".

[^36]: Network Development and MARC Standards Office (Hrsg.), „59X -- Local Notes (R)", in: *MARC 21 Format for Bibliographic Data*, online: https://www.loc.gov/marc/bibliographic/bd59x.html (abgerufen am 31. Januar 2020).

[^37]: RISM hält im Netz eine Liste der verwendeten Abkürzungen und Bezeichnungen vor: Répertoire Internationale des Sources Musicales, „Hilfe. Anleitungen und Tutorials", in: *RISM Katalog*, online: https://opac.rism.info/de/hauptmenu/kachelmenu/hilfe\#c52 (abgerufen am 31. Juli 2020). Allerdings ist dort der Term *cor da caccia* nicht verzeichnet. Auf Nachfrage in der RISM-Zentralredaktion stellte sich heraus, dass noch ein zweiter, dort gepflegter interner Thesaurus existiert, in dem jedoch der Term ebenfalls fehlte. Mittlerweile ist er in das interne, jedoch nicht das öffentlich einsehbare Vokabular eingepflegt (Quelle: persönliche Kommunikation).

[^38]: Sie sind daher selbstverständlich beispielsweise auch nicht über den *RISM SPARQL Endpoint* suchbar.

[^39]: Es scheint sich hier um einen multilingualen synthetischen Neologismus aus den französischen und italienischen Begriffen *cor de chasse* und *corno da caccia* zu handeln.

[^40]: *Google*-Suche mit Suchbegriff „cor da caccia". Durchgeführt am 31.01.2020.

[^41]: Wie bereits erwähnt, ist es nicht Ziel dieser Arbeit, klassifikatorische Fragestellungen zu Musikinstrumenten zu untersuchen.

[^42]: Gisela Csiba, Jozsef Csiba, *Die Blechblasinstrumente in Johann Sebastian Bachs Werken*, Kassel u.a. 1994.

[^43]: Johann Sebastian Bach, *Was mir behagt, ist nur die muntre Jagd*, D-B Mus.ms. Bach P 42, Bl. \[81\].

[^44]: Tatsächlich existieren bereits dank des DOREMUS-Projekts Pasquale Lisena u. a., „Improving (Re-) Usability of Musical Datasets. An Overview of the DOREMUS Project", in: *Bibl. Forsch. Prax.* 42/2 (2018), S. 194--205, DOI: https://doi.org/10.1515/bfp-2018-0023 Mappings etwa zwischen dem IAML Medium of Performance-Vokabular International Association of Music Libraries, Archives and Documentation Centres (Hrsg.), Doing Reusable Music Data, „List of Media of Performances according to IAML", online: http://data.doremus.org/vocabulary/iaml/mop/ (abgerufen am 2. Juni 2020) und dem MIMO-Thesaurus. Laut Korrespondenz mit RISM ist zudem die Erstellung eines neuen RISM-Thesaurus' mit entsprechenden Mappings für 2022 vorgesehen (mündl. Auskunft d. RISM-Zentralredaktion vom 21.02.2020).

[^45]: Für eine Disambiguierung der folgenden Begriffe s. Kapitel 4.3.

[^46]: Wolfgang Auhagen, Art. „Stimmung und Temperatur", in: *MGG Online*, Kassel, Stuttgart, New York 2016, online: https://www-mgg-online-com.wwwdb.dbod.de/article?id=mgg16098&v=1.0&rs=id-41932d6d-11fc-3f8c-2d92-74829fd97f5e&q=stimmung (abgerufen am 7. Februar 2020).

[^47]: Wie sie etwa in der Bezeichnung „in F" (der Grundton *f* also nicht anhand seiner Frequenz fest definiert) gemeint ist.

[^48]: Etwa *a'* = 440 Hz.

[^49]: Etwa die mitteltönige Stimmung einer Orgel.

[^50]: Erich von Hornbostel, Curt Sachs, „Systematik der Musikinstrumente. Ein Versuch", in: *Z. Für Ethnol.* 46/4 und 5 (1914), S. 553--590, hier S. 23031207. Online referenzierbar etwa über: Museum Digital, „Hornbostel-Sachs-Systematik", in: *md:term*, online: https://term.museum-digital.de/hornbostel/tag/84 (abgerufen am 26. August 2020).

[^51]: Musical Instrument Museums Online, *Database*, online: http://www.mimo-db.eu/ (abgerufen am 28. August 2020).

[^52]: Stimmung, Werk aus dem bibliographischen Bereich; Objekt, Material, Instrumententyp aus dem organologischen, musealen Bereich; Fragen zu Werk, Interpretation aus dem Bereich der historischen Musikwissenschaft bzw. dem Editionswesen.

[^53]: Association Répertoire International d'Iconographie Musicale, online: https://ridim.org/ (abgerufen am 24. August 2020).

[^54]: Association Répertoire International d'Iconographie Musicale, *Database*, online: https://db.ridim.org/ (abgerufen am 24. August 2020).

[^55]: Deutsche Digitale Bibliothek, *Deutsche Digitale Bibliothek. Kultur und Wissen online*, online: https://www.deutsche-digitale-bibliothek.de/ (abgerufen am 25. August 2020).

[^56]: *International Music Score Library Project. Petrucci Music Library*, online: https://imslp.org/wiki/Main\_Page (abgerufen am 24. August 2020).

[^57]: Répertoire Internationale des Sources Musicales, *RISM SPARQL-Endpoint*, online: https://opac.rism.info/index.php?id=14&L=1 (abgerufen am 24. August 2020).

[^58]: Da diese Arbeit angesichts ihres Fallbeispiels sehr stark *RISM* als primäre Domäne hervorhebt, kann gar nicht oft genug betont werden, dass jede andere relevante Domäne gleichermaßen im Vordergrund stehen könnte. So ist letztlich auch die Objektentität innerhalb einer Domäne, in diesem Fall dem Musikinstrumentenmuseum der Universität Leipzig, angesiedelt, das seinerseits sein Objekt mit dem *RISM*-Datensatz verlinken könnte, und dasselbe gilt selbstverständlich auch für Editionen, Bibliotheken, Archive, Wirtschaftsunternehmen etc.

[^59]: In den sogenannten *Functional Requirements for Bibliographic Data*, deren Entitätenmodell an dieser Stelle verwendet wird, heißt es: „Ein Werk ist eine abstrakte Entität; es gibt keinen entsprechenden materiellen Gegenstand." (Vgl.:Arbeitsstelle für Standardisierung (Hrsg.), *Funktionelle Anforderungen an bibliografische Datensätze. Abschlussbericht der IFLA Study Group on the Functional Requirements for Bibliographic Records*, Den Haag, Leipzig, Frankfurt 2006, S. 16.)

[^60]: Ebd., S. 18--20.

[^61]: Zur spezifischen Problematik des an dieser Stelle verwendeten *FRBR/FRAD*-Modells bei Werken der Musik s. Katrin Bicher, Barbara Wiermann, „Normdaten zu ‚Werken der Musik' und ihr Potenzial für die digitale Musikwissenschaft", in: *Bibl. Forsch. Prax.* 42/2 (2018), S. 222--235, hier S. 225, DOI: https://doi.org/10.1515/bfp-2018-0043.

[^62]: Arbeitsstelle für Standardisierung (Hrsg.), *Funktionelle Anforderungen an bibliografische Datensätze*, S. 20--22.

[^63]: Ebd., S. 22--23.

[^64]: https://mimo-international.com/MIMO/doc/IFD/OAI\_ULEI\_M0001655

[^65]: Ob es sich bei ihm tatsächlich um ein in allen Aspekten passendes Objekt handelt, ist an dieser Stelle zunächst nicht relevant -- es dient vor allem zur Verdeutlichung. (Tatsächlich wäre das Objekt wohl eher dem Typ „Corne du chasse" zuzuordnen. Vgl. die Ausführungen zu *Corno* und *Corne du chasse* in: Csiba/Csiba: *Die Blechblasinstrumente in Johann Sebastian Bachs Werken*, S. S. 57--63 und 46--51.)

[^66]: Ein gleichermaßen illustratives wie auch charmantes Beispiel für eine solche Beziehung wären etwa Leopold Mozarts und Johann Ernst Eberlins Komposition „Der Morgen und der Abend" (http://d-nb.info/gnd/1096212412) für das Hornwerk der Festung Hohensalzburg aus dem 16. Jahrhundert, dem sog. *Salzburger Stier* (Jürgen Hocker, Art. „Mechanische Musikinstrumente, Repertoire, Freistehende Walzenorgeln", in: *MGG Online*, Kassel, Stuttgart, New York 2016, online: https://www.mgg-online.com/mgg/stable/55716 (abgerufen am 28. März 2020)). (Ein klanglicher Eindruck lässt sich hier gewinnen: Salzburger Burgen und Schlösser, „Der Salzburger Stier auf der Festung Hohensalzburg", in: *youtube*, online: https://www.youtube.com/watch?v=psu6nH2m9js (abgerufen am 19. März 2020)).

[^67]: Anders verhielte es sich freilich, würde mit dem hier definierten Schema beispielsweise eine Audioaufnahme einer Aufführung mit modernen Instrumenten erschlossen.

[^68]: Etwa lassen die Stimmungen von unstimmbaren Instrumenten (Blockflöten, Zinken etc.) sehr präzise Rückschlüsse auf die historische Musikpraxis zu (vgl.: Bruce Haynes, Art. „Stimmton", in: *MGG Online*, Kassel, Stuttgart, New York 2016, online: https://www.mgg-online.com/mgg/stable/14734 (abgerufen am 30. März 2020)).

[^69]: Vgl.: Hermann von Helmholtz, *Die Lehre von den Tonempfindungen als physiologische Grundlage für die Theorie der Musik*, Braunschweig 1863, S. 28, 30, online: http://digbib.ubka.uni-karlsruhe.de/volltexte/wasbleibt/27162822/27162822.pdf.

[^70]: Noy/McGuinness, *Ontology Development 101. A Guide to Creating Your First Ontology*. Auch Stuckenschmidt legt diese Vorgehensweise nahe (vgl.: Stuckenschmidt: *Ontologien*.).

[^71]: Zum Begriff siehe Bertram, *Einführung in die inhaltliche Erschließung. Grundlagen, Methoden, Instrumente*, S. 150.

[^72]: Noy/McGuinness, *Ontology Development 101. A Guide to Creating Your First Ontology*, S. 6.

[^73]: Ebd., S. 8.

[^74]: Ebd., S. 11.

[^75]: „Individualbegriffe", Stock/Stock, *Wissensrepräsentation*, S. 84.

[^76]: Siehe hierzu etwa: Hartmut Ernst, Jochen Schmidt, Gerd Beneken, *Grundkurs Informatik. Grundlagen und Konzepte für die erfolgreiche IT-Praxis - Eine umfassende, praxisorientierte Einführung*, Wiesbaden ^5^2015, S. 338--343.

[^77]: So etwa im Falle der Eigenschaft *Entsprechungsgrad* angelegt: Es lassen sich unterschiedliche Grade vorstellen.

[^78]: Ernst/Schmidt/Beneken, *Grundkurs Informatik*, S. 342--343.

[^79]: Ebd., S. 343.

[^80]: Sowohl „simultan" (vgl. etwa den Hornsatz in C. M. v. Webers Ouvertüre zur Oper „Der Freischütz": „Corni in F" sowie „Corni in C"), als auch „sukszessive" ab der Klassik zwischen Sätzen und mit der zunehmenden Erweiterung des harmonischen Raums im Laufe des 19. Jahrhunderts immer mehr auch in kontingenter Abfolge.

[^81]: Tatsächlich kann diese Entität in Zusammenhang mit Objekten lediglich in Verbindung mit Instrumenten Verwendung finden, die etwa aus baulichen, physikalischen Gründen eine solche „Grundstimmung" vorweisen.

[^82]: Vgl. Haynes, „Stimmton".

[^83]: Für diese Arbeit spielen insbesondere *RDFS* (RDF Working Group, *RDF-Schema*, online: http://www.w3.org/2000/01/rdf-schema\#) und *OWL* (Conrad Bock, Achille Fokoue, Peter Haase, Rinke Hoekstra, u. a., *OWL 2 Web Ontology Language Structural Specification and Functional-Style Syntax (Second Edition)*, online: https://www.w3.org/TR/owl2-syntax/\# (abgerufen am 30. März 2020)) eine Rolle.

[^84]: Auf eine Übersicht der gängigen übergeordneten Klassen -- etwa *Literals*, *Datatypes*, *Blank nodes* etc. -- muss an dieser Stelle verzichtet werden.

[^85]: In „*Semantic-Web*-Sprache" ausgedrückt, wären das die Klassen *rdfs:class*, *rdfs:instanceOf* und *rdf:property*.

[^86]: Bertram, *Einführung in die inhaltliche Erschließung. Grundlagen, Methoden, Instrumente*, S. 151.

[^87]: Ebd.

[^88]: Stuckenschmidt, *Ontologien*, S. 95--99.

[^89]: RDF Working Group, *RDF 1.1 Primer*, online: https://www.w3.org/TR/2014/NOTE-rdf11-primer-20140624/\#2.\_Why\_Use\_RDF? (abgerufen am 17. März 2020).

[^90]: RDF Working Group, *RDF Schema 1.1*, online: https://www.w3.org/TR/rdf-schema/ (abgerufen am 10. Mai 2020).

[^91]: Conrad Bock, Achille Fokoue, Peter Haase, Rinke Hoekstra, *OWL 2 Web Ontology Language. Structural Specification and Functional-Style Syntax (Second Edition)*, online: https://www.w3.org/TR/owl2-syntax/ (abgerufen am 30. März 2020).

    Diese Arbeit verwendet *OWL* Full, das die größten Ausdrucksmöglichkeiten bietet und mit RDFS kompatibel ist. (Vgl. Hitzler u. a., *Semantic Web*, S. 125--127.)

[^92]: Stuckenschmidt, *Ontologien*, S. 146.

[^93]: Hitzler u. a., *Semantic Web*, S. 13.

[^94]: David Beckett u. a., *RDF 1.1 Turtle. Terse RDF Triple Language*, online: https://www.w3.org/TR/2014/REC-turtle-20140225/ (abgerufen am 3. April 2020).

[^95]: *OWL2* differenziert zwischen *Object Properties* und *Datatype Properties* (vgl.: Sean Bechhofer u. a., *OWL Web Ontology Language Reference*, online: https://www.w3.org/TR/owl-ref/\#Property (abgerufen am 31. März 2020)). Obwohl etwa *ma:a'=415Hz* prinzipiell auch mit *Datatype Properties* modelliert werden könnte, erscheint diese Detailtiefe für den hier exemplarisch durchgeprobten Anwendungsfall nicht notwendig.

[^96]: Die Serialisierung erfolgt am einfachsten, indem etwa der Ontologie-Editor *Protégé* zu Hilfe genommen wird. Er ermöglicht den Export von Ontologien in vielfältigen Formaten.

[^97]: https://github.com/SPARQLCRMSUPPE/VocsForInstruments/blob/master/namespaces/proteg%C3%A9\_dumps/20200514\_ma.owl (abgerufen am 13. August 2020).

[^98]: Zu den technischen Aspekten von Namespaces im Semantic Web siehe insb. Dodds/Davis, „Linked Data Patterns. A Pattern Catalogue for Modelling, Publishing, and Consuming Linked Data".sowie Tom Heath, Christian Bizer, *Linked Data. Evolving the Web into a Global Data Space*, o. O. 2011 (= Synthesis Lectures on the Semantic Web: Theory and Technology), online: https://doi.org/10.2200/S00334ED1V01Y201102WBE001 (abgerufen am 21. April 2020) und The W3C Technical Architecture Group, *Associating Resources with Namespaces*, online: https://www.w3.org/2001/tag/doc/nsDocuments/\#div.semwebNSDoc (abgerufen am 31. März 2020).

[^99]: Vgl. Tim Berners-Lee u. a., *Architecture of the World Wide Web. Volume One*, online: https://www.w3.org/TR/webarch/\#pr-namespace-documents (abgerufen am 9. Mai 2020).

[^100]: Dieser Schritt erfolgt in Kapitel 4.4.

[^101]: *OWL2* differenziert, anders als etwa *RDFS*, nicht lediglich zwischen Klasse und Instanz, sondern zwischen Klasse und unterschiedlichen Individuen (vgl. Conrad Bock, Achille Fokoue, Peter Haase, Rinke Hoekstra, *OWL 2 Web Ontology Language. Structural Specification and Functional-Style Syntax (Second Edition)*, online: https://www.w3.org/TR/owl2-syntax/\#Named\_Individuals (abgerufen am 30. März 2020).

[^102]: Vgl. etwa die Aussage „Individual instances are the most specific concepts represented in a knowledge base." (Thomas Gängler, *Semantic Federation of Musical and Music-Related Information for Establishing a Personal Music Knowledge Base*, Dresden 2011, S. 18, online: https://tud.qucosa.de/api/qucosa%3A25670/attachment/ATT-0/.).

[^103]: Zur obigen Schreibweise: Es handelt sich um zwei „Tripel". Das Subjekt des Tripels in Zeile 1 wird dank des „`;“` (im Gegensatz zum „`.“`) auf die Aussage (*Statement*) in Zeile 2 übertragen. Gleichbedeutend wäre die Schreibweise:

    `ma:Barockhorn_(Mitteldeutschland)``	rdf:type``	``	owl:Class``	.    ``
    ma:Barockhorn_(Mitteldeutschland) ``	rdfs:subClassOf ``	ma:Instrument_(Klassifikation)``	.`

[^104]: Vgl. etwa: Christian Bizer, Tom Heath, Tim Berners-Lee, „Linked Data - The Story So Far", in: *Int. J. Semantic Web Inf. Syst.* 5 (2009), S. 1--22, hier S. 3.

[^105]: The W3C Technical Architecture Group, *Associating Ressources with Namespaces.*

[^106]: Allemang/Hendler, *Semantic Web for the Working Ontologist*, S. 128--130.

[^107]: Franz Baader u. a. (Hrsg.), *The Description Logic Handbook: Theory, implementation, and applications*, Cambridge u.a. ^2^2007, S. 72, DOI: https://doi.org/10.1017/CBO9780511711787 (abgerufen am 26. August 2020).

[^108]: RDF Core Working Group, *Resource Description Framework (RDF). Concepts and Abstract Data Model*, online: https://www.w3.org/TR/2002/WD-rdf-concepts-20020829/ (abgerufen am 11. Mai 2020).

[^109]: Stuckenschmidt, *Ontologien*, S. 32.\
    Dies etwa im Gegensatz zur *closed world assumption* in herkömmlichen relationalen Datenbanken. Zur Notwendigkeit der Open World Assumption in semantischen Netzen s: Ebd., S. 43.

[^110]: Hitzler u. a., *Semantic Web*, S. 67.

[^111]: Szeredi u. a., *The Semantic Web Explained*, S. 98--99.

[^112]: Stuckenschmidt, *Ontologien*, S. 169.

[^113]: https://www.w3.org/TR/rdf-schema/\#ch\_range (abgerufen am 6. April 2020).

[^114]: https://www.w3.org/TR/rdf-schema/\#ch\_domain (abgerufen am 6. April 2020).

[^115]: Auch in *OWL* verfügt über entsprechende (noch mächtigere) Möglichkeiten, diese Beziehungen auszudrücken (vgl. hierzu etwa: Allemang/Hendler, *Semantic Web for the Working Ontologist*, S. 238--239.) Allerdings erscheint für die Belange dieser Arbeit die Terminologie von *RDFS* als genügend.

[^116]: Hitzler u. a., *Semantic Web*, S. 77.

[^117]: Ebd.: „Jede definierte Einschränkung auf einer Property wirkt also immer global auf jedes Vorkommen dieser Property, weswegen man bei der Angabe solcher Einschränkungen darauf achten muss, immer die allgemeinsten denkbaren Klassen anzugeben (also diejenigen, die mit Sicherheit alle möglichen Ressourcen, die in der fraglichen Beziehung stehen können, enthalten)."

[^118]: World Wide Web Consortium (Hrsg.), *Examples of RDF Validation*, online: https://www.w3.org/2012/12/rdf-val/SOTA (abgerufen am 13. Mai 2020).

[^119]: Ebd.

[^120]: Hitzler u. a., *Semantic Web*, S. 68.

[^121]: Hyvönen, *Publishing and Using Cultural Heritage Linked Data on the Semantic Web*, S. 76.

[^122]: Stuckenschmidt, *Ontologien*, S. 170--171.

[^123]: Amit Singhal, „Introducing the Knowledge Graph. Things, not Strings", online: https://blog.google/products/search/introducing-knowledge-graph-things-not/ (abgerufen am 18. Mai 2020).

[^124]: Martin Heidegger, *Sein und Zeit*, Tübingen ^19^2006, S. 68--72.

[^125]: Ebd., S. 69.

[^126]: Ebd., S. 71--72.

[^127]: Noy/McGuinness, *Ontology Development 101. A Guide to Creating Your First Ontology*.

[^128]: Stuckenschmidt, *Ontologien*.

[^129]: Hyvönen, *Publishing and Using Cultural Heritage Linked Data on the Semantic Web*, S. 87--88.

[^130]: Vgl. auch: Christian Bizer, Richard Cyganiak, Tom Heath, „How to publish Linked Data on the Web", online: http://wifo5-03.informatik.uni-mannheim.de/bizer/pub/LinkedDataTutorial/\#whichvocabs (abgerufen am 20. Mai 2020).: „It is common practice to mix terms from different vocabularies."

[^131]: Letzterer gilt gar als „Erfinder" des Konzepts eines *Semantic Web*.

[^132]: Bizer/Heath/Berners-Lee, „Linked Data - The Story So Far", S. 6.

[^133]: Semantic Web Deployment Working Group, *SKOS Simple Knowledge Organization System*, online: https://www.w3.org/2004/02/skos/ (abgerufen am 23. August 2020).

[^134]: Allemang/Hendler, *Semantic Web for the Working Ontologist*, S. 207.

[^135]: Ebd., S. 213.

[^136]: Gabriel Képéklian, Olivier Curé, Laurent Bihanic, „From the Web of Documents to the Linked Data", in: *Business Intelligence. 4th European Summer School, eBISS 2014, Berlin, Germany, July 6-11, 2014, Tutorial Lectures* (= Lecture Notes in Business Information Processing 205), hrsg. von Esteban Zimányi und Ralf-Detlef Kutsche, Cham u.a. 2015, S. 60--87, hier S. 79--80, DOI: https://doi.org/10.1007/978-3-319-17551-5\_3 (abgerufen am 20. Mai 2020).

[^137]: RDF Core Working Group, *Resource Description Framework (RDF). Concepts and Abstract Data Model*.

[^138]: Bizer/Heath/Berners-Lee, „Linked Data - The Story So Far", S. 7. Die Autoren berufen sich ihrerseits auf Bizer/Cyganiak/Heath, „How to publish Linked Data on the Web".

[^139]: Stuckenschmidt, *Ontologien*, S. 160--161.

[^140]: The W3C Technical Architecture Group, *Associating Ressources with Namespaces.*

[^141]: „Begriffliche Kontrolle", vgl: Bertram, *Einführung in die inhaltliche Erschließung. Grundlagen, Methoden, Instrumente*, S. 128.

[^142]: Ebd.

[^143]: Z. Begriff „Hypertext" siehe etwa: Dennis Niewerth, *Dinge-Nutzer-Netze. Von der Virtualisierung des Musealen zur Musealisierung des Virtuellen* (= Edition Museum 30), Bielefeld und Wetzlar 2018, S. 92--93.

[^144]: In dieser Arbeit wurden vor allem die Texte Allemang/Hendler, *Semantic Web for the Working Ontologist*. sowie Hitzler u. a., *Semantic Web*. zu Rate gezogen.

[^145]: Für eine Auswahl relevanter Vokabulare für den GLAM-Bereich s. Marina Ziku, „Digital Cultural Heritage and Linked Data. Semantically-Informed Conceptualisations and Practices with a Focus on Intangible Cultural Heritage", in: *Liber Q.* 30/1 (2020), S. 1--16, DOI: https://doi.org/http://doi.org/10.18352/lq.10315. Für eine Auswahl musikrelevanter Vokabulare s. Pasquale Lisena u. a., „Controlled Vocabularies for Music Metadata", in: *Proceedings* of the *19th International Society* for *Music Information Retrieval Conference* *ISMIR 2018,* hrsg. v. Emilia Gómez u.a., Paris 2018, 7 ungezählte Seiten; Bicher/Wiermann, „Normdaten zu Werken der Musik"; Terhi Nurmikko-Fuller u. a., „Building Prototypes Aggregating Musicological Datasets on the Semantic Web", in: *Bibl. Forsch. Prax.* 42/2 (2018), S. 206--221, DOI: https://doi.org/10.1515/bfp-2018-0025; Terhi Nurmikko-Fuller u. a., „In Collaboration with In Concert. Reflecting a Digital Library as Linked Data for Performance Ephemera", in: *Proceedings of the 3rd International Workshop on Digital Libraries for Musicology - DLfM 2016*, o. Hrsg., New York 2016, S. 17--24, DOI: https://doi.org/10.1145/2970044.2970049 (abgerufen am 25. Mai 2020); Münnich, „Ontologien in der Praxis. Möglichkeiten und Herausforderungen für die Modellierung musikwissenschaftlicher/musikeditorischer Wissensstrukturen".

[^146]: Basel University Library (Hrsg.), *BARTOC.org. Basel Register of Thesauri, Ontologies & Classifications*, online: https://bartoc.org/ (abgerufen am 28. Juli 2020).

[^147]: Ontology Engineering Group -- UPM (Hrsg.), *Linked Open Vocabularies (LOV)*, online: https://lov.linkeddata.es/dataset/lov/ (abgerufen am 3. Juni 2020).

[^148]: Martin Doerr u. a., *Definition of the CIDOC Conceptual Reference Model* A, 2020, S. 52, online: http://www.cidoc-crm.org/sites/default/files/CIDOC%20CRM\_v6.2.9%2030-4-2020%20.pdf.

[^149]: Carlo Meghini u. a., *Europeana Data Model v5.2.8*, 2017, S. 11, online: https://pro.europeana.eu/files/Europeana\_Professional/Share\_your\_data/Technical\_requirements/EDM\_Documentation//EDM\_Definition\_v5.2.8\_102017.pdf.

[^150]: https://www.wikidata.org/wiki/Property:P175 (abgerufen am 25. Mai 2020).

[^151]: https://schema.org/byArtist (abgerufen am 25. Mai 2020).

[^152]: Pierre Choffé, Raphael Troncy, Pasquale Lisena, „DOREMUS Ontology", in: *GitHub*, online: https://github.com/DOREMUS-ANR/doremus-ontology (abgerufen am 25. Mai 2020).

[^153]: http://data.doremus.org/ontology/\#U54\_is\_performed\_expression\_of (abgerufen am 25. Mai 2020).

[^154]: http://data.doremus.org/ontology/\#U81i\_is\_performer\_status\_of (abgerufen am 25. Mai 2020).

[^155]: Arbeitsstelle für Standardisierung (Hrsg.): *Funktionelle Anforderungen an bibliografische Datensätze*.

[^156]: https://d-nb.info/standards/elementset/gnd\#instrumentalist (abgerufen am 25. Mai 2020).

[^157]: Weitere Ausführungen zum Verständnis des Konzepts „Musikinstrument" in dieser Arbeit folgen in Kapitel 4.2.2.1.

[^158]: Nurmikko-Fuller u. a., „Building Prototypes Aggregating Musicological Datasets on the Semantic Web".

[^159]: http://musicontology.com/specification/\#term-Performance (abgerufen am 25. Mai 2020).

[^160]: http://xmlns.com/foaf/spec/\#term\_Agent (abgerufen am 25. Mai 2020).

[^161]: http://xmlns.com/foaf/spec/\#term\_Person (abgerufen am 25. Mai 2020).

[^162]: RDF Core Working Group, *Resource Description Framework (RDF) Schema Specification 1.0*, online: https://www.w3.org/2001/sw/RDFCore/Schema/20010913/\#s2.3.2 (abgerufen am 25. Mai 2020).

[^163]: Library of Congress (Hrsg.), *Library of Congress Names*, online: http://id.loc.gov/authorities/names.html (abgerufen am 25. Mai 2020).

[^164]: Online Computer Library Center (Hrsg.), *Virtual International Authority File*, online: http://viaf.org/ (abgerufen am 25. Mai 2020).

[^165]: Bertil Hermann van Boer, „Observations on Bach's Use of the Horn. Part I", in: *Bach* 11/2 (1980), S. 21--28, hier S. 22.

[^166]: https://www.wikidata.org/wiki/Q97621186 (abgerufen am 23. Juli 2020).

[^167]: https://www.wikidata.org/wiki/Q97621343 (abgerufen am 23. Juli 2020).

[^168]: http://musicontology.com/specification/\#term-Performance (abgerufen am 26. Mai 2020).

[^169]: http://musicontology.com/specification/\#term-instrument (abgerufen am 26. Mai 2020).

[^170]: Irish Traditional Music Archive (Hrsg.), *Linked Irish Traditional Music Ontology*, online: https://www.itma.ie/litmus/ontology (abgerufen am 26. Mai 2020).

[^171]: https://www.itma.ie/litmus/ontology\#L58\_played\_on\_instrument (abgerufen am 26. Mai 2020).

[^172]: https://www.itma.ie/litmus/ontology\#L58i\_instrument\_played\_by (abgerufen am 26. Mai 2020).

[^173]: RDA Steering Committee (Hrsg.), „6.15.1.1 Scope", in: *RDA-Toolkit*, online: https://access.rdatoolkit.org/ (abgerufen am 2. Juni 2020).

[^174]: Übrigens ein ganz typisches Instrument im sog. *Calypso*.

[^175]: Richard Taruskin, *The Earliest Notations to the Sixtenth Century* (= The Oxford History of Western Music 1), Oxford u.a. 2005, S. 70--71.

[^176]: Manfred Pfister, Art. „Performance/Performativität", in: *Metzler Lexikon Literatur- und Kulturtheorie. Ansätze - Personen - Grundbegriffe*, Stuttgart u.a. ^4^2008, S. 562--564.

[^177]: Nancy Lorimer, Jeremy Nelson, u. a., *Performed Music Ontology*, online: https://github.com/LD4P/PerformedMusicOntology (abgerufen am 2. Juni 2020).

[^178]: Nancy Lorimer, Kirk-Evan Billet, u. a., *Performed Music Ontology*, online: https://wiki.lyrasis.org/display/LD4P/Performed+Music+Ontology (abgerufen am 2. Juni 2020).

[^179]: http://performedmusicontology.org/ontologies/PerformedMusicOntology.html\#MediumOfPerformance (abgerufen am 2. Juni 2020). Deren URI (http://performedmusicontology.org/ontology/MediumOfPerformance) jedoch zu einer „404-Meldung" auflöst (Stand 02. Juni 2020).

[^180]: http://data.doremus.org/ontology/\#M14\_Medium\_Of\_Performance (abgerufen am 2. Juni 2020).

[^181]: Einen guten Einstiegspunkt bietet: Deutsche Nationalbibliothek, „IFLA Library Reference Model (IFLA LRM)", online: https://www.dnb.de/DE/Professionell/Standardisierung/Standards/\_content/ifla\_lrm\_akk.html (abgerufen am 28. August 2020).

[^182]: Jakob Kusnick u. a., „A Timeline Metaphor for Analyzing the Relationships between Musical Instruments and Musical Pieces", in: *Proceedings of the 15th International Joint Conference on Computer Vision, Imaging and Computer Graphics Theory and Applications*, o. Hrsg., Valletta 2020, S. 240--251, DOI: https://doi.org/10.5220/0008990502400251 (abgerufen am 26. Mai 2020).

[^183]: Josef Focht (Hrsg.), *musiXplora*, online: https://home.uni-leipzig.de/mim/about/ (abgerufen am 26. Mai 2020).

[^184]: Kusnick u. a., „A Timeline Metaphor for Analyzing the Relationships between Musical Instruments and Musical Pieces", S. 250.

[^185]: Semantic Web Deployment Working Group, *SKOS Simple Knowledge Organization System Reference*, online: https://www.w3.org/TR/skos-reference/ (abgerufen am 26. Mai 2020).

[^186]: Semantic Web Deployment Working Group, *SKOS Simple Knowledge Organization System Reference*, online: https://www.w3.org/TR/skos-reference/\#mapping (abgerufen am 26. Mai 2020).

[^187]: Musical Instrument Museums Online, *MIMO Thesaurus*, online: http://www.mimo-db.eu/InstrumentsKeywords (abgerufen am 2. Juni 2020).

[^188]: Diese würden naturgemäß in der Regel nicht mit einem Objekt verknüpft. Ausnahmen fänden sich, wie so oft, in der zeitgenössischen Musik: Ob anhand eines Synthesizers eine Stimme verzerrt wird (tatsächlich böte bereits die Verstärkung einer Stimme durch ein Mikrophon als „Instrument" im weitesten Sinne), oder in ein Instrument „hineingesungen" wird, wären auch diese Szenarien darstellbar.

[^189]: International Association of Music Libraries, Archives and Documentation Centres (Hrsg.)/Doing Reusable Music Data, „List of Media of Performances according to IAML".

[^190]: So werden -- dank der Transitivität des Superpropertys -- bei einer SPARQL-Suche zugleich auch Entitäten, die durch dessen Subproperties miteinander verbunden sind, ausgegeben.

[^191]: Dublin Core Metadata Initiative, „DCMI Metadata Terms", online: https://www.dublincore.org/specifications/dublin-core/dcmi-terms/\#relation (abgerufen am 2. Juni 2020).

[^192]: https://www.w3.org/TR/rdf-schema/\#ch\_subpropertyof (abgerufen am 2. Juni 2020).

[^193]: Alistair Miles, Nikki Rogers, Dave Beckett, „SKOS-Core 1.0 Guide", online: https://www.w3.org/2001/sw/Europe/reports/thes/1.0/guide/20040504/\#3.5 (abgerufen am 30. Mai 2020).

[^194]: Ebd.

[^195]: Doerr u. a., *Definition of the CIDOC Conceptual Reference Model*, S. 90.

[^196]: Ebd., S. 2.

[^197]: Ebd., S. 26.

[^198]: Ebd., S. xxvi.

[^199]: Ebd., S. 89. Wobei in dieser Arbeit die Verwendung von `rdfs:subclassOf` zu genügen scheint.

[^200]: Ebd., S. xxvi.

[^201]: Hitzler u. a., *Semantic Web*, S. 149.

[^202]: https://www.w3.org/TR/owl-ref/\#SymmetricProperty-def (abgerufen am 3. Juni 2020).

[^203]: Doerr u. a., *Definition of the CIDOC Conceptual Reference Model*, S. 13--14.

[^204]: https://www.wikidata.org/wiki/Q34379 (abgerufen am 2. Juni 2020).

[^205]: https://www.wikidata.org/wiki/Q6679199 (abgerufen am 2. Juni 2020).

[^206]: Eine grundsätzliche Herausforderung liegt jedoch in dem Umstand, dass -- abgesehen etwa von *MIMO* -- kaum referenzierbare Datensätze für Instrumente im Netz vorhanden sind. So lässt sich zwar etwa mittels SPARQL-Abfrage eine Liste der auf *Wikidata* vorhandenen „Stradivaris" (https://query.wikidata.org/sparql?query=%23%22Stradivaris%22%20in%20Wikidata%0ASELECT%20%3Finstrument%20%3FinstrumentLabel%20%0AWHERE%20%0A%7B%0A%20%20%3Finstrument%20wdt%3AP170%20wd%3AQ182011%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO\_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A%0A)\
    oder von Orgeln (auf 500 beschränkt)\
    (https://query.wikidata.org/sparql?query=%23Orgel%20in%20Wikidata%0ASELECT%20%3Finstrument%20%3FinstrumentLabel%20%0AWHERE%20%0A%7B%0A%20%20%3Finstrument%20%23wdt%3AP170%20%3Fcreator%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP31%20wd%3AQ1444%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO\_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A%0ALimit%20500)\
    generieren, jedoch böte sich das systematische Verzeichnen -- insbesondere von Orgeln -- als möglicher Ansatzpunkt für künftige Erschließungsprojekte an.

[^207]: https://www.w3.org/TR/owl-ref/\#sameAs-def (abgerufen am 2. Juni 2020).

[^208]: Siehe etwa den Twitter-Thread unter dem Hashtag *\#openmasterarbeit* vom 09.--10.06.2020 zu diesem Thema -- dort insb. in Hinsicht auf Werk-Entitäten: *Twitter*, online: https://twitter.com/SPARQLCRMSUPPE/status/1270298014519869440 (abgerufen am 11. Juni 2020).

[^209]: *Twitter*, online: https://twitter.com/MusiCog/status/1270301139293155333 (abgerufen am 11. Juni 2020).

[^210]: *Twitter*, online: https://twitter.com/MusiCog/status/1270696812312236032 (abgerufen am 11. Juni 2020).

[^211]: https://www.wikidata.org/wiki/Property:P4733 (abgerufen am 11. Juni 2020).

[^212]: https://www.wikidata.org/wiki/Property:P51 (abgerufen am 11. Juni 2020).

[^213]: https://www.w3.org/TR/rdf-schema/\#ch\_label (abgerufen am 11. Juni 2020).

[^214]: https://www.w3.org/TR/rdf-schema/\#ch\_comment (abgerufen am 11. Juni 2020).

[^215]: Ebd.

[^216]: Amelie Gyrard, *SemWeb Best Practices for Dummies with PerfectO*, 2017, S. 16--17, online: http://perfectsemanticweb.appspot.com/documentation/SemanticWebBestPracticesForDummies.pdf.

[^217]: https://schema.org/track (abgerufen am 11. Juni 2020).

[^218]: Nuno Freire, Valentine Charles, Antoine Isaac, „Evaluation of Schema.org for Aggregation of Cultural Heritage Metadata", in: *The Semantic Web. 15th International Conference, ESWC 2018, Heraklion, Crete, Greece* (= Lecture Notes in Computer Science 10843)*, June 3--7, 2018. Proceedings*, hrsg. von Aldo Gangemi u. a., Cham 2018, S. 225--239, DOI: https://doi.org/10.1007/978-3-319-93417-4\_15 (abgerufen am 11. Juni 2020) oder Anna Neovesky, Frederic von Vlahovits, „Interconnecting Music Repositories with Semantic Web Technologies. An RDF- and Schema.org-based Approach", in: *Digit. Scholarsh. Humanit.* (2020), DOI: https://doi.org/10.1093/llc/fqaa019.

[^219]: https://schema.org/ (abgerufen am 11. Juni 2020).

[^220]: Sinnvoll wäre es etwa für maschinelle Auswertungen, die Festlegung des Stimmtons ebenfalls als Tripel mit unterschiedlichen Datentypen zu modellieren und mit etablierten Vokabularen -- v.a. aus dem Bereich der Physik/Akustik -- zu verknüpfen.

[^221]: http://d-nb.info/gnd/4122368-8 (abgerufen am 27. Juli 2020).

[^222]: http://www.w3.org/2000/01/rdf-schema\#label (abgerufen am 10. Mai 2020).

[^223]: Wobei dies freilich zunächst ebenfalls ein theoretisches „Klingen" ist.

[^224]: Eine sehr verständliche Einführung zur Transposition in Hornstimmen findet sich in: Kurt Janetzky, Bernhard Brüchle, *Das Horn. Eine kleine Chronik seines Werdens und Wirkens* (= Unsere Musikinstrumente 6), Mainz u.a. 1984, S. 67--72.

[^225]: S. hierzu etwa: Klaus Wogram, *Ein Beitrag zur Ermittlung der Stimmung von Blechblasinstrumenten*, Braunschweig 1972.

[^226]: Alle Noten sind in *MEI/XML* erstellt und mit der *Verovio MEI Viewer* (Répertoire Internationale des Sources Musicales Schweiz, „Verovio MEI Viewer", online: https://www.verovio.org/mei-viewer.xhtml (abgerufen am 27. August 2020)) gerendert.

[^227]: Vgl.: Janetzky/Brüchle, *Das Horn*, S. 69.

[^228]: https://www.wikidata.org/wiki/Q775617 (abgerufen am 26. Juli 2020).

[^229]: Hitzler u. a., *Semantic Web*, S. 51--52.

[^230]: RDF Core Working Group, *RDF Primer*, online: https://www.w3.org/TR/rdf-primer/\#rdfvalue (abgerufen am 26. Juli 2020)., Hitzler u. a., *Semantic Web*, S. 55--56.

[^231]: RDF Working Group, online: https://www.w3.org/TR/rdf-schema/\#ch\_reificationvocab (abgerufen am 27. Juli 2020)., Allemang/Hendler, *Semantic Web for the Working Ontologist*, S. 42--44.

[^232]: https://www.w3.org/TR/rdf-schema/\#ch\_subject (abgerufen am 27. Juli 2020).

[^233]: https://www.w3.org/TR/rdf-schema/\#ch\_predicate (abgerufen am 27. Juli 2020).

[^234]: https://www.w3.org/TR/rdf-schema/\#ch\_object (abgerufen am 27. Juli 2020).

[^235]: https://www.w3.org/TR/rdf-schema/\#ch\_statement (abgerufen am 27. Juli 2020).

[^236]: Hitzler u. a., *Semantic Web*, S. 80.

[^237]: http://data.doremus.org/ontology/\#U28\_has\_ambitus (abgerufen am 27. Juli 2020).

[^238]: https://www.wikidata.org/wiki/Property:P2279 (abgerufen am 27. Juli 2020).

[^239]: „Bereich einer Melodie, einer Stimme oder eines Instruments zwischen tiefster und höchster Note" (Übersetzung: Verf.).

[^240]: https://www.wikidata.org/wiki/Q745780 (abgerufen am 27. Juli 2020).

[^241]: Vgl. etwa: Szeredi u. a., *The Semantic Web Explained*, S. 175--183.

[^242]: Leigh Dodds, Ian Davis, „Label Everything", in: *Linked Data Patterns. A Pattern Catalogue for Modelling, Publishing, and Consuming Linked Data*, 2012, online: https://patterns.dataincubator.org/book/label-everything.html (abgerufen am 11. Juni 2020).

[^243]: https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/domaene

[^244]: Tim Berners-Lee, „Cool URIs Don't Change", online: https://www.w3.org/Provider/Style/URI (abgerufen am 13. August 2020).

[^245]: Die Visualisierung ist als (besser lesbare) Vektorgrafik hier hinterlegt: https://github.com/SPARQLCRMSUPPE/VocsForInstruments/blob/master/namespaces/Visualisierung/20200802\_wumms.svg. Visualisierung mit: Link Vincent u. a., „WebVOWL. Web-based Visualization of Ontologies", online: http://vowl.visualdataweb.org/webvowl.html (abgerufen am 27. August 2020).

[^246]: www.purl.org/wumms

[^247]: Lydia Pintscher u. a., „Strategy for the Wikibase Ecosystem" (2019), online: https://upload.wikimedia.org/wikipedia/commons/c/cc/Strategy\_for\_Wikibase\_Ecosystem.pdf.

[^248]: Shape Expressions Community Group, *Shape Expressions (ShEx) 2.1 Primer*, online: https://shex.io/shex-primer/ (abgerufen am 15. August 2020).

[^249]: RDF Data Shapes Working Group, *Shapes Constraint Language (SHACL)*, online: https://www.w3.org/TR/shacl/ (abgerufen am 15. August 2020).

[^250]: Hier fehlt es noch sehr an verständlichen Anleitungen und Lernmöglichkeiten für Nichtinformatiker.

[^251]: Go Fair International Support and Coordination Office, „FAIR Principles", in: *GO FAIR*, online: https://www.go-fair.org/fair-principles/ (abgerufen am 15. August 2020).

[^252]: Tim Berners-Lee, „Linked Data", online: https://www.w3.org/DesignIssues/LinkedData.html (abgerufen am 27. August 2020).

  [1 Einleitung 3]: #einleitung-1
  [1.1 Vorbemerkungen 7]: #vorbemerkungen-1
  [1.1.1 *Semantic Web*: Konzept 7]: #semantic-web-konzept
  [1.1.2 Terminologie 8]: #terminologie
  [2 Ausgangssituation 11]: #ausgangssituation
  [2.1 Erschließung von Instrumentalbesetzungen -- Beispiel: RISM 11]: #erschließung-von-instrumentalbesetzungen-beispiel-rism
  [2.2 Zielstellung 14]: #zielstellung
  [2.3 Anwendungsbeispiel 16]: #_Toc49465351
  [3 Modellierung mit RDF 18]: #modellierung-mit-rdf
  [3.1 Anwendungsmodellierung 18]: #anwendungsmodellierung
  [3.1.1 Ausführungen zum Anwendungsmodell 20]: #ausführungen-zum-anwendungsmodell
  [3.1.2 „Domäne" 20]: #domäne
  [3.1.3 Mapping 21]: #mapping
  [3.1.4 Anreicherung 21]: #anreicherung
  [3.2 Formalisierte Modellierung 23]: #formalisierte-modellierung
  [*3.2.1* *Entity Relationship Model* 24]: #entity-relationship-model
  [3.2.2 Transformation mit *RDF*, *RDFS* und *OWL* 27]: #transformation-mit-rdf-rdfs-und-owl
  [3.2.2.1 Vorgehensweise 29]: #vorgehensweise
  [3.2.3 Vokabular 30]: #vokabular
  [3.2.3.1 Bemerkungen zum Vokabular 30]: #bemerkungen-zum-vokabular
  [3.2.3.1.1 Namensraum und Benennung 30]: #namensraum-und-benennung
  [3.2.3.1.2 Instanzen (owl:namedIndividuals) und Klassen (owl:class, rdfs:subClassOf) 31]: #instanzen-owlnamedindividuals-und-klassen-owlclass-rdfssubclassof
  [3.2.3.1.3 Identifier 32]: #identifier
  [3.2.3.1.4 Attribute und Properties 33]: #attribute-und-properties
  [3.2.3.1.5 Weitere Anmerkungen 33]: #weitere-anmerkungen
  [3.2.4 Spezifizierung von Relationen mit *rdfs:range* und *rdfs:domain* 33]: #spezifizierung-von-relationen-mit-rdfsrange-und-rdfsdomain
  [3.2.5 Vom Vokabular zur „Lightweight Ontology" 36]: #vom-vokabular-zur-lightweight-ontology
  [*4* Anbindung an- / Integration in das *Semantic Web* 37]: #anbindung-an--integration-in-das-semantic-web
  [4.1 Vorüberlegungen 37]: #vorüberlegungen
  [4.1.1 Hintergrund 37]: #hintergrund
  [4.1.2 Semantische Verknüpfungsmöglichkeiten mit dem *Semantic Web* 38]: #semantische-verknüpfungsmöglichkeiten-mit-dem-semantic-web
  [4.1.2.1 1) Mapping 39]: #mapping-1
  [4.1.2.2 2) Integration von bereits etablierten externen Konzepten 40]: #integration-von-bereits-etablierten-externen-konzepten
  [4.1.3 Vorgehensweise 41]: #vorgehensweise-1
  [4.1.3.1 Terminologische Kontrolle / Modellierung / Methodik 42]: #terminologische-kontrolle-modellierung-methodik
  [4.2 Erfassung und Modellierung mit externen Vokabularen 43]: #erfassung-und-modellierung-mit-externen-vokabularen
  [4.2.1 Interpret und Aufführung 43]: #interpret-und-aufführung
  [4.2.1.1 Interpret und Aufführung -- Relation 44]: #interpret-und-aufführung-relation
  [4.2.1.2 Personennormdaten 46]: #personennormdaten
  [4.2.1.3 Modellierung von Zusammenhängen zwischen Musikinstrumenten, Interpreten und Aufführungen 46]: #modellierung-von-zusammenhängen-zwischen-musikinstrumenten-interpreten-und-aufführungen
  [4.2.2 Mapping und Klassifikation 48]: #mapping-und-klassifikation
  [4.2.2.1 „Medium of Performance" 48]: #medium-of-performance
  [4.2.2.2 Herausforderungen 51]: #herausforderungen
  [4.2.2.3 Mapping 52]: #mapping-2
  [4.2.2.3.1 Szenario 1: Mapping über Klassifikation 52]: #szenario-1-mapping-über-klassifikation
  [4.2.2.3.1.1 Klassifikation 53]: #klassifikation
  [4.2.2.3.2 Szenario 2: direktes Mapping 53]: #szenario-2-direktes-mapping
  [4.2.2.3.3 Erkenntnisse aus der Modellierung 57]: #erkenntnisse-aus-der-modellierung
  [4.2.3 Klangbeispiel 57]: #klangbeispiel
  [4.3 Erfassung des Komplexes „Stimmungen" 61]: #erfassung-des-komplexes-stimmungen
  [4.3.1 Problemstellung 61]: #problemstellung
  [4.3.2 Stimmton 62]: #stimmton
  [4.3.3 Stimmungssystem 62]: #stimmungssystem
  [4.3.4 Stimmung 63]: #stimmung
  [4.3.5 Töne 65]: #töne
  [4.3.5.1 Ton als Abstraktum 65]: #ton-als-abstraktum
  [4.3.5.2 Ton als normativ fixiertes Zeichen 66]: #ton-als-normativ-fixiertes-zeichen
  [4.3.5.2.1 Taxonomie 66]: #taxonomie
  [4.3.5.2.2 Stimmton 67]: #stimmton-1
  [4.3.5.3 Ton als physikalisches Phänomen 68]: #ton-als-physikalisches-phänomen
  [4.3.5.3.1 Modellierung Stimmhöhe / Referenzton 68]: #modellierung-stimmhöhe-referenzton
  [4.3.5.4 Tonraum (Ambitus) 69]: #tonraum-ambitus
  [4.3.5.5 Inferenzmöglichkeiten 70]: #inferenzmöglichkeiten
  [4.4 Technische Nachbereitung / The Rise of wumms: 71]: #technische-nachbereitung-the-rise-of-wumms
  [5 Schluss 73]: #schluss-1
  [5.1 Anwendungssimulation 73]: #anwendungssimulation
  [5.1.1 Modellierung 73]: #modellierung
  [5.2 Fazit 77]: #fazit-1
  [6 Verwendete Literatur 80]: #verwendete-literatur
  [6.1 Externes Bildmaterial 89]: #externes-bildmaterial
  [Besetzung1]: media/image1.png {width="5.833333333333333in" height="1.1505369641294838in"}
  [Besetzung2]: media/image2.png {width="5.833333333333333in" height="1.975805993000875in"}
  [Ein Bild, das Text enthält. Automatisch generierte Beschreibung]: media/image3.png {width="6.361206255468066in" height="3.6222222222222222in"}
  [Ein Bild, das Text, Karte enthält. Automatisch generierte Beschreibung]: media/image4.png {width="6.958333333333333in" height="5.219120734908136in"}
  [Datenmodell -- Beziehungen ausgedrückt als Verbindungslinien zwischen den umkreisten Entitäten]: media/image5.png {width="6.692308617672791in" height="6.076923665791776in"}
  [Entity Relationship Modell: farbige Markierung externer Entitäten. Entitäten sind in Rechtecken, Eigenschaften in Ovalen, Beziehungen in Rauten eingefasst. Schlüsseleigenschaften sind durch Unterstreichung gekennzeichnet.]: media/image6.png {width="8.009027777777778in" height="7.594086832895888in"}
  [1]: media/image7.png {width="5.842592957130359in" height="3.6203696412948383in"}
  [2]: media/image8.png {width="2.9298654855643043in" height="2.3194444444444446in"}
  [blablablub -- fett markiert: übergeordnete Klassen und deren Beziehungen zueinander]: media/image9.png {width="6.288888888888889in" height="3.088888888888889in"}
  [blablablub -- fett umrandet: Klassen, dünn umrundet: Instanzen]: media/image10.png {width="5.811111111111111in" height="4.222222222222222in"}
  [3]: media/image11.png {width="6.531944444444444in" height="0.7881944444444444in"}
  [4]: media/image12.png {width="0.5388888888888889in" height="0.38125in"}
  [5]: media/image13.png {width="2.832638888888889in" height="2.6527777777777777in"}
  [6]: media/image14.png {width="3.5416666666666665in" height="2.8472222222222223in"}
  [Ein Bild, das Tisch, Luft, haltend, fliegend enthält. Automatisch generierte Beschreibung]: media/image15.png {width="7.196027996500438in" height="7.111111111111111in"}
