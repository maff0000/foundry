# Work Order contract and entry gates

## Purpose and authority

A Work Order (WO) is the bounded, approved authorization for one engineering delivery unit. **One WO corresponds to one bounded ForgeV2 delivery cycle.** One Product Backlog Item (PBI) may be delivered through multiple WOs; a PBI is not itself implementation authority. A Project Initiation Mandate (PIM) establishes initiation context, not authority to implement application changes. Approval of the Product Vision or Product Backlog does not approve a WO.

The Project Architect (CGPT) approves engineering delivery within the approved product and architectural scope. A PL may prepare and refine a draft WO but cannot approve it or dispatch its own draft. The Orchestrator dispatches an approved WO to a PL. Matt retains product direction, priorities, material product-risk decisions and final product acceptance. Product-direction changes, priorities or material product-risk acceptance requiring Matt's decision must be resolved before affected work proceeds. Approval authority does not expand scope beyond the reviewed WO.

This standard defines the minimum content and entry conditions, not a blank form, scripted interview, orchestration mechanism or claim of technical enforcement. The WO author creates the actual contract from verified project context and approved decisions. Unknown information remains explicit; missing authority, evidence or constraints are not invented.

## Required contract content

An approved WO MUST communicate the following information clearly enough for a PL to control delivery and for each specialist to act within a bounded assignment.

### Identity, purpose and authority

- A stable WO identifier and its exact GitHub Issue URL.
- The parent PBI identifier and the approved product outcome/value being advanced.
- Applicable architectural decisions and approved product records.
- The governing FOUNDRY repository revision and the paths/versions of applicable standards and decisions. Carry the requirements needed for the assigned work or point to those exact sources; a specialist is not expected to read the entire framework.
- The applicable PIM and, where relevant, a product-specific PID, approved amendments or other governing artifacts. A PIM is initiation context; it does not substitute for a ForgeV1 PID or an approved WO.
- The exact reviewed WO artifact version and CGPT approval evidence for that version. Identify the approver, decision, timestamp, and immutable artifact reference.
- The PL or delivery assignment authorized by the Orchestrator, including any assigned delivery context and boundaries.

### Repository and workspace

- Exact GitHub repository identity and the verified starting commit SHA.
- The authorized branch and worktree boundary, including what repository state must remain untouched.
- Actual verified development host and workspace/worktree details needed for this WO, with their evidence and availability status.
- Any repository-specific access, submodule, generated-file or working-tree prerequisites relevant to safe work.

Repository, host, path, IP address and SSH alias are project facts, not FOUNDRY defaults. Record only values actually verified for this project and WO. A host or workspace that is unavailable or ambiguous blocks dependent work; do not substitute a familiar environment by assumption.

### Delivery boundary

- The intended outcome and its connection to the approved product direction.
- Explicit in-scope files, components, behavior or investigation, stated at a useful level of precision.
- Explicit exclusions, prohibited changes and protected files, components, branches or environments.
- Dependencies and prerequisites, with their verified state and owners where relevant.
- Applicable architectural constraints, compatibility requirements and implementation limits.
- The required engineering skills, specialist roles and applicable FOUNDRY standards, including the [secure engineering standard](secure-engineering.md) and [Security by Design skill reference](../skills/security-by-design.md).

Scope must be sufficient to identify what may change and what must not change. Unlisted work is not implicitly authorized. A specialist receives only the WO information and authoritative references needed for its assigned role; minimum context does not permit omission of requirements or guardrails material to that role.

### Quality, security and evidence

- Observable, testable acceptance criteria tied to the intended outcome.
- Required automated tests and expected evidence, including commands or project-specific procedures when known and verified.
- Functional and real-browser verification where applicable to the changed behavior. Record what must be observed and what evidence is required; a skipped or unavailable check is not a pass.
- Required independent Auditor review and DevSecOps assessment, their scope, evidence expectations and reporting paths. Each must report a reasoned result; a non-applicable assessment requires an explicit, evidence-based rationale and Architect approval before dispatch.
- Relevant dependency restrictions and approvals, and the product's external-code register/provenance controls under the secure engineering standard. Do not approve new dependencies by implication.
- Required evidence for acceptance, including test results, review findings, security assessment, changed paths and any unresolved limitations.

Verification must be proportionate to risk while meeting every explicit criterion. A failure, unavailable environment or incomplete required assessment is not a pass and cannot be hidden by aggregate status.

### Communications and completion

- The exact GitHub Issue URL used for WO status, evidence references and escalation.
- Exact WO-specific log locations for PL and each participating specialist, and the writers/readers for each location. These are project-specific paths and must be verified rather than guessed.
- Concise, event-driven progress reporting expectations and who receives each escalation.
- The required completion report: outcome, changed paths, starting and final commit identities, acceptance criteria and verification results, independent audit and DevSecOps outcomes, evidence locations, deviations, limitations and remaining risks/questions.

The PL owns the authoritative WO delivery record and reports aggregate progress, blockers and final evidence through the Orchestrator to CGPT. Specialist findings and work remain attributable to their role logs. The GitHub Issue is a communication and traceability channel; its existence or contents alone do not grant scope or constitute approval.

