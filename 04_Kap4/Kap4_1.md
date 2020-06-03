# Anbindung an- / Integration in das Semantic Web

In den vorangegangenen Kapiteln wurde ein Modell in eine strukturell auf RDF basierende Ontologie "übersetzt". Deren "Grammatik" orientierte sich zwar an der im Semantic Web standardisierten (RDF, RDFS, OWL), deren Semantik und Etablierung das Potential für eine Integration im Semantic Web birgt. Doch bleiben die in dieser Ontologie verwahrten Konzepte durch die Brille des "Semantic Web-Subjekts" betrachtet diffus: erkennbar sind lediglich eine Menge arbiträrer Entitäten, die in bestimmten, jedoch nicht weiter spezifizierten Beziehungen zueinander stehen. 
Es gilt insofern an dieser Stelle abermals einen hermeneutischen Prozess zu durchlaufen, in dessen Zuge die nicht-explizierten Konzepte im Namespace :ma dermaßen erschlossen werden, dass sie für ein Wahrnehmungssubjekt interpretierbar werden. 
Abermals stellt sich, wie in #Kapitel die Frage, in welcher Weise der Verständnishorizont zu überwinden ist. Dies ist für ein menschliches Subjekt relativ einfach zu beantworten, etwa indem Konzepte mit sinnvollen Namen und Erklärungen versehen werden. Doch wie verhält es sich mit einem Wahrnehmungssubjekt, das nur die Sprache des Semantic Webs beherrscht ("things not strings")?[^c8697]

Eine zentrale Idee der Heidegger'schen Philosophie ist, dass das eigentliche Wesen von "Zeug"[^c8694] (im Gegensatz etwa zu Platons Ideenlehre) keineswegs diesem a priori inhärent ist, sondern sich in der Welt erst in seiner kontextuellen habituellen Funktionalität und Materialität gegenüber einem Wahrnehmungssubjekt äußert.[^c8696] Dieses Prinzip erscheint sich hier nochmals im Rahmen von Linked Data und Semantic Web eindrücklich nachzubilden: Kontext – sich in funktionalen Beziehungen zwischen Konzepten ausdrückend – bildet die Prämisse von Semantik. Das Wesen der Konzepte zeigt sich keineswegs in ihrer textuellen Beschreibung ("strings") begründet, sondern in ihrer Rolle als Sinnträger innerhalb eines Bedeutungsgefüges und gegenüber einem "besorgenden" Wahrnehmungssubjekt.

So ist etwa – ganz vereinfacht – das Wesen des Konzepts "Spucknapf" in den folgenden RDF-Tripeln ein je anderes: 

1. "Mann" "spuckt in" "Spucknapf"
2. "Spucknapf" "fällt auf" "Mann (Kopf)"

Neben dem offensichtlichen, hier variablen grammatikalischen "Wesen", Subjekt und Objekt,[nicht sicher ob das so geht] liegt im ersten Beispiel das Wesen des Spucknapfs darin begründet, dass es "der Gegenstand" ist, "in das man reinspuckt". Im zweiten ist es jedoch "das zerbrechliche Ding, das durch Fallen auf den Kopf Schmerzen und Ekel bereitet."
Exakt analog hierzu erscheint das "Wesen" einer Entität innerhalb einer formalen Welt dadurch bestimmt, in welchen Relationen sie zu der sie umgebenden, wechselwirkenden Welt steht.
Und umgekehrt, löst man Konzepte aus diesem Gefüge heraus (wie es bislang in dieser Arbeit der Fall ist), entbindet man sie ihrer semantischen Kraft, und sie werden, im schlimmsten Fall, zu nichts weiterem als zu kontingenten URIs, jedenfalls aber – zumindest nach Heidegger – zu einem trivialen lediglich Vorhandenen.
\

Es stellt sich nun die Frage, wie diese Kontextualisierung technisch umzusetzen ist. Boten bislang insbesondere die Arbeiten von Ontology101[^c8698] und Stuckenschmidt[^c8699] einen guten Leitfaden für die Erstellung von Ontologien im Sinne abstrakter formalisierter Wissenspräsentationen, so findet sich in der Literatur kaum irgendwo ein Hinweis zur Umsetzung semantischer Kontextualisierung eigener Ontologien im Semantic Web.

Einen Hinweis liefert Hyvönen, indem er drei Bestandteile einer (Semantic Web)-"Ontologieinfrastruktur" ausmacht:

>1.  Domain independent vocabularies are needed for facilitating cross-domain interoperability. For example, thesaurus standards and the W3C Semantic Web recommendations RDF(S), SKOS, and OWL fall into this category, as well as generic metadata schemas, such as Dublin Core.
    
>2.  Domain specific ontologies [...]. For example, the Getty Vocabularies (AAT, TGN, and ULAN), the Library of Congress Subject Headings (LCSH), and other vocabularies used for annotating contents fall in this category.

