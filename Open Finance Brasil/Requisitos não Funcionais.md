# Desempenho

---
id: 17891396
title: Desempenho
version: 4
modified: 2024-03-27T16:23:19.833Z
url: /spaces/OF/pages/17891396/Desempenho
---

Deverá ser medido o tempo de resposta de cada requisição, ou seja, o tempo transcorrido entre o recebimento de uma requisição que não ultrapassa os limites de tráfego e o momento em que a requisição é completamente respondida.Adicionalmente, esta medição deverá ser feita de maneira que os tempos medidos sejam os mais próximos possíveis dos tempos de resposta experimentados por quem fez a requisição. Neste contexto, os *endpoints*das APIs deverão manter o percentil 95 do tempo de resposta em no máximo:I. 1.500ms, em endpoints classificados como de alta e média-alta frequências;II. 2.000ms, em endpoints classificados como de média frequência;III. 4.000ms, em endpoints classificados como de baixa frequência.Por exemplo, em um dia que um *endpoint*de alta frequência receba 10.000 requisições, o tempo de resposta de pelo menos 9.500 requisições deve ser inferior a 1.500ms.

---

# Disponibilidade

---
id: 17891406
title: Disponibilidade
version: 10
modified: 2024-06-03T13:41:42.326Z
url: /spaces/OF/pages/17891406/Disponibilidade
---

