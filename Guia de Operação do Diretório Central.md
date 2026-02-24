---
id: 17378602
title: Guia de Operação do Diretório Central
version: 17
modified: 2025-05-03T04:20:37.841Z
url: /spaces/OF/pages/17378602/Guia+de+Opera+o+do+Diret+rio+Central
---

Este guia serve para orientar os participantes a atuar no Diretório Central em procedimentos necessários para a operação no Open Finance Brasil.Destina-se a administradores, contatos técnicos primários e secundários.Aqui estão descritas as etapas técnicas para cadastrar usuários, criar e manter declarações de software, tokens de acesso e servidores de autorização no ambiente de sandbox e produção do Diretório Central.
- Controle de Versão - [GODC]
- 01. Introdução Tipos de Usuários Relação - Organização x Marcas Pontos de Atenção no Cadastramento de Marca/Authorisation Server Cadastramento - Fase 1 x Fase 2 Exemplos de Possíveis Cenários
- 02. Registrando uma organização no Diretório Etapa 1: Entendendo como Adicionar uma Organização no Diretório
- 03. Registrando um usuário no Diretório Etapa 1: Registrando um Usuário no Diretório Etapa 2: Verificando os Dados Informados Etapa 3: Confirmando o Processo de Registro Etapa 4: Confirmação da Assinatura Eletrônica Etapa 5: Análise e Confirmação do Termo de Aceite Etapa 6: Assinando o Termo de Adesão da Instituição
- 04. Acessando uma Organisation Etapa 1: Exibindo Detalhes de uma Organização Cadastramento Conglomerado
- 05. Cadastrando contatos de notificação Etapa 1: Cadastrando um Novo Contato
- 06. Cadastrando reivindicações de domínio de autoridade Etapa 1: Cadastrando uma Nova Reivindicação de Domínio
- 07. Cadastrando reivindicações de autoridade Detalhamento das Modalidades Etapa 1: Cadastrando uma Nova Reivindicação de Função Etapa 2: Cadastrando um Usuário de Domínio de Autorização Sistemas e Funções de um Usuário/Contato
- 08. Cadastrando um Authorisation Server Etapa 1: Criando um Novo Servidor de Autorização Etapa 2: Cadastrando uma Certificação de Segurança no Servidor
- 09. Cadastrando recursos de uma API Cadastramento de Recursos Etapa 1: Cadastrando um Novo Recurso de uma API Etapa 2: Cadastrando um Novo Recurso de uma API com Certificação Automática - Fase 4A Etapa 3: Removendo um Recurso de uma API
- 10. Criando um Software Statements Etapa 1: Criando uma Nova Declaração de Software Etapa 2: Cadastrando Certificação de Declaração de Software
- 11. Criando uma nova reivindicação de autoridade de software Etapa 1: Criando Reivindicação de Autoridade de Software
- 12. Criando certificados de transporte e assinatura em Sandbox Etapa 1: Criando um Novo Certificado de Transporte Etapa 2: Criando um Novo Certificado de Assinatura
- 13. Carregando certificados emitidos por autoridade de certificação em Produção Etapa 1: Carregando Certificado de Transporte Etapa 2: Carregando Certificado de Assinatura
- 14. Cadastrando administradores da organização Etapa 1: Cadastrando um Administrador da Organização
- 15. Obtendo um Software Statements Assertion Etapa 1: Criando uma Nova Declaração de Software Assinada
- 16. Configurando eventos de notificação no Diretório Etapa 1: Inscrever-se em um Tópico Etapa 2: Solicitando uma Subscrição Etapa 3: Confirmando uma Subscrição Etapa 4: Analisando um Evento de Notificação
- 17. Obtendo um token de acesso para as APIs do Diretório Etapa 1: Localizando o Identificador do Cliente Etapa 2: Localizando a URL de Token no Diretório Etapa 3: Adicionando Certificados SSL por Domínio Etapa 4: Obtendo um Token de Acesso
- 18. Listando as organizações cadastradas no Diretório via API Etapa 1: Obtendo Detalhes das Organizações
- 19. Listando os servidores de autorização de uma organização via API Etapa 1: Listando os Servidores de Autorização
- 20. Obtendo um Software Statement via API Etapa 1: Obtendo um SS no Diretório via API
- 21. Obtendo um Software Statement Assertion via API Etapa 1: Obtendo um SSA do Diretório via API
- 22. Como se inscrever nas atualizações de lançamento do Diretório Etapa 1: Cadastrando o Recebimento de Release Notes Etapa 2: Acessando o Release Notes
- 23. Como obter suporte ao Diretório Service Desk
- 24. Anexos Mapa de utilização do Guia Operacional do Diretório por Papel Regulatório Modelo de Segurança

---

# 01. Introdução

---
id: 133758989
title: 01. Introdução
version: 4
modified: 2025-05-03T04:20:38.028Z
url: /spaces/OF/pages/133758989/01.+Introdu+o
---

