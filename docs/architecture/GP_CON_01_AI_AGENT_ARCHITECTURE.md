# GP-CON-01 — Arquitetura Institucional de IA e Agentes

Status: **APROVADA SEM RESSALVAS — VIGENTE**

Data: 2026-07-21 (America/Sao_Paulo)

Classificação: Arquitetura institucional do núcleo ICFACTORY

Escopo: integração entre Desenvolvedor, ICFACTORY, Agente, Contrato da IA, IA e Projeto

## 1. Decisão arquitetural

A GP-CON-01 estabelece oficialmente uma arquitetura institucional independente de fornecedor para o uso de agentes e inteligências artificiais em projetos governados pelo framework.

Os efeitos institucionais desta arquitetura entram em vigor em 2026-07-21, após aprovação formal sem ressalvas pelo processo de governança do ICFACTORY.

A arquitetura separa três funções que não podem ser confundidas:

1. **governança metodológica**, exercida pelo ICFACTORY e pelas autoridades humanas competentes;
2. **orquestração assistida**, exercida pelo Agente dentro de mandato explícito;
3. **capacidade computacional de inteligência**, fornecida pela IA por meio do Contrato da IA.

O Agente não é a fonte do método. A IA não é autoridade. O Projeto é instância governada e não redefine o núcleo do framework. O Desenvolvedor permanece responsável pela intenção, pelas autorizações e pelas decisões humanas que não podem ser delegadas.

Esta decisão cria arquitetura operacional e vocabulário arquitetural. Ela não altera a Constituição, o Léxico Constitucional, a Custódia Metodológica, a escala de maturidade científica ou qualquer projeto governado.

## 2. Fundamento institucional

A arquitetura aplica normas já vigentes:

- Constituição, Artigo III — a autoridade deve ser explícita;
- Constituição, Artigo IV — o contexto deve ser explícito;
- Constituição, Artigo V — a governança deve ser unificada;
- Constituição, Artigo VI — observadores não governam;
- Constituição, Artigo VII — explicabilidade é obrigação arquitetural;
- Constituição, Artigo X — a evolução deve ser auditável;
- Constituição, Artigo XI — inteligência não é autoridade;
- `GOVERNANCE_ARCHITECTURE.md` — nenhum mecanismo de governança possui autoridade superior à Constituição ICFACTORY;
- `METHODOLOGICAL_CUSTODY_MODEL.md` — agentes, Harnesses e IAs podem preparar evidências e recomendações, mas não praticam atos oficiais de Custódia.

Não foi identificada necessidade de emenda constitucional para instituir esta arquitetura. A eventual inclusão de seus verbetes no Léxico Constitucional ou sua elevação a princípio constitucional exigirá GP e processo constitucional próprios.

## 3. Arquitetura Institucional

### 3.1 Visão estrutural

```text
                         autoridade humana e intenção
                                  │
                                  ▼
                          ┌─────────────────┐
                          │  Desenvolvedor  │
                          └────────┬────────┘
                                   │ propósito, autorização,
                                   │ contexto e decisão humana
                                   ▼
                          ┌─────────────────┐
                          │    ICFACTORY    │
                          └────────┬────────┘
                                   │ método, governança, escopo,
                                   │ restrições e critérios
                                   ▼
                          ┌─────────────────┐
                          │     Agente      │
                          └──────┬─────┬────┘
                                 │     │
             ação governada      │     │ solicitação estruturada
             e evidência          │     ▼
                                 │  ┌─────────────────┐
                                 │  │ Contrato da IA  │
                                 │  └────────┬────────┘
                                 │           │ contexto autorizado,
                                 │           │ capacidades e limites
                                 │           ▼
                                 │  ┌─────────────────┐
                                 │  │       IA        │
                                 │  └────────┬────────┘
                                 │           │ resultado + metadados
                                 ▼           │
                          ┌─────────────────┐│
                          │     Projeto     │◄┘ somente após validação
                          └─────────────────┘   e mediação do Agente
```

### 3.2 Cadeias obrigatórias

```text
Desenvolvedor
     ↓
ICFACTORY
     ↓
Agente
     ↓
Projeto
```

```text
Agente
     ↓
Contrato da IA
     ↓
IA
```

A primeira cadeia define governança e intervenção no Projeto. A segunda define uso de capacidade de IA. A segunda cadeia nunca substitui, contorna ou inverte a primeira.

