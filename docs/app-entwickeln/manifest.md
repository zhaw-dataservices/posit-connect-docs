# manifest.json erstellen

Posit Connect liest Apps direkt von GitHub. Dafür ist eine `manifest.json`-Datei zwingend erforderlich – sie beschreibt die App und ihre Abhängigkeiten.

## Was ist manifest.json?

<!-- TODO: Kurze Erklärung, was die Datei enthält und warum Posit Connect sie braucht -->

## Für Shiny-Apps (R)

Das Template enthält ein Skript `write_manifest.R`. Einmalig ausführen:

```r
source("write_manifest.R")
```

Die generierte `manifest.json` muss ins Repository committet werden.

<!-- TODO: Details, häufige Fehler -->

## Für Streamlit-Apps (Python)

<!-- TODO: write_manifest.py – folgt sobald Streamlit-Template verfügbar -->

## manifest.json aktuell halten

Bei Änderungen an Abhängigkeiten muss `manifest.json` neu generiert und committet werden.

<!-- TODO: Hinweis, wann eine Aktualisierung nötig ist -->
