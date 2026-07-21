# Incorporation Conflict Report

GP: GP-FW-04B - Incorporacao Institucional do Nucleo Constitucional
Date: 2026-07-20

## Direct Filename Collisions

No direct collisions were found for the incorporated root constitutional files because the destination repository did not previously contain:

- CONSTITUTION.md
- CONSTITUTIONAL_LEXICON.md
- LEXICON.md
- HISTORY.md
- ROADMAP.md
- DOCUMENT_MAP.md
- GETTING_STARTED.md
- concepts/
- governance/
- provenance/

## README Collision Deferred

The destination repository contains a tracked `README.md` placeholder. GP-FW-04B did not replace or update it by custodial condition. README update remains a separate future action.

## Historical Reference Collisions

Existing reports and gates in `docs/governance` and `docs/audits` refer to `C:\HANDA_CORE\ICFACTORY` as the then-current authority. These references were preserved because they are historical evidence. They are not silently rewritten.

## Material Conflicts

No material constitutional conflict was identified between the incorporated constitutional core and the scientific/custodial governance documents.

The material risk was reproducibility: several custodial and governance documents existed only in the destination working tree before GP-FW-04B. They must be included in the same institutional commit to make the new authority reconstructible.

## Working Tree Caveats

- HISTORY.md and ROADMAP.md were incorporated from modified source working tree and are explicitly marked as such.
- Research lifecycle and inventories were incorporated from unversioned source working tree and ratified by this GP as Research-layer documents.
