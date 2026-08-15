---
identity: PO-GOV-SCHEMA
schema_version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
representation: MODULAR_MARKDOWN_WITH_YAML_FRONT_MATTER
---

# PO-GOV Modular Record Schema

## 1. Contract

Canonical decision records are human-readable Markdown with modular YAML front matter. Every decision record contains `CANONICAL_CORE` and exactly one materiality extension. The non-decisional `GROUPED_D1_ITEMS` envelope is the sole structural exception and contains only its envelope contract plus independently authoritative item references. Conditional blocks are physically absent when their trigger is absent; they are not populated with repetitive `NOT_APPLICABLE` fields.

Unknown modules, schema versions, lifecycle states or materiality classes are structurally invalid. Empty values and `REPLACE_REQUIRED_INVALID` do not satisfy required fields. Structural conformance is not substantive approval, competence, source sufficiency, acceptance or promulgation.

### Restricted YAML/front-matter profile

PO-GOV structural YAML is a deliberately restricted profile. Before parsing, normalization or semantic interpretation, a validator must inspect the trustworthy raw representation and reject:

- anchors (`&`), aliases (`*`), merge keys (`<<`) or equivalent composition constructs;
- custom tags (`!tag`) or implicit object composition;
- duplicate mapping keys at any nesting level, including front-matter keys;
- duplicate module names or more than one occurrence of a conditional module;
- duplicate collection identifiers inside the applicable uniqueness scope;
- malformed, unknown or materiality-incompatible modules.

The restricted profile never expands anchors, aliases, merges or custom objects. Their presence in structural YAML is invalid even when a parser would produce an apparently unambiguous object. First-wins, last-wins, silent merge and normalization that erases structural evidence are prohibited. Detection precedes ordinary schema validation and preserves a reportable reference to each prohibited occurrence. Parsed input without trustworthy raw source fails closed. Automation may report the violation but cannot expand, select, merge or infer a surviving value.

## 2. CANONICAL_CORE

Required for D1, D2 and D3:

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-<PROJECT>-<YYYY>-<NNNN>
project_id: <canonical-project-id>
title: <text>
materiality_class: D1|D2|D3
classification_justification: <text>
status: REQUESTED|DELIBERATED|ACCEPTED|PROMULGATED|REJECTED|DEFERRED|WITHDRAWN|REVOKED|SUPERSEDED|EXPIRED
disposition: PENDING|ACCEPTED|REJECTED|DEFERRED|WITHDRAWN
request_source: HUMAN|AUDIT|AGENT|OTHER
original_request_reference: <verbatim content or integrity-preserving reference>
authority_role: <role>
authority_holder: <human identity>
authority_provenance: <evidence reference>
evidence_references: [<reference>]
acceptance: GRANTED|NOT_GRANTED
promulgation: GRANTED|NOT_GRANTED
effective_date: <ISO-8601 or null>
confidentiality: PUBLIC|INTERNAL|CONFIDENTIAL|RESTRICTED
framework_version: <adopted PO-GOV version>
framework_source_commit: <40-character commit>
```

Core consistency:

- `REQUESTED` and `DELIBERATED` require `disposition: PENDING`.
- `DEFERRED`, `REJECTED`, `ACCEPTED` and `WITHDRAWN` require matching disposition.
- `PROMULGATED`, `REVOKED`, `SUPERSEDED` and promulgated-origin `EXPIRED` retain `disposition: ACCEPTED` as historical decision provenance.
- Acceptance and promulgation combinations follow `LIFECYCLE.md`.
- A raw template sentinel makes the record invalid.

## 3. Materiality extensions

Exactly one extension matching `materiality_class` is required.

### D1_EXTENSION

```yaml
d1:
  affected_scope: <bounded local scope>
  result_summary: <decision result>
  reversibility: REVERSIBLE|LIMITED
  residual_risk: <concise text or NONE>
```

D1 contains no specialist, correction, commercial or terminal block unless independently triggered. Grouping uses a separate authority-free envelope, never a block inside the D1 decision. D1 escalates when required evidence cannot remain concise and auditable.

### D2_EXTENSION

```yaml
d2:
  affected_scope: <scope>
  affected_stakeholders: [<stakeholder>]
  alternatives: [<option including no-action>]
  risks: [<risk>]
  dependencies: [<dependency or NONE>]
  data_or_semantic_effect: <effect or NONE>
  implementation_scope: <authorized/prohibited effects>
  validation_plan: <criteria and evidence>
  rollback_or_containment: <control>
  publication_or_user_effect: <effect or NONE>
```

### D3_EXTENSION

```yaml
d3:
  affected_scope: <scope>
  affected_stakeholders: [<stakeholder>]
  alternatives: [<option including no-action>]
  reinforced_risks: [<legal/security/privacy/external risk>]
  required_external_authorities: [<authority or NONE>]
  authority_separation_analysis: <analysis>
  legal_or_normative_basis: [<reference or NONE>]
  privacy_and_access_controls: <controls>
  security_controls: <controls>
  external_effects_and_notice: <effects/notice>
  implementation_scope: <authorized/prohibited effects>
  validation_plan: <reinforced criteria>
  rollback_and_external_remedy: <control>
  additional_signatures: [<evidence reference or NONE>]
  independent_review: <reference or NONE>
  mandatory_review_date: <ISO-8601>
```

## 4. Conditional blocks

### SPECIALIST_AUTHORITY_BLOCK

Trigger: specialist requirement is assessed for the affected question, an opinion is used, official-source sufficiency is relied upon, or domain authority is uncertain.

```yaml
specialist_authority:
  domain_authority_required: true|false|UNDETERMINED
  specialist_requirement: NOT_REQUIRED|RECOMMENDED|MANDATORY|OUT_OF_SCOPE
  specialist_question: <bounded question>
  source_sufficiency: SUFFICIENT|INSUFFICIENT|CONFLICTING|NOT_USED
  source_sufficiency_evaluator: <identified human/institution>
  evaluator_competence_evidence: [<reference>]
  evaluator_authority_basis: <basis>
  blocked_scope: <scope or NONE>
  containment: <control or NONE>
  containment_release_status: BLOCKED|READY_FOR_HUMAN_RELEASE|RELEASED|NOT_REQUIRED
  containment_release_authority: <reference or NONE>
  parent_opinion_status: NONE|STRUCTURALLY_SUPPORTING|INCONCLUSIVE|OPEN_DIVERGENCE|BLOCKED
  opinions: []
  resolution: null
```

`domain_authority_required: UNDETERMINED` prohibits `NOT_REQUIRED`, `SUFFICIENT`, promulgation and activation of the affected scope. `resolution` is required only to close material divergence or mitigate a material conflict.

### MIXED_CORRECTION_COMPONENTS

Trigger: a correction is governed by COR-01; mixed corrections require the mixed value and both component types.

```yaml
correction:
  correction_type: IMPLEMENTATION_CORRECTION|DOMAIN_CORRECTION|MIXED_CORRECTION
  parent_status: BLOCKED|UNRESOLVED|CLOSED|RESOLVED_WITH_CONTAINMENT|OUT_OF_SCOPE|REJECTED
  parent_disposition: CONTINUE_REMEDIATION|COMPLETE_PROPOSAL_REJECTED|NONE
  components:
    - component_id: <stable-local-id>
      correction_type: IMPLEMENTATION_CORRECTION|DOMAIN_CORRECTION
      affected_scope: <scope>
      finding: <finding>
      evidence: [<reference>]
      containments:
        - containment_id: <stable-id>
          affected_scope_id: <stable-scope-id>
          containment_type: DISABLE|ISOLATE|SUPPRESS_CLAIM|REMOVE_FROM_OPERATIONAL_SCOPE|OTHER
          operational_effect: <bounded effect>
          compatibility_group_id: <group-id>
          conflicts_with_containment_ids: [<containment-id>]
          compatibility_assessments:
            - assessment_id: <stable-id>
              assessment_sequence: <positive-integer>
              previous_assessment_id: <assessment-id or null>
              compatibility_status: COMPATIBLE|CONFLICTING|UNDETERMINED
              assessed_by: <human/institution reference>
              assessor_competence_or_authority_basis: <reference>
              assessment_evidence: [<reference>]
              assessed_at: <ISO-8601>
              limitations: <limitations or NONE>
      remediation: <action>
      responsible_authority: <authority reference>
      status: OPEN|BLOCKED|IN_REMEDIATION|CLOSED|CONTAINED|OUT_OF_SCOPE|REJECTED
      disposition_kind: NONE|REMEDIATION_REJECTED|EVIDENCE_REJECTED|SCOPE_CONTAINED|OPERATIONAL_SCOPE_REMOVED|FINDING_CLOSED
      authorized_terminal_treatment: <treatment or NONE>
      treatment_evidence: <references-or-NONE>
      finding_protection_disposition:
        disposition_type: FINDING_CLOSED|SCOPE_CONTAINED|OPERATIONAL_SCOPE_REMOVED|UNRESOLVED
        affected_scope_id: <stable-scope-id>
        authorization: <authority reference or NONE>
        evidence: <references-or-NONE>
      closure_evidence: <references-or-NONE>
      closure_authority: <authority reference or NONE>
      closure_date: <ISO-8601 or null>
