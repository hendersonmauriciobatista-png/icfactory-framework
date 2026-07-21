# Registro Oficial de Dívida Científica

GP-FW-02B — 2026-07-20

Foram identificados **16 conceitos** que influenciam decisões, arquitetura, auditorias, governança ou prática operacional sem validação formal suficiente para o alcance em que vêm sendo usados.

## DM-01 — Identificação do Núcleo do Negócio

- **Maturidade:** E
- **Uso:** Uso pontual
- **OGs/execuções de governança:** GP-R01; aplicação no CASE-01
- **Influência:** princípios — Orientação da arquitetura pelo núcleo do negócio; constituições — Nenhuma; auditorias — Evidência declarada na evolução arquitetural do CASE-01
- **Evidência da dívida:** METHODOLOGICAL_DISCOVERIES linhas 67–77 e 127–151 registra impacto no CASE-01, exige projetos distintos e mantém estado CANDIDATA.
- **Ação obrigatória recomendada:** Executar validação multidomínio antes de promover ou usar como regra geral

## DA-01 — Especialização por Contexto Operacional

- **Maturidade:** E
- **Uso:** Uso pontual
- **OGs/execuções de governança:** GP-R01; aplicação no CASE-01
- **Influência:** princípios — Reuso de arquitetura por contexto; constituições — Nenhuma; auditorias — Evidência arquitetural apenas no projeto de origem
- **Evidência da dívida:** ARCHITECTURAL_DISCOVERIES linhas 39–118 marca CANDIDATA, assinala apenas Sistema de Análise de Água e deixa outros projetos pendentes.
- **Ação obrigatória recomendada:** Testar em segundo domínio e documentar critérios de falsificação

## DA-02 — Auditoria de Integração Arquitetural

- **Maturidade:** E
- **Uso:** Utilizado em OG
- **OGs/execuções de governança:** GP-A14 AI-01…AI-08
- **Influência:** princípios — Coerência das dependências e integração entre camadas; constituições — Nenhuma; auditorias — Oito auditorias de integração da GP-A14
- **Evidência da dívida:** PROTEUS HISTORY linhas 5314–5936 registra oito auditorias executadas; ARCHITECTURAL_DISCOVERIES linhas 126–226 mantém DA-02 CANDIDATA e requer projetos distintos.
- **Ação obrigatória recomendada:** Validar a técnica em outro projeto antes de promoção arquitetural

## PA-02 — Progressão de Valor

- **Maturidade:** E
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-R02; GP-D02A…GP-D10A; AC-01; PAC-14; OEG-PA02/03
- **Influência:** princípios — Enriquecimento de camadas existentes em vez de novas camadas; constituições — Nenhuma; não promovida; auditorias — AC-01; CASE01; auditorias GP-D; OP-00…OP-03; PAC
- **Evidência da dívida:** DISCOVERY_CATALOG linhas 63–81 mantém CANDIDATA; busca documental encontra PA-02 em 32 arquivos; GP-D07A/08A e AC-01 usam PA-02 para justificar decisões.
- **Ação obrigatória recomendada:** Suspender uso como fundamento decisório geral ou abrir validação formal multidomínio

## PA-03 — Materialização sob Necessidade

- **Maturidade:** E
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-D01A…GP-D10A; AC-01; PAC-14; OEG-PA03…08
- **Influência:** princípios — Materialização apenas diante de necessidade operacional objetiva; constituições — Nenhuma; não promovida; auditorias — GP-D; AC-01; PE-06; OP-00…OP-03; PAC e OEG
- **Evidência da dívida:** DISCOVERY_CATALOG linhas 85–112 mantém CANDIDATA; busca encontra PA-03 em 32 arquivos; GP-D07A/08A e AC-01 a usam diretamente para não materializar.
- **Ação obrigatória recomendada:** Formalizar validação e limites; até lá rotular decisões como experimentais

## H1 — Auditoria antes da Materialização

- **Maturidade:** P
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-D07A; GP-D08B; GP-D09A
- **Influência:** princípios — Auditoria documental precede entidade, persistência, workflow ou camada; constituições — Nenhuma; auditorias — Auditorias de domínio que preservaram conceitos documentais
- **Evidência da dívida:** AI-01 linhas 62–80, 181–200 e 258–314 declara hipótese em monitoramento, recorrente, não promovida e dependente de validação humana.
- **Ação obrigatória recomendada:** Executar auditoria humana independente e protocolo comparativo

## H2 — Memória Permanente versus Operação Diária

- **Maturidade:** P
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-D06A; GP-D07A; GP-D08A/B; GP-D09A
- **Influência:** princípios — Separação de memória permanente e estado operacional; constituições — Nenhuma; auditorias — Auditorias do domínio Projeto e Dossiê Final
- **Evidência da dívida:** AI-01 linhas 82–101 e 209–225 chama este o padrão mais recorrente, mas exige auditoria independente e validação humana.
- **Ação obrigatória recomendada:** Validar em domínio externo e definir critérios observáveis

## H3 — Sucesso do Projeto como Declaração Documental

- **Maturidade:** P
- **Uso:** Utilizado em OG
- **OGs/execuções de governança:** GP-D08A; GP-D08B
- **Influência:** princípios — Evitar motor automático de sucesso nesta fase; constituições — Nenhuma; auditorias — Auditoria de objetivos/resultados
- **Evidência da dívida:** AI-01 linhas 123–140 e 227–240 mantém a hipótese; GP-D08A usa a leitura para limitar cálculo automático.
- **Ação obrigatória recomendada:** Testar critérios e separar prudência local de regra metodológica

