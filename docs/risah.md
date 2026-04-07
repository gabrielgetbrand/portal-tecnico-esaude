---
title: risah
description: 
published: true
date: 2026-04-07T14:40:56.892Z
tags: 
editor: markdown
dateCreated: 2026-04-06T19:57:32.960Z
---

# Modelo Municipal do Sumário de Alta Hospitalar (RISAH)

Este documento descreve o Modelo Municipal de Informação do Registro de Internação e Sumário de Alta Hospitalar (RISAH) adotado pelo Município de São Paulo, organizado conforme os incisos I a XVII do art. 2º da Portaria GM/MS nº 8.026/2025, para integração ao Repositório Clínico Municipal – e-saúdeSP, em alinhamento aos padrões HL7 FHIR R4.

## I – Identificação do prontuário no sistema de origem
Identificador local do prontuário ou episódio de internação no sistema do estabelecimento de saúde, com rastreabilidade ao sistema de origem.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do prontuário no sistema de origem | Identificador estruturado | Identificador único do prontuário ou episódio de internação no sistema de origem. Deve ser imutável após a criação.  |
| 2 | [1..1] | Sistema de origem | Código estruturado | Código ou identificador padronizado do sistema de origem, pertencente a um catálogo municipal de sistemas. |
| 2 | [0..1] | Versão do registro no sistema de origem | Texto codificado | Versão/ordinal do registro no sistema de origem, quando houver controle de versionamento local. |

## II – Identificação do indivíduo (CPF ou CNS)
Identificação da pessoa a quem se refere o Sumário de Alta, preferencialmente por CNS ou CPF, com bloco demográfico complementar para vinculação.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Identificação do indivíduo | – | O registro deve conter CNS ou CPF. Na ausência, utilizar obrigatoriamente o bloco de identificação por dados demográficos. |
| 2 | [1..1] | Identificador nacional do indivíduo | Identificador estruturado | CPF. system deve indicar o namespace CPF. O valor deve ser validado conforme regras nacionais. |
| 2 | [0..1] | Identificação por dados demográficos | Bloco estruturado | Utilizado quando CNS/CPF não estiver disponível no momento do registro. Deve permitir posterior vinculação. |

## III – CNES do estabelecimento de internação
Identificação do estabelecimento de saúde onde ocorreu a internação.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Estabelecimento de internação | – | Bloco obrigatório de identificação do estabelecimento onde se deu a internação. |
| 2 | [1..1] | Identificador do estabelecimento de saúde | Identificador estruturado | CNES do estabelecimento onde ocorreu a internação. |
| 2 | [0..1] | Nome do estabelecimento de saúde | Texto livre | Nome do estabelecimento, conforme cadastro no CNES. |
| 2 | [0..1] | Tipo de estabelecimento | Texto codificado (CNES) | Tipo de estabelecimento conforme tipologia do CNES. |

## IV – Procedência
Identifica o serviço que encaminhou o indivíduo ou a iniciativa própria na busca pelo atendimento.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Procedência | – | Bloco obrigatório de origem do atendimento que resultou na internação. |
| 2 | [1..1] | Tipo de procedência | Texto codificado | Ordem Judicial; Retorno; Demanda espontânea; Demanda referenciada; Outros. |
| 2 | [0..1] | Detalhamento da procedência | Texto livre | Serviço/setor/unidade de origem. |

## V – Caráter da internação
Classificação da internação quanto à prioridade de sua realização.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Caráter da internação | Texto codificado | Eletiva; Urgência; Outros (quando previsto em norma). Deve ser codificado conforme value set oficial. |

## VI – Data e hora da internação
Momento em que a internação foi efetivada.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Data e hora da internação | Data e hora | Momento de aceitação do indivíduo para início da internação. |
| 1 | [0..1] | Data e hora da entrada no serviço | Data e hora | Momento em que o paciente chegou à unidade/serviço. |

## VII – Modalidade assistencial
Classificação do contato com o serviço de saúde segundo o modo, local e duração do atendimento.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Modalidade assistencial | Texto codificado | Atenção Domiciliar; Atenção Hospitalar; Atenção Intermediária; Atenção Psicossocial; Atenção à Urgência/Emergência. |

