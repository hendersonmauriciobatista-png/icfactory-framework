# R-03A — Resultados de Validação da PoC

Status: **VALIDAÇÃO EXPERIMENTAL CONCLUÍDA — HIPÓTESE NÃO PROMOVIDA**

Data: 2026-07-20

## 1. Resultado consolidado

| Cenário | Resultado esperado | Resultado observado | Veredito |
|---|---|---|---|
| S1 — Envelope primário | aceitar | assinatura, hash e chave ancorada válidos | PASS |
| S2 — Dois canais | inventários idênticos | 16/16 arquivos idênticos | PASS |
| S3 — Documento adulterado | rejeitar | hash falhou; adulteração detectada | PASS |
| S4 — Chave substituta não autorizada | rejeitar | assinatura não validou com chave nova | PASS |
| S5 — Rotação autorizada | aceitar | cross-sign, registro, cadeia e ato novo válidos | PASS |
| S6 — Rastreabilidade | preservar vínculos | designação, namespace e cadeia preservados | PASS |

As duas execuções independentes por geração de chaves obtiveram 6/6 cenários aprovados.

## 2. Validação por controle

### Identidade de teste

- `framework_id`: preservado em todos os manifestos;
- `custodian_id`: preservado;
- `appointment_act_id`: preservado;
- escopo: `R03A-LAB-ONLY`;
- aviso fictício: presente.

Resultado: PASS para consistência interna. Não comprova identidade oficial externa.

### Integridade documental

- documento original: digest correspondente;
- documento adulterado: digest divergente;
- manifesto original: assinatura permaneceu válida após adulteração do documento;
- decisão do envelope completo: rejeição quando qualquer artefato falha.

Resultado: PASS. Demonstrada necessidade de validar tanto assinatura quanto todos os digests.

### Autenticidade criptográfica

- assinatura original com chave inicial: válida;
- assinatura original com chave substituta: inválida;
- rotação assinada pela chave anterior: válida;
- rotação aceita pela nova chave: válida;
- ato posterior assinado pela nova chave registrada: válido.

Resultado: PASS para posse de chave e transição controlada.

### Cadeia

- `GENESIS → TEST-ACT-001`: estabelecido;
- digest de `TEST-ACT-001 → TEST-ROTATE-001`: válido;
- digest de `TEST-ROTATE-001 → TEST-ACT-002`: válido.

Resultado: PASS no cenário linear.

### Multicanal

- Canal A: filesystem;
- Canal B: diretório de release de teste + ZIP;
- inventários por caminho/digest: idênticos.

Resultado: PASS para reprodução de payload. Não foi testada independência real de infraestrutura.

### Verificação por terceiro técnico

O produtor foi implementado em Python/`cryptography`; o verificador foi implementado em Node.js/`crypto` e consumiu somente o pacote público.

Resultado: PASS para interoperabilidade mínima entre duas implementações/runtime no mesmo host.

## 3. Resultado estruturado da execução primária

O arquivo `evidence/validation_results_node.json` registra:

```text
S1_primary_envelope.overall = true
S2_multiple_channels.overall = true
S3_tampered_document.tampering_detected = true
S4_unauthorized_key_substitution.substitution_detected = true
S5_authorized_key_rotation.overall = true
S6_traceability.overall = true
bootstrap_assessment.institutional_authenticity_from_envelope_alone = false
```

## 4. Avaliação dos critérios

| Critério | Resultado | Fundamentação |
|---|---|---|
| Facilidade de implementação | **Média/alta** | poucas primitivas e bibliotecas comuns; gestão de chave permanece complexa |
| Facilidade de auditoria | **Alta** | evidências legíveis, resultados estruturados e verificação offline |
| Independência tecnológica | **Alta, parcialmente demonstrada** | duas linguagens e transporte filesystem/ZIP; apenas um SO/host |
| Complexidade operacional | **Média** | manifesto simples; rotação, revogação e bootstrap exigem política |
| Riscos identificados | **Relevantes, tratáveis em pesquisa** | raiz de confiança, chave privada, equivocações, canonicalização e tempo |
| Limitações | **Materiais** | não houve infraestrutura independente, auditor humano externo ou incidente real |
| Melhorias | **Definidas** | pin externo, schema, key lifecycle, checkpoints, vetores e verificador de referência |

## 5. Respostas objetivas ao critério de encerramento

### A hipótese funciona?

**Sim, condicionalmente.** H-R03-01 funcionou para integridade, assinatura, registro de chave, cadeia, adulteração e rotação no ambiente controlado. Ela não resolve sozinha o bootstrap da raiz institucional.

### O Envelope pode ser validado por terceiros?

**Sim, para consistência criptográfica e rastreabilidade**, desde que o terceiro possua ou reconheça uma âncora/fingerprint confiável. O verificador independente validou o pacote público sem chave privada. **Não**, se “validar” significar descobrir do zero, somente pelo pacote, qual raiz é oficialmente reconhecida.

### A cadeia de evidências permaneceu íntegra?

**Sim.** Os vínculos `TEST-ACT-001 → TEST-ROTATE-001 → TEST-ACT-002`, a designação fictícia, o namespace e os digests permaneceram íntegros nas duas execuções.

### Existem vulnerabilidades relevantes?

**Sim.** A principal é o bootstrap da raiz de confiança. Também permanecem gestão/proteção da chave privada, revogação, equivocações entre canais, canonicalização completa, tempo confiável, recuperação e obsolescência criptográfica.

### A hipótese recomenda promoção para Experimental?

**Sim, como recomendação documental de P → E, em escopo controlado.** A PoC fornece evidência suficiente para experimentação controlada adicional. Esta R-03A não executa a promoção e não autoriza uso oficial. A promoção deverá ocorrer somente por GP custodial própria.

## 6. Veredito

H-R03-01 demonstrou viabilidade prática e falsificabilidade. O resultado é suficiente para recomendar maturidade E, mas insuficiente para V ou adoção institucional. O próximo ciclo deve resolver o bootstrap e testar infraestrutura realmente independente, revogação, fork/equivocação e recuperação.