>3.  Institution specific ontologies are needed for concepts that may be relevant for a particular organization only or cannot be shared for some reason with a larger community[...].[^c8700]

Anhand dieser Bestandsaufnahme lassen sich mehrere Aussagen schlussfolgern: Neben der auf technischer Ebene wichtigen Information, dass eine im Semantic Web integrierte Ontologie sich aus verschiedenen Vokabularen aus verschiedenen Bereichen zusammensetzt (ja zusammensetzen sollte),[^c8708] halten diese Informationen auch Hinweise auf die Frage nach semantischer Kontextualisierung bereit:
Eine Ontologie erhält ihre Aussagekraft indem sie sich in den Kontext bereits etablierter Vokabulare stellt. Dabei sind die etabliertesten diejenigen, die das höchste Maß an Verständlichkeit (Interoperabilität) anbieten –  domänen- und institutionsspezifische die, die das höchste Maß an semantischer Spezifität zu erreichen imstande sind.

Freilich ist hierdurch nur wenig über den eigentlichen technischen Prozess der Verknüpfung eigener Ontologien im Semantic Web ausgesagt. Etwas aussagekräftiger ist wiederum etwa die Maßgabe "[s]et RDF links to other data sources on the Web, so that clients can navigate the Web of Data as a whole by following RDF links."[^c8701] Die folgenden Möglichkeiten lassen sich aus dieser Forderung ableiten:

1) In etwa analog zur Klassierung von Konzepten in #kapitelx erscheint es denkbar, eigene Konzepte in Relation zu externen Konzepten zu setzen, und diese Relationen als Eigenschaft in der RDF-Beschreibung des Konzepts zu fixieren. Der bisherige Verständnishorizont wäre somit für eine Anwendung, die das Applikationsprofil parsed, überwunden, und ein Konnex zwischen Domänenontologie und Semantic Web geschaffen.\
Ein – vorläufiges – Beispiel:

``ma:Klangbeispiel	rdfs:subclassOf	<http://d-nb.info/gnd/4052020-1> .``

In Worten: Der Term "Klangbeispiel" im :ma-Namespace wird als Unterklasse des in der GND definierten Schlagworts "Schallaufzeichnung" verstanden. 

Das Property `rdfs:subclassOf` verlinkt dabei in eine externe, bereits im Semantic Web eingebundene und semantisch etablierte Ontologie, die GND. 

Neben dieser hierarchischen Relation sind auch Äquivalenzrelationen darstellbar. Insbesondere das Vokabular SKOS ("Simple Knowledge Organization System")[^c8702] hat sich etabliert, um etwa Thesauri in RDF zu überführen,[^c8703] jedoch insbesondere auch um Vokabulare und Ontologien aufeinander zu beziehen[^c8704] (ontology alignment,[^c8706] Mapping). Hierfür sind sich etwa die Properties

``
skos:exactMatch

skos:narrowMatch

skos:broadMatch

skos:closeMatch
``
besonders geeignet. Es wird jedoch deutlich, dass die Ambivalenz dieser Propeties (ausgenommen `skos:exactMatch`) naturgemäß groß ist und daher keine endgültig befriedigende semantische Eindeutigkeit ermöglichen kann.\

2) Während das Mappen zu äquivalenten Termen im Falle sich bereits in Verwendung befindlicher und somit unantastbarer Vokabulare notwendig sein mag, erscheint es angesichts von Funktionsweise und Architektur des Semantic Webs im Falle des Applikationsprofils nicht erstrebenswert. Obwohl die Produktion von Doubletten (und anschließendem Mapping) im Sinne der *open world assumption* im Semantic Web nicht "falsch" ist,[^c8705] so ist sie doch eingedenk dessen Konzeption als offene, ins Netz ausgelagerte "Datenbank", in dem jeder Datensatz für jeden zugänglich und referenzierbar ist, unsinnig, ist doch Kontextualisierung durch den Rekurs auf semantisch etablierte und somit aussagekräftige Konzepte, wie bereits mehrfach betont, sogar außerordentlich wünschenswert. 
Diese Aussagekraft erhöht sich weiter durch Wiederverwendung etablierter Konzepte und der Vermeidung von konkurrierenden Redeundanzen: "it is considered good practice to reuse terms from well-known RDF vocabularies [...] wherever possible in order to make it easier for client applications to process Linked Data. Only if these vocabularies do not provide the required terms should data publishers define new, data source-specific terminology [...]."[^c8707]So wird zu guter Letzt "[...]die Einheitlichkeit und Interoperabilität der Beschreibungen sicher[gestellt]."[^c8709]

