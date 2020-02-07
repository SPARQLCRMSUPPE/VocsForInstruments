# Erschließungspraxis – Beispiel RISM

Im folgenden Kapitel soll, ausgehend von der derzeitigen Praxis bei der Erschließung von Quellen mit musikinstrumentenbezogenen Metadaten, eine exemplarische Bestandsaufnahme der Problemstellung versucht werden. Die Kenntnis dieser bildet die Grundlage für das Entwickeln denkbarer Lösungsansätze.
Um ein möglichst breitgefächertes Bild zeichnen zu können, ist es eingangs geeignet, eingangs jeweils ein Beispiel aus dem bibliothekarischen Umfeld, dem Museumswesen sowie aus dem Editionswesen zu untersuchen. **[da nur 1 Bsp.: anpassen!]**

1. _RISM und das *cor da caccia*_

file:///Users/alanriedel/Zotero/storage/JLSMADRI/singleHit.html **entspr. im GH anpassen** -> Pfad zotero storage hierher verschieben

Es finden sich im Datensatz[^23b1] an zwei Orten Informationen zur Besetzung: Zum einen unter "Quellenbeschreibung / Originaler Titel" (MARC-Feld #245$a (Title))[^9a22] der String "Cantata â 4 Voci. 2 Corni di Caccia. 2 Violini una Viola è Cont.[?]". Zum anderen unter "Weitere Angaben und Bemerkungen" im Unterfeld "Besetzung" (MARC-Feld #594$a (freies Feld))[^1d26]. Dabei scheint es sich um ein kontrolliertes Vokabular zu handeln **was ist das für 1 Vokabular??!**. Mehreres fällt an dieser Stelle auf:

1. Die Bezeichnungen der Instrumente in Originaltitel und im Feld "Besetzung" weichen voneinander ab (etwa "Corn[o] da Caccia" vs. "cor da caccia").
2. Die Besetzung in den MARC/XML- bzw. RDF/XML-Dateien ist nicht maschinenlesbar.[^eaa6]
3. Auch auf der Benutzeroberfläche sind die (teils kryptischen) Abkürzungen nicht mit einem Vokabular oder einer disambiguierenden Seite verlinkt.
4. Die Bezeichnung *cor da caccia*[^1807] ist ungebräuchlich und somit als normierter Term – zumal ohne Disambiguierung – wenig geeignet.

Die Vieldeutigkeit des Terms *cor da caccia* lässt sich dabei auch durch eine Internetrecherche nicht einfach lösen: Die Google-Suche[^43a9] ergibt neben Treffer zum *Corno da Caccia* auch viele Treffer zu Oboen-Instrumenten wie der *Oboe da Caccia*, dem *Englischhorn* oder zu einem modernen terompetenartigen *Corno da Caccia* mit Ventilen.[^714c]

Tatsächlich handelt es sich bei der Frage um die Verwendung von Blechblasinstrumenten in der Musik Bachs um auch in der Musikwissenschaft umstrittene Fragestellungen.[^8646] Doch lassen sich durch Konsultation des autographen Quellenmaterials[^cbf9] durchaus gewisse verbindliche Aussagen treffen:

* Die Instrumente sind in F gestimmt – das in F-notierte "eingestrichene c" (c') entspricht, dies wird im Bezug zum Basso Continuo deutlich, dem klingenden "kleinen f" (f).
* Es handelt sich aufgrund der stereotypen Stimmführung zwischen den Instrumenten keineswegs um oboenartige Instrumente, sondern um Blechblasinstrumente.
* Angesichts der Lage und der Stellung der Naturtöne lässt sich eine Aussage in Bezug auf die Länge und den Ambitus des Instruments treffen.
* Eingedenk der raumzeitlichen Dimension in der das Stück entstanden ist, ließen sich Verbindungen zu änhlichen erhaltenen Instrumenten herstellen.

Gleichwohl eine solche Erschließungstiefe nicht notwendigerweise bei der Katalogisierung vorausgesetzt werden kann, handelt es sich bei diesen Schlüssen doch um wesentliche Informationen, die eine Disambiguierung – eigentlich Sinn und Zweck eines kontrollierten Vokabulars – in diesem Fall überhaupt erst ermöglichen. **[Das ist gerade bei Instrumenten wichtig, da diese keineswegs eindeutig sind (besonders zu der Zeit)]** Doch auch eine alternative Benennung als "Corno da Caccia"[^008d] würde wenig zur eigentlichen Begriffsbestimmung beitragen können. Es wird deutlich, dass die semantische Eindeutigkeit der hier untersuchten Entität – wie auch immer sie benannt sein mag – sich letztlich vor allem durch ihre Eigenschaften (Stimmung, Lage etc.) und ihrer Beziehungen zu anderen Entitäten (etwa dem historischen Instrumententyp, der sich in einem Objekt manifestieren könnte) ergibt.[^aafd] Erst mit diesen versehen hat der Term *cor da caccia* eine geschärfte Bedeutung.

**[Man muss irgendwo erwähnen, dass das so gängige Praxis bei der Erschließung ist]**

# Desiderat

Mit Blick auf die am Beispiel des RISM-Datensatzes identifizierten Mängel und Chancen lassen sich mehrere Schlüsse ziehen:

1. Es liegt auf der Hand, dass das verwendete Vokabular nicht ideal ist. Abgesehen von der offenbarten Unschärfe ist das Vokabular nicht öffentlich einsehbar[^c1f9] – termonologische Kontrolle somit nicht nachvollziehbar. Um ein alternatives Vokabular zu verwenden, wäre eine philologische Auswertung verfügbarer Klassifikationen und Taxonomien bzw. entsprechender Crosskonkordanzen hinsichtlich ihrer Präszision und Anwendbarkeit erfolgsversprechend.
2. Es sind noch eine Vielzahl weiterer – wie gezeigt wurde: durchaus signifikanter – Aussagen zum verwendeten Instrumentarium sinnvoll.
3. Leider mangelt es an etabliertem, geschweige denn maschinenlesbarem Vokabular, solcherlei Aussagen in eindeutiger Weise treffen zu können.

Wie bereits dargestellt ist eine ausführliche Auseinandersetzung mit musikinstrumentalen Klassifikationen und Taxonomien im Umfang dieser Arbeit nicht sinnvoll. Das augenscheinliche Fehlen von Ausdrucksfähigkeit in Bezug auf bestimmende Eigenschaften von Musikinstrumenten hingegen birgt enormes Potential und bildet mangels entsprechender Vorarbeiten ein wichtiges Desiderat.

Für den Fortgang dieser Arbeit erscheint dabei die Klärung der folgenden Fragestellungen als insbesondere relevant:

1. Welche Eigenschaften fehlen in den einschlägigen Vokabularen?
2. Gibt es bereits Vokabulare, die prinzipiell imstande wären, diese Eigenschaften abzubilden?
3. Welche Aussagen können vermöge der untersuchten Vokabularen nicht getroffen werden?
4. Welche Mittel können ergriffen werden, um diese Aussagen doch zu ermöglichen?

Zu 1.: Es existieren zahllose Musikinstrumente. Diese wiederum besitzen unzählige charakteristische Eigenschaften. Es erscheint daher unumgänglich, sich in dieser Arbeit auf ein Instrument oder auf eine Instrumentengruppe zu beschränken. Dieser Schritt ist auch insofern legitimiert, indem die Demonstration grundsätzlicher ontologischer Zusammenhänge eine heuristische Übertragbarkeit des in der Arbeit entwickelten Modells zulässt. Dieser Legitimierung eingedenk bedient sich diese Arbeit deshalb auch in ihrem weiteren Fortgang exemplarisch vornehmlich des bereits eingeführten Beispiels.

Bereits im vorhergehenden Kapitel waren einige Eigenschaften benannt worden, die als bestimmende Eigenschaften des *cor da caccia* (und zwar jenes Typs, der in BWV 208 Verwendung finden sollte) identifiziert wurden. Dies waren etwa:

* Stimmung[^4ee1]
  * sowohl relative Stimmung[^d355]
  * als auch absolute Stimmung[^3141]
  * als auch Temperatur[^fd29]
* Instrumententyp (also etwa als Mapping zu einer Hornbostel und Sachs-Klassifikation: **xxxxx**[^17ba])
* Ambitus[^1389]
* historische Äquivalente, oder, falls bekannt, Objekt
* daraus: Material

Darüber hinaus wären weitere Eigenschaften denkbar, wie:

* Verwendung in BWV 208
* Interpret
* etc.

Die kontrollierte, maschinenlesbare Darstellbarkeit dieser Eigenschaften in Bezug zu einer ohne sie allzu undifferenzierten und unspezifischen Entität *cor da caccia* wird es sein, die als Indikator für ein Gelingen des Ziels dieser Arbeit auf praktischer Ebene herhält. Zugleich trägt die gemeinsame Anwendung von Aspekten aus unterschiedlichen Domänen, wie sie oben abgebildet sind[^429c], eine implizite Aussage zur Vernetzbarkeit und den Chancen, die diese birgt, in sich.

Am Beispiel des RISM-Datensatzes exemplifiziert wäre etwa das folgende Szenario denkbar: Entweder innerhalb des Datensatzes eingeblendet, oder als Verlinkung aus dem String *cor da caccia* heraus ließe sich die Kombination geeigneter Eigenschaften aufrufen. Möglich wären weitere Verlinkungen etwa zu ähnlichen Sammlungsobjekten, zu disambiguierenden Namespaces oder zu weiteren nützlichen Informationen. Umgekehrt erzielte eine Suche mit einer entsprechenden Kombination indizierter Terme – etwa über die RISM SPARQL-Schnittstelle – zumindest den erwähnten Datensatz als Treffer. Eine wesentlich differenziertere und vielfältigere Suche wäre somit ermöglicht.





So würde etwa







1 Bsp., was dann der fassbare Vorteil ist (z.B. ich klicke im RISM-Datensatz auf das Instrument, sehe, welches es eigentlich ist, dergleichen)





Tatsächlich ist die Frage nach der Klassifikation dann ja auch egal: das unscharfe Ding ist dann anhand seiner je spezifischen Eigenschaften definiert bzw. verdeutlicht.












genau: es kann ja schon was geben – man muss es nur herausfinden und dann als Schema "standardisieren"



1 Bsp. (das von oben)


Bedeutung des Terms ist eh uneindeutig bzw. Benenung erstmal egal. Aus dem Kontext wird klar, was gemeint ist. Das heißt jeder kann seine jeweilige Klassifikation verwenden.


Aber: Metadatenprofil, damit nicht irgendwie noch neue quasi-Dubletten entstehen. **<- das kommt in Methodik**






Aus dem


was folgt hieraus? es folgt daraus, dass man 1 gute Taxonomie nehmen muss (oder zumindest Datensätze, die durch Mapping gut definiert sind)
dass noch viele Aussagen möglich und nötig wären, um wirklich schlioeßen zu können, was das für ein Instrument ist (Erschließungstiefen nicht unbedingt möglich. Denkbar: Datenübernahme etwa von Editionen, die diese Erschließungstiefe haben wollen!)
dass es diese Vokabulare nicht gibt! diesen Kontext geben muss –










---

[^9a22]: https://www.loc.gov/marc/bibliographic/bd245.html
[^1d26]: https://www.loc.gov/marc/bibliographic/bd59x.html
[^1807]: Es scheint sich hier um einen multilingualen synthetischen Neologismus aus den französischen und italienischen Begriffen *cor de chasse* und *corno da caccia* zu handeln.
[^eaa6]: Sie sind daher selbstverständlich auch nicht über den RISM SPARQL Endpoint suchbar.
[^43a9]: Durchgeführt am 31.01.2020 LINK
[^8646]: Vgl. etwa Gisela Csiba und Jozsef Csiba, *Die Blechblasinstrumente in Johann Sebastian Bachs Werken*, Kassel 1994.
[^714c]: Wie bereits erwähnt, ist es nicht Ziel dieser Arbeit, klassifikatorische Fragestellungen zu Musikinstrumenten zu untersuchen.
[^cbf9]: Johann Sebastian Bach, "Was mir behagt ist nur die muntre Jagd", in: *3 Kantaten, 1 Instrumentalstück*, D-B Mus.ms. Bach P 42, S. 77.
[^008d]: Vgl. http://www.mimo-db.eu/InstrumentsKeywords/4138
[^aafd]: x **das muss näher erklärt werden, durch Literatur abgesichert werden.**

[^c1f9]: RISM selbst konnte zunächst keine Angaben zu dem verwendeten Vokabular geben – vermutlich habe eine Kollegin eine Datei gespeichert (Anfrage und Korrespondenz am 31.01.2020).
[^4ee1]: Wolfgang Auhagen, Art. "Stimmung und Temperatur, Tasteninstrumente und Bundinstrumente, Temperatur", in: *MGG Online*, Kassel u.a. 2016ff., <https://www.mgg-online.com/mgg/stable/55149> 07.02.2020.
[^17ba]:
[^1389]: s. o.

[^23b1]: Es handelt sich um den RISM-Datensatz... **s. Zotero** zu BWV 208 (http://d-nb.info/gnd/300009178) **<- Fußnote bearbeiten!!**
[^429c]: Stimmung, Werk aus dem bibliographischen Bereich; Objekt, Material, Instrumententyp aus dem organologischen, musealen Bereich; Fragen zu Werk, Interpretation aus dem Bereich der historischen Musikwissenschaft bzw. dem Editionswesen.

[^d355]: Wie sie etwa in der Bezeichnung "in F" (der Grundton *f* also nicht anhand seiner Frequenz fest definiert) gemeint ist.
[^3141]: Etwa *a* = 440 Hz.
[^fd29]: Etwa die mitteltönige Stimmung einer Orgel.
