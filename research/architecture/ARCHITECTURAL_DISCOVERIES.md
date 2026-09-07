# ICFACTORY — Architectural Discoveries

## Objetivo

Este documento constitui o inventário oficial das Descobertas Arquiteturais (DA) identificadas durante o desenvolvimento de projetos utilizando o ICFACTORY.

Seu propósito é registrar, preservar e acompanhar a evolução de descobertas que ampliam ou modificam os princípios arquiteturais empregados pelo framework.

As Discoveries registradas neste documento ainda não representam princípios oficiais do ICFACTORY.

Enquanto permanecerem na camada Research, constituem hipóteses arquiteturais em processo de validação.

---

# Escopo

Este inventário contempla exclusivamente descobertas relacionadas à arquitetura de software.

São consideradas Descobertas Arquiteturais aquelas que afetam a estrutura dos sistemas, a organização das camadas, a especialização de componentes, a integração entre módulos ou qualquer princípio reutilizável de construção de software.

Descobertas relacionadas ao processo de desenvolvimento pertencem ao inventário de Descobertas Metodológicas.

---

# Processo De Evolução

Toda Discovery registrada neste documento deverá seguir obrigatoriamente o Discovery Lifecycle definido pelo ICFACTORY.

Nenhuma Discovery poderá ser promovida diretamente ao núcleo arquitetural do framework.

Sua promoção dependerá exclusivamente das evidências produzidas durante o desenvolvimento de múltiplos projetos.

---

# Inventário Oficial

---

# DA-01 — Especialização Por Contexto Operacional

## Estado

CANDIDATA

---

## Origem

Projeto:

Sistema de Análise de Água

Categoria:

Descoberta Arquitetural

---

## Problema Observado

Durante a evolução do Sistema de Análise de Água verificou-se que diferentes domínios operacionais exigiam sensores, indicadores, regras e painéis distintos.

A criação de uma arquitetura específica para cada domínio produziria duplicação estrutural e dificultaria a evolução da plataforma.

---

## Descoberta

Uma única arquitetura pode atender múltiplos contextos operacionais.

A seleção explícita do contexto determina quais sensores, indicadores, regras, análises e funcionalidades serão ativados, preservando um núcleo arquitetural comum.

---

## Hipótese Arquitetural

A especialização por contexto operacional permite reutilizar a mesma plataforma em diferentes domínios sem necessidade de reestruturação arquitetural.

---

## Evidências

Durante o desenvolvimento do Sistema de Análise de Água foi identificada a possibilidade de utilização da mesma arquitetura para contextos como:

* abastecimento urbano;
* ambiente rural;
* ambiente industrial;
* monitoramento ambiental;
* aquicultura;
* pesquisa.

Cada contexto ativa capacidades específicas preservando a arquitetura central da plataforma.

---

## Aplicabilidade Esperada

A Discovery possui potencial de reutilização em diversos domínios, incluindo:

* sistemas hospitalares;
* sistemas industriais;
* plataformas educacionais;
* sistemas administrativos;
* ERPs;
* plataformas financeiras;
* sistemas de monitoramento.

---

## Critérios De Validação

A Discovery deverá ser observada em projetos distintos para confirmar que a adaptação por contexto representa um princípio arquitetural reutilizável e independente do domínio.

---

## Próximas Validações

✔ Sistema de Análise de Água

⬜ Sistema de Gestão para Autoescola

⬜ Outros projetos desenvolvidos utilizando o ICFACTORY

---

# DA-02 — Auditoria De Integração Arquitetural

## Estado

CANDIDATA

---

## Origem

Projeto:

Sistema de Análise de Água

Categoria:

Descoberta Arquitetural

---

## Problema Observado

Durante as auditorias verificou-se que confirmar apenas a existência de integração entre módulos era insuficiente para avaliar a qualidade da arquitetura.

Era necessário compreender também a direção das dependências, os riscos indiretos, os componentes isolados e as integrações ausentes.

---

## Descoberta

A Auditoria de Integração Arquitetural amplia a auditoria tradicional ao verificar não apenas se módulos se comunicam, mas se as relações estabelecidas são coerentes com a arquitetura proposta.

---

## Hipótese Arquitetural

A análise sistemática das integrações aumenta a capacidade de evolução da arquitetura e reduz riscos decorrentes de dependências inadequadas ou ausentes.

---

## Evidências

Durante a auditoria do Painel Executivo do Sistema de Análise de Água foram identificados:

* dependências diretas;
* dependências indiretas;
* integrações ausentes;
* riscos herdados;
* oportunidades de evolução arquitetural.

Essas informações não seriam obtidas por uma simples verificação funcional de integração.

---

