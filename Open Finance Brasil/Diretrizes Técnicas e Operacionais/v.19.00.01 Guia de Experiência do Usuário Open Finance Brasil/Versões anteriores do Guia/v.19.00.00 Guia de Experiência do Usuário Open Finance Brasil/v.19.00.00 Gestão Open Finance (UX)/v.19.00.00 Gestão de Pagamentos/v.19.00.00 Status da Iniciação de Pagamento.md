---
id: 1436289394
title: v.19.00.00 Status da Iniciação de Pagamento
version: 1
modified: 2026-01-12T19:25:35.111Z
url: /spaces/OF/pages/1436289394/v.19.00.00+Status+da+Inicia+o+de+Pagamento
---

Sumário76016truenonelisttrue
# Detalhamento dos Status da Jornada
**Para padronizar e facilitar o entendimento do usuário nas Jornadas de Compartilhamento de Dados e Iniciação de Pagamento, mostramos a seguir os status que devem ser apresentados ao usuário.**As tabelas têm como objetivo deixar claro o De-Para entre o status apresentado para o usuário e os status técnicos das APIs.Área de Gestão de Pagamentos 
# Status da Iniciação de Pagamentos
Para apresentar o status final ao usuário, deve-se seguir esta matriz de Status do “Consentimento” vs Status “Payments”:
| STATUS PARA O USUÁRIO FINAL | STATUS DE CONSENTIMENTO | STATUS DO `GET/PIX/PAYMENTS/{PAYMENTID}` |
| --- | --- | --- |
| (Pagamento) Solicitado | CONSUMED (Etapa de Efetivação) | `RCVD ` (Received) |
| (Pagamento) Agendado | CONSUMED | `SCHD ` (Processo de agendamento realizado) |
| (Consentimento) Aguardando aprovação de multiplas alçadas | PARTIALLY ACCEPTED | N/A |
| (Pagamento) Pendente | CONSUMED | `PDNG ` (Pendente) |
| (Pagamento) Em Processamento | CONSUMED | `ACCP ` (Pagamento pronto para ser enviado para liquidação)   `ACPD ` (Pagamento enviado para liquidação) |
| (Pagamento) Rejeitado pelo usuário ou detentor | CONSUMED | `RJCT ` (Rejeitado) |
| (Pagamento) Concluído | CONSUMED | `ACSC ` (Pagamento liquidado) |
| (Pagamento) Cancelado | REJECTED  CONSUMED | N/A `CANC ` (Transação cancelada a pedido do usuário) |
| Agendamento cancelado | CONSUMED | `CANC ` (Transação cancelada a pedido do usuário) |
| (Pagamento) Solicitado | AUTHORISED (Etapa de Efetivação) | `RCVD ` (Received) |
| (Pagamento) Pendente | AUTHORISED | `PDNG ` (Pendente) |
| (Pagamento) Em Processamento | AUTHORISED | `ACCP ` (Pagamento pronto para ser enviado para liquidação)   `ACPD ` (Pagamento enviado para liquidação) |
| (Pagamento) Rejeitado pelo usuário ou detentor | AUTHORISED | `RJCT ` (Rejeitado) |
| (Pagamento) Concluído | AUTHORISED | `ACSC ` (Pagamento liquidado) |
| (Pagamento) Cancelado | AUTHORISED | `CANC ` (Transação cancelada a pedido do usuário) |
| (Consentimento) Rejeitado pelo usuário ou detentor | REJECTED | N/A |
| (Consentimento) Revogado pelo usuário, pelo detentor ou pelo iniciador | REVOKED | Qualquer status de pagamento que seja diferente de `RCVD ` ou `SCHD` |
| (Consentimento) Aguardando aprovação de multiplas alçadas | PARTIALLY ACCEPTED | N/A |
| (Consentimento) Aguardando aprovação | AWAITING AUTHORISATION | N/A |
| (Consentimento) atingiu o seu limite (Prazo ou valor) | CONSUMED | `RJCT ` (Rejeitado)   `ACSC` (Pagamento liquidado)   `CANC ` (Transação cancelada a pedido do usuário) |
#F4F5F7
## Requisitos - ID e ITP
**Cenário: Geral**
1. O usuário deve ter acesso aos status dos pagamentos nos ambientes já disponíveis e/ou no ambiente dedicado a gestão do Open Finance.
2. Instituição Detentora de Conta: deve apresentar quando aplicável os status de acordo com a tabela/ matriz de status disponibilizado neste guia.
3. O status “(pagamento) solicitado” não é aplicável na Instituição Detentora de Contas, portanto não deve ser apresentado ao usuário.
4. Caso a instituição tenha o cenário de múltipla-alçada, deve ser apresentado o status “aguardando aprovação (do pagamento)” para todos os usuários necessários e envolvidos nessa operação.
5. Caso a instituição tenha o status “(pagamento ou agendamento) em processamento”, deve ser apresentado ao usuário seguindo a matriz de status.
6. Os status “(pagamento) não concluído” e “(pagamento) concluído” devem ser apresentados ao usuário sem exceção.
Status dos pagamentos