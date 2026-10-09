# Instructions for AI agents

FOUNDRY enables continuity across independent AI sessions. Work from the repository's recorded doctrine and the actual authority granted for the task; do not infer authority from access to tools or documents.

## Required reading

Read [README.md](README.md), this file, [GOVERNANCE.md](GOVERNANCE.md), [DECISIONS.md](DECISIONS.md), [Stage 1](stages/01-product-discovery.md), then the [Product Vision](templates/PRODUCT-VISION.md) and [Product Backlog](templates/PRODUCT-BACKLOG.md) templates.

For work on an individual product, also inspect that project's authoritative records and relevant implementation evidence. FOUNDRY supplies the framework, not the current truth or approval status of every product.

## Scope and authority

- Keep framework changes in FOUNDRY and product-specific records in the product's own repository. Do not add active product backlogs or outstanding product decisions here.
- Matt owns product direction, scope, priority and final product acceptance. CGPT stewards architecture, critically reviews proposals and determines architectural acceptance. Rogue coordinates only authorised delivery.
- An implementation agent or tool does not acquire the authority of Matt, CGPT or Rogue simply by reading their responsibilities.
- Reading a document does not grant permission to change it. Repository access is not product or architectural approval.
- A Product Backlog Item (PBI) is a desired capability or value, not a Work Order, Sprint or implementation instruction. Defined does not mean implementation-ready; Provisional and Placeholder items do not authorise agents to invent requirements.
- Stage 1 approval establishes product direction and the initial backlog. It does not independently authorise implementation.

## Evidence and proposed changes

Distinguish verified evidence, inference, assumptions and unresolved uncertainty. For an existing project, establish current truth before proposing changes; inspection itself does not authorise implementation changes.

Separate approved doctrine from proposed improvements. Do not silently convert a suggestion, a provisional requirement or an unresolved question into an agreed decision. Rogue may propose improvements and backlog additions, but CGPT must critically evaluate them; product-direction changes ultimately require Matt's authority.

When reporting an ambiguity, identify the affected document or evidence, what is unclear, its impact and any supported alternatives. Return material architectural ambiguity to CGPT and product-direction decisions to Matt with CGPT's analysis. Do not transfer every unfamiliar technical or domain question to Matt: CGPT is expected to investigate and contribute expertise.

## Respect the defined boundary

Only Stage 1 is defined. Preserve the downstream principles and explicit deferrals in [DECISIONS.md](DECISIONS.md); do not invent missing stages, contracts, automation or tooling integration. Independently authorised work may progress around a blocker only when dependencies permit.

The authority model is governance doctrine, not a claim of verified GitHub permission controls or automated enforcement. Report what has actually been verified. Keep approved changes and their rationale traceable in Git history and the relevant governing records.