O Open Finance ou Sistema Financeiro Aberto é uma iniciativa do Banco Central do Brasil que tem como principais objetivos trazer inovação ao sistema financeiro, promover a concorrência, e melhorar a oferta de produtos e serviços financeiros ao consumidor final. Este guia tem o objetivo de auxiliar os profissionais envolvidos no negócio e no desenvolvimento desse serviço, facilitando e esclarecendo dúvidas relacionadas ao Diretório e boas práticas envolvidas.
## Antes de Começar!
Esse guia tem como objetivo demostrar de forma prática a operação do Diretório Central do Open Finance Brasil. Além disso, ele é complementar a outras documentações disponibilizadas pela governança e não fazem parte do escopo do mesmo quaisquer detalhamentos relacionados a experiência do usuário e desenvolvedor, definições de segurança e especificação de APIs.**Todas as funcionalidades estão disponíveis em sandbox e podem ser testadas em:**[https://web.sandbox.directory.openbankingbrasil.org.br](https://web.sandbox.directory.openbankingbrasil.org.br/)Procedimentos em produção pendentes serão disponibilizados assim que possível.As ações aqui apresentadas podem ser realizadas tanto por administradores quanto por contatos técnicos primários e secundários.Para ilustrar este guia e tentar deixar as situações de uso mais palpáveis, foram criadas instituições e telas fictícias.Para ilustrar este guia e tentar deixar as situações de uso mais palpáveis, foram criadas instituições e telas fictícias.
- As instituições e marcas não são reais .
- As telas desenvolvidas, os softwares e sites são meramente ilustrativos , para que seja possível ver um exemplo de como os requisitos e as recomendações podem ser aplicados em situações de uso real.
- Nomenclaturas e imagens ilustrativas estão descritas na língua inglesa , devido sua ampla abrangência e por conter terminologia técnica que em algumas situações não dispõe de tradução literal. O ajuste do idioma no Diretório fica a critério do usuário, podendo ser ajustado a qualquer momento.

## Tipos-de-Usuários Tipos de Usuários
Neste exemplo, mostramos as diversas possibilidades suportadas de atribuições de função para um usuário cadastrado no Diretório.
| Público | O Diretório possibilita o cadastramento de usuários sem vínculos com nenhuma instituição. Esse tipo de usuário não tem nenhum acesso ou poder no Diretório. O cadastramento de um usuário relacionado a um participante, até que não seja feito o vinculo no Diretório, possui essas mesmas características. |
| --- | --- |
| Administrativo | Usuários com poderes de administração no Diretório, podendo realizar todas ações. |
| Operação | Usuários com poderes específicos no Diretório. |
| Plataforma | Usuários para gestão e operação das plataformas do ecossistema, como o Service Desk, Portal, Plataforma de Resolução de Disputas e Plataforma Centralizada (Ressarcimento). |
Para obter mais detalhes sobre consulte [Cadastrando um usuário de domínio de autorização](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/85360721/07.+Cadastrando+reivindica+es+de+autoridade#ETAPA-2:-Cadastrando-um-usuário-de-domínio-de-autorização) e **Poderes dos Usuários no Diretório**.
## Relação---Organização-x-Marcas Relação - Organização x Marcas
Neste exemplo, mostramos as diversas possibilidades suportadas para se realizar cadastros de organizações no Diretório. Assim, **uma organização pode ser cadastrada de forma independente ou pertencente a um conglomerado**. Já as marcas são uma forma mais amigável, democrática e fácil para identificação das instituições participantes. **Uma Marca de um conglomerado pode estar correlacionada a mais de uma Instituição Participante**, assim
como uma Instituição Participante pode estar
correlacionada a mais de uma marca.**Importante:** a Marca cadastrada no diretório será a mesma apresentada para escolha do usuário na Jornada de Compartilhamento de Dados e Iniciação de Pagamentos. As Instituições Participantes (ou organizações) também serão apresentadas em tela, apenas em caráter informativo. Para maiores detalhes, consulte o Guia de Experiência do Usuário.Para obter mais detalhes sobre como cadastrar uma marca veja a seção **Cadastrando um Authorisation Server**.
## Pontos-de-Atenção-no-Cadastramento-de-Marca/Authorisation-Server Pontos de Atenção no Cadastramento de Marca/Authorisation Server

- Uma marca é representada por um Authorisation Server e o mesmo sempre deve ser cadastrado associado a uma organização;
- O vinculo entre uma organização master (mãe) e uma organização que pertence ao conglomerado é realizado via o preenchimento do campo Parent Organization Reference ID no cadastro da organização filha, informando o CNPJ da organização mãe (caso seja necessário ajuste, favor entrar em contato com cadastro@openfinancebrasil.org.br );
- Quando a estrutura for de um conglomerado (uma organização master e uma ou mais organizações relacionadas) é recomendado o cadastro da marca na instituição mãe, caso as filhas venham a utilizar a mesma marca e arquitetura de autenticação. Importante ressaltar que caso não seja cadastrado uma marca exclusiva para o organização filha, será inferido que os cadastros de marcas para atendimento dos papéis regulatórios foi realizado na organização mãe;
- Caso a mesma marca pertença a mais de uma organização, esta deverá ser cadastra como um único Authorisation Server em apenas uma das organizações. É vedado a duplicação de marcas, ou seja, marcas que possuem o mesmo Customer Friendly Server Name ;
- Caso uma marca pertença exclusivamente a uma organização filha o cadastro poderá ser realizado apenas na filha;
- É permitido que o papel regulatório pertencente apenas à uma organização filha seja replicado na organização mãe para permitir o reuso de solução arquitetural e Authorisation Server.
Importante! Devido a questões históricas, algumas instituições apresentam marcas duplicadas. Por isso, é essencial que os clients das receptoras e iniciadoras de pagamento estejam preparadas para lidar com essa situação até que esses participantes migrem ou unifiquem seus servidores, a fim de regularizar a questão.
1. API Participants : Prefira por consumir dados da API Participants . Ela permite que o conteúdo seja fornecido ao usuário através de um servidor mais próximo, acelerando, assim, a distribuição e melhorando a experiência de consumo.
2. Webhook do Diretório : Inscreva-se no webhook do Diretório para receber os eventos de notificação das principais atualizações, como alteração de cadastro, atualização de marca,  entre outros.
3. Cache local : Alguns participantes optam pela utilização de estruturas de cache local. Assim, é recomendável a revalidação diária dos dados, a fim de mantê-los íntegros e com a versão mais recente possível.
Importante! Caso a instituição queira utilizar alguma chave forte, recomendamos utilizar o AuthorisationServerID. Os campos Customer Friendly Server Name e Description são especialmente susceptíveis a atualizações pelas organizações e não devem ser utilizados para esse fim
## Exemplos-de-Possíveis-Cenários Exemplos de Possíveis Cenários

| Organização e Marcas | Neste exemplo, temos uma “Organização” que não possui organizações filhas e possui os papéis regulatórios DADOS e CONTA. Neste cenário a organização possui apenas um AS/marca, a “Marca 1”, que possui todos os recursos necessários para atendimento dos seus papéis regulatórios. |
| Organização e Marcas | Neste exemplo, temos uma “Organização” que não possui organizações filhas e possui os papéis regulatórios DADOS e CONTA. Neste cenário a organização possui três AS/marcas, a “Marca 1” que possui os recursos necessários para atendimento do papel DADOS, a “Marca 2” que possui os recursos referente ao papel “CONTA” e a “Marca 3” atende a ambos os papéis regulatórios. |
| Conglomerado | O relacionamento entre as “organizações filhas” com a “organização mãe” é realizado via PARENT ORGANISATION REFERENCE ID, preenchendo o Parent das “organizações filhas” com o CNPJ da “organização mãe”. Quando uma “organização mãe” tem uma ou mais de uma “organização filha”, temos um conglomerado Neste exemplo, temos uma “organização mãe” que possui duas filhas e todas possuem os mesmos papéis regulatórios DADOS e CONTA. Neste cenário a “organização mãe” possui um AS/marca, a “Marca 1”, que possui apenas um AS/marca, a “Marca 1” que possui todos os recursos necessários para atendimento dos seus papéis regulatórios. Ambas as suas organizações filhas compartilham da mesma arquitetura e infraestrutura de autenticação, utilizando o mesmo AS/marca para compartilhamento dos seus recursos. |
| Organização e Marcas | Neste exemplo, temos uma “organização mãe” que possui duas filhas que possuem papéis regulatórios distintos. A “organização mãe” e a “organização filha 1” possuem o papel regulatório DADOS, enquanto a “Organização Filha 2” possui o papel regulatório CONTA. Neste cenário a “organização mãe” possui um AS/marca, a “Marca 1”, que possui apenas um AS/marca, a “Marca 1”, entregando todos os recursos necessários para atendimento do papéis regulatórios tanto para a “Organização Mãe”, quanto para a “Organização Filha 1”, compartilhando a mesma arquitetura e infraestrutura de autenticação. A “Organização Filha 2” possui a “Marca 2” que entrega os recursos necessários para atender ao seu papel regulatório. Neste caso, a “Organização Filha 2” possui a sua própria arquitetura e infraestrutura de autenticação. |
| Organização e Marcas | Neste exemplo, temos uma “organização mãe” que possui duas filhas que possuem papéis regulatórios distintos. A “Organização Mãe” e a “Organização Filha 1” possuem o papel regulatório DADOS, enquanto a “Organização Filha 2” possui o papel regulatório CONTA. Com a intenção de reuso da arquitetura e infraestrutura de autenticação, o participante replicou o papel regulatório da “Organização Filha 2” para a “Organização Mãe” e desta forma, com uso de uma única marca/AS, a “Marca A”, entrega todos os recursos necessários para atender aos papéis regulatórios do conglomerado. |
| Organização e Marcas | Neste exemplo, temos uma “Organização Mãe” que possui duas filhas e todas possuem os mesmos papéis regulatórios DADOS e CONTA. Neste cenário a “organização mãe” possui um AS/marca, a “Marca 1”, que possui apenas um AS/marca, a “Marca 1” que possui todos os recursos necessários para atendimento dos papéis regulatórios da “Organização Mãe” e “Organização Filha 1”. A “Organização Filha 2” possui a “Marca 2” que entrega os recursos necessários para atender dos seus papéis regulatórios. Neste caso, a “Organização Filha 2” possui a sua própria arquitetura e infraestrutura de autenticação. |

---

# 02. Registrando uma organização no Diretório

---
id: 134283265
title: 02. Registrando uma organização no Diretório
version: 1
modified: 2025-05-03T04:20:38.013Z
url: /spaces/OF/pages/134283265/02.+Registrando+uma+organiza+o+no+Diret+rio
---

## Etapa-1:-Entendendo-como-Adicionar-uma-Organização-no-Diretório Etapa 1: Entendendo como Adicionar uma Organização no Diretório
Para participação no Open Finance Brasil, é necessário que a instituição seja autorizada a funcionar pelo Banco Central, conforme mencionado no Art. 6º da Resolução Conjunta 1/2020 do BCB.As instituições autorizadas até momento do início do Open Finance em 2021 foram cadastradas No Diretório de participantes (Produção e Sandbox) pela Estrutura Central.Novos entrantes precisam contatar a Estrutura a partir do e-mail [cadastro@openfinancebrasil.org.br](mailto:cadastro@openfinancebrasil.org.br), enviando a comprovação de que a instituição é autorizada a funcionar pelo Banco Central.Maiores informações sobre o processo de autorização do BCB estão disponíveis em:
 [https://www.bcb.gov.br/estabilidadefinanceira/autorizabc](https://www.bcb.gov.br/estabilidadefinanceira/autorizabc) .Dúvidas sobre o processo de cadastro podem ser enviadas para o e-mail [cadastro@openfinancebrasil.org.br](mailto:cadastro@openfinancebrasil.org.br).**NOTA:** Não é possível efetuar o cadastro em Sandbox sem que a instituição seja uma instituição autorizada pelo BCB.

---

# 03. Registrando um usuário no Diretório

---
id: 133791791
title: 03. Registrando um usuário no Diretório
version: 3
modified: 2025-05-03T04:20:37.963Z
url: /spaces/OF/pages/133791791/03.+Registrando+um+usu+rio+no+Diret+rio
---

Para acessar o Diretório de participantes você precisa estar registrado com um usuário válido. Esta seção descreve as etapas necessárias para realizar o registro de um novo usuário.
## Etapa-1:-Registrando-um-Usuário-no-Diretório Etapa 1: Registrando um Usuário no Diretório

### Requisitos
**1.** No navegador, digite a `URL` de acordo com o ambiente a ser acessado:`Sandbox:`******[Open Banking Brasil Sandbox](https://web.sandbox.directory.openbankingbrasil.org.br/) `Produção:` [Open Banking Brasil](https://web.directory.openbankingbrasil.org.br/) **2.** Clique no link `Register`**3.** Na tela `Register for an account`, preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**4.** Clique no botão `Register`*.***NOTA:** E-mails sociais não são permitidos, e você deve utilizar um endereço de e-mail válido da instituição. O cadastro pode ser realizado por qualquer colaborador da organização, identificado aqui como um Iniciador de Cadastro, podendo ser tanto um contato administrativo quanto técnico da instituição.
## 03.Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| --- | --- | --- |
| `First Name` | Deve ser preenchido com o primeiro nome do usuário | Deve ser preenchido com o primeiro nome do usuário |
| `Family Name` | Deve ser preenchido com o sobrenome do usuário | Deve ser preenchido com o sobrenome do usuário |
| `E-mail Address` | Deve ser informado um endereço de e-mail corporativo | Deve ser informado um endereço de e-mail corporativo |
| `Phone Number` | Informar o número de telefone de contato do usuário. | Informar o número de telefone de contato do usuário. |
| `Password` | Definir uma senha que deve conter entre 8 e 24 caracteres com letras maiúsculas, minúsculas, números e ao menos um carácter especial | Definir uma senha que deve conter entre 8 e 24 caracteres com letras maiúsculas, minúsculas, números e ao menos um carácter especial |
| `Confirm Password` | Repetir a mesma senha informada no campo anterior. | Repetir a mesma senha informada no campo anterior. |
| `National ID (CPF)` | Informar o número de registro do Cadastro de Pessoa Física (CPF) | Informar o número de registro do Cadastro de Pessoa Física (CPF) |
| `Do you possess na e-signature certificate?` | O seletor deve estar assinalado caso o usuário possua um e-CPF. | Informar o número de registro do Cadastro de Pessoa Física (CPF) |

## Etapa-2:-Verificando-os-Dados-Informados Etapa 2: Verificando os Dados Informados

### Requisitos
**1.** Nesta etapa, o Diretório irá enviar uma senha de uso único (`OTP`), que será encaminhada ao endereço de e-mail e número de telefone informado na etapa anterior.**2.** No e-mail recebido, selecione, copie e cole o código `OTP` no campo `EMAIL VERIFICATION CODE`.**3.** Na mensagem SMS recebida no telefone celular, copie o código `OTP` e informe no campo `PHONE NUMBER VERIFICATION CODE`.**4.** Clique no botão `Verify`*.***NOTA:** Caso você não tenha recebido o e-mail com o código de confirmação, verifique sua caixa de `SPAM` e as politicas de bloqueio de mensagens. O envio das mensagens poderá sofrer algum atraso, contudo, se o problema persistir, clique no botão `Resend OTP` para reenvio das mensagens.
## Etapa-3:-Confirmando-o-Processo-de-Registro Etapa 3: Confirmando o Processo de Registro

### Requisitos
**1.** Nesta etapa, faça o *download* de um aplicativo de autenticação de sua preferência. É possível utilizar o *Google Authenticator*, *Microsoft Authenticator*, *LastPass* *Authenticator*, *1Password* entre outros.**2.** Digitalize o QR Code que aparece na página e no aplicativo de autenticação, copie e cole a senha de uso único (`OTP`).**3.** Clique no botão `Sign-In`
## Etapa-4:-Confirmação-da-Assinatura-Eletrônica Etapa 4: Confirmação da Assinatura Eletrônica

### Requisitos
**1.** Nesta etapa, será enviado um e-mail contendo um `link` para análise e assinatura do Termo de Aceite.**2.** Selecione e copie o código de acesso apresentado na janela `Confirmação de Assinatura Eletrônica`.**3.** Na mensagem recebida na caixa de entrada em nome da `DocuSign`, clique no *link* `ANALISAR DOCUMENTO`*.*Ao clicar, você será redirecionado para o website da `DocuSign`.**4.** No navegador, cole o valor copiado no passo 2 e cole no campo `Código de acesso`.**5.** Clique no botão `Validar`.
## Etapa-5:-Análise-e-Confirmação-do-Termo-de-Aceite Etapa 5: Análise e Confirmação do Termo de Aceite

### Requisitos
**1.** Nesta etapa, no website da DocuSign, clique no botão `Continuar`.**2.** Role o documento para baixo, e na página seguinte clique no ícone `Rubricar`*,* e ao final das páginas no ícone**`Assinar`.**3.** Clique no botão `Concluir`.**4.** Na janela `Salvar uma cópia do seu documento`, você pode ser inscrever para obter uma conta DocuSign gratuita e assinar todos os seus documentos eletronicamente. Nesta janela, também é possível clicar no ícone `Fazer Download`**e baixar uma cópia do documento assinado.**5.** Clique no botão `Submeter`. Ao clicar no botão Submeter, você aceita os Termos e Condições e reconhece que seus dados serão utilizados conforme descrito na Política de Privacidade da DocuSign.**6.** Na caixa de entrada, você receberá um e-mail enviado pela DocuSign contendo um cópia do documento `Termo de Aceite` assinado eletronicamente.**7.** Retorne ao Diretório, e na janela `Upload e-signature confirmation`**clique no botão**`Check status`. Se todas as etapas anteriores forem validadas com sucesso, você será automaticamente redirecionado à página inicial do Diretório.**8.** Se você optou por usar o e-CPF também para assinar o documento de aceite, o e-CPF será solicitado pelo Docusign.**9.** O selo de assinatura do e-CPF vai estar inseridos no Termo de Aceite que foi assinado.
## Etapa-6:-Assinando-o-Termo-de-Adesão-da-Instituição Etapa 6: Assinando o Termo de Adesão da Instituição

### Requisitos
**1.** Caso você seja o administrador da instituição e esteja configurando o termo de adesão ao Open Finance, será necessário selecionar os signatários do termo.**2.** Informe a quantidade de signatários e clique em `SALVAR`.**3.** Em seguida, você receberá por e-mail um documento via DocuSign.**4.** O código a ser inserido no DocuSign estará disponível em `"História TnC"`.**5.** Ao abrir o documento do DocuSign, você deverá indicar os representantes legais da organização.**6.** Os representantes receberão os e-mails do DocuSign para coletar as assinaturas e os documentos comprobatórios.**7.** O primeiro signatário precisará preencher o nome da Razão Social.**8.** Marcar o(s) tipo(s) de participação(ões) da instituição no Open Finance.**9.**E assinar o documento.

---

# 04. Acessando uma Organisation

---
id: 134283281
title: 04. Acessando uma Organisation
version: 2
modified: 2025-05-03T04:20:38.093Z
url: /spaces/OF/pages/134283281/04.+Acessando+uma+Organisation
---

Esta seção descreve as etapas necessárias para exibir detalhes de uma organização.
## Etapa-1:-Exibindo-Detalhes-de-uma-Organização Etapa 1: Exibindo Detalhes de uma Organização

### Requisitos
**1.**No Diretório, localize e selecione a sua organização.**2.** Revise as informações previamente cadastradas.**NOTA:** Os cadastrados foram realizados de forma antecipada a partir de informações fornecidas junto ao Banco Central do Brasil. É fundamental que as organizações verifiquem as informações cadastradas.Em Caso exista alguma divergência entre em contato pelo e-mail: [cadastro@openfinancebrasil.org.br](mailto:cadastro@openfinancebrasil.org.br)
## 04.Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| --- | --- | --- |
| `Status` | Define o estado atual do cadastro, se ativo ou não. | Active |
| `Organisation Name` | Deve ser informado o nome da organização. | BCO Wizcredi S.A. |
| `Tag` | Com o objetivo de identificar as Instituições de Transação de Pagamento (ITPs) homologadas no processo de onboarding do Open Finance | Instituição bancária; Instituição de pagamento;  Cooperativa de Crédito Singular, Central e Confederação; Corretora e Distribuidora de Títulos e Valores Mobiliários; Outra Instituição de Crédito; ITP Habilitada |
| `Registration Number-CNPJ` | Deve ser informado o número de Cadastro Nacional da Pessoa Jurídica (CNPJ) da organização. | 22.222.222/0002-22 |
| `Date of Creation` | Data de criação do registro de cadastro da organização. | 2021-01-07T11:13:08.531Z |
| `Company Registrar` | | Cadastro Nacional da Pessoa Jurídica |
| `Organisation ID` | Identificador da organização. Esta informação será gerada automaticamente. | cdc674fd-b019-5110-af5d-0268ed8227371 |
| `Parent Organisation Reference ID` | Deve ser informado o número de Cadastro Nacional da Pessoa Jurídica (CNPJ) da organização mãe para casos em que seja necessário a constituição de um conglomerado. O slide Cadastramento de conglomerados ilustra este cenário em mais detalhes. | 11.111.111/0001-11 |
| `Legal Name` | Deve ser informado o nome legal de cadastro da instituição. | Banco Wizcredi S.A. |
| `Address Line 1` | Deve ser informado o logradouro da organização. | Av. Dr. Chucri Zaidan 296 |
| `Address Line 2` | Deve ser informado o logradouro da organização. | Cidades Monções |
| `City` | Deve ser informado a cidade da organização. | São Paulo, SP |
| `Country` | Deve ser informado o país da organização. | BR |

## CADASTRAMENTO-DE-CONGLOMERADO Cadastramento Conglomerado
No diretório de participantes há o conceito de conglomerado.Assim, uma organização mãe poderá ser referenciada em um cadastro de uma organização filha, atribuindo-se o CNPJ da organização mãe no campo PARENT ORGANISATION REFERENCE ID da organização filha.**Importante!** Se a sua organização faz parte de um conglomerado é fundamental referenciar as organizações filhas com a organização mãe.

---

# 05. Cadastrando contatos de notificação

---
id: 134316033
title: 05. Cadastrando contatos de notificação
version: 1
modified: 2025-05-03T04:20:38.016Z
url: /spaces/OF/pages/134316033/05.+Cadastrando+contatos+de+notifica+o
---

Após o *onboarding* da instituição e do representante da mesma é necessário realizar o cadastro da equipe de contatos de notificação no Diretório Central. Esses contatos são para possíveis comunicações entre os participantes e a estrutura central.
## Etapa-1:-Cadastrando-um-Novo-Contato Etapa 1: Cadastrando um Novo Contato

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Contacts` e clique no botão `New Contact`.**3.** Na janela `New Contact`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**4.** Clique no botão `Save`.**NOTA:** Os usuários de notificação não possuem ações dentro do Diretório e nas demais plataformas do perímetro central.
## 05.Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| --- | --- | --- |
| `Contact Type*` | Tipo do contato (Business/Negócio, Technical/Técnico, Billing/Cobrança, Incident/Incidente e Security/Segurança) | Incident |
| `Department` | Deve ser informado o departamento do contato | Operações de TI |
| `First Name` | Deve ser informado o primeiro nome do contato | João |
| `Last Name` | Deve ser informado o sobrenome do contato | Silva |
| `Email*` | O endereço de e-mail do contato | joao.silva@wizcredi.com.br |
| `Phone Number*` | Deve ser informado o número de telefone do contato | +55 51 900000000 |
| `Additional Information` | Deve ser informado o e-mail para o grupo de notificação do contato. | openfinance@wizcredi.com.br |
| `PGP Public Key` | Deve ser preenchido com uma chave alfanumérica, para comunicação de dados de incidentes de Segurança entre instituições. | Como esta chave tem extensão muito grande para adicionar como exemplo, segue link para documentações que definem a chave PGP ( RFC 4880 ). |
| `Address Line 1` | Deve ser informado o endereço (Rua, Avenida ou Alameda) | Av. Dr. Chucri Zaidan 296 |
| `Address Line 2` | Deve ser informado o bairro | Cidades Monções |
| `City` | Deve ser informado a cidade de domicílio | São Paulo |
| `Post Code` | Deve ser informado o código portal | 99.999-99 |
| `Country` | Deve ser informado o país de domicílio | Brasil |
*Campo obrigatório
## Detalhamento-dos-Tipos-de-Contato Detalhamento dos Tipos de Contato

| Nome do campo | Descrição |
| `Business/Negócio` | Contato responsável pela gestão de negócio do Open Finance na instituição. |
| `Technical/Técnico` | Contato para tratativa de problemas técnicos do tipo: performance, disponibilidade e quanto a API’s de forma geral. |
| `Billing/Cobrança` | Contato responsável pela cobrança dos custos da estrutura central do Open Finance Brasil. |
| `Incident/Incidente` | Contato responsável pelo atendimento de incidentes relacionados ao Open Finance na instituição. |
| ` Security/Segurança` | Contato para tratativas relacionadas a problemas de caráter de segurança como DCR, certificados entre outros. |
*Campo obrigatório**NOTA:**Orientamos o cadastro de pelos menos 1 para cada um dos 5 tipos de contato. Além disso, é de inteira responsabilidade da instituição inserir os contatos técnicos para cada departamento e mantê-los sempre atualizados para que a comunicação entre as instituições participantes não seja prejudicada.Os contatos publicados no Diretório Central deverão ser utilizados **apenas** no contexto de implementação do Open Finance. Contatos com objetivos comerciais – ainda que estejam inseridos no contexto de Open Finance – como soluções de implementação ou infraestrutura, deverão ser evitados. Tal medida visa preservar a eficácia da comunicação do ecossistema.

---

# 06. Cadastrando reivindicações de domínio de autoridade

---
id: 134283333
title: 06. Cadastrando reivindicações de domínio de autoridade
version: 1
modified: 2025-05-03T04:20:38.078Z
url: /spaces/OF/pages/134283333/06.+Cadastrando+reivindica+es+de+dom+nio+de+autoridade
---

Esta seção explica as etapas para cadastrar reivindicações de domínio de autoridade.
## Etapa-1:-Cadastrando-uma-Nova-Reivindicação-de-Domínio Etapa 1: Cadastrando uma Nova Reivindicação de Domínio

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Authority Domain Claims`**e clique no botão `New Domain Claim`.**3.** Na janela `New Authority Domain Claim`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**4.** Clique no botão `Save`.
## 06.Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Authority Name*` | Informe o nome da autoridade. | Banco Central do Brasil |
| `Authorisation Domain Name*` | Informe o nome de domínio de autorização. | Open Finance Brasil |
| `Authority ID` | Exibe o identificador de autoridade única. Esta informação será gerada automaticamente. | 5360d5bf-5024-47cd-bd18-daab08df38ba |
| `Registration ID` | Informe o ID de registro de reivindicação de domínio exclusivo. Não é necessário preencher esta informação. | <CNPJ-OBB> |
*Campo obrigatório

---

# 07. Cadastrando reivindicações de autoridade

---
id: 134283363
title: 07. Cadastrando reivindicações de autoridade
version: 3
modified: 2025-05-03T04:20:37.909Z
url: /spaces/OF/pages/134283363/07.+Cadastrando+reivindica+es+de+autoridade
---

Esta seção explica as etapas para cadastrar reivindicações de autoridade e como adicionar usuários com suas respectivas funções que serão desempenhadas pela organização dentro do Open Finance.
## Detalhamento-das-Modalidades Detalhamento das Modalidades

| Nome da modalidade no diretório | Descrição |
| `DADOS` | Instituição transmissora e/ou receptora de dados é a instituição que sendo: Transmissora de dados: instituição participante que compartilha os dados com a instituição receptora; Receptora de dados: instituição participante que apresenta solicitação de compartilhamento à instituição transmissora para recepção dos dados. |
| `CONTA` | Instituição detentora de conta é a instituição participante que mantém conta de depósitos à vista ou de poupança ou conta de pagamento pré-paga de cliente. |
| `PAGTO` | Instituição prestadora de serviço de iniciação de transação de pagamento é uma instituição participante que presta serviço de iniciação de transação de pagamento. |
| `CCORR` | Instituição que tenha firmado, na condição de contratante, contrato de correspondente no País, cujo objeto contemple a atividade de atendimento prevista no art. 8º., inciso V, da Resolução nº 3.954, de 24 de fevereiro de 2011, por meio eletrônico. |
**NOTA:** As modalidades assumidas pelos participantes no âmbito do Open Finance são auto declaratórias e podem ser exercidas simultaneamente. Contudo, tais modalidades deverão estar em conformidade com o modelo de negócio do participante e estarão sujeitas à verificação pela fiscalização do Banco Central do Brasil, especialmente com relação ao cumprimento do princípio da reciprocidade no compartilhamento de dados no Open Finance Brasil.
## ETAPA-1:-CADASTRANDO-UMA-NOVA-REIVINDICAÇÃO-DE-FUNÇÃO Etapa 1: Cadastrando uma Nova Reivindicação de Função

### Requisitos
**1.** Necessário realizar a seção Cadastrando reivindicações de domínio de autoridade.**2.** No Diretório, localize e selecione a sua organização.**3.** Selecione o menu `Authority Domain Role Claims`**e clique no botão `New Role Claim`.**4.** Na janela `New Authority Domain Role Claim`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**5.** Clique no botão `Save`.
## 07.1-Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Authority Name*` | Selecione o nome da autoridade. | Banco Central do Brasil |
| `Authorisation Domain Name*` | Selecione o nome de domínio de autorização. | Open Finance Brasil |
| `Role*` | Selecione a modalidade (função) sendo um dos valores: CONTA, DADOS, CCORR ou PAGTO, para obter mais detalhes verifique em Detalhamento das modalidades . | DADOS |
| `Unique Technical Identifier` | Selecione o identificador técnico único. | |
| `Registration ID*` | Deve ser informado o número de registro único [ISPB-OBB-FUNÇÃO]. Substitua o [ISPB] pelos primeiros 8 dígitos do seu CNPJ e o [FUNÇÃO] pela sigla da função que você está inserindo. | 12345678-OBB-DADOS |
*Campo obrigatório
## ETAPA-2:-Cadastrando-um-usuário-de-domínio-de-autorização Etapa 2: Cadastrando um Usuário de Domínio de Autorização

### Requisitos
**1.** Necessário realizar a Cadastrando uma nova reivindicação de domínio.**2.** No Diretório, localize e selecione a sua organização.**3.** Selecione o menu `Authority Domain Role Claims`**, será carregado um submenu  na parte superior esquerda , clique no link `Authorisation Domain User`****4.** Na janela clique no botão `New Authorisation Domain User`.**5.** Na janela `New Authorisation Domain User`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**6.** Clique no botão `Save`.
## 07.2-Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Domain Name` | É apresentado o domínio de autorização para o qual esta a reivindicação de domínio está mapeada. | Open Finance Brasil |
| `Authorisation Domain Role` | É apresentada a função mapeada para o domínio de autorização. | DADOS |
| `System*` | Selecione o sistema de contato sendo um dos valores a seguir: Directory, Service Desk, Dispute Resolution, Portal ou Centralized Platform . Para obter mais detalhes verifique em Sistemas e Funções de um usuário/contato . | Directory |
| `Contact Role*` | Selecione o papel assumido pelo contato. Para obter mais detalhes verifique em Sistemas e Funções de um usuário/contato . | PBC |
| `Email*` | Deve ser informado o endereço de e-mail corporativo do contato. | joao.silva@wizcredi.com.br |
*Campo obrigatório
## SISTEMAS-E-FUNÇÕES-DE-UM-USUÁRIO/CONTATO Sistemas e Funções de um Usuário/Contato
**NOTA:**
- Os perfis para os sistemas Directory, Service Desk e Dispute Resolution são obrigatórios.
- Para obter mais detalhes dos poderes do usuário verifique a tabela Modelo de Segurança .
- Podem existir quantos contatos primários e secundários a instituição achar necessário.
- Contatos primários podem acessar o Diretório e adicionar contatos secundários. Já os Contatos secundários não conseguem acessar o Diretório e consequentemente, não conseguem adicionar novos usuários secundários.
- A implementação dos poderes de acesso de contatos primários e secundários dependem e podem variar de plataforma.
- Os perfis de administradores do Diretório são responsáveis por toda a administração do ambiente, o que inclui a adição ou remoção de usuários, recepção de notificações, cadastro de novos administradores e contatos da instituição, concessão de acesso à outras plataformas e responsável pelas publicações técnicas. Não existe a exigência que esse perfil seja procurador da instituição

---

# 08. Cadastrando um Authorisation Server

---
id: 133792023
title: 08. Cadastrando um Authorisation Server
version: 4
modified: 2025-05-03T04:20:38.043Z
url: /spaces/OF/pages/133792023/08.+Cadastrando+um+Authorisation+Server
---

Durante a jornada de consentimento do usuário, os receptores exibirão a marca e o servidor de autorização que está sendo solicitado o acesso aos dados do usuário. Esta seção descreve as etapas necessárias para cadastrar as marcas e os servidores de autorização da organização.
## Etapa-1:-Criando-um-Novo-Servidor-de-Autorização Etapa 1: Criando um Novo Servidor de Autorização

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Authorisation Servers`. No canto superior esquerdo será carregado um submenu, para cadastrar um novo authorisations Server clique no botão `New Authorisation Server`  localizado no lado direito da tela.**3.** Na janela `New Authorisation Server`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**Atenção 1:** Tendo em vista a ausência de análise de impacto para o ecossistema da retirada de um Authorisation Server, recomenda-se que os AS responsáveis por consentimentos não sejam retirados do diretório até a expiração/revogação dos consentimentos pelos quais é responsável.**Atenção 2:**Caso a instituição queira utilizar alguma chave forte, recomendamos utilizar o AuthorisationServerID. Os campos Customer Friendly Server Name e Description são especialmente susceptíveis a atualizações pelas organizações e não devem ser utilizados para esse fim**Atenção 3:**Não é necessária atualização de Authorisation Server no Diretório caso a instituição seja iniciador de transação de pagamentos puro.
## 08.Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Customer Friendly Server Name*` | Deve ser definido o valor da marca que será exibido no receptor. Apresentar seu nome por inteiro, sem abreviações, de forma a ser reconhecido pelo cliente e aderente a interfaces menores. •Limite de caracteres: 40 (padrão do campo) Para mais informações sobre marca, consulte o Guia de Experiência de Usuário. | Wizcredi |
| `OpenID Discovery Document URL*` | O URL para a localização do documento de descoberta OpenID. | https://www.wizcredi.com.br/.well-known/openid-configuration |
| `Payload Signing Certificate URL*` | O URL para a localização do certificado de assinatura. | https://www.wizcredi.com.br/jwks |
| `Customer Friendly Logo URL*` | Deve ser definida a URL para o logotipo da marca. Para obter mais detalhes sobre formato, dimensão e peso máximo do arquivo consulte o Guia de Experiencia Fase 2. | https://www.wizcredi.com.br/logo.svg |
| `Developer Portal URL` | O URL do portal do desenvolvedor. | https://developers.wizcredi.com.br |
| `Terms Of Service URL` | A URL de localização do documento de termos e serviços da organização. | https://www.wizcredi.com.br/tos.html |
| `Notification Webhook Endpoint` | Endpoint do Webhook de notificação. A seção Configurando eventos de notificação no Diretório descreve esta configuração em mais detalhes. | https://webhook.site/9d84a827-c200-4170-b0f8-f830170037bb |
| `Description*` | Esse é um texto de marcação onde deverá ser descrita a marca, trazendo informações adicionais para que o cidadão não tenha dúvidas sobre a escolha feita. Limite de caracteres: 256 (padrão do campo) Não deve ser permitido que a descrição traga links O que deve conter: Esse é um texto de marcação onde deverá ser descrita a marca, trazendo informações adicionais para que o cidadão não tenha dúvidas sobre a escolha feita. Orientações sobre o que pode conter: Texto institucional de apresentação Desde quanto atua Diferenciais de atuação Canais de atendimento | “A insituição Wizcredi atua desde 2000 sendo um dos maiores bancos do Brasil, seja na web ou pelo App oferecemos serviços de pagamentos, ofertas de crédito e investimentos para Pessoas Físicas.” |
| `Deprecation Date` | Data programada para iniciar a descontinuação do servidor de autorização | N/A |
| `Retirement Date` | Data programada para a aposentadoria do servidor | N/A |
| `SupersededByAuthorisationServerId` | ID do servidor de autorização que substituirá o servidor atual | N/A |
| `Status` | Indica se o servidor está Ativo, Inativo ou Descontinuado | N/A |
*Campo obrigatório**NOTA:** O campo Customer Friendly Logo URL é o que a receptora deverá utilizar para apresentar a logomarca da transmissora.
## Detalhamento-do-Logotipo Detalhamento do Logotipo
O logotipo das instituições participantes deverá ser  aplicado no Portal do Cidadão e também poderá  ser aplicado no redirecionamento entre instituições durante a Jornada de Compartilhamento de Dados.**Por isso foram deliberadas práticas para uso e disponibilização:**
- Utilizar preferencialmente logotipo prioritário, que os clientes  reconheçam nos canais;
- Versão reduzida do logo, símbolo ou favicon de site;
- Enviar arquivo SVG contendo a área de proteção do logo da  instituição para garantir a leitura e o espaçamento correto;
- Formato de envio:
**SVG**
- Dimensão mínima: 512px x 512px
- Sem sombra
- Peso máximo do arquivo: 1 mega;

## Etapa-2:-Cadastrando-uma-Certificação-de-Segurança-no-Servidor Etapa 2: Cadastrando uma Certificação de Segurança no Servidor

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Authorisation Servers`.  Depois selecione o servidor de autorização que deseja. Após selecionar, vá no submenu à esquerda em cima e clique em Server Certifications.**3.**Dentro dessa área, para cadastrar uma nova certificação, clique no botão `Add New Certification`**localizado no lado direito da tela.**4.** Na janela `New certification`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.As informações da certificação do Authorisation Server são referentes a certificação FAPI obtida através da [OpenID Foundation](https://openid.net/certification/). Dentro do site é possível encontrar uma tabela **Brazil Open Finance (Based on FAPI 1 Advanced Final)**que contém as informações que devem ser refletidas no formulário para adição da certificação de segurança.
## Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Certification type*` | O tipo de certificação que foi efetuada com a OpenID Foundation – Deve ser adicionado ao menos uma certificação Redirect (FAPI) e uma DCR | Redirect DCR CIBA – certificação ainda não disponível |
| `Certification type variant*` | As variantes dependem do tipo de certificação escolhida. Dentro da tabela da OpenID Foundation, cada coluna representam as possíveis variações nas certificações. Vale notar que JARM não é requisitado segundo a especificação de segurança logo não está presente como uma opção a ser adicionada Para a certificação DCR a instiuiçao deve avaliar se certificou utilizadondo APIs de Dados do consumidor – Unsigned , ou de Pagamentos - Signed | Se escolheu Redirect: •FAPI Adv. OP w/ MTLS •FAPI Adv. OP w/ MTLS, PAR •FAPI Adv. OP w/ Private Key •FAPI Adv. OP w/ Private Key, PAR Se escolheu DCR: •DCR Signed payload – JWT •DCR Unsigned payload - JSON |
| `Profile version*` | A versão da certificação selecionado – Campo livre, apenas para controle da própria instituição | 1 |
| `Certification payload*` | O URL que aponta para o arquivo hospedado pela OpenID Foundation com o pacote de certificação. Formato zip. | https://openid.net/wordpress-content/uploads/2021/08/BR-OB_Adv._OP_MTLS-exemplo.zip |
| `Start date of certification*` | A data de certificação inicial – é a mesma data que consta na tabela da OpenID Foundation. Formato dd/mm/yyyy | 09/05/2022 |
*Campo obrigatório**Descontinuação/Aposentadoria de Authorisation Server**Para o cenário de uma Organização ou Conglomerado que tome a decisão de descontinuar/aposentar uma marca (Authorisation Server), ficam especificadas abaixo, as regras para preenchimento dos campos no diretório e outros pontos importantes:
| Nome do Campo | Descrição | Exemplo | Regra de preenchimento |
| Deprecation Date | Data programada para iniciar a descontinuação do servidor de autorização | 2024-11-01 | Data a partir da qual o Authorisation Server não aceitará mais requisições de novos consentimentos |
| Retirement Date | Data programada para a aposentadoria do servidor | 2024-12-01 | Data a partir da qual o Authorisation Server será Inativado |
| SupersededByAuthorisationServerId | ID do servidor de autorização que substituirá o servidor atual | xxxxxxxx-XXXX-xxxx-XXXX-xxxxXXXXxxxx | ID do servidor de autorização que passará a recepcionar os pedidos de novos consentimentos a partir da inatividade do servidor em questão |
 Pontos Importantes:
- As datas inseridas nos campos citados, devem ser informadas e acordadas com o regulador.
- A boa prática sugerida é que a data de depreciação seja anterior a data de aposentadoria em pelo menos 1 mês (30 dias corridos), a ser validada caso a caso junto ao regulador.
- Esses campos são meramente informativos. Isso significa que, é de responsabilidade da Instituição que está descontinuando/aposentando a marca construir uma solução para "recusar" as requisições de consentimento recebidas a partir da data informada no campo " Deprecation Date ", não sendo responsabilidade das demais Instituições participantes não requisitarem novos consentimentos através do Authorisation Server, uma vez que o mesmo permanece como "Ativo" até a data de sua aposentadoria.
- Os consentimentos de transmissão ativos na marca que está sendo descontinuada/aposentada deverão continuar acessíveis para as Instituições receptoras, seguindo as regras de "tempo" determinadas pela regulação e especificações vigentes.

---

# 09. Cadastrando recursos de uma API

---
id: 133759051
title: 09. Cadastrando recursos de uma API
version: 2
modified: 2025-05-03T04:20:37.921Z
url: /spaces/OF/pages/133759051/09.+Cadastrando+recursos+de+uma+API
---

Esta seção explica as etapas para cadastrar os *endpoints* de recursos de uma API.
## Cadastramento de Recursos - Fase 1
Para cada uma das famílias de APIs devem ser adicionadas todos os endpoints disponíveis. Supondo que a instituição tenha disponibilizado dados em todos os endpoints da fase 1, a publicação deveria ser:
## Cadastramento de Recursos - Fase 2
Na Fase 2 o padrão de cadastramento continua como na Fase 1, segue alguns pontos de atenção:
- Para a API de consentimento é necessário apenas o cadastramento de uma entrada para o GET e o DELETE;
- A API de customers foi dividida em duas famílias para facilitar o consumo pelos receptores. Customers-business onde é cadastrado os Endpoints PJ e customers-personal onde será cadastrado os endpoints PF. Cabendo aqui o cadastramento conforme a disponibilização do produto pela instituição;
- O cadastramento de recursos deve respeitar a tabela de etapas da implementação assistida, conforme IN BCB n° 136 de 29/7/2021;
- Para as APIs v2 da Fase 2 será necessário adicionar novos Family tipes informando a versão 2 e sua certificação.
Exemplo de preenchimento, levando em consideração que a instituição disponibilize tanto PF e PJ e o inicio da implementação assistida.
## Cadastramento de Recursos - Fase 3
Na Fase 3 o padrão de segue alguns pontos de atenção:
- A API de payments foi dividida para facilitar o consumo pelos iniciadores.
- Na família de payments-consents devem ser declarados os endpoints de consentimento.
- Na família de payments-pix devem ser declarado sos endpoints da forma de pagamento PIX.
- Demais formas de pagamentos devem ser cadastradas conforme as especificações avancem.
Exemplo de preenchimento
## Tabela Exemplo de Recursos - Fase 1

| API | Diretório (Family Type) | Recursos (resources) |
| `discovery` | `discovery` | https://api.banco.com.br/open-banking/discovery/v1/status https://api.banco.com.br/open-banking/discovery/v1/outages |
| `channels` | `channels` | https://api.banco.com.br/open-banking/channels/v1/branches https://api.banco.com.br/open-banking/channels/v1/electronic-channels https://api.banco.com.br/open-banking/channels/v1/phone-channels https://api.banco.com.br/open-banking/channels/v1/banking-agents https://api.banco.com.br/open-banking/channels/v1/shared-automated-teller-machines |
| `products-services` | `products-services` | https://api.banco.com.br/open-banking/products-services/v1/personal-accounts https://api.banco.com.br/open-banking/products-services/v1/business-accounts https://api.banco.com.br/open-banking/products-services/v1/personal-loans https://api.banco.com.br/open-banking/products-services/v1/business-loans https://api.banco.com.br/open-banking/products-services/v1/personal-financings https://api.banco.com.br/open-banking/products-services/v1/business-financings https://api.banco.com.br/open-banking/products-services/v1/personal-invoice-financings https://api.banco.com.br/open-banking/products-services/v1/business-invoice-financings https://api.banco.com.br/open-banking/products-services/v1/personal-credit-cards https://api.banco.com.br/open-banking/products-services/v1/business-credit-cards https://api.banco.com.br/open-banking/products-services/v1/personal-unarranged-account-overdraft https://api.banco.com.br/open-banking/products-services/v1/business-unarranged-account-overdraft |
| `admin` | `admin` | https://api.banco.com.br/open-banking/admin/v1/metrics |

## Tabela Exemplo de Recursos - Fase 2

| API | Diretório (Family Type) | Recursos (resources) |
| `consents` | `consents` | https://api.banco.com.br/open-banking/consents/v1/consents https://api.banco.com.br/open-banking/consents/v1/consents/{consentId} |
| `resources` | `resources` | https://api.banco.com.br/open-banking/resources/v1/resources |
| `customers` | `customers-bussines` `customers-personal` | `customers-personal` https://api.banco.com.br/open-banking/customers/v1/personal/identifications https://api.banco.com.br/open-banking/customers/v1/personal/qualifications https://api.banco.com.br/open-banking/customers/v1/personal/financial-relations `customers-bussines` https://api.banco.com.br/open-banking/customers/v1/business/identifications https://api.banco.com.br/open-banking/customers/v1/business/qualifications https://api.banco.com.br/open-banking/customers/v1/business/financial-relations |
| `credit-cards-accounts` | `credit-cards-accounts` | https://api.banco.com.br/open-banking/credit-cards-accounts/v1/accounts https://api.banco.com.br/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId} https://api.banco.com.br/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/limits https://api.banco.com.br/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions https://api.banco.com.br/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/bills https://api.banco.com.br/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/bills/{billId}/transactions |
| `accounts` | `accounts` | https://api.banco.com.br/open-banking/accounts/v1/accounts https://api.banco.com.br/open-banking/accounts/v1/accounts/{accountId} https://api.banco.com.br/open-banking/accounts/v1/accounts/{accountId}/balances https://api.banco.com.br/open-banking/accounts/v1/accounts/{accountId}/transactions https://api.banco.com.br/open-banking/accounts/v1/accounts/{accountId}/overdraft-limits |
| `loans` | `loans` | https://api.banco.com.br/open-banking/loans/v1/contracts https://api.banco.com.br/open-banking/loans/v1/contracts/{contractId} https://api.banco.com.br/open-banking/loans/v1/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/loans/v1/contracts/{contractId}/payments https://api.banco.com.br/open-banking/loans/v1/contracts/{contractId}/scheduled-instalments |
| `financings` | `financings` | https://api.banco.com.br/open-banking/financings/v1/contracts https://api.banco.com.br/open-banking/financings/v1/contracts/{contractId} https://api.banco.com.br/open-banking/financings/v1/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/financings/v1/contracts/{contractId}/payments https://api.banco.com.br/open-banking/financings/v1/contracts/{contractId}/scheduled-instalment |
| `unarranged-accounts-overdraft` | `unarranged-accounts-overdraft` | https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v1/contracts https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId} https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId}/payments https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId}/scheduled-instalments |
| `invoice-financings` | `invoice-financings` | https://api.banco.com.br/open-banking/invoice-financings/v1/contracts https://api.banco.com.br/open-banking/invoice-financings/v1/contracts/{contractId} https://api.banco.com.br/open-banking/invoice-financings/v1/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/invoice-financings/v1/contracts/{contractId}/payments https://api.banco.com.br/open-banking/invoice-financings/v1/contracts/{contractId}/scheduled-instalments |

## Tabela Exemplo de Recursos - Fase 2 v2

| API | Diretório (Family Type) | Recursos (resources) |
| `consents` | `consents` | https://api.banco.com.br/open-banking/consents/v2/consents https://api.banco.com.br/open-banking/consents/v2/consents/{consentId} |
| `resources` | `resources` | https://api.banco.com.br/open-banking/resources/v2/resources |
| `customers` | `customers-bussines` `customers-personal` | `customers-personal` https://api.banco.com.br/open-banking/customers/v2/personal/identifications https://api.banco.com.br/open-banking/customers/v2/personal/qualifications https://api.banco.com.br/open-banking/customers/v2/personal/financial-relations `customers-bussines` https://api.banco.com.br/open-banking/customers/v2/business/identifications https://api.banco.com.br/open-banking/customers/v2/business/qualifications https://api.banco.com.br/open-banking/customers/v2/business/financial-relations |
| `credit-cards-accounts` | `credit-cards-accounts` | https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId} https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills https://api.banco.com.br/open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions |
| `accounts` | `accounts` | https://api.banco.com.br/open-banking/accounts/v2/accounts https://api.banco.com.br/open-banking/accounts/v2/accounts/{accountId} https://api.banco.com.br/open-banking/accounts/v2/accounts/{accountId}/balances https://api.banco.com.br/open-banking/accounts/v2/accounts/{accountId}/transactions https://api.banco.com.br/open-banking/accounts/v2/accounts/{accountId}/transactions-current https://api.banco.com.br/open-banking/accounts/v2/accounts/{accountId}/overdraft-limits |
| `loans` | `loans` | https://api.banco.com.br/open-banking/loans/v2/contracts https://api.banco.com.br/open-banking/loans/v2/contracts/{contractId} https://api.banco.com.br/open-banking/loans/v2/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/loans/v2/contracts/{contractId}/payments https://api.banco.com.br/open-banking/loans/v2/contracts/{contractId}/scheduled-instalments |
| `financings` | `financings` | https://api.banco.com.br/open-banking/financings/v2/contracts https://api.banco.com.br/open-banking/financings/v2/contracts/{contractId} https://api.banco.com.br/open-banking/financings/v2/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/financings/v2/contracts/{contractId}/payments https://api.banco.com.br/open-banking/financings/v2/contracts/{contractId}/scheduled-instalment |
| `unarranged-accounts-overdraft` | `unarranged-accounts-overdraft` | https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v2/contracts https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId} https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/payments https://api.banco.com.br/open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments |
| `invoice-financings` | `invoice-financings` | https://api.banco.com.br/open-banking/invoice-financings/v2/contracts https://api.banco.com.br/open-banking/invoice-financings/v2/contracts/{contractId} https://api.banco.com.br/open-banking/invoice-financings/v2/contracts/{contractId}/warranties https://api.banco.com.br/open-banking/invoice-financings/v2/contracts/{contractId}/payments https://api.banco.com.br/open-banking/invoice-financings/v2/contracts/{contractId}/scheduled-instalments |

