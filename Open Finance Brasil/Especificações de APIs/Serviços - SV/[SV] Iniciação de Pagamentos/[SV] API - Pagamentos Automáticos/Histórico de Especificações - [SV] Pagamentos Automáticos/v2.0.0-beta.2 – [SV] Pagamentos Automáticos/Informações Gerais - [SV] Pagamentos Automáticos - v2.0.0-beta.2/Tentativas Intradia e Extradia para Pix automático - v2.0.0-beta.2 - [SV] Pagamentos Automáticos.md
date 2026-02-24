---
id: 718405998
title: Tentativas Intradia e Extradia para Pix automático - v2.0.0-beta.2 - [SV] Pagamentos Automáticos
version: 2
modified: 2024-12-06T19:48:26.738Z
url: /spaces/OF/pages/718405998/Tentativas+Intradia+e+Extradia+para+Pix+autom+tico+-+v2.0.0-beta.2+-+SV+Pagamentos+Autom+ticos
---

- Conceito geral do fluxo de tentativas Intradia e Extradia para o produto Pix automático Fluxo Intradia - A transação ocorre no dia em que foi solicitada a sua programação Primeira Tentativa: A liquidação da transação é tentada entre 0h e 8h no dia programado Na situação de falha onde o e2eid não pode ser mais utilizado a iniciadora deve enviar um novo pagamento contendo um novo e2eid Situações de erro que exigem a realização de novas tentativas de liquidação pelo iniciador, com e sem reenvio de e2eID para o agendamento do pagamento, conforme Tabela 1 O horário de envio que o Iniciador deve enviar o novo e2eid para ser persistido na segunda tentativa deve ser no máximo ao meio-dia (12h00) do mesmo dia para para tentativas de liquidação intradia Segunda Tentativa: Se a ordem de pagamento não for liquidada até às 8h, o PSP (prestador de serviços de pagamento) do pagador deve realizar uma nova tentativa entre 18h e 21h do mesmo dia Fluxo Extradia - A transação é programada para ocorrer em uma data futura, com processamento e liquidação automática nessa data O iniciador a pedido do recebedor pode realizar as novas tentativas Quando um pagamento não é liquidado na data programada (Intradia), a detentora pode realizar novas tentativas dentro de uma janela de 7 dias corridos após a data original de liquidação, por meio de acionamento do iniciador para detentora, até às 23:59h do dia imediatamente anterior à liquidação Durante esse período de sete dias o iniciador pode fazer até três tentativas de liquidação em datas diferentes, seguindo as mesmas regras de prazos da intradia
**Tabela 1: Situações de erro que exigem a realização de novas tentativas de liquidação pelo iniciador, com e sem reenvio de e2eID para o agendamento do pagamento**
| Código de erro | Contabiliza tentativa? | Permite nova tentativa intradia ³ | Exige reevio de e2eID |
| NAO_INFORMADO | SIM | SIM | SIM |
| PAGAMENTO_RECUSADO_SPI | SIM | SIM | SIM |
| FALHA_INFRAESTRUTURA_SPI | SIM | SIM | SIM |
| FALHA_INFRAESTRUTURA_ICP | SIM | SIM | SIM |
| FALHA_INFRAESTRUTURA_PSP_RECEBEDOR | SIM | SIM | SIM |
| SALDO_INSUFICIENTE | SIM | SIM | NÃO |
| VALOR_ACIMA_LIMITE | SIM | SIM | NÃO |
| PAGAMENTO_RECUSADO_DETENTORA | SIM | SIM | NÃO |
| FALHA_INFRAESTRUTURA_DETENTORA | SIM | NÃO | NÃO |
| LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO² | SIM | NÃO | NÃO |
| DETALHE_TENTATIVA_INVALIDO | NÃO | SIM | NÃO |
| VALOR_INVALIDO | NÃO | NÃO | NÃO |
| PAGAMENTO_DIVERGENTE_CONSENTIMENTO | NÃO | NÃO | NÃO |
| CONSENTIMENTO_INVALIDO | N/A | NÃO | NÃO |
| TITULARIDADE_INCONSISTENTE | N/A | NÃO | NÃO |
| LIMITE_PERIODO_VALOR_EXCEDIDO¹ | N/A | NÃO | NÃO |
| LIMITE_PERIODO_QUANTIDADE_EXCEDIDO¹ | N/A | NÃO | NÃO |
| LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO¹ | N/A | NÃO | NÃO |
| LIMITE_TENTATIVAS_EXCEDIDO² | N/A | NÃO | NÃO |
| CONSENTIMENTO_REVOGADO² | N/A | NÃO | NÃO |
| FORA_PRAZO_PERMITIDO | N/A | NÃO | NÃO |
| PERMISSAO_INSUFICIENTE | N/A | NÃO | NÃO |
¹ - Erro exclusivo para o produto Transferências inteligentes
² - Erro não ocorre no momento da liquidação, apenas no momento do agendamento
³ - Conforme previsto no Art. 7, parágrafo 1 da IN BCB 513 - "Caso a ordem de pagamento não seja enviada para liquidação no horário previsto, por ausência de recursos suficientes ou de limite transacional disponível, o prestador de serviços de pagamento do usuário pagador deve enviar notificação para seu cliente informando-o sobre a não liquidação do Pix Automático (...)"
- Exemplo de aplicabilidade

- Data envio: 14/09/24 – (02 a 10 dias de antecedência da liquidação) Data liquidação: 16 de setembro de 2024.
- A primeira tentativa (Intradia): Data liquidação: 16 de setembro de 2024 Primeira Tentativa: A liquidação é tentada entre 0h e 8h. Se houver saldo suficiente e os limites forem respeitados, a transação é concluída. Caso falhe (por exemplo, por saldo insuficiente), segue-se para as novas tentativas. Segunda Tentativa: Uma nova tentativa é feita entre 18h e 21h. Se houver saldo suficiente e os limites forem respeitados, a transação é concluída Em caso de falha considerar o cenário de tentativas (Extradias)
 
- Novas tentativas nos 7 dias seguintes (Extradias): Se a liquidação não for concluída no dia 16 de setembro, o detentor pode tentar realizar novas liquidações durante os próximos 7 dias corridos, através do acionamento do iniciador em até 3 tentativas em dias diferentes. Primeira Tentativa Extradias: 18 de setembro de 2024 A primeira tentativa após a falha no dia 16 pode ser feita. A liquidação é tentada novamente dentro das janelas de liquidação. Segunda Tentativa Extradias: 20 de setembro de 2024 Se a tentativa do dia 18 falhar, o iniciador pode realizar uma nova tentativa Terceira Tentativa Extradias: 22 de setembro de 2024, é feita no dentro do período de 7 dias corridos. Se houver saldo suficiente e os limites forem respeitados, a transação é concluída Em caso de falha notificar o motivo