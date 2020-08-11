## Erfassung und Modellierung mit externen Vokabularen

### Interpret und Aufführung

In diesem Bereich spielen drei Konzepte eine Rolle:

1) *Interpret*
2) *Aufführung*
3) Das Verhältnis dieser beiden Entitäten zueinander, welches durch eine Property ausgedrückt wird.

Während *Interpret* und *Aufführung* jeweils im Bereich der "Domäne" und somit in deren Ermessen liegen, muss die Relation zwischen den beiden Entitäten verbindlich definiert sein und somit einen Bestandteil des Metadatenprofils bilden.

#### Interpret und Aufführung – Relation

* CIDOC CRM verfügt über das Property `P14`: "This property describes the active participation of an instance of E39 Actor in an instance of E7 Activity."[^d1] Diese Definition erscheint für den vorliegenden Anwendungsfall allzu allgemein gefasst und daher unpassend.

* Ähnlich verhält es sich mit den Properties des *Europeana Data Models*, die in Verbindung mit der Klasse `edm:agent` Verwendung finden.[^d2]

* *Wikidata* verfügt über das Property `wd:P175` ("performer")[^d3]. Während Wikidata aufgrund der potnenitellen Instabilität seiner Terme zwar in der Regel keine Verwendung im Rahmen dieser Arbeit, verweist Wikidata in seiner Eigenschaft als Data Hub unter anderem auf den folgenden Datensatz:

* Auf *schema.org* findet sich das Property `schema:byArtist`.[^d4] mit möglichen Objekten `schema:musicGroup` und `schema:person`. Als Subjekte kommen `schema:musicAlbum`oder `schema:musicRecording` infrage. Während die Objekte geeignet erscheinen, anwendungsrelevante Sachverhalte wiederzugeben, sind die Subjekte offenbar auf Audioaufnahmen beschränkt: Somit könnten Aufführungen, die nicht in Form einer Aufnahme vorliegen, durch diese Entitäten nicht repräsentiert werden.

* In der *DOREMUS Ontology*[^d7] finden sich die Properties `mus:U54`[^d5] ("is performed expression of") und `mus:U81`[^d6] ("had performer status"). Jedoch scheint ersteres durch die implizit starke Konzentration auf FRBR für eine generische Anwendung zu eingeschränkt und nicht sachgemäß. Letzteres ist offenbar auf eine Verwendung bei der Erfassung von Konzertprogrammen semantisch ausgerichtet und  somit für das vorliegende Anwendungsszenario ebenfalls unsachgemäß.

* Die *GND Ontology* verfügt über das Property `gnd:instrumentalist`[^d8] mit der Domain `gnd:work` und Range `gnd:differentiatedPerson`. Während diese Verwendungsspezifikationen dem Zweck einer Verbindung von Instrumenten und Werken in prinzipieller Weise gerecht werden könnte, würde die Anwendung des Propertys die Darstellung einiger vorstellbarer angrenzender Sachverhalte erschweren. So bezöge das Property etwa vokale Äußerungen jeder Form nicht mit ein. Diese Einschränkung wirft gerade im Bereich der Musik des letzten Jahrhunderts etliche Probleme auf – wie wäre etwa mit gesampleten Stimmen mit anschließender Verzerrung, oder  instrumentell-imitatorischen Äußerungen des Vokaltrakts, etwa dem sog. *Vocal Percussion* zu verfahren?[^29]

* Im Rahmen des *Body&Soul*-Projekts[^d9] findet das Property `mo:performer` der *Music Ontology* Verwendung. Seine Domain ist mit `mo:performance`[^d10] und dem Range `foaf:agent`[^d11] sehr allgemein gehalten, sodass hohe Anschlussfähigkeit zu erwarten ist. 

Allerdings entspricht die Klasse `foaf:agent` nicht der vorgesehenen Klasse `ma:Person`, welche besser durch die Klasse `foaf:person`[^d12] dargestellt würde. Diese Inkonsistenz ist jedoch keineswegs als Defizit aufzufassen, eröffnet doch die Klasse `foaf:agent` recht eigentlich das Modell für weitere Szenarien: So lässt sich das Darstellungsspektrum um Instanzen in Form von Personen, wie auch "Körperschaften", die dieser Klasse subsumiert werden, erweitern: In Folge werden Aussagen der Form
\
"\<Das Werk Soundso> \<wird gespielt von> \<Blockflötenensemble "Schlingenfittich">"

ermöglicht. Diese Darstellungstiefe ist dabei nicht nur im "Werk-Ereignisbereich", sondern auch im Bereich der Musikinstrumente wichtig. Auch Aussagen der folgenden Form sind entsprechend möglich:
\
"\<Klavierduo Soundso> \<spielt auf> \<dem Klavier "Objekt Schlagmichtot">"

Soll `foaf:agent` Verwendung finden, muss das Datenmodell dergestalt ummodelliert werden, dass `foaf:person` zur Unterklasse von `foaf:agent` wird. Dies geschieht mit dem bereits bekannten Property `rdfs:subclassOf`. Zugleich tritt anstelle des Propertys `ma:Interpret` das Property `mo:performer`. Dessen Range wiederum muss auf `foaf:agent` bezogen werden. Da das Property `rdfs:subclassOf` transitiv ist[^d13], wird die Range-Beschränkung auch auf mögliche Unterklassen von `foaf:agent` "vererbt" und gilt somit auch für `foaf:person`.


