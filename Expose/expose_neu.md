

# Exposé Masterarbeit Alan Riedel

Ein zentrales Anliegen an eine künftige Nationale Forschungsdateninfrastruktur (NFDI) besteht laut Deutscher Forschungsgemeinschaft (DFG) darin, "Datenqualität und Metadaten, Standardbildung, [...] Interoperabilität und Transfer"[^a] zu fördern. Ganz dezidiert werden diese Themen von der DFG dabei trotz notwendiger "fachspezifischer Verankerung"[^b] keineswegs als domänenspezifische, intern-ausgerichtete Aufgaben begriffen, sondern als interkonsortiale, verbindende "Querschnittsthemen"[^c], die es gilt, wo immer möglich auf generische Anwendbarkeit und Validität auszurichten.[^i] Der hiermit implizit exisitierende Wunsch nach ultimativer interdisziplinärer Nachnutzbarkeit von Daten mag angesichts der fachlichen Heterogenität innerhalb der deutschen Forschungslandschaft als überaus ambitioniert erscheinen, unterscheiden sich doch Methoden und Forschungsgegenstände substantiell bzw. fehlen wissenschaftlich nutzbare Standards und Vokabulare in einer Vielzahl von Disziplinen noch weitestgehend. **[da muss ein Bsp. verlinkt werden – idealerweise sagen, das insb. in Naturwiss.]** Zugleich aber muss die Verwendung von gemeinsamen Schemata und Vokabularen als zentrale Prämisse für die Möglichkeit einer Vernetzung interdisziplinärer Daten verstanden werden. Begreift man die NFDI-Ausschreibung als Steuerungsmaßnahme und somit als Indikator einer zukünftigen Wissenschaftskultur, so wird deutlich, dass die Weiter- und Neuntwicklung von interoperablen Vokabularen und Metadatenschemata in der Wissenschaft der kommenden Jahre eine stark zunehmende Priorität einnehmen wird.  
Während die Rolle der Bibliotheken innerhalb dieser neuen Wissenschaftskultur noch nicht endgültig ausdefiniert ist, ist es angesichts der Tatsache, dass Standardisierung und terminologische Arbeit seit jeher zu den zentralen  bibliothekarischen Kernkompetenz gehören, geradezu naheliegend, dass Bibliotheken bzw. Forschungsdatenmanager ihre Kompetenzen in diesem Feld in die disziplinäre Ausbildung entsprechender Strukturen beisteuern werden. Hierbei wird es gelten, geeignete Mittel zu finden, fachspezifische Expertise und bibliothekarisches Generalistentum miteinander auszutarieren.

Auch diese Arbeit bewegt sich innerhalb dieses oftmals nicht trennbaren Spannungsfelds, indem sie es sich zum Ziel macht, ein semantisches Framework für die Entwicklung eines Schemas in Form einer sogenannten *Application Profile*[^d] – in diesem Fall im Feld der musikalischen Besetzungen – zu schaffen, das interdisziplinär anschlussfähig und weiterverwendbar ist, und somit einen fachunspezifischen, generischen Mehrwert bieten kann. Dieser generische Mehrwert beschränkt sich dabei keineswegs auf die terminologische Arbeit, sondern bemisst sich mittelbar auch gerade etwa in der Generierung von allgemeinen Erkenntnissen bezüglich der Modellierung und Entwicklung von spezifischen Metadatenschemata auf Basis vorhandener Vokabulare und Standards, Routinen zur Neuanlage und technischen Verfügbarmachung von Namespaces, einer Fokussierung der Trennschärfe zwischen fachbibliothekarischer und fachwissenschaftlicher Arbeit bei der Modellierung von Applikationsprofilen, oder der Verwendung geeigneter Werkzeuge und Routinen zur kooperativen, gemeinschaftsbasierten Arbeit – allesamt Bestandteile nachfolgender Publikationen.

Es liegt dabei auf der Hand, dass angesichts des Anspruchs nach interdisziplinärer Nutzbarkeit ein technischer Standard Verwendung finden muss, der gleichermaßen in der Musikwissenschaft, wie in jeder anderen denkbaren wissenschaftlichen Domäne anerkannt und je operabel ist. Diese scheinbar nicht einzuhaltende Maßgabe wird jedoch kraft sogennanter *Semantic Web-Technologien* und des Ressource Description Framework (RDF)[^e] erfüllbar. Durch die Verwendung von maschinenlesbaren Bedeutungsträgern (Namespaces), deren Semantik durch ihre allgemein anerkannte – im Gegensatz zu einer disziplinär hochspezifizierten und somit eingeschränkten Nutzung – im Semantic Web bereits etabliert ist, kann hier auf ein erweiterbares und je anpassbares Metadatenschema zurückgegriffen werden, das bereits imstande ist, komplexe, heterogene Sachverhalte maschinenlesbar und interoperabel darzustellen und damit auch Daten von vormals weit entfernten Disziplinen miteinander sprechen zu lassen **[in Beziehung zu setzen (?)]**.