## VIII – Motivo da internação (CID / SNOMED-CT)
Motivo principal que levou à internação, codificado em terminologia clínica estruturada.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Motivo da internação | – | Bloco obrigatório. |
| 2 | [1..1] | Código do motivo da internação | Texto codificado | Diagnóstico de admissão (CID-10, CID-11 ou SNOMED-CT). |
| 2 | [1..1] | Terminologia utilizada | Identificador | Ex.: CID-10, CID-11, SNOMED-CT. |

## IX – Problemas ou diagnósticos avaliados
Conjunto de problemas/diagnósticos avaliados durante a internação.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Problemas ou diagnósticos avaliados | – | Lista estruturada de condições clínicas. |
| 2 | [1..N] | Diagnóstico/problema | – | Cada linha representa um diagnóstico/problema clínico. |
| 3 | [1..1] | Código do diagnóstico | Texto codificado | Preferencialmente SNOMED-CT. |
| 3 | [1..1] | Categoria do diagnóstico | Texto codificado | Principal; Secundário; Comorbidade; Complicação; Diagnóstico de alta. |
| 3 | [1..1] | Indicador de presença na admissão | Texto codificado | Sim; Não; Desconhecido. |

## X – Restrições funcionais ou incapacidades
Registro de restrição funcional ou incapacidade e seu status.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [0..1] | Restrições funcionais e incapacidades em saúde | – | Bloco opcional para registro de limitações funcionais. |
| 2 | [1..N] | Restrição funcional ou incapacidade | – | Cada item representa uma restrição/incapacidade. |
| 3 | [1..1] | Código da restrição/incapacidade | Texto codificado | Conceito estruturado de limitação funcional. |
| 3 | [1..1] | Status da restrição/incapacidade | Texto codificado | Ativo; Inativo; Indeterminado. |

## XI – Procedimentos realizados
Registro dos procedimentos realizados ou solicitados, com problema/diagnóstico associado, código do procedimento, status e informações temporais.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Procedimentos realizados ou solicitados | – | Bloco obrigatório. |
| 2 | [1..N] | Procedimento | – | Cada item representa um procedimento individual (realizado ou solicitado). |
| 3 | [0..1] | Problema/diagnóstico relacionado | Texto codificado | Código do problema ao qual o procedimento está relacionado. |
| 3 | [1..1] | Terminologia que descreve o procedimento | Texto codificado | OID das terminologias SIGTAP, CBHPM, TUSS ou outra terminologia adotada. |
| 3 | [1..1] | Código do procedimento | Texto codificado | Código do procedimento na terminologia informada. |
| 3 | [1..1] | Status do procedimento | Texto codificado | Planejado; Em andamento; Não realizado; Suspenso; Cancelado; Completado; Desconhecido; Entrada com erro. |

## XII – Evolução clínica (resumo)
Descrição resumida da evolução clínica durante a internação.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Resumo da evolução clínica | – | Bloco narrativo estruturado. |
| 2 | [1..1] | Descrição da evolução clínica | Texto livre | Descrição narrativa integrada da evolução clínica, principais eventos, resposta terapêutica, complicações e manejo clínico. |

## XIII – Alergias e/ou reações adversas
Informação sobre alergias e reações adversas relevantes durante a internação.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [0..N] | Alergias e/ou reações adversas na internação | – | Bloco opcional, porém recomendado quando houver alergias/reação relevante. |
| 2 | [0..N] | Alergia e/ou reação adversa | – | Cada item representa uma alergia ou reação adversa. |
| 3 | [1..1] | Categoria do agente causador | Texto codificado | Alimento; Medicamento; Fator Externo/Ambiental; Biológico; Outro. |
| 3 | [1..1] | Agente/substância específica | Texto codificado | Identificação estruturada do agente. |
| 3 | [0..1] | Severidade clínica | Texto codificado | Leve; Moderada; Grave. |

## XIV – Prescrição de medicamentos na alta
Prescrições de medicamentos na alta, em forma estruturada e/ou não estruturada.

| Nível | Ocorrência | Seção/Item | Tipo de Dados | Conceito/Observações |
|---|---|---|---|---|
| 1 | [1..1] | Prescrição da alta | – | Bloco obrigatório. |
| 2 | [0..1] | Medicamentos prescritos na alta (não estruturado) | – | Para cenários de transição. |
| 3 | [1..1] | Descrição da prescrição | Texto livre | Texto contendo um ou mais medicamentos, doses e orientações.
