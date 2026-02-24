---
id: 1101955090
title: Informações Gerais - [DC] Adiantamento a Depositantes - v2.5.0-beta.1
version: 2
modified: 2025-09-01T19:28:55.842Z
url: /spaces/OF/pages/1101955090/Informa+es+Gerais+-+DC+Adiantamento+a+Depositantes+-+v2.5.0-beta.1
---

17**Visão Geral**A API Unarranged-accounts-overdraft viabiliza o compartilhamento de informações das Operações de Crédito do tipo Adiantamento a Depositantes.
## Adiantamento a Depositantes : (GET /unarranged-accounts-overdraft/v2/contracts)
**Visão Geral**Obtém dados referentes à operação de crédito de Adiantamento a DepositantesTags: Adiantamento a Depositante (Unarranged Account Overdraft) e Identificador padronizado da operação de crédito – Ipoc Code.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContracts_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_unarrangedAccountsOverdraftGetContracts_v2.5.0.csv)
## Adiantamento a Depositantes - Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de Adiantamento a DepositantesTags: Adiantamento a Depositante (Unarranged Account Overdraft), Custo Efetivo Total (CET), Encargo (Charge), Identificador padronizado da operação de crédito – Ipoc Code, Indexador (Indexer), Sistema de Amortização Constante (SAC), Sistema Francês de Amortização (Price), Tarifa (Fee), Taxa Efetiva (EffectiveTax) e Taxa nominal (NominalTax).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractId_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_unarrangedAccountsOverdraftGetContractsContractId_v2.5.0.csv)
## Adiantamento a Depositantes - Garantias do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Adiantamento a Depositantes contratadaTags: Adiantamento a Depositante (Unarranged Account Overdraft) e Garantia (Warranty).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdWarranties_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_unarrangedAccountsOverdraftGetContractsContractIdWarranties_v2.5.0.csv)

## Adiantamento a Depositantes - Pagamentos do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Adiantamento a Depositantes contratadasTags: Adiantamento a Depositante (Unarranged Account Overdraft), Encargo (Charge), Saldo Devedor (Outstanding Balance) e Tarifa (Fee).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdPayments_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_unarrangedAccountsOverdraftGetContractsContractIdPayments_v2.5.0.csv)
## Adiantamento a Depositantes - Parcelas do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Adiantamento a Depositantes contratadasTags: Adiantamento a Depositante (Unarranged Account Overdraft).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments_v2.5.0.csv)