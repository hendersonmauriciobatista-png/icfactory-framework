# ICFACTORY — PROJECT CONSTITUTION INITIALIZATION AND PROJECT AUTHORITY PROTOCOL

**Identificação:** PCIP-01-CANDIDATE  
**Revisão candidata:** 0.2  
**Natureza:** Proposta normativa prospectiva para eliminar bootstrap recursivo, lacunas de autoridade interna e armadilhas de contexto em projetos ICFACTORY  
**Status:** CANDIDATE — NÃO VIGENTE — NÃO PROMULGADO  
**Escopo:** Framework ICFACTORY; futuras Constituições iniciais e cadeia ordinária de autoridade interna dos projetos  

## 1. Problema

O regime ordinário do `PROJECT_CONSTITUTION_TEMPLATE` exige autoridade de elaboração, validação constitucional, aprovação e custódia com competência e proveniência preexistentes. Quando aplicado à primeira Constituição de um projeto cuja governança ainda não foi constituída, esse requisito pode produzir regressão recursiva.

Além disso, mesmo após a constituição inicial, um projeto pode voltar a travar se chegar a uma decisão material — arquitetura, implementação, migração, ativação, cutover, release, suspensão, rollback ou outra decisão interna nova — sem autoridade previamente identificada para decidir.

O ICFACTORY deve possuir uma solução permanente, geral, auditável e aplicável por terceiro sem depender de contexto oculto, memória conversacional ou inferência de autoridade.

## 2. Princípio de solução

Cada projeto ICFACTORY poderá possuir exatamente um **Evento de Constituição Inicial**.

O Evento de Constituição Inicial não reutiliza a capacidade originária excepcional do BOOTSTRAP-01. É um ato ordinário prospectivo praticado por função competente regularmente constituída na cadeia vigente do ICFACTORY, com proveniência própria.

O Evento deve criar uma cadeia de governança de projeto suficientemente completa para impedir novas lacunas internas previsíveis de autoridade durante o ciclo de vida do projeto.

## 3. Modelo mínimo de três elementos

A governança operacional do projeto deve distinguir, no mínimo, três elementos:

### 3.1 Autoridade Humana Soberana do Projeto — AHSP

Pessoa humana identificada, regularmente designada, responsável pela decisão final sobre matérias internas do projeto que não estejam reservadas por autoridade superior, externa ou especializada aplicável.

A AHSP é a autoridade interna de fechamento decisório do projeto.

### 3.2 Inteligência de Governança — IG

Função informativa exercida por IA, assistente, auditor, mecanismo analítico ou combinação destes, destinada a:

- analisar contexto;
- identificar riscos e lacunas;
- executar revisão adversarial;
- propor alternativas;
- classificar materialidade de forma não vinculante;
- verificar rastreabilidade;
- preparar contratos, evidências e recomendações;
- alertar sobre autoridade externa ou especializada possivelmente aplicável.

A IG não possui autoridade de decisão, transição, aprovação, liberação ou execução por si mesma.

### 3.3 Agente de Execução — AE

Agente, ferramenta, automação, pessoa executora ou combinação destes que realiza apenas ações expressamente autorizadas dentro de escopo identificável.

O AE:

- não infere autoridade;
- não amplia escopo;
- não transforma recomendação em ordem;
- não executa além do contrato autorizado;
- deve produzir resultado e evidência de execução;
- deve parar diante de conflito material não resolvido ou comando fora do escopo.

## 4. Autoridade Humana Soberana do Projeto

O Evento de Constituição Inicial deverá instituir ou reconhecer a AHSP e designar seu titular humano.

Salvo reserva explícita aplicável, a AHSP possui competência interna para decidir, autorizar, negar, suspender, retomar, revogar, substituir, conter ou liberar matérias do ciclo de vida do projeto, incluindo:

- identidade e escopo do produto;
- requisitos;
- prioridades;
- arquitetura do projeto;
- semântica e significado operacional de dados quando não reservados a autoridade externa ou especializada;
- seleção da fonte interna de verdade do projeto;
- implementação;
- mudança técnica;
- migração reversível ou irreversível, observadas as reservas aplicáveis;
- ativação;
- desativação;
- cutover;
- rollback;
- release;
- suspensão operacional;
- retomada operacional;
- aceitação ou rejeição de risco interno;
- decisões emergenciais;
- contenção;
- declaração de fora de escopo;
- submissão externa quando a submissão em si não depender de autoridade externa distinta;
- encerramento do projeto.

A competência para decidir não equivale à decisão positiva.

`AUTHORITY_TO_DECIDE != DECISION_TO_PROCEED`.

A AHSP pode possuir autoridade de cutover enquanto o cutover permanece `PENDING`, `NO` ou `BLOCKED` por evidência insuficiente.

## 5. Regra de fechamento de lacuna interna de autoridade

Nenhuma nova categoria de decisão **interna do projeto** poderá produzir vacância indefinida de autoridade.