```

`MIXED_CORRECTION` requires at least one implementation and one domain component. Components and containment identifiers are unique. Components close independently. `REJECTED` records rejection of proposed remediation or evidence; it never says the underlying finding disappeared. `CONTAINED` limits the affected scope, `OUT_OF_SCOPE` removes that scope from operation, and only `CLOSED` with closure evidence declares the original finding closed.

Compatibility is a declared human assessment, never an automated inference from free text. Every referenced containment ID must exist. The latest valid assessment is selected by contiguous `assessment_sequence`, beginning at 1 and linked through `previous_assessment_id`; a changed assessment appends a new entry and never rewrites the former one. `UNDETERMINED`, any declared conflict, a `COMPATIBLE` assertion that names a conflict, asymmetric `conflicts_with_containment_ids`, a missing reciprocal declaration or inconsistent compatibility group fails closed. Free text may explain but cannot supply machine-relevant compatibility.

Parent aggregation is exhaustive and evaluated in this order:

1. malformed fields, unknown states, missing evidence for an asserted terminal treatment, `UNDETERMINED`/`CONFLICTING`/asymmetric containment assessments, incompatible groups or inconsistent parent declarations are structurally invalid and fail closed;
2. any `BLOCKED` component produces parent `BLOCKED`;
3. any `OPEN` or `IN_REMEDIATION` component produces parent `UNRESOLVED`;
4. any `REJECTED` component produces parent `UNRESOLVED`, unless `parent_disposition: COMPLETE_PROPOSAL_REJECTED` is authorized and every component supplies a structured, authorized `finding_protection_disposition` of `FINDING_CLOSED`, `SCOPE_CONTAINED` or `OPERATIONAL_SCOPE_REMOVED` with evidence; only that complete-parent case produces parent `REJECTED`;
5. all components `CLOSED` with closure evidence produce parent `CLOSED`;
6. a terminal set containing at least one `CONTAINED`, with every other component `CLOSED` or declared-`COMPATIBLE` `CONTAINED`, produces `RESOLVED_WITH_CONTAINMENT`;
7. all components `OUT_OF_SCOPE`, with an authorized reason and evidence for every affected scope, produce parent `OUT_OF_SCOPE`;
8. a terminal mixture of `CLOSED`, declared-`COMPATIBLE` `CONTAINED` and `OUT_OF_SCOPE` produces `RESOLVED_WITH_CONTAINMENT` and preserves every bounded scope and reason;
9. every other or incomplete combination is invalid and fails closed pending human resolution.

No component state neutralizes another. Parent terminal treatment requires evidence for every mandatory component and does not expand its effect to unrelated scope.

### SPECIALIST_OPINIONS

Each opinion lineage inside `specialist_authority.opinions` is independent and contains immutable revisions plus append-only replacement/revalidation events:

```yaml
- opinion_lineage_id: <stable-lineage-id>
  opinion_id: <stable-opinion-id>
  revisions:
    - opinion_revision_id: <revision-id>
      predecessor_opinion_revision_id: <revision-id or NONE>
      replacement_or_revalidation_event_id: <event-id or NONE>
      supersedes_revision_id: <revision-id or NONE>
      replacement_reason: <reason or NONE>
      specialist_identity_reference: <controlled reference>
      competence_evidence: [<reference>]
      authority_basis: <basis>
      concrete_question: <question>
      original_conclusion: <conclusion>
      sources: [<reference>]
      original_scope: <scope>
      territorial_limit: <territory>
      normative_version: <version/reference>
      responsibility_scope: <scope>
      commercial_relationship: <controlled reference or NONE>
      declared_conflicts: <conflict-references-or-NONE>
      conflict_assessment: NONE|MITIGATED|OPEN|UNDISCLOSED_MATERIAL_DISCOVERED
      mitigation: <control or NONE>
      issued_at: <ISO-8601>
      original_validity_conditions:
        warning_at: <ISO-8601 or null>
        review_due_at: <ISO-8601>
        expires_at: <ISO-8601 or null>
        alternative_validity_condition: <condition or NONE>
      evidence_reference: <reference>
  revision_events:
    - event_id: <event-id>
      event_sequence: <positive-integer>
      previous_event_id: <event-id or null>
      opinion_lineage_id: <stable-lineage-id>
      affected_revision_ids: [<revision-id>]
      event_type: ISSUED|DECLARED_CURRENT|REVIEW_OVERDUE|EXPIRED|WITHDRAWN|SUPERSEDED|REVALIDATED|REPLACED
      resulting_revision_effects:
        - opinion_revision_id: <revision-id>
          resulting_revision_status: CURRENT_SUPPORTING|CURRENT_CONTRARY|CURRENT_INCONCLUSIVE|OVERDUE_FOR_REVIEW|EXPIRED|WITHDRAWN|SUPERSEDED|REVALIDATED|INAPPLICABLE
      reason: <reason>
      evidence_reference: <reference>
      authority: <human authority reference>
      effective_at: <ISO-8601>
```

Revision content is immutable. Temporal and current status is derived only from the valid append-only event chain. Genesis sequence is 1 with `previous_event_id: null`; each later event is previous+1 and references the immediately preceding event. Duplicate/gapped/rolled-back sequences, branches, cycles, missing events or revisions, and cross-lineage references fail closed. `effective_at` is evidence of timing, not event ordering authority.

Revalidation creates an immutable successor revision and one structured event whose effects mark the predecessor `REVALIDATED` and the successor exactly one current status; paired consecutive linked events are also valid when both are normatively complete. Replacement creates a successor in the same lineage or a new explicitly cross-referenced lineage when identity/question materially changes. Prior revisions and events are never rewritten or deleted. Exactly one current usable revision is derived from the terminal valid event. Expired, withdrawn or superseded revisions cannot become current without a new authorized successor/revalidation event.

A material change to scope, conclusion, sources, responsibility or validity requires a non-empty `replacement_reason` and supporting event evidence; `NONE` is prohibited. Every referenced revision belongs to the event's `opinion_lineage_id`. Automation validates structure only and cannot decide substantive equivalence, applicability or sufficiency.

Temporal chronology is structural: when present, `warning_at < review_due_at`; when `expires_at` exists, `review_due_at <= expires_at`; without `expires_at`, `alternative_validity_condition` must be explicit and non-`NONE`. Violations fail closed. Passing dates may cause authorized or deterministic events but dates never order the chain.

Parent aggregation consumes the single current applicable revision derived from each valid opinion lineage while retaining all historical contrary evidence for human review:

- `BLOCKED` has first precedence when a mandatory lineage has no current usable applicable revision or its current revision has open material conflict;
- otherwise `OPEN_DIVERGENCE` applies when applicable supporting and contrary opinions coexist, regardless of majority count;
- otherwise `INCONCLUSIVE` applies when an applicable opinion is inconclusive or no applicable supporting opinion exists;
- otherwise `STRUCTURALLY_SUPPORTING` applies when at least one current applicable revision has `CURRENT_SUPPORTING`, with no `CURRENT_CONTRARY`, `CURRENT_INCONCLUSIVE` or open conflict; `OVERDUE_FOR_REVIEW` remains usable only when an accompanying current conclusion effect remains derivable, every other validity condition holds and no stricter documented rule blocks it;
- `NONE` applies only when no current opinion participates; withdrawn opinions remain preserved but do not count;
- one supporting current revision cannot neutralize another applicable contrary current revision, and preserved historical contrary evidence remains visible for substantive human review;
- these are structural aggregates only; competent human authority separately determines substantive sufficiency and release.

No `EXPIRING` normative state exists. Passing `review_due_at` before expiry appends or deterministically proposes a `REVIEW_OVERDUE` event producing `OVERDUE_FOR_REVIEW`, not a lifecycle transition. A documented stricter human rule may block earlier. Failure of applicability causes immediate bounded containment. At expiry, an `EXPIRED` event records that continued reliance is prohibited unless a valid successor revalidation already exists. Dates never renew evidence, order events or affect unrelated scope.

### DIVERGENCE_OR_CONFLICT_RESOLUTION

Required when closing material divergence or declaring material conflict mitigated:

```yaml
resolution:
  resolver_identity: <human/institution reference>
  resolver_competence: [<relevant evidence>]
  authority_basis: <applicable basis>
  evidence_considered: [<reference>]
  resolution_method: EXTERNAL_AUTHORITY|INDEPENDENT_REVIEW|INSTITUTIONAL_AUTHORITY|ADDITIONAL_JUSTIFIED_OPINION|REJECTION|OUT_OF_SCOPE
  scope: <bounded scope>
  limitations: <limits>
  decided_at: <ISO-8601>
  review_or_expiry_condition: <condition>
  resulting_containment_or_release: <result>
