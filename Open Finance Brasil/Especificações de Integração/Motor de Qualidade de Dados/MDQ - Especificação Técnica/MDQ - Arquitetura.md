---
id: 362578657
title: MDQ - Arquitetura
version: 4
modified: 2025-03-27T11:59:54.672Z
url: /spaces/OF/pages/362578657/MDQ+-+Arquitetura
---

1. Arquitetura
2. Proxy reverso
3. Diagramas de Sequência Fluxo da Receptora Fluxo da Transmissora Fluxo de Atualização de Configuração Fluxo de Validação Fluxo de Envio de Resultados

## Arquitetura
Apesar de ter sido criada como um monolito, a aplicação MQD – Client foi desenvolvida com um desacoplamento em componentes, o que permitirá futuramente dividi-la em seções menores (microserviços) se necessário.Arquitetura do Motor de Qualidade de Dados (MQD)
## Componentes

| Serviço | Descrição | Tecnologia | Versão |
| --- | --- | --- | --- |
| SERVICE | Serviço executado na Instituição financeira que envia a resposta obtida ao MQD | N.A | N.A |
| API | API REST que expõe os métodos necessários para validar as mensagens da RECEPTORA | Go | 1.20 |
| CONFIGURATION MANAGER | Componente responsável por ler os arquivos de configuração e estabelecer os valores encontrados para que a aplicação possa utilizá-los | Go | 1.20 |
| MONITORING | Componente responsável pela criação das métricas da aplicação, tanto de desempenho quanto de negócio | Go OpenTelemetry | 1.20 |
| QUEUE MANAGER | Linha que armazena as mensagens recebidas pela API | Go | 1.20 |
| MESSAGE PROCESS WORKER | Componente que lê a fila de tarefas e processa cada uma das mensagens | Go | 1.20 |
| VALIDATOR | Componente que valida mensagens convertendo-as em objetos e executando uma validação baseada em um esquema JSON para cada um dos endpoints | Go | 1.20 |
| QUEUE RESULTS | Linha que salva os resultados das mensagens já validadas | Go | 1.20 |
| RESULT PROCESSOR | Componente responsável por processar os resultados, criando um resumo de cada janela de tempo (definida na configuração) e enviando-os ao servidor MQD | Go | 1.20 |
| MQD SERVER PROXY | Servidor proxy reverso responsável por estabelecer uma conexão segura com o servidor | NGINX | 1.25 |
| GATEWAY | Camada responsável pelo controle e administração das APIs do servidor MQD | AWS Gateway | N.A. |