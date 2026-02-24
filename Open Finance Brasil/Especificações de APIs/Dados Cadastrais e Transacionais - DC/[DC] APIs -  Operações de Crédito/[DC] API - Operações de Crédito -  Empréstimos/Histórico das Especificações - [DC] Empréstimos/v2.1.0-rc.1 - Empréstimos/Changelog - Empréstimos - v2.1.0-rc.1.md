---
id: 157417929
title: Changelog - Empréstimos - v2.1.0-rc.1
version: 2
modified: 2023-08-14T20:23:55.816Z
url: /spaces/OF/pages/157417929/Changelog+-+Empr+stimos+-+v2.1.0-rc.1
---

GET /contracts
| Campo | O que foi alterado? |
| | |
GET /contracts/{contractId}
| Campo | O que foi alterado? |
| get/responses/200/data/contractAmount | Mandatoriedade - “Obrigatório“ |
| get/responses/200/data/contractAmount | Alterado - “description“ |
| get/responses/200/data/CET | Mandatoriedade - “Obrigatório“ |
| get/responses/200/data/CET | Alterado - “description“ |
GET /contracts/{contractId}/warranties
| Campo | O que foi alterado? |
| get/responses/200/data/items/currency | Mandatoriedade - “Obrigatório“ |
| get/responses/200/data/items/warrantAmount | Mandatoriedade - “Obrigatório“ |
GET /contracts/{contractId}/scheduled-instalments
| Campo | O que foi alterado? |
| | |
GET /contracts/{contractId}/payments
| Campo | O que foi alterado? |
| get/responses/200/data/releases/items/paymentId | Mandatoriedade - “Obrigatório“ |
| get/responses/200/data/releases/items/paymentId | Alterado - “description“ |