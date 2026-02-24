---
id: 1212514305
title: Regras de Descarte - DA
version: 1
modified: 2025-11-18T12:36:33.737Z
url: /spaces/OF/pages/1212514305/Regras+de+Descarte+-+DA
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Opendata API

| Campo | Regra |
| --- | --- |
| endpoint | Informação não enviada Invalid type: endpoint: Required: campo endpoint ausente Conteúdo inválido Validation error:{endpoint incorreto}: conteúdo do campo endpoint inválido Missing property, endpoint can't be empty: campo endpoint não pode estar vazio Unlisted endpoint: endpoint: endpoint must be listed: endpoint enviado não é válido (consultar a tabela de endpoints aceitos pela PCM) |
| httpMethod | Informação não enviada Invalid type: httpMethod: Required: campo httpMethod ausente Conteúdo inválido Invalid field value, httpMethod: httpMethod must be in enum: conteúdo do campo httpMethod inválido Invalid value: httpMethod: Invalid enum value. Expected ‘GET' | 'POST' | 'PUT' | 'PATCH' | 'DELETE', received 'xxxx’: conteúdo do campo httpMethod inválido, recebido conteúdo não determinado no enum do campo Missing property, httpMethod can't be empty: conteúdo do campo httpMethod não pode estar vazio |
| processTimespan | Informação não enviada Invalid type: processTimespan: Required: campo processTimespan ausente Conteúdo inválido Invalid field value, processTimespan: process timespan must be a positive number: campo timestamp deve se um número positivo Invalid type: processTimespan: Expected number, received 'xxxx': conteúdo do campo processTimespan inválido; esperado número Invalid value: processTimespan must be greater than zero: campo timestamp deve ser maior do que zero |
| statusCode | Informação não enviada Invalid type: statusCode: Required: campo statusCode ausente Conteúdo inválido Invalid type: statusCode: Expected number, received ‘xxxx’: conteúdo do campo statusCode inválido; esperado número Invalid value: statusCode must be between 200 and 599: campo statusCode com valor inválido, deve estar entre 200 e 599 |
| timestamp | Conteúdo inválido Timestamp is older than 7 days: campo timestamp com data posterior a 7 dias Validation error: Invalid timestamp format: formato do campo timestamp inválido Validation error: Report is too old: campo timestamp com data posterior a 7 dias |