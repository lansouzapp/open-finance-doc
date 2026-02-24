---
id: 1477285800
title: v.19.00.01 Requisitos e Recomendações - Vinculação de Conta (JSR)
version: 4
modified: 2026-01-30T15:39:49.067Z
url: /spaces/OF/pages/1477285800/v.19.00.01+Requisitos+e+Recomenda+es+-+Vincula+o+de+Conta+JSR
---

Requisitos e recomendações para a jornada de Vinculação de Conta para Pagamentos Sem Redirecionamento (JSR). Este subcapítulo está organizado em cinco etapas principais — **Solicitação de Vinculação de Conta, Direcionamento ITP > ID, Confirmação, Redirecionamento ID > ITP e Efetivação da Vinculação de Conta.**
# Etapa 1: Solicitação de Vinculação de Conta
Nesta etapa, o usuário inicia a jornada de vinculação de conta na Instituição Iniciadora de Transação de Pagamento (ITP), onde ele escolhe a Instituição Detentora de Conta (ID) que será utilizada para realizar os pagamentos sem redirecionamento.  A ITP deve garantir uma experiência clara, segura e informativa, indicando, em algum ponto da jornada, que o serviço é baseado em Open Finance, explicando os benefícios da jornada e permitindo a seleção eficiente da ID. Também é sua responsabilidade validar os dados inseridos, ocultar informações sensíveis, preparar a solicitação de vinculação de conta para envio à ID e, quando aplicável, exibir mensagens de erro claras ao usuário. #F4F5F7
## Requisitos - ITP
**Cenário: Solicitação da vinculação de conta**
1. Identificação do Open Finance: Mencionar o Open Finance em algum ponto visível da interface. Ex.: tooltip, selo, frase como "com a segurança do Open Finance”.
2. Próximos passos: Dar visibilidade sobre as próximas etapas até a conclusão da jornada.
3. Finalidade da jornada: Informar o usuário que o vínculo de conta está sendo criado para realização de transações futuras.
4. Termos e condições : Quando aplicável, apresentar os termos de uso de forma clara. Não utilizar opt-in para aceite. Informar que, ao continuar, o usuário está concordando com os termos e condições.
5. Jornada Otimizada (Saldo e limite): Permitir, quando aplicável, que o usuário compartilhe, de forma opcional, o saldo e limite da conta selecionada. Apresentar a opção de compartilhamento de saldo e limite desabilitada por padrão. Solicitação de Vinculação de Conta Quando aplicável, informar que o saldo e o limite estão sendo compartilhados. Exibir o escopo de cada dado compartilhado. Solicitação de Vinculação de Conta - Jornada Otimizada
**Cenário: Busca e seleção da ID**
1. Busca e seleção da ID: Disponibilizar ferramenta de busca e seleção da ID, com funcionamento baseado em marcas e conforme os critérios abaixo: Exibir todas as Detentoras que ofereçam a JSR. Permitir que o usuário busque tanto pela marca da ID quanto por um participante associado, exibindo corretamente a marca correspondente nos resultados. Exigir que a seleção final da ID seja feita pela marca da instituição, e não pelo nome do participante associado. Exibir apenas marcas adequadas ao tipo de público identificado (PF ou PJ). Garantir que cada marca seja exibida uma única vez, mesmo que existam múltiplos registros para ela no Diretório de Participantes.
Busca e seleção da ID#F4F5F7
## Recomendações - ITP
**Cenário: Geral**
1. Onboarding do Open Finance: No primeiro uso, disponibilizar o link de acesso para a Área do Cidadão para que o usuário possa acessar informações relativas ao Open Finance.
2. Onboarding da vinculação de conta: Disponibilizar, ao menos na primeira Jornada de Vinculação de Conta via Open Finance, informações claras sobre as principais regras do produto, incluindo, no mínimo: O que é a vinculação de conta e suas vantagens. Possibilidade de definição de limite diário/por transação para o vínculo. Possibilidade de definição de um apelido para o dispositivo autorizado. Possibilidade de definição de prazo de validade do vínculo. Possibilidade de cancelamento do vínculo a qualquer momento.
3. Proposta de valor : Explicar claramente os benefícios da jornada com Open Finance, destacando pontos como segurança, rapidez e praticidade.
Geral - Recomendações
1. Dados adicionais para autenticação : Quando necessário, solicitar dados complementares da ID selecionada, como agência e número da conta, para facilitar a autenticação do usuário na ID.
2. Prevenção à fraude: Solicitar dados complementares para compor análises de prevenção à fraude, validade de identidade ou outras próprias de cada instituição.
3. Termos e condições : Apresentar os termos e condições, quando aplicável, de forma acessível, por exemplo via link, garantindo que o conteúdo seja compreensível e não redundante com o que já está presente na jornada.
4. Prevenção de interrupções : Alertar sobre a possibilidade de falha na jornada em dispositivos com o recurso de ocultação de aplicativos ativado, orientando o usuário a desativar esse recurso se necessário.
Prevenção de interrupções da jornada - Recomendação
# Etapa 2: Direcionamento
Nesta etapa, o usuário é direcionado da Instituição Iniciadora de Transação de Pagamento (ITP) para a Instituição Detentora de Conta (ID) para se autenticar, revisar e confirmar o vínculo de conta.  A ITP deve orientar o usuário sobre o direcionamento e assegurar que a navegação ocorra de forma transparente, conforme o dispositivo utilizado.Além disso, quando aplicável, a ITP deve exibir mensagens de erro claras ao usuário. **Nota:**Consulte o subcapítulo **Jornada de Hybrid Flow com hand-off (Pagamentos)** ****para visualizar os requisitos e recomendações para a implementação dessa jornada.#F4F5F7
## Requisitos - ITP
**Cenário: Tela de transição****Nota:**Consulte a etapa **Direcionamento** do subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento**para visualizar os requisitos e recomendações complementares a esse cenário. 
1. Tempo de conclusão:  Informar que o usuário possui até 15 minutos para confirmar o vínculo de conta na ID. Ex.: Você tem até 15 minutos para finalizar a transação.
Direcionamento ITP > ID
# Etapa 3: Confirmação
Nesta etapa, o usuário se autentica na Instituição Detentora de Conta (ID) e pode, em caso de múltiplas contas de débito, escolher a que deseja usar para fazer os pagamentos sem redirecionamento. Ele também revisa as informações do vínculo de conta enviadas pela Instituição Iniciadora de Pagamento (ITP) e confirma a vinculação.   A ID deve garantir um ambiente seguro para autenticação, exibir o resumo do vínculo, permitir a edição da conta de débito, em caso de múltiplas contas, e viabilizar a confirmação com o mínimo de fricção.    Também é sua responsabilidade, em caso de falha, exibir mensagens de erro claras ao usuário, comunicar o resultado da vinculação à ITP, enviar notificações ao usuário, inclusive em casos de falha na conclusão da vinculação.  
 #F4F5F7
