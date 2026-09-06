---
identity: PO-GOV-01
title: Product Owner Decision Governance Policy
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# PO-GOV-01 - Product Owner Decision Governance Policy

## 1. Purpose and scope

This policy defines a proportional and traceable governance standard for project-local Product Owner decisions. It applies prospectively to decisions created after an explicit project adoption of the promulgated `PO-GOV 1.0.0` package through the version-pinned derivation process.

It governs decision records, not ordinary engineering activity. It does not replace the ICFACTORY Constitution, Constitutional Lexicon, Methodological Custody or the Project Constitution.

## 2. Core principles

1. **One canonical record:** each decision has one project-local canonical record and stable identifier. Registries index; they do not duplicate deliberation.
2. **No presumed acceptance:** request, discussion, silence, time, code, commit, AI output or partial execution do not constitute acceptance.
3. **No automatic promulgation:** acceptance has no operational effect until an authorized promulgation records the content identity and effective date.
4. **Explicit provenance:** every authoritative transition identifies role, holder, source of competence, evidence and capacity exercised.
5. **Proportional governance:** D0-D3 controls scale with materiality.
6. **Historical preservation:** rejected, deferred, revoked, superseded, expired and legacy records remain traceable.
7. **Prospective operation:** the standard neither rewrites history nor implies retroactive compliance.
8. **Project custody:** concrete project decisions and their evidence remain in the project repository or its authorized evidence system.
9. **Framework boundary:** ICFACTORY stores the standard, not project decisions.
10. **Pinned derivation:** framework changes cannot silently update a project's adopted governance.
11. **Domain legitimacy:** implementation evidence does not, by itself, legitimize the implemented rule.
12. **Bounded specialist escalation:** specialist review is required only for a justified question, rule, claim or functionality and cannot create parallel authority.

## 3. Required separation of contributions and authority

A record must keep these layers distinguishable:

- `AI_PROPOSAL`: generated or transformed content with identified assistance and limitations;
- `HUMAN_DELIBERATION`: human-governed analysis of evidence, alternatives, risks and restrictions;
- `PRODUCT_OWNER_DECISION`: explicit manifestation by the competent project Product Owner;
- `PROMULGATION`: separate act placing accepted content into operational effect.

An AI proposal may be accepted, restricted or rejected. Its presence does not prove human agreement. Product Owner statements must be supported by manifestation evidence and must never be invented or paraphrased as authority without traceability.

## 4. Canonical record and traceability

Decision identifiers use `PO-DEC-<PROJECT>-<YYYY>-<NNNN>` and never change with lifecycle state. The canonical record links, as applicable:

```text
request -> deliberation -> authority manifestation -> acceptance
        -> promulgation -> implementation -> tests -> commits -> publication
```

Material correction, revocation or supersession requires a new decision/act and preserved predecessor linkage. Administrative corrections may repair typography, broken non-semantic links or registry metadata only when they do not alter request, reasoning, scope, authority, outcome, effect or evidence meaning; they must be logged and must not manufacture history.

Accepted but unpromulgated content may be explicitly `WITHDRAWN`; it has no operational effect to revoke. `REVOKED` and `SUPERSEDED` apply only after promulgation under the lifecycle rules.

## 5. Immutability

Before promulgation, a candidate record may evolve through Git history. After promulgation, its decision content is materially immutable:

- a material correction requires a successor record;
- revocation and supersession are explicit acts;
- the registry reflects current state without rewriting the original decision;
- the original promulgated file is not edited to simulate updated history;
- promulgated content must be hash-verifiable after a future canonicalization standard is approved.

Canonicalization is a prerequisite for future hashing. This policy does not define an executable canonicalizer or calculate hashes.

## 6. Storage and evidence

Projects maintain the structure defined in [`DERIVATION_STANDARD.md`](DERIVATION_STANDARD.md). Evidence may be local, externally controlled or confidential. References must be durable enough to audit the decision. Tests and commits should cite their authorizing decision where applicable; a commit is evidence or execution, not automatically a decision.

## 7. Legacy policy

Pre-standard decisions are classified `LEGACY_PRE_PO_GOV`. They may be inventoried and referenced but must not be rewritten to simulate compliance. `OG-001` remains historically valid under its original authority. Migration is prospective.

## 8. Non-engessamento safeguards

It is prohibited to:

- treat every commit as a decision;
- demand D2/D3 dossiers for D1;
- create PO-DEC records for routine D0 work under existing authority;
- duplicate the canonical record in the registry;
- block read-only audits;
- require repetitive manual registry work that future authorized automation can perform;
- use governance to create a Product Owner bottleneck;
- fragment D2/D3 matters into D0/D1 actions.

The standard requires immediate D0 execution when already authorized, lightweight D1 records, traceable grouping of similar D1 items, a provisional emergency path and versioned evolution. A grouped-D1 object is an administrative envelope only: it has no acceptance, disposition, promulgation or operational authority, while each item retains its own manifestation and lifecycle result.

Canonical records use the modular schema. Conditional modules are absent when not triggered. An ordinary D1 contains only the canonical core and D1 extension; it must not reproduce D2/D3 or specialist dossiers.

## 9. Domain correctness and specialist authority

[`DOMAIN_CORRECTNESS_AND_SPECIALIST_AUTHORITY.md`](DOMAIN_CORRECTNESS_AND_SPECIALIST_AUTHORITY.md) defines `COR-01`, `SA-01`, `SA-02` and guards `G01-G15`.

Before material remediation, the record distinguishes `IMPLEMENTATION_CORRECTION` from `DOMAIN_CORRECTION`. Specialist necessity is separately classified as `NOT_REQUIRED`, `RECOMMENDED`, `MANDATORY` or `OUT_OF_SCOPE`. D0-D3 does not automatically determine that state.

When both correction types exist, use `MIXED_CORRECTION` with separately traceable components and closure evidence.

Materiality reassessment uses append-only `reclassification_lineage`. Every reassessment creates a successor record and canonical event; it never overwrites predecessor substantive content. The event identifies both directions, the unique current record and the preserved former classification, reason, evidence, authority, disposition and effect. Competing heads, cycles, disconnected revisions and multiple current declarations fail closed. Downgrade cannot remove unresolved materiality, specialist or containment controls.

Raw front matter uses the restricted YAML profile. Anchors, aliases, merge keys, custom tags, implicit composition and duplicate keys/modules/collection identifiers are invalid before parsing; parsed-only input fails closed. Structural automation reports but never expands or chooses among prohibited constructs.

Reclassification and opinion event chains use contiguous positive `event_sequence` and immediate `previous_event_id`; dates are evidence only. Cross-lineage references, branches, gaps, rollback and competing heads fail closed.

Missing mandatory validation blocks only the affected scope. Specialist advice remains separate from professional responsibility, Product Owner decisions, Methodological Custody and acts reserved to external authority.

## 10. Status

`ACCEPTED / IN_FORCE`.
