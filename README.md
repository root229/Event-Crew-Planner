# 🎛️ Event Crew Planner

Eine einfache statische Website, um für verschiedene Events die Crew, Ankunftszeiten und Aufgaben übersichtlich darzustellen.

## Struktur

```
event-crew-planner/
├── index.html      ← Die Website
├── events.json     ← Alle Daten (hier bearbeiten!)
└── README.md
```

## Hosting auf GitHub Pages

1. Neues Repository auf GitHub erstellen
2. Diese Dateien in das Repository pushen:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/DEIN-USERNAME/REPO-NAME.git
   git push -u origin main
   ```
3. In den Repository-Einstellungen: **Settings → Pages → Source: "main branch"**
4. Nach 1-2 Minuten ist die Seite erreichbar unter:  
   `https://DEIN-USERNAME.github.io/REPO-NAME/`

## Events bearbeiten (events.json)

Die `events.json` enthält ein Array von Events. Jedes Event hat folgende Felder:

```json
{
  "id": "eindeutige-id",          // Für die URL-Logik (keine Leerzeichen)
  "name": "Eventname",
  "date": "2025-08-15",           // Format: JJJJ-MM-TT
  "location": "Ort",
  "crew": [
    {
      "name": "Hans",
      "arrival": "16:30",         // Ankunftszeit
      "color": "#4A90D9",         // Farbe für diesen Helfer (Hex)
      "tasks": [
        { "time": "16:30", "label": "Aufbau" },
        { "time": "18:00", "label": "Tontechnik" }
      ]
    }
  ]
}
```

### Farb-Empfehlungen

| Person | Farbcode  |
|--------|-----------|
| Blau   | `#4A90D9` |
| Lila   | `#7B68EE` |
| Orange | `#E07B54` |
| Grün   | `#5BAD8F` |
| Pink   | `#D4699E` |
| Gelb   | `#C9A227` |

## Lokaler Test

Da die Website eine JSON-Datei per Fetch lädt, funktioniert ein direktes Öffnen der HTML-Datei im Browser **nicht** (CORS-Beschränkung). Stattdessen:

```bash
# Option 1: Python (meistens vorinstalliert)
python3 -m http.server 8000
# → Browser: http://localhost:8000

# Option 2: Node.js
npx serve .
# → Browser: http://localhost:3000
```
