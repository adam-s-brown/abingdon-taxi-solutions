# Abingdon Taxi Solutions

For this tutorial, **we are Abingdon Taxi Solutions**, an AI-first taxi
services company. Our customers want better driver, manager, and owner
experiences, and they want to know how we use AI to provide them.

This is a **Git evidence repository**, not a runnable taxi application.
Read [our service description](service/experience.md), then follow the
[AI TrustBOM tutorial](https://aitrustbom.com/). Our rider support already
uses an OpenAI model (`requirements.txt` and `config/models.yaml`). The
tutorial adds a Gemini model for drivers in a pull request, then an MCP
connection, one tracked change at a time. The scanner produces draft, cited
evidence, not proof of an operational deployment.

Fork this repository on GitHub, clone your fork, and run:

```sh
cd abingdon-taxi-solutions
trustbom scan
```

Install the CLI with the installer script (`install.sh` or `install.ps1` from the
release page, see the [CLI installation reference](https://aitrustbom.com/install/))
or, if you have Node.js, `npm install --global trustbom` (license terms: <https://aitrustbom.com/legal/terms/> or `trustbom license`; privacy policy:
<https://aitrustbom.com/legal/privacy/>). You need Git and the `trustbom` CLI; **no Node.js (installer-script route), Python runtime, API
key, or server** is needed. The `workshop/` files are not in scope until
the tutorial copies them to recognized paths. All scenario data and the
customer's [sample RFI](rfi/request.csv) are synthetic; do not put real
employee records or confidential customer questions in this public
repository.

The `workshop/` folder stages the AI the tutorial adds
(`gemini-requirements.example`, `models.example`, `mcp-config.example`) and
the declarations that fill the gaps the pull-request check reports
(`manual.example`, `subprocessors.example` and the synthetic provider
notes they reference). There is no script and no prepared approved branch:
the sign-off is a real `trustbom propose` and a real pull-request review.

Until a sign-off is merged to the default branch, `export` and `answer`
**refuse** instead of responding from a draft. Once approved,
`trustbom export` followed by
`trustbom answer --questions rfi/request.csv` produces cited RFI answers.
Unknown and unmatched answers still require Trust review before anything
goes to a customer. `trustbom publish` builds a deployable trust page under
`export/site/` and a buyer runs `trustbom verify export/site` offline.
