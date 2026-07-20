# R-03A — Recomendações após a PoC H-R03-01

Status: **RECOMENDAÇÕES DE RESEARCH — NÃO EXECUTADAS**

Data: 2026-07-20

## 1. Recomendação de maturidade

Recomenda-se abrir GP custodial específica para avaliar a promoção da H-R03-01 de **Pesquisa (P)** para **Experimental (E)**, com o seguinte escopo:

> Envelope Custodial Portável em Camadas, validado apenas como protótipo técnico para integridade, assinatura, rotação linear, rastreabilidade e verificação offline em ambiente controlado e fictício.

Não se recomenda:

- promoção automática nesta R-03A;
- classificação V;
- adoção em atos oficiais;
- criação imediata de chave custodial real;
- uso do schema experimental como padrão;
- substituição da governança vigente.

## 2. Fundamentação da recomendação P → E

A PoC produziu evidências suficientes para experimentação controlada adicional:

- duas execuções com chaves aleatórias distintas;
- 6/6 cenários aprovados em ambas;
- produção Python e verificação Node.js;
- detecção de alteração de artefato;
- rejeição de chave não autorizada;
- rotação cross-signed válida;
- preservação da cadeia;
- pacote verificável offline;
- limitações e critérios de falsificação identificados.

O resultado satisfaz o propósito de um gate P → E: há hipótese testável, protocolo, evidência inicial, riscos conhecidos e escopo controlável. A decisão de promoção pertence à Custódia e não foi praticada nesta pesquisa.

## 3. Condições mínimas para uma eventual fase E

Antes do primeiro experimento E, formalizar:

- identificador e versão de schema;
- definição de canonicalização;
- algoritmo(s) permitidos e agilidade criptográfica;
- modelo de trust anchor/bootstrapping;
- registro experimental de chaves;
- estados de chave: ativa, substituída, expirada, revogada, comprometida;
- procedimento de rotação ordinária e emergência;
- regra de checkpoints e conflito entre canais;
- separação inequívoca entre chave de teste e chave oficial;
- critérios de sucesso, falha e interrupção;
- responsável experimental e revisor independente.

## 4. Prioridade 1 — Resolver o bootstrap

Comparar experimentalmente:

1. fingerprint inicial publicado em dois ou mais canais independentes;
2. documento de designação com fingerprint ratificado por ato custodial separado;
3. certificado custodial próprio com raiz preservada offline;
4. testemunhas/checkpoints sem autoridade decisória;
5. PKI externa opcional como evidência adicional;
6. combinação de pin local e publicação multiponto.

Critério: um terceiro deve distinguir o envelope oficial de um fork autoconsistente sem depender exclusivamente de um fornecedor.

## 5. Prioridade 2 — Schema e canonicalização

- produzir schema `v0` formalmente versionado apenas para teste;
- restringir tipos e encoding;
- comparar JSON canônico RFC 8785 com formato textual rígido;
- criar vetores positivos e negativos;
- testar Python, Node.js e terceira implementação;
- definir comportamento para Unicode, números, chaves duplicadas e campos desconhecidos;
- preservar bytes canônicos junto ao manifesto legível.

## 6. Prioridade 3 — Ciclo de vida de chaves

Testar:

- geração com entropia adequada;
- armazenamento offline ou hardware;
- backup/recovery;
- rotação do mesmo titular;
- substituição de titular;
- revogação por comprometimento;
- perda total da chave anterior;
- sobreposição temporal;
- atos emitidos durante intervalo disputado;
- reatestação antes de obsolescência.

Nenhuma chave oficial deve ser criada antes de política, cerimônia e ambiente aprovados.

## 7. Prioridade 4 — Forks e publicação multiponto

Criar cenários:

- dois sucessores válidos para o mesmo ato;
- dois canais com checkpoints divergentes;
- canal indisponível;
- atraso de replicação;
- exclusão de ato intermediário;
- reordenação;
- mirror comprometido;
- mudança completa de forge/infraestrutura.

