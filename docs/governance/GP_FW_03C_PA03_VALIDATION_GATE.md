# GP-FW-03C — Gate de Promoção do PA-03 para Validado (V)

Data da decisão: 2026-07-20 (America/Sao_Paulo)

Status: **GATE APROVADO**

Transição: **Experimental (E) → Validado (V)**

Objeto: **PA-03 — Materialização sob Necessidade**

Escopo ratificado: **PROTEUS/CASE-01, no período documental de 2026-06-30 a 2026-07-20**

Natureza: gate científico e ato custodial limitado; não constitucional

## 1. Decisão executiva

O gate **é aprovado**. PA-03 satisfaz os critérios de saída de Experimental (E) e de entrada em Validado (V) no escopo observado do PROTEUS/CASE-01.

A decisão valida o conhecimento no escopo declarado. Não estabelece proibição universal de materializar, não declara validade fora do CASE-01, não transforma PA-03 em princípio constitucional e não autoriza ampliação por analogia.

> PA-03 passa oficialmente a integrar o conjunto de conceitos Validados do ICFACTORY, no escopo explicitamente documentado, permanecendo elegível para futura promoção Constitucional conforme o Scientific Maturity Model.

## 2. Instrumento e autoridade

| Campo | Registro |
|---|---|
| Identificador do ato | `GP-FW-03C-AC-001` |
| Tipo | Gate E→V e decisão de validação com escopo explícito |
| Titular responsável | Henderson Mauricio Batista |
| Fundamento da autoridade | Custódia Metodológica vigente, designação `CM-001` |
| Objeto | PA-03 — Materialização sob Necessidade |
| Estado anterior | Experimental (E) — Discovery Candidata |
| Estado vigente | Validado (V), exclusivamente no escopo ratificado |
| Versão da hipótese avaliada | Formulação registrada em `DISCOVERY_CATALOG.md`, seção “PA-03 — Materialização sob Necessidade”, com gatilhos e limites documentados no corpus GP-D01/GP-D/OP |
| Vigência | 2026-07-20 |
| Documentos oficiais atualizados | `CONCEPT_PROMOTION_MATRIX.csv` e `SCIENTIFIC_MATURITY_MODEL.md` |
| Autoridade máxima preservada | Constituição ICFACTORY v0.2; nenhuma alteração constitucional ou lexical |

A revisão documental foi preparada como atividade auditável e não substitui a competência humana da Custódia. A decisão formal deste instrumento é atribuída ao titular vigente identificado em `CM-001`, dentro da competência exclusiva E→V registrada no `METHODOLOGICAL_CUSTODY_MODEL.md`.

## 3. Método e congelamento das evidências

A avaliação foi passiva e documental. Foram executadas:

1. busca lexical por `PA-03`, `Materialização sob Necessidade` e variante sem acentos nos três acervos relevantes;
2. separação entre a Discovery PA-03 e identificadores homônimos de PAC, OEG e frentes arquiteturais;
3. inclusão das fontes de origem GP-D01A/GP-D01C, mesmo sem o identificador literal;
4. reconstrução da primeira ocorrência e dos eventos de implementação pelo histórico Git;
5. leitura das auditorias de domínio, arquitetura e operação que aplicam o conceito;
6. busca de conflitos, contraexemplos, resultados adversos e razões de regressão;
7. confronto com Constituição, Discovery Lifecycle, Scientific Maturity Model e Custódia Metodológica;
8. revisão independente do encadeamento entre hipótese, decisões de adiar, decisões de materializar minimamente, riscos e gate.

Repositórios e estados examinados:

- `C:\HANDA_CORE\ICFACTORY` — autoridade constitucional e Discovery Lifecycle; HEAD anteriormente validado pelas GP-FW-02/02B como `95f23628319a969e1d89c3a89466d8533fb09140`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua` — corpus operacional PROTEUS; HEAD `66598f3f8338ce1c02c9b7139fcde3ceb78d37ac`;
- `C:\Users\Guiuliano\icfactory-framework` — governança científica e custodial; base desta GP `c8a675049fe7c2b62b86b4e1b81496cb6a9b01fa`.

### 3.1 Correção da contagem anterior

A GP-FW-02C informou 32 documentos e 22 artefatos de auditoria. A busca atual reproduziu **32 arquivos com correspondência lexical**, mas oito não tratam da Discovery “Materialização sob Necessidade”:

- `docs/pac/PE_01_IMPLEMENTATION_EXECUTION_STRATEGY.md` — PA-03 é o “Plano de rastreabilidade, integridade e governança de dados”;
- `docs/pac/PAC_14_PROJECT_EVOLUTION_PLAN.md` — o mesmo plano do PAC;
- `docs/architecture/PE_06_PA01B_ARCHITECTURAL_AUDIT.md` — PA-03 é uma frente evolutiva do programa PA-01, vinculada ao PAC;
- `docs/media/OEG_PA_03_PICTURE_LOCK_REVIEW.md` — PA-03 integra o código OEG-PA-03;
- `docs/media/OEG_PA_04_SC009_RECAPTURE_PLAN.md` — referência ao código OEG-PA-03;
- `docs/media/OEG_PA_06_SC009_COMPARATIVE_EVALUATION.md` — referência ao código OEG-PA-03;
- `docs/media/OEG_PA_07_SC009_PROMOTION.md` — referência ao código OEG-PA-03;
- `docs/media/OEG_PA_08_PICTURE_LOCK_REEVALUATION.md` — referência ao código OEG-PA-03.

Foram acrescentadas duas fontes de origem sem o identificador literal: GP-D01A e GP-D01C. Resultado depurado: **26 documentos semanticamente relacionados**, dos quais **21 são artefatos de auditoria**.

A evidência anterior que atribuía aplicação a PAC, OEG e PE-06 estava contaminada por homônimos e não é usada neste gate. A correção reduz a contagem, mas preserva um corpus recorrente e decisório em domínio, arquitetura e operação.

### 3.2 Integridade criptográfica das fontes centrais

| Fonte | SHA-256 |
|---|---|
| `C:\HANDA_CORE\ICFACTORY\CONSTITUTION.md` | `1E9A6CB132E4D209B2F784F5C26E0030DF7C65F433CDB102029884905D347A56` |
| `C:\HANDA_CORE\ICFACTORY\research\DISCOVERY_LIFECYCLE.md` | `EA469930278FBAC8634DD5E07AA16C67B3EE70D55857FD88302B09E6355ACF95` |
| `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D01A_MONITORING_PROJECT_DOMAIN_AUDIT.md` | `152D8103D058DD89EBE2E3EAF83BB98D1BF37C9298E249D9B204B9486E054D6C` |
| `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D01C_PERSISTENCE_STRATEGY_AUDIT.md` | `74A2503DCC54BDEEF225BA8222B6599FE4F6F184FB24ED0A44CDD832E0F24C80` |
| `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\research\DISCOVERY_CATALOG.md` | `957BAFD72275030C92081C61F89C0A444C684D7E9F6A5DC7653550D685593969` |
| `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D02A_OPERATIONAL_CONTEXT_AUDIT.md` | `354C4BC5085AC34251A0A65A49F22AB3BAB353129405B080F9A0409B244E1B55` |
| `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\architecture\AC_01_ARCHITECTURAL_CONSOLIDATION_AUDIT.md` | `51245F8E4AB03B64425BD32BB92ECE40790F1E76A5D2892A00C3519A3F7DCB2B` |
| `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\architecture\PE_22_WAVE_B_ELIGIBILITY_AUDIT.md` | `63615083193D4FC4CE85EDC14F7E9712CF7F8805DCDAC8BB81A16C3D1C2E5F82` |
| `docs/governance/GP_FW_02C_CONCEPT_PROMOTION_REVIEW.md` | `2DDB806D321308523ABD2EE12399F957375216096A56E0C644040AD4AE45B2D1` |
| `docs/governance/CONCEPT_PROMOTION_MATRIX.csv` antes desta GP | `70CD6A89CC1212F877CCF792623AA39A12177A772FE2097ED8457C5C65A56662` |
| `docs/governance/SCIENTIFIC_MATURITY_MODEL.md` antes desta GP | `F71382EFD71FEA004D874534B8F887D7FAF8DE0DEAA0AD5F7897710F0724FED0` |
| `docs/governance/METHODOLOGICAL_CUSTODY_MODEL.md` | `3F6E0DE754BE75BA2C9ED2D8B3835249D596473859E3CACB3BE527864F9A6873` |
| `docs/governance/METHODOLOGICAL_CUSTODIAN_REGISTER.md` | `EAA0602F16C69EC433CA210CF22D6251E2EB96455C4AA12B4EE365F585FA0580` |

`GP_D01C_PERSISTENCE_STRATEGY_AUDIT.md` e `DISCOVERY_CATALOG.md` estão apenas na working tree do PROTEUS. Seus conteúdos são verificáveis e foram congelados por hash, mas a ausência de versionamento é risco de proveniência e publicação que deve ser resolvido antes de V→C.

## 4. Origem, definição e cadeia de evidências

### 4.1 Origem e primeira ocorrência

- origem conceitual: GP-D01A, commit `e9f4dbeb8d5e14a842943f76ae7dc12a1d1a0ba7`, de 2026-06-30;
- implementação mínima GP-D01B: commit `7b9d7a0148f339ddbfafb2791ccda49e179199cd`, de 2026-06-30, preservado em Git, HISTORY e ROADMAP;
- auditoria de persistência GP-D01C: arquivo local `GP_D01C_PERSISTENCE_STRATEGY_AUDIT.md`;
- primeira ocorrência versionada do identificador `PA-03`: GP-D02A, commit `386aa37e171a824d4ad690b2a0dcea3bf3502bbd`, de 2026-06-30;
- registro institucional local: `docs/research/DISCOVERY_CATALOG.md`, seção PA-03;
- recomendação E→V: GP-FW-02C, em 2026-07-20.

Não foi localizado relatório autônomo denominado GP-D01B. Sua existência e execução são comprovadas pelo commit `7b9d7a0`, por `HISTORY.md` e por `ROADMAP.md`. A ausência do relatório individual é uma lacuna de linhagem, não ausência do evento.

### 4.2 Objeto exato validado

É validada, no PROTEUS/CASE-01, a hipótese catalogada de que um conceito aprovado pelo modelo de domínio não deve ser obrigatoriamente materializado na persistência enquanto não existir necessidade operacional objetiva que justifique essa materialização.

O corpus demonstra que PA-03 não significa “nunca materializar”. Seu comportamento observado é:

1. reconhecer e auditar o conceito;
2. explicitar necessidade, valor, autoridade e gatilhos;
3. adiar entidade, coleção, persistência, interface ou workflow sem necessidade objetiva;
4. materializar a forma mínima suficiente quando a necessidade for comprovada;
5. preservar caminho de evolução e reabrir a decisão diante de novos gatilhos.

### 4.3 Corpus semanticamente relacionado

Origem e Research:

- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D01A_MONITORING_PROJECT_DOMAIN_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D01C_PERSISTENCE_STRATEGY_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\research\DISCOVERY_CATALOG.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\research\AI_METHODOLOGICAL_OBSERVATIONS_CONSOLIDATION.md`.

