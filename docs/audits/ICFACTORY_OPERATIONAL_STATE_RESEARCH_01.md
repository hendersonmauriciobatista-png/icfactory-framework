# ICFACTORY-OPERATIONAL-STATE-RESEARCH-01

**Title:** Operational State, Runtime Cutover and Authorization Scope Research  
**Date:** 2026-09-01  
**Status:** RESEARCH_CLOSED / PUBLISHED / NON_NORMATIVE  
**Origin:** PROTEUS MCM-WQ architectural research  
**Scope:** ICFACTORY generic governance semantics, with PROTEUS local application explicitly separated  
**Implementation authority:** NONE  
**Normative promotion:** NO  

---

## 1. Research question

The research originated from a concrete architectural problem observed during the MCM-WQ migration study in PROTEUS:

```text
AUTHORIZED_CHANGE
→ IMPLEMENTED_CHANGE
→ VALIDATED_CHANGE
→ ?
→ CURRENT_OPERATIONAL_STATE
```

The initial question was whether ICFACTORY lacked a formal mechanism by which an implemented and validated technical state becomes the operationally used state.

This question was intentionally treated as a research problem rather than as immediate justification to create a new state, role, authority, ALO competence or normative mechanism.

The investigation therefore adopted the following fail-safe rule:

```text
DO_NOT_CREATE_ICFACTORY_CONCEPT
BEFORE_EXTERNAL_REFERENCE_ANALYSIS
DO_NOT_MODIFY_ALO
DO_NOT_ASSIGN_NEW_AUTHORITY
DO_NOT_IMPLEMENT_MCM_WQ_CUTOVER
```

---

## 2. Research method

The investigation combined:

1. internal ICFACTORY semantic and governance audits;
2. adversarial hypothesis testing;
3. external reference analysis using authoritative or primary technical sources when publicly recoverable;
4. explicit preservation of refuted hypotheses;
5. separation between generic engineering/governance conclusions and project-local PROTEUS evidence;
6. provenance tracking for each material finding.

The traceability model used for closure was:

```text
QUESTION
→ HYPOTHESIS
→ SOURCE
→ EVIDENCE
→ INTERPRETATION
→ ADVERSARIAL_TEST
→ FINDING
→ DECISION
→ LIMITATION
→ REMAINING_GAP
```

---

## 3. Initial hypothesis — missing operational-state recognition

The first formulation was:

```text
AUTHORIZED_AND_VALIDATED_PROJECT_INTERVENTION
→ GOVERNED_RECOGNITION_OF_NEW_OPERATIONAL_STATE
```

A negative internal audit found that ICFACTORY already governed decision, authorization, execution, validation and effect semantics, but did not demonstrate a generic runtime-state edge equivalent to:

```text
IMPLEMENTED_AND_VALIDATED_TECHNICAL_STATE
→ FORMALLY_RECOGNIZED_CURRENT/ACTIVE/PRIMARY_RUNTIME_STATE
```

At that stage, the gap was classified as supported by negative audit, not as proof that a new concept was required.

---

## 4. ALO competence audit

ALO was tested as a possible existing authority capable of closing the apparent edge.

The audit distinguished:

```text
ALO_CAN_REPRESENT_CURRENT_STATE
!=
ALO_CAN_CAUSE_A_STATE_TO_BECOME_CURRENT
```

The existing ALO semantics support architectural governance, context representation and coordination of authority and direction. They did not demonstrate constitutive competence to formally establish a validated technical runtime as CURRENT, ACTIVE or PRIMARY.

Result:

```text
ALO_OPERATIONAL_STATE_RECOGNITION_COMPETENCE::NOT_DEMONSTRATED
ALO_SCOPE_EXPANSION::NO
```

No ALO change was authorized or proposed as a closure mechanism.

---

## 5. External engineering research

The investigation then examined established software lifecycle, configuration management and deployment practices.

The public sources consulted included:

- ISO/IEC/IEEE 12207:2026 — software lifecycle processes;
- IEEE 828-2012 public scope and current P828 status;
- NIST SP 800-128 — security-focused configuration management;
- NASA configuration management guidance and lifecycle material;
- Google SRE release engineering and canary/progressive rollout practices;
- Microsoft Azure deployment approvals, blue/green and progressive traffic transition practices;
- Kubernetes Deployment rollout mechanics.

The research did not use a sufficiently detailed primary ITIL source for any material conclusion.

The external evidence established several distinctions:

