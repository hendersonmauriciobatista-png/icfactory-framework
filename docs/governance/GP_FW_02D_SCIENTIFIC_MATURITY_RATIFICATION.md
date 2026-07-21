# GP-FW-02D — Ratificação da Escala de Maturidade Científica

Status: **CONCLUÍDA — MODELO P/E/V/C RATIFICADO; NENHUM CONCEITO PROMOVIDO**

Data: 2026-07-20 (America/Sao_Paulo)

## 1. Veredito executivo

O ICFACTORY passa a reconhecer oficialmente, em sua governança científica, uma escala com **exatamente quatro níveis**:

1. Pesquisa (P);
2. Experimental (E);
3. Validado (V);
4. Constitucional (C).

Foram formalizados definição, entrada, saída, responsabilidades, rastreabilidade, requisitos de evidência, requisitos de revisão e regressão para cada nível. Também foram definidos os gates P → E, E → V e V → C e a relação entre a escala científica e os estados preexistentes do Discovery Lifecycle.

Esta GP ratifica o **modelo**, não a maturidade de conceitos individuais. PA-02, PA-03 e GDC-R continuam com o estado documental anterior. A recomendação B da GP-FW-02C permanece uma recomendação formal ainda não executada.

## 2. Autoridade e escopo auditado

Autoridade documental de origem: `C:\HANDA_CORE\ICFACTORY`, conforme GP-FW-02.

Documentação da GP-FW-02B examinada:

- `C:\Users\Guiuliano\icfactory-framework\docs\audits\GP_FW_02B_BASELINE_AND_SCIENTIFIC_MATURITY_AUDIT.md`
- `C:\Users\Guiuliano\icfactory-framework\docs\audits\SCIENTIFIC_MATURITY_REGISTER.md`
- `C:\Users\Guiuliano\icfactory-framework\docs\audits\SCIENTIFIC_DEBT_REGISTER.md`
- `C:\Users\Guiuliano\icfactory-framework\docs\audits\SCIENTIFIC_MATURITY_MATRIX.csv`

Documentação da GP-FW-02C examinada:

- `C:\Users\Guiuliano\icfactory-framework\docs\governance\GP_FW_02C_CONCEPT_PROMOTION_REVIEW.md`
- `C:\Users\Guiuliano\icfactory-framework\docs\governance\CONCEPT_PROMOTION_MATRIX.csv`

Autoridades complementares examinadas:

- `C:\HANDA_CORE\AGENTS.md`
- `C:\HANDA_CORE\ICFACTORY\research\DISCOVERY_LIFECYCLE.md`
- `C:\HANDA_CORE\ICFACTORY\CONSTITUTION.md`, somente para confirmar o limite de autoridade e a ausência de alteração;
- `C:\HANDA_CORE\ICFACTORY\CONSTITUTIONAL_LEXICON.md`, somente para confirmar a ausência de alteração.

## 3. Método

Foi aplicado ACI(R), com leitura passiva e separação entre evidência e intervenção:

1. inventário e hash SHA-256 dos seis entregáveis das GP-FW-02B/02C;
2. importação integral das duas matrizes CSV;
3. conferência das classificações, recomendações e dívidas;
4. confronto com estados e critérios do `DISCOVERY_LIFECYCLE.md`;
5. identificação de ambiguidades entre estado de workflow, maturidade e recomendação;
6. síntese do modelo sem alteração dos documentos de origem;
7. validação estrutural dos três entregáveis desta GP.

Hashes usados para congelar o corpus decisório:

| Documento | SHA-256 |
|---|---|
| GP_FW_02B_BASELINE_AND_SCIENTIFIC_MATURITY_AUDIT.md | `E5C3FDC28FBEB2A8139993DBE856B9ABC130686CB650C47E0EADAE584DD68239` |
| SCIENTIFIC_MATURITY_REGISTER.md | `08F01F06621ADB3D092882829F36EDC51C70C59D0A7DF290C112942EF340A571` |
| SCIENTIFIC_DEBT_REGISTER.md | `0C4C8A88FC7D3C312C9B8A258CD0DA7C278577ED90CD6AC5E47650FC1C9B1028` |
| SCIENTIFIC_MATURITY_MATRIX.csv | `6CE98F5E0D9B5CDB85C087B99FF35687A7893733568773DFCF44E21E370F59C1` |
| GP_FW_02C_CONCEPT_PROMOTION_REVIEW.md | `2DDB806D321308523ABD2EE12399F957375216096A56E0C644040AD4AE45B2D1` |
| CONCEPT_PROMOTION_MATRIX.csv | `51A0F232A575DF33C4FDBE77730E90DA97F7D8FC7268F73D4C35CF8D50B6DF6F` |

