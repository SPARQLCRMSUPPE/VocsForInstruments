# Anbindung an- / Integration in das Semantic Web

## Vorüberlegungen

### Hintergrund

In den vorangegangenen Kapiteln wurde ein Modell in eine strukturell auf RDF basierende Ontologie "übersetzt". Deren "Grammatik" orientierte sich zwar an der im Semantic Web standardisierten (RDF, RDFS, OWL), deren Semantik und Etabliertheit das Potential für eine anschließende Integration im Semantic Web birgt. Doch bleiben die in dieser Ontologie verwahrten Konzepte durch die Brille des "Semantic Web-Subjekts" betrachtet diffus: es handelt sich lediglich um eine Menge arbiträrer Entitäten, die in bestimmten, jedoch außerordentlich allgemeinen Beziehungen stehen. 
Es gilt insofern an dieser Stelle abermals einen hermeneutischen Prozess zu durchlaufen, in dessen Zuge die nicht-explizierten Konzepte im Namespace `ma:` dermaßen erschlossen werden, dass sie für ein Wahrnehmungssubjekt interpretierbar werden. 
Abermals stellt sich, wie in #Kapitel die Frage, in welcher Weise der hier begegnende Verständnishorizont zu überwinden ist. Dies ist für ein menschliches Subjekt relativ einfach zu beantworten, etwa indem Konzepte mit sinnvollen Namen und Erklärungen versehen werden. Doch wie verhält es sich mit einem Wahrnehmungssubjekt, das nur die Sprache des Semantic Webs beherrscht ("things not strings")?[^yc8697]

Hier erscheint eine kurze Digression in die philosophische Ontologie hilfreich: Eine zentrale Idee der Heidegger'schen Philosophie ist, dass das "eigentliche Wesen" von "Zeug"[^yc8694] (im Gegensatz etwa zu Platons Ideenlehre) keineswegs diesem a priori inhärent ist, sondern sich in der Welt erst in seiner kontextuellen habituellen Funktionalität und Materialität gegenüber einem Wahrnehmungssubjekt äußert.[^yc8696] Diese Annahme erscheint auch hier aufschlussreich: Kontext – sich in funktionalen Beziehungen zwischen Konzepten ausdrückend – bildet im Semantic Web die Prämisse von Semantik. Das "Wesen" der Konzepte liegt keineswegs in ihrer textuellen Beschreibung ("strings") begründet, sondern in ihrer Rolle als Sinnträger innerhalb eines Bedeutungsgefüges und gegenüber einem "besorgenden" Wahrnehmungssubjekt.

So ist etwa das Wesen des Konzepts "Spucknapf" in den folgenden RDF-Tripeln ein je anderes: 

1. "Mann" "spuckt in" "Spucknapf"
2. "Spucknapf" "fällt auf" "Mann (Kopf)"

Neben dem offensichtlichen, hier variablen grammatikalischen "Wesen", Subjekt und Objekt,[nicht sicher ob das so geht] liegt im ersten Beispiel das Wesen des Spucknapfs darin begründet, dass es "der Gegenstand" ist, "in das man reinspuckt". Im zweiten ist es jedoch "das zerbrechliche Ding, das durch Fallen auf den Kopf Schmerzen und Ekel bereitet.
Exakt analog hierzu erscheint das "Wesen" einer Entität innerhalb einer formalen Welt dadurch bestimmt, in welchen Relationen sie zu der sie umgebenden, wechselwirkenden Welt steht.
Und umgekehrt: löst man Konzepte aus diesem Gefüge heraus (wie es bislang in dieser Arbeit der Fall ist), entbindet man sie ihrer semantischen Kraft, und sie werden, im schlimmsten Fall, zu nichts weiterem als zu kontingenten URIs, jedenfalls aber – zumindest nach Heidegger – zu einem trivialen lediglich "Vorhandenen".
\

### Semantische Verknüpfungsmöglichkeiten mit dem Semantic Web 

