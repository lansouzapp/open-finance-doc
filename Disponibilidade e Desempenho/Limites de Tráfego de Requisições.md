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