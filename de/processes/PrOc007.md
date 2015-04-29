
### [PrOc007](https://github.com/PolitAktiv/politaktiv-requirements/tree/master/de/processes/PrOc007.md) CRM Account anlegen

#### Owner
 * IT


#### Stakeholder
 * PolitAktiv IT


#### Anstoss (Trigger)
PO beantragt in Jira einen neuen Zugang


#### Normaler Verlauf
 1 Ein IT-Admin erhält die Aufforderungn, einen neuen BenutzerAccount für das CRM einzurichten. Enthaltene Angaben sind:
  2 Vorname Nachname
  2 Kürzel (=username)
  2 Email
 1 Der IT Admin fügt den neuen Benutzer an
  2 ssh root@crm.intra.politaktiv.org an
  2 htpasswd -nb <username> <password>
  2 Das Ergebnis
    3 in htpasswd eintragen: vi /etc/apache2/htpasswd
    3 in puppet eintragen & commiten
    3 eine Email[1] schreiben & verschicken


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
