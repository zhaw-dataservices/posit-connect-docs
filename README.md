# Posit Connect – Dokumentation

Dokumentationssite für Posit Connect an der ZHAW, betrieben durch ZHAW Services Forschungsdaten. Gebaut mit [MkDocs](https://www.mkdocs.org/) und dem [Material-Theme](https://squidfunk.github.io/mkdocs-material/). Veröffentlicht unter: https://zhaw-dataservices.github.io/posit-connect-docs/

## Arbeiten mit diesem Repo
### Allgemeines

Inhalte liegen unter `docs/`. Jede Seite existiert auf Deutsch (`.md`) und Englisch (`.en.md`) — beide Versionen immer gemeinsam aktualisieren.

Änderungen auf `main` pushen: GitHub Actions baut die Site automatisch und veröffentlicht sie auf dem `gh-pages`-Branch.

### Rendering mit MkDocs

Falls nicht schon installiert, muss MkDocs und da Material-Theme installiert werden:

```bash
pip install mkdocs-material
```

Anschliessend kann die Webseite lokal gerendert werden:

```bash
mkdocs serve
```