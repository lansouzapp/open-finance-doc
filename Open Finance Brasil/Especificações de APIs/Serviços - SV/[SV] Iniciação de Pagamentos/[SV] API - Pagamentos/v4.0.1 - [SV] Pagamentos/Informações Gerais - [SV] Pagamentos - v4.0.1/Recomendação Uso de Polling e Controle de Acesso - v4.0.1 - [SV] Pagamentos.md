---
id: 1165623512
title: Recomendação Uso de Polling e Controle de Acesso - v4.0.1 - [SV] Pagamentos
version: 1
modified: 2025-10-10T20:49:48.701Z
url: /spaces/OF/pages/1165623512/Recomenda+o+Uso+de+Polling+e+Controle+de+Acesso+-+v4.0.1+-+SV+Pagamentos
---

A consulta via GET, para verificar o processamento da transação, pode ser efetuada a qualquer momento desde que se respeite os limites da seção "Requisitos não Funcionais". Como sugestão, é indicado que a instituição iniciadora do pagamento implemente um retry exponencial.
### Controle de acesso
O endpoint de consulta de pagamento GET /pix/payments/{​​​paymentId}​​​ deve apenas suportar acesso a partir de access_token emitido por meio de um *grant_type* do tipo `client credentials`, como opção do uso do token vinculado ao consentimento (hybrid flow). Para evitar vazamento de informação, a detentora deve validar que o pagamento consultado pertence ao `client_id` que o criou e, caso haja divergências, retorne um erro HTTP 400.