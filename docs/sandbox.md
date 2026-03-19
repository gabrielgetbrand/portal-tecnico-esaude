# Sandbox (Ambiente de Testes)

O ambiente de **Sandbox** do e-saúdeSP é uma instância de testes isolada, projetada para que desenvolvedores e empresas de software possam validar suas integrações com segurança antes da homologação formal.

Este ambiente utiliza dados sintéticos (fictícios) e cenários padronizados para garantir a interoperabilidade técnica.

---

## Como obter acesso

O acesso ao Sandbox é restrito e exige o fornecimento de credenciais de autenticação (*Client ID* e *Client Secret*).

### Opção 1: Via Formulário (Recomendado)
Para agilizar o provisionamento das suas chaves, preencha o formulário oficial de solicitação:

* 📝 **[Acessar Formulário de Solicitação de Sandbox]([ADICIONAR_LINK_DO_GOOGLE_FORMS])**
    * *Prazo de resposta: Até 48h úteis.*

### Opção 2: Via E-mail Institucional
Encaminhe sua solicitação para a nossa equipe de interoperabilidade:

* 📧 **E-mail:** [ADICIONAR_E-MAIL_AQUI]
* **Assunto:** Solicitação de Acesso ao Sandbox - Nome da sua Empresa

---

## Regras e Limites de Uso

Para garantir a estabilidade do ambiente para todos os usuários, aplicam-se as seguintes regras:

1. **Privacidade (LGPD):** É **terminantemente proibido** o envio de dados reais de pacientes (CPFs reais, nomes, endereços ou prontuários verdadeiros). Utilize apenas dados sintéticos.
2. **Rate Limit:** O limite de requisições é de **100 chamadas por minuto** por credencial. Exceder este limite resultará em erro *HTTP 429 (Too Many Requests)*.
3. **Persistência:** O banco de dados do Sandbox é resetado mensalmente. Não utilize este ambiente para armazenamento de longo prazo.
4. **Segurança:** As credenciais são de uso exclusivo da empresa solicitante e não devem ser compartilhadas.

---

## Cenários de Referência e Testes

O Sandbox está configurado para aceitar os cenários descritos nos manuais técnicos:

* **Cenário 1 (CDEM-RAC):** Registro de atendimento ambulatorial com identificação do profissional (CBO) e procedimento realizado.
* **Cenário 2 (RISAH):** Fluxo de internação hospitalar, incluindo entrada, permanência e alta.

### Checklist de "Smoke Tests" (Validação Inicial):
Antes de solicitar a homologação, valide se o seu sistema executa com sucesso:
- [ ] **Autenticação:** Obtenção do Token JWT via OAuth2.
- [ ] **Validação Estrutural:** Envio de um Resource *Patient* sem erros de Schema.
- [ ] **Escrita de Dados:** Recebimento do status *HTTP 201 Created* ao enviar um atendimento.
- [ ] **Consulta:** Recuperação de um recurso previamente enviado via ID.

---

## Status do Ambiente

* **Status Atual:** ✅ Operacional
* **Janelas de Manutenção:** Terças-feiras, das 22h às 02h (Pode haver instabilidade).

> **Nota:** Se você encontrar comportamentos inesperados ou erros 500 recorrentes, consulte nossa página de [Suporte e Comunicação](suporte.md) para verificar se há incidentes em aberto.
