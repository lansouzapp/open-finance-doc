---
id: 1268252691
title: Informações Gerais - [DC] Direitos Creditórios Descontados - v2.4.0
version: 2
modified: 2025-11-14T20:15:39.155Z
url: /spaces/OF/pages/1268252691/Informa+es+Gerais+-+DC+Direitos+Credit+rios+Descontados+-+v2.4.0
---

Visão GeralA API Invoice-financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Direitos Creditórios Descontados.
## Direitos Creditórios Descontados : (GET /invoice-financings/v2/contracts)
**Visão Geral**Conjunto de informações de contratos de direitos creditórios descontados mantidos pelo cliente na instituição transmissora e para os quais ele tenha fornecido consentimentoTags: Direito Creditório Descontado (Invoice Financing) e Identificador padronizado da operação de crédito – Ipoc Code.**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContracts_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_invoiceFinancingsGetContracts_v2.4.0.csv)
## Direitos Creditórios Descontados - Contrato : (GET /invoice-financings/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de Direitos Creditórios DescontadosTags: Custo Efetivo Total (CET), Direito Creditório Descontado (Invoice Financing), Encargo (Charge), Ente Consignante (CnpjConsignee), Identificador padronizado da operação de crédito – Ipoc Code, Indexador (Indexer), Tarifa (Fee), Taxa Efetiva (EffectiveTax) e Taxa nominal (NominalTax).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractId_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_invoiceFinancingsGetContractsContractId_v2.4.0.csv)
## Direitos Creditórios Descontados - Garantias do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Direitos Creditórios Descontados contratadaTags: Direito Creditório Descontado (Invoice Financing) e Garantia (Warranty).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdWarranties_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_invoiceFinancingsGetContractsContractIdWarranties_v2.4.0.csv)
## Direitos Creditórios Descontados - Pagamentos do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Direitos Creditórios Descontados contratadasTags: Direito Creditório Descontado (Invoice Financing), Encargo (Charge), Saldo Devedor (Outstanding Balance) e Tarifa (Fee).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdPayments_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_invoiceFinancingsGetContractsContractIdPayments_v2.4.0.csv)
## Direitos Creditórios Descontados - Parcelas do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Direitos Creditórios Descontados contratadasTags: Direito Creditório Descontado (Invoice Financing).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdScheduledInstalments_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_invoiceFinancingsGetContractsContractIdScheduledInstalments_v2.4.0.csv)