# FAQ Geral

---
id: 17379169
title: FAQ Geral
version: 3
modified: 2022-12-21T17:19:54.331Z
url: /spaces/OF/pages/17379169/FAQ+Geral
---

## Como tratar campos Obrigatórios?
No Github, item Padrões – Convenções de payload – Atributos vazios / nulos encontram-se as orientações solicitadas quanto ao tratamento de campos: obrigatórios, opcionais e condicionais."Um atributo omitido (ou seja, um atributo que não está presente no *payload*) será considerado equivalente a um atributo que esteja presente com o valor `null`.Uma *string* vazia (`“”`) não será considerada equivalente a `null`.O valor booleano `false` não será considerado equivalente a `null`. Os atributos booleanos opcionais, por definição, possuirão três valores possíveis: verdadeiro (`true`), falso (`false`) e indeterminado (`null`).Na situação onde o campo a ser informado no payload seja obrigatório e a Instituição, seja consumidora no envio ou transmissora no retorno, não a possuir, deve-se implementar o valor padronizado: “NA” - Não se Aplica, com exceção dos campos declarados como ENUM que deverão ser sempre preenchidos com os valores válidos para o ENUM correspondente."
## Como tratar campos Opcionais?
No Github, item Padrões – Convenções de payload – Atributos vazios / nulos encontram-se as orientações solicitadas quanto ao tratamento de campos: obrigatórios, opcionais e condicionais."Um atributo omitido (ou seja, um atributo que não está presente no *payload*) será considerado equivalente a um atributo que esteja presente com o valor `null`.Uma *string* vazia (`“”`) não será considerada equivalente a `null`.O valor *booleano* `false` não será considerado equivalente a `null`. Os atributos booleanos opcionais, por definição, possuirão três valores possíveis: verdadeiro (`true`), falso (`false`) e indeterminado (`null`).Na situação onde o campo a ser informado no *payload* seja obrigatório e a Instituição, seja consumidora no envio ou transmissora no retorno, não a possuir, deve-se implementar o valor padronizado: “NA” - Não se Aplica, com exceção dos campos declarados como ENUM que deverão ser sempre preenchidos com os valores válidos para o ENUM correspondente."
## Por que todos os campos com domínio definidos não tem tamanho explicitado no dicionário de dados?
Por Padrão, explicitado no item Tipos de Dados Comuns, no Github, todos os possíveis conteúdos de Enum estão declarados. Não é informado o tamanho para este tipo de dado. Cada instituição definirá o tamanho máximo a ser adotado. Como regra, observar que o tamanho máximo deve ser igual ou maior ao tamanho total da maior ocorrência da lista.
## No momento, o compartilhamento dos dados relativos aos Terminais de autoatendimento compartilhados é facultativo?
A normativa nº 35 explicita a existência da API de Terminais de autoatendimento compartilhado, por isso o Github traz esta estrutura. Num primeiro momento, foi declarado através da normativa nº 35 que todos seus atributos são opcionais.
## De que tipo de terminal o regulador está se referindo, pois temos algumas situações distintas em nossa instituição:

1. Terminais de nossa propriedade cujo demais bancos firmam convênio para que seus clientes os utilizem
2. Terminais de terceiros como Saque e Pague e Banco 24h, que possuímos convênio para uso de nossos clientes.
**Para o segundo caso, se for esse o foco do pedido do regulador, não teremos os dados de forma atualizada para informar via API, uma vez que tal informação estará disponível no proprietário do terminal, como por exemplo a TecBan? Se precisarmos informar tais dados, não teremos como nos responsabilizar pela veracidade e integridade do mesmo.**O item 2.4.2, sobre terminais de autoatendimento compartilhados, do ANEXO À INSTRUÇÃO NORMATIVA BCB Nº 35, de 2020, , refere-se exatamente aos terminais de propriedade de terceiros, a exemplo do Saque e Pague e Banco 24h citados, contratados pelas instituições para a prestação de serviços a seus clientes. No que diz respeito à veracidade e à integridade dos dados fornecidos, trata-se de responsabilidade da instituição participante, conforme dispõe o art. 31 da Resolução Conjunta n.º 1, de 2020.
## Na normativa nº 35, do BCB, para Correspondente Bancário os atributos weekday e phonestype aparecem como opcional, mas no Github aparecem como obrigatórios isto está correto?
O atributo `weekday` faz parte da lista `availability`, assim como `phonestype` faz parte da lista `phones`. As listas estão classificadas como opcionais, portanto caso a Instituição não tenha valores para informar em `availability` ou em `phones` estas listas como um todo estão classificadas opcionais não aparecerão na resposta solicitada. Porém, caso haja conteúdo a ser informado na lista `availability` ou `phones` o preenchimento dos atributos do tipo Enum: `weekday` ou `phonestype` passam a ser obrigatórios. Por isso estão assim classificados, seguindo protocolos das melhores práticas.
### Sendo consideradas somente as operações “contratadas” no mês da apuração no cálculo e disponibilização de informações relativas a distribuição de frequência de Taxas remuneratória s.

