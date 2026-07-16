# Willkommen

Diese Seite dokumentiert den ZHAW-Service «Interaktive Datenvisualisierung» – die zentrale Hosting-Infrastruktur für interaktive Forschungsdatenvisualisierungen.

!!! note "Hinweis"
    Diese Dokumentation befindet sich noch im Aufbau und wird laufend ergänzt. Einzelne Inhalte fehlen oder können sich noch ändern.

## Über diesen Service

Seit Juni 2026 betreibt die ZHAW mit Posit Connect eine Plattform für interaktive Datenvisualisierungen. Forscher:innen können damit ihre Daten interaktiv erlebbar machen – passend für ganz unterschiedliche Zielgruppen.

Im Zentrum stehen interaktive Dashboards: kleine Web-Anwendungen, in denen Nutzende die Daten selbst erkunden, filtern und in Diagrammen sichtbar machen können, ganz ohne eigene Installation. Solche Dashboards entstehen meist mit Shiny (für R) oder Streamlit (für Python). Ebenso hosten wir gerne interaktive Berichte und Webseiten, die mit Quarto (R / Python) erstellt wurden.

Posit Connect kann grundsätzlich noch mehr veröffentlichen; einen vollständigen Überblick bietet die [Produktseite von Posit Connect](https://posit.co/products/enterprise/connect). Unsere Best Practices und unser Support sind zunächst auf Shiny und Streamlit ausgerichtet.

## Ablauf auf einen Blick

Von der Idee bis zur publizierten App führen fünf Schritte:

<div class="process-diagram-wrapper">
--8<-- "assets/ablauf.svg"
</div>

Schritt 1 und 2 können unabhängig voneinander und in beliebiger Reihenfolge erfolgen.

### Schritt 1: Vorabklärung

Den Anfang macht die erste Kontaktaufnahme, für Erstanwender:innen empfohlen: am besten per Mail an [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch), um das Vorgehen zu besprechen. Danach füllst du im Self Service Portal (SSP) das [SSP-Formular](https://servicedesk.zhaw.ch/tas/public/ssp/content/serviceflow?unid=330c213f-12fa-44e4-ad9b-07abb40fa513) aus, das bei Bedarf auch eine Nutzungsabklärung umfasst (Datenschutz, Ressourcen, Sicherheit). Details dazu auf der Seite [Nutzungsabklärung](nutzungsabklaerung.md).

### Schritt 2: App entwickeln

Du entwickelst deine App entweder mit unseren Templates oder durch Einbinden einer bestehenden App. Unterstützt werden primär Shiny, Streamlit und Quarto; dazu gehören Best Practices, Corporate Design und das Generieren der `manifest.json`. Siehe [App entwickeln](app-entwickeln/template.md). Wichtige Infos, Tipps & Tricks findest du unter [Best Practices](app-entwickeln/best-practices.md).

### Schritt 3: Code teilen

Der Source Code wird in einem Repository auf github.zhaw.ch bereitgestellt, damit Posit Connect die App direkt von dort lesen kann (GitHub.com nur als Ausnahme je nach Datenlage). Über Git ist auch die Kollaboration mit anderen Forschenden möglich. Siehe [Code teilen](code-teilen/github-zhaw.md).

### Schritt 4: Review

Wir prüfen Code und App – unter anderem auf Best Practices, Corporate Design, Datenschutz und Datensparsamkeit, Metadaten und Projektzuordnung, Zugriffsrechte sowie End of Life. Sind Anpassungen nötig, geht die App zur Überarbeitung zurück; andernfalls folgt das Deployment. Siehe [Deployment](deployment.md).

### Schritt 5: Deployment

Nach erfolgreichem Review übernehmen wir das Deployment auf Posit Connect. Die App geht live unter einer Wunsch-URL nach dem Muster `exploredata.zhaw.ch/name-der-app`. Anschliessend werden die Zugriffsrechte konfiguriert, und bei Bedarf folgen spätere Updates. Siehe [Deployment](deployment.md).

## Kontakt

Dieser Service wird von den ZHAW Services Forschungsdaten betrieben.

**Kontakt:** [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch)