#### Personennormdaten

Die Instanz `ma:Person_a` stellt eine Variable dar, die je nach Bedarf mit entsprechenden Normdaten aus beliebigen externen Domänenvokabularen befüllt werden kann (GND, LCNAF[^d14], VIAF[^d15], Wikidata etc.). So hat der Verfasser beispielsweise zur Illustration für die Arbeit Personendatensätze auf Wikidata der angeblich an der Uraufführung der Kantate BWV 208 beteiligten Hornisten des Weißenfelser Hofs,[^46] Johann Zedelmayer (`wdt:Q97621186`)[^44] und Anton Fischer (`wdt:Q97621343`)[^45] angelegt.

Da die Entitäten `ma:hat_Name` und `ma:hat_Lebensdaten`, ursprünglich ja als Attribute im ERM eingeführt, in der Regel Bestandteil von Personennormdatensätzen sind, können erstere als obsolet betrachtet werden und aus dem Vokabular `ma:` entfernt werden.


#### Modellierung von Zusammenhängen zwischen Musikinstrumenten, Interpreten und Aufführungen

Während Aussagen gemäß dem Schema
\
"\<das Klavier "Objekt Schlagmichtot"> \<wird bespielt von> \<Klavierduo Soundso>"

nun in Bezug auf das Objekt dank `foaf:agent` ermöglicht worden sind, ist aufgrund der Beschränkungen von `mo:performer` eine Verbindung mit einem Subjekt, welches kein "Agent" ist (etwa ein Musikinstrument), nicht möglich.

Während die Modellierung im ERM kraft der einfachen Eigenschaft "Interpret" erfolgte, wird spätestens zu diesem Zeitpunkt deutlich, dass dieses an äußere Vorgaben ungebundene, monodimensionale Modell der vorgefundenen Realität des Semantic Web nicht mehr gerecht werden kann. Es gilt daher, Um- und Neumodellierungen vorzunehmen.\

1)\ Zentralen Verbindungsknoten bei der Modellierung von Instrument und Interpret bildet das Ereignis in Form einer Aufführung – durch die nun einzuführende Klasse `mo:performance`[^d16] vertreten –, unter den domänenspezifische Ereignisse (also Instanzen von `ma:Aufführung_Domäne)` fallen. Durch die Einführung dieser Oberklasse wird die Klasse `ma:Aufführung_Domäne` typisiert und in das Semantic Web eingebettet.  Eine Verbindung zwischen Instrumenten und Aufführungen kann dabei mit der Property `mo:instrument` erfolgen: "[The property r]elates a performance to a musical instrument involved [.]"[^d17]\
Diese Verbindung ist zum einen zum Objektbereich zu knüpfen:\

`mo:performance	mo:instrument	ma:Objekt_Domäne .`
\
Zum anderen muss eine Verknüpfung "werkseitig" erfolgen. Hier bietet es sich an, angesichts der ohnehin angedachten Normierung durch Mapping zu einer Klassifikation, direkt eine Verbindung zwischen entsprechender Klasse und Aufführung zu schaffen:\

`mo:performance	mo:instrument	ma:Instrument_(Klassifikation) .`
\
2)\ Während es nun möglich ist, sowohl die Beteiligung eines Musikinstruments, wie auch der einer Person an einer Aufführung darzustellen, befinden sich beide Entitäten noch in kontingentem Verhältnis zueinander. Noch besteht kein Konnex zwischen Instrument und Person: die Aussage, jemand spiele ein Instrument, ist noch nicht ermöglicht.

Erstaunlicherweise findet sich in den großen etablierten Vokabularen keine Terminologie, um diesen scheinbar banalen Sachverhalt abzubilden. Fündig wird man jedoch in der *Linked Irish Traditional Music Ontology*.[^d18] Das Property L58[^d20] ("played on instrument") und das inverse Property L58i[^d19] ("instrument played by") geben den hier gewünschten Sachverhalt in geeigneter Weise wieder.


![](medien_Kap4/20200526_interpret3.png)

### Mapping und Klassifikation
#### "Medium of Performance"

@Musicalinstrument Vehicle for exploring and expressing musical ideas and feelings through sound. Practically anything that is used to make sound can be employed in music, so the concept of a musical instrument embraces a very broad range of things, including, for purposes of this dictionary, the human body.

Ein zentrales Anliegen dieser Arbeit ist eine Maximierung der Anschlussfähigkeit des entwickelten Metadatenprofils. An diese Maximierung geknüpft, befindet sich die Offenheit seiner Konzepte, deren Fokussierung erst möglicher Endpunkt eines diskursiven Community-Verfahrens darstellen könnte. Somit muss an dieser Stelle die Schärfung des Konzepts "Musikinstrument" zum einen nicht vorweggenommen werden, zum anderen gilt es sogar, dieses Konzept möglichst weit zu fassen und somit integrativ zu gestalten. Bei diesen Überlegungen bietet die Vorstellung vom "Medium of Performance" – , in RDA 6.15.1.1 als "[a]n instrument, voice, and/or ensemble for which a musical work was originally conceived[...]",[^18] definiert – einen recht guten Anfangspunkt. 

