# Rogue — portable host adoption and communication smoke test

**Status: FOUNDRY Rogue host-bootstrap procedure, companion to [ROGUE.md](../ROGUE.md), effective upon approved merge.** This is a setup procedure, not independent Work Order, installation or host-change approval. Record the approved role-file Git commit before copying it to any host.
**Date:** 2026-11-15. 
**Sources:** FOUNDRY delivery/rogue-handoff.md, governance and host-scaffolding rules; proposed Issue #2 orchestrator memory model (still unapproved); maff0000/forgev2 plugin/ORCHESTRATOR.md; architect-gateway Issue #3's host inventory as reported by Claude, **not independently verified by CGPT on the host**.

## Why this belongs in FOUNDRY

FOUNDRY owns the portable Orchestrator role and cross-project bootstrapping expectations. ForgeV2 owns the immutable PL delivery toolchain and its run contract. The new architect-gateway project owns eventual transport and durability. **Do not put ROGUE.md inside ForgeV2's protected engine or turn it into a ForgeV2 plugin; that confuses ownership and encourages project work in the engine.**

## What a new host needs

- Access to the verified approved GitHub FOUNDRY revision that contains ROGUE.md; actual role/version approval recorded in FOUNDRY.
- An existing, working Claude Code installation and an authorised subscription/login; version and executable path checked on the host.
- A **private, separate Rogue home**, ordinarily 0700, with router + canonical role file + project-index and working notes; root or non-root identity is a **host-specific Matt-approved choice**.
- Read-only access to FOUNDRY and relevant project GitHub records, and narrowly authorised Issue commenting for the synthetic first communication test. No credential value in GitHub, scripts, logs or memory.
- Optional ForgeV2 installed engine: confirm its repo, revision, plugin version and path before use. The engine is **immutable** during Rogue/application work. PL and specialists run with ForgeV2's documented runtime under the PL identity designated for the host. On a development host Matt may designate the same account as Rogue, including root (ROGUE.md section H, FND-047); do not infer that designation from Rogue's own identity.
- Read-only evidence of which, if any, Rogue is already active and which projects/Work Orders it owns. A new Rogue starts in **observer mode** if another currently controls them.
- A real FOUNDRY-approved project/PIM/WO and verified application host/canonical checkout/worktree parent **only when engineering dispatch is proposed**. These are not needed merely to boot Rogue or do a no-side-effect GitHub read test.

## IONOS reference deployment shape (pilot installed as reported by Rogue; host not independently inspected by CGPT)

The 2026-11-15 host report suggests a root-controlled Claude Code controller, protected ForgeV2 at a separate immutable location, and Rogue's working home **/srv/rogue**. It reports Claude 2.1.325 for Rogue, a v0.3 ForgeV2 plugin under **/srv/forgev2/src/plugin**, a separate PL Claude 2.1.310, and no active Forge processes. All of these must be rechecked **on the actual target host**; do not blindly treat them as live truth.

**Root Rogue is Matt's explicit preference for this particular IONOS host**. It is a pragmatic accepted risk: inspect target + authority before root writes, preserve recoverability, avoid altering other projects, and keep already working ForgeV2's non-root PL/specialist contract intact. This does **not** adopt the proposed FOUNDRY Issue #2 row “root for administration only” or bypass any currently adopted framework rule; reconcile that pending proposal before its eventual merge.

The IONOS provider firewall is Matt's chosen perimeter control. **Do not install or manage an additional host firewall** unless separately requested. No separate Rogue Linux account, Claude login, API-key subscription, excessive sandbox project or new daemon is implied by this candidate role.

### Host file arrangement

    /srv/rogue/               # root-owned; mode 0700
      CLAUDE.md               # concise router; no imports or other personas
      ROGUE.md                # byte-identical approved FOUNDRY version
      MEMORY.md               # index; one row per project, no project facts
      memory/
        FOUNDRY.md            # notes only (if relevant)
        FORGEV2.md            # notes only (if relevant)
        GATEWAY.md            # notes only (if relevant)
      START.sh                # verified Claude executable; optional

Only create/update these files after bounded host-adoption authority; first inspect whether they already exist. Copy any valuable existing draft to restricted backup, do not overwrite silently. The FOUNDRY repository stores **none** of the host's private memory or secrets.

### Example CLAUDE.md *router*, not an extra role file

    # Rogue entry point (host-local)
    This working directory is Rogue's private Orchestrator home.
    Before responding to a new task, read ./ROGUE.md and ./MEMORY.md.
    Load only the project file whose triggers match the current task.
    Do not import another persona, unrelated project notes or memory automatically.
    Verify current project authority against GitHub before consequential action.
    Installed ForgeV2 is a protected, read-only delivery toolchain.

