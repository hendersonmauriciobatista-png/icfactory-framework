---
identity: PO-GOV-LIFECYCLE
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# Product Owner Decision Lifecycle

## 1. States

Core:

```text
REQUESTED -> DELIBERATED -> ACCEPTED -> PROMULGATED
```

Exceptional or terminal:

```text
REJECTED | DEFERRED | WITHDRAWN | REVOKED | SUPERSEDED | EXPIRED
```

No state is inferred from silence, time, code, commit, implementation, AI output or registry entry.

## 2. Semantics and authority

| State | Meaning | Transition authority |
|---|---|---|
| REQUESTED | Request preserved; may originate from person, audit or agent | Intake has no decisional effect |
| DELIBERATED | Human-governed analysis records evidence, alternatives, risks and classification | Competent human-led process |
| ACCEPTED | Competent human authority accepts identified content | Project Product Owner for project decisions; Methodological Custody for framework normative decisions |
| PROMULGATED | Accepted content is explicitly placed into effect with identity and effective date | Same competent authority in the relevant capacity |
| REJECTED | Request is explicitly refused with rationale | Competent human authority |
| DEFERRED | Decision postponed with trigger/date for reconsideration | Competent human authority |
| WITHDRAWN | Accepted but unpromulgated content is withdrawn without ever acquiring operational effect | Same competent authority that could promulgate the accepted content |
| REVOKED | Operational effect of promulgated content ends without deleting history | Competent authority for the affected scope |
| SUPERSEDED | New promulgated content replaces previously promulgated content with bidirectional links | Competent authority through the successor record |
| EXPIRED | Explicit expiry condition is reached without ratification/successor | Condition recorded by prior authority; automation may detect, not decide |

AI, agents, audits, validators and time possess no transition authority.

## 3. Valid transitions

```text
REQUESTED    -> DELIBERATED | REJECTED | DEFERRED
DEFERRED     -> DELIBERATED | REJECTED | EXPIRED
DELIBERATED  -> ACCEPTED | REJECTED | DEFERRED
ACCEPTED     -> PROMULGATED | WITHDRAWN | EXPIRED
PROMULGATED  -> REVOKED | SUPERSEDED | EXPIRED
```

`REJECTED`, `WITHDRAWN`, `REVOKED`, `SUPERSEDED` and `EXPIRED` are terminal. A materially changed or reopened matter requires a new decision identifier and linkage to the prior record. `DEFERRED` is non-terminal and requires a review trigger or date.

## 4. Acceptance is not promulgation

Acceptance records a human decision on identified content. It does not automatically authorize implementation, publication, execution or effect. Promulgation separately records:

- accepted content identity;
- competent authority and capacity;
- effective date;
- scope and implementation authorization;
- version/record hash when canonicalization exists;
- affected records and predecessor state.

Project promulgation belongs to the designated Product Owner. Framework normative promulgation belongs to Methodological Custody. A dual-role holder must declare the role exercised.

## 5. Preservation and succession

- Rejection preserves request and rationale.
- Deferral preserves the request and records a reconsideration trigger/date.
- Withdrawal preserves acceptance evidence and records why promulgation will not occur; it is not revocation and has no operational effect to terminate.
- Revocation terminates effect without deleting or rewriting the record.
- Revocation applies only to promulgated content.
- Supersession requires a new promulgated canonical record; both records link each other and the predecessor loses effect only when the successor enters into effect.
- Expiry requires an explicit condition or date.
- Ratification is an explicit human review outcome. It may authorize continued acceptance/promulgation but is not silent permanence or an additional ambiguous lifecycle state.

## 6. Provisional emergency decisions

Emergency use retains D1/D2/D3 and sets `provisional: true`. It requires:

- explicit authority;
- urgency reason and material risk of delay;
- limited scope;
- effective and expiry dates;
- containment or rollback plan;
- mandatory review deadline.

Provisional status never becomes permanent by time or continued use. Expiry without explicit ratification produces `EXPIRED`. Emergency does not waive specialist or external authority required for the affected matter, regardless of materiality class.

