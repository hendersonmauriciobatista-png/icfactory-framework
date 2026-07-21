# GP-FW-04 — Baseline de Governança v1.0

Status: **BASELINE APROVADA - GOVERNANCE BASELINE v1.0 VIGENTE**

Data da auditoria original: 2026-07-20 (America/Sao_Paulo)
Data da revalidação: 2026-07-20 (America/Sao_Paulo)
Baseline Commit v1.0: 38152f16091dedae70d739a2911c88e140e742b0

Natureza: inventário documental passivo; nenhum conceito, princípio, documento constitucional, pesquisa ou maturidade foi alterado.

## 0. Revalidação GP-FW-04 - Governance Baseline v1.0

Resultado da revalidação: **APROVADA**.

A revalidação da GP-FW-04 foi executada após a conclusão da GP-FW-04A e da GP-FW-04B. O commit `38152f16091dedae70d739a2911c88e140e742b0` passa a constituir o **Baseline Commit v1.0** da Governance Baseline v1.0 do ICFACTORY.

A primeira execução da GP-FW-04 permanece preservada neste documento como registro histórico de reprovação institucional. A aprovação atual não reescreve retroativamente a reprovação original; ela registra a superação dos bloqueios por meio da reconciliação topológica e da incorporação institucional do núcleo constitucional.

### 0.1 Respostas objetivas da revalidação

| Verificação obrigatória | Resultado |
|---|---|
| O framework pode ser reconstruído apenas a partir do repositório oficial? | Sim. |
| Existe alguma dependência operacional do HANDA_CORE? | Não. O HANDA_CORE permanece apenas como origem histórica preservada. |
| Existe documento obrigatório ausente? | Não. |
| Existe documento obrigatório apenas em working tree? | Não. |
| Existem documentos essenciais fora do histórico Git? | Não, exceto material explicitamente classificado como fora da baseline institucional. |
| Existem conflitos de autoridade? | Não bloqueantes após a GP-FW-04B. |
| Existe conflito constitucional? | Não identificado. |
| A proveniência foi preservada? | Sim, por manifesto e inventário. |
| Os manifestos são suficientes? | Sim para reconstrução institucional da Baseline v1.0. |
| O estado institucional é único? | Sim. |
| O estado institucional é íntegro? | Sim. |
| O estado institucional é reproduzível? | Sim. |
| O commit 38152f16091dedae70d739a2911c88e140e742b0 representa uma baseline consistente? | Sim. |
| Existe algum bloqueio para congelamento da Baseline v1.0? | Não. |

### 0.2 Escopo explicitamente fora da baseline

O diretório `research/authenticity_custody/poc/evidence/` permanece corretamente fora da baseline institucional. Sua exclusão não constitui bloqueio, pois o diretório não integra o núcleo institucional aprovado da Governance Baseline v1.0.

### 0.3 Declaração formal

A partir desta revalidação, a **Governance Baseline v1.0** passa a constituir o estado institucional oficial do ICFACTORY, tendo como baseline commit o hash `38152f16091dedae70d739a2911c88e140e742b0`.

## 1. Primeira execução GP-FW-04 - registro histórico preservado

## 1. Decisão executiva

A governança científica é documentalmente reconstruível, e os quatro gates GP-FW-03A…03D possuem decisões explícitas. Entretanto, o corpus atual não satisfaz os requisitos mínimos de uma baseline institucional única, íntegra e reproduzível.

A aprovação é bloqueada por quatro classes de achados materiais:

1. autoridades institucionais utilizadas pelos gates existem somente na working tree do repositório novo;
2. o registro central atribui simultaneamente P e E a cinco conceitos;
3. H-R03-01 foi promovida para E, mas não consta da matriz central de promoção;
4. o ROADMAP oficial existe somente na autoridade histórica, já possui alteração local anterior e não existe no repositório novo.

Consequentemente, esta GP registra o **estado candidato à baseline**, mas não declara `GOVERNANCE_BASELINE_V1` vigente, não encerra oficialmente o Primeiro Ciclo Científico, não atualiza o ROADMAP e não autoriza commit.

## 2. Método e regra de evidência