Es stellt sich nun die Frage, wie diese Kontextualisierung konzeptionell umzusetzen ist. Boten bislang insbesondere die Arbeiten von Ontology101[^yc8698] und Stuckenschmidt[^yc8699] einen guten Leitfaden für die Erstellung von Ontologien im Sinne abstrakter formalisierter Wissensrepräsentationen, so findet sich in der Literatur kaum irgendwo ein Hinweis zur Umsetzung semantischer Kontextualisierung eigener Ontologien im Semantic Web.

Einen Hinweis liefert Hyvönen, indem er drei Bestandteile einer (Semantic Web)-"Ontologieinfrastruktur" ausmacht:

>1.  Domain independent vocabularies are needed for facilitating cross-domain interoperability. For example, thesaurus standards and the W3C Semantic Web recommendations RDF(S), SKOS, and OWL fall into this category, as well as generic metadata schemas, such as Dublin Core.
    
>2.  Domain specific ontologies [...]. For example, the Getty Vocabularies (AAT, TGN, and ULAN), the Library of Congress Subject Headings (LCSH), and other vocabularies used for annotating contents fall in this category.

>3.  Institution specific ontologies are needed for concepts that may be relevant for a particular organization only or cannot be shared for some reason with a larger community[...].[^yc8700]

Anhand dieser Bestandsaufnahme lassen sich mehrere Aussagen schlussfolgern: Neben der auf technischer Ebene wichtigen Information, dass eine im Semantic Web integrierte Ontologie sich aus verschiedenen Vokabularen aus verschiedenen Bereichen zusammensetzt (ja zusammensetzen sollte),[^yc8708] halten diese Informationen auch Hinweise auf die Frage nach semantischer Kontextualisierung bereit:
Eine Ontologie erhält ihre Aussagekraft indem sie sich in den Kontext bereits etablierter Vokabulare stellt. Dabei sind die etabliertesten diejenigen, die das höchste Maß an Verständlichkeit anbieten –  domänen- und institutionsspezifische die, die das höchste Maß an semantischer Spezifität zu erreichen imstande sind.

Freilich ist hierdurch nur wenig über den eigentlichen semantischen Prozess der Verknüpfung eigener Ontologien im Semantic Web ausgesagt. Die Empfehlung der Semantic Web-Pioniere Bizer, Heath und Berners-Lee[^y5] hingegen "[s]et RDF links to other data sources on the Web, so that clients can navigate the Web of Data as a whole by following RDF links[...]",[^yc8701] bietet einige konkrete Hinweise für diese Umsetzung:

#### 1) Mapping

In etwa analog zur Klassifizierung von Konzepten in #kapitelx können eigene Konzepte in Relation zu extern, etablierten Konzepten gesetzt werden, und diese Relationen als Eigenschaft in der RDF-Beschreibung des Konzepts fixiert werden. Der bisherige Verständnishorizont wäre somit für eine Anwendung, die das Metadatenprofil parsed, überwunden, und ein Konnex zwischen Metadatenprofil und Semantic Web geschaffen.\
Ein *vorläufiges* Beispiel:

``ma:Klangbeispiel	rdfs:subclassOf	<http://d-nb.info/gnd/4052020-1> .``

In Worten: Der Term "Klangbeispiel" im `ma:`-Namespace wird als Unterklasse des in der GND definierten Schlagworts "Schallaufzeichnung" verstanden. 

Das Property `rdfs:subclassOf` verlinkt dabei die Entität `ma:Klangbeispiel` in eine externe, bereits im Semantic Web eingebundene und semantisch etablierte Ontologie, die Gemeinsame Normdatei, sodass nun also auch die Entität `ma:Klangbeispiel` (freilich erst nach Publikation im Netz) in das Semantic Web integriert ist. 

Neben Integration durch hierarchische Relation (bspw. `rdfs:subclassOf`) kommen auch Äquivalenzrelationen für diesen Verlinkungsvorgang infrage. Insbesondere das Vokabular SKOS ("Simple Knowledge Organization System")[^yc8702] hat sich etabliert, um etwa Thesauri in RDF zu überführen,[^yc8703] jedoch insbesondere auch um Vokabulare und Ontologien aufeinander zu beziehen[^yc8704] (ontology alignment,[^yc8706] Mapping). Hierfür sind etwa die Properties

