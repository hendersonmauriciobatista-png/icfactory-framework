# GP-FW-02B — Auditoria de Integridade da Baseline e da Maturidade Científica

Status: **CONCLUÍDA — BASELINE INCOMPLETA E DÍVIDA CIENTÍFICA FORMALIZADA; NENHUMA MIGRAÇÃO EXECUTADA**

Data: 2026-07-20 (America/Sao_Paulo)

## 1. Veredito executivo

A baseline publicada **não representa integralmente** o estado documental atual do ICFACTORY. HEAD e origin/principal coincidem em `95f23628319a969e1d89c3a89466d8533fb09140`, mas a working tree contém sete documentos relevantes apenas locais e alterações não ratificadas em HISTORY/ROADMAP. A camada Research validada pela GP-R01 e suas três Discoveries iniciais não existem no HEAD.

A auditoria científica registrou **28 conceitos**: P=8, E=16, V=3 e C=1. **16** constituem dívida científica por influência ou uso sem validação formal suficiente.

O framework **não pode ser congelado hoje sem perda de conhecimento**. Pode-se congelar tecnicamente o HEAD como baseline publicada, mas isso excluiria onboarding, mapa documental, teste de adoção, Research/GP-R01, DM-01, DA-01, DA-02 e os registros locais correspondentes. Também cristalizaria o descompasso entre Discoveries usadas no PROTEUS e sua ausência no núcleo publicado.

## 2. Método e escopo

A GP aplicou ACI(R): leitura passiva, comparação Git, inventário de documentos, busca exata de identificadores e conceitos, reconstrução de primeira ocorrência, verificação de status declarados e diferenciação entre uso, menção e hipótese. Foram inspecionados `C:\HANDA_CORE\ICFACTORY`, documentos de método/AGENTS da raiz HANDA_CORE e o corpus PROTEUS de research, architecture, domain, operational, PAC, media, HISTORY e ROADMAP.

Não existe nos arquivos pesquisados uma definição ou catálogo formal chamado “Organização de Governança (OG)”. Para não inventar ontologia, o campo `ogs` registra somente identificadores explícitos de execução governada (GP, OEG ou PAC). Os níveis “Utilizado em OG/múltiplas OGs” significam uso documentado em uma ou várias famílias desses programas, não comprovação de uma entidade organizacional adicional.

## 3. Parte I — Integridade da baseline

### Working tree × HEAD

Documentos alterados e pendentes de ratificação:

- `ICFACTORY/HISTORY.md`: +33 linhas GP-R01.
- `ICFACTORY/ROADMAP.md`: +31/-1 linhas GP-R01.

Documentos apenas locais e pendentes de ratificação:

- `README.md`
- `ICFACTORY/DOCUMENT_MAP.md`
- `ICFACTORY/GETTING_STARTED.md`
- `ICFACTORY/adoption_tests/ICFACTORY_AI_ADOPTION_TEST.md`
- `ICFACTORY/research/DISCOVERY_LIFECYCLE.md`
- `ICFACTORY/research/architecture/ARCHITECTURAL_DISCOVERIES.md`
- `ICFACTORY/research/methodology/METHODOLOGICAL_DISCOVERIES.md`

Documentos removidos: **nenhum**. Documentos apenas remotos: **nenhum**.

### HEAD × origin/principal

Nenhuma diferença. HEAD = origin/principal = `95f23628319a969e1d89c3a89466d8533fb09140`.

### tag icfactory-v1.0 × HEAD

Tag de origem: `1c719e61c71cdef403a16830e13835e78a08ed43`. Entre o tag e o HEAD atual, somente três documentos do núcleo mudaram:

- `ICFACTORY/governance/PROJECT_CONSTITUTION_TEMPLATE.md`: integração de conformidade/remediação e baseline v0.6.
- `ICFACTORY/HISTORY.md`: registros das evoluções constitucionais.
- `ICFACTORY/ROADMAP.md`: atualização do planejamento constitucional.

Não houve adição, remoção ou rename versionado dos sete documentos locais, porque eles permanecem fora do HEAD.

## 4. Parte II — Maturidade científica

Critérios: P = hipótese/pesquisa sem validação; E = aplicada ou consolidada experimentalmente, mas sem validação suficiente para generalização; V = validação formal apenas no escopo declarado; C = incorporada a autoridade constitucional vigente. “Baseline metodológica da pesquisa” não equivale a C nem a validação universal.

| Código | Quantidade |
|---|---:|
| P | 8 |
| E | 16 |
| V | 3 |
| C | 1 |
| **Total** | **28** |

A matriz CSV e o Registro de Maturidade apresentam origem, primeira ocorrência, documentos, GPs/OEG/PAC, princípios, constituições e auditorias de cada conceito.

## 5. Parte III — Estado de uso

