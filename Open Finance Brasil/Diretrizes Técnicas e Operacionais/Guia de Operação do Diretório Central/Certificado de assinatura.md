---
id: 941818211
title: Certificado de assinatura
version: 1
modified: 2025-05-03T04:21:29.937Z
url: /spaces/OF/pages/941818211/Certificado+de+assinatura
---

A documentação de segurança do Open Finance Brasil estabelece que as organizações devem emitir um certificado de assinatura (BRSEAL) por Autoridades Certificadoras (ACs) reconhecidas pela cadeia ICP Brasil e em seguida, inseri-lo no Diretório de participantes com a opção EXTERNAL BRSEAL.Ao adicionar o certificado no Diretório duas validações serão feitas:
1. O Diretório validará que o certificado foi assinado por uma das ACs credenciadas ao Open Finance Brasil, cuja lista completa pode ser encontrada na documentação de segurança. – É possível executar essa consulta avaliando se o issuer do certificado está na lista citada, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl - openssl x509 -in brcac.pem -noout -issuer

1. O Diretório validará que o certificado possui UID em seu subject igual ao Organisation ID no caso do BRSEAL – É possível executar essa consulta avaliando se o UID do subject é igual ao UID apresentado no diretório, que pode ser obtido utilizando a ferramenta openssl com o seguinte commando: openssl x509 -in brcac.pem -noout –subject
No ambiente sandbox, é possível a geração de certificados de assinatura emitidos pelo próprio Diretório para uso exclusivo neste ambiente.[Clique para conferir o passo a passo para registro de certificado de assinatura](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941819091/08.+Carregando+certificados+emitidos+por+autoridade+de+certifica+o+em+Produ+o?atlOrigin=eyJpIjoiYzQwOGU0ZDJkZDE1NDMwMWI1NjczNmM3NDUzNTA0N2MiLCJwIjoiYyJ9)[Clique para conferir o passo a passo para emissão de certificados no Diretório para uso exclusivo do ambiente sandbox](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/941818944/07.+Criando+certificados+de+transporte+e+assinatura+em+Sandbox?atlOrigin=eyJpIjoiMTczZTY1OGUwOGY0NDE3ZmE5YTY5MWM4YzQyMjhjNWQiLCJwIjoiYyJ9)