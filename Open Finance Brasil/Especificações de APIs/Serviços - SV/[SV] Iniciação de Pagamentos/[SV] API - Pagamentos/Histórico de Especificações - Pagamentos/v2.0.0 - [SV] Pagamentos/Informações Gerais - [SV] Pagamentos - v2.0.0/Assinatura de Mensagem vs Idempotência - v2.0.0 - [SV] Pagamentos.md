---
id: 24182973
title: Assinatura de Mensagem vs Idempotência - v2.0.0 - [SV] Pagamentos
version: 3
modified: 2023-12-06T16:55:14.313Z
url: /spaces/OF/pages/24182973/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v2.0.0+-+SV+Pagamentos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.