## Anforderungen Version3

### Allgemeine Anforderung
Als Gesamtsystem und Community der verwendeten Teile wurde Leaflet und die zugehörige Familie von möglichen Add-Ins ausgewählt. Im Besonderen bedeutet es auch, dass nur Add-Ins verwendet werden dürfen, die zu dieser Familie gehören. Die Aufgabe der Polit@ktiv-Entwicklung ist also, die entsprechenden Leaflet-Teile und ausgewählte Add-Ins so in Liferay einzubauen, dass die Anforderungen des Kartenportlets V2 erfüllt werden. Dabei soll ein Polit@ktiv-Portlet entstehen, das immer als Ganzes genutzt wird. Es wird keine in Liferay auswählbaren Komponenten geben.

Alles ist mit Code, der einem Built unterliegt, nicht in einem Hook realisiert.

### Basis
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0070.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0071.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0116.md" %}
Festlegung des Standar

### Kartensetup
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0107.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0104.md" %}

### Berechtigungseinstellung
Installation und Anzeige des Karten-Portlets durch einen Liferay-Nutzer unterliegt der üblichen Berechtigung für die Nutzung von Portlets.
Es gibt die Berechtigung, das Portlet als Ganzes zu manipulieren (anzeigen, hinzufügen, konfigurieren, …) wie üblich in Liferay. Diese Berechtigungen sind bei den Funktionen abgelegt.

{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0112.md" %}

Die Berechtigungen lassen sich bei der einzelnen Instanz des Portlets einstellen, nicht für alle Kartenportlets einer Site gemeinsam.

{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0075.md" %} 


Mit der Berechtigung „Anzeige“ (=Portlet anzeigen) ist verbunden: Zoom verändern und Karte verschieben
Mit der Berechtigung „Hinzufügen“ (Portlet hinzufügen) ist verbunden: Hinzufügen, korfigurieren

Es gibt die Berechtigung, die Objekte im Portlet „anzuzeigen“ (Anzeige). Dazu gehören:

    die Beschriftung ein/auszuschalten
    Marker und Figuren ein-/auszublenden
    Layer einzublenden / auszublenden. Diese Einstellungen werden nicht persistiert und auf alle Objekte gleichzeitig angewandt.

Es gibt die Berechtigung, Objekte zu erzeugen („hinzufügen“) und zu beschriften. Darunter:

    Polygone
    Marker
    Bookmarks
    Layer
Objekte hochladen und auf Karte auf eigenem Layer darstellen. 
Diese Einstellungen werden persistiert und auf alle Objekte gleich angewandt.

Wer das Recht hat, Objekte zu erzeugen, darf eigene Objekte auch bearbeiten. Bei den Objekten muss also der Autor gespeichert werden.
Es gibt die Berechtigung, die Grundeinstellung vorzunehmen. Dazu gehört:

    Zentrum und Basis-Zoom
    Maximale Anzahl Layer
    Maximale Anzahl Marker
    Maximale Anzahl Figuren
    Export und Import von Objekten einer Instanz des Kartenportlets.


{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0075/ac001.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0076.md" %} 

Wer das Recht hat, die Grundeinstellungen vorzunehmen, darf auch fremde (alle) Objekte
bearbeiten.

### Marker
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0077.md" %}
Also: Ein zweites Portlet auf einer anderen Page der Site zeigt nicht dieselben Marker wie das erste Portlet.

{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0100.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0073.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0122.md" %}

### Linien
Gleich wie Marker

### Polygonzüge
Gleich wie Marker

### Flächen
Gleich wie Marker

### Kreise 
Gleich wie Marker

### Bookmarks & Figuren
URL der Seite mit dem Kartenportlet plus geografische Bookmarks
Dazu wird das Plug-In Bookmark verwendet wie im Beispiel am 10.7.15

Zur komfortablen Beschriftung wird ein PlugIn verwendet, das am 10.7. in seiner ausführlichen Form vorgestellt wurde. Insbesondere ist wichtig, dass von einem Objekt aus ein URL und ein Bookmark auf eine Page der Site mit Portlet gelegt werden kann.
Und umgekehrt ist es möglich, dass von einem Content aus ein URL und eine geografische Bookmark auf ein Objekt im Kartenportlet gelegt werden kann.

Figuren können eingezeichnet und komfortabel beschriftet (einschl. URL) und geändert werden. Dazu wird das Plug-In verwendet, das es am 10.7.15 auf intermediate gab.

Eine persistente Grundeinstellung kann vorgenommen werden, einschließlich:

    maximale Anzahl von Markern pro Portlet
    maximale Anzahl von Figuren pro Portlet
    Übernahme der aktuellen Zoom- und Zentrumseinstellung in die persistente.

###Layer
Es ist möglich, Layer zu erzeugen und zu beschriften
Festlegung maximale Anzahl Layer pro Portlet
Die erzeugten Objekte können definierten Layern zugewiesen werden.

###Export und Import
Ein Export und ein Import von Figuren mit ihren Beschriftungen und geografischen Bookmarks ist möglich.
Import von Grafiken ist möglich, um z.B. Pläne von Architekten darstellen zu können. Dazu gehört:

    Hochladen
    Einspielen
    Vergrößern, verkleinern in groben und feinen Stufen
    Höhen- und Breiten-Einstellungen
    Drehen in groben und feinen Stufen
    Beschriften der Grafik wie bei anderen Figuren auch. g. NICHT aber: Strichdicke mit dem Zoom ändern

###Weitere Anforderungen
* Indoor-Funktion ist möglich. Dazu gehört insbesondere Zoomen deutlich tiefer als die tiefste Stufe auf der Karte.
* Beim Mouseover über eine Figur oder einen Marker oder eine importierte Grafik erscheint ein kurzer Text, der nicht identisch ist mit der ausführlichen Beschriftung.
* Noch offen: Im Block für die ausführliche Beschriftung ist ein Content enthalten, der ein „normaler“ Content von Liferay ist. Er kann ausgewählt werden. Während der ausführlichen Beschriftung entsteht ein normaler Content von Liferay. Dazu steht der übliche embedded Editor von Liferay zur Verfügung.
* 3D-Darstellung
* Übergang zu Google-Earth mit Walkthrough


## Quelle
[Fachliche Anforderungen](domainrequirements.md)