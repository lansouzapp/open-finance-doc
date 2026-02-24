---
id: 1039073299
title: Informações Gerais - [DC] Empréstimos - v2.5.0
version: 2
modified: 2025-07-18T18:09:19.033Z
url: /spaces/OF/pages/1039073299/Informa+es+Gerais+-+DC+Empr+stimos+-+v2.5.0
---

61falsedefaultlisttrue**Visão Geral**A API Loans viabiliza o compartilhamento de informações das Operações de Crédito do tipo Empréstimo.
## Empréstimos : (GET /loans/v2/contracts)
**Visão Geral**Obtém a lista de contratos de empréstimos mantidos pelos clientes da instituição transmissora.Tags: CNPJ (CNPJ Number), Custo Efetivo Total (CET), Empréstimo (Loan), Encargo (Charge), Ente Consignante (CnpjConsignee), Identificador padronizado da operação de crédito – Ipoc Code, Indexador (Indexer), Sistema de Amortização Constante (SAC), Sistema Francês de Amortização (Price), Tarifa (Fee), Taxa Efetiva (EffectiveTax) e Taxa nominal (NominalTax).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContracts_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_loansGetContracts_v2.5.0.csv)
## Empréstimos - Contrato : (GET /loans/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de EmpréstimosTags: CNPJ (CNPJ Number), Custo Efetivo Total (CET), Empréstimo (Loan), Encargo (Charge), Ente Consignante (CnpjConsignee), Identificador padronizado da operação de crédito – Ipoc Code, Indexador (Indexer), Sistema de Amortização Constante (SAC), Sistema Francês de Amortização (Price), Tarifa (Fee), Taxa Efetiva (EffectiveTax) e Taxa nominal (NominalTax).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractId_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_loansGetContractsContractId_v2.5.0.csv)
## Empréstimos - Garantias do Contrato : (GET /loans/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Empréstimos contratadaTags: Empréstimo (Loan) e Garantia (Warranty).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdWarranties_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_loansGetContractsContractIdWarranties_v2.5.0.csv)
## Empréstimos - Pagamentos do Contrato : (GET /loans/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Empréstimos contratadasTags: Empréstimo (Loan), Encargo (Charge), Saldo Devedor (Outstanding Balance) e Tarifa (Fee).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdPayments_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_loansGetContractsContractIdPayments_v2.5.0.csv)
## Empréstimos - Parcelas do Contrato : (GET /loans/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Empréstimos contratadasTags: Empréstimo (Loan) e Prestação Regular (Instalment).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdScheduledInstalments_v2.5.0.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_loansGetContractsContractIdScheduledInstalments_v2.5.0.csv)