So ist also das Konzept `ma:Ton` bei der Einbindung ins Semantic Web nicht über die Festlegung
``
ma:Ton	skos:exactMatch	gnd:Ton .,
``
sondern einfach durch das Konzept `gnd:Ton` zu ersetzen.

### Vorgehensweise

Für den Fortgang dieser Arbeit erscheint die folgende Vorgehensweise sinnvoll:

1. Das Vokabular in seiner derzeitigen Form beinhaltet auch Platzhalter für institutionsspezifische Terme. Diese sind aus dem Vokabular auszulagern und in separaten Namespaces zu sammeln.
2. Das verbleibende, institutionsübergreifende Vokabular im Namespace :ma ist daraufhin zu untersuchen, ob sich seine Semantizität auch ebensogut in externen Konzepten abbildet, und eigene Terme in diesem Fall durch sie zu ersetzen. Dabei wird es gelten, eine ausgewogene Balance zwischen semantisch festen, jedoch vermutlich eher unspezifischen, domänenübergreifend verwendeten Konzepten, und spezifischen, jedoch womöglich weniger etablierten Konzepten auszutarieren. Dieser Vorgang birgt einige methodische Herausforderungen, auf die an entsprechender Stelle eingegangen werden wird.
3. Eigene Terme, für die sich keine vorexistierende Entsprechungen finden lassen, sind nochmals zu fokussieren und einer terminologischen Kontrolle zu unterziehen. Anschließend sind sie gemäß 1) im vorhergehenden Kapitel in Beziehung zu externen Vokabularen zu setzen und so im Semantic Web durch Verknüpfung aussagekräftig referenzierbar zu machen. Sie sind anschließend gemäß der guten Praxis bei Namespaces[^c8710] auch mit menschenlesbaren Informationen und Bezeichnungen ("Labels") anzureichern.[^c8711]


#### Terminologische Kontrolle

Mit "terminologischer Kontrolle" sind im Sinne Bertrams "alle Maßnahmen [...], die direkt oder indirekt der Definition und Abgrenzung von Begriffen und der eindeutigen Zuordnung von Bezeichnungen zu Begriffen dienen [...]"[^c8712] gemeint. Während dieser Prozess in einem herkömmlichen Thesaurus insbesondere introspektiv auf die Arbeit mit internen Termen gerichtet sein dürfte, so umfasst der hier miteinzubeziehende Thesaurus nichts Geringeres als die Gesamtheit aller im Semantic Web eingebundenen Daten. Es liegt somit auf der Hand, dass dieser Prozess sich in vielem von der herkömmlichen Erstellung von Vokabularen unterscheiden muss. Leider findet sich in der Literatur, wie bereits eingangs erwähnt, kaum ein Hinweis, wie dieser Vorgang zu gestalten sein mag. Dieser Umstand kann auch nicht weiter verwundern, bedenkt man, dass die Heterogenität formalisierter Weltrepräsentationen in Form von Ontologien die Heterogenität, Komplexität und Ambivalenz der realen Welt widerspiegeln muss – einen allgemeingültigen Leitfaden unter diesen Umständen zu formulieren, ist somit naturgemäß schwierig, erscheint aber als lohnenswertes Desiderat für künftige Arbeiten.

Für diese Arbeit erscheinen die folgenden Schritte und Abwägungen sinnvoll:

* Bereits mehrfach wurde auf den Wert etablierter Vokabulare hingewiesen. Unter diesen findet sich eine Reihe von Vokabularen, die als Standards, wenn nicht gar als Grundpfeiler des Semantic Webs gelten können. Diese sind insbesondere RDF, RDFS, SKOS, OWL, aber auch etwa Dublin Core. Ihre Verwendung ist gut dokumentiert, und es existiert eine vergleichbar große Menge einführender Literatur, die als Leitfaden zu Rate gezogen werden kann.[^c8713] Diese Vokabulare fanden bereits teilweise Verwendung in den vorangegangenen Kapiteln, und es wird aufgrund ihrer hohen Aussagekraft gelten, auch im Folgenden sich ihrer wann immer möglich zu bedienen.

Hinsichtlich der Recherche nach domänenspezifischen Vokabularen und deren Anwendung sind verschiedene Strategien vorstellbar, die in dieser Arbeit jeweils zur Anwendung kommen werden:

* Es erscheint naheliegend, die Verwendung von Vokabularen im Rahmen solcher domänenspezifischer Projekte zu untersuchen, die ihre Daten als Linked Open Data zur Verfügung stellen. Entsprechend der spartenübergreifenden Zielsetzung dieser Arbeit sind dies Akteure aus dem gesamten Spektrum des musikbezogenen Kulturerbebereichs. Also Portale


* Europeana
* RISM
* MIMO
* DOREMUS

Vokabulare

* GND
* LCSH
* CIDOC CRM
* https://wiki.lyrasis.org/display/LD4P/Performed+Music+Ontology

