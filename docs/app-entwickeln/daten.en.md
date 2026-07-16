# Data Sources & Access

Apps on Posit Connect should only use the data that is actually needed. This page shows where the data for your dashboard should live and how to retrieve it as gently as possible.

## Where Is the Data?

### Dataset in the App Bundle (recommended)

For most research dashboards, we recommend—in line with [Posit's best practice](https://solutions.posit.co/connections/deploying-data/)—bundling the dataset directly as part of the app repository, for example as a `.csv` file in the `data/` folder.
The dataset should contain only the variables actually needed for the visualization. Sensitive variables—even ones that aren't displayed directly—should not be included.

#### Structure

[Tidy format](https://r4ds.had.co.nz/tidy-data.html) (one observation per row, one variable per column) makes it easier to work with most R visualization packages. Using correct data types (e.g. `Date` instead of `character` for dates) saves memory and simplifies the code.

| species          | region       | count | year |
|------------------|--------------|-------|------|
| Quercus robur    | Zurich       | 42    | 2023 |
| Fagus sylvatica  | Bern         | 17    | 2023 |
| Pinus sylvestris | Graubünden   | 89    | 2023 |
| Acer platanoides | Zurich       | 31    | 2022 |
| Betula pendula   | St. Gallen   | 24    | 2022 |

#### Size

There is no fixed threshold. If the dataset already takes noticeably long to load with `read.csv()` in local testing, it's probably too large for the app bundle—reach out to the ZSF team in that case.

*Limitation:* Every data update requires a redeploy of the app. If the data changes much more frequently than the code, reach out to the ZSF team—we'll work out together whether a different approach makes more sense.

### Confidential or Sensitive Data

For confidential or personal data, we recommend [ZHAW-REDCap](https://redcap.zhaw.ch/). See [REDCap Integration](redcap.md) for a step-by-step guide.

Special categories of personal data may only be processed if this has been explicitly approved as part of the [Usage Assessment](../nutzungsabklaerung.md).

### Other Data Sources

If you want to pull data from a database or another external system, reach out to the ZSF team—we'll work through the options together on a case-by-case basis.

## Principle: Data Minimisation

Apps on Posit Connect should access their data source as rarely and as narrowly as possible—whether that's REDCap, an ORD repository, or an institutional source. The source sits downstream of Posit Connect and shouldn't be burdened unnecessarily.

### The Most Common Mistake: Reloading Data on Every Interaction

If the data request sits inside a reactive function (e.g. `observeEvent()`), every user interaction triggers a new request to the source—even if nothing has changed there. With many concurrent users, that quickly adds up to an unnecessary number of requests.

Better: load the data once when the app starts, outside the server logic. Every subsequent interaction then works with the already-loaded object in memory—no further request to the source:

```r
raw <- load_data()  # once, at app start

server <- function(input, output, session) {
  observeEvent(input$lookup_btn, {
    data <- raw |> filter(...)  # no new request
  })
}
```

Users then see the data as of app start—which is entirely sufficient for most research dashboards. For a very large user base, or data that needs to be refreshed more frequently, more advanced caching options exist; just reach out to the ZHAW Services Research Data team.

### Checklist Before Deployment

- Is the data loaded outside the server function (once, at app start)?
- Are credentials (API tokens, etc.) stored only as environment variables—never in code or in a committed file?
