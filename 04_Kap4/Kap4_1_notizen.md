Wie lässt sich die Semantik eines Terms messen? Müsste man jetzt für jedes nochmal eine föderierte Suche machen?














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










—

das gemeinsame ist dieser Gedanke, dass der Sinn von Dingen sich nicht aus sich selbst heraus generiert, bzw. ihrer Äußerlichkeit, sondern dass er in ihrer Funktionalität in Beziehung zu anderem entsteht

ihr Wesen (also das, was für sie wesentlich ist) ist das Sein der zuhandenen Entitäten. Das wird in einer Ontologie ganz deutlich: Entitäten sind auf ihr Wesen beschränkt und stehen aufgrund von diesem in intentionaler Beziehung zueinander.

Das ist eine 1:1 Rekreation von Verstehen und sinnlicher Beziehung in der realen Welt – die Dinge haben keinen inhärenten, objektivierbaren Wesenskern (Plato?), sondern ihre Bedeutung konstruiert sich in ihrer Beziehung zueinander.
Auch Linguistic Turn oder so.


"Das Dasein existiert nicht zunächst rein für sich selbst, um sich dann auch auf die Welt zu beziehen. Vielmehr muss die Welt, die Heidegger als einen umfassenden Bedeutungszusammenhang versteht, als ein konstitutives Element des Daseins selbst, d.h. also als ein Strukturmoment des Daseins betrachtet werden." [Phäno 49]

"Man hat gemeinhin als völlig selbstverständlich vorausgesetzt [...], dass das Seiende, das uns zunächst und zumeist in der Welt umgibt, Gegenstände von substantiellen, materiellem, ausgedehntem etc. Charakter" seien. Das ist jedoch – nach Heidegger – ein grundlegender Irrtum. Dasjenige Seiende, das uns in unserem alltäglichen In-der-Welt-sein zunächst und zumeist begegnet, ist kein vorhandenes Ding, sondern *zuhandenes "Zeug"*."[Phänom 49–50]






Das ist vielleicht genau der Punkt, warum Heidegger hier so interessant ist: Ontologie als solches klammert die die Wahrnehmungskomponente aus – hier aber ja genau das behandelt – es geht um "formale" Erfahrung und "sinnliche" Erschließung einer Welt.



In der Vorhandenheit, also in der theoretischen Umgangsweise des Menschen mit dem Ding, fokussiert man — meistens anschauend — das gegebene Ding und vernachlässigt dessen Umkreis. Das so anvisierte Ding wird nach Heidegger aus seinem natürlichen und zweckmäßigen **Zusammenhang** gerissen und als das Objekt der reinen Theorie betrachtet. Unter diesen Umständen kann das Wesen des Dings versteckt oder verzerrt sein.

In der Zuhandenheit, also in der **praktischen Umgangsweise** des Daseins mit dem Ding, bewahrt man den Überblick über den lebendigen und zweckentsprechenden Zusammenhang. Das Ding bekommt seinen passenden Platz und verliert nicht sein natürliches Milieu.  
Das Zuhandene als Zeug besitzt eine Struktur der Hinweisung. Es verweist stets auf die Zeug- und Zweckganzheit, die Heidegger als die Bewandtnisganzheit bezeichnet. Das heißt: Ein isoliertes Zeug zählt nicht zum Zeug.
https://edoc.hu-berlin.de/bitstream/handle/18452/15701/Sun.pdf?sequence=1&isAllowed=y















"Wie schon in XML versteht man un- ter einem Vokabular meist eine Zusammenstellung von Bezeichnern mit klar definierter Bedeutung." [@TN_libero_mab21631588, S. 48]

"formale Definition von Begriffen und deren Beziehungen als Grundlage für ein gemeinsames Verständnis."[@busse_was_2014, S. 2] 

"Wir nennen in der Informatik eine Ontologie eine formale Definition von Begriffen und deren Beziehungen – bezogen auf eine Anwendungsdomäne. „Formal“ heißt in einer Sprache, deren Syntax und Semantik definiert sind und die von Computerprogrammen bearbeitet werden kann." [@busse_was_2014, S. 4]

Ontologie hier verwendet im Sinne seiner Vieldimensionalität.



Begriff Vokabular hier (auch wenn eigentlich Ontologie) v.a. verwendet, um zu suggerieren, dass jene Ontologie hier als Sammlung von Begriffen benutzt wird bzw. die Begriffe kontingent herangezogen werden


















---

# Notizen

Nachdem bereits vorläufige "Domains" in Form von Präfixen (*ma:*, *rism:*, *taxonomie:*, *mimul*) definiert worden waren, scheint es denkbar, die nun mit RDF ausgezeichneten Terme im Internet zu verankern und somit in das Semantic Web einzubetten. 





Many namespaces have been created in the context of Semantic Web projects to distinguish the names of classes, properties and individuals defined and/or described by that project from all others. One common approach is to use a namespace URI ending with a hash (`#`) to identify the namespace, in which case the URI _without_ the hash is available to identify the information resource which describes the namespace, that is, the namespace document.

"An URIs kann, abgetrennt durch #, auch ein weiteres Fragment angehängt werden. Die Kombination aus URI und Fragment wird URI-Referenz genannt. URI- Referenzen werden in RDF häufig zur eindeutigen Referenzierung von Ressourcen verwendet und stellen somit eine wichtige Komponente der Semantic-Web-Schichten dar."[^c6]



"Oft muss man aber auch vo ̈llig neue URIs bilden. In einem solchen Fall muss man sicherstellen, dass die gewa ̈hlte URI nicht versehentlich anderswo mit anderer Bedeutung zum Einsatz kommt. Eine gute Methode dazu ist es, eine URI zu wa ̈hlen, die sich aus einer Webadresse ableitet, deren Inhalte man selbst kontrolliert. Eine URI, die mit http://springer.com/... beginnt, soll- te demnach nur vom Springer-Verlag eingefu ̈hrt werden. Außerdem ist es in einem solchen Fall mo ̈glich, an der entsprechenden Adresse ein Dokument ab- zulegen, welches die Bedeutung der URI fu ̈r Menschen beschreibt." [@TN_libero_mab21631588, S. 48–49]

"Eine Mo ̈glichkeit ist die Verwendung von URI-Referenzen. Schreibt man z.B. http://de.wikipedia.org/wiki/Othello#URI, dann zeigt dies nicht direkt auf ein existierendes Dokument (da es den Abschnitt ”URI“ auf dieser Seite nicht gibt). Wenn man diese URI-Referenz als URL aufruft, dann erha ̈lt man dennoch die beschreibende Seite fu ̈r diese URI." [@TN_libero_mab21631588, S. 49]

"Eine andere Mo ̈glichkeit ist die Verwendung von Weiterleitungen: auch bei Aufruf einer nicht existierenden URL kann ein Server den Nutzer auf eine alternative Seite weiterleiten. Da das Programm des Nutzers diese Weiterlei- tung wahrnimmt, ist dennoch die Unterscheidung der URIs gewa ̈hrleistet. Die automatische Weiterleitung hat außerdem den Vorteil, dass man entweder eine menschenlesbare HTML-Datei oder eine maschinenlesbare RDF-Datei auslie- fern kann – abha ̈ngig von Informationen in der Anfrage. Dieses Verfahren ist auch als Content Negotiation bekannt." [@TN_libero_mab21631588, S. 49]


---