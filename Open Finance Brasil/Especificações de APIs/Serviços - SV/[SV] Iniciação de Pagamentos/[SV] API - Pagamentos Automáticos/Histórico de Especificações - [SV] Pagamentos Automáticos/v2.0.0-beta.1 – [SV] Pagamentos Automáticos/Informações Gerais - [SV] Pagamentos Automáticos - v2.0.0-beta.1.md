---
id: 628195414
title: Informações Gerais - [SV] Pagamentos Automáticos - v2.0.0-beta.1
version: 2
modified: 2024-10-11T15:20:18.790Z
url: /spaces/OF/pages/628195414/Informa+es+Gerais+-+SV+Pagamentos+Autom+ticos+-+v2.0.0-beta.1
---

23
## Visão geral
A API tem como objetivo coletar o consentimento e realizar a iniciação de pagamento entre bancos, instituições financeiras e é acessível também à estabelecimentos comerciais participantes do Open Finance Brasil.Os recursos estão disponíveis para pagadores que possuem registro em uma instituição detentora de conta participante do Open Finance, independentemente de serem pessoa física ou jurídica.
## Criar consentimento para iniciação de pagamento : (POST /automatic-payments/v2/recurring-consents)
Método para a criação do consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /recurring-consents[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPostRecurringConsents_v2.csv)
## Consultar consentimento para iniciação de pagamento : (GET /automatic-payments/v2/recurring-consents/{recurringConsentId})
Método para consultar o consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /recurring-consents[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsGetRecurringConsentsConsentId_v2.csv)
## Consultar consentimento para iniciação de pagamento : (PATCH /automatic-payments/v2/recurring-consents/{recurringConsentId})
Método para consultar o consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /recurring-consents[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPatchRecurringConsentsConsentId_v2.csv)
## Pix - Criar iniciação de pagamento : (POST /automatic-payments/v2/pix/recurring-payments)
Método para a criação de uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPostPixRecurringPayments_v2.csv)
## Pix - Criar iniciação de pagamento : (GET /automatic-payments/v2/pix/recurring-payments)
Método para a criação de uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsGetPixRecurringPayments_v2.csv)
## Pix - Consultar iniciação de pagamento : (GET /automatic-payments/v2/pix/recurring-payments/{recurringPaymentId})
Método para consultar uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments/{recurringPaymentId}.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsGetPixRecurringPaymentsPaymentId_v2.csv)
## Pix - Cancelar iniciação de pagamento : (PATCH /automatic-payments/v2/pix/recurring-payments/{recurringPaymentId})
Método para cancelar uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de /pix/recurring-payments/{recurringPaymentId}.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/automaticPaymentsPatchPixRecurringPaymentsPaymentId_v2.csv)