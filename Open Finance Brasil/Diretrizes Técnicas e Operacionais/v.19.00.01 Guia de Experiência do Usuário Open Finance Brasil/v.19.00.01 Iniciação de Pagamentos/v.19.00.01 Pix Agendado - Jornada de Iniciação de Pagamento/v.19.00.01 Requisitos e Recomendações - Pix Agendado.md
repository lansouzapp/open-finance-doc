---
id: 1477283715
title: v.19.00.01 Requisitos e Recomendações - Pix Agendado
version: 1
modified: 2026-01-23T17:46:51.251Z
url: /spaces/OF/pages/1477283715/v.19.00.01+Requisitos+e+Recomenda+es+-+Pix+Agendado
---

Requisitos e recomendações das etapas de **Solicitação de Iniciação de Pagamento, Direcionamento ITP > ID, Confirmação, Redirecionamento ID > ITP e Efetivação** da jornada de pagamento agendado (único ou recorrente) com Pix via Open Finance. **Nota:**Os requisitos e recomendações deste capítulo sobre **Pix Agendado** complementam os da **Pix - Jornada Básica de Iniciação de Pagamento**. Quando ambos forem aplicáveis, **todos os requisitos e recomendações devem ser observados.** Em caso de conflito entre orientações, **prevalecem os requisitos e recomendações descritos neste capítulo**.
# Exemplos de casos de uso

### Agendamentos recorrentes com Pix
Possibilita agendamentos de pagamentos de parcelas fixas. Útil para pagamentos frequentes a varejistas, pessoas físicas ou serviços de streaming, como:
- Pagamento de aluguel.
- Pagamento de serviços.
- Remessas recorrentes.
- Doações.

# Etapa 1: Solicitação de Iniciação de Pagamento
Nesta etapa, ao iniciar a jornada de pagamento com Pix via Open Finance, o usuário escolhe a Instituição Detentora da Conta (ID) que será usada para realizar o(s) pagamento(s), agenda o pagamento de forma única ou recorrente e configura outros parâmetros como valor e dados do recebedor. Em seguida, ele revisa os dados configurados e visualiza as demais informações da autorização que será enviada à ID.      A Instituição Iniciadora de Transação de Pagamento (ITP) é responsável por validar os dados inseridos, ocultar informações sensíveis, preparar a solicitação de iniciação de pagamento para envio à ID e, quando aplicável, exibir mensagens de erro claras ao usuário.#F4F5F7
## Requisitos - ITP
**Cenário: Autorização de Pix Agendado****Nota:**Consulte a etapa **Solicitação de Iniciação de Pagamento** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.A ITP deve possibilitar que o usuário insira e/ou revise as informações do agendamento conforme as regras do arranjo Pix e a forma de iniciação de pagamento selecionada. 
1. Data do agendamento: Possibilitar que o usuário insira a data do agendamento único ou escolha a recorrência dos agendamentos.
2. Datas inexistentes: Em caso de agendamento para datas inexistentes (Ex.: Dias 29, 30 e 31 de determinados meses), informar que o pagamento será efetivado no dia posterior.
Data do agendamento**Para agendamentos únicos**
1. Data do agendamento: Permitir que o usuário insira a data do pagamento dentro do período de até 24 meses a partir da data da solicitação
2. Prazo da autorização: Exibir a data de validade da autorização como a mesma data do agendamento único.
Agendamento único**Para agendamentos recorrentes**
1. Quantidade de recorrências: Permitir que o usuário agende até 60 recorrências de pagamentos em uma única autorização, dentro do período de até 24 meses a partir da data de solicitação, independentemente do modelo de recorrência definido na autorização (diário, semanal, mensal ou customizado).
2. Data do último pagamento: Se o usuário definir uma data final para a recorrência, impossibilitar a edição do número de recorrências.
3. Número de recorrências: Se o usuário definir um número de recorrências, exibir automaticamente a data do último pagamento.
4. Periodicidade: Exibir, com clareza, a periodicidade dos agendamentos escolhida pelo usuário.
5. Prazo da autorização: Exibir a data de validade da autorização como a mesma data do último pagamento agendado.
Agendamento recorrente
1. Recorrências padronizadas: Seguir o padrão seguinte para informar a data de encerramento e/ou número de recorrências do agendamento:

| TIPO | ENCERRAMENTO | PADRÃO DE CAMPO DE TEXTO | EXEMPLO |
| --- | --- | --- | --- |
| Mensal | Encerra após uma data. | Mensal, todo dia {número}, até {dd/mm/aa}. | Periodicidade da recorrência: Mensal, até 18/10/2024. |
| Mensal | Encerra após um número de ocorrências. | Mensal, todo dia {número}, {número ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: Mensal, todo dia 10, 2 ocorrências, até 18/12/2023. |
| Semanal | Encerra após uma data. | Semanal, toda(o) {dia da semana}, até {dd/mm/ aa}. | Periodicidade da recorrência: Semanal, toda terça-feira, até 31/12/2023. |
| Semanal | Encerra após um número de ocorrências. | Semanal, toda(o) {dia da semana}, {número} ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: Semanal, toda terça-feira, 4 ocorrências, até 31/12/2023. |
| Diário | Encerra após uma data. | Diário, até {dd/mm/aa}. | Periodicidade da recorrência: Diário, até 31/12/2023. |
| Diário | Encerra após um número de ocorrências. | Diário, {número} ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: Diário, 5 ocorrências, até 31/12/2023. |

1. Recorrências customizadas: Seguir o padrão seguinte para informar a data de encerramento e/ou número de recorrências do agendamento:

| TIPO | ENCERRAMENTO | PADRÃO DE CAMPO DE TEXTO | EXEMPLO |
| --- | --- | --- | --- |
| Customizado anual | Encerra após uma data. | A cada {número} ano(s), até {dd/mm/aa}. | Periodicidade da recorrência: A cada 1 ano(s), até 18/10/2024. |
| Customizado anual | Encerra após um número de ocorrências. | A cada {número} ano(s), {número} ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: A cada 1 ano(s), 2 ocorrências, até 18/10/2024. |
| Customizado mensal | Encerra após uma data. | A cada {número} mês(es), todo dia {número, ...}, até {dd/mm/aa}. | Periodicidade da recorrência: A cada 2 mês(es), todo dia 10 e 20, até 18/10/2024. |
| Customizado mensal | Encerra após um número de ocorrências. | A cada {número} mês(es), todo dia {número, ...}, {número} ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: A cada 2 mês(es), todo dia 10 e 20, 6 ocorrências, até 18/10/2024. |
| Customizado semanal | Encerra após uma data. | Semanalmente na {dia da semana, ...}, até {dd/ mm/aa}. | Periodicidade da recorrência: Semanalmente na terça-feira e quinta-feira, até 31/12/2023. |
| Customizado semanal | Encerra após um número de ocorrências. | Semanalmente na {dia da semana, ...}, {número} ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: Semanalmente na terça-feira e quinta-feira, 4 ocorrências, até 31/12/2023. |
| Customizado diário | Encerra após uma data. | A cada {número} dia(s), até {dd/mm/aa}. | Periodicidade da recorrência: A cada 2 dia(s), até 31/12/2023. |
| Customizado diário | Encerra após um número de ocorrências. | A cada {número} dia(s), {número} ocorrências, até {dd/mm/aa}. | Periodicidade da recorrência: A cada 2 dia(s), 5 ocorrências, até 31/12/2023. |

# Etapa 2: Direcionamento
**Nota:**A etapa **Direcionamento** está detalhada no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento**Tela de transição - ITP > ID
# Etapa 3: Confirmação
Nesta etapa, o usuário se autentica na Instituição Detentora de Conta (ID) e pode, em caso de múltiplas contas de débito, escolher a que deseja usar para fazer o(s) pagamento(s). Ele também revisa as informações da autorização enviadas pela Instituição Iniciadora de Transação de Pagamento (ITP) e confirma a transação.   A ID deve garantir um ambiente seguro para autenticação, exibir o resumo da autorização, permitir a edição da conta de débito, em caso de múltiplas contas, e viabilizar a confirmação com o mínimo de fricção. Também é sua responsabilidade, em caso de falha, exibir mensagens de erro claras ao usuário, comunicar o resultado da transação à ITP, enviar notificações ao usuário e, quando aplicável, aos demais aprovadores — em casos de múltiplas alçadas ou falha na conclusão da autorização.Digite ou cole algo aqui para o transformar em um trecho.#F4F5F7
## Requisitos - ID
**Cenário: Revisão e confirmação do agendamento****Nota:**Consulte a etapa **Confirmação** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.Após o usuário se autenticar, a ID deve exibir todas as informações do agendamento informadas pela ITP.
1. Data do agendamento: Exibir a data do agendamento único ou do primeiro pagamento da recorrência.
2. Prazo da autorização: Exibir a data de validade da autorização (mesma data do agendamento único ou do último pagamento da recorrência).
Revisão e confirmação do agendamento - Geral**Para agendamentos recorrentes**
1. Periodicidade: Exibir a periodicidade da recorrência (Diária, Semanal, Mensal ou Customizado).
2. Número de recorrências: Exibir o número de recorrências, se informado pela ITP.
Revisão e confirmação do agendamento recorrente#F4F5F7
## Recomendações - ID
**Cenário: Revisão e confirmação do agendamento**
1. Exibição de limites disponíveis: Exibir o limite transacional disponível da conta para que o usuário possa considerá-lo na data de efetivação do pagamento. Quando o limite disponível for inferior ao valor do pagamento agendado, destacar essa informação e exibir uma mensagem orientando o ajuste necessário para garantir a efetivação do pagamento.  Ex.: O valor do pagamento agendado é superior ao seu limite diário Pix Agendado. Ajuste o limite até a data programada para garantir que o pagamento será efetuado.
Revisão e confirmação do agendamento - Limite disponível - Recomendação
# Etapa 4: Redirecionamento
**Nota:**A etapa **Redirecionamento** está detalhada no subcapítulo**Pix - Jornada Básica de Iniciação de Pagamento**.Tela de transição ITP > ID
# Etapa 5: Efetivação
Nesta etapa final da jornada, o usuário é recebido no ambiente da Instituição Iniciadora de Transação de Pagamento (ITP) onde visualiza o resultado do agendamento.    A ITP deve apresentar com clareza o status e resumo do agendamento, com mensagens claras de sucesso ou falha, e disponibilizar um comprovante com os principais dados do agendamento.    Essa etapa também pode envolver orientações em caso de erro ou pendências, como autorizações em múltiplas alçadas, transações temporizadas ou indisponibilidade momentânea dos sistemas.#F4F5F7
## Requisitos - ITP
**Cenário: Efetivação do agendamento****Nota:**Consulte a etapa **Efetivação** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.
1. Data do agendamento: Exibir a data do agendamento único ou do primeiro pagamento da recorrência.
2. Necessidade de saldo e limites: Informar ao usuário que a transação estará sujeita à disponibilidade de saldo e limites transacionais da conta de débito no momento da efetivação do pagamento.     Ex.: Você precisa ter saldo e limite diário Pix Agendado disponíveis na sua conta na data agendada do pagamento.
**Para agendamentos únicos**
1. Identificador do pagamento: Exibir o número da transação ( `endToEndId` do Pix).
Efetivação do agendamento único**Para agendamentos recorrentes**
1. Identificador da autorização: Exibir o número da autorização (número final do `consentId` , excluindo o prefixo `urn:instituicao:` )
Efetivação do agendamento recorrente#F4F5F7
## Recomendações - ITP
**Cenário: Efetivação do agendamento**
1. Efetivação do agendamento: Exibir mensagem informando que a efetivação diz respeito ao agendamento e não à efetivação dos pagamentos agendados em si.    Ex.: Pagamentos agendados com sucesso!
2. Cancelamento dos agendamentos: Informar sobre a possibilidade de cancelamento do(s) agendamento(s) e o horário limite conforme definido pelo arranjo de pagamento Pix Agendado.    Ex.: Você pode cancelar o pagamento até às 23:59 do dia anterior à data agendada.
Efetivação do agendamento - Recomendações