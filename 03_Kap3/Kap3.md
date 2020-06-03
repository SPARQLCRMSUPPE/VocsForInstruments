# Modellierung und Klassifizierung mit RDF

## Anwendungsmodellierung

Insgesamt erscheint es als sinnvoll, zuerst die bereits in Kapitel #Desiderat angerissenen Anforderungen nochmals zu schärfen und aus ihnen ein Modell zu generieren, das künftig als diskursive Grundlage für die spätere "dokumentationssprachliche" Ausarbeitung herhalten kann. Dies soll in einem zweistufigen Prozess geschehen, in dem zunächst ein informelles Anwendungsmodell generiert wird, aus dem wiederum ein verbindliches Datenmodell in Form eines *ERM*s (Entity Relationship Model) abgeleitet werden kann, das die Grundlage für die RDF-Modellierung bietet.
Dieses Vorgehen gewährleistet außerdem, dass sich das Anwendungsprofil an den tatsächlichen in der Praxis vorgefundenen Erfordernissen ausrichtet und sich nicht etwa "in vorauseilendem Gehorsam" anhand der bereits etablierten Darstellungsmöglichkeiten selbst zensiert und beschneidet. (In Vorgriff auf die terminologische Ausarbeitung heißt dies etwa: domänenspezifische Vokabulare dahingehend zu untersuchen, ob sie in der Lage sind, das Geforderte abzubilden und andernfalls nach Möglichkeiten zu suchen, diese Darstellungsmöglichkeiten selbst zu schaffen.)
Jedoch darf diese scheinbare Übersimplifizierung, die zunächst also jederlei Eindeutigkeit – etwa in Form von Normdaten – vermeidet, keineswegs als solche missverstanden werden. Vielmehr bildet sie die eigentliche Prämisse für spätere grundsätzliche terminologische Anschlussfähigkeit und Interoperabilität, indem sie sich nicht auf bestimmte gebräuchliche Datenstrukturen oder eine bestimmte Domäne fixiert. 

![Datenmodell – Beziehungen ausgedrückt als Verbindungslinien zwischen den umkreisten Entitäten](medien_Kap3/20200320_Datenmodell_Skizze2.png)



### Domäne[^c8660]

1) Dies wird etwa im Falle der Entität *BWV 208* deutlich: Das "Label" "BWV 208" referenziert hier die Kantate auf Werkebene und fungiert als Platzhalter[^c8650] für eine Expression[^c8651] (etwa der in RISM beschriebenen Quelle),[^c8649] einer Manifestation[^c8652] (etwa einer Edition), oder aber auch eines Exemplars[^c8653] (etwa einer, freilich illegal, mit Bleistift eingerichteten Ausgabe in einer Bibliothek).

2) Über die Beziehung "Besetzung" mit der Entität Werk verbunden ist die Entität *Corno da caccia*, im Modell mit dem – willkürlichen – Label "cor da caccia", der Terminologie von RISM folgend, versehend. Auch an dieser Stelle ist das Label völlig flexibel – analog also zur Entität *BWV 208*.

Diese beiden Entitäten sind diejenigen, die herkömmlicherweise – wie im RISM-Datensatz exemplarisch demonstriert – die Erschließungstiefe in den allermeisten Datenbanken ausfüllen.
Die Entitäten dieses Bereichs sind institutions-, sparten-, domänenspezifisch sowie bereits etabliert und stehen daher für dieses Metadatenprofil nicht zur Disposition. Das spätere Datenmodell wird daher an dieser Stelle  keinen präskriptiven Charakter für sich beanspruchen können, und auch eine Weiterentwicklung dieses erscheint hier müßig. -> **darauf zurückkommen und sagen, wo was gemacht werden kann** 

### Mapping

Beim Mapping-Anteil steht einerseits die Vernetzung zwischen Objekt und Werk im Vordergrund, zum anderen kann hier die Disambiguierung unklarer Terminologie erfolgen.
Die Anbindung der Besetzungsentität *Corno da caccia* an die Objekt-Entität – in diesem Fall verkörpert durch ein Objekt des Musikinstrumentenmuseums der Universität Leipzig[^c8654] – kann in zweierlei Weise erfolgen:

