---
id: 17379564
title: Changelog - [DC] Dados Cadastrais - v2.0.1
version: 4
modified: 2023-12-06T14:44:13.966Z
url: /spaces/OF/pages/17379564/Changelog+-+DC+Dados+Cadastrais+-+v2.0.1
---

GET /personal/identifications
| Campo | O que foi feito? |
| Header | Adicionado page |
| Header | Adicionado page-size |
| nationality/documents/country | Alterado pattern |
| otherDocuments | Alterada mandatoriedade Alterado minItems |
| otherDocuments/type | Removida opção ‘SEM_OUTROS_DOCUMENTOS’ do enum |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 504 |
GET /personal/qualifications
| Campo | O que foi feito? |
| Response code | Adicionado o status code 504 |
GET /personal/financial-relations
| Response code | Adicionado o status code 504 |
GET /business/identifications
| Campo | O que foi feito? |
| contacts/postalAddresses/districtName | Alterado pattern |
| contacts/postalAddresses/country | Alterado pattern |
| parties/documentCountry | Alterado pattern |
| otherDocuments | Alterada mandatoriedade Alterado minItems |
| Header | Adicionado pages |
| Header | Adicionado page-size |
| Response code | Adicionado o status code 422 |
| Response code | Adicionado o status code 504 |
GET /business/qualifications
| Campo | O que foi feito? |
| Response code | Adicionado o status code 504 |
GET /business/financial-relations
| Campo | O que foi feito? |
| Response code | Adicionado o status code 504 |