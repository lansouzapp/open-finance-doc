---
id: 1436289555
title: v.19.00.00 Requisitos e Recomendações - Jornada Básica de Compartilhamento de Dados
version: 1
modified: 2026-01-12T19:25:38.436Z
url: /spaces/OF/pages/1436289555/v.19.00.00+Requisitos+e+Recomenda+es+-+Jornada+B+sica+de+Compartilhamento+de+Dados
---

# Etapa 1: Consentimento
DC - etapa 1#F4F5F7
## Requisitos - IR
**Cenário: Início do compartilhamento**
1. Coleta de informações mínimas sobre o usuário: Para casos de usuário com cadastro prévio na Instituição Receptora de Dados, é necessário verificar se o CPF é válido.  Em casos de segmento PJ, também é necessário validar o CNPJ  além do CPF. Para casos de usuário sem cadastro prévio na Instituição  Receptora de Dados, é necessário realizar a coleta de, no  mínimo, o CPF em casos de segmento PF e do CPF e CNPJ  em casos de segmento PJ, assim como de outras informações  de identificação que a Instituição Receptora de Dados entenda como necessárias para prosseguir com a jornada ou que  sejam solicitadas pela regulação, como na Circular n° 3978 , de  23/01/2020.
2. A Instituição Receptora de Dados deve apresentar a finalidade do consentimento de forma clara ao usuário, seja na tela em que a jornada é iniciada ou durante a etapa de solicitação do consentimento.
3. Deve ser disponibilizada ao usuário uma ferramenta de busca e seleção da Instituição Transmissora de Dados da qual ele deseja trazer os dados: A ferramenta de busca deve exibir resultados corretos para quando o usuário pesquisar pelo nome da marca da Instituição Transmissora de Dados, assim como tem de exibir a marca correspondente caso o usuário pesquise por algum participante associado a ela. O usuário deverá sempre selecionar a marca e não o participante associado. Caso a Instituição Receptora de Dados identifique o usuário como sendo do segmento de Pessoa Física, apenas as marcas que atendem esse público devem estar disponíveis para seleção. Marcas que suportem exclusivamente o segmento de Pessoa Jurídica não devem ser exibidas. A mesma lógica se aplica para os casos de usuários identificados como segmento de Pessoa Jurídica. Cada marca Transmissora de Dados deve ser exibida apenas uma única vez na lista de resultados, mesmo em casos nos quais a marca esteja cadastrada duas ou mais vezes no Diretório de Participantes.
Compartilhamento de dados - Início do compartilhamento **Cenário: Seleção de dados**
1. No ambiente da Instituição Receptora de Dados, devem estar disponíveis a visualização e a configuração (quando aplicável) dos dados objeto do compartilhamento, conforme as condições abaixo: As categorias de dados devem ser exibidas diretamente na tela principal da jornada, porém os agrupamentos devem estar ocultos para acesso apenas dos usuários interessados. (Ex.: menu agrupado ou botão de mais detalhes). A Instituição Receptora de Dados tem autonomia para determinar quais categorias de dados ou agrupamentos são obrigatórios para o caso de uso em andamento, desde que tenham relação direta com a finalidade de uso. Ela deve discriminar ao usuário quais dados são obrigatórios e quais são opcionais (quando aplicável). Para casos em que sejam oferecidos dados obrigatórios e opcionais, deve ser especificado o motivo da obrigatoriedade. Deve ser possível remover ou incluir as categorias e agrupamentos de dados opcionais no consentimento. Para casos em que dados transacionais de operações de crédito, investimento e/ou câmbio façam parte do escopo de dados, deve estar disponível ao usuário a informação de que se durante a vigência do compartilhamento vier a contratar ou realizar novas operações dessas categorias, os dados destas novas contratações e operações serão automaticamente incluídos no consentimento em questão.
Compartilhamento de dados - Seleção dos dados**Cenário: Prazo de consentimento**
1. A Instituição Receptora de Dados deve apresentar em tela um campo que indique a duração/prazo do compartilhamento, considerando: O campo de prazo deve estar preenchido por padrão, conforme prazo que a Instituição Receptora de Dados entender mais adequado para o caso de uso. Deve ser disponibilizada possibilidade de alteração do prazo pelo usuários interessados para, no mínimo, uma outra opção além do prazo padrão já indicado. Em casos de prazo indeterminado, o prazo deverá ser apresentado como “Indeterminado” ou termo similar e não deverá ser indicada data final ao usuário.
**Nota:**Caso os dados compartilhados sejam informações pontuais ou de prazo curto (por exemplo: dados para abertura de conta, contratação de empréstimo etc.) ou como um consentimento de compartilhamento pontual, que não necessita de prazo baseado em meses, é indicado que sejam apresentados prazos proporcionais (por exemplo: horas, dias ou semanas)Compartilhamento de dados - Prazo de consentimento**Cenário: Informações da solicitação**
1. Deve estar claro ao usuário que, ao continuar estará concordando com os termos e condições da Instituição Receptora de Dados.
2. Se a Instituição Receptora de Dados optar por disponibilizar os Termos e Condições, não deve fazer uso de opt-in.
3. As Instituições Financeiras devem dar visibilidade ao usuário em relação às etapas em andamento e próximos passos, durante toda a jornada, seja por meio de elementos visuais ou textuais.
4. Durante toda a jornada, a Instituição Receptora de Dados deve utilizar os termos definidos na Tabelas de Dados para as categorias de dados, agrupamentos e suas descrições.
**Nota:**Os requisitos não exigem a apresentação de uma tela específica para checkout do usuário antes do redirecionamento para a Instituição Receptora de Dados. Fica a critério da Instituição Receptora de Dados incluir ou não uma tela de checkout para uma melhor experiência ou para auxiliar no cumprimento dos requisitos.Compartilhamento de dados - Informações da solicitação#F4F5F7
## Recomendações - IR
**Cenário: Informações da solicitação**
1. Trazer pré-selecionados os agrupamentos de dados correlacionados com a finalidade, permitindo que o usuário retire a seleção dos dados opcionais.
2. Oferecer a possibilidade de selecionar ou limpar a seleção de múltiplos agrupamentos com uma única ação.
3. Possibilitar a visualização dos dados que compõem cada agrupamento de maneira simples.
Compartilhamento de dados - Informações da solicitação
1. Caso o usuário não possua um cadastro prévio, além dos campos obrigatórios citados no requisito 1.a desta mesma etapa, informações como nome completo, razão social, e-mail, telefone etc. podem ser solicitadas de acordo com a necessidade de cada Instituição Financeira, sempre deixando claro para o usuário quais campos são obrigatórios e quais são opcionais para preenchimento.
2. Informar ao usuário o benefício em compartilhar os dados opcionais, caso existam.
3. Criar vocabulário simples para os campos, para facilitar o entendimento do usuário, como, por exemplo, resumir em “Endereço completo” a listagem de CEP, endereço, número, complemento, cidade, UF, país etc.
4. A linguagem “Termos para o Usuário” presente no Glossário de Experiência pode ser simplificada, para evitar repetitividade, e apresentada de outras formas (p.ex.: no infinitivo).
5. Durante o processo de consentimento, é recomendado que a Instituição Receptora de Dados informe aos usuários sobre a gratuidade do compartilhamento de dados, sem prejudicar a conclusão da jornada.
6. Quando o usuário estiver fazendo um novo consentimento, exatamente o mesmo escopo de dados de algum consentimento já ativo, a Instituição Receptora de Dados poderá exibir, caso queiram, um aviso/alerta em tela, pedindo para o usuário confirmar se realmente quer seguir dessa forma ou não, pois isso causa múltiplos consentimentos iguais, e dificulta a gestão. A navegação precisará conter opções para seguir ou interromper.
7. Devido a possibilidade de ocultar aplicativos em dispositivos com sistema operacional iOS 18 (ou superiores), causando a falha no redirecionamento do usuário, é recomendado que a receptora de Dados comunique ao usuário que, caso este tenha optado por ocultar algum dos aplicativos financeiros necessários para o compartilhamento de dados, não será possível completar a jornada e é necessário realizar a desocultação antes de realizar o redirecionamento.
Compartilhamento de Dados - Informações da solicitação
# Etapa 2: Direcionamento
DC - etapa 2#F4F5F7
## Requisitos - IT
**Cenário: Seleção de métodos de direcionamento**
1. A Instituição Transmissora de Dados deve levar o usuário para um canal digital seguro, seguindo a ordem de preferência descrita abaixo: A Instituição Transmissora de Dados deve redirecionar o usuário para seu aplicativo (Hybrid Flow). A Instituição Transmissora de Dados deve redirecionar o usuário para a página de download de seu aplicativo na loja de aplicativos do seu dispositivo. A Instituição Transmissora de Dados deve redirecionar o usuário ou para seu ambiente browser (Hybrid Flow), o que permitirá a continuidade da jornada, ou para a página de download de seu aplicativo na loja de aplicativos. A Instituição Transmissora de Dados deve redirecionar o usuário para o seu aplicativo (Hybrid Flow com Hand-off ). A instituição Transmissora de Dados deve redirecionar o usuário ou para seu aplicativo (Hybrid Flow com Hand-off) ou para seu ambiente em desktop (Hybrid Flow).
Compartilhamento de dados - Seleção do método de direcionamento#F4F5F7
## Requisitos - IR
**Cenário: Tela de transição**
1. Durante o processo de redirecionamento, a Instituição Receptora de Dados deve apresentar uma tela dedicada a esclarecer ao usuário que o redirecionamento está em andamento. A tela deve conter, no mínimo, as seguintes informações/elementos. Indicação de que o redirecionamento está em andamento. Indicação de que o redirecionamento é seguro.
2. Tanto a Instituição Receptora de Dados quanto a Instituição Transmissora de Dados não devem exigir qualquer ação adicional do usuário para confirmar o redirecionamento, o carácter da etapa é apenas informativo
3. Em dispositivo móvel, o redirecionamento da Instituição Receptora de Dados para Instituição Transmissora de Dados deve ocorrer diretamente para o aplicativo da Instituição Transmissora de Dados, sem a passagem de navegadores intermediários.
Compartilhamento de dados - Tela de transição#F4F5F7
## Recomendações - IR
**Cenário: Tela de transição**
1. Caso o fluxo de solicitação seja interrompido nesta etapa, deve existir fácil acesso à continuidade do processo por meio dos canais digitais da Instituição.
Compartilhamento de dados - Tela de transição
# Etapa 3: Autenticação
DC - etapa 3#F4F5F7
## Requisitos - IT
**Cenário: Login**
1. Para o usuário se autenticar, é necessário que ele tenha acesso a um canal digital da Instituição Transmissora de Dados.
2. A autenticação deve ser realizada conforme padrões dos canais digitais já definidos pelas instituições para jornada/acessos não relacionados ao Open Finance, conforme disposto na Resolução Conjunta nº 1.
**Nota:**Reforçamos que, conforme Instrução Normativa BCB n° 637 de 13/06/2025, referente à versão 8.0 do Manual de Experiência do Usuário no Open Finance, etapas adicionais ou o uso métodos mais rigorosos de autenticação não contemplados atualmente no canal digital da Instituição Transmissora de Dados serão interpretados como mecanismos que desincentivam o compartilhamento de dados.
1. Em dispositivo móvel, o redirecionamento da Instituição Receptora de Dados para Instituição Transmissora de Dados deve ocorrer diretamente para o aplicativo da Instituição Transmissora de Dados, sem a passagem de navegadores intermediários.
Compartilhamento de dados - LoginType or paste something here to turn it into an excerpt.**Cenário: Validação da titularidade**
1. No ambiente logado, é necessário fazer a validação da titularidade do usuário, com objetivo de garantir que a solicitação e a confirmação de compartilhamento estejam sendo realizadas pelo mesmo titular.
2. Caso a titularidade do usuário após a autenticação seja diferente daquela associada ao consentimento solicitado: A Transmissora deve interromper a jornada e não exibir as telas de resumo da confirmação com os dados do consentimento A interrupção da jornada deve ser acompanhada da apresentação de erro, de maneira transparente e clara, seguindo os padrões de segurança de cada instituição. Nesse caso, também é necessário informar os procedimentos para a resolução do problema.
Compartilhamento de dados - Validação de titularidade 
# Etapa 4: Confirmação
DC - etapa 4#F4F5F7
## Requisitos - IT
**Cenário: Informações de consentimento**
1. Após a autenticação, a Instituição Transmissora de Dados deve apresentar ao usuário, no mínimo, as seguintes informações sobre o consentimento: Dados do objeto de compartilhamento. Instituição Receptora de Dados. Validade de consentimento (prazo e data final). Para os casos de prazo indeterminado, o prazo deve ser apenas identificado para o usuário como “indeterminado” ou termo similar, descartando necessidade de exibição de data final.
2. A Instituição Transmissora de Dados, na etapa de confirmação, deve exibir somente as categorias e agrupamentos de dados que foram selecionados pelo usuário no ambiente da Instituição Receptora de Dados.
Compartilhamento de dados - Informações de consentimento **Cenário: Seleção de origem**
1. Em casos de multiplicidade de origem/produto para as categorias de dados: Deve-se permitir a escolha da origem/produto, de acordo com o escopo de dados atualmente acessíveis no canal digital onde o usuário se relaciona com a Instituição Transmissora de Dados, seguindo as diretrizes. Todas as opções da origem/produto devem ser apresentadas pré-selecionadas, com a possibilidade do usuário de desmarcar uma ou mais origens para redução do escopo, mantendo, no mínimo, uma origem. Caso a marca escolhida contemple diferentes instituições que são percebidas pelo usuário de forma segregada, e isso cause multiplicidade de origens de dados para seleção, deve-se deixar claro a qual instituição cada opção de origem pertence.
**Nota:**Caso o login do usuário na Instituição Transmissora de Dados utilize o número da conta (acesso a uma conta por vez), não é esperado que haja multiplicidade de origem para a categoria Dados da Conta. Compartilhamento de dados - Seleção de origem
1. Não deve haver multiplicidade de origem/produto para categorias diferentes das seguintes: Dados de contas. Sejam contas de depósito à vista, de poupança, de pagamento pré-pagas ou pós-pagas. Cartões de crédito.
2. Para o restante das categorias de dados (dados cadastrais, investimentos, operações de crédito e câmbio), não haverá seleção de origens. Todos os dados existentes na Instituição Transmissora de Dados serão compartilhados Serão compartilhadas as submodalidades referentes aos produtos contratados ou distribuídos pela Instituição Transmissora de Dados e/ou as operações de câmbio contratadas, canceladas ou liquidadas pela Transmissora que são acessíveis por meio de seus canais digitais. Para casos em que dados transacionais de operações de crédito, investimento e/ou câmbio façam parte do escopo de dados, deve estar disponível informação de que se durante a vigência do compartilhamento o usuário vier a contratar ou realizar novas operações destas categorias, os dados destas novas contratações e operações serão automaticamente incluídos no consentimento em questão.
**Nota:**Os dados transacionais, operações de crédito, investimentos e de operações de câmbio serão compartilhados por até 12 meses retroativos, conforme [Resolução Conjunta nº1](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Resolu%C3%A7%C3%A3o%20Conjunta&numero=1).Compartilhamento de dados - Seleção de origem**Cenário: Detalhes dos dados compartilhados**
1. Por padrão, as informações secundárias (descritas abaixo) não devem aparecer de forma detalhada:

