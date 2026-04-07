---
title: especificacao
description: 
published: true
date: 2026-04-07T14:41:59.502Z
tags: 
editor: markdown
dateCreated: 2026-04-06T19:57:18.283Z
---

# Especificação Técnica (HL7 FHIR R4 / IG)

Esta página contém a referência técnica obrigatória para a integração de sistemas com o ecossistema **e-saúdeSP**. Todas as transações de dados devem seguir o padrão internacional **HL7 FHIR Release 4 (R4)**.

---

## Guia de Implementação (IG)

O *Implementation Guide* (IG) é o documento que define como os recursos FHIR devem ser estruturados especificamente para o cenário da Secretaria Municipal da Saúde de São Paulo.

* 🌐 **[Acessar o Guia de Implementação Online (IG Web)]** - [ADICIONAR LINK DO IG PUBLICADO]
* 📦 **[Baixar Pacote de Definições FHIR (JSON/ZIP)]** - [ADICIONAR LINK DO ARQUIVO]
    * *Utilize este pacote para importar os perfis em ferramentas de validação automática.*

---

## Perfis e Recursos (Profiles)

Cada mensagem enviada deve estar em conformidade com o seu respectivo *StructureDefinition*. Abaixo estão os principais perfis utilizados:

* **Paciente (Patient):** Regras para identificação única (CNS, CPF) e dados demográficos.
    * 🔗 [Ver detalhes do Perfil Patient]([ADICIONAR LINK])
* **Atendimento (Encounter):** Especificações para registros ambulatoriais e hospitalares.
    * 🔗 [Ver detalhes do Perfil Encounter]([ADICIONAR LINK])
* **Procedimento (Procedure):** Registro de ações clínicas baseadas na tabela SIGTAP.
    * 🔗 [Ver detalhes do Perfil Procedure]([ADICIONAR LINK])
* **Condição (Condition):** Diagnósticos padronizados via CID-10.
    * 🔗 [Ver detalhes do Perfil Condition]([ADICIONAR LINK])

---

## Terminologias e Padrões de Dados

Para garantir a interoperabilidade, o e-saúdeSP exige o uso de terminologias padronizadas nacional e municipalmente:

| Domínio | Padrão Utilizado | Link de Referência |
| :--- | :--- | :--- |
| **Procedimentos** | Tabela SIGTAP (SUS) | [ADICIONAR LINK] |
| **Diagnósticos** | CID-10 / CIAP-2 | [ADICIONAR LINK] |
| **Ocupações** | CBO (Classificação Brasileira de Ocupações) | [ADICIONAR LINK] |
| **Medicamentos** | Catálogo Nacional (Rename/TNUMM) | [ADICIONAR LINK] |
| **Identificadores** | OIDs Oficiais (CPF, CNS, CNES) | [ADICIONAR LINK] |

---

## Segurança e Autenticação

A segurança da informação é prioridade e segue as diretrizes da LGPD.

1. **Protocolo de Transporte:** TLS 1.2 ou superior (HTTPS mandatório).
2. **Autorização:** Utilização de **OAuth2 com Client Credentials**.
    * **URL do Servidor de Identidade:** `[ADICIONAR URL DO ENDPOINT DE AUTH]`
3. **Escopos (Scopes):** O acesso é granular. Exemplo: `Patient.write`, `Encounter.read`.
4. **Assinatura Digital:** (Se aplicável) [ADICIONAR REQUISITOS DE ASSINATURA DIGITAL].

---

## Padrão de Erros (OperationOutcome)

Sempre que uma transação falhar, o servidor responderá com um recurso do tipo `OperationOutcome` detalhando o erro.

* **Erros de Validação (422):** Ocorrem quando um campo obrigatório está ausente ou o formato do dado está incorreto.
* **Erros de Negócio (400):** Ocorrem quando a regra clínica não é respeitada (ex: data de alta anterior à data de admissão).
* **Erros de Segurança (401/403):** Token inválido ou sem permissão para o recurso solicitado.

---

## Convenções Técnicas Adicionais

* **Fuso Horário:** Todas as datas devem seguir o padrão ISO 8601 com fuso horário (Ex: `YYYY-MM-DDThh:mm:ss-03:00`).
* **Limite de Payload:** O tamanho máximo aceito por requisição é de **10MB**.
* **Identificadores de Transação:** O uso do cabeçalho `X-Correlation-ID` é obrigatório para rastreabilidade de logs.

>  **Dica de Implementador:** Antes de iniciar o desenvolvimento, baixe os **Exemplos de Mensagens JSON** na nossa [Central de Downloads](downloads.md).
