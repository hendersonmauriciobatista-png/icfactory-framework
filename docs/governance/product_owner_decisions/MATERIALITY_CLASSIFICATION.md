---
identity: PO-GOV-MATERIALITY
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# D0-D3 Materiality Classification

This candidate specializes the existing constitutional concept of Materiality; it does not redefine it.

## D0 - OPERATIONAL

No new decision about scope, behavior, meaning, authority or risk. The action is already authorized by an existing promulgated decision.

Examples: read-only inspection, authorized tests, formatting without semantic change and reversible implementation detail within an approved contract.

Control: operational evidence must contain `already-authorized-by`. No PO-DEC record is created. D0 must never conceal a new decision.

## D1 - SIMPLE_PRODUCT_OWNER_DECISION

Local, low-risk and reversible; no architectural, semantic, authority or external-claim effect. Requires a lightweight canonical record and explicit Product Owner manifestation.

Similar D1 items may be grouped only when each item, effect and disposition remains individually traceable.

Grouped D1 uses the authority-free administrative envelope. Each item declares project scope, D1 materiality and `NOT_REQUIRED`/`RECOMMENDED` specialist state. D2/D3 or `MANDATORY` items must leave through a resolvable same-project successor lineage; the envelope preserves history. A future derived project index checks item uniqueness and single active-group membership without becoming a canonical decision.

D1 remains lightweight by default. If it uses `MANDATORY` specialist validation, it must still record proportional competence, conflict, temporal-validity and responsibility evidence. Escalate to D2 when that evidence cannot remain concise and auditable. A D1 label cannot remove an applicable guard.

## D2 - MATERIAL_PRODUCT_OWNER_DECISION

Changes scope, requirement, behavior, architecture, data meaning, priority, authority or published functionality. Requires complete lifecycle, evidence, alternatives, risks, human deliberation, acceptance, promulgation and execution linkage.

## D3 - CRITICAL_NORMATIVE_EXTERNAL_DECISION

Affects legal/normative claims, security, privacy, licensing, ownership, monetization, irreversible migration, external submission or other high-impact behavior. Requires D2 content plus reinforced evidence, privacy controls, containment/rollback and additional competent or specialist review when required.

## Classification controls

1. Final classification belongs to a competent human authority.
2. Classification justification is mandatory.
3. Ambiguity fails upward.
4. Automation may suggest a class with reasons but cannot downgrade it.
5. A decision may be promoted when new risk appears; the record preserves why and when.
6. D2/D3 may not be fragmented into D0/D1 to evade governance.
7. Operational implementation steps under a promulgated D2/D3 decision remain D0 when they introduce no new decision.
8. D1 must not inherit the full D2/D3 dossier.
9. Read-only audits remain immediately executable D0 when otherwise authorized.
10. D0-D3 and SA-01 are independent classifications: no class automatically requires or dispenses with a specialist.
11. A mandatory specialist gate cannot be fragmented or downgraded, while a D2/D3 label alone cannot manufacture an unnecessary gate.
12. Every reassessment creates a successor and appends a complete `reclassification_lineage` event with exactly one current head; automation validates the graph but cannot decide it.

## Decision guide

- New discretion or changed meaning? At least D2.
- External/legal/security/privacy effect? D3.
- Local reversible preference without semantic/architectural effect? D1.
- No new discretion and a valid authorization reference? D0.
- Uncertain? Select the higher applicable class and escalate for human confirmation.

## Specialist proportionality

Classify specialist necessity per concrete question, rule, claim or functionality as `NOT_REQUIRED`, `RECOMMENDED`, `MANDATORY` or `OUT_OF_SCOPE`. Official-source sufficiency, domain uncertainty, externally reserved authority and affected risk determine the state. Cost, title and materiality class alone do not.

An ambiguous correction type produces a finding and proportional containment. It does not automatically convert the whole project into D3 or require specialist review for unrelated scope.

A `MIXED_CORRECTION` classifies each implementation and domain component separately. Closing the implementation component cannot downgrade or close the domain component.

## Status

`ACCEPTED / IN_FORCE`.
