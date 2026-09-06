# ICFACTORY — PROJECT CONSTITUTION INITIALIZATION PROTOCOL

**Identificação:** PCIP-01-CANDIDATE  
**Natureza:** Proposta normativa prospectiva para eliminação do bootstrap recursivo de Constituições de Projeto  
**Status:** CANDIDATE — NÃO VIGENTE — NÃO PROMULGADO  
**Escopo:** Framework ICFACTORY; futuras Constituições iniciais de projetos  

## 1. Problema

O regime ordinário do `PROJECT_CONSTITUTION_TEMPLATE` exige autoridade de elaboração, validação constitucional, aprovação e custódia com competência e proveniência preexistentes. Quando aplicado à primeira Constituição de um projeto cuja governança ainda não foi constituída, esse requisito pode produzir regressão recursiva: a Constituição depende de autoridades que dependeriam da própria Constituição para existir.

O ICFACTORY deve possuir uma solução permanente, geral e auditável para esse nascimento, sem criar exceções específicas por projeto e sem reutilizar a capacidade originária excepcional consumida pelo BOOTSTRAP-01.

## 2. Princípio de solução

Cada projeto ICFACTORY poderá possuir exatamente um **Evento de Constituição Inicial**.

O Evento de Constituição Inicial não é uma reutilização do BOOTSTRAP-01. Ele é um ato ordinário prospectivo praticado por função competente regularmente constituída na cadeia vigente do ICFACTORY, com proveniência própria, destinado exclusivamente a formar a primeira cadeia de governança do projeto.

## 3. Autoridade instituidora

A autoridade instituidora do Evento de Constituição Inicial deve ser demonstrada por instrumento vigente anterior ao ato.

Quando utilizada a Camada Soberana de Governança, sua competência limita-se àquela já regularmente constituída para sustentar a formação e continuidade da cadeia ordinária de autoridade, instituir ou reconhecer funções subordinadas, definir seus escopos e designar titulares.

A posição soberana não absorve competência ausente, não cria competência técnica, científica, regulatória, operacional ou de domínio e não autoriza automaticamente decisões específicas de produto, implementação, migração, ativação, cutover ou release.

## 4. Efeitos permitidos

O Evento de Constituição Inicial poderá exclusivamente:

1. identificar inequivocamente o projeto;
2. instituir ou reconhecer as funções iniciais de governança necessárias ao projeto;
3. definir competência e escopo de cada função constituída;
4. designar titulares humanos quando houver competência instituidora demonstrada para fazê-lo;
5. identificar a primeira Constituição de Projeto candidata;
6. estabelecer a proveniência prospectiva dos papéis constituídos;
7. registrar a transição para governança ordinária do projeto.

## 5. Efeitos proibidos

O Evento de Constituição Inicial não poderá, por si só:

- produzir legitimação retroativa;
- validar decisões históricas sem autoridade demonstrada;
- dispensar autoridade científica, técnica, regulatória, jurídica ou de domínio quando aplicável;
- autorizar implementação;
- autorizar migração de dados;
- autorizar ativação;
- autorizar cutover;
- autorizar release;
- autorizar submissão externa;
- transformar inteligência, IA, agente, auditor ou observador em autoridade;
- ampliar a competência da própria autoridade instituidora;
- criar governança paralela ao ICFACTORY.

## 6. Consumação por projeto

O mecanismo é reutilizável pelo framework, mas consumível por projeto.

Para cada identidade de projeto, somente um Evento de Constituição Inicial poderá produzir efeito.

Após a entrada em vigor da primeira Constituição válida do projeto, o mecanismo considera-se consumado para aquela identidade e não poderá ser invocado para alterar, substituir, contornar ou reinicializar sua governança.

Toda evolução posterior deverá seguir o ciclo constitucional ordinário vigente.

Mudança de nome, versão, branch, repositório, produto, titular ou arquitetura não reabre o Evento de Constituição Inicial se houver continuidade material do mesmo projeto.

## 7. Validação e autovalidação

A presente proposta não elimina nem reduz a proibição ordinária de autovalidação.

A elaboração, validação, aprovação e custódia permanecem funções constitucionalmente distinguíveis conforme os instrumentos vigentes.

O Evento de Constituição Inicial resolve exclusivamente a origem prospectiva da competência necessária para que essas funções possam existir no primeiro ciclo do projeto. Ele não converte a autoridade instituidora em autora, validadora ou aprovadora automática da Constituição criada.

Qualquer incompatibilidade de funções permanece sujeita às regras vigentes de proveniência, conflito de interesse, revisão e validação.

## 8. IA e elaboração material

IA, agentes, Harnesses, ferramentas e colaboradores podem auxiliar na redação, análise, auditoria e produção de evidências, mas sua participação material não lhes confere autoridade constitucional.

Toda autoridade exercida deverá permanecer humana, explícita, rastreável e vinculada a competência previamente demonstrada.

## 9. Requisitos mínimos do ato de inicialização

Cada Evento de Constituição Inicial deverá registrar, no mínimo:

- identificador único;
- identidade do projeto;
- autoridade instituidora e capacidade em que atua;
- fonte imediata da competência;
- ato de instituição/designação aplicável;
- data de efeito da competência;
- escopo exato do ato;
- funções de governança instituídas ou reconhecidas;
- competências e limites de cada função;
- titulares designados, quando aplicável;
- referência à Constituição candidata;
- declaração expressa de não retroatividade;
- declaração expressa das autoridades não concedidas;
- condição de consumação;
- evidências e referências verificáveis;
- data e efeito do ato.

## 10. Invariantes

O protocolo deve preservar integralmente:

- Autoridade Deve Ser Explícita;
- Governança Deve Ser Unificada;
- Observadores Não Governam;
- Evolução Auditável;
- Inteligência Não É Autoridade;
- SG-01 — Invariância de Autoridade;
- SG-02 — Continuidade de Vigência;
- SG-03 — Ordem de Dependência Constitucional;
- ausência de legitimação retroativa;
- separação entre evidência e governança.

## 11. Gate adversarial obrigatório

Antes de qualquer promulgação desta proposta, deve ser executada revisão adversarial explícita, limitada pelo menos às seguintes perguntas:

1. O protocolo viola qualquer artigo da Constituição ICFACTORY?
2. O protocolo reutiliza, reativa ou reproduz indevidamente a capacidade originária excepcional consumida pelo BOOTSTRAP-01?
3. O protocolo amplia a Camada Soberana além da competência ordinária já constituída?
4. O protocolo cria mecanismo permanente de autolegitimação ou bypass de autoridade?
5. O protocolo preserva SG-01, SG-02 e SG-03?
6. O protocolo preserva a proibição de retroatividade e autovalidação?
7. O protocolo pode ser aplicado por terceiro sem depender de contexto oculto?

Falha material em qualquer item bloqueia promulgação.

## 12. Regra de incorporação

Este documento é apenas candidato. Não altera `CONSTITUTION.md`, `PROJECT_CONSTITUTION_TEMPLATE.md`, `CONSTITUTIONAL_LEXICON.md`, BOOTSTRAP-01 ou qualquer Constituição de Projeto enquanto não houver processo normativo competente, revisão/gates aplicáveis, decisão expressa e incorporação documental rastreável.

Nenhum projeto, inclusive o Sistema de Monitoramento de Águas, recebe autoridade nova pela simples existência desta proposta.
