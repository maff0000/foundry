# Stage 1 — Product Initiation & Discovery

**Stage identifier:** FND-S1

**Version:** v0.4

Amendments 002 and 003 add engineering/security and project-initiation requirements; the existing approval gates remain in force.

## Purpose and operating principles

Stage 1 establishes coherent, explicitly approved product direction supported by an initial Product Backlog. It applies to new products and existing products requiring initiation reconciliation, reassessment or re-scoping. It is Agile-aligned and iterative, not a mandatory Scrum ceremony or waterfall phase.

The Architect MUST apply established Agile principles and professional judgment, avoiding scripted interviews. Prefer useful decisions and evidence over documentation volume; produce minimum sufficient records from actual understanding. Do not invent facts, decisions, approvals or constraints. Preserve meaningful uncertainty. Do not initiate implementation during Stage 1.

Discovery depth must reflect project complexity, uncertainty, risk and consequences of failure. Do not impose fixed meeting counts, question counts or arbitrary timeboxes. A simple product must not require the investigation appropriate to a complex, safety-critical or financially consequential system.

## Entry

The Architect establishes the route from available context:

- **NEW:** A product not previously initiated under FOUNDRY.
- **EXISTING:** An existing product requiring initiation reconciliation, reassessment or re-scoping.

Infer the appropriate route; ask Matt only if it is genuinely unclear. Do not repeatedly request known information. Select the sensible next activity using context and professional judgment rather than a mandatory conversational sequence.

## New-product discovery

Establish sufficient understanding of the problem or opportunity, intended beneficiaries, intended product value, Product Goal, important constraints, scope boundaries and non-goals, material risks, significant assumptions, observable success indicators and candidate capabilities.

Investigate meaningful alternatives, including whether building software is justified. Evaluate the underlying problem rather than automatically accepting the initially proposed solution. Detailed architecture is not required during Stage 1.

## Existing-product discovery

Establish current truth before recommending changes. Inspect relevant GitHub documentation and history, existing product records, implementation, tests, architectural decisions, deployment and operational evidence, and known failures and limitations.

Distinguish evidence using these meanings:

| Classification | Meaning |
| --- | --- |
| VERIFIED | Supported by evidence. |
| INFERRED | Reasoned conclusion, not directly proven. |
| ASSUMED | Proposition requiring validation. |
| UNKNOWN | Insufficient evidence. |

Determine what should be retained, corrected, reconsidered or retired. Existing documentation is not automatically proof of implementation reality. Inspection does not authorise implementation changes.

## Foundational security context

