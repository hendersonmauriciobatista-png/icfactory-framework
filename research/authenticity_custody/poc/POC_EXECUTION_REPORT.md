# R-03A — Relatório de Execução da PoC H-R03-01

Status: **EXECUÇÃO EXPERIMENTAL CONCLUÍDA — SEM EFEITO NORMATIVO**

Data: 2026-07-20 (America/Sao_Paulo)

Classificação: Research / evidência experimental

## 1. Objetivo

Testar se um terceiro consegue verificar, a partir de um Envelope Custodial portátil, a integridade, a assinatura, o vínculo de chave, a cadeia e a rotação de um Ato Custodial inteiramente fictício.

## 2. Isolamento

A PoC utilizou somente:

- namespace `ICFACTORY-R03A-TEST-ONLY`;
- titular fictício `TEST-CUSTODIAN-ALPHA`;
- designação fictícia `TEST-CM-001`;
- atos `TEST-ACT-001`, `TEST-ROTATE-001` e `TEST-ACT-002`;
- duas chaves Ed25519 geradas exclusivamente para teste;
- documentos marcados `FICTITIOUS` e `TEST ONLY`;
- release `test-v0.0.1` e canais simulados;
- laboratório fora do repositório oficial.

Nenhuma identidade, chave, credencial, release ou ato oficial do ICFACTORY foi usado. As duas chaves privadas permaneceram somente no laboratório e não foram copiadas para o pacote público nem para o novo repositório.

## 3. Ambiente de execução

| Componente | Uso |
|---|---|
| Python 3.12.13 — runtime empacotado do workspace | produtor do envelope |
| `cryptography` 49.0.0 | geração e assinatura Ed25519 de teste |
| Node.js v24.14.0 | verificador independente do produtor |
| SHA-256 | digests de documentos, manifestos e chaves públicas |
| JSON determinístico restrito | manifesto e registros da PoC |
| Filesystem + arquivo ZIP | canais/releases de teste |

“Independente” nesta PoC significa implementação e runtime distintos no mesmo host. Não significa auditor externo, hardware separado ou infraestrutura organizacional independente.

## 4. Estrutura do envelope experimental

O pacote público preservado em `evidence/public_evidence/` contém:

- `trust_anchor.json` — âncora fictícia autocontida;
- `keys/` — duas chaves públicas de teste;
- `act_001/` — documento fictício, manifesto e assinatura;
- `tampered_scenario/` — cópia com documento alterado;
- `rotation/` — registro de chaves v2, manifesto de rotação e assinaturas antiga/nova;
- `act_002_post_rotation/` — ato posterior assinado pela segunda chave;
- `release_test_v0.0.1.json` — registro de release de teste;
- `channels/` — duas publicações simuladas e ZIP de teste;
- `channel_payload/` — payload comum usado nos dois canais.

O pacote também inclui:

- `evidence/validation_results_node.json` — resultado estruturado;
- `evidence/r03a_verifier.js` — verificador independente usado;
- nenhuma chave privada.

Reexecução do verificador, a partir da pasta `poc/`:

```text
node evidence/r03a_verifier.js evidence --no-write
```

## 5. Representação experimental do manifesto

Campos usados:

```text
framework_id
act_id
act_type
appointment_act_id
custodian_id
custodial_scope
issued_at
effective_at
key_id
previous_act_digest
artifacts[] { path, media_type, hash_algorithm, digest }
signature_algorithm
version_or_release
test_notice
```

O produtor serializou JSON UTF-8 com chaves ordenadas, sem espaços e sem valores numéricos especiais. Isso forneceu determinismo suficiente para os dados restritos da PoC. Não foi realizado teste integral de conformidade RFC 8785 e o formato não deve ser tratado como schema oficial.

## 6. Execução dos cenários

### Cenário 1 — Ato fictício e envelope

Foi criado `TEST-ACT-001` com um documento Markdown fictício. O manifesto incluiu digest SHA-256, escopo, designação, chave, versão e referência `GENESIS`.

Resultado: envelope produzido e marcado como teste.

### Cenário 2 — Assinatura com chave de teste

O produtor gerou `TEST-KEY-001`, exportou somente a chave pública ao pacote e assinou os bytes exatos do manifesto.

Resultado: assinatura Ed25519 verificável pelo runtime Node.js.

### Cenário 3 — Hashes dos artefatos

O documento, manifesto, âncora e chaves receberam digests SHA-256 conforme sua função no envelope.

Resultado: o verificador recalculou o digest do documento e obteve correspondência.

### Cenário 4 — Publicação multicanal

O mesmo payload foi copiado para:

- `channel_A_filesystem`;
- `channel_B_test_release` e seu ZIP.

