# Es ist zu laut!

## Worum geht es?

Das Miniserium für Verkehr will die Autobahn A5 vom Frankfurter Kreuz bis zum Frankfurter Westkreuz 10spurig ausbauen. Die Bürgerinitiative "Es ist zu laut" hat gute Gründe, das abzulehnen:

- Der Individualverkehr wird weiter ansteigen -> mehr CO2 wird freigesetzt
- Die Anwohner werden durch noch mehr Verkehrslärm belästigt

In diesem GitHub Repository sind die Dateien für die Website zu finden, mit der wir auf das Problem aufmerksam machen. Du findest die fertige Website auf https://www.esistzulaut.org

## Mitmachen

Jede:r, die/der sich uns anschließen will, ist herzlich dazu eingeladen. Nimm' [Kontakt zu uns auf](mailto:es.ist.zu.laut@gmx.de), wir freuen uns!

Ein Teil unserer Arbeit ist diese Website. Im Weiteren geht es hier darum, wie man die Website modifiziert, richtet sich also eher an die Techniker unter uns.

## Website inhaltlich bearbeiten

Sollen nur inhaltliche Änderungen an der Website gemacht werden, kann man direkt die Dateien in diesem Repository anpassen. GitHub Pages sorgt dafür, dass die Änderungen nach kurzer Zeit (ca. 1-2 Minuten) auf der Website zu sehen sind.

Bei größeren inhaltlichen Änderungen, bei denen z.B. auch Bilder verändert werden oder mehrere Seiten gleichzeitig geändert werden sollen, ist es sinnvoll, einen sog. "Branch" anzulegen und die Änderungen darin vorzunehmen. Wenn alles Notwendige für die Änderung fertig vorbereitet ist, wird der Branch "gemergt", die Änderungen werden gleichzeitig aktiv.

Wie das genau mit dem "branchen" funktioniert, ist [hier beschrieben](https://git-scm.com/book/de/v2/Git-Branching-Einfaches-Branching-und-Merging)

## Änderungen am Layout

Soll das Layout der Seite verändert werden, sollten diese Änderungen zunächst auf dem eigenen Rechner gemacht und erst wenn alles fertig ist, auf GitHub veröffentlicht werden.

Voraussetzung ist, dass man [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) und am besten auch [docker](https://docs.docker.com/get-docker/) installiert hat. Praktisch ist auch, wenn man [Visual Studio Code](https://code.visualstudio.com/download) hat.

Als erstes fertigt man ein "Klon" des Repositories an, indem man im Terminal folgendes Kommando eingibt:

    git clone https://github.com/esistzulaut/website.git

Dies legt ein Verzeichnis "website" im aktuellen Verzeichnis an und kopiert alle im Repository enthaltenen Dateien hinein.

Dann legt man einen Branch für die Änderungen an, die man machen will. Der Branch erhält einen Namen der beschreibt, was man machen will. Dazu ruft man im Terminal ein Kommando wie folgendes auf:

    git checkout -b "farbschema"

Der Name des Branches (hier im Beispiel "farbschema") darf nur Buchstaben, Ziffern und Bindestriche enthalten.

Wenn man dann alle notwendigen Änderungen durchgeführt hat, kann man mit folgenden Kommandos diese wieder an GitHub übertragen:

    git commit -a -m "Neues Farbschema"

In dem Kommando wird innerhalb der Anführungszeichen mit einem meist sehr kurzen Satz beschrieben, was die Änderung bewirken soll, hier im Beispiel, dass ein "Neues Farbschema" eingerichtet wurde. Dieser Satz ist dann später in der "Historie" zu sehen, in der alle vorgenommenen Änderungen (auch die inhaltlichen) dokumentiert sind.

Die Änderungen (der "Commit") kann dann mit dem folgenden Kommando wieder an GitHub übertragen werden, so dass auch Andere die Änderung schon sehen können:

    git push origin "farbschema"

Noch immer sind die Änderungen nur in dem Branch, d.h. sie sind noch nicht auf der Website veröffentlicht. Aber nun kann auf GitHub ein sogenannter "Pull Request" angelegt werden, in dem z.B. ein zweiter Bearbeiter noch Korrekturen vornehmen kann, bevor die Änderung veröffentlich wird.

Geht man direkt nach dem "git push" auf https://github.com/esistzulaut/website, wird im oberen Bereich ein Button angezeigt, mit dem man unmittelbar einen solchen Pull Request anlegen kann. Dieser Pull Request kann dann in den "main" Branch gemergt werden.

Danach bietet es sich an, auf dem eigenenen Rechner wieder auf den Hauptbranch "main" zurück zu wechseln, damit man die nächste Änderung automatisch wieder auf dem neuesten Stand durchführt:

    git checkout main

## Lokal testen

Gerade bei größeren Layout-Änderungen bietet es sich an, diese zunächst lokal (auf dem eigenen Rechner) zu testen. Am einfachsten geht das, wenn man docker installiert hat (s.o.). Dann kann man im Terminal-Fenster folgendes Kommando eingeben:

    scripts/run.sh

Dies wird eine Laufzeitumgebung aus dem Internet herunter laden und starten, welche aus den lokalen Dateien mit den vorgenommenen Änderungen die Website generiert und auf der Adresse http://localhost:4000 verfügbar macht. Nimmt man weitere Änderungen vor, werden die Website-Dateien automatisch neu generiert, so dass man die Auswirkung der Änderungen unmittelbar im Browser verfolgen kann.
