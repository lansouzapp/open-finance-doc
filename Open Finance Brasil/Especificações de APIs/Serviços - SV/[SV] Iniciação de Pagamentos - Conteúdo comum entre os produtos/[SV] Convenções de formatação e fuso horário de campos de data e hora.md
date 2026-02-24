---
id: 728301690
title: [SV] Convenções de formatação e fuso horário de campos de data e hora
version: 2
modified: 2024-12-06T19:27:36.345Z
url: /spaces/OF/pages/728301690/SV+Conven+es+de+formata+o+e+fuso+hor+rio+de+campos+de+data+e+hora
---

**Date**
Campos onde o tipo é string($date), o formato utilizado é AAAA-MM-DD.
Exemplo: 2022-12-01, esse formato é especificado pela RFC-3339.
Seu fuso horário atual é o horário de Brasília UTC-3.**DateTime**
Campos onde o tipo é string($date-time), o formato utilizado é AAAA-MM-DDTHH:MM:SSZ, onde T e Z são marcações, representando T a divisão entre data e horário e Z o timezone UTC. 
Exemplo: 2022-12-01T08:30:00Z, esse formato é especificado pela RFC-3339.
Seu fuso horário atual é o UTC.*Existem algumas diferenças nos formatos de alguns campos nas especificações das APIs de Serviços, porém, ao implementar, leve em consideração as informações aqui registradas. Divergências serão corrigidas em momento oportuno.*