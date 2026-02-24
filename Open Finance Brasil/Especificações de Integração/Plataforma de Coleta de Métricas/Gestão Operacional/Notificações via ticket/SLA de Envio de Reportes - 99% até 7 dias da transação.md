---
id: 1506934785
title: SLA de Envio de Reportes - 99% até 7 dias da transação
version: 2
modified: 2026-02-19T15:16:40.404Z
url: /spaces/OF/pages/1506934785/SLA+de+Envio+de+Reportes+-+99+at+7+dias+da+transa+o
---

v 1.00
## Objetivo
Apontar os casos em as instituições não enviaram em até 7 dias o mínimo de 99% dos reportes esperados, a partir da data e horário das transações ou cuja quantidade de reportes UNPAIRED ou PAIRED_INCONSISTENT  seja superior a 1% do total de reportes esperados.
## Escopo
São analisados envios dos reportes de Dados Cadastrais e Transacionais (Fases 2 e 4b) e Dados de Pagamentos (Fase 3)  
## Terminologia
Os termos abaixo estão no contexto da Plataforma de Coleta de Métricas, que por sua vez está no contexto do Open Finance Brasil.  **Client e Server** Em uma interação, a parte que solicita os dados é chamada de *client*, ao passo que a parte que devolve os dados é *server*. Portanto, supondo que A faça uma consulta em B pelos dados de uma conta, esses dados serão transmitidos por quem recebeu a solicitação, e recebidos por quem a fez. Neste caso, A é o *client* e B é o *server*.  **Faltante**Quando uma organização envia um reporte contra uma outra organização, caso esta última não envie sua contraparte ela será considerada *faltante*no processo de pareamento. 
## Forma de avaliação do percentual de SLA 99%
Diariamente são apurados os reportes que não cumpriram o SLA de envio da seguinte forma:
1. Contam-se todos os reportes enviados pela organização que foram recebidos pela PCM até 7 dias da data da transação, por endpoint e método
2. Contam-se todos os reportes enviados contra a organização e que não foram pareados (faltantes) por endpoint e método; este número representa o total de reportes não enviados
3. Calcula-se o total de reportes esperados: não enviados + recebidos até 7 dias da data da transação
4. O quociente entre os faltantes pelos esperados representa o percentual de não cumprimento, e o SLA do dia para a organização é calculado por [1-(faltantes/esperados)]*100
Em um exemplo prático:
- Apuração em 11/08/2025 para o Banco X
- Quantidade de reportes transacionados de 03/08/2025 enviados pelo Banco X até 10/08/2025 para o endpoint /payments, método POST = 18
- Quantidade de reportes transacionados de 03/08/2025 enviados contra o Banco X, endpoint /payments, método POST e que não foram pareados (Banco X faltante) = 2
- Quantidade de reportes esperados transacionados em 03/08/2025 = 18 + 2 = 20
- SLA do Banco X de 03/08/2025 para o endpoint /payments e método POST = [1 - (2/20)] * 100 = 90%
- Neste exemplo, o Banco X receberá um ticket de não cumprimento do SLA

## Pontos importantes

- O envio do ticket ocorre se o total reportado pela organização para qualquer endpoint e contra a organização estiver abaixo de 99% durante 7 dias a partir da data de transação, independente do total de envios realizados pela organização no dia.
- Neste caso, se uma organização enviar reportes de 10 endpoints diferentes mas 1 deles estiver com SLA abaixo de 99%, o ticket será enviado independente do percentual dos outros endpoints.
- Essas regras valem também para os percentuais de UNPAIRED e PAIRED__INCONSISTENT superiores a 1%

## Arquivo de evidências
Todo ticket aberto possui anexado um arquivo de evidências, onde são listados até 5 fapiInteractionId para cada caso encontrado por dia, para facilitar a investigação das causas pelas organizações. **Campos do arquivo de evidências** 
- org_faltante: organização que não enviou o reporte, identificado através de reportes onde ela é a contraparte faltante no pareamento
- nome_faltante: nome da organização que não enviou o reporte
- data_referencia: data da transação do reporte no formato GMT
- endpoint: endpoint do reporte que não cumpriu o SLA
- httpmethod: método do reporte que não cumpriu o SLA
- clientorgid: id da organização identificada com client no reporte encontrado contra a organização notificada
- serverorgid: id da organização identificada com server no reporte encontrado contra a organização notificada
- perc_sla: percentual calculado do SLA
- perc_unpaired: percentual dos reportes com status UNPAIRED na data de referência
- perc_paired_inconistent: percentual dos reportes com status PAIRED_INCONSISTENT na data de referência
- evidencias_de_xfapi: até 5 xfapis que violaram o SLA ou os percentuais de UNPAIRED ou PAIRED_INCONSISTENT