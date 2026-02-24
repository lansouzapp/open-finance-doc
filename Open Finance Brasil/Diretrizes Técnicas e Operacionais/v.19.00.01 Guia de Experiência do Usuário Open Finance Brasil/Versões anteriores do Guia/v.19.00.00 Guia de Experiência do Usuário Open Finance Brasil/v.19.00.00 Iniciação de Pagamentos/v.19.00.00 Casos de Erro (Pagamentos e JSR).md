---
id: 1436292740
title: v.19.00.00 Casos de Erro (Pagamentos e JSR)
version: 1
modified: 2026-01-12T19:26:33.724Z
url: /spaces/OF/pages/1436292740/v.19.00.00+Casos+de+Erro+Pagamentos+e+JSR
---

Requisitos e recomendações para o tratamento e a comunicação de erros nas **Jornadas de Iniciação de Pagamento** e **Vinculação de Conta** para pagamentos sem redirecionamento (JSR) via Open Finance. 
# Mensagem de erro
**A mensagem de erro deve comunicar**o erro **com clareza**, **explicar**o que ocasionou o erro com **linguagem simples** e **fornecer orientação** e **opções de ação** para que o usuário consiga continuar.Boas práticas de experiência considerando os pilares: 
- O que houve com o usuário?
- O que ocasionou o erro?
- Orientações ao usuário.
- Ação necessária para prosseguir.
**Exemplo de erro:**
Um navegador de internet não foi localizado para direcionar e autenticar o usuário na Detentora.
- O que houve? Usuário não pôde ser direcionado.
- O que ocasionou o erro? O navegador de internet não foi encontrado no dispositivo do usuário.
- Orientações ao usuário Instalar um navegador de internet.
- Ações para prosseguir Tentar novamente.
- Mensagem de erro Não foi possível te direcionar para a [sua instituição]. Instale um navegador de internet e tente novamente.

# Casos de erro - Geral
Esta seção descreve os requisitos para tratar erros nas jornadas:
- Iniciação de Pagamento Com Redirecionamento.
- Iniciação de Pagamento Sem Redirecionamento (JSR).
- Vinculação de Conta para JSR .
Sempre que possível, identificar se o problema ocorreu na Instituição Iniciadora de Transação de Pagamento (ITP) ou na Instituição Detentora de Conta (ID), além do tipo de erro.
Quando o erro acontecer em ambiente da ID, esta deverá redirecionar o usuário ao ambiente da ITP junto com o código do erro específico, conforme as possibilidades descritas no **Diagrama de Sequência — Momento 3 - Etapa de Autorização do Cliente**, disponível no Portal do Desenvolvedor, onde deverá ocorrer a tratativa.
A tratativa na ITP deverá ser o mais específica possível a fim de evitar erros genéricos. 
Os casos de erros devem ser tratados conforme previsto nos regulamentos dos arranjos.Os requisitos estão organizados por **cenário, etapa** da jornada, **instituição** que deve comunicar o erro ao usuário, **ações necessárias** **para resolver o erro**e **exemplos de mensagem para comunicar o erro**de forma clara. Para casos que não estejam cobertos nesse capítulo, as instituições devem garantir que, diante de qualquer erro, o usuário seja sempre informado com clareza, sobre o que ocorreu e o que pode fazer a seguir. **Nota:**Consulte as seções de **Casos de erro** da jornada desejada ao longo desse subcapítulo para visualizar possíveis erros e exemplos de mensagens. #F4F5F7
## Requisitos - ITP
**Cenário: Erro genérico na ITP**
1. Mensagem de erro: Exibir mensagem de erro clara, orientando o usuário sobre como prosseguir.
Erro na ITP - Geral#F4F5F7
## Requisitos - ID
**Cenário: Erro genérico na ID**
1. Mensagem de erro: Comunicar o erro com clareza, orientando o usuário sobre como prosseguir.
Erro na ID - Geral
1. Redirecionamento:  Quando a solicitação não puder ser confirmada por conta de erros como indisponibilidade da conta, saldo insuficiente, falha de infraestrutura ou outros impedimentos, redirecionar o usuário para a ITP.
Redirecionamento pós-erro - ID**Atenção:**A informação sobre **insuficiência de saldo ou limite, com exceção de limite de crédito pré-aprovado, e a consequente desabilitação da conta**, deve ocorrer **apenas em transações de pagamento imediatas com Pix**.

