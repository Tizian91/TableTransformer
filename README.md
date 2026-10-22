<p align="center"><img src="icons/icon.svg" width="96" alt=""></p>

# TableTransformer

Markdown-Tabelle einfügen → gestalten → als Bild, Word-Tabelle, LaTeX oder Markdown exportieren.

Der Tabellen-Designer ist eine einzelne HTML-Datei ohne Abhängigkeiten. Er läuft komplett im Browser; die Tabellen verlassen den Rechner nicht.

**➜ Online nutzen:** [tizian91.github.io/TableTransformer](https://tizian91.github.io/TableTransformer/)

## Funktionen

- **Eingabe:** Markdown-Tabellen, aus Excel kopierte Zellen (Tabulator-getrennt), `.md`/`.csv`/`.tsv`/`.txt`-Dateien per Öffnen-Dialog oder Drag & Drop
- **Daten:** sortieren, Zahlen runden, Zeilen und Spalten tauschen, Spalten ausblenden
- **Gestaltung:** Schrift, Ausrichtung, Spaltenbreiten und Zeilenhöhen, Linien, Farben, Zebrastreifen, Beschriftung und Fußnote
- **Stile:** Vorlagen, eigene Stile im Browser oder in einem Ordner speichern, als JSON exportieren/importieren
- **Export:**
  - als echte Tabelle für Word (Zwischenablage oder `.doc`)
  - als Bild (PNG kopieren/speichern, SVG, PDF über Drucken)
  - als LaTeX (`booktabs`, Farben) oder bereinigtes Markdown

## Als App installieren (Microsoft Edge)

Der Tabellen-Designer lässt sich als eigenständige App installieren. Danach hat er ein eigenes Fenster und Icon im Startmenü und in der Taskleiste und funktioniert auch offline.

1. Die Online-Version (Link oben) in **Microsoft Edge** öffnen.
2. Rechts in der Adressleiste auf das Symbol **„App verfügbar – Installieren“** klicken
   *oder* Menü **⋯ → Apps → Diese Website als App installieren**.
3. Mit **Installieren** bestätigen. Optional: an Taskleiste/Startmenü anheften.

In Chrome funktioniert es genauso (Menü **⋮ → Streamen, speichern und teilen → Seite als App installieren**).

### Dateien aus dem Explorer öffnen

Die installierte App meldet sich bei Windows als Programm für `.md`, `.markdown`, `.csv`, `.tsv` und `.txt` an:
im Explorer Rechtsklick auf die Datei → **Öffnen mit** → **Tabellen-Designer**. Beim ersten Mal fragt Edge einmalig, ob die App Dateien öffnen darf.

### Deinstallieren

In der App oben rechts **⋯ → App-Einstellungen → Deinstallieren** oder unter `edge://apps`.

> **Warum nicht direkt aus der lokalen Datei?** Browser erlauben die App-Installation nur für Seiten, die über `https://` (oder `http://localhost`) geladen werden, nicht für Dateien, die per Doppelklick geöffnet werden (`file://`). Deshalb wird über GitHub Pages installiert. Nach der Installation läuft die App trotzdem vollständig lokal und offline.

## Ohne Installation nutzen

`TableTransformer.html` herunterladen und per Doppelklick im Browser öffnen. Alles funktioniert offline. Nur die App-Installation und „Öffnen mit“ sind dann nicht verfügbar.

## Datenspeicherung

Tabelle, Stil und eigene Vorlagen werden nur lokal im Browser (`localStorage`) gespeichert. Die lokale Datei, die Online-Version und die installierte App haben jeweils einen eigenen Speicher. Stile lassen sich über **Stil exportieren/importieren** übertragen.

## Eigene Kopie auf GitHub Pages veröffentlichen

1. Repository auf GitHub anlegen und die Dateien hochladen (`git push`).
2. **Settings → Pages → Build and deployment → Source: Deploy from a branch**, Branch `main`, Ordner `/ (root)` → **Save**.
3. Nach ca. einer Minute ist die App unter `https://<GITHUB-NAME>.github.io/<REPO-NAME>/` erreichbar.

Wenn Sie Dateien ändern, erhöhen Sie in `sw.js` die Konstante `VERSION`, damit installierte Apps die neue Fassung laden.

## Projektstruktur

| Datei | Zweck |
|---|---|
| `TableTransformer.html` | Die komplette Anwendung |
| `index.html` | Weiterleitung, damit die Startadresse von GitHub Pages funktioniert |
| `manifest.webmanifest` | App-Name, Icons, Dateizuordnungen für die Installation |
| `sw.js` | Service Worker für den Offline-Betrieb |
| `icons/` | App-Icons (SVG-Quelle und PNGs) |

## Lizenz

Copyright (C) 2026 Tizian Arold

Dieses Programm ist freie Software: Sie können es unter den Bedingungen der [GNU General Public License](LICENSE), Version 3 oder (nach Ihrer Wahl) jeder späteren Version, weitergeben und/oder verändern. Es wird ohne jede Gewährleistung bereitgestellt.
