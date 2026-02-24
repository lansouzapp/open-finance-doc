---
id: 1275232257
title: Jornada Otimizada - DC
version: 1
modified: 2025-11-18T12:46:20.131Z
url: /spaces/OF/pages/1275232257/Jornada+Otimizada+-+DC
---

v 1.00
## Objetivo
Com o intuito de monitorar a Jornada Otimizada, faz-se necessária a inclusão de dois novos additionalInfo nos reportes da PCM, de forma a diferenciar consentimentos primários e secundários, e relacionar consentimentos vinculados.Para consultar os detalhes técnicos da implementação destes additilnalInfo, por favor consultar a página Documentação da API - PCM 
## journeyIsLinked

- Descrição: indica que o consentimento é vinculado a outro em uma Jornada Otimizada
- Dados Cadastrais e Transacionais ⁠ Regra de preenchimento: Deve ser preenchido com a string obtida no campo journey.isLinked, após a chamada inicial na API “POST /consents” se o parâmetro isLinked estiver preenchido na requisição no contexto de Jornada Otimizada. Exemplo: true  Roles: CLIENT  Métodos: POST e GET Http Code: Todos endpoints:  /open-banking/consents/v3/consents /open-banking/consents/v3/consents/{consentId}
**Exceções de reporte:** 
- Não deve ser reportado o campo journeyIsLinked ou journeyLinkId quando: O consentimento for criado fora do contexto de Jornada Otimizada, ou seja, quando não houver indicação de journey.isLinked=true no payload da criação do consentimento O consentimento for do tipo convencional (ex.: consents isolados, enrollments isolados, recurring-consents isolados), sem vínculo com outro consentimento
- Nestes casos, a transmissora/detentora deve omitir os campos journeyIsLinked e journeyLinkId no reporte à PCM