# Introdução ao ICFACTORY

Este guia destina-se a um leitor com competência técnica que está conhecendo o ICFACTORY pela primeira vez e deseja compreender como iniciar sua adoção sem ajuda direta do criador do framework.

Ele não substitui a Constituição, a Arquitetura de Governança, o Léxico Constitucional ou o Modelo de Constituição de Projeto. Ele apenas apresenta o primeiro caminho de adoção.

## Antes de começar

Você deve ter:

* um projeto ou sistema que necessite de governança controlada;
* uma razão para preservar auditabilidade e rastreabilidade;
* disposição para separar observação de intervenção;
* disposição para identificar a autoridade antes de realizar mudanças estruturais;
* compreensão básica de documentação técnica e arquitetura de sistemas.

Você não precisa conhecer ACI, CIE-X, ALO, OSE ou TUX antes de começar. Esses conceitos podem ser consultados posteriormente por meio do mapa de documentos.

## O que você produzirá

O primeiro resultado da adoção não é código.

O primeiro resultado deve ser uma compreensão controlada de como seu projeto se relacionará com o ICFACTORY. Na prática, isso normalmente significa iniciar uma Constituição de Projeto utilizando:

`governance/PROJECT_CONSTITUTION_TEMPLATE.md`

Ao final desta primeira etapa, você deverá ser capaz de identificar:

* o que é o seu projeto;
* por que ele necessita de governança;
* quais princípios constitucionais se aplicam;
* quais autoridades devem ser declaradas;
* quais evidências e registros serão necessários;
* se o projeto pode começar como rascunho, não vigente ou aprovado.

## Etapa 1 - Compreenda a fronteira

ICFACTORY é o framework.

Seu projeto é o domínio de implementação.

H&A é um domínio de implementação já presente neste repositório. Ele fornece contexto útil, mas não é necessário para a adoção do ICFACTORY em outros contextos.

Não presuma que componentes de runtime específicos do H&A sejam partes obrigatórias do ICFACTORY. O framework é expresso por meio de seus documentos constitucionais, de governança, conceituais e de integração inicial.

## Etapa 2 - Leia a Constituição e a Arquitetura de Governança

Leia:

1. `CONSTITUTION.md`
2. `governance/GOVERNANCE_ARCHITECTURE.md`

A Constituição explica os princípios que não podem ser contornados.

A Arquitetura de Governança explica a relação entre:

1. Constituição do ICFACTORY
2. Constituição do Projeto
3. Camada de governança operacional
4. Sistema

Nesta etapa, não tente memorizar todos os termos. O objetivo é compreender a direção da autoridade e por que o framework exige governança explícita.

## Etapa 3 - Compreenda o fluxo operacional mínimo

O ICFACTORY favorece uma sequência controlada:

1. observar o estado real;
2. auditar antes de alterar;
3. identificar autoridade e escopo;
4. projetar a menor mudança segura;
5. obter aprovação explícita;
6. aplicar somente a mudança aprovada;
7. validar comportamento e evidências;
8. registrar o resultado.

Esse fluxo é explicado em mais detalhes na `documentação do método ICFACTORY`.

Para a integração inicial, o ponto importante é simples: o ICFACTORY não trata a implementação como a primeira etapa. Ele considera compreensão, autoridade e evidência como pré-requisitos para a implementação.

## Etapa 4 - Abra o Modelo de Constituição de Projeto

Abra:

`governance/PROJECT_CONSTITUTION_TEMPLATE.md`

Utilize-o como artefato inicial para adoção.

Não copie o Léxico Constitucional para o modelo. Não reproduza o modelo dentro de outro documento de integração inicial. Trabalhe diretamente no modelo quando estiver pronto para criar uma Constituição de Projeto.

Durante a primeira etapa, concentre-se apenas nas áreas principais:

* identificação do projeto;
* compatibilidade constitucional;
* governança documental;
* autoridades constitucionais;
* aprovação e vigência;
* conformidade e remediação;
* missão, objetivos, prioridades, restrições e governança.

Se um campo ainda não puder ser preenchido, mantenha-o como uma decisão controlada em rascunho, em vez de inventar autoridade ou evidência.

## Etapa 5 - Consulte o Léxico somente quando necessário

Utilize:

`CONSTITUTIONAL_LEXICON.md`

O léxico é a referência semântica autoritativa. Ele não é o melhor documento para uma primeira leitura.

Consulte-o quando precisar de precisão sobre termos como validade, vigência, aprovação constitucional, conformidade, remediação ou escopo de autoridade.

Não utilize o léxico como substituto do modelo. O léxico define significados; o modelo estrutura uma Constituição de Projeto.

## Critérios de prontidão para adoção inicial

Você está pronto para continuar a adoção quando conseguir responder:

* Qual é o projeto que está adotando o ICFACTORY?
* Qual problema torna a governança necessária?
* Qual documento é o rascunho da Constituição do Projeto?
* Quais autoridades devem ser identificadas?
* Quais evidências são necessárias para validação, aprovação e vigência?
* Quais partes do projeto ainda são desconhecidas ou não aplicáveis?
* Quais documentos do ICFACTORY são referências e quais são artefatos de trabalho?

Se essas perguntas ainda não puderem ser respondidas, continue a leitura e o mapeamento antes de tentar realizar alterações de implementação.

## Próxima leitura

Após este guia, leia:

`DOCUMENT_MAP.md`

Utilize-o para decidir qual documento abrir em seguida de acordo com seu objetivo.

Se seu objetivo for adoção, continue com o Modelo de Constituição de Projeto.

Se seu objetivo for precisão semântica, utilize o Léxico Constitucional.

Se seu objetivo for contexto histórico, consulte posteriormente o Histórico e o Roadmap, depois que o caminho central de integração inicial estiver compreendido.

## Nota de incorporação

Este documento foi adaptado durante a GP-FW-04B para a estrutura do repositório autônomo icfactory-framework. O caminho da fonte original era C:\HANDA_CORE\ICFACTORY\GETTING_STARTED.md. O hash da fonte e a adaptação estão registrados em `provenance/HANDA_CORE_INCORPORATION_MANIFEST.md`.
