# Anforderungen Version4

## Context
Als Gesamtsystem und Community der verwendeten Teile wurde Leaflet und die zugehörige Familie von möglichen Add-Ins ausgewählt. Im Besonderen bedeutet es auch, dass nur Add-Ins verwendet werden dürfen, die zu dieser Familie gehören. Die Aufgabe der Polit@ktiv-Entwicklung ist also, die entsprechenden Leaflet-Teile und ausgewählte Add-Ins so in Liferay einzubauen, dass die Anforderungen des Kartenportlets V2 erfüllt werden. Dabei soll ein Polit@ktiv-Portlet entstehen, das immer als Ganzes genutzt wird. Es wird keine in Liferay auswählbaren Komponenten geben.


## Basis
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0070.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0071.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0116.md" %}

## Kartensetup
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0107.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0104.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0078.md" %}
  
  * Maximale Anzahl Layer
  * Maximale Anzahl Figuren
* Export und Import von Objekten einem Layer.
 
Anm. mje: 
1. Festlegen der maximalen Anzahl von Figuren fehlt noch
2. Macht eine Aufteilung in einzelne F.Typen Sinn?
 
Grobschätzung der offenen Punkte (jem): 5PT

## Berechtigungseinstellung
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0112.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0075.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0075/ac001.md" %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0076.md" %} 

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

Grobschätzung der offenen Punkte (jem): Risiko - 5PT


## Figuren
Marker, Linien, Polygonzüge, Flächen, Kreise sind Figuren.

* Der Benutzer kann Beschriftung zu Figuren ein und ausblenden.

Anm jem: was ist damit gemeint? 

* Figuren löschen
* Zoomstufe bei der Figur mit abspeichern, nicht nur den Ort
* Linienfarbe einstellbar machen in Konfiguration. Gilt jeweils für alle neuen Figuren. Dazu muss die Linienfarbe auch bei der Figur mit abgespeichert werden.

Grobschätzung der offenen Punkte (jem): Zoomstufe, Linienfarbe, Löschen & Bugfixing - 5PT

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

## Referenzierung von Figuren und Content (Bookmarks & Figuren)
* Jede Figur ist durch eine URL eindeutig referenzierbar.
  * URL-Bestandteile sind: Seite - Portlet-Instanz-ID - Figur-ID
  * Security: URL-Parameter werden validiert.
* URLs einer Figur können in einem einblendbaren (Rand-)bereich geladen und angezeigt werden
  * Security: Das System lädt nur URLs von einem Server aus einer konfigurierten Whitelist nach.

Grobschätzung der offenen Punkte (jem): 10PT

##Layer
* Es ist möglich, Layer zu erzeugen und zu beschriften
* Die erzeugten Objekte können definierten Layern zugewiesen werden.

Anm. mje: Figuren werden dem zum Erstellzeitpunkt aktuellen Layer zugewiesen.

* Ein Benutzer kann Layer ein- und aus-blenden. 
* Ein Export und ein Import von Figuren mit ihren Beschriftungen und geografischen Bookmarks ist für einen Layer möglich.

Grobschätzung der offenen Punkte (jem): 5-10PT

##Verarbeitung von Grafiken
Grafiken sind z.b. Pläne von Architekten und sollen verwendet werden können.

* Der Benutzer kann eine Grafik in den aktuellen Layer hochladen
* Der Benutzer kann eine Grafik Vergrößern, verkleinern in groben und feinen Stufen
* Der Benutzer kann f. eine Grafik Höhen und Breiten einstellen
* Der Benutzer kann eine Grafik drehen in groben und feinen Stufen
* Der Benutzer kann Grafiken beschriften wie bei anderen Figuren auch. 
* g. NICHT aber: Strichdicke mit dem Zoom ändern

Anm mje: Strickdichte funktioniert nicht.

Grobschätzung der offenen Punkte (jem): 10-20PT

###Weitere Anforderungen
* Indoor-Funktion ist möglich. Dazu gehört insbesondere Zoomen deutlich tiefer als die tiefste Stufe auf der Karte.
* Beim Mouseover über eine Figur oder einen Marker oder eine importierte Grafik erscheint ein kurzer Text, der nicht identisch ist mit der ausführlichen Beschriftung.

Anm mje: Was ist das für ein Text?

* 3D-Darstellung

Anm mje: muss noch spez. werden

* Übergang zu Google-Earth mit Walkthrough

Anm mje: muss noch spez. werden


## Quelle
[Fachliche Anforderungen](domainrequirements.md)