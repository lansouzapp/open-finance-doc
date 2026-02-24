---
id: 1477284112
title: v.19.00.01 Requisitos e Recomendações - Pix Automático
version: 3
modified: 2026-02-10T18:07:41.658Z
url: /spaces/OF/pages/1477284112/v.19.00.01+Requisitos+e+Recomenda+es+-+Pix+Autom+tico
---

Requisitos e recomendações específicos das etapas de **Solicitação de Iniciação de Pagamento, Direcionamento ITP > ID, Confirmação, Redirecionamento ID > ITP e Efetivação** da jornada de pagamento com Pix Automático via Open Finance.**Nota:**Os requisitos e recomendações deste capítulo sobre **Pix Automático** complementam os de **Pix - Jornada Básica de Iniciação de Pagamento****.**Quando ambos forem aplicáveis, **todos os requisitos e recomendações devem ser observados.**   Em caso de conflito entre orientações, **prevalecem os requisitos e recomendações descritos neste capítulo.**
# Etapa 1: Solicitação de Iniciação de Pagamento
Nesta etapa, o usuário inicia a jornada de pagamento com Pix Automático via Open Finance no ambiente da Instituição Iniciadora de Transação de Pagamento (ITP), e — em caso de primeiro uso — é informado sobre as principais características do serviço, como configuração de valor máximo por transação, envio de notificações e política de retentativas.   Ele também escolhe a Instituição Detentora de Conta (ID) que será usada para realizar os pagamentos, insere e visualiza as demais informações da autorização.  A ITP é responsável por validar os dados inseridos, ocultar informações sensíveis e preparar a solicitação de iniciação de pagamento para envio à ID e, quando aplicável, exibir mensagens de erro claras ao usuário.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre o Pix Automático**
1. Onboarding: Disponibilizar, ao menos na primeira utilização do Pix Automático via Open Finance, informações claras sobre as principais regras do produto, incluindo, no mínimo: O que é o Pix Automático e suas vantagens. Funcionamento geral (autorização, agendamento, possibilidade de cancelamento do agendamento e da autorização). Possibilidade de configuração do valor máximo por transação, em caso de valores variáveis. Configuração do recebimento de notificações de agendamento, caso a ITP as envie. Regras de retentativas de liquidação em caso de saldo insuficiente, a critério do recebedor. Uso de limite de crédito pré-aprovado habilitado automaticamente e possibilidade de desabilitação na Detentora.
*Onboarding -*Primeiro uso
### Cenário: Autorização de Pix Automático
**Nota:**Consulte a etapa **Solicitação de Iniciação de Pagamento** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.A ITP deve possibilitar que o usuário insira e/ou revise as informações da autorização de pagamentos com Pix Automático conforme as regras do arranjo de pagamento. 
1. Valor máximo: Em caso de valores variáveis, permitir que o usuário defina o valor máximo de cada pagamento recorrente, podendo inclusive ser um valor indeterminado. Exibir mensagem informando que o valor máximo não pode ser inferior ao valor mínimo estabelecido pelo recebedor, quando aplicável. Ex.: O valor máximo não pode ser inferior a R$ 325,00. Exibir aviso claro ao usuário de que pagamentos com valor superior ao valor máximo configurado não serão efetivados e que ele poderá ser notificado para ajustar o limite ou buscar outras formas de pagamento. Ex.: Caso o valor do pagamento ultrapasse este valor, o pagamento não será realizado e você será avisado para ajustar o limite ou buscar outra forma de pagamento. Por se tratar de uma transação com Pix instantâneo, informar que o valor do pagamento inicial avulso, quando aplicável, não está sujeito ao valor máximo definido e sim ao limite transacional do arranjo Pix. Ex.: O pagamento inicial está sujeito ao limite do arranjo Pix.
Autorização de Pix Automático - Valor máximo
1. Descrição da autorização: Disponibilizar um campo para que o usuário preencha opcionalmente uma descrição para a autorização (via campo `additionalInformation` ).    Ex.: Introdução à Música Clássica, Conta de Energia etc.
2. Identificação do pagador: Exibir nome e CPF (mascarado) ou CNPJ.
3. Identificação do recebedor: Exibir CNPJ e, quando existir, o Nome Fantasia da empresa recebedora. Caso contrário, exibir o Nome Empresarial/Razão Social.
4. Identificador da cobrança: Exibir o identificador da cobrança. Ex.: Número do contrato, código do usuário etc.
5. Data do primeiro pagamento: Exibir a data prevista do primeiro pagamento da recorrência.
6. Periodicidade: Exibir a periodicidade dos pagamentos futuros conforme estabelecido pelo recebedor (Semanal, Mensal, Trimestral, Semestral ou Anual).
7. Início da autorização: Exibir a data de início da autorização.
8. Prazo da autorização: Exibir a data de validade da autorização, inclusive quando for indeterminada.
9. Regras de retentativas: Exibir as regras de retentativas de efetivação de pagamento após a data de vencimento conforme definido pelo recebedor e de acordo com as regras do arranjo de pagamento. Informar sobre a possibilidade de incidência de juros e multas em caso de falha na efetivação do pagamento na data de vencimento, a critério do recebedor, no próximo pagamento da recorrência.
Autorização de Pix Automático - Geral
1. Pagamento inicial avulso: Em caso de pagamento inicial avulso à recorrência, exibir, com destaque, as informações mínimas aplicáveis a um pagamento instantâneo com Pix, conforme as regras do arranjo. Descrição do pagamento: Disponibilizar um campo para que o usuário preencha opcionalmente uma descrição para o pagamento (via campo `remittanceInformation` ).   Valor do pagamento: Exibir o valor do pagamento. Data do pagamento: Exibir a data do pagamento. Ex.: Imediato Omissão de dados bancários do recebedor: Omitir o número da agência, número da conta e a instituição bancária do recebedor. Necessidade de saldo e limites disponíveis: Caso o pagamento inicial avulso seja imediato, informar sobre a necessidade de saldo e limite Pix para efetivação do pagamento.
Pagamento inicial avulso#F4F5F7
## Recomendações - ITP
**Cenário: Autorização de Pix Automático com vínculo de conta****Para casos em que a ITP oferece a Jornada de Pagamento Sem Redirecionamento (JSR) a partir do Pix Automático**
1. Pix Automático em JSR: Se o usuário não possuir nenhuma conta vinculada, informar que é necessário fazer um vínculo previamente e direcioná-lo para a jornada de Vinculação de Conta .
Pix Automático com Vinculação de Conta
# Etapa 2: Direcionamento
Nesta etapa, o usuário é direcionado da Instituição Iniciadora de Transação de Pagamento (ITP) para a Instituição Detentora de Conta (ID) para se autenticar, revisar e confirmar a autorização de pagamento. A ITP deve orientar o usuário sobre o direcionamento e assegurar que a navegação ocorra de forma transparente, conforme o dispositivo utilizado. Além disso, quando aplicável, a ITP deve exibir mensagens de erro claras ao usuário.#F4F5F7
## Requisitos - ITP
**Cenário: Tela de transição****Nota:**Consulte a etapa **Direcionamento** no subcapítulo**Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.
1. Tempo de conclusão:   Informar que o usuário possui até 60 minutos para confirmar a autorização de pagamento na ID.      Ex.: Você tem até 60 minutos para finalizar a transação.
Tela de transição ITP > ID
# Etapa 3: Confirmação
Nesta etapa, o usuário se autentica na Instituição Detentora de Conta (ID) e pode, em caso de múltiplas contas de débito, escolher a que deseja usar para fazer o(s) pagamento(s). Ele também revisa as informações da autorização enviadas pela Instituição Iniciadora de Transação de Pagamento (ITP) e confirma a transação.  A ID deve garantir um ambiente seguro para autenticação, exibir o resumo da autorização, permitir a edição da conta de débito, em caso de múltiplas contas, e viabilizar a confirmação com o mínimo de fricção. Também é sua responsabilidade, em caso de falha, exibir mensagens de erro claras ao usuário, comunicar o resultado da transação à Instituição Iniciadora de Transação de Pagamento (ITP), enviar notificações ao usuário e, quando aplicável, aos demais aprovadores — em casos de múltiplas alçadas ou falha na conclusão da autorização.#F4F5F7
## Requisitos - ID
**Cenário: Revisão e confirmação da autorização****Nota:**Consulte a etapa **Confirmação** no subcapítulo**Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.
1. Identificação do recebedor: Exibir o CNPJ, Nome Fantasia ou Nome Empresarial/Razão Social conforme informados pela ITP.
2. Identificação do pagador: Exibir nome e CPF (mascarado) ou CNPJ.
3. Identificador da cobrança: Exibir o identificador da cobrança. Ex.: Número do contrato, código do usuário etc.
4. Valor máximo: Exibir valor máximo a ser transacionado, inclusive em caso de valor indeterminado, quando aplicável.
5. Periodicidade: Exibir a periodicidade dos pagamentos futuros conforme informado pela ITP (Semanal, Mensal, Trimestral, Semestral ou Anual).
6. Descrição da autorização: Exibir descrição da autorização, se preenchido pelo usuário pagador na ITP (via campo `additionalInformation` ). Ex.: Introdução à Música Clássica, Conta de Energia.
7. Data do primeiro pagamento: Exibir a data prevista do primeiro pagamento da recorrência.
8. Início da autorização: Exibir data de início da autorização.
9. Prazo da autorização: Exibir a data de validade da autorização, inclusive quando for indeterminada.
10. Pagamento inicial avulso: Em caso de pagamento inicial avulso à recorrência, exibir, com destaque, as informações mínimas aplicáveis a um pagamento instantâneo com Pix, conforme as regras do arranjo. Valor do pagamento: Exibir o valor do pagamento. Data do pagamento: Exibir a data do pagamento. Descrição do pagamento: Exibir a descrição do pagamento, se preenchido pelo usuário pagador na ITP (via campo `remittanceInformation` ).    Ex.: Taxa de adesão, Matrícula, Taxa de instalação etc. Omissão do dados bancários do recebedor: Omitir o número da agência, número da conta e instituição do recebedor.
11. Possibilidade de retentativas: Exibir informação sobre a existência de retentativas de efetivação de pagamento.
12. Juros e multas: Exibir informação sobre a possibilidade de incidência de juros e multas em caso de falha na efetivação do pagamento na data de vencimento, a critério do recebedor, no próximo pagamento da recorrência.
13. Informações complementares : Exibir qualquer informação adicional exigida pelo arranjo de pagamento, conforme a regulação vigente.
Revisão e confirmação da autorização - ID#F4F5F7
## Recomendações - ID
**Cenário: Revisão e confirmação da autorização**
1. Envio de notificações: Informar o usuário, na tela de confirmação, que notificações serão enviadas quando os próximos pagamentos forem agendados e que o usuário pode desabilitar essas notificações na área de gestão.

