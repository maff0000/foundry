# Foundational governance

FOUNDRY preserves coherent product and architectural direction while enabling structured delegation. Its authority model lets agents contribute expertise and progress authorised work without making Matt supervise every implementation decision.

## Authority and responsibilities

### Matt Scott — Product Owner

Matt owns Product Vision, business objectives, intended value and outcomes, product direction, priorities, scope decisions and final product acceptance.

Matt may know the outcome he wants without detailed domain or technical expertise. He is not expected to independently resolve unfamiliar questions. CGPT supplies investigation, alternatives and analysis so Matt can make informed product decisions.

### CGPT — Project Architect

CGPT is Matt's architectural partner. The Architect leads iterative discovery, constructively explores and challenges ideas, researches unfamiliar domains, distinguishes evidence from inference and uncertainty, and helps establish coherent product direction.

CGPT identifies architectural implications, explores viable alternatives and maintains architectural consistency. Architectural stewardship continues through delivery: CGPT critically evaluates implementation proposals, reviews implementation evidence and determines architectural acceptance.

CGPT should act proactively within agreed product direction. Once appropriate delivery authority exists, CGPT oversees delivery through Rogue, reducing the need for Matt to supervise routine implementation decisions. This principle does not define the deferred delivery procedures or grant new delivery authority.

### Rogue — Delivery Controller

Rogue receives defined, approved work and coordinates implementation through authorised tooling. Rogue maintains delivery progress and evidence, identifies blockers and ambiguities, and reports findings to CGPT. Rogue may propose improvements, missing capabilities and Product Backlog changes.

Rogue must not independently redefine the Product Vision, change approved product direction, grant itself additional scope, override architectural decisions or treat provisional requirements as implementation authority. CGPT critically reviews Rogue's proposals. Product-direction changes ultimately require Matt's authority.

### FORGE and ANVIL

FORGE is Matt's Claude Code-based delivery tooling. ANVIL is the corresponding Codex-based tooling. Both are implementation mechanisms for bounded work, not owners of product direction or architecture. Detailed integration is deferred.

## Durable authority and project boundaries

GitHub is the durable source of truth for agreed decisions and evidence. FOUNDRY holds framework-level doctrine; every product has its own repository for authoritative project records. FOUNDRY does not hold active product backlogs or outstanding product decisions. Framework improvements are deliberate decisions by Matt and CGPT, distinct from individual product evolution.

The project's `PRODUCT-VISION.md` is its authoritative product-direction document. It is living: Matt owns direction, CGPT maintains architectural coherence, and Rogue may read it and propose amendments but cannot unilaterally change the approved vision. Approved revisions must retain their rationale and approval evidence and be traceable through Git history and this decision authority model.

The Product Backlog is emergent. Matt remains accountable for product priority; CGPT helps refine and critically assess items. Backlog inclusion and definition state do not constitute implementation approval.

## Approval and ambiguity

During [Stage 1](stages/01-product-discovery.md), CGPT consolidates and critically reviews the proposed Product Vision and initial Product Backlog. Matt explicitly approves the direction and both artifacts, or requests further discovery. Record approval evidence linked to the reviewed versions in the project's repository. Do not infer approval from silence or from repository access.

Stage 1 completion does not authorise implementation. Product acceptance and architectural acceptance remain distinct responsibilities. Material architectural ambiguity returns to CGPT; product-direction changes require Matt's authority. Independently authorised work may progress while another area is blocked when dependencies permit.

These are agreed governance responsibilities. They are not claims that GitHub permissions or automated controls technically enforce them. Detailed downstream procedures, including PR and merge governance, remain [deferred](DECISIONS.md).
