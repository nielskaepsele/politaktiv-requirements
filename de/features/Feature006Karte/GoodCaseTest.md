#Simple Good-Case-Test

## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0070.md" %}
## Test:
### Durchführung
Besuche eine Seite mit der Karte
### Erwartetes Verhalten
Karte mit Markern und Overlays wird angezeigt


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0071.md" %}
## Test:
### Durchführung
Klicken auf den Plus bzw. Minus Button; Rollen mit dem Mausrad
### Erwartetes Verhalten
1. Das Zoomen funktioniert
2. Die Grafiken zoomen mit der selben Skalierung mit


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0116.md" %}
## Test:
### Durchführung
* Auf einer Seite zwei Map2-Portlets einfügen
* Unterschiedliche Änderungen in den jeweiligen Portlets durchführen und speichern
### Erwartetes Verhalten
* zwei Map2-Portlets lassen sich hinzufügen
* nach dem Neuladen der Seite wurden die Änderungen an der Karten getrennt voneinander gespeichert und werden wieder angezeigt


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0107.md" %}
## Test:
### Durchführung
* Zwei Portlets anlegen
* In beiden Portlets die Konfiguration verändern: Längen- und Breitengrade festlegen, Zoom-Level festlegen
  * Konfiguration 1: Längengrad: 20.00000, Breitengrad 40.00000; Zoom-Stufe 5
  * Konfiguration 2: Längengrad: 40.00000, Breitengrad 140.00000; Zoom-Stufe 3
### Erwartetes Verhalten
* die Einstellungen wirken in beiden Portlets unabhängig voneinander, d.h.
  * beim Neuladen der Seite wird die Karte an der definierten Stelle (Kartenzentrum) angezeigt
  * beim Neuladen der Seite entspricht die Zoomstufe der definierten Zoomstufe
* Konkret
  * Konfiguration 1 zeigt das Rote Meer
  * Konfiguration 2 zeigt Süd-Ost Asien


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0112.md" %}
## Test:
### Durchführung
* Mit Nutzer ohne Adminrechte Anmelden und einen Marker platzieren und speichern
* Seite neu laden
* Marker bearbeiten und speichern
* Mit Nutzer mit Adminrechten in der Konfiguration verbieten, dass Nutzer ihre Marker ändern können
* Mit Nutzer ohne Adminrechten versuchen, seine Marker zu bearbeiten
### Erwartetes Verhalten
* Das Speichern und anschließende Verändern der Marker ohne Eingriff auf die Berechtigungen durch den Admin funktioniert einwandfrei. Änderungen werden gespeichert, die Möglichkeit zur Bearbeitung ist gegeben
* Nach dem Eingriff des Admins ist dies nicht mehr möglich


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0100.md" %}
## Test:
### Durchführung
* Auf Marker-Symbol klicken
* Marker platzieren
* Eigenschaften im Pop-Up definieren
* Speichern
### Erwartetes Verhalten
Marker wird mit seinen Informationen angezeigt


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0073.md" %}
## Test:
### Durchführung
* Karte ansurfen als Gast (nicht angemeldet)
* auf fremden Marker klicken
* Karte ansurfen als Nutzer 
* auf fremden Marker klicken
### Erwartetes Verhalten
* Gast bekommt Marker-Informationen angezeigt
* Nutzer bekommt Marker-Informationen über fremde Marker angezeigt


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0122.md" %}
## Test:
### Durchführung
* Karte ansurfen als Nutzer
* auf eigenen Marker klicken
### Erwartetes Verhalten
* Nutzer bekommt Marker-Informationen über eigenen Marker sowie die Möglichkeit, den Marker zu bearbeiten angezeigt (Voraussetzung: Bearbeitung der eigenen Marker ist durch Admin aktiviert)


## Requirement:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0111.md" %}
## Test:
### Durchführung
* Auf Zeichen-Button klicken
* Element zeichnen
* Speichern
* Zoomlevel ändern
* weiteres Element zeichnen
* Speichern
* Neuladen der Seite
### Erwartetes Verhalten
* Die Elemente werden angezeigt, konform des Zoom-Levels, auf welchem sie gezeichnet wurden

