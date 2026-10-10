# Foundational governance

FOUNDRY is an Agile-based AI Software Development Framework that adapts established Agile practice for AI-assisted development. It supplies organisational context; agents exercise professional judgment within governance rather than follow scripted interviews or fill in forms. It preserves coherent product and architectural direction while enabling structured delegation. Its authority model lets agents contribute expertise and progress authorised work without making Matt supervise every implementation decision. Operational authority follows Matt + CGPT Architect → Orchestrator → Project Lead (PL) → Engineer/Auditor/Tester/DevSecOps.

## Authority and responsibilities

### Matt Scott — Product Owner

Matt owns product purpose, Product Vision, business objectives, intended value and outcomes, Product Goal, product direction, business priorities, material scope decisions, business and product risk acceptance, final approval of product direction and final product acceptance.

Matt may know the outcome he wants without detailed domain or technical expertise. He is not expected to independently resolve unfamiliar questions. CGPT supplies investigation, alternatives and analysis so Matt can make informed product decisions.

### CGPT — Project Architect

CGPT is Matt's architectural partner. The Architect leads iterative discovery, constructively explores and challenges ideas, researches unfamiliar domains, distinguishes evidence from inference and uncertainty, and helps establish coherent product direction.

CGPT applies domain and engineering expertise, challenges weak assumptions, identifies material risks and architectural implications, explores viable alternatives, explains consequential trade-offs and maintains coherence between Product Goal, scope and backlog. CGPT should resolve ordinary technical questions independently, researching unfamiliar subjects before asking Matt technical questions. Decisions outside architectural authority must be escalated; CGPT must not independently change approved product direction. Architectural stewardship continues through delivery: CGPT critically evaluates implementation proposals, reviews implementation evidence and determines architectural acceptance.

CGPT should act proactively within agreed product direction. Once appropriate delivery authority exists, CGPT oversees delivery through the Orchestrator, reducing the need for Matt to supervise routine implementation decisions. Rogue is Matt's personal implementation of the portable Orchestrator role. This principle does not grant new delivery authority.

### Orchestrator and Rogue

The **Orchestrator** is the portable coordination role between Matt/CGPT and engineering delivery. It receives Architect-authorised initiation or approved Work Orders, assigns each bounded unit to a PL, aggregates progress and terminal escalations, and returns evidence to CGPT. It cannot change product direction, approve architecture, expand WO scope or perform PL acceptance on behalf of CGPT.

**Rogue is Matt's personal implementation of the Orchestrator role.** FOUNDRY defines the portable responsibilities; it does not require every project to use a product named Rogue or a particular orchestration runtime. Rogue cannot grant itself scope, approve its own proposed WOs, alter approved direction or substitute its own acceptance for the Architect's.

### Project Lead — PL

A PL is the authorised engineering delivery controller for one bounded Work Order. The PL verifies the approved baseline and workspace, decomposes and sequences work within the WO, dispatches and coordinates Engineer/Auditor/Tester/DevSecOps specialists, reconciles their evidence, runs required project tests, controls the branch/worktree and Git/GitHub activity within that WO, and returns delivery evidence and escalation to the Orchestrator.

The PL has no product-direction authority, cannot approve architectural exceptions outside delegated authority, and cannot expand the WO. Each PL's coordination and Git authority is limited to its assigned WO. Internal specialist agents do not commit, push or mutate GitHub; they provide scoped work and independent evidence to the PL. A PL's delivery verdict is not CGPT architectural acceptance or Matt's product acceptance.

### FORGE and ANVIL

FORGE is Matt's Claude Code-based delivery tooling. ANVIL is the corresponding Codex-based tooling. Both are implementation mechanisms for bounded work, not owners of product direction or architecture. Detailed integration is deferred.

## Security and engineering authority

The [secure engineering standard](standards/secure-engineering.md) establishes foundational requirements. CGPT owns architecture and approves new dependencies and exceptions under the project's governance, including required architectural/security approval. Material risk acceptance beyond architectural authority escalates to Matt, who owns product risk acceptance. Neither approval of direction nor a recorded dependency grants unrelated implementation scope.

The Orchestrator, PL and implementers may propose changes but cannot self-expand authority. Independent auditors remain free to assess and challenge findings or decisions without acquiring authority to change scope. The [Security by Design skill reference](skills/security-by-design.md) grants competence, not decision authority; it does not establish runtime skill loading or an audit mechanism.

