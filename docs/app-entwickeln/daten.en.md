# Data Sources & Access

Apps on Posit Connect should only use the data that is actually needed. This page shows where the data for your dashboard should live and how to retrieve it as gently as possible.

## Where Is the Data?

The recommended path depends on the type of data.

### Public Research Data

Ideally, store the data in an ORD repository (Open Research Data). The app reads the data directly from there—data and code stay separate and independently versioned. Recommended repositories are, e.g.:

- [Zenodo](https://zenodo.org)—general-purpose repository (CERN), issues DOIs, suitable for almost any file type
- [OSF](https://osf.io)—Open Science Framework, project and data management including versioning
- [BORIS](https://boris.unibe.ch)—Bern Open Repository and Information System

### Confidential or Sensitive Data

For confidential or personal data, we recommend [ZHAW-REDCap](https://redcap.zhaw.ch/). Apps can read data directly from REDCap. See [REDCap Integration](redcap.md) for a dedicated guide.

Special categories of personal data (e.g. health data, ethnicity, religious beliefs) may only be processed if this has been explicitly approved as part of the [Usage Assessment](../nutzungsabklaerung.md).

### Other Institutional Sources

!!! note "Under Review"
    Internal databases and SharePoint are being considered as possible sources, but the connection to Posit Connect hasn't been tested yet. These and other institutional options are under internal review—details to follow.

### Excluded: Data Bundled in the Repository

Placing a data file (e.g. `.RData` or `.csv`) in the code repository goes against several best practices: the data wouldn't be versioned independently from the code, every update would require a redeploy, and there'd be a risk of accidentally committing sensitive data. The [shiny-base](https://github.zhaw.ch/service-research-data/shiny-base) template *(work in progress, not yet public)* enforces this technically too: it already excludes `.RData` and `.csv` files via `.gitignore`, so they're never committed in the first place. Load your data from one of the sources listed above instead (ORD repository, REDCap, institutional source).

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

### Fetch Only What You Need

Rather than a full export, it's worth configuring the request narrowly—e.g. loading only specific fields or records instead of downloading everything and filtering within the app. For REDCap, see [REDCap Integration](redcap.md).

### Checklist Before Deployment

- Is the data loaded outside the server function (once, at app start)?
- Is only a subset of the source retrieved, rather than a full export?
- Are credentials (API tokens, etc.) stored only as environment variables—never in code or in a committed file?
