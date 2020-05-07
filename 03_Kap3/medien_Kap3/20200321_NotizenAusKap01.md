Es folgt, wie kann man das technisch umsetzen? – RDF! - warum? Gut beschrieben in Allemang, RDF Primer


Danach weiterer Methodikteil: wie macht man weiter? Also eigentliche


kann man das irgendwie kommunizieren, dass das alles nicht auf den ersten Blick besonders logisch/eingängig erscheint?




[In Kenntnis der praktischen Anforderungen lassen sich in einem Folgeschritt Überlegungen hinsichtlich eines angemessenen Modells für die Wissensrepräsentation bzw. einer sinnvollen Datenstruktur anstellen.
Diese bilden ihrerseits wiederum die Grundlage für die Ausarbeitung]

RDF bei Graphen
Welcher Standard der Wissensrepräsentation macht Sinn?  Konzeptuelle
hier auch: interoperabilität
eignet sich voll gut für verteilte systeme, die übers netz angebunden sind











diskursiv machen irgendwie? Wenn ja, dann wie?

* eigentlich müsste der erste Schritt sein, zu definieren, was man eigentlich modellieren / darstellen will.
*  was gibt es für alternative Ansätze, um so etwas darzustellen? (oder macht das überhaupt Sinn? Gleich sagen es muss RDF sein?)
* warum muss es deshalb RDF sein?
* wie macht man 1 LOD-Anwendungsprofil? <- dazu mit Kompetenzzentrum in Mainz schreiben!

Fragen an Jens:
ist der namespace z.B. rdfs oder ist auch rdfs:class ein namespace?

Vorgehen: ok, rdfs und OWL ist klar, aber wie Vorgehen für andere Vokabulare?



RDFSchema: Was bedeutet in diesem Kontext "Schema"?
"Given this variety of understandings of how schema information can be used in different modeling paradigms, one might wonder whether calling something a schema language actually tells us anything at all! But there is something in common among all these notions of a schema. In all cases, the schema tells us something about the information that is expressed in the system. The schema is information about the data.
How then can we understand the notion of schema in RDF? What might we want to say about RDF data? And how might we want to say it? The key idea of the schema in RDF is that it should help provide some sense of meaning to the data. It accomplishes this by specifying semantics using inference patterns." (Allemang 126)

Erstmal definieren, was Zeug überhaupt ist (Class, property):
"We can see this in action by showing how a set is defined in RDFS. The basic construct for specifying a set in RDFS is called an rdfs:Class. Since RDFS is expressed in RDF, the way we express that something is a class is with a triple—in particular, a triple in which the predicate is rdf:type, and the object is rdfs:Class." (Allemang 127)

rdfs:subPropertyOf <- auch properties hierarchisch ordnen – also werden die Properties dadurch zu Subjekten und Objekten? <- scheint so. vgl. "In RDFS, properties are treated in a way analogous to the treatment of classes, and all the same operations and limitations apply" (Allemang 135)

rdfs:domain
rdfs:range
"In RDFS, domain and range give some information about how the property P is to be used; domain refers to the subject of any triple that uses P as its predicate, and range refers to the object of any such triple." (Alleman 130)
"That is, whenever we specify the rdfs:domain of a property to be some class, we can also infer that the property also has any superclass as rdfs:domain. The same conclusion holds for rdfs:range, using the same argument.
These simple definitions of domain and range are actually quite aggressive; we can draw conclusions about the type of any element based simply on its use in a single triple whenever we have domain or range information about the predicate. As we shall see in later examples, this can result in some surprising inferences.
" (Allemang 133)

rdfs:subPropertyOf zum Mappen verwenden! (vgl. Allemang 137 ff.)

rdfs:Label: <- Darstellung von Strings etwa im Web

personName rdfs:subPropertyOf rdfs:label.

wenn man zuvor definiert hat: :Person1 :personName "James Dean".

Dann würde dank Webclients der Name "James Dean" angezeigt.








"The Web that we are accustomed to is made up of documents that are linked to one another. Any connection between a document and the thing(s) in the world it describes is made only by the person who reads the document. There could be a link from a document about Shakespeare to a document about Stratford-upon-Avon, but there is no notion of an entity that is Shakespeare or linking it to the thing that is Stratford." (Allemang 27)
illustrativ zur Sinnhaftigkeit der Verlinkung von Dingen innerhalb von Datensätzen (= documents)





Federation = merging datasets in 1 triple store
however, not necessarily necessary: "But, in contrast to conventional data-backed web portals, and because of the distributed nature of the RDF store that backs a Semantic Web portal, information on a single RDF-backed web page typically comes from multiple sources. The merge capability of an RDF store supports this sort of information distribution as part of the infrastructure of the web portal. When the portal is backed by RDF, there is no difference between building a distributed web portal and one in which all the information is local. Using RDF, federated web portals are as easy as siloed portals." (Allemang 58)
Es folgt1 Kapitel: "Data Federation"
Folgendes "Summary" sehr gut!



Ganz allgemein: "One of the great powers of the Semantic Web is that information that has been specified by one person in one context can be reused either by that person or by others in different contexts." (Allemang 222)


1 Schwierigkeit Methodik: Verwendung von Vokabularen ist intuitiv. Gibt keine "Regeln"/Verbindliches sehr vage -> Auswertung erfolgt nicht systematisch. Aber muss auch, da Bedeutung insb. dadurch, dass viele eine sprache verwenden (nicht unbedingt messbar).

##### Umwandlung zu LOD:

1. Das Bisschen, was verbindlich ist, umsetzen.
    - Entitäten – classes oder instances?
        - dazu is a


"defining classes in the ontology,  
arranging the classes in a taxonomic (subclass–superclass) hierarchy, 
defining slots and describing allowed values for these slots,  
filling in the values for slots for instances." [@noy_ontology_nodate, S.3] 

" 2)  Ontology development is necessarily an iterative process." [@noy_ontology_nodate, S.4] 