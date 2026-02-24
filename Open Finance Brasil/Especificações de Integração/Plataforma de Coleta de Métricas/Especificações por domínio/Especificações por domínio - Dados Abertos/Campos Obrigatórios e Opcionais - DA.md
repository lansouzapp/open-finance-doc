---
id: 1211334657
title: Campos Obrigatórios e Opcionais - DA
version: 2
modified: 2025-11-19T11:43:20.216Z
url: /spaces/OF/pages/1211334657/Campos+Obrigat+rios+e+Opcionais+-+DA
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Opendata API

| Campo | Definição | Obrigatório | Tipo | Métodos | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| additionalInfo | Informações adicionais sobre o reporte deste endpoint/método. Possui característica variável. As regras de preenchimento estão na documentação funcional em Regras de Obrigatoriedade (additionalInfo) - DA Caso não exista o campo enviar como um objeto vazio: {} | Sim | object | POST | | | | | | |
| endpoint | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar presente na lista de endpoints aceitos pela PCM para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original. | Sim | string | POST | Endpoints aceitos pela PCM | | | | | /open-banking/opendata-acquiring-services/v1/businesses |
| httpMethod | Método HTTP da solicitação. | Sim | string | POST | DELETE, GET, PATCH, POST, PUT | | | | | GET |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. | Sim | integer <int16> | POST | | | | | | 120 |
| statusCode | Status de retorno HTTP da solicitação. | Sim | integer <int32> | POST | | | 200 | 599 | | 200 |
| timestamp | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. | Sim | string <date-time> | POST | | 28 | | | YYYY-MM-DDTHH:mm:ss.sssZ | 2021-11-11T18:08:08.278Z |