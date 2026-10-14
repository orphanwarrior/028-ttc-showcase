# Five engineering decisions

These notes explain the current implementation. The alternatives are comparisons used to explain the trade-offs, not a claim that every option was built.

## 1. A passing review belongs to one draft

A model might review revision 1 successfully, then revision 2 changes the wording. A boolean such as `reviewPassed` would be unsafe if it survived that edit.

TTC attaches checks and review results to a draft revision and SHA-256. The runtime only accepts a result for the current draft. Human confirmation then creates the version that later stages may use.

A version ID alone is convenient, but checking the content identity also catches mismatched records. The cost is more invalidation logic and repeated review after edits. It establishes which text was reviewed, not whether the review was professionally correct.

**Verified:** the Agent and three-stage suites reject stale reports and mismatched bindings.

## 2. Check inputs again when publishing

A request can start with confirmed claims and finish after those claims have changed. Checking inputs only at the start leaves that race open.

Holding a database transaction for the whole model call would be a poor fit for long requests. Instead, TTC captures input identities, runs the model outside the publication transaction, then checks the confirmed inputs and expected previous current version again before publishing.

This can leave paid work marked stale. I prefer that to silently making outdated work current. Drawing semantics are tracked separately from layout/render state, so a verified layout-only change does not force a specification rewrite.

**Verified:** the three-stage suite covers input changes, publication conflicts and retained state. This design has not been evaluated as a distributed execution system.

## 3. Starting a run should not replace working content

Replacing the current version as soon as generation starts makes a failed request unnecessarily destructive.

New drawing/specification runs therefore begin without current authority. Draft checkpoints and calls are saved as the run progresses. Only successful, validated publication switches the current version in a short transaction.

The trade-off is additional records and storage. The interface also has to show whether a user is looking at a failed attempt or usable work. Supported continuation can reuse saved drafts; it does not resume arbitrary model execution from the exact point of interruption.

**Verified:** Agent and three-stage tests preserve earlier work after generation/review failures.

## 4. Put a limit on repair loops

A model can repeatedly try to fix an artifact without reaching a valid result. One-shot generation is simpler, but cannot handle even small recoverable errors.

TTC uses a bounded runtime with stage-specific operations: inspect evidence, update the draft, run checks and request an independent review. The artifact defaults allow six model calls, 90,000 reported tokens and 240 seconds. Blocking facts, cancellation or budget exhaustion stop the run and retain its state.

These are application budgets, not billing guarantees. Usage can be absent or reported after a call has already exceeded an estimate. Unknown calls remain explicitly unknown. The HTTP adapter also avoids automatic full-call retries; the user decides whether to start another attempt.

**Verified:** runtime/provider suites cover budget stops, cancellation, incomplete responses and failure accounting. No drafting-quality claim follows from those tests.

## 5. Keep writing guidance separate from execution rules

Domain guidance changes with the patent field and drafting stage. Execution rules decide which tools can run, what counts as a valid review and when an output can become current. Putting both in one large prompt makes that distinction hard to inspect.

TTC assembles the relevant domain/stage/application-type guidance and reads versioned administrator overrides where available. Code enforces budgets, output contracts and publication checks. Runs record provenance and rule fingerprints.

This adds assembly paths to maintain, but lets professional guidance change without confusing it with a runtime deployment. Rule versioning provides traceability; it does not prove that a new rule improves output.

**Evidence:** the loader/override paths were inspected. Dedicated rule-file tests exist but were not rerun in this portfolio pass. Proprietary rule text is not included here.
