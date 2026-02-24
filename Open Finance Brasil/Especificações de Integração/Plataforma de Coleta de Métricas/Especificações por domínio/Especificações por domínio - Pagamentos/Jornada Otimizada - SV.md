---
id: 1275625473
title: Jornada Otimizada - SV
version: 1
modified: 2025-11-18T12:54:10.836Z
url: /spaces/OF/pages/1275625473/Jornada+Otimizada+-+SV
---

v 1.00
## Objetivo
Com o intuito de monitorar a Jornada Otimizada, faz-se necessária a inclusão de dois novos additionalInfo nos reportes da PCM, de forma a diferenciar consentimentos primários e secundários, e relacionar consentimentos vinculados.Para consultar os detalhes técnicos da implementação destes additilnalInfo, por favor consultar a página Documentação da API - PCM 
## journeyIsLinked

- Descrição: indica que o consentimento é vinculado a outro em uma Jornada Otimizada
- Jornada Sem Redirecionamento (JSR) ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.isLinked”, retornado após a chamada inicial na API “POST /enrollments” em caso de Jornada Otimizada. Exemplo: true  Roles: CLIENT  Métodos: POST e GET Http Code: Todos endpoints:  /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId}

- PIX Automático ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.i sLinked”, retornado após a chamada inicial na API “POST /consent” em caso de Jornada Otimizada. Exemplo: true  Roles: CLIENT  Métodos: POST e GET Http Code: Todos menos 4xx e 5xx no POST endpoints:  /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}

## journeyLinkId

- Descrição: Identifica o consentimento de dados vinculado a uma Jornada Otimizada.
- Jornada Sem Redirecionamento (JSR) ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.linkId”, retornado após a chamada inicial na API “POST /enrollments” em caso de Jornada Otimizada. Roles: CLIENT  Métodos: POST e GET Http Code: Todos endpoints:  /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId}

- PIX Automático ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.li nkId”, retornado após a chamada inicial na API “POST /consent” em caso de Jornada Otimizada. Roles: CLIENT  Métodos: POST e GET Http Code: Todos menos 4xx e 5xx no POST endpoints:  /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}
**Exceções de reporte:** 
- Não deve ser reportado o campo journeyIsLinked ou journeyLinkId quando: O consentimento for criado fora do contexto de Jornada Otimizada, ou seja, quando não houver indicação de journey.isLinked=true no payload da criação do consentimento O consentimento for do tipo convencional (ex.: consents isolados, enrollments isolados, recurring-consents isolados), sem vínculo com outro consentimento
- Nestes casos, a transmissora/detentora deve omitir os campos journeyIsLinked e journeyLinkId no reporte à PCM