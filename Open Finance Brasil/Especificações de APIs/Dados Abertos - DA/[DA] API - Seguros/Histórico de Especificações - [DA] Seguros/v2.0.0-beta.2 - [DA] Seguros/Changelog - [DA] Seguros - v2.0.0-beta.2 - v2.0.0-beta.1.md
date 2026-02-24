---
id: 372867198
title: Changelog - [DA] Seguros - v2.0.0-beta.2 - v2.0.0-beta.1
version: 3
modified: 2024-04-16T12:58:47.910Z
url: /spaces/OF/pages/372867198/Changelog+-+DA+Seguros+-+v2.0.0-beta.2+-+v2.0.0-beta.1
---

## GET /personals

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/deductible | Removido obrigatóriedade no campo 'amount' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/deductible | Removido obrigatóriedade no campo 'currency' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/differentiatedDeductible | Removido obrigatóriedade no campo 'amount' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/differentiatedDeductible | Removido obrigatóriedade no campo 'currency' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/maxValue | Removido obrigatóriedade no campo 'amount' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/maxValue | Removido obrigatóriedade no campo 'currency' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/minValue | Removido obrigatóriedade no campo 'amount' | Remoção | required | |
| get/responses/200/data/items/society/products/items/coverages/items/attributes/minValue | Removido obrigatóriedade no campo 'currency' | Remoção | required | |
| get/responses/200/data/items/society/products/items/portabilityGraceTime | Removido obrigatóriedade no campo 'amount' | Remoção | required | |
| get/responses/200/data/items/society/products/items/reclaim/gracePeriod | Removido obrigatóriedade no campo 'amount' | Remoção | required | |
| /data[]/society/products[]/pmbacRemuneration/ updateIndexes​ | Alterado - “Exemplo” | Alteração | IPCA | IPC-FGV​ |
| /data[]/society/products[]/coverages[]/ typeAdditionalInfos[]​ | Alterado - “Exemplo” | Alteração | Informações Adicionais | [Informações Adicionais]​ |
| /data[]/society/products[]/coverages[]/attributes/ indemnityPaymentMethods​ | Alterado - “Exemplo” | Alteração | | PAGAMENTO_CAPITAL_SEGURADO_VALOR_MONETARIO​ |
| /data[]/society/products[]/ assistanceTypesAdditionalInfos​ | Alterado - “Exemplo” | Alteração | Informações Adicionais | [Informações Adicionais]​ |
| /data[]/society/products[]/terms​ | Alteração do Enum | Alteração | | Removido - NA |
| /data[]/society/products[]/terms​ | Removido obrigatóriedade no campo | Remoção | required | |
| /data[]/society/products[]/additionalServices​ | Alteração do Enum | Alteração | | Removido - NA |
| /data[]/society/products[]/additionalServices​ | Removido obrigatóriedade no campo | Remoção | required | |
| /data[]/society/products[]/assistenceTypes​ | Alteração do Enum | Alteração | | Removido - NA |
| /data[]/society/products[]/ageAdjustment/criterias​ | Alteração do Enum | Alteração | | Removido - NA |
| /data[]/society/products[]/coverages[]/attributes/indemnityPaymentMethods​ | Alteração do Enum | Alteração | | Removido - NA |
| /data[]/society/products[]/coverages[]/attributes/indemnityPaymentMethods​ | Removido obrigatóriedade no campo | Remoção | required | |
| /data[]/society/products[]/coverages[]/attributes/gracePeriod/unit​ | Alteração do Enum | Alteração | | Removido - NA |
| /data[]/society/products[]/coverages[]/attributes/gracePeriod/unit​ | Removido obrigatóriedade no campo | Remoção | required | |