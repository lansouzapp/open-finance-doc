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