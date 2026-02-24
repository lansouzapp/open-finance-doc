---
id: 1267990659
title: Informações Gerais - [DC] Financiamento - v2.4.0
version: 4
modified: 2025-11-14T19:57:35.921Z
url: /spaces/OF/pages/1267990659/Informa+es+Gerais+-+DC+Financiamento+-+v2.4.0
---

**Visão Geral**A API Financings viabiliza o compartilhamento de informações das Operações de Crédito do tipo Financiamento.
## Financiamentos : (GET /financings/v2/contracts)
**Visão Geral**Obtém dados referentes à operação de crédito de FinanciamentosTags: CNPJ (CNPJ Number), CPF - Cadastro de Pessoa Física (CPF Number) e Financiamento (Financing).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContracts_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_financingsGetContracts_v2.4.0.csv)
## Financiamentos - Contrato : (GET /financings/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de FinanciamentosTags: CNPJ (CNPJ Number), CPF - Cadastro de Pessoa Física (CPF Number) , Custo Efetivo Total (CET), Encargo (Charge), Ente Consignante (CnpjConsignee), Financiamento (Financing), Identificador Padronizado da Operação de Crédito – Ipoc Code, Indexador (Indexer), Sistema de Amortização Constante (SAC), Sistema de Amortização Misto (SAM), Sistema Francês de Amortização (Price), Tarifa (Fee), Taxa Efetiva (EffectiveTax) e Taxa nominal (NominalTax).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractId_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_financingsGetContractsContractId_v2.4.0.csv)
## Financiamentos - Garantias do Contrato : (GET /financings/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Financiamentos contratadaTags: Financiamento (Financing), Garantia (Warranty) e Sistema de Amortização Misto (SAM).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdWarranties_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_financingsGetContractsContractIdWarranties_v2.4.0.csv)
## Financiamentos - Pagamentos do Contrato : (GET /financings/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Financiamentos contratadasTags: Encargo (Charge), Financiamento (Financing), Identificador Padronizado da Operação de Crédito – Ipoc Code, Saldo Devedor (Outstanding Balance), Sistema de Amortização Constante (SAC), Sistema de Amortização Misto (SAM), Sistema Francês de Amortização (Price) e Tarifa (Fee).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdPayments_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_financingsGetContractsContractIdPayments_v2.4.0.csv)
## Financiamentos - Parcelas do Contrato : (GET /financings/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Financiamentos contratadasTags: Financiamento (Financing) e Prestação Regular (Instalment).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/financingsGetContractsContractIdScheduledInstalments_v2.4.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_financingsGetContractsContractIdScheduledInstalments_v2.4.0.csv)