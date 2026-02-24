---
id: 1212088361
title: Regras de Validação - DA
version: 1
modified: 2025-11-18T12:35:58.755Z
url: /spaces/OF/pages/1212088361/Regras+de+Valida+o+-+DA
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Dados Abertos

| Campo | Regra |
| --- | --- |
| clientIp | SE Role = CLIENT E endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, %/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/% , %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o clientIp for nulo, retorna Nulo Se o clientIp for vazio, retorna Vazio |
| endpoint | Se o endpoint for nulo, retorna Nulo Se o endpoint for vazio, retorna Vazio |
| httpMethod | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o httpMethod for nulo, retorna Nulo Se o httpMethod for vazio, retorna Vazio |
| processTimespan | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o processTimespan for nulo, retorna Nulo Se o processTimespan for vazio, retorna Vazio |
| statusCode | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o statusCode for nulo, retorna Nulo Se o statusCode for vazio, retorna Vazio |
| timestamp | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o timestamp for nulo, retorna Nulo Se o timestamp for vazio, retorna Vazio |