---
document_id: PO-GOV-TEMPLATE-D2
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
materiality: D2
---

# Product Owner Decision — D2 Template

> **ACCEPTED / IN_FORCE.** Replace this candidate-document front matter with the canonical block below when instantiating a record. Sentinels make an unchanged copy invalid.

## Canonical core and D2 extension

```yaml
schema_version: po-gov/1.0.0
decision_id: REPLACE_REQUIRED_INVALID
project_id: REPLACE_REQUIRED_INVALID
title: REPLACE_REQUIRED_INVALID
materiality_class: D2
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
d2:
  affected_scope: REPLACE_REQUIRED_INVALID
  affected_stakeholders: [REPLACE_REQUIRED_INVALID]
  alternatives: [REPLACE_REQUIRED_INVALID]
  risks: [REPLACE_REQUIRED_INVALID]
  dependencies: [NONE]
  data_or_semantic_effect: NONE
  implementation_scope: REPLACE_REQUIRED_INVALID
  validation_plan: REPLACE_REQUIRED_INVALID
  rollback_or_containment: REPLACE_REQUIRED_INVALID
  publication_or_user_effect: NONE
```

Before interpreting this front matter, inspect trustworthy raw source. Anchors, aliases, merge keys, custom tags, implicit composition, duplicate keys/modules/collection IDs, first-wins, last-wins and silent merge are invalid and never expanded. Parsed-only input fails closed.

## ORIGINAL_REQUEST_AND_SCOPE

- Original request/reference:
- In scope and out of scope:
- Intended result:

## EVIDENCE_ALTERNATIVES_AND_RISKS

- Favorable, contrary and inconclusive evidence:
- Alternatives, including no action:
- Product, data, operational and external risks:

## HUMAN_DELIBERATION_AND_AUTHORITY

- Human participants and contributions:
- AI/automation contribution and limits:
- Product Owner rationale and manifestation:
- Lifecycle disposition: ACCEPTED / REJECTED / DEFERRED

## IMPLEMENTATION_AND_VALIDATION

- Authorized/prohibited implementation:
- Validation evidence and result:
- Rollback/containment:
- Publication/user effect:

## CONDITIONAL_MODULES

Insert only when triggered: `specialist_authority`, `correction`, `reclassification_lineage` or `terminal_effect`. D2 cannot contain `d1`, `d3` or the non-decisional `grouped_d1` envelope.

Mandatory specialist release requires the full opinion and resolver sub-schemas where applicable. Structural conformity is not acceptance, source sufficiency or promulgation.
