# Ciclo Monitoramento da Jornada do Cliente > 11º Ciclo de Monitoramento da Jornada UX - Em andamento

---
id: 551059530
title: 11º Ciclo de Monitoramento da Jornada UX - Em andamento
version: 10
modified: 2026-01-27T18:28:39.748Z
url: /spaces/OF/pages/551059530/11+Ciclo+de+Monitoramento+da+Jornada+UX+-+Em+andamento
---

Atualização mensal
### Período

- Dezembro a Março/2025

### Versão do Guia de UX

- Neste ciclo, a versão do Guia de UX utilizada como referência é a 15.00.00 de 30/09/2025

### Escopo

- Serão monitoradas as jornadas de Jornada sem Redirecionamento (Vinculação de Conta, Pagamento sem Redirecionamento e Gestão de Vínculo de Conta)
- Todas as marcas selecionadas para participação serão monitoradas como:  Iniciadora e Detentora, quando aplicável
- Segmentos PF
- Ambiente App, a não ser quando a marca/cenário testado exija uso de outro ambiente
- Sistema Operacional, Android ou iOS
- Alçada simples

### Marcas Detentoras Participantes

| Marcas | |
| --- | --- |
| Bradesco Pessoa Física BTG Banking C6 Bank Banco do Brasil Banco Santander Pessoa Física CAIXA Sicredi Sicoob Itaú Mercado Pago Nubank PagBank | banco Digio Banco Inter Pagamentos PF Banco PAN Banco BV Neon PicPay Quero-quero PAG Next Uber Conta by Digio CAIXA Tem Íon Player’s Bank Porto Bank |

### Marcas Iniciadoras Participantes

| Marcas |
| --- |
| Carteira Google Cumbuca Iniciador.com Lina OPX Belvo BTG Celcoin |

### Cronograma

| Atividade | Período |
| --- | --- |
| Planejamento e Preparação | de 24/11 a 05/12 de 22/01 a 04/02 |
| Comunicação às Instituições Financeiras | 19/12/2025 |
| Captura e avaliação | de 10/12 a 19/12/2025 de 05/01 a 23/01/2026 de 04/02 a 24/02/2026 |
| Abertura dos tickets de Não Conformidade | 05/01/2026 a 09/01/2026 30/01/2026 a 06/02/2026 19/02/2026 a 25/02/2026 03/03/2026 a 06/06/2026 |
| Checkpoint de acompanhamento | 16/12/2025 15/01/2026 30/01/2026 16/02/2026 03/03/2026 |
| Apresentação Final do Ciclo de Monitoramento | 10/03/2026 |

---

# Ciclo Monitoramento da Jornada do Cliente > Gestão dos tickets de Não Conformidade

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

---

# Ciclo Monitoramento da Jornada do Cliente > Histórico dos Ciclos de Monitoramento da Jornada UX

---
id: 551059645
title: Histórico dos Ciclos de Monitoramento da Jornada UX
version: 10
modified: 2025-12-17T20:44:41.845Z
url: /spaces/OF/pages/551059645/Hist+rico+dos+Ciclos+de+Monitoramento+da+Jornada+UX
---

16falsedefaultlisttrue
## Quadro resumo

| Ciclo | Escopo |
| --- | --- |
| Ciclo 10 | Jornadas de Transferências Inteligentes Segmentos PF e PJ Alçada simples |
| Ciclo 09 | Homologar novas Transmissoras de Dados para 3 jornadas do escopo de compartilhamentos de dados (novo consentimento, consulta ao ambiente de gestão e revogação). Segmento PF e PJ Ponto de Atenção: O saldo de vagas não ocupadas pelo escopo acima será remanejar para o Piloto de Pix Automático , onde seria possível homologar marcas Detentoras que, no plano inicial, haviam sido selecionadas para participação, mas foram despriorizadas. |
| Ciclo 08 | Monitorar as jornadas infelizes para novos consentimentos e novos pagamentos Segmento PJ Alçada Simples e Múltipla |
| Ciclo 07 | Jornadas de gestão do consentimento Segmentos PF e PJ |
| Ciclo 06 | Jornadas de compartilhamento de dados Segmentos PF Alçada simples e múltipla em App |
| Ciclo 05 | Jornadas de compartilhamento de dados Segmentos PJ Alçada simples e múltipla em App |
| Ciclo 04 | Iniciação de PIX imediato Segmentos PF e PJ Alçada Simples e Múltipla m App |
| Ciclo 03 | Gestão do Consentimento e Iniciação de Novo Pagamento Segmento PF e PJ Alçada Simples em APP |
| Ciclo 02 | Cenários de erro, cancelamento e estresse Segmento PF Alçada Simples |
| Ciclo 01 | Criação de Novo Consentimento e Iniciação de Novo Pagamento Segmento PF e PJ Alçada Simples e Múltipla |

