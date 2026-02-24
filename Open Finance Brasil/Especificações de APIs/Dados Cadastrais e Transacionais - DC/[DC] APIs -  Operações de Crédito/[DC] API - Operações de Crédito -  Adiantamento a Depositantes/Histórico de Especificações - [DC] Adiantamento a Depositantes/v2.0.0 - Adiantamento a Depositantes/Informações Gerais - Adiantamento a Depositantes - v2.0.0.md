---
id: 17374911
title: Informações Gerais - Adiantamento a Depositantes - v2.0.0
version: 1
modified: 2022-10-27T12:03:24.194Z
url: /spaces/OF/pages/17374911/Informa+es+Gerais+-+Adiantamento+a+Depositantes+-+v2.0.0
---

17**Visão Geral**A API Unarranged-accounts-overdraft viabiliza o compartilhamento de informações das Operações de Crédito do tipo Adiantamento a Depositantes.
## Adiantamento a Depositantes : (GET /unarranged-accounts-overdraft/v2/contracts)
**Visão Geral**Obtém dados referentes à operação de crédito de Adiantamento a DepositantesTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioAdiantamentoDepositante) e [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContracts_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_unarranged_accounts_overdraft_contract_list.csv)
## Adiantamento a Depositantes - Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId})
**Visão Geral**Obtém dados referentes à identificação da operação de crédito de Adiantamento a DepositantesTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioAdiantamentoDepositante), [Custo Efetivo Total (CET)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioCET), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Identificador padronizado da operação de crédito – Ipoc Code](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIPOC), [Indexador (Indexer)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioIndexador), [Sistema de Amortização Constante (SAC)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSAC), [Sistema Francês de Amortização (Price)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioPrice), [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa), [Taxa Efetiva (EffectiveTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaEfetiva) e [Taxa nominal (NominalTax)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTaxaNominal).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractId_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_unarranged_accounts_overdraft_contract.csv)
## Adiantamento a Depositantes - Garantias do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties)
**Visão Geral**Obtém dados referentes às garantias que avalizam a operação de crédito de Adiantamento a Depositantes contratadaTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioAdiantamentoDepositante) e [Garantia (Warranty)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioGarantia).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdWarranties_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_unarranged_accounts_overdraft_warranties.csv)

## Adiantamento a Depositantes - Pagamentos do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/payments)
**Visão Geral**Obtém dados dos pagamentos referentes às operações de crédito de Adiantamento a Depositantes contratadasTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioAdiantamentoDepositante), [Encargo (Charge)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioEncargo), [Saldo Devedor (Outstanding Balance)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioSaldoDevedor) e [Tarifa (Fee)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioTarifa).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdPayments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_unarranged_accounts_overdraft_payments.csv)
## Adiantamento a Depositantes - Parcelas do Contrato : (GET /unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments)
**Visão Geral**Obtém dados referentes às parcelas / prestações da operação de crédito de Adiantamento a Depositantes contratadasTags: [Adiantamento a Depositante (Unarranged Account Overdraft)](https://openbanking-brasil.github.io/areadesenvolvedor/#glossarioAdiantamentoDepositante).**Visão de alto de nível das estruturas de dados****DER - Diagramas de Entidade e Relacionamento**
- DER Conceitual

- DER Lógico
**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/unarrangedAccountsOverdraftGetContractsContractIdScheduledInstalments_v2.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/areadesenvolvedor/dictionary/example/examples_unarranged_accounts_overdraft_scheduled_instalments.csv)