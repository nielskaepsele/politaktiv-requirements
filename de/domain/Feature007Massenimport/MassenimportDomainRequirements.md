# Anforderungen aus dem Fachbereich
## Ziel
Für große Bürgerbeteiligungsverfahren wird ein Massenimport von Webcontent benötigt, zum Beispiel für folgende Anwendungsfälle:
1.	Beiträge von Bürgern liegen beim Start eines DK bereits massenweise vor und sind rasch einzupflegen.
2.	Beiträge von Bürgern gehen per Formular ein, sei es per Webform-Portlet, sei es durch andere Fragebögen.
3.	Die in einer Präsenzveranstaltung gesammelten Beiträge sind einzupflegen.
4.	Bei der Extraktion von Aussagen aus den Beiträgen können an einem einzigen Tag hunderte von Extrakten außerhalb von Liferay entstehen, die ebenfalls als Webcontent abgelegt werden sollen. (Beispiel: KI-Tool)

Ein misslungener Massenimport muss reparierbar sein!
Daraus folgen mindestens vier weitere Anforderungen:
1.	1. Zur Reparatur eines misslungenen Massenimports muss es ein Massenupdate geben, mit dem bestimmte Attribute von Contents auf einen Schlag geändert werden können.
2.	Damit dieses zur Reparatur eines Massenimports verwendet werden kann, muss beim Massenimport eine Ergebnisliste erzeugt werden, die die ID und Version des jeweils erstellten Contents enthält.
3.	Es muss ein Massenlöschen geben, das auf der Ergebnisliste mit ID’s eines Massenimports beruht.
4.	Ergänzend muss es einen Massenexport geben, der entweder auf der manuellen Auswahl in einem Assetpublisher oder auf der Ergebnisliste eines Massenimports beruht.


