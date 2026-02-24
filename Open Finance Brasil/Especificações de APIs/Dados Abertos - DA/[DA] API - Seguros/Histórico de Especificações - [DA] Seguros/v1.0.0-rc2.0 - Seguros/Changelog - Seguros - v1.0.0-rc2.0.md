---
id: 94961726
title: Changelog - Seguros - v1.0.0-rc2.0
version: 4
modified: 2023-05-16T16:20:38.711Z
url: /spaces/OF/pages/94961726/Changelog+-+Seguros+-+v1.0.0-rc2.0
---

GET /personals
| Campo | O que foi alterado? |
| get/responses/200/data/items/participant/urlComplementaryList | Adicionado - "description" |
| get/responses/200/data/items/pmbacRemuneration/interestRate | example |
| get/responses/200/data/items/pmbacRemuneration/interestRate | Adicionado - "maxLength" |
| get/responses/200/data/items/pmbacRemuneration/interestRate | Adicionado - "minLength" |
| get/responses/200/data/items/pmbacRemuneration/interestRate | pattern |
| get/responses/200/data/items/reclaim/table/items/percentage | example |
| get/responses/200/data/items/reclaim/table/items/percentage | maxLength |
| get/responses/200/data/items/reclaim/table/items/percentage | Adicionado - "minLength" |
| get/responses/200/data/items/reclaim/table/items/percentage | pattern |
| get/responses/200/data/items/termsAndConditions/items/susepProcessNumber | pattern |
| get/responses/200/data/items/termsAndConditions/items/susepProcessNumber | Adicionado - "minLength" |
| get/responses/400//meta | description |
| get/responses/404//meta | description |
| get/responses/405//meta | description |
| get/responses/429//meta | description |
| get/responses/500//meta | description |
| 200/data/minimumRequirements | Mandatoriedade |
| 200/data/coverages/attributes | Mandatoriedade |
| 200/data/coverages/attributes/gracePeriod/amount | Mandatoriedade |
| 200/data/coverages/attributes/gracePeriod/unit | Mandatoriedade |
| 200/data/assistanceTypes | Mandatoriedade |
| 200/data/benefitRecalculation/updateIndexes | Mandatoriedade |
| 200/data/benefitRecalculation | Mandatoriedade |
| 200/data/modality | Mandatoriedade |
| 200/data/coverages/attributes/maximumQtyIndemnifiableInstallments | Mandatoriedade |
| 200/data/coverages/attributes/deductibleDays | Mandatoriedade |
| 200/data/coverages/attributes/deductible | Mandatoriedade |
| 200/data/coverages/attributes/excludedRisks | Mandatoriedade |
| 200/data/coverages/attributes/allowApartPurchase | Mandatoriedade |
| 200/data/minimumRequirement/contractingMinRequirement | Mandatoriedade |
| 200/data/coverages/attributes/indemnifiablePeriods | Mandatoriedade |
| get/responses/200/data/items/coverages/items/attributes/indemnifiablePeriods | Adicionado - "description" |
| get/responses/200/data/items/coverages/items/attributes/indemnifiablePeriods/items | Removido - "description" |
| get/responses/200/data/items/coverages/items/attributes/indemnifiablePeriods/items | Removido - "enum" |
| get/responses/200/data/items/coverages/items/attributes/indemnifiablePeriods/items | example |
| get/responses/200/data/items/coverages/items/attributes/indemnifiablePeriods/items | maxLength |
| get/responses/200/data/items/coverages/items/type/enum | Adicionado - "DOENCA_GRAVE" |
| get/responses/200/data/items/coverages/items/type/enum | Adicionado - "TRANSLADO_MEDICO" |
| get/responses/200/data/items/premiumPayment/paymentMethods/items/enum | Removido - "OUTROS" |
| get/responses/200/data/items/premiumPayment/paymentMethods/items/enum | Corrigido - "PONTOS_PROGRAMA_BENEFICIO" |
| get/responses/200/data/items/premiumPayment/paymentMethods/items/enum | Adicionado - "REGRA_PARCEIRO" |
| get/responses/200/data/items/minimumRequirement/contractType/enum | Removido - "AMBAS" |
| get/responses/200/data/items/coverages/items/attributes/indemnifiablePeriods | Tipo do componente |
| get/responses/200/data/items/society/properties | Adicionado - "brand" |
| 200/data/coverages/attributes/indemnityPaymentMethods | Mandatoriedade |
| 200/data/coverages/attributes/indemnityPaymentFrequencies | Mandatoriedade |
| 200/data/coverages/attributes/maximumQtyIndemnifiableInstallments | Mandatoriedade |
| 200/data/coverages/attributes/deductibleDays | Mandatoriedade |
| 200/data/globalCapital | Mandatoriedade |
| 200/data/financialRegimes | Mandatoriedade |
| 200/data/reclaim/table/initialMonthRange | Mandatoriedade |
| 200/data/reclaim/table/finalMonthRange | Mandatoriedade |
| 200/data/reclaim/table/percentage | Mandatoriedade |
| 200/data/reclaim/gracePeriod | Mandatoriedade |
| 200/data/allowPortability | Mandatoriedade |
| 200/data/minimumRequirement/contractingMinRequirement | Mandatoriedade |
| 200/data/premiumPayment | Mandatoriedade |
| 200/data/minimumRequirement | Mandatoriedade |
| get/responses/200/data/items/reclaim/gracePeriod/properties | Adicionado - "details" |
| get/responses/200/data/items/coverages/items/attributes/gracePeriod/properties | Adicionado - "details" |
| get/responses/200/data/items/coverages/items/attributes/differentiatedGracePeriod | type |
| get/responses/200/data/items/coverages/items/attributes/differentiatedGracePeriod | description |
| get/responses/200/data/items/coverages/items/attributes/differentiatedGracePeriod | maxLength |
| get/responses/200/data/items/coverages/items/attributes/differentiatedGracePeriod | Removido - unit |
| get/responses/200/data/items/coverages/items/attributes/differentiatedGracePeriod | Removido - amount |