---
id: 17369662
title: Informações Gerais - Consentimento - v2.0.0
version: 1
modified: 2022-10-27T12:02:26.157Z
url: /spaces/OF/pages/17369662/Informa+es+Gerais+-+Consentimento+-+v2.0.0
---

## Visão Geral
A API Consents viabiliza a criação, consulta e revogação dos consentimentos para a Fase 2 (customer-data) do [Open Finance Brasil](https://openfinancebrasil.org.br/).
## Criar novo pedido de consentimento : ( POST /consents/v2/consents)
Método para a criação de um novo consentimento.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsPostConsents_v2.csv)
## Obter detalhes do consentimento identificado por consentId : ( GET /consents/v2/consents/{consentId})
Método para obter detalhes do consentimento identificado por consentId.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsGetConsentsConsentId_v2.csv)
## Deletar / Revogar o consentimento identificado por consentId : ( DELETE /consents/v2/consents/{consentId})
Método para deletar / revogar o consentimento identificado por consentId.