Resultado: os inventários A/B possuíam 16 arquivos e eram idênticos por caminho/digest.

### Cenário 5 — Validação independente

O verificador Node.js recebeu somente evidências públicas. Ele não leu as chaves privadas nem importou código do produtor Python.

Resultado: assinatura, hash, chave ancorada e envelope primário foram aceitos.

### Cenário 6 — Alteração de documento

`BLUE-TEST` foi substituído por `RED--TEST`, preservando manifesto e assinatura originais.

Resultado: a assinatura do manifesto continuou matematicamente válida, mas o hash do artefato falhou; o envelope completo foi rejeitado. Isso comprova que assinatura do manifesto e verificação dos artefatos são controles complementares.

### Cenário 7 — Substituição não autorizada de chave

A assinatura original foi verificada contra `TEST-KEY-002`, ainda não legitimada pela cadeia.

Resultado: verificação criptográfica falhou e a substituição foi detectada.

### Cenário 8 — Rotação autorizada de chave

Foi produzido `TEST-ROTATE-001`:

- referencia o digest de `TEST-ACT-001`;
- registra fingerprint da chave anterior e da nova;
- referencia registro de chaves v2;
- possui assinatura da chave anterior e da nova;
- introduz `TEST-KEY-002` como ativa.

Depois, `TEST-ACT-002` foi assinado pela nova chave e referenciou o digest do manifesto de rotação.

Resultado: todas as assinaturas, registros, digests e vínculos de cadeia foram aceitos.

### Cenário 9 — Rastreabilidade completa

A cadeia verificada foi:

```text
TEST-CM-001
  → TEST-ACT-001 / TEST-KEY-001
  → TEST-ROTATE-001 / TEST-KEY-001 + TEST-KEY-002
  → TEST-ACT-002 / TEST-KEY-002
```

Resultado: namespace, designação, ato anterior, rotação e ato posterior permaneceram ligados.

## 7. Execuções e repetibilidade

Foram realizadas duas execuções completas com pares de chaves aleatórios distintos.

| Execução | S1 | S2 | S3 | S4 | S5 | S6 | Resultado |
|---|---|---|---|---|---|---|---|
| Run 001 | PASS | PASS | PASS | PASS | PASS | PASS | 6/6 |
| Run 002 | PASS | PASS | PASS | PASS | PASS | PASS | 6/6 |

A segunda execução levou aproximadamente 580 ms no ambiente local, incluindo produção e verificação. Esse valor é observacional, não benchmark.

## 8. Identificadores da execução primária

| Evidência | Valor SHA-256/fingerprint |
|---|---|
| Chave inicial SPKI DER | `b5b59ccd68f1912658d6b708ef4335d95d1b48fdad498a290d3f299dbcdfc6e2` |
| Nova chave SPKI DER | `1cfd8549702149f4f20141054cb3098553aa55b5b07a0d7b5883f1b8a62901da` |
| Âncora fictícia | `38a28f3877fb63f19318a0b3aed0939124a2651a253b9016097369fea81de519` |
| Manifesto TEST-ACT-001 | `5e8615fc0e6b612a1aabc4ba2b1dcfc34eaf1149629a2e041ce45d3723a2c105` |
| Manifesto TEST-ROTATE-001 | `1f4c12990363f9353c4f7f011c1a8c9cfd00dba0546391c50f2c98a21ecb401f` |

## 9. Facilidade e complexidade observadas

| Critério | Avaliação | Evidência |
|---|---|---|
| Facilidade de implementação | Média/alta para protótipo | produtor e verificador pequenos; bibliotecas comuns |
| Facilidade de auditoria | Alta para integridade/cadeia | JSON, PEM, Base64 e resultados estruturados |
| Independência tecnológica | Alta no desenho | Python produziu; Node verificou; filesystem/ZIP transportou |
| Complexidade operacional | Média | chave, canonicalização, rotação e âncora exigem disciplina |
| Rastreabilidade | Alta no cenário controlado | cadeia completa e referências verificadas |

## 10. Limite fundamental observado

O verificador confirmou que a chave pública coincide com a âncora incluída no próprio pacote. Isso prova **consistência interna**, não prova que essa âncora é a raiz oficial reconhecida pelo mundo externo.

Um atacante pode criar outro pacote autoconsistente com sua própria âncora, chave e cadeia. Portanto, a Autenticidade Institucional completa exige pelo menos um fingerprint/checkpoint obtido previamente por canal independente e confiável. Esse problema de bootstrap não invalida o envelope; delimita o que ele consegue provar sozinho.

## 11. Não intervenção

Nenhum arquivo de governança foi alterado. Nenhuma chave real foi usada. Nenhuma release oficial, commit, push, promoção ou gate científico foi executado.