Definir regra que sinalize conflito sem escolher silenciosamente uma cadeia.

## 8. Prioridade 5 — Validação semântica

O verificador futuro deve separar:

- **VALID_CRYPTOGRAPHICALLY:** bytes e assinatura válidos;
- **VALID_CHAIN:** vínculo e sequência válidos;
- **AUTHORIZED_KEY:** chave reconhecida no instante;
- **AUTHORIZED_SCOPE:** cargo possuía competência;
- **OFFICIAL_CHECKPOINT:** cadeia ancorada externamente;
- **INSTITUTIONALLY_AUTHENTIC:** todos os controles requeridos satisfeitos;
- **INDETERMINATE:** evidência insuficiente ou conflito;
- **INVALID:** falha objetiva.

Isso evita que “assinatura válida” seja interpretada como “ato legítimo”.

## 9. Prioridade 6 — Auditoria externa e replicação

- entregar pacote a terceiro que não participou da produção;
- executar em outro sistema operacional e host;
- reproduzir com implementação independente;
- testar sem acesso ao repositório de origem;
- aplicar em projeto-piloto com namespace próprio;
- obter revisão criptográfica/operacional independente;
- medir passos, tempo, erros e compreensão do auditor.

## 10. Melhorias no envelope

### Obrigatórias para experimentação E

- `schema_version` e política de compatibilidade;
- `manifest_digest` explícito;
- fingerprint SPKI com algoritmo identificado;
- registro temporal de estado das chaves;
- `previous_act_digest` e `checkpoint_id`;
- inventário completo de artefatos;
- resultado de verificação estruturado;
- aviso/namespace de ambiente;
- regra de falha fechada para campos críticos desconhecidos.

### Opcionais para comparação

- OpenPGP como formato de assinatura;
- certificado X.509 em ambientes regulados;
- carimbo temporal RFC 3161;
- múltiplos digests;
- arquivo de transparência/checkpoint;
- assinatura de testemunha sem competência custodial;
- tag Git assinada como projeção de release.

## 11. Métricas propostas

| Dimensão | Métrica |
|---|---|
| Implementação | linhas/componentes/dependências e tempo de setup |
| Auditoria | passos e tempo até veredito |
| Independência | número de runtimes/SO/canais capazes de verificar |
| Complexidade | operações humanas por ato/rotação |
| Integridade | taxa de detecção dos vetores negativos |
| Continuidade | atos históricos preservados após rotação/incidente |
| Interoperabilidade | vetores aceitos identicamente por implementações |
| Segurança | falsos positivos, falsos negativos e estados indeterminados |

## 12. Critérios de interrupção

Suspender a fase E se:

- uma alteração não for detectada;
- chave não registrada for aceita;
- canonicalização produzir assinaturas divergentes sem diagnóstico;
- fork for aceito silenciosamente como oficial;
- chave de teste puder ser confundida com oficial;
- recuperação exigir apagar ou reescrever histórico;
- dependência exclusiva de plataforma se tornar necessária;
- custo operacional impedir auditoria humana razoável.

## 13. Roadmap experimental sugerido

1. E-01 — Bootstrap e pin multiponto;
2. E-02 — Canonicalização e vetores cruzados;
3. E-03 — Rotação, revogação e perda de chave;
4. E-04 — Forks/checkpoints concorrentes;
5. E-05 — Portabilidade entre plataformas/SO;
6. E-06 — Piloto em projeto com namespace separado;
7. E-07 — Auditoria independente e custo operacional;
8. revisão de maturidade somente após consolidar resultados.

## 14. Resposta final

A H-R03-01 deve continuar. A PoC recomenda avaliação formal de promoção para E, limitada a experimentação controlada. O modelo ainda não está pronto para V, C ou uso em atos reais.

## 15. Não execução

Estas recomendações não alteram maturidade. Nenhuma GP de promoção foi aberta, nenhuma chave real foi criada e nenhum artefato de governança foi modificado.
