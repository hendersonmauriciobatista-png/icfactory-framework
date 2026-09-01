# ICFACTORY-OPERATIONAL-STATE-RESEARCH-01 — KL-01 Lessons Learned

**Date:** 2026-09-01  
**Status:** PUBLISHED_RESEARCH_LESSON / NON_NORMATIVE  
**Origin:** `ICFACTORY-OPERATIONAL-STATE-RESEARCH-01`  

## KL-01 — Research provenance and problem reformulation

### Lesson 1 — A conclusion is not preserved without provenance

```text
A_CORRECT_CONCLUSION
WITHOUT_RECONSTRUCTIBLE_PROVENANCE
IS_NOT_A_PRESERVED_RESEARCH_RESULT
```

Preservation requires, for material findings:

```text
SOURCE
+
EVIDENCE
+
INTERPRETATION
+
LIMITATION
+
DECISION_TRACE
```

The ability to recover a conclusion is not equivalent to the ability to reconstruct why that conclusion was justified.

### Lesson 2 — Refuted hypotheses are research evidence

The investigation must preserve not only the final answer but also material hypotheses that were tested and rejected.

In this research, the following apparent needs were progressively removed or reduced:

```text
NEW_OPERATIONAL_STATE_MECHANISM
→ PRIMARY_RUNTIME_STATE
→ DISTINCT_CUTOVER_AUTHORITY
→ AUTHORIZATION_SCOPE_EVIDENCE
```

The rejected stages explain why the final model is intentionally smaller.

### Lesson 3 — A missing edge may be an artificial problem

```text
MISSING_EDGE
MAY_NOT_MEAN
MISSING_MECHANISM
```

Before creating a mechanism to reach a destination state, test whether the destination state itself is necessary.

The generic PRIMARY state failed this test.

### Lesson 4 — Do not create authority from implementation need

```text
NEED_FOR_ACTION
!=
EVIDENCE_OF_AUTHORITY
```

A technically necessary action does not prove the need for a new role or authority. First determine whether the action is already within the scope of an existing competent authorization model.

### Lesson 5 — Authority identity and authorization scope must remain separate

```text
WHO_CAN_AUTHORIZE
!=
WHAT_THIS_AUTHORIZATION_ALLOWS
```

Failure to preserve this distinction can produce both over-authorization and unnecessary proliferation of authorities.

### Lesson 6 — Validation does not create authority

```text
VALIDATION_PASS
MAY_SATISFY_A_PRECONDITION
BUT
DOES_NOT_CREATE_AUTHORITY
```

The same applies to test success, deployment readiness, code completion and technical capability.

### Lesson 7 — Automation executes; it does not self-authorize

```text
AUTOMATION
MAY_EXECUTE_PREAUTHORIZED_ACTIONS
BUT_MUST_NOT
SELF_EXPAND_SCOPE
```

This remains true for progressive rollout, automated traffic transition and rollback.

### Lesson 8 — Current validity matters

```text
AUTHORIZATION_EXISTED
!=
AUTHORIZATION_IS_CURRENTLY_EXECUTABLE
```

Temporal validity, revocation, expiry, scope change, artifact identity and preconditions may affect current executability without rewriting historical authorization evidence.

### Lesson 9 — Configuration/runtime facts and governance facts are distinct

```text
RUNTIME_CONFIGURATION_FACT
!=
GOVERNANCE_AUTHORIZATION_FACT
```

Deployment systems can prove what is serving. Governance records can prove what was authorized. Neither fact should be inferred from the other.

### Lesson 10 — Do not confuse representation with constitutive authority

```text
STATE_IS_REPRESENTED
!=
STATE_IS_AUTHORITATIVELY_ESTABLISHED
```

This distinction prevented an unsupported expansion of ALO competence.

### Lesson 11 — Research must be allowed to correct its own question

```text
A_RESEARCH_PROCESS
MUST_BE_ALLOWED
TO_DELETE_OR_REFORMULATE
ITS_OWN_PROBLEM_FORMULATION
WHEN_EVIDENCE_SHOWS
THAT_THE_PROBLEM_WAS_PARTLY_CREATED
BY_THE_MODEL_USED_TO_DESCRIBE_IT
```

The final value of the investigation was not merely finding an answer. It was progressively improving the question until only the evidence-relevant problem remained.

### Lesson 12 — Generic framework sufficiency does not prove local project applicability

```text
GENERIC_SEMANTICS_EXIST
!=
LOCAL_PROJECT_BINDING_EXISTS
```

ICFACTORY already contains authority-scope, competence, provenance and bounded-execution semantics. This does not establish that PROTEUS currently has a valid MCM-WQ production-cutover authorization.

---

## Consolidated KL-01 statement

```text
RESEARCH_CLOSURE_REQUIRES::
QUESTION
+
SOURCE
+
EVIDENCE
+
INTERPRETATION
+
REFUTATION
+
DECISION
+
LIMITATION
+
REMAINING_GAP

AND::

A_MISSING_EDGE
MUST_NOT_AUTOMATICALLY_CAUSE_CREATION_OF
A_NEW_STATE
A_NEW_CONCEPT
A_NEW_ROLE
OR
A_NEW_AUTHORITY

FIRST_TEST::
IS_THE_DESTINATION_SEMANTIC_ACTUALLY_NECESSARY?

SECOND_TEST::
IS_THE_APPARENT_AUTHORITY_GAP_ACTUALLY_A_SCOPE_GAP?

THIRD_TEST::
DO_EXISTING_GOVERNANCE_PRIMITIVES_ALREADY_COVER_THE_GENERIC_NEED?

ONLY_THEN::
CONSIDER_NEW_MECHANISM
```

---

## Status

```text
KL_01_RESEARCH_PROVENANCE::PUBLISHED
NORMATIVE_STATUS::NON_NORMATIVE_RESEARCH_LESSON
NEW_CONCEPT::NO
NEW_AUTHORITY::NO
ALO_CHANGE::NO
PROTEUS_CUTOVER_AUTHORIZATION::NO
```
