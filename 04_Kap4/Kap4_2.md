Vielleicht generell: als Ende jedes Teils ein Teil "Änderungen am Vokabular" oder so, in dem alle Änderungen nochmal nachvollziebar gemacht werden? Zu aufwendig?

1 Mal (NUR) exemplarisch durchgespielt

### Interpret und Aufführung

#### Interpret und Aufführung

* CIDOC CRM verfügt über das Property `P14`: "This property describes the active participation of an instance of E39 Actor in an instance of E7 Activity."[^d1] Diese Definition erscheint für den vorliegenden Anwendungsfall allzu allgemein gefasst und daher unpassend.

* Ähnlich verhält es sich mit den Properties des *Europeana Data Models*, die in Verbindung mit der Klasse `edm:agent` Verwendung finden.[^d2]

* *Wikidata* verfügt über das Property `wd:P175` ("performer")[^d3]. Während Wikidata aufgrund der potnenitellen Instabilität seiner Terme zwar in der Regel keine Verwendung im Rahmen dieser Arbeit, verweist Wikidata in seiner Eigenschaft als Data Hub unter anderem auf den folgenden Datensatz:

* Auf *schema.org* findet sich das Property `schema:byArtist`.[^d4] mit möglichen Objekten `schema:musicGroup` und `schema:person`. Als Subjekte kommen `schema:musicAlbum`oder `schema:musicRecording` infrage. Während die Objekte geeignet erscheinen, anwendungsrelevante Sachverhalte wiederzugeben, sind die Subjekte offenbar auf Audioaufnahmen beschränkt: Somit können sämtliche Aufführung, die nicht in Form einer Aufnahme vorliegen, nicht repräsentiert werden.

* In der *DOREMUS Ontology*[^d7] finden sich die Properties `mus:U54`[^d5] ("is performed expression of") und `mus:U81`[^d6] ("had performer status"). Jedoch scheint ersteres durch die implizit starke Konzentration auf FRBR für eine generische Anwendung überkomplex und nicht sachgemäß. Letzteres ist offenbar auf eine Verwendung bei der Erfassung von Konzertprogrammen semantisch ausgerichtet und  somit für das vorliegende Anwendungsszenario ebenfalls unsachgemäß.

* In der *GND Ontology* findet sich das Property `gnd:instrumentalist`[^d8] mit Domain `gnd:work` und Range `gnd:differentiatedPerson`. Während diese Verwendungsspezifikationen dem globalen Zweck einer Verbindung von Instrumenten und Werken gerecht wird, würde eine Verwendung die Darstellung einiger möglicher angrenzender Sachverhalte erschweren. So sind mit diesem Property etwa vokale Äußerungen jeder Form ausgeschlossen. Dies wirft gerade im Bereich der Musik des letzten Jahrhunderts etliche Probleme auf – was ist etwa mit gesampleten Stimmen mit anschließender Verzerrung, oder was ist mit instrumentell-imitatorischen Äußerungen des Vokaltrakts, etwa dem sog. *Vocal Percussion*?

* Im Rahmen des *Body&Soul*-Projekts[^d9] findet das Property `mo:performer` der *Music Ontology* Verwendung. Seine Domain ist mit `mo:performance`[^d10] und dem Range `foaf:agent`[^d11] sehr allgemein gehalten, sodass hohe Anschlussfähigkeit gewährleistet wird. 

Allerdings entspricht die Klasse `foaf:agent` nicht der vorgesehenen Klasse `ma:Person`, welche besser durch die Klasse `foaf:person`[^d12] dargestellt würde. Diese Inkonsistenz ist jedoch keineswegs als Defizit aufzufassen, eröffnet doch die Klasse `foaf:agent` das Modell für weitere Szenarien: So lässt sich das Darstellungsspektrum um Instanzen in Form von Personen, wie auch Körperschaften, die dieser Klasse subsumiert werden, erweitern: So werden Aussagen der Form
\
"\<Das Werk Soundso> \<wird gespielt von> \<dem Blockflötenensemble "Schlingenfittich">"

ermöglicht. Diese Darstellungstiefe ist dabei nicht nur im "Werk-Ereignisbereich", sondern auch im Bereich der Musikinstrumente wichtig. So werden auch Aussagen der folgenden Form ermöglicht:
\
"\<Klavierduo Soundso> \<spielt auf> \<dem Klavier "Objekt Schlagmichtot">"

