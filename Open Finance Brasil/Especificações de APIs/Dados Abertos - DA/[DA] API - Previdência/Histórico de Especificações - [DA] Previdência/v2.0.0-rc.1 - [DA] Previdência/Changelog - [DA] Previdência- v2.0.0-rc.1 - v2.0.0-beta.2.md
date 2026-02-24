---
id: 387514732
title: Changelog - [DA] Previdência- v2.0.0-rc.1 - v2.0.0-beta.2
version: 2
modified: 2024-04-30T20:20:43.452Z
url: /spaces/OF/pages/387514732/Changelog+-+DA+Previd+ncia-+v2.0.0-rc.1+-+v2.0.0-beta.2
---

## GET /risk-coverages

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/properties | Adicionado obrigatóriedade no campo 'excludedRisks' | Adição | | required |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/properties | Removido obrigatóriedade no campo 'excludedRisksURL' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/x-regulatory-required | Removido - "excludedRisksURL" | Remoção | x-regulatory-required | |