3) durch ein direktes In-Beziehung-Setzen mit der Entität *Corno da Caccia*. Hier sind mehrere Arten der Beziehung denkbar: 
- Einerseits könnte es sich beim Objekt um exakt jenes handeln, das Bach für das Werk besetzt hatte.[^c8655].
- In den meisten Fällen jedoch wird eine dermaßen eindeutige Beziehung nicht nachzuvollziehen sein. Vielmehr wird – wie ja auch im Falle von BWV 208 – auf ein ungefähres Äquivalent zu verweisen sein.

4) durch das Mapping über eine zwischengelagerte Klassifikation. Dieses erscheint etwa im hier verwendeten Falle sinnvoll, um den Term "cor da caccia" weiter zu disambiguieren. **für die Zukunft: wenn man mit MIMO verlinkt, kann der Typ inferenziert werden (MIMO-Thesaurus)!!** Unsinnig erscheint dieser Ansatz hingegen, wenn im Bereich der Domäne ein maschinenlesbares und bereits gemapptes Standardvokabular (etwa GND, IAML MoP etc.) Verwendung findet – auch wenn diese mitunter, wie bereits erwähnt, mitunter sehr zu wünschen übrig lassen.

### Anreicherung

Nachdem die Besetzungsentität durch Verknüpfung mit einem Objekt bzw. einer Klassifikation eindeutig bestimmt worden ist, ist es wünschenswert, sie durch weitere Aussagen anzureichern und dadurch noch aussagekräftiger zu machen.

5) Die Hörner sind im Autograph "in F" notiert – der tatsächliche Klang der in F notierten Töne der Hornstimme liegt also eine Quinte tiefer. Dies wird durch die Beziehung der Besetzungsentität zu ihrer relativen Stimmung "in F" ausgedrückt. Auch für das Objekt könnte bekannt sein, dass es in F gestimmt ist (= das Instrument produziert Töne der sog. *Naturtonreihe* über dem Ton *f*), was im hier behandelten Szenario jedoch nicht der Fall ist.[^c8656]

> Aus diesem Umstand lassen sich – zumindest für die Zeit bis zur Erfindung des Ventilhorns – sehr facettierte Aussagen zum vorgesehenen Instrument treffen (Länge, Mensur etc.), deren Darstellung jedoch für den begrenzten Rahmen dieser Arbeit keine Rolle spielen kann. Außerdem liefert die Angabe der Stimmung der Hörner – ebenfalls begrenzt auf die Zeit bis zur Erfindung des Ventilhorns – einen Indikator für die Bestimmung der Tonart (wie auch im Fall von BWV 208: Die Kantate steht in F-Dur).

6) Der Besetzungsentität ist in ihrer Eigenschaft als Besetzung für *BWV 208* ein bestimmter Tonvorrat zu eigen, der sich durch die Entität *Ambitus* ausdrückt. Dieser wiederum setzt sich aus einer Tonmenge zusammen, die durch die beiden Entitäten des höchsten und des tiefsten Tons eingegrenzt wird.

>Die Kenntnis des Ambitus' lässt in wissenschaftlicher Hinsicht vielerlei Rückschlüsse zu: etwa auf die Länge des Instruments (Faustregel: kürzer = Tonvorrat liegt höher). Für Musiker (etwa Anfänger) kann diese Information selbstverständlich bei der Suche nach Noten ebenfalls außerordentlich nützlich sein.

7) Im in dieser Arbeit gewählten Szenario ist aus physikalischen Gründen das Stimmungssystem des *Corno da caccia* eindeutig und kann hier berücksichtigt werden.[^c8657] Tatsächlich ist das Bestimmen historisch verwendeter Stimmungssysteme in vielen Fällen weit weniger eindeutig.

8) Über die absolute Stimmung der ursprünglich vorgesehenen Instrumente, wie auch für das Objekt *MIMUL 1663* selbst, lässt sich keine eindeutige Aussage treffen. Gleichwohl ist diese Entität grundsätzlich durchaus als aufschlussreich für die Wissenschaft anzusehen.[^c8658] Somit handelt es sich bei der Angabe *a* = 415 Hz um einen vermuteten Wert, und es ergibt sich für den Fortgang der Arbeit die Frage, ob es in einem späteren Datenmodell auch möglich sein wird, auch Ambivalenzen und Unsicherheiten dieser Art abzubilden.

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