### 3.3 Regra de precedência

Em caso de conflito:

1. a Constituição ICFACTORY prevalece;
2. a governança oficial e a Custódia prevalecem sobre configurações de Agente;
3. a Constituição e os contratos válidos do Projeto prevalecem sobre preferências operacionais do Agente;
4. o mandato explícito do Desenvolvedor limita a execução;
5. o Contrato da IA limita a interação com a IA;
6. a saída da IA nunca prevalece automaticamente sobre qualquer camada anterior.

## 4. Papéis Institucionais

### 4.1 Desenvolvedor

**Finalidade:** representar a responsabilidade humana que inicia, orienta, autoriza, revisa e aceita trabalho realizado sob o ICFACTORY.

**Responsabilidades:**

- declarar objetivo, contexto e resultado esperado;
- identificar a autoridade humana aplicável;
- conceder mandato e limites ao Agente;
- fornecer ou autorizar acesso às fontes necessárias;
- avaliar riscos e decisões que exijam julgamento humano;
- aprovar intervenções materiais quando requerido;
- responder pela aceitação do resultado no Projeto;
- preservar autoria, assistência utilizada e rastreabilidade.

**Limites:**

- não pode declarar que preferência pessoal substitui Constituição ou governança vigente;
- não pode transferir autoridade institucional para Agente ou IA por simples delegação de tarefa;
- não pode usar o Projeto para alterar silenciosamente o ICFACTORY;
- não pode atribuir validade factual automática à saída da IA.

**Relacionamentos:** governa a intenção e as autorizações humanas; utiliza o ICFACTORY como método; delega tarefas ao Agente dentro da governança; recebe evidências e resultados para decisão.

### 4.2 ICFACTORY

**Finalidade:** fornecer a infraestrutura metodológica, constitucional, arquitetural e de governança que torna o trabalho explicável, auditável, reproduzível e independente de fornecedor.

**Responsabilidades:**

- definir princípios, processos, papéis e limites institucionais;
- estabelecer como o Agente opera e presta contas;
- definir requisitos mínimos do Contrato da IA;
- separar conhecimento, recomendação, decisão e autoridade;
- preservar rastreabilidade, proveniência, histórico e evolução controlada;
- estabelecer critérios de conformidade e aceitação;
- manter independência em relação a agente, modelo, fornecedor, protocolo e infraestrutura específicos.

**Limites:**

- não substitui a autoridade humana competente;
- não executa automaticamente ações no Projeto;
- não absorve regras específicas do Projeto como normas universais;
- não depende de um Agente ou de uma IA determinados;
- não concede autoridade à IA.

**Relacionamentos:** recebe intenção e autorização humanas; governa o Agente; enquadra o Projeto; define o contrato abstrato que deve mediar qualquer IA.

### 4.3 Agente

**Finalidade:** atuar como componente operacional substituível que interpreta instruções governadas, organiza contexto, planeja tarefas, utiliza ferramentas e IAs autorizadas, produz evidências e propõe ou executa ações dentro de mandato explícito.

**Responsabilidades:**

- ler e respeitar a hierarquia documental aplicável;
- verificar escopo, autoridade, estado e restrições antes da ação;
- distinguir fato, inferência, recomendação e decisão;
- minimizar e estruturar o contexto enviado à IA;
- utilizar a IA exclusivamente por meio do Contrato da IA;
- validar saídas antes de usá-las;
- executar somente ações autorizadas;
- registrar fontes, transformações, decisões, ferramentas, resultados e falhas;
- interromper ou escalar quando autoridade, contexto ou segurança forem insuficientes;
- produzir handoff que permita continuidade por outro Agente.

**Limites:**

- não possui autoridade constitucional, custodial ou estratégica própria;
- não amplia o próprio mandato;
- não altera o método oficial por interpretação;
- não trata saída da IA como evidência verificada sem validação;
- não permite acesso direto e não governado da IA ao Projeto;
- não oculta dependência de fornecedor, ferramenta ou modelo;
- não retém estado indispensável somente em memória privada ou sessão efêmera.

**Relacionamentos:** é governado pelo ICFACTORY; recebe mandato do Desenvolvedor; atua sobre o Projeto; consome IA pelo Contrato da IA; devolve evidências e resultados ao Desenvolvedor.