Para **Pix Agendado, Pix Automático, Transferências Inteligentes e a jornada de Vinculação de Conta**, a validação de saldo e limite ocorre apenas **no momento da liquidação do pagamento,**e não durante a efetivação da solicitação. Nesses casos, o usuário deve ser informado sobre a indisponibilidade de saldo e limite **após a tentativa de liquidação do pagamento**através de, por exemplo, notificação via *push*. 

Consulte as seções de **Casos de Erro** da jornada desejada ao longo desse subcapítulo para visualizar possíveis erros e exemplos de mensagens.  **Cenário: Tratativa de erro pós-cancelamento por parte do usuário**
1. Manutenção do cancelamento: Respeitar a decisão do usuário de cancelar a transação mesmo que o cancelamento ocorra após a validação de algum erro (Ex.: Conta indisponível, Saldo insuficiente etc).
Manutenção do cancelamento mesmo após validação de erro - ID#F4F5F7
## Recomendações - ITP
**Cenário: Otimização da solicitação em caso de erro**
1. Manutenção dos dados da solicitação: Ao receber o usuário de volta após a identificação do erro, otimizar a nova solicitação, mantendo os dados corretos já preenchidos e indicando a alteração apenas da informação que causou o erro.
Otimização da solicitação em caso de erro - ITP
# Casos de erro - Pagamentos com Redirecionamento e Vinculação de Conta para JSR
Esta seção descreve os requisitos para tratar erros nas jornadas de:
- Iniciação de Pagamento Com Redirecionamento .
- Vinculação de Conta para JSR .
#F4F5F7
## Requisitos - ITP
**Cenário: Erros no direcionamento ITP > ID**
1. Erro genérico de direcionamento: Informar o usuário sobre a impossibilidade de direcioná-lo para a ID em caso de erro genérico.

- Etapa: Direcionamento ITP > ID
- Quem comunica: ITP
- Ações para prosseguir: Tentar novamente mais tarde.
- Exemplo de mensagem: Não foi possível te direcionar para a [Detentora] para confirmar a transação . Tente novamente mais tarde.
Falha no direcionamento - ITP#F4F5F7
## Requisitos - ID
**Cenário: Erros na autenticação/confirmação**
1. Falha de infraestrutura: Informar o usuário sobre a impossibilidade de concluir a autenticação/confirmação devido à falha de infraestrutura.

- Etapa: Autenticação/Confirmação
- Quem comunica: ID
- Ações para prosseguir: Tentar novamente mais tarde.
- Exemplo de mensagem:  Tivemos um problema com sua autenticação. Tente novamente mais tarde.
Falha de infraestrutura - Autenticação - ID
1. Dados divergentes: Informar o usuário sobre a impossibilidade de concluir a autenticação devido à divergência dos dados informados na ITP.

- Etapa: Autenticação
- Quem comunica: ID
- Ações para prosseguir: Tentar novamente com os dados corrigidos. / Alterar a conta de origem, se necessário.
- Exemplo de mensagem: Não foi possível prosseguir com a solicitação. Os dados informados não coincidem com os registrados na sua instituição. Verifique e tente novamente com as informações corretas.
Dados divergentes - ID
1. Conta indisponível: Informar o usuário sobre a indisponibilidade da conta impedindo-o de confirmar a transação através da desabilitação da conta.

- Etapa: Confirmação (tela de revisão)
- Quem comunica: ID
- Ações para prosseguir: Tentar novamente com outra conta de origem ou outra ID.
- Exemplo de mensagem: Conta indisponível. Ex.: tag
Conta indisponível - ID
1. Sessão expirada: Informar o usuário sobre a expiração do tempo para confirmação da solicitação.