Das folgende Kapitel bildet den Ausgangspunkt dafür, den Weg von einem Anwendungsszenario zu einem Semantic Web-kompatiblen Metadatenprofil zu beschreiten. [vielleicht noch etwas darüber, dass es keine wirkliche Lit. gibt, die einen Leitfaden von Anfang bis Ende bildet] Gemäß Noy und McGuinness[^c8] steht dabei ganz zu Beginn des Prozesses hin zur Ontologie zunächst eine Klassierung[^c9] der benötigten Typen nach folgendem Schema:

> "Define the classes and the class hierarchy"

> "Define the properties of classes [...]"

> "Create instances"

Das Produkt dieser Vorgehensweise bildet, wie oben angedeutet, eine zunächst auf den Anwendungsbereich beschränkte "Ontologie", die nicht mit den Sprachen des Semantic Web ausgezeichnet ist.
Tatsächlich hat sich im Verlauf dieser Arbeit ganz organisch eine andere Reihenfolge ergeben: Nach dem exemplarischen Auffinden eines Defizits wurde ein spezifisches Szenario entworfen, um dieses zu beheben: Einige wichtige Instanzen[^c11] wurden bereits im vorhergehenden Kapitel identifiziert und aufgeführt.

#### Entity Relationship Model [es muss klar werden, dass das nur eine Hilfestellung ist – die aber nicht kompatibel mit RDF ist]

Ein erster möglicher Schritt in Richtung einer Modellierung mit RDF ist die Überführung des Anwendungsmodells in ein Hilfskonstrukts in Form eines *Entity Relationship Models* (ERM). Hierbei sollen die anwendungsspezifischen Szenarien strukturiert und auf eine allgemeine Ebene gesetzt werden, auf der übergeordnete Entitätsklassen und ihre Eigenschaften in Beziehung zueinander stehen.[^c8661] So werden Klassen definiert und erste einfache hierarchische Relationen zwischen Klassen und untergeordneten, "beschreibenden" Klassen (Eigenschaften) hergestellt.

Beziehungen ("properties" s.o.) wiederum können in diesem ERM ebenfalls zunächst als potentielle zukünftige "Eigenschaftsklassen" verstanden werden, die zukünftig Container für weitere "Untereigenschaften" darstellen können.[^c8668]
Im ERM fungieren besondere Schlüsseleigenschaften ("Primärschlüssel") als eindeutige Identifier einer Entität. Es ist zu erwarten, dass diese in einer RDF-Modellierung keine Rolle spielen werden, da dort eindeutige Referenzierbarkeit bereits dank URIs gegeben ist. [^c8662] Mengenverhältnisse zwischen Entitäten werden im ERM zudem durch "Kardinalitäten" miteinbezogen und dadurch fixierbar.[^c8663] 

![Entity Relationship Modell: farbige Markierung der externen Vokabulare. Entitäten stehen in Rechtecken, Eigenschaften in Ovalen, Beziehungen in Rauten. Schlüsseleigenschaften sind durch Unterstreichung gekennzeichnet.](medien_Kap3/20200507_ERM2.png)

Einige wesentlichen Entwicklungen gegenüber dem Anwendungsmodell sowie weitere Überlegungen sind es wert, nochmals kurz erläutert und erörtert zu werden.

* Wie bereits erwähnt sind den Entitäten des ERM gegenüber denen der Anwendungsmodellierung weitere sie beschreibende Eigenschaften hinzugefügt worden (etwa *Name* zu *Person*)

* Neben dem verwendeten Instrument *Instrument nach Vokabular (Domäne)* muss die Entität *Interpret* auch immer an ein Ereignis, in der Regel eine *Aufführung* geknüpft sein (diesem Umstand wurde durch die Zusätze im linken Domänenbereich Rechnung getragen). Dabei sind folgende Szenarien berücksichtigt: ein *Instrument* kann sowohl mehrfach ("n Mal") mit beliebig vielen *Interpreten* besetzt sein (entspricht beispielsweise der Bezeichnung "2 Oboen" oder "Celli" in einer Partitur) als auch gesondert aufgeführt werden (entspricht etwa dem Sachverhalt "Musiker a und Musiker b spielen vierhändig Klavier").

