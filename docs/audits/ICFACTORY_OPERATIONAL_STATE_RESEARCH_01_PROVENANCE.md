# ICFACTORY-OPERATIONAL-STATE-RESEARCH-01 — Provenance Register

**Date:** 2026-09-01  
**Status:** PUBLISHED_RESEARCH_EVIDENCE / NON_NORMATIVE  
**Companion synthesis:** `ICFACTORY_OPERATIONAL_STATE_RESEARCH_01.md`  

## 1. Purpose

Preserve reconstructible provenance for the material findings of `ICFACTORY-OPERATIONAL-STATE-RESEARCH-01`.

Required traceability:

```text
SOURCE
→ EVIDENCE
→ INTERPRETATION
→ FINDING
→ LIMITATION
→ DECISION
```

A conclusion without recoverable provenance is not treated as a fully preserved research result.

---

## 2. External source register

### EXT-01 — ISO/IEC/IEEE 12207:2026

- Authority: ISO/IEC/IEEE.
- Document: `ISO/IEC/IEEE 12207:2026 — Systems and software engineering — Software life cycle processes`.
- Public source: https://www.iso.org/standard/90219.html
- Accessed: 2026-09-01.
- Public status observed during research: published April 2026; 2017 edition superseded/withdrawn.
- Supports: software lifecycle scope including operation and maintenance.
- Does not support from the public summary: exact `VALIDATED → ACTIVE/CURRENT/PRIMARY` edge or universal cutover-authority semantics.
- Classification: `LIFECYCLE_FOUNDATION / NOT_DEMONSTRATED_FOR_EXACT_EDGE`.

### EXT-02 — IEEE 828 / P828

- Authority: IEEE Standards Association.
- Public source: https://standards.ieee.org/ieee/828/5367/
- Accessed: 2026-09-01.
- Public status observed: IEEE 828-2012 shown as Inactive-Reserved; P828 is the active replacement project.
- Supports from public scope: configuration management, change control, configuration status, builds and release engineering.
- Does not support from public material: exact universal authorization boundary for runtime cutover.
- Classification: `SUPPORTED_CONFIGURATION_MANAGEMENT_CONTEXT`.

### EXT-03 — NIST SP 800-128

- Authority: National Institute of Standards and Technology.
- Document: `NIST SP 800-128 — Guide for Security-Focused Configuration Management of Information Systems`.
- Primary source: https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-128.pdf
- Accessed: 2026-09-01.
- Supports:
  - formal change request;
  - analysis/testing;
  - approval/disapproval;
  - implementation of approved change by authorized personnel;
  - implementation verification;
  - affected components and impacts;
  - implementation plan/date;
  - deliverables;
  - back-out plan;
  - closure after deployment confirmation.
- Material interpretation: approval applies to an identifiable change and its recorded scope; it is not evidence of unlimited permission for every related action.
- Limitation: NIST does not prove that every organization must use one universal authority model.
- Classification: `DEMONSTRATED_FOR_CONTROLLED_CHANGE_AND_SCOPE`.

### EXT-04 — NIST CM-3 / configuration change control

- Authority: NIST.
- Public NIST control material consulted during adversarial audit.
- Supports: identify configuration-controlled changes; approve/disapprove controlled changes; implement approved changes; monitor change activity; automated enforcement may prevent action until designated approvals exist.
- Limitation: does not establish a universal distinct cutover-authority role.
- Classification: `DEMONSTRATED_CONTROL_PATTERN`.

### EXT-05 — NASA Configuration Management

- Authority: NASA.
- Source: https://www.nasa.gov/reference/6-5-configuration-management/
- Accessed: 2026-09-01.
- Supports: configuration change management of approved designs and implementation of approved changes; proposal/evaluation/incorporation/verification; contextual change authority/CCB.
- Limitation: NASA project governance is not automatically ICFACTORY or PROTEUS authority.
- Classification: `DEMONSTRATED_GOVERNED_CHANGE_PATTERN`.

