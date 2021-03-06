# Modellierung und Klassifizierung mit RDF

## Anwendungsmodellierung

Insgesamt erscheint es als sinnvoll, zuerst die bereits in Kapitel #Desiderat angerissenen Anforderungen nochmals zu schärfen und aus ihnen ein Modell zu generieren, das künftig als diskursive Grundlage für die spätere Ausarbeitung herhalten kann. Dies soll in einem zweistufigen Prozess geschehen, während dessen zunächst ein informelles Anwendungsmodell generiert wird, aus dem wiederum ein formalisiertes Datenmodell in Form eines *ERM*s (Entity Relationship Model) abgeleitet werden kann. Dieses wiederum wird die Grundlage für die RDF-Modellierung bieten.
Dieses Vorgehen gewährleistet, dass sich das Anwendungsprofil an den tatsächlichen in der Praxis vorgefundenen Erfordernissen ausrichtet und sich nicht etwa "in vorauseilendem Gehorsam" anhand im Semantic Web bereits vorhandener Darstellungsmöglichkeiten ausrichtet und selbst zensiert. (In Vorgriff auf die terminologische Ausarbeitung heißt dies etwa: domänenspezifische Vokabulare dahingehend zu untersuchen, ob sie in der Lage sind, das Geforderte abzubilden und andernfalls nach Möglichkeiten zu suchen, diese Darstellungsmöglichkeiten selbst zu schaffen.)
Jedoch darf diese scheinbare Übersimplifizierung, die zunächst also jederlei Eindeutigkeit – etwa in Form von Normdaten – vermeidet, keineswegs als solche missverstanden werden. Vielmehr bildet sie die eigentliche Prämisse für spätere grundsätzliche terminologische Anschlussfähigkeit und Interoperabilität, indem sie sich nicht auf bestimmte gebräuchliche Datenstrukturen oder eine bestimmte Domäne fixiert. 

![Datenmodell – Beziehungen ausgedrückt als Verbindungslinien zwischen den umkreisten Entitäten](medien_Kap3/20200801_szenario.png)



### "Domäne"[^nc8660]

1) Dies wird etwa im Falle der Entität *BWV 208* deutlich: Das "Label" "BWV 208" referenziert hier die Kantate auf Werkebene und fungiert als Platzhalter[^nc8650] für eine Expression[^nc8651] (etwa der in RISM beschriebenen Quelle),[^nc8649] eine Manifestation[^nc8652] (etwa eine Edition), oder aber auch eines Exemplars[^nc8653] (etwa einer, freilich verdammenswerterweise, mit Bleistift eingerichteten Ausgabe in einer Bibliothek).

2) Über die Beziehung "Besetzung" mit der Entität Werk verbunden ist die Entität *Corno da caccia*, im Modell mit dem – willkürlichen – Label "cor da caccia", der Terminologie von RISM folgend, versehend. Auch an dieser Stelle ist das Label völlig flexibel – analog also zur Entität *BWV 208*.

3) Bei der Entität *MIMUL Inv.-Nr. 1663*[^n1q] handelt es sich um ein Objekt, das in dieser Arbeit exemplarisch als materielles Gegenpart zum Term "cor da caccia" geführt wird.[^n2q]

Die Entitäten dieses Bereichs sind institutions-, sparten-, domänenspezifisch sowie bereits etabliert und stehen daher für dieses Metadatenprofil nicht zur Disposition. Das spätere Datenmodell wird daher an dieser Stelle keinen präskriptiven Charakter für sich beanspruchen können. Jedoch werden entsprechende Beispielentitäten aus der Kulturerbe-Domäne im Folgenden angelegt, um Anschlussfähigkeit des Metadatenprofils in diese Domäne simulieren und prüfen zu können.

### Mapping

Beim Mapping-Anteil steht einerseits die Vernetzung zwischen Objekt und Werk im Vordergrund, zum anderen kann hier die Disambiguierung unklarer Terminologie erfolgen.
Die Anbindung der Besetzungsentität *Corno da caccia* an die Objekt-Entität kann in zweierlei Weise erfolgen:

3) durch ein direktes In-Beziehung-Setzen zwischen Term und Objekt. Hier sind mehrere Arten der Beziehung denkbar: 
- Einerseits könnte es sich beim Objekt um exakt jenes handeln, das Bach für das Werk besetzt hatte.[^nc8655].
- In den meisten Fällen jedoch wird eine dermaßen eindeutige Beziehung nicht nachzuvollziehen sein. Vielmehr wird – wie ja auch im Falle von BWV 208 – auf ein ungefähres Äquivalent zu verweisen sein.

4) durch das Mapping über eine zwischengelagerte Klassifikation. Dieses erscheint etwa im hier verwendeten Falle sinnvoll, um den Term "cor da caccia" weiter zu disambiguieren. Unsinnig erscheint dieser Ansatz hingegen, wenn im Bereich der Domäne ein maschinenlesbares und bereits gemapptes Standardvokabular (etwa GND, IAML MoP etc.) Verwendung findet – auch wenn diese, wie bereits erwähnt, mitunter sehr zu wünschen übrig lassen.

### Anreicherung

Nachdem die Besetzungsentität durch Verknüpfung mit einem Objekt bzw. einer Klassifikation eindeutig bestimmt worden ist, ist es wünschenswert, sie durch weitere Aussagen anzureichern und dadurch noch aussagekräftiger zu machen.

5) Die Hörner sind im Autograph "in F" notiert – der tatsächliche Klang der in F notierten Töne der Hornstimme liegt also eine Quinte tiefer. Dies wird durch die Beziehung der Besetzungsentität zu ihrer relativen Stimmung "in F" ausgedrückt. Auch für das Objekt könnte bekannt sein, dass es in F gestimmt ist (= das Instrument produziert Töne der sog. *Naturtonreihe* über dem Ton *f*).

> Aus diesem Umstand lassen sich – zumindest für die Zeit bis zur Erfindung des Ventilhorns – sehr facettierte Aussagen zum vorgesehenen Instrument treffen (Länge, Mensur etc.), deren Darstellung jedoch für den begrenzten Rahmen dieser Arbeit keine Rolle spielen kann. Außerdem liefert die Angabe der Stimmung der Hörner – ebenfalls begrenzt auf die Zeit bis zur Erfindung des Ventilhorns – einen Indikator für die Bestimmung der Tonart (wie auch im Fall von BWV 208: Die Kantate steht in F-Dur).

