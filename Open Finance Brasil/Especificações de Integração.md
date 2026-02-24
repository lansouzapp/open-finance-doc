# APIs Service Desk > v0.0.1 - APIs Service Desk > Informações Gerais - APIs Service Desk - v0.5

---
id: 17377992
title: Informações Gerais - APIs Service Desk - v0.5
version: 6
modified: 2025-03-24T14:55:51.063Z
url: /spaces/OF/pages/17377992/Informa+es+Gerais+-+APIs+Service+Desk+-+v0.5
---

# Especificação API Service Desk Open Finance Brasil
O objetivo desse documento é prover material para publicação das informações referentes a APIs do Service Desk no portal do Open Finance Brasil.A Documentação completa e também utilizada como fonte deste conteúdo pode ser encontrada em: [https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm](https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm) 
# 1. Modelo de Fluxo de atendimento:

# 2. URLs de acesso:
[https://servicedesk.openfinancebrasil.org.br/](https://servicedesk.openfinancebrasil.org.br/): Ambiente Produtivo do Service Desk Open Finance.[https://servicedesksandbox.openfinancebrasil.org.br/](https://servicedesksandbox.openfinancebrasil.org.br/): Ambiente Sandbox (Homologação) do Service Desk Open Finance.
# 3. Tabela DE/PARA front-end para API

| Nome do Campo | API | Detalhes |
| Categoria | problem_type | 1ºNível_2ºNível_3ºNível / Na resposta: 1º Nível de Categoria |
| Subcategoria | problem_sub_type | Na resposta: 2º Nível de Categoria |
| Categoria de 3º Nível | third_level_category | Na resposta: 3º Nível de Categoria |
| Título | title | |
| Descrição | description | |
| Anotações | notes | {“userName”:{NOME DO USUÁRIO},”createDate”:{DATA EM MILISEGUNDOS},”text”:{TEXTO}} |
| Solução | solution | |
| Atividades | activities | Iterações entre N1 e N2 |
| Data de solicitação | insert_time | Em milisegundos |
| Data de modificação | uptade_time | Em milisegundos |
| Data de encerramento | close_time | Em milisegundos |
| Prazo de SLA | due_date | Em milisegundos |
| Data Prevista para Implementação da Correção | CustomColumn82sr | Necessária quando utilizado o status “AGUARDANDO CORREÇÃO N2” em categorias de Incidentes |
| Usuário Solicitante | request_user | |
| Equipe de Atendimento | assigned_group | |
| Instituição Requerente | CustomColumn155sr | Nome da instituição que está abrindo o chamado |
| Especialista Atribuído | responsibility | |
| Status | status | Conferir lista de status |
| Contador de Reabertura | reopen_counter | Número de vezes que o chamado foi reaberto |
| Anexos | attachments | |
| Tipo de Registro de Serviço | sr_type | |
| Arquivado | arquive | Tipo Booleano |
| Nível de Suporte Atual | current_support_level | |
| Tipo do Chamado | type | Incidentes = 1; Solicitação de Serviço = 10 |
| Formulário Utilizado | template | Padrão Incidente = 20; Padrão Solicitação de Serviço = 12 |
| O conteúdo da reclamação é procedente? | CustomColumn129sr | Necessário o preenchimento ao encerrar um chamado tipo Incidente (status: ATENDIMENTO ENCERRADO) |
| Tipo de Erro | CustomColumn119sr | Disponível apenas para consulta nos chamados da categoria “Erro na Jornada ou Dados” |

# 4. APIs
Tipo de API: RESTFormato dos dados de retorno e envio: JSON Fonte do conteúdo:[https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm](https://community.sysaid.com/Sysforums/templates/default/help/files/Guide_REST_API.htm) FAQ Service Desk: [https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp](https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp)
## 4.1 Login
Responsável pela autenticação na API, é pré-requisito para a execução de qualquer requisição. As credenciais devem ser solicitadas via Portal do Service Desk Open Finance.É necessário um usuário Administrador (Atendimento N2) para a utilização da API.
#### POST - {URL}/api/v1/login
Campos Obrigatórios:“user_name” = Nome de usuário de integração “password” = Senha do usuário de integraçãoExemplo de Body:{"user_name":"{NOME DO USUÁRIO}", "password":"{SENHA}"}No retorno é necessário armazenar o Cookie JSESSIONID para consumo dos demais métodos.Nesta requisição de login, também é necessário identificar o ID do Grupo de Atendimento que será utilizado nas requisições de consulta de chamados, para identificar este número na resposta deve ser capturado o valor do "id" na key "user_groups". De acordo com o exemplo a seguir:
## 4.2 Consulta de Chamados
Retorna todos os chamados, ativos e encerrados, que se encontram na equipe de atendimento do usuário autenticado, com exceção dos chamados que já foram arquivados. Neste tipo de requisição é necessário passar o parâmetro “assigned_group” para que apenas os tickets pertencentes ao grupo de atendimento do usuário sejam retornados.
#### GET – {URL}/api/v1/sr?assigned_group={ID do Grupo}
Body: Manter vazioPara refinar a busca é necessário incluir parâmetros na requisição.Estes são alguns exemplos de keys comuns a serem utilizadas:“problem_type” = Categoria: 1º nível_2º nível_3ºnível “status” = Qual status que o chamado se encontra “insert_time” = Abertura do chamado“due_date” = SLAConsultar a Tabela DE/PARA (Tópico 3.)Exemplo de requisição:
#### GET – {URL}/api/v1/sr?problem_type=Incidentes_APIs_Erros&assigned_group=10
Body: Manter vazioO retorno virá com todas as informações referentes aos chamados que entrarem nos parâmetros estabelecidos. Para retornar campos específicos na reposta é necessário utilizar a key “fields" na requisição e selecionar os parâmetros de retorno.Estes são alguns exemplos de keys comuns a serem utilizadas:“id” = ID do chamado“update_time” = Data e hora da última modificação “solution” = Solução do chamado“request_user” = Usuário Solicitante Consultar a Tabela DE/PARA (Tópico 3.)Exemplo de requisição:
#### GET – {URL}/api/v1/sr?problem_type=Incidentes_APIs_Erros&fields=id,update_time&assigned_group=10
Aplicando os mesmos parâmetros da requisição anterior, os chamados exibidos serão os mesmos, porém agora apenas a informações indicadas em “fields” serão exibidas em cada chamado respectivamente.Existem outros parâmetros que podem ser consultados na Documentação Completa do SysAid (Tópico 4.)Exemplo de retorno:Para uma consulta que considere os chamados arquivados, deve ser passado um parâmetro a mais no endpoint da requisição: "archive=1".Portanto, caso o objetivo seja trazer toda a base de chamados (arquivados e não) o ideal é que seja executada a query da seguinte forma:**GET – {URL}/api/v1/sr?assigned_group={idgrupo}&archive=0,1**
## 4.3 Consulta de chamado específico
Traz todas as informações de um chamado específico, possível aplicar parâmetros de busca e de retorno para customizar a consulta.
#### GET – {URL}/api/v1/sr/{ID DO CHAMADO}

## 4.4 Abertura de Chamados
Abre um chamado para o Service Desk. Todos os campos a serem inseridos no chamado devem ser passados no Body da requisição.Consultar a Tabela DE/PARA (Tópico 3.) para informar o “type” e “template”Algumas categorias podem possuir formulários customizados, sendo necessário utilizar templates específicos e informar campos customizados. Nestes casos deve-se acessar a FAQ do Service Desk e consultar a categoria específica no seguinte link:[https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp](https://servicedesk.openfinancebrasil.org.br/KBFAQTree.jsp)
#### POST – {URL}/api/v1/sr?type={TIPO DE CHAMADO}&template={ID DO FORMULÁRIO}
Campos Obrigatórios:“problem_type” = Categoria (São 3 níveis de categorização, devem ser separados utilizando “_”) “title” = Título“description” = DescriçãoExemplo de requisição:
#### POST – {URL}/api/v1/sr?type=1&template=20
Exemplo de Body:
## 4.5 Alteração no Chamado
Alterar um chamado, modificando as informações. Todos os campos a serem modificados no chamado devem ser passados no Body da requisição.(Para consultar a lista com os IDs dos Status, visite a FAQ).
#### PUT - {URL}/api/v1/sr/{ID DO CHAMADO}
Exemplo de Body:
## 4.6 Recuperado Anexos
Para consultar os anexos dentro do chamado é necessário a utilização do campo "attachments" na chave "fields", de acordo com o exemplo a seguir:
#### GET - {URL}/api/v1/sr/{ID do CHAMADO}?fields=attachments
Body: Manter vazioExemplo de retorno:Com o ID do anexo contido no campo "fileId" você vai poder utilizar a URL de Download para obter o arquivo.URL de download:
#### {URL}/getFile?table=service_req&id={ID do CHAMADO}&getFile={ID do ANEXO}

## 4.7 Inserindo Atividades
Para utilizar o campo de atividades, deve ser feita a seguinte requisição:
#### POST – {URL}/api/v1/sr/{ID DO CHAMADO}/activity
Campos obrigatórios:"id" = ID do chamado onde será adicionada a atividade "userId" = ID do usuário que está inserindo a atividade "fromTime" = Data e hora do início da atividade "toTime” = Data e hora do término da atividade "description” = Descrição da AtividadeObs: A data e hora de início e término da atividade podem ser as mesmas, mas devem indicar o momento em que foi inserida a atividade.Exemplo do Body:
## 4.8 Consulta de chamados como solicitante
Além das consultas que podem ser feitas como Equipe de Atendimento dos chamados, para aqueles chamados que são abertos pelo seu usuário, tanto via API quanto via Portal do Usuário Final, também é possível fazer a consulta dos mesmos via API, para isso deve-se acrescentar um Header na requisição.Header:Portanto ambas as requisições dos tópicos **4.2**e **4.3**podem ser executadas adicionando este novo header para efetuar as consultas no papel de usuário solicitante. Lembrando que mesmo efetuando a consulta como solicitante é pré-requisito que o seu usuário seja N2 (Administrador) e tenha as permissões necessárias para o consumo da API.Caso o usuário seja supervisor, também será possível obter os chamados abertos por outros membros da instituição utilizando um parâmetro adicional no endpoint:Como no exemplo a seguir:
#### GET - {URL}/v1/sr?status=1&fields=id,insert_time,status&supervisedRequests=Y

## 4.9 Adição de notas como solicitante
Seguindo o que foi instruído no item **4.8**além de fazer a consulta das informações, também é possível fazer a adição de notas ao chamado no papel de requisitante via API. Para isso é necessário a utilização do Header e executar o processo descrito no item **4.5**seguindo os parâmetros para a adição de notas contida na Tabela DE/PARA no item **3.0**deste documento:
#### Requisição: PUT - {URL}/api/v1/sr/{ID DO CHAMADO}
Exemplo do Body:É importante ressaltar que não devem ser alterados os demais campos do chamado incluindo o status, apenas a adição da nota deve ser executada e o chamado já terá o status alterado de forma automática pelo SysAid.
## 4.10 Adição de anexos
Para adicionar anexos a um chamado é necessário a utilização do body como “form-data” e a key como “file”, de acordo com o exemplo a seguir:Key: fileValue: exemplo.txt **POST - {URL}/api/v1/sr/{ID do CHAMADO}/attachment** **Importante:** No value da requisição, é necessário informar o nome e a extensão do arquivo a ser adicionado.
## 4.11 Consulta de Chamados Supervisionados
Caso o usuário seja supervisor, também será possível obter os chamados abertos por outros membros da instituição utilizando um parâmetro adicional no endpoint.Essa requisição retorna todos os chamados, ativos e encerrados com exceção dos chamados que já foram arquivados.  
**GET – {URL}/api/v1/sr/supervisor**Body: Manter vazioPara refinar a busca é necessário incluir parâmetros na requisição.Estes são alguns exemplos de keys comuns a serem utilizadas: “problem_type” = Categoria: 1º nível_2º nível_3ºnível“status” = Qual status que o chamado se encontra“insert_time” = Abertura do chamado“due_date” = SLA Consultar a Tabela DE/PARA (Tópico 3.) Exemplo de requisição: **GET – {URL}/api/v1/sr/supervisor?problem_type=Incidentes_APIs_Erros**Body: Manter vazio****O retorno virá com todas as informações referentes aos chamados que entrarem nos parâmetros estabelecidos. Para retornar campos específicos na reposta é necessário utilizar a key “fields" na requisição e selecionar os parâmetros de retorno. Estes são alguns exemplos de keys comuns a serem utilizadas: “id” = ID do chamado“update_time” = Data e hora da última modificação“solution” = Solução do chamado“request_user” = Usuário SolicitanteConsultar a Tabela DE/PARA (Tópico 3.) Exemplo de requisição: **GET – {URL}/api/v1/sr/supervisor?problem_type=Incidentes_APIs_Erros&fields=id,update_time******Aplicando os mesmos parâmetros da requisição anterior, os chamados exibidos serão os mesmos, porém agora apenas a informações indicadas em “fields” serão exibidas em cada chamado respectivamente.Existem outros parâmetros que podem ser consultados na Documentação Completa do SysAid (Tópico 4.)Exemplo de retorno: [    {        "id": "1273",        "canUpdate": true,        "canDelete": true,        "canArchive": true,        "hasChildren": false,        "info": [            {                "key": "update_time",                "value": 1646856953697,                "valueClass": "",                "keyCaption": "Data de modificação",                "valueCaption": "09-03-2022 17:15:53"            }        ]    },    {        "id": "1274",        "canUpdate": true,        "canDelete": true,        "canArchive": true,        "hasChildren": false,        "info": [            {                "key": "update_time",                "value": 1646862779347,                "valueClass": "",                "keyCaption": "Data de modificação",                "valueCaption": "09-03-2022 18:52:59"            }        ] Para uma consulta que considere os chamados arquivados, deve ser passado um parâmetro a mais no endpoint da requisição: "archive=1".Portanto, caso o objetivo seja trazer toda a base de chamados (arquivados e não) o ideal é que seja executada a query da seguinte forma:**GET – {URL}/api/v1/sr/supervisor?archive=0,1****Em caso de dúvidas ou dificuldades na utilização da API entrar em contato com o Service Desk através do Portal:**[https://servicedesk.openfinancebrasil.org.br/](https://servicedesk.openfinancebrasil.org.br/)

---

# APIs Service Desk > v0.0.1 - APIs Service Desk > Informações Técnicas - APIs Service Desk - v0.0.1

---
id: 17378033
title: Informações Técnicas - APIs Service Desk - v0.0.1
version: 2
modified: 2022-11-22T20:27:39.324Z
url: /spaces/OF/pages/17378033/Informa+es+T+cnicas+-+APIs+Service+Desk+-+v0.0.1
---

[Abrir informação técnica](https://servicedesksandbox.openbankingbrasil.org.br/swagger/)no100%hide9083.13

---

# APIs do Diretório > Lista de Participantes

---
id: 17377913
title: Lista de Participantes
version: 1
modified: 2022-10-27T12:03:54.881Z
url: /spaces/OF/pages/17377913/Lista+de+Participantes
---

Os **participantes do Open Finance Brasil**podem ser consultados a partir do arquivo localizado no *link* [https://data.directory.openbankingbrasil.org.br/participants](https://data.directory.openbankingbrasil.org.br/participants).A lista é composta por todos os participantes cadastrados no Diretório do Open Finance.Os campos que contêm informações relevantes para descoberta dos *endpoints* para a Fase 1 são:
| Campo | Descrição |
| --- | --- |
| OrganisationDetails.OrganisationId | O Identificador do participante |
| AuthorisationServers.CustomerFriendlyName | Nome da marca |
| OrganisationDetails.RegistrationNumber | CNPJ |
| OrganisationDetails.RegisteredName | Razão Social |
| OrgDomainRoleClaim.Role | Papel junto ao Open Finance |
| OrgDomainRoleClaim.Status | Status do papel |
| AuthorisationServers.APIResources.APIFamilyTipe | URL das APIs |
| AuthorisationServers.APIResources.APIVersion | |
| AuthorisationServers.APIResources.APIEndPoint | |
| AuthorisationServers.DeveloperPortalURI | URL da documentação sobre a API do participante |
A especificação do arquivo de participantes pode ser acessada [aqui](https://github.com/OpenBanking-Brasil/specs-directory/blob/main/swagger_participants.yaml).
## Especificações de registro de participantes
Passo a passo do Cadastramento - acesse neste [link](https://openfinancebrasil.atlassian.net/wiki/download/attachments/7996604/Open_Finance_cadastro_diretorio_passo_a_passo.pdf?api=v2) o arquivo com instruções.

---

# APIs do Diretório > v1.3 - APIs do Diretório > Informações Gerais - APIs do Diretório - v1.3

---
id: 17377863
title: Informações Gerais - APIs do Diretório - v1.3
version: 1
modified: 2022-10-27T12:03:54.410Z
url: /spaces/OF/pages/17377863/Informa+es+Gerais+-+APIs+do+Diret+rio+-+v1.3
---

O **Diretório Central do Open Finance Brasil**pode ser acessado tanto via interface gráfica quanto por meio de integração por APIs.Para acessar as APIs do Diretório, verifique o item 10 do guia operacional do Diretório Central - “Obtendo um token de acesso para acessar as APIs do Diretório”. O guia está disponível na sessão **“Diretrizes Técnicas do Diretório”**.Para entender como usar cada API, leia a especificação do Swagger da API do Diretório disponível nesse link ([https://github.com/OpenBanking-Brasil/specs-directory/blob/main/openapi.yaml](https://github.com/OpenBanking-Brasil/specs-directory/blob/main/openapi.yaml) ).

---

# APIs do Diretório > v1.3 - APIs do Diretório > Informações Técnicas - APIs do Diretório - v1.3

---
id: 17377888
title: Informações Técnicas - APIs do Diretório - v1.3
version: 1
modified: 2022-10-27T12:03:54.638Z
url: /spaces/OF/pages/17377888/Informa+es+T+cnicas+-+APIs+do+Diret+rio+-+v1.3
---

[Abrir informação técnica](https://openbanking-brasil.github.io/openapi/swagger-apis/central-directory/)no100%hide285013

---

# MISP > 01. Sistemas operacionais suportados e considerações sobre versões da plataforma a serem utilizadas

---
id: 117080089
title: 01. Sistemas operacionais suportados e considerações sobre versões da plataforma a serem utilizadas.
version: 1
modified: 2023-06-06T12:46:35.953Z
url: /spaces/OF/pages/117080089/01.+Sistemas+operacionais+suportados+e+considera+es+sobre+vers+es+da+plataforma+a+serem+utilizadas.
---

O participante deve observar a necessidade de manter pacotes de sistema operacional atualizados, seguindo as boas práticas de um programa de patch management, conforme política interna e manual de segurança do Open Finance Brasil.No que se refere a versões da plataforma MISP, recomenda-se a utilização de até 5 versões (considerando o *revision* da versão) anteriores a versão atual disponibilizada no repositório oficial da ferramenta.
## 1.1-Utilizar-versão-Linux-LTS 1.1 Utilizar versão Linux LTS
Dentro do universo do software livre e de projetos de código aberto, como distribuições Linux, frameworks e IDEs de desenvolvimento, existe a demanda por programas com estabilidade garantida por meses ou até anos. Tal exigência gerou mudanças no ciclo de vida útil de algumas aplicações, que lançaram “versões LTS (Long Term Suport)”.As distribuições Linux com suporte de longo prazo exaltam a importância dos três pilares da Segurança da Informação.
- Confidencialidade é a garantia de que a informação será restrita e disponível exclusivamente para os usuários autorizados;
- Integridade é a preservação das informações em seu último estado;
- Disponibilidade define a disposição dos dados sempre que solicitados pelos colaboradores.
Recomendamos sempre utilizar uma distribuição Linux LTS como software básico.
## 1.2-Instalação-e-Hardening-da-Instância-dos-Participantes 1.2 Instalação e Hardening da Instância dos Participantes
É obrigatória a aplicação e manutenção de Hardening na instância do participante, observando a política de segurança da instituição e a regulamentação vigente.Recomenda-se fortemente que a instalação das instâncias MISP no ambiente dos participantes siga o padrão mínimo de Hardening descrito nos documentos de orientação disponibilizados pelo [http://CERT.br](http://CERT.br) em [https://cert.br/misp/](https://cert.br/misp/) - Tópico Passo-a-Passo de Instalação e Configuração de uma Instância MISP.Os exemplos disponibilizados na documentação supracitada referem-se à instalação em sistema operacional Ubuntu, entretanto deve ser observado o mesmo padrão mínimo de segurança em outros sistemas operacionais.Recomenda-se ainda a instalação do sistema operacional Linux/Unix com a mídia original disponibilizada pelo fabricante, uma vez que a utilização de imagens disponibilizadas na internet pode acarretar vulnerabilidades desconhecidas ou pré-existentes na mídia utilizada.

---

# MISP > 02. Padrão de Conectividade entre os participantes e a estrutura de governança

---
id: 117243910
title: 02. Padrão de Conectividade entre os participantes e a estrutura de governança
version: 1
modified: 2023-06-06T12:47:00.525Z
url: /spaces/OF/pages/117243910/02.+Padr+o+de+Conectividade+entre+os+participantes+e+a+estrutura+de+governan+a
---

Toda conectividade entre as instâncias MISP dos participantes e a estrutura de governança do Open Finance Brasil deve ser realizada obrigatoriamente por https e com protocolo conforme descrito no Manual de Segurança do Open Finance Brasil  (IN 134 ou qualquer uma que venha substitui-la).De forma a garantir maior segurança ao processo, é recomendado o uso do HSTS (HTTP Strict Transport Security).
## 2.1-Certificado-Digital 2.1  Certificado Digital
O MISP preconiza pelo uso de conexões em https com o uso de um certificado digital válido.Os certificados digitais emitidos para uso no MISP devem estar em conformidade com as boas práticas de TLS, conforme descrito no Manual de Segurança do Open Finance Brasil (IN 134 ou qualquer uma que venha substitui-la), sendo emitido por uma autoridade certificadora pública.  Não haverá exigências quanto ao tipo de certificado digital a ser utilizado, mas esse deverá ser compatível com os modelos de validação do domínio no campo (SAN – Subject Alternative Name).Não é permitida a utilização de certificados auto assinados entre os participantes do MISP Open Finance Brasil.
## 2.2-Armazenamento-do-Certificado-Digital 2.2  Armazenamento do Certificado Digital
O meio de armazenamento da chave privada utilizado pelo titular assegura, por meios técnicos e procedimentais adequados, no mínimo que:**a)** A chave privada utilizada está suficientemente assegurada pelas proteções que a instituição oferece, sendo armazenada de maneira a protegê-la de terceiros de má-fé;**b)** A chave privada utilizada deve ser eficazmente protegida pelo legítimo titular contra a utilização por terceiros, tendo em vista que temos um duplo fator de segurança: posse da chave privada e senha de utilização da chave;**c)** Não é permitida a recuperação de chaves privadas na renovação dos certificados digitais;**d)** Em nenhuma hipótese será permitida a cópia de segurança de chave privada, mesmo que realizada com o consentimento do respectivo titular;**h)** As chaves privadas serão utilizadas apenas durante período de validade dos certificados correspondentes. As correspondentes chaves públicas podem ser utilizadas durante todo o período determinado pela legislação aplicável, para a verificação das assinaturas geradas durante o prazo de validade dos respectivos certificados.
## 2.3-Cuidados-com-Firewall,-WAF-e-Anti-DDoS-Corporativos 2.3  Cuidados com Firewall, WAF e Anti-DDoS Corporativos
A instância MISP precisa ser mantida atualizada e potencialmente terá em seus eventos payloads maliciosos (malware, URLs de phishing e IoCs variados).É imprescindível que:
- A instância MISP possa acessar a Internet, principalmente os servidores de atualização do sistema operacional e as atualizações da plataforma;
- O WAF corporativo ou proxy reverso (se houver) não interfira no tráfego do MISP;
- Ferramentas Anti-DDoS não devem classificar acessos de instâncias parceiras como ataques.
O participante deverá observar o uso de qualquer ferramenta de inspeção de tráfego em especial TLS/SSL, pois esses podem interferir no envio e recebimento de eventos.Referência:[https://cert.br/misp/tutorial-ubuntu/](https://cert.br/misp/tutorial-ubuntu/)

---

# MISP > 03. Meios para solicitação de utilização da instância compartilhada

---
id: 116949042
title: 03. Meios para solicitação de utilização da instância compartilhada
version: 1
modified: 2023-06-06T12:50:02.211Z
url: /spaces/OF/pages/116949042/03.+Meios+para+solicita+o+de+utiliza+o+da+inst+ncia+compartilhada
---

## 3.1-Solicitação-de-credenciais 3.1  Solicitação de credenciais
O processo de credenciamento de um participante para troca de eventos relacionados ao Open Finance será centralizado na estrutura de governança do Open Finance Brasil.Novas solicitações de acesso devem ser enviadas para o escritório de segurança da estrutura de governança do Open Finance Brasil através de abertura de chamado no Service Desk.
## 3.2-Informações-necessárias-para-a-participação-–-Participante-com-estrutura-própria-de-MISP 3.2  Informações necessárias para a participação – Participante com estrutura própria de MISP
Os participantes devem enviar para a estrutura de governança as seguintes informações:
- ORGNAME: < Nome Fantasia do participante>
- CNPJ: <CNPJ do Participante>
- UUID da ORGNAME: <Valor encontrado na instância MISP>
- URL do MISP da ORGNAME: < URL HTTPS do MISP da organização>
- Endereço IP da instância MISP
- Descrição da organização: <Texto livre de descrição da organização>
- Authkey do SYNC USER: <Código do usuário criado para as conexões de PUSH e PULL do MISP

## 3.3-Envio-de-informações-necessárias-para-a-participação-–-Participante-que-usará-a-instância-compartilhada 3.3  Envio de informações necessárias para a participação – Participante que usará a instância compartilhada
Os participantes devem enviar para a estrutura de governança as seguintes informações:
- ORGNAME: < Nome Fantasia do participante>
- CNPJ: <CNPJ do Participante>
- Range de IPs de saída para a internet, necessário para liberação de acesso à instância compartilhada
- Descrição da organização: <Texto livre de descrição da organização>
- Nome, e-mail e telefone dos colaboradores que terão acesso à instância – máximo de 3 usuários por organização.

## 3.4-Inclusão,-alteração-ou-exclusão-no-ambiente-de-produção 3.4  Inclusão, alteração ou exclusão no ambiente de produção
Ao ter a participação aprovada, a entrada do participante será anunciada pelo escritório de segurança da estrutura de governança do Open Finance Brasil através da plataforma MISP por meio de um evento com as seguintes características:
| Data | <data da inclusão> |
| Distribution | <Nome do Sharing Group> |
| Threat Level | Undefined |
| Share Info | Inclusão/alteração/exclusão de novo participante |
| Tags | TLP GREEN |
| Attribute | Categoria: Targeting data, Tipo: target-org: <nome da instituição> |
| Attribute | Categoria: Internal Reference, Tipo: text: <UUID> |
| Attribute | Categoria: Internal Reference, Tipo: text: <ORGNAME> |
| Attribute | Categoria: Network activity, Tipo: url: <endereço> |
| Attribute | Categoria: Network activity, Tipo: IP: <endereço> Obs.: |

## 3.5-Questões-de-liberação-em-firewall 3.5  Questões de liberação em firewall
Para que seja possível haver comunicação entre a instância MISP do participante com a instância da estrutura de governança, será necessário que o participante libere em seus firewalls, atividade que será executada no momento da integração com as informações sendo compartilhadas através de e-mail, para o contato de segurança previamente registrado no diretório do Open Finance

---

# MISP > 04. Papéis e Responsabilidades

---
id: 117637132
title: 04. Papéis e Responsabilidades
version: 1
modified: 2023-06-06T12:49:37.786Z
url: /spaces/OF/pages/117637132/04.+Pap+is+e+Responsabilidades
---

## 4.1-Participante 4.1  Participante
O participante deverá compartilhar os eventos de incidentes e seus indicadores de comprometimento, conforme descrito no Manual de Segurança do Open Finance Brasil (IN 134 ou qualquer uma que venha substitui-la).O compartilhamento de eventos deverá ser realizado de forma centralizada na estrutura de governança do Open Finance Brasil, por meio de Sharing Groups.Os eventos observados em empresas terceiras contratadas pela instituição participante também deverão ser compartilhados.Entende-se como eventos:
- Incidentes internos da instituição ou terceiros contratados ligados à arquitetura do Open Finance Brasil;
- Riscos cibernéticos com a finalidade de fraudar ou capturar credenciais de clientes do Open Finance;
- Páginas de phishing relacionadas com o ecossistema Open Finance Brasil;
- Ataques de negação de serviço;
- Dentre outros que a instituição julgar relevante.

## 4.2-Outras-entidades-não-reguladas-pelo-Banco-Central-e-Associações-do-Mercado-Financeiro 4.2  Outras entidades não reguladas pelo Banco Central e Associações do Mercado Financeiro
É permitida a participação de associações com poder de voto no Conselho Deliberativo do Open Finance Brasil no compartilhamento dos incidentes e indicadores de comprometimento.A participação de outras instituições e times de resposta a incidentes neste compartilhamento deverá ser aprovada pelo Conselho Deliberativo.
## 4.3-Da-estrutura-de-governança-do-Open-Finance-Brasil 4.3 Da estrutura de governança do Open Finance Brasil

- 4.3.1 Escritório de Segurança Monitorar os eventos e responder a incidentes de segurança relacionados com o ecossistema, através da implementação e gestão de um Security Operations Center (SOC), conforme descrito na política de segurança cibernética e plano de prevenção de resposta a incidentes. Providenciar a manutenção da plataforma MISP. Participar do compartilhamento de eventos de segurança, publicando e consumindo os indicadores de comprometimento. Controlar os acessos à plataforma MISP, solicitados por meio de chamados enviados ao Service Desk. Produzir métricas sobre a utilização da plataforma pelos participantes.

- 4.3.2 Área de Tecnologia do Open Finance Brasil Responsável pela operação da infraestrutura em que o ambiente do MISP estiver hospedado. Garantir a atualização do sistema operacional e do banco de dados; Garantir a execução dos backups.

---

# MISP > 05. Definição de objetos a serem compartilhados - taxonomias e atributos

---
id: 117080118
title: 05. Definição de objetos a serem compartilhados / taxonomias e atributos
version: 1
modified: 2023-06-06T12:50:27.349Z
url: /spaces/OF/pages/117080118/05.+Defini+o+de+objetos+a+serem+compartilhados+taxonomias+e+atributos
---

## 5.1-Taxonomia 5.1  Taxonomia
A taxonomia permite expressar o mesmo vocabulário entre um conjunto distribuído de usuários e organizações.As TAGS no MISP são um conjunto de bibliotecas taxonômicas comuns para marcar, classificar e organizar informações. Ao publicar um evento no MISP é muito importante que se utilize de TAGs abaixo indicadas.
- TLP (Obrigatória) - Será utilizado Traffic Lights Protocol (TLP) para definição do nível de privacidade dos eventos compartilhados, conforme padrão definido pelo Forum of Incident Response Security Teams (FIRST). As definições do padrão estão disponíveis em https://www.first.org/tlp/docs/tlp-v1-pt-br.pdf
- ECSIRT (Complementar) – Será utilizado o padrão de classificação de incidentes definido pela ECSIRT.NET ( http://www.ecsirt.net ) e enriquecido com Intel-MQ.
- RSIT (Complementar) - Será utilizada o padrão estabelecido pela Reference Security Incident Taxonomy Working Group como elemento indicativos para a classificação de incidentes cibernéticos https://github.com/enisaeu/Reference-Security-Incident-Taxonomy-Task-Force
- Taxonomia própria Open Finance (Complementar) – Os incidentes e eventos não contemplados nas taxonomias RSIT e ECSIRT poderão ser inclusos futuramente, se necessário.

## 5.2-Sharing-Groups 5.2  Sharing Groups
O padrão Sharing Group compartilha o evento apenas com os membros definidos no grupo. Grupos de compartilhamento no MISP são uma maneira mais granular de criar listas de distribuição reutilizáveis para eventos/atributos que permitem que os usuários incluam organizações de sua própria instância (organizações locais), bem como organizações de instâncias diretas ou indiretamente conectadas (organizações externas).Sharing Group será a distribuição oficial e obrigatória a ser utilizada entre as instituições cadastradas para o compartilhamento de eventos do Open Finance Brasil.O sharing group oficial do Open Finance Brasil terá como nome, “Open Finance Brasil” e seu UUID será disponibilizado em tempo de configuração para cada instituição participante.O cadastramento e gestão do sharing group está descrito na sessão Meios para solicitação de utilização da instância compartilhada.
## 5.3-Definição-de-itens-mínimos-para-publicação-de-1-evento-MISP 5.3  Definição de itens mínimos para publicação de 1 evento MISP
A publicação de um evento é algo relativamente simples no MISP e esse documento visa definir alguns padrões de preenchimento e utilização do mesmo.
| Date: | Data de ocorrência do evento |
| Distribuition: | Sharing Group - Open Finance Brasil |
| Threat level: | Seguir classificação do campo conforme entendimento de risco da instituição |
| Analysis: | Estágio atual em que se encontra o evento Initial – Ongoing - Completed |
| Event Info: | <Tipo de incidente>: [Instituição/Alvo] - <referência> Exemplos: PHISHING: [IF NOME A] - http://assineopenbanking.ru/teste CERTIFICADO: [IF NOME A] - Revogado por comprometimento RANSOMWARE: [IF NOME A] - ataque interno identificado |
| TAGS | Vide definições de Taxonomia acima |
| Attribute | Vide exemplos abaixo |
Seguem alguns exemplos de atributos que podem ser usados na publicação de um evento.
| Attribute | Categoria: Targeting data, Tipo: target-org: <nome da instituição> |
| Attribute | Categoria: Network activity, Tipo: url: <endereço> |
| Attribute | Categoria: Network activity, Tipo: others: <Número de série do certificado> |

---

# MISP > 06. Continuidade da operação - Meio alternativo para comunicação de incidentes

---
id: 117309462
title: 06. Continuidade da operação / Meio alternativo para comunicação de incidentes
version: 1
modified: 2023-06-06T12:50:59.032Z
url: /spaces/OF/pages/117309462/06.+Continuidade+da+opera+o+Meio+alternativo+para+comunica+o+de+incidentes
---

Para a situação de indisponibilidade do MISP do Open Finance Brasil ou impossibilidade do participante de comunicar seus incidentes através da plataforma, o meio alternativo de comunicação de incidentes de segurança será através do Service Desk, com o registro do incidente categorizado como INCIDENTE-SEGURANCA DA INFORMAÇAO-NOTIFICAÇÃO, que deverá ser configurada para notificar todos os participantes e o Banco Central, quando houver registro ou atualização da ocorrência.

---

# MISP > Controle de Versão - [MISP]

---
id: 117538817
title: Controle de Versão - [MISP]
version: 1
modified: 2023-06-06T12:46:09.765Z
url: /spaces/OF/pages/117538817/Controle+de+Vers+o+-+MISP
---

| Versão | Data | Resumo das Alterações |
| Draft - 1.0 | | Versão inicial do Guia de boas práticas para implantação e uso do MISP no ecossistema Open Finance Brasil, para aprovação no GT de Segurança |
| Final - 1.0 | | Versão final, com ajustes solicitados pelo time do Banco Central. |
| Final 1.1 – Sanitizada | | Retiradas informações técnicas. |
| Final 1.2 – Sanitizada | | Substituição Open Banking por Open Finance |

---

# Motor de Qualidade de Dados > FAQ - MQD

---
id: 362579143
title: FAQ - MQD
version: 3
modified: 2024-04-17T17:53:27.473Z
url: /spaces/OF/pages/362579143/FAQ+-+MQD
---

**O que significa a sigla M.Q.D.?**M.Q.D. é a sigla para Motor de Qualidade de Dados, ferramenta de código aberto que avalia a qualidade dos dados que são compartilhados entre os participantes do Open Finance, assegurando assim a integridade das informações.**Qual é o escopo de endpoints que o MQD vai receber?**Os endpoints suportados pelo MQD podem ser vistos na página abaixo:Tabela de endpoints validados pelo Motor de Qualidade de Dados (MQD) - Draft - Área do Desenvolvedor - Open Finance Brasil - Área do Desenvolvedor (atlassian.net)**Temos a necessidade de teste funcional ou certificação específica dos participantes para o MQD?**Será disponibilizado um ambiente Sandbox seguro para que as instituições possam realizar testes funcionais da aplicação antes de entrar em produção.**Quais são os padrões de certificado de segurança que precisam ser adotados para se instalar o MQD?**MQD utiliza as práticas de confiabilidade e segurança do ecossistema de finanças abertas, incluindo uso de certificados para ICP-Brasil, para conexão mTLS e fluxo de segurança de “client_credentials” com token de acesso **A instalação do MQD e obrigatória?**Sim, seguindo o cronograma aprovado pelo GT de Qualidade de Dados.**Como validar a data da request?**O Body é dinâmico (é o mesmo response obtido da TRANSMISSORA), por isso ele não foi incluso no Swagger.**O report enviado para o servidor central deverá conter todos os requests de um x intervalo de tempo, ou caso alguns dados ainda estejam em processamento poderão ser enviados na próxima janela?**Esse relatório conterá todos os relatórios que estão validados corretamente, caso existam itens a serem validados na memória, estes serão enviados no próximo envio.**A Instituição Financeira precisa estar com a organization id registrada em algum lugar pro getJWKToken?**O cliente precisa de dois IDs: 
1. ID da RECEPTORA é configurado coo variable de ambiente na configuração do container
2. ID da TRANSMISORA, que precisa ser incluso como Header no request
**Temos cenários com retornos de grandes payloads (por exemplo contas). O Motor de qualidade de Dados está preparado para lidar com esses retornos grandes? Existe algum limite de tamanho de payload para o MQD, pensando inclusive na Mensageria interna do MQD, ela suportará mensagens grandes?**Hoje não há limite para o Motor de Qualidade de Dados, tanto no tamanho quanto na quantidade de mensagens. Mas ainda recomendamos o monitoramento constante do contêiner da aplicação, pois dependendo da carga entregue será necessário aumentar os recursos (RAM e CPU) para processar adequadamente todas as mensagens.**Hoje não temos acesso ao repositório do Motor de Qualidade de Dados, há um previsão de quando ele será disponibilizado no Github?**O acesso ao repositório do MQD pode ser solicitado através do Portal de Solicitação de Acessos através do link abaixo. [https://openfinancebrasil.atlassian.net/servicedesk/customer/portal/1/group/17](https://openfinancebrasil.atlassian.net/servicedesk/customer/portal/1/group/17) **Estou com uma dúvida que não está explicada nem na documentação neste FAQ. Como faço para fazer perguntas para especialistas em MQD?**Você pode acessar o [canal no Slack do Motor de Qualidade de Dados](https://app.slack.com/client/T02JY7RKQN5/C062L04SW58) para sanar possíveis dúvidas sobre a instalação e funcionamento da feramenta.

---

# Motor de Qualidade de Dados > MDQTroubleshooting - MQD

---
id: 362579195
title: MDQTroubleshooting - MQD
version: 1
modified: 2024-04-08T19:43:32.301Z
url: /spaces/OF/pages/362579195/MDQTroubleshooting+-+MQD
---

Em desenvolvimento.

---

# Motor de Qualidade de Dados > MQD - Documentação da API

---
id: 362578918
title: MQD - Documentação da API
version: 6
modified: 2025-03-27T11:57:22.245Z
url: /spaces/OF/pages/362578918/MQD+-+Documenta+o+da+API
---

A documentação da API no formato OpenAPI se encontra abaixo. O swagger para transmissor e receptor é o mesmo e está incluído na documentação do MQD.

---

# Motor de Qualidade de Dados > Manual de Instalação - MQD

---
id: 362578967
title: Manual de Instalação - MQD
version: 3
modified: 2024-04-08T19:47:02.429Z
url: /spaces/OF/pages/362578967/Manual+de+Instala+o+-+MQD
---

O presente documento fornece orientações para instalação do Motor de Qualidade de Dados nas Instituições Financeiras participantes do Open Finance Brasil.11falsenonelistfalse
# Instalação
O primeiro passo é clonar o código do repositório (disponível no Github) para a sua pasta local.Em seguida, valide se o clone foi realizado corretamente em sua pasta local.Acesse a pasta do código criada localmente.Após acessar a pasta, é necessário compilar e criar a imagem que será utilizada pelo Docker para o container onde o Motor de Qualidade de Dados estará alocado.A seguir, valide se a imagem foi criada corretamente.Modifique as variáveis ​​de ambiente de acordo com as necessidades no arquivo:
### Variáveis de ambiente

| Nome | Descrição | Valores |
| --- | --- | --- |
| API_PORT | Porta que será usada para expor os endpoints da API | ":" + porta |
| SERVER_ORG_ID | ID da organização da instituição financeira Existem 2 parâmetros de configuração, um enviado no cabeçalho e outro como parte da configuração da aplicação (variável de ambiente).  A configuração como variável de ambiente deve indicar o ID da organização do IF onde o motor está sendo instalado (ex.: ID da Instituição Financeira no Diretório Central) | Organisation Id Válido |
| REPORT_EXECUTION_WINDOW | Indica a janela de execução para envio de relatórios, é um campo opcional, caso não esteja definido seu valor será carregado automaticamente | > 0, < 60 |
| REPORT_EXECUTION_NUMBER | Indica a quantidade de relatórios que devem ser processados ​​antes do envio, caso a quantidade de relatórios atinja o limite, o relatório é enviado automaticamente e o timer da janela de tempo é reiniciado é um campo opcional, caso não esteja definido seu valor será carregado automaticamente | >0, < 2000000 |
| ENVIRONMENT | Indica o ambiente em que o aplicativo está sendo instalado | PROD SANDBOX DEV |
| LOGGING_LEVEL | Indica o nível de rastreio que será utilizado na aplicação | DEBUG INFO WARNING ERROR FATAL |
| APPLICATION_MODE | Indica a forma como será executada a aplicação, isso dependerá se se trata de uma instituição do tipo transmissora ou receptora. A obrigação apenas define a instalação como TRANSMISSOR, mas se desejar instalar em ambos os modos (RECEPTORA / TRANSMISSORA) será necessário ter 2 instalações. | TRANSMITTER RECEIVER |
| PROXY_URL | Indica a url onde será encontrado o Proxy que estabelece conexão segura com o servidor. | URL válida |

### Volumes

| Volume | Descrição |
| --- | --- |
| /etc/nginx/conf.d/default.conf | Volume do arquivo de configuração NGINX deve ser modificado para utilizar a configuração necessária de acordo com o ambiente onde será instalado ./proxy/default.prd.conf ./proxy/default.sandbox.conf ./proxy/default.dev.conf |
| /etc/ssl | Volumen quie indica la carpeta que contiene los archivos de certificados de acuerdo al archivo de configuracion /etc/ssl/client.crt /etc/ssl/client.crt Caso os nomes sejam diferentes do configurado, esses nomes podem ser modificados no arquivo/caminho específico |
Por fim, use o Docker Compose para iniciar a aplicação do Motor de Qualidade de Dados.Em seguida, execute o comando para enviar um request de teste a API do Motor de Qualidade de Dados.**Importante!**Hoje não há limite para o MQD, tanto no tamanho quanto na quantidade de mensagens. Mas ainda recomendamos o monitoramento constante do contêiner da aplicação, pois dependendo da carga entregue será necessário aumentar os recursos (RAM e CPU) para processar adequadamente todas as mensagens.
# Configuração
Para integrar a validação de dados ao Motor de Qualidade de Dados, é necessário atualizar os serviços que deseja validar conforme fluxo mostrado abaixo.Para isso é necessário consumir a API conforme especificação disponível em [mqd-client/docs/specification/mqd-client-openapi.yml at main · OpenBanking-Brasil/mqd-client (github.com)](https://github.com/OpenBanking-Brasil/mqd-client/blob/main/docs/specification/mqd-client-openapi.yml), gerando assim uma nova solicitação ao obter a resposta da TRANSMISSORA.Para a tratativa de erros no processamento do MQD ou para envio do request para ele, espera-se conseguir enviar 100% das transações para processamento, porém, podem ocorrer pequenas perdas que não afetariam os resultados. Por esta razão recomendamos uma abordagem padrão incluindo 3 tentativas no momento da integração.O relatório pode ser enviado minutos ou horas depois de acontecer, porém deve-se levar em consideração o seguinte:
1. O mecanismo enviará os resultados da validação a cada 15 minutos, portanto o melhor cenário é que o envio da transação não ultrapasse esta janela de tempo.
2. Evite acumular transações a serem enviadas ao MQD, o que pode sobrecarregar os requisitos de processamento e, em última análise, causar a ocorrência de mais erros.
 Uma política que pode funcionar seria de 3 tentativas:
- 10 segundos
- 30 segundos
- 1 minuto
Jitter: insira um valor aleatório (+/-) em segundos, evitando que todas as novas tentativas aconteçam ao mesmo tempo.Se a % de solicitações que necessitam de nova tentativa for muito alta, será necessário analisar os tipos de problemas e iniciar um cenário de melhoria.É necessário incluir as informações do cabeçalho nesta nova solicitação: 
| Variável | Descrição | Exemplo |
| --- | --- | --- |
| serverOrgId | Para Instituições Receptoras: Identificador da TRANSMISSORA onde a informação foi solicitada Para Instituições Transmissoras: Identificador da RECEPTORA que solicitou a informação Para eliminar a necessidade de criar diferentes endpoints para RECEPTORA e TRANSMISSORA e incluir parâmetros diferentes, existe um único parâmetro geral serverOrgId , que no caso de instalação como TRANSMISORA, será o id da organização que está solicitando o informações (clientOrgID) | c73bcdcc-2669-4bf6-81d3-e4ae73fb11fd |
| endpointName | Nome do endpoint que foi solicitado, como descrito na documentação , sem incluir as informações dos parâmetros dentro da URI | /accounts/v2/accounts/{accountId} |
| versionHeader | Validar diferentes versões da API em períodos de convivência Esta variável é opcional | 2.0.0 |

---

# Motor de Qualidade de Dados > Tabela de endpoints validados pelo Motor de Qualidade de Dados (MQD)

---
id: 619413971
title: Tabela de endpoints validados pelo Motor de Qualidade de Dados (MQD)
version: 2
modified: 2025-10-03T16:49:14.817Z
url: /spaces/OF/pages/619413971/Tabela+de+endpoints+validados+pelo+Motor+de+Qualidade+de+Dados+MQD
---

Abaixo a lista dos endpoints validados pelo Motor de Qualidade de Dados para cada MVP. Ressalta-se que apenas os métodos “GET” serão validados.none
# Dados Abertos

## Títulos de Capitalização - 1.0.1

| /opendata-capitalization/v1/bonds |
| --- |

## Investimentos - 1.0.0

| /opendata-investments/v1/funds |
| /opendata-investments/v1/bank-fixed-incomes |
| /opendata-investments/v1/credit-fixed-incomes |
| /opendata-investments/v1/variable-incomes |
| /opendata-investments/v1/treasure-titles |

## Câmbio - 1.0.0

| /opendata-exchange/v1/online-rates |
| /opendata-exchange/v1/vet-values |

## Credenciamento - 1.0.0

| /opendata-acquiring-services/v1/personals |
| /opendata-acquiring-services/v1/businesses |

## Previdência - 1.0.1

| /opendata-pension/v1/risk-coverages |
| /opendata-pension/v1/survival-coverages |

## Seguros - 1.0.1

| /opendata-insurance/v1/personals |
| --- |

# Dados do Cliente

## Consentimento - 3.0.1

| /consents/v3/consents/{consentId}/extensions |
| /consents/v2/consents/{consentId} |

## Recursos - 3.0.0

| /resources/v3/resources |

## Dados cadastrais - 2.1.0

| /customers/v2/personal/identifications |
| /customers/v2/business/qualifications |
| /customers/v2/business/financial-relations |
| /customers/v2/personal/financial-relations |
| /customers/v2/business/identifications |
| /customers/v2/personal/qualifications |

## Cartão de Crédito - 2.3.1

| /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions |
| /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions |
| /credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits |
| /credit-cards-accounts/v2/accounts/{creditCardAccountId} |
| /credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills |
| /credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current |
| /credit-cards-accounts/v2/accounts |

## Contas - 2.4.1

| /accounts/v2/accounts/{accountId}/transactions-current |
| /accounts/v2/accounts/{accountId}/balances |
| /accounts/v2/accounts |
| /accounts/v2/accounts/{accountId} |
| /accounts/v2/accounts/{accountId}/transactions |
| /accounts/v2/accounts/{accountId}/overdraft-limits |

## Operações de Crédito - Empréstimos - 2.2.0

| /loans/v2/contracts/{contractId}/scheduled-instalments |
| /loans/v2/contracts |
| /loans/v2/contracts/{contractId}/payments |
| /loans/v2/contracts/{contractId} |
| /loans/v2/contracts/{contractId}/warranties |

## Operações de Crédito - Financiamento - 2.2.0

| /financings/v2/contracts/{contractId}/scheduled-instalments |
| /financings/v2/contracts/{contractId}/payments |
| /financings/v2/contracts |
| /financings/v2/contracts/{contractId} |
| /financings/v2/contracts/{contractId}/warranties |

## Operações de Crédito - Adiantamento a Depositantes - 2.2.0

| /unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments |
| /unarranged-accounts-overdraft/v2/contracts/{contractId} |
| /unarranged-accounts-overdraft/v2/contracts |
| /unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties |
| /unarranged-accounts-overdraft/v2/contracts/{contractId}/payments |

## Operações de Crédito - Direitos Creditórios Descontados - 2.2.0

| /invoice-financings/v2/contracts/{contractId}/warranties |
| /invoice-financings/v2/contracts/{contractId}/payments |
| /invoice-financings/v2/contracts/{contractId} |
| /invoice-financings/v2/contracts/{contractId}/scheduled-instalments |
| /invoice-financings/v2/contracts |

## Investimentos - Renda Fixa Crédito - 1.0.2

| /credit-fixed-incomes/v1/investments |
| /credit-fixed-incomes/v1/investments/{investmentId} |
| /credit-fixed-incomes/v1/investments/{investmentId}/balances |
| /credit-fixed-incomes/v1/investments/{investmentId}/transactions |
| /credit-fixed-incomes/v1/investments/{investmentId}/transactions-current) |

## Investimentos - Renda Fixa Bancária - 1.0.3

| /bank-fixed-incomes/v1/investments |
| /bank-fixed-incomes/v1/investments/{investmentId} |
| /bank-fixed-incomes/v1/investments/{investmentId}/balances |
| /bank-fixed-incomes/v1/investments/{investmentId}/transactions |
| /bank-fixed-incomes/v1/investments/{investmentId}/transactions-current) |

## Investimentos - Renda Variável - 1.2.0

| /variable-incomes/v1/investments |
| /variable-incomes/v1/investments/{investmentId} |
| /variable-incomes/v1/investments/{investmentId}/balances |
| /variable-incomes/v1/investments/{investmentId}/transactions |
| /variable-incomes/v1/investments/{investmentId}/transactions-current) |
| /variable-incomes/v1/investments/{investmentId}/broker-notes/{brokerNoteId} |

## Investimentos - Títulos do Tesouro Direto - 1.0.1

| /treasure-titles/v1/investments |
| /treasure-titles/v1/investments/{investmentId} |
| /treasure-titles/v1/investments/{investmentId}/balances |
| /treasure-titles/v1/investments/{investmentId}/transactions |
| /treasure-titles/v1/investments/{investmentId}/transactions-current) |

## Investimentos - Fundos de Investimento - 1.0.2

| /funds/v1/investments |
| /funds/v1/investments/{investmentId} |
| /funds/v1/investments/{investmentId}/balances |
| /funds/v1/investments/{investmentId}/transactions |
| /funds/v1/investments/{investmentId}/transactions-current) |

## Câmbio - 1.0.0

| /exchanges/v1/operations |
| /exchanges/v1/operations/{operationId} |
| /exchanges/v1/operations/{operationId}/events |

# Portabilidade de Crédito

## Portabilidade de Crédito - 1.0.0

| /credit-portability/v1/portabilities/{portabilityId}/account-data |
| /credit-portability/v1/credit-operations/{contractId}/portability-eligibility |
| /credit-portability/v1/portabilities/{portabilityId} |

---

# Motor de Qualidade de Dados > MDQ - Especificação Técnica > MDQ - Arquitetura > MDQ - Proxy reverso

---
id: 362578698
title: MDQ - Proxy reverso
version: 3
modified: 2025-03-27T12:00:05.523Z
url: /spaces/OF/pages/362578698/MDQ+-+Proxy+reverso
---

Para a versão 2.0 do Motor de Qualidade de Dados (MQD) foi implementada uma camada intermediária encarregada de estabelecer uma conexão segura (mTLS) utilizando os certificados da instituição.Neste arquivo docker compose, incluímos um exemplo de proxy reverso usando NGINX como tecnologia, mas qualquer ferramenta pode ser usada conforme a conveniência da Instituição.Será necessário que o proxy tenha a capacidade de rodar em modo "transparente", isso significa que a mensagem a ser enviada ao servidor MQD deve ser a mesma recebida em seus endpoints (cabeçalho e corpo).Da mesma forma, este proxy terá acesso aos arquivos de certificados (Cert e key) da instituição financeira para permitir o estabelecimento de uma conexão segura com o servidor.
#### Endpoints

| Endpoint | Path | Proxy - Produção | Proxy - Sandbox |
| --- | --- | --- | --- |
| - | /token | https://mqd.openfinancebrasil.org.br/token | https://mqd.sandbox.openfinancebrasil.org.br/token |
| - | /report | https://mqd.openfinancebrasil.org.br/report | https://mqd.sandbox.openfinancebrasil.org.br/report |
| - | /settings | https://mqd.openfinancebrasil.org.br/settings | https://mqd.sandbox.openfinancebrasil.org.br/settings |

---

# Motor de Qualidade de Dados > MDQ - Especificação Técnica > MDQ - Arquitetura > MDQ - Diagramas de sequência > MDQ - Fluxo da Receptora

---
id: 362578884
title: MDQ - Fluxo da Receptora
version: 4
modified: 2025-03-27T12:01:22.225Z
url: /spaces/OF/pages/362578884/MDQ+-+Fluxo+da+Receptora
---

Este fluxo representa o processo de enfileramento de messagens e integração com o MQD na visão da RECEPTORA.
## Passos

| Passo | Participante | Descrição |
| --- | --- | --- |
| 1. | SERVICE | O serviço gera uma solicitação para a API da TRANSMISORA |
| 2. | API | A API processa a solicitação recebida |
| 3. | API | A API retorna um resultado para a solicitação |
| 4. | SERVICE | O Serviço gera uma nova requisição, tendo como base a Resposta da TRANSMISORA, incluindo no cabeçalho o valor de [EndpointName] e [serverOrgId] que indica o ID do transmissor (enviar somente validações de solicitações bem-sucedidas - 2xx) |
| 5. | SERVICE | O serviço envia a nova solicitação para a API do MQD |
| 6. | MQD | MQD Valida se as informações do cabeçalho estão completas e corretas |
| 7. | MQD | MQD encaminha as informações para serem processadas posteriormente |
| 8. | MQD | MQD responde OK se o processo foi bem-sucedido |

### Exemplo de Soliciação da API - MQD

| endpointName | serverOrgId | x-fapi-interaction-id | Corpo |
| --- | --- | --- | --- |
| /loans/v2/contracts/{contractId}/payments Nome do endpoint e deve corresponder à lista de endpoints aceitos | c73bcdcc-2669-4bf6-81d3-e4ae73fb11fd Id da TRANSMISORA | 241e202-e8f0-5f5a-9651-ebc257371e24 valor x-fapi usado durante a transação | Valor retornado como resposta da TRANSMISORA |

---

# Motor de Qualidade de Dados > MDQ - Especificação Técnica > MDQ - Arquitetura > MDQ - Diagramas de sequência > MDQ - Fluxo da Transmissora

---
id: 362578850
title: MDQ - Fluxo da Transmissora
version: 4
modified: 2025-03-27T12:01:11.074Z
url: /spaces/OF/pages/362578850/MDQ+-+Fluxo+da+Transmissora
---

Este fluxo representa o processo de enfileramento de messagens e integração com o MQD na visão da TRANSMISSORA.
## Passos

| Passo | Participante | Descrição |
| --- | --- | --- |
| 1. | SERVICE | O serviço gera uma solicitação para a API da TRANSMISORA |
| 2. | API | A API processa a solicitação recebida |
| 3. | API | A API retorna um resultado para a solicitação |
| 4. | API | A API atualiza a solicitação, incluindo a resposta enviada para a RECEPTORA - Corpo+Cabeçalho - e adicionando oa parâmetros clientOrgID (clientOrgID: OrganisationID (cadastrado no Diretório Central) da Receptora que esta solicitando a informação, este campo deve ser incluso como parte de cabeçalho) - o ID da RECEPTORA - e endpointName ao cabeçalho (enviar somente validações de solicitações bem-sucedidas - 2xx) |
| 5. | API | A API da TRANSMISSORA envia a nova resposta válida para o MQD |
| 6. | MQD | MQD Valida se as informações do cabeçalho estão completas e corretas |
| 7. | MQD | MQD encaminha as informações para serem processadas posteriormente |
| 8. | MQD | MQD responde OK se o processo foi bem-sucedido |

### Exemplo de Soliciação da API - MQD

| endpointName | serverOrgId | x-fapi-interaction-id | Corpo |
| --- | --- | --- | --- |
| /loans/v2/contracts/{contractId}/payments Nome do endpoint e deve corresponder à lista de endpoints aceitos | c73bcdcc-2669-4bf6-81d3-e4ae73fb11fd Id da TRANSMISORA | 241e202-e8f0-5f5a-9651-ebc257371e24 valor x-fapi usado durante a transação | Valor retornado como resposta da TRANSMISORA |

---

# Motor de Qualidade de Dados > MDQ - Especificação Técnica > MDQ - Arquitetura > MDQ - Diagramas de sequência > MDQ - Fluxo de Atualização de Configuração

---
id: 362578786
title: MDQ - Fluxo de Atualização de Configuração
version: 4
modified: 2025-03-27T12:00:35.443Z
url: /spaces/OF/pages/362578786/MDQ+-+Fluxo+de+Atualiza+o+de+Configura+o
---

Este fluxo representa o processo de atualização de configuração.
## Passos

| Passos | Participante | Descrição |
| --- | --- | --- |
| 0. | CONFIGURATION_MANAGER | CONFIGURATION_MANAGER solicita o proxy para o token usando o OrganizationID configurado |
| 1. | PROXY | O proxy solicita o token do servidor usando o OrganizationID enviado no cabeçalho usando uma conexão segura |
| 2. | GATEWAY | O componente valida o ID do cliente e retorna o token se for válido |
| 3. | PROXY | PROXY retorna o token recebido ao cliente |
| 4. | CONFIGURATION_MANAGER | O componente solicita a configuração através do proxy |
| 5. | PROXY | O proxy estabelece uma conexão segura com o servidor e solicita a configuração |
| 6. | GATEWAY | O componente retorna a configuração solicitada |
| 7. | PROXY | O proxy retorna a configuração solicitada ao cliente |
| 8. | CONFIGURATION_MANAGER | O componente valida as versões da configuração obtidas |
| 9. | CONFIGURATION_MANAGER | Se for uma versão diferente da mais recente, o componente solicita a configuração dos diferentes grupos de APIs através do proxy |
| 10. | PROXY | O componente estabelece uma conexão segura e solicita os arquivos de configuração |
| 11. | GATEWAY | O componente valida a existência dos arquivos e se for encontrado, os retorna |
| 12. | PROXY | O proxy retorna as informações recebidas ao cliente |
| 13. | CONFIGURATION_MANAGER | O componente atualiza a configuração localmente |

## Esquema de Definições de Configuração
O objeto recebido pelo cliente no momento da atualização da configuração está definido abaixo.

---

# Motor de Qualidade de Dados > MDQ - Especificação Técnica > MDQ - Arquitetura > MDQ - Diagramas de sequência > MDQ - Fluxo de Envio de Resultados

---
id: 362578754
title: MDQ - Fluxo de Envio de Resultados
version: 4
modified: 2025-03-27T12:00:24.624Z
url: /spaces/OF/pages/362578754/MDQ+-+Fluxo+de+Envio+de+Resultados
---

Este fluxo representa o processo de envio de resultados executado na aplicação
## Passos

| Passos | Participante | Descrição |
| --- | --- | --- |
| 0. | RESULT_PROCESSOR | A cada intervalo definido o Componente inicia seu processo |
| 1. | RESULT_PROCESSOR | O componente solicita ao Validador a lista de resultados a serem processados |
| 2. e 3. | VALIDADOR | Após retornar os resultados, o validador limpa a lista para um novo processo |
| 4. | RESULT_PROCESSOR | O componente gera um novo resumo com a lista de resultados obtidos |
| 5. | RESULT_PROCESSOR | O componente solicita um token de acesso ao proxy do servidor |
| 6. | PROXY | Solicita o token ao servidor utilizando certificados para estabelecer mTLS |
| 7. e 8. | GATEWAY | O Gateway usa as credenciais para validar a ID do Cliente e obtem um token JWT, enviando ao Proxy |
| 9. | PROXY | Proxy retorna as informações recebidas ao cliente |
| 10. | RESULT_PROCESSOR | O componente envia o resumo criado para o servidor usando o token recebido como autorização |
| 11. | PROXY | O proxy estabelece uma conexão segura e envia as informações do relatório ao servidor |
| 12. | GATEWAY | O Gateway valida o acesso ao recurso (MQD_SERVER) com base no token recebido |
| 13. | GATEWAY | Se tudo estiver correto, o componente armazena as informações do relatório com a data de recebimento |
| 14. e 15. | GATEWAY | Gateway retorna a resposta do servidor para o componente Result Processor |

## Esquema de Report Enviado

---

# Motor de Qualidade de Dados > MDQ - Especificação Técnica > MDQ - Arquitetura > MDQ - Diagramas de sequência > MDQ - Fluxo de Validação

---
id: 362578818
title: MDQ - Fluxo de Validação
version: 4
modified: 2025-03-27T12:00:45.013Z
url: /spaces/OF/pages/362578818/MDQ+-+Fluxo+de+Valida+o
---

Este fluxo representa o processo de validação executado na aplicação.
## Passos

| Passos | Participante | Descrição |
| --- | --- | --- |
| 0. | VALIDATOR | O componente de validação carrega regras de validação com base em arquivos JSON de configuração |
| 1., 2. e 3. | MESSAGE_PROCESS_WORKER | O componente Message Process Worker checa a Fila e em seguida solicita e recebe da Fila a lista de tarefas enfileiradas a serem processadas |
| 4. | MESSAGE_PROCESS_WORKER | Para cada uma das mensagens encontradas, o Message Process Worker envia a mensagem para o componente Validação |
| 5. | VALIDATOR | O componente valida se o Endpoint está na lista de endpoints válidos |
| 6. | VALIDATOR | O componente desserializa as informações |
| 7. | VALIDATOR | O componente valida o objeto usando um esquema JSON carregado anteriormente |
| 8. | VALIDATOR | Retorna a resposta de validação ao Worker |
| 9. | MESSAGE_PROCESS_WORKER | As informações do resultado são salvas na memória |

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Endpoints e APIs Legadas > Histórico - Tabela de endpoints aceitos pela PCM

---
id: 43089921
title: Histórico - Tabela de endpoints aceitos pela PCM
version: 22
modified: 2025-11-18T13:54:34.555Z
url: /spaces/OF/pages/43089921/Hist+rico+-+Tabela+de+endpoints+aceitos+pela+PCM
---

# Esta é a documentação legada, e deve ser consultada apenas para fins de histórico. A página atualizada pode ser encontrada aqui:
Endpoints aceitos pela PCM Abaixo a lista dos endpoints aceitas pela PCM para cada categoria de API. Para maiores informações, veja as regras para utilização em Campos Especiais (itens `endpoint` e `additionalInfo`).
## API Private Reports

- accounts /open-banking/accounts/v1/accounts /open-banking/accounts/v1/accounts/{accountId} /open-banking/accounts/v1/accounts/{accountId}/balances /open-banking/accounts/v1/accounts/{accountId}/overdraft-limits /open-banking/accounts/v1/accounts/{accountId}/transactions /open-banking/accounts/v2/accounts /open-banking/accounts/v2/accounts/{accountId} /open-banking/accounts/v2/accounts/{accountId}/balances /open-banking/accounts/v2/accounts/{accountId}/overdraft-limits /open-banking/accounts/v2/accounts/{accountId}/transactions /open-banking/accounts/v2/accounts/{accountId}/transactions-current
- admin /open-banking/admin/v1/metrics /open-banking/admin/v2/metrics
- automatic payments /open-banking/automatic-payments/v1/pix/recurring-payments /open-banking/automatic-payments/v1/pix/recurring-payments/{recurringPaymentId} /open-banking/automatic-payments/v1/pix/recurring-payments/{recurringPaymentId} /open-banking/automatic-payments/v1/recurring-consents /open-banking/automatic-payments/v1/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v1/recurring-consents/{recurringConsentId}
- bank fixed incomes /open-banking/bank-fixed-incomes/v1/investments /open-banking/bank-fixed-incomes/v1/investments/{investmentId} /open-banking/bank-fixed-incomes/v1/investments/{investmentId}/balances /open-banking/bank-fixed-incomes/v1/investments/{investmentId}/transactions /open-banking/bank-fixed-incomes/v1/investments/{investmentId}/transactions-current
- consents /open-banking/consents/v1/consents /open-banking/consents/v1/consents/{consentId} /open-banking/consents/v1/consents/{consentId} /open-banking/consents/v2/consents /open-banking/consents/v2/consents/{consentId} /open-banking/consents/v2/consents/{consentId} /open-banking/consents/v2/consents/{consentId}/extends /open-banking/consents/v2/consents/{consentId}/extends /open-banking/consents/v3/consents /open-banking/consents/v3/consents /open-banking/consents/v3/consents/{consentId} /open-banking/consents/v3/consents/{consentId} /open-banking/consents/v3/consents/{consentId}/extends /open-banking/consents/v3/consents/{consentId}/extensions
- credit cards accounts /open-banking/credit-cards-accounts/v1/accounts /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId} /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/bills /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/bills/{billId}/transactions /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions /open-banking/credit-cards-accounts/v2/accounts /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId} /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current
- credit cards incomes /open-banking/credit-fixed-incomes/v1/investments /open-banking/credit-fixed-incomes/v1/investments/{investmentId} /open-banking/credit-fixed-incomes/v1/investments/{investmentId}/balances /open-banking/credit-fixed-incomes/v1/investments/{investmentId}/transactions /open-banking/credit-fixed-incomes/v1/investments/{investmentId}/transactions-current
- costumers /open-banking/customers/v1/business/financial-relations /open-banking/customers/v1/business/identifications /open-banking/customers/v1/business/qualifications /open-banking/customers/v1/personal/financial-relations /open-banking/customers/v1/personal/identifications /open-banking/customers/v1/personal/qualifications /open-banking/customers/v2/business/financial-relations /open-banking/customers/v2/business/identifications /open-banking/customers/v2/business/qualifications /open-banking/customers/v2/personal/financial-relations /open-banking/customers/v2/personal/identifications /open-banking/customers/v2/personal/qualifications
- discovery /open-banking/discovery/v1/outages /open-banking/discovery/v1/status /open-banking/discovery/v2/outages /open-banking/discovery/v2/status
- enrollments /open-banking/enrollments/v1/consents/{consentId}/authorise /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v1/enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v2/consents/{consentId}/authorise /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/risk-signals
- exchanges /open-banking/exchanges/v1/operations /open-banking/exchanges/v1/operations/{operationId} /open-banking/exchanges/v1/operations/{operationId}/events
- financings /open-banking/financings/v1/contracts /open-banking/financings/v1/contracts/{contractId} /open-banking/financings/v1/contracts/{contractId}/payments /open-banking/financings/v1/contracts/{contractId}/scheduled-instalments /open-banking/financings/v1/contracts/{contractId}/warranties /open-banking/financings/v2/contracts /open-banking/financings/v2/contracts/{contractId} /open-banking/financings/v2/contracts/{contractId}/payments /open-banking/financings/v2/contracts/{contractId}/scheduled-instalments /open-banking/financings/v2/contracts/{contractId}/warranties
- funds /open-banking/funds/v1/investments /open-banking/funds/v1/investments/{investmentId} /open-banking/funds/v1/investments/{investmentId}/balances /open-banking/funds/v1/investments/{investmentId}/transactions /open-banking/funds/v1/investments/{investmentId}/transactions-current
- i nvoice financings /open-banking/invoice-financings/v1/contracts /open-banking/invoice-financings/v1/contracts/{contractId} /open-banking/invoice-financings/v1/contracts/{contractId}/payments /open-banking/invoice-financings/v1/contracts/{contractId}/scheduled-instalments /open-banking/invoice-financings/v1/contracts/{contractId}/warranties /open-banking/invoice-financings/v2/contracts /open-banking/invoice-financings/v2/contracts/{contractId} /open-banking/invoice-financings/v2/contracts/{contractId}/payments /open-banking/invoice-financings/v2/contracts/{contractId}/scheduled-instalments /open-banking/invoice-financings/v2/contracts/{contractId}/warranties
- loans /open-banking/loans/v1/contracts /open-banking/loans/v1/contracts/{contractId} /open-banking/loans/v1/contracts/{contractId}/payments /open-banking/loans/v1/contracts/{contractId}/scheduled-instalments /open-banking/loans/v1/contracts/{contractId}/warranties /open-banking/loans/v2/contracts /open-banking/loans/v2/contracts/{contractId} /open-banking/loans/v2/contracts/{contractId}/payments /open-banking/loans/v2/contracts/{contractId}/scheduled-instalments /open-banking/loans/v2/contracts/{contractId}/warranties
- payments /open-banking/payments/v1/consents /open-banking/payments/v1/consents/{consentId} /open-banking/payments/v1/pix/payments /open-banking/payments/v1/pix/payments/{paymentId} /open-banking/payments/v2/consents /open-banking/payments/v2/consents/{consentId} /open-banking/payments/v2/pix/payments /open-banking/payments/v2/pix/payments/{paymentId} /open-banking/payments/v2/pix/payments/{paymentId} /open-banking/payments/v3/consents /open-banking/payments/v3/consents/{consentId} /open-banking/payments/v3/pix/payments /open-banking/payments/v3/pix/payments/{paymentId} /open-banking/payments/v3/pix/payments/{paymentId} /open-banking/payments/v4/consents /open-banking/payments/v4/consents/{consentId} /open-banking/payments/v4/pix/payments /open-banking/payments/v4/pix/payments/{paymentId} /open-banking/payments/v4/pix/payments/{paymentId} /open-banking/payments/v4/pix/payments/consents/{consentId}
- resources /open-banking/resources/v2/resources /open-banking/resources/v2/resources /open-banking/resources/v3/resources
- security /register /register/{clientId} /token /revocation /introspection /pushed-authorization-request
- treasure titles /open-banking/treasure-titles/v1/investments /open-banking/treasure-titles/v1/investments/{investmentId} /open-banking/treasure-titles/v1/investments/{investmentId}/balances /open-banking/treasure-titles/v1/investments/{investmentId}/transactions /open-banking/treasure-titles/v1/investments/{investmentId}/transactions-current
- unarranged accounts overdraft /open-banking/unarranged-accounts-overdraft/v1/contracts /open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId} /open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId}/payments /open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId}/scheduled-instalments /open-banking/unarranged-accounts-overdraft/v1/contracts/{contractId}/warranties /open-banking/unarranged-accounts-overdraft/v2/contracts /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId} /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/payments /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties
- variable incomes /open-banking/variable-incomes/v1/broker-notes/{brokerNoteId} /open-banking/variable-incomes/v1/investments /open-banking/variable-incomes/v1/investments/{investmentId} /open-banking/variable-incomes/v1/investments/{investmentId}/balances /open-banking/variable-incomes/v1/investments/{investmentId}/transactions /open-banking/variable-incomes/v1/investments/{investmentId}/transactions-current

## API Open Data

- channels /open-banking/channels/v1/banking-agents /open-banking/channels/v1/branches /open-banking/channels/v1/electronic-channels /open-banking/channels/v1/phone-channels /open-banking/channels/v1/shared-automated-teller-machines /open-banking/channels/v2/banking-agents /open-banking/channels/v2/branches /open-banking/channels/v2/electronic-channels /open-banking/channels/v2/phone-channels /open-banking/channels/v2/shared-automated-teller-machines
- accounts /open-banking/opendata-accounts/v1/personal-accounts
- acquiring services /open-banking/opendata-acquiring-services/v1/businesses /open-banking/opendata-acquiring-services/v1/personals
- capitalization /open-banking/opendata-capitalization/v1/bonds /open-banking/opendata-capitalization/v2/bonds
- creditcards /open-banking/opendata-creditcards/v1/business-credit-cards /open-banking/opendata-creditcards/v1/personal-credit-cards
- exchange /open-banking/opendata-exchange/v1/online-rates /open-banking/opendata-exchange/v1/vet-rates /open-banking/opendata-exchange/v1/vet-values
- financings /open-banking/opendata-financings/v1/business-financings /open-banking/opendata-financings/v1/personal-financings
- insurance /open-banking/opendata-insurance/v1/personals /open-banking/opendata-insurance/v2/personals
- investments /open-banking/opendata-investments/v1/bank-fixed-incomes /open-banking/opendata-investments/v1/credit-fixed-incomes /open-banking/opendata-investments/v1/funds /open-banking/opendata-investments/v1/treasure-titles /open-banking/opendata-investments/v1/variable-incomes
- invoice financings /open-banking/opendata-invoicefinancings/v1/business-invoice-financings /open-banking/opendata-invoicefinancings/v1/personal-invoice-financings
- loans /open-banking/opendata-loans/v1/business-loans /open-banking/opendata-loans/v1/personal-loans
- pension /open-banking/opendata-pension/v1/risk-coverages /open-banking/opendata-pension/v1/survival-coverages /open-banking/opendata-pension/v2/risk-coverages /open-banking/opendata-pension/v2/survival-coverages
- unarranged /open-banking/opendata-unarranged/v1/business-unarranged-account-overdraft /open-banking/opendata-unarranged/v1/personal-unarranged-account-overdraft
- products services /open-banking/opendata-accounts/v1/business-accounts /open-banking/opendata-creditcards/v1/business-credit-cards /open-banking/opendata-creditcards/v1/personal-credit-cards /open-banking/opendata-financings/v1/business-financings /open-banking/opendata-financings/v1/personal-financings /open-banking/opendata-loans/v1/business-loans /open-banking/opendata-loans/v1/personal-loans /open-banking/opendata-unarranged/v1/business-unarranged-account-overdraft /open-banking/opendata-unarranged/v1/personal-unarranged-account-overdraft /open-banking/products-services/v1/business-accounts /open-banking/products-services/v1/business-credit-cards /open-banking/products-services/v1/business-financings /open-banking/products-services/v1/business-invoice-financings /open-banking/products-services/v1/business-loans /open-banking/products-services/v1/business-unarranged-account-overdraft /open-banking/products-services/v1/personal-accounts /open-banking/products-services/v1/personal-credit-cards /open-banking/products-services/v1/personal-financings /open-banking/products-services/v1/personal-invoice-financings /open-banking/products-services/v1/personal-loans /open-banking/products-services/v1/personal-unarranged-account-overdraft

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Endpoints e APIs Legadas > Histórico - Documentação da API - PCM > Informações Técnicas - [PCM] Telemetria - v2.1.2 (Visualização Legada)

---
id: 1062174721
title: Informações Técnicas - [PCM] Telemetria - v2.1.2 (Visualização Legada)
version: 4
modified: 2025-09-04T14:35:50.003Z
url: /spaces/OF/pages/1062174721/Informa+es+T+cnicas+-+PCM+Telemetria+-+v2.1.2+Visualiza+o+Legada
---

100%hide82583

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Especificações additionalInfo Descontinuadas > Histórico - Planilha AdditionalInfo

---
id: 806158355
title: Histórico - Planilha AdditionalInfo
version: 7
modified: 2025-11-19T18:42:13.366Z
url: /spaces/OF/pages/806158355/Hist+rico+-+Planilha+AdditionalInfo
---

# Esta é a documentação legada, e deve ser consultada apenas para fins de histórico. A página atualizada pode ser encontrada aqui por domínio:
Especificações por domínio 
| Arquivo | Versão |
| --- | --- |
| | v20 |

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Especificações additionalInfo Descontinuadas > Histórico - Tabela de AdditionalInfo PIX Automático

---
id: 873333409
title: Histórico - Tabela de AdditionalInfo PIX Automático
version: 7
modified: 2025-11-19T18:43:01.239Z
url: /spaces/OF/pages/873333409/Hist+rico+-+Tabela+de+AdditionalInfo+PIX+Autom+tico
---

# Esta é a documentação legada, e deve ser consultada apenas para fins de histórico. A página atualizada pode ser encontrada aqui:
Regras de Obrigatoriedade (additionalInfo) - SV Abaixo a tabela com os campos especiais additionalinfo.
| Nome | Jornada | Regra de preenchimento | Role | Http code | Método | Endpoints | |
| amountType | Consentimento | Valida se o serviço contratado possui maior conversão em relação ao tipo do valor definido, sendo ele fixo ou variável​ ENUM com duas possibilidades: ​ Se não enviando nem ".data.recurringConfiguration.automatic.fixedAmount" e nem ".data.recurringConfiguration.automatic.maximumVariableAmount", “VARIAVEL”; ou ​* Se enviado fixedAmount, “FIXO”; ou Se enviado maximumVariableAmount, “VARIAVEL” Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| authorisationFlow​ | Pagamento | Identifica o fluxo de autorização em que o pagamento foi solicitado​ Deve ser preenchido com a mesma string obtida no ".data.authorisationFlow". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | Todos | POST/PATCH/​GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| cancellationReason​ | Pagamento | Identifica o estado que o pagamento estava quando foi  cancelado​ Preencher com o valor do campo ".cancellation.reason" Deve ser enviado quando em um GET ou POST /payment e o campo status é "CANC" ou em um PATCH /payment (que é a API de cancelamento). | CLIENT | 2xx | POST/PATCH/​GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| cancelledFrom​ | Pagamento | Informa o meio pelo qual foi realizado o cancelamento​ Preencher com o valor do campo ".cancellation.cancelledFrom" Status do pagamento deve ser "CANC" Valores possíveis: INICIADORA, DETENTORA | CLIENT | 2xx | POST/PATCH/​GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| consentId​ | Consentimento Pagamento | Deve ser preenchido com a mesma string obtida no campo ".data.recurringConsentId" ou ".data.recurringconsentId" retornado após a chamada inicial na API "POST /consent". *Ao reportar o uso de um endpoint /token, o identificador único de consentimento só será reportado nos casos em que "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token", uma vez que esta informação de consentId é inexistente quando "grant_type" é do tipo "client_credentials". | CLIENT | Todos exceto 4xx e 5xx no método POST | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| consentId​ | Consentimento | Deve ser preenchido com a mesma string obtida no campo ".data.recurringConsentId" ou ".data.recurringconsentId" retornado após a chamada inicial na API "POST /consent". *Ao reportar o uso de um endpoint /token, o identificador único de consentimento só será reportado nos casos em que "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token", uma vez que esta informação de consentId é inexistente quando "grant_type" é do tipo "client_credentials". | CLIENT | Todos exceto 4xx e 5xx no método POST | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents | |
| dropReason | Consentimento | Identifica a razão pela qual o usuário não pode prosseguir na jornada.​ Regras: O campo dropReason deve ser adicionado nas informações do campo additionalInfo que deverá ser enviado no reporte do provedor do serviço consumido (papel SERVER) O reporte deverá ser feito por todos os transmissores de dados e detentoras de conta. Para os casos em que ocorram falhas técnicas que impossibilitem a verificação do CPF/CNPJ (incluindo, mas não se limitando, a erros HTTP 4xx, 500 ou timeout na resposta), o reporte deve ser realizado com o valor NO_CREDENTIAL, Em jornadas de múltipla alçada de pessoas jurídicas, quando a autenticação é bem-sucedida mas os poderes constituídos são insuficientes para finalização do Hybrid Flow, deve-se usar NO_AUTHORITY. Diretrizes: NONE: quando o CPF (loggedUser) / CNPJ (businessEntity) possui credencial autenticadora e poderes suficientes para prosseguir o fluxo monitorado - exemplo: PF, cliente, que possui credencial ativa, mas não se autenticou; cliente que se autenticou utilizando a credencial correta. NO_CREDENTIAL: quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado. NO_AUTHORITY: quando o CPF (loggedUser) / CNPJ (businessEntity) consegue se autenticar, mas não dispõe de poderes ou alçadas para prosseguir no fluxo de compartilhamento de dados e serviços. NO_AUTHORITY_PERSON_MISMATCH: quando o CPF (loggedUser) não possui relação com a credencial utilizada na etapa de autenticação do Hybrid Flow - exemplo: consentimento criado para um CPF e autenticado por outro; criado para um CNPJ e autenticado por CPF sem relação com o CNPJ. | SERVER | Todos | POST | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| hasMinimumAmount​ | Consentimento | Valida se possui o valor mínimo definido pelo usuário recebedor​ Se preenchido o campo “.data/recurringConfiguration.automatic.minimumVariableAmount”, enviar "TRUE"; ou Se não preenchido o campo “.data.recurringConfiguration.automatic.minimumVariableAmount” enviar "FALSE" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| interval​ | Consentimento | Periodicidade que a recorrência foi definida (semanal, trimestral, anual...)​ Preencher com o valor do campo ".data.recurringConfiguration.interval" Deve ser preenchido quando paymentType for AUTOMATIC Valores possíveis: SEMANAL, MENSAL, ANUAL, SEMESTRAL, TRIMESTRAL | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| isFirstPayment​ | Consentimento | Valida se o serviço possui um pagamento associado na adesão​ Se preenchido o campo ".data.recurringConfiguration.automatic.firstPayment", enviar "TRUE"; ou Se não preenchido o campo ".data.recurringConfiguration.automatic.firstPayment", enviar "FALSE" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| isRetryAccepted​ | Consentimento | Identifica se foi autorizado a tentativas de pagamento em dias subsequentes na situação de falha do pagamento da recorrência​ Preencher com o valor do campo ".data.recurringConfiguration.automatic.isRetryAccepted" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST/PATCH) Todos menos 4xx e 5xx (GET) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| localInstrument​ | Pagamento | Especifica a forma de iniciação do pagamento​ Deve ser preenchido com a mesma string informada no payload ".data.localInstrument" | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| originalRecurringPaymentId​ | Pagamento | Identifica o primeiro pagamento da recorrência em relação as retentativas​ Preencher com o valor do campo ".data.originalRecurringPaymentId" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST/PATCH) Todos menos 4xx e 5xx (GET) | POST/PATCH/GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| paymentReference​ | Pagamento | Identifica a referência do pagamento no tempo (semanal, mensal, trimestral...)​ Preencher com o valor do campo ".data.paymentReference" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST/PATCH) Todos menos 4xx e 5xx (GET) | POST/PATCH/GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| paymentType | Consentimento Pagamento | Identifica o modo de pagamento acionado no consentimento e deve ser preenchido de acordo com o campo ".data.recurringConfiguration/oneOf" Valores possíveis: SWEEPING, AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| personType​ | Consentimento | Identifica a natureza do solicitante (PESSOA_NATURAL/PESSOA_JURIDICA)​ Deve ser preenchida baseado no tipo de pessoa responsável pelo consentimento. Deverá ser observado se '/data/businessEntity' estiver preenchido no payload, se estiver então preencher com "PESSOA_JURIDICA", se não estiver então preencher com "PESSOA_NATURAL" | CLIENT | 2xx | POST/PATCH/​GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| recurringPaymentId​ | Pagamento | Contagem de acionamentos feitos no pagamento​ Para Pagamentos v4: Preencher com o valor do campo ".data.paymentId"​ Para Pagamentos Automáticos v2: Preencher com o valor do campo ".data.recurringPaymentId" | CLIENT | Todos menos 4xx e 5xx | POST/PATCH/GET | /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| rejectionReasonCode​ | Consentimento Pagamento | Código de rejeição referente ao consentimento​ Preencher com o valor do campo ".data.rejection.reason.code" Deve ser preenchido se o campo ".data.status" for igual a REJECTED para APIs de consentimento e RJCT para APIs de pagamento | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| rejectionReasonDetail​ | Consentimento Pagamento | Detalhe sobre a rejeição referente ao consentimento​ Preencher com o valor do campo ".data.rejection.reason.detail" Deve ser preenchido se o campo ".data.status" for igual a REJECTED para APIs de consentimento e RJCT para APIs de pagamento | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |
| revocationReasonCode​ | Consentimento | Código de revogação referente ao consentimento​ Preencher com o valor do campo ".data.revocation.reason.code" Deve ser preenchido se o campo ".data.status" for igual a "REVOKED" | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| revocationReasonDetail​ | Consentimento | Detalhe sobre a revogação referente ao consentimento​ Preencher com o valor do campo ".data.revocation.reason.detail" Deve ser preenchido se o campo ".data.status" for igual a "REVOKED" | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} | |
| status​ | Consentimento Pagamento | Status que se encontra o recurso  do pagamento Deve ser preenchido com a mesma string obtida no ".data.status" Valores possíveis para consentimento: AWAITING_AUTHORISATION, PARTIALLY_ACCEPTED, AUTHORISED, REJECTED, REVOKED, CONSUMED Valores possíveis para pagamento: RCVD, CANC, ACCP, ACPD, RJCT, ACSC, PDNG, SCHD | CLIENT | 2xx | POST/PATCH/GET | /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} | |

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Especificações additionalInfo Descontinuadas > Histórico - Tabela de AdditionalInfo para Jornada Sem Redirecionamento (JSR)

---
id: 657981441
title: Histórico - Tabela de AdditionalInfo para Jornada Sem Redirecionamento (JSR)
version: 9
modified: 2025-11-18T13:55:58.361Z
url: /spaces/OF/pages/657981441/Hist+rico+-+Tabela+de+AdditionalInfo+para+Jornada+Sem+Redirecionamento+JSR
---

# Esta é a documentação legada, e deve ser consultada apenas para fins de histórico. A página atualizada pode ser encontrada aqui:
Tabela de Obrigatoriedade de additionalInfo Abaixo a tabela com os campos especiais additionalinfo.
| Nome | Descrição | Role | Http Code | Método | Enrollments |
| --- | --- | --- | --- | --- | --- |
| consentId | Deve ser preenchido com a mesma string obtida no campo `.data.consentId` retornado após a chamada inicial na API "POST /consent". *Ao reportar o uso de um endpoint /token, o identificador único de consentimento só será reportado nos casos em que "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token", uma vez que esta informação de consentId é inexistente quando "grant_type" é do tipo "client_credentials". | CLIENT | Todos | Todos | /open-banking/enrollments/v1/consents/{consentId}/authorise /open-banking/enrollments/v2/consents/{consentId}/authorise |
| personType | Deve ser preenchida baseado no tipo de pessoa responsável pelo consentimento. Deverá ser obserdado se `.data.businessEntity` estiver preenchido no payload, se estiver então preencher com "PJ", se não estiver então preencher com "PF" | CLIENT | 2xx | GET e POST | /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId} |
| localInstrument | Deve ser preenchido com a mesma string informada no payload ".data.localInstrument" | CLIENT | N/A | N/A | N/A |
| status | Deve ser preenchido com a mesma string obtida no ".data.status" | CLIENT | 2xx | GET e POST | /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId} |
| clientIp | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | CLIENT | Todos | Todos | /open-banking/enrollments/v1/consents/{consentId}/authorise /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v1/enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v2/consents/{consentId}/authorise /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/risk-signals |
| errorCodes | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code" . Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 4xx ou 5xx | Todos | /open-banking/enrollments/v1/consents/{consentId}/authorise /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v1/enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v2/consents/{consentId}/authorise /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/risk-signals |
| webhookEnable | Deve ser preenchido com o valor booleano TRUE caso haja pelo menos um item indicado na lista do campo ".webhook_uris" no payload, caso contrário deverá ser preenchido com o valor booleano FALSE | CLIENT | N/A | N/A | N/A |
| webhookInteractionId | Caso o GET esteja sendo feito após o estímulo do webhook, o x-webhook-interaction-id deverá ser indicado | CLIENT | N/A | N/A | N/A |
| enrollmentId​ | Deve ser preenchido com a mesma string obtida no campo `.data.enrollmentId` retornado após a chamada inicial na API "POST /enrollments". *Ao reportar o uso de um endpoint /token, o identificador único de consentimento só será reportado nos casos em que "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token", uma vez que esta informação de enrollmentId é inexistente quando "grant_type" é do tipo "client_credentials".​ | CLIENT​ | Todos​ | Todos​ | /open-banking/enrollments/v1/consents/{consentId}/authorise `​` /open-banking/enrollments/v1/enrollments/{enrollmentId} `​` /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration `​` /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration-options `​` /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-sign-options `​` /open-banking/enrollments/v1/enrollments/{enrollmentId}/risk-signals `​` /open-banking/enrollments/v2/consents/{consentId}/authorise `​` /open-banking/enrollments/v2/enrollments/{enrollmentId} `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/risk-signals​ |
| enrollmentId​ | Deve ser preenchido com a mesma string obtida no campo `.data.enrollmentId` retornado após a chamada inicial na API "POST /enrollments". *Ao reportar o uso de um endpoint /token, o identificador único de consentimento só será reportado nos casos em que "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token", uma vez que esta informação de enrollmentId é inexistente quando "grant_type" é do tipo "client_credentials".​ | CLIENT​ | 201​ | POST​ | /open-banking/enrollments/v1/enrollments `​` /open-banking/enrollments/v2/enrollments​ |
| authenticatorAttachment​ | Deve ser preenchido com a mesma string definida em ".data.authenticatorAttachment". Não havendo string, deve ser explicitamente enviada esse additionalInfo como sendo uma string vazia.​ | CLIENT​ | Todos​ | Todos​ | /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration​ |
| platform​ | Deve ser preenchido com a mesma string definida em ".data.platform"​ | CLIENT​ | Todos​ | Todos​ | /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration-options `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options `​` /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-sign-options `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options​ |
| rp​ | Deve ser preenchido com a mesma string definida em ".data.rp"​ | CLIENT​ | Todos​ | POST​ | /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-registration-options `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options `​` /open-banking/enrollments/v1/enrollments/{enrollmentId}/fido-sign-options `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options​ |
| rejectionReasonCode​ | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.code" ou ".data.rejection.reason.code" ou ".data.cancellation.rejectionReason"​ | CLIENT​ | Todos (PATCH) `​` 200 (GET)​ | GET ou PATCH​ | /open-banking/enrollments/v1/enrollments/{enrollmentId} `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}​ |
| rejectionReasonDetail​ | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.detail" ou ".data.rejection. reason.detail"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| authorisationFlow​ | Deve ser preenchido com a mesma string obtida no ".data.authorisationFlow"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| dropReason​ | Regras: O campo dropReason deve ser adicionado nas informações do campo additionalInfo que deverá ser enviado no reporte do provedor do serviço consumido (papel SERVER) O reporte deverá ser feito por todos os transmissores de dados e detentoras de conta. Para os casos em que ocorram falhas técnicas que impossibilitem a verificação do CPF/CNPJ (incluindo, mas não se limitando, a erros HTTP 4xx, 500 ou timeout na resposta), o reporte deve ser realizado com o valor NO_CREDENTIAL, Em jornadas de múltipla alçada de pessoas jurídicas, quando a autenticação é bem-sucedida mas os poderes constituídos são insuficientes para finalização do Hybrid Flow, deve-se usar NO_AUTHORITY. Diretrizes: NONE: quando o CPF (loggedUser) / CNPJ (businessEntity) possui credencial autenticadora e poderes suficientes para prosseguir o fluxo monitorado - exemplo: PF, cliente, que possui credencial ativa, mas não se autenticou; cliente que se autenticou utilizando a credencial correta. NO_CREDENTIAL: quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado. NO_AUTHORITY: quando o CPF (loggedUser) / CNPJ (businessEntity) consegue se autenticar, mas não dispõe de poderes ou alçadas para prosseguir no fluxo de compartilhamento de dados e serviços. NO_AUTHORITY_PERSON_MISMATCH: quando o CPF (loggedUser) não possui relação com a credencial utilizada na etapa de autenticação do Hybrid Flow - exemplo: consentimento criado para um CPF e autenticado por outro; criado para um CNPJ e autenticado por CPF sem relação com o CNPJ. | SERVER | Todos | POST | ​/open-banking/enrollments/v1/enrollments `​` /open-banking/enrollments/v2/enrollments​ |
| paymentType​ | Identifica o modo de pagamento acionado no consentimento e deve ser preenchido de acordo com a tabela especificada no swagger da API​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| revocationReasonCode​ | Deve ser preenchido com a mesma string definida em ".data.revocation.reason.code" ou ".data.cancellation.revocationReason"​ | CLIENT​ | Todos (PATCH) `​` 200 (GET)​ | GET ou PATCH​ | /open-banking/enrollments/v1/enrollments/{enrollmentId} `​` /open-banking/enrollments/v2/enrollments/{enrollmentId}​ |
| revocationReasonDetail​ | Deve ser preenchido com a mesma string definida em ".data.revocation.reason.detail"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| revokedBy​ | Deve ser preenchido com a mesma string definida em ".data.revocation.revokedBy"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| revokedFrom​ | Deve ser preenchido com a mesma string definida em ".data.revocation.revokedFrom"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| rejectedBy ​ | Deve ser preenchido com a mesma string definida em ".data.rejection. rejectedBy"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| rejectedFrom​ | Deve ser preenchido com a mesma string definida em ".data.rejection. rejectedFrom"​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| grantType​ | Deve ser preenchido com a mesma string enviada no campo ".grant_type "​ | CLIENT​ | N/A​ | N/A​ | N/A​ |
| riskSignalsQuantity​ | Calculado pelo iniciador. Cada parâmetro enviado no request body no objeto data.riskSignals durante a operação deve-se ser contabilizado, seja ele opcional ou obrigatório, gerando a quantidade total de parâmetros que foram enviados pelo iniciador na operação. É um numero inteiro​ | CLIENT​ | Todos​ | POST​ | /open-banking/enrollments/v2/consents/{consentId}/authorize​ |
| riskSignalsEnumList​ | Lista das propriedades de RiskSignals enviadas no request body (Schema RiskSignals.data )​ | CLIENT​ | Todos​ | POST​ | /open-banking/enrollments/v2/enrollments/{enrollmentId}/risk-signals​ |
| cancelledFrom​ | Deve ser preenchido com a mesma string definida em ".data.cancelledFrom "​ | CLIENT​ | 200​ | GET​ | /open-banking/enrollments/v2/enrollments/{enrollmentId}​ |
| nfcPayment | Identifica se o pagamento foi realizado através de NFC Valores aceitos: TRUE,, FALSE | CLIENT | Todos | POST | /open-banking/consents/{consentId}/authorise |

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Funcionalidades Anteriores > Histórico - Estoque de Consentimentos Ativos 

---
id: 937820214
title: Histórico - Estoque de Consentimentos Ativos 
version: 7
modified: 2025-11-18T13:56:46.081Z
url: /spaces/OF/pages/937820214/Hist+rico+-+Estoque+de+Consentimentos+Ativos
---

# Esta é a documentação legada, e deve ser consultada apenas para fins de histórico. A página atualizada pode ser encontrada aqui:
Estoque de Consentimentos Ativos **Objetivo**Disponibilização de uma nova API dedicada à obtenção de dados quantitativos de consentimentos ativos e únicos por tipo de cliente. Esta solução permite que as instituições realizem o autorreporte via PCM, garantindo precisão e conformidade com a IN 588, fornecendo uma perspectiva completa e transparente sobre o fluxo de dados e consentimentos para cada instituição.  **Terminologia**Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.  **Estoque de Consentimento**São os consentimentos que se encontram ativos e foram reportados por determinada organização, separados pelo tipo de pessoa (Física ou Jurídica), correspondentes aos dados dos clientes e transacionais (Fases 2 e 4b).  **Client e Server**Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.   **Descrição funcional da API**
| CAMPO | DESCRIÇÃO |
| Data de Referência¹ | Deve conter a data a que se referem os dados de consentimento enviados na mensagem. Formato: AAAA-MM-DD |
| organisationId¹ | Organização de envio da mensagem referente ao papel do Transmissor ou Receptor, conforme Role , a ser preenchido a partir do Certificado |
| Papel (Role)¹ | A ser preenchido com “CLIENT” ou “SERVER” |
| Escopo de Dados¹ | A ser preenchido com a Role “DADOS” |
| Total de clientes únicos PF | A ser preenchido com o total de clientes PF com consentimentos ativos. Formato: numérico inteiro natural |
| Total de clientes únicos PJ | A ser preenchido com o total de clientes PJ com consentimentos ativos. Formato: numérico inteiro natural |
| Lista de Estoque de Consentimentos, composta pelos campos¹: | |
| organisationId do CLIENT¹ | Identificador da Organização de onde a chamada foi realizada |
| organisationId do SERVER¹ | Identificador da Organização para onde a chamada foi realizada |
| Quantidade de consentimentos ativos¹ | Estoque total de consentimentos ativos, correspondendo ao número de consentimentos totais válidos até a data de referência |
¹ Campos com preenchimento obrigatório para que a mensagem seja considerada válida na ingestão **Detalhes operacionais**
| PARÂMETRO | REGRA | JUSTIFICATIVA |
| Frequência de envio | Diária | Alinha-se com a prática atual das instituições que enviam reportes diários  Proporciona dados mais atualizados e granulares  Facilita a detecção de tendências e anomalias |
| Período de Referência | Diário, das 00:00:00 às 23:59:59 | Permite às instituições consolidar dados de um dia completo |
| Política de Deduplicação | Se uma instituição enviar dados com as mesmas quantidades dentro de um período de 24 horas, considerar apenas o primeiro envio  Permitir atualizações se houver alteração nos números | Evita duplicações acidentais  Permite correções em caso de erros no reporte inicial |
| Prazo Máximo de Reporte | Até 08h00 do próximo dia da Data de Referência | Garante que os dados sejam processados em um pipeline uniforme e respeitem a janela única de processamento |
 **Regras de Validação**
- Verificar se o organisationId informado é válido

- Garantir que a Data de Referência seja sempre anterior ou igual à Data de Envio

- Assegurar que a quantidade de consentimentos únicos para PF/PJ não exceda a quantidade de consentimentos ativos

- Confirmar que o envio dos dados relativos a uma Data de Referência ocorreu até D+1 às 08h00
**Documentação da API**<Documentação da API - Área do Desenvolvedor - Open Finance Brasil - Área do Desenvolvedor>

---

# Plataforma de Coleta de Métricas > Arquivo Histórico > Funcionalidades Anteriores > Histórico - Portabilidade de Crédito

---
id: 1002668073
title: Histórico - Portabilidade de Crédito.
version: 6
modified: 2025-11-18T13:56:52.436Z
url: /spaces/OF/pages/1002668073/Hist+rico+-+Portabilidade+de+Cr+dito.
---

# Esta é a documentação legada, e deve ser consultada apenas para fins de histórico. A página atualizada pode ser encontrada aqui:
Portabilidade de Crédito **Objetivo** Disponibilização de uma nova API dedicada à obtenção de dados referentes às solicitações da portabilidade por parte dos clientes das instituições financeiras. Esta solução permite que as instituições forneçam dados à PCM de forma completa e transparente sobre o fluxo de solicitações de Portabilidade de Crédito ao ecossistema do Open Finance Brasil.    **Terminologia** Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.    **Portabilidade de Crédito** A Portabilidade de Crédito permite que usuários transfiram suas operações de crédito e arrendamento mercantil entre instituições financeiras em busca de melhores condições. Atualmente, a solicitação de portabilidade pode ser feita via registradora. A implementação da solicitação de portabilidade, alinhada à agenda do Open Finance Brasil (OFB), visa agilizar e simplificar o processo.    **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.    **Descrição funcional das APIs**   
| API de inclusão de reportes de portabilidade - SERVER |
| Campo | Descrição |
| fapiInteractionId¹ | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY- UUID que identifica uma transação específica entre dois participantes. Esse dado pode ser encontrado no header x-fapi-interaction-id que é informado pelo Client e devolvido pelo Server. Mais informações em Cabeçalhos HTTP na documentação do Open Finance Brasil. |
| endpoint¹ | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. |
| statusCode¹ | Status de retorno HTTP da solicitação. No caso de ocorrer um timeout client side preencher com um código 403 (conforme documentação ). |
| httpMethod¹ | Método HTTP da solicitação.  [ GET, POST, PUT, DELETE, PATCH ] |
| correlationId | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. |
| timestamp¹ | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| clientOrgId¹ | Identificador da organização de onde a chamada foi disparada. |
| serverOrgId¹ | Identificador da organização para onde a chamada foi feita. |
| Data e hora da atualização do status | Data e hora em que o contrato teve o status atualizado. Uma string com data e hora conforme especificação ISO-8601, sempre com a utilização de timezone UTC(UTC time format). |
| Motivo da recusa | Motivo de recusa do pedido de portabilidade.  Só será preenchido caso o status seja REJECTED, CANCELLED ou PAYMENT_ISSUE ` ` A consulta ao endpoint de GET é requerida para o fluxo de portabilidade |
| Rejeitado por | Informar usuário responsável pela rejeição da proposta, onde: PROPONENTE - Indica que o pedido de portabilidade de crédito foi rejeitado pela proponente, seja porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades. USUARIO - Indica que o cliente cancelou o pedido de portabilidade de crédito. CREDORA- Indica que a Instituição Credora cancelou o contrato por retenção do cliente ou outros motivos conforme motivo de recusa.  Só será preenchido caso o status seja REJECTED ou CANCELLED  [ PROPONENTE, USUARIO, CREDORA ] |
| Papel¹ | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client.  [ CLIENT, SERVER ] |
| Status da portabilidade | Informação sobre o status de um pedido de portabilidade de crédito, onde:  RECEIVED: Estado inicial. Indica que o pedido de portabilidade foi solicitado junto à instituição credora. O pedido deve permanecer neste estado até o próximo dia útil (D+1) onde começará a contar o prazo de 3 dias úteis para a etapa de contraproposta e o pedido de portabilidade deverá ser movido para PENDING  PENDING: Indica que o pedido de portabilidade de crédito está na fase de contraproposta, onde a instituição credora poderá enviar uma contraproposta ou não para o cliente por qualquer canal (email, telefone, etc.) porém o aceite só deverá ser valido se o cliente aprovar no canal digital da instituição credora  ACCEPTED_SETTLEMENT_IN_PROCESS: Indica que a contraproposta não foi aceita pelo cliente e a instituição proponente terá que quitar o valor do contrato no mesmo dia em que o estado foi ativado.  ACCEPTED_SETTLEMENT_COMPLETED: Indica que a instituição proponente já liquidou o contrato e comunicou a respeito à credora que está validando os dados do contrato bem como valores recebidos para a quitação do mesmo (nesta etapa a instituição credora tem 2 dias úteis para fornecer a confirmação e o recibo de quitação do contrato de empréstimo)  PORTABILITY_COMPLETED: Indica que o pedido de portabilidade foi concluído com sucesso REJECTED: Indica que o pedido de portabilidade de crédito foi rejeitado, seja porque o cliente aceitou a contraproposta, ou porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades  CANCELLED: Indica que o cliente cancelou o pedido de portabilidade de crédito  PAYMENT_ISSUE: Indica que a Instituição Credora encontrou alguma inconsistência na liquidação efetuada e que a Instituição Proponente deverá realizar ajustes conforme sugerido pela Instituição Credora para solucionar a pendência antes do cancelamento do pedido de portabilidade de crédito |
¹ Campos com preenchimento obrigatório para que a mensagem seja considerada válida na ingestão  
| API de inclusão de reportes de portabilidade - CLIENT |
| Campo | Descrição |
| timestamp¹ | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| Id da Portabilidade¹ | Código identificador do pedido de portabilidade realizado. |
| Id do contrato¹ | Identifica de forma única o contrato da operação de crédito do cliente, mantendo as regras de imutabilidade dentro da instituição transmissora. |
| Data/hora da criação¹ | Data e hora em que a Proponente registrou a presente proposta (chamada ao POST /portabilities). Uma string com data e hora conforme especificação ISO8601, sempre com a utilização de timezone UTC-0 (UTC time format). |
| Submodalidade da categoria do produto¹ | Categoria para classificação específica relacionada com a submodalidade do produto |
| CET do contrato original¹ | CET – Custo Efetivo Total deve ser expresso na forma de taxa percentual anual e incorpora todos os encargos e despesas incidentes nas operações de crédito (taxa de juro, mas também tarifas, tributos, seguros e outras despesas cobradas). O preenchimento deve respeitar as 6 casas decimais, mesmo que venham preenchidas com zeros (representação de porcentagem p.ex: 0.150000. Este valor representa 15%. O valor 1 representa 100%). Para o público PF (pessoa física) o campo é de envio obrigatório para contratos firmados a partir de 2008, conforme Resolução CMN 3.517. Para o público PJ (pessoa jurídica) o campo é de envio obrigatório para contratos firmados a partir de 2011, conforme Resolução CMN 3.909. O campo poderá ser preenchido com 0.00 em cenários nos quais a casa não tenha a informação de CET (Custo efetivo total) apenas para as exceções listadas abaixo:  Em contratos anteriores a 2008 (para o público PF)  Em contratos anteriores a 2011 (para o público PJ);  Público PJ de médio ou grande porte. |
| CET da proposta original¹ | CET – Custo Efetivo Total deve ser expresso na forma de taxa percentual anual e incorpora todos os encargos e despesas incidentes nas operações de crédito (taxa de juro, mas também tarifas, tributos, seguros e outras despesas cobradas). O preenchimento deve respeitar as 6 casas decimais, mesmo que venham preenchidas com zeros (representação de porcentagem p.ex: 0.150000. Este valor representa 15%. O valor 1 representa 100%). Para o público PF (pessoa física) o campo é de envio obrigatório para contratos firmados a partir de 2008, conforme Resolução CMN 3.517. Para o público PJ (pessoa jurídica) o campo é de envio obrigatório para contratos firmados a partir de 2011, conforme Resolução CMN 3.909. O campo poderá ser preenchido com 0.00 em cenários nos quais a casa não tenha a informação de CET (Custo efetivo total) apenas para as exceções listadas abaixo:  Em contratos anteriores a 2008 (para o público PF)  Em contratos anteriores a 2011 (para o público PJ);  Público PJ de médio ou grande porte. |
| Prazo do contrato original¹ | Prazo restante do contrato original de empréstimo. |
| Prazo da proposta¹ | Prazo da proposta de portabilidade de crédito |
| Status da portabilidade¹ | Informação sobre o status de um pedido de portabilidade de crédito, onde:  RECEIVED: Estado inicial. Indica que o pedido de portabilidade foi solicitado junto à instituição credora. O pedido deve permanecer neste estado até o próximo dia útil (D+1) onde começará a contar o prazo de 3 dias úteis para a etapa de contraproposta e o pedido de portabilidade deverá ser movido para PENDING  PENDING: Indica que o pedido de portabilidade de crédito está na fase de contraproposta, onde a instituição credora poderá enviar uma contraproposta ou não para o cliente por qualquer canal (email, telefone, etc.) porém o aceite só deverá ser valido se o cliente aprovar no canal digital da instituição credora  ACCEPTED_SETTLEMENT_IN_PROCESS: Indica que a contraproposta não foi aceita pelo cliente e a instituição proponente terá que quitar o valor do contrato no mesmo dia em que o estado foi ativado.  ACCEPTED_SETTLEMENT_COMPLETED: Indica que a instituição proponente já liquidou o contrato e comunicou a respeito à credora que está validando os dados do contrato bem como valores recebidos para a quitação do mesmo (nesta etapa a instituição credora tem 2 dias úteis para fornecer a confirmação e o recibo de quitação do contrato de empréstimo)  PORTABILITY_COMPLETED: Indica que o pedido de portabilidade foi concluído com sucesso REJECTED: Indica que o pedido de portabilidade de crédito foi rejeitado, seja porque o cliente aceitou a contraproposta, ou porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades  CANCELLED: Indica que o cliente cancelou o pedido de portabilidade de crédito  PAYMENT_ISSUE: Indica que a Instituição Credora encontrou alguma inconsistência na liquidação efetuada e que a Instituição Proponente deverá realizar ajustes conforme sugerido pela Instituição Credora para solucionar a pendência antes do cancelamento do pedido de portabilidade de crédito |
| Data e hora da atualização do status | Data e hora em que o contrato teve o status atualizado. Uma string com data e hora conforme especificação ISO-8601, sempre com a utilização de timezone UTC(UTC time format). |
| Motivo da recusa | Motivo de recusa do pedido de portabilidade.  Só será preenchido caso o status seja REJECTED, CANCELLED ou PAYMENT_ISSUE A consulta ao endpoint de GET é requerida para o fluxo de portabilidade |
| Rejeitado por | Informar usuário responsável pela rejeição da proposta, onde: PROPONENTE - Indica que o pedido de portabilidade de crédito foi rejeitado pela proponente, seja porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades. USUARIO - Indica que o cliente cancelou o pedido de portabilidade de crédito. CREDORA- Indica que a Instituição Credora cancelou o contrato por retenção do cliente ou outros motivos conforme motivo de recusa.  Só será preenchido caso o status seja REJECTED ou CANCELLED  [ PROPONENTE, USUARIO, CREDORA ] |
| fapiInteractionId¹ | UUID que identifica uma transação específica entre dois participantes. Esse dado pode ser encontrado no header x-fapi-interaction-id informado pelo Client e devolvido pelo Server. Mais informações em Cabeçalhos HTTP na documentação do Open Finance Brasil. O envio dessa informação é obrigatório, exceto nos casos ontem ela não esteja disponível como, por exemplo, em respostas com status 5xx, ou em chamadas que terminaram por timeout onde o reporte tem que ser enviado, mas sem esse atributo. Nos demais cenários, o envio é obrigatório. |
| endpoint¹ | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. |
| endpointUriPrefix¹ | Endereço do servidor de destino da chamada, incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: https://{host}/{prefixo }, sendo:  host: endereço FQDN do servidor de destino  prefixo: toda a parte do path que vem antes da string /open-banking |
| httpMethod¹ | Método HTTP da solicitação.  [ GET, POST, PUT, DELETE, PATCH ] |
| correlationId | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. |
| statusCode¹ | Status de retorno HTTP da solicitação. No caso de ocorrer um timeout client side preencher com um código 403 (conforme documentação ). |
| Id do reporte¹ | Identificador único interno do reporte no formato UUID v4. |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| clientOrgId¹ | Identificador da organização de onde a chamada foi disparada. |
| serverOrgId¹ | Identificador da organização para onde a chamada foi feita. |
| clientSSId¹ | Identificador do software statement de onde a chamada foi disparada. A PCM garante que foi esta orgId que obteve o token de acesso utilizado neste reporte. |
| Papel¹ | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client.  [ CLIENT, SERVER ] |
¹ Campos com preenchimento obrigatório para que a mensagem seja considerada válida na ingestão  **Documentação da API** Documentação da API

---

# Plataforma de Coleta de Métricas > Controle de Versões > Calendário de releases

---
id: 1157595137
title: Calendário de releases
version: 1
modified: 2025-10-09T15:34:20.097Z
url: /spaces/OF/pages/1157595137/Calend+rio+de+releases
---

v 1.00
## Objetivo desta página
Apresentar o cronograma de desenvolvimento e implantação das releases.2026D18002026C18002026B18002026A18002025D18002025C18002025B18002025A1800

---

# Plataforma de Coleta de Métricas > Controle de Versões > Changelog Completo

---
id: 1216872449
title: Changelog Completo
version: 13
modified: 2026-02-09T18:32:40.354Z
url: /spaces/OF/pages/1216872449/Changelog+Completo
---

## Objetivo desta página
Registrar as mudanças realizadas na documentação da PCM.
# Primeiros passos

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Visão geral da PCM | v.7 | 03/01/2023 | Atualizadas as premissas técnicas | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Manual de integração | v.11 | 04/04/2024 | Atualização de links da documentação da API Inclusão do fluxo de autenticação Alteração no exemplo de autenticação Alteração no exemplo da interação com a API Alteração no exemplo do cenário PAIRED_INCONSISTENT | | |
| | v.1 | 23/12/2022 | Versão inicial | | |
| Lista de endpoints | 1.02 | 10/11/2025 | Inclusão do endpoint /open-banking/enrollments/v2/recurring-consents/{recurringConsentId}/authorise | 2025D | |
| | 1.01 | 12/09/2025 | Retirada do endpoint /open-banking/credit-portability/v1/credit-operations/{contractId}/portability-eligibility de Portabilidade de Crédito, incluído erronamente. | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |

# Especificações por Domínio

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Dados Abertos | | | | | |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Obrigatoriedade de additionalInfo | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Dados Cadastrais e Transacionais | | | | | |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Obrigatoriedade de additionalInfo | 1.0.3 | 10/12/2025 | Ajuste no padrão do campo consentId | | |
| | 1.0.2 | 10/11/2025 | Inclusão do additionalInfo tokenId Inclusão do additionalInfo journeyIsLinked, referente à Jornada Otimizada | 2025D | |
| | 1.01 | 01/10/2025 | Melhoria na descrição do campo companyProfileInfo, contemplando os links para pesquisa de CNPJ | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| | | | | | |
| Regras de Validação | 1.01 | 17/12/2025 | Inclusão da validação do campo companyProfileInfo para Consentimentos, de acordo com a implementação realizada na release 2025C | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Pagamentos | | | | | |
| Estados de Pagamento | 1.0.2 | 10/12/2025 | Ajuste no padrão do campo paymentId | | |
| | 1.01 | 03/10/2025 | Correção do role responsável pelo envio - de CLIENT para SERVER Inclusão do domínio “SCHEDULED” em paymentType | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Obrigatoriedade de additionalInfo | 1.06 | 23/01/2026 | Ajuste na regra de preenchimento do campo errorCodes, dando clareza à regra vigente de envio de apenas um registro, e não de uma lista. Ajuste na obrigatoriedade de envio dos campos journeyIsLinked e journeyLinkId para PIX Automáticos - retirada da restrição de 4xx e 5xx | | |
| | 1.05 | 01/12/2025 | Inclusão do endpoint /open-banking/enrollments/v x /recurring-consents/{recurringConsentId}/authorise, na Jornada Sem Redirecionamento, para os additionalInfo enrollmentId, recurringConsentId e errorCodes. | 2025D | |
| | 1.04 | 10/11/2025 | Inclusão do additionalInfo recurringConsentId para o endpoint /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options, mutuamente excludente com o additionalInfo consentId Inclusão das regras de validação dos additionalInfo consentId e recurringConsentId para Jornada sem Redirecionamento Inclusão do domínio AUTO no additionalInfo localInstrument para Iniciação de Pagamentos e PIX Automático Retirado do domínio do additionalInfo errorCodes de Pagamentos Automáticos: DETALHE_TENTATIVA_INVALIDA e LIMITE_TENTATIVAS_EXCEDIDO Incluído no domínio do additionalInfo rejectionReasonCode de Pagamentos Automáticos: FLUXO_NAO_SUPORTADO_PRODUTO Inclusão do additionalInfo authorisationFlowIntent para Iniciação de Pagamentos e Pagamentos Automáticos Inclusão do additionalInfo tokenId para todas as jornadas Inclusão dos additionalInfo journeyIsLinked e journeyLinkId em Jornada Sem Redirecionamento e PIX Automático, referentes à Jornada Otimizada | 2025D | |
| | 1.03 | 01/10/2025 | Melhoria na descrição do campo companyProfileInfo, contemplando os links para pesquisa de CNPJ Inclusão do domínio do campo status para Pagamento Sem Redirecionamento | | |
| | 1.02 | 24/09/2025 | Alteração na regra de preenchimento do campo authorisationFlow em Iniciação de Pagamentos e PIX Automático, de acordo com o contrato da API Inclusão de domínio do campo authorisationFlow em Iniciação de Pagamentos e PIX Automático, de acordo com o contrato da API | | |
| | 1.01 | 12/09/2025 | Retirada dos campos riskSignalsEnumList e rislSignalsQuantity, incluídos erroneamente na documentação Ajustes na documentação: authorisationFlow: inclusão do endpoint /open-banking/payments/v x /pix/payments/{paymentId}​ e métodos GET/PATCH consentId: correção do padrão, exemplo e statusCodes errorCodes: ajuste no domínio para erros 422 demais erros paymentSchedule: correção na regra de preenchimento - deve ser mutualmente excludente com paymentDate paymentList: identificação dos itens que fazem parte da lista com o identificador paymentList[]. paymentType: adequação da regra de preenchimento nfcPayment: ajuste na regra de preenchimento status: ajuste na descrição do campo para Pagamentos Sem Redirecionamento | | |
| | 1.00 | 22/08/2025 | Versão inicial | | |
| Regras de Validação | 1.04 | 09/02/2026 | Inclusão de campos: paymentSchedule e localInstrument Ajustes diversos nas validações | | |
| | 1.03 | 15/10/2025 | Inclusão da validação do campo companyProfileInfo para Iniciação de Pagamentos, Jornada Sem Redirecionamento e Pagamentos Automáticos, de acordo com a implementação realizada na release 2025C Inclusão da validação do campo nfcPayment para Jornada Sem Redirecionamento, de acordo com implementação realizada na release 2025B | | |
| | 1.02 | 09/10/2025 | Ajuste das regras de validação para refletir alterações feitas nas obrigatoriedades de campos da PCM | | |
| | 1.01 | 15/09/2025 | Retirada da regra de validação do additionalInfo authenticatorAttachment devido ao campo não ser obrigatório | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Portabilidade de crédito | | | | | |
| Funcionalidade e Campos | 1.01 | 13/10/2025 | Alteração do status ACCEPTED_SETTLEMENT_IN_PROCESS para ACCEPTED_SETTLEMENT_IN_PROGRESS | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Campos Obrigatórios e Opcionais | 1.0.5 | 02/01/2026 | Ajuste na visualização dos campos, separando os campos de acordo com a obrigatoriedade de envio no POST e recuperação através de GET na PCM, com o intuito de diferenciar os métodos e endopints exigidos pelas APIs de produtos contra a forma de envio e obtenção dos campos na PCM. | | |
| | 1.0.4 | 10/12/2025 | Ajuste no padrão do campo consentId | | |
| | 1.0.3 | 10/11/2025 | Inclusão dos campos creationDateTime e consentId Exclusão dos campos role, contractId, originalContractTerm e propositionTerm Inclusão das informações referentes à obrigatoriedade considerando Http code e endpoint Complementadas as regras de preenchimento dos campos cresitPortabilityStatus, rejectedBy e rejectionReason para dar mais clareza | 2025D | |
| | 1.02 | 13/10/2025 | Alteração do domínio do campo creditPortabilityStatus - de ACCEPTED_SETTLEMENT_IN_PROCESS para ACCEPTED_SETTLEMENT_IN_PROGRESS | | |
| | 1.01 | 26/09/2025 | Exclusão do campo Id do Reporte da API Client | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.01 | 09/02/2026 | Inclusão da regra de validação do campo consentId Inclusão da regra de validação do campo errorCode Ajustes diversos nas validações | | |
| | 1.00 | 03/12/2025 | Versão inicial | 2025D | |
| Regras de Descarte | 1.0.1 | 10/12/2025 | Inclusão das regras de descarte da API de Estados de Pagamento | | |
| | 1.00 | 10/11/2025 | Versão inicial | 2025D | |
| Hybridflow | | | | | |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Diagramas de Fluxo | | | | | |
| Diagrama de Envio de Reportes | v.3 | 03/09/2025 | Atualização do diagrama | | |
| | v.1 | 26/08/2025 | Versão inicial | | |
| Diagrama de Sequência | v.1 | 26/08/2025 | Versão inicial | | |
| Segurança | | | | | |
| Regras de Obrigatoriedade de additionalInfo | 1.0.1 | 10/12/2025 | Ajuste no padrão do campo consentId | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Descarte | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Consentimentos | | | | | |
| Estoque de Consentimentos Ativos | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Campos Obrigatórios e Opcionais | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Regras de Validação | 1.01 | 09/02/2026 | Inclusão da regra de validação de envio diário do estoque de consentimento Inclusão da regra de validação dos campos clientOrgId e serverOrgId | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |

# Integração Técnica

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Especificações de Reporte | | | | | |
| Processo de Reporte | v.50 | 31/10/2025 | Atualização do link do manual de integtação Inclusão e ajustes dos modelos dos reportes Inclusão de informações sobre additionalInfo Inclusão e ajustes das formas de envio | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Processamento de Dados | v.11 | 21/11/2025 | Retirado um trecho da Conciliação que estava gerando dúvida sobre o processo de descarte do campo fapiInteractionId x statusCode 408 e 5xx. Ajustado o diagrama de Ciclo de vida do reporte para refletir o processo correto na ausência do fapiInteractionId para statusCode 408 e 5xx. Ajustada a definição de ACCEPTED, refletindo o ajuste realizado no diagrama do Ciclo de vida de reporte. | | |
| | v.10 | 23/02/2024 | Inclusão do processo de conciliação Inclusão do ciclo de vida do reporte | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Tratamento de Divergências | v.4 | 25/12/2022 | Ajuste de texto (inconsistências) | | |
| | v.1 | 22/12/2022 | Versão inicial | | |
| Documentação da API | v.7 | 07/10/2025 | Movimentação da visualização legada para a estrutura de histórico | | |
| | v.1 | 25/08/2025 | Versão inicial | | |

# Gestão Operacional

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Notificações via ticket | | | | | |
| SLA de Envio | 1.02 | 10/11/2025 | Ajuste da fórmula apresentada de cálculo do SLA - o cálculo está sendo feito corretamente, porém a fórmula documentada não estava refletindo a realidade | 2025D | |
| | 1.01 | 10/10/2025 | Início do envio dos tickets de SLA de Envio de Dados Cadastrais e Transacionais (Fases 2 e 4b) | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Qualidade de Dados | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Reportes Descartados | 1.01 | 03/11/2025 | Início do envio dos tickets de Reportes Descartados de Segurança | | |
| | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| Reportes Não Pareados | 1.00 | 22/08/2025 | Versão inicial | 2025C | 781 - 22/08/2025 |
| FAQ | v.4 | 15/04/2024 | Atualização do descritivo do SLA de reportes à PCM Inclusão de informação sobre crítica de criação de consentimento | | |
| | v.1 | 18/01/2023 | Versão inicial | | |
| Troubleshooting | v.6 | 08/04/2024 | Inclusão das críticas “Report is too old” e “OrganisationId doesn’t exist on Directory” | | |
| | v.1 | 18/01/2023 | Versão inicial | | |

# Controle de Versões

| Área | Versão | Data | Mudança realizada | Release | Informa |
| --- | --- | --- | --- | --- | --- |
| Release Notes | 1.00 | 15/09/2025 | Versão inicial | | |
| Release Candidate | 1.00 | 09/10/2025 | Versão inicial | | |
| Calendário de releases | 1.00 | 09/10/2025 | Versão inicial | | |
| Changelog completo | 1.01 | | Reestruturação do changelog de acordo com a nova árvore de documentação da PCM | | |
| | 1.00 | | Versão inicial | 2025C | 781 - 22/08/2025 |

---

# Plataforma de Coleta de Métricas > Controle de Versões > Release Candidate

---
id: 1118470185
title: Release Candidate
version: 7
modified: 2025-11-18T14:06:10.069Z
url: /spaces/OF/pages/1118470185/Release+Candidate
---

v 1.00
## Objetivo desta página
Acompanhar, em caráter preliminar, a lista e status das iniciativas previstas para cada novo ciclo de desenvolvimento da PCMRelease 2025D1800**Data prevista da release:** 17/11/2025
| Contexto | Detalhes | Status atual |
| --- | --- | --- |
| Jornada Sem Redirecionamento | Novo código de rejeição (rejectionReasonCode): ORIGEM_FIDO_INVALID) no POST /consents/{consentId}/authorise | Finalizado |
| Jornada Sem Redirecionamento | Novo código de rejeição (rejectionReasonCode): MAXIMO_CHALLENGES_ATINGIDO no POST /enrollments/{enrollmentId}/fido-registration-options | Finalizado |
| Jornada Sem Redirecionamento | Novo código de rejeição (rejectionReasonCode): REJEITADO_TITULARIDADE_DIVERGENTE no GET /enrollments/enrollmentId | Finalizado |
| Jornada Sem Redirecionamento | Novo endpoint para autorização de consentimentos recorrentes de Pix Automático | Finalizado |
| Jornada Sem Redirecionamento | Ajuste do endpoint que obtém os parâmetros de autenticação para incluir consentimentos de longa duração (recurringConsentId) no POST /enrollments/{enrollmentId}/fido-sign-options | Finalizado |
| Jornada Sem Redirecionamento | Ajuste da descrição do endpoint POST /enrollments/{enrollmentId}/risk-signals | Sem impacto para a PCM, retirado da release |
| Jornada Otimizada | Jornada Otimizada - Inclusão de campos para monitoramento de consentimentos em Jornada Otimizada | Finalizado |
| Jornada Sem Redirecionamento | Novo código de erro (errorCode): PERMISSAO_INVALIDA_VINCULO_CONSENTIMENTO em /enrollments/{enrollmentId}/fido-sign-options | Finalizado |
| Pagamentos Automáticos | inclusão de localInstrument AUTO em GET /pix/payments/{recurringPaymentId} e PATCH /pix/payments/{recurringPaymentId} | Finalizado |
| Pagamentos Automáticos | Alteração da descrição do endpoint PATCH /recurring-consents/{recurringConsentId} | Finalizado |
| Pagamentos Automáticos | Alteração na regra do campo localInstrument para o tipo AUTO em POST /pix/recurring-payments, GET /pix/recurring-payments/{recurringPaymentId} e PATCH /pix/recurringpayments/{recurringPaymentId} | Finalizado |
| Pagamentos Automáticos | Remoção do código de erro (errorCodes) DETALHE_TENTATIVA_INVALIDA em POST /pix/recurring-payments | Finalizado |
| Pagamentos Automáticos | Remoção da mensagem de cancelamento do pagamento em POST /pix/recurring-payments | Finalizado |
| Pagamentos Automáticos | Remoção dos códigos de erro (errorCodes): DETALHE_TENTATIVA_INVALIDO e LIMITE_TENTATIVAS_EXCEDIDO em POST /pix/recurring-payments | Finalizado |
| Pagamentos Automáticos | Novo código de rejeição (rejectionReasonCode):FLUXO_NAO_SUPORTADO_PRODUTO em POST /recurring-consents, GET /recurring-consents/{recurringConsentId} e PATCH /recurring-consents/{recurringConsentId} | Finalizado |
| Pagamentos Automáticos | Alteração das regras de preenchimento para o campo paymentReference em POST /pix/recurring-payments, GET /pix/recurring-payments/{recurringPaymentId}, GET /pix/recurring-payments e PATCH /pix/recurringpayments/{recurringPaymentId} | Sem impacto para a PCM, retirado da release |
| Pagamentos Automáticos | Altração do código de erro (errorCodes): LIMITE_TENTATIVAS_EXCEDIDO) | Sem impacto para a PCM, retirado da release |
| Portabilidade de Crédito | Ingestão de consentId para Portabilidade de Crédito | Finalizado |
| Segurança | Tratamento do tempo de expiração do token | Finalizado |
| Dados Cadastrais e Transacionais / Pagamentos | IQD PJ | Retirado da release |
| Dados Cadastrais e Transacionais / Pagamentos / Hybridflow / Segurança / Dados Abertos | Introdução do additionalInfo tokenId para vinculação e rastreabilidade das jornadas de tokens | Finalizado |
| Iniciação de Pagamentos / Pagamentos Automáticos | Desambiguação de jornadas de pagamentos via campo autorisationFlowIntent | Finalizado |

---

# Plataforma de Coleta de Métricas > Controle de Versões > Release notes

---
id: 1118306305
title: Release notes
version: 7
modified: 2025-11-18T14:32:19.411Z
url: /spaces/OF/pages/1118306305/Release+notes
---

v 1.00
## Objetivo desta página
Relacionar a lista de iniciativas implementadas em cada uma das Releases da PCM2025D1800**Data da release:** 17/11/2025**Data do Informa:** 18/11/2025**Número do Informa:** -
| Contexto | Tipo de alteração | O que foi alterado? | Detalhes | Antes | Depois |
| --- | --- | --- | --- | --- | --- |
| Reestruturação da documentação da PCM, reorganizando os itens por contexto | Alteração | Reorganização da estrutura da árvore | Principais benefícios: Organização dos itens por contexto, de forma que siga uma jornada de construção e entendimento dentro do contexto da PCM. | Itens “soltos” dentro da estrutura da PCM, unificação de itens por tipo (validação, addinfo, descartes) e não por contexto. | Criação de árvores de contexto que mostrem o contexto da PCM dentro de um fluxo. |
| Inclusão da documentação das regras de descarte de Portabilidade de Crédito | Inclusão | Disponibilização das regras de descarte de Portabilidade de Crédito | As regras de descarte de reportes de Portabilidade de Crédito não estavam documentadas. | Regras de descarte de reportes de Portabilidade de Crédito não documentadas. | Documentação das regras de descarte de reportes de Portabilidade de Crédito. |
| Ajustes na documentação de campos obrigatórios e opcionais de Portabilidade de Crédito | Alteração | Inclusões, exclusões e adequações dos campos da Portabilidade de Crédito na PCM | Inclusão de http code e endpoints/versões Adequação da obrigatoriedade de envio de acordo com o statusCode Inclusão dos campos creationDateTime, consentId e errorCode Remoção dos campos originalContractTerm, propositionTerm e contractId Ajustes nas regras de preenchimento para tornar mais claro a origem do dado | Tabela de campos obrigatórios e opcionais não aderentes às alterações realizadas no produto | Tabela de campos obrigatórios e opcionais alinhado com as últimas atualizações do produto |
| Revisão nas regras de descarte de reportes de Portabilidade de Crédito | Alteração | Regras de descarte de reportes de Portabilidade de Crédito | Retirada a obrigatoriedade dos campos portabilityId, creationDateTime e creditPortabilityStatus para casos de statusCode 4xx e 5xx Retirada a validação de enum do campo rejectionReason (será validado dentro do processo de aferição de qualidade dos reportes) | Reportes sendo descartados indevidamente | Regras de descarte ajustadas |
| Descarte indevido de reportes de Estados de Pagamento | Alteração | Ajuste no enum do campo paymentType na validação da ingestão da PCM | Correção de um erro que estava descartando indevidamente reportes de Estados de Pagamento no campo paymentType (SCHEDULED) | Rejeitando paymentType do tipo SCHEDULED | Crítica ajustada para aceitar corretamente |
| Descarte indevido de reportes de Dados Cadastrais e Transacionais | Alteração | Ajuste do tipo do campo statusSummary e seus subitens | Correção de um erro que estava descartando indevidamente reportes de Dados Cadastrais e Transacionais no additionalInfo statusSummary | Rejeitando statusSummary (enviando string, correto número) | Ajustada a regra do statusSummary (aceitando string) |
| Jornada Sem Redirecionamento - enums | Alteração | Inclusão de enums dos campos errorCodes e rejectionReasonCode | Inclusão de novos errorCodes: ORIGEM_FIDO_INVALIDA no POST /consents/{consentId}/authorise MAXIMO_CHALLENGES_ATINGIDO no POST /enrollments/{enrollmentId}/fido-registration-options PERMISSAO_INVALIDA_VINCULO_CONSENTIMENTO em /enrollments/{enrollmentId}/fido-sign-options Inclusão de novo rejectionReasonCode: REJEITADO_TITULARIDADE_DIVERGENTE no GET /enrollments/enrollmentId | Não existente | Novos enums adicionados na documentação funcional e nos critérios de aberturas de ticket de qualidade de dados e dashboard de monitoramento operacional |
| Jornada Sem Redirecionamento - novo endpoint | Inclusão | Novo endpoint ingerido pela PCM | Novo endpoint para autorização de consentimentos recorrentes de PIX Automático: /recurring-consents/{recurringConsentId}/authorise | Não existente | Novo endpoint sendo ingerido pela PCM |
| PIX Automático - enums | Alteração | Inclusão e exclusção de enums dos campos localInstrument, errorCodes e rejectionReasonCode | Inclusão de novo localInstrument: AUTO em GET /pix/payments/{recurringPaymentId} e PATCH /pix/payments/{recurringPaymentId} Remoção de rejectionReasonCode: CONSENTIMENTO_REVOGADO de POST/pix/recurring-payments, GET /pix/recurringpayments/{recurringPaymentId} e PATCH /pix/recurring-payments/{recurringPaymentId} Remoção de errorCodes: DETALHE_TENTATIVA_INVALIDA e LIMITE_TENTATIVAS_EXCEDIDO de POST /pix/recurring-payments Inclusão de novo rejectionReasonCode: FLUXO_NAO_SUPORTADO_PRODUTO em POST /recurring-consents, GET /recurring-consents/{recurringConsentId} e PATCH /recurring-consents/{recurringConsentId} | Não existente | Novos enums adicionados na documentação funcional e nos critérios de aberturas de ticket de qualidade de dados e dashboard de monitoramento operacional |
| Novo additionalInfo tokenId em todas as APIs da PCM | Inclusão | Novo additionalInfo | Inclusão do additionalInfo tokenId nas APIs Private, Hybridflow e Open Data no papel CLIENT. Este campo atuará como um identificador único e criptograficamente seguro do token utilizado no consumo da API | Não existente | additionalInfo sendo ingerido pela PCM |
| Novo additionalInfo authorisationFlowIntent na API Private | Inclusão | Novo additionalInfo | Inclusão do additionalInfo authorisationFlowIntent, no reporte da etapa de solicitação de consentimento. O propósito principal deste campo é permitir a desambiguação e clara distinção entre as jornadas de pagamento que demandam ou não redirecionamento do usuário, já na etapa de provisionamento do consentimento | Não existente | additionalInfo sendo ingerido pela PCM |
| Novo additionalInfo recurringConsentId na API Private | Inclusão | Novo additionalInfo | Inclusão do additionalInfo recurringConsentId mutuamente exclusivo com consentId para o endpoint POST /enrollments/{enrollmentId}/fido-sign-options | Não existente | additionalInfo sendo ingerido pela PCM |
| Jornada Otimizada | Inclusão | Novos additionalInfo | Inclusão de additionalInfo para Jornada Otimizada: Consentimentos: journeyIsLinked JSR e PIX Automático: journeyIsLinked e journeyLinkId | Não existente | additionalInfo sendo ingerido pela PCM |
| Nova regra de descarte - timestamp | Inclusão | Nova regra de descarte em todas as APIs | Inclusão de regra de descarte para o campo timestamp: Não permitir o recebimento de timestamp com data futura superior a 5 minutos da data de recebimento do reporte na PCM Não permitir o recebimento de timestamp fora do formato válido (YYYY-MM-DDTHH:mm:ss.sssZ) | Não existente | Reportes descartados que infrinjam a nova regra |
| Ajuste na formatação do campo "expires_in" | Alteração | Ajuste no retorno do campo expires_in | Ajuste na formatação do campo "expires_in" no retorno de um novo token para envio doa dados da PCM | Retornando sempre o valor inicial, não o total restante | Retornando o total restante |
2025C1800**Data da release:** 01/09/2025**Data do Informa:** 22/08/2025**Número do Informa:** 781
| Contexto | Tipo de alteração | O que foi alterado? | Detalhes | Antes | Depois |
| --- | --- | --- | --- | --- | --- |
| Evolução da estrutura funcional na Área do Desenvolvedor, permitindo reorganizar, ampliar e evidenciar regras de Monitoramento Operacional. | Inclusão | Criação da documentação funcional | Principais benefícios e entregáveis: Reorganização dos Campos Adicionais (Addinfos), unificando as informações em tabelas por Famílias de Produtos; Criação de estrutura contendo as regras de descartes, qualidade e pareamento de reportes, em aderência aos dados demonstrados no Dashboar d de Monitoramento Operacional e tickets emitidos; Criação de página de Changelog , permitindo acompanhamento das mudanças na documentação. | Tabelas de additionalInfo espalhadas, regras não documentadas | Área de documentação funcional estruturada para comportar tabela unificada de additionalInfo e documentação de regras |
| Evolução da estrutura Swagger  no padrão Open API, disponível na Área do Desenvolvedor | Evolução | Disponibilização de novo swagger | Principais benefícios e entregáveis: Acelerador de integrações, com a geração de docs ( Swagger  UI/ReDoc), SDKs e stubs automaticamente, viabilizando a geração de contratos de testes; Possibilidade de automação e validação de entradas/saídas com JSON Schema , mitigando riscos de quebras antes da publicação em produção; Remoção de ambiguidades na escrita e fonte única para áreas e perfis envolvidos; Acompanhamento do versionamento das mudanças; Maior portabilidade e menor acoplamento, independentemente da linguagem/ framework . | Swagger baseado na documentação OpenAPI | Swagger baseado na documentação APIDog |
| Portabilidade de Crédito | Alteração | Obrigatoriedade do campo portabilityId e lista de endpoints | Aprimoramento da documentação funcional na PCM; Inclusão da obrigatoriedade de ingestão do campo PortabilityId em todos os endpoints da API; Atualização dos endpoints  aceitos. Endpoints aceitos pela PCM | portabilityId não era obrigatório em todos os endpoints; lista de endpoints aceitos pela PCM não apresentava os endpoints de Portabilidade de Crédito | portabilityId obrigatório em todos os endpoints; endpoints de Portabilidade de Crédito apresentados na lista de endpoints aceitos pela PCM |
| Novo campo Addinfo statusSummary, que permite o monitoramento da jornada de consentimentos para o público PJ, através do reporte pelos receptores de todos os estados observados na API Resources. | Inclusão | Novo additionalInfo | Tabela de Obrigatoriedade de additionalInfo - Dados Cadastrais e Transacionais | Não existente | additionalInfo statusSummary incluído na API Resources |
| Novo campo Addinfo, que permite observar a Natureza Jurídica e Porte do Cliente PJ, através do reporte do lado cliente no consumo das APIs de consentimentos para recepção de dados cadastrais e de pagamentos. | Inclusão | Novo additionalInfo | Tabela de Obrigatoriedade de additionalInfo - Pagamentos Tabela de Obrigatoriedade de additionalInfo - Dados Cadastrais e Transacionais | Não existente | additionalInfo companyProfileInfo incluído na API Private para Pagamentos e Clientes |
| Novo endpoint  Path /pix/recurring-payments/{originalRecurringPaymentId}/retry de retentativas de pagamentos e Addinfo referencestartDate, para identificação da data prevista para início do ciclo de cobrança dos pagamentos associados à recorrência no Pix Automático. | Inclusão | Novo endpoint e additionalInfo | Endpoints aceitos pela PCM Tabela de Obrigatoriedade de additionalInfo - Pagamentos | Não existente | endpoint /pix/recurring-payments/{originalRecurringPaymentId}/retry incluído na lista de endpoints aceitos pela PCM; additionalInfo referencestartDate incluído na API Private para Pagamentos |
| Novo endpoint  PATCH /consents/{consentId}/pix/payments, para consulta de recursos na API Pagamentos, a partir do identificador do consentimento. | Inclusão | Novo endpoint | Endpoints aceitos pela PCM | Não existente | endpoint /consents/{consentId}/pix/payments incluído na lista de endpoints aceitos pela PCM |
| Novo Fluxo de Ingestão de Reportes para obtenção dos Estados de Pagamentos, com o objetivo de garantir a identificação precisa da liquidação, rejeição e outros estados de pagamentos. | Inclusão | Nova API | Dados relativos aos estados de pagamentos | Não existente | Criação de API de Dados Relativos aos Estados de Pagamento, com a devida documentação funcional |
| Atualização dos endpoints aceitos na PCM, reforçando a necessidade de reporte para os endpoints de investimentos em Dados Transacionais e de Clientes. | Evolução | Lista de endpoints aceitos pela PCM | Endpoints aceitos pela PCM | Lista de endpoints não apresentava os endpoints de investimentos | Lista de endpoints aceitos pela PCM atualizada com os endpoints de investimentos |
| Demais melhorias funcionais | Alteração | Fluxo do HybridFlow atualizado, definições dos campos de Hybridflow | Detalhamento das informações no fluxo Hybrid Flow | | /report-api/v2/hybrid-flow/client/redirect-to-server: Incluída a descrição do campo “uriAuthorizationEndpoint”: Endpoint utilizado para o redirecionamento do usuário conforme cadastrado pela transmissora/detentora no arquivo .well-known/openid-configuration sem qualquer parâmetro introduzido pelo sistema da receptora/iniciadora. Caso a URI tenha mais de 200 caracteres de extensão, truncar. Alterado o campo uriAuthorizationEndpoint no exemplo para " https://auth.banco.com.br/open-banking/Auth " |
| | | | | | /report-api/v2/hybrid-flow/server/redirect-target: Alterado o texto da descrição para "Inclusão de reporte de chegada de usuário em sistema da transmissora/detentora. É ESSENCIAL A LEITURA DO DIAGRAMA DE SEQUÊNCIA PARA O ENTENDIMENTO DE COMO DEVE SER FEITO O REPORTE. Ao enviar um report, a Plataforma vai fazer o processo de validação de maneira síncrona e devolver o resultado dessa validação na resposta. O status HTTP de retorno será 200 caso o reporte enviado seja aceito." Incluída a descrição do campo “uriAuthorizationEndpoint”: Endpoint utilizado para o redirecionamento do usuário conforme cadastrado pela transmissora/detentora no arquivo .well-known/openid-configuration sem qualquer parâmetro introduzido pelo sistema da receptora/iniciadora. Caso a URI tenha mais de 200 caracteres de extensão, truncar Alterado o campo uriAuthorizationEndpoint no exemplo para " https://auth.banco.com.br/openbanking/Auth " |
| | | | | | /report-api/v2/hybrid-flow/server/authenticated Alterado o texto da descrição para "Inclusão de reporte de que o usuário está apto a prosseguir com a autorização do consentimento. Deverá ser enviado após o usuário se autenticar/entrar na área autenticada e antes de autorizar o consentimento. É ESSENCIAL A LEITURA DO DIAGRAMA DE SEQUÊNCIA PARA O ENTENDIMENTO DE COMO DEVE SER FEITO O REPORTE. Ao enviar um reporte, a Plataforma vai fazer o processo de validação de maneira síncrona e devolver o resultado dessa validação na resposta. O status HTTP de retorno será 200 caso o reporte enviado seja aceito." |
| | | | | | /report-api/v2/hybrid-flow/server/redirect-to-client Alterado o campo uri_callback no exemplo para " https://receptora.com.br/open-banking/landing-page " No campo uri_callback, incluída a descrição "Preencher com a uri_callback registrada pelo sistema consumidor durante o DCR/DCM. Caso a URI tenha mais de 200 caracteres de extensão, truncar ." |
| Demais melhorias funcionais | Alteração | Descrição do campo clientIp | Maior detalhamento funcional do campo clientIp. | clientIp estava obrigatório para enrollments | Alterada a documentação de forma a ficar claro que o campo clientip no enrollment é opcional |
| Demais melhorias funcionais | Alteração | Descrição do campo dropReason | Maior detalhamento funcional do campo dropReason | De " * NO_CREDENTIAL: quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado. " | Para " * NO_CREDENTIAL: quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado ou quando o HTTP response code for diferente de 201" |
2025B1800**Data da release:** 01/07/2025**Data do Informa:** 16/06/2025**Número do Informa:** 753
| Contexto | Tipo de alteração | O que foi alterado? | Detalhes | Antes | Depois |
| --- | --- | --- | --- | --- | --- |
| Portabilidade de Crédito | Inclusão | Lançamento da documentação na versão beta | Lançamento da documentação na versão beta, permitindo o entendimento para a ingestão dos reportes a serem monitorados através da PCM | Não existente | Disponibilização da documentação da nova API de Portabilidade de Crédito |
| Tratamento de Conglomerado e Organizações Filhas | Evolução | Tratamento no recebimento de reportes para identificar conglomerados enviando dados de organizações filhas | Solução que possibilitará, a partir de 18/06/2025, a uma organização mãe ou filha o envio de reportes utilizando o certificado válido de qualquer organização pertencente ao conglomerado. | Descarte de reportes devido às organizações filhas não possuírem certificado; não-pareamento de reportes quando as organizações reportam client ou server da organização filha, mas o conglomerado reporta como mãe. | Tratamento no recebimento do reporte, identificando que é uma organização filha utilizando o certificado da organização mãe, eliminando os descartes e problemas de pareamento. |
| Novo additionalInfo nfcPayment | Inclusão | Novo additionalInfo no fluxo da JSR | Inclusão de campo adicional (AdditionalInfo) nfcPayment na PCM: a inclusão do campo no monitoramento permite a identificação do pagamento quando realizado através do método de aproximação no POS (Point of Safe) via NFC (Near Field Communication) no fluxo da JSR. | Não existente | additionalInfo nfcPayment incluído na API Private |
| Alteração no additionalInfo dropReason | Alteração | Novos domínios para o additionalInfo | Adequação dos valores disponíveis do campo (AdditionlInfo) DropReason: a alteração permite a correta distinção, esclarecendo valores previstos para envio no campo | Domínio: NO_CREDENTIAL, NONE | Domínio: NO_AUTHORITY, NO_AUTHORITY_PERSON_MISMATCH, NO_CREDENTIAL, NONE |
| Detalhamento do additionalInfo grantType | Evolução | Descrição do domínio do campo grantType | Detalhamento dos valores disponíveis do campo (AdditionalInfo) GrantType | Não especificado | Domínio: AUTHORIZATION_CODE, REFRESH_TOKEN, CLIENT_CREDENTIALS |
Release 2025A / 2025A11800**Data da release:** 01/04/2025**Data do Informa:** 13/03/2025**Número do Informa:** 709 / 723 / 731 / 752
| Contexto | Tipo de alteração | O que foi alterado? | Detalhes | Antes | Depois |
| --- | --- | --- | --- | --- | --- |
| Novos campos de additionalInfo para PIX Automático | Inclusão | Inclusão de novos campos additionalInfo; criação de tabela de obrigatoriedade de additionalInfo para PIX Automático | Esta atualização possibilitará uma análise mais apurada do serviço, e segue o cronograma de implementação da v2.0.0 da API Pagamentos automáticos (Pix automático), conforme comunicado no Informa #661 | Não existentes | Inclusão dos additionalInfo: amountType interval isfirstPayment hasMinimumAmount​ isRetryAccepted originalRecurringPaymentId paymentReference cancellationReason​ |
| Nova API de Dados Relativos à Quantidade de Consentimentos Ativos e Únicos por clientes | Inclusão | Nova API para recebimento de dados relativos a Estoque de Consentimentos | Apuração dos dados de Estoque de Consentimentos através da PCM, não mais por planilhas autorreportadas. | Dados recebidos via planilha | Dados recebidos pela PCM |
| Chamada da Private API (GET) | Alteração | Alteração na forma de chamada da API | Maior eficiência e aumento de performance do recurso | Chamada pelo reportId | Chamada pelo fapiInteractionId |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Consentimentos > Campos Obrigatórios e Opcionais - CO

---
id: 1211858957
title: Campos Obrigatórios e Opcionais - CO
version: 2
modified: 2025-11-19T12:05:35.186Z
url: /spaces/OF/pages/1211858957/Campos+Obrigat+rios+e+Opcionais+-+CO
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Consents API

| Campo | Definição | Obrigatório | Tipo | Regra de preenchimento | Métodos | Domínio | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| date | Data UTC no formato ISO8601 (YYYY-MM-DD) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. Deve conter a data a que se referem os dados de consentimento enviados na mensagem | Sim | string <date-time> | | POST | | 10 | YYYY-MM-DD | 2021-11-11 |
| orgId | Organização de envio da mensagem referente ao papel do Transmissor ou Receptor, conforme Role, a ser preenchido a partir do Certificado | Sim | string <uuid> | | POST | | 36 | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| role | Indica se o reporte que está sendo enviado apresenta a visão do SERVER ou do CLIENT | Sim | enum<string> | | POST | CLIENT, SERVER | | | CLIENT |
| scope | Escopo do reporte | Sim | enum<string> | | POST | DADOS | | | DADOS |
| totalCustomerPF | Total de clientes PF com consentimentos ativos | Não | number | | POST | | | | 50 |
| totalCustomerPJ | Total de clientes PJ com consentimentos ativos | Não | number | | POST | | | | 100 |
| consentsStockList | Lista de estoque de consentimentos. Caso não haja estoque a reportar, enviar o array vazio. Os itens indentados abaixo pertencem ao objeto consentsStockList e seguem as mesmas regras de obrigatoriedade | Sim | array [object {3}] | | POST | | | | |
| clientOrgId | Identificador da organização de onde a chamada foi disparada | Não | string <uuid> | | POST | | 36 | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| serverOrgId | Identificador da organização para onde a chamada foi feita | Não | string <uuid> | | POST | | 36 | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| totalActiveConsents | Estoque total de consentimentos ativos, correspondendo ao número de consentimentos totais válidos até a data de referência. | Não | number | | POST | | | | 30 |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Consentimentos > Estoque de Consentimentos Ativos

---
id: 1084325889
title: Estoque de Consentimentos Ativos
version: 2
modified: 2025-08-29T12:27:50.395Z
url: /spaces/OF/pages/1084325889/Estoque+de+Consentimentos+Ativos
---

## Objetivo
Disponibilização de uma nova API dedicada à obtenção de dados quantitativos de consentimentos ativos e únicos por tipo de cliente. Esta solução permite que as instituições realizem o autorreporte via PCM, garantindo precisão e conformidade com a IN 588, fornecendo uma perspectiva completa e transparente sobre o fluxo de dados e consentimentos para cada instituição.  
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.  **Estoque de Consentimento**São os consentimentos que se encontram ativos e foram reportados por determinada organização, separados pelo tipo de pessoa (Física ou Jurídica), correspondentes aos dados dos clientes e transacionais (Fases 2 e 4b).  **Client e Server**Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.   
## Descrição funcional da API

| Campo | Descrição |
| --- | --- |
| Data de Referência¹ | Deve conter a data a que se referem os dados de consentimento enviados na mensagem. Formato: AAAA-MM-DD |
| organisationId¹ | Organização de envio da mensagem referente ao papel do Transmissor ou Receptor, conforme Role , a ser preenchido a partir do Certificado |
| Papel (Role)¹ | A ser preenchido com “CLIENT” ou “SERVER” |
| Escopo de Dados¹ | A ser preenchido com a Role “DADOS” |
| Total de clientes únicos PF | A ser preenchido com o total de clientes PF com consentimentos ativos. Formato: numérico inteiro natural |
| Total de clientes únicos PJ | A ser preenchido com o total de clientes PJ com consentimentos ativos. Formato: numérico inteiro natural |
| Lista de Estoque de Consentimentos, composta pelos campos¹: | |
| organisationId do CLIENT¹ | Identificador da Organização de onde a chamada foi realizada |
| organisationId do SERVER¹ | Identificador da Organização para onde a chamada foi realizada |
| Quantidade de consentimentos ativos¹ | Estoque total de consentimentos ativos, correspondendo ao número de consentimentos totais válidos até a data de referência |
¹ Campos com preenchimento obrigatório para que a mensagem seja considerada válida na ingestão  
## Detalhes operacionais

| Parâmetro | Regra | Justificativa |
| --- | --- | --- |
| Frequência de envio | Diária | Alinha-se com a prática atual das instituições que enviam reportes diários  Proporciona dados mais atualizados e granulares  Facilita a detecção de tendências e anomalias |
| Período de Referência | Diário, das 00:00:00 às 23:59:59 | Permite às instituições consolidar dados de um dia completo |
| Política de Deduplicação | Se uma instituição enviar dados com as mesmas quantidades dentro de um período de 24 horas, considerar apenas o primeiro envio  Permitir atualizações se houver alteração nos números | Evita duplicações acidentais  Permite correções em caso de erros no reporte inicial |
| Prazo Máximo de Reporte | Até 08h00 do próximo dia da Data de Referência | Garante que os dados sejam processados em um pipeline uniforme e respeitem a janela única de processamento |
 
## Regras de validação

- Verificar se o organisationId informado é válido

- Garantir que a Data de Referência seja sempre anterior ou igual à Data de Envio

- Assegurar que a quantidade de consentimentos únicos para PF/PJ não exceda a quantidade de consentimentos ativos

- Confirmar que o envio dos dados relativos a uma Data de Referência ocorreu até D+1 às 08h00
 
## Documentação da API
Documentação da API - PCM

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Consentimentos > Regras de Validação - CO

---
id: 1212153869
title: Regras de Validação - CO
version: 2
modified: 2026-02-09T18:16:02.687Z
url: /spaces/OF/pages/1212153869/Regras+de+Valida+o+-+CO
---

v 1.01**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Estoque de Consentimentos

| Campo | Regra |
| --- | --- |
| totalActiveConsents | A soma das quantidades de estoques únicos PF e PJ (totalCustomerPF e totalCustomerPJ) não pode ser superior à soma dos estoques ativos |
| Data do consentimento | Deve haver envio dário |
| clientOrgId | Deve ser uma organização válida dentro do ecossistema Open Finance, e em casos de conglomerados, não pode ser diferente da organização reportadora quando o role for CLIENT |
| serverOrgId | Deve ser uma organização válida dentro do ecossistema Open Finance, e em casos de conglomerados, não pode ser diferente da organização reportadora quando o role for SERVER |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Abertos > Campos Obrigatórios e Opcionais - DA

---
id: 1211334657
title: Campos Obrigatórios e Opcionais - DA
version: 2
modified: 2025-11-19T11:43:20.216Z
url: /spaces/OF/pages/1211334657/Campos+Obrigat+rios+e+Opcionais+-+DA
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Opendata API

| Campo | Definição | Obrigatório | Tipo | Métodos | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| additionalInfo | Informações adicionais sobre o reporte deste endpoint/método. Possui característica variável. As regras de preenchimento estão na documentação funcional em Regras de Obrigatoriedade (additionalInfo) - DA Caso não exista o campo enviar como um objeto vazio: {} | Sim | object | POST | | | | | | |
| endpoint | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar presente na lista de endpoints aceitos pela PCM para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original. | Sim | string | POST | Endpoints aceitos pela PCM | | | | | /open-banking/opendata-acquiring-services/v1/businesses |
| httpMethod | Método HTTP da solicitação. | Sim | string | POST | DELETE, GET, PATCH, POST, PUT | | | | | GET |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. | Sim | integer <int16> | POST | | | | | | 120 |
| statusCode | Status de retorno HTTP da solicitação. | Sim | integer <int32> | POST | | | 200 | 599 | | 200 |
| timestamp | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. | Sim | string <date-time> | POST | | 28 | | | YYYY-MM-DDTHH:mm:ss.sssZ | 2021-11-11T18:08:08.278Z |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Abertos > Regras de Descarte - DA

---
id: 1212514305
title: Regras de Descarte - DA
version: 1
modified: 2025-11-18T12:36:33.737Z
url: /spaces/OF/pages/1212514305/Regras+de+Descarte+-+DA
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Opendata API

| Campo | Regra |
| --- | --- |
| endpoint | Informação não enviada Invalid type: endpoint: Required: campo endpoint ausente Conteúdo inválido Validation error:{endpoint incorreto}: conteúdo do campo endpoint inválido Missing property, endpoint can't be empty: campo endpoint não pode estar vazio Unlisted endpoint: endpoint: endpoint must be listed: endpoint enviado não é válido (consultar a tabela de endpoints aceitos pela PCM) |
| httpMethod | Informação não enviada Invalid type: httpMethod: Required: campo httpMethod ausente Conteúdo inválido Invalid field value, httpMethod: httpMethod must be in enum: conteúdo do campo httpMethod inválido Invalid value: httpMethod: Invalid enum value. Expected ‘GET' | 'POST' | 'PUT' | 'PATCH' | 'DELETE', received 'xxxx’: conteúdo do campo httpMethod inválido, recebido conteúdo não determinado no enum do campo Missing property, httpMethod can't be empty: conteúdo do campo httpMethod não pode estar vazio |
| processTimespan | Informação não enviada Invalid type: processTimespan: Required: campo processTimespan ausente Conteúdo inválido Invalid field value, processTimespan: process timespan must be a positive number: campo timestamp deve se um número positivo Invalid type: processTimespan: Expected number, received 'xxxx': conteúdo do campo processTimespan inválido; esperado número Invalid value: processTimespan must be greater than zero: campo timestamp deve ser maior do que zero |
| statusCode | Informação não enviada Invalid type: statusCode: Required: campo statusCode ausente Conteúdo inválido Invalid type: statusCode: Expected number, received ‘xxxx’: conteúdo do campo statusCode inválido; esperado número Invalid value: statusCode must be between 200 and 599: campo statusCode com valor inválido, deve estar entre 200 e 599 |
| timestamp | Conteúdo inválido Timestamp is older than 7 days: campo timestamp com data posterior a 7 dias Validation error: Invalid timestamp format: formato do campo timestamp inválido Validation error: Report is too old: campo timestamp com data posterior a 7 dias |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Abertos > Regras de Obrigatoriedade (additionalInfo) - DA

---
id: 1212088335
title: Regras de Obrigatoriedade (additionalInfo) - DA
version: 4
modified: 2025-12-29T20:01:39.213Z
url: /spaces/OF/pages/1212088335/Regras+de+Obrigatoriedade+additionalInfo+-+DA
---

v 1.00**Guia de leitura**
1. Se o campo não está listado, é porque não existe a obrigatoriedade de enviá-lo.
2. Nos endpoints, a referência “v x ” indica que se aplicam às versões listadas na coluna “Versões”. Por exemplo, Endpoint “open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId}” e Versões “v1 v2” significa que o endpoint é válido para as versões 1 e 2.
Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Dados Abertos

| Campo | Grupo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| clientIp | Atendimento | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | SERVER | Todos | GET | /open-banking/channels/v x /branches /open-banking/channels/v x /electronic-channels /open-banking/channels/v x /phone-channels /open-banking/channels/v x /banking-agents | v1 |
| tokenId | Atendimento | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/channels/v x /branches /open-banking/channels/v x /electronic-channels /open-banking/channels/v x /phone-channels /open-banking/channels/v x /banking-agents | v1 |
| clientIp | Câmbio | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | Todos | Todos | GET | /open-banking/exchange/v x /online-rates /open-banking/exchange/v x /vet-values | v1 |
| tokenId | Câmbio | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/exchange/v x /online-rates /open-banking/exchange/v x /vet-values | v1 |
| clientIp | Credenciameto | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | Todos | Todos | GET | /open-banking/acquiring-services/v x /personals /open-banking/acquiring-services/v x /businesses | v1 |
| tokenId | Credenciameto | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/acquiring-services/v x /personals /open-banking/acquiring-services/v x /businesses | v1 |
| clientIp | Investimentos | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | Todos | Todos | GET | /open-banking/investments/v x /funds /open-banking/investments​/v x /bank-fixed-incomes /open-banking/investments​/v x /credit-fixed-incomes /open-banking/investments​/v x /variable-incomes /open-banking/investments​/v x /treasure-titles | v1 |
| tokenId | Investimentos | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/investments/v x /funds /open-banking/investments​/v x /bank-fixed-incomes /open-banking/investments​/v x /credit-fixed-incomes /open-banking/investments​/v x /variable-incomes /open-banking/investments​/v x /treasure-titles | v1 |
| clientIp | Previdência | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | Todos | Todos | GET | /open-banking/pension/v x /risk-coverages /open-banking/pension/v x /survival-coverages | v1 |
| tokenId | Previdência | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/pension/v x /risk-coverages /open-banking/pension/v x /survival-coverages | v1 |
| clientIp | Produtos e Serviços | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | SERVER | Todos | GET | /open-banking/products-services/v x /personal-accounts /open-banking/products-services/v x /business-accounts /open-banking/products-services/v x /personal-loans /open-banking/products-services/v x /business-loans /open-banking/products-services/v x /personal-financings /open-banking/products-services/v x /business-financings /open-banking/products-services/v x /personal-invoice-financings /open-banking/products-services/v x /business-invoice-financings /open-banking/products-services/v x /personal-credit-cards /open-banking/products-services/v x /business-credit-cards /open-banking/products-services/v x /personal-unarranged-account-overdraft /open-banking/products-services/v x /business-unarranged-account-overdraft | v1 |
| tokenId | Produtos e Serviços | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/products-services/v x /personal-accounts /open-banking/products-services/v x /business-accounts /open-banking/products-services/v x /personal-loans /open-banking/products-services/v x /business-loans /open-banking/products-services/v x /personal-financings /open-banking/products-services/v x /business-financings /open-banking/products-services/v x /personal-invoice-financings /open-banking/products-services/v x /business-invoice-financings /open-banking/products-services/v x /personal-credit-cards /open-banking/products-services/v x /business-credit-cards /open-banking/products-services/v x /personal-unarranged-account-overdraft /open-banking/products-services/v x /business-unarranged-account-overdraft | v1 |
| clientIp | Seguros | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | Todos | Todos | GET | /open-banking/opendata-insurance/v x /personals | v1 |
| tokenId | Seguros | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/opendata-insurance/v x /personals | v1 |
| clientIp | Titulos de Capitalização | Endereço IPv4 ou IPv6 do client que fez a requisição | Deve ser preenchido com o Endereço IPv4 ou IPv6 do client que fez a requisição | Todos | Todos | GET | /open-banking/capitalization-bonds/v x /bonds | v1 |
| tokenId | Titulos de Capitalização | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/capitalization-bonds/v x /bonds | v1 |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Abertos > Regras de Validação - DA

---
id: 1212088361
title: Regras de Validação - DA
version: 1
modified: 2025-11-18T12:35:58.755Z
url: /spaces/OF/pages/1212088361/Regras+de+Valida+o+-+DA
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Dados Abertos

| Campo | Regra |
| --- | --- |
| clientIp | SE Role = CLIENT E endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, %/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/% , %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o clientIp for nulo, retorna Nulo Se o clientIp for vazio, retorna Vazio |
| endpoint | Se o endpoint for nulo, retorna Nulo Se o endpoint for vazio, retorna Vazio |
| httpMethod | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o httpMethod for nulo, retorna Nulo Se o httpMethod for vazio, retorna Vazio |
| processTimespan | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o processTimespan for nulo, retorna Nulo Se o processTimespan for vazio, retorna Vazio |
| statusCode | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o statusCode for nulo, retorna Nulo Se o statusCode for vazio, retorna Vazio |
| timestamp | SE Endpoint = %/products-services/%, %/channels/%, %/capitalization-bonds/%, '%/opendata-investments/%, %/opendata-capitalization%, %/opendata-exchange/%, %/opendata-acquiring-services/%, %/opendata-pension/% ou %/opendata-insurance/% E método = GET ENTÃO Se o timestamp for nulo, retorna Nulo Se o timestamp for vazio, retorna Vazio |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Cadastrais e Transacionais > Campos Obrigatórios e Opcionais - DC

---
id: 1211760641
title: Campos Obrigatórios e Opcionais - DC
version: 5
modified: 2026-01-23T20:55:36.537Z
url: /spaces/OF/pages/1211760641/Campos+Obrigat+rios+e+Opcionais+-+DC
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Private API

| Campo | Definição | Obrigatório | Tipo | Regra de preenchimento | Roles | Métodos | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| additionalInfo | Informações adicionais sobre o reporte deste endpoint/método. Possui característica variável. As regras de preenchimento estão na documentação funcional em Regras de Obrigatoriedade (additionalInfo) - DC . | Client: Sim Server: Não | object | Caso não exista o campo enviar como um objeto vazio: {} | CLIENT SERVER | POST GET | | | | | | |
| clientOrgId | Identificador da organização de onde a chamada foi disparada | Sim | string <uuid> | | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 56411f7e-d58b-44a8-8a2b-ff326d3f2955 |
| clientSSId | Identificador do software statement de onde a chamada foi disparada. A PCM garante que foi esta orgId que obteve o token de acesso utilizado neste reporte. | Sim | string <uuid> | | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 84570da9-567b-4201-9b77-c715bc5bffde |
| correlationId | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. | Não | string | | CLIENT | POST | | 100 | | | ^[- /:_.',0-9a-zA-Z]{0,100}$ | uGQHwNupARo7I9E2PLJZph18a0M9y7DcUe7ITt3DqUOJd9NVjnskxf2 |
| createdAt | Carimbo do tempo do momento da criação do registro | Não | string <date-time> | | CLIENT SERVER | GET | | 28 | | | | |
| endpoint | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar presente na lista de endpoints aceitos pela PCM para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. | Sim | string <uri> | Identificação do Endpoint: Deve ser preenchido com o identificador padronizado do endpoint, conforme uma lista (ENUM) predefinida. Não usar o caminho real: É fundamental NÃO utilizar o caminho completo da requisição original, que inclui dados variáveis (ex: IDs). Exemplo: Se a requisição foi para /open-banking/credit-cards-accounts/v1/accounts/123456789/transactions, o valor a ser enviado no endpoint deve ser /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions. O dado real 123456789 não deve ser enviado no campo endpoint. | CLIENT SERVER | POST GET | Endpoints aceitos pela PCM | | | | | /open-banking/consents/v2/consents |
| endpointUriPrefix | Endereço do servidor de destino da chamada, incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: https://{host}/{prefixo}, sendo: host: endereço FQDN do servidor de destino prefixo: toda a parte do path que vem antes da string /open-banking | Sim | string | Exemplos: Para uma requisição em `https://openbanking.instituicao-1.com.br/opbk/open-banking/products-services/v1/business-accounts` , o dado a ser enviado é `https://openbanking.instituicao-1.com.br/opbk` . Para uma requisição em `https://openbanking.instituicao-2.com.br/open-banking/products-services/v1/business-accounts` , o dado a ser enviado é `https://openbanking.instituicao-1.com.br/` . Nos reportes relativos aos endpoints /token e /register este campo deverá conter a URL inteira do request. Exemplos: `https://oauth2.cartaodummy.opf.instituicao/as/token.oauth2` `https://instituicao.com.br/orgs/instituicao/reg` | CLIENT | POST GET | | 200 | | | ^[- /:_.',0-9a-zA-Z]{0,200}$ | https://openbanking.instituicao-1.com.br/opbk |
| fapiInteractionId | UUID RFC4122 que identifica uma transação específica entre dois participantes no ecossistema Open Finance. Este identificador é derivado do header HTTP x-fapi-interaction-id, conforme especificação RFC4122 para geração de identificadores únicos universais. Serve como chave de correlação fundamental para rastreabilidade, auditoria e conciliação de transações entre instituições participantes. Mais informações em Cabeçalhos HTTP na documentação de produtos do Open Finance Brasil | Sim | string <uuid> | Para CLIENT: OBRIGATÓRIO em todos os cenários onde o x-fapi-interaction-id foi gerado, incluindo respostas com status 4xx (incluindo 408 - timeout), respostas com status 5xx recebidas e transações completadas com sucesso. Para SERVER: OBRIGATÓRIO quando o x-fapi-interaction-id foi recebido na requisição ou quando o Server gerou o x-fapi-interaction-id conforme especificação da API de Produto. Falhas de aplicação, validação, autorização, timeout, indisponibilidade de dependências ou erros internos (5xx) NÃO caracterizam, por si só, falha crítica para fins de ausência do x-fapi-interaction-id, desde que a requisição tenha sido recebida pelo Server. Nota: A ausência do fapiInteractionId compromete significativamente a capacidade de correlação e auditoria das transações no ecossistema Open Finance | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| httpMethod | Método HTTP da solicitação. | Sim | enum<string> | | CLIENT SERVER | POST GET | DELETE, GET, PATCH, POST, PUT | | | | | GET |
| pairedReportId | Esse atributo indica o reportId do registro que forma uma correlação com o presente registro. Se essa informação existir, o status do registro atual deverá ser PAIRED. | Não | string <uuid> | | CLIENT SERVER | GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 9a97c2df-b261-4fc2-aa66-d1b5168397da |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. | Sim | integer <int16> | | CLIENT SERVER | POST GET | | | | | | 120 |
| reportId | Identificador único do registro criado na Plataforma de Coleta de Métricas. | Não | string <uuid> | | CLIENT SERVER | GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | |
| role | Indica se o reporte que está sendo enviado apresenta a visão do server ou do client. | Sim | enum<string> | | CLIENT SERVER | POST GET | CLIENT, SERVER | | | | | CLIENT |
| serverOrgId | Identificador da organização para onde a chamada foi feita | Sim | string <uuid> | | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| status | Informa o status do registro de reporte. | Não | enum<string> | DISCARDED : O status DISCARDED indica que o reporte enviado pelo participante foi rejeitado pela PCM. O motivo do descarte será enviado com a resposta, podendo ser por conta de um reporte inválido ou por um erro no processamento. Não é possível modificar um reporte DISCARDED, portanto o reportador deverá corrigir o registro que apresentou erro e reenviar via POST. SINGLE : O status SINGLE indica que o reporte em questão não tem uma contraparte. Ele é utilizado em casos onde a conciliação entre dois reportes não é possível. ACCEPTED : O status ACCEPTED indica que a validação de formato do reporte não tem erros e este será enviado para processamento. UNPAIRED : O status UNPAIRED significa que o reporte atual não possui uma correspondência em outro reporte através do atributo fapiInteractionId. Indica um reporte divergente. PAIRED_INCONSISTENT : O status PAIRED_INCONSISTENT significa que o reporte corrente possui uma contraparte com o mesmo fapiInteractionId, mas os demais dados estão inconsistentes. Indica um reporte divergente. PAIRED : Indica que o reporte tem uma contraparte com o mesmo fapiInteractionId e os demais dados estão conciliados. Representa o estado final desejado em um fluxo correto. | CLIENT SERVER | GET | ACCEPTED, DISCARDED, PAIRED, PAIRED_INCONSISTENT, SINGLE, UNPAIRED | | | | | PAIRED |
| statusCode | Status de retorno HTTP da solicitação. | Sim | integer <int32> | No caso de ocorrer um timeout client side, preencher com um código 403. | CLIENT SERVER | POST GET | | | 200 | 599 | | 200 |
| timestamp | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. | Sim | string <date-time> | | CLIENT SERVER | POST GET | | 28 | | | YYYY-MM-DDTHH:mm:ss.sssZ | 2021-11-11T18:08:08.278Z |
| updatedAt | Carimbo do tempo do momento da última atualização do registro | Não | string <date-time> | | CLIENT SERVER | GET | | 28 | | | | |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Cadastrais e Transacionais > Jornada Otimizada - DC

---
id: 1275232257
title: Jornada Otimizada - DC
version: 1
modified: 2025-11-18T12:46:20.131Z
url: /spaces/OF/pages/1275232257/Jornada+Otimizada+-+DC
---

v 1.00
## Objetivo
Com o intuito de monitorar a Jornada Otimizada, faz-se necessária a inclusão de dois novos additionalInfo nos reportes da PCM, de forma a diferenciar consentimentos primários e secundários, e relacionar consentimentos vinculados.Para consultar os detalhes técnicos da implementação destes additilnalInfo, por favor consultar a página Documentação da API - PCM 
## journeyIsLinked

- Descrição: indica que o consentimento é vinculado a outro em uma Jornada Otimizada
- Dados Cadastrais e Transacionais ⁠ Regra de preenchimento: Deve ser preenchido com a string obtida no campo journey.isLinked, após a chamada inicial na API “POST /consents” se o parâmetro isLinked estiver preenchido na requisição no contexto de Jornada Otimizada. Exemplo: true  Roles: CLIENT  Métodos: POST e GET Http Code: Todos endpoints:  /open-banking/consents/v3/consents /open-banking/consents/v3/consents/{consentId}
**Exceções de reporte:** 
- Não deve ser reportado o campo journeyIsLinked ou journeyLinkId quando: O consentimento for criado fora do contexto de Jornada Otimizada, ou seja, quando não houver indicação de journey.isLinked=true no payload da criação do consentimento O consentimento for do tipo convencional (ex.: consents isolados, enrollments isolados, recurring-consents isolados), sem vínculo com outro consentimento
- Nestes casos, a transmissora/detentora deve omitir os campos journeyIsLinked e journeyLinkId no reporte à PCM

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Cadastrais e Transacionais > Regras de Descarte - DC

---
id: 1212383245
title: Regras de Descarte - DC
version: 1
modified: 2025-11-18T12:43:49.707Z
url: /spaces/OF/pages/1212383245/Regras+de+Descarte+-+DC
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Private API - Dados Cadastrais e Transacionais

| Campo | Regra |
| --- | --- |
| additionalInfo | Informação não enviada Invalid type: additionalInfo: Required: additonalInfo não enviado; na ausência de additonalInfo, deve ser informada uma matriz vazia Conteúdo inválido additionalInfo should not be empty: additonalInfo vazio; na ausência de additonalInfo, deve ser informada uma matriz vazia Invalid type: additionalInfo: Expected object, received ‘xxxx’: tipo do campo additionalInfo inválido; esperado objeto |
| clientOrgId | Informação não enviada Invalid type: clientOrgId: Required: campo ClientOrgId ausente Missing property: clientOrgId or serverOrgId: campo clientOrgid ausente Conteúdo inválido clientOrgId 'xxxx' is invalid to role 'CLIENT': clientOrgId informado é inválido para o role CLIENT Invalid field type, clientOrgId must be a valid UUID: clientOrgId não está no formato UUID Invalid type: clientOrgId: Expected string, received null: conteúdo do campo clientOrgId inválido; esperado string, recebido nulo Requester id mismatch with clientOrgId: clientOrgId informado no role CLIENT não é a mesma organização reportadora (PAR-100) Validation error: clientOrgId: conteúdo do campo clientOrgId inválido |
| clientSSId | Informação não enviada Invalid type: clientSSId: Required: campo clientSSId ausente Missing property: clientSSId: campo clientSSId ausente Conteúdo inválido Invalid field type, clientSSId should not be empty: campo clientSSId não pode estar vazio Invalid format: clientSSId: Invalid uuid: formato do clientSSId inválido, deve estar no formato UUID Invalid format: Unrecognized key(s) in object: 'clientSSId': conteúdo do campo clientSSId inválido Invalid type: clientSSId: Expected string, received null: conteúdo do campo clientSSId inválido; esperado string, recebido nulo Invalid value: Client SSID not found in combined org IDs: campo clientSSId inválido, não encontrado na combinação de org IDs |
| correlationId | Conteúdo inválido Invalid format: correlationId: Invalid correlationId format: formato do correlationId inválido (não pode ter mais de 100 caracteres) |
| endpoint | Informação não enviada Invalid type: endpoint: Required; validation error: undefined: campo endpoint ausente Conteúdo inválido Missing property, endpoint can't be empty: campo endpoint não pode estar vazio Unlisted endpoint: endpoint enviado não é válido (consultar a tabela de endpoints aceitos pela PCM) |
| endpointUriPrefix | Informação não enviada Invalid type: endpointUriPrefix: Required: campo endpointUriPrefix ausente Conteúdo inválido Invalid format: : Unrecognized key(s) in object: 'endpointUriPrefix': conteúdo do campo endpointUriPrefix inválido |
| fapiInteractionId | Informação não enviada Invalid field value fapiInteractionId can't be empty for status 408 or 500: fapiInteractionId deve ser informado para status 408 ou 500 Missing property: fapiInteractionId is required: campo fapiInteractionId ausente Missing property, fapiInteractionId is not provided: campo fapiInteractionId ausente Conteúdo inválido Invalid format: fapiInteractionId must match format "uuid”: campo fapiInteractionId com formato inválido (UUID) ou com menos de 36 caracteres Invalid format: : Unrecognized key(s) in object: 'fapiinteractionid': conteúdo do campo fapiInteractionId inválido Invalid type: fapiInteractionId mismatch. Ensure the ID is not "00000000-0000-0000-0000-000000000000.": formato do campo fapiInteractionId inválido Invalid type: fapiInteractionId: Expected string, received ‘xxxx’: tipo do campo fapiInteractionId inválido; esperado string |
| httpMethod | Informação não enviada Invalid type: httpMethod: Required: campo httpMethod ausente Conteúdo inválido Invalid format: : Unrecognized key(s) in object: 'httpmethod': conteúdo do campo httpMethod inválido Invalid value: httpMethod: Invalid enum value. Expected ‘GET' | 'POST' | 'PUT' | 'PATCH' | 'DELETE', received 'HEAD’: conteúdo do campo httpMethod inválido, recebido conteúdo não determinado no enum do campo |
| processTimespan | Informação não enviada Invalid type: processTimespan: Required: campo processTimespan ausente Conteúdo inválido Invalid type: processTimespan: Expected number, received ‘xxxx’: conteúdo do campo processTimespan inválido; esperado número Invalid value: processTimespan must be greater than zero: campo processTimespan deve ter valor maior do que zero |
| role | Informação não enviada Invalid type: role: Required campo role ausente Conteúdo inválido Invalid value: role: Invalid enum value. Expected 'SERVER' | 'CLIENT', received 'xxxx': conteúdo do campo role inválido, recebido conteúdo não determinado no enum do campo |
| serverOrgId | Informação não enviada Invalid type: serverOrgId: Required; missing property: serverOrgId: campo serverOrgId ausente Missing property: clientOrgId or serverOrgId : serverOrgId ausente Missing property: serverOrgId: campo serverOrgId ausente Conteúdo inválido Invalid field type, serverOrgId must be a valid UUID: serverOrgId não está no formato UUID Requester id mismatch with serverOrgId: serverOrgId informado no role SERVER não é a mesma organização reportadora (PAR-100) Requester mismatch: serverOrgId: serverOrgId informado no role SERVER não é a mesma organização reportadora (PAR-100) serverOrgId 'xxxx' is invalid to role 'SERVER': serverIrgId informado é inválido para o role SERVER |
| status (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.status: Expected string, received ‘xxxx’: tipo do campo status inválido; esperado string |
| statusCode | Informação não enviada Invalid type: statusCode: Required: campo statusCode ausente Conteúdo inválido Invalid type: statusCode: Expected number, received ‘xxxx’: conteúdo do campo statusCode inválido; esperado número Invalid value: statusCode must be between 200 and 599: campo statusCode com valor menor do que 200 ou maior do que 599 Missing property, statusCode can't be empty: campo statusCode não pode estar vazio |
| timestamp | Conteúdo inválido Error not mapped or not expected by validations: Report is too old: campo timestamp com data passada de 7 dias Invalid format: timestamp: Invalid date: conteúdo do campo timestamp inválidlo Missing property, timestamp can't be empty: campo timestamp não pode estar vazio Timestamp is older than 7 days: campo timestamp com data passada de 7 dias Timestamp of report is too old: campo timestamp com data passada de 7 dias Validation error: Report is too old: campo timestamp com data passada de 7 dias |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Cadastrais e Transacionais > Regras de Obrigatoriedade (additionalInfo) - DC

---
id: 1211891728
title: Regras de Obrigatoriedade (additionalInfo) - DC
version: 7
modified: 2026-01-29T19:51:02.563Z
url: /spaces/OF/pages/1211891728/Regras+de+Obrigatoriedade+additionalInfo+-+DC
---

v 1.03**Guia de leitura**
1. Se o campo não está listado, é porque não existe a obrigatoriedade de enviá-lo.
2. Nos endpoints, a referência “v x ” indica que se aplicam às versões listadas na coluna “Versões”. Por exemplo, Endpoint “open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId}” e Versões “v1 v2” significa que o endpoint é válido para as versões 1 e 2.
Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Dados Cadastrais e Transacionais

### Câmbio

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos | GET | /open-banking/exchanges/v x /operations /open-banking/exchanges/v x /operations/{operationId} /open-banking/exchanges/v x /operations/{operationId}/events | v1 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/exchanges/v x /operations /open-banking/exchanges/v x /operations/{operationId} /open-banking/exchanges/v x /operations/{operationId}/events | v1 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Cartão de Crédito

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos | GET | /open-banking/credit-cards-accounts/v x /accounts /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId} /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/limits /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/transactions /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/transactions-current /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/bills /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/bills/{billId}/transactions | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,-.:=@;$_!*''%/?#]+ | urn:bancoex:C1DD33123 |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/credit-cards-accounts/v x /accounts /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId} /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/limits /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/transactions /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/transactions-current /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/bills /open-banking/credit-cards-accounts/v x /accounts/{creditCardAccountId}/bills/{billId}/transactions | v2 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Consentimento

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Domínio | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| companyProfileInfo | Objeto JSON que representa o perfil da Pessoa Jurídica (PJ) do cliente, contendo informações como a natureza jurídica e o porte da empresa, conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O objeto deve conter um objeto de perfil da empresa. As informações de natureza jurídica e porte devem ser obtidas prioritariamente da API oficial Consulta CNPJ (RFB/SERPRO) ou dos Dados Abertos do CNPJ (RFB) , conforme o Dicionário de Dados do CNPJ da Receita Federal. Este objeto deve ser enviado como parte do additionalInfo ao consumir as APIs de criação de consentimento para dados e serviços. Consulta CNPJ — Catálogo de APIs governamentais (API/Swagger) Portal de Dados Abertos (arquivo de dados) | CLIENT | Todos | POST | | /open-banking/consents/v x /consents | v3 | N/A | Objeto JSON | { "naturezaJuridica": "2135", "porteEmpresa": "01" } |
| naturezaJuridica | Código que identifica a constituição jurídico-institucional da entidade, conforme a Tabela de Natureza Jurídica do IBGE, categorizando-a em: Administração pública; Entidades empresariais; Entidades sem fins lucrativos; Pessoas físicas e organizações internacionais; e Outras instituições extraterritoriais. | Obrigatório. O cliente (receptor/iniciador) deve obter essa informação a partir de fontes oficiais (ex., Governo Federal/Dados Abertos/Base CNPJs ou API do SERPRO), com base no CNPJ do usuário, e reportá-la como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | 4 | ^\d{4}$ | 2135 |
| porteEmpresa | Código numérico que identifica o porte da empresa do cliente Pessoa Jurídica (PJ), conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O receptor/iniciador, que detém o CNPJ do usuário, é responsável por obter o código do porte da empresa. Esta informação deve ser consultada e validada a partir de fontes oficiais, como a base de Dados Abertos do CNPJ ou a API do SERPRO, ambas mantidas pelo Governo Federal, e conforme o Dicionário de Dados do CNPJ da Receita Federal. O valor deve ser enviado como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | 2 | ^\d{2}$ | 01 |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos menos 4xx e 5xx para o método POST | DELETE GET POST | | /open-banking/consents/v x /consents /open-banking/consents/v x /consents/{consentId} /open-banking/consents/v x /consents/{consentId}/extensions /open-banking/consents/v x /consents/{consentId}/extends | v3 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| dropReason | Razão pela qual um usuário não conseguiu prosseguir em uma jornada, especificamente no contexto de consentimentos | O campo dropReason deve ser adicionado nas informações do campo additionalInfo que deverá ser enviado no reporte do provedor do serviço consumido (papel SERVER) O reporte deverá ser feito por todos os transmissores de dados e detentoras de conta. Para os casos em que ocorram falhas técnicas que impossibilitem a verificação do CPF/CNPJ (incluindo, mas não se limitando, a erros HTTP 4xx, 500 ou timeout na resposta), o reporte deve ser realizado com o valor NO_CREDENTIAL, Em jornadas de múltipla alçada de pessoas jurídicas, quando a autenticação é bem-sucedida mas os poderes constituídos são insuficientes para finalização do Hybrid Flow, deve-se usar NO_AUTHORITY. NONE : quando o CPF (loggedUser) / CNPJ (businessEntity) possui credencial autenticadora e poderes suficientes para prosseguir o fluxo monitorado - exemplo: PF, cliente, que possui credencial ativa, mas não se autenticou; cliente que se autenticou utilizando a credencial correta. NO_CREDENTIAL : quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado ou quando o HTTP response code for diferente de 201. NO_AUTHORITY : quando o CPF (loggedUser) / CNPJ (businessEntity) consegue se autenticar, mas não dispõe de poderes ou alçadas para prosseguir no fluxo de compartilhamento de dados e serviços. NO_AUTHORITY_PERSON_MISMATCH : quando o CPF (loggedUser) não possui relação com a credencial utilizada na etapa de autenticação do Hybrid Flow - exemplo: consentimento criado para um CPF e autenticado por outro; criado para um CNPJ e autenticado por CPF sem relação com o CNPJ. | SERVER | Todos | POST | NO_AUTHORITY, NO_AUTHORITY_PERSON_MISMATCH, NO_CREDENTIAL, NONE | /open-banking/consents/v x /consents | v3 | | | |
| journeyIsLinked | Indica que o consentimento é vinculado a outro em uma Jornada Otimizada | Deve ser preenchido com a string obtida no campo journey.isLinked, após a chamada inicial na API “POST /consents” se o parâmetro isLinked estiver preenchido na requisição no contexto de Jornada Otimizada Não deve ser reportado o campo journeyIsLinked ou journeyLinkId quando: O consentimento for criado fora do contexto de Jornada Otimizada, ou seja, quando não houver indicação de journey.isLinked=true no payload da criação do consentimento O consentimento for do tipo convencional (ex.: consents isolados, enrollments isolados, recurring-consents isolados), sem vínculo com outro consentimento Nestes casos, a transmissora/detentora deve omitir os campos journeyIsLinked e journeyLinkId no reporte à PCM | CLIENT | Todos | POST GET | TRUE, FALSE | /open-banking/consents/v x /consents /open-banking/consents/v x /consents/{consentId} | v3 | | | |
| personType | Identifica a natureza do solicitante em uma transação ou consentimento. | Se .data.businessEntity estiver preenchido no payload, se estiver então preencher com "PJ", se não estiver então preencher com "PF" | CLIENT | Todos | POST | PESSOA_JURIDICA, PESSOA_NATURAL, PF, PJ | /open-banking/consents/v x /consents | v3 | | | |
| status | Identifica o status atual do recurso (como um consentimento ou um pagamento) que está sendo reportado. | Deve ser preenchido com a mesma string obtida no ".data.status". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | Todos menos 4xx e 5xx | GET | AUTHORISED, AWAITING_AUTHORISATION, REJECTED | /open-banking/consents/v x /consents/{consentId} | v3 | | | |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | | /open-banking/consents/v x /consents /open-banking/consents/v x /consents/{consentId} | v3 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Contas

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos | GET | /open-banking/accounts/v x /accounts /open-banking/accounts/v x /accounts/{accountId} /open-banking/accounts/v x /accounts/{accountId}/balances /open-banking/accounts/v x /accounts/{accountId}/transactions /open-banking/accounts/v x /accounts/{accountId}/transactions-current /open-banking/accounts/v x /accounts/{accountId}/overdraft-limits | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/accounts/v x /accounts /open-banking/accounts/v x /accounts/{accountId} /open-banking/accounts/v x /accounts/{accountId}/balances /open-banking/accounts/v x /accounts/{accountId}/transactions /open-banking/accounts/v x /accounts/{accountId}/transactions-current /open-banking/accounts/v x /accounts/{accountId}/overdraft-limits | v2 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Dados Cadastrais

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos | GET | /open-banking/customers/v x /personal/identifications /open-banking/customers/v x /business/identifications /open-banking/customers/v x /personal/qualifications /open-banking/customers/v x /business/qualifications /open-banking/customers/v x /personal/financial-relations /open-banking/customers/v x /business/financial-relations | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/customers/v x /personal/identifications /open-banking/customers/v x /business/identifications /open-banking/customers/v x /personal/qualifications /open-banking/customers/v x /business/qualifications /open-banking/customers/v x /personal/financial-relations /open-banking/customers/v x /business/financial-relations | v2 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Investimentos

| Campo | Grupo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | Fundos de Investimento | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/funds/v x /investments /open-banking/funds/v x /investments/{investmentId} /open-banking/funds/v x /investments{investmentId}/balances /open-banking/funds/v x /investments{investmentId}/transactions /open-banking/funds/v x /investments{investmentId}/transactions-current | v1 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Renda Fixa Bancária | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/bank-fixed-incomes/v x /investments /open-banking/bank-fixed-incomes/v x /investments/{investmentId} /open-banking/bank-fixed-incomes/v x /investments{investmentId}/balances /open-banking/bank-fixed-incomes/v x /investments{investmentId}/transactions /open-banking/bank-fixed-incomes/v x /investments{investmentId}/transactions-current | v1 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Renda Fixa Crédito | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/credit-fixed-incomes/v x /investments /open-banking/credit-fixed-incomes/v x /investments/{investmentId} /open-banking/credit-fixed-incomes/v x /investments{investmentId}/balances /open-banking/credit-fixed-incomes/v x /investments{investmentId}/transactions /open-banking/credit-fixed-incomes/v x /investments{investmentId}/transactions-current | v1 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Renda Variável | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/variable-incomes/v x /investments /open-banking/variable-incomes/v x /investments/{investmentId} /open-banking/variable-incomes/v x /investments{investmentId}/balances /open-banking/variable-incomes/v x /investments{investmentId}/transactions /open-banking/variable-incomes/v x /investments{investmentId}/transactions-current /open-banking/variable-incomes/v x /broker-notes/{brokerNoteId} | v1 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Títulos do Tesouro Direto | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/treasure-titles/v x /investments /open-banking/treasure-titles/v x /investments/{investmentId} /open-banking/treasure-titles/v x /investments{investmentId}/balances /open-banking/treasure-titles/v x /investments{investmentId}/transactions /open-banking/treasure-titles/v x /investments{investmentId}/transactions-current | v1 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| tokenId | Todos | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | Todos | v1 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Operações de Crédito

| Campo | Grupo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | Adiantamento a Depositantes | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/unarranged-accounts-overdraft/v x /contracts /open-banking/unarranged-accounts-overdraft/v x /contracts/{contractId} /open-banking/unarranged-accounts-overdraft/v x /contracts/{contractId}/warranties /open-banking/unarranged-accounts-overdraft/v x /contracts/{contractId}/payments /open-banking/unarranged-accounts-overdraft/v x /contracts/{contractId}/scheduled-instalments | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Direitos Creditórios Descontados | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/invoice-financings/v x /contracts /open-banking/invoice-financings/v x /contracts/{contractId} /open-banking/invoice-financings/v x /contracts/{contractId}/warranties /open-banking/invoice-financings/v x /contracts/{contractId}/payments /open-banking/invoice-financings/v x /contracts/{contractId}/scheduled-instalments | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Empréstimos | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/loans/v x /contracts /open-banking/loans/v x /contracts/{contractId} /open-banking/loans/v x /contracts/{contractId}/warranties /open-banking/loans/v x /contracts/{contractId}/payments /open-banking/loans/v x /contracts/{contractId}/scheduled-instalments | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | Financiamentos | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/financings/v x /contracts /open-banking/financings/v x /contracts/{contractId} /open-banking/financings/v x /contracts/{contractId}/warranties /open-banking/financings/v x /contracts/{contractId}/payments /open-banking/financings/v x /contracts/{contractId}/scheduled-instalments | v2 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| tokenId | Todos | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | Todos | v2 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Recursos

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos | GET | /open-banking/resources/v x /resources | v3 | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| statusSummary | Sumarização das quantidades de reportes por status. Os itens indentados abaixo pertencem ao objeto statusSummary e seguem as mesmas regras de obrigatoriedade. | Sumarização da quantidade por ENUM observado em data.status | CLIENT | Todos | GET | /open-banking/resources/v x /resources | v3 | | | |
| available | Disponíveis | | CLIENT | Todos | GET | /open-banking/resources/v x /resources | v3 | | | |
| unavailable | Indisponíveis | | CLIENT | Todos | GET | /open-banking/resources/v x /resources | v3 | | | |
| temporary_unavailable | Temporariamente indisponível | | CLIENT | Todos | GET | /open-banking/resources/v x /resources | v3 | | | |
| pending_authorisation | Autorização pendente | | CLIENT | Todos | GET | /open-banking/resources/v x /resources | v3 | | | |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | /open-banking/resources/v x /resources | v3 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Dados Cadastrais e Transacionais > Regras de Validação - DC

---
id: 1212350465
title: Regras de Validação - DC
version: 3
modified: 2025-12-17T19:31:06.668Z
url: /spaces/OF/pages/1212350465/Regras+de+Valida+o+-+DC
---

v 1.01**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Dados Cadastrais e Transacionais

### Câmbio

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/exchanges/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Cartão de Crédito

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/credit-cards-accounts/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Consentimento

| Campo | Regra |
| --- | --- |
| companyProfileInfo | SE Role = CLIENT E personType = PJ ou PESSOA_JURIDICA E endpoint = %consents/v X /consents E método = POST ENTÃO Se naturezaJuridica e porteEmpresa forem simultaneamente nulos ou vazios, retorna Nulo/Vazio Se naturezaJuridica for nulo ou vazio e porteEmpresa estiver preenchido, retorna Incompleto - sem Natureza Juridica Se naturezaJuridica estiver preenchido e porteEmpresa estiver nulo ou vazio, retorna Incompleto - sem Porta da Empresa Se o porteEmpresa não for 00, 01, 03 ou 05, retorna Invalido |
| consentId | SE Role = CLIENT E endpoint = %/consents/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| dropReason | SE Role = SERVER E endpoint = %/consents/v x /consents ou %/payments/v x /consents E método = POST ENTÃO Se o dropReason for nulo, retorna Nulo Se o dropReason for vazio, retorna Vazio Se o dropReason não for NONE, NO_CREDENTIAL, NO_AUTHORITY ou NO_AUTHORITY_PERSON_MISMATCH retorna Invalido |
| personType | SE Role = CLIENT E endpoint = %/consents E método = POST ENTÃO Se o personType for nulo, retorna Nulo Se o personType for vazio, retorna Vazio Se o personType não for PF ou PJ retorna Invalido |
| status | SE Role = CLIENT E endpoint = %/consents/{consentId} E método = GET E statusCode não é 4xx, nem 5xx ENTÃO Se o status for nulo, retorna Nulo Se o status for vazio, retorna Vazio Se o status não for AWAITING_AUTHORISATION, AUTHORISED ou REJECTED retorna Invalido |

### Contas

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/accounts/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Dados Cadastrais

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/customers/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Investimentos

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/investments/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Operações de Crédito

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/unarranged-accounts-overdraft/%, %/invoice-financings/%, %/loans/% ou %/financings/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

### Recursos

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/ressources/% E não é método POST com statusCode 4xx e 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Hybridflow > Campos Obrigatórios e Opcionais - HF

---
id: 1211891714
title: Campos Obrigatórios e Opcionais - HF
version: 2
modified: 2025-11-19T21:01:38.704Z
url: /spaces/OF/pages/1211891714/Campos+Obrigat+rios+e+Opcionais+-+HF
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Hybridflow API

| Campo | Definição | Obrigatório | Tipo | Roles | Métodos | Domínio | Endpoints | Versões | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| clientOrgId | A ser enviado vazio caso o report seja da mesma instituição que obteve o token para uso da PCM e, caso contrário, deve ser preenchido com o organisationId da instituição filha para o qual a instituição mãe está fazendo o report. | Sim | string <uuid> | CLIENT | POST | | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/client/redirect-target-with-errors /report-api/v x /hybrid-flow/client/redirect-target-without-errors | v2 | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 56411f7e-d58b-44a8-8a2b-ff326d3f2955 |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Sim | string | CLIENT SERVER | POST | | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/client/redirect-target-with-errors /report-api/v x /hybrid-flow/client/redirect-target-without-errors /report-api/v x /hybrid-flow/server/redirect-target /report-api/v x /hybrid-flow/server/authenticated /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | 256 | | | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%\/?#]+$ | urn:bancoex:C1DD33123 |
| error | Código de erro retornado no payload do Hybrid Flow | Sim | string | CLIENT | POST | | /report-api/v x /hybrid-flow/client/redirect-target-with-errors | v2 | | | | | |
| os | Sistema Operacional utilizado | Sim | enum<string> | CLIENT SERVER | POST | ANDROID, IOS, LINUX, MACOS, OTHER, UNIX, WINDOWS | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/client/redirect-target-with-errors /report-api/v x /hybrid-flow/client/redirect-target-without-errors /report-api/v x /hybrid-flow/server/redirect-target /report-api/v x /hybrid-flow/server/authenticated /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | | | | | LINUX |
| osVersion | Versão do Sistema Operacional utilizado | Sim | string | CLIENT SERVER | POST | | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/client/redirect-target-with-errors /report-api/v x /hybrid-flow/client/redirect-target-without-errors /report-api/v x /hybrid-flow/server/redirect-target /report-api/v x /hybrid-flow/server/authenticated /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | | | | | 20.04 |
| platform | Identifica a plataforma utilizada | Sim | enum<string> | CLIENT SERVER | POST | APP, BROWSER | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/client/redirect-target-with-errors /report-api/v x /hybrid-flow/client/redirect-target-without-errors /report-api/v x /hybrid-flow/server/authenticated /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | | | | | BROWSER |
| serverOrgId | A ser enviado vazio caso o report seja da mesma instituição que obteve o token para uso da PCM e, caso contrário, deve ser preenchido com o organasationId da instituição filha para o qual a instituição mãe está fazendo o report | Sim | string <uuid> | SERVER | POST | | /report-api/v x /hybrid-flow/server/redirect-target /report-api/v x /hybrid-flow/server/authenticated /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| timestamp | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. | Sim | string <date-time> | CLIENT SERVER | POST | | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/client/redirect-target-with-errors /report-api/v x /hybrid-flow/client/redirect-target-without-errors /report-api/v x /hybrid-flow/server/redirect-target /report-api/v x /hybrid-flow/server/authenticated /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | 28 | | | YYYY-MM-DDTHH:mm:ss.sssZ | 2021-11-11T18:08:08.278Z |
| type | Tipo do fluxo de Hybridflow | Sim | enum<string> | SERVER | POST | AWAITING_HANDOFF, AWAITING_USER_AUTH, AWAITING_REDIRECT_TO_APP | /report-api/v x /hybrid-flow/server/redirect-target | v2 | | | | | |
| type | Tipo do fluxo de Hybridflow | Sim | enum<string> | SERVER | POST | AUTHORISED, REJECTED | /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | | | | | |
| uri_callback | URI específico fornecido como endpoint de retorno de chamada. Preencher com a uri_callback registrada pelo sistema consumidor durante o DCR/DCM. Caso a URI tenha mais de 200 caracteres de extensão, truncar. | Sim | string <uri> | SERVER | POST | | /report-api/v x /hybrid-flow/server/redirect-to-client | v2 | 200 | | | ^[- /:_.',0-9a-zA-Z]{0,200}$ | https://receptora.com.br/open-banking/landing-page |
| uriAuthorizationEndpoint | Endpoint utilizado para o redirecionamento do usuário conforme cadastrado pela transmissora/detentora no arquivo .well-known/openid-configuration sem qualquer parâmetro introduzido pelo sistema da receptora/iniciadora. Caso a URI tenha mais de 200 caracteres de extensão, truncar. | Não | string | CLIENT SERVER | POST | | /report-api/v x /hybrid-flow/client/redirect-to-server /report-api/v x /hybrid-flow/server/redirect-target | v2 | 200 | | | ^[- /:_.',0-9a-zA-Z]{0,200}$ | https://auth.banco.com.br/open-banking/Auth |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Hybridflow > Regras de Descarte - HF

---
id: 1212350477
title: Regras de Descarte - HF
version: 1
modified: 2025-11-18T13:12:11.000Z
url: /spaces/OF/pages/1212350477/Regras+de+Descarte+-+HF
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Hybridflow API

| Campo | Regra |
| --- | --- |
| clientOrgId | Informação não enviada Invalid type: clientOrgId: Required: campo clientOrgId ausente Conteúdo inválido Invalid format: clientOrgId: Invalid uuid: campo clientOrgId vazio, inválido ou com mais de 36 caracteres |
| consentId | Informação não enviada Invalid type: consentId: Required: campo consentId ausente Conteúdo inválido Invalid field type, consentId need match with regex: conteúdo do campo consentId inválido, não está dentro do padrão especificado Invalid field value, consentId can't be empty: campo consentId não pode estar vazio Invalid format: consentId: Invalid: conteúdo do campo consentId inválido Invalid format: consentId: String must contain at least 1 character(s): conteúdo do campo consentId inválido, deve possuir pelo menos um caractere |
| error | Informação não enviada Invalid type: error: Required: campo error ausente Conteúdo inválido error must be a string: conteúdo do campo error inválido, deve ser uma string Invalid type: error: Expected string, received array: conteúdo do campo error inválido; esperado string, recebido array Invalid format: error: String must contain at least 1 character(s): conteúdo do campo error inválido, deve possuir pelo menos um caractere Missing property, error can't be empty: campo error não pode estar vazio |
| os | Informação não enviada Invalid type: os: Required: campo os ausente Conteúdo inválido Invalid field value, os must be a valid enum: conteúdo do campo os inválido, deve ser um enum válido Invalid value: os: Invalid enum value. Expected ‘LINUX' | ‘MACOS' | 'UNIX' | 'WINDOWS' | 'IOS' | 'ANDROID' | 'OTHER', received 'XXX’: conteúdo do campo os inválido, recebido conteúdo não determinado no enum do campo Missing property, os can't be empty: campo os não pode estar vazio |
| osVersion | Conteúdo inválido Invalid field value, osVersion can't be empty: campo osVersion não pode estar vazio Invalid format: osVersion: Invalid: conteúdo do campo osVersion inválido Invalid format: osVersion: String must contain at least 1 character(s): conteúdo do campo osVersion inválido, deve possuir pelo menos um caracter Invalid type: osVersion: Expected string, received ‘xxxx’: conteúdo do campo osVersion inválido, deve ser string |
| platform | Informação não enviada Invalid type: platform: Required: campo platform ausente Conteúdo inválido Invalid field value, platform must be a valid enum: conteúdo do campo platform inválido, recebido conteúdo não determinado no enum do campo Invalid value: platform: Invalid enum value. Expected 'BROWSER' | 'APP', received 'xxxx': conteúdo do campo platform inválido, recebido conteúdo não determinado no enum do campo Missing property, platform can't be empty: campo platform não pode estar vazio |
| serverOrgId | Informação não enviada Invalid type: serverOrgId: Required: campo serverOrgId ausente Conteúdo inválido Invalid field type, serverOrgId must be a valid uuid: conteúdo do campo serverOrgId inválido, deve estar no formato UUID Invalid format: serverOrgId: Invalid uuid: conteúdo do campo serverOrgId inválido, deve estar no formato UUID |
| timestamp | Conteúdo inválido Invalid format: timestamp: Invalid date: conteúdo do campo timestamp inválido, não é uma data válida Validation error: Report is too old: campo timestamp com data passada de 7 dias |
| type | Informação não enviada Invalid type: type: Required: campo type ausente Conteúdo inválido Invalid field value, type must be a valid enum: conteúdo do campo type inválido Invalid value: type: Invalid enum value. Expected ‘AWAITING_HANDOFF' | 'AWAITING_USER_AUTH' | 'AWAITING_REDIRECT_TO_APP' | 'AUTHORISED' | 'REJECTED', received 'xxxx’: conteúdo do campo type inválido, recebido conteúdo não determinado no enum do campo |
| uriAuthorizationEndpoint | Informação não enviada Invalid type: uriAuthorizationEndpoint: Required: campo uriAuthorizationEndpoint ausente Conteúdo inválido Invalid field type, uriAuthorizationEndpoint need match with regex: conteúdo do campo uriAuthorizationEndpoint inválido, não está dentro do padrão especificado Invalid field value, uriAuthorizationEndpoint must be less than 11 characters: conteúdo do campo uriAuthorizationEndpoint não pode ter menos do que 11 caracteres Invalid field value, uriAuthorizationEndpoint must be more than 200 characters: conteúdo do campo uriAuthorizationEndpoint não pode ter mais do que 200 caracteres Invalid format: uriAuthorizationEndpoint: Invalid: conteúdo do campo uriAuthorizationEndpoint inválido Invalid format: uriAuthorizationEndpoint: String must contain at least 1 character(s): campo uriAuthorizationEndpoint deve possuir pelo menos 1 caractere |
| uri_callback | Informação não enviada Invalid type: uri_callback: Required: campo uriAuthorizationEndpoint ausente Conteúdo inválido Invalid field type, uri_callback need match with regex: conteúdo do campo uri_callback inválido, não está dentro do padrão especificado Invalid field value, uri_callback must be less than 11 characters: conteúdo do campo uri_callback não pode ter menos do que 11 caracteres Invalid field value, uri_callback must be more than 200 characters: conteúdo do campo uri_callback não pode ter mais do que 200 caracteres Missing property, uri_callback can't be empty: campo uri_callback não pode estar vazio |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Hybridflow > Regras de Validação - HF

---
id: 1212252198
title: Regras de Validação - HF
version: 1
modified: 2025-11-18T13:06:28.384Z
url: /spaces/OF/pages/1212252198/Regras+de+Valida+o+-+HF
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Hybridflow

| Campo | Regra |
| --- | --- |
| clientOrgId | SE Endpoint = %/client/redirect-to-server, %/client/redirect-target-with-errors ou %/client/redirect-target-without-errors ENTÃO Se o clientOrgId for nulo, retorna Nulo Se o clientOrgId for vazio, retorna Vazio |
| consentId | SE Endpoint = %/client/redirect-to-server, %/client/redirect-target-with-errors, %/client/redirect-target-without-errors, %/server/redirect-target, %/server/authenticated ou %/server/redirect-to-client ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| error | SE Endpoint = %/client/redirect-target-with-errors ENTÃO Se o error for nulo, retorna Nulo Se o error for vazio, retorna Vazio |
| os | SE Endpoint = %/client/redirect-to-server, %/client/redirect-target-with-errors, %/client/redirect-target-without-errors, %/server/redirect-target, %/server/authenticated ou %/server/redirect-to-client ENTÃO Se o os for nulo, retorna Nulo Se o os for vazio, retorna Vazio |
| osVersion | SE Endpoint = %/client/redirect-to-server, %/client/redirect-target-with-errors, %/client/redirect-target-without-errors, %/server/redirect-target, %/server/authenticated ou %/server/redirect-to-client ENTÃO Se o osVersion for nulo, retorna Nulo Se o osVersion for vazio, retorna Vazio |
| platform | SE Endpoint = %/client/redirect-to-server, %/client/redirect-target-with-errors, %/client/redirect-target-without-errors, %/server/authenticated ou %/server/redirect-to-client ENTÃO Se o platform for nulo, retorna Nulo Se o platform for vazio, retorna Vazio |
| serverOrgId | SE Endpoint = %/server/redirect-target, %/server/authenticated ou %/server/redirect-to-client ENTÃO Se o serverOrgId for nulo, retorna Nulo Se o serverOrgId for vazio, retorna Vazio |
| timestamp | SE Endpoint = %/client/redirect-to-server, %/client/redirect-target-with-errors, %/client/redirect-target-without-errors, %/server/redirect-target, %/server/authenticated ou %/server/redirect-to-client ENTÃO Se o timestamp for nulo, retorna Nulo Se o timestamp for vazio, retorna Vazio |
| type | SE Endpoint = %/server/redirect-target ou %/server/redirect-to-client ENTÃO Se o osVersion for nulo, retorna Nulo Se o osVersion for vazio, retorna Vazio |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Hybridflow > Diagramas de Hybridflow > Diagrama de envio de reportes

---
id: 1091534849
title: Diagrama de envio de reportes
version: 3
modified: 2025-09-03T19:41:55.261Z
url: /spaces/OF/pages/1091534849/Diagrama+de+envio+de+reportes
---

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Hybridflow > Diagramas de Hybridflow > Diagrama de sequência

---
id: 1091567617
title: Diagrama de sequência
version: 1
modified: 2025-08-26T18:55:44.647Z
url: /spaces/OF/pages/1091567617/Diagrama+de+sequ+ncia
---

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Pagamentos > Campos Obrigatórios e Opcionais - SV

---
id: 1211334670
title: Campos Obrigatórios e Opcionais - SV
version: 5
modified: 2026-01-23T20:56:22.816Z
url: /spaces/OF/pages/1211334670/Campos+Obrigat+rios+e+Opcionais+-+SV
---

v 1.00Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Private API

| Campo | Definição | Obrigatório | Tipo | Regra de preenchimento | Roles | Métodos | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| additionalInfo | Informações adicionais sobre o reporte deste endpoint/método. Possui característica variável. As regras de preenchimento estão na documentação funcional em Regras de Obrigatoriedade (additionalInfo) - SV . | Client: Sim Server: Não | object | Caso não exista o campo enviar como um objeto vazio: {} | CLIENT SERVER | POST GET | | | | | | |
| clientOrgId | Identificador da organização de onde a chamada foi disparada | Sim | string <uuid> | | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 56411f7e-d58b-44a8-8a2b-ff326d3f2955 |
| clientSSId | Identificador do software statement de onde a chamada foi disparada. A PCM garante que foi esta orgId que obteve o token de acesso utilizado neste reporte. | Sim | string <uuid> | | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 84570da9-567b-4201-9b77-c715bc5bffde |
| correlationId | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. | Não | string | | CLIENT | POST | | 100 | | | ^[- /:_.',0-9a-zA-Z]{0,100}$ | uGQHwNupARo7I9E2PLJZph18a0M9y7DcUe7ITt3DqUOJd9NVjnskxf2 |
| createdAt | Carimbo do tempo do momento da criação do registro | Não | string <date-time> | | CLIENT SERVER | GET | | 28 | | | | |
| endpoint | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar presente na lista de endpoints aceitos pela PCM para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. | Sim | string <uri> | Identificação do Endpoint: Deve ser preenchido com o identificador padronizado do endpoint, conforme uma lista (ENUM) predefinida. Não usar o caminho real: É fundamental NÃO utilizar o caminho completo da requisição original, que inclui dados variáveis (ex: IDs). Exemplo: Se a requisição foi para /open-banking/credit-cards-accounts/v1/accounts/123456789/transactions, o valor a ser enviado no endpoint deve ser /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions. O dado real 123456789 não deve ser enviado no campo endpoint. | CLIENT SERVER | POST GET | Endpoints aceitos pela PCM | | | | | /open-banking/consents/v2/consents |
| endpointUriPrefix | Endereço do servidor de destino da chamada, incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: https://{host}/{prefixo}, sendo: host: endereço FQDN do servidor de destino prefixo: toda a parte do path que vem antes da string /open-banking | Sim | string | Exemplos: Para uma requisição em `https://openbanking.instituicao-1.com.br/opbk/open-banking/products-services/v1/business-accounts` , o dado a ser enviado é `https://openbanking.instituicao-1.com.br/opbk` . Para uma requisição em `https://openbanking.instituicao-2.com.br/open-banking/products-services/v1/business-accounts` , o dado a ser enviado é `https://openbanking.instituicao-1.com.br/` . Nos reportes relativos aos endpoints /token e /register este campo deverá conter a URL inteira do request. Exemplos: `https://oauth2.cartaodummy.opf.instituicao/as/token.oauth2` `https://instituicao.com.br/orgs/instituicao/reg` | CLIENT | POST GET | | 200 | | | ^[- /:_.',0-9a-zA-Z]{0,200}$ | https://openbanking.instituicao-1.com.br/opbk |
| fapiInteractionId | UUID RFC4122 que identifica uma transação específica entre dois participantes no ecossistema Open Finance. Este identificador é derivado do header HTTP x-fapi-interaction-id, conforme especificação RFC4122 para geração de identificadores únicos universais. Serve como chave de correlação fundamental para rastreabilidade, auditoria e conciliação de transações entre instituições participantes. Mais informações em Cabeçalhos HTTP na documentação de produtos do Open Finance Brasil | Sim | string <uuid> | Para CLIENT: OBRIGATÓRIO em todos os cenários onde o x-fapi-interaction-id foi gerado, incluindo respostas com status 4xx (incluindo 408 - timeout), respostas com status 5xx recebidas e transações completadas com sucesso. Para SERVER: OBRIGATÓRIO quando o x-fapi-interaction-id foi recebido na requisição ou quando o Server gerou o x-fapi-interaction-id conforme especificação da API de Produto. Falhas de aplicação, validação, autorização, timeout, indisponibilidade de dependências ou erros internos (5xx) NÃO caracterizam, por si só, falha crítica para fins de ausência do x-fapi-interaction-id, desde que a requisição tenha sido recebida pelo Server. Nota: A ausência do fapiInteractionId compromete significativamente a capacidade de correlação e auditoria das transações no ecossistema Open Finance | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| httpMethod | Método HTTP da solicitação. | Sim | enum<string> | | CLIENT SERVER | POST GET | DELETE, GET, PATCH, POST, PUT | | | | | GET |
| pairedReportId | Esse atributo indica o reportId do registro que forma uma correlação com o presente registro. Se essa informação existir, o status do registro atual deverá ser PAIRED. | Não | string <uuid> | | CLIENT SERVER | GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 9a97c2df-b261-4fc2-aa66-d1b5168397da |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. | Sim | integer <int16> | | CLIENT SERVER | POST GET | | | | | | 120 |
| reportId | Identificador único do registro criado na Plataforma de Coleta de Métricas. | Não | string <uuid> | | CLIENT SERVER | GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | |
| role | Indica se o reporte que está sendo enviado apresenta a visão do server ou do client. | Sim | enum<string> | | CLIENT SERVER | POST GET | CLIENT, SERVER | | | | | CLIENT |
| serverOrgId | Identificador da organização para onde a chamada foi feita | Sim | string <uuid> | | CLIENT SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| status | Informa o status do registro de reporte. | Não | enum<string> | DISCARDED : O status DISCARDED indica que o reporte enviado pelo participante foi rejeitado pela PCM. O motivo do descarte será enviado com a resposta, podendo ser por conta de um reporte inválido ou por um erro no processamento. Não é possível modificar um reporte DISCARDED, portanto o reportador deverá corrigir o registro que apresentou erro e reenviar via POST. SINGLE : O status SINGLE indica que o reporte em questão não tem uma contraparte. Ele é utilizado em casos onde a conciliação entre dois reportes não é possível. ACCEPTED : O status ACCEPTED indica que a validação de formato do reporte não tem erros e este será enviado para processamento. UNPAIRED : O status UNPAIRED significa que o reporte atual não possui uma correspondência em outro reporte através do atributo fapiInteractionId. Indica um reporte divergente. PAIRED_INCONSISTENT : O status PAIRED_INCONSISTENT significa que o reporte corrente possui uma contraparte com o mesmo fapiInteractionId, mas os demais dados estão inconsistentes. Indica um reporte divergente. PAIRED : Indica que o reporte tem uma contraparte com o mesmo fapiInteractionId e os demais dados estão conciliados. Representa o estado final desejado em um fluxo correto. | CLIENT SERVER | GET | ACCEPTED, DISCARDED, PAIRED, PAIRED_INCONSISTENT, SINGLE, UNPAIRED | | | | | PAIRED |
| statusCode | Status de retorno HTTP da solicitação. | Sim | integer <int32> | No caso de ocorrer um timeout client side, preencher com um código 403. | CLIENT SERVER | POST GET | | | 200 | 599 | | 200 |
| timestamp | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. | Sim | string <date-time> | | CLIENT SERVER | POST GET | | 28 | | | YYYY-MM-DDTHH:mm:ss.sssZ | 2021-11-11T18:08:08.278Z |
| updatedAt | Carimbo do tempo do momento da última atualização do registro | Não | string <date-time> | | CLIENT SERVER | GET | | 28 | | | | |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Pagamentos > Jornada Otimizada - SV

---
id: 1275625473
title: Jornada Otimizada - SV
version: 1
modified: 2025-11-18T12:54:10.836Z
url: /spaces/OF/pages/1275625473/Jornada+Otimizada+-+SV
---

v 1.00
## Objetivo
Com o intuito de monitorar a Jornada Otimizada, faz-se necessária a inclusão de dois novos additionalInfo nos reportes da PCM, de forma a diferenciar consentimentos primários e secundários, e relacionar consentimentos vinculados.Para consultar os detalhes técnicos da implementação destes additilnalInfo, por favor consultar a página Documentação da API - PCM 
## journeyIsLinked

- Descrição: indica que o consentimento é vinculado a outro em uma Jornada Otimizada
- Jornada Sem Redirecionamento (JSR) ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.isLinked”, retornado após a chamada inicial na API “POST /enrollments” em caso de Jornada Otimizada. Exemplo: true  Roles: CLIENT  Métodos: POST e GET Http Code: Todos endpoints:  /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId}

- PIX Automático ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.i sLinked”, retornado após a chamada inicial na API “POST /consent” em caso de Jornada Otimizada. Exemplo: true  Roles: CLIENT  Métodos: POST e GET Http Code: Todos menos 4xx e 5xx no POST endpoints:  /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}

## journeyLinkId

- Descrição: Identifica o consentimento de dados vinculado a uma Jornada Otimizada.
- Jornada Sem Redirecionamento (JSR) ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.linkId”, retornado após a chamada inicial na API “POST /enrollments” em caso de Jornada Otimizada. Roles: CLIENT  Métodos: POST e GET Http Code: Todos endpoints:  /open-banking/enrollments/v1/enrollments /open-banking/enrollments/v1/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId}

- PIX Automático ⁠ Regra de preenchimento: Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.li nkId”, retornado após a chamada inicial na API “POST /consent” em caso de Jornada Otimizada. Roles: CLIENT  Métodos: POST e GET Http Code: Todos menos 4xx e 5xx no POST endpoints:  /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}
**Exceções de reporte:** 
- Não deve ser reportado o campo journeyIsLinked ou journeyLinkId quando: O consentimento for criado fora do contexto de Jornada Otimizada, ou seja, quando não houver indicação de journey.isLinked=true no payload da criação do consentimento O consentimento for do tipo convencional (ex.: consents isolados, enrollments isolados, recurring-consents isolados), sem vínculo com outro consentimento
- Nestes casos, a transmissora/detentora deve omitir os campos journeyIsLinked e journeyLinkId no reporte à PCM

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Pagamentos > Regras de Descarte - SV

---
id: 1212514317
title: Regras de Descarte - SV
version: 2
modified: 2025-12-10T16:47:12.566Z
url: /spaces/OF/pages/1212514317/Regras+de+Descarte+-+SV
---

v 1.01**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Private API - Pagamentos

| Campo | Regra |
| --- | --- |
| additionalInfo | Informação não enviada Invalid type: additionalInfo: Required: additonalInfo não enviado; na ausência de additonalInfo, deve ser informada uma matriz vazia Conteúdo inválido additionalInfo should not be empty: additonalInfo vazio; na ausência de additonalInfo, deve ser informada uma matriz vazia Invalid type: additionalInfo: Expected object, received ‘xxxx’: tipo do campo additionalInfo inválido; esperado objeto |
| amountType (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.amountType: Expected string, received ‘xxxx’: tipo do campo amountType inválido; esperado objeto |
| authorisationFlow (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.authorisationFlow: Expected string, received ‘xxxx’: tipo do campo authorisationFlow inválido; esperado objeto |
| cancellationReason (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.cancellationReason: Expected string, received ‘xxxx’: tipo do campo cancellationReason inválido; esperado string |
| cancelledFrom (additionalInfo) | Conteúdo inválido Invalid value: additionalInfo.cancelledFrom: Invalid enum value. Expected 'REJECTED' | 'REVOKED', received 'XXX': conteúdo do campo cancelledFrom inválido, recebido conteúdo não determinado no enum do campo |
| clientIp (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.clientIp: Expected string, received ‘xxxx’: tipo do campo clientIp inválido; esperado string |
| clientOrgId | Informação não enviada Invalid type: clientOrgId: Required: campo ClientOrgId ausente Missing property: clientOrgId or serverOrgId: campo clientOrgid ausente Conteúdo inválido clientOrgId 'xxxx' is invalid to role 'CLIENT': clientOrgId informado é inválido para o role CLIENT Invalid field type, clientOrgId must be a valid UUID: clientOrgId não está no formato UUID Invalid type: clientOrgId: Expected string, received null: conteúdo do campo clientOrgId inválido; esperado string, recebido nulo Requester id mismatch with clientOrgId: clientOrgId informado no role CLIENT não é a mesma organização reportadora (PAR-100) Validation error: clientOrgId: conteúdo do campo clientOrgId inválido |
| clientSSId | Informação não enviada Invalid type: clientSSId: Required: campo clientSSId ausente Missing property: clientSSId: campo clientSSId ausente Conteúdo inválido Invalid field type, clientSSId should not be empty: campo clientSSId não pode estar vazio Invalid format: clientSSId: Invalid uuid: formato do clientSSId inválido, deve estar no formato UUID Invalid format: Unrecognized key(s) in object: 'clientSSId': conteúdo do campo clientSSId inválido Invalid type: clientSSId: Expected string, received null: conteúdo do campo clientSSId inválido; esperado string, recebido nulo Invalid value: Client SSID not found in combined org IDs: campo clientSSId inválido, não encontrado na combinação de org IDs |
| correlationId | Conteúdo inválido Invalid format: correlationId: Invalid correlationId format: formato do correlationId inválido (não pode ter mais de 100 caracteres) |
| dropReason (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.dropReason: Expected string, received ‘xxxx’: tipo do campo dropReason inválido; esperado string Invalid value: additionalInfo.dropReason: Invalid enum value. Expected 'NONE' | 'NO_CREDENTIAL', received 'XXX': conteúdo do campo dropReason inválido, recebido conteúdo não determinado no enum do campo |
| endpoint | Informação não enviada Invalid type: endpoint: Required; validation error: undefined: campo endpoint ausente Conteúdo inválido Missing property, endpoint can't be empty: campo endpoint não pode estar vazio Unlisted endpoint: endpoint enviado não é válido (consultar a tabela de endpoints aceitos pela PCM) |
| endpointUriPrefix | Informação não enviada Invalid type: endpointUriPrefix: Required: campo endpointUriPrefix ausente Conteúdo inválido Invalid format: : Unrecognized key(s) in object: 'endpointUriPrefix': conteúdo do campo endpointUriPrefix inválido |
| errorCodes (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.errorCodes: Expected string, received ‘xxxx’: tipo do campo errorCodes inválido; esperado string |
| fapiInteractionId | Informação não enviada Invalid field value fapiInteractionId can't be empty for status 408 or 500: fapiInteractionId deve ser informado para status 408 ou 500 Missing property: fapiInteractionId is required: campo fapiInteractionId ausente Missing property, fapiInteractionId is not provided: campo fapiInteractionId ausente Conteúdo inválido Invalid format: fapiInteractionId must match format "uuid”: campo fapiInteractionId com formato inválido (UUID) ou com menos de 36 caracteres Invalid format: : Unrecognized key(s) in object: 'fapiinteractionid': conteúdo do campo fapiInteractionId inválido Invalid type: fapiInteractionId mismatch. Ensure the ID is not "00000000-0000-0000-0000-000000000000.": formato do campo fapiInteractionId inválido Invalid type: fapiInteractionId: Expected string, received ‘xxxx’: tipo do campo fapiInteractionId inválido; esperado string |
| grantType (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.grantType: Expected string, received ‘xxxx’: tipo do campo grantType inválido; esperado string |
| hasMinimumAmount (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.hasMinimumAmount: Expected string, received ‘xxxx’: tipo do campo hasMinimumAmount inválido; esperado string |
| httpMethod | Informação não enviada Invalid type: httpMethod: Required: campo httpMethod ausente Conteúdo inválido Invalid format: : Unrecognized key(s) in object: 'httpmethod': conteúdo do campo httpMethod inválido Invalid value: httpMethod: Invalid enum value. Expected ‘GET' | 'POST' | 'PUT' | 'PATCH' | 'DELETE', received 'HEAD’: conteúdo do campo httpMethod inválido, recebido conteúdo não determinado no enum do campo |
| interval (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.interval: Expected string, received ‘xxxx’: tipo do campo interval inválido; esperado objeto |
| isFirstPayment (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.isFirstPayment: Expected string, received ‘xxxx’: tipo do campo isFirstPayment inválido; esperado string |
| isRetryAccepted (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.isRetryAccepted: Expected string, received ‘xxxx’: tipo do campo isRetryAccepted inválido; esperado string isRetryAccepted must be a string: conteúdo do campo isRetryAccepted inválido, deve ser string |
| originalRecurringPaymentId (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.originalRecurringPaymentId: Expected string, received ‘xxxx’: tipo do campo originalRecurringPaymentId inválido; esperado objeto |
| paymentReference (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.paymentReference: Expected string, received ‘xxxx’: tipo do campo paymentReference inválido; esperado objeto |
| paymentType (additionalInfo) | Conteúdo inválido Invalid value: additionalInfo.paymentType: Invalid enum value. Expected 'IMMEDIATE' | 'RECURRENT' | 'SCHEDULED' | 'SWEEPING', received 'xxxx': conteúdo do campo paymentType inválido, recebido conteúdo não determinado no enum do campo |
| personType (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.personType: Expected string, received null: conteúdo do campo personType inválido; esperado string Invalid value: additionalInfo.personType: Invalid enum value. Expected ‘PF' | 'PJ', received 'xxxx’: conteúdo do campo personType inválido, recebido conteúdo não determinado no enum do campo |
| processTimespan | Informação não enviada Invalid type: processTimespan: Required: campo processTimespan ausente Conteúdo inválido Invalid type: processTimespan: Expected number, received ‘xxxx’: conteúdo do campo processTimespan inválido; esperado número Invalid value: processTimespan must be greater than zero: campo processTimespan deve ter valor maior do que zero |
| recurringPaymentId (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.recurringPaymentId: Expected string, received ‘xxxx’: tipo do campo recurringPaymentId inválido; esperado objeto |
| rejectionReasonCode (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.rejectionReasonCode: Expected string, received ‘xxxx’: tipo do campo rejectionReasonCode inválido; esperado string |
| rejectionReasonDetail (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.rejectionReasonDetail: Expected string, received ‘xxxx’: tipo do campo rejectionReasonDetail inválido; esperado string |
| revocationReasonCode (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.revocationReasonCode: Expected string, received ‘xxxx’: tipo do campo revocationReasonCode inválido; esperado string |
| role | Informação não enviada Invalid type: role: Required campo role ausente Conteúdo inválido Invalid value: role: Invalid enum value. Expected 'SERVER' | 'CLIENT', received 'xxxx': conteúdo do campo role inválido, recebido conteúdo não determinado no enum do campo |
| serverOrgId | Informação não enviada Invalid type: serverOrgId: Required; missing property: serverOrgId: campo serverOrgId ausente Missing property: clientOrgId or serverOrgId : serverOrgId ausente Missing property: serverOrgId: campo serverOrgId ausente Conteúdo inválido Invalid field type, serverOrgId must be a valid UUID: serverOrgId não está no formato UUID Requester id mismatch with serverOrgId: serverOrgId informado no role SERVER não é a mesma organização reportadora (PAR-100) Requester mismatch: serverOrgId: serverOrgId informado no role SERVER não é a mesma organização reportadora (PAR-100) serverOrgId 'xxxx' is invalid to role 'SERVER': serverIrgId informado é inválido para o role SERVER |
| status (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.status: Expected string, received ‘xxxx’: tipo do campo status inválido; esperado string |
| statusCode | Informação não enviada Invalid type: statusCode: Required: campo statusCode ausente Conteúdo inválido Invalid type: statusCode: Expected number, received ‘xxxx’: conteúdo do campo statusCode inválido; esperado número Invalid value: statusCode must be between 200 and 599: campo statusCode com valor menor do que 200 ou maior do que 599 Missing property, statusCode can't be empty: campo statusCode não pode estar vazio |
| timestamp | Conteúdo inválido Error not mapped or not expected by validations: Report is too old: campo timestamp com data passada de 7 dias Invalid format: timestamp: Invalid date: conteúdo do campo timestamp inválidlo Missing property, timestamp can't be empty: campo timestamp não pode estar vazio Timestamp is older than 7 days: campo timestamp com data passada de 7 dias Timestamp of report is too old: campo timestamp com data passada de 7 dias Validation error: Report is too old: campo timestamp com data passada de 7 dias |
| webhookEnable (additionalInfo) | Conteúdo inválido Invalid type: additionalInfo.webhookEnable: Expected string, received ‘xxxx’: tipo do campo webhookEnable inválido; esperado string |

# API Estados de Pagamento

| Campo | Regra |
| --- | --- |
| clientOrgId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| consentId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no padrão especificado na documentação funcional para ser considerado válido |
| eventDateTime | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no padrão especificado na documentação funcional para ser considerado válido |
| paymentId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no padrão especificado na documentação funcional para ser considerado válido |
| paymentStatus | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no domínio especificado na documentação funcional para ser considerado válido |
| paymentType | Deve ser enviado no payload (não deve estar ausente) Deve estar no domínio especificado na documentação funcional para ser considerado válido |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Pagamentos > Regras de Obrigatoriedade (additionalInfo) - SV

---
id: 1212121089
title: Regras de Obrigatoriedade (additionalInfo) - SV
version: 13
modified: 2026-01-29T19:50:43.241Z
url: /spaces/OF/pages/1212121089/Regras+de+Obrigatoriedade+additionalInfo+-+SV
---

v 1.06**Guia de leitura**
1. Se o campo não está listado, é porque não existe a obrigatoriedade de enviá-lo.
2. Nos endpoints, a referência “v x ” indica que se aplicam às versões listadas na coluna “Versões”. Por exemplo, Endpoint “open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId}” e Versões “v1 v2” significa que o endpoint é válido para as versões 1 e 2.
Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Pagamentos

### Iniciação de Pagamentos

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Domínio | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| authorisationFlow | Identifica o fluxo de autorização em que um pagamento ou operação foi solicitado | O campo deve ser preenchido com a string obtida em ".data.authorisationFlow". Se a informação for uma lista, utilize apenas o primeiro item. Caso a string de ".data.authorisationFlow" seja nula, preencha obrigatoriamente com HYBRID_FLOW. É fundamental que sempre seja reportado um dos valores do enum (como HYBRID_FLOW, CIBA ou FIDO), e nunca um valor nulo, pois para fins de telemetria é necessário identificar explicitamente qual fluxo de autorização foi utilizado, independentemente da permissão de valor nulo nas especificações das APIs do Open Finance. | CLIENT | Todos | POST GET PATCH | CIBA_FLOW, FIDO_FLOW, HYBRID_FLOW | /open-banking/payments/vx/pix/payments /open-banking/payments/v x /pix/payments/{paymentId}​ | v4 | | | |
| authorisationFlowIntent | Permite a desambiguação e clara distinção entre as jornadas de pagamento que demandam ou não redirecionamento do usuário, já na etapa de provisionamento do consentimento | O campo deve ser preenchido obrigatoriamente com um dos valores do enum: HYBRID_FLOW, CIBA_FLOW ou FIDO_FLOW. A instituição iniciadora deve comunicar a intenção de fluxo de autorização que será utilizado na jornada de pagamento. Esta informação é essencial para a desambiguação das jornadas de pagamento na etapa de consentimento.   Nota técnica: Esta informação não existe tecnicamente nesta etapa da API de Consents; cabe à instituição iniciadora, por seu conhecimento prévio, reportar sua intenção de fluxo que será efetivamente utilizado na transação. | CLIENT | Todos | POST GET PATCH | CIBA_FLOW, FIDO_FLOW, HYBRID_FLOW | /open-banking/payments/v x /consents | v4 | | | |
| companyProfileInfo | Objeto JSON que representa o perfil da Pessoa Jurídica (PJ) do cliente, contendo informações como a natureza jurídica e o porte da empresa, conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O objeto deve conter um objeto de perfil da empresa. As informações de natureza jurídica e porte devem ser obtidas prioritariamente da API oficial Consulta CNPJ (RFB/SERPRO) ou dos Dados Abertos do CNPJ (RFB) , conforme o Dicionário de Dados do CNPJ da Receita Federal. Este objeto deve ser enviado como parte do additionalInfo ao consumir as APIs de criação de consentimento para dados e serviços. Consulta CNPJ — Catálogo de APIs governamentais (API/Swagger) Portal de Dados Abertos (arquivo de dados) | CLIENT | Todos | POST | | /open-banking/payments/v x /consents | v4 | | Objeto JSON | { "naturezaJuridica": "2135", "porteEmpresa": "01" } |
| naturezaJuridica | Código que identifica a constituição jurídico-institucional da entidade, conforme a Tabela de Natureza Jurídica do IBGE, categorizando-a em: Administração pública; Entidades empresariais; Entidades sem fins lucrativos; Pessoas físicas e organizações internacionais; e Outras instituições extraterritoriais. | Obrigatório. O cliente (receptor/iniciador) deve obter essa informação a partir de fontes oficiais (ex., Governo Federal/Dados Abertos/Base CNPJs ou API do SERPRO), com base no CNPJ do usuário, e reportá-la como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | 4 | ^\d{4}$ | 2135 |
| porteEmpresa | Código numérico que identifica o porte da empresa do cliente Pessoa Jurídica (PJ), conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O receptor/iniciador, que detém o CNPJ do usuário, é responsável por obter o código do porte da empresa. Esta informação deve ser consultada e validada a partir de fontes oficiais, como a base de Dados Abertos do CNPJ ou a API do SERPRO, ambas mantidas pelo Governo Federal, e conforme o Dicionário de Dados do CNPJ da Receita Federal. O valor deve ser enviado como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | 2 | ^\d{2}$ | 01 |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos menos 4xx e 5xx para o método POST | GET PATCH POST | | /open-banking/payments/v x /consents /open-banking/payments/v x /consents/{consentId} | v4 | 256 | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos | GET PATCH POST | | /open-banking/payments/v x /pix/payments /open-banking/payments/v x /pix/payments/{paymentId}​ /open-banking/payments/v x /pix/payments/consents/{consentId} | | 256 | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| dropReason | Razão pela qual um usuário não conseguiu prosseguir em uma jornada, especificamente no contexto de consentimentos | O campo dropReason deve ser adicionado nas informações do campo additionalInfo que deverá ser enviado no reporte do provedor do serviço consumido (papel SERVER) O reporte deverá ser feito por todos os transmissores de dados e detentoras de conta. Para os casos em que ocorram falhas técnicas que impossibilitem a verificação do CPF/CNPJ (incluindo, mas não se limitando, a erros HTTP 4xx, 500 ou timeout na resposta), o reporte deve ser realizado com o valor NO_CREDENTIAL, Em jornadas de múltipla alçada de pessoas jurídicas, quando a autenticação é bem-sucedida mas os poderes constituídos são insuficientes para finalização do Hybrid Flow, deve-se usar NO_AUTHORITY. NONE : quando o CPF (loggedUser) / CNPJ (businessEntity) possui credencial autenticadora e poderes suficientes para prosseguir o fluxo monitorado - exemplo: PF, cliente, que possui credencial ativa, mas não se autenticou; cliente que se autenticou utilizando a credencial correta. NO_CREDENTIAL : quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado ou quando o HTTP response code for diferente de 201. NO_AUTHORITY : quando o CPF (loggedUser) / CNPJ (businessEntity) consegue se autenticar, mas não dispõe de poderes ou alçadas para prosseguir no fluxo de compartilhamento de dados e serviços. NO_AUTHORITY_PERSON_MISMATCH : quando o CPF (loggedUser) não possui relação com a credencial utilizada na etapa de autenticação do Hybrid Flow - exemplo: consentimento criado para um CPF e autenticado por outro; criado para um CNPJ e autenticado por CPF sem relação com o CNPJ. | SERVER | Todos | POST | NO_AUTHORITY, NO_AUTHORITY_PERSON_MISMATCH, NO_CREDENTIAL, NONE | /open-banking/payments/v x /consents | v4 | | | |
| errorCodes | Registrar os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 422 | GET POST PATCH | 422ReponseError Create Consent DATA_PAGAMENTO_INVALIDA, DETALHE_PAGAMENTO_INVALIDO, ERRO_IDEMPOTENCIA, FORMA_PAGAMENTO_INVALIDA, NAO_INFORMADO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO CreateError PIX Payments COBRANCA_INVALIDA, CONSENTIMENTO_INVALIDO, CONSENTIMENTO_PENDENTE_AUTORIZACAO, DETALHE_PAGAMENTO_INVALIDO, ERRO_IDEMPOTENCIA, NAO_INFORMADO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PAGAMENTO_NAO_PERMITE_CANCELAMENTO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, SALDO_INSUFICIENTE, VALOR_ACIMA_LIMITE, VALOR_INVALIDO | /open-banking/payments/v x /consents /open-banking/payments/v x /consents/{consentId} /open-banking/payments/v x /pix/payments /open-banking/payments/v x /pix/payments/{paymentId}​ /open-banking/payments/v x /pix/payments/consents/{consentId} | v4 | | | |
| errorCodes | Registrar os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 4xx ou 5xx exceto 422 | GET POST PATCH | | /open-banking/payments/v x /consents /open-banking/payments/v x /consents/{consentId} /open-banking/payments/v x /pix/payments /open-banking/payments/v x /pix/payments/{paymentId}​ /open-banking/payments/v x /pix/payments/consents/{consentId} | v4 | | | |
| localInstrument | Especifica a forma de iniciação do pagamento​ | Deve ser preenchido com a mesma string informada no payload ".data.localInstrument" Se /data/payment/schedule enviado com valor diferente de single durante a criação do consentimento, apenas os métodos MANU, DICT ou QRES são permitidos. | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET POST PATCH | DICT, INIC, MANU, QRDN, QRES, AUTO | /open-banking/payments/v x /consents /open-banking/payments/v x /pix/payments/{paymentId} | v4 | | | |
| paymentDate | Data em que o pagamento será realizado | Deve ser preenchido com o conteúdo de data.payment.date Mutualmente excludente com o campo paymentSchedule | CLIENT | 201 | POST | | /open-banking/payments/v x /consents | v4 | | | |
| paymentSchedule | Estrutura responsável pela parametrização dos pagamentos que acontecerão sob aquele consentimento | Deve ser preenchido com o conteúdo de data.payment.schedule Mutualmente excludente com o campo paymentDate | CLIENT | 201 | POST | | /open-banking/payments/v x /consents | v4 | | | |
| paymentList | Lista de dados de pagamentos com agendamentos recorrentes Os itens indentados abaixo pertencem ao objeto paymentList e seguem as mesmas regras de obrigatoriedade | | CLIENT | 201 | POST | | /open-banking/payments/v x /pix/payments | v4 | | | |
| paymentId | Código ou identificador único informado pela instituição detentora da conta para representar a iniciação de pagamento​ | | | | | | | | | | |
| consentId | Identificador único do consentimento criado para a iniciação de pagamento solicitada​ | | | | | | | | | | |
| statusUpdateDateTime | Data e hora da última atualização da iniciação de pagamento | | | | | | | | | | |
| status | Estado atual do pagamento | | | | | | | | | | |
| rejectionReasonCode | Código identificador do motivo de rejeição. Deve ser enviado vazio se não houver conteúdos, seguindo a mesma regra da API de negócio relacionada | | | | | | | | | | |
| rejectionReasonDetail | Detalhe sobre o código identificador do motivo de rejeição. Deve ser enviado vazio se não houver conteúdos, seguindo a mesma regra da API de negócio relacionada | | | | | | | | | | |
| paymentType | Identifica o modo de pagamento acionado no consentimento | Deve observar se é imediato, agendamento único ou agendamento recorrente. Se for imediato o campo payment.date vai estar preenchido. Se for agendamento único, o campo payment.schedule.single vai estar preenchido. Se for agendamento recorrente o campo payment.schedule vai estar preenchido com valor diferente de single. | CLIENT | Todos | POST | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | /open-banking/payments/v x /consents /open-banking/payments/v x /pix/payments | v4 | | | |
| paymentType | Identifica o modo de pagamento acionado no consentimento | Deve observar se é imediato, agendamento único ou agendamento recorrente. Se for imediato o campo payment.date vai estar preenchido. Se for agendamento único, o campo payment.schedule.single vai estar preenchido. Se for agendamento recorrente o campo payment.schedule vai estar preenchido com valor diferente de single. | CLIENT | Todos | PATCH | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | /open-banking/payments/v x /pix/payments/{paymentId}​ | v4 | | | |
| personType | Identifica a natureza do solicitante em uma transação ou consentimento. | Se .data.businessEntity estiver preenchido no payload, se estiver então preencher com "PJ", se não estiver então preencher com "PF" | CLIENT | Todos | POST | PF, PJ | /open-banking/payments/v x /consents | v4 | | | |
| rejectionReasonCode | Código da razão pela qual um consentimento ou pagamento foi rejeitado | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.code" ou ".data.rejection.reason.code" ou ".data.cancellation.rejectionReason"​ | CLIENT | Todos menos 4xx e 5xx | GET | RejectionReasonType COBRANCA_INVALIDA, CONSENTIMENTO_INVALIDO, CONSENTIMENTO_REVOGADO, CONTAS_ORIGEM_DESTINO_IGUAIS, DETALHE_PAGAMENTO_INVALIDO, DETALHE_TENTATIVA_INVALIDO, FALHA_AGENDAMENTO_PAGAMENTOS, FALHA_INFRAESTRUTURA_DETENTORA, FALHA_INFRAESTRUTURA_DICT, FALHA_INFRAESTRUTURA_ICP, FALHA_INFRAESTRUTURA_PSP_RECEBEDOR, FALHA_INFRAESTRUTURA_SPI, FORA_PRAZO_PERMITIDO, LIMITE_PERIODO_QUANTIDADE_EXCEDIDO, LIMITE_PERIODO_VALOR_EXCEDIDO, LIMITE_TENTATIVAS_EXCEDIDO, LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO, LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO, NAO_INFORMADO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, SALDO_INSUFICIENTE, TITULARIDADE_INCONSISTENTE, VALOR_ACIMA_LIMITE, VALOR_INVALIDO ConsentRejectionReason AUTENTICACAO_DIVERGENTE, CONTA_NAO_PERMITE_PAGAMENTO, CONTAS_ORIGEM_DESTINO_IGUAIS, FALHA_INFRAESTRUTURA, NAO_INFORMADO, QRCODE_INVALIDO, REJEITADO_USUARIO, SALDO_INSUFICIENTE, TEMPO_EXPIRADO_AUTORIZACAO, TEMPO_EXPIRADO_CONSUMO, VALOR_ACIMA_LIMITE, VALOR_INVALIDO | /open-banking/payments/v x /consents/{consentId} /open-banking/payments/v x /pix/payments/{paymentId}​ | v4 | | | |
| rejectionReasonDetail | Detalhe mais específico sobre a rejeição de um consentimento ou pagamento | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.detail". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista additionalInfo_status deve ser 'REJECTED' ou 'RJCT' | CLIENT | Todos menos 4xx e 5xx | GET | | /open-banking/payments/v x /consents/{consentId} /open-banking/payments/v x /pix/payments/{paymentId}​ | v4 | | | |
| status | Identifica o status atual do recurso (como um consentimento ou um pagamento) que está sendo reportado. | Deve ser preenchido com a mesma string obtida no ".data.status". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | 2xx | GET POST PATCH | Para consentimentos: AUTHORISED, AWAITING_AUTHORISATION, CONSUMED, PARTIALLY_ACCEPTED, REJECTED, REVOKED Para pagamentos: ACCP, ACPD, ACSC, CANC, PDNG, RCVD, RJCT, SCHD | /open-banking/payments/vx/consents /open-banking/payments/vx/consents/{consentId} /open-banking/payments/vx/pix/payments /open-banking/payments/vx/pix/payments/{paymentId}​ /open-banking/payments/v x /pix/payments/consents/{consentId} | v4 | | | |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | | /open-banking/payments/vx/consents /open-banking/payments/vx/consents/{consentId} /open-banking/payments/vx/pix/payments /open-banking/payments/vx/pix/payments/{paymentId}​ /open-banking/payments/v x /pix/payments/consents/{consentId} | v4 | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |
| webhookInteractionId | Indica o identificador x-webhook-interaction-id quando uma requisição GET é realizada após o estímulo de um webhook. | Caso o GET esteja sendo feito após o estímulo do webhook, o x-webhook-interaction-id deverá ser indicado | CLIENT | Todos menos 4xx e 5xx | GET | | /open-banking/payments/v x /consents/{consentId}​ | v4 | | | |

### Iniciação de Pagamentos Sem Redirecionamento

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Domínio | Endpoints | Versões | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| authenticatorAttachment​ | Descreve como o autenticador (por exemplo, um dispositivo FIDO) está anexado ao cliente que realiza a autenticação (ex: platform para autenticadores integrados como Face ID ou cross-platform para chaves de segurança USB). | Deve ser preenchido com a mesma string definida em ".data.authenticatorAttachment". Não havendo string, deve ser explicitamente enviada esse additionalInfo como sendo uma string vazia.​ | CLIENT | Todos | Todos | | /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration​ | v1 v2 | | |
| cancelledFrom | Informa o meio pelo qual foi realizado o cancelamento | Preencher com o valor do campo ".cancellation.cancelledFrom" Status do pagamento deve ser "CANC" | CLIENT | 2xx | GET | INICIADORA, DETENTORA | /open-banking/enrollments/v x /enrollments/{enrollmentId}​ | v2 | | |
| companyProfileInfo | Objeto JSON que representa o perfil da Pessoa Jurídica (PJ) do cliente, contendo informações como a natureza jurídica e o porte da empresa, conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O objeto deve conter um objeto de perfil da empresa. As informações de natureza jurídica e porte devem ser obtidas prioritariamente da API oficial Consulta CNPJ (RFB/SERPRO) ou dos Dados Abertos do CNPJ (RFB) , conforme o Dicionário de Dados do CNPJ da Receita Federal. Este objeto deve ser enviado como parte do additionalInfo ao consumir as APIs de criação de consentimento para dados e serviços. Consulta CNPJ — Catálogo de APIs governamentais (API/Swagger) Portal de Dados Abertos (arquivo de dados) | CLIENT | Todos | POST | | /open-banking/enrollments/v x /enrollments | v2 | Objeto JSON | { "naturezaJuridica": "2135", "porteEmpresa": "01" } |
| naturezaJuridica | Código que identifica a constituição jurídico-institucional da entidade, conforme a Tabela de Natureza Jurídica do IBGE, categorizando-a em: Administração pública; Entidades empresariais; Entidades sem fins lucrativos; Pessoas físicas e organizações internacionais; e Outras instituições extraterritoriais. | Obrigatório. O cliente (receptor/iniciador) deve obter essa informação a partir de fontes oficiais (ex., Governo Federal/Dados Abertos/Base CNPJs ou API do SERPRO), com base no CNPJ do usuário, e reportá-la como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | ^\d{4}$ | 2135 |
| porteEmpresa | Código numérico que identifica o porte da empresa do cliente Pessoa Jurídica (PJ), conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O receptor/iniciador, que detém o CNPJ do usuário, é responsável por obter o código do porte da empresa. Esta informação deve ser consultada e validada a partir de fontes oficiais, como a base de Dados Abertos do CNPJ ou a API do SERPRO, ambas mantidas pelo Governo Federal, e conforme o Dicionário de Dados do CNPJ da Receita Federal. O valor deve ser enviado como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | ^\d{2}$ | 01 |
| consentId​ | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos menos 4xx e 5xx para o método POST | Todos | | /open-banking/enrollments/v x /consents/{consentId}/authorise /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options | v1 v2 | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | uri:bv:6096c7f6-53a0-4c53-bc95-9c8d48b9a6cf |
| dropReason | Razão pela qual um usuário não conseguiu prosseguir em uma jornada, especificamente no contexto de consentimentos | O campo dropReason deve ser adicionado nas informações do campo additionalInfo que deverá ser enviado no reporte do provedor do serviço consumido (papel SERVER) O reporte deverá ser feito por todos os transmissores de dados e detentoras de conta. Para os casos em que ocorram falhas técnicas que impossibilitem a verificação do CPF/CNPJ (incluindo, mas não se limitando, a erros HTTP 4xx, 500 ou timeout na resposta), o reporte deve ser realizado com o valor NO_CREDENTIAL, Em jornadas de múltipla alçada de pessoas jurídicas, quando a autenticação é bem-sucedida mas os poderes constituídos são insuficientes para finalização do Hybrid Flow, deve-se usar NO_AUTHORITY. NONE : quando o CPF (loggedUser) / CNPJ (businessEntity) possui credencial autenticadora e poderes suficientes para prosseguir o fluxo monitorado - exemplo: PF, cliente, que possui credencial ativa, mas não se autenticou; cliente que se autenticou utilizando a credencial correta. NO_CREDENTIAL : quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado ou quando o HTTP response code for diferente de 201. NO_AUTHORITY : quando o CPF (loggedUser) / CNPJ (businessEntity) consegue se autenticar, mas não dispõe de poderes ou alçadas para prosseguir no fluxo de compartilhamento de dados e serviços. NO_AUTHORITY_PERSON_MISMATCH : quando o CPF (loggedUser) não possui relação com a credencial utilizada na etapa de autenticação do Hybrid Flow - exemplo: consentimento criado para um CPF e autenticado por outro; criado para um CNPJ e autenticado por CPF sem relação com o CNPJ. | SERVER | Todos | POST | NO_AUTHORITY, NO_AUTHORITY_PERSON_MISMATCH, NO_CREDENTIAL, NONE | /open-banking/enrollments/v x /enrollments | v1 v2 | | |
| enrollmentId | Identificador usado para registrar uma jornada ou um vínculo inicial | Deve ser preenchido com a mesma string obtida no campo .data.enrollmentId retornado após a chamada inicial na API "POST /enrollments". | CLIENT | 2XX | POST | | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /recurring-consents/{recurringConsentId}/authorise | v1 v2 | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| enrollmentId | Identificador usado para registrar uma jornada ou um vínculo inicial | Deve ser preenchido com a mesma string obtida no campo .data.enrollmentId retornado após a chamada inicial na API "POST /enrollments". | CLIENT | Todos | Todos | | /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v x /consents/{consentId}/authorise | v1 v2 | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| errorCodes | Registrar os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 422 | Todos | 422ReponseError Create Enrollment CONTA_INVALIDA, ERRO_IDEMPOTENCIA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PERMISSOES_INVALIDAS 422ReponseError Cancel Enrollment ERRO_IDEMPOTENCIA, MOTIVO_REJEICAO, MOTIVO_REVOGACAO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, REJEITADO_OUTRO_SEM_DETALHES, REVOGADO_OUTRO_SEM_DETALHES, STATUS_INVALIDO 422ResponseError Fido Registration CHALLENGE_INVALIDO, ERRO_IDEMPOTENCIA, EXTENSION_INVALIDA, ORIGEM_FIDO_INVALIDA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PUBLIC_KEY_INVALIDA, RP_INVALIDA, STATUS_VINCULO_INVALIDO 422ResponseError Fido Registration-Options ERRO_IDEMPOTENCIA, MAXIMO_CHALLENGES_ATINGIDO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, RP_INVALIDA, STATUS_VINCULO_INVALIDO 422ResponseError Risk Signals ERRO_IDEMPOTENCIA, FALTAM_SINAIS_OBRIGATORIOS_DA_PLATAFORMA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, STATUS_VINCULO_INVALIDO 422ResponseError Fido Sign Options ERRO_IDEMPOTENCIA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PERMISSAO_INVALIDA_VINCULO_CONSENTIMENTO, RP_INVALIDA, STATUS_CONSENTIMENTO_INVALIDO, STATUS_VINCULO_INVALIDO 422ResponseError Consents Authorization CONTA_DEBITO_DIVERGENTE_CONSENTIMENTO_VINCULO, ERRO_IDEMPOTENCIA, FALTAM_SINAIS_OBRIGATORIOS_DA_PLATAFORMA, ORIGEM_FIDO_INVALIDA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, RISCO, STATUS_CONSENTIMENTO_INVALIDO, STATUS_VINCULO_INVALIDO 422ResponseError Create Consent COMBINACAO_PERMISSOES_INCORRETA, DATA_EXPIRACAO_INVALIDA, DEPENDE_MULTIPLA_ALCADA, ERRO_NAO_MAPEADO, ESTADO_CONSENTIMENTO_INVALIDO, INFORMACOES_PJ_NAO_INFORMADAS, PERMISSAO_PF_PJ_EM_CONJUNTO, PERMISSOES_PJ_INCORRETAS, SEM_PERMISSOES_FUNCIONAIS_RESTANTES | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v x /consents/{consentId}/authorise | v1 v2 | | |
| errorCodes | Registrar os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 4xx e 5xx exceto 422 | Todos | | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v x /consents/{consentId}/authorise /open-banking/enrollments/v x /recurring-consents/{recurringConsentId}/authorise | v1 v2 | | |
| journeyIsLinked | Indica que o consentimento faz parte de uma jornada otimizada | Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.isLinked”, retornado após a chamada inicial na API “POST /enrollments” em caso de Jornada Otimizada | CLIENT | Todos | POST GET | TRUE, FALSE | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} | v1 v2 | | |
| journeyLinkId | Identifica o consentimento de dados vinculado a uma Jornada Otimizada. | Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.linkId”, retornado após a chamada inicial na API “POST /enrollments” em caso de Jornada Otimizada. | CLIENT | Todos | POST GET | | /open-banking/enrollments/v x/ enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} | v1 v2 | | |
| nfcPayment | Identifica se o pagamento foi realizado através de NFC | Enviar o valor do campo "x-bcb-nfc", presente no de request header do endpoint de autorização de consentimentos via JSR (POST /consents/{consentId}/authorise) | CLIENT | Todos | POST | TRUE, FALSE | /open-banking/enrollments/v x /consents/{consentId}/authorise | v2 | | |
| personType | Identifica a natureza do solicitante em uma transação ou consentimento. | Se .data.businessEntity estiver preenchido no payload, se estiver então preencher com "PJ", se não estiver então preencher com "PF" | CLIENT | 2xx | POST GET | PF, PJ,PESSOA_NATURAL, PESSOA_JURIDICA | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} | v1 v2 | | |
| platform | Identifica a plataforma utilizada | Deve ser preenchido com a mesma string definida em ".data.platform" | CLIENT | | Todos | | /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options | v1 v2 | | |
| recurringConsentId​ | Identificador único do consentimento de longa duração criado para a iniciação de pagamento solicitada | Deverá ser um URN - Uniform Resource Name. Um URN, conforme definido na RFC8141 é um Uniform Resource Identifier - URI - que é atribuído sob o URI scheme "urn" e um namespace URN específico, com a intenção de que o URN seja um identificador de recurso persistente e independente da localização. Considerando a string urn:bancoex:C1DD33123 como exemplo para `recurringConsentId` temos: o namespace(urn) o identificador associado ao namespace da instituição transmissora (bancoex) o identificador específico dentro do namespace (C1DD33123). Informações mais detalhadas sobre a construção de namespaces devem ser consultadas na RFC8141 . | CLIENT | Todos menos 4xx e 5xx para o método POST | Todos | | /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v x /recurring-consents/{recurringConsentId}/authorise | v1 v2 | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | uri:bv:6096c7f6-53a0-4c53-bc95-9c8d48b9a6cf |
| rejectionReasonCode | Código da razão pela qual um consentimento ou pagamento foi rejeitado | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.code, “data.rejection.reason.code” ou “data.cancellation.reason.rejectionReason". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista. | CLIENT | Todos | GET PATCH | REJEITADO_DISPOSITIVO_INCOMPATIVEL, REJEITADO_FALHA_FIDO, REJEITADO_FALHA_HYBRID_FLOW, REJEITADO_FALHA_INFRAESTRUTURA, REJEITADO_MANUALMENTE, REJEITADO_MAXIMO_CHALLENGES_ATINGIDO, REJEITADO_OUTRO, REJEITADO_SEGURANCA_INTERNA, REJEITADO_TEMPO_EXPIRADO_ACCOUNT_HOLDER_VALIDATION, REJEITADO_TEMPO_EXPIRADO_RISK_SIGNALS, REJEITADO_TEMPO_EXPIRADO_ENROLLMENT, REJEITADO_TITULARIDADE_DIVERGENTE | /open-banking/enrollments/v x /enrollments/{enrollmentId} | v1 v2 | | |
| revocationReasonCode | Código indicador do motivo da revogação | | CLIENT | Todos (PATCH) 200 (GET) | GET PATCH | REVOGADO_FALHA_INFRAESTRUTURA, REVOGADO_MANUALMENTE, REVOGADO_OUTRO, REVOGADO_SEGURANCA_INTERNA, REVOGADO_VALIDADE_EXPIRADA | /open-banking/enrollments/v x /enrollments/{enrollmentId} | v1 v2 | | |
| rp | "Relying Party" (RP) onde reside originalmente na requisição FIDO | Deve ser preenchido com a mesma string definida em ".data.rp" | CLIENT | Todos | POST | | /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options | v1 v2 | | |
| status | Identifica o status atual do recurso (como um consentimento, um pagamento ou vínculo) que está sendo reportado. | Deve ser preenchido com a mesma string obtida no ".data.status". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | 2xx | GET POST | AWAITING_RISK_SIGNALS, AWAITING_ACCOUNT_HOLDER_VALIDATION, AWAITING_ENROLLMENT, AUTHORISED, REVOKED, REJECTED | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} | v1 v2 | | |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | | /open-banking/enrollments/v x /enrollments /open-banking/enrollments/v x /enrollments/{enrollmentId} /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v x /enrollments/{enrollmentId}/risk-signals /open-banking/enrollments/v x /consents/{consentId}/authorise | v2 | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Pagamentos Automáticos

| Campo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Domínio | Endpoints | Versões | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| authorisationFlowIntent | Permite a desambiguação e clara distinção entre as jornadas de pagamento que demandam ou não redirecionamento do usuário, já na etapa de provisionamento do consentimento | O campo deve ser preenchido obrigatoriamente com um dos valores do enum: HYBRID_FLOW, CIBA_FLOW ou FIDO_FLOW. A instituição iniciadora deve comunicar a intenção de fluxo de autorização que será utilizado na jornada de pagamento. Esta informação é essencial para a desambiguação das jornadas de pagamento na etapa de consentimento.   Nota técnica: Esta informação não existe tecnicamente nesta etapa da API de Consents; cabe à instituição iniciadora, por seu conhecimento prévio, reportar sua intenção de fluxo que será efetivamente utilizado na transação. | CLIENT | Todos | POST GET PATCH | CIBA_FLOW, FIDO_FLOW, HYBRID_FLOW | /open-banking/automatic-payments/v x /recurring-consents | v2 | | |
| companyProfileInfo | Objeto JSON que representa o perfil da Pessoa Jurídica (PJ) do cliente, contendo informações como a natureza jurídica e o porte da empresa, conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O objeto deve conter um objeto de perfil da empresa. As informações de natureza jurídica e porte devem ser obtidas prioritariamente da API oficial Consulta CNPJ (RFB/SERPRO) ou dos Dados Abertos do CNPJ (RFB) , conforme o Dicionário de Dados do CNPJ da Receita Federal. Este objeto deve ser enviado como parte do additionalInfo ao consumir as APIs de criação de consentimento para dados e serviços. Consulta CNPJ — Catálogo de APIs governamentais (API/Swagger) Portal de Dados Abertos (arquivo de dados) | CLIENT | Todos | POST | | /open-banking/automatic-payments/v x /recurring-consents | v2 | Objeto JSON | { "naturezaJuridica": "2135", "porteEmpresa": "01" } |
| naturezaJuridica | Código que identifica a constituição jurídico-institucional da entidade, conforme a Tabela de Natureza Jurídica do IBGE, categorizando-a em: Administração pública; Entidades empresariais; Entidades sem fins lucrativos; Pessoas físicas e organizações internacionais; e Outras instituições extraterritoriais. | Obrigatório. O cliente (receptor/iniciador) deve obter essa informação a partir de fontes oficiais (ex., Governo Federal/Dados Abertos/Base CNPJs ou API do SERPRO), com base no CNPJ do usuário, e reportá-la como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | ^\d{4}$ | 2135 |
| porteEmpresa | Código numérico que identifica o porte da empresa do cliente Pessoa Jurídica (PJ), conforme a classificação oficial da Receita Federal do Brasil. | Obrigatório para clientes PJ. O receptor/iniciador, que detém o CNPJ do usuário, é responsável por obter o código do porte da empresa. Esta informação deve ser consultada e validada a partir de fontes oficiais, como a base de Dados Abertos do CNPJ ou a API do SERPRO, ambas mantidas pelo Governo Federal, e conforme o Dicionário de Dados do CNPJ da Receita Federal. O valor deve ser enviado como parte do additionalInfo quando houver consumo as APIs de criação de consentimento para compartilhamento de dados e serviços. | | | | | | | ^\d{2}$ | 01 |
| consentId | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consents | CLIENT | Todos menos 4xx e 5xx para o método POST | GET PATCH POST | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v1 v2 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | uri:bv:6096c7f6-53a0-4c53-bc95-9c8d48b9a6cf |
| dropReason | Razão pela qual um usuário não conseguiu prosseguir em uma jornada, especificamente no contexto de consentimentos | O campo dropReason deve ser adicionado nas informações do campo additionalInfo que deverá ser enviado no reporte do provedor do serviço consumido (papel SERVER) O reporte deverá ser feito por todos os transmissores de dados e detentoras de conta. Para os casos em que ocorram falhas técnicas que impossibilitem a verificação do CPF/CNPJ (incluindo, mas não se limitando, a erros HTTP 4xx, 500 ou timeout na resposta), o reporte deve ser realizado com o valor NO_CREDENTIAL, Em jornadas de múltipla alçada de pessoas jurídicas, quando a autenticação é bem-sucedida mas os poderes constituídos são insuficientes para finalização do Hybrid Flow, deve-se usar NO_AUTHORITY. NONE : quando o CPF (loggedUser) / CNPJ (businessEntity) possui credencial autenticadora e poderes suficientes para prosseguir o fluxo monitorado - exemplo: PF, cliente, que possui credencial ativa, mas não se autenticou; cliente que se autenticou utilizando a credencial correta. NO_CREDENTIAL : quando o CPF (loggedUser) / CNPJ (businessEntity) não for cliente ou não possuir credencial válida/ativa para prosseguir no fluxo monitorado ou quando o HTTP response code for diferente de 201. NO_AUTHORITY : quando o CPF (loggedUser) / CNPJ (businessEntity) consegue se autenticar, mas não dispõe de poderes ou alçadas para prosseguir no fluxo de compartilhamento de dados e serviços. NO_AUTHORITY_PERSON_MISMATCH : quando o CPF (loggedUser) não possui relação com a credencial utilizada na etapa de autenticação do Hybrid Flow - exemplo: consentimento criado para um CPF e autenticado por outro; criado para um CNPJ e autenticado por CPF sem relação com o CNPJ. | SERVER | Todos | POST | NO_AUTHORITY, NO_AUTHORITY_PERSON_MISMATCH, NO_CREDENTIAL, NONE | /open-banking/automatic-payments/v x /recurring-consents | v2 | | |
| errorCodes | Registra os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 4xx ou 5xx | POST | ReponseError Create Consent DATA_PAGAMENTO_INVALIDA, DETALHE_PAGAMENTO_INVALIDO, ERRO_IDEMPOTENCIA, FUNCIONALIDADE_NAO_HABILITADA, NAO_INFORMADO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO 422ReponseError Recurring Consent CAMPO_NAO_PERMITIDO, CONSENTIMENTO_NAO_PERMITE_CANCELAMENTO, DETALHE_EDICAO_INVALIDO, FALTAM_SINAIS_OBRIGATORIOS_PLATAFORMA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PERMISSAO_INSUFICIENTE 422ResponseError PIX Recurring Payment CONSENTIMENTO_INVALIDO, CONSENTIMENTO_PENDENTE_AUTORIZACAO, DETALHE_PAGAMENTO_INVALIDO, ERRO_IDEMPOTENCIA, FORA_PRAZO_PERMITIDO, LIMITE_PERIODO_QUANTIDADE_EXCEDIDO, LIMITE_PERIODO_VALOR_EXCEDIDO, LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO, LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO, NAO_INFORMADO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, SALDO_INSUFICIENTE, VALOR_ACIMA_LIMITE, VALOR_INVALIDO 422ReponseErrorCreate Recurring Payment PaymentId CANCELAMENTO_FORA_PERIODO_PERMITIDO, PAGAMENTO_NAO_PERMITE_CANCELAMENTO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /pix/recurring-payments | v2 | | |
| errorCodes | Registra os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. Não havendo string, deve ser enviada uma lista vazia. | CLIENT | 4xx ou 5xx | GET PATCH | ReponseError Create Consent DATA_PAGAMENTO_INVALIDA, DETALHE_PAGAMENTO_INVALIDO, ERRO_IDEMPOTENCIA, FUNCIONALIDADE_NAO_HABILITADA, NAO_INFORMADO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO 422ReponseError Recurring Consent CAMPO_NAO_PERMITIDO, CONSENTIMENTO_NAO_PERMITE_CANCELAMENTO, DETALHE_EDICAO_INVALIDO, FALTAM_SINAIS_OBRIGATORIOS_PLATAFORMA, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PERMISSAO_INSUFICIENTE 422ResponseError PIX Recurring Payment CONSENTIMENTO_INVALIDO, CONSENTIMENTO_PENDENTE_AUTORIZACAO, DETALHE_PAGAMENTO_INVALIDO, ERRO_IDEMPOTENCIA, FORA_PRAZO_PERMITIDO, LIMITE_PERIODO_QUANTIDADE_EXCEDIDO, LIMITE_PERIODO_VALOR_EXCEDIDO, LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO, LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO, NAO_INFORMADO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, SALDO_INSUFICIENTE, VALOR_ACIMA_LIMITE, VALOR_INVALIDO 422ReponseErrorCreate Recurring Payment PaymentId CANCELAMENTO_FORA_PERIODO_PERMITIDO, PAGAMENTO_NAO_PERMITE_CANCELAMENTO, PARAMETRO_INVALIDO, PARAMETRO_NAO_INFORMADO | /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | |
| paymentList | Lista de dados de pagamentos com agendamentos recorrentes Os itens indentados abaixo pertencem ao objeto paymentList e seguem as mesmas regras de obrigatoriedade | | CLIENT | 200 | GET | | /open-banking/automatic-payments/v x /pix/recurring-payments | v2 | | |
| paymentId | Código ou identificador único informado pela instituição detentora da conta para representar a iniciação de pagamento​ | | | | | | | | | |
| consentId | Identificador único do consentimento criado para a iniciação de pagamento solicitada​ | | | | | | | | | |
| statusUpdateDateTime | Data e hora da última atualização da iniciação de pagamento | | | | | | | | | |
| status | Estado atual do pagamento | | | | | | | | | |
| rejectionReasonCode | Código identificador do motivo de rejeição. Deve ser enviado vazio se não houver conteúdos, seguindo a mesma regra da API de negócio relacionada | | | | | | | | | |
| rejectionReasonDetail | Detalhe sobre o código identificador do motivo de rejeição. Deve ser enviado vazio se não houver conteúdos, seguindo a mesma regra da API de negócio relacionada | | | | | | | | | |
| paymentType | Identifica o modo de pagamento acionado no consentimento | Identifica o modo de pagamento acionado no consentimento e deve ser preenchido de acordo com o campo ".data.recurringConfiguration/oneOf" IMMEDIATE : Pix sem configuração de agendamento SCHEDULED : Pix com configuração de agendamento RECURRENT : Pix com agendamento e recorrência SWEEPING : Chamadas de pagamentos inteligentes AUTOMATIC : Pagamentos automáticos | CLIENT | Todos | PATCH POST | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v1 | | |
| paymentType | Identifica o modo de pagamento acionado no consentimento | Identifica o modo de pagamento acionado no consentimento e deve ser preenchido de acordo com o campo ".data.recurringConfiguration/oneOf" IMMEDIATE : Pix sem configuração de agendamento SCHEDULED : Pix com configuração de agendamento RECURRENT : Pix com agendamento e recorrência SWEEPING : Chamadas de pagamentos inteligentes AUTOMATIC : Pagamentos automáticos | CLIENT | Todos | GET | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v1 | | |
| recurringPaymentDate | Data em que o pagamento será realizado | Deve ser preenchido com a mesma string obtida no ".data.date". | CLIENT | 201 | POST | | /open-banking/automatic-payments/v x /pix/recurring-paymens | v2 | | |
| referenceStartDate | Data prevista para o início do ciclo de cobrança dos pagamentos associados à recorrência | Preencher com o valor do campo ".data.recurringConfiguration.automatic.referenceStartDate". Deve ser preenchido quando paymentType for AUTOMATIC. | CLIENT | 2xx | POST GET PATCH | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v1 v2 | | |
| rejectedBy | Quem iniciou a solicitação de rejeição | | CLIENT | Todos menos 4xx e 5xx | GET PATCH | DETENTORA, INICIADORA, USUARIO | /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v1 v2 | | |
| rejectedFrom | Canal onde iniciou-se o processo de rejeição | | CLIENT | Todos menos 4xx e 5xx | GET PATCH | DETENTORA, INICIADORA | /open-banking/automatic-payments/vx/recurring-consents/{recurringConsentId} | v1 v2 | | |
| rejectionReasonCode | Código da razão pela qual um consentimento ou pagamento foi rejeitado | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.code". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | Todos menos 4xx e 5xx | GET PATCH | AUTENTICACAO_DIVERGENTE, CONTA_NAO_PERMITE_PAGAMENTO, CONTAS_ORIGEM_DESTINO_IGUAIS, FALHA_INFRAESTRUTURA, FLUXO_NAO_SUPORTADO_PRODUTO, NAO_INFORMADO, REJEITADO_USUARIO, SALDO_INSUFICIENTE, TEMPO_EXPIRADO_AUTORIZACAO, VALOR_ACIMA_LIMITE | /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v1 v2 | | |
| rejectionReasonDetail | Detalhe mais específico sobre a rejeição de um consentimento ou pagamento | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.detail". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista additionalInfo_status deve ser 'REJECTED' ou 'RJCT' | CLIENT | Todos menos 4xx e 5xx | GET PATCH | | /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v1 v2 | | |
| tokenId | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | Todos | Todos | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |

### Específicos PIX Automático - estes campos de additionalInfo somente são validados para automatic-payments v2 em diante

| Campo | Grupo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Domínio | Endpoints | Versões | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| amountType | Pagamentos | Valida se o serviço contratado possui maior conversão em relação ao tipo do valor definido, sendo ele fixo ou variável​ | Se não enviando nem ".data.recurringConfiguration.automatic.fixedAmount" e nem ".data.recurringConfiguration.automatic.maximumVariableAmount", “VARIAVEL”; ou Se enviado fixedAmount, “FIXO”; ou Se enviado maximumVariableAmount, “VARIAVEL” Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | FIXO, VARIAVEL | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| authorisationFlow | Pagamentos | Identifica o fluxo de autorização em que um pagamento ou operação foi solicitado | O campo deve ser preenchido com a string obtida em ".data.authorisationFlow". Se a informação for uma lista, utilize apenas o primeiro item. Caso a string de ".data.authorisationFlow" seja nula, preencha obrigatoriamente com HYBRID_FLOW. É fundamental que sempre seja reportado um dos valores do enum (como HYBRID_FLOW, CIBA ou FIDO), e nunca um valor nulo, pois para fins de telemetria é necessário identificar explicitamente qual fluxo de autorização foi utilizado, independentemente da permissão de valor nulo nas especificações das APIs do Open Finance. | CLIENT | Todos | GET PATCH POST | CIBA_FLOW, FIDO_FLOW, HYBRID_FLOW | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| cancellationReason | Pagamentos | Identifica o estado que o pagamento estava quando foi cancelado​ | Preencher com o valor do campo ".cancellation.reason" Deve ser enviado quando em um GET ou POST /payment e o campo status é "CANC" ou em um PATCH /payment (que é a API de cancelamento). | CLIENT | 2xx | GET PATCH POST | CANCELADO_AGENDAMENTO, CANCELADO_PENDENCIA | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| cancelledFrom | Pagamentos | Informa o meio pelo qual foi realizado o cancelamento | Preencher com o valor do campo ".cancellation.cancelledFrom" Status do pagamento deve ser "CANC" | CLIENT | 2xx | GET PATCH POST | DETENTORA, INICIADORA | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| hasMinimumAmount | Consentimentos | Valida se possui o valor mínimo definido pelo usuário recebedor​ | Se preenchido o campo “.data/recurringConfiguration.automatic.minimumVariableAmount”, enviar "TRUE"; ou Se não preenchido o campo “.data.recurringConfiguration.automatic.minimumVariableAmount” enviar "FALSE" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | TRUE, FALSE | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| interval | Consentimentos | Periodicidade que a recorrência foi definida (semanal, trimestral, anual...)​ | Preencher com o valor do campo ".data.recurringConfiguration.interval" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| isFirstPayment | Consentimentos | Valida se o serviço possui um pagamento associado na adesão | Se preenchido o campo ".data.recurringConfiguration.automatic.firstPayment", enviar "TRUE"; ou Se não preenchido o campo ".data.recurringConfiguration.automatic.firstPayment", enviar "FALSE" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | TRUE, FALSE | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| isRetryAccepted | Consentimentos | Identifica se foi autorizado a tentativas de pagamento em dias subsequentes na situação de falha do pagamento da recorrência​ | Preencher com o valor do campo ".data.recurringConfiguration.automatic.isRetryAccepted" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| journeyIsLinked | Consentimento em Jornada Otimizada | Indica que o consentimento faz parte de uma jornada otimizada. | Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.isLinked”, retornado após a chamada inicial na API “POST /consent” em caso de Jornada Otimizada. | CLIENT | Todos | POST GET | TRUE, FALSE | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| journeyLinkId | Consentimento em Jornada Otimizada | Identifica o consentimento de dados vinculado a uma Jornada Otimizada. | Deve ser preenchido com a mesma string enviada ou recebida no campo “.data.journey.linkId”, retornado após a chamada inicial na API “POST /consent” em caso de Jornada Otimizada. | CLIENT | Todos | POST GET | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| localInstrument | Pagamentos | Especifica a forma de iniciação do pagamento​ | Deve ser preenchido com a mesma string informada no payload ".data.localInstrument" Caso consentimento associado a tentativa de pagamento seja para Pix automático (objeto “automatic” selecionado no oneOf do campo "/data/recurringConfiguration") e a referência do pagamento indicar uma recorrência (valor do campo "/data/paymentReference" diferente de "zero"), apenas o método AUTO é permitido, ou; Caso consentimento associado a tentativa de pagamento seja para Pix automático (objeto “automatic” selecionado no oneOf do campo "/data/recurringConfiguration") e a referência do pagamento indicar o pagamento inicial avulso (valor do campo "/data/paymentReference" igual a "zero"), apenas o método MANU é permitido. Para consentimentos de Transferências Inteligentes (objeto “sweeping” selecionado no “oneOf” do campo “/data/recurringConfiguration/”), apenas os métodos MANU, DICT e INIC são permitidos | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | DICT, INIC, MANU, QRDN, QRES, AUTO | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| originalRecurringPaymentId | Pagamentos | Identifica o primeiro pagamento da recorrência em relação as retentativas​ | Preencher com o valor do campo ".data.originalRecurringPaymentId" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST/PATCH) Todos menos 4xx e 5xx (GET) | GET PATCH POST | | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| paymentReference | Pagamentos | Identifica a referência do pagamento no tempo (semanal, mensal, trimestral...)​ | Preencher com o valor do campo ".data.paymentReference" Deve ser preenchido quando paymentType for AUTOMATIC | CLIENT | Todos (POST/PATCH) Todos menos 4xx e 5xx (GET) | GET PATCH POST | | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| paymentType | Consentimentos e Pagamentos | Identifica o modo de pagamento acionado no consentimento | IMMEDIATE : Pix sem configuração de agendamento SCHEDULED : Pix com configuração de agendamento RECURRENT : Pix com agendamento e recorrência SWEEPING : Chamadas de pagamentos inteligentes AUTOMATIC : Pagamentos automáticos | CLIENT | Todos (POST) Todos menos 4xx e 5xx (GET/PATCH) | GET PATCH POST | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| personType | Consentimentos | Identifica a natureza do solicitante em uma transação ou consentimento. | Se .data.businessEntity estiver preenchido no payload, se estiver então preencher com "PJ", se não estiver então preencher com "PF" | CLIENT | 2xx | GET PATCH POST | PF, PJ,PESSOA_NATURAL, PESSOA_JURIDICA | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |
| recurringPaymentId | Pagamentos | Contagem de acionamentos feitos no pagamento​ | Para Pagamentos v4: Preencher com o valor do campo "/data/paymentId" Para Pagamentos Automáticos v2: Preencher com o valor do campo "/data/recurringPaymentId"​ | CLIENT | Todos menos 4xx e 5xx | GET PATCH POST | | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| rejectionReasonCode | Consentimentos e Pagamentos | Código da razão pela qual um consentimento ou pagamento foi rejeitado | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.code". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | GET PATCH POST | Pagamentos CONSENTIMENTO_INVALIDO, CONSENTIMENTO_REVOGADO, DETALHE_PAGAMENTO_INVALIDO, DETALHE_TENTATIVA_INVALIDO, FALHA_INFRAESTRUTURA_DETENTORA, FALHA_INFRAESTRUTURA_ICP, FALHA_INFRAESTRUTURA_PSP_RECEBEDOR, FALHA_INFRAESTRUTURA_SPI, FORA_PRAZO_PERMITIDO, LIMITE_PERIODO_QUANTIDADE_EXCEDIDO, LIMITE_PERIODO_VALOR_EXCEDIDO, LIMITE_TENTATIVAS_EXCEDIDO, LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO, NAO_INFORMADO, LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, SALDO_INSUFICIENTE, TITULARIDADE_INCONSISTENTE, VALOR_ACIMA_LIMITE, VALOR_INVALIDO ConsentRejectionReason AUTENTICACAO_DIVERGENTE, CONTA_NAO_PERMITE_PAGAMENTO, CONTAS_ORIGEM_DESTINO_IGUAIS, FALHA_INFRAESTRUTURA, NAO_INFORMADO, REJEITADO_USUARIO, SALDO_INSUFICIENTE, TEMPO_EXPIRADO_AUTORIZACAO, VALOR_ACIMA_LIMITE | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| rejectionReasonDetail | Consentimentos e Pagamentos | Detalhe mais específico sobre a rejeição de um consentimento ou pagamento | Deve ser preenchido com a mesma string obtida no ".data.rejectionReason.detail". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista additionalInfo_status deve ser 'REJECTED' ou 'RJCT' | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | GET PATCH POST | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId | v2 | | | |
| revocationReasonCode | Consentimentos e Pagamentos | Código indicador do motivo da revogação | | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | GET PATCH POST | NAO_INFORMADO, REVOGADO_RECEBEDOR, REVOGADO_USUARIO | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| revocationReasonDetail | Consentimentos | Detalhe sobre a revogação referente ao consentimento​ | | CLIENT | Todos (POST/GET) Todos menos 4xx e 5xx (PATCH) | GET PATCH POST | | /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} | v2 | | | |
| status | Consentimentos e Pagamentos | Identifica o status atual do recurso (como um consentimento ou um pagamento) que está sendo reportado. | Deve ser preenchido com a mesma string obtida no ".data.status". Caso a informação esteja em formato de lista, enviar apenas o valor do primeiro item da lista | CLIENT | 2xx | GET PATCH POST | Para consentimentos: AWAITING_AUTHORISATION, PARTIALLY_ACCEPTED, AUTHORISED, REJECTED, REVOKED, CONSUMED. Para pagamentos: RCVD, CANC, ACCP, ACPD, RJCT, ACSC, PDNG, SCHD. | /open-banking/automatic-payments/v x /pix/recurring-payments /open-banking/automatic-payments/v x /pix/recurring-payments/{recurringPaymentId} /open-banking/automatic-payments/v x /recurring-consents /open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId} | v2 | | | |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Pagamentos > Regras de Validação - SV

---
id: 1212383233
title: Regras de Validação - SV
version: 2
modified: 2026-02-09T18:11:34.513Z
url: /spaces/OF/pages/1212383233/Regras+de+Valida+o+-+SV
---

v 1.04**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Pagamentos

### Iniciação de Pagamentos

| Campo | Regra |
| --- | --- |
| authorisationFlow | SE Role = CLIENT E endpoint = %payments/v x /pix/payments ou %payments/v x /pix/payments/{paymentId} E método = POST, PATCH ou GET ENTÃO Se o authorisationFlow for nulo, retorna Nulo Se o authorisationFlow for vazio, retorna Vazio Se o authorisationFlow não for CIBA_FLOW, FIDO_FLOW ou HYBRID_FLOW, retorna Invalido |
| authorisationFlowIntent | SE Role = CLIENT E endpoint = %/payments/v x /consents E método = POST, PATCH ou GET ENTÃO Se o authorisationFlowIntent for nulo, retorna Nulo Se o authorisationFlowIntent for vazio, retorna Vazio Se o authorisationFlowIntent não for CIBA_FLOW, FIDO_FLOW ou HYBRID_FLOW, retorna Invalido |
| companyProfileInfo | SE Role = CLIENT E personType = PJ ou PESSOA_JURIDICA E endpoint = %/payments/v x /consents E método = POST ENTÃO Se naturezaJuridica e porteEmpresa forem simultaneamente nulos ou vazios, retorna Nulo/Vazio Se naturezaJuridica for nulo ou vazio e porteEmpresa estiver preenchido, retorna Incompleto - sem Natureza Juridica Se naturezaJuridica estiver preenchido e porteEmpresa estiver nulo ou vazio, retorna Incompleto - sem Porta da Empresa Se o porteEmpresa não for 00, 01, 03 ou 05, retorna Invalido |
| consentId | SE Role = CLIENT E endpoint = %/payments/v x /consents% E método = GET ou PATCH com qualquer statusCode OU POST com statusCode diferente de 4xx e 5xx OU %/payments/v x /pix/payments% E método = POST, GET ou PATCH com qualquer statusCode ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| dropReason | SE Role = SERVER E endpoint = %/payments/v x /consents E método = POST ENTÃO Se o dropReason for nulo, retorna Nulo Se o dropReason for vazio, retorna Vazio Se o dropReaso não for NONE, NO_CREDENTIAL, NO_AUTHORITY ou NO_AUTHORITY_PERSON_MISMATCH, retorna Invalido |
| errorCodes | SE Role = CLIENT E statusCode = 4xx ou 5xx E endpoint = %/payments/v x /consents% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["DATA_PAGAMENTO_INVALIDA"], ["DETALHE_PAGAMENTO_INVALIDO"], ["ERRO_IDEMPOTENCIA"], ["FORMA_PAGAMENTO_INVALIDA"], ["NAO_INFORMADO"], ["PARAMETRO_INVALIDO"] ou ["PARAMETRO_NAO_INFORMADO"], retorna Invalido OU endpoint = %/payments/v x /pix/payments% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["COBRANCA_INVALIDA"], ["CONSENTIMENTO_INVALIDO"], ["CONSENTIMENTO_PENDENTE_AUTORIZACAO"], ["DETALHE_PAGAMENTO_INVALIDO"], ["ERRO_IDEMPOTENCIA"], ["NAO_INFORMADO"], ["PAGAMENTO_DIVERGENTE_CONSENTIMENTO"], ["PAGAMENTO_NAO_PERMITE_CANCELAMENTO"], ["PAGAMENTO_RECUSADO_DETENTORA"], ["PAGAMENTO_RECUSADO_SPI"], ["PARAMETRO_INVALIDO"], ["PARAMETRO_NAO_INFORMADO"], ["SALDO_INSUFICIENTE"], ["VALOR_ACIMA_LIMITE"] ou ["VALOR_INVALIDO"], retorna Invalido Se statuscode for 4xx ou 5xx e statusCode não for 422, retorna Error_Code invalido |
| localInstrument | SE Role = CLIENT E endpoint = %/payments/v x /consents ou %/payments/v x /pix/payments/{paymentId} E método = POST OU PATCH, GET com statusCode diferente de 4xx e 5xx ENTÃO Se o localInstrument for nulo, retorna Nulo Se o localInstrument for vazio, retorna Vazio Se o localInstrument não for DICT, INIC, MANU, QRDN, QRES ou AUTO, retorna Invalido |
| paymentSchedule | SE Role = CLIENT E paymentType for diferente de IMMEDIATE E endpoint = %/payments/v x /consents E método = POST E statusCode = 201 ENTÃO Se o conteúdo do paymentSchedule não tiver os tipos single, daily, weekly, monthly ou custom , retorna Conteudo do additionalInfo paymentSchedule nulo ou invalido Se o tipo de agendamento for single Se não possuir o campo date , retorna Conteudo do agendamento single nulo ou invalido Se possuir o campo date , porém não houver data informada, retorna Conteudo do agendamento single invalido Se o tipo de agendamento for daily Se não possuir os campos startDate ou quantity , retorna Conteudo do agendamento diario nulo ou invalido Se possuir os campos startDate e quantity , porém não houver dados informados, retorna Conteudo do agendamento diario invalido Se o tipo de agendamento for weekly Se não possuir os campos dayOfWeek, startDate ou quantity , retorna Conteudo do agendamento semanal nulo ou invalido Se possuir os campos dayOfWeek, startDate e quantity , porém não houver dados informados, retorna Conteudo do agendamento semanal invalido Se o tipo de agendamento for monthly Se não possuir os campos dayOfMonth, startDate ou quantity , retorna Conteudo do agendamento mensal nulo ou invalido Se possuir os campos dayOfMonth, startDate e quantity , porém não houver dados informados, retorna Conteudo do agendamento mensal invalido Se o tipo de agendamento for custom Se não possuir o campo dates , retorna Conteudo do agendamento custom nulo ou invalido Se possuir o campo dates , porém não houver dados informados, retorna Conteudo do agendamento custom invalido |
| paymentType | SE Role = CLIENT E endpoint = %/payments/v x /consents ou %/payments/v x /pix/payments E método = POST OU endpoint = %/payments/v x /pix/payments/{paymentId} E método = PATCH ENTÃO Se paymentType for nulo, retorna Nulo Se paymentType for vazio, retorna Vazio Se paymentType não for AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED ou SWEEPING, retorna Invalido |
| personType | SE Role = CLIENT E endpoint = %/payments/v x /consents E método = POST ENTÃO Se personType for nulo, retorna Nulo Se personType for vazio, retorna Vazio Se personType não for PF, PJ, PESSOA_JURIDICA ou PESSOA_NATURAL, retorna Invalido |
| rejectionReasonCode | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/payments/v x /consents/{consentId} ou %/payments/v x /pix/payments/{paymentId} E método = GET E statusCode não é 4xx ou 5xx ENTÃO Se rejectionReasonCode for nulo, retorna Nulo Se rejectionReasonCode for vazio, retorna Vazio Se rejectionReasonCode não for AUTENTICACAO_DIVERGENTE, COBRANCA_INVALIDA, CONSENTIMENTO_INVALIDO, CONSENTIMENTO_REVOGADO, CONTA_NAO_PERMITE_PAGAMENTO, CONTAS_ORIGEM_DESTINO_IGUAIS, DETALHE_PAGAMENTO_INVALIDO, DETALHE_TENTATIVA_INVALIDO, FALHA_AGENDAMENTO_PAGAMENTOS, FALHA_INFRAESTRUTURA, FALHA_INFRAESTRUTURA_DETENTORA, FALHA_INFRAESTRUTURA_DICT, FALHA_INFRAESTRUTURA_ICP, FALHA_INFRAESTRUTURA_PSP_RECEBEDOR, FALHA_INFRAESTRUTURA_SPI, FORA_PRAZO_PERMITIDO, LIMITE_PERIODO_QUANTIDADE_EXCEDIDO, LIMITE_PERIODO_VALOR_EXCEDIDO, LIMITE_TENTATIVAS_EXCEDIDO, LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO, LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO, NAO_INFORMADO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, QRCODE_INVALIDO, REJEITADO_USUARIO, SALDO_INSUFICIENTE, TEMPO_EXPIRADO_AUTORIZACAO, TEMPO_EXPIRADO_CONSUMO, TITULARIDADE_INCONSISTENTE, VALOR_ACIMA_LIMITE ou VALOR_INVALIDO, retorna Invalido |
| rejectionReasonDetail | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/payments/v x /consents/{consentId} ou %/payments/v x /pix/payments/{paymentId} E método = GET E statusCode não é 4xx ou 5xx ENTÃO Se rejectionReasonDetail for nulo, retorna Nulo Se rejectionReasonDetail for vazio, retorna Vazio |
| status | SE Role = CLIENT E endpoint = %/payments/v x /consents ou %/payments/v x /pix/payments E método = GET ou POST OU endpoint = %/payments/v x /pix/payments/{paymentId} ou %/payments/v x /pix/payments/consents/{consentId} E método = PATCH E statusCode = 2xx ENTÃO Se status for nulo, retorna Nulo Se status for vazio, retorna Vazio Se status não for AWAITING_AUTHORISATION, AUTHORISED, REJECTED, PARTIALLY_ACCEPTED, REVOKED, CONSUMED, AWAITING_RISK_SIGNALS, AWAITING_ACCOUNT_HOLDER_VALIDATION, AWAITING_ENROLLMENT, RCVD, CANC, ACCP, ACPD, RJCT, ACSC, PDNG ou SCHD, retorna Invalido |

### Iniciação de Pagamentos Sem Redirecionamento

| Campo | Regra |
| --- | --- |
| cancelledFrom | SE Role = CLIENT E status = CANC E endpoint = %/enrollments/v x /enrollments/{enrollmentId} E método = GET E statusCode = 2xx ENTÃO Se o cancelledFrom for nulo, retorna Nulo Se o cancelledFrom for vazio, retorna Vazio Se o cancelledFrom não for INICIADORA ou DETENTORA, retorna Invalido |
| companyProfileInfo | SE Role = CLIENT E personType = PJ ou PESSOA_JURIDICA E endpoint = %/enrollments/v x /enrollments E método = POST ENTÃO Se naturezaJuridica e porteEmpresa forem simultaneamente nulos ou vazios, retorna Nulo/Vazio Se naturezaJuridica for nulo ou vazio e porteEmpresa estiver preenchido, retorna Incompleto - sem Natureza Juridica Se naturezaJuridica estiver preenchido e porteEmpresa estiver nulo ou vazio, retorna Incompleto - sem Porta da Empresa Se o porteEmpresa não for 00, 01, 03 ou 05, retorna Invalido |
| consentId | SE Role = CLIENT E endpoint = %/enrollments/v x /consents/{consentId}/authorise ou %/enrollments/vx/enrollments/{enrollmentId}/fido-sign-options E não é método = POST com statusCode 4xx ou 5xx ENTÃO Se o enrollmentId e o consentId forem simultaneamente nulos, retorna Nulo Se o enrollmentId e o consentId forem simultaneamente vazios, retorna Vazio Se for o endpoint /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options consentId e o recurringConsentId estiverem simultaneamente preenchidos, retorna Invalido - nao podem ser preenchidos simulaneamente consentId e recurringConsentId Se for o endpoint /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options consentId e o recurringConsentId estiverem simultaneamente vazios ou nulos, retorna Pelo menos consentId ou recurringConsentId deve estar preenchido Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| dropReason | SE Role = SERVER E endpoint = %/enrollments/v x /enrollments E método = POST ENTÃO Se o dropReason for nulo, retorna Nulo Se o dropReason for vazio, retorna Vazio Se o dropReason não for NONE, NO_CREDENTIAL, AUTHORITY ou NO_AUTHORITY_PERSON_MISMATCH, retorna Invalido |
| enrollmentId | SE Role = CLIENT E endpoint = %/open-banking/enrollments/v x /enrollments E método = POST E statusCode = 2x OU endpoint = %/enrollments/v x /enrollments/{enrollmentId}/fido-registration, %/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options, %/enrollments/v x /enrollments/{enrollmentId}/risk-signals ou %/enrollments/v x /consents/{consentId}/authorise E método = POST, GET ou PATCH ENTÃO Se o enrollmentId e o consentId forem simultaneamente nulos, retorna Nulo Se o enrollmentId e o consentId forem simultaneamente vazios, retorna Vazio |
| errorCodes | SE Role = CLIENT E statusCode = 4xx ou 5xx E endpoint = %/enrollments/v x /enrollments/% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["CONTA_INVALIDA"], ["ERRO_IDEMPOTENCIA"], ["MOTIVO_REJEICAO"], ["MOTIVO_REVOGACAO"], ["PARAMETRO_INVALIDO"], ["PARAMETRO_NAO_INFORMADO"], ["PERMISSOES_INVALIDAS"], ["REJEITADO_OUTRO_SEM_DETALHES"], ["REVOGADO_OUTRO_SEM_DETALHES"] ou ["STATUS_INVALIDO"], retorna Invalido OU endpoint = %/enrollments/v x /enrollments/{enrollmentId}/fido% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["CHALLENGE_INVALIDO"], ["ERRO_IDEMPOTENCIA"], ["EXTENSION_INVALIDA"], ["MAXIMO_CHALLENGES_ATINGIDO"], ["ORIGEM_FIDO_INVALIDA"], ["PARAMETRO_INVALIDO"], ["PARAMETRO_NAO_INFORMADO"], ["PERMISSAO_INVALIDA_VINCULO_CONSENTIMENTO"], ["PUBLIC_KEY_INVALIDA"], ["RP_ID_HASH_INVALIDO"], ["RP_INVALIDA"], ["STATUS_CONSENTIMENTO_INVALIDO"] ou ["STATUS_VINCULO_INVALIDO"], retorna Invalido OU endpoint = %/enrollments/v x /enrollments/{enrollmentId}/risk% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["ERRO_IDEMPOTENCIA"], ["FALTAM_SINAIS_OBRIGATORIOS_DA_PLATAFORMA"], ["PARAMETRO_INVALIDO"], ["PARAMETRO_NAO_INFORMADO"] ou ["STATUS_VINCULO_INVALIDO"], retorna Invalido OU endpoint = %/enrollments/v x /consents% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["COMBINACAO_PERMISSOES_INCORRETA"], ["CONTA_DEBITO_DIVERGENTE_CONSENTIMENTO_VINCULO"], ["DATA_EXPIRACAO_INVALIDA"], ["DEPENDE_MULTIPLA_ALCADA"], ["ERRO_IDEMPOTENCIA"], ["ERRO_NAO_MAPEADO"], ["ESTADO_CONSENTIMENTO_INVALIDO"], ["FALTAM_SINAIS_OBRIGATORIOS_DA_PLATAFORMA"], ["INFORMACOES_PJ_NAO_INFORMADAS"], ["PARAMETRO_INVALIDO"], ["ORIGEM_FIDO_INVALIDA"], ["PARAMETRO_NAO_INFORMADO"], ["PERMISSAO_PF_PJ_EM_CONJUNTO"], ["PERMISSOES_PJ_INCORRETAS"], ["RISCO"], ["SEM_PERMISSOES_FUNCIONAIS_RESTANTES"], ["STATUS_CONSENTIMENTO_INVALIDO"] ou ["STATUS_VINCULO_INVALIDO"], retorna Invalido Se statuscode for 4xx ou 5xx e statusCode não for 422, retorna Error_Code invalido |
| nfcPayment | SE Role = CLIENT E endpoint = %/enrollments/v x /consents/{consentId}/authorise E método = POST ENTÃO Se nfcPayment for nulo, retorna Nulo Se nfcPayment for vazio, retorna Vazio Se nfcPayment não for TRUE ou FALSE, retorna Invalido |
| personType | SE Role = CLIENT E endpoint = %/enrollments/v x /enrollments ou %/enrollments/v x /enrollments/{enrollmentId} E método = POST, GET E statusCode = 2xx ENTÃO Se personType for nulo, retorna Nulo Se personType for vazio, retorna Vazio Se personType não for PF, PJ, PESSOA_JURIDICA ou PESSOA_NATURAL, retorna Invalido |
| platform | SE Role = CLIENT E endpoint = %/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options ou %/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options ENTÃO Se platform for nulo, retorna Nulo Se platform for vazio, retorna Vazio |
| recurringConsentId | SE Role = CLIENT E endpoint = %/enrollments/v % /enrollments/{enrollmentId}/fido-sign-options ou %/enrollments/v x /recurring-consents/{recurringConsentId}/authorise E não é método = POST com statusCode 4xx ou 5xx ENTÃO Se for o endpoint /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options consentId e o recurringConsentId estiverem simultaneamente preenchidos, retorna Invalido Se for o endpoint /open-banking/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options consentId e o recurringConsentId estiverem simultaneamente vazios ou nulos, retorna Pelo menos consentId ou recurringConsentId deve estar preenchido Se o REGEX do recurringConsentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| rejectionReasonCode | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/enrollments/v x /enrollments/{enrollmentId} E método = PATCH ou GET ENTÃO Se rejectionReasonCode for nulo, retorna Nulo Se rejectionReasonCode for vazio, retorna Vazio Se rejectionReasonCode não for REJEITADO_DISPOSITIVO_INCOMPATIVEL, REJEITADO_FALHA_FIDO, REJEITADO_FALHA_HYBRID_FLOW, REJEITADO_FALHA_INFRAESTRUTURA, REJEITADO_MANUALMENTE, REJEITADO_MAXIMO_CHALLENGES_ATINGIDO, REJEITADO_OUTRO, REJEITADO_SEGURANCA_INTERNA, REJEITADO_TEMPO_EXPIRADO_ACCOUNT_HOLDER_VALIDATION, REJEITADO_TEMPO_EXPIRADO_RISK_SIGNALS, REJEITADO_TEMPO_EXPIRADO_ENROLLMENT ou REJEITADO_TITULARIDADE_DIVERGENTE, retorna Invalido |
| revocationReasonCode | SE Role = CLIENT E status = REVOKED E endpoint = %/enrollments/v x /enrollments/{enrollmentId} E método = PATCH OU GET e statusCode = 200 ENTÃO Se revocationReasonCode for nulo, retorna Nulo Se revocationReasonCode for vazio, retorna Vazio Se revocationReasonCode não for REVOGADO_FALHA_INFRAESTRUTURA, REVOGADO_MANUALMENTE, REVOGADO_OUTRO, REVOGADO_SEGURANCA_INTERNA ou REVOGADO_VALIDADE_EXPIRADA, retorna Invalido |
| rp | SE Role = CLIENT E endpoint = %/enrollments/v x /enrollments/{enrollmentId}/fido-registration-options ou %/enrollments/v x /enrollments/{enrollmentId}/fido-sign-options E método = POST ENTÃO Se rpf or nulo, retorna Nulo Se rp for vazio, retorna Vazio |
| status | SE Role = CLIENT E endpoint = %/enrollments/v x /enrollments ou %/enrollments/v x /enrollments/{enrollmentId} E método = GET ou POST E statusCode = 2xx ENTÃO Se status for nulo, retorna Nulo Se status for vazio, retorna Vazio Se status não for AWAITING_AUTHORISATION, AUTHORISED, REJECTED, PARTIALLY_ACCEPTED, REVOKED, CONSUMED, AWAITING_RISK_SIGNALS, AWAITING_ACCOUNT_HOLDER_VALIDATION, AWAITING_ENROLLMENT, RCVD, CANC, ACCP, ACPD, RJCT, ACSC, PDNG ou SCHD, retorna Invalido |

### Pagamentos Automáticos

| Campo | Regra |
| --- | --- |
| authorisationFlowIntent | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents E método = POST, PATCH ou GET ENTÃO Se o authorisationFlowIntent for nulo, retorna Nulo Se o authorisationFlowIntent for vazio, retorna Vazio Se o authorisationFlowIntent não for CIBA_FLOW, FIDO_FLOW ou HYBRID_FLOW, retorna Invalido |
| companyProfileInfo | SE Role = CLIENT E personType = PJ ou PESSOA_JURIDICA E endpoint = %/automatic-payments/v x /recurring-consents E método = POST ENTÃO Se naturezaJuridica e porteEmpresa forem simultaneamente nulos ou vazios, retorna Nulo/Vazio Se naturezaJuridica for nulo ou vazio e porteEmpresa estiver preenchido, retorna Incompleto - sem Natureza Juridica Se naturezaJuridica estiver preenchido e porteEmpresa estiver nulo ou vazio, retorna Incompleto - sem Porta da Empresa Se o porteEmpresa não for 00, 01, 03 ou 05, retorna Invalido |
| consentId | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% ou %automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E método = GET, PATCH OU POST com statusCode diferente de 4xx ou 5xx ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| dropReason | SE Role = SERVER E endpoint = %/automatic-payments/v x /recurring-consents E método = POST ENTÃO Se o dropReason for nulo, retorna Nulo Se o dropReason for vazio, retorna Vazio Se o dropReason não for NONE, NO_CREDENTIAL, AUTHORITY ou NO_AUTHORITY_PERSON_MISMATCH, retorna Invalido |
| errorCodes | SE Role = CLIENT E statusCode = 4xx ou 5xx E endpoint = %automatic-payments/v x /recurring-payments% e endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["CANCELAMENTO_FORA_PERIODO_PERMITIDO"], ["CONSENTIMENTO_INVALIDO"], ["CONSENTIMENTO_PENDENTE_AUTORIZACAO"], ["DETALHE_PAGAMENTO_INVALIDO"], ["ERRO_IDEMPOTENCIA"], ["FORA_PRAZO_PERMITIDO"], ["LIMITE_PERIODO_QUANTIDADE_EXCEDIDO"], ["LIMITE_PERIODO_VALOR_EXCEDIDO"], ["LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO"], ["LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO"], ["NAO_INFORMADO"], ["PAGAMENTO_DIVERGENTE_CONSENTIMENTO"], ["PAGAMENTO_NAO_PERMITE_CANCELAMENTO"], ["PAGAMENTO_RECUSADO_DETENTORA"], ["PAGAMENTO_RECUSADO_SPI"], ["PARAMETRO_INVALIDO"], ["PARAMETRO_NAO_INFORMADO"], ["SALDO_INSUFICIENTE"], ["VALOR_ACIMA_LIMITE"] ou ["VALOR_INVALIDO"], retorna Invalido OU endpoint = %automatic-payments/v x /recurring-consents% Se o errorCodes for nulo, retorna Nulo Se o errorCodes for vazio, retorna Vazio Se o errorCodes possui mais de um item, retorna Multiplos itens Se statusCode = 422 e errorCodes não for ["CAMPO_NAO_PERMITIDO"], ["CONSENTIMENTO_NAO_PERMITE_CANCELAMENTO"], ["DATA_PAGAMENTO_INVALIDA"], ["DETALHE_EDICAO_INVALIDO"], ["DETALHE_PAGAMENTO_INVALIDO"], ["ERRO_IDEMPOTENCIA"], ["FALTAM_SINAIS_OBRIGATORIOS_PLATAFORMA"], ["FUNCIONALIDADE_NAO_HABILITADA"], ["NAO_INFORMADO"], ["PARAMETRO_INVALIDO"], ["PARAMETRO_NAO_INFORMADO"], ["PERMISSAO_INSUFICIENTE"], retorna Invalido Se statuscode for 4xx ou 5xx e statusCode não for 422, retorna Error_Code invalido |
| localInstrument | SE Role = CLIENT E endpoint = %/automatic-payments/v x /pix/recurring-payments% E método = POST OU PATCH, GET com statusCode diferente de 4xx e 5xx ENTÃO Se o localInstrument for nulo, retorna Nulo Se o localInstrument for vazio, retorna Vazio Se o localInstrument não for DICT, INIC, MANU, QRDN, QRES ou AUTO, retorna Invalido |
| paymentType | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% ou %/automatic-payments/v x /pix/recurring-payments% e não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E método = POST, PATCH OU endpoint = %/automatic-payments/v x /recurring-consents/{recurringConsentId}' E método = GET ENTÃO Se o paymentType for nulo, retorna Nulo Se o paymentType for vazio, retorna Vazio Se o paymentType não for AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED ou SWEEPING, retorna Invalido |
| rejectedBy | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/automatic-payments/v x /recurring-consents/{recurringConsentId} E método = PATCH ou GET E statusCode não é 4xx e 5xx ENTÃO Se o rejectedBy for nulo, retorna Nulo Se o rejectedBy for vazio, retorna Vazio Se o rejectedBy não for DETENTORA, INICIADORA, USUARIO, retorna Invalido |
| rejectedFrom | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/automatic-payments/v x /recurring-consents/{recurringConsentId} E método = PATCH ou GET E statusCode não é 4xx e 5xx ENTÃO Se o rejectedFrom for nulo, retorna Nulo Se o rejectedFrom for vazio, retorna Vazio Se o rejectedFrom não for DETENTORA, INICIADORA, retorna Invalido |
| rejectionReasonCode | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/automatic-payments/v x /recurring-consents/{recurringConsentId} E método = GET ou PATCH E statusCode não é 4xx ou 5xx ENTÃO Se rejectionReasonCode for nulo, retorna Nulo Se rejectionReasonCode for vazio, retorna Vazio Se rejectionReasonCode não for AUTENTICACAO_DIVERGENTE, CONTA_NAO_PERMITE_PAGAMENTO, CONTAS_ORIGEM_DESTINO_IGUAIS, FALHA_INFRAESTRUTURA, FLUXO_NAO_SUPORTADO_PRODUTO, NAO_INFORMADO, REJEITADO_USUARIO, SALDO_INSUFICIENTE, TEMPO_EXPIRADO_AUTORIZACAO, VALOR_ACIMA_LIMITE ou VALOR_INVALIDO, retorna Invalido |
| rejectionReasonDetail | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/automatic-payments/v x /recurring-consents/{recurringConsentId} E método = GET ou PATCH E statusCode não é 4xx e 5xx ENTÃO Se rejectionReasonDetail for nulo, retorna Nulo Se rejectionReasonDetail for vazio, retorna Vazio |

### Específicos PIX Automático

| Campo | Regra |
| --- | --- |
| amountType | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% E versão = v2 E método = POST OU PATCH ou GET com statusCode diferente de 4xx ou 5xx E paymentType = AUTOMATIC ENTÃO Se o amountType for nulo, retorna Nulo Se o amountType for vazio, retorna Vazio Se o amountType não for FIXO ou VARIAVEL, retorna Invalido |
| authorisationFlow | SE Role = CLIENT E endpoint = %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST, PATCH ou GET ENTÃO Se o authorisationFlow for nulo, retorna Nulo Se o authorisationFlow for vazio, retorna Vazio Se o authorisationFlow não for CIBA_FLOW, FIDO_FLOW ou HYBRID_FLOW, retorna Invalido |
| cancellationReason | SE Role = CLIENT E status = CANC E endpoint = %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST, PATCH ou GET E statusCode = 2xx ENTÃO Se o cancellationReason for nulo, retorna Nulo Se o cancellationReason for vazio, retorna Vazio Se o cancellationReason não for CANCELADO_AGENDAMENTO ou CANCELADO_PENDENCIA, retorna Invalido |
| cancelledFrom | SE Role = CLIENT E status = CANC E endpoint = %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST, GET ou PATCH E statusCode = 2xx ENTÃO Se o cancelledFrom for nulo, retorna Nulo Se o cancelledFrom for vazio, retorna Vazio Se o cancelledFrom não for INICIADORA ou DETENTORA, retorna Invalido |
| hasMinimumAmount | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% E versão = v2 E método = POST OU método = GET ou PATCH e statusCode diferente de 4xx e 5xx E paymentType = AUTOMATIC ENTÃO Se o hasMinimumAmount for nulo, retorna Nulo Se o hasMinimumAmount for vazio, retorna Vazio Se o hasMinimumAmount não for TRUE ou FALSE, retorna Invalido |
| interval | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% E versão = v2 E método = POST OU método = GET ou PATCH e statusCode diferente de 4xx e 5xx E paymentType = AUTOMATIC ENTÃO Se interval for nulo, retorna Nulo Se interval for vazio, retorna Vazio |
| isFirstPayment | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% E versão = v2 E método = POST OU método = GET ou PATCH e statusCode diferente de 4xx e 5xx E paymentType = AUTOMATIC ENTÃO Se isFirstPayment for nulo, retorna Nulo Se isFirstPayment for vazio, retorna Vazio Se isFirstPayment não for TRUE ou FALSE, retorna Invalido |
| isRetryAccepted | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% E versão = v2 E método = POST OU GET ou PATCH e statusCode diferente de 4xx e 5xx E paymentType = AUTOMATIC ENTÃO Se isRetryAccepted for nulo, retorna Nulo Se isRetryAccepted for vazio, retorna Vazio |
| paymentReference | SE Role = CLIENT E endpoint = %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST e PATCH OU GET e statusCode diferente de 4xx e 5xx E paymentType = AUTOMATIC ENTÃO Se paymentReference for nulo, retorna Nulo Se paymentReference for vazio, retorna Vazio |
| paymentType | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% ou %/automatic-payments/v x /pix/recurring-payments% e não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST OU GET ou PATCH e statusCode diferente de 4xx e 5xx ENTÃO Se o paymentType for nulo, retorna Nulo Se o paymentType for vazio, retorna Vazio Se o paymentType não for AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED ou SWEEPING, retorna Invalido |
| personType | SE Role = CLIENT E endpoint = %/automatic-payments/v x /recurring-consents% E versão = v2 E método = POST, PATCH ou GET E statusCode = 2xx ENTÃO Se personType for nulo, retorna Nulo Se personType for vazio, retorna Vazio Se personType não for PF, PJ, PESSOA_JURIDICA, PESSOA_NATURAL, retorna Invalido |
| recurringPaymentId | SE Role = CLIENT E endpoint = %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST, GET e PATCH E statusCode não é 4xx e 5xx ENTÃO Se recurringPaymentId for nulo, retorna Nulo Se recurringPaymentId for vazio, retorna Vazio |
| rejectionReasonCode | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/automatic-payments/v x /recurring-consents% ou %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST ou GET OU PATCH e statusCode diferente de 4xx e 5xx ENTÃO Se rejectionReasonCode for nulo, retorna Nulo Se rejectionReasonCode for vazio, retorna Vazio Se rejectionReasonCode não for AUTENTICACAO_DIVERGENTE, CONSENTIMENTO_INVALIDO, CONTA_NAO_PERMITE_PAGAMENTO, CONTAS_ORIGEM_DESTINO_IGUAIS, DETALHE_PAGAMENTO_INVALIDO, DETALHE_TENTATIVA_INVALIDO, FALHA_INFRAESTRUTURA, FALHA_INFRAESTRUTURA_DETENTORA, FALHA_INFRAESTRUTURA_ICP, FALHA_INFRAESTRUTURA_PSP_RECEBEDOR, FALHA_INFRAESTRUTURA_SPI, FORA_PRAZO_PERMITIDO, LIMITE_PERIODO_QUANTIDADE_EXCEDIDO, LIMITE_PERIODO_VALOR_EXCEDIDO, LIMITE_TENTATIVAS_EXCEDIDO, LIMITE_VALOR_TOTAL_CONSENTIMENTO_EXCEDIDO, LIMITE_VALOR_TRANSACAO_CONSENTIMENTO_EXCEDIDO, NAO_INFORMADO, PAGAMENTO_DIVERGENTE_CONSENTIMENTO, PAGAMENTO_RECUSADO_DETENTORA, PAGAMENTO_RECUSADO_SPI, REJEITADO_USUARIO, SALDO_INSUFICIENTE, TEMPO_EXPIRADO_AUTORIZACAO, TITULARIDADE_INCONSISTENTE, VALOR_ACIMA_LIMITE, VALOR_INVALIDO, retorna Invalido |
| rejectionReasonDetail | SE Role = CLIENT E status = RJCT ou REJECTED E endpoint = %/automatic-payments/v x /recurring-consents/% E versão = v2 E método = POST ou GET OU PATCH com statusCode diferente de 4xx e 5xx ENTÃO Se rejectionReasonDetail for nulo, retorna Nulo Se rejectionReasonDetail for vazio, retorna Vazio |
| revocationReasonCode | SE Role = CLIENT E status = REVOKED E endpoint = %/automatic-payments/v x /recurring-consents% ou %/automatic-payments/v x /pix/recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST ou GET OU PATCH com statusCode diferente de 4xx e 5xx ENTÃO Se revocationReasonCode for nulo, retorna Nulo Se revocationReasonCode for vazio, retorna Vazio Se revocationReasonCode não for NAO_INFORMADO, REVOGADO_RECEBEDOR ou REVOGADO_USUARIO, retorna Invalido |
| revocationReasonDetail | SE Role = CLIENT E status = REVOKED E endpoint = %/automatic-payments/v x /recurring-consents% ou %/automatic-payments/v x /recurring-payments% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E versão = v2 E método = POST ou GET OU PATCH e statusCode diferente de 4xx e 5xx ENTÃO Se revocationReasonDetail for nulo, retorna Nulo Se revocationReasonDetail for vazio, retorna Vazio |
| status | SE Role = CLIENT E endpoint = %/automatic-payments/v x /pix/recurring-payments% ou %/automatic-payments/v x /recurring-consents% E endpoint não for %/automatic-payments/v x /pix/recurring-payments/{originalRecurringPaymentId}/retry E método = GET, PATCH ou POST E statusCode = 2xx ENTÃO Se status for nulo, retorna Nulo Se status for vazio, retorna Vazio Se status não for AWAITING_AUTHORISATION, AUTHORISED, REJECTED, PARTIALLY_ACCEPTED, REVOKED, CONSUMED, AWAITING_RISK_SIGNALS, AWAITING_ACCOUNT_HOLDER_VALIDATION, AWAITING_ENROLLMENT, RCVD, CANC, ACCP, ACPD, RJCT, ACSC, PDNG ou SCHD, retorna Invalido |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Pagamentos > Dados relativos aos Estados de Pagamento - SV > API Estados de Pagamento - SV

---
id: 1211858945
title: API Estados de Pagamento - SV
version: 5
modified: 2025-12-10T16:59:11.170Z
url: /spaces/OF/pages/1211858945/API+Estados+de+Pagamento+-+SV
---

v 1.02Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Payment Status API

| Campo | Definição | Obrigatório | Tipo | Regra de preenchimento | Roles | Métodos | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| clientOrgId | Identificador da organização de onde a chamada foi disparada. | Sim | string <uuid> | | SERVER | POST GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| consentId | Identificador único do consentimento criado para aquele pagamento. | Sim | string | | SERVER | POST GET | | 100 | | | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,-.:=@;$_!*''%/?#]+ | uGQHwNupARo7I9E2PLJZph18a0M9y7DcUe7ITt3DqUOJd9NVjnskxf2 |
| createdAt | Carimbo do tempo do momento da criação do registro | Não | string <date-time> | | SERVER | GET | | 28 | | | | |
| eventDateTime | Data e hora associados à mudança de estados finais reportados, como liquidação, rejeição ou cancelamento. Deve ser informado em UTC-0. | Sim | string <date-time> | | SERVER | POST GET | | 28 | | | | 2025-08-18T00:00:00Z |
| paymentId | Código único para identificar a transação de pagamento | Sim | string | | SERVER | POST GET | | | | | ^[a-zA-Z0-9][a-zA-Z0-9\-]{0,99}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| paymentStatus | Status de agendamento ou final do pagamento | Sim | enum<string> | | SERVER | POST GET | ACSC, RJCT, CANC, SCHD | | | | | ACSC |
| paymentType | Tipo de pagamento realizado | Sim | enum<string> | | SERVER | POST GET | AUTOMATIC, IMMEDIATE, RECURRENT, SCHEDULED, SWEEPING | | | | | RECURRENT |
| reportId | Identificador único do registro criado na Plataforma de Coleta de Métricas. | Não | string | | SERVER | GET | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | |
| status | Informa o status do registro de reporte. | Não | enum<string> | | SERVER | GET | ACCEPTED, DISCARDED | | | | | |
| statusReasonCode | Razão do status informado. | Sim | string | Campo atrelado ao status de pagamento. Quando o status for RJCT (Rejected), o valor deve ser preenchido com o motivo da rejeição (valores previstos em rejectionReason.Code). Quando o status for CANC (Cancelled), o valor deve ser preenchido com o motivo do cancelamento (valores previstos em cancellationReason.Code). | SERVER | POST GET | | | | | | |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Portabilidade de Crédito > Campos Obrigatórios e Opcionais - PC

---
id: 1212055553
title: Campos Obrigatórios e Opcionais - PC
version: 24
modified: 2026-01-23T20:57:15.275Z
url: /spaces/OF/pages/1212055553/Campos+Obrigat+rios+e+Opcionais+-+PC
---

v 1.05
# Credit Portability API
**[POST] /report-api/v1/credit-portabilities/client****[POST] /report-api/v1/credit-portabilities/server**
| Campo | Definição | Regra de preenchimento | Obrigatório | Tipo | Roles | Http code | Métodos | Domínio | Endpoints | Versões | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| clientOrgId | Identificador da organização de onde a chamada foi disparada. | | Sim | string <uuid> | CLIENT SERVER | Todos | Todos | | Todos | v1 | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| clientSSId | Identificador do software statement de onde a chamada foi disparada. A PCM garante que foi esta orgId que obteve o token de acesso utilizado neste reporte. | | Sim | string <uuid> | CLIENT | Todos | Todos | | Todos | v1 | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 84570da9-567b-4201-9b77-c715bc5bffde |
| consentId | Código identificador do consentimento de dados utilizado pela instituição proponente para acessar as informações do contrato de crédito do cliente na credora | | Sim | string <uuid> | CLIENT SERVER | Todos exceto 4xx e 5xx | POST | | /open-banking/credit-portability/v1/portabilities | v1 | 100 | | | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%\/?#]+$ | urn:bancoex:C1DD33123 |
| correlationId | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. | | Não | string | CLIENT SERVER | Todos | Todos | | Todos | v1 | 100 | | | ^[- /:_.',0-9a-zA-Z]{0,100}$ | uGQHwNupARo7I9E2PLJZph18a0M9y7DcUe7ITt3DqUOJd9NVjnskxf2 |
| creationDateTime | Data e hora em que a Proponente registrou a presente proposta (chamada ao POST /portabilities). Uma string com data e hora conforme especificação ISO8601, sempre com a utilização de timezone UTC-0 (UTC time format). | Preencher com o valor do campo "/data/creationDateTime" no response do POST | Sim | string | CLIENT | Todos exceto 4xx e 5xx | POST | | /open-banking/credit-portability/v x /portabilities | v1 | 20 | | | ^\d{4}-\d{2}-\d{2}T(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d(?:\.\d+)?(?:Z|[+-][01]\d:[0-5]\d)$ | 2020-07-21T08:30:00Z |
| creditPortabilityStatus | Informação sobre o status de um pedido de portabilidade de crédito | Preencher com o valor do campo "/data/status" RECEIVED : Estado inicial. Indica que o pedido de portabilidade foi solicitado junto à instituição credora. O pedido deve permanecer neste estado até o próximo dia útil (D+1) onde começará a contar o prazo de 3 dias úteis para a etapa de contraproposta e o pedido de portabilidade deverá ser movido para PENDING PENDING : Indica que o pedido de portabilidade de crédito está na fase de contraproposta, onde a instituição credora poderá enviar uma contraproposta ou não para o cliente por qualquer canal (email, telefone, etc.) porém o aceite só deverá ser valido se o cliente aprovar no canal digital da instituição credora ACCEPTED_SETTLEMENT_IN_PROGRESS : Indica que a contraproposta não foi aceita pelo cliente e a instituição proponente terá que quitar o valor do contrato no mesmo dia em que o estado foi ativado. ACCEPTED_SETTLEMENT_COMPLETED : Indica que a instituição proponente já liquidou o contrato e comunicou a respeito à credora que está validando os dados do contrato bem como valores recebidos para a quitação do mesmo (nesta etapa a instituição credora tem 2 dias úteis para fornecer a confirmação e o recibo de quitação do contrato de empréstimo) PORTABILITY_COMPLETED : Indica que o pedido de portabilidade foi concluído com sucesso REJECTED : Indica que o pedido de portabilidade de crédito foi rejeitado, seja porque o cliente aceitou a contraproposta, ou porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades CANCELLED : Indica que o cliente cancelou o pedido de portabilidade de crédito PAYMENT_ISSUE : Indica que a Instituição Credora encontrou alguma inconsistência na liquidação efetuada e que a Instituição Proponente deverá realizar ajustes conforme sugerido pela Instituição Credora para solucionar a pendência antes do cancelamento do pedido de portabilidade de crédito | Sim | string | CLIENT SERVER | Todos exceto 4xx e 5xx | GET | ACCEPTED_SETTLEMENT_COMPLETED, ACCEPTED_SETTLEMENT_IN_PROGRESS, CANCELLED, PENDING, PAYMENT_ISSUE, PORTABILITY_COMPLETED, RECEIVED, REJECTED | /open-banking/credit-portability/v x /portabilities/{portabilityId} | v1 | | | | | |
| endpoint | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar presente na lista de endpoints aceitos pela PCM para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original. | Identificação do Endpoint: Deve ser preenchido com o identificador padronizado do endpoint, conforme uma lista (ENUM) predefinida. Não usar o caminho real: É fundamental NÃO utilizar o caminho completo da requisição original, que inclui dados variáveis (ex: IDs). Exemplo: Se a requisição foi para /open-banking/credit-cards-accounts/v1/accounts/123456789/transactions, o valor a ser enviado no endpoint deve ser /open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions. O dado real 123456789 não deve ser enviado no campo endpoint. | Sim | string | CLIENT SERVER | Todos | Todos | Endpoints aceitos pela PCM | Todos | v1 | | | | | /open-banking/consents/v2/consents |
| endpointUriPrefix | Endereço do servidor de destino da chamada, incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: https://{host}/{prefixo}, sendo: host: endereço FQDN do servidor de destino prefixo: toda a parte do path que vem antes da string /open-banking | | Sim | string | CLIENT | Todos | Todos | | Todos | v1 | 200 | | | ^[- /:_.',0-9a-zA-Z]{0,200}$ | https://openbanking.instituicao-1.com.br/opbk |
| errorCode | Registra os códigos de erro detalhados de uma requisição que resultou em um erro HTTP (série 4xx ou 5xx). | Caso o HTTP Code seja 4XX ou 5XX, esse campo deve ser preenchido com a lista das strings obtidas em ".errors[].code", devendo constar apenas um código de erro. | Não | string | CLIENT | 4xx e 5xx | POST GET PATCH | | /open-banking/credit-portability/v x /portabilities /open-banking/credit-portability/v x /portabilities/{portabilityId} /open-banking/credit-portability/v x /portabilities/{portabilityId}/account-data /open-banking/credit-portability/v x /portabilities/{portabilityId}/cancel /open-banking/credit-portability/v x /portabilities/{portabilityId}/payment | v1 | | | | | |
| fapiInteractionId | UUID RFC4122 que identifica uma transação específica entre dois participantes no ecossistema Open Finance. Este identificador é derivado do header HTTP x-fapi-interaction-id, conforme especificação RFC4122 para geração de identificadores únicos universais. Serve como chave de correlação fundamental para rastreabilidade, auditoria e conciliação de transações entre instituições participantes. Mais informações em Cabeçalhos HTTP na documentação de produtos do Open Finance Brasil | Para CLIENT: OBRIGATÓRIO em todos os cenários onde o x-fapi-interaction-id foi gerado, incluindo respostas com status 4xx (incluindo 408 - timeout), respostas com status 5xx recebidas e transações completadas com sucesso. Para SERVER: OBRIGATÓRIO quando o x-fapi-interaction-id foi recebido na requisição ou quando o Server gerou o x-fapi-interaction-id conforme especificação da API de Produto. Falhas de aplicação, validação, autorização, timeout, indisponibilidade de dependências ou erros internos (5xx) NÃO caracterizam, por si só, falha crítica para fins de ausência do x-fapi-interaction-id, desde que a requisição tenha sido recebida pelo Server. Nota: A ausência do fapiInteractionId compromete significativamente a capacidade de correlação e auditoria das transações no ecossistema Open Finance | Sim | string <uuid> | CLIENT SERVER | Todos | POST GET PATCH | | /open-banking/credit-portability/v x /portabilities /open-banking/credit-portability/v x /portabilities/{portabilityId} /open-banking/credit-portability/v x /portabilities/{portabilityId}/account-data /open-banking/credit-portability/v x /portabilities/{portabilityId}/cancel /open-banking/credit-portability/v x /portabilities/{portabilityId}/payment | v1 | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | d78fc4e5-37ca-4da3-adf2-9b082bf92280 |
| httpMethod | Método HTTP da solicitação. | | Sim | enum<string> | CLIENT SERVER | Todos | Todos | DELETE, GET, PATCH, POST, PUT | Todos | v1 | | | | | GET |
| portabilityId | Código identificador do pedido de portabilidade realizado. | O envio dessa informação é obrigatório, exceto nos casos onde ela não esteja disponível como, por exemplo, em respostas com status 5xx, ou em chamadas que terminaram por timeout onde o reporte tem que ser enviado, mas sem esse atributo. Nos demais cenários, o envio é obrigatório. Preencher com o valor do campo "/data/portabilityId"​no response do POST | Sim | string <uuid> | CLIENT SERVER | Todos exceto 4xx e 5xx | POST GET PATCH | | /open-banking/credit-portability/v x /portabilities /open-banking/credit-portability/v x /portabilities/{portabilityId} /open-banking/credit-portability/v x /portabilities/{portabilityId}/account-data /open-banking/credit-portability/v x /portabilities/{portabilityId}/cancel /open-banking/credit-portability/v x /portabilities/{portabilityId}/payment | v1 | 100 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 54d5348c-1a3f-4ff4-a8a8-d0724fb806c6 |
| processTimespan | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. | | Não | integer | CLIENT SERVER | Todos | Todos | | Todos | v1 | | | | | 120 |
| rejectedBy | Usuário responsável pela rejeição da proposta | Quando a origem da informação for a CREDORA, preencher com o valor do campo "/data/rejection/rejectedBy" Quando a origem da informação for o PROPONENTE, preencher com o valor enviado no campo "/data/rejectedBy" PROPONENTE - Indica que o pedido de portabilidade de crédito foi rejeitado pela proponente, seja porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades. USUARIO - Indica que o cliente cancelou o pedido de portabilidade de crédito. CREDORA - Indica que a Instituição Credora cancelou o contrato por retenção do cliente ou outros motivos conforme motivo de recusa. | Não | string | CLIENT SERVER | Todos exceto 4xx e 5xx | GET PATCH | CREDORA, PROPONENTE, USUARIO | /open-banking/credit-portability/v x /portabilities/{portabilityId} /open-banking/credit-portability/v x /portabilities/{portabilityId}/cancel | | | | | | |
| rejectionReason | Motivo de recusa do pedido de portabilidade | Motivo de recusa do pedido de portabilidade. Só será preenchido caso o status seja REJECTED, CANCELLED ou PAYMENT_ISSUE A consulta ao endpoint de GET é requerida para o fluxo de portabilidade: Quando a origem da informação for a CREDORA, preencher com o valor do campo "/data/statusReason/reasonType” Quando a origem da informação for o PROPONENTE, preencher com o valor enviado no campo "/data/reason/type" | Não | string | CLIENT SERVER | Todos exceto 4xx e 5xx | GET PATCH | Se o status for REJECTED Se rejectedBy for PROPONENTE OUTROS, POLITICA_DE_CREDITO, SALDO_DEVEDOR_ATUALIZADO_SUBSTANCIALMENTE_DIVERGENTE Se rejectedBy for CREDORA CLIENTE_COM_ACAO_JUDICIAL, CONTRATO_JA_LIQUIDADO, DECURSO_DO_PRAZO_PARA_PAGAMENTO, MODALIDADE_DA_OPERACAO_INCOMPATIVEL, PORTABILIDADE_CANCELADA_POR_FALTA_DE_LIQUIDACAO, PORTABILIDADE_EM_ANDAMENTO, RETENCAO_DO_CLIENTE Se o status for CANCELLED Se rejectedBy for USUARIO CANCELADO_PELO_CLIENTE Se o status for PAYMENT_ISSUE Se rejectedBy for CREDORA DIVERGENCIA_DE_PAGAMENTO_EFETUADO, OUTROS | /open-banking/credit-portability/v x /portabilities/{portabilityId} /open-banking/credit-portability/v x /portabilities/{portabilityId}/cancel | v1 | | | | | CANCELADO_PELO_CLIENTE |
| serverOrgId | Identificador da organização para onde a chamada foi feita. | | Sim | string <uuid> | CLIENT SERVER | Todos | Todos | | Todos | v1 | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | c1ca8e62-9d6f-4ea3-84f2-d66bc0a8f7dc |
| statusCode | Status de retorno HTTP da solicitação. | No caso de ocorrer um timeout client side preencher com um código 403. | Sim | integer <int32> | CLIENT SERVER | Todos | Todos | | Todos | v1 | | 200 | 599 | | 200 |
| statusUpdateDateTime | Data e hora em que o contrato teve o status atualizado. Uma string com data e hora conforme especificação ISO-8601, sempre com a utilização de timezone UTC(UTC time format). | Preencher com o valor do campo "/data/statusUpdateDateTime" | Sim | string | CLIENT SERVER | Todos exceto 4xx e 5xx | GET | | /open-banking/credit-portability/v x /portabilities/{portabilityId} | v1 | 20 | | | ^\d{4}-\d{2}-\d{2}T(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d(?:\.\d+)?(?:Z|[+-][01]\d:[0-5]\d)$ | 2020-07-21T08:30:00Z |
| timestamp | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. | | Sim | string <date-time> | CLIENT SERVER | Todos | Todos | | Todos | v1 | 28 | | | ^\d{4}-\d{2}-\d{2}T(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d(?:\.\d+)?(?:Z|[+-][01]\d:[0-5]\d)$ | 2021-11-11T18:08:08.278Z |
**[GET] /report-api/v1/credit-portabilities/{fapiInteractionId}**
| Campo | Definição | Obrigatório | Tipo | Domínio | Tamanho máximo | Valor mínimo | Valor máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| createdAt | Carimbo do tempo do momento da criação do registro. Esta é a data da criação do reporte na PCM. | Não | string <date-time> | | 28 | | | ^\d{4}-\d{2}-\d{2}T(?:[01]\d|2[0-3]):[0-5]\d:[0-5]\d(?:\.\d+)?(?:Z|[+-][01]\d:[0-5]\d)$ | 2020-07-21T08:30:00Z |
| creditPortabilityStatus | Informação sobre o status de um pedido de portabilidade de crédito | Não | string | ACCEPTED_SETTLEMENT_COMPLETED, ACCEPTED_SETTLEMENT_IN_PROGRESS, CANCELLED, PENDING, PAYMENT_ISSUE, PORTABILITY_COMPLETED, RECEIVED, REJECTED | | | | | |
| pairedReportId | Esse atributo indica o reportId do registro que forma uma correlação com o presente registro. Se essa informação existir, o status do registro atual deverá ser PAIRED | Não | string <uuid> | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | 9a97c2df-b261-4fc2-aa66-d1b5168397da |
| reportId | Identificador único do registro criado na Plataforma de Coleta de Métricas. | Não | string <uuid> | | 36 | | | ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$ | |
| status | Informa o status do registro de reporte. | Não | string | ACCEPTED, DISCARDED, PAIRED, PAIRED_INCONSITENT, SINGLE, UNPAIRED | | | | | PAIRED |
| updatedAt | Carimbo do tempo do momento da última atualização do registro. Esta é a data da atualização do reporte na PCM. | Não | string <date-time> | | 28 | | | | |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Portabilidade de Crédito > Funcionalidade e Campos - PC

---
id: 1212088321
title: Funcionalidade e Campos - PC
version: 1
modified: 2025-11-18T13:22:21.914Z
url: /spaces/OF/pages/1212088321/Funcionalidade+e+Campos+-+PC
---

v 1.01
## Objetivo
Disponibilização de uma nova API dedicada à obtenção de dados referentes às solicitações da portabilidade por parte dos clientes das instituições financeiras. Esta solução permite que as instituições forneçam dados à PCM de forma completa e transparente sobre o fluxo de solicitações de Portabilidade de Crédito ao ecossistema do Open Finance Brasil.  Esta é uma documentação funcional. Para a documentação técnica, acesso o link: Documentação da API - PCM   
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.    **Portabilidade de Crédito** A Portabilidade de Crédito permite que usuários transfiram suas operações de crédito e arrendamento mercantil entre instituições financeiras em busca de melhores condições. Atualmente, a solicitação de portabilidade pode ser feita via registradora. A implementação da solicitação de portabilidade, alinhada à agenda do Open Finance Brasil (OFB), visa agilizar e simplificar o processo.    **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.    
## Descrição funcional das APIs
**API de inclusão de reportes de portabilidade - SERVER**
| Campo | Descrição |
| xfapi¹ | UUID que identifica uma transação específica entre dois participantes. Esse dado pode ser encontrado no header x-fapi-interaction-id informado pelo Client e devolvido pelo Server. Mais informações em Cabeçalhos HTTP na documentação do Open Finance Brasil. O envio dessa informação é obrigatório, exceto nos casos ontem ela não esteja disponível como, por exemplo, em respostas com status 5xx, ou em chamadas que terminaram por timeout onde o reporte tem que ser enviado, mas sem esse atributo. Nos demais cenários, o envio é obrigatório. |
| Id da Portabilidade¹ | Código identificador do pedido de portabilidade realizado. |
| endpoint¹ | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. |
| statusCode¹ | Status de retorno HTTP da solicitação. |
| Método¹ | Método HTTP da solicitação.  [ GET, POST, PUT, DELETE, PATCH ] |
| Id de Correlação | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. |
| timestamp¹ | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| Intervalo de tempo do processo | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| Id da organização atuando como CLIENT¹ | Identificador da organização de onde a chamada foi disparada. |
| Id da organização atuando como SERVER¹ | Identificador da organização para onde a chamada foi feita. |
| Data e hora da atualização do status | Data e hora em que o contrato teve o status atualizado. Uma string com data e hora conforme especificação ISO-8601, sempre com a utilização de timezone UTC(UTC time format). |
| Motivo da recusa | Motivo de recusa do pedido de portabilidade.  Só será preenchido caso o status seja REJECTED, CANCELLED ou PAYMENT_ISSUE ` ` A consulta ao endpoint de GET é requerida para o fluxo de portabilidade |
| Rejeitado por | Informar usuário responsável pela rejeição da proposta, onde: PROPONENTE - Indica que o pedido de portabilidade de crédito foi rejeitado pela proponente, seja porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades. USUARIO - Indica que o cliente cancelou o pedido de portabilidade de crédito. CREDORA- Indica que a Instituição Credora cancelou o contrato por retenção do cliente ou outros motivos conforme motivo de recusa.  Só será preenchido caso o status seja REJECTED ou CANCELLED  [ PROPONENTE, USUARIO, CREDORA ] |
| Papel¹ | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client.  [ CLIENT, SERVER ] |
| Status da portabilidade | Informação sobre o status de um pedido de portabilidade de crédito, onde:  RECEIVED: Estado inicial. Indica que o pedido de portabilidade foi solicitado junto à instituição credora. O pedido deve permanecer neste estado até o próximo dia útil (D+1) onde começará a contar o prazo de 3 dias úteis para a etapa de contraproposta e o pedido de portabilidade deverá ser movido para PENDING  PENDING: Indica que o pedido de portabilidade de crédito está na fase de contraproposta, onde a instituição credora poderá enviar uma contraproposta ou não para o cliente por qualquer canal (email, telefone, etc.) porém o aceite só deverá ser valido se o cliente aprovar no canal digital da instituição credora  ACCEPTED_SETTLEMENT_IN_PROGRESS: Indica que a contraproposta não foi aceita pelo cliente e a instituição proponente terá que quitar o valor do contrato no mesmo dia em que o estado foi ativado.  ACCEPTED_SETTLEMENT_COMPLETED: Indica que a instituição proponente já liquidou o contrato e comunicou a respeito à credora que está validando os dados do contrato bem como valores recebidos para a quitação do mesmo (nesta etapa a instituição credora tem 2 dias úteis para fornecer a confirmação e o recibo de quitação do contrato de empréstimo)  PORTABILITY_COMPLETED: Indica que o pedido de portabilidade foi concluído com sucesso REJECTED: Indica que o pedido de portabilidade de crédito foi rejeitado, seja porque o cliente aceitou a contraproposta, ou porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades  REJECTED: Indica que o pedido de portabilidade de crédito foi rejeitado, seja porque o cliente aceitou a contraproposta, ou porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades CANCELLED: Indica que o cliente cancelou o pedido de portabilidade de crédito  PAYMENT_ISSUE: Indica que a Instituição Credora encontrou alguma inconsistência na liquidação efetuada e que a Instituição Proponente deverá realizar ajustes conforme sugerido pela Instituição Credora para solucionar a pendência antes do cancelamento do pedido de portabilidade de crédito |
¹ Campos com preenchimento obrigatório para que a mensagem seja considerada válida na ingestão  **API de inclusão de reportes de portabilidade - CLIENT**
| Campo | Descrição |
| --- | --- |
| timestamp¹ | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| Id da Portabilidade¹ | Código identificador do pedido de portabilidade realizado. |
| Id do contrato¹ | Identifica de forma única o contrato da operação de crédito do cliente, mantendo as regras de imutabilidade dentro da instituição transmissora. |
| Data/hora da criação¹ | Data e hora em que a Proponente registrou a presente proposta (chamada ao POST /portabilities). Uma string com data e hora conforme especificação ISO8601, sempre com a utilização de timezone UTC-0 (UTC time format). |
| Prazo do contrato original¹ | Prazo restante do contrato original de empréstimo. |
| Prazo da proposta¹ | Prazo da proposta de portabilidade de crédito |
| Status da portabilidade¹ | Informação sobre o status de um pedido de portabilidade de crédito, onde:  RECEIVED: Estado inicial. Indica que o pedido de portabilidade foi solicitado junto à instituição credora. O pedido deve permanecer neste estado até o próximo dia útil (D+1) onde começará a contar o prazo de 3 dias úteis para a etapa de contraproposta e o pedido de portabilidade deverá ser movido para PENDING  PENDING: Indica que o pedido de portabilidade de crédito está na fase de contraproposta, onde a instituição credora poderá enviar uma contraproposta ou não para o cliente por qualquer canal (email, telefone, etc.) porém o aceite só deverá ser valido se o cliente aprovar no canal digital da instituição credora  ACCEPTED_SETTLEMENT_IN_PROGRESS: Indica que a contraproposta não foi aceita pelo cliente e a instituição proponente terá que quitar o valor do contrato no mesmo dia em que o estado foi ativado.  ACCEPTED_SETTLEMENT_COMPLETED: Indica que a instituição proponente já liquidou o contrato e comunicou a respeito à credora que está validando os dados do contrato bem como valores recebidos para a quitação do mesmo (nesta etapa a instituição credora tem 2 dias úteis para fornecer a confirmação e o recibo de quitação do contrato de empréstimo)  PORTABILITY_COMPLETED: Indica que o pedido de portabilidade foi concluído com sucesso REJECTED: Indica que o pedido de portabilidade de crédito foi rejeitado, seja porque o cliente aceitou a contraproposta, ou porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades  CANCELLED: Indica que o cliente cancelou o pedido de portabilidade de crédito  PAYMENT_ISSUE: Indica que a Instituição Credora encontrou alguma inconsistência na liquidação efetuada e que a Instituição Proponente deverá realizar ajustes conforme sugerido pela Instituição Credora para solucionar a pendência antes do cancelamento do pedido de portabilidade de crédito |
| Data e hora da atualização do status | Data e hora em que o contrato teve o status atualizado. Uma string com data e hora conforme especificação ISO-8601, sempre com a utilização de timezone UTC(UTC time format). |
| Motivo da recusa | Motivo de recusa do pedido de portabilidade.  Só será preenchido caso o status seja REJECTED, CANCELLED ou PAYMENT_ISSUE A consulta ao endpoint de GET é requerida para o fluxo de portabilidade |
| Rejeitado por | Informar usuário responsável pela rejeição da proposta, onde: PROPONENTE - Indica que o pedido de portabilidade de crédito foi rejeitado pela proponente, seja porque a proponente rejeitou a liquidação que excedeu em 15% o valor do contrato original, entre outras possibilidades. USUARIO - Indica que o cliente cancelou o pedido de portabilidade de crédito. CREDORA- Indica que a Instituição Credora cancelou o contrato por retenção do cliente ou outros motivos conforme motivo de recusa.  Só será preenchido caso o status seja REJECTED ou CANCELLED  [ PROPONENTE, USUARIO, CREDORA ] |
| xfapi¹ | UUID que identifica uma transação específica entre dois participantes. Esse dado pode ser encontrado no header x-fapi-interaction-id informado pelo Client e devolvido pelo Server. Mais informações em Cabeçalhos HTTP na documentação do Open Finance Brasil. O envio dessa informação é obrigatório, exceto nos casos ontem ela não esteja disponível como, por exemplo, em respostas com status 5xx, ou em chamadas que terminaram por timeout onde o reporte tem que ser enviado, mas sem esse atributo. Nos demais cenários, o envio é obrigatório. |
| endpoint¹ | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. |
| endpointUriPrefix¹ | Endereço do servidor de destino da chamada, incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: https://{host}/{prefixo }, sendo:  host: endereço FQDN do servidor de destino  prefixo: toda a parte do path que vem antes da string /open-banking |
| Método¹ | Método HTTP da solicitação.  [ GET, POST, PUT, DELETE, PATCH ] |
| Id de Correlação | ID de correlação que identifica uma sequência de chamadas inter-relacionadas no ecossistema. Diferente do fapiInteractionId que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. Este valor é de livre provimento pelo reportador. |
| statusCode¹ | Status de retorno HTTP da solicitação. No caso de ocorrer um timeout client side preencher com um código 403 (conforme documentação ). |
| Intervalo de tempo do processo | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| Id da organização atuando como CLIENT¹ | Identificador da organização de onde a chamada foi disparada. |
| Id da organização atuando como SERVER¹ | Identificador da organização para onde a chamada foi feita. |
| clientSSId¹ | Identificador do software statement de onde a chamada foi disparada. A PCM garante que foi esta orgId que obteve o token de acesso utilizado neste reporte. |
| Papel¹ | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client.  [ CLIENT, SERVER ] |
¹ Campos com preenchimento obrigatório para que a mensagem seja considerada válida na ingestão  
## Documentação da API
Documentação da API - PCM

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Portabilidade de Crédito > Regras de Descarte - PC

---
id: 1213136897
title: Regras de Descarte - PC
version: 1
modified: 2025-11-18T13:04:23.010Z
url: /spaces/OF/pages/1213136897/Regras+de+Descarte+-+PC
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.
# Credit Portability API

| Campo | Regra |
| --- | --- |
| clientOrgId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| clientSSId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID para ser considerado válido |
| creationDateTime | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato datetime para ser considerado válido |
| endpoint | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve ser um endpoint ingerido pela PCM para ser considerado válido |
| endpointUriPrefix | Deve ter no máximo 200 caracteres alfanuméricos para ser considerado válido |
| fapiInteractionId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| httpMethod | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve pertencer ao domínio do campo para ser considerado válido |
| processTimespan | Deve ser enviado no payload (não deve estar ausente) |
| role | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve pertencer ao domínio do campo para ser considerado válido |
| serverOrgId | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato UUID e ser um código existente para ser considerado válido |
| statusCode | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve ser um valor entre 200 e 599 para ser considerado válido |
| statusUpdateDateTime | Deve estar no formato datetime para ser considerado válido |
| timestamp | Não pode estar vazio Deve ser enviado no payload (não deve estar ausente) Deve estar no formato datetime e não ser inferior a 10 dias da data de recebimento para ser considerado válido |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Portabilidade de Crédito > Regras de Validação - PC

---
id: 1339850753
title: Regras de Validação - PC
version: 2
modified: 2026-02-09T18:31:06.534Z
url: /spaces/OF/pages/1339850753/Regras+de+Valida+o+-+PC
---

v 1.01**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Portabilidade de Crédito

| Campo | Regra |
| --- | --- |
| clientOrgId | SE Método = POST ou GET E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId}% ENTÃO Se o clientOrgId for nulo, retorna Nulo Se o clientOrgId for vazio, retorna Vazio Se o REGEX do clientOrgId não for ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$, retorna Invalido |
| clientSSId | SE Role = CLIENT E método = POST ou GET E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId}% ENTÃO Se o clientSSId for nulo, retorna Nulo Se o clientSSId for vazio, retorna Vazio Se o REGEX do clientSSId não for ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$, retorna Invalido |
| consentId | SE Método = POST ou GET E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId} ENTÃO Se o consentId for nulo, retorna Nulo Se o consentId for vazio, retorna Vazio Se o REGEX do consentId não for ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%\/?#]+$, retorna Invalido |
| creationDateTime | SE Role = CLIENT E método = POST ou GET E statusCode não é 4xx ou 5xx E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId} ENTÃO Se o creationDateTime for nulo, retorna Nulo Se o creationDateTime for vazio, retorna Vazio |
| creditPortabilityStatus | SE Método = POST ou GET E statusCode não é 4xx ou 5xx E endpoint = %/credit-portability/v x /portabilities/{portabilityId} ENTÃO Se o creditPortabilityStatus for nulo, retorna Nulo Se o creditPortabilityStatus for vazio, retorna Vazio Se o creditPortabilityStatus não for ACCEPTED_SETTLEMENT_COMPLETED, ACCEPTED_SETTLEMENT_IN_PROGRESS, CANCELLED, PENDING, PAYMENT_ISSUE, PORTABILITY_COMPLETED, RECEIVED ou REJECTED, retorna Invalido |
| endpoint | SE endpoint for nulo, retorna Nulo endpoint for vazio, retorna Vazio endpoint não for um endpoint válido para Portabilidade de Crédito, retorna Invalido |
| endpointUriPrefix | SE Role = CLIENT E método = POST ou GET ENTÃO Se o endpointUriPrefix for nulo, retorna Nulo Se o endpointUriPrefix for vazio, retorna Vazio Se o REGEX do endpointUriPrefix não for ^[- /:_.,0-9a-zA-Z]{0,200}$, retorna Invalido |
| errorCode | SE Role = CLIENT E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId}% E método = POST ou GET E statusCode for 4xx ou 5xx ENTÃO Se o errorCode for nulo, retorna Nulo Se o errorCode for vazio, retorna Vazio |
| fapiInteractionId | SE Método = POST ou GET E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId}% ENTÃO Se o fapiInteractionId for nulo, retorna Nulo Se o fapiInteractionId for vazio, retorna Vazio Se o REGEX do fapiInteractionId não for ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$, retorna Invalido |
| httpMethod | SE httpMethod for nulo, retorna Nulo httpMethod for vazio, retorna Vazio httpMethod não for DELETE, GET, PATCH, POST ou PUT, retorna Invalido |
| portabilityId | SE Método = POST ou GET E statusCode não for 4xx ou 5xx E endpoint = %/credit-portability/v x /portabilities ENTÃO Se o portabilityId for nulo, retorna Nulo Se o portabilityId for vazio, retorna Vazio Se o REGEX do portabilityId não for ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$, retorna Invalido |
| rejectedBy | SE Método = POST ou GET E statusCode não é 4xx ou 5xx E endpoint = %/credit-portability/v x /portabilities/{portabilityId} ou %/credit-portability/v x /portabilities/{portabilityId}/cancel E creditPortabilityStatus = REJECTED, CANCELLED ou PAYMENT_ISSUE ENTÃO Se o rejectedBy for nulo, retorna Nulo Se o rejectedBy for vazio, retorna Vazio Se o rejectedBy não for CREDORA, PROPONENTE ou USUARIO, retorna Invalido |
| rejectionReason | SE Método = POST ou GET E statusCode não é 4xx ou 5xx E endpoint = %/credit-portability/v x /portabilities/{portabilityId} ou %/credit-portability/v x /portabilities/{portabilityId}/cancel E creditPortabilityStatus = REJECTED, CANCELLED ou PAYMENT_ISSUE ENTÃO Se o rejectionReason for nulo, retorna Nulo Se o rejectionReason for vazio, retorna Vazio Se o rejectedBy for PROPONENTE, creditPortabilityStatus for REJECTED e rejectionReason não for OUTROS, POLITICA_DE_CREDITO, SALDO_DEVEDOR_ATUALIZADO_SUBSTANCIALMENTE_DIVERGENTE, retorna Invalido Se o rejectedBy for CREDORA, creditPortabilityStatus for REJECTED e rejectionReason não for CLIENTE_COM_ACAO_JUDICIAL, CONTRATO_JA_LIQUIDADO, DECURSO_DO_PRAZO_PARA_PAGAMENTO, MODALIDADE_DA_OPERACAO_INCOMPATIVEL, PORTABILIDADE_CANCELADA_POR_FALTA_DE_LIQUIDACAO, PORTABILIDADE_EM_ANDAMENTO ou RETENCAO_DO_CLIENTE, retorna Invalido Se o rejectedBy for USUARIO, creditPortabilityStatus for CANCELLED e rejectionReason não for CANCELADO_PELO_CLIENTE, retorna Invalido Se o rejectedBy for CREDORA, creditPortabilityStatus for PAYMENT_ISSUE e rejectionReason não for DIVERGENCIA_DE_PAGAMENTO_EFETUADO ou OUTROS, retorna Invalido |
| serverOrgId | SE Método = POST ou GET E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId}% ENTÃO Se o serverOrgId for nulo, retorna Nulo Se o serverOrgId for vazio, retorna Vazio Se o REGEX do serverOrgId não for ^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$, retorna Invalido |
| statusCode | SE Método = POST ou GET E endpoint = %/credit-portability/v x /portabilities ou %/credit-portability/v x /portabilities/{portabilityId}% ENTÃO Se o statusCode for nulo, retorna Nulo Se o statusCode for vazio, retorna Vazio Se o statusCode for menor do que 200 ou maior do que 599, retorna Invalido |
| statusUpdateDateTime | SE Método = POST ou GET E statusCode não for 4xx ou 5xx E endpoint = %/credit-portability/v x /portabilities/{portabilityId} ENTÃO Se o statusUpdateDateTime for nulo, retorna Nulo Se o statusUpdateDateTime for vazio, retorna Vazio |
| timestamp | SE timestamp for nulo, retorna Nulo |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Segurança > Regras de Descarte - SG

---
id: 1212383257
title: Regras de Descarte - SG
version: 1
modified: 2025-11-18T13:20:34.267Z
url: /spaces/OF/pages/1212383257/Regras+de+Descarte+-+SG
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de descartes de reportes realizados na PCM. Estas regras são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Private API - Segurança

| Campo | Regra |
| --- | --- |
| additionalInfo | Informação não enviada Invalid type: additionalInfo: Required: additonalInfo não enviado; na ausência de additonalInfo, deve ser informada uma matriz vazia Conteúdo inválido AdditionalInfo should not be empty: additonalInfo vazio; na ausência de additonalInfo, deve ser informada uma matriz vazia Invalid type: additionalInfo: Expected object, received ‘xxxx’: conteúdo do campo additionalInfo inválido, deveria ser object |
| clientOrgId | Informação não enviada Invalid type: clientOrgId: Required: campo ClientOrgId ausente Missing property: clientOrgId: campo clientOrgid ausente Conteúdo inválido clientOrgId 'xxxx' is invalid to role 'CLIENT': clientOrgId informado é inválido para o role CLIENT clientOrgId must be a valid UUID: clientOrgId não está no formato UUID Invalid type: clientOrgId: Expected string, received ‘xxxx’: conteúdo do campo clientOrgId inválido; esperado string Requester id mismatch with clientOrgId: clientOrgId informado no role CLIENT não é a mesma organização reportadora |
| clientSSId | Informação não enviada Invalid type: clientSSId: Required: campo clientSSId ausente Missing property: clientSSId: campo clientSSId ausente Conteúdo inválido clientSSId should not be empty: campo clientSSId não pode estar vazio Invalid format: clientSSId: Invalid uuid: formato do clientSSId inválido, deve estar no formato UUID Invalid format: Unrecognized key(s) in object: 'clientSSId': conteúdo do campo clientSSId inválido Invalid type: clientSSId: Expected string, received null: conteúdo do campo clientSSId inválido; esperado string, recebido nulo |
| correlationId | Conteúdo inválido Invalid format: correlationId: Invalid correlationId format: formato do correlationId inválido (não pode ter mais de 100 caracteres) |
| endpoint | Informação não enviada Invalid type: endpoint: Required; validation error: undefined: campo endpoint ausente Conteúdo inválido Missing property, endpoint can't be empty: campo endpoint não pode estar vazio Unlisted endpoint: endpoint enviado não é válido (consultar a tabela de endpoints aceitos pela PCM) |
| endpointUriPrefix | Informação não enviada invalid type: endpointUriPrefix: Required: campo endpointUriPrefix ausente Conteúdo inválido endpointUriPrefix should not be empty: campo endpointUriPrefix não pode estar vazio Invalid format: : Unrecognized key(s) in object: 'endpointUriPrefix': conteúdo do campo endpointUriPrefix inválido |
| errorCodes | Conteúdo inválido Invalid type: additionalInfo.errorCodes.0: Expected string, received 'xxxx': conteúdo do campo inválido, deveria ser string |
| fapiInteractionId | Informação não enviada fapiInteractionId is not provided: campo fapiInteractionId não enviado Invalid field value fapiInteractionId can't be empty for status 408 or 500: fapiInteractionId deve ser enviado para status 408 e 500 Conteúdo inválido fapiInteractionId must be a valid UUID: formato do fapiInteractionId inválido, deve estar no formato UUID Invalid type: fapiInteractionId mismatch. Ensure the ID is not "00000000-0000-0000-0000-000000000000.": conteúdo do fapiInteractionId inválido Invalid type: fapiInteractionId: Expected string, received null: conteúdo do campo fapiInteractionId inválido |
| grantType (additionalInfo) | Conteúdo inválido Invalid value: additionalInfo.grantType: Invalid enum value. Expected 'AUTHORIZATION_CODE' | 'CLIENT_CREDENTIALS' | 'REFRESH_TOKEN', received 'xxxx': conteúdo do campo grantType inválido, recebido conteúdo não determinado no enum do campo Unsupported grant_type: campo grantType inválido, vazio ou ausente |
| processTimespan | Informação não enviada Invalid type: processTimespan: Required: campo processTimespan ausente Conteúdo inválido Invalid type: processTimespan: Expected number, received ‘xxxx’: conteúdo do campo processTimespan inválido; esperado número Invalid value: processTimespan must be greater than zero: campo processTimespan deve ter valor maior do que zero |
| role | Conteúdo inválido Invalid type: role: Required: campo role ausente Invalid value: role: Invalid enum value. Expected 'SERVER' | 'CLIENT': conteúdo do campo role inválido, recebido conteúdo não determinado no enum do campo |
| serverOrgId | Informação não enviada Invalid type: serverOrgId: Required: campo serverOrgId ausente Missing property: clientOrgId or serverOrgId : serverOrgId ausente Missing property: serverOrgId: campo serverOrgId ausente Conteúdo inválido Invalid field type, serverOrgId must be a valid UUID: serverOrgId não está no formato UUID Invalid type: serverOrgId: Expected string, received ‘xxxx’: conteúdo do campo serverOrgid inválido Requester id mismatch with serverOrgId: serverOrgId informado no role SERVER não é a mesma organização reportadora Requester mismatch: serverOrgId: serverOrgId informado no role SERVER não é a mesma organização reportadora serverOrgId 'xxxx' is invalid to role 'SERVER': serverIrgId informado é inválido para o role SERVER |
| statusCode | Informação não enviada Invalid type: statusCode: Required: campo statusCode ausente Conteúdo inválido Invalid type: statusCode: Expected number, received string: conteúdo do campo statusCode inválido; esperado número, recebido string Invalid value: statusCode must be between 100 and 599: campo statusCode com valor menor do que 100 ou maior do que 599 Missing property, statusCode can't be empty: campo statusCode não pode estar vazio |
| timestamp | Conteúdo inválido Error not mapped or not expected by validations: Report is too old: campo timestamp com data passada de 7 dias Invalid format: timestamp: Invalid date: conteúdo do campo timestamp inválidlo Timestamp is older than 7 days: campo timestamp com data passada de 7 dias Timestamp of report is too old: campo timestamp com data passada de 7 dias |
| webhookEnable | Conteúdo inválido Invalid type: additionalInfo.webhookEnable: Expected string, receivded bollean: conteúdo do campo webhookEnable inválido, deveria ser string, recebido boolean webhookEnable must be a string: conteúdo do campo webhookEnable inválido, deveria ser string |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Segurança > Regras de Obrigatoriedade (additionalInfo) - SG

---
id: 1212153857
title: Regras de Obrigatoriedade (additionalInfo) - SG
version: 4
modified: 2026-01-07T18:59:36.196Z
url: /spaces/OF/pages/1212153857/Regras+de+Obrigatoriedade+additionalInfo+-+SG
---

v 1.01**Guia de leitura**
1. Se o campo não está listado, é porque não existe a obrigatoriedade de enviá-lo.
2. Nos endpoints, a referência “v x ” indica que se aplicam às versões listadas na coluna “Versões”. Por exemplo, Endpoint “open-banking/automatic-payments/v x /recurring-consents/{recurringConsentId}” e Versões “v1 v2” significa que o endpoint é válido para as versões 1 e 2.
Dica: para rolar a tabela horizontalmente, segure SHIFT e utilize o botão de rolagem do mouse.Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Segurança

| Campo | Grupo | Definição | Regra de preenchimento | Roles | Http code | Métodos | Domínio | Endpoints | Tamanho máximo | Padrão | Exemplo |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| consentId | Token | O consentId é o identificador único do consentimento e deverá ser um URN - Uniform Resource Name. | Deve ser preenchido com a mesma string obtida no campo .data.consentId retornado após a chamada inicial na API "POST /consent | CLIENT | Todos menos 4xx e 5xx | POST | | /token | 100 | ^urn:[a-zA-Z0-9][a-zA-Z0-9-]{0,31}:[a-zA-Z0-9()+,-.:=@;$_!*''%/?#]+ | uGQHwNupARo7I9E2PLJZph18a0M9y7DcUe7ITt3DqUOJd9NVjnskxf2 |
| enrollmentId | Token | Identificador usado para registrar uma jornada ou um vínculo inicial | Deve ser preenchido com a mesma string obtida no campo .data.enrollmentId retornado após a chamada inicial na API "POST /enrollments". Ao reportar o uso de um endpoint /token, o identificador único de consentimento só será reportado nos casos em que "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token" | CLIENT | Todos menos 4xx e 5xx | POST | | /token | | ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*'%\/?#]+$ | urn:bancoex:C1DD33123 |
| grantType | Token | Informa o tipo de concessão (grant type) utilizado em uma solicitação | Deve ser preenchido com a mesma string enviada no campo ".grant_type "​ | CLIENT | Todos | POST | AUTHORIZATION_CODE, REFRESH_TOKEN, CLIENT_CREDENTIALS | /token | | | |
| tokenId | Todos | Identificador único e criptograficamente seguro do token utilizado no consumo da API. A implementação do tokenId preencherá a lacuna de rastreabilidade, permitindo vincular a emissão de cada token (incluindo os de CLIENT_CREDENTIALS) às suas respectivas jornadas, mesmo quando múltiplos consentimentos forem iniciados por um único token. Isso resultará em uma visão mais completa da jornada do token, aprimorando a capacidade de rastreabilidade e análise operacional para as instituições e do ecossistema | O tokenId será gerado pelo cliente (role CLIENT) no momento do reporte para a PCM, aplicado um hash SHA256 sobre o token recebido e um Pepper (segredo) gerenciado internamente pela instituição. Este tokenId deve ser reportado na PCM, complementando as informações já existentes de grant_type e consentId (onde aplicável). Para garantir a robustez criptográfica do hash, o Pepper utilizado deverá ser um valor aleatório e criptograficamente forte, gerenciado internamente pela instituição. Recomenda-se um tamanho de 128 a 256 bits para o Pepper, aplicado no cálculo do tokenId, como por exemplo, SHA256 (token + Pepper). O tokenId será composto pelos 72 bits iniciais do hash Base64URL-safe encoded.    Importante: O tokenId será gerado apenas quando o token for recebido com sucesso na resposta do POST /token. Em casos nos quais a requisição ao POST /token resultar em erros 4xx ou 5xx, o token não será obtido e, consequentemente, o tokenId não poderá ser gerado. Nessas situações, o campo tokenId deve ser omitido do reporte à PCM. | CLIENT | 200 | POST | | /token /register /register/{clientId} | | | Dados de entrada * Token: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...' (JWT completo) * Pepper: '[valor secreto da instituição]' Processo Concatenar: token + pepper Hash SHA256: da string concatenada Truncar: primeiros 72 bits (9 bytes) Codificar: Base64URL-safe Resultado { "additionalInfo": { "tokenId": "c9ng8aKzxNXm" } } |
| webhookEnable | DCR/DCM | Indica se há URLs de webhook configuradas em uma requisição. | Deve ser preenchido com o valor booleano TRUE caso haja pelo menos um item indicado na lista do campo ".webhook_uris" no payload, caso contrário deverá ser preenchido com o valor booleano FALSE | CLIENT | Todos | PUT | TRUE, FALSE | /register/{clientId} | | | |
| webhookEnable | DCR/DCM | Indica se há URLs de webhook configuradas em uma requisição. | Deve ser preenchido com o valor booleano TRUE caso haja pelo menos um item indicado na lista do campo ".webhook_uris" no payload, caso contrário deverá ser preenchido com o valor booleano FALSE | CLIENT | Todos | POST PUT | TRUE, FALSE | /register | | | |

---

# Plataforma de Coleta de Métricas > Especificações por domínio > Especificações por domínio - Segurança > Regras de Validação - SG

---
id: 1212285004
title: Regras de Validação - SG
version: 1
modified: 2025-11-18T13:20:12.260Z
url: /spaces/OF/pages/1212285004/Regras+de+Valida+o+-+SG
---

v 1.00**Objetivo desta página**Demonstrar funcionalmente as regras de validação de qualidade de campos básicos e additionalInfos realizados na PCM. Estas validações são utilizadas para aberturas de tickets e monitoramento através do dashboard de Monitoramento Operacional.**Guia de leitura**
1. Nos endpoints, a referência “v x ” deve ser substituída pela versão da API que está sendo enviada. Por exemplo, para a versão 4 (v4) dos endpoints de pagamento, enviar “open-banking/automatic-payments/ v 4 /recurring-consents/{recurringConsentId}”.
2. Nos endpoints, a referência % significa que vale para qualquer conteúdo antes ou depois, de acordo com o endpoint em questão. Por exemplo, “%/automatic-payments/v x /recurring-consents%” significa que vale para os endpoints “/open-banking/automatic-payments/v2/recurring-consents” e “/open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId}”.
Dica: não existe a opção de exportar as tabelas para Excel, porém pode-se selecionar o conteúdo da página com CTRL+A, copiar e colar no Excel. 
# Segurança

| Campo | Regra |
| --- | --- |
| consentId | SE Role = CLIENT E endpoint = %/token E não é método POST com statusCode 4xx e 5xx E grantType = AUTHORIZATION_CODE ou REFRESH_TOKEN ENTÃO Se o consentId e enrollmentId forem ambos vazios ou nulos, retorna Obrigatorio o preenchimento ou do consentId ou do enrollmentId Se o REGEX do consentId não bater com ^urn:[a-zA-Z0-9][a-zA-Z0-9\-]{0,31}:[a-zA-Z0-9()+,\-.:=@;$_!*''%/?#]+, retorna Invalido |
| enrollmentId | SE Role = CLIENT E endpoint = %/token E não é método POST com statusCode 4xx e 5xx E grantType = AUTHORIZATION_CODE ou REFRESH_TOKEN ENTÃO Se o consentId e enrollmentId forem ambos vazios ou nulos, retorna Obrigatorio o preenchimento ou do consentId ou do enrollmentId |
| grantType | SE Role = CLIENT E endpoint = %/token E statusCode = 2xx E método = POST E status = CANC ENTÃO Se o grantType for nulo, retorna Nulo Se o grantType for vazio, retorna Vazio Se o grantType não for AUTHORIZATION_CODE, REFRESH_TOKEN ou CLIENT_CREDENTIALS, retorna Invalido |
| webhookEnable | SE Role = CLIENT E endpoint = %/register E método = POST ou PUT OU endpoint = %/register/{clientId} E método = PUT ENTÃO Se o webhookEnable for nulo, retorna Nulo Se o webhookEnable for vazio, retorna Vazio |

---

# Plataforma de Coleta de Métricas > Gestão Operacional > FAQ - PCM

---
id: 45711395
title: FAQ - PCM
version: 6
modified: 2025-11-18T17:02:49.022Z
url: /spaces/OF/pages/45711395/FAQ+-+PCM
---

#### O que significa a sigla P.C.M.?
PCM significa Plataforma de Coleta de Métricas.
#### Onde podemos acessar a documentação da PCM?
A documentação está publicada na Área do Desenvolvedor dentro do portal Open Finance Brasil. Link direto: Plataforma de Coleta de Métricas 
#### Qual é o SLA para envio de reportes à PCM?
Diariamente é necessário enviar, até às 08:00 do dia seguinte (D+1) no horário padrão do Brasil (BRT), pelo menos 95% dos reportes referentes ao dia atual (D zero). Demais reportes devem ser enviados até “D+7” a partir do *timestamp*da transação. A PCM não aceitará reportes enviados após decorrido este prazo. A meta diária pode ser infringida em uma janela de 30 dias corridos por até 4 vezes, e em uma janela de 90 dias por até 10 vezes.
#### Preciso enviar dados da versão 1 da Fase 2?
Não. Esta versão está sendo depreciada.
#### Precisarei enviar dados referentes a futuras APIs em estado deprecated?
Sim. A única exceção é a versão 1.x.x da Fase 2.
#### Como faço para referenciar as marcas acionadas?
Atualmente os dados enviados à PCM não são diferenciados por marcas, estão à nível da organização (organization-org-id).
#### Havia um problema em minha integração e eu enviei um dado errado. Consigo corrigir?
Está previsto um método PUT para que o participante corrija algum dado de sua responsabilidade, entretanto o processo administrado de resolução de divergências será definido futuramente, após aprendizados baseados nos eventos observados no MVP.
#### Qual é o escopo de endpoints que a PCM vai receber?
São todas as APIs hoje disponíveis no Open Finance Brasil. Elas são separadas em duas categorias:**Private APIs:** que são as que possuem Dados de Cliente (fase 2), Serviços (fase 3) e Segurança (FAPI/OAUTH).**OpenData APIs**: que são as APIs não autenticadas, que respondem por Dados Abertos (fase 1).Você encontra na especificação técnica da PCM uma lista detalhada com todos os endpoints e que quais papéis necessitam realizar envio quais tipos de telemetria. Saiba mais
#### Temos a necessidade de teste funcional ou certificação específica dos participantes para a PCM?
Não há pré-certificação. Está previsto para que a FVP (Ferramenta de Validação em Produção) envie telemetria à PCM sobre todas as requisições feitas, e, desta forma, será possível ter métricas relativas à conformidade da integração feita pelo participante em ambiente produtivo.
#### Podemos enviar dados de sandbox para a PCM?
Até 1/2/2023 será permitido o envio de dados não produtivos. Nós recomendamos que sejam enviados dados produtivos, a fim de se colaborar para testarmos a capacidade de pareamento real da plataforma.
#### Quais são os padrões de certificado de segurança que precisam ser adotados para se integrar à PCM?
A PCM utiliza o padrão de tokens OAuth2, na modalidade client_credentials. Deve-se utilizar, para tal, um certificado de transporte (mTLS) padrão Open Finance Brasil (BRCAC) atrelado a sua organização. Para detalhes, consulte a documentação técnica da PCM.
#### Minha instituição não possui BRCAC. Como faço para me integrar à PCM?
Você poderá utilizar o certificado emitido pelo Diretório de sandbox. Para sua plena operação e 1/2/23, uma alternativa está em definição pelo GT Arquitetura.
#### Qual é o prazo para se integrar à PCM?
Prazo estabelecido, conforme Open Finance Informa #282, para 1/Fev/2023.
#### Qual é o processo para correção de eventos com divergência de reportes com status PAIRED_INCONSISTENT ou UNPAIRED?
A PCM possui um métodos do tipo PUT, que deverão ser utilizados para a realização de reenvio de pontos de telemetria problemáticos e, desta forma, se aplique a correções. Neste momento, porém, não há definição de regras definidas sobre quais os casos em que o uso do PUT será permitido, pois o GT Arquitetura optou por elaborar tais regras baseado em estudo de casos reais, com dados reais, que ocorrerem em produção pós lançamento da plataforma.
#### Como é contabilizada a paginação?
Atualmente não é feita contabilização de paginações pela PCM. Será feito um estudo para adição do pagination-key como campo no additionalInfo.
#### Estou com uma dúvida que não está explicada nem na documentação neste FAQ. Como faço para fazer perguntas para especialistas em PCM?
Utilize o Service Desk. Uma nova categoria para centralizar as questões será disponibilizada nos próximos dias.
#### Não há incoerência entre falar para não criticar a criação do consentimento, e informar se é ou não é cliente?
Os impedimentos colocados na API de pagamentos dizem respeito ao que não informar ao iniciador no momento de criação de consentimento e, portanto, não se aplicam ao processo de reporte, que ocorre de forma assíncrona à criação do consentimento, e reporta-se ao perímetro central. Por este motivo, entendemos não haver incoerência entre as recomendações.
O consentimento é criado sem qualquer crítica e, depois, em tempo de reporte, eventuais críticas ou complementação de dados são executadas para enviar o reporte apenas ao perímetro central.

---

# Plataforma de Coleta de Métricas > Gestão Operacional > Troubleshooting - PCM

---
id: 46170119
title: Troubleshooting - PCM
version: 7
modified: 2025-11-18T17:04:13.238Z
url: /spaces/OF/pages/46170119/Troubleshooting+-+PCM
---

# Solução de erros na PCM
Os erros enviados pelas APIs da PCM seguem um padrão de mensagem conforme o template abaixo:`<tipo do erro>: <detalhe do erro>`Quando múltiplos erros são enviados, eles são separados por ponto-e-vírgula (`;`).A Documentação da API - PCM contém a especificação detalhada sobre cada um dos campos.Abaixo os tipos de erro, seus significados e princípios para investigação da solução.
## Missing property
**Quando ocorre:** quando uma das propriedades do JSON está faltando. O detalhe contém o atributo. **Investigação para Solução:**Verifique o Swagger da PCM e observe se está enviando todos os campos que são requeridos em cada papel (role). 
## Invalid field value
**Quando ocorre:** quando um valor pré estabelecido para um determinado campo não é respeitado. Exemplo: enviar o valor “OPTIONS” no campo `httpMethod` gera esse erro, uma vez que essa opção não está disponível dentre as previstas. O detalhamento informa o campo que tem o valor errado.**Investigação para Solução:**Verifique o Swagger da PCM e observe se está enviando todos os campos conforme especificados.
## Unlisted endpoint
**Quando ocorre:** quando um endpoint que não está na lista de *enums* é enviado. O detalhe possui o nome do atributo que foi enviado pelo client. É uma especialização do tipo *Invalid Field Value* para o campo `endpoint`. **Investigação para Solução:** verifique a planilha com lista de endpoint e observe se o endpoint que se está enviando está na lista. Um erro comum é o envio do path que foi chamado ao invés da entrada no enum de valores permitidos. Consulte a Endpoints aceitos pela PCM para maiores informações. 
## Invalid payload format
**Quando ocorre:** quando o payload não é um array.**Investigação para solução:** envie os payloads sempre em formato de array, mesmo quando exista apenas um elemento.
## Requester id mismatch with
**Quando ocorre:** quando o organisationId de quem está enviando não é exatamente o mesmo do organisationId do contexto em questão: se a role for client, tem que bater com o clientOrgId, se for server, com serverOrgId. O detalhamento informa com qual role ele não coincidiu.**Investigação para solução:** verifique se o certificado utilizado para se recuperar o token de acesso possui as informações da organização que está enviando o reporte. O organisationId utilizado para essa checagem é o que foi recuperado do atributo OU/OrganizationIdentifier do certificado no momento da geração do token.
## Field type mismatch
**Quando ocorre:** quando há divergência no tipo de dados esperado para um determinado campo. O detalhamento informa o campo que contém o erro, bem como o tipo de dados esperado.**Investigação para solução:** verifique o tipo do dado de acordo com a documentação da API (swagger).
## Additional property not allowed
**Quando ocorre:** quando uma propriedade adicional que não está na especificação da API é enviada. O detalhamento informa o campo adicional.**Investigação para solução:** remova os campos que não estejam definidos na API. Um erro comum é a escrita errada de um campo existente.
## Report is too old
**Quando ocorre:** quando uma propriedade timestamp tem mais de 7 dias.**Investigação para solução:** altere a propriedade timestamp para que o campo tenha data inferior a 7 dias.
## OrganisationId doesn't exist on Directory.
**Quando ocorre:** quando a propriedade organizationId não existe no diretório da open banking.**Investigação para solução:** altere a propriedade organizationId com um valor existente no diretório.

---

# Plataforma de Coleta de Métricas > Gestão Operacional > Notificações via ticket > Qualidade de Dados

---
id: 1212219393
title: Qualidade de Dados
version: 1
modified: 2025-11-18T13:36:17.081Z
url: /spaces/OF/pages/1212219393/Qualidade+de+Dados
---

v 1.00
## Objetivo
Apontar os casos em que a qualidade dos dados dos reportes enviados pelas organizações dentro de um determinado período não cumpriu as regras definidas.Para melhor visualização dos dados, é possível consultar os detalhes no Dashboard de Monitoramento Operacional - Aba Qualidade de Reportes
## Escopo
São analisados os dados (comuns e additionalinfo) dos reportes de Dados Transacionais e Cadastrais (fases 2 e 4b) e Dados de Pagamentos (Fase 3), Hybridflow, Segurança e Estoque de Consentimentos.  
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.   **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.   
## Motivos da crítica de qualidade
Os motivos de crítica de qualidade de um reporte dependem de regras específicas para cada campo de cada API. As regras de validação para cada campo podem ser consultadas em em cada domínio: [https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/edit-v2/1215135767?draftShareId=7d7a2fd7-611e-419d-8342-6729b93eaf62](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/edit-v2/1215135767?draftShareId=7d7a2fd7-611e-419d-8342-6729b93eaf62)  
## Arquivo de evidências
Todo ticket aberto possui anexado um arquivo de evidências, onde são listados até 5 fapiInteractionId para cada caso encontrado por dia, para facilitar a investigação das causas pelas organizações. **Campos do arquivo de evidências** 
- role, orgid, nome: informações da organização que enviou os dados
- data_referencia: data GMT do envio do reporte
- data_deescartado: data em que foi feito o descarte do reporte
- serverorgid e clientorgid: dados das organizações envolvidas na comuicação
- api_family, api_version, endpoint, httpmethod, statuscode: identificação do reporte enviado
- *_status: campo ou additionalinfo que foi identificado como fora da qualidade establelecida pelo ecossistema OFB
- evidencias_de_fapi_*: lista de até 5 xfapis que foram criticados pelos motivos apresentados em cada campo/additionalinfo. No caso de Hybridflow, são os reportid relacionados.

---

# Plataforma de Coleta de Métricas > Gestão Operacional > Notificações via ticket > Reportes Descartados

---
id: 1212088347
title: Reportes Descartados
version: 1
modified: 2025-11-18T13:36:42.432Z
url: /spaces/OF/pages/1212088347/Reportes+Descartados
---

v 1.00
## Objetivo
Apontar os casos em que os reportes enviados pelas organizações dentro de um determinado período foram descartados e seus motivos.Para melhor visualização dos dados, é possível consultar os detalhes no Dashboard de Monitoramento Operacional - Aba Reportes Descartados.
## Escopo
São analisados os descartes dos reportes de Dados Transacionais e Cadastrais (fases 2 e 4b) e Dados de Pagamentos (Fase 3), Hybridflow e Segurança.  
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.   **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.   
## Motivos de descartes
Os motivos de descarte de um reporte dependem de regras específicas para cada campo de cada API. As regras de descarte para cada campo podem ser consultadas em em cada domínio: [https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/edit-v2/1215135767?draftShareId=7d7a2fd7-611e-419d-8342-6729b93eaf62](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/edit-v2/1215135767?draftShareId=7d7a2fd7-611e-419d-8342-6729b93eaf62). 
## Descarte do reporte
O processo de identificação e descarte do reporte pode ser encontrado em Processamento  
## Arquivo de evidências
Todo ticket aberto possui anexado um arquivo de evidências, onde são listados até 5 fapiInteractionId para cada caso encontrado por dia, para facilitar a investigação das causas pelas organizações. **Campos do arquivo de evidências** 
- role, orgid, nome: informações da organização que enviou os dados
- data_referencia: data GMT do envio do reporte
- data_deescartado: data em que foi feito o descarte do reporte
- serverorgid e clientorgid: dados das organizações envolvidas na comuicação
- api_family, api_version, endpoint, httpmethod, statuscode: identificação do reporte enviado
- mensagem_erro_1, mensagem_erro_2, mensagem_erro_3, mensagem_erro_4: motivo pelo qual o relatório foi descartado; é apresentado em até 4 campos separados porque é possível que o reporte tenha sido descartado por mais de um motivo. Neste caso, cada motivo será demonstrado separadamente
- campo_error_1, campo_erro_2, campo_erro_3, campo_erro_4: campo do reporte que foi validado para o desscarte
- evidencias_de_xfapi: lista de até 5 xfapis que foram descartados pelos motivos apresentados em cada linha do arquivo de evidências. No caso de Hybridflow, são os reportid relacionados.
 
## Referências
Fluxo de pareamento de reportes na PCMProcessamento

---

# Plataforma de Coleta de Métricas > Gestão Operacional > Notificações via ticket > Reportes Não Pareados

---
id: 1212252161
title: Reportes Não Pareados
version: 1
modified: 2025-11-18T13:37:12.662Z
url: /spaces/OF/pages/1212252161/Reportes+N+o+Pareados
---

v 1.00
## Objetivo
Apontar os casos em que não houve o pareamento de reportes enviados contra as organizações dentro de um determinado período.Para melhor visualização dos dados, é possível consultar os detalhes no Dashboard de Monitoramento Operacional - Aba Reportes Não Enviados.
## Escopo
São analisados o pareamento dos reportes de Dados Transacionais e Cadastrais (fases 2 e 4b) e Dados de Pagamentos (Fase 3).
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.   **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.   **Faltante**Quando uma organização envia um reporte contra uma outra organização, caso esta última não envie sua contraparte ela será considerada *faltante*no processo de pareamento. 
## Percentual de pareamento
O percentual de pareamento é calculado levando-se em conta a quantidade de reportes enviados contra uma organização (total esperado) e sua relação com a quantidade não enviada por esta última (total faltante). É calculado pela fórmula abaixo: De acordo com a Normativa 575 do Banco Central, o percentual esperado de pareamento é de no mínimo 95% desde 01/07/2025.
## Identificação do não-paraemento
O processo de identificação do não-pareamento por organização é apurado da seguinte maneira: Neste exemplo, olhando para a organização A, vemos que foram enviados contra ela 5 reportes (2,3,4,5 e 8), sendo que somente 2 (3 e 5) foram enviados pela organização A. Note que, olhando para a organização A como faltante, os reportes 6 e 7 não são considerados, pois são comunicações entre outras organizações.Assim, teríamos um percentual de não pareamento igual a 2 / 5 = 40%, portanto fora do mínimo esperado e passível de recebimento de ticket. 
## Arquivo de evidências
Todo ticket aberto possui anexado um arquivo de evidências, onde são listados até 5 fapiInteractionId para cada caso encontrado por dia, para facilitar a investigação das causas pelas organizações. **Campos do arquivo de evidências** 
- org_faltante, nome_faltante, role_faltante: informações da organização que não enviou os dados
- data_referencia: data GMT do envio do reporte
- api_family, api_version, endpoint, httpmethod, statuscode: identificação do reporte enviado
- contagem_unpaired_referencia: quantidade de reportes não pareados na data de referência
- contagem_chamadas_referencia: quantidade de reportes total na data de referência (pareados, pareados inconsistentes e não pareados)
- perc_unpaired_referencia: percentual de não-pareamento na data de referência
- contagem_total_unpaired, contagem_total_chamadas, perc_total_unpaired: valores de referência da API no período selecionado
- evidencias_de_xfapi: lista de até 5 xfapis que não estão pareados, informados por outras organizações contra a organização faltante
 
## Referências
Fluxo de pareamento de reportes na PCMProcessamento

---

# Plataforma de Coleta de Métricas > Gestão Operacional > Notificações via ticket > SLA de Envio de Reportes - 95% até 08-00h de D+1

---
id: 1212186625
title: SLA de Envio de Reportes - 95% até 08:00h de D+1
version: 5
modified: 2026-02-19T15:15:41.663Z
url: /spaces/OF/pages/1212186625/SLA+de+Envio+de+Reportes+-+95+at+08+00h+de+D+1
---

v 1.03
## Objetivo
Apontar os casos em que o envio dos reportes pelas organizações não ocorreu dentro do SLA de no mínimo 95% em D+1 até às 8:00.Para melhor visualização dos dados, é possível consultar os detalhes no Dashboard de Monitoramento Operacional - Aba Reporte de Informações.
## Escopo
São analisados envios dos reportes de Dados Cadastrais e Transacionais (Fases 2 e 4b), Dados de Pagamentos (Fase 3) e Estoque de Consentimentos.  
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.  **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.  **Faltante**Quando uma organização envia um reporte contra uma outra organização, caso esta última não envie sua contraparte ela será considerada *faltante*no processo de pareamento. 
## Forma de avaliação do percentual de SLA
Diariamente são apurados os reportes que não cumpriram o SLA de envio da seguinte forma:
1. Contam-se todos os reportes enviados pela organização que foram recebidos pela PCM até D-1 às 08:00 (GMT) por endpoint e método
2. Contam-se todos os reportes enviados contra a organização e que não foram pareados (faltantes) por endpoint e método; este número representa o total de reportes não enviados
3. Calcula-se o total de reportes esperados: não enviados + recebidos até 08:00 de D+1
4. O quociente entre os faltantes pelos esperados representa o percentual de não cumprimento, e o SLA do dia para a organização é calculado por [1-(faltantes/esperados)]*100
Em um exemplo prático:
- Apuração em 03/08/2025 para o Banco X
- Quantidade de reportes de 01/08/2025 enviados pelo Banco X até 02/08/2025 às 08:00 para o endpoint /payments, método POST = 18
- Quantidade de reportes de 01/08/2025 enviados contra o Banco X, endpoint /payments, método POST e que não foram pareados (Banco X faltante) = 2
- Quantidade de reportes esperados em 01/08/2025= = 18 + 2 = 20
- SLA do Banco X de 01/08/2025 para o endpoint /payments e método POST = [1 - (2/20)] * 100 = 90%
- Neste exemplo, o Banco X receberá um ticket de não cumprimento do SLA

## Pontos importantes

- O envio do ticket ocorre se qualquer os endpoints reportados pela organização e contra a organização estiver abaixo de 95%, independente do total de envios realizados pela organização no dia.
- Neste caso, se uma organização enviar reportes de 10 endpoints diferentes mas 1 deles estiver com SLA abaixo de 95%, o ticket será enviado independente do percentual dos outros endpoints.

## Arquivo de evidências
Todo ticket aberto possui anexado um arquivo de evidências, onde são listados até 5 fapiInteractionId para cada caso encontrado por dia, para facilitar a investigação das causas pelas organizações. **Campos do arquivo de evidências** 
- timestamp_gmt_date: timestamp do reporte no formato GMT
- fapiinteractionid: xfapi de exemplo do endpoint e método que não cumpriu o SLA diário
- organisationid: id da organização reportadora do reporte encontrado contra a organização notificada
- clientorgid: id da organização identificada com client no reporte encontrado contra a organização notificada
- serverorgid: id da organização identificada com server no reporte encontrado contra a organização notificada
- role: role do reporte encontrado contra a organização notificada
- status: status do reporte encontrado contra a organização notificada
- httpmethod: método do reporte que não cumpriu o SLA
- endpoint: endpoint do reporte que não cumpriu o SLA
- timestamp: timestamp do reporte encontrado contra a organização notificada

---

# Plataforma de Coleta de Métricas > Gestão Operacional > Notificações via ticket > SLA de Envio de Reportes - 99% até 7 dias da transação

---
id: 1506934785
title: SLA de Envio de Reportes - 99% até 7 dias da transação
version: 2
modified: 2026-02-19T15:16:40.404Z
url: /spaces/OF/pages/1506934785/SLA+de+Envio+de+Reportes+-+99+at+7+dias+da+transa+o
---

v 1.00
## Objetivo
Apontar os casos em as instituições não enviaram em até 7 dias o mínimo de 99% dos reportes esperados, a partir da data e horário das transações ou cuja quantidade de reportes UNPAIRED ou PAIRED_INCONSISTENT  seja superior a 1% do total de reportes esperados.
## Escopo
São analisados envios dos reportes de Dados Cadastrais e Transacionais (Fases 2 e 4b) e Dados de Pagamentos (Fase 3)  
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.  **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.  **Faltante**Quando uma organização envia um reporte contra uma outra organização, caso esta última não envie sua contraparte ela será considerada *faltante*no processo de pareamento. 
## Forma de avaliação do percentual de SLA 99%
Diariamente são apurados os reportes que não cumpriram o SLA de envio da seguinte forma:
1. Contam-se todos os reportes enviados pela organização que foram recebidos pela PCM até 7 dias da data da transação, por endpoint e método
2. Contam-se todos os reportes enviados contra a organização e que não foram pareados (faltantes) por endpoint e método; este número representa o total de reportes não enviados
3. Calcula-se o total de reportes esperados: não enviados + recebidos até 7 dias da data da transação
4. O quociente entre os faltantes pelos esperados representa o percentual de não cumprimento, e o SLA do dia para a organização é calculado por [1-(faltantes/esperados)]*100
Em um exemplo prático:
- Apuração em 11/08/2025 para o Banco X
- Quantidade de reportes transacionados de 03/08/2025 enviados pelo Banco X até 10/08/2025 para o endpoint /payments, método POST = 18
- Quantidade de reportes transacionados de 03/08/2025 enviados contra o Banco X, endpoint /payments, método POST e que não foram pareados (Banco X faltante) = 2
- Quantidade de reportes esperados transacionados em 03/08/2025 = 18 + 2 = 20
- SLA do Banco X de 03/08/2025 para o endpoint /payments e método POST = [1 - (2/20)] * 100 = 90%
- Neste exemplo, o Banco X receberá um ticket de não cumprimento do SLA

## Pontos importantes

- O envio do ticket ocorre se o total reportado pela organização para qualquer endpoint e contra a organização estiver abaixo de 99% durante 7 dias a partir da data de transação, independente do total de envios realizados pela organização no dia.
- Neste caso, se uma organização enviar reportes de 10 endpoints diferentes mas 1 deles estiver com SLA abaixo de 99%, o ticket será enviado independente do percentual dos outros endpoints.
- Essas regras valem também para os percentuais de UNPAIRED e PAIRED__INCONSISTENT superiores a 1%

## Arquivo de evidências
Todo ticket aberto possui anexado um arquivo de evidências, onde são listados até 5 fapiInteractionId para cada caso encontrado por dia, para facilitar a investigação das causas pelas organizações. **Campos do arquivo de evidências** 
- org_faltante: organização que não enviou o reporte, identificado através de reportes onde ela é a contraparte faltante no pareamento
- nome_faltante: nome da organização que não enviou o reporte
- data_referencia: data da transação do reporte no formato GMT
- endpoint: endpoint do reporte que não cumpriu o SLA
- httpmethod: método do reporte que não cumpriu o SLA
- clientorgid: id da organização identificada com client no reporte encontrado contra a organização notificada
- serverorgid: id da organização identificada com server no reporte encontrado contra a organização notificada
- perc_sla: percentual calculado do SLA
- perc_unpaired: percentual dos reportes com status UNPAIRED na data de referência
- perc_paired_inconistent: percentual dos reportes com status PAIRED_INCONSISTENT na data de referência
- evidencias_de_xfapi: até 5 xfapis que violaram o SLA ou os percentuais de UNPAIRED ou PAIRED_INCONSISTENT

---

# Plataforma de Coleta de Métricas > Integração Técnica > Documentação da API - PCM > Informações Técnicas - [PCM] Telemetria - v3.9.0

---
id: 1062141953
title: Informações Técnicas - [PCM] Telemetria - v3.9.0
version: 6
modified: 2025-11-19T21:46:39.575Z
url: /spaces/OF/pages/1062141953/Informa+es+T+cnicas+-+PCM+Telemetria+-+v3.9.0
---

## Especificação em OAS 3.0
[Download da Especificação (OAS 3.0) - v3.9.0](https://raw.githubusercontent.com/OpenBanking-Brasil/pcm-specs/refs/heads/main/PCM-v390.openapi.yaml)100%hide82583

---

# Plataforma de Coleta de Métricas > Integração Técnica > Especificações de Reporte > Processamento

---
id: 37912631
title: Processamento
version: 12
modified: 2025-12-03T17:42:13.565Z
url: /spaces/OF/pages/37912631/Processamento
---

A rotina de **Processamento** compreende o trabalho de conciliação dos dados recebidos pelas instituições, bem como o procedimento de fechamento periódico.O desenho esquemático abaixo mostra como esse processo funciona:Desenho esquemático do processo de conciliação
## Conciliação
O processo de conciliação consiste em encontrar os reportes feitos por duas instituições que representem a requisição e a devida resposta de uma transação de negócio. O processo acontece de maneira assíncrona após a recepção do reporte, e consiste em se buscar um reporte que contenha o mesmo valor no atributo `fapiInteractionId`. Se esse reporte-par não existir, o reporte corrente é considerado *não pareado* (status `UNPAIRED`). Caso esse registro exista, a segunda etapa de validação busca conciliar os campos `clientOrgId`, `serverOrgId`, `statusCode`, `httpMethod` e `endpoint`. Se esses campos estiverem com valores iguais nos dois reportes, ambos serão considerados conciliados (status `PAIRED`). Caso esses dados não sejam iguais, eles são considerados *pareados e inconsistentes* (status `PAIRED_INCONSISTENT`), e portanto divergentes. Para maiores informações sobre cada status, consulte o tópico Ciclo de vida do reporte mais abaixo. O fluxo da regra de conciliação é descrita no diagrama a seguir:Diagrama de atividades do processo de conciliação**Importante**Os participantes devem sempre que possível enviar os reportes dos dois lados, seja como server ou como client, mesmo que a chamada não tenha sido bem sucedida, uma vez que elas serão usadas para fins de controle estatístico e de monitoramento do ecossistema (objetivo principal da plataforma), incluindo casos de erros http séries 5xx, 4xx, etc.
## Fases do processamento
O processo de conciliação ocorre em três momentos do fluxo de processamento dos reportes: Recepção, Fechamento e na Resolução de Divergências.
### Recepção
Quando um report é recebido pela API, ele é validado e enfileirado para que cada reporte seja processado individualmente. É nesse momento que a maioria dos reportes serão conciliados.
### Fechamento
No momento do fechamento, a plataforma busca por todos os registros que ainda permanecem como pendentes e aplica a regra da conciliação sobre eles. Esse passo é necessário para evitar eventuais problemas de concorrência no processamento em tempo real. O momento do fechamento e os SLAs a serem cumpridos pelo sparticipantes serão oportunamente definidos pelos GTs responsáveis.
### Resolução de Divergências
Registros com os status `UNPAIRED` e `PAIRED_INCONSISTENT` são considerados divergentes e deverão passar pelo processo de resolução. Este processo será oportunamente definido pelos GT responsáveis.
## Ciclo de vida do reporte
O diagrama abaixo ilustra as interações entre os status de um reporte:Interação entre as partes de um reporteUm reporte deverá sempre estar em um dos seguinte status:
### DISCARDED
O status `DISCARDED` indica que o reporte foi enviado pelo participante e será descartado para fins de composição de métricas. Ainda que não utilizado nas métricas, ele será persistido e só será utilizado em relatórios estatísticos, não sendo possível corrigí-lo e nem utilizá-lo em nenhum processo de negócio. Esse status é devolvido para o participante de maneira síncrona no momento da inclusão do reporte. Consulte a Documentação da API - PCM para informações sobre o schema a ser enviado.
**Transições**: N/A (estado terminal)
### ACCEPTED
O status `ACCEPTED` indica que a validação de formato do reporte não apresentou erros e este será enviado para processamento.
**Transições**:
[1] Transiciona para `PAIRED` para indicar que outro reporte foi encontrado com o mesmo `fapiInteractionId` e os demais dados foram conciliados
[2] Transiciona para `PAIRED_INCONSISTENT` quando outro reporte foi encontrado com o mesmo `fapiInteractionId` mas os demais dados não foram conciliados
[3] Transiciona para `UNPAIRED` quando não existe outro reporte com o mesmo `fapiInteractionId`.[9] Transiciona para `DISCARDED` quando existe algum tipo de erro semântico no reporte.
### SINGLE
O status `SINGLE` indica que o reporte em questão não tem uma contraparte. Ele é atribuído nos casos em que o reporte não contêm  `fapiInteractionId`, como por exemplo reportes de dados abertos, em que apenas o SERVER reporta.**Transições**: N/A (estado terminal)
### UNPAIRED
O status `UNPAIRED` significa que o reporte atual não possui uma correspondência em outro reporte através do atributo `fapiInteractionId`. Indica um reporte *divergente*.
**Transições**:
[4] Transiciona para `PAIRED` para indicar que outro reporte foi encontrado com o mesmo `fapiInteractionId` e os demais dados foram conciliados. Esse processo só vai acontecer quando o reporte par for enviado.
[5] Transiciona para `PAIRED_INCONSISTENT` caso um reporte seja enviado com o mesmo `fapiInteractionId` mas algum dado esteja inconsistênte entre os reportes.
[8] Transiciona para `SINGLE` caso o reporte seja válido, mas não haja a possibilidade de conciliá-lo com outro reporte.
### PAIRED_INCONSISTENT
O status `PAIRED_INCONSISTENT` significa que o reporte corrente possui uma contraparte com o mesmo `fapiInteractionId`, mas algum dado esteja inconsistente entre os reportes. Indica um reporte *divergente*.
**Transições**:
[6] Transiciona para `PAIRED` caso o processo de resolução de divergência"*" corrija um dos dois reportes. Processo a ser definido.
### PAIRED
Indica que o reporte tem uma contraparte com o mesmo `fapiInteractionId` e os demais dados estão conciliados. Representa o estado final desejado em um fluxo correto.
**Transições**: N/A (estado terminal)

---

# Plataforma de Coleta de Métricas > Integração Técnica > Especificações de Reporte > Reporte, Processamento e Divergências

---
id: 37945368
title: Reporte, Processamento e Divergências
version: 6
modified: 2025-11-18T16:57:36.858Z
url: /spaces/OF/pages/37945368/Reporte+Processamento+e+Diverg+ncias
---

# Reporte
A Plataforma de Coleta de Métricas tem por objetivo coletar informações sobre as solicitações que foram feitas entre as instituições. Quando uma chamada é feita entre duas instituições, ambas precisam enviar para a Plataforma de Coleta de Métricas o dado sobre essa solicitação. Esse dado que é enviado pelas instituições é chamado de **Reporte**.
# Processamento
Quando um *Reporte* é recebido, a plataforma busca a contraparte, ou seja, o *reporte* enviado pela instituição que fez par com a solicitação original. Caso a encontre, os dois registros já são marcados com o status que os define como conciliados. Esse processo é feito em tempo real conforme os registros são adicionados à plataforma. O módulo de **Processamento** é responsável por fazer a conciliação em tempo real descrita acima, a conciliação no momento do fechamento e o ajuste de divergências.
# Fechamento
O Fechamento é procedimento de contabilização das chamadas enviadas pelos participantes com o objetivo de encontrar inconsistências. Ela contabiliza um período pré especificado. Ao encontrar inconsistências, esse procedimento abre *Divergências* a serem ajustadas pelas instituições.
# Divergência
Uma divergência é aberta quando um determinado *reporte* não encontra uma correspondência entre os reportes enviados pela instituição com quem a chamada foi feita. Considere hipotéticas instituições A e B. Quando A faz uma solicitação para B, ambas precisam enviar para a Plataforma de Coleta de Métricas os dados sobre essa solicitação. Caso uma delas não envie, ou envie com dados errados, é gerada uma **Divergência**.Divergências também podem ser geradas por inconsistências absolutas ou lógicas entre os reportes, tais como dados que deveriam ser iguais e diferem no momento da conciliação (absolutas) ou parâmetros que carecem de sentido quanto combinados (lógicos). note**Exemplos de inconsistências**
- Inconsistência absoluta : instituição "A" reporta que obteve um código HTTP 200, enquanto a instituição "B" reporta um código HTTP 201.
- Inconsistência lógica : Instituição "B" no pepel de server reporta um timestamp de requisição com timestamp inferior ao timestamp reportado pela instituição "A" no papel de client (um response não pode ser acontecido antes de um request).

**Exemplos de inconsistências**
- Inconsistência absoluta : instituição "A" reporta que obteve um código HTTP 200, enquanto a instituição "B" reporta um código HTTP 201.
- Inconsistência lógica : Instituição "B" no pepel de server reporta um timestamp de requisição com timestamp inferior ao timestamp reportado pela instituição "A" no papel de client (um response não pode ser acontecido antes de um request).
 
As próximas seções descrevem em detalhe cada um desses componentes.Próximo: Reporte

---

# Plataforma de Coleta de Métricas > Integração Técnica > Especificações de Reporte > Reporte

---
id: 37879861
title: Reporte
version: 54
modified: 2026-01-15T13:11:02.105Z
url: /spaces/OF/pages/37879861/Reporte
---

O Reporte é o dado que as instituições participantes enviam para a Plataforma de Coleta de Métricas para catalogar a interação entre elas. note8e78e168-3297-4961-b56f-4483117060c3**Nota sobre segurança**Consulte o Manual de Integração - Área do Desenvolvedor - Open Finance Brasil - Área do Desenvolvedor para maiores informações sobre como se autenticar na plataforma.
**Nota sobre segurança**Consulte o [Manual de Integração - Área do Desenvolvedor - Open Finance Brasil - Área do Desenvolvedor](/wiki/spaces/OF/pages/37945515/Manual+de+Integra+o) para maiores informações sobre como se autenticar na plataforma.

## Fluxo
Considerando:
- Uma interação entre "Instituição A" e "Instituição B" onde a Instituição A vai solicitar a lista de contas de um determinado responsável pelo objeto de negócio para a Instituição B;
- A parte que realiza a chamada já tem o consentimento do responsável pelo objeto de negócio para recuperar os dados;
O esquema abaixo mostra a interação entre as duas instituições. 
1. Instituição A faz uma chamada para `/accounts/v1/accounts` na Instituição B. Essa chamada contém o header `x-fapi-interaction-id` , conforme documentação do endpoint[^1];
2. Instituição B registra essa chamada e processa o pedido e retorna resposta à instituição A;
3. Instituição B envia o reporte para Plataforma Coleta de Métricas ;
4. Instituição A recebe a resposta da instituição B e envia o reporte para Plataforma Coleta de Métricas.
note69a912a2-37a8-409a-b39e-1a7c2f8b0be1**Cabeçalho**`x-fapi-interaction-id`O cabeçalho `x-fapi-interaction-id` é um cabeçalho obrigatório para o client e deve ser repetido pelo server em sua resposta conforme especificação do Open Finance Brasil. Esse cabeçalho identifica uma requisição (e sua devida resposta) em específico, e não deve ser utilizado para identificar sequências de chamadas (jornadas, paginação, etc). Cada par requisição-resposta deverá conter seu próprio valor nesse cabeçalho.
**Cabeçalho**`x-fapi-interaction-id`O cabeçalho `x-fapi-interaction-id` é um cabeçalho obrigatório para o client e deve ser repetido pelo server em sua resposta conforme especificação do Open Finance Brasil. Esse cabeçalho identifica uma requisição (e sua devida resposta) em específico, e não deve ser utilizado para identificar sequências de chamadas (jornadas, paginação, etc). Cada par requisição-resposta deverá conter seu próprio valor nesse cabeçalho.

## Modelos dos reportes
As APIs da PCM são divididas em duas categorias:**Reportes private:** representam os reportes sobre transações feitas entre duas instituições participantes do Open Finance. Se tratam de transações protegidas pelos mecanismos de segurança vigentes no OFB, e portanto são considerados reportes de APIs privadas.**Reportes opendata:** se referem aos reportes feitos em APIs da fase 1 específicas para dados abertos. Como se referem à endpoints que são disponíveis a público em geral, são considerados reportes abertos.
### Modelos para reportes Private
O reporte contém dados que se referem à uma transação em específico entre dois participantes, e é a informação que cada papel (server ou client) tem que enviar para a Plataforma de Coleta de Métricas.
Uma instituição é identificada pelo seu `organisationId` (com "s").No contexto de uma chamada, os dados enviados para a Plataforma de Coleta de Métricas pelo client e pelo server são diferentes, uma vez que essa diferença reflete os contextos de execução da transação de cada um dos lados.**Importante**Além dos campos que são obrigatórios exclusivamente para o client (`clientSSId`, `endpointUriPrefix`, e `additionalInfo`), os campos `timestamp` e `processTimespan` possuem significado diferente para cada papel, bem como o campo `role` que possui valor fixo dependendo do papel.Os campos abaixo são comuns tanto para o client quanto para o server:
| Campo | Descritivo |
| --- | --- |
| `fapiInteractionId` | UUID que identifica uma transação específica entre dois participantes. Esse dado pode ser encontrado no header x-fapi-interaction-id que é informado pelo Client e devolvido pelo Server. Mais informações em Cabeçalhos HTTP na documentação do Open Finance Brasil. |
| `endpoint` | Identificação do endpoint que foi utilizado na transação reportada. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. Nesse campo não deve ser utilizado o path da requisição original, uma vez que ao comparar com os valores dessa enum, ele não será considerado válido. Exemplo: Caso uma chamada à um endpoint com o path `/open-banking/credit-cards-accounts/v1/accounts/123456789/transactions` tenha sido feita, o valor a ser enviado no reporte é `/open-banking/credit-cards-accounts/v1/accounts/{creditCardAccountId}/transactions` , que é o identificador desse endpoint no enum. Nesse caso, o dado real da parte variável do path não deverá ser enviado. A seção endpoint em Campos Especiais abaixo possui uma lista dos valores válidos. |
| `statusCode` | Status de retorno HTTP da solicitação, conforme descrito na documentação de cada endpoint. |
| `httpMethod` | Método HTTP da solicitação. |
| `clientOrgId` | Identificador da organização de onde a chamada foi disparada |
| `serverOrgId` | Identificador da organização para onde a chamada foi feita |
| `correlationId` (opcional) | ID de correlação que identifica uma sequência de chamadas inter-relacionadas. Diferente do `fapiInteractionId` que serve para identificar cada par request-response (interação), o identificador de correlação serve para ligar diferentes reportes quando estes representam uma jornada ou uma sequência de chamadas. |
**statusCode e timeout**Quando o client não receber uma resposta do server em tempo hábil, ele deve enviar no reporte o status `408` no campo `statusCode`, e o tempo que aguardou até o evento de timeout ocorrer no campo `processTimespan` do modelo do client.**Timeout e divergências**Em casos onde o client não receber a resposta em tempo hábil e reportar um timeout, o server ainda poderá responder e reportar a resposta. O motor de conciliação vai buscar a contraparte.
#### Modelo do Client
Além dos campos padrão do reporte, o *client* necessita enviar os campos abaixo. Note que todos eles são obrigatórios:
| Campo | Descritivo |
| --- | --- |
| `timestamp` | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| `processTimespan` | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| `clientSSId` | Identificador do software statement de onde a chamada foi disparada. |
| `endpointUriPrefix` | Endereço do servidor de destino da chamada incluindo o prefixo quando houver. O formato do campo deverá ser o seguinte: `https://{host}/{prefixo}` , sendo: `host` : endereço FQDN do servidor de destino `prefixo` : toda a parte do path que vem antes da string `/open-banking` Exemplos: Para uma requisição em `https://openbanking.instituicao-1.com.br/opbk/open-banking/products-services/v1/business-accounts` , o dado a ser enviado é `https://openbanking.instituicao-1.com.br/opbk` . `Para uma requisição em https://openbanking.instituicao-2.com.br/open-banking/products-services/v1/business-accounts` , o dado a ser enviado é `https://openbanking.instituicao-1.com.br/` . |
| `additionalInfo.personType` | Identifica se a transação aconteceu em nome de uma pessoa física ou jurídica. |
| `additionalInfo.consentId` | Deve ser preenchido com a mesma string obtida no campo `data.consentId` retornado após a chamada inicial na API `POST /consent` . |
| `additionalInfo.localInstrument` | Deve ser preenchido com a mesma string informada no payload "data.localInstrument" |
| `additionalInfo.status` | Deve ser preenchido com a mesma string obtida no "data.status" |
| `additionalInfo.rejectReason` | Deve ser preenchido com a mesma string obtida no "data.rejectionReason" |
| `role` | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client. Obrigatório valor "CLIENT" |
**Importante:** Os atributos do campo `additionalInfo` deverão ser preenchidos de maneira contextual conforme valor do campo `endpoint`. Informações adicionais podem ser encontradas aqui: Especificações por domínio.Além dos campos padrão do reporte, o *server* necessita enviar os seguintes campos: 
| Campo | Descritivo |
| --- | --- |
| `timestamp` | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi disparada, imediatamente antes do primeiro byte enviado na requisição. |
| `processTimespan` | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| `role` | ENUM indicando se o reporte que está sendo enviado apresenta a visão do server ou do client. Obrigatório valor "SERVER". |
Para informações detalhadas, bem como exemplos de utilização, consulte a documentação da API.
### Reportes OpenData
Quando o envio for para um reporte de chamadas em endpoints da fase 1 (dados abertos), o modelo a ser enviado segue o padrão de dados a seguir. Como as APIs da fase 1 não se referem à transações entre duas instituições participantes, não existe processo de conciliação. 
| Campo | Descritivo |
| --- | --- |
| `endpoint` | Identificação do endpoint que foi utilizado na chamada da api de dados abertos. A identificação do endpoint deve estar entre as entradas desse enum para ser considerado válido. |
| `statusCode` | Tempo em milissegundos inteiros decorrido desde o registro do timestamp até a chegada do primeiro byte da resposta do server. |
| `httpMethod` | Método HTTP da solicitação. |
| `timestamp` | Data/Hora UTC no formato ISO8601 com milissegundos (YYYY-MM-DDTHH:mm:ss.sssZ) do momento em que a chamada foi recebida |
| `processTimespan` | Tempo em milissegundos inteiros decorrido desde o recebimento do request até o momento imediato ao envido do primeiro byte da resposta |
| `additionalInfo.clientIp` | Endereço IP do cliente que efetuou a chamada |
Para detalhes sobre o campo `additionalInfo`, consulte Especificações por domínio.
### Campos especiais

#### fapiInteractionId
O `fapiInteractionId` é um dado que precisa ser conhecido pelas duas partes. Ele trafega no header `x-fapi-interaction-id` e identifica uma chamada e resposta em específico. Quando o client enviar essa informação para o server, ambos enviam o dado que foi gerado pelo client. Caso essa informação não seja enviada pelo client, ela deve ser gerada e devolvida pelo server, e nesse caso, ambos enviam o dado gerado pelo server. Essa informação é obrigatória para a Plataforma de Coleta de Métricas, uma vez que é o principal dado utilizado na conciliação das chamadas mas, de acordo com a documentação dos headers do Open Finance.
#### endpoint
O campo `endpoint` registra o identificador do endpoint envolvido na transação. O dado faz parte do conjunto (ENUM) previamente listado na Documentação da API - PCM e reproduzido abaixo, a qual refletirá os endpoints previstos na documentação do Open Finance. Por se tratar da identificação do endpoint, o valor do *path* efetivamente trafegado na transação será considerado inválido pela plataforma, caso ele seja diferente das entradas do ENUM.O envio do campo endpoint difere para reportes privados e para reportes de dados abertos. A lista de endpoints para cada tipo de envio pode ser encontrada em Endpoints aceitos pela PCM.Existem dois casos especiais que são os endpoints `/token` e `/register`. Esses endpoints não possuem padrão pré definido, uma vez que cada participante decide suas próprias URLs e informam dentro dos seus respectivos catálogos. Portanto, para o preenchimento do reporte no papel de client, é necessário que cada participante identifique o endpoint através das URL’s de .well-known e inclua esse valor no campo `endpointUriPrefix`. Esse procedimento é obrigatório para participantes que estejam enviando reportes no papel de client. A lista de endpoints válidos será atualizada quinzenalmente dentro da PCM.
#### additionalInfo
O campo `additionalInfo` tem por objetivo concentrar informações adicionais dentro de um determinado contexto da transação. Ele tem uma ligação estrita com o campo `endpoint`, ou seja, as informações que deverão ser repassadas no `additionalInfo` dependem do valor informado no campo `endpoint`. Especificações por domínio contém o detalhamento das regras de envio de cada informação no campo `additionalInfo` conforme o contexto.**Nota sobre** `consentId` **no endpoint** `/token`Ao reportar o uso de um endpoint `/token`, o identificador único de consentimento só será reportado nos casos em que o "grant_type" é do tipo "authorization_code" ou do tipo "refresh_token", uma vez que esta informação de consentId é inexistente quando o "grant_type" é do tipo "client_credentials".Exemplos de uso e detalhamento dos campos e das operações podem ser encontradas em Documentação da API - PCM.
## Formas de Envio
Os reportes deverão ser enviados através de seus respectivos endpoints seguindo sua natureza (reportes ou opendata). Todos os reportes devem ser enviados em lotes, ainda que sejam poucos reportes por lote. É permitido enviar reportes de client e server no mesmo lote. O limite operacional estabelecido para o envio é de no máximo 5.000 reportes por requisição.Em todos os casos, o processamento dos dados é feito de forma assíncrona.
## Recepção e retorno
Quando um reporte chega nos endpoints da API, ele recebe um atributo `reportId`, que o identifica unicamente na plataforma. A partir daí é feita a validação de campos obrigatórios. Caso o formato do reporte esteja inválido, aquele `reportId` em particular será marcado com o status `DISCARDED`, acrescido de uma descrição. Caso não haja erro no formato, o report ganha o status `ACCEPTED`. Depois dessa validação, são retornados os campos `reportId`, `status` e `correlationId` (quando aplicável) para o chamador. Todos os reportes são então inseridos em uma fila de processamento, feito sempre de maneira **assíncrona**, e portanto se utiliza da premissa da consistência posterior[2].O detalhamento dos status e o ciclo de vida do reporte são detalhados no tópico sobre Processamento.[1]: A documentação das APIs do Open Finance Brasil define os cabeçalhos padrão para uma chamada. O detalhamento de cada cabeçalho pode ser encontrado em Cabeçalhos HTTP [2]: Definição de Consistência Tardia ou Posterior - [Inglês](https://en.wikipedia.org/wiki/Eventual_consistency)/[Português](https://pt.wikipedia.org/wiki/Consist%C3%AAncia_posterior) Próximo: Processamento.

---

# Plataforma de Coleta de Métricas > Primeiros passos > Endpoints aceitos pela PCM

---
id: 1069350926
title: Endpoints aceitos pela PCM
version: 6
modified: 2025-11-28T16:29:59.888Z
url: /spaces/OF/pages/1069350926/Endpoints+aceitos+pela+PCM
---

v 1.03Abaixo a lista dos endpoints aceitas pela PCM para cada categoria de API.
## API Private Reports

- accounts /open-banking/accounts/v2/accounts /open-banking/accounts/v2/accounts/{accountId} /open-banking/accounts/v2/accounts/{accountId}/balances /open-banking/accounts/v2/accounts/{accountId}/overdraft-limits /open-banking/accounts/v2/accounts/{accountId}/transactions /open-banking/accounts/v2/accounts/{accountId}/transactions-current
- admin /open-banking/admin/v2/metrics
- automatic payments /open-banking/automatic-payments/v2/recurring-consents /open-banking/automatic-payments/v2/recurring-consents/{recurringConsentId} /open-banking/automatic-payments/v2/pix/recurring-payments /open-banking/automatic-payments/v2/pix/recurring-payments/{recurringPaymentId} /open-banking/automatic-payments/v2/pix/recurring-payments/{originalRecurringPaymentId}/retry
- bank fixed incomes /open-banking/bank-fixed-incomes/v1/investments /open-banking/bank-fixed-incomes/v1/investments/{investmentId} /open-banking/bank-fixed-incomes/v1/investments/{investmentId}/balances /open-banking/bank-fixed-incomes/v1/investments/{investmentId}/transactions /open-banking/bank-fixed-incomes/v1/investments/{investmentId}/transactions-current
- consents /open-banking/consents/v3/consents /open-banking/consents/v3/consents/{consentId} /open-banking/consents/v3/consents/{consentId}/extends /open-banking/consents/v3/consents/{consentId}/extensions
- credit cards accounts /open-banking/credit-cards-accounts/v2/accounts /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId} /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/bills/{billId}/transactions /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/limits /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions /open-banking/credit-cards-accounts/v2/accounts/{creditCardAccountId}/transactions-current
- credit cards incomes /open-banking/credit-fixed-incomes/v1/investments /open-banking/credit-fixed-incomes/v1/investments/{investmentId} /open-banking/credit-fixed-incomes/v1/investments/{investmentId}/balances /open-banking/credit-fixed-incomes/v1/investments/{investmentId}/transactions /open-banking/credit-fixed-incomes/v1/investments/{investmentId}/transactions-current
- customers /open-banking/customers/v2/business/financial-relations /open-banking/customers/v2/business/identifications /open-banking/customers/v2/business/qualifications /open-banking/customers/v2/personal/financial-relations /open-banking/customers/v2/personal/identifications /open-banking/customers/v2/personal/qualifications
- discovery /open-banking/discovery/v2/outages /open-banking/discovery/v2/status
- enrollments /open-banking/enrollments/v2/consents/{consentId}/authorise /open-banking/enrollments/v2/recurring-consents/{recurringConsentId}/authorise /open-banking/enrollments/v2/enrollments /open-banking/enrollments/v2/enrollments/{enrollmentId} /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-registration-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/fido-sign-options /open-banking/enrollments/v2/enrollments/{enrollmentId}/risk-signals
- exchanges /open-banking/exchanges/v1/operations /open-banking/exchanges/v1/operations/{operationId} /open-banking/exchanges/v1/operations/{operationId}/events
- financings /open-banking/financings/v2/contracts /open-banking/financings/v2/contracts/{contractId} /open-banking/financings/v2/contracts/{contractId}/payments /open-banking/financings/v2/contracts/{contractId}/scheduled-instalments /open-banking/financings/v2/contracts/{contractId}/warranties
- funds /open-banking/funds/v1/investments /open-banking/funds/v1/investments/{investmentId} /open-banking/funds/v1/investments/{investmentId}/balances /open-banking/funds/v1/investments/{investmentId}/transactions /open-banking/funds/v1/investments/{investmentId}/transactions-current
- i nvoice financings /open-banking/invoice-financings/v2/contracts /open-banking/invoice-financings/v2/contracts/{contractId} /open-banking/invoice-financings/v2/contracts/{contractId}/payments /open-banking/invoice-financings/v2/contracts/{contractId}/scheduled-instalments /open-banking/invoice-financings/v2/contracts/{contractId}/warranties
- loans /open-banking/loans/v2/contracts /open-banking/loans/v2/contracts/{contractId} /open-banking/loans/v2/contracts/{contractId}/payments /open-banking/loans/v2/contracts/{contractId}/scheduled-instalments /open-banking/loans/v2/contracts/{contractId}/warranties
- payments /open-banking/payments/v4/consents /open-banking/payments/v4/consents/{consentId} /open-banking/payments/v4//consents/{consentId}/pix/payments  /open-banking/payments/v4/pix/payments /open-banking/payments/v4/pix/payments/{paymentId} /open-banking/payments/v4/pix/payments/consents/{consentId}
- resources /open-banking/resources/v3/resources
- security /register /register/{clientId} /token /revocation /introspection /pushed-authorization-request
- treasure titles /open-banking/treasure-titles/v1/investments /open-banking/treasure-titles/v1/investments/{investmentId} /open-banking/treasure-titles/v1/investments/{investmentId}/balances /open-banking/treasure-titles/v1/investments/{investmentId}/transactions /open-banking/treasure-titles/v1/investments/{investmentId}/transactions-current
- unarranged accounts overdraft /open-banking/unarranged-accounts-overdraft/v2/contracts /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId} /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/payments /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/scheduled-instalments /open-banking/unarranged-accounts-overdraft/v2/contracts/{contractId}/warranties
- variable incomes /open-banking/variable-incomes/v1/broker-notes/{brokerNoteId} /open-banking/variable-incomes/v1/investments /open-banking/variable-incomes/v1/investments/{investmentId} /open-banking/variable-incomes/v1/investments/{investmentId}/balances /open-banking/variable-incomes/v1/investments/{investmentId}/transactions /open-banking/variable-incomes/v1/investments/{investmentId}/transactions-current

## API Open Data

- channels /open-banking/channels/v2/banking-agents /open-banking/channels/v2/branches /open-banking/channels/v2/electronic-channels /open-banking/channels/v2/phone-channels /open-banking/channels/v2/shared-automated-teller-machines
- accounts /open-banking/opendata-accounts/v1/business-accounts /open-banking/opendata-accounts/v1/personal-accounts

- acquiring services /open-banking/opendata-acquiring-services/v1/businesses /open-banking/opendata-acquiring-services/v1/personals
- capitalization /open-banking/opendata-capitalization/v2/bonds
- creditcards /open-banking/opendata-creditcards/v1/business-credit-cards /open-banking/opendata-creditcards/v1/personal-credit-cards
- exchange /open-banking/opendata-exchange/v1/online-rates /open-banking/opendata-exchange/v1/vet-values
- financings /open-banking/opendata-financings/v1/business-financings /open-banking/opendata-financings/v1/personal-financings
- insurance /open-banking/opendata-insurance/v2/personals
- investments /open-banking/opendata-investments/v1/bank-fixed-incomes /open-banking/opendata-investments/v1/credit-fixed-incomes /open-banking/opendata-investments/v1/funds /open-banking/opendata-investments/v1/treasure-titles /open-banking/opendata-investments/v1/variable-incomes
- invoice financings /open-banking/opendata-invoicefinancings/v1/business-invoice-financings /open-banking/opendata-invoicefinancings/v1/personal-invoice-financings
- loans /open-banking/opendata-loans/v1/business-loans /open-banking/opendata-loans/v1/personal-loans
- pension /open-banking/opendata-pension/v2/risk-coverages /open-banking/opendata-pension/v2/survival-coverages
- unarranged /open-banking/opendata-unarranged/v1/business-unarranged-account-overdraft /open-banking/opendata-unarranged/v1/personal-unarranged-account-overdraft

## API Credit Portability

- credit portability /open-banking/credit-portability/v1/portabilities /open-banking/credit-portability/v1/portabilities/{portabilityId} /open-banking/credit-portability/v1/portabilities/{portabilityId}/account-data /open-banking/credit-portability/v1/portabilities/{portabilityId}/cancel /open-banking/credit-portability/v1/portabilities/{portabilityId}/payment

---

# Plataforma de Coleta de Métricas > Primeiros passos > Especificação Técnica

---
id: 37945356
title: Especificação Técnica
version: 8
modified: 2025-11-18T16:58:42.391Z
url: /spaces/OF/pages/37945356/Especifica+o+T+cnica
---

# Introdução
A plataforma de Coleta de Métricas foi idealizada com o objetivo de contabilizar as interações entre as instituições participantes, de modo a promover um ambiente equitativo e não discriminatório. Se trata de uma plataforma localizada no perímetro central, gerida pelo regulador do ecossistema.
## Motivação
Para que o ecossistema do Open Finance Brasil seja saudável para instituições e clientes finais, fez-se necessária a criação de uma plataforma que deverá concentrar dados sobre as chamadas que as instituições fazem umas às outras. Dessa forma, torna-se possível coletar informações com o objetivo de se criar métricas e indicadores a fim de se ter visibilidade sobre todo o ambiente.No intuito de manter a integridade e consistência nos dados, o envio destes pelas instituições deverá passar por um processo de conciliação. Quando divergente, as instituições serão notificadas e terão a possibilidade de ajustar as chamadas, o que promove um ambiente saudável de auto-regulação, prevenindo assim uma disputa.
## O que a plataforma não é
A plataforma recebe os dados de maneira póstuma, ou seja, dentro do período de fechamento, mas depois de a chamada concreta ter sido feita. Dada essa natureza, a plataforma não pode atuar como um agente que proíbe, bloqueia ou interfere nas interações entre as instituições.Por mais que concentre informações importantes das chamadas entre as instituições, a plataforma não é uma ferramenta de BI, e o controle de acesso aos dados é feito em diferentes níveis (participante, regulador e administrador).
## Premissas Técnicas

- Tanto o envio por parte dos participantes quanto o processamento por parte da plataforma serão feitos de maneira assíncrona;

# Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.
## Client e Server
Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é o *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados vão ser transmitidos por quem recebeu a solicitação, e recebidos por quem a fez, nesse caso, "A" é o client e "B" é o server. Em contextos onde os termos "transmissor" e "receptor" são utilizados, eles passam a significar "server" e "client" respectivamente.
## PCM
Acrônimo para Plataforma de Coleta de Métricas.
## Reporte
No contexto da API de Coleta de Métricas, um *reporte* é o registro da chamada que será enviado tanto pelo server quanto pelo client. Esse registro será armazenado na Plataforma para posterior processo de conciliação de chamadas e extração de dados estatísticos.
## Software Statement
Um participante do Open Finance é sempre identificador pelo seu `organisationId` (com "s"). Um `organisationId` um ou mais software statements, que identifica uma instancia de software autorizada a consumir os serviços do ecossistema.

---

# Plataforma de Coleta de Métricas > Primeiros passos > Manual de Integração

---
id: 37945515
title: Manual de Integração
version: 12
modified: 2025-11-18T17:00:57.586Z
url: /spaces/OF/pages/37945515/Manual+de+Integra+o
---

O presente documento demonstra o uso das APIs da Plataforma de Coleta de Métricas. 
## Referências

### Documentação da API
A documentação oficial da API se encontra em Documentação da API - PCM 
### Documentação funcional
A documentação funcional pode ser encontrada em Plataforma de Coleta de Métricas 
## Procedimento de integração

### Visão geral
O diagrama abaixo ilustra os principais componentes da plataforma Para que reportes sejam enviados para a PCM é necessário que o participante obtenha um token de acesso, o que é feito através de um endpoint de autenticação que é acessível através de uma conexão mTLS. De posse do token, o participante pode efetuar os envios para os endpoints da API descritas na documentação. É necessário o uso de certificados válidos para a recuperação do token, em contrapartida os envios de reportes são feitos sem a necessidade de uma conexão mTLS.
### Endereços base
Os endereços base em cada ambiente, bem como suas respectivas datas de validade são os abaixo:
| Ambiente | Endereço | Tipo | Validade |
| --- | --- | --- | --- |
| Sandbox | https://api.pcm.sandbox.openfinancebrasil.org.br | API | Indeterminada |
| https://auth.pcm.sandbox.openfinancebrasil.org.br | Autenticação |
| Piloto | https://api.pcm.piloto.openfinancebrasil.org.br | API | Disponível até 31/01/2023 |
| https://auth.pcm.piloto.openfinancebrasil.org.br | Autenticação |
| Produção | https://api.pcm.openfinancebrasil.org.br | API | Disponível a partir de 01/02/2023 |
| https://auth.pcm.openfinancebrasil.org.br | Autenticação |

## Autenticação
O procedimento segue o fluxo de `client_credentials` da especificação oauth2, sendo que o acesso ao endpoint precisa ser feito usando uma conexão mTLS. As credenciais, bem como os certificados aceitos em cada um dos ambientes estão descritos abaixo:
| Ambiente | Credenciais | Certificados |
| --- | --- | --- |
| Sandbox/Piloto | client_id do Software Statement do diretório de sandbox | Certificado emitido pelo diretório central de sandbox |
| Produção | client_id do Software Statement do diretório de produção | Certificado emitido por autoridade certificadora aceita pelo ecossistema [1] |
O endpoint de recuperação de token é: `<endereço de autenticação conforme ambiente>/token/`**Importante**: manter a última barra ("/") depois de *token*. Para se recuperar um token, é necessário estabelecer uma comunicação mTLS entre o cliente que está fazendo a chamada e o authorization server, utilizando um certificado de cliente. Os passos para configuração de certificados cliente no Postman podem ser encontrados em [https://learning.postman.com/docs/sending-requests/certificates/](https://learning.postman.com/docs/sending-requests/certificates/). Os tokens gerados estão configurados com duração de 21600 segundos (6 horas). Não há limitação para a quantidade de tokens gerados muito embora seja importante que eles sejam reaproveitados no período de validade. É possível fazer a introspecção do token para se determinar até quando ele é válido, uma vez que ele não é criptografado.Para recuperar um token é necessário fazer uma chamada POST usando um payload com os seguintes campos:
| client_id | `client_id` do software statement ligado ao certificado usado no acesso |
| grant_type | Fixo: `client_credentials` |
Não há a necessidade do envio do `client_secret`, uma vez que a camada de transporte via certificado cliente já assegura a autenticidade do chamador. Os campos relevantes devolvidos por esse endpoint são: 
| access_token | Token no padrão jwt para acesso às APIs |
| expires_in | Número de segundos em que o token é válido |
| token_type | O tipo do token fornecido (nesse caso, Bearer) |

### Exemplo
Envio de um request para o endereço de autenticação em sandbox: nonewide1800Resposta: wide1800
## Interação com a API
Para realizar chamadas localmente, realize a importação da documentação OpenAPI no seu cliente HTTP (Postman: [https://learning.postman.com/docs/integrations/available-integrations/working-with-openAPI/](https://learning.postman.com/docs/integrations/available-integrations/working-with-openAPI/) , Insomnia: [https://docs.insomnia.rest/insomnia/import-export-data#import-data](https://docs.insomnia.rest/insomnia/import-export-data#import-data) ). Esse procedimento irá criar as collections nos formatos descritos pela documentação. O token gerado deverá ser enviado nas chamadas da API do PCM dentro do header Authorization, identificando o tipo do token conforme abaixo: `Authorization: <token type> <token> `Onde `<token type>` pode ser Bearer, Basic, etc (no caso das APIs da PCM, será aceito apenas tokens do tipo Bearer), e o token recuperado no processo de autenticação. Usando o exemplo da chamada da sessão anterior, o header deverá ser mandado com o seguinte conteúdo: `Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IkFiT `
### Exemplo
Para o envio de um reporte como server, o request tem que ser como o exemplo abaixo:wide1800Respostawide1800
## Exemplos de chamadas
Os exemplos abaixo utilizam as instituições que participaram do Piloto da PCM. São elas (em ordem alfabética): Banrisul, BV, Caixa e Gerencianet.Os cenários de teste foram montados a fim de demonstrar o uso da API. A escolha de qual instituição faz qual chamada foi aleatória, e tem o único objetivo de exemplificar os tipos de chamadas em seus cenários.
### Cenário 1: PAIRED
BV faz chamada para Caixa, ambos enviam reportes sem erros. O status esperado para os dois reportes finais é **PAIRED**. BV:wide1800Caixa:wide1800
### Cenário 2: PAIRED_INCONSISTENT
Caixa reporta transação feita com Banrisul, mas os dados de consistência não estão iguais. O status esperado para os dois reportes finais é **PAIRED_INCONSISTENT.** Caixa:wide1800Banrisul:wide1800
### Cenário 3: SINGLE
Banrisul reporta timeout em uma transação com BV, sendo que a geração do fapiInteractionId seria feita pelo server. O status desse reporte será `SINGLE`.wide1800
### Cenário 4: DISCARDED
Gerencianet envia um reporte sem o campo httpMethod, que é um campo obrigatório. O status do reporte será registrado como DISCARDED, e o status retorno da chamada será 400. wide1800Respostawide1800
### Cenário 5: DISCARDED
Caixa envia reporte com dado inconsistente no campo endpoint (veja lista dos endpoints válidos na Documentação da API - PCM e na documentação funcional). Status do reporte tem que ser DISCARDED com a devida justificativa, e o status da resposta 400. wide1800Respostawide1800
### Cenário 6: DISCARDED
Banrisul envia reporte sem os identificadores de receptor e transmissor. Status do reporte deverá ser DISCARDED com a devida justificativa e o status de retorno, 400. No entanto, apenas o Banrisul poderá consultar esse reporte. wide1800[1] Padrão de certificação do Open Finance Brasil v2.1