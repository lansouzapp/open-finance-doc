---
id: 193954306
title: Changelog - Pagamentos - v4.0.0-beta.1
version: 2
modified: 2023-10-13T23:24:56.813Z
url: /spaces/OF/pages/193954306/Changelog+-+Pagamentos+-+v4.0.0-beta.1
---

Alteração na parte de orientações dentro do swagger
| Campo | O que foi feito? |
| Description | Alterado |
| Description | Alterado |
| Description | Alterado |
| Description | Alterado |
| Description | Alterado |
| Description | Alterado |
POST /consents
| Campo | O que foi feito? |
| get/requestBody/data/payment/schedule/oneOf | Adicionado - “daily“ |
| get/requestBody/data/payment/schedule/oneOf | Adicionado - “weekly“ |
| get/requestBody/data/payment/schedule/oneOf | Adicionado - “monthly“ |
| get/requestBody/data/payment/schedule/oneOf | Adicionado - “custom“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “daily“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “weekly“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “monthly“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “custom“ |
| post/requestBody/data/payment/schedule | description |
| post/requestBody/data/payment/schedule/oneOf/4/custom/properties | Mandatoriedade |
| post/requestBody/data/payment/schedule/oneOf/4/custom/properties | Adicionado - "additionalInformation" |
| post/responses/201/data/payment/schedule/oneOf/4/custom/properties | Mandatoriedade |
| post/responses/201/data/payment/schedule/oneOf/4/custom/properties | Adicionado - "additionalInformation" |
| post/responses | Removido - "429" |
GET /consents/{consentId}
| Campo | O que foi feito? |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “daily“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “weekly“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “monthly“ |
| get/responses/200/data/payment/schedule/oneOf | Adicionado - “custom“ |
| get/responses/200/data/payment/schedule/oneOf/4/custom/properties | Mandatoriedade |
| get/responses/200/data/payment/schedule/oneOf/4/custom/properties | Adicionado - "additionalInformation" |
| get/responses | Removido - "429" |
POST /pix/payments
| Campo | O que foi feito? |
| get/responses/201/data | Alterado - “type“ |
| request/data | Alterado para tipo array |
| post/responses/201/data/items/status | description |
| post/responses/201/data/items/status/enum | Removido - "PATC" |
| post/responses/422/errors/items/code | description |
| post/responses/422/errors/items/code/enum | Adicionado - "CONSENTIMENTO_PENDENTE_AUTORIZACAO" |
| post/responses/422/errors/items/detail | description |
| post/responses/422/errors/items/title | description |
| post/responses | Removido - "429" |
GET /pix/payments/{paymentId}
| Campo | O que foi feito? |
| get/responses/200/data | Alterado - “type“ |
| get/responses/200/data/items/rejectionReason/code | description |
| get/responses/200/data/items/rejectionReason/code/enum | Adicionado - "FALHA_AGENDAMENTO_PAGAMENTOS" |
| get/responses/200/data/items/status | description |
| get/responses/200/data/items/status/enum | Removido - "PATC" |
| get/responses | Removido - "429" |
PATCH pix/payments/{paymentId}/
| Campo | O que foi feito? |
| patch/responses/422 | description |
| patch | description |
| patch/responses/200/data/status | description |
| patch/responses/200/data/status/enum | Removido - "PATC" |
| patch/responses | Removido - "429" |
PATCH pix/payments/consents/{consentId}
| Campo | O que foi feito? |
| - | Endpoint criado |