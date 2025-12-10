# Galileo Rechercheboard (GitHub Pages)

Ein leichtgewichtiges Frontend im Galileo-Look, mit dem Redakteur:innen bildstarke und seriös recherchierte Beitragsthemen filtern können. Läuft statisch auf GitHub Pages – kein Python oder Backend nötig.

## Inhalte
- `index.html`: Komplettes UI im Galileo-Design mit Filterlogik, Ranking nach Schlagwort-Treffern und Live-Suche nach Newsfeeds (24h/7/30 Tage).
- `topics.json`: Vorausgefüllte Themenideen mit Zusammenfassung, Relevanz, visueller Umsetzung, Quellen und Storyline (5–20 Minuten).
- `.github/workflows/deploy.yml`: Automatisches Deploy auf GitHub Pages.

## Nutzung
### GitHub Pages
1. Repository auf GitHub pushen.
2. In den Repository-Einstellungen unter **Pages** **Build and Deployment** auf "GitHub Actions" stellen (damit Pages über die
   Actions aktiviert wird).
3. Workflow `.github/workflows/deploy.yml` wird bei jedem Push auf `main` ausgeführt, konfiguriert Pages automatisch und baut
   die statische Seite.
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
- "Live-Themen finden" ruft aktuelle News (Google News RSS via AllOrigins) für 24h/7/30 Tage ab, versieht sie mit Schlagworten und reiht sie in das Ranking ein; mit "Nur Live-Ergebnisse" lässt sich zwischen Kuratierung und Live filtern.
- Jede Karte zeigt klar: Zusammenfassung, Relevanz, visuelle Umsetzung, seriöse Quellen und Storyline (5–20 Minuten) sowie die getroffenen Schlagwörter.

## Anpassung
- Neue Schlagwörter in `index.html` unter `KEYWORDS` ergänzen.
- Weitere Themen durch Ergänzen von Objekten in `topics.json` hinzufügen (Felder: `title`, `summary`, `relevance`, `visual_idea`, `sources`, `storyline`, `keywords`).
