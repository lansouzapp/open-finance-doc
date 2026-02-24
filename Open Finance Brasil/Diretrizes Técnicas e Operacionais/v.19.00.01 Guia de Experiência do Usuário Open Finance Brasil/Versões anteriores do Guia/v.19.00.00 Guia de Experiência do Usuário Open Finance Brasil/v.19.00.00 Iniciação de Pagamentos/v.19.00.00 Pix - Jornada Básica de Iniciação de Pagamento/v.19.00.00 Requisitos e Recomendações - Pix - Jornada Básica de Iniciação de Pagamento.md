---
id: 1436290196
title: v.19.00.00 Requisitos e Recomendações - Pix - Jornada Básica de Iniciação de Pagamento
version: 2
modified: 2026-01-18T13:56:20.795Z
url: /spaces/OF/pages/1436290196/v.19.00.00+Requisitos+e+Recomenda+es+-+Pix+-+Jornada+B+sica+de+Inicia+o+de+Pagamento
---

Requisitos e recomendações para a jornada de pagamento instantâneo com Pix via Open Finance. Este subcapítulo está organizado em cinco etapas principais — **Solicitação de Iniciação de Pagamento, Direcionamento ITP > ID, Confirmação, Redirecionamento ID > ITP e Efetivação**— com foco no seguinte cenário: 
**pagamento instantâneo com Pix, alçada simples e redirecionamento entre instituições no mesmo dispositivo.** **Nota:**Essa jornada representa o fluxo básico para pagamentos com Pix via Open Finance. Os requisitos e recomendações descritos aqui servem como base para as demais jornadas de pagamento com Pix, que são tratados em seções dedicadas ao longo do capítulo **Iniciação de Pagamentos**. 
# Etapa 1 : Solicitação de Iniciação de Pagamento
Nesta etapa, o usuário inicia a jornada de pagamento com Pix via Open Finance, escolhe a Instituição Detentora de Conta (ID) que será utilizada para realizar o pagamento e define os
parâmetros da transação, como valor e dados do recebedor, quando aplicável, conforme as regras da forma de iniciação selecionada. Em seguida, ele revisa os dados configurados e visualiza as demais informações que compõem a autorização a ser enviada à ID.  A Instituição Iniciadora de Transação de Pagamento (ITP) deve garantir uma experiência clara, segura e informativa, indicando, em algum ponto da jornada, que o serviço é baseado em Open Finance, explicando os benefícios da jornada e permitindo a seleção eficiente da ID. Também é sua responsabilidade validar os dados inseridos, ocultar informações sensíveis, preparar a solicitação de iniciação de pagamento para envio à ID e, quando aplicável, exibir [mensagens de erro claras](https://openfinancebrasil.atlassian.net/wiki/pages/createpage.action?spaceKey=gdedu&title=v.19.00.00%20Casos%20de%20Erro%20%28Pagamentos%20e%20JSR%29&linkCreation=true&fromPageId=1422754052) ao usuário.Etapa 1: Solicitação de Iniciação de Pagamento
### Métodos de iniciação com Pix
Métodos de iniciação com Pix#F4F5F7
## Requisitos - ITP
**Cenário: Solicitação de pagamento**
1. Oferta do Pix via Open Finance: Disponibilizar a opção de pagamento com Pix por meio do Open Finance, mesmo que o termo “Open Finance” não esteja presente no nome da opção apresentada ao usuário.    Ex.: Pagar com outro banco.
2. Comparação entre arranjos: Não comparar arranjos de pagamento de forma a desqualificar um deles.
3. Identificação do Open Finance: Mencionar o Open Finance em algum ponto visível da interface. Ex.: Tooltip, selo, frase como "com a segurança do Open Finance.
4. Próximos passos: Dar visibilidade sobre as próximas etapas até a conclusão da jornada. Solicitação de pagamento - Início da jornada
**Cenário: Busca e seleção da ID**
1. Busca e seleção da ID: Disponibilizar ferramenta de busca e seleção da ID, com funcionamento baseado em marcas e conforme os critérios abaixo: Permitir que o usuário busque tanto pela marca da instituição quanto por um participante associado, exibindo corretamente a marca correspondente nos resultados. Exigir que a seleção final da ID seja feita pela marca da instituição, e não pelo nome do participante associado. Exibir apenas marcas adequadas ao tipo de público identificado (PF ou PJ). Garantir que cada marca seja exibida uma única vez, mesmo que existam múltiplos registros para ela no Diretório de Participantes.
Busca e seleção da ID**Cenário: Autorização de Pix**A ITP deve possibilitar que o usuário insira e/ou revise as informações da transação conforme a forma de iniciação de pagamento selecionada e as regras do arranjo Pix.
1. Valor do pagamento: Exibir o valor do pagamento, conforme a forma de iniciação selecionada. Disponibilizar um campo para que o usuário preencha o valor, em caso de valor variável. Ex.: Pagamentos, depósitos ou transferências. Exibir o valor automaticamente caso seja pré-determinado. Ex.: Boletos.
Valor do pagamento
1. Forma de pagamento: Exibir, com clareza, a forma de pagamento escolhida.  Ex.: Pix.
2. Tarifa do serviço: Exibir o valor da tarifa cobrada pela ITP, quando aplicável.
3. Data do pagamento: Exibir a data da cobrança.
4. Descrição do pagamento: Exibir a descrição do pagamento, conforme a forma de iniciação selecionada (via campo `remittanceInformation` ). Disponibilizar um campo para que o usuário preencha a descrição opcionalmente, quando aplicável. Ex.: Ração do Rex. Exibir a descrição automaticamente, quando aplicável. Ex.: QR Code com valor fixo e descrição pré-definida.
Descrição do pagamento
1. Identificação do recebedor: Exibir os dados do recebedor, conforme a forma de iniciação selecionada. Permitir que o usuário insira os dados do recebedor, quando aplicável. Ex.: Instituição, agência, conta e CPF/CNPJ. Exibir os dados do recebedor automaticamente, quando aplicável. Em caso de pessoa física, exibir o CPF do recebedor de forma mascarada.   Ex.: ***.456.789-**
2. Identificação da ID: Exibir o nome da Detentora selecionada pelo usuário, caso essa etapa tenha sido apresentada antes da revisão da transação.
3. Identificação da ITP: Exibir o nome da instituição responsável pela iniciação da transação de pagamento.
**Nota:**Caso o usuário já esteja no ambiente da própria ITP, a exibição do
nome da ITP não é obrigatória, pois a identificação já é evidente no contexto.Dados gerais
1. Necessidade de saldo e limites disponíveis: Informar ao usuário que a transação será concluída apenas se houver saldo e limite transacional disponíveis.
2. Termos e condições: Quando aplicável, apresentar os termos de uso de forma clara. Não utilizar opt-in para aceite. Informar que, ao continuar, o usuário está concordando com os termos e condições.
3. Informações complementares obrigatórias: Exibir qualquer informação adicional exigida pelo arranjo Pix, conforme a regulação vigente.
Necessidade de saldo e limites disponíveis #F4F5F7
## Recomendações - ITP
**Cenário: Seleção da forma de pagamento**
1. Vocabulário amigável: Ao permitir que o usuário selecione uma conta salva (Ex.: segunda compra), usar linguagem pessoal e natural (meu/minha). 
- “Pagar com minha conta”.
- “Transferir com meu banco”.
- “Usar minha Instituição”.
- “Pagar com outro banco”.
**Nota:**Esses exemplos foram baseados no [teste de usabilidade feito pelo GT UX](https://ob-public-files.s3.amazonaws.com/20221024_Teste+de+etiquetas.pdf) em outubro de 2022 e não contemplam todas as formas de abordar o usuário. Sugestões de termosVocabulário amigável
1. Apresentação do fluxo da jornada: Informar, logo no início, o fluxo completo da jornada, incluindo o direcionamento para a Detentora e o retorno à Iniciadora.
2. Proposta de valor: Explicar claramente os benefícios da jornada com Open Finance, destacando pontos como segurança, rapidez e praticidade.
3. Educação do usuário: Disponibilizar conteúdos educativos ( onboarding ) que expliquem como o serviço funciona, com exemplos e instruções.
4. Gratuidade: Quando aplicável, informar sobre a gratuidade da operação de forma clara e sem fricções que atrapalhem a jornada.
5. Recapitulação pós primeira transação: Após a primeira experiência, utilizar recursos como “Saiba mais” para reforçar os benefícios da jornada e dar visibilidade às etapas futuras sem criar fricções na experiência padrão.
*Onboarding*- Recomendações **Cenário: Autorização de Pix**
1. Dados adicionais para autenticação: Quando necessário, solicitar dados complementares da Detentora selecionada, como agência e número da conta, para facilitar a autenticação do usuário na Detentora.
2. Termos e condições: Apresentar os termos e condições, quando aplicável, de forma acessível, por exemplo via link, garantindo que o conteúdo seja compreensível e não redundante com o que já está presente na jornada.
3. Edição de dados: Permitir que o usuário edite facilmente os dados revisáveis antes da confirmação, evitando o reinício da jornada.
4. Posicionamento dos parâmetros: Posicionar os campos editáveis na parte superior da tela, quando aplicáveis, para garantir visibilidade e facilitar a edição.
5. Preenchimento automático da data: Definir a data do pagamento automaticamente com a data da solicitação.
6. Prevenção de interrupções: Alertar sobre a possibilidade de falha na jornada em dispositivos com o recurso de ocultação de aplicativos ativado, orientando o usuário a desativar esse recurso se necessário.
Autorização de pagamento - Recomendações gerais
# Etapa 2: Direcionamento
Nesta etapa, o usuário é direcionado da Iniciadora (ITP) para a Detentora de Conta (ID) para se autenticar, revisar e confirmar a autorização de pagamento. A ITP deve orientar o usuário sobre o direcionamento e assegurar que a navegação ocorra de forma transparente, conforme o dispositivo utilizado.Além disso, quando aplicável, a ITP deve exibir [mensagens de erro claras](https://openfinancebrasil.atlassian.net/wiki/pages/createpage.action?spaceKey=gdedu&title=v.19.00.00%20Casos%20de%20Erro%20%28Pagamentos%20e%20JSR%29&linkCreation=true&fromPageId=1422754052) ao usuário.#F4F5F7
## Requisitos - ITP
**Cenário: Direcionamento Hybrid Flow**
1. Ordem de preferência do direcionamento: Levar o usuário para um canal digital seguro, seguindo a ordem de preferência descrita a seguir: Direcionar para o aplicativo da ID (Hybrid Flow). Direcionar para a loja de aplicativos, caso o aplicativo não esteja instalado. Direcionar para o ambiente browser (Hybrid Flow) ou para a loja de aplicativos. Direcionar para o aplicativo com Hand-off (Hybrid Flow com Hand-off). Direcionar para o aplicativo ou ambiente desktop da ID (Hybrid Flow).
Ordem de preferência do direcionamento **Cenário: Tela de transição**
1. Informações sobre o direcionamento: Durante o direcionamento, exibir uma tela informativa, sem exigir ação adicional do usuário para confirmar o direcionamento, contendo as seguintes informações mínimas: Indicação de que o direcionamento está em andamento. Indicação de que o direcionamento é seguro. Ex.: Estamos te direcionando com segurança para finalizar a transação. Informação que o usuário possui até 5 minutos para confirmar a iniciação de pagamento na ID.  Ex.: Você tem até 5 minutos para finalizar a transação.
2. Direcionamento entre dispositivos móveis: Em dispositivos móveis, direcionar o usuário diretamente para o aplicativo da ID, sem passar por navegadores intermediários.
 Tela de transição ID > ITP#F4F5F7
## Recomendações - ITP
**Cenário: Tela de transição**
1. Interrupção da jornada: Permitir que, caso a jornada seja interrompida nesta etapa, o usuário consiga retomá-la facilmente através dos canais digitais da ITP.
2. Tela de transição: Apresentar uma mensagem amigável e contextualizada na tela de transição, destacando as vantagens do direcionamento. Utilizar elementos visuais e textuais que reforcem o direcionamento, como loaders , animações, barras de progresso ou indicadores visuais.
Tela de transição ID > ITP - Recomendações
# Etapa 3: Confirmação
Nesta etapa, o usuário se autentica na Instituição Detentora de Conta (ID) e pode, em caso de múltiplas contas de débito, escolher a que deseja usar para fazer o pagamento. Ele também revisa as
informações da autorização enviadas pela Instituição Iniciadora de Transação de Pagamento (ITP) e confirma a transação.  A ID deve garantir um ambiente seguro para autenticação, exibir o resumo da autorização, permitir a edição da conta de débito, em caso de múltiplas contas, e viabilizar a confirmação com o mínimo de fricção.   
Também é sua responsabilidade, em caso de falha, [exibir mensagens de erro claras](https://openfinancebrasil.atlassian.net/wiki/pages/createpage.action?spaceKey=gdedu&title=v.19.00.00%20Casos%20de%20Erro%20%28Pagamentos%20e%20JSR%29&linkCreation=true&fromPageId=1422754052) ao usuário, comunicar o resultado da autorização à ITP, enviar notificações ao usuário e,
quando aplicável, aos demais aprovadores — em casos de múltiplas alçadas ou falha na conclusão da autorização.Etapa 3: Confirmação#F4F5F7
## Requisitos - ID
**Cenário: Autenticação**
1. Solicitação de autenticação: Solicitar a autenticação do usuário conforme os padrões já definidos pela própria ID para operações fora do Open Finance, em conformidade com a regulação vigente.
2. Primeiro acesso ou esquecimento de senha: Possibilitar que o usuário siga o fluxo padrão da instituição para recuperação ou criação de acesso.
3. Manutenção do fluxo padrão: Não exigir etapas adicionais ou utilizar métodos mais rigorosos de autenticação não contemplados em seu canal digital afim de desincentivar a transação, conforme a regulação vigente.
Autenticação na ID**Cenário: Seleção da conta de débito****Em caso de múltiplas contas na Detentora**
1. Exibição da conta de débito: Se a conta de débito tiver sido especificada pelo usuário pagador na ITP e estiver válida e disponível após o login, exibi-la já selecionada por padrão.
2. Alteração da conta de débito: Permitir que o usuário altere a conta de débito no momento da confirmação. Exibir todas as contas aptas para seleção e desabilitar visualmente aquelas que não estiverem disponíveis, com indicação clara do motivo. Ex.: Tag . Manter a opção de confirmação desabilitada até que uma conta válida esteja selecionada. Manter o texto da opção de confirmação consistente, mesmo quando desabilitado.
Fluxograma de exibição da conta de débito selecionada**Atenção:**Em caso de resposta negativa para alguma das perguntas do fluxograma apresentado, a Detentora não conseguirá utilizar o dado da conta de débito para facilitar a jornada.**Cenário: Revisão e confirmação da transação**Após o usuário se autenticar, a ID deve exibir todos os dados da transação informados pela
ITP.
1. Valor do pagamento: Exibir o valor do pagamento.
2. Conta selecionada:  Exibir identificação da conta de débito selecionada (Número da agência e conta).
3. Descrição do pagamento: Exibir descrição do pagamento, quando informado pela ITP (via campo `additionalInformation` ).
4. Identificação do recebedor:   Exibir os dados do recebedor conforme informado pela ITP. Em caso de pessoa física, exibir o CPF do recebedor de forma mascarada.    Ex.: ***.456.789.**
5. Data do pagamento: Exibir a data da cobrança.
6. Forma de pagamento: Exibir, com clareza, a forma de pagamento.
7. Tarifa do serviço: Exibir o valor da tarifa cobrada pela ID, quando aplicável.
Revisão e confirmação da transação
1. Identificação da ITP: Exibir o nome da instituição responsável pela iniciação da transação de pagamento.
2. Ofertas de crédito: Não apresentar ofertas de crédito durante a jornada, conforme regulação vigente. A exceção aplica-se apenas a limites de crédito previamente contratados e disponíveis. Ex.: cheque especial.
3. Próximos passos: Informar ao usuário que, após a confirmação, ele será redirecionado para a ITP.
4. Confirmação da transação: Possibilitar que, após se autenticar e revisar os dados da transação, o usuário conclua a operação com uma única confirmação. Caso a instituição deseje utilizar um método adicional de confirmação da transação, seguir o mesmo padrão utilizado fora do Open Finance.
5. Omissão de termos e condições: Omitir termos e condições de uso durante a jornada de pagamento.
6. Informações complementares obrigatórias: Exibir qualquer informação adicional exigida pelo arranjo Pix, conforme a regulação vigente.
Revisão e confirmação da transação**Cenário: Cancelamento da transação**
1. Cancelamento da transação: Possibilitar que o usuário interrompa a jornada antes da confirmação. Garantir que a opção de interrupção da jornada não seja visualmente mais proeminente do que a opção de prosseguir. Redirecionar o usuário para a ITP caso ele cancele a operação. Redirecionar o usuário para a ITP caso ele retorne manualmente à etapa anterior da jornada (por meio de botão do ambiente digital, botão do dispositivo, link clicável etc.) e não seja possível exibir a tela imediatamente anterior.
Cancelamento da transação#F4F5F7
## Recomendações - ITP
**Cenário: Seleção da conta de débito**
1. Aproveitamento de dados para autenticação: Caso a ITP capture os dados de conta do usuário, utilizá-los para facilitar a autenticação na ID, contanto que não haja prejuízo dos protocolos de segurança para autenticação seguidos pelas instituições.
Aproveitamento de dados para autenticação**Cenário: Confirmação**
1. Exibição do saldo: Exibir o saldo disponível em conta para que o usuário possa avaliar a viabilidade do pagamento.
Exibição do saldo
1. Tentativa de cancelamento: Em caso de tentativa de cancelamento da transação por parte do usuário, exibir uma mensagem de confirmação.   Ex.: Tem certeza que deseja cancelar a transação?
2. Redirecionamento para ITP: Informar ao usuário que, caso a transação não possa ser concluída, ele será redirecionado ao ambiente da ITP.
Tentativa de cancelamento - ID
# Etapa 4: Redirecionamento
Nesta etapa, o usuário é redirecionado da Instituição Detentora de Conta (ID) para o ambiente da Iniciadora de Transação de Pagamento (ITP), onde poderá visualizar o status da solicitação e
um resumo da transação.  A ID deve garantir um redirecionamento seguro, automático e sem fricções, mantendo o usuário no mesmo ambiente (app ou browser) em que iniciou a jornada.  Essa etapa também pode envolver [orientações em caso de falhas](https://openfinancebrasil.atlassian.net/wiki/pages/createpage.action?spaceKey=gdedu&title=v.19.00.00%20Casos%20de%20Erro%20%28Pagamentos%20e%20JSR%29&linkCreation=true&fromPageId=1422754052) ou pendências, como autorizações em múltiplas alçadas ou indisponibilidade momentânea dos sistemas.#F4F5F7
## Requisitos - ID
**Cenário: Tela de transição**
1. Informações sobre o redirecionamento: Garantir que essa etapa seja somente informativa sem exigir qualquer ação adicional do usuário para confirmar o redirecionamento, contendo as seguintes informações mínimas: Indicação de que o redirecionamento está em andamento. Indicação de que o redirecionamento é seguro. Informação de que a operação está sendo processada e que é necessário aguardar a abertura automática do aplicativo da ITP.
2. Redirecionamento entre dispositivos móveis: Em dispositivos móveis, redirecionar o usuário diretamente para o aplicativo da ITP, sem passar por navegadores intermediários.
3. Manutenção do ambiente original: Redirecionar o usuário ao mesmo ambiente da ITP utilizado no início da jornada (aplicativo ou browser).
Tela de transição ID > ITP
# Etapa 5: Efetivação
Nesta etapa final da jornada, o usuário é recebido no ambiente da Instituição Iniciadora de Transação de Pagamento (ITP) onde visualiza o resultado da transação.   A ITP deve apresentar com clareza o status e resumo da solicitação, com mensagens claras de sucesso ou falha, e disponibilizar um comprovante com os principais dados da
transação.  Essa etapa também pode envolver [orientações em caso de erro](https://openfinancebrasil.atlassian.net/wiki/pages/createpage.action?spaceKey=gdedu&title=v.19.00.00%20Casos%20de%20Erro%20%28Pagamentos%20e%20JSR%29&linkCreation=true&fromPageId=1422754052) ou pendências, como autorizações em múltiplas alçadas, transações temporizadas ou indisponibilidade momentânea dos sistemas.Etapa 5: EfetivaçãoDigite ou cole algo aqui para o transformar em um trecho.#F4F5F7
## Requisitos - ITP
**Cenário: Efetivação do pagamento**
1. Sucesso: Em caso de sucesso, exibir um resumo da transação com, no mínimo, as seguintes informações. Identificador da transação: Número de identificação da transação ( `endtoEndId ` do Pix) Valor do pagamento: Exibir o valor do pagamento, conforme a forma de iniciação selecionada. Identificação do pagador: Exibir nome completo e CPF (mascarado ou não)/CNPJ. Conta selecionada:   Exibir identificação da conta de débito selecionada (Número da agência e conta). Identificação do recebedor: Exibir os dados do recebedor, conforme a forma de iniciação selecionada. Em caso de pessoa física, exibir o CPF do recebedor de forma mascarada.   Ex.: ***.456.789-** Descrição do pagamento: Exibir a descrição do pagamento, quando aplicável. Data do pagamento: Data e hora/minuto/segundo da efetivação do pagamento (horário de Brasília). Forma de pagamento: Exibir, com clareza, a forma de pagamento. Ex.: Pix. Tarifa do serviço: Exibir o valor da tarifa cobrada pela ITP, quando aplicável. Informações complementares obrigatórias: Exibir qualquer informação adicional exigida pelo arranjo Pix, conforme a regulação vigente. Identificação da ITP: Exibir o nome da instituição responsável pela iniciação da transação de pagamento.
**Nota:**Caso o usuário já esteja no ambiente da própria ITP, a exibição do nome da ITP não é obrigatória, pois a identificação já é evidente no contexto.Conclusão da solicitação - ITP**Cenário: Cancelamento da solicitação**
1. Cancelamento : Em caso de cancelamento da transação, informar o usuário sobre o cancelamento e exibir os dados da transação cancelada.
Cancelamento da solicitação#F4F5F7
## Recomendações - ITP
**Cenário: Efetivação pagamento**
1. Exibição dos dados da solicitação: Exibir o resumo da solicitação em tela ou através de, por exemplo, um botão. Ex.: “Ver comprovante”, “Detalhes”, “Saiba mais” etc.
Efetivação do pagamento