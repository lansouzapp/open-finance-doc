---
id: 950861965
title: Idempotência - v1.0.0-beta.2
version: 1
modified: 2025-05-09T11:56:17.427Z
url: /spaces/OF/pages/950861965/Idempot+ncia+-+v1.0.0-beta.2
---

- APIs que implementam o conceito de idempotência oferecem maior confiabilidade ao processo e mitigam problemas de inconsistência de informações ou duplicidade de registros. No entanto, aumentam a complexidade da implementação, tornando essencial sua consideração desde a etapa de arquitetura e design do sistema até a codificação.
- Na portabilidade de crédito, existem dois fluxos distintos: a solicitação via Open Finance Brasil (OFB) e via Registradora. Conforme especificado no PRD, o processo de portabilidade ocorre por meio de fluxos assíncronos, com espaçamentos de dias úteis. Isso permite que a Instituição Credora identifique solicitações duplicadas e mantenha o registro mais antigo, alinhado ao escopo regulatório e à gestão de simultaneidade.