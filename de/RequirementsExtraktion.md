
## Extrahieren von Anforderungen

Um in Gitbook Anforderungen als separate "Requirements" aus einem Fließtext zu extrahieren, ist das Vorgehen wie folgt:

* Schritt 1 ist zunächst fachlich/ gedankliche Vorarbeit. 
Hierbei geht es um die fachliche Analyse des Textes, um inhaltlich zusammenhängende Bestandteile als einzelne "Requirements" zu extrahieren.
Dazu kann es auch ggf. erforderlich sein, den Text inhaltlich nochmal umzustrukturieren. Optimalerweise sollten die identifizierten Einzelelemente dergestalt sein, dass es möglich wäre, sie einzeln (oder auch einzelne im Verbund) an einen Entwickler zur weiteren Bearbeitung zu geben oder als Basis zur Releaseplanung zu nutzen, o.ä..

* Ab Schritt 2 beginnt der eher "technische Teil" der Extraktion. 
Zunächst wird im zugehörigen Editor in einem Verzeichnis des Gitbooks - hier unter https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/ bzw. in der Filestruktur 
unter ->de ->requirements - eine neue Datei im Format reqXXXX.md angelegt. XXXX ist dabei eine vierstellige, fortlaufende Nummer, die bislang nicht vergeben ist, z.B. req0123.md.

* In Schritt 3 wird der als "Requirement" identifizierte Textbestandteil in die neue Datei übernommen und gespeichert.
Dabei wird zu Beginn des Textes noch ein Linkaufruf auf das Requirement gesetzt. Dieser hat folgendes Format: 

'''[req0123] https://github.com/PolitAktiv/politaktiv-requirements/tree/master/de/requirements/req0123.md''' 

als Linkziel (so können einzelne Requirements zukünftig leicht "in place" bearbeitet werden).  
Danach folgt dann erst der eigentlich Text.

* In Schritt 4 wird der bisherige Text in der Ursprungsdatei, die so immer mehr zu einem Rahmendokument wird, nur noch mit dem zugehörigen Include ersetzt.
Dieser sieht hier folgendermaßen aus: 

{% raw %}
{% include "git+https://github.com/PolitAktiv/politaktiv-requirements.git/de/requirements/req0123.md" %}
{% endraw %}

Nachdem alles gespeichert ist - ist die Extraktion erledigt.