## Aplicabilidade Esperada

A Discovery possui potencial de utilização em qualquer arquitetura baseada em módulos ou camadas.

---

## Critérios De Validação

A Discovery deverá ser aplicada em projetos distintos para verificar sua capacidade de revelar riscos arquiteturais reutilizáveis.

---

## Próximas Validações

✔ Sistema de Análise de Água

⬜ Sistema de Gestão para Autoescola

⬜ Outros projetos desenvolvidos utilizando o ICFACTORY

---

# DA-03 — GAB — Governed Architectural Boundary

## Estado

CANDIDATA — RESEARCH

## Identidade Experimental

DISCOVERY_ID::DA-03

PROVISIONAL_ID::GAB-R01

VERSION::0.1

LAYER::RESEARCH

MATURITY::CANDIDATE

NORMATIVE::NO

PROMOTION::NO

---

## Sigla

GAB — Governed Architectural Boundary

Tradução operacional:

Fronteira Arquitetural Governada.

---

## Origem E Proveniência

Projeto de origem:

Sistema de Monitoramento de Águas

Domínio de aplicação:

Monitoramento e avaliação governada de qualidade da água.

Contexto operacional:

Auditoria arquitetural da fronteira semântica entre o catálogo hídrico e o Governed Core.

Módulo de origem:

CORE_11 — Semantic Boundary

Motivação:

Impedir que diferenças de identificador, linguagem, unidade, versão ou contexto sejam silenciosamente tratadas como equivalência semântica válida entre subsistemas.

Data do registro inicial:

2026-09-07

Autor(es):

Henderson Mauricio Batista — projeto e decisão de pesquisa.

ChatGPT / Alfred — apoio à auditoria, formulação e consolidação da hipótese sob governança do projeto.

Categoria:

Descoberta Arquitetural

Estado atual:

CANDIDATA — RESEARCH

---

## Problema Observado

Durante a auditoria semântica do Sistema de Monitoramento de Águas verificou-se que subsistemas distintos utilizavam referências diferentes para conceitos potencialmente equivalentes, por exemplo `ph` no catálogo hídrico e `PH` no Governed Core.

A existência de identificadores, metadados e autorização de referência não demonstrava, por si só, identidade ou equivalência semântica entre os modelos.

Também se verificou que o ICFACTORY possuía princípios de separação de responsabilidades, governança, auditoria e interfaces, mas não foi localizado um processo geral específico para formalização de fronteiras arquiteturais entre modelos com semânticas distintas.

---

## Pesquisa Externa De Apoio

A pesquisa externa autorizada examinou conceitos consolidados de arquitetura e Domain-Driven Design, especialmente:

* Bounded Context;
* Anti-Corruption Layer (ACL);
* Context Map;
* Ports and Adapters / Hexagonal Architecture.

Fontes principais consultadas:

* Microsoft Azure Architecture Center — Anti-Corruption Layer pattern: https://learn.microsoft.com/en-us/azure/architecture/patterns/anti-corruption-layer
* AWS Prescriptive Guidance — Anti-corruption layer pattern: https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/acl.html

As fontes descrevem a Anti-Corruption Layer como mecanismo de mediação/tradução entre subsistemas ou bounded contexts que possuem semânticas distintas, preservando o modelo interno e concentrando a tradução na fronteira.

O ICFACTORY não adota automaticamente esses padrões. Eles constituem fundamentação externa para investigação e adaptação governada.

---

## Descoberta

Uma fronteira arquitetural entre modelos, módulos ou contextos não deve ser tratada apenas como interface técnica.

Quando existe diferença de identidade, linguagem, semântica, autoridade ou representação, a fronteira deve possuir contrato explícito, tradução controlada, isolamento de responsabilidades, comportamento fail-safe e evidência observável da resolução realizada.

---

## Hipótese Arquitetural

Uma Governed Architectural Boundary (GAB) pode reduzir acoplamento e ambiguidade entre componentes ao tornar explícitos:

* os contextos e namespaces envolvidos;
* os objetos autorizados a atravessar a fronteira;
* as transformações ou equivalências permitidas;
* as responsabilidades proibidas na fronteira;
* os estados de resolução e falha;
* a versão aplicável do contrato;
* a evidência da tradução ou resolução efetuada.

---

## Contrato Experimental GAB-R01 v0.1

Contrato mínimo candidato:

```text
GAB_BINDING
concept_id
source_namespace
source_reference
target_namespace
target_reference
semantic_version
canonical_unit_reference
equivalence_status
resolution_evidence
```

`resolution_evidence` deve permitir reconstruir por que uma travessia foi resolvida, bloqueada ou classificada como incompatível.

Regra central candidata:

