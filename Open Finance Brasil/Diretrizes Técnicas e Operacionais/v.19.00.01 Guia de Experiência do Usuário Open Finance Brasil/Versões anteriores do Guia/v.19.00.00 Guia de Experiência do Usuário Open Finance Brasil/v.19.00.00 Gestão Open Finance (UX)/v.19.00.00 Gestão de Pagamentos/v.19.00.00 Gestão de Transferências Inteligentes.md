---
id: 1436288914
title: v.19.00.00 Gestão de Transferências Inteligentes
version: 1
modified: 2026-01-12T19:25:27.644Z
url: /spaces/OF/pages/1436288914/v.19.00.00+Gest+o+de+Transfer+ncias+Inteligentes
---

Requisitos e recomendações para gestão de pagamentos com Transferências Inteligentes via Open Finance. Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento – para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.Gestão de Transferências Inteligentes - ID/ITP#F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta à autorização de Transferências Inteligentes**As instituições devem atualizar os status de cada autorização de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas Áreas de Gestão conforme as regras do arranjo de pagamento. 
1. Histórico de autorizações: Exibir a lista de autorizações de Transferências Inteligentes com seus respectivos status individuais.    Exs.: Ativa, Expirada, Cancelada, Pendente etc.
Histórico de autorizações 
1. Detalhes da autorização: Permitir que o usuário acesse os detalhes do comprovante com todas as informações de cada autorização de Transferências Inteligentes, conforme definido na etapa de Solicitação de Iniciação de Pagamento.   Limite de crédito: Informar sobre a possibilidade, quando aplicável, da utilização de limite de crédito pré-aprovado para transferências de valor superior ao saldo disponível em conta.
Detalhes da autorização - Limite de crédito
1. Sinalização da Jornada Otimizada: Quando aplicável, sinalizar, de forma clara, na lista de autorizações, aquelas para os quais o usuário optou por compartilhar o saldo e limite.
2. Detalhes da autorização: Na tela de detalhes da autorização, indicar que o saldo e o limite estão sendo compartilhados, bem como o escopo de cada dado.
**Cenário: Consulta às transferências realizadas**
1. Histórico de transferências: Exibir a lista de transferências vinculadas a cada autorização, com seus respectivos status individuais.   Exs.: Concluída, Cancelada, Não realizada etc.
2. Detalhes da transferência: Exibir comprovante de cada transferência com todas as informações conforme definido pelo arranjo de pagamento.
Histórico e Detalhes de transferências#F4F5F7
## Requisitos - ITP
**Cenário: Consulta às transferências realizadas**
1. Detalhes da transferência: Além das informações mínimas previstas no comprovante do arranjo de pagamento, exibir o gatilho que originou a transferência, quando aplicável.
Detalhes da transferência - Gatilhos**Cenário: Alteração da autorização de Transferências Inteligentes**Todas as alterações referentes a autorizações de Transferências Inteligentes devem ser realizadas exclusivamente na área de gestão da Instituição Iniciadora de Transação de Pagamento (ITP) que deve comunicar cada alteração à Instituição Detentora de Conta (ID).  
1. Alteração das contas recebedoras: Permitir que o usuário inclua, altere ou exclua contas recebedoras de mesma titularidade para suas autorizações ativas.
2. Gatilhos de transferências: Permitir que, caso a ITP ofereça mais de uma opção de gatilho de transferência, o usuário possa alterá-las.
Alteração da autorização - Contas recebedoras e Gatilhos**Nota:**Alterações como troca da ID ou da conta de origem, modificação do prazo da autorização, ajuste de valor ou de limites transacionais exigem a revogação da autorização vigente e a criação de uma nova. A ITP pode, se desejar, oferecer essas alterações como uma edição simples, reaproveitando informações já preenchidas e conduzindo o usuário para a etapa de Solicitação de Iniciação de Pagamento de forma fluida e transparente, sem exigir ações manuais de cancelamento ou reinício do processo.  
1. Confirmação da alteração: Na etapa de efetivação, exibir mensagem informando que a autorização anterior foi cancelada e substituída por uma nova, sem necessidade de reinício do processo.    Ex.: Tudo certo! Sua autorização anterior foi cancelada e uma nova foi criada com a nova conta de débito escolhida.
Confirmação da alteração#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação da autorização de Transferências Inteligentes**Na área de gestão de pagamento, as Instituições devem possibilitar que o usuário cancele as autorizações ativas de Transferências Inteligentes, assegurando clareza, rastreabilidade e segurança para o usuário. 
1. Revogação da autorização: Permitir que o usuário cancele autorizações ativas e informá-lo sobre as regras para cancelamento, quando aplicável.  Jornada otimizada: Ao optar pela revogação da autorização do pagamento, deixar claro para o usuário que o compartilhamento de saldo e limite também será revogado.​
2. Irreversibilidade da revogação: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências.
Revogação da autorização**Cenário: Jornada Otimizada - Revogação da autorização de Transferências Inteligentes com saldo e limite**
1. Revogação do compartilhamento de saldo e limite:  Permitir que o usuário encerre o compartilhamento de saldo e limite de uma autorização a qualquer momento. Ao optar pelo encerramento do compartilhamento de saldo e limite, deixar claro para o usuário que a autorização de pagamento se mantém ativa.
Revogação do compartilhamento de saldo e limite#F4F5F7
## Recomendações - ITP
**Cenário: Consulta à autorização de Transferências Inteligentes**
1. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre suas autorizações e pagamentos com facilidade.
Consulta à autorização - Busca - Recomendação**Cenário: Alteração da autorização de Transferências Inteligentes**
1. Apelido para contas recebedoras: Permitir que o usuário crie um apelido para cada uma de suas contas recebedoras.    Exs.: Investimentos, Poupança para Viagem etc.
2. Gestão de notificações: Permitir a gestão de recebimento de notificações por autorização.
Alteração da autorização - Apelido para contas recebedoras - Recomendação **Cenário: Revogação da autorização de Transferências Inteligentes**
1. Confirmação da revogação: Em caso de tentativa de cancelamento da autorização por parte do usuário, exibir uma mensagem de confirmação da ação.    Ex.: Deseja cancelar esta autorização? Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento.   Ex.: Tem certeza que quer cancelar a autorização? Essa ação não pode ser desfeita e resultará no cancelamento de todas as transferências futuras vinculadas.
Confirmação da revogação - Recomendação **Cenário: Jornada Otimizada - Revogação da autorização de Transferências Inteligentes com saldo e limite**
1. Benefícios do compartilhamento: Caso o usuário selecione a opção de encerramento do compartilhamento de saldo e limite, exibir mensagem informando sobre os benefícios de manter a funcionalidade.
2. Informação adicional: Incluir informação adicional sobre o compartilhamento de saldo e limite através de link, botão, imagem, texto etc.
Revogação do compartilhamento de saldo e limite - Recomendação