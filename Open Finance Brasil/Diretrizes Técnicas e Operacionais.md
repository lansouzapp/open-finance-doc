# FAQ Onboarding ITP

---
id: 653524994
title: FAQ Onboarding ITP
version: 3
modified: 2024-12-02T18:07:33.509Z
url: /spaces/OF/pages/653524994/FAQ+Onboarding+ITP
---

**P: Qual o requisito para solicitar o início do processo de onboarding de ITP como Iniciadora?**R: Anterior à etapa de abertura do ticket via Service Desk, a ITP deve, necessariamente, preencher os requisitos descritos na página 2 do [Guia de Onboarding de Iniciador de Transação de Pagamento](https://openfinancebrasil.atlassian.net/wiki/download/attachments/589135873/%5BExternal%5D%20Manual-Onboarding-ITP_v19.pptx?api=v2).******P: Qual o requisito para ser uma detentora de conta voluntária para o processo de onboarding de ITP?**R: Para ser uma detentora voluntária para auxílio nos testes do Onboarding de ITPs é necessário que sua instituição já esteja autorizada a atuar no Open Finance Brasil como detentora de conta. Essa autorização é concedida pelo Banco Central e a atuação como detentora é independente do processo de onboarding.A solicitação de interesse deve ser manifestada via ticket no Service Desk após já ter preenchido o requisito acima. **P: Já sou uma instituição detentora de conta voluntária no Onboarding de ITP e preciso atualizar o contato do responsável. Por qual via devo realizar a atualização?**R: O controle dos contatos das detentoras de contas voluntárias no processo de Onboarding de ITP é realizado pelo GT Arquitetura e, portanto, qualquer alteração no contato do responsável deve ser enviada diretamente para o e-mail do GT ([gt-arquitetura@openfinancebrasil.org.br](mailto:gt-arquitetura@openfinancebrasil.org.br)).**P: Quais são as detentoras de conta voluntárias do processo de Onboarding?**R:  As detentoras de conta que já são voluntárias no processo de Onboarding de ITP podem ser consultadas na lista a seguir.Activtrades CctvmBanco Agibank S.A.Banco Bradesco ASBanco Btg Pactual S.A.Banco Bv S.A.Banco Cooperativo Sicredi S.A.Banco Da Amazonia S.A.Banco Do Brasil S.A.Banco Master S.A.Banco Mercantil Do BrasilBanco Modal S.A.Banco PanBanco Ribeirao Preto S.A.Banco Santander (Brasil) S.A.Banco SicoobBanco Sofisa S.A.Banco Triangulo S.A.BBR - Banco De Brasilia S.A.Caixa Economica FederalCielo S.A.Conf Nac Coop Centrais UnicredCrefisa S.A. CfiCresol ConfederaçãoGerencianetItaú Unibanco S.A.Mercadopago Instituição De Pagamento Ltda.Midway S.A. - ScfiNeon PagamentosNu Pagamentos S.A.Otimo Sociedade De Credito Direto S.A.PagseguroPefisa S.A. - CfiPicPayPinbank Brasil Instituição De Pagamento S/APortoseg S/A Credito, Financiamento E InvestimentoQi Scd S.A.Sisprime Do Brasil - Cooperativa De CreditoStone Pagamentos S.A.Sumup Scd S.A.Uniprime CentralWNT Dtvm**P: Uma das instituições do meu conglomerado já fez o onboarding, preciso refazer?**R: O onboarding de ITP é válido para todo o conglomerado caso seja utilizado o mesmo software. A autodeclaração da utilização de mesmo software deve ser realizada no diretório e o link da certificação do relying partie deve ser o mesmo.

---

# Guia de Boas Práticas

---
id: 301662235
title: Guia de Boas Práticas
version: 7
modified: 2024-11-22T18:30:42.677Z
url: /spaces/OF/pages/301662235/Guia+de+Boas+Pr+ticas
---

### OCSP e cache
As respostas OCSP das ACs podem ser cacheadas pelo participante provedor do serviço de forma a permitir melhor performance na checagem necessária à conexão mTLS oriunda do consumidor do serviço, de acordo com a política de risco de cada instituição provedora. **JWKS e cache**As respostas JWKS do diretório obtidas pelos participantes podem ser cacheadas pelo participante de forma a evitar consultas recorrentes à Infraestrutura do diretório e permitir maior celeridade nas checagens de assinatura dos *payloads*melhorando, assim, o tempo de resposta a qual o participante está sujeito.O participante pode utilizar duas estratégias para definir quando solicitar a atualização (*refresh)*de um objeto JWKS cacheado localmente:
- Update on error : Consulta o objeto JWKS vigente quando a checagem com o objeto JWKS cacheado não obtém êxito
- Update on Webhook : Consulta o objeto JWKS vigente quando recebe uma notificação de Webhook do diretório informando da mudança, conforme consta na documentação que pode ser acessada através do link 16. Configurando eventos de notificação no Diretório
 **Captura do authorization code na receptora/iniciadora**As implementações responsáveis pela captura do *authorization code* nas URLs de *call back* devem ser as mais simples possíveis, de forma a minimizar o risco de quebra de dependência e não execução da funcionalidade pelo *user-agent* do usuário. Entre outras, deve-se evitar (em ordem decrescente de criticidade):
- Dependências externas ao domínio da URL (exemplo: captcha, analytics );
- Que o conteúdo da página seja cacheado no lado do usuário;
- Dependências externas ao host da URL;
- Páginas com várias imagens;
- Demais implementações que possam não funcionar por alguma indisponibilidade de rede ou dependência a partir da máquina do usuário.
Após a captura do *authorization code*, realize as demais operações de UX necessárias. ***Payload*****de resposta e cache**Nas APIs de negócio, as respostas dos sistemas de negócio podem ser cacheadas no API *Gateway*, desde que a arquitetura do sistema invalide dinamicamente os registros em cache que não espelhem mais a realidade.

---

# Guia de Prevenção a Fraudes

---
id: 17378664
title: Guia de Prevenção a Fraudes
version: 6
modified: 2025-04-15T20:52:01.222Z
url: /spaces/OF/pages/17378664/Guia+de+Preven+o+a+Fraudes
---

Esse guia é parte integrante do Open Finance no Brasil e engloba um conjunto de recomendações para mitigações em Prevenção a Fraude, Lavagem de Dinheiro e Financiamento ao Terrorismo para as instituições participantes.O documento é focado na Iniciação de Transação de Pagamento e é composto por recomendações de estratégias que os participantes podem implementar para mitigar riscos, sendo que estas recomendações são divididas em quatro pilares: 
1) Prevenção, 
2) Detecção, 
3) Remediação e 
4) Repressão.Estas especificações fazem parte de um trabalho em desenvolvimento e novos conceitos e definições serão abordados em versões futuras deste documento. Dessa maneira, nenhuma informação aqui apresentada deve ser considerada final para qualquer propósito.Este documento não busca alterar nenhum tipo de norma ou legislação a respeito do tema, e sim recomendar melhores práticas para criar um ecossistema seguro.O guia pode ser baixado neste link [Open Finance - Guia de Prevenção a Fraudes, Lavagem de Dinheiro e Financiamento ao Terrorismo](https://openfinancebrasil.atlassian.net/wiki/download/attachments/17378664/20250225_Guia_Prev_Fraudes_Consolidado.pdf?api=v2).

---

# Processo de coleta de dados de indicadores para o Dashboard do Cidadão da estrutura do Open Finance

---
id: 460521473
title: Processo de coleta de dados de indicadores para o Dashboard do Cidadão da estrutura do Open Finance
version: 2
modified: 2024-10-31T15:26:37.055Z
url: /spaces/OF/pages/460521473/Processo+de+coleta+de+dados+de+indicadores+para+o+Dashboard+do+Cidad+o+da+estrutura+do+Open+Finance
---

O Dashboard do Cidadão reúne métricas que permitem o acompanhamento da evolução do ecossistema do Open Finance Brasil (OFB). Para atualização do painel, a Estrutura de Governança do Open Finance Brasil realiza semanalmente (conforme descrição a seguir) a coleta de dados autorreportados por instituições participantes do ecossistema. As instituições devem reportar os arquivos referentes às respectivas fases de atuação, assim como o arquivo de métricas de consumo de APIs/*endpoints.*O reporte de fases 2, 4B (Dados cadastrais e transacionais) e métricas de consumo de APIs/*endpoints* devem ser realizados por todas as instituições definidas pelo Banco Central e instituições que se voluntariaram a participar e estão certificadas para atuar nesta fase. O reporte de fase 3 (Iniciação de pagamentos) deve ser realizado por todas as instituições detentoras de conta definidas pelo Banco Central, devidamente certificadas, e instituições iniciadoras de pagamento com *onboarding* homologado no ecossistema, no qual a certificação é uma das etapas. Caso haja a inclusão de novas instituições com atuação obrigatória em uma das fases, a instituição e a Estrutura de Governança do Open Finance Brasil serão notificadas pelo Banco Central.Ao cumprir os requisitos acima, a instituição receberá uma solicitação de envio de reporte nos endereços de e-mail de cadastro técnico registrados no Diretório. A instituição poderá solicitar adição de outros endereços de e-mail na relação de envios de coleta semanais por meio de envio de mensagem ao endereço: [indicadores@openfinancebrasil.org.br](mailto:indicadores@openfinancebrasil.org.br)O processo de coleta de dados ocorre em 4 etapas:

1. [Segunda-feira] Solicitação de dados às instituições E-mail de coleta de dados é enviado para as instituições, junto a informações relevantes para o processo de coleta; Semanalmente, são enviadas 3 planilhas anexas que devem ser utilizadas como modelo de reporte de dados das fases 2, 3, 4B e métricas de chamadas de APIs/ endpoints ; As orientações de preenchimento podem ser consultadas nos respectivos arquivos modelo.
2. [Terça e quarta-feira] Recebimentos dos dados  Instituições devem realizar o envio de dados da semana vigente ao endereço indicadores@openfinancebrasil.org.br ; O título do envio do e-mail deve conter a palavra “ interoperabilidade ”, para que os arquivos sejam devidamente encaminhados à etapa de processamento de dados; O reporte deve contemplar o período de aferição de sábado a sexta-feira ( e.g.:18/05/2024 a 24/05/2024). A data-base a ser utilizada na nomenclatura dos arquivos deve referenciar a sexta-feira do período em questão ( e.g. : 20240524…) e o Registration Number corresponde ao CNPJ da instituição registrado em Diretório:
• 20240524_Interoperabilidade_da_Fase_2_e_4B_*RegistrationNumber ;*• 20240524_Interoperabilidade_da_Fase_3_*RegistrationNumber;*• 20240524_Metricas_DA_DC_*RegistrationNumber;*d. Todos os arquivos devem ser enviados em formato Excel (extensão *.xlsx);*e. Caso sejam identificadas divergências em relação ao modelo de reporte ou informações inconsistentes aos padrões requeridos, as instituições serão notificadas e um novo envio de dados é solicitado;f. Não são permitidas alterações na estrutura do arquivo modelo (*e.g.*: criação de novas colunas nas tabelas de reporte de dados);**g. O prazo de envio é de até quarta-feira, 12:00, imediatamente subsequente à data-base.**
3. **[Quinta-feira] Consolidação dos dados e*****Quality Assurance***
a. Dados enviados pelas instituições são consolidados;b. Dados recebidos fora do período (até quarta-feira) serão consolidados e processados somente na semana seguinte.
 
1. [Sexta-feira] Ingestão dos dados a. Os dados são publicados no Dashboard do Cidadão três semanas após o envio à estrutura; b. Uma vez publicados no dashboard público, os dados não podem mais ser modificados.
O prazo para envio de erratas é até a última quarta-feira dos primeiros 14 dias do mês subsequente ao mês de apuração, caso seja identificado o reporte de dados errôneos por parte da mesma à Estrutura de Governança do Open Finance Brasil.O reporte à Estrutura de Governança do Open Finance Brasil não desobriga a instituição de encaminhar as informações ao Banco Central, por meio do endereço openfinance.desup@bcb.gov.br, e vice-versa. Para o reporte ao Banco Central, devem ser consultados os prazos definidos pela Autarquia.Concomitantemente a este processo, as instituições devem se integrar à Plataforma de Coleta de Métricas (PCM) para o envio dos reportes das integrações individuais. As instruções referentes a este processo estão disponíveis em: Área do Desenvolvedor - Especificações de Integração - **Plataforma de Coleta de Métricas**

---

# Solução de contorno de Hybrid flow em navegadores no Android

---
id: 817823765
title: Solução de contorno de Hybrid flow em navegadores no Android
version: 2
modified: 2025-03-13T19:23:18.626Z
url: /spaces/OF/pages/817823765/Solu+o+de+contorno+de+Hybrid+flow+em+navegadores+no+Android
---

Algumas instituições receptoras/iniciadoras reportaram um problema que ocorre especificamente na utilização do fluxo *web-to-app* quando a parte web se inicia via Google Chrome, ou navegadores semelhantes, em dispositivos Android. ​Este problema acontece porque o Google Chrome, no momento de redirecionamento para o aplicativo da instituição detentora/transmissora, realiza uma pré validação do link de redirecionamento, e essa pré validação acaba "queimando" a URL de *request_uri*. Essa "queima" acontece porque segundo a RFC 9126, sessão 4, é recomendado que a URL *request_uri* seja de uso único, portanto uma segunda chamada a ela deveria ser invalidada. Esta recomendação combinada com o comportamento do Google Chrome em dispositivos Android causa um problema na experiência do usuário, pois o mesmo fica impossibilitado de completar a aprovação do consentimento. ​Para contornar este problema, foi encontrada uma solução que pode ser aplicada diretamente pelos receptores/iniciadores e este contorno está documentado no video abaixo. Essa solução se baseia na criação de um *intent* com base no *package* da aplicação da instituição transmissora/detentora para que o redirecionamento ocorra diretamente para o aplicativo sem requisição “*pre flight*” realizadas pelo próprio navegador Chrome. **Demonstração da implementação da solução**

---

# Guia de Atendimento de Tickets pelo N2 > 01. Acesso ao Service Desk OFB

---
id: 309821596
title: 01. Acesso ao Service Desk OFB
version: 4
modified: 2024-09-04T19:43:27.507Z
url: /spaces/OF/pages/309821596/01.+Acesso+ao+Service+Desk+OFB
---

Nesta página serão detalhadas as etapas para o analista acessar a ferramenta do Service Desk do OFB.
## Acesso ao Portal de Serviços
O Portal de Serviços da SysAid é uma estrutura de portal front-end que permite experiências de autoatendimento para seus usuários (Requisitantes e Equipes de Atendimento).
1. Acessar o ambiente de produção da Ferramenta de Service Desk Sysaid através do endereço: https://servicedesk.openfinancebrasil.org.br .
2. Faça o login com o usuário do Diretório pelo botão "Acessar via Diretório" ou digite seu nome de usuário “ E-mail e Senha” , caso possua um acesso local.
3. Pressionar o botão Logar.
4. Em relação ao “Logar como login convidado: "Caso o usuário desenvolvedor ou participante do Open Finance não possua o cadastro na plataforma, poderá ser solicitado o acesso utilizando o botão "Convidado" disponível na tela de login".

## Acesso ao Dashboard de Atendimento

1. Ao logar com um usuário N2, você será redirecionado(a) ao dashboard de atendimento da sua instituição e/ou equipe de atendimento .
*6, Para acessar os tickets, clique em " **Central de Serviços** " e " **Tudo** ".*
## Acesso ao Painel de Tickets

1. Serão apresentados os tickets que foram encaminhados para a fila de atendimento da sua instituição e/ou equipe de atendimento .
2. Certifique-se no campo “ Status ” de que não há filtros selecionados, assim você terá a visão de todos os tickets da sua fila.
*Na opção “Ativo” são todos os tickets em Estoque / Pendentes.*9. *Clique no ticket  para iniciar o atendimento.*
##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 02. Detalhamento dos Campos

---
id: 309821669
title: 02. Detalhamento dos Campos
version: 4
modified: 2024-09-04T19:43:53.859Z
url: /spaces/OF/pages/309821669/02.+Detalhamento+dos+Campos
---

Nesta página serão apresentadas todas as informações da aba “Detalhes Gerais”.
1. Número do ticket (Incidente ou Solicitação de Serviço)
2. Data de solicitação e encerramento
3. Nome e Empresa do usuário solicitante
4. Equipes de atendimento,  solucionadora e especialista responsável pelo responsável pelo atendimento
5. Categorias do ticket
6. Prazo de SLA do ticket

1. As informações preenchidas pelo usuário requisitante no campo “ Titulo ” e “ Descrição ” serão apresentadas no corpo do ticket.
2. As “ Notas ” deverão ser utilizadas para interagir com o requisitante.  Solicite ou envie informações neste campo.
3. Clique “ +Novo ” para inserir uma nota no pop-up do campo

1. Os anexos inseridos pelo requisitante estarão disponíveis no campo de " Anexos“, clique o arquivo para realizar o download.
2. Clique em “ clique para buscar " para anexar um arquivo no ticket

##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 03. Início do Atendimento de Tickets pelo N2

---
id: 309821740
title: 03. Início do Atendimento de Tickets pelo N2
version: 4
modified: 2024-09-04T19:44:35.509Z
url: /spaces/OF/pages/309821740/03.+In+cio+do+Atendimento+de+Tickets+pelo+N2
---

## Iniciando o Atendimento
Vamos iniciar o atendimento do ticket  alterando o status de **“**Encaminhado N2 Atendimento” para "**Em Atendimento N2**“
1. Utilize o status " Em Análise N2 " para os tickets que não possuem uma tratativa imediata.
2. Selecione o analista que irá atender o ticket.
3. Clique em " Aplicar " ou " Salvar " para salvar as alterações.
***Ponto Importante:** Durante o atendimento, caso o analista identifique a necessidade de reclassificar o ticket para “Erros de desconformidade na implementação” ou “Demais erros” e/ou o Prazo de SLA, ele deve solicitar a “*[Reclassificação](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/309821988#Reclassifica%C3%A7%C3%A3o-e-Altera%C3%A7%C3%A3o-do-prazo-de-SLA)*”, se precisar se comunicar com o N1 ele deve utilizar a aba “*[Atividades](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/309821988#Aba-Atividades)*”, exceto se a alteração ocorrer no momento de alteração para o status “*[Aguardando implementação N2](https://openfinancebrasil.atlassian.net/wiki/x/AwBiDg)*”.****Obs:** Caso o analista N2 das **filas da ESTRUTURA** identifique que o ticket deve ser direcionado para outra equipe (N2 ou N3), ele deve utilizar o status " Encaminhado N2 Atendimento " ou " Encaminhado N3 Atendimento " e na "Equipe de Atendimento" selecionar a equipe que será direcionado o ticket N2 ou N3*
1. Leia atentamente as informações do tickets “ Titulo ”, “ Descrição ”, “ Anexo ” Neste momento inicia o atendimento, validação até a solução por parte da equipe N2 responsável.
2. Encontrando a solução, vá para aba “ Solução ”.

## Aba Solução

1. Clique na aba de “ Solução” para finalizar o atendimento do ticket.
2. Altere o status para “ Atendimento Encerrado ”
3. No campo de Solução , insira as informações com riqueza de detalhes, apresentando causa-raiz, e sempre que possível, o processo que foi executado para chegar ao resultado.
4. Se for um ticket de “ Incidentes ” deve ser informado se o conteúdo da reclamação é procedente ou não .
5. Clique em “Salvar” para salvar as alterações.

## Atendimento Encerrado
*Todas as informações do ticket são atualizadas após o ticket ser encerrado status “ **Atendimento Encerrado** ”*
1. Número do ticket (Incidente ou Solicitação de Serviço;
2. Data de encerramento;
3. Status do ticket “Atendimento Encerrado”;
4. Equipe N2 responsável pelo atendimento/solução;
5. Prazo de SLA do ticket.

##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 04. Interação com o Requisitante

---
id: 309821827
title: 04. Interação com o Requisitante
version: 4
modified: 2024-09-04T19:45:06.572Z
url: /spaces/OF/pages/309821827/04.+Intera+o+com+o+Requisitante
---

Nesta página serão apresentados momentos de interação com o requisitante.
## Reaberto pelo Requisitante
*Após o ticket ser encerrado, o requisitante possui até **3 dias úteis para reabrir** o ticket.*
1. Caso o ticket seja reaberto pelo requisitante, ele estará disponível na fila de atendimento com o status " Reaberto pelo Requisitante " ou " Encaminhado N2 Atendimento “.
2. Observe que a Data de encerramento estará vazia.
3. No campo Notas deverá ter o motivo da reabertura do ticket.
*Inicie o atendimento do ticket alterando o status para " **Em atendimento N2 (***[Inicio do Atendimento](https://openfinancebrasil.atlassian.net/wiki/spaces/DTO/pages/232620233/V1+-+Guia+de+Atendimento+de+Tickets+pelo+N2#Etapa-7%3A-Atendimento-de-tickets-pelo-N2---Aba-Detalhes)***).***
## Aguardando Requisitante
*Após iniciar o atendimento do ticket, o analista identifica a necessidade de pedir novas informações ao requisitante, ele deve:*
1. Alterar  o status para “ Encaminhado N1 Análise ”
2. No campo Notas incluir quais informações precisam ser solicitadas ao requisitante.
3. Clique em " Salvar " para salvar as alterações
***Ponto Importante:** Existem três diferentes status “aguardando requisitante”. Somente dois deles pausam o SLA:*
- AGUARDANDO REQUISITANTE  - O SLA não é pausado. É utilizado para solicitar informações/evidencias ao requisitante para tratamento/andamento dos tickets.
- AGUARDANDO REQUISITANTE – ESSENCIAL - O SLA é pausado. É utilizado para solicitar informações/evidencias essenciais ao requisitante,  apenas para os tickets que não foram preenchidas corretamente nos campos dos formulários ;
- AGUARDANDO REQUISITANTE – VALIDAÇÃO DA IMPLEMENTAÇÃO - O SLA é pausado. É utilizado após uma implementação feita pelo N2, ou seja, quando um ticket passou em algum momento no status “AGUARDANDO IMPLEMENTAÇÃO N2”.

1. O N1 irá alterar o status para “Aguardando Requisitante”.
2. O Analista N2 deverá aguardar o retorno das informações atualizadas pelo requisitante.
***Ponto importante:** Se o ticket ficar em um dos três status “ **Aguardando Requisitante** ” por mais de 5 dias úteis sem interação do requisitante, será*
*encerrado automaticamente, não sendo necessária a ação por parte da equipe N2.*
## Atualizado pelo Requisitante
*Após a atualização do Requisitante:*
1. O ticket retornará para o N2 no status “ Atualizado pelo Requisitante " ou " Encaminhado N2 Atendimento "
2. O analista deve verificar os campos “ Notas e Anexo ”  se as informações foram fornecidas pelo requisitante.
*Inicie o atendimento do ticket alterando o status para " **Em atendimento N2 (***[Inicio do Atendimento](https://openfinancebrasil.atlassian.net/wiki/spaces/DTO/pages/232620233/V1+-+Guia+de+Atendimento+de+Tickets+pelo+N2#Etapa-7%3A-Atendimento-de-tickets-pelo-N2---Aba-Detalhes)*)*
##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 05. Aguardando Implementação N2

---
id: 309821890
title: 05. Aguardando Implementação N2
version: 4
modified: 2024-09-04T19:46:09.165Z
url: /spaces/OF/pages/309821890/05.+Aguardando+Implementa+o+N2
---

*Se, após iniciar o atendimento, o analista identificar que para solução do ticket necessita de um **desenvolvimento** , ele deve:*

1. Alterar  o status para “ Aguardando Implementação N2.
2. Será disponibilizado um novo campo “ Data Prevista para Implementação ”.
3. Clique para aparecer o calendário e insira a data prevista para implementação.
4. Clique “ +Novo ” para inserir uma “ Nota ” informando os requisitos para Reclassificação e/ou alteração do Prazo de SLA.
*Após o preenchimento da “justificativa” dos requisitos para alteração do Prazo de SLA ou Reclassificação do ticket no campo **Notas** :*

1. Status “ Aguardando Implementação N2 ”
2. Se a data definida para Implementação da correção for posterior ao “Prazo de SLA”
3. I rá aparece uma janela para “justificar” e “informar os requisitos” para alteração do Prazo do SLA e/ou Reclassificação do ticket, conforme os critérios da Instrução Normativa BCB Nº359.
*Após o preenchimento da “justificativa” dos requisitos para alteração do Prazo de SLA ou Reclassificação do ticket na janela **Justificativa** :*

1. O status passa automaticamente para “ Encaminhado N1 Análise ”.
2. Na aba " Atividades “ aparece a justificativa data pelo analista do N2.
*Após a análise e validação da “justificativa” dos requisitos para alteração do Prazo de SLA ou Reclassificação do ticket pelo N1:*

1. O status volta para “ Aguardando Implementação N2 ” e o ticket deverá ser mantido ativo neste status até que a solução seja implementada .
2. O novo prazo de SLA será atualizado, lembrando que não pode exceder os limites da IN BCB 359, mesmo que a data prevista para implementação da correção seja superior ao respectivo limite máximo.
3. A data deve ser atualizada sempre que estiver no passado e/ou houver replanejamento.
***Ponto importante:** Em relação aos incidentes “Erros de desconformidade de implementação” e “Demais erros”, o Banco Central do Brasil poderá estabelecer prazos diferenciados para sua correção em virtude de análise quanto ao esforço requerido e ao impacto para o cidadão.*Após a implementação da correção, o analista N2 poderá solicitar a validação
ao requisitante ou encerrar o ticket.

1. Alterar o status para “ Encaminhado N1 Análise ”.
2. No campo Notas deve ser solicitada a validação da implementação e incluídas eventuais orientações ao requisitante.
3. Clique em " Salvar " para salvar as alterações.
***Ponto importante:** Neste cenário de validação, o N1 irá alterar o status para “ **Aguardando Requisitante – Validação da Implementação** ” e o relógio do SLA é pausado.*
- AGUARDANDO REQUISITANTE – VALIDAÇÃO DA IMPLEMENTAÇÃO IMPLEMENTAÇÃO o SLA é pausado. É utilizado após uma implementação feita pelo N2, ou seja, quando um ticket passou em algum momento no status “AGUARDANDO IMPLEMENTAÇÃO N2” .

## Aguardando Requisitante – Validação da Implementação
*Após alteração do status no N1 para “ **Aguardando Requisitante – Validação da Implementação** ”, o requisitante irá interagir no ticket podendo “ **Adicionar nota** ” ou **“Fechar ticket** ”*

1. Após o retorno do ticket, para o N2 o status será “ Atualizado pelo Requisitante " ou " Encerrado pelo requisitante "
*Inicie o atendimento do ticket alterando o status para " **Em atendimento N2 (***[Inicio do Atendimento](https://openfinancebrasil.atlassian.net/wiki/spaces/DTO/pages/232620233/V1+-+Guia+de+Atendimento+de+Tickets+pelo+N2#Etapa-7%3A-Atendimento-de-tickets-pelo-N2---Aba-Detalhes)***).******Ponto importante:** o SLA é pausado e se o ticket ficar em “ **Aguardando Requisitante – Validação da Implementação** ” por mais de 5 dias úteis sem interação do requisitante, será encerrado automaticamente, não sendo necessária a ação por parte da equipe N2.*
##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 06. Reclassificação e Alteração do prazo de SLA

---
id: 309821988
title: 06. Reclassificação e Alteração do prazo de SLA
version: 5
modified: 2024-09-04T19:47:00.591Z
url: /spaces/OF/pages/309821988/06.+Reclassifica+o+e+Altera+o+do+prazo+de+SLA
---

Nesta página serão explicados os tipos de erros que podem ser utilizados e prazos diferenciados para correções. 
1. Para solicitar a reclassificação e alteração do SLA utilize a aba " Atividades “.
2. Para o Ticket poder ser reclassificado para " Demais erros " deverá ser informado qual aspecto não estava previsto na documentação, os trechos divergentes da documentação ou o motivo de eventual ambiguidade na documentação.
3. Para o ticket poder ser reclassificado para " Erros de desconformidade de implementação " a situação objeto do ticket não pode estar sendo testada em motores de conformidade nem em ferramentas de validação em ambiente produtivo; dessa maneira, na descrição da atividade, deve haver declaração explícita de que o objeto do ticket não está sendo testado em motores de conformidade nem em ferramentas de validação em ambiente produtivo.
*Após a adição da Atividade, o status do chamado deve ser alterado para " **Encaminhado N1 Análise** “ . Para o N1 atuar no ticket, atualizando o SLA de acordo com as informações inseridas. Caso a instituição receba prazos diferenciados pelo Banco Central do Brasil, o analista N2 deverá seguir o mesmo fluxo citado acima e informar o novo prazo estabelecido.*
## Aba Atividades

1. A aba “Atividades” é utilizada para comunicação entre as equipes de N1, N2 e N3.
2. No campo de Atividades, deverão ser adicionadas informações pertinentes apenas a outra equipe de atendimento
***Pontos Importantes:***
- As equipes N2 das Instituições, só se comunicam com o N1.
- No caso das equipes da ESTRUTURA elas podem se comunicar pela Aba “Atividades” e encaminhar os tickets entre as equipes n2 e N3.

##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 07. Aba Histórico

---
id: 309822039
title: 07. Aba Histórico
version: 4
modified: 2024-09-04T19:47:22.720Z
url: /spaces/OF/pages/309822039/07.+Aba+Hist+rico
---

1. Clique na aba de “ Histórico” para conferir as interações do ticket.
2. Detalhes das interações.

##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 08. Definição de STATUS e Fluxo de Atendimento Service Desk

---
id: 309822085
title: 08. Definição de STATUS e Fluxo de Atendimento Service Desk
version: 4
modified: 2024-09-04T19:49:19.742Z
url: /spaces/OF/pages/309822085/08.+Defini+o+de+STATUS+e+Fluxo+de+Atendimento+Service+Desk
---

## Definição de STATUS - OFB
A seguir serão apresentados os status do Service Desk e o detalhamento de cada um:
## Fluxo de Atendimento Service Desk
Nesta seção iremos mostrar o fluxo de atendimento do service desk 
##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > 09. Guia de Atendimento de Tickets pelo N2 versão PDF

---
id: 309822151
title: 09. Guia de Atendimento de Tickets pelo N2 versão PDF
version: 4
modified: 2024-09-04T19:49:46.192Z
url: /spaces/OF/pages/309822151/09.+Guia+de+Atendimento+de+Tickets+pelo+N2+vers+o+PDF
---

No anexo a seguir, nós temos o guia de atendimento que será apresentado neste material versão PDF:
##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Atendimento de Tickets pelo N2 > Controle de Versão [GATN2]

---
id: 309821538
title: Controle de Versão [GATN2]
version: 6
modified: 2024-09-04T19:39:06.410Z
url: /spaces/OF/pages/309821538/Controle+de+Vers+o+GATN2
---

| Versão | Data | Resumo das Alterações |
| --- | --- | --- |
| 1.0 | | Criação do Documento. |
| 2.0 | | Correções pontuadas pelo Squad Service Desk |

##### Em caso de dúvidas sobre o processo de atendimento no Service Desk, abrir um chamado na ferramenta Sysaid ou entrar em contato pelo e-mail gestao.atendimento@openfinance.com.br .

---

# Guia de Operação da Ferramenta de Validação em Produção > Execução do Plano de testes de Pix Automático na FVP

---
id: 958693401
title: Execução do Plano de testes de Pix Automático na FVP
version: 1
modified: 2025-05-15T04:31:23.185Z
url: /spaces/OF/pages/958693401/Execu+o+do+Plano+de+testes+de+Pix+Autom+tico+na+FVP
---

## Introdução
Esta página possui como intuito auxiliar as instituições para realizarem a devida configuração e execução da FVP Manual para os testes relacionados ao produto de Pix Automático.
- Acessando e configurando a FVP : Para as devidas instruções de acesso e configurações iniciais da ferramenta, é recomendado que sejam seguidas as etapas presentes no Guia de Operação da FVP , na etapa “Configurando e executando testes”;
- Nome do Plano de Testes de Pix Automático : Para execução dos testes de Pix Automático na FVP, o seguinte plano de testes na plataforma deve ser selecionado: “ Production Functional Tests for Automatic Pix Payments - API Version 2.1” Este plano de testes valida os fluxos funcionais da API Pagamentos Automáticos via Pix (versão 2.1) no ambiente de produção.

## Preenchimento de Campos
Além dos campos padrão exigidos para a seleção do *Authorization Server*, o plano de testes de Pix Automático requer também o preenchimento de **campos adicionais obrigatórios**.
Esses campos simulam dados reais de usuários e contas, necessários para a execução adequada dos fluxos de Pix Automático.Esses campos incluem:
- Informações sobre o usuário autenticado (CPF ou CNPJ)
- Informações do devedor presentes no consentimento ( debtor )
- Detalhes completos da conta do credor ( creditor )
**Nota:** O Pix Automático foi desenvolvido para pagamentos destinados a pessoas jurídicas (empresas). A conta a ser creditada deve ser corporativa (CNPJ). Pagamentos para pessoas físicas não são suportados.**Segue o detalhamento dos campos adicionais obrigatórios de preenchimento:**
- Dados do Usuário Autenticado (Pessoa Física ou Jurídica)

| Campo | Descrição | Exemplo |
| Payment consent - Logged User CPF | CPF do usuário que está autorizando o consentimento | 76109277673 |
| brazilCpf | CPF utilizado durante a autenticação | 76109277673 |
| brazilCnpj * | CNPJ utilizado durante a autenticação, caso o teste seja com um usuário pessoa jurídica | <seu CNPJ> |
*Obrigatório apenas se o usuário autenticado for uma pessoa jurídica. 
- Informações do Debtor (dentro do consentimento)

| Campo | Descrição | Exemplo |
| Recurring Payment consent - Contract Debtor Name | Nome do titular da conta responsável pelo pagamento | Ralph Bragg |
| Recurring Payment consent - Contract Debtor Identification | CPF ou CNPJ do titular da conta | 76109277673 |

- Creditor Account (deve pertencer a uma entidade legal)

| Campo | Descrição | Exemplo |
| Payment consent - Creditor Account Name | Nome da empresa que receberá os valores | Empresa Exemplo S.A. |
| Payment consent - Creditor Account CPF/CNPJ | CNPJ da empresa que receberá os valores | 50685362006773 |
| Payment consent - Business Entity CNPJ | CNPJ da pessoa jurídica recebedora | 50685362006773 |
| Payment consent - Creditor Account ISPB | Código ISPB da instituição financeira recebedora | 99999004 |
| Payment consent - Creditor Account Issuer | Código da agência da conta do recebedor | 0001 |
| Payment consent - Creditor Account Number | Número da conta do recebedor | 11188222 |
| Payment consent - Creditor Account Type | Tipo da conta (ver opções abaixo) | SVGS |
**Importante:** A conta recebedora deve, obrigatoriamente, pertencer a uma pessoa jurídica (CNPJ). Contas de pessoas físicas (CPF) **não são válidas** para fluxos de Pix Automático.**Sobre o campo*****accountType*****:**Indica o tipo de conta bancária utilizada pelo credor (recebedor). Este campo é obrigatório e deve ser consistente com os demais dados da conta (ISPB, agência, número).Valores Permitidos (conforme versão 2.1.0 da API do Open Finance Brasil):
| Valor | Descrição |
| CACC | Conta Corrente |
| SVGS | Conta Poupança |
| TRAN | Conta de Pagamento Pré-Paga |
**Nota**: Contas salário (SLRY) não são permitidas nessa API.
## Modelo de Configuração FVP:
O modelo a seguir serve para instruir como construir uma configuração funcional para os planos de teste da FVP. Abaixo estão listados todos os campos que você deverá preencher no arquivo JSON de configuração para executar os módulos de teste da FVP:{    "alias": "74e929d9-33b6-4d85-8ba7-c146c867a817",    "description": "mock",    "server": {        "discoveryUrl": "[https://auth.mockbank.poc.raidiam.io/.well-known/openid-configuration](https://auth.mockbank.poc.raidiam.io/.well-known/openid-configuration)",        "authorisationServerId": "xxxxx-xxxx-xxxx-xxxx-xxxxx"    },    "resource": {        "brazilOrganizationId": "xxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",        "name": "John Doe",        "brazilCpf": "00000000000",        "loggedUserIdentification": "00000000000",        "paymentAmount": "0.00",        "creditorAccountIspb": "00000000",        "creditorAccountIssuer": "0000",        "creditorAccountNumber": "0000000000",        "creditorAccountAccountType": "CACC",        "creditorName": "John Doe",        "creditorCpfCnpj": "00000000000",        "creditorProxy": "00000000000",        "debtorAccountIspb": "00000000",        "debtorAccountNumber": "0000000",        "debtorAccountIssuer": "0000",        "debtorAccountType": "TRAN"        "contractDebtorName": "Example",        "contractDebtorIdentification": "00000000000"    },    "directory": {        "participants": "[https://data.example.directory/participants](https://data.example.directory/participants)",        "keystore": "[https://keystore.example.directory/](https://keystore.example.directory/)",        "apibase": "[https://api.example.directory/](https://api.example.directory/)",        "directoryRootsUri": "[https://data.example.directory/roots_directory.jwks](https://data.example.directory/roots_directory.jwks)",        "discoveryUrl": "[https://auth.example.directory/.well-known/openid-configuration](https://auth.example.directory/.well-known/openid-configuration)"    }}

---

# Guia de Operação da Ferramenta de Validação em Produção > FVP Automática

---
id: 553254972
title: FVP Automática
version: 4
modified: 2025-11-06T13:17:44.210Z
url: /spaces/OF/pages/553254972/FVP+Autom+tica
---

1. Escopo de testes
Com rotina de execução diária e automática, a ferramenta realiza testes de conformidade periódicos em servidores selecionados e reporta os resultados à instituição testada via plataforma Service Desk de maneira automática.Os testes realizados contemplam validações que não precisam de interação de usuário, especialmente DCR, FAPI, testes funcionais e de cadastro no Diretório.Esses testes também estão disponíveis para execução pelas instituições através da FVP Manual.
1. Fluxo de notificação das instituições através de tickets no Service Desk
**a.      Abertura de Tickets**Após a execução da FVP automática, caso a instituição falhe em algum dos testes executados, a rotina abrirá um ticket ou atualizará os existentes. Dois tipos de tickets podem ser criados:I. "Teste Automático DCR - *CustomerFriendlyName*" - aberto se o servidor falhar em pelo menos um teste relacionado ao DCR ou testes funcionais.II. "Teste Automático Cadastro Diretório - *CustomerFriendlyName*" - aberto se o servidor falhar em pelo menos um teste relacionado à validação de cadastro no diretório.Se o servidor falhar em ambos os tipos de testes, ambos os tickets serão abertos para a instituição. Dentro do ticket, as seguintes informações devem estar presentes:
- Lista dos testes que retornaram falha
- Hipóteses sobre as falhas para ajudar os participantes a ajustar suas implementações
- Well-Known do servidor testado
- ID do Authorisation Server encontrado no Diretório
·       Evidências apontando onde a instituição falhou no plano de testes em dois formatos potenciais:o   URI para página de resultados, que poderá ser acessada apenas por usuários autenticados com as credenciais do Diretórioo   Arquivo *zip* com os *logs* de execução**b.     Manutenção de Tickets**Caso a instituição continue com falha na execução, as falhas serão anexas ao ticket existente com os novos logs de execução. Se a instituição obtiver sucesso em todos os módulos de teste, o ticket é fechado automaticamente com uma nota de sucesso.Os testes DCR realizados no ambiente de produção estão acessíveis no [Motor de Conformidade](https://web.conformance.directory.openbankingbrasil.org.br/) regular, permitindo que as instituições os executem no ambiente de Sandbox para correção de problemas identificados na produção.Em caso de dúvidas ou problemas nos testes executados, a instituição deve abrir um novo ticket no Service Desk de conformidade, onde as questões serão analisadas pela equipe de conformidade.Ocasionalmente, a equipe do motor de conformidade pode adicionar notas aos tickets junto com os logs de execução, especificando comportamentos ou ações esperadas da instituição.
1. Página de Resultados
Após cada execução da FVP automática, são geradas páginas de resultados de testes com os *logs* das execuções e detalhamentos dos pontos de falha, semelhante aos resultados do motor de conformidade.A URL base da plataforma é [https://results.sandbox.directory.openbankingbrasil.org.br/TestID/index.html](https://results.sandbox.directory.openbankingbrasil.org.br/TestID/index.html), onde *TestID*é uma sequência aleatória de caracteres que será fornecida à instituição após a abertura de um ticket no Service Desk.Para acessar os resultados, é necessário autenticar-se com credenciais do Diretório Open Finance e estar vinculado a uma organização ativa. Também não há possibilidade de indexar os resultados de testes existentes, então a instituição deve salvar o URI do teste para futuras consultas. 
1. Clients de Teste
É responsabilidade da instituição realizar a checagem diária e a exclusão de eventuais *clients* remanescentes de execuções anteriores das FVPs. Com a introdução do novo *software statement*para testes de longa duração, cujos *clients* não devem ser deletados, aplicam-se as seguintes diretrizes:
- Software statements  cujos clients devem ser deletados: É mantida a necessidade da checagem diária e deleção dos  clients  remanescentes associados aos seguintes SSIDs: bcc3ba64-faf5-456c-a162-8fef7ee67170; bc97b8f0-cae0-4f2f-9978-d93f0e56a833; 70ee2970-038b-44d6-9300-d3af3a890154; 21ef921f-7d9f-4fa5-afae-d24545d6c880; f61e3065-ca7b-4982-8ff5-86dff43ece63; d52c9049-a67b-432f-bdde-fe613099f83b
- Software statements  cujos clients não devem ser deletados: O  client  não deverá ser deletado, uma vez que o mesmo clientId será usado em novos testes. SSIDs: 44ffd907-2318-496b-ad91-07bbb0a836da; 25402dd0-7553-477b-b635-b9ce79da18f2.
Reforçamos que, para os *software statements*cujos *clients* devem ser deletados, mantem-se a sugestão de realizar a exclusão preferencialmente entre **22h e 6h**, a fim de evitar interferências na execução dos testes conduzidos pela Associação Open Finance.
1. Exemplo de Configuração de Teste – Sandbox
Os testes executados pela FVP automática também podem ser visualizados no motor de conformidade de Sandbox e na FVP manual. Esses testes estão incluídos no plano de testes chamado: "*Functional Tests* for DCR - FVP 1.0 - *Live Tests*". Abaixo está uma configuração de exemplo que inclui credenciais geradas no Sandbox do Diretório e executa testes contra o *Mock Bank*, com certificados gerados em maio de 2024.Exemplo de Configuração de Sandbox ([Link de um exemplo](https://gitlab.com/raidiam-conformance/open-finance/certification/-/wikis/Automated-Production-Tests#test-plan-list)[C:\Users\Chicago\AppData\Roaming\Microsoft\Word\gitlab.com\raidiam-conformance\open-finance\certification\-\wikis\Automated-Production-Tests - test-plan-list](file:///C:/Users/Chicago/AppData/Roaming/Microsoft/Word/gitlab.com/raidiam-conformance/open-finance/certification/-/wikis/Automated-Production-Tests%23test-plan-list))Observe que os testes da FVP Automática foram projetados para serem executados em produção. Os certificados e chaves utilizados no exemplo acima diferem dos utilizados em produção. Portanto, não há garantia de que a aprovação nos testes de Sandbox resultará em aprovação na execução automatizada em produção.
1. Interação com o Diretório
Para iniciar a execução dos testes automatizados, a FVP interroga a API pública do Diretório, analisa a resposta JSON e extrai informações sobre todas as organizações registradas no diretório.Essas informações incluem:
- ID da Organização
- Nome da Organização
- Lista de todos os servidores de autorização registrados sob esta organização
- URL do Well-Known
- Customer Friendly Name
- ID do Authorisation Server
- URI de Consents
Após extrair todas as informações do diretório, a FVP interroga e processa os *endpoints Well-Known* de cada servidor de autorização nesta parte da rotina. Em seguida, as informações obtidas são atualizadas.As informações incluem:
- Métodos de autorização suportados (chave privada ou MTLS)
- Se PAR é suportado, e se é obrigatório
Com todas essas informações em mãos, uma série de planos de teste será criada para cada cenário potencial de teste válido. Aqui, o número de planos válidos por servidor de autorização depende do número de credenciais X variantes de autorização suportadas.Baseado nas informações extraídas, a FVP cria planos de teste para cada cenário potencial. O número de planos válidos por servidores de autorização depende do número de credenciais X *supported_authorisation_variants,* por exemplo, se um AS suporta duas variantes de autorização e os testes são feitos com dois tipos de *software statments*, 4 planos de teste válidos são gerados.

---

# Guia de Operação da Ferramenta de Validação em Produção > FVP Manual

---
id: 553255015
title: FVP Manual
version: 12
modified: 2026-01-06T18:24:46.802Z
url: /spaces/OF/pages/553255015/FVP+Manual
---

## Introdução
A FVP Manual tem como objetivo validar, de forma controlada e em ambiente produtivo, se os fluxos e as respostas das APIs implementadas pelas instituições participantes estão em conformidade com os padrões técnicos definidos pelo Open Finance Brasil. Para isso, os testes exigem a autenticação e o consentimento do usuário, garantindo que os comportamentos esperados estejam sendo corretamente executados em ambiente de produção das instituições.Os testes realizados na FVP (Ferramenta de validação em produção) utilizam dados reais dos usuários em produção, tanto para o compartilhamento de dados quanto para as iniciações de transações de pagamentos. Por padrão, as informações relativas às execuções ficam disponibilizadas nos próprios logs de execução dos testes, sendo deletados da ferramenta após 1 hora do início do teste. Caso os logs de execução sejam baixados, eles estarão com informações sensíveis do usuário. Portanto, pedimos atenção redobrada dos usuários no cuidado com o manuseio e compartilhamento desses arquivos, especialmente quando realizados testes em contas de uso pessoal.Neste página, você encontrará os seguinte tópicos:
- 1 - Diferença entre FVP Manual - Testes restritos e Testes abertos : Diferença entre os planos de testes e responsabilidades de execução;
- 2 - FVP Manual - Testes Abertos : O que é a FVP Manual - Testes Abertos, funcionamento dos ciclos e as responsabilidades de execução dos ciclos pelas instituições;
- 3 - FVP Manual - Testes Restritos : O que é a FVP Manual - Testes Restritos, funcionamento dos ciclos e módulos de testes que serão validados em produção pela estrutura; Testes de longa duração : Funcionamento e validação dos testes de longa duração;
- 4 - Configurando e executando testes : Passo-a-passo para configuração e execução da FVP Manual pelas instituições (Testes Abertos), além de um detalhamento para diferenciação de um teste relacionado à uma pessoa física (PF) ou à uma pessoa jurídica (PJ).

## 1 - Diferença entre FVP Manual - Testes restritos e Testes abertos
Em geral, a FVP Manual - Testes Restritos representa um conjunto de testes (planos de testes) que podem realizados exclusivamente por membros da Associação Open Finance Brasil e fornecedores, enquanto os planos de testes relacionados à FVP Manual - Testes Abertos podem ser executados pelas próprias instituições.As execuções dos testes da FVP Manual ocorrem em ciclos bimestrais, e a responsabilidade de execução da ferramenta depende das contas abertos pelo fornecedor contratado pela estrutura para execução da FVP Manual:
- FVP Manual - Testes Abertos : São planos de testes da FVP acessíveis às instituições ( Open tests ). Caso o fornecedor não possua conta aberta na marca para execução da FVP Manual, a responsabilidade de execução dos testes na FVP Manual - Testes Abertos para o servidor é de responsabilidade da própria instituição .
- FVP Manual - Testes Restritos : São planos de testes da FVP exclusivos à estrutura ( Restricted test plans ). Caso o fornecedor possua conta aberta na marca para execução da FVP Manual, a responsabilidade de execução dos testes na FVP Manual - Testes Restritos para o servidor é de responsabilidade da estrutura .
A relação das contas abertas pelo fornecedor, bem como a responsabilidade de execução bimestral para cada servidor, pode ser encontrada no [Dashboard da FVP Manual - Relação de Contas Abertas](https://sa-east-1.quicksight.aws.amazon.com/sn/accounts/471112653989/dashboards/c31415b5-e3ca-4a60-adfd-fa5856538c9d?directory_alias=openfinance-brasil).
## 2 - FVP Manual - Testes Abertos
Os Testes Abertos permitem que instituições realizem testes em produção em seus próprios servidores, restringindo o acesso para usuários da mesma organização e evitando interferências externas. Para o devido acesso, configuração e execução dos testes da FVP, consulte a seção *“4 - Configurando e executando testes“*.Os ciclos de execução da FVP Manual obedecem um ciclo bimestral, conforme cronograma de execução abaixo: Dentro de cada ciclo bimestral acima compartilhado, é esperado que as instituições obtenham sucesso nos testes da FVP Manual - Testes Abertos. Os servidores, segmentos e testes que devem obter sucesso em cada ciclo, dependem dos seguintes critérios :
- Servidor : Marcas (servidores) em que o fornecedor contratado não possua conta aberta, a responsabilidade de obtenção de sucesso é da própria instituição, caso esse que caracteriza a necessidade de execução da FVP Manual - Testes Abertos
- Segmento suportado (PF e/ou PJ) : Para cada segmento suportado pelo servidor (PF e/ou PJ), a instituição deverá obter sucesso nos testes, realizando execuções que são caracterizadas como usuários PF ou PJ. A identificação dos segmentos suportados por cada servidor é baseada nas flags de cada servidor no diretório dos participantes: “ Suporta contas PF ” e “ Suporta contas PJ “
- APIs Publicadas : De acordo com as APIs publicadas em cada servidor, serão exigidos sucessos nos testes relativos à essas APIs. A relação de planos e módulos de testes cobrados de acordo com cada API publicada está melhor descrita abaixo.
Nota: As novas instituições participantes de compartilhamento de dados (em *onboarding*) estão dispensadas do ciclo de Agosto/Setembro da FVP Manual - Testes Abertos ou Restritos.Segue abaixo a lista de planos e módulos de testes da FVP em que os servidores das instituições deverão obter sucesso completo a cada ciclo bimestral, de acordo com as APIs publicadas em cada servidor:
- API Pagamentos Automáticos v2.2.0 - Pix Automático : Criação e validação de consentimento, com realização de 2 pagamentos Plano de teste: Production Functional Tests for Automatic Pix Payments - API Version 2.2 Módulo de teste a ser executado: fvp_automatic-payments_api_automatic-pix-semanal-core_open_test-module_v2-2
- API Pagamentos Automáticos v2.2.0 - Transferências Inteligentes : Criação e validação de consentimento, com realização de 2 pagamentos: Plano de teste: Production Functional Tests for Automatic Sweeping Payments - API Version 2.2 Módulo de teste a ser executado: fvp_automatic-payments_api_sweeping-accounts-core_test-module_v2-2
- API Dados do cliente : Criação de consentimento com prazo indeterminado e chamada de todas as API de Compartilhamento de Dados, a depender das publicações da instituição: Plano de teste: Production Functional Tests for Customer Data Happy Path - API Version 3 Módulo de teste a ser executado: fvp-customer_data_unique_happy_path_test-module
- API Pagamentos v4.0.0 : Criação, sem cancelamento, de 2 agendamentos customizados: D+1 e D+2: Plano de teste: Production Functional Tests for Payments E2E - API Version 4 Módulo de teste a ser executado: fvp-payments_api_recurring-payments-custom-not-cancelled_open_test-module_v4

## 3 - FVP Manual - Testes Restritos
Caso o fornecedor contratado pela estrutura possua conta aberta em sua instituição, o próprio fornecedor é quem será responsável pela execução bimestral na FVP Manual - Testes Restritos. Os Testes Restritos (*Restricted test plan*) possuem acesso exclusivo pela própria estrutura do Open Finance Brasil.Nos ciclos bimestrais de execução da FVP Manual - Testes restritos, caso seja identificada uma falha durante a exeucução dos servidores das instituições, um ticket com as evidências das falhas será direcionado às instituições via *Service Desk*. Para que o ticket seja encerrado, uma reexecução com sucesso do módulo de teste da FVP deve ser obtida exclusivamente pelo fornecedor responsável pela execução dos testes. Para solicitações de pedidos de reexecução, um novo chamado deve ser aberto na categoria: Requisição > Reexecução > FVP Manual - Testes restritos. Para mais informações sobre solicitações de reexecução ou contestações, acesse o [Fluxos de Reexecução e Contestação da FVP Manual – Testes Restritos](https://openfinancebrasil.atlassian.net/wiki/x/GQDtPg)Abaixo, conforme discussão e definição do Squad Sandbox, está detalhado o ciclo vigente da FVP Manual - Testes Restritos, relativo ao ciclo de Dezembro-25/Janeiro-26:
### Testes de longa duração
Os testes de longa duração, presentes apenas na FVP Manual – Testes Restritos, têm como objetivo validar os comportamentos e etapas que ocorrem em dias posteriores à execução inicial do teste. Esses casos são aplicáveis principalmente em fluxos que envolvem validação da liquidação de pagamentos futuros, tentativas de retry automáticas, ou outras ações que não se encerram imediatamente após o teste inicial.Visto que os testes de longa duração exigem validações em dias seguintes à primeira execução com sucesso, como a confirmação de uma liquidação, o sucesso em uma primeira etapa de execução não significa que o teste foi concluído com sucesso. O ticket de notificação dos testes de longa duração apenas serão encerrados quando todas as etapas subsequentes do fluxo forem concluídas com sucesso. Assim, mesmo em pedidos de reexecução cujo no primeiro teste é obtido sucesso, é necessário aguardar o resultado completo dos testes de longa duração antes de considerar a pendência como resolvida. Até que a execução subsequente tenha um resultado, o SLA dos tickets serão pausados. Em caso de sucesso, o ticket será encerrado ou, em caso de falha, as novas evidências serão adicionadas ao ticket e o SLA será retomado.Para identificação dos testes de longa duração, seguem abaixo alguns exemplos de módulos de teste:
- Testes de validação da liquidação de Pix Automático: Teste 1 de 2: automatic-payments_api_automatic-pix-scheduling_1-2_test-module_v2 Teste 2 de 2: automatic-payments_api_automatic-pix-verification_2-2_test-module_v2
- Testes de validação de retrys de Pix Automático: Teste 1 de 3: automatic-payments_api_automatic-pix-scheduling-retry_1-3_test-module_v2 Teste 2 de 3: automatic-payments_api_automatic-pix-scheduling-retry_2-3_test-module_v2 Teste 3 de 3: automatic-payments_api_automatic-pix-scheduling-retry_3-3_test-module_v2
O detalhamento dos testes completos presentes na FVP Manual podem ser encontrados na [página do Gitlab](https://gitlab.com/raidiam-conformance/open-finance/certification/-/wikis/FVP-Restricted-Test-Plans) do fornecedor responsável pela ferramenta.
## 4 - Configurando e executando testes da FVP Manual
**a.      Criando uma conta no Diretório de Produção**Para acessar a plataforma, é necessário ter uma conta no [Ambiente de Produção do Diretório dos Participantes](https://web.directory.openbankingbrasil.org.br/organisations). As instruções para criação da conta estão no Capítulo 03 do Guia Operacional do Diretório de Participantes.A criação de uma conta envolve assinar os Termos e Condições e configurar um TOTP para futuro acesso. Se houver problemas não resolvidos pelo guia do usuário, é recomendado abrir um *ticket* de suporte no *Service Desk*.**b.     Escopo de acesso ao Diretório**Para obter acesso ao [ambiente da FVP](https://web.fvp.directory.openbankingbrasil.org.br/), o usuário deve ser designado com a função "PFVPC" no [Ambiente de Produção do Diretório](https://web.directory.openbankingbrasil.org.br/organisations), para a organização que será testada. Caso um usuário que não tenha o papel "PFVPC" no diretória tente executar a ferramente, uma mensagem de erro “403 - *FORBIDDEN”* aparecerá ao tentar fazer login na plataforma.Tendo-se em vista que o usuário que irá acessar a FVP deve autorizar consentimentos para as APIs do Open Finance que serão testadas, é necessário que o CPF registrado também tenha acesso aos recursos que serão testados na ferramenta.**c.      Acessando a plataforma**Para acessar a [plataforma da FVP](https://web.fvp.directory.openbankingbrasil.org.br/), o usuário (já com a devida permissão PFVPC) deve realizar o login através do Diretório dos participantes. Após autenticar-se, o usuário deve aceitar os termos e condições da FVP, que aparecerá a cada login na ferramenta.**d.      Criando um plano de testes**Após aceitar os termos, o usuário acessará uma interface similar à do motor de conformidade funcional. Nela, o plano de testes desejado deverá ser selecionado e as informações preenchidas conforme instruções abaixo, para testes de Pessoa Física (PF) ou Pessoa Jurídica (PJ):**Testes de Pessoa Física (PF)**Para executar os testes com caracterização de Pessoa Física (PF), o usuário deverá fornecer:
1. Alias : Deve corresponder ao orgId da organização
2. Authorisation Server ID : Authorisation Server ID que será testado. O Authorisation Server ID deverá estar registrado no orgId mencionado no campo Alias
3. BrazilCpf: CPF do usuário atrelado ao usuário logado, o com o devido acesso de PFVPC à organização no diretório dos participantes, conforme mencionado no tópico “Configurando e executando testes”.
4. A depender do plano de testes executado, outras informações deverão ser fornecidas, como debtorAccount ou creditorAccount
Segue abaixo modelo de configuração base de um plano de testes da FVP Manual para um teste para Pessoa Física (PF):Se o CPF ou o *Authorisation Server ID* fornecidos não corresponderem ao do PFVPC cadastrado no diretório dos participantes, a mensagem abaixo será exibida, indicando que a criação do plano de testes não poderá ser realizada.**Testes de Pessoa Jurídica (PJ)**Para executar os testes com caracterização de Pessoa Jurídica (PJ), o usuário deverá fornecer:
- Alias : Deve corresponder ao orgId da organização
- Authorisation Server ID : Authorisation Server ID que será testado. O Authorisation Server ID deverá estar registrado no orgId mencionado no campo Alias
- BrazilCpf: CPF do usuário atrelado ao usuário logado, o com o devido acesso de PFVPC à organização no diretório dos participantes, conforme mencionado no tópico “Configurando e executando testes”.
- BrazilCnpj : CNPJ cujo o CPF fornecido possua acesso à conta no servidor testado.
- A depender do plano de testes executado, outras informações deverão ser fornecidas, como debtorAccount ou creditorAccount
Segue abaixo modelo de configuração base de um plano de testes da FVP Manual para um teste para Pessoa Jurídica (PJ):

---

# Guia de Operação da Ferramenta de Validação em Produção > Fluxos de Reexecução e Contestação da FVP Manual – Testes Restritos

---
id: 1055719449
title: Fluxos de Reexecução e Contestação da FVP Manual – Testes Restritos
version: 2
modified: 2025-12-04T20:49:37.187Z
url: /spaces/OF/pages/1055719449/Fluxos+de+Reexecu+o+e+Contesta+o+da+FVP+Manual+Testes+Restritos
---

# Introdução
A Ferramenta de Validação em Produção (FVP) Manual – Testes Restritos é utilizada para verificar periodicamente a conformidade das implementações técnicas, em ambiente produtivo das instituições. Quando uma instituição é notificada de uma falha em um teste da FVP Manual – Testes Restritos (ou seja, recebe um ticket de notificação comunicando a falha), existem dois caminhos possíveis a seguir para resolver a situação: o **fluxo de Reexecução** ou o **fluxo de Contestação**. Esta documentação descreve cada fluxo, indicando quando e como utilizar cada um deles.As instituições devem utilizar o fluxo apropriado de acordo com o motivo da falha identificada no ticket de notificação:
- O Fluxo de Reexecução deve ser seguido quando a instituição identificar que a falha ocorreu devido a um problema em sua própria implementação ou ambiente, devendo corrigi-lo e, após isso, solicitar uma nova execução pela Associação.
- O Fluxo de Contestação deve ser utilizado quando a instituição acreditar que a falha reportada não foi causada por falha em sua implementação, mas sim por um erro da ferramenta de teste ou por alguma falha operacional na execução do teste.
Abaixo, são apresentadas as definições de alguns termos e detalhamos cada um dos fluxos, incluindo exemplos práticos de utilização.**Importante:** Sempre selecione a categoria correta ao abrir um chamado no Service Desk do Open Finance. Pedidos de contestação feitos na categoria de reexecução (ou vice-versa) **não serão atendidos** e serão encerrados sem seu devido atendimento. Certifique-se de escolher “Reexecução” apenas quando desejar uma nova execução dos testes após corrigir sua implementação, e “Contestação” somente quando desejar questionar o resultado devido a um possível erro da ferramenta ou do processo de teste.Para melhor compreensão, seguem as definições de alguns termos utilizados no contexto dos fluxos de reexecução e contestação:
- Ticket de notificação: é o chamado aberto pela própria Associação Open Finance Brasil (via Service Desk) para notificar a instituição participante de que uma execução dos testes da FVP Manual – Testes Restritos resultou em falha. Este ticket de notificação inclui evidências da falha identificada (logs de falha, descrições do erro, capturas de tela etc.) e permanece aberto até que uma execução com sucesso seja realizada pela própria Associação.
- Ticket de reexecução: é o chamado aberto pela instituição para solicitar uma nova execução (reteste) do módulo de teste que falhou. A abertura é feita no Service Desk, na categoria apropriada (“Requisição > Reexecução > FVP Manual – Testes Restritos”). No primeiro pedido de reexecução, a instituição deve referenciar o número do ticket de notificação original. Em casos de múltiplas reexecuções (ver Fluxo de Reexecução adiante), se uma reexecução anterior também falhar, um novo ticket de reexecução deverá ser aberto referenciando o ticket de reexecução anterior , e não mais o ticket de notificação inicial.
- Ticket de contestação: é o chamado aberto pela instituição para contestar o resultado de um teste da FVP Manual – Testes Restritos. A abertura é feita no Service Desk na categoria “Requisição > Contestação > FVP Manual – Testes Restritos”. No ticket de contestação, a instituição deve informar o número do ticket de notificação relacionado e indicar o tipo de falha que está sendo contestada (vide falha técnica vs falha operacional ). Em casos de múltiplas reexecuções, se uma reexecução anterior também falhar, um novo ticket de reexecução deverá ser aberto referenciando o  ticket de reexecução anterior , e não mais o ticket de notificação inicial. O ticket de contestação será analisado pela Estrutura do Open Finance, que decidirá se a contestação procede ou não. Os tickets de contestação poderão ser classificados pela instituição da seguinte maneira: Falha técnica (erro técnico): refere-se a uma falha causada por alguma inconsistência ou bug na própria ferramenta de teste (FVP). Falha operacional (erro operacional): refere-se a uma falha decorrente de problemas no processo de execução ou notificação do teste . São situações em que a execução não ocorreu como deveria por questões operacionais ou de configuração. Alguns exemplos de falha operacional são: Parâmetros de teste inválidos ou incorretos, ausência de evidências anexadas no ticket de notificação da falha ou saldo insuficiente na conta utilizada para um cenário de pagamento durante o teste, resultando em falha que não está ligada a uma falha na implementação da API da instituição.

# Fluxo de Reexecução
O fluxo de reexecução deve ser utilizado quando a instituição, ao analisar a falha reportada no ticket de notificação, conclui que é necessária alguma **correção em sua implementação ou ambiente** para atender aos requisitos do Open Finance. Em resumo, a reexecução é apropriada quando a falha indica uma não conformidade real no sistema da instituição, a qual precisa ser ajustada. A seguir, detalhamos os passos do fluxo de reexecução dos tickes da FVP Manual - Testes Restritos:
1. Notificação da falha: A instituição recebe um ticket de notificação informando que sua execução dos testes da FVP Manual – Testes Restritos apresentou falhas. O ticket contém as evidências do problema.
2. Análise e correção interna: A equipe da instituição analisa a falha apontada e identifica a causa em sua implementação ou configuração. Em seguida, são feitos os devidos ajustes ou correções no sistema (por exemplo, correção de um bug na API, ajustes de configurações de sistemas etc.).
3. Solicitação de reexecução: Após corrigir o problema, a instituição deve abrir um ticket de reexecução no Service Desk, seguindo o caminho Requisição > Reexecução > FVP Manual – Testes Restritos . Nesse chamado, é preciso informar o número do ticket de notificação original da falha e detalhar, quando necessário, as correções realizadas ou o contexto da solicitação.
4. Pausa do SLA e nova execução do teste: Ao receber o pedido de reexecução, o ticket de notificação terá seu SLA pausado .
5. Avaliação do resultado da reexecução: Se o novo teste passar com sucesso na reexecução, a falha é considerada resolvida. O ticket de notificação original será então encerrado . Importante: Os testes de longa duração são testes que fazem validações em dias posteriores (como liquidações de pagamentos e novas tentativas de pagamento, como retrys ). Portanto, um sucesso parcial (por exemplo, sucesso apenas no primeiro teste, realizado manualmente pelo fornecedor) em um pedido de reexecução não garante o encerramento do ticket de notificação, pois é necessário que todos os testes seguintes, que serão realizados automaticamente pela ferramenta, tenham sucesso. (Mais informações sobre os testes de longa duração estão disponíveis na página "FVP Manual")
6. Se a falha persistir ou surgirem novas falhas na reexecução: a Associação atualizará o ticket de notificação original anexando as novas evidências da falha ocorrida na reexecução e retomará o SLA. Nesse caso, a instituição deverá retornar ao passo 2 (analisar e corrigir) considerando as novas falhas evidenciadas.

# Fluxo de Contestação
O fluxo de contestação deve ser utilizado quando a instituição entende que a falha reportada **não se deve a um erro de sua implementação**, mas possivelmente a um **equívoco na execução ou problema nos testes**. Em outras palavras, a contestação deverá ser utilizada quando a instituição suspeita de falso negativo na detecção da falha. Contestações de resultado podem ser ocasionados por **erro da ferramenta (falha técnica)** ou por um **erro no processo de execução/notificação (falha operacional)**, conforme definidos anteriormente. O objetivo da contestação é solicitar à Associação do Open Finance uma revisão do resultado do teste ou a correção de algum fator externo. A seguir, detalhamos os passos do fluxo de contestação dos tickes da FVP Manual - Testes Restritos:
1. Notificação da falha: Assim como no caso anterior, tudo começa com a instituição recebendo um ticket de notificação de falha nos testes da FVP Manual – Testes Restritos, contendo as evidências do problema.

1. Análise interna: A equipe da instituição analisa as evidências e o contexto da falha. Nesta etapa, ao invés de encontrar um defeito no sistema próprio, a instituição identifica que a falha pode ter sido causada por falhas na ferramenta ou na execução. Por exemplo, ao verificar os logs, a instituição nota um comportamento inesperado da ferramenta de teste ou percebe que informações ausentes podem ter sido causadas por parâmetros incorretos fornecidos no teste.

1. Solicitação de contestação: Por se tratar de um erro da ferramenta ou do processo, a instituição abre um ticket de contestação no Service Desk, seguindo o caminho Requisição > Contestação > FVP Manual – Testes Restritos . No chamado de contestação, deve-se: Referenciar o número do ticket de notificação da falha. Lembre-se: caso já tenha ocorrido uma tentativa de reexecução anterior que também falhou, informe o número do ticket de reexecução anterior, ao invés do ticket de notificação, conforme as orientações acima; Informar o tipo de falha que está sendo contestada, selecionando “Erro Técnico” ou “Erro Operacional” conforme a natureza do problema identificado; Descrever claramente por que a instituição entende que o resultado do teste está equivocado ou o que foi realizado errado no processo. Inclua detalhes da evidência e qualquer dado adicional que sustente a contestação.
2. Avaliação da contestação pela Estrutura: Ao receber o pedido de contestação, a Estrutura do Open Finance (e/ou a equipe técnica responsável pela FVP, como o provedor dos testes) irá analisar as evidências e a justificativa apresentadas. O ticket de notificação original terá seu SLA pausado durante essa análise, já que a resolução depende de verificação da Associação. A análise pode resultar em dois cenários: Contestação procedente (aceita) ou Contestação improcedente (negada).

1. Contestação procedente (aceita): Se a equipe concluir que de fato houve um erro na ferramenta ou no processo do teste que invalida o resultado: No caso de contestações de tickets de notificação originais, eles serão cancelados . Após o cancelamento do ticket de notificação, a Estrutura do Open Finance realizará uma nova execução do teste. Caso ocorra uma nova falha, um novo ticket de notificação será aberto à instituição; No caso de contestações de tickets de reexecução , o ticket de notificação original não será encerrado ou cancelado, permanecendo em aberto. Para esses casos, será adicionado ao ticket original o tempo compreendido entre o fechamento do ticket de reexecução e a abertura do ticket de contestação. No caso de falha técnica confirmada: o caso é encaminhado para correção da ferramenta de teste. O ticket de notificação permanecerá aberto (em status de aguardando correção) enquanto a falha na ferramenta é corrigida pela Estrutura. Após a correção do problema técnico ou operacional identificado, a Estrutura realizará uma nova execução do teste para verificar se tudo está correto. Essa execução é iniciada pela própria Estrutura como parte da validação da contestação, não exigindo que a instituição abra um pedido de reexecução. Se o teste tiver novas falhas identificadas, um novo ticket de notificação será aberto à instituição.
2. Contestação improcedente (negada): Se a análise concluir que não houve erro na ferramenta ou no processo, isto é, a falha apontada realmente indica um problema na implementação da instituição: O ticket de contestação será recusado . A Estrutura atualizará o chamado informando os motivos (por exemplo, esclarecendo que os testes funcionaram como esperado, com o devido embasamento técnico, e que a falha demonstra uma não conformidade real da instituição). O ticket de notificação original terá seu SLA retomado e continuará aberto aguardando uma nova solicitação de reexecução. A instituição deve então providenciar as correções necessárias em seu sistema e posteriormente solicitar uma reexecução conforme o fluxo já descrito anteriormente, para tentar obter sucesso nos testes.
3. Encerramento: Para contestação procedente (aceita), o ticket de notificação será cancelado. Se a contestação for improcedente (negada), o encerramento ocorrerá somente após a instituição efetuar correções e conseguir uma execução bem-sucedida via fluxo de reexecução.
**Nota**: A cada nova solicitação de contestação, utilize sempre o número do último ticket de reexecução falhado como referência, conforme mencionado. Apenas o último ticket de reexecução associado a um ticket de notificação pode ser contestado. Contestações de tickets de reexecuções anteriores não serão aceitas. Não abra um novo pedido referenciando novamente o ticket de notificação após já ter ocorrido uma reexecução, pois isso pode causar confusão no rastreamento do caso.

---

# Guia de Operação da Ferramenta de Validação em Produção > Plano de testes

---
id: 553255065
title: Plano de testes
version: 3
modified: 2025-02-07T15:57:22.994Z
url: /spaces/OF/pages/553255065/Plano+de+testes
---

- FVP Manual: Testes Restritos ( ) Testes Abertos ( )
- FVP Automática ( )

---

# Guia de Operação da Ferramenta de Validação em Produção > Problemas e dúvidas comuns

---
id: 553255097
title: Problemas e dúvidas comuns
version: 3
modified: 2024-10-31T17:54:02.246Z
url: /spaces/OF/pages/553255097/Problemas+e+d+vidas+comuns
---

**Dúvidas comuns sobre a ferramenta****Pergunta**: O que é a FVP Manual Restrita e qual a diferença dela para a FVP Manual Aberta e a FVP Automática?**Resposta**: A FVP Automática é executada diariamente de forma automática. Nela, são realizados testes de DCR, DCM e testes de todas as fases que vão até a etapa de autorização de consentimento. A FVP Manual, diferentemente da FVP Automática, inclui testes que realizam a jornada completa de compartilhamento de dados e de iniciação de pagamentos. Ou seja, por necessitarem de uma etapa de interação do usuário para autorização do consentimento e realização de iniciações de pagamento, a interação manual do usuário é necessária para a finalização do teste. Além disso, o que diferencia a FVP Manual Aberta da FVP Manual Restrita são alguns poucos módulos de testes que estão disponíveis para a estrutura do Open Finance Brasil como, por exemplo, um teste para a validação dos limites do usuário. **Pergunta**: Recebi a mensagem “Failed to fetch” na ferramenta, o que isso significa? **Resposta**: Erros com a mensagem “Failed to fetch” estão relacionados à timeout da sessão da FVP, que é um erro esperado para sessões longas ou após transições de abas no navegador. Esse erro não impede a execução do módulo de testes, ou seja, basta recarregar a página para seguir acompanhando normalmente a sua execução.**Dúvidas comuns sobre as notificações e encerramento dos tickets****Pergunta**: Recebi um ticket de notificação da FVP Manual Restrita, porém não consigo comentar ou encerrar ele. O que devo fazer?**Resposta**: Os tickets relativos às notificações da FVP Manual Restrita, de fato, não podem ser comentados ou encerrados pela instituição. Para que o ticket seja encerrado, uma reexecução com sucesso do módulo de teste da FVP deve ser obtida exclusivamente pelo fornecedor responsável pela execução dos testes. Para solicitações de pedidos de reexecução, um novo chamado deve ser aberto na categoria: Requisição > Reexecução > FVP Manual - Testes restritos. Para esclarecimento de dúvidas com relação à FVP, um chamado deve ser aberto na categoria: Requisições > Solicitação de Informações > Conformidade > Ferramenta de Validação em Produção**Pergunta**: Solicitei um pedido de reexecução. Como não possuo nenhuma atuação até o retorno do resultado, o SLA do meu ticket será impactado?**Resposta**: Não, o SLA do ticket não será impactado após solicitação de pedidos de reexecução. A partir do momento em que um pedido de reexecução é aberto, o ticket mencionado terá seu status alterado para “Aguardando Requisitante - Essencial”. Tendo-se em vista que a instituição não possui nenhuma ação a ser realizada enquanto aguarda o retorno da reexecução, a cada 24h o ticket ganhará 24h adicionais de SLA. Após encerramento do pedido de reexecução, o status voltará normalmente para “Encaminhado N2 Atendimento”, recontando, a partir desse momento, o SLA normalmente.**Pergunta**: Ao invés dos logs, recebi como evidência um JSON com a mensagem “DCR Error – Failure on generating a client”, o que isso quer dizer?**Resposta**: Em cada execução de testes da FVP, um cliente (client) é sempre criado no início e excluído ao final. Esse processo de registro é chamado de DCR (Dynamic Client Registration). Quando ocorre uma falha de DCR no início dos testes, o módulo de teste não consegue ser executado, pois a geração do cliente é fundamental para dar início ao teste.Atualmente, na FVP, cada módulo de teste inclui uma etapa prévia de DCR, onde um cliente é registrado para o servidor em teste. Ao final do teste, esse cliente é excluído. Isso acontece porque, conforme os parâmetros de infraestrutura acordados, a FVP não pode reter as informações do cliente. Cada teste deve excluir o cliente criado para evitar falhas em tentativas subsequentes de DCR, pois os servidores podem rejeitar múltiplos registros do mesmo cliente. Essa abordagem é necessária devido às especificações da OPF, que permitem o registro de apenas um cliente por software statement.Quando ocorre uma falha durante a etapa de pré-DCR, enquanto o módulo de teste está sendo configurado, o módulo não chega a ser iniciado e uma mensagem de erro é retornada: "DCR Error – Failure on generating a client". Junto com essa mensagem, normalmente é gerado um log detalhando o motivo da falha no processo de registro, além de um botão para baixar esses logs. Enquanto o DCR falhar, o módulo de teste não poderá ser criado, pois ele depende da geração do cliente para ser executado.**Dúvidas comuns sobre o comportamento dos testes****Pergunta**: O teste não chegou até o final, visto que o status está como “INTERRUPTED” e os logs apresentam a falha “Test was interrupted before it could complete”, o que isso significa?**Resposta**: A mensagem de erro “Test was interrupted before it could complete" pode ser gerada pelos seguintes motivos:Falha bloqueante: Durante a execução do teste, a FVP identificou uma falha que impossibilita a continuidade das próximas etapas de validação do módulo. Isso significa que o teste não pôde ser finalizado. Um exemplo comum é uma falha no fluxo de autorização. O código de autorização é essencial para obter o token de acesso, que permite a realização de requisições para as APIs. Quando ocorre uma falha nessa etapa, o teste é geralmente interrompido. Interrupção espontânea: Durante a execução, o responsável pela criação do teste pode, a qualquer momento, acionar o botão "stop", o que interrompe o teste. Essa interrupção pode ocorrer por diversos motivos, como a identificação de falhas no ambiente da detentora de conta que não geram um "retorno de erro" para a FVP. Nesses casos, as falhas não aparecem nos logs, deixando o usuário sem alternativa a não ser interromper manualmente o teste. Para obter mais detalhes sobre as falhas observadas no ambiente da detentora de conta, é possível utilizar as informações das requisições presentes nos logs, como o xfapi-interaction-id, para identificar o erro diretamente no ambiente da detentora.**Pergunta**: O motor realizou chamadas de “Delete” de consentimentos ou pagamentos no momento indevido do teste, por quê?**Resposta**: A chamada de "Delete" de consentimentos ou pagamentos pode ocorrer pelos seguintes motivos:
1. Como parte do processo de "Cleanup" final : Após a execução do fluxo do módulo de testes, durante a sua finalização, seja com sucesso ou falha, a FVP inicia a etapa chamada "Cleanup". Nessa fase, os recursos criados durante o teste são deletados para garantir que não permaneçam armazenados nos bancos de dados da instituição detentora. Isso evita o acúmulo de dados de teste desnecessários.
2. Como "Cleanup" preventivo : Caso o teste encontre uma falha crítica durante sua execução, a etapa de "Cleanup" é acionada de forma preventiva, mesmo antes da conclusão do teste. Isso é feito para garantir que dados temporários ou indesejados não fiquem armazenados nos sistemas das detentoras após a execução do teste.
Importante: se o teste falhou antes da criação de um consentimento ou pagamento, a etapa de "Cleanup" pode gerar um erro, já que não haverá recurso a ser deletado. Contudo, nesses casos, deve-se considerar a primeira falha que interrompeu o teste e acionou o "Cleanup". A etapa de "Cleanup" geralmente inclui ações como "Unregister dynamically registered client", "Deleting consent" e "Patch consents endpoint".**Pergunta**: Após execução do teste, baixei os logs e eles vieram vazios, por quê?**Resposta**: Cinco minutos após o término da execução, as informações são apagadas da FVP. Por razões de segurança, a FVP não pode armazenar as informações usadas durante o teste. Assim, após esse período de 5 minutos, os logs da FVP são excluídos automaticamente. Embora eles fiquem visíveis inicialmente na página, depois de 5 minutos, se for feito um reload da página, os logs também não estarão mais disponíveis. Desta maneira, o download dos logs da FVP deve ser realizado em até 5 minutos após a finalização do teste. Caso seja feito posteriormente a esse tempo, o arquivo de logs estará vazio.**Dúvidas comuns sobre as mensagens de erro dos testes**Para apoiar as instituições na identificação e correção das falhas identificadas pela FVP, abaixo estão listadas algumas mensagens de erro que são mais frequentemente encontradas nos logs, juntamente com seu detalhamento do porquê ele ocorre e como solucioná-lo:
1. 40x na requisição do DCR - Client already present for this Software Statement on Server
**Problema**: O servidor não aceita um novo DCR porque já existe um client_id gerado para esse Software Statement. O client foi criado em um módulo de teste de DCR anterior e, devido a um problema no servidor, a solicitação de exclusão do registro foi recusada, resultando na não exclusão correta do client.**Solução**: Verifique o plano de teste e confirme se o problema com a solicitação DELETE ocorreu em algum dos módulos de teste existentes.a. Se positivo, identifique a causa do problema e implemente uma correção. Exclua manualmente o client criado usando a chave SoftwareStatementID fornecida neste documento.b. Se negativo, o problema de exclusão ocorreu em um teste anterior contra a instituição e não pode ser rastreado corretamente com as evidências fornecidas.Exclua manualmente o client criado usando a chave SoftwareStatementID fornecida neste documento e aguarde a próxima execução para avaliar a possível causa do problema na exclusão.
1. Test was unable to call the Consents API on test
**Problema**: No teste consents-bad-logged, não foi possível chamar a API POST Consents porque o URI da API de Consentimento não foi fornecido no plano de teste.**Solução**: Verifique no diretório se o Servidor de Autorização está registrado com uma API de Consentimentos válida para a Fase 3 e/ou Fase 2, dependendo da fase em que a instituição participa. Consulte o Guia Operacional do Diretório para registrar a API de Consentimentos no servidor.
1. DCR is not being accepeted because of missing optional fields on the request
**Problema**: O servidor recusa o DCR porque um campo opcional não foi incluído no corpo da solicitação.**Solução**: O servidor deve aplicar um padrão suportado para todos os campos opcionais, garantindo que a solicitação seja processada pela instituição.
1. Routine was unable to confirm within the well-known endpoint the supported token authentication methods Causas potenciais que podem ser:
**Causas potenciais que podem ser:**
- Well-Known utilizou certificados SSL inválidos, impedindo o acesso às informações.
- response_body não inclui private_key_jwt ou tls_client_auth no objeto token_endpoint_auth_methods_supported.
- O servidor negou acesso a FVP ao tentar verificar o conteúdo do endpoint WellKnown
**Solução:**
- Assegure-se de que o endpoint Well-Known está utilizando um certificado SSL EV válido de CA ou ICP-Brasil, conforme especificado na Documentação de Padrões de Certificado.
- Garanta que o retorno esteja em conformidade com o RFC8414.
- Verifique se o payload JSON retornado contém os métodos de autenticação de token esperados.

1. Server claims the authorization token is invalid or expired
**Problema**: O servidor não está aceitando tokens de acesso válidos. Algumas instituições identificaram um problema de sincronização no cache de tokens entre diferentes instâncias do authorisation server.**Solução**: Implementar uma estratégia de fallback para consultar o token no banco de dados quando não for encontrado no cache.
1. Failure when calling the directory endpoints - Token or Assertion
**Problema**: O diretório retornou um erro 50x ao chamar um de seus endpoints devido ao alto uso da plataforma durante o teste.**Solução**: Nenhuma mudança é necessária para a instituição, ignore os resultados do teste e aguarde uma nova execução.
1. Server returned that the client presented invalid certificates
**Problema**: Em todas as solicitações de DCR, o servidor testado está retornando credenciais do cliente emitidas como inválidas, resultando em falhas em todos os testes.**Solução**: O servidor não está reconhecendo o certificado emitido como válido. Certifique-se de que o API Gateway confia no certificado e na CA que emitiu este certificado.
1. State was passed in request, but is missing from response
**Problema**: Alguns casos de falha, como no caso da mensagem de erro “State was passed in request, but is missing from response”, ocorrem em redirecionamentos de volta à FVP. A causa dessa falha, após a finalização da jornada no ambiente da detentora, está relacionada ao fato de que, se o usuário que está realizando o teste não estiver logado no navegador padrão de seu dispositivo móvel, as informações transmitidas na URL de redirecionamento se perdem no momento em que o navegador solicita a autenticação. Isso ocorre pois o link de redirecionamento é único, ou seja, se ele for acessado uma vez, e a sessão do usuário não estiver ativa, o link se perde, resultando na falha do redirecionamento.**Solução**: Para execuções que são realizadas via leitura de QR Code, recomenda-se sempre realizar a autenticação em seus dispositivos móveis, no navegador em que será utilizado, previamente ao início ao início do teste. Isso garante que o fluxo de redirecionamento funcione corretamente e os parâmetros sejam transmitidos de forma adequada.

---

# Guia de Operação do Diretório Central > 02. Cadastrando reivindicações de domínio de autoridade

---
id: 941818484
title: 02. Cadastrando reivindicações de domínio de autoridade
version: 1
modified: 2025-05-03T04:21:34.378Z
url: /spaces/OF/pages/941818484/02.+Cadastrando+reivindica+es+de+dom+nio+de+autoridade
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

# Guia de Operação do Diretório Central > 03. Cadastrando reivindicações de autoridade

---
id: 941818522
title: 03. Cadastrando reivindicações de autoridade
version: 1
modified: 2025-05-03T04:21:35.273Z
url: /spaces/OF/pages/941818522/03.+Cadastrando+reivindica+es+de+autoridade
---

Esta seção explica as etapas para cadastrar reivindicações de autoridade e como adicionar usuários com suas respectivas funções que serão desempenhadas pela organização dentro do Open Finance.
## Detalhamento-das-Modalidades Detalhamento das Modalidades

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

# Guia de Operação do Diretório Central > 04. Registrando um usuário no Diretório

---
id: 941818599
title: 04. Registrando um usuário no Diretório
version: 1
modified: 2025-05-03T04:21:37.417Z
url: /spaces/OF/pages/941818599/04.+Registrando+um+usu+rio+no+Diret+rio
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
**1.** Caso você se o administrador da instituição e esteja configurando o termo de adesão ao Open Finance, será necessário selecionar os signatários do temo.**2.** Informe a quantidade de signatáfios e clique em `SALVAR`.**3.** Em seguida, você receberá por e-mail um documento via DocuSign.**4.** O código a ser inserido no DocuSign estará disponível em `"História TnC"`.**5.** Ao abrir o documento do DocuSign, você deverá indicar os representantes legais da organização.**6.** Os representantes receberão os e-mails do DocuSign para coletar as assinaturas e os documentos comprobatórios.**7.** O primeiro signatário precisará preencher o nome da Razão Social.**8.** Marcar o(s) tipo(s) de participação(ões) da instituição no Open Finance.**9.**E assinar o documento.

---

# Guia de Operação do Diretório Central > 05. Cadastrando contatos de notificação (2)

---
id: 941818846
title: 05. Cadastrando contatos de notificação (2)
version: 1
modified: 2025-05-03T04:21:46.053Z
url: /spaces/OF/pages/941818846/05.+Cadastrando+contatos+de+notifica+o+2
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

# Guia de Operação do Diretório Central > 06. Cadastrando administradores da organização

---
id: 941818897
title: 06. Cadastrando administradores da organização
version: 1
modified: 2025-05-03T04:21:47.113Z
url: /spaces/OF/pages/941818897/06.+Cadastrando+administradores+da+organiza+o
---

Esta seção explica as etapas necessárias para realizar o cadastro de um novo administrador da organização.
## Etapa 1: Cadastrando um Administrador da Organização

### Requisitos
**1.** No Diretório, localize e selecione a sua organização.**2.** Selecione o menu `Organisation Administrator`**e clique no botão `New Organisation Administrators`.**3.** Na janela `New Organisation Administrator`**preencha o campo do formulário. O slide a seguir apresenta cada um dos campos em mais detalhes.**4.** Clique no botão `Save`.**NOTA:**Somente administradores da organização podem cadastrar novos administradores.

---

# Guia de Operação do Diretório Central > 07. Criando certificados de transporte e assinatura em Sandbox

---
id: 941818944
title: 07. Criando certificados de transporte e assinatura em Sandbox
version: 1
modified: 2025-05-03T04:21:48.197Z
url: /spaces/OF/pages/941818944/07.+Criando+certificados+de+transporte+e+assinatura+em+Sandbox
---

Esta seção explica as etapas para criar uma solicitação de assinatura de certificado para certificados de transporte e assinatura que não foram emitidos por uma autoridade de certificação e para uso exclusivo em ambiente de Sandbox do Diretório.
## Etapa 1: Criando um Novo Certificado de Transporte

### Requisitos
**1.** Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, selecione a sua organização e no menu lateral clique em `Software Statements`**3.** No menu superior clique em `Software Statements Certificates` e clique no botão `New Certificate`.**4.** Na janela `New Certificate`, na caixa de seleção `Select Certificate Type` selecione a opção `BRCAC_2022`**e clique no botão**`Continue`*.***5.** No passo seguinte, é possível gerar automaticamente o CSR referente ao certificado via diretório. Para isso clique no botão Automatic config generation.**6.** Na janela `Generate certificate - BRCAC_2022`, edite as informações de forma que elas sejam idênticas as informações contidas no Diretório na página de detalhes da organização, conforme especificado no Padrão de Certificados e clique no botão `Next`.**7.** Clique no botão `Download` para baixar o arquivo `brcac.cnf` com as informações do certificado**8.** Copie o comando que aparece na tela e execute através do prompt de comando no caminho do arquivo `brcac.cnf`. para a geração do par `CSR` e `KEY`. Clique no botão `Continue`**9.** Selecione a opção `Upload CSR/PEM` e localize o `brcac.csr` gerado pela execução do passo anterior e clique no botão `Continue`.**10.**Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**11.**Na tela anterior de certificates, vá até actions e clique na seta de download. Salve o `<arquivo>.pem` em uma pasta local. 
## Etapa-2:-Criando-um-Novo-Certificado-de-Assinatura Etapa 2: Criando um Novo Certificado de Assinatura

### Requisitos
**1.** No Diretório, selecione a sua organização e no menu lateral clique em `Organisation Certificates`.**2.** Na janela `New Certificate`*,*na caixa de seleção `Select Certificate Type` selecione a opção `BRSEAL`**e clique no botão**`Continue`*.***3.** No passo seguinte, é possível gerar automaticamente o CSR referente ao certificado via diretório. Para isso clique no botão `Automatic config generation`.**4.** Na janela `Generate certificate - BRSEAL`, edite as informações de forma que elas sejam idênticas as informações contidas no Diretório na página de detalhes da organização, conforme especificado no Padrão de Certificados e clique no botão `Next`.**5.** Clique no botão `Download` para baixar o arquivo brseal.cnf com as informações do certificado**6.** Copie o comando que aparece na tela e execute através do prompt de comando no caminho do arquivo `brseal.cnf`. para a geração do par `CSR e KEY`. Clique no botão `Continue`**7.** Selecione a opção `Upload CSR/PEM` e localize o `brseal.cnf` gerado pela execução do passo anterior e clique no botão `Continue`.**8.** Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**9.** Na tela anterior de certificates, vá até `actions` e clique na seta de `download`. Salve o `<arquivo>.pem` em uma pasta local.

---

# Guia de Operação do Diretório Central > 08. Carregando certificados emitidos por autoridade de certificação em Produção

---
id: 941819091
title: 08. Carregando certificados emitidos por autoridade de certificação em Produção
version: 1
modified: 2025-05-03T04:21:52.944Z
url: /spaces/OF/pages/941819091/08.+Carregando+certificados+emitidos+por+autoridade+de+certifica+o+em+Produ+o
---

Esta seção explica as etapas para importar certificados que foram emitidos por uma autoridade de certificação e para uso exclusivo em ambiente de Produção do Diretório.
## Etapa 1: Carregando Certificado de Transporte

### Requisitos
**1.**Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, selecione a sua organização e Selecione o menu `Software Statements` .**3.** Na tela Software Statement , clique no botão `New Certificate`.**4.** Na janela `New Certificate`, na caixa de seleção `Select Certificate Type` selecione a opção `EXTERNAL BRCAC`**e clique no botão**`Continue`*.***5.** No passo seguinte, em `Generate CSR`*,* clique no botão `Continue`.**6.** Na opção `Upload CSR/PEM`, localize o arquivo em formato `.cer` ou `.pem` do certificado gerado junto a AC. **Para essa etapa garanta que nenhuma chave privada, arquivo em formato**`.key`**, será adicionada sob risco de exposição de credenciais.****7.** Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**8.** Uma nova entrada será fornecida na tela de certificados. Certifique que o novo certificado se encontra adicionado.
## Etapa-2:-Carregando-Certificado-de-Assinatura Etapa 2: Carregando Certificado de Assinatura

### Requisitos
**1.**No Diretório, selecione a sua organização e no menu lateral clique em `Organisations Certificate`*.***2.**Na janela `New Organisations Certificate`, na caixa de seleção `Select Certificate Type` selecione a opção `BRSEAL EXTERNAL`**e clique no botão**`Continue`*.***3.** No passo seguinte, em `Generate CSR`*,* clique no botão `Continue`.**4.** Na opção `Upload CSR/PEM`, localize o `<arquivo>.csr` e clique no botão `Continue`.**5.** Aguarde o carregamento do arquivo para o Diretório e no passo seguinte clique no botão `Done`.**6.** Na tela anterior em `Organisation Certificates`, vá até `actions` e clique na seta de `download`. Salve o `<arquivo>.pem` em uma pasta local.

---

# Guia de Operação do Diretório Central > 09. Cadastrando um Authorisation Server

---
id: 941819190
title: 09. Cadastrando um Authorisation Server
version: 1
modified: 2025-05-03T04:21:55.858Z
url: /spaces/OF/pages/941819190/09.+Cadastrando+um+Authorisation+Server
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
| `Description*` | | Esse é um texto de marcação onde deverá ser descrita a marca, trazendo informações adicionais para que o cidadão não tenha dúvidas sobre a escolha feita. Limite de caracteres: 256 (padrão do campo) Não deve ser permitido que a descrição traga links O que deve conter: Esse é um texto de marcação onde deverá ser descrita a marca, trazendo informações adicionais para que o cidadão não tenha dúvidas sobre a escolha feita. Orientações sobre o que pode conter: Texto institucional de apresentação Desde quanto atua Diferenciais de atuação Canais de atendimento |
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
*Campo obrigatório

---

# Guia de Operação do Diretório Central > 1. Acessando uma Organisation

---
id: 941818418
title: 1. Acessando uma Organisation
version: 1
modified: 2025-05-03T04:21:32.547Z
url: /spaces/OF/pages/941818418/1.+Acessando+uma+Organisation
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

# Guia de Operação do Diretório Central > 10. Cadastrando recursos de uma API

---
id: 941819273
title: 10. Cadastrando recursos de uma API
version: 1
modified: 2025-05-03T04:21:57.619Z
url: /spaces/OF/pages/941819273/10.+Cadastrando+recursos+de+uma+API
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

# Guia de Operação do Diretório Central > 11. Ciclo de Vida de Authorization Server

---
id: 941819709
title: 11. Ciclo de Vida de Authorization Server
version: 1
modified: 2025-05-03T04:22:03.939Z
url: /spaces/OF/pages/941819709/11.+Ciclo+de+Vida+de+Authorization+Server
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

# Guia de Operação do Diretório Central > 12. Criando um Software Statements

---
id: 941819734
title: 12. Criando um Software Statements
version: 1
modified: 2025-05-03T04:22:04.401Z
url: /spaces/OF/pages/941819734/12.+Criando+um+Software+Statements
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

# Guia de Operação do Diretório Central > 13. Criando uma nova reivindicação de autoridade de software

---
id: 941819817
title: 13. Criando uma nova reivindicação de autoridade de software
version: 1
modified: 2025-05-03T04:22:06.194Z
url: /spaces/OF/pages/941819817/13.+Criando+uma+nova+reivindica+o+de+autoridade+de+software
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

# Guia de Operação do Diretório Central > 14. Obtendo um Software Statements Assertion

---
id: 941819893
title: 14. Obtendo um Software Statements Assertion
version: 1
modified: 2025-05-03T04:22:08.221Z
url: /spaces/OF/pages/941819893/14.+Obtendo+um+Software+Statements+Assertion
---

Uma Software Statements Assertion (SSA) é um JWT assinado do diretório que contém todas as informações sobre um aplicativo que existe em um determinado momento no diretório. Inclui a localização de todas as chaves públicas vinculadas a esta declaração de software e todos os outros metadados de que um banco precisa para validar a legitimidade do aplicativo.
## Etapa 1: Criando uma Nova Declaração de Software Assinada

### Requisitos
**1.** Necessário ter criado uma Criando um Software Statements para sua organização.**2.** No Diretório, localize e selecione a sua organização.**3.** Vá até o menu `Software Statement`, acesse o artefato criado anteriormente clicando no link `CLIENT NAME`*.***4.** Na janela `Software Statement Details`*,*role a página para baixo e**selecione o menu `Software Statements Assertion`.**5.** Clique no botão `Copy to Clipboard`**para copiar o SSA gerado pelo Diretório.

---

# Guia de Operação do Diretório Central > 15. Como obter suporte ao Diretório

---
id: 941819937
title: 15. Como obter suporte ao Diretório
version: 1
modified: 2025-05-03T04:22:09.270Z
url: /spaces/OF/pages/941819937/15.+Como+obter+suporte+ao+Diret+rio
---

Aqui apresentamos as formas de contato para suporte ao Diretório Central.
## Service Desk
Todas as consultas, problemas ou solicitações de suporte precisam ser roteados por meio do Service Desk.O Service Desk do Open Finance Brasil pode ser acessado pelo endereço: [https://servicedesk.openbankingbrasil.org.br/](https://servicedesk.openbankingbrasil.org.br/)É possível abrir chamados de Solicitação de Informações, Melhorias e incidentes de indisponibilidade ou problemas de performance.

---

# Guia de Operação do Diretório Central > 16. Configurando eventos de notificação no Diretório (2)

---
id: 941819977
title: 16. Configurando eventos de notificação no Diretório (2)
version: 1
modified: 2025-05-03T04:22:10.174Z
url: /spaces/OF/pages/941819977/16.+Configurando+eventos+de+notifica+o+no+Diret+rio+2
---

Aqui apresentamos a configuração de *webhook* no Diretório
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

# Guia de Operação do Diretório Central > 17. Obtendo um token de acesso para as APIs do Diretório (2)

---
id: 941820052
title: 17. Obtendo um token de acesso para as APIs do Diretório (2)
version: 1
modified: 2025-05-03T04:22:12.410Z
url: /spaces/OF/pages/941820052/17.+Obtendo+um+token+de+acesso+para+as+APIs+do+Diret+rio+2
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
**1.** Para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **2.** No campo `Enter request URL`, digite o valor obtido da URL de token mencionado na [etapa 2](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820052/17.+Obtendo+um+token+de+acesso+para+as+APIs+do+Diret+rio+2#Etapa-2:-Localizando-a-URL-de-Token-no-Diretório).**3.** Defina o tipo da operação para `POST`.**4.** Vá para a guia `Body` e selecione o botão de opção `'x-www-form-urlencoded'`.**5.** Insira os parâmetros como descritos a seguir:client_id = <valor obtido no CLIENT ID na [etapa 1](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820052/17.+Obtendo+um+token+de+acesso+para+as+APIs+do+Diret+rio+2#Etapa-1:-Localizando-o-Identificador-do-Cliente)>
grant_type = client_credentials
scope = directory:software**6.** Uma vez que todos os parâmetros e valores estejam preenchidos, clique no botão `Send`*.***7.** Selecione e copie o valor retornado no atributo `access_token`*.*

---

# Guia de Operação do Diretório Central > 18. Listando as organizações cadastradas no Diretório via API (2)

---
id: 941820148
title: 18. Listando as organizações cadastradas no Diretório via API (2)
version: 1
modified: 2025-05-03T04:22:14.779Z
url: /spaces/OF/pages/941820148/18.+Listando+as+organiza+es+cadastradas+no+Diret+rio+via+API+2
---

Para acessar a API Organisations no Diretório, você precisará de um token de acesso. Esta seção descreve as etapas necessárias para listar e visualizar os detalhes das organizações cadastradas no Diretório.
## Etapa 1: Obtendo Detalhes das Organizações

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.**Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`.**3.** No campo *Enter request URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations)`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations](https://matls-auth.directory.openbankingbrasil.org.br/organisations)**4.** Defina o tipo da operação para `GET`.**5.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**6.**Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**7.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.**NOTA:** Para localizar uma organização mãe que pertença a um conglomerado, você poderá percorrer na lista de resposta de dados JSON do servidor, capturando o identificador no atributo `ParentOrganisationReference` das organizações filhas e localizar o mesmo ID na organização cujo o atributo `RegistrationId` contenha este mesmo valor.

---

# Guia de Operação do Diretório Central > 19. Listando os servidores de autorização de uma organização via API (2)

---
id: 941820204
title: 19. Listando os servidores de autorização de uma organização via API (2)
version: 1
modified: 2025-05-03T04:22:16.156Z
url: /spaces/OF/pages/941820204/19.+Listando+os+servidores+de+autoriza+o+de+uma+organiza+o+via+API+2
---

Aqui apresentamos os passos para listar os servidores de autorização de uma organização.
## Etapa 1: Listando os Servidores de Autorização

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.** Necessário ter realizado os passos da sessão Listando as organizações cadastradas no Diretório via API.**3.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **4.** No campo *Enter request URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/authorisationservers`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/authorisationservers**5.** Defina o tipo da operação para `GET`.**6.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**7.** Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**8.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.**NOTA:**Na resposta de dados JSON do servidor o atributo `CustomerFriendlyName` contém o valor da marca e o `CustomerFriendlyLogoUri` o logotipo vinculado a marca.`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/authorisationservers**9.** Defina o tipo da operação para GET.**10.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**11.** Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**12.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.**NOTA:** Na resposta de dados JSON do servidor o atributo `CustomerFriendlyName` contém o valor da marca e o `CustomerFriendlyLogoUri` o logotipo vinculado a marca.

---

# Guia de Operação do Diretório Central > 20. Obtendo um Software Statement via API (2)

---
id: 941820277
title: 20. Obtendo um Software Statement via API (2)
version: 1
modified: 2025-05-03T04:22:18.069Z
url: /spaces/OF/pages/941820277/20.+Obtendo+um+Software+Statement+via+API+2
---

Aqui apresentamos os passos para obter um Software Statement (SS) no Diretório via API.
## Etapa 1: Obtendo um SS no Diretório via API

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.** Necessário ter realizado os passos da sessão Listando as organizações cadastradas no Diretório via API.**3.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **4.** No campo *Enter request URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements**5.** Defina o tipo da operação para GET.**6.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**7.** Na coluna ao lado, no campo *Token* cole o `access_token` obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**8.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.

---

# Guia de Operação do Diretório Central > 21. Obtendo um Software Statement Assertion via API (2)

---
id: 941820335
title: 21. Obtendo um Software Statement Assertion via API (2)
version: 1
modified: 2025-05-03T04:22:19.408Z
url: /spaces/OF/pages/941820335/21.+Obtendo+um+Software+Statement+Assertion+via+API+2
---

qui apresentamos os passos para obter um Software Statement Assertion (SSA) no Diretório via API.
## Etapa 1: Obtendo um SSA do Diretório via API

### Requisitos
**1.** Necessário ter um token de acesso. Veja mais detalhes em Obtendo um token de acesso para acessar as APIs do Diretório.**2.** Necessário ter realizado os passos da sessão Listando as organizações cadastradas no Diretório via API.**3.** Necessário ter realizado os passos da sessão Obtendo um Software Statement via API.**4.** Para fins ilustrativos será utilizado o [Postman](https://www.postman.com/) para acessar as APIs do Diretório do Open Finance. Assim, para adicionar uma nova requisição a uma coleção, abra uma nova aba e salve a partir daí, ou em `Collection` à esquerda do Postman, clique em `'...'` na coleção e escolha `Add Request`. Você também pode criar uma solicitação clicando no menu `File > New`*,* e em seguida `Request`. **5.** No campo `Enter request`*URL*, insira um dos valores descritos a seguir de acordo com o ambiente utilizado:`Sandbox:`**[https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.sandbox.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements/<software_id>/assertion`Produção:`**[https://matls-auth.directory.openbankingbrasil.org.br/organisations/](https://matls-auth.directory.openbankingbrasil.org.br/organisations/)<organisation_id>/softwarestatements/<software_id>/assertion**6.** Defina o tipo da operação para `GET`.**7.** Vá para a guia `Authorisation` e na caixa de seleção `Type` selecione a opção `Bearer Token`.**8.** Na coluna ao lado, no campo *Token* cole o `access_token`**obtido na seção Obtendo um token de acesso para acessar as APIs do Diretório.**9.** Uma vez que todos os valores estejam preenchidos, clique no botão `Send`*.*Você verá a resposta de dados JSON do servidor no painel inferior.

---

# Guia de Operação do Diretório Central > 22. Como se inscrever nas atualizações de lançamento do Diretório (2)

---
id: 941820395
title: 22. Como se inscrever nas atualizações de lançamento do Diretório (2)
version: 1
modified: 2025-05-03T04:22:20.616Z
url: /spaces/OF/pages/941820395/22.+Como+se+inscrever+nas+atualiza+es+de+lan+amento+do+Diret+rio+2
---

Constantemente são realizados aprimoramentos e atualizações no Diretório e estas mudanças são registradas em uma página Web onde reside todo o conteúdo do *Release Notes*. Esta seção descreve as etapas necessárias de inscrição para o recebimento de notificação do release notes do Diretório quando publicado.
## Etapa 1: Cadastrando o Recebimento de Release Notes

### Requisitos
**1.**Em seu navegador, navegue até site de [monitoramento de disponibilidade do Diretório](https://status.directory.openbankingbrasil.org.br/).**2.** Clique em `Subscrever atualizações`.**3.** Na tela seguinte, adicione seu e-mail e clique no botão `Subscrever`. O Diretório irá enviar uma mensagem de confirmação, que será encaminhada ao endereço de e-mail informado.**4.** No e-mail recebido, clique no botão `Sim, subscreve-me`.**5.** Em uma página da Web será apresentada a mensagem que seu e-mail encontra-se agora subscrito para atualizações de estado Open Finance Brasil.**NOTA:**Caso você não tenha recebido o e-mail de confirmação, verifique sua caixa de *SPAM* e as politicas de bloqueio de mensagens. O envio das mensagens poderá sofrer algum atraso, contudo, se o problema persistir, clique no botão `Subscrever Alterações` para reenvio das mensagens.
## Etapa-2:-Acessando-o-Release-Notes Etapa 2: Acessando o Release Notes

### Requisitos
**1.**No navegador, digite a URL de acordo com o ambiente a ser acessado:`Sandbox:` [https://data.sandbox.directory.openbankingbrasil.org.br/release-notes](https://data.sandbox.directory.openbankingbrasil.org.br/release-notes) `Produção:`**[https://data.directory.openbankingbrasil.org.br/release-notes](https://data.directory.openbankingbrasil.org.br/release-notes)

---

# Guia de Operação do Diretório Central > 23. APIs do Diretório - Boas Práticas

---
id: 941820454
title: 23. APIs do Diretório - Boas Práticas
version: 1
modified: 2025-05-03T04:22:21.923Z
url: /spaces/OF/pages/941820454/23.+APIs+do+Diret+rio+-+Boas+Pr+ticas
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

# Guia de Operação do Diretório Central > APIs do Diretório de participantes

---
id: 941818334
title: APIs do Diretório de participantes
version: 1
modified: 2025-05-03T04:21:31.826Z
url: /spaces/OF/pages/941818334/APIs+do+Diret+rio+de+participantes
---

O Diretório possui APIs abertas e restritas que facilitam o compartilhamento de informações entre os participantes do ecossistema bem como um*webhook* para notificações de eventos. As APIs abertas permitem o acesso a informações gerais como dados de participantes e chaves públicas, e as APIs restritas são usadas para acessar dados sensíveis, com acesso concedido após a obtenção de um token de autenticação.[Clique para conferir o manual de boas práticas de consumo das APIs do Diretório](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820454/23.+APIs+do+Diret+rio+-+Boas+Pr+ticas?atlOrigin=eyJpIjoiMzM1YjdmMTZmYWNhNGI5MjlkYmE3MTQ2ZDFhYjg0NmYiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para obtenção do token de acesso para as APIs do Diretório](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820052/17.+Obtendo+um+token+de+acesso+para+as+APIs+do+Diret+rio+2?atlOrigin=eyJpIjoiYmQxODBhNDZhZDljNGI2MWE2OGUyYzFlMDg5N2M4OTYiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para listar as organizações cadastradas no Diretório via API](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820148/18.+Listando+as+organiza+es+cadastradas+no+Diret+rio+via+API+2?atlOrigin=eyJpIjoiN2QwMTViNmNkZGFjNDY3ZTkwMjdhYWNjOWFmMDk3NDUiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para listar os servidores de autorização de uma organização via API](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820204/19.+Listando+os+servidores+de+autoriza+o+de+uma+organiza+o+via+API+2?atlOrigin=eyJpIjoiMGJhZGM4MTQyMmE4NDY4MmFkYmM2ODI4NDBiMDZhMWMiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para listar as declarações de software cadastrados no Diretório via API](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820277/20.+Obtendo+um+Software+Statement+via+API+2?atlOrigin=eyJpIjoiNmE5ZWUxYmNkZGY1NDQ1MjhkNjYzNDU0ZTRiZWE2YjYiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para obter um software statement assertion via API](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941820335/21.+Obtendo+um+Software+Statement+Assertion+via+API+2?atlOrigin=eyJpIjoiZWVmOTY1M2M1Y2NiNDE1MjhhZDFkOTQ3NzQ4N2ZlMDYiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para obter suporte ao Diretório](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819937/15.+Como+obter+suporte+ao+Diret+rio?atlOrigin=eyJpIjoiOTdmY2NhNTUyNjFjNDVmYmFjM2Y0N2NmOTNlMjNiZDYiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para configurar eventos de notificação do Diretório](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819977/16.+Configurando+eventos+de+notifica+o+no+Diret+rio+2?atlOrigin=eyJpIjoiYzVmNjQ1OTdjNWI5NGUwY2I4Nzg1NjUxNzY3MGQxYmEiLCJwIjoiYyJ9)

---

# Guia de Operação do Diretório Central > Certificado de assinatura

---
id: 941818211
title: Certificado de assinatura
version: 1
modified: 2025-05-03T04:21:29.937Z
url: /spaces/OF/pages/941818211/Certificado+de+assinatura
---

A documentação de segurança do Open Finance Brasil estabelece que as organizações devem emitir um certificado de assinatura (BRSEAL) por Autoridades Certificadoras (ACs) reconhecidas pela cadeia ICP Brasil e em seguida, inseri-lo no Diretório de participantes com a opção EXTERNAL BRSEAL.Ao adicionar o certificado no Diretório duas validações serão feitas:
1. O Diretório validará que o certificado foi assinado por uma das ACs credenciadas ao Open Finance Brasil, cuja lista completa pode ser encontrada na documentação de segurança. – É possível executar essa consulta avaliando se o issuer do certificado está na lista citada, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl - openssl x509 -in brcac.pem -noout -issuer

1. O Diretório validará que o certificado possui UID em seu subject igual ao Organisation ID no caso do BRSEAL – É possível executar essa consulta avaliando se o UID do subject é igual ao UID apresentado no diretório, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl x509 -in brcac.pem -noout –subject
No ambiente sandbox, é possível a geração de certificados de assinatura emitidos pelo próprio Diretório para uso exclusivo neste ambiente.[Clique para conferir o passo a passo para registro de certificado de assinatura](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819091/08.+Carregando+certificados+emitidos+por+autoridade+de+certifica+o+em+Produ+o?atlOrigin=eyJpIjoiYzQwOGU0ZDJkZDE1NDMwMWI1NjczNmM3NDUzNTA0N2MiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para emissão de certificados no Diretório para uso exclusivo do ambiente sandbox](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818944/07.+Criando+certificados+de+transporte+e+assinatura+em+Sandbox?atlOrigin=eyJpIjoiMTczZTY1OGUwOGY0NDE3ZmE5YTY5MWM4YzQyMjhjNWQiLCJwIjoiYyJ9)

---

# Guia de Operação do Diretório Central > Como participar do Open Finance-

---
id: 941818136
title: Como participar do Open Finance?
version: 1
modified: 2025-05-03T04:21:29.180Z
url: /spaces/OF/pages/941818136/Como+participar+do+Open+Finance
---

A participação no Open Finance Brasil para instituições financeiras, instituições de pagamento e outras instituições autorizadas a funcionar pelo Banco Central do Brasil (BCB) ocorre mediante o registro da organização no Diretório de Participantes, conforme estabelecido na Resolução Conjunta 1/2020 do BCB e Conselho Monetário Nacional.As instituições que desejem participar do ecossistema devem solicitar à Associação Open Finance o cadastro no Diretório de Participantes, através de um chamado na plataforma *Service Desk*, na seção para convidados, seguindo o caminho:Catálogo de Serviços > Instituição Financeira Participante > Gestão de cadastro> Cadastro de Nova InstituiçãoPara instituições participantes que desejam registrar novas organizações pertencentes ao conglomerado, a solicitação estará disponível na seção de participantes, seguindo o caminho: Catálogo de Serviços > Requisições > Gestão de Cadastro > Cadastro de Nova InstituiçãoNo momento da abertura do chamado, a instituição deverá indicar as seguintes informações:
- Dados cadastrais
- Categoria de representação perante a Associação, conforme descrito na Instrução Normativa BCB nº 485
- Dados do representante perante a Associação
- Dados do administrador do cadastro
- Dados para contato de incidente
- Dados da equipe de atendimento do service desk
- Documentos necessários para comprovação de autorização de funcionamento pelo Banco Central, Estatuo Social, Ata de Eleição do representante legal e documentos de identidade do representante legal
Após a abertura do chamado, a Associação irá validar a documentação e emitir o termo de adesão à Associação e termo de aceite da plataforma de resolução de disputas. Estes documentos deverão ser assinados pelos representantes legais da organização, de acordo com seu estatuto social.Após a assinatura do documento, será realizado o registro do usuário administrador da organização no Diretório de participantes e a organização terá seu chamado encerrado e os acessos liberados. Após o registro no Diretório de participantes, o administrador da organização deve realizar o cadastro dos demais usuários técnicos e em seguida realizar as publicações técnicas da organização de acordo com sua modalidade de participação. **Dispensa de participação do Open Finance Brasil para instituições participantes**Instituições participantes podem solicitar dispensa de participação do Open Finance e exclusão do Diretório de participantes, caso estejam enquadradas nas modalidades de dispensa que a regulação vigente permite. A solicitação deve ser encaminhada para análise da Associação com o devido embasamento normativo, através do service desk, no seguinte caminho:Catálogo de Serviços > Requisições > Gestão de Cadastro > Exclusão de Instituição​​

---

# Guia de Operação do Diretório Central > Controle de Versão - [GODC] (2)

---
id: 941818004
title: Controle de Versão - [GODC] (2)
version: 1
modified: 2025-05-03T04:21:28.174Z
url: /spaces/OF/pages/941818004/Controle+de+Vers+o+-+GODC+2
---

| Versão | Data | Resumo das Alterações |
| --- | --- | --- |
| 1.2.16 | | Alteração: Vedada a possibilidade de duplicação de marcas Alteração: Substituído o conceito de herança no cadastro pelo conceito de atendimento de papéis regulatórios, atualizando as imagens e exemplos |
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

---

# Guia de Operação do Diretório Central > Diretório de participantes

---
id: 941818081
title: Diretório de participantes
version: 1
modified: 2025-05-03T04:21:28.468Z
url: /spaces/OF/pages/941818081/Diret+rio+de+participantes
---

O Diretório de participantes é uma plataforma centralizada que registra as organizações participantes do Open Finance Brasil, armazenando informações cruciais como dados cadastrais, modalidades de participação, certificados de segurança, publicações técnicas e os recursos disponibilizados pelas organizações, além de suas certificações funcionais e de segurança.Através da gestão de identidades, acessos e da aplicação de padrões de segurança, o Diretório proporciona aos participantes um ambiente seguro, permitindo as autenticações necessárias para viabilizar o compartilhamento de dados e serviços entre si. Além disso, por ser uma plataforma centralizada, oferece um ponto único de consulta de servidores e recursos disponíveis, contribuindo para um ecossistema eficiente e interoperável.Há dois ambientes que são disponibilizados para as instituições:
- O ambiente de produção é onde as aplicações e serviços operam em condições reais. Neste ambiente, as transações são efetivas e os dados dos usuários são manipulados de maneira segura conforme as regulamentações. Este ambiente está disponível em: Open Banking Brasil
- O ambiente sandbox é um espaço controlado e seguro, onde desenvolvedores podem testar suas aplicações e serviços sem o risco de impactar usuários finais ou transações reais. Ele permite a validação de ideias e funcionalidades em um ambiente simulado que replica as condições do mundo real, garantindo que as soluções sejam seguras e eficazes antes de serem lançadas no ambiente de produção. Este ambiente de sandbox está disponível em: Open Banking Brasil Sandbox

---

# Guia de Operação do Diretório Central > Organização

---
id: 941818106
title: Organização
version: 1
modified: 2025-05-03T04:21:28.723Z
url: /spaces/OF/pages/941818106/Organiza+o
---

A organização é a entidade principal do Diretório de participantes, ela representa as instituições participantes do ecossistema e contém suas publicações técnicas de acordo com seus papeis regulatórios. No Open Finance, há dois tipos de modalidade de participação para as organizações:
- Provedora de dados e serviços (Transmissoras/Detentoras) Instituições transmissoras de dados ou detentoras de conta são as organizações que disponibilizam dados do cliente ou serviços, como por exemplo, pagamentos e portabilidade de crédito – mediante o consentimento do usuário – para organizações recebedoras através da publicação de recursos em um servidor de autorização
- Consumidoras de dados e serviços (Receptoras/Iniciadoras) Instituições receptora de dados ou iniciadora de pagamentos são as organizações que acessam os dados das organizações provedoras para construir novos produtos ou viabilizar serviços através de suas declarações de software
**Uma organização pode ser cadastrada de forma independente ou pertencente a um conglomerado**. Organizações líderes de conglomerados são chamadas de ‘organização mãe’, enquanto organizações participantes do conglomerado são chamadas de ‘organização filha’. O vínculo entre conglomerados é indicado através do preenchimento do campo do número de registro (CNPJ) da organização mãe na organização filha. Este cadastro é realizado pela Associação Open Finance e solicitações de alteração devem ser realizadas através da plataforma *service desk.*As marcas são uma forma mais amigável, democrática e fácil para identificação das instituições participantes pelos clientes finais. Para organizações provedoras de dados, elas são indicadas através de seus servidores de autorização, e para organizações recebedoras de dados e serviços, elas são indicadas através de suas declarações de software. A marca cadastrada no Diretório será a mesma apresentada para escolha do usuário na jornada de compartilhamento de dados e iniciação de pagamentos. As instituições participantes (ou organizações) também serão apresentadas em tela, apenas em caráter informativo. Para maiores detalhes, consulte o Guia de Experiência do Usuário.[Clique para conferir os campos de detalhes da organização](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/folder/935919732?atlOrigin=eyJpIjoiMTFiOTU4N2UwMzY4NGFiNDk4OWE3MmUxNWE2MWI4MTIiLCJwIjoiYyJ9)

---

# Guia de Operação do Diretório Central > Organizações consumidoras de dados e serviços (receptoras-iniciadoras)

---
id: 941818299
title: Organizações consumidoras de dados e serviços (receptoras/iniciadoras)
version: 1
modified: 2025-05-03T04:21:31.586Z
url: /spaces/OF/pages/941818299/Organiza+es+consumidoras+de+dados+e+servi+os+receptoras+iniciadoras
---

Organizações que desejarem atuar como recebedoras de dados deverão publicar suas declarações de software para realizar o Dynamic Client Registration (DCR), ou registro dinâmico do cliente nos servidores de autorização dos provedores, e ter acessos aos dados e recursos das organizações provedoras de dados de acordo com o escopo de seu papel regulatório. Para a declaração de software, é necessário que a organização adicione um certificado de transporte (BRCAC) emitido por Autoridades Certificadoras reconhecidas pela cadeia ICP Brasil. O diretório irá validar que o certificado possui UID em seu subject igual ao UID da declaração do software no caso do BRCAC.  É possível executar essa consulta avaliando se o UID do subject é igual ao UID apresentado no diretório, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl x509 -in brcac.pem -noout -subject .No ambiente sandbox, é possível a geração de certificados de transporte emitidos pelo próprio Diretório para uso exclusivo neste ambiente.Após a criação da declaração de software, a organização deverá obter um software statement assertion (SSA). Uma Software Statements Assertion (SSA) é um JWT assinado do diretório que contém todas as informações sobre um aplicativo que existe em um determinado momento no diretório. Inclui a localização de todas as chaves públicas vinculadas a esta declaração de software e todos os outros metadados de que um banco precisa para validar a legitimidade do aplicativo.A entrada em produção de instituições consumidora de dados e serviços só deverá ocorrer após a obtenção de certificação de segurança RP e a realização das devidas integrações com ferramentas do perímetro central. Instituições que atuarem na modalidade de iniciadoras de pagamento deverão realizar o processo de *onboarding*de ITPs.[Clique para conferir o passo a passo para criar uma declaração de software](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819734/12.+Criando+um+Software+Statements?atlOrigin=eyJpIjoiM2ViMTE5MjY3MDRiNDJmOTg5ODU4NDFiODljNGVmZjIiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para vinculação do papel regulatório na declaração de software](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819817/13.+Criando+uma+nova+reivindica+o+de+autoridade+de+software?atlOrigin=eyJpIjoiM2U1ZDFlOTE1NDhkNGQ0OWE2MjAyZTk5MzVmOWU1MWEiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para registro de certificado de transporte    da declaração de software](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819091/08.+Carregando+certificados+emitidos+por+autoridade+de+certifica+o+em+Produ+o?atlOrigin=eyJpIjoiN2UxZDc4NDA4ZTYyNDdiYTg4MTY1ZTg4MjIxMjdjNzMiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para obter o](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819893/14.+Obtendo+um+Software+Statements+Assertion?atlOrigin=eyJpIjoiNGM3NjI2MDYzNDg1NGVjZTgwZDY2OWU1YjcxNzg1YWMiLCJwIjoiYyJ9)*software statement assertition*(SSA)[Clique para conferir o passo a passo para emissão de certificados no Diretório para uso exclusivo do ambiente sandbox](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818944/07.+Criando+certificados+de+transporte+e+assinatura+em+Sandbox?atlOrigin=eyJpIjoiNmIyMjBlYTYyZDQ4NDA4Y2ExNzdkYTZhNjQzMzk4MGIiLCJwIjoiYyJ9)[Clique para conferir as regras e obrigações das instituições participantes do Open Finance Brasil](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818371/Regras+e+obriga+es+das+institui+es+participantes+do+Open+Finance+Brasil?atlOrigin=eyJpIjoiZWY5OTI4YzAwNWQzNGZjYmFhOWYyMTJiYWE4YTVkNGQiLCJwIjoiYyJ9)

---

# Guia de Operação do Diretório Central > Organizações provedoras de dados (transmissoras-detentoras)

---
id: 941818238
title: Organizações provedoras de dados (transmissoras/detentoras)
version: 1
modified: 2025-05-03T04:21:30.168Z
url: /spaces/OF/pages/941818238/Organiza+es+provedoras+de+dados+transmissoras+detentoras
---

As organizações que desejarem atuar como provedoras de dados devem publicar servidores de autorização. O servidor de autorização representa a identidade da organização (marca) e contém os recursos de dados aos quais os receptores podem solicitar acesso. Além disso, o servidor realiza as validações necessárias, como a autenticação do cliente que está requisitando acesso à determinado recurso e a verificação das permissões, garantindo que o acesso aos dados seja seguro e conforme o consentimento do usuário.As informações configuradas no servidor de autorização, incluindo seu endpoint de /.well-known, são utilizadas pelos clientes que fornecem o consentimento para o compartilhamento de dados ou serviços. Esta URI contém a maior parte das informações necessárias para uma aplicação de um recebedor interagir com o servidor do provedor de dados. Após a criação do servidor de autorização, inicialmente em ambiente sandbox[[FV3]](#) , a organização deverá desenvolver suas APIs, realizar testes funcionais através do motor de conformidade, submeter evidências de sucesso para recebimento de certificação funcional e de segurança e realizar integrações com as ferramentas do perímetro central.A criação do servidor de autorização em ambiente de produção e a publicação dos recursos deve ocorrer apenas após as etapas mencionadas acima realizadas em ambiente sandbox. A instituição está sujeita ao monitoramento de desconformidade a partir do momento em que realiza suas publicações em ambiente produção.**Pontos de atenção no cadastramento de servidor de autorização (marcas transmissoras de dados/detentoras de conta)**
- Uma marca é representada por um servidor de autorização e o mesmo sempre deve ser cadastrado associado a uma organização;
- O vínculo entre uma organização master (mãe) e uma organização que pertence ao conglomerado é realizado via o preenchimento do campo Parent Organization Reference ID no cadastro da organização filha, informando o CNPJ da organização mãe (caso seja necessário ajuste, favor abrir um ticket no service desk );
- Quando a estrutura for de um conglomerado (uma organização master e uma ou mais organizações relacionadas) é recomendado o cadastro da marca na instituição mãe, caso as filhas venham a utilizar a mesma marca e arquitetura de autenticação. Importante ressaltar que caso não seja cadastrado uma marca exclusiva para a organização filha, será inferido que os cadastros de marcas para atendimento dos papéis regulatórios foram realizados na organização mãe;
- Caso a mesma marca pertença a mais de uma organização, esta deverá ser cadastra como um único servidor de autorização em apenas uma das organizações. É vedado a duplicação de marcas, ou seja, marcas que possuem o mesmo Customer Friendly Server Name ;
- Caso uma marca pertença exclusivamente a uma organização filha o cadastro poderá ser realizado apenas na filha;
**Exemplos de possíveis cenários para cadastro de servidor de autorização**
| Neste exemplo, temos uma “Organização” que não possui organizações filhas e possui os papéis regulatórios DADOS e CONTA. Neste cenário a organização possui apenas um AS/marca, a “Marca 1”, que possui todos os recursos necessários para atendimento dos seus papéis regulatórios. |
| Neste exemplo, temos uma “Organização” que não possui organizações filhas e possui os papéis regulatórios DADOS e CONTA. Neste cenário a organização possui três AS/marcas, a “Marca 1” que possui os recursos necessários para atendimento do papel DADOS, a “Marca 2” que possui os recursos referente ao papel “CONTA” e a “Marca 3” atende a ambos os papéis regulatórios. |
| Neste exemplo, temos uma “organização mãe” que possui duas filhas e todas possuem os mesmos papéis regulatórios DADOS e CONTA. Neste cenário a “organização mãe” possui um AS/marca, a “Marca 1”, que possui apenas um AS/marca, a “Marca 1” que possui todos os recursos necessários para atendimento dos seus papéis regulatórios. Ambas as suas organizações filhas compartilham da mesma arquitetura e infraestrutura de autenticação, utilizando o mesmo AS/marca para compartilhamento dos seus recursos. |
| Neste exemplo, temos uma “organização mãe” que possui duas filhas que possuem papéis regulatórios distintos. A “organização mãe” e a “organização filha 1” possuem o papel regulatório DADOS, enquanto a “Organização Filha 2” possui o papel regulatório CONTA. Neste cenário a “organização mãe” possui um AS/marca, a “Marca 1”, que possui apenas um AS/marca, a “Marca 1”, entregando todos os recursos necessários para atendimento do papéis regulatórios tanto para a “Organização Mãe”, quanto para a “Organização Filha 1”, compartilhando a mesma arquitetura e infraestrutura de autenticação. A “Organização Filha 2” possui a “Marca 2” que entrega os recursos necessários para atender ao seu papel regulatório. Neste caso, a “Organização Filha 2” possui a sua própria arquitetura e infraestrutura de autenticação. |
| Neste exemplo, temos uma “organização mãe” que possui duas filhas que possuem papéis regulatórios distintos. A “Organização Mãe” e a “Organização Filha 1” possuem o papel regulatório DADOS, enquanto a “Organização Filha 2” possui o papel regulatório CONTA. Com a intenção de reuso da arquitetura e infraestrutura de autenticação, o participante replicou o papel regulatório da “Organização Filha 2” para a “Organização Mãe” e desta forma, com uso de uma única marca/AS, a “Marca A”, entrega todos os recursos necessários para atender aos papéis regulatórios do conglomerado. |
| Neste exemplo, temos uma “Organização Mãe” que possui duas filhas e todas possuem os mesmos papéis regulatórios DADOS e CONTA. Neste cenário a “organização mãe” possui um AS/marca, a “Marca 1”, que possui apenas um AS/marca, a “Marca 1” que possui todos os recursos necessários para atendimento dos papéis regulatórios da “Organização Mãe” e “Organização Filha 1”. A “Organização Filha 2” possui a “Marca 2” que entrega os recursos necessários para atender dos seus papéis regulatórios. Neste caso, a “Organização Filha 2” possui a sua própria arquitetura e infraestrutura de autenticação. |
 **Ciclo de vida do servidor de autorização (marcas transmissoras de dados/detentoras de conta)**Cenários de encerramento, aquisição ou incorporação de marcas, encerramento de produtos ofertados por uma marca, migração de infraestrutura tecnológica ou demais mudanças que demandem alteração no servidor de autorização são descritas na seção do ciclo de vida do servidor de autorização. Essa seção contém recomendações para gestão de mudanças do servidor.Para o cenário de uma organização ou conglomerado que tome a decisão de descontinuar/aposentar um servidor de autorização, ficam especificadas abaixo, as regras para preenchimento dos campos no diretório e outros pontos importantes:
| Nome do Campo | Descrição | Exemplo | Transmissora/Detentora | Receptora/Iniciadora |
| Deprecation Date | Data programada para iniciar a descontinuação do servidor de autorização | 2024-11-01 | Data a partir da qual o servidor de autorização não aceitará mais requisições de novos consentimentos | Data limite para solicitação de novos consentimentos naquele servidor. |
| Retirement Date | Data programada para a aposentadoria do servidor | 2024-12-01 | Data a partir da qual o servidor de autorização será inativado | Data limite para consultas de consentimentos naquele servidor. |
| SupersededByAuthorisationServerId | ID do servidor de autorização que substituirá o servidor atual | xxxxxxxx-XXXX-xxxx-XXXX-xxxxXXXXxxxx | ID do servidor de autorização que passará a recepcionar os pedidos de novos consentimentos a partir da inatividade do servidor em questão | Redirecionamento das solicitações de novos consentimentos. |
******Pontos Importantes:**
- Os campos Deprecation Date e Retirement Date serão obrigatórios no contexto de descontinuação de marcas e o campo SupersededByAuthorisationServerId só será obrigatório no caso de substituição do servidor de autorização.
- O campo Deprecation Date deve ser informado com pelo menos 10 dias antes do início da descontinuação.
- As datas inseridas nos campos citados, devem ser informadas e acordadas com o regulador.
- A boa prática sugerida é que a data de depreciação seja anterior a data de aposentadoria em pelo menos 1 mês (30 dias corridos), a ser validada caso a caso junto ao regulador.
- Esses campos são meramente informativos. Isso significa que, é de responsabilidade da Instituição que está descontinuando/aposentando a marca construir uma solução para "recusar" as requisições de consentimento recebidas a partir da data informada no campo " Deprecation Date ", não sendo responsabilidade das demais Instituições participantes não requisitarem novos consentimentos através do Authorisation Server, uma vez que o mesmo permanece como "Ativo" até a data de sua aposentadoria.
- Os consentimentos de transmissão ativos na marca que está sendo descontinuada/aposentada deverão continuar acessíveis para as Instituições receptoras, seguindo as regras de "tempo" determinadas pela regulação e especificações vigentes.
[Clique para conferir o passo a passo para registro de um servidor de autorização](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819190/09.+Cadastrando+um+Authorisation+Server?atlOrigin=eyJpIjoiNmFiMWVhMmE2ZTI0NDRjNDhkMTY1YmNhZDdiOTYxMTgiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para registro de certificação de segurança do servidor de autorização](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819190/09.+Cadastrando+um+Authorisation+Server?atlOrigin=eyJpIjoiNmFiMWVhMmE2ZTI0NDRjNDhkMTY1YmNhZDdiOTYxMTgiLCJwIjoiYyJ9) [Clique para conferir o passo a passo para publicação de recursos no servidor de  autorização](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819273/10.+Cadastrando+recursos+de+uma+API?atlOrigin=eyJpIjoiYTFjZmZkNzYzZTI1NDUyYWEwZGFlZTc1MTc4ZDU0YzEiLCJwIjoiYyJ9) [Clique para conferir orientações sobre o ciclo de vida do servidor de autorização](https://openfinancebrasil.atlassian.net/wiki/x/AQAWEw)[Clique para conferir as regras e obrigações das instituições participantes do Open Finance Brasil](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818371/Regras+e+obriga+es+das+institui+es+participantes+do+Open+Finance+Brasil?atlOrigin=eyJpIjoiZWY5OTI4YzAwNWQzNGZjYmFhOWYyMTJiYWE4YTVkNGQiLCJwIjoiYyJ9)

---

# Guia de Operação do Diretório Central > Papéis regulatórios

---
id: 941818157
title: Papéis regulatórios
version: 1
modified: 2025-05-03T04:21:29.418Z
url: /spaces/OF/pages/941818157/Pap+is+regulat+rios
---

No Diretório de Participantes, as organizações devem declarar seus papéis regulatórios de acordo com a sua modalidade de participação, vinculada ao domínio de autoridade do ecossistema, o Banco Central do Brasil. Os papéis regulatórios determinam o acesso aos recursos, o consumo de APIs e as requisições de acordo com o escopo específico de cada organização.As modalidades assumidas pelos participantes no âmbito do Open Finance são auto declaratórias e podem ser exercidas simultaneamente. O papel regulatório deve estar em conformidade com o modelo de negócios do participante e sua declaração em produção deve ocorrer em conjunto com as demais publicações técnicas referentes à modalidade de participação da instituição após suas devidas validações em ambiente sandbox.A modalidade de participação declarada em ambiente de produção é monitorada pela Associação Open Finance e está sujeita à verificação do Banco Central do Brasil, especialmente com relação ao cumprimento do princípio da reciprocidade no compartilhamento de dados no Open Finance Brasil.A inativação de um papel regulatório declarado pela organização no Diretório de participantes só ocorre mediante autorização explícita da Associação Open Finance. A instituição deverá solicitar esta alteração através de abertura de ticket no *service desk*.Os papeis regulatórios e respectivas modalidades de participação são os seguintes:
| Papel regulatório | Modalidade de participação |
| DADOS | Instituição transmissora e/ou receptora de dados é a instituição que sendo: |
| Transmissora de dados: instituição participante que compartilha os dados com a instituição receptora; |
| Receptora de dados: instituição participante que apresenta solicitação de compartilhamento à instituição transmissora para recepção dos dados. |
| CONTA | Instituição detentora de conta é a instituição participante que mantém conta de depósitos à vista ou de poupança ou conta de pagamento pré-paga de cliente. |
| PAGTO | Instituição prestadora de serviço de iniciação de transação de pagamento é uma instituição participante que presta serviço de iniciação de transação de pagamento. |
| CCORR | Instituição que tenha firmado, na condição de contratante, contrato de correspondente no País, cujo objeto contemple a atividade de atendimento prevista no art. 8º., inciso V, da Resolução nº 3.954, de 24 de fevereiro de 2011, por meio eletrônico.   Atualmente essa modalidade não é utilizada nas jornadas de compartilhamento de dados ou serviços do Open Finance. |
[Clique para conferir o passo a passo para registro do domínio de autoridade](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818484/02.+Cadastrando+reivindica+es+de+dom+nio+de+autoridade?atlOrigin=eyJpIjoiM2IwNGEzMTc0MWE2NDg4NTlkNDA1NzVhMjg5ZjIxNTUiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para registro do papel regulatório](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818522/03.+Cadastrando+reivindica+es+de+autoridade?atlOrigin=eyJpIjoiMjJlODQ2MmE3YzMyNGJjNjhkZTU3YjAyOWJjYjc2ZWMiLCJwIjoiYyJ9)

---

# Guia de Operação do Diretório Central > Regras e obrigações das instituições participantes do Open Finance Brasil

---
id: 941818371
title: Regras e obrigações das instituições participantes do Open Finance Brasil
version: 1
modified: 2025-05-03T04:21:32.070Z
url: /spaces/OF/pages/941818371/Regras+e+obriga+es+das+institui+es+participantes+do+Open+Finance+Brasil
---

A Resolução Conjunta 1/2020 estabelece que a participação no Open Finance pode ocorrer de forma obrigatória ou voluntária pelas instituições. A partir do registro da organização no Diretório de participantes e assinatura do termo de adesão ao Open Finance, todas as organizações participantes do ecossistema ficam submetidas às políticas e diretrizes estabelecidos pela Associação e normativos do regulador, incluindo custeio da estrutura de governança, atendimento de tickets abertos contra a instituição, cumprimento das políticas de segurança, desenvolvimento e implementação de APIs e jornadas de experiência do usuário, integrações com as ferramentas do perímetro central e monitoramento de desconformidades.Abaixo podem ser consultadas as principais diretrizes do Open Finance Brasil:
- Custeio da Estrutura de governança Instrução Normativa BCB Nº 485
- Política de segurança Documentos de especificação de segurança do Open Finance
- Implementação de APIs Especificações das APIs Guia de certificação funcional e de segurança
- Atendimento de tickets no service desk Guia de atendimento de tickets pelo N2
- Ferramentas do perímetro central Plataforma de coleta de métricas Guia de operação da Ferramenta de Validação em Produção Motor de qualidade de dados
- Monitoramento de desconformidade Guia de itens monitorados e métricas

---

# Guia de Operação do Diretório Central > Usuários e contatos de notificação

---
id: 941818182
title: Usuários e contatos de notificação
version: 2
modified: 2025-11-27T14:46:01.612Z
url: /spaces/OF/pages/941818182/Usu+rios+e+contatos+de+notifica+o
---

O Diretório permite que diferentes tipos de usuários sejam habilitados a desempenhar funções específicas. Além disso, possui os contatos da organização que devem ser acionados em casos de incidentes.
- Administrador da organização Possui o maior nível de autoridade dentro da organização, o que inclui a adição ou remoção de usuários, recepção de notificações, cadastro de novos administradores e contatos da instituição, concessão de acesso à outras plataformas e responsável pelas publicações técnicas. Não existe a exigência que esse perfil seja procurador da instituição A responsabilidade pela gestão dos cadastros dos administradores é da própria organização. A alteração deste usuário após o cadastro da organização só é realizada pela Associação mediante autorização expressa do representante legal da instituição e abertura de ticket no service desk.
- Usuários de domínio Também conhecidos como usuários técnicos, estes usuários possuem funções específicas e estão vinculados ao papel regulatório que a organização declarou. No Open Finance Brasil, estes usuários são utilizados para autenticação em demais plataformas do perímetro central: Motor de conformidade Ferramenta de validação em produção Plataforma de resolução de disputas Plataforma de visualização de dados Plataforma service desk Usuários primários podem acessar o Diretório e cadastrar usuários secundários e usuários secundários tem acesso restrito ao Diretório de participantes.
- Contatos de notificação Os contatos de notificação não possuem acesso ao Diretório, mas devem ser indicados pela organização para que sejam acionados pela Associação em casos de dúvidas ou incidentes relacionados ao Open Finance Negócio: Contato responsável pela gestão de negócio do Open Finance na instituição. Técnico: Contato para tratativa de problemas técnicos do tipo: performance, disponibilidade e quanto a API’s de forma geral. Cobrança: Contato responsável pela cobrança dos custos da estrutura central do Open Finance Brasil. Incidente: Contato responsável pelo atendimento de incidentes relacionados ao Open Finance na instituição. Segurança: Contato para tratativas relacionadas a problemas de caráter de segurança como DCR, certificados entre outros. Orientamos o cadastro de pelos menos 1 para cada um dos 5 tipos de contato. Além disso, é de inteira responsabilidade da instituição inserir os contatos técnicos para cada departamento e mantê-los sempre atualizados para que a comunicação entre as instituições participantes não seja prejudicada. Os contatos publicados no Diretório Central deverão ser utilizados apenas no contexto de implementação do Open Finance. Contatos com objetivos comerciais – ainda que estejam inseridos no contexto de Open Finance – como soluções de implementação ou infraestrutura, deverão ser evitados. Tal medida visa preservar a eficácia da comunicação do ecossistema.
Para qualquer usuário acessar o Diretório, ele deverá estar vinculado a alguma organização como administrador ou usuário de domínio primário de alguma das plataformas. No primeiro acesso, o usuário deverá realizar seu cadastro e assinar o termo de aceite individual do Diretório.Vale ressaltar que o cadastro de usuários em sandbox e em produção são apartados, ou seja, um usuário ser administrador em produção não dá poderem em sandbox, nem vice e versa. Além disso, cadastro e senhas também são apartados.Clique para conferir o passo a passo para registro do usuárioClique para conferir o passo a passo para registro do administrador da organização[Clique para conferir o passo a passo para registro do usuário de domínio](https://openfinancebrasil.atlassian.net/wiki/x/mgIjO)Clique para conferir o passo a passo para registro do contato de notificação

---

# Lançamento Escalonado > Definições para o Lançamento Escalonado da Fase 3

---
id: 17378821
title: Definições para o Lançamento Escalonado da Fase 3
version: 1
modified: 2022-10-27T12:04:04.251Z
url: /spaces/OF/pages/17378821/Defini+es+para+o+Lan+amento+Escalonado+da+Fase+3
---

### Mensagens de erro para escalonamento da Fase 3
Estão disponíveis as orientações da Estrutura para comunicação com os usuários que passarem por algum erro na jornada, que seja ocasionado pelas definições de escalonamento da Fase 3. Mais especificamente, erros motivados por extrapolar limite de valor, limite de horário e/ou limite de público. A iniciadora deve garantir que o usuário seja impedido de iniciar um pagamento que extrapola as restrições impostas.
### Orientações quanto a restrição de iniciação em função do dispositivo do usuário.
A iniciadora de pagamentos em função do período de escalonamento poderá restringir o acesso a determinados dispositivos (Celular ou desktop) e jornadas em múltiplos devices, conforme determinações estabelecidas pelo regulador.Em ambos os casos, a iniciadora deverá avisar o cliente antes da jornada de redirecionamento seguindo as diretrizes de UX do Open Finance Brasil.
| | Código de erro | Mensagem de erro |
| --- | --- | --- |
| 1 | Response Code 422: limite de valor | O valor do pagamento ultrapassa o limite de R$ 1.000,00 estabelecido nesta fase inicial. O Open Finance está sendo disponibilizado gradualmente para garantir um sistema seguro e estável. |
| 2 | | DraftOFS.: Proposta a respeito das especificações devido à limitações do escalonamento: |
| 3 | | Em caso de extrapolação dos limites impostos para o lançamento escalonado, o consentimento não deve ser criado e a detentora deve retornar o seguinte de acordo com o caso: |
| 4 | | Limites operacionais (valor da transação): atributo DETALHE_PGTO_INVALIDO) |
| 5 | | Limites operacionais (funcionalidade): atributo FORMA_PGTO_INVALIDA) |
| 6 | | (Recomendação para que a Instituição Iniciadora sugira o que fazer, ex.: call to action) |
| 7 | Responde Code 425: limite de horário | Esta solicitação não poderá ser atendida pois está fora do horário de funcionamento estabelecido nesta fase inicial (recomendação para que a Instituição Iniciadora apresente a grade de horários, se quiser). O Open Finance está sendo disponibilizado gradualmente para garantir um sistema seguro e estável. |
| 8 | | DraftOFS.: O horário de funcionamento definido no normativo se refere à disponibilidade do endpoint POST do consentimento. Demais endpoints deverão ficar disponíveis por mais 1 hora. |
| 9 | | (Recomendação para que a Instituição Iniciadora sugira o que fazer, ex.: call to action) |
| 10 | Response Code 429: limite de público | No momento, a instituição detentora da conta não poderá atender esta solicitação, pois atingiu os limites de transações estabelecidos. O Open Finance está sendo disponibilizado gradualmente para garantir um sistema seguro e estável. |
| 11 | | (Recomendação para que a Instituição Iniciadora sugira o que fazer, ex.: call to action) |

---

# Monitoramento e Gestão de Consequências > Aderência das APIs das instituições participantes às especificações funcionais e de segurança

---
id: 498500006
title: Aderência das APIs das instituições participantes às especificações funcionais e de segurança
version: 2
modified: 2024-11-29T14:07:17.028Z
url: /spaces/OF/pages/498500006/Ader+ncia+das+APIs+das+institui+es+participantes+s+especifica+es+funcionais+e+de+seguran+a
---

item 2.2 - viiPurple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica visa garantir que as APIs das instituições participantes do Open Finance em ambiente produtivo estejam aderentes às especificações funcionais e de segurança estabelecidas. A Estrutura Responsável pela Governança do Open Finance verifica e exige essa conformidade para assegurar a integridade, segurança e eficiência do ecossistema do Open Finance.
## Sobre a Métrica
A métrica consiste na avaliação das APIs em ambiente produtivo das instituições participantes que estejam cadastradas no Diretório de Participantes do Open Finance. Seu objetivo é identificar desconformidades, ou seja, divergências entre as APIs publicadas em ambiente produtivo e as especificações funcionais e de segurança. A análise ocorre tanto no aspecto funcional quanto no de segurança das APIs.
### Especificações Funcionais

#### Verificação dos endpoints de Consents e Payments

- Verifica se todos os endpoints das APIs publicadas têm todos os endpoints publicados.
- Verifica se os endpoints de consents e payments estão acessíveis e conformes.

#### Verificação do logotipo

- Verifica se foi registrado um logotipo válido.
- Confirma se o logo é acessível.
- Valida se o logo é do tipo .svg e possui dimensões de no mínimo 512 de altura e 512 de largura.

#### Verificação do endpoint de Well-Known

- Verifica se o endpoint de well-known cadastrado no Diretório está válido e acessível em ambiente produtivo na instituição participante.

#### Verificação dos scopes suportados

- Valida se os scopes suportados pela instituição são válidos e declarados no well-known.
- Compara os scopes com os family types cadastrados no diretório pela organização.

#### Verificação de fluxos de DCR

- Verifica se o servidor de autorização da instituição realiza o fluxo DCR com diferentes configurações e se rejeita o fluxo DCR em cenários de erro.

## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será mensal, conforme orientado pelo Manual de Monitoramento do Open Finance Brasil. A avaliação envolverá:
#### Verificação das Especificações Funcionais

- Chamada aos endpoints de consents e payments, validação se as chamadas foram aceitas e se a resposta é válida, e verificação de respostas esperadas ao chamar o endpoint de payments-consents com diferentes tipos de parâmetros.
- Verificação do logotipo registrado, acessibilidade e conformidade com as especificações (.svg, dimensões mínimas de 512x512).
- Verificação se o endpoint de well-known está válido e acessível em ambiente produtivo.

#### Verificação das Especificações de Segurança

- Verificação do fluxo DCR com diferentes configurações, validação da cadeia de certificados, e rejeição do fluxo DCR em cenários de erro.
- Validação dos scopes suportados e comparação com os family types cadastrados no diretório pela organização.

## Interpretação dos Resultados
Os resultados da métrica serão interpretados para verificar se as instituições estão aderentes às especificações funcionais e de segurança das APIs em ambiente produtivo. A análise incluirá:
#### Especificações Funcionais

#### Verificação dos endpoints de Consents

- Chamada aos endpoints de consents e validação se as chamadas foram aceitas e se a resposta é válida.

#### Verificação dos Endpoints de Payments

- Chamada aos endpoints de payments, se disponíveis pela instituição, e validação se as chamadas foram aceitas e se a resposta é válida.
- Chamadas ao endpoint de payments-consents com diferentes tipos de parâmetros, como payments type igual a BAD, person type igual a INVALID, currency igual a XXX, utilizando uma data do passado, entre outros, para verificar se as respostas estão de acordo com o esperado, como retornar o código de erro 422 ou 400.

#### Verificação do logotipo

- Verificação se foi registrado um logotipo válido.
- Confirmação se o logo é acessível.
- Validação se o logo é do tipo .svg e possui dimensões de no mínimo 512 de altura e 512 de largura.

#### Verificação dos endpoints de Well-Known

- Verificação se o endpoint de well-known cadastrado no Diretório está válido e acessível em ambiente produtivo na instituição participante.ante.

### Especificações de Segurança

#### Verificação do fluxo DCR

- Verificação se o servidor de autorização da instituição realiza o fluxo DCR com diferentes configurações, como: Configurações básicas e sem campos adicionais. Alterando a ordem do parâmetro grant_types e adicionando o parâmetro opcional scopes. Com campo opcional scopes em ordem diferente. Chamada ao endpoint de token para receber um token.

#### Verificação da Cadeia de Certificados

- Verificação se a cadeia de certificados retornados pelos endpoints do servidor de autorização (token, registro) e endpoints funcionais estão de acordo com a RFC5246 - 7.4.2.
- Verificação se a CA é aceita pelo Open Finance Brasil.
- Validação se todas as certificações de segurança necessárias estão publicadas no diretório.
- Verificação se, para o novo perfil único, a instituição deve ter publicado exclusivamente a certificação BR-OF Adv. OP com Private Key, PAR (FAPI-BR v2).

#### Rejeição do Fluxo DCR em Cenários de Erro

- Utilizando Software Statement Assertion com assinatura inválida.
- Sem enviar o Software Statement Assertion.
- Sem adicionar os certificados TLS do cliente, verificando se as chamadas GET e DELETE são recusadas ao não utilizar os certificados TLS.
- Adicionando um certificado TLS não confiável, verificando se as chamadas GET e DELETE são recusadas ao utilizar um certificado TLS não confiável.
- Sem enviar o redirect_uri.
- Com um jwks_uri não presente no diretório.
- Enviando um jwks by_value.
- Utilizando um certificado emitido pela PKI do Diretório de Participantes em ambiente de Sandbox.
- Tentando registrar o DCR novamente, pois não devem ser permitidos múltiplos clients.
- Utilizando um certificado revogado pela CA.
- Após a deleção do client, executando as chamadas de GET e DELETE esperando a recusa às chamadas.
- Nas chamadas de GET e DELETE ao utilizar um access token inválido.

#### Verificação dos scopes Suportados

- Validação se os scopes suportados pela instituição são válidos e declarados no well-known.
- Comparação dos scopes com os family types cadastrados no diretório pela organização.
noteExemplo Ilustrativo
Exemplo Ilustrativo
Considere uma instituição em que o servidor de autorização não rejeite o fluxo DCR ao utilizar um Software Statement Assertion com assinatura inválida. Mesmo que todos os outros critérios estejam em conformidade, a métrica consideraria a instituição em desconformidade devido a esse único item não atendido. Em caso de desconformidade com algum dos critérios, a métrica deverá destacar o item em questão como um ponto de atenção.
## Dados e Fontes
Para o cálculo da métrica, utilizam-se os dados obtidos a partir do Diretório de Participantes e da Ferramenta de Validação de Produção (FVP). A FVP gera logs detalhados sobre o sucesso ou falha dos cenários de testes executados. Esses logs são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. A combinação dessas fontes de dados permite uma avaliação precisa da métrica e um monitoramento efetivo da conformidade regulatória no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
Squad Sandbox

---

# Monitoramento e Gestão de Consequências > Cadastro Atualizado das APIs

---
id: 498499760
title: Cadastro Atualizado das APIs
version: 2
modified: 2024-11-29T14:03:22.609Z
url: /spaces/OF/pages/498499760/Cadastro+Atualizado+das+APIs
---

ITEM 2.2 - IIPurple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica visa garantir que as informações relativas às APIs das instituições participantes armazenadas pela Estrutura Responsável pela Governança do Open Finance estejam corretas e atualizadas. A conformidade com esta métrica assegura a integridade e a eficácia do ecossistema do Open Finance.
## Sobre a Métrica
A métrica se baseia na verificação dos recursos das APIs das instituições participantes para determinar a conformidade das informações. Para que uma instituição esteja em conformidade com essa métrica, todos os critérios abaixo devem ser atendidos com sucesso para cada uma de suas marcas. A Estrutura Responsável pela Governança do Open Finance verifica e exige que as informações estejam corretas e atualizadas.
#### Recursos das APIs

- Verifica se os recursos das APIs publicadas têm todos os endpoints cadastrados.
- Confirma se o parâmetro FamilyComplete está definido como True.

## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será mensal, conforme orientado pelo Manual de Monitoramento do Open Finance Brasil. A metodologia de análise envolve:
- Recursos das APIs: Verificação da publicação completa dos endpoints das APIs e confirmação do parâmetro FamilyComplete como True.

## Interpretação dos Resultados
Os resultados da métrica serão interpretados para verificar se as instituições estão cumprindo os critérios de conformidade para o cadastro atualizado das APIs no Diretório de Participantes. A conformidade é evidenciada pelo parâmetro FamilyComplete definido como True, indicando que todos os endpoints previstos para uma família de APIs foram cadastrados.A desconformidade é pontuada quando forem localizadas hipóteses de falha contendo o valor 'Incomplete Family Type', evidenciando que nem todos os endpoints das APIs foram cadastrados para uma determinada família de APIs.noteExemplo Ilustrativo
Exemplo Ilustrativo
Considere uma instituição que, ao cadastrar seus endpoints no Diretório, não os tenha cadastrado integralmente, resultando no atributo FamilyComplete com o valor False. Nesse caso, a instituição seria pontuada em uma situação de desconformidade. 
## Dados e Fontes
Para o cálculo da métrica, utilizam-se os dados obtidos a partir do Diretório de Participantes e da Ferramenta de Validação de Produção (FVP). A FVP gera logs detalhados sobre o sucesso ou falha do cenário de teste executado. Esses logs são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. A combinação dessas fontes de dados permite uma avaliação precisa da métrica e um monitoramento efetivo da conformidade regulatória no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
Squad Sandbox

---

# Monitoramento e Gestão de Consequências > Certificação funcional e de segurança das APIs das instituições participantes

---
id: 498499806
title: Certificação funcional e de segurança das APIs das instituições participantes
version: 3
modified: 2024-11-29T14:04:08.827Z
url: /spaces/OF/pages/498499806/Certifica+o+funcional+e+de+seguran+a+das+APIs+das+institui+es+participantes
---

item 2.2 iiiPurple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica visa garantir que as instituições participantes do Open Finance certifiquem suas APIs, conforme a versão em vigor. A Estrutura Responsável pela Governança do Open Finance exige essa conformidade para assegurar a integridade, segurança e eficácia do ecossistema do Open Finance.
## Sobre a Métrica
A métrica leva em conta vários critérios para determinar a conformidade das APIs das instituições participantes. Para que uma instituição esteja em conformidade com essa métrica, todos os critérios a seguir devem ser cumpridos com sucesso para cada uma de suas marcas. A Estrutura Responsável pela Governança do Open Finance verifica e exige que as certificações estejam corretas e atualizadas.
#### Certificação Funcional

- Valida se a URI de certificação funcional está correta de acordo com a API ‘<api>’ e versão ‘<major>’. https://github.com/OpenBanking-Brasil/conformance/)(blob|raw)(/main/submissions/functional/)(<api>/)(<major>.\d.\d)(.*)(<month>)(-)(<year>)((.zip)|(.json))
- Verifica se a versão major disponível na URI da certificação funcional é a mesma, quando comparada com a versão major da API publicada.

#### Certificação de Segurança

- Verifica se a URI da certificação de segurança está registrada corretamente no cadastro do servidor de autorização do Diretório de Participantes.
- Valida se as certificações de segurança estão corretamente registradas no Diretório, verificando se a data de certificação está de acordo com a data do link e se a certificação não está expirada (com mais de 1 ano desde a data do link).

## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será no momento da detecção da desconformidade, conforme orientado pelo Manual de Monitoramento do Banco Central do Brasil. A metodologia de análise envolve:
- Certificação Funcional: Validação se a URI de certificação funcional está correta e se a versão major disponível na URI corresponde à versão major da API publicada.
- Certificação de Segurança: Verificação se a URI da certificação de segurança está registrada corretamente no cadastro do servidor de autorização do Diretório de Participantes e validação se as certificações de segurança estão corretas e não expiradas.

## Interpretação dos Resultados
Os resultados da métrica serão interpretados para verificar se as instituições estão cumprindo os critérios de conformidade para a certificação funcional e de segurança das APIs. A métrica avalia a existência das seguintes hipóteses de falha:
### Certificação Funcional

#### Incorrect API Certification URI

- A métrica avalia se a URI de certificação funcional não está correta de acordo com a API e versão especificadas.
- A desconformidade é pontuada se a URI não seguir o formato esperado ou se a versão major disponível na URI não corresponder à versão major da API publicada.

### Certificação de Segurança

#### Missing Security Certifications

- A métrica avalia se a URI da certificação de segurança não está registrada corretamente no cadastro do servidor de autorização do Diretório de Participantes.

#### Incorrect Certification URI

- A métrica avalia se a URI da certificação de segurança não está seguindo o formato correto ou não está acessível.

#### Missing CertificationStartDate

- A métrica avalia se a data de certificação de segurança não está devidamente preenchida no diretório.

#### Incorrect CertificationStartDate

- A métrica avalia se a data de certificação de segurança está correta e não expirada (com mais de 1 ano desde a data do link).
noteExemplo Ilustrativo
Exemplo Ilustrativo
Considerando uma instituição em que a URI da certificação de segurança não esteja registrada corretamente no cadastro do servidor de autorização do Diretório. Mesmo que todos os outros critérios estejam em conformidade, a métrica consideraria a instituição em desconformidade devido a esse único item não atendido. Em caso de desconformidade com algum dos critérios, a métrica deverá destacar o item em questão como um ponto de atenção.
## Dados e Fontes
Para o cálculo da métrica, utilizam-se os dados obtidos a partir do Diretório de Participantes e da Ferramenta de Validação de Produção (FVP). A FVP gera logs detalhados sobre o sucesso ou falha do cenários de testes executados. Esses logs são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. A combinação dessas fontes de dados permite uma avaliação precisa da métrica e um monitoramento efetivo da conformidade regulatória no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
Squad Sandbox

---

# Monitoramento e Gestão de Consequências > Cumprimento de marcos regulatórios e de outras exigências de testes para certificação de novas especificações

---
id: 498499714
title: Cumprimento de marcos regulatórios e de outras exigências de testes para certificação de novas especificações
version: 3
modified: 2025-03-25T14:16:35.425Z
url: /spaces/OF/pages/498499714/Cumprimento+de+marcos+regulat+rios+e+de+outras+exig+ncias+de+testes+para+certifica+o+de+novas+especifica+es
---

Item 2.2 - IPurple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |
| 2 | | Revisão geral do documento Inclusão do tópico “Interpretação dos Dados no Painel” |

## Introdução e Objetivos
Esta métrica tem como foco o cumprimento de marcos regulatórios e das exigências de testes para a certificação de novas especificações no âmbito do Open Finance. A responsabilidade de monitorar e assegurar o cumprimento destes pontos de controle, definidos tanto pela regulamentação quanto pela Estrutura Responsável pela Governança do Open Finance, é essencial para a integridade e eficácia do processo de publicação e atualização de APIs no ecossistema do Open Finance.O objetivo é garantir que todas as etapas, desde a publicação inicial até a implementação de novas versões das APIs, estejam em conformidade com os padrões estabelecidos, promovendo um ambiente de Open Finance seguro, eficiente e inovador. Esta métrica visa, portanto, avaliar a aderência e eficácia do processo de governança no cumprimento desses requisitos críticos.
## Sobre a Métrica
Para garantir a maturidade dos testes realizados no motor funcional e o desenvolvimento correto por parte das instituições, conforme o cronograma estabelecido pela regulamentação ou pela Estrutura Responsável pela Governança do Open Finance, propõe-se periodicamente marcos de certificação temporais. O objetivo é validar se o motor de testes funcionais está correto e se não há problemas nas especificações, estabelecendo assim um ciclo de maturidade a ser seguido. Dessa forma, são determinados quais planos de testes devem ser executados e quais módulos pertencentes aos planos devem ter sucesso até a data especificada no marco. Não se trata apenas de atingir um percentual de testes disponíveis, mas sim de garantir que, naquela data específica, a instituição tenha atingido o percentual de testes exigido. Os marcos definidos podem variar em sua porcentagem, dependendo do total de testes disponíveis para o plano e das potenciais correções e ajustes no motor, que podem incluir erros, mudanças nas especificações, entre outros. Essas variações podem resultar em uma nova data, um novo marco ou novos critérios de sucesso. Para os módulos que sofreram alterações relevantes, são consideradas apenas as execuções realizadas após a data em que a alteração do motor esteja planejada.A métrica em questão considera o percentual de testes realizados até a data estipulada para o marco de certificação, excluindo os testes com resultado de falha. O denominador do cálculo leva em conta os testes esperados de acordo com as APIs oferecidas pela instituição. Testes condicionais são adicionados ao cálculo para instituições com determinadas funcionalidades ou clientes específicos, como clientes PJ, temporização e múltiplas alçadas.
## Metodologia Simplificada
Para fins de monitoramento desse item, o período de apuração será no momento da detecção da desconformidade, conforme o Manual de Monitoramento do Open Finance.A metodologia para calcular a métrica de cumprimento dos marcos regulatórios e de testes no Open Finance é baseada na verificação periódica do sucesso nos testes funcionais exigidos. Essa verificação leva em conta:
- A porcentagem de testes bem-sucedidos em relação ao total de testes esperados, ajustada pelos critérios específicos de cada marco temporal estabelecido.
- A data da realização dos testes, considerando apenas os testes realizados após a última atualização significativa no motor de testes ou nas especificações.
- A inclusão de testes condicionais, baseada nas funcionalidades ou serviços específicos oferecidos pela instituição.

## Interpretação dos Resultados
Os resultados da métrica serão interpretados para avaliar se as instituições estão cumprindo os requisitos regulatórios associados aos marcos de certificação. O motor de conformidade funcional é a plataforma utilizada para a certificação das instituições participantes do Open Finance Brasil. Deste modo, uma instituição participante só estará apta a participar do Open Finance Brasil se passar em 100% dos testes obrigatórios e nos condicionais que se aplicam à instituição. A análise incluirá:
| Percentual de testes realizados |
| --- |
| Exemplo: Uma instituição que disponha das APIs de Consents , Resources e Câmbio, com 20, 5 e 8 testes respectivamente, deve realizar um total de 33 testes. Já uma instituição que não oferece produtos de Câmbio deve executar apenas os 25 testes obrigatórios de Consents e Resources . O total de testes esperados para um marco é arredondado para baixo. Por exemplo, se o total de testes para um marco de Consents , Resources e Câmbio fosse 33, um marco de 25% exigiria 8,25 testes, mas seria esperado o sucesso em 8 testes para alcançar o marco. |
| Desconformidades |
| Exemplo: Uma desconformidade será considerada sempre que uma API ou agrupamento de APIs não cumprir o percentual de testes obrigatórios na data prevista. Se o descumprimento do percentual de testes de uma API resultar em uma desconformidade e, na próxima data do marco, ocorrer outra desconformidade, mesmo que em uma API ou agrupamento de APIs diferentes, essa situação será considerada uma reincidência. |
noteExemplo Ilustrativo
Exemplo Ilustrativo
Considere uma instituição que disponha das APIs de *Consents*, *Resources* e Câmbio. Suponha que o total de testes esperados para um marco seja 37. Se o marco de 25% exigir 9,25 testes, será esperado o sucesso em 9 testes para alcançar o marco. Se a instituição não conseguir atingir esse número, ela será considerada em desconformidade. Caso ocorra uma nova desconformidade na próxima data do marco, mesmo que em APIs diferentes, essa situação será considerada uma reincidência.
## Interpretação dos Dados no Painel
As informações contidas neste item têm como objetivo ajudar o usuário a compreender cada um dos campos exibidos no painel de “Cumprimento de marcos regulatórios”. Desta forma, têm-se:
| Campos | Descrição |
| --- | --- |
| Conglomerado | selecionar o conglomerado desejado |
| Organização | selecionar a organização desejada |
Em “**Cumprimento de marcos regulatórios de especificações**”, têm-se:
| Campos | Descrição |
| --- | --- |
| Marco | selecionar o conglomerado desejado |
| Data do marco | selecionar uma data específica do marco ou selecionar todos os marcos |
| Status de conformidade | selecionar o status desejado ou todos os status |
| Conglomerado | exibição do conglomerado selecionado |
| Organização | exibição da organização pertencente ao conglomerado |
| Agrupamento | refere-se a uma API ou um grupo de APIs relacionadas aos testes |
| Marco | data referente ao marco |
| Data do marco | data em que o marco foi registrado |
| Módulos necessários | total de testes que devem ser realizados |
| Módulos com sucesso | total de testes realizados com sucesso |
| Status de conformidade | conforme ou não conforme |

## Dados e Fontes
Para o cálculo da métrica, utiliza-se um conjunto diversificado de dados provenientes de diferentes fontes. A principal ferramenta para a realização de testes é o motor funcional, que gera logs detalhados sobre o sucesso ou falha dos cenários de testes executados. Esses logs são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica.Adicionalmente, integram-se à PAD dados oriundos do Gerenciador de Configuração (GDC). O GDC por sua vez, consolida parâmetros adicionais para o cálculo da métrica, como datas de marcos regulatórios e o percentual de sucesso esperado em cada um desses marcos. Essas informações de configuração e parâmetros são mantidas e atualizadas pela Equipe de Aceleração e Interoperabilidade, garantindo que a métrica reflita os objetivos regulatórios e as expectativas de desempenho atuais.A sinergia entre os logs gerados pelos testes no motor funcional, as informações consolidadas na PAD e os dados de configuração do GDC permite uma avaliação precisa do cumprimento dos marcos regulatórios e das exigências de testes. Esta abordagem integrada assegura a confiabilidade e a relevância da métrica para o monitoramento efetivo no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela aprovação
Squad Sandbox
## Referências
As especificações desta métrica baseiam-se, referenciam e complementam, quando aplicável, os seguintes documentos do Banco Central do Brasil, que fornecem as diretrizes e requisitos que devem ser considerados para garantir a conformidade:
| Referência | Origem |
| --- | --- |
| INSTRUÇÃO NORMATIVA BCB Nº 575, DE 20 DE DEZEMBRO DE 2024 - versão 2.0 Manual de Monitoramento do Open Finance | |

---

# Monitoramento e Gestão de Consequências > Cumprimento regulatório das modalidades de participação

---
id: 498499905
title: Cumprimento regulatório das modalidades de participação
version: 2
modified: 2024-11-29T14:05:45.022Z
url: /spaces/OF/pages/498499905/Cumprimento+regulat+rio+das+modalidades+de+participa+o
---

item 2.2 - VPurple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica visa monitorar o cumprimento regulatório das modalidades de participação das instituições no ecossistema do Open Finance. A Estrutura Responsável pela Governança do Open Finance verifica se as modalidades de participação cadastradas pelas instituições participantes estão em conformidade com o estabelecido na regulamentação e adota as providências necessárias para a regularização, sempre que houver informações disponíveis para tal verificação.
## Sobre a Métrica
A métrica se baseia na identificação das modalidades de participação das instituições conforme o artigo 2º da Resolução Conjunta nº 1, de 4 de maio de 2020, e o devido cadastro das roles no Diretório de Participantes. Para integrar o ecossistema do Open Finance, as instituições credenciadas devem se cadastrar de acordo com seus papéis regulatórios, que refletem a autorização do Banco Central e determinam as APIs que podem utilizar. As modalidades assumidas pelos participantes no âmbito do Open Finance são auto declaratórias e podem ser exercidas simultaneamente. Contudo, tais modalidades deverão estar em conformidade com o modelo de negócio do participante e estarão sujeitas à verificação pela fiscalização do Banco Central do Brasil, especialmente com relação ao cumprimento do princípio da reciprocidade no compartilhamento de dados no Open Finance Brasil.
### Modalidades de participação

#### Instituição Transmissora e Receptora de Dados (role DADOS)

- Obrigatória para todas as instituições dos segmentos S1 e S2.
- Demais instituições autorizadas podem participar facultativamente, observando o princípio da reciprocidade.
- Instituições com a role DADOS devem publicar as APIs de Consents e Resources para o compartilhamento de dados.

#### Instituição Prestadora de Serviço de Iniciação de Pagamentos (role PAGTO)

- Destina-se às instituições que tenham publicado sua certificação OpenID Relying Party e constem na Lista de Participantes Ativos do Pix do BCB como iniciador de transação de pagamento.
- Devem ter obtido a certificação, e caso sua instituição também seja detentora de conta, deverá já ter obtido a certificação e publicação de suas APIs de serviços do Open Finance conforme item V, do artigo 2º, da Resolução Conjunta no. 1, de 4 de maio de 2020.
- Necessitam passar pelo processo de Onboarding de ITPs da Estrutura de Governança do Open Finance, com divulgação em um Informa emitido ao ecossistema.

#### Instituição Detentora de Conta (role CONTA)

- Destinada à instituição participante com a qual o cliente possui relacionamento e detém sua conta para movimentação de recursos.
- Verificação se as APIs de serviços estão cadastradas no Diretório para a instituição participante que tenha declarado a role CONTA.
- Não há base de dados disponível para consulta prévia junto ao BCB, sendo necessário análise comparativa com os endpoints declarados pela instituição.

#### Correspondente de Crédito (role CCORR)

- Destinada às instituições participantes que tenham firmado contrato de correspondente no país para recepção e encaminhamento de propostas de operações de crédito e de arrendamento mercantil.
- A role CCORR no Diretório de Participantes do Open Finance ainda não está em vigor e será discutida em um momento futuro.

## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será mensal, conforme orientado pelo Manual de Monitoramento do Open Finance Brasil. A avaliação envolverá:
- Identificação das modalidades no Diretório: Verificação das modalidades de participação de cada instituição no Diretório de Participantes.
- Publicação das APIs: Checagem das APIs publicadas conforme as roles declaradas.
- Conformidade com regulamentações: Avaliação da conformidade das modalidades de participação e APIs publicadas com as regulamentações vigentes.

## Interpretação dos Resultados
Os resultados da métrica serão interpretados para verificar se as instituições estão cumprindo os requisitos regulatórios associados às suas modalidades de participação. Para fins de monitoramento, a instituição estará em desconformidade, o que ocasionará o apontamento do item em desconformidade para o conglomerado ao qual essa organização pertence. A análise incluirá:
- A verificação das Instituições Transmissora de Dados (role DADOS) envolve confirmar se a role DADOS está declarada em reivindicações de domínio de autoridade (Authority Domain Claim) e se a instituição possui um servidor de autorização para exposição das APIs de serviços, exclusivamente com uma ou mais das APIs payments-consents, payments-pix, payments-pix-recurring-payments, payments-recurring-consents e enrollments. Essa verificação da marca exclusiva como detentora de conta possibilita identificar todos os demais servidores de autorização que devem conter as APIs consents, resources e customer-business ou customer-personal para estarem conformes. Se a organização não possuir um servidor de autorização, deve possuir preenchido o atributo ParentOrganisationReference no Diretório. Para organizações com marcas exclusivas detentoras de contas, não há obrigatoriedade de compartilhamento de dados por essas marcas, inferindo-se que o compartilhamento é realizado pela infraestrutura da organização mãe em uma marca distinta.
- A verificação das Instituições Iniciadoras de Transação de Pagamento (role PAGTO) envolve confirmar se a role PAGTO está declarada no software statement da instituição, e se a instituição passou pelo processo de onboarding, indicado pela flag "Habilitada para Iniciação de Pagamento" ou flag "Em processo de onboarding de ITP". A verificação do software statement também abrange o ITP puro, que pode não dispor de authorisation server.
- A verificação das Instituições Detentoras de Conta (role CONTA) envolve confirmar se a role CONTA está declarada em reivindicações de domínio de autoridade (Authority Domain Claim) no Diretório, e se as APIs family types ‘payments-consents', 'payments-pix', 'payments-pix-recurring-payments', 'payments-recurring-consents’ está cadastrada em pelo menos um dos authorisation servers da instituição.
- Correspondente de Crédito (role CCORR): A declaração da role CCORR está em espera e não será avaliada para fins de monitoramento da métrica até futura regulamentação.
noteExemplo Ilustrativo
Exemplo Ilustrativo
Considere uma instituição do segmento S1 com a role DADOS declarada no Diretório. A verificação será feita para assegurar que a instituição publicou as APIs ‘consents', ‘resources' e 'customer-personal’ ou 'customer-business’. Se uma Instituição Prestadora de Serviço de Iniciação de Pagamentos (role PAGTO) declarou essa role no Diretório e no software statement, mas não possui flag "Habilitada para Iniciação de Pagamento" ou "Em processo de onboarding de ITP", ela será considerada em desconformidade. Além disso, instituições Detentoras de Conta devem ter a role CONTA declarada em reivindicações de domínio de autoridade (Authority Domain Claim) e as APIs family types ‘payments-consents', 'payments-pix', 'payments-pix-recurring-payments', 'payments-recurring-consents’ cadastrada em pelo menos um dos servidores de autorização para estar em conformidade.
## Dados e Fontes
Para o cálculo da métrica, utilizam-se os dados obtidos a partir do Diretório de Participantes do Open Finance. Esses dados são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. Diferentemente das demais informações que atualmente são mantidas pelas instituições, as flags que demonstram que uma instituição concluiu e/ou está participando do processo de onboarding são mantidas e atualizadas pela Equipe de Aceleração e Interoperabilidade.A combinação dessas fontes de dados permite uma avaliação precisa da métrica e um monitoramento efetivo da conformidade regulatória no contexto do Open Finance, garantindo que a métrica reflita os objetivos observados.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
Squad Sandbox

---

# Monitoramento e Gestão de Consequências > Disponibilidade de APIs

---
id: 795017220
title: Disponibilidade de APIs
version: 3
modified: 2025-03-25T15:20:03.814Z
url: /spaces/OF/pages/795017220/Disponibilidade+de+APIs
---

## Controle de versão

| Versão | Data | Resumo das alterações |
| | | |
| 1 | | Versão inicial |
| 2 | 31 de jan. de 2025 | Segregação da métrica de desempenho de APIs da métrica de disponibilidade de APIs. Maior detalhamento do cálculo da métrica. |
| 3 | | Revisão geral do documento Inclusão do tópico “Interpretação dos Dados no Painel” |

## Introdução e Objetivos
Esta métrica visa monitorar se os *endpoints* das APIs das instituições participantes estão cumprindo os SLAs de disponibilidade, estabelecidos no Manual de APIs do Open Finance.Considerando que a disponibilidade dos *endpoints* das APIs do *Open Finance* será calculada empiricamente, baseada na monitoração de requisições válidas.
## Sobre a Métrica
A métrica de Disponibilidade das APIs mede a capacidade de uma API estar acessível e funcionando corretamente para os desenvolvedores e usuários finais.As medições devem ser feitas todos os dias, em todas as faixas de 1 minuto disponíveis, iniciando na primeira faixa (00:00:00-00:00:59) e terminando na última faixa (23:59:00-23:59:59), considerando o horário de Brasília.As medições devem ser realizadas de maneira independente para cada versão "*major*" dos *endpoints* em produção.O *status code* a ser considerado para uma requisição é o valor reportado pelo consumidor da API, ou seja, o valor reportado pela instituição iniciadora de pagamentos nas APIs de “Serviços de Iniciação de Pagamentos” e o valor reportado pela receptora de dados no caso de APIs de "Dados Cadastrais e Transacionais".****Na falta de informações dos consumidores, serão utilizadas as informações dos provedores para o cálculo do SLA de disponibilidade, ou seja,  o valor reportado pela instituição detentora de contas nas APIs de "Serviços de Iniciação de Pagamentos", e o valor reportado pela instituição transmissora de dados no caso de APIs de "Dados Cadastrais e Transacionais".A indisponibilidade programada não exime o cálculo da disponibilidade no período apurado.A disponibilidade de *endpoints* que não tenham requisições válidas no período apurado será considerada "indefinida", não estando sujeita a um SLA.Cada um dos *endpoints* das APIs categorizadas como "Dados Abertos", "Dados Cadastrais e Transacionais", "Relatórios e Métricas", por versão, e os *endpoints* das APIs de "Segurança" "/*register*" e "/*token*", deverão satisfazer os requisitos mínimos de disponibilidade abaixo:I - disponibilidade diária (calendário): 95%; eII - disponibilidade longa (média móvel de 90 dias), medida diariamente: 99,5%.As APIs classificadas como "Serviços de Iniciação de Pagamentos" seguem o definido na regulamentação do Pix, ou seja, ou seja os participantes têm metas de índice de disponibilidade diferentes, de acordo com as suas categorias de participação no arranjo:
| Categoria | Disponibilidade |
| --- | --- |
| A | 99,5% |
| B | 99,0% |
| C | 98,5% |
| D | 95,0% |
A conformidade é avaliada mensalmente, verificando se os *endpoints* das APIs das instituições participantes atenderam aos SLAs de disponibilidade. A aferição mensal deve considerar a disponibilidade longa do último dia do mês de referência.
## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será mensal, conforme orientado pelo Manual de Monitoramento do Open Finance Brasil. A avaliação envolverá:Para as APIs de “Dados Abertos", "Dados Cadastrais e Transacionais", "Relatórios e Métricas", por versão, e os *endpoints* das APIs de "Segurança" "/*register*" e "/*token*":
- Disponibilidade diária: monitoramento da disponibilidade em todos os dias do mês de referência.
- Disponibilidade longa: monitoramento da da disponibilidade longa como média móvel dos últimos 90 dias.
Para as APIs de “Serviços de Iniciação de Transação de Pagamentos” monitoramento mensal de acordo com a regulamentação do Pix, .
## Aspectos Técnicos
O monitoramento inclui várias etapas:
| AGRUPAR POR MINUTO E CONTAR AS REQUISIÇÕES COM SUCESSO E ERRO |
| Filtragem |
| organisationid = clientorgid OU ( organisationid = s erverorgid E status = 'UNPAIRED' ) statuscode = 2xx, 5xx, 408 ou 422 status ≠ “PAIRED_INCONSISTENT” |
| Agrupamento |
| serverorgid endpoint dia minuto |
| Contar as requisições por tipo |
| total_validas → total de chamadas success → total chamadas com status code 2xx ou 422 error → total chamadas com status code 5xx OU 408 |
| CALCULAR A DISPONIBILIDADE DO MINUTO |
| Para cada minuto, realiza o cálculo do percentual de disponibilidade: |
| AGRUPAR POR DIA E CALCULAR O TOTAL DE MINUTOS DISPONÍVEIS |
| Agrupamento |
| orgid do servidor ponto final dia |
| Cálculo |
| total_validas_dia → total de chamadas no dia total_minutos_disponiveis → total disponibilidade_no_minuto ≥ 95% total_minutos → total de minutos do dia |
| CALCULAR DISPONIBILIDADE E CONFORMIDADE DIÁRIA, MENSAL E LONGA |
| Disponibilidade diária |
| |
| Conformidade diária |
| Porcentagem_disp_dia ≥ 0,95  = CONFORME Porcentagem_ disp _dia < 0,95  = NÃO CONFORME |
| Disponibilidade mensal (iniciação de pagamentos) |
| percent_disp_mensal = média mensal de percent_disp_dia |
| Conformidade mensal (Iniciação de pagamentos) |
| percent_disp_mensal ≥  categoria de disponibilidade Pix da instituição = CONFORME percent_disp_mensal <  categoria de disponibilidade Pix da instituição = NÃO CONFORME |
| Disponibilidade longa |
| percent_disp_u90d = média dos últimos 90 dias de percent_disp_dia |
| Conformidade longa |
| percent_disp_u90d ≥ 0.995 = CONFORME percent_disp_u90d < 0.995 = NÃO CONFORME |

## Interpretação dos Resultados
Os resultados da métrica serão interpretados para verificar se as instituições estão cumprindo os critérios de conformidade para disponibilidade das APIs. A análise incluirá:
### Disponibilidade das APIs

#### Disponibilidade Diária

- A disponibilidade pontual (t) é calculada como a fração do total de requisições válidas processadas com sucesso a cada intervalo de 1 minuto. Por exemplo, a disponibilidade pontual de um endpoint referente ao minuto 11:34, de um determinado dia, no qual houve um total de requisições válidas com sucesso de 255 e um total de requisições válidas com erro de 4, é calculada da seguinte forma:
A disponibilidade diária é calculada baseada nas informações das disponibilidades pontuais.
#### Disponibilidade Longa

- A disponibilidade longa é calculada diariamente como média móvel das disponibilidades dos últimos 90 dias corridos. Por exemplo, a disponibilidade longa do último dia de março é a média das disponibilidades diárias dos últimos 90 dias.
A conformidade para a disponibilidade das APIs depende da conformidade em todos os dias da disponibilidade diária das APIs e da sua disponibilidade longa, considerando o último dia do mês de apuração. As APIs de “Serviços de Iniciação de Pagamentos” seguem as metas do índice de disponibilidade do arranjo Pix.noteExemplo Ilustrativo
Exemplo Ilustrativo
Para ilustrar as condições de conformidade e desconformidade, considere os seguintes exemplos:
#### Conformidade
Por exemplo, considerando um dia (ex.: 10/06/2024) em que houve requisições válidas em 1.360 das 1.440 faixas de 1 minuto possíveis (1 dia = 24h * 60min= 1.440 faixas de horário) para um *endpoint* específico "x" de versão 1, e dos quais 30 períodos tiveram a disponibilidade menor que o limite de disponibilidade definido (95%), a Disponibilidade Diária de "x" v1 será igual a:
## Interpretação dos Dados no Painel
As informações contidas neste item têm como objetivo ajudar o usuário a compreender cada um dos campos exibidos no painel de “Disponibilidade”. Desta forma, têm-se:Em “**Controles**”:
| Campos | Descrição |
| Mês análise | informar a data ou período desejado, podendo ser uma data relativa ou intervalo de datas absoluto |
| Conglomerado | selecionar o conglomerado desejado |
| Visualizar organização | selecionar a opção “sim” para exibir os detalhes da organização pertencentes ao conglomerado ou a opção “não” para exibir o resultado por conglomerado |
Em “**Desconformidade Consolidada**” é apresentado o resultado consolidado da apuração mensal por conglomerado e/ou organização, de acordo com o filtro selecionado em “**Controles**”.O painel é interativo. Por exemplo, ao clicar na célula “**NÃO CONFORME**” do conglomerado ou da organização, será exibido os detalhamentos do mês de apuração. Além disso, é possível maximizar a visualização do painel e exportar os dados para CSV ou Excel.Nos detalhes da “**Desconformidade Mensal**”, têm-se:
| Campos | Descrição |
| Mês análise | mês referente a apuração |
| Organização | organização selecionada em “Controles” |
| Diária | resultado referente ao mês de apuração da disponibilidade diária |
| Longa | resultado referente ao mês de apuração da disponibilidade longa |
| Serviços | resultado referente ao mês de apuração da disponibilidade de serviços |
**Importante**: as células vazias representam conformidade.Para que o detalhamento seja exibido, deve-se clicar nas células “NÃO CONFORME” nas colunas “Diária”, “Longa” ou “Serviços”.Em “**Disponibilidade Diária**”, têm-se:
| Campos | Descrição |
| Dia análise | dia do mês referente a apuração |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Nr. minutos disponíveis | total de minutos disponíveis de um determinado dia |
| Nr. minutos indisponíveis | total de minutos indisponíveis de um determinado dia |
| Disponibilidade diária | percentual da disponibilidade diária de um determinado dia |
| Status | não conforme * |
*****Só serão exibidos os resultados não conformes.Ao clicar nas células das colunas “**nr. minutos disponíveis**” ou “**nr. minutos indisponíveis**” serão exibidos os detalhamentos dos dados em “**Disponibilidade Pontual**”.Em “**Disponibilidade Pontual**”, têm-se:
| Campos | Descrição |
| Intervalo minuto | intervalo em que a requisição apresentou sucesso ou erro |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Método HTTP | método da requisição |
| Nr. requisições válidas c/ sucesso | total requisições válidas com sucesso no intervalo de um determinado minuto |
| Nr. requisições válidas c/ erro | total requisições válidas com erro no intervalo de um determinado minuto |
| Disponibilidade pontual | percentual da disponibilidade pontual aferida |
**Importante**: serão exibidos no máximo cinco evidências de reporte.Em “**Disponibilidade Longa**”, têm-se:
| Campos | Descrição |
| Mês análise | mês referente a análise |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Disponibilidade aferida | percentual da disponibilidade aferida na requisição |
| Meta disponibilidade longa | meta definida da disponibilidade longa |
| Status | não conforme * |
*****Só serão exibidos os resultados não conformes.Em “**Disponibilidade de Serviços**”, têm-se:
| Campos | Descrição |
| Mês análise | mês referente a análise |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Disponibilidade aferida | percentual da disponibilidade aferida na requisição |
| Meta mensal índice de disponibilidade | meta mensal definida do índice de disponibilidade |
| Status | não conforme * |
*****Só serão exibidos os resultados não conformes.
## Dados e Fontes
Para o cálculo da métrica, utiliza-se um conjunto diversificado de dados provenientes de diferentes fontes. A principal fonte informacional é a Plataforma de Coleta de Métricas (PCM), que consolida os dados a partir dos reportes enviados pelas instituições participantes. Além disso, as planilhas auto reportadas pelas instituições são integradas e consolidadas na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. Essa combinação de dados provenientes da PCM e das planilhas auto reportadas permite uma avaliação precisa da métrica e um monitoramento efetivo do desempenho e disponibilidade das APIs no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
GT Arquitetura

---

# Monitoramento e Gestão de Consequências > Gestão de Monitoramento e Medidas

---
id: 922288135
title: Gestão de Monitoramento e Medidas
version: 4
modified: 2025-05-09T13:40:02.718Z
url: /spaces/OF/pages/922288135/Gest+o+de+Monitoramento+e+Medidas
---

16falsenonelisttrue
# Controle de versão

| Número do POP | Versão | Data | Resumo das alterações |
| 01 | 001 | | Versão inicial |
| 01 | 002 | | Alteração dos fluxogramas |

# 1. Introdução e Objetivos
Este Procedimento Operacional Padrão (POP) visa documentar e detalhar as etapas do fluxo de “**Gestão de Monitoramento e Medidas**”, com base nas métricas dispostas na versão 2.0 do Manual de Monitoramento do Open Finance.
# 2. Tickets Consolidadores
Conforme disposto na Instrução Normativa BCB n.º 575/2024, item 3:*“Caso seja detectado que uma instituição participante não esteja em conformidade com um item monitorado, o caso deve ser acompanhado por um ticket do Service Desk, podendo ser utilizado um ticket que já tinha sido aberto referente ao caso ou ser aberto novo ticket, específico ou que consolide diversas situações de desconformidade.”*A seguir, serão detalhadas as etapas de abertura, acompanhamento e fechamento dos *tickets* relacionados aos “Itens monitorados em situação de desconformidade”, denominados “tickets consolidadores”. O objetivo desses tickets é comunicar à Instituição Participante a ocorrência de uma ou mais desconformidades identificadas no mês de apuração.
### 2.1 Área responsável
A diretoria responsável pelo Monitoramento deverá realizar a abertura, acompanhamento e encerramento dos tickets consolidadores e dos planos de adequação, avaliação interna da taxa específica e diagnóstico por empresa especializada da taxa de conversão.
### 2.2 Métricas Monitoradas
Conforme disposto na IN 575 BCB n.º 575/2024, as métricas monitoradas são:
| Item correspondente a IN | Resumo da métrica monitorada |
| 2.1 Performance de APIs e requisitos não funcionais | I – Tempo de resposta das APIs das instituições participantes II – Disponibilidade das APIs das instituições participantes III – Volume de requisições com  status code  HTTP 529 |
| 2.2 Especificações, cadastros, certificação e publicação de APIs | I – Cumprimento de marcos regulatórios II – Cadastro de APIs III – Certificação funcional e de segurança das APIs IV – Publicação de APIs pelas instituições participantes V – Modalidades de participação VII – Aderência das APIs |
| 2.3 Metas de prazo máximo para atendimento de tickets | I – tickets relativos a demandas de resolução de incidentes, abertos bilateralmente entre instituições participantes no Service Desk II – tickets abertos pela Estrutura de Governança do Open Finance |
| 2.4 Reporte de informações | Reportes relacionados à Plataforma de Coleta de Métricas (PCM) e ao Motor de Qualidade de Dados (MQD) |
| 2.5 Qualidade de Dados | Índice de Qualidades de Dados (IQD) |
| 2.6.1 Jornada do Cliente | Guia de Monitoramento UX |
| 2.6.2 Taxa de Conversão | Jornadas de compartilhamento de dados e de iniciação de pagamentos |

### 2.3 Apuração e consolidação dos resultados
Cada métrica possui um prazo de apuração específico, devido à imutabilidade dos dados e aos períodos estabelecidos para o fechamento das informações. A contagem para o início da apuração tem como marco o dia 15 (quinze) de cada mês, acrescido de 2 (dois) dias úteis. Por exemplo, para apuração dos dados referentes ao mês de janeiro de 2025, a contagem se inicia no mês subsequente, em dia 15 de fevereiro (sábado) e finaliza no dia 18, terça-feira.
### 2.4 Abertura dos tickets consolidadores dos itens em situação de desconformidade
A seguir, serão apresentadas as etapas para a abertura do *ticket* consolidador. Os tickets devem ser abertos pela diretoria responsável pelo Monitoramento para as instituições participantes, exclusivamente para aquelas que apresentaram desconformidade em um ou em alguns dos itens monitorados. Nessas situações, deve-se abrir um único ticket, especificando todos os itens que estão em desconformidade.
1. Acessar o Service Desk: https://servicedesk.openfinancebrasil.org.br/Login.jsp?navLanguage=pt-BR ;
2. Inserir login e senha;
3. No canto superior direito, acessar “Portal do usuário final” ( Figura 1 );
Figura 1 - Service Desk - Portal do usuário final
1. Selecionar a opção “Requisições” ( Figura 2 );
Figura 2 - Service Desk - Requisições 
1. Selecionar “Conformidade – Monitoração de Gestão e Consequências” ( Figura 3 );
Figura 3 - Service Desk - Conformidade - Monitoração e Gestão de Consequências
1. Selecionar “Desconformidades” ( Figura 4 );
Figura 4 - Service Desk - Desconformidades
1. Selecionar “Análise de Desconformidades” ( Figura 5 );
Figura 5 - Service Desk - Análise de Desconformidades
1. Será exibida a tela “Enviar Solicitação” ( Figura 6 ). Deve-se preencher todos os campos, conforme orientações a seguir:

- Instituição requerente : inserir a opção “Open Banking Brasil – Chicago”;
- Equipe de atendimento : inserir o conglomerado desejado. Caso o conglomerado desejado não esteja disponível na lista, deve-se selecionar N2_Inst_Pendentes;
:note:atlassian-note#F4F5F7O “N2_Inst_Pendentes” correspondem às instituições que não estão cadastradas na lista de seleção. Por esse motivo, o nome da instituição participante em desconformidade deve ser mencionado no início da descrição do texto, conforme exemplo a seguir: “Prezados responsáveis pela Instituição/Conglomerado “Banco ABC”...”. 
- Título : inserir “Itens monitorados em situação de desconformidade”;
- Descrição : inserir texto padrão:

| Prezados responsáveis pela Instituição/Conglomerado,  Apuração: [ mês de apuração/ano da apuração ] O Manual de Monitoramento do Open Finance estabelece que as instituições participantes devem estar em conformidade com as obrigações previstas na regulamentação do Banco Central do Brasil e em documentos elaborados pela Estrutura Responsável pela Governança do Open Finance. Caso seja detectado que uma instituição participante não esteja em conformidade com um item monitorado, o caso deve ser acompanhado por um ticket do Service Desk Após analisar o painel de acompanhamento das situações de desconformidade, constatamos que pelo menos uma instituição do seu conglomerado não está cumprindo as obrigações estipuladas no manual de monitoramento em um ou mais dos itens relacionados Caso a instituição não concorde com os apontamentos de desconformidade, deverá devolver para a equipe de monitoramento as justificativas e anexar as evidências nesse ticket, comprovando a conformidade Concordando com os apontamentos, a instituição deverá anexar a este ticket o relatório de situações de desconformidade, contendo a descrição detalhada do ocorrido e as soluções adotadas para a correção. O relatório deve ser aprovado e acompanhado da ciência do diretor responsável pelo compartilhamento de dados e serviços no âmbito do Open Finance Dados importantes:  Versão 2.0 do Manual de Monitoramento do Open Finance IN BCB Nº 575: https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=575 Os itens monitorados do Manual de Monitoramento devem ser acompanhados pela Área de Gestão de Desconformidade (Quicksight) pelo link: https://desconformidades.openfinancebrasil.org.br/  A gestão de acesso à Plataforma de Visualização de Dados do Open Finance, que inclui o painel de desconformidades e outros dashboards, deverá ser realizada pelo administrador da instituição no Diretório de participantes através do cadastro de usuário de domínio da organização ‘PDV’ ou ‘SDV’ no sistema ‘Data Visualization Plataform’. Usuários PDV podem adicionar e excluir membros do grupo SDV; Usuários SDV têm acesso limitado, sem permissão para adicionar ou excluir membros. O guia de Itens Monitorados e Métricas pode ser acessado pela Área do Desenvolvedor pelo link: https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/498499604/Guia+de+Itens+Monitorados+e+M+tr+cas A Política de Monitoramento pode ser visualizada por meio deste link: https://openfinancebrasil.org.br/politica-de-monitoramento/ " |
| --- |

- Itens monitorados : adicionar todos os itens monitorados (métricas) que estiverem em desconformidade, podendo ser um ou mais. Ao clicar em “ +Adicionar ”, será exibida uma lista com todos os itens monitorados disponíveis para seleção;
- Ao finalizar, deve-se clicar em “ Enviar ” ( Figura 6 ).
Figura 6 - Service Desk - Enviar solicitaçãoApós o envio da solicitação, um número de ticket será gerado. Toda gestão do ticket será realizada com base nesse número de chamado.
### 2.5 Prazo de atendimento do ticket consolidador
O ticket possui um prazo de atendimento de até 5 (cinco) dias úteis, dentro do qual a instituição deverá realizar as devidas interações.
### 2.6 Apresentação do Relatório de Situações de Desconformidade
Conforme informado no campo “Descrição” durante a abertura do ticket, a instituição deverá analisar os apontamentos realizados e, caso não concorde com as desconformidades indicadas, deverá retornar o ticket à equipe de Monitoramento, apresentar as devidas justificativas, anexar as evidências que comprovem a conformidade e alterar o *status* do ticket para “ENCAMINHADO PARA OPERAÇÃO DE MONITORAMENTO” (**Figura 7**). Após a alteração de *status*, o SLA permanecerá pausado até que a estrutura responsável analise as evidências apresentadas.Caso a diretoria responsável pelo Monitoramento avalie que não houve a desconformidade, o ticket será cancelado e um novo será aberto, contendo apenas os itens cuja desconformidade tenha sido procedente, reiniciando-se o fluxo. Caso contrário, o ticket permanecerá aberto.Figura 7 - Service Desk - Alteração de *status* ticketSe a instituição concordar com os apontamentos, deverá anexar ao ticket o relatório de situações de desconformidade, no prazo até 5 (cinco) dias úteis, contendo a descrição detalhada do ocorrido e as soluções adotadas para a correção. O relatório deve ser aprovado e acompanhado da ciência do diretor responsável pelo compartilhamento de dados e serviços no âmbito do Open Finance.A diretoria responsável pelo Monitoramento receberá o relatório aprovado junto a ciência do diretor e encerará o ticket. **Importante**: o ticket deve ser encerrado pela Estrutura do Open Finance.Caso o relatório de situações de desconformidade não seja aprovado pela diretoria responsável pelo Monitoramento ou se a instituição, quando solicitada, não apresentar o relatório dentro do prazo estipulado, será necessário elaborar e apresentar o Plano de Adequação, conforme descrito no [https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#4.1-Solicita%C3%A7%C3%A3o-do-Plano-de-Adequa%C3%A7%C3%A3o](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#4.1-Solicita%C3%A7%C3%A3o-do-Plano-de-Adequa%C3%A7%C3%A3o).
# 3. Ocorrência Reiterada
A ocorrência reiterada é a apresentação de situação de desconformidade em relação a um mesmo item monitorado por uma instituição participante. Cada item monitorado possui regras, caso seja configurado uma ocorrência reiterada:
| Item monitorado correspondente a IN 575 | Regra da ocorrência reiterada |
| 2.1 Performance de APIs e requisitos não funcionais | Decurso de três períodos de apuração após detecção da desconformidade inicial. O período de apuração para fins de detecção de ocorrência reiterada é mensal. |
| 2.2 Especificações, cadastros, certificação e publicação de APIs |
| 2.3 Metas de prazo máximo para atendimento de tickets |
| 2.4 Reporte de informações |
| 2.5 Qualidade de Dados |
| 2.6.2 Taxa de Conversão |
| 2.6.1 Jornada do Cliente | Decurso de quatro períodos de apuração após detecção da desconformidade inicial. O período de apuração para fins de detecção de ocorrência reiterada é mensal. |

### 3.1 Primeira ocorrência reiterada
Caso a instituição participante apresente situação de desconformidade em relação a um mesmo item monitorado de forma reiterada, deverá apresentar à Estrutura de Governança do Open Finance o plano de adequação, conforme descrito no item****[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#4.1-Solicita%C3%A7%C3%A3o-do-Plano-de-Adequa%C3%A7%C3%A3o](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#4.1-Solicita%C3%A7%C3%A3o-do-Plano-de-Adequa%C3%A7%C3%A3o).
### 3.2 Segunda ocorrência reiterada
Em caso de segunda ocorrência reiterada, o Conselho de Administração deve comunicar o Banco Central do Brasil, com conhecimento da instituição participante, a respeito do caso com, no mínimo, as seguintes informações:
- Item monitorado descumprido;
- Relato descritivo do caso;
- Histórico de todas as informações disponíveis; e
- Documentação comprobatória.
Após a comunicação ao Banco Central do Brasil, a diretoria responsável pelo Monitoramento deve continuar acompanhando a instituição participante em situação de desconformidade, que deverá apresentar novos planos de adequação até a completa regularização. Uma vez sanada a desconformidade, a Estrutura de Governança do Open Finance deverá informar o Banco Central do Brasil.
### 3.3 Taxa de conversão inferior a 60%
Caso a desconformidade não configurar em ocorrência reiterada, mas a Taxa de Conversão estiver inferior a 60%, a Diretoria Responsável pelo Monitoramento deverá solicitar a avaliação especifica sobre Taxa de Conversão, conforme descrito no item [https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#5.-Avalia%C3%A7%C3%A3o-espec%C3%ADfica-da-Taxa-de-Convers%C3%A3o](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#5.-Avalia%C3%A7%C3%A3o-espec%C3%ADfica-da-Taxa-de-Convers%C3%A3o) .
# 4. Plano de Adequação
O plano de adequação deve ser elaborado caso a instituição participante apresente ocorrência reiterada em uma mesma situação de desconformidade ou apresente ocorrência reiterada no decurso de três ou quatro períodos de apuração, conforme descrito nos itens****[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#3.1-Primeira-ocorr%C3%AAncia-reiterada](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#3.1-Primeira-ocorr%C3%AAncia-reiterada) e [https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#3.2-Segunda-ocorr%C3%AAncia-reiterada](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/917766173/Gest+o+de+Monitoramento+e+Medidas#3.2-Segunda-ocorr%C3%AAncia-reiterada).Conforme disposto no item 3.2.2 da IN BCB 575/2024, o plano de adequação deve:*“*I - ser apresentado pela instituição participante em desconformidade;II - conter cronograma detalhado para que a situação de desconformidade seja solucionada e elementos mitigadores para prevenção de novas ocorrências;III - ser assinado pelo diretor responsável pelo compartilhamento de dados e serviços no âmbito do Open Finance;IV - ser apresentado por meio de canais oficiais da instituição participante em até dez dias úteis após solicitação da Estrutura de Governança do Open Finance; eV - ser avaliado e aprovado pela Estrutura de Governança do Open Finance*”.*
### 4.1 Abertura de ticket de solicitação do plano de adequação
Uma vez que a instituição participante apresente a ocorrência reiterada, a diretoria responsável pelo Monitoramento deverá abrir ticket solicitando a apresentação do plano de adequação. A seguir, serão detalhadas as etapas para abertura do ticket:
1. Acessar o Service Desk: https://servicedesk.openfinancebrasil.org.br/Login.jsp?navLanguage=pt-BR ;
2. Inserir login e senha;
3. No canto superior direito, acessar “Portal do usuário final” ( Figura 8 );
Figura 8- Service Desk - Portal do usuário final
1. Selecionar a opção “Requisições” ( Figura 9 );
Figura 9 - Service Desk - Requisições
1. Selecionar “Conformidade – Monitoração de Gestão e Consequências” ( Figura 10 );
Figura 10 - Service Desk - Conformidade - Monitoração e Gestão de Consequências
1. Selecionar “Desconformidades” ( Figura 11 );
Figura 11 - Service Desk - Desconformidades 
1. Selecionar “Apresentação do Plano de Adequação” ( Figura 12 );
Figura 12 - Service Desk - Apresentação do Plano de Adequação
1. Será exibida a tela “Enviar Solicitação” ( Figura 13 ). Deve-se preencher todos os campos, conforme orientações a seguir:

- Instituição requerente : inserir a opção “Open Banking Brasil – Chicago”;
- Equipe de atendimento : inserir o conglomerado desejado. Caso o conglomerado desejado não esteja disponível na lista, deve-se selecionar N2_Inst_Pendentes;
:note:atlassian-note#F4F5F7O “N2_Inst_Pendentes” correspondem às instituições que não estão cadastradas na lista de seleção. Por esse motivo, o nome da instituição participante em desconformidade deve ser mencionado no início da descrição do texto, conforme exemplo a seguir: “Prezados responsáveis pela Instituição/Conglomerado “Banco ABC”...”. 
- Título : inserir “Identificação de Ocorrência Reiterada e Solicitação de Plano de Adequação”;
- Número do ticket de análise de desconformidade : inserir o número do ticket consolidador
- Descrição : inserir texto padrão:

| Prezados,  Em conformidade com a Instrução Normativa 575, destacamos que, após a identificação da primeira desconformidade em um item monitorado, qualquer nova ocorrência relacionada ao mesmo item, dentro dos períodos especificados, será configurada como uma Ocorrência Reiterada  Nesse sentido, informamos que foi constatada nova ocorrência de desconformidade no(s) seguinte(s) item(s) monitorado listado(s)  Com base no inciso II da subseção 3.2, solicitamos a apresentação de um Plano de Adequação que atenda integralmente aos seguintes requisitos: Cronograma detalhado para solucionar a situação de desconformidade identificada; Elementos mitigadores para prevenir novas ocorrências relacionadas ao item em questão; Assinatura do diretor responsável, que assegure a responsabilidade e o comprometimento no âmbito do compartilhamento de dados e serviços do Open Finance  Os critérios aplicáveis para a configuração de Ocorrência Reiterada estão previstos no inciso 3.3 da IN BCB nº 575: https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=575 |
| --- |

- Itens monitorados : adicionar todos os itens monitorados (métricas) que estiverem em desconformidade e que configuraram a ocorrência reiterada. Ao clicar em “ +Adicionar ”, será exibida uma lista com todos os itens monitorados disponíveis para seleção ( Figura 13 );
- Ao finalizar, deve-se clicar em “ Enviar ”.
Figura 13 - Service Desk - Abertura tick plano de adequação
### 4.2 Prazo de atendimento do ticket e a elaboração do plano de adequação
O ticket de solicitação do plano de adequação possui um prazo de atendimento de 10 (dez) dias úteis. Ao receber a solicitação, a instituição participante deverá, dentro desse período, elaborar o plano de adequação e anexar ao ticket, contendo a assinatura do diretor.O plano de adequação deve ser avaliado e aprovado pela diretoria responsável pelo Monitoramento. Caso a participante não apresente o plano de adequação dentro do prazo regulamentar, a diretoria responsável pelo Monitoramento deve dar ciência ao Banco Central comunicando o ocorrido por e-mail ao Desup ([openfinance.desup@bcb.gov.br](mailto:openfinance.desup@bcb.gov.br)), Desuc ([openfinance.desup@bcb.gov.br](mailto:openfinance.desup@bcb.gov.br)) e Denor ([openfinance.denor@bcb.gov.br](mailto:openfinance.denor@bcb.gov.br)).
### 4.3 Minuta de e-mail para comunicação ao Banco Central do Brasil sobre a situação do plano de adequação

| [Data] Ao Banco Central do Brasil [ Departamento responsável ] Assunto: Comunicação de Não Apresentação do Plano de Adequação no Prazo Estabelecido Prezados Senhores, Em cumprimento a Instrução Normativa 575 de 20/12/2024, comunicamos que a instituição/conglomerado [inserir razão social e CNPJ da instituição ] não apresentou o Plano de Adequação dentro do prazo estabelecido, conforme demonstram as evidências anexas. Colocamo-nos à disposição para quaisquer esclarecimentos adicionais que se façam necessários. Atenciosamente, [Nome do Responsável] Estrutura de Governança Open Finance |
| --- |

# 5. Avaliação específica sobre a Taxa de Conversão
A avaliação específica sobre a taxa de conversão deve ser elaborada e apresentada pela instituição participante quando a taxa de conversão (experiência do cliente) estiver inferior a 60%, devendo:I - conter diagnóstico sobre sua taxa de conversão;II - ser apresentada em até dez dias úteis após a detecção da desconformidade; eIII - ter seus resultados submetidos à Estrutura de Governança do *Open Finance* e ao Banco Central do Brasil.A avaliação mencionada neste tópico poderá ser elaborada pela própria instituição, desde que aborde os itens previamente indicados e seja realizada dentro do prazo estabelecido.
### 5.1 Abertura de ticket de solicitação de avaliação específica da taxa de conversão
Caso a instituição participante apresente uma taxa de conversão inferior a 60%, a diretoria responsável pelo Monitoramento deverá abrir um ticket solicitando a avaliação específica dessa taxa. A seguir, serão descritas as etapas para a abertura do ticket:
1. Acessar o Service Desk: https://servicedesk.openfinancebrasil.org.br/Login.jsp?navLanguage=pt-BR ;
2. Inserir login e senha;
3. No canto superior direito, acessar “Portal do usuário final” ( Figura 14 );
Figura 14 - Service Desk - Portal do usuário final
1. Selecionar a opção “Requisições” ( Figura 15 );
Figura 15 - Service Desk - Requisições 
1. Selecionar “Conformidade – Monitoração de Gestão e Consequências” ( Figura 16 );
Figura 16 - Conformidade – Monitoração de Gestão e Consequências
1. Selecionar “Desconformidades” ( Figura 17 );
Figura 17 - Service Desk - Desconformidades
1. Selecionar “Apresentação Avaliação Específica da Taxa de Conversão” ( Figura 18 );
Figura 18 - Service Desk - Apresentação Avaliação Específica da Taxa de Conversão
1. Será exibida a tela “ Enviar Solicitação ” ( Figura 19 ). Deve-se preencher todos os campos, conforme orientações a seguir:

- Instituição requerente : inserir a opção “Open Banking Brasil – Chicago”;
- Equipe de atendimento : inserir o conglomerado desejado. Caso o conglomerado desejado não esteja disponível na lista, deve-se selecionar N2_Inst_Pendentes;
:note:atlassian-note#F4F5F7O “N2_Inst_Pendentes” correspondem às instituições que não estão cadastradas na lista de seleção. Por esse motivo, o nome da instituição participante em desconformidade deve ser mencionado no início da descrição do texto, conforme exemplo a seguir: “Prezados responsáveis pela Instituição/Conglomerado “Banco ABC”...”. 
- Título : inserir “Avaliação interna sobre taxa de conversão”;
- Número do ticket de análise de desconformidade : inserir o número do ticket consolidador
- Descrição : inserir texto padrão:

| Prezados, Em conformidade com a Instrução Normativa 575 e com o disposto no inciso III da subseção 3.2, destacamos que essa instituição apresentou taxa de conversão inferior a 60% das taxas mínimas estabelecidas na subseção 2.6.2. Diante dessa desconformidade, solicitamos a apresentação de um diagnóstico detalhado sobre a taxa de conversão, contemplando: Análise das causas da baixa conversão; Medidas adotadas para correção; Estratégias para prevenir novas ocorrências. Além disso, informamos que, após análise da Estrutura de Governança do Open Finance, caso a maior parte dos erros que resultaram na taxa de conversão abaixo do patamar exigido esteja relacionada a aspectos técnicos ou à jornada do cliente, a instituição deverá contratar uma empresa especializada independente para realizar um diagnóstico mais completo sobre a taxa de conversão da instituição participante em desconformidade. |
| --- |

- Itens monitorados : adicionar os itens relacionados a métrica da taxa de conversão que estiverem em desconformidade ( Figura 19 ). Ao clicar em “ +Adicionar ”, será exibida a lista com os itens monitorados relacionados as taxas de conversão para seleção ( Figura 20 );

1. Ao finalizar, deve-se clicar em “ Enviar ”.
Figura 19 - Service Desk - Abertura de ticket avaliação específica da taxa de conversãoFigura 20 - Lista para seleção dos itens relacionados a taxa de conversãoA instituição deverá anexar a avaliação elaborada diretamente no ticket e encaminhar para análise da diretoria responsável pelo Monitoramento.
### 5.2 Análise da avaliação específica da taxa de conversão
Após análise da diretoria responsável pelo Monitoramento, caso seja identificado que a maioria dos erros que resultaram a taxa de conversão inferior a 60% está relacionada a aspectos de implementação, sejam eles de natureza técnica ou ligados à jornada do cliente, a instituição participante em desconformidade deverá contratar empresa especializada independente para realizar um diagnóstico mais completo sobre a taxa de conversão da instituição participante em desconformidade. 
### 5.3 Abertura de ticket de solicitação de diagnóstico por empresa especializada
A seguir, serão apresentadas as etapas para a abertura do ticket de solicitação a instituição participante em desconformidade, para contratação e apresentação do diagnóstico elaborado por empresa especializada. Para isso, é necessário::
1. Acessar o Service Desk: https://servicedesk.openfinancebrasil.org.br/Login.jsp?navLanguage=pt-BR ;
2. Inserir login e senha;
3. No canto superior direito, acessar “Portal do usuário final” ( Figura 21 );
Figura 21 - Service Desk - Portal do usuário final
1. Selecionar a opção “Requisições” ( Figura 22 );
Figura 22 - Service Desk - Requisições 
1. Selecionar “Conformidade – Monitoração de Gestão e Consequências” ( Figura 23 );
Figura 23 - Conformidade – Monitoração de Gestão e Consequências
1. Selecionar “Desconformidades” ( Figura 24 );
Figura 24 - Desconformidades
1. Selecionar “Diagnóstico Taxa de Conversão” ( Figura 25 );
Figura 25 - Diagnóstico de Taxa de Conversão
1. Será exibida a tela “ Enviar Solicitação ” ( Figura 26 ). Deve-se preencher todos os campos, conforme orientações a seguir:

- Instituição requerente : inserir a opção “Open Banking Brasil – Chicago”;
- Equipe de atendimento : inserir o conglomerado desejado. Caso o conglomerado desejado não esteja disponível na lista, deve-se selecionar N2_Inst_Pendentes;
:note:atlassian-note#F4F5F7O “N2_Inst_Pendentes” correspondem às instituições que não estão cadastradas na lista de seleção. Por esse motivo, o nome da instituição participante em desconformidade deve ser mencionado no início da descrição do texto, conforme exemplo a seguir: “Prezados responsáveis pela Instituição/Conglomerado “Banco ABC”...”. 
- Título : inserir “Diagnóstico Taxa de conversão”;
- Número do ticket de análise de desconformidade : inserir o número do ticket consolidador
- Descrição : inserir texto padrão:

| Prezados, Em conformidade com a Instrução Normativa 575 e com o disposto no item 3.2.3, destacamos que, após a análise realizada pela Estrutura de Governança do Open Finance, da Avaliação específica sobre a Taxa de Conversão, foi identificado que a maior parte dos erros que resultaram na taxa de conversão abaixo do patamar exigido esteja relacionada a aspectos técnicos ou à jornada do cliente. Sendo assim, a instituição deverá contratar empresa especializada independente para realizar um diagnóstico mais completo sobre a taxa de conversão. O relatório completo deverá ser apresentado no prazo de 90 (noventa) dias corridos. |
| --- |

- Itens monitorados : adicionar os itens relacionados a métrica da taxa de conversão que estiverem em desconformidade ( Figura 26 ). Ao clicar em “ +Adicionar ”, será exibida a lista com os itens monitorados relacionados as taxas de conversão para seleção;

1. Ao finalizar, deve-se clicar em “ Enviar ”.
Figura 26 - Service Desk - Abertura ticket diagnóstico taxa de conversão
### 5.4 Prazo para apresentação do diagnóstico por empresa especializada
O referido diagnóstico deve ser apresentado em até 90 (noventa) dias corridos após solicitação da diretoria responsável pelo Monitoramento e tem validade de 12 (doze) meses.
# 6. Fluxograma
Os fluxogramas apresentados nas **Figuras 27**a**32**, sintetizam os possíveis cenários e os principais aspectos abordados neste Procedimento Operacional Padrão. Para melhor visualização, clique na imagem ou faça o download. A**Figura 27** ilustra o 'Cenário 1' de abertura do ticket consolidador para o Banco ABC, correspondente a três itens monitorados no mês de apuração de janeiro de 2025.Figura 27 - Cenário 1 - Banco ABC - Abertura de Ticket Consolidador (Análise De Desconformidade) - Jan/25A **Figura 28** ilustra o 'Cenário 2' de abertura do ticket consolidador para o Banco ABC, correspondente a três itens monitorados no mês de apuração de fevereiro de 2025.Figura 28 - Cenário 2 - Banco ABC - Abertura de Ticket Consolidador (Análise De Desconformidade) - Fev/25 A **Figura 29** ilustra o 'Cenário 3' de abertura do ticket de Plano de Adequação para o Banco ABC, em decorrência de ocorrência reiterada relacionada a dois itens monitorados no mês de apuração de fevereiro de 2025.Figura 29 - Cenário 3 - Banco ABC - Abertura de Ticket de Plano de Adequação em função de ocorrência reiterada - Fev/25  A **Figura 30** ilustra o 'Cenário 1' de abertura do ticket consolidador para o Banco FGV, correspondente a três itens monitorados no mês de apuração de janeiro de 2025.Figura 30 - Cenário 1 - Banco FGV - Abertura de Ticket Consolidador (Análise De Desconformidade) - Jan/25A **Figura 31** ilustra o 'Cenário 2' de abertura do ticket Avaliação Interna específica da Taxa de Conversão do Banco FGV, referente ao mês de apuração fevereiro de 2025, por apresentar valor inferior a 60%.Figura 31 - Cenário 2 - Banco FGV - Abertura de Ticket Avaliação específica interna da Taxa de Conversão inferior a 60% - Fev/25A **Figura 32** ilustra o 'Cenário 1' correspondente às comunicações realizadas ao Banco Central do Brasil e à ciência dada às instituições participantes, na detecção de segunda ocorrência reiterada.Figura 32 - Banco EBX - Comunicação ao Banco Central do Brasil e à ciência dada as instituições participantes

---

# Monitoramento e Gestão de Consequências > Metas de prazo máximo para atendimento de tickets

---
id: 782401538
title: Metas de prazo máximo para atendimento de tickets
version: 4
modified: 2025-04-02T17:56:31.266Z
url: /spaces/OF/pages/782401538/Metas+de+prazo+m+ximo+para+atendimento+de+tickets
---

Item 2.3Purple
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |
| 2 | | Alteração da nomenclatura da métrica de "Requisição de informação, sugestão de melhorias e demanda de resolução de incidentes" para "Meta de prazo máximo para atendimento de tickets". Flexibilização do percentual de tickets atendidos dentro do prazo máximo para fins de análise de desconformidade, conforme versão 2.0 do Manual de Monitoramento do Open Finance. |
| 3 | | Revisão geral do documento Inclusão dos tópicos “Interpretação dos Dados no Painel” e “Período de Apuração dos Dados” |

## Introdução e Objetivos
Esta métrica visa monitorar se as instituições participantes do Open Finance estão respeitando os prazos máximos de atendimento de tickets estabelecidos no Manual de Serviços Prestados pela Estrutura de Governança do Open Finance. Esses tickets incluem: I - Tickets bilaterais****abertos entre instituições participantes no Service Desk*,*relativos a demandas de resolução de incidentes.II- Tickets abertos pela Estrutura de Governança do Open Finance**que compreendem aqueles abertos por órgãos da Estrutura de Governança do Open Finance, fornecedores e ferramentas.
## Sobre a Métrica
A métrica de “Prazo Máximo para Atendimento de Tickets” é uma medida quantitativa que avalia o tempo decorrido entre a abertura de um ticket e sua resolução final. O prazo máximo para atendimento é estabelecido no Manual de Serviços Prestados pela Estrutura de Governança do Open Finance. A conformidade é avaliada mensalmente, considerando que as instituições participantes devem atender ao **prazo máximo para pelo menos 80% de seus tickets elegíveis para a métrica, sem apresentar tickets com atraso superior ao dobro do prazo máximo estabelecido**.
## Metodologia Simplificada
A metodologia adotada para o monitoramento e análise dos tickets inclui várias etapas:
| Classificação dos tickets | Qualificação das categorias, subcategorias e categorias de 3° nível com “Sim” no atributo “Métricas de Monitoramento”, no  Service Desk , dos tickets que serão elegíveis para fins da avaliação de conformidade |
| --- | --- |
| Análise de prazos de atendimento dos tickets | Avaliação dos prazos de atendimento desses tickets, identificando a quantidade de tickets que no período de apuração se encontram abertos ou encerrados dentro do prazo estabelecido versus a quantidade daqueles com prazo vencido, calculando o percentual de tickets atendidos dentro do prazo |
| Avaliação detalhada dos tickets com prazo vencido | Cálculo para verificar se os dias em atraso dos tickets com prazo vencido, são superiores ao dobro dos dias de prazo do seu SLA |
Os tickets **não elegíveis** são:
| Categoria | Subcategoria | Categoria de 3º Nível |
| Monitoração e Gestão de Consequência | Desconformidades | Painel - Informações |
| Monitoração e Gestão de Consequência | Desconformidades | Painel - Melhorias |
| Monitoração e Gestão de Consequência | Notificação | - |
| Processo de onboarding | - | - |

## Interpretação dos Resultados
Admite-se, para fins de avaliação sobre a conformidade deste item monitorado, que as instituições participantes atendam ao prazo máximo para 80% dos tickets**elegíveis para fins desta avaliação, desde que não apresentem tickets com atraso superior ao dobro do seu prazo máximo.A mensuração da quantidade de tickets por mês contempla:
- Tickets cujo prazo de SLA esteja no mês de apuração;
- Tickets não resolvidos cujo prazo de SLA seja anterior o mês de apuração;
- Tickets resolvidos no mês de apuração cujo prazo de SLA seja anterior ao mês apuração.
note
#### Exemplo Ilustrativo

#### Exemplo Ilustrativo

No exemplo da Figura 1, é possível visualizar o número total de tickets em cada um dos meses apresentados, assim como os diferentes cenários de resolução.Figura 1 - Possíveis cenários de resolução dos tickets
## Período de Apuração dos Dados
Para fins do processo de monitoramento, o período de apuração referente a este item é mensal, compreendendo sempre entre o primeiro e o último dia no mês. 
## Interpretação dos Dados no Painel
As informações contidas neste item têm como objetivo ajudar o usuário a compreender cada um dos campos exibidos no painel de “**Atendimento dos tickets**”. Desta forma, têm-se:Em “**Controles**”:
| Campos | Descrição |
| Mês apuração | informar a data ou período desejado, podendo ser uma data relativa ou intervalo de datas absoluto |
| Conglomerado | selecionar o conglomerado desejado |
| Visualizar organização | selecionar a opção “sim” para exibir os detalhes da organização pertencentes ao conglomerado ou a opção “não” para exibir o resultado por conglomerado |
Em “**Desconformidade mensal**” é apresentado o resultado consolidado da apuração mensal por conglomerado e/ou organização, de acordo com o filtro selecionado em “**Controles**”.O painel é interativo. Por exemplo, ao clicar na célula “**NÃO CONFORME**” do conglomerado ou da organização, serão exibidos os detalhamentos do mês de apuração. Além disso, é possível maximizar a visualização do painel e exportar os dados para CSV ou Excel.**Importante**: As células em branco indicam conformidade.Em “**Detalhes mês apuração**” têm-se, o resultado por conglomerado e por organização.
| Campos | Descrição |
| Conglomerado e/ou Organização | exibição do conglomerado e/ou organização selecionada em “Controles” |
| Mês apuração | mês referente a apuração |
| Total acima dobro SLA | quantidade total de tickets que se encontram acima do dobro do prazo do SLA |
| % mês conforme | percentual total dos tickets encerrados dentro do prazo de SLA no mês de apuração |
Em “**Tickets referentes ao mês de apuração**” têm-se:
| Campos | Descrição |
| Conglomerado | exibição do conglomerado selecionado |
| Organização | exibição da organização selecionado |
| Mês apuração | mês referente a apuração |
| Ticket | número do ticket referente a apuração |
| Tipo | tipo do ticket apurado (bilateral ou estrutura) |
| Categoria | categoria em que o ticket está enquadrado |
| Subcategoria | subcategoria em que o ticket está enquadrado |
| Data de abertura | data de abertura e/ou solicitação do ticket |
| Prazo SLA | data máxima para resolução ticket |
| Data fechamento | data em que o ticket foi encerrado |
| Dias excedente SLA | quantidade total de dias excedentes do prazo do SLA |
| Acima do dobro SLA | "sim" indica que o ticket ultrapassou o dobro do prazo do SLA, enquanto "não" significa que o ticket não ultrapassou o dobro do prazo do SLA |

## Dados e Fontes
Para a execução desta métrica, são utilizadas informações oriundas do sistema de *Service Desk* utilizado pela Estrutura de Governança do Open Finance e pelas instituições participantes. Os dados incluem, mas não se limitam a data de solicitação, data de encerramento, prazo de SLA, SLA em dias, SLA dias em atraso e Métricas de Monitoramento. Esses dados são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica.Os tickets sem SLA foram classificados no atributo de “Métricas de Monitoramento” como não elegíveis para a avaliação deste item monitorado.A data de fechamento que está sendo considerada para os tickets da Subcategoria de “Jornada de UX” e categoria de 3° nível “Descumprimento Ditame Regulatório” corresponde à data na qual o ticket é atualizado para CORREÇÃO IMPLEMENTADA. 
## Limitações e Considerações
O monitoramento dos prazos máximos de atendimento de tickets estabelecidos no Manual de Serviços Prestados pela Estrutura de Governança do Open Finance, resulta num status de conformidade ou desconformidade de acordo com a data de referência da avaliação, que é sempre o primeiro dia do mês posterior ao de apuração, e por isso, o cancelamento de tickets que ocorrerem após a data de referência, não ensejarão mudança de status de conformidade.
## Responsável pela Aprovação
GT Infraestrutura

---

# Monitoramento e Gestão de Consequências > Métricas de Desconformidade Consolidadas

---
id: 1319993668
title: Métricas de Desconformidade Consolidadas
version: 1
modified: 2025-11-28T11:51:41.067Z
url: /spaces/OF/pages/1319993668/M+tricas+de+Desconformidade+Consolidadas
---

# Introdução e Objetivos
Este documento tem como finalidade apresentar a estrutura, a lógica e o propósito do dashboard consolidado das 13 métricas de desempenho. O painel foi desenvolvido para centralizar, em um único ambiente, informações que anteriormente estavam distribuídas em dashboards individuais, facilitando a visualização integrada e permitindo uma análise mais rápida e eficiente.O objetivo principal é fornecer uma visão unificada que apoie tomadas de decisão, reduza o tempo de navegação entre diferentes relatórios e aumente a consistência das análises. Além disso, o documento descreve o funcionamento do painel, suas principais seções, filtros, regras de cálculo aplicadas e a origem dos dados utilizados.
# Sobre as Métricas
O dashboard consolidado reúne **14 métricas principais**, das quais **13** são provenientes de uma mesma fonte de dados e **1 métrica** é obtida separadamente a partir da **fonte PAD**. Para permitir a integração adequada no QuickSight, foram criados **dois datasets**:
1. um dedicado ao tratamento da métrica derivada da fonte PAD;
2. outro contendo o tratamento das demais 13 métricas, incluindo o join com a métrica da fonte PAD para compor a visão consolidada.
Embora grande parte das métricas já venha parcialmente tratada em suas bases de origem, algumas exigiram tratamentos adicionais diretamente nas queries, tanto para padronização de campos quanto para alinhamento das regras de cálculo.Um ponto crítico do processo foi a inconsistência nos **nomes de conglomerados e instituições** entre diferentes métricas. Para garantir uniformidade, foi necessário aplicar um tratamento de padronização dentro das queries: todos os nomes disponíveis foram mapeados e, para cada *parent_organisation_reference*, foi selecionado apenas o **primeiro nome válido e recorrente**, evitando divergências e duplicidades entre indicadores.Esse conjunto de tratamentos garante consistência e comparabilidade entre todas as métricas consolidadas no dashboard.
### 2.1.I Tempo de Resposta APIs:
A métrica já é fornecida pronta na base `bl_desempenho_consolidado_conformidade_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.1.II Disponibilidade APIs:
A métrica já é fornecida pronta na base `bl_disponibilidade_consolidado_conformidade_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.1.III Requisições Status Code HTTP 529:
A métrica já é fornecida pronta na base `bl_server_overloaded_conformidade_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.2.I Implementações Novas versões APIs:
A métrica já é fornecida pronta na base `bl_acomp_versoes_apis_conformidade_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.2.II Versões Implementadas de APIs e artefatos associados:
A métrica já é fornecida pronta na base `bl_acomp_apis_artefatos_conformidade`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.2.III Modalidades de participação:
A métrica já é fornecida pronta na base `bl_modalidades_participacao_conformidade_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.2.IV Retirada das versões antigas das APIs:
A métrica já é fornecida na base `bl_retirada_api_consolidado_mensal`, porém **somente os registros “NÃO CONFORME” aparecem na fonte**.
No tratamento, foi realizado o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name` e, no dashboard, todos os valores **nulos foram considerados como “CONFORME”**, garantindo a classificação completa.
### 2.3 SLA Tickets:
A métrica não é fornecida pronta na base `vw_dl_service_desk_ticket_mensal`, sendo necessário realizar todo o tratamento dentro da query.
O tratamento inclui a criação de um calendário de dias úteis, cálculo de prazos de SLA, dias úteis decorridos, classificação por “DENTRO do SLA” / “FORA do SLA” e verificação do dobro do SLA.
Após os cálculos, os resultados foram **agrupados por**`parent_organisation_reference`**e**`mes_analise` para aplicar a regra final de conformidade.
### 2.4.1. Report Informações:
A métrica já é fornecida pronta na base `bl_reporte_info_pcm_mqd_conformidade_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.4.2 Planilha autorreportada:
A métrica já é fornecida pronta na base `bl_controle_respondentes_mensal`.
O tratamento realizado foi apenas o **agrupamento por**`parent_organisation_reference`**,**`mes_analise`**e**`parent_organisation_name`, aplicando a regra de conformidade conforme a base.
### 2.5 Qualidade Dados:
Esta métrica vem de uma fonte diferente das demais (PAD), sendo fornecida pela base `mqd.vw_quicksight_conglomerate_iqd`. O tratamento realizado consistiu na aplicação da regra de conformidade considerando **IQA ≥ 0,95 como CONFORME**, seguida do **agrupamento por**`parent_organisation_reference`**e**`mes_analise`.
### 2.6.1 Jornada do Cliente:
Esta métrica ainda não foi desenvolvida, pois está em processo de revisão da forma de cálculo e **não possui uma base final disponível** para implementação no momento.
### 2.6.2.1 Taxa Conversão Transmissor:
A métrica utiliza a base `bl_consentimento_transmissor_taxa_conversao`.
O tratamento realizado foi a **conversão do campo**`ano_mes`**para data**, a definição do nome da organização a partir do campo `transmissor` e a aplicação da regra de conformidade, onde **“NOTIFICAÇÃO” foi considerado como “NÃO CONFORME”**.
### 2.6.2.2 Taxa Conversão Detentor:
métrica utiliza a base `bl_funil_detentor_taxa_conversao`.
O tratamento realizado foi a **conversão do campo**`ano_mes`**para data**, a definição do nome da organização a partir do campo `detentora` e a aplicação da regra de conformidade, onde **“NOTIFICAÇÃO” foi tratado como “NÃO CONFORME”**.
### 2.6.2.3 Taxa Conversão Vinculo:
A métrica utiliza a base `bl_taxa_conversao_consolidado_mensal`, filtrada apenas para registros cujo `source = 'Vinculo'`.
O tratamento realizado foi o **agrupamento por**`parent_organisation_reference`**e**`mes_analise`, aplicando a regra de conformidade conforme o status da base.
### Sobre a query de consolidação das métricas:
Essa etapa cria uma base única contendo todas as organizações e meses presentes em qualquer uma das métricas. Para isso, o bloco **consolidado** faz um *UNION* de todas as tabelas de métricas (tempo de resposta, disponibilidade, requisições, implementações, versões, modalidades, retiradas, reports, autorreport, vínculo, transmissor, detentor e SLA), garantindo que nenhuma combinação de *parent_organisation_reference* e *mes_analise* fique de fora.Em seguida, cada métrica é incorporada por meio de **LEFT JOIN** usando essas duas chaves. O nome da organização é unificado com **COALESCE**, assegurando que, mesmo quando a nomenclatura varia entre as bases, apenas um nome final seja retornado.Por fim, a seleção filtra apenas registros com **parent_organisation_reference** e nome válidos, evitando linhas nulas ou não identificadas.

---

# Monitoramento e Gestão de Consequências > Publicação das APIs pelas instituições participantes

---
id: 498499852
title: Publicação das APIs pelas instituições participantes
version: 2
modified: 2024-11-29T14:04:54.172Z
url: /spaces/OF/pages/498499852/Publica+o+das+APIs+pelas+institui+es+participantes
---

## ITEM 2.2 - IV Purple

## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica visa garantir que as instituições participantes do Open Finance publiquem devidamente suas APIs, conforme os requisitos estabelecidos pela regulamentação e pela Estrutura Responsável pela Governança do Open Finance. A métrica monitora a conformidade das APIs e suas versões atuais registradas no Diretório de Participantes e no ambiente produtivo, assegurando a consistência e disponibilidade das APIs em ambos os ambientes.
## Sobre a Métrica
A métrica abrange a verificação das APIs e suas versões atuais registradas no Diretório de Participantes e no ambiente produtivo, de acordo com o cronograma estabelecido pela regulamentação ou pela Estrutura Responsável pela Governança do Open Finance, incluindo o período de convivência das versões.
- Consistência entre Diretório e ambiente produtivo: A métrica verifica se as APIs registradas no Diretório estão publicadas no ambiente produtivo das instituições participantes. A desconformidade é identificada se houver diferenças entre o que está registrado no Diretório e o que foi publicado no ambiente produtivo.
- Disponibilidade de versões atuais e em desuso: Durante o período de convivência, tanto a versão atual (current) quanto a versão em desuso (deprecated) das APIs devem estar disponíveis no Diretório e no ambiente produtivo. A desconformidade é identificada se qualquer uma dessas versões não estiver publicada conforme exigido.
- Identificação de endpoints no ambiente produtivo: A identificação dos endpoints no ambiente produtivo é feita por meio de requisições aos endpoints analisados. Requisições respondidas com o código de status HTTP 404 por mais de 8 horas são consideradas como indisponíveis no contexto dessa métrica.

## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será no momento da detecção da desconformidade, conforme orientado pelo Manual de Monitoramento do Banco Central do Brasil (BCB). A avaliação envolverá:
- Verificação de Consistência: Comparação entre as APIs registradas no Diretório e as APIs publicadas no ambiente produtivo.
- Checagem da Disponibilidade: Monitoramento da disponibilidade das versões atuais e em desuso das APIs durante o período de convivência.
- Teste de Endpoints: Requisições aos endpoints analisados para verificar a disponibilidade das APIs no ambiente produtivo.

## Interpretação dos Resultados
Os resultados da métrica serão utilizados para identificar instituições que não estão cumprindo com os requisitos de publicação das APIs, conforme estabelecido pela regulamentação e pela Estrutura Responsável pela Governança do Open Finance. A análise incluirá:Consistência entre Diretório e ambiente produtivo: Verificação se todas as APIs registradas no Diretório estão publicadas no ambiente produtivo.
Disponibilidade de versões atuais e em desuso: Confirmação de que ambas as versões das APIs (current e deprecated) estão disponíveis durante o período de convivência.
Disponibilidade dos endpoints: Identificação de endpoints que respondem com o código de status HTTP 404 por mais de 8 horas.
noteExemplo Ilustrativo
Exemplo Ilustrativo
Suponha que uma instituição tenha registrado no Diretório de Participantes a API Canais de Atendimento (*channels*). A métrica estará em desconformidade se a API estiver presente no Diretório, mas não tiver sido disponibilizada no ambiente produtivo da instituição.Além disso, considere que essa API esteja na sua versão atual (*current*) 2.0.0 e que sua versão anterior esteja marcada como em desuso (*deprecated*) na versão 1.0.2. Durante o período de convivência, ambas as versões devem estar disponíveis tanto no Diretório quanto no ambiente produtivo. Se alguma dessas versões não estiver publicada, a instituição estará em desconformidade em relação ao item monitorado.
## Dados e Fontes
Para o cálculo da métrica, utilizam-se os dados obtidos a partir do Diretório de Participantes do Open Finance. Esses dados são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. Adicionalmente, integram-se à PAD dados oriundos do Gerenciador de Configuração (GDC). O GDC complementa as informações disponíveis na PAD, consolidando detalhes adicionais sobre todas as versões das APIs mantidas pela Estrutura de Governança do Open Finance, incluindo endpoints, famílias de APIs, versões e as respectivas datas de início e término de vigência. Essas informações são mantidas e atualizadas pelos grupos de produtos responsáveis.A combinação dessas fontes de dados — Diretório de Participantes, monitoramento sintético, dados consolidados na PAD e informações do GDC, cria um ecossistema de informações, permitindo avaliação da métrica e monitoramento efetivo das APIs no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
Squad Sandbox

---

# Monitoramento e Gestão de Consequências > Reporte de informações

---
id: 498500110
title: Reporte de informações
version: 3
modified: 2025-04-02T18:13:25.835Z
url: /spaces/OF/pages/498500110/Reporte+de+informa+es
---

item 2.4Purple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |
| 2 | | Revisão geral do documento Inclusão dos tópicos “Interpretação dos Dados no Painel” e “Período de Apuração dos Dados” |

## Introdução e Objetivos
Esta métrica tem como foco garantir que as instituições participantes do Open Finance cumpram os requisitos de reporte de informações, conforme definido pela Estrutura Responsável pela Governança do Open Finance. O objetivo é assegurar a disponibilização de dados com qualidade e detalhamento suficientes, dentro dos prazos estabelecidos, permitindo a implementação efetiva das funcionalidades dispostas no manual. A métrica visa monitorar e identificar situações de desconformidade no processo de envio de informações, promovendo a transparência e a integridade dos dados no ecossistema do Open Finance.
## Sobre a Métrica
A avaliação da conformidade é feita através da verificação dos reportes das instituições participantes à Plataforma de Coleta de Métricas, que devem enviar pelo menos 70% dos reportes de um determinado dia até 8h do próximo dia e pelo menos 75% dos reportes em até sete dias a partir da data e horário das transações. Diariamente deve ser avaliado também se existem dados reportados para o Motor de Qualidade.**Importante**: conforme disposto na IN 575 de 20/12/2024, no item 2.4, a partir do dia 01 de julho de 2025 entrarão em vigor os novos percentuais de envio dos reportes, sendo:
- O atendimento da meta de envio de pelo menos 95% dos reportes até 8h do próximo dia a partir da data e horário das transações (em vez dos 70%)
- O atendimento da meta de envio de pelo menos 99% dos reportes em até 7 dias a partir da data e horário das transações (em vez dos 75%).

## Metodologia Simplificada
**Plataforma de Coleta de Métricas (PCM)**A conformidade é avaliada com base na quantidade, periodicidade, e status dos dados reportados, de acordo com os critérios estabelecidos pela Estrutura de Governança do Open Finance. Uma instituição participante estará em desconformidade se ocorrerem as seguintes situações, considerando para o universo da análise o total de reportes com os status “PAIRED” , “UNPAIRED” e “PAIRED_INCONSISTENT” : 
- Percentual de reporte diário para uma API até 8h do próximo dia a partir da data e hora das transações com status UNPAIRED >5%;

- Não atendimento, superior a 3 dias do mês de apuração, da meta diária de envio de reportes em até 8h do próximo dia a partir da data e hora das transações, mesmo que atenda à meta de pelo menos 99% dos reportes desses dias em até 7 dias a partir da data e hora das transações para a API monitorada;

- Percentual de reportes diários para uma API em até 7 dias a partir da data e hora das transações com status UNPAIRED e PAIRED_INCONSISTENT>1%.
**Motor de Qualidade de Dados (MQD)**
- A conformidade é avaliada com base na quantidade de dias com reporte, no mês de apuração. Um conglomerado estará em desconformidade se para uma ou mais APIs a quantidade de dias sem reporte esperado ao Motor de Qualidade for superior a 3 dias no mês de apuração.

## Interpretação dos Resultados
A interpretação dos resultados obtidos através desta métrica permite identificar instituições que não estão cumprindo com os requisitos de reporte de informações estabelecidos. 
- Se o total de reportes diários para a PCM até às 8h do próximo dia a partir da data e hora das transações, com status "UNPAIRED" excederem 5% do volume de chamadas da instituição para cada API, a instituição estará em desconformidade;
- Se o total de reportes diários para a PCM em até sete dias a partir da data e hora das transações com status "UNPAIRED" e "PAIRED INCONSISTENT” excederem 1% do volume de chamadas da instituição para cada API, a instituição estará em desconformidade.

## Período de Apuração dos Dados
Para fins do processo de monitoramento, o período de apuração referente a esta métrica é mensal e deve haver controle diário do envio dos reportes. Durante o mês, ainda que a instituição não exceda 1% do volume de chamadas com status "UNPAIRED" e "PAIRED INCONSISTENT” em 7 dias a partir da data e hora das transações, se o número de dias em que a meta diária não for atingida for superior a 3, a instituição estará em desconformidade.
## Interpretação dos Dados no Painel
As informações contidas neste item têm como objetivo ajudar o usuário a compreender cada um dos campos exibidos no painel de “Reporte de Informações”. Desta forma, têm-se:Em “**Controles**”:
| Campos | Descrição |
| Mês análise | informar a data ou período desejado, podendo ser uma data relativa ou intervalo de datas absoluto |
| Conglomerado | selecionar o conglomerado desejado |
| Visualizar organização | selecionar a opção “sim” para exibir os detalhes da organização pertencentes ao conglomerado ou a opção “não” para exibir o resultado por conglomerado |
Em “**Desconformidade Consolidada**” é apresentado o resultado consolidado da apuração mensal por conglomerado e/ou organização, de acordo com o filtro selecionado em “**Controles**”.O painel é interativo. Por exemplo, ao clicar na célula “**NÃO CONFORME**” do conglomerado ou da organização, serão exibidos os detalhamentos do mês de apuração. Além disso, é possível maximizar a visualização do painel e exportar os dados para CSV ou Excel.Em “**Desconformidade Mensal**”, têm-se:**Importante**: O MQD aplica-se para as instituições transmissoras de dados pertencentes ao rol de 99%. Sendo assim, as células em branco indicam que as instituições não pertencem a este grupo.
| Campos | Descrição |
| Mês análise | mês referente a apuração |
| Organização | organização selecionada |
| PCM | resultado mensal dos reportes realizados à PCM referente ao mês de apuração |
| MQD | resultado mensal dos reportes realizados ao MQD referente ao mês de apuração |
Em “**Detalhes do mês de apuração da PCM**”, têm-se:
| Campos | Descrição |
| Mês análise | mês/ano referente a apuração |
| Dias de tolerância mensal (até 3 dias) | quantidade total de dias de tolerância mensal referente ao mês de apuração |
| Status | não conforme |
Para exibir os detalhamentos, deve-se sempre clicar nas células “**NÃO CONFORME**”. Desta forma, têm-se:
| Campos | Descrição |
| Data transação | data em que a transação foi realizada |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Total reportes diário | quantidade total de reportes realizados em um determinado dia |
| % até 08h do próximo dia | percentual de reportes de um determinado dia realizados até às 08h do próximo dia |
| % não pareados | percentual de reportes não pareados de um determinado dia |
| Total reportes 7 dias | total de reportes realizados dentro do período de 7 dias das transações referentes a um determinado dia |
| % não pareados e pareados inconsistentes | percentual dos reportes não pareados e pareados inconsistentes de um determinado dia |
| Status | não conforme |
Nos “**Detalhes do mês de apuração do MQD**”, têm-se:
| Campos | Descrição |
| Mês análise | mês referente apuração |
| Family Type | tipo da família de APIs |
| Total de dias no período | quantidade total de dias do mês de apuração |
| Quantidade de dias com reporte | quantidade total de dias do mês de apuração em que houve reporte |
| Quantidade de dias sem reporte | quantidade total de dias do mês de apuração em que não houve reporte |
| Status | não conforme |

## Dados e Fontes
Para o cálculo desta métrica, os dados são obtidos a partir dos dados reportados para a Plataforma de Coleta de Métricas (PCM ) e para o Motor de Qualidade (MQD). Esses dados são posteriormente consolidados na Plataforma Analítica de Dados (PAD), que é um repositório centralizado e serve como base para a análise e avaliação da métrica.
## Limitações e Considerações
Caso a instituição não consiga enviar os reportes devido a falhas da PCM, e seja comprovada a ocorrência de instabilidades ou indisponibilidades da ferramenta, a meta de envio dos reportes até 8h do próximo dia não precisa ser atendida, mas a instituição continua obrigada a enviá-los em até 7 dias a partir da data e hora das transações.
## Responsável pela Aprovação
GT Arquitetura

---

# Monitoramento e Gestão de Consequências > Retirada das versões antigas das APIs de ambiente produtivo e do cadastro no diretório

---
id: 498499951
title: Retirada das versões antigas das APIs de ambiente produtivo e do cadastro no diretório
version: 2
modified: 2024-11-29T14:06:32.782Z
url: /spaces/OF/pages/498499951/Retirada+das+vers+es+antigas+das+APIs+de+ambiente+produtivo+e+do+cadastro+no+diret+rio
---

item 2.2 - VIPurple 
## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica tem como foco garantir a conformidade das instituições participantes do Open Finance com o cronograma estipulado para a retirada de versões antigas das APIs de ambiente produtivo e do cadastro no diretório. O propósito é assegurar uma transição ordenada para as novas versões das APIs, eliminando potenciais riscos associados à manutenção de versões descontinuadas, conforme definido pela regulamentação ou pela Estrutura Responsável pela Governança do Open Finance.
## Sobre a Métrica
A métrica abrange a verificação das APIs e suas versões antigas registradas tanto no Diretório quanto no ambiente produtivo. Ela é medida conforme o cronograma estabelecido para o período de convivência das versões, assegurando que, ao término deste período, nenhuma API que tenha atingido o estado de descontinuada (retired) permaneça disponível ou acessível.
## Metodologia Simplificada

- Verificação de conformidade: A métrica se baseia na verificação do Diretório e do ambiente produtivo para identificar a presença de versões antigas das APIs que deveriam ter sido retiradas, conforme o cronograma de descontinuação.
- Período de convivência: Refere-se ao intervalo de tempo estabelecido que permite a coexistência das versões antigas e novas das APIs antes da retirada completa das versões anteriores.
- Detecção de desconformidade: A desconformidade é identificada quando, após o término do período de convivência, versões descontinuadas das APIs permanecem ativas no Diretório ou no ambiente produtivo.

## Interpretação dos Resultados
A interpretação dos resultados visa identificar as instituições que não cumpriram com o cronograma de retirada de versões antigas das APIs, mantendo-as ativas além do período de convivência estipulado. Um exemplo prático seria a API Consents na versão 2.1.0, que se encontrada ativa no Diretório e/ou ambiente produtivo após seu estado de descontinuação, indicaria uma desconformidade com os requisitos estabelecidos.Para a análise de desconformidade no que tange às APIs listadas no Diretório de participantes, caso uma API que tenha alcançado o estado de descontinuação (retired) seja identificada, como por exemplo, em 16/05/2024, é indicativo de uma desconformidade. Contudo, se a API permanecer cadastrada até 20/05/2024, não serão registradas novas desconformidades durante esse intervalo. No entanto, em um cenário hipotético, se a API for removida em 21/05/2024 e recadastrada em 22/05/2024, uma nova desconformidade será identificada. Isso se deve ao fato de que o período de apuração para a detecção de desconformidades é definido no momento de sua identificação, conforme orientações do Manual de Monitoramento do Open Finance.Em relação ao monitoramento em ambiente produtivo, a desconformidade é estabelecida por meio de monitoramento sintético das interações com as APIs das instituições participantes. Uma desconformidade é reconhecida quando um endpoint, previamente determinado para descontinuação, é acionado após o término do período de convivência, acrescido de 2 dias ou mais, resultando em um status da solução de monitoramento sintético igual a 'SUCCESS' na resposta da chamada. Esse cenário ratifica que a instituição não cumpriu com os requisitos de descontinuação da API em questão.
## Dados e Fontes
A coleta de dados para esta métrica é realizada por meio de uma abordagem integrada que envolve várias fontes e ferramentas especializadas, garantindo uma avaliação abrangente e precisa das APIs no ecossistema do Open Finance. As informações iniciais são extraídas do Diretório, que cataloga todas as instituições participantes e detalha as APIs disponibilizadas por cada uma, incluindo suas versões. Utilizando o Dynatrace, uma solução de monitoramento sintético, são realizadas chamadas às APIs das instituições participantes em ambiente produtivo. Os dados coletados pelo monitoramento sintético são persistidos na PAD, um repositório analítico que serve como o principal ponto de análise e avaliação da métrica. O GDC complementa as informações disponíveis na PAD, consolidando detalhes adicionais sobre todas as versões das APIs mantidas pela Estrutura de Governança do Open Finance, incluindo endpoints, famílias de APIs, versões e as respectivas datas de início e término de vigência. Essas informações são mantidas e atualizadas pelos grupos de produtos responsáveis.A combinação dessas fontes de dados — Diretório de Participantes, monitoramento sintético, dados consolidados na PAD e informações do GDC, cria um ecossistema de informações, permitindo avaliação da métrica e monitoramento efetivo das APIs no contexto do Open Finance.
## Limitações e Considerações
O processo de monitoramento das APIs das em ambiente produtivo, enfrenta desafios significativos relacionados à identificação precisa das versões das APIs em produção. Isso ocorre devido à estruturação das URLs que, frequentemente, não incluem a identificação de versões minor. Por exemplo, uma URL típica ([https://](https://matls-openbanking-uber.digio.com.br/open-banking/consents/v2/consents))`<host>`[/open-banking/consents/v2/consents)](https://matls-openbanking-uber.digio.com.br/open-banking/consents/v2/consents)) não detalha a versão minor, apenas o identificador da versão major (v2).Considere o seguinte cenário para ilustrar essa limitação:No exemplo anterior, a identificação precisa da versão minor não é possível devido à estrutura da URL. Neste contexto, a instituição poderia ser classificada como conforme no que diz respeito ao ambiente produtivo, ainda que haja uma desconformidade real devido à presença de uma versão descontinuada em operação.
## Responsável pela Aprovação
Squad Sandbox

---

# Monitoramento e Gestão de Consequências > Taxa de conversão

---
id: 498500156
title: Taxa de conversão
version: 3
modified: 2025-11-26T21:05:16.068Z
url: /spaces/OF/pages/498500156/Taxa+de+convers+o
---

## item 2.6.2 Purple

## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |

## Introdução e Objetivos
Esta métrica tem como propósito de monitorar a eficiência das jornadas de compartilhamento de dados e de iniciação de pagamentos dentro do ecossistema do Open Finance. O objetivo é assegurar padrões de conversão, refletindo a qualidade e a eficácia dessas jornadas na facilitação de operações seguras e eficientes entre as instituições participantes e seus clientes.
## Sobre a Métrica
Esta métrica foca em duas áreas principais:I. Compartilhamento de dados: A taxa de conversão para compartilhamento de dados é calculada com base na proporção de consentimentos gerados com sucesso em relação ao número total de solicitações de criação de consentimentos, direcionadas para a instituição transmissora de dados.II. Iniciação de Transação de Pagamento: Similarmente, a taxa de conversão para iniciação de transação de pagamento é determinada pela quantidade de consentimentos gerados com sucesso em comparação ao volume de solicitações de criação de consentimentos, direcionadas para a instituição detentora de conta.As taxas mínimas de conversão são definidas como 80% da média ponderada das três maiores taxas de conversão, tanto para instituições transmissoras de dados quanto para instituições detentoras de conta, calculadas nos últimos três meses, excluindo o mês de referência. Uma tolerância de três pontos percentuais é permitida para essas taxas mínimas.
## Metodologia Simplificada

- Cálculo da Taxa de Conversão: A taxa é calculada mensalmente, dividindo o número de consentimentos gerados com sucesso pelo número total de solicitações de criação de consentimentos, excluindo-se aquelas que retornaram erros por falta de permissões adequadas.
- Período de apuração: As taxas são apuradas mensalmente, considerando todas as semanas cujas sextas-feiras ocorrem dentro do mês de referência.
- Exclusões no cálculo: Solicitações de criação de consentimentos que resultaram exclusivamente em erros relacionados a tentativas de acesso sem as devidas permissões não são incluídas no cálculo das taxas de conversão.

## Interpretação dos Resultados
Para compreender a taxa de conversão no contexto do Open Finance, usa-se os dados fornecidos pelas instituições participantes abrangendo um período de três meses, excluindo o mês de referência. A taxa de conversão é um indicador crucial que reflete a eficiência das jornadas de compartilhamento de dados e iniciação de pagamentos, calculada pela quantidade de consentimentos gerados com sucesso (access tokens gerados) dividida pela quantidade total de solicitações de criação de consentimentos.
#### Identificação das três maiores taxas de conversão (Top 3)
Para determinar as três maiores taxas de conversão, calcula-se o percentual de conversão ponderado pela quantidade total de consentimentos solicitados para cada instituição, seguindo esta lógica:Cálculo da taxa ponderada de conversão:
- Para cada instituição, multiplica-se a taxa de conversão pelo total de consentimentos solicitados durante o período de apuração.
- Soma-se os valores resultantes para todas as instituições.
- Divide-se essa soma pela quantidade total de consentimentos solicitados para as instituições no Top 3.
Usando esse método, identifica-se as instituições com as três maiores taxas de conversão ponderadas.
#### Cálculo da taxa mínima de conversão
A taxa mínima de conversão é definida como 80% da média ponderada das taxas de conversão das três maiores taxas de conversão. Com base nos cálculos, chega-se a uma taxa mínima de conversão. Adicionalmente, aplica-se um limite de tolerância de três pontos percentuais, resultando numa taxa mínima ajustada de conversão.
#### Limiares estabelecidos
Limite para notificação: 80% da taxa mínima de conversão.
Limite para diagnóstico (avaliação independente): 60% da taxa mínima.note66bade43-c8a9-44c4-b2d4-086bf56869d2
#### Exemplo Ilustrativo

#### Exemplo Ilustrativo

Considere o seguinte cenário para ilustrar o processo para o período de janeiro a março, sendo março o mês de referência.No exemplo anterior, a Instituição A com uma taxa de conversão média de 60,2% lidera as taxas de conversão, seguida pela Instituição B com 50,3% e pela Instituição C com 46,1%.
#### Cálculo da média ponderada das três maiores taxas de conversão
A média ponderada das três maiores taxas de conversão é calculada somando-se as taxas de conversão ponderadas pelo número de consentimentos solicitados (etapa 2 do funil das jornadas de compartilhamento de dados e etapa 4 do funil da jornada de iniciação de pagamentos) e dividindo esse valor pelo total de consentimentos solicitados. No exemplo, a média ponderada resultou em 56,9%.Primeiro, calcula-se o total de consentimentos solicitados por cada instituição no período de janeiro a marçoInstituição A: 550.581 + 350.210 + 494.310 + 459.320 + 421.015 + 504.100 + 90.451 + 580.211 + 605.051 + 595.151 + 641.510 + 575.101 + 655.011 = 6.522.022Instituição B: 151.002 + 157.448 + 163.383 + 122.041 + 155.376 + 137.648 + 169.040 + 110.091 + 151.090 + 110.803 + 189.893 + 166.027 + 115.193 = 1.899.035Instituição C: 57.354 + 67.288 + 79.410 + 60.399 + 76.852 + 70.380 + 68.173 + 67.530 + 74.913 + 75.106 + 64.694 + 58.036 + 73.052 = 893.187Em seguida, calcula-se a média ponderada das taxas de conversãoInstituição A: 60,2% * 6.522.022 = 3.926.241,24Instituição B: 50,3% * 1.899.035 = 955.628,61Instituição C: 46,1% * 893.187 = 411.586,71Somando os valores ponderados e dividindo pelo total de consentimentos solicitadosMédia ponderada = (3.926.241,24 + 955.628,61 + 411.586,71) / (6.522.022 + 1.899.035 + 893.187) = 56,83%, arredondado para 56,9%
#### Cálculo de 80% da média ponderada
A taxa mínima de conversão é definida como 80% da média ponderada das três maiores taxas de conversão. No exemplo, a taxa mínima de conversão é 45,6%.80% de 56,6% = 0,8 x 56,6 = 45,52% arredondando para 45,6%
#### Aplicação da tolerância de três pontos percentuais
Para acomodar pequenas variações e manter uma margem de tolerância, três pontos percentuais são subtraídos da taxa mínima de conversão. No exemplo, a taxa mínima ajustada é 42,6%.Taxa mínima de conversão ajustada: 45,6% - 3% = 42,6%
#### Cálculo para notificação (80% da taxa mínima)
Caso uma instituição apresente uma taxa de conversão inferior a 80% da taxa mínima, ela será notificada para tomar ações corretivas. Este limiar é estabelecido para garantir que as instituições mantenham um desempenho aceitável. No exemplo, o limite para notificação é 36,4%.80% de 45,6% = 0,8 x 45,6 = 36,48%, arredondado para 36,4%
#### Cálculo para diagnóstico (avaliação Independente - 60% da taxa mínima)
Se a taxa de conversão de uma instituição cair abaixo de 60% da taxa mínima, será necessário uma avaliação independente por uma empresa especializada para diagnosticar e corrigir os problemas subjacentes. No exemplo, o limite para avaliação independente é 27,3%.60% de 45,6% = 0,6 x 45,6 = 27,36%, arredondado para 27,3%Com base nos cálculos realizados, os limiares são definidos da seguinte maneira:Este exemplo ilustra como as taxas de conversão são calculadas e aplicadas no monitoramento das atividades das instituições participantes do Open Finance, visando aprimorar continuamente a eficiência e a eficácia das jornadas de compartilhamento de dados e iniciação de pagamentos.
## Dados e Fontes
A coleta de dados para esta métrica é realizada por meio de uma abordagem integrada que envolve várias fontes de dados, garantindo uma avaliação abrangente e precisa no ecossistema do Open Finance.As informações iniciais são extraídas das planilhas auto reportadas pelas instituições participantes e dos dados consolidados a partir dos reportes enviados através da Plataforma de Coleta de Métricas (PCM).A combinação dessas fontes de dados cria um ecossistema de informações robusto, permitindo uma avaliação precisa da métrica e um monitoramento efetivo das taxas de conversão no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
GT Arquitetura

---

# Monitoramento e Gestão de Consequências > Tempo de Resposta das APIs

---
id: 801996803
title: Tempo de Resposta das APIs
version: 6
modified: 2025-03-25T19:51:35.024Z
url: /spaces/OF/pages/801996803/Tempo+de+Resposta+das+APIs
---

## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |
| 2 | | Segregação da métrica de desempenho de APIs da métrica de disponibilidade de APIs. Maior detalhamento do cálculo da métrica. |
| 3 | | Revisão geral do documento Inclusão do tópico “Interpretação dos Dados no Painel” |

## Introdução e Objetivos
Esta métrica visa monitorar se os *endpoints* das APIs das instituições participantes estão cumprindo os SLAs de tempo de resposta, estabelecidos no Manual de APIs do Open Finance.Considerando que, o tempo de resposta de cada requisição é o tempo transcorrido entre o recebimento de uma requisição que não ultrapassa os limites de tráfego e o momento em que a requisição é completamente respondida.
## Sobre a Métrica
A métrica de Tempo de Resposta das APIs considera o valor do percentil 95 e o número de requisições ocorridas no dia.As medições devem ser realizadas de maneira independente para cada versão "*major*" dos *endpoints* em produção e devem ser consideradas as requisições com todos os códigos de retorno possíveis, **com exceção dos associados a limites de tráfego e limites operacionais**.**O valor do tempo de resposta a ser considerado para uma requisição é o valor reportado pelo consumidor da API,**ou seja, o valor reportado pela instituição iniciadora de pagamentos nas APIs de “Serviços de Iniciação de Pagamentos” e o valor reportado pela receptora de dados no caso de APIs de "Dados Cadastrais e Transacionais".******Na falta de informações dos consumidores, serão utilizadas as informações dos provedores** para o cálculo do SLA de desempenho, ou seja, o valor reportado pela instituição detentora de contas nas APIs de "Serviços de Iniciação de Pagamentos", e o valor reportado pela instituição transmissora de dados no caso de APIs de "Dados Cadastrais e Transacionais".Os *endpoints* das APIs deverão manter, diariamente, o SLA do percentil 95 do tempo de resposta em no máximo:I - 1.500ms, em *endpoints* classificados como de alta e média-alta frequências;II - 2.000ms, em *endpoints* classificados como de média frequência; eIII - 4.000ms, em *endpoints* classificados como de baixa frequência.A conformidade é avaliada mensalmente, verificando se os *endpoints* das APIs das instituições participantes atenderam aos SLAs do desempenho.
## Metodologia Simplificada
A metodologia adotada para o monitoramento do tempo de resposta das APIs avalia se, diariamente, o percentil 95 dos endpoints cumpre o seu SLA, ou seja, se em um dia que o endpoint avaliado receba 100 requisições, o tempo de resposta de pelo menos 95 requisições é inferior ao SLA.  
## Aspectos Técnicos
O monitoramento inclui várias etapas:
| Filtro inicial dos dados provenientes da Plataforma de Coleta de Métricas (PCM) | Serão consideradas apenas as chamadas com tempo de processamento maior que zero, ou seja, processtimespan > 0 |
| Serão excluídas as requisições com status ‘PAIRED_INCONSISTENT’ e ‘DISCARDED’ para todos os endpoints |
| Serão excluídas as chamadas com status code 423, 429 e 529 |
| Agrupamento dos dados (serão agrupados para facilitar o cálculo do percentil 95 (P 95 )) | Timestamp : data da chamada da API (yyyy-mm-dd) |
| Serverorgid : identificador da organização consumidora da API utilizada pelo cliente para a solicitação do dado |
| Endpoint : endpoint da API com o método e recurso |
| Cálculo do percentil | Coleta dos dados : Seja R o conjunto de todos os tempos de resposta de um dia, onde “ri” é o tempo de resposta da i-ésima requisição. Ou seja, R={r1, r2, ..., rn}. Nessa coleta é utilizado o processtimespan quando clientorgid = organisationid ou serverorgid = organisationid e status ‘UNPAIRED’ |
| Cálculo do índice do percentil 95 : o índice para o percentil 95, denotado por i95, é calculado pela fórmula i95 = 0.95 ∗ n, arredondado para o número inteiro mais próximo, e onde “n” representa número de requisições |
| Ordenação dos dados : O conjunto R em ordem crescente para obter o conjunto ordenado Rord={r(1), r(2), ..., r(n)}, onde r(1) é o menor tempo de resposta e r(n) é o maior |
| Obtenção do valor do percentil 95 : o valor do percentil 95, denotado por P 95 , é o valor no índice i95 no conjunto ordenado Rord. Ou seja, P 95  = r(i95) |

## Interpretação dos Resultados
Para fins do processo de monitoramento, o período de apuração referente a este item é mensal e a análise de desconformidade é feita por conglomerado. A título de exceção, no caso de conglomerados que possuam equipes N2 por CNPJ, a desconformidade será gerada para a instituição. Considera-se que um *endpoint* está em conformidade caso tenha respeitado o SLA do desempenho em pelo menos 90% dos dias do mês de referência, arredondando-se para o número inteiro mais próximo, desde que o valor do percentil 95 (P95) dos demais dias não tenha sido superior ao SLA do desempenho aumentado em 20%.****Os dias do mês de referência são os dias do mês em que houve requisições para o *endpoint*avaliado.Assim, consideramos cada conformidade diária:
| CONFORME | DENTRO DA TOLERÂNCIA | NÃO CONFORME |
| P 95 < SLA | SLA < P 95 < SLA * 1,2 | P 95 > SLA * 1,2 |
E fazemos a apuração mensal:
| CONFORME | NÃO CONFORME |
| Se a quantidade de dias conforme ≥ 90% de dias de acionamento | Se a quantidade de dias não conforme > 0 Se a quantidade de dias não conforme < 90% de dias de acionamento |
**Importante**: A métrica não se aplica às APIs de "*Webhook*".note
#### Exemplo Ilustrativo

#### Exemplo Ilustrativo

I - Em um mês de 30 dias, em que um *endpoint* de alta frequência tenha apresentado valor de P95 inferior a 1.500ms em 27 dias e, nos demais dias, tenha apresentado valor de P95 entre 1.500ms e 1.800ms (1.500ms * 1,2 = 1.800ms), o *endpoint* está em **conformidade** para fins do processo de monitoramento naquele mês.II - Em um mês de 31 dias, em que um *endpoint* de alta frequência tenha apresentado valor de P95 inferior a 1.500ms em 28 dias e, nos demais dias, tenha apresentado, em pelo menos um dos dias, valor de P95 superior a 1.800ms (1.500ms * 1,2 = 1.800ms), o *endpoint* está **não conforme**para fins do processo de monitoramento naquele mês.
## Interpretação dos Dados no Painel
As informações contidas neste item têm como objetivo ajudar o usuário a compreender cada um dos campos exibidos no painel de “Tempo de Respostas das APIs”. Desta forma, têm-se:Em “**Controles**”:
| Campos | Descrição |
| Mês análise | informar a data ou período desejado, podendo ser uma data relativa ou intervalo de datas absoluto |
| Conglomerado | selecionar o conglomerado desejado |
| Endpoint | selecionar o endpoint desejado ou selecionar todos os endpoint s |
| Visualizar organização | selecionar a opção “sim” para exibir os detalhes da organização pertencentes ao conglomerado ou a opção “não” para exibir o resultado por conglomerado |
Em “**Desconformidade mensal**” é apresentado o resultado consolidado da apuração mensal por conglomerado e/ou organização, de acordo com o filtro selecionado em “**Controles**”.O painel é interativo. Por exemplo, ao clicar na célula “**NÃO CONFORME**” do conglomerado ou da organização, serão exibidos os detalhamentos do mês de apuração. Além disso, é possível maximizar a visualização do painel e exportar os dados para CSV ou Excel.Nos detalhes do mês de apuração:
| Campos | Descrição |
| Mês da apuração | mês referente a apuração |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Dias acionamentos | total de dias do mês de apuração que o endpoint foi acionado |
| Dias P 95 < frequência | total de dias do mês de apuração em que o P 95 (percentil 95) encontra-se inferior a frequência do endpoint |
| Dias P 95 entre a frequência | total de dias em que o P 95 (percentil 95) encontra-se no intervalo de tempo da frequência do endpoint |
| Dias P 95 > tolerância | total de dias do mês de apuração em que o P 95 (percentil 95) encontra-se superior a tolerância de 20% |
| Status | não conforme (P95>SLA*1,2) |
No detalhamento, é possível visualizar:
| Campos | Descrição |
| Dias acionamento | dia do mês de apuração em que o endpoint foi acionado |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Frequência API (ms) | SLA da frequência de classificação do endpoint |
| Quantidade de requisições | total de requisições utilizadas para o cálculo de um determinado dia do mês de apuração |
| P 95 (ms) | percentil 95 do tempo de requisição por milissegundo |
| Status | dentro da tolerância (SLA<P95<SLA*1,2) ou não conforme (P95 > SLA*1,2) |
**Importante**: para que o detalhamento seja exibido, deve-se sempre clicar na célula “NÃO CONFORME”.
| Campos | Descrição |
| x-fapi-interaction-id | identificador único do reporte |
| Server | servidor reportado na requisição |
| Client | cliente reportado na requisição |
| Método HTTP | método da requisição |
| Endpoint | endpoint da requisição |
| Requisição (ms) | tempo de resposta da requisição |
**Importante:**serão exibidos no máximo cinco evidências de reporte.
## Dados e Fontes
Para o cálculo desta métrica, a fonte informacional é a Plataforma de Coleta de Métricas (PCM), que consolida os dados a partir dos reportes enviados pelas instituições participantes.  Todos os métodos e recursos dos *endpoints* serão avaliados. Esses dados são consolidados na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
GT Arquitetura

---

# Monitoramento e Gestão de Consequências > Volume de requisições com status code HTTP 529

---
id: 794329168
title: Volume de requisições com status code HTTP 529
version: 2
modified: 2025-02-28T14:41:55.207Z
url: /spaces/OF/pages/794329168/Volume+de+requisi+es+com+status+code+HTTP+529
---

## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | 31 de jan. de 2025 | Versão inicial |

## Introdução e Objetivos
Esta métrica visa monitorar as requisições que excederem os limites de TPS e que devem ser respondidas com *status code* HTTP 529 (*Site is overloaded*). A Estrutura de Governança do Open Finance visa, com esta métrica, fornecer informação sobre a infraestrutura das instituições provendo APIs no *Open Finance*que deve ter a capacidade de, no mínimo, atender a 300 requisições simultâneas por segundo (TPS).
## Sobre a Métrica
A métrica se baseia no volume de requisições excedentes que retornam o status code HTTP 529.
## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será mensal, conforme orientado pelo Manual de Monitoramento do Open Finance Brasil. A metodologia adotada para o monitoramento do volume de requisições com status code HTTP 529 avalia se, diariamente, esse volume é inferior a 0,5% das requisições válidas. 
## Aspectos Técnicos

- Excluir chamadas com status 'PAIRED_INCONSISTENT' e ‘DISCARTED’

- Considerar as requisições válidas que retornam  status code  da faixa 2XX, 5XX, igual a 408 ou igual a 422

## Interpretação dos Resultados
Para fins do processo de monitoramento, o período de apuração referente a este item é mensal e a análise de desconformidade é feita por conglomerado. Considera-se que uma determinada instituição participante está em conformidade caso tenha respeitado o limite de 0,5% em pelo menos 90% dos dias do mês de referência, arredondando-se para o número inteiro mais próximo, desde que o volume diário de requisições com *status code* HTTP 529 dos demais dias não tenha sido superior a 5%.noteExemplo Ilustrativo
Exemplo Ilustrativo
Para ilustrar as condições de conformidade e desconformidade, considere o seguinte exemplo:O Banco ABC, com uma capacidade inicial de 300 TPS, recebeu um pico de 350 TPS em 05/12. As 50 requisições excedentes retornaram o status HTTP 529, totalizando 0,54% das requisições válidas naquele dia. Isso exige um aumento imediato da capacidade para 450 TPS. Ainda no mês de dezembro, o Banco ABC teve 28 dias dentro do limite de 0,5%, 2 dias com valores entre 0,51% e 5%, e 1 dia crítico com 6,2%. Como violou o limite de 5% em um dia, foi classificado como não conforme, mesmo tendo 90% dos dias dentro do padrão.
## Dados e Fontes
Para o cálculo da métrica, utiliza-se um conjunto diversificado de dados provenientes de diferentes fontes. A principal fonte informacional é a Plataforma de Coleta de Métricas (PCM), que consolida os dados a partir dos reportes enviados pelas instituições participantes. Além disso, as planilhas auto reportadas pelas instituições são integradas e consolidadas na Plataforma Analítica de Dados (PAD), um repositório centralizado que serve como base para a análise e avaliação da métrica. Essa combinação de dados provenientes da PCM e das planilhas auto reportadas permite uma avaliação precisa da métrica e um monitoramento efetivo do desempenho e disponibilidade das APIs no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esta métrica. A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.
## Responsável pela Aprovação
GT Arquitetura

---

# Monitoramento e Gestão de Consequências > Índice de Qualidade dos Dados (IQD)

---
id: 498500234
title: Índice de Qualidade dos Dados (IQD)
version: 7
modified: 2025-05-09T11:46:41.046Z
url: /spaces/OF/pages/498500234/ndice+de+Qualidade+dos+Dados+IQD
---

## item 2.5 Purple

## Controle de versão

| Versão | Data | Resumo das alterações |
| 1 | | Versão inicial |
| 2 | | Implementado o Fator de Consistência no cálculo do IQA para mensurar a regularidade do reporte de dados de cada família de API |
| 3 | | Revisão geral do documento Alteração do Tópico “Classificação de conformidade do IQD” Inclusão do tópico “Interpretação dos Dados no Painel” |
O monitoramento referente ao item 2.5 terá início em 1º de julho de 2025, conforme estabelecido na Instrução Normativa BCB nº 575, de 20 de dezembro de 2024. 
## Introdução e Objetivos
Para garantir transparência quanto à qualidade dos dados no ecossistema do Open Finance, a Estrutura Responsável pela Governança do Open Finance disponibiliza o Índice de Qualidade dos Dados (IQD), juntamente com seus indicadores e metodologias de cálculo. Esses dados serão divulgados mensalmente, permitindo que o público acompanhe o nível de qualidade dos dados fornecidos pelas instituições participantes. Essa transparência proporciona informações confiáveis para a tomada de decisões relacionadas a riscos e resultados de negócios.O Índice de Qualidade de Dados (IQD) foi desenvolvido para fornecer informações detalhadas sobre a qualidade dos dados oferecidos pelas instituições participantes aos cidadãos, associações e demais participantes do ecossistema do Open Finance. Com maior transparência, esses grupos têm acesso a um conjunto abrangente de informações para decidir qual instituição desejam utilizar para o compartilhamento de dados e/ou serviços financeiros por meio do Open Finance.
## Sobre o Índice
O Índice de Qualidade dos Dados (IQD) é composto por três índices principais: Índice de Resolução (IR), Índice de Confiabilidade (IC) e Índice de Abrangência (IA). Esses índices, quando combinados, fornecem uma visão abrangente da qualidade dos dados fornecidos pelas instituições participantes do Open Finance.
### Componentes do IQD

#### Índice de Resolução (IR)
Esse índice mede a eficiência na resolução de problemas e no atendimento ao suporte relacionado a uma determinada família de APIs. Esse índice é calculado com base na quantidade de tickets encerrados dentro do prazo de SLA em relação ao total de tickets abertos para a família de APIs em questão. Um valor alto de IR indica que a instituição é eficiente na resolução de problemas e no atendimento às demandas dos usuários. A eficiência é avaliada com base nas seguintes condições:
- Se não houver tickets abertos ou encerrados e o total de requisições com erro for igual a 0, o IR é considerado 100%, indicando máxima eficiência na gestão de erros;
- Se não houver tickets abertos ou encerrados e o total de requisições com erro for maior que 0, o IR é 0%, indicando uma situação onde, apesar da ausência de tickets, há problemas não resolvidos impactando a qualidade dos dados;
- Nos demais casos, o IR é calculado pela fórmula a seguir, proporcionando uma medida quantitativa da eficiência na resolução de problemas:

#### Índice de Confiabilidade (IC)
Esse índice avalia a qualidade e a integridade dos dados fornecidos por uma determinada API. Esse índice indica a proporção de requisições bem-sucedidas em relação ao total de requisições. Um valor alto indica que os dados fornecidos pela API são confiáveis e podem ser utilizados com segurança pelas aplicações e serviços que dependem dessas informações.
#### Índice de Abrangência (IA)
Esse índice mede o quão abrangente é uma determinada API em relação ao total de APIs analisadas na organização. Esse índice leva em consideração a quantidade de requisições realizadas para uma determinada família de API, comparando-a com todas as famílias de APIs analisadas naquela organização. Um valor alto de IA indica que a API em questão possui uma grande relevância e abrangência dentro da organização.
#### Cálculo do Índice de Qualidade de Dados (IQD)
O Índice de Qualidade de Dados (IQD) é calculado em várias etapas, considerando diferentes aspectos da qualidade e consistência dos dados fornecidos.
#### a) Cálculo do Índice de Qualidade da API (IQA)
O IQA é obtido através da combinação ponderada dos índices IR e IC, multiplicada pelo Índice de Abrangência (IA).
#### Fórmula do IQA
**𝐼𝑄𝐴 inicial = ((𝐼𝑅 × Peso IR) + (𝐼𝐶 × Peso IC)) × 𝐼𝐴**
#### Pesos atribuídos

- Índice de Resolução (IR): 25%

- Índice de Confiabilidade (IC): 75%
 
#### b) Aplicação do Fator de Consistência
O Fator de Consistência mede a regularidade do reporte de dados para cada família de API.
#### Fórmula do Fator de Consistência

#### Fator de Consistência = (Dias com Reporte / Total de Dias no Período)
**IQA final = IQA inicial x Fator de Consistência**O Fator de Consistência incorpora a regularidade do fornecimento de dados ao cálculo do IQA, complementando as métricas de qualidade. 
#### c) Calculo do IQD
O Índice de Qualidade de Dados (IQD) é a somatória de todos os Índices de Qualidade da API (IQA) finais.
#### Fórmula do IQD
**IQD = Σ (IQA final)** 
#### Classificação de conformidade do IQD

| CONFORME | NÃO CONFORME |
| --- | --- |
| ≥ 80% | < 80% |

## Metodologia Simplificada
Para fins de monitoramento deste item, o período de apuração será mensal, conforme orientado pelo Manual de Monitoramento do Banco Central do Brasil. A avaliação envolverá:
- Coleta de Dados: Os dados são coletados a partir do Motor de Qualidade de Dados (MQD).
- Cálculo dos Índices: Índice de Resolução (IR): Calcula a quantidade de tickets encerrados em relação ao total de tickets abertos. Índice de Confiabilidade (IC): Avalia a integridade dos dados, considerando a quantidade de requisições bem-sucedidas. Índice de Abrangência (IA): Mede a relevância de uma API em relação ao total de APIs analisadas.
- Cálculo do IQA: Combinação ponderada dos índices IR e IC, multiplicada pelo índice IA.
- Cálculo do IQD: Soma de todos os Índices de Qualidade da API (IQA).
- Enquadramento dos níveis de qualidade em uma escala progressiva

## Interpretação dos Resultados
Os resultados do índice serão interpretados para verificar se as instituições estão cumprindo os critérios de qualidade dos dados. A análise incluirá a avaliação dos três índices principais (IR, IC e IA) e a combinação ponderada desses índices para calcular o IQA e, subsequentemente, o IQD. noteExemplo ilustrativo
Exemplo ilustrativo
Considere a organização ABC com diferentes volumes de requisições para as APIs, como mostrado na tabela a seguir:
| Organização | Família de API | Total de requisições | Total de requisições com erros | Tickets Abertos | Tickets Encerrados | Índice de Resolução | Índice de Confiabilidade | Índice de Abrangência | Índice de Qualidade de Dados |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ABC | accounts | 2.998.324 | 54.843 | 2 | 1 | 33% | 98% | 62% | 69,5% |
| credit-cards-accounts | 1.155.313 | 87.156 | 3 | 0 | 0% | 92% | 24% |
| loans | 686.806 | 166.179 | 1 | 1 | 50% | 76% | 14% |

#### Família de API: accounts
IR = Tickets encerrados / (Tickets abertos + Tickets encerrados)
IR = 1 / (2 + 1) = 33%IC = (Total de requisições - Total de requisições com erros) / Total de requisições
IC = (2.998.324 - 54.843) / 2.998.324 = 98%IA = Total de requisições / Soma total de requisições (todas as APIs)
IA = 2.998.324 / (2.998.324 + 1.155.313 + 686.806) = 62%FC = (Dias com reporte / Total de dias no período)
FC = (27 / 30) = 0,9IQA = ((IR x Peso IR) + (IC x Peso IC)) x IA
IQA = ((33% x 0.25) + (98% x 0.75)) x 62 = 51%
IQA = 51 * 0,9 = 45,9%
#### Família de API: credit-cards-accounts
IR = Tickets encerrados / (Tickets abertos + Tickets encerrados)
IR = 0 / (3 + 0) = 0%IC = (Total de requisições - Total de requisições com erros) / Total de requisições
IC = (1.155.313 - 87.156) / 1.155.313 = 92%IA = Total de requisições / Soma total de requisições (todas as APIs)
IA = 1.155.313 / (2.998.324 + 1.155.313 + 686.806) = 24%FC = (Dias com Reporte / Total de Dias no Período)
FC = (24 / 30) = 0,8IQA = ((IR x Peso IR) + (IC x Peso IC)) x IA
IQA = ((0% x 0.25) + (92% x 0.75)) x 24 = 17%
IQA = 17 * 0,8 = 13,6%
#### Família de API: loans
IR = Tickets encerrados / (Tickets abertos + Tickets encerrados)
IR = 1 / (1 + 1) = 50%IC = (Total de requisições - Total de requisições com erros) / Total de requisições
IC = (686.806 - 166.179) / 686.806 = 76%IA = Total de requisições / Soma total de requisições (todas as APIs)
IA = 686.806 / (2.998.324 + 1.155.313 + 686.806) = 14%FC = (Dias com Reporte / Total de Dias no Período)
FC = (30 / 30) = 1IQA = ((IR x Peso IR) + (IC x Peso IC)) x IA
IQA = ((100% x 0.25) + (76% x 0.75)) x 14 = 10%
IQA = 10 * 1 = 10%
#### Cálculo do IQD para a organização A
IQD = ∑ (IQA)IQD = ∑ IQA ≈ 45,9% + 13,6% + 10% = 69,5%
## Interpretação dos Dados no Painel
As informações contidas neste item têm como objetivo ajudar o usuário a compreender cada um dos campos exibidos no painel de “Índice de Qualidade de Dados (IQD)”. Desta forma, têm-se:Em “**Controles**”:
| Campos | Descrição |
| Data início | informar a data de início ou período desejado, podendo ser uma data relativa ou intervalo de datas absoluto |
| Data fim | informar a data de fim ou período desejado, podendo ser uma data relativa ou intervalo de datas absoluto |
| Conglomerado | selecionar o conglomerado desejado |
| Visualizar por conglomerado ou instituição | selecionar a opção “instituição” para exibir os detalhes da organização pertencentes ao conglomerado ou a opção “conglomerado” para exibir o resultado por conglomerado |
Em “**Desconformidade mensal do IDQ por Conglomerado**” (**Figura 1**) é apresentado o resultado consolidado da apuração mensal por conglomerado, de acordo com o filtro selecionado em “**Controles**”.O painel é interativo. Por exemplo, ao clicar na célula “**NÃO CONFORME**” do conglomerado, serão exibidos os detalhamentos do mês de apuração.Figura 1 - Desconformidade mensal do IQD por conglomeradoEm “**Desconformidade mensal do IDQ por Instituição Participante**” (**Figura 2**) é apresentado o resultado consolidado da apuração mensal por **Instituição Participante**, de acordo com o filtro selecionado em “**Controles**”.O painel é interativo. Por exemplo, ao clicar na célula “**NÃO CONFORME**” da Instituição, serão exibidos os detalhamentos do mês de apuração.Figura 2 - Desconformidade mensal do IQD por instituição participanteEm “**Desconformidade mensal - Instituição Participante**”, têm-se:
| Campos | Descrição |
| Mês apuração | mês referente a apuração |
| IQD | percentual referente ao Índice de Qualidade dos Dados (IQD) no mês de apuração |
| Status | não conforme |
Em “**Detalhamento do cálculo do IQD por Instituição Participante**”, têm-se:noteÉ possível ampliar a visualização do painel e exportar os dados para CSV ou Excel por meio da opção 'Opções de menu', localizada no canto superior direito”.
É possível ampliar a visualização do painel e exportar os dados para CSV ou Excel por meio da opção 'Opções de menu', localizada no canto superior direito”.

| Campos | Descrição |
| Mês/Ano | mês e ano referente a apuração |
| Conglomerado Participante | conglomerado/instituição selecionado(a) |
| Família de APIs | família de APIs correspondentes |
| Quantidade de Requisições | total de requisições reportadas no mês de apuração de determinada família de APIs |
| Quantidade de Requisições com erros | total de requisições com erros reportadas no mês de apuração de determinada família de APIs |
| Tickets abertos | total de tickets abertos quando contém erro em requisições de determinada família de APIs no mês de apuração |
| Tickets encerrados | total de tickets encerrados de determinada família de APIs no mês de apuração |
| Dia do mês | dia do mês em que houve reporte de dados para determinada família de API |
| Dias reportados | total de dias do mês de apuração em que houve reporte de dados para determinada família de API |
| Índice de Resolução (IR) | resultado do percentual do índice de resolução |
| Índice de Confiabilidade (IC) | resultado do percentual do índice de confiabilidade |
| Índice de Abrangência (IA) | resultado do percentual do índice de abrangência |
| Fator de Consistência (FC) | percentual do fator de consistência |
| Índice de Qualidade da API (IQA) | percentual do índice de qualidade da API |
| Índice de Qualidade de Família (IQF) | percentual do índice de qualidade de família |

## Dados e Fontes
Para o cálculo do índice, utilizam-se os dados provenientes do Motor de Qualidade de Dados (MQD). Esses dados são posteriormente consolidados na Plataforma Analítica de Dados (PAD), que é um repositório centralizado e serve como base para a análise e avaliação dos dados para o índice.Essa estrutura permite uma avaliação precisa do índice e um monitoramento efetivo da qualidade dos dados no contexto do Open Finance.
## Limitações e Considerações
Atualmente, não há visibilidade ou conhecimento de limitações ou considerações adicionais para esse índice . A análise será continuamente revisada e aprimorada conforme novos dados e informações se tornem disponíveis.

---

# Plano de Resposta a Incidentes Críticos de Negócio entre IFs > 01. Identificação do Incidente

---
id: 524124246
title: 01. Identificação do Incidente
version: 1
modified: 2024-08-09T18:20:08.562Z
url: /spaces/OF/pages/524124246/01.+Identifica+o+do+Incidente
---

### Critérios
Para garantir uma resposta eficaz e oportuna a eventos que possam impactar significativamente as operações, é crucial identificá-los claramente. Com este objetivo, foram estabelecidos critérios específicos para esclarecê-los. A seguir, os três critérios para a identificação de um incidente crítico de negócio: :info:atlassian-info#F4F5F7
### Interrupção dos Serviços Prestados
Interrupções prolongadas ou falhas graves que tornem a Instituição indisponível para o ecossistema.:info:atlassian-info#F4F5F7
### Perda Financeira Significativa
Danos econômicos substanciais às Instituições envolvidas devido a falhas operacionais, erros de processamento ou outras questões relacionadas ao OFB.:info:atlassian-info#F4F5F7
### Impacto na Reputação e Confiança dos Clientes
Redução da confiança dos clientes devido a falhas no serviço, resultando em perda de negócios ou danos à Instituição Financeira.Para garantir que os recursos e a atenção sejam direcionados de maneira adequada, é fundamental que os incidentes sejam corretamente avaliados antes de serem escalonados. A Árvore de Decisão de Criticidade é o meio orientar nesta avaliação. Este método estruturado norteia para que apenas incidentes verdadeiramente críticos sejam escalonados, evitando alarmes falsos e promovendo uma resposta eficaz.
### Árvore de Decisão de Criticidade
A árvore de decisão atua como uma ferramenta para determinar a necessidade de tratar de forma imediata um incidente crítico de negócio. Cada questão auxilia na avaliação da seriedade e do impacto do incidente, assegurando que incidentes críticos sejam realmente gerenciados com a urgência e os recursos adequados.
- Questionário de Avaliação

- Tabela de decisão para tratativa imediata com abertura de Sala de Crise

---

# Plano de Resposta a Incidentes Críticos de Negócio entre IFs > 02. Registro e Reporte do Incidente

---
id: 524124294
title: 02. Registro e Reporte do Incidente
version: 5
modified: 2025-08-06T18:54:50.849Z
url: /spaces/OF/pages/524124294/02.+Registro+e+Reporte+do+Incidente
---

Ao confirmar o cenário de um incidente crítico de negócio, a IF deverá registrar a ocorrência na **ferramenta Service Desk**e, em seguida, reportar o incidente à DTO por contato telefônico **(lista de sobreaviso)**e por e-mail, informando o número do incidente atribuído pela ferramenta. Esta ação preferencialmente deverá ocorrer nos primeiros minutos após a identificação do incidente.
### Registro do incidente na ferramenta Service Desk

1. Acesse a ferramenta Service Desk - https://servicedesk.openfinancebrasil.org.br/servicePortal
2. Selecione a opção Incidentes no menu
3. Dentre as opções de categorias disponíveis na ferramenta, selecione a que melhor descreva o cenário enfrentado.
*Em andamento proposta para espaço exclusivo na ferramenta Service Desk para reportar incidentes críticos. 
### Reporte do Incidente a DTO
Após obter o número do incidente, a IF afetada deve reportar a ocorrência à DTO, conforme a lista de sobreaviso, informando o número do incidente fornecido pela ferramenta. Esta ação deve, preferencialmente, ocorrer nos primeiros minutos após a identificação do incidente.**Lista de Sobreaviso**
| Níveis de Escalonamento | E-mail | Manter em Cópia |
| 1º - Adolfo Kawiatkowski | tecnologia@openfinancebrasil.org.br | adolfo.neto@openfinancebrasil.org.br |
| 2º - Fábio Szescsik | fabio.szescsik@openfinancebrasil.org.br |
| 3º - Paulo Moraes | paulo.moraes@openfinancebrasil.org.br |
**Cobertura do Atendimento: Segunda a Sexta-Feira - 09:00h - 18:00h**

---

# Plano de Resposta a Incidentes Críticos de Negócio entre IFs > 03. Analise e Comunicação

---
id: 524124347
title: 03. Analise e Comunicação
version: 1
modified: 2024-08-09T18:20:10.801Z
url: /spaces/OF/pages/524124347/03.+Analise+e+Comunica+o
---

O responsável da DTO avaliará tecnicamente o incidente e decidirá por seguir a tratativa via estrutura de suporte DTO ou por mobilizar os líderes técnicos de acordo com a matriz de escalonamento das IFs para a abertura de uma Sala de Crise. 
### Sala de Crise
Sala de crise é uma reunião virtual estruturada e dedicada, onde um grupo convocado se reúne em resposta a incidentes críticos de negócios com impactos severos ao ecossistema. O objetivo principal é coordenar uma resposta eficaz e unificada, minimizando danos e restaurando a normalidade operacional.Nesse espaço, os participantes trabalham de forma intensiva para avaliar a situação, tomar decisões rápidas e implementar ações estratégicas com o objetivo de minimizar danos, restaurar operações essenciais e/ou proteger a reputação dos envolvidos em caso de incidentes críticos.
### Composição da Sala de Crise
****A composição da sala de crise é crucial para assegurar uma resposta eficiente e coordenada ao incidente de negócio. Cada Instituição Financeira deve designar representantes com conhecimento substancial e autoridade necessária para tomar decisões em nome de suas respectivas instituições.Os representantes devem estar preparados para discutir detalhes técnicos e estratégicos, contribuir com informações relevantes e participar ativamente na formulação de soluções. Papéis e Responsabilidades dos participantes da Sala de Crise:
- Incident Commander :  representante designado pelo DTO que atuará como moderador neutro e imparcial para facilitar as discussões. Responsável por convocar as Instituições Financeiras quando necessário, assegurando as credenciais adequadas dos participantes e garantindo canais necessários para condução da tratativa com segurança.
- Representantes Autorizados : representantes autorizados pelas Instituições Financeiras preparados para discutir detalhes técnicos e estratégicos, contribuir com informações relevantes e participar ativamente na formulação de soluções. Serão convocados através da Matriz de Escalonamento mencionada no item abaixo.
- Grupo Técnico (GT):   se identificado que serão relevantes para a tratativa do incidente, podem ser convocados para colaboração mediante informações sanitizadas, em conformidade com as práticas de segurança.
- Diretoria de Tecnologia e Operações (DTO) : se identificado que serão relevantes para a tratativa do incidente, podem ser convocados para colaboração.

### Matriz de Escalonamento IFs
Os representantes autorizados das IFs serão inicialmente convocados via e-mail à Sala de Crise através da Matriz de Escalonamento abaixo. A convocação deve ser priorizada para que todos estejam informados e alinhados, possibilitando uma resposta rápida, coordenada e eficaz ao incidente. PTC - Primeiro Contato Técnico STCV - Segundo Contato Técnico
### Comunicação
Diante da necessidade de tratar o incidente através de uma Sala de Crise e convocação dos envolvidos, o Incident Commander seguirá com o plano de comunicação para garantir transparência e ciência das tratativas realizadas.**Plano de Comunicação**Como parte do plano de comunicação, é essencial notificar o Conselho e o Regulador sobre a ocorrência de uma crise para possibilitar uma tomada de decisão ágil. Nesse contexto, o uso do WhatsApp é mais eficiente que o e-mail, garantindo uma comunicação rápida e a visualização imediata. Assim, o responsável pela DTO, ao conduzir a Sala de Crise, utilizará o canal de WhatsApp previamente estabelecido com os Conselheiros para notificar sobre crises e incidentes críticos de negócio, complementando a comunicação com um e-mail detalhado.**Modelos de Notificações - Canal WhatsApp****Notificação Inicial da crise**Prezados,Estamos enfrentando um incidente crítico [descrição resumida do incidente e impacto].Estamos trabalhando para resolver o problema o mais rápido possível. Atualizações serão enviadas em breve.**Comunicação contínua durante a condução da crise**Prezados,Identificamos [detalhes do andamento da crise] e esperamos resolver em [tempo estimado].Evoluímos para [detalhes]. Estamos tomando as seguintes medidas: [ações específicas]."**Notificação de Conclusão da Crise**Prezados,Informamos que o incidente crítico [descrição resumida do incidente] foi resolvido com sucesso. As ações necessárias foram concluídas e o impacto foi mitigado.Uma análise detalhada do ocorrido e as medidas preventivas adotadas serão compartilhadas em breve.**Modelo de Notificação - E-mail**Prezados,Estamos enfrentando um incidente crítico [descrição do incidente e impacto].
- Instituições Envolvidas:
- Número do Incidente:
- Ações em andamento:
Estamos trabalhando para resolver o problema o mais rápido possível. Atualizações serão enviadas em breve.DTO.

---

# Plano de Resposta a Incidentes Críticos de Negócio entre IFs > 04. Tratativa do Incidente Crítico

---
id: 524124380
title: 04. Tratativa do Incidente Crítico
version: 1
modified: 2024-08-09T18:20:11.447Z
url: /spaces/OF/pages/524124380/04.+Tratativa+do+Incidente+Cr+tico
---

O responsável da DTO iniciará a sala de crise através de um canal privado no Microsoft Teams para orquestrar as tratativas e se comunicar com todos os envolvidos. Ele garantirá a participação ativa dos membros e monitorará todas as etapas até a resolução do incidente.
### Canal Privado Microsoft Teams
As tratativas da Sala de Crise devem ocorrer em um canal privado para garantir segurança, controle de acesso e foco, mantendo informações críticas restritas aos participantes necessários.Orientação para criação de canal privado na ferramenta Microsoft Teams: 
1. Abra o aplicativo Microsoft Teams no seu computador ou acesse a versão web.
2. No painel lateral esquerdo, clique na equipe onde você deseja criar o canal privado.
3. Clique nos três pontos (reticências) ao lado do nome da equipe.
4. Selecione "Adicionar canal".
5. Na janela que se abre, digite o nome do canal.
6. Adicione uma descrição opcional para o canal.
7. Na seção "Privacidade", clique no menu suspenso e selecione "Privado – Apenas membros específicos têm acesso".
8. Clique no botão "Adicionar" para adicionar membros específicos ao canal privado.
9. Digite os nomes das pessoas que você deseja adicionar e selecione-as na lista que aparece.
10. Após adicionar todos os membros, clique em "Concluído" para finalizar a criação do canal.
11. Você verá o novo canal listado sob a equipe com um ícone de cadeado ao lado do nome, indicando que é um canal privado.

### Documentação
As medidas da sala de crise serão documentadas no **Relatório da Sala de Crise**, que será mantido na DTO para análise posterior e compartilhado às IFs envolvidas, caso solicitado.

---

# Plano de Resposta a Incidentes Críticos de Negócio entre IFs > 05. Conclusão

---
id: 524124413
title: 05. Conclusão
version: 1
modified: 2024-08-09T18:20:12.107Z
url: /spaces/OF/pages/524124413/05.+Conclus+o
---

Após a resolução do incidente crítico, o responsável da DTO desmobilizará a sala de crise, encerrando oficialmente as atividades e liberando os membros envolvidos, além de concluir a documentação do incidente para assegurar que todos os detalhes relevantes foram registrados.Em seguida, é essencial realizar uma análise detalhada para avaliar a eficácia da resposta e identificar áreas de melhoria. Esse processo inclui a revisão das ações tomadas, a documentação das lições aprendidas e a implementação de medidas corretivas para evitar futuras ocorrências. A análise pós crise ajuda a aprimorar continuamente os procedimentos aplicados, reforçar a resiliência organizacional e garantir uma resposta mais eficiente a eventos futuros.Para as tratativas do pós crise, os envolvidos serão novamente convocados, pórem com a devida antecedência, garantindo assim que todos estejam disponíveis para contribuir. A convocação deve incluir informações sobre o propósito do fórum, a agenda e os documentos a serem revisados. Espera-se que todos os participantes contribuam com suas perspectivas e insights, compartilhando experiências e sugestões para melhorias.

---

# Plano de Resposta a Incidentes Críticos de Negócio entre IFs > Introdução

---
id: 524124208
title: Introdução
version: 2
modified: 2024-08-13T20:24:25.803Z
url: /spaces/OF/pages/524124208/Introdu+o
---

### Definição
Incidente Crítico refere-se a uma grave ocorrência ou problema, envolvendo duas ou mais entidades **(bilateral ou multilateral)** que interrompe serviços críticos, resultando em impactos significativos nas operações ou na experiência dos clientes entre as Instituições.
### Objetivo
O objetivo da Gestão de Incidentes Críticos de Negócio é fornecer um protocolo estruturado para o tratamento e gerenciamento de incidentes críticos. Esse protocolo permite o engajamento, comunicação, orquestração, acompanhamento e documentação de todos os passos necessários até a resolução do incidente. Permite uma abordagem rápida e eficaz, visando minimizando os impactos negativos e acelerando a recuperação dos serviços impactados.
### Benefícios
A adoção desta prática traz diversos benefícios, incluindo:
- Foco: Direcionamento claro das ações necessárias para resolver o incidente crítico, evitando dispersão de esforços.
- Coordenação: Facilitação da colaboração entre diferentes entidades envolvidas, assegurando uma resposta coesa e alinhada.
- Engajamento: Envolvimento ativo de todas as partes interessadas, garantindo que todos os recursos e conhecimentos disponíveis sejam utilizados.
- Agilidade: Resposta rápida e eficiente aos incidentes, reduzindo o tempo de inatividade e os impactos nas operações e nos clientes.
- Gestão de Comunicação: Comunicação clara e consistente entre todas as partes envolvidas, melhorando a transparência e a confiança.
- Aprendizado: Documentação detalhada de todos os passos e decisões tomadas, permitindo a análise posterior e o aprendizado contínuo para melhorar futuras respostas a incidentes.

### Jornada do Incidente Crítico de Negócio
A jornada do incidente, fornece a visão de um conjunto essencial de prática de todos os passos até a resolução do incidente.
### Plano de Resposta a Incidentes Críticos de Negócio entre IFs

###

---

# Política de testes em produção > Diretrizes gerais dos testes em produção

---
id: 1209892867
title: Diretrizes gerais dos testes em produção
version: 5
modified: 2025-11-03T18:30:19.660Z
url: /spaces/OF/pages/1209892867/Diretrizes+gerais+dos+testes+em+produ+o
---

**Introdução**Este guia tem como objetivo disponibilizar aos participantes as diretrizes para testes em produção, incluindo seus objetivos, critérios e procedimentos operacionais. A realização desses testes é obrigatória para todas as instituições participantes, independentemente de sua modalidade de participação no Open Finance, e deverá ocorrer antes da disponibilização de novas marcas, produtos ou serviços à população.**Objetivos**A política de testes em produção está em consonância com as Resolução BCB 463, e tem como principais objetivos:I) Garantir o comportamento funcional dos produtos e serviços do Open Finance;II) Garantir uma jornada de experiência do usuário fluida e sem fricções ao usuário final;III) Garantir a qualidade de dados compartilhados;IV) Garantir a integração entre as instituições com as ferramentas de monitoramento do perímetro central;V) Garantir a interoperabilidade do ecossistema e reduzir a quantidade de incidentes bilaterais.**Modelos de testes em produção**Os testes em produção poderão ser realizados em modelos de piloto ou *onboarding.*
- Pilotos: Período previsto nos cronogramas de implementação aplicado ao lançamento de novos produtos e/ou funcionalidades por participantes ativos do ecossistema. O não atingimento de qualquer um dos critérios até o fim do piloto terá as seguintes consequências: Para consumidores de dados e serviços: não serão considerados aptos para disponibilizarem o produto para o público geral até atingimento de sucesso em todos os indicadores; Para provedores de dados e serviços: as instituições consumidoras de dados e serviços terão a opção de não mostrar a marca com problemas em produção até que a situação seja regularizada
- Onboarding : Processo de testes direcionado exclusivamente a novos entrantes no ecossistema ou participantes que queiram ofertar um produto adicional após o período de piloto desse produto. Novos entrantes obrigatórios no Open Finance deverão obter sucesso em todos os indicadores monitorados até 6 semanas da data de entrada da instituição; Novos entrantes voluntárias não possuem prazo para entrada em produção.
**Restrição de usuários**Durante o período de testes em produção, os novos produtos, funcionalidades ou marcas deverão ser restritos para uma base de usuários variável. Essa restrição é de responsabilidade da instituição consumidora de dados, enquanto o provedor não deve impedir o acesso a nenhum usuário.A Associação é responsável por coletar a lista de usuários testadores:
- das instituições participantes (consumidores e provedores de dados e serviços) geralmente, são recomendados cerca de 100 usuários por instituição, mas não é um critério obrigatório
- do Banco Central
- da Associação
- de responsáveis por testes
Exceto em alguns casos, essa lista deverá conter apenas o CPF dos usuários e ser compartilhada com os consumidores de maneira anonimizada. Os consumidores são responsáveis por garantir que essa lista de usuários possa testar a funcionalidade.Adicionalmente, a funcionalidade poderá ser disponibilizada para uma porcentagem da base de clientes, de maneira escalonada, a depender de aprovação em testes anteriores ou de tempo. Essa opção de liberar para base de clientes dependerá do produto sendo lançado, e poderá seguir o exemplo abaixo:
- 0% entre 01/01/20XX e 15/01/20XX;
- No mínimo 1% ou 2.000.000 entre 16/01/20XX e 15/02/20XX;
- No mínimo 5% ou 10.000.000 entre 16/02/20XX e 05/03/20XX;
- No mínimo 10% ou 20.000.000 entre 06/03/20XX e 20/03/20XX;
- No mínimo 50% ou 100.000.000 entre 21/03/20XX e 05/04/20XX;
- 100% a partir de 06/04/20XX ( fim do piloto ).
**Critérios de sucesso dos testes em produção**Durante o período de testes em produção, a instituição participante será monitorada pela Associação Open Finance, e deverá obter sucesso nos indicadores específicos de cada modalidade. Estes indicadores são:
| Item | Descrição |
| --- | --- |
| Comportamento funcional | Sucesso em módulos de teste da Ferramenta de Validação em Produção (FVP) |
| Jornada de experiência do usuário | Monitoramento simplificado da jornada de experiência do usuário |
| Integração com ferramentas do perímetro central | Pareamento de 95% das chamadas com a Plataforma de Coleta de Métricas (PCM) e envio de todos additionalInfos ou dados equivalentes do produto; Para os participantes que tenham utilização obrigatória do Motor de Qualidade de Dados (MQD), não haver apontamentos relativos a não envio ou qualidade. |
| Testes bilaterais | Realização de testes bilaterais entre instituições participantes, respeitando critérios específicos de volumetria e representatividade |
| Incidentes bilaterais | Resolução de todos os chamados em aberto até a conclusão do processo |
**Consulta de organizações homologadas**Instituições de organizações aptas a disponibilizar um produto ou serviço aos seus clientes finais podem ser consultadas através do Diretório de Participantes, não podendo haver nenhuma *flag*ou metadado da Família de API indicando status de homologação do recurso.

---

# Política de testes em produção > Restrição de recursos e habilitação de usuários para testes

---
id: 971341825
title: Restrição de recursos e habilitação de usuários para testes
version: 10
modified: 2026-02-06T17:42:45.816Z
url: /spaces/OF/pages/971341825/Restri+o+de+recursos+e+habilita+o+de+usu+rios+para+testes
---

Durante o período de testes em produção, os novos produtos, funcionalidades ou marcas deverão ser disponibilizados apenas para uma base controlada e variável de usuários, que poderá incluir funcionários ou prestadores de serviço de instituições participantes, funcionários ou prestadores de serviço da Associação Open Finance e servidores do Banco Central do Brasil.  A aplicação dessa restrição é de responsabilidade das instituições consumidoras de dados, cabendo às instituições provedoras de dados indicar, por meio do Diretório de Participantes, quais recursos se encontram em processo de homologação. À Associação Open Finance compete consolidar a relação de usuários habilitados para testes e disponibilizá-la às instituições consumidoras
1. Publicação no Diretório e configuração de restrição do recurso
Instituições provedoras de dados e serviços (transmissoras, detentoras e credoras originais) devem configurar a restrição de recurso no Diretório de Participantes no momento de publicação do recurso em produção.  
- Nova marca: Flag no servidor de autorização  Servidores de autorização > Editar servidor de autorização > Flags: “Homologacao” A atribuição dessa flag é exclusiva para novas organizações
- Novo produto ou funcionalidade em produto existente: Metadado na Família da API  Servidores de autorização > Recursos de API > Ações > Configurar Metadados da API: “Em homologacao” ou metadado específico a ser definido para cada piloto

1. Indicação de usuários para realização de testes em produção
Após a publicação, a instituição deverá indicar, por meio de formulário abaixo, a relação de usuários (CPFs) que deverão ser habilitados pelas consumidoras de dados e serviços (receptoras, iniciadoras e proponentes) para a realização de testes.  Para compartilhamento de **dados em massa**dos usuários, utilizar CSV, conforme seguinte modelo de arquivo: Os campos enviados, seja de forma individual ou em massa, devem necessariamente respeitar as seguintes regras abaixo. Caso contrário, os dados **não serão** enviados ou processados.
| Campo | Regra de preenchimento | Exemplo |
| --- | --- | --- |
| CPF | Apenas números, sem traços ou pontos | 38301141093 |
| CNPJ | 14 caracteres, sem traços ou pontos | 58569410000138 |
| Email | Endereço de e-mail dos usuários testadores¹ | email@openfinancebrasil.org.br |
| OrgID | Conforme OrgID da instituição no diretório, com traços | d7384bd0-842f-43c5-be02-9d2b2d5efc2c |
| Instituição | Conforme nome da instituição no diretório | ASSOCIACAO OPEN FINANCE |
1 Envio opcional. Exclusivo para utilização de Consumidores de Dados e Serviços que utilizam endereço de e-mail para habilitação de usuários para testes. Atualmente, apenas a ITP Google Pay declarou essa necessidade.**Formulário para compartilhamento dos dados dos usuários abaixo:**100%500
1. Verificação de restrição de uso
A aplicação da restrição é de **responsabilidade das instituições consumidoras de dados**, que deverão implementar mecanismo de consulta de restrição de recursos e habilitação dos usuários indicados pelas provedoras. A consulta desses usuários poderá ocorrer através do link [https://openfinance.app.n8n.cloud/webhook/participantes-piloto](https://openfinance.app.n8n.cloud/webhook/participantes-piloto)
- Credenciais para acesso à API podem ser solicitados para a Associação através de abertura de chamado no service desk
**Prazos de implementação de mecanismo de restrição e habilitação de usuários** Instituições consumidoras de dados deverão implementar os mecanismos de habilitação de usuários para testes em produção até **06/02/2026** 
- O onboarding de transmissores e detentores poderá ocorrer sem restrição de usuários até essa data. A partir de então, passará a ocorrer exclusivamente com a aplicação do fluxo de restrição
- O onboarding de receptoras e iniciadoras não depende deste fluxo para restrição usuários, e, portanto, os testes em produção deverão ocorrer com restrição imediata

---

# Política de testes em produção > Critérios de Onboarding > Onboarding de Detentores de Conta

---
id: 1209925664
title: Onboarding de Detentores de Conta
version: 8
modified: 2025-12-10T21:01:09.544Z
url: /spaces/OF/pages/1209925664/Onboarding+de+Detentores+de+Conta
---

**Obrigatoriedade de participação:**A participação na fase de iniciação de pagamentos na modalidade de detentora de conta é obrigatória para instituições obrigatórias no arranjo Pix. A participação é voluntária para as demais instituições.**Requisitos de atuação na modalidade:**
- Homologação no arranjo Pix: Instituição deve ter obtido sucesso nos testes de Open Finance no ambiente Pix tester, conforme https://mailchi.mp/1a06af40e3d4/open-banking-informa-10141804 ;
- Habilitação do papel regulatório: Habilitar papel “CONTA” no Diretório de Participantes;
- Publicação das APIs: Instituições obrigatórias no arranjo Pix: Necessário a publicação das APIs de Pagamentos e Pagamentos automáticos A publicação da API Vínculo de dispositivo será obrigatória a partir de fev/2026 Instituições voluntárias: Necessário publicação das APIs de Pagamentos e Pagamentos automáticos
**Restrição de funcionalidades para testes:**Nova marca detentora de conta: Indicação de *flag*“Homologacao” no servidor de autorização para caso de nova marca detentora de contaNovo produto (instituições voluntárias): Indicação de metadado “Homologacao” na Família da API.**Indicadores monitorados:**
| Item | Pagamentos (Imediato e agendados) | Pagamentos automáticos (Transf. Inteligentes e Pix automático) | Vínculo de Dispositivo (Jornada sem redirecionamento) |
| --- | --- | --- | --- |
| Comportamento funcional | Sucesso em todos os módulos dos planos de testes relativos à cada API, para todos os servidores de autorização, PF e PJ (quando aplicável) |
| fvp-payments-e2e_open_test-plan-v4 | fvp-automatic-payments_open_test-plan-v1 | fvp-no_redirect_payments_open_test-plan-v2 |
| Integração com ferramentas do perímetro central | Pareamento de 95% das chamadas com a Plataforma de Coleta de Métricas (PCM) e envio de todos additionalInfos |
| Testes bilaterais | Realização de pagamentos liquidados com 10 ITPs |
| 200 pagamentos, sendo: 100 imediatos 100 agendados | 200 pagamentos, sendo: 100 transferências inteligentes 100 pix automáticos 30 first payments 70 recurring payments | 100 pagamentos |
| Incidentes bilaterais | Resolução de todos os chamados em aberto até a conclusão do processo |
**Links úteis:**[Clique para acessar o Painel Integrado - Pagamentos](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/5a1cb1ad-921c-4548-95b7-2c8355af1233)[Clique para acessar o Painel Integrado - Pagamentos automáticos](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/bd53b4da-289e-465f-b9fa-c2954928b45f)[Clique para acessar o Painel Integrado - Jornada sem redirecionamento (Vínculo de Dispositivo)](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/1338e60a-c4d6-4a67-a861-7c5046ad7ac2)

---

# Política de testes em produção > Critérios de Onboarding > Onboarding de Iniciadores de Transações de Pagamentos (ITPs)

---
id: 1210318906
title: Onboarding de Iniciadores de Transações de Pagamentos (ITPs)
version: 4
modified: 2025-11-07T18:59:02.739Z
url: /spaces/OF/pages/1210318906/Onboarding+de+Iniciadores+de+Transa+es+de+Pagamentos+ITPs
---

**Obrigatoriedade de participação:**A participação na fase de iniciação de pagamentos na modalidade de instituição iniciadora de transação de pagamento (ITP) é opcional.**Requisitos de atuação na modalidade:**
- Autorização do Banco Central: Instituição deve estar listada na relação de participantes ativos do Pix divulgada diariamente pelo Banco Central, com a coluna “Iniciação” igual a Sim
- Certificação de segurança: Obter a certificação de segurança Relying Party (RP)
**Restrição de funcionalidades para testes:**Iniciadoras devem manter suas soluções de consumo de dados restrita ao público geral até a conclusão dos testes em produção.**Indicadores monitorados:**
| Item | Pagamento imediato | Agendamento único | Agendamento recorrente | Transf. Inteligentes | Pix automático | Jornada sem redirecionamento¹ |
| --- | --- | --- | --- | --- | --- | --- |
| Jornada de experiência do usuário | Monitoramento simplificado da jornada de experiência do usuário, de acordo com requisitos do Guia de UX. A instituição deverá anexar no chamado de onboarding uma evidência em vídeo que comprove a implementação da jornada de experiência do usuários seguindo os requisitos do Guia de UX. |
| Integração com as ferramentas do perímetro central | Pareamento de 95% das chamadas com a Plataforma de Coleta de Métricas (PCM) e envio de todos additionalInfos |
| Testes bilaterais | Realização de pagamentos liquidados com 20 detentoras¹, sendo pelo menos 50% das instituições pertencentes aos conglomerados do grupo de controle² |
| 100 pagamentos | 100 pagamentos | 100 pagamentos | 100 pagamentos | 100 pagamentos, sendo: 30 ( first payments ) 70 ( recurring payments ) | 100 pagamentos |
| Incidentes bilaterais | Resolução de todos os chamados em aberto até a conclusão do processo |
1 Para jornada sem redirecionamento, os testes podem ser realizados com 8 detentoras de conta até 22/04/2026
2 Banco do Brasil, Bradesco, BTG Pactual, Caixa Econômica Federal, Itaú Unibanco, Mercado Pago, Nubank, Pagbank, Picpay, Santander, Sicoob, Sicredi**Links úteis:**[Clique para acessar o Painel Integrado - Pagamentos](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/5a1cb1ad-921c-4548-95b7-2c8355af1233)[Clique para acessar o Painel Integrado - Pagamentos automáticos](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/bd53b4da-289e-465f-b9fa-c2954928b45f)[Clique para acessar o Painel Integrado - Jornada sem redirecionamento (Vínculo de Dispositivo)](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/1338e60a-c4d6-4a67-a861-7c5046ad7ac2)

---

# Política de testes em produção > Critérios de Onboarding > Onboarding de Receptores de Dados

---
id: 1210548229
title: Onboarding de Receptores de Dados
version: 4
modified: 2025-10-30T14:33:14.145Z
url: /spaces/OF/pages/1210548229/Onboarding+de+Receptores+de+Dados
---

**Obrigatoriedade de participação:**A participação na fase na modalidade de receptora de dados é opcional, mas deve seguir o principio da reciprocidade do compartilhamento do dado.**Requisitos de atuação na modalidade:**
- Habilitação do papel regulatório: Habilitar papel “DADOS” no Diretório de Participantes;
- Reciprocidade: Instituições devem atuar no compartilhamento de dados.
**Restrição de funcionalidades para testes:**Receptoras de dados devem manter suas soluções de consumo de dados restrita ao público geral até a conclusão dos testes em produção.**Indicadores monitorados:**
| Item | Descrição |
| --- | --- |
| Jornada de experiência do usuário | Monitoramento simplificado da jornada de experiência do usuário, de acordo com requisitos do Guia de UX A instituição deverá anexar no chamado de onboarding uma evidência em vídeo que comprove a implementação da jornada de experiência do usuários seguindo os requisitos do Guia de UX. |
| Integração com ferramentas do perímetro central | Pareamento de 95% das chamadas com a Plataforma de Coleta de Métricas (PCM) e envio de todos additionalInfos |
| Testes bilaterais | Realização de 100 consentimentos únicos com 20 transmissoras diferentes, sendo pelo menos 50% das instituições pertencentes aos conglomerados do grupo de controle¹ |
| Incidentes bilaterais | Resolução de todos os chamados em aberto até a conclusão do processo |
1 Banco do Brasil, Bradesco, BTG Pactual, Caixa Econômica Federal, Itaú Unibanco, Mercado Pago, Nubank, Pagbank, Picpay, Santander, Sicoob, Sicredi**Links úteis:**[Clique para acessar o Painel Integrado - Dados do cliente](https://sa-east-1.quicksight.aws.amazon.com/sn/accounts/471112653989/dashboards/d364bb5c-9c1c-4863-8094-106672da4cfd/sheets/d364bb5c-9c1c-4863-8094-106672da4cfd_9fd57eaa-67b7-4c33-bc03-d344d518b507)

---

# Política de testes em produção > Critérios de Onboarding > Onboarding de Transmissores de Dados

---
id: 995131396
title: Onboarding de Transmissores de Dados
version: 12
modified: 2025-11-03T18:30:37.131Z
url: /spaces/OF/pages/995131396/Onboarding+de+Transmissores+de+Dados
---

**Obrigatoriedade de participação:**A participação na fase de compartilhamento de dados é obrigatória para instituições S1 e S2 e instituições individuais ou participantes de conglomerados com 5 milhões de clientes por dois trimestres consecutivos. A participação é voluntária para as demais instituições.**Requisitos de atuação na modalidade:**
- Habilitação do papel regulatório: Habilitar papel “DADOS” no Diretório de Participantes;
- Publicação das APIs: Instituições que participarem na fase de compartilhamento de dados devem realizar a publicação das APIs de todos os produtos que ofertarem.
**Restrição de funcionalidades para testes:**Indicação de *flag*“Homologacao” no servidor de autorização.**Indicadores monitorados:**
| Item | Descrição |
| --- | --- |
| Comportamento funcional | Sucesso no módulo de teste fvp-customer_data_unique_happy_path_test-module, para todos os servidores de autorização, PF e PJ (quando aplicável) |
| Compartilhamento com sucesso dos produtos ofertados pela instituição |
| Integração com ferramentas do perímetro central | Pareamento de 95% das chamadas com a Plataforma de Coleta de Métricas (PCM) e envio de todos additionalInfos; Para os participantes que tenham utilização obrigatória do Motor de Qualidade de Dados (MQD), não haver apontamentos relativos a não envio ou qualidade. |
| Testes bilaterais | Realização de 100 consentimentos únicos com 10 receptoras diferentes |
| Incidentes bilaterais | Resolução de todos os chamados em aberto até a conclusão do processo |
**Links úteis:**[Clique para acessar o Painel Integrado - Dados do cliente](https://sa-east-1.quicksight.aws.amazon.com/sn/accounts/471112653989/dashboards/d364bb5c-9c1c-4863-8094-106672da4cfd/sheets/d364bb5c-9c1c-4863-8094-106672da4cfd_9fd57eaa-67b7-4c33-bc03-d344d518b507)

---

# Política de testes em produção > Critérios de Onboarding > Solicitação de participação de processo de onboarding de novos entrantes

---
id: 932970497
title: Solicitação de participação de processo de onboarding de novos entrantes
version: 16
modified: 2025-10-30T14:18:27.955Z
url: /spaces/OF/pages/932970497/Solicita+o+de+participa+o+de+processo+de+onboarding+de+novos+entrantes
---

**Processo de solicitação de*****onboarding***
- O processo de onboarding será conduzido através do service desk. As instituições interessadas deverão abrir um chamado na categoria Requisições > Processo de onboarding > Solicitação de interesse de participação;
- Após validação das informações do formulário, o atendimento de nível 1 irá adicionar uma nota com orientação para inicio dos testes pelas instituições e alterar o status do ticket para ‘Aguardando requisitante’;
- Após atualização do status do ticket para ‘Aguarda requisitante’, a instituição poderá iniciar os testes. Assim que identificar sucesso em todos os indicadores, a instituição deverá retornar o ticket para avaliação da Associação através do status ‘Encaminhado N2’ Critérios de comportamento funcional, integração com ferramentas, testes bilaterais e incidentes bilaterais poderão ser acompanhados pela instituição através dos Painéis de produto disponibilizados na Plataforma de Visualização de Dados;
- Caso a instituição obtiver sucesso em todos os indicadores do onboarding, ela será autorizada a disponibilizar seus produtos e serviços à população. Caso contrário, o ticket será retornado para a instituição até atingimento de todos os critérios

---

# Política de testes em produção > Critérios de Piloto > Piloto de Jornada sem redirecionamento (JSR) 2.2.0

---
id: 1449754670
title: Piloto de Jornada sem redirecionamento (JSR) 2.2.0
version: 25
modified: 2026-02-12T21:12:47.089Z
url: /spaces/OF/pages/1449754670/Piloto+de+Jornada+sem+redirecionamento+JSR+2.2.0
---

**Introdução**O piloto da Jornada sem Redirecionamento 2.2.0 está previsto para ocorrer entre 06/02/2026 e 21/04/2026 e tem como objetivo testar a participação de novos entrantes na jornada e validar, para as instituições já operantes, as novas funcionalidades introduzidas nesta versão, incluindo o produto Pix Automático, o suporte ao ambiente desktop e a ampliação da jornada para o segmento PJ.**Obrigatoriedade de participação**O piloto será obrigatório para: 
- Instituições Detentoras de conta : Que já operam JSR : Instituições que participaram do piloto de JSR v2.1.0 deverão realizar testes exclusivamente para as funcionalidades introduzidas na v2.2.0 Novos entrantes : Instituições obrigatórias no arranjo Pix deverão obter sucesso nos testes de todos os escopos da jornada sem redirecionamento (Pagamentos imediatos e agendados; Pix automático; PF; PJ; Mobile e Desktop)
- Instituições Iniciadoras de Transação de Pagamentos (ITPs) : Instituições que optarem por disponibilizar serviços de JSR para os novos produtos e serviços introduzidos neste versionamento: JSR – Pagamentos imediatos e agendados JSR – Pix automático – Mobile JSR – Pix automático – Desktop
**Declaração de interesse em participação – ITPs**Para que seja uma instituição participante do piloto de JSR v2.2.0, **a ITP deverá abrir um ticket no service desk até 30/01/2026, indicando o produto, segmento e ambiente que pretende ofertar.**A ITP deve abrir um ticket por produto na categoria Processo de onboarding > Solicitação de interesse em participação > Iniciadora e selecionar a opção do produto que deseja ofertar:
- JSR – Pagamentos imediatos e agendados
- JSR – Pix automático
Instituições que optarem por disponibilizar a funcionalidade após essa data deverão realizar os testes em produção seguindo a política de onboarding do Open Finance e não farão parte deste go live **Público participante do piloto e restrição de usuários**O piloto de jornada sem redirecionamento ocorrerá exclusivamente com restrição de usuários e seguirá a política vigente de testes em produção do Open Finance, cujos detalhes podem ser consultados na guia [Restrição de recursos e habilitação de usuários para testes em produção](https://openfinancebrasil.atlassian.net/wiki/x/AYDlOQ).
- Instituições detentoras de conta: Que já operam JSR: Deverão indicar o metadado da Familia de API ‘Em homologacao' novos recursos’ no momento de publicação da API no Diretório de Participantes Novos entrantes: Deverão indicar o metadado da Familia de API ‘Em homologacao’ no momento de publicação da API no Diretório de Participantes A partir de 23/01/2026 deverão indicar os usuários que deverão ser habilitados pelas ITPs para realização de testes. Informações adicionais serão compartilhadas nessa data
- Instituições iniciadoras de transação de pagamentos: As credenciais de acesso para a API de consumo dos recursos dos usuários serão disponibilizadas pelo service desk até 23/01/2026
**Indicadores de sucesso das instituições****Detentoras**
| Item | Indicador | Detalhe do requisito | Obrigatoriedade |
| Implementação de jornada adequada | Atendimento de requisitos mínimos | Área de gestão (com edição de limites) | Exclusivo para marcas detentoras do grupo de controle |
| Comportamento funcional e de segurança | Execução com sucesso dos testes na FVP Manual | Sucesso em todos os testes de jornada sem redirecionamento para todos os servidores de autorização (PF e PJ, quando aplicável) 11 módulos de Vínculo + Pagamentos imediatos 5 módulos de Vínculo + Pagamento (Pix Automático) | Todas as detentoras de conta •Instituições que já tenham participado do piloto de JSR estão dispensada da execução de testes de vínculo + pagamentos imediatos (PF) |
| Integração com ferramentas | % pareamento de chamadas | >= 95% PAIRED | Todas as detentoras de conta |
| Envio de additionalinfos | Envio de 100% de additionalInfos |
| Engajamento | Liquidação de pagamentos | Realização de pagamentos liquidados a partir do vínculo de dispositivo com 10 ITPs ou o máximo de ITPs que ofertar o produto | Todas as detentoras de conta |
| 100 pagamentos, com pelo menos 30 pagamentos agendados e 15 pagamentos PJ 100 pagamentos (Pix automático), com pelo menos 30 first payments, 70 recurring payments e 15 pagamentos PJ |
| Comportamento bilateral | Tickets bilaterais abertos | Sem tickets bilaterais aberto no final do processo | Todas as detentoras de conta |
**ITPs**
| Item | Indicador | Pagamentos imediatos e agendados | Pix automático |
| Implementação de jornada adequada | Atendimento de requisitos mínimos | Vínculo e Pagamento + Área de gestão Mobile e/ou desktop | Vínculo e Pagamento (Pix automático) + Área de gestão Mobile e/ou desktop O vínculo com a empresa recebedora (CNPJ recebedor) é de total responsabilidade da instituição iniciadora de pagamento. Será permitida, de forma voluntária, a utilização do CNPJ de um cliente da iniciadora de pagamentos que não tenha contrato firmado para o produto de Pix Automático. O uso deve ser restrito a testes e não pode envolver a contratação do produto “real”. |
| Integração com ferramentas | % pareamento de chamadas | >= 95% PAIRED |
| Envio de additionalinfos | Envio de 100% de additionalInfos |
| Engajamento | Liquidação de pagamentos | Realização de pagamentos liquidados com 20 detentoras, sendo pelo menos 50% das instituições pertencentes aos conglomerados do grupo de controle¹ |
| 100 pagamentos, com pelo menos 30 pagamentos agendados e 15 pagamentos PJ (se a instituição ofertar este serviço) | 100 pagamentos (Pix automáticos), com pelo menos 30 first payments, 70 recurring payments e 15 pagamentos PJ |
| Comportamento bilateral | Tickets bilaterais abertos | Sem tickets bilaterais aberto no final do processo |
1Banco Bradesco S.A., Banco BTG Pactual S.A., Banco C6 S.A., Banco Digio S.A., Banco do Brasil S.A., Banco Inter S.A.., Banco Pan S.A., Banco Santander (Brasil) S.A., Banco Votorantim, Banco XP S.A., Caixa Econômica Federal, CloudWalk, Sicredi, Sicoob, Itaú Unibanco S.A., Mercado Pago, Neon Pagamentos S.A., Nu Pagamentos S.A., PagSeguro, PicPay**Relação de ITPs participantes**
| | Pagamentos imediatos e agendados | Pix Automático | Canal ofertado |
| Instituição | PF-Mobile | PJ | Desktop | PF | PJ | Mobile | Desktop |
| BANCO BTG PACTUAL | ITP Homologada | X | X | | | | | https://developer.btgpactual.com/login |
| Belvo IP | ITP Homologada | | X | | | | | https://jsr.belvo.com |
| CUMBUCA IP | ITP Homologada | X | X | X | X | X | X | https://juspay.io/demoapp |
| Iniciador IP | ITP Homologada | X | X | X | X | X | X | https://app.iniciador.com.br/jsr/login |
| LINA IP | ITP Homologada | X | X | X | X | X | X | https://doacao.linaopenx.com.br/ |
| MUEVY IP | ITP Homologada | X | X | | X | X | X | https://app.openfinance.muevy.com.br/jsr |
| PLUGGY | | X | X | | X | X | X | https://app.of.pluggy.ai/jsr |
**Relação de ITPs Homologadas (Pagamentos-PF-Mobile)**As instituições abaixo já obtiveram autorização para disponibilizar a jornada sem redirecionamento para pagamentos imediatos, pessoa física em ambiente mobile. Embora não sejam participantes deste Piloto, suas soluções poderão ser utilizadas pelos detentores para atingimento dos testes bilaterais:ADYEN
BANCO BRADESCO
BANCO RIBEIRAO PRETO
CELCOIN
DLOCAL BRASIL IP
EFI S.A. - IP
GOOGLE PAY
OKTO IP******Cronograma do piloto****Certificação FIDO**Instituições detentoras de conta deverão registrar a certificação FIDO no seu servidor de autorização no momento de publicação da API Vínculo de Dispositivo no tipo de perfil ‘Others’ e variante ‘FIDO’.
- Se for feita uma certificação própria utilizar a URL https://fidoalliance.org/certification/fido-certified-products/
- Se utilizar um servidor de terceiro certificado utilizar URL para o site do produto utilizado (página do AS utilizado)
**Painel Integrado de acompanhamento de indicadores**Para o devido acompanhamento das métricas e indicadores de Portabilidade de Crédito, foi-se construído o [Painel de Jornada sem redirecionamento](https://sa-east-1.quicksight.aws.amazon.com/sn/account/openfinance-brasil/dashboards/1338e60a-c4d6-4a67-a861-7c5046ad7ac2). Nele, poderão ser encontradas as métricas de acompanhamentos da PCM, pagamentos liquidados, acompanhamento funcional da FVP, dentre outros; Para solicitação de **acesso ao painel**, é necessário que sejam seguidas as seguintes instruções: 
- O usuário deve-se cadastrar, em sua instituição no diretório dos participantes, o seu email com acesso à funcionalidade PDV.
- Para isso, na página da sua instituição no diretório dos participantes, acesse: Papéis > Usuários de domínio > Adicionar novo > Data visualization platform > PDV
- Após isso, o usuário irá receber um email do diretório confirmando o seu devido cadastrado
- Após execução da rotina de concessão de acesso, realizada ao final de cada dia, o usuário deverá receber um email do Quicksight com as devidas orientações para cadastro
- No momento de realização do login, caso solicitado, é necessário inserir em “ account name ”, o seguinte valor “openfinance-brasil”
**Acompanhamento com as instituições**Para melhor apoiar as instituições participantes do Piloto de Jornada sem redirecionamento a Associação acompanhará e apoiará as instituições durante todo o período do Piloto através de: 
- Agendas semanais : Toda sexta-feira, das 15h às 16h, de 13/02/26 a 22/05/26    Para compartilhamento de informações relevantes, e esclarecimento de dúvidas com a Associação ou bilaterais com demais instituições
- Grupo do Whatsapp : Para dúvidas pontuais e interações com outras instituições ou Associação  Clique aqui para acessar o Grupo do Whatsapp  do Piloto de JSR 2.2.0, ou escaneie o QR Abaixo com a câmera de seu celular:
 **Outros links úteis**
- 
- Descrição dos testes da FVP Manual: Link aqui
- Painel de consulta de contas abertas
- Workshop do Piloto de Jornada sem redirecionamento - 23/01/2026
- Material do Workshop:

---

# Política de testes em produção > Critérios de Piloto > Piloto de Portabilidade de Crédito Pessoal Clean (CPC)

---
id: 1171619917
title: Piloto de Portabilidade de Crédito Pessoal Clean (CPC)
version: 21
modified: 2026-01-30T21:07:31.252Z
url: /spaces/OF/pages/1171619917/Piloto+de+Portabilidade+de+Cr+dito+Pessoal+Clean+CPC
---

## Introdução
Está sendo lançado o novo produto de Portabilidade de Crédito (CPC). Com isso, tem-se como intuito, nesta página, a centralização das informações relevantes para compartilhamento com as instituições participantes do **Piloto de Portabilidade de Crédito**, que será realizado de **03/11/2025 a 01/02/2026**. 
## Objetivos do Piloto
O período do Piloto para novos produtos do Open Finance Brasil possui os seguintes **objetivos**: 
- Garantir o funcionamento e a interoperabilidade de novos produtos e APIs em ambiente produtivo ;
- Validar as integrações e o funcionamento das APIs dos participantes;
- Antecipar a identificação de problemas em ambiente produtivo;
- Viabilizar a criação de agendas (bilaterais e multilaterais) antes do Go Live , para antecipação e correção de eventuais problemas e dificuldades encontradas;

## Especificações da Portabilidade de Crédito

- Informações Gerais sobre as funcionalidades da API de Portabilidade de Crédito podem ser encontradas nessa página;
- Informações Técnicas podem ser encontradas nessa página;
- Histórico das especificações podem também ser encontrados no portal do desenvolvedor.

## Obrigatoriedade de participação
O piloto será obrigatório para: 
- Instituições Credoras Originais : Instituições que possuem a API de Loans publicada e que possuem o produto de Crédito Pessoal Clean (CPC);
- Instituições Proponentes : Instituições que são obrigatoriamente credoras e que também optarem por ofertarem o produto como proponentes.

## Público participante do piloto e restrição de usuários
Para viabilizar o piloto, a nova funcionalidade deve ser inicialmente disponibilizada para um público restrito, que contempla apenas funcionários das próprias instituições, servidores do Banco Central, equipe responsável pela execução dos testes e membros da Associação Open Finance; O formulário abaixo deve ser preenchido para que os usuários tenham acesso à funcionalidade das Proponentes: **Formulário de compartilhamento de usuários**Para acesso à fucionalidade de Portabilidade nas proponentes, as instituições credoras podem enviar as informações de forma individual ou em em massa, através de upload de arquivo csv.Para compartilhamento de **dados em massa**dos usuários, utilizar CSV, conforme seguinte modelo de arquivo: Os campos enviados, seja de forma individual ou em massa, devem necessariamente respeitar as seguintes regras abaixo. Caso contrário, os dados **não serão** enviados ou processados.
| Campo | Regra de preenchimento | Exemplo |
| --- | --- | --- |
| CPF | Apenas números, sem traços ou pontos | 38301141093 |
| Email (opcional) | Endereço de e-mail dos usuários testadores | email@openfinancebrasil.org.br |
| OrgID | Conforme OrgID da instituição no diretório, com traços | d7384bd0-842f-43c5-be02-9d2b2d5efc2c |
| Instituição | Conforme nome da instituição no diretório | ASSOCIACAO OPEN FINANCE |
**Formulário para compartilhamento dos dados dos usuários abaixo:**100%500A liberação de acesso aos usuários pelas instituições deverá acontecer conforme regras abaixo, a depender do escopo de atuação: 
- Instituições Credoras : Funcionalidade deverá ser disponibilizada para toda a base de usuários .
- Instituições Proponentes: Funcionalidade deverá ser disponibilizada para base de usuários restrita, de forma faseada, seguindo-se as seguintes etapas:
**1 - Validação da jornada**: 
- Acesso à funcionalidade deve ser compartilhada com base de usuários restrita, apenas aos CPFs de usuários compartilhados pela Associação diretamente às Proponentes;
- A base de usuários restrita contempla apenas funcionários das próprias instituições, servidores do Banco Central, equipe responsável pela execução dos testes e membros da Associação Open Finance;
- Após validação da jornada do produto da proponente pela Associação, a instituição poderá seguir para a próxima etapa.
**2 - Liberação gradual da jornada**: 
- Além do acesso à funcionalidade ser mantida à base de usuários restrita, a instituição poderá disponibilizar a funcionalidade à sua base de clientes;
- Para jornadas validadas (Etapa 1) até 05/01/2026   0% da base até 31/11/2025  Até 1% ou 2.000.000 de clientes entre 01/12/2025 e 04/01/2025  Até 10% ou 20.000.000 de clientes entre 05/01/2026 e 18/01/2026  Até 50% ou 100.000.000 de clientes entre 19/01/2026 e 01/02/2026  100% da base de clientes a partir de 02/02/2026 (Go Live)
- Para jornadas validadas (Etapa 1) a partir de 06/01/2026   Até 1% ou 2.000.000 de clientes a partir da validação da jornada  Até 10% ou 20.000.000 de clientes a partir de 2 semanas depois da validação  Até 50% ou 100.000.000 de clientes a partir de 4 semanas depois da validação  100% da base de clientes a partir de 6 semanas depois da validação

## Indicadores de sucesso das instituições

### Painel Integrado de acompanhamento de indicadores
Para o devido acompanhamento das métricas e indicadores de Portabilidade de Crédito, foi-se construído o [Painel Integrado de acompanhamento do Piloto](https://sa-east-1.quicksight.aws.amazon.com/sn/accounts/471112653989/dashboards/e47c20c3-aaf2-49ac-a065-9d8db31bc05b?directory_alias=openfinance-brasil) (Será utilizado o mesmo painel de acompanhamento das certificações. Métricas e critérios de acompanhamento do Piloto estão em construção). Nele, poderão ser encontradas as métricas de acompanhamentos da PCM, portabilidades concluídas, acompanhamento funcional da FVP, dentre outros; Para solicitação de **acesso ao painel**, é necessário que sejam seguidas as seguintes instruções: 
- O usuário deve-se cadastrar, em sua instituição no diretório dos participantes, o seu email com acesso à funcionalidade PDV.
- Para isso, na página da sua instituição no diretório dos participantes, acesse: Papéis > Usuários de domínio > Adicionar novo > Data visualization platform > PDV
- Após isso, o usuário irá receber um email do diretório confirmando o seu devido cadastrado
- Após execução da rotina de concessão de acesso, realizada ao final de cada dia, o usuário deverá receber um email do Quicksight com as devidas orientações para cadastro
- No momento de realização do login, caso solicitado, é necessário inserir em “ account name ”, o seguinte valor “openfinance-brasil”

### Critérios e indicadores a serem acompanhados
Durante o piloto, os seguintes **indicadores serão monitorados**: 
- Plataforma de Coleta de Métricas (PCM) : Todas as instituições devem ter, em D+1, ao menos 95% de pareamentos com sucesso na PCM;
- UX : Durante o período do piloto, serão realizadas validações de UX para as marcas participantes do Piloto. O questionário de UX, que será utilizado de base para validação das jornadas as instituições, será integralmente baseado nos requisitos do Guia de Experiência do Usuário .
- Tickets bilaterais : Tickets bilaterais relativos ao Piloto de Portabilidade de Crédito considerados críticos (sob avaliação e demanda da DTO) devem ser encerrados previamente ao final do piloto, independentemente de sua data de abertura ou do seu SLA ;
- Ferramenta de Validação em Produção - FVP Manual : As credoras participantes devem obter o sucesso nos testes relacionados à FVP Manual. A responsabilidade de execução e obtenção de sucesso nos testes varia de acordo a classificação de cada marca participante, detalhado na seção abaixo "Grupos de validação para o Piloto de Portabilidade de Crédito - Credoras".
- Engajamento - Portabilidades Concluídas : Para cada instituição participante do piloto, um número mínimo de portabilidades deve ser concluído e identificado com sucesso via PCM, até data ainda a ser definida (pendente garantia de maturidade de proponentes através de validações da Associação):  Para Proponentes : 10 Portabilidades devem ser concluídas e identificadas com sucesso via PCM;  Para Credoras : 5 Portabilidades devem ser concluídas e identificadas com sucesso via PCM;  Pontos de atenção às instituições  Portabilidade solicitadas podem levar até 7 dias úteis para serem devidamente concluídas e identificadas com sucesso via PCM  Cada instituição é responsável por atingir as próprias portabilidades concluídas
**Grupos de validação para o Piloto de Portabilidade de Crédito - Credoras** Com a necessidade de contratação do produto CPC para execução dos testes da FVP ou validações das jornadas de UX, algumas premissas são necessárias serem estabelecidas para classificação das marcas das Credoras originais em diferentes grupos.  As marcas das **Credoras Originais** participantes do Piloto serão divididas em 2 Grupos**:** 
- Grupo 1 : Marcas que o fornecedor possui conta aberta e possui o produto de CPC contratado para realização de validações com a instituição.  FVP Manual : Sucesso completo esperado nos 3 cenários de curta duração e em um cenário de longa duração, sob responsabilidade de execução do fornecedor;  Validações de UX : Sucesso completo esperado no questionário de UX, sob responsabilidade de execução do fornecedor;  Engajamento: Sucesso em ao menos 5 Portabilidades concluídas e identificadas com sucesso via PCM, sob responsabilidade das instituições. As instituições também poderão realizar a solicitação de portabilidade via fornecedor.
- Grupo 2 : Demais Marcas, que o fornecedor não possui conta aberta ou não possui o produto de CPC contratado para realização de validações com a instituição.  Execução da FVP : Sucesso completo esperado nos 3 cenários de curta duração, sob responsabilidade de execução da própria instituição;  Validações de UX : Sucesso completo esperado no questionário de UX. A jornada em ambiente produtivo deverá ser gravada pela instituição e disponibilizada à Associação para validação.  Engajamento: Sucesso em ao menos 5 Portabilidades concluídas e identificadas com sucesso via PCM, sob responsabilidade das instituições. As instituições do Grupo 2 não poderão realizar a solicitação de portabilidade via fornecedor.
A relação de segmentação de cada marca pode ser acompanhada através do [Painel Integrado de Acompanhamento do Piloto de Portabilidade de Crédito Pessoal Clean (CPC)](https://sa-east-1.quicksight.aws.amazon.com/sn/accounts/471112653989/dashboards/e47c20c3-aaf2-49ac-a065-9d8db31bc05b/sheets/e47c20c3-aaf2-49ac-a065-9d8db31bc05b_ec55b994-79d8-4c94-b229-c40d7ff444a4); 
### Consequências em caso de não atingimento dos critérios
**Instituições Credoras**: 
- Que não atingirem os critérios até 2 semanas antes do final do piloto : Serão realizados War rooms para apresentação e acompanhamento de planos de ação;
- Que não atingirem os critérios até o final do piloto : Credora poderá não ser listada pelas ITPs na utilização de Portabilidade de Crédito.
**Instituições Proponentes**: 
- Com Jornadas disponíveis e validadas após 06/01/26 : Não participam do Piloto e terão a funcionalidade disponível para toda a base de clientes após conclusão de processo de onboarding ;
- Que não atingirem os critérios até 2 semanas antes do final do piloto : Serão realizados War rooms para apresentação e acompanhamento de planos de ação;
- Que não atingirem os critérios até o final do piloto : Não poderão disponibilizar a funcionalidade em produção.
 
## Cronograma de execução dos testes manuais para o Piloto de Portabilidade de Crédito
Com o intuito de dar mais visibilidade ao ecossistema quanto ao cronograma de execução da FVP e de execução de UX pelo fornecedor, compartilhamos, abaixo, as datas previstas que serão realizadas as validações com as Credoras e Proponentes participantes do piloto. 
## Validações de UX para Credoras do Grupo 2
Com o objetivo de realizarmos as validações da experiência de usuário (UX) da área de gestão de portabilidade de crédito das Credoras Originais do Grupo 2, estão abaixo descritas as instruções para validação de **(a)** **portabilidade canceladas ou em andamento; (b) portabilidade concluídas**.
### 1. Preparação da gravação
Para que a jornada seja possível de ser validada, os seguintes pré-requisitos devem ser atendidos pelas credoras:
1. A jornada que será gravada pela instituição deverá utilizar um aplicativo atualizado , contemplando a última versão disponível e utilizando um usuário real em ambiente produtivo. Gravações realizadas em emuladores ou qualquer outro cenário que não representem um aplicativo em ambiente produtivo não serão considerados. Para o caso de instituições que não tenham habilitação para gravação das jornadas do aplicativos, é solicitado que seja utilizado um segundo aparelho para gravação da tela.
2. Para validação da área de gestão, o usuário deverá ter ao menos um contrato de crédito ativo (CPC) que possa ser utilizado para a jornada de portabilidade. Caso não exista, o usuário deverá: Contratar um Crédito Pessoal Clean (CPC); Garantir que o contrato esteja ativo e visível no aplicativo.
3. Para validação das jornadas de UX, é necessário que tenham Portabilidade cancelada ou em andamento (Teste 1): É necessário que uma portabilidade esteja “Cancelada” ou “Em andamento”. Para que uma portabilidade esteja em qualquer um desses dois status, é possível seguir as seguintes alternativas: Via FVP: O sucesso em qualquer um dos testes da FVP garantirá que uma portabilidade será cancelada, podendo seguir para a gravação da jornada do Teste 1 (Etapa 3 “Gravação das jornadas”). Via Proponente : Funcionalidades de portabilidade de proponentes também podem ser utilizadas para que uma portabilidade vá para o status de “Em andamento” ou “Cancelada”. Portabilidade concluídas (Teste 2): É necessário que uma portabilidade esteja “Concluída”, necessariamente utilizando-se a funcionalidade de portabilidade de uma proponente.

### 2. Gravação das jornadas
Para validação das jornadas das credoras, é necessário que em uma **única gravação** **de tela**, sem interrupção, apareçam as seguintes informações, presentes no questionário e sendo requisitos do Guia de Experiência do Usuário:
- Nome da credora
- Taxa
- Valor da parcela
- Número de parcelas
- Saldo devedor
- Número do contrato

### 3. Disponibilização das evidências
Após conclusão da etapa 3 “Gravação das jornadas”, a jornada deverá ser disponibilizada para validação da estrutura através da seguinte categoria do Service Desk: Processo de Onboarding > Solicitação de Interesse em Participação > Credora Original.Os títulos dos tickets abertos devem seguir o seguinte padrão: 
- “Teste 1 – Jornada de portabilidade em andamento ou cancelada”, para validação da área de gestão de portabilidades com status em andamento ou cancelada
- “Teste 2 – Jornada de portabilidade concluída”, para validação da área de gestão de portabilidades com status concluída

## Instruções para utilização da Proponente - Caixa

### Material de apoio: “Jornada de Portabilidade Empréstimo pessoal Clean via Caixa“

### Pré-requisitos para realização de uma portabilidade de Crédito Pessoal Clean (CPC) via Caixa
Para que uma solicitação de portabilidade de Crédito Pessoal Clean (CPC) seja realizada utilizando-se a**Caixa Econômica Federal como instituição proponente**, é necessário garantir o atendimento de todos os pré-requisitos abaixo. Se alguma dessas condições não for cumprida, a portabilidade **não poderá ser iniciada** ou autorizada.Pré-requisitos para utilização da Caixa como instituição proponente: 
- CPF incluído no formulário: O CPF do usuário (funcionário participante do piloto) deve ser previamente cadastrado por meio do formulário de compartilhamento de usuários disponibilizado nesta mesma página. Somente os CPFs enviados e validados conforme as regras definidas (apenas números, sem pontos ou traços, por exemplo) estarão habilitados a acessar a funcionalidade de portabilidade nas instituições proponentes. Caso o CPF não tenha sido compartilhado, o usuário não conseguirá visualizar nem iniciar a portabilidade envolvendo a Caixa durante esse período. Segundo regras compartilhadas pela própria instituição, as atualizações dos CPFs ocorrem 2x por semana, todas as segundas-feiras e quintas-feiras, por volta das 12h, com base nos dados preenchidos no formulário até o final do dia anterior.
- Conta ativa na Caixa: É necessário que o usuário possua uma conta corrente aberta e ativa na Caixa Econômica Federal. Se o usuário não for correntista ativo da Caixa, não será possível prosseguir com a portabilidade para essa instituição, pois o cliente precisa ter vínculo ativo (cadastro e conta) na Caixa para solicitar uma portabilidade de crédito. A abertura de conta deve ocorrer em unidade física da Caixa, apresentando Documento de identificação original ou CNH digital gerada no APP CNH do Brasil.
- Crédito pré-aprovado na Caixa: O usuário deve estar aprovado na política de crédito pessoal da Caixa para realizar uma solicitação de portabilidade. Para verificar previamente se há aprovação de crédito, o usuário deverá acessar o aplicativo CAIXA e navegar até: Menu Empréstimos > Empréstimo Pessoal > Simular e Contratar. Se ao fazer isso for exibida uma simulação de empréstimo disponível para contratação, significa que o cliente possui crédito aprovado na Caixa. Ao invés disso, caso apareça uma opção de “atualização cadastral”, significa que, naquele momento, não há aprovação e o cliente deve atualizar seus dados. No dia subsequente após atualização, caso a opção de simulação/contratação ainda não estiver disponível, indica que o usuário não foi aprovado na política de crédito da instituição. Nessa situação, a portabilidade não poderá ser realizada , pois não há aprovação de crédito para efetivar a transferência do contrato.
- Compartilhamento de dados (Open Finance): O usuário precisa autorizar o compartilhamento de seus dados financeiros via Open Finance envolvendo a Caixa e a instituição detentora do contrato original. Esse procedimento deve ser realizado pelo próprio app da Caixa, onde o usuário seleciona a instituição de origem do crédito e consente o compartilhamento dos dados solicitados. Sem o devido compartilhamento de dados aprovado, a Caixa não conseguirá recuperar os detalhes do contrato original do cliente, impedindo uma solicitação de portabilidade.
- Contrato elegível em outra instituição: Por fim, o usuário deve ter um contrato de Crédito Pessoal Clean (CPC) ativo em outra instituição financeira. Além de estar ativo, esse contrato precisa atender a alguns critérios mínimos de elegibilidade para a portabilidade ser possível via Caixa:  Saldo devedor maior que R$ 150,00: Contratos com saldos abaixo não são elegíveis.  Valor da parcela mensal acima de R$ 20,00: Parcelas de valor muito baixo não se qualificam.  Taxa de juros do contrato original superior à taxa ofertada pela Caixa: O juros vigente no empréstimo atual do cliente deve ser maior do que o juro que a Caixa oferece no novo crédito via portabilidade. A taxa oferecida pela Caixa para portabilidade não é divulgada previamente e pode variar conforme políticas internas da instituição, havendo a necessidade de vantagem financeira para o cliente na migração. Para saber qual taxa será aplicada na oferta de portabilidade, o usuário pode acessar os detalhes ao realizar uma simulação de portabilidade.

### Passo a passo para realização de solicitação de portabilidade via Caixa
Atendidas todas as condições acima, o funcionário/usuário participante do piloto poderá realizar o processo de portabilidade do seu empréstimo para a Caixa. O passo a passo abaixo descreve **como solicitar a portabilidade** no aplicativo da Caixa: 
1. Acessar o menu de Portabilidade (Open Finance) no app da Caixa: Abra o aplicativo CAIXA e acesse Menu “Trazer meus dados de outro banco > Open Finance”. Em seguida, selecione a opção “Crédito”, dentro de “Minhas portabilidades”. Dentro desse menu, navegue até “Solicitar Portabilidade”. Essa seção é dedicada à portabilidade de crédito e permitirá iniciar uma nova solicitação. Se o usuário não visualizar nenhum contrato para solicitar portabilidade, isso pode indicar ausência de compartilhamento ativo de dados e o passo 2 deverá ser realizado.
2. Iniciar o compartilhamento dos dados do contrato original: No menu “Trazer meus dados de outro banco > Open Finance”, o usuário deve, em seguida, obter os dados do contrato que se deseja portar. Para isso, clique em “Trazer meus dados”. O aplicativo irá guiar o usuário pelo fluxo de consentimento Open Finance, no qual será preciso selecionar a instituição financeira de origem (onde está o empréstimo atual) e autorizar o compartilhamento das informações desse contrato com a Caixa. Caso o usuário já tenha um consentimento ativo e dados atualizados referentes ao contrato, a etapa de compartilhamento pode ser pulada. Após isso, antes de seguir para a próxima etapa, é necessário que seja aguardado até 1 dia útil para avaliação dos contratos e análise da oferta de portabilidade pela proponente.
3. Solicitar a portabilidade do contrato: Após a conclusão do compartilhamento de dados, o sistema da Caixa poderá apresentar as informações dos contratos de crédito pessoal do usuário obtidos junto à instituição original. Em seguida, ainda dentro do Menu “Trazer meus dados de outro banco > Open Finance > Crédito”, selecione a funcionalidade “Solicitar Portabilidade”. Após isso, o usuário iniciará a solicitação de portabilidade junto à Caixa para o contrato selecionado. Caso a opção de “Solicitar Portabilidade” ou o contrato não apareça, é recomendado que seja aguardado até 1 dia útil para avaliação dos contratos e análise da oferta de portabilidade pela proponente.
4. Selecionar e confirmar o contrato a ser portado: Caso haja mais de um contrato de crédito listado (por exemplo, se o usuário tiver empréstimos em mais de uma instituição ou mais de um contrato na mesma instituição), será necessário selecionar o contrato específico que se deseja portar para a Caixa. Marque o contrato correto e confirme a solicitação de portabilidade. Depois da confirmação, o fluxo de portabilidade de crédito seguirá normalmente via Open Finance.
Uma vez solicitada, a portabilidade de crédito pessoal clean pode levar **até 7 dias úteis para ser concluída**totalmente. Durante esse período, a portabilidade ficará em andamento e o usuário poderá acompanhar atualizações de status pelo próprio aplicativo da Caixa, na seção de "Minhas solicitações enviadas”, ou por notificações da própria instituição. Após a conclusão, o contrato original será encerrado na instituição de origem e o novo contrato passará a vigorar na Caixa, já com as condições acordadas no momento da solicitação. 
## Contratação de fornecedor para realização de testes de engajamento bilateral
As instituições que optarem pela contratação de um fornecedor para a execução dos testes bilaterais poderão utilizar o mesmo mesmo fornecedor da Associação Open Finance, responsável pela execução dos demais testes do Piloto. **A contratação do fornecedor refere-se especificamente à realização de solicitação de uma portabilidade de crédito**com uma Proponente de C**r**édito, em instituições nas quais seja possível a contratação de crédito pelo fornecedor, e**não garante a efetivação  da portabilidade**, que depende da apresentação de proposta pela Proponente e da identificação da liquidação pela PCM.**A contratação do fornecedor possui um custo de R$ 1.120,58 por teste realizado**, que será repassado à instituição por meio da cobrança de custeio emitida pela Associação Open Finance. O valor a ser cobrado dependerá do resultado obtido na execução do teste, conforme as condições abaixo:
- Impossibilidade de abertura de conta ou contratação do produto:  o chamado será encerrado  com essa justificativa e a instituição não será cobrada;
- Falha na etapa de compartilhamento de dados: será cobrado 50% do va l or do teste (R$ 560,29) e a instituição poderá solicitar uma nova execução através do mesmo ticket; Em caso de sucesso na nova execução, será cobrado o valor integral do teste; Em caso de falha na nova execução, será mantida a cobrança de 50% do valor do teste e o ticket será encerrado.
- Sucesso no compartilhamento do dado:  será cobrado o valor integral independente do recebimento de proposta da Proponente de Crédito.
A solicitação do. teste ao fornecedor pode ser feita mediante a abertura de um ticket no service desk no caminho: Processo de Onboarding > Solicitação de Testes > Portabilidade de Crédito. Cada ticket corresponde a uma portabilidade única.Reforçamos que a responsabilidade pelo atingimento do critério de engajamento bilateral é exclusiva de cada instituição e que a contratação o fornecedor é opcional, não garantindo o atingimento do critério.
## Considerações adicionais

- Consulta das portabilidades pelas proponentes devem ser realizadas (GET) em todos os dias úteis, de 2h em 2h, das 8h às 18h, conforme documentação técnica;
- Integração com PCM é necessária para a devida identificação e contabilização dos critérios do Piloto;
- Por se tratar do uso de valores e produtos reais em ambiente produtivo, é recomendada a contratação de produtos com baixos valores

## Acompanhamento com as instituições
Para melhor apoiar as instituições participantes do Piloto de Portabilidade de Crédito, a equipe de Sucesso do Participante da Associação acompanhará e apoiará as instituições durante todo o período do Piloto através de: 
- Agendas semanais : Toda sexta-feira, das 14h às 15h, de 31/10/25 a 27/02/26    Para compartilhamento de informações relevantes, e esclarecimento de dúvidas com com a Associação ou bilaterais com demais instituições Clique aqui para entrar na agenda semanal de acompanhamento
- Grupo do Whatsapp : Para dúvidas pontuais e interações com outras instituições ou Associação  Clique aqui para acessar o Grupo do Whatsapp  do Piloto de Portabilidade de Crédito, ou escaneie o QR Abaixo com a câmera de seu celular:

## Outros links úteis

- Descrição dos testes da FVP Manual: Link aqui

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Changelog

---
id: 1477279768
title: v.19.00.01 Changelog
version: 1
modified: 2026-01-23T17:45:51.418Z
url: /spaces/OF/pages/1477279768/v.19.00.01+Changelog
---

# Sobre o Changelog
Desde a v.16.00.00, o formato de entrega do Guia de Experiência Open Finance é on-line. Com isso, a equipe de UX da DTO vem tentando aprimorar a qualidade da leitura e explorar ao máximo os recursos desse formato para entregar uma experiência de consulta melhor aos usuários do Guia.
- O Changelog foi reorganizado por tópicos para que os interessados encontrem rapidamente o produto ou serviço desejado.
- A funcionalidade dropdown foi incorporada para que os usuários não precisem rolar a página com textos e tabelas extensos e assuntos misturados. O detalhamento das alterações, fundamentais para a rastreabilidade, foram mantidos sem comprometer a leitura.
- Em cada tópico, há um pequeno resumo com a visão geral das mudanças no produto ou serviço.
- Com a migração do formato PDF para a versão on-line, a paginação deixa de ser um recurso viável para indicar onde cada conteúdo se encontra. No novo formato em wiki, estruturado como uma árvore de conhecimento, a organização passa a se apoiar em princípios de UX já consolidados: hierarquia da informação e contextualização por meio da estrutura. Nesse modelo, o Changelog reflete a própria organização do Guia. Primeiro aparece o capítulo; em seguida, o subcapítulo e a etapa (quando existir). Depois, são apresentados os Requisitos ou Recomendações, mantendo o mesmo padrão visual; por fim, os cenários, que seguem a mesma lógica aplicada nos capítulos. Para complementar essa estrutura, cada item recebe uma indicação clara de localização, como: Versão → Capítulo X → Subcapítulo Y → Requisito → Cenário.

# Gestão Open Finance

- Revisão textual do subcapítulo Gestão do Consentimento , sem alteração de requisitos e recomendações.
- Atualização para padronização de telas do subcapítulo Gestão do Consentimento , sem alteração dos elementos.

# Compartilhamento de Dados

- Revisão textual dos subcapítulos Jornada Básica de Compartilhamento e Jornada de Compartilhamento via Hybrid Flow com Hand-off , sem alteração de requisitos e recomendações.
- Atualização para padronização de telas dos subcapítulos Jornada Básica de Compartilhamento e Jornada de Compartilhamento via Hybrid Flow com Hand-off , sem alteração dos elementos.

# Iniciação de Pagamentos

- Correção do texto, fluxo e do protótipo na página Pix Automático - Jornada de Iniciação de Pagamento .

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 PDF da versão

---
id: 1477287157
title: v.19.00.01 PDF da versão
version: 1
modified: 2026-01-23T17:47:44.682Z
url: /spaces/OF/pages/1477287157/v.19.00.01+PDF+da+vers+o
---

Acesse a [v.19.00.01 do Guia de Experiência do Usuário Open Finance Brasil em PDF](https://openfinancebrasil.sharepoint.com/:b:/s/OPENBANKINGDocumentaoParticipantes/IQB8FdydFC65RY-oLUSIjXe1AajsXsyhkLcO-jeUJm-Atho?e=CNcWoL).

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Pesquisa- Avalie a sua experiência com o Guia de UX

---
id: 1477287144
title: v.19.00.01 Pesquisa: Avalie a sua experiência com o Guia de UX
version: 1
modified: 2026-01-23T17:47:44.380Z
url: /spaces/OF/pages/1477287144/v.19.00.01+Pesquisa+Avalie+a+sua+experi+ncia+com+o+Guia+de+UX
---

[https://forms.office.com/r/Ud8MhDy6jf](https://forms.office.com/r/Ud8MhDy6jf)

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Changelog (UX)

---
id: 1436287613
title: v.19.00.00 Changelog (UX)
version: 1
modified: 2026-01-12T19:25:06.185Z
url: /spaces/OF/pages/1436287613/v.19.00.00+Changelog+UX
---

# Sobre o Changelog
Desde a v.16.00.00, o formato de entrega do Guia de Experiência Open Finance é on-line. Com isso, a equipe de UX da DTO vem tentando aprimorar a qualidade da leitura e explorar ao máximo os recursos desse formato para entregar uma experiência de consulta melhor aos usuários do Guia.
- O Changelog foi reorganizado por tópicos para que os interessados encontrem rapidamente o produto ou serviço desejado.
- A funcionalidade dropdown foi incorporada para que os usuários não precisem rolar a página com textos e tabelas extensos e assuntos misturados. O detalhamento das alterações, fundamentais para a rastreabilidade, foram mantidos sem comprometer a leitura.
- Em cada tópico, há um pequeno resumo com a visão geral das mudanças no produto ou serviço.
- Com a migração do formato PDF para a versão on-line, a paginação deixa de ser um recurso viável para indicar onde cada conteúdo se encontra. No novo formato em wiki, estruturado como uma árvore de conhecimento, a organização passa a se apoiar em princípios de UX já consolidados: hierarquia da informação e contextualização por meio da estrutura. Nesse modelo, o Changelog reflete a própria organização do Guia. Primeiro aparece o capítulo; em seguida, o subcapítulo e a etapa (quando existir). Depois, são apresentados os Requisitos ou Recomendações, mantendo o mesmo padrão visual; por fim, os cenários, que seguem a mesma lógica aplicada nos capítulos. Para complementar essa estrutura, cada item recebe uma indicação clara de localização, como: Versão → Capítulo X → Subcapítulo Y → Requisito → Cenário.

# Gestão Open Finance

- Inclusão de requisito na Gestão de Vínculos de Conta para JSR
Detalhamento das alterações em JSR760
## Gestão de Vínculos de Conta para JSR
#F4F5F7
### Requisitos - ID
**Cenário: Alteração dos Vínculos de Conta**
| Tipo | De (v. 18.00.00) N/A | Para (v. 19.00.00) Localização v.19 → Gestão Open Finance→ Gestão de Pagamentos→ Gestão de Vínculos de Conta para JSR→ Requisitos - ID → Alteração dos Vínculos de Conta |
| --- | --- | --- |
| Inclusão | N/A | b. Caso o usuário tenha o compartilhamento de saldo e limite ativo, informar que a data de validade desse consentimento será automaticamente atualizada conforme a nova data de validade do vínculo de conta.​ |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 PDF da versão

---
id: 1436294732
title: v.19.00.00 PDF da versão
version: 2
modified: 2026-01-12T19:59:42.078Z
url: /spaces/OF/pages/1436294732/v.19.00.00+PDF+da+vers+o
---

Acesse a [v.19.00.00 do Guia de Experiência do Usuário Open Finance Brasil em PDF](https://openfinancebrasil.sharepoint.com/:b:/s/OPENBANKINGDocumentaoParticipantes/IQAGvnoTgMAHQIAx3xskhBGwASVvwP2EWYc0s9QPLQY4SFc?e=luGeT9).

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Pesquisa- Avalie a sua experiência com o Guia de UX

---
id: 1436294719
title: v.19.00.00 Pesquisa: Avalie a sua experiência com o Guia de UX
version: 1
modified: 2026-01-12T19:27:06.587Z
url: /spaces/OF/pages/1436294719/v.19.00.00+Pesquisa+Avalie+a+sua+experi+ncia+com+o+Guia+de+UX
---

[https://forms.office.com/r/Ud8MhDy6jf](https://forms.office.com/r/Ud8MhDy6jf)

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Anexos (UX) > v.19.00.00 Jornada do Usuário e Consentimento na Versão Whitelabel de Pagamentos

---
id: 1436294671
title: v.19.00.00 Jornada do Usuário e Consentimento na Versão Whitelabel de Pagamentos
version: 1
modified: 2026-01-12T19:27:05.662Z
url: /spaces/OF/pages/1436294671/v.19.00.00+Jornada+do+Usu+rio+e+Consentimento+na+Vers+o+Whitelabel+de+Pagamentos
---

Na versão whitelabel, os requisitos da Jornada do Usuário definidos neste Guia de Experiência devem ser observados pelo parceiro do ITP. As informações apresentadas ao usuário devem indicar, de forma transparente, para quem o consentimento está sendo dado.Jornada de Iniciação de Pagamentos WhitelabelJornada de Iniciação de Pagamentos WhitelabelJornada de Iniciação de Pagamentos Whitelabel

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Anexos (UX) > v.19.00.00 Modalidades de Crédito

---
id: 1436294660
title: v.19.00.00 Modalidades de Crédito
version: 1
modified: 2026-01-12T19:27:05.483Z
url: /spaces/OF/pages/1436294660/v.19.00.00+Modalidades+de+Cr+dito
---

# Modalidades de operações de crédito apresentadas na Circular 4.015

## Jornada de Consentimento de Dados

| DOC 3040 | | REFERÊNCIA A ORIGEM DO CRÉDITO - CIRCULAR 4015 |
| DOMÍNIO | DESCRIÇÃO | SUB | DESCRIÇÃO (SUB) | SUGESTÃO DE SUBMODALIDADE |
| 01 | Adiantamentos e Empréstimos | 01 | Adiantamentos a depositantes | Adiantamentos a depositantes |
| 02 | Empréstimos | 02 | Crédito pessoal - com consignação em folha de pagamento. | Crédito pessoal - com consignação |
| | | 13 | Crédito pessoal - sem consignação em folha de pagamento. | Crédito pessoal - sem consignação |
| | | 11 | Home equity | Home equity |
| | | 12 | Microcrédito produtivo orientado | Microcrédito produtivo orientado |
| | | 13 | Cheque especial | Cheque especial |
| | | 14 | Conta garantida | Conta garantida |
| | | 15 | Capital de giro com prazo de vencimento de até 365 dias | Capital de giro |
| | | 16 | Capital de giro com prazo de vencimento superior a 365 dias | |
| | | 17 | Capital de giro com teto rotativo | |
| 03 | Direitos creditórios descontados | 01 | Desconto de duplicatas | Desconto de duplicatas |
| | | 02 | Desconto de cheques | Desconto de cheques |
| | | 03 | Antecipação de faturas de cartão de crédito | Antecipação de recebíveis de cartão de crédito |
| | | 98 | Outros direitos creditórios descontados | Desconto de nota promissória |
| | | 99 | Outros títulos descontados | Desconto de nota promissória |
| 04 | Financiamentos | 01 | Aquisição de bens - veículos automotores | Aquisições de bens móveis |
| | | 02 | Aquisição de bens - outros bens | |
| | | 03 | Microcréditos | Microcrédito produtivo orientado |
| 08 | Financiamentos | 01 | Custeiro | Rurais |
| | | 02 | Investimento | |
| | | 03 | Comercialização | Microcrédito produtivo orientado |
| | | 04 | Industrialização | Microcrédito produtivo orientado |
| 09 | | 01 | Financiamento habitacional - SFH | Sistema Financeiro da Habilitação (SFH) |
| | | 02 | Financiamento habitacional - exceto SFH | Sistema Financeiro Imobiliário (SFI) |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Anexos (UX) > v.19.00.00 Proto-personas e casos de uso

---
id: 1436294590
title: v.19.00.00 Proto-personas e casos de uso
version: 1
modified: 2026-01-12T19:27:04.377Z
url: /spaces/OF/pages/1436294590/v.19.00.00+Proto-personas+e+casos+de+uso
---

Esta página apresenta a abordagem adotada para a validação da Jornada de Compartilhamento de Dados, utilizando proto-personas e casos de uso como elementos para a análise. Ela tem como objetivo apoiar a visualização de diferentes perfis e cenários, além de auxiliar a validação das decisões relacionadas ao desenho da jornada.
# Etapas para Validação da Jornada

- Etapa 1: Definir a proto-persona
- Etapa 2 : Definir o caso de uso
- Etapa 3 : Validar a jornada
Etapas para a validação da jornada
# As proto-personas da Jornada de Compartilhamento de Dados
As proto-personas apresentadas neste guia foram elaboradas pelo GT-UX e refletem hipóteses construídas a partir da experiência dos participantes. Elas não esgotam todos os perfis possíveis e podem ser ajustadas pelas instituições conforme seus próprios contextos e necessidades.Para apoiar a análise da Jornada de Compartilhamento de Dados, essas proto-personas devem ser utilizadas em conjunto com os casos de uso, permitindo explorar possíveis situações, decisões e necessidades ao longo da jornada.#F4F5F7**Proto-persona**: recurso utilizado para explicitar e organizar hipóteses sobre os perfis envolvidos na jornada, a partir do conhecimento prévio e das experiências acumuladas de equipes técnicas e de produtos, sem coleta de dados primários. Seu uso permite alinhar entendimentos iniciais sobre comportamentos, necessidades e objetivos dos usuários.As proto-personas definidas são:
- Maria , usuária PF: múltiplos acessos
- Mônica , usuária PF: múltiplos acessos
- Eduardo , usuário PF: poucos acessos
- João , usuário PF: poucos acessos
**Nota:** As referências a poucos acessos e múltiplos acessos indicam a frequência de uso de canais digitais pelas proto-personas no contexto da jornada.Proto-personas da Jornada de Compartilhamento de Dados
# Os Casos de Uso
A Jornada de Compartilhamento de Dados pode ocorrer em diferentes cenários que conduzem ao objetivo comum de utilizar a plataforma de Open Finance para o compartilhamento de dados. Esses cenários são denominados casos de uso.Em conjunto com as proto-personas, os casos de uso fornecem contexto e apoiam a compreensão das situações mais prováveis que levam o usuário a percorrer a jornada. Assim como as proto-personas, esses casos de uso não esgotam todas as possibilidades.Os casos de uso definidos são:
- Agregação de informações financeiras Intenção do usuário de agregar contas mantidas em diferentes instituições, incluindo a instituição principal.
- Contratação de produtos com relacionamentos iguais e esquecimento de senha na Instituição Transmissora Intenção do usuário de compartilhar informações de produtos do mesmo tipo (por exemplo, duas contas correntes) após esquecer a senha do canal eletrônico da Instituição Transmissora.
- Abertura de conta com dados cadastrais (básico) Intenção do usuário de compartilhar dados cadastrais para abertura de conta.
- Contratação de produtos com relacionamentos diferentes Intenção do usuário de compartilhar informações de produtos distintos (por exemplo, conta corrente e cartão de crédito).
- Cancelamento da jornada na etapa de consentimento Intenção do usuário de interromper a jornada na etapa de consentimento e cancelar o compartilhamento de dados.

# Combinação entre proto-personas e casos de uso

| Proto-persona | Maria Usuária PF Múltiplos acessos | Mônica Usuária PJ Múltiplos acessos | Eduardo Usuário PJ Poucos acessos | João Usuário PF Poucos acessos |
| --- | --- | --- | --- | --- |
| Casos de uso | Agregação de informação financeira (várias contas em Instituições diferentes e uma na sua instituição principal). | Abertura de conta com dados cadastrais (básico). | Contratação de produtos com relacionamentos iguais (como duas contas correntes) e esquecimento de senha no canal eletrônico da Transmissora. | Contratação de produtos com relacionamentos diferentes (conta corrente x cartão de crédito) nas instituições. |
| Características | 32 anos, graduada, administradora, e está iniciando uma família. | 43 anos, pós-graduada e diretora financeira de uma empresa de médio porte. | 26 anos, autônomo com ensino técnico, atua no limite da MEI e complementa a renda dos pais. | 63 anos, aposentado, casado e tem 2 filhos adultos. |
| Necessidades | Está em processo de maturidade de sua vida financeira, busca melhores oportunidades digitais no mercado e utilizaria o Open Finance para aprimorar produtos e serviços. | Está buscando alternativas eficientes para a saúde financeira do negócio e sua expansão. Utilizaria o Open Finance para acessar melhores opções de produtos e otimizar a gestão financeira. | Tem a expectativa de se resolver nos canais digitais, porém, necessita de auxílio para resolver os assuntos financeiros de seu negócio. Utilizaria o Open Finance para ter melhores condições de alavancar seu negócio. | Tem poucos recursos financeiros. Procura uma solução para um eventual imprevisto ou um objetivo sem planejamento. Utilizaria o Open Finance para ter uma visão completa da sua saúde financeira. |
| Comportamento | Busca sempre se atualizar quanto a novos acontecimentos. É independente e organizada. Utiliza os serviços providos pela sua instituição para seu planejamento. | Os serviços financeiros da sua instituição são essenciais para a operação do negócio. Utiliza frequentemente todos os canais disponíveis e demanda atendimento consultivo. | Iniciou sua relação financeira com uma instituição por necessidade profissional. Conhece e utiliza os serviços digitais, porém tem baixas expectativas quanto à sua experiência. | Utiliza as instituições financeiras por necessidade, prioritariamente por canais presenciais. Depende de seu gerente ou de familiares para realizar suas operações financeiras. |
| Desafio | Unificar os pagamentos e transferências em uma única instituição ao utilizar os saldos das suas contas de outras instituições. | Otimizar os processos de pagamento dentro da sua empresa por meio desse serviço. | Realizar compras de produtos para sua empresa em canais digitais, utilizando diretamente o saldo de sua conta. | Realizar sua primeira compra em um canal digital utilizando diretamente do saldo de sua conta. |

## Maria
**“Se você quer algo bem feito, faça você mesmo.”**
- Usuária PF
- Múltiplos acessos
- Idade : 32 anos
- Profissão : administradora
- Escolaridade : superior completo
- Renda : R$7.000,00/mês
- Estado civil : casada
- Dependentes diretos : filho pequeno
- Níveis de acesso : não tem dependentes na relação financeira com a instituição.
- Relação com instituições : uso distribuído entre várias instituições financeiras.

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| Maria |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Alta | Média | Médio |
| Encara as soluções de serviços financeiros como uma ferramenta de planejamento e um meio para identificar novas oportunidades (perfil investidora). | Utiliza soluções financeiras frequentemente em mais de um canal, prioritariamente no canal digital (mobile banking e internet banking). | Se mantém antenada quanto a novos acontecimentos. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de Maria
### Outras informações

- Momento de vida : em processo de maturidade da vida financeira.
- Expectativa com a Instituição (por quê?): busca boas oportunidades de mercado com atendimento rápido, fácil e digital.
- Relacionamento com sua instituição (como?): contratação de um novo produto em uma nova instituição (operações de crédito, contas etc.).
- Principais motivos de adoção do Open Finance : complementar sua relação financeira com as instituições para aprimorar seus produtos e serviços.
- Principais motivos para usar a Iniciação de Transação de Pagamento : unificar os pagamentos e transferências em uma única instituição ao utilizar os saldos das suas contas de outras instituições.
- Inseguranças : uso indevido de dados, vazamento de dados e fraudes.

## Mônica
**“Sozinha você vai mais rápido, junto você vai mais longe.”**
- Usuária PJ
- Múltiplos acessos
- Idade : 43 anos
- Profissão : Diretora Financeira
- Escolaridade : Pós graduação completa
- Renda: R$ 12.000.000,00/ano
- Estado civil : N/A
- Dependentes diretos : N/A
- Níveis de acesso : não tem acesso para sócios, administradores e operadores
- Relação com instituições : distribuída entre várias instituições financeiras.

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| Mônica |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Alta | Alta | Alto |
| Os serviços financeiros de sua instituição são essenciais para a operação do negócio (perfil misto). | Utiliza praticamente todos os canais disponíveis frequentemente, com preferência por canais digitais quando mais conveniente (internet banking). | Irá demandar um atendimento consultivo de sua instituição. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de Mônica
### Outras informações

- Momento de vida : está buscando alternativas eficientes para a saúde financeira do negócio.
- Expectativa com a Instituição (por quê?): sustentabilidade do negócio.
- Relacionamento com sua instituição (como?): expansão do negócio por meio de produtos de linhas de crédito ou investimentos.
- Principais motivos de adoção do Open Finance : ter uma visão mais global do setor financeiro para buscar melhores opções de produtos e otimização da gestão financeira da empresa.
- Principais motivos para usar a Iniciação de Transação de Pagamento : otimizar os processos de pagamento dentro da sua empresa por meio desse serviço.
- Inseguranças : não saber o que está sendo compartilhado, não saber como os dados estão sendo utilizados, desrespeito aos níveis/perfis de acesso da empresa, vazamento de credenciais e sua utilização nesse ambiente e vazamento de informações financeiras da empresa.

## Eduardo
**“Deus ajuda quem cedo madruga”**
- Usuário PJ
- Poucos acessos
- Idade : 26 anos
- Profissão : mecânico autônomo
- Escolaridade : ensino técnico
- Renda : R$ 80.000,00/ano
- Estado civil : N/A
- Dependentes diretos : complementa a renda dos pais
- Níveis de acesso : não tem dependentes na relação financeira.
- Relação com instituições : concentrado em uma única instituição financeira.

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| Eduardo |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Média | Média | Médio |
| Iniciou sua relação financeira com uma Instituição por necessidade profissional (emissão de nota MEI), perfil tomador. | Tem experiência em serviços digitais diversos e não tem expectativa quanto à sua experiência digital com uma instituição financeira. | Adquiriu seu conhecimento financeiro com base em sua vivência, relação com mídias sociais e familiares. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de Eduardo
### Outras informações

- Momento de vida : recentemente demitido e começou a empreender.
- Expectativa com a Instituição (por quê?): necessita de auxílio para resolver os assuntos financeiros de seu negócio.
- Relacionamento com sua instituição (como?): conta corrente para conduzir seu pequeno negócio.
- Principais motivos de adoção do Open Finance : compartilhar suas informações financeiras para que tenha melhores condições de alavancar seu negócio:  “O que eu ganho com isso?”.
- Principais motivos para usar a Iniciação de Transação de Pagamento : realizar compras de produtos para sua empresa em canais digitais utilizando diretamente do saldo de sua conta.
- Inseguranças : qual o custo, não saber como os dados estão sendo utilizados e “Meu dinheiro vai ser transferido?”

## João
**“Melhor um pássaro na mão do que dois voando.”**
- Usuário PF
- Poucos acessos
- Idade : 63 anos
- Profissão : aposentado
- Escolaridade : ensino médio completo
- Renda : R$ 1.045,00/mês
- Estado civil : casado
- Dependentes diretos : dois filhos adultos
- Níveis de acesso : não tem conta conjunta com o cônjuge.
- Relação com instituições : concentrado em uma única instituição financeira

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| João |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Baixa | Baixa | Baixo |
| Utiliza as instituições financeiras apenas por necessidade (recebimento de aposentadoria, etc.) perfil tomador. | Utiliza pouco os serviços de canais digitais, prioritariamente prefere atendimento presencial (relação com o gerente, caixa físico, etc.). | Depende de recomendações do gerente ou familiares para realizar suas operações financeiras. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de João
### Outras informações

- Momento de vida : atualmente tem poucos recursos financeiros para pequenos projetos/desafios pessoais.
- Expectativa com a Instituição (por quê?): procura uma solução para eventual imprevisto financeiro ou um objetivo sem planejamento, buscando informações com familiares e a solução com sua instituição financeira.
- Relacionamento com sua instituição (como?): renegociação de um crédito, ou contratação de um crédito consignado.
- Principais motivos de adoção do Open Finance : ter uma visão completa de sua saúde financeira, possibilitando melhores condições de adoção ao Open Finance negociação de produtos e serviços.
- Principais motivos para usar a Iniciação de Transação de Pagamento : realizar sua primeira compra em um canal digital utilizando diretamente o saldo de sua conta.
- Inseguranças : tem receio de inserir senhas em canais digitais e golpes.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Anexos (UX) > v.19.00.00 Tabela de Dados

---
id: 1436294649
title: v.19.00.00 Tabela de Dados
version: 1
modified: 2026-01-12T19:27:05.288Z
url: /spaces/OF/pages/1436294649/v.19.00.00+Tabela+de+Dados
---

Tabela de dados em sua versão resumida, para facilitar acesso aos times técnicos.
# Jornada de Compartilhamento de Dados

## Dados cadastrais

### Agrupamentos PF

| Dados cadastrais | Nome completo e nome social, endereço completo, CPF, passaporte, telefone, e-mail, documento de identificação, filiação, data de nascimento, estado civil, sexo, nacionalidade, residência brasileira, documento estrangeiro. |
| Informações complementares | Renda, profissão, patrimônio, informações de cônjuge, produtos contratados, representantes, informações do empregador de conta salário e portabilidade. |

### Agrupamentos PJ

| Dados cadastrais | Razão social, endereço completo, CNPJ, número de registro no país de origem, telefone, e-mail, data de abertura da empresa, informações de sócios e administradores. |
| Informações complementares | Faturamento, valor patrimonial, ramo de atuação, data de início de relacionamento, produtos contratados, representantes. |

## Dados da conta

| Saldo | Informações da conta, saldo disponível, saldo bloqueado, outros saldos. |
| Limites | Informações da conta, limite utilizado, limite contratado de cheque especial. |
| Extratos | Informações da conta, detalhes da transação. |

## Dados do Cartão de Crédito

| Limite | Informações do cartão, informações sobre o limite do cartão, limite total, limite utilizado, limite disponível, limite por tipo de crédito. |
| Transações | Informações do cartão, identificação de transação, valor da transação, datas, identificação do estabelecimento. |
| Faturas | Informações do cartão, bandeira do cartão, informações da fatura, encargos e formas de pagamento. |

## Dados de Operação de Crédito

| Contratos de Crédito | Dados do contrato, data da contratação, data do recebimento do crédito, valor do crédito, data de vencimento, datas de pagamento das parcelas, período recorrente dos pagamentos, datas de vencimento de cada parcela, data de vencimento da primeira parcela, saldo devedor, prazo total, prazo remanescente, quantidade de prestações, prestações, taxas de juros, Custo Efetivo Total, sistema de amortização, tarifas, sigla identificadora da tarifa, valor da tarifa, moeda, data da cobrança de tarifa, encargos, garantias, número do documento da Instituição consignante. |

## Investimentos

| Operações de Investimentos | “As operações referem-se a contratos de renda fixa, renda variável, tesouro direto e fundos de investimentos. São informações como: identificação do produto, informações de remuneração, data de emissão, vencimento, aquisição, data fim da carência, saldo bloqueado, líquido e bruto, quantidade de títulos, preço unitário, impostos provisionados, multa e mora, indexadores, código ISIN, Classificação ANBIMA, Classe e Subclasse.” |

### Fundos de Investimento

| Identificação do Produto | Informações de identificação do produto, Código ISIN, Classificação ANBIMA, Classe e Subclasse. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade de cotas , valor bruto da cota, impostos provisionados. |
| Movimentações | Identificação da movimentação, data da conversão, quantidade de cotas movimentada, valor da cota, valor da movimentação, valor líquido e bruto da movimentação e impostos. |

### Renda Fixa Bancária

| Identificação do Produto | Informações de identificação do produto, informações de remuneração do produto, data de vencimento, aquisição, data fim carência. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade título, preço unitário, impostos provisionados. |
| Movimentações | Identificação da movimentação, Preços unitário e quantidade movimentados, valores liquido e bruto da movimentação, impostos e indexadores. |

### Renda Fixa Crédito Privado

| Identificação do Produto | Informações de identificação do produto, informações de remuneração do produto, data de vencimento, aquisição, data fim carência, pagamento de cupom. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade título, preço unitário, impostos provisionados, multa e mora. |
| Movimentações | Identificação da movimentação, preços unitários e quantidade movimentados, valores liquido e bruto da movimentação, impostos e indexadores. |
| Contratos de Crédito | Dados do contrato, data da contratação, data do recebimento do crédito, valor do crédito, data de vencimento, datas de pagamento das parcelas, período recorrente dos pagamentos, datas de vencimento de cada parcela, data de vencimento da primeira parcela, saldo devedor, prazo total, prazo remanescente, quantidade de prestações, prestações, taxas de juros, Custo Efetivo Total, sistema de amortização, tarifas, sigla identificadora da tarifa, valor da tarifa, moeda, data da cobrança de tarifa, encargos, garantias, número do documento da Instituição consignante. |

### Renda Variável

| Identificação do Produto | Informações de identificação do produto (código ISIN e ticker). |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade, preço unitário, impostos provisionados, multa e mora. |
| Movimentações | Identificação da movimentação, Preços unitário e quantidade movimentada, valor da movimentação, data da movimentação. |
| Detalhes da Nota de Negociação | Número da nota, valor monetário das taxas aplicáveis, emolumentos, impostos e valor líquido da nota. |

### Tesouro Direto

| Identificação do Produto | Informações de identificação do produto, informações de remuneração do produto, data de vencimento, aquisição, data fim carência, pagamento de cupom. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade título, preço unitário, impostos provisionados, multa e mora. |
| Movimentações | Identificação da movimentação, preços unitários e quantidade movimentados, valores liquido e bruto da movimentação, impostos e indexadores. |

## Operações de Câmbio

| Operações de Câmbio | Identificação da operação, data do fechamento do contrato de câmbio, data em que a operação (compra ou venda) está prevista para ser liquidada, valor da taxa de câmbio aplicada ao contrato, valor do saldo da operação a liquidar, percentual do valor concedido ao usuário antecipadamente, natureza fato do fechamento da operação e relação de vínculo entre o usuário e o pagador/Recebedor no exterior. |

# Jornada de Iniciação de Pagamentos

| Tipo de pagamento | Informações na Iniciadora* | Informações na Detentora |
| --- | --- | --- |
| Todos Tipos de Pagamento | Forma de pagamento. Valor da tarifa na Iniciadora (se houver). Valor do pagamento:  – Digitável ou para visualização, conforme o caso;  – Se necessário, desdobrar valores de juros e multa. Data do pagamento:  – Adaptável para agendamento e recorrente. Descrição/Observação/Finalidade (preenchimento opcional, sendo vedada a apresentação de campo denominado “Descrição” nas transações Pix iniciadas por QR Code)”data de encerramento e/ou número de recorrências. Periodicidade da recorrência. | Forma de pagamento. Valor da tarifa na Detentora (se houver). Valor do pagamento:  – Se necessário, desdobrar valores de juros e multa. Data do pagamento:  – Adaptável para agendamento e recorrente. Informações da conta do pagador a ser debitada, como os dados da agência e conta. Data de encerramento e/ou número de recorrências. Periodicidade da recorrência. |
| Pix Inserção Manual | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Instituição (apenas o nome). Agência sem dígito. Conta com dígito. Descrição (preenchimento opcional). | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Instituição (apenas o nome). Agência sem dígito. Conta com dígito. |
| Pix Por Chave | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Chave Pix (CPF/CNPJ, e-mail, ou celular). Descrição (preenchimento opcional. | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Chave Pix (CPF/CNPJ, e-mail, ou celular). |
| Pix Direto pelo Iniciador | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. | Nome do recebedor. CPF do recebedor mascarado ou CNP. |
| Pix QR Code e Copia e Cola | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. QR Code (captura / copia e cola). Dados necessários conforme tipo de QR Code:  – De acordo com os requisitos mínimos especificados nos documentos que regulamentam o arranjo Pix. Mensagem Pix. | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. |
***Informações na Iniciadora**: dados mínimos (obrigatórios) que devem ser apresentados ao usuário. Outros dados que possam ajudar na experiência, seguindo as diretrizes, podem ser apresentados.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Compartilhamento de Dados (UX) > v.19.00.00 Casos de erro (Dados)

---
id: 1436290076
title: v.19.00.00 Casos de erro (Dados)
version: 1
modified: 2026-01-12T19:25:47.740Z
url: /spaces/OF/pages/1436290076/v.19.00.00+Casos+de+erro+Dados
---

## A mensagem de erro deve:
**Comunicar** o erro**com clareza**, **explicar** o que ocasionou o erro com **linguagem simples** e **fornecer orientação** e **opções de ação** para que o usuário consiga continuar.Boas práticas de experiência considerando os pilares:
- O que houve com o usuário?
- O que ocasionou o erro?
- Orientações ao usuário.
- Ação necessária para prosseguir.
**Exemplo:**
Um navegador de internet não foi localizado para redirecionar e autenticar o usuário na Transmissora.
- O que houve? Usuário não pôde ser redirecionado.
- O que ocasionou o erro? O navegador de internet não foi encontrado no dispositivo do usuário.
- Orientação ao usuário Verificar se existe um navegador instalado.
- Ações para prosseguir Tentar novamente.
- Mensagem de erro Desculpe, não foi possível direcioná-lo. Não encontramos um navegador de internet em seu celular. Verifique se seu dispositivo tem o navegador, pois precisamos dele para concluir seu compartilhamento.

| Erro | Etapa | Orientação para o usuário | Ação para prosseguir | Observações |
| --- | --- | --- | --- | --- |
| Não encontra um destino Aplicativo ou navegador - dependendo do caminho escolhido pela Transmissora | Direcionamento IT > IR | Avisar que o navegador / aplicativo não está instalado e recomendar a instalação. | Preferencialmente, direcionar para instalação do aplicativo. Caso não seja possível, recomendar instalação do app ou navegador e indicar nova tentativa. | Antes de exibir qualquer erro para o usuário, todos os caminhos possíveis devem ser tentados. Por exemplo: Se o usuário não tem o aplicativo da Transmissora e esta aceita direcionar para o navegador, este caminho deve ser feito antes de mostrar a mensagem de erro. Incluir reforço de que se trata de caso para a jornada de redirecionamento. |
| Time out | Direcionamento IT > IR | Indicar que o fluxo foi interrompido pois o tempo limite para se autenticar foi atingido. | Na Transmissora: cancelar o fluxo e redirecionar para a Receptora.   Na Receptora: informar que não foi possível concluir o compartilhamento. Orientar o usuário a tentar novamente. | |
| O fluxo é interrompido e usuário volta para Receptora devido à indisponibilidade do sistema | Direcionamento IT > IR | Indicar que ocorreu um erro de comunicação com a Instituição Transmissora e sugerir que tente novamente mais tarde. | Recomendar que tente novamente mais tarde. | |
| Transmissora ter parte ou nenhum dos dados obrigatórios ou não selecionados da Receptora | Confirmação e Efetivação | Fica a cargo da Receptora como continuar o fluxo. | Ação detalhada ao lado. | Para a Transmissora Dados parciais: se houver qualquer dado que possa ser compartilhado, a Instituição Transmissora deve permitir que o usuário conclua a confirmação do compartilhamento e seja redirecionado para a Receptora, disponibilizando todos os dados disponíveis. Isto se deve à Instituição Transmissora não saber a finalidade escolhida pelo usuário na Receptora e nem mesmo quais dados são necessários ou opcionais para aquela finalidade. Logo, não deverá orientar o usuário sobre seguir ou não com o compartilhamento dos dados. Nenhum dado: caso o usuário não tenha NENHUM dado solicitado na Receptora, a Instituição Transmissora poderá enviar mensagem ao usuário e orientá-lo a voltar à Receptora ou seguir com a jornada mesmo sem nenhum dado. Para a Receptora Caberá à Receptora analisar quais dados foram retornados e avaliar se informará ao usuário sobre a inexistência total ou parcial dos dados, seguindo ou não com a oferta do produto ou serviço. Deve-se deixar claro que a Transmissora compartilhou todos os dados possíveis, porém o usuário não tinha os dados. |
| Casos em que o usuário não tem poderes suficientes na jornada PJ | Confirmação | Explicar para o usuário que sua alçada não é suficiente para a ação desejada. Informar claramente sobre a necessidade de revisão dos poderes. | Dar clareza sobre qual ação é necessária para o usuário seguir em frente.  Ter indicação do canal em que o usuário possa buscar informações. | Exemplos SEM detalhes do erro Não foi possível realizar o compartilhamento de dados. Erro na solicitação [ERR-103] A conta informada não existe ou não está vinculada à chave J da autenticação. Exemplos COM detalhes do erro Verificamos que você não tem os poderes necessários para compartilhar os dados da sua empresa com outras instituições. Solicite sua permissão: Para que você possa compartilhar os dados da sua empresa com outros participantes do Open Finance, é preciso que você apresente os documentos com os poderes necessários do representantes legais e/ou procuradores. |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Compartilhamento de Dados (UX) > v.19.00.00 Jornada Básica de Compartilhamento de Dados > v.19.00.00 Requisitos e Recomendações - Jornada Básica de Compartilhamento de Dados

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

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Compartilhamento de Dados (UX) > v.19.00.00 Jornada de Hybrid flow com Hand-off (Dados) > Requisitos e Recomendações - Hybrid flow com Hand-off (Dados)

---
id: 1436289945
title: Requisitos e Recomendações - Hybrid flow com Hand-off (Dados)
version: 1
modified: 2026-01-12T19:25:44.683Z
url: /spaces/OF/pages/1436289945/Requisitos+e+Recomenda+es+-+Hybrid+flow+com+Hand-off+Dados
---

A seguir, estão descritos os requisitos e recomendações específicos para o **Hybrid flow com Hand-off**entre as instituições nas etapas de **Direcionamento** e **Redirecionamento** da Jornada de Compartilhamento de Dados.
# Etapa 2: Direcionamento Hybrid flow com Hand-off
DC hybrid flow - etapa 2#F4F5F7
## Requisitos - IR
**Cenário: Tela de transição**
1. Durante o processo de redirecionamento, a Instituição Receptora de Dados deve apresentar uma tela dedicada a esclarecer ao usuário que o redirecionamento está em andamento, contendo, no mínimo, as seguintes informações/elementos: Indicação de que o redirecionamento está em andamento. Indicação de que o redirecionamento é seguro.
Compartilhamento de dados - E2 - Redirecionamento IR> IT desktop #F4F5F7
## Requisitos - IT
**Cenário: Tela de transição**
1. Após receber o usuário da Instituição Receptora de Dados, a Instituição Transmissora de Dados deve apresentar uma tela na qual fornece, de maneira clara e simples, as instruções e ferramentas necessárias para continuidade da Jornada pelo celular.
Compartilhamento de dados - E2 - Redirecionamento IR > IT desktop com hand-off 6 #F4F5F7
## Recomendações - IR e IT
**Cenário: Tela de transição**
1. Utilizar o menor número de interações possível de forma a reduzir a fricção na jornada.
2. Ao redirecionar para o browser da Instituição Transmissora de Dados, pode-se abrir na aba da Receptora, ou seja, substituir a página da Receptora pela nova página da Transmissora, ou manter a aba da Receptora e abrir o browser da Instituição Transmissora em uma nova aba.
3. Essa página criada deve seguir o padrão visual da Instituição Transmissora de Dados, de modo a passar segurança ao usuário que está habituado a usar o aplicativo da instituição.
4. Caso a Instituição Transmissora de Dados tenha mais de um canal disponível (ex: app ou browser), é possível oferecer mais de uma opção de acesso, de acordo com o que ela julgue mais apropriado para a experiência de seu usuário.
Como não são todas as instituições que têm mais de um canal disponível, essa tela é opcional e deve ser implementada apenas quando aberta em ambiente desktop. Além disso, essas opções podem estar em uma tela única de redirecionamento, facilitando a navegação do fluxo.O exemplo abaixo foi desenhado em duas etapas apenas para garantir um melhor entendimento do processo de escolha do canal.Compartilhamento de dados - F3E2 - ITP - Redirecionamento ID > ITP desktop com hand-off 1 #F4F5F7
## Recomendações - IT
**Cenário: Tela de transição**
1. Para que o usuário consiga ser redirecionado do browser da Instituição Transmissora de Dados ao aplicativo da Instituição Transmissora de dados, podem ser utilizadas diversas alternativas, como por exemplo: QR Code dinâmico, código de ativação, entre outros, ficando a cargo da Receptora definir o melhor mecanismo.
No caso de jornadas iniciadas por meio de device mobile, elas podem ser suprimidas pela utilização de DeepLink.A Transmissora de Dados poderá utilizar recursos visuais para mostrar a informação de tempo restante para confirmação do compartilhamento.
1. Devido à possibilidade de ocultar aplicativos em dispositivos com sistema operacional iOS 18 (ou superiores), causando a falha no redirecionamento do usuário, é recomendado que nos fluxos hybrid flow com hand-off, a transmissora de Dados comunique ao usuário que, caso este tenha optado por ocultar algum dos aplicativos financeiros necessários para o compartilhamento de dados, não será possível completar a jornada e é necessário realizar a desocultação antes de realizar o redirecionamento.
**Nota:** A interface é a representação ilustrativa de apenas uma das diversas opções, o QR Code dinâmico. Fica a cargo da Receptora definir o melhor mecanismo de escolha. Compartilhamento de dados - E2 - Redirecionamento IR> IT desktop com hand-off 6
# Etapa 5: Redirecionamento Hybrid flow com Hand-off
DC hybrid flow - etapa 5#F4F5F7
## Requisitos - IT
**Cenário: Tela de transição**
1. Como não há redirecionamento de retorno para o ambiente desktop da Instituição Receptora de Dados nos casos de Hand-Off, após a etapa de confirmação, a Instituição Transmissora de Dados deve, em seu ambiente: Informar que a solicitação foi concluída com sucesso ou apresentar o caso de erro pertinente. Apresentar informações claras de continuidade, orientando o usuário a retornar ao canal da Receptora utilizado para iniciar o processo.
Compartilhamento de dados - F3E2 - MKP - Redirecionamento ID #F4F5F7
## Recomendações - IT
**Cenário: Tela de transição**
1. Apresentar a página de redirecionamento para a página da Instituição Receptora de Dados após identificar a finalização da jornada do usuário no App da Instituição Transmissora de Dados (Confirmação/Cancelamento/Timeout).
Compartilhamento de dados - E2 - Redirecionamento IT > IR desktop

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Compartilhamento de Dados (UX) > v.19.00.00 Jornada de Múltiplos Aprovadores > Requisitos e Recomendações - Múltiplos Aprovadores (Dados)

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

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão Geral

---
id: 1436288271
title: v.19.00.00 Gestão Geral
version: 1
modified: 2026-01-12T19:25:17.412Z
url: /spaces/OF/pages/1436288271/v.19.00.00+Gest+o+Geral
---

Requisitos e recomendações específicos para o ambiente de gestão geral do Open Finance.Através desse ambiente, as instituições participantes que devem disponibilizar uma área de gestão dedicada ao Open Finance devem possibilitar que o usuário acesse informações gerais, termos de uso e os serviços oferecidos. **Nota:**Consulte os subcapítulos Gestão do Consentimento, Gestão de Portabilidade de Crédito e Gestão de Pagamentos para visualizar os requisitos e recomendações específicos para esses ambientes.#F4F5F7
## Requisitos - IT e ID
**Cenário: Sobre a área de gestão do Open Finance**
1. Termos e condições: Quando aplicável, disponibilizar termos e condições de uso somente na área de gestão.
Área de gestão - Termos de uso#F4F5F7
## Recomendações - Instituições participantes
**Cenário: Sobre a área de gestão do Open Finance**
1. Conteúdos institucionais: Na tela inicial da área de gestão do Open Finance, exibir opções como “O que é o Open Finance?” e “Ler Termos de Uso” facilitando o acesso a informações essenciais sobre o funcionamento e os direitos do usuário no Open Finance.
Área de gestão - Conteúdos institucionais - RecomendaçãoRodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Portabilidade de Crédito (UX)

---
id: 1436289418
title: v.19.00.00 Gestão de Portabilidade de Crédito (UX)
version: 1
modified: 2026-01-12T19:25:35.718Z
url: /spaces/OF/pages/1436289418/v.19.00.00+Gest+o+de+Portabilidade+de+Cr+dito+UX
---

As instituições participantes da jornada de Portabilidade de Crédito — Instituição Proponente (IP) e Instituição Credora (IC) — devem disponibilizar ao usuário, por meio de uma Área de Gestão, a listagem de todos os pedidos realizados, com o tipo de produto, seus respectivos status e informações detalhadas, respeitando o contexto da jornada (síncrona ou assíncrona) e os prazos de exibição definidos para cada situação. As instituições também devem permitir que o usuário cancele uma portabilidade que esteja em andamento a qualquer momento antes da fase de liquidação e devem comunicar o cancelamento à outra instituição.#F4F5F7
## Requisitos - IP e IC
**Cenário: Consulta aos pedidos**
1. Exibição de pedidos de Portabilidade de Crédito : Exibir a lista de pedidos de Portabilidade de Crédito com seus respectivos status individuais. Ex.: Em análise, Portabilidade em andamento, etc. Identificação do tipo de contrato : Indicar o tipo de contrato associado a cada pedido. Ex. Consignado Federal ou CPC.
2. Exibição de dados de proposta e contraproposta : Exibir os dados da proposta e contraproposta conforme descrito no cenário de Apresentação da Proposta .

### Área de Gestão da Instituição Proponente (IP)
Portabilidade de Crédito - Instituição Proponente (IP) 
### Área de Gestão da Instituição Credora (IC)
 Portabilidade de Crédito - Instituição Credora (IC)As tabelas a seguir apresentam os status que cada instituição, quando aplicável, deve exibir, os motivos para cada status, os dados a serem exibidos, o prazo de exibição e o possível próximo status, a fim de garantir melhor entendimento da jornada.
| Instituição Proponente (IP) |
| --- |
| Status | Motivo | O que exibir | Prazo de exibição | Próximo status |
| Em análise (Requisito para jornada assíncrona) | Pedido de Portabilidade de Crédito em análise | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | Até a análise ser concluída, conforme informado pela Proponente | Proposta disponível  Sem proposta |
| Proposta disponível (Requisito) | Proposta recebida, aguardando resposta do usuário | Comparativo entre proposta e contrato original | No mínimo 2 dias, conforme legislação e regulação vigente | Em andamento (caso a proposta seja aceita e o contrato seja assinado)  Cancelada (em caso de recusa ou expiração) |
| Sem proposta (Requisito para jornada assíncrona) | Nenhuma proposta disponível para o pedido de Portabilidade de Crédito | Dados do contrato original (opcional): Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | A ser definido pela Proponente | N/A |
| Portabilidade em andamento (Requisito) | Proposta aceita pelo usuário | Comparativo entre proposta aceita e contrato original | Até o cancelamento ou conclusão da portabilidade | Concluída  Cancelada (se cancelada pelo usuário antes da fase de liquidação ou pela Proponente) |
| Portabilidade concluída (Requisito) | Portabilidade de Crédito finalizada com sucesso | Comparativo entre proposta aceita e contrato original | 14 dias corridos após o status final, e depois pode mover para Área de Gestão de Crédito da IF | N/A |
| Portabilidade cancelada (Requisito) | Proposta recusada  Proposta expirada | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito) | Usuário cancelou a portabilidade  Proponente cancelou a portabilidade | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito quando aplicável) | Contraproposta aceita | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |

| Instituição Credora (IC) |
| --- |
| Status | Motivo | O que exibir | Prazo de exibição | Próximo status |
| Portabilidade em andamento (Requisito) | Proposta aceita pelo usuário | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | Até o cancelamento ou conclusão da portabilidade | Concluída  Cancelada (se contraproposta for aceita, ou se portabilidade for cancelada pelo usuário antes da fase de liquidação ou pela Proponente) |
| Portabilidade em andamento (Requisito quando aplicável) | Contraproposta recusada  Contraproposta expirada | Comparativo entre contraproposta e proposta da Proponente | Até o cancelamento ou conclusão da portabilidade | Em andamento |
| Portabilidade concluída (Requisito) | Portabilidade de Crédito finalizada com sucesso | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito) | Usuário cancelou a portabilidade  Proponente cancelou a portabilidade | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito quando aplicável) | Contraproposta aceita | Comparativo entre contraproposta aceita e proposta da Proponente | 14 dias corridos após o status final, e depois pode mover para Área de Gestão de Crédito da IF | N/A |
#F4F5F7
## Requisitos - IP
**Cenário: Pedido em análise**Para pedidos que estejam em análise, nos casos de jornada assíncrona, a Proponente deve:   
1. Prazo de análise: Informar prazo estimado para finalização da análise do pedido.
Portabilidade de Crédito - Pedido em análise #F4F5F7
## Requisitos - IP e IC
**Cenário: Portabilidade em andamento**Para pedidos de portabilidade em andamento, a instituição deve:  
1. Desistência da portabilidade: Permitir desistência da Portabilidade de Crédito antes da liquidação. Informar que o usuário pode desistir da portabilidade antes da fase da liquidação. Caso a portabilidade entre em fase de liquidação, desabilitar a opção de cancelamento do pedido.
Portabilidade de Crédito - Portabilidade em andamento #F4F5F7
## Requisitos - IP
**Cenário: Portabilidade em andamento**Para pedidos de portabilidade em andamento, a Proponente deve:  
1. Download do contrato assinado: Possibilitar que o usuário baixe o contrato assinado da proposta.
Portabilidade de Crédito - Portabilidade em andamento **Cenário: Portabilidade concluída**Para pedidos cuja portabilidade tenha sido efetivada, a Proponente deve:  
1. Download do contrato assinado: Possibilitar que o usuário baixe o contrato assinado da proposta.
Portabilidade de Crédito - Portabilidade concluída #F4F5F7
## Recomendações - IP
**Cenário: Sem oferta disponível**Para pedidos para os quais não há proposta, a Proponente pode:
1. Novo pedido: Possibilitar que o usuário faça um novo pedido de Portabilidade de Crédito.
Portabilidade de crédito - Sem oferta disponível **Cenário: Portabilidade cancelada**Para pedidos de portabilidade que tenham sido cancelados pelo usuário ou pela Proponente, a instituição pode:  
1. Novo pedido: Possibilitar que o usuário faça um novo pedido de Portabilidade de Crédito.
Portabilidade de Crédito - Portabilidade cancelada

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão do Consentimento

---
id: 1436288303
title: v.19.00.00 Gestão do Consentimento
version: 1
modified: 2026-01-12T19:25:18.014Z
url: /spaces/OF/pages/1436288303/v.19.00.00+Gest+o+do+Consentimento
---

O Guia de Experiência apresenta os requisitos e recomendações para o ambiente de Open Finance dentro das Instituições Receptoras e Transmissoras de Dados, e é nesse ambiente que o usuário terá acesso à seção “Meus Compartilhamentos”, na qual poderá ver os dados recebidos e enviados, bem como os detalhes e status dos seus compartilhamentos, sejam eles ativos, cancelados ou vencidos. Nesse ambiente será possível, também, acessar as ações referentes à gestão dos compartilhamentos, sendo possível revogar, alterar ou renovar um compartilhamento de dados. seguindo as diretrizes específicas a cada tipo de ação.As Instituições Receptoras de Dados deverão disponibilizar a ação de Revogação do consentimento dado e opcionalmente, podem disponibilizar as ações de Alteração e Renovação (padrão ou simplificada) dos consentimentos dados. Em caso de implantação das jornadas opcionais, deve-se seguir os requisitos previstos no Guia de UX. As instituições Transmissoras de Dados deverão apenas disponibilizar a ação de revogação do consentimento dado. As demais ações, de Alteração ou Renovação só poderão ser realizadas nas Instituições Receptoras.Dentro do ambiente Open Finance de cada instituição será possível acessar os compartilhamentos, bem como as opções de:
- Revogar compartilhamento.
- Alterar compartilhamento.
- Renovar compartilhamento.

### Revogação:
Ação de revogar um consentimento ativo. Pode acontecer tanto na Instituição Transmissora de Dados quanto na Instituição Receptora de Dados, em concordância com o Art. 15 da Resolução Conjunta nº1 .
### Alteração e renovação padrão:
Ações complementares, realizadas apenas na Instituição Receptora de Dados, que oferecem uma experiência facilitada para criação de um novo consentimento com base nos dados de um consentimento prévio. Caso o consentimento prévio esteja ativo, alterá-lo ou renová-lo implica revogá-lo para criar um novo em seu lugar.
### Renovação simplificada:
Ação complementar similar à renovação padrão, porém restrita a consentimentos ativos, já que trata da atualização do prazo, sem a substituição do consentimento atual por um novo. É dita simplificada pois dispensa a necessidade de redirecionamento e confirmação na Instituição Transmissora de Dados.
## Ambiente Open Finance
Para fácil acesso às jornadas complementares, é importante criarmos o ambiente Open Finance, que vai disponibilizar, entre outros conteúdos, informações sobre os compartilhamentos do usuário.**Nota:** Os requisitos e as recomendações para demais conteúdos do ambiente Open Finance podem ser tratados em momento futuro por esta convenção.Compartilhamento de dados - Ambiente Open Finance#F4F5F7
## Requisitos - IR e IT
**Cenário: Acesso ao Open Finance**
1. As Instituições Receptora de Dados e Transmissora de Dados devem oferecer o ambiente Open Finance em seus canais, incluindo-o no primeiro nível do menu principal, para acesso rápido e fácil pelo usuário.
Compartilhamento de dados - Acesso ao Open Finance**Cenário: Histórico de consentimentos**
1. Dentro do ambiente Open Finance, deve haver uma seção dedicada a expor o histórico completo de compartilhamentos. O histórico deve ter clara diferenciação para consulta de consentimentos transmitidos ou recebidos. O histórico deve ter clara diferenciação para consulta de consentimentos ativos, pendentes e inativos (revogados ou expirados).
2. Deve ser disponibilizado acesso aos detalhes de cada consentimento do histórico, contendo, no mínimo: Validade do consentimento (prazo e data final). No caso de prazo indeterminado, identificar para o usuário como “Indeterminado” ou termo similar. Escopo de dados compartilhados (ex.: cadastrais, conta, cartões de créditos, investimentos e operações de crédito). Nos casos em que a consulta for feita no ambiente da Instituição Receptora de Dados, deve estar disponível a finalidade do compartilhamento. Nos casos em que o consentimento foi renovado através da jornada de renovação simplificada, deve estar disponível todo o histórico dos prazos anteriores, a fim de dar visibilidade ao usuário sobre as renovações passadas de determinado consentimento. Em consentimentos de múltiplos aprovadores, quando consultados pelo ambiente da Instituição Transmissora de Dados, deve ser apresentada a identificação do usuário solicitante.
Compartilhamento de dados - Histórico de consentimentos **Cenário: Revogação do consentimento**
1. Ao acessar os históricos e detalhes dos consentimentos, deve estar disponível ao usuário a opção de revogação de qualquer um dos consentimentos ativos, seja enviado ou recebido.
2. A efetivação de revogação deve ser precedida de tela de confirmação com informações sobre as consequências da ação.
3. A revogação do consentimento deve contemplar todos os dados que são objeto do compartilhamento.
**Nota:**Fica a cargo das Instituições Receptoras de Dados tratar e/ou excluir os dados de acordo com a legislação vigente, incluindo a LGPD.
1. Para a revogação, serão respeitadas as regras de poderes já estabelecidas nas instituições.
2. Após a revogação, o consentimento e seus detalhes devem permanecer acessíveis no histórico, porém com status e informações devidamente atualizadas.
3. A instituição pela qual o usuário revogar o consentimento deve avisar a outra sobre a ação realizada.
Compartilhamento de dados - Revogação do consentimento #F4F5F7
## Requisitos - IR
**Cenário: Alteração e renovação do consentimentos**
1. A Instituição Transmissora de Dados não deve oferecer as jornadas de alteração ou renovação do consentimento, enquanto para a Instituição Receptora de Dados, a oferta é facultativa.
2. Deve-se deixar claro para o usuário que será necessária nova confirmação na Instituição Transmissora de Dados, portanto ele será redirecionado.
3. Ambas as jornadas devem seguir os mesmos requisitos de todas as etapas para uma jornada de criação de consentimento (Capítulo 2), com exceção das limitações de configuração dos parâmetros do consentimento inerentes a uma alteração ou renovação. Ex.: Não é necessário apresentar possibilidade de seleção da Instituição Transmissora de Dados nessas jornadas.
4. Após efetivação da jornada, tanto os detalhes do consentimento revogado quanto do novo devem permanecer acessíveis no histórico, porém com status e informações devidamente atualizadas.
**Nota:**As jornadas de alteração a de renovação padrão são uma forma de otimizar etapas, criando um consentimento com base em informações de outro já existente. São ações tecnicamente idênticas, logo cabe à interface da Instituição Receptora de Dados desenhar cada jornada com a narrativa condizente com as opções de edição oferecidas, como permitir apenas incrementos de prazo em jornadas apresentadas como renovação ou permitir inclusão de mais escopo em jornadas apresentadas como alteração.**Caso a jornada de alteração seja oferecida:**
1. A jornada de alteração deve ser oferecida apenas em consentimentos ativos.
2. Durante a jornada, além da apresentação das informações do consentimento descritas nos requisitos sobre Ambiente de Gestão do consentimento, para uma jornada ser caracterizada como uma alteração e não como uma renovação deve ser apresentado ao menos um dos seguintes elementos: Possibilidade de alteração dos dados (inclusão ou exclusão). Possibilidade de redução do prazo. Possibilidade de alteração da finalidade, para casos em que a Instituição Receptora de Dados tiver mais de uma opção vigente.
3. Em caso de haver somente uma finalidade, essa deve ficar explícita para o usuário, ainda que a finalidade utilizada para o consentimento anterior não esteja mais vigente na Instituição Receptora de Dados.
**Caso a jornada de renovação padrão seja oferecida:**
1. Na jornada de renovação padrão, não deve haver alteração do escopo de dados compartilhados ou da Instituição Transmissora de Dados.
2. A finalidade deve ser alterada apenas em casos de necessidade de atualização por parte da Instituição Receptora de Dados.
3. A nova data de validade do consentimento deve ser calculada a partir da data em que ocorrer a renovação, podendo ser modificada pelo usuário apenas para uma data posterior à data de expiração vigente, inclusive para prazo indeterminado. Ex.: caso um consentimento tenha vigência entre 01/01/2023 e 01/01/2024 (prazo de 12 meses), em qualquer opção de prazo apresentada ao usuário, independentemente do momento da renovação, a data fim do consentimento renovado deve ser posterior à data fim do consentimento original.
Compartilhamento de dados - Alteração e renovação do consentimento **Cenário: Renovação simplificada do consentimentos**
1. A renovação simplificada é realizada exclusivamente pela Instituição Receptora de Dados e apenas para os consentimentos ativos.
2. A comunicação entre Instituição Receptora de Dados e Transmissora de Dados para atualização do prazo de vigência do consentimento será exclusivamente via backend , ou seja, não haverá redirecionamento do usuário para confirmação no ambiente da Instituição Transmissora de Dados.
3. Na jornada de renovação, não deve haver alteração do escopo de dados compartilhados ou da Instituição Transmissora de Dados.
4. A finalidade deve ser alterada apenas em casos de necessidade de atualização por parte da Instituição Receptora de Dados, desde que não resulte em alteração no escopo de dados, comunicando claramente para o usuário o novo objetivo do compartilhamento.
5. A nova data de validade do consentimento deve ser calculada a partir da data em que ocorrer a renovação, podendo ser modificada pelo usuário apenas para uma data superior à data de expiração vigente, inclusive para prazo indeterminado. Ex.: caso um consentimento tenha vigência entre 01/01/2023 e 01/01/2024 (prazo de 12 meses), em qualquer opção de prazo apresentada ao usuário, independentemente do momento da renovação, a data fim do consentimento renovado deve ser posterior à data fim do consentimento original.
6. Consentimentos que envolvam múltipla alçada não poderão ser renovados de forma simplificada.
7. Deve ser exibida tela de sucesso ou insucesso ao final do processo com a resposta da Instituição Transmissora de Dados, em padrão de tela semelhante à tela de efetivação, reforçando ao usuário que a renovação foi concluída (ou não) com sucesso.
8. Em caso de insucesso da renovação de forma simplificada, exibir mensagens conforme o motivo do erro retornado, conforme exemplos abaixo: DEPENDE_MULTIPLA_ALCADA: “O compartilhamento de dados não pôde ser renovado pois depende de múltipla alçada.”. DATA_EXPIRACAO_INVALIDA: “O compartilhamento de dados não pôde ser renovado pois a data final ficou anterior à data de requisição do pedido de renovação ou igual à data de expiração atual ou diferente de prazo indeterminado e maior que 12 meses da data de requisição do pedido de renovação.” REFRESH_TOKEN_JWT: “O compartilhamento de dados não pôde ser renovado com esta Instituição Transmissora.” ESTADO_CONSENTIMENTO_INVALIDO: “O compartilhamento de dados não pôde ser renovado pois está encerrado ou foi cancelado.” ERRO GENÉRICO: “O compartilhamento de dados não pôde ser renovado devido a problemas técnicos. Tente novamente mais tarde.”
Compartilhamento de dados - Renovação simplificada do consentimento #F4F5F7
## Recomendações - IR e IT
**Cenário: Onboarding Open Finance**
1. Na primeira utilização do usuário, realizar um onboarding simples, apresentando as funcionalidades que a instituição oferece dentro do ambiente Open Finance e disponibilizando o link de acesso para a Área do Cidadão, caso o usuário queira acessar informações relativas ao Open Finance.
Compartilhamento de dados - Onboarding Open Finance**Cenário: Ambiente Open Finance**
1. O acesso aos consentimentos pode ser feito das seguintes maneiras:

- Logo após o usuário acessar a opção “Open Finance”.
- Por meio de “Meus compartilhamentos”, acessado pela “Open Finance”.

1. Para fácil acesso do usuário, o ambiente Open Finance pode também estar contido em áreas dedicadas aos produtos, nos canais das instituições.
2. Pode-se permitir, de maneira opcional a cada instituição, a seleção de mais de um consentimento para revogação, com foco em facilitar a experiência.
3. Pode-se permitir, de maneira opcional a cada instituição, a inclusão de filtros de busca para facilitar a localização dos consentimentos.
4. As Transmissoras poderão, a seu critério, disponibilizar termos e condições referentes ao serviço de compartilhamento de dados, no Ambiente de Gestão de consentimento.
Compartilhamento de Dados - Ambiente Open Finance #F4F5F7
## Recomendações - IR
**Cenário: Renovação simplificada do consentimento**
1. Aviso de renovação padrão: As instituições podem comunicar o usuário que o consentimento está perto de sua data de vencimento, levando em consideração a proporcionalidade com o prazo total do compartilhamento. Após uma renovação, se o consentimento anterior ainda estiver vigente, poderá ser revogado.
2. Aviso de renovação simplificada: As instituições podem comunicar o usuário que o consentimento está perto de sua data de vencimento, levando em consideração a proporcionalidade com o prazo total do compartilhamento.
Compartilhamento de dados - Renovação simplificada do consentimento
# Status do Compartilhamento de dados
Para padronizar e facilitar o entendimento do usuário nas Jornadas de Compartilhamento de Dados e Iniciação de Pagamento, mostramos a seguir os status que devem ser apresentados ao usuário.As tabelas têm como objetivo deixar claro o De/Para entre o status apresentados para o usuário e os status técnicos das APIs.Compartilhamento de dados - Status do compartilhamento de dados #F4F5F7
## Requisitos - IR e IT
**Cenário: Geral**
1. O status do compartilhamento deve estar relacionado com a combinação do status do consentimento e, conforme aplicável, das `resources ` associadas a ele e do efetivo compartilhamento de dados cadastrais.
`PENDING AUTHORISATION` > `AVAILABLE `> `TEMPORARILY UNAVAILABLE` > `UNAVAILABLE`Por exemplo: se um consentimento vigente está compartilhando normalmente dados de cadastro e transacionais, mas tem algum recurso com status `UNAVAILABLE`, o status para o usuário deve ser **Ativo**, pois status `AVAILABLE `na ordem de precedência, vem antes do status `UNAVAILABLE `. Por outro lado, se algum recurso está com status `PENDING AUTHORISATION`, então o status para o usuário final deve ser **Pendente de autorização**. 
Confira outros exemplos para casos de API com diferentes status a seguir.
| STATUS PARA USUÁRIO FINAL | CONSENTIMENTO | RECURSO DE SELEÇÃO AGRUPADA (OPERAÇÃO DE CRÉDITO, INVESTIMENTO, CÂMBIO) | RECURSOS DE SELEÇÃO INDIVIDUAL (CONTA OU CARTÃO) | PERMISSÃO PARA DADOS CADASTRAIS |
| --- | --- | --- | --- | --- |
| Ativo | AUTHORISED | AVAILABLE | UNAVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | UNAVAILABLE | AVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | AVAILABLE | TEMPORARILY UNAVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | NÃO SOLICITOU PERMISSÕES¹ | NÃO SOLICITOU PERMISSÕES¹ | SIM |
| Ativo² | AUTHORISED | UNAVAILABLE | UNAVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | TEMPORARILY UNAVAILABLE | UNAVAILABLE | SIM |
| Temporariamente indisponível | AUTHORISED | TEMPORARILY UNAVAILABLE | UNAVAILABLE | NÃO |
| Aguardando aprovação | AUTHORISED | PENDING AUTHORISATION | AVAILABLE | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | PENDING AUTHORISATION | TEMPORARILY UNAVAILABLE | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | PENDING AUTHORISATION | UNAVAILABLE | SIM/NÃO |
#F4F5F71 Usuário não solicitou permissões dos produtos2 Considerando que o usuário manteve relacionamento com a instituição transmissora
1. Caso haja diferentes status de recursos em um mesmo consentimento ( `AVAILABLE` , `PENDING_AUTHORISATION` , T `EMPORARILY UNAVAILABLE` e `UNAVAILABLE` ) e considerando, também, se há ou não impedimento no tráfego de dados cadastrais (pois não geram recursos listáveis na API Resources) , o peso de cada status para consolidação e demonstração do status do consentimento deve seguir o seguinte:

| STATUS PARA USUÁRIO FINAL | CONSENTIMENTO | RECURSO DE SELEÇÃO AGRUPADA (OPERAÇÃO DE CRÉDITO, INVESTIMENTO, CÂMBIO) | RECURSOS DE SELEÇÃO INDIVIDUAL (CONTA OU CARTÃO) | PERMISSÃO PARA DADOS CADASTRAIS |
| --- | --- | --- | --- | --- |
| Aguardando aprovação | AUTHORISED | AVAILABLE | PENDING AUTHORISATION | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | TEMPORARILY UNAVAILABLE | PENDING AUTHORISATION | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | UNAVAILABLE | PENDING AUTHORISATION | SIM/NÃO |
| Aguardando aprovação | AWAITING_AUTHORISATION | NÃO SE APLICA | NÃO SE APLICA | NÃO SE APLICA |
| Vencido | REJECTED | NÃO SE APLICA | NÃO SE APLICA | NÃO SE APLICA |
| Encerrado | REJECTED | NÃO SE APLICA | NÃO SE APLICA | NÃO SE APLICA |

1. Os `rejections_reasons` podem ser utilizados para mostrar detalhes sobre os status. Para três deles, temos os seguintes requisitos: `INTERNAL_SECURITY_REASON` : por se tratar de um consentimento rejeitado devido às políticas de segurança aplicadas pela Instituição Transmissora (prevenção a fraudes), não deverão ser utilizados, na consulta do detalhamento do consentimento, termos que afirmem se tratar de fraude. `CONSENT_MAX_DATE_REACHED` : deve ser mostrado ao usuário com o status Vencido. `CONSENT_EXPIRED` , `CUSTOMER_MANUALLY_REJECTED` e `CONSENT_ TECHNICAL_ISSUE` : não precisam ser demonstrados na consulta dos consentimentos, pois o usuário não chegou a concluir sua solicitação. `CUSTOMER_MANUALLY_REVOKED` : deve ser mostrado ao usuário com o status Encerrado .
 **Nota:**Deseja entender melhor? Mais detalhes e informações técnicas sobre os status das APIs de dados cadastrais e transacionais do usuário podem ser encontrados na Área do Desenvolvedor.#F4F5F7
## Recomendações - IR e IT
**Cenário: Geral**
1. Recomenda-se que, para consentimentos encerrados, as Instituições Receptoras e Transmissoras podem, a seu critério, apresentar o detalhamento do motivo do encerramento – conforme `rejection_reason` associado.
2. Caso o compartilhamento esteja com status ativo, porém, com algum recurso não acessível, a Instituição Receptora dos Dados pode, a seu critério, sinalizar a existência da pendência na lista de consentimento e sugerir que o usuário verifique o detalhamento do consentimento. Fica a critério da instituição apresentar o status isolado por `resource ` na consulta do usuário.
Compartilhamento de dados - Geral

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Contas Salvas em CIBA

---
id: 1436289054
title: v.19.00.00 Gestão de Contas Salvas em CIBA
version: 1
modified: 2026-01-12T19:25:30.065Z
url: /spaces/OF/pages/1436289054/v.19.00.00+Gest+o+de+Contas+Salvas+em+CIBA
---

#F4F5F7
## Requisitos - ID e ITP
**Cenário: Contas salvas em CIBA**
1. O acesso às contas salvas deve ser feito por meio de “Minhas contas salvas”, acessado na opção “Open Finance“, e deve estar disponível tanto na instituição Iniciadora de Transação de Pagamentos como na Instituição Detentora de Conta.
2. Cada conta salva precisa ser identificada individualmente e ter, no mínimo, as seguintes informações: Identificação da outra instituição envolvida no vínculo. Data da autorização: data em que o usuário escolheu salvar a conta no último consentimento dado. Identificação da conta de origem: dados da conta de origem dos pagamentos (número e agência) disponível no consentimento dado. Data do vencimento da autorização. Informações sobre os status das contas salvas: ativos e vencidos/ revogados.
Contas salvas em CIBA #F4F5F7
## Recomendações - ID e ITP
**Cenário: Contas salvas em CIBA**
1. Para fácil acesso do usuário, o ambiente de Gestão Open Finance ou as funcionalidades específicas do Open Finance podem estar contidos em áreas dedicadas aos produtos, nos canais das instituições.
2. Pode-se permitir, de maneira opcional a cada instituição, a seleção de mais de uma conta salva para revogação, com foco em facilitar a experiência.
3. A Instituições Iniciadoras e Detentoras podem, a seu critério, disponibilizar termos e condições referentes ao serviço de iniciação de pagamento, no Ambiente de Gestão de contas salvas.
4. Como possibilidade de atalho para a Área de Gestão, poderá existir um botão/link logo após o usuário concluir uma jornada de pagamento e ter salvo essa conta neste pagamento por meio do CIBA.
5. Fica a critério da cada instituição, a ordenação das contas salvas ativas. Recomendamos que as mais próximas do vencimento apareçam primeiro e em destaque.
Contas salvas em CIBA - Recomendações

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Pix - Jornada Básica de Iniciação de Pagamento

---
id: 1436288686
title: v.19.00.00 Gestão de Pix - Jornada Básica de Iniciação de Pagamento
version: 1
modified: 2026-01-12T19:25:24.041Z
url: /spaces/OF/pages/1436288686/v.19.00.00+Gest+o+de+Pix+-+Jornada+B+sica+de+Inicia+o+de+Pagamento
---

Requisitos e recomendações para gestão de pagamentos com Pix - Jornada Básica de Iniciação de Pagamento via Open Finance. Esta seção serve como base para as demais jornadas de pagamento com Pix oferecidas no Open Finance. #F4F5F7
## Requisitos - ID
**Cenário: Sobre a área de gestão de pagamentos**
1. Área de gestão de pagamentos: Disponibilizar, dentro do Open Finance, ambiente para gestão de contas vinculadas, autorizações e pagamentos.
Área de gestão de pagamentos - ID 
#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a área de gestão de pagamentos**
1. Área de gestão de pagamentos: Disponibilizar, dentro do Open Finance, ambiente para gestão de contas vinculadas, autorizações e pagamentos quando: Oferecer serviços de Pix Agendado, Pix Automático e/ou Transferências Inteligentes. Atuar no escopo de compartilhamento de dados. Diferenciar, com clareza, a área para gestão de compartilhamento de dados da área para gestão de pagamentos.
2. Diferenciação das transações: Quando a ITP não for obrigada a disponibilizar a área para gestão de pagamentos, diferenciar no histórico, os pagamentos realizados via Open Finance daqueles realizados diretamente na instituição.   Ex.: Filtros ou iconografia.
Área de gestão de pagamentos - ITP #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta aos pagamentos**As Instituições devem atualizar os status de cada pagamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Status dos pagamentos: Exibir o status de cada pagamento. Ex.: Concluído, Agendado, Cancelado, Pendente etc.
2. Detalhes dos pagamentos concluídos: Possibilitar que o usuário acesse um comprovante com os detalhes de cada pagamento concluído contendo as seguintes informações, conforme definido pelo arranjo de pagamento: Valor do pagamento. Data e hora/minuto/segundo (horário de Brasília) do pagamento. Identificador da transação ( `endtoEndID` do Pix). Forma de pagamento. Identificação do recebedor (nome completo, CPF mascarado/CNPJ e instituição recebedora). Descrição do pagamento, quando aplicável. Valor da tarifa do serviço, quando aplicável. Identificação do pagador (nome completo, CPF/CNPJ e Detentora). Informações adicionais exigidas pelo arranjo Pix, conforme regulação vigente.
Consulta aos pagamentos 
1. Detalhes dos pagamentos não concluídos: Nos casos em que o pagamento não for concluído com sucesso — como status cancelado, expirado ou rejeitado — exibir os campos aplicáveis de acordo com a disponibilidade de informações no momento da falha, conforme definido pelo arranjo Pix.
Detalhes dos pagamentos não concluídos #F4F5F7
## Recomendações - ID e ITP
**Cenário: Geral**
1. Área Pix: Possibilitar que a gestão de pagamento via Open Finance também possa ser feita na área Pix da instituição.
2. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre os pagamentos com facilidade.
Gestão de pagamentos - Geral - Recomendações

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Pix Agendado

---
id: 1436288725
title: v.19.00.00 Gestão de Pix Agendado
version: 1
modified: 2026-01-12T19:25:24.751Z
url: /spaces/OF/pages/1436288725/v.19.00.00+Gest+o+de+Pix+Agendado
---

Requisitos e recomendações para gestão de pagamentos com Pix Agendado via Open Finance, inclusive em Jornadas sem Redirecionamento (JSR). Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.As instituições devem atualizar os status de cada agendamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta aos agendamentos**As instituições devem atualizar os status de cada agendamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Histórico de pagamentos: Exibir a lista de pagamentos gerados por agendamentos únicos ou recorrentes, com seus respectivos status individuais.   Exs.: Agendado, Concluído, Cancelado, Não realizado etc.
2. Detalhes do pagamento: Exibir comprovante de cada pagamento com todas as informações conforme definido pelo arranjo de pagamento.
3. Detalhes da recorrência: Permitir que o usuário acesse os detalhes do comprovante com todas as informações do agendamento, conforme definido pelo arranjo de pagamento.
Consulta aos agendamentos#F4F5F7
## Requisitos - ITP
**Cenário: Alteração dos agendamentos**Na área de gestão de pagamento, a Iniciadora pode permitir que, além de visualizar os agendamentos, o usuário tenha a experiência de alteração dos parâmetros como data, recebedor ou Detentora, embora esteja cancelando o agendamento vigente e criando uma nova autorização de agendamento.
1. Confirmação de alteração: Na etapa de efetivação, exibir mensagem informando que o agendamento anterior foi cancelado e substituído por um novo, sem necessidade de reinício do processo.      Ex.: Tudo certo! Seu agendamento anterior foi encerrado e um novo foi criado com o novo valor.
Experiência de alteração do agendamento#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação dos agendamentos - Único ou recorrentes**Na área de gestão de pagamento, as instituições devem possibilitar que o usuário cancele os pagamentos agendados com Pix, assegurando clareza, rastreabilidade e segurança. 
1. Cancelamento de agendamentos: Permitir que o usuário cancele os pagamentos agendados (único ou recorrente) e informá-lo sobre as regras para cancelamento, conforme definido pelo arranjo de pagamento.   Ex.: Você pode cancelar o pagamento até às 23:59 do dia anterior à data agendada.
2. Irreversibilidade do cancelamento: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências.
Revogação do agendamento **Para agendamentos recorrentes**
1. Manutenção de pagamentos futuros: Deixar claro para o usuário que o cancelamento de um pagamento agendado não impede que os pagamentos de agendamentos futuros sejam efetivados.
Cancelamento de um pagamento da recorrência - 
Manutenção dos pagamentos futuros #F4F5F7
## Recomendações - ID e ITP
**Cenário: Cancelamento de pagamentos avulsos - Agendamento recorrente**Para casos nos quais seja necessária aprovação adicional, além do solicitante:
1. Confirmação de cancelamento: Em caso de tentativa de cancelamento de um pagamento individual por parte do usuário, exibir uma mensagem de confirmação da ação.    Ex.: Deseja cancelar este pagamento para João Rodrigues? Em caso de cancelamento de um pagamento da recorrência, combinar a mensagem de confirmação com a informação obrigatória de que o cancelamento do pagamento atual não impede o agendamento dos pagamentos futuros, conforme os parâmetros da autorização ativa.    Ex.: Deseja cancelar este pagamento para João Rodrigues? Essa ação não pode ser desfeita e não impede o agendamento dos pagamentos futuros. Em caso de cancelamento completo, combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento.    Ex.: Deseja cancelar esse agendamento para João Rodrigues? Esta ação é irreversível e resultará no cancelamento de todos os pagamentos futuros vinculados.
Cancelamento de um pagamento da recorrência - Recomendações **Cenário: Consulta aos agendamentos**
1. Necessidade de saldo e limites: Informar ao usuário que a transação estará sujeita à disponibilidade de saldo e limites transacionais na conta de débito no momento da efetivação do pagamento.
Necessidade de saldo e limite - Recomendação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Pix Automático

---
id: 1436288776
title: v.19.00.00 Gestão de Pix Automático
version: 1
modified: 2026-01-12T19:25:25.661Z
url: /spaces/OF/pages/1436288776/v.19.00.00+Gest+o+de+Pix+Autom+tico
---

Requisitos e recomendações para gestão de pagamentos com Pix Automático, inclusive em Jornadas sem Redirecionamento (JSR), via Open Finance. Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos. #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta às autorizações de Pix Automático**As Instituições devem atualizar os status de cada autorização de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Histórico de autorizações: Exibir a lista de autorizações de Pix Automático com seus respectivos status individuais.    Exs.: Ativa, Expirada, Cancelada, Pendente etc.
Histórico de autorizações 
1. Detalhes da autorização: Permitir que o usuário acesse os detalhes do comprovante com todas as informações de cada autorização de Pix Automático, conforme definido na etapa de Solicitação de Iniciação de Pagamento. Limite de crédito: Informar sobre a possibilidade, quando aplicável, da utilização de limite de crédito pré-aprovado para pagamentos de valor superior ao saldo disponível em conta.
Consulta às autorizações - Limite de crédito**Cenário: Consulta aos pagamentos com Pix Automático**
1. Histórico de pagamentos: Exibir a lista de pagamentos vinculados a cada autorização, com seus respectivos status individuais.    Exs.: Concluído, Cancelado, Não realizado etc.
2. Detalhes do pagamento: Exibir comprovante de cada pagamento com todas as informações conforme definido pelo arranjo de pagamento.
Detalhes do pagamento**Cenário: Alteração de autorização de Pix Automático**Na área de gestão de pagamentos, as Instituições devem possibilitar que, além de visualizar as autorizações, o usuário possa configurar os parâmetros disponíveis das autorizações ativas como valor máximo (ID/ITP), uso do limite de crédito (ID) e preferências de recebimento de notificações (ID/ITP). 
1. Valor máximo: Para autorizações ativas de valor variável, manter desativado por padrão (valor indeterminado) e permitir que o usuário ative e insira um valor máximo para cada pagamento, respeitando o valor mínimo definido pelo usuário recebedor. Informar que se o valor máximo configurado for inferior ao valor de um pagamento agendado, o pagamento não será efetivado e o usuário poderá ser notificado para buscar outras formas de pagamento. Informar que o novo valor máximo se aplica apenas aos pagamentos ainda não agendados da recorrência.
Alteração da autorização - Valor máximo#F4F5F7
## Requisitos - ID
**Cenário: Alteração de autorização de Pix Automático**
1. Uso do limite de crédito : Manter o uso do limite de crédito ativado por padrão e permitir que o usuário desative.
2. Gestão de notificações: Manter o envio de notificações ativado por padrão e permitir que o usuário desative.
Alteração da autorização - Limite de crédito e notificações#F4F5F7
## Requisitos - ITP
**Cenário: Alteração de autorização de Pix Automático****Nota:**Alterações como troca da ID ou da conta de origem exigem a revogação da autorização vigente e a criação de uma nova. 
A ITP pode, se desejar, oferecer essas alterações como uma edição simples, reaproveitando informações já preenchidas e conduzindo o usuário para a etapa de **Solicitação de Iniciação de Pagamento** de forma fluida e transparente, sem exigir ações manuais de cancelamento ou reinício do processo. 
1. Confirmação de alteração: Na etapa de efetivação, exibir mensagem informando que a autorização anterior foi cancelada e substituída por uma nova, sem necessidade de reinício do processo.    Ex.: Tudo certo! A autorização anterior foi cancelada e uma nova foi criada com a sua nova instituição.
Confirmação da alteração #F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação de autorização de Pix Automático**
1. Revogação da autorização: Permitir que o usuário cancele autorizações ativas e informá-lo sobre as regras para cancelamento conforme definido pelo arranjo de pagamento. Irreversibilidade da revogação: Deixar clara a irreversibilidade do cancelamento da autorização e outras possíveis consequências.
Revogação da autorização**Cenário: Cancelamento do pagamento com Pix Automático**Na área de gestão de pagamento, as instituições devem possibilitar que o usuário cancele os pagamentos da recorrência de Pix Automático, assegurando clareza, rastreabilidade e segurança. 
1. Cancelamento dos pagamentos: Permitir que o usuário cancele os pagamentos da recorrência e informá-lo sobre as regras para cancelamento, conforme definido pelo arranjo de pagamento.    Ex.: Você pode cancelar este pagamento até às 23:59 do dia anterior à data agendada. Irreversibilidade do cancelamento: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências. Manutenção dos pagamentos futuros: Deixar claro para o usuário que o cancelamento de um pagamento não impede que os agendamentos futuros sejam efetivados e novos pagamentos sejam agendados.
Cancelamento de pagamento avulso da recorrência #F4F5F7
## Recomendações - ID e ITP
**Cenário: Revogação de autorização de Pix Automático**
1. Confirmação da revogação: Em caso de tentativa de cancelamento da autorização por parte do usuário, exibir uma mensagem de confirmação da ação.  Ex.: Deseja cancelar esta autorização para Telefonia S/A? Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento. Ex.: Deseja cancelar essa autorização? Esta ação é irreversível e resultará no cancelamento de todos os pagamentos futuros vinculados.
Confirmação da revogação**Cenário: Consulta às autorizações e pagamentos com Pix Automático**
1. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre suas autorizações e pagamentos com facilidade.
Busca - Recomendação**Cenário: Cancelamento do pagamento com Pix Automático**
1. Confirmação do cancelamento: Em caso de tentativa de cancelamento de um pagamento individual por parte do usuário, exibir uma mensagem de confirmação da ação.   Ex.: Deseja cancelar este pagamento para Telefonia S/A?  Combinar a mensagem de confirmação com a informação obrigatória de que o cancelamento do pagamento atual não impede o agendamento dos pagamentos futuros, conforme os parâmetros da autorização ativa.   Ex.: Tem certeza que quer cancelar este pagamento para Telefonia S/A? Esta ação é irreversível e não impede o agendamento dos pagamentos futuros.
Confirmação do cancelamento do pagamento avulso - Recomendação **Cenário: Alteração de autorização de Pix Automático**
1. Gestão de notificações: Permitir a gestão de recebimento de notificações para cada autorização ativa em uma única jornada.
2. Valor máximo: Permitir edição de valor máximo para cada autorização ativa de valor variável em uma única jornada.
Alteração de autorização em uma única jornada - Notificações e Valor máximo #F4F5F7
## Recomendações - ID
**Cenário: Alteração de autorização de Pix Automático**
1. Uso do limite de crédito: Permitir edição do uso do limite de crédito para cada autorização ativa em uma única jornada.
Alteração da autorização em uma única jornada - Limite de crédito

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Transações Temporizadas

---
id: 1436289025
title: v.19.00.00 Gestão de Transações Temporizadas
version: 1
modified: 2026-01-12T19:25:29.540Z
url: /spaces/OF/pages/1436289025/v.19.00.00+Gest+o+de+Transa+es+Temporizadas
---

Requisitos e recomendações para gestão das transações que exigem análise adicional por parte da Instituição Detentora de Conta (ID). #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta à transação temporizada**Caso o usuário saia da tela de análise na etapa de **Efetivação**da Instituição Iniciadora de Transação de Pagamento (ITP), ele deve conseguir retomar a consulta da transação pela área de gestão de pagamentos, juntamente com as demais transações.
Para garantir consistência, as instituições precisam manter o status da transação sempre atualizado, de modo que o usuário visualize as mesmas informações tanto na ITP quanto na ID. 
1. Status das transações: Exibir o status atualizado de cada transação temporizada. Exs.: Em análise, Pendente, Concluída, Cancelada, Negada.
2. Detalhes da transação pendente: Enquanto estiver em análise, disponibilizar acesso aos detalhes da transação, contendo a informação sobre necessidade de tempo adicional para análise e todas as demais informações conforme definido pelo arranjo de pagamento.
Consulta à transação temporizada#F4F5F7
## Requisitos - ITP
**Cenário: Consulta à transação temporizada**
1. Alternativa para transação negada: Se após análise, a transação for negada pela Detentora selecionada, indicar ao usuário, quando aplicável, outra Detentora e/ou forma de iniciação de pagamento.
Alternativa para transação negada #F4F5F7
## Requisitos - ID e ITP
**Cenário: Cancelamento da transação**
1. Cancelamento da transação: Permitir que ao acessar os detalhes da transação em análise na área de gestão, o usuário cancele a transação antes da efetivação.
Cancelamento da transação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Transferências Inteligentes

---
id: 1436288914
title: v.19.00.00 Gestão de Transferências Inteligentes
version: 1
modified: 2026-01-12T19:25:27.644Z
url: /spaces/OF/pages/1436288914/v.19.00.00+Gest+o+de+Transfer+ncias+Inteligentes
---

Requisitos e recomendações para gestão de pagamentos com Transferências Inteligentes via Open Finance. Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento – para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.Gestão de Transferências Inteligentes - ID/ITP#F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta à autorização de Transferências Inteligentes**As instituições devem atualizar os status de cada autorização de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas Áreas de Gestão conforme as regras do arranjo de pagamento. 
1. Histórico de autorizações: Exibir a lista de autorizações de Transferências Inteligentes com seus respectivos status individuais.    Exs.: Ativa, Expirada, Cancelada, Pendente etc.
Histórico de autorizações 
1. Detalhes da autorização: Permitir que o usuário acesse os detalhes do comprovante com todas as informações de cada autorização de Transferências Inteligentes, conforme definido na etapa de Solicitação de Iniciação de Pagamento.   Limite de crédito: Informar sobre a possibilidade, quando aplicável, da utilização de limite de crédito pré-aprovado para transferências de valor superior ao saldo disponível em conta.
Detalhes da autorização - Limite de crédito
1. Sinalização da Jornada Otimizada: Quando aplicável, sinalizar, de forma clara, na lista de autorizações, aquelas para os quais o usuário optou por compartilhar o saldo e limite.
2. Detalhes da autorização: Na tela de detalhes da autorização, indicar que o saldo e o limite estão sendo compartilhados, bem como o escopo de cada dado.
**Cenário: Consulta às transferências realizadas**
1. Histórico de transferências: Exibir a lista de transferências vinculadas a cada autorização, com seus respectivos status individuais.   Exs.: Concluída, Cancelada, Não realizada etc.
2. Detalhes da transferência: Exibir comprovante de cada transferência com todas as informações conforme definido pelo arranjo de pagamento.
Histórico e Detalhes de transferências#F4F5F7
## Requisitos - ITP
**Cenário: Consulta às transferências realizadas**
1. Detalhes da transferência: Além das informações mínimas previstas no comprovante do arranjo de pagamento, exibir o gatilho que originou a transferência, quando aplicável.
Detalhes da transferência - Gatilhos**Cenário: Alteração da autorização de Transferências Inteligentes**Todas as alterações referentes a autorizações de Transferências Inteligentes devem ser realizadas exclusivamente na área de gestão da Instituição Iniciadora de Transação de Pagamento (ITP) que deve comunicar cada alteração à Instituição Detentora de Conta (ID).  
1. Alteração das contas recebedoras: Permitir que o usuário inclua, altere ou exclua contas recebedoras de mesma titularidade para suas autorizações ativas.
2. Gatilhos de transferências: Permitir que, caso a ITP ofereça mais de uma opção de gatilho de transferência, o usuário possa alterá-las.
Alteração da autorização - Contas recebedoras e Gatilhos**Nota:**Alterações como troca da ID ou da conta de origem, modificação do prazo da autorização, ajuste de valor ou de limites transacionais exigem a revogação da autorização vigente e a criação de uma nova. A ITP pode, se desejar, oferecer essas alterações como uma edição simples, reaproveitando informações já preenchidas e conduzindo o usuário para a etapa de Solicitação de Iniciação de Pagamento de forma fluida e transparente, sem exigir ações manuais de cancelamento ou reinício do processo.  
1. Confirmação da alteração: Na etapa de efetivação, exibir mensagem informando que a autorização anterior foi cancelada e substituída por uma nova, sem necessidade de reinício do processo.    Ex.: Tudo certo! Sua autorização anterior foi cancelada e uma nova foi criada com a nova conta de débito escolhida.
Confirmação da alteração#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação da autorização de Transferências Inteligentes**Na área de gestão de pagamento, as Instituições devem possibilitar que o usuário cancele as autorizações ativas de Transferências Inteligentes, assegurando clareza, rastreabilidade e segurança para o usuário. 
1. Revogação da autorização: Permitir que o usuário cancele autorizações ativas e informá-lo sobre as regras para cancelamento, quando aplicável.  Jornada otimizada: Ao optar pela revogação da autorização do pagamento, deixar claro para o usuário que o compartilhamento de saldo e limite também será revogado.​
2. Irreversibilidade da revogação: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências.
Revogação da autorização**Cenário: Jornada Otimizada - Revogação da autorização de Transferências Inteligentes com saldo e limite**
1. Revogação do compartilhamento de saldo e limite:  Permitir que o usuário encerre o compartilhamento de saldo e limite de uma autorização a qualquer momento. Ao optar pelo encerramento do compartilhamento de saldo e limite, deixar claro para o usuário que a autorização de pagamento se mantém ativa.
Revogação do compartilhamento de saldo e limite#F4F5F7
## Recomendações - ITP
**Cenário: Consulta à autorização de Transferências Inteligentes**
1. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre suas autorizações e pagamentos com facilidade.
Consulta à autorização - Busca - Recomendação**Cenário: Alteração da autorização de Transferências Inteligentes**
1. Apelido para contas recebedoras: Permitir que o usuário crie um apelido para cada uma de suas contas recebedoras.    Exs.: Investimentos, Poupança para Viagem etc.
2. Gestão de notificações: Permitir a gestão de recebimento de notificações por autorização.
Alteração da autorização - Apelido para contas recebedoras - Recomendação **Cenário: Revogação da autorização de Transferências Inteligentes**
1. Confirmação da revogação: Em caso de tentativa de cancelamento da autorização por parte do usuário, exibir uma mensagem de confirmação da ação.    Ex.: Deseja cancelar esta autorização? Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento.   Ex.: Tem certeza que quer cancelar a autorização? Essa ação não pode ser desfeita e resultará no cancelamento de todas as transferências futuras vinculadas.
Confirmação da revogação - Recomendação **Cenário: Jornada Otimizada - Revogação da autorização de Transferências Inteligentes com saldo e limite**
1. Benefícios do compartilhamento: Caso o usuário selecione a opção de encerramento do compartilhamento de saldo e limite, exibir mensagem informando sobre os benefícios de manter a funcionalidade.
2. Informação adicional: Incluir informação adicional sobre o compartilhamento de saldo e limite através de link, botão, imagem, texto etc.
Revogação do compartilhamento de saldo e limite - Recomendação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Gestão de Vínculos de Conta para JSR

---
id: 1436289078
title: v.19.00.00 Gestão de Vínculos de Conta para JSR
version: 1
modified: 2026-01-12T19:25:30.594Z
url: /spaces/OF/pages/1436289078/v.19.00.00+Gest+o+de+V+nculos+de+Conta+para+JSR
---

Requisitos e recomendações para gestão de vínculos de conta utilizados nas Jornadas de Pagamento Sem Redirecionamento (JSR). 
#F4F5F7
## Requisitos - ID e ITP
**Cenário: Geral**
1. Retorno ao usuário: Conforme regulação vigente, comunicar o resultado de todas as ações ao usuário, inclusive em caso de falha, conforme descrito na seção Casos de erro do subcapítulo Jornada Básica de Iniciação de Pagamento.
Feedback ao usuário**Cenário: Consulta aos Vínculos de Conta**As instituições devem atualizar os status de cada vínculo de conta para todos os tipos de pagamento sem redirecionamento via Open Finance, de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão.
1. Histórico de vínculos de conta: Exibir a lista de vínculos de conta com seus respectivos status individuais. Exs.: Ativo, Expirado, Cancelado, Em análise etc. Jornada Otimizada (saldo e limite): Sinalizar, de forma clara, na lista de contas vinculadas, aquelas para os quais o usuário optou por compartilhar o saldo e limite.
Histórico dos Vínculos de Conta
1. Detalhes dos vínculos de conta ativos: Permitir que o usuário acesse os detalhes de cada vínculo concluído contendo as seguintes informações: Identificação da outra instituição: Exibir a marca da outra instituição envolvida no vínculo. Identificação da Detentora e conta: Exibir identificação da ID e da conta de débito selecionada (Número da agência e conta). Jornada Otimizada (saldo e limite): Quando aplicável, indicar que o compartilhamento de saldo e limite está ativo . Exibir o escopo de cada dado compartilhado.
Detalhes dos Vínculos de Conta ativos
1. Detalhes dos vínculos de conta inativos: Nos casos em que o vínculo de conta não estiver ativo — como status cancelado, expirado ou rejeitado — exibir os campos aplicáveis de acordo com a disponibilidade de informações no momento.
Detalhes dos Vínculos de Conta inativos#F4F5F7
## Requisitos - ID
**Cenário: Consulta aos Vínculos de Conta**
1. Validade do vínculo: Além das informações mínimas previstas no detalhe de cada vínculo, exibir a data de validade do vínculo de conta.
Validade do Vínculo de Conta**Cenário: Alteração dos Vínculos de Conta** Na área de gestão de vínculos de conta, a Instituição Detentora de Conta (ID) deve possibilitar que o usuário altere parâmetros dos vínculos de conta ativos para pagamentos sem redirecionamento via Open Finance e deve comunicar as alterações à Instituição Iniciadora de Transação de Pagamento (ITP).
1. Alteração da validade: Permitir a alteração do prazo de validade do vínculo da conta. Informar o usuário, no momento da confirmação da alteração, que as alterações do prazo vínculo de conta podem afetar os pagamentos automáticos. Ex.: Prazo alterado com sucesso. Pagamentos automáticos programados para data posterior ao novo prazo serão cancelados. Caso o usuário tenha o compartilhamento de saldo e limite ativo, informar que a data de validade desse consentimento será automaticamente atualizada conforme a nova data de validade do vínculo de conta.

1. Alteração de limites: Permitir a alteração dos limites diário e/ou por transação do vínculo de conta. Informar o usuário, no momento da confirmação da alteração, que as alterações do limite podem afetar os pagamentos agendados.   Ex.: Limite alterado com sucesso. Pagamentos agendados com valor superior ao novo limite não serão efetuados.
Alteração de limites do Vínculo de Conta#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação dos Vínculos de Conta**Na área de gestão de vínculos de conta, as instituições devem possibilitar que o usuário cancele os vínculos ativos para pagamentos sem redirecionamento via Open Finance, assegurando clareza, rastreabilidade e segurança para o usuário. 
1. Revogação do vínculo de conta: Permitir que o usuário cancele vínculos de conta ativos a qualquer momento. Irreversibilidade da revogação : Deixar clara a irreversibilidade do cancelamento do vínculo de conta, e quando aplicável, do compartilhamento de saldo e limite e outras possíveis consequências. Revogação Pix Automático com JSR: Ao optar pela revogação do vínculo de conta, deixar claro para o usuário que a autorização de Pix Automático atrelada ao vínculo de conta também será revogada. Informar que novos agendamentos não poderão ser criados após a revogação. Informar que pagamentos já enviados serão mantidos. Jornada Otimizada (saldo e limite): Ao optar pela revogação do vínculo de conta, deixar claro para o usuário que o compartilhamento de saldo e limite também será revogado.
Revogação do Vínculo de Conta**Cenário: Revogação do compartilhamento de saldo e limite**Na área de gestão de vínculos de conta, as instituições devem possibilitar que o usuário cancele o compartilhamento de saldo e limite de um vínculo de conta para pagamentos sem redirecionamento via Open Finance, sem cancelar o vínculo de conta, assegurando clareza, rastreabilidade e segurança para o usuário.  
1. Revogação do compartilhamento de saldo e limite: Permitir que o usuário cancele o compartilhamento de saldo e limite de um vínculo de conta a qualquer momento. Manutenção do vínculo: Ao optar pelo encerramento do compartilhamento de saldo e limite, deixar claro para o usuário que o vínculo de conta se mantém ativo.
Revogação do compartilhamento de saldo e limite#F4F5F7
## Recomendações - ID e ITP
**Cenário: Consulta aos Vínculos de Conta**
1. Acesso às contas salvas: Disponibilizar acesso às contas salvas através:  - Da área “Open Finance”.  - Do caminho “Open Finance” > “Minhas contas salvas/vinculadas”.   - De áreas dedicadas aos produtos, no canal da instituição.
2. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre seus vínculos de conta com facilidade.
3. Ordenação da lista: Na lista de vínculos de conta ativos, exibir primeiramente os que estiverem próximo de expirar.
Consulta aos Vínculos de Conta - Geral - Recomendações
1. Identificação do dispositivo: Exibir a identificação (apelido) do dispositivo autorizado.
Consulta aos Vínculos de Conta - Dispositivo autorizado - Recomendações#F4F5F7
## Recomendações - ITP
**Cenário: Consulta aos Vínculos de Conta**
1. Validade do vínculo: Exibir a data de validade do vínculo de conta.
Validade do Vínculo de Conta - Recomendação#F4F5F7
## Recomendações - ID
**Cenário: Alteração dos Vínculos de Conta**
1. Uso do termo “alterar”: Usar o termo “alterar” em suas diferentes conjugações, de acordo com o contexto.
2. Otimização da alteração: Pré-preencher dados do vínculo de conta para facilitar a alteração. Ex.: Se o parâmetro alterado for de limites, os demais campos podem vir preenchidos.
Alteração dos Vínculos de Conta#F4F5F7
## Recomendações - ID e ITP
**Cenário: Revogação dos Vínculos de Conta**
1. Revogação do vínculo de conta: Possibilitar que o usuário cancele vínculos de conta ativos em uma única jornada.
2. Confirmação da revogação: Em caso de tentativa de cancelamento do vínculo de conta – com ou sem Jornada Otimizada – por parte do usuário, exibir uma mensagem de confirmação da ação.  Ex.: Tem certeza que quer cancelar o vínculo de conta? [O compartilhamento de saldo e limite também será cancelado.] Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento. Ex.: Tem certeza que deseja cancelar o vínculo? Essa ação é irreversível [e encerra o compartilhamento do saldo e limite e a autorização de Pix Automático atrelada. Os pagamentos agendados serão mantidos, mas novos agendamentos não poderão ser feitos].
Revogação dos Vínculos de Conta - Recomendações**Cenário: Jornada Otimizada - Revogação do compartilhamento de saldo e limite**
1. Benefícios do compartilhamento: Caso o usuário selecione a opção de encerramento do compartilhamento de saldo e limite, exibir mensagem informando sobre os benefícios de manter a funcionalidade.
2. Informação adicional: Incluir informação adicional sobre o compartilhamento de saldo e limite através de link, botão, imagem, texto etc.
Revogação do compartilhamento de saldo e limite - Recomendações

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Gestão Open Finance (UX) > v.19.00.00 Gestão de Pagamentos > v.19.00.00 Status da Iniciação de Pagamento

---
id: 1436289394
title: v.19.00.00 Status da Iniciação de Pagamento
version: 1
modified: 2026-01-12T19:25:35.111Z
url: /spaces/OF/pages/1436289394/v.19.00.00+Status+da+Inicia+o+de+Pagamento
---

Sumário76016truenonelisttrue
# Detalhamento dos Status da Jornada
**Para padronizar e facilitar o entendimento do usuário nas Jornadas de Compartilhamento de Dados e Iniciação de Pagamento, mostramos a seguir os status que devem ser apresentados ao usuário.**As tabelas têm como objetivo deixar claro o De-Para entre o status apresentado para o usuário e os status técnicos das APIs.Área de Gestão de Pagamentos 
# Status da Iniciação de Pagamentos
Para apresentar o status final ao usuário, deve-se seguir esta matriz de Status do “Consentimento” vs Status “Payments”:
| STATUS PARA O USUÁRIO FINAL | STATUS DE CONSENTIMENTO | STATUS DO `GET/PIX/PAYMENTS/{PAYMENTID}` |
| --- | --- | --- |
| (Pagamento) Solicitado | CONSUMED (Etapa de Efetivação) | `RCVD ` (Received) |
| (Pagamento) Agendado | CONSUMED | `SCHD ` (Processo de agendamento realizado) |
| (Consentimento) Aguardando aprovação de multiplas alçadas | PARTIALLY ACCEPTED | N/A |
| (Pagamento) Pendente | CONSUMED | `PDNG ` (Pendente) |
| (Pagamento) Em Processamento | CONSUMED | `ACCP ` (Pagamento pronto para ser enviado para liquidação)   `ACPD ` (Pagamento enviado para liquidação) |
| (Pagamento) Rejeitado pelo usuário ou detentor | CONSUMED | `RJCT ` (Rejeitado) |
| (Pagamento) Concluído | CONSUMED | `ACSC ` (Pagamento liquidado) |
| (Pagamento) Cancelado | REJECTED  CONSUMED | N/A `CANC ` (Transação cancelada a pedido do usuário) |
| Agendamento cancelado | CONSUMED | `CANC ` (Transação cancelada a pedido do usuário) |
| (Pagamento) Solicitado | AUTHORISED (Etapa de Efetivação) | `RCVD ` (Received) |
| (Pagamento) Pendente | AUTHORISED | `PDNG ` (Pendente) |
| (Pagamento) Em Processamento | AUTHORISED | `ACCP ` (Pagamento pronto para ser enviado para liquidação)   `ACPD ` (Pagamento enviado para liquidação) |
| (Pagamento) Rejeitado pelo usuário ou detentor | AUTHORISED | `RJCT ` (Rejeitado) |
| (Pagamento) Concluído | AUTHORISED | `ACSC ` (Pagamento liquidado) |
| (Pagamento) Cancelado | AUTHORISED | `CANC ` (Transação cancelada a pedido do usuário) |
| (Consentimento) Rejeitado pelo usuário ou detentor | REJECTED | N/A |
| (Consentimento) Revogado pelo usuário, pelo detentor ou pelo iniciador | REVOKED | Qualquer status de pagamento que seja diferente de `RCVD ` ou `SCHD` |
| (Consentimento) Aguardando aprovação de multiplas alçadas | PARTIALLY ACCEPTED | N/A |
| (Consentimento) Aguardando aprovação | AWAITING AUTHORISATION | N/A |
| (Consentimento) atingiu o seu limite (Prazo ou valor) | CONSUMED | `RJCT ` (Rejeitado)   `ACSC` (Pagamento liquidado)   `CANC ` (Transação cancelada a pedido do usuário) |
#F4F5F7
## Requisitos - ID e ITP
**Cenário: Geral**
1. O usuário deve ter acesso aos status dos pagamentos nos ambientes já disponíveis e/ou no ambiente dedicado a gestão do Open Finance.
2. Instituição Detentora de Conta: deve apresentar quando aplicável os status de acordo com a tabela/ matriz de status disponibilizado neste guia.
3. O status “(pagamento) solicitado” não é aplicável na Instituição Detentora de Contas, portanto não deve ser apresentado ao usuário.
4. Caso a instituição tenha o cenário de múltipla-alçada, deve ser apresentado o status “aguardando aprovação (do pagamento)” para todos os usuários necessários e envolvidos nessa operação.
5. Caso a instituição tenha o status “(pagamento ou agendamento) em processamento”, deve ser apresentado ao usuário seguindo a matriz de status.
6. Os status “(pagamento) não concluído” e “(pagamento) concluído” devem ser apresentados ao usuário sem exceção.
Status dos pagamentos

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamento Sem Redirecionamento - JSR > v.19.00.00 Jornada de Pagamento Sem Redirecionamento - JSR > v.19.00.00 Requisitos e Recomendações - Pagamentos Sem Redirecionamento (JSR) > v.19.00.00 Comunicação e Notificações - Pagamentos Sem Redirecionamento (JSR)

---
id: 1436294061
title: v.19.00.00 Comunicação e Notificações - Pagamentos Sem Redirecionamento (JSR)
version: 1
modified: 2026-01-12T19:26:53.889Z
url: /spaces/OF/pages/1436294061/v.19.00.00+Comunica+o+e+Notifica+es+-+Pagamentos+Sem+Redirecionamento+JSR
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a Jornada de Pagamento Sem Redirecionamento (JSR).  **Nota:**Consulte a seção de **Comunicação e Notificações** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento****,****Pix Agendado****,****Pix Automático****,****Múltiplos Aprovadores****e****Transações Temporizadas******para visualizar os requisitos e recomendações dos produtos e cenários, que também se aplicam à JSR.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamento Sem Redirecionamento - JSR > v.19.00.00 Jornada de Vinculação de Conta - JSR > v.19.00.00 Requisitos e Recomendações - Vinculação de Conta (JSR) > v.19.00.00 Comunicação e Notificações - Vinculação de Conta (JSR)

---
id: 1436293573
title: v.19.00.00 Comunicação e Notificações - Vinculação de Conta (JSR)
version: 1
modified: 2026-01-12T19:26:46.369Z
url: /spaces/OF/pages/1436293573/v.19.00.00+Comunica+o+e+Notifica+es+-+Vincula+o+de+Conta+JSR
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a Jornada de Vinculação de Conta. **Nota:** Consulte a seção de **Comunicação e Notificações** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento (Pix)****,****Pix Agendado****ou****Pix Automático******para visualizar os requisitos e recomendações dos produtos, que também se aplicam à Jornada de Pagamento Sem Redirecionamento. #F4F5F7
## Requisitos - ITP e ID
**Cenário: Sobre a Vinculação de Conta**
1. Notificações sobre a Vinculação de Conta: Notificar o usuário sobre a vinculação de conta, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) do capítulo Iniciação de Pagamentos . Jornada Otimizada (saldo e limite): Quando aplicável, notificar o usuário sobre o compartilhamento de saldo e limite, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) do capítulo Iniciação de Pagamentos .
Notificações de falha na Vinculação #F4F5F7
## Recomendações - ITP
**Cenário: Sobre a Vinculação de Conta**
1. Expiração do vínculo: Notificar o usuário quando o vínculo de conta estiver próximo de expirar, indicando como renovar ou criar outro vínculo.
Notificação de Vínculo prestes a expirar

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Casos de Erro (Pagamentos e JSR)

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

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Jornada com CIBA (Pagamentos) > Requisitos e Recomendações - CIBA (Pagamentos)

---
id: 1436292542
title: Requisitos e Recomendações - CIBA (Pagamentos)
version: 1
modified: 2026-01-12T19:26:29.396Z
url: /spaces/OF/pages/1436292542/Requisitos+e+Recomenda+es+-+CIBA+Pagamentos
---

Requisitos e recomendações para as etapas de **Solicitação e Confirmação**nas jornadas de Iniciação de Pagamento com CIBA.
# Etapa 1: Solicitação
Solicitação de Iniciação de Transação de Pagamento na Instituição Iniciadora de Transação de Pagamento (ITP) para jornadas com CIBA#F4F5F7
## Requisitos - ITP
**Cenário: Salvar conta na etapa de Confirmação**
1. Para ser possível aplicar os benefícios de uma jornada com CIBA, é necessário que a origem de débito (conta) da Instituição Detentora de Conta tenha sido previamente salva na Instituição Iniciadora de Pagamento. Durante a etapa de confirmação na Instituição Detentora de Conta, em uma jornada de pagamento tradicional via Open Finance, caso ambas as instituições envolvidas tenham suporte para CIBA: Antes do redirecionamento e da resposta da autorização do pagamento, apresentar ao usuário a possibilidade “lembrar” esta Instituição para pagamentos futuros simplificados. Ao exibir a possibilidade de salvar conta entre Instituição Detentora e Iniciadora de Transação de Pagamento, deve se explicar os benefícios da funcionalidade através de uma mensagem, respeitando o tom de voz de cada instituição.
Salvar na conta na etapa de Confirmação**Nota:**Estes requisitos tem o objetivo de, em uma compra futura, permitir que a Iniciadora de Pagamentos mostre a conta salva ao usuário, possibilitando uma jornada de confirmação de pagamento facilitada através do CIBA (*Client Initiated Backchannel Authentication*). O prazo de vencimento da autorização determinado pela Instituição Detentora de Conta por meio das regras previstas no manual de experiência tem extensão mínima de 6 meses, podendo ser indeterminado a depender da escolha da Instituição Detentora de Conta**Cenário: Geral****Para jornadas nas quais sejam utilizadas contas previamente salvas com CIBA:**
1. A jornada de pagamento via CIBA está sujeita aos mesmos requisitos especificados para uma jornada de pagamentos tradicional via Open Finance, quando aplicáveis: Como não há redirecionamento automático em CIBA, os requisitos das etapas de redirecionamento não se aplicam à jornada CIBA. O restante dos requisitos, quando aplicáveis, são válidos para a jornada CIBA, exceto quando substituídos pelos requisitos listados neste capítulo.
2. Caso exista, sempre permitir que o usuário possa selecionar outra forma de pagamento ou seguir o fluxo de Open Finance com outra Detentora de Conta.
Pagamento com conta salva
1. Após a escolha de uma Detentora de Conta vinculada, a Iniciadora de Pagamento deve apresentar um aviso em tela com as seguintes informações: Orientação sobre a necessidade de confirmação do pagamento na Instituição Detentora de Conta. Tempo limite para execução dessa confirmação (5 minutos). Orientação para o usuário não fechar a tela de checkout da Iniciadora de Transação de Pagamento.
Informações sobre a confirmação da transação#F4F5F7
## Recomendações - ITP
**Cenário: Geral**
1. Apresentar ao usuário a possibilidade de pagamento mais rápido selecionando uma Detentora que já processou um pagamento anterior.
Seleção de ID já utilizada
# Etapa 3: Confirmação
Confirmação do pagamento na Instituição Detentora de Conta (ID) para jornadas com CIBA.#F4F5F7
## Requisitos - ID
**Cenário: Geral****Para jornadas nas quais sejam utilizadas contas previamente salvas com CIBA:**
1. O usuário deve ser notificado pela Instituição Detentora de Conta que há um pagamento pendente pelo do canal eletrônico padrão (p.ex.: SMS, push, e-mail etc).
2. Ao clicar na notificação, a jornada terá continuidade no ambiente da Instituição Detentora de Conta. Após a autenticação, o usuário deve ir diretamente para a tela de confirmação do pagamento.
3. Caso o usuário não clique na notificação e sim faça o acesso manual ao canal digital da Instituição Detentora de Conta, deve haver sinalização com destaque de que há uma pendência de confirmação de pagamento.
4. Após a confirmação, a Instituição Detentora de Conta deve orientar o usuário a voltar para o Instituição Iniciadora de Transação de Pagamento a fim de verificar a confirmação do pagamento.
Notificações sobre a transação**Nota:**Lembramos a possibilidade de facilitar ainda mais a jornada com CIBA, permitindo que o usuário aprove a transação clicando na notificação e/ou usando a biometria do dispositivo e/ou capturando a identificação do dispositivo, a critério dos requisitos de segurança e autenticação da Detentora.  
Requisitos e recomendações referentes à gestão de contas salvas estão disponíveis em "Gestão de contas salvas em CIBA"

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Jornada com Múltiplos Aprovadores (Pagamentos) > Requisitos e Recomendações - Múltiplos Aprovadores (Pagamentos) > v.19.00.00 Comunicação e Notificações - Múltiplos Aprovadores (Pagamentos)

---
id: 1436292611
title: v.19.00.00 Comunicação e Notificações - Múltiplos Aprovadores (Pagamentos)
version: 1
modified: 2026-01-12T19:26:31.444Z
url: /spaces/OF/pages/1436292611/v.19.00.00+Comunica+o+e+Notifica+es+-+M+ltiplos+Aprovadores+Pagamentos
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a jornada de iniciação de pagamento via Open Finance com múltiplos aprovadores. **Nota:**Consulte a seção de **Comunicação e Notificações** nos subcapítulos dos produtos de pagamentos para visualizar os demais requisitos e recomendações.#F4F5F7
## Requisitos - ID
**Cenário: Ao solicitante**
1. Status da transação: Notificar o usuário solicitante após a atuação de todos os aprovadores com a atualização de status da transação.
 Notificação ao solicitante **Cenário: Ao aprovador**
1. Notificação de pendência: Notificar ativamente o(s) usuário(s) aprovador(es) imediatamente após a confirmação da transação pelo usuário solicitante. Ex.: push, SMS, e-mail etc.
Notificação ao aprovador

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Jornada de Hybrid flow com hand-off (Pagamentos) > v.19.00.00 Requisitos e Requisitos - Hybrid flow com hand-off (Pagamentos)

---
id: 1436292433
title: v.19.00.00 Requisitos e Requisitos - Hybrid flow com hand-off (Pagamentos)
version: 1
modified: 2026-01-12T19:26:27.059Z
url: /spaces/OF/pages/1436292433/v.19.00.00+Requisitos+e+Requisitos+-+Hybrid+flow+com+hand-off+Pagamentos
---

Requisitos e recomendações para o uso do Hybrid flow com Hand-off entre instituições nas etapas de Direcionamento e Redirecionamento em jornadas de Iniciação de Pagamento.**Nota:**Consulte o subcapítulo **Casos de erro - Pagamentos e JSR** para mais informações sobre os possíveis erros e como comunicá-los ao usuário nas etapas de **Direcionamento**e **Redirecionamento.**
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

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Jornada de Transações Temporizadas (Pagamentos) > Requisitos e Recomendações - Transações Temporizadas (Pagamentos) > v.19.00.00 Comunicação e Notificações - Transações Temporizadas (Pagamentos)

---
id: 1436292721
title: v.19.00.00 Comunicação e Notificações - Transações Temporizadas (Pagamentos)
version: 1
modified: 2026-01-12T19:26:33.286Z
url: /spaces/OF/pages/1436292721/v.19.00.00+Comunica+o+e+Notifica+es+-+Transa+es+Temporizadas+Pagamentos
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante as jornadas de pagamento via Open Finance que envolvam transações temporizadas. Essas comunicações podem ser feitas pela Iniciadora ou pela Detentora, conforme definido pelo arranjo de pagamento.  **Nota:**Consulte a seção de **Comunicação e Notificações** nos subcapítulos dos produtos de pagamentos para visualizar os demais requisitos e recomendações. #F4F5F7
## Recomendações - ITP
**Cenário: Sobre a transação**
1. Status da transação: Caso o usuário saia da tela da ITP, notificá-lo via canal padrão da instituição sobre o andamento e/ou conclusão da transação.   Exs.: Sua transação ainda está em análise. Aguarde. / Transação concluída com sucesso.
Notificações da transação temporizada

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Pix - Jornada Básica de Iniciação de Pagamento > v.19.00.00 Requisitos e Recomendações - Pix - Jornada Básica de Iniciação de Pagamento > v.19.00.00 Comunicação e Notificações - Pix - Jornada Básica de Iniciação de Pagamento

---
id: 1436290708
title: v.19.00.00 Comunicação e Notificações - Pix - Jornada Básica de Iniciação de Pagamento
version: 2
modified: 2026-01-18T13:58:29.238Z
url: /spaces/OF/pages/1436290708/v.19.00.00+Comunica+o+e+Notifica+es+-+Pix+-+Jornada+B+sica+de+Inicia+o+de+Pagamento
---

Esta seção reúne requisitos relacionados à comunicação e ao envio de notificações ao usuário durante a jornada de pagamento instantâneo com Pix via Open Finance conforme
definido pelo arranjo de pagamento.#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix**
1. Notificações sobre o pagamento: Notificar o usuário sobre a efetivação do pagamento, inclusive em caso de falha, conforme as regras do arranjo Pix e conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações sobre pagamentos com Pix

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Pix Agendado - Jornada de Iniciação de Pagamento > v.19.00.00 Requisitos e Recomendações - Pix Agendado > v.19.00.00 Comunicação e Notificações - Pix Agendado

---
id: 1436291475
title: v.19.00.00 Comunicação e Notificações - Pix Agendado
version: 1
modified: 2026-01-12T19:26:09.807Z
url: /spaces/OF/pages/1436291475/v.19.00.00+Comunica+o+e+Notifica+es+-+Pix+Agendado
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a jornada do Pix Agendado. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento.  **Nota:**Consulte a seção de **Comunicação e Notificações** no subcapítulo**Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Pix Agendado**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização do agendamento, inclusive em caso de falha, conforme descrito no subcapítulo Casos de Erro (Pagamentos e JSR) .
Notificações de agendamento - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix Agendado**
1. Status dos pagamentos: Notificar o usuário sobre o sucesso, falha ou cancelamento de um pagamento agendado único ou da recorrência, conforme as regras do arranjo de pagamento Pix Agendado.    Ex.: O Pix Agendado no valor de R$100,00 foi enviado para João Rodrigues da Silva CPF ***.345.678-**.
2. Encerramento de conta do recebedor: Notificar o usuário caso a conta do recebedor seja encerrada, informando-o que esse é o motivo para a não efetivação do pagamento atual e dos futuros, em caso de agendamentos recorrentes.   Ex.: O Pix Agendado para João Rodrigues (R$ 100,00) não foi realizado porque a conta do recebedor foi encerrada. Altere a conta na Área de Gestão.
Notificações de pagamento - ID #F4F5F7
## Recomendações - ID
**Cenário: Sobre pagamentos com Pix Agendado****Para agendamentos recorrentes**
1. Encerramento de conta do recebedor: Em caso de encerramento da conta do recebedor, notificar o usuário direcionando-o para a jornada de Alteração/Cancelamento do(s) agendamento(s), a fim de possibilitar a manutenção do produto com o cadastro de uma nova conta recebedora.    Ex.: O Pix Agendado para João Rodrigues (R$ 100,00) não foi realizado porque a conta do recebedor foi encerrada. Altere a conta na Área de Gestão.
Notificação de pagamento - Recomendação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Pix Automático - Jornada de Iniciação de Pagamento > v.19.00.00 Requisitos e Recomendações - Pix Automático > v.19.00.00 Comunicação e Notificações - Pix Automático

---
id: 1436291876
title: v.19.00.00 Comunicação e Notificações - Pix Automático
version: 1
modified: 2026-01-12T19:26:16.425Z
url: /spaces/OF/pages/1436291876/v.19.00.00+Comunica+o+e+Notifica+es+-+Pix+Autom+tico
---

Esta seção reúne os requisitos relacionados à comunicação com o usuário e ao envio de notificações durante a jornada de Pix Automático. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento. **Nota:**Consulte a seção de **Comunicação e Notificações** no subcapítulo**Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Pix Automático**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização do de Pix Automático, inclusive em caso de falha, conforme descrito no subcapítulo Casos de Erro (Pagamentos e JSR) .
Notificações de autorização - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre a autorização de Pix Automático**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização de Pix Automático, inclusive em caso de falha, conforme as regras do arranjo Pix Automático e conforme descrito no subcapítulo Casos de Erro (Pagamentos e JSR) .
Notificações de autorização - ID #F4F5F7
## Requisitos - ITP
**Cenário: Sobre pagamentos com Pix Automático****Para casos em que a ITP ou recebedor disponibilize notificações sobre pagamentos**
1. Notificações sobre pagamentos: Se a ITP ou recebedor disponibilizar notificações sobre os pagamentos e o usuário tiver habilitado, notificá-lo sobre agendamentos e efetivação de pagamentos, inclusive em caso de falha, conforme descrito no subcapítulo Casos de Erro (Pagamentos e JSR) .
 Notificações de pagamento/agendamento - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix Automático**
1. Notificações sobre pagamentos: Notificar o usuário sobre os pagamentos com Pix Automático, inclusive em caso de falha, conforme as regras do arranjo Pix Automático e conforme descrito no subcapítulo Casos de Erro (Pagamentos e JSR) .
Notificações de pagamento/agendamento - ID

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Iniciação de Pagamentos > v.19.00.00 Transferências Inteligentes - Jornada de Iniciação de Pagamento > v.19.00.00 Requisitos e Recomendações - Transferências Inteligentes > v.19.00.00 Comunicação e Notificações (Transferências Inteligentes)

---
id: 1436292282
title: v.19.00.00 Comunicação e Notificações (Transferências Inteligentes)
version: 1
modified: 2026-01-12T19:26:23.723Z
url: /spaces/OF/pages/1436292282/v.19.00.00+Comunica+o+e+Notifica+es+Transfer+ncias+Inteligentes
---

Esta seção reúne os requisitos relacionados à comunicação com o usuário e ao envio de notificações durante a jornada de Transferências Inteligentes. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento. **Nota:**Consulte a seção de **Comunicação e Notificações** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Transferências Inteligentes**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização de Transferências Inteligentes, inclusive em caso de falha, conforme descrito no subcapítulo Casos de Erro (Pagamentos e JSR) .
Notificações de autorização - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Transferências Inteligentes**
1. Encerramento da conta recebedora: Notificar o usuário caso a conta recebedora seja encerrada, informando-o que esse é o motivo para a não efetivação da transferência atual e das futuras. Ex.: O Pix de R$ 500,00 da sua Gestão Financeira Inteligente para sua conta da Wiscredi falhou porque essa conta foi encerrada. Acesse a área de gestão e altere a conta.
Notificação de pagamentos - ID#F4F5F7
## Recomendações - ITP
**Cenário: Sobre pagamentos com Transferências Inteligentes**
1. Encerramento da conta recebedora: Em caso de encerramento da conta recebedora, notificar o usuário direcionando-o para a jornada de Alteração/Cancelamento da autorização, a fim de possibilitar a manutenção do produto com o cadastro de uma nova conta recebedora.  Ex.: O Pix de R$ 500,00 da sua Gestão Financeira Inteligente para sua conta da Wiscredi falhou porque essa conta foi encerrada. Acesse a área de gestão e altere a conta.
Notificações de pagamentos - Recomendação - ITP

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Portabilidade de Crédito (UX) > v.19.00.00 Motivos de cancelamento do pedido de Portabilidade (UX)

---
id: 1436294543
title: v.19.00.00 Motivos de cancelamento do pedido de Portabilidade (UX)
version: 1
modified: 2026-01-12T19:27:03.071Z
url: /spaces/OF/pages/1436294543/v.19.00.00+Motivos+de+cancelamento+do+pedido+de+Portabilidade+UX
---

Motivos padronizados de cancelamento e inconsistências que possam impedir a conclusão de um pedido de Portabilidade de Crédito na jornada do Open Finance Brasil.
### Instituição Proponente (IP)

| MOTIVO DE CANCELAMENTO | DETALHAMENTO | FASE |
| --- | --- | --- |
| Cancelado pelo usuário | Usuário desiste do pedido de Portabilidade de Crédito | Aceite da contraproposta |
| Valor do saldo devedor atualizado substancialmente divergente do valor informado inicialmente | Saldo devedor atualizado divergente do informado inicialmente | Liquidação |
| Política de crédito | Proponente desiste da oferta ao usuário por políticas internas | Liquidação |

### Instituição Credora (IC)

| MOTIVO DE CANCELAMENTO | DETALHAMENTO | FASE |
| --- | --- | --- |
| Retenção do usuário | Usuário aceitou contraproposta da Instituição Credora (dentro do prazo) | Aceite da contraproposta |
| Contrato já liquidado | Contrato liquidado pelo usuário | Liquidação |
| Divergência de valor do pagamento efetuado | Proponente realizou a liquidação com valor divergente | Confirmação do recebimento |
| Decurso de prazo por pagamento não realizado dentro do prazo (pagamento em data inválida) | Proponente realizou a liquidação fora do prazo | Confirmação do recebimento |
| Falta de liquidação | Proponente não realizou a liquidação do contrato | Confirmação do recebimento |
| Portabilidade de Crédito em andamento | Posteriormente à efetivação do pedido de Portabilidade de Crédito, a Credora identificou que o usuário já possui outro pedido de Portabilidade de Crédito em andamento | Formalização/antes do envio da contraproposta |
| Usuário com ação judicial | Usuário possui ação judicial | Liquidação |
| Modalidade da operação incompatível | Modalidade divergente da indicada pela Instituição Proponente | Liquidação |
Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Portabilidade de Crédito (UX) > v.19.00.00 Jornada Básica de Portabilidade de crédito > v.19.00.00 Requisitos e Recomendações - Jornada Básica de Portabilidade do usuário > v.19.00.00 Comunicação e Notificações (Portabilidade)

---
id: 1436294471
title: v.19.00.00 Comunicação e Notificações (Portabilidade)
version: 1
modified: 2026-01-12T19:27:01.008Z
url: /spaces/OF/pages/1436294471/v.19.00.00+Comunica+o+e+Notifica+es+Portabilidade
---

Esta seção reúne requisitos e recomendações relacionados à comunicação e ao envio de notificações ao usuário durante a jornada de Portabilidade de Crédito.Cada instituição é responsável por notificar o usuário sobre as mudanças de status que ocorrerem em seu respectivo ambiente.As notificações ativas garantem que o usuário seja informado sobre mudanças relevantes do seu pedido. Esses mesmos eventos devem estar refletidos na Área de Gestão por meio de status e descrições acessíveis ao usuário. Mudanças de estado que não exigem notificação ativa ainda podem ser apresentadas como status na Área de Gestão, de forma clara e contextualizada.#F4F5F7
## Requisitos - IP
**Cenário: Geral**
1. Mudanças de status obrigatórias: Notificar ativamente o usuário (ex. push , e-mail, SMS) sobre, no mínimo, as seguintes mudanças de status dos pedidos de Portabilidade de Crédito. Proposta disponível ou não disponível ( jornada assíncrona). Ex.: Temos uma proposta disponível para o seu pedido de portabilidade de crédito. Confira agora mesmo! / Não encontramos uma proposta de portabilidade de crédito adequada ao seu perfil agora. Cancelamento (pela Proponente). Ex.: Sua solicitação de portabilidade de crédito para o empréstimo 885320 foi cancelada. Visualize os detalhes na Área de Gestão. Efetivação da portabilidade. Ex.: Tudo certo! A portabilidade do seu empréstimo 885320 foi concluída. Acesse a Área de Gestão para mais informações.
Portabilidade de Crédito - Geral#F4F5F7
## Requisitos - IC
**Cenário: Geral**
1. Disponibilidade de contraproposta: Quando aplicável, notificar ativamente o usuário (ex. push , e-mail, SMS) sobre a disponibilidade de contraproposta para os pedidos de Portabilidade de Crédito. Ex.: Temos uma contraproposta para você. Recebemos o seu pedido de portabilidade de crédito para o empréstimo 885320 e temos uma contraproposta para você. Confira!
Portabilidade de Crédito - Geral#F4F5F7
## Recomendações - IP
**Cenário: Geral**
1. Mudanças de status opcionais: Para aprimorar a experiência, em caso de jornadas assíncronas, notificar ativamente o usuário (ex. push , e-mail, SMS) sobre as demais mudanças de status dos pedidos de Portabilidade de Crédito, como nos exemplos a seguir. Proposta prestes a expirar . Ex.: Aceite sua proposta de portabilidade do empréstimo 885320 até amanhã às 23h59. Após esse prazo, ela será cancelada.   Portabilidade em andamento . Ex.:  A portabilidade do seu empréstimo 885320 está em fase final e será concluída em até 2 dias. Te avisaremos quando estiver tudo certo!
Portabilidade de Crédito - Geral#F4F5F7
## Recomendações - IC

### Cenário: Geral

1. Expiração da contraproposta: Para aprimorar a experiência, quando aplicável, notificar ativamente o usuário (ex. push , e-mail, SMS) quando a contraproposta estiver próxima de expirar. Ex.: Contraproposta prestes a expirar. Você tem até amanhã às 9h para aceitar a nossa contraproposta para o empréstimo 885320. Após esse prazo, ela será cancelada e a portabilidade será sequenciada com a Wiscredi.
Portabilidade de Crédito - Geral

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Portabilidade de Crédito (UX) > v.19.00.00 Jornada do Consignado Federal > v.19.00.00 Requisitos e Recomendações do Consignado Federal

---
id: 1436294517
title: v.19.00.00 Requisitos e Recomendações do Consignado Federal
version: 1
modified: 2026-01-12T19:27:02.346Z
url: /spaces/OF/pages/1436294517/v.19.00.00+Requisitos+e+Recomenda+es+do+Consignado+Federal
---

Os requisitos e recomendações do **Consignado Federal** correspondem aos da Jornada Básica de Portabilidade do Usuário, acrescidos dos requisitos e recomendações específicos descritos neste capítulo.
# Etapa 2: Consulta (Consignado Federal)
**Nota:**Verifique a etapa **Consulta** no subcapítulo **Jornada Básica de Portabilidade de Crédito** para visualizar outros requisitos e recomendações dos cenários comuns a todos os produtos de Portabilidade. #F4F5F7
## Requisitos - IP
**Cenário: Autorização no SouGov**Quando não tiver a autorização do usuário no SouGov, depois da escolha do contrato, a IP deve observar os requisitos a seguir.**Para casos em que somente o usuário pode dar a autorização:**
1. Direcionamento para o SouGov : Exibir uma tela direcionando o usuário para o SouGov. Na tela de direcionamento, informar ao usuário que, no SouGov, ele deve autorizar a consulta aos dados dos contratos que deseja portar. Ainda na mesma tela, orientar o usuário a retornar à IP depois da autorização no SouGov para seguir com a portabilidade.
**Para casos em que a instituição pode coletar a autorização pelo usuário:**
1. Autorização do contrato no SouGov : Exibir uma tela informando sobre a importância da autorização no SouGov. Exibir opção de continuidade da jornada para o usuário.
Consignado Federal - Autorização no SouGov#F4F5F7
## Recomendação - IP
**Cenário: Autorização no SouGov**
1. Opção para autorização existente : Exibir opção de continuidade da jornada para o usuário que já realizou a autorização no SouGov, informando que essa autorização permanece válida por 45 dias.
Consignado Federal - Autorização no SouGov

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Open Finance Brasil

---
id: 1436287682
title: v.19.00.00 Open Finance Brasil
version: 1
modified: 2026-01-12T19:25:07.362Z
url: /spaces/OF/pages/1436287682/v.19.00.00+Open+Finance+Brasil
---

Este conteúdo tem como objetivo introduzir os conceitos básicos do Open Finance Brasil, apresentando sua estrutura, princípios fundamentais e principais elementos de funcionamento. A seção estabelece uma base comum de entendimento para apoiar a leitura do Guia e contextualizar as jornadas, produtos e serviços abordados nos capítulos seguintes.
# O conceito de Open Finance
O Open Finance (Sistema Financeiro Aberto) é um conjunto de tecnologias e regras que pretendem dar maior controle e liberdade aos usuários de serviços financeiros.Dessa forma, o usuário (pessoa física ou jurídica) é o titular dos seus dados e decidirá quando, com quem, para qual finalidade e por quanto tempo deseja compartilhá-los.Isso acontece por meio do Compartilhamento de Dados e de Serviços entre as diversas instituições financeiras participantes. Essa ação é feita pelo usuário, mediante seu expresso consentimento, e é viabilizada por APIs que permitem uma integração padronizada dos sistemas.**O Open Finance viabiliza o compartilhamento padronizado de dados e serviços financeiros.**
## Open Finance no Brasil
Iniciativa do Banco Central do Brasil (BCB), o Open Finance Brasil funciona por meio da abertura e integração de sistemas entre as instituições participantes. O processo só pode ser iniciado com o consentimento (autorização) do usuário, é 100% gratuito e digital, ocorrendo exclusivamente nos canais digitais das instituições participantes. O objetivo do Open Finance Brasil é dinamizar o sistema financeiro nacional, ampliar a competitividade do mercado e, como consequência, fornecer melhores produtos e serviços com melhores preços e condições ao usuário final.#F4F5F7O **Open Finance Brasil**, ou Sistema Financeiro Aberto, é uma iniciativa do Banco Central do Brasil que tem como principais objetivos trazer inovação ao sistema financeiro, promover a concorrência, melhorar a oferta de produtos e serviços financeiros ao usuário. 
# Quem está envolvido na implementação do Open Finance no Brasil
O Banco Central definiu a Estrutura Inicial do Open Finance, responsável pela governança do processo de implementação do Open Finance no Brasil, que é composta por três níveis: estratégico, administrativo e técnico.
- O nível estratégico é composto por sete conselheiros, sendo um deles um conselheiro independente, ou seja, sem vínculo com as instituições participantes.
- O nível administrativo é composto pela camada administrativa e de secretariado.
- O nível técnico é composto por Grupos Técnicos, com participação das associações que representam as instituições do sistema financeiro e de pagamentos do Brasil. Esse grupo tem o objetivo de definir, em conjunto, as regras do Open Finance para garantir que todos os participantes do ecossistema tenham os mesmos direitos e deveres.

## Principais Instituições do Grupo de Trabalho

- ABBC: Associação Brasileira de Bancos
- ABBI: Associação Brasileira de Bancos Internacionais
- ABCD: Associação Brasileira de Crédito Digital
- ABDE: Associação Brasileira de Desenvolvimento
- Abecs: Associação Brasileira das Empresas de Cartões de Crédito e Serviços
- ABFintechs: Associação Brasileira de Fintechs
- Abipag: Associação Brasileira de Instituições de Pagamentos
- Abranet: Associação Brasileira de Internet
- ACREFI: Associação Nacional das Instituições de Crédito, Financiamento e Investimento
- Home - Camara-e.net : Câmara Brasileira da Economia Digital
- Febraban: Federação Brasileira de Bancos
- OCB: Organização das Cooperativas Brasileiras

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Experiência do Usuário > v.19.00.00 Princípios de Experiência no Open Finance Brasil

---
id: 1436287718
title: v.19.00.00 Princípios de Experiência no Open Finance Brasil
version: 1
modified: 2026-01-12T19:25:07.905Z
url: /spaces/OF/pages/1436287718/v.19.00.00+Princ+pios+de+Experi+ncia+no+Open+Finance+Brasil
---

Esta página apresenta os princípios de experiência aplicáveis ao Open Finance Brasil, combinando conceitos consolidados de usabilidade ao contexto do Open Finance. Dessa forma, ajuda a orientar a concepção de jornadas e interfaces de maneira alinhada às necessidades dos usuários e às diretrizes regulatórias.
# Instituições e Jornadas Open Finance Brasil
**Atenção**: Os princípios listados neste documento devem ser seguidos por todas as instituições participantes do Open Finance Brasil.O Banco Central do Brasil reforça por meio da regulação vigente que as instituições participantes não devem adotar mecanismos que de alguma maneira incentivem, de forma voluntária ou involuntária, o usuário a desistir do compartilhamento de dados ou de serviços no âmbito do Open Finance. Tais mecanismos incluem, por exemplo:
- A inserção de telas, etapas ou informações desnecessárias à confirmação do compartilhamento.
- O uso de linguagem que possa gerar incerteza ou que afete negativamente, de forma direta ou indireta, a percepção do usuário quanto à credibilidade e à segurança do Open Finance ou das demais instituições participantes.
**As instituições participantes não devem adotar mecanismos que de alguma maneira incentivem, de forma voluntária ou involuntária, o usuário a desistir.**
# Princípios das Jornadas Open Finance Brasil
**Princípios são uma forma de criar um entendimento compartilhado sobre as boas práticas no desenvolvimento de um produto ou serviço.**Os princípios expostos neste documento são baseados nas necessidades e nos direitos dos cidadãos, enquanto usuários vivenciando as diferentes jornadas apresentadas neste Guia de Experiência**.**Eles buscam garantir que os times técnicos se mantenham no caminho correto e ajudam na tomada de decisão a respeito das soluções mais apropriadas, quando existem dúvidas ou divergências. Dessa forma, toda jornada desenvolvida no trilho do Open Finance Brasil deve ser:
## 1. Centrada no usuário
A jornada do usuário do Open Finance deve ser centrada nas necessidades, nos comportamentos e nas expectativas dos usuários, considerando que podem mudar ao longo do tempo. As interfaces só fazem sentido se forem desenvolvidas do ponto de vista de quem irá utilizá-las. Caso contrário, a experiência fica comprometida.
## 2. Compreensível

- Em sua jornada, o usuário deve conseguir entender: Quais informações são compartilhadas; Com quem os dados são compartilhados; Qual a finalidade do compartilhamento; Quando começa e quando termina o compartilhamento; Como podem gerenciar o uso dos seus dados.

## 3. Disponível nos canais digitais das instituições
Em todos os canais digitais onde as instituições participantes ofereçam acesso aos seus produtos e serviços (Ex.: aplicativo) devem constar todas as jornadas do Open Finance que a instituição tenha, incluindo as não obrigatórias.
## 4. Simples e intuitiva
As interações devem ser simples e intuitivas, sem prejudicar consentimento, controle, transparência, privacidade ou compreensão. Evitar elementos desnecessários, excesso de texto, palavras confusas, repetições, muitas etapas ou demora que possam causar frustração ou até desistência.
## 5. Veloz
A velocidade das interações é um dos elementos relacionados a uma boa experiência de uso e deve ser adequada ao usuário e à jornada que ele está realizando. Quando falamos em velocidade de carregamento, já se sabe que apenas um segundo é suficiente para influenciar a percepção do usuário. A espera gera uma resposta de estresse e desconfiança no funcionamento do sistema e pode afetar negativamente a experiência.
## 6. Fundamentada no consentimento atual
O consentimento do usuário deve ser atual, ou seja, fundamentado no direito do usuário de fazer e desfazer uma ação a qualquer momento.
## 7. Acessível e Inclusiva
Uma gama diversificada de pessoas deve ser capaz de acessar, usar e compreender o ecossistema do Open Finance. A experiência do Open Finance deve ser democrática e gerar novas oportunidades de engajamento. Dessa forma, é preciso ter cuidado para não criar barreiras de uso na sua implementação. As interfaces devem estar de acordo com as Heurísticas de Nielsen, que são regras gerais que guiam o processo de construção de uma interface, visando garantir que diferentes usuários consigam utilizar a interface sem dificuldades e com uma experiência de uso positiva.
## 8. Segura
No decorrer da jornada, os usuários devem ser orientados em relação a preocupações sobre fraude e privacidade dos dados. Devem estar claras as questões sobre uso, segurança e proteção dos dados, tanto pessoais quanto transacionais.  É importante que se construa um ambiente de confiança (no sistema, no processo e nas instituições) para assegurar o entendimento, a aceitação e a adesão a esse novo serviço. Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Boas práticas para desktop

---
id: 1436287852
title: v.19.00.00 Boas práticas para desktop
version: 1
modified: 2026-01-12T19:25:10.220Z
url: /spaces/OF/pages/1436287852/v.19.00.00+Boas+pr+ticas+para+desktop
---

O Guia de Experiência do Open Finance foi desenvolvido com foco principal em mobile. Esta seção apresenta orientações para adaptar as mesmas diretrizes e boas práticas à experiência em desktop, garantindo consistência, usabilidade e acessibilidade em diferentes dispositivos.
# Adaptação responsiva
A seguir, são apresentados exemplos que demonstram a adaptação da Área de Gestão da versão *mobile* para a versão *desktop*, preservando a estrutura do fluxo e respeitando as boas práticas de UX.Versão *mobile*Versão *desktop*
# Recomendações para ambientes desktop

- Aproveitar o espaço disponível: Distribuir os elementos com equilíbrio, sem sobrecarregar a tela, mantendo a hierarquia de informações clara.
- Manter a consistência visual e funcional : As interações e os componentes devem seguir o mesmo padrão definido no Guia, garantindo familiaridade entre as plataformas.
- Respeitar os fluxos propostos : Adaptar o layout, mas preservando os passos e a lógica dos fluxos descritos no Guia.
- Priorizar acessibilidade e legibilidade : Utilizar fontes e contrastes adequados para leitura em telas maiores, com atenção especial à navegação por teclado.
- Responsividade inteligente : Para resoluções intermediárias (ex: laptops), certificar-se de que os elementos se ajustem corretamente sem comprometer a experiência.
- Foco no usuário : A adaptação para desktop deve manter o foco no usuário, garantindo uma experiência fluida, intuitiva e segura, independentemente do dispositivo utilizado.

# Boas práticas aplicadas
Esta seção apresenta quatro boas práticas aplicadas à adaptação de interfaces para ambientes desktop, com foco na preservação dos fluxos, na consistência visual e na experiência do usuário em telas maiores.
## Hierarquia e Escaneabilidade

1. Hierarquia da informação : Agrupar visualmente menus, filtros e informações para evitar dispersão.
2. Cabeçalhos e subtítulos claros : Cabeçalhos e subtítulos claros são essenciais, pois ajudam na rápida compreensão do conteúdo.
3. Zonas de atenção : Priorizar a área central/esquerda para conteúdo crítico, seguindo os padrões de leitura F/Z.
Hierarquia e Escaneabilidade
## Uso de Espaço e Layout

1. Layout em colunas : Utilizar layout em colunas, recorrendo a painéis laterais para melhor organização do conteúdo.
2. Componentes adaptativos : Utilizar componentes adaptativos, permitindo que botões e campos se expandam conforme o espaço disponível.
3. Espaçamento generoso : Garantir um espaçamento generoso, evitando elementos "grudados" e proporcionando áreas de respiro.
Uso de Espaço e *Layout*
## Navegação e Localização

1. Menu persistente : Manter um menu persistente ou breadcrumb sempre visível para orientar o usuário.
2. Acesso rápido : Incluir atalhos e filtros para facilitar o acesso rápido a ações recorrentes.
3. Estados visíveis : Destacar claramente o que está ativo, como a aba selecionada e os filtros aplicados.
Navegação e Localização
## Consistência Multiplataforma

1. Padronização de componentes : Padronizar componentes para manter a mesma identidade visual e padrões do mobile.
2. Manutenção do fluxo original : Preservar a jornada do usuário mantendo a mesma sequência de etapas do mobile.
Versão *mobile*Versão *desktop* Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Diferenciação entre -marca- e -instituição- para o usuário

---
id: 1436287779
title: v.19.00.00 Diferenciação entre "marca" e "instituição" para o usuário
version: 1
modified: 2026-01-12T19:25:08.981Z
url: /spaces/OF/pages/1436287779/v.19.00.00+Diferencia+o+entre+marca+e+institui+o+para+o+usu+rio
---

Complementando as informações apresentadas na página anterior, esta página apresenta definições e orientações sobre o uso e a identificação de marcas no contexto do Open Finance Brasil, trazendo exemplos que apoiam o reconhecimento pelo usuário e a aplicação consistente das marcas ao longo das jornadas, complementando as informações apresentadas no capítulo anterior.Marca e instituição podem parecer semelhantes para os usuários, mas apresentam diferenças conceituais.#F4F5F7
# Requisitos

## Marca

- Nome de fácil identificação que permite rápida associação para o público em geral.
- Deve levar em consideração o posicionamento atual perante o mercado e ser utilizada pelas instituições que serão identificadas pela marca no Open Finance.
- Deve haver ao menos um canal eletrônico associado a ela, onde seja possível autenticação e confirmação dos dados pelo usuário.
- Usualmente, não tem um CNPJ, mas é usada para identificar uma ou mais instituições de um mesmo conglomerado ou ainda, produtos identificados com marcas de terceiros.
- A definição da marca é feita a exclusivo critério da instituição do Open Finance, inclusive considerando seu posicionamento de mercado e marca, estratégia de negócios e canais digitais acessíveis aos usuários.

## Instituição

- Necessita ser parte do posicionamento de mercado relacionado à marca que utiliza.
- Necessariamente tem CNPJ.
- Instituição com a qual o usuário se relaciona contratualmente e na efetiva prestação de serviço.
- Conglomerado, para fins deste guia, pode ser composto por subsidiárias ou outras instituições controladas, controladoras, coligadas, filiadas, ligadas ou relacionadas contratualmente que podem usar determinada marca para sua identificação no Open Finance.

## Exemplos de diferenciação
Exemplo de diferenciação entre marca e instituição

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Glossário

---
id: 1436288211
title: v.19.00.00 Glossário
version: 1
modified: 2026-01-12T19:25:16.076Z
url: /spaces/OF/pages/1436288211/v.19.00.00+Gloss+rio
---

O glossário padroniza o uso de termos presentes nas resoluções, com o objetivo de promover alinhamento entre as instituições e facilitar a compreensão pelos usuários. Os termos são descritos de forma clara e acessível, apoiando o uso consistente das referências ao longo do Guia e contribuindo para uma jornada mais uniforme.
# Glossário de Consentimento

| Termo na Resolução | Termo para o usuário | Descrição |
| --- | --- | --- |
| Usuário | Usuário | Qualquer pessoa natural ou jurídica que mantém relacionamento destinado à prestação de serviço financeiro ou à realização de operação financeira com as instituições. |
| Solicitação de compartilhamento | Solicitação de compartilhamento ou solicitar compartilhamento | Solicitação iniciada por um usuário para compartilhamento com a Instituição Receptora de seus dados mantidos na Instituição Transmissora. Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “solicitação”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Consentimento | Autorização de compartilhamento ou autorizar compartilhamento | Etapa inicial do fluxo de solicitação de compartilhamento, na qual a Instituição Receptora solicita o consentimento ao usuário. Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “autorização”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Autenticação | Autenticação ou autenticar | Etapa do fluxo de solicitação de compartilhamento na qual a Instituição Transmissora autentica o usuário, ou seja, confirma a identidade do usuário. |
| Confirmação do compartilhamento | Confirmação do compartilhamento ou confirmar compartilhamento | Etapa do fluxo de compartilhamento na qual a Instituição Transmissora confirma com o usuário os dados objeto de compartilhamento. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “confirmação”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Efetivação da solicitação | Situação do compartilhamento | Última etapa do fluxo de solicitação de compartilhamento, na qual a Instituição Receptora informa ao usuário sobre a conclusão e o status da solicitação de compartilhamento (i.e, efetivada, não efetivada ou em aberto). Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “situação”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Redirecionamento | Redirecionamento ou redirecionar | Etapa na qual o usuário é notificado e redirecionado para o ambiente de outra Instituição, seja esta uma Instituição Transmissora de Dados ou Instituição Receptora de Dados. |
| Instituição Transmissora | Instituição de origem | Instituição participante que compartilha com a Instituição Receptora os dados objeto de compartilhamento. |
| Instituição Receptora | Instituição de destino | Instituição participante que recebe os dados objeto de compartilhamento. |
| Identificação do usuário | Autenticação ou autenticar | CPF ou CNPJ utilizados para identificar o usuário no fluxo de solicitação de compartilhamento. |
| Dados objeto de compartilhamento | Confirmação do compartilhamento ou confirmar compartilhamento | Dados do usuário que serão compartilhados com a Instituição Receptora de Dados para uma finalidade específica. Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “dados”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Prazo de validade do consentimento | Situação do compartilhamento | Prazo de validade do consentimento, limitado a 12 meses, apresentado de acordo com a finalidade, podendo ser alterado pelo cliente. Considera desde a data atual até a data final escolhida pelo cliente. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “prazo”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Pré-solicitação de compartilhamento | N/A | Etapa anterior ao fluxo de solicitação de compartilhamento, ocorrendo no ambiente da Instituição Receptora. |
| Pós-solicitação de compartilhamento | N/A | Etapa posterior ao fluxo de solicitação de compartilhamento, ocorrendo no ambiente da Instituição Receptora. |
| Termos e condições do consentimento | Termos e condições do compartilhamento | Termos e condições do consentimento para compartilhamento de dados no Open Finance. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “termos e condições”, caso o contexto do compartilhamento esteja claro nos demais elementos. |
| Origem dos dados | Origem dos dados do compartilhamento | Produtos ou serviços na Instituição Transmissora que serão utilizados para compartilhar os dados objeto de compartilhamento (p.ex.: conta poupança, cartão de crédito, etc.). Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “origem dos dados”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Finalidade do consentimento | Objetivo do compartilhamento | Finalidade de uso pela Instituição Receptora dos Dados objeto de compartilhamento. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “objetivo”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Revogação do consentimento | Encerramento do compartilhamento ou encerrar compartilhamento | Revogação do consentimento realizado pelo usuário na Instituição Transmissora ou Receptora. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “encerrar”, caso o contexto de compartilhamento esteja claro nos demais elementos. |

# Glossário de Iniciação de Pagamentos

| Termo na Resolução | Termo para o usuário | Tipo | Descrição |
| --- | --- | --- | --- |
| Instituição Iniciadora de Transação de Pagamento | Instituição Iniciadora de Pagamento | Requisito | Instituição participante que o usuário utilizou para realizar o serviço de Iniciação de Pagamento pelo Open Finance, e que irá realizar o processo junto à Instituição Detentora de Conta. |
| Instituição Detentora de Conta | Instituição de débito | Requisito | Instituição participante com a qual o usuário tem relacionamento e detém sua conta para movimentação de recursos. |
| Serviço de Iniciação de Transação de Pagamento | (Conferir exemplos após a tabela) | Recomendação | Pagamento que será realizado utilizando o Open Finance. |
| Arranjos de pagamento vigentes | Forma de pagamento | Recomendação | É o conjunto de regras e procedimentos que disciplina a prestação de determinado serviço de pagamento ao público. |
| Recebedor da transação de pagamento | Recebedor ou lojista | Recomendação | São os termos utilizados para se referir ao beneficiário do pagamento, podendo ser o “lojista” no caso de B2C e “recebedor” no caso de P2P. |
| Transferências entre contas na própria Instituição | Transferência entre contas da mesma instituição /transferência / transferência entre conta | Requisito | Transferências entre contas na própria instituição: forma de pagamento disponível para o serviço de Iniciação de Transação de Pagamento. É permitido utilizar o termo resumido “transferência” ou “transferência entre contas” para interfaces menores e em situações em que o contexto está claro ao usuário. |
| Transação de Pagamento Instantâneo (Pix) Pix | Pix | Requisito | Forma de pagamento instantâneo brasileiro disponível para o serviço de Iniciação de Transação de Pagamento. Por se tratar de um termo conhecido do usuário comum, recomendamos a utilização de Pix. |
| Data do Pagamento | Data do Pagamento | Recomendação | Data em que o pagamento deverá ser iniciado e executado. |
| Efetivação da Iniciação da Transação de Pagamento | Pagamento solicitado | Requisito | Última etapa do fluxo de solicitação de Iniciação de Pagamento, na qual a Instituição Iniciadora de Pagamento informa ao usuário sobre a efetivação ou não da solicitação de pagamento, bem como seu respectivo status (p.ex.: concluído, pendente, aguardando demais aprovadores). |
| Informações do Pagamento | Informações do Pagamento | Recomendação | Informações referentes ao pagamento que serão disponibilizadas ao usuário após sua transação. |
| Finalidade do Pagamento | Descrição do pagamento ou descrição | Recomendação | Campo aberto para o usuário descrever ou identificar a finalidade das suas transações. |
| Informações do Pagador | Pagador | Recomendação | Informações complementares relativas a conta utilizada para realizar a transação de Iniciação de Pagamento pelo usuário (pagador). |
| Usuário Pagador | Consumidor(a) | Recomendação | Identificação da pessoa pagadora em uma autorização de Pix Automático. |
| Usuário Recebedor | Recebedor | Recomendação | Identificação do destinatário dos pagamentos em uma autorização de Pix Automático. |
| Pagamentos Únicos | Pagamento | Requisito | Transação que ocorrerá uma única vez. |
| Origem | Conta de Débito | Requisito | Contas disponíveis na Instituição de débito que serão utilizados para realizar o pagamento (p.ex.: conta poupança, conta de depósito, etc.). |
| Prazo | Prazo | Requisito | Prazo de validade do consentimento, que estabelecerá até quando (data final) o serviço de iniciação de transação de pagamento será prestado. |
| Periodicidade da Transação | Data do(s) próximo(s) pagamento(s)/Recorrência de Pagamento | Recomendação | Define o intervalo de execução entre os pagamentos de transações recorrentes.   Data do(s) próximo(s) pagamento(s): aplicável para os casos/arranjos onde o usuário pode definir o intervalo estabelecendo uma data fixa e frequência. Exemplo: pagamento realizado mensalmente, todo dia 5.   Recorrência de pagamento: aplicável para os casos/arranjos onde o usuário pode definir o intervalo estabelecendo uma frequência. Exemplo: pagamento realizado semanalmente ou mensalmente.   Data inicial: data que inicia a recorrência de pagamentos.   Data final: a data em que ocorre o último pagamento. |
| Transações de pagamentos sucessivas | Pagamentos recorrentes | Requisito | Consentimento que ocorre na etapa inicial do fluxo de iniciação de transação de pagamento, na qual a Instituição Iniciadora solicita o consentimento ao usuário. Exemplos: Pix Automáticos, agendamentos recorrentes e transferências inteligentes. |
| Consentimento | Autorização de pagamento ou autorizar pagamento | Requisito | São os termos utilizados para se referir à confirmação explícita dada pelo usuário para a solicitação de transação de pagamento. |
| Pagamento de boleto | Pagamento de boleto(s) ou pagar boleto(s | Requisito | Pagamento de boleto: Forma de pagamento disponível para o serviço de Iniciação de Transação de Pagamento. |
| Débito em Conta | Débito em Conta | Requisito | Débito em conta: Forma de pagamento disponível para o serviço de Iniciação de Transação de Pagamento. |
| Ainda não Publicado | Pix Automático | Requisito | Tipo de transação sucessiva, cujo consentimento permite o débito programado de valores recorrentes fixos ou variáveis, com a possibilidade de definição de limites pelo pagador. O recebedor deve ser PJ, pode ser originado de forma online e offline e alguns casos de uso são: pagamentos de contas e assinaturas de serviços. |
| Ainda não Publicado | Agendamentos Recorrentes | Requisito | Tipo de transação sucessiva, cujo consentimento possui valor fixo e limites de quantidade e prazo, definidos pelo pagador. O recebedor pode ser PF ou PJ e alguns casos de uso são: mesadas, doações e pagamentos diversos (diarista, professor particular, etc.). |
| Ainda não Publicado | Transferências Inteligentes | Requisito | Tipo de transação sucessiva, cujo consentimento permite a transferência automática de fundos entre contas bancárias de mesma titularidade, geralmente em diferentes instituições financeiras, com a possibilidade de definição de limites pelo pagador. O usuário pode ser PF ou PJ e alguns casos de uso são: cobertura de contas negativadas, automações de gestão financeira e automações de investimentos. |
| CIBA (Client Initiated Backchannel Authentication) | - | - | O serviço de Iniciação de Pagamentos do Open Finance Brasil implementa o fluxo de consentimento com redirecionamento para a autorização de pagamentos. Esse redirecionamento pode ser realizado via redirect entre aplicativos ou sites e aplicativos. O CIBA fornece uma alternativa para esse fluxo onde ocorre um desacoplamento do processo e o canal para a autorização poderá ser um push-notification, SMS, e-mail, WhatsApp etc. |
| Contas Salvas | - | - | Na jornada CIBA, é dada ao usuário a opção de vincular a Iniciadora de Pagamentos com a Detentora de Conta. Assim, em uma transação futura, a Iniciadora de Pagamentos pode mostrar a conta salva ao usuário, possibilitando uma jornada de confirmação de pagamento facilitada. |

## Identificação do arranjo de pagamentos - Exemplos
As formas de identificação da funcionalidade são exemplos, entretanto, a identificação do arranjo é requisito no caso de exibição junto às outras formas de pagamento.**Nota:** Os exemplos não contemplam todas as possibilidades de aplicação. São apenas formas de demonstrar como a identificação pode ser apresentada ao usuário, havendo inúmeras formas de fazê-lo.
| Combinações possíveis |
| --- |
| Usar | Minha/Meu | Conta |
| Pagar com | Outro/Outra | Saldo |
| Transferir para | | Banco |
| Depositar em/na | | Instituição |

### Exemplos aplicados
Pix: Pagar com outro banco.Boleto: Pagar com minha instituição
# Glossário de Jornada sem Redirecionamento

| Termo na Resolução | Termo para o usuário | Descrição |
| --- | --- | --- |
| N/A | Instituição Parceira | Instituição Parceira é entendida como Detentora de Conta que tem o acordo/contrato bilateral com a ITP para a Jornada de Iniciação de Pagamento sem redirecionamento. |
| Participantes Associados | A Definir | Instituições autorizadas pelo Banco Central a operarem no Open Finance. |
| N/A | Contas Vinculadas | Contas em que o usuário autorizou pagamentos futuros, para fins de jornada sem redirecionamento, entre ITP, ID e o dispositivo do usuário. |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Manual de uso da marca Open Finance Brasil

---
id: 1436288064
title: v.19.00.00 Manual de uso da marca Open Finance Brasil
version: 1
modified: 2026-01-12T19:25:14.173Z
url: /spaces/OF/pages/1436288064/v.19.00.00+Manual+de+uso+da+marca+Open+Finance+Brasil
---

Este manual tem como objetivo orientar o uso coerente e consistente da marca Open Finance e de seus elementos visuais. As ações de comunicação da Estrutura de Governança devem seguir as orientações na íntegra, de forma de garantir a construção da personalidade Open Finance. Os licenciados têm permissão para aplicar a marca Open Finance dentro de sua identidade corporativa, desde que preservando as regras de proporção de símbolo e logotipo, bem como suas regras de cores e de grafia do nome em textos, ficando dispensados de seguir regras de tipografia, códigos cromáticos e iconografia.**Nota:**O uso incorreto ou indevido de qualquer elemento da marca Open Finance será tratado pela estrutura por meio da abertura de ticket.
# Marca

## Versão preferencial Colorida
A marca Open Finance é uma marca mista, e deve ser sempre aplicada na sua forma íntegra, constituída pelo conjunto símbolo e logotipo. O símbolo pode ser aplicado sozinho, mas, na função de ícone, possui normas específicas. A versão colorida da marca usa as cores azul-claro e grafite da paleta de cores e deve sempre preservar o contraste e a legibilidade. A marca Open Finance apresenta-se apenas na versão horizontal.Versão preferencial colorida[Baixar a versão colorida em SVG](https://ob-public-files.s3.amazonaws.com/marca_open_finance.ai)[Baixar a versão colorida em JPEG](https://ob-public-files.s3.amazonaws.com/marca_colorida_open_finance.JPEG.jpg)
## Versões monocromáticas Positiva e negativa
As versões monocromáticas positiva (preta) e negativa (branca) devem ser aplicadas em casos de fundos coloridos em que a versão colorida não tem legibilidade ou contraste. Sendo a versão positiva aplicada para fundos coloridos claros, e a versão negativa para fundos coloridos escuros. Quando a cor de fundo for o azul-escuro ou o azul-claro da paleta de cores, a marca deve sempre ser aplicada na versão negativa (branca), conforme ilustrado abaixo. Versões monocromáticas[Baixar a versão positiva em SVG](https://ob-public-files.s3.amazonaws.com/marca_positiva_open_finance.svg)[Baixar a versão negativa em SVG](https://ob-public-files.s3.amazonaws.com/marca_negativa_open_finance.svg)
## Proporções e margens

### Redução máxima
A redução máxima da marca é o menor tamanho permitido, preservando sua legibilidade. Foi estabelecido que o tamanho mínimo para a altura da marca Open Finance nunca seja inferior a 12,5mm ou 35,6px. As medidas estão em milímetros para mídias impressas e em pixels para mídias digitais.Redução máxima
### Margem de segurança
A margem de segurança é a área imaginária (linha tracejada ciano) de não interferência nos elementos da marca, assegurando a sua correta percepção. A dimensão h é o espaçamento definido a partir da altura da “asa” do símbolo, conforme ilustra o diagrama abaixo.Margem de segurança
# Símbolo
O símbolo é um elemento importante da identidade visual da marca Open Finance, uma vez que transmite os atributos de liberdade financeira. Pode ser aplicado sozinho, como um recurso de grafismo nas versões: preenchido colorido; preenchido positivo e negativo; contorno colorido; contorno positivo e negativo e monocromático azul-claro e monocromático grafite. Para aplicações como ícone (pictograma), o símbolo possui normas específicas.**Atenção:**Não é permitido o uso de gradientes, sombras e efeitos no símbolo, por não preservar as características nem garantir a legibilidade deste.Símbolos Open Finance Brasil[Baixar a versão colorida em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_open_finance.HTML.svg)[Baixar a versão negativa em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_negativo_open_finance.HTML.svg)
## Redução máxima
A redução máxima do símbolo é o menor tamanho permitido, preservando sua legibilidade. Foi estabelecido que o tamanho mínimo para a altura do símbolo Open Finance nunca seja inferior a 10,6mm ou 30px. A espessura do contorno na redução máxima é de 1pt, de forma a garantir as características e legibilidade do símbolo. As medidas estão em milímetros para mídias impressas e em pixels para mídias digitais.Redução máxima
## Margem de segurança
A margem de segurança é a área imaginária (linha pontilhada ciano) de não interferência nos elementos do símbolo, assegurando a sua correta percepção. A dimensão h é o espaçamento definido a partir da altura da "asa" do símbolo.Margem de segurança
# Ícone
Essa versão foi criada para circunstâncias específicas, em ambientes digitais, em casos que os sistemas ou as plataformas usem ícones. O símbolo Open Finance pode ser utilizado sozinho, como ícone, na função de pictograma. Entretanto, suas características visuais devem ser preservadas.**Atenção:**Não é permitido o uso de gradientes, sombras e efeitos no ícone Open Finance, por não preservar as características nem garantir a legibilidade deste.Aplicações e dimensões mínimas[Baixar a versão colorida em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_open_finance.svg)[Baixar a versão positiva em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_positivo_open_finance.svg)[Baixar a versão negativa em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_negativo_open_finance.svg)[Baixar a versão azul claro em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_azul_claro_open_finance.svg)[Baixar a versão grafite em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_grafite_open_finance.svg)
## Cores preferenciais
Preferencialmente, deve-se usar o ícone Open Finance na versão colorida e nas versões monocromáticas positiva (preta) e negativa (branca), sendo a positiva para fundos claros, e a negativa para fundos escuros.
## Cores alternativas
Para uma melhor adequação do ícone às diversas interfaces gráficas e às diversas paletas cromáticas existentes, é permitido o uso dos matizes dos sistemas ou plataformas.
## Contorno
Como ícone, só é permitida a versão contorno em tamanho de redução máxima (9,7mm x 10,6mm ou 27,5px x 30px), com espessura de 1pt, de forma a garantir as características e a legibilidade do símbolo.O ícone Open Finance dividirá o espaço do widget com o símbolo ou o logotipo do participante. Nesse caso, o espaço do quadrante superior esquerdo deve ser utilizado para o ícone Open Finance, enquanto o quadrante inferior direito será utilizado para o símbolo ou o logotipo do participante. Esse layout é fixo e não pode ser alterado.Para uma melhor adequação visual ao espaço disponível no widget, o símbolo ou o logotipo do participante pode extrapolar os limites do quadrante em 20% do formato original, conforme diagrama abaixo.Como já explicado, o ícone Open Finance pode assumir a cor predominante do participante para melhor adequação à interface gráfica.Ícone Open Finance em widget
# Grafia
Para assegurar a consistência e a coerência da marca Open Finance, é fundamental atentar para a forma de grafar o nome. Apesar de a marca ser escrita em caixa-baixa, em textos corridos, deve-se usar a primeira letra das duas palavras, Open Finance, em caixa-alta. Nos casos em que o texto encontra-se todo em letras maiúsculas, é permitido o uso do nome Open Finance todo em caixa-alta. Nos casos em que é necessário destacar o nome Open Finance, em textos, usa-se o negrito, não sendo permitido o uso de sublinhado, itálico ou aspas.
## Formas corretas
Com o Open Finance, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.COM O OPEN FINANCE, VOCÊ VAI PODER ESCOLHER OS PRODUTOS E SERVIÇOS FINANCEIROS MAIS ADEQUADOS PARA VOCÊ, INDEPENDENTEMENTE DA INSTITUIÇÃO.Com o **Open Finance**, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.
## Formas incorretas
Com o open finance, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o OPEN FINANCE, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o *Open Finance*, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o Open Finance, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o “Open Finance”, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição. Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Premissas de implementação

---
id: 1436287747
title: v.19.00.00 Premissas de implementação
version: 1
modified: 2026-01-12T19:25:08.341Z
url: /spaces/OF/pages/1436287747/v.19.00.00+Premissas+de+implementa+o
---

Este tópico apresenta as premissas de implementação que orientam a aplicação das diretrizes de experiência no Open Finance Brasil, resultantes do alinhamento realizado no âmbito do Grupo de Trabalho de Experiência do Usuário (GT- UX), com o objetivo de apoiar decisões técnicas na execução das jornadas. As orientações se baseiam em duas premissas centrais: preservar o tom de voz das instituições participantes e reforçar seu posicionamento como marcas, assegurando flexibilidade na comunicação sem comprometer a padronização necessária para a jornada do usuário.
# Premissa 1: Preservar o tom de voz de cada instituição
**Tom de voz é como a marca se comunica com seus usuários em diferentes canais.**Por exemplo, para conversar com seus usuários, uma marca mais informal pode usar termos como ‘E aí?’ ou “Legal!”, já uma marca mais tradicional pode usar termos como “Pronto!” ou “Tudo certo”. Em uma situação de erro, por exemplo, pode-se usar a palavra “Ops” (para exemplificar uma linguagem um pouco mais informal) ou “Desculpe” (para exemplificar uma linguagem um pouco mais formal).
# Premissa 2: Instituições participantes devem se posicionar como marcas
**Marcas são uma forma mais amigável, democrática e fácil para identificação das instituições participantes.**Uma marca de conglomerado pode estar correlacionada a mais de uma instituição participante, assim como uma instituição participante pode estar correlacionada a mais de uma marca.
## Relação Instituição x Marca
No exemplo a seguir, são apresentadas duas marcas distintas que compartilham dados do mesmo usuário. Em alguns casos, o usuário pode não reconhecer o nome institucional da instituição, identificando-a apenas pela marca.Além disso, uma instituição pode representar um grupo de participantes, no qual outras instituições estão associadas.Em uma situação fictícia, a marca **Wiscredi** também integra a instituição **GOOP**, relação que pode não ser evidente para o usuário. Ao apresentar o nome das marcas de forma associada às suas instituições participantes, o processo se torna mais claro e transparente.Outro exemplo ocorre quando a instituição participante utiliza uma marca de terceiro, não pertencente ao seu conglomerado, para identificação no Open Finance.Nessa situação, a instituição responsável pelo produto participante deve realizar o cadastro da marca no Diretório, podendo assim usar marca de terceiro para essa identificação, caso o produto seja reconhecido pelo usuário por meio dessa marca.Esse é o caso de *e-commerces* com iniciadores de pagamento *White Label* ou de serviços prestados no modelo *Bank as a Service.*A seguir, são apresentadas as deliberações definidas no âmbito do Grupo de Trabalho para o uso de marcas no Open Finance Brasil, considerando aspectos de identificação, reconhecimento pelo usuário e preservação do tom de voz das instituições ao longo das jornadas:
1. Ter pelo menos um canal digital que permita a autenticação e o compartilhamento de dados pelo usuário.
2. Estabelecer uma correlação dos dados objeto de compartilhamento contidos na marca. Esses dados precisam estar também relacionados aos seus canais digitais  (Ex: produtos comercializados no canal);
3. Definir o nome a ser utilizado pelas instituições participantes dentro do Diretório Central, considerando o posicionamento atual de cada instituição que é conhecido pelos usuários (utilizar nome da marca e não o nome de registro no BCB);
4. Apresentar seu nome por inteiro, sem abreviações, de forma a ser reconhecida pelo usuário e aderente a interfaces menores;
5. Declarar de forma transparente ao usuário a utilização dos dados pela marca e pelos participantes associados, por meio da finalidade de uso;
6. A marca da Instituição Transmissora e da Instituição Detentora de Conta será declarada no `Authorisation Server` , no campo `Customer Friendly Server Name` . Já a marca da Instituição Receptora e da Iniciadora de Transação de Pagamento será declarada no `Software Statement` no campo `Client Name` . Essas serão as marcas que aparecerão na jornada para o usuário. Para mais informações sobre esses campos, ver o Guia de Operação do Diretório Central.
 Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Requisitos para uso e disponibilização de logotipos

---
id: 1436287912
title: v.19.00.00 Requisitos para uso e disponibilização de logotipos
version: 1
modified: 2026-01-12T19:25:11.240Z
url: /spaces/OF/pages/1436287912/v.19.00.00+Requisitos+para+uso+e+disponibiliza+o+de+logotipos
---

Este conteúdo apresenta requisitos e recomendações para o uso dos logotipos das instituições nas Jornadas Open Finance e para sua disponibilização no Diretório de Participantes. Os logotipos cadastrados no Diretório são utilizados tanto no Portal do Cidadão quanto nas jornadas realizadas entre Instituições Receptoras, Transmissoras, Iniciadoras de Pagamentos e Detentoras de Conta.#F4F5F7
## Requisitos

1. Disponibilização de versão reduzida do logotipo: Disponibilizar versão reduzida do logotipo (por exemplo, símbolo ou favicon), priorizando a forma mais reconhecida pelos usuários.
2. Envio de logotipo em SVG: Enviar arquivo SVG contendo a área de proteção do logotipo da instituição, a fim de garantir leitura adequada e espaçamento correto. Formato de envio SVG: Dimensão mínima: 512px x 512px | Sem sombra Margem de segurança: 90px para cada uma das 4 bordas
3. Ajuste do logotipo à moldura: Garantir que o logotipo enviado toque as margens da moldura, conforme os exemplos apresentados a seguir.
4. Limite de tamanho do arquivo: Definir peso máximo do arquivo em 1 megabyte .
5. Logotipo em SVG: Garantir que os logotipos em formato SVG não incorporem imagens de outros formatos (como JPG ou PNG).
6. Disponibilização da URL do logotipo: Disponibilizar a URL do logotipo no Diretório Centralizado, conforme as orientações definidas no respectivo Guia de Operação.
7. Uso de transparência em SVG: Utilizar o recurso de transparência no SVG com atenção, a fim de não comprometer a visualização do logotipo em fundos coloridos, escuros ou em dark mode .
8. Integridade e proporção da marca: Manter a marca sem manipulações e preservar sua proporção original, independentemente do formato de apresentação (por exemplo, recorte circular ou quadrado).
#F4F5F7
## Recomendações

1. Aplicação de logotipos: Realizar a aplicação dos logotipos com tamanho mínimo de 48×48 px em telas de dispositivos móveis e 40×40px em telas web, em todas as jornadas.

## Exemplos para disponibilização do logotipo das instituições

### Aplicações corretas

1. Justificado em todas as margens.
2. Justificado verticalmente.
3. Justificado horizontalmente.
Aplicações corretas
### Aplicações incorretas

1. Ultrapassa todas as margens.
2. Não encosta em algum par de margens.
3. Ultrapassa um par de margens.
Aplicações incorretas Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Orientações transversais > v.19.00.00 Termos e condições de uso

---
id: 1436287984
title: v.19.00.00 Termos e condições de uso
version: 1
modified: 2026-01-12T19:25:12.764Z
url: /spaces/OF/pages/1436287984/v.19.00.00+Termos+e+condi+es+de+uso
---

Os Termos e Condições de Uso disponibilizados aos usuários/clientes (“Usuários”) devem contemplar um conjunto mínimo de tópicos, com o objetivo de assegurar transparência, clareza e adequada compreensão das condições aplicáveis ao uso dos produtos e serviços. As orientações a seguir aplicam-se às instituições participantes do Open Finance (“Instituições Participantes”), incluindo Receptoras de Dados, Iniciadoras de Transações de Pagamento ou aquelas que coletam consentimento dos usuários para o compartilhamento de proposta de crédito (“Instituições Receptoras”), conforme as determinações da Resolução Conjunta nº 01/2020 do Banco Central do Brasil e do Conselho Monetário Nacional.
# Termos e condições de uso para a jornada do usuário (Receptoras)
Os Termos e Condições de Uso devem ser elaborados pelas Instituições Receptoras conforme suas políticas e linguagem de relacionamento com os usuários, devendo conter, no mínimo, os tópicos a seguir:
- Visão geral do Open Finance - o que é, quem são os participantes, como funciona a Jornada do Consentimento e o compartilhamento de dados e serviços (oportunamente, de acordo com as fases de implementação do Open Finance), principais funções.
- Possibilidade de alteração dos termos e condições a qualquer momento pelas Instituições Receptoras.
- Fazer menção ou link para a Política de Privacidade da Instituição Receptora, que pode estar na própria API ou no site da Instituição Receptora.
- Descrição das possíveis finalidades de tratamento de dados pessoais objeto do consentimento que podem ser realizadas pela Receptora, bem como outras finalidades relacionadas ao Open Finance (inclusive em casos de resolução de eventuais disputas entre instituições participantes, atendimento do usuário no Service Desk etc.; esclarecendo que o tratamento de dados ocorrerá de acordo com os limites do consentimento do usuário).
- Descrição sobre possível uso de dados de terceiros que constam dos dados cadastrais e do histórico dos dados e serviços que serão compartilhados.
- Descrição da jornada do usuário, necessidade de identificação do usuário na Receptora e informação sobre o direcionamento do usuário aos ambientes das Instituições Transmissoras de Dados ou Detentoras de Contas para autenticação e confirmação do compartilhamento de dados e serviços ou Iniciação de Transação de Pagamento.
- Incluir a possibilidade de revogação do consentimento na Receptora e Transmissora de Dados, bem como na Detentora de Conta e na Iniciadora de Pagamento.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > Versões anteriores do Guia > v.19.00.00 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.00 Visão Geral (UX) > v.19.00.00 Sobre o Guia > v.19.00.00 Como ler o Guia de UX do Open Finance

---
id: 1436287660
title: v.19.00.00 Como ler o Guia de UX do Open Finance
version: 1
modified: 2026-01-12T19:25:07.093Z
url: /spaces/OF/pages/1436287660/v.19.00.00+Como+ler+o+Guia+de+UX+do+Open+Finance
---

A partir de 30 de outubro de 2025, o Guia de UX foi reorganizado para tornar a leitura mais objetiva e facilitar a consulta durante o desenho e a validação das jornadas.Agora, os cenários de uma mesma etapa estão agrupados por instituição, reunindo em um único bloco todos os cenários. Essa organização favorece uma leitura linear, evita repetições e permite a visualização consolidada de cada conjunto de cenários.Dessa forma, é possível localizar com mais facilidade os requisitos, recomendações e cenários de cada etapa. A estrutura aparece da seguinte maneira:
# Etapa 1: Nome da etapa (Jornada)
#F4F5F7
## Requisitos - Abreviação da instituição (Ex.: ITP)
**Cenário: Momento específico da etapa**
1. Requisito a ser seguido pela ITP. Requisito dependente do requisito 1. Requisito dependente do requisito 1.a.
#F4F5F7
## Recomendações - Abreviação da instituição (Ex.: ITP)
**Cenário: Momento específico da etapa**
1. Recomendação sugerida para a ITP. Recomendação dependente da recomendação 1. Recomendação dependente da recomendação 1.a.
Essa organização permite compreender rapidamente quais cenários se aplicam a cada instituição dentro de uma mesma etapa, além de facilitar a navegação direta para os conteúdos correspondentes.A mudança contribui para uma navegação mais fluida, possibilita comparações diretas entre instituições e agiliza a identificação de requisitos e recomendações em jornadas extensas.Por fim, as caixas de **Nota** e **Atenção** são utilizadas para complementar o conteúdo principal, destacando detalhes adicionais e pontos críticos que auxiliam na interpretação correta e na aplicação das orientações apresentadas.**Nota:**As notas possuem caráter informativo. **Atenção:**As informações possuem caráter de alerta e, se não observadas, podem comprometer o entendimento do conteúdo do Guia.Rodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Anexos (UX) > v.19.00.01 Jornada do Usuário e Consentimento na Versão Whitelabel de Pagamentos

---
id: 1477287096
title: v.19.00.01 Jornada do Usuário e Consentimento na Versão Whitelabel de Pagamentos
version: 1
modified: 2026-01-23T17:47:43.416Z
url: /spaces/OF/pages/1477287096/v.19.00.01+Jornada+do+Usu+rio+e+Consentimento+na+Vers+o+Whitelabel+de+Pagamentos
---

Na versão whitelabel, os requisitos da Jornada do Usuário definidos neste Guia de Experiência devem ser observados pelo parceiro do ITP. As informações apresentadas ao usuário devem indicar, de forma transparente, para quem o consentimento está sendo dado.Jornada de Iniciação de Pagamentos WhitelabelJornada de Iniciação de Pagamentos WhitelabelJornada de Iniciação de Pagamentos Whitelabel

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Anexos (UX) > v.19.00.01 Modalidades de Crédito

---
id: 1477287085
title: v.19.00.01 Modalidades de Crédito
version: 1
modified: 2026-01-23T17:47:43.119Z
url: /spaces/OF/pages/1477287085/v.19.00.01+Modalidades+de+Cr+dito
---

# Modalidades de operações de crédito apresentadas na Circular 4.015

## Jornada de Consentimento de Dados

| DOC 3040 | | REFERÊNCIA A ORIGEM DO CRÉDITO - CIRCULAR 4015 |
| DOMÍNIO | DESCRIÇÃO | SUB | DESCRIÇÃO (SUB) | SUGESTÃO DE SUBMODALIDADE |
| 01 | Adiantamentos e Empréstimos | 01 | Adiantamentos a depositantes | Adiantamentos a depositantes |
| 02 | Empréstimos | 02 | Crédito pessoal - com consignação em folha de pagamento. | Crédito pessoal - com consignação |
| | | 13 | Crédito pessoal - sem consignação em folha de pagamento. | Crédito pessoal - sem consignação |
| | | 11 | Home equity | Home equity |
| | | 12 | Microcrédito produtivo orientado | Microcrédito produtivo orientado |
| | | 13 | Cheque especial | Cheque especial |
| | | 14 | Conta garantida | Conta garantida |
| | | 15 | Capital de giro com prazo de vencimento de até 365 dias | Capital de giro |
| | | 16 | Capital de giro com prazo de vencimento superior a 365 dias | |
| | | 17 | Capital de giro com teto rotativo | |
| 03 | Direitos creditórios descontados | 01 | Desconto de duplicatas | Desconto de duplicatas |
| | | 02 | Desconto de cheques | Desconto de cheques |
| | | 03 | Antecipação de faturas de cartão de crédito | Antecipação de recebíveis de cartão de crédito |
| | | 98 | Outros direitos creditórios descontados | Desconto de nota promissória |
| | | 99 | Outros títulos descontados | Desconto de nota promissória |
| 04 | Financiamentos | 01 | Aquisição de bens - veículos automotores | Aquisições de bens móveis |
| | | 02 | Aquisição de bens - outros bens | |
| | | 03 | Microcréditos | Microcrédito produtivo orientado |
| 08 | Financiamentos | 01 | Custeiro | Rurais |
| | | 02 | Investimento | |
| | | 03 | Comercialização | Microcrédito produtivo orientado |
| | | 04 | Industrialização | Microcrédito produtivo orientado |
| 09 | | 01 | Financiamento habitacional - SFH | Sistema Financeiro da Habilitação (SFH) |
| | | 02 | Financiamento habitacional - exceto SFH | Sistema Financeiro Imobiliário (SFI) |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Anexos (UX) > v.19.00.01 Proto-personas e casos de uso

---
id: 1477287015
title: v.19.00.01 Proto-personas e casos de uso
version: 1
modified: 2026-01-23T17:47:41.822Z
url: /spaces/OF/pages/1477287015/v.19.00.01+Proto-personas+e+casos+de+uso
---

Esta página apresenta a abordagem adotada para a validação da Jornada de Compartilhamento de Dados, utilizando proto-personas e casos de uso como elementos para a análise. Ela tem como objetivo apoiar a visualização de diferentes perfis e cenários, além de auxiliar a validação das decisões relacionadas ao desenho da jornada.
# Etapas para Validação da Jornada

- Etapa 1: Definir a proto-persona
- Etapa 2 : Definir o caso de uso
- Etapa 3 : Validar a jornada
Etapas para a validação da jornada
# As proto-personas da Jornada de Compartilhamento de Dados
As proto-personas apresentadas neste guia foram elaboradas pelo GT-UX e refletem hipóteses construídas a partir da experiência dos participantes. Elas não esgotam todos os perfis possíveis e podem ser ajustadas pelas instituições conforme seus próprios contextos e necessidades.Para apoiar a análise da Jornada de Compartilhamento de Dados, essas proto-personas devem ser utilizadas em conjunto com os casos de uso, permitindo explorar possíveis situações, decisões e necessidades ao longo da jornada.#F4F5F7**Proto-persona**: recurso utilizado para explicitar e organizar hipóteses sobre os perfis envolvidos na jornada, a partir do conhecimento prévio e das experiências acumuladas de equipes técnicas e de produtos, sem coleta de dados primários. Seu uso permite alinhar entendimentos iniciais sobre comportamentos, necessidades e objetivos dos usuários.As proto-personas definidas são:
- Maria , usuária PF: múltiplos acessos
- Mônica , usuária PF: múltiplos acessos
- Eduardo , usuário PF: poucos acessos
- João , usuário PF: poucos acessos
**Nota** As referências a poucos acessos e múltiplos acessos indicam a frequência de uso de canais digitais pelas proto-personas no contexto da jornada.Proto-personas da Jornada de Compartilhamento de Dados
# Os Casos de Uso
A Jornada de Compartilhamento de Dados pode ocorrer em diferentes cenários que conduzem ao objetivo comum de utilizar a plataforma de Open Finance para o compartilhamento de dados. Esses cenários são denominados casos de uso.Em conjunto com as proto-personas, os casos de uso fornecem contexto e apoiam a compreensão das situações mais prováveis que levam o usuário a percorrer a jornada. Assim como as proto-personas, esses casos de uso não esgotam todas as possibilidades.Os casos de uso definidos são:
- Agregação de informações financeiras Intenção do usuário de agregar contas mantidas em diferentes instituições, incluindo a instituição principal.
- Contratação de produtos com relacionamentos iguais e esquecimento de senha na Instituição Transmissora Intenção do usuário de compartilhar informações de produtos do mesmo tipo (por exemplo, duas contas correntes) após esquecer a senha do canal eletrônico da Instituição Transmissora.
- Abertura de conta com dados cadastrais (básico) Intenção do usuário de compartilhar dados cadastrais para abertura de conta.
- Contratação de produtos com relacionamentos diferentes Intenção do usuário de compartilhar informações de produtos distintos (por exemplo, conta corrente e cartão de crédito).
- Cancelamento da jornada na etapa de consentimento Intenção do usuário de interromper a jornada na etapa de consentimento e cancelar o compartilhamento de dados.

# Combinação entre proto-personas e casos de uso

| Proto-persona | Maria Usuária PF Múltiplos acessos | Mônica Usuária PJ Múltiplos acessos | Eduardo Usuário PJ Poucos acessos | João Usuário PF Poucos acessos |
| --- | --- | --- | --- | --- |
| Casos de uso | Agregação de informação financeira (várias contas em Instituições diferentes e uma na sua instituição principal). | Abertura de conta com dados cadastrais (básico). | Contratação de produtos com relacionamentos iguais (como duas contas correntes) e esquecimento de senha no canal eletrônico da Transmissora. | Contratação de produtos com relacionamentos diferentes (conta corrente x cartão de crédito) nas instituições. |
| Características | 32 anos, graduada, administradora, e está iniciando uma família. | 43 anos, pós-graduada e diretora financeira de uma empresa de médio porte. | 26 anos, autônomo com ensino técnico, atua no limite da MEI e complementa a renda dos pais. | 63 anos, aposentado, casado e tem 2 filhos adultos. |
| Necessidades | Está em processo de maturidade de sua vida financeira, busca melhores oportunidades digitais no mercado e utilizaria o Open Finance para aprimorar produtos e serviços. | Está buscando alternativas eficientes para a saúde financeira do negócio e sua expansão. Utilizaria o Open Finance para acessar melhores opções de produtos e otimizar a gestão financeira. | Tem a expectativa de se resolver nos canais digitais, porém, necessita de auxílio para resolver os assuntos financeiros de seu negócio. Utilizaria o Open Finance para ter melhores condições de alavancar seu negócio. | Tem poucos recursos financeiros. Procura uma solução para um eventual imprevisto ou um objetivo sem planejamento. Utilizaria o Open Finance para ter uma visão completa da sua saúde financeira. |
| Comportamento | Busca sempre se atualizar quanto a novos acontecimentos. É independente e organizada. Utiliza os serviços providos pela sua instituição para seu planejamento. | Os serviços financeiros da sua instituição são essenciais para a operação do negócio. Utiliza frequentemente todos os canais disponíveis e demanda atendimento consultivo. | Iniciou sua relação financeira com uma instituição por necessidade profissional. Conhece e utiliza os serviços digitais, porém tem baixas expectativas quanto à sua experiência. | Utiliza as instituições financeiras por necessidade, prioritariamente por canais presenciais. Depende de seu gerente ou de familiares para realizar suas operações financeiras. |
| Desafio | Unificar os pagamentos e transferências em uma única instituição ao utilizar os saldos das suas contas de outras instituições. | Otimizar os processos de pagamento dentro da sua empresa por meio desse serviço. | Realizar compras de produtos para sua empresa em canais digitais, utilizando diretamente o saldo de sua conta. | Realizar sua primeira compra em um canal digital utilizando diretamente do saldo de sua conta. |

## Maria
**“Se você quer algo bem feito, faça você mesmo.”**
- Usuária PF
- Múltiplos acessos
- Idade : 32 anos
- Profissão : administradora
- Escolaridade : superior completo
- Renda : R$7.000,00/mês
- Estado civil : casada
- Dependentes diretos : filho pequeno
- Níveis de acesso : não tem dependentes na relação financeira com a instituição.
- Relação com instituições : uso distribuído entre várias instituições financeiras.

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| Maria |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Alta | Média | Médio |
| Encara as soluções de serviços financeiros como uma ferramenta de planejamento e um meio para identificar novas oportunidades (perfil investidora). | Utiliza soluções financeiras frequentemente em mais de um canal, prioritariamente no canal digital (mobile banking e internet banking). | Se mantém antenada quanto a novos acontecimentos. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de Maria
### Outras informações

- Momento de vida : em processo de maturidade da vida financeira.
- Expectativa com a Instituição (por quê?): busca boas oportunidades de mercado com atendimento rápido, fácil e digital.
- Relacionamento com sua instituição (como?): contratação de um novo produto em uma nova instituição (operações de crédito, contas etc.).
- Principais motivos de adoção do Open Finance : complementar sua relação financeira com as instituições para aprimorar seus produtos e serviços.
- Principais motivos para usar a Iniciação de Transação de Pagamento : unificar os pagamentos e transferências em uma única instituição ao utilizar os saldos das suas contas de outras instituições.
- Inseguranças : uso indevido de dados, vazamento de dados e fraudes.

## Mônica
**“Sozinha você vai mais rápido, junto você vai mais longe.”**
- Usuária PJ
- Múltiplos acessos
- Idade : 43 anos
- Profissão : Diretora Financeira
- Escolaridade : Pós graduação completa
- Renda: R$ 12.000.000,00/ano
- Estado civil : N/A
- Dependentes diretos : N/A
- Níveis de acesso : não tem acesso para sócios, administradores e operadores
- Relação com instituições : distribuída entre várias instituições financeiras.

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| Mônica |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Alta | Alta | Alto |
| Os serviços financeiros de sua instituição são essenciais para a operação do negócio (perfil misto). | Utiliza praticamente todos os canais disponíveis frequentemente, com preferência por canais digitais quando mais conveniente (internet banking). | Irá demandar um atendimento consultivo de sua instituição. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de Mônica
### Outras informações

- Momento de vida : está buscando alternativas eficientes para a saúde financeira do negócio.
- Expectativa com a Instituição (por quê?): sustentabilidade do negócio.
- Relacionamento com sua instituição (como?): expansão do negócio por meio de produtos de linhas de crédito ou investimentos.
- Principais motivos de adoção do Open Finance : ter uma visão mais global do setor financeiro para buscar melhores opções de produtos e otimização da gestão financeira da empresa.
- Principais motivos para usar a Iniciação de Transação de Pagamento : otimizar os processos de pagamento dentro da sua empresa por meio desse serviço.
- Inseguranças : não saber o que está sendo compartilhado, não saber como os dados estão sendo utilizados, desrespeito aos níveis/perfis de acesso da empresa, vazamento de credenciais e sua utilização nesse ambiente e vazamento de informações financeiras da empresa.

## Eduardo
**“Deus ajuda quem cedo madruga”**
- Usuário PJ
- Poucos acessos
- Idade : 26 anos
- Profissão : mecânico autônomo
- Escolaridade : ensino técnico
- Renda : R$ 80.000,00/ano
- Estado civil : N/A
- Dependentes diretos : complementa a renda dos pais
- Níveis de acesso : não tem dependentes na relação financeira.
- Relação com instituições : concentrado em uma única instituição financeira.

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| Eduardo |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Média | Média | Médio |
| Iniciou sua relação financeira com uma Instituição por necessidade profissional (emissão de nota MEI), perfil tomador. | Tem experiência em serviços digitais diversos e não tem expectativa quanto à sua experiência digital com uma instituição financeira. | Adquiriu seu conhecimento financeiro com base em sua vivência, relação com mídias sociais e familiares. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de Eduardo
### Outras informações

- Momento de vida : recentemente demitido e começou a empreender.
- Expectativa com a Instituição (por quê?): necessita de auxílio para resolver os assuntos financeiros de seu negócio.
- Relacionamento com sua instituição (como?): conta corrente para conduzir seu pequeno negócio.
- Principais motivos de adoção do Open Finance : compartilhar suas informações financeiras para que tenha melhores condições de alavancar seu negócio:  “O que eu ganho com isso?”.
- Principais motivos para usar a Iniciação de Transação de Pagamento : realizar compras de produtos para sua empresa em canais digitais utilizando diretamente do saldo de sua conta.
- Inseguranças : qual o custo, não saber como os dados estão sendo utilizados e “Meu dinheiro vai ser transferido?”

## João
**“Melhor um pássaro na mão do que dois voando.”**
- Usuário PF
- Poucos acessos
- Idade : 63 anos
- Profissão : aposentado
- Escolaridade : ensino médio completo
- Renda : R$ 1.045,00/mês
- Estado civil : casado
- Dependentes diretos : dois filhos adultos
- Níveis de acesso : não tem conta conjunta com o cônjuge.
- Relação com instituições : concentrado em uma única instituição financeira

### Adoção financeira X Adoção tecnológica X Conhecimento financeiro

| João |
| --- |
| Adoção financeira | Adoção tecnológica | Conhecimento financeiro |
| Baixa | Baixa | Baixo |
| Utiliza as instituições financeiras apenas por necessidade (recebimento de aposentadoria, etc.) perfil tomador. | Utiliza pouco os serviços de canais digitais, prioritariamente prefere atendimento presencial (relação com o gerente, caixa físico, etc.). | Depende de recomendações do gerente ou familiares para realizar suas operações financeiras. |
Níveis de adoção financeira, adoção à tecnologia e conhecimento financeiro de João
### Outras informações

- Momento de vida : atualmente tem poucos recursos financeiros para pequenos projetos/desafios pessoais.
- Expectativa com a Instituição (por quê?): procura uma solução para eventual imprevisto financeiro ou um objetivo sem planejamento, buscando informações com familiares e a solução com sua instituição financeira.
- Relacionamento com sua instituição (como?): renegociação de um crédito, ou contratação de um crédito consignado.
- Principais motivos de adoção do Open Finance : ter uma visão completa de sua saúde financeira, possibilitando melhores condições de adoção ao Open Finance negociação de produtos e serviços.
- Principais motivos para usar a Iniciação de Transação de Pagamento : realizar sua primeira compra em um canal digital utilizando diretamente o saldo de sua conta.
- Inseguranças : tem receio de inserir senhas em canais digitais e golpes.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Anexos (UX) > v.19.00.01 Tabela de Dados

---
id: 1477287074
title: v.19.00.01 Tabela de Dados
version: 1
modified: 2026-01-23T17:47:42.823Z
url: /spaces/OF/pages/1477287074/v.19.00.01+Tabela+de+Dados
---

Tabela de dados em sua versão resumida, para facilitar acesso aos times técnicos.
# Jornada de Compartilhamento de Dados

## Dados cadastrais

### Agrupamentos PF

| Dados cadastrais | Nome completo e nome social, endereço completo, CPF, passaporte, telefone, e-mail, documento de identificação, filiação, data de nascimento, estado civil, sexo, nacionalidade, residência brasileira, documento estrangeiro. |
| Informações complementares | Renda, profissão, patrimônio, informações de cônjuge, produtos contratados, representantes, informações do empregador de conta salário e portabilidade. |

### Agrupamentos PJ

| Dados cadastrais | Razão social, endereço completo, CNPJ, número de registro no país de origem, telefone, e-mail, data de abertura da empresa, informações de sócios e administradores. |
| Informações complementares | Faturamento, valor patrimonial, ramo de atuação, data de início de relacionamento, produtos contratados, representantes. |

## Dados da conta

| Saldo | Informações da conta, saldo disponível, saldo bloqueado, outros saldos. |
| Limites | Informações da conta, limite utilizado, limite contratado de cheque especial. |
| Extratos | Informações da conta, detalhes da transação. |

## Dados do Cartão de Crédito

| Limite | Informações do cartão, informações sobre o limite do cartão, limite total, limite utilizado, limite disponível, limite por tipo de crédito. |
| Transações | Informações do cartão, identificação de transação, valor da transação, datas, identificação do estabelecimento. |
| Faturas | Informações do cartão, bandeira do cartão, informações da fatura, encargos e formas de pagamento. |

## Dados de Operação de Crédito

| Contratos de Crédito | Dados do contrato, data da contratação, data do recebimento do crédito, valor do crédito, data de vencimento, datas de pagamento das parcelas, período recorrente dos pagamentos, datas de vencimento de cada parcela, data de vencimento da primeira parcela, saldo devedor, prazo total, prazo remanescente, quantidade de prestações, prestações, taxas de juros, Custo Efetivo Total, sistema de amortização, tarifas, sigla identificadora da tarifa, valor da tarifa, moeda, data da cobrança de tarifa, encargos, garantias, número do documento da Instituição consignante. |

## Investimentos

| Operações de Investimentos | “As operações referem-se a contratos de renda fixa, renda variável, tesouro direto e fundos de investimentos. São informações como: identificação do produto, informações de remuneração, data de emissão, vencimento, aquisição, data fim da carência, saldo bloqueado, líquido e bruto, quantidade de títulos, preço unitário, impostos provisionados, multa e mora, indexadores, código ISIN, Classificação ANBIMA, Classe e Subclasse.” |

### Fundos de Investimento

| Identificação do Produto | Informações de identificação do produto, Código ISIN, Classificação ANBIMA, Classe e Subclasse. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade de cotas , valor bruto da cota, impostos provisionados. |
| Movimentações | Identificação da movimentação, data da conversão, quantidade de cotas movimentada, valor da cota, valor da movimentação, valor líquido e bruto da movimentação e impostos. |

### Renda Fixa Bancária

| Identificação do Produto | Informações de identificação do produto, informações de remuneração do produto, data de vencimento, aquisição, data fim carência. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade título, preço unitário, impostos provisionados. |
| Movimentações | Identificação da movimentação, Preços unitário e quantidade movimentados, valores liquido e bruto da movimentação, impostos e indexadores. |

### Renda Fixa Crédito Privado

| Identificação do Produto | Informações de identificação do produto, informações de remuneração do produto, data de vencimento, aquisição, data fim carência, pagamento de cupom. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade título, preço unitário, impostos provisionados, multa e mora. |
| Movimentações | Identificação da movimentação, preços unitários e quantidade movimentados, valores liquido e bruto da movimentação, impostos e indexadores. |
| Contratos de Crédito | Dados do contrato, data da contratação, data do recebimento do crédito, valor do crédito, data de vencimento, datas de pagamento das parcelas, período recorrente dos pagamentos, datas de vencimento de cada parcela, data de vencimento da primeira parcela, saldo devedor, prazo total, prazo remanescente, quantidade de prestações, prestações, taxas de juros, Custo Efetivo Total, sistema de amortização, tarifas, sigla identificadora da tarifa, valor da tarifa, moeda, data da cobrança de tarifa, encargos, garantias, número do documento da Instituição consignante. |

### Renda Variável

| Identificação do Produto | Informações de identificação do produto (código ISIN e ticker). |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade, preço unitário, impostos provisionados, multa e mora. |
| Movimentações | Identificação da movimentação, Preços unitário e quantidade movimentada, valor da movimentação, data da movimentação. |
| Detalhes da Nota de Negociação | Número da nota, valor monetário das taxas aplicáveis, emolumentos, impostos e valor líquido da nota. |

### Tesouro Direto

| Identificação do Produto | Informações de identificação do produto, informações de remuneração do produto, data de vencimento, aquisição, data fim carência, pagamento de cupom. |
| Posição do Usuário | Saldo bloqueado, líquido e bruto, quantidade título, preço unitário, impostos provisionados, multa e mora. |
| Movimentações | Identificação da movimentação, preços unitários e quantidade movimentados, valores liquido e bruto da movimentação, impostos e indexadores. |

## Operações de Câmbio

| Operações de Câmbio | Identificação da operação, data do fechamento do contrato de câmbio, data em que a operação (compra ou venda) está prevista para ser liquidada, valor da taxa de câmbio aplicada ao contrato, valor do saldo da operação a liquidar, percentual do valor concedido ao usuário antecipadamente, natureza fato do fechamento da operação e relação de vínculo entre o usuário e o pagador/Recebedor no exterior. |

# Jornada de Iniciação de Pagamentos

| Tipo de pagamento | Informações na Iniciadora* | Informações na Detentora |
| --- | --- | --- |
| Todos Tipos de Pagamento | Forma de pagamento. Valor da tarifa na Iniciadora (se houver). Valor do pagamento:  – Digitável ou para visualização, conforme o caso;  – Se necessário, desdobrar valores de juros e multa. Data do pagamento:  – Adaptável para agendamento e recorrente. Descrição/Observação/Finalidade (preenchimento opcional, sendo vedada a apresentação de campo denominado “Descrição” nas transações Pix iniciadas por QR Code)”data de encerramento e/ou número de recorrências. Periodicidade da recorrência. | Forma de pagamento. Valor da tarifa na Detentora (se houver). Valor do pagamento:  – Se necessário, desdobrar valores de juros e multa. Data do pagamento:  – Adaptável para agendamento e recorrente. Informações da conta do pagador a ser debitada, como os dados da agência e conta. Data de encerramento e/ou número de recorrências. Periodicidade da recorrência. |
| Pix Inserção Manual | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Instituição (apenas o nome). Agência sem dígito. Conta com dígito. Descrição (preenchimento opcional). | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Instituição (apenas o nome). Agência sem dígito. Conta com dígito. |
| Pix Por Chave | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Chave Pix (CPF/CNPJ, e-mail, ou celular). Descrição (preenchimento opcional. | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. Chave Pix (CPF/CNPJ, e-mail, ou celular). |
| Pix Direto pelo Iniciador | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. | Nome do recebedor. CPF do recebedor mascarado ou CNP. |
| Pix QR Code e Copia e Cola | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. QR Code (captura / copia e cola). Dados necessários conforme tipo de QR Code:  – De acordo com os requisitos mínimos especificados nos documentos que regulamentam o arranjo Pix. Mensagem Pix. | Nome do recebedor. CPF do recebedor mascarado ou CNPJ. |
***Informações na Iniciadora**: dados mínimos (obrigatórios) que devem ser apresentados ao usuário. Outros dados que possam ajudar na experiência, seguindo as diretrizes, podem ser apresentados.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Compartilhamento de Dados > v.19.00.01 Casos de erro (Dados)

---
id: 1477282378
title: v.19.00.01 Casos de erro (Dados)
version: 1
modified: 2026-01-23T17:46:31.781Z
url: /spaces/OF/pages/1477282378/v.19.00.01+Casos+de+erro+Dados
---

## A mensagem de erro deve:
**Comunicar** o erro**com clareza**, **explicar** o que ocasionou o erro com **linguagem simples** e **fornecer orientação** e **opções de ação** para que o usuário consiga continuar.Boas práticas de experiência considerando os pilares:
- O que houve com o usuário?
- O que ocasionou o erro?
- Orientações ao usuário.
- Ação necessária para prosseguir.
**Exemplo:**
Um navegador de internet não foi localizado para redirecionar e autenticar o usuário na Transmissora.
- O que houve? Usuário não pôde ser redirecionado.
- O que ocasionou o erro? O navegador de internet não foi encontrado no dispositivo do usuário.
- Orientação ao usuário Verificar se existe um navegador instalado.
- Ações para prosseguir Tentar novamente.
- Mensagem de erro Desculpe, não foi possível direcioná-lo. Não encontramos um navegador de internet em seu celular. Verifique se seu dispositivo tem o navegador, pois precisamos dele para concluir seu compartilhamento.

| Erro | Etapa | Orientação para o usuário | Ação para prosseguir | Observações |
| --- | --- | --- | --- | --- |
| Não encontra um destino Aplicativo ou navegador - dependendo do caminho escolhido pela Transmissora | Direcionamento IT > IR | Avisar que o navegador / aplicativo não está instalado e recomendar a instalação. | Preferencialmente, direcionar para instalação do aplicativo. Caso não seja possível, recomendar instalação do app ou navegador e indicar nova tentativa. | Antes de exibir qualquer erro para o usuário, todos os caminhos possíveis devem ser tentados. Por exemplo: Se o usuário não tem o aplicativo da Transmissora e esta aceita direcionar para o navegador, este caminho deve ser feito antes de mostrar a mensagem de erro. Incluir reforço de que se trata de caso para a jornada de redirecionamento. |
| Time out | Direcionamento IT > IR | Indicar que o fluxo foi interrompido pois o tempo limite para se autenticar foi atingido. | Na Transmissora: cancelar o fluxo e redirecionar para a Receptora.   Na Receptora: informar que não foi possível concluir o compartilhamento. Orientar o usuário a tentar novamente. | |
| O fluxo é interrompido e usuário volta para Receptora devido à indisponibilidade do sistema | Direcionamento IT > IR | Indicar que ocorreu um erro de comunicação com a Instituição Transmissora e sugerir que tente novamente mais tarde. | Recomendar que tente novamente mais tarde. | |
| Transmissora ter parte ou nenhum dos dados obrigatórios ou não selecionados da Receptora | Confirmação e Efetivação | Fica a cargo da Receptora como continuar o fluxo. | Ação detalhada ao lado. | Para a Transmissora Dados parciais: se houver qualquer dado que possa ser compartilhado, a Instituição Transmissora deve permitir que o usuário conclua a confirmação do compartilhamento e seja redirecionado para a Receptora, disponibilizando todos os dados disponíveis. Isto se deve à Instituição Transmissora não saber a finalidade escolhida pelo usuário na Receptora e nem mesmo quais dados são necessários ou opcionais para aquela finalidade. Logo, não deverá orientar o usuário sobre seguir ou não com o compartilhamento dos dados. Nenhum dado: caso o usuário não tenha NENHUM dado solicitado na Receptora, a Instituição Transmissora poderá enviar mensagem ao usuário e orientá-lo a voltar à Receptora ou seguir com a jornada mesmo sem nenhum dado. Para a Receptora Caberá à Receptora analisar quais dados foram retornados e avaliar se informará ao usuário sobre a inexistência total ou parcial dos dados, seguindo ou não com a oferta do produto ou serviço. Deve-se deixar claro que a Transmissora compartilhou todos os dados possíveis, porém o usuário não tinha os dados. |
| Casos em que o usuário não tem poderes suficientes na jornada PJ | Confirmação | Explicar para o usuário que sua alçada não é suficiente para a ação desejada. Informar claramente sobre a necessidade de revisão dos poderes. | Dar clareza sobre qual ação é necessária para o usuário seguir em frente.  Ter indicação do canal em que o usuário possa buscar informações. | Exemplos SEM detalhes do erro Não foi possível realizar o compartilhamento de dados. Erro na solicitação [ERR-103] A conta informada não existe ou não está vinculada à chave J da autenticação. Exemplos COM detalhes do erro Verificamos que você não tem os poderes necessários para compartilhar os dados da sua empresa com outras instituições. Solicite sua permissão: Para que você possa compartilhar os dados da sua empresa com outros participantes do Open Finance, é preciso que você apresente os documentos com os poderes necessários do representantes legais e/ou procuradores. |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Compartilhamento de Dados > v.19.00.01 Jornada Básica de Compartilhamento de Dados > v.19.00.01 Requisitos e Recomendações - Jornada Básica de Compartilhamento de Dados

---
id: 1477281743
title: v.19.00.01 Requisitos e Recomendações - Jornada Básica de Compartilhamento de Dados
version: 4
modified: 2026-02-03T20:48:57.517Z
url: /spaces/OF/pages/1477281743/v.19.00.01+Requisitos+e+Recomenda+es+-+Jornada+B+sica+de+Compartilhamento+de+Dados
---

# Etapa 1: Consentimento
Nesta etapa, o usuário inicia o compartilhamento de dados no ambiente da Instituição Receptora (IR), fornecendo as informações mínimas de identificação e compreendendo a finalidade do uso dos dados. O usuário também seleciona a instituição de origem dos dados, define quais categorias e agrupamentos serão compartilhados, ajusta o prazo da autorização e revisa os termos antes de prosseguir com a jornada.A Instituição Receptora deve conduzir essa etapa de forma clara, transparente e orientada à finalidade informada, garantindo a correta identificação do usuário, a apresentação adequada das opções de compartilhamento e a visibilidade dos próximos passos.DC - etapa 1#F4F5F7
## Requisitos - IR
**Cenário: Início do compartilhamento**
1. Coleta de informações mínimas do usuário: coletar e validar as informações mínimas necessárias para identificação do usuário, conforme o tipo de cadastro e o segmento. Usuário com cadastro prévio na Instituição Receptora de Dados: Validar o CPF. Validar também o CNPJ nos casos de segmento PJ. Usuário sem cadastro prévio na Instituição Receptora de Dados: Coletar, no mínimo, o CPF nos casos de segmento PF. Coletar o CPF e o CNPJ nos casos de segmento PJ. Coletar outras informações de identificação consideradas necessárias pela Instituição Receptora de Dados para prosseguir com a jornada ou informações exigidas pela regulação vigente.
2. Objetivo do compartilhamento: apresentar ao usuário a finalidade de uso dos dados forma clara, seja na tela de início da jornada ou na tela de solicitação do consentimento.
3. Ferramenta de busca : disponibilizar ferramenta de busca para seleção da instituição de origem dos dados, com funcionamento baseado em marcas. Permitir que o usuário busque tanto pela marca da instituição quanto por um participante associado, exibindo corretamente a marca correspondente nos resultados. Exigir que a seleção final seja feita pela marca da instituição, e não pelo nome do participante associado. Exibir apenas marcas adequadas ao tipo de público identificado (PF ou PJ). Garantir que cada marca seja exibida uma única vez, mesmo que existam múltiplos registros para ela no Diretório de Participantes.
Compartilhamento de Dados - Início do compartilhamento**Cenário: Seleção de dados**
1. Exibição dos dados de compartilhamento : disponibilizar a visualização e a configuração, quando aplicável, dos dados objeto do compartilhamento, conforme as condições a seguir. Exibir as categorias de dados na tela principal da jornada, ocultando os agrupamentos, mas permitindo que eles permaneçam acessíveis a partir da interação dos usuários. Ex.: menu agrupado ou botão de mais detalhes. Discriminar categorias obrigatórias e opcionais para dados ou agrupamentos, observando que a obrigatoriedade só é permitida em casos de relação direta com a finalidade de uso. Especificar o motivo da obrigatoriedade, quando houver dados obrigatórios. Permitir a remoção ou inclusão de categorias e agrupamentos de dados opcionais no consentimento. Em cenários de transações de crédito, investimento e/ou câmbio, informar ao usuário que novas operações ou contratações dessas categorias terão seus dados automaticamente incorporados ao consentimento vigente.
Compartilhamento de Dados - Seleção de dados**Cenário: Prazo de consentimento**
1. Prazo da autorização: exibir um campo que indique a duração ou o prazo do compartilhamento de dados, considerando as condições a seguir. Preencher o campo de prazo por padrão, conforme entender mais adequado ao caso de uso. Disponibilizar ao usuário a possibilidade de alterar o prazo para, no mínimo, uma opção adicional além do prazo padrão. No caso de prazo indeterminado, identificar para o usuário como “Indeterminado” ou termo similar.
**Nota**Caso os dados compartilhados sejam informações pontuais ou de prazo curto (por exemplo: dados para abertura de conta, contratação de empréstimo etc.) ou como um consentimento de compartilhamento pontual, que não necessita de prazo baseado em meses, é indicado que sejam apresentados prazos proporcionais (por exemplo: horas, dias ou semanas)Compartilhamento de Dados - Prazo de consentimento**Cenário: Informações da solicitação**
1. Termos e Condições : apresentar os termos de uso de forma clara. Informar que, ao continuar, o usuário está concordando com os Termos e Condições.
2. Forma de aceite : não utilizar opt-in para aceite dos Termos e Condições.
3. Próximos passos : dar visibilidade sobre as próximas etapas até a conclusão da jornada.
4. Termos padronizados: utilizar, ao longo de toda a jornada, os termos definidos nas Tabelas de Dados para as categorias de dados, seus agrupamentos e respectivas descrições.
**Nota**Os requisitos não exigem a apresentação de uma tela específica para checkout do usuário antes do redirecionamento para a Instituição Receptora de Dados. Fica a critério da Instituição Receptora de Dados incluir ou não uma tela de checkout para uma melhor experiência ou para auxiliar no cumprimento dos requisitos.Compartilhamento de Dados - Informações da solicitação#F4F5F7
## Recomendações - IR
**Cenário: Informações da solicitação**
1. Seleção inicial de dados : pré-selecionar os agrupamentos de dados correlacionados com a finalidade, permitindo que o usuário retire a seleção dos dados opcionais.
2. Ação simultânea para múltiplos agrupamentos : possibilitar marcar ou desmarcar múltiplos agrupamentos em uma só ação.
3. Visualização simplificada dos dados : possibilitar que o usuário visualize, de forma clara e intuitiva, os dados que compõem cada agrupamento.
Compartilhamento de Dados - Informações da Solicitação
1. Informações complementares: nos casos em que o usuário não possua cadastro prévio, além dos campos obrigatórios, solicitar informações adicionais necessárias para o seguimento da jornada.
2. Benefícios no compartilhamento de dados opcionais : informar ao usuário os benefícios de compartilhar dados opcionais, quando houver dados opcionais.
3. Vocabulário simples : reunir vários campos em um termo simples. Ex.: resumir a listagem de CEP, endereço, número, complemento, cidade, UF e país como “Endereço completo”.
4. Uso de linguagem simplificada nos Termos para o Usuário: simplificar a linguagem dos “Termos para o Usuário” definidos no Glossário de Experiência, evitando repetições.
5. Gratuidade : quando aplicável, informar sobre a gratuidade da operação de forma clara e sem fricções que atrapalhem a jornada.
6. Alerta de escopo de consentimento duplicado : informar o usuário quando o escopo de dados de um novo consentimento for idêntico a outro já existente, para impedir a duplicação desnecessária e facilitar a gestão.
7. Prevenção de interrupções : alertar sobre a possibilidade de falha na jornada em dispositivos com o recurso de ocultação de aplicativos ativado, orientando o usuário a desativar esse recurso se necessário.
Compartilhamento de Dados - Informação da solicitação
# Etapa 2: Direcionamento
Nesta etapa, o usuário é direcionado do ambiente da IR para o ambiente da IT a fim de confirmar o compartilhamento dos dados. O usuário acompanha o direcionamento por meio de uma tela informativa, sem a necessidade de realizar ações adicionais, tendo visibilidade de que o processo é seguro e de que a jornada continuará no ambiente da instituição de origem dos dados.A Instituição Receptora deve informar de forma clara que o direcionamento está em andamento e assegurar que a transição ocorra sem fricções. É recomendável que a IR permita a retomada da jornada em caso de interrupção. Já a Instituição Transmissora deve conduzir o direcionamento para um canal digital seguro, priorizando o uso de aplicativo quando disponível e garantindo uma experiência contínua e confiável.DC - etapa 2#F4F5F7
## Requisitos - IT
**Cenário: Seleção de métodos de direcionamento**
1. Ordem de preferência do direcionamento : levar o usuário para um canal digital seguro, seguindo a ordem de preferência descrita abaixo.   Direcionar para o aplicativo da IT ( Hybrid Flow ). Direcionar para a loja de aplicativos, caso aplicativo da IT não esteja instalado. Direcionar para o ambiente browser da IT ( Hybrid Flow ) ou para a loja de aplicativo. Direcionar para o aplicativo da IT com Hand-off ( Hybrid Flow com Hand-off ). Direcionar para o aplicativo da IT (Hybrid Flow com Hand-off ) ou para o ambiente em desktop da IT ( Hybrid Flow ).
Compartilhamento de dados - Seleção do método de direcionamento#F4F5F7
## Requisitos - IR
**Cenário: Tela de transição**
1. Informações sobre o direcionamento : durante o direcionamento, exibir uma tela informativa contendo, no mínimo, as informações abaixo. Indicação de que o direcionamento está em andamento.   Indicação de que o direcionamento é seguro.
2. Vedação de ação adicional no direcionamento: não exigir qualquer ação adicional do usuário para confirmar o direcionamento, uma vez que a etapa possui caráter exclusivamente informativo.
3. Direcionamento entre dispositivos móveis : em dispositivo móvel, direcionar o usuário diretamente para o aplicativo da IT, sem passar por navegadores intermediários.
Compartilhamento de Dados - Tela de transição#F4F5F7
## Recomendações - IR
**Cenário: Tela de transição**
1. Interrupção da jornada : permitir que, caso a jornada seja interrompida nesta etapa, o usuário consiga retomá-la facilmente através dos canais digitais da instituição.

# Etapa 3: Autenticação
Nesta etapa, o usuário acessa o ambiente da Instituição Transmissora e realiza a autenticação por meio dos canais digitais já utilizados pela instituição. A Instituição Transmissora deve solicitar a autenticação conforme seus padrões usuais, sem exigir etapas adicionais ou métodos mais rigorosos do que os aplicados em outras operações. Também é sua responsabilidade validar a titularidade do usuário autenticado e, em caso de divergência em relação à solicitação de consentimento, interromper a jornada de forma imediata, apresentar mensagem de erro clara e orientar sobre os procedimentos disponíveis para resolução.DC - etapa 3#F4F5F7
## Requisitos - IT
**Cenário: Login**
1. Para o usuário se autenticar, é necessário que ele tenha acesso a um canal digital da Instituição Transmissora de Dados.
2. Solicitação de autenticação: solicitar a autenticação do usuário conforme os padrões já definidos pela própria IT para operações fora do Open Finance, em conformidade com a regulação vigente.
**Manutenção do fluxo padrão:** Não exigir etapas adicionais ou utilizar métodos mais rigorosos de autenticação não contemplados em seu canal digital a fim de desincentivar a transação, conforme a regulação vigente.
1. Direcionamento entre dispositivos móveis : em dispositivo móvel, não exigir navegadores intermediários no direcionamento do usuário que vem do aplicativo da IR.
Compartilhamento de Dados - LoginType or paste something here to turn it into an excerpt.**Cenário: Validação da titularidade**
1. No ambiente logado, é necessário fazer a validação da titularidade do usuário, com objetivo de garantir que a solicitação e a confirmação de compartilhamento estejam sendo realizadas pelo mesmo titular.
2. Validação de titularidade : caso a titularidade validada após a autenticação seja diferente daquela associada à solicitação, observar as ações abaixo. Interromper a jornada imediatamente e não exibir a tela de resumo da confirmação nem os dados da autorização.  Apresentar uma mensagem de erro clara sobre o motivo da interrupção.  Informar quais os procedimentos disponíveis para resolução do problema.
Compartilhamento de Dados - Validação da titularidade 
# Etapa 4: Confirmação
Nesta etapa, o usuário confirma, no ambiente da Instituição Transmissora, o compartilhamento dos dados conforme a solicitação realizada anteriormente na Instituição Receptora. Ele revisa as informações do consentimento, verifica os dados que serão compartilhados, a instituição destinatária e o prazo da autorização antes de confirmar ou cancelar a continuidade da jornada.A Instituição Transmissora deve apresentar apenas os dados e categorias previamente selecionados, garantir transparência e conformidade com o escopo autorizado e conduzir a confirmação com o mínimo de interações necessárias. Também é sua responsabilidade permitir o cancelamento antes da confirmação, indicar a próxima etapa da jornada e assegurar o redirecionamento adequado à Instituição Receptora em caso de interrupção.DC - etapa 4#F4F5F7
## Requisitos - IT
**Cenário: Informações de consentimento**
1. Informações sobre o consentimento: após a autenticação, apresentar ao usuário, no mínimo, as informações a seguir. Objeto do compartilhamento: informar os dados que serão compartilhados. Instituição Receptora de Dados: identificar a instituição que receberá os dados. Validade do consentimento: apresentar o prazo e a data final. Prazo indeterminado: identificar o prazo como “Indeterminado” ou termo equivalente, sem exibir data final.
2. Conformidade na exibição de dados: exibir somente as categorias e os agrupamentos de dados selecionados pelo usuário no ambiente da Instituição Receptora de Dados.
Compartilhamento de Dados - Informação do Consentimento**Cenário: Seleção de origem**
1. Multiplicidade de origem/produto dos dados: em casos de multiplicidade de origem/produto para as categorias de dados, observar as ações abaixo. Escolha da origem/ produto: permitir a seleção conforme o escopo de dados disponível no canal digital da Instituição Transmissora de Dados. Pré-seleção das opções: apresentar todas as opções de origem/ produto pré-selecionadas, com possibilidade de desmarcação para redução do escopo, mantendo no mínimo uma origem selecionada. Identificação da instituição: quando uma mesma marca contemplar diferentes instituições percebidas pelo usuário de forma segregada, deixar claro a qual instituição cada opção de origem pertence.
**Nota**Caso o login do usuário na Instituição Transmissora de Dados utilize o número da conta (acesso a uma conta por vez), não é esperado que haja multiplicidade de origem para a categoria Dados da Conta.Compartilhamento de Dados - Seleção de origem 
1. Disponibilização de multiplicidade de origem/produto: disponibilizar multiplicidade de origem/produto somente para as seguintes categorias de dados descritas abaixo. Dados de contas (contas de depósito à vista, de poupança e de pagamento pré-pagas ou pós-pagas) Cartões de crédito.
2. Restrição seleção de origem/produto: não disponibilizar seleção de origem para as demais categorias de dados, como dados cadastrais, investimentos, operações de crédito e câmbio. Para esses casos, compartilhar todos os dados existentes na Instituição Transmissora de Dados. Compartilhar as sub-modalidades dos produtos contratados ou distribuídos pela Instituição Transmissora de Dados, bem como as operações de câmbio contratadas, canceladas ou liquidadas por essa instituição. O acesso a essas sub-modalidades acontece em seus canais digitais. Em cenários de transações de crédito, investimento e/ou câmbio, informar ao usuário que novas operações ou contratações dessas categorias terão seus dados automaticamente incorporados ao consentimento vigente.
**Nota**Os dados transacionais, operações de crédito, investimentos e de operações de câmbio serão compartilhados por até 12 meses retroativos, conforme [Resolução Conjunta nº1](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Resolu%C3%A7%C3%A3o%20Conjunta&numero=1).Compartilhamento de Dados - Seleção de origem**Cenário: Detalhes dos dados compartilhados**
1. Por padrão, as informações secundárias (descritas abaixo) não devem aparecer de forma detalhada: O nome dos agrupamentos – exemplo: saldo, limites e extratos O detalhamento de informações da tabela de dados – exemplo: transações de cartões de crédito - informações do cartão, identificação de transação, valor da transação, datas, identificação do estabelecimento. Para apresentar os detalhamentos que a Instituição Transmissora de Dados julgar como necessários, deve-se utilizar recursos de User Experience conforme padrões da instituição, por exemplo: pequenos botões de informação (tooltips) (?) (+), expandir informação ao passar o mouse (mouseover), link do tipo “Mostrar mais” etc.
2. Para situações nas quais o usuário compartilha uma categoria de produtos ou de contratos por meio de seleção única (ex.: operações de crédito, investimento e/ou câmbio), a Instituição Transmissora de Dados deve considerar todas as permissões para os produtos da mesma categoria, ainda que não os comercialize no momento da confirmação.
 Compartilhamento de Dados - Detalhes dos dados compartilhados**Cenário: Detalhes para a confirmação**
1. Indicação da próxima etapa da jornada: apresentar ao usuário um indicativo da próxima etapa da jornada.
2. Continuidade da transmissão de dados: permitir que o usuário continue a transmissão dos dados com apenas uma única confirmação. Reduzir cliques desnecessários após a autenticação, admitindo apenas cliques adicionais para seleção de origens e digitação de credenciais, quando aplicável.
3. Não devem ser apresentados ‘Termos e Condições’ nesta etapa, mesmo que por meio de link, ainda que não se exija aceite e/ou leitura.
**Nota**Reforçamos que, conforme [Instrução Normativa BCB n° 463 de 10/04/2024](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=463), referente à versão 6.0 do Manual de Experiência do usuário no Open Finance, e [Resolução Conjunta nº1 de 04/05/2020](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Resolu%C3%A7%C3%A3o%20Conjunta&numero=1), etapas adicionais ou utilização de métodos mais rigorosos de autenticação não contempladas atualmente no canal digital da Instituição Transmissora de Dados serão interpretadas como mecanismos que desincentivam o compartilhamento de dados.Compartilhamento de Dados - Detalhes para a confirmação
1. Cancelamento do compartilhamento: possibilitar que o usuário interrompa a jornada antes da confirmação. Garantir que a opção de interrupção da jornada não seja visualmente mais proeminente do que a opção de prosseguir.
2. Cancelamento da confirmação de compartilhamento: redirecionar o usuário para a Instituição Receptora de Dados quando houver cancelamento da confirmação de compartilhamento, respeitando os requisitos de redirecionamento de retorno (IT para IR). A IR deve apresentar, no retorno do usuário, mensagem informando que o consentimento não foi realizado.
Compartilhamento de Dados - Detalhes para a confirmação#F4F5F7
## Recomendações - IT
**Cenário: Detalhes dos dados compartilhados**
1. Visualização granular por modalidade: disponibilizar opção (ex. botão, link, etc) para a visualização granular das informações vinculadas a cada modalidade ocultadas por padrão, para os produtos descritos abaixo. Crédito: Ex. número do contrato e valor. Investimentos: Ex. renda fixa bancária e fundos de investimento. Câmbio: Ex. identificação da operação e data de fechamento do contrato.
2. Ausência de agrupamento selecionado: quando a IT não possuir algum agrupamento selecionado pelo usuário, apresentar mensagem informativa . Ex. “No momento, não encontramos nenhum produto que atenda aos dados selecionados.”

# Etapa 5: Redirecionamento
Nesta etapa, o usuário é redirecionado do ambiente da Instituição Transmissora para o ambiente da Instituição Receptora para a efetivação do compartilhamento de dados. O usuário acompanha o processo por meio de uma tela informativa, sem a necessidade de realizar qualquer ação adicional, sendo informado de que o redirecionamento está em andamento e ocorre de forma segura.A Instituição Transmissora deve garantir que o redirecionamento seja automático, sem o uso de navegadores intermediários. Também pode possibilitar a consulta ao status do processo em caso de interrupção, assegurando continuidade e clareza na experiência.DC - etapa 5#F4F5F7
## Requisitos - IT
**Cenário: Tela de transição**
1. Informações sobre o redirecionamento: garantir que essa etapa seja somente informativa, sem exigir qualquer ação adicional do usuário para confirmar o redirecionamento, e contendo, no mínimo, as informações abaixo. Indicação de que o redirecionamento está em andamento. Indicação de que o redirecionamento é seguro.
**Nota**É importante dar a****informação de que a operação está sendo processada e que é necessário aguardar a abertura automática do aplicativo da IR.
1. Tanto a Instituição Receptora de Dados quanto a Instituição Transmissora de Dados não devem exigir qualquer ação adicional do usuário para confirmar o redirecionamento, o carácter da etapa é apenas informativo.
2. Redirecionamento entre dispositivos móveis: em dispositivos móveis, redirecionar o usuário diretamente para o aplicativo da IR, sem a passagem por navegadores intermediários.
3. Manutenção do ambiente original: redirecionar o usuário ao mesmo ambiente da IR utilizado no início da jornada (aplicativo ou browser).
Compartilhamento de Dados - Tela de transição #F4F5F7
## Recomendações - IT
**Cenário: Interrupção da jornada**
1. Interrupção do fluxo de consentimento: quando o fluxo de consentimento for interrompido nesta etapa, permitir o acesso fácil à visualização do status do processo pelos canais digitais da Instituição.

# Etapa 6: Efetivação
Nesta etapa, o compartilhamento de dados é efetivado e o usuário visualiza, no ambiente da IR, o resultado da solicitação realizada. O usuário recebe a confirmação de sucesso ou insucesso do compartilhamento e pode consultar o status do consentimento, assim como os principais detalhes da autorização concedida.A IR deve comunicar o resultado da jornada de forma clara e, em caso de sucesso, apresentar um resumo com informações essenciais, como validade do consentimento, finalidade do uso dos dados e escopo compartilhado.DC - etapa 6#F4F5F7
## Requisitos - IR e IT
**Cenário: Mensagem de sucesso**
1. Disponibilização do status do consentimento: incluir no ambiente de gestão do Open Finance nos canais digitais as informações e o status do consentimento recém-confirmado.
#F4F5F7
## Requisitos - IR
**Cenário: Mensagem de sucesso**
1. Comunicação de sucesso ou insucesso: assim que o usuário retornar da IT, apresentar uma tela informando o sucesso ou o insucesso do compartilhamento .
Compartilhamento de Dados - Mensagem de sucesso**Cenário: Detalhes do consentimento**
1. Sucesso: em caso de sucesso, exibir um resumo da solicitação (Ex. botão “detalhes” ou “veja mais”) com, no mínimo, as informações abaixo. Validade do consentimento: apresentar o prazo e a data final. Em caso de prazo indeterminado, identificar como “Indeterminado” ou termo equivalente. Finalidade do uso dos dados: informar o propósito do uso dos dados compartilhados. Escopo dos dados compartilhados: apresentar os tipos de dados compartilhados, como dados cadastrais, contas, cartões de crédito, investimentos e operações de crédito.
2. Ausência de escopo de dados: informar o usuário sobre os impactos quando algum escopo de dados solicitado inicialmente não for compartilhado e essa ausência impedir o cumprimento integral da funcionalidade, da finalidade ou do benefício oferecido pela Instituição Receptora de Dados.
**Nota**O resumo contém as informações mínimas necessárias. Fica a critério de cada Instituição Receptora de Dados manter apenas o resumo ou substituí-lo por um comprovante mais completo.Compartilhamento de Dados - Detalhes do consentimento#F4F5F7
## Recomendações - IR e IT
**Cenário: Geral**
1. Uso de linguagem simplificada nos Termos para o Usuário: simplificar a linguagem dos “Termos para o Usuário” definidos no Glossário de Experiência, evitando repetições.
#F4F5F7
## Recomendações - IR
**Cenário: Geral**
1. Identificação da IT: no resumo do compartilhamento, exibir o nome da instituição de origem dos dados.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Compartilhamento de Dados > v.19.00.01 Jornada de Compartilhamento de Dados com Múltiplos Aprovadores > v.19.00.01 Requisitos e Recomendações - Jornada de Compartilhamento de Dados com Múltiplos Aprovadores

---
id: 1477282342
title: v.19.00.01 Requisitos e Recomendações - Jornada de Compartilhamento de Dados com Múltiplos Aprovadores
version: 1
modified: 2026-01-23T17:46:30.947Z
url: /spaces/OF/pages/1477282342/v.19.00.01+Requisitos+e+Recomenda+es+-+Jornada+de+Compartilhamento+de+Dados+com+M+ltiplos+Aprovadores
---

Os requisitos e recomendações para **Múltiplos Aprovadores** correspondem aos da Jornada Básica de Compartilhamento de Dados acrescidos dos requisitos e recomendações específicos descritos neste capítulo.**Atenção**!Por se tratar de um cenário com múltiplos aprovadores, que envolve participantes adicionais na jornada, podem existir especificidades em relação às orientações da **Jornada Básica de Compartilhamento de Dados**. Em caso de divergência, prevalecem os requisitos e recomendações definidos neste capítulo.
# Etapa 4: Confirmação com Múltiplos Aprovadores
DC Múltiplos Aprovadores - etapa 4**Para os casos nos quais seja necessária aprovação adicional, além do solicitante:**#F4F5F7
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

# Etapa 6: Efetivação com Múltiplos Aprovadores
DC Múltiplos Aprovadores - etapa 6**Para casos nos quais seja necessária aprovação adicional, além do solicitante:**#F4F5F7
## Requisitos - IR
**Cenário: Tela do solicitante**
1. Na perspectiva do solicitante, após ser redirecionado de volta da Instituição Transmissora de Dados, a Instituição Receptora de Dados deve: Apresentar uma tela comunicando o sucesso (ou insucesso) da etapa de confirmação da solicitação. Informar que a solicitação está pendente de aprovação e que, após a atuação do aprovador, a funcionalidade, finalidade ou benefício terão continuidade no ambiente da Instituição Receptora de Dados. Em caso de erro, o problema deve ser especificado ao usuário e deve ser acrescentada uma orientação para resolução, se possível.
**Nota**Como o consentimento ainda não foi efetivado, não é necessário apresentar o resumo da solicitação. Compartilhamento de dados - Tela do solicitante#F4F5F7
## Requisitos - IT
**Cenário: Tela do aprovador**
1. Na perspectiva do aprovador, após a confirmação no ambiente de Instituição Transmissora da Dados, deve ser apresentada: Uma tela comunicando o sucesso (ou insucesso) da etapa de aprovação do compartilhamento. Em caso de erro, o problema deve ser especificado ao usuário e deve ser acrescentada uma orientação para resolução, se possível.
Compartilhamento de dados - Tela do aprovador#F4F5F7
## Recomendações - IR
**Cenário: Geral**
1. Para casos com mais de um aprovador, é recomendado que a Receptora possibilite acesso rápido para a continuação da jornada pelo usuário, após a conclusão das aprovações na Transmissora.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Compartilhamento de Dados > v.19.00.01 Jornada de Compartilhamento de Dados via Hybrid Flow com Hand-off > v.19.00.01 Requisitos e Recomendações - Jornada de Compartilhamento de Dados via Hybrid flow com Hand-off

---
id: 1477282232
title: v.19.00.01 Requisitos e Recomendações - Jornada de Compartilhamento de Dados via Hybrid flow com Hand-off
version: 1
modified: 2026-01-23T17:46:28.985Z
url: /spaces/OF/pages/1477282232/v.19.00.01+Requisitos+e+Recomenda+es+-+Jornada+de+Compartilhamento+de+Dados+via+Hybrid+flow+com+Hand-off
---

A seguir, estão descritos os requisitos e recomendações específicos para o ***Hybrid flow*****com*****Hand-off*******entre as instituições nas etapas de **Direcionamento** e **Redirecionamento** da Jornada de Compartilhamento de Dados.
# Etapa 2: Direcionamento Hybrid flow com Hand-off
Nesta etapa, o usuário é direcionado do ambiente da IR para o ambiente da IT para dar continuidade à jornada de compartilhamento de dados, por meio de um fluxo híbrido com *hand-off* entre canais digitais (ex. celular e desktop). Durante o direcionamento, o usuário acompanha o processo por telas informativas, sem a necessidade de realizar ações adicionais, tendo visibilidade de que a transição está em andamento e é segura.As instituições envolvidas devem garantir uma experiência clara, segura e contínua durante o direcionamento, comunicando de forma transparente o andamento da transição e reduzindo fricções entre canais. Também faz parte das atribuições das instituições disponibilizar mecanismos adequados para a continuidade da jornada, como direcionamento para aplicativo ou browser, e assegurar a retomada do fluxo em caso de interrupção, até a confirmação do compartilhamento de dados.DC hybrid flow - etapa 2#F4F5F7
## Requisitos - IR
**Cenário: Tela de transição**
1. Informações sobre o direcionamento: durante o direcionamento, exibir uma tela informativa contendo, no mínimo, as informações abaixo. Indicação de que o direcionamento está em andamento. Indicação de que o direcionamento é seguro. Ex.: “Estamos te levando com segurança para a [Instituição X]”.
Compartilhamento de Dados - Tela de Transição - Direcionamento IR> IT desktop#F4F5F7
## Requisitos - IT
**Cenário: Tela de transição**
1. Recepção do usuário: após o direcionamento da IR, apresentar ao usuário uma tela com instruções e ferramentas necessárias para continuidade da jornada pelo celular, de forma clara e simples.
Compartilhamento de Dados - Tela de transição - Direcionamento IR > IT desktop#F4F5F7
## Recomendações - IR e IT
**Cenário: Tela de transição**
1. Simplificação da jornada: utilizar o menor número de interações possível para reduzir a fricção na jornada.
2. Ao direcionar para o browser da Instituição Transmissora de Dados, pode-se abrir na aba da Receptora, ou seja, substituir a página da Receptora pela nova página da Transmissora, ou manter a aba da Receptora e abrir o browser da Instituição Transmissora em uma nova aba.
3. Padrão visual: seguir o padrão visual do aplicativo da IT para garantir segurança e familiaridade ao usuário.
4. Disponibilização do canal de acesso: caso a IT possua mais de um canal disponível - app ou browser (desktop) - , oferecer a opção de acesso que julgar mais apropriada para a experiência do seu usuário.
Como não são todas as instituições que têm mais de um canal disponível, essa tela é opcional e deve ser implementada apenas quando aberta em ambiente desktop. Além disso, essas opções podem estar em uma tela única de redirecionamento, facilitando a navegação do fluxo.O exemplo abaixo foi desenhado em duas etapas apenas para garantir um melhor entendimento do processo de escolha do canal. Compartilhamento de Dados - Tela de transição - Direcionamento IR > IT desktop#F4F5F7
## Recomendações - IT
**Cenário: Tela de transição**
1. Alternativas para o direcionamento: para facilitar o direcionamento do usuário do browser (desktop) para o aplicativo da IT, utilizar mecanismos como QR code dinâmico, código de ativação, entre outros. 
- Utilizar DeepLink nas jornadas iniciadas em dispositivos móveis.
- Utilizar elementos visuais e textuais que reforcem o direcionamento, como loaders , animações, barras de progresso ou indicadores visuais.
2. Prevenção de interrupções : alertar sobre a possibilidade de falha na jornada em dispositivos com o recurso de ocultação de aplicativos ativado, orientando o usuário a desativar esse recurso se necessário.
**Nota**A interface é a representação ilustrativa de apenas uma das diversas opções, o QR Code dinâmico. Fica a cargo da instituição definir o melhor mecanismo de escolha. Compartilhamento de Dados - Tela de transição - Direcionamento IR>IT desktop
# Etapa 5: Redirecionamento Hybrid flow com Hand-off
Nesta etapa, o usuário segue do ambiente da Instituição Transmissora para o ambiente da Instituição Receptora para a efetivação do compartilhamento de dados. O usuário é orientado nesse processo por telas informativas.A Instituição Transmissora deve comunicar de forma clara o resultado da solicitação e orientar o usuário a retornar ao canal da Instituição Receptora utilizado para a efetivação do compartilhamento.DC hybrid flow - etapa 5#F4F5F7
## Requisitos - IT
**Cenário: Tela de transição**
1. Como não há redirecionamento de retorno para o ambiente desktop da Instituição Receptora de Dados nos casos de Hand-off , após a etapa de confirmação, a Instituição Transmissora de Dados deve, em seu ambiente: Informar que a solicitação foi concluída com sucesso ou apresentar o caso de erro pertinente. Apresentar informações claras de continuidade, orientando o usuário a retornar ao canal da Receptora utilizado para visualizar o status do processo.
Compartilhamento de dados - Tela de transição- Redirecionamento IT> IR #F4F5F7
## Recomendações - IT
**Cenário: Tela de transição**
1. Tela de transição: no browser (desktop), ao identificar que o usuário finalizou a jornada no app da IT (com a confirmação, o cancelamento ou por timeout), exibir a página de redirecionamento para a IR.
Compartilhamento de Dados - Tela de transição - Redirecionamento IT > IR desktop

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão Geral

---
id: 1477280409
title: v.19.00.01 Gestão Geral
version: 1
modified: 2026-01-23T17:46:01.570Z
url: /spaces/OF/pages/1477280409/v.19.00.01+Gest+o+Geral
---

Requisitos e recomendações específicos para o ambiente de gestão geral do Open Finance.Através desse ambiente, as instituições participantes que devem disponibilizar uma área de gestão dedicada ao Open Finance devem possibilitar que o usuário acesse informações gerais, termos de uso e os serviços oferecidos. **Nota:**Consulte os subcapítulos Gestão do Consentimento, Gestão de Portabilidade de Crédito e Gestão de Pagamentos para visualizar os requisitos e recomendações específicos para esses ambientes.#F4F5F7
## Requisitos - IT e ID
**Cenário: Sobre a área de gestão do Open Finance**
1. Termos e condições: Quando aplicável, disponibilizar termos e condições de uso somente na área de gestão.
Área de gestão - Termos de uso#F4F5F7
## Recomendações - Instituições participantes
**Cenário: Sobre a área de gestão do Open Finance**
1. Conteúdos institucionais: Na tela inicial da área de gestão do Open Finance, exibir opções como “O que é o Open Finance?” e “Ler Termos de Uso” facilitando o acesso a informações essenciais sobre o funcionamento e os direitos do usuário no Open Finance.
Área de gestão - Conteúdos institucionais - RecomendaçãoRodapétrue

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Portabilidade de Crédito (UX)

---
id: 1477281606
title: v.19.00.01 Gestão de Portabilidade de Crédito (UX)
version: 1
modified: 2026-01-23T17:46:19.534Z
url: /spaces/OF/pages/1477281606/v.19.00.01+Gest+o+de+Portabilidade+de+Cr+dito+UX
---

As instituições participantes da jornada de Portabilidade de Crédito — Instituição Proponente (IP) e Instituição Credora (IC) — devem disponibilizar ao usuário, por meio de uma Área de Gestão, a listagem de todos os pedidos realizados, com o tipo de produto, seus respectivos status e informações detalhadas, respeitando o contexto da jornada (síncrona ou assíncrona) e os prazos de exibição definidos para cada situação. As instituições também devem permitir que o usuário cancele uma portabilidade que esteja em andamento a qualquer momento antes da fase de liquidação e devem comunicar o cancelamento à outra instituição.#F4F5F7
## Requisitos - IP e IC
**Cenário: Consulta aos pedidos**
1. Exibição de pedidos de Portabilidade de Crédito : exibir a lista de pedidos de Portabilidade de Crédito com seus respectivos status individuais. Ex.: Em análise, Portabilidade em andamento, etc. Identificação do tipo de contrato : indicar o tipo de contrato associado a cada pedido. Ex. Consignado Federal ou CPC.
2. Exibição de dados de proposta e contraproposta : exibir os dados da proposta e contraproposta conforme descrito no cenário de Apresentação da Proposta .

### Área de Gestão da Instituição Proponente (IP)
Portabilidade de Crédito - Instituição Proponente (IP) 
### Área de Gestão da Instituição Credora (IC)
 Portabilidade de Crédito - Instituição Credora (IC)As tabelas a seguir apresentam os status que cada instituição, quando aplicável, deve exibir, os motivos para cada status, os dados a serem exibidos, o prazo de exibição e o possível próximo status, a fim de garantir melhor entendimento da jornada.
| Instituição Proponente (IP) |
| --- |
| Status | Motivo | O que exibir | Prazo de exibição | Próximo status |
| Em análise (Requisito para jornada assíncrona) | Pedido de Portabilidade de Crédito em análise | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | Até a análise ser concluída, conforme informado pela Proponente | Proposta disponível  Sem proposta |
| Proposta disponível (Requisito) | Proposta recebida, aguardando resposta do usuário | Comparativo entre proposta e contrato original | No mínimo 2 dias, conforme legislação e regulação vigente | Em andamento (caso a proposta seja aceita e o contrato seja assinado)  Cancelada (em caso de recusa ou expiração) |
| Sem proposta (Requisito para jornada assíncrona) | Nenhuma proposta disponível para o pedido de Portabilidade de Crédito | Dados do contrato original (opcional): Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | A ser definido pela Proponente | N/A |
| Portabilidade em andamento (Requisito) | Proposta aceita pelo usuário | Comparativo entre proposta aceita e contrato original | Até o cancelamento ou conclusão da portabilidade | Concluída  Cancelada (se cancelada pelo usuário antes da fase de liquidação ou pela Proponente) |
| Portabilidade concluída (Requisito) | Portabilidade de Crédito finalizada com sucesso | Comparativo entre proposta aceita e contrato original | 14 dias corridos após o status final, e depois pode mover para Área de Gestão de Crédito da IF | N/A |
| Portabilidade cancelada (Requisito) | Proposta recusada  Proposta expirada | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito) | Usuário cancelou a portabilidade  Proponente cancelou a portabilidade | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito quando aplicável) | Contraproposta aceita | Comparativo entre proposta e contrato original | 14 dias corridos após o status final | N/A |

| Instituição Credora (IC) |
| --- |
| Status | Motivo | O que exibir | Prazo de exibição | Próximo status |
| Portabilidade em andamento (Requisito) | Proposta aceita pelo usuário | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | Até o cancelamento ou conclusão da portabilidade | Concluída  Cancelada (se contraproposta for aceita, ou se portabilidade for cancelada pelo usuário antes da fase de liquidação ou pela Proponente) |
| Portabilidade em andamento (Requisito quando aplicável) | Contraproposta recusada  Contraproposta expirada | Comparativo entre contraproposta e proposta da Proponente | Até o cancelamento ou conclusão da portabilidade | Em andamento |
| Portabilidade concluída (Requisito) | Portabilidade de Crédito finalizada com sucesso | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito) | Usuário cancelou a portabilidade  Proponente cancelou a portabilidade | Dados do contrato original: Taxa de juros Valor da parcela Número de parcelas Saldo devedor Número do contrato | 14 dias corridos após o status final | N/A |
| Portabilidade cancelada (Requisito quando aplicável) | Contraproposta aceita | Comparativo entre contraproposta aceita e proposta da Proponente | 14 dias corridos após o status final, e depois pode mover para Área de Gestão de Crédito da IF | N/A |
#F4F5F7
## Requisitos - IP
**Cenário: Pedido em análise**Para pedidos que estejam em análise, nos casos de jornada assíncrona, a Proponente deve:   
1. Prazo de análise: informar prazo estimado para finalização da análise do pedido.
Portabilidade de Crédito - Pedido em análise #F4F5F7
## Requisitos - IP e IC
**Cenário: Portabilidade em andamento**Para pedidos de portabilidade em andamento, a instituição deve:  
1. Desistência da portabilidade: permitir desistência da Portabilidade de Crédito antes da liquidação. Informar que o usuário pode desistir da portabilidade antes da fase da liquidação. Caso a portabilidade entre em fase de liquidação, desabilitar a opção de cancelamento do pedido.
Portabilidade de Crédito - Portabilidade em andamento #F4F5F7
## Requisitos - IP
**Cenário: Portabilidade em andamento**Para pedidos de portabilidade em andamento, a Proponente deve:  
1. Download do contrato assinado: possibilitar que o usuário baixe o contrato assinado da proposta.
Portabilidade de Crédito - Portabilidade em andamento **Cenário: Portabilidade concluída**Para pedidos cuja portabilidade tenha sido efetivada, a Proponente deve:  
1. Download do contrato assinado: possibilitar que o usuário baixe o contrato assinado da proposta.
Portabilidade de Crédito - Portabilidade concluída #F4F5F7
## Recomendações - IP
**Cenário: Sem oferta disponível**Para pedidos para os quais não há proposta, a Proponente pode:
1. Novo pedido: possibilitar que o usuário faça um novo pedido de Portabilidade de Crédito.
Portabilidade de crédito - Sem oferta disponível **Cenário: Portabilidade cancelada**Para pedidos de portabilidade que tenham sido cancelados pelo usuário ou pela Proponente, a instituição pode:  
1. Novo pedido: possibilitar que o usuário faça um novo pedido de Portabilidade de Crédito.
Portabilidade de Crédito - Portabilidade cancelada

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão do Consentimento

---
id: 1477280441
title: v.19.00.01 Gestão do Consentimento
version: 1
modified: 2026-01-23T17:46:02.202Z
url: /spaces/OF/pages/1477280441/v.19.00.01+Gest+o+do+Consentimento
---

O Guia de Experiência apresenta os requisitos e recomendações para o ambiente de Open Finance dentro das Instituições Receptoras e Transmissoras de Dados, e é nesse ambiente que o usuário terá acesso à seção **Meus Compartilhamentos**, na qual poderá ver os dados recebidos e enviados, bem como os detalhes e status dos seus compartilhamentos, sejam eles ativos, cancelados ou vencidos. Nesse ambiente será possível, também, acessar as ações referentes à gestão dos compartilhamentos, sendo possível revogar, alterar ou renovar um compartilhamento de dados seguindo as diretrizes específicas a cada tipo de ação.As Instituições Receptoras de Dados deverão disponibilizar a ação de Revogação do consentimento dado e opcionalmente, podem disponibilizar as ações de Alteração e Renovação (padrão ou simplificada) dos consentimentos dados. Em caso de implantação das jornadas opcionais, deve-se seguir os requisitos previstos no Guia de UX. As instituições Transmissoras de Dados deverão apenas disponibilizar a ação de revogação do consentimento dado. As demais ações, de Alteração ou Renovação só poderão ser realizadas nas Instituições Receptoras.Dentro do ambiente Open Finance de cada instituição será possível acessar os compartilhamentos, bem como as opções de:
- Revogar compartilhamento.
- Alterar compartilhamento.
- Renovar compartilhamento.

### Revogação:
Ação de revogar um consentimento ativo. Pode acontecer tanto na Instituição Transmissora de Dados quanto na Instituição Receptora de Dados, em concordância com o Art. 15 da Resolução Conjunta nº1 .
### Alteração e renovação padrão:
Ações complementares, realizadas apenas na Instituição Receptora de Dados, que oferecem uma experiência facilitada para criação de um novo consentimento com base nos dados de um consentimento prévio. Caso o consentimento prévio esteja ativo, alterá-lo ou renová-lo implica revogá-lo para criar um novo em seu lugar.
### Renovação simplificada:
Ação complementar similar à renovação padrão, porém restrita a consentimentos ativos, já que trata da atualização do prazo, sem a substituição do consentimento atual por um novo. É dita simplificada pois dispensa a necessidade de redirecionamento e confirmação na Instituição Transmissora de Dados.
## Ambiente Open Finance
Para fácil acesso às jornadas complementares, é importante criar o ambiente Open Finance, que vai disponibilizar, entre outros conteúdos, informações sobre os compartilhamentos do usuário.**Nota**Os requisitos e as recomendações para demais conteúdos do ambiente Open Finance podem ser tratados em momento futuro por esta convenção.Compartilhamento de dados - Ambiente Open Finance#F4F5F7
## Requisitos - IR e IT
**Cenário: Acesso ao Open Finance**
1. Disponibilização do Open Finance nos canais: disponibilizar o ambiente Open Finance nos seus canais, incluindo-o no primeiro nível do menu principal, para garantir acesso rápido e fácil ao usuário.
Compartilhamento de Dados - Acesso ao Open Finance**Cenário: Histórico de consentimentos**
1. Exibição do histórico de compartilhamentos: disponibilizar, no ambiente Open Finance, uma seção dedicada à exibição do histórico completo de compartilhamentos. a. Diferenciar claramente os consentimentos transmitidos e recebidos para fins de consulta. b. Diferenciar claramente os consentimentos conforme o status: ativos, pendentes e inativos (revogados ou expirados).
2. Exibição dos detalhes do consentimento: disponibilizar acesso aos detalhes de cada consentimento no histórico, contendo, no mínimo: Validade do consentimento : prazo e data final. No caso de prazo indeterminado, identificar para o usuário como “Indeterminado” ou termo similar. Escopo dos dados compartilhados : dados cadastrais, contas, cartões de crédito, investimentos e operações de crédito, etc. Finalidade do compartilhamento: quando a consulta ocorrer no ambiente da Instituição Receptora de Dados. Histórico completo de prazos anteriores: quando o consentimento tiver sido renovado por meio da jornada de renovação simplificada, garantindo visibilidade sobre renovações passadas. Identificação do usuário solicitante em consentimentos com múltiplos aprovadores : quando a consulta ocorrer no ambiente da Instituição Transmissora de Dados.
Compartilhamento de Dados - Histórico de consentimentos**Cenário: Revogação do consentimento**
1. Disponibilização da opção de revogação: no histórico e nos detalhes dos consentimentos, disponibilizar ao usuário a opção de revogar qualquer consentimento ativo, seja transmitido ou recebido.
2. Consequências da revogação: antes da efetivação da revogação, exibir uma tela de confirmação, informando de forma clara as consequências da ação.
3. Abrangência da revogação: garantir que a revogação do consentimento contemple todos os dados objeto do compartilhamento.
**Nota**Fica a cargo das Instituições Receptoras de Dados tratar e/ou excluir os dados de acordo com a legislação vigente, incluindo a LGPD.
1. Respeito às regras de poderes: respeitar, no processo de revogação, as regras de poderes já estabelecidas nas instituições.
2. Manutenção do consentimento no histórico: após a revogação, manter o consentimento e seus detalhes acessíveis no histórico, com status e informações devidamente atualizados.
3. Notificação entre instituições: notificar a outra instituição quando o usuário realizar a revogação do consentimento.
Compartilhamento de Dados - Revogação do consentimento#F4F5F7
## Requisitos - IR
**Cenário: Alteração e renovação do consentimentos**
1. A Instituição Transmissora de Dados não deve oferecer as jornadas de alteração ou renovação do consentimento, enquanto para a Instituição Receptora de Dados, a oferta é facultativa.
2. Comunicação sobre nova confirmação: informar claramente ao usuário que será necessária uma nova confirmação na Instituição Transmissora de Dados, e direcioná-lo para essa instituição.
3. Requisitos aplicáveis às jornadas: aplicar às jornadas de alteração e renovação os mesmos requisitos de todas as etapas da jornada de criação de consentimento, excetuando-se as limitações de configuração dos parâmetros inerentes a esses tipos de jornada. Dessa forma, não é necessário apresentar possibilidade de seleção da Instituição Transmissora de Dados nessas jornadas.
4. Manutenção do histórico após alteração ou renovação: após a efetivação da jornada, manter acessíveis no histórico os detalhes do consentimento revogado e do novo consentimento, com status e informações devidamente atualizados.
**Nota**As jornadas de alteração e de renovação padrão são uma forma de otimizar etapas, criando um consentimento com base em informações de outro já existente. São ações tecnicamente idênticas, logo cabe à interface da Instituição Receptora de Dados desenhar cada jornada com a narrativa condizente com as opções de edição oferecidas, como permitir apenas incrementos de prazo em jornadas apresentadas como renovação ou permitir inclusão de mais escopo em jornadas apresentadas como alteração.**Caso a jornada de alteração seja oferecida:**
1. Disponibilização da jornada de alteração: oferecer a jornada de alteração apenas para consentimentos ativos.
2. Caracterização da jornada de alteração : durante a jornada, apresentar, além das informações do consentimento previstas nos requisitos do Ambiente de Gestão de Consentimentos, ao menos um dos elementos a seguir para caracterizar a jornada como alteração, e não como renovação. Possibilidade de alteração dos dados (inclusão ou exclusão). Possibilidade de redução do prazo. Possibilidade de alteração da finalidade, para casos em que a Instituição Receptora de Dados tiver mais de uma opção vigente.
3. Exibição da finalidade: quando houver apenas uma finalidade do consentimento, exibi-la explicitamente ao usuário, mesmo que a finalidade utilizada no consentimento anterior não esteja mais vigente na Instituição Receptora de Dados.
**Caso a jornada de renovação padrão seja oferecida:**
1. Restrições na jornada de renovação padrão: não permitir, na jornada de renovação padrão, a alteração do escopo de dados compartilhados ou a alteração da Instituição Transmissora de Dados.
2. Restrição na alteração da finalidade: permitir a alteração da finalidade apenas nos casos em que houver necessidade de atualização por parte da Instituição Receptora de Dados.
3. Cálculo da nova data de validade: calcular a nova data de validade do consentimento a partir da data em que ocorrer a renovação, permitindo ao usuário modificá-la apenas para uma data posterior à data de expiração vigente, inclusive para prazo indeterminado. Ex.: Caso um consentimento tenha vigência de 01/01/2023 a 01/01/2024 (prazo de 12 meses), em qualquer opção de prazo apresentada ao usuário e independentemente do momento da renovação, a data final do consentimento renovado deve ser sempre posterior à data final do consentimento original.
Compartilhamento de Dados - Alteração e renovação do consentimento**Cenário: Renovação simplificada do consentimentos**
1. A renovação simplificada é realizada exclusivamente pela Instituição Receptora de Dados e apenas para os consentimentos ativos.
2. Comunicação sem acionamento do usuário: para atualização do prazo de vigência do consentimento, realizar a comunicação entre a Instituição Receptora de Dados e a Instituição Transmissora de Dados exclusivamente via backend , sem direcionar o usuário para confirmação no ambiente da Instituição Transmissora de Dados.
3. Restrição de alteração de dados e da transmissora: não alterar o escopo de dados compartilhados, ou a Instituição Transmissora de Dados.
4. Limitação na alteração da finalidade: alterar a finalidade apenas quando houver necessidade de atualização por parte da Instituição Receptora de Dados, desde que não resulte em alteração do escopo de dados, comunicando de forma clara ao usuário o novo objetivo do compartilhamento.
5. Cálculo da nova data de validade: calcular a nova data de validade do consentimento a partir da data em que ocorrer a renovação, permitindo ao usuário modificá-la apenas para uma data posterior à data de expiração vigente, inclusive para prazo indeterminado. Ex.: Caso um consentimento tenha vigência de 01/01/2023 a 01/01/2024 (prazo de 12 meses), em qualquer opção de prazo apresentada ao usuário e independentemente do momento da renovação, a data final do consentimento renovado deve ser sempre posterior à data final do consentimento original.
6. Restrição à renovação simplificada em múltiplas alçadas: não oferecer a renovação simplificada de consentimentos que envolvam múltiplas alçadas.
7. Exibição do resultado da renovação: ao final do processo, exibir uma tela de sucesso ou insucesso com a resposta da Instituição Transmissora de Dados, em padrão visual semelhante ao da tela de efetivação, reforçando ao usuário se a renovação foi concluída ou não com sucesso.
8. Em caso de insucesso da renovação de forma simplificada, exibir mensagens conforme o motivo do erro retornado, conforme exemplos abaixo: `DEPENDE_MULTIPLA_ALCADA` : “O compartilhamento de dados não pôde ser renovado pois depende de múltipla alçada.”. `DATA_EXPIRACAO_INVALIDA` : “O compartilhamento de dados não pôde ser renovado pois a data final ficou anterior à data de requisição do pedido de renovação ou igual à data de expiração atual ou diferente de prazo indeterminado e maior que 12 meses da data de requisição do pedido de renovação.” `REFRESH_TOKEN_JWT` : “O compartilhamento de dados não pôde ser renovado com esta Instituição Transmissora.” `ESTADO_CONSENTIMENTO_INVALIDO` : “O compartilhamento de dados não pôde ser renovado pois está encerrado ou foi cancelado.” `ERRO GENÉRICO` : “O compartilhamento de dados não pôde ser renovado devido a problemas técnicos. Tente novamente mais tarde.”
Compartilhamento de Dados - Renovação simplificada do consentimento #F4F5F7
## Recomendações - IR e IT
**Cenário: Onboarding Open Finance**
1. Onboarding: na primeira utilização do usuário, realizar onboarding objetivo, apresentando as funcionalidades disponibilizadas pela instituição no ambiente Open Finance. Disponibilizar, também, link de acesso à Área do Cidadão para consulta de informações relacionadas ao Open Finance.
Compartilhamento de Dados - Onboarding Open Finance**Cenário: Ambiente Open Finance**
1. Acesso aos consentimentos: disponibilizar ao usuário o acesso aos consentimentos pelas opções a seguir. Logo após o usuário acessar a opção Open Finance . Por meio de Meus compartilhamentos , acessado pela Open Finance .
2. Localização do ambiente Open Finance: disponibilizar o ambiente Open Finance em áreas dedicadas aos produtos nos canais da instituição para facilitar o acesso do usuário.
3. Revogação múltipla de consentimentos: permitir, de forma opcional para cada instituição, a seleção de mais de um consentimento para revogação, com o objetivo de facilitar a experiência do usuário.
4. Filtros de busca de consentimentos: disponibilizar, de forma opcional para cada instituição, filtros de busca para facilitar a localização dos consentimentos.
5. As ITs poderão, a seu critério, disponibilizar termos e condições referentes ao serviço de compartilhamento de dados, no Ambiente de Gestão de consentimento.
Compartilhamento de Dados - Ambiente Open Finance #F4F5F7
## Recomendações - IR
**Cenário: Renovação simplificada do consentimento**
1. Aviso de renovação padrão: Comunicar o usuário sobre a proximidade da data de vencimento do consentimento, considerando a proporcionalidade em relação ao prazo total do compartilhamento. Permitir a revogação do consentimento anterior após a renovação, caso ele ainda esteja vigente.
2. Aviso de renovação simplificada: comunicar o usuário sobre a proximidade da data de vencimento do consentimento, considerando a proporcionalidade em relação ao prazo total do compartilhamento.
Compartilhamento de Dados - Renovação simplificada do consentimento
# Status do Compartilhamento de dados
Para padronizar e facilitar o entendimento do usuário nas Jornadas de Compartilhamento de Dados e Iniciação de Pagamento, são apresentados a seguir os status que devem ser apresentados ao usuário.As tabelas têm como objetivo deixar claro o De/Para entre o status apresentados para o usuário e os status técnicos das APIs.Compartilhamento de Dados - Status do compartilhamento de dados #F4F5F7
## Requisitos - IR e IT
**Cenário: Geral**
1. O status do compartilhamento deve estar relacionado com a combinação do status do consentimento e, conforme aplicável, das `resources ` associadas a ele e do efetivo compartilhamento de dados cadastrais.
`PENDING AUTHORISATION` > `AVAILABLE `> `TEMPORARILY UNAVAILABLE` > `UNAVAILABLE`Por exemplo: se um consentimento vigente está compartilhando normalmente dados de cadastro e transacionais, mas tem algum recurso com status `UNAVAILABLE`, o status para o usuário deve ser **Ativo**, pois status `AVAILABLE `na ordem de precedência, vem antes do status `UNAVAILABLE `. Por outro lado, se algum recurso está com status `PENDING AUTHORISATION`, então o status para o usuário final deve ser **Pendente de autorização**. 
Confira outros exemplos para casos de API com diferentes status a seguir.
| STATUS PARA USUÁRIO FINAL | CONSENTIMENTO | RECURSO DE SELEÇÃO AGRUPADA (OPERAÇÃO DE CRÉDITO, INVESTIMENTO, CÂMBIO) | RECURSOS DE SELEÇÃO INDIVIDUAL (CONTA OU CARTÃO) | PERMISSÃO PARA DADOS CADASTRAIS |
| --- | --- | --- | --- | --- |
| Ativo | AUTHORISED | AVAILABLE | UNAVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | UNAVAILABLE | AVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | AVAILABLE | TEMPORARILY UNAVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | NÃO SOLICITOU PERMISSÕES¹ | NÃO SOLICITOU PERMISSÕES¹ | SIM |
| Ativo² | AUTHORISED | UNAVAILABLE | UNAVAILABLE | SIM/NÃO |
| Ativo | AUTHORISED | TEMPORARILY UNAVAILABLE | UNAVAILABLE | SIM |
| Temporariamente indisponível | AUTHORISED | TEMPORARILY UNAVAILABLE | UNAVAILABLE | NÃO |
| Aguardando aprovação | AUTHORISED | PENDING AUTHORISATION | AVAILABLE | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | PENDING AUTHORISATION | TEMPORARILY UNAVAILABLE | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | PENDING AUTHORISATION | UNAVAILABLE | SIM/NÃO |
#F4F5F71 Usuário não solicitou permissões dos produtos2 Considerando que o usuário manteve relacionamento com a instituição transmissora
1. Caso haja diferentes status de recursos em um mesmo consentimento ( `AVAILABLE` , `PENDING_AUTHORISATION` , T `EMPORARILY UNAVAILABLE` e `UNAVAILABLE` ) e considerando, também, se há ou não impedimento no tráfego de dados cadastrais (pois não geram recursos listáveis na API Resources) , o peso de cada status para consolidação e demonstração do status do consentimento deve seguir o seguinte:

| STATUS PARA USUÁRIO FINAL | CONSENTIMENTO | RECURSO DE SELEÇÃO AGRUPADA (OPERAÇÃO DE CRÉDITO, INVESTIMENTO, CÂMBIO) | RECURSOS DE SELEÇÃO INDIVIDUAL (CONTA OU CARTÃO) | PERMISSÃO PARA DADOS CADASTRAIS |
| --- | --- | --- | --- | --- |
| Aguardando aprovação | AUTHORISED | AVAILABLE | PENDING AUTHORISATION | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | TEMPORARILY UNAVAILABLE | PENDING AUTHORISATION | SIM/NÃO |
| Aguardando aprovação | AUTHORISED | UNAVAILABLE | PENDING AUTHORISATION | SIM/NÃO |
| Aguardando aprovação | AWAITING_AUTHORISATION | NÃO SE APLICA | NÃO SE APLICA | NÃO SE APLICA |
| Vencido | REJECTED | NÃO SE APLICA | NÃO SE APLICA | NÃO SE APLICA |
| Encerrado | REJECTED | NÃO SE APLICA | NÃO SE APLICA | NÃO SE APLICA |

1. Os `rejections_reasons` podem ser utilizados para mostrar detalhes sobre os status. Para três deles, temos os seguintes requisitos: `INTERNAL_SECURITY_REASON` : por se tratar de um consentimento rejeitado devido às políticas de segurança aplicadas pela Instituição Transmissora (prevenção a fraudes), não deverão ser utilizados, na consulta do detalhamento do consentimento, termos que afirmem se tratar de fraude. `CONSENT_MAX_DATE_REACHED` : deve ser mostrado ao usuário com o status Vencido. `CONSENT_EXPIRED` , `CUSTOMER_MANUALLY_REJECTED` e `CONSENT_ TECHNICAL_ISSUE` : não precisam ser demonstrados na consulta dos consentimentos, pois o usuário não chegou a concluir sua solicitação. `CUSTOMER_MANUALLY_REVOKED` : deve ser mostrado ao usuário com o status Encerrado .
 **Nota**Mais detalhes e informações técnicas sobre os status das APIs de dados cadastrais e transacionais do usuário podem ser encontrados na Área do Desenvolvedor.#F4F5F7
## Recomendações - IR e IT
**Cenário: Geral**
1. Detalhamento de motivo de encerramento de consentimento: para consentimentos encerrados, apresentar o detalhamento do motivo do encerramento, conforme o `rejection_reason` associado.
2. Caso o compartilhamento esteja com status ativo, porém, com algum recurso não acessível, a Instituição Receptora dos Dados pode, a seu critério, sinalizar a existência da pendência na lista de consentimento e sugerir que o usuário verifique o detalhamento do consentimento. Fica a critério da instituição apresentar o status isolado por `resource ` na consulta do usuário.
Compartilhamento de Dados - Geral

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Contas Salvas em CIBA

---
id: 1477281247
title: v.19.00.01 Gestão de Contas Salvas em CIBA
version: 1
modified: 2026-01-23T17:46:14.100Z
url: /spaces/OF/pages/1477281247/v.19.00.01+Gest+o+de+Contas+Salvas+em+CIBA
---

#F4F5F7
## Requisitos - ID e ITP
**Cenário: Contas salvas em CIBA**
1. O acesso às contas salvas deve ser feito por meio de “Minhas contas salvas”, acessado na opção “Open Finance“, e deve estar disponível tanto na instituição Iniciadora de Transação de Pagamentos como na Instituição Detentora de Conta.
2. Cada conta salva precisa ser identificada individualmente e ter, no mínimo, as seguintes informações: Identificação da outra instituição envolvida no vínculo. Data da autorização: data em que o usuário escolheu salvar a conta no último consentimento dado. Identificação da conta de origem: dados da conta de origem dos pagamentos (número e agência) disponível no consentimento dado. Data do vencimento da autorização. Informações sobre os status das contas salvas: ativos e vencidos/ revogados.
Contas salvas em CIBA #F4F5F7
## Recomendações - ID e ITP
**Cenário: Contas salvas em CIBA**
1. Para fácil acesso do usuário, o ambiente de Gestão Open Finance ou as funcionalidades específicas do Open Finance podem estar contidos em áreas dedicadas aos produtos, nos canais das instituições.
2. Pode-se permitir, de maneira opcional a cada instituição, a seleção de mais de uma conta salva para revogação, com foco em facilitar a experiência.
3. A Instituições Iniciadoras e Detentoras podem, a seu critério, disponibilizar termos e condições referentes ao serviço de iniciação de pagamento, no Ambiente de Gestão de contas salvas.
4. Como possibilidade de atalho para a Área de Gestão, poderá existir um botão/link logo após o usuário concluir uma jornada de pagamento e ter salvo essa conta neste pagamento por meio do CIBA.
5. Fica a critério da cada instituição, a ordenação das contas salvas ativas. Recomendamos que as mais próximas do vencimento apareçam primeiro e em destaque.
Contas salvas em CIBA - Recomendações

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Pix - Jornada Básica de Iniciação de Pagamento

---
id: 1477280879
title: v.19.00.01 Gestão de Pix - Jornada Básica de Iniciação de Pagamento
version: 1
modified: 2026-01-23T17:46:08.548Z
url: /spaces/OF/pages/1477280879/v.19.00.01+Gest+o+de+Pix+-+Jornada+B+sica+de+Inicia+o+de+Pagamento
---

Requisitos e recomendações para gestão de pagamentos com Pix - Jornada Básica de Iniciação de Pagamento via Open Finance. Esta seção serve como base para as demais jornadas de pagamento com Pix oferecidas no Open Finance. #F4F5F7
## Requisitos - ID
**Cenário: Sobre a área de gestão de pagamentos**
1. Área de gestão de pagamentos: Disponibilizar, dentro do Open Finance, ambiente para gestão de contas vinculadas, autorizações e pagamentos.
Área de gestão de pagamentos - ID 
#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a área de gestão de pagamentos**
1. Área de gestão de pagamentos: Disponibilizar, dentro do Open Finance, ambiente para gestão de contas vinculadas, autorizações e pagamentos quando: Oferecer serviços de Pix Agendado, Pix Automático e/ou Transferências Inteligentes. Atuar no escopo de compartilhamento de dados. Diferenciar, com clareza, a área para gestão de compartilhamento de dados da área para gestão de pagamentos.
2. Diferenciação das transações: Quando a ITP não for obrigada a disponibilizar a área para gestão de pagamentos, diferenciar no histórico, os pagamentos realizados via Open Finance daqueles realizados diretamente na instituição.   Ex.: Filtros ou iconografia.
Área de gestão de pagamentos - ITP #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta aos pagamentos**As Instituições devem atualizar os status de cada pagamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Status dos pagamentos: Exibir o status de cada pagamento. Ex.: Concluído, Agendado, Cancelado, Pendente etc.
2. Detalhes dos pagamentos concluídos: Possibilitar que o usuário acesse um comprovante com os detalhes de cada pagamento concluído contendo as seguintes informações, conforme definido pelo arranjo de pagamento: Valor do pagamento. Data e hora/minuto/segundo (horário de Brasília) do pagamento. Identificador da transação ( `endtoEndID` do Pix). Forma de pagamento. Identificação do recebedor (nome completo, CPF mascarado/CNPJ e instituição recebedora). Descrição do pagamento, quando aplicável. Valor da tarifa do serviço, quando aplicável. Identificação do pagador (nome completo, CPF/CNPJ e Detentora). Informações adicionais exigidas pelo arranjo Pix, conforme regulação vigente.
Consulta aos pagamentos 
1. Detalhes dos pagamentos não concluídos: Nos casos em que o pagamento não for concluído com sucesso — como status cancelado, expirado ou rejeitado — exibir os campos aplicáveis de acordo com a disponibilidade de informações no momento da falha, conforme definido pelo arranjo Pix.
Detalhes dos pagamentos não concluídos #F4F5F7
## Recomendações - ID e ITP
**Cenário: Geral**
1. Área Pix: Possibilitar que a gestão de pagamento via Open Finance também possa ser feita na área Pix da instituição.
2. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre os pagamentos com facilidade.
Gestão de pagamentos - Geral - Recomendações

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Pix Agendado

---
id: 1477280918
title: v.19.00.01 Gestão de Pix Agendado
version: 1
modified: 2026-01-23T17:46:09.211Z
url: /spaces/OF/pages/1477280918/v.19.00.01+Gest+o+de+Pix+Agendado
---

Requisitos e recomendações para gestão de pagamentos com Pix Agendado via Open Finance, inclusive em Jornadas sem Redirecionamento (JSR). Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.As instituições devem atualizar os status de cada agendamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta aos agendamentos**As instituições devem atualizar os status de cada agendamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Histórico de pagamentos: Exibir a lista de pagamentos gerados por agendamentos únicos ou recorrentes, com seus respectivos status individuais.   Exs.: Agendado, Concluído, Cancelado, Não realizado etc.
2. Detalhes do pagamento: Exibir comprovante de cada pagamento com todas as informações conforme definido pelo arranjo de pagamento.
3. Detalhes da recorrência: Permitir que o usuário acesse os detalhes do comprovante com todas as informações do agendamento, conforme definido pelo arranjo de pagamento.
Consulta aos agendamentos#F4F5F7
## Requisitos - ITP
**Cenário: Alteração dos agendamentos**Na área de gestão de pagamento, a Iniciadora pode permitir que, além de visualizar os agendamentos, o usuário tenha a experiência de alteração dos parâmetros como data, recebedor ou Detentora, embora esteja cancelando o agendamento vigente e criando uma nova autorização de agendamento.
1. Confirmação de alteração: Na etapa de efetivação, exibir mensagem informando que o agendamento anterior foi cancelado e substituído por um novo, sem necessidade de reinício do processo.      Ex.: Tudo certo! Seu agendamento anterior foi encerrado e um novo foi criado com o novo valor.
Experiência de alteração do agendamento#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação dos agendamentos - Único ou recorrentes**Na área de gestão de pagamento, as instituições devem possibilitar que o usuário cancele os pagamentos agendados com Pix, assegurando clareza, rastreabilidade e segurança. 
1. Cancelamento de agendamentos: Permitir que o usuário cancele os pagamentos agendados (único ou recorrente) e informá-lo sobre as regras para cancelamento, conforme definido pelo arranjo de pagamento.   Ex.: Você pode cancelar o pagamento até às 23:59 do dia anterior à data agendada.
2. Irreversibilidade do cancelamento: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências.
Revogação do agendamento **Para agendamentos recorrentes**
1. Manutenção de pagamentos futuros: Deixar claro para o usuário que o cancelamento de um pagamento agendado não impede que os pagamentos de agendamentos futuros sejam efetivados.
Cancelamento de um pagamento da recorrência - 
Manutenção dos pagamentos futuros #F4F5F7
## Recomendações - ID e ITP
**Cenário: Cancelamento de pagamentos avulsos - Agendamento recorrente**Para casos nos quais seja necessária aprovação adicional, além do solicitante:
1. Confirmação de cancelamento: Em caso de tentativa de cancelamento de um pagamento individual por parte do usuário, exibir uma mensagem de confirmação da ação.    Ex.: Deseja cancelar este pagamento para João Rodrigues? Em caso de cancelamento de um pagamento da recorrência, combinar a mensagem de confirmação com a informação obrigatória de que o cancelamento do pagamento atual não impede o agendamento dos pagamentos futuros, conforme os parâmetros da autorização ativa.    Ex.: Deseja cancelar este pagamento para João Rodrigues? Essa ação não pode ser desfeita e não impede o agendamento dos pagamentos futuros. Em caso de cancelamento completo, combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento.    Ex.: Deseja cancelar esse agendamento para João Rodrigues? Esta ação é irreversível e resultará no cancelamento de todos os pagamentos futuros vinculados.
Cancelamento de um pagamento da recorrência - Recomendações **Cenário: Consulta aos agendamentos**
1. Necessidade de saldo e limites: Informar ao usuário que a transação estará sujeita à disponibilidade de saldo e limites transacionais na conta de débito no momento da efetivação do pagamento.
Necessidade de saldo e limite - Recomendação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Pix Automático

---
id: 1477280969
title: v.19.00.01 Gestão de Pix Automático
version: 1
modified: 2026-01-23T17:46:10.072Z
url: /spaces/OF/pages/1477280969/v.19.00.01+Gest+o+de+Pix+Autom+tico
---

Requisitos e recomendações para gestão de pagamentos com Pix Automático, inclusive em Jornadas sem Redirecionamento (JSR), via Open Finance. Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos. #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta às autorizações de Pix Automático**As Instituições devem atualizar os status de cada autorização de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Histórico de autorizações: Exibir a lista de autorizações de Pix Automático com seus respectivos status individuais.    Exs.: Ativa, Expirada, Cancelada, Pendente etc.
Histórico de autorizações 
1. Detalhes da autorização: Permitir que o usuário acesse os detalhes do comprovante com todas as informações de cada autorização de Pix Automático, conforme definido na etapa de Solicitação de Iniciação de Pagamento. Limite de crédito: Informar sobre a possibilidade, quando aplicável, da utilização de limite de crédito pré-aprovado para pagamentos de valor superior ao saldo disponível em conta.
Consulta às autorizações - Limite de crédito**Cenário: Consulta aos pagamentos com Pix Automático**
1. Histórico de pagamentos: Exibir a lista de pagamentos vinculados a cada autorização, com seus respectivos status individuais.    Exs.: Concluído, Cancelado, Não realizado etc.
2. Detalhes do pagamento: Exibir comprovante de cada pagamento com todas as informações conforme definido pelo arranjo de pagamento.
Detalhes do pagamento**Cenário: Alteração de autorização de Pix Automático**Na área de gestão de pagamentos, as Instituições devem possibilitar que, além de visualizar as autorizações, o usuário possa configurar os parâmetros disponíveis das autorizações ativas como valor máximo (ID/ITP), uso do limite de crédito (ID) e preferências de recebimento de notificações (ID/ITP). 
1. Valor máximo: Para autorizações ativas de valor variável, manter desativado por padrão (valor indeterminado) e permitir que o usuário ative e insira um valor máximo para cada pagamento, respeitando o valor mínimo definido pelo usuário recebedor. Informar que se o valor máximo configurado for inferior ao valor de um pagamento agendado, o pagamento não será efetivado e o usuário poderá ser notificado para buscar outras formas de pagamento. Informar que o novo valor máximo se aplica apenas aos pagamentos ainda não agendados da recorrência.
Alteração da autorização - Valor máximo#F4F5F7
## Requisitos - ID
**Cenário: Alteração de autorização de Pix Automático**
1. Uso do limite de crédito : Manter o uso do limite de crédito ativado por padrão e permitir que o usuário desative.
2. Gestão de notificações: Manter o envio de notificações ativado por padrão e permitir que o usuário desative.
Alteração da autorização - Limite de crédito e notificações#F4F5F7
## Requisitos - ITP
**Cenário: Alteração de autorização de Pix Automático****Nota:**Alterações como troca da ID ou da conta de origem exigem a revogação da autorização vigente e a criação de uma nova. 
A ITP pode, se desejar, oferecer essas alterações como uma edição simples, reaproveitando informações já preenchidas e conduzindo o usuário para a etapa de **Solicitação de Iniciação de Pagamento** de forma fluida e transparente, sem exigir ações manuais de cancelamento ou reinício do processo. 
1. Confirmação de alteração: Na etapa de efetivação, exibir mensagem informando que a autorização anterior foi cancelada e substituída por uma nova, sem necessidade de reinício do processo.    Ex.: Tudo certo! A autorização anterior foi cancelada e uma nova foi criada com a sua nova instituição.
Confirmação da alteração #F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação de autorização de Pix Automático**
1. Revogação da autorização: Permitir que o usuário cancele autorizações ativas e informá-lo sobre as regras para cancelamento conforme definido pelo arranjo de pagamento. Irreversibilidade da revogação: Deixar clara a irreversibilidade do cancelamento da autorização e outras possíveis consequências.
Revogação da autorização**Cenário: Cancelamento do pagamento com Pix Automático**Na área de gestão de pagamento, as instituições devem possibilitar que o usuário cancele os pagamentos da recorrência de Pix Automático, assegurando clareza, rastreabilidade e segurança. 
1. Cancelamento dos pagamentos: Permitir que o usuário cancele os pagamentos da recorrência e informá-lo sobre as regras para cancelamento, conforme definido pelo arranjo de pagamento.    Ex.: Você pode cancelar este pagamento até às 23:59 do dia anterior à data agendada. Irreversibilidade do cancelamento: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências. Manutenção dos pagamentos futuros: Deixar claro para o usuário que o cancelamento de um pagamento não impede que os agendamentos futuros sejam efetivados e novos pagamentos sejam agendados.
Cancelamento de pagamento avulso da recorrência #F4F5F7
## Recomendações - ID e ITP
**Cenário: Revogação de autorização de Pix Automático**
1. Confirmação da revogação: Em caso de tentativa de cancelamento da autorização por parte do usuário, exibir uma mensagem de confirmação da ação.  Ex.: Deseja cancelar esta autorização para Telefonia S/A? Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento. Ex.: Deseja cancelar essa autorização? Esta ação é irreversível e resultará no cancelamento de todos os pagamentos futuros vinculados.
Confirmação da revogação**Cenário: Consulta às autorizações e pagamentos com Pix Automático**
1. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre suas autorizações e pagamentos com facilidade.
Busca - Recomendação**Cenário: Cancelamento do pagamento com Pix Automático**
1. Confirmação do cancelamento: Em caso de tentativa de cancelamento de um pagamento individual por parte do usuário, exibir uma mensagem de confirmação da ação.   Ex.: Deseja cancelar este pagamento para Telefonia S/A?  Combinar a mensagem de confirmação com a informação obrigatória de que o cancelamento do pagamento atual não impede o agendamento dos pagamentos futuros, conforme os parâmetros da autorização ativa.   Ex.: Tem certeza que quer cancelar este pagamento para Telefonia S/A? Esta ação é irreversível e não impede o agendamento dos pagamentos futuros.
Confirmação do cancelamento do pagamento avulso - Recomendação **Cenário: Alteração de autorização de Pix Automático**
1. Gestão de notificações: Permitir a gestão de recebimento de notificações para cada autorização ativa em uma única jornada.
2. Valor máximo: Permitir edição de valor máximo para cada autorização ativa de valor variável em uma única jornada.
Alteração de autorização em uma única jornada - Notificações e Valor máximo #F4F5F7
## Recomendações - ID
**Cenário: Alteração de autorização de Pix Automático**
1. Uso do limite de crédito: Permitir edição do uso do limite de crédito para cada autorização ativa em uma única jornada.
Alteração da autorização em uma única jornada - Limite de crédito

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Transações Temporizadas

---
id: 1477281218
title: v.19.00.01 Gestão de Transações Temporizadas
version: 1
modified: 2026-01-23T17:46:13.584Z
url: /spaces/OF/pages/1477281218/v.19.00.01+Gest+o+de+Transa+es+Temporizadas
---

Requisitos e recomendações para gestão das transações que exigem análise adicional por parte da Instituição Detentora de Conta (ID). #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta à transação temporizada**Caso o usuário saia da tela de análise na etapa de **Efetivação**da Instituição Iniciadora de Transação de Pagamento (ITP), ele deve conseguir retomar a consulta da transação pela área de gestão de pagamentos, juntamente com as demais transações.
Para garantir consistência, as instituições precisam manter o status da transação sempre atualizado, de modo que o usuário visualize as mesmas informações tanto na ITP quanto na ID. 
1. Status das transações: Exibir o status atualizado de cada transação temporizada. Exs.: Em análise, Pendente, Concluída, Cancelada, Negada.
2. Detalhes da transação pendente: Enquanto estiver em análise, disponibilizar acesso aos detalhes da transação, contendo a informação sobre necessidade de tempo adicional para análise e todas as demais informações conforme definido pelo arranjo de pagamento.
Consulta à transação temporizada#F4F5F7
## Requisitos - ITP
**Cenário: Consulta à transação temporizada**
1. Alternativa para transação negada: Se após análise, a transação for negada pela Detentora selecionada, indicar ao usuário, quando aplicável, outra Detentora e/ou forma de iniciação de pagamento.
Alternativa para transação negada #F4F5F7
## Requisitos - ID e ITP
**Cenário: Cancelamento da transação**
1. Cancelamento da transação: Permitir que ao acessar os detalhes da transação em análise na área de gestão, o usuário cancele a transação antes da efetivação.
Cancelamento da transação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Transferências Inteligentes

---
id: 1477281107
title: v.19.00.01 Gestão de Transferências Inteligentes
version: 1
modified: 2026-01-23T17:46:11.927Z
url: /spaces/OF/pages/1477281107/v.19.00.01+Gest+o+de+Transfer+ncias+Inteligentes
---

Requisitos e recomendações para gestão de pagamentos com Transferências Inteligentes via Open Finance. Consulte a seção Gestão de Pix – Jornada Básica de Iniciação de Pagamento – para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.Gestão de Transferências Inteligentes - ID/ITP#F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta à autorização de Transferências Inteligentes**As instituições devem atualizar os status de cada autorização de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas Áreas de Gestão conforme as regras do arranjo de pagamento. 
1. Histórico de autorizações: Exibir a lista de autorizações de Transferências Inteligentes com seus respectivos status individuais.    Exs.: Ativa, Expirada, Cancelada, Pendente etc.
Histórico de autorizações 
1. Detalhes da autorização: Permitir que o usuário acesse os detalhes do comprovante com todas as informações de cada autorização de Transferências Inteligentes, conforme definido na etapa de Solicitação de Iniciação de Pagamento.   Limite de crédito: Informar sobre a possibilidade, quando aplicável, da utilização de limite de crédito pré-aprovado para transferências de valor superior ao saldo disponível em conta.
Detalhes da autorização - Limite de crédito
1. Sinalização da Jornada Otimizada: Quando aplicável, sinalizar, de forma clara, na lista de autorizações, aquelas para os quais o usuário optou por compartilhar o saldo e limite.
2. Detalhes da autorização: Na tela de detalhes da autorização, indicar que o saldo e o limite estão sendo compartilhados, bem como o escopo de cada dado.
**Cenário: Consulta às transferências realizadas**
1. Histórico de transferências: Exibir a lista de transferências vinculadas a cada autorização, com seus respectivos status individuais.   Exs.: Concluída, Cancelada, Não realizada etc.
2. Detalhes da transferência: Exibir comprovante de cada transferência com todas as informações conforme definido pelo arranjo de pagamento.
Histórico e Detalhes de transferências#F4F5F7
## Requisitos - ITP
**Cenário: Consulta às transferências realizadas**
1. Detalhes da transferência: Além das informações mínimas previstas no comprovante do arranjo de pagamento, exibir o gatilho que originou a transferência, quando aplicável.
Detalhes da transferência - Gatilhos**Cenário: Alteração da autorização de Transferências Inteligentes**Todas as alterações referentes a autorizações de Transferências Inteligentes devem ser realizadas exclusivamente na área de gestão da Instituição Iniciadora de Transação de Pagamento (ITP) que deve comunicar cada alteração à Instituição Detentora de Conta (ID).  
1. Alteração das contas recebedoras: Permitir que o usuário inclua, altere ou exclua contas recebedoras de mesma titularidade para suas autorizações ativas.
2. Gatilhos de transferências: Permitir que, caso a ITP ofereça mais de uma opção de gatilho de transferência, o usuário possa alterá-las.
Alteração da autorização - Contas recebedoras e Gatilhos**Nota:**Alterações como troca da ID ou da conta de origem, modificação do prazo da autorização, ajuste de valor ou de limites transacionais exigem a revogação da autorização vigente e a criação de uma nova. A ITP pode, se desejar, oferecer essas alterações como uma edição simples, reaproveitando informações já preenchidas e conduzindo o usuário para a etapa de Solicitação de Iniciação de Pagamento de forma fluida e transparente, sem exigir ações manuais de cancelamento ou reinício do processo.  
1. Confirmação da alteração: Na etapa de efetivação, exibir mensagem informando que a autorização anterior foi cancelada e substituída por uma nova, sem necessidade de reinício do processo.    Ex.: Tudo certo! Sua autorização anterior foi cancelada e uma nova foi criada com a nova conta de débito escolhida.
Confirmação da alteração#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação da autorização de Transferências Inteligentes**Na área de gestão de pagamento, as Instituições devem possibilitar que o usuário cancele as autorizações ativas de Transferências Inteligentes, assegurando clareza, rastreabilidade e segurança para o usuário. 
1. Revogação da autorização: Permitir que o usuário cancele autorizações ativas e informá-lo sobre as regras para cancelamento, quando aplicável.  Jornada otimizada: Ao optar pela revogação da autorização do pagamento, deixar claro para o usuário que o compartilhamento de saldo e limite também será revogado.​
2. Irreversibilidade da revogação: Deixar clara a irreversibilidade do cancelamento e outras possíveis consequências.
Revogação da autorização**Cenário: Jornada Otimizada - Revogação da autorização de Transferências Inteligentes com saldo e limite**
1. Revogação do compartilhamento de saldo e limite:  Permitir que o usuário encerre o compartilhamento de saldo e limite de uma autorização a qualquer momento. Ao optar pelo encerramento do compartilhamento de saldo e limite, deixar claro para o usuário que a autorização de pagamento se mantém ativa.
Revogação do compartilhamento de saldo e limite#F4F5F7
## Recomendações - ITP
**Cenário: Consulta à autorização de Transferências Inteligentes**
1. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre suas autorizações e pagamentos com facilidade.
Consulta à autorização - Busca - Recomendação**Cenário: Alteração da autorização de Transferências Inteligentes**
1. Apelido para contas recebedoras: Permitir que o usuário crie um apelido para cada uma de suas contas recebedoras.    Exs.: Investimentos, Poupança para Viagem etc.
2. Gestão de notificações: Permitir a gestão de recebimento de notificações por autorização.
Alteração da autorização - Apelido para contas recebedoras - Recomendação **Cenário: Revogação da autorização de Transferências Inteligentes**
1. Confirmação da revogação: Em caso de tentativa de cancelamento da autorização por parte do usuário, exibir uma mensagem de confirmação da ação.    Ex.: Deseja cancelar esta autorização? Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento.   Ex.: Tem certeza que quer cancelar a autorização? Essa ação não pode ser desfeita e resultará no cancelamento de todas as transferências futuras vinculadas.
Confirmação da revogação - Recomendação **Cenário: Jornada Otimizada - Revogação da autorização de Transferências Inteligentes com saldo e limite**
1. Benefícios do compartilhamento: Caso o usuário selecione a opção de encerramento do compartilhamento de saldo e limite, exibir mensagem informando sobre os benefícios de manter a funcionalidade.
2. Informação adicional: Incluir informação adicional sobre o compartilhamento de saldo e limite através de link, botão, imagem, texto etc.
Revogação do compartilhamento de saldo e limite - Recomendação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Gestão de Vínculos de Conta para JSR

---
id: 1477281271
title: v.19.00.01 Gestão de Vínculos de Conta para JSR
version: 1
modified: 2026-01-23T17:46:14.588Z
url: /spaces/OF/pages/1477281271/v.19.00.01+Gest+o+de+V+nculos+de+Conta+para+JSR
---

Requisitos e recomendações para gestão de vínculos de conta utilizados nas Jornadas de Pagamento Sem Redirecionamento (JSR). 
#F4F5F7
## Requisitos - ID e ITP
**Cenário: Geral**
1. Retorno ao usuário: Conforme regulação vigente, comunicar o resultado de todas as ações ao usuário, inclusive em caso de falha, conforme descrito na seção Casos de erro do subcapítulo Jornada Básica de Iniciação de Pagamento.
Feedback ao usuário**Cenário: Consulta aos Vínculos de Conta**As instituições devem atualizar os status de cada vínculo de conta para todos os tipos de pagamento sem redirecionamento via Open Finance, de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão.
1. Histórico de vínculos de conta: Exibir a lista de vínculos de conta com seus respectivos status individuais. Exs.: Ativo, Expirado, Cancelado, Em análise etc. Jornada Otimizada (saldo e limite): Sinalizar, de forma clara, na lista de contas vinculadas, aquelas para os quais o usuário optou por compartilhar o saldo e limite.
Histórico dos Vínculos de Conta
1. Detalhes dos vínculos de conta ativos: Permitir que o usuário acesse os detalhes de cada vínculo concluído contendo as seguintes informações: Identificação da outra instituição: Exibir a marca da outra instituição envolvida no vínculo. Identificação da Detentora e conta: Exibir identificação da ID e da conta de débito selecionada (Número da agência e conta). Jornada Otimizada (saldo e limite): Quando aplicável, indicar que o compartilhamento de saldo e limite está ativo . Exibir o escopo de cada dado compartilhado.
Detalhes dos Vínculos de Conta ativos
1. Detalhes dos vínculos de conta inativos: Nos casos em que o vínculo de conta não estiver ativo — como status cancelado, expirado ou rejeitado — exibir os campos aplicáveis de acordo com a disponibilidade de informações no momento.
Detalhes dos Vínculos de Conta inativos#F4F5F7
## Requisitos - ID
**Cenário: Consulta aos Vínculos de Conta**
1. Validade do vínculo: Além das informações mínimas previstas no detalhe de cada vínculo, exibir a data de validade do vínculo de conta.
Validade do Vínculo de Conta**Cenário: Alteração dos Vínculos de Conta** Na área de gestão de vínculos de conta, a Instituição Detentora de Conta (ID) deve possibilitar que o usuário altere parâmetros dos vínculos de conta ativos para pagamentos sem redirecionamento via Open Finance e deve comunicar as alterações à Instituição Iniciadora de Transação de Pagamento (ITP).
1. Alteração da validade: Permitir a alteração do prazo de validade do vínculo da conta. Informar o usuário, no momento da confirmação da alteração, que as alterações do prazo vínculo de conta podem afetar os pagamentos automáticos. Ex.: Prazo alterado com sucesso. Pagamentos automáticos programados para data posterior ao novo prazo serão cancelados. Caso o usuário tenha o compartilhamento de saldo e limite ativo, informar que a data de validade desse consentimento será automaticamente atualizada conforme a nova data de validade do vínculo de conta.

1. Alteração de limites: Permitir a alteração dos limites diário e/ou por transação do vínculo de conta. Informar o usuário, no momento da confirmação da alteração, que as alterações do limite podem afetar os pagamentos agendados.   Ex.: Limite alterado com sucesso. Pagamentos agendados com valor superior ao novo limite não serão efetuados.
Alteração de limites do Vínculo de Conta#F4F5F7
## Requisitos - ID e ITP
**Cenário: Revogação dos Vínculos de Conta**Na área de gestão de vínculos de conta, as instituições devem possibilitar que o usuário cancele os vínculos ativos para pagamentos sem redirecionamento via Open Finance, assegurando clareza, rastreabilidade e segurança para o usuário. 
1. Revogação do vínculo de conta: Permitir que o usuário cancele vínculos de conta ativos a qualquer momento. Irreversibilidade da revogação : Deixar clara a irreversibilidade do cancelamento do vínculo de conta, e quando aplicável, do compartilhamento de saldo e limite e outras possíveis consequências. Revogação Pix Automático com JSR: Ao optar pela revogação do vínculo de conta, deixar claro para o usuário que a autorização de Pix Automático atrelada ao vínculo de conta também será revogada. Informar que novos agendamentos não poderão ser criados após a revogação. Informar que pagamentos já enviados serão mantidos. Jornada Otimizada (saldo e limite): Ao optar pela revogação do vínculo de conta, deixar claro para o usuário que o compartilhamento de saldo e limite também será revogado.
Revogação do Vínculo de Conta**Cenário: Revogação do compartilhamento de saldo e limite**Na área de gestão de vínculos de conta, as instituições devem possibilitar que o usuário cancele o compartilhamento de saldo e limite de um vínculo de conta para pagamentos sem redirecionamento via Open Finance, sem cancelar o vínculo de conta, assegurando clareza, rastreabilidade e segurança para o usuário.  
1. Revogação do compartilhamento de saldo e limite: Permitir que o usuário cancele o compartilhamento de saldo e limite de um vínculo de conta a qualquer momento. Manutenção do vínculo: Ao optar pelo encerramento do compartilhamento de saldo e limite, deixar claro para o usuário que o vínculo de conta se mantém ativo.
Revogação do compartilhamento de saldo e limite#F4F5F7
## Recomendações - ID e ITP
**Cenário: Consulta aos Vínculos de Conta**
1. Acesso às contas salvas: Disponibilizar acesso às contas salvas através:  - Da área “Open Finance”.  - Do caminho “Open Finance” > “Minhas contas salvas/vinculadas”.   - De áreas dedicadas aos produtos, no canal da instituição.
2. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre seus vínculos de conta com facilidade.
3. Ordenação da lista: Na lista de vínculos de conta ativos, exibir primeiramente os que estiverem próximo de expirar.
Consulta aos Vínculos de Conta - Geral - Recomendações
1. Identificação do dispositivo: Exibir a identificação (apelido) do dispositivo autorizado.
Consulta aos Vínculos de Conta - Dispositivo autorizado - Recomendações#F4F5F7
## Recomendações - ITP
**Cenário: Consulta aos Vínculos de Conta**
1. Validade do vínculo: Exibir a data de validade do vínculo de conta.
Validade do Vínculo de Conta - Recomendação#F4F5F7
## Recomendações - ID
**Cenário: Alteração dos Vínculos de Conta**
1. Uso do termo “alterar”: Usar o termo “alterar” em suas diferentes conjugações, de acordo com o contexto.
2. Otimização da alteração: Pré-preencher dados do vínculo de conta para facilitar a alteração. Ex.: Se o parâmetro alterado for de limites, os demais campos podem vir preenchidos.
Alteração dos Vínculos de Conta#F4F5F7
## Recomendações - ID e ITP
**Cenário: Revogação dos Vínculos de Conta**
1. Revogação do vínculo de conta: Possibilitar que o usuário cancele vínculos de conta ativos em uma única jornada.
2. Confirmação da revogação: Em caso de tentativa de cancelamento do vínculo de conta – com ou sem Jornada Otimizada – por parte do usuário, exibir uma mensagem de confirmação da ação.  Ex.: Tem certeza que quer cancelar o vínculo de conta? [O compartilhamento de saldo e limite também será cancelado.] Combinar a mensagem de confirmação com a informação obrigatória sobre a irreversibilidade do cancelamento. Ex.: Tem certeza que deseja cancelar o vínculo? Essa ação é irreversível [e encerra o compartilhamento do saldo e limite e a autorização de Pix Automático atrelada. Os pagamentos agendados serão mantidos, mas novos agendamentos não poderão ser feitos].
Revogação dos Vínculos de Conta - Recomendações**Cenário: Jornada Otimizada - Revogação do compartilhamento de saldo e limite**
1. Benefícios do compartilhamento: Caso o usuário selecione a opção de encerramento do compartilhamento de saldo e limite, exibir mensagem informando sobre os benefícios de manter a funcionalidade.
2. Informação adicional: Incluir informação adicional sobre o compartilhamento de saldo e limite através de link, botão, imagem, texto etc.
Revogação do compartilhamento de saldo e limite - Recomendações

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Gestão Open Finance > v.19.00.01 Gestão de Pagamentos > v.19.00.01 Status da Iniciação de Pagamento

---
id: 1477281582
title: v.19.00.01 Status da Iniciação de Pagamento
version: 1
modified: 2026-01-23T17:46:18.901Z
url: /spaces/OF/pages/1477281582/v.19.00.01+Status+da+Inicia+o+de+Pagamento
---

Sumário76016truenonelisttrue
# Detalhamento dos Status da Jornada
**Para padronizar e facilitar o entendimento do usuário nas Jornadas de Compartilhamento de Dados e Iniciação de Pagamento, mostramos a seguir os status que devem ser apresentados ao usuário.**As tabelas têm como objetivo deixar claro o De-Para entre o status apresentado para o usuário e os status técnicos das APIs.Área de Gestão de Pagamentos 
# Status da Iniciação de Pagamentos
Para apresentar o status final ao usuário, deve-se seguir esta matriz de Status do “Consentimento” vs Status “Payments”:
| STATUS PARA O USUÁRIO FINAL | STATUS DE CONSENTIMENTO | STATUS DO `GET/PIX/PAYMENTS/{PAYMENTID}` |
| --- | --- | --- |
| (Pagamento) Solicitado | CONSUMED (Etapa de Efetivação) | `RCVD ` (Received) |
| (Pagamento) Agendado | CONSUMED | `SCHD ` (Processo de agendamento realizado) |
| (Consentimento) Aguardando aprovação de multiplas alçadas | PARTIALLY ACCEPTED | N/A |
| (Pagamento) Pendente | CONSUMED | `PDNG ` (Pendente) |
| (Pagamento) Em Processamento | CONSUMED | `ACCP ` (Pagamento pronto para ser enviado para liquidação)   `ACPD ` (Pagamento enviado para liquidação) |
| (Pagamento) Rejeitado pelo usuário ou detentor | CONSUMED | `RJCT ` (Rejeitado) |
| (Pagamento) Concluído | CONSUMED | `ACSC ` (Pagamento liquidado) |
| (Pagamento) Cancelado | REJECTED  CONSUMED | N/A `CANC ` (Transação cancelada a pedido do usuário) |
| Agendamento cancelado | CONSUMED | `CANC ` (Transação cancelada a pedido do usuário) |
| (Pagamento) Solicitado | AUTHORISED (Etapa de Efetivação) | `RCVD ` (Received) |
| (Pagamento) Pendente | AUTHORISED | `PDNG ` (Pendente) |
| (Pagamento) Em Processamento | AUTHORISED | `ACCP ` (Pagamento pronto para ser enviado para liquidação)   `ACPD ` (Pagamento enviado para liquidação) |
| (Pagamento) Rejeitado pelo usuário ou detentor | AUTHORISED | `RJCT ` (Rejeitado) |
| (Pagamento) Concluído | AUTHORISED | `ACSC ` (Pagamento liquidado) |
| (Pagamento) Cancelado | AUTHORISED | `CANC ` (Transação cancelada a pedido do usuário) |
| (Consentimento) Rejeitado pelo usuário ou detentor | REJECTED | N/A |
| (Consentimento) Revogado pelo usuário, pelo detentor ou pelo iniciador | REVOKED | Qualquer status de pagamento que seja diferente de `RCVD ` ou `SCHD` |
| (Consentimento) Aguardando aprovação de multiplas alçadas | PARTIALLY ACCEPTED | N/A |
| (Consentimento) Aguardando aprovação | AWAITING AUTHORISATION | N/A |
| (Consentimento) atingiu o seu limite (Prazo ou valor) | CONSUMED | `RJCT ` (Rejeitado)   `ACSC` (Pagamento liquidado)   `CANC ` (Transação cancelada a pedido do usuário) |
#F4F5F7
## Requisitos - ID e ITP
**Cenário: Geral**
1. O usuário deve ter acesso aos status dos pagamentos nos ambientes já disponíveis e/ou no ambiente dedicado a gestão do Open Finance.
2. Instituição Detentora de Conta: deve apresentar quando aplicável os status de acordo com a tabela/ matriz de status disponibilizado neste guia.
3. O status “(pagamento) solicitado” não é aplicável na Instituição Detentora de Contas, portanto não deve ser apresentado ao usuário.
4. Caso a instituição tenha o cenário de múltipla-alçada, deve ser apresentado o status “aguardando aprovação (do pagamento)” para todos os usuários necessários e envolvidos nessa operação.
5. Caso a instituição tenha o status “(pagamento ou agendamento) em processamento”, deve ser apresentado ao usuário seguindo a matriz de status.
6. Os status “(pagamento) não concluído” e “(pagamento) concluído” devem ser apresentados ao usuário sem exceção.
Status dos pagamentos

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Casos de erro (Pagamentos e JSR)

---
id: 1477284996
title: v.19.00.01 Casos de erro (Pagamentos e JSR)
version: 1
modified: 2026-01-23T17:47:11.984Z
url: /spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR
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

Consulte as seções de **Casos de erro** da jornada desejada ao longo desse subcapítulo para visualizar possíveis erros e exemplos de mensagens.  **Cenário: Tratativa de erro pós-cancelamento por parte do usuário**
1. Manutenção do cancelamento: Respeitar a decisão do usuário de cancelar a transação mesmo que o cancelamento ocorra após a validação de algum erro (Ex.: Conta indisponível, Saldo insuficiente etc).
Manutenção do cancelamento mesmo após validação de erro - ID#F4F5F7
## Recomendações - ITP
**Cenário: Otimização da solicitação em caso de erro**
1. Manutenção dos dados da solicitação: Ao receber o usuário de volta após a identificação do erro, otimizar a nova solicitação, mantendo os dados corretos já preenchidos e indicando a alteração apenas da informação que causou o erro.
Otimização da solicitação em caso de erro - ITP
# Casos de erro - Iniciação de Pagamento Com Redirecionamento e Vinculação de Conta para JSR
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
# Casos de erro - Iniciação de Pagamento Com Redirecionamento
Esta seção descreve os requisitos para tratar erros nas jornadas de:
- Iniciação de Pagamento Com Redirecionamento .
**Nota**: Consulte a seção **Casos de erro**[https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)**- Iniciação de Pagamento Com Redirecionamento e Vinculação de Conta para JSR**para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
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
**Nota**: Consulte a seção **Casos de erro**[https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)**- Iniciação de Pagamento Com Redirecionamento e Vinculação de Conta para JSR**para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
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
# Casos de erro - Jornada Otimizada - Transferências Inteligentes e Vinculação de Conta para JSR
Esta seção descreve os requisitos para tratar erros nas jornadas de:
- Transferências Inteligentes com Jornada Otimizada (saldo e limite). .
- Vinculação de Conta com Jornada Otimizada (saldo e limite).
**Nota**: Consulte a seção **Casos de erro**[https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)**- Iniciação de Pagamento Com Redirecionamento e Vinculação de Conta para JSR**para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
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
# Casos de erro - Iniciação de Pagamento Sem Redirecionamento (JSR)
Esta seção descreve os requisitos e recomendações para tratar erros nas jornadas de:
- Pagamento Sem Redirecionamento (JSR) .
**Nota**: Consulte a seção **Casos de erro**[https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/1477284996/v.19.00.01+Casos+de+erro+Pagamentos+e+JSR#Casos-de-erro-na-Jornada-de-Inicia%C3%A7%C3%A3o-de-Pagamento-com-Redirecionamento-e-Vincula%C3%A7%C3%A3o-de-Conta-para-JSR)**- Iniciação de Pagamento Com Redirecionamento e Vinculação de Conta para JSR**para visualizar casos de erro que também se aplicam a essa jornada. #F4F5F7
## Recomendações - ITP
**Cenário: Erros na liquidação do pagamento**
1. Limite do vínculo excedido: Informar o usuário sobre a impossibilidade de realizar o pagamento imediato com Pix com valor superior ao do vínculo de conta utilizado.

- Etapa: Liquidação do pagamento
- Quem comunica: ITP
- Ações para prosseguir: Ajustar o valor do pagamento e tentar novamente. / Tentar novamente com outro vínculo de conta que possua limite disponível.
- Exemplo de mensagem: Limite do vínculo excedido. O valor da transação excede o limite diário/por transação definido para este vínculo de conta. Altere o valor da transação ou use outra conta para concluir o pagamento.
Limite do vínculo excedido - ITP

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Jornada de Pagamentos via CIBA

---
id: 1477284767
title: v.19.00.01 Jornada de Pagamentos via CIBA
version: 3
modified: 2026-01-23T20:36:32.526Z
url: /spaces/OF/pages/1477284767/v.19.00.01+Jornada+de+Pagamentos+via+CIBA
---

# Visão geral
CIBA (Client Initiated Backchannel Authentication ou Autenticação de Backchannel Iniciada pelo Usuário, em português), é um dos mais recentes padrões da OpenID Foundation. Serve para definir novos fluxos de autenticação e autorização, que são categorizados como “fluxo desacoplado”. Ele oferece novas formas de obter o consentimento do usuário final.
# Como funciona a jornada CIBA?

#

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Jornada de Pagamentos com Múltiplos Aprovadores > v.19.00.01 Comunicação e Notificações  (Múltiplos Aprovadores Pag.)

---
id: 1477284899
title: v.19.00.01 Comunicação e Notificações  (Múltiplos Aprovadores Pag.)
version: 1
modified: 2026-01-23T17:47:09.749Z
url: /spaces/OF/pages/1477284899/v.19.00.01+Comunica+o+e+Notifica+es+M+ltiplos+Aprovadores+Pag.
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a jornada de iniciação de pagamento via Open Finance com múltiplos aprovadores. **Nota:**Consulte a seção de **Comunicação e Notificações** nos subcapítulos dos produtos de pagamentos para visualizar os demais requisitos e recomendações.#F4F5F7
## Requisitos - ID
**Cenário: Ao solicitante**
1. Status da transação: Notificar o usuário solicitante após a atuação de todos os aprovadores com a atualização de status da transação.
 Notificação ao solicitante **Cenário: Ao aprovador**
1. Notificação de pendência: Notificar ativamente o(s) usuário(s) aprovador(es) imediatamente após a confirmação da transação pelo usuário solicitante. Ex.: push, SMS, e-mail etc.
Notificação ao aprovador

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Jornada de Pagamentos com Transações Temporizadas > v.19.00.01 Comunicação e Notificações (Transações Temporizadas)

---
id: 1477284977
title: v.19.00.01 Comunicação e Notificações (Transações Temporizadas)
version: 1
modified: 2026-01-23T17:47:11.385Z
url: /spaces/OF/pages/1477284977/v.19.00.01+Comunica+o+e+Notifica+es+Transa+es+Temporizadas
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante as jornadas de pagamento via Open Finance que envolvam transações temporizadas. Essas comunicações podem ser feitas pela Iniciadora ou pela Detentora, conforme definido pelo arranjo de pagamento.  **Nota:**Consulte a seção de **Comunicação e Notificações** nos subcapítulos dos produtos de pagamentos para visualizar os demais requisitos e recomendações. #F4F5F7
## Recomendações - ITP
**Cenário: Sobre a transação**
1. Status da transação: Caso o usuário saia da tela da ITP, notificá-lo via canal padrão da instituição sobre o andamento e/ou conclusão da transação.   Exs.: Sua transação ainda está em análise. Aguarde. / Transação concluída com sucesso.
Notificações da transação temporizada

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Jornada de Pagamentos via Hybrid flow com hand-off > v.19.00.01 Requisitos e Requisitos - Hybrid flow com hand-off (Pagamentos)

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

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Pix - Jornada Básica de Iniciação de Pagamento > v.19.00.01 Requisitos e Recomendações - Pix - Jornada Básica de Iniciação de Pagamento > v.19.00.01 Comunicação e Notificações - Pix - Jornada Básica de Iniciação de Pagamento

---
id: 1477283506
title: v.19.00.01 Comunicação e Notificações - Pix - Jornada Básica de Iniciação de Pagamento
version: 1
modified: 2026-01-23T17:46:48.245Z
url: /spaces/OF/pages/1477283506/v.19.00.01+Comunica+o+e+Notifica+es+-+Pix+-+Jornada+B+sica+de+Inicia+o+de+Pagamento
---

Esta seção reúne requisitos relacionados à comunicação e ao envio de notificações ao usuário durante a jornada de pagamento instantâneo com Pix via Open Finance conforme
definido pelo arranjo de pagamento.#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix**
1. Notificações sobre o pagamento: Notificar o usuário sobre a efetivação do pagamento, inclusive em caso de falha, conforme as regras do arranjo Pix e conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações sobre pagamentos com Pix

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Pix Agendado - Jornada de Iniciação de Pagamento > v.19.00.01 Requisitos e Recomendações - Pix Agendado > v.19.00.01 Comunicação e Notificações - Pix Agendado

---
id: 1477283850
title: v.19.00.01 Comunicação e Notificações - Pix Agendado
version: 1
modified: 2026-01-23T17:46:53.136Z
url: /spaces/OF/pages/1477283850/v.19.00.01+Comunica+o+e+Notifica+es+-+Pix+Agendado
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a jornada do Pix Agendado. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento.  **Nota:**Consulte a seção de **Comunicação e Notificações - Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Pix Agendado**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização do agendamento, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações de agendamento - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix Agendado**
1. Status dos pagamentos: Notificar o usuário sobre o sucesso, falha ou cancelamento de um pagamento agendado único ou da recorrência, conforme as regras do arranjo de pagamento Pix Agendado.    Ex.: O Pix Agendado no valor de R$100,00 foi enviado para João Rodrigues da Silva CPF ***.345.678-**.
2. Encerramento de conta do recebedor: Notificar o usuário caso a conta do recebedor seja encerrada, informando-o que esse é o motivo para a não efetivação do pagamento atual e dos futuros, em caso de agendamentos recorrentes.   Ex.: O Pix Agendado para João Rodrigues (R$ 100,00) não foi realizado porque a conta do recebedor foi encerrada. Altere a conta na Área de Gestão.
Notificações de pagamento - ID #F4F5F7
## Recomendações - ID
**Cenário: Sobre pagamentos com Pix Agendado****Para agendamentos recorrentes**
1. Encerramento de conta do recebedor: Em caso de encerramento da conta do recebedor, notificar o usuário direcionando-o para a jornada de Alteração/Cancelamento do(s) agendamento(s), a fim de possibilitar a manutenção do produto com o cadastro de uma nova conta recebedora.    Ex.: O Pix Agendado para João Rodrigues (R$ 100,00) não foi realizado porque a conta do recebedor foi encerrada. Altere a conta na Área de Gestão.
Notificação de pagamento - Recomendação

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Pix Automático - Jornada de Iniciação de Pagamento > v.19.00.01 Requisitos e Recomendações - Pix Automático > v.19.00.01 Comunicação e Notificações - Pix Automático

---
id: 1477284332
title: v.19.00.01 Comunicação e Notificações - Pix Automático
version: 1
modified: 2026-01-23T17:46:59.975Z
url: /spaces/OF/pages/1477284332/v.19.00.01+Comunica+o+e+Notifica+es+-+Pix+Autom+tico
---

Esta seção reúne os requisitos relacionados à comunicação com o usuário e ao envio de notificações durante a jornada de Pix Automático. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento. **Nota:**Consulte a seção de **Comunicação e Notificações (Pagamentos)** no subcapítulo**Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Pix Automático**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização do de Pix Automático, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações de autorização - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre a autorização de Pix Automático**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização de Pix Automático, inclusive em caso de falha, conforme as regras do arranjo Pix Automático e conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações de autorização - ID #F4F5F7
## Requisitos - ITP
**Cenário: Sobre pagamentos com Pix Automático****Para casos em que a ITP ou recebedor disponibilize notificações sobre pagamentos**
1. Notificações sobre pagamentos: Se a ITP ou recebedor disponibilizar notificações sobre os pagamentos e o usuário tiver habilitado, notificá-lo sobre agendamentos e efetivação de pagamentos, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
 Notificações de pagamento/agendamento - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Pix Automático**
1. Notificações sobre pagamentos: Notificar o usuário sobre os pagamentos com Pix Automático, inclusive em caso de falha, conforme as regras do arranjo Pix Automático e conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações de pagamento/agendamento - ID

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Iniciação de Pagamentos > v.19.00.01 Transferências Inteligentes - Jornada de Iniciação de Pagamento > v.19.00.01 Requisitos e Recomendações - Transferências Inteligentes > v.19.00.01 Comunicação e Notificações - Transferências Inteligentes

---
id: 1477284634
title: v.19.00.01 Comunicação e Notificações - Transferências Inteligentes
version: 1
modified: 2026-01-23T17:47:04.766Z
url: /spaces/OF/pages/1477284634/v.19.00.01+Comunica+o+e+Notifica+es+-+Transfer+ncias+Inteligentes
---

Esta seção reúne os requisitos relacionados à comunicação com o usuário e ao envio de notificações durante a jornada de Transferências Inteligentes. Essas comunicações podem ser feitas pela Instituição Iniciadora de Transação de Pagamento (ITP) ou pela Instituição Detentora de Conta (ID), conforme definido pelo arranjo de pagamento. **Nota:**Consulte a seção de **Comunicação e Notificações (Pagamentos)** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos Pix.#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a autorização de Transferências Inteligentes**
1. Notificações sobre a autorização: Notificar o usuário sobre a autorização de Transferências Inteligentes, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) .
Notificações de autorização - ITP#F4F5F7
## Requisitos - ID
**Cenário: Sobre pagamentos com Transferências Inteligentes**
1. Encerramento da conta recebedora: Notificar o usuário caso a conta recebedora seja encerrada, informando-o que esse é o motivo para a não efetivação da transferência atual e das futuras. Ex.: O Pix de R$ 500,00 da sua Gestão Financeira Inteligente para sua conta da Wiscredi falhou porque essa conta foi encerrada. Acesse a área de gestão e altere a conta.
Notificação de pagamentos - ID#F4F5F7
## Recomendações - ITP
**Cenário: Sobre pagamentos com Transferências Inteligentes**
1. Encerramento da conta recebedora: Em caso de encerramento da conta recebedora, notificar o usuário direcionando-o para a jornada de Alteração/Cancelamento da autorização, a fim de possibilitar a manutenção do produto com o cadastro de uma nova conta recebedora.  Ex.: O Pix de R$ 500,00 da sua Gestão Financeira Inteligente para sua conta da Wiscredi falhou porque essa conta foi encerrada. Acesse a área de gestão e altere a conta.
Notificações de pagamentos - Recomendação - ITP

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 JSR - Jornada de Pagamento Sem Redirecionamento (UX) > v.19.00.01 Jornada de Pagamento Sem Redirecionamento - JSR > v.19.00.01 Requisitos e Recomendações - Pagamentos Sem Redirecionamento (JSR) > v.19.00.01 Comunicação e Notificações (Pagamentos Sem Redirecionamento)

---
id: 1477286491
title: v.19.00.01 Comunicação e Notificações (Pagamentos Sem Redirecionamento)
version: 1
modified: 2026-01-23T17:47:33.005Z
url: /spaces/OF/pages/1477286491/v.19.00.01+Comunica+o+e+Notifica+es+Pagamentos+Sem+Redirecionamento
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a Jornada de Pagamento Sem Redirecionamento (JSR).  **Nota:**Consulte a seção de **Comunicação e Notificações** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento****,****Pix Agendado****,****Pix Automático****,****Múltiplos Aprovadores****e****Transações Temporizadas******para visualizar os requisitos e recomendações dos produtos e cenários, que também se aplicam à Jornada de Pagamento Sem Redirecionamento.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 JSR - Jornada de Pagamento Sem Redirecionamento (UX) > v.19.00.01 Jornada de Vinculação de Conta (JSR) > v.19.00.01 Requisitos e Recomendações - Vinculação de Conta (JSR) > v.19.00.01 Comunicação e Notificações (Vinculação de Conta - JSR)

---
id: 1477285928
title: v.19.00.01 Comunicação e Notificações (Vinculação de Conta - JSR)
version: 1
modified: 2026-01-23T17:47:25.377Z
url: /spaces/OF/pages/1477285928/v.19.00.01+Comunica+o+e+Notifica+es+Vincula+o+de+Conta+-+JSR
---

Esta seção reúne os requisitos e recomendações referentes à comunicação com o usuário e ao envio de notificações durante a Jornada de Vinculação de Conta. **Nota:** Consulte a seção de **Comunicação e Notificações** no subcapítulo **Pix - Jornada Básica de Iniciação de Pagamento (Pix)****,****Pix Agendado****ou****Pix Automático******para visualizar os requisitos e recomendações dos produtos, que também se aplicam à Jornada de Pagamento Sem Redirecionamento (JSR). #F4F5F7
## Requisitos - ITP e ID
**Cenário: Sobre a Vinculação de Conta**
1. Notificações sobre a Vinculação de Conta: Notificar o usuário sobre a vinculação de conta, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) do capítulo Iniciação de Pagamentos . Jornada Otimizada (saldo e limite): Quando aplicável, notificar o usuário sobre o compartilhamento de saldo e limite, inclusive em caso de falha, conforme descrito no subcapítulo Casos de erro (Pagamentos e JSR) do capítulo Iniciação de Pagamentos .
Notificações de falha na Vinculação #F4F5F7
## Recomendações - ITP
**Cenário: Sobre a Vinculação de Conta**
1. Expiração do vínculo: Notificar o usuário quando o vínculo de conta estiver próximo de expirar, indicando como renovar ou criar outro vínculo.
Notificação de Vínculo prestes a expirar

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Portabilidade de Crédito (UX) > v.19.00.01 Jornada Básica de Portabilidade de Crédito > v.19.00.01 Motivos de cancelamento do pedido de Portabilidade (UX)

---
id: 1477286933
title: v.19.00.01 Motivos de cancelamento do pedido de Portabilidade (UX)
version: 1
modified: 2026-01-23T17:47:39.988Z
url: /spaces/OF/pages/1477286933/v.19.00.01+Motivos+de+cancelamento+do+pedido+de+Portabilidade+UX
---

Motivos padronizados de cancelamento e inconsistências que possam impedir a conclusão de um pedido de Portabilidade de Crédito na jornada do Open Finance Brasil.
### Instituição Proponente (IP)

| MOTIVO DE CANCELAMENTO | DETALHAMENTO | FASE |
| --- | --- | --- |
| Cancelado pelo usuário | Usuário desiste do pedido de Portabilidade de Crédito | Aceite da contraproposta |
| Valor do saldo devedor atualizado substancialmente divergente do valor informado inicialmente | Saldo devedor atualizado divergente do informado inicialmente | Liquidação |
| Política de crédito | Proponente desiste da oferta ao usuário por políticas internas | Liquidação |

### Instituição Credora (IC)

| MOTIVO DE CANCELAMENTO | DETALHAMENTO | FASE |
| --- | --- | --- |
| Retenção do usuário | Usuário aceitou contraproposta da Instituição Credora (dentro do prazo) | Aceite da contraproposta |
| Contrato já liquidado | Contrato liquidado pelo usuário | Liquidação |
| Divergência de valor do pagamento efetuado | Proponente realizou a liquidação com valor divergente | Confirmação do recebimento |
| Decurso de prazo por pagamento não realizado dentro do prazo (pagamento em data inválida) | Proponente realizou a liquidação fora do prazo | Confirmação do recebimento |
| Falta de liquidação | Proponente não realizou a liquidação do contrato | Confirmação do recebimento |
| Portabilidade de Crédito em andamento | Posteriormente à efetivação do pedido de Portabilidade de Crédito, a Credora identificou que o usuário já possui outro pedido de Portabilidade de Crédito em andamento | Formalização/antes do envio da contraproposta |
| Usuário com ação judicial | Usuário possui ação judicial | Liquidação |
| Modalidade da operação incompatível | Modalidade divergente da indicada pela Instituição Proponente | Liquidação |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Portabilidade de Crédito (UX) > v.19.00.01 Jornada Básica de Portabilidade de Crédito > v.19.00.01 Requisitos e Recomendações - Jornada Básica de Portabilidade do usuário > v.19.00.01 Comunicação e Notificações (Portabilidade)

---
id: 1477286899
title: v.19.00.01 Comunicação e Notificações (Portabilidade)
version: 1
modified: 2026-01-23T17:47:39.137Z
url: /spaces/OF/pages/1477286899/v.19.00.01+Comunica+o+e+Notifica+es+Portabilidade
---

Esta seção reúne requisitos e recomendações relacionados à comunicação e ao envio de notificações ao usuário durante a jornada de Portabilidade de Crédito.Cada instituição é responsável por notificar o usuário sobre as mudanças de status que ocorrerem em seu respectivo ambiente.As notificações ativas garantem que o usuário seja informado sobre mudanças relevantes do seu pedido. Esses mesmos eventos devem estar refletidos na Área de Gestão por meio de status e descrições acessíveis ao usuário. Mudanças de estado que não exigem notificação ativa ainda podem ser apresentadas como status na Área de Gestão, de forma clara e contextualizada.#F4F5F7
## Requisitos - IP
**Cenário: Geral**
1. Mudanças de status obrigatórias: notificar ativamente o usuário (ex. push , e-mail, SMS) sobre, no mínimo, as seguintes mudanças de status dos pedidos de Portabilidade de Crédito. Proposta disponível ou não disponível ( jornada assíncrona). Ex.: Temos uma proposta disponível para o seu pedido de portabilidade de crédito. Confira agora mesmo! / Não encontramos uma proposta de portabilidade de crédito adequada ao seu perfil agora. Cancelamento (pela Proponente). Ex.: Sua solicitação de portabilidade de crédito para o empréstimo 885320 foi cancelada. Visualize os detalhes na Área de Gestão. Efetivação da portabilidade. Ex.: Tudo certo! A portabilidade do seu empréstimo 885320 foi concluída. Acesse a Área de Gestão para mais informações.
Portabilidade de Crédito - Geral#F4F5F7
## Requisitos - IC
**Cenário: Geral**
1. Disponibilidade de contraproposta: quando aplicável, notificar ativamente o usuário (ex. push , e-mail, SMS) sobre a disponibilidade de contraproposta para os pedidos de Portabilidade de Crédito. Ex.: Temos uma contraproposta para você. Recebemos o seu pedido de portabilidade de crédito para o empréstimo 885320 e temos uma contraproposta para você. Confira!
Portabilidade de Crédito - Geral#F4F5F7
## Recomendações - IP
**Cenário: Geral**
1. Mudanças de status opcionais: para aprimorar a experiência, em caso de jornadas assíncronas, notificar ativamente o usuário (ex. push , e-mail, SMS) sobre as demais mudanças de status dos pedidos de Portabilidade de Crédito, como nos exemplos a seguir. Proposta prestes a expirar . Ex.: Aceite sua proposta de portabilidade do empréstimo 885320 até amanhã às 23h59. Após esse prazo, ela será cancelada.   Portabilidade em andamento . Ex.:  A portabilidade do seu empréstimo 885320 está em fase final e será concluída em até 2 dias. Te avisaremos quando estiver tudo certo!
Portabilidade de Crédito - Geral#F4F5F7
## Recomendações - IC

### Cenário: Geral

1. Expiração da contraproposta: para aprimorar a experiência, quando aplicável, notificar ativamente o usuário (ex. push , e-mail, SMS) quando a contraproposta estiver próxima de expirar. Ex.: Contraproposta prestes a expirar. Você tem até amanhã às 9h para aceitar a nossa contraproposta para o empréstimo 885320. Após esse prazo, ela será cancelada e a portabilidade será sequenciada com a Wiscredi.
Portabilidade de Crédito - Geral

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Portabilidade de Crédito (UX) > v.19.00.01 Jornada do Consignado Federal > v.19.00.01 Requisitos e Recomendações - Jornada do Consignado Federal

---
id: 1477286956
title: v.19.00.01 Requisitos e Recomendações - Jornada do Consignado Federal
version: 1
modified: 2026-01-23T17:47:40.583Z
url: /spaces/OF/pages/1477286956/v.19.00.01+Requisitos+e+Recomenda+es+-+Jornada+do+Consignado+Federal
---

Os requisitos e recomendações da **Jornada do** **Consignado Federal** correspondem aos da Jornada Básica de Portabilidade de Crédito, acrescidos dos requisitos e recomendações específicos descritos neste capítulo.
# Etapa 2: Consulta (Consignado Federal)
**Nota**Verifique a etapa **Consulta** no subcapítulo **Jornada Básica de Portabilidade de Crédito** para visualizar os requisitos e recomendações dos cenários comuns a todos os produtos de Portabilidade. #F4F5F7
## Requisitos - IP
**Cenário: Autorização no SouGov**Quando não tiver a autorização do usuário no SouGov, depois da escolha do contrato, a IP deve observar os requisitos a seguir.**Para casos em que somente o usuário pode dar a autorização:**
1. Direcionamento para o SouGov : exibir uma tela direcionando o usuário para o SouGov. Na tela de direcionamento, informar ao usuário que, no SouGov, ele deve autorizar a consulta aos dados dos contratos que deseja portar. Ainda na mesma tela, orientar o usuário a retornar à IP depois da autorização no SouGov para seguir com a portabilidade.
**Para casos em que a instituição pode coletar a autorização pelo usuário:**
1. Autorização do contrato no SouGov : exibir uma tela informando sobre a importância da autorização no SouGov. Exibir opção de continuidade da jornada para o usuário.
Consignado Federal - Autorização no SouGov#F4F5F7
## Recomendação - IP
**Cenário: Autorização no SouGov**
1. Opção para autorização existente : exibir opção de continuidade da jornada para o usuário que já realizou a autorização no SouGov, informando que essa autorização permanece válida por 45 dias.
Consignado Federal - Autorização no SouGov

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Open Finance Brasil

---
id: 1477279834
title: v.19.00.01 Open Finance Brasil
version: 1
modified: 2026-01-23T17:45:52.549Z
url: /spaces/OF/pages/1477279834/v.19.00.01+Open+Finance+Brasil
---

Este conteúdo tem como objetivo introduzir os conceitos básicos do Open Finance Brasil, apresentando sua estrutura, princípios fundamentais e principais elementos de funcionamento. A seção estabelece uma base comum de entendimento para apoiar a leitura do Guia e contextualizar as jornadas, produtos e serviços abordados nos capítulos seguintes.
# O conceito de Open Finance
O Open Finance (Sistema Financeiro Aberto) é um conjunto de tecnologias e regras que pretendem dar maior controle e liberdade aos usuários de serviços financeiros.Dessa forma, o usuário (pessoa física ou jurídica) é o titular dos seus dados e decidirá quando, com quem, para qual finalidade e por quanto tempo deseja compartilhá-los.Isso acontece por meio do Compartilhamento de Dados e de Serviços entre as diversas instituições financeiras participantes. Essa ação é feita pelo usuário, mediante seu expresso consentimento, e é viabilizada por APIs que permitem uma integração padronizada dos sistemas.**O Open Finance viabiliza o compartilhamento padronizado de dados e serviços financeiros.**
## Open Finance no Brasil
Iniciativa do Banco Central do Brasil (BCB), o Open Finance Brasil funciona por meio da abertura e integração de sistemas entre as instituições participantes. O processo só pode ser iniciado com o consentimento (autorização) do usuário, é 100% gratuito e digital, ocorrendo exclusivamente nos canais digitais das instituições participantes. O objetivo do Open Finance Brasil é dinamizar o sistema financeiro nacional, ampliar a competitividade do mercado e, como consequência, fornecer melhores produtos e serviços com melhores preços e condições ao usuário final.#F4F5F7O **Open Finance Brasil**, ou Sistema Financeiro Aberto, é uma iniciativa do Banco Central do Brasil que tem como principais objetivos trazer inovação ao sistema financeiro, promover a concorrência, melhorar a oferta de produtos e serviços financeiros ao usuário. 
# Quem está envolvido na implementação do Open Finance no Brasil
O Banco Central definiu a Estrutura Inicial do Open Finance, responsável pela governança do processo de implementação do Open Finance no Brasil, que é composta por três níveis: estratégico, administrativo e técnico.
- O nível estratégico é composto por sete conselheiros, sendo um deles um conselheiro independente, ou seja, sem vínculo com as instituições participantes.
- O nível administrativo é composto pela camada administrativa e de secretariado.
- O nível técnico é composto por Grupos Técnicos, com participação das associações que representam as instituições do sistema financeiro e de pagamentos do Brasil. Esse grupo tem o objetivo de definir, em conjunto, as regras do Open Finance para garantir que todos os participantes do ecossistema tenham os mesmos direitos e deveres.

## Principais Instituições do Grupo de Trabalho

- ABBC: Associação Brasileira de Bancos
- ABBI: Associação Brasileira de Bancos Internacionais
- ABCD: Associação Brasileira de Crédito Digital
- ABDE: Associação Brasileira de Desenvolvimento
- Abecs: Associação Brasileira das Empresas de Cartões de Crédito e Serviços
- ABFintechs: Associação Brasileira de Fintechs
- Abipag: Associação Brasileira de Instituições de Pagamentos
- Abranet: Associação Brasileira de Internet
- ACREFI: Associação Nacional das Instituições de Crédito, Financiamento e Investimento
- Home - Camara-e.net : Câmara Brasileira da Economia Digital
- Febraban: Federação Brasileira de Bancos
- OCB: Organização das Cooperativas Brasileiras

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Experiência do Usuário > v.19.00.01 Princípios de Experiência no Open Finance Brasil

---
id: 1477279868
title: v.19.00.01 Princípios de Experiência no Open Finance Brasil
version: 1
modified: 2026-01-23T17:45:53.041Z
url: /spaces/OF/pages/1477279868/v.19.00.01+Princ+pios+de+Experi+ncia+no+Open+Finance+Brasil
---

Esta página apresenta os princípios de experiência aplicáveis ao Open Finance Brasil, combinando conceitos consolidados de usabilidade ao contexto do Open Finance. Dessa forma, ajuda a orientar a concepção de jornadas e interfaces de maneira alinhada às necessidades dos usuários e às diretrizes regulatórias.
# Instituições e Jornadas Open Finance Brasil
**Atenção!** Os princípios listados neste documento devem ser seguidos por todas as instituições participantes do Open Finance Brasil.O Banco Central do Brasil reforça por meio da regulação vigente que as instituições participantes não devem adotar mecanismos que de alguma maneira incentivem, de forma voluntária ou involuntária, o usuário a desistir do compartilhamento de dados ou de serviços no âmbito do Open Finance. Tais mecanismos incluem, por exemplo:
- A inserção de telas, etapas ou informações desnecessárias à confirmação do compartilhamento.
- O uso de linguagem que possa gerar incerteza ou que afete negativamente, de forma direta ou indireta, a percepção do usuário quanto à credibilidade e à segurança do Open Finance ou das demais instituições participantes.
**As instituições participantes não devem adotar mecanismos que de alguma maneira incentivem, de forma voluntária ou involuntária, o usuário a desistir.**
# Princípios das Jornadas Open Finance Brasil
**Princípios são uma forma de criar um entendimento compartilhado sobre as boas práticas no desenvolvimento de um produto ou serviço.**Os princípios expostos neste documento são baseados nas necessidades e nos direitos dos cidadãos, enquanto usuários vivenciando as diferentes jornadas apresentadas neste Guia de Experiência**.**Eles buscam garantir que os times técnicos se mantenham no caminho correto e ajudam na tomada de decisão a respeito das soluções mais apropriadas, quando existem dúvidas ou divergências. Dessa forma, toda jornada desenvolvida no trilho do Open Finance Brasil deve ser:
## 1. Centrada no usuário
A jornada do usuário do Open Finance deve ser centrada nas necessidades, nos comportamentos e nas expectativas dos usuários, considerando que podem mudar ao longo do tempo. As interfaces só fazem sentido se forem desenvolvidas do ponto de vista de quem irá utilizá-las. Caso contrário, a experiência fica comprometida.
## 2. Compreensível

- Em sua jornada, o usuário deve conseguir entender: Quais informações são compartilhadas; Com quem os dados são compartilhados; Qual a finalidade do compartilhamento; Quando começa e quando termina o compartilhamento; Como podem gerenciar o uso dos seus dados.

## 3. Disponível nos canais digitais das instituições
Em todos os canais digitais onde as instituições participantes ofereçam acesso aos seus produtos e serviços (Ex.: aplicativo) devem constar todas as jornadas do Open Finance que a instituição tenha, incluindo as não obrigatórias.
## 4. Simples e intuitiva
As interações devem ser simples e intuitivas, sem prejudicar consentimento, controle, transparência, privacidade ou compreensão. Evitar elementos desnecessários, excesso de texto, palavras confusas, repetições, muitas etapas ou demora que possam causar frustração ou até desistência.
## 5. Veloz
A velocidade das interações é um dos elementos relacionados a uma boa experiência de uso e deve ser adequada ao usuário e à jornada que ele está realizando. Quando falamos em velocidade de carregamento, já se sabe que apenas um segundo é suficiente para influenciar a percepção do usuário. A espera gera uma resposta de estresse e desconfiança no funcionamento do sistema e pode afetar negativamente a experiência.
## 6. Fundamentada no consentimento atual
O consentimento do usuário deve ser atual, ou seja, fundamentado no direito do usuário de fazer e desfazer uma ação a qualquer momento.
## 7. Acessível e Inclusiva
Uma gama diversificada de pessoas deve ser capaz de acessar, usar e compreender o ecossistema do Open Finance. A experiência do Open Finance deve ser democrática e gerar novas oportunidades de engajamento. Dessa forma, é preciso ter cuidado para não criar barreiras de uso na sua implementação. As interfaces devem estar de acordo com as Heurísticas de Nielsen, que são regras gerais que guiam o processo de construção de uma interface, visando garantir que diferentes usuários consigam utilizar a interface sem dificuldades e com uma experiência de uso positiva.
## 8. Segura
No decorrer da jornada, os usuários devem ser orientados em relação a preocupações sobre fraude e privacidade dos dados. Devem estar claras as questões sobre uso, segurança e proteção dos dados, tanto pessoais quanto transacionais.  É importante que se construa um ambiente de confiança (no sistema, no processo e nas instituições) para assegurar o entendimento, a aceitação e a adesão a esse novo serviço.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Boas práticas para desktop

---
id: 1477279997
title: v.19.00.01 Boas práticas para desktop
version: 1
modified: 2026-01-23T17:45:55.135Z
url: /spaces/OF/pages/1477279997/v.19.00.01+Boas+pr+ticas+para+desktop
---

O Guia de Experiência do Open Finance foi desenvolvido com foco principal em mobile. Esta seção apresenta orientações para adaptar as mesmas diretrizes e boas práticas à experiência em desktop, garantindo consistência, usabilidade e acessibilidade em diferentes dispositivos.
# Adaptação responsiva
A seguir, são apresentados exemplos que demonstram a adaptação da Área de Gestão da versão *mobile* para a versão *desktop*, preservando a estrutura do fluxo e respeitando as boas práticas de UX.Versão *mobile*Versão *desktop*
# Recomendações para ambientes desktop

- Aproveitar o espaço disponível: Distribuir os elementos com equilíbrio, sem sobrecarregar a tela, mantendo a hierarquia de informações clara.
- Manter a consistência visual e funcional : As interações e os componentes devem seguir o mesmo padrão definido no Guia, garantindo familiaridade entre as plataformas.
- Respeitar os fluxos propostos : Adaptar o layout, mas preservando os passos e a lógica dos fluxos descritos no Guia.
- Priorizar acessibilidade e legibilidade : Utilizar fontes e contrastes adequados para leitura em telas maiores, com atenção especial à navegação por teclado.
- Responsividade inteligente : Para resoluções intermediárias (ex: laptops), certificar-se de que os elementos se ajustem corretamente sem comprometer a experiência.
- Foco no usuário : A adaptação para desktop deve manter o foco no usuário, garantindo uma experiência fluida, intuitiva e segura, independentemente do dispositivo utilizado.

# Boas práticas aplicadas
Esta seção apresenta quatro boas práticas aplicadas à adaptação de interfaces para ambientes desktop, com foco na preservação dos fluxos, na consistência visual e na experiência do usuário em telas maiores.
## Hierarquia e Escaneabilidade

1. Hierarquia da informação : Agrupar visualmente menus, filtros e informações para evitar dispersão.
2. Cabeçalhos e subtítulos claros : Cabeçalhos e subtítulos claros são essenciais, pois ajudam na rápida compreensão do conteúdo.
3. Zonas de atenção : Priorizar a área central/esquerda para conteúdo crítico, seguindo os padrões de leitura F/Z.
Hierarquia e Escaneabilidade
## Uso de Espaço e Layout

1. Layout em colunas : Utilizar layout em colunas, recorrendo a painéis laterais para melhor organização do conteúdo.
2. Componentes adaptativos : Utilizar componentes adaptativos, permitindo que botões e campos se expandam conforme o espaço disponível.
3. Espaçamento generoso : Garantir um espaçamento generoso, evitando elementos "grudados" e proporcionando áreas de respiro.
Uso de Espaço e *Layout*
## Navegação e Localização

1. Menu persistente : Manter um menu persistente ou breadcrumb sempre visível para orientar o usuário.
2. Acesso rápido : Incluir atalhos e filtros para facilitar o acesso rápido a ações recorrentes.
3. Estados visíveis : Destacar claramente o que está ativo, como a aba selecionada e os filtros aplicados.
Navegação e Localização
## Consistência Multiplataforma

1. Padronização de componentes : Padronizar componentes para manter a mesma identidade visual e padrões do mobile.
2. Manutenção do fluxo original : Preservar a jornada do usuário mantendo a mesma sequência de etapas do mobile.
Versão *mobile*Versão *desktop*

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Diferenciação entre -marca- e -instituição- para o usuário

---
id: 1477279924
title: v.19.00.01 Diferenciação entre "marca" e "instituição" para o usuário
version: 1
modified: 2026-01-23T17:45:54.007Z
url: /spaces/OF/pages/1477279924/v.19.00.01+Diferencia+o+entre+marca+e+institui+o+para+o+usu+rio
---

Complementando as informações apresentadas na página anterior, esta página apresenta definições e orientações sobre o uso e a identificação de marcas no contexto do Open Finance Brasil, trazendo exemplos que apoiam o reconhecimento pelo usuário e a aplicação consistente das marcas ao longo das jornadas, complementando as informações apresentadas no capítulo anterior.Marca e instituição podem parecer semelhantes para os usuários, mas apresentam diferenças conceituais.#F4F5F7
## Requisitos

### Marca

- Nome de fácil identificação que permite rápida associação para o público em geral.
- Deve levar em consideração o posicionamento atual perante o mercado e ser utilizada pelas instituições que serão identificadas pela marca no Open Finance.
- Deve haver ao menos um canal eletrônico associado a ela, onde seja possível autenticação e confirmação dos dados pelo usuário.
- Usualmente, não tem um CNPJ, mas é usada para identificar uma ou mais instituições de um mesmo conglomerado ou ainda, produtos identificados com marcas de terceiros.
- A definição da marca é feita a exclusivo critério da instituição do Open Finance, inclusive considerando seu posicionamento de mercado e marca, estratégia de negócios e canais digitais acessíveis aos usuários.

### Instituição

- Necessita ser parte do posicionamento de mercado relacionado à marca que utiliza.
- Necessariamente tem CNPJ.
- Instituição com a qual o usuário se relaciona contratualmente e na efetiva prestação de serviço.
- Conglomerado, para fins deste guia, pode ser composto por subsidiárias ou outras instituições controladas, controladoras, coligadas, filiadas, ligadas ou relacionadas contratualmente que podem usar determinada marca para sua identificação no Open Finance.

### Exemplos de diferenciação
Exemplo de diferenciação entre marca e instituição

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Glossário

---
id: 1477280349
title: v.19.00.01 Glossário
version: 1
modified: 2026-01-23T17:46:00.430Z
url: /spaces/OF/pages/1477280349/v.19.00.01+Gloss+rio
---

O glossário padroniza o uso de termos presentes nas resoluções, com o objetivo de promover alinhamento entre as instituições e facilitar a compreensão pelos usuários. Os termos são descritos de forma clara e acessível, apoiando o uso consistente das referências ao longo do Guia e contribuindo para uma jornada mais uniforme.
# Glossário de Consentimento

| Termo na Resolução | Termo para o usuário | Descrição |
| --- | --- | --- |
| Usuário | Usuário | Qualquer pessoa natural ou jurídica que mantém relacionamento destinado à prestação de serviço financeiro ou à realização de operação financeira com as instituições. |
| Solicitação de compartilhamento | Solicitação de compartilhamento ou solicitar compartilhamento | Solicitação iniciada por um usuário para compartilhamento com a Instituição Receptora de seus dados mantidos na Instituição Transmissora. Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “solicitação”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Consentimento | Autorização de compartilhamento ou autorizar compartilhamento | Etapa inicial do fluxo de solicitação de compartilhamento, na qual a Instituição Receptora solicita o consentimento ao usuário. Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “autorização”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Autenticação | Autenticação ou autenticar | Etapa do fluxo de solicitação de compartilhamento na qual a Instituição Transmissora autentica o usuário, ou seja, confirma a identidade do usuário. |
| Confirmação do compartilhamento | Confirmação do compartilhamento ou confirmar compartilhamento | Etapa do fluxo de compartilhamento na qual a Instituição Transmissora confirma com o usuário os dados objeto de compartilhamento. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “confirmação”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Efetivação da solicitação | Situação do compartilhamento | Última etapa do fluxo de solicitação de compartilhamento, na qual a Instituição Receptora informa ao usuário sobre a conclusão e o status da solicitação de compartilhamento (i.e, efetivada, não efetivada ou em aberto). Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “situação”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Redirecionamento | Redirecionamento ou redirecionar | Etapa na qual o usuário é notificado e redirecionado para o ambiente de outra Instituição, seja esta uma Instituição Transmissora de Dados ou Instituição Receptora de Dados. |
| Instituição Transmissora | Instituição de origem | Instituição participante que compartilha com a Instituição Receptora os dados objeto de compartilhamento. |
| Instituição Receptora | Instituição de destino | Instituição participante que recebe os dados objeto de compartilhamento. |
| Identificação do usuário | Autenticação ou autenticar | CPF ou CNPJ utilizados para identificar o usuário no fluxo de solicitação de compartilhamento. |
| Dados objeto de compartilhamento | Confirmação do compartilhamento ou confirmar compartilhamento | Dados do usuário que serão compartilhados com a Instituição Receptora de Dados para uma finalidade específica. Para a redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “dados”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Prazo de validade do consentimento | Situação do compartilhamento | Prazo de validade do consentimento, limitado a 12 meses, apresentado de acordo com a finalidade, podendo ser alterado pelo cliente. Considera desde a data atual até a data final escolhida pelo cliente. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “prazo”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Pré-solicitação de compartilhamento | N/A | Etapa anterior ao fluxo de solicitação de compartilhamento, ocorrendo no ambiente da Instituição Receptora. |
| Pós-solicitação de compartilhamento | N/A | Etapa posterior ao fluxo de solicitação de compartilhamento, ocorrendo no ambiente da Instituição Receptora. |
| Termos e condições do consentimento | Termos e condições do compartilhamento | Termos e condições do consentimento para compartilhamento de dados no Open Finance. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “termos e condições”, caso o contexto do compartilhamento esteja claro nos demais elementos. |
| Origem dos dados | Origem dos dados do compartilhamento | Produtos ou serviços na Instituição Transmissora que serão utilizados para compartilhar os dados objeto de compartilhamento (p.ex.: conta poupança, cartão de crédito, etc.). Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “origem dos dados”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Finalidade do consentimento | Objetivo do compartilhamento | Finalidade de uso pela Instituição Receptora dos Dados objeto de compartilhamento. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “objetivo”, caso o contexto de compartilhamento esteja claro nos demais elementos. |
| Revogação do consentimento | Encerramento do compartilhamento ou encerrar compartilhamento | Revogação do consentimento realizado pelo usuário na Instituição Transmissora ou Receptora. Para redução de caracteres, especialmente em interfaces gráficas menores, é possível usar apenas o termo “encerrar”, caso o contexto de compartilhamento esteja claro nos demais elementos. |

# Glossário de Iniciação de Pagamentos

| Termo na Resolução | Termo para o usuário | Tipo | Descrição |
| --- | --- | --- | --- |
| Instituição Iniciadora de Transação de Pagamento | Instituição Iniciadora de Pagamento | Requisito | Instituição participante que o usuário utilizou para realizar o serviço de Iniciação de Pagamento pelo Open Finance, e que irá realizar o processo junto à Instituição Detentora de Conta. |
| Instituição Detentora de Conta | Instituição de débito | Requisito | Instituição participante com a qual o usuário tem relacionamento e detém sua conta para movimentação de recursos. |
| Serviço de Iniciação de Transação de Pagamento | (Conferir exemplos após a tabela) | Recomendação | Pagamento que será realizado utilizando o Open Finance. |
| Arranjos de pagamento vigentes | Forma de pagamento | Recomendação | É o conjunto de regras e procedimentos que disciplina a prestação de determinado serviço de pagamento ao público. |
| Recebedor da transação de pagamento | Recebedor ou lojista | Recomendação | São os termos utilizados para se referir ao beneficiário do pagamento, podendo ser o “lojista” no caso de B2C e “recebedor” no caso de P2P. |
| Transferências entre contas na própria Instituição | Transferência entre contas da mesma instituição /transferência / transferência entre conta | Requisito | Transferências entre contas na própria instituição: forma de pagamento disponível para o serviço de Iniciação de Transação de Pagamento. É permitido utilizar o termo resumido “transferência” ou “transferência entre contas” para interfaces menores e em situações em que o contexto está claro ao usuário. |
| Transação de Pagamento Instantâneo (Pix) Pix | Pix | Requisito | Forma de pagamento instantâneo brasileiro disponível para o serviço de Iniciação de Transação de Pagamento. Por se tratar de um termo conhecido do usuário comum, recomendamos a utilização de Pix. |
| Data do Pagamento | Data do Pagamento | Recomendação | Data em que o pagamento deverá ser iniciado e executado. |
| Efetivação da Iniciação da Transação de Pagamento | Pagamento solicitado | Requisito | Última etapa do fluxo de solicitação de Iniciação de Pagamento, na qual a Instituição Iniciadora de Pagamento informa ao usuário sobre a efetivação ou não da solicitação de pagamento, bem como seu respectivo status (p.ex.: concluído, pendente, aguardando demais aprovadores). |
| Informações do Pagamento | Informações do Pagamento | Recomendação | Informações referentes ao pagamento que serão disponibilizadas ao usuário após sua transação. |
| Finalidade do Pagamento | Descrição do pagamento ou descrição | Recomendação | Campo aberto para o usuário descrever ou identificar a finalidade das suas transações. |
| Informações do Pagador | Pagador | Recomendação | Informações complementares relativas a conta utilizada para realizar a transação de Iniciação de Pagamento pelo usuário (pagador). |
| Usuário Pagador | Consumidor(a) | Recomendação | Identificação da pessoa pagadora em uma autorização de Pix Automático. |
| Usuário Recebedor | Recebedor | Recomendação | Identificação do destinatário dos pagamentos em uma autorização de Pix Automático. |
| Pagamentos Únicos | Pagamento | Requisito | Transação que ocorrerá uma única vez. |
| Origem | Conta de Débito | Requisito | Contas disponíveis na Instituição de débito que serão utilizados para realizar o pagamento (p.ex.: conta poupança, conta de depósito, etc.). |
| Prazo | Prazo | Requisito | Prazo de validade do consentimento, que estabelecerá até quando (data final) o serviço de iniciação de transação de pagamento será prestado. |
| Periodicidade da Transação | Data do(s) próximo(s) pagamento(s)/Recorrência de Pagamento | Recomendação | Define o intervalo de execução entre os pagamentos de transações recorrentes.   Data do(s) próximo(s) pagamento(s): aplicável para os casos/arranjos onde o usuário pode definir o intervalo estabelecendo uma data fixa e frequência. Exemplo: pagamento realizado mensalmente, todo dia 5.   Recorrência de pagamento: aplicável para os casos/arranjos onde o usuário pode definir o intervalo estabelecendo uma frequência. Exemplo: pagamento realizado semanalmente ou mensalmente.   Data inicial: data que inicia a recorrência de pagamentos.   Data final: a data em que ocorre o último pagamento. |
| Transações de pagamentos sucessivas | Pagamentos recorrentes | Requisito | Consentimento que ocorre na etapa inicial do fluxo de iniciação de transação de pagamento, na qual a Instituição Iniciadora solicita o consentimento ao usuário. Exemplos: Pix Automáticos, agendamentos recorrentes e transferências inteligentes. |
| Consentimento | Autorização de pagamento ou autorizar pagamento | Requisito | São os termos utilizados para se referir à confirmação explícita dada pelo usuário para a solicitação de transação de pagamento. |
| Pagamento de boleto | Pagamento de boleto(s) ou pagar boleto(s | Requisito | Pagamento de boleto: Forma de pagamento disponível para o serviço de Iniciação de Transação de Pagamento. |
| Débito em Conta | Débito em Conta | Requisito | Débito em conta: Forma de pagamento disponível para o serviço de Iniciação de Transação de Pagamento. |
| Ainda não Publicado | Pix Automático | Requisito | Tipo de transação sucessiva, cujo consentimento permite o débito programado de valores recorrentes fixos ou variáveis, com a possibilidade de definição de limites pelo pagador. O recebedor deve ser PJ, pode ser originado de forma online e offline e alguns casos de uso são: pagamentos de contas e assinaturas de serviços. |
| Ainda não Publicado | Agendamentos Recorrentes | Requisito | Tipo de transação sucessiva, cujo consentimento possui valor fixo e limites de quantidade e prazo, definidos pelo pagador. O recebedor pode ser PF ou PJ e alguns casos de uso são: mesadas, doações e pagamentos diversos (diarista, professor particular, etc.). |
| Ainda não Publicado | Transferências Inteligentes | Requisito | Tipo de transação sucessiva, cujo consentimento permite a transferência automática de fundos entre contas bancárias de mesma titularidade, geralmente em diferentes instituições financeiras, com a possibilidade de definição de limites pelo pagador. O usuário pode ser PF ou PJ e alguns casos de uso são: cobertura de contas negativadas, automações de gestão financeira e automações de investimentos. |
| CIBA (Client Initiated Backchannel Authentication) | - | - | O serviço de Iniciação de Pagamentos do Open Finance Brasil implementa o fluxo de consentimento com redirecionamento para a autorização de pagamentos. Esse redirecionamento pode ser realizado via redirect entre aplicativos ou sites e aplicativos. O CIBA fornece uma alternativa para esse fluxo onde ocorre um desacoplamento do processo e o canal para a autorização poderá ser um push-notification, SMS, e-mail, WhatsApp etc. |
| Contas Salvas | - | - | Na jornada CIBA, é dada ao usuário a opção de vincular a Iniciadora de Pagamentos com a Detentora de Conta. Assim, em uma transação futura, a Iniciadora de Pagamentos pode mostrar a conta salva ao usuário, possibilitando uma jornada de confirmação de pagamento facilitada. |

## Identificação do arranjo de pagamentos - Exemplos
As formas de identificação da funcionalidade são exemplos, entretanto, a identificação do arranjo é requisito no caso de exibição junto às outras formas de pagamento.**Nota:** Os exemplos não contemplam todas as possibilidades de aplicação. São apenas formas de demonstrar como a identificação pode ser apresentada ao usuário, havendo inúmeras formas de fazê-lo.
| Combinações possíveis |
| --- |
| Usar | Minha/Meu | Conta |
| Pagar com | Outro/Outra | Saldo |
| Transferir para | | Banco |
| Depositar em/na | | Instituição |

### Exemplos aplicados
Pix: Pagar com outro banco.Boleto: Pagar com minha instituição
# Glossário de Jornada sem Redirecionamento

| Termo na Resolução | Termo para o usuário | Descrição |
| --- | --- | --- |
| N/A | Instituição Parceira | Instituição Parceira é entendida como Detentora de Conta que tem o acordo/contrato bilateral com a ITP para a Jornada de Iniciação de Pagamento sem redirecionamento. |
| Participantes Associados | A Definir | Instituições autorizadas pelo Banco Central a operarem no Open Finance. |
| N/A | Contas Vinculadas | Contas em que o usuário autorizou pagamentos futuros, para fins de jornada sem redirecionamento, entre ITP, ID e o dispositivo do usuário. |

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Manual de uso da marca Open Finance Brasil

---
id: 1477280204
title: v.19.00.01 Manual de uso da marca Open Finance Brasil
version: 1
modified: 2026-01-23T17:45:58.668Z
url: /spaces/OF/pages/1477280204/v.19.00.01+Manual+de+uso+da+marca+Open+Finance+Brasil
---

Este manual tem como objetivo orientar o uso coerente e consistente da marca Open Finance e de seus elementos visuais. As ações de comunicação da Estrutura de Governança devem seguir as orientações na íntegra, de forma de garantir a construção da personalidade Open Finance. Os licenciados têm permissão para aplicar a marca Open Finance dentro de sua identidade corporativa, desde que preservando as regras de proporção de símbolo e logotipo, bem como suas regras de cores e de grafia do nome em textos, ficando dispensados de seguir regras de tipografia, códigos cromáticos e iconografia.**Nota**O uso incorreto ou indevido de qualquer elemento da marca Open Finance será tratado pela estrutura por meio da abertura de ticket.
# Marca

## Versão preferencial Colorida
A marca Open Finance é uma marca mista, e deve ser sempre aplicada na sua forma íntegra, constituída pelo conjunto símbolo e logotipo. O símbolo pode ser aplicado sozinho, mas, na função de ícone, possui normas específicas. A versão colorida da marca usa as cores azul-claro e grafite da paleta de cores e deve sempre preservar o contraste e a legibilidade. A marca Open Finance apresenta-se apenas na versão horizontal.Versão preferencial colorida[Baixar a versão colorida em SVG](https://ob-public-files.s3.amazonaws.com/marca_open_finance.ai)[Baixar a versão colorida em JPEG](https://ob-public-files.s3.amazonaws.com/marca_colorida_open_finance.JPEG.jpg)
## Versões monocromáticas Positiva e negativa
As versões monocromáticas positiva (preta) e negativa (branca) devem ser aplicadas em casos de fundos coloridos em que a versão colorida não tem legibilidade ou contraste. Sendo a versão positiva aplicada para fundos coloridos claros, e a versão negativa para fundos coloridos escuros. Quando a cor de fundo for o azul-escuro ou o azul-claro da paleta de cores, a marca deve sempre ser aplicada na versão negativa (branca), conforme ilustrado abaixo. Versões monocromáticas[Baixar a versão positiva em SVG](https://ob-public-files.s3.amazonaws.com/marca_positiva_open_finance.svg)[Baixar a versão negativa em SVG](https://ob-public-files.s3.amazonaws.com/marca_negativa_open_finance.svg)
## Proporções e margens

### Redução máxima
A redução máxima da marca é o menor tamanho permitido, preservando sua legibilidade. Foi estabelecido que o tamanho mínimo para a altura da marca Open Finance nunca seja inferior a 12,5mm ou 35,6px. As medidas estão em milímetros para mídias impressas e em pixels para mídias digitais.Redução máxima
### Margem de segurança
A margem de segurança é a área imaginária (linha tracejada ciano) de não interferência nos elementos da marca, assegurando a sua correta percepção. A dimensão h é o espaçamento definido a partir da altura da “asa” do símbolo, conforme ilustra o diagrama abaixo.Margem de segurança
# Símbolo
O símbolo é um elemento importante da identidade visual da marca Open Finance, uma vez que transmite os atributos de liberdade financeira. Pode ser aplicado sozinho, como um recurso de grafismo nas versões: preenchido colorido; preenchido positivo e negativo; contorno colorido; contorno positivo e negativo e monocromático azul-claro e monocromático grafite. Para aplicações como ícone (pictograma), o símbolo possui normas específicas.**Atenção:**Não é permitido o uso de gradientes, sombras e efeitos no símbolo, por não preservar as características nem garantir a legibilidade deste.Símbolos Open Finance Brasil[Baixar a versão colorida em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_open_finance.HTML.svg)[Baixar a versão negativa em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_negativo_open_finance.HTML.svg)
## Redução máxima
A redução máxima do símbolo é o menor tamanho permitido, preservando sua legibilidade. Foi estabelecido que o tamanho mínimo para a altura do símbolo Open Finance nunca seja inferior a 10,6mm ou 30px. A espessura do contorno na redução máxima é de 1pt, de forma a garantir as características e legibilidade do símbolo. As medidas estão em milímetros para mídias impressas e em pixels para mídias digitais.Redução máxima
## Margem de segurança
A margem de segurança é a área imaginária (linha pontilhada ciano) de não interferência nos elementos do símbolo, assegurando a sua correta percepção. A dimensão h é o espaçamento definido a partir da altura da "asa" do símbolo.Margem de segurança
# Ícone
Essa versão foi criada para circunstâncias específicas, em ambientes digitais, em casos que os sistemas ou as plataformas usem ícones. O símbolo Open Finance pode ser utilizado sozinho, como ícone, na função de pictograma. Entretanto, suas características visuais devem ser preservadas.**Atenção!**Não é permitido o uso de gradientes, sombras e efeitos no ícone Open Finance, por não preservar as características nem garantir a legibilidade deste.Aplicações e dimensões mínimas[Baixar a versão colorida em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_open_finance.svg)[Baixar a versão positiva em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_positivo_open_finance.svg)[Baixar a versão negativa em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_negativo_open_finance.svg)[Baixar a versão azul claro em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_azul_claro_open_finance.svg)[Baixar a versão grafite em SVG](https://ob-public-files.s3.amazonaws.com/simbolo_contorno_grafite_open_finance.svg)
## Cores preferenciais
Preferencialmente, deve-se usar o ícone Open Finance na versão colorida e nas versões monocromáticas positiva (preta) e negativa (branca), sendo a positiva para fundos claros, e a negativa para fundos escuros.
## Cores alternativas
Para uma melhor adequação do ícone às diversas interfaces gráficas e às diversas paletas cromáticas existentes, é permitido o uso dos matizes dos sistemas ou plataformas.
## Contorno
Como ícone, só é permitida a versão contorno em tamanho de redução máxima (9,7mm x 10,6mm ou 27,5px x 30px), com espessura de 1pt, de forma a garantir as características e a legibilidade do símbolo.O ícone Open Finance dividirá o espaço do widget com o símbolo ou o logotipo do participante. Nesse caso, o espaço do quadrante superior esquerdo deve ser utilizado para o ícone Open Finance, enquanto o quadrante inferior direito será utilizado para o símbolo ou o logotipo do participante. Esse layout é fixo e não pode ser alterado.Para uma melhor adequação visual ao espaço disponível no widget, o símbolo ou o logotipo do participante pode extrapolar os limites do quadrante em 20% do formato original, conforme diagrama abaixo.Como já explicado, o ícone Open Finance pode assumir a cor predominante do participante para melhor adequação à interface gráfica.Ícone Open Finance em widget
# Grafia
Para assegurar a consistência e a coerência da marca Open Finance, é fundamental atentar para a forma de grafar o nome. Apesar de a marca ser escrita em caixa-baixa, em textos corridos, deve-se usar a primeira letra das duas palavras, Open Finance, em caixa-alta. Nos casos em que o texto encontra-se todo em letras maiúsculas, é permitido o uso do nome Open Finance todo em caixa-alta. Nos casos em que é necessário destacar o nome Open Finance, em textos, usa-se o negrito, não sendo permitido o uso de sublinhado, itálico ou aspas.
## Formas corretas
Com o Open Finance, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.COM O OPEN FINANCE, VOCÊ VAI PODER ESCOLHER OS PRODUTOS E SERVIÇOS FINANCEIROS MAIS ADEQUADOS PARA VOCÊ, INDEPENDENTEMENTE DA INSTITUIÇÃO.Com o **Open Finance**, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.
## Formas incorretas
Com o open finance, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o OPEN FINANCE, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o *Open Finance*, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o Open Finance, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.Com o “Open Finance”, você vai poder escolher os produtos e serviços financeiros mais adequados para você, independentemente da instituição.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Premissas de implementação

---
id: 1477279895
title: v.19.00.01 Premissas de implementação
version: 1
modified: 2026-01-23T17:45:53.436Z
url: /spaces/OF/pages/1477279895/v.19.00.01+Premissas+de+implementa+o
---

Este tópico apresenta as premissas de implementação que orientam a aplicação das diretrizes de experiência no Open Finance Brasil, resultantes do alinhamento realizado no âmbito do Grupo de Trabalho de Experiência do Usuário (GT- UX), com o objetivo de apoiar decisões técnicas na execução das jornadas. As orientações se baseiam em duas premissas centrais: preservar o tom de voz das instituições participantes e reforçar seu posicionamento como marcas, assegurando flexibilidade na comunicação sem comprometer a padronização necessária para a jornada do usuário.
# Premissa 1: Preservar o tom de voz de cada instituição
**Tom de voz é como a marca se comunica com seus usuários em diferentes canais.**Por exemplo, para conversar com seus usuários, uma marca mais informal pode usar termos como ‘E aí?’ ou “Legal!”, já uma marca mais tradicional pode usar termos como “Pronto!” ou “Tudo certo”. Em uma situação de erro, por exemplo, pode-se usar a palavra “Ops” (para exemplificar uma linguagem um pouco mais informal) ou “Desculpe” (para exemplificar uma linguagem um pouco mais formal).
# Premissa 2: Instituições participantes devem se posicionar como marcas
**Marcas são uma forma mais amigável, democrática e fácil para identificação das instituições participantes.**Uma marca de conglomerado pode estar correlacionada a mais de uma instituição participante, assim como uma instituição participante pode estar correlacionada a mais de uma marca.
## Relação Instituição x Marca
No exemplo a seguir, são apresentadas duas marcas distintas que compartilham dados do mesmo usuário. Em alguns casos, o usuário pode não reconhecer o nome institucional da instituição, identificando-a apenas pela marca.Além disso, uma instituição pode representar um grupo de participantes, no qual outras instituições estão associadas.Em uma situação fictícia, a marca **Wiscredi** também integra a instituição **GOOP**, relação que pode não ser evidente para o usuário. Ao apresentar o nome das marcas de forma associada às suas instituições participantes, o processo se torna mais claro e transparente.Outro exemplo ocorre quando a instituição participante utiliza uma marca de terceiro, não pertencente ao seu conglomerado, para identificação no Open Finance.Nessa situação, a instituição responsável pelo produto participante deve realizar o cadastro da marca no Diretório, podendo assim usar marca de terceiro para essa identificação, caso o produto seja reconhecido pelo usuário por meio dessa marca.Esse é o caso de *e-commerces* com iniciadores de pagamento *White Label* ou de serviços prestados no modelo *Bank as a Service.*A seguir, são apresentadas as deliberações definidas no âmbito do Grupo de Trabalho para o uso de marcas no Open Finance Brasil, considerando aspectos de identificação, reconhecimento pelo usuário e preservação do tom de voz das instituições ao longo das jornadas:
1. Ter pelo menos um canal digital que permita a autenticação e o compartilhamento de dados pelo usuário.
2. Estabelecer uma correlação dos dados objeto de compartilhamento contidos na marca. Esses dados precisam estar também relacionados aos seus canais digitais  (Ex: produtos comercializados no canal);
3. Definir o nome a ser utilizado pelas instituições participantes dentro do Diretório Central, considerando o posicionamento atual de cada instituição que é conhecido pelos usuários (utilizar nome da marca e não o nome de registro no BCB);
4. Apresentar seu nome por inteiro, sem abreviações, de forma a ser reconhecida pelo usuário e aderente a interfaces menores;
5. Declarar de forma transparente ao usuário a utilização dos dados pela marca e pelos participantes associados, por meio da finalidade de uso;
6. A marca da Instituição Transmissora e da Instituição Detentora de Conta será declarada no `Authorisation Server` , no campo `Customer Friendly Server Name` . Já a marca da Instituição Receptora e da Iniciadora de Transação de Pagamento será declarada no `Software Statement` no campo `Client Name` . Essas serão as marcas que aparecerão na jornada para o usuário. Para mais informações sobre esses campos, ver o Guia de Operação do Diretório Central.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Requisitos para uso e disponibilização de logotipos

---
id: 1477280054
title: v.19.00.01 Requisitos para uso e disponibilização de logotipos
version: 1
modified: 2026-01-23T17:45:56.069Z
url: /spaces/OF/pages/1477280054/v.19.00.01+Requisitos+para+uso+e+disponibiliza+o+de+logotipos
---

Este conteúdo apresenta requisitos e recomendações para o uso dos logotipos das instituições nas Jornadas Open Finance e para sua disponibilização no Diretório de Participantes. Os logotipos cadastrados no Diretório são utilizados tanto no Portal do Cidadão quanto nas jornadas realizadas entre Instituições Receptoras, Transmissoras, Iniciadoras de Pagamentos e Detentoras de Conta.#F4F5F7
## Requisitos

1. Disponibilização de versão reduzida do logotipo: Disponibilizar versão reduzida do logotipo (por exemplo, símbolo ou favicon), priorizando a forma mais reconhecida pelos usuários.
2. Envio de logotipo em SVG: Enviar arquivo SVG contendo a área de proteção do logotipo da instituição, a fim de garantir leitura adequada e espaçamento correto. Formato de envio SVG: Dimensão mínima: 512px x 512px | Sem sombra Margem de segurança: 90px para cada uma das 4 bordas
3. Ajuste do logotipo à moldura: Garantir que o logotipo enviado toque as margens da moldura, conforme os exemplos apresentados a seguir.
4. Limite de tamanho do arquivo: Definir peso máximo do arquivo em 1 megabyte .
5. Logotipo em SVG: Garantir que os logotipos em formato SVG não incorporem imagens de outros formatos (como JPG ou PNG).
6. Disponibilização da URL do logotipo: Disponibilizar a URL do logotipo no Diretório Centralizado, conforme as orientações definidas no respectivo Guia de Operação.
7. Uso de transparência em SVG: Utilizar o recurso de transparência no SVG com atenção, a fim de não comprometer a visualização do logotipo em fundos coloridos, escuros ou em dark mode .
8. Integridade e proporção da marca: Manter a marca sem manipulações e preservar sua proporção original, independentemente do formato de apresentação (por exemplo, recorte circular ou quadrado).
#F4F5F7
## Recomendações

1. Aplicação de logotipos: Realizar a aplicação dos logotipos com tamanho mínimo de 48×48 px em telas de dispositivos móveis e 40×40px em telas web, em todas as jornadas.

## Exemplos para disponibilização do logotipo das instituições

### Aplicações corretas

1. Justificado em todas as margens.
2. Justificado verticalmente.
3. Justificado horizontalmente.
Aplicações corretas
### Aplicações incorretas

1. Ultrapassa todas as margens.
2. Não encosta em algum par de margens.
3. Ultrapassa um par de margens.
Aplicações incorretas

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Orientações transversais > v.19.00.01 Termos e condições de uso

---
id: 1477280124
title: v.19.00.01 Termos e condições de uso
version: 1
modified: 2026-01-23T17:45:57.315Z
url: /spaces/OF/pages/1477280124/v.19.00.01+Termos+e+condi+es+de+uso
---

Os Termos e Condições de Uso disponibilizados aos usuários/clientes (“Usuários”) devem contemplar um conjunto mínimo de tópicos, com o objetivo de assegurar transparência, clareza e adequada compreensão das condições aplicáveis ao uso dos produtos e serviços. As orientações a seguir aplicam-se às instituições participantes do Open Finance (“Instituições Participantes”), incluindo Receptoras de Dados, Iniciadoras de Transações de Pagamento ou aquelas que coletam consentimento dos usuários para o compartilhamento de proposta de crédito (“Instituições Receptoras”), conforme as determinações da Resolução Conjunta nº 01/2020 do Banco Central do Brasil e do Conselho Monetário Nacional.
# Termos e condições de uso para a jornada do usuário (Receptoras)
Os Termos e Condições de Uso devem ser elaborados pelas Instituições Receptoras conforme suas políticas e linguagem de relacionamento com os usuários, devendo conter, no mínimo, os tópicos a seguir:
- Visão geral do Open Finance - o que é, quem são os participantes, como funciona a Jornada do Consentimento e o compartilhamento de dados e serviços (oportunamente, de acordo com as fases de implementação do Open Finance), principais funções.
- Possibilidade de alteração dos termos e condições a qualquer momento pelas Instituições Receptoras.
- Fazer menção ou link para a Política de Privacidade da Instituição Receptora, que pode estar na própria API ou no site da Instituição Receptora.
- Descrição das possíveis finalidades de tratamento de dados pessoais objeto do consentimento que podem ser realizadas pela Receptora, bem como outras finalidades relacionadas ao Open Finance (inclusive em casos de resolução de eventuais disputas entre instituições participantes, atendimento do usuário no Service Desk etc.; esclarecendo que o tratamento de dados ocorrerá de acordo com os limites do consentimento do usuário).
- Descrição sobre possível uso de dados de terceiros que constam dos dados cadastrais e do histórico dos dados e serviços que serão compartilhados.
- Descrição da jornada do usuário, necessidade de identificação do usuário na Receptora e informação sobre o direcionamento do usuário aos ambientes das Instituições Transmissoras de Dados ou Detentoras de Contas para autenticação e confirmação do compartilhamento de dados e serviços ou Iniciação de Transação de Pagamento.
- Incluir a possibilidade de revogação do consentimento na Receptora e Transmissora de Dados, bem como na Detentora de Conta e na Iniciadora de Pagamento.

---

# v.19.00.01 Guia de Experiência do Usuário Open Finance Brasil > v.19.00.01 Visão Geral > v.19.00.01 Sobre o Guia > v.19.00.01 Como ler o Guia de UX do Open Finance

---
id: 1477279814
title: v.19.00.01 Como ler o Guia de UX do Open Finance
version: 1
modified: 2026-01-23T17:45:52.304Z
url: /spaces/OF/pages/1477279814/v.19.00.01+Como+ler+o+Guia+de+UX+do+Open+Finance
---

A partir de 30 de outubro de 2025, o Guia de UX foi reorganizado para tornar a leitura mais objetiva e facilitar a consulta durante o desenho e a validação das jornadas.Agora, os cenários de uma mesma etapa estão agrupados por instituição, reunindo em um único bloco todos os cenários. Essa organização favorece uma leitura linear, evita repetições e permite a visualização consolidada de cada conjunto de cenários.Dessa forma, é possível localizar com mais facilidade os requisitos, recomendações e cenários de cada etapa. A estrutura aparece da seguinte maneira:
# Etapa 1: Nome da etapa (Jornada)
#F4F5F7
## Requisitos - Abreviação da instituição (Ex.: ITP)
**Cenário: Momento específico da etapa**
1. Requisito a ser seguido pela ITP. Requisito dependente do requisito 1. Requisito dependente do requisito 1.a.
#F4F5F7
## Recomendações - Abreviação da instituição (Ex.: ITP)
**Cenário: Momento específico da etapa**
1. Recomendação sugerida para a ITP. Recomendação dependente da recomendação 1. Recomendação dependente da recomendação 1.a.
Essa organização permite compreender rapidamente quais cenários se aplicam a cada instituição dentro de uma mesma etapa, além de facilitar a navegação direta para os conteúdos correspondentes.A mudança contribui para uma navegação mais fluida, possibilita comparações diretas entre instituições e agiliza a identificação de requisitos e recomendações em jornadas extensas.Por fim, as caixas de **Nota** e **Atenção** são utilizadas para complementar o conteúdo principal, destacando detalhes adicionais e pontos críticos que auxiliam na interpretação correta e na aplicação das orientações apresentadas.**Nota**As notas possuem caráter informativo. **Atenção!**As informações possuem caráter de alerta e, se não observadas, podem comprometer o entendimento do conteúdo do Guia.