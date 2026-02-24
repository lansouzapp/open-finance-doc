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