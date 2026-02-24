---
id: 207717414
title: Informações Gerais - [DC] Direitos Creditórios Descontados - v2.1.1
version: 3
modified: 2023-12-06T14:50:06.443Z
url: /spaces/OF/pages/207717414/Informa+es+Gerais+-+DC+Direitos+Credit+rios+Descontados+-+v2.1.1
---

Visão GeralA API Invoice-financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Direitos Creditórios Descontados.
## Direitos Creditórios Descontados : (GET /invoice-financings/v2/contracts)
**Visão Geral**Conjunto de informações de contratos de direitos creditórios descontados mantidos pelo cliente na instituição transmissora e para os quais ele tenha fornecido consentimentoTags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-(Invoice-Financing)) e [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContracts_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContracts.csv?api=v2&download=true)
## Direitos Creditórios Descontados - Contrato : (GET /invoice-financings/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de Direitos Creditórios DescontadosTags: [Custo Efetivo Total (CET)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Custo-Efetivo-Total-(CET)), [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-(Invoice-Financing)), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-(Charge)), [Ente Consignante (CnpjConsignee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Ente-Consignante-(CnpjConsignee)), [Identificador padronizado da operação de crédito – Ipoc Code](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Identificador-Padronizado-da-Opera%C3%A7%C3%A3o-de-Cr%C3%A9dito-%E2%80%93-Ipoc-Code), [Indexador (Indexer)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Indexador-(Indexer)), [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-(Fee)), [Taxa Efetiva (EffectiveTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-Efetiva-(EffectiveTax)) e [Taxa nominal (NominalTax)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Taxa-nominal-(NominalTax)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractId_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractId.csv?api=v2&download=true)
## Direitos Creditórios Descontados - Garantias do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Direitos Creditórios Descontados contratadaTags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-(Invoice-Financing)) e [Garantia (Warranty)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Garantia-(Warranty)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdWarranties_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractIdWarranties.csv?api=v2&download=true)
## Direitos Creditórios Descontados - Pagamentos do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Direitos Creditórios Descontados contratadasTags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-(Invoice-Financing)), [Encargo (Charge)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Encargo-(Charge)), [Saldo Devedor (Outstanding Balance)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Saldo-Devedor-(Outstanding-Balance)) e [Tarifa (Fee)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Tarifa-(Fee)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdPayments_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractIdPayments.csv?api=v2&download=true)
## Direitos Creditórios Descontados - Parcelas do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Direitos Creditórios Descontados contratadasTags: [Direito Creditório Descontado (Invoice Financing)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17379230#Direito-Credit%C3%B3rio-Descontado-(Invoice-Financing)).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdScheduledInstalments_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/10059965/invoiceFinancingsGetContractsContractIdScheduledInstalments.csv?api=v2&download=true)