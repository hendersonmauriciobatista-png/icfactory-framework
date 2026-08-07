# ICFACTORY — Methodological Discoveries

## Objetivo

Este documento constitui o inventário oficial das Descobertas Metodológicas (DM) identificadas durante o desenvolvimento de projetos utilizando o ICFACTORY.

Seu propósito é registrar, preservar e acompanhar a evolução de descobertas que modificam ou ampliam o próprio processo metodológico do framework.

As Discoveries registradas neste documento ainda não representam princípios oficiais do ICFACTORY.

Enquanto permanecerem na camada Research, constituem hipóteses metodológicas em processo de validação.

---

# Escopo

Este inventário contempla exclusivamente descobertas que alteram o modo pelo qual projetos são concebidos, estruturados, desenvolvidos, auditados ou evoluídos.

Descobertas relacionadas à estrutura dos sistemas pertencem ao inventário de Descobertas Arquiteturais.

---

# Processo De Evolução

Toda Discovery registrada neste documento deverá seguir obrigatoriamente o Discovery Lifecycle definido pelo ICFACTORY.

Nenhuma Discovery poderá ser promovida diretamente ao núcleo metodológico do framework.

Sua promoção dependerá da existência de evidências suficientes obtidas durante o desenvolvimento de projetos distintos.

---

# Inventário Oficial

---

# DM-01 — Identificação Do Núcleo Do Negócio

## Estado

CANDIDATA

---

## Origem

Projeto:

Sistema de Análise de Água

Categoria:

Descoberta Metodológica

---

## Problema Observado

Durante o desenvolvimento do projeto foi observado que a compreensão do domínio, isoladamente, não era suficiente para orientar adequadamente a arquitetura do sistema.

Mesmo conhecendo o domínio, diferentes arquiteturas ainda poderiam ser produzidas caso o verdadeiro núcleo do negócio não estivesse explicitamente identificado.

---

## Descoberta

Antes da definição arquitetural, deve existir uma etapa formal destinada à identificação do Núcleo do Negócio.

Essa identificação estabelece o elemento central que deverá orientar toda a construção da solução.

---

## Hipótese Metodológica

A identificação explícita do Núcleo do Negócio reduz ambiguidades arquiteturais, melhora a definição de responsabilidades e aumenta a coerência das decisões estruturais do projeto.

Esse princípio poderá ser reutilizado independentemente do domínio da aplicação.

---

## Fluxo Proposto

Entendimento do Domínio

↓

Identificação do Núcleo do Negócio

↓

Definição Arquitetural

↓

Implementação Incremental

↓

Testes

↓

Documentação

↓

Auditoria

---

## Evidências

Evidência observada durante o desenvolvimento do Sistema de Análise de Água.

A identificação explícita do Núcleo do Negócio permitiu reorganizar a arquitetura em torno da finalidade principal da plataforma, distinguindo claramente funcionalidades operacionais, analíticas, executivas e de governança.

---

## Aplicabilidade Esperada

A Discovery possui potencial de reutilização em diferentes tipos de software, incluindo:

* sistemas administrativos;
* sistemas industriais;
* plataformas analíticas;
* sistemas embarcados;
* plataformas de monitoramento;
* sistemas financeiros;
* aplicações corporativas.

---

## Critérios De Validação

A Discovery deverá ser observada novamente em projetos distintos.

A validação será considerada suficiente quando a etapa de Identificação do Núcleo do Negócio demonstrar impacto positivo na qualidade arquitetural em múltiplos domínios de software.

---

## Próximas Validações

✔ Sistema de Análise de Água

⬜ Sistema de Gestão para Autoescola

⬜ Outros projetos desenvolvidos utilizando o ICFACTORY

---

## Observações

Esta Discovery representa a primeira hipótese metodológica oficialmente registrada na camada Research do ICFACTORY.

Sua promoção ao núcleo metodológico dependerá exclusivamente das evidências produzidas em projetos futuros.

---

# Registro GP-R01

Linha de programa:

GP-R - Programas da camada Research.

Confirmacao:

DM-01 permanece registrada como Discovery Metodologica CANDIDATA.

Nao ha promocao automatica ao nucleo metodologico oficial do ICFACTORY.

A GP-R01 apenas institucionaliza a camada Research e preserva a DM-01 como hipotese metodologica em investigacao.

---

