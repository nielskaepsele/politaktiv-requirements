##### AcceptanceTest  
| Schrittnr. | Aktion | Erwartetes Ergebnis | Ergebnis |
| -- |
| 1 | Als Admin einloggen, zu einer Seite navigieren mit Kartenportlet, Karte anklicken | Karte bleibt sichtbar | ok |
| 2 | Prüfen: Sind die Buttons "Hilfe, Marker, Overlay" vorhanden? | Die Buttons "Hilfe, Marker, Overlay" sind sichtbar | ok |
| 3 | Button "Overlay" anklicken | Eine Gruppe weiterer Menüteile erscheint: "Bild/Zeichnung hochladen, Bild/Zeichnung auswählen, Overlay ausrichten, Overlay fixieren, Overlay entfernen, zurück" | ok |
| 4 | Solange kein Overlay ausgewählt ist, ... | sollten die Menüteile "fixieren, löschen" ausgegraut sein | ok |
| 5 | Button "Durchsuchen" anklicken. | der lokale Explorer geht auf, in dem man eine Datei auswählen kann | ok |
| 6 | Datei auswählen | Die gewählte Datei wird hinter dem Button "Durchsuchen" angezeigt. | ok |
| 7 | Button "Hochladen" anklicken | Die Datei wird hochgeladen. | ok. Gleichzeitig geht das Overlay-Bedienmenü zu. Das ist hässlich, aber nicht tödlich. |
| 8 | Neu öffnen durch Klick auf "Overlay" | Die Gruppe weiterer Menüteile erscheint wieder. | ok |
| 9 | Im Dropdown-Menü von "Bild/Zeichnung auswählen" die hochgeladene Datei auswählen. | Die Datei erscheint im Drop-Downfeld und wird auf der Karte plaziert. Gleichzeitig wird der Button "Overlay fixieren" aktiviert. | ok |
| 10 | Alle Buttons von "Overlay ausrichten" testen: | Das neue Overlay lässt sich mit der Maus anfassen und auf der Karte beliebig verschieben. | ok |
| 10a | Breite | Breite lässt sich in großen und kleinen Schritten vergrößern und verkleinern. | ok |
| 10b | Höhe | Höhe lässt sich in großen und in kleinen Schritten vergrößern und verkleinern. | ok |
| 10c | Winkel | Winkel lässt sich in großen und in kleinen Schritten nach rechts und nach links um die linke obere Ecke drehen. | ok. Aber: dreht sich nicht um die linke obere Ecke, sondern um einen Punkt, der ca 200 m (absolute Werte!) an der linken Kante unterhalb der oberen linken Ecke sitzt. Das ist sehr hässlich, muss zunächst aber geduldet werden, da es sich umgehen lässt. |
| 10d | Transparenz | Die Transparenz lässt sich verbessern und verschlechtern | ok |
| 11 | Button anklicken "Overlay fixieren" | Ein Menü geht auf zur Eingabe von Text und anderen Daten fürs Overlay | Fehlermeldung: "Failed to retrieve content" |
| 12 | Es lässt sich nicht weiter testen | | |
| 13 | Button "zurück" anklicken | Karte geht in Grundzustand über | ok |
