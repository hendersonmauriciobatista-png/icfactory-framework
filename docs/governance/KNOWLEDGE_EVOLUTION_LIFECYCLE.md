# ICFACTORY — Ciclo de Evolução do Conhecimento

Status: **RATIFICADO PELA GP-FW-02D**

Data: 2026-07-20 (America/Sao_Paulo)

## 1. Objetivo

Este documento operacionaliza o `SCIENTIFIC_MATURITY_MODEL.md`. Ele define a sequência, os gates, as responsabilidades e os registros necessários para mover conhecimento entre Pesquisa (P), Experimental (E), Validado (V) e Constitucional (C).

O ciclo não promove conceitos por si. Toda transição depende de uma GP própria, decisão humana, evidências verificáveis e atualização do registro oficial.

## Ciclo Oficial de Evolução do Conhecimento

```text
Pesquisa (P)
     │
     │ Gate P→E: hipótese testável + evidência inicial + protocolo controlado
     ▼
Experimental (E)
     │
     │ Gate E→V: uso operacional comprovado + estabilidade + escopo explícito
     ▼
Validado (V)
     │
     │ Gate V→C: multidomínio + longitudinalidade + compatibilidade constitucional
     ▼
Constitucional (C)
```

Em qualquer nível, nova evidência pode iniciar revisão, redução de escopo, regressão ou arquivamento. Não existe promoção tácita.

## 3. Fase P — Investigar

### Entrada

Observação, problema, Discovery ou hipótese com proveniência identificável.

### Atividades obrigatórias

1. atribuir nome/identificador e versão;
2. registrar origem, primeira ocorrência, contexto e motivação;
3. separar fato, interpretação e hipótese;
4. definir critérios de avaliação e falsificação;
5. identificar riscos, conflitos potenciais e fontes;
6. propor protocolo de experimentação controlada.

### Artefatos mínimos

- registro de pesquisa ou Discovery;
- inventário de fontes;
- hipótese testável;
- critérios de sucesso, falha e inconclusão;
- proposta de experimento.

### Gate P → E

O gate somente é aprovado quando a hipótese é testável, a evidência inicial justifica experimentação, o protocolo limita o risco, a coleta de evidência está definida e uma autoridade humana autoriza o uso experimental.

## 4. Fase E — Experimentar sob observação

### Entrada

Gate P → E aprovado e protocolo controlado vigente.

### Atividades obrigatórias

1. executar somente no escopo autorizado;
2. identificar cada aplicação e dependência operacional;
3. registrar resultados favoráveis, contrários e inconclusivos;
4. executar auditorias previstas;
5. comparar resultado com critérios pré-declarados;
6. revisar riscos e possibilidade de falsificação;
7. impedir que o conceito seja apresentado como consolidado ou normativo.

### Artefatos mínimos

- protocolo versionado;
- registros de execução;
- evidências primárias;
- relatórios de auditoria;
- registro de exceções e resultados negativos;
- matriz de dependências;
- revisão experimental.

### Gate E → V

O gate somente é aprovado quando existe uso operacional comprovado, recorrência suficiente no escopo, estabilidade metodológica, evidência documental consistente, dependência operacional verificável, tratamento de conflitos e revisão independente. A decisão deve declarar explicitamente o escopo de validade e seus limites.

## 5. Fase V — Validar dentro do escopo

### Entrada

Gate E → V aprovado, decisão formal emitida e registro oficial atualizado.

### Atividades obrigatórias

1. manter o conceito e seu escopo versionados;
2. monitorar novas aplicações, falhas e exceções;
3. impedir ampliação informal do escopo;
4. testar em projetos e domínios adicionais;
5. observar estabilidade ao longo do tempo;
6. avaliar compatibilidade com princípios e autoridades vigentes;
7. preparar análise de impacto constitucional quando aplicável.

### Artefatos mínimos