#### Delimitação científica do papel Agente

A definição arquitetural do papel **Agente** possui finalidade exclusivamente institucional.

Ela não promove, não substitui, não altera, não modifica o grau de maturidade e não institucionaliza os conceitos experimentais correlatos relacionados a:

- Harness como Executor Assistido sem Autoridade Própria;
- Especificação Estruturada de Execução;
- Contexto de Execução governado.

Esses conceitos conservam integralmente seus estados científicos vigentes. Qualquer evolução continuará obedecendo ao ciclo científico próprio do ICFACTORY, incluindo evidências, revisão, gate, decisão custodial e atualização do registro aplicável.

### 4.4 Contrato da IA

**Finalidade:** constituir a fronteira institucional, auditável e independente de fornecedor entre o Agente e qualquer IA.

**Responsabilidades:**

- declarar identidade e versão do contrato;
- declarar capacidades requeridas e capacidades efetivamente disponíveis;
- estruturar objetivo, contexto autorizado, restrições e formato esperado;
- estabelecer políticas de dados, confidencialidade, retenção e minimização;
- definir limites de ferramentas, efeitos colaterais e permissões;
- exigir metadados de proveniência e execução disponíveis;
- normalizar resultados, recusas, erros, interrupções e incerteza;
- permitir cancelamento, timeout, orçamento e limites operacionais;
- registrar adaptador, fornecedor, modelo ou implementação utilizados sem torná-los normativos;
- permitir substituição e teste de conformidade entre implementações.

**Limites:**

- não confere autoridade institucional à IA;
- não aprova o conteúdo produzido;
- não substitui validação do Agente ou decisão humana;
- não incorpora peculiaridade de fornecedor como requisito universal sem extensão explícita;
- não autoriza acesso além do contexto e das capacidades declaradas.

**Relacionamentos:** recebe uma solicitação governada do Agente; traduz a solicitação para a interface concreta da IA; normaliza a resposta; devolve resultado e metadados ao Agente.

### 4.5 IA

**Finalidade:** fornecer capacidade computacional substituível para interpretar, gerar, classificar, transformar, recuperar, estimar ou recomendar informação segundo uma solicitação contratada.

**Responsabilidades:**

- processar somente o contexto recebido pelo contrato;
- retornar resultado no formato acordado ou falha explícita;
- expor, quando disponível, identificação técnica, versão, limitações e metadados solicitados;
- respeitar as restrições aplicadas pelo adaptador e pela infraestrutura.

**Limites:**

- não governa o ICFACTORY;
- não governa o Agente;
- não governa o Projeto;
- não pratica ato custodial, constitucional ou aprovação humana;
- não define o próprio escopo de acesso;
- não transforma geração em verdade, evidência ou decisão por si só;
- não acessa ou modifica o Projeto fora das capacidades mediadas e autorizadas.

**Relacionamentos:** é acessada somente pelo Contrato da IA; fornece resultado ao Agente por essa mesma fronteira; permanece substituível por outra implementação conforme testes de conformidade.

### 4.6 Projeto

**Finalidade:** constituir a instância concreta na qual objetivos, domínio, artefatos, código, dados, estados e regras específicas são desenvolvidos sob o ICFACTORY.

**Responsabilidades:**

- manter sua constituição, autoridade, contexto e contratos próprios quando aplicáveis;
- expor ao Agente somente os recursos necessários e autorizados;
- preservar estado, evidência e histórico das intervenções;
- declarar requisitos específicos sem apresentá-los como regras universais do framework;
- aceitar, rejeitar ou revisar resultados por autoridade competente.

**Limites:**

- não governa nem redefine o ICFACTORY;
- não invalida princípios universais do framework;
- não concede autoridade institucional ao Agente ou à IA;
- não converte uma decisão local em norma metodológica universal;
- não depende obrigatoriamente de fornecedor de IA específico para adotar o ICFACTORY.

**Relacionamentos:** é governado pelo ICFACTORY e por sua Constituição de Projeto; recebe atuação mediada do Agente; fornece estado e evidências; permanece separado do núcleo metodológico.

## 5. Interfaces Institucionais

### 5.1 Interface Desenvolvedor → ICFACTORY (`D-ICF`)

**Entrada mínima:**