6) Der Besetzungsentität ist in ihrer Eigenschaft als Besetzung für *BWV 208* ein bestimmter Tonvorrat zu eigen, der sich durch die Entität *Ambitus* ausdrückt. Dieser wiederum setzt sich aus einer Tonmenge zusammen, die durch die beiden Entitäten des höchsten und des tiefsten Tons eingegrenzt wird.

>Die Kenntnis des Ambitus' lässt in wissenschaftlicher Hinsicht vielerlei Rückschlüsse zu: etwa auf die Länge des Instruments (Faustregel: kürzer = Tonvorrat liegt höher). Für Musiker (etwa Anfänger) könnte diese Information selbstverständlich bei der Suche nach Noten ebenfalls außerordentlich nützlich sein.

7) Im in dieser Arbeit gewählten Szenario ist aus physikalischen Gründen das Stimmungssystem des *Corno da caccia* eindeutig und kann hier berücksichtigt werden.[^nc8657] Tatsächlich ist das Bestimmen historisch verwendeter Stimmungssysteme in vielen Fällen weit weniger eindeutig.

8) Über die Stimmhöhe der ursprünglich vorgesehenen Instrumente, wie auch für das Objekt *MIMUL 1663* selbst, lässt sich keine eindeutige Aussage treffen. Gleichwohl ist diese Entität grundsätzlich durchaus als aufschlussreich für die Wissenschaft anzusehen.[^nc8658] Somit handelt es sich bei der Angabe *a'* = 415 Hz um einen vermuteten Wert, und es ergibt sich für den Fortgang der Arbeit die Frage, ob es in einem späteren Datenmodell möglich sein wird, auch Ambivalenzen und Unsicherheiten dieser Art abzubilden.

9) Über die Beziehung "Klangbeispiel" ist es möglich, die Objektentität oder die Typ-Entität mit einem Klangbeispiel zu verknüpfen. Selbstverständlich wäre dies im gleichen Maße auch für eine Werkentität denkbar.

10) Denkbar ist, dass eine Person – etwa im Rahmen einer Audioaufnahme – auf einem bestimmbarenen Instrument spielt. Hier wäre also eine Verknüpfung zwischen Besetzung (evtl. Werk), Person und Objekt wünschenswert.

Tatsächlich sind den potentiellen Anwendungsszenarien eines solchen Modells keine Grenzen gesetzt. Angesichts der Komplexität und der vielfältigen spezifischen Anforderungen, die trotz der Beschränkung auf BWV 208 und das *Corno da caccia* erarbeitet wurden, lässt sich bestenfalls erahnen, welches Darstellungspotential eine Erweiterung des Modells für andere Instrumente und Instrumentengruppen bergen könnte: Es ließe sich etwa die Skordatur von Saiten ausdrücken. Oder verschiedene Sing- und Spieltechniken – vom Jodeln bis zum Spiel *con sordino* etc.


## Klassifikatorische Erschließung [umbenennen?]


Das folgende Kapitel bildet den Ausgangspunkt dafür, den Weg von einem auf dem Reißbrett entworfenen, Anwendungsszenario zu einem formalisierten, Semantic Web-kompatiblen Metadatenprofil zu beschreiten.  Gemäß Noy und McGuinness[^nc8] steht dabei ganz zu Beginn des Prozesses hin zur Ontologie zunächst eine Klassierung[^nc9] der benötigten Typen nach folgendem Schema:

> "Define the classes and the class hierarchy"

> "Define the properties of classes [...]"

> "Create instances"

Tatsächlich hat sich im Verlauf dieser Arbeit ganz organisch eine andere Reihenfolge ergeben: Nach dem exemplarischen Auffinden eines Defizits wurde ein spezifisches Szenario entworfen, um dieses zu beheben: Einige wichtige Instanzen[^nc11] wurden bereits im vorhergehenden Kapitel identifiziert und aufgeführt.\

Das Produkt dieses Kapitels bildet eine zunächst auf den Anwendungsbereich beschränkte "Ontologie", die auf sehr elementarer Ebene imstande ist, das Anwendungsszenario mit formalisierten Sprachen wiederzugeben. 

### Entity Relationship Model

Ein erster möglicher Schritt in Richtung einer Modellierung mit RDF ist die Überführung des Anwendungsmodells in ein Modell in Form eines *Entity Relationship Models* (ERM). Wichtig ist gleich eingangs darauf hinzuweisen, dass auch das ERM zunächst ebenfalls lediglich eine Eskalationsstufe auf dem Weg zur RDF-"Ontologie" darstellt, das wohl, wie auch das "Anwendungsszenario" Gegenstand vielfacher Veränderungen wird sein müssen. Hierbei sollen die anwendungsspezifischen Szenarien strukturiert und auf eine allgemeine Ebene gesetzt werden, auf der übergeordnete Entitätsklassen und ihre Eigenschaften in Beziehung zueinander stehen.[^nc8661] So werden Klassen definiert und erste einfache hierarchische Relationen zwischen Klassen und untergeordneten, "beschreibenden" Klassen (Eigenschaften) hergestellt.

Beziehungen wiederum können in diesem ERM ebenfalls zunächst als potentielle zukünftige "Eigenschaftsklassen" verstanden werden, die zukünftig Container für weitere "Untereigenschaften" darstellen können.[^nc8668]
Im ERM fungieren besondere Schlüsseleigenschaften ("Primärschlüssel") als eindeutige Identifier einer Entität. Es ist zu erwarten, dass diese in einer RDF-Modellierung keine Rolle spielen werden, da dort eindeutige Referenzierbarkeit bereits dank URIs gegeben ist. [^nc8662] Mengenverhältnisse zwischen Entitäten werden im ERM zudem durch "Kardinalitäten" miteinbezogen und dadurch fixierbar.[^nc8663] 

![Entity Relationship Modell: farbige Markierung externer Entitäten. Entitäten sind in Rechtecken, Eigenschaften in Ovalen, Beziehungen in Rauten eingefasst. Schlüsseleigenschaften sind durch Unterstreichung gekennzeichnet.](medien_Kap3/20200801_ERM.png)

