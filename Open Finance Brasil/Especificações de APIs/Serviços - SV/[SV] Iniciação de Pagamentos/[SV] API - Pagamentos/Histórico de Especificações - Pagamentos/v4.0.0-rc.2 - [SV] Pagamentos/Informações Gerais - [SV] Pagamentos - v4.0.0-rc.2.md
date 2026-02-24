---
id: 305594389
title: Informações Gerais - [SV] Pagamentos - v4.0.0-rc.2
version: 2
modified: 2024-02-21T18:15:43.496Z
url: /spaces/OF/pages/305594389/Informa+es+Gerais+-+SV+Pagamentos+-+v4.0.0-rc.2
---

23
## Visão geral
A API tem como objetivo coletar o consentimento e realizar a iniciação de pagamento entre bancos, instituições financeiras e é acessível também à estabelecimentos comerciais participantes do Open Finance Brasil.Os recursos estão disponíveis para pagadores que possuem registro em uma instituição detentora de conta participante do Open Finance, independentemente de serem pessoa física ou jurídica.
## Criar consentimento para iniciação de pagamento : (POST /payments/v4/consents)
Método para a criação do consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de `/consents`[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/paymentsPostConsents_v4.csv)
## Consultar consentimento para iniciação de pagamento : (GET /payments/v4/consents/{consentId})
Método para consultar o consentimento para iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de `/consents/{consentId}`[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/paymentsGetConsentsConsentId_v4.csv)
## Pix - Criar iniciação de pagamento : (POST /payments/v4/pix/payments)
Método para a criação de uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de `/pix/payments`[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/paymentsPostPixPayments_v4.csv)
## Pix - Consultar iniciação de pagamento : (GET /payments/v4/pix/payments/{paymentId})
Método para consultar uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de `/pix/payments/{paymentId}`.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/paymentsGetPixPaymentsPaymentId_v4.csv)
## Pix - Cancelar iniciação de pagamento : (PATCH /payments/v4/pix/payments/{paymentId})
Método para cancelar uma iniciação de pagamento.
### Dicionário de dados
Campos de resposta do endpoint de `/pix/payments/{paymentId}`.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/paymentsPatchPixPaymentsPaymentId_v4.csv)
## Pix - Cancelar iniciação de pagamento : (PATCH /payments/v4/pix/payments/consents/{consentId})
Método para cancelar todos os pagamentos referentes ao mesmo consentimento.
### Dicionário de dados
Campos de resposta do endpoint de `/pix/payments/consents/{consentId}`.[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/paymentsPatchPixPaymentsConsentId_v4.csv)