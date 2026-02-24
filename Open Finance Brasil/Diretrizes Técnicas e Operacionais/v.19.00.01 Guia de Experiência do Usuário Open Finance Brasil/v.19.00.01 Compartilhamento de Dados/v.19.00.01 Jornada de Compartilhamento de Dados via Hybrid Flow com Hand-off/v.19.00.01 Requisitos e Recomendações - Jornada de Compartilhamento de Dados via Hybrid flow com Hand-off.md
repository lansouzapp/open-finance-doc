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