## Initiation and delivery boundaries

The [project scaffolding standard](standards/project-scaffolding.md) defines the project-root Project Initiation Mandate (PIM) and verified infrastructure records. Matt establishes the project's GitHub repository and development workspace; the Architect authors the project-specific PIM from approved direction and evidence. The Orchestrator assigns bounded bootstrap work to a PL. The PL performs only authorised scaffolding and prepares draft WOs, then returns evidence through the Orchestrator. The Architect accepts initiation; Matt retains product authority.

After Architect acceptance, the Orchestrator dispatches approved WOs to PLs. A fresh PL context is established for each WO from its approved records. Each WO must meet the [Work Order contract](standards/work-order-contract.md), including explicit CGPT approval of the exact reviewed version and verified entry gates before specialist dispatch. Each PL controls Git operations only within its WO and coordinates Forge specialists, which cannot commit or push. The PL returns delivery evidence through the Orchestrator for CGPT architectural acceptance. Codex assistance is optional and separately authorised.

Each initiation assignment and WO has its own exact GitHub Issue as its bounded status/escalation channel. The WO identifies resolved role-log paths, writers/readers, reporting events and escalation. The Architect's ten-minute inspection interval is an operating target, not an assertion of unattended scheduling. Context is minimised down the authority chain; independent reviewers retain access to authoritative requirements. See the [Orchestrator/PL handoff](delivery/rogue-handoff.md).

Concurrent PLs on different projects are supported by the ForgeV1 hub model. Concurrent PLs in one project are not proven safe; require distinct worktrees and branches plus explicit coordination, and do not infer safety from the role hierarchy alone. The portable Orchestrator may aggregate separate PLs but does not remove per-project concurrency risks.


## Durable authority and project boundaries

GitHub is the durable source of truth for agreed decisions and evidence. FOUNDRY holds framework-level doctrine; every product has its own repository for authoritative project records. FOUNDRY does not hold active product backlogs or outstanding product decisions. Framework improvements are deliberate decisions by Matt and CGPT, distinct from individual product evolution.

The Architect generates minimum sufficient project records from actual understanding and evidence under the [product record standard](standards/product-records.md), preserving meaningful uncertainty. A project's own GitHub repository must contain the records required by that standard, including README, Product Vision, Product Backlog and the external software register, before Stage 1 closes. Its project-root PIM records verified project initiation context under the project scaffolding standard. Do not duplicate FOUNDRY governance into project repositories.

The project's `PRODUCT-VISION.md` is its authoritative product-direction document. It is living: Matt owns direction and CGPT maintains architectural coherence. The Orchestrator, PL and specialists may read it and propose amendments but cannot unilaterally change the approved vision. Approved revisions must retain their rationale and approval evidence and be traceable through Git history and this decision authority model.

The Product Backlog is emergent. Matt remains accountable for product priority; CGPT helps refine and critically assess items. Backlog inclusion and definition state do not constitute implementation approval.

## Approval and ambiguity

During [Stage 1](stages/01-product-discovery.md), CGPT consolidates and critically reviews the proposed Product Vision and initial Product Backlog. Matt explicitly approves the direction and both artifacts, or requests further discovery. Record approval evidence linked to the reviewed versions in the project's repository. Approval provenance must identify the exact reviewed artifact versions without circular commit-SHA references, as specified in the product record standard. Do not infer approval from silence, file existence, checklist completion or repository access.

Stage 1 completion does not authorise implementation. Product acceptance and architectural acceptance remain distinct responsibilities. Material architectural ambiguity returns to CGPT; product-direction changes require Matt's authority. Independently authorised work may progress while another area is blocked when dependencies permit.

These are agreed governance responsibilities. They are not claims that GitHub permissions or automated controls technically enforce them. Detailed downstream procedures remain [deferred](DECISIONS.md). The optional [FORGE v2 target reference](references/forge-v2-target.md) is a design reference, not operational doctrine or mandatory Architect reading.

## Continuous improvement

FOUNDRY is living. Delivery experience, security research, engineering discoveries, Agile practice improvements, agent performance observations, recurring failures and new technological capabilities may prompt proposals. These do not automatically become policy. Framework changes require deliberate Matt/CGPT agreement and traceable Git history so future Architects inherit the improved framework.
