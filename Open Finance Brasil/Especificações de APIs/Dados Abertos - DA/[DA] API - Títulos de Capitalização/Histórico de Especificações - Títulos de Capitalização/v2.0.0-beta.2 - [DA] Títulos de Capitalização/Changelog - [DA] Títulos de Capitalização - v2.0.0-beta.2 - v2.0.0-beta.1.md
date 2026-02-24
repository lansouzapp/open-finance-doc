---
id: 372834437
title: Changelog - [DA] Títulos de Capitalização - v2.0.0-beta.2 - v2.0.0-beta.1
version: 3
modified: 2024-04-16T12:43:52.366Z
url: /spaces/OF/pages/372834437/Changelog+-+DA+T+tulos+de+Capitaliza+o+-+v2.0.0-beta.2+-+v2.0.0-beta.1
---

## GET /bonds

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/items/society/products/items/additionalInfo​ | Alterado nome do campo | Alteração | additionalInfo​ | additionalDetails​ |
| get/responses/200/data/items/participant/brand | Adicionado - "pattern" | Adição | | ^(?!\s)[\w\W\s]*[^\s]$ |
| get/responses/200/data/items/participant/name | Adicionado - "pattern" | Adição | | ^(?!\s)[\w\W\s]*[^\s]$ |
| get/responses/200/data/items/society | Alterado - "description" | Alteração | Dados sobre a seguradora participante do OPIN. | Objeto que representa a empresa regulada pela SUSEP que oferta produtos definidos em OPIN. |
| get/responses/200/data/items/society/products/items | Removido obrigatóriedade no campo 'additionalDetails' | Remoção | required | |
| get/responses/200/data/items/society/products/items/minimumRequirementDetails | Adicionado - "pattern" | Adição | | ^(https:\/\/)?(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&\/\/=]*)$ |
| get/responses/200/data/items/society/products/items/termsAndConditions/termsRegulations | Adicionado - "pattern" | Adição | | ^(https:\/\/)?(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&\/\/=]*)$ |