- objetivo e motivação;
- identidade da autoridade solicitante;
- Projeto e domínio afetados;
- escopo, restrições e riscos;
- evidências e fontes disponíveis;
- nível de autonomia autorizado;
- critérios de aceitação e encerramento.

**Saída esperada:**

- processo ou GP aplicável;
- hierarquia documental;
- papéis e autoridades;
- gates, restrições e evidências requeridas;
- definição do que exige nova autorização.

### 5.2 Interface ICFACTORY → Agente (`ICF-A`)

**Entrada mínima ao Agente:**

- mandato operacional derivado do objetivo humano;
- Constituição e políticas aplicáveis;
- estado institucional vigente;
- fronteiras entre auditoria, recomendação e intervenção;
- artefatos autorizados;
- critérios de aceitação, validação e parada;
- requisitos de rastreabilidade e handoff.

**Saída esperada:**

- plano rastreável;
- execução limitada ao mandato;
- evidências, diffs, resultados de validação e riscos;
- indicação explícita de hipóteses e bloqueios;
- registro de ferramentas e IAs utilizadas.

### 5.3 Interface Agente ↔ Projeto (`A-P`)

**Do Projeto para o Agente:**

- constituição e instruções locais;
- estado verificável;
- artefatos, contratos e dados autorizados;
- testes, logs, histórico e dependências;
- limites de escrita, execução e publicação.

**Do Agente para o Projeto:**

- leituras e diagnósticos sem efeitos colaterais quando em auditoria;
- alterações mínimas quando autorizadas;
- evidência de validação;
- registro de decisões, autoria assistida e proveniência;
- plano de reversão ou tratamento de falha quando aplicável.

Toda ação material deve ser atribuível ao mandato que a autorizou. O Agente deve operar em modo seguro quando não puder demonstrar essa cadeia.

### 5.4 Interface Agente → Contrato da IA (`A-CIA`)

Cada solicitação deve transportar, conforme aplicável:

- identificador de correlação;
- objetivo delimitado;
- contexto mínimo autorizado;
- classificação e política dos dados;
- instruções e restrições aplicáveis;
- capacidades e ferramentas permitidas;
- formato ou schema de saída;
- critérios de qualidade e validação;
- orçamento, timeout, cancelamento e limites de repetição;
- requisitos de proveniência;
- política para incerteza, recusa e erro.

O Agente não deve enviar contexto integral por conveniência quando um subconjunto suficiente puder ser declarado.

### 5.5 Interface Contrato da IA ↔ IA (`CIA-IA`)

O adaptador concreto pode usar API, processo local, protocolo aberto, serviço remoto ou outra infraestrutura. Independentemente do meio, deve:

- mapear o contrato institucional para a interface técnica;
- declarar extensões específicas do fornecedor;
- impedir capacidade não autorizada;
- capturar resultado, falha e metadados observáveis;
- normalizar a resposta para o Agente;
- evitar que identificadores técnicos se tornem semântica institucional.

### 5.6 Retorno IA → Agente → Desenvolvedor/Projeto

A resposta deve distinguir:

- conteúdo produzido;
- fatos citados e suas fontes;
- inferências e hipóteses;
- incerteza ou limitação declarada;
- identidade técnica disponível da execução;
- uso de ferramentas ou dados externos;
- erros, truncamentos, recusas e resultados parciais.

O Agente valida estrutura, escopo, segurança e consistência antes de propor uso. A validação factual ou institucional necessária permanece separada da geração.

## 6. Princípios Arquiteturais

Os princípios desta seção são oficiais no escopo da arquitetura GP-CON-01 a partir de sua aprovação formal. Eles não alteram nem ampliam o rol constitucional vigente.

### PAIA-01 — O ICFACTORY governa o Agente

O Agente opera segundo método, hierarquia documental, autoridade, limites, gates e rastreabilidade definidos pelo ICFACTORY. Configuração do Agente não pode substituir a governança do framework.

### PAIA-02 — O Contrato da IA governa a IA

Toda interação institucional com IA deve possuir contrato explícito que delimite contexto, capacidade, restrições, resultado e evidência de execução.

### PAIA-03 — A IA não governa o ICFACTORY

Saídas, recomendações ou capacidades da IA não criam, modificam, interpretam autoritativamente ou revogam o método oficial.

### PAIA-04 — O Projeto não governa o ICFACTORY

Requisitos e aprendizados locais podem gerar contribuição ou Research, mas não alteram automaticamente o núcleo metodológico.

