# GP-FW-03A — Gate de Promoção da H-R03-01 para Experimental (E)

Status: **GATE APROVADO — TRANSIÇÃO P → E EXECUTADA DOCUMENTALMENTE**

Data: 2026-07-20 (America/Sao_Paulo)

Autoridade: Custódia Metodológica do ICFACTORY — titular Henderson Mauricio Batista, ato `CM-001`

Conceito: H-R03-01 — Envelope Custodial Portável em Camadas

## 1. Decisão executiva

O gate **Pesquisa (P) → Experimental (E)** está **APROVADO**.

A hipótese foi claramente caracterizada, possui fundamentação técnica suficiente, foi confirmada em PoC controlada, apresentou resultados reproduzíveis, documentou limitações materiais, manteve escopo isolado e forneceu justificativa compatível com os critérios P → E do `SCIENTIFIC_MATURITY_MODEL.md`.

Por decisão desta GP:

> H-R03-01 passa a integrar oficialmente o conjunto de conceitos experimentais do ICFACTORY, permanecendo sujeita à evolução, validação adicional, regressão ou futura promoção, conforme o Scientific Maturity Model.

A promoção é limitada à maturidade **Experimental (E)**. Não constitui validação V, constitucionalização C, adoção institucional, princípio oficial ou autorização para atos/releases/chaves reais.

## 2. Escopo documental e congelamento de evidências

Foram revisados exclusivamente os oito documentos autorizados:

| Documento | SHA-256 |
|---|---|
| `research/authenticity_custody/AUTHENTICITY_CUSTODIAL_RESEARCH.md` | `E66ED53CB885FC69057304D36F171A95D6276CFCD3F52F99D9D5107B9C3B54E5` |
| `research/authenticity_custody/CUSTODIAL_AUTHENTICATION_ALTERNATIVES.md` | `4A003500B28F994AB7272CB3918A1C5EBF45929A50CF6F720A6511A0BE6B0062` |
| `research/authenticity_custody/INITIAL_HYPOTHESES.md` | `C536B2F17121715F572F8E862789A1D599525AFF2C7DBA747F8D589F4F069AB4` |
| `research/authenticity_custody/RESEARCH_LOG.md` | `4B6E7E82F2BE8BF1BDC410989BB5DF10879906111D277BA01371E2A2E24BE1CB` |
| `research/authenticity_custody/poc/POC_EXECUTION_REPORT.md` | `3F789E0C8733C9735496C05BA4540C75D22F32229CE97C40B8E6CDE8706F8CFD` |
| `research/authenticity_custody/poc/POC_VALIDATION_RESULTS.md` | `402687E4D67E8EB13AE02ED0FB6F9135D2518E2D46AD6C121BB6BC3F42EC955F` |
| `research/authenticity_custody/poc/POC_LIMITATIONS.md` | `277DF3137CB825A7CEF8688A1C50B030B2DB263B191BA2A33B9D001CF40537AE` |
| `research/authenticity_custody/poc/POC_RECOMMENDATIONS.md` | `10A9418A9A2855F3D7050EB3D318EE3194CF0FFDA4C7216B7DC375401E85F327` |

O pacote público da PoC foi usado somente para reexecução do verificador e confirmação das evidências já registradas. Não foi tratado como documento adicional de decisão.

## 3. Método do gate

Foi aplicado ACI(R):

1. congelamento dos documentos por hash;
2. leitura das caracterizações, alternativas, hipóteses, log, execução, resultados, limitações e recomendações;
3. reexecução read-only do verificador independente;
4. avaliação separada dos sete critérios obrigatórios;
5. distinção entre prova técnica, autenticidade institucional e maturidade;
6. registro de riscos, restrições e critérios E → V;
7. decisão custodial limitada à transição P → E.

## 4. Reexecução independente do pacote

O verificador Node.js foi executado novamente no pacote público, sem escrita e sem acesso às chaves privadas.

| Cenário | Resultado reconfirmado |
|---|---|
| S1 — Envelope primário | PASS |
| S2 — Múltiplos canais simulados | PASS |
| S3 — Documento adulterado | PASS — adulteração detectada |
| S4 — Substituição não autorizada de chave | PASS — rejeitada |
| S5 — Rotação autorizada de chave | PASS |
| S6 — Rastreabilidade | PASS |

O resultado manteve `institutional_authenticity_from_envelope_alone = false`, preservando a limitação do bootstrap em vez de ocultá-la.

## 5. Avaliação dos critérios obrigatórios

### 5.1 A hipótese foi claramente caracterizada?

**APROVADO.** `INITIAL_HYPOTHESES.md` define H-R03-01, componentes, fundamentação, predições testáveis, critérios de falsificação e estado. `AUTHENTICITY_CUSTODIAL_RESEARCH.md` separa identidade, competência, integridade, oficialidade e continuidade.

### 5.2 Existe fundamentação técnica suficiente?

**APROVADO para E.** A pesquisa comparou 17 alternativas, identificou limites de mecanismos isolados e fundamentou a combinação de registro, chave pública, manifesto, hashes, assinatura, cadeia, versão e publicação multiponto. A fundamentação sustenta experimento, não adoção oficial.

### 5.3 A PoC confirmou a hipótese?

**APROVADO.** A PoC demonstrou envelope válido, detecção de adulteração, rejeição de chave não autorizada, rotação cross-signed, ato pós-rotação e rastreabilidade linear. Todos os cenários obtiveram PASS.

### 5.4 Os resultados são reproduzíveis?

**APROVADO com limite.** Duas execuções com chaves aleatórias alcançaram 6/6. Um verificador Node.js distinto do produtor Python foi reexecutado em modo read-only. A reprodução ocorreu no mesmo host/SO; independência organizacional e multiplataforma permanecem pendentes.

### 5.5 As limitações foram explicitamente documentadas?

**APROVADO.** `POC_LIMITATIONS.md` registra bootstrap, armazenamento de chave, independência, canonicalização, tempo, revogação, forks, validação semântica, release, escala, agilidade criptográfica e risco humano.

### 5.6 O escopo permanece controlado?

**APROVADO.** Foram usados namespace, titular, designação, atos, chaves, documentos, canais e releases fictícios. Nenhuma chave privada foi incorporada ao pacote público. Nenhum artefato alegou autoridade oficial.

### 5.7 Existe justificativa técnica para promoção a Experimental?

**APROVADO.** Há hipótese testável, protocolo executado, evidência inicial, resultado reproduzível, falhas detectáveis, riscos conhecidos, restrições declaradas e próximos experimentos definidos. Esses elementos satisfazem o gate P → E sem alcançar os requisitos E → V.

## 6. Matriz final do gate

| Critério | Resultado | Condição |
|---|---|---|
| Caracterização | APROVADO | completa e falsificável |
| Fundamentação técnica | APROVADO | suficiente para experimento |
| Confirmação por PoC | APROVADO | 6/6 cenários |
| Reprodutibilidade | APROVADO | limitada ao mesmo host/SO |
| Limitações | APROVADO | explícitas e materiais |
| Escopo controlado | APROVADO | totalmente fictício |
| Justificativa P → E | APROVADO | evidência suficiente para E |

Resultado: **7/7 APROVADOS**.

## 7. Nova maturidade e escopo oficial

| Campo | Estado após GP-FW-03A |
|---|---|
| Conceito | H-R03-01 — Envelope Custodial Portável em Camadas |
| Estado anterior | Pesquisa (P) |
| Estado vigente | **Experimental (E)** |
| Data | 2026-07-20 |
| Gate | GP-FW-03A |
| Autoridade | Custódia Metodológica — `CM-001` |
| Escopo | experimentação controlada, fictícia e rastreável |
| Validado | NÃO |
| Constitucional | NÃO |
| Uso oficial | PROIBIDO |

Os documentos de Research permanecem como evidência histórica P/PoC e não são reescritos. O estado vigente é registrado neste relatório e na seção de transições do `SCIENTIFIC_MATURITY_MODEL.md`.

## 8. Restrições de uso

H-R03-01 pode ser utilizada experimentalmente somente quando:

- o ambiente for explicitamente classificado como teste;
- identidades, atos, chaves, credenciais e releases forem fictícios;
- chaves oficiais não forem usadas;
- namespace de teste impedir confusão com ICFACTORY oficial;
- protocolo, critérios e resultados forem versionados;
- evidências favoráveis, negativas e inconclusivas forem preservadas;
- falhas forem fechadas como `INVALID` ou `INDETERMINATE`;
- não houver alegação de autenticidade institucional real;
- houver revisão humana e rastreabilidade integral;
- cada experimento puder ser interrompido sem afetar governança vigente.

É proibido:

