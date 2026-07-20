# R-03 — Research Log: Autenticidade Custodial

Status: **ATIVO**

Data de abertura: 2026-07-20 (America/Sao_Paulo)

## Regras do log

- entradas são acrescentadas; não devem ser sobrescritas;
- fatos, hipóteses, decisões e lacunas são separados;
- nenhuma entrada promove conceito ou altera governança;
- fontes locais são identificadas por caminho/hash quando material;
- referências externas devem ser primárias e abertas sempre que possível.

## R03-L001 — Abertura da pesquisa

- **Tipo:** decisão de pesquisa.
- **Pergunta:** como comprovar objetivamente que ato foi emitido pela Custódia oficial?
- **Escopo:** identidade, competência, integridade, oficialidade, continuidade e histórico.
- **Maturidade:** P.
- **Restrições:** nenhuma alteração normativa, chave oficial, assinatura real, release, commit ou push.

## R03-L002 — Congelamento do corpus local

- **Tipo:** evidência documental.
- **Resultado:** autoridades de titularidade, sucessão e escopo foram localizadas.

| Documento | SHA-256 em 2026-07-20 |
|---|---|
| `METHODOLOGICAL_CUSTODIAN_REGISTER.md` | `EAA0602F16C69EC433CA210CF22D6251E2EB96455C4AA12B4EE365F585FA0580` |
| `CUSTODIAL_APPOINTMENT_POLICY.md` | `174E0975B3CBDDA011EAB690B0AE493345EAEE4503B442FA3B81D34B1E726B66` |
| `GP_FW_02F_METHODOLOGICAL_CUSTODIAN_APPOINTMENT.md` | `172FD0B2D70E2D62728878261D1E1C2DACBD4C042A7E8062EA396F915C2EF4E4` |
| `METHODOLOGICAL_CUSTODY_MODEL.md` | `3F6E0DE754BE75BA2C9ED2D8B3835249D596473859E3CACB3BE527864F9A6873` |
| `CONSTITUTIONAL_LEXICON.md` | `73C39120D4F283CC24801F2F33A93FD01C72187400FDF7ACC3560C2DD0142C0C` |

- **Fato:** o corpus identifica titular, `CM-001`, escopo e vigência.
- **Lacuna:** não existe chave pública, assinatura, certificado, manifesto canônico ou cadeia criptográfica oficial.

## R03-L003 — Busca de mecanismos preexistentes

- **Tipo:** inspeção do corpus local.
- **Busca:** assinatura digital, chave pública, credencial/certificado custodial, cadeia de atos, hash documental e releases oficiais.
- **Resultado:** nenhum mecanismo de autenticidade custodial foi localizado em HANDA_CORE ou no novo repositório.
- **Observação:** PROTEUS contém menções a assinatura digital em outro domínio, geralmente adiada por falta de necessidade; essas menções não constituem mecanismo custodial e não foram reutilizadas como autoridade.

## R03-L004 — Decomposição do problema

- **Tipo:** hipótese analítica.
- **Dimensões:** identidade, competência, integridade, oficialidade e continuidade.
- **Resultado:** nenhum controle único cobre todas as dimensões.
- **Implicação:** comparação deve avaliar combinações, não apenas algoritmos.

## R03-L005 — Hash documental

