---
id: 1436290040
title: Requisitos e Recomendações - Múltiplos Aprovadores (Dados)
version: 1
modified: 2026-01-12T19:25:46.769Z
url: /spaces/OF/pages/1436290040/Requisitos+e+Recomenda+es+-+M+ltiplos+Aprovadores+Dados
---

Os requisitos e recomendações para **Múltiplos Aprovadores** correspondem aos da Jornada Básica de Compartilhamento de Dados acrescidos dos requisitos e recomendações específicos descritos neste capítulo.**Atenção**: Por se tratar de um cenário com múltiplos aprovadores, que envolve um participante adicional na jornada, podem existir especificidades em relação às orientações da **Jornada Básica**. Em caso de divergência, prevalecem os requisitos e recomendações definidos neste capítulo.
# Etapa 4: Confirmação Múltiplos Aprovadores
DC Múltiplos Aprovadores - etapa 4Para casos nos quais seja necessária aprovação adicional, além do solicitante:#F4F5F7
## Requisitos - IT
**Cenário: Confirmação do usuário solicitante**
1. A autorização e a confirmação do consentimento devem ocorrer de acordo com os poderes já vigentes para a movimentação de conta nas políticas internas da Instituição Transmissora de Dados (ex.: estatutos, contratos sociais), sendo vedada a constituição de alçadas e poderes específicos para fins de compartilhamento de dados. As solicitações de compartilhamento de dados devem seguir as mesma dinâmica de alçada e fila de aprovação vigente para movimentações de conta fora do Open Finance, de acordo com a configuração de cada usuário dentro da instituição.
2. Caso a Instituição Transmissora de Dados já disponibilize em seus canais mecanismos para que representantes legais, devidamente constituídos, possam autorizar ou delegar poderes para outras pessoas, a funcionalidade deve ser estendida para o âmbito do Open Finance.
3. No caso de conta conjunta, desde que haja acesso eletrônico por titulares: Cada titular pode compartilhar apenas sua própria informação cadastral, sem depender da confirmação de todos os titulares da conta. A Instituição Transmissora de Dados somente deverá exigir a confirmação de todos os titulares da conta, para efetivar o compartilhamento de dados, caso o acesso a informações transacionais da conta dependa da autorização de todos os titulares.
4. A etapa de confirmação do usuário solicitante na Instituição Transmissora de Dados está sujeita a todos os requisitos gerais especificados para a etapa de confirmação e, adicionalmente, aos requisitos abaixo: A Instituição Transmissora de Dados deve especificar que serão necessárias uma ou mais aprovações adicionais, de acordo com a política de poderes de cada Instituição. Devem ser apresentadas instruções claras sobre o caminho dentro da Instituição Transmissora de Dados que o aprovador deve acessar para atuar e efetivar o compartilhamento. Deve estar especificado que o prazo máximo para atuação do(s) aprovador(es) é de 15 dias corridos, contados a partir da aprovação do consentimento pelo usuário solicitante. Deve estar claro que caso o prazo expire será necessário um novo pedido de compartilhamento. Ao concluir a etapa de confirmação, o solicitante deve ser redirecionado de volta para a Instituição Receptora de Dados.
Compartilhamento de dados - Confirmação do usuário solicitante**Cenário: Confirmação do aprovador**
1. Após a conclusão de todas as aprovações necessárias na Instituição Transmissora de Dados, o solicitante, que iniciou a jornada, deve ser notificado via canal eletrônico padrão da Instituição Transmissora de Dados sobre a atualização de status do consentimento.
2. Na perspectiva do aprovador, a etapa de confirmação deve ser realizada de forma assíncrona e estar disponível a partir do momento em que a confirmação pelo usuário solicitante tiver tido sucesso, obedecendo: O(s) aprovador(es) devem ser notificados via canal eletrônico padrão da Instituição Transmissora de Dados sobre a ação necessária (ex.: SMS, push etc.).
3. Dentro do fluxo de aprovação do aprovador devem estar incluídos os seguintes elementos: A tela de confirmação exibida ao aprovador deve conter, no mínimo, as mesmas informações de caracterização da operação que foram apresentadas ao usuário solicitante na etapa de confirmação na Instituição Transmissora de Dados. Deve ser apresentada uma identificação do usuário que iniciou a jornada e dos outros aprovadores envolvidos na operação, caso exista. Deve estar especificado que o prazo máximo para atuação do(s) aprovador(es) é de 15 dias corridos, contados a partir da aprovação do consentimento pelo solicitante. Deve estar claro que, caso o prazo expire, será necessário um novo pedido de compartilhamento.
Compartilhamento de dados - Confirmação do aprovador#F4F5F7
## Recomendações - IT
**Cenário: Geral**
1. A linguagem (“Termo para o Cliente”) presente no Glossário de Experiência pode ser simplificada, para evitar repetitividade, e apresentada de outras formas (p.ex.: no infinitivo).
2. Caso o usuário queira cancelar o compartilhamento de dados na etapa de confirmação da Transmissora, ela poderá mostrar um alerta para confirmar a ação do usuário. Sugestão: “Deseja cancelar o compartilhamento de dados?”.
3. Caso os aprovadores não tomem as ações necessárias em até 7 dias, recomenda-se que a Instituição Transmissora de Dados envie novas notificações para lembrar o usuário responsável pela aprovação da pendência, por meio de seu canal eletrônico padrão (SMS, push etc.).
4. De acordo com as especificações de Fase 2 mais recentes, a Instituição Receptora de Dados pode informar ao solicitante que o seu compartilhamento de dados está pendente de aprovação na Instituição Transmissora. Isso pode ser feito por meio de canais como SMS, push e outros.

