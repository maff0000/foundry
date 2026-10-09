# Project scaffolding and initiation standard

## Purpose and authority

This standard governs discovery-driven infrastructure and project-record bootstrap for FOUNDRY projects. It defines what must be established, not a fixed host or scripted workflow. Apply professional judgment and risk-proportionate investigation. Do not invent project facts or perform automatic operations on legacy code.

Matt is Product Owner and provides or confirms the project's GitHub repository, development host and project root. None is a global constant: repository owner/name, remote, host, IP, SSH alias, path, branch and connectivity are discovered project facts. Verify existence, identity, access and current state before use; do not inherit another project's settings by assumption. Record value, evidence and status truthfully.

## Project Initiation Mandate

When product understanding is sufficiently coherent, the Architect authors a complete, project-specific `PROJECT-INITIATION-MANDATE.md` (PIM) in the project root. This filename identifies a live project record, not a FOUNDRY form or template. FOUNDRY defines its required content; never add blank fields, fictional values or a generic PIM to this framework repository.

The PIM records, as applicable:

- Project identity, NEW/EXISTING route, author/date/version and immutable FOUNDRY governing revision.
- Approved product intent, beneficiaries, Product Goal, outcomes, scope, exclusions, constraints, assumptions, unknowns, risks and security expectations, with links to authoritative decisions and evidence.
- The actual GitHub repository, default branch and verified baseline; actual development host/root and connectivity; verification evidence/status; and applicable workspace conventions. Unavailable or unknown facts remain explicit and block dependent actions.
- Required project records and bootstrap deliverables, bounded initiation authority, exclusions, stop conditions and the prohibition on Forge delivery before Architect authority.
- Initiation Issue URL or explicit authority for Rogue to create it as its first action, before substantive scaffolding; reporting and escalation boundaries.
- Review evidence and exit/acceptance criteria, including Matt's product decisions and Architect acceptance. No self-approval, inferred approval or automatic merge.

The PIM is a traceable initiation snapshot. Preserve it in GitHub and the verified development copy with identical governed contents. Living product authority remains in the approved Product Vision, Product Backlog, decisions and subsequent approved amendments. PIM contents must be reconstructable from evidence and approved discussion.

## Workspace topology and safety

Where a Linux workspace is approved and available, use the following relative topology beneath the actual verified project root:

```text
<verified-project-root>/
  main/       canonical checkout; no direct implementation edits
  worktrees/  separate isolated worktrees for bounded authorised changes
```

This topology does not prescribe `/srv`, a host, IP, SSH alias or absolute path. Record the actual verified paths in project records. A deviation may be used when approved and when canonical checkout and isolated worktrees remain distinct. Worktrees alone do not guarantee correct-repository lineage, prevent shared-service collisions or grant Git authority.

Investigate existing projects before migration or cleanup. This standard authorises no automatic relocation, deletion, reset, overwrite or operation on legacy code. If infrastructure is unavailable, report it BLOCKED/PENDING and stop host-dependent work. That does not prevent a separately authorised GitHub-only action whose prerequisites are independently met. Assess which Stage 1 closure requirements depend on the missing infrastructure; do not declare full initiation complete while required records or evidence are unavailable.

## Bootstrap boundary

After product direction and records are sufficiently understood, CGPT may delegate bounded project initiation to Rogue. Rogue verifies the PIM, repository and environment, performs only explicitly authorised bootstrap work, drafts Work Orders and reports evidence. Rogue cannot approve its own draft Work Orders, change approved product direction or start Forge delivery before Architect approval.

After Architect acceptance of initiation, a fresh Rogue delivery context is established from GitHub-approved project records and approved Work Orders. Work Order drafting is not dispatch authority. Forge v2 is a target; a baseline import or repository name does not establish an implemented or accepted release. See the [Rogue handoff](../delivery/rogue-handoff.md). Codex may assist only when separately authorised; it is not a mandatory project handoff or authority role.

Application engineering scaffolding and implementation belong to subsequently approved Work Orders. This standard defines no Work Order contract, delivery cycle or automation. The [product record standard](product-records.md) and [secure engineering standard](secure-engineering.md) continue to apply.
