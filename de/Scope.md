## Scope & Decisions

### Requirements
Die Requirements beschreiben die technischen Funktionen und Eigenschaften der Plattform [Polit@ktiv](https://www.politaktiv.org), die auf Liferay basiert. Es wird daher davon ausgegangen, bzw. es wird dabei unterstellt, dass die Eigenschaften und Funktionen von Liferay in der aktuellen Version auch auf der Plattform [Polit@ktiv](https://www.politaktiv.org) zur Verfügung stehen und den Entwicklern prinzipiell bekannt und geläufig sind. Die Requirements beschreiben also die funktionalen und die nicht funktionalen Eigenschaften sowie die Schnittstellen von [Polit@ktiv](https://www.politaktiv.org).

### Ausschlüsse
Eigentlich gehört hier auch die '''Architektur''' des Gesamtsystems (Hard- und Software) beschreiben. Darauf wird aber vorläufig verzichtet.

Die Requirements beschreiben '''nicht die Philosophie''' von Polit@ktiv.

Die Requirements definieren '''nicht die Methoden''' von [Polit@ktiv](https://www.politaktiv.org) und beschreiben daher auch '''nicht die methodischen Grundlagen''' von [Polit@ktiv](https://www.politaktiv.org).

Aus diesem Grund werden auch '''nicht die Prozesse''' von [Polit@ktiv](https://www.politaktiv.org) in den Requirements festgelegt. Die Prozesse von [Polit@ktiv](https://www.politaktiv.org) werden hier nur insoweit beschrieben, wie sie erforderlich sind, um die Anforderungen besser zu verstehen.

Die Requirements definieren '''nicht die Konfiguration''' und daher auch nicht alle Module von Polit@ktiv. Die Konfiguration wird nur dann beschreiben, wenn sie nur durch Customizing bei der Installation erreicht werden kann. Konfigurationseinstellungen, die durch normale Admin-Tätigkeit auf der Oberfläche erreicht werden kann, wird nicht beschrieben.

Die Requirements definieren und beschreiben also '''nur diejenigen Portlets''', die für Polit@ktiv entwickelt oder deren Software angepasst wurden.

Die Requirements beschreiben allerdings '''die Schnittstellen''' von Polit@ktiv zu anderen Softwaresystemen, sofern sie neu entwickelt oder abgeändert wurden.

Die Requirements beschreiben daher auch '''nicht das Design''' von [Polit@ktiv](https://www.politaktiv.org) oder legen es gar fest. Vom Design ausgehend werden allerdings Anforderungen an die Navigation in [Polit@ktiv](https://www.politaktiv.org) gestellt.

In den Requirements werden allerdings zum besseren Verständnis die '''Rechte der verschiedenen Rollen''' beschrieben und festgelegt.

### Namenszug
der gültige Namenszug lautet: '''Polit@ktiv'''

### Logo
 * mit dem Logo darf nicht gespielt werden, daher enthalten die Homepage und die Landingpages keine stilisierten Schattenrisse, sondern Kacheln.
 * Das Logo hat immer einen Schutzraum um sich, der in Höhe oder breite der Buchstabenhöhe des darin enthaltenen "@"-Zeichens entspricht.

### Liferay-Version
 * Alle Spezifikationen und Abnahmentests sind für die Liferay-Version 6.2.1 oder höher beschrieben.
 * Sind sie ausnahmsweise für andere Versionen gemeint, steht dies explizit im Kopf der Spezifikation

### Entwicklung mit Open-Source
Im Gegensatz zur Version 1 des Polit@ktiv-Kartenportlets, das eigens programmiert wurde, sollen alle Entwicklungen künftig möglichst weitgehend aus Open-Source-Teilen aufgebaut werden. Dies ist das zugrunde liegende Prinzip, von dem nur in Ausnahmen abgewichen werden darf, weil es einer Stiftung angemessen ist, die von Spendengeldern finanziert wird. Selbstverständlich werden die entwickelten Teile der Open-Source-Community angeboten.

Die Vorteile sind:
1. Die Community entwickelt weiter, nicht die Entwicklung von Polit@ktiv
2. Mögliche Fehler werden von anderen beseitigt.
3. Bewährte Bausteine werden integriert.

Die Nachteile sind:
1. Es stehen nur solche Features zur Verfügung, die eben schon vorhanden sind.
Eventuell muss lange auf neue Features gewartet werden.
2. Die Entwicklungsarbeiten von Polit@ktiv müssen der Open-Source-Community wieder zur Verfügung gestellt werden. Damit sind sie auch für die Konkurrenz der HIT verfügbar.