Todos os endpoints das APIs classificadas como ‘Dados Abertos’, ‘Dados Cadastrais e Transacionais’ e ‘Relatórios e métricas’, deverão satisfazer requisitos mínimos de disponibilidade abaixo. Cada um de seus endpoints deverá estar disponível:I.95% do tempo a cada 24 horas;II.99,5% do tempo a cada 3 meses (calculado de acordo com os dados enviados pelas instituições).Sendo que para o cálculo da disponibilidade diária considera-se:  As métricas devem respeitar a individualidade do endpoint implementado pela instituição, isto é: deve-se enviar cada endpoint separadamente, conforme exemplo abaixo, no máximo nível de granularidade:i. [https://example.api/open-banking/financings/v2/contracts](https://example.api/open-banking/financings/v2/contracts)ii. [https://example.api/open-banking/financings/v2/contracts/contractId](https://example.api/open-banking/financings/v2/contracts/contractId)iii. [https://example.api/open-banking/financings/v2/contracts/contractId/warranties](https://example.api/open-banking/financings/v2/contracts/contractId/warranties)iv. [https://example.api/open-banking/financings/v2/contracts/contractId/scheduled-instalments](https://example.api/open-banking/financings/v2/contracts/contractId/scheduled-instalments)v. [https://example.api/open-banking/financings/v2/contracts/contractId/payments](https://example.api/open-banking/financings/v2/contracts/contractId/payments)vi. [https://example.api/open-banking/financings/v2/contracts/{contractId}](https://example.api/open-banking/financings/v2/contracts/%7BcontractId%7D)vii. [https://example.api/open-banking/financings/v2/contracts/{contractId}/warranties](https://example.api/open-banking/financings/v2/contracts/%7BcontractId%7D/warranties)viii. [https://example.api/open-banking/financings/v2/contracts/{contractId}/scheduled-instalments](https://example.api/open-banking/financings/v2/contracts/%7BcontractId%7D/scheduled-instalments)ix. [https://example.api/open-banking/financings/v2/contracts/{contractId}/payments](https://example.api/open-banking/financings/v2/contracts/%7BcontractId%7D/payments)Observação: Endpoint com path variable, a exemplo {contractId}, podem ser enviados com ou sem chaves {}.Todos os endpoints das APIs classificadas como ‘Serviços’ deverão possuir a mesma disponibilidade do arranjo de pagamento ou do serviço aos quais estão associadas.A disponibilidade é checada no endpoint GET /discovery/status, conforme documentada no item [API de Status](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/17377105/Informa+es+Gerais+-+APIs+Comuns+-+v1.0.2).A cada 30 segundos, a API de status é requisitada com timeout de 1s.Será considerado *uptime*, se o retorno for:
- OK.
Será considerado *downtime*, se o retorno for:
- PARTIAL_FAILURE
- SCHEDULED_OUTAGE Se a requisição for realizada entre o período de 01h e 07h, o contador de SCHEDULED_OUTAGE é iniciado com 30 segundos acrescidos Cada nova requisição vai adicionando 30 segundos ao contador de SCHEDULED_OUTAGE, até que uma requisição volte outro valor ou a requisição for feita depois das 7h
- UNAVAILABLE Se a requisição for realizada entre o período de 7h e 1h Se serviço não responder a requisição O contador de downtime é iniciado com 30 segundos acrescidos Cada nova requisição adicionará 30 segundos ao contador de downtime , até que uma requisição retorne OK
O *downtime*deve ser calculado como o número total de segundos simultâneos por requisição da API, por período de 24 horas, começando e terminando à meia-noite, que qualquer endpoint da API não esteja disponível, dividido por 86.400 (total de segundos em 24 horas) e expresso como uma porcentagem.A disponibilidade é calculada sendo 100% menos a quantidade em percentual da indisponibilidade.
- De modo geral, consideram-se os erros HTTP Status Code 5XX como erros do servidor, e portanto, atribuíveis ao servidor das APIs
- Erros baseados em HTTP Status Code 4XX são, em grande parte, atribuídos a ações ou falhas dos clientes, e desta forma, não devem ser incluídos no cálculo

---

# Limites de tráfego

---
id: 17989722
title: Limites de tráfego
version: 10
modified: 2025-06-13T14:16:10.832Z
url: /spaces/OF/pages/17989722/Limites+de+tr+fego
---

17
## Limites por origem - TPM (Transações por minuto)
 **Limites por origem - TPM (Transações por minuto)**Existem dois tipos de origem quando analisamos o tráfego de dados, desconsiderando o tráfego interno da instituição:
- IP: aplicado aos endpoints que não demandam autenticação;
- Instituição ou organizationId: aplicado aos endpoints autenticados.
Os limites, quando implementados, são definidos por *endpoint* e por origem como segue:
- Alta frequência: De acordo com o número de consentimentos possuídos por uma determinada instituição receptora de dados com uma determinada instituição transmissora de dados: Quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2.500 1 000 000 < QCA ≤ 2 000 000 → 5.000 2 000 000 < QCA ≤ 3 000 000 → 8.000 3 000 000 < QCA ≤ 6 000 000 → 10.000 Para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2.000 ao limite da faixa anterior (ex.: 6-8 MM → 12.000 TPM)
- Média-alta frequência: 2.000 TPM
- Média frequência: 1.500 TPM
- Baixa frequência: 1.000 TPM
Para contabilização dos limites de tráfego, tanto transmissoras como receptoras, devem considerar minuto cheio, ou seja, é preciso zerar o contador a cada minuto. Assim, tipicamente, a contabilização deve começar no início do minuto (00s000ms) e terminar no final do minuto (59s999ms). Como por exemplo:
- O servidor começa a receber requisições em 10h25m55s123ms. O servidor deve contabilizar até 10h25m59s999ms;
- Deve-se contabilizar a cada minuto: 10h25m00s000ms até 10h25m59s999ms, depois zerar e contar 10h26m00s000ms até 10h26m59s999ms.
Nos casos abaixo não são aplicáveis limites por origem:
- APIs de Segurança: Token: consumo OAuth 2.0 (FAPI) Token: DCR/DCM
- APIs de Consentimento ( Consents )
- APIs de Recursos ( Resources )
- Grupo de APIs de Serviços
O erro HTTP *Status* *Code* 429 (*Too many requests*) passa a ser utilizado de forma exclusiva para pedidos de consumo que excedam os limites de TPM.Por fim, as requisições que ultrapassarem os limites deverão ser desprezadas no cálculo do tempo de resposta das implementações das APIs.
## Limites globais - TPS (Transações por segundo)
A infraestrutura das instituições provendo APIs no Open Finance (Dados Abertos, Dados Cadastrais e Transacionais, Serviços, Relatórios e Métricas, Segurança) deve ter a capacidade de, no mínimo, atender a 300 requisições simultâneas por segundo (TPS), desconsiderando chamadas internas.Caso o limite de 300 TPS seja atingido, no contexto do Open Finance, a instituição deve ampliar sua capacidade de infraestrutura para possibilitar um acréscimo de 150 TPS ao limite anterior. Tal aumento deve ocorrer novamente a cada vez que o limite vigente na instituição for atingido. Cada instituição deve criar monitoramento preventivo, de acordo com critérios definidos; as evidências devem estar à disposição do Banco Central do Brasil por um período de doze meses.Fica definida a utilização do código HTTP *Status* *Code* 529 (*Site is overloaded*) para retorno quando atingido o limite de TPS estabelecido.*Endpoints* criados dentro do conceito de extensibilidade, sejam dentro de novas APIs ou em APIs existentes, não podem ser considerados para controle do limite global de transações simultâneas.
- Gatilho para ampliação do TPS
- O aumento do limite deve ocorrer novamente, a cada vez que o limite vigente naquela instituição for atingido
- Cada instituição precisará realizar este cálculo preventivamente
- Caso a instituição tenha aumentado a sua infraestrutura para disponibilizar um TPS maior do que os 300, mas tenha elasticidade para diminuir de acordo com a demanda, poderá fazer isso até o limite mínimo de 300 TPS
- Formato de cálculo para monitoramento: Limite máximo de 10% de atingimento de 90% do TPS estabelecido por quinzena, em 3 quinzenas consecutivas Cálculo de TPS a cada 1 segundo Contador de segundos com TPS maior que 90% do regulamento atual (inicial 270 TPS) Caso ao final da quinzena o contador atinja um número maior que 10%, a quinzena deve ser contabilizada Caso a instituição contabilize 3 quinzenas consecutivas ultrapassando o limite percentual, o TPS deve ser acrescido em 150 TPS ao limite anterior O tempo para adequação deve ser de no máximo 2 meses após a identificação do gatilho

---

# Limites operacionais

---
id: 17924220
title: Limites operacionais
version: 5
modified: 2025-06-13T14:16:45.395Z
url: /spaces/OF/pages/17924220/Limites+operacionais
---

É facultado às instituições participantes implementarem um limite de acesso mensal por *endpoint* e por cliente.Em *endpoints* que acessem recursos ou produtos, os limites serão também considerados por recurso ou produto.A contabilização dos acessos deve ser realizada por:I. mêsII. endpointIII. objeto mais granular referenciado na chamada (consentimento/recurso/produto)IV. cliente (CPF ou CNPJ)V. instituição consumidora da informaçãoPor exemplo: uma instituição receptora ‘A’ pode acessar um endpoint ‘B’, acessando o recurso ‘C’, de um cliente “D” da instituição transmissora ‘E’, no mínimo ‘N’ vezes (ou chamadas) com sucesso por mês.Aplicabilidade dos limites operacionais: todos *endpoints* das APIs do tipo Dados Cadastrais e Transacionais (conforme classificação de Tipo), destes excetuam-se aqueles *endpoints* das APIs de Consentimento (*Consents*) e Recursos (*Resources*). As APIs de Segurança, de Dados Abertos e de Serviços (como de Iniciação de Pagamento) não podem ter restrições de limites operacionais.A implementação dos limites operacionais é opcional pelas instituições transmissoras, mas, uma vez que sejam implementados, devem garantir o consumo mínimo. É facultada à instituição a possibilidade de ampliar esses limites, mas vedada a implementação de limites inferiores aos estabelecidos.Os valores mínimos de limites operacionais a serem considerados, por *endpoint*, que devem ser iguais ou maiores que os abaixo, de acordo com a classificação de frequência de utilização:I. 8 chamadas ao mês, para endpoint classificado como de baixa frequênciaII. 30 chamadas ao mês, para *endpoint* classificados como de média frequênciaIII. 120 chamadas ao mês, para *endpoint* classificado como de média-alta frequênciaIV. 240 chamadas ao mês, para *endpoint* classificado como de alta frequênciaV. 420 chamadas ao mês, para os seguintes *endpoints* da API de Contas: ‘Saldos da conta’ e ‘Limites da conta’Só deverão ser contabilizadas nos limites operacionais requisições respondidas com HTTP *Status* *Code* 2XX, sendo que as requisições adicionais a um endpoint para fins de paginação não devem ser contabilizadas.As requisições que excederem os limites operacionais deverão ser respondidas com o HTTP *Status* *Code* 423.Todas as requisições autenticadas em *endpoints* sujeitos ao limite operacional devem possuir o atributo *x-fapi-interaction-id* preenchido no seu *header* pela receptora, que deve ser copiado pela transmissora nos *headers* da resposta. Essa definição objetiva permitir um adequado rastreamento de divergências que podem ocorrer entre transmissoras e receptoras associadas ao limite operacional.
## Paginação no contexto dos limites operacionais
Para a não contabilização de rechamadas, considerando que eventuais chamadas que possuam paginação devam ser interpretadas como uma única chamada, foi estabelecido a criação de um *query* *parameter* adicional para funcionar como identificador de rechamadas.
- Esse novo parâmetro deve ter o nome pagination-key .
- Cabe à Transmissora criar o identificador e enviá-lo via HATEOAS no retorno da chamada.
- O tempo máximo de utilização do identificador pelo Receptor é de 60 minutos.
- A Transmissora deve implementar validações para garantir a coerência da utilização do identificador, de acordo com as regras de limites operacionais.
- Caso a Receptora utilize um pagination-key inválido ou expirado, a Transmissora deverá gerar um novo pagination-key retornando o resultado com sucesso. Esta chamada será contabilizada para os limites operacionais.
- Essa implementação deve ser realizada em todos endpoints atuais com paginação.
- A Transmissora poderá gerar um único ID para controle das chamadas das próximas páginas.

## Exemplo do uso do pagination-key
**Primeira chamada**GET /accounts/v2/accounts/12345678/transactions?page=1&page-size=1000**Próximas chamadas**GET /accounts/v2/accounts/12345678/transactions?page=2&page-size=1000&pagination-key=123456

---

# Referência

---
id: 17957025
title: Referência
version: 24
modified: 2025-12-01T13:35:05.000Z
url: /spaces/OF/pages/17957025/Refer+ncia
---

## Relatórios e Métricas

| API Admin |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /metrics | Baixa | 4000 | 15 | NA | NA | NA |

| API Comum (Discovery) |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /status | Baixa | 4000 | 15 | NA | NA | NA |
| GET /outages | Baixa | 4000 | 15 | NA | NA | NA |

## Dados Abertos

| [DA] API Produtos e Serviços |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /personal-accounts | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-accounts | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-loans | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-loans | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-credit-cards | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-credit-cards | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-invoice-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-invoice-financings | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personal-unarranged-account-overdraft | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /business-unarranged-account-overdraft | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Canais de Atendimento |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /banking-agents | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /branches | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /electronic-channels | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /phone-channels | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /shared-automated-teller-machines | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Títulos de Capitalização |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /bonds | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Investimentos |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /funds | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /bank-fixed-incomes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /credit-fixed-incomes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /variable-incomes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /treasure-titles | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Câmbio |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /online-rates | Alta | 1500 | 15 | 500 | 300 | NA |
| GET /vet-values | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Credenciamento |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /businesses | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personals | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Previdência |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /risk-coverages | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /survival-coverages | Baixa | 4000 | 15 | 500 | 300 | NA |

| [DA] API Seguros |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /automotives | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /homes | Baixa | 4000 | 15 | 500 | 300 | NA |
| GET /personals | Baixa | 4000 | 15 | 500 | 300 | NA |

## Dados do Cliente

| [DC] API Consentimento |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| POST /consents | Alta | 1500 | 15 | NA | 300 | NA |
| GET /consents​/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| DELETE /consents​/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST /consents/{consentId}/extends​ | Baixa | 4000 | 15 | NA | 300 | NA |
| GET /consents/​{consentId}/extensions​ | Baixa | 4000 | 15 | NA | 300 | NA |

| [DC] API Recursos |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /resources | Alta | 1500 | 15 | NA | 300 | NA |

| [DC] API Dados Cadastrais |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/personal​/identifications | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/personal​/qualifications | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/personal​/financial-relations | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/business​/identifications | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/business​/qualifications | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/business​/financial-relations | Baixa | 4000 | 15 | 1000 | 300 | 8 |

| [DC] API Cartão de Crédito |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/accounts | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/accounts​/{creditCardAccountId} | Média-Alta | 1500 | 15 | 2000 | 300 | 120 |
| GET ​/accounts​/{creditCardAccountId}​/bills | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/accounts​/{creditCardAccountId}​/bills​/{billId}​/transactions | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/accounts​/{creditCardAccountId}​/limits | Alta | 1500 | 15 | a) quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2 500 1 000 000 < QCA ≤ 2 000 000 → 5 000 2 000 000 < QCA ≤ 3 000 000 → 8 000 3 000 000 < QCA ≤ 6 000 000 → 10 000 b) para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2 000 ao limite da faixa anterior (ex.: 6-8 MM → 12 000 TPM). | 300 | 240 |
| GET ​/accounts​/{creditCardAccountId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/accounts​/{creditCardAccountId}​/transactions-current | Alta | 1500 | 15 | a) quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2 500 1 000 000 < QCA ≤ 2 000 000 → 5 000 2 000 000 < QCA ≤ 3 000 000 → 8 000 3 000 000 < QCA ≤ 6 000 000 → 10 000 b) para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2 000 ao limite da faixa anterior (ex.: 6-8 MM → 12 000 TPM). | 300 | 240 |

