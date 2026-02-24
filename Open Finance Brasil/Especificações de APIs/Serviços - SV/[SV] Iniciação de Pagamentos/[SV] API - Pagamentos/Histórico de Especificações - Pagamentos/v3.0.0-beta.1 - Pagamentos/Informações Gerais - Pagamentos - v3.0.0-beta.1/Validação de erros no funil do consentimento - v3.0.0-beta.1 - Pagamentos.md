---
id: 136937703
title: Validação de erros no funil do consentimento - v3.0.0-beta.1 - Pagamentos
version: 1
modified: 2023-07-05T17:42:21.116Z
url: /spaces/OF/pages/136937703/Valida+o+de+erros+no+funil+do+consentimento+-+v3.0.0-beta.1+-+Pagamentos
---

Na tabela abaixo, é possível observar quais são os possíveis retornos do campo rejectionReason podem ser enviados em cada etapa envolvida com o consentimento, no fluxo de pagamentos:
| Etapas do funil do consentimento | Code |
| --- | --- |
| (5) Início da autenticação | FALHA_INFRAESTRUTURA TEMPO_EXPIRADO_AUTORIZAÇAO |
| (6) Conclusão da autenticação | FALHA_INFRAESTRUTURA TEMPO_EXPIRADO_AUTORIZAÇAO REJEITADO_USUARIO |
| (7) Autorização do cliente | FALHA_INFRAESTRUTURA CONTAS_ORIGEM_DESTINO_IGUAIS CONTA_SALARIO SALDO_INSUFICIENTE VALOR_ACIMA_LIMITE QRCODE_INVALIDO |
| (8) Authorisation code emitido | FALHA_INFRAESTRUTURA TEMPO_EXPIRADO_CONSUMO |