For both NEW and EXISTING routes, the Architect MUST establish project-relevant security context and constraints according to the [secure engineering standard](../standards/secure-engineering.md#security-context-during-initiation), applying the [Security by Design competence](../skills/security-by-design.md). Preserve that understanding in project records and establish the external software register with truthful coverage before closure. The standard governs new products with no incorporated code and existing products with incomplete inspection; neither invented inventory nor unsupported assurance is acceptable.

This work is proportionate discovery and reconciliation, not security implementation. Material uncertainties remain subject to critical review and the unchanged product-direction approval gates below.

## Responsibilities

CGPT, the Project Architect, MUST apply relevant domain and engineering expertise, research unfamiliar subjects, challenge weak assumptions, identify material risks, explore alternatives, explain consequential trade-offs, maintain coherence between goal, scope and backlog, distinguish evidence from hypotheses, and escalate decisions outside architectural authority.

The Architect SHOULD resolve ordinary technical questions without involving Matt. Research independently before asking the PO technical questions; ask Matt questions requiring product authority. The Architect MUST NOT independently change approved product direction.

Matt, the Product Owner, retains authority over product purpose, intended value, Product Goal, business priorities, material scope decisions, business risk acceptance and final approval of product direction. Matt need not supply technical expertise reasonably obtainable by the Architect. The broader authority model remains in [Governance](../GOVERNANCE.md).

## Evidence and efficient discovery

Verify consequential claims and reference significant external evidence. Do not invent metrics or baselines. Avoid repeated questions, group related questions when useful, record significant decisions durably and avoid duplicating authoritative information. Minimise unnecessary documentation while retaining enough evidence to support responsible decisions.

Iterate as learning changes understanding. Discovery activities are not a fixed sequence and depth is governed by risk, not document volume.

## Required project records

Every product MUST have its own GitHub repository before Stage 1 closes, containing authoritative `README.md`, `PRODUCT-VISION.md`, `PRODUCT-BACKLOG.md` and `security/EXTERNAL_CODE_REGISTER.yaml`. The Architect generates these from actual project context, evidence and agreed direction according to the [product record standard](../standards/product-records.md). Do not use blank forms or placeholder-based document templates, fabricate facts to complete records, or duplicate FOUNDRY governance into the project. Unknown information remains explicitly unknown.

The Product Vision communicates identity, purpose, problem or opportunity, beneficiaries, value proposition, Product Goal, desired outcomes, observable success indicators, scope boundaries, non-goals, material constraints, significant assumptions, supporting evidence, material risks, unresolved questions, and approval status and provenance.

The Product Backlog contains candidate PBIs describing capabilities or intended outcomes. Each MUST have a stable identifier, capability or intended outcome, intended value and definition state. Include relative priority, dependencies, significant assumptions, supporting evidence and unresolved questions where justified. Matt remains accountable for product priority.

| Definition state | Meaning |
| --- | --- |
| DEFINED | Capability and value sufficiently understood for further refinement; not automatically implementation-ready. |
| PROVISIONAL | Intent understood, but significant uncertainty remains. |
| PLACEHOLDER | Future capability anticipated; detailed definition is premature. It does not authorise agents to invent requirements. |

A PBI is not a Work Order or Sprint. Progressively elaborate the backlog; do not demand detailed requirements for all future PBIs. No definition state grants implementation authority.

The project README orients a fresh agent to product identity, the governing FOUNDRY reference, authoritative product records, current approved state and relevant next authorised activity. Infrastructure values remain project-specific and must be verified. Where applicable, the relative Linux `main/` and `worktrees/` topology under the verified project root follows the [project scaffolding standard](../standards/project-scaffolding.md); no global absolute host or path is prescribed.

## Project initiation record and infrastructure

When product understanding is coherent enough for initiation planning, the Architect authors a project-specific `PROJECT-INITIATION-MANDATE.md` in the project root under the [project scaffolding standard](../standards/project-scaffolding.md). This is a live project record, never a FOUNDRY template. It links the approved product direction and evidence to proposed bounded initiation authority, deliverables, exclusions, verification and escalation. It does not grant Forge delivery permission.

Matt creates/confirms the project's GitHub repository and designated development root; the Architect records the actual verified repository, branch/baseline, host, path and access evidence. No infrastructure value is presumed from another project. Where applicable, the canonical checkout and isolated worktrees use the documented relative Linux topology beneath that verified root. Unknown or unavailable infrastructure remains honestly pending and blocks dependent work; it does not block an independently authorised, safe GitHub-only action. Stage 1 cannot be represented as fully closed while a required project record or closure criterion remains unverified.

## Critical architectural review

Before acceptance, CGPT MUST critically review Product Goal coherence, intended value, intended beneficiaries, contradictory requirements, unsupported consequential assumptions, unrealistic expectations, material risks, scope conflicts, and Product Vision and Backlog alignment.

The review must also assess the security context and register coverage against the secure engineering standard, with approvals and risk escalation governed by [security and engineering authority](../GOVERNANCE.md#security-and-engineering-authority).

Resolve genuine direction-blocking gaps. Non-blocking uncertainty may remain documented. Record review evidence and the versions reviewed in accordance with the product record standard.

## Exit gate

In addition to the required security context, established external-code register with truthful coverage, project-root PIM and verified infrastructure/availability status required by the project standards, Stage 1 may close ONLY when all of the following hold:

1. The problem or opportunity is understood.
2. Intended product value is clear.
3. A Product Goal exists.
4. Scope boundaries and material constraints are recorded.
5. Significant assumptions and risks are visible.
6. An initial Product Backlog exists.
7. The Architect has completed critical review.
8. No unresolved issue prevents responsible approval of product direction.
9. Matt explicitly approves the Product Vision and initial Product Backlog.
10. Approval evidence identifies the exact reviewed artifact versions.
11. Approved records are preserved in GitHub.

Approval must be explicit and traceable. Do not infer it from silence, file existence or checklist completion. Do not create circular commit-SHA references; follow the [approval provenance requirements](../standards/product-records.md#approval-provenance).

## Exit behaviour

After approval, preserve the approved baseline, record non-blocking deferred uncertainties and Stage 1 completion, and identify the next applicable FOUNDRY process. Where authorised, Rogue may then perform bounded project initiation under the PIM. Architect acceptance of initiation is a hard boundary; any later WO delivery uses a fresh Rogue context and separately approved WOs under the [Rogue handoff](../delivery/rogue-handoff.md).

**Stage 1 approval does not authorise implementation.** If the next process is undefined, identify that framework gap for architectural resolution. Do not invent delivery procedures. Later stages and the mechanisms in the [decision register](../DECISIONS.md) remain deferred.

## Continuous improvement

The Architect may identify improvements to FOUNDRY during initiation. These findings are proposals, not automatic policy changes. Framework changes require deliberate Matt/CGPT agreement and traceable Git history, as established in [Governance](../GOVERNANCE.md).