DM-02 — Deriva Semântica e Interoperabilidade Inicial do IOP
Estado
EM VALIDAÇÃO
Origem
Projeto:
H&A CORE
Categoria:
Descoberta Metodológica
Domínio de aplicação:
Governança operacional, representação declarativa de contratos e interoperabilidade entre executores de IA.
Contexto operacional:
Onda 4 da migração da Baseline 1.0 do H&A CORE.
Data do registro:
2026-08-06
Autor:
Henderson Mauricio Batista
Referência de proveniência:
DC-001
Participantes de IA registrados na proveniência:
Alfred
Codex
Claude
Gemini
Microsoft Copilot
DeepSeek
Os agentes de IA participaram exclusivamente dos experimentos e observações. Nenhum agente possui autoridade institucional sobre esta Discovery.
Motivação da Descoberta
Durante a Onda 4 da migração da Baseline 1.0 do H&A CORE, foram observadas ambiguidades na tradução de decisões metodológicas e documentais para instruções operacionais destinadas a executores de IA.
A necessidade de tornar autoridade, fonte da verdade, escopo, estratégia, mapeamentos, exclusões, políticas de destino, conflitos, integridade e estado-alvo explicitamente verificáveis motivou a experimentação de uma representação operacional estruturada denominada provisoriamente IOP.
Problema Observado
Instruções produzidas a partir de documentação metodológica ou linguagem natural podem exigir que o executor traduza, interprete ou complete informações antes de agir.
Essa etapa introduz possibilidade de:
deriva semântica;
inferências não autorizadas;
divergência entre executores;
dificuldade de distinguir falhas do método;
dificuldade de distinguir falhas do prompt;
dificuldade de distinguir falhas do próprio executor.
Durante os experimentos da Onda 4, contratos IOP incompletos produziram interrupções explícitas por:
autoridade não resolvida;
mapeamentos insuficientes;
estado inicial do destino não definido.
Essas interrupções tornaram as lacunas observáveis antes da execução.
Descoberta
Os experimentos iniciais demonstraram que uma representação operacional estruturada pode tornar ausências, conflitos e condições de execução explicitamente verificáveis antes da realização de alterações.
Também foi observado que a explicitação do estado do destino permitiu distinguir:
artefatos ausentes;
artefatos já materializados com hash idêntico;
artefatos com conteúdo divergente.
Essa distinção permitiu a retomada da execução experimental sem sobrescrita e sem inferência no experimento E04.
Essas observações constituem evidência inicial. Não constituem validação universal, padronização do IOP ou promoção ao Framework ICFACTORY.
Hipótese Metodológica
Investigar se decisões metodológicas e operacionais podem ser representadas por contratos declarativos autocontidos, explícitos e auditáveis, capazes de separar:
autoridade;
fonte da verdade;
regras;
estado;
validação;
execução.
A hipótese sob validação é que essa separação poderá reduzir a necessidade de inferência do executor e permitir que diferentes agentes de IA interpretem o mesmo contrato com comportamento operacional comparável.
A interoperabilidade permanece como hipótese em validação.
Não se afirma:
interoperabilidade universal;
compatibilidade universal entre modelos de IA;
economia comprovada de tokens;
redução causalmente comprovada do tempo de execução;
independência completa de modelo;
reconhecimento do IOP como padrão do ICFACTORY.
Fluxo Proposto
Autoridade explícita
↓
Fonte da verdade identificada
↓
Escopo, estratégia, mapeamentos e exclusões
↓
Políticas de estado, conflito, ambiguidade e integridade
↓
Validação anterior à execução
↓
Execução autorizada ou interrupção explícita
↓
Auditoria do estado resultante
Este fluxo permanece experimental.
Evidências
E01 — Autoridade e mapeamento insuficientes
Contexto:
H&A CORE — Onda 4.
Observação:
As primeiras representações IOP apresentaram lacunas de autoridade e mapeamento.
Resultado:
FAIL
Evidência:
O executor interrompeu antes da execução ao detectar referência de autoridade não resolvida e destino insuficientemente definido.
E02 — Precheck com elementos explícitos
Observação:
Autoridade, fonte autoritativa, estratégia, mapeamentos, exclusões e classificações foram explicitados.
Resultado:
PASS_PRECHECK
Evidência:
As ambiguidades semânticas anteriormente observadas foram eliminadas sem necessidade de inferência.
E03 — Estado inicial insuficientemente modelado
Observação:
O estado inicial do destino não estava suficientemente modelado.
Resultado:
FAIL
Evidência:
357 de 360 destinos já existiam enquanto OVERWRITE=PROHIBITED.
E04 — Política declarativa do estado do destino
Observação:
A política de destino passou a distinguir ABSENT, HASH_EQUAL e HASH_DIFFERENT.
Resultado:
PASS
Evidência:
357 artefatos foram reconhecidos como já materializados com hash igual e três artefatos ausentes foram copiados, sem sobrescrita e sem inferência.
Hipótese resultante:
A representação declarativa do estado do destino pode permitir retomada idempotente e auditável.
E05 — Ausência de autorização para onda posterior
Observação:
Foi realizada tentativa de iniciar uma onda posterior sem autorização própria.
Resultado:
FAIL
Evidência:
O executor interrompeu ao detectar ausência de autorização, domínio, estratégia e mapeamentos da nova onda.
Hipótese resultante:
O estado concluído de uma onda não constitui autorização automática da onda seguinte.
Experimento Inicial de Interoperabilidade
Objetivo
Verificar se executores distintos e sem contexto prévio do ICFACTORY conseguem interpretar o mesmo contrato IOP autocontido.
Protocolo de referência
IOP 0.8
Condições
mesmo protocolo para todos os executores;
resposta esperada não fornecida;
contexto do ICFACTORY não fornecido;
execução real proibida;
inferência proibida.
Gabarito esperado
IOP_VALIDATION=FAIL
CONTRACT_STATUS=INVALID
VALID_MAPPINGS=1
INVALID_MAPPINGS=2

