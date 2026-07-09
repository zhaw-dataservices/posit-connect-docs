# Process Overview

This page describes the full process—from the preliminary assessment through app development to publication on Posit Connect.

## Process Summary

--8<-- "assets/ablauf.en.svg"

Steps 1 and 2 can be completed independently and in any order.

## Detailed Description

### Step 1: Preliminary Assessment

It all starts with initial contact, recommended for first-time users: ideally an email to [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch) to discuss the process. You then complete the [SSP form](https://servicedesk.zhaw.ch/tas/public/ssp/content/serviceflow?unid=330c213f-12fa-44e4-ad9b-07abb40fa513) in the Self Service Portal (SSP), which also includes a usage assessment if needed (data protection, resources, security). See [Usage Assessment](nutzungsabklaerung.md).

### Step 2: Develop Your App

You develop your app either using our templates or by integrating an existing one. We primarily support Shiny, Streamlit, and Quarto; this includes best practices, corporate design, and generating the `manifest.json`. See [Develop Your App](app-entwickeln/template.md). Important info, tips & tricks are under [Best Practices](app-entwickeln/best-practices.md).

### Step 3: Share Your Code

Your source code is published in a repository on github.zhaw.ch so that Posit Connect can read the app directly from there (GitHub.com only as an exception, depending on the data context). Git also makes collaboration with other researchers possible. See [Share Your Code](code-teilen/github-zhaw.md).

### Step 4: Review

We review the code and the app—covering best practices, corporate design, data protection and minimisation, metadata and project assignment, access rights, and end of life. If changes are needed, the app goes back for rework; otherwise, deployment follows. See [Deployment](deployment.md).

### Step 5: Deployment

After a successful review, we handle the deployment on Posit Connect. The app goes live at a chosen URL following the pattern `exploredata.zhaw.ch/app-name`. Access rights are then configured, and later updates follow as needed. See [Deployment](deployment.md).
