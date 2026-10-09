# Secure engineering standard

## Purpose and applicability

Engineering quality and Security by Design are foundational requirements of FOUNDRY's AI-first Agile development. This is the authoritative engineering and security standard for project initiation and authorised AI-agent development. Apply professional judgment proportionate to project risks; these are requirements, not a scripted workflow or a claim of technical enforcement.

All coding agents inherit the applicable foundational requirements. The [Security by Design skill reference](../skills/security-by-design.md) describes the competence needed to apply them. [Governance](../GOVERNANCE.md#security-and-engineering-authority) determines decision authority; a skill or access to tools grants none.

## Reuse-first engineering

Before creating an implementation, inspect the project's existing functions, modules, services, templates and components. Reuse suitable implementations; extend them when responsibilities remain coherent. Otherwise create purposeful, reusable implementations with clear responsibilities. Avoid unnecessary duplication, premature abstraction and monolithic global utility files. Reuse does not remove the obligation to assess suitability and security.

## Component-first user interfaces

Each project owns its design tokens, CSS, reusable UI components and page structures. Inspect and reuse established styles and components instead of repeatedly hardcoding visual properties or recreating equivalent elements. Introduce new components only where the existing design cannot coherently meet the need.

## Project isolation

Each application owns its code and reusable assets. Cross-project source-directory dependencies are prohibited. Independently versioned shared packages may be considered only through approved dependency governance and the controls below. This standard does not create or mandate a shared library, physical host layout or worktree convention.

## Controlled third-party software

Approved third-party software is permitted only with identifiable provenance, an exact version or hash identifying the incorporated code, suitable licensing, vulnerability and supply-chain assessment, awareness of transitive dependencies, and required architectural/security approval under project governance.

Assess components before trusting or executing them, including during installation and builds. Review evidence relevant to origin, integrity, intended use and execution privileges; a scan result alone does not establish safety. New dependencies and exceptions require CGPT's approval within project governance, with material risk beyond architectural authority escalated to Matt under [Governance](../GOVERNANCE.md#security-and-engineering-authority). Implementers cannot approve their own scope expansion.

Applications execute approved dependencies locally within controlled builds and deployments. Runtime loading, downloading or execution of externally hosted code, including CDN-hosted JavaScript, is prohibited without an explicit approved exception. Legitimate data-service/API integrations are distinct from remotely obtained executable code: assess their trust boundaries, sensitive data, access and other security risks separately. Network egress should follow project security policy. These requirements do not define build, deployment or egress enforcement machinery.

## External software register

Every product repository MUST maintain `security/EXTERNAL_CODE_REGISTER.yaml` as its authoritative project-level register of externally sourced executable code and dependencies. Its scope includes copied or vendored code, direct dependencies, relevant transitive components and applicable base images.

For incorporated components, capture identity, origin, exact version/hash, local location, application usage or consumers, purpose, licence, approval/security evidence and inventory coverage status. Record actual knowledge and evidence; unknown facts or missing approvals must remain explicit, not be replaced with invented entries or fake placeholder fields. Inclusion in the register is not approval to use or execute a component.

The register must truthfully describe what has been inspected and what remains outside verified coverage. A new unimplemented product may accurately report no incorporated code, with the basis for that conclusion. An existing product whose inspection is incomplete must report unverified or incomplete coverage, including known gaps; absence of discovered entries does not establish absence of external code. Do not assert complete coverage without verification. Known incorporated but unapproved components must remain visible with their actual status for architectural assessment rather than being omitted or retrospectively labelled approved.

A generated software bill of materials (SBOM) supplements this register and should be preferred for dependency enumeration. Reference its scope and evidence where available; it does not replace approval, usage context or coverage assessment. Exact automation, YAML schema and schema enforcement remain deferred. No register is created in FOUNDRY on behalf of an individual product.

## Security context during initiation

During both NEW discovery and EXISTING reconciliation, the Project Architect MUST establish project-relevant security context and constraints proportionate to risk: trust boundaries, sensitive information, security risks, deployment/execution assumptions and third-party code expectations. Preserve this understanding and significant uncertainty in the [project records](product-records.md#security-context-and-provenance).

For NEW products, distinguish proposed dependencies and execution assumptions from incorporated code and approvals actually granted. For EXISTING products, reconcile claims against implementation and operational evidence without executing unassessed components merely to discover their behaviour. Use the Stage 1 evidence classifications and report inspection gaps honestly.

Before [Stage 1](../stages/01-product-discovery.md) closes, establish the external software register and truthfully describe its coverage. Incomplete inspection is not proof of safety: CGPT assesses whether uncertainty blocks responsible product-direction approval, escalating product risk acceptance as required. Do not invent complete coverage as a condition for filling a record. All existing Stage 1 review and approval gates continue to apply.

## Evidence and boundaries

Preserve consequential security findings, dependency assessments, approvals, exceptions and accepted risks as traceable project evidence. Distinguish observed behaviour, inference and unverified claims. Written policy and recorded competence do not prove implemented controls or security outcomes.

Security implementation, delivery automation, scanners, SBOM generators, audit systems or agents, runtime skill loading and automatic enforcement are not introduced by this standard. Detailed Work Order contracts, FORGE cycles, ANVIL integration and downstream lifecycle design remain [deferred](../DECISIONS.md). Establishing security context and records during Stage 1 does not authorise implementation.
