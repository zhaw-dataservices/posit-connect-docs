# Datenquellen & Datenzugriff

Apps auf Posit Connect sollen nur die Daten verwenden, die tatsächlich benötigt werden. Diese Seite zeigt, wo die Daten für dein Dashboard liegen sollten und wie sie möglichst schonend abgerufen werden.

## Wo liegen die Daten?

### Datensatz im App-Bundle (empfohlen)

Für die meisten Forschungs-Dashboards empfehlen wir – in Übereinstimmung mit [Posits Best Practice](https://solutions.posit.co/connections/deploying-data/) – den Datensatz direkt als Teil des App-Repositoriums bereitzustellen, z. B. als `.csv`-Datei im `data/`-Ordner.
In den Datensatz gehören nur die Variablen, die für die Visualisierung tatsächlich benötigt werden. Sensible Variablen – auch solche, die nicht direkt angezeigt werden – sollten nicht enthalten sein.

#### Struktur

[Tidy-Format](https://r4ds.had.co.nz/tidy-data.html) (eine Beobachtung pro Zeile, eine Variable pro Spalte) erleichtert die Arbeit mit den meisten R-Visualisierungs-Packages. Korrekte Datentypen (z. B. `Date` statt `character` für Datumsangaben) sparen Speicher und vereinfachen den Code.

| art              | region       | anzahl | jahr |
|------------------|--------------|--------|------|
| Quercus robur    | Zürich       | 42     | 2023 |
| Fagus sylvatica  | Bern         | 17     | 2023 |
| Pinus sylvestris | Graubünden   | 89     | 2023 |
| Acer platanoides | Zürich       | 31     | 2022 |
| Betula pendula   | St. Gallen   | 24     | 2022 |

#### Grösse

Es gibt keinen fixen Grenzwert. Wenn der Datensatz beim lokalen Testen mit `read.csv()` bereits spürbar lange lädt, ist er wahrscheinlich zu gross für das App-Bundle – meldet euch in dem Fall beim ZSF-Team.

*Einschränkung:* Bei jeder Datenaktualisierung muss die App neu deployed werden. Wenn sich die Daten deutlich häufiger ändern als der Code, melde dich beim ZSF-Team – wir prüfen gemeinsam, ob ein anderer Ansatz sinnvoller ist.

### Vertrauliche oder besonders schützenswerte Daten

Sind die Daten vertraulich oder personenbezogen, empfehlen wir [ZHAW-REDCap](https://redcap.zhaw.ch/). Eine Schritt-für-Schritt-Anleitung zur Anbindung findet sich unter [REDCap-Integration](redcap.md).

Besonders schützenswerte Personendaten dürfen nur verarbeitet werden, wenn dies im Rahmen der [Nutzungsabklärung](../nutzungsabklaerung.md) explizit freigegeben wurde.

### Andere Datenquellen

Wer Daten aus einer eigenen Datenbank oder einer anderen externen Quelle beziehen möchte, ist eingeladen, sich beim ZSF-Team zu melden – wir prüfen die Anbindung je nach Fall gemeinsam.

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

### Checkliste vor dem Deployment

- Werden die Daten ausserhalb der Server-Funktion geladen (einmal beim App-Start)?
- Sind Zugangsdaten (API-Tokens etc.) nur als Umgebungsvariable hinterlegt – nie im Code oder in einer committeten Datei?
