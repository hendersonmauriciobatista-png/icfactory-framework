# HANDA_CORE Document Classification

GP: GP-FW-04B - Incorporacao Institucional do Nucleo Constitucional
Date: 2026-07-20

## Classification Rules

A. Pertence integralmente ao ICFACTORY
B. Pertence integralmente ao H&A
C. Documento hibrido que exige separacao
D. Evidencia historica apenas
E. Documento obsoleto ou superado
F. Documento conflitante
G. Documento pendente de decisao custodial

## Result

The complete row-level classification is recorded in `provenance/HANDA_CORE_INCORPORATION_INVENTORY.csv`.

Summary:

- A: Constitution, Constitutional Lexicon, general Lexicon, Governance Architecture, Project Constitution Template, concept documents, and concepts README.
- D: Project Constitution ALFA Draft as example/draft; adoption test as historical evidence only.
- G: HISTORY.md and ROADMAP.md because source had local uncommitted modifications; DOCUMENT_MAP.md, GETTING_STARTED.md, Discovery Lifecycle, and Research inventories because source had no commit.

## H&A-Only Exclusions

H&A runtime, trading components, operational code, project-specific state, and root H&A governance files outside `ICFACTORY/` were not incorporated. They remain under H&A authority.

## Hybrid Treatment

Research inventories mention Sistema de Analise de Agua as project of origin. They were incorporated because the documents define ICFACTORY Research hypotheses, not because the water-analysis project itself is part of the framework. The project-origin references were preserved as provenance.