## Tabela Exemplo de Recursos - Fase 3

| API | Diretório (Family Type) | Recursos (resources) |
| `payments` | `payments-consents` `payments-pix` | payments-consents https://api.banco.com.br/open-banking/payments/v1/consents https://api.banco.com.br/open-banking/payments/v1/consents/{consentId} payments-pix https://api.banco.com.br/open-banking/payments/v1/pix/payments https://api.banco.com.br/open-banking/payments/v1/pix/payments/{paymentId} |

## Etapa-1:-Cadastrando-um-Novo-Recurso-de-uma-API Etapa 1: Cadastrando um Novo Recurso de uma API

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Authorisation Servers`**e clique no link do servidor de autorização na qual se deseja cadastrar os recursos.**3.** No canto superior esquerdo da página clique em `API Resources`.**4.** Na página que será carregada clique no botão `New API Resources` para abrir a janela `New API Resource`*.***5.**Na janela `New API Resource`*,*clique na caixa de seleção `API Family Type` e selecione uma das opções disponíveis.**6.**No campo ao lado, em *Version*especifique o valor apropriado utilizando versionamento semântico (major.minor.patch, exemplo 1.0.7)**7.** No campo `Certification URL` é necessário informar a URL onde se encontra a localização do certificado publicado no GitHub. Esse preenchimento é obrigatório para famílias de API’s a partir da Fase 2 e clique no botão `Save`.**NOTA 1:** A URL a ser informada deve ser a presente no [GitHub](https://github.com/OpenBanking-Brasil/conformance/tree/main/submissions/functional) no caminho: `conformance > submissions/functional` selecionando a API especifica e informar a URL com o artefato de certificação .zip.*Exemplo:*[https://openbanking-brasil.github.io/conformance/submissions/functional/](https://openbanking-brasil.github.io/conformance/submissions/functional/)<family-type>/<version>/<file-name>.zip**NOTA 2:** No ambiente de Sandbox do Diretório, caso não exista uma certificação, é possível incluir um endereço para testes: [https://openbanking-brasil.github.io/teste.zip](https://opennanking-brasil.github.io/teste.zip)**8.** De volta a tela `API Resources`, informe URL principal no campo `API Discovery Endpoints`*,*e em seguida pressione a tecla `Enter`*.***9.** Para cada uma das famílias de APIs repita os passos 4 a 7.**NOTA:** Todos os *endpoints* deverão ser preenchidos, incluindo os respectivos recursos. Para obter mais detalhes sobre o padrão do *endpoints* e versão consulte o Portal do Desenvolvedor do Open Finance.
## Cadastramento-de-Recursos---Fase-4A Cadastramento de Recursos - Fase 4A
Na Fase 4A o padrão de cadastro segue alguns pontos de atenção:
- O cadastro das APIs deve ser realizado individualmente, para cada um dos recursos/endpoints existirá um tipo de família (Family Type)
- Diferente das outras famílias, ao requisitar o cadastro dessas APIs, será executado um teste de conformidade funcional que verificará a conformidade da API com a especificação do Swagger
- O diretório só permitirá o cadastro da API caso o teste de conformidade seja bem sucedido
- Semelhante a Fase 1, a publicação do recurso é condiciona a IF possuir tal produto, logo, não necessariamente todos os recursos precisam ser publicados
Exemplo de preenchimento
## Cadastramento de Recursos - Fase 4A (1/2)

| API | Diretório (Family Type) | Recursos (resources) |
| `opendata-investments` | `opendata-investments_funds` `opendata-investments_bank-fixed-incomes` `opendata-investments_credit-fixed-incomes` `opendata-investments_variable-incomes` `opendata-investments_treasure-titles` | `opendata-investment-funds` https://api.banco.com.br/open-banking/opendata-investments/v1/funds `opendata-investments-bank-fixed-incomes` https://api.banco.com.br/open-banking/opendata-investments/v1/bank-fixed-incomes `opendata-investments-credit-fixed-incomes` https://api.banco.com.br/open-banking/opendata-investments/v1/credit-fixed-incomes `opendata-investments-variable-incomes` https://api.banco.com.br/open-banking/opendata-investments/v1/variable-incomes `opendata-investments-treasure-titles` https://api.banco.com.br/open-banking/opendata-investments/v1/treasure-titles |
| `opendata-capitalization` | `opendata-capitalization_bonds` | `opendata-capitalization-bonds` https://api.banco.com.br/open-banking/opendata-capitalization/v1/bonds |
| `opendata-exchange` | `opendata-exchange_online-rates` `opendata-exchange_vet-values` | `opendata-exchange-online-rates` https://api.banco.com.br/open-banking/opendata-exchange/v1/online-rates `opendata-exchange-vet-values` https://api.banco.com.br/open-banking/opendata-exchange/v1/vet-values |

## Cadastramento de Recursos - Fase 4A (2/2)

| API | Diretório (Family Type) | Recursos (resources) |
| `opendata-acquiring-services` | `opendata-acquiring-services_personals` `opendata-acquiring-services_businesses` | `opendata-acquiring-services-personals` https://api.banco.com.br/open-banking/opendata-acquiring-services/v1/personals `opendata-acquiring-services-businesses` https://api.banco.com.br/open-banking/opendata-acquiring-services/v1/businesses |
| `opendata-pension` | `opendata-pension_risk-coverages` `opendata-pension_survival-coverages` | `opendata-pension-risk-coverages` https://api.banco.com.br/open-banking/opendata-pension/v1/risk-coverages `opendata-pension-survival-coverages` https://api.banco.com.br/open-banking/opendata-pension/v1/survival-coverages |
| `opendata-insurance` | `opendata-insurance_automotives` `opendata-insurance_homes` `opendata-insurance_personals` | `opendata-insurance-automotives` https://api.banco.com.br/open-banking/opendata-insurance/v1/automotives `opendata-insurance-homes` https://api.banco.com.br/open-banking/opendata-insurance/v1/homes `opendata-insurance-personals` https://api.banco.com.br/open-banking/opendata-insurance/v1/personals |

## Etapa-2:-Cadastrando-um-Novo-Recurso-de-uma-API-com-Certificação-Automática---Fase-4A Etapa 2: Cadastrando um Novo Recurso de uma API com Certificação Automática - Fase 4A

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Authorisation Servers`**e clique no link do servidor de autorização na qual se deseja cadastrar os recursos.**3.** No lado esquerdo da tela clique em `API Resources`**4.** Clique no botão `New API Resources` para abrir a janela `New API Resource`**5.** Na janela `New API Resource`*,*clique na caixa de seleção `API Family Type` e selecione uma das opções disponíveis que possuem certificação automática**6.** No campo ao lado, em `Version`**especifique o valor da versão da API conforme especificação**7.** No campo `THE URL FOR THE API`**é necessário informar a URL referente ao recurso da API a ser registrado**8.** A URL da API deve seguir o formato especificado no portal do desenvolvedor, caso contrário o diretório irá retornar um erro, não permitindo a continuidade do cadastro**9.** Ao selecionar `Save`**uma janela irá aparecer informando que ao pressionar `OK` um teste de conformidade será executado contra o recurso preenchido acima**NOTA 1:** O valor informado no campo `THE URL FOR THE API` é a URI contra a qual o teste será executado.**NOTA 2:** Caso o teste de conformidade não seja bem sucedido é possível consultar os logs de execução do teste que impediu a publicação da API. Para isso basta copiar a URL apresentada na mensagem de erro e colar na barra do navegador.**10.** Caso a execução seja mal sucedida, é possível consultar os detalhes que geraram a falha em `View Logs`.**11.** Caso o teste seja bem sucedido, a nova API será adicionada automaticamente a tabela de recursos do `Authorisation Server`**12.** A coluna referente a `API CERTIFICATION URL`**também será preenchida automaticamente e apresentada na tabela.**13.** Caso seja necessário atualizar a URL do recurso adicionado basta clicar no botão editar ou em apagar.
## Etapa-3:-Removendo-um-Recurso-de-uma-API Etapa 3: Removendo um Recurso de uma API

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Servidores de Autorização`. Na tela ao lado, selecione o servidor de autorização no qual o recurso será removido.**3.** De volta ao menu, selecione a opção `Recursos do API`, e na tela ao lado, localize o `Tipo da Família da API (API Family Type)` que será removido.**4.** Clique no ícone `Excluir` para remover a família de recursos e suas APIs.**NOTA:** Para remover pontualmente um recurso dentro de um `Tipo da Família da API (API Family Type)` existente, siga os passos descritos nesta etapa.

---

# 10. Criando um Software Statements

---
id: 134283423
title: 10. Criando um Software Statements
version: 3
modified: 2025-05-03T04:20:38.051Z
url: /spaces/OF/pages/134283423/10.+Criando+um+Software+Statements
---

Aqui apresentamos a configuração necessária para criar uma nova declaração de software no Diretório. 
## Etapa-1:-Criando-uma-Nova-Declaração-de-Software Etapa 1: Criando uma Nova Declaração de Software

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Software Statements`**e clique no botão `New Software Statement`.**3.** Na janela `New Software Statement`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.
## 10.Detalhamento-dos-Campos Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Version*` | A versão do software deve ser definida para um valor numérico, um número inteiro (por exemplo, 1) ou um número de ponto flutuante (1,2, 2,2, 3,2 etc.). | 1 |
| `Client Name*` | Para registro de software da instituição receptora (software statement), no campo Client Name, recomenda-se usar o nome da Marca, de conhecimento do cliente. Se o nome da marca foi declarado Authorisation Server, por exemplo, pode-se usar o nome da marca que foi utilizado no cadastro (customer friendly server name). Este é o nome que a transmissora irá receber e declarar ao cliente durante a jornada. | Wizcredi |
| `Client URL*` | O site ou URL raiz do recurso, podendo ser o site institucional da organização. | https://www.wizcredi.com.br/info.html |
| `Policy URL` | Deve ser definido como uma sequência de texto que representa uma URL única de política. | https://www.wizcredi.com.br/policy.html |
| `Logo URL*` | Deve ser definida a URL para o logotipo da marca. Para obter mais detalhes sobre formato, dimensão e peso máximo do arquivo consulte o Guia de Experiencia Fase 2. | https://www.wizcredi.com.br/logo.svg |
| `Redirect URL*` | Os URLs de redirecionamento devem ser definidos como uma string de texto que representa uma URL único de redirecionamento. | https://www.wizcredi.com.br/cb 1 https://www.wizcredi.com.br/cb2 |
| `Terms of Service URL` | Deve ser definido como uma string de texto que representa uma URL única dos Termos de Serviço. | https://www.wizcredi.com.br/tos.html |
| `Description` | Deve ser definido como uma string de texto de sua escolha. | Aplicativo Wizcredi para o segmento de varejo |
| `On Behalf` `Of` | O campo “Em nome de” é classificado como opcional para implementação. | <Não se aplica para o contexto do Open Finance Brasil> |
| `API Webhook URL` | Deve ser definida uma URL* para notificação da API de Iniciação de Pagamentos * A implementação do webhook é opcional para instituições iniciadoras de pagamento | https://example.com/brandname |
| `software_origin_uris` | Origens que podem iniciar um registro ou autorização através do protocolo FIDO | |
*Campo obrigatório**NOTA:** O campo Logo URL é o que a transmissora deverá utilizar para apresentar a logomarca da receptora.
## Etapa-2:-Cadastrando-Certificação-de-Declaração-de-Software Etapa 2: Cadastrando Certificação de Declaração de Software

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.**Selecione o menu `Software Statements`.  Depois selecione a declaração de software que deseja. Após selecionar, vá no submenu à esquerda em cima e clique em `Certifications`.**3.** Dentro dessa área, para cadastrar uma nova certificação, clique no botão `Add New Certification`**localizado no lado direito da tela.**4.** Na janela `New certification`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.As informações da certificação do Software Statement são referentes a certificação FAPI obtida através da [OpenID Foundation](https://openid.net/certification/). Dentro do site é possível encontrar uma tabela **Brazil Open Finance (Based on FAPI Relying Parties)**que contém as informações que devem ser refletidas no formulário para adição da certificação de segurança.
## Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Certification type*` | O tipo de certificação que foi efetuada com a OpenID Foundation – Deve ser adicionado ao menos uma certificação Redirect (FAPI e DCR) | Redirect DCR CIBA – certificação ainda não disponível |
| `Certification type variant*` | As variantes dependem do tipo de certificação escolhida. Dentro da tabela da OpenID Foundation, cada coluna representam as possíveis variações nas certificações. Vale notar que JARM não é requisitado segundo a especificação de segurança logo não está presente como uma opção a ser adicionada Para a certificação DCR a instiuiçao deve avaliar se certificou utilizadondo APIs de Dados do consumidor – Unsigned , ou de Pagamentos - Signed | Se escolheu Redirect: FAPI Adv. OP w/ MTLS FAPI Adv. OP w/ MTLS, PAR FAPI Adv. OP w/ Private Key FAPI Adv. OP w/ Private Key, PAR Se escolheu DCR: DCR Signed payload – JWT DCR Unsigned payload - JSON |
| `Profile version*` | A versão da certificação selecionado – Campo livre, apenas para controle da própria instituição | 1 |
| `Certification payload*` | O URL que aponta para o arquivo hospedado pela OpenID Foundation com o pacote de certificação. Formato zip. | https://openid.net/wordpress-content/uploads/2021/08/BR-OB_Adv._OP_MTLS-exemplo.zip |
| `Start date of certification*` | A data de certificação inicial – é a mesma data que consta na tabela da OpenID Foundation. Formato dd/mm/yyyy | 09/05/2022 |
*Campo obrigatório

---

# 11. Criando uma nova reivindicação de autoridade de software

---
id: 133792088
title: 11. Criando uma nova reivindicação de autoridade de software
version: 2
modified: 2025-05-03T04:20:38.058Z
url: /spaces/OF/pages/133792088/11.+Criando+uma+nova+reivindica+o+de+autoridade+de+software
---

Esta seção explica as etapas para criar uma reivindicação de autoridade de software. Esta etapa será necessária para definir as funções regulatórias que serão inseridas no *Software Statement Assertion*.
## Etapa 1: Criando Reivindicação de Autoridade de Software

### Requisitos
**1.** Necessário realizar a seção Cadastrando reivindicações de domínio de autoridade.**2.** Necessário realizar a seção Cadastrando reivindicações de autoridade.**3.** Necessário ter criado uma Criando um Software Statements para sua organização.**4.**No Diretório, selecione a sua organização e no menu lateral clique em `Software Statements` .**5.** Selecione o menu lateral  a opção `Authority Claims`.**NOTA:** Para mais detalhes consulte a seção [Funções regulatórias para mapeamentos OpenID e OAuth 2.0](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID1-ptbr.html) no documento de especificação para implementadores do [Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 1](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID1-ptbr.html).**6.** Na janela `Software Statements Details`*,* role a página para baixo, selecione o menu `Authority Claims` e clique no botão `New Software Authority Claims`.**7.** Na janela `New Software Authority Claims`**preencha os campos do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.
## Detalhamento dos Campos

| Nome do campo | Descrição | Exemplo |
| `Authorisation Domain Name` | É apresentado o domínio de autorização para o qual esta a reivindicação de domínio está mapeada. | Open Finance Brasil |
| `Role` | É apresentada a função mapeada para o domínio de autorização. | DADOS |
*Campo obrigatório

---

# 12. Criando certificados de transporte e assinatura em Sandbox

---
id: 133792152
title: 12. Criando certificados de transporte e assinatura em Sandbox
version: 3
modified: 2025-05-03T04:20:37.890Z
url: /spaces/OF/pages/133792152/12.+Criando+certificados+de+transporte+e+assinatura+em+Sandbox
---

Esta seção explica as etapas para criar uma solicitação de assinatura de certificado para certificados de transporte e assinatura que não foram emitidos por uma autoridade de certificação e para uso exclusivo em ambiente de Sandbox do Diretório.
## Etapa 1: Criando um Novo Certificado de Transporte

### Requisitos
**1.** Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, selecione a sua organização e no menu lateral clique em `Software Statements`**3.** No menu superior clique em `Software Statements Certificates` e clique no botão `New Certificate`.**4.** Na janela `New Certificate`, na caixa de seleção `Select Certificate Type` selecione a opção `BRCAC_2022`**e clique no botão**`Continue`*.***5.** No passo seguinte, é possível gerar automaticamente o CSR referente ao certificado via diretório. Para isso clique no botão Automatic config generation.**6.** Na janela `Generate certificate - BRCAC_2022`, edite as informações de forma que elas sejam idênticas as informações contidas no Diretório na página de detalhes da organização, conforme especificado no [Padrão de Certificados](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82313425) e clique no botão `Next`.**7.**Clique no botão `Download` para baixar o arquivo `brcac.cnf` com as informações do certificado**8.**Copie o comando que aparece na tela e execute através do prompt de comando no caminho do arquivo `brcac.cnf`. para a geração do par `CSR` e `KEY`. Clique no botão `Continue`**9.**Selecione a opção `Upload CSR/PEM` e localize o `brcac.csr` gerado pela execução do passo anterior e clique no botão `Continue`.**10.**Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**11.**Na tela anterior de certificates, vá até actions e clique na seta de download. Salve o `<arquivo>.pem` em uma pasta local. 
## Etapa-2:-Criando-um-Novo-Certificado-de-Assinatura Etapa 2: Criando um Novo Certificado de Assinatura

### Requisitos
**1.** No Diretório, selecione a sua organização e no menu lateral clique em `Organisation Certificates`.**2.** Na janela `New Certificate`*,*na caixa de seleção `Select Certificate Type` selecione a opção `BRSEAL`**e clique no botão**`Continue`*.***3.** No passo seguinte, é possível gerar automaticamente o CSR referente ao certificado via diretório. Para isso clique no botão `Automatic config generation`.**4.** Na janela `Generate certificate - BRSEAL`, edite as informações de forma que elas sejam idênticas as informações contidas no Diretório na página de detalhes da organização, conforme especificado no Padrão de Certificados e clique no botão `Next`.**5.** Clique no botão `Download` para baixar o arquivo brseal.cnf com as informações do certificado**6.** Copie o comando que aparece na tela e execute através do prompt de comando no caminho do arquivo `brseal.cnf`. para a geração do par `CSR e KEY`. Clique no botão `Continue`**7.** Selecione a opção `Upload CSR/PEM` e localize o `brseal.cnf` gerado pela execução do passo anterior e clique no botão `Continue`.**8.** Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**9.** Na tela anterior de certificates, vá até `actions` e clique na seta de `download`. Salve o `<arquivo>.pem` em uma pasta local.

---

# 13. Carregando certificados emitidos por autoridade de certificação em Produção

---
id: 133792231
title: 13. Carregando certificados emitidos por autoridade de certificação em Produção
version: 2
modified: 2025-05-03T04:20:37.996Z
url: /spaces/OF/pages/133792231/13.+Carregando+certificados+emitidos+por+autoridade+de+certifica+o+em+Produ+o
---

Esta seção explica as etapas para importar certificados que foram emitidos por uma autoridade de certificação e para uso exclusivo em ambiente de Produção do Diretório.
## Requisitos
Apos a emissão de um Certificado de transporte ou assinatura junto a alguma AC credenciada pelo ICP Brasil será necessário inseri-lo no Diretório de participantes ao nível da organização, para BRSEALs, ou ao nível do Software Statements, para BRCACs. A adição de certificados no diretório deve ser feita sempre com a opção EXTERNAL BRCAC ou EXTERNAL BRSEAL, já que os certificados são gerados pela cadeia do ICP Brasil, externa ao PKI diretório.Ao adicionar o certificado no diretório duas validações serão feitas.O diretório irá validar que o certificado foi assinado por uma das ACs credenciadas ao Open Finance Brasil, cuja lista [completa pode ser encontrada na documentação de segurança.](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1-ptbr.html) – É possível executar essa consulta avaliando se o issuer do certificado está na lista citada, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl - openssl x509 -in brcac.pem -noout -issuerO diretório irá validar que o certificado possui UID em seu subject igual ao UID so Software Statement no caso do BRCAC, ou igual ao Organisation ID no caso do BRSEAL – É possível executar essa consulta avaliando se o UID do subject é igual ao UID apresentado no diretório, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl x509 -in brcac.pem -noout -subject
## Etapa 1: Carregando Certificado de Transporte

### Requisitos
**1.**Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, selecione a sua organização e Selecione o menu `Software Statements` .**3.** Na tela Software Statement , clique no botão `New Certificate`.**4.** Na janela `New Certificate`, na caixa de seleção `Select Certificate Type` selecione a opção `EXTERNAL BRCAC`**e clique no botão**`Continue`*.***5.** No passo seguinte, em `Generate CSR`*,* clique no botão `Continue`.**6.** Na opção `Upload CSR/PEM`, localize o arquivo em formato `.cer` ou `.pem` do certificado gerado junto a AC. **Para essa etapa garanta que nenhuma chave privada, arquivo em formato**`.key`**, será adicionada sob risco de exposição de credenciais.****7.** Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**8.** Uma nova entrada será fornecida na tela de certificados. Certifique que o novo certificado se encontra adicionado.
## Etapa-2:-Carregando-Certificado-de-Assinatura Etapa 2: Carregando Certificado de Assinatura

### Requisitos
**1.**No Diretório, selecione a sua organização e no menu lateral clique em `Organisations Certificate`*.***2.**Na janela `New Organisations Certificate`, na caixa de seleção `Select Certificate Type` selecione a opção `BRSEAL EXTERNAL`**e clique no botão**`Continue`*.***3.** No passo seguinte, em `Generate CSR`*,* clique no botão `Continue`.**4.** Na opção `Upload CSR/PEM`, localize o `<arquivo>.csr` e clique no botão `Continue`.**5.** Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**6.** Na tela anterior em `Organisation Certificates`, vá até `actions` e clique na seta de `download`. Salve o `<arquivo>.pem` em uma pasta local.

---

# 14. Cadastrando administradores da organização

---
id: 133759355
title: 14. Cadastrando administradores da organização
version: 1
modified: 2025-05-03T04:20:37.947Z
url: /spaces/OF/pages/133759355/14.+Cadastrando+administradores+da+organiza+o
---

Esta seção explica as etapas necessárias para realizar o cadastro de um novo administrador da organização.
## Etapa 1: Cadastrando um Administrador da Organização

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Organisation Administrator`**e clique no botão `New Organisation Administrators`.**3.** Na janela `New Organisation Administrator`**preencha o campo do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**4.** Clique no botão `Save`.**NOTA:**Somente administradores da organização podem cadastrar novos administradores.

---

# 15. Obtendo um Software Statements Assertion

---
id: 134283488
title: 15. Obtendo um Software Statements Assertion
version: 2
modified: 2025-05-03T04:20:38.088Z
url: /spaces/OF/pages/134283488/15.+Obtendo+um+Software+Statements+Assertion
---

Uma Software Statements Assertion (SSA) é um JWT assinado do diretório que contém todas as informações sobre um aplicativo que existe em um determinado momento no diretório. Inclui a localização de todas as chaves públicas vinculadas a esta declaração de software e todos os outros metadados de que um banco precisa para validar a legitimidade do aplicativo.
## Etapa 1: Criando uma Nova Declaração de Software Assinada

### Requisitos
**1.** Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, localize e selecione a sua organização.**3.** Vá até o menu `Software Statement`, acesse o artefato criado anteriormente clicando no link `CLIENT NAME`*.***4.** Na janela `Software Statement Details`*,*role a página para baixo e**selecione o menu `Software Statements Assertion`.**5.** Clique no botão `Copy to Clipboard`**para copiar o SSA gerado pelo Diretório.

---

# 16. Configurando eventos de notificação no Diretório

---
id: 134316072
title: 16. Configurando eventos de notificação no Diretório
version: 2
modified: 2025-05-03T04:20:37.870Z
url: /spaces/OF/pages/134316072/16.+Configurando+eventos+de+notifica+o+no+Diret+rio
---

Aqui apresentamos a configuração de *webhook* no Diretório
## Introdução Webhooks
Habilite notificações em tempo real e orientadas por eventos**para manter sua organização alerta sobre todas as mudanças no ecossistema. Permaneça sincronizado e informado sobre atualizações**importantes, tais como mudanças para as organizações, APIs, certificados e *roles*sem a necessidade de constantemente buscar informações.*Webhooks* provêm às organizações atualizações em tempo real sobre mudanças no ecossistema, garantindo que elas estejam informadas e atentas.Através da automação de notificações, *webhooks* eliminam a necessidade de monitoramento manual, melhorando eficiência operacional significativamente. Adicionalmente, elas oferecem flexibilidade na integração, permitindo que organizações adaptem seus sistemas de maneira dinâmica às atualizações do ecossistema e mantendo interação transparente com outros participantes.Você pode inscrever uma aplicação ou um *authorization server*para notificações na Raidiam.Para aprender como fazer a inscrição para eventos no seu ecossistema, veja o trecho de **Inscrição para eventos**mais****abaixo.**Lista de Eventos que Iniciam um Webhook**Determinadas ações podem resultar em múltiplas notificações sendo enviadas pelo *webhook*.Por exemplo, suspender uma aplicação não suspende apenas a aplicação, como também desabilita qualquer certificado ou token de acesso para isso. Consequentemente, notificações separadas são enviadas para cada um desses eventos, com detalhes sobre a desabilitação de cada certificado e token de acesso individualmente.**Criação, atualização ou exclusão**·      **Organizações:**Notificações são acionadas quando uma organização é criada, atualizada ou deletada do diretório. Isso garante que qualquer mudança em detalhes da organização, como nomes, informação de contatos ou status, são imediatamente notificados à sistemas relevantes.·       ***Authorization Server*****:**Mudanças nas configurações de *Authorization Server* de uma organização – tais como adicionar ou remover uma instância – são comunicadas pelos *webhooks*.·       **Reivindicações de domínio de autoridade:**Notificações são enviadas quando as reivindicações de domínio de uma organização são alteradas.·       **Reinvidicação de papel de domínio de autoridade da organização:**Quando uma organização requere ou atualiza sua autorização papel dentro de um domínio, *webhooks*notificam às partes interessadas.·       **Certificado de*****Authorization Server*****:***Webhooks*são acionados quando o servidor do *Authorization Server* de uma organização perde ou ganha um certificado. Esses certificados averiguam conformidade com os padrões do ecossistema.·       **API Recursos:**Mudanças na API recursos, tais como *endpoints*, versionamentos ou operações com suporte, acionarão notificações.·       ***Endpoint*****da API Comum (*****Discovery*****):***Webhooks* notificam mudanças relativas a *endpoints* usados na API Comum (*Discovery*).·       **Contatos:**Notificações são enviadas quando os detalhes no contato da organização, tais como contatos administrativos ou técnicos, são adicionados, atualizados ou removidos.**Criação ou atualização**·       **Reivindicação de autoridade de software:**Webhooks notificam quando uma reivindicação de autoridade de software é criada ou atualizada.**Criação ou exclusão**·       **Autorização por papel de domínio:**Notificação são acionadas quando uma autorização por papel dentro de um domínio é tanto concedida quanto revogada por uma autorização.**Criação ou revogação**·       **Certificado de Software Statement/Aplicação ou Organização :**Webhooks notificação o erro em *issue*ou revogação de certificados digitais para organizações ou seus *softwares*. Esses certificados são cruciais para assegurar comunicações e autenticações dentro do ecossistema.**Criação, atualização, deleção, suspensão, reativação/fim da suspensão , bloqueio e desbloqueio**·       **Aplicação (Software Statement):**Um amplo grupo eventos em webhook são acionados para *software* *statements*. Isso inclui criação, atualização, deleção, suspensão, reativação, bloqueio ou desbloqueio.**Outro**
- Termos e condições da organização : Webhooks são acionados quando o processo de assinatura de termos e condições se inicia. Notificações também são enviadas se houverem mudanças no status do processo, tais como aprovação, rejeição ou cancelamento.
**Payload de Notifiçações**Os *payloads* de *webhooks* são construídos sendo guiados por uma estrutura de “geral-para-específico”. Para cada evento iniciado, a estrutura inteira do recurso alterado é detalhada dentro do *payload* da resposta.Esse desenho permite que a cadeia de contexto seja inclusa no *payload*, permitindo facilidade para interpretação e ação nas notificações.O evento *payload* sempre consiste em quatro campos:·       ApiResource – o identificador do recurso para cada evento ocorrido.·       UpdateTimestamp – o tempo de cada evento.·       ResourcePayload – o payload (detalhes) do recurso para qual o evento ocorreu.·        Revision – um mecanismo de versionamento que acompanha mudanças ou atualizações para o recurso que está sendo notificado.Para os exemplos mais atualizados de recursos de *payload*, consulte sempre a [documentação da API Raidiam](https://api.connect.raidiam.io/) e o esquema para o recurso específico.**Inscrição em eventos**Inscrever uma *Authorization Server*ou API para eventos acontecendo dentro do ecossistema ou federação inteira.**Inscrevendo*****Authorization Server*****em eventos**
1. Acesse a sua organização.

1. Selecione Servers e selecione um servidor de sua escolha.

1. Selecione Edit Server.

1. Inclua no campo Notification Webhook Endpoint o URL para qual a Raidiam enviará as notificações.

1. Salve.
**Inscrevendo aplicações em eventos**
1. Acesse a sua organização.

1. Selecione Applications e selecione um servidor de sua escolha.

1. Selecione Edit Application.

1. Inclua no campo Notification Webhook Endpoint o URL para qual a Raidiam enviará as notificações.

1. Salve.

## Etapa 1: Inscrever-se em um Tópico

### Requisitos
**1.** Em seu navegador, navegue até [webhook.site](https://webhook.site/) e uma URL única e aleatória será gerada automaticamente. Ela poderá ser utilizada para testar e depurar Webhooks e solicitações HTTP.**2.** Selecione a URL e copie.
## Etapa-2:-Solicitando-uma-Subscrição Etapa 2: Solicitando uma Subscrição

### Requisitos
**1.** No Diretório, selecione a sua organização e vá até a página detalhes da organização.**2.** Selecione o menu `Authorisation Servers`**e em *actions* clique no ícone editar.**3.**Na página `Authorisation Server Information` cole a URL obtida na Etapa 1 no campo `Notification Webhook Endpoint`*.*
## Etapa-3:-Confirmando-uma-Subscrição Etapa 3: Confirmando uma Subscrição

### Requisitos
**1.**De volta ao webhook.site, role para baixo e no campo de texto**`Raw Context`**selecione e copie a URL em `SubscribeURL`**para se subscrever no tópico.**2.** Em uma nova aba do navegador, cole a URL obtida no passo anterior.**3.** Pronto! A partir daqui, toda e qualquer modificação que ocorra no Diretório será notificada através de eventos.
## Etapa-4:-Analisando-um-Evento-de-Notificação Etapa 4: Analisando um Evento de Notificação

### Requisitos
**1.** No Diretório, selecione a sua organização e vá até a página detalhes da organização.**2.** Selecione o menu `Software Statement `e em *actions* clique no ícone editar.**3.** Na janela `Software Statement Details` vá até o campo `description` e digite qualquer valor e clique no botão `Salvar`.**4.**Neste momento, o Diretório irá enviar uma notificação `push`.**5.** De volta ao webhook.site, clique no primeiro evento que surge na lista a esquerda da tela.**6.** Role a tela para baixo e no campo de texto**`Raw Context`**localize o novo valor adicionado no atributo `description`.

---

# 17. Obtendo um token de acesso para as APIs do Diretório

---
id: 133759390
title: 17. Obtendo um token de acesso para as APIs do Diretório
version: 2
modified: 2025-05-03T04:20:37.880Z
url: /spaces/OF/pages/133759390/17.+Obtendo+um+token+de+acesso+para+as+APIs+do+Diret+rio
---

Para acessar as APIs do Diretório do Open Finance, você precisará de um token de acesso. Esta seção descreve as etapas necessárias para adquirir tokens de acesso.
## Etapa-1:-Localizando-o-Identificador-do-Cliente Etapa 1: Localizando o Identificador do Cliente

### Requisitos
**1.** Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, localize e selecione a sua organização.**3.** Vá até o menu `Software Statement`, acesse o artefato criado anteriormente clicando no símbolo do lápis*.***4.** Na janela `Software Statement Details` localize o campo `CLIENT ID`, selecione e copie o valor.
## Etapa-2:-Localizando-a-URL-de-Token-no-Diretório Etapa 2: Localizando a URL de Token no Diretório

### Requisitos
**1.**No navegador, acesse a URL de descoberta de conexão OpenID de acordo com o ambiente utilizado:
- `Sandbox:` https://auth.sandbox.directory.openbankingbrasil.org.br/.well-known/openid-configuration
- `Produção:` https://auth.directory.openbankingbrasil.org.br/.well-known/openid-configuration
**2.** Localize o endpoint de token que será utilizado para trocar as credenciais de autenticação para tokens de acesso.
## Etapa-3:-Adicionando-Certificados-SSL-por-Domínio Etapa 3: Adicionando Certificados SSL por Domínio

### Requisitos
**1.** Necessário ter criado uma Criando uma solicitação de Assinatura de Certificado (CSR).**2.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, no Postman, selecione o menu `File` e em seguida o menu `Settings`*.***3.** Na janela `Settings`, selecione o menu `Certificates` e clique no link `Add Certificate`*.***4.** Na aba *Certificates*, no campo *Host* insira um dos valores descritos a seguir de acordo com o ambiente utilizado:
- `Sandbox:` matls-auth.sandbox.directory.openbankingbrasil.org.br
- `Produção:` matls-auth.directory.openbankingbrasil.org.br
**5.** Em `CRT file`, clique no botão `Select file`*,*e localize o `<arquivo>.pem` obtido na seção Criando uma solicitação de Assinatura de Certificado (CSR).**6.** No passo seguinte, clique no botão `KEY File` e localize o `<arquivo>.key` criado no processo de geração de chaves na seção Criando uma solicitação de Assinatura de Certificado (CSR).**7.** Clique no botão `Add`*.*
## Etapa-4:-Obtendo-um-Token-de-Acesso Etapa 4: Obtendo um Token de Acesso

### Requisitos
**1.** Para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **2.** No campo `Enter request URL`, digite o valor obtido da URL de token mencionado na [etapa 2](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/85753877#Etapa-2:-Localizando-a-URL-de-Token-no-Diretório).**3.** Defina o tipo da operação para `POST`.**4.** Vá para a guia `Body` e selecione o botão de opção `'x-www-form-urlencoded'`.**5.** Insira os parâmetros como descritos a seguir:client_id = <valor obtido no CLIENT ID na [etapa 1](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/85753877#Etapa-1:-Localizando-o-Identificador-do-Cliente)>
grant_type = client_credentials
scope = directory:software**6.** Uma vez que todos os parâmetros e valores estejam preenchidos, clique no botão `Send`*.***7.** Selecione e copie o valor retornado no atributo `access_token`*.*

---

# 18. Listando as organizações cadastradas no Diretório via API

---
id: 133792318
title: 18. Listando as organizações cadastradas no Diretório via API
version: 3
modified: 2025-05-03T04:20:38.008Z
url: /spaces/OF/pages/133792318/18.+Listando+as+organiza+es+cadastradas+no+Diret+rio+via+API
---

Para acessar a API Organisations no Diretório, você precisará de um token de acesso. Esta seção descreve as etapas necessárias para listar e visualizar os detalhes das organizações cadastradas no Diretório.
## Etapa 1: Obtendo Detalhes das Organizações

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.**Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`.**3.** No campo *Enter request URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations)`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations](https://matls-auth.directory.openbankingbrasil.org.br/organisations)**4.** Defina o tipo da operação para `GET`.**5.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**6.**Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**7.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.**NOTA:** Para localizar uma organização mãe que pertença a um conglomerado, você poderá percorrer na lista de resposta de dados JSON do servidor, capturando o identificador no atributo `ParentOrganisationReference` das organizações filhas e localizar o mesmo ID na organização cujo o atributo `RegistrationId` contenha este mesmo valor.

---

# 19. Listando os servidores de autorização de uma organização via API

---
id: 134283519
title: 19. Listando os servidores de autorização de uma organização via API
version: 2
modified: 2025-05-03T04:20:38.066Z
url: /spaces/OF/pages/134283519/19.+Listando+os+servidores+de+autoriza+o+de+uma+organiza+o+via+API
---

Aqui apresentamos os passos para listar os servidores de autorização de uma organização.
## Etapa 1: Listando os Servidores de Autorização

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.** Necessário ter realizado os passos da sessão Listando as organizações cadastradas no Diretório via API.**3.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **4.** No campo *Enter request URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/authorisationservers`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/authorisationservers**5.** Defina o tipo da operação para `GET`.**6.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**7.** Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**8.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.**NOTA:**Na resposta de dados JSON do servidor o atributo `CustomerFriendlyName` contém o valor da marca e o `CustomerFriendlyLogoUri` o logotipo vinculado a marca.`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/authorisationservers**9.** Defina o tipo da operação para GET.**10.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**11.** Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**12.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.**NOTA:** Na resposta de dados JSON do servidor o atributo `CustomerFriendlyName` contém o valor da marca e o `CustomerFriendlyLogoUri` o logotipo vinculado a marca.

---

# 20. Obtendo um Software Statement via API

---
id: 133759469
title: 20. Obtendo um Software Statement via API
version: 2
modified: 2025-05-03T04:20:37.952Z
url: /spaces/OF/pages/133759469/20.+Obtendo+um+Software+Statement+via+API
---

Aqui apresentamos os passos para obter um Software Statement (SS) no Diretório via API.
## Etapa 1: Obtendo um SS no Diretório via API

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.** Necessário ter realizado os passos da sessão Listando as organizações cadastradas no Diretório via API.**3.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **4.** No campo *Enter request URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements**5.** Defina o tipo da operação para GET.**6.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**7.** Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**8.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.

---

# 21. Obtendo um Software Statement Assertion via API

---
id: 133759514
title: 21. Obtendo um Software Statement Assertion via API
version: 2
modified: 2025-05-03T04:20:37.957Z
url: /spaces/OF/pages/133759514/21.+Obtendo+um+Software+Statement+Assertion+via+API
---

qui apresentamos os passos para obter um Software Statement Assertion (SSA) no Diretório via API.
## Etapa 1: Obtendo um SSA do Diretório via API

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.** Necessário ter realizado os passos da sessão Listando as organizações cadastradas no Diretório via API.**3.** Necessário ter realizado os passos da sessão Obtendo um Software Statement via API.**4.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **5.** No campo `Enter request`*URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements/<software_id>/assertion`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements/<software_id>/assertion**6.** Defina o tipo da operação para `GET`.**7.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**8.** Na coluna ao lado, no campo *Token* cole o `access_token`**obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**9.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.