- O nome dos agrupamentos – exemplo: saldo, limites e extratos.
- O detalhamento de informações da tabela de dados – exemplo: transações de cartões de crédito - informações do cartão, identificação de transação, valor da transação, datas, identificação do estabelecimento. Para apresentar os detalhamentos que a Instituição Transmissora de Dados julgar como necessários, deve-se utilizar recursos de User Experience conforme padrões da instituição, por exemplo: pequenos botões de informação (tooltips) (?) (+), expandir informação ao passar o mouse (mouseover), link do tipo “Mostrar mais” etc.

1. Para situações nas quais o usuário compartilha uma categoria de produtos ou de contratos por meio de seleção única (ex.: operações de crédito, investimento e/ou câmbio), a Instituição Transmissora de Dados deve considerar todas as permissões para os produtos da mesma categoria, ainda que não os comercialize no momento da confirmação.
Compartilhamento de dados - Detalhes dos dados compartilhados **Cenário: Detalhes para a confirmação**
1. A Instituição Transmissora de Dados deve apresentar um indicativo para o usuário de qual será a próxima etapa da jornada.
2. Na etapa de confirmação, o usuário deve ser capaz de continuar a transmissão dos dados fazendo apenas uma única confirmação. De modo geral, a Instituição Transmissora de Dados deve retirar cliques desnecessários após a autenticação, sendo os únicos cliques adicionais previstos nesta etapa os de seleção das origens e digitação de credenciais, todos apenas quando necessário.
**Nota:**Reforçamos que, conforme [Instrução Normativa BCB n° 463 de 10/04/2024](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=463), referente à versão 6.0 do Manual de Experiência do usuário no Open Finance, e [Resolução Conjunta nº1 de 04/05/2020](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Resolu%C3%A7%C3%A3o%20Conjunta&numero=1), etapas adicionais ou utilização de métodos mais rigorosos de autenticação não contempladas atualmente no canal digital da Instituição Transmissora de Dados serão interpretadas como mecanismos que desincentivam o compartilhamento de dados.Compartilhamento de dados - Detalhes para a confirmação
1. A Instituição Transmissora de Dados deve disponibilizar a opção de interrupção da jornada de compartilhamento de dados, antes da confirmação. A opção de interrupção do fluxo não deve ser proeminente em relação ao botão “Confirmar”/”Continuar”.
2. Caso o usuário cancele a confirmação de compartilhamento na Instituição Transmissora de Dados, ele deve ser redirecionado de volta para a Instituição Receptora de Dados, respeitando os requisitos do redirecionamento de retorno (IT para IR). Ao receber o usuário de volta, a Instituição Receptora de Dados deve apresentar uma mensagem informando que o consentimento não foi realizado.
Compartilhamento de dados - Detalhes para a confirmação #F4F5F7
## Recomendações - IT
**Cenário: Detalhes dos dados compartilhados**
1. Para os seguintes produtos, as instituições podem disponibilizar opção para que o usuário possa visualizar em nível granular as informações vinculados a cada modalidade:

- Crédito (número do contrato, valor etc.);
- Investimento (renda fixa bancária, fundos de investimento etc.);
- Câmbio (identificação da operação, data de fechamento do contrato etc.).
Caso a instituição opte por disponibilizar o detalhamento das informações, este deverá ser ocultado por padrão e a instituição deverá disponibilizar recurso (botão, link, etc.) para permitir ao usuário visualizar o detalhamento do contrato/operação.
1. Caso a Instituição Transmissora de Dados não tenha algum agrupamento selecionado pelo usuário, ela pode mostrar uma mensagem relativa àquele agrupamento, por exemplo: “No momento não encontramos nenhum produto que atenda os dados selecionados”.
Compartilhamento de Dados - Detalhes dos dados compartilhadosType or paste something here to turn it into an excerpt.
# Etapa 5: Redirecionamento
DC - etapa 5#F4F5F7
## Requisitos - IT
**Cenário: Tela de transição**
1. Na etapa de redirecionamento, a Instituição Transmissora de Dados deve apresentar uma tela dedicada a esclarecer para o usuário que o processamento da operação está em andamento. A tela deve conter, no mínimo, as seguintes informações/elementos: Indicação de que o redirecionamento está em andamento. Indicação de que o redirecionamento é seguro.
**Nota:**Para o compartilhamento ser efetivado com sucesso, o usuário não pode sair da tela de redirecionamento e deve aguardar a abertura automática do aplicativo da Instituição Receptora de Dados. Por essa razão, é mais importante deixar claro ao usuário que a operação está sendo processada e é mais necessário aguardar do que informar sobre o redirecionamento em andamento.
1. Tanto a Instituição Receptora de Dados quanto a Instituição Transmissora de Dados não devem exigir qualquer ação adicional do usuário para confirmar o redirecionamento, o carácter da etapa é apenas informativo.
2. Em dispositivo móvel, o redirecionamento da Instituição Transmissora de Dados para a Instituição Receptora de Dados deve ocorrer diretamente para o aplicativo da Instituição Receptora de Dados, sem a passagem por navegadores intermediários.
3. O redirecionamento deve ocorrer para o mesmo ambiente da Receptora previamente utilizado para iniciar a jornada.
Compartilhamento dos dados - Tela de transição #F4F5F7
## Recomendações - IT
**Cenário: Interrupção da jornada**
1. Caso o fluxo do consentimento seja interrompido nesta etapa, deve existir fácil acesso à visualização do status do processo pelos canais digitais da Instituição.