- Etapa: Confirmação
- Quem comunica: ID
- Ações para prosseguir: Iniciar nova solicitação.
- Exemplo de mensagem: Sessão expirada. A solicitação não foi realizada pois o tempo expirou. Tente novamente.
Sessão expirada - ID
1. Usuário não autorizado (PJ): Informar o usuário que ele não possui poderes suficientes (PJ) para confirmar a solicitação iniciada.

- Etapa: Confirmação
- Quem comunica: ID
- Ações para prosseguir: Contatar a ID. / Contatar o titular principal da conta.
- Exemplo de mensagem: Você não tem autorização para concluir essa ação. Entre em contato conosco ou com o titular principal da conta para mais informações.
Usuário não autorizado - ID
#F4F5F7
## Requisitos - ID
**Cenário: Erros na tentativa de confirmação**
1. Prazo expirado: Informar sobre a expiração do prazo para efetivação do pagamento autorizado pelo usuário.

- Etapa: Após tentativa de confirmação
- Quem comunica: ID
- Ações para prosseguir: Iniciar nova solicitação.
- Exemplo de mensagem: Falha na solicitação. Sua solicitação falhou devido a problemas internos na [Iniciadora]. Tente novamente.
Falha na solicitação - ID
#F4F5F7
## Requisitos - ITP
**Cenário: Erros na efetivação**

1. Sistema indisponível: Informar o usuário sobre a indisponibilidade do sistema e sobre a possibilidade de a solicitação ter sido concluída no backend .

- Etapa: Redirecionamento ID > ITP/Efetivação
- Quem comunica: ITP
- Ações para prosseguir: Verificar se a solicitação foi efetivada na ID./Tentar novamente mais tarde caso a solicitação não tenha sido efetivada.
- Exemplo de mensagem: Sistema indisponível. Verifique na sua instituição se a solicitação foi concluída. Caso não tenha sido, tente novamente mais tarde.
Sistema indisponível - Transação pode ter sido concluída - ITP#F4F5F7
## Requisitos - ID e ITP
**Cenário: Erros na gestão**
1. Falha na revogação da solicitação: Informar o usuário sobre o erro na revogação da solicitação.

- Etapa: Gestão
- Quem comunica: A IF onde o usuário solicitou a revogação (ID ou ITP)
- Ações para prosseguir: Tentar novamente mais tarde.
- Exemplo de mensagem:  Falha no cancelamento. Não foi possível cancelar [a autorização de pagamento/vínculo de conta]. Tente novamente mais tarde.
Falha na revogação da solicitação - ID ou ITP
1. Falha na alteração da solicitação : Informar o usuário sobre o erro na alteração de algum parâmetro da solicitação.

- Etapa: Gestão
- Quem comunica: A IF onde o usuário solicitou a alteração (ID ou ITP)
- Ações para prosseguir: Tentar novamente mais tarde.
- Exemplo de mensagem: Falha na alteração. Não foi possível realizar essa alteração. Tente novamente mais tarde.
Falha na alteração da solicitação - ID ou ITP
# Casos de erro - Jornada de Iniciação de Pagamento com Redirecionamento
Esta seção descreve os requisitos para tratar erros nas jornadas de:
- Iniciação de Pagamento Com Redirecionamento .
**Nota**: Consulte a seção [Casos de erro na Jornada de Iniciação de Pagamento com Redirecionamento e Vinculação de Conta para JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1436292740/v.19.00.00+Casos+de+Erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)****para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
## Requisitos - ITP
**Cenário: Erros na solicitação**
1. QR Code inválido: Informar o usuário sobre a invalidade do QR Code informado.

- Etapa: Solicitação
- Quem comunica: ITP
- Ações para prosseguir: Tentar novamente com outro QR Code ou usar outra forma de pagamento.
- Exemplo de mensagem: QR Code inválido. O QR Code informado é inválido ou não pôde ser lido corretamente.
Erro na ITP - QR Code inválido#F4F5F7
## Requisitos - ID
**Cenário: Erros na confirmação**
1. Contas iguais: Informar o usuário sobre a impossibilidade de iniciar uma solicitação com contas de origem e destino iguais e impedir a confirmação da solicitação.

