---
id: 189694195
title: Changelog - Consentimento - v2.2.0-beta.2
version: 2
modified: 2023-10-06T18:43:39.733Z
url: /spaces/OF/pages/189694195/Changelog+-+Consentimento+-+v2.2.0-beta.2
---

Alteração na parte de orientações dentro do swagger
| Campo | O que foi feito? |
| --- | --- |
| Description | Alterado |
POST /consents
| Campo | O que foi feito? |
| --- | --- |
| post/requestBody/data/expirationDateTime | description |
| post/responses/201/data/expirationDateTime | description |
GET /consents/{consentId}
| Campo | O que foi feito? |
| --- | --- |
DELETE /consents/{consentId}
| Campo | O que foi feito? |
| --- | --- |
GET /consents/{consentId}/extends
| Campo | O que foi feito? |
| --- | --- |
| get/security/0 | Removido - "OAuth2ClientCredentials" |
| get/security/0 | Adicionado - "OAuth2Security" |
POST /consents/{consentId}/extends
| Campo | O que foi feito? |
| --- | --- |
| post/responses/422 | Adicionado - "application/json; charset=utf-8" |
| post/responses/422 | Removido - "application/jwt" |
| post/responses/422 | description |
| post/responses/422/errors/items/code/enum | Adicionado - "DATA_EXPIRACAO_INVALIDA" |
| post/responses/422/errors/items/code/enum | description |
| post/responses/422/errors/items/title | description |
| post/responses/422/errors/items/detail | description |
| post/security/0 | Adicionado - "OAuth2AuthorizationCode" |
| post/security/0 | Removido - "OAuth2Security" |