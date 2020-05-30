**+++ ACHTUNG: zu überarbeiten: klingend/notiert ist falsch / Grundstimmung / obertonreine Stimmung / relative Stimmung bleibt? +++**

# Erschließungspraxis bei Instrumentalbesetzungen

Im folgenden Kapitel soll, ausgehend von der derzeitigen Praxis bei der Erschließung von Quellen mit musikinstrumentenbezogenen Metadaten, eine exemplarische Bestandsaufnahme der Problemstellung – hier am Beispiel eines RISM-Datensatzes[^b8661] versucht werden. Die Kenntnis dieser bildet die Grundlage für das Entwickeln denkbarer Lösungsansätze. [**klarer machen, dass das hier exemplarisch ist – in Einleitung?**]
Um ein möglichst breitgefächertes Bild zeichnen zu können, ist es eingangs geeignet, eingangs jeweils ein Beispiel aus dem bibliothekarischen Umfeld, dem Museumswesen sowie aus dem Editionswesen zu untersuchen.

Es finden sich im Datensatz[^b23b1] an zwei [**auch bei "Besetzungshinweis"**] Stellen Informationen zur Besetzung: Zum einen unter "Quellenbeschreibung / Originaler Titel" (MARC-Feld #245\$a (Title))[^b9a22] der String "Cantata â 4 Voci. 2 Corni di Caccia. 2 Violini una Viola è Cont.[?]".

![Besetzung1](medien_Kap2/20200320_RISM_Besetzung1.png)

Zum anderen unter "Weitere Angaben und Bemerkungen" im Unterfeld "Besetzung" (MARC-Feld #594$a (freies Feld))[^b1d26]. 

![Besetzung2](medien_Kap2/20200320_RISM_Besetzung2.png)

Dabei scheint es sich um ein kontrolliertes Vokabular zu handeln.[^b8647] Mehreres fällt an dieser Stelle auf:

1. Die Bezeichnungen der Instrumente in Originaltitel und im Feld "Besetzung" weichen voneinander ab (etwa "Corn[o] da Caccia" vs. "cor da caccia").
2. Die Besetzung in den MARC/XML- bzw. RDF/XML-Dateien ist nicht maschinenlesbar.[^beaa6]
3. Auch auf der Benutzeroberfläche sind die (teils kryptischen) Abkürzungen nicht mit einem Vokabular oder einer disambiguierenden Seite verlinkt.
4. Die Bezeichnung *cor da caccia*[^b1807] ist ungebräuchlich und somit als normierter Term – zumal ohne Disambiguierung – wenig geeignet.

Die Vieldeutigkeit des Terms *cor da caccia* lässt sich dabei auch durch eine Internetrecherche nicht einfach lösen: Die Google-Suche[^b43a9] ergibt neben Treffer zum *Corno da Caccia* auch viele Treffer zu Oboen-Instrumenten wie der *Oboe da Caccia*, dem *Englischhorn* oder zu einem modernen terompetenartigen *Corno da Caccia* mit Ventilen.[^b714c]

Tatsächlich handelt es sich bei der Frage um die Verwendung von Blechblasinstrumenten in der Musik Bachs um auch in der Musikwissenschaft umstrittene Fragestellungen.[^b8646] Doch lassen sich durch Konsultation des autographen Quellenmaterials[^bcbf9] durchaus gewisse verbindliche Aussagen treffen:

* Die Instrumente sind in F gestimmt – das in F-notierte "eingestrichene c" (c') entspricht, dies wird im Bezug zum Basso Continuo deutlich, dem klingenden "kleinen f" (f).
* Es handelt sich aufgrund der stereotypen Stimmführung zwischen den Instrumenten keineswegs um oboenartige Instrumente, sondern um Blechblasinstrumente.
* Angesichts der Lage und der Stellung der Naturtöne lässt sich eine Aussage in Bezug auf die Länge und den Ambitus des Instruments treffen.
* Eingedenk der raumzeitlichen Dimension in der das Stück entstanden ist, ließen sich Verbindungen zu änhlichen erhaltenen Instrumenten herstellen.

Gleichwohl eine solche Erschließungstiefe nicht notwendigerweise bei der Katalogisierung vorausgesetzt werden kann, handelt es sich bei diesen Schlüssen doch um wesentliche Informationen, die eine Disambiguierung – eigentlich Sinn und Zweck eines kontrollierten Vokabulars – in diesem Fall überhaupt erst ermöglichen. **[Das ist gerade bei Instrumenten wichtig, da diese keineswegs eindeutig sind (besonders zu der Zeit)]** Doch auch eine alternative Benennung als "Corno da Caccia"[^b008d] würde wenig zur eigentlichen Begriffsbestimmung beitragen können. Es wird deutlich, dass die semantische Eindeutigkeit der hier untersuchten Entität – wie auch immer sie benannt sein mag – sich letztlich vor allem durch ihre Eigenschaften (Stimmung, Lage etc.) und ihrer Beziehungen zu anderen Entitäten (etwa dem historischen Instrumententyp, der sich in einem Objekt manifestieren könnte) ergibt.[^baafd] Erst mit diesen versehen, hat der Term *cor da caccia* eine aussagekräftige Bedeutung.


# Desiderat

Mit Blick auf die am Beispiel des RISM-Datensatzes identifizierten Mängel und Chancen lassen sich mehrere Schlüsse ziehen:

1. Es liegt auf der Hand, dass das verwendete Vokabular nicht ideal ist. Abgesehen von der offenbarten Unschärfe ist das Vokabular nicht öffentlich einsehbar[^bc1f9] – terminologische Kontrolle somit nicht nachvollziehbar. Um ein alternatives Vokabular zu verwenden, wäre eine philologische Auswertung verfügbarer Klassifikationen und Taxonomien bzw. entsprechender Crosskonkordanzen hinsichtlich ihrer Präzision und Anwendbarkeit erfolgsversprechend.[^b8648]
2. Es sind noch eine Vielzahl weiterer – wie gezeigt wurde: durchaus signifikanter – Aussagen zum verwendeten Instrumentarium sinnvoll.
3. Leider mangelt es an etabliertem, geschweige denn maschinenlesbarem Vokabular, solcherlei Aussagen in eindeutiger Weise treffen zu können.

Wie bereits dargestellt ist eine ausführliche Auseinandersetzung mit musikinstrumentalen Klassifikationen und Taxonomien im Umfang dieser Arbeit nicht sinnvoll. Das augenscheinliche Fehlen von Ausdrucksfähigkeit in Bezug auf bestimmende Eigenschaften von Musikinstrumenten hingegen birgt enormes Potential und bildet mangels entsprechender Vorarbeiten ein wichtiges Desiderat.

Für den Fortgang dieser Arbeit erscheint dabei die Klärung der folgenden Fragestellungen als insbesondere relevant:

1. Welche Eigenschaften fehlen in den einschlägigen Vokabularen?
2. Existieren bereits Vokabulare, womöglich auch aus dem nicht-musikalischen Bereich, die prinzipiell imstande wären, gewünschte Sachverhalte abzubilden?
3. Welche Aussagen können vermöge dieser Vokabulare nicht getroffen werden?
4. Welche Mittel können ergriffen werden, um diese Aussagen doch zu ermöglichen?

Zu 1.: Es existieren zahllose Musikinstrumente. Diese wiederum besitzen unzählige charakteristische Eigenschaften. Es erscheint daher unumgänglich, sich in dieser Arbeit auf ein Instrument oder auf eine Instrumentengruppe zu beschränken. Dieser Schritt ist auch insofern legitimiert, indem die Demonstration grundsätzlicher ontologischer Zusammenhänge eine heuristische Übertragbarkeit des in der Arbeit entwickelten Modells zulässt. Dieser Legitimierung eingedenk bedient sich diese Arbeit deshalb auch in ihrem weiteren Fortgang exemplarisch vornehmlich des bereits eingeführten Beispiels.

Bereits im vorhergehenden Kapitel waren einige Eigenschaften benannt worden, die als bestimmende Eigenschaften des *cor da caccia* (und zwar jenes Typs, der in BWV 208 Verwendung finden sollte) identifiziert wurden. Dies waren etwa: **hier muss jeder Punkt terminolog. belegt sein!**

* Stimmung[^b4ee1]
  * sowohl relative Stimmung[^bd355]
  * als auch absolute Stimmung[^b3141]
  * als auch Temperatur[^bfd29]
* Instrumententyp (also etwa als Mapping zu einer Hornbostel und Sachs-Klassifikation: **xxxxx**[^b17ba])
* Ambitus[^b1389]
* historische Äquivalente, oder, falls bekannt, Objekt
* daraus: Material

Darüber hinaus wären – je nach Verwendungskontext – weitere Eigenschaften denkbar, wie:

* Verwendung in BWV 208
* Interpret
* etc.

Die kontrollierte, maschinenlesbare Darstellbarkeit dieser Eigenschaften in Bezug zu einer ohne sie allzu undifferenzierten und unspezifischen Entität *cor da caccia* wird es sein, die als Indikator für ein Gelingen des Ziels dieser Arbeit auf praktischer Ebene fungiert. Zugleich trägt die gemeinsame Anwendung von Aspekten aus unterschiedlichen Domänen, wie sie oben abgebildet sind[^b429c], eine implizite vorläufige Aussage zur Vernetzbarkeit und den Chancen, die diese birgt, in sich.


## Anwendungsbeispiel

aus der Perspektive von RISM – allerdings auch aus jeder anderen Perpektive (Sucheinstieg) mögl.

Als einfaches "Domänenmodell"[^b8659] am Beispiel des RISM-Datensatzes exemplifiziert (wobei auch jede andere Datenbank gleichermaßen gut herhalten könnte) wäre etwa das folgende Szenario denkbar: Entweder innerhalb des Datensatzes eingeblendet, oder als Verlinkung aus dem String *cor da caccia* heraus ließe sich die Kombination geeigneter Eigenschaften aufrufen. Möglich wären weitere Verlinkungen etwa zu ähnlichen Sammlungsobjekten, zu disambiguierenden Normdaten oder zu weiteren nützlichen Informationen. Umgekehrt erzielte eine Suche mit einer entsprechenden Kombination indizierter Terme – etwa über die RISM SPARQL-Schnittstelle – zumindest den erwähnten Datensatz als Treffer. Eine wesentlich differenziertere und vielfältigere Suche über Spartengrenzen hinweg wäre somit ermöglicht.

![Sucheinstieg über RISM – Bildrechte blabla Naturtonreihe: [@ahrens_horner_2016]](medien_Kap2/20200320_Anwendungsbeispiel.001.png)


---

[^b9a22]: [@noauthor_marc_nodate-2]

[^b1d26]: [@noauthor_marc_nodate-3]

[^b1807]: Es scheint sich hier um einen multilingualen synthetischen Neologismus aus den französischen und italienischen Begriffen *cor de chasse* und *corno da caccia* zu handeln.

[^beaa6]: Sie sind daher selbstverständlich auch nicht über den RISM SPARQL Endpoint suchbar.

[^b43a9]: Durchgeführt am 31.01.2020 LINK

[^b8646]: [@TN_libero_mab2197075]

[^b714c]: Wie bereits erwähnt, ist es nicht Ziel dieser Arbeit, klassifikatorische Fragestellungen zu Musikinstrumenten zu untersuchen.

[^bcbf9]: Johann Sebastian Bach, "Was mir behagt ist nur die muntre Jagd", in: *3 Kantaten, 1 Instrumentalstück*, D-B Mus.ms. Bach P 42, S. 77.

[^b008d]: Vgl. [@noauthor_vizskos_nodate]

[^baafd]: x **das muss näher erklärt werden, durch Literatur abgesichert werden.**

[^bc1f9]: RISM selbst konnte zunächst keine Angaben zu dem verwendeten Vokabular geben – vermutlich habe eine Kollegin eine Datei gespeichert (Anfrage und Korrespondenz am 31.01.2020).

[^b4ee1]: [@auhagen_stimmung_1998-1] 07.02.2020.

[^b17ba]:

[^b1389]: s. o.

[^b23b1]: [@noauthor_20200131_was_nodate]. BWV 208 (http://d-nb.info/gnd/300009178) **<- Fußnote bearbeiten!!**

[^b429c]: Stimmung, Werk aus dem bibliographischen Bereich; Objekt, Material, Instrumententyp aus dem organologischen, musealen Bereich; Fragen zu Werk, Interpretation aus dem Bereich der historischen Musikwissenschaft bzw. dem Editionswesen.

[^bd355]: Wie sie etwa in der Bezeichnung "in F" (der Grundton *f* also nicht anhand seiner Frequenz fest definiert) gemeint ist.

[^b3141]: Etwa *a* = 440 Hz.

[^bfd29]: Etwa die mitteltönige Stimmung einer Orgel.

[^b8647]: Hierbei handelt es sich laut RISM um ein internes Vokabular, das nicht unmittelbar einsehbar ist (s. Fußnote [^bc1f9]).

[^b8648]: Tatsächlich existieren bereits dank des DOREMUS-Projekts **Link** Mappings etwa zwischen dem IAML Medium of Performance-Vokabular **Link** und MIMO **Link**. Laut Korrespondenz mit RISM ist zudem die Erstellung eines neuen RISM-Thesaurus' mit entsprechenden Mappings für 2022 vorgesehen.

[^b8661]: Bei *RISM*, Akronym für *Répertoire International des Sources Musicales*, handelt es sich um "[...] ein länderübergreifendes, gemeinnützig orientiertes Unternehmen mit dem Ziel, die weltweit überlieferten Quellen zur Musik umfassend zu dokumentieren." (vgl.: [@noauthor_unternehmen_nodate]) Für die Musikwissenschaft stellt es das wichtigste Nachweissystem von historischem musikalischem Quellenmaterial (insb. bis etwa 1850) dar. [**in den TexT!**]