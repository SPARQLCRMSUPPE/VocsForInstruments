1. "intellektuelle" Klassenzuordnung
2. Fixierung der klassifizierten Entitäten mithilfe einer Semantic Web-Sprache – Übersetzung in ihr "Weltbild" <- wird so verständlich
    -Auswahl Syntax
    -Auswahl Sprache!!
4. Verfügbarmachen: Einfügen dieser Entitäten in die Architektur des Semantic Webs
        eigentlich erst später – macht aber Sinn jetzt schon
        
        
 Literatur bezieht sich eigentlich fast nie auf das Technische, das man braucht, um selbst Daten zu publizieren.


# Klassifikatorische Erschließung


Das folgende Kapitel bildet den Ausgangspunkt dafür, den Weg von einem eigenen Datenmodell zu einer Semantic Web-kompatiblen Metadatenprofil zu beschreiten. Gemäß Noy und McGuinness[^8] steht ganz zu Beginn dieses langen Prozesses zunächst eine Klassierung[^9] der benötigten Typen nach folgendem Schema:

> 1. "Define the classes and the class hierarchy"
							2. "Define the properties of classes [...]"

Dieser Vorgehensweise liegt zugrunde, dass bereits in RDF bestimmte Klassen angelegt sind – in Folgevokabularen[^10] um weitere ergänzt –, die bestimmte Klassen vorgegeben.[^13] Dabei erscheinen angesichts des zuvor ausgearbeiteten Datenmodells die gebräuchlichsten drei Klassen[^12] für die Zwecke dieser Arbeit ausreichend. Diese sind:

1. Klassen
2. Instanzen[^11]
3. Eigenschaften

Durch die Aufteilung in Entitäten und Beziehungen lassen sich so also bereits RDF-Tripel bilden – zusätzlich gelingt es, dank der qualitativen Unterscheidung in Individuum und Klasse, einfache hierarchische Sachverhalte nachzubilden. In den folgenden Unterkapiteln wird es entsprechend darum gehen, eine entsprechende Klassierung vorzunehmen.

Doch worin besteht an dieser Stelle der tiefere Sinn einer Klassifikation? Neben der Funktion des reinen "Ordnens" führt Bertram auch die "erkenntnisvermittelnde Aufgabe" von Klassifikationen ins Feld, die in der "Aufhellung von Zusammenhängen anhand geordneten Wissens" besteht.[^14] Diese hermeneutische Dimension erscheint auch hier ganz zentral: Das Modell, das in seiner gegenwärtigen Form auf einem subjektiv geprägtem Verständnis, Wertesystem und Denkweisen des Autors beruht, wird in ein objektives, standardisiertes Modell überführt. Gewissermaßen findet so eine "Übersetzung" statt, die den Erkenntnishorizont zwischen Mensch und Maschine überwindet. Das eigene Denkmodell wird dabei mithilfe der sprachlichen Ausdruckmittel des Semantic Web erfasst und ausgezeichnet, und so in das von RDF-vorgegebene Erkenntnisschema eingepflegt. Die dem Modell inhärente Semantik wird – freilich zunächst auf einer sehr oberflächlichen Ebene – dadurch objektiviert und gemeinhin auslegbar.

Diese Übersetzung geht mithilfe entsprechend standardiserter, sich ergänzender Modellierungssprachen, den sogenannten "Ontologiesprachen", vonstatten.[^16] Dabei richtet sich diese Arbeit insbesondere an der Ontologiesprache OWL[^17], der "inzwischen [...] meistbenutzen Ontologiesprache aller Zeiten"[^19] aus. Dies geschieht sowohl aus pragmatischen Gründen – der Ontologie-Editor *Protégé*[^18] basiert auf dieser Sprache – als auch aus fachlichen, die es wert sein wird, in einem nachfolgenden Unterkapitel für sich kurz zu skizzieren.

**wichtig, dass kein Informationsverlust durch diese Wahl!**