## 7. Specialist validation gates

COR-01 and SA-01 are conditions within the lifecycle, not additional lifecycle states. A technical opinion cannot cause a transition.

- Missing `MANDATORY` validation prevents promulgation or activation only for `specialist_authority.blocked_scope`.
- The Product Owner may still reject, defer, contain, narrow or declare the matter `OUT_OF_SCOPE`.
- Material specialist divergence remains an open finding and prevents a claim of sufficient validation.
- Expiry or loss of applicability does not rewrite history; it triggers review and may prevent future reliance on the source or opinion.
- Passing an opinion `review_due_at` before expiry produces an append-only `REVIEW_OVERDUE` opinion event, not mutation of the revision or a lifecycle transition; event sequence, not dates, orders opinion state.
- Promulgation identifies the exact responsibility scope and cannot transfer professional responsibility by implication.

## 8. Deterministic state and effect rules

| Status | Transition authority | Required combination | Operational effect | Prohibited combination | Closure/release |
|---|---|---|---|---|---|
| `REQUESTED` | Intake only; no decisional authority | acceptance/promulgation `NOT_GRANTED`; no effective date | None | Any granted acceptance/promulgation | Deliberation, rejection or deferral |
| `DELIBERATED` | Competent human-led process | human deliberation present; acceptance/promulgation `NOT_GRANTED` | None | Effective date or granted promulgation | Acceptance, rejection or deferral |
| `ACCEPTED` | Product Owner for project; Methodological Custody for framework | acceptance `GRANTED`; promulgation `NOT_GRANTED`; no effective date | None | Revocation, supersession or operational activation | Promulgation, withdrawal or explicit expiry |
| `PROMULGATED` | Same competent authority in declared capacity | acceptance/promulgation `GRANTED`; effective date present; all applicable release conditions satisfied | Begins no earlier than effective date and only for unblocked scope | Missing authority, unresolved mandatory block or invalid temporal evidence | Revocation, supersession or expiry |
| `DEFERRED` | Competent human authority | acceptance/promulgation `NOT_GRANTED`; review trigger/date present | None | Operational activation | Return to deliberation, rejection or expiry |
| `REJECTED` | Competent human authority | acceptance/promulgation `NOT_GRANTED`; terminal state `REJECTED` | None | Effective date or later activation | New linked record only |
| `WITHDRAWN` | Same competent authority that could promulgate | prior `ACCEPTED`; acceptance retained; promulgation not granted; predecessor/act/date recorded | None | Revocation or assertion of prior operational effect | New linked record only |
| `REVOKED` | Competent authority for the promulgated effect | prior `PROMULGATED`; grants/original effective date retained as history; predecessor/act/date recorded | None after terminal date | Direct transition from unpromulgated content | New linked decision only |
| `SUPERSEDED` | Competent authority through the successor act | prior `PROMULGATED`; grants/original effective date retained; promulgated successor and bidirectional links | Successor governs from its effective date | Missing or unpromulgated successor | Successor lifecycle governs |
| `EXPIRED` | Prior explicit condition; automation may detect but not decide renewal | predecessor is `DEFERRED`, `ACCEPTED` or `PROMULGATED`; grants/effective date remain consistent with that predecessor; expiry act/date recorded | None after expiry; previously promulgated effect ends only for the affected scope | Silent permanence or predecessor mismatch | Explicit new or ratifying record |

For every status, unresolved domain authority, absent current mandatory opinion, divergence, conflict or evidence prevents affected-scope activation. Overdue status is event-derived and follows validity conditions without automatic decision transition. Reclassification uses a monotonic same-lineage successor chain and cannot accept/promulgate either record. Unrelated scope remains unaffected. Terminal states require `terminal_effect`; non-terminal states prohibit it.

Structural consistency never constitutes acceptance, substantive validation, source sufficiency or authorization.

## 9. Status

`ACCEPTED / IN_FORCE`.