Soll `foaf:agent` Verwendung finden, muss das Datenmodell dergestalt ummodelliert werden, dass `foaf:person` zur Unterklasse von `foaf:agent` wird. Dies geschieht mit dem bereits bekannten Property `rdfs:subclassOf`. Zugleich tritt anstelle des Propertys `ma:Interpret` das Property `mo:performer`. Dessen Range wiederum muss auf `foaf:agent` bezogen werden. Da das Property `rdfs:subclassOf` transitiv ist[^d13], wird die Range-Beschränkung auch auf mögliche Unterklassen von `foaf:agent` vererbt und gilt somit auch für `foaf:person`. [ist das wirklich so???]\


#### Personennormdaten

Die Instanz `ma:Person_a` stellt eine Variable dar, die je nach Bedarf mit entsprechenden Normdaten aus beliebigen externen Vokabularen befüllt werden kann (GND, LCNAF[^d14], VIAF[^d15], Wikidata etc.).

Da die Entitäten `ma:hat_Name` und `ma:hat_Lebensdaten`, ursprünglich ja als Attribute im ERM eingeführt, in der Regel Bestandteil von Personennormdatensätzen sind, können erstere als obsolet betrachtet werden und aus dem Vokabular entfernt werden.


#### Modellierung von Zusammenhängen zwischen Musikinstrumenten, Interpreten und Aufführungen

Während Aussagen gemäß dem Schema
\
"\<das Klavier "Objekt Schlagmichtot"> \<wird bespielt von> \<Klavierduo Soundso>"

nun in Bezug auf auf das Objekt dank `foaf:agent` ermöglicht worden sind, ist aufgrund der Beschränkungen von `mo:performer` mit diesem Property eine Verbindung mit einem Subjekt in Form eines Musikinstruments – immerhin eines der zentralen Anliegen dieser Arbeit – nicht möglich.

Während die Modellierung im ERM kraft der einfachen Eigenschaft "Interpret" erfolgte, wird spätestens zu diesem Zeitpunkt deutlich, dass dieses an äußere Vorgaben ungebundene, monodimensionale Modell der vorgefundenen Realität des Semantic Web nicht mehr gerecht werden kann. Es gilt daher, Um- und Neumodellierungen vorzunehmen.\

1)\ Zentraler Verbindungsknoten bei der Modellierung von Instrument und Interpret ist das Ereignis in Form einer Aufführung, durch die nun einzuführende Klasse `mo:performance`[^d16] vertreten, unter die domänenspezifische Ereignisse (also Instanzen von `ma:Aufführung_Domäne)` fallen. Durch die Einführung dieser Oberklasse wird die Klasse `ma:Aufführung_Domäne` typisiert und in das Semantic Web eingebettet.  Eine Verbindung zwischen Instrumenten und Aufführungen kann dabei mit der Property `mo:instrument` erfolgen: "[The property r]elates a performance to a musical instrument involved [.]"[^d17] Diese Verbindung ist zum einen zum Objektbereich zu knüpfen:\

`mo:performance	mo:instrument	ma:Objekt_Domäne .`
\
Zum anderen muss eine Verknüpfung "werkseitig" erfolgen. Hier bietet es sich an, angesichts der ohnehin angedachten Normierung durch Mapping zu einer Klassifikation, direkt eine Verbindung zwischen entsprechender Klasse und Aufführung zu schaffen:\

`mo:performance	mo:instrument	ma:Instrument_(Klassifikation) .`
\
2)\ Während es nun möglich ist, sowohl die Beteiligung eines Musikinstruments, wie auch der einer Person an einer Aufführung darzustellen, befinden sich beide Entitäten noch in kontingentem Verhältnis zueinander. Noch besteht kein Konnex zwischen Instrument und Person: die Aussage, jemand spiele ein Instrument, ist noch nicht ermöglicht.

Erstaunlicherweise findet sich in den großen etablierten Vokabularen keine Terminologie, um diesen scheinbar banalen Sachverhalt abzubilden. Fündig wird man jedoch in der *Linked Irish Traditional Music Ontology*.[^d18] Das Property L58[^d20] ("played on instrument") und das inverse Property L58i[^d19] ("instrument played by") geben den hier gewünschten Sachverhalt in geeigneter Weise wieder.

![](medien_Kap4/20200526_interpret3.png)

Hierbei ergeben sich auch einige Fragen bezüglich der Verwendung der Entität `ma:Instrument_Domäne`, die im folgenden Kapitel zu diskutieren sein werden.


