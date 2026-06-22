# Ablauf im Überblick

Diese Seite beschreibt den gesamten Prozess – von der Entwicklung einer App bis zur Publikation auf Posit Connect.

## Prozessübersicht

![Ablauf im Überblick](assets/ablauf.svg)

Die Schritte im Überblick:

1. **Nutzungsabklärung** – Abklärung im Self Service Portal (SSP)
2. **App entwickeln** – App mit unserem Template entwickeln oder bestehende App einbinden
3. **Code teilen** – Source Code auf github.zhaw.ch bereitstellen
4. **Feedback & Deployment** – Wir prüfen den Code und deployen die App

## Detaillierte Beschreibung der Schritte

### Schritt 1: Nutzungsabklärung

Jede App startet mit einer Nutzungsabklärung über das Self Service Portal (SSP). Dabei werden Datenschutz, Ressourcenbedarf und Sicherheit geprüft. Details dazu auf der Seite [Nutzungsabklärung](nutzungsabklaerung.md).

### Schritt 2: App entwickeln

Anschliessend entwickelst du deine App – entweder mit unserem Template oder durch Einbinden einer bestehenden App. Unterstützt werden primär Shiny, Streamlit und Quarto. Siehe [App entwickeln](app-entwickeln/template.md).

### Schritt 3: Code teilen

Der Source Code wird in einem Repository auf github.zhaw.ch bereitgestellt, damit Posit Connect die App direkt von dort lesen kann. Siehe [Code teilen](code-teilen/github-zhaw.md).

### Schritt 4: Feedback & Deployment

Zum Schluss prüfen wir den Code und übernehmen das Deployment auf Posit Connect. Nach dem Deployment erhältst du die URL deiner App. Siehe [Deployment](deployment.md).
