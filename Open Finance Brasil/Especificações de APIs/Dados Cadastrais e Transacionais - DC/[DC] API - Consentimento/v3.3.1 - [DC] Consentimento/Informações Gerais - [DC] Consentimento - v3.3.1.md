---
id: 1378385938
title: Informações Gerais - [DC] Consentimento - v3.3.1
version: 2
modified: 2025-12-15T17:07:30.878Z
url: /spaces/OF/pages/1378385938/Informa+es+Gerais+-+DC+Consentimento+-+v3.3.1
---

## Operações para criação, consulta, renovação e revogação do consentimento dado pelo cliente

## Visão Geral
A API Consents viabiliza a criação, consulta e revogação dos consentimentos para a dados do cliente (customer-data) do [Open Finance Brasil](https://openfinancebrasil.org.br/).
## Criar novo pedido de consentimento : ( POST /consents/v3/consents)
Método para a criação de um novo consentimento.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsPostConsents_v3.3.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_consentsPostConsents_v3.3.1.csv)
## Obter detalhes do consentimento identificado por consentId : ( GET /consents/v3/consents/{consentId})
Método para obter detalhes do consentimento identificado por consentId.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsGetConsentsConsentId_v3.3.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_consentsGetConsentsConsentId_v3.3.1.csv)
## Deletar / Revogar o consentimento identificado por consentId : ( DELETE /consents/v3/consents/{consentId})
Método para deletar / revogar o consentimento identificado por consentId.
## Obter detalhes de extensões feitas no consentimento identificado por consentId: (GET /consents/{consentId}/extensions)
Método para obter detalhes de extensões consentimento identificado por consentId.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsGetConsentsConsentIdExtensions_v3.3.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_consentsGetConsentsConsentIdExtensions_v3.3.1.csv)
## Renovar consentimento identificado por consentId: (POST /consents/{consentId}/extends)
Método para renovar consentimento identificado por consentId, exceto casos com múltiplas alçadas. Nos casos de múltiplas alçadas, a transmissora deve retornar o status 422.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsPostConsentsConsentIdExtends_v3.3.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_consentsPostConsentsConsentIdExtends_v3.3.1.csv)