## Ciclo 1 de Monitoramento da Jornada UX
**Período**
- Dezembro /2023 e Janeiro /2024
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 4.10.04 de 17/10/2023
**Escopo**
- Criação de Novo Consentimento
- Iniciação de Novo Pagamento
- Segmento PF e Pj
- Alçada Simples e Mútipla em APP
**Marcas Participantes**
| Detentora PF | Detentora PJ | Iniciadora PF | Receptora PF | Transmissora PF | Transmissora PJ |
| --- | --- | --- | --- | --- | --- |
| Banco do Brasil Bradesco Caixa C6 Itaú Mercado Pago Neon Nubank PagBank PicPay Santander Sicoob | Bradesco Caixa C6 Inter Mercado Pago Nubank PicPay Santander | Banco do Brasil Bradesco BTG BV Inter Itaú Mercado Pago Nubank PicPay Sicoob Sicredi XP | Banco do Brasil Bradesco Caixa Itaú Mercado Pago Nubank Pan PicPay Santander | Banco do Brasil Bradesco Caixa Itaú Mercado Pago Nubank PicPay Santander XP | Banco do Brasil BTG Caixa Mercado Pago Nubank PicPay Santander Sicoob Sicredi |

## Ciclo 2 de Monitoramento da Jornada UX
**Período**
- Fevereiro e Março /2024
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 6.00.00 de 22/12/2023
**Escopo**
- Cenários de erro, cancelamento e estresse
- Segmento PF
- Alçada Simples em App
**Marcas Participantes**
| Detentora | Iniciadora | Receptora | Transmissora |
| --- | --- | --- | --- |
| BMG C6 Banco do Brasil Banco Pan Bradesco BTG Banking Caixa Inter Itaú Iti Mercado Pago Neon Next Nubank PagBank Picpay Players Bank Rico Santander Sicoob Sicredi Superdigital XP | Banco do Brasil Inter Nubank Picpay Rico Sicredi XP | Banco do Brasil Banco Pan Bradesco BTG Investimentos Investimentos BB Itaú Iti Mercado Pago Next Nubank Ourocard Picpay Players Bank Rico Santander Santander Cartões PF (Way) Santander Financiamentos Sicredi XP | BMG Banco do Brasil Banco Pan Bradesco BTG Banking BTG Investimentos Caixa Empréstimo Sim Getnet Investimentos BB Itaú Itaúcard Iti Mercado Pago Next Nubank Olé Consignado Ourocard Picpay Players Bank Rico Santander Santander Cartões PF (Way) Santander Financiamentos Sicoob Sicredi Superdigital Toro XP |

## Ciclo 3 de Monitoramento da Jornada UX
**Período**
- Abril e Maio /2024
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 7.00.00 de 07/03/2024
**Escopo**
- Gestão do Consentimento Renovação, Revogação, Alteração e Consulta
- Iniciação de Novo Pagamento
- Segmento PF e PJ
- Alçada Simples em APP
**Marcas Participantes**
| Receptora PF | Receptora PJ | Transmissora PF | Transmissora PJ |
| --- | --- | --- | --- |
| Ágora Investimentos Azimut Brasil Banco BMG Banco do Brasil Banco PAN Banco XP Bradesco BTG Banking BTG Investimentos Caixa Cartão Luiza Credi Nissan Credicard Empréstimo Sim Getnet Hipercard Hyundai Financiamentos Investimentos BB Íon Itaú Itaúcard Iti Mercado Pago Next Nubank Olé consignado Ourocard PicPay Player's Bank Rede Rico Santander Santander Cartões Santander Corretora Santander Financiamentos Sicoob Sicredi Superdigital Toro Volvo Car Financial Services | Ágora Investimentos Banco BMG Banco do Brasil Banco XP Bradesco BTG Empresas Caixa Getnet Itaú Empresas Mercado Pago Nubank PicPay Rede Santander Santander Cartões Santander Corretora Sicoob Sicredi Superdigital Toro | Banco do Brasil Ágora Investimentos Azimut Brasil Banco BMG Banco do Brasil Banco PAN Banco XP Bradesco BTG Banking BTG Investimentos Caixa Cartão Luiza Credi Nissan Credicard Empréstimo Sim Getnet Hipercard Hyundai Financiamentos Investimentos BB Íon Itaú Itaúcard Iti Mercado Pago Next Nubank Olé Consignado Ourocard PicPay Player's Bank Rede Rico Santander Santander Cartões Santander Corretora Santander Financiamentos Sicoob Sicredi Superdigital Toro Volvo Car Financial Services | Ágora Investimentos Banco BMG Banco do Brasil Banco XP Bradesco BTG Empresas Caixa Getnet Itaú Empresas Mercado Pago Nubank PicPay Rede Santander Santander Cartões Santander Corretora Sicoob Sicredi Superdigital Toro |

