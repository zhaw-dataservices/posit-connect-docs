# Welcome

This page documents the ZHAW service “Interactive Data Visualisation”—the central hosting infrastructure for interactive research data visualisations.

!!! note "Note"
    This documentation is still under construction and is being updated on an ongoing basis. Some content may be missing or subject to change.

## About This Service

Since June 2026, ZHAW has been running a platform for interactive data visualisations based on Posit Connect. It lets researchers make their data interactively explorable—tailored to a wide range of audiences.

At its core are interactive dashboards: small web applications in which users can explore, filter, and visualise the data themselves in charts, without installing anything. Such dashboards are usually built with Shiny (for R) or Streamlit (for Python). We are also happy to host interactive reports and websites created with Quarto (R / Python).

Posit Connect can publish much more in principle; for a full overview, see the [Posit Connect product page](https://posit.co/products/enterprise/connect). Our best practices and support are initially focused on Shiny and Streamlit.

## Process at a Glance

Getting from an idea to a published app takes five steps:

<div class="process-diagram-wrapper">
--8<-- "assets/ablauf.en.svg"
</div>

Steps 1 and 2 can be completed independently and in any order.

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

## Contact

This service is operated by ZHAW Services Research Data.

**Contact:** [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch)
