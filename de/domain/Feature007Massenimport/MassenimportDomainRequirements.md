# Ziel
Für große Bürgerbeteiligungsverfahren wird ein Massenimport von Webcontent benötigt, zum Beispiel für folgende Anwendungsfälle:
1.	Beiträge von Bürgern liegen beim Start eines DK bereits massenweise vor und sind rasch einzupflegen.
2.	Beiträge von Bürgern gehen per Formular ein, sei es per Webform-Portlet, sei es durch andere Fragebögen.
3.	Die in einer Präsenzveranstaltung gesammelten Beiträge sind einzupflegen.
4.	Bei der Extraktion von Aussagen aus den Beiträgen können an einem einzigen Tag hunderte von Extrakten außerhalb von Liferay entstehen, die ebenfalls als Webcontent abgelegt werden sollen. (Beispiel: KI-Tool)

Ein misslungener Massenimport muss reparierbar sein!
Daraus folgen mindestens vier weitere Anforderungen:
1.	Zur Reparatur eines misslungenen Massenimports muss es ein Massenupdate geben, mit dem bestimmte Attribute von Contents auf einen Schlag geändert werden können.
2.	Damit dieses zur Reparatur eines Massenimports verwendet werden kann, muss beim Massenimport eine Ergebnisliste erzeugt werden, die die ID und Version des jeweils erstellten Contents enthält.
3.	Es muss ein Massenlöschen geben, das auf der Ergebnisliste mit ID’s eines Massenimports beruht.
4.	Ergänzend muss es einen Massenexport geben, der entweder auf der manuellen Auswahl in einem Assetpublisher oder auf der Ergebnisliste eines Massenimports beruht.

