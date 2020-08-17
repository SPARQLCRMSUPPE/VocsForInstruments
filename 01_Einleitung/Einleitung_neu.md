# Einleitung

Ziel dieser Arbeit ist es, einen Ansatz für ein semantisches Framework zu entwickeln, das seine Anwender in die Lage versetzt, musikinstrumentenbezogene Ressourcen aus Einrichtungen unterschiedlicher Sparten des Kulturerbes zueinander in Beziehung zu setzen, zu verbinden und dabei zugleich – mittelbar – bereits vorhandenes Vokabular um wichtige Aspekte anzureichern. 

Musikinstrumente sind schwer zu fassende Phänomene, deren "Wesen" situativ und je nach Blickwinkel[^e8] sehr unterschiedlich – etwa materiell, immateriell, medial oder performativ – sich ergeben kann.[^e2] Hinzu kommt, dass sie mit ihrem Bezugspunkt "Musik" (zumeist primär) in Abhängigkeit zu einem gleichermaßen immateriellen, hochgradig ambivalenten und damit für Kulturerbeinstitutionen ohnehin außerordentlich schwierig fassbaren Gegenstand stehen.[^e1] Trotzdem spielen Musikinstrumente in verschiedenen solcher Einrichtungen eine Rolle – sei es als Museumsobjekt, als Besetzungsangabe einer Quelle, als Instrument in einer Aufnahme oder als Term in einem Vokabular etc. 

Es liegt dabei auf der Hand, dass sich das Konzept "Musikinstrument" eingedenk seines eingangs beschriebenen, sparten- oder gar institutionsspezifischen Blickwinkels unterscheiden muss: Eine "Objekt-zentrierte Herangehensweise" wird womöglich ganz andere Aspekte jenes Konzepts hervorheben – etwa physische oder ereignisbezogene – als eine bibliographische.[^e6] Und so mag es denn auch nicht verwundern, wenn konzeptuelle Modelle und Vokabulare verschiedener Kulturerbesparten – etwa Museen, Archive, Bibliotheken etc. – mitunter nicht unmittelbar miteinander kompatibel sind.

Dabei bärge vor dem Hintergrund eines digitalisierten *GLAM*-Bereichs[^e5] eine Vernetzung von Beständen, dessen Prämisse jene Kompatibilität bildet, bekanntlich einiges an Potential: So könnten etwa Bestandsmetadaten durch Kontextualisierung nach außen zusätzlich in Wert gesetzt werden, die Übernahme von Fremddaten zur Anreicherung eigener Datensätze erleichtert werden,[^e3] neue – womöglich bestandsübergreifende – Suchmöglichkeiten und -Einstiege für den Nutzer geschaffen[^e7] und Bestände virtuell zusammengeführt und sichtbarer werden.[^e4] Für Forscher, etwa Editionswissenschaftler oder Digital Humanists, ergibt sich neben der Nutzung und Auswertung von hochwertigen Metadaten die Möglichkeit, eigene Forschungsdaten in diesem Austausch beizutragen. Die Aktualität und Relevanz dieses Anliegens im geisteswissenschaftlichen Bereich zeigt sich dabei etwa darin, dass mit den Projekten GND4C[^e266] sowie im NFDI4Culture-Konsortium (insb. "Task Area 2")[^e267] gleich zwei Projekte von nationaler Größenordnung die Vernetzung und Standardisierung im Kulturerbebereich angehen.

Ein weiteres zentrales Problem im Zusammenhang mit musikalischen Quellen besteht zudem darin, dass vorhandene, meist generische Vokabulare im Bereich der Musikinstrumente mithin starke Defizite (Konsistenz, Detailtiefe, Präzision) aufweisen. Eine Möglichkeit, diese – möglichst einfach – um wichtige Konzepte zu ergänzen, erscheint daher ebenfalls außerordentlich fruchtbar. Der praktische Nutzen einer solchen Möglichkeit wurde im Vorfeld dieser Arbeit in zahlreichen persönlichen Gesprächen mit Vertretern verschiedener Sparten sowie Forschenden verifiziert. Dabei findet sich so manche kleinere Institution und Forschung oftmals vor die Herausforderung gestellt, dass sie, oftmals durchaus spezielle, Bedürfnisse bei Erschließung oder Publikation ihrer Forschung haben, die Teilhabe an der Entwicklung von Standardvokabular ihnen jedoch verwehrt ist. Für diese ist es wichtig, Möglichkeiten zu finden, diese Teilhabe dennoch niederschwellig zu ermöglichen.

