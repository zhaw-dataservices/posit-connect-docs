# Posit Connect – Dokumentation

Documentation site for Posit Connect at ZHAW, built with [MkDocs](https://www.mkdocs.org/) and the [Material theme](https://squidfunk.github.io/mkdocs-material/).

Published at: https://zhaw-dataservices.github.io/posit-connect-docs/

## Structure

```
docs/
  index.md               # Home (German)
  index.en.md            # Home (English)
  erste-schritte.md      # Getting Started (German)
  erste-schritte.en.md   # Getting Started (English)
  assets/
    zhaw-logo.svg          # ZHAW logo
  stylesheets/
    extra.css              # ZHAW branding overrides
mkdocs.yml
.github/workflows/deploy.yml
```

## Deployment

Pushing to `main` triggers a GitHub Actions workflow that builds the site and deploys it to the `gh-pages` branch automatically.
