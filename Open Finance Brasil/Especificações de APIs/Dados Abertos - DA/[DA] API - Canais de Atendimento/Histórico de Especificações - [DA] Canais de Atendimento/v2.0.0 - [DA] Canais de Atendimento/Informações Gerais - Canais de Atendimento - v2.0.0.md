---
id: 297533461
title: Informações Gerais - Canais de Atendimento - v2.0.0
version: 3
modified: 2024-03-14T14:01:43.672Z
url: /spaces/OF/pages/297533461/Informa+es+Gerais+-+Canais+de+Atendimento+-+v2.0.0
---

22
## Prefixo:
- Prefixo dos endpoints: /channels/v2
## Dependências próprias : ( GET /channels/v2/branches)
Obtém a lista de dependências próprias da instituição financeira.Dependência própria é o espaço físico destinado ao atendimento ao público.
### Visão de alto nível das estruturas de dados

### Orientações de preenchimento​
Campo: data/identification/checkDigit​
- Em caso de ausência do dígito no campo `checkDigit` , o preenchimento deverá ser realizado com o valor zero (0).

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getBranches_v2.csv)
## Canais de atendimento eletrônico : (GET /channels/v2/electronic-channels)
Obtém a lista de canais eletrônicos próprios da instituição financeira.Esse *endpoint* retorna os possíveis canais de atendimento eletrônico, bem como suas informações, serviços prestados e formas de acesso.
### Visão de alto nível das estruturas de dados

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getElectronicChannels_v2.csv)
## Canais de atendimento telefônico : ( GET /channels/v2/phone-channels)
Obtém a lista de canais telefônicos próprios da instituição financeira.Esse *endpoint* retorna os possíveis canais de atendimento telefônico bem como suas informações, serviços prestados e formas de acesso.
### Visão de alto nível das estruturas de dados

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getPhoneChannels_v2.csv)
## Correspondentes Bancários : ( GET /channels/v2/banking-agents)
Obtém a lista de Correspondentes bancários.
### Visão de alto nível das estruturas de dados

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getBankingAgents_v2.csv)
## Terminais de autoatendimento compartilhados : ( GET /channels/v2/shared-automated-teller-machines)
Obtém a lista de terminais compartilhados de autoatendimento da instituição financeira.
### Visão de alto nível das estruturas de dados

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/getSharedAutomatedTellerMachines_v2.csv)