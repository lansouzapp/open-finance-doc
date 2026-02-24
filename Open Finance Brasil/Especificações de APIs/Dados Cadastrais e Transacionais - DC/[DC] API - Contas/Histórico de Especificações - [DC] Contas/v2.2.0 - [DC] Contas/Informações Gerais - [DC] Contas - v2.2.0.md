---
id: 245760301
title: Informações Gerais - [DC] Contas - v2.2.0
version: 4
modified: 2024-01-12T20:05:30.362Z
url: /spaces/OF/pages/245760301/Informa+es+Gerais+-+DC+Contas+-+v2.2.0
---

22
## Visão Geral
A API Accounts viabiliza o compartilhamento das informações de contas de depósito à vista, contas de poupança e contas de pagamento pré-paga tais como limites, transações e saldos.
## Lista de contas : ( GET /accounts/v2/accounts)
Obtém a lista de contas consentidas pelo cliente.Método para obter a lista de contas depósito à vista, poupança e pagamento pré-pagas mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccounts_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_accountsGetAccounts_v2.csv)
## Identificação da conta : ( GET /accounts/v2/accounts/{accountId})
Obtém os dados de identificação da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre a Identificação de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountId_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_accountsGetAccountsAccountId_v2.csv)
## Saldos da conta : (GET /accounts/v2/accounts/{accountId}/balances)
Obtém os saldos da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre os saldos de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdBalances_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_accountsGetAccountsAccountIdBalances_v2.csv)
## Transações da conta : ( GET /accounts/v2/accounts/{accountId}/transactions)
Obtém a lista de transações da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre as transações efetivadas e os pagamentos autorizados de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdTransactions_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_accountsGetAccountsAccountIdTransactions_v2.csv)
## Transações da conta : ( GET /accounts/v2/accounts/{accountId}/transactions-current)
Obtém a lista de transações da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre as transações efetivadas e os pagamentos autorizados de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdTransactionsCurrent_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_accountsGetAccountsAccountIdTransactionsCurrent_v2.csv)
## Limites da conta : (GET /accounts/v2/accounts/{accountId}/overdraft-limits)
Obtém os dados de limite de cheque especial e de adiantamento a depositante da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre os valores utilizado e disponível do limite do Cheque Especial e o valor em excesso (Adiantamento a depositante) de uma conta de depósito à vista, referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdOverdraftLimits_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_accountsGetAccountsAccountIdOverdraftLimits_v2.csv)