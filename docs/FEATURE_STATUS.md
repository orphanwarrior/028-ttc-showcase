# Feature status

Status as of 2026-10-14. **Implemented** means an execution path was inspected; testing scope is stated separately. **Partial** identifies a usable subset or exposure limitation. **Planned** is not an implemented feature.

| Feature | Status | Technical notes | Known limitations / evidence |
| --- | --- | --- | --- |
| DOCX text and image extraction | Implemented | Mammoth, ZIP/XML inspection, file/hash limits | Inspected; synthetic imports exercised by selected suites |
| Technical solution proposal and confirmation | Implemented | Stage-specific Agent, adopt/reject and confirmed snapshot | Solution Agent suite passed; professional quality not benchmarked |
| Claims Agent and human confirmation | Implemented | Version-bound checks/review and draft revisions | Claims Agent suite passed |
| Drawing / reference generation | Implemented | Default artifact Agent; domain-specific output contracts | Three-stage and artifact suites passed |
| Finished mechanical drawings | Planned | Current mechanical output is textual figure/reference guidance | Do not present mechanical reference text as completed drawings |
| Editable electrical diagrams | Implemented | Draw.io artifacts, preview and artifact versions | Synthetic three-stage coverage; browser preview inspected |
| Specification Agent and run history | Implemented | Confirmed inputs, checks/review and guarded publication | Three-stage suite passed; quality requires practitioner review |
| Version-bound implementation discussion | Implemented | Suggestion preview and explicit application | Inspected; discussion suite not rerun in this pass |
| Immutable confirmation snapshots | Implemented | Version identities, timestamps and SHA-256 | Snapshot/three-stage tests passed |
| Dependency invalidation | Implemented | Source, solution, claims and drawing semantics | Workbench/three-stage coverage; layout handled separately |
| Failed-run preservation | Implemented | Draft checkpoints and delayed current switching | Agent and three-stage coverage |
| Provider abstraction / streaming / cancel | Implemented | Native HTTP; Chat Completions and Responses | Provider regression passed; not a distributed scheduler |
| Image understanding and confirmation | Partial | Vision channel and configurable manual/automatic mode | Default is automatic; real vision quality not evaluated here |
| Account and case isolation | Implemented | Sessions, case ownership and administrator access | SaaS suite passed; not organization tenancy |
| Model usage and run records | Implemented | Per-run calls, reported usage and unknown-call accounting | Agent suites cover failures and accounting |
| Administrator rule-file management | Implemented | Database overrides and version history | Inspected; dedicated suite not rerun |
| Final acceptance / DOCX export | Implemented | Workbench panel, assembly, completeness checks and accepted snapshot | SaaS backend test passed; fresh browser verification pending |
| Complete case-dossier ZIP export | Implemented | Administrator export, manifest and cleanup | Inspected; dedicated dossier suite not rerun |
| Distributed jobs and horizontal scaling | Planned | Current execution uses application process and SQLite | No queue framework or demonstrated scale |
| Professional quality / speed benchmark | Planned | Requires defined dataset and practitioner rubric | No verified quality percentage or time savings |
| Public self-service TTC demo | Planned | Current test environment is invitation-based | No public login or demo account is published |

Selected regression suites and their limits are documented in [VALIDATION.md](VALIDATION.md).