---

# 22. Como se inscrever nas atualizações de lançamento do Diretório

---
id: 134316138
title: 22. Como se inscrever nas atualizações de lançamento do Diretório
version: 1
modified: 2025-05-03T04:20:38.082Z
url: /spaces/OF/pages/134316138/22.+Como+se+inscrever+nas+atualiza+es+de+lan+amento+do+Diret+rio
---

Constantemente são realizados aprimoramentos e atualizações no Diretório e estas mudanças são registradas em uma página Web onde reside todo o conteúdo do *Release Notes*. Esta seção descreve as etapas necessárias de inscrição para o recebimento de notificação do release notes do Diretório quando publicado.
## Etapa 1: Cadastrando o Recebimento de Release Notes

### Requisitos
**1.**Em seu navegador, navegue até site de [monitoramento de disponibilidade do Diretório](https://status.directory.openbankingbrasil.org.br/).**2.** Clique em `Subscrever atualizações`.**3.** Na tela seguinte, adicione seu e-mail e clique no botão `Subscrever`. O Diretório irá enviar uma mensagem de confirmação, que será encaminhada ao endereço de e-mail informado.**4.** No e-mail recebido, clique no botão `Sim, subscreve-me`.**5.** Em uma página da Web será apresentada a mensagem que seu e-mail encontra-se agora subscrito para atualizações de estado Open Finance Brasil.**NOTA:**Caso você não tenha recebido o e-mail de confirmação, verifique sua caixa de *SPAM* e as politicas de bloqueio de mensagens. O envio das mensagens poderá sofrer algum atraso, contudo, se o problema persistir, clique no botão `Subscrever Alterações` para reenvio das mensagens.
## Etapa-2:-Acessando-o-Release-Notes Etapa 2: Acessando o Release Notes

### Requisitos
**1.**No navegador, digite a URL de acordo com o ambiente a ser acessado:`Sandbox:` [https://data.sandbox.directory.openbankingbrasil.org.br/release-notes](https://data.sandbox.directory.openbankingbrasil.org.br/release-notes) `Produção:`**[https://data.directory.openbankingbrasil.org.br/release-notes](https://data.directory.openbankingbrasil.org.br/release-notes)

---

# 23. Como obter suporte ao Diretório

---
id: 134283579
title: 23. Como obter suporte ao Diretório
version: 1
modified: 2025-05-03T04:20:38.074Z
url: /spaces/OF/pages/134283579/23.+Como+obter+suporte+ao+Diret+rio
---

Aqui apresentamos as formas de contato para suporte ao Diretório Central.
## Service Desk
Todas as consultas, problemas ou solicitações de suporte precisam ser roteados por meio do Service Desk.O Service Desk do Open Finance Brasil pode ser acessado pelo endereço: [https://servicedesk.openbankingbrasil.org.br/](https://servicedesk.openbankingbrasil.org.br/)É possível abrir chamados de Solicitação de Informações, Melhorias e incidentes de indisponibilidade ou problemas de performance.

---

# 24. Ciclo de Vida de Authorization Server

---
id: 320208897
title: 24. Ciclo de Vida de Authorization Server
version: 3
modified: 2025-05-03T04:20:37.917Z
url: /spaces/OF/pages/320208897/24.+Ciclo+de+Vida+de+Authorization+Server
---

### Matriz de orientações em caso de alterações dos Authorization Servers
Esta planilha é um material de trabalho elaborado com contribuições dos GTs Arquitetura, PRC e Infraestrutura, com suporte do Secretariado do Open Finance e contribuições de técnicos do Banco Central
| | | VISÃO DE NEGÓCIO | VISÃO TÉCNICA | |
| # | Cenário | Cliente | Transmissor | Recebedor | Transmissor | Recebedor | Considerações finais |
| 1 | Transmissor encerra uma marca (usuário final ainda pode acessar histórico através de autoatendimento pela internet). | Não é necessário ação do cliente. | O compartilhamento de dados será mantido enquanto existir canal para gestão daquele produto. | Receberá os dados referente aos 12 meses anteriores previstos na regulação. Após esse período, não receberá mais dados | O transmissor deve continuar enviando as informações ao longo de 12 meses, e após esse período alterar o status do recurso para 'UNAVAIABLE' e encerrar o envio de informações | Pode consultar o status do recurso na API Resources referente aos 12 meses anteriores previstos na regulação | N/A |
| 2 | Transmissor encerra uma marca (usuário final ainda pode acessar histórico através da internet) e migra os clientes e os recursos para outra marca dentro da mesma instituição (mesmo CNPJ). | N/A | Consentimentos autorizados devem continuar vigentes. | Não é necessário ação do recebedor. Passará a receber dados da nova marca. | A informação deve ser disponibilizada enquanto estiver disponível no canal e dentro do prazo de compartilhamento | Os produtos a serem compartilhados serão ajustados a medida em que sua visualização for extinta do respectivo canal | N/A |
| 3 | Transmissor encerra uma marca (usuário final ainda pode acessar histórico através de autoatendimento pela internet) e migra os clientes e os recursos para outra marca dentro do mesmo conglomerado (CNPJs distintos). | N/A | Consentimentos autorizados podem continuar vigentes. | Não é necessário ação do recebedor. Se houver a migração, a instituição receptora passará a receber dados da nova instituição. Caso contrário, os consentimentos serão revogados e a instituição receptora não receberá mais os dados. | A solicitação deve ser encaminhada ao Banco Central, preferencialmente, antes do fato gerador ou, na inviabilidade, em no máximo 10 dias corridos. | A solicitação deve ser encaminhada ao Banco Central, preferencialmente, antes do fato gerador ou, na inviabilidade, em no máximo 10 dias corridos. | A migração de AS com mudança da instituição transmissora de dados, no atual patamar do Open Finance, não é recomendável. Assim, em cenários que envolvem essa migração, os consentimentos podem ser revogados. No entanto, nesse cenário específico, como estamos falando de mudanças dentro do mesmo conglomerado, cabe uma análise caso a caso. O caso deve ser descrito e solicitada autorização da Supervisão. A solicitação deve ser encaminhada para DESUP/DESUC/DENOR, preferencialmente, antes do fato gerador ou, na inviabilidade, em no máximo 10 dias corridos. Não se aplica ao cenário de cooperativas. |
| 4 | Transmissor encerra uma marca (usuário final não tem como acessar histórico através de autoatendimento pela internet – Portal não existe mais). | Não é necessário ação do cliente. | N/A | Não é necessário ação do recebedor. Não receberá mais dados dessa marca. | O consentimento deixa de existir. | Não há consulta pois não há mais API para consumo de dados. | N/A |
| 5 | Transmissor encerra um produto de uma marca. | Não é necessário ação do cliente. | Os consentimentos devem continuar vigentes. Apenas no caso de consentimentos restritos ao produto encerrado, eles poderiam ser revogados pelo transmissor após o fim do período de 12 meses | Não é necessário ação do recebedor. Não receberá mais dados desse produto. | API recurso muda para UNAVAILABLE após fim do período de 12 meses. API produto deixa de apresentar os dados. | Deve consultar o status do recurso na API Resources. | N/A |
| 6 | Marca de transmissor é adquirida por outra instituição e é mantida ativa. | Não é necessário ação do cliente. | N/A | Não é necessário ação do recebedor. | AS de origem fica em convivência pelo menos até expiração de todos os consentimentos ativos. Os consentimentos devem ser migrados se houver anuência explícita do cliente. Caso contrário, devem ser revogados. | Não é necessário ação do recebedor. | A migração de AS com mudança da instituição transmissora de dados, no atual patamar do Open Finance, não é recomendável. Assim, em cenários que envolvem essa migração, os consentimentos podem ser revogados. |
| 7 | Transmissor é absorvido por outra instituição (incorporação). | Não é necessário ação do cliente. | Existem dois cenários possíveis: manutenção ou revogação dos consentimentos. O Banco Central avaliará cada caso. | Não é necessário ação do recebedor. | Caso a marca seja substituída deverá considerar os campos: DeprecatedDate; RetirementDate; SupersededByAuthorizationIServerID; Status. Caso a marca anterior seja descontinuada deverá optar entre revogar e solicitar aos clientes que façam novo consentimento ou migrar os consentimentos atuais para o novo modelo, mantendo os mesmos IDs utilizados para servidores, clientes, serviços, consentimentos e infraestrutura previamente utilizados. | Não é necessário ação do recebedor. | A migração de AS com mudança da instituição transmissora de dados, no atual patamar do Open Finance, não é recomendável. Assim, em cenários que envolvem essa migração, os consentimentos podem ser revogados. Solicitação deve ser encaminhada para DESUP/DESUC/DENOR |
| 8 | É feita a migração do AS para outra instância do mesmo produto tecnologico dentro do mesmo cnpj transmissor | Não é necessário ação do cliente. | Consentimentos autorizados devem continuar vigentes. | Não é necessário ação do recebedor. | O transmissor deve garantir que os consentimentos permaneçam vigentes sem impacto ao cliente durante o período de migração | Não é necessário ação do recebedor. | A migração de AS com mudança da instituição transmissora de dados, no atual patamar do Open Finance, não é recomendável. Assim, em cenários que envolvem essa migração, os consentimentos podem ser revogados. Esse cenários também pode ser aplicável às cooperativas |
| 9 | Cooperativa muda de sistema cooperativo (dois ou três níveis) – o serviço técnico de TI é provido pelo sistema cooperativo. | Após revogação ou manutenção automática na marca de origem o cliente deverá criar um novo consentimento na nova marca. | Existem dois cenários possíveis: manutenção ou revogação dos consentimentos. O Banco Central avaliará cada caso | Não é necessário ação do recebedor. | Os consentimentos serão revogados ou alterados na marca original. | Não é necessário ação do recebedor. | Casos de exceção deverão ser analisados pontualmente pelo regulador. |
| 10 | Cooperativa muda de sistema cooperativo – o serviço técnico de TI era provido pela própria cooperativa, agora será provido pelo sistema cooperativo. | Após revogação ou manutenção automática na marca de origem o cliente deverá criar um novo consentimento na nova marca. | Existem dois cenários possíveis: manutenção ou revogação dos consentimentos. O Banco Central avaliará cada caso | Não é necessário ação do recebedor. | A marca atual deverá indicar os campos no authorisation server cadastrado no diretório: DeprecatedDate; RetirementDate; SupersededByAuthorizationIServerID; Status. Os consentimentos serão revogados com a descontinuação da marca original. | Deve solicitar novo consentimento ao cliente | N/A |
| 11 | Cooperativa muda de sistema cooperativo – o serviço técnico de TI era provido pela mesma cooperativa, agora será provido pelo sistema cooperativo. Sistema cooperativo anterior permanece operacional. | Após revogação ou manutenção automática na marca de origem o cliente deverá criar um novo consentimento na nova marca. | Existem dois cenários possíveis: manutenção ou revogação dos consentimentos. O Banco Central avaliará cada caso | Não é necessário ação do recebedor. | Transmissor irá revogar ou alterar os consentimentos da cooperativa na marca original da qual está sendo desvinculada. | Deve solicitar novo consentimento ao cliente | Casos de exceção deverão ser analisados pontualmente pelo regulador. |
| 12 | Cooperativa é incorporada por outra cooperativa do mesmo sistema cooperativo. | Não é necessário ação do cliente. | Consentimentos autorizados devem continuar vigentes. | Não é necessário ação do recebedor. | A Resources deve listar os números antigos como UNAVAILABLE e os novos como AVAILABLE. | Não é necessário ação do recebedor. | Casos de exceção deverão ser analisados pontualmente pelo regulador. |
| 13 | Cooperativa participante da fase de dados muda para sistema cooperativo que não participa da fase de dados | Não é necessário ação do cliente. | Consentimentos devem ser revogados pela própria cooperativa no sistema cooperativo original | Não é necessário ação do recebedor. Não receberá mais dados dessa marca. | A revogação de consentimento deve ser avaliada pelo regulador. | Não é necessário ação do recebedor. | Casos de exceção deverão ser analisados pontualmente pelo regulador. |
Para a utilização dos campos de descontinuação do servidor de autorização disponíveis no Diretório as instituições transmissoras/detentoras devem preencher os campos no Diretório e as instituições receptoras/iniciadoras devem consumir as informações através da API do Diretório.
| Campos | Transmissora/Detentora | Receptora/Iniciadora |
| --- | --- | --- |
| Deprecation Date | Data programada para iniciar a descontinuação do servidor de autorização. | Data limite para solicitação de novos consentimentos naquele servidor. |
| Retirement Date | Data programada para a aposentadoria do servidor. | Data limite para consultas de consentimentos naquele servidor. |
| SupersededByAuthorisationServerId | ID do servidor de autorização que substituirá o servidor atual. | Redirecionamento das solicitações de novos consentimentos. |
| Status | Indica se o servidor está Ativo, Inativo ou Descontinuado. | |
Os campos *Deprecation Date* e *Retirement Date* serão obrigatórios no contexto de descontinuação de marcas e o campo *SupersededByAuthorisationServerId* só será obrigatório no caso de substituição do servidor de autorização.O campo *Deprecation Date*deve ser informado com pelo menos 10 dias antes do início da descontinuação.

---

# 25. APIs do Diretório - Boas Práticas

---
id: 807108609
title: 25. APIs do Diretório - Boas Práticas
version: 1
modified: 2025-05-03T04:20:38.043Z
url: /spaces/OF/pages/807108609/25.+APIs+do+Diret+rio+-+Boas+Pr+ticas
---

- Introdução
- Diferenciação entre APIs Públicas e APIs Protegidas APIs Públicas Cache-Control nas APIs de Dados Públicos do Diretório Requisitos Execução e Limitação de Taxa (rate-limit): APIs Protegidas Autenticação e Acesso Endpoints de Token: Características principais das APIs protegidas: Exemplos de APIs protegidas: Documentação Swagger
- Melhores Práticas para o Uso da API do Diretório Uso das APIs Públicas Uso das APIs Protegidas Recomendações Gerais Principais Considerações

## Introdução
As APIs do Diretório no Open Banking Brasil permitem que os participantes recuperem informações armazenadas no Diretório, facilitando o compartilhamento de dados seguro e eficiente em todo o ecossistema. Essas APIs são cruciais para descobrir participantes disponíveis, recursos técnicos como servidores de autorização ou APIs publicadas, e chaves públicas.Este guia tem como objetivo fornecer detalhes sobre as APIs abertas e restritas do Diretório, focando nas informações fornecidas por esses endpoints. Ele também oferece as melhores práticas a serem seguidas quanto ao consumo e à política de cache.
## Diferenciação entre APIs Públicas e APIs Protegidas
O Diretório oferece dois tipos de APIs, cada uma com finalidades distintas:·       **APIs Abertas**: Endpoints acessíveis publicamente, que não exigem mTLS, servem para fins gerais de descoberta, permitindo que os participantes reúnam informações não sensíveis, como detalhes dos participantes e chaves públicas.·       **APIs Restritas**: Esses endpoints requerem uma conexão mTLS para garantir uma interação segura e são usados ao acessar dados sensíveis ou seguros. O acesso a essas APIs é concedido após a obtenção de um token de acesso, como parte do fluxo de autenticação.
### APIs Públicas
As APIs públicas são endpoints que não exigem autenticação, permitindo que qualquer aplicativo interaja com elas sem usar um certificado TLS ou passar pela autenticação OAuth 2.0. Abaixo estão as APIs públicas disponíveis no Diretório:
| Nome da API | Endpoint | Uso | Recomendação de Consumo |
| Participantes | Sandbox: https://data.sandbox.directory.openbankingbrasil.org.br/participants Produção: https://data.directory.openbankingbrasil.org.br/participants | Explorar informações sobre os provedores de dados : Uma lista completa de servidores de autorização de provedores de dados, incluindo informações detalhadas sobre os recursos de API e certificações de servidores. Informações Atualizadas e Relevantes : Apenas organizações e servidores operacionais são incluídos, garantindo que os dados sejam precisos e reflitam o status mais recente. Destaque para Servidores de Autorização Ativos : A lista apresenta exclusivamente organizações com servidores de autorização funcionando, fornecendo uma visão clara e atualizada dos participantes disponíveis. | Recomendação: O endpoint /participants deve ser utilizado preferencialmente em relação às APIs restritas, como /authorisationservers ou /apiresources, para descoberta de dados. Como a /participants fornece informações abrangentes sobre os participantes ativos, incluindo seus servidores de autorização e recursos, ela reduz a necessidade de chamadas adicionais para endpoints restritos e oferece um método mais simples e sem mTLS para obter os detalhes necessários. Nota: As informações no endpoint /participants são recarregadas a cada 15 minutos. Dada essa frequência de atualização, recomenda-se armazenar os dados em cache localmente, em vez de fazer solicitações repetidas com mais frequência do que o necessário. Swagger: https://docs.connect.raidiam.io/participants-api |
| Keystore do Diretório | Sandbox: https://keystore.sandbox.directory.openbankingbrasil.org.br Produção: https://keystore.directory.openbankingbrasil.org.br | Esta keystore fornece a chave pública usada para assinar informações dentro do Diretório, como o Software Statement Assertion (SSA). O SSA é assinado pelo Diretório e utilizado durante o processo de Registro Dinâmico de Clientes (DCR). Os participantes podem usar essa chave para validar a assinatura do SSA, garantindo a integridade dos dados relacionados ao diretório, o que é crucial para concluir o processo de DCR de forma segura. | As chaves apresentadas nas keystores devem ser armazenadas em cache, pois suas informações só mudam quando um certificado é revogado ou adicionado. O acesso aos endpoints da keystore deve estar alinhado com a política de risco da sua instituição, mas manter um cache é importante devido à alta frequência com que as validações de assinatura são realizadas. O armazenamento em cache ajuda a minimizar solicitações redundantes e melhorar a eficiência geral ao verificar assinaturas e estabelecer conexões seguras. |
| Keystore de Certificados de Transporte a Nível de Software | Sandbox: https://web.sandbox.directory.openbankingbrasil.org.br/{organisationId}/application.jwks/{softwarestatementId}/transport.jwks Produção: https://web.directory.openbankingbrasil.org.br/{organisationId}/{softwarestatementId}/transport.jwks | Esta keystore retorna as chaves públicas dos certificados de transporte para todos os certificados anexados ao {softwarestatementId} e {organisationId} especificados. Essas chaves são usadas na conexão mTLS (mutual TLS) entre as instituições, garantindo comunicação segura entre as participantes. |
| Keystore de Certificados de Assinatura a Nível de Software | Sandbox: https://web.sandbox.directory.openbankingbrasil.org.br/{organisationId}/application.jwks/{softwarestatementId}/application.jwks Produção: https://web.directory.openbankingbrasil.org.br/{organisationId}/{softwarestatementId}/application.jwks | Essa keystore retorna as chaves públicas dos certificados de assinatura para todos os certificados anexados ao {softwarestatementId} e {organisationId} especificados. Essas chaves são usadas para validar as assinaturas das mensagens compartilhadas entre os participantes. Isso é crucial para garantir que os dados trocados entre as instituições estejam devidamente assinados e sejam confiáveis. |
| Keystore de Certificados de Assinatura a Nível de Organização | Sandbox: https://web.sandbox.directory.openbankingbrasil.org.br/{organisationId}/application.jwks Produção: https://web.directory.openbankingbrasil.org.br/{organisationId}/application.jwks | Este endpoint fornece as chaves públicas dos certificados anexados à respectiva organização, identificada pelo {organisationId}. Essas chaves são usadas para validar as assinaturas das mensagens compartilhadas entre os participantes. Isso é crucial para garantir que os dados trocados entre as instituições sejam devidamente assinados e confiáveis. |
| Recursos de API | Sandbox: https://web.sandbox.directory.openbankingbrasil.org.br/config/apiresources Produção: https://web.directory.openbankingbrasil.org.br/config/apiresources | Este endpoint fornece informações sobre todos os recursos de API disponíveis para o ecossistema do Open Banking Brasil para publicação. Isso inclui: ·       Tipo de Família: O nome do recurso de API ·       Versão: A versão disponível de cada recurso de API ·       URLs Esperadas: A estrutura esperada da URL para cada endpoint do recurso de API | Este endpoint deve ser chamado para verificar os detalhes sobre os Recursos de API que podem ser registrados no Framework de Confiança, bem como suas expressões regulares esperadas. |
| Well-known | Sandbox: https://auth.sandbox.directory.openbankingbrasil.org.br/.well-known/openid-configuration Produção: https://auth.directory.openbankingbrasil.org.br/.well-known/openid-configuration | O endpoint .well-known/openid-configuration fornece metadados essenciais sobre o OP (Provedor OpenID) do Diretório, incluindo URLs para APIs restritas, como /token e /auth. Este endpoint serve como o ponto de partida para o fluxo de autenticação necessário para interagir com as APIs restritas. | Esses metadados raramente mudam e são atualizados apenas em casos específicos, como a adição de novos recursos ou mudanças significativas na configuração. Portanto, chamadas repetidas a este endpoint são desnecessárias. |
| Roles | Sandbox: https://data.sandbox.directory.openbankingbrasil.org.br/roles Produção: https://data.directory.openbankingbrasil.org.br/roles | O endpoint /roles fornece informações sobre os diversos papéis atribuídos aos participantes no nível organizacional dentro do ecossistema do Open Banking Brasil. Os papéis atribuídos ajudam a definir a função e as capacidades de cada participante, como fornecedor de dados ou receptor de dados. Essas informações são úteis para entender quais entidades possuem autorizações e responsabilidades específicas no ecossistema. | |
**Nota**: Os dados fornecidos pelas APIs públicas mudam muito raramente, normalmente apenas quando são feitas atualizações significativas. Por isso, é recomendável implementar uma estratégia de cache para evitar chamadas desnecessárias a esses endpoints. A duração do cache deve estar alinhada com a diretiva max-age especificada no cabeçalho Cache-Control (veja a [seção de cache](https://raidiam.atlassian.net/wiki/spaces/BCM/pages/edit-v2/4184342598#Cache-Control-nas-APIs-de-Dados-P%C3%BAblicos-do-Diret%C3%B3rio) para referência). A natureza estável desses dados suporta práticas de cache eficientes e reduz solicitações redundantes, melhorando o desempenho.
### Cache-Control nas APIs de Dados Públicos do Diretório
**Esta seção é aplicável a todos os endpoints data.* e auth.*, notavelmente o endpoint de /participants e o /well-known.**As respostas da API do Diretório incluem um cabeçalho Cache-Control, que especifica diretivas de cache para os clientes.**Exemplo de Cabeçalho**:Isso indica que:·       A resposta pode ser armazenada em cache por qualquer cache (pois está marcada como `pública`).·       O `max-age=900` especifica que a resposta pode ser armazenada por 900 segundos (15 minutos) antes que uma nova solicitação deva ser feita.
#### Requisitos
·       **Cache-Control**: Os participantes **DEVEM** respeitar as diretivas de cache-control e implementar cache local com base no valor de max-age.·       **Cache Local ou Proxy**: Para cumprir as políticas de limitação de taxa, espera-se que os participantes utilizem mecanismos de cache local ou proxies organizacionais.
#### Execução e Limitação de Taxa (rate-limit) :
·       Participantes que executarem um número de solicitações muito acima do esperado, com base no cabeçalho de política de cache, podem ter suas requisições bloqueadas (rate-limit) pelos serviços do Diretório
### APIs Protegidas
As APIs protegidas mTLS só podem ser acessadas por aplicações (Software Statements) registrados no Diretório e que possuam certificados TLS/Transport válidos emitidos por Autoridades Certificadoras (CAs) autorizadas dentro do Diretório.Para acessar essas APIs protegidas, o participante deve gerar um token de acesso com o escopo `directory:software`, chamando o endpoint de token usando o tipo de grant_type `client_credentials`. As instruções para obter um token de acesso podem ser encontradas em [https://docs.connect.raidiam.io/client-credentials-flow-obtain-access-token#YzDfh](https://docs.connect.raidiam.io/client-credentials-flow-obtain-access-token#YzDfh) 
#### Autenticação e Acesso
O fluxo de autenticação para as APIs restritas começa com o endpoint /.well-known/openid-configuration, que fornece os metadados necessários, incluindo URLs para obtenção do token de acesso (/token) e autorização (/auth). Após obter o token de acesso, os participantes podem usá-lo para acessar de forma segura as APIs restritas.
#### Endpoints de Token :
·       Sandbox: [https://matls-auth.sandbox.directory.openfinance.ae/token](https://matls-auth.sandbox.directory.openfinance.ae/token)·       Produção: [https://matls-auth.directory.openfinance.ae/token](https://matls-auth.directory.openfinance.ae/token)Após obter o token de acesso, ele pode ser usado para acessar as operações GET de todas as APIs do Diretório que não retornam dados pessoais.·       A documentação Swagger para a API do TF está disponível aqui: [https://api.connect.raidiam.io/source.yaml](https://api.connect.raidiam.io/source.yaml)·       As URLs do Host da API são:o   **Sandbox**: [https://matls-api.sandbox.directory.openfinance.ae](https://matls-api.sandbox.directory.openfinance.ae)o   **Produção**: [https://matls-api.directory.openfinance.ae](https://matls-api.directory.openfinance.ae)Um exemplo de solicitação contra as APIs protegidas do Diretório pode ser encontrado em: [https://docs.connect.raidiam.io/find-all-applications](https://docs.connect.raidiam.io/find-all-applications) 
### Características principais das APIs protegidas:
As APIs protegidas podem ser acessadas por meio de uma conexão mTLS (mutual TLS) com as seguintes URLs base:·       **URL Base do Sandbox**: [https://matls-api.sandbox.directory.openbankingbrasil.org.br/{endpoint}](https://matls-api.sandbox.directory.openbankingbrasil.org.br/%7bendpoint%7d)·       **URL Base de Produção**: [https://matls-api.directory.openbankingbrasil.org.br/{endpoint}](https://matls-api.directory.openbankingbrasil.org.br/%7bendpoint%7d)
#### Exemplos de APIs protegidas:
·       **/organisations**
Fornece informações sobre todas as organizações que participam do ecossistema Open Banking Brasil.·       **/organisations/{organisationId}**
Permite acessar informações detalhadas de uma organização específica identificada por {organisationId}.·       **/organisations/{organisationId}/authorisationservers**
Fornece informações sobre todos os servidores de autorização vinculados a um determinado {organisationId}.·       **/organisations/{organisationId}/softwarestatements**
Lista todas as declarações de software associadas a um {organisationId} específico.·       **/organisations/{organisationId}/softwarestatements/{softwarestatementId}/assertion**
Gera uma Declaração de Software (SSA) para um determinado {organisationId} e {softwarestatementId}.·       **/clients**
Lista todos os clientes registrados no diretório. A vantagem sobre a API de declarações de software é que ela retorna todas as declarações de software de todas as organizações, sem a necessidade de fazer uma chamada por {organisationId}.Essas APIs protegidas fornecem informações sensíveis e detalhadas, que são essenciais para o compartilhamento seguro e autorizado de dados dentro do ecossistema.
#### Documentação Swagger
Uma lista completa de todos os endpoints disponíveis está disponível na documentação Swagger fornecida pela Raidiam, que abrange vários endpoints.A especificação Swagger pode ser usada para navegar por todas as operações disponíveis dentro do Diretório e determinar quais endpoints são adequados para diferentes casos de uso.**Observação**: Implemente estratégias de **backoff exponencial** para lidar com solicitações falhadas, evitando sobrecarregar o sistema com chamadas repetidas e garantindo a recuperação suave de erros.**Swagger**: [https://api.connect.raidiam.io/source.yaml](https://api.connect.raidiam.io/source.yaml)
## Melhores Práticas para o Uso da API do Diretório
Para garantir o uso eficiente e seguro das APIs do Diretório, siga as seguintes melhores práticas:
### Uso das APIs Públicas
**Descoberta Inicial de Dados:**·       Utilize o endpoint `/participants` para obter informações gerais, como dados sobre participantes ativos e seus endpoints. Isso ajuda a evitar o uso desnecessário de APIs restritas.**Cache Eficiente:**·       Como as informações fornecidas pelas APIs abertas são, em sua maioria, estáticas, recomenda-se fazer cache dos dados para reduzir a frequência das chamadas à API. Por exemplo, o endpoint `/participants` é atualizado a cada 15 minutos, e o `.well-known/openid-configuration` também é relativamente estático, então armazenar em cache esses endpoints ajuda a equilibrar a carga do sistema.
### Uso das APIs Protegidas
**Utilizar Apenas Quando Necessário:**·       As APIs restritas exigem mais recursos devido às conexões mTLS. Utilize essas APIs apenas quando interações seguras forem necessárias. Por exemplo, use `/authorisationservers` apenas se os dados necessários não estiverem disponíveis no endpoint `/participants`, como quando se busca servidores de autorização inativos, que não são retornados por este último.**Otimização das Conexões:**·       Implemente conexões mTLS persistentes ou utilize pooling de conexões para lidar com solicitações repetidas às APIs restritas, reduzindo o overhead dos handshakes. Use **backoff exponencial** para tentar novamente solicitações que falharam.
### Recomendações Gerais
**Priorizar Dados Abertos:**·       Sempre que possível, inicie a descoberta de dados com APIs abertas para reduzir o uso de endpoints restritos.**Armazenamento Seguro de Tokens:**·       Certifique-se de armazenar tokens e outros dados sensíveis de forma segura, respeitando as políticas de expiração para prevenir acessos não autorizados.
### Principais Considerações
·       **Use APIs públicas** primeiro para obter informações gerais e de descoberta, com o `/participants` sendo a fonte preferida para descobrir servidores de autorização e recursos ativos.·       **Minimize chamadas a APIs mTLS**, utilizando-as apenas para interações seguras e sensíveis.·       **Cache eficiente** é crucial para reduzir a carga e garantir um uso suave da API, especialmente para dados majoritariamente estáticos, como `/participants`, `.well-known/openid-configuration`, e os diferentes tipos de keystores.Seguindo essas melhores práticas, os participantes podem garantir uma integração segura, eficiente e escalável dentro do ecossistema do Open Finance Brasil.

---

# 26. Anexos

---
id: 134316186
title: 26. Anexos
version: 3
modified: 2025-05-03T04:20:38.021Z
url: /spaces/OF/pages/134316186/26.+Anexos
---

## Mapa de utilização do Guia Operacional do Diretório por Papel Regulatório

## MODELO-DE-SEGURANÇA Modelo de Segurança
Poderes dos Usuários no Diretório
## Recomendações para Receptores

## Recomendações para busca - Identifica Marca: Complemento ao Guia de Experiencia para Receptores de Dados
Exibir a(s) marca(s) em função do nome da mesma (Marca do Authorisation Server) e da literal que o cliente informou.Caso sejam identificados mais de uma marca de mesmo nome, exibir uma única vez para o cliente.**Validar se a marca/Authorisation Servers possui os recursos (família de API’s) necessários para a jornada.**Em `Ver detalhes da marca` exibir todas as organizações que estão relacionadas a ela:
- Se a marca estiver em mais do que uma organização, exibir todas as organizações que a mesma está cadastrada;
- Organização que é hierarquicamente inferior a organização (mãe) que a marca está cadastrada, desde que a mesma (filha) não possua uma marca cadastrada para ela.
Para saber as instituições hierarquicamente inferiores e necessário utilizar o campo parente. No mesmo será indicado o CNPJ da instituição mãe, se a mesma for uma filha.Se for mãe, terá o campo sem dado.
## Recomendações para busca - Identifica Instituição: Complemento ao Guia de Experiencia para Receptores de Dados
Exibir a(s) marca(s) em função do nome da mesma (Marca do Authorisation Server) e da literal que o cliente informou.Exibir a(s) instituição(ões) em funções do nome da organização e da literal que o cliente informou.Aplicar a mesma regra utilizada para exibir as instituições de uma marca para demonstrar quantas instituições estão associadas a marca retornada, quando a busca identificar uma instituição.
## Recomendações para busca - Identifica Instituição: Complemento ao Guia de Experiencia para Receptores de Dados
No detalhamento da marca, exibir a marca informada no Authorisation ServerA descrição da marca cadastrada no Autorisation Server.E para a instituições que participam da marca, aplicar a mesma regra utilizada para exibir as instituições de uma marca.Maiores informações:[https://github.com/OpenBanking-Brasil/specs-seguranca/blob/main/aspsp-user-guide-ptbr.md](https://github.com/OpenBanking-Brasil/specs-seguranca/blob/main/aspsp-user-guide-ptbr.md) [https://github.com/OpenBanking-Brasil/specs-seguranca/blob/main/tpp-user-guide-ptbr.md](https://github.com/OpenBanking-Brasil/specs-seguranca/blob/main/tpp-user-guide-ptbr.md) 
## Tabela da Dados Utilizado na Recomendação

### Organização

| Dados | UI Diretório | API |
| `Nome` | LEGAL NAME (ING) NOME LEGAL (PT) | `LegalEntityName` |
| `CNPJ` | REGISTRATION NUMBER-CNPJ (ING) NÚMERO DE REGISTRO – CNPJ (PT) | `RegistrationNumber` |
| `Mãe` | PARENT ORGANISATION REFERENCE ID (ING) NÚMERO DE REGISTRO DA ORGANIZAÇÃO MÃE – CNPJ (PT) | `ParentOrganisationReference` |

## Tabela da Dados Utilizado na Recomendação

### Authorisation Server

| Dados | UI Diretório | API |
| `Marca` | CUSTOMER FRIENDLY SERVER NAME (ING) NOME DO SERVIDOR (PT) | `CustomerFriendlyName` |
| `Descrição` | DESCRIPTION (ING) DESCRIÇÃO (PT) | `CustomerFriendlyDescription` |

---

# Controle de Versão - [GODC]

---
id: 133791750
title: Controle de Versão - [GODC]
version: 4
modified: 2025-05-03T04:20:37.919Z
url: /spaces/OF/pages/133791750/Controle+de+Vers+o+-+GODC
---

| Versão | Data | Resumo das Alterações |
| --- | --- | --- |
| 1.2.15 | | Alteração: As orientações para que as instituições submetessem ao regulador o pedido de alteração de seus servidores foram removidas em 6 dos 8 cenários que continham essa consideração. Além disso, foram realizados ajustes pontuais nos demais cenários descritos no documento Ciclo de Vida de Authorization Server . |
| 1.2.15 | | Alteração: Foi adicionada um novo detalhamento na sessão Ciclo de Vida de Authorization Server |
| 1.2.15 | | Alteração: Foi adicionada um novo detalhamento na sessão Carregando certificados emitidos por autoridade de certificação em Produção Alteração: Foi adicionada um novo detalhamento na sessão Criando um Software Statements , em detalhamento dos campos Alteração: Foi adicionada um novo detalhamento na sessão Anexos no Mapa de utilização do Guia Operacional do Diretório por papel regulatório |
| 1.2.14 | | Adição: Foi adicionada informação no campo nota do slide Detalhamento dos Tipos de Contato Atualização: Imagens da ETAPA 1: Exibindo detalhes de uma organização Adição: Nova funcionalidade no diretório, TAG “Habilitação de iniciação de pagamento” |
| 1.2.13 | | Adição: ETAPA 3: Removendo um recurso de uma API Alteração: nomenclatura Open Banking para Open Finance, bem como as logomarcas ao longo do documento Alteração: formatação adequada de parágrafos |
| 1.2.12 | | Adição: foi adicionado um novo detalhamento apresentando os Tipos de Usuários . Adição: foi adicionado no rodapé do slide Cadastramento de Conglomerado uma nota que caso a organização faça parte de um conglomerado é fundamental referenciar as organizações filhas com a organização mãe. Adição: foi adicionada uma nova seção Cadastrando Contatos de Notificação . Adição: foi adicionada uma nova seção Cadastrando reivindicações de domínio de autoridade Adição: foi adicionada uma nova seção Cadastrando reivindicações de autoridade . Adição: foi adicionada uma nova seção Criando uma nova reivindicação de autoridade de software . Alteração: a seção Criando uma solicitação de Assinatura de Certificado (CSR) em Sandbox foi ajustada para Criando certificados de transporte e assinatura em Sandbox . Adição: foi adicionado a seção Carregando certificados emitidos por autoridade de certificação em Produção . Adição: foi adicionado a seção Modelo de Segurança – Poderes dos Usuários no Diretório . Alteração: campo "Description" no cadastro do Authorisation Server agora é obrigatório, para maiores detalhes  Cadastrando um Authorisation Server . |
| 1.2.11 | | Adição de link nos menus e na opção home Adição da tabela de recursos fase na seção cadastrando recursos de uma API. |
| 1.2.10 | | Orientações sobre sobre cadastro de iniciador de pagamentos puro em Cadastrando um Authorisation Server . |
| 1.2.9 | | Atualização do detalhamento dos Contatos de notificação . Inclusão de orientações sobre o processo de emissão de certificado ICP, tópico 12 Alteração das imagens do Open Finance. Alteração do nome Open Banking para Open Finance. |
| 1.2.8 | | Adição do slide Alternativas para atualização da marca com recomendações para o consumo da marca Atualização das orientações com relação aos perfis necessários para os sistemas e funções de um usuário/contato em Cadastrando reivindicações de autoridade Adição da seção Como se inscrever nas atualizações de lançamento do Diretório com orientações para subscrição e recebimento de notificações de atualizações no Release Notes |
| 1.2.7 | | Versionamento em Cadastrando recursos de uma API . Atualização de orientações sobre os campos Customer Friendly Server Name e Description em Cadastrando um Authorisation Server . Adição de forma de cadastro de certificados de segurança no Software Statement em Criando Software Statements . Adição de forma de notificação em Configurando eventos de notificação . |
| 1.2.6 | | Adição dos detalhes sobre o cadastramento de recursos com certificação automática Cadastramento de Recursos Fase 4A . |
| 1.2.5 | | Adição da definição dos tipos de contatos no diretório em Detalhamento dos tipos de contato . |
| 1.2.4 | | Alteração na definição da modalidade PAGTO em Detalhamento das modalidades. |
| 1.2.3 | | Ponto de atenção sobre Authorisation Server em Cadastrando um Authorisation Server . Mudança na descrição do campo Client URI e retirada dos campos (mode e environment) Criando um Software Statements . Ponto de atenção sobre usuários de plataformas em Cadastrando reivindicações de autoridade . Alteração quanto ao cadastramento de recursos em Cadastrando recursos de uma API . |
| 1.2.2 | | Alteração: Correção dos exemplos de Fase 2 e orientações Fase 3 Cadastrando recursos de uma API . |
| 1.2.1 | | Alteração: Foi a incluído recomendação para cadastramento de recurso tanto da Fase 1 quanto da Fase 2 em Cadastrando recursos de uma API . Alteração: Foi alterado a descrição do campo Customer Friendly Server Name do Cadastrando um Authorisation Server . Alteração: Foi alterado a descrição do campo Client Name do Criando um Software Statements . Alteração: Adicionado um ponto de atenção em Obtendo um Software Statements Assertion . Alteração: Adicionado um ponto de atenção em Criando certificados de transporte e assinatura em Sandbox . |
| Draft | | Alteração: foi adicionado recomendações e casos de uso para exemplificar o cadastramento de marcas . Alteração: foi alterado o detalhamento do campo “Descrição” do Authorisation Server . Adição: foi adicionado uma descrição do logotipo . Adição: foi adicionado a seção Recomendações para receptores com recomendações para a montagem de telas de experiencia de usuário dado a estrutura de dados do Diretório. |