- Etapa: Confirmação
- Quem comunica: ID
- Ações para prosseguir: Tentar novamente com outra conta.
- Exemplo de mensagem: A conta de débito do pagamento não pode ser a mesma que a conta destino. Escolha outra conta para prosseguir.
Transação entre contas iguais - ID
1. Saldo (e limite de crédito) insuficiente: Se o usuário não possuir saldo e nem limite de crédito pré-aprovado, informá-lo sobre a insuficiência de saldo na conta escolhida, impedindo-o de confirmar a transação através da desabilitação da conta.

- Etapa: Confirmação (tela de revisão)
- Quem comunica: ID
- Ações para prosseguir: Tentar novamente com outra conta ou outra ID.
- Exemplo de mensagem: Saldo insuficiente (Ex.: Tag)
Saldo (e limite de crédito) insuficiente - IDSaldo (e limite de crédito) insuficiente - Múltiplas contas - ID 
1. Limite excedido: Informar o usuário que o valor da transação excede o limite da conta, impedindo-o de confirmar a transação através da desabilitação da conta.

- Etapa: Confirmação (tela de revisão)
- Quem comunica: ID
- Ações para prosseguir: Tentar novamente com outra conta de origem ou outra Detentora. / Ajustar o valor e tentar novamente.
- Exemplo de mensagem: Limite excedido. Ajuste o valor da transação e tente novamente.
Limite excedido - ID
1. Valor inválido: Informar o usuário que o valor informado na ITP está divergente do valor atual.

- Etapa: Confirmação (tela de revisão).
- Quem comunica: ID
- Ações para prosseguir: Iniciar nova solicitação.
- Exemplo de mensagem: Valor divergente. Não podemos prosseguir com a solicitação pois o valor informado na [Iniciadora] está divergente. Tente novamente.
Valor inválido - ID#F4F5F7
## Requisitos - ITP
**Cenário: Erros na gestão**
1. Cancelamento não permitido: Informar o usuário que não é possível cancelar a solicitação, pois ela já está cancelada ou liquidada.

- Etapa: Gestão de pagamentos
- Quem comunica: ITP
- Ações para prosseguir: Verificar na ID o estado atual do pagamento.
- Exemplo de mensagem: Cancelamento não permitido. Este pagamento já foi processado/cancelado. Verifique o status na sua instituição para confirmar a situação da transação.
Cancelamento não permitido - ITP
# Casos de erro - Jornada de Pix Automático
Esta seção descreve os requisitos para tratar erros na jornada:
- Pix Automático .
**Nota**: Consulte a seção [Casos de erro na Jornada de Iniciação de Pagamento com Redirecionamento e Vinculação de Conta para JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1436292740/v.19.00.00+Casos+de+Erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)****para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
## Requisitos - ITP
**Cenário: Erros na solicitação**
1. QR Code não pode ser lido na ITP: Se o usuário tentar fazer a leitura de um QR Code de Pix Automático em uma ITP que também não seja uma ID, informá-lo que o tipo de QR Code informado não pode ser lido na ITP.

- Etapa: Solicitação
- Quem comunica: ITP
- Ações para prosseguir: Utilizar os canais disponíveis para pagamento com Pix Automático acessando a opção diretamente na Detentora.
- Exemplo de mensagem: Esse tipo de QR Code não pode ser lido neste canal. Faça a leitura do QR Code na sua instituição bancária para realizar o pagamento.
QR Code não pode ser lido - ITP **Cenário: Erros na efetivação**
1. Falha do pagamento inicial avulso: Se o pagamento inicial avulso falhar, informar o usuário sobre a falha e a necessidade de contatar o recebedor ou ITP para regularizar a situação, sobre a manutenção da autorização de Pix Automático e sobre a possibilidade, a critério do recebedor, de cancelamento posterior da autorização.

