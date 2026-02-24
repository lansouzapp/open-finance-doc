---
id: 156434552
title: Informações Gerais - API Comum -  v2.0.0-beta.1
version: 5
modified: 2023-12-19T20:28:32.944Z
url: /spaces/OF/pages/156434552/Informa+es+Gerais+-+API+Comum+-+v2.0.0-beta.1
---

### Contexto:
Conforme IN nº [306 de 19/02/2022](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=306), o Item 2 do Anexo lista todas as APIs integrantes do Open Finance. Dentre elas, as APIs de Status, de Outages e Métricas são comuns a todos os participantes do Open Finance Brasil, independentemente da fase de adesão.
| Relatórios e Métricas | Situação do Ambiente | Deve dar acesso a dados sobre a disponibilidade atual das implementações das APIs, bem como a dados sobre indisponibilidades programadas. |
| Métricas | Deve dar acesso a dados de performance de todas as APIs disponibilizadas. |
Sendo assim: 
1. Todas as instituições devem publicar essas APIs que monitoram a situação do ambiente;
2. APIs comuns devem reportar os dados de disponibilidade e indisponibilidade programada de todas as APIs que a instituição oferece;
3. APIs comuns devem ser atualizadas conforme lançamento de novas APIs pela instituição ou atualização das APIs já existentes.

## API de status: (GET /discovery/v1/status)

### Visão geral
A instituição deve disponibilizar o código de status de todas as suas APIs nesse endpoint
### Visão de alto nível das estruturas de dados

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getStatus_v2.csv)
## API de outages: (GET /discovery/v1/outages)

### Visão geral
A instituição deve disponibilizar previamente a previsão de indisponibilidade agendada dos seus serviços através desse endpoint.
### Visão de alto nível das estruturas de dados

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getOutage_v2.csv)
### Exemplo de código
Na estrutura de retorno exemplificada abaixo, no caso em que o parâmetro isPartial devolvido seja true, o array unavailableEndpoints deve conter a lista de endpoints indisponíveis:",
 "first": "https://api.banco.com.br/open-banking/channels/v1/",
 "prev": "https://api.banco.com.br/open-banking/channels/v1/",
 "next": "https://api.banco.com.br/open-banking/channels/v1/",
 "last": "https://api.banco.com.br/open-banking/channels/v1/"
 },
 "meta": {
 "totalRecords": 1,
 "totalPages": 1
 }
}]]>