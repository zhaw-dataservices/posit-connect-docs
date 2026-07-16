# Willkommen

Diese Seite dokumentiert den ZHAW-Service «Interaktive Datenvisualisierung» – die zentrale Hosting-Infrastruktur für interaktive Forschungsdatenvisualisierungen.

!!! note "Hinweis"
    Diese Dokumentation befindet sich noch im Aufbau und wird laufend ergänzt. Einzelne Inhalte fehlen oder können sich noch ändern.

## Über diesen Service

Seit Juni 2026 betreibt die ZHAW mit Posit Connect eine Plattform für interaktive Datenvisualisierungen. Forscher:innen können damit ihre Daten interaktiv erlebbar machen – passend für ganz unterschiedliche Zielgruppen.

Im Zentrum stehen interaktive Dashboards: kleine Web-Anwendungen, in denen Nutzende die Daten selbst erkunden, filtern und in Diagrammen sichtbar machen können, ganz ohne eigene Installation. Solche Dashboards entstehen meist mit Shiny (für R) oder Streamlit (für Python). Ebenso hosten wir gerne interaktive Berichte und Webseiten, die mit Quarto (R / Python) erstellt wurden.

Posit Connect kann grundsätzlich noch mehr veröffentlichen; einen vollständigen Überblick bietet die [Produktseite von Posit Connect](https://posit.co/products/enterprise/connect). Unsere Best Practices und unser Support sind zunächst auf Shiny und Streamlit ausgerichtet.

## Ablauf

Von der Idee bis zur publizierten App führen fünf Schritte:

<div class="process-diagram-wrapper">
--8<-- "assets/ablauf.svg"
</div>

Schritt 1 und 2 können unabhängig voneinander und in beliebiger Reihenfolge erfolgen.

### Schritt 1: Vorabklärung

Den Anfang macht die erste Kontaktaufnahme, für Erstanwender:innen empfohlen: am besten per Mail an [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch), um das Konzept und das Vorgehen zu besprechen. Für das Gespräch hilfreich sind Antworten zu folgenden Fragen:

- Was ist das Ziel und das Konzept der Datenvisualisierung?
- Über welche Funktionalitäten soll die Visualisierung verfügen?
- Mit welcher Programmiersprache und welchen Bibliotheken soll sie umgesetzt werden?
- Wie sehen die Daten aus, und wie sind sie bezüglich Vertraulichkeit klassifiziert?
- Wo werden die Daten abgelegt?

Wir besprechen ausserdem Code-Entwicklung und Kollaboration, die App-Registrierung und eine allfällige Nutzungsabklärung sowie das weitere Vorgehen und den Zeitplan.

Danach füllst du im Self Service Portal das [SSP-Formular](https://servicedesk.zhaw.ch/tas/public/ssp/content/serviceflow?unid=330c213f-12fa-44e4-ad9b-07abb40fa513) aus, das bei Bedarf auch eine Nutzungsabklärung umfasst. Details dazu auf der Seite [Nutzungsabklärung](nutzungsabklaerung.md).

### Schritt 2: App entwickeln

Du entwickelst deine App, idealerweise mit unseren Templates, die du unter [github.zhaw.ch/service-research-data](https://github.zhaw.ch/service-research-data) findest. Unterstützt werden primär Shiny, Streamlit und Quarto. Siehe [App entwickeln](app-entwickeln/template.md). Wichtige Infos, Tipps & Tricks findest du unter [Best Practices](app-entwickeln/best-practices.md). Wir empfehlen besonders, Git zu nutzen, idealerweise über [github.zhaw.ch](https://github.zhaw.ch) – Über Git ist auch die Kollaboration mit anderen Forscher:innen möglich.

### Schritt 3: Code teilen

Sobald du bereit bist, deine App zu veröffentlichen, wird der finale Source Code auf [github.zhaw.ch/service-research-data](https://github.zhaw.ch/service-research-data) bereitgestellt, damit Posit Connect die App direkt von dort lesen kann (GitHub.com nur als Ausnahme je nach Datenlage). Siehe [Code teilen](code-teilen/github-zhaw.md).

### Schritt 4: Review

Wir prüfen Code und App – unter anderem auf Best Practices, Corporate Design, Datenschutz und Datensparsamkeit, Metadaten und Projektzuordnung, Zugriffsrechte sowie End of Life. Sind Anpassungen nötig, geht die App zur Überarbeitung zurück; andernfalls folgt die Veröffentlichung. Siehe [Veröffentlichung](deployment.md).

### Schritt 5: Veröffentlichung

Nach erfolgreichem Review übernehmen wir die Veröffentlichung auf Posit Connect. Die App geht live unter einer Wunsch-URL nach dem Muster `exploredata.zhaw.ch/name-der-app`. Anschliessend werden die Zugriffsrechte konfiguriert, und bei Bedarf folgen spätere Updates. Siehe [Veröffentlichung](deployment.md).

## Kontakt

Dieser Service wird von den ZHAW Services Forschungsdaten betrieben.

**Kontakt:** [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch)
