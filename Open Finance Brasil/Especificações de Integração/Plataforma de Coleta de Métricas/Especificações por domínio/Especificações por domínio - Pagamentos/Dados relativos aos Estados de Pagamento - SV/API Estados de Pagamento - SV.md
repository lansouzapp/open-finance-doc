---
id: 1211858945
title: API Estados de Pagamento - SV
version: 5
modified: 2025-12-10T16:59:11.170Z
url: /spaces/OF/pages/1211858945/API+Estados+de+Pagamento+-+SV
---

v 1.02Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Payment Status API

| Campo | Definição | Obrigatório | Tipo | Regra de preenchimento | Roles | Métodos | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| clientOrgId | Identificador da organização de onde a chamada foi disparada. | Sim | string <uuid> | | SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| consentId | Identificador único do consentimento criado para aquele pagamento. | Sim | string | | SERVER | POST GET | | 100 | | | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,-.:=@;$_!*''%/?#]+ | uGQHwNupARo7I9E2PLJZph18a0M9y7DcUe7ITt3DqUOJd9NVjnskxf2 |
| createdAt | Carimbo do tempo do momento da criação do registro | Não | string <date-time> | | SERVER | GET | | 28 | | | | |
| eventDateTime | Data e hora associados à mudança de estados finais reportados, como liquidação, rejeição ou cancelamento. Deve ser informado em UTC-0. | Sim | string <date-time> | | SERVER | POST GET | | 28 | | | | 2025-08-18T00:00:00Z |
| paymentId | Código único para identificar a transação de pagamento | Sim | string | | SERVER | POST GET | | | | | ^[a-zA-Z0-9][a-zA-Z0-9\-]{0,99}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| paymentStatus | Status de agendamento ou final do pagamento | Sim | enum<string> | | SERVER | POST GET | ACSC, RJCT, CANC, SCHD | | | | | ACSC |
| paymentType | Tipo de pagamento realizado | Sim | enum<string> | | SERVER | POST GET | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | | | | | RECURRENT |
| reportId | Identificador único do registro criado na Plataforma de Coleta de Métricas. | Não | string | | SERVER | GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | |
| status | Informa o status do registro de reporte. | Não | enum<string> | | SERVER | GET | ACCEPTED, DISCARDED | | | | | |
| statusReasonCode | Razão do status informado. | Sim | string | Campo atrelado ao status de pagamento. Quando o status for RJCT (Rejected), o valor deve ser preenchido com o motivo da rejeição (valores previstos em rejectionReason.Code). Quando o status for CANC (Cancelled), o valor deve ser preenchido com o motivo do cancelamento (valores previstos em cancellationReason.Code). | SERVER | POST GET | | | | | | |