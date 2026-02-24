---
id: 1521189132
title: Máquina de Estados - v1.0.0-beta.1 - [PC] Portabilidade de Crédito - CF
version: 1
modified: 2026-02-06T13:55:24.182Z
url: /spaces/OF/pages/1521189132/M+quina+de+Estados+-+v1.0.0-beta.1+-+PC+Portabilidade+de+Cr+dito+-+CF
---

**A máquina de estados para o produto Portabilidade de crédito é composta de 8 estados, listados a seguir:**
- RECEIVED
- PENDING
- ACCEPTED_SETTLEMENT_IN_PROGRESS
- ACCEPTED_SETTLEMENT_COMPLETED
- PAYMENT_ISSUE
- AWAITING_CONTRACT_DISCHARGE
- PORTABILITY_COMPLETED
- CANCELLED
- REJECTED

## Máquina de estados do produto Portabilidade de Crédito - Consignado
**Exemplo de cenários da Máquina de Estados CF**: Cenários Máquinas de Estados
### Descrição dos estados da Portabilidade de crédito:

#### RECEIVED
Estado inicial. Indica que o pedido de portabilidade foi solicitado junto à instituição credora. O pedido deve permanecer nesse estado até o próximo dia útil (D+1), quando começará a contagem do prazo de 3 dias úteis para a etapa de contraproposta. Nesse momento, o pedido de portabilidade deverá ser movido para o estado PENDING. Caso o cliente cancele o pedido de portabilidade no canal digital da proponente, e esta comunique o cancelamento à instituição credora, a portabilidade de crédito deverá ser movida para o estado CANCELLED.
#### PENDING
Indica que o pedido de portabilidade de crédito está na fase de contraproposta, durante a qual a instituição credora pode enviar uma contraproposta ao cliente por qualquer canal (e-mail, telefone etc.). Contudo, o aceite será válido apenas se o cliente aprovar a contraproposta no canal digital da instituição credora.​ 
- Caso a contraproposta não seja aceita no canal digital da credora e transcorram três dias úteis, OU caso a contraproposta seja rejeitada pelo cliente, a portabilidade de crédito deverá ser movida para o status ACCEPTED_SETTLEMENT_IN_PROGRESS​.
- Caso a credora não tenha interesse ou não deseje apresentar uma contraproposta, poderá mover a portabilidade para o status ACCEPTED_SETTLEMENT_IN_PROGRESS antes do término do prazo de três dias úteis. Essa atualização de status deverá, obrigatoriamente, ocorrer em dia útil, até às 10h da manhã​.
- Caso a contraproposta seja aceita pelo cliente no canal digital da credora, a portabilidade de crédito deverá ser movida para o status REJECTED​.
- Caso o cliente cancele o pedido de portabilidade no canal digital da proponente, e esta comunique o cancelamento à instituição credora, a portabilidade de crédito deverá ser movida para o status CANCELLED.

#### ACCEPTED_SETTLEMENT_IN_PROGRESS
Indica que a contraproposta não foi aceita pelo cliente, e a instituição proponente deverá quitar o valor do contrato no mesmo dia em que o estado foi ativado. 
- Independentemente da notificação, a Instituição credora deverá mudar para o estado ACCEPTED_SETTLEMENT_COMPLETED somente no próximo dia útil (D+1), caso identifique o recebimento da STR exclusiva do OFB.
- Caso o valor atualizado do contrato para quitação ultrapasse (exceda) mais do que 15% do valor original, a instituição proponente poderá cancelar a portabilidade, comunicando a credora, que atualizará o estado atual da portabilidade para REJECTED.
- Caso a instituição proponente não liquide o contrato no mesmo dia em que o estado corrente (ACCEPTED_SETTLEMENT_IN_PROGRESS) foi ativado, a instituição credora poderá mover o estado para REJECTED no (D+1), com o motivo de recusa apropriado.
- Caso o cliente cancele o pedido de portabilidade no canal digital da proponente, e esta comunicar o fato à instituição credora, a portabilidade de crédito deverá ser movida para CANCELLED.