`skos:exactMatch`, `skos:narrowMatch`, `skos:broadMatch`, `skos:closeMatch`

besonders geeignet. Deutlich wird aber zugleich, dass die Ambivalenz dieser Propeties (ausgenommen `skos:exactMatch`) groß ist und daher womöglich keine endgültig befriedigende semantische Eindeutigkeit ermöglichen kann.\

#### 2) Integration von bereits etablierten externen Konzepten

Während das Mappen zu äquivalenten Termen im Falle sich bereits in Verwendung befindlicher und somit unantastbarer Vokabulare im Sinne einer bestmöglichen Integration ins Semantic Web sinnvoll sein mag, erscheint es angesichts von Funktionsweise und Architektur des Semantic Webs im Falle des Metadatenprofils als nicht erstrebenswert. Obwohl die Produktion von Doubletten (und anschließendem Mapping) im Sinne der *open world assumption* im Semantic Web nicht "falsch" ist,[^yc8705] so ist sie doch eingedenk dessen Konzeption als offene, ins Netz ausgelagerte "Datenbank", in dem jeder Datensatz für jeden zugänglich und referenzierbar ist, unsinnig, ist doch Kontextualisierung durch den Rekurs auf semantisch etablierte und somit aussagekräftige Konzepte, wie bereits mehrfach betont, sogar außerordentlich wünschenswert. 
Diese Aussagekraft erhöht sich weiter durch Wiederverwendung etablierter Konzepte und der Vermeidung von konkurrierenden Redundanzen: "it is considered good practice to reuse terms from well-known RDF vocabularies [...] wherever possible in order to make it easier for client applications to process Linked Data. Only if these vocabularies do not provide the required terms should data publishers define new, data source-specific terminology [...]."[^yc8707] Zu guter Letzt wird so "[...]die Einheitlichkeit und Interoperabilität der Beschreibungen sicher[gestellt]."[^yc8709]

So erfolgte also die semantische Verknüpfung des Konzepts `ma:Ton` mit dem Semantic Web nicht nach dem in #Kapitel 1) Mapping erwähnten Schema
``
ma:Ton	skos:exactMatch	gnd:Ton .,
``
sondern besser einfach durch Übernahme des Konzepts `gnd:Ton` anstelle von `ma:Ton`.

### Vorgehensweise

Für den Fortgang dieser Arbeit erscheint die folgende allgemeine Vorgehensweise sinnvoll:

1. Das verbleibende, institutionsübergreifende Vokabular im Namespace `ma:` ist daraufhin zu untersuchen, ob sich seine Semantizität auch adäquat mit externen Konzepten abbildet, und eigene Terme in diesem Fall durch sie zu ersetzen. Dabei wird es gelten, eine ausgewogene Balance zwischen semantisch festen, jedoch vermutlich eher unspezifischen, domänenübergreifend verwendeten Konzepten, und spezifischen, jedoch womöglich weniger etablierten Konzepten auszutarieren. Dieser Vorgang birgt einige methodische Herausforderungen, auf die an entsprechender Stelle eingegangen werden wird.
2. Eigene Terme, für die sich keine vorexistierende Entsprechungen finden lassen, sind nochmals zu fokussieren und einer terminologischen Kontrolle zu unterziehen. Anschließend sind sie gemäß 1) im vorhergehenden Kapitel in Beziehung zu externen Vokabularen zu setzen und so im Semantic Web durch Verknüpfung aussagekräftig referenzierbar zu machen. Sie sind anschließend gemäß der guten Praxis bei Namespaces[^yc8710] auch mit menschenlesbaren Informationen und Bezeichnungen ("Labels") anzureichern.[^yc8711]


#### Terminologische Kontrolle / Modellierung / Methodik

Mit "terminologischer Kontrolle" sind im Sinne Bertrams "alle Maßnahmen [...], die direkt oder indirekt der Definition und Abgrenzung von Begriffen und der eindeutigen Zuordnung von Bezeichnungen zu Begriffen dienen [...]"[^yc8712] gemeint. Während dieser Prozess in einem herkömmlichen Thesaurus insbesondere introspektiv auf die Arbeit mit internen Termen gerichtet sein dürfte, so umfasst der hier miteinzubeziehende Thesaurus nichts Geringeres als die Gesamtheit aller im Semantic Web eingebundenen Daten. Es liegt somit auf der Hand, dass dieser Prozess sich in vielem von der herkömmlichen Erstellung von Vokabularen unterscheiden muss. Leider findet sich in der Literatur, wie bereits eingangs erwähnt, kaum ein Hinweis, wie dieser Vorgang zu gestalten sein mag. Dieser Umstand kann auch nicht weiter verwundern, bedenkt man, dass die Heterogenität formalisierter Weltrepräsentationen in Form von Ontologien, die die Komplexität und Ambivalenz der realen Welt widerspiegeln muss. Zugleich erscheint der Vorgang der Formalisierung von Wissen, und somit von Wahrnehmung, ein stark subjektiver – einen allgemeingültigen Leitfaden unter diesen Umständen zu formulieren, ist somit naturgemäß schwierig, erscheint aber als lohnenswertes Desiderat für künftige Arbeiten.

Für diese Arbeit erscheinen die folgenden Schritte und Abwägungen sinnvoll:

* Eine Grundbeschaffenheit des Semantic Webs liegt in seiner Qualität als Hypertext[^y4] aller in ihm verwobenen Modellierungen und Ontologien. Dieser Umstand macht eine – eigentlich wünschenswerte – initiale vollständige philologische Auswertung einzelner Textteile (Vokabulare), und es muss mit einem heuristischen Ansatz vorliebgenommen werden. Dieser besteht darin, unter Zuhilfenahme geeigneter Suchwerkzeuge, fallspezifisch nach terminologischen Lösungen zu suchen. Wie dies in der Praxis gelingen kann, wird sich prozessual im Laufe der folgenden Kapitel entfalten. (Eine Ausarbeitung der generierten Erkenntnisse zur Methodik ist nicht Gegenstand dieser Arbeit, stellt aber wie erwähnt ein sehr vielversprechendes Desiderat dar!)
* Bereits mehrfach wurde auf den Wert etablierter Vokabulare hingewiesen. Unter diesen findet sich eine Reihe von Vokabularen, die als Standards, wenn nicht gar als Grundpfeiler des Semantic Webs gelten können. Diese sind insbesondere RDF, RDFS, SKOS, OWL, aber auch etwa Dublin Core. Ihre Verwendung ist gut dokumentiert, und es existiert eine vergleichbar große Menge einführender Literatur, die als Leitfaden zu Rate gezogen werden kann.[^yc8713] Diese Vokabulare fanden bereits teilweise Verwendung in den vorangegangenen Kapiteln, und es wird aufgrund ihrer hohen Aussagekraft gelten, auch im Folgenden sich ihrer wann immer möglich zu bedienen.

Hinsichtlich der Recherche nach domänenspezifischen Vokabularen und deren Anwendung sind verschiedene Strategien vorstellbar, die in dieser Arbeit jeweils anzuwenden sein werden:

* Es erscheint naheliegend, die Verwendungsweise von Terminologie im Rahmen solcher domänenspezifischer Projekte zu untersuchen, die ihre Daten als Linked Open Data zur Verfügung stellen. Entsprechend der spartenübergreifenden Zielsetzung dieser Arbeit sind dies Akteure aus dem gesamten Spektrum des musikbezogenen Kulturerbebereichs.[^y1]
* Einen Sucheinstieg für Vokabulare bietet das *Basel Register of Thesauri, Ontologies and Classifikations*[^y2], in dem auch fachspezifische Suchen möglich sind.
* Das Portal *Linked Open Vocabularies*[^y3] ist eine Metasuchmaschine, mit der eine große Zahl von Triplestores durchsucht werden kann. Suchergebnisse können wiederum nach unterschiedlichen Kriterien (Disziplin, Konzept etc.) gefiltert werden.
* Zumindest erwähnenswert ist die technische Möglichkeit, eigene referenzierbare und semantisch kontextualisierte Datensätze – etwa in Wikidata – zu erstellen. Ob dies auch für das hier entwickelte Metadatenprofil sinnvoll ist, ist wiederum eine andere Frage.

















