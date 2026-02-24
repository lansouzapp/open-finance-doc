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