---
id: 887914521
title: Informações Gerais - [DC] Dados Cadastrais -  v2.2.1
version: 5
modified: 2025-03-24T21:13:16.091Z
url: /spaces/OF/pages/887914521/Informa+es+Gerais+-+DC+Dados+Cadastrais+-+v2.2.1
---

22
## Visão geral
A API Customers permite a consulta aos dados cadastrais de clientes, incluindo também dados de qualificação e de relacionamento financeiro.
## Identificação pessoa natural : ( GET /customers/v2/personal/identifications)
Obtém os registros de identificação da pessoa natural.Esta especificação inclui todos os itens relevantes que permitam a ação e o efeito de identificar de forma única a pessoa natural através de seus dados cadastrais.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalIdentifications_v2.2.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_customersGetPersonalIdentifications_v2.csv)
## Identificação pessoa jurídica : ( GET /customers/v2/business/identifications)
Obtém os registros de identificação da pessoa jurídica.Esta especificação inclui todos os itens relevantes que permitam a ação e o efeito de identificar de forma única a pessoa jurídica através de seus dados cadastrais.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessIdentifications_v2.2.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_customersGetBusinessIdentifications_v2.csv)
## Qualificação pessoa natural : ( GET /customers/v2/personal/qualifications)
Obtém os registros de qualificação da pessoa natural.Esta especificação inclui todos os itens relevantes, que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalQualifications_v2.2.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_customersGetPersonalQualifications_v2.csv)
## Qualificação pessoa jurídica : ( GET /customers/v2/business/qualifications)
Obtém os registros de qualificação da pessoa jurídica.Esta especificação inclui todos os itens relevantes, que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessQualifications_v2.2.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_customersGetBusinessQualifications_v2.csv)
## Relacionamento pessoa natural : ( GET /customers/v2/personal/financial-relations)
Obtém os registros de relacionamentos com a instituição financeira e de representantes da pessoa natural.Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente.
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetPersonalFinancialRelations_v2.2.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_customersGetPersonalFinancialRelations_v2.csv)
## Relacionamento pessoa jurídica : ( GET /customers/v2/business/financial-relations)
Obtém os registros de relacionamentos com a instituição financeira e de representantes da pessoa jurídica.Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente
### Visão de alto nível das estruturas de dados

### DER - Diagramas de Entidade e Relacionamento

- DER Conceitual

- DER Lógico

### Dicionário de dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/openapi/dictionary/customersGetBusinessFinancialRelations_v2.2.1.csv)[Fazer download dos exemplos](https://openbanking-brasil.github.io/openapi/dictionary/example/examples_customersGetBusinessFinancialRelations_v2.csv)
## Tabela descritiva das possibilidades de retorno para a API Dados Cadastrais

| Cenário ​ | API Dados Cadastrais ​ | Code ​ |
| --- | --- | --- |
| Sem consentimento​ | 401 UNAUTHORIZED​ | -​ |
| Com consentimento recusado (REJECTED)​ | 401 UNAUTHORIZED​ | -​ |
| Com consentimento autorizado (pendente múltipla alçada)​ | 403 FORBIDDEN​ | STATUS_PENDING_ AUTHORISATION​ |
| Com consentimento autorizado (aprovado múltipla alçada)​ | 200 Retorna dados​ | -​ |
| Com consentimento autorizado (aprovado múltipla alçada) – cliente com bloqueio temporário​ | 403 FORBIDDEN​ | STATUS_TEMPORARY_ UNAVAILABLE​ |
| Com consentimento autorizado (aprovado múltipla alçada) - cliente encerrou relacionamento​ | 403 FORBIDDEN​ | STATUS_UNAVAILABLE​ |
| Com consentimento autorizado (recusado múltipla alçada)​ | 403 FORBIDDEN​ | STATUS_UNAVAILABLE​ |
| Com consentimento revogado ou expirado​ | 401 UNAUTHORIZED​ | -​ |