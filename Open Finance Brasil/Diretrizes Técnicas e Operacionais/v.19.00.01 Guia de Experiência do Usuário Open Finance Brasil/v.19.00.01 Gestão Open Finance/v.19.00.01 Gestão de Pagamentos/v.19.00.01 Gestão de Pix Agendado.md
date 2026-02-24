---
id: 1477280918
title: v.19.00.01 Gestão de Pix Agendado
version: 1
modified: 2026-01-23T17:46:09.211Z
url: /spaces/OF/pages/1477280918/v.19.00.01+Gest+o+de+Pix+Agendado
---

Requisitos e recomendações para gestão de pagamentos com Pix Agendado via Open Finance, inclusive em Jornadas sem Redirecionamento (JSR). Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.As instituições devem atualizar os status de cada agendamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta aos agendamentos**As instituições devem atualizar os status de cada agendamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Histórico de pagamentos: Exibir a lista de pagamentos gerados por agendamentos únicos ou recorrentes, com seus respectivos status individuais.   Exs.: Agendado, Concluído, Cancelado, Não realizado etc.
2. Detalhes do pagamento: Exibir comprovante de cada pagamento com todas as informações conforme definido pelo arranjo de pagamento.
3. Detalhes da recorrência: Permitir que o usuário acesse os detalhes do comprovante com todas as informações do agendamento, conforme definido pelo arranjo de pagamento.
Consulta aos agendamentos#F4F5F7
## Requisitos - ITP
**Cenário: Alteração dos agendamentos**Na área de gestão de pagamento, a Iniciadora pode permitir que, além de visualizar os agendamentos, o usuário tenha a experiência de alteração dos parâmetros como data, recebedor ou Detentora, embora esteja cancelando o agendamento vigente e criando uma nova autorização de agendamento.
1. Confirmação de alteração: Na etapa de efetivação, exibir mensagem informando que o agendamento anterior foi cancelado e substituído por um novo, sem necessidade de reinício do processo.      Ex.: Tudo certo! Seu agendamento anterior foi encerrado e um novo foi criado com o novo valor.
Experiência de alteração do agendamento#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação dos agendamentos - Único ou recorrentes**Na área de gestão de pagamento, as instituições devem possibilitar que o usuário cancele os pagamentos agendados com Pix, assegurando clareza, rastreabilidade e segurança. 
1. Cancelamento de agendamentos: Permitir que o usuário cancele os pagamentos agendados (único ou recorrente) e informá-lo sobre as regras para cancelamento, conforme definido pelo arranjo de pagamento.   Ex.: Você pode cancelar o pagamento até às 23:59 do dia anterior à data agendada.
2. Irreversibilidade do cancelamento: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências.
Revogação do agendamento **Para agendamentos recorrentes**
1. Manutenção de pagamentos futuros: Deixar claro para o usuário que o cancelamento de um pagamento agendado não impede que os pagamentos de agendamentos futuros sejam efetivados.
Cancelamento de um pagamento da recorrência - 
Manutenção dos pagamentos futuros #F4F5F7
## Recomendações - ID e ITP
**Cenário: Cancelamento de pagamentos avulsos - Agendamento recorrente**Para casos nos quais seja necessária aprovação adicional, além do solicitante:
1. Confirmação de cancelamento: Em caso de tentativa de cancelamento de um pagamento individual por parte do usuário, exibir uma mensagem de confirmação da ação.    Ex.: Deseja cancelar este pagamento para João Rodrigues? Em caso de cancelamento de um pagamento da recorrência, combinar a mensagem de confirmação com a informação obrigatória de que o cancelamento do pagamento atual não impede o agendamento dos pagamentos futuros, conforme os parâmetros da autorização ativa.    Ex.: Deseja cancelar este pagamento para João Rodrigues? Essa ação não pode ser desfeita e não impede o agendamento dos pagamentos futuros. Em caso de cancelamento completo, combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento.    Ex.: Deseja cancelar esse agendamento para João Rodrigues? Esta ação é irreversível e resultará no cancelamento de todos os pagamentos futuros vinculados.
Cancelamento de um pagamento da recorrência - Recomendações **Cenário: Consulta aos agendamentos**
1. Necessidade de saldo e limites: Informar ao usuário que a transação estará sujeita à disponibilidade de saldo e limites transacionais na conta de débito no momento da efetivação do pagamento.
Necessidade de saldo e limite - Recomendação