The router should be short, avoid copying governance, and not include a direct import of every project note. Verify actual Claude Code bootstrap behaviour: the existence of CLAUDE.md alone does not prove the model loaded another file; **test with a clean session**.

### Example START.sh outline — replace executable after host verification

    #!/bin/sh
    set -eu
    cd /srv/rogue
    exec env CLAUDE_CODE_DISABLE_AUTO_MEMORY=1 DISABLE_AUTOUPDATER=1 \
      /root/.local/share/claude/versions/2.1.325

The pinned path **is merely the version reported by Claude on this host**. Validate that exact path, executable ownership and current CLI behaviour before writing START.sh. Do not enable an unattended root service or background launcher as part of the initial interactive smoke test. If a local advisorModel is configured, preserve it and verify use only through authorised mechanisms; advice is not authority.

### Working memory

MEMORY.md is an index with stable project ID, repo URL, local note path, match triggers, current execution host/paths only if verified, role/lane and last GitHub reconciliation time. Notes in memory/<PROJECT>.md are short working observations, not repeated Product Vision/WO text or approval claims. After every relevant merge, replay from GitHub first, then update notes.

Existing FOUNDRY Issue #2 defines a comprehensive **unapproved** memory standard and fictional examples. If it becomes normative, reconcile this recipe and the canonical ROGUE.md before merging, rather than introducing contradictory standards.

## Minimal practical security and identity

- Use the existing root Claude subscription on the host (where Matt has chosen it). Where the PL has its own account, **do not copy** its Claude login/SSH keys, GitHub credentials or private ledger to Rogue.
- For the **private architect-gateway** GitHub communication proof, choose a GitHub credential granted only the required repository and permissions. A fine-grained GitHub PAT with Issues read/write (and necessary repository metadata access) is an option, **entered privately by Matt** using gh authentication. Other project read scopes must be explicitly justified. Verify gh auth status without printing tokens.
- If a GitHub event is posted under the shared human GitHub identity, a nonce and event ID provide **correlation/deduplication** only. They do not independently certify who authored it; never treat Rogue-authored Issue comments as Matt's personal approval.
- IONOS firewall management belongs to Matt; do not add another firewall, alter SSH access, open a web endpoint or install a network daemon for a GitHub Issue-only smoke test.
- Keep secrets out of any public FOUNDRY/ForgeV2/Gateway docs. When a security finding needs private detail, use restricted host-local evidence and a sanitized GitHub summary.
- Preserve /srv/forgev2 and any other immutable engine/reference installation. **No git fetch, package install, git config changes or chown/chmod experiments inside protected paths** for read-only identity verification.
- If the root-operated model and a later specialist isolation test conflict, report the exact conflict; do not weaken the engine's checks to achieve a green verdict. `FORGE_ALLOW_ROOT=1` is for a designated development host whose PL identity is root, not a way past a failing test.

## GitHub project onboarding — standard for Rogue and each newly assigned repository

**This is mandatory to prove the capabilities Rogue needs, but the credential type is chosen pragmatically.** The initial test project is the private `maff0000/architect-gateway` repository. On a fresh host or new project, do this once, then reuse the verified access until revocation or a genuine change requires reassessment.

