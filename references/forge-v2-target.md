# FORGE v2 — target design reference

**Status: OPTIONAL DESIGN TARGET ONLY. Not implemented, not an active release contract and not mandatory reading for a fresh FOUNDRY Architect.**

The mandatory interface is the [Rogue handoff](../delivery/rogue-handoff.md). FORGE v1 remains operational in [`maff0000/forge`](https://github.com/maff0000/forge). The separate [`maff0000/forgev2`](https://github.com/maff0000/forgev2) repository contains the inherited v1 baseline at commit `665b32c991caaace95710abd22af6d4c97eefc3b`; it has no v2 functional implementation. A baseline copy does not create or validate a v2 release. Operational v1 remains unchanged. The previously intended `dell-debian` host was offline during Matt's house move; no replacement host is presumed and host provisioning remains a separate discovery task.

This document preserves an optional architectural target. It does not implement or activate agents, controls, cycles or automation.

## Target roles and Git boundary

| Role | Target responsibility | Git/GitHub writes |
| --- | --- | --- |
| Rogue | External controller: coordinate approved WOs, own delivery Git, receive terminal results and escalate | Yes, within delegated delivery authority |
| ENGINEER | Implement within the WO and decide bounded correction versus terminal return | No |
| AUDITOR | Independently assess WO, architecture and engineering conformance | No |
| TESTER | Independently verify functional, integration, regression and real user/browser behaviour where relevant | No |
| DEVSECOPS | Independently assess secure engineering, dependency provenance, secrets and trust boundaries | No |

Only Rogue may alter delivery Git refs/history or GitHub state. Engineer may edit only authorised implementation files in the correct isolated project worktree. Review agents do not edit authoritative implementation. The target requires technical tool/credential isolation to prove these boundaries; instructions alone do not prove enforcement. Reviewers receive sufficient authoritative requirements and relevant specialist competence, independently of Engineer reasoning.

## Target assurance sequence

1. ENGINEER produces an identifiable candidate for AUDITOR.
2. AUDITOR returns PASS or FAIL with reason and evidence. PASS proceeds to TESTER; FAIL findings go to ENGINEER.
3. TESTER returns PASS or FAIL with reason and evidence. PASS proceeds to DEVSECOPS; FAIL findings go to ENGINEER.
4. DEVSECOPS returns PASS or FAIL with reason and evidence. PASS marks engineering verification complete; FAIL findings go to ENGINEER.
5. Only ENGINEER decides whether to correct within the bounded allowance or terminate the WO by returning a substantiated blocked/unresolved report to Rogue. Reviewers cannot repair, alter scope or independently route a failed WO to Rogue.
6. Any Engineer change invalidates prior PASS evidence. The entire AUDITOR → TESTER → DEVSECOPS chain restarts on the new candidate. All PASS verdicts must refer to the same unchanged candidate; no scores or averages.
7. Engineer returns successful verified evidence to Rogue. Rogue performs authorised delivery Git/GitHub operations and returns the candidate to CGPT for architectural acceptance. Matt retains product acceptance and material risk authority.

Environmental inability to verify is not PASS. Report the cause and affected criteria. No reviewer may waive a FAIL to progress the sequence.

## Bounded execution target

For each Work Order, each of ENGINEER, AUDITOR, TESTER and DEVSECOPS has its own independent execution count. Four total executions per role are permitted, counting the initial invocation; a fifth is prohibited. Counts persist through session restarts and context resets. Each agent checks its own limit; Rogue maintains the authoritative persisted count. Exhaustion returns FAIL with reason and evidence. Only ENGINEER escalates execution failures to Rogue. Rogue cannot silently reset counts or create replacement WOs to bypass a limit.

These are approved design principles, not an implemented counter, database or runtime guarantee. Exact persistence, identity and enforcement mechanisms remain implementation-design questions. They must be proven before v2 operation.

## Candidate identity and carried v1 assurance

In-loop candidates may be uncommitted because Forge agents cannot commit. The fingerprint mechanism is to be designed; every reviewer must identify the exact candidate and evidence reviewed. Rogue verifies the eventual committed candidate matches the one that received all required PASS outcomes. Mixed-candidate acceptance is prohibited.

For applicable user-facing work, TESTER retains the existing v1 mandatory real-browser interaction/state verification property. Source inspection or server responses alone cannot replace browser evidence; the check must not pass vacuously. V1's existing browser acceptance remains intact during any future migration.

DEVSECOPS applies FOUNDRY's [secure engineering standard](../standards/secure-engineering.md) and [Security by Design competence](../skills/security-by-design.md). New dependencies, security exceptions, product decisions or material architectural ambiguity are escalated under the governance authority; agents do not grant themselves approval.

## Unimplemented design questions

Before an operational v2 release, separately design and verify:

- Engineer's reviewer coordination and bounded correction/return path.
- Correct-project worktree lineage, isolation and non-mutation of canonical `main/` or other WOs.
- Immutable candidate fingerprinting and match to the eventual Git commit.
- Durable per-agent/per-WO counter storage, check ownership and reset/bypass resistance.
- Hard retry, token, cost and time ceilings and meaningful stop conditions; do not invent values or assume WO scope limits resource use.
- Independent reviewer and tool/credential isolation.
- TESTER's real-browser acceptance, test ownership and evidence retention.
- Version compatibility, dependency assessments and operational tests.

Forge v1's PL/Engineer/Auditor model and instructions are not changed by this reference. No features, agent behaviour, schedulers, CI, deployment or runtime controls are implemented by documenting this target.
