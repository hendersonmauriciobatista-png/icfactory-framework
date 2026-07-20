# R-03 — Pesquisa sobre Autenticidade Custodial

Status: **P — PESQUISA ATIVA; FASE INICIAL CONCLUÍDA**

Data de abertura: 2026-07-20 (America/Sao_Paulo)

Classificação: conhecimento de Research, não normativo

## 1. Questão central

Como terceiros podem comprovar, de forma objetiva, independente e auditável, que um ato custodial foi realmente emitido pela autoridade oficial do ICFACTORY e que os documentos associados não foram alterados ou substituídos?

## 2. Escopo e não intervenção

A pesquisa investiga identidade, legitimidade, integridade documental, continuidade de custódia e validação histórica. Não altera Constituição, Léxico Constitucional, Custódia Metodológica, Scientific Maturity Model ou conceitos existentes. Não cria princípio, credencial, certificado, chave, assinatura, release ou ato oficial.

Todos os mecanismos descritos são alternativas ou hipóteses em maturidade P.

## 3. Corpus institucional

Fontes locais principais:

- `METHODOLOGICAL_CUSTODY_MODEL.md` — define papel, escopo e exigência de ato explícito;
- `COMMUNITY_CONTRIBUTION_POLICY.md` — separa contribuição de método oficial;
- `METHODOLOGICAL_CUSTODIAN_REGISTER.md` — registra `CM-001`, titular e vigência;
- `CUSTODIAL_APPOINTMENT_POLICY.md` — disciplina sucessão e vacância;
- `GP_FW_02F_METHODOLOGICAL_CUSTODIAN_APPOINTMENT.md` — designa Henderson Mauricio Batista;
- Constituição — exige autoridade explícita, governança unificada e evolução auditável;
- Léxico Constitucional — define papel, ato, escopo, competência, proveniência e evidência verificável.

O corpus atual permite verificar **quem foi designado**, **qual o escopo** e **quando a designação entrou em vigor**. Ele ainda não fornece prova criptográfica de que uma cópia específica de um ato foi emitida pelo titular nem mecanismo independente para distinguir uma história oficial de um fork documental bem-formado.

## 4. Caracterização do problema

Autenticidade Custodial possui cinco dimensões distintas:

1. **Identidade:** quem controla a identidade/credencial usada no ato?
2. **Competência:** essa pessoa era titular vigente e podia praticar aquele tipo de ato?
3. **Integridade:** o conteúdo verificado é idêntico ao conteúdo emitido?
4. **Oficialidade:** o ato integra a cadeia e a versão oficialmente reconhecidas?
5. **Continuidade:** a prova continua verificável após rotação de chave, troca de titular, mudança de repositório ou desaparecimento de fornecedor?

Nenhum mecanismo isolado resolve as cinco dimensões:

- nome e declaração resolvem legibilidade, mas são copiáveis;
- hash detecta alteração, mas não identifica emissor;
- assinatura prova posse de chave, mas não liga a chave à Custódia sem registro confiável;
- certificado liga identidade segundo uma política, mas introduz emissor, validade e revogação;
- tag/release prova posição em um repositório, mas não define por si qual repositório é oficial;
- registro oficial define autoridade, mas uma cópia do registro pode ser forjada;
- cadeia de hashes detecta ruptura, mas pode existir um fork alternativo coerente.

## 5. Modelo de ameaça inicial

| Ameaça | Exemplo | Controle necessário |
|---|---|---|
| Falsificação de autoria | terceiro publica ato em nome do custodiante | assinatura + vínculo entre chave e titularidade |
| Alteração de conteúdo | documento modificado após emissão | digest criptográfico + assinatura do manifesto |
| Fork com aparência oficial | cópia replica nomes e estrutura | identificador do framework + cadeia oficial + canais independentes |
| Reuso fora de escopo | assinatura válida usada para ato não autorizado | tipo de ato, competência e escopo no manifesto |
| Chave comprometida | atacante assina novos atos | revogação, rotação, data, registro de chave e resposta a incidente |
| Substituição de custodiante | sucessor precisa preservar atos antigos | registro temporal de chaves e ato de transição |
| Plataforma indisponível | forge/repositório desaparece | artefatos portáveis e múltiplas cópias verificáveis |
| Obsolescência criptográfica | algoritmo deixa de ser seguro | agilidade algorítmica e reatestação preservando prova anterior |
| Equivocação | emissor cria duas cadeias conflitantes | encadeamento, publicação multiponto e reconciliação de checkpoints |

