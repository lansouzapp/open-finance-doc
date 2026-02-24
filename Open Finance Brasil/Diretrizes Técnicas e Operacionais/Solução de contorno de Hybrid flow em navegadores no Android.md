---
id: 817823765
title: Solução de contorno de Hybrid flow em navegadores no Android
version: 2
modified: 2025-03-13T19:23:18.626Z
url: /spaces/OF/pages/817823765/Solu+o+de+contorno+de+Hybrid+flow+em+navegadores+no+Android
---

Algumas instituições receptoras/iniciadoras reportaram um problema que ocorre especificamente na utilização do fluxo *web-to-app* quando a parte web se inicia via Google Chrome, ou navegadores semelhantes, em dispositivos Android. ​Este problema acontece porque o Google Chrome, no momento de redirecionamento para o aplicativo da instituição detentora/transmissora, realiza uma pré validação do link de redirecionamento, e essa pré validação acaba "queimando" a URL de *request_uri*. Essa "queima" acontece porque segundo a RFC 9126, sessão 4, é recomendado que a URL *request_uri* seja de uso único, portanto uma segunda chamada a ela deveria ser invalidada. Esta recomendação combinada com o comportamento do Google Chrome em dispositivos Android causa um problema na experiência do usuário, pois o mesmo fica impossibilitado de completar a aprovação do consentimento. ​Para contornar este problema, foi encontrada uma solução que pode ser aplicada diretamente pelos receptores/iniciadores e este contorno está documentado no video abaixo. Essa solução se baseia na criação de um *intent* com base no *package* da aplicação da instituição transmissora/detentora para que o redirecionamento ocorra diretamente para o aplicativo sem requisição “*pre flight*” realizadas pelo próprio navegador Chrome. **Demonstração da implementação da solução**