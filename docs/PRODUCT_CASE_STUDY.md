# Why TTC has review steps

TTC comes from my experience with patent agency work. The starting point is a technical disclosure, but the practitioner still has to decide what the technical solution is, what belongs in the claims, how to explain it, and which details the source actually supports.

A model can help produce text. The product has to make those decisions manageable.

## Break the work into decisions

I separated the workflow into solution review, claims, drawing/reference baselines and specification text. Each stage produces something the practitioner can inspect before moving on.

The solution table is particularly useful as a boundary. A proposal can be adopted or rejected before the system uses it to draft claims. Confirming that table makes the selected interpretation explicit.

Claims need a similar boundary. Once confirmed, their version becomes an input to the drawing stage. A later substantive edit invalidates the dependent work, because keeping a polished but outdated specification would be misleading.

## Give model output a limited role

The model can look back at evidence, revise a candidate and run a separate review. It cannot confirm upstream work or decide that the practitioner has accepted the final document.

This takes more steps than a single generation button. The extra steps are there because the consequences differ: discussing a passage, proposing an edit, applying it and confirming it should not be the same action.

## Keep failures usable

A failed request may still contain useful drafting work and may already have incurred model cost. TTC keeps drafts and call records separately from the current usable version.

That choice also affects the interface: users need to distinguish a failed attempt from an older working version. A new run is not treated as an improvement merely because it is newer.

## Choose a smaller scope where necessary

Electrical cases can use editable block/flow diagrams. Mechanical cases currently receive a figure list and reference-numeral guidance. I treat that as a narrower feature, rather than claiming the system produces finished mechanical drawings.

The same discipline applies to evaluation. Regression tests can verify that a stale result is rejected; they do not establish whether a patent draft is professionally sufficient.

## My role

I own the product requirements, review boundaries and engineering choices. I use AI coding tools for implementation and work through debugging, testing and iteration. I do not claim that every line was written manually.

## What still needs validation

TTC is in invitation-based testing. It needs broader practitioner evaluation using a consistent set of disclosures and review criteria. I have not measured time savings or published user/quality metrics.

The local application and the deployed test environment can also differ. A local change only becomes a deployed feature after the server has been updated and checked.

The next useful evidence is a repeatable task walkthrough, followed by practitioner review of the generated artifacts. That would say more about the product than another feature list.
