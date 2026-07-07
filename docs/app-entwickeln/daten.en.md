# Data Minimisation & Data Sources

Apps on Posit Connect should only use the data that is actually needed. This page shows where the raw data for your dashboard should come from and what to avoid.

## Where Does the Raw Data Come From?

The recommended path depends on the type of data.

### Public Research Data

Ideally, store the data in an ORD repository (Open Research Data). The app reads the data directly from there—data and code stay separate and independently versioned.

<!-- TODO: List recommended ORD repositories (e.g. Zenodo, OSF, BORIS) -->

### Confidential or Sensitive Data

For confidential or personal data, we recommend REDCap. Apps can read data directly from REDCap. See [REDCap Integration](redcap.md) for a dedicated guide.

### Other Institutional Sources

!!! note "Under Review"
    Internal databases and SharePoint are being considered as possible sources, but the connection to Posit Connect hasn't been tested yet. These and other institutional options are under internal review—details to follow.

### Not Recommended: Data Bundled in the Repository

Placing a data file (e.g. `.RData` or `.csv`) directly in the code repository is technically possible but not a recommended pattern: the data isn't versioned independently from the code, every update requires a redeploy, and there's a risk of accidentally committing sensitive data. If unavoidable, use this only as a last resort for very small, static, non-sensitive datasets.

<!-- TODO: Write that it will be ignored and it's not safe practice anyways>

## Principle: Data Minimisation

<!-- TODO: Explain the principle and why it matters -->

## Loading Data in Your App

<!-- TODO: How to load data—directly from ORD repository, local file, etc. -->

## What Should Not Be on the Server

<!-- TODO: Sensitive data, personal data, what is not permitted -->
