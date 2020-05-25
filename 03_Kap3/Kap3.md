# Modellierung

## Anwendungsmodellierung

Insgesamt erscheint es als sinnvoll, zuerst die bereits in Kapitel #Desiderat angerissenen Anforderungen nochmals zu schärfen und aus ihnen ein Modell zu generieren, das künftig als diskursive Grundlage für die spätere "dokumentationssprachliche" Ausarbeitung herhalten kann. Dies soll in einem zweistufigen Prozess geschehen, in dem zunächst ein informelles Anwendungsmodell generiert wird, aus dem wiederum ein verbindliches Datenmodell in Form eines *ERM*s (Entity Relationship Model) abgeleitet werden kann, das die Grundlage für die RDF-Modellierung bietet.
Dieses Vorgehen gewährleistet außerdem, dass sich das Anwendungsprofil an den tatsächlichen in der Praxis vorgefundenen Erfordernissen ausrichtet und sich nicht etwa "in vorauseilendem Gehorsam" anhand der bereits etablierten Darstellungsmöglichkeiten selbst zensiert und beschneidet. (In Vorgriff auf die terminologische Ausarbeitung heißt dies etwa: domänenspezifische Vokabulare dahingehend zu untersuchen, ob sie in der Lage sind, das Geforderte abzubilden und andernfalls nach Möglichkeiten zu suchen, diese Darstellungsmöglichkeiten selbst zu schaffen.)
Jedoch darf diese scheinbare Übersimplifizierung, die zunächst also jederlei Eindeutigkeit – etwa in Form von Normdaten – vermeidet, keineswegs als solche missverstanden werden. Vielmehr bildet sie die eigentliche Prämisse für spätere grundsätzliche terminologische Anschlussfähigkeit und Interoperabilität, indem sie sich nicht auf bestimmte gebräuchliche Datenstrukturen oder eine bestimmte Domäne fixiert. 

![Datenmodell – Beziehungen ausgedrückt als Verbindungslinien zwischen den umkreisten Entitäten](medien_Kap3/20200320_Datenmodell_Skizze2.png)



### Domäne[^8660]

1) Dies wird etwa im Falle der Entität *BWV 208* deutlich: Das "Label" "BWV 208" referenziert hier die Kantate auf Werkebene und fungiert als Platzhalter[^8650] für eine Expression[^8651] (etwa der in RISM beschriebenen Quelle),[^8649] einer Manifestation[^8652] (etwa einer Edition), oder aber auch eines Exemplars[^8653] (etwa einer, freilich illegal, mit Bleistift eingerichteten Ausgabe in einer Bibliothek).

2) Über die Beziehung "Besetzung" mit der Entität Werk verbunden ist die Entität *Corno da caccia*, im Modell mit dem – willkürlichen – Label "cor da caccia", der Terminologie von RISM folgend, versehend. Auch an dieser Stelle ist das Label völlig flexibel – analog also zur Entität *BWV 208*.

Diese beiden Entitäten sind diejenigen, die herkömmlicherweise – wie im RISM-Datensatz exemplarisch demonstriert – die Erschließungstiefe in den allermeisten Datenbanken ausfüllen.
Die Entitäten dieses Bereichs sind institutions-, sparten-, domänenspezifisch sowie bereits etabliert und stehen daher für dieses Metadatenprofil nicht zur Disposition. Das spätere Datenmodell wird daher an dieser Stelle  keinen präskriptiven Charakter für sich beanspruchen können, und auch eine Weiterentwicklung dieses erscheint hier müßig. -> **darauf zurückkommen und sagen, wo was gemacht werden kann** 

### Mapping

Beim Mapping-Anteil steht einerseits die Vernetzung zwischen Objekt und Werk im Vordergrund, zum anderen kann hier die Disambiguierung unklarer Terminologie erfolgen.
Die Anbindung der Besetzungsentität *Corno da caccia* an die Objekt-Entität – in diesem Fall verkörpert durch ein Objekt des Musikinstrumentenmuseums der Universität Leipzig[^8654] – kann in zweierlei Weise erfolgen:

3) durch ein direktes In-Beziehung-Setzen mit der Entität *Corno da Caccia*. Hier sind mehrere Arten der Beziehung denkbar: 
- Einerseits könnte es sich beim Objekt um exakt jenes handeln, das Bach für das Werk besetzt hatte.[^8655].
- In den meisten Fällen jedoch wird eine dermaßen eindeutige Beziehung nicht nachzuvollziehen sein. Vielmehr wird – wie ja auch im Falle von BWV 208 – auf ein ungefähres Äquivalent zu verweisen sein.

4) durch das Mapping über eine zwischengelagerte Klassifikation. Dieses erscheint etwa im hier verwendeten Falle sinnvoll, um den Term "cor da caccia" weiter zu disambiguieren. **für die Zukunft: wenn man mit MIMO verlinkt, kann der Typ inferenziert werden (MIMO-Thesaurus)!!** Unsinnig erscheint dieser Ansatz hingegen, wenn im Bereich der Domäne ein maschinenlesbares und bereits gemapptes Standardvokabular (etwa GND, IAML MoP etc.) Verwendung findet – auch wenn diese mitunter, wie bereits erwähnt, mitunter sehr zu wünschen übrig lassen.

### Anreicherung

Nachdem die Besetzungsentität durch Verknüpfung mit einem Objekt bzw. einer Klassifikation eindeutig bestimmt worden ist, ist es wünschenswert, sie durch weitere Aussagen anzureichern und dadurch noch aussagekräftiger zu machen.

5) Die Hörner sind im Autograph "in F" notiert – der tatsächliche Klang der in F notierten Töne der Hornstimme liegt also eine Quinte tiefer. Dies wird durch die Beziehung der Besetzungsentität zu ihrer relativen Stimmung "in F" ausgedrückt. Auch für das Objekt könnte bekannt sein, dass es in F gestimmt ist (= das Instrument produziert Töne der sog. *Naturtonreihe* über dem Ton *f*), was im hier behandelten Szenario jedoch nicht der Fall ist.[^8656]

> Aus diesem Umstand lassen sich – zumindest für die Zeit bis zur Erfindung des Ventilhorns – sehr facettierte Aussagen zum vorgesehenen Instrument treffen (Länge, Mensur etc.), deren Darstellung jedoch für den begrenzten Rahmen dieser Arbeit keine Rolle spielen kann. Außerdem liefert die Angabe der Stimmung der Hörner – ebenfalls begrenzt auf die Zeit bis zur Erfindung des Ventilhorns – einen Indikator für die Bestimmung der Tonart (wie auch im Fall von BWV 208: Die Kantate steht in F-Dur).

6) Der Besetzungsentität ist in ihrer Eigenschaft als Besetzung für *BWV 208* ein bestimmter Tonvorrat zu eigen, der sich durch die Entität *Ambitus* ausdrückt. Dieser wiederum setzt sich aus einer Tonmenge zusammen, die durch die beiden Entitäten des höchsten und des tiefsten Tons eingegrenzt wird.

>Die Kenntnis des Ambitus' lässt in wissenschaftlicher Hinsicht vielerlei Rückschlüsse zu: etwa auf die Länge des Instruments (Faustregel: kürzer = Tonvorrat liegt höher). Für Musiker (etwa Anfänger) kann diese Information selbstverständlich bei der Suche nach Noten ebenfalls außerordentlich nützlich sein.

7) Im in dieser Arbeit gewählten Szenario ist aus physikalischen Gründen das Stimmungssystem des *Corno da caccia* eindeutig und kann hier berücksichtigt werden.[^8657] Tatsächlich ist das Bestimmen historisch verwendeter Stimmungssysteme in vielen Fällen weit weniger eindeutig.

8) Über die absolute Stimmung der ursprünglich vorgesehenen Instrumente, wie auch für das Objekt *MIMUL 1663* selbst, lässt sich keine eindeutige Aussage treffen. Gleichwohl ist diese Entität grundsätzlich durchaus als aufschlussreich für die Wissenschaft anzusehen.[^8658] Somit handelt es sich bei der Angabe *a* = 415 Hz um einen vermuteten Wert, und es ergibt sich für den Fortgang der Arbeit die Frage, ob es in einem späteren Datenmodell auch möglich sein wird, auch Ambivalenzen und Unsicherheiten dieser Art abzubilden.

9) Über die Beziehung "Klangbeispiel" ist es möglich, die Objektentität oder die Typ-Entität mit einem Klangbeispiel zu verknüpfen. Selbstverständlich wäre dies im gleichen Maße auch für eine Werkentität denkbar.

10) Denkbar ist, dass eine Person – etwa im Rahmen einer Audioaufnahme – auf einem bestimmbarenen Instrument spielt. Hier wäre also eine Verknüpfung zwischen Besetzung (evtl. Werk), Person und Objekt nützlich.

