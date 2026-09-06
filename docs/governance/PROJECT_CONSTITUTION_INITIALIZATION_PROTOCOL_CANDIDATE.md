# ICFACTORY — PROJECT CONSTITUTION INITIALIZATION AND PROJECT AUTHORITY PROTOCOL

**Identificação:** PCIP-01-CANDIDATE  
**Revisão candidata:** 0.3  
**Natureza:** Proposta normativa prospectiva para eliminar bootstrap recursivo, lacunas de autoridade interna, dependência nominal e armadilhas de contexto em projetos ICFACTORY  
**Status:** CANDIDATE — NÃO VIGENTE — NÃO PROMULGADO  
**Escopo:** Framework ICFACTORY; futuras Constituições iniciais e cadeia ordinária de autoridade interna dos projetos  

## 1. Problema

O regime ordinário do `PROJECT_CONSTITUTION_TEMPLATE` exige autoridade de elaboração, validação constitucional, aprovação e custódia com competência e proveniência preexistentes. Quando aplicado à primeira Constituição de um projeto cuja governança ainda não foi constituída, esse requisito pode produzir regressão recursiva.

Além disso, mesmo após a constituição inicial, um projeto pode voltar a travar se chegar a uma decisão material — arquitetura, implementação, migração, ativação, cutover, release, suspensão, rollback, delegação, sucessão ou outra decisão interna nova — sem autoridade previamente identificada para decidir.

O ICFACTORY deve possuir uma solução permanente, geral, auditável e aplicável por terceiro sem depender de contexto oculto, memória conversacional, identidade pessoal fixa ou inferência de autoridade.

## 2. Princípio de solução

Cada projeto ICFACTORY poderá possuir exatamente um **Evento de Constituição Inicial**.

O Evento de Constituição Inicial não reutiliza a capacidade originária excepcional do BOOTSTRAP-01. É um ato ordinário prospectivo praticado por função competente regularmente constituída na cadeia vigente do ICFACTORY, com proveniência própria.

O Evento deve criar uma cadeia de governança de projeto suficientemente completa para impedir novas lacunas internas previsíveis de autoridade durante o ciclo de vida do projeto.

## 3. Modelo mínimo de três elementos

A governança operacional do projeto deve distinguir, no mínimo, três elementos:

### 3.1 Autoridade Soberana do Projeto — ASP

Função humana institucional do projeto, independente da pessoa que a ocupa, responsável pela decisão final sobre matérias internas que não estejam reservadas por autoridade superior, externa ou especializada aplicável.

A ASP existe como **papel**, não como nome de pessoa.

O titular inicial, sucessor, substituto, delegado ou ocupante temporário deve ser identificado por ato próprio, mas o protocolo não fecha a função em torno de qualquer indivíduo específico.

### 3.2 Inteligência de Governança — IG

Função informativa exercida por IA, assistente, auditor, mecanismo analítico ou combinação destes, destinada a analisar contexto, identificar riscos e lacunas, executar revisão adversarial, propor alternativas, verificar rastreabilidade, preparar contratos/evidências e alertar sobre reservas externas.

A IG não possui autoridade decisória, de transição, aprovação, liberação ou execução por si mesma.

### 3.3 Agente de Execução — AE

Agente, ferramenta, automação, pessoa executora ou combinação destes que realiza apenas ações expressamente autorizadas dentro de escopo identificável.

O AE não infere autoridade, não amplia escopo, não transforma recomendação em ordem e deve produzir resultado e evidência de execução.

## 4. Poderes internos da ASP

Salvo reserva constitucional, legal, regulatória, contratual, profissional, científica ou externa aplicável, a ASP deve possuir **todos os poderes internos necessários à continuidade, evolução, contenção e encerramento do projeto**.

Esses poderes incluem, sem se limitar a:

- definir e alterar identidade, missão e escopo do projeto;
- definir, alterar, aprovar, rejeitar ou retirar requisitos;
- definir prioridades;
- decidir arquitetura e evolução arquitetural;
- definir semântica operacional interna quando não reservada externamente;
- selecionar, substituir ou descontinuar fonte interna de verdade;
- autorizar, negar, suspender ou revogar implementação;
- autorizar, negar, suspender ou revogar mudança técnica;
- autorizar, negar, suspender ou revogar migração;
- autorizar, negar, suspender ou revogar ativação;
- autorizar, negar, suspender ou revogar cutover;
- autorizar, negar, suspender ou revogar release;
- autorizar rollback;
- suspender e retomar operação;
- aceitar, rejeitar, conter ou transferir risco interno dentro de sua competência;
- decidir emergências internas;
- declarar escopo `OUT_OF_SCOPE`;
- encerrar o projeto;
- criar, alterar, fundir, suspender ou extinguir papéis subordinados internos;
- designar, substituir, remover ou reconduzir titulares de papéis internos;
- delegar competências internas total ou parcialmente;
- revogar delegações;
- autorizar subdelegação quando expressamente permitido;
- designar substituto temporário;
- designar sucessor;
- criar mecanismos de continuidade e contingência de autoridade.

A competência para decidir não equivale à decisão positiva.

`AUTHORITY_TO_DECIDE != DECISION_TO_PROCEED`.

## 5. Regra de fechamento de lacuna interna

Nenhuma nova categoria de decisão interna poderá produzir vacância indefinida de autoridade.

Se uma matéria interna relevante surgir e nenhuma função especializada possuir competência explicitamente vigente, a competência decisória interna retorna à ASP por regra de fechamento, desde que a matéria não esteja reservada por autoridade superior ou externa aplicável.

A regra de fechamento elimina vacância interna; não fabrica competência externa.

## 6. Delegação sem aprisionamento nominal

A ASP pode delegar poderes internos para uma ou mais funções ou pessoas, de modo permanente, temporário, condicionado ou por escopo.

Toda delegação deve declarar:

- delegante;
- delegado;
- competência delegada;
- escopo;
- limites;
- início de vigência;
- condição de término ou duração;
- possibilidade ou proibição de subdelegação;
- poder de revogação;
- efeitos sobre decisões em curso.

Por padrão:

- delegação não elimina a existência da ASP;
- delegação não amplia a matéria além da competência original;
- delegação é revogável, salvo instrumento válido que disponha diferentemente;
- silêncio não cria subdelegação;
- um titular pode acumular funções, desde que cada capacidade exercida permaneça identificável;
- nenhuma função fica eternamente vinculada a um nome.

## 7. Sucessão, substituição e vacância

A estrutura deve permitir troca de pessoas sem reconstrução constitucional do projeto.

A ASP pode designar:

- sucessor;
- substituto temporário;
- autoridade em exercício;
- cadeia de contingência;
- condições objetivas de assunção.

A mudança de titular não cria novo projeto, não reabre o Evento de Constituição Inicial e não exige reescrever toda a Constituição.

Se houver vacância inesperada e nenhum sucessor válido estiver definido, a autoridade instituidora superior competente poderá designar novo titular da ASP por ato ordinário prospectivo, sem reutilizar o bootstrap originário e sem produzir retroatividade.

## 8. Regra HOLD / RELEASE

A autoridade competente para o escopo deve poder colocar qualquer matéria interna em `HOLD` e retirar o `HOLD` quando os critérios aplicáveis estiverem satisfeitos ou quando o risco puder ser legitimamente aceito dentro da competência correspondente.

Estados mínimos:

- `OPEN`
- `HOLD`
- `RELEASED`
- `REJECTED`
- `OUT_OF_SCOPE`
- `REVOKED`

`HOLD` não transfere autoridade para IA, auditor ou agente.

`RELEASED` exige ato humano explícito da autoridade competente.

## 9. Autoridade instituidora do Evento de Constituição Inicial