* Ein *Instrument nach Vokabular (Domäne)* kann innerhalb eines Werks beliebig viele notierte *Stimmungen* besitzen.[^c8665]. Die Bedeutung der Entität *Stimmung* – etwa mit dem Wert "F" – weicht dabei in der Kombination mit *Instrument* von der der Verwendung in Kombination mit *Objekt (Domäne)* ab: In dieser Kombination bezieht sich die Entität *Stimmung* auf die mögliche "Grundstimmung" eines Objekts (z.B. F-Horn), sofern es eine besitzt.[^c8666]

* Mithilfe einer Kombination gegebener Informationen zu *Stimmung* und *notiertem Ambitus* sollte es im Zuge eines späteren Schrittes möglich sein, Informationen zu den *klingenden Tönen* maschinell abzuleiten.

* Im ERM ist definiert, dass ein *Instrument nach Vokabular (Domäne)* nur eine (variable) *absolute Stimmung* besitzen kann. Denkbar wären jedoch auch z.B. Sachverhalte – Konzerte, Aufnahmen etc. – in deren Verlauf mehrmals umgestimmt wird. In diesen Fällen wäre auch eine Verknüpfung mit der Entität *Aufführung* angebracht.[^c8664]

* Grundsätzlich ist wünschenswert – wie im Fall des *Interpreten* oder dem Umstimmen von Instrumenten – bestimmte Entitäten mit Ereignissen verknüpfen zu können. Dies gilt insbesondere für die Entitäten *Stimmungssystem* (wird mit historisch akkurater gespielt, oder wohltemperierter Stimmung gespielt?) , *Kammerton* (wird mit den heute üblichen 440 Hz musiziert, oder mit einer historischen Stimmung, z.B. gemäß dem sog. *Cornettton*[^c8667]?), *Klangbeispiel* (Das Klangbeispiel stammt aus der und der Aufnahme) und *Instrument (Klassifikation)* (bei der Uraufführung fand Instrument a Verwendung, in der Aufnahme x ein typverschiedenes). 

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

Der Vorgehensweise im weiteren Verlauf liegt zugrunde, dass in RDF bereits bestimmte Klassen angelegt sind – in Folgevokabularen[^c10] um weitere ergänzt –, die verwendet werden können, um Konzepte zu klassifizieren.[^c13] Dabei erscheinen angesichts der zuvor ausgearbeiteten Anwendungsmodellierung die allgemein gebräuchlichsten drei Klassen[^c12] für die Zwecke dieser Arbeit ausreichend. Diese sind:

1. Klassen

2. Instanzen

3. Relationen (im Folgenden auch Properties) [Relationen? vg. Stuckschmidt 11]

Es mag an dieser Auflistung auffallen, dass in RDF das Konzept von Attributen gegenüber dem ERM keine ausgezeichnete Klasse mehr bildet. Dies ist unmittelbar einleuchtend, kann doch jede RDF-Entität auch als Subjekt eines Tripels agieren (somit erscheint das von seiner Bezugsentität abhängige und auf ihn verweisende Attribut mit RDF inkompatibel).
Durch die Aufteilung in (theoretisch also gleichgestellte) Entitäten und Beziehungen lassen sich bereits vollwertige RDF-Tripel bilden – zusätzlich gelingt es, dank der qualitativen Unterscheidung in Instanz und Klasse, einfache hierarchische Sachverhalte nachzubilden. In den folgenden Unterkapiteln wird es entsprechend darum gehen, eine entsprechende Klassierung am Gegenstand der erarbeiteten Konzepte vorzunehmen.

