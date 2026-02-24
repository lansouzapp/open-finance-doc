---
id: 223805974
title: Informações Gerais - [SV] Pagamentos Automáticos - v1.0.0-beta.3
version: 3
modified: 2023-12-06T16:46:41.243Z
url: /spaces/OF/pages/223805974/Informa+es+Gerais+-+SV+Pagamentos+Autom+ticos+-+v1.0.0-beta.3
---

23
## Visão geral
A API tem como objetivo coletar o consentimento e realizar a iniciação de pagamento entre bancos, instituições financeiras e é acessível também à estabelecimentos comerciais participantes do Open Finance Brasil.Os recursos estão disponíveis para pagadores que possuem registro em uma instituição detentora de conta participante do Open Finance, independentemente de serem pessoa física ou jurídica.
## Criar consentimento para iniciação de pagamento : (POST /automatic-payments/v1/recurring-consents)
Método para a criação do consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /recurring-consents[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPostRecurringConsents_v1.csv)
## Consultar consentimento para iniciação de pagamento : (GET /automatic-payments/v1/recurring-consents/{consentId})
Método para consultar o consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /recurring-consents[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsGetRecurringConsentsConsentId_v1.csv)
## Consultar consentimento para iniciação de pagamento : (PATCH /automatic-payments/v1/recurring-consents/{consentId})
Método para consultar o consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /recurring-consents[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPatchRecurringConsentsConsentId_v1.csv)
## Pix - Criar iniciação de pagamento : (POST /automatic-payments/v1/pix/recurring-payments)
Método para a criação de uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPostPixRecurringPayments_v1.csv)
## Pix - Criar iniciação de pagamento : (GET /automatic-payments/v1/pix/recurring-payments)
Método para a criação de uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsGetPixRecurringPayments_v1.csv)
## Pix - Consultar iniciação de pagamento : (GET /automatic-payments/v1/pix/recurring-payments/{paymentId})
Método para consultar uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments/{paymentId}.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsGetPixRecurringPaymentsPaymentId_v1.csv)
## Pix - Cancelar iniciação de pagamento : (PATCH /automatic-payments/v1/pix/recurring-payments/{paymentId})
Método para cancelar uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments/{paymentId}.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPatchPixRecurringPaymentsPaymentId_v1.csv)