```text
RELEASED != DEPLOYED
DEPLOYED != FULLY_EXPOSED
VALIDATED != UNIVERSALLY_CURRENT
DEPLOYED_CONFIGURATIONS_MAY_COEXIST
```

Modern canary, rolling and blue/green patterns demonstrate that more than one runtime configuration can participate in production during the same time interval.

---

## 6. Refutation of PRIMARY as a generic required state

A subsequent hypothesis proposed a generic progression such as:

```text
IMPLEMENTED
→ VALIDATED
→ ACTIVE
→ PRIMARY
```

Adversarial analysis rejected PRIMARY as a universal engineering necessity.

A runtime can be represented sufficiently by factual properties such as:

```text
CONFIGURATION_IDENTITY
+
OBSERVED_SERVING_OR_EXPOSURE_STATE
+
TIME_REFERENCE
+
TRACEABLE_EVIDENCE
```

without requiring a generic PRIMARY designation.

The research therefore concluded:

```text
PRIMARY_AS_GENERIC_RUNTIME_STATE::NOT_REQUIRED
CURRENT != PRIMARY
```

PRIMARY can be context-dependent and may mean majority traffic, designated production, preferred route, unique serving configuration or an organizational designation. Treating it as a universal state would create semantic ambiguity.

This removed an artificial destination node from the original problem.

---

## 7. Reformulation toward runtime cutover authority

After removing PRIMARY, the problem became smaller:

```text
CHANGE_AUTHORIZATION
→ CONTROLLED_RUNTIME_EXPOSURE/CUTOVER
```

The next working hypothesis was that a distinct cutover authority might be required.

The adversarial cutover audit produced two simultaneous findings:

```text
CHANGE_AUTHORIZATION
!= AUTOMATIC_CUTOVER_AUTHORIZATION
```

and

```text
CUTOVER
!= NECESSARILY_REQUIRES_A_DISTINCT_AUTHORITY
```

This distinction was decisive.

The generic problem was no longer best expressed as:

```text
WHO_HAS_CUTOVER_AUTHORITY?
```

but as:

```text
IS_THE_RUNTIME_CUTOVER_ACTION
WITHIN_THE_SCOPE
OF_A_CURRENT_VALID_AUTHORIZATION
ISSUED_BY_A_COMPETENT_AUTHORIZER?
```

The gap was therefore reformulated as an authorization-scope problem.

---

## 8. External support for authorization scope

### 8.1 NIST SP 800-128

NIST SP 800-128 describes a controlled change lifecycle in which a proposed change is analyzed, tested, approved, implemented by authorized personnel and verified. Its sample change-request artifact identifies the change, affected components, impacts, implementation plan/date, deliverables, approval and a back-out plan.

This supports:

```text
AUTHORIZATION
IS_ATTACHED_TO
AN_IDENTIFIABLE_CHANGE_AND_SCOPE
```

and rejects the inference:

```text
"THE_CHANGE_WAS_AUTHORIZED"
==
"EVERY_ACTION_RELATED_TO_THE_CHANGE_WAS_AUTHORIZED"
```

The content of the approval matters.

### 8.2 NASA configuration management

NASA configuration-management guidance supports governance of approved designs and implementation of approved changes, including evaluation, incorporation and implementation verification. Lifecycle material also supports approval before implementation, release of changed configuration items for use and monitoring of unintended effects.

This demonstrates that a governed approved change can continue through implementation and release-for-use without implying a universal requirement for a second authority.

### 8.3 Azure approvals and progressive deployment

Azure demonstrates that an organization may configure approval/check gates specifically for a production environment or stage. This proves that a distinct production approval event is a valid governance pattern.

It does not prove that such a separate event is universally mandatory.

Azure progressive and blue/green deployment patterns also demonstrate that controlled traffic transition may occur as part of a predefined deployment workflow.

### 8.4 Google SRE and Kubernetes

Google SRE provides evidence of canary and progressive rollout with intermediate evaluation and automated rollback. Kubernetes provides technical evidence that multiple revisions/configurations can coexist during a rollout.

These sources support runtime and automation semantics, but are not used as evidence for governance-authority identity.

---

## 9. Internal ICFACTORY evidence

The investigation then re-audited ICFACTORY itself.

### 9.1 TUX-31 — Escopo De Autoridade

The Constitutional Lexicon defines authority scope as an explicitly defined set of limits, matters, objects, decisions, acts or responsibilities within which an authority or constitutional role may legitimately exercise its competencies.

