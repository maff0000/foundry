# FOUNDRY

FOUNDRY is Matt Scott's **Agile-based AI Software Development Framework**. It establishes how Matt and AI agents collaboratively initiate, architect, develop, verify and deliver independent software products, adapting established Agile principles and practices to AI-assisted development.

FOUNDRY supplies organisational context: roles, authority, development conventions, engineering standards, documentation requirements, agreed delivery practices, decision and acceptance boundaries, agent tooling conventions and continuous improvement principles. Only the processes and standards explicitly documented here are established; the framework will grow incrementally. Agents contribute their existing engineering knowledge and exercise professional judgment within its governance.

FOUNDRY is not a software application, project management product, collection of forms, scripted interview system, replacement for Agile, deterministic decision tree or AI orchestration engine.

It exists to preserve product direction and architectural coherence, support Agile learning and structured delegation, and reduce unnecessary dependence on Matt during implementation. GitHub preserves authoritative decisions and evidence so new AI sessions can continue without repeatedly reconstructing the development process.

## People, roles and tooling

- **Matt Scott — Product Owner (PO):** owns product vision, objectives, intended value, direction, priorities, scope decisions and final product acceptance.
- **ChatGPT (CGPT) — Project Architect:** leads discovery, contributes research and expertise, stewards architecture through delivery and determines architectural acceptance.
- **Rogue — Delivery Controller:** coordinates authorised delivery, maintains progress and evidence, and reports proposals and blockers to CGPT within approved scope.
- **FORGE and ANVIL:** Claude Code-based and Codex-based implementation tooling respectively. They do not own product direction or architecture; their detailed integration remains deferred.

See [Governance](GOVERNANCE.md) for authority boundaries.

## Start here: humans and fresh AI sessions

Read in this order:

1. This README for purpose and scope.
2. [Agent instructions](AGENTS.md) for how to work within the framework.
3. [Governance](GOVERNANCE.md) for responsibilities and decision authority.
4. [Framework decisions](DECISIONS.md) for agreed doctrine and deferred design.
5. [Stage 1 — Product Initiation & Discovery](stages/01-product-discovery.md) for the currently defined process.
6. [Product record standard](standards/product-records.md) for project README, Product Vision, Product Backlog and approval provenance requirements.

A fresh session receiving “You are the Project Architect. Align yourself to FOUNDRY” should use this reading to understand responsibilities, authority, established processes, standards, conventions and deferred design. It should independently determine the sensible next activity from context, including when clarification or escalation is necessary. There is no mandatory conversational script. If project context is missing, the Architect may establish whether Matt wants to initiate a new product or review an existing one; ask only when the route is genuinely unclear.

A fresh session should establish which role it is acting in, which project is being discussed, what is approved, and what authority exists for the requested work. Reading FOUNDRY does not itself authorise edits or implementation. Identify material uncertainty rather than filling missing processes with assumptions.

## Framework and individual products

FOUNDRY contains framework governance, reusable processes, standards and framework decisions. Each product has its own GitHub repository holding its authoritative Product Vision, Product Backlog and, as applicable, architectural decisions, implementation plans, Work Orders, delivery logs, test and audit evidence, and implementation history.

The Architect generates each project's README, Product Vision and Product Backlog from actual evidence and agreed direction, following the product record standard. Blank forms and placeholder-based document templates are not used. Do not duplicate FOUNDRY's governance documents into product repositories. Active product backlogs and outstanding product decisions do not belong in FOUNDRY. Matt and CGPT deliberately evolve the framework; projects evolve independently under it.

## Current scope

Only **Stage 1 — Product Initiation & Discovery (FND-S1, v0.2)** is defined. It supports new products and evidence-based initiation reconciliation, reassessment or re-scoping of existing products through iterative discovery, an agreed Product Vision and an initial Product Backlog. Matt must explicitly approve those artifacts, and they must be recorded in the project's GitHub repository. Stage 1 completion does not authorise implementation.

Agreed downstream principles are recorded in [DECISIONS.md](DECISIONS.md), but later stages are not designed. Work Order contracts, FORGE cycle mechanics, ANVIL integration, execution budgets, retry policies, audit protocols, PR and merge governance, inter-agent communication, delivery status mechanics, automated enforcement and detailed stop conditions remain deferred. Physical host and directory standards are also undefined and must not be invented. After Stage 1, identify the next applicable process; if none is defined, report the framework gap for architectural resolution.

## Continuous improvement

FOUNDRY is a living framework. Delivery experience, security research, engineering discoveries, Agile practice improvements, agent performance observations, recurring failures and new technological capabilities may reveal improvements. Agents may propose changes, but proposals do not become policy automatically. Deliberate Matt/CGPT agreement and traceable Git history preserve improvements for future Architects.
