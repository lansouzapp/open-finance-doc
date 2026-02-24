---
id: 1477284726
title: v.19.00.01 Requisitos e Requisitos - Hybrid flow com hand-off (Pagamentos)
version: 3
modified: 2026-01-23T19:32:55.984Z
url: /spaces/OF/pages/1477284726/v.19.00.01+Requisitos+e+Requisitos+-+Hybrid+flow+com+hand-off+Pagamentos
---

Requisitos e recomendações para o uso do Hybrid flow com Hand-off entre instituições nas etapas de Direcionamento e Redirecionamento em jornadas de Iniciação de Pagamento e Vinculação de Conta (JSR).**Nota:**Consulte o subcapítulo **Casos de erro - Pagamentos e JSR** para mais informações sobre os possíveis erros e como comunicá-los ao usuário nas etapas de **Direcionamento**e **Redirecionamento.**
# Etapa 2: Direcionamento
Após o usuário iniciar a transação de pagamento, a Instituição Iniciadora de Transação de Pagamento (ITP) deve direcionar o usuário para o ambiente - *app*ou *browser (desktop) -* da Instituição Detentora de Conta (ID) para que o usuário revise e confirme (ou cancele) a transação.#F4F5F7
## Requisitos - ITP
**Cenário: Tela de transição**
1. Informações sobre o direcionamento: Durante o direcionamento, exibir uma tela informativa, contendo as seguintes informações mínimas:   Indicação de que o direcionamento está em andamento. Indicação de que o direcionamento é seguro. Ex.: Estamos te levando com segurança para a [Instituição X]. Informação sobre o tempo para confirmar a iniciação de pagamento na ID conforme definido pelo tipo de transação. Ex.: Você tem até xx minutos para confirmar a transação.
Tela de transição ITP > ID#F4F5F7
## Requisitos - ID
**Cenário: Recepção do usuário**
1. Recepção do usuário no app : Em caso de direcionamento do browser (desktop) da ITP para aplicativo da ID, receber o usuário com mensagem com instruções para continuidade da jornada.
Recepção do usuário no app#F4F5F7
## Recomendações - ITP
**Cenário: Tela de transição**
1. Simplificação da jornada: Utilizar o menor número de interações possível para reduzir a fricção na jornada.
2. Apresentação da tela: Apresentar uma mensagem amigável e contextualizada na tela de transição, destacando as vantagens do direcionamento. Utilizar elementos visuais e textuais que reforcem o direcionamento, como loaders , animações, barras de progresso ou indicadores visuais.
3. Padrão visual: No browser (desktop) , seguir o padrão visual do aplicativo da instituição para garantir segurança e familiaridade ao usuário.
4. Alternativas para o direcionamento: Para facilitar o direcionamento do usuário do browser (desktop) da ITP para o aplicativo da ID, utilizar mecanismos como QR code dinâmico, código de ativação, entre outros. Utilizar DeepLink nas jornadas iniciadas em dispositivos móveis.
5. Prevenção de interrupções : Alertar sobre a possibilidade de falha na jornada em dispositivos com o recurso de ocultação de aplicativos ativado, orientando o usuário a desativar esse recurso se necessário.
Tela de transição ITP > ID - Recomendações#F4F5F7
## Recomendações - ID
**Cenário: Recepção do usuário**
1. Disponibilização do canal de acesso: Caso a ID possua mais de um canal disponível - app ou browser (desktop) - , oferecer a opção de acesso que julgar mais apropriada para a experiência do seu usuário.

# Etapa 4: Redirecionamento
Após o usuário confirmar, cancelar ou o tempo da transação expirar, a Instituição Detentora de Conta (ID) deve redirecionar o usuário para o ambiente - app ou browser (desktop)*-* da Instituição Iniciadora de Transação de Pagamento (ITP) para que ele possa visualizar o resultado da transação. #F4F5F7
## Requisitos - ID
**Cenário: Tela de transição**
1. Mensagem sobre o retorno à ITP: Exibir mensagem informando que a próxima etapa será o retorno para a ITP, onde o usuário visualizará a efetivação da transação.
2. Informações sobre o redirecionamento: Garantir que essa etapa seja somente informativa sem exigir qualquer ação adicional do usuário para confirmar o redirecionamento, contendo as seguintes informações mínimas: Indicação de que o redirecionamento está em andamento. Indicação de que o redirecionamento é seguro.
Redirecionamento ID > ITP#F4F5F7
## Recomendações - ID
**Cenário: Tela de transição**
1. Tela de transição: No browser (desktop), ao identificar que o usuário confirmou, cancelou ou que o tempo expirou, exibir a página de redirecionamento para a ITP.
Redirecionamento ID > ITP - Browser - Recomendação