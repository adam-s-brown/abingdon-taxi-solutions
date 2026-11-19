# Abingdon Taxi Solutions

For this tutorial, **we are Abingdon Taxi Solutions**, an AI-first taxi
services company. Our customers want better driver, manager, and owner
experiences, and they want to know how we use AI to provide them.

This is a **Git evidence repository**, not a runnable taxi application.
Read [our service description](service/experience.md), then follow the
[AI TrustBOM tutorial](https://aitrustbom.com/)
to introduce a proposed Gemini dependency, model configuration, and
MCP connection one tracked change at a time. The scanner produces
draft, cited evidence, not proof of an operational deployment.

```powershell
git clone https://github.com/resolveinterim/abingdon-taxi-solutions.git
cd abingdon-taxi-solutions
trustbom init
trustbom scan
```

Install the CLI with the installer script (`install.sh` or `install.ps1` from the
release page, see the [CLI installation reference](../../documentation/guides/installing.md))
or, if you have Node.js, `npm install --global trustbom` (license terms: <https://aitrustbom.com/legal/terms/> or `trustbom license`; privacy policy:
<https://aitrustbom.com/legal/privacy/>). You need Git and the `trustbom` CLI; **no Node.js (installer-script route), Python runtime, API
key, or server** is needed. The `workshop/` inputs are not in scope
until the tutorial copies them to recognized paths. All scenario data
and the customer's [sample RFI](rfi/request.csv) are synthetic; do not
put real employee records or confidential customer questions in this
public repository.

The `workshop/` folder also stages the declarations that resolve the
scanner's `region-unknown` and `subprocessor-undeclared` findings and record
provider data handling (`manual-model-region.example`,
`manual-data-handling.example`, `subprocessors.example` and the synthetic
terms, deletion and agreement notes they reference). Copy them yourself,
rescan, run `trustbom request-approval` on a feature branch and merge it to
the default branch as Trust. There is no script and no prepared approved
branch: the approval is the real command and a real review.

Until an approval is merged to the default branch, `export` and `answer`
**refuse** instead of responding from a draft. Once approved,
`trustbom export` followed by
`trustbom answer --questions rfi\request.csv` produces cited RFI answers.
Unknown and unmatched answers still require Trust review before anything
goes to a customer. `trustbom publish` builds a deployable trust page under
`export/site/` and a buyer runs `trustbom verify export/site` offline.
