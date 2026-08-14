# Welcome

This page documents the ZHAW service [“Interactive Visualization of Research Data”](https://servicedesk.zhaw.ch/tas/public/ssp/content/detail/service?unid=e3c1b43fa13643cdaed8aa5451e49568&from=df5dab14-4041-45d0-9729-c32c78acfca1), provided by ZHAW Services Forschungsdaten.

## About This Service

The service includes a local infrastructure (servers and data hosted at ZHAW) as well as corresponding support services that enable researchers to create interactive visualizations of their research data. The idea is to make research data easily accessible and engaging in the spirit of Open Science. Experience has shown that the opportunity to explore data interactively generates strong interest and creates additional visibility for research topics.

At the core of the service are interactive dashboards: small web applications that allow users to explore, filter, and visualize data through charts and other graphical representations. Such dashboards are typically developed using Shiny (for R) or Streamlit (for Python). The creation of interactive reports with Quarto (R / Python) is also supported. If you have no idea what is being discussed, take a look at [Shiny Basics](learn/shiny-basics.en.md)/[Streamlit Basics](learn/streamlit-basics.en.md).

The product "Posit Connect" from Posit Software is used as the hosting and publishing platform. The configuration and publishing of visualizations are handled by the team of ZHAW Services Forschungsdaten.

To use the service, data storage must be defined and code stored on GitHub. It is also important to comply with data protection requirements, web accessibility standards (WCAG), and corporate design guidelines. We therefore recommend using our templates as the basis for developing visualizations. <strong>To ensure efficient development, please read this documentation carefully.</strong> We recommend that first-time users request a brief introduction to the service.

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

You then complete the [SSP form](https://servicedesk.zhaw.ch/tas/public/ssp/content/serviceflow?unid=330c213f-12fa-44e4-ad9b-07abb40fa513) in the Self Service Portal, which includes a usage assessment if needed.

### Step 2: Develop Your App

You develop your app, ideally using our templates, available at [github.zhaw.ch/service-research-data](https://github.zhaw.ch/service-research-data). We primarily support Shiny, Streamlit, and Quarto. See [Develop Your App](app-entwickeln/general.md). <!--Important info, tips & tricks are under [Best Practices](app-entwickeln/best-practices.md).-->We especially recommend using Git, ideally via [github.zhaw.ch](https://github.zhaw.ch)—it also enables collaboration with other researchers.

### Step 3: Share Your Code

Once you are ready to publish your app, the final source code is made available on [github.zhaw.ch/service-research-data](https://github.zhaw.ch/service-research-data) so that Posit Connect can read the app directly from there (GitHub.com only as an exception, depending on the data context). See [Share Your Code](code-teilen/github-zhaw.md).

### Step 4: Review

We review the code and the app—covering best practices, corporate design, data protection and minimisation, metadata and project assignment, access rights, and end of life. If changes are needed, the app goes back for rework; otherwise, publishing follows. See [Publishing](deployment.md).

### Step 5: Publishing

After a successful review, we handle the publishing. The app goes live at a chosen URL following the pattern `exploredata.zhaw.ch/app-name`. Access rights are then configured, and later updates follow as needed. See [Publishing](deployment.md).

## Contact

This service is operated by ZHAW Services Research Data.

**Contact:** [researchdata@zhaw.ch](mailto:researchdata@zhaw.ch)
