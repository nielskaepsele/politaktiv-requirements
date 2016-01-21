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
1. Portlet des PA-AP auf einer Seite (page) platzieren.
2. Konfigurationsmenü des PA-AP-Präsentations-Portlets aufrufen.
3. Grobe Auswahl konfigurieren, welche Contents dargestellt werden können.
Ähnlich wie bisher mit dem Standard-Assetpublisher.
Beispiel: Nur Beiträge oder nur Extrakte oder nur ….
Dies soll anhand einer oder mehrerer Kategorien erfolgen.
4. Die Möglichkeiten für den Benutzer-Filter konfigurieren.
5. Die Default-Sortierung konfigurieren!
6. Präsentation konfigurieren, wie die Contents dargestellt werden sollen.
7. Abspeichern und Konfigurationsmenü schließen. Fertig!

#### Benutzung:
1. Der Benutzer ruft die Seite (page) auf und sieht die Contents, wie sie per Default-Einstellung des PA-AP dargestellt werden:
Also kein Filter, Default-Sortierung und Default-Darstellung
2. Wenn der Benutzer auf die grau unterlegte Zeile „Sortierung“ klickt, klappt ein grau unterlegter Bereich nach unten auf und bietet eine Auswahl an Sortiermöglichkeiten an, z.B. nach Datum oder nach Autor oder nach Kategtorie. Es werden die Sortiermöglichkeiten angeboten, die vom Admin im Konfigmenü vorgegeben wurden. Voreingestellt ist die Sortierung, die der Admin im Konfigmenü als Default festgelegt hat.
3. Wenn der Benutzer dann auf den Button „Neu Anzeigen“ klickt, werden die Contents im Portlet in der neuen Sortierreihenfolge angezeigt.
4. Der Benutzer kann dann den grau unterlegten Bereich wieder zuklappen durch Klick auf den Pfeil nach oben.
5. Wenn der Benutzer auf die grau unterlegte Zeile „Filter“ klickt, klappt ein grau unterlegter Bereich nach unten auf und bietet eine Auswahl an Filtermöglichkeiten an, z.B. nach diversen Kategorien. Es werden genau die Filtermöglichkeiten angeboten, die der Admin im Konfigmenü vorgegeben hat. Voreingestellt ist ein leerer Filter (alles wird angezeigt).
6. Wenn der Benutzer dann auf den Button „Neu Anzeigen“ klickt, werden nur noch die Contents im Portlet angezeigt, die der Filter durchlässt.
7. Der Benutzer kann dann den grau unterlegten Bereich wieder zuklappen durch Klick auf den Pfeil nach oben.
8. Selbstverständlich können verschiedene Benutzer gleichzeitig verschiedene Einstellungen benutzen. Verschiedene Benutzer sind unabhängig voneinander.

# Anforderungen
Nicht alle künftigen Eigenschaften sollen von Anfang an zur Verfügung stehen.
Die Entwicklung soll vielmehr stufenweise erfolgen.
Die Entwicklung der Stufen kann sich eventuell über mehrere Jahre hin erstrecken.
Zunächst werden nur die dringendsten Eigenschaften benötigt.
Zunächst sollen mit den ersten beiden Stufen Erfahrungen gesammelt werden.

## Erste Stufe 
1. Es gibt nur zwei Bereiche: Filtern und Sortieren.
Beide sind zunächst sehr einfach ausgeprägt.
2. Filter: nur nach Kategorien (nicht Autor, nicht Datum, nicht Tags, etc…)
3. Sortierung nur nach Kategorien oder nach Autor oder nach Datum.
Aber nur eine einzige Sortierung (keine mehrstufige Sortierung).
4. Keine Auswahl einer bestimmten Präsentation.
Die Präsentation wird vielmehr vom Admin fest vorgegeben.
5. Keine facettierte Suche

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