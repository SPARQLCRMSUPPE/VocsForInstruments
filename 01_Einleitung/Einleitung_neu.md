# Einleitung

Ziel dieser Arbeit ist es, einen Ansatz für ein semantisches Framework zu entwickeln, das seine Anwender in die Lage versetzt, musikinstrumentenbezogene Ressourcen aus Einrichtungen unterschiedlicher Sparten des Kulturerbes zueinander in Beziehung zu setzen, zu verbinden und dabei zugleich – mittelbar – bereits vorhandenes Vokabular um wichtige Aspekte anreichert. 

Musikinstrumente sind schwer zu fassende Phänomene, deren "Wesen" situativ und je nach Blickwinkel[^8] sehr unterschiedlich – etwa materiell, immateriell, medial oder performativ – sich ergeben kann.[^2] Hinzu kommt, dass sie mit ihrem Bezugspunkt "Musik" (zumeist primär) in Abhängigkeit zu einem gleichermaßen immateriellen, hochgradig ambivalenten und damit für Kulturerbeinstitutionen ohnehin außerordentlich schwierig fassbaren Gegenstand stehen.[^1] Trotzdem spielen Musikinstrumente in verschiedenen solcher Einrichtungen eine Rolle – sei es als Museumsobjekt, als Besetzungsangabe einer Quelle, als Instrument in einer Aufnahme oder als Term in einem Vokabular etc. 

Es liegt dabei auf der Hand, dass sich das Konzept "Musikinstrument" eingedenk seines eingangs beschriebenen, sparten- oder gar institutionsspezifischen Blickwinkels unterscheiden muss: Eine "Objekt-zentrierte Herangehensweise" wird womöglich ganz andere Aspekte jenes Konzepts hervorheben – etwa physische oder ereignisbezogene – als eine bibliographische.[^6] Und so mag es denn auch nicht verwundern, wenn konzeptuelle Modelle und Vokabulare verschiedener Kulturerbesparten – etwa Museen, Archive, Bibliotheken etc. – mitunter nicht unmittelbar miteinander kompatibel sind.

Dabei bärge vor dem Hintergrund eines digitalisierten *GLAM*-Bereichs[^5] eine Vernetzung von Beständen, dessen Prämisse jene Kompatibilität bildet, bekanntermaßen einiges an Potential: So könnten etwa Bestandsmetadaten durch Kontextualisierung nach außen zusätzlich in Wert gesetzt werden, die Übernahme von Fremddaten zur Anreicherung eigener Datensätze erleichtert werden,[^3] neue – womöglich bestandsübergreifende – Suchmöglichkeiten und -Einstiege für den Nutzer geschaffen[^7] und Bestände virtuell zusammengeführt und sichtbarer werden.[^4] Für Forscher, etwa Editionswissenschaftler oder Digital Humanists, ergibt sich neben der Nutzung und Auswertung von hochwertigen Metadaten die Möglichkeit, eigene Forschungsdaten in diesem Austausch beizutragen. Die Aktualität und Relevanz dieses Anliegens im geisteswissenschaftlichen Bereich zeigt sich dabei etwa darin, dass mit den Projekten GND4C[^266] sowie im NFDI4Culture-Konsortium (insb. "Task Area 2")[^267] gleich zwei Projekte von nationaler Größenordnung die Vernetzung und Standardisierung im Kulturerbebereich angehen.

Ein weiteres zentrales Problem im Zusammenhang mit musikalischen Quellen besteht zudem darin, dass vorhandene, meist generische Vokabulare im Bereich der Musikinstrumente mithin starke Defizite (Konsistenz, Detailtiefe, Präzision) aufweisen. Die Möglichkeit, diese um wichtige Konzepte zu ergänzen, erscheint daher ebenfalls außerordentlich fruchtbar. Der praktische Nutzen einer solchen Möglichkeit wurde im Vorfeld dieser Arbeit in zahlreichen persönlichen Gesprächen mit Vertretern verschiedener Sparten sowie Forschenden verifiziert.