Während dieses Konzept erfreulicherweise Musikinstrumente im herkömmlichen Sinne um weitere Medien musikalischer Äußerung ergänzt, erscheint jedoch die dieser Definition inhärente deterministische Qualität sowie die eindimensionale Ausrichtung auf die Entität "Werk" hier einigermaßen fehl am Platz. Diese Arbeit nimmt vielmehr eine phänomenologische Perspektive ein, indem sie davon ausgeht, dass jede Entität, die in der Lage ist, Klang zu erzeugen, das situative Potential besitzt, die Funktion "Musikinstrument" einzunehmen (abermals ließe sich hier Heidegger bemühen). So kann beispielsweise auch eine zufällig vor-(/bzw. "zu-")handene Flasche[^19] oder jeder andere beliebige Gegenstand situationsbezogen zum Musikinstrument werden. Selbst beispielsweise Boethius' im Mittelalter außerordentlich einflussreiche und fest im sog. *Quadrivium* verankerte Idee "kosmischer Musik", die *musica mundana*,[^20] findet als Zusammenspiel verschiedener "Medien", der Himmelskörper, Raum in diesem Verständnis.\
Anhand letzteren Beispiels wird dabei auch deutlich, dass in dieser Arbeit auch das Konzept "performance" in einem sehr allgemeinen Verständnis Verwendung findet. Prämisse einer solchen "Performance" bildet also nicht etwa eine wie auch immer geartete artifizielle "Performativität"[^21].\
Zugleich besteht – im Gegensatz etwa zu RDA – kein notwendiger und schon gar kein hierarchischer Zusammenhang zwischen Medium und Werk. Auch ein Museumsobjekt gilt – kraft seines Potentials, Medium einer musikalischen Äußerung (gewesen) zu sein – nach diesem Verständnis als "Medium of Performance".\
Gleichzeitig wird, eingedenk dieser phänomenologischen Annäherungsweise vorgehend, der Begriff "Musik" ebenfalls zum außerordentlich integrativen Konzept, nach dem – man denke an Boethius – genau dasjenige als Musik aufzufassen ist, das als solches wahrgenommen wird – und dies selbst ganz und gar unabhängig von einer (nicht-)vorhandenen "Klanglichkeit". So liegt denn also "Musik" gewissermaßen im Auge des Betrachters, und das Medium dieser Wahrnehmung ist ein – im eigentlichen Wortsinne – "instrumentales" Werkzeug – ein (Musik-)Instrument.
\
Bislang wurde in dieser Arbeit das Konzept `ma:Instrument_Klassifikation` als Platzhalter verwendet. Im Sinne einer Anbindung ans Semantic Web sollte jedoch nach einem etablierten Term gesucht werden. Zwar findet sich in der *Performed Music Ontology* – einer Ontologie,[^23] die für den Gebrauch im Rahmen von *BIBFRAME* entwickelt worden ist –[^22] die Klasse `pmo:mediumOfPerformance`.[^24] Jedoch ist davon auszugehen, dass sie durch ihre RDA-Ausrichtung keinen Raum für Nutzungsszenarien, wie die eben skizzierten, bietet.

Vielversprechender erscheint das Konzept `mus:M14`[^25] ("medium of performance") der DOREMUS-Ontologie. Dies jedoch leider vor allem deshalb, da sie – zumindest auf den ersten Blick – keinerlei inhärente Einschränkungen bei ihrer Verwendung vorgibt. Entsprechend wird im Folgenden das Konzept `ma:Instrument_Klassifikation` mit dem Konzept `mus:M14` ersetzt.

Jedoch erschiene es sinnvoll, im Nachgang dieser Arbeit – etwa im Rahmen jenes Community-basierten Diskurses – die Neuanlage eines Konzepts zu prüfen, um ein höheres Maß an Offenheit, Anschlussfähigkeit und Unabhängigkeit gegenüber bibliographisch-"gedachten" Modellen wie insbesondere RDA / IFLA-LRM erzielen zu können.

[klarer machen: auf der einen Seite wird der ganze Klassifikationskram bedient, auf der anderen die Objekt – Ressourcen-Beziehungen] **<- Einleitend in den jew. Abschnitten.**

