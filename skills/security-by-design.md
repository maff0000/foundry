# Security by Design — skill reference

## Purpose and applicability

This reference defines foundational competence for AI agents applying the [secure engineering standard](../standards/secure-engineering.md). All coding agents inherit its applicable foundational security requirements; Architects apply the competence to discovery, reconciliation and architectural assessment. Specialist roles may receive deeper skills later.

This is an AI-readable FOUNDRY reference, not an executable skill, runtime loading mechanism or certification of competence. It grants no decision authority. Apply professional judgment to the actual project and consult [Governance](../GOVERNANCE.md#security-and-engineering-authority) for approvals and escalation.

## Applicable competence

An agent applying this reference should be able to:

- **Secure coding:** identify security consequences of proposed behaviour, unsafe failure modes and misuse cases; reason about safe implementation choices within authorised work.
- **Input and output handling:** recognise untrusted inputs and interpretation boundaries; select context-appropriate validation, encoding and parameterisation, and evaluate unintended disclosure through outputs, logs and errors.
- **Secrets:** recognise credentials and sensitive configuration, reason about their exposure and lifecycle, and select handling that avoids embedding or disclosing secrets in code, records or output.
- **Authentication and authorisation:** distinguish identity verification from permission to act, assess access decisions at relevant boundaries and identify bypass or privilege-escalation risks.
- **Least privilege:** evaluate the permissions required by users, agents, services and build-time code, and identify unnecessary access or execution privileges.
- **Threat and trust boundaries:** identify assets, sensitive information, entry points, actors and transitions in trust; explain material threats and consequential deployment/execution assumptions proportionately to risk.
- **Software provenance and controlled dependencies:** assess origin, integrity, version identity, licence, supply-chain risks and transitive exposure; distinguish data/API consumption from external executable code and apply the standard's approval and register requirements.
- **Evidence:** distinguish verified behaviour from inference, assumptions and unknowns; assess coverage limitations, record consequential findings accurately and explain why scanning alone cannot establish safety.

Use these capabilities to investigate before escalating ordinary technical questions, explain consequential trade-offs and identify gaps in evidence or competence. Do not substitute confidence for verification or product-risk authority. Independent security assessment may challenge conclusions without changing the assessor's scope authority.

## Limits

The secure engineering standard remains the single source of engineering/security requirements; this reference describes the competence to apply it rather than a second policy. Deeper specialist skills, audit protocols, execution tooling and runtime skill-loading mechanics are not defined here. Stage 1 uses this competence for understanding and records, not to begin security implementation.
