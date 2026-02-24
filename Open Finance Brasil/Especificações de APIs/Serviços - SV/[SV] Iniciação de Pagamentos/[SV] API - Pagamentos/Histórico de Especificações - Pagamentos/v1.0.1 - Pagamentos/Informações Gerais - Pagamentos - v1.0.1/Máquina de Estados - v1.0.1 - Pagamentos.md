---
id: 17376637
title: Máquina de Estados - v1.0.1 - Pagamentos
version: 1
modified: 2022-10-27T12:03:42.182Z
url: /spaces/OF/pages/17376637/M+quina+de+Estados+-+v1.0.1+-+Pagamentos
---

#### Os possíveis status do consentimento são:
AWAITING_AUTHORISATION - Aguardando autorização AUTHORISED - Autorizado REJECTED - Rejeitado CONSUMED - ConsumidoAlgumas definições são importantes para tratar a transição dos estados do consentimento em diferentes momentos do fluxo:
#### AWAITING_AUTHORISATION

- O consentimento é sempre criado com o status AWAITING_AUTHORISATION. Ele pode ser aprovado antes do tempo de expiração de 5 minutos, assumindo o status AUTHORISED. Se não, deve assumir o status REJECTED caso expire ou seja cancelado pelo usuário.

#### AUTHORISED

- Para o cenário em que o status assumiu AUTHORISED, o tempo máximo do expirationDateTime do consentimento deve assumir "now + 60 minutos". Este é o tempo para consumir o consentimento autorizado, mudando seu status para CONSUMED. Não é possível prorrogar este tempo e a criação de um novo consentimento será necessária para os cenários de insucesso. O tempo do expirationDateTime é garantido com os 15 minutos do access token, sendo possível utilizar mais três refresh tokens até totalizar 60 minutos.

##### REJECTED

- Em caso de consentimento expirado a Detentora deverá retornar o status REJECTED.
- Em caso de consentimento rejeitado pelo usuário ou por regra de negócio da Detentora, o status deverá ser retornado como REJECTED.

#### CONSUMED

- O consentimento assume o status CONSUMED após ocorrer o processamento da iniciação do pagamento, seja ele com sucesso (HTTP 201) ou ainda em casos de insucesso (HTTP 422) retornados pela Detentora. Para os demais códigos HTTP não há mudança de status do consentimento, o mesmo permanecerá AUTHORISED, respeitando o tempo máximo de expiração do consentimento (60 minutos).

### Recomendação uso de polling

#### A consulta via GET, para verificar o processamento da transação, pode ser efetuada a qualquer momento desde que se respeite o rate limit de:

- 300 TPS global, 50 TPS por instituição e 8 TPS por endereço IP (Internet Protocol). Como sugestão, é indicado que a instituição iniciadora do pagamento implemente um retry exponencial.