* BARTOC
* https://lov.linkeddata.es/dataset/lov/



---

Weiteres Vorgehen: Schluss mit Methodikgeschwafel: jeder Begriff wird jetzt einfach systematisch abgearbeitet.



es bleibt ein subjektives, gefühlsmäßiges Ding – es gibt kein eindeutiges Richtig/Falsch

Denkbar wäre philologische Auswertung der Vokabulare, aber würde Rahmen der Arbeit sprengen. Daher iterativ – deckt sich auch mit Vorgehen in der Praxis.






Wie lässt sich die Semantik eines Terms messen? Müsste man jetzt für jedes nochmal eine föderierte Suche machen?



2 Möglichkeiten:
1. Bei den Playern suchen, gucken was sie verwenden
2. Freie Suche nach Vokabularen 






Es ist eigentlich egal, welche Systematik man verwendet – man sollte vielleicht einfach immer auf einen Standard verlinken.









Vielleicht erstmal die domänenspezifischen Dinger jeweils vorstellen – tabellarisch?
die anderen sind ja schon standardisiert, dann muss man nicht.



---


"Anyone is free to publish vocabularies to the Web of Data (Berrueta & Phipps, 2008), which in turn can be connected by RDF triples that link classes and properties in one vocabulary to those in another, thereby defining mappings between related vocabularies."

" Linked Data - The Story So Far

1\. Assign URIs to the entities described by the data set and provide for dereferencing these URIs over the HTTP protocol into RDF representations.

2\. Set RDF links to other data sources on the Web, so that clients can navigate the Web of Data as a whole by following RDF links.

3\. Provide metadata about published data, so that clients can assess the quality of published data and choose between different means of access."



" Linked Data - The Story So Far

it is considered good practice to reuse terms from well-known RDF vocabularies such as FOAF, SIOC, SKOS, DOAP, vCard, Dublin Core, OAI-ORE or GoodRelations wherever possible in order to make it easier for client applications to process Linked Data. Only if these vocabularies do not provide the required terms should data publishers define new, data source-specific terminology (Bizer & Cyganiak & Heath, 2007). If new terminology is defined, it should be made self-describing by making the URIs that identify terms Web dereferencable (Berrueta & Phipps, 2008)."


" Linked Data - The Story So Far

based on a mixture of using common vocabularies together with data source-specific terms that are connected by mappings as deemed necessary."

Wiederum auf technischer Ebene 













die Entität in ihrer Funktionalität charakterisiert, die sie aus dem Kontext erhält → Mapping/In-Relation-Setzen

Sollte man das "Wahrnehmungssubjekt" irgendwie vom Endnutzer abkoppeln? Das eine ist in der Welt – das andere nicht.

Die Entitäten der Welt 


Es geht also wieder um Klassierung und dadurch Erkennbarkeit, Deutbarkeit von Entitäten gegenüber einem Subjekt. Hermeneutik


Wie werden Sachen verstehbar? Man sagt, was sie sind



Was wird gemacht:

Die Konzepte, die konzeptuell da sind, stehen nicht mehr nur in irgendeiner undefinierten Beziehung zueinander. Sie sind mit – kontextuell-objektiviertem, normativem – Sinn angereichert (beschrieben), der durch das Wahrnehmungssubjekt interpretierbar ist. [das ist dann auch :label drin]

technisch: Übersetzung mit domänen




war das davor die Grammatik? Vorsicht: nicht zuviel Linguistik



Weltheit

Während bei Ontologieerstellung durchaus Anleitungen, bei Einbindung in Semantic Web eher nicht (stimmt?)
Wie also verfahren? Methodik entwickeln...


Dimensionen:

1. Generisches Vokabular verwenden.
hier zu sagen, warum.
Welche? Wie ausgewählt.
* sollte generell etabliert sein. sollte in den Domänen etabliert sein.
    * wo gucken? Europeana, RISM, MIMO <- ja! und nach Überschneidungen suchen!
2. Verbindung zu ähnlichen Konzepten (sofern sie nicht existieren!) – z.B. ma:natürliche Stimmung a gnd:Stimmungssystem – oder so
= "Einfügen dieser Entitäten in die Architektur des Semantic Webs" 
<- das Ding ist, dass die Bedeutung im Semantic Web tatsächlich durch den Kontext hergestellt wird
Eine tiefere Einsicht in die Natur eines Konzeptes wird nur dadurch erreicht, dass es innerhalb des Verständnishorizonts und seiner Gegenstände eingeführt wird – es wird vom Vorhandenen zum Zuhandenen – ihr Sein zeigt sich erst in ihrer Eingebettetheit



man müsste dann auch jetzt mal die Vokabulare trennen. Ist vielleicht ein guter Zeitpunkt, so als Einführung


