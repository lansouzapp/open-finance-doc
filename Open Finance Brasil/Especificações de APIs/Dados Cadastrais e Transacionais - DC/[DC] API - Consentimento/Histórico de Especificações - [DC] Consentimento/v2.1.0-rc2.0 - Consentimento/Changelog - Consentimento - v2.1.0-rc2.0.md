---
id: 128778331
title: Changelog - Consentimento - v2.1.0-rc2.0
version: 2
modified: 2023-06-21T20:16:25.705Z
url: /spaces/OF/pages/128778331/Changelog+-+Consentimento+-+v2.1.0-rc2.0
---

POST /consents
| Campo | O que foi feito? |
| --- | --- |
| post/requestBody/data/permissions | Removido - "maxItems" |
| post/requestBody/data/permissions/items | Alteração na descrição |
| post/responses/201/data/permissions | Alteração na descrição |
| post/responses/201/data/permissions | Removido - "maxItems" |
GET /consents/{consentId}
| Campo | O que foi feito? |
| get/responses/200/data/permissions | Alteração na descrição |
| get/responses/200/data/permissions | Removido - "maxItems" |
DELETE /consents/{consentId}
| Campo | O que foi feito? |