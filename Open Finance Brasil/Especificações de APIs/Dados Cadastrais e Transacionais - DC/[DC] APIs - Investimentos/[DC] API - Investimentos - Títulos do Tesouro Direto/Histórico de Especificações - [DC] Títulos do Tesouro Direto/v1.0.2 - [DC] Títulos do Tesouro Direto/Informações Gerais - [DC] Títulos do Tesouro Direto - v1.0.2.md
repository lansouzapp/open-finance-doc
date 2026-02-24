---
id: 979206430
title: Informações Gerais - [DC] Títulos do Tesouro Direto - v1.0.2
version: 2
modified: 2025-05-30T18:28:01.306Z
url: /spaces/OF/pages/979206430/Informa+es+Gerais+-+DC+T+tulos+do+Tesouro+Direto+-+v1.0.2
---

**Visão Geral**API de informações de operações de Títulos do Tesouro Direto Open Finance Brasil – Fase 4. API que retorna informações de operações de investimento do tipo Títulos do Tesouro Direto mantidas nas instituições transmissoras por seus clientes, incluindo dados como informações do produto, quantidade, saldos em posição do cliente e movimentações financeiras.
## Product List: (GET /treasure-titles/v1/investments)
**Visão Geral**Obtém a lista de operações de Títulos do Tesouro Direto mantidas pelo cliente na instituição transmissora e para as quais ele tenha fornecido consentimento.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestments_v1.0.2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestments_v1.csv)
## Product Identification: (GET /treasure-titles/v1/investments/{investmentId})
**Visão Geral**Obtém os dados da operação de Títulos do Tesouro Direto identificada por investmentId.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentId_v1.0.2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentId_v1.csv)
## Balances: (GET /treasure-titles/v1/investments/{investmentId}/balances)
**Visão Geral**Obtém a posição da operação de Títulos do Tesouro Direto identificada por investmentId.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentIdBalances_v1.0.2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentIdBalances_v1.csv)
## Transactions: (GET /treasure-titles/v1/investments/{investmentId}/transactions)
**Visão Geral**Obtém as movimentações da operação (últimos 12 meses) de Títulos do Tesouro Direto identificada por investmentId.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentIdTransactions_v1.0.2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentIdTransactions_v1.csv)
## Transactions Current: (GET /treasure-titles/v1/investments/{investmentId}/transactions-current)
**Visão Geral**Obtém as movimentações recentes da operação de Títulos do Tesouro Direto identificada por investmentId. O período a ser considerado para apresentação de movimentações será de até 7 dias - 7 dias anteriores da consulta, incluindo o dia da consulta (D-6).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/treasureTitlesGetInvestmentsInvestmentIdTransactionsCurrent_v1.0.2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_treasureTitlesGetInvestmentsInvestmentIdTransactionsCurrent_v1.csv)