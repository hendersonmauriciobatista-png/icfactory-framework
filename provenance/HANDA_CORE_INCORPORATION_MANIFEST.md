# HANDA_CORE Incorporation Manifest

GP: GP-FW-04B - Incorporacao Institucional do Nucleo Constitucional
Date: 2026-07-20
Destination repository: C:\Users\Guiuliano\icfactory-framework
Origin repository: C:\HANDA_CORE
Origin directory: C:\HANDA_CORE\ICFACTORY
Origin HEAD observed: 95f23628319a969e1d89c3a89466d8533fb09140
Destination HEAD before incorporation: 10e3f72417d491d295721277ba89b72fcae5c2b5

## Custodial Decision

The custodian explicitly approved GP-FW-04B Fase 2 and adopted the following institutional premises:

- The historical origin of a concept does not determine the permanent location of its institutional authority.
- H&A integrates the history of ICFACTORY, but does not constitute the definitive institutional repository of the framework.
- The icfactory-framework repository becomes the official autonomous methodological repository of ICFACTORY after this controlled incorporation is verified and committed.

## Relationship Between H&A And ICFACTORY

HANDA_CORE remains recognized as the historical origin and first development/application environment of ICFACTORY concepts. It is not deleted, rewritten, or treated as operational dependency of the autonomous framework after incorporation.

This incorporation applies only to documents and concepts institutionally belonging to ICFACTORY. H&A-specific runtime, project, or domain documents remain under H&A authority and were not incorporated.

## Source Categories

### Tracked And Clean Source Files

The following files were incorporated from tracked clean source state and preserve their source SHA-256 in `HANDA_CORE_INCORPORATION_INVENTORY.csv`:

- CONSTITUTION.md
- CONSTITUTIONAL_LEXICON.md
- LEXICON.md
- governance/GOVERNANCE_ARCHITECTURE.md
- governance/PROJECT_CONSTITUTION_TEMPLATE.md
- governance/PROJECT_CONSTITUTION_ALFA_DRAFT.md
- concepts/README.md
- concepts/ACI.md
- concepts/CIEX.md
- concepts/AUDIT_PLAYBOOK.md
- concepts/OSE.md
- concepts/ALO.md

### Source Files From Modified Working Tree

The following files were incorporated from the origin working tree while the source repository reported local modifications:

- HISTORY.md
- ROADMAP.md

These files are not represented as belonging to origin HEAD. Their source commit column records the last commit touching the file, while their SHA-256 records the exact incorporated working-tree content observed during GP-FW-04B.

### Source Files From Unversioned Working Tree

The following files had no origin commit at incorporation time and were ratified by GP-FW-04B as documents eligible for incorporation:

- DOCUMENT_MAP.md
- GETTING_STARTED.md
- research/DISCOVERY_LIFECYCLE.md
- research/architecture/ARCHITECTURAL_DISCOVERIES.md
- research/methodology/METHODOLOGICAL_DISCOVERIES.md

Their SHA-256 values record the exact source content observed before incorporation. They must not be represented as if they belonged to origin HEAD.

### Adapted During Incorporation

Only navigation/onboarding path references were adapted:

- DOCUMENT_MAP.md
- GETTING_STARTED.md

The adaptation removed obsolete `ICFACTORY/` path prefixes where the autonomous repository root now contains the ICFACTORY core. No constitutional, lexical, conceptual, historical, roadmap, governance, or research content was rewritten for merit.

### Not Incorporated

The following observed source artifact was not incorporated in Fase 2 main incorporation:

- adoption_tests/ICFACTORY_AI_ADOPTION_TEST.md

Reason: adoption test evidence is historical/supporting material, not part of the constitutional core, conceptual core, governance core, or Research layer required for autonomy.

## Non-Retroactivity Declaration

This incorporation does not fabricate retroactive authority. It does not assign old commits to the destination repository, does not rewrite historical dates, does not erase H&A as origin, and does not claim that untracked origin files were present in origin HEAD.

## Baseline Boundary

This incorporation does not approve Baseline v1.0 and does not declare the First Scientific Cycle closed. GP-FW-04 remains historically recorded as not approving the governance baseline freeze.

## Phase 3 Verification Notes

- Phase 3 normalization verification (2026-08-09): controlled, in-memory normalization (UTF-8, remove BOM, Unicode NFC, LF endings) executed for incorporated artifacts and used as evidence for provenance reconciliation.

- governance/PROJECT_CONSTITUTION_ALFA_DRAFT.md: raw-hash mismatch identified earlier was a FALSE_POSITIVE caused by line-ending normalization. Recorded as: NORMALIZED_CONTENT_EQUIVALENT; CONTENT_CORRECTION_NOT_REQUIRED; DRAFT status preserved. No authority promoted.

- governance/PROJECT_CONSTITUTION_TEMPLATE.md: current HEAD content matches authoritative HANDA_CORE source after controlled normalization (A↔C normalized match). The incorporation commit blob (38152f16091dedae70d739a2911c88e140e742b0) contains a different payload (historical incorporation blob mismatch) which is preserved as historical evidence. Provenance correction performed in inventory to align recorded source_sha256 with authoritative source; CURRENT_CONTENT_CORRECTION_NOT_REQUIRED. Historical commit preserved and not rewritten.

- CONSTITUTION.md: inventory source_sha256 corrected to match the verified authoritative HANDA_CORE source; CURRENT_CONTENT_MATCHES_AUTHORIZED_SOURCE recorded.

These provenance edits preserve all prior historical facts, do not rewrite commits, and explicitly document detected mismatches and normalization findings for Product Owner review and ratification.

## Product Owner Deliberation — GP-FW-04B Phase 3

Authority: PRODUCT_OWNER
Decision: APPROVED_WITH_RECORDED_RESERVATIONS
Date: 2026-08-09

Deliberation summary:
- README duplicate paths: ACCEPTED_AS_NON_BLOCKING. No content conflict; non-blocking reservation recorded.
- governance/PROJECT_CONSTITUTION_TEMPLATE.md historical incorporation blob mismatch: ACCEPTED_AS_NON_BLOCKING_HISTORICAL_EVIDENCE. Historical divergence preserved in provenance; no rewrite authorized.

Decision rules:
- Preserve reservations as auditable historical evidence.
- Do not rewrite Git history, modify constitutional content, modify governance templates, remove historical evidence, or perform unrelated corrections.
- Do not push these local provenance records without explicit authorization.

Baseline verification:
- Baseline verified: YES
- Worktree before writing: CLEAN

Action taken:
- Product Owner deliberation recorded in this manifest as the authoritative GP-FW-04B deliberation record. Only the minimum documentary record was modified.

Commit instruction (local):
Commit message: docs: ratify GP-FW-04B phase 3 with recorded reservations
Push: NOT AUTHORIZED

Note: This entry records Product Owner approval with recorded reservations. No constitutional or governance-template content was modified.