Domínio:

- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D02A_OPERATIONAL_CONTEXT_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D03A_MONITORING_PROJECT_LIFECYCLE_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D03B_LIFECYCLE_REMARKS_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D03C_LIFECYCLE_REMARKS_PRIORITY.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D03D_PROJECT_CLOSURE_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D04A_PROJECT_DOSSIER_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D04C_PROJECT_DOSSIER_CONTENT_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D05A_PROJECT_RESPONSIBILITIES_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D06A_PROJECT_EVIDENCE_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D07A_PROJECT_INSTITUTIONAL_EVENTS_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D08A_PROJECT_OBJECTIVES_RESULTS_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D09A_PROJECT_DOMAIN_SATURATION_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\domain\GP_D10A_PROJECT_INSTANCE_AUDIT.md`.

Operação e arquitetura:

- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\operational\OP_00_OPERATIONAL_SCOPE_BOUNDARY_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\operational\OP_01_OPERATIONAL_INFORMATION_FLOW_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\operational\OP_02_INFORMATION_UNIT_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\operational\OP_03_INFORMATION_RECORD_TYPES_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\architecture\AC_01_ARCHITECTURAL_CONSOLIDATION_AUDIT.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\architecture\PE_22_WAVE_B_ELIGIBILITY_AUDIT.md`.

Memória e adoção:

- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\history\HISTORY.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\roadmap\ROADMAP.md`;
- `C:\Users\Guiuliano\SistemaAnaliseAgua\docs\branding\BRAND_GUIDELINES.md`.

### 4.4 Aplicações observadas e dependência

O corpus registra decisões negativas e positivas, evitando viés de confirmar PA-03 apenas pela ausência de implementação:

- GP-D01A reconheceu Amostra conceitualmente e adiou implementação até necessidade objetiva;
- GP-D01B materializou somente o Projeto ativo mínimo e preservou os CSVs;
- GP-D01C rejeitou `projeto_id` prematuro e índice paralelo, mas declarou gatilhos objetivos para futura persistência;
- GP-D02A/GP-D02B auditaram e depois materializaram apenas o perfil operacional necessário;
- GP-D03 auditou ciclo, ressalvas e encerramento antes de materializar estados mínimos;
- GP-D04 auditou Dossiê e conteúdo antes de materializar estrutura e memória permanente mínimas;
- GP-D06 e GP-D08 materializaram referências e campos textuais simples, sem entidades, coleções ou workflows dedicados;
- GP-D07 manteve Eventos Institucionais documentais por falta de necessidade objetiva;
- OP-00…OP-03 reconheceram atividades, fluxos, unidades e tipos sem materialização automática;
- AC-01 aceitou persistência simples no estado atual e PE-22 registrou gatilhos de reabertura: escala, multiprojeto, multiusuário, concorrência e transação.

A dependência é decisória: PA-03 controla quando adiar e quando escolher a menor materialização suficiente. O resultado observado não é imobilismo; é evolução condicionada por evidência.

## 5. Avaliação dos critérios obrigatórios

| # | Critério | Resultado | Fundamentação documental |
|---:|---|---|---|
| 1 | O conceito permanece tecnicamente consistente? | **Sim** | A hipótese catalogada é coerente com GP-D01A/01C e com a sequência auditoria → necessidade → materialização mínima. Não proíbe evolução e possui gatilhos explícitos. |
| 2 | As evidências permanecem válidas? | **Sim, no escopo declarado** | A origem conceitual, o commit de implementação e 26 documentos semânticos/21 auditorias são reconstruíveis. Não foi localizada revogação ou falsificação posterior. Fontes locais foram congeladas por hash. |
| 3 | Existem aplicações suficientes para sustentar a validação? | **Sim, para V no PROTEUS/CASE-01** | Há decisões recorrentes de adiar, materializar minimamente e reabrir sob gatilho em domínio, arquitetura e operação. A evidência não sustenta universalidade ou C. |
| 4 | O conceito apresenta estabilidade metodológica? | **Sim, com limites explícitos** | “Necessidade operacional objetiva antes de materialização” permaneceu estável. As aplicações preservam auditabilidade, forma mínima e evolução futura. |
| 5 | Existe conflito com a Constituição vigente? | **Não identificado** | PA-03 operacionaliza especialmente Observação Antes da Intervenção (Art. II), Contexto Explícito (Art. IV) e Evolução Auditável (Art. X), sem criar autoridade normativa paralela. |
| 6 | Existe conflito com a Custódia Metodológica? | **Não** | A promoção ocorre por gate próprio, evidência depurada, escopo, riscos, autoridade `CM-001` e registros oficiais, sem promoção automática ou constitucional. |
| 7 | Existem fundamentos técnicos para regressão? | **Não identificados** | Não há evidência de protocolo inadequado, hipótese invalidada ou aplicação irreproduzível. As fragilidades de persistência são gatilhos de reavaliação, não refutação do conceito. |

### 5.1 Pareceres contrários e inconclusivos preservados

Os registros “não promover” e “permanece candidata” documentam corretamente o estado anterior ou a falta de competência daqueles atos. Não são refutações técnicas.

Permanecem inconclusivos:

- aplicação em projeto ou domínio independente;
- métricas comparativas de complexidade evitada, custo de adiamento e custo de materialização tardia;
- adequação em contextos regulados, transacionais, concorrentes ou multiprojeto;
- suficiência para incorporação constitucional.

## 6. Limitações, riscos e condições de falsificação

### Limitações remanescentes

1. O escopo positivo contém somente PROTEUS/CASE-01.
2. Não existe validação externa ou multidomínio documentada.
3. A janela longitudinal observada é curta.
4. “Necessidade operacional objetiva” possui exemplos e gatilhos, mas ainda não tem protocolo quantitativo universal.
5. GP-D01C e `DISCOVERY_CATALOG.md` permanecem não versionados; GP-D01B não possui relatório autônomo localizado.
6. O identificador PA-03 colide com PAC, OEG e uma frente arquitetural.
7. A evidência não cobre requisitos legais, segurança crítica, alta concorrência ou integridade transacional obrigatória.

### Riscos conhecidos

- usar PA-03 como justificativa genérica para não implementar requisito necessário;
- postergar materialização até gerar dívida, ambiguidade histórica ou migração onerosa;
- confundir simplicidade atual com suficiência permanente;
- ignorar gatilhos de multiprojeto, volume, concorrência, transação ou rastreabilidade por linha;
- promover uso fora do CASE-01 por analogia;
- inflar evidências por colisão de identificadores;
- perder fontes locais não versionadas.

### Condições que exigem revisão extraordinária ou regressão

- materialização tardia causar perda de dados, rastreabilidade ou custo desproporcional;
- gatilhos objetivos serem ignorados ou não detectados;
- aplicação sistemática bloquear requisito obrigatório ou transferência de autoridade;
- resultados contraditórios em outro projeto/domínio;
- alteração substancial da definição;
- perda de reconstruibilidade das fontes;
- expansão do escopo sem novo gate.

## 7. Escopo de validade e futura promoção Constitucional

### Escopo positivo

PA-03 é Validado para decisões de domínio, persistência, interface, workflow e estrutura no PROTEUS/CASE-01, quando a decisão:

- é precedida por auditoria e evidência;
- declara a necessidade ou sua ausência;
- escolhe a forma mínima suficiente;
- registra riscos e gatilhos de reabertura;
- preserva rastreabilidade e caminho de evolução.

### Limites negativos

PA-03 não está validado como regra universal, não autoriza omissão de requisitos mandatórios e não substitui análise de segurança, legalidade, integridade, transação, concorrência ou escalabilidade.

### Requisitos para futura avaliação V→C

1. aplicações independentes em outros projetos ou domínios;
2. protocolo objetivo para caracterizar necessidade e momento de reabertura;
3. casos positivos, negativos e de materialização tardia mensurados longitudinalmente;
4. validação em cenários com multiprojeto, concorrência, transação ou requisitos regulatórios;
5. resolução/qualificação oficial da colisão do identificador PA-03;
6. versionamento e preservação das fontes de origem;
7. análise de impacto, texto normativo proposto, revisão constitucional e aprovação humana específica.

Próxima revisão: quando surgir novo domínio, gatilho de persistência, conflito, mudança de definição ou evidência adversa; na ausência de evento, recomenda-se revisão até 2027-01-20.

## 8. Atualizações autorizadas e preservação

Esta GP atualiza exclusivamente:

- `docs/governance/GP_FW_03C_PA03_VALIDATION_GATE.md`;
- a linha de PA-03 em `docs/governance/CONCEPT_PROMOTION_MATRIX.csv`;
- o registro de transições em `docs/governance/SCIENTIFIC_MATURITY_MODEL.md`.

Não altera Constituição, Léxico Constitucional, Discovery Lifecycle, PA-02, GDC-R ou qualquer outro conceito. Não promove PA-03 para Constitucional. Não cria princípio. Não altera arquivos do PROTEUS ou do HANDA_CORE.

## 9. Respostas ao critério de encerramento

1. **Gate aprovado ou reprovado?** Aprovado.
2. **PA-03 passa oficialmente para Validado (V)?** Sim.
3. **Em qual escopo essa validação é válida?** Exclusivamente no PROTEUS/CASE-01, no período e nas condições documentadas nas seções 3, 4 e 7.
4. **Quais limitações permanecem?** Ausência de validação externa/multidomínio, janela longitudinal curta, falta de protocolo quantitativo universal, lacunas de versionamento/linhagem, colisão de identificador e cenários críticos ainda não observados.
5. **O conceito permanece elegível para futura promoção Constitucional?** Sim, condicionado ao atendimento integral dos requisitos V→C da seção 7.

## 10. Encerramento

A GP-FW-03C está documentalmente concluída. A transição E→V entra em vigor em 2026-07-20 no escopo ratificado. Qualquer uso fora desse escopo permanece experimental ou não avaliado até gate próprio.
