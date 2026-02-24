---
id: 1216872449
title: Changelog Completo
version: 13
modified: 2026-02-09T18:32:40.354Z
url: /spaces/OF/pages/1216872449/Changelog+Completo
---

## Objetivo desta página
Registrar as mudanças realizadas na documentação da PCM.
# Primeiros passos

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Visão geral da PCM | v.7 | 03/01/2023 | Atualizadas as premissas técnicas | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Manual de integração | v.11 | 04/04/2024 | Atualização de links da documentação da API Inclusão do fluxo de autenticação Alteração no exemplo de autenticação Alteração no exemplo da interação com a API Alteração no exemplo do cenário PAIRED_INCONSISTENT | | |
| | v.1 | 23/12/2022 | Versão inicial | | |
| Lista de endpoints | 1.02 | 10/11/2025 | Inclusão do endpoint /open-banking/enrollments/v2/recurring-consents/{recurringConsentId}/authorise | 2025D | |
| | 1.01 | 12/09/2025 | Retirada do endpoint /open-banking/credit-portability/v1/credit-operations/{contractId}/portability-eligibility de Portabilidade de Crédito, incluído erronamente. | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |

# Especificações por Domínio

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Dados Abertos | | | | | |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Obrigatoriedade de additionalInfo | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Dados Cadastrais e Transacionais | | | | | |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Obrigatoriedade de additionalInfo | 1.0.3 | 10/12/2025 | Ajuste no padrão do campo consentId | | |
| | 1.0.2 | 10/11/2025 | Inclusão do additionalInfo tokenId Inclusão do additionalInfo journeyIsLinked, referente à Jornada Otimizada | 2025D | |
| | 1.01 | 01/10/2025 | Melhoria na descrição do campo companyProfileInfo, contemplando os links para pesquisa de CNPJ | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| | | | | | |
| Regras de Validação | 1.01 | 17/12/2025 | Inclusão da validação do campo companyProfileInfo para Consentimentos, de acordo com a implementação realizada na release 2025C | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Pagamentos | | | | | |
| Estados de Pagamento | 1.0.2 | 10/12/2025 | Ajuste no padrão do campo paymentId | | |
| | 1.01 | 03/10/2025 | Correção do role responsável pelo envio - de CLIENT para SERVER Inclusão do domínio “SCHEDULED” em paymentType | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Obrigatoriedade de additionalInfo | 1.06 | 23/01/2026 | Ajuste na regra de preenchimento do campo errorCodes, dando clareza à regra vigente de envio de apenas um registro, e não de uma lista. Ajuste na obrigatoriedade de envio dos campos journeyIsLinked e journeyLinkId para PIX Automáticos - retirada da restrição de 4xx e 5xx | | |
| | 1.05 | 01/12/2025 | Inclusão do endpoint /open-banking/enrollments/v x /recurring-consents/{recurringConsentId}/authorise, na Jornada Sem Redirecionamento, para os additionalInfo enrollmentId, recurringConsentId e errorCodes. | 2025D | |
| | 1.04 | 10/11/2025 | Inclusão do additionalInfo recurringConsentId para o endpoint /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options, mutuamente excludente com o additionalInfo consentId Inclusão das regras de validação dos additionalInfo consentId e recurringConsentId para Jornada sem Redirecionamento Inclusão do domínio AUTO no additionalInfo localInstrument para Iniciação de Pagamentos e PIX Automático Retirado do domínio do additionalInfo errorCodes de Pagamentos Automáticos: DETALHE_TENTATIVA_INVALIDA e LIMITE_TENTATIVAS_EXCEDIDO Incluído no domínio do additionalInfo rejectionReasonCode de Pagamentos Automáticos: FLUXO_NAO_SUPORTADO_PRODUTO Inclusão do additionalInfo authorisationFlowIntent para Iniciação de Pagamentos e Pagamentos Automáticos Inclusão do additionalInfo tokenId para todas as jornadas Inclusão dos additionalInfo journeyIsLinked e journeyLinkId em Jornada Sem Redirecionamento e PIX Automático, referentes à Jornada Otimizada | 2025D | |
| | 1.03 | 01/10/2025 | Melhoria na descrição do campo companyProfileInfo, contemplando os links para pesquisa de CNPJ Inclusão do domínio do campo status para Pagamento Sem Redirecionamento | | |
| | 1.02 | 24/09/2025 | Alteração na regra de preenchimento do campo authorisationFlow em Iniciação de Pagamentos e PIX Automático, de acordo com o contrato da API Inclusão de domínio do campo authorisationFlow em Iniciação de Pagamentos e PIX Automático, de acordo com o contrato da API | | |
| | 1.01 | 12/09/2025 | Retirada dos campos riskSignalsEnumList e rislSignalsQuantity, incluídos erroneamente na documentação Ajustes na documentação: authorisationFlow: inclusão do endpoint /open-banking/payments/v x /pix/payments/{paymentId}​ e métodos GET/PATCH consentId: correção do padrão, exemplo e statusCodes errorCodes: ajuste no domínio para erros 422 demais erros paymentSchedule: correção na regra de preenchimento - deve ser mutualmente excludente com paymentDate paymentList: identificação dos itens que fazem parte da lista com o identificador paymentList[]. paymentType: adequação da regra de preenchimento nfcPayment: ajuste na regra de preenchimento status: ajuste na descrição do campo para Pagamentos Sem Redirecionamento | | |
| | 1.00 | 22/08/2025 | Versão inicial | | |
| Regras de Validação | 1.04 | 09/02/2026 | Inclusão de campos: paymentSchedule e localInstrument Ajustes diversos nas validações | | |
| | 1.03 | 15/10/2025 | Inclusão da validação do campo companyProfileInfo para Iniciação de Pagamentos, Jornada Sem Redirecionamento e Pagamentos Automáticos, de acordo com a implementação realizada na release 2025C Inclusão da validação do campo nfcPayment para Jornada Sem Redirecionamento, de acordo com implementação realizada na release 2025B | | |
| | 1.02 | 09/10/2025 | Ajuste das regras de validação para refletir alterações feitas nas obrigatoriedades de campos da PCM | | |
| | 1.01 | 15/09/2025 | Retirada da regra de validação do additionalInfo authenticatorAttachment devido ao campo não ser obrigatório | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Portabilidade de crédito | | | | | |
| Funcionalidade e Campos | 1.01 | 13/10/2025 | Alteração do status ACCEPTED_SETTLEMENT_IN_PROCESS para ACCEPTED_SETTLEMENT_IN_PROGRESS | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Campos Obrigatórios e Opcionais | 1.0.5 | 02/01/2026 | Ajuste na visualização dos campos, separando os campos de acordo com a obrigatoriedade de envio no POST e recuperação através de GET na PCM, com o intuito de diferenciar os métodos e endopints exigidos pelas APIs de produtos contra a forma de envio e obtenção dos campos na PCM. | | |
| | 1.0.4 | 10/12/2025 | Ajuste no padrão do campo consentId | | |
| | 1.0.3 | 10/11/2025 | Inclusão dos campos creationDateTime e consentId Exclusão dos campos role, contractId, originalContractTerm e propositionTerm Inclusão das informações referentes à obrigatoriedade considerando Http code e endpoint Complementadas as regras de preenchimento dos campos cresitPortabilityStatus, rejectedBy e rejectionReason para dar mais clareza | 2025D | |
| | 1.02 | 13/10/2025 | Alteração do domínio do campo creditPortabilityStatus - de ACCEPTED_SETTLEMENT_IN_PROCESS para ACCEPTED_SETTLEMENT_IN_PROGRESS | | |
| | 1.01 | 26/09/2025 | Exclusão do campo Id do Reporte da API Client | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.01 | 09/02/2026 | Inclusão da regra de validação do campo consentId Inclusão da regra de validação do campo errorCode Ajustes diversos nas validações | | |
| | 1.00 | 03/12/2025 | Versão inicial | 2025D | |
| Regras de Descarte | 1.0.1 | 10/12/2025 | Inclusão das regras de descarte da API de Estados de Pagamento | | |
| | 1.00 | 10/11/2025 | Versão inicial | 2025D | |
| Hybridflow | | | | | |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Diagramas de Fluxo | | | | | |
| Diagrama de Envio de Reportes | v.3 | 03/09/2025 | Atualização do diagrama | | |
| | v.1 | 26/08/2025 | Versão inicial | | |
| Diagrama de Sequência | v.1 | 26/08/2025 | Versão inicial | | |
| Segurança | | | | | |
| Regras de Obrigatoriedade de additionalInfo | 1.0.1 | 10/12/2025 | Ajuste no padrão do campo consentId | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Consentimentos | | | | | |
| Estoque de Consentimentos Ativos | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.01 | 09/02/2026 | Inclusão da regra de validação de envio diário do estoque de consentimento Inclusão da regra de validação dos campos clientOrgId e serverOrgId | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |

# Integração Técnica

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Especificações de Reporte | | | | | |
| Processo de Reporte | v.50 | 31/10/2025 | Atualização do link do manual de integtação Inclusão e ajustes dos modelos dos reportes Inclusão de informações sobre additionalInfo Inclusão e ajustes das formas de envio | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Processamento de Dados | v.11 | 21/11/2025 | Retirado um trecho da Conciliação que estava gerando dúvida sobre o processo de descarte do campo fapiInteractionId x statusCode 408 e 5xx. Ajustado o diagrama de Ciclo de vida do reporte para refletir o processo correto na ausência do fapiInteractionId para statusCode 408 e 5xx. Ajustada a definição de ACCEPTED, refletindo o ajuste realizado no diagrama do Ciclo de vida de reporte. | | |
| | v.10 | 23/02/2024 | Inclusão do processo de conciliação Inclusão do ciclo de vida do reporte | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Tratamento de Divergências | v.4 | 25/12/2022 | Ajuste de texto (inconsistências) | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Documentação da API | v.7 | 07/10/2025 | Movimentação da visualização legada para a estrutura de histórico | | |
| | v.1 | 25/08/2025 | Versão inicial | | |

# Gestão Operacional

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Notificações via ticket | | | | | |
| SLA de Envio | 1.02 | 10/11/2025 | Ajuste da fórmula apresentada de cálculo do SLA - o cálculo está sendo feito corretamente, porém a fórmula documentada não estava refletindo a realidade | 2025D | |
| | 1.01 | 10/10/2025 | Início do envio dos tickets de SLA de Envio de Dados Cadastrais e Transacionais (Fases 2 e 4b) | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Qualidade de Dados | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Reportes Descartados | 1.01 | 03/11/2025 | Início do envio dos tickets de Reportes Descartados de Segurança | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Reportes Não Pareados | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| FAQ | v.4 | 15/04/2024 | Atualização do descritivo do SLA de reportes à PCM Inclusão de informação sobre crítica de criação de consentimento | | |
| | v.1 | 18/01/2023 | Versão inicial | | |
| Troubleshooting | v.6 | 08/04/2024 | Inclusão das críticas “Report is too old” e “OrganisationId doesn’t exist on Directory” | | |
| | v.1 | 18/01/2023 | Versão inicial | | |

# Controle de Versões

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Release Notes | 1.00 | 15/09/2025 | Versão inicial | | |
| Release Candidate | 1.00 | 09/10/2025 | Versão inicial | | |
| Calendário de releases | 1.00 | 09/10/2025 | Versão inicial | | |
| Changelog completo | 1.01 | | Reestruturação do changelog de acordo com a nova árvore de documentação da PCM | | |
| | 1.00 | | Versão inicial | 2025C | 781 - 22/08/2025 |