---
id: 17379029
title: Disponibilidade e Desempenho
version: 1
modified: 2022-10-28T19:35:18.852Z
url: /spaces/OF/pages/17379029/Disponibilidade+e+Desempenho
---

---

# Limites de Tráfego de Requisições

---
id: 17379100
title: Limites de Tráfego de Requisições
version: 1
modified: 2022-10-28T19:35:18.971Z
url: /spaces/OF/pages/17379100/Limites+de+Tr+fego+de+Requisi+es
---

## Os limites de tráfego serão estabelecidos utilizando as seguintes métricas:

- Transações por segundo (TPS) - o número de transações simultâneas a cada segundo;
- Número de chamadas - o número de chamadas de  endpoint  iniciadas por uma duração especificada.
Cada instituição transmissora deverá garantir os seguintes limites mínimos de tráfego abaixo especificados para as APIs de Dados Públicos – Fase 1, os quais serão revisados e ajustados em decorrência dos indicadores de uso das APIs, com revisão prevista imediatamente antes da entrada da Fase 2:
- 500 requisições por minuto por receptora (via endereço IP);
- 300 TPS globalmente.
As chamadas que excedam os seguintes limites de tráfego poderão ser enfileiradas ou rejeitadas por um detentor de dados sem impacto em seu desempenho ou requisitos de disponibilidade.Requisições que ultrapassem os limites estabelecidos poderão ser rejeitadas utilizando o HTTP *status code*:`429 Too Many` `Requests`.

---

# Nível de Desempenho

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

---

# Nível de Serviço (SLA)

---
id: 17379052
title: Nível de Serviço (SLA)
version: 1
modified: 2022-10-28T19:35:18.944Z
url: /spaces/OF/pages/17379052/N+vel+de+Servi+o+SLA
---

O suporte eficaz da disponibilidade do Open Finance Brasil mantém níveis consistentes de serviços do sistema.As APIs “Produtos e Serviços”, “Canais de Atendimento”, “Consentimento”, “Dados Cadastrais”, “Cartão de Crédito”, “Contas” e “Operações de Crédito” deverão satisfazer requisitos mínimos de disponibilidade.Cada um de seus endpoints deverá estar disponível:
- I - 85% do tempo a cada 24 horas; e
- II - 95% do tempo a cada 1 mês; e
- III - 99,5% do tempo a cada 3 meses.

## Checagem de disponibilidade:
A disponibilidade é checada no *endpoint* `GET /discovery/status`, conforme documentada no item [API de Status](https://openbankingbrasil.atlassian.net/wiki/spaces/DraftOF/pages/1671948/APIs+Comuns+Discovery).A cada 30 segundos, a API de status é requisitada com *timeout* de 1s.
- Será considerado  uptime , se o retorno for: OK.
- Será considerado  downtime , se o retorno for: PARTIAL_FAILURE ; SCHEDULED_OUTAGE : Se a requisição for realizada entre o período de 01h e 07h, o contador de SCHEDULED_OUTAGE é iniciado com 30 segundos acrescidos; Cada nova requisição vai adicionando 30 segundos mais ao contador de SCHEDULED_OUTAGE, até que uma requisição volte outro valor ou a requisição for feita depois das 07h. UNAVAILABLE : Se a requisição for realizada entre o período de 07h e 01h; Se serviço não responder a requisição; O contador de  downtime  é iniciado com 30 segundos acrescidos; Cada nova requisição adicionará 30 segundos a mais ao contador de  downtime , até que uma requisição retorne OK.
O *downtime* deve ser calculado como o número total de segundos simultâneos por requisição da API, por período de 24 horas, começando e terminando à meia-noite, que qualquer *endpoint* da API não esteja disponível, dividido por 86.400 (total de segundos em 24 horas) e expresso como uma porcentagem.**A disponibilidade é calculada sendo 100% menos a quantidade em percentual da indisponibilidade.**
- De modo geral, consideram-se os erros 5XX HTTP  status codes  como erros do servidor, e portanto, atribuíveis ao servidor das APIs;
- Erros baseados em 4XX HTTP  status code  são, em grande parte, atribuídos à ações ou falhas dos receptores, e dessa forma, não devem ser incluídos no cálculo.
Não será considerado como *downtime*:
- Uma indisponibilidade por mês, por 3h entre 01h e 07h, desde que reportado com uma semana de antecedência ao diretório;
- Por tempo não definido, a qualquer momento e sem notificação em caso de resolução de problemas de segurança, desde que aprovado pelo Diretório. Neste caso, as instituições devem garantir o emprego dos melhores esforços para a resolução do problema