So ergeben sich drei Hauptanliegen für diese Arbeit:

1) die Möglichkeit einer Vernetzung von musikinstrumentenbezogenen Daten verschiedener Sparten zu erproben.
2) auszuloten, in welcher Weise eine Anreicherung der vorhandenen Vokabulare möglich ist.
3) ein Gelingen wäre ein Indikator für die Möglichkeit, fehlendes kontrolliertes Vokabular niederschwellig selbst – also von kleineren Einrichtungen und Forschern – anlegen zu können.

Technisch kann dies durch die sog. "Semantic Web-Technologien"[^e265] ermöglicht werden. Dank des ihnen zugrundeliegenden *RDF*-Modells (*Research Description Framework*) ist es bei Nutzung verschiedener etablierter Technologien des Internets möglich, im Netz gespeicherte Daten in semantische Beziehungen zueinander zu setzen und dabei interoperabel und maschinenlesbar zu machen. Aus der Gesamtheit der an dieses semantische Netz angeschlossenen Daten, dem *Linked Data Cloud*, lässt sich so ein eigenes anwendungsbezogenes Schema, ein sog. *Metadatenprofil*[^e264] erzeugen, das imstande ist, als Schema für Vernetzung und Anreicherung musikinstrumentenbezogener Metadaten herzuhalten. Es könnte dabei als gedankliche Vorarbeit für eine anschließende Weiterentwicklung und Ausarbeitung durch eine Fachcommunity fungieren. Dank der semantischen und technischen Offenheit des sog. *Semantic Web* ist dabei terminologische Anschlussfähigkeit und die Darstellung sehr spezifischer Sachverhale möglich.

---

In methodischer Hinsicht ist die Entwicklung eines solchen Profils jedoch mit einigen Herausforderungen verbunden:

Nach dem RDF strukturierte Vokabulare liegen gewöhnlich "als Endprodukt" vor – Rückschlüsse auf die Modalitäten ihrer Genese (und somit methodische Ansätze für die Entwicklung eigener) bleiben dem Betrachter in der Regel somit verwehrt. Zudem ist der Vorgang der Modellierung stark prozessual und mitunter zirkulär geprägt, was das Gießen dieses Prozesses in die chronologische Form wissenschaftlicher Stringenz in Form einer schriftlichen wissenschaftlichen Fixierung sehr erschwert. (Da nicht jede Iteration dieser Genese umfassend im Rahmen der verschriftlichten Variante dieser Arbeit nachgezeichnet werden kann, wurde im *GitHub*-Repositorium dieser Arbeit[^e269] jeder Schritt dokumentiert und offen nachvollziehbar gemacht.)

Eine zusätzliche Herausforderung liegt in den auszuwertenden Quellen selbst begründet: Die Quellen, aus deren Termen sich das Metadatenprofil zusammensetzen könnte, umfasst potentiell die Gesamtheit der im Semantic Web enthaltenen. Eine philologische Auswertung ist daher schlichtweg unmöglich, und es werden im Laufe der Arbeit alternative heuristische Lösungen gefunden werden müssen. 
Umso schwerer wiegt es da, dass es an einführender Literatur, die imstande wäre – insbesondere Nicht-Informatikern –, einen Kompass im Prozess des Modellierens und Publizierens von Linked Data an die Hand zu geben, mangelt.[^e268] 

Diese besonderen Rahmenbedingungen machen es erforderlich, dass sich die Arbeit in großen Teilen deduktiv vorantastet, wobei die Methodik anlassbezogen anhand der in der Praxis vorgefundenen jeweiligen Problemstellung zu entwickeln sein wird, so dass der methodische Faden im Laufe der Arbeit immer wieder aufzunehmen zu sein wird.

[es ist ja theoretisch unbegrenzt anschlussfähig – das endgültige Modell hat Situationen, die ins Leere laufen (z.B. Instrument nicht mit Ereignis verknüpft etc.)]