## Requisitos - ID
**Cenário: Autenticação**
1. Solicitação de autenticação: Solicitar a autenticação do usuário conforme os padrões já definidos pela própria ID para operações fora do Open Finance, em conformidade com a regulação vigente.
2. Primeiro acesso ou esquecimento de senha : Possibilitar que o usuário siga o fluxo padrão da instituição para recuperação ou criação de acesso.
3. Manutenção do fluxo padrão: Não exigir etapas adicionais ou utilizar métodos mais rigorosos de autenticação não contemplados em seu canal digital afim de desincentivar a transação, conforme a regulação vigente.
4. Validação de CPF divergente: Impedir que um usuário com CPF diferente daquele declarado pela ITP acesse a tela de autorização do vínculo de conta, informando com clareza sobre o motivo do impedimento.
Autenticação **Cenário: Seleção da conta de débito**
1. Exibição da conta de débito: Se a conta de débito tiver sido especificada pelo usuário pagador na ITP e estiver válida e disponível após o login, exibi-la já selecionada por padrão.
Exibição da conta de débito selecionada **Para casos de múltiplas de contas na Detentora** 
1. Alteração da conta de débito: Permitir que o usuário altere a conta de débito no momento da confirmação. Exibir todas as contas aptas para seleção e desabilitar visualmente aquelas que não estiverem disponíveis, com indicação clara do motivo. Ex.: Tag. Manter a opção de confirmação desabilitada até que uma conta válida esteja selecionada. Manter o texto da opção de confirmação consistente, mesmo quando desabilitado.
Alteração da conta de débitoFluxograma para exibição da conta selecionada **Atenção:**Em caso de resposta negativa para alguma das perguntas do fluxograma apresentado, a ID não conseguirá utilizar o dado da conta de débito para facilitar a jornada.**Cenário: Revisão e confirmação da Vinculação de Conta**Após o usuário se autenticar, a ID deve exibir todas as informações do vínculo de conta informadas pela ITP.
1. Identificação do usuário:   Exibir os dados do usuário conforme informado pela ITP. Em caso de pessoa física, exibir o CPF do usuário de forma mascarada. ` ` Ex.: ***.456.789.** Em caso de pessoa jurídica, exibir a razão social e CNPJ
2. Identificação da conta:   Exibir identificação da conta de débito selecionada (Número da agência e conta).
3. Validade do vínculo: Exibir a data de expiração do vínculo com prazo padrão de 5 anos e permitir que o usuário edite o prazo, inclusive com a opção de prazo Indeterminado .
4. Identificação da ITP : Exibir o nome da instituição responsável pela iniciação da transação de pagamento.
Revisão e confirmação da Vinculação de Conta
1. Limites transacionais: Permitir que o usuário defina, se desejar, os valores máximos diário e por transação para pagamentos com o vínculo de conta. Diário: Manter o limite como indeterminado (não preenchido) por padrão e permitir que o usuário insira um valor. Se o usuário não definir um valor máximo diário, informar que os limites do Pix serão considerados. Por transação: Preencher, por padrão, com o valor de R$500,00 e permitir que o usuário edite respeitando o contrato bilateral entre ITP e ID. Impedir que o usuário defina um valor máximo por transação superior ao valor máximo diário.
2. Conta conjunta: Para conta conjunta de pessoas físicas, permitir que cada titular autorize seu próprio dispositivo.
Definição de limites transacionais
1. Jornada Otimizada (saldo e limite): Quando aplicável, informar que o saldo e limite estão sendo compartilhados. Exibir o escopo de cada dado compartilhado.
2. Próximos passos: Informar ao usuário que, após a confirmação, ele será redirecionado para a ITP.
3. Confirmação da transação: Utilizar os mesmos métodos de confirmação para vinculação de conta já adotados para confirmação de pagamentos fora do Open Finance, sem a exigência de métodos adicionais.
4. Termos e condições: Omitir termos de uso durante a jornada de vinculação de conta.
5. Omissão de informações desnecessárias: Omitir qualquer aspecto que desvie o foco do usuário em concluir o vínculo de conta, como, por exemplo link, botão, imagem, texto, entre outros.
Resumo e confirmação da Vinculação - Geral**Cenário: Cancelamento da Vinculação de Conta**
1. Cancelamento da vinculação: Possibilitar que o usuário interrompa a jornada antes da confirmação. Garantir que a opção de interrupção da jornada não seja visualmente mais proeminente do que a opção de prosseguir. Redirecionar o usuário para a ITP caso ele cancele a operação. Redirecionar o usuário para a ITP caso ele retorne manualmente à etapa anterior da jornada (por meio de botão do ambiente digital, botão do dispositivo, link clicável etc.) e não seja possível exibir a tela imediatamente anterior.
Cancelamento da Vinculação de Conta#F4F5F7
## Recomendações - ID
**Cenário: Seleção da conta de débito**
1. Aproveitamento de dados para autenticação: Caso a ITP capture os dados de conta do usuário, utilizá-los para facilitar a autenticação na ID, contanto que não haja prejuízo dos protocolos de segurança para autenticação seguidos pelas instituições.
Aproveitamento de dados para autenticação**Cenário: Revisão e confirmação da Vinculação de Conta**
1. Dispositivo autorizado: Permitir que o usuário defina um nome para o dispositivo autorizado.
Revisão e confirmação da Vinculação de Conta - Recomendação**Cenário: Cancelamento da Vinculação de Conta**
1. Tentativa de cancelamento: Em caso de tentativa de cancelamento da vinculação de conta por parte do usuário, exibir uma mensagem de confirmação.   Ex.: Tem certeza que deseja cancelar a solicitação?
Cancelamento da Vinculação de Conta - Recomendação
# Etapa 4: Redirecionamento
**Nota:**A etapa **Redirecionamento******está detalhada no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento.****Nota:**Consulte o subcapítulo **Jornada de Hybrid Flow com hand-off (Pagamentos)** para visualizar os requisitos e recomendações para a implementação dessa jornada.Redirecionamento ID > ITP
# Etapa 5: Efetivação da Vinculação de Conta
Nesta etapa final da jornada, o usuário é recebido no ambiente da Instituição Iniciadora de Transação de Pagamento (ITP) onde cria as chaves de autenticação que serão utilizadas para se autenticar na ITP cada vez que o vínculo de conta for utilizado em uma jornada de pagamento. Em seguida, a ITP exibe o resultado da solicitação de vinculação de conta.   A ITP deve apresentar com clareza o status e os dados da solicitação, com mensagens de sucesso ou falha, e disponibilizar um comprovante com os principais dados da solicitação. Essa etapa também pode envolver orientações em caso de falhas ou pendências. #F4F5F7
## Requisitos - ITP
**Cenário: Criação de chaves no dispositivo**
1. Criação da chave de autenticação: Solicitar que o usuário valide a geração da chave de autenticação através de suas credenciais. Ex.: Biometria, senha ou PIN.
Criação de chaves no dispositivo**Cenário: Efetivação da Vinculação de Conta**
1. Resultado da solicitação: Exibir mensagem informando sobre o resultado (sucesso ou falha) da solicitação de vinculação de conta.
2. Detalhes do vínculo: Informar sobre a possibilidade de acesso aos detalhes do vínculo através da área de gestão.
3. Revogação do vínculo: Informar sobre a possibilidade de cancelamento do vínculo através da área de gestão. Quando aplicável, informar que o cancelamento do vínculo também cancela o compartilhamento de saldo e limite.
4. Revogação da Jornada Otimizada (saldo e limite) : Quando aplicável, informar que o compartilhamento de saldo e limite pode ser cancelado a qualquer momento através da área de gestão.  Informar que o cancelamento do compartilhamento de saldo e limite não cancela o vínculo de conta.
Conclusão da Vinculação de Conta#F4F5F7
## Recomendações - ITP
**Cenário: Efetivação da Vinculação de Conta**
1. Detalhes do vínculo: Exibir os detalhes do vínculo através de, por exemplo, um botão ou link que direcione para área de gestão. Exs.: “Ver comprovante”, “Detalhes”, “Saiba mais” etc.
Conclusão da Vinculação de Conta - Detalhes