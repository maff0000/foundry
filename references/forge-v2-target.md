# FORGE v2 — target design reference

**Status: OPTIONAL DESIGN TARGET ONLY. Not implemented, not an active release contract, and not required reading for a fresh FOUNDRY Architect.**

The mandatory FOUNDRY interface is the [Orchestrator/PL handoff](../delivery/rogue-handoff.md). The portable Orchestrator role may be implemented personally by Rogue for Matt. FORGE v1 remains operational in [`maff0000/forge`](https://github.com/maff0000/forge). The separate [`maff0000/forgev2`](https://github.com/maff0000/forgev2) repository contains the inherited v1 baseline at `665b32c991caaace95710abd22af6d4c97eefc3b`, with no v2 functional implementation. V1 has not been altered by this documentation. The former `dell-debian` host was unavailable during Matt's house move; no replacement host is presumed.

## Established ForgeV1 PL capability

At source commit `665b32c991caaace95710abd22af6d4c97eefc3b`, ForgeV1 defines the PL as the driving Claude Code session for an individual PID. The PL verifies project truth, decomposes/sequences work, dispatches Engineer/Auditor specialists, reconciles and tests work, owns Git and the PR lifecycle, and accepts/rejects results within the engineering delivery loop. Engineer does not commit; Auditor independently challenges and does not edit. ForgeV1 requires real-browser verification by the Auditor for applicable `PRODUCT_USABLE`+ UI work.

This target preserves the established PL controller and Git ownership within one WO. Any move to named Markdown agent definitions, different reviewer routing, execution-state ownership or Orchestrator fan-out is an **intended V2 design change**; it is not a description of current V1 behavior.

Read the original PL instructions directly rather than duplicating them here: [FORGE-NORTH-STAR.md](https://github.com/maff0000/forge/blob/665b32c991caaace95710abd22af6d4c97eefc3b/docs/FORGE-NORTH-STAR.md), [ARCHITECTURE.md](https://github.com/maff0000/forge/blob/665b32c991caaace95710abd22af6d4c97eefc3b/docs/ARCHITECTURE.md), [OPERATING-MODEL.md](https://github.com/maff0000/forge/blob/665b32c991caaace95710abd22af6d4c97eefc3b/docs/OPERATING-MODEL.md), and [the Forge skill](https://github.com/maff0000/forge/blob/665b32c991caaace95710abd22af6d4c97eefc3b/.claude/skills/forge/SKILL.md).

## Proposed ForgeV2 Markdown roles

The following six role definitions are proposed files for a future ForgeV2 design. They are not present/implemented by this reference and do not gain authority until separately designed, approved and verified.

| Proposed role file | Intended responsibility | Authority boundary |
| --- | --- | --- |
| `forge-orchestrator` | Assign bounded initiation and approved WOs to PLs; aggregate progress/escalation and return evidence to Architect | No product/architectural authority or PL Git operations |
| `forge-project-lead` | Control delivery for one authorised WO; coordinate specialists, own WO Git lifecycle, maintain execution counts and return evidence | No product-direction authority or scope expansion |
| `forge-engineer` | Implement within its assigned role and worktree; decide bounded correction or escalation to PL | No Git/GitHub mutation |
| `forge-auditor` | Independently assess engineering, architecture and WO conformance | No code edits or Git/GitHub mutation |
| `forge-tester` | Independently assess behavior, regression and actual user/browser behavior where relevant | No authoritative code edits or Git/GitHub mutation |
| `forge-devsecops` | Independently assess security, dependencies/provenance, secrets and trust boundaries | No code edits or Git/GitHub mutation |

The hierarchy is Matt + CGPT Architect → Orchestrator (Rogue implementation) → PL → specialists. Agents receive task-specific minimum sufficient context. Independent reviewers can inspect the authoritative WO and standards without inheriting Engineer reasoning as established fact.

## Proposed per-WO delivery loop

1. The Orchestrator assigns one approved WO to one PL. **One WO is one bounded ForgeV2 delivery cycle.**
2. PL confirms the exact project baseline and isolated, project-correct worktree/branch before dispatch. PL owns Git operations within that WO.
3. PL dispatches the proposed specialist sequence: Engineer → Auditor → Tester → DevSecOps. Each reviewer returns PASS or FAIL with reason and evidence; an environmental inability to verify is not PASS.
4. On reviewer FAIL, findings return to Engineer. Engineer alone chooses bounded correction or escalation to the PL. Engineer changes invalidate previous PASS results and require the assurance chain to restart on the new candidate. All final PASS results identify the same unchanged candidate.
5. PL integrates/tests and returns final delivery evidence or terminal escalation to the Orchestrator, which aggregates status and returns it to CGPT. CGPT performs architectural acceptance; Matt retains product acceptance and material risk authority.

### Execution bound and state ownership

Each Engineer, Auditor, Tester and DevSecOps has an independent execution counter per WO. At most **four executions including the first** are permitted; a fifth is prohibited. Counters persist across session restarts/context resets. Each specialist checks its own bound. The **PL holds the authoritative persisted execution count/state for its WO** and returns aggregate progress or escalation to the Orchestrator. Exhaustion produces FAIL with reason/evidence. Only Engineer escalates execution failures to the PL. Neither PL nor Orchestrator may silently reset counters or create replacement WOs to bypass the limit.

This is target doctrine, not a claim of runtime enforcement, persisted storage or operational behavior. The exact counter implementation, reset resistance and evidence mechanism remain unimplemented design questions.

## Git boundaries and candidate identity

The PL controls the WO's branch/worktree, reconciliation, commits and authorised push/PR activity within its scope. Internal specialists cannot commit, push, alter refs/history or mutate GitHub. Engineer edits only authorised code in the assigned worktree; reviewers do not edit authoritative code. Technical/tool/credential isolation must demonstrate these limits when implemented.

A candidate's immutable fingerprint is an unimplemented design choice. Every reviewer must identify the candidate and evidence assessed, and PL verifies the final committed candidate matches all required PASS verdicts. No mixed-candidate acceptance.

Each initiation assignment and WO has an exact GitHub Issue and resolved WO-specific per-role `.log` paths. PL records concise event-driven updates and maintains role-writer/reader boundaries; Orchestrator receives aggregate progress and escalation. Issue comments are status/evidence, not scope authority. The ten-minute Architect inspection remains an operating target, not an unattended-scheduler claim.

## Concurrency and V1 assurance

ForgeV1 documents concurrent PLs on different projects as the hub model, but states concurrent PLs in the same project are not exercised/proven safe. Therefore, do not claim same-project PL concurrency is safe. If it is authorised, require distinct project-correct worktrees and branches plus explicit coordination; isolation alone does not prove safety.

Preserve V1's existing real-browser verification for applicable `PRODUCT_USABLE`+ changes. The proposed V2 move of verification duties from V1's Auditor to a Tester is an explicit behavioral change: it must preserve the same independent, non-vacuous real-browser interaction/state evidence. It does not replace or alter operational V1.

No v2 feature, role file, counter, scheduler, CI, runtime, deployment or tool isolation is implemented here. Design and verify these separately before describing a usable FORGE v2 release.