# Etapa 6: Efetivação
DC - etapa 6#F4F5F7
## Requisitos - IR e IT
**Cenário: Mensagem de sucesso**
1. A partir do momento em que a etapa de confirmação tiver sido concluída, tanto a Instituição Transmissora de Dados quanto a Instituição Receptora de Dados devem incluir em seus ambientes de gestão Open Finance, de seus canais, informações e status do consentimento recém-confirmado.
#F4F5F7
## Requisitos - IR
**Cenário: Mensagem de sucesso**
1. Assim que o usuário retornar da Instituição Transmissora de Dados, a Instituição Receptora de Dados deve apresentar uma tela comunicando o sucesso (ou insucesso) do compartilhamento.
Compartilhamento de dados - Mensagem de sucesso**Cenário: Detalhes do consentimento**
1. No caso de consentimento efetivado com sucesso, também deve ser apresentado o resumo da solicitação, seja diretamente na tela de efetivação da jornada ou disponível por meio de um botão (como "detalhes" ou "veja mais") para uma consulta fácil e direta pelo usuário. Tal resumo deve conter, no mínimo, as seguintes informações: Validade do consentimento (prazo e data final). No caso de prazo indeterminado, identificar para o usuário como "Indeterminado" ou termo similar. Finalidade de uso dos dados compartilhados. Escopo de dados compartilhados (ex.: cadastrais, conta, cartões de crédito, investimentos e operações de crédito).
2. Caso algum escopo de dados inicialmente solicitado esteja ausente do compartilhamento efetivado e tal ausência não permita o cumprimento integral da funcionalidade, finalidade ou benefício oferecido pela Instituição Receptora de Dados, o usuário deve ser informado a respeito dos impactos.
**Nota:**O resumo contém as informações mínimas necessárias. Fica a critério de cada Instituição Receptora de Dados manter apenas o resumo ou substituí-lo por um comprovante mais completo.Compartilhamento de dados - Detalhes do consentimento#F4F5F7
## Recomendações - IR e IT
**Cenário: Geral**
1. A linguagem (“Termos para o Cliente”) presente no Glossário de Experiência pode ser simplificada, para evitar repetitividade, e apresentada de outras formas (p.ex.: no infinitivo).
#F4F5F7
## Recomendações - IR
**Cenário: Geral**
1. As Instituições Receptoras, no resumo do compartilhamento, poderão apresentar a identificação da Instituição de origem dos dados.