- dossiê de validação;
- declaração de escopo e limites;
- registro de maturidade atualizado;
- trilha longitudinal de evidências;
- matriz multidomínio;
- análise de compatibilidade e conflitos;
- decisão de revisão periódica.

### Gate V → C

O gate somente é aprovado quando há comprovação multidomínio, estabilidade longitudinal, aceitação metodológica suficiente, ausência de conflitos não resolvidos, compatibilidade constitucional, análise de impacto, proposta normativa e aprovação humana pela governança competente.

## 6. Fase C — Incorporar e governar

### Entrada

Gate V → C aprovado e incorporação efetiva à autoridade documental.

### Atividades obrigatórias

1. alterar a Constituição por processo próprio;
2. atualizar o Léxico Constitucional quando aplicável;
3. atualizar a Governança Oficial e documentos dependentes;
4. registrar versão, vigência, autoridade e histórico;
5. comunicar alcance normativo e plano de adoção;
6. monitorar evidências contraditórias e impactos regressivos.

### Artefatos mínimos

- decisão constitucional aprovada;
- Constituição vigente com o conhecimento incorporado;
- Léxico e Governança sincronizados quando aplicáveis;
- HISTORY/ROADMAP e mapa de dependências;
- plano de adoção e auditoria de conformidade.

## Relação entre Descobertas e Constituição

Discovery é a forma de registrar uma hipótese metodológica ou arquitetural ainda não consolidada. Maturidade científica e estado do Discovery Lifecycle são controles relacionados, mas distintos:

| Estado no Discovery Lifecycle | Maturidade científica admissível | Regra de relação |
|---|---|---|
| HIPÓTESE | P | Investigação ainda sem uso metodológico obrigatório |
| CANDIDATA | P ou E | Permanece P enquanto apenas preparada; torna-se E quando o uso experimental controlado começa |
| EM VALIDAÇÃO | E | Uso experimental está produzindo evidências; ainda não é V |
| VALIDADA | V | Exige decisão formal e escopo explícito; o nome do estado não dispensa o gate E → V |
| PROMOVIDA | V ou C | Recomendação/promoção ao método não é automaticamente constitucional; somente é C após incorporação efetiva à autoridade constitucional |
| CONSOLIDADA | V ou C | Consolidação operacional pode permanecer V; é C apenas quando Constituição, Léxico aplicável e Governança Oficial registram a incorporação |

Uma Discovery evolui da seguinte forma:

1. nasce de observação verificável e é registrada em Research;
2. recebe maturidade P enquanto hipótese investigável;
3. após gate, passa a E e é aplicada somente em experimento controlado;
4. acumula evidências, auditorias, resultados negativos e dependências;
5. após gate formal, passa a V com escopo explícito;
6. é testada em múltiplos domínios e longitudinalmente;
7. recebe revisão metodológica, arquitetural e constitucional;
8. somente após incorporação formal torna-se C e fundamento normativo.

Os estados preexistentes de Discoveries não são alterados por este documento. Divergências entre rótulo histórico e maturidade devem ser reconciliadas por GP específica, preservando a proveniência.

## Princípios da Promoção Científica

- **Promoção por Evidência:** cada gate depende de evidência suficiente e verificável.
- **Não Promoção por Popularidade:** recorrência textual, preferência ou uso informal não promove.
- **Escopo Explícito de Validação:** V declara alcance positivo, limites e condições.
- **Rastreabilidade Integral:** toda transição liga origem, evidência, decisão, autoridade e versão.
- **Preservação Histórica:** nenhum estado anterior ou resultado negativo é apagado.
- **Regressão Possível mediante novas evidências:** nova evidência pode reduzir escopo ou maturidade por processo formal.

## 9. Responsabilidades

