---
id: 1477283850
title: v.19.00.01 Comunicação e Notificações - Pix Agendado
version: 1
modified: 2026-01-23T17:46:53.136Z
url: /spaces/OF/pages/1477283850/v.19.00.01+Comunica+o+e+Notifica+es+-+Pix+Agendado
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a jornada do Pix Agendado. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento.  **Nota:**Consulte a seção de **Comunicação e Notificações - Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Pix Agendado**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização do agendamento, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações de agendamento - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix Agendado**
1. Status dos pagamentos: Notificar o usuário sobre o sucesso, falha ou cancelamento de um pagamento agendado único ou da recorrência, conforme as regras do arranjo de pagamento Pix Agendado.    Ex.: O Pix Agendado no valor de R$100,00 foi enviado para João Rodrigues da Silva CPF ***.345.678-**.
2. Encerramento de conta do recebedor: Notificar o usuário caso a conta do recebedor seja encerrada, informando-o que esse é o motivo para a não efetivação do pagamento atual e dos futuros, em caso de agendamentos recorrentes.   Ex.: O Pix Agendado para João Rodrigues (R$ 100,00) não foi realizado porque a conta do recebedor foi encerrada. Altere a conta na Área de Gestão.
Notificações de pagamento - ID #F4F5F7
## Recomendações - ID
**Cenário: Sobre pagamentos com Pix Agendado****Para agendamentos recorrentes**
1. Encerramento de conta do recebedor: Em caso de encerramento da conta do recebedor, notificar o usuário direcionando-o para a jornada de Alteração/Cancelamento do(s) agendamento(s), a fim de possibilitar a manutenção do produto com o cadastro de uma nova conta recebedora.    Ex.: O Pix Agendado para João Rodrigues (R$ 100,00) não foi realizado porque a conta do recebedor foi encerrada. Altere a conta na Área de Gestão.
Notificação de pagamento - Recomendação