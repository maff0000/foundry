# Stage 1 — Agile Product Discovery & Definition

## Purpose and outputs

Stage 1 transforms an initial idea or an existing project requiring reconsideration into an agreed Product Vision, an initial Product Backlog, and a clear understanding of intended value and outcomes. These form a foundation for subsequent architectural and delivery work.

This is an Agile-aligned, iterative discovery process supporting empirical learning and progressive elaboration. It is not a mandatory Scrum ceremony or a waterfall phase. Activities may be revisited as evidence changes. Not every unknown must be resolved before direction can be agreed.

Matt is Product Owner. CGPT is the Project Architect and discovery partner, supplying research and expertise rather than requiring Matt to independently answer unfamiliar technical or domain questions. Their authority is defined in [Governance](../GOVERNANCE.md).

## Two entry routes

### A. New project

Matt presents an idea, problem, opportunity or desired outcome. A comprehensive specification is not required. Begin by exploring what he wants to achieve and why.

### B. Existing project requiring re-scoping

Matt identifies a project whose product direction, architecture or development scope needs reconsideration. Before proposing changes, CGPT establishes current truth from available evidence. Inspect relevant:

- GitHub documentation and history.
- Implemented functionality.
- Tests and their results.
- Architectural records.
- Deployment and operational evidence.
- Known failures and limitations.

Separate verified facts from unsupported claims, inference and uncertainty. Identify what should be retained, corrected, reconsidered or retired, recording supporting evidence and any gaps in the project's records. Repository inspection does not itself authorise implementation changes.

## Iterative working method

Matt and CGPT work through repeated, focused discussions. Ask a small number of useful questions at a time; do not attempt to define the entire product in one conversation. The following activities are logical areas of work, not rigid sequential gates.

### 1. Explore

Understand the idea, problem or opportunity, why the product should exist, what Matt ultimately wants to achieve, and who may benefit.

### 2. Investigate and challenge

CGPT researches unfamiliar domains, tests important assumptions, challenges weak reasoning constructively and explains viable alternatives. Distinguish evidence from hypotheses and identify significant uncertainty. Contribute expertise rather than returning every difficult question to Matt.

### 3. Establish Product Vision and Product Goal

Agree product purpose, intended users or beneficiaries, value proposition, an explicit Product Goal, desired outcomes, success and learning indicators, important constraints, scope boundaries and non-goals.

Keep unverified assumptions visible as assumptions rather than converting them into firm requirements. Use the [Product Vision template](../templates/PRODUCT-VISION.md) to consolidate direction in the project's `PRODUCT-VISION.md`.

### 4. Shape the initial Product Backlog

Identify candidate capabilities as Product Backlog Items (PBIs). Each PBI describes desired product value or capability; it is not a Work Order, Sprint or implementation instruction. Use the [Product Backlog template](../templates/PRODUCT-BACKLOG.md) in the project's `PRODUCT-BACKLOG.md`.

Capture intended value, approximate priority where known, definition state, important dependencies, material assumptions or unresolved questions, and supporting notes where useful. Future capabilities need not all be specified in detail immediately.

### 5. Review and approve

CGPT consolidates the proposed Product Vision and initial Product Backlog and critically reviews them for:

- Coherence and contradictions.
- Unrealistic assumptions.
- Missing important outcomes.
- Unclear boundaries.
- Material risks.
- Significant unresolved questions.

Record the review findings, remaining uncertainties and any direction-blocking gaps in the project records. Matt then explicitly approves the Product Vision and initial Product Backlog or requests further discovery. Record approval evidence and identify the versions it covers; do not treat draft text or a completed checklist as approval in itself.

Revisit any discovery activity when necessary. A discovery gap blocks closure only when overall product direction cannot responsibly be approved without resolving it.

## Progressive Product Backlog definition

| State | Meaning |
| --- | --- |
| Defined | Intended capability and value are sufficiently understood for further refinement. This does not automatically mean implementation-ready. |
| Provisional | Intended capability is understood, but important assumptions, dependencies or decisions remain unresolved. |
| Placeholder | A future capability is anticipated, but detailed definition would currently be premature. This is not permission for an agent to invent requirements. |

Substantial portions of a product may remain intentionally undefined while sufficiently understood areas progress under the relevant authority. Do not impose unnecessary up-front engineering specifications. The backlog is emergent: Matt remains accountable for product priority, with CGPT helping refine and critically assess items. Changes in definition state do not themselves authorise implementation.

## Authoritative artifacts and revisions

The individual project's GitHub repository holds the authoritative `PRODUCT-VISION.md` and `PRODUCT-BACKLOG.md`, including approval evidence and CGPT's review record or links to it. FOUNDRY holds reusable templates, not active product records.

The Product Vision is living. Matt owns product direction; CGPT maintains architectural coherence. Rogue may read it and propose amendments, but cannot unilaterally change the approved vision. Approved revisions must be traceable through Git history and the governing decision authority, with rationale and approval evidence. Approval of one version must not be presented as approval of later unapproved changes.

The initial Product Backlog is explicitly approved alongside the vision. It remains emergent as learning continues; Matt retains priority accountability. Detailed downstream delivery procedures remain deferred. The authority model is not a claim of technically enforced GitHub permissions.

## Definition of Done

Stage 1 may close when all of the following are satisfied:

- [ ] The problem or opportunity is understood.
- [ ] Intended value is articulated.
- [ ] Intended users or beneficiaries are identified as far as available evidence allows.
- [ ] An explicit Product Goal exists.
- [ ] Desired outcomes are documented.
- [ ] Important scope boundaries and non-goals are understood.
- [ ] Significant assumptions, risks and uncertainties are visible.
- [ ] An initial Product Backlog exists.
- [ ] CGPT has critically reviewed the proposed direction.
- [ ] Matt has explicitly approved the Product Vision and initial Product Backlog.
- [ ] The approved artifacts are recorded in the project's GitHub repository.

Not every unknown must be resolved. Closure does not require complete product architecture, detailed design of every PBI, Sprint planning, Work Orders, FORGE execution, implementation or deployment.

**Stage 1 completion does not itself authorise implementation.** Agreed downstream principles and intentionally deferred mechanisms are recorded in the [framework decision register](../DECISIONS.md); this process does not design later stages.
