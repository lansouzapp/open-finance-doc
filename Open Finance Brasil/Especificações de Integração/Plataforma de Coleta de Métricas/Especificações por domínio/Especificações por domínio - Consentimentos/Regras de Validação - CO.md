---
id: 1212153869
title: Regras de Validação - CO
version: 2
modified: 2026-02-09T18:16:02.687Z
url: /spaces/OF/pages/1212153869/Regras+de+Valida+o+-+CO
---

v 1.01**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Estoque de Consentimentos

| Campo | Regra |
| --- | --- |
| totalActiveConsents | A soma das quantidades de estoques únicos PF e PJ (totalCustomerPF e totalCustomerPJ) não pode ser superior à soma dos estoques ativos |
| Data do consentimento | Deve haver envio dário |
| clientOrgId | Deve ser uma organização válida dentro do ecossistema Open Finance, e em casos de conglomerados, não pode ser diferente da organização reportadora quando o role for CLIENT |
| serverOrgId | Deve ser uma organização válida dentro do ecossistema Open Finance, e em casos de conglomerados, não pode ser diferente da organização reportadora quando o role for SERVER |