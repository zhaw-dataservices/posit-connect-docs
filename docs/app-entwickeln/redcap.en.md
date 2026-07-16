# Loading Data from REDCap

Apps on Posit Connect can read data directly from [ZHAW-REDCap](https://redcap.zhaw.ch/). This page describes how to set this up.

## Example Repositories

We provide two example repositories showing how to pull records via the REDCap API and use them as a data frame:

- [redcap-api-r](https://github.zhaw.ch/service-research-data/redcap-api-r)—for R
- [redcap-api-py](https://github.zhaw.ch/service-research-data/redcap-api-py)—for Python

Both are primarily meant as a guide for working locally (e.g. in RStudio or Jupyter), but they double as a template for loading data for a dashboard that will later be published to Posit Connect—see [Working Locally & Posit Connect](#working-locally-posit-connect) below.

## Prerequisites

You need a REDCap API token for your project. Find it in REDCap under **Applications > API**; if none exists yet, request one from a REDCap admin.

## Connecting from R

See [redcap-api-r](https://github.zhaw.ch/service-research-data/redcap-api-r): a minimal R script with a `get_redcap_data()` function that returns REDCap records as a data frame—including instructions on regenerating the export via the API Playground whenever the REDCap project changes.

## Connecting from Python

See [redcap-api-py](https://github.zhaw.ch/service-research-data/redcap-api-py): the same approach for Python (`get_redcap_data()`, returning a pandas DataFrame), including a Jupyter notebook for inspecting the data.

## Working Locally & Posit Connect

Both repositories are primarily meant for pulling and working with data locally on your own device—via a local `secrets.yml` that is never committed. We recommend the same pattern for dashboards that will later be published to Posit Connect: there, `get_redcap_data()` automatically reads credentials from environment variables (the app's **Vars** tab on Posit Connect) instead of the file, with no code changes required.

## Storing API Tokens Securely

Tokens never belong in code or in the repository. Locally: `config/secrets.yml` (gitignored). On Posit Connect: an environment variable under the **Vars** tab. See the READMEs of both repositories above for details.