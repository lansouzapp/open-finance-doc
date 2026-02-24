---
id: 164528744
title: Convenções de formatação e fuso horário de campos de data e hora - v3.1.0 - [SV] Pagamentos
version: 3
modified: 2023-12-06T16:50:53.622Z
url: /spaces/OF/pages/164528744/Conven+es+de+formata+o+e+fuso+hor+rio+de+campos+de+data+e+hora+-+v3.1.0+-+SV+Pagamentos
---

:warning:atlassian-warning#FFF0B3O conteúdo criado nessa página deve ser utilizado pelas instituições que forem participar do desenvolvimento do piloto da jornada sem redirecionamento. Caso a instituição não tenha se voluntariado a participar seguir com a implementação da versão 3.0.0.**Date**
Campos onde o tipo é string($date), o formato utilizado é AAAA-MM-DD.
Exemplo: 2022-12-01, esse formato é especificado pela RFC-3339.
Seu fuso horário atual é o horário de Brasília UTC-3.**DateTime**
Campos onde o tipo é string($date-time), o formato utilizado é AAAA-MM-DDTHH:MM:SSZ, onde T e Z são marcações, representando T a divisão entre data e horário e Z o timezone UTC. 
Exemplo: 2022-12-01T08:30:00Z, esse formato é especificado pela RFC-3339.
Seu fuso horário atual é o UTC.*Existem algumas inconsistências nas descrições de alguns campos no swagger da API de Serviços - Iniciação de Pagamentos, porém ao implementar leve em consideração as informações aqui registradas.*