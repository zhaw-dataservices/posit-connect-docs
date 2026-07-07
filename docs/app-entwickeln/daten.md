# Datenquellen & Datenzugriff

Apps auf Posit Connect sollen nur die Daten verwenden, die tatsächlich benötigt werden. Diese Seite zeigt, wo die Daten für dein Dashboard liegen sollten und wie sie möglichst schonend abgerufen werden.

## Wo liegen die Daten?

Je nach Art der Daten empfehlen wir unterschiedliche Wege.

### Öffentliche Forschungsdaten

Ideal ist die Ablage in einem ORD-Repository (Open Research Data). Die App liest die Daten direkt von dort – Daten und Code bleiben getrennt und unabhängig versionierbar. Empfohlene Repositorien sind z. B.:

- [Zenodo](https://zenodo.org) – generisches Repositorium (CERN), vergibt DOIs, für praktisch jeden Dateityp geeignet
- [OSF](https://osf.io) – Open Science Framework, Projekt- und Datenverwaltung inklusive Versionierung
- [BORIS](https://boris.unibe.ch) – Bern Open Repository and Information System

### Vertrauliche oder sensible Daten

Für vertrauliche oder personenbezogene Daten empfehlen wir [ZHAW-REDCap](https://redcap.zhaw.ch/). Apps können Daten direkt aus REDCap lesen. Eine gesonderte Anleitung dazu findet sich unter [REDCap-Integration](redcap.md).

Besonders schützenswerte Personendaten (z. B. Gesundheitsdaten, Herkunft, religiöse Anschauungen) dürfen nur verarbeitet werden, wenn dies im Rahmen der [Nutzungsabklärung](../nutzungsabklaerung.md) explizit freigegeben wurde.

### Weitere institutionelle Quellen

!!! note "In Prüfung"
    Interne Datenbanken und SharePoint sind als mögliche Quellen im Blick, die Anbindung an Posit Connect wurde aber noch nicht getestet. Diese und weitere institutionelle Optionen werden intern geprüft – Details folgen.

### Ausgeschlossen: Daten direkt im Repository

Eine Datendatei (z. B. `.RData` oder `.csv`) im Code-Repository abzulegen widerspricht mehreren Best Practices: Die Daten wären nicht unabhängig vom Code versioniert, jede Aktualisierung würde ein Redeploy erfordern, und es bestünde das Risiko, versehentlich sensible Daten einzuchecken. Das [shiny-base](https://github.zhaw.ch/service-research-data/shiny-base)-Template *(work in progress, noch nicht öffentlich)* setzt das auch technisch durch: `.RData`- und `.csv`-Dateien sind dort bereits über `.gitignore` ausgeschlossen und werden gar nicht erst committet. Lies deine Daten stattdessen über eine der oben genannten Quellen ein (ORD-Repository, REDCap, institutionelle Quelle).

## Grundsatz: Datensparsamkeit

Apps auf Posit Connect sollen so selten und so gezielt wie möglich auf ihre Datenquelle zugreifen – egal ob REDCap, ein ORD-Repository oder eine institutionelle Quelle. Die Quelle liegt nachgelagert von Posit Connect und sollte nicht unnötig belastet werden.

### Häufigster Fehler: Daten bei jeder Interaktion neu laden

Steht der Datenabruf innerhalb einer reaktiven Funktion (z. B. `observeEvent()`), löst jede Nutzerinteraktion eine neue Anfrage an die Quelle aus – auch wenn sich dort gar nichts verändert hat. Bei vielen gleichzeitigen Nutzer:innen sind das schnell unnötig viele Anfragen.

Besser: Daten einmal beim App-Start laden, ausserhalb der Server-Logik. Alle weiteren Interaktionen arbeiten dann mit dem bereits geladenen Objekt im Speicher – ohne weitere Anfrage an die Quelle:

```r
raw <- load_data()  # einmal beim App-Start

server <- function(input, output, session) {
  observeEvent(input$lookup_btn, {
    data <- raw |> filter(...)  # keine erneute Anfrage
  })
}
```

Nutzer:innen sehen dabei den Datenstand zum Zeitpunkt des App-Starts – für die meisten Forschungs-Dashboards reicht das völlig aus. Bei sehr grossem Nutzer:innenkreis oder Daten, die häufiger aktualisiert werden müssen, gibt es weitergehende Caching-Optionen; meldet euch dazu einfach beim ZHAW Services Forschungsdaten Team.

### Nur die benötigten Daten abrufen

Statt eines Vollexports lohnt es sich, die Abfrage gezielt zu konfigurieren – z. B. nur bestimmte Felder oder Datensätze laden, statt alles herunterzuladen und erst in der App zu filtern. Für REDCap siehe [REDCap-Integration](redcap.md).

### Checkliste vor dem Deployment

- Werden die Daten ausserhalb der Server-Funktion geladen (einmal beim App-Start)?
- Wird nur ein Teilausschnitt der Quelle abgerufen, statt eines Vollexports?
- Sind Zugangsdaten (API-Tokens etc.) nur als Umgebungsvariable hinterlegt – nie im Code oder in einer committeten Datei?
