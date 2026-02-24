---
id: 1477281218
title: v.19.00.01 Gestão de Transações Temporizadas
version: 1
modified: 2026-01-23T17:46:13.584Z
url: /spaces/OF/pages/1477281218/v.19.00.01+Gest+o+de+Transa+es+Temporizadas
---

Requisitos e recomendações para gestão das transações que exigem análise adicional por parte da Instituição Detentora de Conta (ID). #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta à transação temporizada**Caso o usuário saia da tela de análise na etapa de **Efetivação**da Instituição Iniciadora de Transação de Pagamento (ITP), ele deve conseguir retomar a consulta da transação pela área de gestão de pagamentos, juntamente com as demais transações.
Para garantir consistência, as instituições precisam manter o status da transação sempre atualizado, de modo que o usuário visualize as mesmas informações tanto na ITP quanto na ID. 
1. Status das transações: Exibir o status atualizado de cada transação temporizada. Exs.: Em análise, Pendente, Concluída, Cancelada, Negada.
2. Detalhes da transação pendente: Enquanto estiver em análise, disponibilizar acesso aos detalhes da transação, contendo a informação sobre necessidade de tempo adicional para análise e todas as demais informações conforme definido pelo arranjo de pagamento.
Consulta à transação temporizada#F4F5F7
## Requisitos - ITP
**Cenário: Consulta à transação temporizada**
1. Alternativa para transação negada: Se após análise, a transação for negada pela Detentora selecionada, indicar ao usuário, quando aplicável, outra Detentora e/ou forma de iniciação de pagamento.
Alternativa para transação negada #F4F5F7
## Requisitos - ID e ITP
**Cenário: Cancelamento da transação**
1. Cancelamento da transação: Permitir que ao acessar os detalhes da transação em análise na área de gestão, o usuário cancele a transação antes da efetivação.
Cancelamento da transação