```

Product Owner status, payment, hierarchy, customer preference, majority count or AI recommendation cannot substitute for relevant resolver competence and authority basis.

### RECLASSIFICATION_HISTORY

Trigger: any reassessment of materiality, including D1→D2, D1→D3, D2→D3 or authorized downgrade.

```yaml
reclassification_lineage:
  lineage_id: <stable-lineage-id>
  record_revision_id: <record-revision-id>
  predecessor_record_id: <record-id or NONE>
  successor_record_id: <record-id or NONE>
  current_record_id: <unique-current-record-id>
  lineage_status: CURRENT|HISTORICAL
  events:
    - event_id: <stable-event-id>
      event_sequence: <positive-integer>
      previous_event_id: <event-id or null>
      previous_classification: D1|D2|D3
      new_classification: D1|D2|D3
      event_date: <ISO-8601>
      reason: <reason>
      triggering_finding_or_evidence: [<reference>]
      authority: <authority reference>
      predecessor_record_id: <record-id>
      successor_record_id: <record-id>
      expected_previous_head_id: <record-id>
      declared_new_head_id: <record-id>
      preserved_disposition_and_effect: <status/effect snapshot>
```

Reclassification always creates a successor and never overwrites predecessor substantive content. The append-only event supplies both logical directions; the successor carries the same event, lineage and predecessor reference. Event ordering is determined only by `event_sequence`, never by `event_date`.

Genesis has sequence 1 and `previous_event_id: null`. Every later event has sequence exactly previous+1, references the immediately preceding event, and sets `expected_previous_head_id` to the effective head declared by that event. `declared_new_head_id` must equal `successor_record_id`, and predecessor, successor and both head IDs must resolve to the same `lineage_id`. The unique terminal event in a valid chain declares `current_record_id`; it makes former heads historical by force of the event without editing their content.

Duplicate sequences, gaps, rollback, late lower-sequence events, branches, competing terminal events, cycles, self-reference, cross-lineage references, missing predecessors, duplicated successors or events, disconnected revisions and inconsistent local/event links fail closed without choosing a winner. Downgrade requires explicit justification and cannot remove unresolved materiality, specialist or containment controls. Automation validates chain structure and uniqueness but cannot authorize or substantively justify an event.

### GROUPED_D1_ITEMS

Trigger: two or more genuinely D1 items share context and preparation conditions. This is an administrative envelope, not a decision record and not a lifecycle authority.

```yaml
grouped_d1:
  group_id: <stable-id>
  project_scope_id: <stable-project-scope-id>
  common_context: <context>
  grouping_rationale: <reason>
  common_evidence: [<reference>]
  preparation_authority: <preparer reference>
  created_at: <ISO-8601>
  item_identifiers: [<item-id>]
  group_integrity_status: COMPLETE|ITEM_ESCALATED|INVALID
  items:
    - item_id: <stable-id>
      project_scope_id: <stable-project-scope-id>
      materiality: D1
      specialist_requirement: NOT_REQUIRED|RECOMMENDED
      request_decision_summary: <summary>
      affected_scope: <scope>
      disposition: ACCEPTED|REJECTED|DEFERRED
      item_specific_evidence: <references-or-NONE>
      authority_manifestation: <human evidence reference>
      lifecycle_result: <recognized lifecycle state>
      group_id: <stable-id>
      escalation_required: true|false
      successor_record_id: <record-id or NONE>
      escalation_lineage_link: <lineage reference or NONE>
```

The envelope has no decision `status`, `disposition`, acceptance, promulgation, effective date or operational effect. Mixed item outcomes are valid because each item has its own authority manifestation and lifecycle result. Group status is structural only.

Within a `project_scope_id`, `item_id` is project-unique and an active item belongs to exactly one active group. Duplicate membership fails closed. Only declared D1 items with `NOT_REQUIRED` or `RECOMMENDED` specialist treatment may remain. D2, D3 or `MANDATORY` items set `escalation_required: true`, leave the active group and require a resolvable successor in the same project scope; the successor references the original group/item through its reclassification lineage. The envelope retains the item historically and uses `ITEM_ESCALATED`. `COMPLETE` is invalid while any escalated item lacks a valid successor or lineage link.

Future derivations must make the project registry/index capable of checking project-wide item uniqueness, active-group membership, successor existence and reciprocal group/item references; this is an index contract, not a second canonical decision or executable registry created by this candidate. Automation validates declared materiality and specialist state but cannot infer them. Human-discovered misclassification creates a finding and reclassification event. Group evidence cannot replace item-specific evidence where differences matter, and grouping cannot conceal rejection, dissent, risk, effect or specialist requirement.

### TERMINAL_EFFECT_BLOCK

Trigger: terminal status.

```yaml
terminal_effect:
  terminal_state: REJECTED|WITHDRAWN|REVOKED|SUPERSEDED|EXPIRED
  terminal_from_status: REQUESTED|DELIBERATED|DEFERRED|ACCEPTED|PROMULGATED
  terminal_act_reference: <reference>
  terminal_effective_date: <ISO-8601>
  supersedes: <decision-id or null>
  superseded_by: <decision-id or null>
```

The lifecycle matrix controls permitted predecessor, grants, effective date and successor requirements.

## 5. Conditionality matrix

| Module | Trigger/materiality | Required when triggered | Must be absent when | Blocking consequence | Release/closure | Human authority | Structural checks |
|---|---|---|---|---|---|---|---|
| `CANONICAL_CORE` | Every D1-D3 | All 20 fields | Never | Record invalid | Complete valid core | Authority fields identify human | Presence, enums, patterns, lifecycle combinations |
| `D1_EXTENSION` | D1 | Four D1 fields | D2/D3 | Record invalid | Correct matching extension | Product Owner | Presence/class match |
| `D2_EXTENSION` | D2 | Ten D2 fields | D1/D3 | Record invalid | Correct matching extension | Product Owner | Presence/class match |
| `D3_EXTENSION` | D3 | Sixteen D3 fields | D1/D2 | Record invalid | Correct matching extension | Product Owner plus applicable external authority | Presence/class match |
| `SPECIALIST_AUTHORITY_BLOCK` | Specialist/source/domain trigger; any class | Triggered fields and applicable opinions/resolution | No specialist/source/domain question | Affected scope blocked for mandatory/uncertain cases | All release conditions plus human authorization | Competent human and reserved external authority | Presence, state consistency, dates, links; no substantive inference |
| `MIXED_CORRECTION_COMPONENTS` | Correction; any class | Parent, components, structured containment assessments/protection | No correction | Parent unresolved/invalid | Exhaustive aggregation from declared compatibility | Responsible authority and competent assessor | Unique IDs, reciprocal conflicts, monotonic assessments, state algorithm |
| `SPECIALIST_OPINIONS` | Opinion relied upon; any class | Immutable revisions, monotonic events/effects and every opinion field | No opinion | Opinion unusable; mandatory scope blocked | One event-derived current revision plus human sufficiency | Competent evaluator/resolver | Restricted YAML, event chain/effects, chronology and aggregation |
| `RECLASSIFICATION_LINEAGE` | Class changes; any class | Lineage, revision and contiguous event fields | No reassessment | Successor not authoritative | Unique terminal head in monotonic chain | Competent classification authority | Restricted YAML, sequence, previous event/head, same-lineage graph |
| `GROUPED_D1_ITEMS` | Two or more independent D1 items | Envelope plus item project scope/materiality/specialist/authority/result | No grouping or ineligible item | Envelope invalid; no item authority inferred | Same-project successor for escalation | Item-specific Product Owner; preparer has no decisional effect | Project uniqueness, one active group, eligibility and reciprocal links |
| `TERMINAL_EFFECT_BLOCK` | Terminal state | Every terminal field and applicable successor link | Non-terminal state | Terminal transition invalid | New linked record/valid successor | Lifecycle authority | Predecessor, dates, grants and successor |

## 6. Lifecycle and release

The deterministic matrix in `LIFECYCLE.md` controls status, disposition, acceptance, promulgation, effective date and terminal effect. Conditional blocks cannot override it. Mandatory release additionally requires evidence, verified competence, covered scope, current applicability, resolved or competently mitigated conflict and divergence, explicit responsibility, human release authorization and separation from reserved external authority.

## 7. Complete conforming RC6 candidate examples

Every example is `COMPLETE_CONFORMING_CANDIDATE_EXAMPLE`, fictional, independent unless explicitly linked, `ACCEPTED / IN_FORCE`, and creates no project authority or derivation. Flow mappings are used only for compact presentation; every required field is present and no restricted YAML composition feature is used.

### 7.1 Ordinary D1 — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-RC6-D1-2099-0001
project_id: PO-GOV-RC6-FICTIONAL
title: COMPLETE_CONFORMING_CANDIDATE_EXAMPLE ordinary D1
materiality_class: D1
classification_justification: fictional local reversible wording decision
status: REQUESTED
disposition: PENDING
request_source: HUMAN
original_request_reference: RC6-D1-REQUEST
authority_role: PRODUCT_OWNER
authority_holder: RC6-FICTIONAL-HUMAN
authority_provenance: RC6-FICTIONAL-AUTHORITY
evidence_references: [RC6-D1-E1]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: INTERNAL
framework_version: 1.0.0
framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
d1: {affected_scope: fictional.ui.help, result_summary: clarify fictional wording, reversibility: REVERSIBLE, residual_risk: NONE}
```

