---
id: 101482572
title: Changelog - Consentimento - v2.1.0-rc1.0
version: 2
modified: 2023-05-09T20:40:16.340Z
url: /spaces/OF/pages/101482572/Changelog+-+Consentimento+-+v2.1.0-rc1.0
---

POST /consents
| Campo | O que foi feito? |
| post/requestBody/data/permissions/items/enum | Adicionado - "BANK_FIXED_INCOMES_READ" |
| post/requestBody/data/permissions/items/enum | Adicionado - "CREDIT_FIXED_INCOMES_READ" |
| post/requestBody/data/permissions/items/enum | Adicionado - "FUNDS_READ" |
| post/requestBody/data/permissions/items/enum | Adicionado - "TREASURE_TITLES_READ" |
| post/requestBody/data/permissions/items/enum | Adicionado - "VARIABLE_INCOMES_READ" |
| post/responses/201/data/permissions/items/enum | Adicionado - "BANK_FIXED_INCOMES_READ" |
| post/responses/201/data/permissions/items/enum | Adicionado - "CREDIT_FIXED_INCOMES_READ" |
| post/responses/201/data/permissions/items/enum | Adicionado - "FUNDS_READ" |
| post/responses/201/data/permissions/items/enum | Adicionado - "TREASURE_TITLES_READ" |
| post/responses/201/data/permissions/items/enum | Adicionado - "VARIABLE_INCOMES_READ" |
| post/requestBody/data/permissions/items/enum | Adicionado - "VARIABLE_INCOMES_READ" |
GET /consents/{consentId}
| Campo | O que foi feito? |
| get/responses/200/data/permissions/items/enum | Adicionado - "BANK_FIXED_INCOMES_READ" |
| get/responses/200/data/permissions/items/enum | Adicionado - "CREDIT_FIXED_INCOMES_READ" |
| get/responses/200/data/permissions/items/enum | Adicionado - "FUNDS_READ" |
| get/responses/200/data/permissions/items/enum | Adicionado - "TREASURE_TITLES_READ" |
| get/responses/200/data/permissions/items/enum | Adicionado - "VARIABLE_INCOMES_READ" |
DELETE /consents/{consentId}
| Campo | O que foi feito? |