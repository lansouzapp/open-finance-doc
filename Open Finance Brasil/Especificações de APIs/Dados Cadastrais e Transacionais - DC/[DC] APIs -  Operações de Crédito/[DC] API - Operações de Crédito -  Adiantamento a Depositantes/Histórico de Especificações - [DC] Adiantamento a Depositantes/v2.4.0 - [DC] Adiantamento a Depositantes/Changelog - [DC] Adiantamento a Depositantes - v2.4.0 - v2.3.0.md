---
id: 784728535
title: Changelog - [DC] Adiantamento a Depositantes - v2.4.0 - v2.3.0
version: 2
modified: 2025-01-24T19:17:12.299Z
url: /spaces/OF/pages/784728535/Changelog+-+DC+Adiantamento+a+Depositantes+-+v2.4.0+-+v2.3.0
---

## GET /contracts/{contractId}

### Response

| Campo | O que foi alterado? | Tipo da Alteração | Antes | Depois |
| --- | --- | --- | --- | --- |
| get/responses/200/data/amortizationScheduledAdditionalInfo | Alterado - "pattern" | Alteração | ^(?!\s)[\w\W\s]*[^\s]$ | [\w\W\s]* |
| get/responses/200/data/instalmentPeriodicityAdditionalInfo | Alterado - "pattern" | Alteração | ^(?!\s)[\w\W\s]*[^\s]$ | [\w\W\s]* |