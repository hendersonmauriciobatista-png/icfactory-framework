# OG-001 — Sequenciamento Oficial das Ondas de Migração

**Identificação:** OG-001
**Versão:** 1.1
**Categoria:** Ordem de Governança
**Status:** Promovida — vigente
**Aplicabilidade:** Framework ICFACTORY
**Data de aprovação:** 2026-08-05 (America/Sao_Paulo)
**Vigência:** 2026-08-05
**Autoridade de aprovação:** Product Owner
**Proveniência da decisão:** Despacho de Promoção GP-OG-001, após auditoria metodológica GP-OG-001A, revisão documental GP-OG-001B e auditoria de conformidade GP-OG-001C

### Histórico de revisões

| Versão | Situação | Registro |
|---|---|---|
| 1.0 | Materialização inicial | Decisão metodológica aprovada na sessão de origem |
| 1.1 | Promovida — vigente | Correções documentais determinadas pela GP-OG-001B, certificação pela GP-OG-001C e promoção autorizada pelo Despacho de Promoção GP-OG-001 |

---

## 1. Objetivo

Estabelecer a norma metodológica oficial para governança da execução de ondas de migração de Baselines em projetos conduzidos segundo o método ICFACTORY.

Esta Ordem de Governança disciplina exclusivamente a sequência operacional das ondas de migração, preservando a separação entre planejamento estrutural e execução operacional.

Esta Ordem de Governança:

- não altera a Constituição ICFACTORY;
- não altera documentos estruturais (EP);
- não redefine arquitetura;
- não redefine classificações documentais;
- não amplia seu escopo além da execução operacional.

## 2. Motivação

Durante a execução da migração da Baseline 1.0 do projeto H&A CORE foi identificado que os documentos estruturais descrevem adequadamente:

- arquitetura;
- classificação dos artefatos;
- destino dos componentes;
- estratégia de migração.

Porém, esses documentos não possuem como responsabilidade definir a sequência operacional das ondas de execução.

A ausência dessa definição pode induzir diferentes executores a interpretações distintas. Esta Ordem de Governança elimina essa possibilidade.

## 3. Princípio da separação entre documentos estruturais e Ordens de Governança

No ICFACTORY existe separação obrigatória entre documentos estruturais e Ordens de Governança.

### 3.1 Documentos Estruturais (EP)

São responsáveis por definir:

- arquitetura;
- classificação;
- organização;
- destinos;
- estratégia documental.

Respondem à pergunta: **O que deve ser executado?**

### 3.2 Ordens de Governança (OG)

São responsáveis por definir:

- autorização;
- sequência operacional;
- controle da execução;
- critérios de encerramento.

Respondem à pergunta: **Quando e em que ordem executar?**

## 4. Princípio da não inferência operacional

Nenhum executor poderá inferir a ordem de execução de ondas a partir de documentos estruturais.

Caso a sequência operacional não esteja explicitamente definida por uma Ordem de Governança aprovada e autorizadora, a execução deverá ser imediatamente interrompida.

É expressamente proibido:

- presumir a próxima onda;
- criar sequência própria;
- reorganizar etapas;
- iniciar ondas por interpretação;
- alterar a estratégia documental definida pelos EPs.

## 5. Autoridade competente

A sequência operacional das ondas será definida pela autoridade competente do projeto, conforme a governança institucional aplicável.

A Ordem de Governança registra formalmente essa decisão para execução auditável.

Nenhuma onda posterior poderá ser iniciada antes do encerramento da onda anterior e da autorização formal da autoridade competente para a continuidade.

## 6. Ciclo oficial das ondas

Toda onda deverá obrigatoriamente obedecer ao seguinte fluxo:

1. autorização formal da autoridade competente;
2. execução exclusiva da onda autorizada;
3. auditoria técnica;
4. verificação do estado dos artefatos;
5. encerramento formal da onda;
6. autorização da próxima onda.

Nenhuma etapa poderá ser omitida.

Quando o projeto utilizar controle de versão baseado em Git, deverão ser observadas as etapas de versionamento e publicação definidas pela governança do projeto, incluindo, quando aplicáveis:

- verificação da árvore de trabalho (`git status`);
- preparação dos artefatos (`git add`);
- registro semântico (`git commit`);
- publicação (`git push`);
- validação do repositório remoto.

## 7. Ondas sem artefatos

Uma onda poderá resultar em:

- migração executada;
- migração parcial;
- migração sem artefatos elegíveis.

Os três resultados são considerados válidos.

É proibida a criação artificial de conteúdo com a finalidade de preencher ou completar uma onda.

## 8. Relação com os documentos estruturais

Esta Ordem de Governança não altera, complementa ou substitui documentos estruturais.

Os EPs permanecem como única fonte autoritativa para:

- classificação;
- destino;
- estratégia;
- arquitetura.

A OG disciplina exclusivamente a execução.

## 9. Aplicabilidade

Esta norma aplica-se igualmente a:

- executores humanos;
- agentes de IA;
- assistentes especializados;
- ferramentas automatizadas;
- pipelines de migração;
- qualquer executor compatível com o método ICFACTORY.

Todos os executores deverão apresentar comportamento operacional equivalente. A aplicação da norma independe do executor utilizado.

## 10. Critérios de conformidade

Será considerada não conforme qualquer execução que:

- inicie uma onda sem autorização;
- infira sequência operacional;
- altere a ordem definida pela autoridade competente;
- execute ondas simultaneamente sem autorização explícita;
- ultrapasse o escopo da onda vigente;
- inicie uma onda posterior antes do encerramento da anterior.

## 11. Requisitos de rastreabilidade

Cada onda deverá possuir evidências auditáveis contendo, no mínimo:

- identificação da onda;
- autorização;
- escopo;
- auditoria;
- evidências de integridade;
- estado dos artefatos;
- estado do repositório, quando aplicável;
- publicação, quando aplicável;
- encerramento formal.

## 12. Vigência

Esta Ordem de Governança entrará em vigor após aprovação e promoção pela autoridade competente, conforme a governança institucional aplicável.

Após sua entrada em vigor, sua utilização será obrigatória sempre que houver separação entre planejamento estrutural e execução operacional em migrações de Baseline, reorganizações estruturais ou execuções em ondas.
