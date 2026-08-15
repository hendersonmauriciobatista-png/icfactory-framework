---
identity: HP-01
title: Human Participation and Provenance
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# HP-01 - Human Participation and Provenance

## 1. Purpose

HP-01 defines evidence sufficient to distinguish AI assistance, human formulation, human deliberation and competent authority. It references the ICFACTORY definitions of authority, evidence and provenance without replacing them.

## 2. Meaningful human participation

A defensible record demonstrates, proportionate to materiality:

1. the original human request or an integrity-preserving reference;
2. the human problem formulation and intended outcome;
3. identified AI/agent/tool assistance;
4. human review of material evidence, alternatives and risks;
5. accepted, restricted and rejected AI proposals;
6. explicit Product Owner manifestation and capacity;
7. human validation/acceptance criteria and responsibility for the resulting decision;
8. traceable implementation and verification where applicable.

Mechanical clicks, silence, unreviewed generation or a Git identity alone do not demonstrate meaningful deliberation or authority.

## 3. Original request preservation

The original request must be preserved verbatim in the canonical record or referenced with identity, location, date and integrity evidence. A summary may accompany it but cannot replace or rewrite it. Confidential requests may use a controlled reference and hash when appropriate.

## 4. AI contribution record

Record:

- system/agent/tool identity when available;
- task and authorized context;
- generated proposals or transformations materially considered;
- factual sources introduced;
- known uncertainty or limitation;
- disposition of each material proposal: `ACCEPTED`, `RESTRICTED` or `REJECTED`;
- human reason for that disposition.

AI cannot attribute a statement to the Product Owner without manifestation evidence and cannot convert its proposal into a governing decision.

## 5. Product Owner manifestation

Evidence must identify the human, role, provenance of competence, decision ID/content, expressed outcome, restrictions and date. The record must distinguish the Product Owner role from Methodological Custody when the same person holds both.

## 6. Responsibility attribution

- AI/agent: assistance and generated content, without authority.
- Deliberating humans/reviewers: analyses and recommendations they actually made.
- Product Owner: project decision within proven scope.
- Methodological Custody: framework normative decision within custodial scope.
- Implementers/testers: execution and evidence, not inferred decision authority.
- Specialists: bounded opinion or validation within evidenced competence and declared scope, without inferred Product Owner, custodial or professional responsibility.
- External authorities: reserved determinations within their applicable legal, regulatory or institutional competence.

Consultation does not imply transfer or assumption of technical or professional responsibility. Record what the specialist actually reviewed, stated, limited and assumed; attribute no broader responsibility. Product Owner manifestation cannot replace an externally reserved act.

## 7. Limits of HP-01 evidence

Compliance does not prove:

- that AI participation was small;
- that no similar system can be built;
- legal authorship or ownership;
- copyright eligibility;
- correctness, novelty or regulatory conformity;
- that a Git identity is a legal signature.

Legal authorship, signature or ownership requires the competent external framework and evidence applicable to the case.

## 8. Defensible institutional statement

When supported by the record, a project may state:

> Development assisted by AI under traceable human formulation, deliberation, authority, validation and responsibility.

No stronger claim follows automatically.

Where SA-01 applies, human provenance also identifies who classified specialist necessity, who selected or referred the specialist, competence evidence reviewed, conflicts/economic relationships, material divergences and who accepted containment or `OUT_OF_SCOPE`. Automation cannot invent or infer those facts.

When official-source sufficiency supports `NOT_REQUIRED`, provenance identifies the evaluator, relevant competence evidence, authority basis and human rationale. When a material conflict is mitigated or containment is released, provenance identifies the human authority, evidence reviewed and exact bounded result. A customer, payer or employer relationship is disclosed but does not decide competence by itself.

Every materiality reassessment records the deciding human authority in an append-only lineage event, creates a successor record and preserves prior classification/disposition/effect without rewriting the predecessor. Every conflict/divergence resolution records resolver identity, relevant competence, authority basis, method, evidence, limitations and result. Product Owner role alone is not evidence of technical resolution competence.

Specialist opinion provenance is revisioned and event-sourced. Immutable revisions contain original content/validity; contiguous append-only events derive current and temporal state. Revalidation/replacement creates a successor and structured effects for predecessor and successor; withdrawal, supersession and expiry preserve evidence. Material changes require a non-empty human reason and evidence. Exactly one usable current revision exists per lineage.

## 9. Status

`ACCEPTED / IN_FORCE`.
