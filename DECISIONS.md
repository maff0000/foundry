# Framework decision register

This register records FOUNDRY-level doctrine agreed in **FOUNDRY-BOOTSTRAP-001**, approved for implementation by Matt Scott. It does not record individual product decisions, backlogs or candidate review acceptance. Changes to the framework require deliberate agreement by Matt and CGPT and traceable rationale.

## Agreed decisions

| ID | Decision |
| --- | --- |
| FND-001 | FOUNDRY is the separate overarching governance framework, not an application, implementation engine or project management product. |
| FND-002 | GitHub is the durable source of truth for authoritative decisions and evidence, supporting continuity across fresh AI sessions. |
| FND-003 | Each product has its own GitHub repository and authoritative project records. FOUNDRY does not hold active product backlogs or outstanding product decisions. |
| FND-004 | Matt Scott is Product Owner and retains product direction, scope, priority and final product acceptance authority. |
| FND-005 | CGPT is Project Architect and retains architectural stewardship through delivery, including critical review and architectural acceptance. |
| FND-006 | Rogue is Delivery Controller and coordinates authorised delivery without granting itself scope or overriding product or architectural decisions. |
| FND-007 | FORGE and ANVIL are Claude Code-based and Codex-based implementation tooling respectively; detailed integration is deferred. |
| FND-008 | Stage 1 is Agile Product Discovery & Definition, supporting new projects and evidence-based re-scoping through iterative discovery rather than mandatory Scrum ceremonies or a waterfall phase. |
| FND-009 | The Product Backlog is progressively elaborated through Defined, Provisional and Placeholder PBIs. These states do not grant implementation authority. |
| FND-010 | Stage 1 requires CGPT's critical review and Matt's explicit approval of the Product Vision and initial Product Backlog, recorded in the project's GitHub repository. Completion does not authorise implementation. |
| FND-011 | Rogue may propose improvements and backlog additions. CGPT critically evaluates these proposals; product-direction changes ultimately require Matt's authority. |
| FND-012 | One PBI may map to multiple Work Orders. A PBI is not a Work Order or Sprint. |
| FND-013 | One Work Order corresponds to one bounded FORGE delivery cycle. Work Orders will represent limited pieces of work that can be delivered and tested. |
| FND-014 | Independently authorised work may progress while another area is blocked, provided dependencies permit. |
| FND-015 | Material architectural ambiguity must return to CGPT. |
| FND-016 | Execution cost and AI token consumption require governance; the detailed mechanisms are deferred. |

## Deferred framework design

The following are intentionally undecided mechanisms, not permission to invent defaults:

- Detailed Work Order contracts.
- FORGE delivery-cycle mechanics.
- ANVIL integration.
- Agent execution budgets.
- Retry policies.
- Audit protocols.
- PR and merge governance.
- Inter-agent communication.
- Delivery status reporting mechanics.
- Automated enforcement.
- Detailed stop conditions.

Later development stages are not designed in this foundation. Future proposals must be identified as proposals until deliberately agreed. The principles above preserve downstream interfaces without specifying their implementation.

See [Governance](GOVERNANCE.md) for responsibilities and [Stage 1](stages/01-product-discovery.md) for the currently defined process.
