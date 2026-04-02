---
title: 
description: 
published: true
date: 2026-04-02T19:46:53.098Z
tags: 
editor: markdown
dateCreated: 2026-04-02T17:43:34.858Z
---

# Portal Técnico e-saúdeSP 
![Version](https://img.shields.io/badge/versão-1.0.0--beta-green) 

Bem-vindo ao canal oficial de integração da Secretaria Municipal da Saúde de São Paulo. Este portal é a referência única para fornecedores de software e equipes de TI que realizam a transmissão de dados assistenciais ao município.

## Transição de Modelos e Prazos

Estamos em um período de evolução tecnológica para o padrão internacional **HL7 FHIR R4**. É fundamental observar os prazos de conformidade:

* **Modelo Vigente (Temporário):** Atualmente, o repositório permanece receptivo para os envios nos formatos **RAC** e **CMD**.
* **Novo Padrão Obrigatório:** A partir de **[INSERIR DATA]**, todos os dados assistenciais deverão ser transmitidos exclusivamente nos novos modelos:
    * **CDEM-RAC:** Conjunto de Dados Expandido Municipal (Ambulatorial).
    * **RISAH:** Registro de Internação e Saúde Associada à Hospitalização (Hospitalar).

> ⚠️ **Atenção:** Recomendamos que todos os parceiros iniciem imediatamente a adequação de seus sistemas para os novos perfis FHIR, utilizando o nosso [Ambiente de Sandbox](sandbox.md).

---

## Como navegar neste Portal

Para facilitar sua implementação, o conteúdo está organizado em etapas lógicas:

1.  **[Guia de Introdução](comece-por-aqui.md):** Entenda o contexto e a [Base Normativa](base-normativa.md) (Portarias 117 e 118/2026).
2.  **[Modelos de Informação](cdem-rac.md):** Consulte as regras de negócio e mapeamentos para CDEM-RAC e RISAH.
3.  **[Desenvolvimento Técnico](especificacao.md):** Acesse o Guia de Implementação (IG), regras de segurança e autenticação.
4.  **[Homologação](homologacao.md):** Saiba como validar seu sistema e obter as credenciais de produção.

---

## Prontos para começar?

Se você é um novo integrador, o primeiro passo é realizar a leitura do manual **[Comece por aqui](comece-por-aqui.md)** e baixar o **[Kit Implementador](downloads.md)**.

Em caso de dúvidas técnicas, acesse nossa página de **[Suporte](suporte.md)**.