Absent modules: no specialist question, correction, reclassification or terminal state is triggered.

### 7.2 Grouped D1 with independent outcomes — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
grouped_d1:
  group_id: RC6-GROUP-MIXED-G1
  project_scope_id: RC6-PROJECT-SCOPE-GROUP-MIXED
  common_context: fictional interface vocabulary
  grouping_rationale: shared preparation without merged authority
  common_evidence: [RC6-GROUP-MIXED-E1]
  preparation_authority: RC6-FICTIONAL-PREPARER
  created_at: 2099-01-01
  item_identifiers: [RC6-GROUP-MIXED-I1, RC6-GROUP-MIXED-I2]
  group_integrity_status: COMPLETE
  items:
    - {item_id: RC6-GROUP-MIXED-I1, project_scope_id: RC6-PROJECT-SCOPE-GROUP-MIXED, materiality: D1, specialist_requirement: NOT_REQUIRED, request_decision_summary: accept fictional label, affected_scope: fictional.ui.a, disposition: ACCEPTED, item_specific_evidence: RC6-I1-E1, authority_manifestation: RC6-I1-PO-ACT, lifecycle_result: ACCEPTED, group_id: RC6-GROUP-MIXED-G1, escalation_required: false, successor_record_id: NONE, escalation_lineage_link: NONE}
    - {item_id: RC6-GROUP-MIXED-I2, project_scope_id: RC6-PROJECT-SCOPE-GROUP-MIXED, materiality: D1, specialist_requirement: RECOMMENDED, request_decision_summary: defer fictional label, affected_scope: fictional.ui.b, disposition: DEFERRED, item_specific_evidence: RC6-I2-E1, authority_manifestation: RC6-I2-PO-ACT, lifecycle_result: DEFERRED, group_id: RC6-GROUP-MIXED-G1, escalation_required: false, successor_record_id: NONE, escalation_lineage_link: NONE}
```

Absent modules: the envelope is non-decisional; neither item triggers mandatory specialist, correction, escalation or terminal effect.

### 7.3 Grouped item escalated to D2 — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

This scenario is presented as two independently validatable YAML payloads. The first payload is the D1 grouped envelope. The second payload is the D2 successor record. Their relationship is expressed only through schema-defined identifiers and reciprocal references, not through presentation-only root keys.

```yaml
grouped_d1:
  group_id: RC7-GROUP-ESC-G1
  project_scope_id: RC7-PROJECT-SCOPE-GROUP-ESC
  common_context: fictional grouped review
  grouping_rationale: original D1 preparation context
  common_evidence: [RC7-GROUP-ESC-E1]
  preparation_authority: RC7-FICTIONAL-PREPARER
  created_at: 2099-01-01
  item_identifiers: [RC7-GROUP-ESC-I1]
  group_integrity_status: ITEM_ESCALATED
  items:
- {item_id: RC7-GROUP-ESC-I1, project_scope_id: RC7-PROJECT-SCOPE-GROUP-ESC, materiality: D2, specialist_requirement: NOT_REQUIRED, request_decision_summary: fictional semantic effect discovered, affected_scope: fictional.semantic.a, disposition: DEFERRED, item_specific_evidence: RC7-GROUP-ESC-F1, authority_manifestation: RC7-GROUP-ESC-PO-ACT, lifecycle_result: DEFERRED, group_id: RC7-GROUP-ESC-G1, escalation_required: true, successor_record_id: PO-DEC-RC7-GROUP-ESC-D2, escalation_lineage_link: RC7-LINEAGE-GROUP-ESC}
```

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-RC7-GROUP-ESC-D2
project_id: RC7-PROJECT-SCOPE-GROUP-ESC
title: COMPLETE_CONFORMING_CANDIDATE_EXAMPLE escalated grouped item
materiality_class: D2
classification_justification: fictional semantic effect requires D2
status: REQUESTED
disposition: PENDING
request_source: AUDIT
original_request_reference: RC7-GROUP-ESC-I1
authority_role: PRODUCT_OWNER
authority_holder: RC7-FICTIONAL-HUMAN
authority_provenance: RC7-FICTIONAL-AUTHORITY
evidence_references: [RC7-GROUP-ESC-F1]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: INTERNAL
framework_version: 1.0.0
framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
d2: {affected_scope: fictional.semantic.a, affected_stakeholders: [FICTIONAL-USERS], alternatives: [remove, review, no-action], risks: [unsupported-meaning], dependencies: [NONE], data_or_semantic_effect: fictional meaning change, implementation_scope: no activation, validation_plan: verify evidence, rollback_or_containment: keep disabled, publication_or_user_effect: NONE}
reclassification_lineage:
  lineage_id: RC7-LINEAGE-GROUP-ESC
  record_revision_id: RC7-GROUP-ESC-R2
  predecessor_record_id: RC7-GROUP-ESC-I1
  successor_record_id: NONE
  current_record_id: PO-DEC-RC7-GROUP-ESC-D2
  lineage_status: CURRENT
  events:
- {event_id: RC7-GROUP-ESC-EV1, event_sequence: 1, previous_event_id: null, previous_classification: D1, new_classification: D2, event_date: 2099-01-02, reason: fictional semantic effect, triggering_finding_or_evidence: [RC7-GROUP-ESC-F1], authority: RC7-GROUP-ESC-PO-ACT, predecessor_record_id: RC7-GROUP-ESC-I1, successor_record_id: PO-DEC-RC7-GROUP-ESC-D2, expected_previous_head_id: RC7-GROUP-ESC-I1, declared_new_head_id: PO-DEC-RC7-GROUP-ESC-D2, preserved_disposition_and_effect: DEFERRED/NONE}
```

Absent modules: no specialist/source question, governed correction or terminal state is asserted; the lineage is triggered and complete.

### 7.4 D2 with mandatory specialist validation — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-RC6-SPECIALIST-0001
project_id: PO-GOV-RC6-FICTIONAL
title: COMPLETE_CONFORMING_CANDIDATE_EXAMPLE mandatory specialist
materiality_class: D2
classification_justification: fictional bounded domain uncertainty
status: REQUESTED
disposition: PENDING
request_source: AUDIT
original_request_reference: RC6-SPECIALIST-REQUEST
authority_role: PRODUCT_OWNER
authority_holder: RC6-FICTIONAL-HUMAN
authority_provenance: RC6-FICTIONAL-AUTHORITY
evidence_references: [RC6-SPECIALIST-F1]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: INTERNAL
framework_version: 1.0.0
framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
d2: {affected_scope: fictional.rule.a, affected_stakeholders: [FICTIONAL-USERS], alternatives: [validate, remove, no-action], risks: [unsupported-claim], dependencies: [NONE], data_or_semantic_effect: fictional rule meaning, implementation_scope: blocked, validation_plan: bounded specialist review, rollback_or_containment: suppress fictional claim, publication_or_user_effect: NONE}
specialist_authority:
  domain_authority_required: true
  specialist_requirement: MANDATORY
  specialist_question: Is fictional rule A supportable in the declared scope?
  source_sufficiency: NOT_USED
  source_sufficiency_evaluator: RC6-FICTIONAL-EVALUATOR
  evaluator_competence_evidence: [RC6-FICTIONAL-COMPETENCE]
  evaluator_authority_basis: RC6-FICTIONAL-BASIS
  blocked_scope: fictional.rule.a
  containment: suppress fictional claim
  containment_release_status: BLOCKED
  containment_release_authority: NONE
  parent_opinion_status: STRUCTURALLY_SUPPORTING
  opinions:
    - opinion_lineage_id: RC6-OP-SPECIALIST-L1
      opinion_id: RC6-OP-SPECIALIST-O1
      revisions:
        - {opinion_revision_id: RC6-OP-SPECIALIST-R1, predecessor_opinion_revision_id: NONE, replacement_or_revalidation_event_id: NONE, supersedes_revision_id: NONE, replacement_reason: NONE, specialist_identity_reference: RC6-FICTIONAL-SPECIALIST, competence_evidence: [RC6-FICTIONAL-COMPETENCE], authority_basis: RC6-FICTIONAL-BASIS, concrete_question: Is fictional rule A supportable?, original_conclusion: supporting only for fictional scope, sources: [RC6-FICTIONAL-SOURCE], original_scope: fictional.rule.a, territorial_limit: FICTIONAL-TERRITORY, normative_version: FICTIONAL-V1, responsibility_scope: advisory-only, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-01-01, original_validity_conditions: {warning_at: 2099-05-01, review_due_at: 2099-06-01, expires_at: 2100-01-01, alternative_validity_condition: NONE}, evidence_reference: RC6-OP-SPECIALIST-E1}
      revision_events:
        - {event_id: RC6-OP-SPECIALIST-EV1, event_sequence: 1, previous_event_id: null, opinion_lineage_id: RC6-OP-SPECIALIST-L1, affected_revision_ids: [RC6-OP-SPECIALIST-R1], event_type: ISSUED, resulting_revision_effects: [{opinion_revision_id: RC6-OP-SPECIALIST-R1, resulting_revision_status: CURRENT_SUPPORTING}], reason: fictional initial issuance, evidence_reference: RC6-OP-SPECIALIST-E1, authority: RC6-FICTIONAL-SPECIALIST, effective_at: 2099-01-01}
  resolution: null