| [DC] API Contas |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/accounts | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/accounts​/{accountId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/accounts​/{accountId}​/balances | Alta | 1500 | 15 | a) quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2 500 1 000 000 < QCA ≤ 2 000 000 → 5 000 2 000 000 < QCA ≤ 3 000 000 → 8 000 3 000 000 < QCA ≤ 6 000 000 → 10 000 b) para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2 000 ao limite da faixa anterior (ex.: 6-8 MM → 12 000 TPM). | 300 | 420 |
| GET /accounts/{accountId}/reserved-balances | Alta | 1500 | 15 | a) quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2 500 1 000 000 < QCA ≤ 2 000 000 → 5 000 2 000 000 < QCA ≤ 3 000 000 → 8 000 3 000 000 < QCA ≤ 6 000 000 → 10 000 b) para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2 000 ao limite da faixa anterior (ex.: 6-8 MM → 12 000 TPM). | 300 | 420 |
| GET ​/accounts​/{accountId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/accounts​/{accountId}​/transactions-current | Alta | 1500 | 15 | a) quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2 500 1 000 000 < QCA ≤ 2 000 000 → 5 000 2 000 000 < QCA ≤ 3 000 000 → 8 000 3 000 000 < QCA ≤ 6 000 000 → 10 000 b) para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2 000 ao limite da faixa anterior (ex.: 6-8 MM → 12 000 TPM). | 300 | 240 |
| GET ​/accounts​/{accountId}​/overdraft-limits | Alta | 1500 | 15 | a) quando a quantidade de consentimentos ativos for ≤ 6 milhões, aplica-se a tabela: QCA | TPM 0 < QCA ≤ 1 000 000 → 2 500 1 000 000 < QCA ≤ 2 000 000 → 5 000 2 000 000 < QCA ≤ 3 000 000 → 8 000 3 000 000 < QCA ≤ 6 000 000 → 10 000 b) para QCA > 6 000 000, o TPM é calculado em faixas de 2 milhões, somando-se 2 000 ao limite da faixa anterior (ex.: 6-8 MM → 12 000 TPM). | 300 | 420 |