## H4 — Saturação por Recorrência Negativa

- **Maturidade:** P
- **Uso:** Utilizado em OG
- **OGs/execuções de governança:** GP-D09A
- **Influência:** princípios — Encerramento de ciclos por ausência recorrente de necessidade estrutural; constituições — Nenhuma; auditorias — Auditoria de saturação do domínio
- **Evidência da dívida:** AI-01 linhas 242–256 e 268–314 mantém hipótese não promovida; GP-D09A e HISTORY registram recorrência negativa na decisão de saturação.
- **Ação obrigatória recomendada:** Replicar com critérios prévios e casos negativos independentes

## GDC-R — Cadeia Premissa–Evidência–Inferência–Fundamentação–Decisão–Validação

- **Maturidade:** E
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-PI-07A; GP-RG-01…09; OEG-GIT-04/05/07
- **Influência:** princípios — Rastreabilidade e fundamentação observável de decisões; constituições — Constituição de pesquisa RG-01; nenhuma alteração da Constituição ICFACTORY; auditorias — Auditorias PI-07A, RG-06, RG-07, RG-09 e OEG-GIT
- **Evidência da dívida:** A cadeia aparece em 12 documentos e GDC-R em 40; RG-01 linha 74 marca hipótese com validação pendente; PHASE I linhas 145–168 limita apoio ao contexto sintético.
- **Ação obrigatória recomendada:** Separar baseline de pesquisa da metodologia oficial e executar Fase II externa

## Critério de Avaliação pré-declarado

- **Maturidade:** P
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-RG-01; GP-RG-05…09
- **Influência:** princípios — Validação por critérios definidos antes da execução; constituições — Nenhuma; auditorias — Pré-registro e auditorias experimentais RG-06/07/09
- **Evidência da dívida:** RG-01 linhas 130–138 rotula HIPÓTESE OBSERVACIONAL e condiciona inclusão; protocolos posteriores usam critérios prévios.
- **Ação obrigatória recomendada:** Validar distinção semântica e necessidade independente na Fase II

## Separação Epistêmica — Evidência não é Inferência

- **Maturidade:** E
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-PI-07A; GP-RG-01…09; GP-R06
- **Influência:** princípios — Observabilidade; distinção fato, hipótese, premissa e interpretação; constituições — Nenhuma alteração constitucional; auditorias — Matrizes e auditorias experimentais GDC-R
- **Evidência da dívida:** RG-01 linhas 168–180 define PM-02/03; H-RG-002 é sustentada em um caso e o relatório proíbe tratá-la como validada.
- **Ação obrigatória recomendada:** Executar comparação controlada com protocolo alternativo

## Revisão Explícita e Preservação Histórica de tentativas rejeitadas

- **Maturidade:** E
- **Uso:** Utilizado em múltiplas OGs
- **OGs/execuções de governança:** GP-PI-07A; GP-RG
- **Influência:** princípios — Evolução auditável; não apagar estados anteriores; constituições — Compatível com Evolução Auditável, mas não incorporado à Constituição; auditorias — Auditorias da cadeia GDC-R
- **Evidência da dívida:** RG-01 linhas 192–198 define PM-07/08; H-RG-003 é sustentada em um caso, explicitamente não validada.
- **Ação obrigatória recomendada:** Validar ganho causal e custo documental antes de promoção

## Harness como executor assistido sem autoridade própria

- **Maturidade:** E
- **Uso:** Uso pontual
- **OGs/execuções de governança:** GP-H01; GP-HA01…08; prática de execução no PROTEUS
- **Influência:** princípios — Inteligência não é autoridade; autoridade humana explícita; constituições — Lacuna constitucional identificada; Constituição não alterada; auditorias — GP-H01 e GP-HA07
- **Evidência da dívida:** Dossiê linhas 23–45 e 221–255 diz consolidado internamente, não normativo e sem validação externa; linha 29 comprova prática operacional.
- **Ação obrigatória recomendada:** Abrir validação externa e decidir camada normativa correta

## Especificação Estruturada de Execução

- **Maturidade:** E
- **Uso:** Uso pontual
- **OGs/execuções de governança:** GP-HA03; prática PROTEUS
- **Influência:** princípios — Escopo e restrições explícitas antes da execução; constituições — Nenhuma; auditorias — GP-HA03; consolidação GP-HA07
- **Evidência da dívida:** Dossiê linhas 29, 92–98, 143 e 221–255 comprova uso de especificações estruturadas e ausência de promoção/validação externa.
- **Ação obrigatória recomendada:** Validar em diferentes Harnesses/projetos antes de normatizar

## Contexto de Execução governado

- **Maturidade:** E
- **Uso:** Uso pontual
- **OGs/execuções de governança:** GP-HA04; prática PROTEUS
- **Influência:** princípios — Contexto explícito e controlado; constituições — Nenhuma; auditorias — GP-HA04; consolidação GP-HA07
- **Evidência da dívida:** Dossiê linhas 29, 100–106, 144 e 221–255 comprova contexto controlado na prática e mantém o conceito fora da norma.
- **Ação obrigatória recomendada:** Definir métricas e validar portabilidade entre Harnesses

## Regra de encerramento da dívida

Nenhum item sai deste registro por uso recorrente, conveniência ou consolidação documental interna. A baixa exige validação formal compatível com o alcance alegado, decisão explícita de governança e, quando aplicável, incorporação constitucional separada.