Vorgehensweise:
* Generelles: wieso Mixtur aus verschiedenen Vokabularen
* Einführung: hier hört es mit der Literatur so langsam auf <- demonstieren
    * Hyvonen?
* Vorgehen
* Vokabulare trennen.
* [rdfs:label]





—

das gemeinsame ist dieser Gedanke, dass der Sinn von Dingen sich nicht aus sich selbst heraus generiert, bzw. ihrer Äußerlichkeit, sondern dass er in ihrer Funktionalität in Beziehung zu anderem entsteht

ihr Wesen (also das, was für sie wesentlich ist) ist das Sein der zuhandenen Entitäten. Das wird in einer Ontologie ganz deutlich: Entitäten sind auf ihr Wesen beschränkt und stehen aufgrund von diesem in intentionaler Beziehung zueinander.

Das ist eine 1:1 Rekreation von Verstehen und sinnlicher Beziehung in der realen Welt – die Dinge haben keinen inhärenten, objektivierbaren Wesenskern (Plato?), sondern ihre Bedeutung konstruiert sich in ihrer Beziehung zueinander.
Auch Linguistic Turn oder so.


"Das Dasein existiert nicht zunächst rein für sich selbst, um sich dann auch auf die Welt zu beziehen. Vielmehr muss die Welt, die Heidegger als einen umfassenden Bedeutungszusammenhang versteht, als ein konstitutives Element des Daseins selbst, d.h. also als ein Strukturmoment des Daseins betrachtet werden." [Phäno 49]

"Man hat gemeinhin als völlig selbstverständlich vorausgesetzt [...], dass das Seiende, das uns zunächst und zumeist in der Welt umgibt, Gegenstände von substantiellen, materiellem, ausgedehntem etc. Charakter" seien. Das ist jedoch – nach Heidegger – ein grundlegender Irrtum. Dasjenige Seiende, das uns in unserem alltäglichen In-der-Welt-sein zunächst und zumeist begegnet, ist kein vorhandenes Ding, sondern *zuhandenes "Zeug"*."[Phänom 49–50]





Wir erschließen uns diese Welt, die wir untersuchen, die aus dem Zuhandenen besteht, Schritt für Schritt

Das ist vielleicht genau der Punkt, warum Heidegger hier so interessant ist: Ontologie als solches klammert die die Wahrnehmungskomponente aus – hier aber ja genau das behandelt – es geht um "formale" Erfahrung und "sinnliche" Erschließung einer Welt.



In der Vorhandenheit, also in der theoretischen Umgangsweise des Menschen mit dem Ding, fokussiert man — meistens anschauend — das gegebene Ding und vernachlässigt dessen Umkreis. Das so anvisierte Ding wird nach Heidegger aus seinem natürlichen und zweckmäßigen **Zusammenhang** gerissen und als das Objekt der reinen Theorie betrachtet. Unter diesen Umständen kann das Wesen des Dings versteckt oder verzerrt sein.

In der Zuhandenheit, also in der **praktischen Umgangsweise** des Daseins mit dem Ding, bewahrt man den Überblick über den lebendigen und zweckentsprechenden Zusammenhang. Das Ding bekommt seinen passenden Platz und verliert nicht sein natürliches Milieu.  
Das Zuhandene als Zeug besitzt eine Struktur der Hinweisung. Es verweist stets auf die Zeug- und Zweckganzheit, die Heidegger als die Bewandtnisganzheit bezeichnet. Das heißt: Ein isoliertes Zeug zählt nicht zum Zeug.
https://edoc.hu-berlin.de/bitstream/handle/18452/15701/Sun.pdf?sequence=1&isAllowed=y











"semantische[s] Bindeglied zwischen Klassen und Propertys".[^c30]




"Wie schon in XML versteht man un- ter einem Vokabular meist eine Zusammenstellung von Bezeichnern mit klar definierter Bedeutung." [@TN_libero_mab21631588, S. 48]

"formale Definition von Begriffen und deren Beziehungen als Grundlage für ein gemeinsames Verständnis."[@busse_was_2014, S. 2] 

"Wir nennen in der Informatik eine Ontologie eine formale Definition von Begriffen und deren Beziehungen – bezogen auf eine Anwendungsdomäne. „Formal“ heißt in einer Sprache, deren Syntax und Semantik definiert sind und die von Computerprogrammen bearbeitet werden kann." [@busse_was_2014, S. 4]

Ontologie hier verwendet im Sinne seiner Vieldimensionalität.



Begriff Vokabular hier (auch wenn eigentlich Ontologie) v.a. verwendet, um zu suggerieren, dass jene Ontologie hier als Sammlung von Begriffen benutzt wird bzw. die Begriffe kontingent herangezogen werden

































Einschränkung der Properties insb. bei Metadatenprofil wichtig: 



















---

# Notizen