### PAIA-05 — Agentes são substituíveis

Mandato, estado necessário, evidências e handoff devem permitir que outro Agente compatível continue o trabalho sem depender de memória privada ou identidade técnica específica.

### PAIA-06 — IAs são substituíveis

A arquitetura não presume modelo, fornecedor, protocolo, hospedagem ou modalidade específicos. Diferenças de capacidade devem ser declaradas e testadas pelo contrato.

### PAIA-07 — O ICFACTORY permanece independente de fornecedor

Identidades comerciais e detalhes de integração pertencem a adaptadores e registros de execução, não às definições institucionais do framework.

### PAIA-08 — Toda IA opera através do Contrato da IA

Nenhuma IA pode receber contexto, utilizar ferramentas ou produzir resultado institucional para o framework fora da fronteira contratual definida nesta arquitetura.

### PAIA-09 — Autoridade não é transferida por automação

Delegar processamento, geração ou execução assistida não transfere autoridade humana, constitucional, custodial ou do Projeto.

### PAIA-10 — Saídas de IA são insumos, não decisões autoexecutáveis

Resultado de IA deve ser classificado, validado e submetido à autoridade aplicável antes de produzir efeito material.

### PAIA-11 — Contexto e capacidade seguem menor privilégio

Agente e contrato expõem à IA somente dados, ferramentas, duração e efeitos necessários ao objetivo autorizado.

### PAIA-12 — Toda interação relevante deixa evidência auditável

Solicitação, contrato, implementação utilizada, resultado, validação, decisão e efeito devem ser correlacionáveis na medida exigida pelo risco e pelo Projeto.

## 7. Léxico Arquitetural Oficial

As definições abaixo são únicas para esta arquitetura e devem orientar documentos derivados. Elas não modificam o `CONSTITUTIONAL_LEXICON.md`.

### IA

Capacidade computacional substituível que, mediante entrada contratada, produz interpretação, geração, classificação, transformação, recuperação, estimativa ou recomendação, sem possuir por isso autoridade institucional, custodial, constitucional ou operacional autônoma.

### Agente

Componente operacional substituível que, sob mandato humano e governança do ICFACTORY, organiza contexto, planeja e executa tarefas autorizadas, utiliza ferramentas e IAs por interfaces governadas, valida resultados e preserva evidências, sem autoridade institucional própria.

### Contrato da IA

Especificação institucional independente de fornecedor que define a fronteira entre Agente e IA, declarando entradas, contexto, capacidades, restrições, políticas de dados, formatos, metadados, falhas, limites operacionais e requisitos de auditabilidade aplicáveis a cada interação ou classe de interações.

### Desenvolvedor

Pessoa humana responsável por declarar intenção, contexto e critérios, exercer ou identificar a autoridade aplicável, autorizar o mandato do Agente, avaliar decisões não delegáveis e aceitar ou rejeitar resultados no escopo do Projeto.

### Projeto

Instância governada que reúne objetivo, domínio, autoridades, artefatos, código, dados, estados e regras específicas desenvolvidos sob o ICFACTORY, sem possuir autoridade para redefinir automaticamente o núcleo do framework.

### Framework

Conjunto institucional versionado de Constituição, princípios, léxico, arquitetura, governança, método, processos, contratos e artefatos oficiais que orienta projetos e agentes sem depender de implementação, IA ou fornecedor específicos. Nesta documentação, `Framework` designa o ICFACTORY salvo qualificação explícita em contrário.

### 7.1 Distinções obrigatórias

- **IA não é Agente:** IA fornece capacidade; Agente governa a utilização dessa capacidade dentro do mandato recebido.
- **Agente não é Desenvolvedor:** o Agente recebe delegação de tarefa; o Desenvolvedor conserva responsabilidade e autoridade humana aplicáveis.
- **Contrato da IA não é contrato do Projeto:** o primeiro governa a interface técnica-institucional com IA; o segundo regula objetos específicos do Projeto.
- **Projeto não é Framework:** o Projeto instancia e aplica o método; o Framework preserva o núcleo universal.
- **Framework não é fornecedor:** o ICFACTORY permanece válido quando agentes, IAs, protocolos ou infraestruturas são substituídos.

## 8. Requisitos Mínimos do Contrato da IA