- autenticar ato custodial real;
- criar credencial/chave oficial;
- publicar release oficial;
- usar a hipótese como princípio ou regra consolidada;
- tratar assinatura válida como legitimidade constitucional;
- omitir o problema de bootstrap;
- promover implicitamente para V.

## 9. Riscos remanescentes

| Risco | Impacto | Tratamento exigido |
|---|---|---|
| Bootstrap da raiz | fork autoconsistente pode simular oficialidade | pin/checkpoint externo e independente |
| Proteção da chave | comprometimento permite assinatura indevida | cerimônia, armazenamento, backup e resposta |
| Revogação/recuperação | atos no intervalo podem ficar disputados | estados temporais e protocolo de incidente |
| Fork/equivocação | duas cadeias podem ser internamente válidas | checkpoints multiponto e regra de conflito |
| Canonicalização | implementações podem assinar bytes diferentes | schema e vetores multiplataforma |
| Tempo confiável | ordem/validade histórica podem ser contestadas | política temporal e evidência opcional externa |
| Competência semântica | assinatura válida pode exceder escopo | verificação de autoridade/gate separada |
| Dependência operacional | ferramentas podem se tornar SSOT indevido | prova portável e verificadores independentes |
| Obsolescência | algoritmos podem perder segurança | agilidade e reatestação longitudinal |

## 10. Recomendações para a etapa Experimental

1. E-01 — testar bootstrap por fingerprint/checkpoint multiponto;
2. E-02 — formalizar schema experimental e canonicalização;
3. E-03 — simular rotação, revogação, comprometimento e perda de chave;
4. E-04 — testar forks/checkpoints concorrentes;
5. E-05 — reproduzir em outro host, sistema operacional e implementação;
6. E-06 — executar piloto em projeto com namespace e autoridade separados;
7. E-07 — obter auditoria independente e medir custo/erro operacional;
8. manter todas as chaves e identidades reais fora do experimento.

## 11. Critérios necessários para futura promoção E → V

Uma futura GP somente poderá considerar V se houver, no mínimo:

- escopo de validação explícito e versionado;
- bootstrap institucional resolvido sem fornecedor exclusivo;
- schema/canonicalização reproduzíveis por implementações independentes;
- execução em múltiplos hosts, sistemas e ambientes;
- repetição longitudinal, não apenas duas execuções locais;
- protocolo testado de rotação, revogação, perda e recuperação;
- detecção de forks/equivocações entre canais independentes;
- verificação separada de criptografia, cadeia, chave, competência e oficialidade;
- piloto em ao menos um projeto externo ao contexto de origem;
- revisão de segurança independente;
- métricas de complexidade, disponibilidade e erro humano;
- dependência operacional comprovada no escopo;
- conflitos conhecidos resolvidos ou delimitados;
- evidências negativas e limitações preservadas;
- decisão custodial própria E → V.

## 12. Respostas ao critério de encerramento

- **Gate aprovado ou reprovado?** **APROVADO**, por 7/7 critérios.
- **H-R03-01 passa oficialmente para Experimental (E)?** **SIM**, a partir desta GP, no escopo declarado.
- **Quais restrições permanecem?** Teste fictício, sem chaves/credenciais/releases oficiais, sem alegação de autenticidade real e com todos os riscos da seção 9.
- **O conceito pode ser utilizado experimentalmente?** **SIM**, somente sob protocolo controlado, rastreável, reversível e não oficial.

## 13. Alterações e versionamento autorizados

Esta GP cria `GP_FW_03A_EXPERIMENTAL_GATE_REPORT.md` e acrescenta ao `SCIENTIFIC_MATURITY_MODEL.md` exclusivamente o registro da transição H-R03-01 P → E. As definições e critérios do modelo não foram alterados.

O commit autorizado pela aprovação deverá conter apenas:

- os oito documentos de evidência revisados, ainda não rastreados;
- este relatório;
- `SCIENTIFIC_MATURITY_MODEL.md` com o registro mínimo da transição.

Nenhum outro arquivo pendente deve ser incluído. Nenhum push é autorizado por esta GP sem confirmação explícita posterior do custodiante.

## 14. Preservação

Constituição, Léxico Constitucional, Custódia Metodológica, Discovery Lifecycle, conceitos existentes e documentos de pesquisa não foram reescritos. Nenhuma credencial, chave ou release oficial foi criada. A promoção limita-se a P → E e permanece sujeita a regressão.