Tatsächlich sind den potentiellen Anwendungsszenarien eines solchen Modells keine Grenzen gesetzt. Angesichts der Komplexität und der vielfältigen spezifischen Anforderungen, die trotz der Beschränkung auf BWV 208 und das *Corno da caccia* erarbeitet wurden, lässt sich bestenfalls erahnen, welches Darstellungspotential eine Erweiterung des Modells für andere Instrumente und Instrumentengruppen bergen könnte: Es ließe sich etwa die Skordatur von Saiten ausdrücken. Oder verschiedene Sing- und Spieltechniken – vom Jodeln bis zum Spiel *con sordino* etc.

Eine zentrale Erkenntnis des vorangehenden Kapitels war die Einteilung der Entitäten und Beziehungen in drei verschiedene Bereiche, die bereits in den Zwischenüberschriften vorweggenommen wurden:

1. Domäne
2. Mapping und Disambiguierung
3. Anreicherung

Während der Bereich der Domäne für diese Arbeit unantastbar bleiben muss, konnte der Fokus der Arbeit und somit die Funktion eines zu entwickelnden Metadatenprofils auf die Punkte

* Mapping und Disambiguierung

sowie

* Anreicherung

gebündelt werden.

![Funktionsbereiche](medien_Kap3/20200321_datenmodell_skizze.png)


## Klassifikatorische Erschließung [umbenennen?]


Das folgende Kapitel bildet den Ausgangspunkt dafür, den Weg von einem Anwendungsszenario zu einem Semantic Web-kompatiblen Metadatenprofil zu beschreiten. [vielleicht noch etwas darüber, dass es keine wirkliche Lit. gibt, die einen Leitfaden von Anfang bis Ende bildet] Gemäß Noy und McGuinness[^8] steht dabei ganz zu Beginn des Prozesses hin zur Ontologie zunächst eine Klassierung[^9] der benötigten Typen nach folgendem Schema:

> "Define the classes and the class hierarchy"

> "Define the properties of classes [...]"

> "Create instances"

Das Produkt dieser Vorgehensweise bildet, wie oben angedeutet, eine zunächst auf den Anwendungsbereich beschränkte "Ontologie", die nicht mit den Sprachen des Semantic Web ausgezeichnet ist.
Tatsächlich hat sich im Verlauf dieser Arbeit ganz organisch eine andere Reihenfolge ergeben: Nach dem exemplarischen Auffinden eines Defizits wurde ein spezifisches Szenario entworfen, um dieses zu beheben: Einige wichtige Instanzen[^11] wurden bereits im vorhergehenden Kapitel identifiziert und aufgeführt.

#### Entity Relationship Model [es muss klar werden, dass das nur eine Hilfestellung ist – die aber nicht kompatibel mit RDF ist]

Ein erster möglicher Schritt in Richtung einer Modellierung mit RDF ist die Überführung des Anwendungsmodells in ein Hilfskonstrukts in Form eines *Entity Relationship Models* (ERM). Hierbei sollen die anwendungsspezifischen Szenarien strukturiert und auf eine allgemeine Ebene gesetzt werden, auf der übergeordnete Entitätsklassen und ihre Eigenschaften in Beziehung zueinander stehen.[^8661] So werden Klassen definiert und erste einfache hierarchische Relationen zwischen Klassen und untergeordneten, "beschreibenden" Klassen (Eigenschaften) hergestellt.

Beziehungen ("properties" s.o.) wiederum können in diesem ERM ebenfalls zunächst als potentielle zukünftige "Eigenschaftsklassen" verstanden werden, die zukünftig Container für weitere "Untereigenschaften" darstellen können.[^8668]
Im ERM fungieren besondere Schlüsseleigenschaften ("Primärschlüssel") als eindeutige Identifier einer Entität. Es ist zu erwarten, dass diese in einer RDF-Modellierung keine Rolle spielen werden, da dort eindeutige Referenzierbarkeit bereits dank URIs gegeben ist. [^8662] Mengenverhältnisse zwischen Entitäten werden im ERM zudem durch "Kardinalitäten" miteinbezogen und dadurch fixierbar.[^8663] 

![Entity Relationship Modell: farbige Markierung der externen Vokabulare. Entitäten stehen in Rechtecken, Eigenschaften in Ovalen, Beziehungen in Rauten. Schlüsseleigenschaften sind durch Unterstreichung gekennzeichnet.](medien_Kap3/20200507_ERM2.png)

Einige wesentlichen Entwicklungen gegenüber dem Anwendungsmodell sowie weitere Überlegungen sind es wert, nochmals kurz erläutert und erörtert zu werden.

* Wie bereits erwähnt sind den Entitäten des ERM gegenüber denen der Anwendungsmodellierung weitere sie beschreibende Eigenschaften hinzugefügt worden (etwa *Name* zu *Person*)

* Neben dem verwendeten Instrument *Instrument nach Vokabular (Domäne)* muss die Entität *Interpret* auch immer an ein Ereignis, in der Regel eine *Aufführung* geknüpft sein (diesem Umstand wurde durch die Zusätze im linken Domänenbereich Rechnung getragen). Dabei sind folgende Szenarien berücksichtigt: ein *Instrument* kann sowohl mehrfach ("n Mal") mit beliebig vielen *Interpreten* besetzt sein (entspricht beispielsweise der Bezeichnung "2 Oboen" oder "Celli" in einer Partitur) als auch gesondert aufgeführt werden (entspricht etwa dem Sachverhalt "Musiker a und Musiker b spielen vierhändig Klavier").

* Ein *Instrument nach Vokabular (Domäne)* kann innerhalb eines Werks beliebig viele notierte *Stimmungen* besitzen.[^8665]. Die Bedeutung der Entität *Stimmung* – etwa mit dem Wert "F" – weicht dabei in der Kombination mit *Instrument* von der der Verwendung in Kombination mit *Objekt (Domäne)* ab: In dieser Kombination bezieht sich die Entität *Stimmung* auf die mögliche "Grundstimmung" eines Objekts (z.B. F-Horn), sofern es eine besitzt.[^8666]

* Mithilfe einer Kombination gegebener Informationen zu *Stimmung* und *notiertem Ambitus* sollte es im Zuge eines späteren Schrittes möglich sein, Informationen zu den *klingenden Tönen* maschinell abzuleiten.

* Im ERM ist definiert, dass ein *Instrument nach Vokabular (Domäne)* nur eine (variable) *absolute Stimmung* besitzen kann. Denkbar wären jedoch auch z.B. Sachverhalte – Konzerte, Aufnahmen etc. – in deren Verlauf mehrmals umgestimmt wird. In diesen Fällen wäre auch eine Verknüpfung mit der Entität *Aufführung* angebracht.[^8664]

* Grundsätzlich ist wünschenswert – wie im Fall des *Interpreten* oder dem Umstimmen von Instrumenten – bestimmte Entitäten mit Ereignissen verknüpfen zu können. Dies gilt insbesondere für die Entitäten *Stimmungssystem* (wird mit historisch akkurater gespielt, oder wohltemperierter Stimmung gespielt?) , *Kammerton* (wird mit den heute üblichen 440 Hz musiziert, oder mit einer historischen Stimmung, z.B. gemäß dem sog. *Cornettton*[^8667]?), *Klangbeispiel* (Das Klangbeispiel stammt aus der und der Aufnahme) und *Instrument (Klassifikation)* (bei der Uraufführung fand Instrument a Verwendung, in der Aufnahme x ein typverschiedenes). 

Für die Zwecke dieser Arbeit ist es ausreichend, die zuletzt genannten Anwendungsszenarien im ERM lediglich einmal exemplarisch im Kontext des *Interpreten* anzudeuten.










**Konzept als Oberbegriff zu  Property, class usw. verwendet – gut? RDF: statt Konzept allg. Ressource verwendet**
**Entität als Oberbegriff zu class, instance?**



Notizen Methodik

2 große Sachen folgen: 
1) die Klassifikation mit RDF

2) die Umwandlung der unspezifischen Beziehungen zu semantisch festgelegten mit OWL

3) Die Anbindung ans Semantic Web durch Austausch entsprechender etablierter Terme bzw. die Verbindung zu ähnlichen Konzepten – z.B. ma:natürliche Stimmung a gnd:Stimmungssystem – oder so
= "Einfügen dieser Entitäten in die Architektur des Semantic Webs"


 Literatur bezieht sich eigentlich fast nie auf das Technische, das man braucht, um selbst Daten zu publizieren.
 darunter: Noy, Allemang, Schneckengruber


## Klassifikation und Transformation mit RDF, RDFS und OWL

Das zuletzt ausgearbeitete Modell befindet sich gewissermaßen noch außerhalb des Erkenntnishorizonts des Semantic Web. Diesen Erkenntnishorizont zu überwinden und eine minimale semantische – wenn auch zunächst nicht primär eine technische – Anschlussfähigkeit zu erreichen, ist Anliegen dieses Kapitels. Dazu wird es gelten, die Konzepte des ERM nochmals zu hinterfragen.

