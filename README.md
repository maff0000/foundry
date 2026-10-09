# FOUNDRY

FOUNDRY is Matt Scott's authoritative, reusable governance framework for AI-assisted software product development. It governs collaboration across independent products; it is not a software application, implementation engine or project management product.

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
5. [Stage 1 — Agile Product Discovery & Definition](stages/01-product-discovery.md) for the currently defined process.
6. [Product Vision template](templates/PRODUCT-VISION.md) and [Product Backlog template](templates/PRODUCT-BACKLOG.md) for project records.

A fresh session should establish which role it is acting in, which project is being discussed, what is approved, and what authority exists for the requested work. Reading FOUNDRY does not itself authorise edits or implementation. Identify material uncertainty rather than filling missing processes with assumptions.

## Framework and individual products

FOUNDRY contains framework governance, reusable processes, templates and framework decisions. Each product has its own GitHub repository holding its authoritative Product Vision, Product Backlog and, as applicable, architectural decisions, implementation plans, Work Orders, delivery logs, test and audit evidence, and implementation history.

Copy the Stage 1 templates into the individual project's repository and adapt their prompts to that product. Active product backlogs and outstanding product decisions do not belong in FOUNDRY. Matt and CGPT deliberately evolve the framework; projects evolve independently under it.

## Current scope

Only **Stage 1 — Agile Product Discovery & Definition** is defined. It supports new ideas and evidence-based re-scoping of existing projects through iterative discovery, an agreed Product Vision and an initial Product Backlog. Matt must explicitly approve those artifacts, and they must be recorded in the project's GitHub repository. Stage 1 completion does not authorise implementation.

Agreed downstream principles are recorded in [DECISIONS.md](DECISIONS.md), but later stages are not designed. Work Order contracts, FORGE cycle mechanics, ANVIL integration, execution budgets, retry policies, audit protocols, PR and merge governance, inter-agent communication, delivery status mechanics, automated enforcement and detailed stop conditions remain deferred.
