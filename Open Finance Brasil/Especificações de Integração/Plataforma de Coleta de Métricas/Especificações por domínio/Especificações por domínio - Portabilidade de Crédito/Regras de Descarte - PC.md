---
id: 1213136897
title: Regras de Descarte - PC
version: 1
modified: 2025-11-18T13:04:23.010Z
url: /spaces/OF/pages/1213136897/Regras+de+Descarte+-+PC
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.
# Credit Portability API

| Campo | Regra |
| --- | --- |
| clientOrgId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| clientSSId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID para ser considerado válido |
| creationDateTime | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato datetime para ser considerado válido |
| endpoint | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve ser um endpoint ingerido pela PCM para ser considerado válido |
| endpointUriPrefix | Deve ter no máximo 200 caracteres alfanuméricos para ser considerado válido |
| fapiInteractionId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| httpMethod | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve pertencer ao domínio do campo para ser considerado válido |
| processTimespan | Deve ser enviado no payload (não deve estar ausente) |
| role | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve pertencer ao domínio do campo para ser considerado válido |
| serverOrgId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| statusCode | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve ser um valor entre 200 e 599 para ser considerado válido |
| statusUpdateDateTime | Deve estar no formato datetime para ser considerado válido |
| timestamp | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato datetime e não ser inferior a 10 dias da data de recebimento para ser considerado válido |