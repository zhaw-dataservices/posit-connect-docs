# Inhalts-Checkliste

Übersicht der noch zu schreibenden Inhalte. Jeder Punkt existiert zweimal:
einmal auf Deutsch (`.md`) und einmal auf Englisch (`.en.md`). Haken setzen,
wenn **beide** Sprachen fertig sind.

> 🔒 = hängt von Externem ab und lässt sich erst dann vollständig schreiben.

## Startseite (`index`)

- [ ] Über diesen Service: Kurzbeschreibung, Betreiber, Zielgruppe
- [ ] Weitere Ressourcen: Linksammlung (ZHAW-intern, Posit-Connect-Doku)

## Nutzungsabklärung (`nutzungsabklaerung`)

- [ ] Warum dieser Schritt? (Datenschutz, Ressourcen, Sicherheit)
- [ ] Vorgehen im Self Service Portal (Schritt für Schritt, evtl. Screenshots)
- [ ] Was passiert danach? (Kontaktaufnahme, Freigabe)

## App entwickeln

### Template verwenden (`app-entwickeln/template`)

- [ ] Warum das Template? (Vorteile)
- [ ] Template herunterladen / klonen (Link zum Repo)
- [ ] Struktur des Templates
- [ ] Anleitung Shiny (R)
- [ ] 🔒 Anleitung Streamlit (Python) – Template fehlt noch
- [ ] 🔒 `manifest.json` generieren (`write_manifest`) – Skripte fehlen noch

### Bestehende App einbinden (`app-entwickeln/bestehende-app`)

- [ ] Voraussetzungen
- [ ] Vorgehen (Schritt für Schritt)
- [ ] Häufige Anpassungen

### Best Practices (`app-entwickeln/best-practices`)

- [ ] Allgemein (Codestruktur, Lesbarkeit, Reproducibility)
- [ ] Shiny (R)
- [ ] Streamlit (Python)
- [ ] Abhängigkeiten verwalten (renv / requirements.txt / pyproject.toml)
- [ ] Corporate Design einhalten

### Datenquellen & Datenzugriff (`app-entwickeln/daten`)

- [x] Wo liegen die Daten? (öffentlich, vertraulich/REDCap, institutionell, Ausschluss Repo-Bundling)
- [x] Empfohlene ORD-Datenquellen (Zenodo, OSF, BORIS)
- [x] Grundsatz Datensparsamkeit (Lade-Muster, gezielte Abfragen, Checkliste)

### REDCap-Integration (`app-entwickeln/redcap`)

- [ ] Voraussetzungen (Zugang, API-Token, Berechtigungen)
- [ ] Verbindung herstellen (R)
- [ ] Verbindung herstellen (Python)
- [ ] API-Token sicher speichern
- [ ] Hinweise zum Datenschutz

## Code teilen & Deployment vorbereiten

### Code teilen via GitHub (`code-teilen/github-zhaw`)

Eine Seite für beide Fälle (github.zhaw.ch als Normalfall, GitHub.com als Ausnahme) – die frühere Aufteilung in zwei Unterseiten wurde am 2026-07-08 rückgängig gemacht.

- [ ] Voraussetzungen
- [ ] Repository anlegen
- [ ] Code hochladen
- [ ] Uns Zugriff geben
- [ ] 🔒 Branch-Konventionen – noch mit der ICT zu definieren
- [ ] Wann ist GitHub.com als Alternative möglich? Vorgehen, Hinweise (Öffentlichkeit, Lizenz)

### manifest.json erstellen (`code-teilen/manifest`)

- [ ] Was ist `manifest.json`?
- [ ] Für Shiny-Apps (R)
- [ ] 🔒 Für Streamlit-Apps (Python) – Template fehlt noch
- [ ] `manifest.json` aktuell halten

## Deployment (`deployment`)

- [ ] Was wir prüfen (Checkliste)
- [ ] Ablauf nach der Übergabe
- [ ] Nach dem Deployment (URL, Rechte, Updates)
- [ ] 🔒 Updates & Änderungen – Branch-Workflow TBD

## Support & FAQ (`support`)

- [ ] Kontaktangaben
- [ ] FAQ: Muss ich zwingend das Template verwenden?
- [ ] FAQ: Was passiert mit meinen Daten auf dem Server?
- [ ] FAQ: Wie lange dauert das Deployment?
- [ ] 🔒 FAQ: Kann ich meine App nachträglich ändern? – Branch-Workflow TBD
- [ ] Bekannte Probleme