Die musikalische Fokussierung dieser Arbeit geschieht dabei vor allem aus pragmatischen Gründen: einerseits aus der Lagerung eigener fachlicher Expertise heraus, andererseits, da die Entwicklung eines semantischen Frameworks musikalischer Besetzungen momentan ein ausgesprochen vielversprechendes Desiderat ausfüllt, da die bis dato vorhandenen Erschließungsmittel in ihrer Differenziertheit als ungenügend oder als ungenau zu betrachten sind. Zugleich wird bei diesem Beispiel dem interdisziplinären spartenübergreifenden Anspruch an eine NFDI in besonderem Maße Rechnung getragen.[^h]  
Im Sinne des bereits erwähnten Spannungsfeldes zwischen bibliothekarischer und fachwissenschaftlicher Arbeit maßt es sich diese Arbeit dabei keinesfalls etwa an, einen erschöpfenden, präskriptiven Standard für die Erschließung musikalischer Besetzungen vorzulegen. Vielmehr glaubt sie, den geeigneten forschungsdatenmanagerialen Beitrag im Modellieren eines Metadaten Applikationsprofils in Form eines semantischen Grundgerüsts, bestehend aus möglichen Beziehungen (properties) identifiziert zu haben **[redundant?]**, der einen ersten Impuls an die Fachgesellschaft zur weiteren Ausarbeitung - freilich mit kuratorischer bibliothekarischer Mitwirkung - liefern will. Indem sich die Arbeit also bei der Ausarbeitung auf die Ebene der semantischen Bezüge beschränkt, klammert sie zunächst ganz bewusst die Entitätsebene (Datenebene) aus. Eine Standardisierung von verwendeten Vokabularen erscheint hier zwar als ähnlich wichtig, stellt jedoch einen separaten Arbeitsbereich dar, der zum einen nicht gleichermaßen akut[^f] und zum anderen im fachwissenschaftlichen Diskurs am sinnvollsten aufgehoben zu sein scheint[^g].











---


[^a]: Deutsche Forschungsgemeinschaft, *Einschätzungen und Beobachtungen des NFDI-Expertengremiums zur Planung von NFDI-Konsortien*, [Bonn] [2019], S.4, <dfg.de/download/pdf/foerderung/programme/nfdi/stellungnahme_nfdi_eg.pdf>(eingesehen am 04.12.2019).  
[^b]: Ebd.  
[^c]: Ebd.  
[^d]: Zur Begriffserklärung s. etwa: Australian National Data Service (Hrsg.): *Metadata*, (= ANDS Guide), o.O. 2016, S. 6, <https://www.ands.org.au/__data/assets/pdf_file/0004/728041/Metadata-Workinglevel.pdf> (abgerufen am 04.12.2019).  
[^e]: World Wide Web Consortium (Hrsg.): *RDF*, <https://www.w3.org/RDF/> (abgerufen am 04.12.2019).  
[^f]: Bsp.: Beim RDF-Tripel *"Op.23456a" - "hat Besetzung" - "Triangel"* erscheint letztlich die Herkunft (hier wären eine Vielzahl möglicher, oftmals bereits gemappter Normdateien denkbar) der Entitäten *"Op.23456a"* und *"Triangel"* für die Bedeutung weniger sinnstiftend, als die eindeutige Definition der Beziehung *"hat Besetzung"*, die diese beiden Entitäten miteinander verbindet.
Für diese Arbeit ergebe dies das folgende Schema: *"musikalisches Werk" - "hat Besetzung" - "Musikinstrument".*  
[^g]: Die Standardbildung im Falle bereits etablierter heterogener Vokabulare und Schemata erscheint, falls überhaupt möglich, im Gegensatz zur Neuentwicklung von Schemata ein genuin fachwissenschaftliches Unterfangen zu sein - freilich auch hier mit bibliothekarischer Unterstützung.  
[^h]: Bedarfe beschränken sich keinesfalls etwa auf den musikwissenschaftlichen Bereich, sondern reichen etwa auch von der Physik (Akkustik) über die Materialwissenschaften bis hin zu den Geisteswissenschaften und Kulturerbeeinrichtungen.  
[^i]: Vgl. auch den Punkt "Added value to be achieved through the development of cross-disciplinary metadata
standards." als Förderkriterium im Zuge der NFDI-Ausschreibung: Deutsche Forschungsgemeinschaft (Hrsg.), *Guidance Notes on Funding Criteria National Research Data Infrastructure (NFDI)*, o.O. o.J., S. 2, <https://www.dfg.de/formulare/nfdi120/nfdi120_en.pdf>(abgerufen am 04.12.2019).  






---
# Notizen







https://edoc.hu-berlin.de/bitstream/handle/18452/19876/DINI-Thesen_2018_2.pdf?sequence=1&isAllowed=y















