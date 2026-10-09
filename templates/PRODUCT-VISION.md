# Product Vision — {product name}

> Copy this template into the individual project's repository as `PRODUCT-VISION.md`. Replace prompts with supported project information; retain material unknowns explicitly. This is a living product-direction document, not an implementation authorisation. See [Stage 1](../stages/01-product-discovery.md) and [Governance](../GOVERNANCE.md) in FOUNDRY. When copying, update these framework links to point to FOUNDRY from the destination repository.

## Product identity

- Product name: {name}
- Project repository: {repository reference}
- Product Owner: Matt Scott
- Project Architect: CGPT
- Discovery entry route: {new project / existing-project re-scoping}
- Revision: {identifier for this proposed or approved version}
- Last updated: {date}
- Approval status: {draft / proposed for approval / approved; evidence required}

## Problem or opportunity

{What problem or opportunity exists? Why should this product exist? Describe relevant context and the evidence supporting the need.}

## Intended users and beneficiaries

{Who benefits, and in what circumstances? Distinguish known users from hypotheses and identify evidence gaps.}

## Value proposition

{What value should the product create for these people or the business? Why does that value matter?}

## Product Goal

{State the explicit objective for the product toward which the Product Backlog is directed. Keep it understandable without an implementation plan.}

## Desired outcomes

{Describe the changes or benefits sought, rather than prescribing engineering tasks.}

## Success and learning indicators

| Outcome or learning question | Indicator and evidence source | Baseline or target, if supported | Uncertainty |
| --- | --- | --- | --- |
| {outcome or question} | {how progress or learning can be assessed} | {known value or unknown} | {limitations} |

## Scope boundaries

{What is included in the agreed direction? Where are the important boundaries? Avoid treating every future capability as a present commitment.}

## Constraints

{Record important business, technical, operational or other constraints and their basis. Mark unverified constraints as assumptions.}

## Non-goals

{What is explicitly outside the intended product direction?}

## Material assumptions and supporting evidence

| Assumption or claim | Evidence reference | Assessment | Implication if incorrect |
| --- | --- | --- | --- |
| {claim} | {source, date and relevant context, or evidence missing} | {verified fact / inference / hypothesis; explain limits} | {effect on direction} |

## Risks

{Describe material risks, their effect on intended outcomes and available evidence. Avoid inventing certainty where investigation is still needed.}

## Unresolved questions

| Question | Why it matters | Current understanding or next investigation | Blocks responsible direction approval? |
| --- | --- | --- | --- |
| {question} | {impact} | {evidence, alternatives or unknown} | {yes/no and rationale} |

## Existing-project evidence, if applicable

{For re-scoping, summarise current truth from documentation and history, functionality, tests, architectural records, deployment/operational evidence and known failures or limitations. Link evidence and separate verified facts from unsupported claims. Identify what should be retained, corrected, reconsidered or retired. For new projects, mark this section not applicable. Inspection is not implementation authority.}

## Initial Product Backlog

See [PRODUCT-BACKLOG.md](PRODUCT-BACKLOG.md). {Identify the revision considered with this vision and any important alignment issues.}

## CGPT critical review

- Reviewed version(s) and date: {vision and backlog revision references}
- Review evidence: {durable reference or recorded review}
- Findings: {coherence, contradictions, unrealistic assumptions, missing outcomes, boundaries, material risks and unresolved questions}
- Disposition: {ready for Matt's direction decision / further discovery needed, with rationale}

## Matt's explicit approval

- Decision: {pending / approved / further discovery requested}
- Product Owner: Matt Scott
- Decision date: {date, once given}
- Approved Product Vision version: {exact revision reference}
- Approved initial Product Backlog version: {exact revision reference}
- Approval evidence: {durable reference or faithful record of Matt's explicit decision}
- Remaining uncertainties accepted with the direction: {record if applicable}

Do not fill approval fields as approved without actual evidence. Approval applies to the identified versions. Stage 1 completion does not authorise implementation.

## Significant revision rationale

| Revision | Change and rationale | Governing decision and approval evidence |
| --- | --- | --- |
| {revision reference} | {what changed and why} | {reference or pending decision} |

Matt owns product direction and CGPT maintains architectural coherence. Rogue may propose amendments but cannot unilaterally change the approved vision. Preserve approved revision history and evidence in Git; do not imply that prior approval covers new proposed changes.
