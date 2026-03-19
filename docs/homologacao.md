# Processo de Homologação

O objetivo desta etapa é garantir a interoperabilidade técnica e a qualidade mínima dos dados antes da entrada em produção, com critérios objetivos e evidências auditáveis.

## Etapas e Gates de Aprovação

| Etapa | O que é testado | Critério de passagem (gate) |
|---|---|---|
| **Etapa 0 - Cadastro** | Cadastro do fornecedor/sistema, responsáveis técnicos, CNES/unidades alvo, versão do sistema. | Cadastro aprovado e canal de contato definido. |
| **Etapa 1 - Sandbox** | Provisionamento de credenciais/certificados, acesso a endpoints e dados sintéticos. | Smoke tests executados com sucesso. |
| **Etapa 2 - Conformidade FHIR** | Validação estrutural (perfis, cardinalidades) e terminologias. | 0 falhas críticas; warnings dentro do limite definido. |
| **Etapa 3 - Cenários funcionais** | Execução de casos de uso obrigatórios (CDEM-RAC e/ou RISAH) e evidências. | 100% dos cenários obrigatórios aprovados. |
| **Etapa 4 - Não funcionais** | Teste de desempenho básico, retries, idempotência, e segurança operacional. | Sem vulnerabilidades críticas; comportamento consistente. |
| **Etapa 5 - Homologação formal** | Registro do resultado, escopo homologado, versão do sistema e data. | Publicação do status de homologado e autorização para produção. |

## Evidências Exigidas (Mínimo)
Para a homologação, o fornecedor deve apresentar:
* Payloads (JSON) enviados e recebidos (incluindo OperationOutcome em falhas).
* Logs com correlation/request-id, timestamps e identificação do ambiente.
* Relatório de execução de testes (casos, resultados, evidências vinculadas).
* Registro de versão do sistema e do IG/pacote utilizado.
* Plano de contingência (comportamento em indisponibilidade/timeout; reenvio seguro).
