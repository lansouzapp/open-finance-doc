---
id: 124289431
title: Changelog - Renda Variável - v1.0.0-rc2.0
version: 2
modified: 2023-06-14T21:36:45.474Z
url: /spaces/OF/pages/124289431/Changelog+-+Renda+Vari+vel+-+v1.0.0-rc2.0
---

GET /investments
| Campo | O que foi alterado? |
| get/parameters/page-size | description |
| get/parameters/page-size | minimum |
GET /investments/{investmentId}
| Campo | O que foi alterado? |
| | |
GET /investments/{investmentId}/balances
| Campo | O que foi alterado? |
| get/responses/200/data/items/quantity | maxLength |
| get/responses/200/data/items/quantity | pattern |
GET /investments/{investmentId}/transactions
| Campo | O que foi alterado? |
| get/responses/200/data/items/properties | nome do campo - "transactionTypeAdditionalInfo" |
| get/responses/200/data/items/transactionType | description |
| get/parameters/page-size | description |
| get/parameters/page-size | minimum |
| get/responses/200/data/items/transactionType | description |
| get/responses/200/data/items/transactionType/enum | Removido - "INPLIT" |
| get/responses/200/data/items/transactionType/enum | Removido - "SPLIT_TRANSFERENCIA_CUSTODIA" |
| get/responses/200/data/items/transactionType/enum | Adicionado - "TRANSFERENCIA_CUSTODIA" |
GET /investments/{investmentId}/transactions-current
| Campo | O que foi alterado? |
| get/responses/200/data/items/properties | nome do campo - "transactionTypeAdditionalInfo" |
| get/responses/200/data/items/transactionType | description |
| get/parameters/page-size | description |
| get/parameters/page-size | minimum |
| get/responses/200/data/items/transactionType | description |
| get/responses/200/data/items/transactionType/enum | Removido - "INPLIT" |
| get/responses/200/data/items/transactionType/enum | Removido - "SPLIT_TRANSFERENCIA_CUSTODIA" |
| get/responses/200/data/items/transactionType/enum | Adicionado - "TRANSFERENCIA_CUSTODIA" |
GET /investments/{investmentId}/broker-notes/{brokerNoteId})
| Campo | O que foi alterado? |
| get | description |