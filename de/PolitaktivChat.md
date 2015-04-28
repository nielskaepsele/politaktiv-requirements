!1 Aus der Chatevaluierung
!3 '''Quelle:'''
politaktiv/Produktmanagement/UseCases/Chat-Typen

!3 Bold-Chat
!img /files/StakeholderRequests/bold-chat.jpg

Ich werde nicht schlau daraus, ob man mit dieser Technik den Bold-Chat bei uns einbauen kann. Offensichtlich hilft mir dafür das dashboard auch nicht wirklich weiter. Hier wird offensichtlich ein neues Fenster im Browser geöffnet mit allen erforderlichen Teilchen (Scrollbalken, etc..). Ob man es aber im selben Portlet innerhalb desselben Fensters öffnen kann, kann ich nicht erkennen.

Bold hat den großen Nachteil, es handelt alle Chat-Kontakte schön getrennt und einzeln ab. Kein Chat-Teilnehmer kann sehen, was die anderen jeweils sagen.

!3 Olark
Der Link: http://www.olark.com/customer/portal/articles/1217765-loading-the-chat-box-from-the-side  beschreibt, wie man OLARk auf eine Website einbauen kann. Das sieht vom Prinzip her ganz ähnlich aus, wie bei BOLD-Chat. Daher kann ich es leider auch bei OLARK nicht erkennen, ob das geht oder nicht. Das dashboard sagt auch dort nicht viel mehr darüber.

Auch OLARk hat den Nachteil, dass es die einzelnen Chats disjunkt behandelt und den Nutzern nicht erlaubt zu sehen, was andere chatten. Was wir benötigen ist ein Collaboration-Chat.

!3 LiveChatinc
Dasselbe Bild bei livechatinc. Auch das ist ein Chat, der für den Helpdesk gedacht ist und die user einzeln behandelt (ungeeignet).

!3 Andere
Wie wärs mit folgenden?

 1 http://frug.github.io/AJAX-Chat/          Scheint alles zu haben, was wir brauchen.

 1 http://chat.keeptalking.de/freechatbox/?lng=de Das         ist auf jeden Fall direkt einbindbar

 1 http://www.chatleasing.de/index.php?ad=chatanbieter&page=tour1

!2 Überlegungen
Es zeigt mir, wir suchen einen Chatroom, nicht ein Hilfesystem per Chat, also eher etwas aus der Spieleecke als aus der professionellen Ecke. In einem Chatroom können mehrere Benutzer gleichzeitig schreiben. UND: Wir suchen einen Chatroom, den wir in jeden DK getrennt einbauen können.‘ Die Benutzer sollen namentlich dargestellt werden. Dargestellt werden die momentan jeweils angemeldeten Benutzer dieses DK. Es ist für alle (auch Gäste) sichtbar, ob ein Chat gerade läuft. Ankündigungs-Muster: „Chatraum – derzeit läuft ein Chat“ oder „Chatraum – derzeit läuft kein Chat“ Der Moderator startet den Chat und stoppt ihn. Nur wer angemeldet ist und dem DK beigetreten ist, kann den Chatraum betreten und sieht was im Chat geschrieben wird und die die Namen der Chattenden Teilnehmer. Die Chatnamen sind die Anmeldenamen (Usernames), nicht die Klarnamen. Der Chat darf wo anders gehostet werden (muss aber nicht). Es genügt ein simples (unendlich) langes sequentielles Protokoll, das für alle Chattenden einsehbar ist durch vor- und zurückscrollen. In den Chat-Text sollten Links einbaubar sein (nice to have). Schön wäre weiterhin folgendes: Man meldet sich an, indem man sich in PA einloggt (nachdem man dem DK beigetreten ist) und man