### Mapping und Klassifikation
#### "Medium of Performance"

Ein Ziel dieser Arbeit liegt in der Maximierung der Anschlussfähigkeit des entwickelten Metadatenprofils. An diese Maximierung geknüpft, befindet sich die Offenheit seiner Konzepte, deren Fokussierung möglicher Endpunkt eines diskursiven, Community-Verfahrens darstellen könnte. Somit muss an dieser Stelle die Schärfung des Konzepts "Musikinstrument" zum einen nicht vorweggenommen werden, zum anderen gilt es sogar, dieses Konzept möglichst weit zu fassen und somit integrativ zu gestalten. Hierfür bietet die Idee des "Medium of Performance" einen guten Anfangspunkt, in RDA 6.15.1.1 als "[a]n instrument, voice, and/or ensemble for which a musical work was originally conceived[...]",[^18] definiert. 

Während dieses Konzept erfreulicherweise Musikinstrumente im herkömmlichen Sinne um weitere Medien musikalischer Äußerung ergänzt, erscheint jedoch die dieser Definition inhärente deterministische Qualität sowie die eindimensionale Ausrichtung auf die Entität "Werk" hier einigermaßen fehl am Platz. Diese Arbeit nimmt vielmehr eine phänomenologische Perspektive ein, indem sie davon ausgeht, dass jede Entität, die in der Lage ist, Klang zu erzeugen, das situative Potential besitzt, die Funktion "Musikinstrument" einzunehmen (abermals ließe sich hier Heidegger bemühen). So kann beispielsweise auch eine zufällig vor-(/bzw. "zu-")handene Flasche[^19] oder jeder andere beliebige Gegenstand situationsbezogen zum Musikinstrument werden. Selbst beispielsweise Boethius' im Mittelalter außerordentlich einflussreiche und fest im sog. *Quadrivium* verankerte Idee "kosmischer Musik", die *musica mundana*,[^20] findet als Zusammenspiel verschiedener "Medien", der Himmelskörper, Raum in diesem Verständnis. An letzterem Beispiel wird dabei deutlich, dass in dieser Arbeit auch das Konzept "performance" in einem sehr allgemeinen Verständnis Verwendung findet. Prämisse einer solchen "Performance" bildet also nicht etwa eine wie auch immer geartete artifizielle "Performativität"[^21]. Zugleich besteht – im Gegensatz etwa zu RDA – kein notwendiger und schon gar kein hierarchischer Zusammenhang zwischen Medium und Werk. Auch ein Museumsobjekt gilt – kraft seines Potentials, Medium einer musikalischen Äußerung (gewesen) zu sein – in dieser Arbeit als "Medium of Performance". Gleichzeitig wird, eingedenk dieser phänomenologischen Annäherungsweise vorgehend, der Begriff "Musik" ebenfalls zum außerordentlich integrativen Konzept, nach dem – man denke an Boethius – genau dasjenige als Musik aufzufassen ist, das als solches wahrgenommen wird – und dies selbst unabhängig von einer (nicht-)vorhandenen "Klanglichkeit". So liegt denn also "Musik" gewissermaßen im Auge des Betrachters, und das Medium dieser Wahrnehmung ist ein – im eigentlichen Wortsinne – "instrumentales" Werkzeug – ein (Musik-)Instrument.
\
Bislang wurde in dieser Arbeit das Konzept `ma:Instrument_Klassifikation` als Platzhalter verwendet. Im Sinne einer Anbindung ans Semantic Web sollte jedoch nach einem etablierten Term gesucht werden. Zwar findet sich in der *Performed Music Ontology* – eine Ontologie,[^23] die für den Gebrauch im Rahmen von *BIBFRAME* entwickelt worden ist –[^22] die Klasse `pmo:mediumOfPerformance`[^24], jedoch ist davon auszugehen, dass sie an RDA angelegt ist und daher keinen Raum für Nutzungsszenarien, wie sie eben exemplifiziert wurden, bietet.

Vielversprechender erscheint das Konzept `mus:M14`[^25] ("medium of performance") der DOREMUS-Ontologie. Dies jedoch leider vor allem deshalb, da sie – zumindest auf den ersten Blick – keinerlei inhärente Einschränkungen bei ihrer Verwendung vorgibt. Entsprechend wird im Folgenden das Konzept `ma:Instrument_Klassifikation` mit dem Konzept `mus:M14` ersetzt.

