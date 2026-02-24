---
id: 17374072
title: Informações Gerais - Financiamento - v2.0.0
version: 1
modified: 2022-10-27T12:03:14.492Z
url: /spaces/OF/pages/17374072/Informa+es+Gerais+-+Financiamento+-+v2.0.0
---

**Visão Geral**A API Financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Financiamento.
## Financiamentos : (GET /financings/v2/contracts)
**Visão Geral**Obtém dados referentes à operação de crédito de FinanciamentosTags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [CPF - Cadastro de Pessoa Física (CPF Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCPF) e [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContracts_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_contract_list.csv)
## Financiamentos - Contrato : (GET /financings/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de FinanciamentosTags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [CPF - Cadastro de Pessoa Física (CPF Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCPF), [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento), [Identificador Padronizado da Operação de Crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema de Amortização Misto (SAM)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAM), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractId_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_contract.csv)
## Financiamentos - Garantias do Contrato : (GET /financings/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Financiamentos contratadaTags: [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento), [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia) e [Sistema de Amortização Misto (SAM)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAM).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdWarranties_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_warranties.csv)
## Financiamentos - Pagamentos do Contrato : (GET /financings/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Financiamentos contratadasTags: [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento), [Identificador Padronizado da Operação de Crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema de Amortização Misto (SAM)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAM), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdPayments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_payments.csv)
## Financiamentos - Parcelas do Contrato : (GET /financings/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Financiamentos contratadasTags: [Financiamento (Financing)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioFinanciamento) e [Prestação Regular (Instalment)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrestacaoRegular).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdScheduledInstalments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_financings_scheduled_instalments.csv)