Doch worin besteht an dieser Stelle der tiefere Sinn einer Klassifikation? Direkt assoziativ ist die Funktion des Klassierens – sofern man sie nicht als reinen Selbstzweck betreibt – insbesondere mit der Ordnung von Ressourcen und deren Retrieval. Doch neben dieser "pragmatischen Aufgabe"[^c23] führt Bertram auch die "erkenntnisvermittelnde Aufgabe" von Klassifikationen ins Feld, die in der "Aufhellung von Zusammenhängen anhand geordneten Wissens" besteht.[^c14] Diese so angedeutete hermeneutische Dimension erscheint auch bei der RDF-Klassifizierung ganz zentral: Das Modell, das in seiner gegenwärtigen Form auf einem subjektiv geprägtem Verständnis, Wertesystem und persönlichen Denkstrukturen des Autors beruht, wird in ein objektives, standardisiertes System überführt. Gewissermaßen findet so eine Übersetzung statt, die den Erkenntnishorizont zwischen Mensch und Maschine überwindet. Das eigene Denkmodell wird dabei mithilfe der formalsprachlichen Ausdruckmittel des Semantic Web erfasst und ausgezeichnet, und so in das von RDF-vorgegebene Erkenntnisschema einsortiert. Die dem Modell inhärente Semantik wird – wie zu sehen sein wird freilich zunächst auf einer sehr oberflächlichen Ebene – dadurch objektiviert und gemeinhin auslegbar.