1. **Identify actual project:** confirm private/public visibility, default branch, pinned main, relevant draft PR/Issue, and approved WO status from the live GitHub API. Do not use `main` or a PR head from remembered notes without checking.
2. **Root Rogue API/coordination access:** reuse an existing narrowly-scoped `gh` credential if suitable. If absent, Matt creates one **fine-grained GitHub Personal Access Token** scoped solely to `maff0000/architect-gateway` (or the exact currently assigned repository). Suggested repository rights: **Metadata: read** (implicit); **Contents: read**; **Issues: read/write**; **Pull requests: read/write**. Do not request Administration, Secrets, Actions write, or account-wide `repo` by default. If the GitHub API reports an additional mandatory permission, determine why and get a narrow explicit grant; do not silently broaden.
3. **Private installation:** Matt enters the secret through an interactive, non-logged, non-echoed `gh auth login --with-token` method or another verified secure secret input; never put a token in shell history, arguments, a public PR, a prompt, local memory or the command output. The existing root user is acceptable on Matt's IONOS server; store the resulting credentials under the root account's normal protected GitHub CLI configuration. `gh auth status` establishes the logged-in identity, not which *single private repo* the token can access.
4. **Verify real API permissions with benign operations:** `gh repo view maff0000/architect-gateway`, `gh issue view 3 -R maff0000/architect-gateway --comments`, `gh pr view 2 -R maff0000/architect-gateway`; perform one explicitly authorised, clearly marked synthetic comment write/readback to Issue #3. Root Rogue does not perform unapproved source code pushes or merges. If an existing token is broader than intended, record the exception and prefer replacement at a convenient gate; never publish its rights or value.
5. **ForgeV2 PL Git route (distinct from root `gh`):** inspect the existing `forgev2-pl` identity, credentials and active projects *without reading secrets*. To work on gateway code, give this existing PL identity a **gateway-only** repository Git credential, such as a write-enabled GitHub deploy key. Matt adds only the public half in GitHub repository **Settings → Deploy keys → Add deploy key → Allow write access**. Do not create a second Claude login or Linux identity. Keep the private half mode 0600, under PL-only private configuration, never in `/srv/rogue` or a worktree. Confirm the repo remote remains the strict canonical `github.com` form accepted by ForgeV2 `forge-start`, and choose/configure the key compatibly with the actual installed plugin; don't use a noncanonical SSH hostname alias to evade origin checks.
6. **Check PL read vs write separately:** the PL must independently read the correct repository and use an approved, **non-writing** Git credential/push-dry-run capability check without changing project refs. A real `forge/<WO>` push and later PR exercise requires a specifically approved test/work order and independent checks. A dry-run is a preflight, not a definitive final write proof. Rogue's root `gh` may register/inspect Issues and PRs, but must not take over PL-controlled commits/branches. If PR creation under a token does not work, report **PR_API_BLOCKED** and fix narrowly.
7. **Document on the host, no secrets:** project identifier; Rogue credential label and scope; PL credential label and scope; tested `gh` commands and result; tested PL repo identity/path; initial/current approved SHA; when next verify or rotate; last synthetic correlation ID. Project index remains a pointer, not a second authority. Avoid public posting of network/credential-specific setup details.
8. **Negative case and revocation:** use a harmless attempted read of a non-authorised project to check accidental overreach; handle a 404/denial without disclosure. Confirm where Matt can revoke the token/deploy key. Do not attempt cross-repository writes.

**Development hosts with one shared account:** where Matt has designated one account for Rogue and the PL (ROGUE.md section H), steps 5–6 reduce to confirming that the account can read the repository and passes the same non-writing push preflight. No deploy key, second login or separate PL account is created.

**Failure classification:** `ROGUE_GH_BLOCKED` = root gh cannot access Issue/PR as authorised; `PL_GIT_BLOCKED` = PL cannot read/push to approved work target; `PROJECT_IDENTITY_BLOCKED` = repo/path mismatch; `AUTHORITY_BLOCKED` = missing exact WO permission. No dummy credentials, global scope switch or bypass to make a test green. Check unrelated active PL sessions first and never overwrite credentials belonging to another project.

**Scaling:** repeat the same narrow onboarding for each new project. Rogue's capabilities vary by project; an existing token for gateway does **not** grant rights to other private repositories, and a new repo should not be added by extending permissions silently. A GitHub App can replace multiple PATs later if credential upkeep becomes genuine overhead, without changing the project's message schema or FOUNDRY authority hierarchy.

## Shared Architect Gateway — onboarding each new project

**Rogue's primary authority is `ROGUE.md` section A3: new-project commissioning.** Project communications are an obligatory item in its intake and readiness report. This is **one centrally operated gateway** with project-specific registrations, not a separate Claude process/timer/service installed per project.

**At the start of every project:** confirm its FOUNDRY product/authority route and exact GitHub repo; execution host, PL, root and worktree topology; Rogue API rights and separate PL Git rights; responsible active Rogue; central Gateway capabilities and inbox/return route. Register project ID and allowed message types, store no credentials in project docs, then perform a project-labelled direct Architect↔Rogue synthetic exchange and link the comments. Test duplicate/restart behavior whenever automatic pickup is in scope. Record the tested mode explicitly:

- `NOT_REGISTERED` — no project route yet
- `PENDING` — setup or test incomplete
- `MANUAL_EXCHANGE_VERIFIED` — direct GitHub comments work with both agents actively checking, but no automatic pickup proof
- `AUTOMATIC_PICKUP_VERIFIED` — central service independently received, validated and replied to the Architect without Matt prompting Rogue; replay/restart checks passed
- `UNSUPPORTED` or `FAILED` — route doesn't exist or did not pass; do not fake success

**At dispatch:** Rogue compares the project's required communication level to its independently verified capability, alongside the approved WO/host/PL/credential gates. An unimplemented automatic route blocks tasks depending on automatic receipt, **not** unrelated Stage 1 document discovery. Where Matt requires always-on Architect supervision for a delivery, a manual fallback must be separately disclosed and accepted; it must not silently count as automatic integration.

