---
id: 17377105
title: Informações Gerais - API Comum - v1.0.2
version: 3
modified: 2023-12-19T20:28:12.252Z
url: /spaces/OF/pages/17377105/Informa+es+Gerais+-+API+Comum+-+v1.0.2
---

## API de status : (GET /discovery/v1/status)

### Visão geral
Obtém a descrição referente ao código de status retornado pelas APIs.
## API de outages : (GET /discovery/v1/outages)

### Visão geral
Obtêm a lista de indisponibilidade agendada para os serviços.
### Exemplo de código
Na estrutura de retorno exemplificada abaixo, no caso em que o parâmetro isPartial devolvido seja true, o array unavailableEndpoints deve conter a lista de endpoints indisponíveis: