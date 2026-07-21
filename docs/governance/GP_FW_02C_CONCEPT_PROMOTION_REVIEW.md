# GP-FW-02C — Processo de Promoção Constitucional dos Conceitos com Uso Operacional Comprovado

Status: **CONCLUÍDA — RECOMENDAÇÕES DOCUMENTAIS EMITIDAS; NENHUMA PROMOÇÃO EXECUTADA**

Data: 2026-07-20 (America/Sao_Paulo)

## 1. Veredito executivo

A revisão avaliou individualmente os 17 conceitos do escopo mínimo. O resultado é:

| Decisão | Quantidade | Conceitos |
|---|---:|---|
| A — Permanecer Experimental | 14 | DM-01; DA-01; DA-02; H1; H2; H3; H4; Critério de Avaliação; Separação Epistêmica; Revisão Explícita; Preservação Histórica; Harness como Executor Assistido; Especificação Estruturada de Execução; Contexto de Execução |
| B — Promover para Validado | 3 | PA-02; PA-03; GDC-R |
| C — Recomendar Promoção Constitucional | 0 | Nenhum |

As três decisões B reconhecem **validação operacional no corpus PROTEUS/ICFACTORY analisado**, não validade universal. Não alteram o estado dos documentos de origem e não promovem automaticamente qualquer conceito. A promoção efetiva exige GP posterior, ratificação humana e atualização controlada dos registros de autoridade.

Nenhum conceito atende integralmente aos requisitos cumulativos de C. Em particular, não foi localizado catálogo ou definição formal de “Organização de Governança (OG)” que permita comprovar uso em múltiplas OGs como entidades. As famílias explícitas de programas governados — GP, OEG e PAC — são informadas como contexto, mas não foram convertidas por inferência em OGs.

## 2. Autoridade, método e regras de evidência

A autoridade documental adotada é `C:\HANDA_CORE\ICFACTORY`, conforme GP-FW-02. Foram usados como corpus complementar os documentos do PROTEUS em `C:\Users\Guiuliano\SistemaAnaliseAgua`, porque ali estão as execuções, auditorias e pesquisas que originaram ou empregaram os conceitos. A GP-FW-02B, seus registros e sua matriz em `C:\Users\Guiuliano\icfactory-framework\docs\audits` foram usados como índice de proveniência, e cada decisão foi reconferida contra os documentos-fonte indicados na matriz.

Procedimento aplicado:

1. busca exata do identificador ou expressão canônica;
2. reconstrução da primeira ocorrência documental identificável;
3. contagem de arquivos distintos, sem multiplicar ocorrências no mesmo arquivo;
4. contagem de auditorias somente quando o artefato ou histórico identifica uma auditoria dependente;
5. separação entre menção, aplicação operacional e validação formal;
6. leitura do estado declarado pelo próprio documento (`CANDIDATA`, hipótese, consolidado internamente, validado etc.);
7. comparação com os critérios A/B/C definidos nesta GP.

Os totais de documentos representam o corpus local inspecionado em 2026-07-20. Para H1–H4, a contagem inclui o documento de consolidação e as fontes explicitamente atribuídas por ele. Para GDC-R, `40` é a contagem de arquivos com o identificador; `12` deles registram explicitamente a cadeia completa. Para “Preservação Histórica”, a busca ampla encontrou 21 arquivos, mas esse número não prova que todos implementem o conceito PM-08; essa limitação foi decisiva para A.

### Escala decisória

- **A — Permanecer Experimental:** evidência insuficiente para validação formal ou critérios declarados ainda não atendidos.
- **B — Promover para Validado:** uso operacional consistente e dependência observável no escopo estudado, sem consolidação constitucional.
- **C — Recomendar Promoção Constitucional:** uso estrutural recorrente, dependência metodológica, estabilidade documental, múltiplas auditorias, múltiplas OGs formalmente comprovadas e ausência de conflito conhecido.

## 3. Revisão individual

### 3.1 DM-01 — Identificação do Núcleo do Negócio