Foram utilizados somente:

- conteúdo dos arquivos existentes;
- estado Git verificável por `status`, `rev-parse`, `ls-files` e `log`;
- SHA-256 dos arquivos auditados;
- decisões expressas nos relatórios GP-FW-03A…03D;
- regra do `SCIENTIFIC_MATURITY_MODEL.md` segundo a qual cada conceito possui exatamente um nível vigente.

Precedência usada para reconstrução:

1. gate posterior e específico prevalece sobre registro anterior;
2. Constituição e Léxico permanecem autoridades externas em `C:\HANDA_CORE\ICFACTORY`;
3. existência na working tree comprova conteúdo local, mas não comprova preservação na baseline Git;
4. divergência não foi resolvida por inferência: foi registrada como inconsistência.

## 3. Topologia documental inspecionada

### 3.1 Autoridade constitucional e histórica

Repositório: `C:\HANDA_CORE`

Diretório documental: `C:\HANDA_CORE\ICFACTORY`

| Item | Estado verificável |
|---|---|
| Branch | `principal` |
| HEAD | `95f23628319a969e1d89c3a89466d8533fb09140` |
| `origin/principal` | `95f23628319a969e1d89c3a89466d8533fb09140` |
| Constituição | rastreada; SHA-256 `1E9A6CB132E4D209B2F784F5C26E0030DF7C65F433CDB102029884905D347A56` |
| Léxico Constitucional | rastreado; SHA-256 `73C39120D4F283CC24801F2F33A93FD01C72187400FDF7ACC3560C2DD0142C0C` |
| Arquitetura de Governança | rastreada; SHA-256 `F0DE25379A84504B197975EEC357BA7E38BC85EBAED6D6DB766B79F116863F8D` |
| Discovery Lifecycle | somente working tree; SHA-256 `EA469930278FBAC8634DD5E07AA16C67B3EE70D55857FD88302B09E6355ACF95` |
| ROADMAP | rastreado, porém alterado localmente antes desta GP; SHA-256 da working tree `067135DF36AC10A9DE940A6E644987745BBEC0EEE61BCAFACB2DE44C8BB66AD0` |
| HISTORY | rastreado, porém alterado localmente antes desta GP; SHA-256 da working tree `D9CA499DD040A3E3036AB2FE94D90928DA812C8C64CD833F56FD8B53FE569273` |

### 3.2 Governança científica e gates

Repositório: `C:\Users\Guiuliano\icfactory-framework`

| Item | Estado verificável |
|---|---|
| Branch | `main` |
| HEAD | `10e3f72417d491d295721277ba89b72fcae5c2b5` |
| `origin/main` | `f799ca9b3c66e118b12584424ecbc2010f1c009f` |
| Publicação | branch local quatro commits à frente de `origin/main` |
| ROADMAP | ausente |

## 4. Inventário das autoridades de governança