#	Abläufe und Übersicht
##	Manuelle Eingabe heute
Die traditionelle Form der Eingabe ist, per Webcontent-Editor in einem Portlet oder im Asset-Publisher den Content manuell einzugeben. Dabei wird der Content normalerweise in eine Structure eingegeben, die vom DK-Owner vorgegeben wurde. Zusätzlich zur Eingabe wird ein Template verwendet, mit dem die Inhalte dann dargestellt werden sollen.
Bei der Eingabe werden neben dem eigentlichen Content sowohl Felder der Structure ausgefüllt, als auch Kategorien zugeordnet und Tags angelegt.
Außerdem werden im Hintergrund weitere Metadatenfelder angelegt, z.B. Autor, Eingabedatum, etc..
Die Darstellung des fertigen Ergebnisses erfolgt dann meist im Asset-Publisher.
##	Künftig per Massenimport
Zum Massenimport wird zunächst manuell eine Tabelle vorbereitet, die alle erforderlichen Daten in geeigneter Form enthält. Jede Zeile darin soll beim Massenimport dann einen eigenen Webcontent ergeben.
Die Tabelle muss dazu alle erforderlichen Daten, Metadaten und Annotationen enthalten, die zur Erzeugung eines Webcontents benötigt werden.
Bei jedem Import soll in einem ersten Schritt ein Prüfdurchlauf erfolgen, der sicherstellt, dass im nachfolgenden zweiten Schritt alles fehlerfrei ablaufen kann. Wird im Prüflauf festgestellt, dass keine fehlerfreie Bearbeitung möglich ist, wird der Import als Ganzes verweigert. Transaktionssicherheit soll also auf Tabellenebene und nicht auf Zeilenebene hergestellt werden. Außerdem sollen aussagekräftige Fehlermeldungen in die Protokollliste eingetragen werden.
##	Ablauf Massenimport
Das Import-Portlet muss und darf in demjenigen DK genau einmal installiert sein, für den die Webcontents angelegt werden sollen.
Zunächst wird auf dem lokalen System des Benutzers die Tabelle zur Verfügung gestellt. Ob sie als File vorher manuell oder vom Import-Portlet selbst hochgeladen wird, ist nicht vorgegeben und offen.
Beim Aufruf des Portlets werden eventuell benötigte Felder ausgefüllt (noch offen), darunter der Filename der zu importierenden Tabelle.
Dazu gehört auch der Name der zu verwendenden Structure und eines zugehörigen Templates.
Dann wird der Prüflauf gestartet. Er endet mit einem modalen Dialog, der entweder besagt, alles prima. Auf den Weitermachen-Klick des Benutzers hin, werden die Daten dann importiert. Erscheint im modalen Dialog aber ein Fehlerhinweis, kann dieser vom Benutzer zur Kenntnis genommen werden, bevor er den modalen Dialog beendet. Es findet dann kein Import statt. Die Details der Fehler stehen dann in der Protokollliste.
Der Prüflauf legt eine Datei mit den gefundenen Fehlern an, die ähnlich aufgebaut ist, wie die Protokollliste.
Wird kein Fehler gefunden und alles importiert, wird die Protokollliste (Datei mit Ergebnisliste) angelegt, die mindestens die ID’s der importierten Webcontents und die angelegte Versionsnummer enthält, so dass daraus ein weiterer Importlauf angestoßen werden kann. Siehe unten.
Es könnte sich als sinnvoll erweisen, dass diese Protokolldatei denselben Aufbau hat wie die Importtabelle.
Dazu ist auch zulässig, dass die Spalte ID und Versionsnummer von vornherein angelegt sein muss.
Da dabei ja keine Fehler vorkommen (sonst würde der Import nicht laufen), wird eine Spalte Fehlernummer nicht unbedingt benötigt.
# Datenstruktur der Import-Tabelle
Die Tabelle muss alle erforderlichen Daten enthalten.
Die über die inhaltlich notwendig hinausgehend erforderlichen Felder werden von der Entwicklung festgelegt. Soweit es von der Anwenderseite her beurteilt werden kann, muss sie mindestens folgende Felder enthalten:
##	Daten für den Webcontent
Da die Inhalte zwingend (!) in einem structured Content dargestellt werden sollen, ist es erforderlich, dass die Structure vorher erstellt wurde und vorliegt. Ihr Name muss im Portlet vor Start des Prüflaufes in einem entsprechenden Feld manuell eingegeben werden.
Daraus ergibt sich, dass in den Spaltenüberschriften in der Tabelle die Feldnamen der Felder stehen, wie sie in der zugehörigen Structure in Liferay angegeben werden.
Die Reihenfolge der Spalten in der Tabelle sollte egal sein. Die Spaltenüberschriften sollten identisch sein mit den Feldnamen aus der zu verwendenden Structure.
Kommt eine Spaltenüberschrift (ein Feldname) in der Structure nicht vor (oder ist er vertippt), ist dies ein Fehler, der die Durchführung des ganzen Massenimports verhindert.
Um mit anderen Feldnamen nicht in Konflikt zu kommen, werden alle anderen Spaltenüberschriften mit speziellen Zeichen gekennzeichnet, die in den Feldnamen der Structures nicht vorkommen. So könnten z.B. die Feldnamen für die ID’s, den Autor, die diversen Datumsfelder, die Kategorien und Tags, etc..  mit „:_“ anfangen.
Oder gibt es bessere Vorschläge von Seiten der Entwicklung?
##	Metadaten für den Ablauf
###	ID
Es soll ein ID-Feld geben, das die ID des Contents angibt. Wenn die ID leer ist, wird ein neuer Content angelegt und eine neue ID automatisch erzeugt, die in der Protokolldatei aufgeführt wird.
Wenn die ID ausgefüllt ist, wird der bestehende Content mit dieser ID geändert. Meist wird dann eine neue Version angelegt. Es gilt dazu das übliche Verhalten von Liferay. Sollen aber z.B. nur die Tags geändert werden, wird in Liferay ja keine neue Version angelegt, sondern die bestehenden Tags werden gelöscht und die neuen eingetragen.
Wenn sich beim Prüflauf ergibt, dass die ID nicht vorhanden ist, ist dies ein Fehler, der aufgelistet wird und zum Abbruch führt. Wichtig: die Prüfung wird immer für alle Zeilen der Import-Tabelle vollständig bis zum Ende durchgeführt.
Beim Erstellen von neuem Inhalt wird die ID des neuen Contents in die Protokolldatei geschrieben. Wir bei einem bestehenden Content etwas geändert, wird dessen vorhandene ID in den Ausgabefile geschrieben. Der Ausgabefile soll so strukturiert sein, dass er einfach wieder für einen Import verwendet werden kann.
###	Action-Feld
Es soll ein Action-Feld geben, in dem in der Import-Tabelle per Auswahlfeld angegeben ist, was geschehen soll:
1.	Action = 0 bedeutet: es wird nur die Prüfung vorgenommen, aber kein Import oder sonstige Änderung von Daten.
2.	Action = -1 (minus 1) bedeutet, der Content (mit zugehörigen Daten) soll gelöscht werden.
Wenn es mehrere Versionen eines Content gibt, soll die neueste Version gelöscht werden. Die älteren bleiben bestehen.
3.	Action = 1 bedeutet: es werden Tags angelegt, sonst aber nicht verändert
4.	Action = 2 bedeutet, es werden Kategorien angelegt, sonst aber nichts verändert
5.	Action = 4 bedeutet, es werden Webcontentfelder angelegt. Damit ist immer verbunden, dass eine neue Version erzeugt wird.