Se uma matéria interna relevante surgir e nenhuma função especializada do projeto possuir competência explicitamente vigente para ela, a competência decisória interna retorna à AHSP por regra de fechamento, desde que a matéria não esteja reservada por:

1. Constituição ICFACTORY;
2. autoridade normativa do próprio framework;
3. legislação ou regulamentação aplicável;
4. autoridade pública competente;
5. obrigação contratual ou institucional vinculante;
6. responsabilidade profissional legalmente reservada;
7. autoridade científica, técnica ou de domínio que tenha sido classificada como obrigatória para a questão concreta;
8. direito legítimo de terceiro.

A regra de fechamento elimina vacância interna; ela não fabrica competência externa.

## 6. Regra HOLD / RELEASE

A AHSP deve possuir poder explícito para colocar qualquer escopo interno do projeto em `HOLD` e para retirar o `HOLD` quando os critérios de liberação aplicáveis estiverem satisfeitos ou quando o risco for legitimamente aceito dentro de sua competência.

Estados mínimos:

- `OPEN`
- `HOLD`
- `RELEASED`
- `REJECTED`
- `OUT_OF_SCOPE`
- `REVOKED`

`HOLD` não transfere autoridade para IA, auditor ou agente.

`RELEASED` exige ato humano explícito da autoridade competente para o escopo.

Quando houver reserva externa ou especializada obrigatória, a AHSP não pode liberar a matéria contrariando essa reserva; pode, porém, reduzir escopo, conter, retirar a funcionalidade, declarar `OUT_OF_SCOPE` ou manter o restante do projeto em evolução.

## 7. Autoridade instituidora do Evento de Constituição Inicial

A autoridade instituidora deve ser demonstrada por instrumento vigente anterior ao ato.

Quando utilizada a Camada Soberana de Governança, sua competência permanece limitada à competência ordinária já constituída para sustentar formação e continuidade da cadeia de autoridade, instituir ou reconhecer funções subordinadas, definir competências e escopos e designar titulares.

O Evento não converte a Camada Soberana em autoridade operacional automática do projeto.

## 8. Efeitos permitidos do Evento de Constituição Inicial

O Evento poderá:

1. identificar inequivocamente o projeto;
2. instituir ou reconhecer a AHSP;
3. designar o titular humano da AHSP;
4. instituir funções especializadas internas adicionais quando necessárias;
5. definir competência, escopo, precedência e limites de cada função;
6. instituir a IG como função informativa sem autoridade;
7. instituir o AE como função executora sem autoridade decisória;
8. identificar a primeira Constituição de Projeto candidata;
9. estabelecer a proveniência prospectiva dos papéis constituídos;
10. declarar a matriz inicial de autoridades reservadas;
11. registrar a transição para governança ordinária do projeto.

## 9. Constituição inicial e prevenção do loop de autovalidação

A Constituição inicial é caso de nascimento da cadeia e deve possuir disciplina própria, distinta da alteração constitucional ordinária posterior.

A proposta permanente deverá, antes de promulgação, resolver explicitamente a incompatibilidade entre:

- necessidade de uma primeira Constituição válida;
- proibição ordinária de autovalidação de conteúdo de própria autoria;
- ausência possível de segunda autoridade humana previamente constituída no nascimento do projeto.

Para o **primeiro ciclo constitucional apenas**, admite-se como hipótese normativa candidata uma **Ratificação Constitucional Inicial** pela AHSP após revisão adversarial documentada pela IG e verificação de compatibilidade com a Constituição ICFACTORY, desde que o ato fundador competente tenha constituído a AHSP para esse fim.

Essa hipótese:

- não está vigente enquanto este candidato não for promulgado;
- não se aplica retroativamente;
- não vale para alterações constitucionais ordinárias posteriores;
- não transforma IA ou auditor em autoridade;
- não dispensa evidência de compatibilidade constitucional;
- não pode ser reutilizada após a primeira Constituição válida do projeto.

A promulgação definitiva deste protocolo deverá declarar expressamente se esta hipótese substitui, apenas no primeiro ciclo, a regra ordinária de autovalidação do template.

## 10. Autoridades externas e especializadas

O ICFACTORY não cria autoridade legal, regulatória, científica, profissional ou pública por decisão interna.

Quando uma questão concreta depender de autoridade externa ou especializada obrigatória:

- a reserva deve ser identificada;
- o escopo bloqueado deve ser o menor possível;
- o restante do projeto não deve ser bloqueado automaticamente;
- a AHSP pode conter, retirar, reformular ou declarar a matéria `OUT_OF_SCOPE`;
- a ausência de validação obrigatória não deve ser convertida em paralisação global se houver isolamento seguro do escopo afetado.

## 11. Armadilhas de contexto proibidas

Nenhum projeto ICFACTORY poderá depender de contexto oculto para saber quem decide, quem executa ou o que está autorizado.

São proibidas como fundamento decisório exclusivo:

- memória de conversa;
- nome informal de papel;
- presença em reunião;
- autoria de código;
- posse do repositório;
- commit Git isolado;
- implementação já realizada;
- costume não documentado;
- silêncio;
- passagem do tempo;
- recomendação de IA;
- interpretação de agente;
- frase ambígua sem escopo identificável.

