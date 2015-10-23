# Anforderungen Version4

## Context
Als Gesamtsystem und Community der verwendeten Teile wurde Leaflet und die zugehörige Familie von möglichen Add-Ins ausgewählt. Im Besonderen bedeutet es auch, dass nur Add-Ins verwendet werden dürfen, die zu dieser Familie gehören. Die Aufgabe der Polit@ktiv-Entwicklung ist also, die entsprechenden Leaflet-Teile und ausgewählte Add-Ins so in Liferay einzubauen, dass die Anforderungen des Kartenportlets V2 erfüllt werden. Dabei soll ein Polit@ktiv-Portlet entstehen, das immer als Ganzes genutzt wird. Es wird keine in Liferay auswählbaren Komponenten geben.


## Basis
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0070.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0071.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0116.md" %}
* Festlegung des Standardmittelpunktes
  * Als Standardmittelpunkt fungiert Tübingen

## Kartensetup
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0107.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0104.md" %}
  * Der Moderator kann das aktuelle Kartenzentrum per Knopfdruck übernehmen.
  * Maximale Anzahl Layer
  * Maximale Anzahl Figuren
* Export und Import von Objekten einer Instanz des Kartenportlets.
 
Anm. mje: 
1. Festlegen der maximalen Anzahl von Figuren fehlt noch
2. Macht eine Aufteilung in einzelne F.Typen Sinn?

## Berechtigungseinstellung
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0112.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0075.md" %}

Arbeitsnotizen mje: 
1. Resources durch Figuren ersetzen.
2. Berechtigung als Resource-basiert beschreiben
3. Resource-basiert und funktionale Berechtigung beschreiben.


* Portlet Anzeigen: Mit der Berechtigung ist verbunden: 
  * Diese Berechtigung ist funktional.
  * Zoom verändern und 
  * Karte verschieben

Anm. mje: Umgesetzt

* Portlet Hinzufügen: Mit der Berechtigung „Hinzufügen“ ist verbunden: 
  * Diese Berechtigung ist funktional.
  * Hinzufügen und 
  * konfigurieren
   
Anm. mje: Umgesetzt

* Figuren anzeigen: Es gibt die Berechtigung, die Figuren im Portlet „anzuzeigen“. Dazu gehören:
  * Diese Berechtigung ist funktional.
  * die Beschriftung ein/auszuschalten
  * Marker und Figuren ein-/auszublenden
  * Layer einzublenden / auszublenden. 
  * Diese Einstellungen werden nicht persistiert und auf alle Objekte gleichzeitig angewandt.

Anm. mje: 
1. Hier werden implizit Funktionen beschrieben - wir sollten diese Funktionen noch mals explizit aufführen.
2. Figuren ein und ausblenden macht im Kontext Layer keinen Sinn.
3. Figur anzeigen fällt mit Portlet Anzeigen zusammen?

{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0075/ac001.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0076.md" %} 


## Figuren
Marker, Linien, Polygonzüge, Flächen, Kreise sind Figuren.
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

## Bookmarks & Figuren
URL der Seite mit dem Kartenportlet plus geografische Bookmarks
Dazu wird das Plug-In Bookmark verwendet wie im Beispiel am 10.7.15

Zur komfortablen Beschriftung wird ein PlugIn verwendet, das am 10.7. in seiner ausführlichen Form vorgestellt wurde. Insbesondere ist wichtig, dass von einem Objekt aus ein URL und ein Bookmark auf eine Page der Site mit Portlet gelegt werden kann.
Und umgekehrt ist es möglich, dass von einem Content aus ein URL und eine geografische Bookmark auf ein Objekt im Kartenportlet gelegt werden kann.

Figuren können eingezeichnet und komfortabel beschriftet (einschl. URL) und geändert werden. Dazu wird das Plug-In verwendet, das es am 10.7.15 auf intermediate gab.

Eine persistente Grundeinstellung kann vorgenommen werden, einschließlich:

    maximale Anzahl von Markern pro Portlet
    maximale Anzahl von Figuren pro Portlet
    Übernahme der aktuellen Zoom- und Zentrumseinstellung in die persistente.

##Layer
Es ist möglich, Layer zu erzeugen und zu beschriften
Festlegung maximale Anzahl Layer pro Portlet
Die erzeugten Objekte können definierten Layern zugewiesen werden.

* Figuren anzeigen: Es gibt die Berechtigung, die Figuren im Portlet „anzuzeigen“. Dazu gehören:
  * die Beschriftung ein/auszuschalten
  * Marker und Figuren ein-/auszublenden
  * Layer einzublenden / auszublenden. 
  * Diese Einstellungen werden nicht persistiert und auf alle Objekte gleichzeitig angewandt.

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