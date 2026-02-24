---
id: 17379077
title: Nível de Desempenho
version: 1
modified: 2022-10-28T19:35:18.989Z
url: /spaces/OF/pages/17379077/N+vel+de+Desempenho
---

O desempenho do *endpoint* da API será medido no tempo de resposta de cada solicitação, desde o recebimento da solicitação até a entrega da resposta.
Espera-se que o detentor dos dados garanta que a medição do tempo de resposta ocorra o mais próximo possível do receptor dos dados, embora algumas camadas técnicas não estejam no controle do detentor dos dados.À luz destas considerações, a exigência de desempenho para os detentores dos dados é:
- APIs de alta prioridade ( status/outages ) devem manter percentil 95 em no máximo 1000ms.
- APIs de média prioridade ( channels/products-services ) devem manter percentil 95 em no máximo 1500ms.
- APIs Admin (ex.  metrics ) devem manter percentil 95 em no máximo 4000ms.
P. ex. Em um dia que a API Produtos e Serviços receba 10.000 chamadas, pelo menos 9.500 delas deveriam ter sido respondidas dentro de um prazo inferior a 1500ms.O controle de timeout de tempo de resposta do servidor (server) e do tempo de espera resposta do consumidor (client), dever ser de 15 segundos para todos os endpoints das APIs.Para identificar que ocorreu timeout em uma determinada requisição, deve ser utilizado o status code 504 - Gateway Timeout.