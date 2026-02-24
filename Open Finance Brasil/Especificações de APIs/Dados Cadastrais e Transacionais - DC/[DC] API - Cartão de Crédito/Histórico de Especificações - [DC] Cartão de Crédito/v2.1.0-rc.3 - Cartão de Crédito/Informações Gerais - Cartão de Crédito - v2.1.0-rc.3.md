---
id: 193691666
title: Informações Gerais - Cartão de Crédito - v2.1.0-rc.3
version: 3
modified: 2023-10-13T20:58:18.469Z
url: /spaces/OF/pages/193691666/Informa+es+Gerais+-+Cart+o+de+Cr+dito+-+v2.1.0-rc.3
---

**Visão Geral**A API Credit-cards-accounts viabiliza o compartilhamento dos dados de conta pós-paga(cartão de crédito), tais como limites, transações e faturas.
## Lista de cartões de crédito: (GET /credit-cards-accounts/v2/accounts)
**Visão Geral**Método para obter a lista de contas de pagamento pós-paga mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimentoTags: [Bandeira (Credit Card Network)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Bandeira-(Credit-Card-Network)), [Cartão Múltiplo (Multiple CreditCard)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cart%C3%A3o-M%C3%BAltiplo-(Multiple-CreditCard)), [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccounts_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts.csv?api=v2&download=true)
## Identificação de cartão de crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId})
**Visão Geral**Obtém dados relativos ao conjunto de informações referentes à identificação da conta de pagamento pós-pagaTags: [Bandeira (Credit Card Network)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Bandeira-(Credit-Card-Network)), [Cartão Múltiplo (Multiple CreditCard)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cart%C3%A3o-M%C3%BAltiplo-(Multiple-CreditCard)), [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)).
Visão de alto de nível das estruturas de dados**DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountId_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId.csv?api=v2&download=true)
## Limites de cartão de crédito : ( GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits)
**Visão Geral**Obtém dados dos limites: de Crédito Total e por Modalidade de Crédito relativos à conta de pagamento pós-paga.Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)), [Empréstimo Cartão Consignado (Payroll Loan)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Empr%C3%A9stimo-Cart%C3%A3o-Consignado-(Payroll-Loan)) e [Limite Flexível (Flexible Limit)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Limite-Flex%C3%ADvel-(Flexible-Limit)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdLimits_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_limits.csv?api=v2&download=true)
## Transações de cartão de crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions)
**Visão Geral**Obtém dados das transações relativas à conta de pagamento pós-paga.Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-(Overdraft)) e [MCC (Merchant Category Code)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#MCC-(Merchant-Category-Code)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactions_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_transactions.csv?api=v2&download=true)
## Transações de cartão de crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current)
**Visão Geral**Obtém dados das transações relativas à conta de pagamento pós-paga.Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-(Overdraft)) e [MCC (Merchant Category Code)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#MCC-(Merchant-Category-Code)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactionsCurrent_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_transactions_current.csv?api=v2&download=true)
## Fatura de Cartão de Crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills)
**Visão Geral**Obtém dados referentes à fatura da conta de pagamento pós-paga.Tags:[CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-(Overdraft)) e [Fatura (Bill)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Fatura-(Bill)).Visão de alto de nível das estruturas de dadosDER - Diagramas de Entidade e Relacionamento
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBills_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_bills.csv?api=v2&download=true)
## Transações de cartão de crédito por fatura : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions)
**Visão Geral**Obtém a lista de transações da conta identificada por creditCardAccountId e billId.Tags: [CNPJ (CNPJ Number)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#CNPJ-(CNPJ-Number)) e [Conta de pagamento pós-paga (Credit Card)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Conta-de-Pagamento-P%C3%B3s-paga-(Credit-Card)), [Crédito Rotativo (Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#Cr%C3%A9dito-Rotativo-(Overdraft)) e [MCC (Merchant Category Code)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230/Gloss+rio#MCC-(Merchant-Category-Code)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBillsBillIdTransactions_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9863186/accounts_creditCardAccountId_bills_billId_transactions.csv?api=v2&download=true)