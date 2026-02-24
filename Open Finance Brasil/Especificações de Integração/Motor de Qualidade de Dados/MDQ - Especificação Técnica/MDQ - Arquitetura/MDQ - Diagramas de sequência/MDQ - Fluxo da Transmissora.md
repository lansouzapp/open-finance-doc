---
id: 362578850
title: MDQ - Fluxo da Transmissora
version: 4
modified: 2025-03-27T12:01:11.074Z
url: /spaces/OF/pages/362578850/MDQ+-+Fluxo+da+Transmissora
---

Este fluxo representa o processo de enfileramento de messagens e integração com o MQD na visão da TRANSMISSORA.
## Passos

| Passo | Participante | Descrição |
| --- | --- | --- |
| 1. | SERVICE | O serviço gera uma solicitação para a API da TRANSMISORA |
| 2. | API | A API processa a solicitação recebida |
| 3. | API | A API retorna um resultado para a solicitação |
| 4. | API | A API atualiza a solicitação, incluindo a resposta enviada para a RECEPTORA - Corpo+Cabeçalho - e adicionando oa parâmetros clientOrgID (clientOrgID: OrganisationID (cadastrado no Diretório Central) da Receptora que esta solicitando a informação, este campo deve ser incluso como parte de cabeçalho) - o ID da RECEPTORA - e endpointName ao cabeçalho (enviar somente validações de solicitações bem-sucedidas - 2xx) |
| 5. | API | A API da TRANSMISSORA envia a nova resposta válida para o MQD |
| 6. | MQD | MQD Valida se as informações do cabeçalho estão completas e corretas |
| 7. | MQD | MQD encaminha as informações para serem processadas posteriormente |
| 8. | MQD | MQD responde OK se o processo foi bem-sucedido |

### Exemplo de Soliciação da API - MQD

| endpointName | serverOrgId | x-fapi-interaction-id | Corpo |
| --- | --- | --- | --- |
| /loans/v2/contracts/{contractId}/payments Nome do endpoint e deve corresponder à lista de endpoints aceitos | c73bcdcc-2669-4bf6-81d3-e4ae73fb11fd Id da TRANSMISORA | 241e202-e8f0-5f5a-9651-ebc257371e24 valor x-fapi usado durante a transação | Valor retornado como resposta da TRANSMISORA |