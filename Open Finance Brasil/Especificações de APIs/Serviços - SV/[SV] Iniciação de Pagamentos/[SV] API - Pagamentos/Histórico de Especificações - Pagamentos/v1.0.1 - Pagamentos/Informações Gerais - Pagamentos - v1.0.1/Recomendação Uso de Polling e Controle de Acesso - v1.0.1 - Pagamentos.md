---
id: 17376664
title: Recomendação Uso de Polling e Controle de Acesso - v1.0.1 - Pagamentos
version: 1
modified: 2022-10-27T12:03:42.562Z
url: /spaces/OF/pages/17376664/Recomenda+o+Uso+de+Polling+e+Controle+de+Acesso+-+v1.0.1+-+Pagamentos
---

#### A consulta via GET, para verificar o processamento da transação, pode ser efetuada a qualquer momento desde que se respeite o rate limit de:

- 300 TPS global, 50 TPS por instituição e 8 TPS por endereço IP (Internet Protocol). Como sugestão, é indicado que a instituição iniciadora do pagamento implemente um retry exponencial.

### Controle de acesso
O endpoint de consulta de pagamento GET /pix/payments/{​​​paymentId}​​​ deve suportar acesso a partir de access_token emitido por meio de um *grant_type* do tipo `client credentials`, como opção do uso do token vinculado ao consentimento (hybrid flow). Para evitar vazamento de informação, a detentora deve validar que o pagamento consultado pertence ao `client_id` que o criou e, caso haja divergências, retorne um erro HTTP 400.