- Modalidades de crédito disponíveis para oferta que não tiveram nenhuma contratação no mês da apuração serão informadas trazendo este conjunto de informações ‘vazio’? R.: Deve-se reportar a modalidade com o valor das taxas e tarifas representados como N/A (justamente para diferenciar de casos em que não oferecemos os produtos, nos quais não reportamos a modalidade, ou no caso de tarifa zerada, que efetivamente viria com um “0”).
- Produtos com características de rotativo, como cartão (rotativo e parcelamento saldo devedor) e cheque especial que têm a incidência das taxas remuneratórias durante a utilização do crédito contratado deverão ter suas taxas remuneratórias informadas na contratação? R.: O entendimento é que seria apenas na referência de contratação de fato, ou seja na utilização do crédito (p.ex. o mês que o cliente entra no especial ou no rotativo)

### Sendo consideradas somente as operações "contratadas" no mês da apuração no cálculo e disponibilização de informações relativas a distribuição de frequência de Tarifas.

- Modalidades de crédito como Contas, Cartão, Cheque Especial que têm em suas tarifas de serviços normalmente relacionadas a utilização do crédito durante a vigência do contrato só serão representadas se a utilização da tarifa incidir no mês da contratação? R.: O entendimento é que seria apenas na referência de contratação de fato, ou seja na utilização do crédito (p.ex. o mês que o cliente entra no especial ou no rotativo); desde que a modalidade de crédito informada ainda seja ofertável.
- No caso de se considerar no cálculo da distribuição de frequência sobre tarifas todas as ocorrências relativas ao mês de apuração, o estoque de operações ainda vigentes de uma modalidade não mais disponível na oferta deve ser desprezada? R.: Sim
- Modalidades de crédito comercializadas que têm tarifas de serviços diferenciadas para funcionários deverão ser consideradas no cálculo da distribuição de frequência? Considerando assim, funcionários consumidores de produto também como clientes? R.: O entendimento é que o funcionário é cliente nos produtos, ele deve sim entrar na conta (ele é um cliente com condições especiais de taxas e tarifas, assim como outros clientes que também conseguem negociar condições especiais por diversos outros motivos).

