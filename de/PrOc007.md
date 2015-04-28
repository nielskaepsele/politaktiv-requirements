
### PrOc007 CRM Account anlegen

#### Owner
 * IT


#### Stakeholder
 * PolitAktiv IT


#### Anstoss (Trigger)
PO beantragt in Jira einen neuen Zugang


#### Normaler Verlauf
 1 Ein IT-Admin erhält die Aufforderungn, einen neuen BenutzerAccount für das CRM einzurichten. Enthaltene Angaben sind:
  1 Vorname Nachname
  1 Kürzel (=username)
  1 Email
 1 Der IT Admin fügt den neuen Benutzer an
  1 ssh root@crm.intra.politaktiv.org an
  1 htpasswd -nb <username> <password>
  1 Das Ergebnis
    1 in htpasswd eintragen: vi /etc/apache2/htpasswd
    1 in puppet eintragen & commiten
    1 eine Email[1] schreiben & verschicken


#### Anhang

[1] Benachrichtigungsmail

Empfänger: 
 * Kandidat
 * PO (mom)

Subject: HTAccess Passwort für das CRM System

Text:
Hallo Herr xxx,

ich habe Ihnen einen äußeren, ersten Account für Ihren CRM Zugang angelegt:

	Die URL lautet: https://crm.intra.politaktiv.org
	User:		xxx
	Passwort: 	xxx
	


Den eigentlichen CRM Account werden Sie von Hr. Mörike zugesandt bekommen.


Mit freundlichen Grüßen,