| [DC] API Operações de Crédito - Empréstimo |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/contracts | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId} | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId}​/warranties | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/scheduled-instalments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId}​/payments | Média-Alta | 1500 | 15 | 2000 | 300 | 120 |

| [DC] API Operações de Crédito - Financiamento |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/contracts | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/warranties | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/scheduled-instalments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId}​/payments | Média | 2000 | 15 | 1500 | 300 | 30 |

| [DC] API Operações de Crédito - Adiantamento a Depositantes |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/contracts | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/warranties | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/scheduled-instalments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId}​/payments | Média | 2000 | 15 | 1500 | 300 | 30 |

| [DC] API Operações de Crédito - Direitos Creditórios Descontados |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/contracts | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/warranties | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/contracts​/{contractId}​/scheduled-instalments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/contracts​/{contractId}​/payments | Média | 2000 | 15 | 1500 | 300 | 30 |

| [DC] API Investimentos - Renda Fixa Bancária |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/investments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET /investments​/{investimentId}​/balances | Média-alta | 1500 | 15 | 2000 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 1500 | 15 | 2000 | 300 | 120 |

| [DC] API Investimentos - Renda Fixa Crédito |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/investments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET /investments​/{investimentId}​/balances | Média-alta | 1500 | 15 | 2000 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 1500 | 15 | 2000 | 300 | 120 |