Therefore:

```text
WHO_CAN_AUTHORIZE?
!=
WHAT_A_SPECIFIC_AUTHORIZATION_ALLOWS
```

### 9.2 TUX-33 — Competência

Competence is explicitly attributed within the applicable authority scope.

### 9.3 TUX-37 and TUX-38 — Provenance and verifiable evidence

ICFACTORY already requires structured provenance and independently examinable evidence. These semantics directly support the research-dossier strategy used for this investigation.

### 9.4 PO-GOV lifecycle

PO-GOV distinguishes:

```text
REQUESTED → DELIBERATED → ACCEPTED → PROMULGATED
```

Acceptance does not automatically authorize implementation, publication, execution or effect. Promulgation separately records content identity, competent authority, effective date, scope, implementation authorization, version/hash when available, and affected records.

PO-GOV also explicitly states that AI, agents, audits, validators and time possess no transition authority.

Therefore:

```text
AUTOMATION_EXECUTES
!=
AUTOMATION_AUTHORIZES
```

### 9.5 OG-001

OG-001 demonstrates an existing ICFACTORY operational discipline:

```text
FORMAL_AUTHORIZATION
→ EXECUTION_EXCLUSIVELY_OF_AUTHORIZED_WAVE
→ TECHNICAL_AUDIT
→ ARTIFACT_STATE_VERIFICATION
→ FORMAL_CLOSURE
→ AUTHORIZATION_OF_NEXT_WAVE
```

Execution outside the current authorized wave/scope is nonconforming.

OG-001 is evidence of a governance pattern. It is not, by itself, authorization for PROTEUS MCM-WQ production cutover.

---

## 10. Refuted hypothesis register

| Hypothesis | Result |
|---|---|
| A new formal state is necessarily required after validation | REFUTED_AS_TOO_BROAD |
| ALO can formally establish the new runtime state | NOT_DEMONSTRATED |
| PRIMARY is required as a generic runtime state | REFUTED |
| A system always has one runtime configuration at a time | REFUTED |
| CURRENT == PRIMARY | REFUTED |
| Configuration status accounting creates runtime state | REFUTED |
| Validation creates authority to expose runtime | REFUTED |
| Automation possesses independent rollout authority | REFUTED |
| Cutover universally requires a new authorization event | REFUTED_AS_UNIVERSAL |
| Cutover universally requires a distinct authority | NOT_DEMONSTRATED |
| A new Cutover Manager role is required | NOT_DEMONSTRATED |
| ICFACTORY requires a new concept to solve the generic problem | NOT_DEMONSTRATED / EVIDENCE_AGAINST_NEED |
| Generic approval covers all related actions | REFUTED |
| Historical authorization remains automatically executable | REFUTED |
| Authorization of version N automatically covers version N+1 | REFUTED |
| Staging authorization automatically covers production | REFUTED |

---

## 11. Surviving generic model

After the adversarial reductions, the smallest supported generic model is:

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

The model intentionally does not require:

- a universal PRIMARY state;
- a new ICFACTORY state type;
- a new ICFACTORY authority;
- a universal separate cutover-authority role;
- ALO competence expansion;
- a new generic runtime-path object.

---

## 12. Progressive execution and automation

A single authorization may support progressive execution, for example:

```text
10% → 25% → 50% → 100%
```

when the original authorization explicitly covers the target, environment, action range, applicable gates and bounds.

The evidence does not establish a universal requirement for a fresh authority decision at every stage.

Automation may execute predefined stages and rollback conditions within preauthorized scope, but automation cannot self-expand that scope.

```text
AUTOMATION_ROLE::PREAUTHORIZED_EXECUTION
AUTOMATION_SELF_EXPAND_SCOPE::NO
```

---

## 13. Rollback

Rollback authorization is context-dependent.

NIST provides strong evidence that a back-out plan can be part of the same change-request package submitted for approval.

Therefore:

```text
CHANGE_AUTHORIZATION
CAN_INCLUDE
ROLLBACK/BACK_OUT_PLAN
```

but:

```text
CUTOVER_AUTHORIZED
=> ROLLBACK_AUTHORIZED
```

is not universally demonstrated without scope evidence.

---

## 14. Temporal validity and target identity

Authorization is not merely historical provenance. Current executability depends on current validity.

```text
AUTHORIZATION_AT_T1
!=
AUTOMATIC_CURRENT_AUTHORIZATION_AT_T4
```

