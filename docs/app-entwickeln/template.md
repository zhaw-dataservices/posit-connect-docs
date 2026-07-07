# Übersicht & Templates

Wir stellen ein Template im Corporate Design der ZHAW zur Verfügung. Es enthält die grundlegende Struktur und ist der empfohlene Ausgangspunkt für neue Apps.

!!! note "Noch nicht veröffentlicht"
    Die Templates sind nicht mehr auf github.com verfügbar. Das Shiny-Template wird derzeit auf github.zhaw.ch neu aufgebaut. Der Zugriff erfolgt dort über institutionelles Login (SSO) – das ist beabsichtigt, da das Repository nicht mehr öffentlich sein soll. Der Link folgt, sobald das Template bereit ist. Ein Streamlit-Template gibt es vorerst nicht, der Fokus liegt zunächst auf Shiny (R).

## Warum das Template?

<!-- TODO: Vorteile erklären (CD, manifest.json bereits integriert, Best Practices) -->

## Template herunterladen / klonen

*Link folgt, sobald das Shiny-Template auf github.zhaw.ch veröffentlicht ist (siehe Hinweis oben).*

<!-- TODO: Link zum GitHub-Repository des Templates, sobald verfügbar -->

## Struktur des Templates

<!-- TODO: Ordnerstruktur und wichtigste Dateien erklären -->

## Template für Shiny (R)

<!-- TODO: Anleitung für Shiny-Template -->

### manifest.json generieren

Das Template enthält ein Skript `write_manifest.R`. Dieses muss einmalig ausgeführt werden, bevor der Code geteilt wird.

```r
# write_manifest.R ausführen
source("write_manifest.R")
```

<!-- TODO: Weitere Details -->

## Template für Streamlit (Python)

<!-- TODO: Anleitung für Streamlit-Template (folgt) -->

### manifest.json generieren

<!-- TODO: Analog write_manifest.py – folgt sobald Template verfügbar -->
