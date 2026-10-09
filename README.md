# FOUNDRY

FOUNDRY is Matt Scott's **Agile-based AI Software Development Framework**, designed for AI-first development. It establishes how Matt and AI agents collaboratively initiate, architect, develop, verify and deliver independent software products, adapting established Agile principles and practices to AI-assisted development.

FOUNDRY supplies organisational context: roles, authority, development conventions, engineering standards, documentation requirements, agreed delivery practices, decision and acceptance boundaries, agent tooling conventions and continuous improvement principles. Only the processes and standards explicitly documented here are established; the framework will grow incrementally. Agents contribute their existing engineering knowledge and exercise professional judgment within its governance.

FOUNDRY is not a software application, project management product, collection of forms, scripted interview system, replacement for Agile, deterministic decision tree or AI orchestration engine.

It exists to preserve product direction and architectural coherence, support Agile learning and structured delegation, and reduce unnecessary dependence on Matt during implementation. GitHub preserves authoritative decisions and evidence so new AI sessions can continue without repeatedly reconstructing the development process.

## People, roles and tooling

- **Matt Scott — Product Owner (PO):** owns product vision, objectives, intended value, direction, priorities, scope decisions and final product acceptance.
- **ChatGPT (CGPT) — Project Architect:** leads discovery, contributes research and expertise, stewards architecture through delivery and determines architectural acceptance.
- **Orchestrator:** portable role that assigns bounded project initiation and approved WOs to Project Leads, aggregates progress and escalations, and reports to the Architect. **Rogue** is Matt's personal implementation of this role.
- **Project Lead (PL):** authorised engineering delivery controller for an individual WO; coordinates specialist agents and owns that WO's Git operations within its approved boundary.
- **FORGE and ANVIL:** Claude Code-based and Codex-based implementation tooling respectively. They do not own product direction or architecture; their detailed integration remains deferred.

See [Governance](GOVERNANCE.md) for authority boundaries.

## Start here: humans and fresh AI sessions

Read in this order:

1. This README for purpose and scope.
2. [Agent instructions](AGENTS.md) for how to work within the framework.
3. [Governance](GOVERNANCE.md) for responsibilities and decision authority.
4. [Framework decisions](DECISIONS.md) for agreed doctrine and deferred design.
5. [Stage 1 — Product Initiation & Discovery](stages/01-product-discovery.md) for the currently defined process.
6. [Product record standard](standards/product-records.md) for authoritative project records and approval provenance.
7. [Secure engineering standard](standards/secure-engineering.md) for foundational engineering quality and Security by Design requirements.
8. [Security by Design skill reference](skills/security-by-design.md) for applicable agent competence, without additional authority or a runtime loading mechanism.
9. [Project scaffolding standard](standards/project-scaffolding.md) for project-specific initiation records and infrastructure discovery.
10. [Orchestrator/PL handoff](delivery/rogue-handoff.md) for authorised initiation and delivery communication.

A fresh session receiving “You are the Project Architect. Align yourself to FOUNDRY” should use this reading to understand responsibilities, authority, established processes, standards, conventions and deferred design. It should independently determine the sensible next activity from context, including when clarification or escalation is necessary. There is no mandatory conversational script. If project context is missing, the Architect may establish whether Matt wants to initiate a new product or review an existing one; ask only when the route is genuinely unclear.

A fresh session should establish which role it is acting in, which project is being discussed, what is approved, and what authority exists for the requested work. Reading FOUNDRY does not itself authorise edits or implementation. Identify material uncertainty rather than filling missing processes with assumptions.

## Framework and individual products

FOUNDRY contains framework governance, reusable processes, standards and framework decisions. Each product has its own GitHub repository holding its authoritative Product Vision, Product Backlog and, as applicable, architectural decisions, implementation plans, Work Orders, delivery logs, test and audit evidence, and implementation history.

The Architect generates each project's README, Product Vision and Product Backlog from actual evidence and agreed direction, following the product record standard. The project also maintains the external software register required by the secure engineering standard. Blank forms and placeholder-based document templates are not used. Do not duplicate FOUNDRY's governance documents into product repositories. Active product backlogs and outstanding product decisions do not belong in FOUNDRY. Matt and CGPT deliberately evolve the framework; projects evolve independently under it.

## Current scope

The framework currently defines **Stage 1 — Product Initiation & Discovery (FND-S1, v0.4)**, project scaffolding and Orchestrator/PL handoff doctrine. It supports new products and evidence-based initiation reconciliation, reassessment or re-scoping of existing products through iterative discovery, an agreed Product Vision and an initial Product Backlog. Matt must explicitly approve those artifacts, and they must be recorded in the project's GitHub repository. Stage 1 completion does not authorise implementation.

Project-specific PIM construction and infrastructure discovery follow the [project scaffolding standard](standards/project-scaffolding.md). Authorised initiation and later delivery are separated by Architect acceptance and a fresh PL context under the [Orchestrator/PL handoff](delivery/rogue-handoff.md). Stage 1 establishes security understanding and truthful provenance coverage; it does not initiate security implementation or delivery machinery.

The optional [FORGE v2 target reference](references/forge-v2-target.md) records a design target only; it is not mandatory Architect reading and does not claim an operational v2 release.

Engineering quality and Security by Design apply from initiation under the secure engineering standard.

Agreed downstream principles are recorded in [DECISIONS.md](DECISIONS.md), but later stages are not designed. Detailed Work Order contracts, FORGE cycle implementation, ANVIL integration, token/cost/time budgets, retry enforcement, audit protocols, PR/merge lifecycle, communication transport and scheduling, automated enforcement and detailed stop conditions remain deferred. The optional ForgeV2 reference records agreed target behavior without claiming implementation. Infrastructure values remain project-specific and must be verified; no host or absolute path is fixed globally. A conditional Linux `main/` and `worktrees/` topology is documented under the verified root. After Stage 1, identify the next applicable process; if none is defined, report the framework gap for architectural resolution.

## Continuous improvement

FOUNDRY is a living framework. Delivery experience, security research, engineering discoveries, Agile practice improvements, agent performance observations, recurring failures and new technological capabilities may reveal improvements. Agents may propose changes, but proposals do not become policy automatically. Deliberate Matt/CGPT agreement and traceable Git history preserve improvements for future Architects.
