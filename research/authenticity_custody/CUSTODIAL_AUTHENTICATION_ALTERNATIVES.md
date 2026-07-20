# R-03 — Alternativas de Autenticação Custodial

Status: **P — CATÁLOGO DE PESQUISA; NÃO NORMATIVO**

Data: 2026-07-20

## 1. Método de comparação

Escala qualitativa:

- 1 — inadequado ou dependência crítica;
- 2 — baixo;
- 3 — médio;
- 4 — alto;
- 5 — muito alto.

Critérios:

- **IT:** independência tecnológica;
- **RT:** rastreabilidade;
- **SO:** simplicidade operacional;
- **AU:** auditabilidade;
- **CI:** continuidade institucional.

As notas são hipóteses comparativas para orientar experimentos. Não representam validação.

## 2. Matriz consolidada

| ID | Alternativa | IT | RT | SO | AU | CI | Conclusão inicial |
|---|---|---:|---:|---:|---:|---:|---|
| A-01 | Identidade nominal do custodiante | 5 | 2 | 5 | 1 | 1 | necessária para legibilidade, insuficiente para prova |
| A-02 | Credencial Custodial documental | 5 | 4 | 4 | 3 | 3 | útil para papel/escopo; precisa de proteção criptográfica |
| A-03 | Certificado Custodial próprio | 4 | 4 | 3 | 4 | 3 | potencial, mas enfrenta bootstrap e revogação |
| A-04 | Registro Oficial de Custódia | 5 | 5 | 4 | 4 | 4 | raiz institucional necessária; cópias ainda precisam autenticação |
| A-05 | Hash documental | 5 | 4 | 5 | 5 | 3 | excelente integridade; não prova emissor |
| A-06 | Assinatura digital destacada | 5 | 5 | 3 | 5 | 4 | prova forte de posse de chave; exige registro/rotação |
| A-07 | Chave pública do custodiante | 5 | 4 | 4 | 4 | 3 | necessária à verificação; vínculo institucional é problema central |
| A-08 | Cadeia de Atos Custodiais | 5 | 5 | 3 | 5 | 4 | preserva sequência; não impede fork alternativo sozinho |
| A-09 | Releases/registro de versões | 4 | 4 | 4 | 4 | 4 | organiza conjuntos oficiais; plataforma não pode ser raiz única |
| A-10 | Tag Git assinada | 3 | 4 | 4 | 4 | 3 | projeção prática; depende de Git e chave confiável |
| A-11 | Certificado X.509/PKI externa | 2 | 5 | 2 | 5 | 4 | forte ecossistema, maior complexidade e dependência de CA |
| A-12 | Carimbo temporal externo | 2 | 4 | 2 | 4 | 4 | evidência temporal adicional; dependência de TSA |
| A-13 | Publicação multiponto/checkpoints | 4 | 5 | 3 | 4 | 5 | reduz dependência e equivocações; exige reconciliação |
| A-14 | Múltiplos custodiantes/limiar | 4 | 5 | 1 | 5 | 5 | resiliente, mas altera governança e aumenta complexidade |
| A-15 | Conselho custodial | 5 | 5 | 1 | 4 | 5 | continuidade alta; incompatível com simplicidade/modelo atual sem nova GP |
| A-16 | Blockchain pública | 2 | 5 | 1 | 4 | 4 | prova de ancoragem, custo/infraestrutura desproporcionais |
| A-17 | Envelope Custodial em camadas | 5 | 5 | 3 | 5 | 5 | hipótese líder; combina controles mínimos portáveis |

## 3. Análise individual

### A-01 — Identidade nominal

**Mecanismo:** nome do titular no ato.

**Vantagem:** máximo de simplicidade e legibilidade.

**Falha:** qualquer terceiro pode copiar o nome. Não comprova integridade, posse de credencial, vigência ou cadeia.

**Uso potencial:** campo obrigatório, nunca prova exclusiva.

### A-02 — Credencial Custodial

**Mecanismo:** documento contendo `custodian_id`, designação, escopo, vigência e referências.

**Vantagem:** torna papel e competência portáveis.

**Falha:** credencial não assinada é copiável; credencial assinada desloca o problema para a confiança na chave emissora.

**Uso potencial:** camada de identidade/competência do envelope.

### A-03 — Certificado Custodial próprio

**Mecanismo:** credencial assinada que vincula titular, cargo e chave.

**Vantagem:** ligação verificável e formato potencialmente independente.

**Falha:** o primeiro certificado precisa de raiz de confiança; revogação, rotação e recuperação exigem política.

**Uso potencial:** objeto de pesquisa após definir bootstrap e sucessão.

### A-04 — Registro Oficial de Custódia

**Mecanismo:** registro institucional `METHODOLOGICAL_CUSTODIAN_REGISTER.md`.