Likewise, the artifact actually exposed must match the identity covered by the authorization.

```text
AUTHORIZED_ARTIFACT_IDENTITY
MUST_MATCH
ARTIFACT_ACTUALLY_EXPOSED
```

A valid authorization for staging is not evidence of authorization for production. A valid authorization for version 1 is not automatically authorization for version 2.

---

## 15. PROTEUS local application

The generic research is closed, but its local application to PROTEUS remains open.

The investigation did not demonstrate the following chain for MCM-WQ production cutover:

```text
PROTEUS_COMPETENT_AUTHORIZER
→ CURRENT_VALID_AUTHORIZATION
→ TARGET::MCM_WQ
→ ENVIRONMENT::PRODUCTION
→ ACTION::RUNTIME_EXPOSURE/CUTOVER
→ SATISFIED_PRECONDITIONS
```

Therefore:

```text
PROTEUS_COMPETENT_AUTHORIZER::NOT_DEMONSTRATED
PROTEUS_CURRENT_CUTOVER_AUTHORIZATION::NOT_DEMONSTRATED
PRODUCTION_RUNTIME_CUTOVER_SCOPE::NOT_DEMONSTRATED
PROTEUS_CUTOVER_AUTHORIZED::NO
MCM_WQ_CUTOVER_ALLOWED::NO
```

This is a project-local evidence gap, not evidence that ICFACTORY requires a new generic authority or concept.

---

## 16. Final research conclusion

The investigation began with the apparent need for a new operational-state recognition mechanism.

Adversarial testing progressively removed unsupported abstractions:

```text
"WE_NEED_A_NEW_OPERATIONAL_STATE_MECHANISM"
↓
"WE_NEED_A_PRIMARY_RUNTIME_STATE"
↓
"WE_NEED_A_DISTINCT_CUTOVER_AUTHORITY"
↓
"WE_NEED_EVIDENCE_THAT_THE_SPECIFIC_RUNTIME_ACTION
IS_WITHIN_A_CURRENT_VALID_AUTHORIZATION
FROM_A_COMPETENT_AUTHORIZER"
```

The final generic result is:

```text
ICFACTORY-OPERATIONAL-STATE-RESEARCH-01
GENERIC_RESEARCH::CLOSED
PRIMARY_STATE_PROBLEM::REFUTED_AS_UNNECESSARY_ABSTRACTION
DISTINCT_CUTOVER_AUTHORITY_AS_UNIVERSAL_REQUIREMENT::NOT_DEMONSTRATED
AUTHORIZATION_SCOPE_REQUIREMENT::SUPPORTED
NEW_ICFACTORY_CONCEPT_REQUIRED::NO_EVIDENCE
NEW_ICFACTORY_AUTHORITY_REQUIRED::NO_EVIDENCE
ALO_EXPANSION_REQUIRED::NO
GENERIC_MODEL::SUPPORTED
PROTEUS_LOCAL_APPLICATION::OPEN
```

---

## 17. Scientific maturity

```text
GENERIC_SEMANTIC_COHERENCE::SUPPORTED
EXTERNAL_REFERENCE_SUPPORT::SUPPORTED
INTERNAL_ICFACTORY_ALIGNMENT::DEMONSTRATED
ADVERSARIAL_REDUCTION::COMPLETED
PROVENANCE_RECONSTRUCTIBILITY::SUPPORTED_BY_COMPANION_REGISTER
PRODUCTION_VALIDATION::NOT_DEMONSTRATED
PROTEUS_LOCAL_AUTHORIZATION::NOT_DEMONSTRATED
NORMATIVE_PROMOTION::NO
IMPLEMENTATION_AUTHORITY::NONE
```

---

## 18. Research closure rule

This publication closes the generic research question only.

It does not authorize:

- MCM-WQ implementation;
- production cutover;
- new runtime authority;
- ALO expansion;
- new normative concept;
- PO-GOV local adoption by implication.

Any future PROTEUS cutover decision must be evaluated against project-local authority, authorization scope, applicable preconditions, current validity and traceable evidence.

---

## 19. Companion artifacts

- `ICFACTORY_OPERATIONAL_STATE_RESEARCH_01_PROVENANCE.md`
- `ICFACTORY_OPERATIONAL_STATE_RESEARCH_01_KL01.md`

These companion artifacts preserve source provenance and lessons learned separately from the final synthesis.
