---
id: 17369300
title: Dados Cadastrais e Transacionais - DC
version: 13
modified: 2024-07-12T17:29:01.118Z
url: /spaces/OF/pages/17369300/Dados+Cadastrais+e+Transacionais+-+DC
---

Clientes poderão solicitar o compartilhamento entre[instituições participantes](https://openfinancebrasil.org.br/quem-participa/)de seus dados cadastrais, de informações sobre transações em suas contas, cartão de crédito e produtos de crédito contratados.O compartilhamento ocorre apenas se a pessoa autorizar através da API de Consentimento, sempre para finalidades determinadas e por um prazo específico. E será possível para o cliente cancelar essa autorização a qualquer momento em qualquer uma das instituições envolvidas no compartilhamento.
### Orientações para implementação
​As instruções para implementação das APIs e seus respectivos fluxos estão detalhadas nas páginas de "Orientações" de cada API.​
## Mapeamento de roles, scopes e permissions das APIs de Dados do Cliente
A tabela de roles, scopes e permissions das APIs de Dados do Cliente Open Finance Brasil pode ser consultada [neste documento](https://openfinancebrasil.atlassian.net/wiki/download/attachments/7996438/Mapeamento_scopes_roles_permissions.xlsx?api=v2).
## Fluxo básico de consentimento
Disponibilizamos neste [link](https://openbanking-brasil.github.io/areadesenvolvedor/documents/fluxo_basico_consentimento.pdf) em formato pdf o arquivo contendo o desenho básico do fluxo de consentimento.Adicionalmente é possível consultar aqui um fluxo mais detalhado elaborado pelo GT Segurança.
## Tempestividade dos dados na Fase 2
Conforme publicado na [Resolução nº 86](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=resolu%C3%A7%C3%A3o%20BCB&numero=86) admite-se que os dados compartilhados pela instituição transmissora dos dados tenham como defasagem máxima em relação à sua disponibilização em seus canais eletrônicos:
- I - até cinco minutos, com relação aos dados relativos ao saldo e às transações realizadas em conta de depósitos ou de pagamento;
- II - até uma hora, para os demais casos.