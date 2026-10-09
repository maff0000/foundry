# Product record standard

## Purpose and applicability

This standard defines the minimum authoritative records required for [Stage 1 — Product Initiation & Discovery](../stages/01-product-discovery.md). Each product MUST have its own GitHub repository containing `README.md`, `PRODUCT-VISION.md` and `PRODUCT-BACKLOG.md` before Stage 1 closes.

The Architect creates actual records from project understanding, evidence and agreed direction. These requirements define what records communicate, not fill-in forms or a prescribed layout. Do not use blank forms or placeholder-based document templates. Unknown information remains explicitly unknown; never fabricate facts, decisions, constraints, approvals, metrics or baselines to complete a document.

Apply professional judgment and risk-proportionate depth. Produce minimum sufficient documentation, reference significant evidence, record significant decisions durably and avoid duplicating authoritative information. Do not copy FOUNDRY governance into product repositories; reference it. Physical host and directory standards remain undefined and must not be invented.

## Project README

The project's `README.md` MUST orient a fresh agent by communicating:

- Product identity.
- The governing FOUNDRY framework reference.
- Where authoritative product records reside.
- The current approved state, clearly distinguished from proposed changes.
- The relevant next authorised activity.

Reference authoritative records rather than repeating their contents. After Stage 1, the next activity must respect actual authority: approval of product direction is not implementation permission. If the next applicable FOUNDRY process is undefined, identify the framework gap for architectural resolution rather than inventing a procedure or claiming delivery is authorised.

## Product Vision

`PRODUCT-VISION.md` MUST communicate:

- Product identity and purpose.
- Problem or opportunity.
- Intended beneficiaries.
- Value proposition.
- Product Goal.
- Desired outcomes.
- Observable success indicators.
- Scope boundaries and non-goals.
- Material constraints.
- Significant assumptions and supporting evidence.
- Material risks and unresolved questions.
- Approval status and provenance.

Distinguish evidence from hypotheses and preserve meaningful uncertainty. For existing products, use VERIFIED, INFERRED, ASSUMED and UNKNOWN as defined in Stage 1; documentation alone does not prove implementation reality. Success indicators must be grounded in project understanding; unsupported metrics and baselines must not be invented.

The Product Vision is a living authoritative product-direction record. Matt owns direction, CGPT maintains architectural coherence, and Rogue may propose amendments but cannot unilaterally change approved direction. Preserve rationale and governing decision evidence for significant revisions through Git history. Prior approval must not be presented as covering later unapproved changes.

## Product Backlog

`PRODUCT-BACKLOG.md` MUST contain candidate Product Backlog Items describing product capabilities or intended outcomes. Every PBI MUST communicate:

- A stable identifier.
- The capability or intended outcome.
- Intended value.
- Definition state.

Where justified, include relative priority, dependencies, significant assumptions, supporting evidence and unresolved questions. Do not demand detailed engineering specifications for future capabilities or turn the backlog into an implementation task tracker.

| State | Meaning |
| --- | --- |
| DEFINED | Capability and value sufficiently understood for further refinement. Defined does not mean implementation-ready. |
| PROVISIONAL | Intent understood, but significant uncertainty remains. |
| PLACEHOLDER | Future capability anticipated; detailed definition is premature. This state does not permit invented requirements. |

PLACEHOLDER is a legitimate PBI definition state, not an instruction to create blank document templates. The backlog is progressively elaborated and emergent. Matt remains accountable for product priority; CGPT helps refine and critically assess items. Rogue may propose changes for CGPT's critical review; product-direction changes require Matt's authority.

A PBI is not a Work Order or Sprint. Backlog inclusion and definition states do not authorise implementation. The agreed downstream relationships remain in [DECISIONS.md](../DECISIONS.md); this standard does not design their mechanisms.

## Approval provenance

Approval MUST be explicit, traceable and preserved in the project's GitHub records. Record or durably reference Matt's actual approval decision, who gave it, when it was given, and the exact Product Vision and initial Product Backlog versions it covers. Preserve CGPT's critical review evidence and identify the reviewed versions. A draft, silence, file existence or a completed checklist is not approval.

Use immutable artifact references so a fresh agent can recover the exact reviewed contents. Avoid circular commit-SHA references: a document must not purport to contain the SHA of the commit that introduces that very content. An approval record can reference an already-existing artifact commit and its file paths, with the approval evidence recorded subsequently. This describes provenance, not a mandatory PR, merge or delivery workflow.

Approved records must be preserved in GitHub before Stage 1 closes. Keep the approved baseline recoverable, record Stage 1 completion and non-blocking deferred uncertainties, and distinguish subsequent proposals from the approved state. Shared approval evidence may be referenced from the product records rather than duplicated, provided the association to exact reviewed versions remains clear.

Stage 1 approval does not authorise implementation. Governance responsibilities are established in [GOVERNANCE.md](../GOVERNANCE.md); this standard makes no claim that GitHub permissions or automated controls enforce them.