# Etapa 4: Redirecionamento
**Nota:**A etapa **Redirecionamento******está detalhada no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento.**Tela de transição ID > ITP
# Etapa 5: Efetivação
Nesta etapa final da jornada, o usuário é recebido no ambiente da Instituição Iniciadora de Transação de Pagamento (ITP)onde visualiza o resultado da solicitação.   A ITP deve apresentar com clareza o status e resumo da solicitação, com mensagens de sucesso ou falha, e disponibilizar um comprovante com os principais dados da transação.  Essa etapa também pode envolver orientações em caso de erro ou pendências, como autorizações em múltiplas alçadas, transações temporizadas ou indisponibilidade momentânea dos sistemas.#F4F5F7
## Requisitos - ITP
**Cenário: Efetivação da autorização****Nota:**Consulte a etapa **Efetivação** no subcapítulo**Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.
1. Status da autorização: Exibir o status da autorização (sucesso ou falha) com todas as informações exigidas pelo arranjo de pagamento.
2. Pagamento inicial avulso: Quando aplicável, exibir os dados do pagamento inicial avulso com todas as informações mínimas aplicáveis a um pagamento instantâneo com Pix, conforme as regras do arranjo.
3. Necessidade de saldo e limites disponíveis: Informar sobre a necessidade de saldo e limites transacionais da conta no momento da efetivação do pagamento.
4. Alteração do valor máximo: Informar o usuário, quando aplicável, que o valor máximo pode ser alterado.
5. Uso do limite de crédito: Informar que o uso do limite de crédito, quando disponível, em caso de transações com valor superior ao saldo disponível é habilitado por padrão e que pode ser desabilitado na Detentora.
Efetivação da autorização