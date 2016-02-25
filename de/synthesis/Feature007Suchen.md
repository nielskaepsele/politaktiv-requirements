# Ziel
Es soll eine neue Version des Assetpublisher entwickelt werden, die gestattet, dass ein nicht 
eingeloggter Benutzer suchen und sortieren kann, ohne dass er die Berechtigung habenmuss, den 
Assetpublisher zu konfigurieren.

# Umfeld
## Lösungsansatz: PA-Assetpublisher
Der Assetpublisher wird herausgelöst und es wird daraus eine zusätzliche Variante des Assetpublisher 
entwickelt, die zusätzlich zu dem bereits im Standardf-Liferay Funktionsumfang bestehenden (im Folgenden 
Standard-Assetpublisher genannt) eingesetzt werden kann.
Der neue wird im Folgenden als PA-Assetpublisher (PA-AP) bezeichnet.
In den PA-AP werden im Kopf ausklappbare Bereiche eingebaut, die es einem nicht angemeldeten Benutzer 
erlauben, das Suchen, Filtern, Sortieren und Präsentieren einzustellen. Sie sind per default nicht 
ausgeklappt und bestehen dann aus je einer grau hinterlegten Zeile, in der die Bezeichnung steht und 
ein Pfeil nach unten. Wenn man auf den Pfeil klickt, klappt der Bereich aus und der Pfeil ändert sich 
in einen Pfeil nach oben. Klickt man wiederholt darauf, klappt der Bereich wieder zu.

Es gibt (langfristig) folgende Bereiche:
1. Suche
2. Filter
3. Sortierung
4. Darstellung

In einer ersten Entwicklungsstufe sollen nur der Filter und die Sortierung entwickelt werden.
Suche und Darstellung können dann später hinzugefügt werden.

## Benutzung des neuen PA-Assetpublisher
### Bisherige Benutzung des Standard-Assetpublisher:
#### Einrichten
1. Portlet des Standard-Assetpublishers auf einer Seite (page) platzieren.
2. Konfigurationsmenü aufrufen
3. Auswahl konfigurieren, welche Contents dargestellt werden sollen
4. Sortierung konfigurieren, in welcher Reihenfolge die Contents dargestellt werden sollen. Beispiel: nach Datum sortiert oder nach Autor sortiert, oder …
5. Präsentation konfigurieren, wie die Contents dargestellt werden sollen.
Beispiel: als Liste oder mit Autorennamen oder …
6. Abspeichern. Fertig!

#### Benutzung:
1. Der Benutzer ruft die Seite (page) auf und sieht die ausgewählten Contents in der Reihenfolge und Präsentation wie konfiguriert.
2. Kommt im Laufe der Zeit ein weiterer Content dazu, der zur Auswahl passt, wird dieser ebenfalls angezeigt in der korrekten Reihenfolge und Darstellung. Wird ein Content gelöscht, fehlt dieser künftig. Das bedeutet: Der Standard-Assetpublisher erstellt alles zur Laufzeit und er macht alles für alle Benutzer gleich.

### Künftige Benutzung des neuen PA-Assetpublisher:
Zunächst wird nur die Funktionalität nach der ersten Entwicklungsstufe beschrieben.

#### Einrichten (erste Entwicklungsstufe)
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0130.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0131.md" %}


#### Benutzung:
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0132.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0133.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0134.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0135.md" %}

# Anforderungen
Nicht alle künftigen Eigenschaften sollen von Anfang an zur Verfügung stehen.
Die Entwicklung soll vielmehr stufenweise erfolgen.
Die Entwicklung der Stufen kann sich eventuell über mehrere Jahre hin erstrecken.
Zunächst werden nur die dringendsten Eigenschaften benötigt.
Zunächst sollen mit den ersten beiden Stufen Erfahrungen gesammelt werden.

## Erste Stufe 
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0136.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0137.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0138.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0139.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0140.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0141.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0142.md" %}

2. Jeder Gast kann mit dem PolitAktiv Asset Publisher (PA-AP) die vom Administrator vorgegebene Ergebnismenge filtern und sortieren. 
  1. Filter: Der Benutzer kann (nur) nach Kategorien (nicht Autor, nicht Datum, nicht Tags, etc…) filtern.
  2. Sortierung: Der Benutzer kann entweder nach Kategorien oder nach Autor oder nach Datum filtern. Die Sortierung ist einstufig.
3. Das System zeigt für die Sortier- und Filter-Funktion jeweils aufklappbare Bereiche an.
4. Der Admin muss (wie bisher auch) 
  1. die Präsentation fest vorgeben.
  2. die default Sortierung vorgeben.
5. Das System zeigt die wirksamen Filter- und Sortierkriterien an. Initial also auch die Default Sortierung.
6. In Stufe 1 kann der Benutzer keine Präsentation verändern.
7. In Stufe 1 kann der Benutzer keine facettierte Suche durchführen.

## Zweite Stufe
1. Erweiterung des Filters
2. Erweiterung der Sortierung
3. Noch Keine Auswahl einer bestimmten Präsentation
4. Keine facettierte Suche

## Spätere Stufen
1. Im Folgenden werden alle aus heutiger Sicht wünschenswerte Funktionen dargestellt

### Bereich Suche
1. Es soll eine facettierte Suche geben, die auch eine Volltextsuche enthält. Details sollen später festgelegt werden. Sie ist dem Filter vorgeschaltet und ergänzt die vom Admin festgelegte Suche.

### Bereich Filter
1. Es ist möglich nach mehreren kombinierten Filtern zu filtern,
nicht nur nach einen einzigen Filter.
2. Filtern nach Kategorien und Unterkategorien.
3. Filtern nach Autor, nach Datum, nach Bewertung, etc.. (Standardfelder von Content)
4. Filtern nach Tags
5. Filtern nach Feldern von Strukturen in den Contents.

### Bereich Sortierung
1. Es ist möglich nach mehreren (max 3) Einstellungen abgestuft zu sortieren,
ähnlich wie in Excel eine Sortierung nach mehreren Spalten möglich ist.
2. Sortierung nach Kategorien und Unterkategorien (dropdown-Menü)
3. Sortierung nach Autor, Datum, Bewertungen, etc… (Standardfelder von Contents)
4. Sortierung nach Tags
5. Sortierung nach Feldern von Strukturen in den Contents

### Bereich Darstellung
1. Es ist möglich, mittels dropdown-Menü eine Darstellung der Contents auszuwählen, aus verschiedenen Darstellungen, die der Admin dazu vorgegeben hat.
2. Der Admin gibt eine davon als Default vor.
3. Auswahl diverser Templates
4. Auswahl diverser Standard-Darstellungen des Assetpublishers,
die der Admin dazu mit passenden Namen bezeichnet hat.
5. Nach Auswahl einer Darstellung durch den Benutzer zeigt der PA-AP die Contents in der ausgewählten Darstellung (Beispiel: Kärtchen, Liste, mit oder ohne Bookmarks).

### Bereich Benutzerprofil
1. In einer späteren Ausbaustufe kann ein angemeldeter Benutzer eine von ihm gewünschte Einstellung in seinem Benutzerprofil abspeichern. Meldet er sich wieder an und besucht dieselbe Seite, werden ihm die Contents im PA-AP in der abgespeicherten Darstellung (Auswahl, Sortierung, Darstellung) angezeigt. Damit ein Benutzer auf jeder Site (DK) und auf jeder Seite (page) ein solches Profil anlegen kann, muss es mit entsprechenden Attributen in seinem Profil abgespeichert werden.