Die formale Interpretierbarkeit der durch die Sprache ausgedrückte semantischen Komponente wird durch eine Syntax, also einer  "Menge von Regeln, um Programme oder Dokumente mit bestimmten Eigenschaften [...] zu erzeugen", ermöglicht. Die Entscheidung für eine bestimmte Syntax ist dabei im Falle nach RDF strukturierter Daten zwar letztlich arbiträr, bilden sie doch gewissermaßen nur die "Verpackung und Beipackzettel" für den eigentlichen semantischen Inhalt. Doch fällt hier die Wahl auf das sogenannte *Turtle*-Format ("Terse RDF Triple Language")[^20] aufgrund der Einfachheit und Übersichtlichkeit dieser Syntax.

So entsteht zunächst ein sehr einfaches kontrolliertes Vokabular – etwa im sehr grob gefassten Sinne des *National Information Standards Organization* und des *American National Standards Institute*. Diesemzufolge handelt es sich bei einem kontrollierten Vokabular um "[a] list of terms that have been enumerated explicitly. This list is controlled by and is available from a controlled vocabulary registration authority. All terms in a controlled vocabulary must have an unambiguous, non-redundant definition."[^21]
Diese Disambiguierung erfolgt dabei analog zur Klassifizierung ind der folgenden Form (s. auch Kapitel #klassenundinstanzen):

Typ ist eine Klasse
Typ ist eine Instanz
Typ ist eine Eigenschaft




!Erstmal erstellen wir einfach ein Vokabular – denn keine Relationen – nur Definitionen

Ich verwende OWL Full! <- informieren… hierzu und zum owl kopf [@TN_libero_mab21631588, S. 130 ff.]



## Klassen und Instanzen

Hier wird auch Serialisiert!

> "Deciding whether a particular concept is a class in an ontology or an individual instance depends on what the potential applications of the ontology are. Deciding where classes end and individual instances begin starts with deciding what is the lowest level of granularity in the representation. The level of granularity is in turn determined by a potential application of the ontology. In other words, what are the most specific items that are going to be represented in the knowledge base?" [@gangler_semantic_nodate, S.18]

Die hier zur Differenzierung zwischen Klasse und Instanz implizit vorgeschlagene Vorgehensweise,[^2] bei der die niedrigste Entität eines hierarchischen Strangs, bestehend aus Klassen, als Instanz zu werten ist, erscheint im Falle einer in sich abgeschlossenen Ontologie als durchaus sinnvoll. Doch muss der Blickwinkel im Fall der hier beabsichtigten Anwendung als verbindendes Metadatenprofil auch auf potentielle Anknüpfungspunkte, aber vor allem auf die Anwendungsfälle und Vokabulare, die hinter diesen liegen, erweitert werden. Die Frage also, ob etwas eine Instanz oder eine Klasse ist, muss nicht notwendigerweise anhand des Datenmodells selbst zu beantworten sein. Zugleich bedeutet dies aber auch ganz allgemein, dass bestimmte ontologische Beschaffenheiten den untersuchten Entitäten nicht bereits a priori inhärent sind: Entitäten können grundsätzlich – je nach Kontext – mal als Klassen, mal als Instanzen begriffen werden. Diese Unschärfe gilt es sich auch während der folgenden Modellierungen immer wieder prüfend vor Augen zu halten.

OWL2 differenziert, anders als etwa RDFS, nicht lediglich zwischen Klassen und Instanzen, sondern zwischen Klassen und Individuen,[^3] wobei letztere nochmals in *owl:namedIndividual* und *owl:anonymousIndividual* unterschieden werden. Über letztere heißt es: "Named individuals are given an explicit name that can be used in any ontology to refer to the same object. _Anonymous individuals_ do not have a global name and are thus local to the ontology they are contained in."[^4]

Auf den ersten Blick finden sich im Modellentwurf in erster Linie Instanzen:[^1]

* *mimul:1663*
* *ma:klangbeispiel* manifestiert sich in Form eines spezifischen Audiofiles.
* *ma:Person* manifestiert sich in Form einer spezifischen Person (etwa in Gestalt seiner Repräsentation als GND Tp-Datensatz).
* *ma:a'=415Hz* erscheint als Klasse nicht sinnvoll (auch wenn sich Frequenzen weiter subsumieren ließen).
* *ma:natuerlichesStimmungssystem* kann ebenfalls nicht als Klasse verwendet werden. Obwohl es denkbar wäre, die Grundstimmung *ma:inF*als Instanz einer Klasse *ma:natuerlichesStimmungssystem* zu betrachten, ist ein Instrument in F nicht zugleich notwendigerweise in natürlich gestimmt (vgl. etwa das *Englischhorn*).
* Sowohl *ma:ambitus* wie auch die ihn definierenden Töne lassen sich nicht weiter differenzieren.

Über die Sinnhaftigkeit weitere übergeordnete Klassen für die Instanzen zu kreieren, wird an späterer Stelle nochmals zu sprechen sein.


* *ma:inF* läßt sich hingegen als Klasse definieren: Ein Anwendungsfall, in dem etwa die Tonhöhe des ersten Naturtons Aussagen zu Intervallverteilung und Tonhöhen zuließen – die Entität weiter teilbar ist –, lässt sich durchaus vorstellen. Instanzen dieser Klassen wären dann die jeweiligen Grundtöne.
* *rism:corDaCaccia* ist – insbesondere in seinem Verhältnis zu seiner Instanz *mimul:1663* als Klasse zu bewerten.
* Dies trifft auch für die Entität *taxonomie:barockhorn* zu.

Mit RDF in OWL2 ausgedrückt ergibt das den folgenden Zusammenhang:


```
#################################################################
#    Classes
#################################################################

###  ma#inF
<ma#inF> rdf:type owl:Class .

###  rism#corDaCaccia
<rism#corDaCaccia> rdf:type owl:Class .

###  taxonomie#barockhorn
<taxonomie#barockhorn> rdf:type owl:Class .

#################################################################
#    Individuals
#################################################################

###  ma#ambitus
<ma#ambitus> rdf:type owl:NamedIndividual .

###  ma#f
<ma#f> rdf:type owl:NamedIndividual .

###  ma#klangbeispiel
<ma#klangbeispiel> rdf:type owl:NamedIndividual .

###  ma#natuerlichesStimmungssystem
<ma#natuerlichesStimmungssystem> rdf:type owl:NamedIndividual .

###  ma#person
<ma#person> rdf:type owl:NamedIndividual .

###  ma#a''
<ma#a''> rdf:type owl:NamedIndividual .

###  ma#a'=115Hz
<ma#a'=115Hz> rdf:type owl:NamedIndividual .

###  ma#c'
<ma#c'> rdf:type owl:NamedIndividual .

###  ma#d''
<ma#d''> rdf:type owl:NamedIndividual .

###  mimul#1663
<mimul#1663> rdf:type owl:NamedIndividual .
```

## Properties

Analog zu den Entitäten müssen auch die Properties in das Schema des Semantic Webs eingebettet werden. Auch hier geschieht dies, indem sie in der Sprache des Semantic Webs erfasst und als Properties definiert werden. Im Gegensatz zu den Entitäten müssen diese (zumindest im hier behandelten Beispiel) jedoch zunächst nicht klassifiziert werden.[^5]

```
#################################################################
#    Object Properties
#################################################################

###  ma#entsprichtGenau
<ma#entsprichtGenau> rdf:type owl:ObjectProperty .

###  ma#entsprichtUngefähr
<ma#entsprichtUngefähr> rdf:type owl:ObjectProperty .

###  ma#grundstimmung
<ma#grundstimmung> rdf:type owl:ObjectProperty .

###  ma#hoechsterTon
<ma#hoechsterTon> rdf:type owl:ObjectProperty .

###  ma#interpret
<ma#interpret> rdf:type owl:ObjectProperty .

###  ma#klangbeispiel
<ma#klangbeispiel> rdf:type owl:ObjectProperty .

###  ma#klingt
<ma#klingt> rdf:type owl:ObjectProperty .

###  ma#stimmungssystem
<ma#stimmungssystem> rdf:type owl:ObjectProperty .

###  ma#tiefsterTon
<ma#tiefsterTon> rdf:type owl:ObjectProperty .

###  ma#tonvorrat
<ma#tonvorrat> rdf:type owl:ObjectProperty .

###  ma#typ
<ma#typ> rdf:type owl:ObjectProperty .

###  ma#vermutlAbsoluteStimmung
<ma#vermutlAbsoluteStimmung> rdf:type owl:ObjectProperty .
```

**"Dieser Schrittist notwendig, da die Kenntnis der zur Verf ̈ugung stehendenRelationen Voraussetzung f ̈ur die Formalisierung der Klassendurch notwendige und hinreichende Bedingungen im n ̈achstenSchritt ist."**[^15]

# Semantic Web-Anbindung
**terminolomuss evtl. anders aufgezogen werden – mehr Ablauf-orientiert im Kontext mit dem Zeug oben.**

Es liegt nahe, die zuletzt mit den Ontologiesprachen OWL und RDF beschriebenen und somit in das schematisch-ontologische Gefüge von RDF für das Semantic Web handhabbar gemachten Terme in Form kontrollierter Vokabulare zu speichern. Dabei beschränkt sich die "terminologische Kontrolle" hier zunächst auf Maßnahmen, "die direkt oder indirekt der Definition und Abgrenzung von Begriffen"[^7] im allerweitesten Sinne dienen. In diesem Sinne reicht es zu diesem Zeitpunkt – zunächst! – aus, eine einfache Liste der Terme und der – freilich außerordentlich vagen – eben erfolgten Spezifikation ihrer Natur als potentielle "Dinge" im Semantic Web zu erstellen.

Die Funktion terminologischer Kontrolle erfüllen in der Informatik sogenannte *Namespaces*. 

—

# Notizen

Nachdem bereits vorläufige "Domains" in Form von Präfixen (*ma:*, *rism:*, *taxonomie:*, *mimul*) definiert worden waren, scheint es denkbar, die nun mit RDF ausgezeichneten Terme im Internet zu verankern und somit in das Semantic Web einzubetten. 

deutlich machen, dass die Vorgehensweise hier nicht sauber, aber für die Belange der Arbeit ausreichend ist.


wichtig ist auch range zu definieren. kann nur verwendet werden mit ma – wie??? mit rdfs:domain? als rdfs:container definieren (= Liste) und dann sagen, dass sich nur auf die Listen bezieht?

aus gründen der lesbarkeit .rdf und nicht rdf/xml (<- könnte man aber geschwind umwandeln?)

Many namespaces have been created in the context of Semantic Web projects to distinguish the names of classes, properties and individuals defined and/or described by that project from all others. One common approach is to use a namespace URI ending with a hash (`#`) to identify the namespace, in which case the URI _without_ the hash is available to identify the information resource which describes the namespace, that is, the namespace document.

"An URIs kann, abgetrennt durch #, auch ein weiteres Fragment angehängt werden. Die Kombination aus URI und Fragment wird URI-Referenz genannt. URI- Referenzen werden in RDF häufig zur eindeutigen Referenzierung von Ressourcen verwendet und stellen somit eine wichtige Komponente der Semantic-Web-Schichten dar."[^6]

"Wie schon in XML versteht man un- ter einem Vokabular meist eine Zusammenstellung von Bezeichnern mit klar definierter Bedeutung." [@TN_libero_mab21631588, S. 48]

"Oft muss man aber auch vo ̈llig neue URIs bilden. In einem solchen Fall muss man sicherstellen, dass die gewa ̈hlte URI nicht versehentlich anderswo mit anderer Bedeutung zum Einsatz kommt. Eine gute Methode dazu ist es, eine URI zu wa ̈hlen, die sich aus einer Webadresse ableitet, deren Inhalte man selbst kontrolliert. Eine URI, die mit http://springer.com/... beginnt, soll- te demnach nur vom Springer-Verlag eingefu ̈hrt werden. Außerdem ist es in einem solchen Fall mo ̈glich, an der entsprechenden Adresse ein Dokument ab- zulegen, welches die Bedeutung der URI fu ̈r Menschen beschreibt." [@TN_libero_mab21631588, S. 48–49]

"Eine Mo ̈glichkeit ist die Verwendung von URI-Referenzen. Schreibt man z.B. http://de.wikipedia.org/wiki/Othello#URI, dann zeigt dies nicht direkt auf ein existierendes Dokument (da es den Abschnitt ”URI“ auf dieser Seite nicht gibt). Wenn man diese URI-Referenz als URL aufruft, dann erha ̈lt man dennoch die beschreibende Seite fu ̈r diese URI." [@TN_libero_mab21631588, S. 49]

"Eine andere Mo ̈glichkeit ist die Verwendung von Weiterleitungen: auch bei Aufruf einer nicht existierenden URL kann ein Server den Nutzer auf eine alternative Seite weiterleiten. Da das Programm des Nutzers diese Weiterlei- tung wahrnimmt, ist dennoch die Unterscheidung der URIs gewa ̈hrleistet. Die automatische Weiterleitung hat außerdem den Vorteil, dass man entweder eine menschenlesbare HTML-Datei oder eine maschinenlesbare RDF-Datei auslie- fern kann – abha ̈ngig von Informationen in der Anfrage. Dieses Verfahren ist auch als Content Negotiation bekannt." [@TN_libero_mab21631588, S. 49]

"The names in a namespace form a collection [...] There's no requirement that the names in a namespace only identify items of a single type; elements and attributes can both come from the same namespace as could functions and concepts or any other homogeneous or heterogeneous collection you can imagine. The names in a namespace can, in theory at least, be defined to identify any thing or any number of things. [...] A user encountering a namespace might want to find any or all of these related resources. In the absence of any other information, a logical place to look for these resources, or information about them, is at the location of the namespace URI itself. The details of exactly what this means may be subtlely different in different cases, but the general point is clear, as [\[WebArch Vol 1\]](file:///Users/alanriedel/Zotero/storage/VEIFTJE6/nsDocuments.html#webarch) says: It is [Good Practice](http://www.w3.org/TR/webarch/#pr-namespace-documents) for the owner of a namespace to make available at the namespace URI “material intended for people to read and material optimized for software agents in order to meet the needs of those who will use the namespace”."





---

zuvor: Methodik – warum OWL? Protégé!


Auf den ersten Blick finden sich im Modellentwurf sehr wenige Klassen. Lediglich*rism:corDaCaccia* sowie *ma:barockhorn*scheinen eine 

"we usually start by defining classes." [@noy_ontology_nodate, S.7] 

Erstmal Aussagen zu der "ontologischen" Beschaffenheit der Entitäten treffen.

Das heißt in OWL-Form bringen

Es fällt auf, dass es wenige taxonomische Beziehungen gibt. Ist das schlimm? Ist ja keine Ontologie, will also nicht alle Verhältnisse in der Domäne abbilden, sondern nur die, die für den Anwendungsfall: Mapping / Anreicherung. Allerdings evtl. sinnvoll: Modell noch etwas ausweiten (dadurch aussagekräftiger machen): z.B. "natürliches Stimmungssystem" subclassOf "Stimmungssystem"

Es scheint so, dass weitere taxonomische Beziehungen lediglich miteinbezogen werden müssten, wenn es darum ginge, eigens kreierte Entitäten in Beziehung zu allgemeineren, bereits etablierten Konzepten zu stellen und sie somit ins Semantic Web einzubinden.
-> es ist nicht nötig, sich mit diesem ganzen Kram einen abzubrechen!!!!

"One of the greatest challenges when designing a semantic model is determining when something should be modeled as a class and when it should be modeled as an individual."

Dieses Bedenken erscheint im hier verwendeten Beispiel sich zunächst nicht zu bestätigen:

Entitäten stehen zumeinst nicht in taxonomischer Relation zueinander.



was zuerst? man ist, wenn man protege verwendet doch an owl gebunden (bzw. die Differenzierung zwischen Klassen und Instanzen). Ist aber ja eigentlich nicht schlimm.

ok, also erstmal owl




An dieser Stelle gerät man bereits an die Grenzen des Datenmodellentwurfs: rism:corDaCaccia wird in diesem Beispiel als Klasse geführt. Im Sinne einer Disambiguierung ist es daher sinnvoll, mithilfe von owl:equivalentClass eine Äquivalenz auszudrücken. So ergibt sich jedoch durch Inferenzierung eine erste Einschränkung gegenüber dem Entwurf, denn dies bedeutet, dass wenn rism:corDaCaccia ebenfalls eine Instanz ist (also etwa der "Salzburger Stier"), sowohl die Beziehungen 




a = 415 Hz ließe sich auch als Tripel abbilden!



Was sind Klassen, was sind Instanzen?


**heute noch ändern: klingend/notiert ist falsch / Grundstimmung / obertonreine Stimmung / relative Stimmung bleibt?**

---

[^1]: Zur Schreibweise: 

[^2]: Vgl. auch die folgende Aussage "Individual instances are the most specific concepts represented in a knowledge base." (vgl. [@gangler_semantic_nodate, S.18]).

[^3]: [@noauthor_owl_nodate-1]

[^4]: [@noauthor_owl_nodate]

[^5]: OWL2 differenziert zwischen *Object Properties* und *Datatype Properties* (vgl.: [noauthor_owl_nodate-2]). Obwohl etwa *ma:a'=415Hz* prinzipiell auch mit *Datatype Properties* modelliert werden könnte, erscheint diese Detailtiefe für den hier exemplarisch durchgeprobten Anwendungsfall nicht notwendig.

[^6]: [@TN_libero_mab21631588, S. 27–28.]

[^7]: [@TN_libero_mab213864266, S. 128]

[^8]: [@noy_ontology_nodate]
Auch Stuckenschmidt legt diese Vorgehensweise nahe (vgl.: [@alma9913393902586]).

[^9]: Zum Begriff siehe [@ TN_libero_mab213864266, S. 150]

[^10]: Für diese Arbeit spielen insbesondere RDFS ([@ noauthor_rdfs_nodate]) und OWL ([@ noauthor_owl_nodate-3]) eine Rolle.

[^11]: "Individualbegriffe"  [@ stock_wissensreprasentation_2008, S. 84].

[^12]: In "Semantic Web-Sprache" augedrückt, wären das die Klassen *rdfs:class*, *rdfs:instanceOf* und *rdf:property*.

[^13]: Auf eine Übersicht der gängigen Klassen muss an dieser Stelle verzichtet werden.

[^14]: [@TN_libero_mab213864266, S. 151]
[^15]: [@alma9913393902586, S. 166]
[^16]: S. hierzu etwa: [@alma9913393902586, S. 95–99]
[^17]: [@noauthor_owl_nodate-3]
[^18]: 

[^19]:  [@alma9913393902586, S. 146]
[^20]: Vgl.: [@noauthor_rdf_nodate-2]
[^21]: [@national_information_standards_organization_u.s._guidelines_2005, S. 3]