| Papel funcional | Responsabilidade mínima | Limite de autoridade |
|---|---|---|
| Responsável pela pesquisa | Formular e registrar hipótese, fontes e critérios | Não promove o próprio conceito |
| Responsável experimental/metodológico | Executar protocolo e manter definição/escopo | Não amplia escopo sem revisão |
| Custodiante documental | Preservar versões, evidências, decisões e vínculos | Não decide mérito científico sozinho |
| Auditor/revisor independente | Verificar evidência, conflitos, repetibilidade e gate | Recomenda; não incorpora à Constituição |
| Autoridade humana de governança | Aprovar manutenção, promoção ou regressão | Deve fundamentar documentalmente |
| Autoridade constitucional humana | Aprovar incorporação ou retirada constitucional | Atua pelo processo constitucional vigente |

Uma mesma pessoa pode exercer mais de um papel somente quando isso for declarado; a revisão independente não pode ser assinada pela mesma função que produziu a evidência primária.

## 10. Registro de rastreabilidade

Cada conceito deve possuir uma cadeia reconstruível:

```text
origem
  → hipótese/Discovery
  → protocolo
  → execuções e evidências
  → auditorias e revisões
  → decisão de maturidade e escopo
  → dependências
  → eventual incorporação constitucional
  → revisões e regressões posteriores
```

O registro de transição deve conter conceito/versão, nível anterior, nível decidido, escopo, evidências favoráveis e contrárias, critérios avaliados, projetos/domínios, dependências, revisores, autoridade, data, vigência, documentos afetados e próxima revisão.

## 11. Protocolo de promoção

1. abrir GP específica para um ou mais conceitos identificados;
2. congelar o conjunto de evidências usado na decisão;
3. verificar critérios de saída e entrada, um a um;
4. documentar lacunas, conflitos e evidências contrárias;
5. obter revisão independente;
6. emitir recomendação;
7. obter decisão humana;
8. atualizar registros e documentos autorizados atomicamente;
9. verificar consistência e publicar a trilha de decisão.

Recomendação sem execução mantém o nível anterior. A GP-FW-02C, portanto, não alterou PA-02, PA-03 ou GDC-R; somente uma GP posterior poderá executar eventual E → V.

## 12. Protocolo de regressão

1. registrar a nova evidência e o risco;
2. identificar conceitos, escopos e dependências afetados;
3. suspender ampliação do uso quando necessário;
4. realizar revisão independente;
5. decidir manutenção, redução de escopo, regressão ou arquivamento;
6. atualizar todos os registros autorizados sem apagar o estado anterior;
7. se C for afetado, executar processo constitucional formal antes de retirar vigência;
8. comunicar impactos e acompanhar remediação.

Regressão não equivale a fracasso institucional; é mecanismo de correção científica e preservação da confiabilidade do framework.

## 13. Checklists dos gates

### P → E

- [ ] proveniência completa;
- [ ] hipótese testável;
- [ ] evidência inicial suficiente;
- [ ] protocolo e critérios pré-declarados;
- [ ] riscos e escopo delimitados;
- [ ] autorização humana.

### E → V

- [ ] uso operacional comprovado;
- [ ] recorrência no escopo;
- [ ] estabilidade metodológica;
- [ ] dependência operacional documentada;
- [ ] evidências favoráveis, negativas e inconclusivas preservadas;
- [ ] revisão independente;
- [ ] escopo e limites explícitos;
- [ ] decisão humana e registro oficial.

### V → C

- [ ] comprovação multidomínio;
- [ ] estabilidade longitudinal;
- [ ] aceitação metodológica suficiente;
- [ ] compatibilidade constitucional;
- [ ] conflitos resolvidos;
- [ ] análise de impacto e texto normativo;
- [ ] revisão constitucional;
- [ ] aprovação humana competente;
- [ ] incorporação efetiva e registro de vigência.

## 14. Aplicação futura

Este ciclo é referência obrigatória para futuras GPs de maturidade científica. Ele pode ser especializado por protocolos adicionais, mas nenhum protocolo subordinado pode criar quinto nível, eliminar gate, presumir universalidade, apagar histórico ou substituir autoridade humana por inteligência ou ferramenta.
