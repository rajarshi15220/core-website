# Qlik Core Website

[![CircleCI](https://circleci.com/gh/qlik-oss/core-website.svg?style=svg)](https://circleci.com/gh/qlik-oss/core-website)

This repository contains sources to the Qlik Core end-user documentation.

Documentation is primarily represented as markdown files and images.
Markdown files are organized in the same way as the generated site is organized.

[MkDocs](http://www.mkdocs.org) is used to generate and build the site.
Currently the [mkdocs-material](https://github.com/squidfunk/mkdocs-material) theme is used but this shall be changes
to a theme matches Qlik branding.

For the generated site, visit [core.qlik.com](https://core.qlik.com).

## Prerequisites

To develop and contribute to the Qlik Core documentation, the following must be available on the local machine:

- Docker - [Docker for Windows](https://www.docker.com/docker-windows) or [Docker for Mac](https://www.docker.com/docker-mac)
- Bash - On Windows, Git Bash included in [Git for Windows](https://git-for-windows.github.io/) is recommended

## Serving the Site Locally

To generate and serve the site locally on a developer machine, use the [serve.sh](./serve.sh) Bash script,
in the repository root:

```sh
./serve.sh
```

This makes the generated site available [locally](http://localhost:8000).

Once the site is running locally, modifications to sources can be made and the local web server automatically updates.
No re-build step is needed.

## Building the Site

To build the site for deployment to some external web server, use the [build.sh](./build.sh) Bash script,
in the repository root:

```sh
./build.sh
```

This builds the site contents in the `site/` folder in the repository root.
This folder is an entry in `.gitignore` to avoid undesired pending repo changes.

## Linting the Documentation

For linting the documentation in this repository we use [lint-condo](https://github.com/singapore/lint-condo),
which contains a set of linters for linting a markdown file.
The linting is part of the Circle CI pipeline, but can also be run locally

```sh
./lint.sh
```

The linters that are enabled is configured in [.lint-condo.yaml](./docs/.lint-condo.yaml).
