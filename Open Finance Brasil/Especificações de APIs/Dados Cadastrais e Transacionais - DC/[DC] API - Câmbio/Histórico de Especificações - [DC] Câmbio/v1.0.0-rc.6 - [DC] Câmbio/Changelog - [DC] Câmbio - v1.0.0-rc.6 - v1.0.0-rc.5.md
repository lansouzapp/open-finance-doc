---
id: 320143724
title: Changelog - [DC] Câmbio - v1.0.0-rc.6 - v1.0.0-rc.5
version: 3
modified: 2024-03-05T14:19:13.312Z
url: /spaces/OF/pages/320143724/Changelog+-+DC+C+mbio+-+v1.0.0-rc.6+-+v1.0.0-rc.5
---

## GET /operations/{operationId}

### Informações do endpoint

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get | Alterado - "description" | Alteração | Obtém os dados da operação de Câmbio identificada por operationId. | Obtém os dados da operação de Câmbio identificada por operationId. As alterações efetuadas na operação original devem ser represen... |

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/deliveryForeignCurrency | Alterado - "description" | Alteração | Forma de entrega da moeda estrangeira. | Forma de entrega da moeda estrangeira. ``` |--------|-------------------------------------------------------------| | Código | EN... |
| get/responses/200/data/deliveryForeignCurrency/enum | Adicionado - "CONTA_DEPOSITO_EXPORTADOR_MANTIDA_NO_EXTERIOR" | Adição | | enum |
| get/responses/200/data/deliveryForeignCurrency/enum | Adicionado - "CONVENIO_PAGAMENTOS_E_CREDITOS_RECIPROCOS" | Adição | | enum |
| get/responses/200/data/deliveryForeignCurrency/enum | Adicionado - "OUTRO_NAO_MAPEADO_OFB" | Adição | | enum |

## GET /operations/{operationId}/events

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/items/deliveryForeignCurrency | Alterado - "description" | Alteração | Forma de entrega da moeda estrangeira. | Forma de entrega da moeda estrangeira. ``` |--------|-------------------------------------------------------------| | Código | EN... |
| get/responses/200/data/items/deliveryForeignCurrency/enum | Adicionado - "CONTA_DEPOSITO_EXPORTADOR_MANTIDA_NO_EXTERIOR" | Adição | | enum |
| get/responses/200/data/items/deliveryForeignCurrency/enum | Adicionado - "CONVENIO_PAGAMENTOS_E_CREDITOS_RECIPROCOS" | Adição | | enum |
| get/responses/200/data/items/deliveryForeignCurrency/enum | Adicionado - "OUTRO_NAO_MAPEADO_OFB" | Adição | | enum |