Uma implementação somente é compatível com esta arquitetura quando documenta:

| Dimensão | Requisito mínimo |
|---|---|
| Identidade | identificador e versão do contrato/adaptador |
| Objetivo | tarefa delimitada e resultado esperado |
| Contexto | dados autorizados, origem e classificação |
| Capacidade | operações e ferramentas permitidas |
| Restrições | ações proibidas, limites de acesso e efeitos |
| Saída | formato, schema ou regras de interpretação |
| Proveniência | correlação, implementação e metadados disponíveis |
| Validação | controles antes do uso do resultado |
| Falha | erro, recusa, timeout, cancelamento e resultado parcial |
| Recursos | orçamento, duração, repetição e limites de consumo |
| Dados | minimização, retenção, confidencialidade e descarte |
| Portabilidade | extensões específicas isoladas e fallback documentado |

O contrato pode ser representado em documento, schema ou interface executável. A representação técnica é substituível; os campos institucionais permanecem.

## 9. Governança e Controle

### 9.1 Autoridade

- a Custódia Metodológica governa a evolução oficial desta arquitetura;
- o Desenvolvedor ou autoridade do Projeto governa a autorização concreta aplicável;
- o Agente governa a orquestração somente dentro do mandato;
- o Contrato da IA governa a exposição de contexto e capacidade à IA;
- a IA não possui autoridade sobre nenhuma dessas camadas.

### 9.2 Gestão de mudanças

Alterações nesta arquitetura devem:

- identificar motivação, escopo e autoridade;
- preservar compatibilidade ou declarar ruptura;
- avaliar impacto sobre agentes, contratos e projetos existentes;
- manter versões e histórico;
- não incorporar extensão proprietária ao núcleo sem alternativa independente;
- seguir Custódia e gates aplicáveis.

### 9.3 Falha segura

Quando contrato, autoridade, contexto, capacidade ou validação forem insuficientes:

- a IA não recebe capacidade adicional por inferência;
- o Agente não amplia o mandato;
- nenhuma saída é aplicada automaticamente;
- o estado permanece preservado;
- a insuficiência é registrada e escalada à autoridade competente.

### 9.4 Auditabilidade

O registro mínimo de uma interação material deve permitir responder:

- quem autorizou;
- qual método e versão governaram;
- qual Agente atuou;
- qual contrato e adaptador foram usados;
- qual IA ou implementação processou a solicitação, quando identificável;
- quais dados e ferramentas foram autorizados;
- qual resultado foi produzido;
- quais validações ocorreram;
- qual decisão humana ou institucional foi tomada;
- qual efeito foi aplicado ao Projeto.

## 10. Substituição e Continuidade

### 10.1 Substituição de Agente

A continuidade entre agentes exige pacote de handoff com:

- objetivo e estado atual;
- mandato e autorizações vigentes;
- plano e critérios de aceitação;
- documentos e versões aplicáveis;
- ações realizadas e pendentes;
- evidências, resultados e falhas;
- decisões que aguardam autoridade humana;
- estado externo necessário para retomada.

Nenhuma continuidade pode depender exclusivamente do histórico privado de uma sessão.

### 10.2 Substituição de IA

A troca de IA exige:

- verificação das capacidades requeridas pelo contrato;
- teste de conformidade de entrada, saída, erro e limites;
- declaração de diferenças relevantes;
- revalidação proporcional ao risco;
- preservação do identificador da implementação em cada registro de execução.

Equivalência de interface não presume equivalência de resultado. A substituição deve preservar governança, não resultados idênticos.

### 10.3 Continuidade do Projeto

O Projeto deve conservar documentos, decisões, artefatos e evidências em repositórios controlados pelo próprio Projeto ou pela governança aplicável. Agente e IA são dependências substituíveis e não podem ser os únicos custodiantes do conhecimento necessário à continuidade.

## 11. Análise Arquitetural de Impacto

### 11.1 Governança

**Impacto positivo:** explicita autoridade, impede inversão entre IA e método, separa decisão de geração e cria fronteiras auditáveis.

**Risco:** tratar o Contrato da IA como autoridade decisória. **Controle:** o contrato limita interação, mas não valida conteúdo nem pratica decisão.

### 11.2 Replicabilidade

**Impacto positivo:** papéis, entradas, saídas, metadados e handoff permitem reproduzir processos com agentes e IAs diferentes.