Nachdem bereits vorläufige "Domains" in Form von Präfixen (*ma:*, *rism:*, *taxonomie:*, *mimul*) definiert worden waren, scheint es denkbar, die nun mit RDF ausgezeichneten Terme im Internet zu verankern und somit in das Semantic Web einzubetten. 





Many namespaces have been created in the context of Semantic Web projects to distinguish the names of classes, properties and individuals defined and/or described by that project from all others. One common approach is to use a namespace URI ending with a hash (`#`) to identify the namespace, in which case the URI _without_ the hash is available to identify the information resource which describes the namespace, that is, the namespace document.

"An URIs kann, abgetrennt durch #, auch ein weiteres Fragment angehängt werden. Die Kombination aus URI und Fragment wird URI-Referenz genannt. URI- Referenzen werden in RDF häufig zur eindeutigen Referenzierung von Ressourcen verwendet und stellen somit eine wichtige Komponente der Semantic-Web-Schichten dar."[^c6]



"Oft muss man aber auch vo ̈llig neue URIs bilden. In einem solchen Fall muss man sicherstellen, dass die gewa ̈hlte URI nicht versehentlich anderswo mit anderer Bedeutung zum Einsatz kommt. Eine gute Methode dazu ist es, eine URI zu wa ̈hlen, die sich aus einer Webadresse ableitet, deren Inhalte man selbst kontrolliert. Eine URI, die mit http://springer.com/... beginnt, soll- te demnach nur vom Springer-Verlag eingefu ̈hrt werden. Außerdem ist es in einem solchen Fall mo ̈glich, an der entsprechenden Adresse ein Dokument ab- zulegen, welches die Bedeutung der URI fu ̈r Menschen beschreibt." [@TN_libero_mab21631588, S. 48–49]

"Eine Mo ̈glichkeit ist die Verwendung von URI-Referenzen. Schreibt man z.B. http://de.wikipedia.org/wiki/Othello#URI, dann zeigt dies nicht direkt auf ein existierendes Dokument (da es den Abschnitt ”URI“ auf dieser Seite nicht gibt). Wenn man diese URI-Referenz als URL aufruft, dann erha ̈lt man dennoch die beschreibende Seite fu ̈r diese URI." [@TN_libero_mab21631588, S. 49]

"Eine andere Mo ̈glichkeit ist die Verwendung von Weiterleitungen: auch bei Aufruf einer nicht existierenden URL kann ein Server den Nutzer auf eine alternative Seite weiterleiten. Da das Programm des Nutzers diese Weiterlei- tung wahrnimmt, ist dennoch die Unterscheidung der URIs gewa ̈hrleistet. Die automatische Weiterleitung hat außerdem den Vorteil, dass man entweder eine menschenlesbare HTML-Datei oder eine maschinenlesbare RDF-Datei auslie- fern kann – abha ̈ngig von Informationen in der Anfrage. Dieses Verfahren ist auch als Content Negotiation bekannt." [@TN_libero_mab21631588, S. 49]


---

[^c1]: Zur Schreibweise: 

[^c2]: Vgl. etwa die Aussage "Individual instances are the most specific concepts represented in a knowledge base." ([@gangler_semantic_nodate, S.18]).

[^c4]: [@noauthor_owl_nodate]

[^c5]: OWL2 differenziert zwischen *Object Properties* und *Datatype Properties* (vgl.: [noauthor_owl_nodate-2]). Obwohl etwa *ma:a'=415Hz* prinzipiell auch mit *Datatype Properties* modelliert werden könnte, erscheint diese Detailtiefe für den hier exemplarisch durchgeprobten Anwendungsfall nicht notwendig.

[^c6]: [@TN_libero_mab21631588, S. 27–28.]

[^c7]: [@TN_libero_mab213864266, S. 128]

[^c8]: [@noy_ontology_nodate]
Auch Stuckenschmidt legt diese Vorgehensweise nahe (vgl.: [@alma9913393902586]).

[^c9]: Zum Begriff siehe [@ TN_libero_mab213864266, S. 150]

[^c10]: Für diese Arbeit spielen insbesondere RDFS ([@ noauthor_rdfs_nodate]) und OWL ([@ noauthor_owl_nodate-3]) eine Rolle.

[^c11]: "Individualbegriffe"  [@ stock_wissensreprasentation_2008, S. 84].

[^c12]: In "Semantic Web-Sprache" augedrückt, wären das die Klassen *rdfs:class*, *rdfs:instanceOf* und *rdf:property*.

[^c13]: Auf eine Übersicht der gängigen übergeordneten Klassen – etwa "Literals", "Datatypes", "Blank nodes" etc. – muss an dieser Stelle verzichtet werden.

[^c14]: [@TN_libero_mab213864266, S. 151]

[^c15]: [@alma9913393902586, S. 166]

