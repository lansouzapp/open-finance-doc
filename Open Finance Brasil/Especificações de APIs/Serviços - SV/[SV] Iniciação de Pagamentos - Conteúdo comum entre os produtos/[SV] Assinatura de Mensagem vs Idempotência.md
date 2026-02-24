---
id: 728301669
title: [SV] Assinatura de Mensagem vs Idempotência
version: 1
modified: 2024-12-06T19:20:19.676Z
url: /spaces/OF/pages/728301669/SV+Assinatura+de+Mensagem+vs+Idempot+ncia
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.