So ergeben sich zwei Hauptanliegen für diese Arbeit:

1) die Möglichkeit einer Vernetzung von musikinstrumentenbezogenen Daten verschiedener Sparten zu erproben.
2) auszuloten, in welcher Weise eine Anreicherung der vorhandenen Vokabulare möglich ist.

Einen technischen Lösungsansatz hierfür halten die sog. "Semantic Web-Technologien"[^265] bereit, indem sie es ermöglichen, Daten auch unabhängig von ihrem ursprünglichen Kontext miteinander in Beziehung zu setzen und interoperabel zu machen. Dank des ihnen zugrundeliegenden *RDF*-Modells (*Research Description Framework*) ist es bei Nutzung verschiedener etablierter Technologien des Internets möglich, im Netz gespeicherte Daten in semantische Beziehungen der Form 

*Subjekt – Prädikat – Objekt*

zueinander zu setzen und maschinenlesbar zu machen. Aus der Gesamtheit der an dieses semantische Netz angeschlossenen Daten, dem *Linked Data Cloud* lässt sich so ein eigenes anwendungsbezogenes Vokabular, ein sog. *Metadatenprofil*[^264] erzeugen, das imstande ist, als Schema für Vernetzung und Anreicherung musikinstrumentenbezogener Metadaten herzuhalten. Es könnte dabei als gedankliche Vorarbeit für eine anschließende Weiterentwicklung und Ausarbeitung durch eine Fachcommunity fungieren.

[weiterentwickelbar – nicht abgeschlossen]

---

In methodischer Hinsicht ist die Entwicklung eines solchen Profils jedoch mit einigen Herausforderungen verbunden:

In RDF strukturierte Vokabulare liegen gewöhnlich "als Endprodukt" vor – Rückschlüsse auf die Modalitäten ihrer Genese (und somit methodische Ansätze für die Entwicklung eigener) bleiben dem Betrachter in der Regel somit verwehrt. Zudem ist der Vorgang der Modellierung stark prozessual und mitunter zirkulär geprägt, was das Gießen dieses Prozesses in die chronologische Form wissenschaftlicher Stringenz in Form einer wissenschaftlichen Fixierung sehr erschwert. (Da nicht jede Iteration dieser Genese umfassend im Rahmen der verschriftlichten Variante dieser Arbeit nachgezeichnet werden kann, wurde im *GitHub*-Repositorium dieser Arbeit[^269] jeder Schritt dokumentiert und offen nachvollziehbar gemacht.)

Eine zusätzliche Herausforderung liegt in den auszuwertenden Quellen selbst begründet: Die Quellen, aus deren Termen sich das Metadatenprofil zusammensetzen könnte, umfasst potentiell die Gesamtheit der im Semantic Web enthaltenen. Eine philologische Auswertung ist daher schlichtweg unmöglich, und es werden im Laufe der Arbeit alternative heuristische Lösungen gefunden werden müssen. 
Umso schwerer wiegt es da, dass es an einführender Literatur, die imstande wäre – insbesondere Nicht-Informatikern –, einen Kompass im Prozess des Modellierens und Publizierens von Linked Data an die Hand zu geben, mangelt.[^268] 

Diese besonderen Rahmenbedingungen machen es erforderlich, dass sich die Arbeit in großen Teilen deduktiv vorantastet, wobei die Methodik anlassbezogen anhand der in der Praxis vorgefundenen jeweiligen Problemstellung zu entwickeln sein wird, so dass der methodische Faden im Laufe der Arbeit immer wieder aufzunehmen zu sein wird.

