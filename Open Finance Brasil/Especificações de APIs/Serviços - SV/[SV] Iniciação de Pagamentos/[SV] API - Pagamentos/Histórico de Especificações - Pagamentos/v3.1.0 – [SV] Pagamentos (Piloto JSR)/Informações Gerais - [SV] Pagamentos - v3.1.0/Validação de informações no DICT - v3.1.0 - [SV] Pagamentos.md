---
id: 164528725
title: Validação de informações no DICT - v3.1.0 - [SV] Pagamentos
version: 4
modified: 2023-12-06T16:50:58.567Z
url: /spaces/OF/pages/164528725/Valida+o+de+informa+es+no+DICT+-+v3.1.0+-+SV+Pagamentos
---

:warning:atlassian-warning#FFF0B3O conteúdo criado nessa página deve ser utilizado pelas instituições que forem participar do desenvolvimento do piloto da jornada sem redirecionamento. Caso a instituição não tenha se voluntariado a participar seguir com a implementação da versão 3.0.0.A detentora de conta poderá optar em qual momento e se realizará validações no DICT.**Opção 1: Criação do Pagamento - POST /pix/payments (síncrona)**Neste cenário o pagamento não é criado, porém o consentimento é consumido e está com o status CONSUMED.
- Retorno da API POST /pix/payments: Caso seja um erro por dados inválidos, o retorno deve ser um erro HTTP 422, com código " DETALHE_PAGAMENTO_INVALIDO ", título “ Detalhe do pagamento inválido. ” e descrição “ Parâmetro [nome_campo] diverge do cadastrado no DICT. ”; Caso seja um erro de suspeita de fraude o retorno deve ser um erro HTTP 422, com código " NAO_INFORMADO ", título " Não informado. " e descrição “ Não reportado/identificado pela instituição detentora de conta. "
**Opção 2: Processamento do pagamento – POST /pix/payments (assíncrona)**Neste cenário o pagamento é criado com sucesso e o consentimento é consumido, porém, as validações contra o DICT só ocorrerão de forma assíncrona e em caso de negativa será percebido pela iniciadora na consulta do pagamento.**Primeira requisição: Retorno da API POST /pix/payments:**
- Sucesso HTTP 201 e status de pagamento RCVD.
**Segunda requisição: Retorno da API GET /pix/payments/{paymentId}**
- Caso seja um erro por dados inválidos o retorno deve ser um sucesso HTTP 200, com status de pagamento RJCT e motivo " DETALHE_PAGAMENTO_INVALIDO ";
- Caso seja um erro por suspeita de fraude o retorno deve ser um erro HTTP 200, com status de pagamento RJCT e motivo " NAO_INFORMADO ".