### EXT-06 — NASA lifecycle configuration management

- Authority: NASA.
- Source used during research: NASA NPR 7123 lifecycle/configuration-management material, including approval before implementation, incorporation of approved changes, release of changed configuration items for use, and monitoring of unintended effects.
- Accessed: 2026-09-01.
- Supports: an approved change can progress through implementation and release-for-use under a governed lifecycle.
- Limitation: does not prove universal second-authorization or same-authority rules.
- Classification: `DEMONSTRATED_LIFECYCLE_PATTERN`.

### EXT-07 — Google SRE — Canarying Releases

- Authority: Google SRE.
- Source: https://sre.google/workbook/canarying-releases/
- Accessed: 2026-09-01.
- Supports: partial/time-limited deployment; coexistence of canary and control; evaluation before continuation of rollout.
- Finding supported: `DEPLOYED != FULLY_EXPOSED`; multiple configurations can participate in production.
- Limitation: operational engineering evidence, not authority-identity evidence.
- Classification: `DEMONSTRATED_OPERATIONAL_PATTERN`.

### EXT-08 — Google SRE — Reliable Product Launches / rollout practices

- Authority: Google SRE.
- Source: https://sre.google/sre-book/reliable-product-launches/
- Accessed: 2026-09-01.
- Supports: gradual rollout, intermediate verification, automation and rollback patterns.
- Finding supported: automation can perform controlled/predefined rollout actions without evidence that automation acquires independent governance authority.
- Classification: `DEMONSTRATED_OPERATIONAL_PATTERN`.

### EXT-09 — Kubernetes Deployments

- Authority: Kubernetes documentation.
- Sources consulted:
  - https://kubernetes.io/docs/concepts/workloads/controllers/deployment/
  - https://kubernetes.io/docs/tasks/run-application/update-deployment-rolling/
- Accessed: 2026-09-01.
- Supports: multiple ReplicaSets/revisions may coexist during rollout; rollout can be paused/resumed/changed.
- Finding supported: one system does not necessarily have exactly one participating runtime configuration at every instant.
- Limitation: Kubernetes is a technical execution mechanism, not a governance-authority model.
- Classification: `DEMONSTRATED_RUNTIME_MECHANISM / NOT_APPLICABLE_TO_AUTHORITY_IDENTITY`.

### EXT-10 — Microsoft Azure Pipelines approvals/checks

- Authority: Microsoft Learn.
- Source: https://learn.microsoft.com/en-us/azure/devops/pipelines/process/approvals?view=azure-devops
- Accessed: 2026-09-01.
- Supports: environment/stage-specific checks and approvals; production can be protected by a distinct approval gate; approvals can have temporal conditions.
- Finding supported: a distinct production authorization event is possible and valid.
- Limitation: does not prove that a distinct event is universally required.
- Classification: `DEMONSTRATED_CONTEXTUAL_GOVERNANCE_PATTERN`.

### EXT-11 — Microsoft Azure progressive / mission-critical deployment

- Authority: Microsoft Learn / Azure Well-Architected Framework.
- Source: https://learn.microsoft.com/en-us/azure/well-architected/mission-critical/mission-critical-deployment-testing
- Accessed: 2026-09-01.
- Supports: blue/green and progressive traffic transition; automation may increase exposure after health verification.
- Finding supported: runtime exposure can be a separable operational phase while remaining inside a predefined deployment workflow.
- Classification: `DEMONSTRATED_OPERATIONAL_PATTERN`.

### EXT-12 — Microsoft Azure blue/green approval-race evidence

- Authority: Microsoft Learn.
- Source consulted during adversarial audit: Azure Spring Apps blue-green deployment strategy documentation.
- Accessed: 2026-09-01.
- Supports: approval can become detached from the actually promoted artifact if target identity changes after approval.
- Finding supported:

```text
AUTHORIZED_ARTIFACT_IDENTITY
MUST_MATCH
ARTIFACT_ACTUALLY_EXPOSED
```

- Classification: `SUPPORTED_TOCTOU_AND_ARTIFACT_IDENTITY_FINDING`.

### EXT-13 — ITIL

- No sufficiently detailed primary ITIL source was used to support a material conclusion in this research.
- Classification: `NOT_USED_FOR_MATERIAL_FINDING`.

---

## 3. Internal ICFACTORY source register

### INT-01 — CONSTITUTIONAL_LEXICON.md

Repository: `hendersonmauriciobatista-png/icfactory-framework`.

Relevant entries:

- TUX-31 — Escopo De Autoridade;
- TUX-33 — Competência;
- TUX-37 — Proveniência;
- TUX-38 — Evidência Verificável;
- TUX-43 — Vigência;
- TUX-45 — Aprovação Constitucional;
- TUX-60 — Operacionalização De Efeitos Constitucionais.

Material support:

```text
AUTHORITY_HAS_EXPLICIT_SCOPE
COMPETENCE_IS_EXERCISED_WITHIN_SCOPE
PROVENANCE_MUST_BE_TRACEABLE
VERIFIABLE_EVIDENCE_MUST_SUPPORT_INDEPENDENT_EXAMINATION
APPROVAL_DOES_NOT_BY_ITSELF_EQUAL_VALIDITY/VIGENCY/EFFECT
```

Limitation: constitutional semantics do not by themselves prove a current PROTEUS authorization for MCM-WQ production cutover.

### INT-02 — PO-GOV-LIFECYCLE

Path: `docs/governance/product_owner_decisions/LIFECYCLE.md`.

Observed identity at research time:

```text
identity::PO-GOV-LIFECYCLE
version::1.0.0
status::ACCEPTED
effect::IN_FORCE
```

Material support:

```text
REQUESTED → DELIBERATED → ACCEPTED → PROMULGATED
ACCEPTED != PROMULGATED
```

Acceptance does not automatically authorize implementation, publication, execution or effect. Promulgation separately records content identity, competent authority/capacity, effective date, scope, implementation authorization, version/hash when applicable, affected records and predecessor state.

PO-GOV also states that AI, agents, audits, validators and time possess no transition authority.

Limitation: local PROTEUS adoption/applicability for the MCM-WQ cutover was not demonstrated by this research.

### INT-03 — OG-001

Path: `docs/governance/OG-001_SEQUENCIAMENTO_OFICIAL_DAS_ONDAS_DE_MIGRACAO.md`.

Observed state during research:

```text
VERSION::1.1
STATUS::PROMOVIDA_VIGENTE
APPLICABILITY::ICFACTORY_FRAMEWORK
```

Material support:

```text
FORMAL_AUTHORIZATION
→ EXECUTION_EXCLUSIVELY_OF_AUTHORIZED_WAVE
→ AUDIT
→ STATE_VERIFICATION
→ CLOSURE
→ NEXT_AUTHORIZATION
```

OG-001 explicitly treats execution beyond the current wave scope as nonconforming and requires auditable authorization and scope evidence.

Limitation: OG-001 is not itself an MCM-WQ production-cutover authorization.

---

## 4. Finding traceability matrix

