---
id: 1323696145
title: Informações Gerais - [DC] Cartão de Crédito - v2.4.0-beta.2
version: 6
modified: 2025-11-28T19:53:31.759Z
url: /spaces/OF/pages/1323696145/Informa+es+Gerais+-+DC+Cart+o+de+Cr+dito+-+v2.4.0-beta.2
---

**Visão Geral**A API Credit-cards-accounts viabiliza o compartilhamento dos dados de conta pós-paga(cartão de crédito), tais como limites, transações e faturas.
## Lista de cartões de crédito: (GET /credit-cards-accounts/v2/accounts)
**Visão Geral**Método para obter a lista de contas de pagamento pós-paga mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimentoTags: Bandeira (Credit Card Network), Cartão Múltiplo (Multiple CreditCard), CNPJ (CNPJ Number) e Conta de pagamento pós-paga (Credit Card).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/draft-openapi/dictionary/creditCardsGetAccounts_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/draft-openapi/dictionary/example/examples_creditCardsGetAccounts_v2.4.0.csv)
## Identificação de cartão de crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId})
**Visão Geral**Obtém dados relativos ao conjunto de informações referentes à identificação da conta de pagamento pós-pagaTags: Bandeira (Credit Card Network), Cartão Múltiplo (Multiple CreditCard), CNPJ (CNPJ Number) e Conta de pagamento pós-paga (Credit Card).
Visão de alto de nível das estruturas de dados**DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountId_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditCardsGetAccountsCreditCardAccountId_v2.4.0.csv)
## Limites de cartão de crédito : ( GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits)
**Visão Geral**Obtém dados dos limites: de Crédito Total e por Modalidade de Crédito relativos à conta de pagamento pós-paga.Tags: CNPJ (CNPJ Number), Conta de pagamento pós-paga (Credit Card), Empréstimo Cartão Consignado (Payroll Loan) e Limite Flexível (Flexible Limit).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdLimits_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditCardsGetAccountsCreditCardAccountIdLimits_v2.4.0.csv)
## Transações de cartão de crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions)
**Visão Geral**Obtém dados das transações relativas à conta de pagamento pós-paga.Tags: CNPJ (CNPJ Number), Conta de pagamento pós-paga (Credit Card), Crédito Rotativo (Overdraft) e MCC (Merchant Category Code).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactions_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditCardsGetAccountsCreditCardAccountIdTransactions_v2.4.0.csv)
## Transações de cartão de crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current)
**Visão Geral**Obtém dados das transações relativas à conta de pagamento pós-paga.Tags: CNPJ (CNPJ Number), Conta de pagamento pós-paga (Credit Card), Crédito Rotativo (Overdraft) e MCC (Merchant Category Code).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactionsCurrent_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditCardsGetAccountsCreditCardAccountIdTransactionsCurrent_v2.4.0.csv)
## Fatura de Cartão de Crédito : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills)
**Visão Geral**Obtém dados referentes à fatura da conta de pagamento pós-paga.Tags: CNPJ (CNPJ Number), Conta de pagamento pós-paga (Credit Card), Crédito Rotativo (Overdraft) e Fatura (Bill).Visão de alto de nível das estruturas de dadosDER - Diagramas de Entidade e Relacionamento
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBills_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditCardsGetAccountsCreditCardAccountIdBills_v2.4.0.csv)
## Transações de cartão de crédito por fatura : (GET /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions)
**Visão Geral**Obtém a lista de transações da conta identificada por creditCardAccountId e billId.Tags: CNPJ (CNPJ Number), Conta de pagamento pós-paga (Credit Card), Crédito Rotativo (Overdraft) e MCC (Merchant Category Code).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/creditCardsGetAccountsCreditCardAccountIdBillsBillIdTransactions_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_creditCardsGetAccountsCreditCardAccountIdBillsBillIdTransactions_v2.4.0.csv)