```text
DEFAULT::DO_NOT_CROSS

CROSS_BOUNDARY
IFF
POSITIVE_GOVERNED_EVIDENCE
DEMONSTRATES_COMPATIBILITY
```

Capacidade de tradução não constitui autoridade para declarar equivalência.

---

## Estados De Resolução Candidatos

GAB-R01 v0.1 reconhece os seguintes estados experimentais:

* `RESOLVED` — vínculo explícito e compatibilidade demonstrada;
* `UNRESOLVED` — referências candidatas existem, mas a compatibilidade/equivalência não foi demonstrada;
* `NOT_MAPPED` — referência de origem conhecida sem contraparte governada registrada;
* `UNKNOWN_REFERENCE` — entrada não reconhecida como referência ou alias governado;
* `AMBIGUOUS` — mais de um vínculo plausível sem desambiguação explícita;
* `INCOMPATIBLE` — incompatibilidade demonstrada entre elementos necessários à travessia.

---

## Princípios Candidatos

GAB-01 — EXPLICIT_CONTEXT

Toda fronteira deve identificar os contextos, modelos ou namespaces que conecta.

GAB-02 — EXPLICIT_CONTRACT

Somente informações previstas no contrato podem atravessar a fronteira.

GAB-03 — CONTROLLED_TRANSLATION

Traduções e equivalências entre modelos devem ser explícitas e rastreáveis; similaridade textual não demonstra equivalência.

GAB-04 — RESPONSIBILITY_ISOLATION

A fronteira não deve absorver regras de negócio, autoridade ou decisões que pertencem aos componentes conectados.

GAB-05 — FAIL_SAFE

Tradução desconhecida, incompatível ou ambígua não pode ser promovida silenciosamente a equivalência válida.

GAB-06 — OBSERVABLE_RESOLUTION

A resolução realizada na fronteira deve produzir evidência suficiente para auditoria e diagnóstico.

GAB-07 — INDEPENDENT_EVOLUTION

A fronteira deve reduzir propagação desnecessária de mudanças entre os componentes conectados.

---

## Invariantes Candidatos Consolidados

GAB-I01 — Similaridade de referência ou linguagem não demonstra equivalência governada.

GAB-I02 — Equivalência exige vínculo canônico explícito.

GAB-I03 — Existência semântica não implica pertencimento governado.

GAB-I04 — Compatibilidade numérica exige compatibilidade semântica e de unidade.

GAB-I05 — Compatibilidade desconhecida não equivale a incompatibilidade comprovada.

GAB-I06 — Estabilidade do identificador não demonstra estabilidade semântica.

GAB-I07 — Mudança semântica material exige nova versão semântica.

GAB-I08 — Registros históricos devem preservar o vínculo semântico original.

GAB-I09 — Aliases exigem vínculo canônico explícito.

GAB-I10 — Múltiplos vínculos plausíveis exigem desambiguação explícita.

GAB-I11 — Contexto pode apoiar interpretação, mas não cria autoridade semântica.

GAB-I12 — `RESOLVED` exige evidência governada positiva.

---

## Responsabilidades E Proibições Candidatas

A GAB pode, experimentalmente:

* identificar contexto;
* reconhecer referências;
* resolver bindings explícitos;
* verificar versão semântica;
* verificar compatibilidade de unidade;
* detectar ambiguidade;
* operar fail-safe;
* produzir evidência de resolução.

A GAB não pode:

* criar autoridade;
* inventar equivalência;
* inferir alias como vínculo governado;
* selecionar equivalência por probabilidade;
* criar conceito automaticamente;
* adicionar membro à APS automaticamente;
* duplicar o catálogo como nova fonte de verdade;
* definir thresholds;
* executar regras;
* decidir conformidade;
* tomar decisão operacional.

---

## Aplicação Inicial — Semantic Boundary

No Sistema de Monitoramento de Águas, a primeira aplicação candidata da GAB é a Semantic Boundary entre o catálogo hídrico e o Governed Core.

Exemplo de problema:

`ph` → catálogo hídrico

`PH` → Governed Core

A GAB não pode inferir equivalência apenas pela semelhança dos identificadores. A equivalência deverá depender de vínculo semântico explícito e governado.

A Semantic Boundary é uma aplicação de pesquisa da GAB; não constitui implementação autorizada nem promoção da GAB ao núcleo normativo do ICFACTORY.

---

## Evidência De Validação — CORE_11

Em 2026-09-07, o contrato GAB-R01 v0.1 foi submetido a uma rodada controlada de validação adversarial no CORE_11 do Sistema de Monitoramento de Águas.

Dez vetores arquiteturais foram avaliados:

