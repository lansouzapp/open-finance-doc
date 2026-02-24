---
id: 136937779
title: Changelog - Pagamentos - v3.0.0-beta.1
version: 3
modified: 2023-07-05T17:44:04.697Z
url: /spaces/OF/pages/136937779/Changelog+-+Pagamentos+-+v3.0.0-beta.1
---

Alteração na parte de orientações dentro do swagger
| Campo | O que foi alterado? |
| Orientações | Alterado texto relativo ao campo PAGTO |
| description | Alterado - "description" |
POST /consents
| Campo | O que foi feito? |
| post/parameters/x-fapi-interaction-id | Mandatoriedade - “obrigatório“ |
| post/requestBody/data/creditor/name | Alterado - "pattern" |
| post/requestBody/data/debtorAccount/accountType | Alterado - "description" |
| post/requestBody/data/payment/details/creditorAccount/accountType | Alterado - "description" |
| post/responses/201/data/creditor/name | Alterado - "pattern" |
| post/responses/201/data/debtorAccount | Alterado - "description" |
| post/responses/201/data/debtorAccount/accountType | Alterado - "description" |
| post/responses/201/data/payment/details/creditorAccount/accountType | Alterado - "description" |
| post/responses/400 | Alterado - "description" |
| post/responses/422 | Alterado - "description" |
| post/responses/422/errors/items/code/enum | Adicionado - "DETALHE_PAGAMENTO_INVALIDO" |
| post/responses/422/errors/items/code/enum | Removido - "DETALHE_PGTO_INVALIDO" |
GET /consents/{consentId}
| Campo | O que foi feito? |
| get/parameters/x-fapi-interaction-id | Mandatoriedade - “obrigatório“ |
| get/responses/200/data/creditor/name | Alterado - "pattern" |
| get/responses/200/data/debtorAccount | Alterado - "description" |
| get/responses/200/data/debtorAccount/accountType | Alterado - "description" |
| get/responses/200/data/payment/details/creditorAccount/accountType | Alterado - "description" |
| get/responses/200/data/properties | Adicionado - "rejectionReason" |
POST /pix/payments
| Campo | O que foi feito? |
| post/parameters/x-fapi-interaction-id | Mandatoriedade - “obrigatório“ |
| post/requestBody/data/creditorAccount/accountType | Alterado - "description" |
| post/requestBody/data/creditorAccount/accountType/enum | Removido - "SLRY" |
| post/requestBody/data/properties | Adicionado - "authorisationFlow" |
| post/responses/201/data/creditorAccount/accountType | Alterado - "description" |
| post/responses/201/data/creditorAccount/accountType/enum | Removido - "SLRY" |
| post/responses/201/data/debtorAccount/accountType | Alterado - "description" |
| post/responses/201/data/debtorAccount/accountType/enum | Removido - "SLRY" |
| post/responses/201/data/properties | Adicionado - "authorisationFlow" |
| post/responses/201/data/rejectionReason/code | Alterado - "description" |
| post/responses/201/data/rejectionReason/code/enum | Adicionado - "CONTAS_ORIGEM_DESTINO_IGUAIS" |
| post/responses/201/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_DETENTORA" |
| post/responses/201/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_DICT" |
| post/responses/201/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_ICP" |
| post/responses/201/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_PSP_RECEBEDOR" |
| post/responses/201/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_SPI" |
| post/responses/400 | Alterado - "description" |
| post/responses/422 | Alterado - "description" |
| post/responses/422/errors/items/code | Alterado - "description" |
| post/responses/422/errors/items/code/enum | Removido - "BENEFICIARIO_INCOMPATIVEL" |
| post/responses/422/errors/items/code/enum | Removido - "JANELA_OPER_INVALIDA" |
| post/responses/422/errors/items/code/enum | Removido - "VALOR_INCOMPATIVEL" |
| get/responses/200/data/rejectionReason/code | Alterado - "description" |
GET /pix/payments/{paymentId}
| Campo | O que foi feito? |
| get/parameters/x-fapi-interaction-id | Mandatoriedade - “obrigatório“ |
| get/responses/200/data/creditorAccount/accountType | Alterado - "description" |
| get/responses/200/data/creditorAccount/accountType/enum | Removido - "SLRY" |
| get/responses/200/data/debtorAccount/accountType | Alterado - "description" |
| get/responses/200/data/debtorAccount/accountType/enum | Removido - "SLRY" |
| get/responses/200/data/properties | Adicionado - "authorisationFlow" |
| get/responses/200/data/rejectionReason/code | Alterado - "description" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "CONTAS_ORIGEM_DESTINO_IGUAIS" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_DETENTORA" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_DICT" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_ICP" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_PSP_RECEBEDOR" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_SPI" |
| get/security/0 | Alteração os security definitions |
| get/responses/200/data/rejectionReason/code | Alterado - "description" |
PATCH pix/payments/{paymentId}/
| Campo | O que foi feito? |
| patch | Alterado - "description" |
| patch/parameters/x-fapi-interaction-id | Mandatoriedade - “obrigatório“ |
| patch/responses/200/data/properties | Adicionado - "authorisationFlow" |
| patch/responses/200/data/rejectionReason/code | Alterado - "description" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "CONTAS_ORIGEM_DESTINO_IGUAIS" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_DETENTORA" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_DICT" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_ICP" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_PSP_RECEBEDOR" |
| get/responses/200/data/rejectionReason/code/enum | Adicionado - "FALHA_INFRAESTRUTURA_SPI" |
| patch/responses/422 | Alterado - "description" |
| patch/responses/422/errors/items/code | Alterado - "description" |
| patch/responses/422/errors/items/code | Alterado - "example” |
| patch/responses/422/errors/items/code/enum | Removido - "BENEFICIARIO_INCOMPATIVEL" |
| patch/responses/422/errors/items/code/enum | Removido - "COBRANCA_INVALIDA" |
| patch/responses/422/errors/items/code/enum | Removido - "CONSENTIMENTO_INVALIDO" |
| patch/responses/422/errors/items/code/enum | Removido - "DETALHE_PAGAMENTO_INVALIDO" |
| patch/responses/422/errors/items/code/enum | Removido - "ERRO_IDEMPOTENCIA" |
| patch/responses/422/errors/items/code/enum | Removido - "JANELA_OPER_INVALIDA" |
| patch/responses/422/errors/items/code/enum | Removido - "NAO_INFORMADO" |
| patch/responses/422/errors/items/code/enum | Removido - "PAGAMENTO_DIVERGENTE_CONSENTIMENTO" |
| patch/responses/422/errors/items/code/enum | Adicionado - "PAGAMENTO_NAO_PERMITE_CANCELAMENTO" |
| patch/responses/422/errors/items/code/enum | Removido - "PAGAMENTO_RECUSADO_DETENTORA" |
| patch/responses/422/errors/items/code/enum | Removido - "PAGAMENTO_RECUSADO_SPI" |
| patch/responses/422/errors/items/code/enum | Removido - "PARAMETRO_INVALIDO" |
| patch/responses/422/errors/items/code/enum | Removido - "PARAMETRO_NAO_INFORMADO" |
| patch/responses/422/errors/items/code/enum | Removido - "SALDO_INSUFICIENTE" |
| patch/responses/422/errors/items/code/enum | Removido - "VALOR_ACIMA_LIMITE" |
| patch/responses/422/errors/items/code/enum | Removido - "VALOR_INCOMPATIVEL" |
| patch/responses/422/errors/items/code/enum | Removido - "VALOR_INVALIDO" |
| patch/responses/422/errors/items/detail | Alterado - "description" |
| patch/responses/422/errors/items/detail | Alterado - "example” |
| patch/responses/422/errors/items/title | Alterado - "description" |
| patch/responses/422/errors/items/title | Alterado - "example” |
| patch/responses/422/examples/Saldo insuficiente/value/errors/0 | Alterado - "code” |
| patch/responses/422/examples/Saldo insuficiente/value/errors/0 | Alterado - "detail” |
| patch/responses/422/examples/Saldo insuficiente/value/errors/0 | Alterado - "title” |
| get/responses/200/data/rejectionReason/code | Alterado - "description" |