**Limite:** modelos não determinísticos podem produzir respostas distintas. Replicabilidade significa reconstrução do processo, das condições e dos critérios, não identidade obrigatória de texto.

### 11.3 Portabilidade

**Impacto positivo:** o núcleo institucional permanece estável enquanto adaptadores absorvem diferenças de API, protocolo, hospedagem e formato.

**Risco:** extensões proprietárias vazarem para o contrato universal. **Controle:** isolar extensões, declarar fallback e manter perfil mínimo comum.

### 11.4 Independência tecnológica

**Impacto positivo:** nenhuma definição depende de marca, modelo, nuvem, biblioteca ou protocolo específico.

**Critério:** a troca de fornecedor não pode exigir mudança de Constituição, princípios ou papéis institucionais; somente adaptadores, perfis de capacidade e validações proporcionais podem mudar.

### 11.5 Adoção do framework

**Impacto positivo:** novos adotantes recebem um modelo único para integrar ferramentas assistidas por IA sem confundir automação com autoridade.

**Custo:** cada adoção deve explicitar mandato, contrato, dados, ferramentas e registros mínimos. Esse custo é deliberado e proporcional ao risco institucional.

### 11.6 Continuidade de projetos

**Impacto positivo:** conhecimento e decisões permanecem no Projeto e nos registros oficiais, reduzindo dependência de contas, sessões, prompts privados ou memória de um agente.

**Risco:** perda de detalhes na substituição. **Controle:** handoff obrigatório, versionamento de contrato e registro de execução.

## 12. Conformidade Arquitetural

Uma integração é **conforme** quando:

1. identifica os seis papéis aplicáveis;
2. demonstra a cadeia Desenvolvedor → ICFACTORY → Agente → Projeto;
3. demonstra a cadeia Agente → Contrato da IA → IA;
4. impede acesso institucional à IA fora do contrato;
5. preserva autoridade humana e documental;
6. permite substituir Agente e IA sem alterar o núcleo do ICFACTORY;
7. registra contexto, capacidades, resultado, validação e efeito;
8. separa regra universal de requisito específico do Projeto.

É **não conforme** quando, entre outros casos:

- a IA atua diretamente como autoridade;
- o Agente altera o método sem ato competente;
- o Projeto redefine princípio do framework;
- contexto ou ferramenta chegam à IA fora do contrato;
- fornecedor ou modelo é tratado como componente institucional obrigatório;
- estado necessário à continuidade existe somente em sessão privada;
- saída de IA produz efeito material sem validação e autorização aplicáveis.

## 13. Critérios de Aceitação da GP-CON-01

| Critério | Evidência neste documento | Resultado |
|---|---|---|
| Arquitetura institucional completa | seções 3 e 9 | ATENDIDO |
| Papéis definidos | seção 4 | ATENDIDO |
| Interfaces documentadas | seção 5 | ATENDIDO |
| Léxico formalizado | seção 7 | ATENDIDO |
| Princípios registrados | seção 6 | ATENDIDO |
| Impactos analisados | seção 11 | ATENDIDO |
| Independência de fornecedor | seções 8, 10 e 11.4 | ATENDIDO |
| HISTORY e ROADMAP atualizados | registros associados à GP-CON-01 | ATENDIDO após aplicação dos registros |

## 14. Recomendações sem efeito automático

Sem alterar a arquitetura aprovada, recomenda-se para ciclos futuros:

- criar um template portátil do Contrato da IA;
- criar suíte de conformidade para adaptadores;
- produzir exemplo de handoff entre agentes;
- avaliar integração desta arquitetura ao `DOCUMENT_MAP.md` em GP documental própria;
- avaliar, somente por processo constitucional, se algum verbete deve integrar o Léxico Constitucional.

Essas recomendações não criam novos artefatos, maturidades, obrigações constitucionais ou promoções nesta GP.

## 15. Encerramento

A GP-CON-01 estabelece oficialmente a camada institucional permanente que separa método, orquestração e inteligência. Desenvolvedores podem compreender e auditar quem governa, quem executa, como a IA é contratada, quais informações atravessam cada fronteira e como agentes e IAs podem ser substituídos sem alterar a identidade do ICFACTORY.

Não foram alterados Constituição, Léxico Constitucional, código-fonte, projetos governados, Research, conceitos científicos ou implementações.
