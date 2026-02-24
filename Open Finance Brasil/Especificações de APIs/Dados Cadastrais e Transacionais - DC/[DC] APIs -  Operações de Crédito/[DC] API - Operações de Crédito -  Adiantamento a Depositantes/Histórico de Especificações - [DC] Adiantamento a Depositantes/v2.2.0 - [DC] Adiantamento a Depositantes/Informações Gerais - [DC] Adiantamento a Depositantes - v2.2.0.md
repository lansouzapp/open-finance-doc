---
id: 474546197
title: Informações Gerais - [DC] Adiantamento a Depositantes - v2.2.0
version: 3
modified: 2024-07-04T15:08:41.530Z
url: /spaces/OF/pages/474546197/Informa+es+Gerais+-+DC+Adiantamento+a+Depositantes+-+v2.2.0
---

none**Visão Geral**A API Unarranged-accounts-overdraft viabiliza o compartilhamento de informações das Operações de Crédito do tipo Adiantamento a Depositantes.
## Adiantamento a Depositantes : (GET /unarranged-accounts-overdraft/v2/contracts)
**Visão Geral**Obtém dados referentes à operação de crédito de Adiantamento a DepositantesTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Adiantamento-a-Depositante-(Unarranged-Account-Overdraft)) e [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual
 
- DER Lógico
 **Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContracts_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContracts.csv?api=v2&download=true)
## Adiantamento a Depositantes - Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de Adiantamento a DepositantesTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Adiantamento-a-Depositante-(Unarranged-Account-Overdraft)), [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Custo-Efetivo-Total-(CET)), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-(Charge)), [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Indexador-(Indexer)), [Sistema de Amortização Constante (SAC)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-de-Amortiza%C3%A7%C3%A3o-Constante-(SAC)), [Sistema Francês de Amortização (Price)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Sistema-Franc%C3%AAs-de-Amortiza%C3%A7%C3%A3o-(Price)), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-(Fee)), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-Efetiva-(EffectiveTax)) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-nominal-(NominalTax)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual
 
- DER Lógico
 **Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractId_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractId.csv?api=v2&download=true)
## Adiantamento a Depositantes - Garantias do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Adiantamento a Depositantes contratadaTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Adiantamento-a-Depositante-(Unarranged-Account-Overdraft)) e [Garantia (Warranty)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Garantia-(Warranty)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual
 
- DER Lógico
 **Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdWarranties_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractIdWarranties.csv?api=v2&download=true)

## Adiantamento a Depositantes - Pagamentos do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Adiantamento a Depositantes contratadasTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Adiantamento-a-Depositante-(Unarranged-Account-Overdraft)), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-(Charge)), [Saldo Devedor (Outstanding Balance)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Saldo-Devedor-(Outstanding-Balance)) e [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-(Fee)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual
 
- DER Lógico
 **Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdPayments_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractIdPayments.csv?api=v2&download=true)
## Adiantamento a Depositantes - Parcelas do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Adiantamento a Depositantes contratadasTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Adiantamento-a-Depositante-(Unarranged-Account-Overdraft)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual
 
- DER Lógico
 **Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/9961672/unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments.csv?api=v2&download=true)