Einige wesentlichen Entwicklungen gegenüber dem Anwendungsmodell sowie weitere Überlegungen sind es wert, nochmals kurz erläutert und erörtert zu werden.

* Wie bereits erwähnt sind den Entitäten des ERM gegenüber denen der Anwendungsmodellierung weitere sie beschreibende Eigenschaften hinzugefügt worden (etwa *Name* zu *Person*)

* Neben dem verwendeten Instrument *Instrument nach Vokabular* muss die Entität *Interpret* auch immer an ein Ereignis, in der Regel eine *Aufführung* geknüpft sein (diesem Umstand wurde durch die Zusätze im linken Domänenbereich Rechnung getragen). Dabei sind folgende Szenarien berücksichtigt: ein Instrument kann sowohl mehrfach ("n Mal") mit beliebig vielen *Interpreten* besetzt sein (entspricht beispielsweise der Bezeichnung "2 Oboen" oder "Celli" in einer Partitur) als auch gesondert aufgeführt werden (entspricht etwa dem Sachverhalt "Musiker a und Musiker b spielen vierhändig Klavier").

* Die Verknüpfung zwischen Ereignis und Werk kann in gleichem Maße auch für Ereignis und Objekt gelten – etwa wenn ein bestimmtes Objekt in einer Aufführung verwendet wird. Dieser Sachverhalt ist der besseren im ERM **nicht** dargestellt! Es wird an späterer Stelle gelten, dies umzusetzen. 