```

Absent modules: no correction, reclassification or terminal state is asserted; specialist authority is triggered and complete.

### 7.5 Mixed correction with structured compatible containment — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-RC6-MIXED-0001
project_id: PO-GOV-RC6-FICTIONAL
title: COMPLETE_CONFORMING_CANDIDATE_EXAMPLE mixed correction
materiality_class: D2
classification_justification: fictional implementation and domain findings
status: REQUESTED
disposition: PENDING
request_source: AUDIT
original_request_reference: RC6-MIXED-REQUEST
authority_role: PRODUCT_OWNER
authority_holder: RC6-FICTIONAL-HUMAN
authority_provenance: RC6-FICTIONAL-AUTHORITY
evidence_references: [RC6-MIXED-F1]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: INTERNAL
framework_version: 1.0.0
framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
d2: {affected_scope: fictional.mixed, affected_stakeholders: [FICTIONAL-USERS], alternatives: [correct-and-contain, remove, no-action], risks: [unsupported-rule], dependencies: [NONE], data_or_semantic_effect: fictional mixed defect, implementation_scope: bounded remediation, validation_plan: independent component evidence, rollback_or_containment: retain domain containment, publication_or_user_effect: NONE}
correction:
  correction_type: MIXED_CORRECTION
  parent_status: RESOLVED_WITH_CONTAINMENT
  parent_disposition: NONE
  components:
    - {component_id: RC6-MIXED-C1, correction_type: IMPLEMENTATION_CORRECTION, affected_scope: fictional.code, finding: fictional mismatch, evidence: [RC6-MIXED-E1], containments: [], remediation: correct fictional code, responsible_authority: RC6-FICTIONAL-PO, status: CLOSED, disposition_kind: FINDING_CLOSED, authorized_terminal_treatment: corrected, treatment_evidence: [RC6-MIXED-E2], finding_protection_disposition: {disposition_type: FINDING_CLOSED, affected_scope_id: RC6-SCOPE-CODE, authorization: RC6-FICTIONAL-PO, evidence: [RC6-MIXED-E2]}, closure_evidence: [RC6-MIXED-E2], closure_authority: RC6-FICTIONAL-PO, closure_date: 2099-01-02}
    - component_id: RC6-MIXED-C2
      correction_type: DOMAIN_CORRECTION
      affected_scope: fictional.rule
      finding: fictional unsupported rule
      evidence: [RC6-MIXED-E3]
      containments:
        - containment_id: RC6-CONTAINMENT-C2
          affected_scope_id: RC6-SCOPE-RULE
          containment_type: DISABLE
          operational_effect: disable fictional rule
          compatibility_group_id: RC6-COMPAT-G1
          conflicts_with_containment_ids: []
          compatibility_assessments:
            - {assessment_id: RC6-COMPAT-A1, assessment_sequence: 1, previous_assessment_id: null, compatibility_status: COMPATIBLE, assessed_by: RC6-FICTIONAL-ASSESSOR, assessor_competence_or_authority_basis: RC6-FICTIONAL-BASIS, assessment_evidence: [RC6-COMPAT-E1], assessed_at: 2099-01-02, limitations: fictional.rule only}
      remediation: validate or remove fictional rule
      responsible_authority: RC6-FICTIONAL-PO
      status: CONTAINED
      disposition_kind: SCOPE_CONTAINED
      authorized_terminal_treatment: disable fictional rule
      treatment_evidence: [RC6-COMPAT-E1]
      finding_protection_disposition: {disposition_type: SCOPE_CONTAINED, affected_scope_id: RC6-SCOPE-RULE, authorization: RC6-FICTIONAL-PO, evidence: [RC6-COMPAT-E1]}
      closure_evidence: NONE
      closure_authority: NONE
      closure_date: null
```

Absent modules: no specialist question, reclassification or terminal state is asserted; correction is triggered and complete.

### 7.6 Two divergent specialist opinions — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-RC6-DIVERGENCE-0001
project_id: PO-GOV-RC6-FICTIONAL
title: COMPLETE_CONFORMING_CANDIDATE_EXAMPLE divergent opinions
materiality_class: D2
classification_justification: fictional bounded specialist divergence
status: REQUESTED
disposition: PENDING
request_source: AUDIT
original_request_reference: RC6-DIVERGENCE-REQUEST
authority_role: PRODUCT_OWNER
authority_holder: RC6-FICTIONAL-HUMAN
authority_provenance: RC6-FICTIONAL-AUTHORITY
evidence_references: [RC6-DIVERGENCE-F1]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: INTERNAL
framework_version: 1.0.0
framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
d2: {affected_scope: fictional.claim, affected_stakeholders: [FICTIONAL-USERS], alternatives: [contain, review, reject], risks: [unsupported-claim], dependencies: [NONE], data_or_semantic_effect: fictional claim, implementation_scope: blocked, validation_plan: resolve divergence, rollback_or_containment: suppress claim, publication_or_user_effect: NONE}
specialist_authority:
  domain_authority_required: true
  specialist_requirement: MANDATORY
  specialist_question: Is fictional claim supportable?
  source_sufficiency: CONFLICTING
  source_sufficiency_evaluator: RC6-FICTIONAL-EVALUATOR
  evaluator_competence_evidence: [RC6-FICTIONAL-COMPETENCE]
  evaluator_authority_basis: RC6-FICTIONAL-BASIS
  blocked_scope: fictional.claim
  containment: suppress fictional claim
  containment_release_status: BLOCKED
  containment_release_authority: NONE
  parent_opinion_status: OPEN_DIVERGENCE
  opinions:
    - opinion_lineage_id: RC6-DIV-L1
      opinion_id: RC6-DIV-O1
      revisions:
        - {opinion_revision_id: RC6-DIV-R1, predecessor_opinion_revision_id: NONE, replacement_or_revalidation_event_id: NONE, supersedes_revision_id: NONE, replacement_reason: NONE, specialist_identity_reference: RC6-FICTIONAL-S1, competence_evidence: [RC6-C1], authority_basis: RC6-B1, concrete_question: Is fictional claim supportable?, original_conclusion: supporting, sources: [RC6-SRC1], original_scope: fictional.claim, territorial_limit: FICTIONAL-TERRITORY, normative_version: FICTIONAL-V1, responsibility_scope: advisory, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-01-01, original_validity_conditions: {warning_at: 2099-05-01, review_due_at: 2099-06-01, expires_at: 2100-01-01, alternative_validity_condition: NONE}, evidence_reference: RC6-DIV-E1}
      revision_events:
        - {event_id: RC6-DIV-EV1, event_sequence: 1, previous_event_id: null, opinion_lineage_id: RC6-DIV-L1, affected_revision_ids: [RC6-DIV-R1], event_type: ISSUED, resulting_revision_effects: [{opinion_revision_id: RC6-DIV-R1, resulting_revision_status: CURRENT_SUPPORTING}], reason: fictional issuance, evidence_reference: RC6-DIV-E1, authority: RC6-FICTIONAL-S1, effective_at: 2099-01-01}
    - opinion_lineage_id: RC6-DIV-L2
      opinion_id: RC6-DIV-O2
      revisions:
        - {opinion_revision_id: RC6-DIV-R2, predecessor_opinion_revision_id: NONE, replacement_or_revalidation_event_id: NONE, supersedes_revision_id: NONE, replacement_reason: NONE, specialist_identity_reference: RC6-FICTIONAL-S2, competence_evidence: [RC6-C2], authority_basis: RC6-B2, concrete_question: Is fictional claim supportable?, original_conclusion: contrary, sources: [RC6-SRC2], original_scope: fictional.claim, territorial_limit: FICTIONAL-TERRITORY, normative_version: FICTIONAL-V1, responsibility_scope: advisory, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-01-02, original_validity_conditions: {warning_at: 2099-05-01, review_due_at: 2099-06-01, expires_at: 2100-01-01, alternative_validity_condition: NONE}, evidence_reference: RC6-DIV-E2}
      revision_events:
        - {event_id: RC6-DIV-EV2, event_sequence: 1, previous_event_id: null, opinion_lineage_id: RC6-DIV-L2, affected_revision_ids: [RC6-DIV-R2], event_type: ISSUED, resulting_revision_effects: [{opinion_revision_id: RC6-DIV-R2, resulting_revision_status: CURRENT_CONTRARY}], reason: fictional issuance, evidence_reference: RC6-DIV-E2, authority: RC6-FICTIONAL-S2, effective_at: 2099-01-02}
  resolution: null
