# Empfehlungen pflegen („Von Thorsten Jekel empfohlen“)

PodMix liest die Liste aus einer öffentlichen JSON-Datei:
`https://raw.githubusercontent.com/tjekel1968/podmix-empfehlungen/main/empfehlungen.json`

Ändert sich die Datei, sehen alle Nutzer die neue Liste beim nächsten Öffnen von
„Entdecken“ – ohne App-Update. Ist die Datei nicht erreichbar, nutzt die App die zuletzt
geladene Fassung, sonst die mitgelieferte Liste (`PodMix/Resources/empfehlungen.json`).

## Einen Podcast hinzufügen

1. Podcast in Apple Podcasts im Browser öffnen. Die Zahl hinter `id` in der Adresse ist
   die `appleId` (z. B. `.../id955053326` → `955053326`).
2. Auf github.com die Datei `empfehlungen.json` öffnen, Stift-Symbol, Eintrag ergänzen:

```json
{ "appleId": 955053326, "note": "Ein Satz, warum Sie ihn empfehlen." }
```

   Ohne Apple-Eintrag geht auch die Feed-Adresse (nur https):
   `{ "feedUrl": "https://…/feed.xml", "note": "…" }`
3. „Commit changes“. Fertig. Die Reihenfolge in der Datei ist die Reihenfolge in der App.

Regeln: höchstens 50 Einträge, Notiz höchstens 300 Zeichen, Datei höchstens 200 KB.
Eine fehlerhafte Datei wird ignoriert; dann bleibt die vorherige Liste sichtbar.