| Nível de uso | Quantidade |
|---|---:|
| Não utilizado | 8 |
| Uso pontual | 5 |
| Utilizado em múltiplas OGs | 8 |
| Utilizado em OG | 5 |
| Utilizado estruturalmente pelo framework | 2 |

A repetição documental por si só não foi contada como uso. Uso exige declaração de aplicação, decisão fundamentada, auditoria executada ou processo efetivamente realizado.

## 6. CONCEITOS EXPERIMENTAIS EM USO

Todos os conceitos abaixo possuem evidência de uso/influência e ainda não têm validação formal suficiente para o alcance observado:

- **DM-01 — Identificação do Núcleo do Negócio** — maturidade E; Uso pontual; evidência: METHODOLOGICAL_DISCOVERIES linhas 67–77 e 127–151 registra impacto no CASE-01, exige projetos distintos e mantém estado CANDIDATA.
- **DA-01 — Especialização por Contexto Operacional** — maturidade E; Uso pontual; evidência: ARCHITECTURAL_DISCOVERIES linhas 39–118 marca CANDIDATA, assinala apenas Sistema de Análise de Água e deixa outros projetos pendentes.
- **DA-02 — Auditoria de Integração Arquitetural** — maturidade E; Utilizado em OG; evidência: PROTEUS HISTORY linhas 5314–5936 registra oito auditorias executadas; ARCHITECTURAL_DISCOVERIES linhas 126–226 mantém DA-02 CANDIDATA e requer projetos distintos.
- **PA-02 — Progressão de Valor** — maturidade E; Utilizado em múltiplas OGs; evidência: DISCOVERY_CATALOG linhas 63–81 mantém CANDIDATA; busca documental encontra PA-02 em 32 arquivos; GP-D07A/08A e AC-01 usam PA-02 para justificar decisões.
- **PA-03 — Materialização sob Necessidade** — maturidade E; Utilizado em múltiplas OGs; evidência: DISCOVERY_CATALOG linhas 85–112 mantém CANDIDATA; busca encontra PA-03 em 32 arquivos; GP-D07A/08A e AC-01 a usam diretamente para não materializar.
- **H1 — Auditoria antes da Materialização** — maturidade P; Utilizado em múltiplas OGs; evidência: AI-01 linhas 62–80, 181–200 e 258–314 declara hipótese em monitoramento, recorrente, não promovida e dependente de validação humana.
- **H2 — Memória Permanente versus Operação Diária** — maturidade P; Utilizado em múltiplas OGs; evidência: AI-01 linhas 82–101 e 209–225 chama este o padrão mais recorrente, mas exige auditoria independente e validação humana.
- **H3 — Sucesso do Projeto como Declaração Documental** — maturidade P; Utilizado em OG; evidência: AI-01 linhas 123–140 e 227–240 mantém a hipótese; GP-D08A usa a leitura para limitar cálculo automático.
- **H4 — Saturação por Recorrência Negativa** — maturidade P; Utilizado em OG; evidência: AI-01 linhas 242–256 e 268–314 mantém hipótese não promovida; GP-D09A e HISTORY registram recorrência negativa na decisão de saturação.
- **GDC-R — Cadeia Premissa–Evidência–Inferência–Fundamentação–Decisão–Validação** — maturidade E; Utilizado em múltiplas OGs; evidência: A cadeia aparece em 12 documentos e GDC-R em 40; RG-01 linha 74 marca hipótese com validação pendente; PHASE I linhas 145–168 limita apoio ao contexto sintético.
- **Critério de Avaliação pré-declarado** — maturidade P; Utilizado em múltiplas OGs; evidência: RG-01 linhas 130–138 rotula HIPÓTESE OBSERVACIONAL e condiciona inclusão; protocolos posteriores usam critérios prévios.
- **Separação Epistêmica — Evidência não é Inferência** — maturidade E; Utilizado em múltiplas OGs; evidência: RG-01 linhas 168–180 define PM-02/03; H-RG-002 é sustentada em um caso e o relatório proíbe tratá-la como validada.
- **Revisão Explícita e Preservação Histórica de tentativas rejeitadas** — maturidade E; Utilizado em múltiplas OGs; evidência: RG-01 linhas 192–198 define PM-07/08; H-RG-003 é sustentada em um caso, explicitamente não validada.
- **Harness como executor assistido sem autoridade própria** — maturidade E; Uso pontual; evidência: Dossiê linhas 23–45 e 221–255 diz consolidado internamente, não normativo e sem validação externa; linha 29 comprova prática operacional.
- **Especificação Estruturada de Execução** — maturidade E; Uso pontual; evidência: Dossiê linhas 29, 92–98, 143 e 221–255 comprova uso de especificações estruturadas e ausência de promoção/validação externa.
- **Contexto de Execução governado** — maturidade E; Uso pontual; evidência: Dossiê linhas 29, 100–106, 144 e 221–255 comprova contexto controlado na prática e mantém o conceito fora da norma.

