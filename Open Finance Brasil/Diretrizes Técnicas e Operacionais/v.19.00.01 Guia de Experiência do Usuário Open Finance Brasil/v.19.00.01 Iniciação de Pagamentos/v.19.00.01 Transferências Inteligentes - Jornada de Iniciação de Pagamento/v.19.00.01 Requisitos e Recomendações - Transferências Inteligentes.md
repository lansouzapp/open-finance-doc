---
id: 1477284519
title: v.19.00.01 Requisitos e Recomendações - Transferências Inteligentes
version: 1
modified: 2026-01-23T17:47:02.981Z
url: /spaces/OF/pages/1477284519/v.19.00.01+Requisitos+e+Recomenda+es+-+Transfer+ncias+Inteligentes
---

Requisitos e recomendações específicos das etapas de **Solicitação de Iniciação de Pagamento, Direcionamento ITP > ID, Confirmação, Redirecionamento ID > ITP e Efetivação** da jornada de pagamento com **Pix**através de **Transferências Inteligentes** via Open Finance.**Nota:**Os requisitos e recomendações deste capítulo sobre **Transferências Inteligentes** complementam os de **Pix - Jornada Básica de Iniciação de Pagamento****.**Quando ambos forem aplicáveis, **todos os requisitos e recomendações devem ser observados.**   Em caso de conflito entre orientações, **prevalecem os requisitos e recomendações descritos neste capítulo.**
# Exemplos de casos de uso

## Transferências Inteligentes com Pix
Permite a programação de envios automáticos de dinheiro entre contas de mesma titularidade.
- Gestão Financeira Centralizada (Multibanking): Movimentar todas as suas contas por um único aplicativo.
- Gestão Financeira Automatizada: Automação de operações recorrentes de conta para redução de carga operacional, encargos ou para otimização de fluxo de caixa.
- Cobertura automática de Cheque Especial: Cobertura de saldo para evitar juros e saldo negativo.
- Aplicações Automáticas Inteligentes: Configurar transferências para contas com aplicações automáticas regularmente.
- Aplicações Automáticas Inteligentes: Configurar transferências para contas com aplicações automáticas regularmente.
- Depósitos Inteligentes de Conta: Facilitar a disponibilidade de saldo em contas do usuário com depósitos com 1 clique, agendados ou acionados automaticamente de acordo com regras por ele definidas. Digite ou cole algo aqui para o transformar em um trecho.

# Etapa 1: Solicitação
Nesta etapa, após selecionar o serviço Transferências Inteligentes com Pix e escolher a Instituição Detentora da Conta (ID) que será usada para realizar a transação, o usuário é informado sobre os gatilhos (manuais ou automáticos) que disparam as transferências conforme disponibilizado pela Instituição Iniciadora de Transação de Pagamento (ITP) e, se desejar, estabelece limites para essas transações.   
  
