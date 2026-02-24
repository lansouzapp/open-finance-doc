---
id: 640287298
title: Changelog - [DC] Consentimento - v3.1.0 - v3.0.1
version: 2
modified: 2024-10-18T19:39:19.946Z
url: /spaces/OF/pages/640287298/Changelog+-+DC+Consentimento+-+v3.1.0+-+v3.0.1
---

16falsenonelisttrue 
## POST /consents

### Request

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| post/requestBody/data/expirationDateTime | Alterado - "description" | Alteração | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... |

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| post/responses/201/data/expirationDateTime | Alterado - "description" | Alteração | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... |
| post/responses/422/errors/items/code | Alterado - "description" | Alteração | SEM_PERMISSOES_FUNCIONAIS_RESTANTES - INFORMACOES_PJ_NAO_INFORMADAS - PERMISSOES_PJ_INCORRETAS - PERMISSAO_PF_PJ_EM_CONJUNTO - C... | SEM_PERMISSOES_FUNCIONAIS_RESTANTES - INFORMACOES_PJ_NAO_INFORMADAS - PERMISSOES_PJ_INCORRETAS - PERMISSAO_PF_PJ_EM_CONJUNTO - C... |
| post/responses/422/errors/items/code/enum | Adicionado - "DATA_EXPIRACAO_INVALIDA" | Adição | | enum |
| post/responses/422/errors/items/code/enum | Adicionado - "ERRO_NAO_MAPEADO" | Adição | | enum |
| post/responses/422/errors/items/detail | Alterado - "description" | Alteração | Descrição legível por humanos deste erro específico. Para o erro de data de expiração maior que um ano, diferente de prazo indeter... | Descrição legível por humanos deste erro específico. |
| post/responses/422/errors/items/title | Alterado - "description" | Alteração | Título legível por humanos deste erro específico. Para o erro de data de expiração maior que um ano, diferente de prazo indetermin... | Título legível por humanos deste erro específico. |

## POST /consents/{consentId}/extends

### Request

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| post/requestBody/data/properties | Removido obrigatóriedade no campo 'permissions' | Remoção | required | |
| post/requestBody/data/expirationDateTime | Alterado - "description" | Alteração | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... |

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| post/responses/201/data/properties | Removido obrigatóriedade no campo 'permissions' | Remoção | required | |
| post/responses/201/data/expirationDateTime | Alterado - "description" | Alteração | Data e hora de expiração da permissão. Deve ser preenchido caso o consentimento tenha data limite de validade. Uma string com data... | Data e hora de expiração da permissão. Reflete a data limite de validade do consentimento. Uma string com data e hora conforme esp... |
| post/responses/422/errors/items/code | Alterado - "description" | Alteração | Códigos de erros previstos na durante o processo de extensão do consentimento: - DEPENDE_MULTIPLA_ALCADA: Necessário aprovação de... | Códigos de erros previstos na durante o processo de extensão do consentimento: - DEPENDE_MULTIPLA_ALCADA: Necessário aprovação de... |
| post/responses/422/errors/items/code/enum | Adicionado - "ERRO_NAO_MAPEADO" | Adição | | enum |
| post/responses/422/errors/items/detail | Alterado - "description" | Alteração | Título específico do erro reportado, de acordo com o código enviado: - DEPENDE_MULTIPLA_ALCADA: O consentimento informado não pode... | Título específico do erro reportado, de acordo com o código enviado: - DEPENDE_MULTIPLA_ALCADA: O consentimento informado não pode... |
| post/responses/422/errors/items/title | Alterado - "description" | Alteração | Título específico do erro reportado, de acordo com o código enviado: - DEPENDE_MULTIPLA_ALCADA: Necessário aprovação de múltipla a... | Título específico do erro reportado, de acordo com o código enviado: - DEPENDE_MULTIPLA_ALCADA: Necessário aprovação de múltipla a... |