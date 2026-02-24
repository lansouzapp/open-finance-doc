---
id: 157450260
title: Informações Gerais - Contas - v2.1.0-rc.1
version: 2
modified: 2023-08-14T20:15:04.954Z
url: /spaces/OF/pages/157450260/Informa+es+Gerais+-+Contas+-+v2.1.0-rc.1
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
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccounts_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797751/accounts.csv?api=v2&download=true)
## Identificação da conta : ( GET /accounts/v2/accounts/{accountId})
Obtém os dados de identificação da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre a Identificação de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountId_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797751/accounts_accountId.csv?api=v2&download=true)
## Saldos da conta : (GET /accounts/v2/accounts/{accountId}/balances)
Obtém os saldos da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre os saldos de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdBalances_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797751/accounts_accountId_balances.csv?api=v2&download=true)
## Transações da conta : ( GET /accounts/v2/accounts/{accountId}/transactions)
Obtém a lista de transações da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre as transações efetivadas e os pagamentos autorizados de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdTransactions_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797751/accounts_accountId_transactions.csv?api=v2&download=true)
## Transações da conta : ( GET /accounts/v2/accounts/{accountId}/transactions-current)
Obtém a lista de transações da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre as transações efetivadas e os pagamentos autorizados de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdTransactionsCurrent_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797751/accounts_accountId_transactions_current.csv?api=v2&download=true)
## Limites da conta : (GET /accounts/v2/accounts/{accountId}/overdraft-limits)
Obtém os dados de limite de cheque especial e de adiantamento a depositante da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre os valores utilizado e disponível do limite do Cheque Especial e o valor em excesso (Adiantamento a depositante) de uma conta de depósito à vista, referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/accountsGetAccountsAccountIdOverdraftLimits_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9797751/accounts_accountId_overdraft_limits.csv?api=v2&download=true)