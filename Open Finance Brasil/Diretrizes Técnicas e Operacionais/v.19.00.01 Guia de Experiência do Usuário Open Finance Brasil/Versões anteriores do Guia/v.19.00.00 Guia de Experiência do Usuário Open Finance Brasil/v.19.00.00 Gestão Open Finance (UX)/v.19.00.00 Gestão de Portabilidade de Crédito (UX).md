---
id: 1436289418
title: v.19.00.00 Gestão de Portabilidade de Crédito (UX)
version: 1
modified: 2026-01-12T19:25:35.718Z
url: /spaces/OF/pages/1436289418/v.19.00.00+Gest+o+de+Portabilidade+de+Cr+dito+UX
---

As instituições participantes da jornada de Portabilidade de Crédito — Instituição Proponente (IP) e Instituição Credora (IC) — devem disponibilizar ao usuário, por meio de uma Área de Gestão, a listagem de todos os pedidos realizados, com o tipo de produto, seus respectivos status e informações detalhadas, respeitando o contexto da jornada (síncrona ou assíncrona) e os prazos de exibição definidos para cada situação. As instituições também devem permitir que o usuário cancele uma portabilidade que esteja em andamento a qualquer momento antes da fase de liquidação e devem comunicar o cancelamento à outra instituição.#F4F5F7
## Requisitos - IP e IC
**Cenário: Consulta aos pedidos**
1. Exibição de pedidos de Portabilidade de Crédito : Exibir a lista de pedidos de Portabilidade de Crédito com seus respectivos status individuais. Ex.: Em análise, Portabilidade em andamento, etc. Identificação do tipo de contrato : Indicar o tipo de contrato associado a cada pedido. Ex. Consignado Federal ou CPC.
2. Exibição de dados de proposta e contraproposta : Exibir os dados da proposta e contraproposta conforme descrito no cenário de Apresentação da Proposta .

### Área de Gestão da Instituição Proponente (IP)
Portabilidade de Crédito - Instituição Proponente (IP) 
### Área de Gestão da Instituição Credora (IC)
 Portabilidade de Crédito - Instituição Credora (IC)As tabelas a seguir apresentam os status que cada instituição, quando aplicável, deve exibir, os motivos para cada status, os dados a serem exibidos, o prazo de exibição e o possível próximo status, a fim de garantir melhor entendimento da jornada.
| Instituição Proponente (IP) |
| --- |
| Status | Motivo | O que exibir | Prazo de exibição | Próximo status |
| Em análise (Requisito para jornada assíncrona) | Pedido de Portabilidade de Crédito em análise | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | Até a análise ser concluída, conforme informado pela Proponente | Proposta disponível  Sem proposta |
| Proposta disponível (Requisito) | Proposta recebida, aguardando resposta do usuário | Comparativo entre proposta e contrato original | No mínimo 2 dias, conforme legislação e regulação vigente | Em andamento (caso a proposta seja aceita e o contrato seja assinado)  Cancelada (em caso de recusa ou expiração) |
| Sem proposta (Requisito para jornada assíncrona) | Nenhuma proposta disponível para o pedido de Portabilidade de Crédito | Dados do contrato original (opcional): Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | A ser definido pela Proponente | N/A |
| Portabilidade em andamento (Requisito) | Proposta aceita pelo usuário | Comparativo entre proposta aceita e contrato original | Até o cancelamento ou conclusão da portabilidade | Concluída  Cancelada (se cancelada pelo usuário antes da fase de liquidação ou pela Proponente) |
| Portabilidade concluída (Requisito) | Portabilidade de Crédito finalizada com sucesso | Comparativo entre proposta aceita e contrato original | 14 dias corridos após o status final, e depois pode mover para Área de Gestão de Crédito da IF | N/A |
| Portabilidade cancelada (Requisito) | Proposta recusada  Proposta expirada | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito) | Usuário cancelou a portabilidade  Proponente cancelou a portabilidade | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito quando aplicável) | Contraproposta aceita | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |

| Instituição Credora (IC) |
| --- |
| Status | Motivo | O que exibir | Prazo de exibição | Próximo status |
| Portabilidade em andamento (Requisito) | Proposta aceita pelo usuário | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | Até o cancelamento ou conclusão da portabilidade | Concluída  Cancelada (se contraproposta for aceita, ou se portabilidade for cancelada pelo usuário antes da fase de liquidação ou pela Proponente) |
| Portabilidade em andamento (Requisito quando aplicável) | Contraproposta recusada  Contraproposta expirada | Comparativo entre contraproposta e proposta da Proponente | Até o cancelamento ou conclusão da portabilidade | Em andamento |
| Portabilidade concluída (Requisito) | Portabilidade de Crédito finalizada com sucesso | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito) | Usuário cancelou a portabilidade  Proponente cancelou a portabilidade | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito quando aplicável) | Contraproposta aceita | Comparativo entre contraproposta aceita e proposta da Proponente | 14 dias corridos após o status final, e depois pode mover para Área de Gestão de Crédito da IF | N/A |
#F4F5F7
## Requisitos - IP
**Cenário: Pedido em análise**Para pedidos que estejam em análise, nos casos de jornada assíncrona, a Proponente deve:   
1. Prazo de análise: Informar prazo estimado para finalização da análise do pedido.
Portabilidade de Crédito - Pedido em análise #F4F5F7
## Requisitos - IP e IC
**Cenário: Portabilidade em andamento**Para pedidos de portabilidade em andamento, a instituição deve:  
1. Desistência da portabilidade: Permitir desistência da Portabilidade de Crédito antes da liquidação. Informar que o usuário pode desistir da portabilidade antes da fase da liquidação. Caso a portabilidade entre em fase de liquidação, desabilitar a opção de cancelamento do pedido.
Portabilidade de Crédito - Portabilidade em andamento #F4F5F7
## Requisitos - IP
**Cenário: Portabilidade em andamento**Para pedidos de portabilidade em andamento, a Proponente deve:  
1. Download do contrato assinado: Possibilitar que o usuário baixe o contrato assinado da proposta.
Portabilidade de Crédito - Portabilidade em andamento **Cenário: Portabilidade concluída**Para pedidos cuja portabilidade tenha sido efetivada, a Proponente deve:  
1. Download do contrato assinado: Possibilitar que o usuário baixe o contrato assinado da proposta.
Portabilidade de Crédito - Portabilidade concluída #F4F5F7
## Recomendações - IP
**Cenário: Sem oferta disponível**Para pedidos para os quais não há proposta, a Proponente pode:
1. Novo pedido: Possibilitar que o usuário faça um novo pedido de Portabilidade de Crédito.
Portabilidade de crédito - Sem oferta disponível **Cenário: Portabilidade cancelada**Para pedidos de portabilidade que tenham sido cancelados pelo usuário ou pela Proponente, a instituição pode:  
1. Novo pedido: Possibilitar que o usuário faça um novo pedido de Portabilidade de Crédito.
Portabilidade de Crédito - Portabilidade cancelada