Der Vorgehensweise im weiteren Verlauf liegt zugrunde, dass in RDF bereits bestimmte Klassen angelegt sind – in Folgevokabularen[^10] um weitere ergänzt –, die verwendet werden können, um Konzepte zu klassifizieren.[^13] Dabei erscheinen angesichts der zuvor ausgearbeiteten Anwendungsmodellierung die allgemein gebräuchlichsten drei Klassen[^12] für die Zwecke dieser Arbeit ausreichend. Diese sind:

1. Klassen

2. Instanzen

3. Relationen (im Folgenden auch Properties) [Relationen? vg. Stuckschmidt 11]

Es mag an dieser Auflistung auffallen, dass in RDF das Konzept von Attributen gegenüber dem ERM keine ausgezeichnete Klasse mehr bildet. Dies ist unmittelbar einleuchtend, kann doch jede RDF-Entität auch als Subjekt eines Tripels agieren (somit erscheint das von seiner Bezugsentität abhängige und auf ihn verweisende Attribut mit RDF inkompatibel).
Durch die Aufteilung in (theoretisch also gleichgestellte) Entitäten und Beziehungen lassen sich bereits vollwertige RDF-Tripel bilden – zusätzlich gelingt es, dank der qualitativen Unterscheidung in Instanz und Klasse, einfache hierarchische Sachverhalte nachzubilden. In den folgenden Unterkapiteln wird es entsprechend darum gehen, eine entsprechende Klassierung am Gegenstand der erarbeiteten Konzepte vorzunehmen.

Doch worin besteht an dieser Stelle der tiefere Sinn einer Klassifikation? Direkt assoziativ ist die Funktion des Klassierens – sofern man sie nicht als reinen Selbstzweck betreibt – insbesondere mit der Ordnung von Ressourcen und deren Retrieval. Doch neben dieser "pragmatischen Aufgabe"[^23] führt Bertram auch die "erkenntnisvermittelnde Aufgabe" von Klassifikationen ins Feld, die in der "Aufhellung von Zusammenhängen anhand geordneten Wissens" besteht.[^14] Diese so angedeutete hermeneutische Dimension erscheint auch bei der RDF-Klassifizierung ganz zentral: Das Modell, das in seiner gegenwärtigen Form auf einem subjektiv geprägtem Verständnis, Wertesystem und persönlichen Denkstrukturen des Autors beruht, wird in ein objektives, standardisiertes System überführt. Gewissermaßen findet so eine Übersetzung statt, die den Erkenntnishorizont zwischen Mensch und Maschine überwindet. Das eigene Denkmodell wird dabei mithilfe der formalsprachlichen Ausdruckmittel des Semantic Web erfasst und ausgezeichnet, und so in das von RDF-vorgegebene Erkenntnisschema einsortiert. Die dem Modell inhärente Semantik wird – wie zu sehen sein wird freilich zunächst auf einer sehr oberflächlichen Ebene – dadurch objektiviert und gemeinhin auslegbar.