```

Absent modules: no correction, reclassification or terminal state is asserted; specialist divergence remains deliberately blocked.

### 7.7 Valid monotonic reclassification chain — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
schema_version: po-gov/1.0.0
decision_id: PO-DEC-RC6-LINEAGE-D3
project_id: PO-GOV-RC6-FICTIONAL
title: COMPLETE_CONFORMING_CANDIDATE_EXAMPLE D1 to D2 to D3
materiality_class: D3
classification_justification: fictional external effect discovered
status: REQUESTED
disposition: PENDING
request_source: AUDIT
original_request_reference: RC6-LINEAGE-REQUEST
authority_role: PRODUCT_OWNER
authority_holder: RC6-FICTIONAL-HUMAN
authority_provenance: RC6-FICTIONAL-AUTHORITY
evidence_references: [RC6-LINEAGE-F2]
acceptance: NOT_GRANTED
promulgation: NOT_GRANTED
effective_date: null
confidentiality: RESTRICTED
framework_version: 1.0.0
framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
d3: {affected_scope: fictional.external.claim, affected_stakeholders: [FICTIONAL-USERS], alternatives: [remove, validate, no-action], reinforced_risks: [external-claim], required_external_authorities: [NONE], authority_separation_analysis: fictional PO cannot replace external authority, legal_or_normative_basis: [NONE], privacy_and_access_controls: restricted evidence, security_controls: no external activation, external_effects_and_notice: none while requested, implementation_scope: blocked, validation_plan: reinforced review, rollback_and_external_remedy: remove fictional claim, additional_signatures: [NONE], independent_review: NONE, mandatory_review_date: 2099-06-01}
reclassification_lineage:
  lineage_id: RC6-LINEAGE-CHAIN-L1
  record_revision_id: RC6-LINEAGE-R3
  predecessor_record_id: PO-DEC-RC6-LINEAGE-D2
  successor_record_id: NONE
  current_record_id: PO-DEC-RC6-LINEAGE-D3
  lineage_status: CURRENT
  events:
    - {event_id: RC6-LINEAGE-E1, event_sequence: 1, previous_event_id: null, previous_classification: D1, new_classification: D2, event_date: 2099-01-01, reason: fictional semantic effect, triggering_finding_or_evidence: [RC6-LINEAGE-F1], authority: RC6-FICTIONAL-PO, predecessor_record_id: PO-DEC-RC6-LINEAGE-D1, successor_record_id: PO-DEC-RC6-LINEAGE-D2, expected_previous_head_id: PO-DEC-RC6-LINEAGE-D1, declared_new_head_id: PO-DEC-RC6-LINEAGE-D2, preserved_disposition_and_effect: REQUESTED/NONE}
    - {event_id: RC6-LINEAGE-E2, event_sequence: 2, previous_event_id: RC6-LINEAGE-E1, previous_classification: D2, new_classification: D3, event_date: 2099-01-02, reason: fictional external effect, triggering_finding_or_evidence: [RC6-LINEAGE-F2], authority: RC6-FICTIONAL-PO, predecessor_record_id: PO-DEC-RC6-LINEAGE-D2, successor_record_id: PO-DEC-RC6-LINEAGE-D3, expected_previous_head_id: PO-DEC-RC6-LINEAGE-D2, declared_new_head_id: PO-DEC-RC6-LINEAGE-D3, preserved_disposition_and_effect: REQUESTED/NONE}
```

Absent modules: this fixture asserts no specialist/source question, correction or terminal state; only D3 and reclassification lineage are triggered.

### 7.8 Valid opinion revalidation chain — COMPLETE_CONFORMING_CANDIDATE_EXAMPLE

```yaml
opinion_lineage_id: RC6-REVALIDATION-L1
opinion_id: RC6-REVALIDATION-O1
revisions:
  - {opinion_revision_id: RC6-REVALIDATION-R1, predecessor_opinion_revision_id: NONE, replacement_or_revalidation_event_id: NONE, supersedes_revision_id: NONE, replacement_reason: NONE, specialist_identity_reference: RC6-FICTIONAL-SPECIALIST, competence_evidence: [RC6-REVAL-C1], authority_basis: RC6-REVAL-B1, concrete_question: Is fictional claim supportable?, original_conclusion: supporting, sources: [RC6-REVAL-SRC1], original_scope: fictional.claim, territorial_limit: FICTIONAL-TERRITORY, normative_version: FICTIONAL-V1, responsibility_scope: advisory, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-01-01, original_validity_conditions: {warning_at: 2099-05-01, review_due_at: 2099-06-01, expires_at: 2100-01-01, alternative_validity_condition: NONE}, evidence_reference: RC6-REVALIDATION-E1}
  - {opinion_revision_id: RC6-REVALIDATION-R2, predecessor_opinion_revision_id: RC6-REVALIDATION-R1, replacement_or_revalidation_event_id: RC6-REVALIDATION-EV2, supersedes_revision_id: RC6-REVALIDATION-R1, replacement_reason: scheduled fictional revalidation with new evidence, specialist_identity_reference: RC6-FICTIONAL-SPECIALIST, competence_evidence: [RC6-REVAL-C1], authority_basis: RC6-REVAL-B1, concrete_question: Is fictional claim supportable?, original_conclusion: supporting, sources: [RC6-REVAL-SRC1, RC6-REVAL-SRC2], original_scope: fictional.claim, territorial_limit: FICTIONAL-TERRITORY, normative_version: FICTIONAL-V2, responsibility_scope: advisory, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-06-01, original_validity_conditions: {warning_at: 2100-05-01, review_due_at: 2100-06-01, expires_at: 2101-01-01, alternative_validity_condition: NONE}, evidence_reference: RC6-REVALIDATION-E2}
revision_events:
  - {event_id: RC6-REVALIDATION-EV1, event_sequence: 1, previous_event_id: null, opinion_lineage_id: RC6-REVALIDATION-L1, affected_revision_ids: [RC6-REVALIDATION-R1], event_type: ISSUED, resulting_revision_effects: [{opinion_revision_id: RC6-REVALIDATION-R1, resulting_revision_status: CURRENT_SUPPORTING}], reason: fictional initial issuance, evidence_reference: RC6-REVALIDATION-E1, authority: RC6-FICTIONAL-SPECIALIST, effective_at: 2099-01-01}
  - {event_id: RC6-REVALIDATION-EV2, event_sequence: 2, previous_event_id: RC6-REVALIDATION-EV1, opinion_lineage_id: RC6-REVALIDATION-L1, affected_revision_ids: [RC6-REVALIDATION-R1, RC6-REVALIDATION-R2], event_type: REVALIDATED, resulting_revision_effects: [{opinion_revision_id: RC6-REVALIDATION-R1, resulting_revision_status: REVALIDATED}, {opinion_revision_id: RC6-REVALIDATION-R2, resulting_revision_status: CURRENT_SUPPORTING}], reason: scheduled fictional revalidation with new evidence, evidence_reference: RC6-REVALIDATION-E2, authority: RC6-FICTIONAL-SPECIALIST, effective_at: 2099-06-01}
```

This is a complete opinion-lineage sub-schema fixture; decision-level modules are outside its declared fixture scope.

## 8. Negative anti-fixtures

Every case below is `INVALID_ANTI_FIXTURE`. The content is deliberately non-YAML pseudocode, prominently invalid, and must never be copied into a record.

```text
INVALID_ANTI_FIXTURE — PROHIBITED YAML COMPOSITION
anchor declaration: &forbidden
merge key: <<
expected result: INVALID_BEFORE_SEMANTIC_VALIDATION
```

```text
INVALID_ANTI_FIXTURE — COMPETING LINEAGE HEADS
sequence 2 declares head RC6-BAD-H1
another sequence 2 declares head RC6-BAD-H2
expected result: INVALID_CHAIN_NO_WINNER
```

```text
INVALID_ANTI_FIXTURE — CONFLICTING CONTAINMENT
containment C1 declares conflict with C2
containment C2 omits reciprocal conflict or declares COMPATIBLE
expected result: FAIL_CLOSED
```

```text
INVALID_ANTI_FIXTURE — MATERIAL OPINION CHANGE WITHOUT REASON
successor changes conclusion and sources; replacement_reason is NONE
expected result: INVALID_EVENT_CHAIN
```

```text
INVALID_ANTI_FIXTURE — DUPLICATE GROUP MEMBERSHIP
project scope P contains item I in active groups G1 and G2
expected result: INVALID_PROJECT_INDEX
```

## 9. Historical defect evidence — invalid and non-reusable

> **INVALID_HISTORICAL_EVIDENCE — DO NOT COPY OR PARSE AS CURRENT YAML.** Everything in this section is a quoted record of RC4/RC5 defects. It is non-normative, non-reusable, not a template and not a project decision. Angle-bracket placeholders and former shapes are intentionally invalid under RC6.

### Ordinary D1 without specialist

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
core: <valid CANONICAL_CORE with materiality D1 and status REQUESTED>
d1:
  affected_scope: interface.help_text
  result_summary: clarify existing authorized wording
  reversibility: REVERSIBLE
  residual_risk: NONE
