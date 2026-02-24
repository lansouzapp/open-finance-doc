---
id: 223806178
title: Assinatura de Mensagem vs Idempotência - v1.0.0-beta.3 - [SV] Pagamentos Automáticos
version: 2
modified: 2023-12-06T16:47:58.896Z
url: /spaces/OF/pages/223806178/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v1.0.0-beta.3+-+SV+Pagamentos+Autom+ticos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.