Em seguida, ele revisa os dados configurados e visualiza as demais informações da autorização que será enviada à ID.      A ITP é responsável por validar os dados inseridos, ocultar informações sensíveis e preparar a solicitação de iniciação de pagamento para envio à ID e, quando aplicável, exibir mensagens de erro claras ao usuário.#F4F5F7
## Requisitos - ITP
**Cenário: Autorização de Transferências Inteligentes****Nota:**Consulte a etapa **Solicitação de Iniciação de Pagamento** no subcapítulo**Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.A ITP deve possibilitar que o usuário insira e/ou revise as informações da autorização de pagamentos com Pix via Transferências Inteligentes conforme as regras do arranjo Pix. 
1. Exibição dos gatilhos: Exibir os gatilhos de transferências com clareza.
Exs.: 
- Para garantir saldo em suas outras contas.
- Para o pagamento de lançamentos futuros que estiverem agendados.
- Para programar investimentos em determinados produtos regularmente etc.
**Atenção:**Os gatilhos de transferências automáticas são definidos conforme a estratégia da ITP e não são enviados à ID.
1. Transferências automáticas: Nos casos em que sejam realizadas transferências sem a presença do usuário no ambiente da ITP, informá-lo que as movimentações poderão acontecer automaticamente dentro dos parâmetros e limites estabelecidos para atender o caso de uso informado.
Autorização de Transferências Inteligentes
1. Contas recebedoras: Informar ao usuário que apenas contas de mesma titularidade serão definidas como contas recebedoras. 
- Para pessoas físicas, as contas devem estar vinculadas ao mesmo nome e CPF.
- Para pessoas jurídicas, as contas devem estar vinculadas à mesma razão social e à mesma raiz de CNPJ.
Contas recebedoras**Nota:**O momento de definição das informações da instituição e das contas recebedoras fica a critério da ITP, com a possibilidade de utilização de chave Pix ou inserção manual.
1. Definição de limites transacionais: Permitir a definição de limites por transferência, por autorização e/ou por períodos (diário, semanal, mensal ou anual). Informar que os limites transacionais definidos na Detentora prevalecem sobre os limites definidos na Iniciadora.   Ex.: Os limites definidos aqui estão sujeitos aos limites da sua conta. Permitir definição de mais de um limite periódico ao mesmo tempo.    Ex.: Limite por transferência de R$1000,00 e limite diário de R$5000,00. Permitir definição de limite total por valor e/ou número de transferências.
Definição de limites transacionais
1. Prazo da autorização: Exibir a validade da autorização, inclusive quando for indeterminada. Caso o usuário tenha definido um limite total, informá-lo que a autorização irá expirar quando esse limite for atingido.   Ex.: Essa autorização irá expirar quando este valor for atingido.
Definição da validade da autorização
1. Datas inexistentes: Em casos de uso que prevejam transferências em datas específicas, informar que em caso de agendamento para datas inexistentes (Ex.: Dias 29, 30 e 31 de determinados meses), a transferência poderá ser feita em data anterior ou posterior à data agendada.
Datas inexistentes
1. Descrição da autorização: Exibir a descrição da autorização (via campo `additionalInformation` ), em casos de uso em que a recorrência das transferências seja previsível. Ex.: Gestão Financeira Inteligente.
**Nota:**Transferências previsíveis são as automáticas. Elas ocorrem sem a presença do usuário e são disparadas a partir do(s) gatilho(s) previamente definidos/selecionados.
1. Número de recorrências: Caso a ITP limite o número de transferências diárias, informar este limite ao usuário de forma clara.
Descrição da autorização
1. Jornada Otimizada (saldo e limite): Permitir que o usuário compartilhe, de forma opcional, o saldo e limite da conta selecionada. A seleção da opção de compartilhamento de saldo e limite deve ser apresentada desabilitada por padrão.​ Permitir que o usuário avance sem obrigá-lo a aceitar o compartilhamento do saldo e limite da conta selecionada. Quando aplicável, informar que o saldo e o limite estão sendo compartilhados. Exibir o escopo de cada dado compartilhado.​ Omitir qualquer aspecto que desvie o foco do usuário em concluir o compartilhamento de saldo e limite, como, por exemplo link, botão, imagem, texto, entre outros.
Jornada Otimizada
# Etapa 2: Direcionamento
Nesta etapa, o usuário é direcionado da Instituição Iniciadora de Transação de Pagamento (ITP) para a Instituição Detentora de Conta (ID) para se autenticar, revisar e confirmar a autorização de pagamento. Já a ITP deve orientar o usuário sobre o direcionamento e assegurar que a navegação ocorra de forma transparente, conforme o dispositivo utilizado.Além disso, quando aplicável, a ITP deve exibir mensagens de erro claras ao usuário.#F4F5F7
## Requisitos - ITP
**Cenário: Tela de transição****Nota:**Consulte a etapa **Direcionamento** no subcapítulo**Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.
1. Tempo de conclusão:  Informar que o usuário possui até 60 minutos para confirmar a autorização de pagamento na ID.    Ex.: Estamos te direcionando com segurança para a (Instituição X). Você tem até 60 minutos para finalizar a transação.
Tela de transição ITP > ID 
# Etapa 3: Confirmação
Nesta etapa, o usuário se autentica na Instituição Detentora de Conta (ID) e pode, em caso de múltiplas contas de débito, escolher a que deseja usar para fazer a(s) transferência(s). Ele também revisa as informações da autorização enviadas pela ID e confirma a transação. A ID deve garantir um ambiente seguro para autenticação, exibir o resumo da autorização, permitir a edição da conta de débito, em caso de múltiplas contas, e viabilizar a confirmação com o mínimo de fricção. Também é sua responsabilidade, em caso de falha, exibir mensagens de erro claras ao usuário, comunicar o resultado da transação à Instituição Iniciadora de Transação de Pagamento (ITP), enviar notificações ao usuário e, quando aplicável, aos demais aprovadores — em casos de múltiplas alçadas ou falha na conclusão da autorização.#F4F5F7
## Requisitos - ID
**Cenário: Revisão e confirmação da autorização****Nota:**Consulte a etapa **Confirmação******no subcapítulo **Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.Após o usuário se autenticar, a ID deve exibir todas as informações da autorização informadas pela ITP.
1. Descrição da autorização: Exibir a descrição da autorização conforme informado pela ITP, quando aplicável (via campo `additionalInformation` ).
2. Limites transacionais: Exibir os limites transacionais definidos na ITP, quando aplicável. Se os limites definidos na ITP forem superiores aos limites da conta na ID, exibir mensagem informando que a efetivação das transferências estará condicionada ao ajuste dos limites.    Ex.: O valor programado para transferência é maior que o limite da sua conta na instituição de débito. Ajuste o limite aqui ou na sua instituição para garantir a transferência. Se a autorização incluir um valor fixo (Ex. Transferir R$ 500,00 da conta X para a conta Y todo dia 10), e no momento da confirmação, a ID identificar insuficiência de saldo na conta selecionada, exibir mensagem informando que a efetivação das transferências estará condicionada à recomposição do saldo.    Ex.: Você não possui saldo suficiente na sua conta. Adicione saldo até a data programada para garantir a transferência.
3. Início da autorização: Exibir a data de início da autorização.
4. Prazo da autorização: Exibir a validade da autorização de acordo com o parâmetro definido pelo usuário, seja por uma data específica, por prazo indeterminado ou pela condição de atingimento de um limite previamente estabelecido.
5. Identificador da autorização: Exibir o número da autorização (número final do `consentId` , excluindo o prefixo `urn:instituicao:` ).
6. Edição de parâmetros: Impossibilitar a edição de parâmetros da autorização configurados na ITP. Ex.: Limites transacionais.
Revisão e confirmação da autorização
1. Jornada Otimizada (saldo e limite): Quando aplicável, informar que o saldo e o limite estão sendo compartilhados.​ Exibir o escopo de cada dado compartilhado.​
Revisão e confirmação da autorização - Jornada Otimizada
# Etapa 4: Redirecionamento
**Nota:**A etapa **Redirecionamento******está detalhada no subcapítulo **Jornada Básica de Iniciação de Pagamento.**Tela de transição ITP > ID
# Etapa 5: Efetivação
Nesta etapa final da jornada, o usuário é recebido no ambiente da Instituição Iniciadora de Transação de Pagamento (ITP) onde visualiza o resultado da solicitação.    A ITP deve apresentar com clareza o status e os principais dados da autorização de pagamento, com mensagens de sucesso ou falha, e disponibilizar, na área de gestão, um comprovante com todos os dados da autorização.   Essa etapa também pode envolver orientações em caso de erro ou pendências, como autorizações em múltiplas alçadas, transações temporizadas ou indisponibilidade momentânea dos sistemas.#F4F5F7
## Requisitos - ITP
**Cenário: Efetivação da autorização****Nota:**Consulte a etapa **Efetivação******no subcapítulo **Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.
1. Contas recebedoras: Exibir informações referentes às contas recebedoras e/ou acesso ao ambiente de gestão de contas recebedoras para a autorização específica, quando aplicável.
2. Descrição da autorização: Exibir a descrição da autorização, quando aplicável.
3. Descrição dos gatilhos: Exibir a descrição dos gatilhos de transferência.
4. Limites transacionais: Exibir os limites transacionais, quando aplicável.
5. Necessidade de saldo e limites: Informar sobre a necessidade de saldo e limites transacionais da conta no momento da efetivação da transferência.
6. Início da autorização:  Exibir a data de início da autorização.
7. Prazo da autorização: Exibir a validade da autorização de acordo com o parâmetro definido pelo usuário, seja por uma data específica, por prazo indeterminado ou pela condição de atingimento de um limite previamente estabelecido.
8. Identificador da autorização: Exibir o número da autorização (número final do `consentId` , excluindo o prefixo `urn:instituicao:` ).
9. Limite de crédito: Informar que o uso do limite de crédito, quando disponível, em caso de transações com valor superior ao saldo disponível é habilitado por padrão e que pode ser desabilitado na ID.
Efetivação da autorização
1. Jornada Otimizada (saldo e limite): Quando aplicável, indicar que o saldo e o limite estão sendo compartilhados. Orientação: Quando aplicável, indicar que o compartilhamento de saldo e limite pode ser encerrado a qualquer momento na área de gestão.  Ex.: Acesse a área de gestão para encerrar o compartilhamento do saldo e limite a qualquer momento e manter a autorização ativa.
Efetivação da autorização - Jornada Otimizada#F4F5F7
## Recomendações - ITP
**Cenário: Efetivação da autorização**
1. Cancelamento da autorização: Informar sobre a possibilidade de cancelamento da autorização e, quando aplicável, o horário limite.
2. Alteração dos limites: Informar sobre a possibilidade de alteração dos limites da autorização.
3. Alteração das contas recebedoras: Informar sobre a possibilidade de alteração das contas recebedoras.
4. Recebimento de notificações: Informar sobre a possibilidade de alteração do recebimento de notificações, quando disponibilizadas.
Efetivação da autorização - Recomendações