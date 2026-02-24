---
id: 264307078
title: Assinatura de Mensagem vs Idempotência - v4.0.0-rc.1 - [SV] Pagamentos
version: 1
modified: 2024-01-18T20:49:07.861Z
url: /spaces/OF/pages/264307078/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v4.0.0-rc.1+-+SV+Pagamentos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.