## 6. O que caracteriza um Ato Custodial autêntico?

Hipótese operacional inicial: um ato é autenticamente atribuível quando um terceiro consegue verificar cumulativamente:

1. identidade institucional única do ICFACTORY;
2. identidade do titular e ato de designação vigente no instante declarado;
3. competência do titular para o tipo e escopo do ato;
4. representação canônica e inequívoca do ato;
5. digest dos documentos/artefatos cobertos;
6. assinatura digital verificável com chave registrada e válida naquele instante;
7. vínculo com o ato anterior ou checkpoint oficial da cadeia;
8. identificador de versão/release quando o ato produzir versão;
9. ausência de revogação, substituição ou conflito não resolvido aplicável;
10. preservação do manifesto, assinatura, chave pública, registro e evidências necessárias à reconstrução.

Assinatura válida sem competência, escopo ou cadeia oficial comprova apenas que determinada chave assinou bytes. Não comprova legitimidade custodial completa.

## 7. Como distinguir documentos oficiais de documentos derivados ou forks?

Propõe-se pesquisar três classificações descritivas:

- **Oficial verificável:** cadeia, titularidade, chave, assinatura, conteúdo e versão satisfazem os controles publicados pelo ICFACTORY.
- **Derivado declarado:** preserva referência ao ato oficial de origem, informa transformações e não afirma autoridade oficial.
- **Fork:** possui história ou conteúdo independente. Pode ser legítimo como fork, mas não é oficial sem ato custodial que o incorpore.

Nome de arquivo, logotipo, domínio, organização Git, branch, tag ou layout não deve ser prova exclusiva. A prova deve viajar com artefatos portáveis e ser verificável fora da infraestrutura de publicação.

## 8. Alternativa tecnicamente mais consistente

### H-R03-01 — Envelope Custodial Portável em Camadas

A hipótese líder combina controles independentes:

1. **Registro Oficial de Custódia:** titular, designação, escopo e vigência.
2. **Registro de Chaves Custodiais:** chave pública, impressão digital, algoritmo, finalidade, início/fim, rotação e revogação.
3. **Manifesto Canônico do Ato:** dados mínimos do ato em formato determinístico e portável.
4. **Digests dos artefatos:** algoritmo identificado e digest de cada documento coberto.
5. **Assinatura digital destacada:** assinatura do manifesto canônico, separada dos documentos legíveis.
6. **Cadeia de Atos:** referência criptográfica ao ato/checkpoint anterior.
7. **Registro de versão/release:** versão semântica e conjunto exato de artefatos.
8. **Publicação multiponto:** cópias em canais independentes para reduzir dependência e detectar equivocações.

Exemplo de campos a investigar no manifesto, sem constituir schema oficial:

```text
framework_id
act_id
act_type
custodian_id
appointment_act_id
custodial_scope
issued_at
effective_at
previous_act_digest
artifact_digests[] { path, media_type, hash_algorithm, digest }
version_or_release
signature_algorithm
key_id
```

