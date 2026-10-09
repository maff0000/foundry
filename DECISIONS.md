# Framework decision register

This register records FOUNDRY-level doctrine agreed in **FOUNDRY-BOOTSTRAP-001**, approved for implementation by Matt Scott, as amended by **FOUNDRY — BOOTSTRAP AMENDMENT 001** (approval dated 2026-10-23). Amendment 001 records Matt/CGPT architectural reassessment and Matt’s explicit approval of Stage 1 v0.2. Engineering & Security Foundation Amendment 002 adds the agreed doctrine below; its implementation candidate remains subject to architectural acceptance. This register excludes individual product decisions and backlogs. Changes to the framework require deliberate agreement by Matt and CGPT and traceable rationale.

## Agreed decisions

| ID | Decision |
| --- | --- |
| FND-001 | FOUNDRY is the separate overarching Agile-based AI Software Development Framework, adapting established Agile practice for AI agents. It is not an application, project management product, scripted workflow, form system, replacement for Agile, deterministic decision tree or AI orchestration engine. |
| FND-002 | GitHub is the durable source of truth for authoritative decisions and evidence, supporting continuity across fresh AI sessions. |
| FND-003 | Each product has its own GitHub repository and authoritative project records. FOUNDRY does not hold active product backlogs or outstanding product decisions. |
| FND-004 | Matt Scott is Product Owner and retains product direction, scope, priority and final product acceptance authority. |
| FND-005 | CGPT is Project Architect and retains architectural stewardship through delivery, including critical review and architectural acceptance. |
| FND-006 | Rogue is Delivery Controller and coordinates authorised delivery without granting itself scope or overriding product or architectural decisions. |
| FND-007 | FORGE and ANVIL are Claude Code-based and Codex-based implementation tooling respectively; detailed integration is deferred. |
| FND-008 | Stage 1 is Product Initiation & Discovery (FND-S1, v0.3), supporting new products and existing-product initiation reconciliation, reassessment or re-scoping through iterative discovery rather than mandatory Scrum ceremonies or a waterfall phase. |
| FND-009 | The Product Backlog is progressively elaborated through DEFINED, PROVISIONAL and PLACEHOLDER PBIs. These states do not grant implementation authority. |
| FND-010 | Stage 1 requires CGPT's critical review and Matt's explicit approval of the Product Vision and initial Product Backlog, recorded in the project's GitHub repository. Completion does not authorise implementation. |
| FND-011 | Rogue may propose improvements and backlog additions. CGPT critically evaluates these proposals; product-direction changes ultimately require Matt's authority. |
| FND-012 | One PBI may map to multiple Work Orders. A PBI is not a Work Order or Sprint. |
| FND-013 | One Work Order corresponds to one bounded FORGE delivery cycle. Work Orders will represent limited pieces of work that can be delivered and tested. |
| FND-014 | Independently authorised work may progress while another area is blocked, provided dependencies permit. |
| FND-015 | Material architectural ambiguity must return to CGPT. |
| FND-016 | Execution cost and AI token consumption require governance; the detailed mechanisms are deferred. |

FND-001 and FND-008 are clarified by Amendment 001; their previous wording remains traceable in Git history. The following decisions record its additional doctrine.

| ID | Decision |
| --- | --- |
| FND-017 | Agents exercise professional judgment within governance. FOUNDRY supplies organisational context without replacing their existing domain and engineering knowledge or imposing conversational scripts. |
| FND-018 | Architects generate product records from actual context, evidence and agreed direction, not blank forms or placeholder-based document templates. Each product requires its own GitHub repository with README, Product Vision and Product Backlog before Stage 1 closes. |
| FND-019 | Discovery is proportionate to complexity, uncertainty and risk. Use minimum sufficient documentation, independently research technical matters and preserve meaningful uncertainty. |
| FND-020 | Framework improvements remain proposals until deliberately agreed by Matt and CGPT and preserved through traceable Git history. |
| FND-021 | Stage 1 approval provenance identifies exact reviewed artifact versions without circular commit-SHA references. Preserve the approved baseline and record completion and non-blocking uncertainties; identify the next applicable process or report the framework gap. |

## Engineering & Security Foundation Amendment 002

Matt and CGPT agreed this doctrine and authorised implementation on the approved base `4a9739211f73e38e0ef8fa681c53a406c6c9ba0d`. FND-008 advances to v0.3 to identify the added Stage 1 requirements; all existing approval gates and downstream principles are preserved. FND-018's project records are supplemented by the external software register, not replaced. The [secure engineering standard](standards/secure-engineering.md) is authoritative for the requirements summarised here.

| ID | Decision |
| --- | --- |
| FND-022 | Engineering quality and Security by Design are foundational to AI-first project initiation and authorised development, applied with professional judgment. |
| FND-023 | Engineering is reuse-first and user interfaces are component-first under the secure engineering standard. |
| FND-024 | Applications own their code and reusable assets; project isolation and shared-package considerations follow the secure engineering standard. |
| FND-025 | Third-party software, provenance, approvals and external executable code are controlled under the secure engineering standard. |
| FND-026 | Each product maintains an authoritative external software register with truthful inventory coverage; SBOM evidence supplements it. |
| FND-027 | All coding agents inherit applicable foundational security requirements. The Security by Design skill reference describes competence, not authority or runtime skill loading. |
| FND-028 | Both Stage 1 routes establish security context and the provenance register before closure, without beginning security implementation or weakening approval gates. |
| FND-029 | Matt owns product risk acceptance; CGPT approves dependencies and exceptions within project governance and escalates risk beyond architectural authority. Proposers and independent auditors gain no scope-changing authority. |

## Deferred framework design

The following are intentionally undecided mechanisms, not permission to invent defaults:

- Detailed Work Order contracts and entry gates.
- FORGE delivery-cycle mechanics.
- ANVIL integration.
- Agent execution budgets.
- Retry policies.
- Audit protocols.
- PR and merge governance.
- Inter-agent communication.
- Delivery status reporting mechanics.
- Automated enforcement.
- Security implementation machinery, scanners, SBOM generators, register automation and schema enforcement, runtime skill loading and audit agents.
- Detailed stop conditions.
- Physical host and directory standards.
- Orchestration mechanisms, deployment procedures and CI/CD automation.

Later development stages are not designed in this foundation. Future proposals must be identified as proposals until deliberately agreed. The principles above preserve downstream interfaces without specifying their implementation.

See [Governance](GOVERNANCE.md) for responsibilities and [Stage 1](stages/01-product-discovery.md) for the currently defined process.