Os conceitos Prompt Operacional derivado, Pré-Validação, processo completo de execução assistida, Inventário de Premissas GP-R06, AFD, IRP, Harness Experimental e Engines foram registrados na matriz, mas **não** incluídos nesta lista porque os próprios documentos os apresentam como modelos não implementados/congelados e nenhuma evidência de uso foi localizada.

## 7. Parte IV — Dívida científica

O Registro Oficial de Dívida Científica contém 16 itens. A maior exposição é PA-02/PA-03: continuam candidatas, mas aparecem em 32 documentos cada e justificam decisões de não criação de camadas, não materialização, persistência, domínio, operação, PAC e OEG. DA-02 também excedeu seu nível formal ao orientar oito auditorias dentro do projeto de origem.

GDC-R e Harnesses apresentam outro tipo de dívida: a documentação declara consolidação interna ou baseline de pesquisa, enquanto validação externa, multidomínio e constitucionalização permanecem ausentes. O uso deve continuar rotulado como experimental até fechamento dos respectivos programas de validação.

## 8. RISCOS DA BASELINE

### Conhecimento perdido se a baseline fosse congelada hoje

- Camada Research/GP-R01 e Discovery Lifecycle validado documentalmente.
- DM-01, DA-01 e DA-02 e sua proveniência.
- Mapa documental, onboarding e evidência do teste de adoção.
- Registro GP-R01 ainda apenas nos diffs de HISTORY/ROADMAP.
- README que separa framework ICFACTORY da instância H&A.

### Conceitos utilizados mas não publicados no ICFACTORY

- DA-02 está apenas na Research local, embora aplicada na GP-A14.
- PA-02/PA-03, hipóteses H1–H4, GDC-R e Harness Governance vivem no PROTEUS e não no HEAD do ICFACTORY.

### Conceitos utilizados mas não constitucionalizados

- DM-01, DA-01, DA-02, PA-02, PA-03, cadeia GDC-R, separação epistêmica e conceitos de Harnesses.
- Nenhum deles altera hoje Constituição, Léxico Constitucional ou Template; uso recorrente não produz constitucionalização tácita.

### Pesquisas usadas sem validação formal suficiente

- PA-02/PA-03 em decisões arquiteturais e de domínio.
- DA-02 em auditorias GP-A14.
- H1–H4 como padrões metodológicos nas GPs de domínio.
- GDC-R em governança documental de decisões e experimentos.
- Harness, Especificação e Contexto em prática assistida no PROTEUS.

## 9. Respostas obrigatórias de encerramento

1. **A baseline representa integralmente o estado oficial do ICFACTORY?** Não. Representa integralmente apenas o estado publicado; não contém sete documentos locais nem os diffs GP-R01 em HISTORY/ROADMAP.
2. **Existem documentos importantes apenas na working tree?** Sim: os sete listados na Parte I, especialmente Research, DOCUMENT_MAP, GETTING_STARTED e README.
3. **Existem pesquisas já utilizadas operacionalmente?** Sim: DA-02, PA-02, PA-03, padrões H1–H4, GDC-R e práticas de Harness possuem evidências de aplicação/influência.
4. **Existem conceitos experimentais sendo usados como fundamento metodológico?** Sim. PA-02/PA-03 fundamentam decisões explícitas; GDC-R fundamenta governança documental; DA-02 fundamenta auditorias; hipóteses H1–H4 orientam decisões de domínio.
5. **Quais conceitos possuem dívida científica?** Os 16 itens do SCIENTIFIC_DEBT_REGISTER.md.
6. **O framework pode ser congelado hoje sem perda de conhecimento?** Não. O congelamento seguro exige primeiro preservar/ratificar a camada local, registrar a dívida e delimitar o alcance dos conceitos V/E/P.

## 10. Recomendação anterior à GP-FW-03

Executar uma decisão de baseline científica antes da migração: (a) ratificar ou rejeitar os sete documentos locais; (b) reconciliar HISTORY/ROADMAP; (c) anexar os registros de maturidade e dívida ao manifesto de origem; (d) bloquear promoção tácita de PA-02/PA-03/DA-02; (e) manter GX-PKG como V apenas no escopo sintético; e (f) abrir programas de validação para conceitos em uso. Somente então a GP-FW-03 poderá congelar uma baseline sem apagar conhecimento ou confundir pesquisa com norma.

## 11. Encerramento e rastreabilidade

Autoridade auditada: `C:\HANDA_CORE\ICFACTORY`. HEAD/origin: `95f23628319a969e1d89c3a89466d8533fb09140`. Tag: `1c719e61c71cdef403a16830e13835e78a08ed43`. PROTEUS permaneceu em `66598f3f8338ce1c02c9b7139fcde3ceb78d37ac`. Destino permaneceu em `f799ca9b3c66e118b12584424ecbc2010f1c009f`. Nenhum arquivo de origem foi alterado, nenhum documento foi migrado, nenhum commit e nenhum push foram executados.