```

No specialist, correction, grouping, reclassification or terminal block is present.

### Grouped D1

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
grouped_d1:
  group_id: RC5-GROUP-EXAMPLE-G1
  common_context: same interface vocabulary
  grouping_rationale: reduce repetition without merging effects
  common_evidence: [RC5-GROUP-E1]
  preparation_authority: RC5-EXAMPLE-PREPARER
  created_at: 2099-01-01
  item_identifiers: [RC5-GROUP-I1, RC5-GROUP-I2]
  group_integrity_status: COMPLETE
  items:
    - {item_id: RC5-GROUP-I1, request_decision_summary: clarify label A, affected_scope: ui.a, disposition: ACCEPTED, item_specific_evidence: RC5-I1-EVIDENCE, authority_manifestation: RC5-I1-PO-ACT, lifecycle_result: ACCEPTED, escalation_lineage_link: NONE}
    - {item_id: RC5-GROUP-I2, request_decision_summary: defer label B, affected_scope: ui.b, disposition: DEFERRED, item_specific_evidence: RC5-I2-EVIDENCE, authority_manifestation: RC5-I2-PO-ACT, lifecycle_result: DEFERRED, escalation_lineage_link: NONE}
```

The envelope deliberately contains no decision lifecycle, acceptance, promulgation or effect fields.

### D1 escalated to D2

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
core: <valid CANONICAL_CORE with materiality D2>
d2: <valid D2_EXTENSION>
reclassification_lineage:
  lineage_id: RC5-LINEAGE-EXAMPLE-A
  record_revision_id: RC5-LINEAGE-A-R2
  predecessor_record_id: RC5-LINEAGE-A-D1
  successor_record_id: NONE
  current_record_id: RC5-LINEAGE-A-D2
  lineage_status: CURRENT
  events:
    - {reclassification_event_id: RC5-LINEAGE-A-E1, previous_classification: D1, new_classification: D2, event_date: 2099-01-01, reason: semantic impact found, triggering_finding_or_evidence: [RC5-LINEAGE-A-F1], deciding_authority: RC5-EXAMPLE-PO, predecessor_record_id: RC5-LINEAGE-A-D1, successor_record_id: RC5-LINEAGE-A-D2, current_record_id: RC5-LINEAGE-A-D2, preserved_disposition_and_effect: REQUESTED/NONE}
```

### D2 with mandatory specialist validation

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
core: <valid CANONICAL_CORE with materiality D2>
d2: <valid D2_EXTENSION>
specialist_authority:
  domain_authority_required: true
  specialist_requirement: MANDATORY
  specialist_question: EXAMPLE-QUESTION
  source_sufficiency: NOT_USED
  blocked_scope: example.parameter
  containment_release_status: BLOCKED
  opinions: [<valid independent opinion lineage with one current revision>]
  resolution: null
```

### Mixed correction

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
core: <valid CANONICAL_CORE>
correction:
  correction_type: MIXED_CORRECTION
  parent_status: RESOLVED_WITH_CONTAINMENT
  parent_disposition: NONE
  components:
    - {component_id: RC5-MIX-C1, correction_type: IMPLEMENTATION_CORRECTION, affected_scope: code.path, finding: wrong implementation, evidence: [RC5-MIX-E1], containment: NONE, remediation: correct code, responsible_authority: RC5-PO, status: CLOSED, disposition_kind: FINDING_CLOSED, authorized_terminal_treatment: corrected, treatment_evidence: [RC5-MIX-E2], closure_evidence: [RC5-MIX-E2], closure_authority: RC5-PO, closure_date: 2099-01-01}
    - {component_id: RC5-MIX-C2, correction_type: DOMAIN_CORRECTION, affected_scope: rule.threshold, finding: unsupported rule, evidence: [RC5-MIX-E3], containment: disable affected rule, remediation: validate or remove, responsible_authority: RC5-PO, status: CONTAINED, disposition_kind: SCOPE_CONTAINED, authorized_terminal_treatment: disable affected rule, treatment_evidence: [RC5-MIX-E4], closure_evidence: NONE, closure_authority: NONE, closure_date: null}
```

### Two opinions with divergence

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
core: <valid CANONICAL_CORE>
specialist_authority:
  specialist_requirement: MANDATORY
  parent_opinion_status: OPEN_DIVERGENCE
  blocked_scope: example.claim
  containment_release_status: BLOCKED
  opinions:
    - {opinion_lineage_id: RC5-OP-L1, opinion_id: RC5-O1, current_opinion_revision_id: RC5-O1-R1, revisions: [<complete current SUPPORTING revision>], revision_events: []}
    - {opinion_lineage_id: RC5-OP-L2, opinion_id: RC5-O2, current_opinion_revision_id: RC5-O2-R1, revisions: [<complete current CONTRARY revision>], revision_events: []}
  resolution: null
```

The abbreviated opinion entries illustrate aggregation only; each real opinion must contain the complete opinion sub-schema.

### Historical RC4 anti-fixture set

The following preserved RC4-shaped collection is historical test input only. It is intentionally invalid under RC5 because it uses the former reclassification, opinion, correction and grouped-envelope shapes. It demonstrates that RC5 does not silently reinterpret or normalize earlier candidate examples. Repeated legacy `EXAMPLE` identifiers are preserved only as evidence of the competing-head defect and are never current fixture linkage. None is a project decision or a current valid fixture.

