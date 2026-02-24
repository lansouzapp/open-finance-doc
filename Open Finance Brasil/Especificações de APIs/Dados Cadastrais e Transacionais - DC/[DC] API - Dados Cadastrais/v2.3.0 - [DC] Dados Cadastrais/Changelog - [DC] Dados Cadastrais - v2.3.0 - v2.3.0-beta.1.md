---
id: 1528823973
title: Changelog - [DC] Dados Cadastrais - v2.3.0 - v2.3.0-beta.1
version: 2
modified: 2026-02-09T17:28:15.338Z
url: /spaces/OF/pages/1528823973/Changelog+-+DC+Dados+Cadastrais+-+v2.3.0+-+v2.3.0-beta.1
---

16falsenonelisttrue
## GET /personal/qualifications

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/occupationDescription | Alterado - "description" | Alteração | Campo livre, de preenchimento obrigatório. Se selecionada a opção *occupationCode* "RECEITA_FEDERAL" ou "CBO", informar o código d... | Campo de livre preenchimento para informar o código da ocupação ou um descritivo da ocupação. Ao preencher o campo atentar para o ... |
| get/responses/200/data/employerCnpjCpf | Removido - "employerCnpjCpf" | Remoção | | |
| get/responses/200/data/employerName | Removido - "employerName" | Remoção | | |
| get/responses/200/data/employers | Adicionado - "employers" | Adição | | |
| get/responses/200/data/employers/cnpjCpf | Adicionado - "cnpjCpf" | Adição | | |
| get/responses/200/data/employers/name | Adicionado - "name" | Adição | | |