#### ACCEPTED_SETTLEMENT_COMPLETED
Indica que a instituição credora iniciará a validação dos dados do contrato, bem como dos valores recebidos para a liquidação do mesmo. A etapa corrente até a desaverbação do contrato representado pelo estado AWAITING_CONTRACT_DISCHARGE, a instituição credora tem até 2 dias úteis para fornecer as informações referentes à liquidação do contrato original, por meio da consulta do pedido de portabilidade (*endpoint*[GET] /portabilities/{portabilityId}) e realizar a desaverbação junto a averbadora:
- Caso a instituição credora reconheça a liquidação do contrato original do pedido de portabilidade, deverá mover o estado para AWAITING_CONTRACT_DISCHARGE para a etapa de desaverbação junto a averbadora;
- Caso a instituição credora não reconheça o pagamento integral do contrato original, deverá mover o estado para PAYMENT_ISSUE;
- Caso a instituição proponente não tenha efetuado a liquidação no dia anterior, a instituição credora deverá mover o estado para REJECTED, com o motivo de recusa apropriado.

#### PAYMENT_ISSUE
Indica que a instituição credora encontrou alguma inconsistência na liquidação efetuada e que a instituição proponente deverá realizar ajustes conforme sugerido pela instituição credora, para solucionar a pendência antes do cancelamento do pedido de portabilidade de crédito.
- Caso a instituição proponente resolva as pendências encontradas, o pedido de portabilidade poderá seguir retornando ao estado ACCEPTED_SETTLEMENT_COMPLETED.
- Caso a instituição proponente não resolva a pendência no prazo, a instituição credora deverá mover o estado para REJECTED e, se aplicável, devolver o valor recebido para a origem do pagamento​.
- OBS.: Lembrando que todo o processo, a partir da primeira passagem do estado ACCEPTED_SETTLEMENT_COMPLETED até sua conclusão, deve ocorrer em até 2 dias úteis​.

#### AWAITING_CONTRACT_DISCHARGE
Indica que a instituição credora finalizou a portabilidade de crédito, fornecendo as informações referentes à quitação do contrato original, permanecendo pendente a solicitação de desaverbação junto à averbadora do contrato consignado para a transferência da margem consignada.
- Caso a instituição credora consiga realizar a desaverbação dentro do prazo (segundo a autorregulação de 2 dias úteis contados a partir da etapa anterior de confirmação do recebimento), deverá mover o pedido de portabilidade para o estado PORTABILITY_COMPLETED.
- Caso a instituição credora não consiga realizar a desaverbação no prazo de 10 dias corridos contados a partir do envio da STR0052 (realizada para liquidar a operação de crédito), a instituição credora deverá restituir por meio da STR0010 (motivo 85), e, logo em seguida a instituição credora deverá mover o pedido para o estado REJECTED, com o motivo de recusa apropriado (DESAVERBACAO_NAO_REALIZADA).

#### PORTABILITY_COMPLETED
Indica que o pedido de portabilidade foi concluído com sucesso.
#### CANCELLED
Indica que o cliente cancelou o pedido de portabilidade de crédito antes de a instituição credora informar que a operação não foi retida ou de a instituição proponente realizar a liquidação da operação.
#### REJECTED
OBS.: São considerados dias úteis apenas os dias de segunda a sexta-feira, exceto feriados nacionais. Além disso, as mudanças de estado vinculadas ao próximo dia útil (D+1) devem ocorrer entre 00:00h e 07:00h do próximo dia útil.
### Mapeamento por motivo de rejeição:

| Máquina de Estados data.status | Motivo da Rejeição data.statusReason.reasonType data.rejection.reason.type | Responsável pela solicitação da rejeição data.rejection.rejectedBy |
| --- | --- | --- |
| REJECTED | POLITICA_DE_CREDITO | PROPONENTE |
| RETENCAO_DO_CLIENTE | CREDORA |
| CONTRATO_JA_LIQUIDADO | CREDORA |
| SALDO_DEVEDOR_ATUALIZADO_SUBSTANCIALMENTE_DIVERGENTE | PROPONENTE |
| DECURSO_DO_PRAZO_PARA_PAGAMENTO | CREDORA |
| PORTABILIDADE_CANCELADA_POR_FALTA_DE_LIQUIDACAO | CREDORA |
| PORTABILIDADE_EM_ANDAMENTO | CREDORA |
| MODALIDADE_DA_OPERACAO_INCOMPATIVEL | CREDORA |
| CLIENTE_COM_ACAO_JUDICIAL | CREDORA |
| RESERVA_MARGEM | CREDORA |
| OUTROS | CREDORA, PROPONENTE |
| CANCELLED | CANCELADO_PELO_CLIENTE | USUARIO |
| PAYMENT_ISSUE | DIVERGENCIA_DE_PAGAMENTO_EFETUADO | CREDORA |
| OUTROS | CREDORA |