- **Origem / primeira ocorrência:** Sistema de Análise de Água; GP-R02/Research, registrada localmente pela GP-R01 em 27/06/2026.
- **Extensão:** 5 documentos; 0 auditorias independentes identificadas; 0 OGs formalmente registradas (família GP-R01 e aplicação CASE-01).
- **Influência:** orientação da arquitetura pelo núcleo do negócio; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** utilizada pontualmente para explicar a evolução arquitetural do CASE-01.
- **Evidência:** `METHODOLOGICAL_DISCOVERIES.md`, especialmente a declaração `CANDIDATA`, a origem no Sistema de Análise de Água e os critérios que exigem projetos distintos; `DISCOVERY_LIFECYCLE.md`, `DOCUMENT_MAP.md`, `HISTORY.md` e `ROADMAP.md` preservam o registro.
- **Decisão:** **A — Permanecer Experimental.** O próprio registro exige validação em projetos distintos e somente um projeto é documentado.

### 3.2 DA-01 — Especialização por Contexto Operacional

- **Origem / primeira ocorrência:** CASE-01 — Sistema de Análise de Água; registro local de 27/06/2026.
- **Extensão:** 5 documentos; 0 auditorias independentes identificadas; 0 OGs formalmente registradas (família GP-R01/CASE-01).
- **Influência:** reuso de arquitetura por contexto; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** evidência arquitetural apenas no projeto de origem.
- **Evidência:** `ARCHITECTURAL_DISCOVERIES.md` mantém `CANDIDATA`, assinala somente o Sistema de Análise de Água e deixa os demais projetos de verificação pendentes.
- **Decisão:** **A — Permanecer Experimental.** Não há segunda aplicação nem auditoria independente documentada.

### 3.3 DA-02 — Auditoria de Integração Arquitetural

- **Origem / primeira ocorrência:** Sistema de Análise de Água; GP-A14 AI-01, 27/06/2026.
- **Extensão:** 7 documentos; 8 auditorias de integração AI-01…AI-08; 0 OGs formalmente registradas (uma família GP-A14).
- **Influência:** coerência de dependências e integração entre camadas; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** aplicada a oito componentes do mesmo projeto.
- **Evidência:** `PROTEUS/HISTORY.md` registra as oito execuções; `ARCHITECTURAL_DISCOVERIES.md` mantém DA-02 `CANDIDATA` e exige evidência em projetos distintos.
- **Decisão:** **A — Permanecer Experimental.** O número de componentes não substitui diversidade de projetos, requisito explícito da própria Discovery.

### 3.4 PA-02 — Progressão de Valor

- **Origem / primeira ocorrência:** GP-R02 — Value Progression Audit; commit `95ded850`, 28/06/2026.
- **Extensão:** 32 documentos; 22 artefatos de auditoria identificados; 0 OGs formalmente registradas. Uso distribuído em seis famílias governadas: GP-R, GP-D, GP-AC/PE, OP, PAC e OEG-PA.
- **Influência:** princípio prático de enriquecer camadas existentes antes de criar novas; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** fundamenta decisões de domínio, arquitetura, operação, PAC e OEG, inclusive decisões de não materialização.
- **Evidência:** `DISCOVERY_CATALOG.md` linhas 63–81 registra origem, hipótese, CASE-01, GP-R02 e evolução GP-A14–GP-A25; GP-D07A/GP-D08A e AC-01 empregam PA-02 como fundamento decisório; a busca documental encontra o identificador em 32 arquivos.
- **Decisão:** **B — Promover para Validado.** Há recorrência operacional, múltiplas auditorias e dependência decisória consistente no corpus. O alcance da validação deve ser declarado como interno ao PROTEUS/CASE-01; falta aplicação externa e consolidação constitucional para C.

### 3.5 PA-03 — Materialização sob Necessidade

- **Origem / primeira ocorrência:** GP-D01A/GP-D01B/GP-D01C; GP-D01A, commit `e9f4dbeb`, 30/06/2026.
- **Extensão:** 32 documentos; 22 artefatos de auditoria identificados; 0 OGs formalmente registradas. Uso em seis famílias governadas: GP-D, GP-R, GP-AC/PE, OP, PAC e OEG-PA.
- **Influência:** materializar somente diante de necessidade operacional objetiva; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** usada para impedir criação prematura de entidades, persistência, workflows e camadas.
- **Evidência:** `DISCOVERY_CATALOG.md` linhas 85–112 registra origem, hipótese e estado `CANDIDATA`; GP-D07A/GP-D08A, AC-01, PE-06, OP-00…OP-03, PAC e OEG registram aplicação; o identificador aparece em 32 arquivos.
- **Decisão:** **B — Promover para Validado.** O uso é recorrente e verificável em decisões heterogêneas do mesmo ecossistema. A promoção deve preservar o limite CASE-01/PROTEUS; falta validação externa e consolidação constitucional para C.

### 3.6 H1 — Auditoria antes da Materialização

- **Origem / primeira ocorrência:** observações GP-D07A, GP-D08B e GP-D09A; consolidação AI-01 em 02/07/2026.
- **Extensão:** 4 documentos (consolidação + 3 fontes); 3 auditorias; 0 OGs formais (família GP-D).
- **Influência:** auditoria documental antes de entidade, persistência, workflow ou camada; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** padrão recorrente nas auditorias de domínio.
- **Evidência:** `AI_METHODOLOGICAL_OBSERVATIONS_CONSOLIDATION.md` linhas 62–80, 181–200 e 258–314 declara hipótese em monitoramento, não promovida e dependente de validação humana/independente.
- **Decisão:** **A — Permanecer Experimental.** A fonte canônica proíbe tratar a recorrência como promoção e exige validação ainda inexistente.

### 3.7 H2 — Memória Permanente versus Operação Diária

- **Origem / primeira ocorrência:** GP-D06A…GP-D09A; consolidação AI-01 em 02/07/2026.
- **Extensão:** 6 documentos (consolidação + 5 fontes atribuídas); 5 auditorias; 0 OGs formais (família GP-D).
- **Influência:** separação entre memória permanente e estado operacional; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** padrão mais recorrente declarado na consolidação do domínio Projeto.
- **Evidência:** `AI_METHODOLOGICAL_OBSERVATIONS_CONSOLIDATION.md` linhas 82–101 e 209–225 registra recorrência, mas mantém hipótese e exige auditoria independente e validação humana.
- **Decisão:** **A — Permanecer Experimental.** A recorrência ocorre em uma única família e o próprio documento mantém a validação pendente.

### 3.8 H3 — Sucesso do Projeto como Declaração Documental

- **Origem / primeira ocorrência:** GP-D08A/GP-D08B, 02/07/2026.
- **Extensão:** 2 documentos; 1 auditoria diretamente dependente; 0 OGs formais (família GP-D).
- **Influência:** evita motor automático de sucesso nesta fase; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** limita o cálculo automático em GP-D08A.
- **Evidência:** `AI_METHODOLOGICAL_OBSERVATIONS_CONSOLIDATION.md` linhas 123–140 e 227–240 mantém a hipótese; `GP_D08A_PROJECT_OBJECTIVES_RESULTS_AUDIT.md` registra a aplicação local.
- **Decisão:** **A — Permanecer Experimental.** A aplicação única não distingue prudência local de regra generalizável.

### 3.9 H4 — Saturação por Recorrência Negativa

- **Origem / primeira ocorrência:** GP-D09A/AI-01, 02/07/2026.
- **Extensão:** 3 documentos; 1 auditoria diretamente dependente; 0 OGs formais (família GP-D).
- **Influência:** encerramento de ciclo pela recorrente ausência de necessidade estrutural; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** fundamenta a decisão de saturação do domínio Projeto.
- **Evidência:** `AI_METHODOLOGICAL_OBSERVATIONS_CONSOLIDATION.md` linhas 242–256 e 268–314 mantém a hipótese não promovida; GP-D09A e `HISTORY.md` registram a recorrência negativa.
- **Decisão:** **A — Permanecer Experimental.** Falta replicação com critérios prévios e casos negativos independentes.

### 3.10 Cadeia Documental GDC-R

- **Origem / primeira ocorrência:** GP-PI-07A, 17/07/2026; linha de pesquisa GP-RG, commit `2c9c852` em 18/07/2026.
- **Extensão:** identificador em 40 documentos e cadeia completa em 12; 4 artefatos de auditoria nominalmente identificados (PI-07A, RG-06, RG-07 e RG-09, além de controles OEG-GIT); 0 OGs formalmente registradas. Uso em três famílias: GP-PI, GP-RG e OEG-GIT.
- **Influência:** rastreabilidade observável de Premissa → Evidência → Inferência → Fundamentação → Decisão → Validação; Constituição de Pesquisa RG-01 afetada, Constituição ICFACTORY não alterada.
- **Dependência metodológica / uso:** estrutura protocolos, matrizes, auditorias, consolidação da Fase I e gates experimentais.
- **Evidência:** `PI_07A_DECISION_FOUNDATION_GOVERNANCE_REPORT.md`, RG-01…RG-09 e `PHASE_I_CONSOLIDATED_REPORT.md`; RG-01 mantém H-RG-001 pendente e o relatório da Fase I limita o apoio ao contexto sintético/documental.
- **Decisão:** **B — Promover para Validado.** A cadeia possui estabilidade, recorrência e dependência metodológica comprovadas dentro da Fase I. A validação deve ser explicitamente limitada ao corpus documental/sintético; a ausência de validação externa e de múltiplas OGs formais impede C.

### 3.11 Critério de Avaliação pré-declarado

- **Origem / primeira ocorrência:** RG-01 — Constituição de Pesquisa GDC-R, 17/07/2026.
- **Extensão:** 20 documentos; 1 artefato de auditoria nominal e protocolos experimentais RG-05…RG-09; 0 OGs formais (família GP-RG).
- **Influência:** avaliação por critérios definidos antes da execução; nenhuma Constituição ICFACTORY alterada.
- **Dependência metodológica / uso:** usado no pré-registro e nos protocolos da Fase I.
- **Evidência:** `RG_01_RESEARCH_CONSTITUTION.md` linhas 130–138 rotula o conceito como hipótese observacional e condiciona sua inclusão a evidência e distinção semântica.
- **Decisão:** **A — Permanecer Experimental.** Uso em protocolo não satisfaz a validação que o documento de origem exige.

### 3.12 Separação Epistêmica — Evidência não é Inferência

- **Origem / primeira ocorrência:** RG-01, PM-02/PM-03, 17/07/2026.
- **Extensão:** 7 documentos com expressão/conteúdo canônico; matrizes experimentais da linha GP-RG; 0 OGs formais (famílias GP-PI, GP-RG e GP-R06).
- **Influência:** observabilidade e separação de fato, hipótese, premissa e interpretação; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** organiza matrizes e auditorias experimentais GDC-R.
- **Evidência:** RG-01 linhas 168–180 define PM-02/PM-03; H-RG-002 é sustentada em um caso, e o relatório consolidado declara que isso não constitui validação.
- **Decisão:** **A — Permanecer Experimental.** Há suporte experimental localizado, não validação formal ou externa.

### 3.13 Revisão Explícita

- **Origem / primeira ocorrência:** GP-PI-07A / PM-07, 17/07/2026.
- **Extensão:** 2 documentos com expressão canônica; replicações dentro da linha GP-RG; 0 OGs formais (famílias GP-PI e GP-RG).
- **Influência:** revisão auditável de decisões; compatível com Evolução Auditável, sem alteração constitucional.
- **Dependência metodológica / uso:** compõe a hipótese H-RG-003 e a cadeia de revisão da Fase I.
- **Evidência:** RG-01 define PM-07; H-RG-003 foi sustentada em um caso e explicitamente não validada no relatório consolidado.
- **Decisão:** **A — Permanecer Experimental.** Suporte em uma linha experimental não comprova estabilidade independente.

### 3.14 Preservação Histórica

- **Origem / primeira ocorrência:** GP-PI-07A / PM-08, 17/07/2026.
- **Extensão:** busca ampla em 21 documentos e 4 artefatos de auditoria; 0 OGs formais (famílias GP-PI e GP-RG).
- **Influência:** preservação de estados e tentativas rejeitadas; compatível com Evolução Auditável, sem incorporação constitucional específica.
- **Dependência metodológica / uso:** associada à revisão da cadeia GDC-R.
- **Evidência:** RG-01 define PM-08 e H-RG-003; o relatório consolidado sustenta a hipótese em um caso, mas não a valida. Muitas ocorrências amplas descrevem história ou estado anterior e não provam aplicação de PM-08.
- **Decisão:** **A — Permanecer Experimental.** A evidência específica não pode ser substituída pela frequência de vocabulário genérico.

### 3.15 Harness como Executor Assistido sem Autoridade Própria

- **Origem / primeira ocorrência:** GP-H01 / GP-HA01…GP-HA08; dossiê consolidado em 12/07/2026.
- **Extensão:** 2 documentos canônicos; 2 auditorias consolidadas (GP-H01 e GP-HA07); 0 OGs formais (famílias GP-H e GP-HA).
- **Influência:** concretiza “Inteligência não é Autoridade”; o dossiê identifica lacuna constitucional, mas não altera a Constituição.
- **Dependência metodológica / uso:** o dossiê comprova prática de execução assistida no PROTEUS.
- **Evidência:** `HARNESS_GOVERNANCE_RESEARCH_DOSSIER.md` linhas 23–45 e 221–255 declara consolidação interna, caráter não normativo e ausência de validação externa; linha 29 registra prática operacional.
- **Decisão:** **A — Permanecer Experimental.** Uso pontual e consolidação interna não satisfazem validação externa nem estabilidade normativa.

### 3.16 Especificação Estruturada de Execução

- **Origem / primeira ocorrência:** GP-HA03; dossiê GP-HA08, 12/07/2026.
- **Extensão:** 1 documento canônico; 1 auditoria consolidativa (GP-HA07); 0 OGs formais (família GP-HA).
- **Influência:** explicitação de escopo e restrições antes da execução; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** a linha 29 do dossiê registra uso de especificações estruturadas na prática PROTEUS.
- **Evidência:** dossiê linhas 29, 92–98, 143 e 221–255 comprova uso interno e ausência de promoção/validação externa.
- **Decisão:** **A — Permanecer Experimental.** Falta reprodução em diferentes Harnesses e projetos.

### 3.17 Contexto de Execução governado

- **Origem / primeira ocorrência:** GP-HA04; dossiê GP-HA08, 12/07/2026.
- **Extensão:** 1 documento canônico; 1 auditoria consolidativa (GP-HA07); 0 OGs formais (família GP-HA).
- **Influência:** contexto explícito e controlado de execução; nenhuma Constituição alterada.
- **Dependência metodológica / uso:** prática PROTEUS descrita no dossiê.
- **Evidência:** dossiê linhas 29, 100–106, 144 e 221–255 registra contexto controlado e mantém o conceito fora da norma.
- **Decisão:** **A — Permanecer Experimental.** Não há métrica de portabilidade nem validação em outro Harness/projeto.

## CONCEITOS RECOMENDADOS PARA PROMOÇÃO CONSTITUCIONAL

**Nenhum.** Não existe evidência documental suficiente de que qualquer conceito reúna simultaneamente uso estrutural recorrente, dependência metodológica, estabilidade documental, aplicação em múltiplas auditorias, utilização em múltiplas OGs formalmente identificadas e ausência de conflitos conhecidos.

PA-02, PA-03 e GDC-R atingem o nível B no escopo observado, mas a ausência de validação externa/multidomínio e de uma ontologia formal de OG impede recomendação C.

## CONCEITOS QUE DEVEM PERMANECER EXPERIMENTAIS

- **DM-01:** somente um projeto; o registro exige projetos distintos.
- **DA-01:** somente CASE-01; projetos de verificação permanecem pendentes.
- **DA-02:** oito componentes de um único projeto não satisfazem o requisito multidomínio.
- **H1:** fonte canônica mantém hipótese em monitoramento e exige validação independente.
- **H2:** recorrência em uma única família GP-D, com validação humana pendente.
- **H3:** uma aplicação não distingue prudência local de regra geral.
- **H4:** falta replicação com critérios prévios e casos negativos independentes.
- **Critério de Avaliação:** RG-01 o declara hipótese observacional condicionada.
- **Separação Epistêmica:** H-RG-002 foi sustentada em um caso, explicitamente sem validação.
- **Revisão Explícita:** H-RG-003 tem suporte localizado, sem validação independente.
- **Preservação Histórica:** ocorrências genéricas não comprovam aplicação do conceito PM-08.
- **Harness como Executor Assistido:** consolidação interna, não normativa e sem validação externa.
- **Especificação Estruturada de Execução:** uma prática/corpus, sem reprodução entre Harnesses ou projetos.
- **Contexto de Execução:** uma prática/corpus, sem métricas ou validação de portabilidade.