```text
INVALID_HISTORICAL_EXCERPT_DO_NOT_REUSE
ordinary_d1: &ordinary_d1
  schema_version: po-gov/1.0.0-rc.4
  decision_id: PO-DEC-EXAMPLE-2099-0001
  project_id: PO-GOV-CANDIDATE-EXAMPLE
  title: Ordinary D1 candidate fixture
  materiality_class: D1
  classification_justification: local reversible wording
  status: REQUESTED
  disposition: PENDING
  request_source: HUMAN
  original_request_reference: EXAMPLE-REQUEST-1
  authority_role: PRODUCT_OWNER
  authority_holder: EXAMPLE-HUMAN
  authority_provenance: EXAMPLE-AUTHORITY
  evidence_references: [EXAMPLE-E1]
  acceptance: NOT_GRANTED
  promulgation: NOT_GRANTED
  effective_date: null
  confidentiality: INTERNAL
  framework_version: 1.0.0-rc.4
  framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
  d1: {affected_scope: interface.help, result_summary: clarify text, reversibility: REVERSIBLE, residual_risk: NONE}

grouped_d1:
  <<: *ordinary_d1
  decision_id: PO-DEC-EXAMPLE-2099-0002
  title: Grouped D1 candidate fixture
  d1: {affected_scope: interface.labels, result_summary: grouped wording, reversibility: REVERSIBLE, residual_risk: NONE}
  grouped_d1:
    group_id: EXAMPLE-G1
    common_context: same vocabulary
    common_authority: EXAMPLE-AUTHORITY
    grouping_rationale: reduce repetition without merging effects
    shared_evidence: [EXAMPLE-E1]
    date: 2099-01-01
    items:
      - {item_id: I1, request_decision_summary: clarify label A, affected_scope: ui.a, disposition: ACCEPTED, item_specific_evidence: NONE, exception_or_escalation: false, lifecycle_result: ACCEPTED}
      - {item_id: I2, request_decision_summary: defer label B, affected_scope: ui.b, disposition: DEFERRED, item_specific_evidence: NONE, exception_or_escalation: false, lifecycle_result: DEFERRED}

escalated_d2: &escalated_d2
  schema_version: po-gov/1.0.0-rc.4
  decision_id: PO-DEC-EXAMPLE-2099-0003
  project_id: PO-GOV-CANDIDATE-EXAMPLE
  title: Escalated D2 candidate fixture
  materiality_class: D2
  classification_justification: semantic impact discovered
  status: REQUESTED
  disposition: PENDING
  request_source: AUDIT
  original_request_reference: EXAMPLE-REQUEST-2
  authority_role: PRODUCT_OWNER
  authority_holder: EXAMPLE-HUMAN
  authority_provenance: EXAMPLE-AUTHORITY
  evidence_references: [EXAMPLE-F1]
  acceptance: NOT_GRANTED
  promulgation: NOT_GRANTED
  effective_date: null
  confidentiality: INTERNAL
  framework_version: 1.0.0-rc.4
  framework_source_commit: 740af6570230fa711af4532cc471fa361a831d8c
  d2:
    affected_scope: example.semantic_rule
    affected_stakeholders: [EXAMPLE-USERS]
    alternatives: [remove, validate, no-action]
    risks: [unsupported meaning]
    dependencies: [NONE]
    data_or_semantic_effect: changes rule meaning
    implementation_scope: no activation before decision
    validation_plan: verify authority and tests
    rollback_or_containment: disable affected rule
    publication_or_user_effect: none while requested
  reclassification_history:
    - previous_classification: D1
      new_classification: D2
      date: 2099-01-01
      reason: semantic impact discovered
      triggering_finding_or_evidence: [EXAMPLE-F1]
      deciding_authority: EXAMPLE-AUTHORITY
      original_record_identifier: PO-DEC-EXAMPLE-2099-0001
      successor_or_current_record_identifier: PO-DEC-EXAMPLE-2099-0003
      preserved_disposition_and_effect: REQUESTED/NONE

d2_mandatory_specialist:
  <<: *escalated_d2
  decision_id: PO-DEC-EXAMPLE-2099-0004
  title: Mandatory specialist candidate fixture
  reclassification_history:
    - {previous_classification: D1, new_classification: D2, date: 2099-01-01, reason: specialist complexity, triggering_finding_or_evidence: [EXAMPLE-F2], deciding_authority: EXAMPLE-AUTHORITY, original_record_identifier: PO-DEC-EXAMPLE-2099-0001, successor_or_current_record_identifier: PO-DEC-EXAMPLE-2099-0004, preserved_disposition_and_effect: REQUESTED/NONE}
  specialist_authority:
    domain_authority_required: true
    specialist_requirement: MANDATORY
    specialist_question: Is example rule supportable in declared scope?
    source_sufficiency: NOT_USED
    source_sufficiency_evaluator: EXAMPLE-EVALUATOR
    evaluator_competence_evidence: [EXAMPLE-COMPETENCE]
    evaluator_authority_basis: EXAMPLE-BASIS
    blocked_scope: example.semantic_rule
    containment: disabled
    containment_release_status: BLOCKED
    containment_release_authority: NONE
    parent_opinion_status: STRUCTURALLY_SUPPORTING
    opinions:
      - opinion_id: O1
        specialist_identity_reference: EXAMPLE-SPECIALIST
        competence_evidence: [EXAMPLE-COMPETENCE]
        authority_basis: EXAMPLE-BASIS
        concrete_question: Is example rule supportable?
        conclusion: supporting for declared scope
        sources: [EXAMPLE-SOURCE]
        scope: example.semantic_rule
        territorial_limit: EXAMPLE-TERRITORY
        temporal_status: CURRENT
        normative_version: EXAMPLE-V1
        responsibility_scope: advisory only
        commercial_relationship: NONE
        declared_conflicts: NONE
        conflict_assessment: NONE
        mitigation: NONE
        issued_at: 2099-01-01
        review_due_at: 2099-06-01
        warning_lead_time: P30D
        expires_at: 2100-01-01
        validity_condition: source remains applicable
        status: SUPPORTING
        evidence_reference: EXAMPLE-OPINION-EVIDENCE
    resolution: null

mixed_correction:
  <<: *escalated_d2
  decision_id: PO-DEC-EXAMPLE-2099-0005
  title: Mixed correction candidate fixture
  reclassification_history:
    - {previous_classification: D1, new_classification: D2, date: 2099-01-01, reason: mixed semantic defect, triggering_finding_or_evidence: [EXAMPLE-F3], deciding_authority: EXAMPLE-AUTHORITY, original_record_identifier: PO-DEC-EXAMPLE-2099-0001, successor_or_current_record_identifier: PO-DEC-EXAMPLE-2099-0005, preserved_disposition_and_effect: REQUESTED/NONE}
  correction:
    correction_type: MIXED_CORRECTION
    parent_status: PARTIALLY_CLOSED
    components:
      - {component_id: C1, correction_type: IMPLEMENTATION_CORRECTION, affected_scope: code.path, finding: wrong implementation, evidence: [E1], containment: NONE, remediation: correct code, responsible_authority: EXAMPLE-AUTHORITY, status: CLOSED, closure_evidence: [E2], closure_authority: EXAMPLE-AUTHORITY, closure_date: 2099-01-01}
      - {component_id: C2, correction_type: DOMAIN_CORRECTION, affected_scope: rule.threshold, finding: unsupported rule, evidence: [E3], containment: disable rule, remediation: validate or remove, responsible_authority: EXAMPLE-AUTHORITY, status: CONTAINED, closure_evidence: NONE, closure_authority: NONE, closure_date: null}

divergent_opinions:
  <<: *escalated_d2
  decision_id: PO-DEC-EXAMPLE-2099-0006
  title: Divergent opinions candidate fixture
  reclassification_history:
    - {previous_classification: D1, new_classification: D2, date: 2099-01-01, reason: specialist divergence, triggering_finding_or_evidence: [EXAMPLE-F4], deciding_authority: EXAMPLE-AUTHORITY, original_record_identifier: PO-DEC-EXAMPLE-2099-0001, successor_or_current_record_identifier: PO-DEC-EXAMPLE-2099-0006, preserved_disposition_and_effect: REQUESTED/NONE}
  specialist_authority:
    domain_authority_required: true
    specialist_requirement: MANDATORY
    specialist_question: Is example claim valid?
    source_sufficiency: CONFLICTING
    source_sufficiency_evaluator: EXAMPLE-EVALUATOR
    evaluator_competence_evidence: [EXAMPLE-COMPETENCE]
    evaluator_authority_basis: EXAMPLE-BASIS
    blocked_scope: example.claim
    containment: suppress claim
    containment_release_status: BLOCKED
    containment_release_authority: NONE
    parent_opinion_status: OPEN_DIVERGENCE
    opinions:
      - {opinion_id: O1, specialist_identity_reference: S1, competence_evidence: [C1], authority_basis: B1, concrete_question: example question, conclusion: support, sources: [SRC1], scope: example.claim, territorial_limit: T1, temporal_status: CURRENT, normative_version: V1, responsibility_scope: advisory, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-01-01, review_due_at: 2099-06-01, warning_lead_time: P30D, expires_at: 2100-01-01, validity_condition: source applicable, status: SUPPORTING, evidence_reference: E1}
      - {opinion_id: O2, specialist_identity_reference: S2, competence_evidence: [C2], authority_basis: B2, concrete_question: example question, conclusion: oppose, sources: [SRC2], scope: example.claim, territorial_limit: T1, temporal_status: CURRENT, normative_version: V1, responsibility_scope: advisory, commercial_relationship: NONE, declared_conflicts: NONE, conflict_assessment: NONE, mitigation: NONE, issued_at: 2099-01-02, review_due_at: 2099-06-01, warning_lead_time: P30D, expires_at: 2100-01-01, validity_condition: source applicable, status: CONTRARY, evidence_reference: E2}
    resolution: null
```

### RC5 adversarial static cases

Every case below is fictional, candidate-only and independent unless it explicitly names a lineage link. Namespaces prevent accidental competing successors.

| Case | Static fixture/result |
|---|---|
| Duplicate front-matter key | Raw `title: A` followed by `title: B` in the same mapping is `INVALID_BEFORE_SEMANTIC_PARSE`; neither value survives. |
| Duplicate conditional module | Two sibling `specialist_authority:` keys are `INVALID_BEFORE_SEMANTIC_PARSE`; they are not merged. |
| Valid D1→D2 | `RC5-LINEAGE-VALID-A` has event `A-E1`, predecessor `A-D1`, successor/current `A-D2`, one current declaration and no cycle: `VALID_STRUCTURE`. |
| Competing heads | `RC5-LINEAGE-INVALID-HEADS` declares both `H-D2A` and `H-D2B` current: `INVALID`. |
| Lineage cycle | `RC5-LINEAGE-INVALID-CYCLE` links `C-R1→C-R2→C-R1`: `INVALID`. |
| Closed plus contained | `RC5-MIX-CC` contains one evidenced `CLOSED` and one compatibly evidenced `CONTAINED`: parent `RESOLVED_WITH_CONTAINMENT`. |
| Open component | `RC5-MIX-OPEN` contains one `CLOSED` and one `OPEN`: parent `UNRESOLVED`. |
| Rejected remediation | `RC5-MIX-REJECT` marks `REMEDIATION_REJECTED`; finding remains `UNRESOLVED` until separately closed, contained or removed. |
| Opinion revalidated | `RC5-OP-REVALIDATED` has immutable R1, successor R2, event `REVALIDATED`, R2 as sole current revision and R1 preserved as historical. |
| Opinion overwritten | `RC5-OP-INVALID-OVERWRITE` replaces R1 content without a successor revision/event: `INVALID`. |
| Mixed grouped outcomes | `RC5-GROUP-OUTCOMES` is an authority-free envelope whose I1 has its own `ACCEPTED` act and I2 its own `DEFERRED` act: `VALID_STRUCTURE`. |
| Grouped item escalation | `RC5-GROUP-ESCALATION` retains item I3 with integrity status `ITEM_ESCALATED` and link to `RC5-LINEAGE-ESC-D2`; the successor alone carries the D2 decision lifecycle. |
| Review overdue before expiry | At `review_due_at < now < expires_at`, with all validity conditions intact, the revision is `OVERDUE_FOR_REVIEW`; no lifecycle transition or unrelated effect occurs. |
| Expiry without revalidation | At `now >= expires_at` without a valid successor revision, the opinion is `EXPIRED`, cannot support release and proportionally contains only its affected scope. |

These cases are assertions of the candidate contract, not executable tests, substantive authority, acceptance or project decisions.

## 10. Identifiers, immutability and hashing readiness

- Decision: `PO-DEC-<PROJECT>-<YYYY>-<NNNN>`.
- Derivation: `PO-DERIVATION-<PROJECT>-<NNNN>`.
- Identifiers are state-independent and never reused.
- Material correction, reclassification through a successor, revocation or supersession preserves linkage.
- Promulgated content is materially immutable.
- Future hashing requires a separately approved canonicalization specification. Until then, no normative hash is asserted; Git identity alone is neither record hash nor legal signature.

## 11. Status

`ACCEPTED / IN_FORCE`.
