---
id: 157450475
title: Máquina de estados - v1.0.0-rc.1 - API Pagamentos sem Redirecionamento
version: 2
modified: 2023-08-14T21:23:04.482Z
url: /spaces/OF/pages/157450475/M+quina+de+estados+-+v1.0.0-rc.1+-+API+Pagamentos+sem+Redirecionamento
---

## Vinculação de Conta

#### AWAITING_AUTHORISATION
O Vínculo da conta começa no status **AWAITING_AUTHORISATION,**a transição de status para **AWAITING_ACCOUNT_HOLDER_VALIDATION** é feita no tempo de até 5 minutos, caso contrário é alterado para **REJECTED**ou****na situação de cancelamento do usuário
#### AWAITING_ACCOUNT_HOLDER_VALIDATION
Estado transitório para o redirecionamento, onde são recebidos os sinais de riscos e validações das credências do vínculo da conta no tempo de até 15 minutos, onde o seu estado é alterando para **AWAITING_ENROLLMENT**, caso não haja o recebimento dos sinais, validações e redirecionamento o status e alterado para **REJECTED**
#### AWAITING_ENROLLMENT
Possui uma janela de 5 minutos para a expiração, caso o usuário não conclua o *enrollment*do seu dispositivo, o estado deve ser alterado para **REJECTED.**
#### AUTHORISED
O usuário possui uma janela de 5 minutos para expiração após a vinculação da conta para concluir a autorização enviando suas credenciais a detentora, caso usuário não conclua a autorização, o estado deve ser alterado para **REVOKED**. Com isso, o dispositivo do usuário estará apto a realizar transações sem redirecionamento entre ITP e detentora.
#### REJECTED
Se o usuário não respeitar a janela máxima de tempo para conclusão de alguma etapa anteriormente citada, o *enrollment*deve ser enviado para o estado **REJECTED.**Também pode ocorrer caso seja detectado algum tipo de fraude na tentativa de *enrollment*.
#### REVOKED
O usuário, após ter concluído todo o processo de *enrollment*, decide cancelar o vínculo. Pode ocorrer tanto através da ITP quanto no ambiente da Detentora de Conta, uma vez que com a perda/roubo do dispositivo o usuário deve ter como cancelar seu vínculo nos canais da Detentora de Conta e do ITP
## Iniciação de Pagamentos
Será utilizada a máquina de estados vigente da API de Pagamentos conforme especificado na página [Máquina de Estados - v3.0.0-beta.2 - Pagamentos](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/142671991/M+quina+de+Estados+-+v3.0.0-beta.2+-+Pagamentos).