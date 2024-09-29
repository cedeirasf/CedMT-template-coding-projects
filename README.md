# coding-projects-template

<h4 align="center">Template to coding projects that requires a conventional workflow</h4>

&nbsp;

<div align="center">

<a href="./LICENSE">
	<img alt="License: MIT" src="https://img.shields.io/badge/License-Private-yellow.svg">
</a>
<a href="./CODE_OF_CONDUCT.md">
	<img alt="Contributor covenant: 2.1" src="https://img.shields.io/badge/Contributor%20Covenant-2.1-4baaaa.svg">
</a>
<a href="https://semver.org/">
	<img alt="Semantic Versioning: 2.0.0" src="https://img.shields.io/badge/Semantic--Versioning-2.0.0-a05f79?logo=semantic-release&logoColor=f97ff0">
</a>

[![Tests](https://github.com/mauroalderete/coding-projects-template/actions/workflows/tests.yml/badge.svg)](https://github.com/mauroalderete/coding-projects-template/actions/workflows/tests.yml)
[![CodeQL](https://github.com/mauroalderete/coding-projects-template/actions/workflows/codeql-analysis.yml/badge.svg)](https://github.com/mauroalderete/coding-projects-template/actions/workflows/codeql-analysis.yml)

<a href="./issues/new?assignees=&labels=bug%2Clifecycle%2Fneeds-triage&projects=mauroalderete%2F20&template=1-bug-report.yml&title=...+is+broken">Bug report</a>
·
<a href="./issues/new?assignees=&labels=enhancement%2Clifecycle%2Fneeds-triage&projects=mauroalderete%2F20&template=2-feature-request.yml&title=As+a+%5Btype+of+user%5D%2C+I+want+%5Ba+goal%5D+so+that+%5Bbenefit%5D">Feature Request</a>
·
<a href="./issues/new?assignees=&labels=help+wanted%2Clifecycle%2Fneeds-triage&projects=mauroalderete%2F20&template=3-help-wanted.yml&title=I+need+help+with...">Help Wanted</a>

<a href="https://twitter.com/intent/tweet?text=👋%20Check%20this%20amazing%20repo%20https://github.com/mauroalderete/coding-projects-template,%20created%20by%20@_mauroalderete%0A%0A%23DEVCommunity%20%23100DaysOfCode%20%23Golang%20%23gcode">
	<img src="https://img.shields.io/twitter/url?label=Share%20on%20Twitter&style=social&url=https%3A%2F%2Fgithub.com%2Fatapas%2Fmodel-repo">
</a>

</div>

&nbsp;
# :wave: Introducing `coding-projects-templates`
This repository template contains the essential elements used in various projects to many stacks.

- Includes workflows to handle labeling, versioning, testing, release and deployment.
- Contains a private license, a basic contributing redaction, and a covenant code of conduct.
- Implements a definition to generate release notes.
- Defines templates to the three issues types (bug, features, help wanted) and a pull request template.
- Additional prepare a dependabot script.
- Schedule a CodeQL Analysis.
- And include CODEOWNERS

> Many of the configuration files in this repository are not working yet. Just consist of a sample definition of the configuration. You may adapt these files depending on your objectives. You should pay attention to subsequent indications to know how you do it.

# :fire: How to use this template

To use this template, click the button **Use this template** shown in the upper section on [root of repository](https://github.com/mauroalderete/coding-projects-template), then create a new repository.

Another way is initing the process of creating a new repository and selecting this template in the upper section.

# :building_construction: How to Set up

This template contains many files. A lot of them require special attention.

## Code of conduct

`/CODE_OF_CONDUCT.md`

This code is based on the covenant code. He is only required to specify an email address to the community to send his messages. Now, this email is alderete.mauro@gmail.com.

## License

`/LICENSE`

This license is a private personal license redacted by chatGPT. This is only an example. I recommend changing this license to other than to be attached better to your needs.
You can replace it with any Open License offered by GitHub, too.

## Gitignore

`/.gitignore`

This file is empty. Replace the content with what you think is more convenient.

## Workflows

### CodeQL

`/.github/workflows/codeql-analysis.yml`

This file enables the CodeQL service provided by GitHub. You should provide a language supported.
If your project is not supported, I recommend removing this yaml file.

### Tests

`/.github/workflows/tests.yml`

This workflow is the most complex to configure. This depends highly on your stack and environment.
In some cases, you will probably need to split this workflow into unit and integration tests.
It only contains some steps with a simple message showing you the commands to configure a node test environment.

I recommend you study your case carefully.

### Labeling

`/.github/workflows/labeling.yml`

Include a PR labeling workflow caller. It consumes the reusable workflows stored in [mauroalderete/workflows](https://github.com/mauroalderete/workflows).

### Liberation

`/.github/workflows/liberation.yml`

The versioning workflow contains a caller to the reusable workflow stored in [mauroalderete/workflows](https://github.com/mauroalderete/workflows).

The `liberation` include a simple versioning and release without adds other artifacts. Is ideal to start, but in the most uses cases you would create your unique liberation flow.

We recommend you look how the [reusable liberation workflow works](https://github.com/mauroalderete/workflows/blob/main/.github/workflows/liberation.yml). You can find two reusables workflows that allows configure your liberation resources easily.

### Project Automation

Contains a `project-automation` caller workflow to perform an issue status managment on project beta.

For this workflows works correctly you need configure the secret `GH_PROJECT_AUTOMATION` with a **PAT token in classic mode**.

The PAT token must have permissions for:

- [x] repo
  - [x] repo:status
  - [x] repo_deployment
  - [x] public_repo
  - [x] repo:invite
  - [x] security_events
- [x] admin:org
  - [x] write:org
  - [x] read:org
  - [x] manage_runners:org
- [x] project
  - [x] read:project
