# PROJECT CONSTITUTION TEMPLATE — v0.6 CANDIDATE

**Versão candidata:** 0.6  
**Status:** CANDIDATE — NÃO VIGENTE — NÃO PROMULGADO  
**Predecessor vigente:** `PROJECT_CONSTITUTION_TEMPLATE.md` v0.5  
**Framework:** ICFACTORY  
**Compatibilidade proposta:** PCIP-01  

> Este documento é sucessor prospectivo candidato do Template v0.5. Não altera retroativamente Constituições, atos, decisões ou proveniências anteriores. Até promulgação competente, o v0.5 permanece a referência vigente.

---

# 1. PROPÓSITO

Este template estabelece a estrutura mínima para constituir e evoluir projetos ICFACTORY sem regressão recursiva de autoridade, vacância interna, dependência de pessoa nominal específica ou contexto oculto.

Toda Constituição de Projeto permanece subordinada à Constituição ICFACTORY.

O template distingue:

- origem da cadeia de autoridade do projeto;
- função institucional e titular humano;
- decisão e execução;
- autoridade interna e autoridade externa/reservada;
- primeiro ciclo constitucional e alterações ordinárias posteriores.

---

# 2. IDENTIFICAÇÃO DO PROJETO

Nome canônico do projeto:

Identificador estável do projeto:

Data de constituição:

Domínio de aplicação:

Responsável contextual:

Repositório(s) canônico(s), quando aplicável:

Continuidade material com projeto anterior:

- [ ] NÃO
- [ ] SIM — identificar predecessor:

As informações contextuais não criam autoridade por si mesmas.

---

# 3. REFERÊNCIAS SUPERIORES E DERIVAÇÃO

Constituição ICFACTORY aplicável:

Versão/commit de referência:

Ato instituidor aplicável:

PCIP aplicável:

Versão/commit do PCIP:

Outras normas do framework aplicáveis:

A Constituição do Projeto não pode contrariar referência superior vigente. Conflito conhecido deve ser declarado e resolvido em favor da autoridade superior aplicável.

---

# 4. EVENTO DE CONSTITUIÇÃO INICIAL

Preencher esta seção somente no primeiro ciclo constitucional do projeto.

Identificador único do Evento de Constituição Inicial:

Autoridade instituidora:

Titular humano que pratica o ato:

Capacidade exercida:

Fonte imediata da competência:

Ato de instituição/designação da autoridade instituidora:

Data de efeito da competência:

Evidência verificável:

Data do Evento:

Identidade integral da Constituição candidata constituída:

Declaração de efeito prospectivo:

Declaração de não retroatividade:

Declaração de consumação após entrada em vigor da primeira Constituição válida:

O Evento é único por identidade material de projeto. Mudança de nome, versão, branch, repositório, tecnologia, arquitetura, equipe ou titular não reabre o Evento quando houver continuidade material.

---

# 5. AUTORIDADE SOBERANA DO PROJETO — ASP

A ASP é função humana institucional do projeto. A autoridade pertence ao papel dentro de seu escopo, não permanentemente à pessoa que o ocupa.

## 5.1 Instituição da função

Identificador do papel:

Nome do papel: Autoridade Soberana do Projeto — ASP

Fonte de instituição:

Escopo:

Data de efeito:

Reservas superiores/externas:

## 5.2 Titularidade

Titular humano inicial:

Ato de designação:

Data de início:

Status:

Substituto temporário, se houver:

Sucessor designado, se houver:

Cadeia de contingência, se houver:

## 5.3 Competência interna residual

Salvo reserva superior ou externa aplicável, a ASP possui todos os poderes internos necessários à continuidade, evolução, contenção, reorganização e encerramento do projeto.

Incluem-se, sem caráter exaustivo:

- identidade, missão e escopo;
- requisitos e prioridades;
- arquitetura e evolução arquitetural;
- semântica operacional interna;
- seleção/substituição/descontinuação de SSoT interna;
- implementação e mudança técnica;
- migração;
- ativação e desativação;
- cutover;
- rollback;
- release;
- suspensão e retomada;
- aceitação/rejeição/contenção de risco interno;
- decisões emergenciais;
- declaração `OUT_OF_SCOPE`;
- encerramento;
- criação, alteração, fusão, suspensão ou extinção de papéis subordinados;
- designação, substituição e remoção de titulares;
- delegação, revogação e subdelegação expressamente permitida;
- sucessão e contingência de autoridade.

Se surgir matéria interna não atribuída a função especializada, a competência retorna à ASP, salvo reserva superior/externa.

`AUTHORITY_TO_DECIDE != DECISION_TO_PROCEED`.

---

# 6. MATRIZ DE AUTORIDADE DO CICLO DE VIDA

Preencher titular/função competente ou declarar `ASP` quando retida pela autoridade residual.

| Matéria | Autoridade competente | Delegação | Reserva/condição |
|---|---|---|---|
| Produto e escopo | | | |
| Requisitos | | | |
| Arquitetura | | | |
| Semântica interna | | | |
| SSoT interna | | | |
| Implementação | | | |
| Migração | | | |
| Ativação | | | |
| Cutover | | | |
| Rollback | | | |
| Release | | | |
| HOLD / RELEASE de gate | | | |
| Risco interno | | | |
| Emergência/contingência | | | |
| Encerramento | | | |

A ausência de linha para matéria interna futura não cria vacância: aplica-se a competência residual da ASP.

---

# 7. DELEGAÇÃO, SUBDELEGAÇÃO E REVOGAÇÃO

Toda delegação deve registrar:

Identificador:

Delegante:

Delegado/função:

Competência delegada:

Escopo:

Limites:

Início de vigência:

Término/condição:

Subdelegação:

- [ ] PROIBIDA
- [ ] PERMITIDA EXPRESSAMENTE dentro destes limites:

Revogabilidade:

Efeito sobre decisões em curso:

Delegação não amplia a competência originária e não cria autoridade externa.

---

# 8. SUCESSÃO, SUBSTITUIÇÃO E VACÂNCIA

Mudança de titular não exige nova Constituição quando a função e a competência permanecem.

Ato de sucessão/substituição:

Titular anterior:

Novo titular/substituto:

Capacidade assumida:

Data de efeito:

Transferência de registros:

Condições de retorno, quando temporária:

Na vacância não coberta por sucessão válida, a autoridade instituidora superior competente pode designar novo titular por ato ordinário prospectivo. O bootstrap originário não é reutilizado.

---

# 9. INTELIGÊNCIA DE GOVERNANÇA — IG

Identificação da função/serviço:

IA(s), assistente(s), auditor(es), Harness(es) ou ferramentas autorizadas:

Escopo informativo:

A IG pode analisar, auditar, contradizer, recomendar, classificar não vinculantemente, verificar rastreabilidade e preparar evidências.

A IG não decide, não aprova, não libera, não cria autoridade e não transforma recomendação em ordem.

`INTELLIGENCE_IS_NOT_AUTHORITY`.

---

# 10. AGENTE DE EXECUÇÃO — AE

Agentes/ferramentas/pessoas executoras autorizáveis:

Fronteira de execução:

Contrato mínimo de execução:

- autoridade humana competente;
- objeto;
- escopo;
- ação autorizada;
- limites;
- critérios de sucesso/falha;
- evidência esperada;
- condição de parada;
- rollback quando aplicável.

O AE não infere nem amplia autoridade.

---

# 11. COMPATIBILIDADE CONSTITUCIONAL

Para cada princípio aplicável da Constituição ICFACTORY, registrar:

| Princípio | Como é preservado | Evidência/mecanismo | Autoridade responsável |
|---|---|---|---|
| Autoridade explícita | | | |
| Governança unificada | | | |
| Observadores não governam | | | |
| Explicabilidade | | | |
| Evolução auditável | | | |
| Inteligência não é autoridade | | | |

Conflitos conhecidos:

- [ ] NENHUM CONHECIDO
- [ ] EXISTEM — listar e tratar:

---

# 12. RATIFICAÇÃO CONSTITUCIONAL INICIAL

Esta seção existe exclusivamente para o primeiro ciclo constitucional e somente produz efeito se o PCIP correspondente estiver vigente e o Evento de Constituição Inicial tiver conferido competência para esta ratificação.

Autoridade humana ratificadora:

Capacidade exercida:

Fonte da competência:

Referência ao Evento de Constituição Inicial:

Revisão adversarial utilizada:

Resultado da compatibilidade constitucional:

- [ ] COMPATÍVEL
- [ ] INCOMPATÍVEL
- [ ] INDETERMINADO

Conflitos e tratamento:

Declaração de Ratificação Constitucional Inicial:

Data:

A Ratificação Constitucional Inicial:

- é prospectiva;
- é consumível uma única vez por projeto;
- não legitima atos pretéritos;
- não cria autoridade externa;
- não transforma IG, auditor ou AE em autoridade;
- não pode ser usada em alterações constitucionais ordinárias posteriores.

Após a primeira Constituição válida, esta seção torna-se historicamente fechada.

---

# 13. ALTERAÇÕES CONSTITUCIONAIS ORDINÁRIAS

Após o primeiro ciclo, alterações constitucionais materiais seguem o regime ordinário vigente do ICFACTORY.

Para cada alteração:

Versão anterior:

Nova versão candidata:

Autor/elaborador responsável:

Fonte de competência para elaboração:

Autoridade de validação constitucional:

Fonte de competência para validação:

Resultado da validação:

Autoridade aprovadora:

Fonte de competência para aprovação:

Data da decisão:

Data de efeito:

Conteúdo integral aprovado:

Evidências/revisões:

A regra ordinária de não autovalidação permanece aplicável às alterações posteriores quando exigida pela norma vigente.

Nenhuma função deve ficar vinculada permanentemente a uma pessoa nominal: titulares podem ser regularmente substituídos ou sucedidos.

---

# 14. AUTORIDADES EXTERNAS E RESERVADAS

O projeto não fabrica competência legal, regulatória, pública, contratual, profissional, científica ou de terceiro.

| Matéria reservada | Fonte externa | Escopo afetado | Evidência exigida | Tratamento enquanto pendente |
|---|---|---|---|---|
| | | | | |

Na ausência de autoridade externa obrigatória, conter o menor escopo material possível. O restante do projeto pode evoluir quando seguro e autorizado.

---

# 15. HOLD, BLOCKED E RELEASE

Todo bloqueio deve registrar:

Identificador:

Estado:

- [ ] OPEN
- [ ] HOLD
- [ ] BLOCKED
- [ ] RELEASED
- [ ] REJECTED
- [ ] OUT_OF_SCOPE
- [ ] REVOKED

Causa:

Escopo afetado:

Autoridade competente para resolver:

Condição objetiva de liberação:

Evidência necessária:

Atividades que podem continuar:

Data/revisão:

Nenhum `HOLD` ou `BLOCKED` interno deve existir sem caminho documentado de resolução. Auditoria/IG registra achado; somente autoridade competente produz transição decisória.

---

# 16. ARMADILHAS DE CONTEXTO PROIBIDAS

Não constituem autoridade por si mesmas:

- memória de conversa;
- presença em reunião;
- autoria de código ou documento;
- posse do repositório;
- commit isolado;
- implementação existente;
- costume não documentado;
- silêncio;
- passagem do tempo;
- recomendação de IA;
- interpretação de agente;
- nome informal de papel.

Todo ato material deve declarar autoridade humana, capacidade, objeto, escopo, decisão, evidência, reservas, data de efeito e executor quando aplicável.

---

# 17. CONTINUIDADE E EVOLUÇÃO

Bloqueio local não paralisa automaticamente o projeto inteiro.

Podem continuar, quando não materialmente dependentes do bloqueio e dentro de autorização aplicável:

- pesquisa;
- auditoria;
- documentação;
- testes;
- produção de evidência;
- implementação isolada/não ativada;
- preparação de rollback;
- funções não afetadas.

Mudança de arquitetura, tecnologia, SSoT, equipe, agente, titular, repositório, branch, nome, versão ou estratégia não reabre o Evento de Constituição Inicial quando houver continuidade material.

---

# 18. MISSÃO

Missão do projeto:

Limites não negociáveis:

---

# 19. OBJETIVOS FUNDAMENTAIS

1.
2.
3.

---

# 20. PRIORIDADES ESTRATÉGICAS

1.
2.
3.

---

# 21. RESTRIÇÕES OPERACIONAIS

Restrições:

---

# 22. CRITÉRIOS DE SUCESSO

Critérios:

---

# 23. APROVAÇÃO, VIGÊNCIA E IDENTIDADE DO CONTEÚDO

Este bloco é a fonte documental autoritativa do estado desta Constituição de Projeto, sem possuir autoridade própria para criar o ato que registra.

Identificação canônica:

Versão constitucional:

Hash/commit/referência integral do conteúdo aprovado:

Tipo de ciclo:

- [ ] CONSTITUIÇÃO INICIAL
- [ ] ALTERAÇÃO ORDINÁRIA

Resultado constitucional aplicável:

- [ ] RATIFICAÇÃO INICIAL COMPATÍVEL
- [ ] VALIDAÇÃO ORDINÁRIA COMPATÍVEL
- [ ] INCOMPATÍVEL
- [ ] INDETERMINADO

Declaração explícita de aprovação/rejeição:

Autoridade responsável:

Capacidade exercida:

Fonte da competência:

Data da decisão:

Data de entrada em vigor:

Versão predecessora:

Data de término da vigência predecessora:

Estado:

- [ ] APROVADA / VIGENTE
- [ ] REJEITADA
- [ ] SUSPENSA
- [ ] REVOGADA
- [ ] SUBSTITUÍDA

Justificativa/evidência:

Versões não aprovadas não possuem autoridade operacional.

---

# 24. REGISTRO DE ALTERAÇÕES E ATOS

| ID | Data | Tipo | Autoridade/capacidade | Objeto | Decisão | Evidência | Efeito |
|---|---|---|---|---|---|---|---|
| | | | | | | | |

O registro preserva história; não fabrica autoridade nem altera estado por si só.

---

# 25. REGRA DE PRECEDÊNCIA

Em caso de conflito:

1. Constituição ICFACTORY;
2. autoridade externa obrigatória dentro de sua matéria legítima;
3. normas vigentes do framework aplicáveis;
4. Constituição vigente do Projeto;
5. decisões válidas da ASP e autoridades delegadas dentro do escopo;
6. contratos de execução;
7. recomendações, auditorias e observações.

Recomendação nunca prevalece sobre autoridade normativa/decisória competente.

---

# 26. REGRA DE TRANSIÇÃO v0.5 → v0.6

Se este candidato vier a ser promulgado:

- v0.6 substitui prospectivamente o Template v0.5 na data declarada pelo ato custodial;
- v0.5 permanece preservado no histórico;
- Constituições já vigentes não são automaticamente invalidadas, reescritas ou reclassificadas;
- projetos podem adotar/remediar estrutura segundo regra de transição expressamente autorizada;
- nenhum ato passado adquire legitimidade retroativa;
- nenhuma autoridade de projeto concreto surge apenas pela promulgação do template;
- o primeiro Evento de Constituição Inicial de projeto somente pode ocorrer mediante ato competente específico para esse projeto.

---

# 27. STATUS DESTE CANDIDATO

`TEMPLATE_0_6_CANDIDATE=PREPARED`

`PREDECESSOR_0_5=UNCHANGED_AND_IN_FORCE`

`PCIP_01_DEPENDENCY=YES`

`PROMULGATED=NO`

`PROJECT_AUTHORITY_CREATED=NO`

`RETROACTIVE_EFFECT=NO`

`INTELLIGENCE_IS_AUTHORITY=NO`