| ID | Finding | Principal evidence | Status | Limitation |
|---|---|---|---|---|
| F-01 | `RELEASED != DEPLOYED` | lifecycle/release engineering sources | SUPPORTED | terminology varies by model |
| F-02 | `DEPLOYED != FULLY_EXPOSED` | Google SRE, Azure | DEMONSTRATED | operational, not authority identity |
| F-03 | multiple runtime configurations may coexist | Google SRE, Kubernetes, Azure | DEMONSTRATED | not every system uses progressive delivery |
| F-04 | generic PRIMARY is not required | F-02/F-03 + adversarial semantic audit | SUPPORTED | local systems may define PRIMARY contextually |
| F-05 | authority identity and authorization scope are distinct | TUX-31/TUX-33, NIST | DEMONSTRATED | local authorizer still must be identified |
| F-06 | approval is action/change specific | NIST SP 800-128 | DEMONSTRATED | exact field set is context-dependent |
| F-07 | same authorized change may include cutover if scope includes it | NIST/NASA/Azure synthesis | SUPPORTED | not a universal same-event rule |
| F-08 | separate production approval is possible | Azure approvals | DEMONSTRATED | not universally required |
| F-09 | separate cutover authority is universally required | no supporting universal evidence | NOT_DEMONSTRATED | organization-specific separation may exist |
| F-10 | validation creates authority | no supporting evidence; PO-GOV separation | REFUTED | validation may be a precondition |
| F-11 | automation creates authority | PO-GOV + deployment sources | REFUTED | automation may execute preauthorized actions |
| F-12 | progressive rollout may be preauthorized | Azure/Google + scope model | SUPPORTED | stages must remain within authorized bounds |
| F-13 | rollback may be included in original authorization | NIST back-out plan | SUPPORTED | not automatically implied by cutover approval |
| F-14 | authorization validity is temporal | PO-GOV/Azure | SUPPORTED | exact lifecycle is model-specific |
| F-15 | artifact identity must match authorized target | Azure TOCTOU evidence + scope principle | SUPPORTED | implementation-specific identity mechanism varies |
| F-16 | ICFACTORY already contains general scope/provenance semantics | TUX-31/33/37/38, PO-GOV, OG-001 | DEMONSTRATED | local MCM-WQ binding remains absent |
| F-17 | new generic ICFACTORY concept is required | accumulated evidence | NOT_DEMONSTRATED | future evidence may reopen research |
| F-18 | ALO must be expanded | ALO audit + no necessity after reformulation | NOT_DEMONSTRATED | no scope expansion authorized |
| F-19 | PROTEUS MCM-WQ production cutover is currently authorized | no complete local authorization chain found | NOT_DEMONSTRATED | requires project-local evidence |

---

## 5. Minimum surviving model and provenance

The final generic model is a synthesis of NIST controlled-change evidence, internal TUX authority-scope semantics, PO-GOV decision/effect separation, OG-001 bounded execution, and progressive deployment evidence:

```text
COMPETENT_AUTHORIZER
→ VALID_AUTHORIZATION
→ IDENTIFIABLE_TARGET/ACTION
→ EXPLICIT_AUTHORIZED_SCOPE
→ APPLICABLE_PRECONDITIONS
→ CURRENT_VALIDITY
→ CONTROLLED_EXECUTION
→ TRACEABLE_EVIDENCE
```

This is a research synthesis. It is not introduced here as a new normative ICFACTORY concept.

---

## 6. Provenance limitations

1. Public summaries of ISO/IEC/IEEE 12207:2026 and IEEE 828/P828 were insufficient for the exact cutover authorization edge; no stronger claim is derived from them.
2. No material conclusion depends on an unverified ITIL primary source.
3. Operational deployment sources demonstrate runtime behavior, not governance-authority identity unless the source explicitly addresses approvals/checks.
4. External governance patterns do not assign authority inside PROTEUS.
5. Internal ICFACTORY framework semantics do not automatically establish local project applicability or authorization.
6. `NOT_DEMONSTRATED` is not treated as proof of nonexistence.
7. URLs and document statuses should be revalidated if the research is reopened materially in the future.

---

## 7. Closure assessment

```text
SOURCE_FAMILIES_RECORDED::YES
MATERIAL_FINDINGS_TRACEABLE::YES
SOURCE_LIMITATIONS_RECORDED::YES
REFUTED_HYPOTHESES_PRESERVED::YES
GENERIC_VS_LOCAL_SCOPE_SEPARATED::YES
UNSUPPORTED_ITIL_DEPENDENCY::NO
NEW_CONCEPT_CREATED::NO
NEW_AUTHORITY_CREATED::NO
PROVENANCE_COMPLETENESS_FOR_RESEARCH_CLOSURE::PASS_WITH_DECLARED_LIMITATIONS
```
