---
id: 17371421
title: Informações Gerais - Cartão de Crédito - v1.0.4
version: 1
modified: 2022-10-27T12:02:45.708Z
url: /spaces/OF/pages/17371421/Informa+es+Gerais+-+Cart+o+de+Cr+dito+-+v1.0.4
---

**Visão Geral**A API Credit-cards-accounts viabiliza o compartilhamento dos dados de conta pós-paga(cartão de crédito), tais como limites, transações e faturas.
## Lista de cartões de crédito: (GET /credit-cards-accounts/v1/accounts)
**Visão Geral**Método para obter a lista de contas de pagamento pós-paga mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimentoTags: [Bandeira (Credit Card Network)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioBandeira), [Cartão Múltiplo (Multiple CreditCard)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCartaoMultiplo), [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ) e [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/creditCardsGetAccounts_v1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_list.csv)
## Identificação de cartão de crédito : (GET /credit-cards-accounts/v1/accounts/{creditCardAccountId})
**Visão Geral**Obtém dados relativos ao conjunto de informações referentes à identificação da conta de pagamento pós-pagaTags: [Bandeira (Credit Card Network)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioBandeira), [Cartão Múltiplo (Multiple CreditCard)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCartaoMultiplo), [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ) e [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga).
Visão de alto de nível das estruturas de dados**DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/creditCardsGetAccountsCreditCardAccountId_v1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_identification.csv)
## Limites de cartão de crédito : ( GET /credit-cards-accounts/v1/accounts/{creditCardAccountId}/limits)
**Visão Geral**Obtém dados dos limites: de Crédito Total e por Modalidade de Crédito relativos à conta de pagamento pós-paga.Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Empréstimo Cartão Consignado (Payroll Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimoCartaoConsignado) e [Limite Flexível (Flexible Limit)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioLimiteFlexivel).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/creditCardsGetAccountsCreditCardAccountIdLimits_v1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_limits.csv)
## Transações de cartão de crédito : (GET /credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions)
**Visão Geral**Obtém dados das transações relativas à conta de pagamento pós-paga.Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [MCC (Merchant Category Code)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioMCC).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/creditCardsGetAccountsCreditCardAccountIdTransactions_v1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_transactions.csv)
## Fatura de Cartão de Crédito : (GET /credit-cards-accounts/v1/accounts/{creditCardAccountId}/bills)
**Visão Geral**Obtém dados referentes à fatura da conta de pagamento pós-paga.Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [Fatura (Bill)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFatura).Visão de alto de nível das estruturas de dadosDER - Diagramas de Entidade e Relacionamento
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/creditCardsGetAccountsCreditCardAccountIdBills_v1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_bill.csv)
## Transações de cartão de crédito por fatura : (GET /credit-cards-accounts/v1/accounts/{creditCardAccountId}/bills/{billId}/transactions)
**Visão Geral**Obtém a lista de transações da conta identificada por creditCardAccountId e billId.Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Conta de pagamento pós-paga (Credit Card)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioContaPagamentoPosPaga), [Crédito Rotativo (Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCreditoRotativo) e [MCC (Merchant Category Code)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioMCC).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/creditCardsGetAccountsCreditCardAccountIdBillsBillIdTransactions_v1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_credit_cards_accounts_transactions.csv)