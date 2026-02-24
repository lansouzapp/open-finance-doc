---
id: 1477280879
title: v.19.00.01 Gestão de Pix - Jornada Básica de Iniciação de Pagamento
version: 1
modified: 2026-01-23T17:46:08.548Z
url: /spaces/OF/pages/1477280879/v.19.00.01+Gest+o+de+Pix+-+Jornada+B+sica+de+Inicia+o+de+Pagamento
---

Requisitos e recomendações para gestão de pagamentos com Pix - Jornada Básica de Iniciação de Pagamento via Open Finance. Esta seção serve como base para as demais jornadas de pagamento com Pix oferecidas no Open Finance. #F4F5F7
## Requisitos - ID
**Cenário: Sobre a área de gestão de pagamentos**
1. Área de gestão de pagamentos: Disponibilizar, dentro do Open Finance, ambiente para gestão de contas vinculadas, autorizações e pagamentos.
Área de gestão de pagamentos - ID 
#F4F5F7
## Requisitos - ITP
**Cenário: Sobre a área de gestão de pagamentos**
1. Área de gestão de pagamentos: Disponibilizar, dentro do Open Finance, ambiente para gestão de contas vinculadas, autorizações e pagamentos quando: Oferecer serviços de Pix Agendado, Pix Automático e/ou Transferências Inteligentes. Atuar no escopo de compartilhamento de dados. Diferenciar, com clareza, a área para gestão de compartilhamento de dados da área para gestão de pagamentos.
2. Diferenciação das transações: Quando a ITP não for obrigada a disponibilizar a área para gestão de pagamentos, diferenciar no histórico, os pagamentos realizados via Open Finance daqueles realizados diretamente na instituição.   Ex.: Filtros ou iconografia.
Área de gestão de pagamentos - ITP #F4F5F7
## Requisitos - ID e ITP
**Cenário: Consulta aos pagamentos**As Instituições devem atualizar os status de cada pagamento de forma sincronizada e possibilitar que o usuário visualize os mesmos detalhes em suas áreas de gestão conforme as regras do arranjo de pagamento. 
1. Status dos pagamentos: Exibir o status de cada pagamento. Ex.: Concluído, Agendado, Cancelado, Pendente etc.
2. Detalhes dos pagamentos concluídos: Possibilitar que o usuário acesse um comprovante com os detalhes de cada pagamento concluído contendo as seguintes informações, conforme definido pelo arranjo de pagamento: Valor do pagamento. Data e hora/minuto/segundo (horário de Brasília) do pagamento. Identificador da transação ( `endtoEndID` do Pix). Forma de pagamento. Identificação do recebedor (nome completo, CPF mascarado/CNPJ e instituição recebedora). Descrição do pagamento, quando aplicável. Valor da tarifa do serviço, quando aplicável. Identificação do pagador (nome completo, CPF/CNPJ e Detentora). Informações adicionais exigidas pelo arranjo Pix, conforme regulação vigente.
Consulta aos pagamentos 
1. Detalhes dos pagamentos não concluídos: Nos casos em que o pagamento não for concluído com sucesso — como status cancelado, expirado ou rejeitado — exibir os campos aplicáveis de acordo com a disponibilidade de informações no momento da falha, conforme definido pelo arranjo Pix.
Detalhes dos pagamentos não concluídos #F4F5F7
## Recomendações - ID e ITP
**Cenário: Geral**
1. Área Pix: Possibilitar que a gestão de pagamento via Open Finance também possa ser feita na área Pix da instituição.
2. Busca: Oferecer funcionalidades de pesquisa, classificação e filtros, para permitir que o usuário encontre os pagamentos com facilidade.
Gestão de pagamentos - Geral - Recomendações