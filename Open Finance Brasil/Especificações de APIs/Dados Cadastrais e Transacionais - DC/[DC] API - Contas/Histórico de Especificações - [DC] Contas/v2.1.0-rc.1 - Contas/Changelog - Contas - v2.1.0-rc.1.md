---
id: 157450418
title: Changelog - Contas - v2.1.0-rc.1
version: 2
modified: 2023-08-14T20:16:55.036Z
url: /spaces/OF/pages/157450418/Changelog+-+Contas+-+v2.1.0-rc.1
---

Alteração na parte de orientações dentro do swagger
| Campo | O que foi alterado? |
| description | Alterado - “description“ |
GET /accounts
| Campo | O que foi alterado? |
| | |
GET /accounts/{accountId}
| Campo | O que foi alterado? |
| | |
GET /accounts/{accountId}/balances
| Campo | O que foi alterado? |
| get/responses/200/data/properties | Adicionado - “updateDateTime“ |
GET /accounts/{accountId}/transactions
| Campo | O que foi alterado? |
| get/responses/200/data/items/completedAuthorisedPaymentType | Alterado - “description“ |
| get/responses/200/data/items/completedAuthorisedPaymentType/enum | Adicionado - "TRANSACAO_PROCESSANDO" |
| get/responses/200/data/partieCnpjCpf | Alterado - “description“ |
| get/responses/200/data/properties | Removido - “transactionDate“ |
| get/responses/200/data/properties | Adicionado - “transactionDateTime“ |
| get/responses/200/data/items/transactionId | Alterado - “description“ |
| get/responses/200/data/items/transactionId | Alterado - “Mandatoriedade“ |
| get/responses/200/data/transactionName | Alterado - “description“ |
| get/responses/200/data/transactionName | Alterado - “maxLength“ |
GET /accounts/{accountId}/transactions-curent
| Campo | O que foi alterado? |
| get/responses/200/data/items/completedAuthorisedPaymentType | Alterado - “description“ |
| get/responses/200/data/items/completedAuthorisedPaymentType/enum | Adicionado - "TRANSACAO_PROCESSANDO" |
| get/responses/200/data/partieCnpjCpf | Alterado - “description“ |
| get/responses/200/data/properties | Removido - “transactionDate“ |
| get/responses/200/data/properties | Adicionado - “transactionDateTime“ |
| get/responses/200/data/items/transactionId | Alterado - “description“ |
| get/responses/200/data/items/transactionId | Alterado - “Mandatoriedade“ |
| get/responses/200/data/transactionName | Alterado - “description“ |
| get/responses/200/data/transactionName | Alterado - “maxLength“ |
GET /accounts/{accountId}/overdraft-limits
| Campo | O que foi alterado? |
| | |