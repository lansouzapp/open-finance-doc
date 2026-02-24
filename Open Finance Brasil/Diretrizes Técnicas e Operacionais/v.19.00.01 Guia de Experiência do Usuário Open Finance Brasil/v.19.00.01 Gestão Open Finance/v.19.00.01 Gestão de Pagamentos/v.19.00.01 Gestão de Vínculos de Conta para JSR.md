---
id: 1477281271
title: v.19.00.01 Gestão de Vínculos de Conta para JSR
version: 1
modified: 2026-01-23T17:46:14.588Z
url: /spaces/OF/pages/1477281271/v.19.00.01+Gest+o+de+V+nculos+de+Conta+para+JSR
---

Requisitos e recomendações para gestão de vínculos de conta utilizados nas Jornadas de Pagamento Sem Redirecionamento (JSR). 
#F4F5F7
## Requisitos - ID e ITP
**Cenário: Geral**
1. Retorno ao usuário: Conforme regulação vigente, comunicar o resultado de todas as ações ao usuário, inclusive em caso de falha, conforme descrito na seção Casos de erro do subcapítulo Jornada Básica de Iniciação de Pagamento.
Feedback ao usuário**Cenário: Consulta aos Vínculos de Conta**As instituições devem atualizar os status de cada vínculo de conta para todos os tipos de pagamento sem redirecionamento via Open Finance, de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão.
1. Histórico de vínculos de conta: Exibir a lista de vínculos de conta com seus respectivos status individuais. Exs.: Ativo, Expirado, Cancelado, Em análise etc. Jornada Otimizada (saldo e limite): Sinalizar, de forma clara, na lista de contas vinculadas, aquelas para os quais o usuário optou por compartilhar o saldo e limite.
Histórico dos Vínculos de Conta
1. Detalhes dos vínculos de conta ativos: Permitir que o usuário acesse os detalhes de cada vínculo concluído contendo as seguintes informações: Identificação da outra instituição: Exibir a marca da outra instituição envolvida no vínculo. Identificação da Detentora e conta: Exibir identificação da ID e da conta de débito selecionada (Número da agência e conta). Jornada Otimizada (saldo e limite): Quando aplicável, indicar que o compartilhamento de saldo e limite está ativo . Exibir o escopo de cada dado compartilhado.
Detalhes dos Vínculos de Conta ativos
1. Detalhes dos vínculos de conta inativos: Nos casos em que o vínculo de conta não estiver ativo — como status cancelado, expirado ou rejeitado — exibir os campos aplicáveis de acordo com a disponibilidade de informações no momento.
Detalhes dos Vínculos de Conta inativos#F4F5F7
## Requisitos - ID
**Cenário: Consulta aos Vínculos de Conta**
1. Validade do vínculo: Além das informações mínimas previstas no detalhe de cada vínculo, exibir a data de validade do vínculo de conta.
Validade do Vínculo de Conta**Cenário: Alteração dos Vínculos de Conta** Na área de gestão de vínculos de conta, a Instituição Detentora de Conta (ID) deve possibilitar que o usuário altere parâmetros dos vínculos de conta ativos para pagamentos sem redirecionamento via Open Finance e deve comunicar as alterações à Instituição Iniciadora de Transação de Pagamento (ITP).
1. Alteração da validade: Permitir a alteração do prazo de validade do vínculo da conta. Informar o usuário, no momento da confirmação da alteração, que as alterações do prazo vínculo de conta podem afetar os pagamentos automáticos. Ex.: Prazo alterado com sucesso. Pagamentos automáticos programados para data posterior ao novo prazo serão cancelados. Caso o usuário tenha o compartilhamento de saldo e limite ativo, informar que a data de validade desse consentimento será automaticamente atualizada conforme a nova data de validade do vínculo de conta.

1. Alteração de limites: Permitir a alteração dos limites diário e/ou por transação do vínculo de conta. Informar o usuário, no momento da confirmação da alteração, que as alterações do limite podem afetar os pagamentos agendados.   Ex.: Limite alterado com sucesso. Pagamentos agendados com valor superior ao novo limite não serão efetuados.
Alteração de limites do Vínculo de Conta#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação dos Vínculos de Conta**Na área de gestão de vínculos de conta, as instituições devem possibilitar que o usuário cancele os vínculos ativos para pagamentos sem redirecionamento via Open Finance, assegurando clareza, rastreabilidade e segurança para o usuário. 
1. Revogação do vínculo de conta: Permitir que o usuário cancele vínculos de conta ativos a qualquer momento. Irreversibilidade da revogação : Deixar clara a irreversibilidade do cancelamento do vínculo de conta, e quando aplicável, do compartilhamento de saldo e limite e outras possíveis consequências. Revogação Pix Automático com JSR: Ao optar pela revogação do vínculo de conta, deixar claro para o usuário que a autorização de Pix Automático atrelada ao vínculo de conta também será revogada. Informar que novos agendamentos não poderão ser criados após a revogação. Informar que pagamentos já enviados serão mantidos. Jornada Otimizada (saldo e limite): Ao optar pela revogação do vínculo de conta, deixar claro para o usuário que o compartilhamento de saldo e limite também será revogado.
Revogação do Vínculo de Conta**Cenário: Revogação do compartilhamento de saldo e limite**Na área de gestão de vínculos de conta, as instituições devem possibilitar que o usuário cancele o compartilhamento de saldo e limite de um vínculo de conta para pagamentos sem redirecionamento via Open Finance, sem cancelar o vínculo de conta, assegurando clareza, rastreabilidade e segurança para o usuário.  
1. Revogação do compartilhamento de saldo e limite: Permitir que o usuário cancele o compartilhamento de saldo e limite de um vínculo de conta a qualquer momento. Manutenção do vínculo: Ao optar pelo encerramento do compartilhamento de saldo e limite, deixar claro para o usuário que o vínculo de conta se mantém ativo.
Revogação do compartilhamento de saldo e limite#F4F5F7
## Recomendações - ID e ITP
**Cenário: Consulta aos Vínculos de Conta**
1. Acesso às contas salvas: Disponibilizar acesso às contas salvas através:  - Da área “Open Finance”.  - Do caminho “Open Finance” > “Minhas contas salvas/vinculadas”.   - De áreas dedicadas aos produtos, no canal da instituição.
2. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre seus vínculos de conta com facilidade.
3. Ordenação da lista: Na lista de vínculos de conta ativos, exibir primeiramente os que estiverem próximo de expirar.
Consulta aos Vínculos de Conta - Geral - Recomendações
1. Identificação do dispositivo: Exibir a identificação (apelido) do dispositivo autorizado.
Consulta aos Vínculos de Conta - Dispositivo autorizado - Recomendações#F4F5F7
## Recomendações - ITP
**Cenário: Consulta aos Vínculos de Conta**
1. Validade do vínculo: Exibir a data de validade do vínculo de conta.
Validade do Vínculo de Conta - Recomendação#F4F5F7
## Recomendações - ID
**Cenário: Alteração dos Vínculos de Conta**
1. Uso do termo “alterar”: Usar o termo “alterar” em suas diferentes conjugações, de acordo com o contexto.
2. Otimização da alteração: Pré-preencher dados do vínculo de conta para facilitar a alteração. Ex.: Se o parâmetro alterado for de limites, os demais campos podem vir preenchidos.
Alteração dos Vínculos de Conta#F4F5F7
## Recomendações - ID e ITP
**Cenário: Revogação dos Vínculos de Conta**
1. Revogação do vínculo de conta: Possibilitar que o usuário cancele vínculos de conta ativos em uma única jornada.
2. Confirmação da revogação: Em caso de tentativa de cancelamento do vínculo de conta – com ou sem Jornada Otimizada – por parte do usuário, exibir uma mensagem de confirmação da ação.  Ex.: Tem certeza que quer cancelar o vínculo de conta? [O compartilhamento de saldo e limite também será cancelado.] Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento. Ex.: Tem certeza que deseja cancelar o vínculo? Essa ação é irreversível [e encerra o compartilhamento do saldo e limite e a autorização de Pix Automático atrelada. Os pagamentos agendados serão mantidos, mas novos agendamentos não poderão ser feitos].
Revogação dos Vínculos de Conta - Recomendações**Cenário: Jornada Otimizada - Revogação do compartilhamento de saldo e limite**
1. Benefícios do compartilhamento: Caso o usuário selecione a opção de encerramento do compartilhamento de saldo e limite, exibir mensagem informando sobre os benefícios de manter a funcionalidade.
2. Informação adicional: Incluir informação adicional sobre o compartilhamento de saldo e limite através de link, botão, imagem, texto etc.
Revogação do compartilhamento de saldo e limite - Recomendações