Eine weitere methodische Besonderheit, die gewissermaßen bereits im Wesen des Semantic Webs begründet liegt, ergibt sich aus der ihm eigenen sonderbaren Verschmolzenheit von Konzepten intellektueller Wissensrepräsentation und der technischen Umstände ihrer digitalen Manifestation, was eine losgelöste Betrachtung eines einzelnen dieser beiden Bestandteile nachgerade unmöglich macht. Dennoch erscheint es angesichts des hier behandelten konkreten Anwendungsfalls sinnvoll, im Folgenden einen gewissen inhaltlichen Schwerpunkt auf die intellektuelle Modellierung zu legen und technische Belange, wo immer möglich, auszuklammern.

Metadatenstandards werden nicht im Rahmen von studentischen Qualifikationsarbeiten verfasst, sondern entstehen etwa als wandelbare Ergebnisse langwieriger diskursiver, Community-getriebener Prozesse.[^270] Das Ergebnis dieser Arbeit besteht daher keineswegs im Fertigstellen einer umfassenden Ontologie der Musikinstrumente, ihrer Eigenschaften und ihrer ontologischen Beziehungen in der Welt. Vielmehr liegt ihr Sinn insbesondere darin, einige Vorüberlegungen für eine potentielle anschließende Entwicklung eines ausdrucksstärkeren Vokabulars vorwegzunehmen, dabei gangbare methodische Wege zu kartieren und zuletzt einige – wenige – konkrete inhaltliche musikwissenschaftliche Vorarbeiten vorauszuschicken – welche insbesondere aber zur Illustration und zu Verifikationszwecken für die Stimmigkeit des Arbeitsansatzes bestimmt sind.

## Vorbemerkungen

### Semantic Web: Konzept

Eine erschöpfende Einführung in die paradoxerweise teils nachgerade banalen wie zugleich hermetisch komplexen Konzepte und Technologien des *Semantic Web* kann an dieser Stelle nicht erfolgen, sondern sie darf sich vielmehr auf einige für das Verständnis der folgenden Arbeit wesentliche Punkte beschränken.

Das *W3C* erklärt die Grundidee des *Semantic Webs* folgendermaßen: "The Semantic Web provides a common framework that allows data to be shared and reused across application, enterprise, and community boundaries."[^a28] Dabei wird das Grundprinzip des Internet – verschiedene mittels *HTML*-Links miteinander *vernetzter* Seiten –, dem *Web of Documents*[^a29], auf den Inhalt dieser Seiten übertragen und erweitert. Leider ist das *Web of Documents* lediglich ein "[...] set of interlinked documents with heterogeneous syntax and semantics and uncontrolled content[...]":[^a31] dessen Inhalt ist also leider nicht einheitlich und somit nicht interoperabel.[^a30] Im *Web of Data*[^a35] hingegen können auch die Inhalte einer Seite (also "Data" innerhalb eines "Documents") dank einer standardiserten "Syntax", dem in #kapitel bereits erwähnten sog. *Ressource Description Framework* (RDF),[^a32] in vielfältige Beziehung zum Inhalt anderer Seiten gesetzt und mit passenden Informationen wiederum innerhalb dieser verlinkt werden. Durch die Charakterisierung der Beziehungen dieser Daten zueinander ergeben sich so mithilfe von RDF Aussagen, sog. "Tripel", mit semantischem Gehalt in der Form 

*Subjekt* - *Prädikat* - *Objekt*.[^a36] 

Die vormals auf die recht banale Beziehung 

*Seite A* - *verlinkt auf* - *Seite B* 

beschränkte  Aussagekraft von HTML wird um komplexe Aussagemöglichkeiten erweitert, die kreuz und quer durch das Netz Aussagen jeder Art über "Dinge" jeder Art zu treffen imstande sind. Dabei können die "Kanten" dieser Aussagen sowohl Subjekt oder Objekt neuer Aussagen werden. 
Dank der Verwendung von RDF und bereits etablierter Webinfrastruktur und -Standards sind Semantic Web-konform strukturierte und publizierte Daten als *Linked Data* maschinenlesbar und interoperabel und können in beliebige Beziehungen gesetzt werden.


### Terminologie

