# Processo de Homologação

O objetivo desta etapa é garantir a interoperabilidade técnica e a qualidade mínima dos dados antes da entrada em produção, com critérios objetivos e evidências auditáveis.

## Etapas e Gates de Aprovação

| Etapa | O que é testado | Critério de passagem (gate) |
| :--- | :--- | :--- |
| **0 - Cadastro** | Fornecedor, responsáveis técnicos, CNES e versão do sistema. | Cadastro aprovado e canal de contato definido. |
| **1 - Sandbox** | Credenciais, certificados e acesso a endpoints com dados sintéticos. | *Smoke tests* executados com sucesso no [Ambiente de Sandbox](sandbox.md). |
| **2 - Conformidade** | Validação estrutural (perfis FHIR, cardinalidades) e terminologias. | 0 falhas críticas; warnings dentro do limite definido. |
| **3 - Funcional** | Execução de casos de uso obrigatórios ([CDEM-RAC](cdem-rac.md) e/ou [RISAH](risah.md)). | 100% dos cenários obrigatórios aprovados. |
| **4 - Não funcionais** | Desempenho básico, idempotência e segurança operacional. | Sem vulnerabilidades críticas; comportamento consistente. |
| **5 - Formal** | Registro do resultado, escopo homologado e data. | Publicação do status e autorização para Produção. |

## Evidências Exigidas (Mínimo)

Para a homologação, o fornecedor deve apresentar os seguintes artefatos:

* **Payloads (JSON):** Exemplos reais enviados e recebidos (incluindo *OperationOutcome* em falhas).
* **Logs Técnicos:** Com *correlation/request-id*, timestamps e identificação do ambiente.
* **Relatório de Testes:** Casos executados, resultados obtidos e evidências vinculadas.
* **Versão do Sistema:** Registro exato da versão do software e do pacote FHIR utilizado.
* **Plano de Contingência:** Procedimento em caso de indisponibilidade ou *timeout* (reenvio seguro).

---

### Próximos Passos
Se o seu sistema já está adequado às normas da [Base Normativa](base-normativa.md), solicite o início da Etapa 0 através do nosso canal de [Suporte](suporte.md) ou pelo formulário oficial.

> 📂 **[BAIXAR CHECKLIST DE HOMOLOGAÇÃO (PDF) - ADICIONAR LINK]**
