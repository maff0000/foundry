# Project scaffolding and initiation standard

## Purpose and authority

This standard governs discovery-driven infrastructure and project-record bootstrap for FOUNDRY projects. It defines what must be established, not a fixed host or scripted workflow. Apply professional judgment and risk-proportionate investigation. Do not invent project facts or perform automatic operations on legacy code.

Matt is Product Owner and provides or confirms the project's GitHub repository, development host and project root. None is a global constant: repository owner/name, remote, host, IP, SSH alias, path, branch and connectivity are discovered project facts. Verify existence, identity, access and current state before use; do not inherit another project's settings by assumption. Record value, evidence and status truthfully.

## Architect Gateway registration for new projects (capability-gated)

**One shared communication service, not one deployment per project.** Where an Architect Gateway has been deployed and verified, a project is **registered with that existing gateway** during initiation. New projects do not acquire a second gateway service, polling timer, message database, Claude subscription or Orchestrator installation by default. The gateway is a transport and operational projection; **GitHub remains the source of truth** and the project's FOUNDRY authority gates do not change. This FOUNDRY onboarding requirement is adopted as framework procedure once merged. It does **not** mean that a production multi-project gateway has been installed; installation and project routing must be verified independently before claiming operational capability.

**Required project registration facts, once the gateway is real:**

1. **Project identity:** canonical GitHub `owner/repo`, immutable default-branch baseline, visibility, project/PIM identifier and applicable approved source references; register with a stable `project_id` and an accurate owner/contact. Never infer from another project's configuration.
2. **Routing:** identify the responsible **active Rogue/Orchestrator instance**, target host and its communication inbox/recipient, any existing in-flight WO ownership, and which instance is observer-only. Prevent two Rogues dispatching the same WO. Cross-host routing is explicit; a central gateway does **not** mean all applications run on the gateway's host.
3. **Credentials and access:** verify Rogue's repo-specific GitHub API read/Issue/PR rights and the **separate** Project Lead's repo-specific Git checkout/branch-push capability, as applicable to the project. Record credential **labels, scope and verified access**, not token/key material. Do not globally broaden existing tokens merely to add a project. GitHub permissions do not themselves authorise a WO or merge.
4. **Event contract:** register the project ID, destination role, inbox route, message type allowlist, stable event/correlation ID conventions, reference format, source revision, ack/dedup/replay behavior, failure and staleness status, and evidence links. Treat comments and model output as untrusted data; a shared GitHub author does **not** prove independent human or agent identity. Never execute arbitrary Issue text as a privileged command.
5. **Verification:** a synthetic, project-labelled `CGPT → gateway → Rogue → GitHub response` test is required to claim **AUTOMATIC_PICKUP_VERIFIED**; a manual interactive GitHub round trip proves only **MANUAL_EXCHANGE_VERIFIED**. Confirm readback, duplicate/restart behavior, and truthful offline/unknown state. If initial watcher has no registered multi-project support, declare **NOT_SUPPORTED** rather than treating an Issue #3-only poller as production-ready onboarding.
6. **Lifecycle:** record the gateway registration reference and test evidence in the project's PIM/initiation records, including enabled/disabled state, last check and next recovery action. Reverify after project moves, Rogue handover, credential rotation, repository rename, gateway upgrades, or service restarts. Offboard a project by revoking its routing/credentials without affecting unrelated projects.

**Fallback:** if the gateway is NOT_DEPLOYED, UNAVAILABLE, or lacks verified multi-project routing, record this as a non-blocking communication-capability status during Stage 1 and use the currently authorised GitHub Issues/manual coordination route. Do not invent an installed service or automatically block unrelated discovery work. Before automated dispatch or live dependency on the gateway, require verified project registration and the applicable separately approved gate.

## Project Initiation Mandate

When product understanding is sufficiently coherent, the Architect authors a complete, project-specific `PROJECT-INITIATION-MANDATE.md` (PIM) in the project root. This filename identifies a live project record, not a FOUNDRY form or template. FOUNDRY defines its required content; never add blank fields, fictional values or a generic PIM to this framework repository.

The PIM records, as applicable:

- Project identity, NEW/EXISTING route, author/date/version and immutable FOUNDRY governing revision.
- Approved product intent, beneficiaries, Product Goal, outcomes, scope, exclusions, constraints, assumptions, unknowns, risks and security expectations, with links to authoritative decisions and evidence.
- The actual GitHub repository, default branch and verified baseline; actual development host/root and connectivity; verification evidence/status; and applicable workspace conventions. Unavailable or unknown facts remain explicit and block dependent actions.
- An explicit execution target for engineering expressed as a verified `development-host:/absolute/project/path`, plus the canonical checkout and worktree parent underneath it. Distinguish this target from the Orchestrator's control host; they are not interchangeable.
- When ForgeV2 is used, the identifiable engine installation and version, its protected installation boundary, and the intended application environment/workspace. Keep engine identity separate from product identity; record only verified deployment-specific facts.
- Required project records and bootstrap deliverables, bounded initiation authority, exclusions, stop conditions and the prohibition on Forge delivery before Architect authority.
- Initiation Issue URL or explicit authority for the assigned PL to create it as its first action, before substantive scaffolding; reporting and escalation boundaries.
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

Application source, assets, Work Orders, application logs, test artifacts, build outputs, dependencies and runtime data belong to the application's own governed project workspace. When ForgeV2 is installed separately, protect its installation directory from application delivery operations; application roots and worktrees must remain distinct from it. Verify actual boundaries and reject unapproved filesystem or repository overlap. ForgeV2 changes require a separately authorised engine-development or upgrade activity, not an application WO.

**Execution rule:** no engineering dispatch until the actual `development-host:/path`, canonical checkout and separate worktree parent are declared, verified and recorded for that project. Never derive them from a previous project, the Orchestrator's current working directory, a default host, `/tmp`, the PL's home, or the engine installation. If the Orchestrator is on a different host, verify the remote execution mechanism before dispatch; naming a remote address is not proof that the engine can operate there. An unavailable transport is BLOCKED, not permission to create a local substitute.

For Matt's **planned Trinity deployment**, `/srv/forgev2` is the protected delivery-engine installation and `/srv/foundry` is the optional protected framework reference. Their existence and immutability must be checked **after deployment sign-off**, not assumed now. Application WOs must never write into either installation, whether executing locally or via a remote host. Only a separately authorised ForgeV2 or FOUNDRY update may change its respective installation. These are Trinity deployment facts, not global project defaults.

Investigate existing projects before migration or cleanup. This standard authorises no automatic relocation, deletion, reset, overwrite or operation on legacy code. If infrastructure is unavailable, report it BLOCKED/PENDING and stop host-dependent work. That does not prevent a separately authorised GitHub-only action whose prerequisites are independently met. Assess which Stage 1 closure requirements depend on the missing infrastructure; do not declare full initiation complete while required records or evidence are unavailable.

## Bootstrap boundary

After product direction and records are sufficiently understood, the Architect authors the PIM and authorises the portable Orchestrator to assign bounded bootstrap work to a PL. Matt establishes the repository and development workspace. The PL verifies the PIM, repository and environment; performs only authorised scaffolding; prepares draft Work Orders; and returns evidence to the Orchestrator. The Orchestrator returns results to the Architect. The Architect accepts initiation; Matt retains product authority. The PL cannot approve its own draft Work Orders or begin Forge delivery before Architect authority.

After Architect acceptance of initiation, approved WOs are assigned to PLs for fresh, per-WO delivery contexts based on GitHub-approved records. Work Order drafting is not dispatch authority; each WO must meet the [Work Order contract](work-order-contract.md) and pass its entry gates before specialist dispatch. Forge v2 is a target; a baseline import or repository name does not establish an implemented or accepted release. See the [Orchestrator/PL handoff](../delivery/rogue-handoff.md). Rogue is Matt's personal implementation of the portable Orchestrator role. Codex may assist only when separately authorised.

Application engineering scaffolding and implementation belong to subsequently approved Work Orders. This standard does not define Forge delivery-cycle mechanics or automation. The [product record standard](product-records.md) and [secure engineering standard](secure-engineering.md) continue to apply.
