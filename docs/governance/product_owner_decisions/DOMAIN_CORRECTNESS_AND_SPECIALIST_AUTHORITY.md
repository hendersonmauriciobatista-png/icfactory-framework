---
identity: PO-GOV-DOMAIN-SPECIALIST
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
concepts: [COR-01, SA-01, SA-02]
---

# Domain Correctness and Specialist Authority

This document is a **ACCEPTED / IN_FORCE** component of PO-GOV. It specializes Product Owner decision governance without creating a parallel authority, professional credential regime, procurement system or financial-governance layer.

## 1. Purpose and precedence

The contract prevents technically correct implementation from being confused with a legitimate domain rule. It is subordinate to the ICFACTORY Constitution, Constitutional Lexicon, Methodological Custody and the established Governance Architecture.

Product Owner authority remains project-local. Methodological Custody remains responsible for framework evolution. External legal, regulatory or professional authority retains every matter reserved to it. A specialist supplies bounded knowledge or validation; the specialist does not acquire Product Owner or custodial authority merely by participating.

## 2. COR-01 — Implementation Correction and Domain Correction

Every material remediation must first classify the correction:

- `IMPLEMENTATION_CORRECTION`: implementation, configuration, test, interface or operation does not correspond to a rule whose authority and applicability are already established for the affected scope.
- `DOMAIN_CORRECTION`: the rule, unit, meaning, premise, model, applicability, evidentiary basis or requirement itself lacks sufficient technical, scientific, professional, legal or normative legitimacy for the intended use.
- `MIXED_CORRECTION`: both conditions exist and are recorded as separately traceable implementation and domain components.

Tests may prove correspondence between code and a stated rule. They cannot, by themselves, legitimize the rule, its source, its applicability or a conformity claim.

Classification occurs before remediation. If evidence does not distinguish the two correction types, the record must preserve a finding, identify the ambiguity and apply proportional containment to the affected scope. Ambiguity must not be converted into presumed domain correctness.

A mixed correction decomposes each component with its own finding, scope, evidence, remediation, containment and closure status. Correcting implementation does not close the domain component; legitimizing or removing the domain rule does not prove the implementation component corrected. The overall mixed finding remains open while either material component remains open.

The structured `correction.components` collection in `SCHEMA.md` is mandatory for every governed correction. `MIXED_CORRECTION` requires both types. Parent aggregation consumes append-only human compatibility declarations for identified containments; automation never infers compatibility. `UNDETERMINED`, asymmetric or conflicting declarations fail closed. `REJECTED` distinguishes remediation/evidence rejection from finding closure; complete rejection requires structured protection for every scope.

An implementation correction may remain D0 when an existing promulgated decision already authorizes the exact correction. A domain correction introduces or changes meaning and is therefore a decision subject to proportional classification. COR-01 does not automatically assign D1, D2 or D3.

## 3. SA-01 — Escalation to Specialist Authority

### 3.1 Requirement states

Specialist necessity is classified for each concrete question, rule, claim or functionality:

- `NOT_REQUIRED`: verified documentary authority and available competence are sufficient; individual specialist review adds no material validation requirement.
- `RECOMMENDED`: specialist review would reduce uncertainty or risk, but its absence does not block the declared scope.
- `MANDATORY`: applicable external authority, reserved professional matter, material uncertainty or risk requires competent specialist validation before the affected scope may be promulgated or activated.
- `OUT_OF_SCOPE`: the project will not operate, publish, evidence or claim the matter because required authority, competence, evidence or intended capability is absent.

The state requires a human justification. D0-D3 materiality may inform the assessment but does not determine it automatically. D2 and D3 are not automatically costly or specialist-dependent, and D0/D1 cannot be used to evade a genuinely mandatory review.

If `domain_authority_required` is `UNDETERMINED`, the affected matter cannot be classified `NOT_REQUIRED`, cannot declare an official source sufficient and cannot be promulgated or activated. Research, audit, non-operational prototype, rejection, containment and `OUT_OF_SCOPE` remain permitted. Resolution requires evidence identifying whether authority is required, the applicable authority basis, the evaluator, relevant evaluator competence and human rationale.

### 3.2 Official-source sufficiency

An official source may dispense with individual specialist review only when all applicable criteria are evidenced:

1. authentic and traceable to the issuing authority;
2. current for the decision date;
3. applicable to the jurisdiction and affected scope;
4. specific to the parameter, unit, context and intended use;
5. unambiguous for the question being decided;
6. usable without material professional interpretation.

Matching values, titles or isolated excerpts are insufficient. Conflicting sources, uncertain applicability, measurement or interpretation choices, reserved professional acts, high-impact uncertainty or material extrapolation prevent an automatic `NOT_REQUIRED` conclusion.

Documentary research locates and analyzes sources. Specialist review applies verifiable competence to a bounded question. Neither activity, by itself, supplies Product Owner authority or an external authorization.

The sufficiency record identifies the human or institution that evaluated these criteria, evidence of competence relevant to applicability and scope, and the authority basis for the evaluation. The evaluator may be competent internal, institutional, external or legally designated capacity. A Product Owner cannot declare `NOT_REQUIRED` solely through unqualified reading. AI, automation, possession of a document, price or generic title cannot establish sufficiency.

An official source and an individual opinion may coexist when the source requires material application, measurement, reconciliation or professional interpretation.

### 3.3 Specialist eligibility and opinion scope

Record proportionately:

- identified person or institution;
- competence related to the concrete question;
- verifiable experience or applicable qualification;
- legally required credential only when the applicable authority requires it;
- method, evidence and sources used;
- conflicts of interest and economic relationships;
- territorial, temporal and normative scope;
- opinion limitations and non-extrapolation conditions.

Cost, reputation, title, referral, payment, employment or self-declaration is not, alone, evidence of competence. Conversely, PO-GOV must not create an occupational reservation or demand a credential that applicable authority does not require.

Payment or employment by a customer does not automatically invalidate an opinion. The relationship must be disclosed and assessed in context.

An opinion is usable only inside the verified competence, question and declared scope. It must not be extrapolated to another parameter, use, jurisdiction, date, population, system or claim without new evidence.

Every opinion is preserved independently through event-sourced `SPECIALIST_OPINIONS`. Immutable revisions retain original scope, conclusion, sources, responsibility, validity and evidence. Monotonic events alone derive current/temporal status. Revalidation effects preserve the predecessor and declare the successor; material changes require non-empty reason/evidence. Withdrawn, superseded and expired revisions remain historical and unusable for release.

### 3.4 Divergence and temporal validity

Materially divergent opinions keep the finding open. Automation, price, majority count and Product Owner preference cannot resolve technical divergence as if it were validated fact.

Resolution requires one or more of:

- competent additional authority;
- a second or further independent opinion;
- additional evidence or a narrowed question;
- proportional containment;
- classification as `OUT_OF_SCOPE`.

Closing divergence or declaring a material conflict mitigated requires the structured `resolution` block. The resolver must have competence relevant to the disputed question and an applicable authority basis. Permitted bases are external authority, competent independent review, qualified institutional authority, an additional technically justified opinion, rejection or `OUT_OF_SCOPE`.

Product Owner status alone cannot resolve substantive technical disagreement. Payment, hierarchy, customer preference, majority count and AI recommendation cannot independently resolve it.

While material divergence remains unresolved, the affected scope cannot claim sufficient specialist validation. Sources and opinions must be reviewed for expiry, amendment, withdrawal, jurisdictional change and factual obsolescence.

An undisclosed material conflict discovered later invalidates use of that opinion as sufficient evidence. A disclosed but unmitigated material conflict keeps the finding open. Resolution requires documented mitigation judged adequate by an authorized human, independent review, additional competent authority, containment or `OUT_OF_SCOPE`. Automation may detect disclosures or missing fields but cannot decide conflict materiality or mitigation sufficiency.

Expiration, normative supersession or loss of applicability of evidence supporting `MANDATORY` validation triggers deterministic review. If continuing validity cannot be established, the affected active scope is suspended or contained; unrelated functionality remains operational. Historical evidence is preserved but is not represented as current.

Release after temporal invalidity requires renewal, replacement or revalidation evidence, confirmed applicability, satisfaction of every mandatory release condition and explicit containment-release authorization.

There is no normative `EXPIRING` opinion state. Validity chronology requires `warning_at < review_due_at <= expires_at` when expiry exists; otherwise an alternative condition is mandatory. Dates never order events. Passing review due produces an event-derived overdue status without lifecycle transition. Applicability failure contains immediately; expiry prohibits continued use without a valid successor.

### 3.5 Bounded validation block and containment

Missing `MANDATORY` validation blocks only the identified `blocked_scope`: the affected question, rule, claim, functionality or external effect. It does not silently block unrelated functions or the entire project.

The block does not prevent a competent Product Owner from rejecting the proposal, narrowing scope, applying containment or declaring `OUT_OF_SCOPE`. Containment must be proportional, recorded and must prevent unvalidated content from re-entering through an alias, adapter, report, score, recommendation or external claim.

Mandatory-validation containment may be released only when:

1. required evidence is present;
2. competence was verified;
3. the opinion scope covers the affected matter;
4. source and opinion remain current and applicable;
5. material conflicts are absent or adequately mitigated by authorized human judgment;
6. material divergence is resolved by authorized human judgment;
7. responsibility scope is explicit;
8. containment release is explicitly authorized;
9. Product Owner decision and reserved external authority remain distinct.

## 4. Authority and responsibility separation

The record distinguishes:

- `TECHNICAL_OPINION`: bounded analysis supplied within verified competence;
- `PROFESSIONAL_RESPONSIBILITY`: responsibility expressly assumed or imposed by applicable external authority, contract or professional act;
- `PRODUCT_DECISION`: project scope, priority and product behavior decided by the competent Product Owner;
- `METHODOLOGICAL_DECISION`: framework evolution decided by Methodological Custody;
- `EXTERNAL_AUTHORITY_ACT`: authorization or determination reserved to an applicable regulator, court, professional body or other competent external authority.

Consultation does not imply transfer or assumption of professional responsibility. Product Owners may not decide matters reserved by external law or authority. Promulgation must identify the exact responsibility scope and may not attribute statements or duties beyond evidence.

## 5. SA-02 — Detection, Contracting and Cost Transparency

When specialist competence must be obtained, the project may use:

- direct contracting;
- identified referral;
- transparent subcontracting;
- institutional contracting;
- multiple or independent opinions.

Record, proportionately and with controlled references when confidentiality requires:

- selection method and rationale;
- contracting modality;
- contractor and identified subcontractors;
- economic relationship and conflicts;
- cost or controlled cost reference;
- contracted deliverable;
- limitations and responsibility scope.

Sensitive financial evidence need not be stored in Git. A durable controlled reference, confidentiality classification and integrity evidence are sufficient when appropriate.

SA-02 does not implement procurement, accounting, payment, budgeting or financial governance. PO-GOV does not approve contracting or cost and does not use payment as proof of competence.

## 6. G01-G15 safety guards

| Guard | Required control |
|---|---|
| `G01_MATERIALITY` | Classify decision materiality and specialist necessity separately; preserve justification and prevent fragmentation. |
| `G02_VERIFIABLE_COMPETENCE` | Require evidence of competence tied to the concrete question; do not infer it from title, cost or reputation. |
| `G03_OPINION_SCOPE` | Bind every opinion to its question, matter, context and limits. |
| `G04_AUTHORITY_SEPARATION` | Keep specialist, Product Owner, Methodological Custody and external authority capacities distinct. |
| `G05_MANDATORY_VALIDATION_BLOCK` | Missing mandatory validation blocks only the declared affected scope. |
| `G06_CONFLICT_OF_INTEREST` | Record actual, potential and perceived conflicts plus mitigation or limitation. |
| `G07_SPECIALIST_DIVERGENCE` | Preserve material divergence as an open finding; prohibit automated resolution or false validation claims. |
| `G08_TEMPORAL_AND_NORMATIVE_VALIDITY` | Record applicable dates, jurisdiction, normative version, expiry and review triggers. |
| `G09_COMMERCIAL_TRANSPARENCY` | Record selection, contractual chain, economic relationship, controlled cost reference and deliverable without creating financial governance. |
| `G10_NON_EXTRAPOLATION` | Prohibit use beyond verified competence, question, territory, time, context and intended claim. |
| `G11_PROPORTIONAL_CONTAINMENT` | Limit containment to affected scope while preventing bypass and preserving unrelated operation. |
| `G12_OFFICIAL_SOURCE_SUFFICIENCY` | Dispense with individual review only when every explicit sufficiency criterion is met. |
| `G13_NO_FALSE_RESPONSIBILITY_TRANSFER` | Separate consultation, professional responsibility and product decision; attribute only what was assumed. |
| `G14_NO_AUTOMATED_AUTHORITY_INFERENCE` | Automation cannot infer competence, sufficiency, responsibility, resolution, acceptance or authority. |
| `G15_NO_UNNECESSARY_SPECIALIST_GATE` | Require specialist participation only when justified for the concrete scope; preserve lightweight D1 and authorized D0. |

Failure of a guard produces a finding and the bounded consequence specified by the applicable requirement. A guard does not manufacture authority or automatically escalate the whole project.

For G06, an undisclosed material conflict or open unmitigated material conflict prevents the affected opinion from satisfying mandatory evidence. For G08, expired, superseded or inapplicable mandatory evidence contains the affected active scope pending review and authorized release. For G12, sufficiency requires an identified evaluator and relevant competence evidence.

## 7. Required record data

Where applicable, the canonical record uses the modular blocks defined in `SCHEMA.md`: `specialist_authority`, its independent `opinions` and optional `resolution`, plus structured `correction.components`. Blocks without a trigger are absent rather than filled with placeholders. Empty fields are not evidence.

## 8. Empirical validation boundary

The PROTEUS generic-pesticide removal may be cited as empirical evidence that implemented structure does not establish unit, meaning or analytical authority. It is not a project derivation, does not reinterpret historical data and does not establish a universal rule that all water parameters require specialist review.

## 9. Candidate status

`ACCEPTED / IN_FORCE`. This contract is not accepted, promulgated, derived or operationally authoritative.
