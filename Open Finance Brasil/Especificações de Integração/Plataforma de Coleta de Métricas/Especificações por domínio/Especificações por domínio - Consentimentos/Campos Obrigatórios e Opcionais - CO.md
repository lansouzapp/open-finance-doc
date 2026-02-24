---
id: 1211858957
title: Campos Obrigatórios e Opcionais - CO
version: 2
modified: 2025-11-19T12:05:35.186Z
url: /spaces/OF/pages/1211858957/Campos+Obrigat+rios+e+Opcionais+-+CO
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Consents API

| Campo | Definição | Obrigatório | Tipo | Regra de preenchimento | Métodos | Domínio | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| date | Data UTC no formato ISO8601 (YYYY-MM-DD) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. Deve conter a data a que se referem os dados de consentimento enviados na mensagem | Sim | string <date-time> | | POST | | 10 | YYYY-MM-DD | 2021-11-11 |
| orgId | Organização de envio da mensagem referente ao papel do Transmissor ou Receptor, conforme Role, a ser preenchido a partir do Certificado | Sim | string <uuid> | | POST | | 36 | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| role | Indica se o reporte que está sendo enviado apresenta a visão do SERVER ou do CLIENT | Sim | enum<string> | | POST | CLIENT, SERVER | | | CLIENT |
| scope | Escopo do reporte | Sim | enum<string> | | POST | DADOS | | | DADOS |
| totalCustomerPF | Total de clientes PF com consentimentos ativos | Não | number | | POST | | | | 50 |
| totalCustomerPJ | Total de clientes PJ com consentimentos ativos | Não | number | | POST | | | | 100 |
| consentsStockList | Lista de estoque de consentimentos. Caso não haja estoque a reportar, enviar o array vazio. Os itens indentados abaixo pertencem ao objeto consentsStockList e seguem as mesmas regras de obrigatoriedade | Sim | array [object {3}] | | POST | | | | |
| clientOrgId | Identificador da organização de onde a chamada foi disparada | Não | string <uuid> | | POST | | 36 | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| serverOrgId | Identificador da organização para onde a chamada foi feita | Não | string <uuid> | | POST | | 36 | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| totalActiveConsents | Estoque total de consentimentos ativos, correspondendo ao número de consentimentos totais válidos até a data de referência. | Não | number | | POST | | | | 30 |