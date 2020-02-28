# Literaturverwaltung in disparaten Systemem:

http://u.arizona.edu/~selisker/post/workflow/
https://jaantollander.com/scientific-writing-with-markdown.html

Atom, Zotero, pandoc, GitHub

* Viele coole Addons für Atom!

Package: autocomplete bibtex – muss mit der .bib-Datei verbunden sein

Zotero – Add-On "Better Bibtex" -> Export der ganzen Bibliothek als .bib - dank BB Synchronisation möglich zw. .bib und zotero selbst

* doch wie wird dieses in die Fußnoten der Datei eingebunden / synchronisiert? Über den YAML-Metadatenblock?
https://blog.martinfenner.org/2013/07/30/citeproc-yaml-for-bibliographies/
https://libguides.princeton.edu/c.php?g=148292&p=991756
https://unimelb.libguides.com/c.php?g=565734&p=3897111
**https://pandoc.org/MANUAL.html#fcitations <-**


* wie funktioniert das Rendering in GitHub? (vermutl. nicht)

https://www.soimort.org/notes/161117/ <- yaml und citations


Erkenntnis: der ganze technische Mist macht unheimlichen Aufwand und man muss schon ganz gute Ahnung von Umgang mit cli, programmierbasics etc. haben. Kaum zu stemmen für dumme Geistis
-> wie lässt sich das besser und glatter managen?




mit diesem Befehl hat's geklappt
Alans-MacBook-Air:kap1 alanriedel$ pandoc -s --bibliography zoterobib.bib --filter pandoc-citeproc test.md -o example24a.pdf

/Users/alanriedel/Desktop/vocmaster/literatur/zoterobib.bib

/Users/alanriedel/Desktop/vocmaster/literatur/gfm_stylz.csl

pandoc -s --bibliography /Users/alanriedel/Desktop/vocmaster/literatur/zoterobib.bib --csl /Users/alanriedel/Desktop/vocmaster/literatur/gfm_stylz.csl --filter pandoc-citeproc kap1.md -o example24a.pdf

/Users/alanriedel/Desktop/vocmaster/metadaten.yml

pandoc -s --bibliography zoterobib.bib --csl /Users/alanriedel/Desktop/vocmaster/literatur/gfm_stylz.csl --filter pandoc-citeproc kap1.md -o example24a.pdf

pandoc --filter pandoc-citeproc kap1.md /Users/alanriedel/Desktop/vocmaster/metadaten.yml -s -o out.pdf


mal in die beispiele gucken: wird der yaml-header auch da mit angezeigt? wenn nicht, liegt's am header!
vermutlich erkennt er den yaml block nicht, muss vermutlich erst irgendwie eingestellt werden?

"pandoc-citeproc will look for the following metadata fields in the input. (For details on how to set metadata fields in pandoc's markdown, see the pandoc (1) man page under --metadata, --metadata-file, and Extension: yaml_metadata_block.)"


**eine alternative Art, Fußnoten zu managen: https://www.simondcoll.com/references-markdown-zotero/** <- vgl. Anfrage Schlosser-Blog: https://www.schlosser.info/markdown-latex/#comment-15029



Weitere Links: https://baireuther.de/page/pandoc/
https://www.soimort.org/notes/161117/
