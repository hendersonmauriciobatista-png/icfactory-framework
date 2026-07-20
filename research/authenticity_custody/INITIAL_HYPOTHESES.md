# R-03 — Hipóteses Iniciais de Autenticidade Custodial

Status: **P — HIPÓTESES DE PESQUISA; NÃO VALIDADAS**

Data: 2026-07-20

## 1. Regra de interpretação

As hipóteses abaixo não criam mecanismo oficial, princípio, credencial, certificado, chave ou autoridade. “Sustentada” nesta fase significa apenas consistência documental/técnica inicial, não validação científica.

## H-R03-01 — Envelope Custodial Portável em Camadas

### Formulação

A autenticidade custodial pode ser comprovada com melhor equilíbrio quando um ato combina:

- Registro Oficial de Custódia;
- registro de chave pública/credencial custodial;
- manifesto canônico;
- hashes dos artefatos;
- assinatura digital destacada;
- referência ao ato/checkpoint anterior;
- versão/release;
- publicação em canais independentes.

### Fundamentação inicial

Cada camada cobre falha distinta. Hash sem assinatura não comprova autor; assinatura sem registro não comprova competência; registro sem proteção não comprova integridade; cadeia sem checkpoint não impede fork concorrente.

### Predições testáveis

- alteração de conteúdo será detectada;
- chave não registrada será rejeitada;
- ato assinado fora de escopo será identificado como ilegítimo;
- pacote continuará verificável offline e fora de Git;
- rotação preservará atos históricos.

### Falsificação

A hipótese perde força se o envelope não puder ser implementado por duas ferramentas independentes, exigir plataforma específica, não detectar fork/alteração ou impor custo operacional incompatível com atos reais.

### Estado

Hipótese líder para protótipo; não validada.

## H-R03-02 — Hash é necessário, mas insuficiente

### Formulação

Hash documental é requisito de integridade, mas não autentica identidade, competência ou oficialidade.

### Evidência inicial