# Etapa 6: Efetivação Múltiplos Aprovadores
DC Múltiplos Aprovadores - etapa 6Os requisitos listados neste capítulo de múltiplos aprovadores são adicionais aos requisitos listados para uma jornada de alçada simples. Dessa forma, todos requisitos de ambos os capítulos, quando aplicáveis, devem ser seguidos nos casos de múltiplos aprovadores.
 
Nos casos em que as orientações são conflitantes, prevalecem os requisitos a seguir:#F4F5F7
## Requisitos - IR
**Cenário: Tela do solicitante****Para casos nos quais seja necessária aprovação adicional, além do solicitante:**
1. Na perspectiva do solicitante, após ser redirecionado de volta da Instituição Transmissora de Dados, a Instituição Receptora de Dados deve: Apresentar uma tela comunicando o sucesso (ou insucesso) da etapa de confirmação da solicitação. Informar que a solicitação está pendente de aprovação e que, após a atuação do aprovador, a funcionalidade, finalidade ou benefício terão continuidade no ambiente da Instituição Receptora de Dados. Em caso de erro, o problema deve ser especificado ao usuário e deve ser acrescentada uma orientação para resolução, se possível.
**Nota:**Como o consentimento ainda não foi efetivado, não é necessário apresentar o resumo da solicitação. Compartilhamento de dados - Tela do solicitante#F4F5F7
## Requisitos - IT
**Cenário: Tela do aprovador****Para casos nos quais seja necessária aprovação adicional, além do solicitante:**
1. Na perspectiva do aprovador, após a confirmação no ambiente de Instituição Transmissora da Dados, deve ser apresentada: Uma tela comunicando o sucesso (ou insucesso) da etapa de aprovação do compartilhamento. Em caso de erro, o problema deve ser especificado ao usuário e deve ser acrescentada uma orientação para resolução, se possível.
Compartilhamento de dados - Tela do aprovador#F4F5F7
## Recomendações - IR
**Cenário: Geral**
1. Para casos com mais de um aprovador, é recomendado que a Receptora possibilite acesso rápido para a continuação da jornada pelo usuário, após a conclusão das aprovações na Transmissora. Type or paste something here to turn it into an excerpt.