* Ein *Instrument nach Vokabular* kann innerhalb eines Werks beliebig viele notierte *Stimmungen* besitzen.[^nc8665]. Die Bedeutung der Entität *Stimmung* – etwa mit dem Wert "F" – weicht dabei in der Kombination mit *Instrument* von der der Verwendung in Kombination mit *Objekt (Domäne)* ab: In dieser Kombination bezieht sich die Entität *Stimmung* auf die mögliche "Grundstimmung" eines Objekts (z.B. F-Horn), sofern es eine besitzt (s. auch #kapitel).[^nc8666]

* Mithilfe einer Kombination gegebener Informationen zu *Stimmung* und notiertem *Ambitus* sollte es im Zuge eines späteren Schrittes möglich sein, Informationen zu den *klingenden Tönen* maschinell abzuleiten (s. #kapitel).

* Im ERM ist definiert, dass ein *Instrument nach Vokabular (Domäne)* nur eine (variable) *Stimmhöhe* besitzen kann. Denkbar wären jedoch auch z.B. Sachverhalte – Konzerte, Aufnahmen etc. – in deren Verlauf mehrmals umgestimmt wird. In diesen Fällen wäre auch eine Verknüpfung mit der Entität *Aufführung* angebracht. Um den Umfang dieser Arbeit jedoch in Grenzen zu halten, kann nicht jedem denkbaren Szenario in ihr Rechnung getragen werden. Vielmehr würden sich solche tiefergehenden Überlegungen im Rahmen einer Weiterentwicklung des Metadatenprofils empfehlen.

* Grundsätzlich ist wünschenswert – wie im Fall des *Interpreten* oder dem Umstimmen von Instrumenten – bestimmte Entitäten mit Ereignissen verknüpfen zu können. Dies gilt insbesondere für die Entitäten *Stimmungssystem* (wird mit historisch akkurater gespielt, oder wohltemperierter Stimmung gespielt?) , *Stimmhöhe* (wird mit den heute üblichen 440 Hz musiziert, oder mit einer historischen Stimmung, z.B. gemäß dem sog. *Cornettton*[^nc8667]?), *Klangbeispiel* (Das Klangbeispiel stammt aus der und der Aufnahme) und *Instrument (Klassifikation)* (bei der Uraufführung fand Instrument a Verwendung, in der Aufnahme x ein typ-verschiedenes). 

Für die Zwecke dieser Arbeit ist es ausreichend, die zuletzt genannten Anwendungsszenarien im ERM lediglich einmal exemplarisch im Kontext des *Interpreten* anzudeuten.




### Klassifikation und Transformation mit RDF, RDFS und OWL

Das zuletzt ausgearbeitete Modell befindet sich gewissermaßen noch außerhalb des Erkenntnishorizonts des Semantic Web. Diesen Erkenntnishorizont zu überwinden und eine minimale semantische – wenn auch zunächst nicht primär eine technische – Anschlussfähigkeit zu erreichen, ist Anliegen dieses Kapitels. Dazu wird es gelten, die Konzepte des ERM nochmals zu hinterfragen.

Der Vorgehensweise im weiteren Verlauf liegt zugrunde, dass in RDF bereits bestimmte Klassen angelegt sind – in Folgevokabularen[^nc10] um weitere ergänzt –, die verwendet werden können, um Konzepte zu klassifizieren.[^nc13] Dabei erscheinen angesichts der zuvor ausgearbeiteten Anwendungsmodellierung die allgemein gebräuchlichsten drei Klassen[^nc12] für die Zwecke dieser Arbeit ausreichend. Diese sind:

1. Klassen

2. Instanzen

3. Relationen (im Folgenden auch "Properties")

Es mag an dieser Auflistung auffallen, dass in RDF das Konzept von Attributen gegenüber dem ERM keine ausgezeichnete eigene Entitätsklasse mehr bildet. Dies ist unmittelbar einleuchtend, kann doch jede RDF-Entität auch als Subjekt eines Tripels agieren (somit erscheint das von seiner Bezugsentität abhängige und auf ihn verweisende Attribut mit RDF inkompatibel).
Durch die Aufteilung in (theoretisch also gleichgestellte) Entitäten und Beziehungen lassen sich bereits vollwertige RDF-Tripel bilden – zusätzlich gelingt es, dank der qualitativen Unterscheidung in Instanz und Klasse, einfache hierarchische Sachverhalte nachzubilden. In den folgenden Unterkapiteln wird es nun darum gehen, eine entsprechende Klassierung am Gegenstand der erarbeiteten Konzepte vorzunehmen.

Doch worin besteht an dieser Stelle der tiefere Sinn einer Klassifikation? Direkt assoziativ ist die Funktion des Klassierens – sofern man sie nicht als reinen Selbstzweck betreibt – insbesondere mit der Ordnung von Ressourcen und deren Retrieval. Doch neben dieser "pragmatischen Aufgabe"[^nc23] führt Bertram auch die "erkenntnisvermittelnde Aufgabe" von Klassifikationen ins Feld, die in der "Aufhellung von Zusammenhängen anhand geordneten Wissens" besteht.[^nc14] Diese so angedeutete hermeneutische Dimension erscheint auch bei der RDF-Klassifizierung ganz zentral: Das Modell, das in seiner gegenwärtigen Form auf einem subjektiv geprägtem Verständnis, Wertesystem und persönlichen Denkstrukturen des Autors beruht, wird in ein objektives, standardisiertes System überführt. Gewissermaßen findet so eine Übersetzung statt, die den Erkenntnishorizont zwischen Mensch und Maschine überwindet. Das eigene Denkmodell wird dabei mithilfe der formalsprachlichen Ausdruckmittel des Semantic Web erfasst und ausgezeichnet, und so in das von RDF-vorgegebene "Erkenntnisschema" einsortiert. Die dem Modell inhärente Semantik wird – wie zu sehen sein wird, freilich zunächst auf einer sehr oberflächlichen Ebene – dadurch objektiviert und gemeinhin auslegbar.\

#### Vorgehensweise

Diese Übersetzung geht mithilfe entsprechend standardiserter, sich ergänzender Modellierungssprachen, den sogenannten "Ontologiesprachen", vonstatten.[^nc16] 
Die durch den W3C standardisierten "Grundpfeiler" des Semantic Web bilden dabei insbesondere die Sprachen RDF (Ressource Description Framework),[^nc8675] RDFS (RDF Schema)[^nc8676] und OWL (Web Ontology Language[^nc17], der "inzwischen [...] meistbenutzen Ontologiesprache aller Zeiten"[^nc19].

Die formale Interpretierbarkeit der durch die Sprache ausgedrückten semantischen Komponente wird durch eine Syntax, also einer  "Menge von Regeln, um Programme oder Dokumente mit bestimmten Eigenschaften [...] zu erzeugen",[^nc8677] ermöglicht. Die Entscheidung für eine bestimmte Syntax ist dabei im Falle nach RDF strukturierter Daten zwar letztlich arbiträr, bilden sie doch im übertragenen Sinne gewissermaßen lediglich "Verpackung und Beipackzettel" für den eigentlichen semantischen Inhalt. Doch fällt aufgrund seiner Einfachheit und Übersichtlichkeit in dieser Arbeit die Wahl auf das sogenannte *Turtle*-Format ("Terse RDF Triple Language")[^nc20].

Dabei erfolgt die Disambiguierung der Konzepte analog zur Klassifizierung in folgender Form (s. auch #Kapitel (klassen und instanzen??)):

* "Typ ist eine Klasse"

* "Typ ist eine Instanz"

* "Typ ist eine Eigenschaft"[^nc5] 

Durch die klassifikatorische Erfassung der Instanzen, Entitäten und Beziehungen aus der Anwendungsmodellierung bzw. der Klassen, Eigenschaften und Beziehungen des ERM ergibt sich ein sehr einfaches kontrolliertes Vokabular – etwa im sehr grob gefassten Sinne des *National Information Standards Organization* und des *American National Standards Institute*.[^nc21] Durch die Zuordnung von Instanzen zu Klassen ergeben sich zudem erste taxonomische Beziehungen.[^nc24] 
Vermöge der Klassifizierung mithilfe der Eigenschaft
```
rdf:type
``` 
werden zudem ontologische Aussagen zu den Einzelkonzepten getroffen. So werden alle konzeptuell-kategorialen Verhältnisse innerhalb des Erkenntnishorizonts des Semantic Web formalsprachlich übersetzt und verstehbar.


### Vokabular

Das gemäß den eben beschriebenen Maßgaben strukturierte und ausgezeichnete Vokabular ist durch Publikation im Online-Repositorium dieser Arbeit[^n3q] im Netz referenzierbar und kann dort abgerufen werden.

#### Bemerkungen zum Vokabular

##### Namensraum und Benennung

Auch wenn keine abschließenden Definitionen der hier geschaffenen Terme erstellt worden sind, lässt sich bereits jetzt die sehr allgemeine Aussage treffen, dass ihr semantischer Gehalt sich darin ausdrückt, wie sie in dieser Arbeit Verwendung finden. Es ist möglich, diese freilich bislang nicht im Einzelnen aussagekräftige, doch trotzdem in so fern definierte und abgrenzbare semantische Reichweite von Vokabular im Bezug zu sogenannten*Namensräumen*[^nc8670] – referenzierbare kontrollierte Vokabulare – festzulegen. Die Namensraumzugehörigkeit der Terme dieser Arbeit wird im Folgenden zunächst durch das Präfix *ma:* gekennzeichnet. Der Namensraum ist am folgenden Ort, 

 https://raw.githubusercontent.com/SPARQLCRMSUPPE/VocsForInstruments/master/namespaces/ma,

hinterlegt.

Eine menschenlesbare Definition der einzelnen Terme, wie sie als gute Praxis gemäß dem W3C (*World Wide Web Consortium*) nahegelegt wird,[^nc8673] wäre aufgrund der voraussichtlichen terminologischen Unbeständigkeit zum gegenwärtigen Zeitpunkt noch verfrüht.

##### Instanzen (owl:namedIndividuals) und Klassen (owl:class, rdfs:subClassOf)

Die bei der Differenzierung zwischen Klasse und Instanz (owl:namedIndividual)[^nc8672] oftmals  vorgeschlagene Vorgehensweise,[^nc2] bei der die niedrigste Entität eines aus Klassen bestehenden hierarchischen Strangs als Instanz zu werten ist, mag im Falle einer in sich abgeschlossenen Ontologie als  sinnvoll erscheinen. Doch muss der Blickwinkel im Fall der hier beabsichtigten Anwendung als verbindendes Metadatenprofil auch auf potentielle Anknüpfungspunkte, aber vor allem auf die Anwendungsfälle und Vokabulare, die gewissermaßen "außerhalb" des Profils liegen, erweitert werden. Die Frage also, ob etwas eine als Instanz oder eine Klasse zu verstehen ist, liegt nicht notwendigerweise in der hierarchischen Ebene begründet. Im Falle des *Barockhorns* wird dies insbesondere deutlich:
```
ma:Barockhorn_(Mitteldeutschland) rdf:type owl:Class ;
                                    rdfs:subClassOf ma:Instrument_(Klassifikation) .
```
Es ist einleuchtend, dass die Bestimmung einer Klasse (Barockhorn) als Instanz, auch wenn sie sich auf der untersten hierarchischen Ebene befindet, unsinnig ist.

>> Zur obigen Schreibweise: Es handelt sich um zwei "Tripel". Das Subjekt des Tripels in Zeile 1 wird dank des`;` (im Gegensatz zum `.`) auf die Aussage ("Statement") in Zeile 2 übertragen. Gleichbedeutend wäre die Schreibweise:

```ma:Barockhorn_(Mitteldeutschland) rdf:type owl:Class .
   ma:Barockhorn_(Mitteldeutschland) rdfs:subClassOf ma:Instrument_(Klassifikation) .```

##### Identifier

Während in einer relationalen Datenbank das Schlüsselattribut einer Entität variabel sein kann, erfolgt die eindeutige Referenzierung von Konzepten – darunter auch Entitäten – im Semantic Web grundsätzlich anhand von URIs (Uniform Ressource Identifier).[^nc8671] Eine konzeptuelle Trennung zwischen Entität und seinem eindeutigen Identifier, wie im ERM, ist im Semantic Web nicht denkbar: Die URI selbst erscheint vielmehr gewissermaßen als digitale Manifestation des durch sie repräsentierten nichtdigital existierenden Konzepts. URIs sind also im Gegensatz zur Repräsentation im ERM keine eigenständigen Konzepte mehr, sondern sie "sind" die Konzepte:

Bei den syntaktischen Elementen der Aussage
```
ma:Klangbeispiel rdf:type owl:Class .
```

etwa sind die Konzepte mit ihrem jeweiligen Namensraum präfigiert und über den Header der Datei zu vollständigen URIs auflösbar:[^n4q]

Header:
```
@\prefix ma: <https://github.com/SPARQLCRMSUPPE/VocsForInstruments/blob/master/namespaces/ma#> .
@\prefix owl: <http://www.w3.org/2002/07/owl#> .
@\prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#&gt .
```

löst auf zu:

```
https://github.com/SPARQLCRMSUPPE/VocsForInstruments/blob/master/namespaces/ma#klangbeispiel
http://www.w3.org/2002/07/owl#class
http://www.w3.org/1999/02/22-rdf-syntax-ns#type
```


##### Attribute und Properties

* Ein Nebeneffekt der Transformation des ERM nach RDF ist, dass Attribute von Entitäten von diesen als nunmehr eigenständige Entitäten entkoppelt sind, und somit dem ERM entsprechende Tripelbeziehungen nicht möglich sind. Dieses Problem lässt sich in der Regel einfach lösen, indem entsprechende Entitäten und Properties erschaffen werden.

##### Weitere Anmerkungen

* Analog zur Defintion von Klassen (owl:Class) und Unterklassen (rdfs:subclassOf) ist es mit *rdfs* möglich, Untereigenschaften (rdfs:subPropertyOf) zu Eigenschaften zu bilden.[^nc8674] Dies ist im Falle der Eigenschaften *genaue Entsprechung* und *ungefähre Entsprechung* nützlich, indem sie der Eigenschaft *Entsprechungsgrad* subsumiert werden.

* Aus Gründen der Kohärenz und der klassifikatorischen Konsolidierung wurde eine Oberklasse `ma:Ton` eingeführt.



## Spezifizierung von Relationen mit *rdfs:range* und *rdfs:domain*

Eines der zentralen Konzepte des Semantic Webs ist die sog. *open world assumption*.[^nc8682] Gemäß dem vielzitierten Leitsatz "Anyone can say anything about anything"[^nc8678] besagt sie, dass eine Aussage, die in einem Modell nicht explizit verankert ist, nicht notwendigerweise falsch sein muss, sondern dass lediglich keine Aussage über ihre Richtigkeit getroffen werden kann.[^nc8679] Es muss somit im Interesse eines RDF-Vokabulars liegen, sein semantisches Ausdruckspotential fort von der Summe alles Möglichen (und somit Willkürlichen) hin zum eigentlich Aussagekräftigen fokussieren zu können, indem es Hinweise zur sinnhaften Verwendung seiner Terme bereithält. Die Möglichkeit einer solchen Fokussierung bieten Ontologiesprachen wie RDFS und OWL, indem sie in RDF formalisierte und somit direkt integrierbare "Anwendungsregeln" zu Properties anbieten.[^nc8680]
Es liegt dabei auf der Hand, dass für ein Applikationsprofil, dessen Sinn darin besteht, schematische Rahmenbedingungen zu schaffen, entlang derer sich Anwender ausrichten und orientieren können, ein hohes Maß an semantischer Fixiertheit insbesondere unabdingbar ist.

Doch werden kraft dieser Schemata keineswegs lediglich die Wirkungsweite von Relationen abgesteckt. Vielmehr entsteht durch sie eine weitere Bedeutungsdimension, die die Grundlage dafür bietet, auch maschinell inhärente logische Schlussfolgerungen (Inferenzen) ziehen zu können (Reasoning).[^nc8681]

Während im Vokabular Properties in Form kontingenter, semantisch ungerichteter Bestandteile einer Liste aufgezählt waren, kann im Folgenden ihre Anwendung in Abhängigkeit zu den durch sie in Relation gesetzten Entitäten näher beschrieben werden.[^nc33] Diesen Schritt zu vollziehen, ermöglichen die Properties *rdfs:range*[^nc31] und *rdfs:domain*[^nc32].[^nc27]

1) Die Wirkung dieser begrenzenden Properties wird im folgenden Beispiel verdeutlicht:

Obwohl die Aussage
```
ma:Person_a ma:hat_Frequenz ma:Lizenz .
```
angesichts der *open world assumption* legitim ist, ist es sinnvoll die Anwendung von `ma:hat_Frequenz` gemäß Anwendungsmodell nur auf bestimmte Subjekte und Objekte auszurichten.
Im Szenario 
```
ma:a' ma:hat_Frequenz ma:415Hz .
```
bezieht sich `ma:hat_Frequenz` auf ein Subjekt aus der Klasse `ma:Ton` (es ist zudem bekannt, dass auch andere Töne Frequenzen besitzen). Zum anderen auf ein Objekt der Klasse Frequenz (mit weiteren möglichen Instanzen, wie 415 Hz etc.).
Somit lässt sich mit der Zuweisung 
```
ma:hat_Frequenz rdfs:domain ma:Ton .
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
Aus diesem Sachverhalt scheint sich inferieren zu lassen, dass jede Instanz der Klasse `ma:Person` immer auch einer Instanz von `ma:Objekt`, `ma:Instrument_nach_Vokabular` sowie `ma:Aufführung` zugleich zugeordnet ist.[^nc8683]
Eine Aussage, wie
\

"Person a ist an dem Ereignis 'Uraufführung' beteiligt (spielt jedoch nicht auf dem Museumsobjekt b)" 
\

wäre demnach nicht möglich.

Einen Ausweg scheint in die Möglichkeit zu bieten, eine übergeordnete Klasse für die Entitäten `ma:Instrument_nach_Vokabular` sowie `ma:Objekt` zu erschaffen und die Verwendung von `ma:Interpret` mit `rdfs:domain` auf diese Oberklasse (`ma:Instrument`) zu beschränken.[^nc8684]
Die Koppelung von Person und Ereignis scheint hingegen eine allgemein gültige.
Somit lautet die neue Definition von `ma:Interpret`:
```
ma:Interpret rdf:type owl:ObjectProperty ;
	rdfs:domain		ma:Instrument ;
 	rdfs:domain		ma:Aufführung ;
 	rdfs:range		 ma:Person		.
```
Bezugnahme auf die neue Superklasse `ma:Instrument` kann nun auch auf analoge Sachverhalte im Falle von `ma:hat_Stimmung_(absolut)`, `ma:hat_Stimmungssystem` sowie `ma:hat_Klangbeispiel` angewendet werden.
\

### Vom Vokabular zur "Lightweight Ontology" 

Die *open world assumption* bringt es mit sich, dass eine Validierung von in RDF strukturierten Daten naturgemäß eigentlich nicht vorgesehen sein kann.[^nc8685] Hieran ändert auch – trotz des Namens – RDFS kaum etwas: "Unlike XML Schema, RDF Schema is generally interpreted as supplementing rather than validating RDF data."[^nc8686] Dennoch sind die Möglichkeiten von RDFS – etwa gegenüber dem sehr viel mächtigeren, dafür aber umso komplexeren OWL DL –[^nc8687] für die Belange dieses Metadatenprofils als angemessen zu betrachten,[^nc8691] nicht zuletzt da es gilt, Überkomplexität aufgrund seiner Anwendungs- und Anwenderorientiertheit insbesondere zu vermeiden.[^nc8690]
Man spricht in solchen Fällen von sogenannten "lightweight ontologies", die "in der Regel nur aus einer Konzepthierarchie sowie Relationen, für die jeweils Domain und Range Einschränkungen [sic!] angegeben werden[, bestehen]."[^nc8692]\

Gegenüber dem Vokabular, das lediglich eine Bestandsaufnahme der für diese Arbeit relevanten Konzepte und deren Klassifikation darstellte, ist kraft der Properties eine weitere ontologische Dimension hinzugekommen **(vgl. Abbildung)**: phänomenologisch gesprochen wird das zuvor lediglich Vorhandene kraft seiner Bezogenheit um die Dimension intentionaler[^nc8693] Bestimmtheit erweitert. Es wird so ein Stück weiter in Richtung eines sinnhaften "Zuhandenenseins" innerhalb des Verständnishorizonts eines wie auch immer gearteten wahrnehmenden Subjekts entwickelt. 

Wenn an dieser Stelle der Begriff (lightweight) Ontologie – auch wenn diese Arbeit den Begriff im Allgemeinen als zu bedeutungsschwer für sich scheut – ausnahmsweise Verwendung findet, so ist mit ihm also genau diese Qualität gemeint. Das Metadatenprofil ist, gemessen an seinem Potential Seinsstrukturen einer Welt darstellen zu können, qualitativ als Ontologie zu betrachten. Gemessen an seiner Funktionalität, die es als Schema für Mapping und Datenanreicherung auszeichnet, ist es ein Metadatenprofil.

---

[^nc2]: Vgl. etwa die Aussage "  &lt;!\-\- /\* Font Definitions */ @font-face {font-family:"Cambria Math"; panose-1:2 4 5 3 5 4 6 3 2 4; mso-font-charset:0; mso-generic-font-family:roman; mso-font-pitch:variable; mso-font-signature:-536870145 1107305727 0 0 415 0;} @font-face {font-family:Cambria; panose-1:2 4 5 3 5 4 6 3 2 4; mso-font-charset:0; mso-generic-font-family:roman; mso-font-pitch:variable; mso-font-signature:-1610611985 1073741899 0 0 159 0;} /* Style Definitions */ p.MsoNormal, li.MsoNormal, div.MsoNormal {mso-style-unhide:no; mso-style-qformat:yes; mso-style-parent:""; margin:0cm; mso-pagination:widow-orphan; font-size:12.0pt; font-family:"Cambria",serif; mso-ascii-font-family:Cambria; mso-ascii-theme-font:minor-latin; mso-fareast-font-family:Cambria; mso-fareast-theme-font:minor-latin; mso-hansi-font-family:Cambria; mso-hansi-theme-font:minor-latin; mso-bidi-font-family:"Times New Roman"; mso-bidi-theme-font:minor-bidi; mso-ansi-language:EN-US; mso-fareast-language:EN-US;} .MsoChpDefault {mso-style-type:export-only; mso-default-props:yes; font-family:"Cambria",serif; mso-ascii-font-family:Cambria; mso-ascii-theme-font:minor-latin; mso-fareast-font-family:Cambria; mso-fareast-theme-font:minor-latin; mso-hansi-font-family:Cambria; mso-hansi-theme-font:minor-latin; mso-bidi-font-family:"Times New Roman"; mso-bidi-theme-font:minor-bidi; mso-ansi-language:EN-US; mso-fareast-language:EN-US;} @page WordSection1 {size:612.0pt 792.0pt; margin:70.85pt 70.85pt 2.0cm 70.85pt; mso-header-margin:36.0pt; mso-footer-margin:36.0pt; mso-paper-source:0;} div.WordSection1 {page:WordSection1;} --&gt; emwebNSDocrepresented in a knowledge base." ([@gangler_semantic_nodate, S.18]).

[^nc4]: [@noauthor_owl_nodate]

[^nc5]: OWL2 differenziert zwischen *Object Properties* und *Datatype Properties* (vgl.: [noauthor_owl_nodate-2]). Obwohl etwa *ma:a'=415Hz* prinzipiell auch mit *Datatype Properties* modelliert werden könnte, erscheint diese Detailtiefe für den hier exemplarisch durchgeprobten Anwendungsfall nicht notwendig.

[^nc6]: [@TN_libero_mab21631588, S. 27–28.]

[^nc7]: [@TN_libero_mab213864266, S. 128]

[^nc8]: [@noy_ontology_nodate]
Auch Stuckenschmidt legt diese Vorgehensweise nahe (vgl.: [@alma9913393902586]).

[^nc9]: Zum Begriff siehe @TN_libero_mab213864266, S. 150.

[^nc10]: Für diese Arbeit spielen insbesondere RDFS ([@noauthor_rdfs_nodate]) und OWL ([@noauthor_owl_nodate-3]) eine Rolle.

[^nc11]: "Individualbegriffe"  [@stock_wissensreprasentation_2008, S. 84].

[^nc12]: In "Semantic Web-Sprache" augedrückt, wären das die Klassen *rdfs:class*, *rdfs:instanceOf* und *rdf:property*.

[^nc13]: Auf eine Übersicht der gängigen übergeordneten Klassen – etwa "Literals", "Datatypes", "Blank nodes" etc. – muss an dieser Stelle verzichtet werden.

[^nc14]: [@TN_libero_mab213864266, S. 151]

[^nc15]: [@alma9913393902586, S. 166]

[^nc16]: S. hierzu etwa: [@alma9913393902586, S. 95–99]

[^nc17]: [@noauthor_owl_nodate-3] Diese Arbeit verwendet OWL Full, das die größten Ausdrucksmöglichkeiten bietet und mit RDFS kompatibel ist. (Vgl. [@TN_libero_mab21631588, S. 125–127])

[^nc18]: 

[^nc19]:  [@alma9913393902586, S. 146]

[^nc20]: Vgl.: [@noauthor_rdf_nodate-2]

[^nc21]: [@national_information_standards_organization_u.s._guidelines_2005, S. 3]



[^nc23]: [@TN_libero_mab213864266, S. 151]

[^nc24]: Die Serialisierung erfolgt am einfachsten, indem etwa der Ontologieeditor *Protégé* zu Hilfe genommen wird. Er ermöglicht den Export von Ontologien in vielfältigen Formaten.

[^nc25]:  [@alma9913393902586, S. 169]

[^nc26]: [@alma9913393902586, S. 24]

[^nc27]: Auch in OWL verfügt über entsprechende (noch mächtigere) Möglichkeiten, diese Beziehungen auszudrücken (vgl. hierzu etwa: [@allemang_semantic_2011, S. 238-239.]) Allerdings erscheint für die Belange dieser Arbeit die Terminologie von RDFS als genügend.

[^nc28]: Wörtlich also: "Das Objekt mit der Signatur 1663 hat den Typ eines Barockhorns".

[^nc29]: [@alma9913393902586, S. 106]


[^nc31]: [@noauthor_rdf_nodate-3]

[^nc32]: [@noauthor_rdf_nodate-4]

[^nc33]: [@alma9913393902586, S. 169]

[^nc8649]: Zur spezifischen Problematik des an dieser Stelle verwendeten  FRBR/FRAD-Modells bei Werken der Musik s.  [@bicher_normdaten_2018, S. 225].

[^nc8650]: In den sogenannten *Functional Requirements for Bibliographic Data*, deren Entitätenmodell an dieser Stelle verwendet wird, heißt es: "Ein Werk ist eine abstrakte Entität; es gibt keinen entsprechenden materiellen Gegenstand." ([@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 16]).

[^nc8651]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 18–20.]

[^nc8652]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 20–22.]

[^nc8653]: [@arbeitsstelle_fur_standardisierung_funktionelle_2006, S. 22–23.]


[^nc8655]: Ein gleichermaßen illustratives wie auch charmantes Beispiel für eine solche Beziehung wären etwa Leopold Mozarts und Johann Ernst Eberlins Komposition "Der Morgen und der Abend" ([@mozart_eberlin_morgen_nodate]) für das "Hornwerk" der Festung Hohensalzburg aus dem 16. Jahrhundert, dem sog. *Salzburger Stier* ([@hocker_mechanische_2016]). (Ein lohnenswerter klanglicher Eindruck lässt sich hier gewinnen: [@noauthor_salzburger_nodate]).


[^nc8657]: Anders verhielte es sich freilich, würde mit dem hier definierten Schema beispielsweise eine Audioaufnahme einer Aufführung mit modernen Instrumenten erschlossen.

[^nc8658]: Etwa lassen die Stimmungen von unstimmbaren Instrumenten (Blockflöten, Zinken etc.) sehr präzise Rückschlüsse auf die historische Musikpraxis zu (vgl.: [@haynes_stimmton_2016]).

[^nc8659]: Nach Martin Fowler, dem Begründer des Modells: "An object model of the domain that incorporates both behavior and data." (vgl.:[@N_libero_mab2, S. 116]).

[^nc8660]: Da diese Arbeit angesichts ihres Fallbeispiels sehr stark RISM als primäre Domäne hervorhebt, kann gar nicht oft genug betont werden, dass jede andere relevante Domäne gleichermaßen im Vordergrund stehen könnte. So ist letztlich auch die Objektentität innerhalb einer Domäne, in diesem Fall dem Musikinstrumentenmuseum der Universität Leipzig, angesiedelt, das seinerseits sein Objekt mit dem RISM-Datensatz verlinken könnte, und dasselbe gilt selbstverständlich auch für Editionen, Bibliotheken, Archive, Wirtschaftsunternehmen etc.


[^nc8661]: Siehe hierzu etwa: [@alma9958916302586, S. 338–343.]

[^nc8662]: [@alma9958916302586, S. 342–343.]

[^nc8663]: [@alma9958916302586, S. 343]



[^nc8665]: Sowohl "simultan" (vgl. etwa den Hornsatz in C. M. v. Webers Ouvertüre zur Oper "Der Freischütz": "Corni in F" sowie "Corni in C"), als auch "sukszessive" ab der Klassik zwischen Sätzen und mit der zunehmenden Erweiterung des harmonischen Raums im Laufe des 19. Jahrhunderts immer mehr auch in kontingenter Abfolge. 

[^nc8666]: Tatsächlich kann diese Entität in Zusammenhang mit Objekten lediglich in Verbindung mit Instrumenten Verwendung finden, die etwa aus baulichen, physikalischen Gründen eine solche "Grundstimmung" vorweisen.

[^nc8667]: Vgl. [@haynes_stimmton_2016].

[^nc8668]: So etwa im Falle der Eigenschaft *Entsprechungsgrad* angelegt: Es lassen sich unterschiedliche Grade vorstellen.

[^nc8670]: Zu den technischen Aspekten von Namespaces im Semantic Web siehe insb. [@noauthor_linked_nodate] sowie [@heath_linked_2011]  und [@noauthor_associating_nodate]

[^nc8671]: Vgl. etwa: [@madoc34762, S. 3]

[^nc8672]: OWL2 differenziert, anders als etwa RDFS, nicht lediglich zwischen Klasse und Instanz, sondern zwischen Klasse und unterschiedlichen Individuen (vgl. [@noauthor_owl_nodate-1])

[^nc8673]: Vgl. [@noauthor_architecture_nodate]

[^nc8674]: [@allemang_semantic_2011, 128–130]

[^nc8675]: [@noauthor_rdf_nodate]

[^nc8676]: [@noauthor_rdf_nodate-6]

[^nc8677]: [@TN_libero_mab21631588, S. 13]

[^nc8678]: [@noauthor_resource_nodate]

[^nc8679]: [@alma9913393902586, S. 32]
\
Dies etwa im Gegensatz zur *closed world assumption* in herkömmlichen relationalen Datenbanken. Zur Notwendigkeit der Open World Assumption in semantischen Netzen s: [@alma9913393902586, S. 43]

[^nc8680]: [@TN_libero_mab21631588, S. 67]

[^nc8681]: [@szeredi_lukácsy_benkő_nagy_2014, S. 98–99]

[^nc8682]: [@noauthor_overview_nodate]

[^nc8683]: [@TN_libero_mab21631588, S. 77]

[^nc8684]: "Jede definierte Einschra ̈nkung auf einer Property wirkt al- so immer global auf jedes Vorkommen dieser Property, weswegen man bei der Angabe solcher Einschra ̈nkungen darauf achten muss, immer die allge- meinsten denkbaren Klassen anzugeben (also diejenigen, die mit Sicherheit alle mo ̈glichen Ressourcen, die in der fraglichen Beziehung stehen ko ̈nnen, enthalten)." ([@TN_libero_mab21631588, S. 77])

[^nc8685]: [@noauthor_examples_nodate]

[^nc8686]: [@noauthor_examples_nodate]

[^nc8687]: descriptive logic – AI - solcher Kram

[^nc8688]: [@alma9913393902586, S. 77]

[^nc8690]: [@hyvonen_publishing_2012, S. 76]

[^nc8691]: [@TN_libero_mab21631588, S. 68]

[^nc8692]: [@alma9913393902586, S. 170–171]

[^nc8693]: Husserl

[^nc8694]: 

[^nc8695]: 

[^nc8696]: 

[^nc8697]: noauthor_introducing_2012
[^nc8698]: 

[^nc8699]: 

[^nc8700]: [@hyvonen_publishing_2012, S. 87–88]

[^nc8701]: [@madoc34762, S. 6]
[^nc8702]: 

[^nc8703]: [@allemang_semantic_2011, S. 207]

[^nc8704]: [@allemang_semantic_2011, S. 213]

[^nc8705]: [@noauthor_overview_nodate]

[^nc8706]: [@zimanyi_web_2015, S. 79–80]

[^nc8707]: [@madoc34762, S. 7] Die Autoren berufen sich ihrerseits auf [@noauthor_how_nodate]

[^nc8708]: Vgl. auch [@noauthor_how_nodate]: "It is common practice to mix terms from different vocabularies."

[^nc8709]: [@alma9913393902586, S. 160–161]

[^nc8710]: 

[^nc8711]: "Begriffliche Kontrolle", vgl.: [@TN_libero_mab213864266, S. 128]

[^nc8712]: [@TN_libero_mab213864266, S. 128]

[^nc8713]: In dieser Arbeit wurden vor allem die Texte [@allemang_semantic_2011] sowie [@TN_libero_mab21631588] zu Rate gezogen.

[^n1]: Für eine Auswahl relevanter Vokabulare für den GLAM-Bereich s. @TN_libero_mab2 und
@ziku_digital_2020. Für eine Auswahl musikrelevanter Vokabulare s. @lisena_controlled_nodate, @bicher_normdaten_2018, @nurmikko-fuller_building_2018, @nurmikko-fuller_collaboration_2016, @futurelearn_linked_nodate.


[^n2]: @noauthor_bartocorg_nodate.
[^n3]: [@noauthor_linked_nodate-1]
[^n4]: Z. Begriff "Hypertext" siehe etwa: [@niewerth_dinge-nutzer-netze_2018, S. 92–93.]
[^n1q]: https://mimo-international.com/MIMO/doc/IFD/OAI_ULEI_M0001655

[^n2q]: Ob es sich bei ihm tatsächlich um ein in allen Aspekten passendes Objekt handelt, ist an dieser Stelle zunächst nicht relevant – es dient vor allem zur Verdeutlichung. (Tatsächlich wäre das Objekt wohl eher dem Typ "Corne du chasse" zuzuordnen. Vgl. die Ausführungen zu *Corno* und *Corne du chasse* in: @TN_libero_mab2197075, S. 57–63 und 46–51. )
[^n3q]: [@sparqlcrmsuppe_sparqlcrmsuppevocsforinstruments_2020]


[^n4q]: [@https://www.w3.org/2001/tag/doc/nsDocuments/#div.semwebNSDoc]