---

[^yc2]: Vgl. etwa die Aussage "Individual instances are the most specific concepts represented in a knowledge base." ([@gangler_semantic_nodate, S.18]).

[^yc4]: [@noauthor_owl_nodate]

[^yc5]: OWL2 differenziert zwischen *Object Properties* und *Datatype Properties* (vgl.: [noauthor_owl_nodate-2]). Obwohl etwa *ma:a'=415Hz* prinzipiell auch mit *Datatype Properties* modelliert werden könnte, erscheint diese Detailtiefe für den hier exemplarisch durchgeprobten Anwendungsfall nicht notwendig.

[^yc6]: [@TN_libero_mab21631588, S. 27–28.]

[^yc7]: [@TN_libero_mab213864266, S. 128]

[^yc8]: [@noy_ontology_nodate]
Auch Stuckenschmidt legt diese Vorgehensweise nahe (vgl.: [@alma9913393902586]).

[^yc9]: Zum Begriff siehe [@ TN_libero_mab213864266, S. 150]

[^yc10]: Für diese Arbeit spielen insbesondere RDFS ([@ noauthor_rdfs_nodate]) und OWL ([@ noauthor_owl_nodate-3]) eine Rolle.

[^yc11]: "Individualbegriffe"  [@ stock_wissensreprasentation_2008, S. 84].

[^yc12]: In "Semantic Web-Sprache" augedrückt, wären das die Klassen *rdfs:class*, *rdfs:instanceOf* und *rdf:property*.

[^yc13]: Auf eine Übersicht der gängigen übergeordneten Klassen – etwa "Literals", "Datatypes", "Blank nodes" etc. – muss an dieser Stelle verzichtet werden.

[^yc14]: [@TN_libero_mab213864266, S. 151]

[^yc15]: [@alma9913393902586, S. 166]

[^yc16]: S. hierzu etwa: [@alma9913393902586, S. 95–99]

[^yc17]: [@noauthor_owl_nodate-3] Diese Arbeit verwendet OWL Full, das die größten Ausdrucksmöglichkeiten bietet und mit RDFS kompatibel ist. (Vgl. [@TN_libero_mab21631588, S. 125–127])

[^yc18]: 

[^yc19]:  [@alma9913393902586, S. 146]

[^yc20]: Vgl.: [@noauthor_rdf_nodate-2]

[^yc21]: [@national_information_standards_organization_u.s._guidelines_2005, S. 3]



[^yc23]: [@TN_libero_mab213864266, S. 151]

[^yc24]: Die Serialisierung erfolgt am einfachsten, indem etwa der Ontologieeditor *Protégé* zu Hilfe genommen wird. Er ermöglicht den Export von Ontologien in vielfältigen Formaten.

[^yc25]:  [@alma9913393902586, S. 169]

[^yc26]: [@alma9913393902586, S. 24]

[^yc27]: Auch in OWL verfügt über entsprechende (noch mächtigere) Möglichkeiten, diese Beziehungen auszudrücken (vgl. hierzu etwa: [@allemang_semantic_2011, S. 238-239.]) Allerdings erscheint für die Belange dieser Arbeit die Terminologie von RDFS als genügend.

[^yc28]: Wörtlich also: "Das Objekt mit der Signatur 1663 hat den Typ eines Barockhorns".

[^yc29]: [@alma9913393902586, S. 106]


[^yc31]: [@noauthor_rdf_nodate-3]

[^yc32]: [@noauthor_rdf_nodate-4]

[^yc33]: [@alma9913393902586, S. 169]

[^yc8649]: Zur spezifischen Problematik des an dieser Stelle verwendeten  FRBR/FRAD-Modells bei Werken der Musik s.  [@bicher_normdaten_2018, S. 225].

[^yc8650]: In den sogenannten *Functional Requirements for Bibliographic Data*, deren Entitätenmodell an dieser Stelle verwendet wird, heißt es: "Ein Werk ist eine abstrakte Entität; es gibt keinen entsprechenden materiellen Gegenstand." ([@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 16]).

