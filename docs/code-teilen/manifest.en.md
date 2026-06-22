# Creating manifest.json

Posit Connect reads apps directly from GitHub. A `manifest.json` file is required—it describes the app and its dependencies.

## What Is manifest.json?

<!-- TODO: Brief explanation of what the file contains and why Posit Connect needs it -->

## For Shiny Apps (R)

The template includes a script `write_manifest.R`. Run it once:

```r
source("write_manifest.R")
```

The generated `manifest.json` must be committed to the repository.

<!-- TODO: Details, common errors -->

## For Streamlit Apps (Python)

<!-- TODO: write_manifest.py—coming once the Streamlit template is available -->

## Keeping manifest.json Up to Date

When dependencies change, `manifest.json` must be regenerated and committed.

<!-- TODO: Note on when an update is needed -->