| Documento | SHA-256 | Estado Git no repositório novo | Avaliação de baseline |
|---|---|---|---|
| `SCIENTIFIC_MATURITY_MODEL.md` | `9229F99955653141C777E6253F3FFA7D6175FEB4E5ED396B41BDC1CA5E0CA8D4` | rastreado | preservado |
| `KNOWLEDGE_EVOLUTION_LIFECYCLE.md` | `2ECCE96BF0FF807F985106D240532AA51A65DBD4FC0784FF75A0178ACB87FB8A` | não rastreado | bloqueio material |
| `METHODOLOGICAL_CUSTODY_MODEL.md` | `3F6E0DE754BE75BA2C9ED2D8B3835249D596473859E3CACB3BE527864F9A6873` | não rastreado | bloqueio material |
| `COMMUNITY_CONTRIBUTION_POLICY.md` | `C9E1D324FF74D9BE2075FB2F9A8290401A7FFECE47D8AEE0214AE2E1E21F55E3` | não rastreado | bloqueio material |
| `METHODOLOGICAL_CUSTODIAN_REGISTER.md` | `EAA0602F16C69EC433CA210CF22D6251E2EB96455C4AA12B4EE365F585FA0580` | não rastreado | bloqueio crítico: contém `CM-001` |
| `CUSTODIAL_APPOINTMENT_POLICY.md` | `174E0975B3CBDDA011EAB690B0AE493345EAEE4503B442FA3B81D34B1E726B66` | não rastreado | bloqueio material |
| `CONCEPT_PROMOTION_MATRIX.csv` | `5CF0EC110CC2AF3A8974B4897358F915F23817CF4B0909DA6A432644B6102A91` | rastreado | preservado, mas inconsistente |
| `GP_FW_03A_EXPERIMENTAL_GATE_REPORT.md` | `9DD86056489D1D1EBC27C1F7903EAB748A9CAB361CA2451FA02F6BF9314E8CBC` | rastreado | preservado |
| `GP_FW_03B_PA02_VALIDATION_GATE.md` | `0BBD582699F53DAA1645FF043D11D98F77A9FCF3E5DBDD708F1D4924E993C6A7` | rastreado | preservado |
| `GP_FW_03C_PA03_VALIDATION_GATE.md` | `99300B30BED850DBD8155588E0B589440E0CE1DFC98AE42C7E8F75686C94F4F4` | rastreado | preservado |
| `GP_FW_03D_GDCR_VALIDATION_GATE.md` | `2F83C0DA604E488D782140E2450A7A4DF670550DADDDA079FA01891442514299` | rastreado | preservado |

Os relatórios GP-FW-03B…03D atribuem a decisão ao titular `CM-001`. O registro que prova a designação de `CM-001` existe localmente e declara Henderson Mauricio Batista como titular vigente, mas não integra o histórico Git. A cadeia decisória é legível na máquina auditada, porém ainda não é reproduzível a partir do repositório versionado.

## 5. Constituição e Léxico vigentes

- Constituição vigente: `C:\HANDA_CORE\ICFACTORY\CONSTITUTION.md`, versão 0.2, status ATIVA, hash acima.
- Léxico vigente: `C:\HANDA_CORE\ICFACTORY\CONSTITUTIONAL_LEXICON.md`, hash acima.
- Nenhum desses documentos foi alterado por esta GP.
- Eles não estão presentes no repositório novo; a baseline, portanto, é distribuída entre duas localizações.

Não foi localizada evidência de conflito material entre PA-02, PA-03, GDC-R ou H-R03-01 e a Constituição vigente. O problema encontrado é de configuração, registro e reprodutibilidade, não de incompatibilidade constitucional demonstrada.

## 6. Estado dos conceitos

### 6.1 Pesquisa (P) sem conflito de registro identificado

- H-R03-02 — Hash é necessário, mas insuficiente;
- H-R03-03 — Assinatura digital precisa de raiz institucional;
- H-R03-04 — Manifesto canônico é preferível à assinatura direta;
- H-R03-05 — Release oficial é projeção, não raiz exclusiva;
- H-R03-06 — sucessão ordinária encadeia chaves antiga e nova;
- H-R03-07 — registro histórico de chaves preserva atos após rotação;
- H-R03-08 — carimbo temporal externo é opcional;
- Índice de Rastreabilidade das Premissas — IRP;
- Harness Experimental GP-R06;
- Assessment, Improvement e Validation Engines.

### 6.2 Experimental (E) confirmado sem promoção posterior

- H-R03-01 — Envelope Custodial Portável em Camadas, promovida por GP-FW-03A e limitada a experimentação fictícia/controlada;
- DM-01 — Identificação do Núcleo do Negócio;
- DA-01 — Especialização por Contexto Operacional;
- DA-02 — Auditoria de Integração Arquitetural;
- Separação Epistêmica — Evidência não é Inferência;
- Revisão Explícita;
- Preservação Histórica;
- Harness como Executor Assistido sem Autoridade Própria;
- Especificação Estruturada de Execução;
- Contexto de Execução governado.

O registro anterior também declara como E, sem promoção posterior documentada: Prompt Operacional derivado de Especificação e Contexto; Pré-Validação da Execução Assistida; Processo completo de Execução Assistida e cadeia de custódia; Inventário de Premissas GP-R06; Artefato de Fundamentação da Decisão — AFD. Esses itens não constam da matriz central atual e exigem reconciliação de cobertura.