1. `ph ↔ PH` — `UNRESOLVED`;
2. `turbidez ↔ TURBIDITY` — `UNRESOLVED`;
3. `oxigenio_dissolvido ↔ DISSOLVED_OXYGEN` — `UNRESOLVED`;
4. `temperatura_agua ↔ ausência de referência governada` — `NOT_MAPPED`;
5. compatibilidade de unidade não demonstrada — `UNRESOLVED`;
6. mudança semântica sem versionamento demonstrado — `UNRESOLVED`;
7. alias desconhecido — `UNKNOWN_REFERENCE`;
8. equivalência ambígua — `AMBIGUOUS`;
9. binding explícito válido, em vetor arquitetural controlado — `RESOLVED`;
10. incompatibilidade de unidade comprovada, em vetor arquitetural controlado — `INCOMPATIBLE`.

Resultado da rodada:

```text
TESTS_EXECUTED::10
EXPECTED_BEHAVIOR_PASS::10
RESOLUTION_STATES_COVERED::6/6
FAIL_SAFE_MODEL::SUPPORTED
POSITIVE_RESOLUTION_MODEL::SUPPORTED_BY_CONTROLLED_VECTOR
NEGATIVE_RESOLUTION_MODEL::SUPPORTED_BY_CONTROLLED_VECTOR
```

Os testes 09 e 10 são vetores arquiteturais controlados; não constituem prova de implementação desses comportamentos no software atual.

A rodada sustenta o contrato experimental e o fechamento arquitetural do CORE_11, mas não demonstra reutilização da GAB em projeto independente.

---

## Relação Com Conhecimento Externo

A GAB possui convergência conceitual com Anti-Corruption Layer e Bounded Context, porém adiciona como hipótese de pesquisa do ICFACTORY ênfase explícita em:

* governança da fronteira;
* autoridade;
* evidência;
* rastreabilidade;
* fail-safe;
* versionamento do contrato;
* separação entre capacidade de tradução e permissão para reconhecer equivalência.

Portanto:

`GAB != ACL`

`GAB != BOUNDED_CONTEXT`

`GAB != PORT_OR_ADAPTER`

Esses conceitos externos são referências de pesquisa, não sinônimos nem autoridade normativa do ICFACTORY.

---

## Critérios De Validação

A Discovery deverá ser testada em múltiplas fronteiras e projetos para avaliar se:

1. reduz ambiguidade entre modelos;
2. impede vazamento indevido de responsabilidades;
3. preserva autoridade e rastreabilidade;
4. produz comportamento fail-safe em traduções não demonstradas;
5. permite evolução independente dos componentes;
6. é reutilizável além do caso semântico do Sistema de Monitoramento de Águas.

---

## Próximas Validações

✔ Sistema de Monitoramento de Águas — Semantic Boundary — hipótese arquitetural identificada

✔ Auditoria adversarial da Semantic Boundary — 10 vetores controlados, 6 estados de resolução cobertos

⬜ Segunda fronteira no Sistema de Monitoramento de Águas

⬜ Sistema de Gestão para Autoescola

⬜ Outro projeto ICFACTORY independente

---

## Autoridade E Maturidade

LAYER::RESEARCH

MATURITY::CANDIDATE

NORMATIVE::NO

PROMOTION::NO

IMPLEMENTATION_AUTHORIZED::NO

A validação adversarial no projeto de origem não altera automaticamente o estado oficial para `EM VALIDAÇÃO`, pois o Discovery Lifecycle exige justificativa documental para mudança de estado e validação em contextos/projetos distintos antes das etapas posteriores.

A existência deste registro não autoriza alteração de arquitetura, implementação, migração ou cutover em qualquer projeto.

---

# Observações Gerais

As Discoveries registradas neste documento representam hipóteses arquiteturais produzidas durante o desenvolvimento de projetos reais.

Sua existência não implica incorporação automática ao núcleo arquitetural do ICFACTORY.

A promoção de qualquer Discovery dependerá exclusivamente do processo definido pelo Discovery Lifecycle e das evidências obtidas em múltiplos contextos de aplicação.

---

# Registro GP-R01

Linha de programa:

GP-R - Programas da camada Research.

Confirmacao:

DA-01 permanece registrada como Discovery Arquitetural CANDIDATA.

DA-02 permanece registrada como Discovery Arquitetural CANDIDATA.

DA-03 — GAB / GAB-R01 v0.1 permanece registrada como Discovery Arquitetural CANDIDATA — RESEARCH.

Nao ha promocao automatica ao nucleo arquitetural oficial do ICFACTORY.

A GP-R01 apenas institucionaliza a camada Research e preserva DA-01, DA-02 e DA-03 como hipoteses arquiteturais em investigacao.