A autoridade instituidora deve ser demonstrada por instrumento vigente anterior ao ato.

Quando utilizada a Camada Soberana de Governança, sua competência permanece limitada à competência ordinária já constituída para sustentar formação e continuidade da cadeia, instituir ou reconhecer funções subordinadas, definir competências e escopos e designar titulares.

O Evento não converte a Camada Soberana em autoridade operacional automática do projeto.

## 10. Efeitos permitidos do Evento de Constituição Inicial

O Evento poderá:

1. identificar inequivocamente o projeto;
2. instituir a ASP como função humana institucional;
3. designar seu titular inicial;
4. definir poderes, limites e reservas da ASP;
5. criar funções subordinadas adicionais;
6. designar seus titulares;
7. instituir IG e AE sem autoridade decisória própria;
8. estabelecer mecanismo de delegação, sucessão e contingência;
9. identificar a primeira Constituição de Projeto candidata;
10. declarar a matriz inicial de autoridades reservadas;
11. registrar a transição para governança ordinária.

## 11. Constituição inicial sem dependência obrigatória de terceiro nominal

A primeira Constituição não deve depender da disponibilidade permanente de uma segunda pessoa específica, auditor externo fixo ou titular nominal predeterminado para existir.

A solução definitiva deve distinguir:

- **revisão/adversarialidade**, que pode ser produzida por IG, auditoria, agente, ferramenta ou humano sem adquirir autoridade;
- **decisão constitucional**, que permanece humana e vinculada à função competente.

Para o primeiro ciclo constitucional, a proposta candidata admite **Ratificação Constitucional Inicial pela ASP**, após revisão adversarial documentada e verificação explícita de compatibilidade com a Constituição ICFACTORY, quando o ato instituidor tiver conferido essa competência à ASP.

Essa ratificação inicial:

- não cria autoridade externa;
- não transforma IA ou auditor em autoridade;
- não se aplica retroativamente;
- não exige auditor humano externo permanente como condição automática;
- não impede revisão independente quando ela for útil, contratual, institucional ou externamente exigida;
- não pode ser reutilizada para reinicializar a governança após a primeira Constituição válida.

Alterações constitucionais posteriores devem seguir o regime ordinário vigente aplicável, mas esse regime não deve criar dependência nominal perpétua nem bloquear a evolução por ausência de uma pessoa específica quando a própria governança puder designar outra autoridade competente.

## 12. Autoridades externas e especializadas

O ICFACTORY não cria autoridade legal, regulatória, científica, profissional ou pública por decisão interna.

Quando uma questão concreta depender de autoridade externa ou especializada obrigatória:

- a reserva deve ser identificada;
- o escopo bloqueado deve ser o menor possível;
- o restante do projeto não deve ser bloqueado automaticamente;
- a ASP pode conter, retirar, reformular ou declarar a matéria `OUT_OF_SCOPE`;
- a ausência de validação obrigatória não deve ser convertida em paralisação global se houver isolamento seguro do escopo afetado.

## 13. Armadilhas de contexto proibidas

Nenhum projeto poderá depender de contexto oculto para saber quem decide, quem executa ou o que está autorizado.

São proibidas como fundamento exclusivo:

- memória de conversa;
- nome informal de papel;
- presença em reunião;
- autoria de código;
- posse de repositório;
- commit isolado;
- implementação já realizada;
- costume não documentado;
- silêncio;
- passagem do tempo;
- recomendação de IA;
- interpretação de agente;
- frase ambígua sem escopo identificável.

Todo ato material deve declarar pelo menos autoridade humana, capacidade exercida, objeto, escopo, decisão, evidência considerada, condições/reservas, data de efeito e executor autorizado quando houver.

## 14. Prevenção de travamento por ambiguidade