"Die  Querverbindungen  zwischen  Konsortien werdeninsbesondere durch  die  gemeinsame Bearbeitung von Querschnittsthemengeschaffen. Hierzu zählen u.a. die während der NFDI-Konferenz  identifizierten  Themen  Ausbildung  und  Training,  Datenqualität  und  Metadaten, Standardbildung, Software und Schnittstellen,Interoperabilität und Transfer sowie Formen der Governance.Diese und andere Themen sind relevant für das Funktionieren und für den Erfolg der NFDI. Für ihre zielführende Bearbeitung ist eine fachspezifische Verankerung notwendig, sodass diese Themen insbesondere im Zusammenwirken der Konsortien bearbeitet werdensollten.  Daher können  und  sollten  Konsortien  sowohl  entsprechende  Ressourcen  einplanen als  auch  im  Antragdarstellen,  welche Querschnittsthemenfür  sie  relevant  sind  und  welchekonsortialen Beiträge sie zu deren Bearbeitung leisten können. Die gemeinsame Gestaltung vonQuerschnittsthemen wird die Zusammenarbeit und die Abstimmungsprozesse zwischen Konsortien  befördernund  somit  maßgeblich  zum  kooperativen  Aufbau  der  NFDI  beitragen. Deshalb   wird eine   Umsetzung   von   Querschnittsthemen   in   spezifischdafür   initiierten Konsortien zum jetzigen Zeitpunkt als nicht sinnvollangesehen."

S.4






Application Profile f. Bestezungen. - Details

was braucht es für beschreibende Elemente, in die in einem zweiten Schritt Datenwerte eingefügt werden könnten?



Nimmt man die NFDI-Initiative als Indikator einer künftigen Wissenschaftspraxis, ja Wissenschaftsphilosophie, so ...









Der in diesem Anspruch exemplifizierte Offenheitsgedanke sowie die hieraus resultierende Interoperabilität[] können dabei als Symptome eines beginnenden Paradigmenwechseln hin zu einer offenen, überfachlichen und in partizipativen Strukturen arbeitenden Wissenschaft verstanden werden (ein weiteres Beispiel wäre etwa das Projekt GND4C).

In dieser Wissenschaft der Zukunft, so mag es scheinen, spielt das Schaffen einer gemeinsamen Sprache sowie von Arbeitsmitteln, die eine kooperative Zusammenarbeit ermöglichen, eine übergeordnete Rolle.




-> RDF <-

Vokabulare sind immer als interdisziplinär und anschlussfähig zu werten!

Ontologien, die auf LOD / RDF basieren erfüllen das perfekt, weil verwendete Vokabulare eh "objektive", unabhängige Semantik besitzen (anschlussfähig)

**immer wichtiger: kooperative(?) Anfertigung -> soll ausgetestet werden, welche Routinen hierfür gut eignen (= ist übertragbar) – vor allem wohl auch Naturwiss.! <- kommt später**

geht darum, ein semantisches Framework (= Application profile) zu schafen, in das anschließend Datenwerte eingepflegt werden könnten.

auch, klar: bislang Sache von Bibliotheken, soll aber immer mehr aus den Fachcommunities kommen - also wäre Frage!

Vorstellbar, dass etwa an Bibliotheken jenes semantische Framework als Grundlage geschaffen wird, welches dann in die Fachcommunity übergeben wird und dann – während sie die inhaltl.-wiss. Arbeit machen, lediglich nachkuratiert wird.

sinnvollerweise mit Musik, weil Expertise hier liegt, weil großes Desiderat - aber: kommt ja allen zugute (s.o.) und halt *hier muss man auch nochmal ins Detail gegangen werden.*







Dabei herausfinden, was ist (in diesem Fall) fachspezifisch und was ist generisch? Welche *allgemeinen* Schlüsse lassen sich daraus ziehen, die auf die jeweilige fachspezifische Arbeit anwendbar sind.
Spannungsfeld zwischen domänenspezifischen Anforderungen und möglichst großer Validität.






















Community driven science -> Tendenz wird offensichtlich etwa in GND4C oder NFDI4C <- dafür muss aber Grundlage da sein

In NFDI-Antrag: Entwicklung v. Metadatenschemata ist offensichtlich außerordentlich wichtig.



In wie weit ist Übertragbarkeit da?

- Spartenübergreifend – Objekte nutzbar für alle - Normativität – Anknüpfung: andere Geisteswissenschaften bei Erstellung neuer Vokabulare. (Wenn sie noch nicht existieren: z.B. Kunstgeschichte, Architektur, Archäologie, Geographie etc.) -> Nutzen wäre, man kann ableiten, was man machen kann, wenn noch nichts existiert / spartenübergreifend / interdisziplinär (z.B Akkustik?)

- Workflows: Neuanlage von Properties, do-it-yourself-Projekte: Worflows (interessant etwa für Sammlungen, Wissenschaften, die sich Klassifikationen befassen/eigene erstellen) (also auch Biologie, Geologie etc.)

- auch Wissensmanagement allg.

- wie kann die Auseinandersetzung mit (musikalischen) Vokabularen als interdisziplinär relevant begründet werden?
  -> exemplarisch für die Auswertung und den Miteinbezug von sowohl generischen Vokabularen wie auch fachspezifischen (wirklich interdisziplinär!)


Fehlende Standards / Vokabulare in vielen Fachdisziplinen!!



Musik expemplarisch

Liegt nahe, da hier Expertise besteht.


Soll die Weichen legen für die generische Anknüpfbarkeit






Anknüpfungspunkte an andere Disziplinen hervorheben