| [DC] API Investimentos - Renda Variável |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/investments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET /investments​/{investimentId}​/balances | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/investments​/{investimentId}​/transactions-current | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/broker-notes/{brokerNoteId} | Média | 2000 | 15 | 1500 | 300 | 30 |

| [DC] API Investimentos - Títulos do Tesouro Direto |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/investments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET /investments​/{investimentId}​/balances | Média-alta | 1500 | 15 | 2000 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 1500 | 15 | 2000 | 300 | 120 |

| [DC] API Investimentos - Fundos de Investimento |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/investments | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/investments​/{investimentId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET /investments​/{investimentId}​/balances | Média-alta | 1500 | 15 | 2000 | 300 | 120 |
| GET /investments​/{investimentId}​/transactions | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/investments​/{investimentId}​/transactions-current | Média-alta | 1500 | 15 | 2000 | 300 | 120 |

| [DC] API Câmbio |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET ​/operations | Média | 2000 | 15 | 1500 | 300 | 30 |
| GET ​/operations​/{operationId} | Baixa | 4000 | 15 | 1000 | 300 | 8 |
| GET ​/operations​/{operationId}/events | Média | 2000 | 15 | 1500 | 300 | 30 |

## Serviços

| [SV] API Pagamentos |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| POST ​/consents | Alta | 1500 | 15 | NA | 300 | NA |
| GET ​/consents​/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST ​/pix​/payments | Alta | 1500 | 15 | NA | 300 | NA |
| GET ​/pix​/payments​/{paymentId} | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /pix/payments/{paymentld} | Alta | 1500 | 15 | NA | 300 | NA |

| [SV] API Pagamentos Automáticos |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| POST /recurring-consents | Alta | 1500 | 15 | NA | 300 | NA |
| GET /recurring-consents/{recurringConsentId} | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /recurring-consents/{recurringConsentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST /recurring-payments | Alta | 1500 | 15 | NA | 300 | NA |
| GET /recurring-payments/{recurringPaymentId} | Alta | 1500 | 15 | NA | 300 | NA |
| GET /recurring-payments | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /recurring-payments/{recurringPaymentId} | Alta | 1500 | 15 | NA | 300 | NA |

| [SV] API Pagamentos sem Redirecionamento |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| POST /enrollments | Alta | 1500 | 15 | N/A | 300 | N/A |
| GET /enrollments/{enrollmentId} | Alta | 1500 | 15 | N/A | 300 | N/A |
| PATCH /enrollments/{enrollmentId} | Alta | 1500 | 15 | N/A | 300 | N/A |
| POST /enrollments/{enrollmentId}/fido-registration-options | Alta | 1500 | 15 | N/A | 300 | N/A |
| POST /enrollments/{enrollmentId}/fido-registration | Alta | 1500 | 15 | N/A | 300 | N/A |
| POST /enrollments/{enrollmentId}/fido-sign-options | Alta | 1500 | 15 | N/A | 300 | N/A |
| POST /enrollments/{enrollmentId}/risk-signals | Alta | 1500 | 15 | N/A | 300 | N/A |

## Portabilidade de Crédito

| [PC] - API Portabilidade de Crédito |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| GET /credit-operations/{contractId}/portability-eligibility | Alta | 1500 | 15 | NA | 300 | NA |
| POST / portabilities | Média | 2000 | 15 | NA | 300 | NA |
| GET /portabilities/{portabilityId} | Alta | 1500 | 15 | NA | 300 | NA |
| PATCH /portabilities/{portabilityId}/cancel | Média | 2000 | 15 | NA | 300 | NA |
| GET /account-data | Baixa | 4000 | 15 | NA | 300 | NA |
| POST /portabilities/{portability}/payment | Média | 2000 | 15 | NA | 300 | NA |

## Webhook

| Webhook - Todas as APIs |
| Endpoint | Frequência | SLA (ms)* | Timeout (s) | TPM | TPS | Limite Operacional (consultas/mês) |
| POST ​/payments/[Versão da API]/consents/{consentId} | Alta | 1500 | 15 | NA | 300 | NA |
| POST ​/payments/[Versão da API]/pix/payments/{paymentId} | Alta | 1500 | 15 | NA | 300 | NA |
**Legenda**
NA - Não se aplica
- - Percentil 95

---

# Timeout

---
id: 17891413
title: Timeout
version: 2
modified: 2022-10-28T19:44:52.192Z
url: /spaces/OF/pages/17891413/Timeout
---

Definição do limite do tempo de espera (timeout) do servidor (server) pelo cliente (client) em 15 segundos.Definição do erro HTTP Status Code 504 (Gateway Timeout) como resposta do atingimento de timeout pelo servidor.