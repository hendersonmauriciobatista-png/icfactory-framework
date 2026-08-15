---
document_id: PO-GOV-DERIVATION-MANIFEST-TEMPLATE
version: 1.0.0
status: ACCEPTED
effect: IN_FORCE
---

# Product Owner Governance Derivation Manifest Template

> **ACCEPTED — IN_FORCE.** This is a candidate example only. Derivation from this package is prohibited until the source standard is explicitly accepted and promulgated. Copying or completing this template is not adoption evidence.

Any future instance must use the restricted YAML profile and trustworthy raw pre-semantic validation. Anchors, aliases, merge keys, custom tags, implicit composition and duplicate keys/modules/collection IDs are invalid and never expanded; parsed-only input fails closed.

```yaml
manifest_id: ""
project_id: ""
framework_repository: ""
framework_standard: "PO-GOV"
framework_component: "PO-GOV-02"
framework_version: ""
framework_source_commit: ""
adoption_decision_id: ""
adopted_at: ""
adopted_by: ""
authority_evidence: ""
derived_files: []
source_sha256: ""
local_sha256: ""
local_extensions: []
local_deviations: []
compatibility_status: ""
previous_manifest: ""
supersedes: ""
effective_from: ""
review_due: ""
status: ""
```

Each derived file must remain attributable to the pinned framework repository, version, and source commit. Hashes describe artifacts; they do not prove authority. Local extensions and deviations must be explicit and may not silently redefine the source standard.

`framework_standard` identifies the complete adopted PO-GOV package; `framework_component` identifies PO-GOV-02 as its derivation component. Adoption covers all applicable policies, schema, lifecycle, COR-01, SA-01, SA-02 and guards G01-G15 at the pinned version.

For a future promulgated version, compatibility assessment must identify deviations affecting restricted YAML, monotonic events, structured containment, event-sourced opinions, project-wide grouped-item uniqueness, modular triggers, reclassification and terminal effects. This candidate template remains prohibited from project instantiation or derivation.
