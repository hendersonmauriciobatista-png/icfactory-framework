---
identity: PO-GOV-02
title: Permanent Project Structure and Versioned Derivation
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# PO-GOV-02 - Permanent Project Structure and Versioned Derivation

## 1. Boundary

ICFACTORY stores the PO-GOV standard. Each project stores its own Product Owner authority, registry, concrete decisions and evidence. Framework publication cannot mutate project governance.

This release candidate is prohibited from project derivation until a future version is explicitly promulgated.

## 2. Mandatory project-local structure

```text
docs/governance/product_owner_decisions/
├── README.md
├── DERIVATION_MANIFEST.md
├── registry/
│   └── PO_DECISION_REGISTRY.md
├── records/
├── templates/
└── evidence/
```

The registry is an index, not a second canonical record. Evidence may be referenced outside Git when privacy, legal or security controls require it.

For grouped D1, a future derived registry/index must resolve `(project_scope_id, item_id)` uniqueness, ensure one active group membership, validate successor existence in the same project scope and verify reciprocal group/item lineage references. It indexes canonical envelopes/records only, creates no authority and may not infer materiality or specialist necessity.

## 3. Version-pinned adoption

Every adoption requires an explicit project Product Owner decision and a `DERIVATION_MANIFEST` containing:

- framework repository, complete standard identity `PO-GOV`, version and exact source commit;
- derivation component identity `PO-GOV-02`, without representing that component as the whole standard;
- adoption decision and authority evidence;
- derived source/local paths and hashes;
- local extensions and deviations;
- compatibility status and effective date;
- predecessor/supersession and review information.

No floating branch, `latest`, implicit upgrade or mutable external reference is a valid derivation pin.

Adoption of `PO-GOV` includes every applicable package policy, lifecycle rule, schema contract, COR-01, SA-01, SA-02 and guard G01-G15 at the pinned version. A project cannot claim package adoption while deriving only PO-GOV-02.

## 4. Compatibility

Allowed statuses:

- `EXACT`: semantics match the pinned framework source.
- `EXTENDED`: local requirements tighten or add controls without removing mandatory semantics.
- `DEVIATING`: a declared incompatibility exists and must be evaluated/authorized.

Local extensions cannot remove human authority, lifecycle integrity, proportionality, preservation, non-retroactivity or the framework/project boundary.
They also cannot remove COR-01 classification, justified SA-01 states, bounded mandatory-validation blocks, responsibility separation or guards G01-G15 when applicable.

Derived schemas preserve modular triggers, restricted YAML, monotonic event chains, structured containment assessments and project-wide grouped-item uniqueness checks. They may not reintroduce flat burden, mutable opinion revisions or weaken lineage, authority-free grouping or terminal modules.

## 5. Upgrade

Framework changes produce no local effect until the project:

1. audits differences and compatibility;
2. identifies migrations and risks;
3. obtains explicit Product Owner authorization;
4. creates a new derivation manifest;
5. preserves the prior manifest and local records;
6. validates hashes, templates and registry behavior;
7. promulgates the new local adoption with an effective date.

## 6. Project permanence and legacy

Project decisions remain valid or invalid according to their own authority and lifecycle, not according to later framework commits. Pre-standard records remain `LEGACY_PRE_PO_GOV` and are not rewritten. A project may inventory them with references and limitations.

## 7. Privacy and evidence

Sensitive evidence is not copied automatically into public repositories. Store a controlled reference, classification and hash where appropriate. Access controls, retention and lawful handling remain project responsibilities.

Specialist competence, commercial relationships and cost evidence may use controlled references. A derivation must not embed sensitive financial evidence merely to demonstrate SA-02 transparency and must not create a project procurement or payment system.

## 8. Status

`ACCEPTED / IN_FORCE`.
