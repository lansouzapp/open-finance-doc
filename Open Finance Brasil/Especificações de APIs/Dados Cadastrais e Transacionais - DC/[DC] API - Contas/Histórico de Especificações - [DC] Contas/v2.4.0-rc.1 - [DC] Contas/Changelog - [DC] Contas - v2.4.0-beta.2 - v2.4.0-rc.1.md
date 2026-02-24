---
id: 480575736
title: Changelog - [DC] Contas - v2.4.0-beta.2 - v2.4.0-rc.1
version: 2
modified: 2024-07-10T18:19:04.227Z
url: /spaces/OF/pages/480575736/Changelog+-+DC+Contas+-+v2.4.0-beta.2+-+v2.4.0-rc.1
---

none 
## GET /accounts

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| | | | | |

## GET /accounts/{accountId}

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| | | | | |

## GET /accounts/{accountId}/balances

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| | | | | |

## GET /accounts/{accountId}/transactions

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/items/partiePersonType | Alterado - "description" | Alteração | Identificação do Tipo de Pessoa da pessoa envolvida na transação. Pessoa Natural - Informar CPF no campo “payerCnpjCpf”. Pessoa Jurídica - Informar CNPJ no campo “payerCnpjCpf”. | Identificação do Tipo de Pessoa da pessoa envolvida na transação. Pessoa Natural - Informar CPF no campo “partieCnpjCpf”. Pessoa Jurídica - Informar CNPJ no campo “partieCnpjCpf”. |

## GET /accounts/{accountId}/transactions-curent

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/items/partiePersonType | Alterado - "description" | Alteração | Identificação do Tipo de Pessoa da pessoa envolvida na transação. Pessoa Natural - Informar CPF no campo “payerCnpjCpf”. Pessoa Jurídica - Informar CNPJ no campo “payerCnpjCpf”. | Identificação do Tipo de Pessoa da pessoa envolvida na transação. Pessoa Natural - Informar CPF no campo “partieCnpjCpf”. Pessoa Jurídica - Informar CNPJ no campo “partieCnpjCpf”. |

## GET /accounts/{accountId}/overdraft-limits

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| | | | | |