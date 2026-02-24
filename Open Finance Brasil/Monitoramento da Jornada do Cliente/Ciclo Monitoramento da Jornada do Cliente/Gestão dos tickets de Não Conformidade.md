---
id: 689045505
title: Gestão dos tickets de Não Conformidade
version: 6
modified: 2025-12-19T14:36:26.288Z
url: /spaces/OF/pages/689045505/Gest+o+dos+tickets+de+N+o+Conformidade
---

## Fluxo dos tickets de Não Conformidade

### Detalhamento

1. O Ticket é aberto pelo Atendimento da Jornada UX e encaminhado para atendimento do N2 das Instituições Financeiras, colocando o status para ENCAMINHADO N2 ATENDIMENTO;
2. O N2 da Instituição Financeira coloca o ticket em ANÁLISE N2
3. O N2 da Instituição Financeira deve verificar os apontamentos, anexos e acesso aos links disponibilizados e: caso haja problema no acesso aos links ou dúvidas relacionadas aos apontamentos, o ticket pode ser encaminhado para o requisitante - status AGUARDANDO REQUISITANTE; o Atendimento da Jornada UX deve responder aos questionamentos e encaminhar de volta à Instituição Financeira, atualizando o status do ticket para ATUALIZADO PELO REQUISITANTE; não havendo problemas ou dúvidas, o N2 da Instituição financeira atualiza o ticket para EM ATENDIMENTO N2;
4. Iniciado o atendimento, caso o N2 da Instituição Financeira identifique que um ou mais apontamentos necessitem de desenvolvimento para resolução, o ticket deve ser atualizado para AGUARDANDO IMPLEMENTAÇÃO N2;
5. Após o atendimento de um ou mais apontamentos, o N2 da Instituição Financeira pode atualizar o ticket para: IMPLEMENTADA CORREÇÃO PARCIAL: esse status indica que alguns apontamentos foram corrigidos e atualizados em ambiente produtivo, podendo ser retestados, e outros apontamentos estão pendentes de correção. Importante : Nesse status não há parada na contagem de tempo do SLA da Instituição Financeira.
6. Após o atendimento de todos os apontamentos, o N2 da Instituição Financeira deve atualizar o ticket para CORREÇÃO IMPLEMENTADA: esse status indica que todos os apontamentos foram corrigidos e atualizados em ambiente produtivo, podendo ser retestados ou ter a evidência validada, de acordo com a indicação do apontamento. Importante : Nesse status há parada na contagem de tempo do SLA da Instituição Financeira, indicando a finalização da correção dos apontamentos, e o ticket é direcionado para a fila de atendimento da DTO para validação da correção da não conformidade.
**O Atendimento da Jornada UX irá verificar se as evidências necessárias foram disponibilizadas** no ticket. Caso não tenham sido disponibilizadas, as mesmas **serão solicitadas através da atualização da Nota do ticket e devolução do ticket para o status “ENCAMINHADO N2 ATENDIMENTO”.** Estando todas as evidências disponíveis, a Estrutura poderá realizar a validação da correção da não conformidade. Caso entenda que é necessário realizar o reteste pelo fornecedor, a estrutura irá realizar a solcitação de reteste e o ticket será atualizado para “**AGUARDANDO VALIDAÇÃO DA NÃO CONFORMIDADE**”.**SLA para Validação da Não Conformidade (reteste):** 5 dias úteis
## Fluxo de Validação da Correção da Não Conformidade

### Detalhamento

1. Após o ticket ser encaminhado para AGUARDANDO VALIDAÇÃO DA NÃO CONFORMIDADE, a equipe responsável irá realizar o reteste e, tendo todos os apontamentos sido corrigidos, o ticket é ENCERRADO; Havendo alguma pendência na solução da correção da não conformidade, o ticket é redirecionado para a equipe N2 da INSTITUIÇÃO FINANCEIRA responsável para ajustes.

## Critérios Mínimos para Geração da Evidência
Para viabilizar a validação da correção da não conformidade por validação de evidência, foram estabelecidos os seguintes critérios mínimos:
- Evidência deve ser gerada, prioritariamente, com o mesmo formato da evidência do apontamento: Vídeo gerado em ambiente produtivo Tratamento adequado aos dados sensíveis do usuário Apresentar a minutagem do vídeo onde mostra a correção realizada Repetir os passos da jornada apresentados no vídeo de evidência do apontamento da não conformidade (disponibilizado no momento da abertura do ticket)

- Caso não seja possível gerar a evidência em vídeo, será permitido o envio de: Captura da tela do app ou do browser em ambiente produtivo Tratamento adequado aos dados sensíveis do usuário Destacar na captura onde a correção foi realizada Apresentar a captura de toda jornada ou, no mínimo, da tela anterior e posterior à tela onde foi feita a correção, além da própria captura da tela da correção
**Ponto de atenção**
A mesma evidência pode ser utilizada para apresentar a correção de mais de um apontamento, desde que, seja informada a minutagem da correção de cada apontamento ou o destaque em tela das correções, para os casos de envio de captura de tela

## Documentos anexados aos tickets de Não conformidade
Os tickets de não conformidade do Ciclo de Monitoramento são encaminhados às Instituições Financeiras contendo dois arquivos:
1. Relatório pdf com os apontamentos de não conformidades, erros técnicos ou impedimento
2. Arquivo xlsx que, além dos com os apontamentos de não conformidades, erros técnicos ou impedimento, contém as informações para acompanhamento da correção dos apontamentos, devendo ser utilizadas da seguinte forma: "Status da correção", a Instituição deve informar se o apontamento já foi corrigido ou se tem previsão de correção "Detalhes para a correção", a Instituição colocar a descrição da correção ou da previsão de correção "Data da correção", a Instituição deve colocar a data da correção realizada ou prevista para realizar "Status após a validação de Evidência ou Reteste", a estrutura do OFB irá atualizar após a realização da validação das evidências ou do reteste.