**Vantagem:** já contém `CM-001`, titular, escopo, vigência e histórico.

**Falha:** uma cópia isolada pode ser alterada; o caminho no repositório não autentica por si.

**Uso potencial:** raiz institucional e fonte de competência, protegida por cadeia/assinatura.

### A-05 — Hash documental

**Mecanismo:** digest criptográfico por artefato.

**Vantagem:** simples, offline, independente e eficiente para detectar alterações. O [NIST FIPS 180-4](https://csrc.nist.gov/pubs/fips/180-4/upd1/final) documenta algoritmos de digest para essa finalidade.

**Falha:** atacante pode alterar documento e publicar novo hash. Hash não identifica autoridade.

**Uso potencial:** integridade obrigatória dentro de manifesto assinado; algoritmo deve ser identificado.

### A-06 — Assinatura digital destacada

**Mecanismo:** assinatura criptográfica de manifesto canônico.

**Vantagem:** mantém documentos legíveis intactos, permite verificação offline e separa conteúdo de prova.

**Falha:** depende de chave privada segura e registro autêntico da chave pública. Comprometimento e rotação exigem tratamento.

**Uso potencial:** componente central. [RFC 8032](https://www.rfc-editor.org/info/rfc8032/) e [RFC 9580](https://www.rfc-editor.org/info/rfc9580/) são opções abertas a experimentar, não escolhas ratificadas.

### A-07 — Chave pública do custodiante

**Mecanismo:** chave verificadora publicada com ID, algoritmo, fingerprint, escopo e vigência.

**Vantagem:** verificação independente e offline.

**Falha:** uma chave autodeclarada não comprova que pertence à Custódia; precisa ser introduzida por ato/registro confiável.

**Uso potencial:** Registro de Chaves Custodiais encadeado ao ato de designação.

### A-08 — Cadeia de Atos Custodiais

**Mecanismo:** cada manifesto referencia o digest do ato/checkpoint anterior.

**Vantagem:** ordem, continuidade e detecção de remoção/alteração.

**Falha:** duas cadeias concorrentes podem ser internamente válidas; são necessários checkpoints publicados e regra de resolução.

**Uso potencial:** componente central com publicação multiponto.

### A-09 — Releases e registro de versões

**Mecanismo:** versão oficial aponta para conjunto exato de manifestos/artefatos.

**Vantagem:** facilita distribuição, reconstrução e escopo.

**Falha:** release não assinada ou publicada em canal não autenticado pode ser forjada.

**Uso potencial:** camada oficial de distribuição ligada ao envelope.

### A-10 — Tag Git assinada

**Mecanismo:** tag anotada com assinatura criptográfica.

**Vantagem:** fluxo conhecido; Git permite criar e verificar tags assinadas e suporta backends diferentes ([git-tag](https://git-scm.com/docs/git-tag.html)).

**Falha:** pressupõe Git, confiança na chave e identificação do repositório oficial; não sobrevive como único mecanismo a mudança de infraestrutura.

**Uso potencial:** projeção opcional do release, nunca raiz exclusiva.

### A-11 — Certificado X.509/PKI

**Mecanismo:** certificado emitido por CA e cadeia de validação/revogação.

**Vantagem:** identidade, políticas e ferramentas maduras; o [RFC 5280](https://www.rfc-editor.org/info/rfc5280/) perfila certificados e CRLs X.509.

**Falha:** dependência de CA/política, expiração, revogação, custos e complexidade.

**Uso potencial:** integração opcional para ambientes regulados, não requisito universal.

### A-12 — Carimbo temporal

**Mecanismo:** token de autoridade de tempo sobre digest.

**Vantagem:** demonstra existência antes de um instante e pode apoiar validade histórica.

**Falha:** terceiro confiável, política e preservação adicionais. O [RFC 3161](https://www.rfc-editor.org/info/rfc3161/) depende de TSA.

**Uso potencial:** evidência suplementar em atos materiais.

### A-13 — Publicação multiponto/checkpoints

**Mecanismo:** mesmo manifesto/checkpoint publicado em filesystem, repositório e canal independente.

**Vantagem:** reduz aprisionamento, perda e fork silencioso.

**Falha:** conflito entre canais precisa de regra; mais operação.

**Uso potencial:** dois ou mais canais para checkpoints materiais, preservando arquivos idênticos.

### A-14 — Múltiplos custodiantes/assinatura limiar

**Mecanismo:** quórum de assinaturas ou chave compartilhada por limiar.

**Vantagem:** reduz ponto único e melhora continuidade.

**Falha:** altera a autoridade singular ratificada, aumenta indisponibilidade e requer política complexa.

**Uso potencial:** experimento futuro; não compatível com adoção imediata sem nova governança.

### A-15 — Conselho custodial

**Mecanismo:** órgão colegiado decide atos.

**Vantagem:** diversidade e sucessão.

**Falha:** cria nova estrutura de autoridade, quórum, conflitos e risco de governança paralela.

**Uso potencial:** somente pesquisa comparativa; não recomendado no modelo mínimo.

### A-16 — Blockchain pública

**Mecanismo:** ancoragem de digest em ledger público.

**Vantagem:** forte publicidade temporal e resistência à alteração.

**Falha:** dependência de rede/protocolo, custo, privacidade e complexidade; não prova competência ou identidade sozinha.

**Uso potencial:** não recomendado na hipótese mínima.

### A-17 — Envelope Custodial Portável em Camadas

**Mecanismo:** A-04 + A-07 + manifesto canônico + A-05 + A-06 + A-08 + A-09, com A-13 para checkpoints materiais.

**Vantagem:** cobre identidade, competência, integridade, oficialidade e continuidade sem fornecedor obrigatório.

**Falha:** precisa de schema, canonicalização, ferramenta, gestão de chave e protocolo de recuperação.

**Uso potencial:** H-R03-01, hipótese prioritária para prototipagem.

## 4. Formatos do manifesto

### F-01 — JSON canônico

- interoperável e estruturado;
- pode usar [RFC 8785](https://www.rfc-editor.org/rfc/rfc8785.html);
- exige implementação correta de canonicalização;
- bom para automação.

### F-02 — Formato textual rígido

- fácil de inspecionar;
- regras de encoding, newline, ordenação e escaping precisam ser definidas;
- risco de implementações divergentes.

### F-03 — CBOR determinístico/COSE

- compacto e próprio para assinatura;
- menor legibilidade humana e ferramentas adicionais;
- deve ser comparado apenas na fase de protótipo.

Hipótese inicial: JSON canônico + assinatura destacada oferece melhor equilíbrio entre auditabilidade humana, interoperabilidade e simplicidade, mas ainda requer ensaio com duas implementações.

## 5. Alternativas de vínculo de identidade

| Modelo | Raiz de confiança | Independência | Complexidade | Hipótese |
|---|---|---:|---:|---|
| Registro próprio + fingerprint | ato `CM-001`/sucessão | alta | média | preferido para núcleo mínimo |
| OpenPGP certificate | registro + certificado transferível | alta | média | bom formato opcional |
| X.509 | CA/política externa ou própria | média/baixa | alta | integração opcional |
| SSH signing key | allowed signers/registro | média | média | útil em Git, menos geral |
| DID/método específico | ledger/resolver/método | variável | alta | adiar; risco de dependência |

## 6. Alternativas de sucessão

| Cenário | Alternativa | Continuidade | Limitação |
|---|---|---|---|
| Transição ordinária | ato cross-signed por chave antiga e nova | forte | requer disponibilidade das duas chaves |
| Rotação técnica, mesmo titular | chave antiga assina introdução da nova | forte | falha se chave antiga perdida |
| Chave comprometida | revogação + nova chave por ato custodial reforçado | média | momento do comprometimento pode ser incerto |
| Incapacidade/falecimento | ato constitucional de sucessão + testemunhos/checkpoints | possível | ruptura não pode ser eliminada criptograficamente |
| Algoritmo obsoleto | reatestação periódica com algoritmo novo | forte se antecipada | não recupera confiança já perdida |

## 7. Hipótese recomendada para próxima fase

Prototipar A-17 com:

- credencial/registro `CM-001` como raiz institucional;
- chave de teste não oficial;
- manifesto JSON canônico;
- SHA-256 e segundo algoritmo configurável para agilidade;
- assinatura destacada;
- `previous_act_digest`;
- pacote portátil com manifesto, assinatura, chave pública e documentos;
- release Git opcional e cópia em filesystem;
- verificador offline independente.

O protótipo não deve usar chave real da Custódia nem produzir ato reconhecível como oficial.

## 8. Critérios de teste

- alteração de um byte deve falhar;
- troca de chave não registrada deve falhar;
- ato fora do escopo deve ser rejeitado semanticamente;
- remoção/reordenação da cadeia deve ser detectada;
- fork concorrente deve ser sinalizado;
- rotação válida deve preservar atos antigos;
- pacote deve ser verificável sem rede;
- mesma prova deve funcionar fora de Git;
- duas implementações devem produzir/verificar os mesmos vetores;
- operação normal deve permanecer compreensível para auditor humano.

## 9. Conclusão provisória

Nenhuma alternativa isolada satisfaz os cinco critérios. A-17 é a hipótese mais consistente por combinar controles institucionais e criptográficos portáveis. Sua simplicidade ainda precisa ser demonstrada experimentalmente; portanto permanece P.
