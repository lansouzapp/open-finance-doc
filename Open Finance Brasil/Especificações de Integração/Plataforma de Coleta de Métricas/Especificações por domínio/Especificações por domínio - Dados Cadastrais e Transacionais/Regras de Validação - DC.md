---
id: 1212350465
title: Regras de Validação - DC
version: 3
modified: 2025-12-17T19:31:06.668Z
url: /spaces/OF/pages/1212350465/Regras+de+Valida+o+-+DC
---

v 1.01**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Dados Cadastrais e Transacionais

### Câmbio

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/exchanges/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Cartão de Crédito

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/credit-cards-accounts/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Consentimento

| Campo | Regra |
| --- | --- |
| companyProfileInfo | SE Role = CLIENT E personType = PJ ou PESSOA_JURIDICA E endpoint = %consents/v X /consents E método = POST ENTÃO Se naturezaJuridica e porteEmpresa forem simultaneamente nulos ou vazios, retorna Nulo/Vazio Se naturezaJuridica for nulo ou vazio e porteEmpresa estiver preenchido, retorna Incompleto - sem Natureza Juridica Se naturezaJuridica estiver preenchido e porteEmpresa estiver nulo ou vazio, retorna Incompleto - sem Porta da Empresa Se o porteEmpresa não for 00, 01, 03 ou 05, retorna Invalido |
| consentId | SE Role = CLIENT E endpoint = %/consents/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| dropReason | SE Role = SERVER E endpoint = %/consents/v x /consents ou %/payments/v x /consents E método = POST ENTÃO Se o dropReason for nulo, retorna Nulo Se o dropReason for vazio, retorna Vazio Se o dropReason não for NONE, NO_CREDENTIAL, NO_AUTHORITY ou NO_AUTHORITY_PERSON_MISMATCH retorna Invalido |
| personType | SE Role = CLIENT E endpoint = %/consents E método = POST ENTÃO Se o personType for nulo, retorna Nulo Se o personType for vazio, retorna Vazio Se o personType não for PF ou PJ retorna Invalido |
| status | SE Role = CLIENT E endpoint = %/consents/{consentId} E método = GET E statusCode não é 4xx, nem 5xx ENTÃO Se o status for nulo, retorna Nulo Se o status for vazio, retorna Vazio Se o status não for AWAITING_AUTHORISATION, AUTHORISED ou REJECTED retorna Invalido |

### Contas

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/accounts/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Dados Cadastrais

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/customers/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Investimentos

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/investments/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Operações de Crédito

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/unarranged-accounts-overdraft/%, %/invoice-financings/%, %/loans/% ou %/financings/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Recursos

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/ressources/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |