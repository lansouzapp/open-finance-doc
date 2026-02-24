---
id: 154763815
title: Changelog - Títulos do Tesouro Direto - v1.0.0
version: 2
modified: 2023-08-09T17:29:58.056Z
url: /spaces/OF/pages/154763815/Changelog+-+T+tulos+do+Tesouro+Direto+-+v1.0.0
---

GET /investments
| Campo | O que foi alterado? |
| get/responses/200/links/properties | Adicionado - "last" |
GET /investments/{investmentId}
| Campo | O que foi alterado? |
| get/responses/200/data/items/remuneration/postFixedIndexerPercentage | Adicionado - "minLength" |
| get/responses/200/data/items/remuneration/preFixedRate | Adicionado - "minLength" |
GET /investments/{investmentId}/balances
| Campo | O que foi alterado? |
| get/responses/200/data/items/blockedBalance | Descrição |
GET /investments/{investmentId}/transactions
| Campo | O que foi alterado? |
| get/responses/200/data/items/remunerationTransactionRate | Adicionado - "minLength" |
GET /investments/{investmentId}/transactions-current
| Campo | O que foi alterado? |
| get/responses/200/data/items/remunerationTransactionRate | Adicionado - "minLength" |