[^c16]: S. hierzu etwa: [@alma9913393902586, S. 95–99]

[^c17]: [@noauthor_owl_nodate-3] Diese Arbeit verwendet OWL Full, das die größten Ausdrucksmöglichkeiten bietet und mit RDFS kompatibel ist. (Vgl. [@TN_libero_mab21631588, S. 125–127])

[^c18]: 

[^c19]:  [@alma9913393902586, S. 146]

[^c20]: Vgl.: [@noauthor_rdf_nodate-2]

[^c21]: [@national_information_standards_organization_u.s._guidelines_2005, S. 3]



[^c23]: [@TN_libero_mab213864266, S. 151]

[^c24]: Die Serialisierung erfolgt am einfachsten, indem etwa der Ontologieeditor *Protégé* zu Hilfe genommen wird. Er ermöglicht den Export von Ontologien in vielfältigen Formaten.

[^c25]:  [@alma9913393902586, S. 169]

[^c26]: [@alma9913393902586, S. 24]

[^c27]: Auch in OWL verfügt über entsprechende (noch mächtigere) Möglichkeiten, diese Beziehungen auszudrücken (vgl. hierzu etwa: [@allemang_semantic_2011, S. 238-239.]) Allerdings erscheint für die Belange dieser Arbeit die Terminologie von RDFS als genügend.

[^c28]: Wörtlich also: "Das Objekt mit der Signatur 1663 hat den Typ eines Barockhorns".

[^c29]: [@alma9913393902586, S. 106]

[^c30]: [@TN_libero_mab21631588, S. 77]

[^c31]: [@noauthor_rdf_nodate-3]

[^c32]: [@noauthor_rdf_nodate-4]

[^c33]: [@alma9913393902586, S. 169]

[^c8649]: Zur spezifischen Problematik des an dieser Stelle verwendeten  FRBR/FRAD-Modells bei Werken der Musik s.  [@bicher_normdaten_2018, S. 225].

[^c8650]: In den sogenannten *Functional Requirements for Bibliographic Data*, deren Entitätenmodell an dieser Stelle verwendet wird, heißt es: "Ein Werk ist eine abstrakte Entität; es gibt keinen entsprechenden materiellen Gegenstand." ([@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 16]).

[^c8651]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 18–20.]

[^c8652]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 20–22.]

[^c8653]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 22–23.]

[^c8654]: Und somit strenggenommen ebenfalls eine domänenspezifische Entität. **in MIMO verlinken**

[^c8655]: Ein gleichermaßen illustratives wie auch charmantes Beispiel für eine solche Beziehung wären etwa Leopold Mozarts und Johann Ernst Eberlins Komposition "Der Morgen und der Abend" ([@mozart_eberlin_morgen_nodate]) für das "Hornwerk" der Festung Hohensalzburg aus dem 16. Jahrhundert, dem sog. *Salzburger Stier* ([@hocker_mechanische_2016]). (Ein lohnenswerter klanglicher Eindruck lässt sich hier gewinnen: [@noauthor_salzburger_nodate]).

[^c8656]: Daher die gestrichelte Verbindungslinie zwischen Objekt und der Entität der relativen Stimmung.

[^c8657]: Anders verhielte es sich freilich, würde mit dem hier definierten Schema beispielsweise eine Audioaufnahme einer Aufführung mit modernen Instrumenten erschlossen.

[^c8658]: Etwa lassen die Stimmungen von unstimmbaren Instrumenten (Blockflöten, Zinken etc.) sehr präzise Rückschlüsse auf die historische Musikpraxis zu (vgl.: [@haynes_stimmton_2016]).

[^c8659]: Nach Martin Fowler, dem Begründer des Modells: "An object model of the domain that incorporates both behavior and data." (vgl.:[@N_libero_mab2, S. 116]).

[^c8660]: Da diese Arbeit angesichts ihres Fallbeispiels sehr stark RISM als primäre Domäne hervorhebt, kann gar nicht oft genug betont werden, dass jede andere relevante Domäne gleichermaßen im Vordergrund stehen könnte. So ist letztlich auch die Objektentität innerhalb einer Domäne, in diesem Fall dem Musikinstrumentenmuseum der Universität Leipzig, angesiedelt, das seinerseits sein Objekt mit dem RISM-Datensatz verlinken könnte, und dasselbe gilt selbstverständlich auch für Editionen, Bibliotheken, Archive, Wirtschaftsunternehmen etc.


[^c8661]: Siehe hierzu etwa: [@alma9958916302586, S. 338–343]

[^c8662]: [@alma9958916302586, S. 342–343]

[^c8663]: [@alma9958916302586, S. 343]

