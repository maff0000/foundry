# Rogue initiation and delivery handoff

## Authority

This is the mandatory FOUNDRY-facing handoff doctrine, not a FORGE operating manual. Matt is Product Owner; CGPT is Project Architect. Rogue is Delivery Controller. Codex may provide separately authorised assistance under CGPT's authority; it is optional, not a mandatory project stage or independent Architect. FORGE is delivery tooling, not product or architectural authority.

## Bounded project initiation

Once product direction is sufficiently coherent, CGPT may issue Rogue a concise, project-specific initiation instruction pointing to the verified project-root PIM, exact repository and baseline, verified host/root where available, immutable FOUNDRY revision, Issue instructions, authorised scope, exclusions and escalation boundaries.

If no initiation Issue exists, creating it may be Rogue's first authorised action. Rogue returns and verifies its URL before substantive scaffolding. Rogue then verifies prerequisites, performs only explicitly authorised bootstrap, prepares reviewable Work Order drafts, and publishes concise progress and evidence. Rogue cannot approve its own draft WOs, change Matt-approved direction, grant itself scope or begin Forge delivery before Architect authority. Architectural uncertainty returns to CGPT; product decisions return to Matt through CGPT.

CGPT reviews initiation evidence and candidate project records; Matt makes required product decisions. On Architect acceptance, the initiation phase ends. Delivery requires separately approved WOs and a **fresh Rogue context**, reconstructed only from GitHub-approved project records and the approved WOs. Do not carry discovery/bootstrap conversation as implicit delivery authority.

## Work Order communication

Before each agent dispatch, its approved WO must identify the exact communication contract:

| Information | Requirement |
| --- | --- |
| Assignment | Stable PIM/WO identifier and current authority state. |
| Issue | Exact verified GitHub Issue URL for that assignment. Each initiation assignment and each WO has its own bounded Issue; no agent substitutes another location. |
| Authority | Exact authoritative project paths and immutable revisions applicable to the work. |
| Role logs | Resolved, WO-specific `.log` paths for each participating role; no invented locations. |
| Writers/readers | Which role writes each record; who may read it; Rogue alone publishes delivery records and performs delivery Git/GitHub writes. |
| Reporting | Concise event-driven start, state transition, review PASS/FAIL with reasons/evidence, blocker, escalation and completion. Full logs are not repeatedly pasted into Issue comments. |
| Escalation and return | Reviewer findings go to Engineer; Engineer returns bounded correction or terminal blockage to Rogue; Rogue escalates architectural questions to CGPT and product decisions to Matt. |
| Completion | Final status, evidence/PR links, exact reviewed candidate identity, unresolved risks and next required approval. |

Issue comments communicate status and evidence; they do not change product direction or WO scope. A blocked Issue is not authority to invent decisions. Need-to-know context narrows down the delivery chain, but independent reviewers retain access to authoritative requirements and standards so they can challenge the work independently.

Progress is event-driven, concise and evidence-linked. A ten-minute Architect inspection interval is an **operating target** while work is active, not a claim of unattended scheduling. Use an actual verified scheduler only when one exists; a normal chat session is not an always-on monitor. Exact polling machinery and continuous monitoring remain undefined.

## Delivery authority and acceptance

One PBI may map to multiple WOs; one approved WO corresponds to one bounded Forge delivery cycle. A WO draft, PBI or Stage 1 approval does not dispatch work. Detailed WO readiness contracts remain future governance unless separately agreed.

During delivery, Rogue alone performs delegated delivery-side Git/GitHub mutations: branch/worktree administration, integration, commits, evidence publication and PR preparation. CGPT/Codex may make separately authorised framework or architectural-record changes under explicit scope. Internal Forge agents cannot write Git refs/history or GitHub state; Engineer edits only authorised application files in its assigned isolated worktree, and reviewers do not edit authoritative implementation. Tool and credential isolation must demonstrate this property when implemented; documentation alone does not enforce it.

Forge engineering verification is not CGPT architectural acceptance or Matt's product acceptance. Rogue returns results and evidence to CGPT. CGPT accepts architecture; Matt retains product direction, product acceptance and material risk authority. Rogue may progress independently authorised work only where dependencies permit. No merge or scope expansion is implied.

## Optional FORGE v2 target

The [FORGE v2 target design reference](../references/forge-v2-target.md) is optional research material, clearly labelled as a not-implemented target. It is excluded from the mandatory fresh-Architect reading order. V1 remains separate and authoritative for its own operation; a v2 repository or baseline does not establish a usable release.