[^yc8651]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 18–20.]

[^yc8652]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 20–22.]

[^yc8653]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 22–23.]

[^yc8654]: Und somit strenggenommen ebenfalls eine domänenspezifische Entität. **in MIMO verlinken**

[^yc8655]: Ein gleichermaßen illustratives wie auch charmantes Beispiel für eine solche Beziehung wären etwa Leopold Mozarts und Johann Ernst Eberlins Komposition "Der Morgen und der Abend" ([@mozart_eberlin_morgen_nodate]) für das "Hornwerk" der Festung Hohensalzburg aus dem 16. Jahrhundert, dem sog. *Salzburger Stier* ([@hocker_mechanische_2016]). (Ein lohnenswerter klanglicher Eindruck lässt sich hier gewinnen: [@noauthor_salzburger_nodate]).

[^yc8656]: Daher die gestrichelte Verbindungslinie zwischen Objekt und der Entität der relativen Stimmung.

[^yc8657]: Anders verhielte es sich freilich, würde mit dem hier definierten Schema beispielsweise eine Audioaufnahme einer Aufführung mit modernen Instrumenten erschlossen.

[^yc8658]: Etwa lassen die Stimmungen von unstimmbaren Instrumenten (Blockflöten, Zinken etc.) sehr präzise Rückschlüsse auf die historische Musikpraxis zu (vgl.: [@haynes_stimmton_2016]).

[^yc8659]: Nach Martin Fowler, dem Begründer des Modells: "An object model of the domain that incorporates both behavior and data." (vgl.:[@N_libero_mab2, S. 116]).

[^yc8660]: Da diese Arbeit angesichts ihres Fallbeispiels sehr stark RISM als primäre Domäne hervorhebt, kann gar nicht oft genug betont werden, dass jede andere relevante Domäne gleichermaßen im Vordergrund stehen könnte. So ist letztlich auch die Objektentität innerhalb einer Domäne, in diesem Fall dem Musikinstrumentenmuseum der Universität Leipzig, angesiedelt, das seinerseits sein Objekt mit dem RISM-Datensatz verlinken könnte, und dasselbe gilt selbstverständlich auch für Editionen, Bibliotheken, Archive, Wirtschaftsunternehmen etc.


[^yc8661]: Siehe hierzu etwa: [@alma9958916302586, S. 338–343]

[^yc8662]: [@alma9958916302586, S. 342–343]

[^yc8663]: [@alma9958916302586, S. 343]

[^yc8664]: Um den Umfang dieser Arbeit in Grenzen zu halten, kann nicht jedem denkbaren Szenario in ihr Rechnung getragen werden. Vielmehr würden sich solche tiefergehenden Überlegungen im Rahmen einer Weiterentwicklung des Anwendungsprofils empfehlen.

[^yc8665]: Sowohl "simultan" (vgl. etwa den Hornsatz in C. M. v. Webers Ouvertüre zur Oper "Der Freischütz": "Corni in F" sowie "Corni in C"), als auch "sukszessive" ab der Klassik zwischen Sätzen und mit der zunehmenden Erweiterung des harmonischen Raums im Laufe des 19. Jahrhunderts immer mehr auch in kontingenter Abfolge. 

[^yc8666]: Tatsächlich kann diese Entität in Zusammenhang mit Objekten lediglich in Verbindung mit Instrumenten Verwendung finden, die etwa aus baulichen, physikalischen Gründen eine solche "Grundstimmung" vorweisen.

[^yc8667]: Vgl. [@haynes_stimmton_2016]

[^yc8668]: So etwa im Falle der Eigenschaft *Entsprechungsgrad* angelegt: Es lassen sich unterschiedliche Grade vorstellen.

[^yc8670]: Zu den technischen Aspekten von Namespaces im Semantic Web siehe insb. [@noauthor_linked_nodate] sowie [@heath_linked_2011]  und [@noauthor_associating_nodate]

[^yc8671]: Vgl. etwa: [@madoc34762, S. 3]

[^yc8672]: OWL2 differenziert, anders als etwa RDFS, nicht lediglich zwischen Klasse und Instanz, sondern zwischen Klasse und unterschiedlichen Individuen (vgl. [@noauthor_owl_nodate-1])

