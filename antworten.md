\# Antworten Generalprobe



\## Teil A – Orientierung

A1: Aktueller Branch: main (Sternchen bei git branch). Weitere Branches: feature/snacks, feature/neuer-titel.

A2: Untracked: kasse.log und test/. Untracked=Git sieht die Dateien, versioniert sie aber nicht.

A3: In .git liegt die komplette Versionsgeschichte. Löscht man .git, ist es kein Repo mehr: Dateien bleiben, Historie ist weg.



\## Teil B – Fast-Forward-Merge

B1: Ausgabe zeigt "Fast-forward", im Log kein Merge-Commit, Linie bleibt gerade.

B2: main hatte seit der Abspaltung keine neuen Commits, Git musste nur den Zeiger von main vorschieben.



\## Teil C – Fehler finden mit git diff

C1: In preise.js steht in der Kinderpreis-Bedingung alter > 14 statt alter < 14. Dadurch zahlen alle über 14, auch Erwachsene, den Kinderpreis.

C2: git diff vergleicht Arbeitsverzeichnis mit Staging-Area; nach git add sind beide gleich, also keine Ausgabe. git diff --staged vergleicht Staging-Area mit letztem Commit, dort liegt der Unterschied.



\## Teil D – git revert

D1: Ja, der Commit "Werbebanner eingefügt" ist noch in der Historie. Neu dazugekommen ist ein Revert-Commit, der die Änderung rückgängig macht.

D2: Im Team-Repo darf man veröffentlichte Historie nicht umschreiben. Revert ist nachvollziehbar und sicher, Löschen würde die Repos der anderen durcheinanderbringen.



\## Teil E – .gitignore

E1: > überschreibt die Datei, >> hängt an das Ende an.

E2: Vorher: kasse.log und test/ als untracked. Nachher: nur noch .gitignore als neue Datei, kasse.log und test/ werden ignoriert. Nach dem Commit ist git status sauber.



\## Teil F – Merge-Konflikt

F1: Die Branches haben sich auseinanderentwickelt, main hat eigene neue Commits. Ein reines Vorschieben des Zeigers ist nicht möglich.

F2: HEAD = aktueller Branch (main), also meine Version. feature/neuer-titel = Version vom Branch, der gemerged wird.

F3: Beide Branches haben dieselbe Zeile unterschiedlich geändert. Git kann nicht entscheiden, welche richtig ist, ein Mensch muss wählen.



\## Teil G – GitHub

G1: git status vergleicht nur mit dem lokal bekannten Stand von origin/main. Ohne fetch weiß Git nichts von der neuen Änderung auf GitHub.

G2: fetch lädt nur die neuen Commits herunter und aktualisiert origin/main, ohne den eigenen Branch zu ändern. pull = fetch + Merge in den aktuellen Branch.

G3: -u setzt den Upstream: lokaler Branch wird dauerhaft mit dem Remote-Branch verknüpft, danach reichen git push / git pull ohne Argumente.

G4: Der Merge des Pull Requests passierte auf GitHub. Lokal kam er erst mit git pull ins main.