O manifesto precisa de canonicalização para que diferentes implementações produzam os mesmos bytes. O [RFC 8785](https://www.rfc-editor.org/rfc/rfc8785.html) descreve uma forma de canonicalizar JSON para hashing e assinatura; ele é referência de pesquisa, não escolha ratificada.

## 9. Por que uma combinação, e não um único mecanismo?

| Mecanismo | O que comprova | O que não comprova sozinho |
|---|---|---|
| Identidade nominal | legibilidade do emissor alegado | posse, integridade e oficialidade |
| Credencial Custodial | vínculo administrativo de papel/escopo | integridade do ato sem assinatura |
| Hash documental | alteração do conteúdo | autoria e competência |
| Assinatura digital | posse da chave sobre bytes | vínculo da chave com o cargo e oficialidade |
| Chave pública | possibilidade de verificar assinatura | legitimidade da chave sem registro |
| Certificado | vínculo conforme política do emissor | independência de emissor/PKI e cadeia oficial |
| Release/tag | agrupamento e versionamento | autoridade do repositório e titular |
| Registro Oficial | autoridade e vigência declaradas | resistência criptográfica de cópias |
| Cadeia de Atos | continuidade e detecção de ruptura | prevenção de dois forks coerentes |
| Carimbo temporal | evidência de existência anterior a um instante | competência e oficialidade |

O [FIPS 180-4](https://csrc.nist.gov/pubs/fips/180-4/upd1/final) explica que funções hash geram digests capazes de detectar modificação; isso sustenta integridade, não identidade. O [RFC 8032](https://www.rfc-editor.org/info/rfc8032/) especifica EdDSA/Ed25519 e vetores de teste, demonstrando uma opção aberta de assinatura; o algoritmo específico deve permanecer substituível. O [RFC 9580](https://www.rfc-editor.org/info/rfc9580/) define formato interoperável OpenPGP para assinaturas e gestão de chaves, mas não resolve sozinho a raiz institucional de confiança.

## 10. Independência tecnológica

Para preservar independência, a hipótese líder exige:

- formatos publicados e implementáveis por terceiros;
- manifesto, chave, assinatura e digests exportáveis como arquivos;
- algoritmo identificado em cada registro, permitindo migração;
- verificação offline, sem API obrigatória;
- nenhuma dependência exclusiva de GitHub, GitLab, nuvem, CA, TSA ou blockchain;
- publicação em mais de um canal quando material;
- possibilidade de reconstruir validação apenas com corpus preservado e ferramentas compatíveis;
- distinção entre camada de prova e camada de transporte.

Git pode ser uma projeção útil: a documentação oficial permite tags criptograficamente assinadas e sua verificação, inclusive com backends OpenPGP, X.509 ou SSH ([git-tag](https://git-scm.com/docs/git-tag.html)). Porém, tag Git não deve ser raiz única, pois repositório, forge e formato podem mudar.

## 11. Continuidade na substituição do custodiante

Hipótese inicial para transição ordinária:

1. o ato de sucessão identifica titular anterior e sucessor;
2. registra nova chave pública e período de vigência;
3. referencia o último checkpoint da cadeia anterior;
4. é assinado pela chave do custodiante anterior e, após aceitação, pela nova chave;
5. preserva chaves antigas como `EXPIRADA` ou `SUBSTITUÍDA`, nunca apagadas;
6. define o instante exato de troca de competência;
7. publica o checkpoint em canais independentes.

A dupla assinatura é uma hipótese forte para continuidade, mas não pode ser requisito absoluto em falecimento, incapacidade ou perda da chave. No cenário excepcional, o ato constitucional de sucessão previsto na política deverá constituir a nova âncora, documentar a ruptura e receber evidência independente reforçada. Não há sucessão automática.

## 12. Validação de atos históricos

Atos históricos devem ser verificados segundo o estado institucional e criptográfico aplicável ao tempo da emissão:

- titular e competência vigentes naquele instante;
- chave válida naquele instante;
- manifesto e documentos originais preservados;
- assinatura válida;
- posição na cadeia/checkpoint;
- estado posterior de rotação ou revogação, distinguindo comprometimento retroativo de simples expiração;
- algoritmo e política vigentes;
- reatestação posterior, quando necessária, sem apagar a assinatura original.

Carimbos temporais podem fortalecer existência temporal. O [RFC 3161](https://www.rfc-editor.org/info/rfc3161/) descreve tokens emitidos por uma autoridade de tempo, mas cria dependência adicional; por isso, deve ser evidência opcional, não raiz exclusiva.

## 13. Múltiplos custodiantes e conselho custodial

Múltiplas assinaturas ou limiar podem reduzir risco de chave única e apoiar continuidade. Entretanto:

- alteram o modelo atual de autoridade singular;
- aumentam coordenação, disponibilidade e complexidade;
- exigem regras de quórum, conflito, ausência e emergência;
- podem fragmentar governança se mal definidos.

Nesta fase, “múltiplos custodiantes” e “conselho custodial” permanecem alternativas de pesquisa, não componentes da hipótese mínima. Podem ser testados como testemunhas/checkpoints sem transferir competência custodial.

## 14. Replicabilidade para projetos ICFACTORY

O conceito demonstra potencial de replicação se o projeto possuir:

- constituição e autoridade próprias;
- identificador de projeto;
- registro de custodiante/autorizador do projeto;
- namespace separado de chaves e atos;
- manifesto com referência ao projeto e ao escopo;
- cadeia independente, subordinada às regras do projeto e compatível com ICFACTORY.

Uma chave do projeto não deve ser confundida com chave da Custódia ICFACTORY. Replicabilidade exige separação de namespaces e autoridade, não compartilhamento automático da raiz.

## 15. Respostas às questões de pesquisa

1. **O que caracteriza um Ato Custodial autêntico?** Convergência verificável entre titularidade, competência, manifesto canônico, integridade, assinatura com chave vigente, cadeia oficial e estado de versão.
2. **Como distinguir documentos oficiais de derivados ou forks?** Por prova portável ligada à cadeia/versão oficial; nomes, plataformas e layouts não bastam. Derivados declaram origem e transformações; forks não possuem incorporação custodial.
3. **Qual mecanismo de autenticação?** A combinação de identidade/registro, credencial de chave, hash, assinatura digital, cadeia e versionamento é tecnicamente mais consistente. Nenhum item isolado é suficiente.
4. **Quais mecanismos preservam independência?** Formatos abertos, verificação offline, agilidade algorítmica, artefatos exportáveis, múltiplos canais e separação entre prova e plataforma.
5. **Como garantir continuidade na substituição?** Ato de sucessão encadeado, registro temporal de chaves, dupla assinatura quando possível e procedimento constitucional excepcional quando não for.
6. **Como validar atos históricos?** Preservando manifestos, assinaturas, chaves e estados temporais, verificando competência no instante do ato e reatestando sem apagar a prova original.
7. **É replicável para projetos?** Potencialmente sim, com namespaces e autoridades separados e pesquisa aplicada em projetos distintos.

## 16. Avaliação pelos critérios obrigatórios

| Critério | Avaliação da H-R03-01 | Risco pendente |
|---|---|---|
| Independência tecnológica | Alta: arquivos e padrões abertos; plataforma é transporte | definir formatos/algoritmos mínimos sem aprisionamento |
| Rastreabilidade | Alta: manifesto + cadeia + registros | equivocações e checkpoints conflitantes |
| Simplicidade operacional | Média: mais simples que PKI/conselho completos | gestão segura de chave e canonicalização |
| Auditabilidade | Alta: verificação offline e corpus reconstruível | ferramenta de referência ainda inexistente |
| Continuidade institucional | Média/alta: rotação e sucessão encadeadas | perda de chave/incapacidade exige protocolo testado |

## 17. Potencial de Discovery

O conceito apresenta potencial para tornar-se Discovery metodológica/governamental porque trata um problema recorrente de autoridade, proveniência e continuidade e possui hipótese testável.

Ainda não deve ser registrado como Discovery validada ou princípio. Faltam:

- definição de schema mínimo;
- protótipo de geração/verificação independente;
- ensaios de rotação, revogação, fork e recuperação;
- comparação de pelo menos duas implementações;
- aplicação fora do corpus ICFACTORY;
- medição de custo operacional e risco humano;
- revisão de segurança independente.

## 18. Critério de encerramento da fase inicial

1. **O problema foi caracterizado?** Sim, em cinco dimensões e nove ameaças iniciais.
2. **As alternativas foram catalogadas?** Sim, em `CUSTODIAL_AUTHENTICATION_ALTERNATIVES.md`.
3. **Existe uma hipótese tecnicamente mais consistente?** Sim: H-R03-01, Envelope Custodial Portátil em Camadas.
4. **O conceito demonstra potencial para tornar-se uma Discovery?** Sim, mas permanece P até testes controlados.
5. **Recomenda-se continuidade da pesquisa?** Sim, por meio de protótipo offline, vetores de teste e experimentos de sucessão/ataque.

## 19. Próximos experimentos recomendados

1. definir dois formatos candidatos de manifesto canônico;
2. produzir vetores de teste públicos, sem usar chave oficial;
3. implementar dois verificadores independentes;
4. simular alteração de documento, fork, rotação, revogação e perda de chave;
5. comparar assinatura destacada OpenPGP com assinatura direta de manifesto;
6. medir número de passos, dependências, tempo e falhas humanas;
7. testar espelhamento em filesystem, Git e arquivo compactado sem alterar a prova;
8. aplicar a um projeto-piloto sem confundir autoridade de projeto com a do ICFACTORY.

## 20. Referências técnicas primárias

- [RFC 8785 — JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785.html)
- [RFC 8032 — Edwards-Curve Digital Signature Algorithm](https://www.rfc-editor.org/info/rfc8032/)
- [RFC 9580 — OpenPGP](https://www.rfc-editor.org/info/rfc9580/)
- [RFC 3161 — Time-Stamp Protocol](https://www.rfc-editor.org/info/rfc3161/)
- [NIST FIPS 180-4 — Secure Hash Standard](https://csrc.nist.gov/pubs/fips/180-4/upd1/final)
- [Git — git-tag Documentation](https://git-scm.com/docs/git-tag.html)

Essas referências demonstram mecanismos disponíveis; não constituem adoção, homologação ou dependência normativa do ICFACTORY.