[^c8664]: Um den Umfang dieser Arbeit in Grenzen zu halten, kann nicht jedem denkbaren Szenario in ihr Rechnung getragen werden. Vielmehr würden sich solche tiefergehenden Überlegungen im Rahmen einer Weiterentwicklung des Anwendungsprofils empfehlen.

[^c8665]: Sowohl "simultan" (vgl. etwa den Hornsatz in C. M. v. Webers Ouvertüre zur Oper "Der Freischütz": "Corni in F" sowie "Corni in C"), als auch "sukszessive" ab der Klassik zwischen Sätzen und mit der zunehmenden Erweiterung des harmonischen Raums im Laufe des 19. Jahrhunderts immer mehr auch in kontingenter Abfolge. 

[^c8666]: Tatsächlich kann diese Entität in Zusammenhang mit Objekten lediglich in Verbindung mit Instrumenten Verwendung finden, die etwa aus baulichen, physikalischen Gründen eine solche "Grundstimmung" vorweisen.

[^c8667]: Vgl. [@haynes_stimmton_2016]

[^c8668]: So etwa im Falle der Eigenschaft *Entsprechungsgrad* angelegt: Es lassen sich unterschiedliche Grade vorstellen.

[^c8670]: Zu den technischen Aspekten von Namespaces im Semantic Web siehe insb. [@noauthor_linked_nodate] sowie [@heath_linked_2011]  und [@noauthor_associating_nodate]

[^c8671]: Vgl. etwa: [@madoc34762, S. 3]

[^c8672]: OWL2 differenziert, anders als etwa RDFS, nicht lediglich zwischen Klasse und Instanz, sondern zwischen Klasse und unterschiedlichen Individuen (vgl. [@noauthor_owl_nodate-1])

[^c8673]: Vgl. [@noauthor_architecture_nodate]

[^c8674]: [@allemang_semantic_2011, 128–130]

[^c8675]: [@noauthor_rdf_nodate]

[^c8676]: [@noauthor_rdf_nodate-6]

[^c8677]: [@TN_libero_mab21631588, S. 13]

[^c8678]: [@noauthor_resource_nodate]

[^c8679]: [@alma9913393902586, S. 32]
\
Dies etwa im Gegensatz zur *closed world assumption* in herkömmlichen relationalen Datenbanken. Zur Notwendigkeit der Open World Assumption in semantischen Netzen s: [@alma9913393902586, S. 43]

[^c8680]: [@TN_libero_mab21631588, S. 67]

[^c8681]: [@szeredi_lukácsy_benkő_nagy_2014, S. 98–99]

[^c8682]: [@noauthor_overview_nodate]

[^c8683]: [@TN_libero_mab21631588, S. 77]

[^c8684]: "Jede definierte Einschra ̈nkung auf einer Property wirkt al- so immer global auf jedes Vorkommen dieser Property, weswegen man bei der Angabe solcher Einschra ̈nkungen darauf achten muss, immer die allge- meinsten denkbaren Klassen anzugeben (also diejenigen, die mit Sicherheit alle mo ̈glichen Ressourcen, die in der fraglichen Beziehung stehen ko ̈nnen, enthalten)." ([@TN_libero_mab21631588, S. 77])

[^c8685]: [@noauthor_examples_nodate]

[^c8686]: [@noauthor_examples_nodate]

[^c8687]: descriptive logic – AI - solcher Kram

[^c8688]: [@alma9913393902586, S. 77]

[^c8690]: [@hyvonen_publishing_2012, S. 76]

[^c8691]: [@TN_libero_mab21631588, S. 68]

[^c8692]: [@alma9913393902586, S. 170–171]

[^c8693]: Husserl

[^c8694]: 

[^c8695]: 

[^c8696]: 

[^c8697]: noauthor_introducing_2012
[^c8698]: 

[^c8699]: 

[^c8700]: [@hyvonen_publishing_2012, S. 87–88]

[^c8701]: [@madoc34762, S. 6]
[^c8702]: 

[^c8703]: [@allemang_semantic_2011, S. 207]

[^c8704]: [@allemang_semantic_2011, S. 213]

[^c8705]: [@noauthor_overview_nodate]

[^c8706]: [@zimanyi_web_2015, S. 79–80]

[^c8707]: [@madoc34762, S. 7] Die Autoren berufen sich ihrerseits auf [@noauthor_how_nodate]

[^c8708]: Vgl. auch [@noauthor_how_nodate]: "It is common practice to mix terms from different vocabularies."

[^c8709]: [@alma9913393902586, S. 160–161]

[^c8710]: 

[^c8711]: "Begriffliche Kontrolle", vgl.: [@TN_libero_mab213864266, S. 128]

[^c8712]: [@TN_libero_mab213864266, S. 128]

[^c8713]: In dieser Arbeit wurden vor allem die Texte [@allemang_semantic_2011] sowie [@TN_libero_mab21631588] zu Rate gezogen.