## 4. Coerência da evolução científica observada

### Evidências de coerência

- A GP-FW-02B já utilizava P, E, V e C, definindo P como pesquisa/hipótese, E como uso experimental, V como validação limitada ao escopo e C como incorporação constitucional.
- A matriz da GP-FW-02B contém 28 conceitos: P=8, E=16, V=3 e C=1.
- O `DISCOVERY_LIFECYCLE.md` determina evolução por evidências, proveniência completa, validação, revisão e promoção controlada.
- A GP-FW-02C distinguiu permanência experimental, recomendação de validação e recomendação constitucional, preservando explicitamente a diferença entre uso e promoção.
- A GP-FW-02C avaliou 17 itens: 14 decisões A, 3 decisões B e nenhuma decisão C.

Essas evidências comprovam que a escala de quatro níveis já era operacionalmente usada, embora ainda não estivesse definida em um documento oficial próprio.

### Ambiguidades resolvidas

1. **P/E/V/C versus A/B/C:** P/E/V/C são níveis científicos. A/B/C da GP-FW-02C são resultados de revisão e não substituem o nível atual.
2. **Uso versus validação:** uso experimental pode justificar E; somente o gate completo E → V e uma decisão formal produzem V.
3. **Validação versus universalidade:** V é sempre limitado ao escopo declarado.
4. **Promoção versus Constituição:** uma recomendação ou um estado de Discovery chamado `PROMOVIDA` não constitui C sem incorporação efetiva à Constituição e autoridades aplicáveis.
5. **Consolidação operacional versus constitucional:** conhecimento consolidado internamente pode continuar V.
6. **Frequência versus evidência:** repetição textual ou popularidade não promove maturidade.
7. **Regressão:** níveis podem ser reduzidos quando nova evidência enfraquece a conclusão; C exige processo constitucional para perder vigência.

### Divergências históricas preservadas

O corpus anterior contém combinações como `Experimental (P — hipótese em monitoramento)`. A GP-FW-02D não reclassifica esses registros. O novo modelo determina que futuras decisões separem:

- nível científico vigente;
- estado do Discovery Lifecycle;
- nível de uso;
- decisão/recomendação da GP.

A normalização retroativa desses campos exige GP própria e deve preservar os rótulos históricos.

Também foi preservada a diferença entre os 16 itens de dívida da GP-FW-02B e os 17 itens revisados na GP-FW-02C: “Revisão Explícita” e “Preservação Histórica”, antes agregadas, foram avaliadas separadamente na GP-FW-02C. Isso não representa criação de conceito nesta ratificação.

## 5. Modelo ratificado

| Nível | Nome | Estado essencial | Gate de saída |
|---|---|---|---|
| 1 | Pesquisa (P) | Hipótese/Discovery em investigação, ainda sem dependência obrigatória | Evidência suficiente e autorização para experimento controlado |
| 2 | Experimental (E) | Uso limitado, rastreado e falsificável | Uso operacional comprovado, recorrência, estabilidade e escopo explícito |
| 3 | Validado (V) | Conhecimento comprovado dentro do escopo observado | Multidomínio, estabilidade longitudinal, aceitação e compatibilidade constitucional |
| 4 | Constitucional (C) | Conhecimento incorporado às autoridades normativas | Sem nível superior; sujeito a revisão/regressão formal |

O detalhamento normativo está em `SCIENTIFIC_MATURITY_MODEL.md`; o procedimento dos gates está em `KNOWLEDGE_EVOLUTION_LIFECYCLE.md`.

## Ciclo Oficial de Evolução do Conhecimento

```text
Pesquisa (P)
     ↓
Experimental (E)
     ↓
Validado (V)
     ↓
Constitucional (C)
```

Cada seta representa uma decisão formal, nunca consequência automática de tempo, popularidade ou frequência de uso.

## Princípios da Promoção Científica

São ratificados os seguintes princípios:

- **Promoção por Evidência:** somente evidência suficiente e verificável autoriza transição.
- **Não Promoção por Popularidade:** uso difundido, repetição ou preferência não substituem validação.
- **Escopo Explícito de Validação:** toda decisão V declara alcance e limites.
- **Rastreabilidade Integral:** origem, evidência, auditoria, decisão, versão e autoridade devem ser reconstruíveis.
- **Preservação Histórica:** nenhum estado, resultado negativo ou decisão anterior pode ser apagado.
- **Regressão Possível mediante novas evidências:** maturidade e escopo podem ser reduzidos por processo formal.

## Relação entre Descobertas e Constituição

O Discovery Lifecycle é o workflow específico de observação, hipótese, candidatura, validação, promoção e consolidação. P/E/V/C é a escala científica transversal que mede a força institucional do conhecimento.

Uma Discovery começa em Research, recebe P enquanto investigada, passa a E após autorização de experimentação, pode alcançar V após uso comprovado e decisão com escopo, e somente alcança C quando a autoridade constitucional incorpora efetivamente o conhecimento ao ICFACTORY.

Não existe equivalência automática entre nomes dos estados do Discovery Lifecycle e maturidade. Em especial:

- `CANDIDATA` pode ser P ou E, conforme exista ou não experimento em curso;
- `VALIDADA` deve satisfazer o gate E → V e declarar escopo;
- `PROMOVIDA` ou `CONSOLIDADA` somente é C com incorporação constitucional efetiva.

## 9. Responsabilidades ratificadas

- **Responsável pela pesquisa:** registra hipótese, origem, fontes e critérios.
- **Responsável experimental/metodológico:** executa e mantém o escopo autorizado.
- **Custodiante documental:** preserva versões, evidências e decisões.
- **Auditor/revisor independente:** verifica critérios, conflitos e reprodutibilidade.
- **Autoridade humana de governança:** decide manutenção, promoção ou regressão.
- **Autoridade constitucional humana:** decide incorporação ou retirada constitucional pelo processo vigente.

Inteligência, Harness ou agente pode auxiliar análise e execução, mas não possui autoridade decisória autônoma.

## 10. Rastreabilidade e requisitos de revisão

Toda transição deverá registrar:

- conceito e versão;
- origem e primeira ocorrência;
- nível anterior e nível decidido;
- escopo e limites;
- evidências favoráveis, contrárias e inconclusivas;
- projetos, domínios, auditorias e dependências;
- critérios de entrada/saída avaliados;
- revisores e autoridade humana;
- data, vigência, documentos afetados e próxima revisão.

Revisões são periódicas em V e C e extraordinárias quando surgirem evidências contraditórias, falhas, mudanças de escopo ou conflitos normativos. Promoções e regressões preservam integralmente o histórico.

## 11. Impacto da ratificação

### Metodológico

O framework passa a possuir linguagem única para distinguir investigação, uso experimental, validação limitada e autoridade constitucional.

### Científico

Os gates tornam explícitos falsificação, evidência negativa, escopo e regressão, reduzindo promoção tácita e dívida científica invisível.

### Documental

Futuras matrizes e registros deverão manter campos separados para maturidade, estado de Discovery, uso e decisão de revisão.

### Governança

Somente decisão humana formal altera maturidade; C exige incorporação às autoridades constitucionais. A ratificação não modifica autoridades preexistentes.

### Conceitos existentes

Nenhum impacto de classificação nesta GP. PA-02, PA-03 e GDC-R permanecem E até eventual ratificação E → V em programa específico. Os 14 conceitos mantidos em A pela GP-FW-02C permanecem com seus estados anteriores.

## 12. Respostas ao critério de encerramento

1. **O ICFACTORY passa a reconhecer oficialmente quatro níveis de maturidade científica?** Sim. Pesquisa (P), Experimental (E), Validado (V) e Constitucional (C), exatamente esses quatro.
2. **Os critérios de transição entre níveis estão formalizados?** Sim. Os gates P → E, E → V e V → C possuem critérios de entrada, saída, evidência, revisão, responsabilidade e decisão.
3. **Existe definição explícita para cada estado?** Sim. Cada nível possui definição, características, requisitos e regras de regressão.
4. **Existe rastreabilidade entre Discovery, Pesquisa, Validação e Constituição?** Sim. O ciclo e a tabela de relação preservam origem, workflow de Discovery, nível científico, evidências, decisão e incorporação constitucional.
5. **O modelo pode ser utilizado como referência para futuras promoções de conceitos?** Sim. Ele é a referência oficial de governança científica para futuras GPs, sem substituir o processo constitucional vigente.

## 13. Não promoção e preservação

Esta GP criou somente:

- `docs/governance/SCIENTIFIC_MATURITY_MODEL.md`;
- `docs/governance/KNOWLEDGE_EVOLUTION_LIFECYCLE.md`;
- `docs/governance/GP_FW_02D_SCIENTIFIC_MATURITY_RATIFICATION.md`.

Nenhum conceito foi promovido. Constituição, Léxico Constitucional, Discovery Lifecycle, registros das GP-FW-02B/02C, HANDA_CORE e PROTEUS não foram alterados. Nenhum commit e nenhum push foram executados.

## 14. Próximo controle recomendado

Executar uma GP de conformidade dos registros científicos para separar retrospectivamente, sem perda histórica, os campos `maturidade`, `estado da Discovery`, `nível de uso` e `decisão de revisão`. Somente depois deverá ser aberta uma GP de ratificação E → V para PA-02, PA-03 e GDC-R segundo os gates agora oficiais.
