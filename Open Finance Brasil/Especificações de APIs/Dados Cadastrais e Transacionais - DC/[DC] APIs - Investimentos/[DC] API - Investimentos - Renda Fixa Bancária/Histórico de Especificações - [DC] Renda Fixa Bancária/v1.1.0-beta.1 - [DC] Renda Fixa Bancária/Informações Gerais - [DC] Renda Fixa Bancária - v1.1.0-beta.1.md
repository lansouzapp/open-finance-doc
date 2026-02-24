---
id: 1115619346
title: Informações Gerais - [DC] Renda Fixa Bancária - v1.1.0-beta.1
version: 2
modified: 2025-09-08T14:21:24.317Z
url: /spaces/OF/pages/1115619346/Informa+es+Gerais+-+DC+Renda+Fixa+Banc+ria+-+v1.1.0-beta.1
---

**Visão Geral**A API bank-fixed-incomes viabiliza o compartilhamento dos dados dos produtos de investimentos de renda fixa bancária como; listagem dos produtos, detalhe do produto, posição do produto e movimentações históricas e recentes do produto do cliente.
## Product List: (GET /bank-fixed-incomes/v1/investments)
**Visão Geral**Obtém a lista de operações de Renda Fixa Bancária mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestments_v1.1.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestments_v1.csv)
## Product Identification: (GET /bank-fixed-incomes/v1/investments/{investmentId})
**Visão Geral**Obtém os dados da operação de Renda Fixa Bancária identificada por investmentId.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentId_v1.1.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentId_v1.csv)
## Balances: (GET /bank-fixed-incomes/v1/investments/{investmentId}/balances)
**Visão Geral**Obtém a posição da operação de Renda Fixa Bancária identificada por investmentId.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdBalances_v1.1.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentIdBalances_v1.csv)
## Transactions: (GET /bank-fixed-incomes/v1/investments/{investmentId}/transactions)
**Visão Geral**Obtém as movimentações da operação de Renda Fixa Bancária identificada por investmentId.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.1.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_bankFixedIncomesGetInvestmentsInvestmentIdTransactions_v1.csv)
## Transactions Current: (GET /bank-fixed-incomes/v1/investments/{investmentId}/transactions-current)
**Visão Geral**Obtém as movimentações recentes da operação de Fundos de Investimento identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/banktFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.1.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_banktFixedIncomesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)