- **Tipo:** referência técnica.
- **Fonte:** [NIST FIPS 180-4](https://csrc.nist.gov/pubs/fips/180-4/upd1/final).
- **Achado:** digests podem detectar alteração de mensagens.
- **Limite:** hash não identifica emissor nem competência; novo conteúdo pode vir acompanhado de novo hash.
- **Decisão de pesquisa:** manter hash como camada de integridade, nunca autenticação completa.

## R03-L006 — Assinaturas digitais abertas

- **Tipo:** referência técnica.
- **Fontes:** [RFC 8032](https://www.rfc-editor.org/info/rfc8032/) e [RFC 9580](https://www.rfc-editor.org/info/rfc9580/).
- **Achado:** existem algoritmos e formatos interoperáveis para assinatura e chave pública.
- **Limite:** validade matemática da assinatura não cria vínculo institucional entre chave e Custódia.
- **Decisão de pesquisa:** investigar assinatura destacada vinculada a registro de chave e designação.

## R03-L007 — Canonicalização

- **Tipo:** referência técnica.
- **Fonte:** [RFC 8785](https://www.rfc-editor.org/rfc/rfc8785.html).
- **Achado:** hashing/assinatura reproduzíveis exigem representação invariável; JCS oferece canonicalização JSON determinística.
- **Limite:** RFC 8785 é informacional e a implementação precisa ser testada entre linguagens.
- **Decisão de pesquisa:** comparar JSON canônico com formato textual rígido; não adotar nesta fase.

## R03-L008 — Versionamento e Git

- **Tipo:** referência técnica.
- **Fonte:** [documentação oficial git-tag](https://git-scm.com/docs/git-tag.html).
- **Achado:** Git suporta tags criptograficamente assinadas e verificação com backends variados.
- **Limite:** tag não define qual repositório é oficial e mantém dependência de Git se usada sozinha.
- **Decisão de pesquisa:** tratar tag/release como projeção opcional de pacote portável.

## R03-L009 — Certificados e carimbo temporal

- **Tipo:** comparação de alternativas.
- **Fontes:** [RFC 5280](https://www.rfc-editor.org/info/rfc5280/) e [RFC 3161](https://www.rfc-editor.org/info/rfc3161/).
- **Achado:** X.509 trata certificados/revogação; TSP adiciona prova temporal por TSA.
- **Limite:** ambos introduzem política e terceiros adicionais.
- **Decisão de pesquisa:** manter como integrações opcionais, não raiz mínima obrigatória.

## R03-L010 — Hipótese H-R03-01

- **Tipo:** formulação de hipótese.
- **Nome:** Envelope Custodial Portável em Camadas.
- **Componentes:** registro de custódia, registro de chave, manifesto canônico, digests, assinatura destacada, cadeia de atos, versão/release e publicação multiponto.
- **Justificativa:** cobre as cinco dimensões com controles independentes e verificáveis offline.
- **Estado:** hipótese líder, não validada.

## R03-L011 — Continuidade de custódia

- **Tipo:** hipótese de sucessão.
- **Transição ordinária:** ato encadeado e assinado pelas chaves anterior/nova quando possível.
- **Transição excepcional:** ato constitucional explícito forma nova âncora quando chave/titular anterior indisponível.
- **Risco:** dupla assinatura não resolve incapacidade, falecimento ou perda de chave.
- **Decisão de pesquisa:** preservar registro temporal de todas as chaves e distinguir expiração de comprometimento.

## R03-L012 — Múltiplos custodiantes/conselho

- **Tipo:** alternativa de governança.
- **Benefício:** resiliência e redução de ponto único.
- **Risco:** altera modelo singular ratificado, cria quórum, conflitos e complexidade.
- **Decisão de pesquisa:** não incluir no envelope mínimo; testar apenas se evidência futura justificar nova governança.

## R03-L013 — Replicabilidade

- **Tipo:** hipótese de generalização.
- **Achado:** estrutura parece replicável para projetos com autoridade própria.
- **Condição:** namespaces, chaves, registros e cadeias de projeto devem permanecer separados do ICFACTORY.
- **Lacuna:** nenhuma aplicação externa foi executada.

## R03-L014 — Avaliação inicial

- **Problema caracterizado:** sim.
- **Alternativas catalogadas:** sim, 17 alternativas e 3 famílias de formato.
- **Hipótese mais consistente:** H-R03-01.
- **Potencial de Discovery:** sim, ainda P.
- **Continuidade recomendada:** sim.
- **Motivo:** faltam protótipo, vetores, duas implementações, ataque/fork, rotação, recuperação e piloto externo.

## R03-L015 — Próxima fase proposta

- criar schema candidato sem autoridade oficial;
- usar somente chaves de teste;
- produzir vetores positivos e negativos;
- implementar/verificar offline em duas ferramentas;
- medir simplicidade e erros humanos;
- simular sucessão e comprometimento;
- testar fora de Git e em projeto-piloto;
- submeter a revisão de segurança independente.

## Estado de encerramento desta execução

A fase documental inicial foi concluída. A pesquisa R-03 permanece aberta em P para experimentação controlada. Nenhum mecanismo foi adotado, nenhum ato foi assinado e nenhuma autoridade vigente foi alterada.
