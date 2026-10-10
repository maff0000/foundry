# Orchestrator and Project Lead handoff

## Portable role and authority

FOUNDRY defines a portable **Orchestrator** role. **Rogue is Matt's personal implementation of that role**, not a universal runtime or mandatory product component. The authority hierarchy is:

```text
Matt + CGPT Architect
        ↓
Orchestrator (Rogue implementation)
        ↓
Project Lead (PL), one bounded Work Order
        ↓
Engineer / Auditor / Tester / DevSecOps
```

Matt owns product direction, priorities, material risk acceptance and product acceptance. CGPT owns architecture and architectural acceptance. The Orchestrator assigns bounded work and aggregates progress/escalation, but cannot expand approved scope or replace either authority. A PL controls engineering delivery for its assigned WO, not product or architectural direction. Specialist agents exercise only their assigned role authority. Codex is optional, separately authorised assistance; it is not a mandatory handoff role.

ForgeV1 already implements a capable PL as the driving Claude Code session. FOUNDRY does not duplicate its PL operating instructions; this document records only the portable authority boundary. The [optional ForgeV2 target](../references/forge-v2-target.md) links to the source doctrine and distinguishes retained V1 behavior from proposed changes.

## Bounded initiation

Once product direction is sufficiently coherent, the Architect authors a project-root PIM and provides an authorised initiation assignment to the Orchestrator. Matt establishes the project GitHub repository and development workspace. The Orchestrator assigns the bounded bootstrap work to a PL, identifying the PIM, exact repository/baseline, verified infrastructure where available, immutable FOUNDRY revision, Issue instructions, scope, exclusions and escalation boundaries.

Each initiation assignment has an exact GitHub Issue. If none exists, the Orchestrator may authorise the assigned PL to create it as its first action and return the verified URL before substantive scaffolding. The PL verifies prerequisites, performs only authorised scaffolding and prepares draft WOs; it cannot approve its own drafts, change Matt-approved direction or start Forge delivery before Architect authority. It returns progress/evidence through the Issue and Orchestrator. The Orchestrator returns the candidate to CGPT; CGPT reviews and accepts initiation, and Matt makes required product decisions.

Architect acceptance ends initiation. Later delivery requires separately approved WOs and fresh PL contexts reconstructed from GitHub-approved records and the relevant WO. Discovery and bootstrap conversation is not implicit delivery authority.

## Work Order communication contract

Before dispatch, each approved WO meets the mandatory [Work Order contract](../standards/work-order-contract.md), which defines the full authorization content and entry gates. It also identifies its exact communication and evidence contract:

| Information | Requirement |
| --- | --- |
| Assignment | Stable PIM/WO identity and current authority state. |
| Issue | Exact, verified GitHub Issue URL for that initiation assignment or WO; no silent substitution. |
| Authority | Exact authoritative project paths and immutable revisions applicable to the assignment. |
| Role logs | Resolved WO-specific `.log` paths for each participating role. |
| Writers/readers | Which role writes each artifact and who may read it. PL publishes the WO's Git/GitHub delivery record; internal Forge agents do not commit, push or mutate GitHub. |
| Reporting | Concise, event-driven start, state transition, PASS/FAIL with reasons/evidence, blocker, escalation and completion. Link targeted evidence instead of pasting full logs repeatedly. |
| Escalation | Specialist findings return to the PL; the PL reports terminal results or blockers to the Orchestrator; architectural decisions go to CGPT and product decisions to Matt. |
| Completion | Final status, evidence/PR links, exact reviewed candidate identity, unresolved risks and next approval. |

Issue comments record status and evidence; they do not change direction or WO scope. A blocked Issue does not authorise invented decisions. Need-to-know context narrows down the hierarchy, but independent reviewers retain access to the authoritative requirements and standards they must assess.

Updates are concise and event-driven. A ten-minute Architect inspection interval is an operating target, not an assertion of unattended scheduling. Use a verified scheduler only when one exists; a normal chat session is not an always-on monitor.

## Engineering delivery and Git authority

The Orchestrator dispatches each approved WO to a PL. **One WO is one bounded ForgeV2 delivery cycle.** The PL owns that WO's decomposition, specialist dispatch and coordination, reconciliation, tests, evidence, branch/worktree and Git/GitHub operations, and delivery verdict. It may commit/push only within its WO's authorised repository and branch boundary. It returns delivery evidence and any escalation through the Orchestrator to CGPT for architectural acceptance.

Each internal specialist—Engineer, Auditor, Tester and DevSecOps—cannot commit, push, alter Git refs/history or write GitHub. Engineer may edit only authorised application files in its assigned isolated worktree. Reviewers do not edit authoritative implementation. Tool/credential isolation must demonstrate these boundaries when implemented; this documentation is not technical enforcement.

Forge specialist execution is bounded independently per agent per WO: at most four executions including the first; a fifth is prohibited. Counters persist across restarts. The PL holds the authoritative persisted per-WO execution state, while each agent checks its own limit. Exhaustion yields FAIL with reason/evidence. Engineer alone escalates execution failure to the PL; the PL reports aggregate progress and terminal escalation to the Orchestrator. Neither PL nor Orchestrator may silently reset counts or create replacement WOs to bypass the bound. Further details remain a ForgeV2 design target in the optional reference.

Multiple PLs working on different projects follows ForgeV1's hub model. Concurrent PLs within one project are not proven safe; require independent project-correct worktrees and branches plus explicit coordination. Worktrees alone do not guarantee isolation or eliminate shared-service conflicts.

Forge verification is not CGPT architectural acceptance or Matt product acceptance. A PL's delivery verdict cannot approve scope changes, dependencies, security exceptions or product risk beyond delegated authority. The Orchestrator returns evidence; CGPT accepts architecture and Matt retains product acceptance and material risk authority. No merge or scope expansion is implied.
