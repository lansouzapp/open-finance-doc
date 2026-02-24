---
id: 1436292600
title: Requisitos e Recomendações - Múltiplos Aprovadores (Pagamentos)
version: 2
modified: 2026-01-16T14:35:35.802Z
url: /spaces/OF/pages/1436292600/Requisitos+e+Recomenda+es+-+M+ltiplos+Aprovadores+Pagamentos
---

Requisitos e recomendações para jornadas de pagamento via Open Finance cuja transação necessita de aprovação de mais de um usuário.**Nota:**Os requisitos e recomendações deste capítulo sobre jornada de transações com múltiplos aprovadores são complementares aos definidos para todas as jornadas de pagamento via Open Finance — como Pix Imediato, Pix Agendado, Pix Automático ou Transferências Inteligentes. Portanto, devem ser observados também os requisitos e recomendações da jornada em questão.Em caso de conflito entre orientações, prevalecem os requisitos e recomendações descritos neste capítulo. 
# Etapa 3: Confirmação
Confirmação da transação na Instituição Detentora de Conta (ID) para jornadas de iniciação de pagamentos com múltiplos aprovadores. #F4F5F7
## Requisitos - ID
**Cenário: Geral**
1. Manutenção da dinâmica de aprovação: Seguir os poderes vigentes para movimentação de conta, conforme as políticas internas da instituição (Ex.: Estatutos e contratos sociais), assegurando que as jornadas de iniciação de pagamento adotem a mesma dinâmica de alçadas e filas de aprovação já aplicáveis a pagamentos fora do Open Finance, sem a criação de regras específicas.
2. Delegação de poderes: Estender para o âmbito do Open Finance os mecanismos já disponibilizados nos canais da instituição que permitam a representantes legais devidamente constituídos autorizar ou delegar poderes a outras pessoas.
**Cenário: Confirmação do usuário solicitante**
1. Aprovações adicionais: Informar o usuário solicitante sobre a necessidade de aprovações adicionais, conforme a política de poderes da instituição.
2. Prazo para atuação: Informar o usuário solicitante sobre o prazo para atuação dos demais representantes e da necessidade de reinício do processo caso o prazo expire.
Tela do solicitante - Prazo para atuação
1. Pagamento acima do limite: Quando aplicável, exibir mensagem informando o solicitante que o pagamento ultrapassa o limite da conta selecionada e que só será efetuado após a última aprovação necessária, desde que o limite seja ajustado em tempo hábil e de acordo com os critérios da instituição para a conta.
Valor acima do limite
1. Redirecionamento para ITP: Redirecionar o usuário solicitante para a ITP após a confirmação da transação.
**Cenário: Confirmação do usuário aprovador**
1. Atuação do aprovador: Permitir a atuação do usuário aprovador de forma assíncrona após a confirmação do usuário solicitante.
2. Informações da transação: Exibir, no mínimo, as mesmas informações da transação apresentadas ao usuário solicitante na etapa de confirmação. Exibir identificação do usuário solicitante. Quando aplicável, informar sobre demais pendências de aprovação.
3. Prazo para atuação: Informar o usuário aprovador sobre o prazo para atuação conforme o tipo de transação e da necessidade de reinício do processo caso o prazo expire.
Confirmação do usuário aprovador
1. Resultado da transação: Após atuação do usuário aprovador, exibir mensagem informando sobre o resultado da transação.
Confirmação do usuário aprovador - Resultado da solicitação#F4F5F7
## Recomendações - ID
**Cenário: Confirmação do usuário aprovador**
1. Acesso à confirmação: Permitir a atuação dos usuários aprovadores através do acesso ao ambiente Open Finance ou de outro fluxo já existente na instituição.
2. Identificação do usuário solicitante: Identificar o usuário solicitante através de seu nome e CPF (mascarado).
Confirmação do usuário aprovador - Recomendações
# Etapa 5: Efetivação
Efetivação da transação na Instituição Iniciadora de Transação de Pagamento (ITP) para jornadas de iniciação de pagamentos com múltiplos aprovadores. #F4F5F7
## Requisitos - ITP
**Cenário: Tela do solicitante**
1. Informação sobre pendência de aprovação: Informar que a solicitação está pendente e será confirmada após aprovação dos demais aprovadores. Ex.: A transação só será concluída após confirmação de todos os aprovadores.
2. Prazo para atuação: Informar o usuário solicitante sobre o prazo para atuação dos demais representantes e da necessidade de reinício do processo caso o prazo expire.  Ex.: Os aprovadores têm até DD/MM/AAAA às HH:MM para confirmar a transação. Após essa data, uma nova ordem de pagamento deverá ser criada.
Tela do solicitante - Pendência