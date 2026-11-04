# Verträge

Haushaltsverträge verwalten: Laufzeiten, Beiträge, Kündigungsfristen und Historie. Der nächstmögliche Kündigungstermin wird automatisch berechnet. Dokumente liegen in Paperless und werden nur verlinkt.

Eine einzige Datei (`index.html`), keine Build-Schritte. Daten liegen in PocketBase, offline wird im Browser zwischengespeichert und beim nächsten Kontakt abgeglichen.

## Einrichtung in PocketBase

1. Neue Collection vom Typ **Base** mit dem Namen `vertraege` anlegen.
2. Feld `data` vom Typ **JSON** hinzufügen.
3. API Rules für List, View, Create, Update und Delete: `@request.auth.id != ""`
4. Anmeldung läuft über die Collection `users`.

Die Einstellungen (Haushaltsmitglieder, Vorlauf) liegen als Datensatz mit der ID `einstellungen00` in derselben Collection.

## Veröffentlichen

`index.html` auf die Subdomain legen. Läuft sie direkt auf PocketBase (`pb_public`), ist die Serveradresse beim Login vorausgefüllt.

## Sicherung

Einstellungen → Sicherung exportiert alle Daten als JSON. `beispieldaten.json` enthält ausgedachte Testdaten zum Einspielen.