Diese Liste ist nicht abschließend und vollständig. Auf jeden Fall können die Felder kombiniert werden, also im obigen Beispiel: 1 + 2 + 4 = 7 als Action bedeutet, es wird alles neu gemacht.
## Kategorien und Tags
Die Kategorien müssen vor Ablauf des Massenimports im DK in Liferay vorhanden sein.
Im Prüflauf ist zu prüfen, ob dies für alle in der Exceltabelle genannten Kategorien der Fall ist. Ist eine Kategorie nicht vorhanden, so bricht der Import schon bei der Prüfung mit einer Fehlermeldung ab.
Für Tags gilt nichts Entsprechendes; in Liferay nicht vorhandene Tags werden beim Import on the fly angelegt.
Die Kategorien werden in der Import-Tabelle in mehreren Spalten angegeben. In jeder Spalte steht eine Kategorie aus einem Kategorienbaum. Dann darf im entsprechenden Feld in der Spalte nur genau eine Kategorie aus dem Kategoriebaum aufgeführt sein. Die Import-Tabelle hat genauso viele Kategorie-Spalten, wie es in dem zugehörigen DK Kategorie-Baume gibt.
Die Tags werden in der Exceltabelle in einer einzigen Spalte aufgeführt. Werden mehrere Tags angegeben, sind diese im Feld durch Semicolon getrennt aufgeführt.
Schwierigkeit: Die individuell zugeordneten Kategorien oder Tags sind an den Content gebunden, nicht an die Version. Was tun, wenn massenweise falsche Kategorien oder Tags hinzugefügt wurden?
Mögliche Lösung: Kategorien und Tags werden beim Massenimport immer vollständig überschrieben. Daher müssen die bereits vorhandenen Kategorien oder Tags vor einem Massenimport in der Tabelle vorhanden sein. Das könnte durch einen entsprechenden Massenexport gelöst werden.
##	Sonstige Metadaten
1.	Autor: Feldname z.B. :_Autor
2.	Datum: Feldname z.B. :_Datum
3.	Titel: wird behandelt wie ein Feld der Structure. Feldname: Titel
4.	Welche sonstigen Daten werden von der Technik benötigt?

Der DK (also die Site) ist festgelegt durch die Instanz des Import-Portlets!!!

# Massenexport und Massenlöschen
Für den Massenexport werden zwei Versionen benötigt:
1.	Export gemäß Auswahl wie in einem Assetpublisher.
2.	Export nach ID des Contents

## Export aus Assetpublisher
Dazu könnte der für die „Suche“ umgebaute Assetpublisher dienen.
Er soll einfach einen zusätzlichen Button enthalten, der bewirkt, dass eine Liste alle ID’s angelegt wird, auf die die Auswahl zutrifft. Damit ist der Fall auf den folgenden zweiten Exportfall zurückgeführt, mit dem der Rest der Aufgabe erledigt werden kann.
Um das Problem mit verschiedenen zugeteilten Structures lösen zu können, soll aber außer der ID eines Contents auch der Name der ihm zugeteilten Structure ausgegeben werden.
Schon auch wegen diesem Problem mit den Structures muss der Export aus dem Assetpublisher in die beiden Einzelschritte zerlegt werden.
## Export nach ID’s und Löschen
Ein Portlet ist zu realisieren, das folgendes kann:
1. Beruhend auf einer Tabelle mit ID’s werden die Inhalte in eine Tabelle exportiert, die einen Aufbau hat, wie er für den Massenimport benötigt wird.
Dabei darf die Tabelle nur solche ID’s enthalten, die dieselbe structure nutzen.
Der Name der structure ist also zum Export anzugeben.
2.	Beruhend auf einer Tabelle mit den ID’s werden die Contents gelöscht.
3.	In beiden Fällen ist ein Protokollfile anzulegen.
4.	In beiden Fällen ist vorher ein Prüflauf durchzuführen, der einen Logfile erzeugt.
Wenn er Fehler ergibt, wird nichts ausgeführt – ähnlich wie beim Massenimport.

Das Portlet erfüllt einen Nebeneffekt:
Wenn man eine Auswahl im Assetpublisher angibt, die genau ein einziges Ergebnis hat, erhält man eine (fast) leere Tabelle, die die Importstruktur für einen Massenimport für die gewählte structure hat.





