---
id: 214597837
title: Assinatura de Mensagem vs Idempotência - v1.0.0-beta.2 - Pagamentos Automáticos
version: 1
modified: 2023-11-10T18:17:57.003Z
url: /spaces/OF/pages/214597837/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v1.0.0-beta.2+-+Pagamentos+Autom+ticos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.