#### Herausforderungen
\ 
Dieser Option lag das Anliegen zugrunde, "werkseitig" fallspezifisch unsaubere oder unspezifische Vokabulare durch In-Beziehung-Setzen zu Musikinstrumenten – entweder über eine Klassifikation, oder direkt gegenüber einem Objekt – zu disambiguieren. Diese Fallspezifität birgt jedoch auch Herausforderungen: Kehrte man die Perspektive zu einer "objektseitigen" um, so mündete ein Suchvorgang unter Umständen in eine mit ambiguösem Vokabular indexierte Treffermenge und somit in übermäßig viele *False Positives*.
Dieses Problem ist nicht einfach lösbar, und es scheint, dass eine wirklich symmetrische Lösung auf terminologischer Basis nur Ergebnis eines gründlichen Standardisierungsprozesses zu schaffen sein wird. Allerdings exisiteren bereits Ansätze, die aus "umgekehrter Richtung" hin zu einer Verbindung zwischen Objekt und Werk vorstoßen: Im Artikel "A Timeline Metaphor for Analyzing the Relationships between Musical Instruments and Musical Pieces",[^d21] einer Publikation aus dem *MusiXplora*-Umfeld,[^d25] wird beschrieben, wie anhand eines statistischen Abgleichverfahrens zwischen Objekt- und Werkmetadaten (Similarity Measure) eine gute Trefferquote bei der maschinellen Herstellung von Objekt-/Werkbeziehungen zwischen MIMO- und RISM-Einträgen erzielt wird.

Der Umstand, dass bereits auf Verfahren verwiesen werden kann, die die "objektseitige" Verlinkung abdecken, lässt das eingangs beschriebene Defizit als zunächst verschmerzbar erscheinen. Angesichts dessen jedoch, dass die die Ergebnisse der Verlinkung laut Artikel noch einen intellektuellen Redaktionsprozess erfordern[^d22] bzw. soweit bekannt nicht mit Semantic Web-Technologien erschlossen sind, erschiene vielmehr ein synergetischer hybrider Ansatz, der die erzielbare hohe intellektuelle Qualität mittels der hier vorgeschlagenen Methodik mit der im Artikel beschriebenen maschinellen Effizienz koppelt, als verfolgenswerter Ansatz.

#### Mapping
\
Zum Mappen hat sich insbesondere das ebenfalls durch die W3C standardisierte Vokabular SKOS ("Simple Knowledge Organization System")[^d24] etabliert.[^d23] Es wird zu klären sein, in wie weit es auch für die Belange des Metadatenprofils nutzbar sein wird.\
Das in dieser Arbeit entwickelte Modell sieht zwei Anwendungsszenarien vor:

##### Szenario 1: Mapping über Klassifikation

Verbindungen zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` werden über eine Unterklasse von `mus:M14` ("Medium of Performance") hergestellt (s. #Abbildung. Dabei ist der jeweilige Vertreter der Klasse `ma:Objekt_(Domäne)` eine Instanz der Klasse `mus:M14`. Dieser Sachverhalt kann mit `rdf:type`, wie auch bereits in #Kapitel geschehen, wiedergegeben werden (das Property `ma:Typ` kann entsprechend entfernt werden):

`ma:Objekt_(Domäne)	rdf:type	mus:M14	.`

Die Entität `ma:Instrument_nach_Vokabular_(Domäne)` findet ihre fallspezifische exakte Entsprechung in der Instanz der Entität `mus:M14` (vgl. #Abbildung), sodass mit `skos:exactMatch` eine Äquivalenzrelation dargestellt werden kann:

`ma:Instrument_nach_Vokabular_(Domäne)	skos:exactMatch	mus:M14	.`

Eine Verwendung weiterer, vagerer SKOS-Relationen erscheint – da von einem "werkseitigen" Mappen ausgegangen wird – an dieser Stelle nicht angebracht, soll doch das uneindeutige Domänenvokabular durch Mappen dismabiguiert, also exakt gemapped, werden.

![](medien_Kap4/20200602_Klass2.png)

###### Klassifikation

Die Entscheidung für eine Klassifikation muss – aus bereits dargelegten Gründen – domänenübergreifend geschehen. Zudem kann an dieser Stelle – wie ebenfalls bereits erwähnt – keine systematische, kritische Untersuchung vorhandener Klassifikationen erfolgen, die eine Entscheidungsgrundlage anbieten könnte. Darin, eine solche Untersuchung vorzunehmen, liegt jedoch großes Potential für zukünftige Arbeiten begründet.
Vorläufig lässt sich jedoch festellen, dass insbesondere der sog. *MIMO Thesaurus*[^15] eine tragfähige klassifikatorische Infrastruktur zu bieten scheint. Weitere Möglichkeiten, insbesondere für die Verwendung von Vokalstimmen,[^17] finden sich im *IAML Medium of Performance Vocabulary*.[^16] Vor allem erscheint denkbar, ähnlich zum hier gewählten Vorgehen, ein Metadatenprofil zu entwickeln, das die Darstellungstiefen verschiedener Klassifikationen und Vokabulare kombiniert und zueinander in Beziehung setzt.

##### Szenario 2: direktes Mapping

Bei der Herstellung einer direkten Relation zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` sind verschiedene Bezugsszenarien je nach Ähnlichkeit von Term und Objekt vorstellbar. Es erscheint daher sinnvoll, eine Relation als sog. "Superproperty" zu definieren, unter die alle weiteren Relationen ("Subpropertys") subsumiert werden.[^30] Als Superproperty ist dabei die Property `dc:relation`[^11] der *Dublin Core Metadata Initiative* als besonders standardisiert zu betrachten. Unter ihn können mit der Property `rdfs:subpropertyOf`[^12] Subproperties für die folgenden Szenarien eingeordnet werden:\

