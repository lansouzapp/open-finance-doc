---
id: 362578884
title: MDQ - Fluxo da Receptora
version: 4
modified: 2025-03-27T12:01:22.225Z
url: /spaces/OF/pages/362578884/MDQ+-+Fluxo+da+Receptora
---

Este fluxo representa o processo de enfileramento de messagens e integração com o MQD na visão da RECEPTORA.
## Passos

| Passo | Participante | Descrição |
| --- | --- | --- |
| 1. | SERVICE | O serviço gera uma solicitação para a API da TRANSMISORA |
| 2. | API | A API processa a solicitação recebida |
| 3. | API | A API retorna um resultado para a solicitação |
| 4. | SERVICE | O Serviço gera uma nova requisição, tendo como base a Resposta da TRANSMISORA, incluindo no cabeçalho o valor de [EndpointName] e [serverOrgId] que indica o ID do transmissor (enviar somente validações de solicitações bem-sucedidas - 2xx) |
| 5. | SERVICE | O serviço envia a nova solicitação para a API do MQD |
| 6. | MQD | MQD Valida se as informações do cabeçalho estão completas e corretas |
| 7. | MQD | MQD encaminha as informações para serem processadas posteriormente |
| 8. | MQD | MQD responde OK se o processo foi bem-sucedido |

### Exemplo de Soliciação da API - MQD

| endpointName | serverOrgId | x-fapi-interaction-id | Corpo |
| --- | --- | --- | --- |
| /loans/v2/contracts/{contractId}/payments Nome do endpoint e deve corresponder à lista de endpoints aceitos | c73bcdcc-2669-4bf6-81d3-e4ae73fb11fd Id da TRANSMISORA | 241e202-e8f0-5f5a-9651-ebc257371e24 valor x-fapi usado durante a transação | Valor retornado como resposta da TRANSMISORA |