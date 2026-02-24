---
id: 180061211
title: Assinatura de Mensagem vs Idempotência - v3.0.0 - [SV] Pagamentos
version: 2
modified: 2023-12-06T16:52:16.873Z
url: /spaces/OF/pages/180061211/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v3.0.0+-+SV+Pagamentos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.