Eine weitere methodische Besonderheit, die gewissermaßen bereits im Wesen des Semantic Webs begründet liegt, ergibt sich aus der ihm eigenen sonderbaren Verschmolzenheit von Konzepten intellektueller Wissensrepräsentation und der technischen Umstände ihrer digitalen Manifestation, was eine losgelöste Betrachtung eines einzelnen dieser beiden Bestandteile nachgerade unmöglich macht. Dennoch erscheint es angesichts des hier behandelten konkreten Anwendungsfalls sinnvoll, im Folgenden einen gewissen inhaltlichen Schwerpunkt auf die intellektuelle Modellierung zu legen und technische Belange, wo immer möglich, auszuklammern.

Metadatenstandards werden nicht im Rahmen von studentischen Qualifikationsarbeiten verfasst, sondern entstehen etwa als wandelbare Ergebnisse langwieriger diskursiver, Community-getriebener Prozesse.[^e270] Das Ergebnis dieser Arbeit besteht daher keineswegs im Fertigstellen einer umfassenden Ontologie der Musikinstrumente, ihrer Eigenschaften und ihrer ontologischen Beziehungen in der Welt. Vielmehr liegt ihr Sinn insbesondere darin, einige Vorüberlegungen für eine potentielle anschließende Entwicklung eines ausdrucksstärkeren Vokabulars vorwegzunehmen, dabei gangbare methodische Wege zu kartieren und zuletzt einige – wenige – konkrete inhaltliche musikwissenschaftliche Vorarbeiten vorauszuschicken – welche insbesondere aber zur Illustration und zu Verifikationszwecken für die Stimmigkeit des Arbeitsansatzes bestimmt sind.

## Vorbemerkungen

### Semantic Web: Konzept

Eine erschöpfende Einführung in die paradoxerweise teils nachgerade banalen wie zugleich hermetisch komplexen Konzepte und Technologien des *Semantic Web* kann an dieser Stelle nicht erfolgen, sondern sie darf sich vielmehr auf einige für das Verständnis der folgenden Arbeit wesentliche Punkte beschränken.

Das *W3C* erklärt die Grundidee des *Semantic Webs* folgendermaßen: "The Semantic Web provides a common framework that allows data to be shared and reused across application, enterprise, and community boundaries."[^ea28] Dabei wird das Grundprinzip des Internet – verschiedene mittels *HTML*-Links miteinander *vernetzter* Seiten –, dem *Web of Documents*[^ea29], auf den Inhalt dieser Seiten übertragen und erweitert. Leider ist das *Web of Documents* lediglich ein "[...] set of interlinked documents with heterogeneous syntax and semantics and uncontrolled content[...]":[^ea31] dessen Inhalt ist also leider nicht einheitlich und somit nicht interoperabel.[^ea30] Im *Web of Data*[^ea35] hingegen können auch die Inhalte einer Seite (also "Data" innerhalb eines "Documents") dank einer standardiserten "Syntax", dem in #kapitel bereits erwähnten sog. *Ressource Description Framework* (RDF),[^ea32] in vielfältige Beziehung zum Inhalt anderer Seiten gesetzt und mit passenden Informationen wiederum innerhalb dieser verlinkt werden. Durch die Charakterisierung der Beziehungen dieser Daten zueinander ergeben sich so mithilfe von RDF Aussagen, sog. "Tripel", mit semantischem Gehalt in der Form 

*Subjekt* - *Prädikat* - *Objekt*.[^ea36] 

Die vormals auf die recht banale Beziehung 

*Seite A* - *verlinkt auf* - *Seite B* 

beschränkte  Aussagekraft von HTML wird um komplexe Aussagemöglichkeiten erweitert, die kreuz und quer durch das Netz Aussagen jeder Art über "Dinge" jeder Art zu treffen imstande sind. Dabei können die Bestandteile dieser Aussagen sowohl Subjekt oder Objekt neuer Aussagen werden. 
Dank der Verwendung von RDF und bereits etablierter Webinfrastruktur und -Standards sind Semantic Web-konform strukturierte und publizierte Daten als *Linked Data* maschinenlesbar und interoperabel und können in beliebige Beziehungen gesetzt werden.


