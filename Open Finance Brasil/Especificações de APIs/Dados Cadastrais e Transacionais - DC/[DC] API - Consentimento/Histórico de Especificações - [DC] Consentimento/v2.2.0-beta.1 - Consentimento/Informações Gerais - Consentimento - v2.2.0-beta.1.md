---
id: 175833211
title: Informações Gerais - Consentimento - v2.2.0-beta.1
version: 3
modified: 2023-09-18T23:12:16.029Z
url: /spaces/OF/pages/175833211/Informa+es+Gerais+-+Consentimento+-+v2.2.0-beta.1
---

## Visão Geral
A API Consents viabiliza a criação, consulta e revogação dos consentimentos para a dados cadastrais e transacionais. (customer-data) do [Open Finance Brasil](https://openfinancebrasil.org.br/).
## Criar novo pedido de consentimento : ( POST /consents/v2/consents)
Método para a criação de um novo consentimento.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsPostConsents_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/101482514/consents.csv?version=2&amp;modificationDate=1683665990545&amp;cacheVersion=1&amp;api=v2&download=true)
## Obter detalhes do consentimento identificado por consentId : ( GET /consents/v2/consents/{consentId})
Método para obter detalhes do consentimento identificado por consentId.**Dicionário de dados**[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/consentsGetConsentsConsentId_v2.csv)[Fazer download dos exemplos](https://openfinancebrasil.atlassian.net/wiki/download/attachments/101482514/consents_consentId.csv?api=v2&download=true)
## Deletar / Revogar o consentimento identificado por consentId : ( DELETE /consents/v2/consents/{consentId})
Método para deletar / revogar o consentimento identificado por consentId.