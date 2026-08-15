---
document_id: PO-GOV-TEMPLATE-D1
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
materiality: D1
---

# Product Owner Decision — D1 Template

> **ACCEPTED / IN_FORCE.** Replace this candidate-document front matter with the canonical block below when instantiating a record. An unchanged copy is invalid and grants no authority.

## Minimal canonical D1 front matter

```yaml
schema_version: po-gov/1.0.0
decision_id: REPLACE_REQUIRED_INVALID
project_id: REPLACE_REQUIRED_INVALID
title: REPLACE_REQUIRED_INVALID
materiality_class: D1
classification_justification: REPLACE_REQUIRED_INVALID
status: REQUESTED
disposition: PENDING
request_source: HUMAN
original_request_reference: REPLACE_REQUIRED_INVALID
authority_role: PRODUCT_OWNER
authority_holder: REPLACE_REQUIRED_INVALID
authority_provenance: REPLACE_REQUIRED_INVALID
evidence_references: [REPLACE_REQUIRED_INVALID]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: INTERNAL
framework_version: REPLACE_REQUIRED_INVALID
framework_source_commit: REPLACE_REQUIRED_INVALID
d1:
  affected_scope: REPLACE_REQUIRED_INVALID
  result_summary: REPLACE_REQUIRED_INVALID
  reversibility: REVERSIBLE
  residual_risk: NONE
```

The ordinary D1 has 20 core fields plus four D1 fields. Specialist, correction, reclassification and terminal blocks are absent unless their independent trigger applies. A grouped-D1 envelope is a separate non-decisional structure, not a conditional authority block inside this record.

**REQUIRED structural rule:** validate trustworthy raw front matter before parsing. Anchors, aliases, merge keys, custom tags, implicit composition, duplicate keys/modules/collection IDs, first-wins, last-wins and silent merge are invalid. Parsed-only input fails closed; prohibited constructs are never expanded.

## ORIGINAL_REQUEST

**GUIDANCE_ONLY:** use this body section when a human-readable rendering helps. The canonical `original_request_reference` remains REQUIRED. An empty or omitted guidance section does not invalidate a conforming D1.

## EVIDENCE_AND_RESULT — OPTIONAL

- Concise evidence reviewed: OPTIONAL human-readable expansion of `evidence_references`.
- Result and affected scope: OPTIONAL human-readable expansion of `d1`.
- Restrictions and residual risk: OPTIONAL human-readable expansion of `d1.residual_risk`.

Omission does not invalidate the record when the canonical fields are complete.

## HUMAN_DELIBERATION_AND_AUTHORITY — CONDITIONAL

- Trigger: any transition beyond `REQUESTED`, or any material human rationale not fully represented by the canonical evidence references.
- Human rationale: REQUIRED when triggered.
- Capacity exercised: REQUIRED when triggered and must match canonical authority provenance.
- Lifecycle disposition: REQUIRED when triggered and must follow `LIFECYCLE.md`.
- Manifestation evidence: REQUIRED when triggered.

At `REQUESTED`, this section is GUIDANCE_ONLY and may be absent. It never substitutes for canonical authority fields.

## CONDITIONAL_MODULES — GUIDANCE_ONLY INDEX

Insert only the applicable module from `SCHEMA.md`:

- a separate `grouped_d1` administrative envelope when multiple traceable D1 items share preparation context;
- `reclassification_lineage` when materiality changes;
- `specialist_authority` when specialist/source/domain analysis is triggered;
- `correction` when COR-01 applies;
- `terminal_effect` only at a terminal lifecycle state.

If mandatory specialist evidence cannot remain concise and auditable, reclassify to D2 and preserve the complete reclassification entry. A D1 label never bypasses G01-G15.

This index adds no empty prompts or placeholders. Acceptance and promulgation remain separate. Apply the lifecycle matrix before any transition; structural conformity is not substantive approval.