### Terminologie

Im Kontext des Semantic Web begegnet eine Vielzahl sehr ambiger Begriffe, die zugleich außerordentlich inkonsistent Verwendung finden. Wenngleich an dieser Stelle für einige ausführlicheren terminologischen Untersuchungen auf @alma9913393902586 verwiesen werden kann, ist es an dieser Stelle dennoch sinnvoll, nochmals kurz auf einige der in dieser Arbeit verwendeten Begriffe einzugehen.

* Der syntaktische Kontext der Elemente *Subjekt*, *Prädikat*, *Objekt* ergibt einen gerichteten Graphen. Der Oberbegriff für die einzelnen, nun kontextuell losgelöst gedachten Elemente lautet in dieser Arbeit gemäß Stuckenschmidt *Konzepte*.[^e271] 
* Die "Kanten" des Graphen, die also je nach Kontext *Subjekt* oder *Objekt* sein können, heißen im Folgenden *Entitäten*, wobei diese *Entitäten* sowohl "Dinge", als auch "Mengen von Dingen" sein können.[^e272] 
* Etwas weniger einheitlich wird mit dem Element *Prädikat* verfahren: er wird, je nach Kontext, als *Property* oder *Relation* bezeichnet.
* Kaum ein anderer Begriff ist in derartige Ambivalenz gehüllt, wie der Begriff "Ontologie", sodass eine Definition für diese Arbeit höchstens näherungsweise – übrigens auch in der Fachliteratur gelebte Praxis –[^e275] erfolgen kann. Dies gilt nicht lediglich für den Umstand, dass er als "Lehnwort" aus der Philosophie in verschiedenen Disziplinen unterschiedliche Verwendung findet,[^e280] vielmehr herrscht auch in der Informatik selbst kein eigentlicher Konsens über seinen Bedeutungsinhalt.[^e281]
Über das Begriffspaar *Ontologie* und *Vokabular* schreibt das *W3C* (*World Wide Web Consortium*): "[...] ontologies and vocabularies within the Semantic Web can be regarded as synonymous, although ontologies may denote more complex conceptualisations (W3C, 2015)."[^e273] Diese Arbeit verfährt wiederum etwas anders, indem sie diese prinzipielle Synonymität aufhebt und die Begriffe anhand Funktion und Struktur qualitativ unterscheidet: Demnach handelt es sich beim Begriff *Vokabular* um "[...]die Verzeichnung aller (allgemeinen oder fachspezifischen) Benennungen zur Nutzung als Wissensordnung [...]."[^e274] Ihre Funktion besteht im Augenblick ihrer Nutzung darin, kontrolliertes Vokabular vorzuhalten. Für diese spezielle Nutzung kann nach Auffassung dieser Arbeit eine Ontologie mitunter ebenfalls verwendet werden. Charakteristika von Ontologien gegenüber anderen Systemen der Wissensorganisation sind in dieser Arbeit aber viel eher die folgenden Aspekte: Zumeist wird – sofern es um Ontologien im Semantic Web-Kontext geht – die formalisierte Sprachlichkeit und Maschinenlesbarkeit[^e277] bzw. die Möglichkeit automatisches Schlussfolgern ("Reasoning") zu vollziehen, erwähnt.[^e279] Bertram unterstreicht zudem ihre Vieldimensionalität und inhärente größtmögliche Flexibilität als Ordnungssystem in Bezug auf Beziehungsmöglichkeiten[^e276] und zuletzt impliziert die Existenz einer "light"-Variante, der sog. *lightweight ontology*[^e278] (s. #kapitel) ein hohes Maß an Komplexität.
* Die Bezeichnung *Metadatenprofil* (auch "Anwendungsprofil", "Applikationsprofil") impliziert – ähnlich wie im Falle von "Vokabular" – insbesondere eine funktionale Qualität für eine bestimmte Anwendung. Es handelt sich beim *Metadatenprofil* um ein Metadatenschema,[^e283] in dem typischerweise Elemente von bereits exisitierenden Modellen und Standards kombiniert und so ein für einen bestimmten Anwendungsfall optimiertes Metadatenschema geschaffen wird.[^e282] Eher untypisch erscheint hingegen, dass ein Metadatenprofil auch eigene Terme definiert.[^e284] Da dies jedoch in dieser Arbeit der Fall sein wird, weist das hier entwickelte Metadatenprofil auch Eigenschaften eines Vokabulars auf.
Bei dieser Definition ist noch nichts über die Struktur gesagt – so nimmt etwa das in dieser Arbeit zu erarbeitende Metadatenprofil die Form eines *lightweight ontology* (s. #kapitel).





[^e1]: [@van_der_meer_instrumentenkunde_nodate.]
[^e2]: [@Musicalinstrument.]
[^e3]: [@hyvonen_publishing_2012, S. 7–8.]
[^e4]: [@gobel_gnd_2017, S.2.]
[^e5]: Akronym blabla
[^e6]: [@tomasi_modellieren_2018, S. 175.]
[^e7]: Eine sehr umfassende Auseinandersetzung mit Chancen für Einrichtungen und Nutzer findet sich in: @waibel_think_2009.
[^e8]: Eine phänomenologisch fundierte Thematisierung der Beziehung zwischen Wahrnehmungssubjekt und Musikinstrument findet sich in: [@de_souza_music_2017, S. 20–23.]

[^e264]: [@alma99244375602586]
[^e265]: [@noauthor_semantic_nodate.]

[^e266]: [@gobel_gnd_2017.]
[^e267]: [@altenhoner_nfdi4culture_2020.]
[^e268]: Einführende Werke zum Semantic Web und einzelner Vokabulare finden sich in @allemang_semantic_2011, @TN_libero_mab21631588, sowie @noy_ontology_nodate zur Modellierung von Ontologien. @hyvonen_publishing_2012 beinhaltet zudem gute Hinweise für die Publikation von Linked Data in Kulturerbeeinrichtungen, @noauthor_notitle_nodate-1 zu technischen Fragen. 
[^e269]: [@sparqlcrmsuppe_sparqlcrmsuppevocsforinstruments_2020.]
[^e270]: So bspw. die Prozesse zur Standardbildung des *W3C*, vgl.: @noauthor_world_nodate.
[^e271]: [@alma9913393902586, S. 10.]
[^e272]: [@fischer_lexikon_2008, S. 275.]
[^e273]: Zit. nach: @ziku_digital_2020, S. 5. Ziku zitiert ihrerseits: [@noauthor_ontologies_nodate-1.]
[^e274]: [@stock_wissensreprasentation_2008, S. 188.] Stock spricht von "Nomenklaturen" statt "Vokabularen".
[^e275]: Diese außerordentliche Ambivalenz des Begriffes wird eindrücklich durch den Umstand illustriert, dass Stuckenschmidt ebenfalls eine endgültige Definition vermeidet (immerhin lautet der Titel "Ontologien : Konzepte, Technologien und Anwendungen").


[^e276]: [@TN_libero_mab213864266, S. 261.]
[^e277]: [@busse_was_2014, S. 289.]
[^e278]: [@article, S. 1.]
[^e279]: [@stock_wissensreprasentation_2008, S. 257.]
[^e280]: Sehr Interessant ist in diesem Zusammenhang der Artikel [@busse_was_2014-2], in dem eine interdisziplinäre Annäherung an den Begriff erfolgt.

[^ea28]: [@noauthor_w3c_nodate.]

[^ea29]: 

[^ea30]: PDF, HTML, Video

[^ea31]: [@szeredi_lukácsy_benkő_nagy_2014, S. 21.]

[^ea32]: 

[^ea34]: [@madoc34762, S. 2.]

[^ea35]: 

[^ea36]: Das Verhältnis zwischen der *Wikipedia* und *Wikidata* mag an dieser Stelle zur Verdeutlichung hilfreich sein: …

[^ea37]: [@noauthor_why_nodate.]

[^e281]: Vgl.: [@alma9913393902586, S. 22–24.]
[^e282]: [@cs79, S. 25.]
[^e283]: "A metadata schema is simply a set of elements with a precise semantic definition, optionally connected by some structure." Vgl.: [@cs79, S. 8.]
[^e284]: 