1. ambiguidade sobre autoridade interna é resolvida pela regra de fechamento da ASP;
2. ambiguidade sobre autoridade externa gera contenção apenas do escopo afetado;
3. ausência de contexto gera pedido de evidência ou decisão humana, não inferência;
4. todo `BLOCKED` ou `HOLD` deve identificar causa, escopo, autoridade que pode resolver e condição de liberação;
5. nenhuma auditoria cria autoridade ou bloqueio por opinião própria;
6. nenhum agente cria novo gate por interpretação;
7. nenhum projeto deve depender permanentemente de pessoa nominal específica quando a função puder ser regularmente reassumida, delegada ou sucedida.

## 15. Continuidade de desenvolvimento

Quando um escopo estiver bloqueado, atividades não dependentes desse bloqueio podem continuar, incluindo pesquisa, auditoria, testes, documentação, implementação isolada e não ativada quando autorizada, preparação de rollback e produção de evidência.

O bloqueio alcança somente atividades materialmente dependentes da decisão ou autoridade ausente/reservada.

## 16. Evolução sem reconstrução constitucional

Mudança de arquitetura, tecnologia, SSoT, equipe, agente, titular, repositório, branch, nome, versão ou estratégia não exige novo Evento de Constituição Inicial quando houver continuidade material do mesmo projeto.

A governança deve permitir evolução por decisões ordinárias, delegações, sucessões e alterações válidas, sem reiniciar a cadeia de autoridade.

## 17. Consumação por projeto

Após a entrada em vigor da primeira Constituição válida, o Evento de Constituição Inicial considera-se consumado para aquela identidade material e não poderá ser usado para apagar ou reinicializar a governança.

## 18. IA e agentes

IA, agentes, Harnesses e ferramentas podem auxiliar na elaboração, auditoria, revisão adversarial, análise, recomendação, execução autorizada e produção de evidência.

Não possuem autoridade humana, constitucional, regulatória ou decisória por participação.

Modelo operacional:

`HUMAN_AUTHORITY_DECIDES -> GOVERNANCE_INTELLIGENCE_CHECKS/ADVISES -> EXECUTION_AGENT_EXECUTES -> EVIDENCE_RETURNS_TO_HUMAN_AUTHORITY`.

## 19. Gate adversarial obrigatório antes da promulgação do protocolo

Antes de qualquer promulgação deste protocolo, a revisão adversarial deve tentar demonstrar pelo menos:

1. regressão infinita de autoridade;
2. vacância futura de autoridade interna;
3. aprisionamento em pessoa nominal específica;
4. impossibilidade de delegação ou sucessão;
5. possibilidade de autolegitimação ilimitada;
6. reutilização indevida do BOOTSTRAP-01;
7. conflito com SG-01, SG-02 ou SG-03;
8. bypass de autoridade externa;
9. bloqueio global por questão local;
10. `HOLD` sem caminho de resolução;
11. `RELEASE` sem autoridade humana competente;
12. contexto oculto necessário à aplicação;
13. agente inferindo autoridade;
14. IA adquirindo poder decisório;
15. arquitetura congelada;
16. impossibilidade de migração, ativação, cutover, rollback ou release por lacuna interna;
17. impossibilidade de substituição do titular sem reconstrução constitucional;
18. impossibilidade de terceiro aplicar o protocolo apenas pelos documentos canônicos.

Falha material em qualquer item bloqueia a promulgação do **protocolo**, não a continuidade automática de todo projeto não afetado.

## 20. Regra de incorporação

Este documento permanece candidato e não altera, por sua simples existência, `CONSTITUTION.md`, `PROJECT_CONSTITUTION_TEMPLATE.md`, `CONSTITUTIONAL_LEXICON.md`, BOOTSTRAP-01 ou qualquer Constituição de Projeto.

A incorporação definitiva exige processo normativo competente, decisão expressa da autoridade metodológica competente e atualização rastreável dos documentos afetados.

Nenhum projeto, inclusive o Sistema de Monitoramento de Águas, recebe autoridade nova enquanto esta proposta não adquirir vigência.
