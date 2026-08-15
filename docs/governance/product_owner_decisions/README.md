---
package: PO-GOV
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# Product Owner Decision Governance

This directory contains the accepted and promulgated normative package for Product Owner decision governance in ICFACTORY. It is the in-force `1.0.0` package, accepted under Product Owner authority after the successful final review of RC7 and the correction of `AR-RC6-001`.

## Authority and precedence

The package is subordinate, in order, to:

1. [`../../../CONSTITUTION.md`](../../../CONSTITUTION.md);
2. [`../../../CONSTITUTIONAL_LEXICON.md`](../../../CONSTITUTIONAL_LEXICON.md);
3. Methodological Custody and `CM-001`, as recorded in [`../METHODOLOGICAL_CUSTODIAN_REGISTER.md`](../METHODOLOGICAL_CUSTODIAN_REGISTER.md);
4. [`../../../governance/GOVERNANCE_ARCHITECTURE.md`](../../../governance/GOVERNANCE_ARCHITECTURE.md).

This package specializes those authorities for Product Owner decisions. It does not redefine constitutional authority, approval, materiality, provenance, validity, entry into force, revocation or substitution.

## Authority boundary

- Framework normative change belongs to Methodological Custody.
- Project-local product decisions belong to the Product Owner designated by the applicable Project Constitution.
- A person holding both roles must identify the capacity exercised in every act.
- Product Owner authority alone cannot modify ICFACTORY.
- Framework publication cannot silently modify project governance.
- AI, agents, audits and automation may inform or prepare work but hold no transition authority.

## Package map

- [`CANDIDATE_MANIFEST.md`](CANDIDATE_MANIFEST.md): candidate identity and non-effect.
- [`POLICY.md`](POLICY.md): `PO-GOV-01` policy.
- [`SCHEMA.md`](SCHEMA.md): modular contract, restricted YAML, monotonic lineages, event-sourced opinions, structured containment, authority-free grouping and complete candidate fixtures.
- [`LIFECYCLE.md`](LIFECYCLE.md): states and transitions.
- [`MATERIALITY_CLASSIFICATION.md`](MATERIALITY_CLASSIFICATION.md): D0-D3 proportionality.
- [`HUMAN_PARTICIPATION_PROVENANCE.md`](HUMAN_PARTICIPATION_PROVENANCE.md): `HP-01`.
- [`DERIVATION_STANDARD.md`](DERIVATION_STANDARD.md): `PO-GOV-02`.
- [`DOMAIN_CORRECTNESS_AND_SPECIALIST_AUTHORITY.md`](DOMAIN_CORRECTNESS_AND_SPECIALIST_AUTHORITY.md): `COR-01`, `SA-01`, `SA-02` and guards `G01-G15`.
- [`templates/`](templates/): proportional D1-D3 and derivation templates.
- [`automation/AUTOMATION_CONTRACT.md`](automation/AUTOMATION_CONTRACT.md): non-executable future automation boundary.

## Candidate restriction

Projects must not derive or claim adoption of this release candidate. No concrete project decision belongs in the framework repository. Future acceptance and promulgation require separate explicit Methodological Custody acts.
