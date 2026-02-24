---
id: 205717535
title: Informações Gerais - API Admin - v2.0.0
version: 7
modified: 2024-01-11T18:19:09.095Z
url: /spaces/OF/pages/205717535/Informa+es+Gerais+-+API+Admin+-+v2.0.0
---

### Contexto
Conforme [IN nº 306 de 19/02/2022](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=306), o Item 2 do Anexo lista todas as APIs integrantes do Open Finance. Dentre elas, as APIs de Status, de Outages e Métricas são comuns a todos os participantes do Open Finance Brasil, independentemente da fase de adesão.
| Relatórios e Métricas | Situação do Ambiente | Deve dar acesso a dados sobre a disponibilidade atual das implementações, bem como dados sobre indisponibilidades programada. |
| Métricas | Deve dar acesso a dados de performance de todas as APIs disponibilizadas. |
Sendo assim: 
1. Todas as instituições devem publicar essas APIs que monitoram a situação do ambiente;
2. API de métricas deve reportar os dados de performance de todas as APIs que a instituição oferece;
3. API de métricas deve ser atualizada conforme lançamento de novas APIs pela instituição ou atualização das APIs já existentes.
**Métricas**: (GET /admin/v2/metrics)
### Visão geral
Os dados das APIs Administrativas são consumidos apenas pelo Diretório para avaliação e controle da qualidade dos serviços fornecidos pelas Instituições Financeiras. 
- Para o entendimento a respeito do cálculo do upTime e DownTime sugere o link de Disponibilidade ;
- Para preenchimento do objeto invocativos sugere o link de Referência .

### Listas de IPs liberados para acesso a API Admin​
As instituições que desejarem restringir o acesso à API Admin, por questões de segurança cibernética, deverão liberar o acesso aos seguintes endereços de IPs conforme tabela abaixo:​
| Diretório | Conformance Suite |
| --- | --- |
| 54.73.60.150 | 34.218.96.135 |
| 54.220.198.63 | |
| 176.34.220.31 | |
As instituições que decidirem não restringir o acesso, conforme sugerido, ficam cientes que estão assumindo os riscos decorrentes a possíveis ataques.​
### Visão de alto nível das estruturas de dados

### Dicionário de Dados
[Fazer download do dicionário de dados](https://openbanking-brasil.github.io/draft-openapi/dictionary/getMetrics_v2.csv)