VIOLATIONS={
R2=doc-c.md
R3=doc-b.md
R5=doc-c.md
}

DESTINATION_DECISIONS={
doc-a.md=ALREADY_MATERIALIZED
doc-b.md=NOT_EVALUATED
doc-c.md=NOT_EVALUATED
}

INFERENCES_REQUIRED=0
EXECUTION_STATUS=PROHIBITED
Resultados por executor
Codex
Resultado:
CONFORMANT
Claude
Resultado:
CONFORMANT
Observação:
O primeiro teste anterior rejeitou corretamente uma representação não autocontida. O teste autocontido convergiu ao gabarito.
Gemini
Resultado:
PARTIAL
Observação:
Compreendeu a estrutura e as principais regras, mas apresentou erro na aplicação de R4 e na consolidação da quantidade de mapeamentos válidos e inválidos.
Microsoft Copilot
Resultado:
CONFORMANT_WITH_MINOR_OMISSION
Observação:
Chegou à contagem e às decisões esperadas, mas não explicitou R2 separadamente no resumo das violações.
DeepSeek
Resultado:
CONFORMANT_WITH_SCHEMA_VARIATION
Observação:
Chegou ao resultado lógico esperado, mas incluiu regras cumpridas ou aplicáveis no bloco destinado a violações.
Limite da evidência
Os resultados constituem evidência inicial de interoperabilidade.
Eles não demonstram:
interoperabilidade universal;
compatibilidade com qualquer agente ou modelo;
independência completa de modelo;
validade do IOP como padrão;
integração do IOP ao ICFACTORY.
Teste de Referência — IOP 0.8
O conteúdo abaixo é preservado como protocolo de referência do experimento.
IOP_VERSION=0.8
IOP_STATUS=EXPERIMENTAL
MODE=CONTRACT_VALIDATION_ONLY
EXPERIMENT=CLAUDE-02
DOMAIN=MIGRATION_VALIDATION

PROTOCOL_SEMANTICS={
AUTHORITY_DECISION=Identifica a autorização que originou o contrato.
SOURCE_OF_TRUTH=Contém os dados autoritativos usados na validação.
STRATEGY_ALLOWED=Única classificação autorizada para execução.
MAPPINGS=Relações propostas entre origem e destino.
EXCLUDE=Itens que não podem integrar a execução.
DESTINATION_POLICY=Tratamento de destinos ausentes ou preexistentes.
AMBIGUITY_POLICY=Comportamento obrigatório diante de informação insuficiente.
CONFLICT_POLICY=Comportamento obrigatório diante de divergência.
}

VALIDATION_RULES={
R1=Cada origem em MAPPINGS deve existir em SOURCE_OF_TRUTH.
R2=Cada origem em MAPPINGS deve possuir classificação igual a STRATEGY_ALLOWED.
R3=O destino em MAPPINGS deve ser idêntico ao destino definido em SOURCE_OF_TRUTH.
R4=Nenhum item presente em EXCLUDE pode aparecer em MAPPINGS.
R5=Itens classificados como CONSOLIDATE, ARCHIVE, PRESERVE ou EXCLUDE_FROM_BASELINE não podem ser migrados.
R6=Destino ausente pode receber COPY.
R7=Destino presente com hash idêntico deve receber ALREADY_MATERIALIZED.
R8=Destino presente com hash diferente deve causar STOP.
R9=Informação ausente ou contraditória deve causar STOP.
R10=Nenhuma execução real deve ocorrer neste experimento.
}

AUTHORITY_DECISION={
DOCUMENT=OEP-TEST-001
AUTHORITY_TYPE=PROJECT_AUTHORITY
AUTHORITY_STATUS=APPROVED
AUTHORIZED_DOMAIN=DOCUMENTATION
AUTHORIZED_STRATEGY=MIGRATE
}

