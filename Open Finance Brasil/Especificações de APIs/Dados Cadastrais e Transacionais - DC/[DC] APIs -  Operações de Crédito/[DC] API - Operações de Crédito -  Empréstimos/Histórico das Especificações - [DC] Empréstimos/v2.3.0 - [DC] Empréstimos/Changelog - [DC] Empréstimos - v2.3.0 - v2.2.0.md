---
id: 602702049
title: Changelog - [DC] Empréstimos - v2.3.0 - v2.2.0
version: 2
modified: 2024-09-26T17:56:24.558Z
url: /spaces/OF/pages/602702049/Changelog+-+DC+Empr+stimos+-+v2.3.0+-+v2.2.0
---

none 

## GET /contracts/{contractId}

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/CET | Alterado - "pattern" | Alteração | ^\d{1,2}\.\d{6}$ | ^\d{1,6}\.\d{6}$ |
| get/responses/200/data/CET | Alterado - "maxLength" | Alteração | 9 | 13 |