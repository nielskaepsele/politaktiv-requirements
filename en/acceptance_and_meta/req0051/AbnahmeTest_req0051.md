##### AcceptanceTest  
#### Vorgehen: Test auf Facebook
 * Verschiedene bestehende URLs von Politaktiv auf Intermediate heraussuchen
 * URLs in Facebook URL Debugger eingeben: https://developers.facebook.com/tools/debug/og/object/
 * Prüfen, ob die von Facebook geparsten Informationen passen
   * In Einzelfällen die URL auch noch in aktiver Facebook-Chronik teilen, um Infos des Debuggers zu prüfen
 * Stichprobenartig ImageURL ausfüllen für einzelne Seiten (bei Seite bearbeiten → „Social Media Preview“, dort komplette URL von entsprechendem Bild der Seite eingefügt.)
 * Stichprobenartig VideoURL ausfüllen für eine Seite
   * normale URL
   * URL zum einbinden

#### Ergebnis: Test auf Facebook  22.01.2015
 * Text-Meta-Tags (Titel, Kurzbeschreibung etc.) werden erfolgreich aus SEO-Infos der Seite übernommen.
 * Politaktiv Logo bzw. Stadt-Logo/Wappen sind Default-Bilder.
   * Facebook wirft im Debugger eine Warnung wegen niedriger Auflösung des jeweiligen Logos, funktioniert aber dann trotzdem.
 * Manuelle ImageURL funktioniert.
 * VideoURL funktioniert nicht: 
   * Sowohl eine „normale“ Youtube URL wie https://www.youtube.com/watch?v=0t-Do4aLBZc als auch die URL zum Einbetten wie http://www.youtube.com/embed/0t-Do4aLBZc sind nicht zielführend. 
   * Es erscheint beim Teilen zwar in Facebook ein Play-Button, wenn man den anklickt, kommt dann aber nicht das Video.
   * Ursache unklar.
   * Priorität: Sehr niedrig. Derzeit ist das primäre Ziel der Integrata-Stiftung, Bürger auf die Website zu locken, nicht, dass sie in Facebook bleiben und dort Videos von der Website ansehen.

#### Testbeschreibung von:
Niels Ott <niels.ott@integrata-stiftung.de>