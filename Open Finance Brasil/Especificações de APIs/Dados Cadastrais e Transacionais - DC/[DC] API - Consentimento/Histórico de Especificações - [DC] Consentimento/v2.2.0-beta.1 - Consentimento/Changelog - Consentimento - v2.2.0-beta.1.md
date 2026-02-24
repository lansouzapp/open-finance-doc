---
id: 175833275
title: Changelog - Consentimento - v2.2.0-beta.1
version: 3
modified: 2023-09-18T23:12:32.317Z
url: /spaces/OF/pages/175833275/Changelog+-+Consentimento+-+v2.2.0-beta.1
---

POST /consents
| Campo | O que foi feito? |
| --- | --- |
| post/requestBody/data/expirationDateTime | description |
| post/responses/201/data/expirationDateTime | description |
GET /consents/{consentId}
| Campo | O que foi feito? |
| --- | --- |
| get/responses/200/data/expirationDateTime | description |
DELETE /consents/{consentId}
| Campo | O que foi feito? |
| --- | --- |
| | |
GET /consents/{consentId}/extends
| Campo | O que foi feito? |
| --- | --- |
| | criação do endpoint |
POST /consents/{consentId}/extends
| Campo | O que foi feito? |
| --- | --- |
| | criação do endpoint |
| post/responses/422/errors/items/code | description |
| post/responses/422/errors/items/code | example |
| post/responses/422/errors/items/code/enum | Adicionado - "DEPENDE_MULTIPLA_ALCADA" |
| post/responses/422/errors/items/code/enum | Removido - "DEPENDE_MULTIPLA_ALCADA_PF" |
| post/responses/422/errors/items/code/enum | Removido - "DEPENDE_MULTIPLA_ALCADA_PJ" |