# Galileo Rechercheboard (GitHub Pages)

Ein leichtgewichtiges Frontend im Galileo-Look, mit dem Redakteur:innen bildstarke und seriös recherchierte Beitragsthemen filtern können. Läuft statisch auf GitHub Pages – kein Python oder Backend nötig.

## Inhalte
- `index.html`: Komplettes UI im Galileo-Design mit Filterlogik und Ranking nach Schlagwort-Treffern.
- `topics.json`: Vorausgefüllte Themenideen mit Zusammenfassung, Relevanz, visueller Umsetzung, Quellen und Storyline (5–20 Minuten).
- `.github/workflows/deploy.yml`: Automatisches Deploy auf GitHub Pages.

## Nutzung
### GitHub Pages
1. Repository auf GitHub pushen.
2. In den Repository-Einstellungen unter **Pages** **Build and Deployment** auf "GitHub Actions" stellen.
3. Workflow `.github/workflows/deploy.yml` wird bei jedem Push auf `main` ausgeführt und baut die statische Seite.
4. Nach dem Deploy unter `https://<user>.github.io/<repo>/` öffnen (URL steht auch in der Actions-Ansicht).

### Lokal testen
Einfach im Browser öffnen:
```bash
# im Repository-Verzeichnis
python -m http.server 8000  # oder ein beliebiger lokaler Webserver
# dann http://localhost:8000/ im Browser öffnen
```

## Bedienung
- Alle Galileo-Schlagwörter sind standardmäßig aktiv; Karten werden nach Trefferzahl sortiert und behalten das Galileo-Farbschema.
- Checkboxen erlauben schnelles Ein- und Ausschalten von Schlagwörtern, die Ergebniskarten aktualisieren sich live.
- Jede Karte zeigt klar: Zusammenfassung, Relevanz, visuelle Umsetzung, seriöse Quellen und Storyline (5–20 Minuten) sowie die getroffenen Schlagwörter.

## Anpassung
- Neue Schlagwörter in `index.html` unter `KEYWORDS` ergänzen.
- Weitere Themen durch Ergänzen von Objekten in `topics.json` hinzufügen (Felder: `title`, `summary`, `relevance`, `visual_idea`, `sources`, `storyline`, `keywords`).