Diese Übersetzung geht mithilfe entsprechend standardiserter, sich ergänzender Modellierungssprachen, den sogenannten "Ontologiesprachen", vonstatten.[^c16] 
Die durch den W3C standardisierten Grundpfeiler des Semantic Web bilden dabei insbesondere die Sprachen RDF (Ressource Description Framework),[^c8675] RDFS (RDF Schema)[^c8676] und OWL (Web Ontology Language[^c17], der "inzwischen [...] meistbenutzen Ontologiesprache aller Zeiten"[^c19].

Die formale Interpretierbarkeit der durch die Sprache ausgedrückten semantischen Komponente wird durch eine Syntax, also einer  "Menge von Regeln, um Programme oder Dokumente mit bestimmten Eigenschaften [...] zu erzeugen",[^c8677] ermöglicht. Die Entscheidung für eine bestimmte Syntax ist dabei im Falle nach RDF strukturierter Daten zwar letztlich arbiträr, bilden sie doch im übertragenen Sinne gewissermaßen lediglich "Verpackung und Beipackzettel" für den eigentlichen semantischen Inhalt. Doch fällt aufgrund seiner Einfachheit und Übersichtlichkeit in dieser Arbeit die Wahl auf das sogenannte *Turtle*-Format ("Terse RDF Triple Language")[^c20].

Dabei erfolgt die Disambiguierung der Lemmata analog zur Klassifizierung in folgender Form (s. auch Kapitel #klassenundinstanzen):

* "Typ ist eine Klasse"

* "Typ ist eine Instanz"

* "Typ ist eine Eigenschaft"[^c5] 

Durch die klassifikatorische Erfassung der Instanzen, Entitäten und Beziehungen aus der Anwendungsmodellierung bzw. der Klassen, Eigenschaften und Beziehungen des ERM ergibt sich ein sehr einfaches kontrolliertes Vokabular – etwa im sehr grob gefassten Sinne des *National Information Standards Organization* und des *American National Standards Institute*.[^c21] Durch die Zuordnung von Instanzen zu Klassen ergeben sich zudem erste taxonomische Beziehungen – hier wie gesagt in Turtle serialisiert.[^c24] 
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

Auch wenn keine abschließenden Definitionen der hier geschaffenen Terme erstellt worden sind, lässt sich bereits jetzt die sehr allgemeine Aussage treffen, dass ihr semantischer Gehalt sich darin ausdrückt, wie sie in dieser Arbeit Verwendung finden. Es ist möglich, diese freilich bislang nicht im Einzelnen aussagekräftige, doch trotzdem in so fern definierte und abgrenzbare semantische Reichweite von Vokabular im Bezug zu sogenannten*Namensräumen*[^c8670] – referenzierbare kontrollierte Vokabulare – festzulegen. Die Namensraumzugehörigkeit der Terme dieser Arbeit wird im Folgenden zunächst durch das Präfix *ma:* gekennzeichnet. Der Namensraum ist am folgenden Ort, 

 https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma,

hinterlegt.

Eine menschenlesbare Definition der einzelnen Terme, wie sie als gute Praxis gemäß dem W3C (*World Wide Web Consortium*) nahegelegt wird,[^c8673] wäre zum gegenwärtigen Zeitpunkt noch verfrüht.

##### Instanzen (owl:NamedIndividuals) und Klassen (owl:Class, rdfs:subClassOf)

Die bei der Differenzierung zwischen Klasse und Instanz (owl:NamedIndividual)[^c8672] oftmals  vorgeschlagene Vorgehensweise,[^c2] bei der die niedrigste Entität eines aus Klassen bestehenden hierarchischen Strangs als Instanz zu werten ist, mag im Falle einer in sich abgeschlossenen Ontologie als  sinnvoll erscheinen. Doch muss der Blickwinkel im Fall der hier beabsichtigten Anwendung als verbindendes Metadatenprofil auch auf potentielle Anknüpfungspunkte, aber vor allem auf die Anwendungsfälle und Vokabulare, die gewissermaßen "außerhalb" des Profils liegen, erweitert werden. Die Frage also, ob etwas eine als Instanz oder eine Klasse zu verstehen ist, liegt nicht notwendigerweise in der hierarchischen Ebene begründet. Im Falle des *Barockhorns* wird dies insbesondere deutlich:
```
ma:Barockhorn_(Mitteldeutschland) rdf:type owl:Class ;
                                    rdfs:subClassOf ma:Instrument_(Klassifikation) .
```
Es ist einleuchtend, dass die Bestimmung einer Klasse (Barockhorn) als Instanz, auch wenn sie sich auf der untersten hierarchischen Ebene befindet, unsinnig ist.

##### Identifier

Während in einer relationalen Datenbank das Schlüsselattribut einer Entität variabel sein kann, erfolgt die eindeutige Referenzierung von Konzepten – darunter auch Entitäten – im Semantic Web grundsätzlich anhand von URIs (Uniform Ressource Identifier).[^c8671] Eine konzeptuelle Trennung zwischen Entität und seinem eindeutigen Identifier, wie im ERM, ist im Semantic Web nicht denkbar: Die URI selbst erscheint vielmehr gewissermaßen als digitale Manifestation des durch sie repräsentierten nichtdigital existierenden Konzepts. URIs sind also im Gegensatz zur Repräsentation im ERM keine eigenständigen Konzepte mehr, sondern sie "sind" die Konzepte:

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

* Analog zur Defintion von Klassen (owl:Class) und Unterklassen (rdfs:subclassOf) ist es mit *rdfs* möglich, Untereigenschaften (rdfs:subPropertyOf) zu Eigenschaften zu bilden.[^c8674] Dies ist im Falle der Eigenschaften *genaue Entsprechung* und *ungefähre Entsprechung* nützlich, indem sie der Eigenschaft *Entsprechungsgrad* subsumiert werden.
* Sonderzeichen, die mit der Turtle-Syntax inkompatibel sind, wurden mit dem "escape character" `\` maskiert.



## Vom Vokabular zur "Lightweight Ontology" – Spezifizierung von Relationen mit *rdfs:range* und *rdfs:domain*

Eines der zentralen Konzepte des Semantic Webs ist die sog. *open world assumption*.[^c8682] Gemäß dem vielzitierten Leitsatz "Anyone can say anything about anything"[^c8678] besagt sie, dass eine Aussage, die in einem Modell nicht explizit verankert ist, nicht notwendigerweise falsch sein muss, sondern dass lediglich keine Aussage über ihre Richtigkeit getroffen werden kann.[^c8679] Es muss somit im Interesse eines RDF-Vokabulars liegen, sein semantisches Ausdruckspotential fort von der Summe alles Möglichen (und somit Willkürlichen) hin zum eigentlich Aussagekräftigen fokussieren zu können, indem es Hinweise zur sinnhaften Verwendung seiner Terme bereithält. Die Möglichkeit einer solchen Fokussierung bieten Ontologiesprachen wie RDFS und OWL, indem sie in RDF formalisierte und somit direkt integrierbare "Anwendungsregel" zu Properties anbieten.[^c8680]
Es liegt dabei auf der Hand, dass für ein Applikationsprofil, dessen Sinn darin besteht, schematische Rahmenbedingungen zu schaffen, entlang derer sich Anwender ausrichten und orientieren können, ein hohes Maß an semantischer Fixiertheit insbesondere unabdingbar ist.

Doch werden kraft dieser Schemata keineswegs lediglich die Wirkungsweite von Relationen abgesteckt. Vielmehr entsteht durch sie eine weitere Bedeutungsdimension, die die Grundlage dafür bietet, auch maschinell inhärente logische Schlussfolgerungen (Inferenzen) ziehen zu können (Reasoning).[^c8681]

Während im Vokabular Properties in Form kontingenter, semantisch ungerichteter Bestandteile einer Liste aufgezählt waren, kann im Folgenden ihre Anwendung in Abhängigkeit zu den durch sie in Relation gesetzten Entitäten näher beschrieben werden.[^c33] Diesen Schritt zu vollziehen, ermöglichen die Properties *rdfs:range*[^c31] und *rdfs:domain*[^c32].[^c27]

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
Aus diesem Sachverhalt scheint sich inferieren zu lassen, dass jede Instanz der Klasse `ma:Person` immer auch einer Instanz von `ma:Objekt_Domäne`, `ma:Instrument_nach_Vokabular_(Domäne)` sowie `ma:Aufführung_(Domäne)` zugleich zugeordnet ist.[^c8683]
Eine Aussage, wie
\

"Person a ist an dem Ereignis 'Uraufführung' beteiligt (spielt jedoch nicht auf dem Museumsobjekt b)" 
\

wäre demnach nicht möglich.

Einen Ausweg scheint in die Möglichkeit zu bieten, eine übergeordnete Klasse für die Entitäten `ma:Instrument_nach_Vokabular_(Domäne)` sowie `ma:Objekt_Domäne` zu erschaffen und die Verwendung von `ma:Interpret` mit `rdfs:domain` auf diese Oberklasse (`ma:Instrument_(Domäne)`) zu beschränken.[^c8684]
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

Die *open world assumption* bringt es mit sich, dass eine Validierung von in RDF strukturierten Daten naturgemäß eigentlich nicht vorgesehen sein kann.[^c8685] Hieran ändert auch – trotz des Namens – RDFS kaum etwas: "Unlike XML Schema, RDF Schema is generally interpreted as supplementing rather than validating RDF data."[^c8686] Dennoch sind die Möglichkeiten von RDFS – etwa gegenüber dem sehr viel mächtigeren, dafür aber umso komplexeren OWL DL –[^c8687] für die Belange dieses Metadatenprofils absolut angemessen,[^c8691] nicht zuletzt da es gilt, Überkomplexität aufgrund seiner Anwendungs- und Anwenderorientiertheit insbesondere zu vermeiden.[^c8690]
Man spricht in solchen Fällen von sogenannten "lightweight ontologies", die "in der Regel nur aus einer Konzepthierarchie sowie Relationen, für die jeweils Domain und Range Einschränkungen [sic!] angegeben werden[, bestehen]."[^c8692] Gegenüber dem Vokabular, das lediglich eine Bestandsaufnahme der für diese Arbeit relevanten Konzepte und deren Klassifikation darstellte, ist kraft der Properties eine weitere ontologische Dimension hinzugekommen (vgl. Abbildung): phänomenologisch gesprochen wird das zuvor lediglich Vorhandene kraft seiner Bezogenheit um die Dimension intentionaler[^c8693] Bestimmtheit erweitert. Es wird so ein Stück weiter in Richtung eines sinnhaften "Zuhandenenseins" innerhalb des Verständnishorizonts eines wie auch immer gearteten wahrnehmenden Subjekts entwickelt. 

Wenn an dieser Stelle der Begriff (lightweight) Ontologie – auch wenn diese Arbeit den Begriff im Allgemeinen als zu bedeutungsschwer für sich scheut – ausnahmsweise Verwendung findet, so ist mit ihm also genau diese Qualität gemeint. Das Anwendungsprofil ist, gemessen an seinem Potential Seinsstrukturen einer Welt darstellen zu können, qualitativ als Ontologie zu betrachten. Gemessen an seiner Funktionalität, die es als Schema für Mapping und Datenanreicherung auszeichnet, ist es ein Anwendungsprofil.

[transitivity in Hierarchien? Muss ich da was machen?]