## Ciclo 4 de Monitoramento da Jornada UX
**Período**
- Junho e Julho /2024
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 7.02.00 de 24/05/2024
**Escopo**
- Iniciação de PIX imediato
- Segmentos PF e PJ
- Alçada Simples e Múltipla m App
**Marcas Participantes**
| Detentora PF | Detentora PJ | Iniciadora PF | Iniciadora PJ |
| --- | --- | --- | --- |
| Azimut Banco do Brasil Banco Pan BMG Bradesco BTG Banking C6 Caixa Inter Íon Itaú Iti Mercado Pago Neon Next Nubank PagBank PicPay Players Bank Rico Santander Sicoob Sicredi Superdigital XP | Banco do Brasil BMG Bradesco BTG Banking C6 Caixa Inter Itaú MEI Fácil Mercado Pago Nubank PagBank PicPay Santander Sicoob Sicredi Superdigital XP | Banco do Brasil Bradesco BTG Banking Inter Itaú Mercado Pago Nubank PicPay Rico Sicoob Sicredi XP | Banco do Brasil Nubank Santander Sicoob Sicredi |

## Ciclo 5 de Monitoramento da Jornada UX
**Período**
- Agosto e Setembro /2024
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 7.03.00 de 28/06/2024
**Escopo**
- Jornadas de compartilhamento de dados
- Segmentos PJ
- Alçada simples e múltipla em App
**Marcas Participantes**
| Marcas PJ | |
| --- | --- |
| Ágora Investimentos Banco Bmg S.A Banco do Brasil Banco XP S.A. (XP Empresas) Bradesco Cartões PJ Bradesco Financiamento Bradesco Pessoa Jurídica BTG Empresas Caixa Credi Nissan Getnet Hyundai Financiamentos Itaú Itaucard | Mercado Pago Mobilize Financial Services Nubank PicPay Negócios Rede Santander Santander Cartões Pessoa Jurídica Santander Corretora Pessoa Jurídica Santander Crédito Imobiliário Santander Financiamentos Sicoob Sicredi Superdigital Toro Volvo Car Financial Services |

## Ciclo 6 de Monitoramento da Jornada UX
**Período**
- Outubro e Novembro /2024
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 7.03.01 de 26/08/2024
**Escopo**
- Jornadas de compartilhamento de dados
- Segmentos PF
- Alçada simples e múltipla em App
**Marcas Participantes**
| Marcas PF | | |
| --- | --- | --- |
| Ágora Investimentos Azimut Brasil Banco Bmg S.A Banco Digio​ Banco do Brasil Banco Pan Banco RCI - Brasil​ Banco XP S.A. Bradescard Bradesco Bradesco Financiamento BTG Banking BTG Investimentos Caixa CAIXA Tem​ Cartão Luiza Clear Corretora - Nativo​ Clear Corretora​ Credi Nissan | Credicard Empréstimo SIM EQI​ Getnet Hipercard Hyundai Financiamentos Investimentos BB Íon Itaú Itaucard Iti Losango Mercado Pago Mobilize Financial Services Monte Bravo​ Necton​ Next Nubank Olé Consignado | Ourocard PicPay Player's Bank Porto Bank​ Rede Rico Santander Santander Cartões Pessoa Física Santander Corretora PF Santander Crédito Imobiliário Santander Financiamentos Sicoob Sicredi Superdigital Toro Uber Conta by Digio​ Volvo Car Financial Services WHG​ |

## Ciclo 7 de Monitoramento da Jornada UX
**Período**
- Dezembro/2024 a Março/2025
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 10.00.00 de 20/12/2024
**Escopo**
- Jornadas de gestão do consentimento
- Segmentos PF e PJ
- Ambiente app (iOS ou em Android)
- Ambiente web (browser desktop)
**Marcas Participantes**
| Marcas | |
| --- | --- |
| Bradescard - PF Bradesco - PF next - PF Bradesco - PJ Banco PAN - PF BTG Banking - PF BTG Empresas - PJ Banco do Brasil - PF Banco do Brasil - PJ PicPay - PF Banco Bmg S.A - PF Banco Bmg S.A - PJ Banco Santander - PF Santander Cartões - PF Banco Santander - PJ Santander Cartões - PJ | Banco XP S.A. - PF Banco XP S.A. (XP Empresas) - PJ CAIXA Tem - PF CAIXA - PF CAIXA - PJ Sicredi - PF Sicredi - PJ Sicoob - PF Sicoob - PJ Íon - PF Itaú - PF Itaú - PJ Itaucard - PF Itaucard - PJ Mercado Pago - PF Mercado Pago - PJ Nubank - PF Nubank - PJ |

