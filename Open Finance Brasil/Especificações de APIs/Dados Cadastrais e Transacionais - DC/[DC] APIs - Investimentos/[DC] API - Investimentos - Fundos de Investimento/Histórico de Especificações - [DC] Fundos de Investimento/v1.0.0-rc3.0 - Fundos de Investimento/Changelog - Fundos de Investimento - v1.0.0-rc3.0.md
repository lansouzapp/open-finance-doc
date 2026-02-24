---
id: 144933516
title: Changelog - Fundos de Investimento - v1.0.0-rc3.0
version: 3
modified: 2023-07-19T17:14:18.009Z
url: /spaces/OF/pages/144933516/Changelog+-+Fundos+de+Investimento+-+v1.0.0-rc3.0
---

GET /investments
| Campo | O que foi alterado? |
| get/responses/200/data/items/investmentId | Alterado - “description” |
GET /investments/{investmentId}
| Campo | O que foi alterado? |
| get/parameters/investmentId | Alterado - “description” |
GET /investments/{investmentId}/balances
| Campo | O que foi alterado? |
| get | Alterado - “description” |
| get/responses/200/data/blockedAmount | Alterado - “description” |
| get/responses/200/data/incomeTaxProvision | Alterado - “description” |
| get/parameters/investmentId | Alterado - “description” |
GET /investments/{investmentId}/transactions
| Campo | O que foi alterado? |
| get/responses/200/data/items/transactionValue | Alterado - “description” |
| get/parameters/investmentId | Alterado - “description” |
GET /investments/{investmentId}/transactions-current
| Campo | O que foi alterado? |
| get/responses/200/data/items/transactionValue | Alterado - “description” |
| get/parameters/investmentId | Alterado - “description” |