## IMPACTO DA PROMOÇÃO

### PA-02 — recomendação B

- **Arquitetural:** transforma a progressão de valor em heurística validada no CASE-01, sem obrigar sua universalização.
- **Metodológico:** exige declarar alcance, condições de aplicação e critérios de falsificação.
- **Documental:** uma GP posterior deverá atualizar Discovery Catalog, registro de maturidade, dívida científica, HISTORY e ROADMAP de forma atômica; nesta GP nada é alterado.
- **Governança:** decisões futuras poderão citá-la como validada apenas no escopo ratificado. Para C, permanece necessária aplicação além do contexto de origem.

### PA-03 — recomendação B

- **Arquitetural:** reforça o gate contra materialização prematura, mas não cria proibição universal.
- **Metodológico:** requer tornar observável o que constitui “necessidade operacional objetiva” e registrar exceções.
- **Documental:** futura ratificação deve sincronizar catálogo, matriz, dívida, HISTORY e ROADMAP; esta revisão não efetua promoção.
- **Governança:** reduz ambiguidade em decisões de não materialização; antes de C, precisa de ensaio externo e análise de conflitos/limites.

### GDC-R — recomendação B

- **Arquitetural:** nenhum impacto estrutural direto; o efeito é na rastreabilidade de decisões arquiteturais.
- **Metodológico:** reconhece a cadeia como validada para pesquisa documental/sintética da Fase I, preservando explicitamente esse limite.
- **Documental:** futura ratificação deve separar baseline da pesquisa, método validado em escopo limitado e norma constitucional; nenhum documento de autoridade é alterado aqui.
- **Governança:** melhora auditabilidade, mas a Fase II externa e a definição formal de OG permanecem pré-condições para C.

### Conceitos mantidos em A

Não há impacto normativo imediato. A manutenção em Research evita que uso localizado seja convertido em obrigação universal. O impacto de governança é a necessidade de rotular explicitamente as decisões dependentes como experimentais e executar os protocolos recomendados na matriz antes de nova revisão.

## 7. Respostas ao critério de encerramento

1. **Quais conceitos podem permanecer experimentais?** DM-01, DA-01, DA-02, H1, H2, H3, H4, Critério de Avaliação, Separação Epistêmica, Revisão Explícita, Preservação Histórica, Harness como Executor Assistido, Especificação Estruturada de Execução e Contexto de Execução.
2. **Quais conceitos já são efetivamente validados pelo uso?** PA-02, PA-03 e GDC-R, exclusivamente no escopo documental/operacional observado e sujeitos a ratificação em GP posterior.
3. **Quais conceitos já atingiram maturidade constitucional?** Nenhum dos 17 conceitos revisados.
4. **Quais conceitos devem ser promovidos imediatamente?** Recomenda-se abrir promoção formal de PA-02, PA-03 e GDC-R para **Validado (B)**. Esta GP não executa a promoção. Nenhum deve ser promovido imediatamente à Constituição.
5. **Quais conceitos ainda necessitam de pesquisa adicional?** Todos os 14 mantidos em A; PA-02, PA-03 e GDC-R também precisam de validação externa/multidomínio antes de eventual C.

## 8. Encaminhamento recomendado

Abrir uma GP de ratificação limitada para PA-02, PA-03 e GDC-R, com autoridade humana explícita, declaração de escopo, critérios de falsificação e atualização atômica dos registros de maturidade/dívida. Em paralelo, abrir trilhas experimentais independentes para os 14 conceitos A. Somente após formalizar a ontologia de OG e obter evidência externa deverá ocorrer nova revisão constitucional.

## 9. Preservação e não alteração

Esta GP produziu somente este relatório e `CONCEPT_PROMOTION_MATRIX.csv` no novo repositório. Não alterou Constituição, Léxico Constitucional, Discovery Lifecycle, documentos do HANDA_CORE ou do PROTEUS; não migrou artefatos; não realizou commit nem push.
