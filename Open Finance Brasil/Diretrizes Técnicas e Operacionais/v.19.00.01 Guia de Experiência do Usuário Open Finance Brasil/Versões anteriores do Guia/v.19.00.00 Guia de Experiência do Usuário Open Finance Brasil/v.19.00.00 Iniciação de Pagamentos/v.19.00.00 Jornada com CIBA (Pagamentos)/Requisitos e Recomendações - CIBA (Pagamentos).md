---
id: 1436292542
title: Requisitos e Recomendações - CIBA (Pagamentos)
version: 1
modified: 2026-01-12T19:26:29.396Z
url: /spaces/OF/pages/1436292542/Requisitos+e+Recomenda+es+-+CIBA+Pagamentos
---

Requisitos e recomendações para as etapas de **Solicitação e Confirmação**nas jornadas de Iniciação de Pagamento com CIBA.
# Etapa 1: Solicitação
Solicitação de Iniciação de Transação de Pagamento na Instituição Iniciadora de Transação de Pagamento (ITP) para jornadas com CIBA#F4F5F7
## Requisitos - ITP
**Cenário: Salvar conta na etapa de Confirmação**
1. Para ser possível aplicar os benefícios de uma jornada com CIBA, é necessário que a origem de débito (conta) da Instituição Detentora de Conta tenha sido previamente salva na Instituição Iniciadora de Pagamento. Durante a etapa de confirmação na Instituição Detentora de Conta, em uma jornada de pagamento tradicional via Open Finance, caso ambas as instituições envolvidas tenham suporte para CIBA: Antes do redirecionamento e da resposta da autorização do pagamento, apresentar ao usuário a possibilidade “lembrar” esta Instituição para pagamentos futuros simplificados. Ao exibir a possibilidade de salvar conta entre Instituição Detentora e Iniciadora de Transação de Pagamento, deve se explicar os benefícios da funcionalidade através de uma mensagem, respeitando o tom de voz de cada instituição.
Salvar na conta na etapa de Confirmação**Nota:**Estes requisitos tem o objetivo de, em uma compra futura, permitir que a Iniciadora de Pagamentos mostre a conta salva ao usuário, possibilitando uma jornada de confirmação de pagamento facilitada através do CIBA (*Client Initiated Backchannel Authentication*). O prazo de vencimento da autorização determinado pela Instituição Detentora de Conta por meio das regras previstas no manual de experiência tem extensão mínima de 6 meses, podendo ser indeterminado a depender da escolha da Instituição Detentora de Conta**Cenário: Geral****Para jornadas nas quais sejam utilizadas contas previamente salvas com CIBA:**
1. A jornada de pagamento via CIBA está sujeita aos mesmos requisitos especificados para uma jornada de pagamentos tradicional via Open Finance, quando aplicáveis: Como não há redirecionamento automático em CIBA, os requisitos das etapas de redirecionamento não se aplicam à jornada CIBA. O restante dos requisitos, quando aplicáveis, são válidos para a jornada CIBA, exceto quando substituídos pelos requisitos listados neste capítulo.
2. Caso exista, sempre permitir que o usuário possa selecionar outra forma de pagamento ou seguir o fluxo de Open Finance com outra Detentora de Conta.
Pagamento com conta salva
1. Após a escolha de uma Detentora de Conta vinculada, a Iniciadora de Pagamento deve apresentar um aviso em tela com as seguintes informações: Orientação sobre a necessidade de confirmação do pagamento na Instituição Detentora de Conta. Tempo limite para execução dessa confirmação (5 minutos). Orientação para o usuário não fechar a tela de checkout da Iniciadora de Transação de Pagamento.
Informações sobre a confirmação da transação#F4F5F7
## Recomendações - ITP
**Cenário: Geral**
1. Apresentar ao usuário a possibilidade de pagamento mais rápido selecionando uma Detentora que já processou um pagamento anterior.
Seleção de ID já utilizada
# Etapa 3: Confirmação
Confirmação do pagamento na Instituição Detentora de Conta (ID) para jornadas com CIBA.#F4F5F7
## Requisitos - ID
**Cenário: Geral****Para jornadas nas quais sejam utilizadas contas previamente salvas com CIBA:**
1. O usuário deve ser notificado pela Instituição Detentora de Conta que há um pagamento pendente pelo do canal eletrônico padrão (p.ex.: SMS, push, e-mail etc).
2. Ao clicar na notificação, a jornada terá continuidade no ambiente da Instituição Detentora de Conta. Após a autenticação, o usuário deve ir diretamente para a tela de confirmação do pagamento.
3. Caso o usuário não clique na notificação e sim faça o acesso manual ao canal digital da Instituição Detentora de Conta, deve haver sinalização com destaque de que há uma pendência de confirmação de pagamento.
4. Após a confirmação, a Instituição Detentora de Conta deve orientar o usuário a voltar para o Instituição Iniciadora de Transação de Pagamento a fim de verificar a confirmação do pagamento.
Notificações sobre a transação**Nota:**Lembramos a possibilidade de facilitar ainda mais a jornada com CIBA, permitindo que o usuário aprove a transação clicando na notificação e/ou usando a biometria do dispositivo e/ou capturando a identificação do dispositivo, a critério dos requisitos de segurança e autenticação da Detentora.  
Requisitos e recomendações referentes à gestão de contas salvas estão disponíveis em "Gestão de contas salvas em CIBA"