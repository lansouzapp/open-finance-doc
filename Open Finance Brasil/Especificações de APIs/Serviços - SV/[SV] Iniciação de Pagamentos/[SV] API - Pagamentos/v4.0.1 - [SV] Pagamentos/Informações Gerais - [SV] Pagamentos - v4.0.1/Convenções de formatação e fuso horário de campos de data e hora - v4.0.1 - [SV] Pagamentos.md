---
id: 1165623589
title: Convenções de formatação e fuso horário de campos de data e hora - v4.0.1 - [SV] Pagamentos
version: 1
modified: 2025-10-10T20:49:49.797Z
url: /spaces/OF/pages/1165623589/Conven+es+de+formata+o+e+fuso+hor+rio+de+campos+de+data+e+hora+-+v4.0.1+-+SV+Pagamentos
---

**Date**
Campos onde o tipo é string($date), o formato utilizado é AAAA-MM-DD.
Exemplo: 2022-12-01, esse formato é especificado pela RFC-3339.
Seu fuso horário atual é o horário de Brasília UTC-3.**DateTime**
Campos onde o tipo é string($date-time), o formato utilizado é AAAA-MM-DDTHH:MM:SSZ, onde T e Z são marcações, representando T a divisão entre data e horário e Z o timezone UTC. 
Exemplo: 2022-12-01T08:30:00Z, esse formato é especificado pela RFC-3339.
Seu fuso horário atual é o UTC.*Existem algumas inconsistências nas descrições de alguns campos no swagger da API de Serviços - Iniciação de Pagamentos, porém ao implementar leve em consideração as informações aqui registradas.*