### 6.3 Validado (V) por gate vigente

| Conceito | Gate | Escopo válido |
|---|---|---|
| PA-02 — Progressão de Valor | GP-FW-03B | PROTEUS/CASE-01; período documental 2026-06-28…2026-07-20 |
| PA-03 — Materialização sob Necessidade | GP-FW-03C | PROTEUS/CASE-01; necessidade operacional objetiva documentada |
| GDC-R | GP-FW-03D | governança documental da Fase I GDC-R no PROTEUS/CASE-01 |

O registro anterior contém ainda alegações V para Research/Discovery Lifecycle, Gate GX-PKG e Executabilidade Experimental/Integridade do Pacote. Elas não aparecem na matriz central de promoção e não foram objeto dos gates GP-FW-03A…03D; permanecem como alegações legadas pendentes de reconciliação, sem regressão ou promoção executada nesta GP.

### 6.4 Constitucional (C)

O corpus constitucional vigente é a Constituição 0.2 e seu Léxico. O registro científico anterior contém explicitamente `Inteligência não é Autoridade` como C, com fundamento no Artigo XI.

Não houve gate V → C no Primeiro Ciclo Científico. Os demais artigos constitucionais são normas vigentes, mas não estão individualizados como conceitos científicos na matriz central; esta GP não cria retroativamente tais registros.

### 6.5 Estados inconsistentes

As linhas abaixo usam o rótulo externo `Experimental`, mas registram `P — hipótese` no próprio campo `current_status`:

- H1 — Auditoria antes da Materialização;
- H2 — Memória Permanente versus Operação Diária;
- H3 — Sucesso do Projeto como Declaração Documental;
- H4 — Saturação por Recorrência Negativa;
- Critério de Avaliação pré-declarado.

O registro científico anterior classifica os cinco como P; a matriz de promoção posterior os apresenta como `Experimental (P ...)`. Como o modelo exige exatamente um nível, eles não podem ser congelados honestamente em P ou E sem ato de correção documental.

## 7. Histórico dos gates

| Gate | Resultado | Transição | Efeito vigente | Commit local |
|---|---|---|---|---|
| GP-FW-03A | aprovado, 7/7 critérios | H-R03-01 P → E | uso experimental controlado; não institucional | `509ce99` |
| GP-FW-03B | aprovado | PA-02 E → V | V no PROTEUS/CASE-01 | `c8a6750` |
| GP-FW-03C | aprovado | PA-03 E → V | V no PROTEUS/CASE-01 | `c2ecda1` |
| GP-FW-03D | aprovado | GDC-R E → V | V na Fase I documental/sintética declarada | `10e3f72` |

Todos os quatro gates possuem relatório e commit local. Nenhum foi publicado em `origin/main` até esta auditoria.

## 8. Pesquisas em andamento

R-03 — Autenticidade Custodial permanece `P — PESQUISA ATIVA; FASE INICIAL CONCLUÍDA` em seu documento principal. A PoC R-03A está concluída. Somente H-R03-01 teve promoção posterior para E; as demais hipóteses continuam em P.

Os textos de Research que descrevem H-R03-01 como P são evidência histórica anterior ao gate, não revogação. O relatório GP-FW-03A e o registro de transições do Scientific Maturity Model prevalecem para o estado vigente.

## 9. Descobertas relevantes ainda não institucionalizadas

Permanecem fora do núcleo constitucional:

- H-R03-01 e todas as demais hipóteses R-03;
- DM-01, DA-01 e DA-02;
- Separação Epistêmica, Revisão Explícita e Preservação Histórica;
- conceitos de Harness/execução assistida;
- conceitos GP-R06 listados no registro científico anterior;
- H1…H4 e Critério de Avaliação, cujo nível ainda deve ser desambiguado;
- PA-02, PA-03 e GDC-R, que são V somente nos escopos declarados.

## 10. Pendências para futura promoção Constitucional

PA-02, PA-03 e GDC-R permanecem elegíveis para futura avaliação V → C, mas ainda exigem, conforme os próprios gates:

- comprovação multidomínio;
- estabilidade longitudinal;
- replicação independente;
- tratamento de resultados adversos e condições de falsificação;
- delimitação de custos, escalabilidade e efeitos;
- análise de compatibilidade constitucional específica;
- gate V → C e ato custodial próprios.

H-R03-01 não é elegível diretamente a C: deve completar experimentação, resolver bootstrap/raiz de confiança, revogação, rotação, forks, validação semântica e replicação antes de eventual E → V.

## 11. Conflitos e riscos internos

| ID | Achado | Severidade | Efeito |
|---|---|---|---|
| CFG-01 | autoridades GP-FW-02D…02F e `CM-001` não rastreadas | crítica | gates não são reproduzíveis somente pelo Git |
| REG-01 | cinco conceitos com rótulo simultâneo P/E | alta | viola unicidade de maturidade |
| REG-02 | H-R03-01 E ausente da matriz central | alta | registro oficial incompleto |
| REG-03 | registro científico anterior diverge da matriz atual e contém alegações V não reconciliadas | alta | não existe inventário único |
| AUTH-01 | Discovery Lifecycle existe apenas na working tree da autoridade histórica | alta | ciclo oficial não está preservado em HEAD |
| MAP-01 | ROADMAP ausente no repositório novo e modificado localmente na autoridade histórica | alta | encerramento não pode ser registrado sem decidir fonte/destino |
| PUB-01 | quatro gates existem somente em commits locais | média | estado publicado não representa o ciclo concluído |

## 12. Riscos de congelar hoje

Se a baseline fosse declarada vigente hoje:

- a designação `CM-001` poderia ser perdida ao reconstruir o repositório por clone;
- o Lifecycle e as políticas de Custódia poderiam desaparecer;
- cinco conceitos seriam congelados com maturidade ambígua;
- H-R03-01 permaneceria fora do inventário central apesar do gate aprovado;
- registros anteriores e atuais continuariam emitindo estados diferentes;
- o ROADMAP poderia ser atualizado na cópia errada ou sobrepor alteração preexistente;
- terceiros obteriam de `origin/main` um estado anterior aos quatro gates.

## 13. Respostas ao critério de encerramento

1. **A governança encontra-se consistente?** Não integralmente. O encadeamento metodológico é compreensível, mas os registros e a configuração documental apresentam inconsistências materiais.
2. **Existem conflitos internos?** Sim: P/E simultâneo, matriz incompleta e divergência entre registros.
3. **Todas as promoções estão devidamente registradas?** Nos relatórios e no Scientific Maturity Model, sim; no inventário central, não, pois H-R03-01 está ausente.
4. **Existe algum conceito em estado inconsistente?** Sim: H1, H2, H3, H4 e Critério de Avaliação pré-declarado.
5. **O framework encontra-se oficialmente estabilizado nesta baseline?** Não. Esta execução não aprova nem põe em vigor a Baseline v1.0.

## 14. Decisão e próxima GP recomendada

**Decisão:** GP-FW-04 reprovada como gate de congelamento; auditoria e inventário concluídos; baseline institucional não ratificada.

Recomenda-se uma **GP-FW-04A — Reconciliação de Configuração e do Registro de Maturidade**, limitada a:

1. definir o corpus versionado oficial e preservar nele as autoridades ratificadas;
2. escolher formalmente o ROADMAP autoritativo e reconciliar sua alteração local preexistente;
3. atribuir um único nível a H1…H4 e Critério de Avaliação sem promoção tácita;
4. incluir H-R03-01 na matriz central como E;
5. reconciliar alegações legadas e cobertura dos registros;
6. confirmar que o histórico Git contém a cadeia `CM-001` → gates;
7. repetir o gate de baseline e somente então registrar o encerramento no ROADMAP.

A frase de estabilização solicitada não é emitida, pois existem inconsistências verificáveis.

## 15. Preservação e não intervenção

Nesta GP:

- Constituição, Léxico, princípios, conceitos, pesquisas e maturidades não foram alterados;
- nenhum arquivo preexistente foi reescrito;
- o ROADMAP não foi alterado;
- nenhum commit foi executado;
- nenhum push foi executado.
