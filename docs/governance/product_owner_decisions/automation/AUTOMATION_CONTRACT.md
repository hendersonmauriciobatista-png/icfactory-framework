---
document_id: PO-GOV-AUTOMATION-CONTRACT
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# Product Owner Decision Governance — Automation Contract

> This human-readable contract is **ACCEPTED** and **IN_FORCE**. It defines no executable automation, hook, workflow, parser, CI gate, or runtime behavior.

## Purpose

Describe the boundary for any separately authorized future automation that supports Product Owner governance records without manufacturing authority or changing normative meaning.

## Allowed assistance

Subject to separate authorization and an in-force source standard, automation may:

- allocate identifiers and create the template corresponding to a human-selected or validly classified materiality class;
- validate structure, required fields, transitions, references, links, hashes, and lifecycle-field consistency;
- synchronize the registry without duplicating the canonical record;
- detect broken links, missing evidence references, duplicate identifiers, prohibited state combinations, and version drift;
- suggest materiality with reasons, while preserving human final classification and upward escalation for ambiguity;
- check promulgated-record immutability and report hash divergence;
- generate traceability reports and prepare comparisons, inventories, and validation reports for human review;
- preserve provenance showing machine actions, inputs, outputs, versions, and timestamps;
- stop and report when authority, evidence, classification, or source version is absent or ambiguous;
- validate declared schema modules, known states, expiry/review dates and presence of mandatory evidence;
- enforce a declared `blocked_scope` without expanding the block to unrelated scope;
- report open divergence, expired evidence and missing non-extrapolation limits for human resolution;
- validate the deterministic state/field matrix and reject prohibited combinations;
- detect missing required conflict declarations, declared conflict states, inconsistent structured fields, declared `UNDETERMINED` and invalid temporal states;
- warn that independent human review is required when a declared conflict, divergence or missing declaration exists;
- validate mixed-component cardinality/status aggregation, individual-opinion fields, reclassification linkage and grouped-D1 item structure;
- inspect trustworthy raw source and reject anchors, aliases, merge keys, custom tags, implicit composition and duplicate keys/modules/collection IDs without expanding them;
- validate contiguous monotonic reclassification/opinion event chains, same-lineage references, unique terminal heads and structured multi-revision effects;
- evaluate mixed corrections only from declared structured containment assessments and protection dispositions;
- validate declared grouped-item materiality/specialist eligibility and, through a future derived index, project-wide item uniqueness, active-group membership and reciprocal escalation links;
- report `OVERDUE_FOR_REVIEW` from declared dates without creating a lifecycle transition or expiry;
- mark the affected scope as structurally blocked when a declared fail-safe condition applies, without releasing containment.

## Prohibited behavior

Automation must not:

- accept, approve, promulgate, sign, adopt, reject, or place a decision in force;
- infer assent from silence, inactivity, repository state, publication, merge, deployment, or elapsed time;
- impersonate a Product Owner, custodian, specialist, approver, or human participant;
- invent or fabricate a request, rationale, human statement, authority evidence, deliberation, signature, specialist review, or human provenance;
- rewrite an original request;
- deliberate, accept, reject, promulgate, or convert AI output directly into a governing decision;
- choose materiality where judgment is unresolved, downgrade materiality, or downgrade D2/D3 controls;
- alter immutable records, delete terminal records, reinterpret legacy decisions, or silently repair normative content;
- upgrade a project's adopted framework version;
- derive project governance from an unpromulgated candidate;
- execute implementation, deployment, rollback, notification, or external effects merely because a record exists;
- infer specialist competence, credential applicability or professional responsibility;
- declare an official source sufficient or an opinion authoritative;
- select a specialist, approve contracting or cost, or rank competence by payment, title or reputation;
- resolve specialist divergence or extrapolate an opinion beyond declared limits;
- determine source-sufficiency evaluator competence, conflict materiality, mitigation adequacy or continuing temporal validity;
- discover or infer undisclosed relationships or declare an opinion independent;
- search external data for substantive conflict, competence or sufficiency judgment under this contract;
- decide reclassification, component closure, opinion aggregation sufficiency or resolver competence;
- expand or choose among anchors, aliases, merges, custom tags or implicit composition; choose a surviving duplicate; or rely on parser-specific normalization;
- decide substantive equivalence between opinion revisions, justification for reclassification, or whether an overdue review remains substantively sufficient;
- authorize renewal, revalidation, containment release or a lifecycle transition;
- activate, publish or process content declared `OUT_OF_SCOPE`;
- accept, promulgate or derive this candidate.

## Fail-safe behavior

When status, class, schema, authority, provenance, materiality, acceptance, promulgation, version pinning, or evidence is missing, inconsistent, unknown, or unverifiable, automation must fail closed: make no authoritative transition, preserve existing state, identify the exact uncertainty, and request meaningful human resolution.

Unknown state, class, schema, or identifier must be rejected. Ambiguous materiality must escalate. Missing authority must block acceptance and promulgation. Missing D2/D3 evidence must block promulgation. A changed promulgated hash must be reported as a violation and never repaired by rewriting the record. Technical validation success is not normative acceptance and must be reported separately.

Unknown, duplicated, malformed or incompatible modules and every prohibited restricted-YAML construct are rejected from trustworthy raw source before semantic interpretation. Parsed-only input fails closed. Unknown correction types or SA-01 states also fail. Missing `MANDATORY` evidence blocks only affected scope. Material ambiguity produces a finding; automation cannot manufacture compatibility, sufficiency, competence or responsibility.

Fail closed on: unresolved authority; invalid lifecycle combinations; open conflict/divergence; `UNDETERMINED`, asymmetric or conflicting containment assessments; incomplete protection dispositions; non-contiguous/branched/cyclic/cross-lineage event chains; competing terminal heads; invalid opinion chronology/effects; more than one current usable opinion revision; duplicate grouped membership; ineligible grouped materiality/specialist state; unresolved escalation; or a group envelope carrying authority.

An undisclosed conflict discovered through authorized human or external evidence enters the record as `UNDISCLOSED_MATERIAL_DISCOVERED`; automation handles only that declared state. It never claims to have discovered the relationship.

Structural validation reports conformance only to declared syntax and deterministic combinations. It is never substantive approval, acceptance, promulgation, competence verification, source sufficiency or authority evidence.

## Human control and auditability

Every machine contribution must remain distinguishable from human judgment. A human with the required capacity must review the relevant evidence and manifest the decision explicitly. Logs and generated reports are supporting evidence only; they do not replace the canonical human-attributable record.
