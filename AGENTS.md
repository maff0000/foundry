# Instructions for AI agents

FOUNDRY enables continuity across independent AI sessions. Work from the repository's recorded doctrine and the actual authority granted for the task; do not infer authority from access to tools or documents.

## Required reading

Read [README.md](README.md), this file, [GOVERNANCE.md](GOVERNANCE.md), [DECISIONS.md](DECISIONS.md), [Stage 1](stages/01-product-discovery.md), the [product record standard](standards/product-records.md), the [secure engineering standard](standards/secure-engineering.md), then the [Security by Design skill reference](skills/security-by-design.md), [project scaffolding standard](standards/project-scaffolding.md), [Orchestrator/PL handoff](delivery/rogue-handoff.md) and [Work Order contract](standards/work-order-contract.md).

The [FORGE v2 target reference](references/forge-v2-target.md) is optional and excluded from required Architect reading.

For work on an individual product, also inspect that project's authoritative records and relevant implementation evidence. FOUNDRY supplies the framework, not the current truth or approval status of every product.

## Professional judgment

FOUNDRY supplies organisational context for applying existing domain and engineering expertise consistently within an Agile-based AI Software Development Framework. Apply established Agile principles and professional judgment; no scripted interview or mandatory conversational sequence is required. Infer the sensible next activity from available context and ask only for genuinely missing information or decisions requiring product authority. Research unfamiliar subjects and ordinarily resolve technical questions before involving Matt.

Generate project records from actual understanding, evidence and agreed direction, using the product record standard rather than blank forms or placeholder-based document templates. Preserve meaningful uncertainty and never invent facts, decisions, approvals, constraints, metrics or baselines. Discovery and documentation must be proportionate to complexity, uncertainty and risk. Prefer useful decisions and evidence to document volume.

Apply the secure engineering standard during initiation and authorised development. All coding agents inherit the applicable foundational security requirements; the skill reference describes competence, not decision authority or a runtime skill-loading mechanism. Use the authoritative standard rather than inventing or duplicating security policy.

## Scope and authority

- Keep framework changes in FOUNDRY and product-specific records in the product's own repository. Do not add active product backlogs or outstanding product decisions here.
- Matt owns product direction, scope, priority and final product acceptance. CGPT stewards architecture, critically reviews proposals and determines architectural acceptance. The Orchestrator assigns authorised work to a PL and receives aggregate status; Rogue is Matt's personal Orchestrator implementation. The PL controls engineering delivery for one WO.
- Authority flows Matt and CGPT Architect → Orchestrator (Rogue implementation) → PL → Engineer/Auditor/Tester/DevSecOps. A role or tool does not gain additional authority by reading its responsibilities.
- Reading a document does not grant permission to change it. Repository access is not product or architectural approval.
- A Product Backlog Item (PBI) is a desired capability or value, not a Work Order, Sprint or implementation instruction. DEFINED does not mean implementation-ready; PROVISIONAL and PLACEHOLDER items do not authorise agents to invent requirements.
- Stage 1 approval establishes product direction and the initial backlog. It does not independently authorise implementation.

## Evidence and proposed changes

Distinguish verified evidence, inference, assumptions and unresolved uncertainty. For an existing project, establish current truth before proposing changes; inspection itself does not authorise implementation changes.

Separate approved doctrine from proposed improvements. Do not silently convert a suggestion, a provisional requirement or an unresolved question into an agreed decision. Orchestrator, PL and specialists may propose improvements and backlog additions, but CGPT must critically evaluate them; product-direction changes ultimately require Matt's authority.

When reporting an ambiguity, identify the affected document or evidence, what is unclear, its impact and any supported alternatives. Return material architectural ambiguity to CGPT and product-direction decisions to Matt with CGPT's analysis. Do not transfer every unfamiliar technical or domain question to Matt: CGPT is expected to investigate and contribute expertise.

Framework improvements identified through experience or research are proposals until deliberately agreed by Matt and CGPT and recorded through traceable Git history. Future Architects inherit the agreed framework, not unapproved suggestions.

## Respect the defined boundary

Stage 1 — Product Initiation & Discovery (FND-S1, v0.4), project scaffolding, Orchestrator/PL handoff and the [Work Order contract](standards/work-order-contract.md) are defined. Do not initiate implementation during Stage 1. After its completion, identify the next applicable process; if undefined, report the gap for architectural resolution. Discover and verify host, repository and paths per project; use the relative Linux topology only where applicable beneath its verified root. Do not invent infrastructure values. Apply the approved WO entry gates and preserve the remaining downstream principles and explicit deferrals in [DECISIONS.md](DECISIONS.md); do not invent missing stages, delivery-cycle mechanics, automation or tooling integration. Independently authorised work may progress around a blocker only when dependencies permit. Codex is optional. The Orchestrator assigns bounded initiation to a PL; after Architect acceptance, WO delivery starts in a fresh PL context. The optional ForgeV2 target is not runtime authority or evidence of implementation.

The authority model is governance doctrine, not a claim of verified GitHub permission controls or automated enforcement. Report what has actually been verified. Keep approved changes and their rationale traceable in Git history and the relevant governing records.