[^yc8673]: Vgl. [@noauthor_architecture_nodate]

[^yc8674]: [@allemang_semantic_2011, 128–130]

[^yc8675]: [@noauthor_rdf_nodate]

[^yc8676]: [@noauthor_rdf_nodate-6]

[^yc8677]: [@TN_libero_mab21631588, S. 13]

[^yc8678]: [@noauthor_resource_nodate]

[^yc8679]: [@alma9913393902586, S. 32]
\
Dies etwa im Gegensatz zur *closed world assumption* in herkömmlichen relationalen Datenbanken. Zur Notwendigkeit der Open World Assumption in semantischen Netzen s: [@alma9913393902586, S. 43]

[^yc8680]: [@TN_libero_mab21631588, S. 67]

[^yc8681]: [@szeredi_lukácsy_benkő_nagy_2014, S. 98–99]

[^yc8682]: [@noauthor_overview_nodate]

[^yc8683]: [@TN_libero_mab21631588, S. 77]

[^yc8684]: "Jede definierte Einschra ̈nkung auf einer Property wirkt al- so immer global auf jedes Vorkommen dieser Property, weswegen man bei der Angabe solcher Einschra ̈nkungen darauf achten muss, immer die allge- meinsten denkbaren Klassen anzugeben (also diejenigen, die mit Sicherheit alle mo ̈glichen Ressourcen, die in der fraglichen Beziehung stehen ko ̈nnen, enthalten)." ([@TN_libero_mab21631588, S. 77])

[^yc8685]: [@noauthor_examples_nodate]

[^yc8686]: [@noauthor_examples_nodate]

[^yc8687]: descriptive logic – AI - solcher Kram

[^yc8688]: [@alma9913393902586, S. 77]

[^yc8690]: [@hyvonen_publishing_2012, S. 76]

[^yc8691]: [@TN_libero_mab21631588, S. 68]

[^yc8692]: [@alma9913393902586, S. 170–171]

[^yc8693]: Husserl

[^yc8694]: 

[^yc8695]: 

[^yc8696]: 

[^yc8697]: noauthor_introducing_2012
[^yc8698]: 

[^yc8699]: 

[^yc8700]: [@hyvonen_publishing_2012, S. 87–88]

[^yc8701]: [@madoc34762, S. 6]
[^yc8702]: 

[^yc8703]: [@allemang_semantic_2011, S. 207]

[^yc8704]: [@allemang_semantic_2011, S. 213]

[^yc8705]: [@noauthor_overview_nodate]

[^yc8706]: [@zimanyi_web_2015, S. 79–80]

[^yc8707]: [@madoc34762, S. 7] Die Autoren berufen sich ihrerseits auf [@noauthor_how_nodate]

[^yc8708]: Vgl. auch [@noauthor_how_nodate]: "It is common practice to mix terms from different vocabularies."

[^yc8709]: [@alma9913393902586, S. 160–161]

[^yc8710]: 

[^yc8711]: "Begriffliche Kontrolle", vgl.: [@TN_libero_mab213864266, S. 128]

[^yc8712]: [@TN_libero_mab213864266, S. 128]

[^yc8713]: In dieser Arbeit wurden vor allem die Texte [@allemang_semantic_2011] sowie [@TN_libero_mab21631588] zu Rate gezogen.

[^y1]: Für eine Auswahl relevanter Vokabulare für den GLAM-Bereich s. @TN_libero_mab2 und
@ziku_digital_2020. Für eine Auswahl musikrelevanter Vokabulare s. @lisena_controlled_nodate, @bicher_normdaten_2018, @nurmikko-fuller_building_2018, @nurmikko-fuller_collaboration_2016.


[^y2]: [@noauthor_bartocorg_nodate.]
[^y3]: [@noauthor_linked_nodate-1]
[^y4]: Z. Begriff "Hypertext" siehe etwa: [@niewerth_dinge-nutzer-netze_2018, S. 92–93.]
[^y5]: Letzterer gilt gar als "Erfinder" des Konzepts eines *Semantic Webs*.