1)\ Zur Exemplifizierung eines Terms wird auf ein beispielhaftes Objekt verwiesen. Dies ist auch im hier behandelten Anwendungsbeispiel der Fall: dem Term `rism:cor_da_caccia` kann aufgrund bestehender Gemeinsamkeiten hinsichtlich Region (Herstellungs-/Kompositionsort: Mitteldeutschland) und Zeit (erste Hälfte 18. Jahrhundert) ein Objekt zugewiesen werden, das als beispielhaft für den Typ des etwa bei der Uraufführung verwendeten Instruments gelten könnte.
SKOS, die erste Anlaufstelle, wenn es um Mapping geht, bietet dabei das Property `skos:example`[^1], dessen Zweck jedoch nicht im Verlinken mit beispielhaften Instanzen zu bestehen, sondern darin zu liegen scheint, beispielhafte Verwendung von Termen zu illustrieren.[^2] 

Da das Verlinken von Objekten weniger im bibliographischen Bereich, als im Museumswesen eine Rolle spielt, erscheint es angebracht, in letzterem nach anwendbarer Terminologie zu suchen: Hier erscheint insbesondere das bereits erwähnte CIDOC CRM eine gute Anlaufstelle zu bieten. Dort findet sich das Property `crm:P137`[^3] mit dem Label "exemplifies (is exemplified by)". Die Domain des Propertys ist dabei auf `crm:E1`[^4] (Entity) bezogen – die Range auf `crm:E55` (Type).[^5] Beim Konzept `crm:E55` handelt es sich um "CIDOC CRM’s interface to domain specific ontologies and thesauri",[^6] indem die domänenspezifischen Terme etwa mit der Property  `crm:P127`[^7] "has broader term (has narrower term)" zu Unterklassen von `crm:E55` deklariert werden (s. #Abbildung).[^8] Mehreres erscheint daher sinnvoll:
- Das Property `crm:P137` darf für die Relation "Beispiel" zwischen`ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` eingeführt werden. Bemerkenswert ist zudem, dass diese Property als eine sog. *symmetric property* definiert werden kann, bei der also Domain und Range variabel sind.[^27] Sie wird dabei durch die Eigenschaft `owl:symmetricProperty`[^28] als solche klassifiziert.
- Anstelle der Entität `ma:Instrument_nach_Vokabular_(Domäne)` kann die Entität `crm:E55` (Type) als Schnittstelle zwischen domänenspezifischem Vokabular und dem Metadatenprofil verwendet werden.
- Das Konzept `crm:E19`[^9] ("physical object") kann, als Unterklasse von `crm:E1`, dabei anstelle von `ma:Objekt_(Domäne)` verwendet werden, um den gleichen Effekt zu erzielen.
- Indem `crm:E55` mit `rdf:type` als Musikinstrument gekennzeichnet wird, kann festgelegt werden, dass es sich bei allen Unterklassen und Instanzen von `crm:E55` um Musikinstrumente handelt (s. #Abbildung). Dies kann anstelle der Klasse `ma:Instrument_(Domäne)` geschehen und macht diese somit obsolet. Obwohl die "großen" Domänenvokabulare (GND, LCSH etc.) vielfältige Terme bereithalten, fallen auch hier spartenunspezifische Terme aus Vokabularen in die engere Auswahl, die ein hohes Maß an Verbreitung versprechen: Der Datensatz `wd:Q34379` "musical instrument" in Wikidata[^10] weist eine Vielzahl von Mappings zu anderen Vokabularen auf und ist somit außerordentlich aussagekräftig. Obwohl Wikidata-Datensätze grundsätzlich manipulierbar sind und daher semantische Persistenz nicht garantieren können, handelt es sich bei "musical instrument" wohl um ein sehr zentrales Konzept, das nicht ohne weiteres zu verändern sein wird. Und tatsächlich ist die "maschineninterpretierbare", kontextuell-hergestellte Semantik nicht weniger persistent als bei anderen, angeblich persistenteren Vokabularen. Eine Übernahme in das Metadatenprofil erscheint daher möglich und sinnvoll. 

2)\ Einen gängigen Anwendungsfall stellt das Szenario dar, dass eine Äquivalenzrelation zwischen Domänenvokabular und Objekt dargestellt werden soll. Beispielhafte Sachverhalte wären – etwa im Falle einer Audioaufnahme: "Anne Sophie Mutter spielt auf ihrer Stradivari *Lord Dunn-Raven*"[^26], oder "J. S. Bach nimmt die *Hildebrandt Orgel* von *St. Wenzel* in Naumburg ab".[^14] Es müsste also eine Verknüpfung zwischen einem domänenspezifischen Vokabular – etwa der GND – und einem Objekt hergestellt werden, die besagt, dass beide Datensätze ein identisches Instrument bezeichnen. Dies kann etwa mithilfe der Property `owl:sameAs`,[^13] im Übrigens ebenfalls eine *symmetric property* (s.o.), geschehen. Analog zu den bereits beschriebenen Herausforderungen beim Mappen über eine Klassifikation ergibt sich jedoch auch hier beim Mappen zwischen einer Entität des Typs *Instanz* (Objekt) und einer des Typs *Klasse* (Vokabular) ein Problem: Während das ambiguöse Domänenvokabular durch den Verweis auf ein spezifisches Objekt disambiguiert wird, folgt "objektseitig" die logische Aussage, mit der "werkseitigen" Verwendung eines (eigentlich generischen) Terms sei immer genau jenes Objekt gemeint.

Einen möglichen Ausweg böte unter Umständen die Verwendung von `rdf:type`, um dieses hierarchische Problem zu umgehen. In diesem Fall müsste jedoch die Superproperty `dc:relation` entfernt werden, würde doch andernfalls jede `rdf:type`-Beziehung – also auch etwa die, die festlegt, dass `dc:relation` eine Property ist – zu einer Subproperty von `dc:relation`; logisch falsch.

Daher soll `owl:sameAs` "als Krücke", im Bewusstsein seiner Unzulänglichkeit vorläufig beibehalten werden, wäre aber im Rahmen einer Community-Nachbereitung zu thematisieren.

![blablablub – fett markiert: übergeordnete Klassen und deren Beziehungen zueinander](medien_Kap4/20200603_mappKlass.png)

##### Erkenntnisse aus der Modellierung

Das – ursprünglich immerhin recht zentrale – Anliegen dieser Arbeit, eine "werk- und objektseitig symmetrische" Verbindung zwischen Vokabularen und Objekten zu schaffen, konnte im Vorhergehenden nur in sehr dürftiger Weise erfüllt werden. Insbesondere die spartenübergreifende Tragweite der Implikationen dieser Verbindung bringen es mit sich, dass diese Arbeit nun zum ersten Mal an einen Punkt gerät, an dem deutlich wird, dass die Lösung eines Problems erst im Rahmen eines anschließenden gemeinschaftlichen Prozesses möglich wäre. Initiale gedankliche Vorarbeiten leisteten dabei die in diesem Kapitel ausgebreiteten Ausführungen.


### Klangbeispiel

Widererwarten stellt sich bei der Sichtung anwendbarer Vokabulare heraus, dass gerade die Verknüpfung eines Klangbeispiels mit einem Instrument offebar ein Szenario ist, das momentan im Semantic Web nicht abgedeckt ist. Um eine solche Verknüpfung doch umzusetzen, liegt die größte Herausforderung darin, dass Properties, die sich auf Aufnahmen Art beziehen, in der Regel mit `rdfs:range` oder `rdfs:domain` an Ereignis-Entitäten gebunden sind.[^31] Zwar lässt sich der Ereignis-Kontext laut Weigl für die Beziehung zwischen Werk und Aufnahme mit einer relativ komplex modellierten, auf der Music Ontology basierenden "Volte"[^32] oder evtl. etwas einfacher, mit *schema.org*, vermeiden[^33]. Allerdings sind auch diese Lösungen auf den Werk-Kontext beschränkt und somit für die Verknüpfung von *Musikinstrument* mit *Klangbeispiel*  ungeeignet. 

Wikidata hält zwar mit den Properties `wdt:P4733` ("produced sound")[^35] und `wdt:P51` ("audio")[^36] Properties bereit, mit denen man Klangbeispiele verlinken kann. Allerdings beziehen sich diese auf Medien aus den *Wiki Commons*. Dennoch scheint im Verlinken in den Wikimedia-Kosmos, eine Chance zu liegen, die prinzipiell nicht ausgeschlossen werden sollte, stellt doch der dieser Kosmos eine riesige, stetig wachsende, intern wie extern verknüpfte Wissensdatenbank dar. Daher erscheint es sinnnvoll, `wdt:P51` als Verbindungsglied in diese Welt in das Applikationsprofil zu übernehmen (vgl. #Abbildung).

Für andere Szenarien scheint, das Property `ma:hat_Klangbeispiel` nicht mit externem Vokabular ersetzbar zu sein. Es ergibt sich somit erstmalig im Zug dieser Arbeit, dass ein neuer Term – `ma:hat_Klangbeispiel` – im Rahmen des Applikationsprofils in das Semantic Web eingeführt werden muss. Bei diesem Schritt sind einige Dinge zu beachten:

* Momentan bezieht sich `ma:hat_Klangbeispiel` vermittels `rdfs:domain` auf `wd:Q34379` (Musikinstrument) – und ist somit explizit auf Musikinstrumente im eigentlichen Sinne beschränkt. Eine Verlinkung mit Musikinstrumenten im offenen Verständnis dieser Arbeit (s. #Kapitel"MediumofPerformance") ist daher nicht möglich. Diese Inkompatibilität lässt sich jedoch recht einfach lösen, indem `rdfs:domain` auf `mus:M14` ("Medium of Performance") bezogen wird. Noch wird jedoch  `mus:M14` nur im Kontext des Mappings verwendet: Eine direkte Verknüpfung mit Objekten oder Vokabularen, wie sie im Anwendungsszenario dieser Arbeit vorgesehen war, ist nicht möglich. Dies lässt sich jedoch lösen, indem `wd:Q34379` mit `rdfs:subclassOf` zur Unterklasse von `mus:M14` erklärt wird (s. #Abbildung). So wäre es denn also möglich, auch Klangbeispiele mit Instrumenten – verstanden im aller weitesten Sinne – zu verknüpfen.\

* Es gehört zur guten Praxis im Semantic Web, Konzepte mit `rdfs:label`[^37] mit einer menschenlesbaren Bezeichnung in Form eines "Strings" zu annotieren.[^34] Um ein größtmögliches Maß an Verständlichkeit im Netz zu gewährleisten, geschieht dies idealerweise auf Englisch. Diese Bezeichnung lautet hier: "audio example medium of performance". Es macht darüber hinaus Sinn, diese Bezeichnung ebenfalls in der URI zu verwenden, um auch diese menschenlesbar zu gestalten. So wird denn aus `ma:hat_Klangbeispiel` das Property `ma:audio_example_medium_of_performance`.\

* Zudem gehört es zur guten Praxis, mit `rdfs:comment`[^40] einen menschenlesbaren Kommentar zur Verwendung eines Properties ebenfalls als String zu hinterlegen.[^39] In diesem Fall heißt er: "[The property r]elates audio files to: musical instrument terms in vocabularies, physical objects used for musical performance."

Nachdem ein passendes Property kreiert worden ist, darf noch das dazugehörige Objekt, bislang `ma:Klangbeispiel`, durch einem etablierten Term ersetzt werden. Hier bietet sich etwa die Klasse `schema:track`[^41] an. 

Bei *schema.org* handelt es sich dabei um ein überaus mächtiges Vokabular, das von den einschlägigen Suchmaschinengiganten unterhalten und verwendet wird. Schon allein auch aus Gründen der Suchmaschinenvisibilität sowie der "mitgelieferten" einfachen Implementierbarkeit von RDF in HTML handelt es sich um eine "Anwendung", die zuletzt auch als potentiell außerordentlich performant für den Kulturerbebereich wahrgenommen worden ist.[^42] Eine weitere Prüfung, in wie weit das hier entwickelte Anwendungsprofil von einer Erschließung mit den Mitteln von *schema.org*[^43] profitieren könnte bzw. ob überhaupt eine Kompatibilität besteht, würde aus genannten Gründen sicherlich im Zuge einer Fortentwicklung des Anwendungsprofils Sinn machen.\

Denkbar wäre es, wie im ERM skizziert, weitere Szenarien darzustellen (etwa Lizenz, Format, Album, Dauer etc.), in das Applikationsprofil zu integrieren. Dies im Rahmen dieser Arbeit durchzuführen ist jedoch nicht möglich. Stattdessen kann zum einen auf Vokabulare verwiesen werden (etwa *schema.org* oder die  *Music Ontology*), andererseits würde eine Ausarbeitung vom eigentlichen Ziel dieser Arbeit – nämlich das spartenübergreifende Verbinden von musikinstrumentalen Daten – allzu sehr weglenken. Daher bleibt auch dies ein mögliches Desiderat im Rahmen einer Weiterentwicklung des Metadatenprofils. Entsprechende, bereits vorhandene Terme können somit aus dem Applikationsprofil entfernt werden.

![blablablub – fett umrandet: Klassen, dünn umrundet: Instanzen](medien_Kap4/20200609_klgBsp.png)




inst peng klatsch  

wumms – SeManticMUsicinstrumentWeb <- sicher schon vergeben?



mu ins se ma web


sch na ps

onto





Wichtig: Arbeit ist Train of thought – absolut deduktiv (manches hätte man vielleicht von Anfang an besser lösen können)

—




—

[^d1]: [@xrysoula_definition_nodate, S. 52]

[^d2]: [@noauthor_resource_nodate, S. 33–36]

[^d3]: [@noauthor_performer_nodate]

[^d4]: [@noauthor_byartist_nodate]

[^d5]: [@noauthor_doremus_nodate-3]

[^d6]: [@noauthor_doremus_nodate-4]

[^d7]: [@noauthor_doremus-anrdoremus-ontology_nodate]

[^d8]: [@noauthor_gnd_nodate]

[^d9]: [@nurmikko-fuller_building_2018]

[^d10]: [@noauthor_music_nodate-3]

[^d11]: [@noauthor_foaf_nodate]

[^d12]: [@noauthor_foaf_nodate-1]

[^d13]: [@noauthor_rdfcore_nodate]

[^d14]: [@noauthor_library_nodate]

[^d15]: [@noauthor_viaf_nodate]

[^d16]: [@noauthor_music_nodate-4]

[^d17]: [@noauthor_music_nodate-5]

[^d18]: [@archive_irish_2020]

[^d19]: [@archive_irish_2020-1]

[^d20]: [@archive_irish_2020-2]

[^d21]: [@kusnick_timeline_2020]

[^d22]: [@kusnick_timeline_2020, S. 250]

[^d23]: [@noauthor_skos_nodate]

[^d24]: [@noauthor_skos_nodate-1]

[^d25]: [@noauthor_musixplora_nodate]

[^1]: [@noauthor_skos-core_nodate]

[^2]: [@noauthor_skos-core_nodate]

[^3]: [@noauthor_definition_nodate-1]

[^4]: [@noauthor_definition_nodate-2]

[^5]: [@noauthor_definition_nodate-3]

[^6]: [@xrysoula_definition_nodate, S. xxvi]

[^7]: [@noauthor_definition_nodate-4] Wobei in dieser Arbeit die Verwendung von `rdfs:subclassOf` zu genügen scheint.

[^8]: [@xrysoula_definition_nodate, S. xxvi]

[^9]: [@noauthor_definition_nodate-5]

[^10]: [@noauthor_musical_nodate]

[^11]: [@noauthor_dcmi_nodate]

[^12]: [@noauthor_rdf_nodate-5]

[^13]: [@noauthor_owl_nodate-4]

[^14]: Eine zentrale Herausforderung liegt jedoch in dem Umstand, dass – abgesehen etwa von MIMO – kaum referenzierbare Datensätze für Instrumente im Netz vorhanden sind. So lässt sich zwar etwa mittels SPARQL-Abfrage eine Liste der auf Wikidata vorhandenen "Stradivaris" (https://query.wikidata.org/sparql?query=%23%22Stradivaris%22%20in%20Wikidata%0ASELECT%20%3Finstrument%20%3FinstrumentLabel%20%0AWHERE%20%0A%7B%0A%20%20%3Finstrument%20wdt%3AP170%20wd%3AQ182011%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A%0A), oder von Orgeln (auf 500 beschränkt) (https://query.wikidata.org/sparql?query=%23Orgel%20in%20Wikidata%0ASELECT%20%3Finstrument%20%3FinstrumentLabel%20%0AWHERE%20%0A%7B%0A%20%20%3Finstrument%20%23wdt%3AP170%20%3Fcreator%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP31%20wd%3AQ1444%20.%0A%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22%5BAUTO_LANGUAGE%5D%2Cen%22.%20%7D%0A%7D%0A%0ALimit%20500) generieren, jedoch böte sich das systematische Verzeichnen – insbesondere von Orgeln – als möglicher Ansatzpunkt für künftige Erschließungsprojekte an.

[^15]: noauthor_vizskos_nodate-1

[^16]: [@noauthor_about_nodate-1]

[^17]: Diese würden naturgemäß in der Regel nicht mit einem Objekt verknüpft. Ausnahmen fänden sich, wie so oft, in der zeitgenössischen Musik: Ob anhand eines Synthesisers eine Stimme verzerrt wird (tatsächlich böte bereits die Verstärkung einer Stimme durch ein Mikrophon als "Instrument" im weitesten Sinne), oder in ein Instrument "hineingesungen" wird, wären auch diese Szenarien darstellbar.

[^18]: [@noauthor_rda-toolkit_nodate]

[^19]: Übrigens ein ganz typisches Instrument im sog. *Calypso*.

[^20]: [@TN_libero_mab214185363, S. 70–71.]

[^21]: Zur Begriffsbestimmung s.: [@TN_libero_mab21693058], S. 562–564.

[^22]: [@noauthor_performed_nodate]

[^23]: [@noauthor_ld4pperformedmusicontology_nodate]

[^24]: [@noauthor_notitle_nodate]. Deren URI (http://performedmusicontology.org/ontology/MediumOfPerformance) jedoch zu einer "404-Meldung" auflöst (Stand 02.06.2020).

[^25]: [@noauthor_doremus_nodate-5]

[^26]: [@noauthor_lord_nodate]

[^27]: [@TN_libero_mab21631588, S. 149.]

[^28]: [@noauthor_owl_nodate-5]

[^29]: Weitere Ausführungen zum Verständnis des Konzepts "Musikinstrument" in dieser Arbeit folgen in #Kapitel.

[^30]: So werden – dank der Transitivität des Superpropertys – bei einer SPARQL-Suche zugleich auch Entitäten, die durch dessen Subproperties miteinander verbunden sind, ausgegeben.
[^31]: Siehe etwa den Twitter-Thread unter dem Hashtag *#openmasterarbeit* vom 09.–10.06.2020 zum diesem Thema – dort insb. in Hinsicht auf Werk-Entitäten: [@noauthor_alan_nodate]
[^32]: [@noauthor_david_nodate]

[^33]: [@noauthor_david_nodate-1]

[^34]: [@noauthor_label_nodate]

[^35]: [@noauthor_produced_nodate]

[^36]: [@noauthor_audio_nodate]

[^37]: [@noauthor_rdf_nodate-7]


[^39]: [@noauthor_notitle_nodate-1, S. 16–17.]

[^40]: [@noauthor_rdf_nodate-8]

[^41]: [@noauthor_track_nodate]

[^42]: S. hierzu etwa: [@gangemi_evaluation_2018] oder [@neovesky_interconnecting_2020-1]

[^43]: [@noauthor_home_nodate]

[^44]: [@noauthor_johann_nodate]

[^45]: [@noauthor_anton_nodate]

[^46]: [@10.2307/41640100, S. 22.]