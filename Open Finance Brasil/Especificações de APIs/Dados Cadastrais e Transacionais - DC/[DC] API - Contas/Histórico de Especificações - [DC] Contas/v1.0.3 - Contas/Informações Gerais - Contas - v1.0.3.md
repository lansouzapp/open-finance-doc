---
id: 17372249
title: Informações Gerais - Contas - v1.0.3
version: 1
modified: 2022-10-27T12:02:54.435Z
url: /spaces/OF/pages/17372249/Informa+es+Gerais+-+Contas+-+v1.0.3
---

22
## Visão Geral
A API Accounts viabiliza o compartilhamento das informações de contas de depósito à vista, contas de poupança e contas de pagamento pré-paga tais como limites, transações e saldos.
## Lista de contas : ( GET /accounts/v1/accounts)
Obtém a lista de contas consentidas pelo cliente.Método para obter a lista de contas depósito à vista, poupança e pagamento pré-pagas mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/accountsGetAccounts_v1.csv?version=1&modificationDate=1630936193411&cacheVersion=1&api=v2&download=true)[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/examples_accounts_list.csv?version=1&modificationDate=1630936212313&cacheVersion=1&api=v2&download=true)
## Identificação da conta : ( GET /accounts/v1/accounts/{accountId})
Obtém os dados de identificação da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre a Identificação de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/accountsGetAccountsAccountId_v1.csv?version=1&modificationDate=1630936238285&cacheVersion=1&api=v2&download=true)[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/examples_accounts_identification.csv?version=1&modificationDate=1630936259633&cacheVersion=1&api=v2&download=true)
## Saldos da conta : (GET /accounts/v1/accounts/{accountId}/balances)
Obtém os saldos da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre os saldos de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/accountsGetAccountsAccountIdBalances_v1.csv?version=1&modificationDate=1630936284729&cacheVersion=1&api=v2&download=true)[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/examples_accounts_balances.csv?version=1&modificationDate=1630936301262&cacheVersion=1&api=v2&download=true)
## Transações da conta : ( GET /accounts/v1/accounts/{accountId}/transactions)
Obtém a lista de transações da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre as transações efetivadas e os pagamentos autorizados de uma conta de: depósito à vista, poupança ou de pagamento pré-paga referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/accountsGetAccountsAccountIdTransactions_v1.csv?version=1&modificationDate=1630936326318&cacheVersion=1&api=v2&download=true)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_accounts_transactions.csv)
## Limites da conta : (GET /accounts/v1/accounts/{accountId}/overdraft-limits)
Obtém os dados de limite de cheque especial e de adiantamento a depositante da conta mantidos na instituição transmissora.Essa especificação inclui todos os artefatos relevantes para a Especificação de API sobre os valores utilizado e disponível do limite do Cheque Especial e o valor em excesso (Adiantamento a depositante) de uma conta de depósito à vista, referente às informações transacionais de cliente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/accountsGetAccountsAccountIdOverdraftLimits_v1.csv?version=1&modificationDate=1630936381138&cacheVersion=1&api=v2&download=true)[Fazer download dos exemplos](https://openbankingbrasil.atlassian.net/wiki/download/attachments/1671640/examples_accounts_overdraft_limits.csv?version=1&modificationDate=1630936400244&cacheVersion=1&api=v2&download=true)