## Orientações, padrões e exemplos sobre apuração dos valores para a distribuição de frequência de tarifas e taxas remuneratórias
Podem ser encontradas no item [Divulgação dos valores de tarifas e taxas de juros remuneratórias](https://openbankingbrasil.atlassian.net/wiki/spaces/DraftOF/pages/1671203/Dados+Abertos#Divulga%C3%A7%C3%A3o-dos-valores-de-tarifas-e-taxas-de-juros-remunerat%C3%B3rios), em API – Produtos Serviços.
## É possível incluir novos tipos de cartão?
Informamos que nesta fase 1 não serão incluídas novas ocorrências no Enum dos tipos de cartão. Deve-se selecionar a opção 'OUTROS' e complementar a informação utilizando o atributo `additionaInfo`.
## Como reportar agências digitais?
Para o item dependências e correspondentes, a grande referência foi o que as instituições já reportam via mensageria regulatória. (UNICAD).RESOLUÇÃO Nº 4.072, DE 26 DE ABRIL DE 2012.Vide 4015 - Art. 2º Os dados sobre os canais de atendimento objeto de compartilhamento de que trata o art. 5º, inciso I, alínea "a", da Resolução Conjunta nº 1, de 4 de maio de 2020, abrangem, no mínimo, aqueles obrigatoriamente divulgados na forma de dados abertos, de que trata a regulamentação vigente, no caso de dependências próprias e correspondentes no País RC1 - I - dados sobre: a. canais de atendimento relacionados com:
1. dependências próprias;
2. correspondentes no País;
3. canais eletrônicos; e
4. demais canais disponíveis aos clientes;
*IN-*35 - Divulga a versão 1.0 do Manual de Escopo de Dados e Serviços do Open Banking debatido em auto regulação e regulado pelo BACEN. Não discutimos os itens especificamente, mas entendo que se não está explicito nas regulações vigentes, não há obrigação de report.
## As operações de repasse são reportadas no Documento 3050 – Estatísticas agregadas de Crédito e Arrendamento Mercantil em: Financiamento de investimentos com recursos do BNDES e Financiamento Agroindustrial com recurso do BNDES. No Documento 3040 – Dados Individualizados de Risco de Crédito, essas operações são reportadas como 08.02. Financiamentos Rurais – Investimentos, porém, com a origem do recurso como direcionado (02 – BNDES, 03- Finame). Devemos incluir essas operações de repasse dentro do reporte do Open Finance Brasil?
As operações informadas no documento 3040, que encontram sua Modalidade representada nas listas das APIs constante do Github devem ser informadas no Open Finance. Quanto a fonte do recurso (02 – BNDES, 03- Finame), esta informação não está discriminada para ser disponibilizada. Para esclarecimento reiteramos que a modalidade 08.02 não faz parte do *reporting*. Citar a origem dos recursos nunca foi escopo das discussões da fase 1.
## Temos participação obrigatória na Fase 3, porém queremos saber detalhes sobre a participação optativa da Fase 1 e Fase 2. As dúvidas iniciais são:

1. Como optativa: Podemos participar da Fase 2 parcialmente?
2. Como optativa: Podemos somente consumir dados da Fase 2?
3. Como optativa: É preciso fazer cadastro do BCB para somente consumir dados da Fase 2?
Salvo possíveis ressalvas do regulador, entendemos, conforme trecho da regulação mais abaixo que não existe participação parcial.
1. O cadastramento para compartilhamento de informações é obrigatório - compartilhamento neste contexto engloba também o consumo de informações.
2. A participação voluntária na Fase II implica na disponibilização das interfaces dedicadas ao compartilhamento de dados das Fases I e II.
3. A instituição poderá decidir se consome ou não os dados no ecossistema - como receptora, mas uma vez participante, torna-se obrigatoriamente transmissora - daí a obrigatoriedade de disponibilizar as interfaces dedicadas.
[RESOLUÇÃO CONJUNTA Nº 1, DE 4 DE MAIO DE 2020](https://www.in.gov.br/en/web/dou/-/resolucao-conjunta-n-1-de-4-de-maio-de-2020-255165055)"Seção IIDa Participação no Open BankingArt. 6º São participantes do Open Banking: [...]§ 1º É obrigatório o compartilhamento dos dados e dos serviços, observados os prazos de implementação mencionados no art. 55: [...]§ 3º A participação voluntária de que trata o inciso I, alínea "b", do caput, pressupõe a disponibilidade de interface dedicada de que trata o art. 23 na condição de instituição transmissora de dados."
## Considerar data da concessão ou data da liberação para o cálculo da distribuição de frequência para operações com característica de liberações parciais?
No que diz respeito a contratos de crédito guarda-chuva, entendemos que deveria se entender, para todos os efeitos, que a contratação ocorre na data da liberação do recurso. Entendimento similar já foi dado para contratos de cheque especial, por exemplo, podendo, a nosso entender, também ser replicado no caso ilustrado pelo demandante de operações de crédito rural e de custeio de projetos.
## Como devemos tratar distribuição de frequência sobre taxas remuneratórias para outras operações de crédito relacionadas ao produto cartão?
A princípio não há exigência normativa para se apresentar a distribuição de frequência para essas outras modalidades de crédito relacionadas à cartão de crédito. Conforme a Instrução Normativa BCB 35, de 2020, somente recairia essa exigência, no caso de cartão de crédito, sobre as operações de crédito rotativo e de parcelamento do saldo devedor da fatura, que já são operações que observam alguma espécie de padronização. De qualquer forma, esse é o escopo mínimo de dados, o que não impede que o GT e o conselho deliberativo deliberem por sua expansão em algum momento.
## É permitido a utilização de PKI Privada para emissão de certificados responsáveis por autenticação (cliente) e assinatura no Open Finance Brasil?
De acordo com a MEDIDA PROVISÓRIA No 2.200-2, DE 24 DE AGOSTO DE 2001, a utilização de PKI Privada é autorizada como mecanismo válido para autenticação e assinatura. Para o Open Finance Brasil, a utilização de PKI Privada para emissão de certificados de autenticação (cliente) e assinatura é permitido apenas quando provisionado pela entidade atuando como transmissora de dados, e quando a entidade receptora de dados não participa do Ecossistema de Open Finance Brasil de maneira a possuir cadastro no Serviço de Diretório do Open Finance Brasil e o certificado emitido deve possuir as mesmas características de chaves criptográficas, e atributos conforme especificados pelo Open Finance Brasil.

---

# Glossário

---
id: 17379230
title: Glossário
version: 2
modified: 2025-02-04T13:20:42.373Z
url: /spaces/OF/pages/17379230/Gloss+rio
---

### Agência (Branch)
É a dependência destinada ao atendimento aos clientes, ao público em geral e aos associados de cooperativas de crédito, no exercício de atividades da instituição, não podendo ser móvel ou transitória
### Adiantamento a Depositante (Unarranged Account Overdraft)
O valor que o banco libera na conta-corrente do cliente, em casos excepcionais, o valor necessário para cobrir algum saque, pagamento, débito automático ou cheque, quando o saldo disponível não é suficiente.
### API
Interface de Programação de Aplicações.
### Bandeira (Credit Card Network)
São instituições que autorizam o uso de sua marca e de sua tecnologia por emissores e credenciadoras de estabelecimentos. Essas marcas aparecem nos cartões e nos estabelecimentos credenciados.
### BCB
Banco Central do Brasil.
### Cartão Múltiplo (Multiple CreditCard)
Trata-se de um único cartão que possui mais de uma função, ou seja, que pode ser utilizado como débito, crédito e para a movimentação da conta.
### CBO (Cbo Code)
A Classificação Brasileira de Ocupações (CBO) é um documento que retrata a realidade das profissões do mercado de trabalho brasileiro. Foi instituída com base legal na Portaria nº 397, de 10.10.2002. Trata-se de um sistema de classificação responsável pela codificação dos títulos e conteúdos dos cargos e ocupações do mercado de trabalho brasileiro
### CCB
Cédula de Crédito Bancário.
### CET
Custo Efetivo Total.
### Cheque Especial (Arranged Overdraft)
É uma operação de crédito, a exemplo do empréstimo, mas que é pré-aprovada e vinculada a uma conta de depósitos à vista. Tem o objetivo de cobrir movimentações financeiras quando não há mais saldo disponível na conta.O banco disponibiliza ao cliente um limite de crédito rotativo que, embora apareça no extrato da conta, não é um recurso do cliente. Quando utilizado esse valor, o banco pode cobrar juros sobre o valor usado, ou seja, sobre o saldo devedor.*Fonte:*[link](https://www.bcb.gov.br/detalhenoticia/402/noticia)
### CPC
Crédito Pessoal Clean.
### CNAE (Cnae Code)
Trata-se de um código utilizado para identificar quais são as atividades econômicas exercidas por uma empresa. A Classificação Nacional de Atividades Econômicas - CNAE é oficialmente adotada pelo Sistema Estatístico Nacional e pelos órgãos federais gestores de registros administrativos
### CNPJ (CNPJ Number)
Código gerido pela Secretaria da Receita Federal e utilizado para identificação das empresas no Cademp. O CNPJ corresponde ao número de inscrição no Cadastro de Pessoa Jurídica. Composto por: os oito primeiros números à esquerda (XX. XXX. XXX) formam a "raiz" ou base, que identifica a empresa de forma única. Os quatro seguintes números de ordem das filiais da empresa. Normalmente a empresa matriz tem este campo preenchido com '0001'. Os dois últimos números correspondem ao dígito verificador. composição do CNPJ pode ser assim representada, conforme ex. '50.685.362/0001-35'.
### Código Compe (compeCode)
O Compe (Sistema de Compensação de Cheques e Outros Papéis) é um sistema que identifica e processa as compensações bancárias. Ele é representado por um código de três dígitos que serve como identificador de bancos, sendo assim, cada instituição bancária possui um número exclusivo.
### Código Ocupação Receita Federal – Receita Federal Code
Código da atividade profissional relacionada com a principal fonte pagadora dos seus rendimentos, assim entendida a que pagou maior rendimento independentemente de escolaridade ou de formação acadêmica*Fonte:*[link](http://www.receita.fazenda.gov.br/publico/programas/irpf/2010/Orientacoes/ManualPreenchimentoDAAIRPF2010.pdf)
### Conta Individual (Sole Account)
Tipo de conta que comporta apenas um titular.
### Conta Conjunta Não-solidária (Joint Account And)
Tipo de conta que comporta mais de um titular, em que os titulares dependem da autorização de “pelo menos” um diferente titular para realização de movimentações em contas.
### Conta Conjunta Solidária (Joint Account Or)
Tipo de conta que comporta mais de um titular, tendo todos os titulares livre movimentação sem que seja exigida a autorização de outros titulares.
### Conta de Depósito à Vista (Current Account)
Conhecida popularmente pelo nome de conta corrente. É a maneira mais comum de manter dinheiro em uma instituição financeira. Funciona como um cofre, em que o cliente deposita seu dinheiro e pode ter acesso a serviços como pagamento de contas, saques, transferências, emissão de cheques e realização de compras com cartão de débito, entre outros. Para guardar o dinheiro e oferecer serviços como os citados, a instituição financeira pode cobrar tarifas, mas o cliente é quem escolhe se prefere pagar uma tarifa individualizada por serviço que utilizar ou uma tarifa única que dá direito a um pacote de serviços.
### Conta de Pagamento Pós-paga (Credit Card)
Referente a cartão de crédito. Instrumento de pagamento que possibilita a aquisição de produtos e serviços com liquidação futura, de acordo com requisitos predeterminados, tais como limite de crédito e validade. O pagamento do valor correspondente ao produto ou ao serviço adquirido será efetuado ao emissor do cartão de crédito em data previamente acordada.
### Conta de Pagamento Pré-paga (Prepaid Payment Account)
Destinada à execução de transações de pagamento em moeda eletrônica realizadas com base em fundos denominados em reais previamente aportados.
### Conta de Poupança (Savings Account)
A conta de depósitos de poupança, popularmente conhecida como conta poupança, conta de poupança ou ainda caderneta de poupança, é um tipo de investimento criado com o objetivo de estimular a economia popular. Assim, para abrir e manter uma conta de poupança, o cliente não paga tarifas, não paga imposto de renda sobre o dinheiro aplicado e ainda pode depositar pequenos valores, que passam a gerar rendimentos mensalmente. Se um valor depositado na conta de poupança não for mantido aplicado por pelo menos um mês, isto é, se for resgatado antes, não ocorrerá remuneração desse dinheiro.
### Correspondente Bancário (Banking Agent)
Empresas, integrantes ou não do Sistema Financeiro Nacional, contratadas por instituições financeiras e demais instituições autorizadas a funcionar pelo Banco Central do Brasil para a prestação de serviços de atendimento aos clientes e usuários dessas instituições. Os correspondentes mais conhecidos são as lotéricas e o banco postal.
### CPF - Cadastro de Pessoa Física (CPF Number)
O CPF é o Cadastro de Pessoa Física. Ele é um documento emitido pela Receita Federal e serve para identificar os contribuintes. O CPF é uma numeração com 11 dígitos, que só mudam por decisão judicial
### Crédito (Credit)
É um termo geral, utilizado para nomear as diferentes maneiras com que bancos, financeiras e outras instituições emprestam dinheiro a seus clientes. Ou seja, quando essas instituições emprestam dinheiro para alguém ou financiam alguma compra de uma pessoa, elas estão concedendo um crédito. Exemplo de uso: Em uma operação de crédito, quem empresta o dinheiro é chamado credor, e quem toma o dinheiro emprestado é chamado devedor.*Fonte:*[link](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/Informacoes_gerais/glossario_cidadania_financeira.pdf)
### Crédito Rotativo (Overdraft)
É um tipo de empréstimo que os bancos concedem para os clientes terem a possibilidade de não pagar, na data do vencimento, o valor total da fatura do cartão de crédito. Isto é, por causa do crédito rotativo, é possível que o cliente pague, no dia do vencimento, qualquer valor entre o pagamento mínimo e o total da fatura. A diferença entre o valor total que deveria ter sido pago e o valor que o cliente efetivamente pagou na data do vencimento é financiada pelo banco e será incluída, acrescida de juros, na fatura do mês seguinte. Quando o cliente não paga o total da fatura, é como se ele estivesse automaticamente pegando emprestado o valor que ele deixou de pagar.
### Custo Efetivo Total (CET)
Custo Efetivo Total. Corresponde a todos os encargos e despesas incidentes nas operações de crédito e de arrendamento mercantil financeiro, contratadas ou ofertadas a pessoas físicas, microempresas ou empresas de pequeno porte. Deve ser informado pelas instituições financeiras e pelas sociedades de arrendamento mercantil antes da contratação de operações de crédito e de arrendamento mercantil e também em qualquer outro momento, a pedido do cliente. Também deve constar dos informes publicitários das instituições quando forem veiculadas ofertas específicas (com divulgação da taxa de juros cobrada, do valor das prestações, etc).*Fonte: Resolução 3.517, de 6/12/2007.*[link](https://www.bcb.gov.br/acessoinformacao/glossario)
### Débito (Debit)
De uma forma geral, significa dívida. Exemplo de uso: Estou em débito com o Fernando, devo R$50 a ele. Ver também: crédito, credor, devedor, dívida.Débito (no extrato) Em um extrato bancário, os débitos, marcados com a letra “D” ao lado do valor registrado, informam as saídas de dinheiro na conta-corrente. Exemplo de uso: Fiz uma compra com a função débito do cartão e apareceu o valor da compra, com um “D”, no extrato da minha conta, diminuindo o saldo.*Fonte:*[link](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/Informacoes_gerais/glossario_cidadania_financeira.pdf)
### Débito Automático (Direct Debit)
Débitos autorizados pelo titular de conta de depósitos ou de conta de pagamento mantidas nas instituições mencionadas
### Direito Creditório Descontado (Invoice Financing)
É o direito de receber dinheiro ou títulos, sejam eles oriundos de operações financeiras, comerciais, imobiliárias ou mesmo de ativos financeiros e investimentos. Esta opção abrange tanto pessoas físicas quanto entidades. Normalmente, ele “existe” na forma de um título.
### Dependência (Branch)
Dependência de instituições financeiras e demais instituições, autorizadas a funcionar pelo Banco Central do Brasil, destinada à prática das atividades para as quais a instituição esteja regularmente habilitada. (Agência é a dependência destinada ao atendimento aos clientes e ao público em geral no exercício de atividades da instituição, não podendo ser móvel ou transitória)
### Empréstimo (Loan)
É o mecanismo utilizado para ter disponível, no presente, uma quantia que só se conseguiria alcançar no futuro, fazendo poupança. O valor emprestado, mais os juros e encargos cobrados pela instituição financeira, vira uma dívida, que deverá ser paga na forma e no prazo combinados (valor e quantidade de parcelas, por exemplo). No empréstimo, o valor emprestado não tem destinação específica, isto é, a pessoa pode utilizar o dinheiro que pegou emprestado onde e como quiser.
### Empréstimo Cartão Consignado (Payroll Loan)
É um tipo de operação de crédito contratada no Cartão de Crédito, na qual o pagamento das compras do titular são descontadas diretamente em folha ou benefício do INSS
### Encargo (Charge)
As instituições financeiras e as sociedades de arrendamento mercantil podem cobrar de seus clientes, no caso de atraso no pagamento ou na liquidação de obrigações, exclusivamente os seguintes encargos: I - juros remuneratórios, por dia de atraso, sobre a parcela vencida; II - multa, nos termos da legislação em vigor; e III - juros de mora, nos termos da legislação em vigor.*Fonte:*[link](https://www.bcb.gov.br/pre/normativos/busca/downloadNormativo.asp?arquivo=/Lists/Normativos/Attachments/50345/Res_4558_v1_O.pdf)
### Ente Consignante (CnpjConsignee)
É a empresa pública ou privada que mantém convênio com entidades Consignatárias afim de descontar no contracheque de seus funcionários os valores mensais referente as operações financeiras contratadas pelos mesmos obedecendo a regra da margem consignável.Os entes consignantes podem ser :
- Privado - Destinado a funcionários de empresas do setor privado
- Público - (prefeituras, estados, órgãos) - Destinado a servidores públicos federais, estaduais ou municipais
- INSS - Destinado a beneficiários (aposentados e / ou pensionistas) do INSS.

### Fatura (Bill)
Fatura é o documento através do qual o emissor realiza a prestação de contas ao portador titular. Nos meses em que ocorrer movimentação, o emissor do cartão de crédito enviará a Fatura discriminando as respectivas transações do período.
### Financiamento (Financing)
Parcelamento. Compra parcelada. Compra a prazo. É um crédito que a pessoa obtém para comprar um bem, como uma casa, um carro, um eletrodoméstico. O pagamento do bem é feito de forma parcelada por meio de carnês, boletos de cobrança, débitos em conta corrente, cartão de crédito, cheques etc. O financiamento pode incluir custos como juros, tarifas, impostos, entre outros encargos.
### Garantia (Warranty)
Ativo que é entregue pelo outorgante da garantia para assegurar uma obrigação à parte que toma a garantia. Os acordos de garantia podem tomar diversas formas legais; as garantias podem ser obtidas por transferência de títulos ou penhora.*Fonte:*[link](https://www.bcb.gov.br/acessoinformacao/glossario)
### GT
Grupo de Trabalho. 
### Identificação (Identification)
Agrupador das informações relativas a Identificação ou seja a ação e o efeito de identificar de forma única a pessoa através de seus dados cadastrais.
### Identificador Padronizado da Operação de Crédito – Ipoc Code
O identificador padronizado da operação de crédito é atribuído a todas as operações de crédito informadas ao SCR (Sistema de Informações de Crédito do Banco Central do Brasil – SCR é um instrumento de registro e consulta de informações sobre as operações de crédito, como empréstimos, financiamentos, avais ou fianças, realizadas entre as Instituições Financeiras e seus Clientes).O IPOC será formado pela concatenação das informações contidas nos campos do SCR abaixo discriminados, respeitando-se a seguinte ordem:
1. CNPJ da instituição
2. Modalidade da operação
3. Tipo do cliente
4. Código do cliente
5. Código do contrato
*Fonte:*[link](https://www.in.gov.br/web/dou/-/circular-n-3.953-de-10-de-julho-de-2019-191917419)
### IGP-M
Índice Geral de Preços - Mercado
### Indexador (Indexer)
É o termo utilizado para se referir aos índices usados como base para corrigir os valores monetários de um determinado ativo. Os índices mais utilizados são IPCA, INPC, IGP-M, CDI, Taxa Selic.
### Instituição Financeira (Company)
Instituições que prestam serviços financeiros e são autorizadas a funcionar pelo Banco Central do Brasil.
### IPCA
Índice Nacional de Preços ao Consumidor Amplo
### Limite Flexível (Flexible Limit)
Geralmente esses cartões não possuem limite oculto inferior a R$ 50 mil, ou seja, é o mesmo que sem limite pré-estabelecido de despesas. Pois são voltados para consumidores de alto poder aquisitivo, sendo considerado um cartão de crédito diferenciado, pois permite ao portador comprar o que quiser.
### Marca (Brand)
A marca é em essência uma promessa da empresa em fornecer uma série específica de atributos, benefícios e serviços uniformes aos clientes.
### MCC (Merchant Category Code)
O MCC ou o código da categoria do estabelecimento comercial. Os MCCs são agrupados segundo suas similaridades. O MCC é usado para classificar o negócio pelo tipo fornecido de bens ou serviços. Os MCCs são atribuídos por tipo de comerciante (por exemplo, um para hotéis, um para lojas de materiais de escritório, etc.) ou por nome de comerciante (por exemplo, 3000 para a United Airlines).
### Mês de Referência (Reference Month)
O mês de referência será tratado como “M-1”.
### Nome Civil Completo (Civil Name)
Nome civil completo da pessoa natural é aquele atribuído à pessoa natural desde o registro de seu nascimento, com o qual será identificada por toda a sua vida, bem como após a sua morte. Trata-se de um Direito fundamental da pessoa natural
### Nome Social (Social Name)
O nome social é definido como a adoção/ adequação do senso de identificação do sujeito referenciando o nome que o representa (Decreto Nº 51.180, de 14 de janeiro de 2010), evitando a exposição desnecessária do indivíduo, o constrangimento de ser tratado de uma forma que não condiz com sua condição humana, psicológica, moral, intelectual, emocional e que não o representa. Tem por objetivo o reconhecimento social e individual segundo o Art. 16 do Código Civil, toda pessoa tem direito ao nome, nele compreendidos o prenome e o sobrenome.
### Núclea
Plataforma de registro de operações de crédito.
### OFB
Open Finance Brasil.
### Pacote de Serviços (Service Bundles)
Cesta de serviços. É uma combinação de diferentes quantidades de serviços bancários (saques, extratos, transferências, cheques e outros) que o cliente pode usar por mês. Antes da contratação de um pacote de serviços, é importante verificar quais os serviços que são efetivamente usados ao longo do mês e se o custo desses serviços, cobrados isoladamente, não é menor que o do pacote de serviços.
### Pagador (Payer)
É a pessoa ou a empresa que deve pagar o valor cobrado em um boleto bancário, normalmente por ter feito uma compra, um financiamento ou por estar pagando por um serviço, como uma mensalidade escolar, por exemplo. O banco recebe o pagamento feito pelo sacado e transfere o valor pago para a conta do beneficiário. No boleto, o campo “pagador” costuma trazer outras informações além do nome do pagador, como o seu endereço. Exemplo de uso: Ao receber um boleto para pagar, a pessoa deve sempre conferir se seus dados estão corretos no campo “pagador”. Se houver algum erro, ela deve procurar o banco que emitiu o boleto*Fonte:*[link](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/Informacoes_gerais/glossario_cidadania_financeira.pdf)
### Pagamento Autorizado (Authorised Payment)
São transações a crédito ou débito que ainda não foram registradas no extrato, mas que a instituição possui autorização do cliente para realizar o débito.*Fonte:*[link](https://www.bcb.gov.br/pre/normativos/busca/downloadNormativo.asp?arquivo=/Lists/Normativos/Attachments/47650/Res_3695_v2_L.pdf)
### PC
Portabilidade de Crédito.
### Posto de Atendimento Bancário - PAB (Branch)
São as dependências de bancos múltiplos com carteira comercial, instaladas em recinto interno de entidade da administração pública ou de empresa privada e destinadas a prestar todos os serviços para os quais a instituição esteja regularmente habilitada de exclusivo interesse do respectivo governo e de seus funcionários, quando instalados em entidade de administração pública, ou da respectiva empresa, de seus empregados e administradores, quando instalados em dependências de empresa privada.
### Posto de Atendimento Eletrônico – PAE (Branch)
O Posto de Atendimento Bancário Eletrônico, Fixo ou Móvel (PAE), é uma extensão automatizada de dependências bancárias, que pode funcionar até 24 (vinte e quatro) horas por dia, ligada à central de controle e processamento.
### PRD
Documento de Requisitos do Produto.
### Prestação Regular (Instalment)
Refere-se a comprar um produto ou serviço de forma parcelada e assim dividir o pagamento em partes, em prestações a serem pagas ao longo de um período de tempo em intervalos regulares, p.ex. parcelas mensais, onde o vencimento acontecerá regularmente todo dia 10 de cada mês
### Procurador (Procurator)
Pessoa autorizada por procuração para dirigir os negócios de outrem ou agir como seu agente, representante, substituto ou advogado.
### Qualificação (Qualification)
Considera-se qualificação as informações que permitam as instituições apreciar, avaliar, caracterizar e classificar o cliente com a finalidade de conhecer o seu perfil de risco e sua capacidade econômico-financeira.
### Razão Social (Company Name)
A razão social é o nome de registro de uma empresa junto aos órgãos do governo e cartório e é o que vai constar em contratos, escrituras, documentos legais, notas fiscais etc. Ela é criada junto com o CNPJ e também é chamada de Denominação social – exatamente por ser, na prática, o nome da pessoa jurídica.
### RCO
Ressarcimento de Custo de Originação.
### Recebedor (Payee)
Pessoa natural ou jurídica, destinatário final dos recursos de uma transação de pagamento*Fonte:*[link](https://www.bcb.gov.br/pre/normativos/busca/downloadNormativo.asp?arquivo=/Lists/Normativos/Attachments/48841/Res_4282_v1_O.pdf)
### Relacionamento (Financial Relation)
Considera-se relacionamento as informações que permitam conhecer desde quando a pessoa consultada é cliente da instituição, bem como um indicador dos produtos e serviços que ela consome atualmente e seus representantes
### Representante Legal (Legal Representative)
Nome Civil completo da Pessoa Natural que represente uma entidade ou uma empresa e é nomeado em seu ato constitutivo, ou seja, no contrato social ou estatuto social
### Saldo (Account Balance)
Quantia que representa o excedente do total de créditos e do total de débitos de uma conta.
### Saldo Bloqueado (Cash Blocked)
É um valor que o banco informa estar separado na conta-corrente para o pagamento, ao fim do dia, de alguma obrigação que tem vencimento naquele dia.Exemplo de uso:
- Se o saldo da minha conta é de R$1.000, mas eu vejo que tem um saldo provisionado de R$400, isso quer dizer que só posso movimentar R$600, se não quiser entrar no vermelho.
- Valor depositado na conta que se encontra bloqueado para utilização, como bloqueios judiciais.
*Fonte:*[link](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/Informacoes_gerais/glossario_cidadania_financeira.pdf)
### Saldo Devedor (Outstanding Balance)
Corresponde ao valor que falta ser pago de uma dívida. Ao longo do tempo, os juros fazem o saldo devedor crescer, enquanto as amortizações pagas pelo devedor fazem o saldo devedor diminuir. O saldo devedor pode vir tanto de um empréstimo ou financiamento quanto de um pagamento inferior ao valor total de uma fatura de cartão de crédito. Ou ainda, em conta-corrente, o que significa que o cliente está “no vermelho” ou “no negativo”, isto é, entrou no limite de crédito do cheque especial ou utilizou o adiantamento a depositantes.
### Saldo Disponível (Cash Amount)
É o valor total à disposição do cliente em sua conta-corrente, que inclui tanto o dinheiro que ele tem depositado nela quanto o limite de cheque especial pré-aprovado pelo banco. 43 Exemplo de uso: Ao consultar o extrato bancário, para saber quanto dinheiro seu de fato tem depositado em conta, o cliente não pode considerar o saldo disponível.*Fonte:*[link](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/Informacoes_gerais/glossario_cidadania_financeira.pdf)
### Sexo (Sex)
“Conjunto de características anatomofisiológicas que distinguem o homem e a mulher: Sexo masculino; sexo feminino”. No caso de não ser feminino nem masculino é classificado como outros.
### Sistema de Amortização Constante (SAC)
É aquele em que o valor da amortização permanece igual até o final. Os juros cobrados sobre o parcelamento não entram nesta conta.
### Sistema de Amortização Misto (SAM)
Cada prestação (pagamento) é a média aritmética das prestações respectivas no Sistemas Price e no Sistema de Amortização Constante (SAC)
### Sistema Francês de Amortização (Price)
As parcelas são fixas do início ao fim do contrato. Ou seja, todas as parcelas terão o mesmo valor, desde a primeira até a última. Nos primeiros pagamentos, a maior parte do valor da prestação corresponde aos juros. Ao longo do tempo, a taxa de juros vai decrescendo. Como o valor da prestação é fixo, com o passar das parcelas, o valor de amortização vai aumentando.
### STR
Sistema de Transferência de Reservas.
### Tarifa (Fee)
A Resolução 3.919, de 25/11/2010, classifica em quatro modalidades os tipos de serviços prestados às pessoas físicas:
1. serviços essenciais – não podem ser cobrados;
2. serviços prioritários – relacionados a contas de depósitos, transferências de recursos, operações de crédito e de arrendamento mercantil, cartão de crédito básico e cadastro, somente podendo ser cobrados os serviços constantes da Lista de Serviços da Tabela I anexa à (Resolução CMN 3.919, de 2010, devendo ainda ser observados a padronização, as siglas e os fatos geradores da cobrança, também estabelecidos por meio da citada Tabela I;
3. serviços especiais – legislação e regulamentação específicas definem as tarifas e as condições em que são aplicáveis, a exemplo dos serviços referentes ao crédito rural, ao Sistema Financeiro da Habitação (SFH), ao Fundo de Garantia do Tempo de Serviço (FGTS), ao Fundo PIS/PASEP, às chamadas contas-salário, e às operações de microcrédito de que trata a Resolução 4.000, de 2011;
4. serviços diferenciados – podem ser cobrados desde que explicitadas ao cliente ou ao usuário as condições de utilização e de pagamento
Fonte: [link](https://www.bcb.gov.br/acessoinformacao/glossario)
### Taxa Efetiva (EffectiveTax)
É a taxa de juros em que a unidade referencial coincide com a unidade de tempo da capitalização. Como as unidades de medida de tempo da taxa de juros e dos períodos de capitalização são iguais, usa-se exemplos simples como 1% ao mês, 60% ao ano.
### Taxa nominal (NominalTax)
É uma taxa de juros em que a unidade referencial não coincide com a unidade de tempo da capitalização. Ela é sempre fornecida em termos anuais, e seus períodos de capitalização podem ser diários, mensais, trimestrais ou semestrais.
### Taxa Referencial – TR (Referential Rate)
É a taxa de juros de referência. É uma taxa calculada pelo Banco Central do Brasil e utilizada para determinar o rendimento de investimentos, como a caderneta de poupança e a correção de financiamentos imobiliários.
### TED
Transferência Eletrônica Disponível.
### Terminais de Autoatendimento Compartilhados (Shared Automatic Teller Machine)
É o compartilhamento dos terminais de autoatendimento (ATM - dispositivo eletromecânico que permite aos usuários, geralmente usando cartões de plástico legíveis em máquina, a realização de um ou mais tipos de operações, tais como saques, depósitos, emissão de extratos e saldos, realização de pagamentos de contas e títulos, transferência de fundos e outro) para aumentar a eficiência do sistema de pagamento de varejo.
### Transação Agendada (Scheduled Payment)
O usuário poderá agendar uma transação de DOC, TED, Pix ou boleto bancário para uma determinada data futura*Fontes:*[link 1](https://www.bcb.gov.br/detalhenoticia/327/noticia)*e*[link 2](https://www.bcb.gov.br/content/cidadaniafinanceira/documentos_cidadania/Cartilha_Migrantes_Refugiados/cartilhaBC-Port_v3.pdf)
### Transações Realizadas (Completed Transaction)
Operações segmentadas efetuadas por tipo de acesso físico (agências e postos tradicionais, caixas de autoatendimento e correspondentes bancários) ou remoto (home e office banking, call centers, smartphones e PDAs) e por tipo de transações( Bloqueto de cobrança e convênios, depósitos, ordem de transferência de crédito, empréstimos e financiamentos, saques, outras transações financeiras, consultas a extratos e saldos e outras transações não financeiras)*Fontes:*[link 1](https://www.bcb.gov.br/nor/relcidfin/cap01.html#nota13*)*e*[link 2](https://dadosabertos.bcb.gov.br/dataset/25166-quantidade-de-outras-transacoes-financeiras-por-canal-nao-presencial)
### Unidade Administrativa Desmembrada (UAD) - (Branch)
É a dependência destinada à execução de atividades administrativas da instituição, tal como atividades contábeis e administrativas de natureza interna, desde que tal unidade esteja instalada no mesmo Município da sede do grupo financeiro, ou de uma agência da instituição e é vedado o atendimento ao público.
### UUID
Universally Unique Identifier.

---

# Service Desk

---
id: 17379205
title: Service Desk
version: 1
modified: 2022-10-27T12:04:08.726Z
url: /spaces/OF/pages/17379205/Service+Desk
---

Fale conosco enviando sua sugestão, dúvida ou problema através do site do *Service Desk*, disponível neste [link](https://servicedesk.openfinancebrasil.org.br/).