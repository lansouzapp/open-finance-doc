---
id: 17375735
title: Informações Gerais - Direitos Creditórios Descontados - v2.0.0
version: 1
modified: 2022-10-27T12:03:33.138Z
url: /spaces/OF/pages/17375735/Informa+es+Gerais+-+Direitos+Credit+rios+Descontados+-+v2.0.0
---

Visão GeralA API Invoice-financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Direitos Creditórios Descontados.
## Direitos Creditórios Descontados : (GET /invoice-financings/v2/contracts)
**Visão Geral**Conjunto de informações de contratos de direitos creditórios descontados mantidos pelo cliente na instituição transmissora e para os quais ele tenha fornecido consentimentoTags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado) e[Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContracts_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_contract_list.csv)
## Direitos Creditórios Descontados - Contrato : (GET /invoice-financings/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de Direitos Creditórios DescontadosTags: [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractId_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_contract.csv)
## Direitos Creditórios Descontados - Garantias do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Direitos Creditórios Descontados contratadaTags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado) e [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdWarranties_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_warranties.csv)
## Direitos Creditórios Descontados - Pagamentos do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Direitos Creditórios Descontados contratadasTags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdPayments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_payments.csv)
## Direitos Creditórios Descontados - Parcelas do Contrato : (GET /invoice-financings/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Direitos Creditórios Descontados contratadasTags: [Direito Creditório Descontado (Invoice Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioDireitoCreditorioDescontado).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/invoiceFinancingsGetContractsContractIdScheduledInstalments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_invoice_financings_instalments.csv)