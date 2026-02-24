---
id: 193954234
title: Assinatura de Mensagem vs Idempotência - v4.0.0-beta.1 - Pagamentos
version: 1
modified: 2023-10-13T23:06:42.648Z
url: /spaces/OF/pages/193954234/Assinatura+de+Mensagem+vs+Idempot+ncia+-+v4.0.0-beta.1+-+Pagamentos
---

O claim jti inserido dentro do JWT da assinatura da mensagem tem como objetivo evitar ataques de repetição e não é utilizado para o controle da idempotência. Desta forma ele deverá ser gerado a cada nova requisição realizada às APIs, independentemente desta ser a requisição para a criação de uma nova operação ou ser a requisição para confirmação de execução de uma operação anterior (idempotente).As validações referentes a assinatura de mensagens devem preceder as validações de idempotência.