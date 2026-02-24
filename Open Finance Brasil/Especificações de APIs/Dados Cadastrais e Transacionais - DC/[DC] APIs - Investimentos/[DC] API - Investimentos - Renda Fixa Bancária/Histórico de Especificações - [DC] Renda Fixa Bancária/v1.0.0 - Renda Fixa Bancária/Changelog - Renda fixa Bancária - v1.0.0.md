---
id: 154730665
title: Changelog - Renda fixa Bancária - v1.0.0
version: 2
modified: 2023-08-09T17:10:38.227Z
url: /spaces/OF/pages/154730665/Changelog+-+Renda+fixa+Banc+ria+-+v1.0.0
---

GET /investments
| Campo | O que foi alterado? |
| get/responses/200/links | Adicionado - “Last” |
GET /investments/{investmentId}
| Campo | O que foi alterado? |
GET /investments/{investmentId}/balances
| Campo | O que foi alterado? |
| get/responses/200/data/items/blockedBalance | Descrição |
GET /investments/{investmentId}/transactions
| Campo | O que foi alterado? |
| get/responses/200/data/items/indexerPercentage | "minLength" |
| get/responses/200/data/items/remunerationTransactionRate | "minLength" |
GET /investments/{investmentId}/transactions-current
| Campo | O que foi alterado? |
| get/responses/200/data/items/indexerPercentage | "minLength" |
| get/responses/200/data/items/remunerationTransactionRate | "minLength" |