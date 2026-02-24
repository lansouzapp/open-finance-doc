---
id: 17369589
title: Informações Gerais - Consentimento - v1.0.3
version: 2
modified: 2022-10-27T18:05:16.605Z
url: /spaces/OF/pages/17369589/Informa+es+Gerais+-+Consentimento+-+v1.0.3
---

## Visão Geral
A API Consents viabiliza a criação, consulta e revogação dos consentimentos para a Fase 2 (customer-data) do [Open Finance Brasil](https://openfinancebrasil.org.br/).
## Criar novo pedido de consentimento : ( POST /consents/v1/consents)
Método para a criação de um novo consentimento.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsPostConsents_v1.csv)
## Obter detalhes do consentimento identificado por consentId : ( GET /consents/v1/consents/{consentId})
Método para obter detalhes do consentimento identificado por consentId.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsGetConsentsConsentId_v1.csv)
## Deletar / Revogar o consentimento identificado por consentId : ( DELETE /consents/v1/consents/{consentId})
Método para deletar / revogar o consentimento identificado por consentId.