Diese Übersetzung geht mithilfe entsprechend standardiserter, sich ergänzender Modellierungssprachen, den sogenannten "Ontologiesprachen", vonstatten.[^16] 
Die durch den W3C standardisierten Grundpfeiler des Semantic Web bilden dabei insbesondere die Sprachen RDF (Ressource Description Framework),[^8675] RDFS (RDF Schema)[^8676] und OWL (Web Ontology Language[^17], der "inzwischen [...] meistbenutzen Ontologiesprache aller Zeiten"[^19].

Die formale Interpretierbarkeit der durch die Sprache ausgedrückten semantischen Komponente wird durch eine Syntax, also einer  "Menge von Regeln, um Programme oder Dokumente mit bestimmten Eigenschaften [...] zu erzeugen",[^8677] ermöglicht. Die Entscheidung für eine bestimmte Syntax ist dabei im Falle nach RDF strukturierter Daten zwar letztlich arbiträr, bilden sie doch im übertragenen Sinne gewissermaßen lediglich "Verpackung und Beipackzettel" für den eigentlichen semantischen Inhalt. Doch fällt aufgrund seiner Einfachheit und Übersichtlichkeit in dieser Arbeit die Wahl auf das sogenannte *Turtle*-Format ("Terse RDF Triple Language")[^20].

Dabei erfolgt die Disambiguierung der Lemmata analog zur Klassifizierung in folgender Form (s. auch Kapitel #klassenundinstanzen):

* "Typ ist eine Klasse"

* "Typ ist eine Instanz"

* "Typ ist eine Eigenschaft"[^5] 

Durch die klassifikatorische Erfassung der Instanzen, Entitäten und Beziehungen aus der Anwendungsmodellierung bzw. der Klassen, Eigenschaften und Beziehungen des ERM ergibt sich ein sehr einfaches kontrolliertes Vokabular – etwa im sehr grob gefassten Sinne des *National Information Standards Organization* und des *American National Standards Institute*.[^21] Durch die Zuordnung von Instanzen zu Klassen ergeben sich zudem erste taxonomische Beziehungen – hier wie gesagt in Turtle serialisiert.[^24] 
Vermöge der Klassifizierung mithilfe der Eigenschaft
```
rdf:type
``` 
werden zudem ontologische Aussagen zu den Einzelkonzepten getroffen. So werden alle konzeptuell-kategorialen Verhältnisse innerhalb des Erkenntnishorizonts des Semantic Web formalsprachlich übersetzt und verstehbar.

### Vokabular

```


##########################
#    Header
##########################

@prefix ma: <https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma#> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xml: <http://www.w3.org/XML/1998/namespace> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@base <https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma#> .

<https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma> rdf:type owl:Ontology  ;
            dc:title "Vocabulary for my M.A. thesis" ;
            dc:date "2020-05-09" ;
            owl:versionInfo "draft" ;
            dc:description "An RDF classification of relevant terms intended for building an application profile linking music instrument related entities. Reuse highly discouraged." .

#################################################################
#    Object Properties
#################################################################

###  ma#Entsprechungsgrad
<ma#Entsprechungsgrad> rdf:type owl:ObjectProperty .


###  ma#Identifikator
<ma#Identifikator> rdf:type owl:ObjectProperty .


###  ma#Interpret
<ma#Interpret> rdf:type owl:ObjectProperty .


###  ma#Typ
<ma#Typ> rdf:type owl:ObjectProperty .


###  ma#entspricht
<ma#entspricht> rdf:type owl:ObjectProperty .


###  ma#genaue_Entsprechung
<ma#genaue_Entsprechung> rdf:type owl:ObjectProperty ;
                         rdfs:subPropertyOf <ma#Entsprechungsgrad> .


###  ma#hat_Ambitus
<ma#hat_Ambitus> rdf:type owl:ObjectProperty .


###  ma#hat_Dauer
<ma#hat_Dauer> rdf:type owl:ObjectProperty .


###  ma#hat_Format
<ma#hat_Format> rdf:type owl:ObjectProperty .


###  ma#hat_Frequenz
<ma#hat_Frequenz> rdf:type owl:ObjectProperty .


###  ma#hat_Klangbeispiel
<ma#hat_Klangbeispiel> rdf:type owl:ObjectProperty .


###  ma#hat_Lebensdaten
<ma#hat_Lebensdaten> rdf:type owl:ObjectProperty .


###  ma#hat_Lizenz
<ma#hat_Lizenz> rdf:type owl:ObjectProperty .


###  ma#hat_Namen
<ma#hat_Namen> rdf:type owl:ObjectProperty .


###  ma#hat_Ort
<ma#hat_Ort> rdf:type owl:ObjectProperty .


###  ma#hat_Signatur
<ma#hat_Signatur> rdf:type owl:ObjectProperty .


###  ma#hat_Stimmungssystem
<ma#hat_Stimmungssystem> rdf:type owl:ObjectProperty .


###  ma#hat_Zeitpunkt
<ma#hat_Zeitpunkt> rdf:type owl:ObjectProperty .


###  ma#hat_höchsten_Ton
<ma#hat_höchsten_Ton> rdf:type owl:ObjectProperty .


###  ma#hat_tiefsten_Ton
<ma#hat_tiefsten_Ton> rdf:type owl:ObjectProperty .


###  ma#in_Sammlung
<ma#in_Sammlung> rdf:type owl:ObjectProperty .


###  ma#klingt
<ma#klingt> rdf:type owl:ObjectProperty .


###  ma#ungefähre_Entsprechung
<ma#ungefähre_Entsprechung> rdf:type owl:ObjectProperty ;
                            rdfs:subPropertyOf <ma#Entsprechungsgrad> .


###  ma#Ereignis_(Domäne)
<ma#Ereignis_(Domäne)> rdf:type owl:ObjectProperty .


###  ma#hat_Besetzung_(Domäne)
<ma#hat_Besetzung_(Domäne)> rdf:type owl:ObjectProperty .


###  ma#hat_ID_(WerkVZ)
<ma#hat_ID_(WerkVZ)> rdf:type owl:ObjectProperty .


###  ma#hat_ID_(intern)
<ma#hat_ID_(intern)> rdf:type owl:ObjectProperty .


###  ma#hat_Stimmung_(absolut)
<ma#hat_Stimmung_(absolut)> rdf:type owl:ObjectProperty .


###  ma#hat_Stimmung_(notierte)
<ma#hat_Stimmung_(notierte)> rdf:type owl:ObjectProperty .


###  ma#hat_Stimmung_(relativ)
<ma#hat_Stimmung_(relativ)> rdf:type owl:ObjectProperty .


#################################################################
#    Classes
#################################################################

###  ma#Ambitus
<ma#Ambitus> rdf:type owl:Class .


###  ma#Dauer
<ma#Dauer> rdf:type owl:Class .


###  ma#Format
<ma#Format> rdf:type owl:Class .


###  ma#Frequenz
<ma#Frequenz> rdf:type owl:Class .


###  ma#Identifikator
<ma#Identifikator> rdf:type owl:Class .


###  ma#Kammerton
<ma#Kammerton> rdf:type owl:Class ;
               rdfs:subClassOf <ma#Ton> .


###  ma#Klangbeispiel
<ma#Klangbeispiel> rdf:type owl:Class .


###  ma#Lebensdaten
<ma#Lebensdaten> rdf:type owl:Class .


###  ma#Lizenz
<ma#Lizenz> rdf:type owl:Class .


###  ma#Name
<ma#Name> rdf:type owl:Class .


###  ma#Ort
<ma#Ort> rdf:type owl:Class .


###  ma#Person
<ma#Person> rdf:type owl:Class .


###  ma#Sammlung
<ma#Sammlung> rdf:type owl:Class .


###  ma#Signatur
<ma#Signatur> rdf:type owl:Class .


###  ma#Stimmung
<ma#Stimmung> rdf:type owl:Class .


###  ma#Stimmungssystem
<ma#Stimmungssystem> rdf:type owl:Class .


###  ma#Ton
<ma#Ton> rdf:type owl:Class .


###  ma#Zeitpunk
<ma#Zeitpunk> rdf:type owl:Class .


###  ma#cor_da_caccia
<ma#cor_da_caccia> rdf:type owl:Class ;
                   rdfs:subClassOf <ma#Instrument_nach_Vokabular_(Domäne)> .


###  ma#höchster_Ton
<ma#höchster_Ton> rdf:type owl:Class ;
                  rdfs:subClassOf <ma#Ton> .


###  ma#tiefster_Ton
<ma#tiefster_Ton> rdf:type owl:Class ;
                  rdfs:subClassOf <ma#Ton> .


###  ma#Aufführung_(Domäne)
<ma#Aufführung_(Domäne)> rdf:type owl:Class .


###  ma#Barockhorn_(Mitteldeutschland)
<ma#Barockhorn_(Mitteldeutschland)> rdf:type owl:Class ;
                                    rdfs:subClassOf <ma#Instrument_(Klassifikation)> .


###  ma#ID_(WerkVZ)
<ma#ID_(WerkVZ)> rdf:type owl:Class .


###  ma#ID_(intern)
<ma#ID_(intern)> rdf:type owl:Class .


###  ma#Instrument_(Klassifikation)
<ma#Instrument_(Klassifikation)> rdf:type owl:Class .


###  ma#Instrument_nach_Vokabular_(Domäne)
<ma#Instrument_nach_Vokabular_(Domäne)> rdf:type owl:Class .


###  ma#Objekt_(Domäne)
<ma#Objekt_(Domäne)> rdf:type owl:Class .


###  ma#Ton_(klingend)
<ma#Ton_(klingend)> rdf:type owl:Class ;
                    rdfs:subClassOf <ma#Ton> .


###  ma#Werk_(Domäne)
<ma#Werk_(Domäne)> rdf:type owl:Class .


#################################################################
#    Individuals
#################################################################

###  ma#BWV_208
<ma#BWV_208> rdf:type owl:NamedIndividual ,
                      <ma#Werk_(Domäne)> .


###  ma#MIMUL_1663
<ma#MIMUL_1663> rdf:type owl:NamedIndividual ,
                         <ma#Signatur> .


###  ma#MIMUL_Inv.-Nr._1663
<ma#MIMUL_Inv.-Nr._1663> rdf:type owl:NamedIndividual ,
                                  <ma#Objekt_(Domäne)> .


###  ma#Person_a
<ma#Person_a> rdf:type owl:NamedIndividual ,
                       <ma#Person> .


###  ma#Track_No_2
<ma#Track_No_2> rdf:type owl:NamedIndividual ,
                         <ma#Klangbeispiel> .


###  ma#f
<ma#f> rdf:type owl:NamedIndividual ,
                <ma#Ton_(klingend)> .


###  ma#in_F
<ma#in_F> rdf:type owl:NamedIndividual ,
                   <ma#Stimmung> .


###  ma#natürliches_Stimmungssystem
<ma#natürliches_Stimmungssystem> rdf:type owl:NamedIndividual ,
                                          <ma#Stimmungssystem> .


###  ma#a''
<ma#a''> rdf:type owl:NamedIndividual ,
                  <ma#höchster_Ton> .


###  ma#a'_=_415_Hz
<ma#a'_=_415_Hz> rdf:type owl:NamedIndividual ,
                          <ma#Kammerton> .


###  ma#c'
<ma#c'> rdf:type owl:NamedIndividual ,
                 <ma#tiefster_Ton> .


###  ma#d''
<ma#d''> rdf:type owl:NamedIndividual ,
                  <ma#Ton_(klingend)> .

              
```

#### Bemerkungen zum Vokabular

##### Namensraum

Auch wenn keine abschließenden Definitionen der hier geschaffenen Terme erstellt worden sind, lässt sich bereits jetzt die sehr allgemeine Aussage treffen, dass ihr semantischer Gehalt sich darin ausdrückt, wie sie in dieser Arbeit Verwendung finden. Es ist möglich, diese freilich bislang nicht im Einzelnen aussagekräftige, doch trotzdem in so fern definierte und abgrenzbare semantische Reichweite von Vokabular im Bezug zu sogenannten*Namensräumen*[^8670] – referenzierbare kontrollierte Vokabulare – festzulegen. Die Namensraumzugehörigkeit der Terme dieser Arbeit wird im Folgenden zunächst durch das Präfix *ma:* gekennzeichnet. Der Namensraum ist am folgenden Ort, 

 https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma,

hinterlegt.

Eine menschenlesbare Definition der einzelnen Terme, wie sie als gute Praxis gemäß dem W3C (*World Wide Web Consortium*) nahegelegt wird,[^8673] wäre zum gegenwärtigen Zeitpunkt noch verfrüht.

##### Instanzen (owl:NamedIndividuals) und Klassen (owl:Class, rdfs:subClassOf)

Die bei der Differenzierung zwischen Klasse und Instanz (owl:NamedIndividual)[^8672] oftmals  vorgeschlagene Vorgehensweise,[^2] bei der die niedrigste Entität eines aus Klassen bestehenden hierarchischen Strangs als Instanz zu werten ist, mag im Falle einer in sich abgeschlossenen Ontologie als  sinnvoll erscheinen. Doch muss der Blickwinkel im Fall der hier beabsichtigten Anwendung als verbindendes Metadatenprofil auch auf potentielle Anknüpfungspunkte, aber vor allem auf die Anwendungsfälle und Vokabulare, die gewissermaßen "außerhalb" des Profils liegen, erweitert werden. Die Frage also, ob etwas eine als Instanz oder eine Klasse zu verstehen ist, liegt nicht notwendigerweise in der hierarchischen Ebene begründet. Im Falle des *Barockhorns* wird dies insbesondere deutlich:
```
ma:Barockhorn_(Mitteldeutschland) rdf:type owl:Class ;
                                    rdfs:subClassOf ma:Instrument_(Klassifikation) .
```
Es ist einleuchtend, dass die Bestimmung einer Klasse (Barockhorn) als Instanz, auch wenn sie sich auf der untersten hierarchischen Ebene befindet, unsinnig ist.

##### Identifier

Während in einer relationalen Datenbank das Schlüsselattribut einer Entität variabel sein kann, erfolgt die eindeutige Referenzierung von Konzepten – darunter auch Entitäten – im Semantic Web grundsätzlich anhand von URIs (Uniform Ressource Identifier).[^8671] Eine konzeptuelle Trennung zwischen Entität und seinem eindeutigen Identifier, wie im ERM, ist im Semantic Web nicht denkbar: Die URI selbst erscheint vielmehr gewissermaßen als digitale Manifestation des durch sie repräsentierten nichtdigital existierenden Konzepts. URIs sind also im Gegensatz zur Repräsentation im ERM keine eigenständigen Konzepte mehr, sondern sie "sind" die Konzepte:

Bei den syntaktischen Elementen der Aussage
```
ma:Klangbeispiel rdf:type owl:Class .
```

etwa sind die Konzepte mit ihrem jeweiligen Namensraum präfigiert und über den Header der Datei zu vollständigen URIs auflösbar.



##### Attribute und Properties

Ein Nebeneffekt der Transformation des ERM nach RDF ist, dass Attribute von Entitäten von diesen als nunmehr eigenständige Entitäten entkoppelt sind, und somit dem ERM entsprechende Tripelbeziehungen nicht möglich sind. Dieses Problem lässt sich in der Regel einfach lösen, indem Properties  gemäß den Schema

```
ma:hat_[Attribut]
```

erschaffen werden.

##### Weitere Anmerkungen

* Analog zur Defintion von Klassen (owl:Class) und Unterklassen (rdfs:subclassOf) ist es mit *rdfs* möglich, Untereigenschaften (rdfs:subPropertyOf) zu Eigenschaften zu bilden.[^8674] Dies ist im Falle der Eigenschaften *genaue Entsprechung* und *ungefähre Entsprechung* nützlich, indem sie der Eigenschaft *Entsprechungsgrad* subsumiert werden.
* Sonderzeichen, die mit der Turtle-Syntax inkompatibel sind, wurden mit dem "escape character" `\` maskiert.



## Vom Vokabular zur "Lightweight Ontology" – Spezifizierung von Relationen mit *rdfs:range* und *rdfs:domain*

Eines der zentralen Konzepte des Semantic Webs ist die sog. *open world assumption*.[^8682] Gemäß dem vielzitierten Leitsatz "Anyone can say anything about anything"[^8678] besagt sie, dass eine Aussage, die in einem Modell nicht explizit verankert ist, nicht notwendigerweise falsch sein muss, sondern dass lediglich keine Aussage über ihre Richtigkeit getroffen werden kann.[^8679] Es muss somit im Interesse eines RDF-Vokabulars liegen, sein semantisches Ausdruckspotential fort von der Summe alles Möglichen (und somit Willkürlichen) hin zum eigentlich Aussagekräftigen fokussieren zu können, indem es Hinweise zur sinnhaften Verwendung seiner Terme bereithält. Die Möglichkeit einer solchen Fokussierung bieten Ontologiesprachen wie RDFS und OWL, indem sie in RDF formalisierte und somit direkt integrierbare "Anwendungsregel" zu Properties anbieten.[^8680]
Es liegt dabei auf der Hand, dass für ein Applikationsprofil, dessen Sinn darin besteht, schematische Rahmenbedingungen zu schaffen, entlang derer sich Anwender ausrichten und orientieren können, ein hohes Maß an semantischer Fixiertheit insbesondere unabdingbar ist.

Doch werden kraft dieser Schemata keineswegs lediglich die Wirkungsweite von Relationen abgesteckt. Vielmehr entsteht durch sie eine weitere Bedeutungsdimension, die die Grundlage dafür bietet, auch maschinell inhärente logische Schlussfolgerungen (Inferenzen) ziehen zu können (Reasoning).[^8681]

Während im Vokabular Properties in Form kontingenter, semantisch ungerichteter Bestandteile einer Liste aufgezählt waren, kann im Folgenden ihre Anwendung in Abhängigkeit zu den durch sie in Relation gesetzten Entitäten näher beschrieben werden.[^33] Diesen Schritt zu vollziehen, ermöglichen die Properties *rdfs:range*[^31] und *rdfs:domain*[^32].[^27]

1) Die Wirkung dieser begrenzenden Properties wird im folgenden Beispiel verdeutlicht:

Obwohl die Aussage
```
ma:Person_a ma:hat_Frequenz ma:Lizenz .
```
angesichts der *open world assumption* legitim ist, ist es sinnvoll die Anwendung von `ma:hat_Frequenz` für das Profil, gemäß Anwendungsmodell, nur auf bestimmte Subjekte und Objekte zu beschränken.
Im Szenario 
```
ma:a\' ma:hat_Frequenz ma:415Hz .
```
bezieht sich `ma:hat_Frequenz` auf ein Subjekt aus der Klasse `ma:Ton` (es ist zudem bekannt, dass auch andere Töne Frequenzen besitzen). Zum anderen auf ein Objekt der Klasse Frequenz (mit weiteren möglichen Instanzen, wie 415 Hz etc.).
Somit lässt sich mit der Zuweisung 
```
ma:hat_Frequenz rdfs:domain ma:Ton ;
ma:hat_Frequenz rdfs:range ma:Frequenz .
```
bestimmen, dass im Profil das Property mit einem Subjekt aus der Klasse `ma:Ton` und einem Objekt aus der Klasse `ma:Frequenz` verwendet werden sollte.

Diese Beschränkungen werden dabei, wie bereits kurz angedeutet, in folgender Form direkt in das Vokabular integriert (dabei wird das Property `ma:hat_Frequenz` zum Subjekt folgender dreier Tripel):
```
ma:hat_Frequenz	rdf:type owl:ObjectProperty 
	rdfs:domain ma:Ton ;
 	rdfs:range ma:Frequenz .
```

2) Durch die Bestimmung der Wirkunsweise von `ma:hat_Freuquenz` ist es im Folgenden möglich aus einer Aussage mehrere weitere Aussagen zu inferieren: Aus dem Tripel
```
example:x ma:hat_Frequenz example:y
```
wäre es für eine Reasoning-Applikation nun möglich zu inferieren, dass es sich bei `example:x` um eine Entität der Klasse `ma:Ton` und bei der Entität `example:y` um eine Entität der Klasse `ma:Frequenz` handeln muss.

3) Eine direkte Überführung des ERM mit `rdfs:domain` und `rdfs:range` ist nur im Falle bestimmter Properties – nämlich derjenigen, die in Bezug zu nur einem einzigen Subjekt und Objekt stehen (etwa `ma:hat_Ambitus`) – möglich. Das Property `ma:Interpret` etwa bezieht sich auf mehrere Subjekte. Eine Aussage in der folgenden Form ist jedoch problematisch:
```
ma:Interpret rdf:type owl:ObjectProperty ;
	rdfs:domain		ma:Instrument_nach_Vokabular_(Domäne) ;
 	rdfs:domain		ma:ma:Objekt_(Domäne) ;
 	rdfs:domain		ma:Aufführung_(Domäne) ;
 	rdfs:range		 ma:Person		.
```
Aus diesem Sachverhalt scheint sich inferieren zu lassen, dass jede Instanz der Klasse `ma:Person` immer auch einer Instanz von `ma:Objekt_Domäne`, `ma:Instrument_nach_Vokabular_(Domäne)` sowie `ma:Aufführung_(Domäne)` zugleich zugeordnet ist.[^8683]
Eine Aussage, wie
\

"Person a ist an dem Ereignis 'Uraufführung' beteiligt (spielt jedoch nicht auf dem Museumsobjekt b)" 
\

wäre demnach nicht möglich.

Einen Ausweg scheint in die Möglichkeit zu bieten, eine übergeordnete Klasse für die Entitäten `ma:Instrument_nach_Vokabular_(Domäne)` sowie `ma:Objekt_Domäne` zu erschaffen und die Verwendung von `ma:Interpret` mit `rdfs:domain` auf diese Oberklasse (`ma:Instrument_(Domäne)`) zu beschränken.[^8684]
Die Koppelung von Person und Ereignis scheint hingegen eine allgemein gültige.
Somit lautet die neue Definition von `ma:Interpret`:
```
ma:Interpret rdf:type owl:ObjectProperty ;
	rdfs:domain		ma:Instrument_(Domäne) ;
 	rdfs:domain		ma:Aufführung_(Domäne) ;
 	rdfs:range		 ma:Person		.
```
Bezugnahme auf die neue Superklasse `ma:Instrument_(Domäne)` kann nun auch auf analoge Sachverhalte im Falle von `ma:hat_Stimmung_(absolut)`, `ma:hat_Stimmungssystem` sowie `ma:hat_Klangbeispiel` angewendet werden.
\

Die *open world assumption* bringt es mit sich, dass eine Validierung von in RDF strukturierten Daten naturgemäß eigentlich nicht vorgesehen sein kann.[^8685] Hieran ändert auch – trotz des Namens – RDFS kaum etwas: "Unlike XML Schema, RDF Schema is generally interpreted as supplementing rather than validating RDF data."[^8686] Dennoch sind die Möglichkeiten von RDFS – etwa gegenüber dem sehr viel mächtigeren, dafür aber umso komplexeren OWL DL –[^8687] für die Belange dieses Metadatenprofils absolut angemessen,[^8691] nicht zuletzt da es gilt, Überkomplexität aufgrund seiner Anwendungs- und Anwenderorientiertheit insbesondere zu vermeiden.[^8690]
Man spricht in solchen Fällen von sogenannten "lightweight ontologies", die "in der Regel nur aus einer Konzepthierarchie sowie Relationen, für die jeweils Domain und Range Einschränkungen [sic!] angegeben werden[, bestehen]."[^8692] Gegenüber dem Vokabular, das lediglich eine Bestandsaufnahme der für diese Arbeit relevanten Konzepte und deren Klassifikation darstellte, ist kraft der Properties eine weitere ontologische Dimension hinzugekommen (vgl. Abbildung): phänomenologisch gesprochen wird das zuvor lediglich Vorhandene kraft seiner Bezogenheit um die Dimension intentionaler[^8693] Bestimmtheit erweitert. Es wird so ein Stück weiter in Richtung eines sinnhaften "Zuhandenenseins" innerhalb des Verständnishorizonts eines wie auch immer gearteten wahrnehmenden Subjekts entwickelt. 

Wenn an dieser Stelle der Begriff (lightweight) Ontologie – auch wenn diese Arbeit den Begriff im Allgemeinen als zu bedeutungsschwer für sich scheut – ausnahmsweise Verwendung findet, so ist mit ihm also genau diese Qualität gemeint. Das Anwendungsprofil ist, gemessen an seinem Potential Seinsstrukturen einer Welt darstellen zu können, qualitativ als Ontologie zu betrachten. Gemessen an seiner Funktionalität, die es als Schema für Mapping und Datenanreicherung auszeichnet, ist es ein Anwendungsprofil.

[transitivity in Hierarchien? Muss ich da was machen?]


## Anbindung an- / Integration in das Semantic Web

In den vorangegangenen Kapiteln wurde ein Modell in eine strukturell auf RDF basierende Ontologie "übersetzt". Deren "Grammatik" orientierte sich zwar an der im Semantic Web standardisierten (RDF, RDFS, OWL), deren Semantik und Etablierung das Potential für eine Integration im Semantic Web birgt. Doch bleiben die in dieser Ontologie verwahrten Konzepte durch die Brille des "Semantic Web-Subjekts" betrachtet diffus: erkennbar sind lediglich eine Menge arbiträrer Entitäten, die in bestimmten, jedoch nicht weiter spezifizierten Beziehungen zueinander stehen. 
Es gilt insofern an dieser Stelle abermals einen hermeneutischen Prozess zu durchlaufen, in dessen Zuge die nicht-explizierten Konzepte im Namespace :ma dermaßen erschlossen werden, dass sie für ein Wahrnehmungssubjekt interpretierbar werden. 
Abermals stellt sich, wie in #Kapitel die Frage, in welcher Weise der Verständnishorizont zu überwinden ist. Dies ist für ein menschliches Subjekt relativ einfach zu beantworten, etwa indem Konzepte mit sinnvollen Namen und Erklärungen versehen werden. Doch wie verhält es sich mit einem Wahrnehmungssubjekt, das nur die Sprache des Semantic Webs beherrscht ("things not strings")?[^8697]

Eine zentrale Idee der Heidegger'schen Philosophie ist, dass das eigentliche Wesen von "Zeug"[^8694] (im Gegensatz etwa zu Platons Ideenlehre) keineswegs diesem a priori inhärent ist, sondern sich in der Welt erst in seiner kontextuellen habituellen Funktionalität und Materialität gegenüber einem Wahrnehmungssubjekt äußert.[^8696] Dieses Prinzip erscheint sich hier nochmals im Rahmen von Linked Data und Semantic Web eindrücklich nachzubilden: Kontext – sich in funktionalen Beziehungen zwischen Konzepten ausdrückend – bildet die Prämisse von Semantik. Das Wesen der Konzepte zeigt sich keineswegs in ihrer textuellen Beschreibung ("strings") begründet, sondern in ihrer Rolle als Sinnträger innerhalb eines Bedeutungsgefüges und gegenüber einem "besorgenden" Wahrnehmungssubjekt.

So ist etwa – ganz vereinfacht – das Wesen des Konzepts "Spucknapf" in den folgenden RDF-Tripeln ein je anderes: 

1. "Mann" "spuckt in" "Spucknapf"
2. "Spucknapf" "fällt auf" "Mann (Kopf)"

Neben dem offensichtlichen, hier variablen grammatikalischen "Wesen", Subjekt und Objekt,[nicht sicher ob das so geht] liegt im ersten Beispiel das Wesen des Spucknapfs darin begründet, dass es "der Gegenstand" ist, "in das man reinspuckt". Im zweiten ist es jedoch "das zerbrechliche Ding, das durch Fallen auf den Kopf Schmerzen und Ekel bereitet."
Exakt analog hierzu erscheint das "Wesen" einer Entität innerhalb einer formalen Welt dadurch bestimmt, in welchen Relationen sie zu der sie umgebenden, wechselwirkenden Welt steht.
Und umgekehrt, löst man Konzepte aus diesem Gefüge heraus (wie es bislang in dieser Arbeit der Fall ist), entbindet man sie ihrer semantischen Kraft, und sie werden, im schlimmsten Fall, zu nichts weiterem als zu kontingenten URIs, jedenfalls aber – zumindest nach Heidegger – zu einem trivialen lediglich Vorhandenen.
\

Es stellt sich nun die Frage, wie diese Kontextualisierung technisch umzusetzen ist. Boten bislang insbesondere die Arbeiten von Ontology101[^8698] und Stuckenschmidt[^8699] einen guten Leitfaden für die Erstellung von Ontologien im Sinne abstrakter formalisierter Wissenspräsentationen, so findet sich in der Literatur kaum irgendwo ein Hinweis zur Umsetzung semantischer Kontextualisierung eigener Ontologien im Semantic Web.

Einen Hinweis liefert Hyvönen, indem er drei Bestandteile einer (Semantic Web)-"Ontologieinfrastruktur" ausmacht:

>1.  Domain independent vocabularies are needed for facilitating cross-domain interoperability. For example, thesaurus standards and the W3C Semantic Web recommendations RDF(S), SKOS, and OWL fall into this category, as well as generic metadata schemas, such as Dublin Core.
    
>2.  Domain specific ontologies [...]. For example, the Getty Vocabularies (AAT, TGN, and ULAN), the Library of Congress Subject Headings (LCSH), and other vocabularies used for annotating contents fall in this category.

>3.  Institution specific ontologies are needed for concepts that may be relevant for a particular organization only or cannot be shared for some reason with a larger community[...].[^8700]

Anhand dieser Bestandsaufnahme lassen sich mehrere Aussagen schlussfolgern: Neben der auf technischer Ebene wichtigen Information, dass eine im Semantic Web integrierte Ontologie sich aus verschiedenen Vokabularen aus verschiedenen Bereichen zusammensetzt (ja zusammensetzen sollte),[^8708] halten diese Informationen auch Hinweise auf die Frage nach semantischer Kontextualisierung bereit:
Eine Ontologie erhält ihre Aussagekraft indem sie sich in den Kontext bereits etablierter Vokabulare stellt. Dabei sind die etabliertesten diejenigen, die das höchste Maß an Verständlichkeit (Interoperabilität) anbieten –  domänen- und institutionsspezifische die, die das höchste Maß an semantischer Spezifität zu erreichen imstande sind.

Freilich ist hierdurch nur wenig über den eigentlichen technischen Prozess der Verknüpfung eigener Ontologien im Semantic Web ausgesagt. Etwas aussagekräftiger ist wiederum etwa die Maßgabe "[s]et RDF links to other data sources on the Web, so that clients can navigate the Web of Data as a whole by following RDF links."[^8701] Die folgenden Möglichkeiten lassen sich aus dieser Forderung ableiten:

1) In etwa analog zur Klassierung von Konzepten in #kapitelx erscheint es denkbar, eigene Konzepte in Relation zu externen Konzepten zu setzen, und diese Relationen als Eigenschaft in der RDF-Beschreibung des Konzepts zu fixieren. Der bisherige Verständnishorizont wäre somit für eine Anwendung, die das Applikationsprofil parsed, überwunden, und ein Konnex zwischen Domänenontologie und Semantic Web geschaffen.\
Ein – vorläufiges – Beispiel:

``ma:Klangbeispiel	rdfs:subclassOf	<http://d-nb.info/gnd/4052020-1> .``

In Worten: Der Term "Klangbeispiel" im :ma-Namespace wird als Unterklasse des in der GND definierten Schlagworts "Schallaufzeichnung" verstanden. 

Das Property `rdfs:subclassOf` verlinkt dabei in eine externe, bereits im Semantic Web eingebundene und semantisch etablierte Ontologie, die GND. 

Neben dieser hierarchischen Relation sind auch Äquivalenzrelationen darstellbar. Insbesondere das Vokabular SKOS ("Simple Knowledge Organization System")[^8702] hat sich etabliert, um etwa Thesauri in RDF zu überführen,[^8703] jedoch insbesondere auch um Vokabulare und Ontologien aufeinander zu beziehen[^8704] (ontology alignment,[^8706] Mapping). Hierfür sind sich etwa die Properties

``
skos:exactMatch

skos:narrowMatch

skos:broadMatch

skos:closeMatch
``
besonders geeignet. Es wird jedoch deutlich, dass die Ambivalenz dieser Propeties (ausgenommen `skos:exactMatch`) naturgemäß groß ist und daher keine endgültig befriedigende semantische Eindeutigkeit ermöglichen kann.\

2) Während das Mappen zu äquivalenten Termen im Falle sich bereits in Verwendung befindlicher und somit unantastbarer Vokabulare notwendig sein mag, erscheint es angesichts von Funktionsweise und Architektur des Semantic Webs im Falle des Applikationsprofils nicht erstrebenswert. Obwohl die Produktion von Doubletten (und anschließendem Mapping) im Sinne der *open world assumption* im Semantic Web nicht "falsch" ist,[^8705] so ist sie doch eingedenk dessen Konzeption als offene, ins Netz ausgelagerte "Datenbank", in dem jeder Datensatz für jeden zugänglich und referenzierbar ist, unsinnig, ist doch Kontextualisierung durch den Rekurs auf semantisch etablierte und somit aussagekräftige Konzepte, wie bereits mehrfach betont, sogar außerordentlich wünschenswert. 
Diese Aussagekraft erhöht sich weiter durch Wiederverwendung etablierter Konzepte und der Vermeidung von konkurrierenden Redeundanzen: "it is considered good practice to reuse terms from well-known RDF vocabularies [...] wherever possible in order to make it easier for client applications to process Linked Data. Only if these vocabularies do not provide the required terms should data publishers define new, data source-specific terminology [...]."[^8707]So wird zu guter Letzt "[...]die Einheitlichkeit und Interoperabilität der Beschreibungen sicher[gestellt]."[^8709]

So ist also das Konzept `ma:Ton` bei der Einbindung ins Semantic Web nicht über die Festlegung
``
ma:Ton	skos:exactMatch	gnd:Ton .,
``
sondern einfach durch das Konzept `gnd:Ton` zu ersetzen.

### Vorgehensweise

Für den Fortgang dieser Arbeit erscheint die folgende Vorgehensweise sinnvoll:

1. Das Vokabular in seiner derzeitigen Form beinhaltet auch Platzhalter für institutionsspezifische Terme. Diese sind aus dem Vokabular auszulagern und in separaten Namespaces zu sammeln.
2. Das verbleibende, institutionsübergreifende Vokabular im Namespace :ma ist daraufhin zu untersuchen, ob sich seine Semantizität auch ebensogut in externen Konzepten abbildet, und eigene Terme in diesem Fall durch sie zu ersetzen. Dabei wird es gelten, eine ausgewogene Balance zwischen semantisch festen, jedoch vermutlich eher unspezifischen, domänenübergreifend verwendeten Konzepten, und spezifischen, jedoch womöglich weniger etablierten Konzepten auszutarieren. Dieser Vorgang birgt einige methodische Herausforderungen, auf die an entsprechender Stelle eingegangen werden wird.
3. Eigene Terme, für die sich keine vorexistierende Entsprechungen finden lassen, sind nochmals zu fokussieren und einer terminologischen Kontrolle zu unterziehen. Anschließend sind sie gemäß 1) im vorhergehenden Kapitel in Beziehung zu externen Vokabularen zu setzen und so im Semantic Web durch Verknüpfung aussagekräftig referenzierbar zu machen. Sie sind anschließend gemäß der guten Praxis bei Namespaces[^8710] auch mit menschenlesbaren Informationen und Bezeichnungen ("Labels") anzureichern.[^8711]


#### Terminologische Kontrolle

Mit "terminologischer Kontrolle" sind im Sinne Bertrams "alle Maßnahmen [...], die direkt oder indirekt der Definition und Abgrenzung von Begriffen und der eindeutigen Zuordnung von Bezeichnungen zu Begriffen dienen [...]"[^8712] gemeint. Während dieser Prozess in einem herkömmlichen Thesaurus insbesondere introspektiv auf die Arbeit mit internen Termen gerichtet sein dürfte, so umfasst der hier miteinzubeziehende Thesaurus nichts Geringeres als die Gesamtheit aller im Semantic Web eingebundenen Daten. Es liegt somit auf der Hand, dass dieser Prozess sich in vielem von der herkömmlichen Erstellung von Vokabularen unterscheiden muss. Leider findet sich in der Literatur, wie bereits eingangs erwähnt, kaum ein Hinweis, wie dieser Vorgang zu gestalten sein mag. Dieser Umstand kann auch nicht weiter verwundern, bedenkt man, dass die Heterogenität formalisierter Weltrepräsentationen in Form von Ontologien die Heterogenität, Komplexität und Ambivalenz der realen Welt widerspiegeln muss – einen allgemeingültigen Leitfaden unter diesen Umständen zu formulieren, ist somit naturgemäß schwierig, erscheint aber als lohnenswertes Desiderat für künftige Arbeiten.

Für diese Arbeit erscheinen die folgenden Schritte und Abwägungen sinnvoll:

* Bereits mehrfach wurde auf den Wert etablierter Vokabulare hingewiesen. Unter diesen findet sich eine Reihe von Vokabularen, die als Standards, wenn nicht gar als Grundpfeiler des Semantic Webs gelten können. Diese sind insbesondere RDF, RDFS, SKOS, OWL, aber auch etwa Dublin Core. Ihre Verwendung ist gut dokumentiert, und es existiert eine vergleichbar große Menge einführender Literatur, die als Leitfaden zu Rate gezogen werden kann.[^8713] Diese Vokabulare fanden bereits teilweise Verwendung in den vorangegangenen Kapiteln, und es wird aufgrund ihrer hohen Aussagekraft gelten, auch im Folgenden sich ihrer wann immer möglich zu bedienen.

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



---

Weiteres Vorgehen: Schluss mit Methodikgeschwafel: jeder Begriff wird jetzt einfach systematisch abgearbeitet.



es bleibt ein subjektives, gefühlsmäßiges Ding – es gibt kein eindeutiges Richtig/Falsch

Denkbar wäre philologische Auswertung der Vokabulare, aber würde Rahmen der Arbeit sprengen. Daher iterativ – deckt sich auch mit Vorgehen in der Praxis.






Wie lässt sich die Semantik eines Terms messen? Müsste man jetzt für jedes nochmal eine föderierte Suche machen?


BARTOC

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











"semantische[s] Bindeglied zwischen Klassen und Propertys".[^30]




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

"An URIs kann, abgetrennt durch #, auch ein weiteres Fragment angehängt werden. Die Kombination aus URI und Fragment wird URI-Referenz genannt. URI- Referenzen werden in RDF häufig zur eindeutigen Referenzierung von Ressourcen verwendet und stellen somit eine wichtige Komponente der Semantic-Web-Schichten dar."[^6]



"Oft muss man aber auch vo ̈llig neue URIs bilden. In einem solchen Fall muss man sicherstellen, dass die gewa ̈hlte URI nicht versehentlich anderswo mit anderer Bedeutung zum Einsatz kommt. Eine gute Methode dazu ist es, eine URI zu wa ̈hlen, die sich aus einer Webadresse ableitet, deren Inhalte man selbst kontrolliert. Eine URI, die mit http://springer.com/... beginnt, soll- te demnach nur vom Springer-Verlag eingefu ̈hrt werden. Außerdem ist es in einem solchen Fall mo ̈glich, an der entsprechenden Adresse ein Dokument ab- zulegen, welches die Bedeutung der URI fu ̈r Menschen beschreibt." [@TN_libero_mab21631588, S. 48–49]

"Eine Mo ̈glichkeit ist die Verwendung von URI-Referenzen. Schreibt man z.B. http://de.wikipedia.org/wiki/Othello#URI, dann zeigt dies nicht direkt auf ein existierendes Dokument (da es den Abschnitt ”URI“ auf dieser Seite nicht gibt). Wenn man diese URI-Referenz als URL aufruft, dann erha ̈lt man dennoch die beschreibende Seite fu ̈r diese URI." [@TN_libero_mab21631588, S. 49]

"Eine andere Mo ̈glichkeit ist die Verwendung von Weiterleitungen: auch bei Aufruf einer nicht existierenden URL kann ein Server den Nutzer auf eine alternative Seite weiterleiten. Da das Programm des Nutzers diese Weiterlei- tung wahrnimmt, ist dennoch die Unterscheidung der URIs gewa ̈hrleistet. Die automatische Weiterleitung hat außerdem den Vorteil, dass man entweder eine menschenlesbare HTML-Datei oder eine maschinenlesbare RDF-Datei auslie- fern kann – abha ̈ngig von Informationen in der Anfrage. Dieses Verfahren ist auch als Content Negotiation bekannt." [@TN_libero_mab21631588, S. 49]


---

[^1]: Zur Schreibweise: 

[^2]: Vgl. etwa die Aussage "Individual instances are the most specific concepts represented in a knowledge base." ([@gangler_semantic_nodate, S.18]).

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

[^13]: Auf eine Übersicht der gängigen übergeordneten Klassen – etwa "Literals", "Datatypes", "Blank nodes" etc. – muss an dieser Stelle verzichtet werden.

[^14]: [@TN_libero_mab213864266, S. 151]

[^15]: [@alma9913393902586, S. 166]

[^16]: S. hierzu etwa: [@alma9913393902586, S. 95–99]

[^17]: [@noauthor_owl_nodate-3] Diese Arbeit verwendet OWL Full, das die größten Ausdrucksmöglichkeiten bietet und mit RDFS kompatibel ist. (Vgl. [@TN_libero_mab21631588, S. 125–127])

[^18]: 

[^19]:  [@alma9913393902586, S. 146]

[^20]: Vgl.: [@noauthor_rdf_nodate-2]

[^21]: [@national_information_standards_organization_u.s._guidelines_2005, S. 3]



[^23]: [@TN_libero_mab213864266, S. 151]

[^24]: Die Serialisierung erfolgt am einfachsten, indem etwa der Ontologieeditor *Protégé* zu Hilfe genommen wird. Er ermöglicht den Export von Ontologien in vielfältigen Formaten.

[^25]:  [@alma9913393902586, S. 169]

[^26]: [@alma9913393902586, S. 24]

[^27]: Auch in OWL verfügt über entsprechende (noch mächtigere) Möglichkeiten, diese Beziehungen auszudrücken (vgl. hierzu etwa: [@allemang_semantic_2011, S. 238-239.]) Allerdings erscheint für die Belange dieser Arbeit die Terminologie von RDFS als genügend.

[^28]: Wörtlich also: "Das Objekt mit der Signatur 1663 hat den Typ eines Barockhorns".

[^29]: [@alma9913393902586, S. 106]

[^30]: [@TN_libero_mab21631588, S. 77]

[^31]: [@noauthor_rdf_nodate-3]

[^32]: [@noauthor_rdf_nodate-4]

[^33]: [@alma9913393902586, S. 169]

[^8649]: Zur spezifischen Problematik des an dieser Stelle verwendeten  FRBR/FRAD-Modells bei Werken der Musik s.  [@bicher_normdaten_2018, S. 225].

[^8650]: In den sogenannten *Functional Requirements for Bibliographic Data*, deren Entitätenmodell an dieser Stelle verwendet wird, heißt es: "Ein Werk ist eine abstrakte Entität; es gibt keinen entsprechenden materiellen Gegenstand." ([@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 16]).

[^8651]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 18–20.]

[^8652]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 20–22.]

[^8653]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 22–23.]

[^8654]: Und somit strenggenommen ebenfalls eine domänenspezifische Entität. **in MIMO verlinken**

[^8655]: Ein gleichermaßen illustratives wie auch charmantes Beispiel für eine solche Beziehung wären etwa Leopold Mozarts und Johann Ernst Eberlins Komposition "Der Morgen und der Abend" ([@mozart_eberlin_morgen_nodate]) für das "Hornwerk" der Festung Hohensalzburg aus dem 16. Jahrhundert, dem sog. *Salzburger Stier* ([@hocker_mechanische_2016]). (Ein lohnenswerter klanglicher Eindruck lässt sich hier gewinnen: [@noauthor_salzburger_nodate]).

[^8656]: Daher die gestrichelte Verbindungslinie zwischen Objekt und der Entität der relativen Stimmung.

[^8657]: Anders verhielte es sich freilich, würde mit dem hier definierten Schema beispielsweise eine Audioaufnahme einer Aufführung mit modernen Instrumenten erschlossen.

[^8658]: Etwa lassen die Stimmungen von unstimmbaren Instrumenten (Blockflöten, Zinken etc.) sehr präzise Rückschlüsse auf die historische Musikpraxis zu (vgl.: [@haynes_stimmton_2016]).

[^8659]: Nach Martin Fowler, dem Begründer des Modells: "An object model of the domain that incorporates both behavior and data." (vgl.:[@N_libero_mab2, S. 116]).

[^8660]: Da diese Arbeit angesichts ihres Fallbeispiels sehr stark RISM als primäre Domäne hervorhebt, kann gar nicht oft genug betont werden, dass jede andere relevante Domäne gleichermaßen im Vordergrund stehen könnte. So ist letztlich auch die Objektentität innerhalb einer Domäne, in diesem Fall dem Musikinstrumentenmuseum der Universität Leipzig, angesiedelt, das seinerseits sein Objekt mit dem RISM-Datensatz verlinken könnte, und dasselbe gilt selbstverständlich auch für Editionen, Bibliotheken, Archive, Wirtschaftsunternehmen etc.


[^8661]: Siehe hierzu etwa: [@alma9958916302586, S. 338–343]

[^8662]: [@alma9958916302586, S. 342–343]

[^8663]: [@alma9958916302586, S. 343]

[^8664]: Um den Umfang dieser Arbeit in Grenzen zu halten, kann nicht jedem denkbaren Szenario in ihr Rechnung getragen werden. Vielmehr würden sich solche tiefergehenden Überlegungen im Rahmen einer Weiterentwicklung des Anwendungsprofils empfehlen.

[^8665]: Sowohl "simultan" (vgl. etwa den Hornsatz in C. M. v. Webers Ouvertüre zur Oper "Der Freischütz": "Corni in F" sowie "Corni in C"), als auch "sukszessive" ab der Klassik zwischen Sätzen und mit der zunehmenden Erweiterung des harmonischen Raums im Laufe des 19. Jahrhunderts immer mehr auch in kontingenter Abfolge. 

[^8666]: Tatsächlich kann diese Entität in Zusammenhang mit Objekten lediglich in Verbindung mit Instrumenten Verwendung finden, die etwa aus baulichen, physikalischen Gründen eine solche "Grundstimmung" vorweisen.

[^8667]: Vgl. [@haynes_stimmton_2016]

[^8668]: So etwa im Falle der Eigenschaft *Entsprechungsgrad* angelegt: Es lassen sich unterschiedliche Grade vorstellen.

[^8670]: Zu den technischen Aspekten von Namespaces im Semantic Web siehe insb. [@noauthor_linked_nodate] sowie [@heath_linked_2011]  und [@noauthor_associating_nodate]

[^8671]: Vgl. etwa: [@madoc34762, S. 3]

[^8672]: OWL2 differenziert, anders als etwa RDFS, nicht lediglich zwischen Klasse und Instanz, sondern zwischen Klasse und unterschiedlichen Individuen (vgl. [@noauthor_owl_nodate-1])

[^8673]: Vgl. [@noauthor_architecture_nodate]

[^8674]: [@allemang_semantic_2011, 128–130]

[^8675]: [@noauthor_rdf_nodate]

[^8676]: [@noauthor_rdf_nodate-6]

[^8677]: [@TN_libero_mab21631588, S. 13]

[^8678]: [@noauthor_resource_nodate]

[^8679]: [@alma9913393902586, S. 32]
\
Dies etwa im Gegensatz zur *closed world assumption* in herkömmlichen relationalen Datenbanken. Zur Notwendigkeit der Open World Assumption in semantischen Netzen s: [@alma9913393902586, S. 43]

[^8680]: [@TN_libero_mab21631588, S. 67]

[^8681]: [@szeredi_lukácsy_benkő_nagy_2014, S. 98–99]

[^8682]: [@noauthor_overview_nodate]

[^8683]: [@TN_libero_mab21631588, S. 77]

[^8684]: "Jede definierte Einschra ̈nkung auf einer Property wirkt al- so immer global auf jedes Vorkommen dieser Property, weswegen man bei der Angabe solcher Einschra ̈nkungen darauf achten muss, immer die allge- meinsten denkbaren Klassen anzugeben (also diejenigen, die mit Sicherheit alle mo ̈glichen Ressourcen, die in der fraglichen Beziehung stehen ko ̈nnen, enthalten)." ([@TN_libero_mab21631588, S. 77])

[^8685]: [@noauthor_examples_nodate]

[^8686]: [@noauthor_examples_nodate]

[^8687]: descriptive logic – AI - solcher Kram

[^8688]: [@alma9913393902586, S. 77]

[^8690]: [@hyvonen_publishing_2012, S. 76]

[^8691]: [@TN_libero_mab21631588, S. 68]

[^8692]: [@alma9913393902586, S. 170–171]

[^8693]: Husserl

[^8694]: 

[^8695]: 

[^8696]: 

[^8697]: noauthor_introducing_2012
[^8698]: 

[^8699]: 

[^8700]: [@hyvonen_publishing_2012, S. 87–88]

[^8701]: [@madoc34762, S. 6]
[^8702]: 

[^8703]: [@allemang_semantic_2011, S. 207]

[^8704]: [@allemang_semantic_2011, S. 213]

[^8705]: [@noauthor_overview_nodate]

[^8706]: [@zimanyi_web_2015, S. 79–80]

[^8707]: [@madoc34762, S. 7] Die Autoren berufen sich ihrerseits auf [@noauthor_how_nodate]

[^8708]: Vgl. auch [@noauthor_how_nodate]: "It is common practice to mix terms from different vocabularies."

[^8709]: [@alma9913393902586, S. 160–161]

[^8710]: 

[^8711]: "Begriffliche Kontrolle", vgl.: [@TN_libero_mab213864266, S. 128]

[^8712]: [@TN_libero_mab213864266, S. 128]

[^8713]: In dieser Arbeit wurden vor allem die Texte [@allemang_semantic_2011] sowie [@TN_libero_mab21631588] zu Rate gezogen.