Funções hash produzem digests para detectar mudança do conteúdo ([NIST FIPS 180-4](https://csrc.nist.gov/pubs/fips/180-4/upd1/final)). Qualquer terceiro, porém, pode publicar conteúdo alterado acompanhado de novo hash.

### Teste

Criar dois documentos divergentes com hashes válidos e demonstrar que, sem assinatura/registro, o verificador não identifica o oficial.

### Estado

Fortemente sustentada conceitualmente; requer demonstração controlada.

## H-R03-03 — Assinatura digital precisa de raiz institucional

### Formulação

Assinatura digital autentica posse de chave sobre uma representação de dados, mas somente se torna prova custodial quando a chave é vinculada ao titular, cargo, escopo e vigência por registro oficial.

### Evidência inicial

[RFC 8032](https://www.rfc-editor.org/info/rfc8032/) especifica assinatura EdDSA; [RFC 9580](https://www.rfc-editor.org/info/rfc9580/) descreve assinaturas OpenPGP e gestão de chaves. Nenhum desses padrões conhece, por si, a governança do ICFACTORY.

### Teste

Assinar o mesmo manifesto com duas chaves tecnicamente válidas, somente uma registrada, e verificar se o procedimento rejeita a chave sem competência.

### Estado

Sustentada inicialmente; não validada operacionalmente.

## H-R03-04 — Manifesto canônico é preferível à assinatura direta de documentos humanos

### Formulação

Assinar um manifesto determinístico contendo digests é mais estável que assinar diretamente arquivos Markdown sujeitos a encoding, newline e formatação.

### Evidência inicial

O [RFC 8785](https://www.rfc-editor.org/rfc/rfc8785.html) afirma que hashing/assinatura requerem representação invariável e define canonicalização JSON reproduzível.

### Teste

Comparar assinatura direta de Markdown em Windows/Linux com assinatura de manifesto canônico para os mesmos conteúdos lógicos.

### Falsificação

Se canonicalização gerar mais divergências ou complexidade que uma convenção textual rígida e interoperável, a preferência deverá ser revista.

### Estado

Hipótese técnica aberta.

## H-R03-05 — Release oficial é projeção, não raiz exclusiva

### Formulação

Releases e tags assinadas facilitam distribuição e versionamento, mas a prova deve continuar válida fora do repositório/plataforma.

### Evidência inicial

Git suporta tags criptograficamente assinadas e verificação com diferentes backends ([git-tag](https://git-scm.com/docs/git-tag.html)). Isso resolve transporte/versionamento em Git, não a definição institucional do repositório oficial.

### Teste

Exportar um pacote de release e verificar autenticidade em máquina sem acesso ao forge e sem checkout Git.

### Estado

Sustentada inicialmente.

## H-R03-06 — Sucessão ordinária deve encadear chaves antiga e nova

### Formulação

Na substituição ordinária, um ato referenciado na cadeia e assinado pelas chaves do titular anterior e do sucessor oferece continuidade mais forte.

### Teste

Simular rotação e troca de titular, verificar atos antigos com chave antiga e atos novos com chave nova e detectar transição não autorizada.

### Limite

Dupla assinatura não pode ser requisito absoluto em perda de chave, incapacidade ou falecimento; nesses casos é necessário novo fundamento constitucional explícito.

### Estado

Hipótese prioritária de continuidade.

## H-R03-07 — Registro histórico de chaves preserva atos após rotação

### Formulação

Chaves públicas antigas, períodos de validade e razões de revogação devem ser preservados para distinguir expiração normal de comprometimento e validar atos históricos.

### Teste

Rotacionar chave, expirar a anterior e verificar se ato emitido durante sua vigência continua validável; depois simular comprometimento retroativo.

### Estado

Hipótese prioritária.

## H-R03-08 — Carimbo temporal externo é opcional

### Formulação

Carimbo temporal pode fortalecer a prova de existência, mas não deve ser raiz obrigatória por introduzir TSA/terceiro e não comprovar competência.

### Evidência inicial

O [RFC 3161](https://www.rfc-editor.org/info/rfc3161/) define tokens de tempo por uma Time-Stamp Authority.

### Teste

Comparar verificação histórica com data do manifesto/cadeia, checkpoint multiponto e token RFC 3161.

### Estado

Alternativa complementar.

## H-R03-09 — Publicação multiponto reduz dependência e equivocações

### Formulação

Publicar checkpoints idênticos em dois ou mais canais independentes reduz risco de perda de plataforma e torna forks conflitantes mais observáveis.

### Teste

Publicar dois checkpoints divergentes em canais diferentes e avaliar se o verificador/auditor detecta conflito sem escolher silenciosamente um deles.

### Estado

Hipótese de resiliência.

## H-R03-10 — Certificado Custodial pode encapsular credencial e chave

### Formulação

Um certificado portável pode vincular titular, cargo, escopo, chave e vigência, desde que a raiz de confiança e a revogação sejam resolvidas pelo registro institucional.

### Alternativas

- certificado próprio assinado pela raiz custodial;
- OpenPGP certificate;
- X.509 para contextos que já possuam PKI.

### Falsificação

Se o certificado apenas deslocar o problema de confiança, aumentar custo sem reduzir ambiguidades ou criar dependência exclusiva, deve ser descartado do núcleo mínimo.

### Estado

Hipótese secundária.

## H-R03-11 — Múltiplos custodiantes ou conselho não pertencem ao núcleo mínimo

### Formulação

Quórum/limiar pode aumentar resiliência, mas altera a autoridade singular, eleva complexidade e pode criar governança paralela.

### Teste

Modelar cenários de ausência, desacordo, comprometimento e emergência; comparar disponibilidade e risco com titular único + testemunhas/checkpoints.

### Estado

Alternativa de pesquisa, sem recomendação de adoção.

## H-R03-12 — Projetos podem replicar o envelope com namespaces separados

### Formulação

Projetos que adotam ICFACTORY podem autenticar atos próprios usando o mesmo padrão estrutural, desde que não reutilizem identidade, chave ou namespace da Custódia ICFACTORY.

### Teste

Criar piloto em projeto com autoridade própria e comprovar que verificadores distinguem atos de projeto de atos do framework.

### Estado

Potencial Discovery; requer aplicação externa.

## 14. Ordem sugerida de experimentação

1. H-R03-02 — demonstrar limite do hash;
2. H-R03-03 — vínculo entre assinatura e registro;
3. H-R03-04 — comparar canonicalizações;
4. H-R03-01 — integrar envelope mínimo;
5. H-R03-05 — testar portabilidade fora de Git;
6. H-R03-06/H-R03-07 — rotação e sucessão;
7. H-R03-09 — checkpoints e forks;
8. H-R03-08/H-R03-10 — serviços/certificados opcionais;
9. H-R03-12 — replicação em projeto;
10. H-R03-11 — governança múltipla somente se a evidência justificar.

## 15. Critério para candidatura a Discovery

Reavaliar como Discovery apenas se H-R03-01:

- for reproduzida por duas implementações independentes;
- detectar alterações, chave ilegítima, quebra de cadeia e fork;
- sobreviver a mudança de infraestrutura;
- preservar atos após sucessão;
- apresentar custo operacional aceitável;
- funcionar em pelo menos um projeto além do contexto de origem;
- receber revisão de segurança independente.