Jedoch erschiene es sinnvoll, im Nachgang dieser Arbeit im Rahmen eines Community-basierten Diskurses die Neuanlage eines Konzepts zu prüfen, um ein höheres Maß an Offenheit, Anschlussfähigkeit und Unabhängigkeit gegenüber bibliographisch-"gedachten" Modellen wie insbesondere RDA / IFLA-LRM erzielen zu können.

[klarer machen: auf der einen Seite wird der ganze Klassifikationskram bedient, auf der anderen die Objekt – Ressourcen-Beziehungen] **<- Einleitend in den jew. Abschnitten.**

#### Herausforderungen
\ 
Dieser Option lag das Anliegen zugrunde, "werkseitig" fallspezifisch unsaubere oder unspezifische Vokabulare durch In-Beziehung-Setzen zu Musikinstrumenten – entweder über eine Klassifikation, oder direkt gegenüber einem Objekt – zu disambiguieren. Diese Fallspezifität birgt jedoch auch Probleme: Kehrte man die Perspektive zu einer "objektseitigen" um, so mündete ein Suchvorgang unter Umständen in eine mit ambiguösem Vokabular indexierte Treffermenge und somit in übermäßig viele *False Positives*.
Dieses Problem ist nicht einfach lösbar, und es scheint, dass eine wirklich symmetrische Lösung auf terminologischer Basis nur Ergebnis eines gründlichen Standardisierungsprozesses zu schaffen sein wird. Allerdings exisiteren bereits Ansätze, die aus "umgekehrter Richtung" hin zu einer Verbindung zwischen Objekt und Werk vorstoßen: Im Artikel "A Timeline Metaphor for Analyzing the Relationships between Musical Instruments and Musical Pieces",[^d21] einer Publikation aus dem *MusiXplora*-Umfeld,[^d25] wird beschrieben, wie anhand eines statistischen Abgleichverfahrens zwischen Objekt- und Werkmetadaten (Similarity Measure) eine gute Trefferquote bei der maschinellen Herstellung von Objekt-/Werkbeziehungen zwischen MIMO- und RISM-Einträgen erzielt wird. 
Der Umstand, dass bereits auf Verfahren verwiesen werden kann, die die "objektseitige" Verlinkung abdecken, lässt das eingangs beschriebene Defizit als zunächst verschmerzbar erscheinen. Angesichts dessen jedoch, dass die die Ergebnisse der Verlinkung laut Artikel noch einen intellektuellen Redaktionsprozess erfordern[^d22] bzw. soweit bekannt nicht mit Semantic Web-Technologien erschlossen sind, erschiene vielmehr ein synergetischer hybrider Ansatz, der die hohe intellektuelle Qualität mittels der hier vorgeschlagenen Methodik mit der im Artikel beschriebenen maschinellen Effizienz koppelt, als verfolgenswerter Ansatz.

#### Mapping
\
Zum Mappen hat sich das ebenfalls durch die W3C standardisierte Vokabular SKOS ("Simple Knowledge Organization System")[^d24] etabliert.[^d23] Das Modell sieht zwei Anwendungsszenarien vor:

##### Mapping über Klassifikation

