---
id: 17373197
title: Informações Gerais - Empréstimos - v2.0.0
version: 1
modified: 2022-10-27T12:03:05.087Z
url: /spaces/OF/pages/17373197/Informa+es+Gerais+-+Empr+stimos+-+v2.0.0
---

**Visão Geral**A API Loans viabiliza o compartilhamento de informações das Operações de Crédito do tipo Empréstimo.
## Empréstimos : (GET /loans/v2/contracts)
**Visão Geral**Obtém a lista de contratos de empréstimos mantidos pelos clientes da instituição transmissora.Tags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Empréstimo (Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimo), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContracts_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_loans_contract_list.csv)
## Empréstimos - Contrato : (GET /loans/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de EmpréstimosTags: [CNPJ (CNPJ Number)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCNPJ), [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Empréstimo (Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimo), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Ente Consignante (CnpjConsignee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEnteConsignante), [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractId_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_loans_contract.csv)
## Empréstimos - Garantias do Contrato : (GET /loans/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Empréstimos contratadaTags: [Empréstimo (Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimo) e [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdWarranties_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_loans_warranties.csv)
## Empréstimos - Pagamentos do Contrato : (GET /loans/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Empréstimos contratadasTags: [Empréstimo (Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimo), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdPayments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_loans_payments.csv)
## Empréstimos - Parcelas do Contrato : (GET /loans/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Empréstimos contratadasTags: [Empréstimo (Loan)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEmprestimo) e [Prestação Regular (Instalment)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrestacaoRegular).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/loansGetContractsContractIdScheduledInstalments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_loans_scheduled_instalments.csv)