- Etapa: Efetivação
- Quem comunica: ITP
- Ações para prosseguir: Contatar o recebedor ou ITP para regularizar o pagamento pendente.
- Exemplo de mensagem: Saldo insuficiente! Não foi possível concluir o pagamento de adesão com Pix, por falta de saldo na sua conta. A autorização de Pix Automático para [Empresa X] foi criada e poderá, a critério do recebedor, ser encerrada posteriormente. Entre em contato com o recebedor para regularizar o pagamento de adesão.
Falha no pagamento inicial avulso - ITP
#F4F5F7
## Requisitos - ID
**Cenário: Erros na liquidação do pagamento**
1. Falha após última tentativa de liquidação: Se após a última tentativa de liquidação, um pagamento da recorrência falhar, informar o usuário sobre a falha sem oferecer outros meios de pagamento.

- Etapa: Liquidação dos pagamentos
- Quem comunica: ID
- Ações para prosseguir: Contatar o recebedor ou ITP para regularizar a situação.
- Exemplo de mensagem: Pagamento não realizado. Não foi possível realizar o pagamento por falha de comunicação. Contate o recebedor ou a Iniciadora para regularizar.
Falha na liquidação do pagamento - ID
# Casos de Erro na Jornada Otimizada - Transferências Inteligentes e Vinculação de Conta para JSR
Esta seção descreve os requisitos para tratar erros nas jornadas de:
- Transferências Inteligentes com Jornada Otimizada (saldo e limite). .
- Vinculação de Conta com Jornada Otimizada (saldo e limite).
**Nota**: Consulte a seção [Casos de erro na Jornada de Iniciação de Pagamento com Redirecionamento e Vinculação de Conta para JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1436292740/v.19.00.00+Casos+de+Erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)****para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
## Requisitos - ITP
**Cenário: Erros na efetivação**
1. Falha na efetivação da Jornada Otimizada: Informar o usuário que a solicitação de Transferências Inteligentes ou Vinculação de Conta foi efetivada, mas o compartilhamento de saldo e limite falhou.

- Etapa: Efetivação
- Quem comunica: ITP
- Ações para prosseguir: Orientar o usuário conforme estratégia da instituição.
- Exemplo de mensagem: Falha no compartilhamento de saldo e limite. O vínculo de conta com a [Instituição] foi criado, mas o compartilhamento de saldo e limite falhou .
Falha na efetivação da Jornada Otimizada - ITP#F4F5F7
## Requisitos - ID e ITP
**Cenário: Erros na gestão**
1. Falha na revogação do compartilhamento de saldo e limite: Informar o usuário que a revogação do compartilhamento de saldo e limite falhou.

- Etapa: Gestão
- Quem comunica: A IF onde o usuário solicitou a revogação (ID ou ITP).
- Ações para prosseguir: Tentar novamente mais tarde.
- Exemplo de mensagem: Tivemos um problema com o encerramento do compartilhamento de saldo e limite. Tente novamente.
Falha na revogação do compartilhamento de saldo e limite - ID ou ITP
# Casos de erro - Jornada de Pagamentos Sem Redirecionamento (JSR)
Esta seção descreve os requisitos e recomendações para tratar erros nas jornadas de:
- Pagamento Sem Redirecionamento (JSR) .
**Nota**: Consulte a seção [Casos de erro na Jornada de Iniciação de Pagamento com Redirecionamento e Vinculação de Conta para JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1436292740/v.19.00.00+Casos+de+Erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)****para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
## Recomendações - ITP
**Cenário: Erros na liquidação do pagamento**
1. Limite do vínculo excedido: Informar o usuário sobre a impossibilidade de realizar o pagamento imediato com Pix com valor superior ao do vínculo de conta utilizado.

- Etapa: Liquidação do pagamento
- Quem comunica: ITP
- Ações para prosseguir: Ajustar o valor do pagamento e tentar novamente. / Tentar novamente com outro vínculo de conta que possua limite disponível.
- Exemplo de mensagem: Limite do vínculo excedido. O valor da transação excede o limite diário/por transação definido para este vínculo de conta. Altere o valor da transação ou use outra conta para concluir o pagamento.
Limite do vínculo excedido - ITP