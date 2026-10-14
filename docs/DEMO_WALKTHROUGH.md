# TTC walkthrough

These are screenshots of the running application in an isolated local test environment. The disclosure, confirmed versions and artifacts were seeded by the project's synthetic fixture. Model requests use a mock channel.

They show the real interface and state handling, not a recorded end-to-end model run or evidence of drafting quality. No customer material is used.

## Workbench

Cases can be reopened without losing their drafting state.

![Case workbench](../assets/screenshots/workbench.jpg)

## Decide which technical solution to use

The practitioner can edit a proposal, adopt or reject it, and confirm a version before drafting claims. This example contains one adopted solution: an input module connected to an output module.

![Technical solution review](../assets/screenshots/solution-review.jpg)

## Inspect and confirm claims

The current draft, model choice and discussion panel are separate. Discussion does not automatically change the draft.

![Claims workbench](../assets/screenshots/claims.jpg)

## Review the drawing baseline

The electrical example has a real editable diagram artifact, with objects, relationships and a claim mapping. The seeded artifact has no generation-validation report; that absence remains visible in the UI.

![Drawing workbench](../assets/screenshots/drawings.jpg)

Mechanical cases instead have a textual figure/reference baseline. This electrical screenshot should not be taken as evidence of finished mechanical drawings.

## Return to a saved version

The history distinguishes the original model version from a confirmed version. Loading an older version is an explicit action.

![Version history](../assets/screenshots/versions.jpg)

## A supervised demonstration

For a fresh task, use the independently written [synthetic disclosure](../examples/synthetic-case/DISCLOSURE.md). Prepare it as DOCX, then walk through import, solution adoption, claim confirmation, drawing/reference review and specification drafting.

Finish by assembling the final document, completing missing sections and confirming its snapshot before export. The frontend/backend path exists and its backend was regression-tested; the full browser export sequence was not repeated for these captures.

A separate failure demonstration can show a new attempt being rejected while the earlier usable version survives. Mark mock responses clearly and do not present them as real model outcomes.

For a public application requiring no invitation, try [Patent Exam Practice](https://orphanwarrior.github.io/test-web/study.html).