Verbindungen zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` werden über eine Unterklasse von `mus:M14` ("Medium of Performance") hergestellt. Dabei ist der jeweilige Vertreter der Klasse `ma:Objekt_(Domäne)` eine Instanz der Klasse `mus:M14`. Dieser Sachverhalt kann mit `rdf:type`, wie auch bereits in #Kapitel geschehen, wiedergegeben werden (das Property `ma:Typ` kann entsprechend entfernt werden):

`ma:Objekt_(Domäne)	rdf:type	mus:M14	.`

Die Entität `ma:Instrument_nach_Vokabular_(Domäne)` findet ihre fallspezifische exakte Entsprechung in der Entität `mus:M14`, sodass mit `skos:exactMatch` eine Äquivalenzrelation dargestellt werden kann:

`ma:Instrument_nach_Vokabular_(Domäne)	skos:exactMatch	mus:M14	.`

Eine Verwendung weiterer, vagerer SKOS-Relationen erscheint – da von einem "werkseitigen" Mappen ausgegangen wird – an dieser Stelle nicht sinnvoll, soll doch das uneindeutige Domänenvokabular durch Mappen dismabiguiert werden.

![](medien_Kap4/20200602_Klass2.png)

###### Klassifikation

Die Entscheidung für eine Klassifikation muss – aus bereits dargelegten Gründen – domänenübergreifend geschehen. Zudem kann an dieser Stelle – wie ebenfalls bereits erwähnt – keine systematische, kritische Untersuchung vorhandener Klassifikationen erfolgen, die eine Entscheidungsgrundlage anbieten könnte. Darin, eine solche Untersuchung vorzunehmen, liegt jedoch ein großes Potential für zukünftige Arbeiten begründet.
Vorläufig lässt sich jedoch festellen, dass insbesondere der sog. *MIMO Thesaurus*[^15] eine tragfähige klassifikatorische Infrastruktur zu bieten scheint. Weitere Möglichkeiten, insbesondere für die Verwendung von Stimmen,[^17] finden sich im *IAML Medium of Performance Vocabulary*.[^16] Vor allem erscheint denkbar, ähnlich zum hier gewählten Vorgehen, ein Metadatenprofil zu entwickeln, das die Darstellungstiefen verschiedener Klassifikationen und Vokabulare kombiniert und zueinander in Beziehung setzt.

##### Direktes Mapping

Bei der Herstellung einer direkten Relation zwischen `ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` erscheinen verschiedene Szenarien vorstellbar. Es erscheint daher sinnvoll eine Relation als sog. "Superproperty" zu definieren, unter die alle weiteren Relationen ("Subpropertys") subsumiert werden. Als Superproperty ist dabei die Property `dc:relation`[^11] der *Dublin Core Metadata Initiative* als besonders standardisiert zu betrachten. Unter ihn können mit der Property `rdfs:subpropertyOf`[^12] Subproperties für die folgenden Szenarien eingeordnet werden:

* Zur Exemplifizierung eines Terms wird auf ein beispielhaftes Objekt verwiesen. Dies ist auch im hier behandelten Anwendungsbeispiel der Fall: dem Term `rism:cor_da_caccia` kann aufgrund bestehender Gemeinsamkeiten hinsichtlich Region (Herstellungs-/Kompositionsort: Mitteldeutschland) und Zeit (erste Hälfte 18. Jahrhundert) ein Objekt zugewiesen werden, das als beispielhaft für den Typ des etwa bei der Uraufführung verwendeten Instruments sein könnte.
SKOS bietet dabei das Property `skos:example`[^1], dessen Zweck jedoch nicht im Verlinken mit beispielhaften Instanzen zu bestehen, sondern darin zu liegen scheint, beispielhafte Verwendung von Termen zu illustrieren.[^2] 

Da das Verlinken zu Objekten weniger im bibliographischen Bereich, als im Museumswesen eine Rolle spielt, erscheint es angebracht, in letzterem nach anwendbarer Terminologie zu suchen: Hier erscheint insbesondere das bereits erwähnte CIDOC CRM eine gute Anlaufstelle zu bieten. Dort findet sich das Property `crm:P137`[^3] mit dem Label "exemplifies (is exemplified by)". Die Domain des Propertys ist dabei auf `crm:E1`[^4] (Entity) bezogen – die Range auf `crm:E55` (Type).[^5] Beim Konzept `crm:E55` handelt es sich um "CIDOC CRM’s interface to domain specific ontologies and thesauri",[^6] indem die domänenspezifischen Terme etwa mit der Property  `crm:P127`[^7] "has broader term (has narrower term)" zu Unterklassen von `crm:E55` deklariert werden.[^8] Es erscheint daher sinnvoll:
- das Property `crm:P137` für die Relation "Beispiel" zwischen`ma:Instrument_nach_Vokabular_(Domäne)` und `ma:Objekt_(Domäne)` einzuführen. Bemerkenswert ist zudem, diese Property als eine sog. *symmetric property* definiert werden kann, bei der also Domain und Range variabel sind.[^27] Sie wird dabei durch die Eigenschaft `owl:symmetricProperty`[^28] als solche klassifiziert.
- Anstelle der Entität `ma:Instrument_nach_Vokabular_(Domäne)` kann die Entität `crm:E55` (Type) als Schnittstelle zwischen domänenspezifischem Vokabular und dem Metadatenprofil verwendet werden.
- Das Konzept `crm:E19`[^9] ("physical object") kann, als Unterklasse von `crm:E1`, dabei anstelle von `ma:Objekt_(Domäne)` verwendet werden, um den gleichen Effekt zu erzielen.
- Indem `crm:E55` mit `rdf:type` als Musikinstrument gekennzeichnet wird, kann festgelegt werden, dass es sich bei allen Unterklassen und Instanzen um Musikinstrumente handelt. Dies kann anstelle der Klasse `ma:Instrument_(Domäne)` geschehen. Obwohl die "großen" Domänenvokabulare (GND, LCSH etc.) vielfältige Terme bereithalten, fallen auch hier Terme aus Vokabularen in die engere Auswahl, die ein hohes Maß an Verbreitung versprechen: Der Datensatz `wd:Q34379` "musical instrument" in Wikidata[^10] weist als "Data Hub" eine Vielzahl von Mappings zu anderen Vokabularen auf und ist daher außerordentlich aussagekräftig. Obwohl Wikidata-Datensätze grundsätzlich manipulierbar sind und daher semantische Persistenz nicht garantieren können, handelt es sich bei "musical instrument" um ein sehr zentrales Konzept, das nicht ohne weiteres zu verändern sein wird. Und tatsächlich ist die "maschineninterpretierbare", kontextuell-hergestellte Semantik nicht weniger persistent als bei anderen, angeblich persistenteren Vokabularen. Eine Übernahme in das Metadatenprofil erscheint daher möglich. 

* Einen gängigen Anwendungsfall stellt das Szenario dar, dass eine Äquivalenzrelation zwischen Domänenvokabular und Objekt dargestellt werden soll. Beispielhafte Sachverhalte wären – etwa im Falle einer Audioaufnahme: "Anne Sophie Mutter spielt auf ihrer Stradivari *Lord Dunn-Raven*"[^26], oder "J. S. Bach nimmt die *Hildebrandt Orgel* von *St. Wenzel* in Naumburg ab".[^14] Es müsste also eine Verknüpfung zwischen einem domänenspezifischen Vokabular – etwa der GND – und einem Objekt hergestellt werden, die besagt, dass es beide Entitäten ein identisches Instrument bezeichnen. Dies kann etwa mithilfe der Property `owl:sameAs`,[^13] im Übrigens ebenfalls eine *symmetric property*, geschehen. Analog zu den bereits beschriebenen Herausforderungen beim Mappen über eine Klassifikation ergibt sich jedoch auch hier beim Mappen zwischen einer Entität des Typs *Instanz* und einer des Typs *Klasse* ein Problem: Während das ambiguöse Domänenvokabular durch den Verweis auf ein spezifisches Objekt disambiguiert wird, folgt "objektseitig" die logische Aussage, mit der "werkseitigen" Verwendung eines (eigentlich generischen) Terms sei immer genau jenes Objekt gemeint.

Einen möglichen Ausweg böte unter Umständen die Verwendung von `rdf:type`, um dieses hierarchische Problem zu umgehen. In diesem Fall müsste jedoch die Superproperty `dc:relation` entfernt werden, würde doch so jede `rdf:type`-Beziehung – also auch etwa die, die festlegt, dass `dc:relation` eine Property ist – zu einer Subproperty von `dc:relation`. Dies wäre falsch.

Daher soll `owl:sameAs` "als Krücke", im Bewusstsein seiner Unzulänglichkeit vorläufig beibehalten werden.

![blablablub – fett umrandet: die übergeordneten Klassen und Properties](/medien_Kap4/20200603_mappKlass.png)

##### Erkenntnisse aus der Modellierung

Das – ursprünglich immerhin recht zentrale – Anliegen dieser Arbeit, eine "werk- und objektseitig" symmetrische Verbindung zwischen Vokabularen und Objekten zu schaffen, konnte im Vorhergehenden in nur sehr dürftiger Weise erfüllt werden. Insbesondere die spartenübergreifende Tragweite der Implikationen dieser Verbindung bringen es mit sich, dass diese Arbeit nun zum ersten Mal an einen Punkt gerät, an dem deutlich wird, dass die Lösung eines Problems nur im Rahmen eines anschließenden gemeinschaftlichen Prozesses möglich sein wird. Die notwendigen gedanklichen Vorarbeiten leisten dabei die in diesem Kapitel ausgebreiteten Ausführungen.




—

Erkenntnisse: 
- so allgemein wie möglich <- das muss nochmal ausgeführt werden!
Denkbar: 
1 - Fokussierung muss erst noch erfolgen
2 - Anschlussfähigkeit für vielfältige (vielleicht noch gar nicht in Erwägung gezogene) Anwendungsszenarien


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