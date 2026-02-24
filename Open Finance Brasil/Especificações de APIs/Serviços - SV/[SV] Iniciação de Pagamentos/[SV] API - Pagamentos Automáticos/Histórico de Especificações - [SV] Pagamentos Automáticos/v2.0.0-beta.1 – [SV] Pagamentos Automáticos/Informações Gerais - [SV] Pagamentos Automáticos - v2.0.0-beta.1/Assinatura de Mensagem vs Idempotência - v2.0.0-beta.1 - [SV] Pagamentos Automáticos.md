---
id: 628195623
title: Assinatura de Mensagem vs Idempotência - v2.0.0-beta.1 - [SV] Pagamentos Automáticos
version: 1
modified: 2024-10-11T15:18:34.002Z
url: /spaces/OF/pages/628195623/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v2.0.0-beta.1+-+SV+Pagamentos+Autom+ticos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.