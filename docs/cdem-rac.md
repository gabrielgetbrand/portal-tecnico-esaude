# Modelo Informacional do Conjunto de Dados Expandido Municipal (CDEM-RAC)

[cite_start]Este documento define o Modelo Informacional do Conjunto de Dados Expandido Municipal, composto por CMD e RAC, incluindo campos, cardinalidades/ocorrências, conceito/observações, regras de preenchimento e validação[cite: 518, 519].

## I – Identificação do prontuário no sistema de origem, quando disponível
[cite_start]Identificador local do prontuário/episódio de atendimento no sistema do estabelecimento de saúde, com rastreabilidade ao sistema de origem[cite: 521].

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do prontuário no sistema de origem | Identificador estruturado (system \| value) | Identificador único do prontuário no sistema de origem. Deve ser imutável após a criação. [cite_start]Ex.: system = URI institucional do sistema (p.ex. https://<domínio>/ehr) e value = ID do prontuário/episódio[cite: 523]. |
| 2 | [1..1] | Sistema de origem | Código estruturado | Código/identificador padronizado do sistema de origem, pertencente a um catálogo municipal de sistemas. [cite_start]Usado para rastreabilidade e auditoria[cite: 523]. |
| 2 | [0..1] | Versão do prontuário no sistema de origem | Texto codificado | [cite_start]Versão/ordinal do prontuário no sistema de origem, quando houver versionamento local (ex.: v1, v2)[cite: 523]. |

*(A documentação completa dos campos continua nas próximas atualizações...)*
