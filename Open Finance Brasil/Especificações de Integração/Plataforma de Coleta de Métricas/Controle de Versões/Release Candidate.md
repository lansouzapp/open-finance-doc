---
id: 1118470185
title: Release Candidate
version: 7
modified: 2025-11-18T14:06:10.069Z
url: /spaces/OF/pages/1118470185/Release+Candidate
---

v 1.00
## Objetivo desta página
Acompanhar, em caráter preliminar, a lista e status das iniciativas previstas para cada novo ciclo de desenvolvimento da PCMRelease 2025D1800**Data prevista da release:** 17/11/2025
| Contexto | Detalhes | Status atual |
| --- | --- | --- |
| Jornada Sem Redirecionamento | Novo código de rejeição (rejectionReasonCode): ORIGEM_FIDO_INVALID) no POST /consents/{consentId}/authorise | Finalizado |
| Jornada Sem Redirecionamento | Novo código de rejeição (rejectionReasonCode): MAXIMO_CHALLENGES_ATINGIDO no POST /enrollments/{enrollmentId}/fido-registration-options | Finalizado |
| Jornada Sem Redirecionamento | Novo código de rejeição (rejectionReasonCode): REJEITADO_TITULARIDADE_DIVERGENTE no GET /enrollments/enrollmentId | Finalizado |
| Jornada Sem Redirecionamento | Novo endpoint para autorização de consentimentos recorrentes de Pix Automático | Finalizado |
| Jornada Sem Redirecionamento | Ajuste do endpoint que obtém os parâmetros de autenticação para incluir consentimentos de longa duração (recurringConsentId) no POST /enrollments/{enrollmentId}/fido-sign-options | Finalizado |
| Jornada Sem Redirecionamento | Ajuste da descrição do endpoint POST /enrollments/{enrollmentId}/risk-signals | Sem impacto para a PCM, retirado da release |
| Jornada Otimizada | Jornada Otimizada - Inclusão de campos para monitoramento de consentimentos em Jornada Otimizada | Finalizado |
| Jornada Sem Redirecionamento | Novo código de erro (errorCode): PERMISSAO_INVALIDA_VINCULO_CONSENTIMENTO em /enrollments/{enrollmentId}/fido-sign-options | Finalizado |
| Pagamentos Automáticos | inclusão de localInstrument AUTO em GET /pix/payments/{recurringPaymentId} e PATCH /pix/payments/{recurringPaymentId} | Finalizado |
| Pagamentos Automáticos | Alteração da descrição do endpoint PATCH /recurring-consents/{recurringConsentId} | Finalizado |
| Pagamentos Automáticos | Alteração na regra do campo localInstrument para o tipo AUTO em POST /pix/recurring-payments, GET /pix/recurring-payments/{recurringPaymentId} e PATCH /pix/recurringpayments/{recurringPaymentId} | Finalizado |
| Pagamentos Automáticos | Remoção do código de erro (errorCodes) DETALHE_TENTATIVA_INVALIDA em POST /pix/recurring-payments | Finalizado |
| Pagamentos Automáticos | Remoção da mensagem de cancelamento do pagamento em POST /pix/recurring-payments | Finalizado |
| Pagamentos Automáticos | Remoção dos códigos de erro (errorCodes): DETALHE_TENTATIVA_INVALIDO e LIMITE_TENTATIVAS_EXCEDIDO em POST /pix/recurring-payments | Finalizado |
| Pagamentos Automáticos | Novo código de rejeição (rejectionReasonCode):FLUXO_NAO_SUPORTADO_PRODUTO em POST /recurring-consents, GET /recurring-consents/{recurringConsentId} e PATCH /recurring-consents/{recurringConsentId} | Finalizado |
| Pagamentos Automáticos | Alteração das regras de preenchimento para o campo paymentReference em POST /pix/recurring-payments, GET /pix/recurring-payments/{recurringPaymentId}, GET /pix/recurring-payments e PATCH /pix/recurringpayments/{recurringPaymentId} | Sem impacto para a PCM, retirado da release |
| Pagamentos Automáticos | Altração do código de erro (errorCodes): LIMITE_TENTATIVAS_EXCEDIDO) | Sem impacto para a PCM, retirado da release |
| Portabilidade de Crédito | Ingestão de consentId para Portabilidade de Crédito | Finalizado |
| Segurança | Tratamento do tempo de expiração do token | Finalizado |
| Dados Cadastrais e Transacionais / Pagamentos | IQD PJ | Retirado da release |
| Dados Cadastrais e Transacionais / Pagamentos / Hybridflow / Segurança / Dados Abertos | Introdução do additionalInfo tokenId para vinculação e rastreabilidade das jornadas de tokens | Finalizado |
| Iniciação de Pagamentos / Pagamentos Automáticos | Desambiguação de jornadas de pagamentos via campo autorisationFlowIntent | Finalizado |