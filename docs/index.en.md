# Welcome

This page documents the ZHAW service “Interactive Data Visualisation”—the central hosting infrastructure for interactive research data visualisations.

!!! note "Note"
    This documentation is still under construction and is being updated on an ongoing basis. Some content may be missing or subject to change.

## About This Service

Since June 2026, ZHAW has been running a platform for interactive data visualisations based on Posit Connect. It lets researchers make their data interactively explorable—tailored to a wide range of audiences.

At its core are interactive dashboards: small web applications in which users can explore, filter, and visualise the data themselves in charts, without installing anything. Such dashboards are usually built with Shiny (for R) or Streamlit (for Python). We are also happy to host interactive reports and websites created with Quarto (R / Python).

Posit Connect can publish much more in principle; for a full overview, see the [Posit Connect product page](https://posit.co/products/enterprise/connect). Our best practices and support are initially focused on Shiny and Streamlit.

## Process

Getting from an idea to a published app takes five steps:

<div class="process-diagram-wrapper">
--8<-- "assets/ablauf.en.svg"
</div>

Steps 1 and 2 can be completed independently and in any order.

### Step 1: Preliminary Assessment

It all starts with initial contact, recommended for first-time users: ideally an email to [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch) to discuss the concept and process. It helps to come prepared with answers to the following questions:

- What is the goal and concept of the data visualisation?
- What functionality should the visualisation have?
- Which programming language and libraries should be used?
- What does the data look like, and how is it classified in terms of confidentiality?
- Where will the data be stored?

We will also cover code development and collaboration, app registration, any required usage assessment, and agree on the next steps and timeline.

You then complete the [SSP form](https://servicedesk.zhaw.ch/tas/public/ssp/content/serviceflow?unid=330c213f-12fa-44e4-ad9b-07abb40fa513) in the Self Service Portal, which includes a usage assessment if needed. See [Usage Assessment](nutzungsabklaerung.md).

### Step 2: Develop Your App

You develop your app, ideally using our templates, available at [github.zhaw.ch/service-research-data](https://github.zhaw.ch/service-research-data). We primarily support Shiny, Streamlit, and Quarto. See [Develop Your App](app-entwickeln/template.md). Important info, tips & tricks are under [Best Practices](app-entwickeln/best-practices.md). We especially recommend using Git, ideally via [github.zhaw.ch](https://github.zhaw.ch)—it also enables collaboration with other researchers.

### Step 3: Share Your Code

Once you are ready to publish your app, the final source code is made available on [github.zhaw.ch/service-research-data](https://github.zhaw.ch/service-research-data) so that Posit Connect can read the app directly from there (GitHub.com only as an exception, depending on the data context). See [Share Your Code](code-teilen/github-zhaw.md).

### Step 4: Review

We review the code and the app—covering best practices, corporate design, data protection and minimisation, metadata and project assignment, access rights, and end of life. If changes are needed, the app goes back for rework; otherwise, publishing follows. See [Publishing](deployment.md).

### Step 5: Publishing

After a successful review, we handle the publishing to Posit Connect. The app goes live at a chosen URL following the pattern `exploredata.zhaw.ch/app-name`. Access rights are then configured, and later updates follow as needed. See [Publishing](deployment.md).

## Contact

This service is operated by ZHAW Services Research Data.

**Contact:** [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch)