### Execution and stop boundaries

- One WO is one bounded ForgeV2 delivery cycle. It cannot be split, replaced or reopened as a bypass for an exhausted execution limit.
- Engineer, Auditor, Tester and DevSecOps each have an independent execution counter for the WO. A maximum of four executions per specialist, including the first invocation, is permitted; a fifth is prohibited. Counts persist across agent restarts and context resets.
- Each specialist checks its own execution limit. The PL owns the authoritative persisted per-specialist execution state for the WO and records the state in the WO-specific PL evidence/log location identified by the contract. A counter cannot be reset to evade its bound, and a replacement WO cannot be created to bypass exhaustion.
- Exhaustion produces FAIL with the reason and evidence. Only Engineer escalates an execution failure to the PL; the PL reports aggregate progress or terminal escalation through the Orchestrator.
- Material architectural ambiguity returns to CGPT. Product-direction, priority or material product-risk decisions return to Matt through the governance chain. A PL, Orchestrator or specialist cannot expand authority or scope by interpretation.
- Any failed entry prerequisite or blocking condition produces BLOCKED with the specific reason and evidence. Stop affected work until the authorized decision or missing prerequisite is resolved. Do not silently bypass gates.

These are documentary requirements for authorised work, not proof that counters, permissions, tools or workflow gates are technically enforced. Exact runtime, storage and enforcement mechanisms remain unimplemented design work.

## Approval provenance and version changes

The WO MUST be an identifiable artifact in the product's GitHub repository and linked to its exact GitHub Issue. Before approval, preserve the candidate WO in an immutable repository version, such as a commit containing its path and content. CGPT's explicit approval MUST be recorded through a traceable GitHub mechanism and identify the exact artifact path and immutable version reviewed. For example, an explicit CGPT-authored approval comment on the WO Issue can name the repository, path and already-existing commit SHA; GitHub records the commenting identity and time. The comment records the authorized decision but does not create broader scope. A subsequent change to that content requires a new identifiable version and renewed Architect approval before dispatch.

The approval record must identify the approver, explicit decision, date/time, artifact path and immutable version (for example, the already-existing commit SHA containing the WO). Create the artifact version first and record approval afterward; do not place a commit SHA in the artifact that purports to identify the commit introducing that same content. A branch name, open Issue, document's presence, silence, checklist, or approval of an earlier version is not approval of the current WO. Matt's product decisions and material risk acceptance must also be separately evidenced when applicable.

The Orchestrator dispatches only the exact Architect-approved WO version. If the WO changes after approval, pause dispatch or affected work and return the revised version for review. This defines approval evidence, not a mandatory pull request, merge sequence or automated permission control.

## Entry gates before specialist dispatch

Before dispatching any Engineer or other delivery specialist, the PL MUST verify and record that:

1. The WO has a stable identifier, exact Issue, immutable artifact version and explicit CGPT approval evidence for that version.
2. Product decisions requiring Matt's authority are recorded; the requested work remains within approved product and architectural scope.
3. Repository identity and the starting commit are verified against the approved WO.
4. The active branch and worktree are confirmed to belong to the correct project and WO, with the authorized boundaries and protected state understood.
5. The actual required host/workspace is verified and available; no environment value has been presumed or substituted.
6. Intended outcome, change scope, exclusions, dependencies and prerequisites are sufficiently clear and verified for responsible execution.
7. Acceptance criteria are observable and testable; required tests, functional/browser verification, independent audit and DevSecOps assessment are defined with evidence expectations.
8. Applicable architectural, engineering, security, dependency and external-code requirements are identified, with required approvals present.
9. Exact Issue and per-role log locations, writers/readers, reporting expectations and escalation routes are available and verified.
10. No unresolved blocker prevents responsible execution, and required specialist execution state can be recorded by the PL.

If any gate fails, the PL records **BLOCKED**, identifies the failed condition and supporting evidence, and reports through the Orchestrator. The Architect resolves architectural ambiguity; Matt resolves product-authority decisions. Work may resume only after the relevant authority resolves the blocker and the entry conditions are re-verified. A PL cannot waive a gate, infer approval or dispatch around a failure.

## ForgeV1 and ForgeV2 intake boundary

ForgeV1 remains operational and unchanged. Its existing `PID.md` and startup gate remain ForgeV1 requirements. FOUNDRY's PIM is a distinct initiation-context artifact and does not replace, satisfy or modify that PID gate. The approved WO is a further, separate authorization artifact: neither a PIM nor a PID alone approves engineering delivery under this contract.

The intended ForgeV2 intake is that an Orchestrator supplies the PL with the exact approved WO version and relevant project records; the PL verifies this contract's entry gates before dispatching specialists. The ForgeV2 mechanism for representing or consuming product-initiation context, and whether it uses a PID-like artifact in addition to FOUNDRY's PIM and approved WO, remain design decisions. This standard does not prescribe an agent prompt format, runtime gate, orchestration behavior or ForgeV2 implementation.
