# R-03A — Limitações e Riscos da PoC

Status: **REGISTRO EXPERIMENTAL — NÃO NORMATIVO**

Data: 2026-07-20

## 1. Limitação de raiz de confiança

### Achado

O envelope inclui uma âncora fictícia e consegue provar que a chave usada coincide com ela. Entretanto, um pacote autocontido não consegue provar que a própria âncora é a raiz institucional reconhecida externamente.

### Risco

Um atacante pode produzir outro envelope internamente consistente com nova âncora, nova chave e cadeia própria.

### Consequência

Autenticidade custodial completa requer bootstrap externo: fingerprint/checkpoint obtido por canal previamente confiável, múltiplos canais independentes ou outra raiz institucional auditável.

### Severidade

**Alta** para alegação de oficialidade; não afeta a demonstração de integridade interna.

## 2. Chaves privadas de laboratório

### Achado

As chaves de teste foram armazenadas em PEM sem proteção dentro do laboratório isolado para simplificar a execução.

### Risco

Esse armazenamento seria inaceitável para chave custodial real.

### Não testado

- HSM ou token físico;
- chave offline;
- criptografia em repouso;
- backup/recovery;
- política de acesso;
- cerimônia de geração;
- destruição segura.

### Severidade

**Crítica se extrapolada para produção.** Sem impacto oficial porque as chaves são fictícias e não foram copiadas ao repositório.

## 3. Independência limitada do verificador

Python e Node.js forneceram implementações diferentes, mas executaram:

- no mesmo host;
- no mesmo sistema operacional;
- sob a mesma atividade;
- sem auditor humano externo;
- sem implementação produzida por equipe independente.

A evidência demonstra interoperabilidade mínima, não independência organizacional completa.

## 4. Publicação multicanal simulada

Os dois canais eram diretórios no mesmo filesystem; um deles também foi compactado em ZIP.

Não foram testados:

- provedores independentes;
- indisponibilidade de canal;
- censura ou remoção;
- latência de replicação;
- conflito entre checkpoints;
- resolução de equivocações;
- verificação sem acesso ao canal primário.

## 5. Canonicalização parcial

O produtor usou JSON UTF-8 com ordenação de chaves e separadores determinísticos. O corpus continha somente strings, listas, objetos, `null` e valores simples.

Não foram testados:

- conformidade completa RFC 8785;
- números e limites IEEE-754;
- normalização Unicode;
- chaves duplicadas;
- serializers de outras linguagens;
- versões de schema;
- migração de canonicalização.

O manifesto deve ser considerado formato experimental `v0`, não padrão.

## 6. Modelo temporal simplificado

Datas eram fixas e autodeclaradas. Não houve relógio confiável, TSA, monotonicidade externa ou prova de existência anterior.

Impactos:

- não se comprova o instante real da assinatura;
- revogação retroativa fica ambígua;
- ordem depende da cadeia, não de tempo independente;
- validade histórica exige política ainda inexistente.

## 7. Revogação incompleta

A PoC testou substituição normal, não comprometimento.

Não foram resolvidos:

- descoberta tardia de chave comprometida;
- data efetiva do comprometimento;
- invalidação seletiva de atos;
- publicação/reconciliação de lista de revogação;
- recuperação sem chave anterior;
- disputa sobre atos emitidos no intervalo de incerteza.

## 8. Cadeia linear sem equivocações complexas

A cadeia única foi preservada. Não foram criados dois atos sucessores válidos concorrentes assinados pela mesma chave.

Uma cadeia de hashes detecta ruptura, mas não impede que um custodiante ou atacante com chave emita forks coerentes. São necessários checkpoints multiponto, política de precedência e alerta de conflito.

## 9. Sem validação semântica completa de competência

O verificador conferiu namespace, designação e referências, mas não implementou motor completo capaz de interpretar:

- todos os tipos de ato custodial;
- limites constitucionais;
- requisitos específicos de gate;
- conflito de interesse;
- revisão independente;
- vigência e precedência normativa;
- documentos obrigatórios por competência.

Assinatura válida não garante que a decisão seja constitucional ou cientificamente suficiente.

## 10. Release de teste simplificada

O “release” foi um registro JSON, diretório e ZIP. Não houve:

- Git commit ou tag;
- forge;
- versionamento semântico real;
- arquivo de checksums publicado externamente;
- assinatura de índice global;
- processo de homologação.

Isso respeita a restrição de não criar releases oficiais ou commits, mas limita a evidência sobre integração com distribuição real.

## 11. Escala e desempenho

A PoC contém poucos atos e artefatos pequenos. Não foram medidos:

- milhares de atos;
- artefatos grandes;
- custo de verificação incremental;
- indexação e busca;
- retenção longa;
- reatestação em massa;
- concorrência.

O tempo de aproximadamente 580 ms da segunda execução é apenas observação local.

## 12. Agilidade criptográfica não exercitada

Foi usado somente Ed25519 para assinatura e SHA-256 para digest.

Não foram testados:

- troca de algoritmo de assinatura;
- múltiplos digests simultâneos;
- reatestação pré-obsolescência;
- compatibilidade pós-quântica;
- verificação de algoritmos legados;
- política de descontinuação.

## 13. Pacote público sem prova de origem oficial

O pacote preservado permite reproduzir o resultado da PoC, mas é explicitamente fictício. Sua existência no repositório de pesquisa não o transforma em envelope oficial, raiz de confiança ou implementação homologada.

## 14. Risco humano e operacional

Não foram avaliados:

- erro ao selecionar chave;
- perda de passphrase;
- assinatura do manifesto errado;
- omissão de artefato;
- confusão entre teste e produção;
- publicação parcial;
- rotação incompleta;
- treinamento e segregação de funções.

Os avisos `TEST ONLY` reduzem confusão, mas não eliminam risco.

## 15. Resumo de severidade

| Limitação | Severidade para experimento | Severidade para adoção oficial |
|---|---|---|
| Bootstrap da raiz | média | alta |
| Proteção da chave | baixa no teste | crítica |
| Independência de infraestrutura | média | alta |
| Canonicalização parcial | média | alta |
| Tempo/revogação | média | alta |
| Equivocação/forks | média | alta |
| Competência semântica | média | alta |
| Escala/desempenho | baixa | média |
| Agilidade criptográfica | baixa | alta longitudinalmente |

## 16. Conclusão

As limitações não invalidam a viabilidade experimental do envelope. Elas impedem validação V e adoção oficial. A maior prioridade da próxima fase é definir e testar o bootstrap da raiz de confiança sem criar dependência exclusiva de plataforma.