## Ciclo 8 de Monitoramento da Jornada UX
**Período**
- Abril/2024 a Junho/2025
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 10.02.01 de 18/03/2025
**Escopo**
- Monitorar as jornadas infelizes para novos consentimentos e novos pagamentos
- Segmento PJ
- Alçada Simples e Múltipla
- Ambiente app (iOS e Android) e
- Ambiente web (browser desktop) quando necessário
**Marcas Participantes**
| Marcas | |
| --- | --- |
| Banco Bmg S.A Banco do Brasil Inter Santander Banco XP S.A. (XP Empresas) Bradesco BTG Empresas C6 Bank | Caixa Itaú Mercado Pago Nubank PagBank Sicoob Sicredi |

## Ciclo 9 de Monitoramento da Jornada UX
**Período**
- Julho/2025 a Setembro/2025
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 11.00.00 de 04/04/2025
**Escopo**
- Homologar novas Transmissoras de Dados para 3 jornadas do escopo de compartilhamentos de dados (novo consentimento, consulta ao ambiente de gestão e revogação)
- Segmento PF e PJ
- Sistema Operacional: Android e iOS para PF Desktop e Android para PJ; caso a não possua jornada em navegador, será avaliado o aplicativo em sistema iOS
- Alçada simples
**Ponto de Atenção**: O saldo de vagas não ocupadas pelo escopo acima será remanejar para o Piloto de Pix Automático, onde seria possível homologar marcas Detentoras que, no plano inicial, haviam sido selecionadas para participação, mas foram despriorizadas.**Marcas Transmissoras Participantes**
| Marcas | |
| --- | --- |
| Inter - PF e PJ Banco CSF S.A - PF CREFISA - PF BRB - Banco de Brasília SA - PF e PJ Pagseguro - PF e PJ | C6 Bank - PF e PJ 99Pay - Instituição de Pagamento S.a. - PF Banco Master S.A - PF Banco Mercantil - PF e PJ MIDWAY - PF |

## Ciclo 10 de Monitoramento da Jornada UX
**Período**
- Outubro/2025 a Dezembro/2025
**Versão do Guia de UX**
- Neste ciclo, a versão do Guia de UX utilizada como referência é a 13.00.00 de 27/07/2025
**Escopo**
- Serão monitoradas as jornadas de Transferências Inteligentes em ambiente produtivo, simulando as jornadas de Criação de novas autorização para Transferência Inteligentes,  Execução de novas Transferências Inteligentes, Consulta e revogação das autorizações realizadas
- Todas as marcas selecionadas para participação serão monitoradas como:  Iniciadora e Detentora, quando aplicável
- Segmentos PF e PJ
- Ambiente App, a não ser quando a marca/cenário testado exija uso de outro ambiente
- Sistema Operacional, Android ou iOS
- Alçada simples
**Marcas Detentoras Participantes**
| Marcas | |
| --- | --- |
| Banco Bmg S.A PF e PJ Banco do Brasil PF e PJ Banco PAN PF Banco Santander PF e PJ Banco XP S.A. PF e PJ Bradesco PF e PJ BTG PF e PJ C6 PF e PJ CAIXA PF e PJ CAIXA Tem PF Digio PF | Inter PF e PJ Íon PF Itaú PF e PJ Iti PF Mercado Pago PF e PJ Neon PF e PJ next PF Nubank PF e PJ PagBank PF e PJ PicPay PF Sicoob PF e PJ Sicredi PF e PJ |
**Marcas Iniciadoras Participantes**
| Marcas |
| --- |
| Mercado Pago PF e PJ Nubank PF e PJ Pag Bank PF e PJ Bradesco PF e PJ |

---

# Ciclo Monitoramento da Jornada do Cliente > Próximos Ciclos de Monitoramento da Jornada UX

---
id: 551059575
title: Próximos Ciclos de Monitoramento da Jornada UX
version: 5
modified: 2025-12-19T14:47:24.471Z
url: /spaces/OF/pages/551059575/Pr+ximos+Ciclos+de+Monitoramento+da+Jornada+UX
---

16falsedefaultlisttrue
## Ciclo 12 de Monitoramento da Jornada UX

### Período

- A ser definida

### Versão do Guia de UX

- A ser definida

### Escopo

- A ser definido

### Marcas Participantes

| Marcas |
| --- |
| A ser definido |
| |