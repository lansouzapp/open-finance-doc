---
id: 17376444
title: Assinatura de Mensagem vs Idempotência - Pagamentos - v1.1.0-rc1.0
version: 1
modified: 2022-10-27T12:03:40.610Z
url: /spaces/OF/pages/17376444/Assinatura+de+Mensagem+vs+Idempot+ncia+-+Pagamentos+-+v1.1.0-rc1.0
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.