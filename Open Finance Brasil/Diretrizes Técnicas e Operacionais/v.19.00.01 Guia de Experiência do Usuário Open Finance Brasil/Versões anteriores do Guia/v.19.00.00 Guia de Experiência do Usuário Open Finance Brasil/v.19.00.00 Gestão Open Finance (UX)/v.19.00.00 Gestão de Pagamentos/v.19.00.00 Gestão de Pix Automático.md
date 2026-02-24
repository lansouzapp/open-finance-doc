---
id: 1436288776
title: v.19.00.00 Gestão de Pix Automático
version: 1
modified: 2026-01-12T19:25:25.661Z
url: /spaces/OF/pages/1436288776/v.19.00.00+Gest+o+de+Pix+Autom+tico
---

Requisitos e recomendações para gestão de pagamentos com Pix Automático, inclusive em Jornadas sem Redirecionamento (JSR), via Open Finance. Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos. #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta às autorizações de Pix Automático**As Instituições devem atualizar os status de cada autorização de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Histórico de autorizações: Exibir a lista de autorizações de Pix Automático com seus respectivos status individuais.    Exs.: Ativa, Expirada, Cancelada, Pendente etc.
Histórico de autorizações 
1. Detalhes da autorização: Permitir que o usuário acesse os detalhes do comprovante com todas as informações de cada autorização de Pix Automático, conforme definido na etapa de Solicitação de Iniciação de Pagamento. Limite de crédito: Informar sobre a possibilidade, quando aplicável, da utilização de limite de crédito pré-aprovado para pagamentos de valor superior ao saldo disponível em conta.
Consulta às autorizações - Limite de crédito**Cenário: Consulta aos pagamentos com Pix Automático**
1. Histórico de pagamentos: Exibir a lista de pagamentos vinculados a cada autorização, com seus respectivos status individuais.    Exs.: Concluído, Cancelado, Não realizado etc.
2. Detalhes do pagamento: Exibir comprovante de cada pagamento com todas as informações conforme definido pelo arranjo de pagamento.
Detalhes do pagamento**Cenário: Alteração de autorização de Pix Automático**Na área de gestão de pagamentos, as Instituições devem possibilitar que, além de visualizar as autorizações, o usuário possa configurar os parâmetros disponíveis das autorizações ativas como valor máximo (ID/ITP), uso do limite de crédito (ID) e preferências de recebimento de notificações (ID/ITP). 
1. Valor máximo: Para autorizações ativas de valor variável, manter desativado por padrão (valor indeterminado) e permitir que o usuário ative e insira um valor máximo para cada pagamento, respeitando o valor mínimo definido pelo usuário recebedor. Informar que se o valor máximo configurado for inferior ao valor de um pagamento agendado, o pagamento não será efetivado e o usuário poderá ser notificado para buscar outras formas de pagamento. Informar que o novo valor máximo se aplica apenas aos pagamentos ainda não agendados da recorrência.
Alteração da autorização - Valor máximo#F4F5F7
## Requisitos - ID
**Cenário: Alteração de autorização de Pix Automático**
1. Uso do limite de crédito : Manter o uso do limite de crédito ativado por padrão e permitir que o usuário desative.
2. Gestão de notificações: Manter o envio de notificações ativado por padrão e permitir que o usuário desative.
Alteração da autorização - Limite de crédito e notificações#F4F5F7
## Requisitos - ITP
**Cenário: Alteração de autorização de Pix Automático****Nota:**Alterações como troca da ID ou da conta de origem exigem a revogação da autorização vigente e a criação de uma nova. 
A ITP pode, se desejar, oferecer essas alterações como uma edição simples, reaproveitando informações já preenchidas e conduzindo o usuário para a etapa de **Solicitação de Iniciação de Pagamento** de forma fluida e transparente, sem exigir ações manuais de cancelamento ou reinício do processo. 
1. Confirmação de alteração: Na etapa de efetivação, exibir mensagem informando que a autorização anterior foi cancelada e substituída por uma nova, sem necessidade de reinício do processo.    Ex.: Tudo certo! A autorização anterior foi cancelada e uma nova foi criada com a sua nova instituição.
Confirmação da alteração #F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação de autorização de Pix Automático**
1. Revogação da autorização: Permitir que o usuário cancele autorizações ativas e informá-lo sobre as regras para cancelamento conforme definido pelo arranjo de pagamento. Irreversibilidade da revogação: Deixar clara a irreversibilidade do cancelamento da autorização e outras possíveis consequências.
Revogação da autorização**Cenário: Cancelamento do pagamento com Pix Automático**Na área de gestão de pagamento, as instituições devem possibilitar que o usuário cancele os pagamentos da recorrência de Pix Automático, assegurando clareza, rastreabilidade e segurança. 
1. Cancelamento dos pagamentos: Permitir que o usuário cancele os pagamentos da recorrência e informá-lo sobre as regras para cancelamento, conforme definido pelo arranjo de pagamento.    Ex.: Você pode cancelar este pagamento até às 23:59 do dia anterior à data agendada. Irreversibilidade do cancelamento: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências. Manutenção dos pagamentos futuros: Deixar claro para o usuário que o cancelamento de um pagamento não impede que os agendamentos futuros sejam efetivados e novos pagamentos sejam agendados.
Cancelamento de pagamento avulso da recorrência #F4F5F7
## Recomendações - ID e ITP
**Cenário: Revogação de autorização de Pix Automático**
1. Confirmação da revogação: Em caso de tentativa de cancelamento da autorização por parte do usuário, exibir uma mensagem de confirmação da ação.  Ex.: Deseja cancelar esta autorização para Telefonia S/A? Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento. Ex.: Deseja cancelar essa autorização? Esta ação é irreversível e resultará no cancelamento de todos os pagamentos futuros vinculados.
Confirmação da revogação**Cenário: Consulta às autorizações e pagamentos com Pix Automático**
1. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre suas autorizações e pagamentos com facilidade.
Busca - Recomendação**Cenário: Cancelamento do pagamento com Pix Automático**
1. Confirmação do cancelamento: Em caso de tentativa de cancelamento de um pagamento individual por parte do usuário, exibir uma mensagem de confirmação da ação.   Ex.: Deseja cancelar este pagamento para Telefonia S/A?  Combinar a mensagem de confirmação com a informação obrigatória de que o cancelamento do pagamento atual não impede o agendamento dos pagamentos futuros, conforme os parâmetros da autorização ativa.   Ex.: Tem certeza que quer cancelar este pagamento para Telefonia S/A? Esta ação é irreversível e não impede o agendamento dos pagamentos futuros.
Confirmação do cancelamento do pagamento avulso - Recomendação **Cenário: Alteração de autorização de Pix Automático**
1. Gestão de notificações: Permitir a gestão de recebimento de notificações para cada autorização ativa em uma única jornada.
2. Valor máximo: Permitir edição de valor máximo para cada autorização ativa de valor variável em uma única jornada.
Alteração de autorização em uma única jornada - Notificações e Valor máximo #F4F5F7
## Recomendações - ID
**Cenário: Alteração de autorização de Pix Automático**
1. Uso do limite de crédito: Permitir edição do uso do limite de crédito para cada autorização ativa em uma única jornada.
Alteração da autorização em uma única jornada - Limite de crédito