SOURCE_OF_TRUTH={
doc-a.md={
classification=MIGRATE
destination=docs/governance/doc-a.md
source_hash=AAA111
}
doc-b.md={
classification=MIGRATE
destination=docs/governance/doc-b.md
source_hash=BBB222
}
doc-c.md={
classification=CONSOLIDATE
destination=docs/knowledge/doc-c.md
source_hash=CCC333
}
doc-d.md={
classification=ARCHIVE
destination=archive/doc-d.md
source_hash=DDD444
}
}

MAPPINGS={
doc-a.md->docs/governance/doc-a.md
doc-b.md->docs/governance/doc-b-renamed.md
doc-c.md->docs/knowledge/doc-c.md
}

EXCLUDE={
doc-d.md
}

DESTINATION_STATE={
docs/governance/doc-a.md={
state=PRESENT
destination_hash=AAA111
}
docs/governance/doc-b-renamed.md={
state=ABSENT
}
docs/knowledge/doc-c.md={
state=ABSENT
}
}

DESTINATION_POLICY={
ABSENT=COPY
PRESENT_HASH_EQUAL=ALREADY_MATERIALIZED
PRESENT_HASH_DIFFERENT=STOP
}

AMBIGUITY_POLICY=STOP
CONFLICT_POLICY=STOP
EXECUTION=PROHIBITED
GIT=PROHIBITED
NO_INFERENCE=TRUE

REQUEST={
VALIDATE_CONTRACT
IDENTIFY_EACH_RULE_VIOLATION
CALCULATE_VALID_MAPPING_COUNT
CALCULATE_INVALID_MAPPING_COUNT
DETERMINE_CONTRACT_STATUS
DO_NOT_EXECUTE
RETURN_ONLY_IOP_STATE
}

OUTPUT_SCHEMA={
IOP_VALIDATION=PASS|FAIL
CONTRACT_STATUS=VALID|INVALID
VALID_MAPPINGS=<integer>
INVALID_MAPPINGS=<integer>
VIOLATIONS={
<rule_identifier>=<affected_item>:<objective_reason>
}
DESTINATION_DECISIONS={
<mapping>=COPY|ALREADY_MATERIALIZED|STOP|NOT_EVALUATED
}
INFERENCES_REQUIRED=<integer>
EXECUTION_STATUS=PROHIBITED
}
Aplicabilidade Esperada
A Discovery possui aplicabilidade experimental potencial em:
migrações documentais;
reorganizações estruturais;
execução de ondas controladas;
validação de contratos operacionais;
coordenação entre executores humanos e agentes de IA;
verificação anterior à execução;
retomada de operações parcialmente materializadas;
auditoria de decisões e estados operacionais.
Essa aplicabilidade permanece em validação e não constitui conclusão geral.
Critérios de Validação
A hipótese deverá ser avaliada por experimentos controlados capazes de verificar:
convergência de interpretação entre executores distintos;
identificação consistente de contratos válidos e inválidos;
detecção de conflitos e ambiguidades;
separação entre evidência, hipótese e decisão;
interrupção consistente diante de lacunas;
comportamento idempotente em estados parcialmente materializados;
reprodutibilidade em sessões independentes;
comportamento em diferentes domínios operacionais.
Economia de tokens e redução de tempo somente poderão ser avaliadas por comparações controladas específicas.
Próximas Validações
comparação controlada de uso de tokens;
comparação controlada de tempo de execução;
inclusão de executores de IA adicionais;
experimentação em domínios operacionais distintos;
utilização de contratos mais complexos;
testes de estresse de conflitos e ambiguidades;
reprodução por sessões independentes.
Limitações
A interoperabilidade possui apenas evidência inicial.
A compatibilidade universal entre agentes de IA não foi demonstrada.
A economia de tokens não foi validada.
A redução de tempo foi observada, mas não foi causalmente validada.
A independência de modelo permanece em validação.
O IOP não constitui padrão do ICFACTORY.
A padronização do IOP não está autorizada.
A integração do IOP ao Framework não está autorizada.
Os experimentos foram originados no contexto da Onda 4 do H&A CORE.
Validações em projetos e domínios distintos permanecem necessárias.
Observações
Esta Discovery:
permanece classificada como EM VALIDAÇÃO;
preserva DC-001 como referência de proveniência;
não produz efeito normativo;
não promove o IOP ao Framework;
não altera a Constituição;
não altera o Léxico;
não atribui autoridade institucional aos agentes de IA;
não declara interoperabilidade universal;
não declara economia de tokens como fato;
não atribui causalmente redução de tempo ao IOP.
Sua eventual promoção dependerá do Discovery Lifecycle e de decisão institucional futura expressamente autorizada.