**At future project onboarding:** register a new route in the already-running gateway and test it; do not launch another Issue #3 timer or give the project its own root service by default. Different project hosts/Rogues stay distinguishable and single-owner dispatch remains mandatory. If only the existing `architect-gateway` Issue #3 pilot is supported, all other projects remain `UNSUPPORTED` until the shared router and project registry are separately implemented and accepted.

Use the [project-scaffolding standard](../standards/project-scaffolding.md#architect-gateway-registration-for-new-projects-capability-gated) for the full project registration record, and [Gateway Issue #5](https://github.com/maff0000/architect-gateway/issues/5) for the first single-project observer proposal. Project records must link the successful gateway registration and comms evidence. Neither this guide nor Issue #5 is implementation authority by itself.

## Small, staged acceptance — no extra framework required

**Stage A: source and local boot (requires explicit approved host adoption).**
- Pin and review the approved FOUNDRY ROGUE.md commit. Compare the host-local role file checksum against the approved GitHub blob. Ensure the router, index and intended project notes exist and are accessible to the Rogue process.
- Start interactive Rogue using existing root Claude login and the separately verified CLI binary from the private Rogue home. Validate loading, one-project selection, exclusion of other personas and actual mode with automatic project memory disabled.
- Read the *currently* installed ForgeV2 plugin manifest and handoff contract without writing into the engine. No PL launch in this stage.
- From a fresh conversation run the reorientation checklist; compare reported GitHub main/Issue SHA against an independent GitHub read.

**Stage B: GitHub-only synthetic two-way test (separate narrow communication authority).**
1. Confirm gh can access only the intended private test Issue(s), without revealing credentials.
2. Rogue posts one clearly labelled **TEST / NO EXECUTION** Issue comment to architect-gateway Issue #3 with unique event ID, UTC time, source role, exact benign evidence link/commit and desired reply. GitHub identity is shared; never interpret this as Matt approval.
3. The Architect independently opens Issue #3 through its connected GitHub integration, verifies event and evidence, writes a correlated *clarification/ack* (not authorisation).
4. Rogue fetches the same Issue comments and returns an answer containing the original correlation ID. Try a duplicate read/restart and confirm Rogue does not re-execute or issue a duplicate side effect.
5. If gh or the Architect's connection fails, report **BLOCKED/NOT DELIVERED**, preserve event identity and pending requirement, and avoid optimistic completion.

**Stage C: later authorised ForgeV2 PL handoff (NOT part of initial smoke test).**
- After exact-WO approval, verified execution HOST/ROOT/WORKTREES, suitable PL login/rights, and current engine gate acceptance, Rogue starts one fresh PL via the **installed** plugin/ORCHESTRATOR.md command. Inspect JSON outcome and independent evidence; never run a WO directly from the root Rogue process. The plugin cannot magically execute on a remote host because a WO states a remote HOST.
- The permitted output is an assessed candidate and next Architect gate, not an unreviewed merge.

**Stage D: future IONOS durable inbox / MCP adapter (NOT part of initial smoke test).** Govern separately in architect-gateway; do not mistake a working GitHub exchange for a running MCP connection, automatic Architect wake-up, or unattended architectural supervision.

## Practical outcome and failure semantics

A successful setup can say **ROGUE ROLE BOOT VERIFIED** only when the role/router are actually loaded from pinned files and a project GitHub status is independently checked. **ARCHITECT↔ROGUE ROUND-TRIP VERIFIED** requires the test message, independent Architect read, correlated response and Rogue readback, all with real GitHub evidence. A proposal, a Claude scratchpad or a local success assertion is not that evidence.

If the original Rogue identity file still exists on another host, inspect/reconcile it before replacing an active Orchestrator. The current IONOS inventory report found **no local ROGUE.md** and proposed an unattached scratchpad role draft, but CGPT has not accessed that scratchpad. Preserve it for comparison if available; do not represent it as reviewed or identical to this role.

## Required gates and change control

The canonical Rogue role and bootstrap are adopted into FOUNDRY after Matt/Architect review and merge. FOUNDRY Issue #2's earlier unapproved setup Work Order remains a separate historical proposal to reconcile or close without silently treating its conflicting provisions as adopted. A repo PR is not deployment approval. Host changes (new /srv/rogue files, ownership or startup automation), new gh authentication, PL dispatch and live deployment each require their own applicable bounded authority. Keep those gates proportionate: one narrowly scoped host-adoption decision may cover reversible installation and a non-destructive smoke test, without re-asking on every read.

**Do not update FOUNDRY/ForgeV2 installations on the deployment server as part of adopting this role.** The copy belongs in /srv/rogue; the master role belongs in FOUNDRY; product/event records belong in their own GitHub repositories.