Todo ato material deve declarar pelo menos:

- autoridade humana;
- capacidade exercida;
- objeto;
- escopo;
- decisão;
- evidência considerada;
- condições ou reservas;
- data de efeito;
- executor autorizado, quando houver;
- critério de encerramento ou revisão quando aplicável.

## 12. Prevenção de travamento por ambiguidade

Ambiguidade não deve gerar expansão de autoridade nem bloqueio global automático.

Regras:

1. ambiguidade sobre autoridade **interna** é resolvida pela regra de fechamento da AHSP;
2. ambiguidade sobre autoridade **externa ou reservada** gera contenção apenas do escopo afetado até classificação;
3. ausência de contexto suficiente gera pedido de evidência ou decisão humana, não inferência;
4. um bloqueio deve identificar causa, escopo, autoridade competente para resolvê-lo e condição objetiva de liberação;
5. nenhum `BLOCKED` ou `HOLD` pode existir sem um caminho de resolução documentado, salvo impedimento externo material não controlável pelo projeto;
6. nenhuma auditoria pode criar bloqueio de autoridade por simples opinião; ela registra achado e encaminha à autoridade competente;
7. nenhum agente pode criar um novo gate por interpretação própria.

## 13. Continuidade de desenvolvimento

Governança deve controlar risco sem impedir evolução desnecessariamente.

Quando um escopo estiver bloqueado:

- pesquisa pode continuar;
- auditoria pode continuar;
- implementação isolada e não ativada pode continuar quando explicitamente autorizada;
- testes podem continuar;
- documentação pode continuar;
- funções não afetadas podem continuar;
- preparação de rollback pode continuar;
- evidência necessária ao desbloqueio pode ser produzida.

O bloqueio só alcança atividades que dependam materialmente da decisão ou autoridade ausente/reservada.

## 14. Evolução da própria arquitetura de projeto

A Constituição inicial não deve congelar a arquitetura para sempre.

A AHSP pode decidir evolução arquitetural, mudança de SSoT, substituição de componente, migração e reorganização interna por decisão material formal, preservando rastreabilidade, risco, rollback e autoridades reservadas aplicáveis.

Mudança arquitetural não exige novo Evento de Constituição Inicial.

## 15. Consumação por projeto

Para cada identidade material de projeto, somente um Evento de Constituição Inicial poderá produzir efeito.

Após a entrada em vigor da primeira Constituição válida, o Evento considera-se consumado e não poderá ser reutilizado para reinicializar, contornar ou apagar a governança ordinária.

Mudança de nome, versão, branch, repositório, produto, titular ou arquitetura não reabre o Evento quando houver continuidade material do projeto.

## 16. IA e agentes

IA, agentes, Harnesses e ferramentas podem auxiliar na elaboração, auditoria, revisão adversarial, análise, recomendação, execução autorizada e produção de evidência.

Não possuem autoridade humana, constitucional, regulatória ou decisória por participação.

Modelo operacional:

`HUMAN_AUTHORITY_DECIDES -> GOVERNANCE_INTELLIGENCE_CHECKS/ADVISES -> EXECUTION_AGENT_EXECUTES -> EVIDENCE_RETURNS_TO_HUMAN_AUTHORITY`.

O fluxo pode possuir iterações, mas a autoridade decisória humana permanece identificável.

## 17. Gate adversarial obrigatório

Antes de qualquer promulgação, a revisão adversarial deve tentar demonstrar pelo menos:

1. regressão infinita de autoridade;
2. vacância futura de autoridade interna;
3. possibilidade de autolegitimação ilimitada;
4. reutilização indevida do BOOTSTRAP-01;
5. conflito com SG-01, SG-02 ou SG-03;
6. bypass de autoridade externa ou especializada;
7. bloqueio global por questão local;
8. `HOLD` sem caminho de resolução;
9. `RELEASE` sem autoridade humana competente;
10. contexto oculto necessário à aplicação;
11. agente inferindo autoridade;
12. IA adquirindo poder decisório por participação;
13. arquitetura congelada por ausência de competência de evolução;
14. impossibilidade de migração, ativação, cutover, rollback ou release por lacuna interna;
15. impossibilidade de terceiro aplicar o protocolo a partir somente dos documentos canônicos.

Falha material em qualquer item bloqueia promulgação.

## 18. Regra de incorporação

Este documento permanece candidato e não altera, por sua simples existência, `CONSTITUTION.md`, `PROJECT_CONSTITUTION_TEMPLATE.md`, `CONSTITUTIONAL_LEXICON.md`, BOOTSTRAP-01 ou qualquer Constituição de Projeto.

A incorporação definitiva exige processo normativo competente, revisão/gates aplicáveis, decisão expressa da autoridade metodológica competente e atualização rastreável dos documentos afetados.

Nenhum projeto, inclusive o Sistema de Monitoramento de Águas, recebe autoridade nova enquanto esta proposta não adquirir vigência.