Im Kontext des Semantic Web begegnet eine Vielzahl sehr schwammiger Begriffe, die zugleich außerordentlich inkonsistent Verwendung finden. Wenngleich an dieser Stelle für einige ausführlicheren terminologischen Untersuchungen auf @alma9913393902586 verwiesen werden kann, ist es an dieser Stelle dennoch sinnvoll, nochmals kurz auf einige der in dieser Arbeit verwendeten Begriffe einzugehen.

* Der syntaktische Kontext der Elemente *Subjekt*, *Prädikat*, *Objekt* ergibt einen gerichteten Graphen. Der Oberbegriff für die einzelnen, nun kontextuell losgelöst gedachten Elemente lautet in dieser Arbeit gemäß Stuckenschmidt *Konzepte*.[^271] 
* Die "Kanten" des Graphen, die also je nach Kontext *Subjekt* oder *Objekt* sein können, heißen im Folgenden *Entitäten*, wobei diese *Entitäten* sowohl "Dinge", als auch "Mengen von Dingen" sein können.[^272] 
* Etwas weniger einheitlich wird mit dem Element *Prädikat* verfahren: er wird, je nach Kontext, als *Property* oder *Relation* bezeichnet.
* Kaum ein anderer Begriff ist in derartige Ambivalenz gehüllt, wie der Begriff "Ontologie", sodass eine Definition für diese Arbeit höchstens näherungsweise – übrigens auch in der Fachliteratur gelebte Praxis –[^275] erfolgen kann. Dies gilt nicht lediglich für den Umstand, dass er als "Lehnwort" aus der Philosophie in verschiedenen Disziplinen unterschiedliche Verwendung findet,[^280] vielmehr herrscht auch in der Informatik selbst kein wirklicher Konsens über seinen Inhalt.[^281]
Über das Begriffspaar *Ontologie* und *Vokabular* schreibt das *W3C* (*World Wide Web Consortium*): "[...] ontologies and vocabularies within the Semantic Web can be regarded as synonymous, although ontologies may denote more complex conceptualisations (W3C, 2015)."[^273] Diese Arbeit verfährt wiederum etwas anders, indem sie diese prinzipielle Synonymität aufhebt und die Begriffe anhand Funktion und Struktur qualitativ unterscheidet: Demnach handelt es sich beim Begriff *Vokabular* um "[...]die Verzeichnung aller (allgemeinen oder fachspezifischen) Benennungen zur Nutzung als Wissensordnung [...]."[^274] Ihre Funktion besteht im Augenblick ihrer Nutzung darin, kontrolliertes Vokabular vorzuhalten. Für diese spezielle Nutzung kann nach Auffassung dieser Arbeit eine Ontologie mitunter ebenfalls verwendet werden. Charakteristika von Ontologien gegenüber anderen Systemen der Wissensorganisation sind in dieser Arbeit aber viel eher die folgenden Aspekte: Zumeist wird – sofern es um Ontologien im Semantic Web-Kontext geht – die formalisierte Sprachlichkeit und Maschinenlesbarkeit[^277] bzw. die Möglichkeit automatisches Schlussfolgern ("Reasoning") zu vollziehen, erwähnt.[^279] Bertram unterstreicht zudem ihre Vieldimensionalität und inhärente größtmögliche Flexibilität als Ordnungssystem in Bezug auf Beziehungsmöglichkeiten[^276] und zuletzt impliziert die Existenz einer "light"-Variante, der sog. *lightweight ontology*[^278] (s. #kapitel) ein hohes Maß an Komplexität.
* Die Bezeichnung *Metadatenprofil* (auch "Anwendungsprofil", "Applikationsprofil") impliziert – ähnlich wie im Falle von "Vokabular" – insbesondere eine funktionale Qualität für eine bestimmte Anwendung. Es handelt sich beim *Metadatenprofil* um ein Metadatenschema,[^283] in dem typischerweise Elemente von bereits exisitierenden Modellen und Standards kombiniert und so ein für einen bestimmten Anwendungsfall optimiertes Metadatenschema geschaffen wird.[^282] Dabei ist jedoch noch nichts über seine Struktur gesagt – so ist etwa das in dieser Arbeit zu erarbeitende Profil eine *lightweight ontology* (s. #kapitel).





*  
*    "a schema consisting of data elements drawn from one or more standardized schemes, op- timized for a particular application domain, whereas its focus is on the reuse of existing, standardized model elements."




[^1]: [@van_der_meer_instrumentenkunde_nodate.]
[^2]: [@Musicalinstrument.]
[^3]: [@hyvonen_publishing_2012, S. 7–8.]
[^4]: [@gobel_gnd_2017, S.2.]
[^5]: Akronym blabla
[^6]: [@tomasi_modellieren_2018, S. 175.]
[^7]: Eine sehr umfassende Auseinandersetzung mit Chancen für Einrichtungen und Nutzer findet sich in: @waibel_think_2009.
[^8]: Eine phänomenologisch fundierte Thematisierung der Beziehung zwischen Wahrnehmungssubjekt und Musikinstrument findet sich in: [@de_souza_music_2017, S. 20–23.]

[^264]: [@alma99244375602586]
[^265]: [@noauthor_semantic_nodate.]

[^266]: [@gobel_gnd_2017.]
[^267]: [@altenhoner_nfdi4culture_2020.]
[^268]: Einführende Werke zum Semantic Web und einzelner Vokabulare finden sich in @allemang_semantic_2011, @TN_libero_mab21631588, sowie @noy_ontology_nodate zur Modellierung von Ontologien. @hyvonen_publishing_2012 beinhaltet zudem gute Hinweise für die Publikation von Linked Data in Kulturerbeeinrichtungen.
[^269]: [@sparqlcrmsuppe_sparqlcrmsuppevocsforinstruments_2020.]
[^270]: So bspw. die Prozesse zur Standardbildung des *W3C*, vgl.: @noauthor_world_nodate.
[^271]: [@alma9913393902586, S. 10.]
[^272]: [@fischer_lexikon_2008, S. 275.]
[^273]: Zit. nach: @ziku_digital_2020, S. 5. Ziku zitiert ihrerseits: [@noauthor_ontologies_nodate-1.]
[^274]: [@stock_wissensreprasentation_2008, S. 188.] Stock spricht von "Nomenklaturen" statt "Vokabularen".
[^275]: Diese außerordentliche Ambivalenz des Begriffes wird eindrücklich durch den Umstand illustriert, dass Stuckenschmidt ebenfalls eine endgültige Definition vermeidet (immerhin lautet der Titel "Ontologien : Konzepte, Technologien und Anwendungen").


[^276]: [@TN_libero_mab213864266, S. 261.]
[^277]: [@busse_was_2014, S. 289.]
[^278]: [@article, S. 1.]
[^279]: [@stock_wissensreprasentation_2008, S. 257.]
[^280]: Sehr Interessant ist in diesem Zusammenhang der Artikel [@busse_was_2014-2], in dem eine interdisziplinäre Annäherung an den Begriff erfolgt.

[^a28]: [@noauthor_w3c_nodate.]

[^a29]: 

[^a30]: PDF, HTML, Video

[^a31]: [@szeredi_lukácsy_benkő_nagy_2014, S. 21.]

[^a32]: 

[^a34]: [@madoc34762, S. 2.]

[^a35]: 

[^a36]: Das Verhältnis zwischen der *Wikipedia* und *Wikidata* mag an dieser Stelle zur Verdeutlichung hilfreich sein: …

[^a37]: [@noauthor_why_nodate.]

[^281]: Vgl.: [@alma9913393902586, S. 22–24.]
[^282]: [@cs79, S. 25.]
[^283]: "A metadata schema is simply a set of elements with a precise semantic definition, optionally connected by some structure." Vgl.: [@cs79, S. 8.]