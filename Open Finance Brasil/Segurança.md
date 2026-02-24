# Assinaturas > Histórico da página - Assinaturas

---
id: 240650215
title: Histórico da página - Assinaturas
version: 2
modified: 2023-12-15T14:54:47.180Z
url: /spaces/OF/pages/240650215/Hist+rico+da+p+gina+-+Assinaturas
---

## Change log
 
| De / Para - Versão | Item de trabalho (Conteúdo Motivador) | Demandante | O que foi alterado? | Motivador |
| --- | --- | --- | --- | --- |
| | | | | |
| | | | | |

---

# Assinaturas > v1.0 - Assinaturas

---
id: 240650189
title: v1.0 - Assinaturas
version: 2
modified: 2023-12-15T14:54:42.698Z
url: /spaces/OF/pages/240650189/v1.0+-+Assinaturas
---

Sobre os certificados exigidos para assinatura de mensagens - Padrões de certificados digitais Open Finance Brasil: [https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82313425/PT+Padr+o+de+Certificados+Open+Finance+Brasil+2.0#Certificado-de-Assinatura](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82313425/PT+Padr+o+de+Certificados+Open+Finance+Brasil+2.0#Certificado-de-Assinatura)Sobre os algoritmos usados para assinatura de mensagens JWS - Perfil de segurança FAPI - Open Finance Brasil: [PT] Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3Sobre mensagens assinadas, JWS e JWKS - Guia de usuário (Receptoras e iniciadoras de pagamento): [https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82346047/PT+Guia+do+Usu+rio+para+Institui+es+Receptores+de+Dados+e+Iniciadores+de+Pagamento+TTP+PISP#O-que-%C3%A9-um-JWT%2C-JWE%2C-JWS-e-JWK-%7B%23JWT_JWE_JWS_JWK)](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82346047/PT+Guia+do+Usu+rio+para+Institui+es+Receptores+de+Dados+e+Iniciadores+de+Pagamento+TTP+PISP#O-que-%C3%A9-um-JWT%2C-JWE%2C-JWS-e-JWK-%7B%23JWT_JWE_JWS_JWK))

---

# Casos de Erro > Histórico da página - Casos de Uso

---
id: 240650277
title: Histórico da página - Casos de Uso
version: 2
modified: 2023-12-15T14:55:09.761Z
url: /spaces/OF/pages/240650277/Hist+rico+da+p+gina+-+Casos+de+Uso
---

## Change log
 
| De / Para - Versão | Item de trabalho (Conteúdo Motivador) | Demandante | O que foi alterado? | Motivador |
| --- | --- | --- | --- | --- |
| | | | | |
| | | | | |

---

# Casos de Erro > v1.0 - Casos de Erro

---
id: 240650255
title: v1.0 - Casos de Erro
version: 2
modified: 2023-12-15T14:54:59.312Z
url: /spaces/OF/pages/240650255/v1.0+-+Casos+de+Erro
---

A **convenção do Open Finance Brasil**mapeou alguns erros esperados durante o fluxo do usuário no ecossistema. Existem orientações específicas já tratadas no [Manual do Usuário](https://openbankingbrasil.atlassian.net/wiki/spaces/DraftOF/pages/6128557/Guia+de+Experi+ncia+do+Usu+rio). Aqui, trataremos a visão mais técnica do que pode ser feito em caso de erro.
- Durante o redirecionamento do Consentimento, não se encontrou o browser no dispositivo do usuário: Além da orientação ao usuário, deve-se perceber que o fluxo de Consentimento continua pendente. Como a intenção de Consentimento segue válida por 60 minutos, deve-se tentar utilizar o mesmo Consentimento para tentar novamente a autorização do usuário.
- Durante o redirecionamento do Consentimento, houve um problema inesperado no servidor do Transmissor (HTTP Code 4xx ou 5xx): Além da orientação ao usuário, deve-se perceber que o fluxo de Consentimento continua pendente. Como a intenção de Consentimento segue válida por 60 minutos, deve-se tentar utilizar o mesmo Consentimento para tentar novamente a autorização do usuário.
- Durante o redirecionamento do Consentimento, houve um problema inesperado no servidor do Transmissor ( Timeout , queda de Internet, etc.): Além da orientação do usuário, deve-se perceber que o fluxo de Consentimento continua pendente. Como a intenção de Consentimento segue válida por 60 minutos, deve-se tentar utilizar o mesmo consentimento para tentar novamente a autorização do usuário.
- Durante o redirecionamento do Consentimento, houve um problema com o Login do usuário (erro de credenciais): Além da orientação ao usuário, deve-se perceber que o fluxo de Consentimento continua pendente. Como a intenção de Consentimento segue válida por 60 minutos, deve-se tentar utilizar o mesmo Consentimento para tentar novamente a autorização do usuário.
- Após o Consentimento do lado do Receptor, o usuário não confirma o compartilhamento: Além da orientação ao usuário, deve-se perceber que o fluxo de Consentimento continua pendente. Como a intenção de Consentimento segue válida por 60 minutos, deve-se tentar utilizar o mesmo Consentimento para tentar novamente a autorização do usuário.
- Após o Consentimento completo, o app do Receptor não consegue acessar os dados por indisponibilidade: Deve-se tentar novamente. Access Token ainda é válido, portanto deve-se tentar novamente sem maiores prejuízos técnicos.
- Após o Consentimento completo, o app do Receptor não consegue acessar os dados por pendência de autorização de um terceiro (ex.: Dupla alçada): Deve-se consultar a API de Resources para verificar as pêndencias e saber como proceder.

---

# Dynamic Client Registration > DCR-BR v2.1.0 - Open FinanceBrasil Dynamic Client Registration > [EN]  Open Finance Brasil Dynamic Client Registration - v2.1.0

---
id: 1334116474
title: [EN]  Open Finance Brasil Dynamic Client Registration - v2.1.0
version: 2
modified: 2025-12-02T19:19:16.407Z
url: /spaces/OF/pages/1334116474/EN+Open+Finance+Brasil+Dynamic+Client+Registration+-+v2.1.0
---

17
## Foreword
Este documento também está disponível em [português](file:///C:/wiki/spaces/DraftOF/pages/76251331)The Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.Open Finance Brasil Financial-grade API Security Profile 1.0 consists of the following parts:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introduction
The Open Finance Brasil Financial-grade API Dynamic Client Registration Profile is a profile of [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) and [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) that aims to provide specific implementation guidelines for security and interoperability which can be applied to the identification, registration and management of OAuth Clients operating in the Brasil Open Finance ecosystem.Although it is possible to code an OpenID Provider and Relying Party from scratch using this specification, the main audience for this specification are parties who already have a certified implementation of [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) and seek to obtain certification for the Brasil Open Finance programme.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml). These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the method of
- applications registered in the Open Finance Directory of Participants to discover OpenID Providers offering services in the Open Finance Brasil ecosystem;
- applications to use OpenID Connect Registration to onboard their applications with Bank OpenID Providers; and
- applications to use OAuth 2.0 Dynamic Client Registration Management Protocol to manage their applications with OpenID Providers;
This document is applicable to all participants engaging in Open Finance in Brasil.
## 2. Normative references
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger
## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) and ISO29100 apply.
## 4. Symbols and Abbreviated terms

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security

## 5. Introduction
Brasil Open Finance ecosystem leverages a federation trust provider or directory of participants as the golden source of information on accredited participants and software that are authorized to partake in the Open Finance Brasil ecosystem.The services by the Directory include
- Software registration and management.
- Software credential registration and management using ICP Certificates.
- Software Statement Assertion (SSA) generation
Participants within the ecosystem must leverage these services to facilitate API driven OAuth client registration using the process outlined in clause 3.1.1 of [RFC7591](https://tools.ietf.org/html/rfc7591) with additional metadata necessary to support OpenID Connect defined in [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).It's important to remember that the client registration payload has most of its attributes as non-mandatory, and that assigned values that conflict with those in the software statement assertion will be overridden by the values of the software statement assertion issued by the Directory of Participants. Not all metadata a client wishes to provide may be contained in a software statement, e.g alternative [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). There are some cases where the client metadata are subset of the existing values in the SSA, such as redirect_URIs.
## 6. Open Finance Brasil OpenID Connect Discovery provisions

### 6.1. Authorization server
The Authorization Server shall support [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) as required by [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). This support shall be explicit in Participant Directory configurations, and in the declaration of its attributes in the Discovery file (well-known), respecting the authentication mechanisms certified by the institution through the Open Finance Brazil compliance tests.In addition, the Authorization Server:
1. shall advertise its presence in the Open Finance Brasil ecosystem by being listed on the Directory of Participants;
2. shall advertise all Open Finance Brasil REST API resources protected by the OpenID Provider on the Directory of Participants;
3. shall advertise support for all signing, encryption, authentication mechanisms and standards required to support Open Finance Brasil Financial API ;
4. shall advertise support for OpenID Dynamic Client Registration ;
5. may advertise mtls_endpoint_aliases as per clause 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens the token_endpoint, registration_endpoint, userinfo_endpoint and push_authorization_request_endpoint;
6. if supporting Financial API - Client Initiated Back Channel Authentication shall advertise through OIDD mtls_endpoint_aliases the backchannel_authentication_endpoint;
7. shall not rotate the registration_access_token.

### 6.2. Client
The Client shall support [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) as required by [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html)In addition, the Client
1. shall rely on ecosystem discovery services provided by Directory of Participants only;
2. shall derive necessary Authorisation Server metadata by relying on an Authorization Servers OpenID Connect Discovery services only;
3. where present, shall use endpoints advertised in mtls_endpoint_aliases as per clause 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens ;

## 7. Open Finance Brasil OpenID Connect Registration Provisions

### 7.1. Authorization server
The Authorization Server shall support the RFC RFCs Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) and [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)In addition, the Authorization Server
1. shall reject dynamic client registration requests not performed over a connection secured with mutual tls using certificates issued by Brazil ICP (production) or the Directory of Participants (sandbox);
2. shall validate that the request contains software_statement JWT signed using the PS256 algorithim issued by the Open Finance Brasil directory of participants;
3. shall validate that the software_statement was issued (iat) not more than 5 minutes prior to the request being received;
4. shall validate that the attribute jwks (key set by value) was not included; but declared as a reference in the jwks_uri attribute;
5. shall, when informed, validate that jwks_uri matches the software_jwks_uri provided in the software_statement; shall validate if the content obtained through jwks_uri contains a certificate of type use: “enc”;
6. shall require and validate that redirect_uris matches or contains a sub set of software_redirect_uris provided in the software_statement;
7. shall require and validate that all client authentication mechanism adhere to the requirements defined in RFC7591 and RFC7592 , validating the registration_access_token and, through a secure connection, the certificate chain of ICP-Brasil;
8. removed;
9. shall validate that the requested scopes are adequate for accredited institutions and their regulatory roles and contained in the software_statement. The list of regulatory permissions and the corresponding scopes are described in the following sections;
10. where possible, shall compare client metadata asserted by a client to the metadata provided in the software_statement, choosing values in the SSA with precedence;
11. shall accept all x.500 AttributeType name strings defined in the Distinguished Name of the x.509 Certificate Profiles defined in Open Finance Brasil x.509 Certificate Standards ;
12. The value of the field UID of the certificate should match the one sent in the SSA, where the UID field should contain the value of the software_id field of the SSA.
13. shall, during the TLS handshake process, use the distinguishedNameMatch rule to compare the DN values as defined in RFC4517 .
14. shall ensure the integrity of the stock of active consents, even after any systemic changes, so that such changes are transparent to the data receiver institutions (TPP).
15. shall perform a recertification on OIDF FAPI and DCR after any systemic changes.
16. The value of the software_api_webhook_uris attribute contained as an attribute in the JWS in software_statement must be compared with the webhook_uris field. If the values are not exactly the same, the error must be returned, with the HTTP status code set to 400, error filled in as invalid_webhook_uris and error_description filled in with The content of the webhook_uris field different from what was Registered in the software_statement noted via the JWS software_api_webhook_uris field.
17. If the webhook_uris field is not declared in the payload, the webhook functionality shall be considered disabled for the specific client.
These provisions apply equally to the processing of [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) and [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html) requests
#### 7.1.1. Applying Server Defaults
Whenever properties of a DCR request are not included nor mandatory in the specification, the Authorisation Server shall apply client defaults in the following manner:
1. shall select and apply the encryption algorithm and cipher choice from the most recommended of the IANA cipher suites that is supported by the Authorisation Server;
2. shall populate defaults from values within the software_statement assertion where possible;
3. shall grant the client permission to the complete set of potential scopes based on the softwares regulatory permissions included in the software_statement;

### 7.2. Regulatory Roles for OpenID and OAuth 2.0 Mappings
To participate in the Open Finance ecosystem, accredited institutions must register themselves in the directory of participants according to their regulatory roles. Those roles reflect the institutions authorization from the Central Bank and, consequently, the APIs they are allowed to use.The following table describes the regulatory roles for Open Finance and the related OAuth 2.0 scopes mapping. If the scopes are omitted during the DCR process, the authorization server shall grant the complete set of potential scopes based on the registering bank's regulatory roles, as described in the Server Defaults section.
| Regulatory Role | Description | Allowed Scopes | Target Phase |
| DADOS | Instituição transmissora ou receptora de dados (AISP) | openid accounts credit-cards-accounts consents customers invoice-financings financings loans unarranged-accounts-overdraft resources credit-fixed-incomes exchanges bank-fixed-incomes variable-incomes treasure-titles funds credit-portability | Phase 2 and Phase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid payments recurring-payments nrp-consents | Phase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Phase 3 |
| CCORR | Correspondente de crédito | openid | Phase 3* |
It is requiread that the active roles in the application's software_statement are validated. The field _software_statement_roles shall be used for validation and currently listed roles shall be active.
## 8. Software Statement Assertion
A Software Statement Assertion (software_statement) is a JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) that asserts the metadata values of the client software as a whole. On the Open Finance Brasil structure, this software_statement is signed by the Participants Directory and it's signature MUST be validated by the Authorization Servers using the public keys available on the following session.
### 8.1. Attributes of the Software Statement Assertion (Claims)
The following example contains all attributes currently included in a software_statement:wide1800
## 9. Processing of the Dynamic Client Registration claim

### 9.1. Sending a Registration Claim with a Software Statement
This example includes several optional fields, some of those may not be applicable to some implememntations. For a complete guide to attributes and its mandate, consult the DCR Swagger [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). Line breaks inside values serve presentation purposes only.wide1800
### 9.2. Open Finance Brasil SSA Key Store and Issuer Details
The following links point to public keys of the Participant Directory and must be used to verify the signature validity of the software_statements presented during the client registration process.**Production**[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)Open Finance Open Finance Brasil production SSA issuer**Sandbox**[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)Open Finance Open Finance Brasil sandbox SSA issuer
### 9.3. About authentication and authorization mechanisms for DCR and DCM services
As they are auxiliary services to the main flow of Open Finance Brasil, the dynamic registration and maintenance services for clients do not use the same access control mechanisms. For example, it is not possible to require an OAuth 2.0 access_token from a client application that isn't registered yet with the transmitting institution.To extend [RFC7591](https://tools.ietf.org/html/rfc7591) and [RFC7592](https://tools.ietf.org/html/rfc7592), which recommend minimum mechanisms for authentication of their services, institutions that support the registration flows and dynamic maintenance of clients must implement the following controls:
#### 9.3.1. Client registration - POST /register

1. validate that the certificate presented by the client application is subordinate to the ICP-Brasil chains defined in the Open Finance Brasil Certificates Standard;
2. ensure that the signature of the software_statement_ presented by the client application during registration has been made by the Directory of Participants using the public keys described in the previous section;
3. ensure that the software_statement presented by the client application during registration corresponds to the same institution as the client certificate presented, validating it through the attributes that bring organization_id in the X.509 certificate.
4. Multiple DCR registrations for the same Software Statement should not be allowed, in a way that in case of a new registration attempt for an already registered Software Statement, the Error Response procedure defined on item 3.2.2 of the RFC7591 must be enforced.
5. issue, on the registry response, a registration_access_token to be used as an authentication token on maintaining operations of the registered client application, following specifications described in RFC7592 .

#### 9.3.2. Client Maintenance - GET /register - PUT /register - DELETE /register

1. Validate the presence and matching of the Bearer header Authorization containing the value of the registration_access_token attribute returned during registration of the corresponding client.
2. When the invoked method is PUT / register, carry out the validations of sub-items 1, 2, 3, and 5 of item Client registration - POST /register .
3. When the invoked method is GET /register, carry out the validations of sub-items 1 and 5 of item Client registration - POST /register .
4. When the invoked method is DELETE /register, carry out the validation of sub-item 1 of item Client registration - POST /register .

### 9.4. Signature certificates validation

- The directory uses cert rescan function hourly to validation process.
- The organization shall ensure that the validation process was completed.
- Each organization must have a continuity plan in case of unavailability validation service.
- If the signature certificate is not valid because it has a revoked status according to the CA’s OCSP/CRL issuer, or is inactive in the directory register, the set of public keys is moved to the inactive key storage.
- The validation process should include: Resource server (Data Transmitter) message signature validation, to be done by the Client (Data Receiver) Validate that the message was signed in line with what’s defined on the Message Signature Guidelines, including that the iss is equal to the organisation_id of the server that issued the message. Fetch the “iss” claim from the JWT and build the directory application JWKS uri for that specific server. Make sure that the kid present on the message JWT header is present on the directory JWKS. Validate that the private key for the corresponding kid is able to validate the message signature. Client (Data Receiver) message signature validation, to be done by the Resource Server Validate how the message was signed in line with what’s defined on the Message Signature Guidelines. Obtain the org_jwks_uri which was presented on the SSA by the client on the moment of the registration (DCR) Make sure that the kid present on the message JWT header is present on the directory JWKS. Validate that the private key for the corresponding kid is able to validate the message signature.

## 10. Acknowledgement
With thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Caio Zanolla (Belvo)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
### A.1. Appendix A. Example Software Statement Assertion
wide1800
## Author's Address
OFBIS GT SecurityOpen Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Dynamic Client Registration > DCR-BR v2.1.0 - Open FinanceBrasil Dynamic Client Registration > [PT]  Open Finance Brasil Dynamic Client Registration - v2.1.0

---
id: 1334116369
title: [PT]  Open Finance Brasil Dynamic Client Registration - v2.1.0
version: 2
modified: 2025-12-02T19:18:48.099Z
url: /spaces/OF/pages/1334116369/PT+Open+Finance+Brasil+Dynamic+Client+Registration+-+v2.1.0
---

17
## Prefácio
The normative version in EnglishA Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. O EIOFB não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
Essas partes devem ser usadas com [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) e [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introdução
O Perfil de Registro de Cliente Dinâmico (DCR - Dynamic Client Registration) do Financal-grade API (FAPI) do Open Finance Brasil é um perfil de [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) que visa fornecer diretrizes de implementação específicas para segurança e interoperabilidade que podem ser aplicadas à identificação, registro e gerenciamento de Clients OAuth operando no ecossistema Open Finance Brasil.[¶](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#section-note.2-1)Embora seja possível codificar um OpenID Provider e Relying Party desde o princípio usando esta especificação, o principal público para esta especificação são as partes que já possuem uma implementação certificada do [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) e desejam obter a certificação para o Open Finance Brasil.
## Convenções Notacionais
As palavras-chave "deve" (shall), "não deve" (shall not), "deveria" (should), "não deveria" (should not) e "pode" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml) observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 1. Escopo
Este documento especifica o método de
- aplicativos cadastrados no Diretorio de Participantes do Open Finance para descobrir OpenID Providers que oferecem serviços no ecossistema Open Finance Brasil;
- aplicativos para usar o OpenID Connect Registration para integrar seus aplicativos com OpenID Providers dos bancos; e
- aplicativos para usar OAuth 2.0 Dynamic Client Registration Management Protocol para gerenciar seus aplicativos com OpenID Providers;
Este documento é aplicável a todos os participantes do Open Finance no Brasil.
## 2. Referências normativas
Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger
## 3. Termos e definições
Para efeitos deste documento, aplicam-se os termos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e ISO29100.
## 4. Símbolos e Termos abreviados

- API - Application Programming Interface (Interface de Programação da Aplicação)
- DCR - Dynamic Client Registration (Registro de Cliente Dinâmico)
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- SS - Software Statement (Declaração de Software)
- SSA - Software Statement Assertion (Afirmação de Declaração de Software)
- TLS - Transport Layer Security

## 5. Introdução
O ecossistema Open Finance Brasil apoia-se em um provedor de confiança ou diretório de participantes como a fonte mais valiosa de informações sobre participantes credenciados e softwares que estão autorizados a participar do ecossistema Open Finance Brasil.Os serviços do Diretório incluem:
- Registro e gerenciamento de software
- Registro e gerenciamento de credenciais de software usando certificados ICP
- Geração de Software Statement Assertion (SSA)
Os participantes do ecossistema devem aproveitar esses serviços para facilitar o registro de cliente OAuth orientado por API usando o processo descrito na cláusula 3.1.1 do [RFC7591](https://tools.ietf.org/html/rfc7591) com metadados adicionais necessários para oferecer suporte ao OpenID Connect definido em [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).É importante reforçar que o payload de registro de clientes possui a maior parte de seus atributos não obrigatórios, e que os atributos cujos valores conflitem com os presentes no software statement assertion serão sobrepostos pelos valores do próprio software statement assertion emitido pelo diretório central. Nem todos os metadados que um cliente deseja fornecer podem estar contidos em um software statement, por exemplo, alternativa [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). Há casos ainda de metadados de cliente que são um subconjunto dos valores existentes no SSA, como por exemplo os redirect_URIs.
## 6. Provisionamentos do OpenID Connect Discovery do Open Finance Brasil

### 6.1. Servidor de Autorização
O servidor de autorização deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). Este suporte deve estar explicito tanto na forma como o Servidor de Autorização está registrado no Diretório de Participantes quanto na declaração dos seus atributos no arquivo de Discovery (well-known), respeitando os mecanismos de autenticação certificados pela institição através dos testes de conformidade do Open Finance Brasil.Adicionalmente, o Servidor de Autorização:
1. deve anunciar sua presença no ecossistema Open Finance Brasil, sendo listada no Diretório de Participantes;
2. deve anunciar todos os recursos API REST do Open Finance Brasil protegidos pelo Provedor OpenID no Diretório de Participantes;
3. deve anunciar suporte para todos os mecanismos de assinatura, criptografia, autenticação e padrões necessários para suportar o Open Finance Brasil Financial API ;
4. deve anunciar suporte para OpenID Dynamic Client Registration ;
5. pode anunciar mtls_endpoint_aliases de acordo com a cláusula 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens o token_endpoint, registration_endpoint, userinfo_endpoint e push_authorization_request_endpoint;
6. se suportar Financial API - Client Initiated Back Channel Authentication , deve anunciar através de OIDD mtls_endpoint_aliases o backchannel_authentication_endpoint;
7. não deve rotacionar o registration_access_token

### 6.2. Cliente
O cliente deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html).Além disso, o Cliente
1. deve contar com serviços de descoberta do ecossistemas fornecidos apenas pelo Diretório de Participantes;
2. deve derivar os metadados necessários do Authorization Server somente por meio do serviço OpenID Connect Discovery dos Authorization Servers;
3. quando presente, deve usar endpoints anunciados em mtls_endpoint_aliases conforme a cláusula 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens ;

## 7. Provisionamento de registro OpenID Connect do Open Finance Brasil

### 7.1. Servidor de Autorização
O servidor de autorização deve suportar as RFCs de Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)Além disso, o servidor de autorização
1. deve rejeitar as solicitações de registro de cliente dinâmico não realizadas em uma conexão protegida com mTLS usando certificados emitidos pelo Brasil ICP (produção) ou o Diretório de Participantes (sandbox);
2. deve validar que a solicitação contém software_statement JWT assinado usando o algoritmo PS256 emitido pelo Diretório de Participantes do Open Finance Brasil;
3. deve validar que o software_statement foi emitido (iat - issued at) não mais de 5 minutos antes do pedido ser recebido;
4. deve validar que um atributo jwks (definida por valor) não foi incluído, e sim declarado como referência no atributo jwks_uri;
5. deve, quando informado, validar que o jwks_uri corresponda ao software_jwks_uri fornecido na declaração do software; deve validar se o conteúdo obtido através do jwks_uri contém um certificado do tipo use: “enc”;
6. deve exigir e validar que o redirect_uris corresponda ou contenha um subconjunto dos valores de software_redirect_uris fornecidos no software_statement;
7. deve exigir e validar que todos os mecanismos de autenticação de cliente cumpram os requisitos definidos nas RFC7591 e RFC7592 , através da validação do registration_access_token e, como conexão segura, da cadeia de certificados confiáveis ICP-Brasil.
8. removido;
9. deve validar se os escopos solicitados são adequados para as permissões regulatórias autorizadas da instituição e contidas no _software_statement. A relação de permissões regulatórias e os escopos correspondentes está descrita nas seções a seguir.
10. deve, sempre que possível, validar os metadados declarados pelo cliente em relação aos metadados fornecidos no software_statement, adotando os valores presentes no SSA com precedência.
11. deve aceitar todos os nomes x.500 AttributeType definidas no Distinguished Name dos Perfis de Certificado x.509 definidos em Open Finance Brasil x.509 Certificate Standards ;
12. O valor do campo UID do certificado deve coincidir com o enviado no SSA, onde o campo UID deve conter o valor do campo software_id do SSA.
13. deve, durante o processo de handshake TLS, usar a regra distinguishedNameMatch para comparar os valores DN conforme definido na RFC4517 . ¶
14. deve ser garantido a todos, após os mesmos atos de consentimentos permanentes, para que também sejam alterados para instituições receptoras de dados transparentes (TPP).
15. deve realizar recertificação FAPI e DCR OIDF após eventuais alterações sistêmicas.
16. O valor do atributo software_api_webhook_uris contido como atributo no JWS em software_statement deverá ser comparado com o campo webhook_uris. Caso os valores não sejam exatamente iguais, deve-se retornar o erro, com HTTP status code setado para 400, error preenchido como invalid_webhook_uris e error_description preenchido com The content of the webhook_uris field differs from what was registered in the software_statement observed through the JWS field's software_api_webhook_uris.
17. Se o campo webhook_uris não for declarado no payload, a funcionalidade webhook deverá ser considerado como desativado para o client em questão.
Estas disposições aplicam-se igualmente ao processamento de pedidos [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)
#### 7.1.1. Aplicando Server Defaults
Quando as propriedades de uma solicitação DCR não estão incluídas e não são obrigatórias na especificação, o Authorization Server deve aplicar os padrões do cliente da seguinte maneira:
1. deve selecionar e aplicar o algoritmo de criptografia e a escolha da cifra a partir dos conjuntos mais recomendados de cifra da IANA que são suportados pelo Servidor de Autorização;
2. deve preencher defaults a partir de valores da afirmação de software_statement, sempre que possível;
3. deve conceder ao cliente permissão para o conjunto completo de escopos potenciais com base nas permissões regulatórias de softwares incluídas no software_statement;

### 7.2. Funções regulatórias para mapeamentos OpenID e OAuth 2.0
Para participar do ecossistema do Open Finance, as instituições credenciadas devem se cadastrar no Diretório de Participantes de acordo com seus papéis regulatórios. Essas funções refletem a autorização do Banco Central para as instituições e, consequentemente, as APIs que podem utilizar.A tabela a seguir descreve as funções regulatórias do Open Finance e o mapeamento de escopos do OAuth 2.0 relacionado. Se os escopos forem omitidos durante o processo de DCR, o Servidor de Autorização deve conceder o conjunto completo de escopos potenciais com base nas funções regulatórias registradas para o banco, conforme descrito na seção Server Defaults.
| Papel Regulador | Descrição | Escopos Permitidos | Fase-alvo |
| DADOS | Instituição transmissora / receptora de dados (AISP) | openid accounts credit-cards-accounts consents customers invoice-financings financings loans unarranged-accounts-overdraft resources credit-fixed-incomes exchanges bank-fixed-incomes variable-incomes treasure-titles funds credit-portability | Fase 2 e Fase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid payments recurring-payments nrp-consents | Fase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Fase 3 |
| CCORR | Correspondente de crédito | openid | Fase 3* |
É necessário validar as roles ativas no software_statement da aplicação. Na validação dessa informação deve ser utilizado o campo _software_statement_roles, e deve ser verificado se as roles listadas estão ativas.
## 8. Declaração de Software
Uma declaração de software (software_statement) é um JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) que afirma valores de metadados sobre o software cliente como um todo. Na estrutura do Open Finance Brasil, esse software_statement é assinado pelo Diretório de Participantes, e sua assinatura DEVE ser validada pelos Servidores de Autorizacao usando as chaves públicas disponíveis na seção a seguir.
### 8.1. Atributos da Declaração de Software (Claims)
O exemplo a seguir contém todos os atributos atualmente incluídos em um software_statement:wide1800
## 9. Processamento de solicitação de registro de cliente dinâmico

### 9.1. Enviar uma solicitação com uma declaração de software
Este exemplo inclui vários campos opcionais, alguns dos quais podem não ser aplicáveis a algumas implantações. Para um guia completo dos atributos e sua obrigatoriedade, consultar o Swagger DCR [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). A quebra de linha dentro dos valores são apenas para fins de exibição.wide1800
### 9.2. Open Finance Brasil SSA Key Store e detalhes do emissor
As links a seguir apontam para as chaves públicas do Diretório de Participantes, e devem ser usadas para verificar a validadade da assinatura dos software_statements apresentados durante o processo de registro de cliente.**Producão**[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)Emissor do Open Finance Open Finance Brasil SSA de produção**Sandbox**[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)Emissor do Open Finance Open Finance Brasil SSA de sandbox
### 9.3. Sobre os mecanismos de autenticação e autorização dos serviços de DCR e DCM
Por serem serviços auxiliares ao fluxo principal do Open Finance Brasil, os serviços de registro e manutenção dinâmica de clientes não utilizam os mesmos mecanismos de controle de acesso. Por exemplo: não é possível exigir um access_token OAuth 2.0 de uma aplicação cliente que ainda não está registrada na instituição transmissora. Para estender as [RFC7591](https://tools.ietf.org/html/rfc7591) e [RFC7592](https://tools.ietf.org/html/rfc7592), que recomendam mecanismos mínimos para autenticação dos seus serviços, as instituições que suportam os fluxos de registro e manutenção dinâmica de clientes devem implementar em seus Servidores de Autorização os controles a seguir:
#### 9.3.1. Registro de cliente - POST /register

1. validar que o certificado apresentado pela aplicação cliente é subordinado às cadeias do ICP-Brasil definidas no Padrão de Certificados do Open Finance Brasil;
2. assegurar que a assinatura do software_statement apresentado pela aplicação cliente durante o registro tenha sido feita pelo Diretório de Participantes através das chaves públicas descritas na seção anterior;
3. assegurar que o software_statement apresentado pela aplicação cliente durante o registro corresponda à mesma instituição do certificado de cliente apresentado, validando-o através dos atributos que trazem organization_id no certificado X.509.
4. não devem ser permitidos múltiplos cadastros DCR para o mesmo Software Statement , de forma que em caso de tentativa de novo registro para um Software Statement já cadastrado, deve se utilizar o procedimento de Error Response definido no item 3.2.2 da RFC7591.
5. emitir, na resposta do registro, um registration_access_token para ser usado como token de autenticação nas operações de manutenção da aplicação cliente registrada, seguindo as especificações descritas na RFC7592 .

#### 9.3.2. Manutenção de cliente - GET /register - PUT /register - DELETE /register

1. validar a presença e a correspondência do header Bearer Authorization contendo o valor do atributo registration_access_token retornado durante o registro do cliente correspondente.
2. quando o método chamado for PUT /register, realizar as validações dos subitens 1, 2, 3 e 5 do item Registro de cliente - POST /register .
3. quando o método chamado for GET /register, realizar as validações dos subitens 1 e 5 do item Registro de cliente - POST /register .
4. quando o método chamado for DELETE /register, realizar a validação do subitem 1 do item Registro de cliente - POST /register .

### 9.4. Validação de certificados de assinatura

- O diretório realiza a validação do certificado de assinatura através da função cert rescan, a cada hora.
- As instituições devem assegurar que o processo de validação é realizado.
- Cada instituição deve ter alternativa de contingência em caso de indisponibilidade do serviço de validação realizado pelo diretório.
- Ao identificar que o certificado de assinatura não é válido pois, está com status revogado de acordo com o OCSP/CRL da CA emissora, ou está inativo no cadastro do diretório, o conjunto de chaves públicas é movido para o repositório de chaves inativas (Inactive Keystore).
- É recomendado que o processo de validação inclua: Validação da assinatura da mensagem do Transmissor de Dados, a ser feita pelo Receptor de Dados Validar se a mensagem está assinada conforme o Message Signature Guidelines, incluindo se o iss é igual ao organisation_id do servidor que emitiu a mensagem. Buscar a declaração iss do JWT e gerar URI do JWKS publicado no diretório, para consulta. Certificar se o kid do cabeçalho JWT da mensagem está presente no diretório JWKS. Validar se a chave privada para o kid correspondente é capaz de validar a assinatura da mensagem. Validação da assinatura da mensagem do Receptor de Dados, a ser feita pelo Transmissor de Dados Validar se a mensagem está assinada conforme o Message Signature Guidelines. Obter o org_jwks_uri que foi apresentado no SSA pelo cliente no momento do DCR. Certificar se o kid do cabeçalho JWT da mensagem está presente no diretório JWKS. Validar se a chave privada para o kid correspondente é capaz de validar a assinatura da mensagem.

## 10. Reconhecimento
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro de dados por meio da formação do Grupo de Trabalho OpenID Foundation FAPI, o GT de Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Avisos
Copyright (c) 2023 Estrutura Inicial do Open Finance BrasilA Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
### A.1. Apêndice A. Exemplo de afirmação de declaração de software
wide1800
## Author's Address
OFBIS GT SecurityOpen Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Dynamic Client Registration > Histórico de Especificações - DCR > DCR-BR v1.0.0 - Open Finance Brasil Dynamic Client Registration > [EN] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3

---
id: 240649661
title: [EN] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3
version: 2
modified: 2023-12-15T14:53:40.393Z
url: /spaces/OF/pages/240649661/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3
---

## Foreword
Este documento também está disponível em portuguêsThe Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.Open Finance Brasil Financial-grade API Security Profile 1.0 consists of the following parts:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introduction
The Open Finance Brasil Financial-grade API Dynamic Client Registration Profile is a profile of [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) and [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) that aims to provide specific implementation guidelines for security and interoperability which can be applied to the identification, registration and management of OAuth Clients operating in the Brasil Open Finance ecosystem.Although it is possible to code an OpenID Provider and Relying Party from scratch using this specification, the main audience for this specification are parties who already have a certified implementation of [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) and seek to obtain certification for the Brasil Open Finance programme.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml). These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the method of
- applications registered in the Open Finance Directory of Participants to discover OpenID Providers offering services in the Open Finance Brasil ecosystem;
- applications to use OpenID Connect Registration to onboard their applications with Bank OpenID Providers; and
- applications to use OAuth 2.0 Dynamic Client Registration Management Protocol to manage their applications with OpenID Providers;
This document is applicable to all participants engaging in Open Finance in Brasil.
## 2. Normative references
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger
## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) and ISO29100 apply.
## 4. Symbols and Abbreviated terms

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security

## 5. Introduction
Brasil Open Finance ecosystem leverages a federation trust provider or *directory of participants* as the golden source of information on accredited participants and software that are authorized to partake in the Open Finance Brasil ecosystem.The services by the Directory include
- Software registration and management.
- Software credential registration and management using ICP Certificates.
- Software Statement Assertion (SSA) generation
Participants within the ecosystem must leverage these services to facilitate API driven OAuth client registration using the process outlined in clause 3.1.1 of [RFC7591](https://tools.ietf.org/html/rfc7591) with additional metadata necessary to support OpenID Connect defined in [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).It's important to remember that the client registration payload has most of its attributes as non-mandatory, and that assigned values that conflict with those in the software statement assertion *will be overridden by the values of the software statement assertion issued by the Directory of Participants*. Not all metadata a client wishes to provide may be contained in a software statement, e.g alternative [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). There are some cases where the client metadata are subset of the existing values in the SSA, such as redirect_URIs.
## 6. Open Finance Brasil OpenID Connect Discovery provisions

### 6.1. Authorization server
The Authorization Server shall support [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) as required by [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). This support shall be explicit in Participant Directory configurations, and in the declaration of its attributes in the Discovery file (well-known), respecting the authentication mechanisms certified by the institution through the Open Finance Brazil compliance tests.In addition, the Authorization Server:
1. shall advertise its presence in the Open Finance Brasil ecosystem by being listed on the Directory of Participants;
2. shall advertise all Open Finance Brasil REST API resources protected by the OpenID Provider on the Directory of Participants;
3. shall advertise support for all signing, encryption, authentication mechanisms and standards required to support Open Finance Brasil Financial API ;
4. shall advertise support for OpenID Dynamic Client Registration ;
5. may advertise `mtls_endpoint_aliases` as per clause 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens the `token_endpoint` , `registration_endpoint` and `userinfo_endpoint` ;
6. if supporting OAuth 2.0 Pushed Authorization Requests shall advertise through OIDD `mtls_endpoint_aliases` the `pushed_authorization_request_endpoint` ;
7. if supporting Financial API - Client Initiated Back Channel Authentication shall advertise through OIDD `mtls_endpoint_aliases` the `backchannel_authentication_endpoint` ;

### 6.2. Client
The Client shall support [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) as required by [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html)In addition, the Client
1. shall rely on ecosystem discovery services provided by Directory of Participants only;
2. shall derive necessary Authorisation Server metadata by relying on an Authorization Servers OpenID Connect Discovery services only;
3. where present, shall use endpoints advertised in `mtls_endpoint_aliases` as per clause 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens ;

## 7. Open Finance Brasil OpenID Connect Registration Provisions

### 7.1. Authorization server
The Authorization Server shall support the RFC RFCs Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) and [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)In addition, the Authorization Server
1. shall reject dynamic client registration requests not performed over a connection secured with mutual tls using certificates issued by Brazil ICP (production) or the Directory of Participants (sandbox);
2. shall validate that the request contains software_statement JWT signed using the `PS256` algorithim issued by the Open Finance Brasil directory of participants;
3. shall validate that the `software_statement` was issued (iat) not more than 5 minutes prior to the request being received;
4. shall validate that the attribute `jwks` (key set by value) was not included; but declared as a reference in the `jwks_uri` attribute;
5. shall, when informed, validate that `jwks_uri` matches the `software_jwks_uri` provided in the `software_statement` ;
6. shall require and validate that `redirect_uris` matches or contains a sub set of software_redirect_uris provided in the `software_statement` ;
7. shall require and validate that all client authentication mechanism adhere to the requirements defined in RFC7591 and RFC7592 , validating the `registration_access_token` and, through a secure connection, the certificate chain of ICP-Brasil;
8. removed ;
9. shall validate that the requested scopes are adequate for accredited institutions and their regulatory roles and contained in the `software_statement` . The list of regulatory permissions and the corresponding scopes are described in the following sections;
10. where possible, shall compare client metadata asserted by a client to the metadata provided in the `software_statement` , choosing values in the SSA with precedence;
11. shall accept all x.500 AttributeType name strings defined in the Distinguished Name of the x.509 Certificate Profiles defined in Open Finance Brasil x.509 Certificate Standards ;
12. if supporting `tls_client_auth` client authentication mechanism as defined in RFC8705 shall only accept `tls_client_auth_subject_dn` as an indication of the certificate subject value as defined in clause 2.1.2 RFC8705 ;
13. The value of the field UID of the certificate should match the one sent in the SSA, where the UID field should contain the value of the software_id field of the SSA.
14. The organizationIdentifier field will be found in the subject_DN in ASN.1 format and must be decoded respecting the corresponding encoding string. The value of the organizationIdentifier field of the certificate which must contain the prefix corresponding to the Registration Reference OFBBR- followed by the value of the org_id field of the SSA. You must convert the values ​​of the OID 2.5.4.97 field from ASN.1 format to human-readable text. For certificates issued before August 31, 2022: The value of the OR field of the certificate must contain the value of the org_id field of the SSA.
15. shall, during the TLS handshake process, use the `distinguishedNameMatch` rule to compare the DN values as defined in RFC4517 .
16. shall ensure the integrity of the stock of active consents, even after any systemic changes, so that such changes are transparent to the data receiver institutions (TPP).
17. shall perform a recertification on OIDF FAPI and DCR after any systemic changes.
18. The value of the software_api_webhook_uris attribute contained as an attribute in the JWS in software_statement must be compared with the webhook_uris field. If the values are not exactly the same, the error must be returned, with the HTTP status code set to 400, `error` filled in as `invalid_webhook_uris` and `error_description` filled in with `The content of the webhook_uris field different from what was Registered in the software_statement noted via the JWS software_api_webhook_uris` field.
19. If the webhook_uris field is not declared in the payload, the webhook functionality shall be considered disabled for the specific client.
These provisions apply equally to the processing of [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) and [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html) requests
#### 7.1.1. Applying Server Defaults
Whenever properties of a DCR request are not included nor mandatory in the specification, the Authorisation Server shall apply client defaults in the following manner:
1. shall select and apply the encryption algorithm and cipher choice from the most recommended of the IANA cipher suites that is supported by the Authorisation Server;
2. shall populate defaults from values within the `software_statement` assertion where possible;
3. shall grant the client permission to the complete set of potential scopes based on the softwares regulatory permissions included in the `software_statement` ;

#### 7.1.2. Certificate Distinguished Name Parsing
Clause 3 of [Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names](https://www.rfc-editor.org/rfc/rfc4514) defines the mandatory OIDs whose AttributeType strings (descriptors) must be recognized by implementers. This mandatory list does not include several of the OIDs defined in [Open Finance Brasil x.509 Certificate](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0)[Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) nor is there a defined mechanism for Authorisation Servers to publish information regarding the format that they would expect a Dynamic Client Registration request that includes a `tls_client_auth_subject_dn` to be presented in.To address this ambiguity, the Authorization Server shall accept only the AttributeTypes (descriptors) defined in the last paragraph of clause 3 [RFC4514](https://www.rfc-editor.org/rfc/rfc4514) in string format, it shall also accept in OID format, with their values in ASN.1, all the AttributeTypes defined in Distinguished Name [Open Finance Brasil x.509 Certificate Standards](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0) or added by the Certificate Authority.In case of non-compliance with these requirements, the Authorization Server shall reject the registration.In terms of format, follow below how decoding should be done:
- Obtain in reverse order the certificate attributes.
- Append each RDN (RelativeDistinguishedName) segment with a comma ','.
- Use the RFC strings (CN, L, ST, O, OR, C, Street, DC, UID) with the value of their attributes in human-readable format.
- Use the OIDs of the attributes defined in this specification for use in the OFB (businessCategory = OID 2.5.4.15, jurisdictionCountryName = OID 1.3.6.1.4.1.311.60.2.1.3, serialNumber = OID 2.5.4.5, organizationIdentifier = OID 2.5.4.97) with values in ASN.1 format, following the RFC4514, being that: Attribute names shall be defined according to dot-decimal notation, without adding the prefix "OID", ie. "2.5.4.15", followed by ('=#') plus the hexadecimal value of the attribute, here follows a complete example: 2.5.4.15=#0C1450726976617465204F7267616E697A6174696F6E There are no restrictions for encoding and formatting attribute values. The hexadecimal value presented on the utilized attribute must be respected (PrintableString, UTF8String, etc). This item complies with opcionality of the format stabilished by the AC face ICP normatives and items 2.3, 2.4 e 5.2 of the RFC4514. -To comply with DCR standard, convert ASN.1 values from OID 2.5.4.97 organizationIdentifier to human readable text, use features of your API gateway or a standard library of type ASN.1 or if necessary still develop manually. To do so, retrieve the full value of the OID 2.5.4.97 contained in the subject_DN. Remove dot-decimal notation (2.5.4.97). Remove the ('=#') signs. Convert the hex value to text. Apply a filter using regular expression to retrieve the org_id after ('OFBBR-'), for example: 2.5.4.97=#132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033. Remove dot-decimal notation and signs ('=#'): 2.5.4.97=#. Convert the hexadecimal value 132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033 to text: **OFBBR-67c57882-043b-031ec Apply the regular expression and retrieve the org_id that is contained after 'OFBBR-':67c57882-043b-11ec-9a03-0242ac130003.
Below are examples of required attributes for CAs active until August 31, 2022:
| ubject_dn | Issuer |
| --- | --- |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,2.5.4.5=#130e3133333533323336303030313839, CN=mycn.bank.gov.br ,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=Open Banking SANDBOX Issuing CA - G1,OU=Open Banking,O=Open Banking Brasil,C=BR |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C0F427573696E65737320456E74697479, CN=mycn.bank.gov.br ,2.5.4.5=#130e3133333533323336303030313839,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=Autoridade Certificadora do SERPRO SSLv1,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| 1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,UID=67c57882-043b-11ec-9a03-0242ac130003, CN=openbanking.mybank.com.br ,2.5.4.5=#130e3133333533323336303030313839,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,L=Goiania,ST=GO,O=MyBank SA,C=BR | issuer=CN=AC SOLUTI SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| CN=mycn.bank.com.br ,UID=67c57882-043b-11ec-9a03-0242ac130003,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,L=Sao Paulo,ST=SP,O=MyBank SA,C=BR,2.5.4.5=#130e3133333533323336303030313839,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C0F427573696E65737320456E74697479 | issuer=CN=AC SERASA SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
Below are examples of required attributes for CAs active after August 31, 2022:
| subject_dn | Issuer |
| --- | --- |
| UID=67c57882-043b-11ec-9a03-0242ac130003,2.5.4.97=#0C2A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,2.5.4.5=#130e3133333533323336303030313839, CN=mycn.bank.gov.br ,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=AC SERASA SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e, CN=mycn.bank.gov.br ,2.5.4.5=#130e3133333533323336303030313839,2.5.4.97=#132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | |

### 7.2. Regulatory Roles for OpenID and OAuth 2.0 Mappings
To participate in the Open Finance ecosystem, accredited institutions must register themselves in the directory of participants according to their regulatory roles. Those roles reflect the institutions authorization from the Central Bank and, consequently, the APIs they are allowed to use.The following table describes the regulatory roles for Open Finance and the related OAuth 2.0 scopes mapping. If the scopes are omitted during the DCR process, the authorization server shall grant the complete set of potential scopes based on the registering bank's regulatory roles, as described in the Server Defaults section.
| Regulatory Role | Description | Allowed Scopes | Target Phase |
| --- | --- | --- | --- |
| DADOS | Instituição transmissora ou receptora de dados (AISP) | openid accounts credit-cards-accounts consents customers invoice-financings financings loans unarranged-accounts-overdraft resources credit-fixed-incomes exchanges | Phase 2 and Phase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid payments | Phase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Phase 3 |
| CCORR | Correspondente de crédito | openid | Phase 3* |
It is requiread that the active roles in the application's *software_statement* are validated. The field _software_statement_roles shall be used for validation and currently listed roles shall be active.
### 7.3. Client Registration
Section 4.2.11 of RFC 4517 (caseIgnoreMatch) must be respected. Upon registering using the *tls_client_auth* authentication method, the client shall forward the *tls_client_auth_subject_dn* field with the AttibuteTypes(Descriptors) using the defined format under item [Certificate Distinguished Name Parsing](#page-82051199). Non adherence to this format shall cause rejection of the registration.
## 8. Software Statement Assertion
A Software Statement Assertion (*software_statement*) is a JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) that asserts the metadata values of the client software as a whole. On the Open Finance Brasil structure, this *software_statement* is signed by the Participants Directory and it's signature MUST be validated by the Authorization Servers using the public keys available on the following session.
### 8.1. Attributes of the Software Statement Assertion (Claims)
The following example contains all attributes currently included in a *software_statement*:
| {
  "software_mode": "Live",
  "software_redirect_uris": [
    "https://www.raidiam.com/accounting/cb"
  ],
  "software_api_webhook_uris": ["https://www.myitp.com/mykong3"],
  "software_statement_roles": [
    {
      "role": "DADOS",
      "authorisation_domain": "Open Banking",
      "status": "Active"
    },
    {
      "role": "PAGTO",
      "authorisation_domain": "Open Banking",
      "status": "Active"
    }
  ],
  "software_client_name": "Raidiam Accounting",
  "org_status": "Active",
  "software_client_id": "Cki1EbvjwyhPB12NGLlz2",
  "iss": "Open Banking Open Banking Brasil prod SSA issuer",
  "software_tos_uri": "https://www.raidiam.com/accounting/tos.html",
  "software_client_description": "Raidiam Accounting leverage cutting edge open banking access to bring you real time up to date views of your finances",
  "software_jwks_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/application.jwks",
  "software_policy_uri": "https://www.raidiam.com/accounting/policy.html",
  "software_id": "25556d5a-b9dd-4e27-aa1a-cce732fe74de",
  "software_client_uri": "https://www.raidiam.com/accounting.html",
  "software_jwks_inactive_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/inactive/application.jwks",
  "software_jwks_transport_inactive_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/inactive/transport.jwks",
  "software_jwks_transport_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/transport.jwks",
  "software_logo_uri": "https://www.raidiam.com/accounting/logo.png",
  "org_id": "b961c4eb-509d-4edf-afeb-35642b38185d",
  "org_number": "112233445566",
  "software_environment": "production",
  "software_version": "1.1",
  "software_roles": [
    "DADOS",
    "PAGTO"
  ],
  "org_name": "Open Banking Brasil",
  "iat": 1620060821,
  "organisation_competent_authority_claims": [
    {
      "authorisation_domain": "Open Banking",
      "authorisations": [],
      "registration_id": "13353236-OBB-CONTA",
      "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",
      "authority_name": "Banco Central",
      "authorisation_role": "CONTA",
      "authority_code": "BCB",
      "status": "Active"
    },
    {
      "authorisation_domain": "Open Banking",
      "authorisations": [],
      "registration_id": "13353236-OBB-DADOS",
      "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",
      "authority_name": "Banco Central",
      "authorisation_role": "DADOS",
      "authority_code": "BCB",
      "status": "Active"
    },
    {
      "authorisation_domain": "Open Banking",
      "authorisations": [],
      "registration_id": "13353236-OBB-PAGTO",
      "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",
      "authority_name": "Banco Central",
      "authorisation_role": "PAGTO",
      "authority_code": "BCB",
      "status": "Active"
    }
  ]
} |

## 9. Processing of the Dynamic Client Registration claim
The steps of the subject_DN extraction process are described in section [Certificate Distinguished Name Parsing](#page-82051199)The following is an example of Javascript code for extracting the subject_DN and the respective certificate teste.pem used in this example.
| const {X509Certificate} = require('crypto')
const fs = require('fs')
 
const x509 = new X509Certificate(fs.readFileSync('teste.pem'))
const sub = x509.subject
var array = sub.split(/\r?\n|\r|\n/g)
 
function hexa(x){
        var res = ''
        for (var i=0; i < x.length ; i++) { res += x.charCodeAt(i).toString(16) }
        return res
}
 
function retornaMatch(palavra, filtro){
        let match = palavra.match(filtro)
        if(match){ return match[0] }
}
 
var array1 = /organizationIdentifier=[o|O][f|F][b|B]{2}[r|R][-].*[,]/
var novaArray1 = retornaMatch(String(array),array1)
novaArray1 = String(novaArray1).split('=')
novaArray1[1] = novaArray1[1].replace(/,(\s+)?$/, '')
 
var array2 = /jurisdictionC=[a-z|A-Z]{2},/
var novaArray2 = retornaMatch(String(array),array2)
novaArray2 = String(novaArray2).split('=')
novaArray2[1] = novaArray2[1].replace(/,(\s+)?$/, '')
 
var array3 = /businessCategory=\w+\s\w+,/
var novaArray3 = retornaMatch(String(array),array3)
novaArray3 = String(novaArray3).split('=')
novaArray3[1] = novaArray3[1].replace(/,(\s+)?$/, '')
 
var array4 = /serialNumber=[0-9]{14},/
var novaArray4 = retornaMatch(String(array),array4)
novaArray4 = String(novaArray4).split('=')
novaArray4[1] = novaArray4[1].replace(/,(\s+)?$/, '')
 
function parseX509(array, encode){
        var tam = array.length-1
        var novaArray = []
 
        novaArray[0] = array[tam]
        novaArray[1] = '2.5.4.97=' +encode +'2A' + hexa(novaArray1[1])
        novaArray[2] = '1.3.6.1.4.1.311.60.2.1.3=' +encode +'02' + hexa(novaArray2[1])
        novaArray[3] = '2.5.4.15=' +encode +'14' + hexa(novaArray3[1])
        novaArray[4] = '2.5.4.5=' +encode +'0E' + hexa(novaArray4[1])
        novaArray[5] = array[tam-5]
        novaArray[6] = array[tam-6]
        novaArray[7] = array[tam-7]
        novaArray[8] = array[tam-8]
        novaArray[9] = array[tam-9]
 
        var res = 'subject='
        for(i=0; i < novaArray.length ; i++){
                res += novaArray[i]
                res += ','
        }
        res = res.replace(/,(\s+)?$/, '')
 
        return res
}
 
console.log('Suject DN em Printable String: ', parseX509(array, '#13'))
console.log('Suject DN em UTF-8: ', parseX509(array, '#0C')) |

| ----BEGIN CERTIFICATE-----
MIIHSzCCBjOgAwIBAgIUKga83ZMp8P0fd24M2oQUvq1ViPcwDQYJKoZIhvcNAQEL
BQAwcTELMAkGA1UEBhMCQlIxHDAaBgNVBAoTE09wZW4gQmFua2luZyBCcmFzaWwx
FTATBgNVBAsTDE9wZW4gQmFua2luZzEtMCsGA1UEAxMkT3BlbiBCYW5raW5nIFNB
TkRCT1ggSXNzdWluZyBDQSAtIEcxMB4XDTIyMDgyOTE3NDYwMFoXDTIzMDkyODE3
NDYwMFowggFDMQswCQYDVQQGEwJCUjELMAkGA1UECBMCU1AxDzANBgNVBAcTBkxP
TkRPTjEcMBoGA1UEChMTT3BlbiBCYW5raW5nIEJyYXNpbDFDMEEGA1UEAxM6aHR0
cHM6Ly93ZWIuY29uZm9ybWFuY2UuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2ls
Lm9yZy5icjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxGjAYBgNVBA8TEUdvdmVy
bm1lbnQgRW50aXR5MRMwEQYLKwYBBAGCNzwCAQMTAlVLMTMwMQYDVQRhEypPRkJC
Ui03NGU5MjlkOS0zM2I2LTRkODUtOGJhNy1jMTQ2Yzg2N2E4MTcxNDAyBgoJkiaJ
k/IsZAEBEyQxMDEyMDM0MC0zMzE4LTRiYWYtOTllMi0wYjU2NzI5YzRhYjIwggEi
MA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC7BjqM17OFx1eN5bdkZIz2cWq5
/eWuQONogpz2e38AyTsA8xxtTmYABTAHnS6QWBrGqK7XDxKks6srHzbNkr7UVR5+
fg5EfF/SqqWeatFstw3rr5qsN3XnHJUCFsBD6R6IetmrnGlWSIAoJFfqKtYx594U
w0dnE5egBfas087RqSM2V5H9uRcjSfB40MqANERDAZEeftGkNYyzj9Csa5g+WZLH
GqdtW28y7d2tOK4px0e99dAuNRjofCLpRoVH8Ez8ayy7+iJoo4CNRwoGGCayRatK
hrsp6CQ1/0X2sn3Rc02QiiCRhEY3AUYSgiUm64YcAbsO913YtC92lSMUe9gDAgMB
AAGjggMFMIIDATAMBgNVHRMBAf8EAjAAMB0GA1UdDgQWBBQ7XBioIXwyC2PYczsD
uwtKXNck1jAfBgNVHSMEGDAWgBSGf1itF/WCtk60BbP7sM4RQ99MvjBMBggrBgEF
BQcBAQRAMD4wPAYIKwYBBQUHMAGGMGh0dHA6Ly9vY3NwLnNhbmRib3gucGtpLm9w
ZW5iYW5raW5nYnJhc2lsLm9yZy5icjBLBgNVHR8ERDBCMECgPqA8hjpodHRwOi8v
Y3JsLnNhbmRib3gucGtpLm9wZW5iYW5raW5nYnJhc2lsLm9yZy5ici9pc3N1ZXIu
Y3JsMEUGA1UdEQQ+MDyCOmh0dHBzOi8vd2ViLmNvbmZvcm1hbmNlLmRpcmVjdG9y
eS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnIwDgYDVR0PAQH/BAQDAgWgMBMGA1Ud
JQQMMAoGCCsGAQUFBwMCMIIBqAYDVR0gBIIBnzCCAZswggGXBgorBgEEAYO6L2QB
MIIBhzCCATYGCCsGAQUFBwICMIIBKAyCASRUaGlzIENlcnRpZmljYXRlIGlzIHNv
bGVseSBmb3IgdXNlIHdpdGggUmFpZGlhbSBTZXJ2aWNlcyBMaW1pdGVkIGFuZCBv
dGhlciBwYXJ0aWNpcGF0aW5nIG9yZ2FuaXNhdGlvbnMgdXNpbmcgUmFpZGlhbSBT
ZXJ2aWNlcyBMaW1pdGVkcyBUcnVzdCBGcmFtZXdvcmsgU2VydmljZXMuIEl0cyBy
ZWNlaXB0LCBwb3NzZXNzaW9uIG9yIHVzZSBjb25zdGl0dXRlcyBhY2NlcHRhbmNl
IG9mIHRoZSBSYWlkaWFtIFNlcnZpY2VzIEx0ZCBDZXJ0aWNpY2F0ZSBQb2xpY3kg
YW5kIHJlbGF0ZWQgZG9jdW1lbnRzIHRoZXJlaW4uMEsGCCsGAQUFBwIBFj9odHRw
Oi8vcmVwb3NpdG9yeS5zYW5kYm94LnBraS5vcGVuYmFua2luZ2JyYXNpbC5vcmcu
YnIvcG9saWNpZXMwDQYJKoZIhvcNAQELBQADggEBACjaIPM71+6aarcCzUUscTuu
N1ZHazWsGBAsVyPPLgC/cxX1IqAA8W9pLaxRBO4F/CVsqJf2ArS0HMB6aZxVxSty
Ka//oAI/qd6Z+8vx10iT2u359yTXBA7AoIQGAeoC0A2UyKG32V2OtCOKdSQVtu2F
MOaDZhdjxrJACAt8/nTXOZubqFk8laFVo9dmdXxdFd0vejCpvcVQItkjmTsjihMp
xpVPAP52I/ZW3tct2cMJfaw+NulaYgVKhcAu/HGtT0KKbPWq8E7IgtuQrqaLe9n6
Jz3aHfCWJ7IYgBbIRyMhd5oi5Dp8txLxrpTgJ2V9+8wyvzijWbUBHMJnXuiXojM=
-----END CERTIFICATE----- |

### 9.1. Sending a Registration Claim with a Software Statement
This example includes several optional fields, some of those may not be applicable to some implememntations. For a complete guide to attributes and its mandate, consult the DCR Swagger [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). Line breaks inside values serve presentation purposes only.
| POST /reg HTTP/1.1
Host: auth.raidiam.com
Content-Type: application/json
{
  "application_type": "web",
  "grant_types": [
    "client_credentials",
    "authorization_code",
    "refresh_token",
    "implicit"
  ],
  "id_token_signed_response_alg": "PS256",
  "require_auth_time": false,
  "response_types": [
    "code id_token",
    "id_token"
  ],
  "software_statement": "eyJraWQiOiJzaWduZXIiLCJ0eXAiOiJKV1QiLCJhbGciOiJQUzI1NiJ9.eyJzb2Z0d2FyZV9tb2RlIjoiTGl2ZSIsInNvZnR3YXJlX3JlZGlyZWN0X3VyaXMiOlsiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvY2IiXSwic29mdHdhcmVfc3RhdGVtZW50X3JvbGVzIjpbeyJyb2xlIjoiREFET1MiLCJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsInN0YXR1cyI6IkFjdGl2ZSJ9LHsicm9sZSI6IlBBR1RPIiwiYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJzdGF0dXMiOiJBY3RpdmUifV0sInNvZnR3YXJlX2NsaWVudF9uYW1lIjoiUmFpZGlhbSBBY2NvdW50aW5nIiwib3JnX3N0YXR1cyI6IkFjdGl2ZSIsInNvZnR3YXJlX2NsaWVudF9pZCI6IkNraTFFYnZqd3loUEIxMk5HTGx6MiIsImlzcyI6Ik9wZW4gQmFua2luZyBPcGVuIEJhbmtpbmcgQnJhc2lsIHByb2QgU1NBIGlzc3VlciIsInNvZnR3YXJlX3Rvc191cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nXC90b3MuaHRtbCIsInNvZnR3YXJlX2NsaWVudF9kZXNjcmlwdGlvbiI6IlJhaWRpYW0gQWNjb3VudGluZyBsZXZlcmFnZSBjdXR0aW5nIGVkZ2Ugb3BlbiBiYW5raW5nIGFjY2VzcyB0byBicmluZyB5b3UgcmVhbCB0aW1lIHVwIHRvIGRhdGUgdmlld3Mgb2YgeW91ciBmaW5hbmNlcyIsInNvZnR3YXJlX2p3a3NfZW5kcG9pbnQiOiJodHRwczpcL1wva2V5c3RvcmUuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5iclwvYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkXC8yNTU1NmQ1YS1iOWRkLTRlMjctYWExYS1jY2U3MzJmZTc0ZGVcL2FwcGxpY2F0aW9uLmp3a3MiLCJzb2Z0d2FyZV9wb2xpY3lfdXJpIjoiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvcG9saWN5Lmh0bWwiLCJzb2Z0d2FyZV9pZCI6IjI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZSIsInNvZnR3YXJlX2NsaWVudF91cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nLmh0bWwiLCJzb2Z0d2FyZV9qd2tzX2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvYXBwbGljYXRpb24uandrcyIsInNvZnR3YXJlX2p3a3NfdHJhbnNwb3J0X2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9qd2tzX3RyYW5zcG9ydF9lbmRwb2ludCI6Imh0dHBzOlwvXC9rZXlzdG9yZS5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyXC9iOTYxYzRlYi01MDlkLTRlZGYtYWZlYi0zNTY0MmIzODE4NWRcLzI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9sb2dvX3VyaSI6Imh0dHBzOlwvXC93d3cucmFpZGlhbS5jb21cL2FjY291bnRpbmdcL2xvZ28ucG5nIiwib3JnX2lkIjoiYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkIiwic29mdHdhcmVfZW52aXJvbm1lbnQiOiJwcm9kdWN0aW9uIiwic29mdHdhcmVfdmVyc2lvbiI6MS4xMCwic29mdHdhcmVfcm9sZXMiOlsiREFET1MiLCJQQUdUTyJdLCJvcmdfbmFtZSI6Ik9wZW4gQmFua2luZyBCcmFzaWwiLCJpYXQiOjE2MTgzMzYyNjIsIm9yZ2FuaXNhdGlvbl9jb21wZXRlbnRfYXV0aG9yaXR5X2NsYWltcyI6W3siYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJhdXRob3Jpc2F0aW9ucyI6W10sInJlZ2lzdHJhdGlvbl9pZCI6IjEzMzUzMjM2LU9CQi1DT05UQSIsImF1dGhvcml0eV9pZCI6IjY4N2ExYzk0LWIzNjAtNGUwNC05NTg5LTBmYTVjYjE2NDUxYiIsImF1dGhvcmlzYXRpb25fcm9sZSI6IkNPTlRBIiwiYXV0aG9yaXR5X2NvZGUiOiJCQ0IiLCJzdGF0dXMiOiJBY3RpdmUifSx7ImF1dGhvcmlzYXRpb25fZG9tYWluIjoiT3BlbiBCYW5raW5nIiwiYXV0aG9yaXNhdGlvbnMiOltdLCJyZWdpc3RyYXRpb25faWQiOiIxMzM1MzIzNi1PQkItREFET1MiLCJhdXRob3JpdHlfaWQiOiI2ODdhMWM5NC1iMzYwLTRlMDQtOTU4OS0wZmE1Y2IxNjQ1MWIiLCJhdXRob3Jpc2F0aW9uX3JvbGUiOiJEQURPUyIsImF1dGhvcml0eV9jb2RlIjoiQkNCIiwic3RhdHVzIjoiQWN0aXZlIn0seyJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsImF1dGhvcmlzYXRpb25zIjpbXSwicmVnaXN0cmF0aW9uX2lkIjoiMTMzNTMyMzYtT0JCLVBBR1RPIiwiYXV0aG9yaXR5X2lkIjoiNjg3YTFjOTQtYjM2MC00ZTA0LTk1ODktMGZhNWNiMTY0NTFiIiwiYXV0aG9yaXNhdGlvbl9yb2xlIjoiUEFHVE8iLCJhdXRob3JpdHlfY29kZSI6IkJDQiIsInN0YXR1cyI6IkFjdGl2ZSJ9XX0.W6hUAYhjT6I61rxEIVMKYKre93LTbRdzKnk9dJvUdzVgAz5B9KxZNutf27oO3k0hrjYVWBdWq23o_e4Y_AaKdpS9-rtU84JiHtmqV0wcFYIM8nqcUVWqQ-Ux6Nq9L2G-s2YNd3PcJ1e3yGg9h8553Gr7iJusKEgApzXUpkM2rBELQuumktUE_JBiuIkXmWxoRnO1cW-Osbk3MT3bxG43SPcxii07Q5S8qXI6PjCPA3fYlnaUAygwZM3O0oa7jqmSr7d9UsHuDMJfYhIKdq2wyQQKORCN-D2UopmMX-lHMvAVkkrAO08T0-7odjr4PJk-PrwuoCxeAfa7440ZDOrlmQ",
  "subject_type": "public",
  "token_endpoint_auth_method": "private_key_jwt",
  "request_object_signing_alg": "PS256",
  "require_signed_request_object": true,
  "require_pushed_authorization_requests": false,
  "tls_client_certificate_bound_access_tokens": true,
  "client_id": "aCnBHjZBvD6ku3KVBaslL",
  "client_name": "Raidiam Accounting",
  "client_uri": "https://www.raidiam.com/accounting.html",
  "request_object_encryption_alg": "RSA-OAEP",
  "request_object_encryption_enc": "A256GCM",
  "jwks_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/application.jwks",
  "redirect_uris": [
    "https://www.raidiam.com/accounting/cb"
  ],
  "webhook_uris": [
    "https://www.myitp.com/mykong3"
  ]
} |

### 9.2. Open Finance Brasil SSA Key Store and Issuer Details
The following links point to public keys of the Participant Directory and must be used to verify the signature validity of the *software_statements* presented during the client registration process.**Production**[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)Open Finance Open Finance Brasil production SSA issuer**Sandbox**[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)Open Finance Open Finance Brasil sandbox SSA issuer
### 9.3. About authentication and authorization mechanisms for DCR and DCM services
As they are auxiliary services to the main flow of Open Finance Brasil, the dynamic registration and maintenance services for clients do not use the same access control mechanisms. For example, it is not possible to require an OAuth 2.0 *access_token* from a client application that isn't registered yet with the transmitting institution.To extend [RFC7591](https://tools.ietf.org/html/rfc7591) and [RFC7592](https://tools.ietf.org/html/rfc7592), which recommend minimum mechanisms for authentication of their services, institutions that support the registration flows and dynamic maintenance of clients must implement the following controls:
#### 9.3.1. Client registration - POST /register

1. validate that the certificate presented by the client application is subordinate to the ICP-Brasil chains defined in the Open Finance Brasil Certificates Standard;
2. As long as there is a need for the coexistence period (mentioned in section 7.1), validation must be implemented for both cases: certificates that have the value org_id in the organizationUnitName field ( OU ) and certificates that have the value org_id in the organizationIdentifier field.
3. ensure that the signature of the `software_statement` _ presented by the client application during registration has been made by the Directory of Participants using the public keys described in the previous section;
4. ensure that the `software_statement` presented by the client application during registration corresponds to the same institution as the client certificate presented, validating it through the attributes that bring `organization_id` in the X.509 certificate.
5. Multiple DCR registrations for the same Software Statement should not be allowed, in a way that in case of a new registration attempt for an already registered Software Statement, the Error Response procedure defined on item 3.2.2 of the RFC7591 must be enforced.
6. issue, on the registry response, a `registration_access_token` to be used as an authentication token on maintaining operations of the registered client application, following specifications described in RFC7592 .

#### 9.3.2. Client Maintenance - GET /register - PUT /register - DELETE /register

1. Removed
2. Validate the presence and matching of the Bearer header `Authorization` containing the value of the `registration_access_token` attribute returned during registration of the corresponding client.
3. When the invoked method is PUT / register, carry out the validations of sub-items 1, 3, 4, and 6 of item Client registration - POST /register .
4. When the invoked method is GET /register, carry out the validations of sub-items 1 and 6 of item Client registration - POST /register .
5. When the invoked method is DELETE /register, carry out the validation of sub-item 1 of item Client registration - POST /register .
Note: [RFC7592](https://tools.ietf.org/html/rfc7592) provides the possibility of rotating the `registration_access_token` issued by the Authorization Server with each use, making it a single-use token. When registering their client applications, institutions should consider this aspect to receive and update the `registration_access_token` for the new value received in client maintenance (DCM) operations.
### 9.4. Signature certificates validation

- The directory uses cert rescan function hourly to validation process.
- The organization shall ensure that the validation process was completed.
- Each organization must have a continuity plan in case of unavailability validation service.
- If the signature certificate is not valid because it has a revoked status according to the CA’s OCSP/CRL issuer, or is inactive in the directory register, the set of public keys is moved to the inactive key storage.
- The validation process should include: Resource server (Data Transmitter) message signature validation, to be done by the Client (Data Receiver) Validate that the message was signed in line with what’s defined on the Message Signature Guidelines, including that the iss is equal to the organisation_id of the server that issued the message. Fetch the “iss” claim from the JWT and build the directory application JWKS uri for that specific server. Make sure that the kid present on the message JWT header is present on the directory JWKS. Validate that the private key for the corresponding kid is able to validate the message signature. Client (Data Receiver) message signature validation, to be done by the Resource Server Validate how the message was signed in line with what’s defined on the Message Signature Guidelines. Obtain the org_jwks_uri which was presented on the SSA by the client on the moment of the registration (DCR) Make sure that the kid present on the message JWT header is present on the directory JWKS. Validate that the private key for the corresponding kid is able to validate the message signature.

## 10. Acknowledgement
With thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Caio Zanolla (Belvo)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
### A.1. Appendix A. Example Software Statement Assertion

| eyJraWQiOiJzaWduZXIiLCJ0eXAiOiJKV1QiLCJhbGciOiJQUzI1NiJ9.eyJzb2Z0d2FyZV9tb2RlIjoiTGl2ZSIsInNvZnR3YXJlX3JlZGlyZWN0X3VyaXMiOlsiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvY2IiXSwic29mdHdhcmVfc3RhdGVtZW50X3JvbGVzIjpbeyJyb2xlIjoiREFET1MiLCJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsInN0YXR1cyI6IkFjdGl2ZSJ9LHsicm9sZSI6IlBBR1RPIiwiYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJzdGF0dXMiOiJBY3RpdmUifV0sInNvZnR3YXJlX2NsaWVudF9uYW1lIjoiUmFpZGlhbSBBY2NvdW50aW5nIiwib3JnX3N0YXR1cyI6IkFjdGl2ZSIsInNvZnR3YXJlX2NsaWVudF9pZCI6IkNraTFFYnZqd3loUEIxMk5HTGx6MiIsImlzcyI6Ik9wZW4gQmFua2luZyBPcGVuIEJhbmtpbmcgQnJhc2lsIHByb2QgU1NBIGlzc3VlciIsInNvZnR3YXJlX3Rvc191cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nXC90b3MuaHRtbCIsInNvZnR3YXJlX2NsaWVudF9kZXNjcmlwdGlvbiI6IlJhaWRpYW0gQWNjb3VudGluZyBsZXZlcmFnZSBjdXR0aW5nIGVkZ2Ugb3BlbiBiYW5raW5nIGFjY2VzcyB0byBicmluZyB5b3UgcmVhbCB0aW1lIHVwIHRvIGRhdGUgdmlld3Mgb2YgeW91ciBmaW5hbmNlcyIsInNvZnR3YXJlX2p3a3NfZW5kcG9pbnQiOiJodHRwczpcL1wva2V5c3RvcmUuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5iclwvYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkXC8yNTU1NmQ1YS1iOWRkLTRlMjctYWExYS1jY2U3MzJmZTc0ZGVcL2FwcGxpY2F0aW9uLmp3a3MiLCJzb2Z0d2FyZV9wb2xpY3lfdXJpIjoiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvcG9saWN5Lmh0bWwiLCJzb2Z0d2FyZV9pZCI6IjI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZSIsInNvZnR3YXJlX2NsaWVudF91cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nLmh0bWwiLCJzb2Z0d2FyZV9qd2tzX2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvYXBwbGljYXRpb24uandrcyIsInNvZnR3YXJlX2p3a3NfdHJhbnNwb3J0X2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9qd2tzX3RyYW5zcG9ydF9lbmRwb2ludCI6Imh0dHBzOlwvXC9rZXlzdG9yZS5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyXC9iOTYxYzRlYi01MDlkLTRlZGYtYWZlYi0zNTY0MmIzODE4NWRcLzI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9sb2dvX3VyaSI6Imh0dHBzOlwvXC93d3cucmFpZGlhbS5jb21cL2FjY291bnRpbmdcL2xvZ28ucG5nIiwib3JnX2lkIjoiYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkIiwic29mdHdhcmVfZW52aXJvbm1lbnQiOiJwcm9kdWN0aW9uIiwic29mdHdhcmVfdmVyc2lvbiI6MS4xMCwic29mdHdhcmVfcm9sZXMiOlsiREFET1MiLCJQQUdUTyJdLCJvcmdfbmFtZSI6Ik9wZW4gQmFua2luZyBCcmFzaWwiLCJpYXQiOjE2MTgzMzYyNjIsIm9yZ2FuaXNhdGlvbl9jb21wZXRlbnRfYXV0aG9yaXR5X2NsYWltcyI6W3siYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJhdXRob3Jpc2F0aW9ucyI6W10sInJlZ2lzdHJhdGlvbl9pZCI6IjEzMzUzMjM2LU9CQi1DT05UQSIsImF1dGhvcml0eV9pZCI6IjY4N2ExYzk0LWIzNjAtNGUwNC05NTg5LTBmYTVjYjE2NDUxYiIsImF1dGhvcmlzYXRpb25fcm9sZSI6IkNPTlRBIiwiYXV0aG9yaXR5X2NvZGUiOiJCQ0IiLCJzdGF0dXMiOiJBY3RpdmUifSx7ImF1dGhvcmlzYXRpb25fZG9tYWluIjoiT3BlbiBCYW5raW5nIiwiYXV0aG9yaXNhdGlvbnMiOltdLCJyZWdpc3RyYXRpb25faWQiOiIxMzM1MzIzNi1PQkItREFET1MiLCJhdXRob3JpdHlfaWQiOiI2ODdhMWM5NC1iMzYwLTRlMDQtOTU4OS0wZmE1Y2IxNjQ1MWIiLCJhdXRob3Jpc2F0aW9uX3JvbGUiOiJEQURPUyIsImF1dGhvcml0eV9jb2RlIjoiQkNCIiwic3RhdHVzIjoiQWN0aXZlIn0seyJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsImF1dGhvcmlzYXRpb25zIjpbXSwicmVnaXN0cmF0aW9uX2lkIjoiMTMzNTMyMzYtT0JCLVBBR1RPIiwiYXV0aG9yaXR5X2lkIjoiNjg3YTFjOTQtYjM2MC00ZTA0LTk1ODktMGZhNWNiMTY0NTFiIiwiYXV0aG9yaXNhdGlvbl9yb2xlIjoiUEFHVE8iLCJhdXRob3JpdHlfY29kZSI6IkJDQiIsInN0YXR1cyI6IkFjdGl2ZSJ9XX0.W6hUAYhjT6I61rxEIVMKYKre93LTbRdzKnk9dJvUdzVgAz5B9KxZNutf27oO3k0hrjYVWBdWq23o_e4Y_AaKdpS9-rtU84JiHtmqV0wcFYIM8nqcUVWqQ-Ux6Nq9L2G-s2YNd3PcJ1e3yGg9h8553Gr7iJusKEgApzXUpkM2rBELQuumktUE_JBiuIkXmWxoRnO1cW-Osbk3MT3bxG43SPcxii07Q5S8qXI6PjCPA3fYlnaUAygwZM3O0oa7jqmSr7d9UsHuDMJfYhIKdq2wyQQKORCN-D2UopmMX-lHMvAVkkrAO08T0-7odjr4PJk-PrwuoCxeAfa7440ZDOrlmQ |

## Author's Address
**OFBIS GT Security**Open Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Dynamic Client Registration > Histórico de Especificações - DCR > DCR-BR v1.0.0 - Open Finance Brasil Dynamic Client Registration > [PT] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3

---
id: 240649543
title: [PT] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3
version: 2
modified: 2023-12-15T14:53:35.969Z
url: /spaces/OF/pages/240649543/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3
---

## Prefácio
The normative version in [English](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3)A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. O EIOFB não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
Essas partes devem ser usadas com [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) e [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introdução
O Perfil de Registro de Cliente Dinâmico (DCR - *Dynamic Client Registration*) do Financal-grade API (FAPI) do Open Finance Brasil é um perfil de [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) que visa fornecer diretrizes de implementação específicas para segurança e interoperabilidade que podem ser aplicadas à identificação, registro e gerenciamento de *Clients OAuth* operando no ecossistema Open Finance Brasil.[¶](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#section-note.2-1)Embora seja possível codificar um *OpenID Provider* e *Relying Party* desde o princípio usando esta especificação, o principal público para esta especificação são as partes que já possuem uma implementação certificada do [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) e desejam obter a certificação para o Open Finance Brasil.
## Convenções Notacionais
As palavras-chave "*deve*" (shall), "*não deve*" (shall not), "*deveria*" (should), "*não deveria*" (should not) e "*pode*" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml) observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 1. Escopo
Este documento especifica o método de
- aplicativos cadastrados no Diretorio de Participantes do Open Finance para descobrir OpenID Providers que oferecem serviços no ecossistema Open Finance Brasil;
- aplicativos para usar o OpenID Connect Registration para integrar seus aplicativos com OpenID Providers dos bancos; e
- aplicativos para usar OAuth 2.0 Dynamic Client Registration Management Protocol para gerenciar seus aplicativos com OpenID Providers;
Este documento é aplicável a todos os participantes do Open Finance no Brasil.
## 2. Referências normativas
Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger
## 3. Termos e definições
Para efeitos deste documento, aplicam-se os termos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e ISO29100.
## 4. Símbolos e Termos abreviados

- API - Application Programming Interface (Interface de Programação da Aplicação)
- DCR - Dynamic Client Registration (Registro de Cliente Dinâmico)
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- SS - Software Statement (Declaração de Software)
- SSA - Software Statement Assertion (Afirmação de Declaração de Software)
- TLS - Transport Layer Security

## 5. Introdução
O ecossistema Open Finance Brasil apoia-se em um provedor de confiança ou *diretório de participantes* como a fonte mais valiosa de informações sobre participantes credenciados e softwares que estão autorizados a participar do ecossistema Open Finance Brasil.Os serviços do Diretório incluem:
- Registro e gerenciamento de software
- Registro e gerenciamento de credenciais de software usando certificados ICP
- Geração de Software Statement Assertion (SSA)
Os participantes do ecossistema devem aproveitar esses serviços para facilitar o registro de cliente OAuth orientado por API usando o processo descrito na cláusula 3.1.1 do [RFC7591](https://tools.ietf.org/html/rfc7591) com metadados adicionais necessários para oferecer suporte ao OpenID Connect definido em [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).É importante reforçar que o payload de registro de clientes possui a maior parte de seus atributos não obrigatórios, e que os atributos cujos valores conflitem com os presentes no software statement assertion *serão sobrepostos pelos valores do próprio software statement assertion emitido pelo diretório central*. Nem todos os metadados que um cliente deseja fornecer podem estar contidos em um *software statement*, por exemplo, alternativa [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). Há casos ainda de metadados de cliente que são um subconjunto dos valores existentes no SSA, como por exemplo os redirect_URIs.
## 6. Provisionamentos do OpenID Connect Discovery do Open Finance Brasil

### 6.1. Servidor de Autorização
O servidor de autorização deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). Este suporte deve estar explicito tanto na forma como o Servidor de Autorização está registrado no Diretório de Participantes quanto na declaração dos seus atributos no arquivo de Discovery (well-known), respeitando os mecanismos de autenticação certificados pela institição através dos testes de conformidade do Open Finance Brasil.Adicionalmente, o Servidor de Autorização:
1. deve anunciar sua presença no ecossistema Open Finance Brasil, sendo listada no Diretório de Participantes;
2. deve anunciar todos os recursos API REST do Open Finance Brasil protegidos pelo Provedor OpenID no Diretório de Participantes;
3. deve anunciar suporte para todos os mecanismos de assinatura, criptografia, autenticação e padrões necessários para suportar o Open Finance Brasil Financial API ;
4. deve anunciar suporte para OpenID Dynamic Client Registration ;
5. pode anunciar `mtls_endpoint_aliases` de acordo com a cláusula 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens o `token_endpoint` , `registration_endpoint` e `userinfo_endpoint` ;
6. se suportar OAuth 2.0 Pushed Authorisation Requests , deve anunciar por meio de OIDD `mtls_endpoint_aliases` o `push_authorization_request_endpoint` ;
7. se suportar Financial API - Client Initiated Back Channel Authentication , deve anunciar através de OIDD `mtls_endpoint_aliases` o `backchannel_authentication_endpoint` ;

### 6.2. Cliente
O cliente deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html).Além disso, o Cliente
1. deve contar com serviços de descoberta do ecossistemas fornecidos apenas pelo Diretório de Participantes;
2. deve derivar os metadados necessários do Authorization Server somente por meio do serviço OpenID Connect Discovery dos Authorization Servers;
3. quando presente, deve usar endpoints anunciados em `mtls_endpoint_aliases` conforme a cláusula 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens ;

## 7. Provisionamento de registro OpenID Connect do Open Finance Brasil

### 7.1. Servidor de Autorização
O servidor de autorização deve suportar as RFCs de Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)Além disso, o servidor de autorização
1. deve rejeitar as solicitações de registro de cliente dinâmico não realizadas em uma conexão protegida com mTLS usando certificados emitidos pelo Brasil ICP (produção) ou o Diretório de Participantes (sandbox);
2. deve validar que a solicitação contém software_statement JWT assinado usando o algoritmo `PS256` emitido pelo Diretório de Participantes do Open Finance Brasil;
3. deve validar que o software_statement foi emitido (iat - issued at ) não mais de 5 minutos antes do pedido ser recebido;
4. deve validar que um atributo `jwks` (definida por valor) não foi incluído, e sim declarado como referência no atributo `jwks_uri` ;
5. deve, quando informado, validar que o `jwks_uri` corresponda ao `software_jwks_uri` fornecido na declaração do software;
6. deve exigir e validar que o `redirect_uris` corresponda ou contenha um subconjunto dos valores de `software_redirect_uris` fornecidos no software_statement ;
7. deve exigir e validar que todos os mecanismos de autenticação de cliente cumpram os requisitos definidos nas RFC7591 e RFC7592 , através da validação do `registration_access_token` e, como conexão segura, da cadeia de certificados confiáveis ICP-Brasil.
8. removido ;
9. deve validar se os escopos solicitados são adequados para as permissões regulatórias autorizadas da instituição e contidas no _software_statement. A relação de permissões regulatórias e os escopos correspondentes está descrita nas seções a seguir.
10. deve, sempre que possível, validar os metadados declarados pelo cliente em relação aos metadados fornecidos no software_statement , adotando os valores presentes no SSA com precedência.
11. deve aceitar todos os nomes x.500 AttributeType definidas no Distinguished Name dos Perfis de Certificado x.509 definidos em Open Finance Brasil x.509 Certificate Standards ;
12. se for compatível com o mecanismo de autenticação do cliente `tls_client_auth` , conforme definido em RFC8705 , somente deve aceitar `tls_client_auth_subject_dn` como uma indicação do valor do atributo subject do certificado, conforme definido na cláusula 2.1.2 RFC8705 ;
13. O valor do campo UID do certificado deve coincidir com o enviado no SSA, onde o campo UID deve conter o valor do campo software_id do SSA.
14. O campo organizationIdentifier será encontrado no subject_DN em formato ASN.1 e deverá ser decodificado respeitando o string enconding correspondente. O valor do campo organizationIdentifier do certificado que deve conter o prefixo correspondente ao Registration Reference OFBBR- seguido do valor do campo org_id do SSA. Deve-se converter os valores do campo OID 2.5.4.97 do formato ASN.1 para texto legível para humanos. Para certificados emitidos até 31 de Agosto de 2022: o valor do campo OU do certificado deve conter o valor do campo org_id do SSA.
15. deve, durante o processo de handshake TLS, usar a regra `distinguishedNameMatch` para comparar os valores DN conforme definido na RFC4517 . ¶
16. deve ser garantido a todos, após os mesmos atos de consentimentos permanentes, para que também sejam alterados para instituições receptoras de dados transparentes (TPP).
17. deve realizar recertificação FAPI e DCR OIDF após eventuais alterações sistêmicas.
18. O valor do atributo software_api_webhook_uris contido como atributo no JWS em software_statement deverá ser comparado com o campo webhook_uris. Caso os valores não sejam exatamente iguais, deve-se retornar o erro, com HTTP status code setado para 400, `error` preenchido como `invalid_webhook_uris` e `error_description` preenchido com `The content of the webhook_uris field differs from what was registered in the software_statement observed through the JWS field's software_api_webhook_uris` .
19. Se o campo webhook_uris não for declarado no payload, a funcionalidade webhook deverá ser considerado como desativado para o client em questão.
Estas disposições aplicam-se igualmente ao processamento de pedidos [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)
#### 7.1.1. Aplicando Server Defaults
Quando as propriedades de uma solicitação DCR não estão incluídas e não são obrigatórias na especificação, o Authorization Server deve aplicar os padrões do cliente da seguinte maneira:
1. deve selecionar e aplicar o algoritmo de criptografia e a escolha da cifra a partir dos conjuntos mais recomendados de cifra da IANA que são suportados pelo Servidor de Autorização;
2. deve preencher defaults a partir de valores da afirmação de software_statement , sempre que possível;
3. deve conceder ao cliente permissão para o conjunto completo de escopos potenciais com base nas permissões regulatórias de softwares incluídas no software_statement ;

#### 7.1.2. Análise do Distinguished Name do Certificado
A cláusula 3 do [Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names](https://www.rfc-editor.org/rfc/rfc4514) define os OIDs obrigatórios cujas as *strings* do AttributeType (descritores) devem ser reconhecidos pelos implementadores. Esta lista obrigatória não inclui vários dos OIDs definidos em [Open Finance Brasil x.509 Certificate Standards](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0), nem existe um mecanismo definido para os Servidores de Autorização publicarem informações sobre o formato que eles esperam de uma Solicitação Dinâmica de Registro do Cliente (*Dynamic Client Registrarion*) que inclui um `tls_client_auth_subject_dn`.Para resolver essa ambiguidade, o Servidor de Autorização deve aceitar exclusivamente os AttributeType (descritores) definidas no último parágrafo da cláusula 3 [RFC4514](https://www.rfc-editor.org/rfc/rfc4514) em formato string,  também deve aceitar em formato OID, com seus valores em ASN.1, todos os AttributeTypes definidos no Distinguished Name [Open Finance Brasil x.509 Certificate Standards](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76710230/EN+Padr+o+de+Certificados+Open+Finance+Brasil+1.0) ou adicionados pela Autoridade Certificadora.Em caso de não atendimento destes requisitos o Servidor de Autorização deverá rejeitar o registro.Segue na tabela abaixo como deve ser feita a decodificação:
- Obtenha na ordem reversa os atributos do certificado
- Concatene cada RDN (RelativeDistinguishedName) com uma virgula (',')
- Use as strings da RFC (CN, L, ST, O, OU, C, Street, DC, UID) com o valor dos seus atributos legível para humanos
- Use os OIDs dos atributos definidos nesta especificação para uso no OFB (businessCategory = OID 2.5.4.15, jurisdictionCountryName = OID 1.3.6.1.4.1.311.60.2.1.3, serialNumber = OID 2.5.4.5, organizationIdentifier = OID 2.5.4.97) com o valor dos seus atributos em formato ASN.1 seguindo a RFC4514, sendo que: Os nomes dos atributos devem ser definidos seguindo a notação ponto-decimal, sem adição de prefixo "OID", ex. "2.5.4.15", seguido dos sinais de ('=#') mais o valor hexadecimal do atributo, exemplo final: 2.5.4.15=#0C1450726976617465204F7267616E697A6174696F6E Não há qualquer restrição para as codificações/formatações utilizadas nos valores dos atributos. Deve ser respeitado o uso em hexadecimal apresentado na codificação utilizada no atributo do certificado (PrintableString, UTF8String, etc). Este item atende à opcionalidade do formato já estabelecido pela AC frente aos normativos ICP e ao itens 2.3, 2.4 e 5.2 da RFC4514. -Para atender ao padrão DCR, converta os valores ASN.1 do OID 2.5.4.97 organizationIdentifier para texto legível para humanos, utilize recursos do seu API gateway ou uma biblioteca padrão do tipo ASN.1 ou se necessário ainda desenvolva manualmente. Para isso recupere o valor completo do OID 2.5.4.97 contido no subject_DN. Remova a notação ponto-decimal (2.5.4.97). Remova os sinais de ('=#'). Converta o valor de hexadecimal para texto. Aplique um filtro usando expressão regular para recuperar o org_id após ('OFBBR-'), por exemplo: 2.5.4.97=#132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033. Remova a notação ponto-decimal e sinais ('=#'): 2.5.4.97=#. Converta o valor hexadecimal 132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033 para texto: **OFBBR-67c57882-043b-11ec-9a03-0242ac130003. Aplique a expressão regular e recupere o org_id que está contido após 'OFBBR-':67c57882-043b-11ec-9a03-0242ac130003.
Seguem abaixo exemplos para os atributos obrigatórios das ACs ativas até 31 de Agosto de 2022:
| Table 1 | |
| subject_dn | Issuer |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,2.5.4.5=#130e3133333533323336303030313839,CN= mycn.bank.gov.br ,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=Open Banking SANDBOX Issuing CA - G1,OU=Open Banking,O=Open Banking Brasil,C=BR |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C0F427573696E65737320456E74697479, CN=mycn.bank.gov.br ,2.5.4.5=#130e3133333533323336303030313839,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | issuer=CN=Autoridade Certificadora do SERPRO SSLv1,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| 1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,UID=67c57882-043b-11ec-9a03-0242ac130003, CN=openbanking.mybank.com.br ,2.5.4.5=#130e3133333533323336303030313839,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,L=Goiania,ST=GO,O=MyBank SA,C=BR | issuer=CN=AC SOLUTI SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| CN=mycn.bank.com.br ,UID=67c57882-043b-11ec-9a03-0242ac130003,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,L=Sao Paulo,ST=SP,O=MyBank SA,C=BR,2.5.4.5=#130e3133333533323336303030313839,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C0F427573696E65737320456E74697479 | issuer=CN=AC SERASA SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
Seguem abaixo exemplos para os atributos obrigatórios das ACs ativas após 31 de Agosto de 2022:
| Table 2 | |
| subject_dn | Issuer |
| UID=67c57882-043b-11ec-9a03-0242ac130003,2.5.4.97=#0C2A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e,2.5.4.5=#130e3133333533323336303030313839,CN= mycn.bank.gov.br ,OU=497e1ffe-b2a2-4a4e-8ef0-70633fd11b59,O=My Public Bank,L= BRASILIA,ST=DF,C=BR | issuer=CN=AC SERASA SSL EV,OU=Autoridade Certificadora Raiz Brasileira v10,O=ICP-Brasil,C=BR |
| UID=67c57882-043b-11ec-9a03-0242ac130003,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#131450726976617465204f7267616e697a6174696f6e, CN=mycn.bank.gov.br ,2.5.4.5=#130e3133333533323336303030313839,2.5.4.97=#132A4F464242522D36376335373838322D303433622D313165632D396130332D303234326163313330303033,O=My Public Bank,L=BRASILIA,ST=DF,C=BR | |

### 7.2. Funções regulatórias para mapeamentos OpenID e OAuth 2.0
Para participar do ecossistema do Open Finance, as instituições credenciadas devem se cadastrar no Diretório de Participantes de acordo com seus papéis regulatórios. Essas funções refletem a autorização do Banco Central para as instituições e, consequentemente, as APIs que podem utilizar.A tabela a seguir descreve as funções regulatórias do Open Finance e o mapeamento de escopos do OAuth 2.0 relacionado. Se os escopos forem omitidos durante o processo de DCR, o Servidor de Autorização deve conceder o conjunto completo de escopos potenciais com base nas funções regulatórias registradas para o banco, conforme descrito na seção Server Defaults.
| Papel Regulador | Descrição | Escopos Permitidos | Fase-alvo |
| --- | --- | --- | --- |
| DADOS | Instituição transmissora / receptora de dados (AISP) | openid accounts credit-cards-accounts consents customers invoice-financings financings loans unarranged-accounts-overdraft resources credit-fixed-incomes exchanges | Fase 2 e Fase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid payments | Fase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Fase 3 |
| CCORR | Correspondente de crédito | openid | Fase 3* |
É necessário validar as roles ativas no *software_statement* da aplicação. Na validação dessa informação deve ser utilizado o campo _software_statement_roles, e deve ser verificado se as roles listadas estão ativas.
### 7.3. Registro do Cliente
Deve-se ser respeitada a seção 4.2.11 da RFC 4517 (caseIgnoreMatch). No processo de registro do cliente, utilizando-se o método de autenticação *tls_client_auth*, o cliente deve encaminhar o campo _tls_client_auth_subject_dn_ com os AttibuteTypes(Descritores) em formato definido no item Análise do Distinguished Name do Certificado. Em caso de não aderencia a este padrão o registro será rejeitado.
## 8. Declaração de Software
Uma declaração de software (*software_statement*) é um JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) que afirma valores de metadados sobre o software cliente como um todo. Na estrutura do Open Finance Brasil, esse *software_statement* é assinado pelo Diretório de Participantes, e sua assinatura DEVE ser validada pelos Servidores de Autorizacao usando as chaves públicas disponíveis na seção a seguir.
### 8.1. Atributos da Declaração de Software (Claims)
O exemplo a seguir contém todos os atributos atualmente incluídos em um *software_statement*:
| {
  "software_mode": "Live",
  "software_redirect_uris": [
    "https://www.raidiam.com/accounting/cb"
  ],
  "software_api_webhook_uris": ["https://www.myitp.com/mykong3"],
  "software_statement_roles": [
    {
      "role": "DADOS",
      "authorisation_domain": "Open Banking",
      "status": "Active"
    },
    {
      "role": "PAGTO",
      "authorisation_domain": "Open Banking",
      "status": "Active"
    }
  ],
  "software_client_name": "Raidiam Accounting",
  "org_status": "Active",
  "software_client_id": "Cki1EbvjwyhPB12NGLlz2",
  "iss": "Open Banking Open Banking Brasil prod SSA issuer",
  "software_tos_uri": "https://www.raidiam.com/accounting/tos.html",
  "software_client_description": "Raidiam Accounting leverage cutting edge open banking access to bring you real time up to date views of your finances",
  "software_jwks_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/application.jwks",
  "software_policy_uri": "https://www.raidiam.com/accounting/policy.html",
  "software_id": "25556d5a-b9dd-4e27-aa1a-cce732fe74de",
  "software_client_uri": "https://www.raidiam.com/accounting.html",
  "software_jwks_inactive_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/inactive/application.jwks",
  "software_jwks_transport_inactive_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/inactive/transport.jwks",
  "software_jwks_transport_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/transport.jwks",
  "software_logo_uri": "https://www.raidiam.com/accounting/logo.png",
  "org_id": "b961c4eb-509d-4edf-afeb-35642b38185d",
  "org_number": "112233445566",
  "software_environment": "production",
  "software_version": "1.1",
  "software_roles": [
    "DADOS",
    "PAGTO"
  ],
  "org_name": "Open Banking Brasil",
  "iat": 1620060821,
  "organisation_competent_authority_claims": [
    {
      "authorisation_domain": "Open Banking",
      "authorisations": [],
      "registration_id": "13353236-OBB-CONTA",
      "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",
      "authority_name": "Banco Central",
      "authorisation_role": "CONTA",
      "authority_code": "BCB",
      "status": "Active"
    },
    {
      "authorisation_domain": "Open Banking",
      "authorisations": [],
      "registration_id": "13353236-OBB-DADOS",
      "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",
      "authority_name": "Banco Central",
      "authorisation_role": "DADOS",
      "authority_code": "BCB",
      "status": "Active"
    },
    {
      "authorisation_domain": "Open Banking",
      "authorisations": [],
      "registration_id": "13353236-OBB-PAGTO",
      "authority_id": "687a1c94-b360-4e04-9589-0fa5cb16451b",
      "authority_name": "Banco Central",
      "authorisation_role": "PAGTO",
      "authority_code": "BCB",
      "status": "Active"
    }
  ]
} |

## 9. Processamento de solicitação de registro de cliente dinâmico
Os passos do processo de extração do subject_DN estão descritos na seção Análise do Distinguished Name do Certificado.O exemplo de código Javascript para extração do subject_DN e o respectivo certificado teste.pem utilizado neste exemplo estão descritos abaixo.
| const {X509Certificate} = require('crypto')
const fs = require('fs')
 
const x509 = new X509Certificate(fs.readFileSync('teste.pem'))
const sub = x509.subject
var array = sub.split(/\r?\n|\r|\n/g)
 
function hexa(x){
        var res = ''
        for (var i=0; i < x.length ; i++) { res += x.charCodeAt(i).toString(16) }
        return res
}
 
function retornaMatch(palavra, filtro){
        let match = palavra.match(filtro)
        if(match){ return match[0] }
}
 
var array1 = /organizationIdentifier=[o|O][f|F][b|B]{2}[r|R][-].*[,]/
var novaArray1 = retornaMatch(String(array),array1)
novaArray1 = String(novaArray1).split('=')
novaArray1[1] = novaArray1[1].replace(/,(\s+)?$/, '')
 
var array2 = /jurisdictionC=[a-z|A-Z]{2},/
var novaArray2 = retornaMatch(String(array),array2)
novaArray2 = String(novaArray2).split('=')
novaArray2[1] = novaArray2[1].replace(/,(\s+)?$/, '')
 
var array3 = /businessCategory=\w+\s\w+,/
var novaArray3 = retornaMatch(String(array),array3)
novaArray3 = String(novaArray3).split('=')
novaArray3[1] = novaArray3[1].replace(/,(\s+)?$/, '')
 
var array4 = /serialNumber=[0-9]{14},/
var novaArray4 = retornaMatch(String(array),array4)
novaArray4 = String(novaArray4).split('=')
novaArray4[1] = novaArray4[1].replace(/,(\s+)?$/, '')
 
function parseX509(array, encode){
        var tam = array.length-1
        var novaArray = []
 
        novaArray[0] = array[tam]
        novaArray[1] = '2.5.4.97=' +encode +'2A' + hexa(novaArray1[1])
        novaArray[2] = '1.3.6.1.4.1.311.60.2.1.3=' +encode +'02' + hexa(novaArray2[1])
        novaArray[3] = '2.5.4.15=' +encode +'14' + hexa(novaArray3[1])
        novaArray[4] = '2.5.4.5=' +encode +'0E' + hexa(novaArray4[1])
        novaArray[5] = array[tam-5]
        novaArray[6] = array[tam-6]
        novaArray[7] = array[tam-7]
        novaArray[8] = array[tam-8]
        novaArray[9] = array[tam-9]
 
        var res = 'subject='
        for(i=0; i < novaArray.length ; i++){
                res += novaArray[i]
                res += ','
        }
        res = res.replace(/,(\s+)?$/, '')
 
        return res
}
 
console.log('Suject DN em Printable String: ', parseX509(array, '#13'))
console.log('Suject DN em UTF-8: ', parseX509(array, '#0C')) |

| ----BEGIN CERTIFICATE-----
MIIHSzCCBjOgAwIBAgIUKga83ZMp8P0fd24M2oQUvq1ViPcwDQYJKoZIhvcNAQEL
BQAwcTELMAkGA1UEBhMCQlIxHDAaBgNVBAoTE09wZW4gQmFua2luZyBCcmFzaWwx
FTATBgNVBAsTDE9wZW4gQmFua2luZzEtMCsGA1UEAxMkT3BlbiBCYW5raW5nIFNB
TkRCT1ggSXNzdWluZyBDQSAtIEcxMB4XDTIyMDgyOTE3NDYwMFoXDTIzMDkyODE3
NDYwMFowggFDMQswCQYDVQQGEwJCUjELMAkGA1UECBMCU1AxDzANBgNVBAcTBkxP
TkRPTjEcMBoGA1UEChMTT3BlbiBCYW5raW5nIEJyYXNpbDFDMEEGA1UEAxM6aHR0
cHM6Ly93ZWIuY29uZm9ybWFuY2UuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2ls
Lm9yZy5icjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxGjAYBgNVBA8TEUdvdmVy
bm1lbnQgRW50aXR5MRMwEQYLKwYBBAGCNzwCAQMTAlVLMTMwMQYDVQRhEypPRkJC
Ui03NGU5MjlkOS0zM2I2LTRkODUtOGJhNy1jMTQ2Yzg2N2E4MTcxNDAyBgoJkiaJ
k/IsZAEBEyQxMDEyMDM0MC0zMzE4LTRiYWYtOTllMi0wYjU2NzI5YzRhYjIwggEi
MA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC7BjqM17OFx1eN5bdkZIz2cWq5
/eWuQONogpz2e38AyTsA8xxtTmYABTAHnS6QWBrGqK7XDxKks6srHzbNkr7UVR5+
fg5EfF/SqqWeatFstw3rr5qsN3XnHJUCFsBD6R6IetmrnGlWSIAoJFfqKtYx594U
w0dnE5egBfas087RqSM2V5H9uRcjSfB40MqANERDAZEeftGkNYyzj9Csa5g+WZLH
GqdtW28y7d2tOK4px0e99dAuNRjofCLpRoVH8Ez8ayy7+iJoo4CNRwoGGCayRatK
hrsp6CQ1/0X2sn3Rc02QiiCRhEY3AUYSgiUm64YcAbsO913YtC92lSMUe9gDAgMB
AAGjggMFMIIDATAMBgNVHRMBAf8EAjAAMB0GA1UdDgQWBBQ7XBioIXwyC2PYczsD
uwtKXNck1jAfBgNVHSMEGDAWgBSGf1itF/WCtk60BbP7sM4RQ99MvjBMBggrBgEF
BQcBAQRAMD4wPAYIKwYBBQUHMAGGMGh0dHA6Ly9vY3NwLnNhbmRib3gucGtpLm9w
ZW5iYW5raW5nYnJhc2lsLm9yZy5icjBLBgNVHR8ERDBCMECgPqA8hjpodHRwOi8v
Y3JsLnNhbmRib3gucGtpLm9wZW5iYW5raW5nYnJhc2lsLm9yZy5ici9pc3N1ZXIu
Y3JsMEUGA1UdEQQ+MDyCOmh0dHBzOi8vd2ViLmNvbmZvcm1hbmNlLmRpcmVjdG9y
eS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnIwDgYDVR0PAQH/BAQDAgWgMBMGA1Ud
JQQMMAoGCCsGAQUFBwMCMIIBqAYDVR0gBIIBnzCCAZswggGXBgorBgEEAYO6L2QB
MIIBhzCCATYGCCsGAQUFBwICMIIBKAyCASRUaGlzIENlcnRpZmljYXRlIGlzIHNv
bGVseSBmb3IgdXNlIHdpdGggUmFpZGlhbSBTZXJ2aWNlcyBMaW1pdGVkIGFuZCBv
dGhlciBwYXJ0aWNpcGF0aW5nIG9yZ2FuaXNhdGlvbnMgdXNpbmcgUmFpZGlhbSBT
ZXJ2aWNlcyBMaW1pdGVkcyBUcnVzdCBGcmFtZXdvcmsgU2VydmljZXMuIEl0cyBy
ZWNlaXB0LCBwb3NzZXNzaW9uIG9yIHVzZSBjb25zdGl0dXRlcyBhY2NlcHRhbmNl
IG9mIHRoZSBSYWlkaWFtIFNlcnZpY2VzIEx0ZCBDZXJ0aWNpY2F0ZSBQb2xpY3kg
YW5kIHJlbGF0ZWQgZG9jdW1lbnRzIHRoZXJlaW4uMEsGCCsGAQUFBwIBFj9odHRw
Oi8vcmVwb3NpdG9yeS5zYW5kYm94LnBraS5vcGVuYmFua2luZ2JyYXNpbC5vcmcu
YnIvcG9saWNpZXMwDQYJKoZIhvcNAQELBQADggEBACjaIPM71+6aarcCzUUscTuu
N1ZHazWsGBAsVyPPLgC/cxX1IqAA8W9pLaxRBO4F/CVsqJf2ArS0HMB6aZxVxSty
Ka//oAI/qd6Z+8vx10iT2u359yTXBA7AoIQGAeoC0A2UyKG32V2OtCOKdSQVtu2F
MOaDZhdjxrJACAt8/nTXOZubqFk8laFVo9dmdXxdFd0vejCpvcVQItkjmTsjihMp
xpVPAP52I/ZW3tct2cMJfaw+NulaYgVKhcAu/HGtT0KKbPWq8E7IgtuQrqaLe9n6
Jz3aHfCWJ7IYgBbIRyMhd5oi5Dp8txLxrpTgJ2V9+8wyvzijWbUBHMJnXuiXojM=
-----END CERTIFICATE----- |

### 9.1. Enviar uma solicitação com uma declaração de software
Este exemplo inclui vários campos opcionais, alguns dos quais podem não ser aplicáveis a algumas implantações. Para um guia completo dos atributos e sua obrigatoriedade, consultar o Swagger DCR [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). A quebra de linha dentro dos valores são apenas para fins de exibição.
| POST /reg HTTP/1.1
Host: auth.raidiam.com
Content-Type: application/json
{
  "application_type": "web",
  "grant_types": [
    "client_credentials",
    "authorization_code",
    "refresh_token",
    "implicit"
  ],
  "id_token_signed_response_alg": "PS256",
  "require_auth_time": false,
  "response_types": [
    "code id_token",
    "id_token"
  ],
  "software_statement": "eyJraWQiOiJzaWduZXIiLCJ0eXAiOiJKV1QiLCJhbGciOiJQUzI1NiJ9.eyJzb2Z0d2FyZV9tb2RlIjoiTGl2ZSIsInNvZnR3YXJlX3JlZGlyZWN0X3VyaXMiOlsiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvY2IiXSwic29mdHdhcmVfc3RhdGVtZW50X3JvbGVzIjpbeyJyb2xlIjoiREFET1MiLCJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsInN0YXR1cyI6IkFjdGl2ZSJ9LHsicm9sZSI6IlBBR1RPIiwiYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJzdGF0dXMiOiJBY3RpdmUifV0sInNvZnR3YXJlX2NsaWVudF9uYW1lIjoiUmFpZGlhbSBBY2NvdW50aW5nIiwib3JnX3N0YXR1cyI6IkFjdGl2ZSIsInNvZnR3YXJlX2NsaWVudF9pZCI6IkNraTFFYnZqd3loUEIxMk5HTGx6MiIsImlzcyI6Ik9wZW4gQmFua2luZyBPcGVuIEJhbmtpbmcgQnJhc2lsIHByb2QgU1NBIGlzc3VlciIsInNvZnR3YXJlX3Rvc191cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nXC90b3MuaHRtbCIsInNvZnR3YXJlX2NsaWVudF9kZXNjcmlwdGlvbiI6IlJhaWRpYW0gQWNjb3VudGluZyBsZXZlcmFnZSBjdXR0aW5nIGVkZ2Ugb3BlbiBiYW5raW5nIGFjY2VzcyB0byBicmluZyB5b3UgcmVhbCB0aW1lIHVwIHRvIGRhdGUgdmlld3Mgb2YgeW91ciBmaW5hbmNlcyIsInNvZnR3YXJlX2p3a3NfZW5kcG9pbnQiOiJodHRwczpcL1wva2V5c3RvcmUuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5iclwvYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkXC8yNTU1NmQ1YS1iOWRkLTRlMjctYWExYS1jY2U3MzJmZTc0ZGVcL2FwcGxpY2F0aW9uLmp3a3MiLCJzb2Z0d2FyZV9wb2xpY3lfdXJpIjoiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvcG9saWN5Lmh0bWwiLCJzb2Z0d2FyZV9pZCI6IjI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZSIsInNvZnR3YXJlX2NsaWVudF91cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nLmh0bWwiLCJzb2Z0d2FyZV9qd2tzX2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvYXBwbGljYXRpb24uandrcyIsInNvZnR3YXJlX2p3a3NfdHJhbnNwb3J0X2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9qd2tzX3RyYW5zcG9ydF9lbmRwb2ludCI6Imh0dHBzOlwvXC9rZXlzdG9yZS5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyXC9iOTYxYzRlYi01MDlkLTRlZGYtYWZlYi0zNTY0MmIzODE4NWRcLzI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9sb2dvX3VyaSI6Imh0dHBzOlwvXC93d3cucmFpZGlhbS5jb21cL2FjY291bnRpbmdcL2xvZ28ucG5nIiwib3JnX2lkIjoiYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkIiwic29mdHdhcmVfZW52aXJvbm1lbnQiOiJwcm9kdWN0aW9uIiwic29mdHdhcmVfdmVyc2lvbiI6MS4xMCwic29mdHdhcmVfcm9sZXMiOlsiREFET1MiLCJQQUdUTyJdLCJvcmdfbmFtZSI6Ik9wZW4gQmFua2luZyBCcmFzaWwiLCJpYXQiOjE2MTgzMzYyNjIsIm9yZ2FuaXNhdGlvbl9jb21wZXRlbnRfYXV0aG9yaXR5X2NsYWltcyI6W3siYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJhdXRob3Jpc2F0aW9ucyI6W10sInJlZ2lzdHJhdGlvbl9pZCI6IjEzMzUzMjM2LU9CQi1DT05UQSIsImF1dGhvcml0eV9pZCI6IjY4N2ExYzk0LWIzNjAtNGUwNC05NTg5LTBmYTVjYjE2NDUxYiIsImF1dGhvcmlzYXRpb25fcm9sZSI6IkNPTlRBIiwiYXV0aG9yaXR5X2NvZGUiOiJCQ0IiLCJzdGF0dXMiOiJBY3RpdmUifSx7ImF1dGhvcmlzYXRpb25fZG9tYWluIjoiT3BlbiBCYW5raW5nIiwiYXV0aG9yaXNhdGlvbnMiOltdLCJyZWdpc3RyYXRpb25faWQiOiIxMzM1MzIzNi1PQkItREFET1MiLCJhdXRob3JpdHlfaWQiOiI2ODdhMWM5NC1iMzYwLTRlMDQtOTU4OS0wZmE1Y2IxNjQ1MWIiLCJhdXRob3Jpc2F0aW9uX3JvbGUiOiJEQURPUyIsImF1dGhvcml0eV9jb2RlIjoiQkNCIiwic3RhdHVzIjoiQWN0aXZlIn0seyJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsImF1dGhvcmlzYXRpb25zIjpbXSwicmVnaXN0cmF0aW9uX2lkIjoiMTMzNTMyMzYtT0JCLVBBR1RPIiwiYXV0aG9yaXR5X2lkIjoiNjg3YTFjOTQtYjM2MC00ZTA0LTk1ODktMGZhNWNiMTY0NTFiIiwiYXV0aG9yaXNhdGlvbl9yb2xlIjoiUEFHVE8iLCJhdXRob3JpdHlfY29kZSI6IkJDQiIsInN0YXR1cyI6IkFjdGl2ZSJ9XX0.W6hUAYhjT6I61rxEIVMKYKre93LTbRdzKnk9dJvUdzVgAz5B9KxZNutf27oO3k0hrjYVWBdWq23o_e4Y_AaKdpS9-rtU84JiHtmqV0wcFYIM8nqcUVWqQ-Ux6Nq9L2G-s2YNd3PcJ1e3yGg9h8553Gr7iJusKEgApzXUpkM2rBELQuumktUE_JBiuIkXmWxoRnO1cW-Osbk3MT3bxG43SPcxii07Q5S8qXI6PjCPA3fYlnaUAygwZM3O0oa7jqmSr7d9UsHuDMJfYhIKdq2wyQQKORCN-D2UopmMX-lHMvAVkkrAO08T0-7odjr4PJk-PrwuoCxeAfa7440ZDOrlmQ",
  "subject_type": "public",
  "token_endpoint_auth_method": "private_key_jwt",
  "request_object_signing_alg": "PS256",
  "require_signed_request_object": true,
  "require_pushed_authorization_requests": false,
  "tls_client_certificate_bound_access_tokens": true,
  "client_id": "aCnBHjZBvD6ku3KVBaslL",
  "client_name": "Raidiam Accounting",
  "client_uri": "https://www.raidiam.com/accounting.html",
  "request_object_encryption_alg": "RSA-OAEP",
  "request_object_encryption_enc": "A256GCM",
  "jwks_uri": "https://keystore.directory.openbankingbrasil.org.br/b961c4eb-509d-4edf-afeb-35642b38185d/25556d5a-b9dd-4e27-aa1a-cce732fe74de/application.jwks",
  "redirect_uris": [
    "https://www.raidiam.com/accounting/cb"
  ],
  "webhook_uris": [
    "https://www.myitp.com/mykong3"
  ]
} |

### 9.2. Open Finance Brasil SSA Key Store e detalhes do emissor
As links a seguir apontam para as chaves públicas do Diretório de Participantes, e devem ser usadas para verificar a validadade da assinatura dos *software_statements* apresentados durante o processo de registro de cliente.**Producão**[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)Emissor do Open Finance Open Finance Brasil SSA de produção**Sandbox**[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)Emissor do Open Finance Open Finance Brasil SSA de sandbox
### 9.3. Sobre os mecanismos de autenticação e autorização dos serviços de DCR e DCM
Por serem serviços auxiliares ao fluxo principal do Open Finance Brasil, os serviços de registro e manutenção dinâmica de clientes não utilizam os mesmos mecanismos de controle de acesso. Por exemplo: não é possível exigir um *access_token* OAuth 2.0 de uma aplicação cliente que ainda não está registrada na instituição transmissora. Para estender as [RFC7591](https://tools.ietf.org/html/rfc7591) e [RFC7592](https://tools.ietf.org/html/rfc7592), que recomendam mecanismos mínimos para autenticação dos seus serviços, as instituições que suportam os fluxos de registro e manutenção dinâmica de clientes devem implementar em seus Servidores de Autorização os controles a seguir:
#### 9.3.1. Registro de cliente - POST /register

1. validar que o certificado apresentado pela aplicação cliente é subordinado às cadeias do ICP-Brasil definidas no Padrão de Certificados do Open Finance Brasil;
2. enquanto houver a necessidade do período de convivência (mencionado no tópico 7.1) deve ser implementado a validação para ambos os casos: certificados que possuem o valor org_id no campo organizationUnitName ( OU ) e certificados que possuem o valor org_id no campo organizationIdentifier .
3. assegurar que a assinatura do software_statement apresentado pela aplicação cliente durante o registro tenha sido feita pelo Diretório de Participantes através das chaves públicas descritas na seção anterior;
4. assegurar que o software_statement apresentado pela aplicação cliente durante o registro corresponda à mesma instituição do certificado de cliente apresentado, validando-o através dos atributos que trazem `organization_id` no certificado X.509.
5. não devem ser permitidos múltiplos cadastros DCR para o mesmo Software Statement , de forma que em caso de tentativa de novo registro para um Software Statement já cadastrado, deve se utilizar o procedimento de Error Response definido no item 3.2.2 da RFC7591.
6. emitir, na resposta do registro, um `registration_access_token` para ser usado como token de autenticação nas operações de manutenção da aplicação cliente registrada, seguindo as especificações descritas na RFC7592 .

#### 9.3.2. Manutenção de cliente - GET /register - PUT /register - DELETE /register

1. removido
2. validar a presença e a correspondência do header Bearer `Authorization` contendo o valor do atributo `registration_access_token` retornado durante o registro do cliente correspondente.
3. quando o método chamado for PUT /register, realizar as validações dos subitens 1, 3, 4 e 6 do item Registro de cliente - POST /register .
4. quando o método chamado for GET /register, realizar as validações dos subitens 1 e 6 do item Registro de cliente - POST /register .
5. quando o método chamado for DELETE /register, realizar a validação do subitem 1 do item Registro de cliente - POST /register .
*Observação:* A [RFC7592](https://tools.ietf.org/html/rfc7592) prevê a possibilidade de rotação do `registration_access_token` emitido pelo Servidor de Autorização a cada uso, tornando-o um token de uso único. As instituições devem considerar esse aspecto no registro de suas aplicações cliente para receber e atualizar o `registration_access_token` pelo novo valor recebido nas chamadas de manutenção de cliente.
### 9.4. Validação de certificados de assinatura

- O diretório realiza a validação do certificado de assinatura através da função cert rescan , a cada hora.
- As instituições devem assegurar que o processo de validação é realizado.
- Cada instituição deve ter alternativa de contingência em caso de indisponibilidade do serviço de validação realizado pelo diretório.
- Ao identificar que o certificado de assinatura não é válido pois, está com status revogado de acordo com o OCSP/CRL da CA emissora, ou está inativo no cadastro do diretório, o conjunto de chaves públicas é movido para o repositório de chaves inativas (Inactive Keystore).
- É recomendado que o processo de validação inclua: Validação da assinatura da mensagem do Transmissor de Dados, a ser feita pelo Receptor de Dados Validar se a mensagem está assinada conforme o Message Signature Guidelines , incluindo se o iss é igual ao organisation_id do servidor que emitiu a mensagem. Buscar a declaração iss do JWT e gerar URI do JWKS publicado no diretório, para consulta. Certificar se o kid do cabeçalho JWT da mensagem está presente no diretório JWKS. Validar se a chave privada para o kid correspondente é capaz de validar a assinatura da mensagem. Validação da assinatura da mensagem do Receptor de Dados, a ser feita pelo Transmissor de Dados Validar se a mensagem está assinada conforme o Message Signature Guidelines . Obter o org_jwks_uri que foi apresentado no SSA pelo cliente no momento do DCR. Certificar se o kid do cabeçalho JWT da mensagem está presente no diretório JWKS. Validar se a chave privada para o kid correspondente é capaz de validar a assinatura da mensagem.

## 10. Reconhecimento
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro de dados por meio da formação do Grupo de Trabalho OpenID Foundation FAPI, o GT de Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Avisos
Copyright (c) 2023 Estrutura Inicial do Open Finance BrasilA Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
### A.1. Apêndice A. Exemplo de afirmação de declaração de software

| eyJraWQiOiJzaWduZXIiLCJ0eXAiOiJKV1QiLCJhbGciOiJQUzI1NiJ9.eyJzb2Z0d2FyZV9tb2RlIjoiTGl2ZSIsInNvZnR3YXJlX3JlZGlyZWN0X3VyaXMiOlsiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvY2IiXSwic29mdHdhcmVfc3RhdGVtZW50X3JvbGVzIjpbeyJyb2xlIjoiREFET1MiLCJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsInN0YXR1cyI6IkFjdGl2ZSJ9LHsicm9sZSI6IlBBR1RPIiwiYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJzdGF0dXMiOiJBY3RpdmUifV0sInNvZnR3YXJlX2NsaWVudF9uYW1lIjoiUmFpZGlhbSBBY2NvdW50aW5nIiwib3JnX3N0YXR1cyI6IkFjdGl2ZSIsInNvZnR3YXJlX2NsaWVudF9pZCI6IkNraTFFYnZqd3loUEIxMk5HTGx6MiIsImlzcyI6Ik9wZW4gQmFua2luZyBPcGVuIEJhbmtpbmcgQnJhc2lsIHByb2QgU1NBIGlzc3VlciIsInNvZnR3YXJlX3Rvc191cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nXC90b3MuaHRtbCIsInNvZnR3YXJlX2NsaWVudF9kZXNjcmlwdGlvbiI6IlJhaWRpYW0gQWNjb3VudGluZyBsZXZlcmFnZSBjdXR0aW5nIGVkZ2Ugb3BlbiBiYW5raW5nIGFjY2VzcyB0byBicmluZyB5b3UgcmVhbCB0aW1lIHVwIHRvIGRhdGUgdmlld3Mgb2YgeW91ciBmaW5hbmNlcyIsInNvZnR3YXJlX2p3a3NfZW5kcG9pbnQiOiJodHRwczpcL1wva2V5c3RvcmUuZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5iclwvYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkXC8yNTU1NmQ1YS1iOWRkLTRlMjctYWExYS1jY2U3MzJmZTc0ZGVcL2FwcGxpY2F0aW9uLmp3a3MiLCJzb2Z0d2FyZV9wb2xpY3lfdXJpIjoiaHR0cHM6XC9cL3d3dy5yYWlkaWFtLmNvbVwvYWNjb3VudGluZ1wvcG9saWN5Lmh0bWwiLCJzb2Z0d2FyZV9pZCI6IjI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZSIsInNvZnR3YXJlX2NsaWVudF91cmkiOiJodHRwczpcL1wvd3d3LnJhaWRpYW0uY29tXC9hY2NvdW50aW5nLmh0bWwiLCJzb2Z0d2FyZV9qd2tzX2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvYXBwbGljYXRpb24uandrcyIsInNvZnR3YXJlX2p3a3NfdHJhbnNwb3J0X2luYWN0aXZlX2VuZHBvaW50IjoiaHR0cHM6XC9cL2tleXN0b3JlLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnJcL2I5NjFjNGViLTUwOWQtNGVkZi1hZmViLTM1NjQyYjM4MTg1ZFwvMjU1NTZkNWEtYjlkZC00ZTI3LWFhMWEtY2NlNzMyZmU3NGRlXC9pbmFjdGl2ZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9qd2tzX3RyYW5zcG9ydF9lbmRwb2ludCI6Imh0dHBzOlwvXC9rZXlzdG9yZS5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyXC9iOTYxYzRlYi01MDlkLTRlZGYtYWZlYi0zNTY0MmIzODE4NWRcLzI1NTU2ZDVhLWI5ZGQtNGUyNy1hYTFhLWNjZTczMmZlNzRkZVwvdHJhbnNwb3J0Lmp3a3MiLCJzb2Z0d2FyZV9sb2dvX3VyaSI6Imh0dHBzOlwvXC93d3cucmFpZGlhbS5jb21cL2FjY291bnRpbmdcL2xvZ28ucG5nIiwib3JnX2lkIjoiYjk2MWM0ZWItNTA5ZC00ZWRmLWFmZWItMzU2NDJiMzgxODVkIiwic29mdHdhcmVfZW52aXJvbm1lbnQiOiJwcm9kdWN0aW9uIiwic29mdHdhcmVfdmVyc2lvbiI6MS4xMCwic29mdHdhcmVfcm9sZXMiOlsiREFET1MiLCJQQUdUTyJdLCJvcmdfbmFtZSI6Ik9wZW4gQmFua2luZyBCcmFzaWwiLCJpYXQiOjE2MTgzMzYyNjIsIm9yZ2FuaXNhdGlvbl9jb21wZXRlbnRfYXV0aG9yaXR5X2NsYWltcyI6W3siYXV0aG9yaXNhdGlvbl9kb21haW4iOiJPcGVuIEJhbmtpbmciLCJhdXRob3Jpc2F0aW9ucyI6W10sInJlZ2lzdHJhdGlvbl9pZCI6IjEzMzUzMjM2LU9CQi1DT05UQSIsImF1dGhvcml0eV9pZCI6IjY4N2ExYzk0LWIzNjAtNGUwNC05NTg5LTBmYTVjYjE2NDUxYiIsImF1dGhvcmlzYXRpb25fcm9sZSI6IkNPTlRBIiwiYXV0aG9yaXR5X2NvZGUiOiJCQ0IiLCJzdGF0dXMiOiJBY3RpdmUifSx7ImF1dGhvcmlzYXRpb25fZG9tYWluIjoiT3BlbiBCYW5raW5nIiwiYXV0aG9yaXNhdGlvbnMiOltdLCJyZWdpc3RyYXRpb25faWQiOiIxMzM1MzIzNi1PQkItREFET1MiLCJhdXRob3JpdHlfaWQiOiI2ODdhMWM5NC1iMzYwLTRlMDQtOTU4OS0wZmE1Y2IxNjQ1MWIiLCJhdXRob3Jpc2F0aW9uX3JvbGUiOiJEQURPUyIsImF1dGhvcml0eV9jb2RlIjoiQkNCIiwic3RhdHVzIjoiQWN0aXZlIn0seyJhdXRob3Jpc2F0aW9uX2RvbWFpbiI6Ik9wZW4gQmFua2luZyIsImF1dGhvcmlzYXRpb25zIjpbXSwicmVnaXN0cmF0aW9uX2lkIjoiMTMzNTMyMzYtT0JCLVBBR1RPIiwiYXV0aG9yaXR5X2lkIjoiNjg3YTFjOTQtYjM2MC00ZTA0LTk1ODktMGZhNWNiMTY0NTFiIiwiYXV0aG9yaXNhdGlvbl9yb2xlIjoiUEFHVE8iLCJhdXRob3JpdHlfY29kZSI6IkJDQiIsInN0YXR1cyI6IkFjdGl2ZSJ9XX0.W6hUAYhjT6I61rxEIVMKYKre93LTbRdzKnk9dJvUdzVgAz5B9KxZNutf27oO3k0hrjYVWBdWq23o_e4Y_AaKdpS9-rtU84JiHtmqV0wcFYIM8nqcUVWqQ-Ux6Nq9L2G-s2YNd3PcJ1e3yGg9h8553Gr7iJusKEgApzXUpkM2rBELQuumktUE_JBiuIkXmWxoRnO1cW-Osbk3MT3bxG43SPcxii07Q5S8qXI6PjCPA3fYlnaUAygwZM3O0oa7jqmSr7d9UsHuDMJfYhIKdq2wyQQKORCN-D2UopmMX-lHMvAVkkrAO08T0-7odjr4PJk-PrwuoCxeAfa7440ZDOrlmQ |

## Author's Address
**OFBIS GT Security**Open Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Dynamic Client Registration > Histórico de Especificações - DCR > DCR-BR v2.0.0 - Open FinanceBrasil Dynamic Client Registration > [EN]  Open Finance Brasil Dynamic Client Registration - v2.0.0

---
id: 246120449
title: [EN]  Open Finance Brasil Dynamic Client Registration - v2.0.0
version: 6
modified: 2025-12-02T19:16:44.626Z
url: /spaces/OF/pages/246120449/EN+Open+Finance+Brasil+Dynamic+Client+Registration+-+v2.0.0
---

17
## Foreword
Este documento também está disponível em [português](file:///C:/wiki/spaces/DraftOF/pages/76251331)The Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.Open Finance Brasil Financial-grade API Security Profile 1.0 consists of the following parts:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introduction
The Open Finance Brasil Financial-grade API Dynamic Client Registration Profile is a profile of [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) and [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) that aims to provide specific implementation guidelines for security and interoperability which can be applied to the identification, registration and management of OAuth Clients operating in the Brasil Open Finance ecosystem.Although it is possible to code an OpenID Provider and Relying Party from scratch using this specification, the main audience for this specification are parties who already have a certified implementation of [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) and seek to obtain certification for the Brasil Open Finance programme.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml). These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the method of
- applications registered in the Open Finance Directory of Participants to discover OpenID Providers offering services in the Open Finance Brasil ecosystem;
- applications to use OpenID Connect Registration to onboard their applications with Bank OpenID Providers; and
- applications to use OAuth 2.0 Dynamic Client Registration Management Protocol to manage their applications with OpenID Providers;
This document is applicable to all participants engaging in Open Finance in Brasil.
## 2. Normative references
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger
## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) and ISO29100 apply.
## 4. Symbols and Abbreviated terms

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security

## 5. Introduction
Brasil Open Finance ecosystem leverages a federation trust provider or directory of participants as the golden source of information on accredited participants and software that are authorized to partake in the Open Finance Brasil ecosystem.The services by the Directory include
- Software registration and management.
- Software credential registration and management using ICP Certificates.
- Software Statement Assertion (SSA) generation
Participants within the ecosystem must leverage these services to facilitate API driven OAuth client registration using the process outlined in clause 3.1.1 of [RFC7591](https://tools.ietf.org/html/rfc7591) with additional metadata necessary to support OpenID Connect defined in [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).It's important to remember that the client registration payload has most of its attributes as non-mandatory, and that assigned values that conflict with those in the software statement assertion will be overridden by the values of the software statement assertion issued by the Directory of Participants. Not all metadata a client wishes to provide may be contained in a software statement, e.g alternative [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). There are some cases where the client metadata are subset of the existing values in the SSA, such as redirect_URIs.
## 6. Open Finance Brasil OpenID Connect Discovery provisions

### 6.1. Authorization server
The Authorization Server shall support [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) as required by [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). This support shall be explicit in Participant Directory configurations, and in the declaration of its attributes in the Discovery file (well-known), respecting the authentication mechanisms certified by the institution through the Open Finance Brazil compliance tests.In addition, the Authorization Server:
1. shall advertise its presence in the Open Finance Brasil ecosystem by being listed on the Directory of Participants;
2. shall advertise all Open Finance Brasil REST API resources protected by the OpenID Provider on the Directory of Participants;
3. shall advertise support for all signing, encryption, authentication mechanisms and standards required to support Open Finance Brasil Financial API ;
4. shall advertise support for OpenID Dynamic Client Registration ;
5. may advertise mtls_endpoint_aliases as per clause 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens the token_endpoint, registration_endpoint, userinfo_endpoint and push_authorization_request_endpoint;
6. if supporting Financial API - Client Initiated Back Channel Authentication shall advertise through OIDD mtls_endpoint_aliases the backchannel_authentication_endpoint;
7. shall not rotate the registration_access_token.

### 6.2. Client
The Client shall support [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) as required by [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html)In addition, the Client
1. shall rely on ecosystem discovery services provided by Directory of Participants only;
2. shall derive necessary Authorisation Server metadata by relying on an Authorization Servers OpenID Connect Discovery services only;
3. where present, shall use endpoints advertised in mtls_endpoint_aliases as per clause 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens ;

## 7. Open Finance Brasil OpenID Connect Registration Provisions

### 7.1. Authorization server
The Authorization Server shall support the RFC RFCs Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) and [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)In addition, the Authorization Server
1. shall reject dynamic client registration requests not performed over a connection secured with mutual tls using certificates issued by Brazil ICP (production) or the Directory of Participants (sandbox);
2. shall validate that the request contains software_statement JWT signed using the PS256 algorithim issued by the Open Finance Brasil directory of participants;
3. shall validate that the software_statement was issued (iat) not more than 5 minutes prior to the request being received;
4. shall validate that the attribute jwks (key set by value) was not included; but declared as a reference in the jwks_uri attribute;
5. shall, when informed, validate that jwks_uri matches the software_jwks_uri provided in the software_statement; shall validate if the content obtained through jwks_uri contains a certificate of type use: “enc”;
6. shall require and validate that redirect_uris matches or contains a sub set of software_redirect_uris provided in the software_statement;
7. shall require and validate that all client authentication mechanism adhere to the requirements defined in RFC7591 and RFC7592 , validating the registration_access_token and, through a secure connection, the certificate chain of ICP-Brasil;
8. removed;
9. shall validate that the requested scopes are adequate for accredited institutions and their regulatory roles and contained in the software_statement. The list of regulatory permissions and the corresponding scopes are described in the following sections;
10. where possible, shall compare client metadata asserted by a client to the metadata provided in the software_statement, choosing values in the SSA with precedence;
11. shall accept all x.500 AttributeType name strings defined in the Distinguished Name of the x.509 Certificate Profiles defined in Open Finance Brasil x.509 Certificate Standards ;
12. The value of the field UID of the certificate should match the one sent in the SSA, where the UID field should contain the value of the software_id field of the SSA.
13. shall, during the TLS handshake process, use the distinguishedNameMatch rule to compare the DN values as defined in RFC4517 .
14. shall ensure the integrity of the stock of active consents, even after any systemic changes, so that such changes are transparent to the data receiver institutions (TPP).
15. shall perform a recertification on OIDF FAPI and DCR after any systemic changes.
16. The value of the software_api_webhook_uris attribute contained as an attribute in the JWS in software_statement must be compared with the webhook_uris field. If the values are not exactly the same, the error must be returned, with the HTTP status code set to 400, error filled in as invalid_webhook_uris and error_description filled in with The content of the webhook_uris field different from what was Registered in the software_statement noted via the JWS software_api_webhook_uris field.
17. If the webhook_uris field is not declared in the payload, the webhook functionality shall be considered disabled for the specific client.
These provisions apply equally to the processing of [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) and [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html) requests
#### 7.1.1. Applying Server Defaults
Whenever properties of a DCR request are not included nor mandatory in the specification, the Authorisation Server shall apply client defaults in the following manner:
1. shall select and apply the encryption algorithm and cipher choice from the most recommended of the IANA cipher suites that is supported by the Authorisation Server;
2. shall populate defaults from values within the software_statement assertion where possible;
3. shall grant the client permission to the complete set of potential scopes based on the softwares regulatory permissions included in the software_statement;

### 7.2. Regulatory Roles for OpenID and OAuth 2.0 Mappings
To participate in the Open Finance ecosystem, accredited institutions must register themselves in the directory of participants according to their regulatory roles. Those roles reflect the institutions authorization from the Central Bank and, consequently, the APIs they are allowed to use.The following table describes the regulatory roles for Open Finance and the related OAuth 2.0 scopes mapping. If the scopes are omitted during the DCR process, the authorization server shall grant the complete set of potential scopes based on the registering bank's regulatory roles, as described in the Server Defaults section.
| Regulatory Role | Description | Allowed Scopes | Target Phase |
| DADOS | Instituição transmissora ou receptora de dados (AISP) | openid accounts credit-cards-accounts consents customers invoice-financings financings loans unarranged-accounts-overdraft resources credit-fixed-incomes exchanges bank-fixed-incomes variable-incomes treasure-titles funds | Phase 2 and Phase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid payments recurring-payments nrp-consents | Phase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Phase 3 |
| CCORR | Correspondente de crédito | openid | Phase 3* |
It is requiread that the active roles in the application's software_statement are validated. The field _software_statement_roles shall be used for validation and currently listed roles shall be active.
## 8. Software Statement Assertion
A Software Statement Assertion (software_statement) is a JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) that asserts the metadata values of the client software as a whole. On the Open Finance Brasil structure, this software_statement is signed by the Participants Directory and it's signature MUST be validated by the Authorization Servers using the public keys available on the following session.
### 8.1. Attributes of the Software Statement Assertion (Claims)
The following example contains all attributes currently included in a software_statement:wide1800
## 9. Processing of the Dynamic Client Registration claim

### 9.1. Sending a Registration Claim with a Software Statement
This example includes several optional fields, some of those may not be applicable to some implememntations. For a complete guide to attributes and its mandate, consult the DCR Swagger [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). Line breaks inside values serve presentation purposes only.wide1800
### 9.2. Open Finance Brasil SSA Key Store and Issuer Details
The following links point to public keys of the Participant Directory and must be used to verify the signature validity of the software_statements presented during the client registration process.**Production**[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)Open Finance Open Finance Brasil production SSA issuer**Sandbox**[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)Open Finance Open Finance Brasil sandbox SSA issuer
### 9.3. About authentication and authorization mechanisms for DCR and DCM services
As they are auxiliary services to the main flow of Open Finance Brasil, the dynamic registration and maintenance services for clients do not use the same access control mechanisms. For example, it is not possible to require an OAuth 2.0 access_token from a client application that isn't registered yet with the transmitting institution.To extend [RFC7591](https://tools.ietf.org/html/rfc7591) and [RFC7592](https://tools.ietf.org/html/rfc7592), which recommend minimum mechanisms for authentication of their services, institutions that support the registration flows and dynamic maintenance of clients must implement the following controls:
#### 9.3.1. Client registration - POST /register

1. validate that the certificate presented by the client application is subordinate to the ICP-Brasil chains defined in the Open Finance Brasil Certificates Standard;
2. ensure that the signature of the software_statement_ presented by the client application during registration has been made by the Directory of Participants using the public keys described in the previous section;
3. ensure that the software_statement presented by the client application during registration corresponds to the same institution as the client certificate presented, validating it through the attributes that bring organization_id in the X.509 certificate.
4. Multiple DCR registrations for the same Software Statement should not be allowed, in a way that in case of a new registration attempt for an already registered Software Statement, the Error Response procedure defined on item 3.2.2 of the RFC7591 must be enforced.
5. issue, on the registry response, a registration_access_token to be used as an authentication token on maintaining operations of the registered client application, following specifications described in RFC7592 .

#### 9.3.2. Client Maintenance - GET /register - PUT /register - DELETE /register

1. Validate the presence and matching of the Bearer header Authorization containing the value of the registration_access_token attribute returned during registration of the corresponding client.
2. When the invoked method is PUT / register, carry out the validations of sub-items 1, 2, 3, and 5 of item Client registration - POST /register .
3. When the invoked method is GET /register, carry out the validations of sub-items 1 and 5 of item Client registration - POST /register .
4. When the invoked method is DELETE /register, carry out the validation of sub-item 1 of item Client registration - POST /register .

### 9.4. Signature certificates validation

- The directory uses cert rescan function hourly to validation process.
- The organization shall ensure that the validation process was completed.
- Each organization must have a continuity plan in case of unavailability validation service.
- If the signature certificate is not valid because it has a revoked status according to the CA’s OCSP/CRL issuer, or is inactive in the directory register, the set of public keys is moved to the inactive key storage.
- The validation process should include: Resource server (Data Transmitter) message signature validation, to be done by the Client (Data Receiver) Validate that the message was signed in line with what’s defined on the Message Signature Guidelines, including that the iss is equal to the organisation_id of the server that issued the message. Fetch the “iss” claim from the JWT and build the directory application JWKS uri for that specific server. Make sure that the kid present on the message JWT header is present on the directory JWKS. Validate that the private key for the corresponding kid is able to validate the message signature. Client (Data Receiver) message signature validation, to be done by the Resource Server Validate how the message was signed in line with what’s defined on the Message Signature Guidelines. Obtain the org_jwks_uri which was presented on the SSA by the client on the moment of the registration (DCR) Make sure that the kid present on the message JWT header is present on the directory JWKS. Validate that the private key for the corresponding kid is able to validate the message signature.

## 10. Acknowledgement
With thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Caio Zanolla (Belvo)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
### A.1. Appendix A. Example Software Statement Assertion
wide1800
## Author's Address
OFBIS GT SecurityOpen Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Dynamic Client Registration > Histórico de Especificações - DCR > DCR-BR v2.0.0 - Open FinanceBrasil Dynamic Client Registration > [PT]  Open Finance Brasil Dynamic Client Registration - v2.0.0

---
id: 246054957
title: [PT]  Open Finance Brasil Dynamic Client Registration - v2.0.0
version: 6
modified: 2025-12-02T19:16:18.839Z
url: /spaces/OF/pages/246054957/PT+Open+Finance+Brasil+Dynamic+Client+Registration+-+v2.0.0
---

17
## Prefácio
The normative version in EnglishA Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. O EIOFB não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:O Perfil de Segurança Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
Essas partes devem ser usadas com [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html), [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) e [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introdução
O Perfil de Registro de Cliente Dinâmico (DCR - Dynamic Client Registration) do Financal-grade API (FAPI) do Open Finance Brasil é um perfil de [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) que visa fornecer diretrizes de implementação específicas para segurança e interoperabilidade que podem ser aplicadas à identificação, registro e gerenciamento de Clients OAuth operando no ecossistema Open Finance Brasil.[¶](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html#section-note.2-1)Embora seja possível codificar um OpenID Provider e Relying Party desde o princípio usando esta especificação, o principal público para esta especificação são as partes que já possuem uma implementação certificada do [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html) e desejam obter a certificação para o Open Finance Brasil.
## Convenções Notacionais
As palavras-chave "deve" (shall), "não deve" (shall not), "deveria" (should), "não deveria" (should not) e "pode" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml) observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 1. Escopo
Este documento especifica o método de
- aplicativos cadastrados no Diretorio de Participantes do Open Finance para descobrir OpenID Providers que oferecem serviços no ecossistema Open Finance Brasil;
- aplicativos para usar o OpenID Connect Registration para integrar seus aplicativos com OpenID Providers dos bancos; e
- aplicativos para usar OAuth 2.0 Dynamic Client Registration Management Protocol para gerenciar seus aplicativos com OpenID Providers;
Este documento é aplicável a todos os participantes do Open Finance no Brasil.
## 2. Referências normativas
Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[RFC4514](https://www.rfc-editor.org/rfc/rfc4514) - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names[RFC4517](https://www.rfc-editor.org/rfc/rfc4517) - Lightweight Directory Access Protocol (LDAP): Syntaxes and Matching Rules[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[OFB-FAPI](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html) - Open Finance Brasil Financial-grade API Security Profile 1.0[OFB-Cert-Standards](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-certificate-standards-1_ID1.html) - Open Finance Brasil x.509 Certificate Standards[OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml) - DCR & DCM Swagger
## 3. Termos e definições
Para efeitos deste documento, aplicam-se os termos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e ISO29100.
## 4. Símbolos e Termos abreviados

- API - Application Programming Interface (Interface de Programação da Aplicação)
- DCR - Dynamic Client Registration (Registro de Cliente Dinâmico)
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- SS - Software Statement (Declaração de Software)
- SSA - Software Statement Assertion (Afirmação de Declaração de Software)
- TLS - Transport Layer Security

## 5. Introdução
O ecossistema Open Finance Brasil apoia-se em um provedor de confiança ou diretório de participantes como a fonte mais valiosa de informações sobre participantes credenciados e softwares que estão autorizados a participar do ecossistema Open Finance Brasil.Os serviços do Diretório incluem:
- Registro e gerenciamento de software
- Registro e gerenciamento de credenciais de software usando certificados ICP
- Geração de Software Statement Assertion (SSA)
Os participantes do ecossistema devem aproveitar esses serviços para facilitar o registro de cliente OAuth orientado por API usando o processo descrito na cláusula 3.1.1 do [RFC7591](https://tools.ietf.org/html/rfc7591) com metadados adicionais necessários para oferecer suporte ao OpenID Connect definido em [OpenID Connect Registration](https://openid.net/specs/openid-connect-registration-1_0.html).É importante reforçar que o payload de registro de clientes possui a maior parte de seus atributos não obrigatórios, e que os atributos cujos valores conflitem com os presentes no software statement assertion serão sobrepostos pelos valores do próprio software statement assertion emitido pelo diretório central. Nem todos os metadados que um cliente deseja fornecer podem estar contidos em um software statement, por exemplo, alternativa [Metadata Languages and Script values](https://openid.net/specs/openid-connect-registration-1_0.html#LanguagesAndScripts). Há casos ainda de metadados de cliente que são um subconjunto dos valores existentes no SSA, como por exemplo os redirect_URIs.
## 6. Provisionamentos do OpenID Connect Discovery do Open Finance Brasil

### 6.1. Servidor de Autorização
O servidor de autorização deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html). Este suporte deve estar explicito tanto na forma como o Servidor de Autorização está registrado no Diretório de Participantes quanto na declaração dos seus atributos no arquivo de Discovery (well-known), respeitando os mecanismos de autenticação certificados pela institição através dos testes de conformidade do Open Finance Brasil.Adicionalmente, o Servidor de Autorização:
1. deve anunciar sua presença no ecossistema Open Finance Brasil, sendo listada no Diretório de Participantes;
2. deve anunciar todos os recursos API REST do Open Finance Brasil protegidos pelo Provedor OpenID no Diretório de Participantes;
3. deve anunciar suporte para todos os mecanismos de assinatura, criptografia, autenticação e padrões necessários para suportar o Open Finance Brasil Financial API ;
4. deve anunciar suporte para OpenID Dynamic Client Registration ;
5. pode anunciar mtls_endpoint_aliases de acordo com a cláusula 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens o token_endpoint, registration_endpoint, userinfo_endpoint e push_authorization_request_endpoint;
6. se suportar Financial API - Client Initiated Back Channel Authentication , deve anunciar através de OIDD mtls_endpoint_aliases o backchannel_authentication_endpoint;
7. não deve rotacionar o registration_access_token

### 6.2. Cliente
O cliente deve suportar [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) conforme exigido pelo [Financial-grade API Security Profile 1.0 - Part 1: Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html).Além disso, o Cliente
1. deve contar com serviços de descoberta do ecossistemas fornecidos apenas pelo Diretório de Participantes;
2. deve derivar os metadados necessários do Authorization Server somente por meio do serviço OpenID Connect Discovery dos Authorization Servers;
3. quando presente, deve usar endpoints anunciados em mtls_endpoint_aliases conforme a cláusula 5 RFC 8705 OAuth 2.0 Mutual-TLS Client Authentication e Certificate-Bound Access Tokens ;

## 7. Provisionamento de registro OpenID Connect do Open Finance Brasil

### 7.1. Servidor de Autorização
O servidor de autorização deve suportar as RFCs de Dynamic Client Registration (DCR) [RFC7591](https://tools.ietf.org/html/rfc7591), Dynamic Client Management (DCM) [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)Além disso, o servidor de autorização
1. deve rejeitar as solicitações de registro de cliente dinâmico não realizadas em uma conexão protegida com mTLS usando certificados emitidos pelo Brasil ICP (produção) ou o Diretório de Participantes (sandbox);
2. deve validar que a solicitação contém software_statement JWT assinado usando o algoritmo PS256 emitido pelo Diretório de Participantes do Open Finance Brasil;
3. deve validar que o software_statement foi emitido (iat - issued at) não mais de 5 minutos antes do pedido ser recebido;
4. deve validar que um atributo jwks (definida por valor) não foi incluído, e sim declarado como referência no atributo jwks_uri;
5. deve, quando informado, validar que o jwks_uri corresponda ao software_jwks_uri fornecido na declaração do software; deve validar se o conteúdo obtido através do jwks_uri contém um certificado do tipo use: “enc”;
6. deve exigir e validar que o redirect_uris corresponda ou contenha um subconjunto dos valores de software_redirect_uris fornecidos no software_statement;
7. deve exigir e validar que todos os mecanismos de autenticação de cliente cumpram os requisitos definidos nas RFC7591 e RFC7592 , através da validação do registration_access_token e, como conexão segura, da cadeia de certificados confiáveis ICP-Brasil.
8. removido;
9. deve validar se os escopos solicitados são adequados para as permissões regulatórias autorizadas da instituição e contidas no _software_statement. A relação de permissões regulatórias e os escopos correspondentes está descrita nas seções a seguir.
10. deve, sempre que possível, validar os metadados declarados pelo cliente em relação aos metadados fornecidos no software_statement, adotando os valores presentes no SSA com precedência.
11. deve aceitar todos os nomes x.500 AttributeType definidas no Distinguished Name dos Perfis de Certificado x.509 definidos em Open Finance Brasil x.509 Certificate Standards ;
12. O valor do campo UID do certificado deve coincidir com o enviado no SSA, onde o campo UID deve conter o valor do campo software_id do SSA.
13. deve, durante o processo de handshake TLS, usar a regra distinguishedNameMatch para comparar os valores DN conforme definido na RFC4517 . ¶
14. deve ser garantido a todos, após os mesmos atos de consentimentos permanentes, para que também sejam alterados para instituições receptoras de dados transparentes (TPP).
15. deve realizar recertificação FAPI e DCR OIDF após eventuais alterações sistêmicas.
16. O valor do atributo software_api_webhook_uris contido como atributo no JWS em software_statement deverá ser comparado com o campo webhook_uris. Caso os valores não sejam exatamente iguais, deve-se retornar o erro, com HTTP status code setado para 400, error preenchido como invalid_webhook_uris e error_description preenchido com The content of the webhook_uris field differs from what was registered in the software_statement observed through the JWS field's software_api_webhook_uris.
17. Se o campo webhook_uris não for declarado no payload, a funcionalidade webhook deverá ser considerado como desativado para o client em questão.
Estas disposições aplicam-se igualmente ao processamento de pedidos [RFC7591](https://tools.ietf.org/html/rfc7591), [RFC7592](https://tools.ietf.org/html/rfc7592) e [OpenID Registration](https://openid.net/specs/openid-connect-registration-1_0.html)
#### 7.1.1. Aplicando Server Defaults
Quando as propriedades de uma solicitação DCR não estão incluídas e não são obrigatórias na especificação, o Authorization Server deve aplicar os padrões do cliente da seguinte maneira:
1. deve selecionar e aplicar o algoritmo de criptografia e a escolha da cifra a partir dos conjuntos mais recomendados de cifra da IANA que são suportados pelo Servidor de Autorização;
2. deve preencher defaults a partir de valores da afirmação de software_statement, sempre que possível;
3. deve conceder ao cliente permissão para o conjunto completo de escopos potenciais com base nas permissões regulatórias de softwares incluídas no software_statement;

### 7.2. Funções regulatórias para mapeamentos OpenID e OAuth 2.0
Para participar do ecossistema do Open Finance, as instituições credenciadas devem se cadastrar no Diretório de Participantes de acordo com seus papéis regulatórios. Essas funções refletem a autorização do Banco Central para as instituições e, consequentemente, as APIs que podem utilizar.A tabela a seguir descreve as funções regulatórias do Open Finance e o mapeamento de escopos do OAuth 2.0 relacionado. Se os escopos forem omitidos durante o processo de DCR, o Servidor de Autorização deve conceder o conjunto completo de escopos potenciais com base nas funções regulatórias registradas para o banco, conforme descrito na seção Server Defaults.
| Papel Regulador | Descrição | Escopos Permitidos | Fase-alvo |
| DADOS | Instituição transmissora / receptora de dados (AISP) | openid accounts credit-cards-accounts consents customers invoice-financings financings loans unarranged-accounts-overdraft resources credit-fixed-incomes exchanges bank-fixed-incomes variable-incomes treasure-titles funds | Fase 2 e Fase 4 |
| PAGTO | Instituição prestadora de serviço de iniciação de pagamentos (PISP) | openid payments recurring-payments nrp-consents | Fase 3 |
| CONTA | Instituição detentora de conta (ASPSP) | openid | Fase 3 |
| CCORR | Correspondente de crédito | openid | Fase 3* |
É necessário validar as roles ativas no software_statement da aplicação. Na validação dessa informação deve ser utilizado o campo _software_statement_roles, e deve ser verificado se as roles listadas estão ativas.
## 8. Declaração de Software
Uma declaração de software (software_statement) é um JSON Web Token (JWT) [RFC7519](https://tools.ietf.org/html/rfc7519) que afirma valores de metadados sobre o software cliente como um todo. Na estrutura do Open Finance Brasil, esse software_statement é assinado pelo Diretório de Participantes, e sua assinatura DEVE ser validada pelos Servidores de Autorizacao usando as chaves públicas disponíveis na seção a seguir.
### 8.1. Atributos da Declaração de Software (Claims)
O exemplo a seguir contém todos os atributos atualmente incluídos em um software_statement:wide1800
## 9. Processamento de solicitação de registro de cliente dinâmico

### 9.1. Enviar uma solicitação com uma declaração de software
Este exemplo inclui vários campos opcionais, alguns dos quais podem não ser aplicáveis a algumas implantações. Para um guia completo dos atributos e sua obrigatoriedade, consultar o Swagger DCR [OFB-DCR/DCM-Swagger](https://raw.githubusercontent.com/OpenBanking-Brasil/specs-seguranca/main/dcr_review/dcr-dcm-swagger.yaml). A quebra de linha dentro dos valores são apenas para fins de exibição.wide1800
### 9.2. Open Finance Brasil SSA Key Store e detalhes do emissor
As links a seguir apontam para as chaves públicas do Diretório de Participantes, e devem ser usadas para verificar a validadade da assinatura dos software_statements apresentados durante o processo de registro de cliente.**Producão**[https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.directory.openbankingbrasil.org.br/openbanking.jwks)Emissor do Open Finance Open Finance Brasil SSA de produção**Sandbox**[https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks](https://keystore.sandbox.directory.openbankingbrasil.org.br/openbanking.jwks)Emissor do Open Finance Open Finance Brasil SSA de sandbox
### 9.3. Sobre os mecanismos de autenticação e autorização dos serviços de DCR e DCM
Por serem serviços auxiliares ao fluxo principal do Open Finance Brasil, os serviços de registro e manutenção dinâmica de clientes não utilizam os mesmos mecanismos de controle de acesso. Por exemplo: não é possível exigir um access_token OAuth 2.0 de uma aplicação cliente que ainda não está registrada na instituição transmissora. Para estender as [RFC7591](https://tools.ietf.org/html/rfc7591) e [RFC7592](https://tools.ietf.org/html/rfc7592), que recomendam mecanismos mínimos para autenticação dos seus serviços, as instituições que suportam os fluxos de registro e manutenção dinâmica de clientes devem implementar em seus Servidores de Autorização os controles a seguir:
#### 9.3.1. Registro de cliente - POST /register

1. validar que o certificado apresentado pela aplicação cliente é subordinado às cadeias do ICP-Brasil definidas no Padrão de Certificados do Open Finance Brasil;
2. assegurar que a assinatura do software_statement apresentado pela aplicação cliente durante o registro tenha sido feita pelo Diretório de Participantes através das chaves públicas descritas na seção anterior;
3. assegurar que o software_statement apresentado pela aplicação cliente durante o registro corresponda à mesma instituição do certificado de cliente apresentado, validando-o através dos atributos que trazem organization_id no certificado X.509.
4. não devem ser permitidos múltiplos cadastros DCR para o mesmo Software Statement , de forma que em caso de tentativa de novo registro para um Software Statement já cadastrado, deve se utilizar o procedimento de Error Response definido no item 3.2.2 da RFC7591.
5. emitir, na resposta do registro, um registration_access_token para ser usado como token de autenticação nas operações de manutenção da aplicação cliente registrada, seguindo as especificações descritas na RFC7592 .

#### 9.3.2. Manutenção de cliente - GET /register - PUT /register - DELETE /register

1. validar a presença e a correspondência do header Bearer Authorization contendo o valor do atributo registration_access_token retornado durante o registro do cliente correspondente.
2. quando o método chamado for PUT /register, realizar as validações dos subitens 1, 2, 3 e 5 do item Registro de cliente - POST /register .
3. quando o método chamado for GET /register, realizar as validações dos subitens 1 e 5 do item Registro de cliente - POST /register .
4. quando o método chamado for DELETE /register, realizar a validação do subitem 1 do item Registro de cliente - POST /register .

### 9.4. Validação de certificados de assinatura

- O diretório realiza a validação do certificado de assinatura através da função cert rescan, a cada hora.
- As instituições devem assegurar que o processo de validação é realizado.
- Cada instituição deve ter alternativa de contingência em caso de indisponibilidade do serviço de validação realizado pelo diretório.
- Ao identificar que o certificado de assinatura não é válido pois, está com status revogado de acordo com o OCSP/CRL da CA emissora, ou está inativo no cadastro do diretório, o conjunto de chaves públicas é movido para o repositório de chaves inativas (Inactive Keystore).
- É recomendado que o processo de validação inclua: Validação da assinatura da mensagem do Transmissor de Dados, a ser feita pelo Receptor de Dados Validar se a mensagem está assinada conforme o Message Signature Guidelines, incluindo se o iss é igual ao organisation_id do servidor que emitiu a mensagem. Buscar a declaração iss do JWT e gerar URI do JWKS publicado no diretório, para consulta. Certificar se o kid do cabeçalho JWT da mensagem está presente no diretório JWKS. Validar se a chave privada para o kid correspondente é capaz de validar a assinatura da mensagem. Validação da assinatura da mensagem do Receptor de Dados, a ser feita pelo Transmissor de Dados Validar se a mensagem está assinada conforme o Message Signature Guidelines. Obter o org_jwks_uri que foi apresentado no SSA pelo cliente no momento do DCR. Certificar se o kid do cabeçalho JWT da mensagem está presente no diretório JWKS. Validar se a chave privada para o kid correspondente é capaz de validar a assinatura da mensagem.

## 10. Reconhecimento
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro de dados por meio da formação do Grupo de Trabalho OpenID Foundation FAPI, o GT de Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- Alexandre Daniel Dalabrida (Cooperativa Central Ailos)
- Alexandre Siqueira (Mercado Pago)
- André Borges (Banco Fibra)
- Bernardo Vale (Banco Inter)
- Danilo Sasaki (Banco Itaú)
- João Rodolfo Vieira da Silva (Banco Itaú)
- Michelle Bandarra (Chicago)
- Nic Marcondes (Quanto)
- Rafael Gonzalez Hashimoto (Banco C6)
- Ralph Bragg (Raidiam)

## Appendix A. Avisos
Copyright (c) 2023 Estrutura Inicial do Open Finance BrasilA Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
### A.1. Apêndice A. Exemplo de afirmação de declaração de software
wide1800
## Author's Address
OFBIS GT SecurityOpen Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Glossário de Segurança > Histórico da página - Glossário de Segurança

---
id: 240650401
title: Histórico da página - Glossário de Segurança
version: 2
modified: 2023-12-15T14:55:37.766Z
url: /spaces/OF/pages/240650401/Hist+rico+da+p+gina+-+Gloss+rio+de+Seguran+a
---

## Change log
 
| De / Para - Versão | Item de trabalho (Conteúdo Motivador) | Demandante | O que foi alterado? | Motivador |
| --- | --- | --- | --- | --- |
| | | | | |
| | | | | |

---

# Glossário de Segurança > v1.0 - Glossário de Segurança

---
id: 240650381
title: v1.0 - Glossário de Segurança
version: 2
modified: 2023-12-15T14:55:32.818Z
url: /spaces/OF/pages/240650381/v1.0+-+Gloss+rio+de+Seguran+a
---

## Glossário de Segurança

| Sigla | Descrição | Informação |
| --- | --- | --- |

| Sigla | Descrição | Informação |
| --- | --- | --- |
| API | Interface de programação de aplicativo | Uma interface de programação de aplicativo é um conjunto de rotinas, protocolos e ferramentas para construir aplicativos de software. Uma API especifica como os componentes de software devem interagir. |
| FAPI | Financial API | Especificação técnica de API e define requisitos técnicos adicionais para o setor financeiro |
| CIBA | Client Initiated Backchannel Authentication | A autenticação de backchannel iniciada pelo cliente (CIBA) é um dos padrões mais recentes da OpenID Foundation. são categorizados como "fluxo desacoplado", Ele permite novas maneiras de obter o consentimento do usuário final |
| Oauth | | O OAuth é um protocolo de autorização para API's web voltado a permitir que aplicações client acessem um recurso protegido em nome de um usuário. |
| OIDC | OpenID Connect | OpenID Connect é um protocolo de identidade simples com padrão aberto |
| JWT | JSON Web Token | é uma técnica definida na RFC 7519 para autenticação remota entre duas partes. Ele é uma das formas mais utilizadas para autenticar usuários em APIs RESTful. |
| JWS | JSON Web Signature | é uma forma de garantir a integridade das informações em um formato altamente serializado |
| SHA256 | Secure Hash Algorithm | é um conjunto de funções criptográficas de hash |
| PKCE | Proof Key for Code Exchange | Chave de prova para troca de código por clientes públicos Oauth |
| MAC | Código de Autenticação de Mensagem | Permite que as declarações sejam assinadas digitalmente ou protegidas por integridade utilizando JWS |
| ICP-Brasil | Infraestrutura de Chaves Públicas Brasileira | na definição oficial, “uma cadeia hierárquica de confiança que viabiliza a emissão de certificados digitais para identificação virtual do cidadão |
| AC | Autoridade Certificadora | |
| AR | Autoridade de Registro | |
| TLS | Transport Layer Security | |
| ECDSA | Elliptic Curve Digital Signature Algorithm | é um algoritmo de método de assinatura digital de documentos utilizando criptografia baseada em curvas elípticas. |
| ECDHE | Elliptic-curve Diffie–Hellman | é um protocolo de contrato chave que permite que duas partes, cada uma com um par de chaves público-privado de curva elíptica, estabeleçam um segredo compartilhado em um canal inseguro |
| AES | Advanced Encryption Standard | algoritmos de criptografia de bloco simétrico com uma chave de criptografia de 256 bits |
| Autenticação mútua | | Chamamos de autenticação mútua quando ambos cliente e servidor apresentam certificados para serem validados pelo par. |
| CSR | Certificate Signing Request | Contém informação que irá ser incluída no seu certificado como o nome da empresa/organização, common name (domínio), localidade e país. Também contém a chave pública (public key) que será incluída no seu certificado. Normalmente é também criada uma chave privada (private key) ao mesmo tempo que é criado o CSR |
| TPP | Instituições Provedoras - Provedores terceirizados | As instituições provedoras são organizações que usam APIs desenvolvidas pelos ASPSP para acessar contas de clientes, a fim de fornecer serviços de informações de contas |
| ASPSP | Instituições Transmissoras - Provedor de serviços de pagamento de manutenção de contas | Um ASPSP é qualquer instituição financeira que oferece uma conta de pagamento com acesso online. Os ASPSPs devem fornecer acesso para permitir que terceiros (TPP) registrados acessem as informações da conta através de APIs |
| SSA | Software Statement Assertion | SSA é um JSON Web Token (JWT) que contém metadados sobre uma instância de aplicativo client desenvolvida por um TPP. O JWT é emitido e assinado pelo OpenBanking Directory. |
| End User | | Identificação de usuário final que possui as informações que se deseja acessar |
| Back-End | | Aplicação ou código que da inteligência de negocio as ações solicitadas via API , código que efetivamente realiza a função desejada |
| Json | JavaScript Object Notation | Json é um modelo para armazenamento e transmissão de informações no formato texto. |
| Claims | | São escopos/declarações usadas em uma API durante a autenticação para autorizar o acesso aos detalhes de um usuário, como nome e imagem por exemplo. Cada escopo retorna um conjunto de atributos do usuário, que são chamados de declarações. |
| Header | | É o cabeçalho de uma solicitação ou resposta que transmite contexto e metadados adicionais sobre a solicitação ou resposta. Por exemplo, em uma mensagem de solicitação podem ser usados para fornecer credenciais de autenticação. |
| Payload | | O Payload é a Carga Útil do token JWT. É aqui que você coloca informações como a quem o token pertence, qual a expiração dele, quando ele foi criado, entre outras coisas |

---

# Guia do Usuário > Histórico da página - Guia do Usuário

---
id: 240648769
title: Histórico da página - Guia do Usuário
version: 2
modified: 2023-12-15T14:52:00.559Z
url: /spaces/OF/pages/240648769/Hist+rico+da+p+gina+-+Guia+do+Usu+rio
---

## Change log
 
| De / Para - Versão | Item de trabalho (Conteúdo Motivador) | Demandante | O que foi alterado? | Motivador |
| --- | --- | --- | --- | --- |
| | | | | |
| | | | | |

---

# Guia do Usuário > v1.0 - Guia do usuário > Instituição receptora ou iniciadora de pagamentos > [EN] Guia do Usuário para Instituições Receptores de Dados e Iniciadores de Pagamento (TTP-PISP)

---
id: 240648690
title: [EN] Guia do Usuário para Instituições Receptores de Dados e Iniciadores de Pagamento (TTP/PISP)
version: 2
modified: 2023-12-15T14:51:55.198Z
url: /spaces/OF/pages/240648690/EN+Guia+do+Usu+rio+para+Institui+es+Receptores+de+Dados+e+Iniciadores+de+Pagamento+TTP+PISP
---

## 1. Registering an Application
At a high level the following major steps are required in order to onboard a new application into the Open Finance Brasil ecosystem.
1. Register your organisation on the directory of participants (User Interface)
2. Register your application on the directory of participants (User Interface)
3. Obtain credentials for your application from the Brasil ICP (Out of scope of this document)
4. Register your credentials for your application on the directory of participants (User Interface)
5. Identify providers of Account information or Payment Services of interest to customers of your application by searching the directory of participants (API)
6. Register your application with each provider (API)

### 1.1. Sequence Diagram

### 1.2. Directory Overview
The trust framework services provided by Open Finance Brasil provide all of the discovery services necessary for TPPs and ASPSPs to interact with each other without being required to validate the authenticity of each others’ Identity, Authorizations, Consumer Offerings (Apps), APIs or Credentials for the Applications. In addition it provides a single registry of all consumer propositions being offered in the market and a single control plane for the regulatory authorities granting permissions to manage participants within the ecosystem.The trust framework does not have visibility or view of interactions that occur between TPPs and Providers. It is designed to provide trust and surety of identity and authorization only. It does not sit within the communication flow between a consumer and a provider and it has no knowledge or visbility of any customer data. This trust framework model is known as transitive trust. Where two parties, a TPP and an ASPSP agree to trust a common trust providers statements and attestations regarding the legitimacy of each other and then proceed with communicating whatever they would like with no additional costly validation or checking being required.
### 1.3. Accessing the Directory
This user guide assumes that participating organisations have already been through the onboarding process with the Open Finance Brasil Initial Structure and have completed all of the necessary onboarding, contract signing and individual administrator onboarding processes.
### 1.4. Creating a new Software Statement
A software statement is an ‘App’ on what can be thought of as the Open Finance Brasil App Store. This App record contains all of the information necessary for a Bank to Technically Identity and Interact with it as well as containing all of the information that assist consumers using the application with confirming its legitimacy.A new application or software statement can be registered by logging on to the Directory, navigating to ‘Software Statements’ and clicking ‘Create New’ and populating the form. Help text is provided for each field on the screen. Please remember that the majority of this information will be displayed to customers by the Banks as part of the redirection or authorization process. As such it is important that all URIs and Descriptions are relevant for customer audience.
#### 1.4.1. Assigning Software Regulatory Roles
In a complex and diverse data sharing ecosystem, the regulatory roles that an organisation can have can change. They can be added and revoked. This means that software added to the directory can be given permission to have 0 or more regulatory roles. A administrator can assign to a given software any and all permissions that the organisation that owns the software can have.Should an organisation lose a regulatory role then all software with that regulatory role will be revoked from the ecosystem so it is very important that an application is only given the roles that it actually needs in order to function.A real world example of this could be ‘Amazon’, Amazon has two applications, ‘Amazon Accounting’ and ‘Amazon Prime’. Amazon as an organisation is an authorized DADOS and PISP, and is allowed to handle customer data as well as make Open Finance Payments. Amazon Accounting should be assigned the domain role of DADOS and Amazon Prime should be assigned a domain role of PISP.In the future, should Amazon lose regulatory permission to be a PISP then only the Amazon Prime application would be removed from the ecosystem. Amazon Account would continue to function without issue.
### 1.5. Creating and Uploading Certificates

#### 1.5.1. Sandbox
The Open Finance Directory contains a PKI that can be used to create certificates for the Applications being registered. Simply select certificates from the drop down menu and follow the instructions.The directory supports multiple certificate and key types and an openssl command and configuration file is made available as an example. Once you have created the necessary Certificate Signing Request (CSR) for both a “Transport” and “Signing” certificate you can submit them to the directory to be validated and minted into certificates.Please remember to follow your organisations key management practices for certificate generation. These credentials and keys need to be handled carefully. A significant key compromise event could lead to customer data being compromised.
#### 1.5.2. Production
Certificates must be provided by the Brasil ICP. The steps to follow are included in the [Open Finance Brasil Certificate Guide](https://github.com/OpenBanking-Brasil/specs-seguranca/blob/main/open-banking-brasil-ICP-certificate-guide.pdf)
#### 1.5.3. What is a JWT, JWE, JWS and JWK
When certificates are uploaded to the directory, the trust framework advertises them in [JSON Web Key Sets](https://tools.ietf.org/html/rfc7517) with each JSON Web Key or JWK having a unique ‘KID’ or Key ID. JWK’s in addition to having specific properties describing the algorithm and cipher suites that they support also advertise their ‘use’ which can either be of type ‘enc’ for encryption or ‘sig’ for signing.These ‘sig’ keys and ‘enc’ key pairs are used in many places within the Open Finance ecosystem to encrypt or to sign data using the standards defined in [RFC 7519 JSON Web Token](https://tools.ietf.org/html/rfc7519) which should be read in detail by developers.Types of JWT include
- OpenID Connect Request Objects defined in Open ID Connect Core
- OpenID Connect id_token defined in Open ID Connect Core
Amongst many others.These JWT’s may be encrypted also be encrypted using JSON Web Encryption (JWE). In the majority of cases the keys that should be used to validate a JSON Web Signature (JWS) or the key that was used to encrypt a JWE is usually published as a JSON Web Key in a JSON Web Key Set with the reference to the key being carried in the ‘kid’ (Key ID) header field.**As a worked example: An example JWT Request Object**The example above is decoded below. In the header is ‘kid’ of `PWAi5ruQcHfzPzq2JFdpY7nAUh6LzTTQtDBUpOM37JQ` which can be located in the JSON Web KeySet for this client [here](https://keystore.sandbox.directory.openbankingbrasil.org.br/74e929d9-33b6-4d85-8ba7-c146c867a817/1509a662-6b3a-4cb8-b7c0-ffb6e596eb0d/application.jwks)The public JWK from the JWKS taken from the uri given earlier The private key that was used to create the JWS
## 2. Interacting with the Trust Services APIs
When an application is registered on the Directory, the central service uses the provided meta data and certificates to create for the software a OAuth 2.0 client that has a grant type of ‘client credentials’ as defined in [RFC6749](https://tools.ietf.org/html/rfc6749) with a client authentication mechanism of ‘`tls_client_auth`' as defined in [RFC 8705](https://tools.ietf.org/html/rfc8705)Using the ClientID listed on the software statement in the Directory, [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) and the OpenID Provider Issuer configuration below, a participant has all of the necessary infomation to discover, authenticate and interact with the Directory APIs.
### 2.1. Trust Framework Issuer
Production: [https://auth.directory.openbankingbrasil.org.br/](https://auth.directory.openbankingbrasil.org.br/)Sandbox: [https://auth.sandbox.directory.openbankingbrasil.org.br/](https://auth.sandbox.directory.openbankingbrasil.org.br/)
### 2.2. How to communicate with the Directory Authorization Server
Use the OpenID Issuer and Clause 4 of the OpenID Discovery Specification to retrieve the ‘openid-configuration’ document.Retrieve the Mutual TLS token endpoint alias as defined by [RFC8705 - OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens](https://tools.ietf.org/html/rfc8705)Establish a Mutual TLS connection using the transport certificate registered early and request an access token with the scope ‘`directory:software`'Use the OpenID Issuer and Clause 4 of the OpenID Discovery Specification to retrieve the ‘openid-configuration’ document.Retrieve the Mutual TLS token endpoint alias as defined by [RFC8705 - OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens](https://tools.ietf.org/html/rfc8705)Establish a Mutual TLS connection using the transport certificate registered early and request an access token with the scope ‘`directory:software`'Retrieve the Mutual TLS token endpoint alias as defined by [RFC8705 - OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens](https://tools.ietf.org/html/rfc8705)Establish a Mutual TLS connection using the transport certificate registered early and request an access token with the scope ‘directory:software’
### 2.3. How to communicate with the Directory APIs
The Directory APIs are RESTful resources secured using the Brasil Open Banking Security Profile, this means that they have the same security posture as Banks APIs. All of the Directories APIs require OAuth 2.0 resource scope of directory:software and are secured using Mutual TLS.Please see the Directory OpenAPI v3 specification for full set of endpoints available.
### 2.4. Discovering Banks Authorization Servers
Interrogate the participants (public information) resource and retrieve a list of all participants and their Authorization Servers.Filter the participants to those that have Authorization Servers protecting resources that you are interested in accessing for your product. In the example above, there are two Authorization Servers for ‘Amazing Bank’ one for the Retail Business and one for the Business Banking.The App now has discovered the list of Banks that are offering APIs that might be useful to customers of the Application and the App can now generate a list of Banks ‘Customer Friendly Names’ and Logos to display to consumers to enable them to select the bank from which they want to share data.
## 3. Registering the application with a provider
From the example given above we can see that the location of the “OpenIDDiscoveryDocument” is advertised by each of the Authorization Servers
### 3.1. Creating a Software Statement
A software statement assertion (SSA) is a signed JWT from the Directory that contains all of the information about an application that exists at a point in time on the directory. It includes the location of all of the public keys that are linked to this software statement and all of the other metadata a bank needs to validate the legitimacy of the application.An SSA does not have an expiry, it is simply a point in time record of what existed as valid attributes at the point of time that it was created. Banks should accept an SSA that is less than a few minutes old but the exact window may differ between providers.Obtain an access token and then retrieve the software statement for a application on the Directory.
### 3.2. Sending an RFC7591 Dynamic Client Registration Request
Please see [Open Finance Brasil Dynamic Client Registration](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82051199/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3)
### 3.3. Saving the RFC7592 Dynamic Client Management Token
Please see [Open Finance Brasil Dynamic Client Registration](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82051199/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3)
### 3.4. Modifying a client using RFC7592 Dynamic Client Management Token
Please see [Open Finance Brasil Dynamic Client Registration](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/82051199/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3)
## 4. Obtaining Access to Customers Resources
For all options including all permission codes please see the [Consent API](https://openbanking-brasil.github.io/areadesenvolvedor/swagger/swagger_consents_apis.yaml). The following examples are minimal but functional examples to demonstrate end to end flow. These examples are assuming that the client is communicating with an OpenID Provider leveraging the ‘tls_client_auth’ token endpoint authentication mechanism. Alternative examples are available in the appendix.
### 4.1. Pre-requisites
These non normative examples assumes that the OAuth Client has discovered the locations of all of the necessary endpoints to communicate with the banks resources from the Directory including the consents resource, the data resources and the OpenID authorization discovery document from the Directory.
### 4.2. Creating Consent

1. Obtain an Access Token with the scope 'consents'
 
1. Create a consent resource

### 4.3. Authorizing Consent - Redirect

#### 4.3.1. Create OpenID Connect Request Object
Different methods of authentication (private_key_jwt and tls_client_auth) and of sending Request Object (with and without PAR) can be supported by Authorization Servers according to the [FAPI-1.0 Part 2 - Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) specification. Therefore, how does it reinforce the security profile for Open Finance Brasil (item 8 of section 5.2.3 of the [security requirements for the confidential client](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html#section-5.2.3)), all combinations (table below) must be supported by API clients.The table below reflects the different security profiles and combinations that shall be supported by all API clients (as per the [OIDF certified profiles for Open Finance Brazil](https://openid.net/certification/#FAPI_OPs)) .
| OIDF Certification Profile |
| BR-OB Adv. OP w/ Private Key, PAR |
All requirements for the OpenID Request Object are included in Brasil Open Finance Security ProfileSignature ommited for brevity
#### 4.3.2. Redirect User to Authorization Server for Authorization
As per OpenID Connect Core.
#### 4.3.3. Obtaining Access Token via Authorization Code Exchange
As per [RFC 7636 Proof Key for Code Exchange](https://tools.ietf.org/html/rfc7636)
#### 4.3.4. Checking Consent Resource Status
At this point, a TPP can optionally check the status of the consent request to see if it has changed to a status of fully authorized. For resources that do not require multi party consent this step should not be necessary however for business accounts or joint accounts with special access requirements then it may take a while for the bank to obtain the additional authorizations necessary for this consent to become completely authorized. TPPs should not abuse checking the consent status API
#### 4.3.5. Access Resources
With the access token that was returned in 4.3.3, the TPP now has the ability to call customers resources.
## Appendix

### A.1 private_key_jwt client credentials grant

### A.2 Example decoded request object body
 
### A.3 Example decoded request object body with specific claim values being requested
In this example a client is requesting that the Authorization Server only authenticates the customer if the cpf claim matches the provided value. The processing requirements for requests with a specific ‘cpf’ value are defined in the Open Finance Brasil Security Profile.
### A.4 Example CIBA decoded Authentication Request body
In this example a CIBA request is being made to request consent authorization using a previously issued id_token as the indication of the resource owner that the bank should contact to obtain authorization.

---

# Guia do Usuário > v1.0 - Guia do usuário > Instituição receptora ou iniciadora de pagamentos > [PT] Guia do Usuário para Instituições Receptores de Dados e Iniciadores de Pagamento (TTP-PISP)

---
id: 240648607
title: [PT] Guia do Usuário para Instituições Receptores de Dados e Iniciadores de Pagamento (TTP/PISP)
version: 2
modified: 2023-12-15T14:51:50.156Z
url: /spaces/OF/pages/240648607/PT+Guia+do+Usu+rio+para+Institui+es+Receptores+de+Dados+e+Iniciadores+de+Pagamento+TTP+PISP
---

TPP - Third Party Provider PISP - Payment Initiation Service Provider
## 1. Registrando um Aplicativo
Em um alto nível, as seguintes etapas principais são necessárias para integrar um novo aplicativo no ecossistema Open Finance Brasil.
1. Cadastre sua organização no Diretório de Participantes (Interface do Usuário)
2. Cadastre seu aplicativo no Diretório de Participantes (Interface do Usuário)
3. Obtenha credenciais para sua aplicação junto à uma autoridade certificadora ICP-Brasi)(fora do escopo deste documento)
4. Registre suas credenciais para o seu aplicativo no Diretório de Participantes (Interface do Usuário)
5. Identifique provedores de informações de conta ou serviços de pagamento de interesse dos clientes de seu aplicativo, pesquisando o Diretório de Participantes (API)
6. Registre seu aplicativo com cada provedor (API)

### 1.1. Diagrama de Sequência

### 1.2. Visão Geral do Diretório
O framework de confiança do Open Finance Brasil fornece todos os serviços de descoberta necessários para que instituições participantes (receptoras e transmissoras de dados, iniciadoras de pagamento ou detentoras de contas) interajam entre si sem serem obrigadas a validarem a autenticidade de identidades, autorizações, Apps, APIs ou credenciais para acessos por aplicativos uns dos outros. Além disso, fornece um único registro de todas propostas ao consumidor sendo oferecidas no mercado e um único ambiente de controle para as autoridades regulatórias que concedem permissões para gerenciar participantes dentro do ecossistema.O framework de confiança não tem visibilidade ou visão das interações que ocorrem entre instituições participantes receptoras (TPP) ou transmissoras (ASPSP) de dados. Ele é projetado para fornecer confiança e garantia de identidade e autorização apenas. Ele não se enquadra no fluxo de comunicação entre um consumidor e um provedor e não tem conhecimento ou visibilidade de quaisquer dados do cliente. Este modelo de framework de confiança é conhecido como confiança transitiva onde duas partes, um TPP e um ASPSP, concordam em confiar nas declarações e atestados de legitimidade uns dos outros emitidos por um provedor de confiança comum e, em seguida, prossigam comunicando o que quiserem, sem qualquer validação adicional onerosa ou outro tipo de verificação
### 1.3. Acessando o Diretório
Este guia do usuário assume que as organizações participantes já passaram pelo processo de iniciação com a Estrutura Inicial do Open Finance Brasil e já concluíram todas as integrações necessárias, processos de assinatura de contrato e inclusão de administrador individual.
### 1.4. Criação de uma Nova Declaração de Software (SSA)
Uma declaração de software descreve um aplicativo inserido naquilo que pode ser considerado a ‘App Store’ do Open Finance Brasil. Este registro de aplicativo contém todas as informações necessárias para que um banco identifique tecnicamente e interaja com o aplicativo, além de conter todas as informações que auxiliam os clientes que estejam utilizando-o a confirmar sua legitimidade.Um novo aplicativo ou declaração de software pode ser registrado fazendo logon no Diretório, navegando até ‘Software Statements’, clicando em ‘Criar Novo’ e preenchendo o formulário. O texto de ajuda é fornecido para cada campo da tela. Lembre-se de que a maioria dessas informações será exibida aos clientes pelos Bancos como parte do processo de redirecionamento ou autorização. Como tal, é importante que todas as URIs e descrições sejam relevantes para o público.
#### 1.4.1. Atribuição de Funções Regulatórias de Software
Em um ecossistema de compartilhamento de dados complexo e diversificado, as funções regulatórias de uma organização podem mudar. Eles podem ser adicionados e revogados. Isso significa que o software adicionado ao Diretório pode receber permissão de ter zero (0) ou mais funções regulatórias. Um administrador pode atribuir a um determinado software todo e qualquer permissões que a organização proprietária do software pode ter.Se uma organização perder uma função regulatória, todo software com essa função regulatória será revogado do ecossistema, portanto, é muito importante que um aplicativo receba apenas as funções de que realmente precisa para funcionar.Um exemplo do mundo real disso poderia ser a Amazon. Ela possui dois aplicativos, ‘Amazon Accounting’ e ‘Amazon Prime’. A Amazon como organização é um DADOS e PISP autorizados e tem permissão para lidar com dados de clientes bem como fazer pagamentos via Open Finance Brasil. A ‘Amazon Accounting’ dever receber a função de domínio de DADOS e a ‘Amazon Prime’ deve receber uma função de domínio de PISP.No futuro, se a Amazon perder a permissão regulatória para ser um iniciador de pagamento, apenas a aplicação ‘Amazon Prime’ seria removida do ecossistema. O App ‘Amazon Accounting’ do exemplo continuaria a funcionar sem problemas.
### 1.5. Criação e Upload de Certificados

#### 1.5.1. Sandbox
O serviço de Diretório do Open Finance Brasil inclui uma infraestrutura de chave pública que pode ser usada para criar certificados para os aplicativos sendo registrados no ambiente Sandbox. Basta selecionar certificados no menu e seguir as instruções.O Diretório suporta vários certificados, tipos de chave e um comando e configuração openssl será disponibilizado como um exemplo. Depois de criar a solicitação de assinatura de certificado (Certificate Signing Request - CSR) para um certificado de “Transporte” e “Assinatura”, você pode enviá-los ao diretório para serem validados e transformados em certificados.Lembre-se de seguir as práticas de gerenciamento de chaves de sua organização para a geração de certificados. Essas credenciais e chaves precisam ser manuseadas com cuidado. Um evento significativo de comprometimento de chave pode levar ao comprometimento dos dados do cliente.
#### 1.5.2. Produção
Os certificados para acesso e assinatura em ambiente de produção devem ser fornecidos pelo ICP Brasil. Os detalhes sobre os certificados e os requisitos para os certificados estão detalhados no [Padrão de Certificados Open Finance Brasil](https://github.com/OpenBanking-Brasil/specs-seguranca/blob/main/open-banking-brasil-certificate-standards-1_ID1.md).
#### 1.5.3. O que é um JWT, JWE, JWS e JWK {#JWT_JWE_JWS_JWK)
Quando os certificados são carregados para o Diretório, o framework de confiança os anuncia em [JSON Web Key Sets](https://tools.ietf.org/html/rfc7517) com cada JSON Web Key (JWK) tendo um ‘KID’ ou um Key ID. Os JWKs, além de ter propriedades específicas que descrevem o algoritmo e os conjuntos de criptografia que eles suportam, também anunciam seu “uso”, que pode ser do tipo ‘enc’ para criptografia ou ‘sig’ para assinatura.Essas chaves ‘sig’ e pares de chaves ‘enc’ são usadas em muitos lugares dentro do ecossistema do Open Finance Brasil para criptografar ou assinar dados usando os padrões definidos em [RFC 7519 JSON Web Token](https://tools.ietf.org/html/rfc7519), que deve ser lido em detalhes pelos desenvolvedores.Tipos de JWT incluem
- OpenID Connect Request Objects definidos em Open ID Connect Core
- OpenID Connect `id_token` definido em Open ID Connect Core
Entre muitos outros.Esses JWTs podem ser criptografados também usando o JSON Web Encryption (JWE). Na maioria dos casos, as chaves que devem ser usadas para validar uma assinatura da Web JSON (JWS) ou a chave que foi usada para criptografar um JWE são geralmente publicadas como uma JSON Web Key em um JSON Web Key Set com a referência à chave que está sendo carregada no campo de cabeçalho ‘kid’ (Key ID).**Exemplo de Request Object JWT assinado**O exemplo acima é apresentado decodificado logo abaixo. No cabeçalho está incluso o atributo ‘kid’ (id da chave) com o valor `PWAi5ruQcHfzPzq2JFdpY7nAUh6LzTTQtDBUpOM37JQ`, que pode ser localizado no JSON Web KeySet para este cliente [aqui](https://keystore.sandbox.directory.openbankingbrasil.org.br/74e929d9-33b6-4d85-8ba7-c146c867a817/1509a662-6b3a-4cb8-b7c0-ffb6e596eb0d/application.jwks)O JWK público do JWKS retirado da uri fornecido anteriormenteA chave privada que foi usada para criar o JWSSe quiser conhecer um pouco mais e exercitar, visite o site [JWT-IO](https://jwt.io/) e conheça um pouco mais.
## 2. Interagindo com as APIs de Serviços de Confiança
Quando um aplicativo é registrado no Diretório, o serviço central usa os metadados e certificados fornecidos para criar para o software um cliente OAuth 2.0 que tem um `grant type` do tipo `client credentials`, conforme definido em [RFC6749](https://tools.ietf.org/html/rfc6749) e com um mecanismo de autenticação de cliente definido como `tls_client_auth`, conforme definido em [RFC 8705](https://tools.ietf.org/html/rfc8705).Usando o ClientID listado na declaração do software (software statement) no Diretório, [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) e a configuração do OpenID Provider Issuer abaixo, um participante tem todos das informações necessárias para descobrir, autenticar e interagir com as APIs do Diretório.
### 2.1. Emissores do Framework de Confiança do Diretório
Produção: [https://auth.directory.openbankingbrasil.org.br/](https://auth.directory.openbankingbrasil.org.br/)Sandbox: [https://auth.sandbox.directory.openbankingbrasil.org.br/](https://auth.sandbox.directory.openbankingbrasil.org.br/)Os certificados para acesso às API´s publicadas pelas instituições participantes devem ser obrigatoriamente certificados emitidos no âmbito da ICP-Brasil.
### 2.2. Como se Comunicar com o Authorization Server do Diretório
Use o OpenID Issuer e a Cláusula 4 da especificação [OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) para obter o documento ‘openid-configuration’.Obtenha o ‘alias’ do endpoint do Mutual TLS Token, conforme definido por [RFC8705 - OAuth 2.0 Mutual-TLS Client Authentication and Certificate-Bound Access Tokens](https://tools.ietf.org/html/rfc8705)Estabeleça uma conexão TLS mútua usando o certificado de transporte registrado anteriormente e solicite um token de acesso com o escopo `directory:software`
### 2.3. Como se Comunicar com as APIs do Diretório
As APIs do Diretório são recursos RESTful protegidos usando o Perfil de Segurança do Open Finance Brasil. Isso significa que eles têm a mesma postura de segurança das APIs publicadas pelos Bancos. Todas as APIs de Diretório requerem o escopo do recurso OAuth 2.0 de `directory:software` e são protegidos usando Mutual TLS (mTLS).Consulte a especificação do Diretório OpenAPI v3 para o conjunto completo de endpoints disponíveis.
### 2.4. Descobrindo Authorization Servers de Bancos
Faça uma busca pelo recurso de participantes (informações públicas) e obtenha uma lista de todos os participantes e seus Authorization Servers.Filtre os participantes por aqueles que possuem Authorization Servers protegendo os recursos que você está interessado em acessar para o seu produto. No exemplo acima, existem dois Authorization Server para ‘Amazing Bank’, um para o negócio de varejo e um para o banco corporativo.O aplicativo agora descobriu a lista de bancos que estão oferecendo APIs que podem ser úteis para os usuários do aplicativo e pode gerar uma lista de ‘customer friendly names’ de bancos e logotipos para exibir aos clientes para permitir que eles selecionem o banco a partir do qual desejam compartilhar dados.
## 3. Registrando o Aplicativo com um Provedor
A partir do exemplo dado acima, podemos ver que a localização do “OpenIDDiscoveryDocument” é anunciada por cada um dos Authorization Server.
### 3.1. Criação de uma Declaração de Software (SSA)
Uma afirmação de declaração de software (software statement assertion - SSA) é um JWT assinado pelo Diretório que contém todas as informações sobre um aplicativo que existe em um determinado momento no Diretório. Inclui a localização de todas as chaves públicas vinculadas à esta declaração de software e todos os outros metadados de que um banco precisa para validar a legitimidade do aplicativo.Um SSA não tem período de validade, é simplesmente um registro pontual do que existia como atributos válidos no momento em que foi criado. Os bancos devem aceitar um SSA com menos de alguns minutos, mas a janela exata pode ser diferente entre os provedores.Obtenha um token de acesso e, em seguida, carregue a declaração do software para um aplicativo no Diretório.
### 3.2. Enviando uma Solicitação de Dynamic Client Registration (RFC7591)
Consulte o [Dynamic Client Registration do Open Finance Brasil](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html)
### 3.3. Salvando o Token de Dynamic Registration Management (RFC7592)
Consulte o [Dynamic Client Registration do Open Finance Brasil](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html)
### 3.4. Modificando um cliente usando Dynamic Client Management Token (RFC7592)
Consulte o [Dynamic Client Registration do Open Finance Brasil](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3-ptbr.html)
## 4. Obtendo Acesso aos Recursos dos Clientes
Para todas as opções, incluindo todos os códigos de permissão, consulte o [Consent API](https://openbanking-brasil.github.io/areadesenvolvedor/swagger/swagger_consents_apis.yaml). Os exemplos a seguir são exemplos mínimos, mas funcionais para demonstrar o fluxo de ponta a ponta. Esses exemplos pressupõem que o cliente está se comunicando com um provedor de OpenID, aproveitando o mecanismo de autenticação de endpoint do token ‘tls_client_auth’. Exemplos alternativos estão disponíveis no apêndice.
### 4.1. Pré-requisitos
Esses exemplos **não normativos** presumem que o cliente OAuth descobriu os locais de todos os ‘endpoints’ necessários para se comunicar com os recursos dos bancos do Diretório, incluindo o recurso de consentimento, os recursos de dados e o documento de descoberta de autorização OpenID do Diretório.
### 4.2. Criando Consentimento
btendo um Token de Acesso com escopo ‘consents’Criando um recurso de consentimento
### 4.3. Autorizando Consentimento - Redirecionar

#### 4.3.1. Criar OpenID Connect Request Object
Diferentes métodos de autenticação (private_key_jwt e tls_client_auth) e de encaminhamento do Request Object (com e sem uso de PAR) podem ser suportados pelos Authorization Servers de acordo com a especificação [FAPI-1.0 Part 2 - Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html).Portanto, como reforça o perfil de segurança para o Open Finance Brasil (item 8 da seção 5.2.3 dos [requisitos de segurança para o cliente confidencial](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3-ptbr.html#section-5.2.3)), todas as 4 combinações de métodos devem ser suportados pelos clientes de API.A tabela abaixo reflete os diferentes profiles de segurança e combinações que devem ser suportados por todos os clientes de API (conforme os [profiles certificados pela OIDF para o Open Finance Brasil](https://openid.net/certification/#FAPI_OPs)).
| Perfil da certificação OIDF |
| BR-OB Adv. OP w/ Private Key, PAR |
Todos os requisitos para o OpenID Request Object estão incluídos no [Perfil de Segurança do Open Finance Brasil](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3-ptbr.html). Veja o exemplo com JWS a seguir:
#### 4.3.2. Redirecionar o Usuário ao Authorization Server para Autorização
De acordo com o OpenID Connect Core.
#### 4.3.3. Obtenção de Token de Acesso por Meio de Troca de Código de Autorização
Conforme [RFC 7636 Proof Key for Code Exchange](https://tools.ietf.org/html/rfc7636)
### 4.3.4. Verificação do Status do Recurso de Consentimento
Neste ponto, um TPP pode, opcionalmente, verificar o status da solicitação de consentimento para ver se mudou para totalmente autorizado. Esta etapa não deverá ser necessária para recursos que não requerem consentimento de múltiplos indivíduos, entretanto, para contas comerciais ou contas conjuntas com requisitos de acesso especiais, então pode demorar um pouco para o banco obter as autorizações adicionais necessárias para que esse consentimento seja totalmente autorizado. Os TPPs não devem abusar da verificação do status de consentimento API.
#### 4.3.5. Acesso aos Recursos
Com o token de acesso que foi retornado em 4.3.3, o TPP agora tem a capacidade de chamar os recursos dos clientes.
## Apêndice

### A.1 Concessão de Credenciais de private_key_jwt client

### A.2 Exemplo de Corpo de Objeto de Solicitação Decodificado

### A.3 Exemplo de Decodificação do Corpo de uma Solicitação com Valores de Reivindicação Específicos Sendo Solicitados
Neste exemplo, um cliente está solicitando que o Authorization Server autentique o cliente apenas se a declaração cpf corresponder ao valor fornecido. Os requisitos de processamento para solicitações com um valor ‘cpf’ específico são definidos no Perfil de Segurança do Open Finance Brasil.
### A.4 Exemplo de Decodificação do Corpo de Solicitação de Autenticação CIBA
Neste exemplo, uma solicitação CIBA está sendo feita para solicitar autorização de consentimento usando um id_token emitido como a indicação do proprietário do recurso que o banco deve entrar em contato para obter autorização.

---

# Guia do Usuário > v1.0 - Guia do usuário > Instituição transmissora > [EN] Guia do Usuário para Entidades Transmissoras de Dados (ASPSP)

---
id: 240648549
title: [EN] Guia do Usuário para Entidades Transmissoras de Dados (ASPSP)
version: 2
modified: 2023-12-15T14:51:40.674Z
url: /spaces/OF/pages/240648549/EN+Guia+do+Usu+rio+para+Entidades+Transmissoras+de+Dados+ASPSP
---

## 1. Registering a Bank

### 1.1. Directory Overview
The trust framework services provided by Open Finance Brasil provide all of the discovery services necessary for a TPPs and ASPSPs to interact with each other without being required to validate the authenticity of each others Identity, Authorizations, Consumer Offerings (Apps), APIs or CredentialsAn Authorization Server or AS as defined by [RFC 6749 - The OAuth 2.0 Authorization Framework](https://tools.ietf.org/html/rfc6749) perform several functions in a Data Sharing ecosystem like Open Finance. Please read ensure that the concepts roles and responsibilities defined in the original RFC are well understood before proceeding. In addition please ensure that the concepts, roles and responsibilities defined in [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) and how they extended the concepts defined in RFC 6749 are equally as well understood.
### 1.2. Registering an Authorization Server and OpenID Provider
Banks, typically large banks, will not be a single entity from a technology operations point of view. They may have different brands, security and IT infrastructure for different customer segments or they may have some IT infrastructure that supports multiple brands or customer segments. This means that the technical ecosystem needs to be flexible enough to support a wide variety of Banks Infrastructure Deployments whilst ensuring that the necessary services are discoverable both Third Parties customers that need to interact with it.A flexible model for advertising authentication/authorization services and the resources that are protected by the AuthN and AuthZ is supported by the Directory.
- Customer Friendly Name - This is will be displayed to customers by TPPs and should be recognisable by the Banks Customers Already.
- Customer Friendly Logo - This will be displayed to customers by TPPs to aid brand recognition.
- Description - This may be displayed to customers by TPPs to aid brand recognition.
- Terms of Service - This is a link to the Banks Terms of Service which may be included by TPPs.
- Notification WebHook - Authorization Servers can register a WebHook that will receive pushed updates regarding changes to participants, their software or certificates.
- OpenID Well Known Document Uri - Link to the Authorization Server’s Discovery Document.
A Bank may choose to have one Authorization Server or many provided that it can satisfy the following requirements.
- A customer can recognise the Authorization Server as a place that they would normally Bank with.
- The Authorization Server can issue tokens for the resource and services that a customer or TPP is looking for.
- For transmiting/account holder institutions whose Authorization Server supports more than one brand, it must accept more than one registry (client_ids creation) for the same software statement . If your Authorization Server implementation does not supports this behaviour, it must be suitable to support multiple brands and the registration of brands in the directory must be annotated according to each brand.

### 1.3. Registering Resources
Once a Bank has registered an Authorization Server, it needs to advertise what resources, APIs or Services it can provide authorization for.[Authorization Resources management image]
| Auth Id | Auth Customer Friendly Name | Well Known | Resource | Version |
| --- | --- | --- | --- | --- |
| 1 | Amazing Business Banking | https://auth.business.amazingbank.org.br/.well-known/openid-configuration | consents | 1 |
| 1 | Amazing Business Banking | https://auth.business.amazingbank.org.br/.well-known/openid-configuration | business account information | 1 |
| 1 | Amazing Business Banking | https://auth.business.amazingbank.org.br/.well-known/openid-configuration | payments | 1 |
| 2 | Amazing Banking | https://auth.amazingbank.org.br/.well-known/openid-configuration | consents | 1 |
| 2 | Amazing Banking | https://auth.amazingbank.org.br/.well-known/openid-configuration | account information | 1 |
| 2 | Amazing Banking | https://auth.amazingbank.org.br/.well-known/openid-configuration | account information | 2 |
| 3 | Amazing Banking | https://auth.payments.amazingbank.org.br/.well-known/openid-configuration | payments consents | 1 |
| 3 | Amazing Banking | https://auth.payments.amazingbank.org.br/.well-known/openid-configuration | payments | 1 |
In the above example, Amazing Banking is advertising two services that should be recognisable to customers. “Amazing Business Banking” and “Amazing Banking”. These **may or may not be** directly related to “Brands” as different Banks may need to advertise different authentication services even within a sub brand.In addition the bank advertises what resources each of the Authorization Servers are protecting or offering. In the above example Amazing Banking is supporting both version 1 and version 2 of the account information API and that “Amazing Banking” has two separate authentication and authorization systems for Payments and Account Information .Correctly advertising what resources are offered by each server is important to achieving the scale envisaged by Brasil Open Finance and critical for ensuring that customers can identify their banking service easily and that TPPs can route customers to the correct Authorization Service based on the resources that protected by each service.
## 2. Validating a client registration request
Using OpenID Connect Discovery and the Brasil Open Finance Dynamic Client Registration specification. A TPP can register their application at each of the Authorization Servers available in the ecosystem.
### 2.1. OpenID Connect Registration and OAuth 2.0 Dynamic Client Registration
Please see Open Finance Brasil Dynamic Client Registration Specification for more details:[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Open-Finance-Brasil-OpenID-Connect-Registration-Provisions](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Open-Finance-Brasil-OpenID-Connect-Registration-Provisions)
### 2.2. Software Statement Assertion Processing
Please see Open Finance Brasil Dynamic Client Registration Specification for more details:[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Software-Statement-Assertion](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76709980/EN+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Software-Statement-Assertion)
## 3. Validating an Authorization Request
Please see Open Finance Security Profile for more details:[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76283925/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3#Brasil-Open-Finance-Security-Profile](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76283925/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3#Brasil-Open-Finance-Security-Profile)

---

# Guia do Usuário > v1.0 - Guia do usuário > Instituição transmissora > [PT] Guia do Usuário para Entidades Transmissoras de Dados (ASPSP)

---
id: 240648513
title: [PT] Guia do Usuário para Entidades Transmissoras de Dados (ASPSP)
version: 2
modified: 2023-12-15T14:51:35.712Z
url: /spaces/OF/pages/240648513/PT+Guia+do+Usu+rio+para+Entidades+Transmissoras+de+Dados+ASPSP
---

ASPSP - *Account Servicing Payment Service Provider*
## 1. Registrando um Banco

### 1.1. Visão Geral do Diretório
Os serviços do framework de confiança providos pelo Open Finance Brasil fornecem todos os serviços de descoberta necessários para que instituiçoes transmissores e receptoras interajam entre si, sem que seja preciso validar individualmente a autenticidade de cada participante.Um *Authorization Server* ou AS, conforme definido por [RFC 6749 - The OAuth 2.0 Authorization Framework](https://tools.ietf.org/html/rfc6749), executa várias funções em um ecossistema de compartilhamento de dados como o Open Finance Brasil. Antes de prosseguir, certifique-se de que os conceitos de funções e responsabilidades definidos na RFC original sejam bem compreendidos. Além disso, certifique-se de que os conceitos, funções e responsabilidades definidos no [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e como eles estendem os conceitos definidos no RFC 6749 são igualmente bem compreendidos.
### 1.2. Registrando um Authorization Server e OpenID Provider
Os bancos, geralmente grandes bancos, não serão uma entidade única do ponto de vista das operações de tecnologia. Eles podem ter marcas, segurança e infraestrutura de TI diferentes para diferentes segmentos de clientes, ou podem ter alguma infraestrutura de TI que ofereça suporte a várias marcas ou segmentos de clientes. Isso significa que o ecossistema técnico precisa ser flexível o suficiente para suportar uma ampla variedade de implantações de infraestrutura de bancos, garantindo que os serviços necessários possam ser descobertos por clientes de instituições receptoras que precisam interagir com ele.Um modelo flexível para anunciar serviços de autenticação / autorização e os recursos protegidos pelo AuthN e AuthZ é suportado pelo Diretório.
- Customer Friendly Name - Será exibido aos clientes pelas instituições receptoras, e já deve ser reconhecido pelos clientes do banco.
- Customer Friendly Logo - Será exibido aos clientes pelas instituições receptoras para auxiliar no reconhecimento da marca.
- Description - Isso pode ser exibido aos clientes pelas instituições receptoras para auxiliar no reconhecimento da marca.
- Terms of Service - Este é um link para os Termos de Serviço do banco, que podem ser incluídos pelas instituições receptoras.
- Notification WebHook - Authorization Servers podem registrar um WebHook que receberá atualizações por push sobre as alterações dos participantes, seus softwares ou certificados.
- OpenID Well Known Document Uri - Link para o documento de descoberta do Authorization Server.
Um banco pode optar por ter um *Authorization Server* ou muitos, desde que satisfaça os seguintes requisitos.
- Um cliente pode reconhecer o Authorization Server como um local com o qual normalmente faria interação com o seu banco.
- O Authorization Server pode emitir tokens para os recursos e serviços que um cliente ou insituição receptora está procurando.
- O Authorization Server das instituições transmissoras/detentoras de contas que atenda mais de uma marca deve aceitar mais de um cadastro (criação de client_ids) para um mesmo software statement . Caso a solução de Authorization Server não suporte este comportamento, deverá ser adequado para suportar múltiplas marcas e o cadastramento das marcas no diretório deverá sofrer apontamento de acordo com cada marca.

### 1.3. Registrando Recursos
Depois que um banco registra um *Authorization Server*, ele precisa anunciar para quais recursos, APIs ou serviços ele pode fornecer autorização.[Authorization Resources management image]
| Auth Id | Auth Customer Friendly Name | Well Known | Resource | Version |
| --- | --- | --- | --- | --- |
| 1 | Amazing Business Banking | https://auth.business.amazingbank.org.br/.well-known/openid-configuration | consents | 1 |
| 1 | Amazing Business Banking | https://auth.business.amazingbank.org.br/.well-known/openid-configuration | business account information | 1 |
| 1 | Amazing Business Banking | https://auth.business.amazingbank.org.br/.well-known/openid-configuration | payments | 1 |
| 2 | Amazing Banking | https://auth.amazingbank.org.br/.well-known/openid-configuration | consents | 1 |
| 2 | Amazing Banking | https://auth.amazingbank.org.br/.well-known/openid-configuration | account information | 1 |
| 2 | Amazing Banking | https://auth.amazingbank.org.br/.well-known/openid-configuration | account information | 2 |
| 3 | Amazing Banking | https://auth.payments.amazingbank.org.br/.well-known/openid-configuration | payments consents | 1 |
| 3 | Amazing Banking | https://auth.payments.amazingbank.org.br/.well-known/openid-configuration | payments | 1 |
No exemplo acima, o Amazing Banking está anunciando dois serviços que devem ser reconhecidos pelos clientes. “Amazing Business Banking” e “Amazing Banking”. Estes **podem ou não estar** diretamente relacionados a “Marcas”, pois bancos diferentes podem precisar anunciar serviços de autenticação diferentes, mesmo dentro de uma submarca.Além disso, o banco anuncia quais recursos cada um dos servidores de autorização está protegendo ou oferecendo. No exemplo acima, o Amazing Banking é compatível com a versão 1 e a versão 2 da API de informações da conta, e o “Amazing Banking” tem dois sistemas separados de autenticação e autorização para Pagamentos e Informações da conta.Anunciar corretamente quais recursos são oferecidos por cada servidor é importante para atingir a escala prevista pelo Open Finance Brasil, além de ser fundamental para garantir que os clientes possam identificar seu serviço bancário facilmente e que as instituições receptoras possam encaminhar os clientes para o *Authorization Server* correto com base nos recursos protegidos por cada serviço.
## 2. Validando uma Solicitação de Registro de Cliente
Usando o OpenID Connect Discovery e a especificação de Dynamic Client Registration (DCR) do Open Finance Brasil. Uma instituição receptora pode registrar seu aplicativo em cada um dos *Authorization Servers* disponíveis no ecossistema.
### 2.1. Registro OpenID Connect e OAuth 2.0 Dynamic Client Registration
Consulte a Especificação de Dynamic Client Registration (DCR) do Open Finance Brasil para obter mais detalhes:[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251331/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Provisionamentos-do-OpenID-Connect-Discovery-do-Open-Finance-Brasil](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251331/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Provisionamentos-do-OpenID-Connect-Discovery-do-Open-Finance-Brasil) .
### 2.2. Processamento de declaração de software (Software Statement Assertion)
Consulte a Especificação de Dynamic Client Registration (DCR) do Open Finance Brasil para obter mais detalhes:[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251331/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Declara%C3%A7%C3%A3o-de-Software](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251331/PT+Open+Finance+Brasil+Financial-grade+API+Dynamic+Client+Registration+1.0+Implementers+Draft+3#Declara%C3%A7%C3%A3o-de-Software)
## 3. Validando um Pedido de Autorização
Consulte o Perfil de Segurança do Open Finance Brasil (Financial-grade API Security Profile) para obter mais detalhes:[https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251182/PT+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3#Profile-de-Seguran%C3%A7a-para-o-Open-Finance-Brasil](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251182/PT+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3#Profile-de-Seguran%C3%A7a-para-o-Open-Finance-Brasil)

---

# Introdução - Segurança > Histórico da página - Introdução - Segurança

---
id: 240648429
title: Histórico da página - Introdução - Segurança
version: 2
modified: 2023-12-15T14:51:03.462Z
url: /spaces/OF/pages/240648429/Hist+rico+da+p+gina+-+Introdu+o+-+Seguran+a
---

## Change log
 
| De / Para - Versão | Item de trabalho (Conteúdo Motivador) | Demandante | O que foi alterado? | Motivador |
| --- | --- | --- | --- | --- |
| | | | | |
| | | | | |

---

# Introdução - Segurança > v1.0 - Introdução - Segurança

---
id: 240648385
title: v1.0 - Introdução - Segurança
version: 2
modified: 2023-12-15T14:50:57.106Z
url: /spaces/OF/pages/240648385/v1.0+-+Introdu+o+-+Seguran+a
---

Esta seção tem como finalidade auxiliar na auto avaliação aos cumprimentos dos requisitos de segurança da informação relacionados a autorização e autenticação de APIs e End-Users, emissão de certificados digitais e requisitos para o *onboarding* no Diretório de participantes para as Instituições participantes do Open Finance Brasil.As instituições participantes do Open Finance Brasil possuem a obrigação de acompanhar a edição e a revogação de eventuais normas com impacto no tema de forma a estar permanentemente em dia com as determinações legais. Compõem, de forma não exaustiva, o rol de atos normativos cuja observância é essencial pelas instituições participantes do Open Finance Brasil:
| Normativa |
| --- |
| Resolução Conjunta CMN/BCB nº 1, de 2020 |
| Resolução CMN nº 4.658, de 2021 |
| Circular BCB nº 3.909, de 2018 |
| Resolução BCB nº 37, de 4 de Novembro de 2020 |
| Resolução BCB n° 32 de 29/10/2020 |
| Lei Geral de Proteção de Dados Pessoais (LGPD - Lei nº 13.709, de 2018) |
Estas especificações baseiam-se, referenciam, e complementam, quando aplicável, os seguintes documentos:
| Referência |
| --- |
| BCP 195/RFC 7525 |
| Owasp API Top 10 |
| Sans Top 25 Software Errors |
| CWE Top 25 Software Weaknesses |
Além desse guia, foi elaborado um checklist para auxiliar os participantes do Open Finance Brasil a alcançar um nível adequado de Segurança da Informação, esse checklist pode ser baixado em formato Word a seguir.[Download - Autoavaliação dos requisitos de SI - 1.1.2.docx](https://openfinancebrasil.atlassian.net/wiki/download/attachments/7997308/20230515_Autoavalia%C3%A7%C3%A3o%20dos%20requisitos%20de%20SI%20-%201.1.2.docx?api=v2)
[Download - Documento auxiliar - Requisitos de SI- V1.10.docx](https://openfinancebrasil.atlassian.net/wiki/download/attachments/7997308/20230515_Documento%20auxiliar%20-%20Requisitos%20de%20SI-%20V1.10.docx?api=v2)

---

# Padrão de Certificados > Histórico da página - Padrão de Certificados > [EN] Padrão de Certificados Open Finance Brasil 2.0

---
id: 240650099
title: [EN] Padrão de Certificados Open Finance Brasil 2.0
version: 2
modified: 2023-12-15T14:54:29.324Z
url: /spaces/OF/pages/240650099/EN+Padr+o+de+Certificados+Open+Finance+Brasil+2.0
---

## Foreword
Este documento também está disponível em português.The Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.
## Objective
Specify the set of necessary certificates required by participating organizations in Open Finance Brasil to ensure interoperability for authentication, confidentiality, integrity and non-repudiation among participants, as well as for users and consumers of these entities. The audience of this specification are the entities participating in Open Finance Brasil that will issue certificates to authenticate themselves with other entities, as well as offering their customers a secure authentication channel.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2][ISODIR2]. These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the types of certificates required for:
- Mutually authenticate (MTLS - Mutual TLS) participants' applications;
- Message Signature (JWS - JSON Web Signature) applications to ensure authenticity and non-repudiation of messages between participants;
- Provide a safe and reliable channel for Open Finance Brasil customers;
- Authenticate participants in the Open Finance Brasil Participant Directory.

## 2. Normative refences
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.
- [ISODIR2] - ISO/IEC Directives Part 2 [ISODIR2]: https://www.iso.org/sites/directives/current/part2/index.xhtml
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile: https://datatracker.ietf.org/doc/html/rfc5280
- [RFC7519] - JSON Web Token (JWT) [RFC7519]: https://tools.ietf.org/html/rfc7519
- [RFC7515] - JSON Web Signature (JWS) [RFC7515] : https://datatracker.ietf.org/doc/html/rfc7515
- [RFC7591] - OAuth 2.0 Dynamic Client Registration Protocol [RFC7591]: https://tools.ietf.org/html/rfc7591
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol [RFC7592]: https://tools.ietf.org/html/rfc7592
- [BCP195] - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS) [BCP195]: https://tools.ietf.org/html/bcp195
- [RFC8705] - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens [RFC8705]: https://tools.ietf.org/html/rfc8705
- [OFB-FAPI] - Open Finance Brasil Financial-grade API Security Profile 1.0 [OFB-FAPI]: https://github.com/OpenBanking-Brasil/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html
- [OFB-FAPI-DCR] - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0 [OFB-FAPI-DCR]: [EN] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3
- [DOC-ICP-01] - DECLARAÇÃO DE PRÁTICAS DE CERTIFICAÇÃO DA AUTORIDADE CERTIFICADORA RAIZ DA ICP-BRASIL: https://www.gov.br/iti/pt-br/centrais-de-conteudo/doc-icp-01-v-5-2-dpc-da-ac-raiz-da-icp-brasil-pdf
- [RFC6749] - The OAuth 2.0 Authorization Framework [RFC6749]: https://tools.ietf.org/html/rfc6749
- [BCB-IN134] - Manual de Segurança do Open Finance: https://www.in.gov.br/web/dou/-/instrucao-normativa-bcb-n-134-de-22-de-julho-de-2021-3345585364
- [RFC2818] - HTTP Over TLS: https://datatracker.ietf.org/doc/html/rfc2818
- [RFC5246] - The Transport Layer Security (TLS) Protocol Version 1.2 https://www.rfc-editor.org/rfc/rfc5246.txt

## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC5280], [BCP195], [RFC8705], e ISO29100 apply.
## 4. Glossary

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- HTTP - Hyper Text Transfer Protocol
- ICP - Infraestrutura de Chave Públicas Brasileira
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security
- mTLS - Mutual Transport Layer Security

## 5. Open Finance Brasil Certificate Standards

### 5.1. Introduction
The Open Finance Brazil ecosystem makes use of chains of certificates and TLS protocol to guarantee the confidentiality, authentication and integrity of the communication channel used by the APIs of the participating organizations, as well as the customers of each of the participants.The certificates used by Open Finance Brasil are also required to authenticate applications through oAuth 2.0 mTLS or private_key_jwt, in addition to being used to perform the payload signature using JWS. Another important attribution of certificates is to authenticate and present a secure channel to the end user in the act of authentication and use of services provided by the participating organizations.
### 5.2. ICP-Brasil Certificates
Certificates issued by Certifying Authorities authorized by ICP-Brasil are only used for communication between entities participating in the Open Finance Brasil ecosystem.The certificate issuing and revocation processes are responsibility of the Certifate Authorities themselves, being regulated by Certification Practice Statements, and supervised by the Management Committee of the Brazilian Public Key Infrastructure (Comitê Gestor da Infraestrutura de Chaves Públicas Brasileira).The practices, processes, availability and values practiced by the Certification Authorities are not responsibility of the Initial Structure of Open Finance Brasil.**Algorithms**All certificates issued by ICP-Brasil must have the following characteristics:
- Type A of ICP-Brasil;
- Key Algorithms: RSA 2048 bits;
- Message Digest: SHA 256 bits.
**Participating Certificate Authorities**The following certifying authorities carried out the onboard process for Open Finance Brasil and are authorized to issue Open Finance Brasil certificates using the level 1 certificates listed here:
- CertiSign (Chain v5 e v10)
- Serasa (Chain v5 e v10)
- Serpro (Chain v5 e v10)
- Soluti (Chain v5 e v10)
Only the certificates indicated with "`Situação: válido`" (which mean "`status: valid`") in these ITI repositories referenced above, which are Chain v5 and v10, should be accepted by the servers of the Open Finance Brasil ecosystem.
#### 5.2.1. Server Certificate
The Server Certificate must be issued to protect and authenticate the TLS channel used by the APIs that will be consumed by client applications of organizations participating in Open Finance.The certificate standard used must follow the existing certificate issuing practices of "CERTIFICATE FOR WEB SERVER - ICP-Brasil".The server certificate shall be sent with the intermediate chain, according to [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/items%207.4.2).
#### 5.2.2. Client Certificate
Client Application Certificates (Transport) are used to authenticate the mTLS channel and to authenticate the client application through oAuth2.0 mTLS or private_key_jwt, according to the application registration performed by the Dynamic Client Registration process with the transmitting organization. Regarding mTLS, the client certificate shall be sent with the intermediate chain, according to [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/items%207.4.2%20and%207.4.6).To issue a Client Certificate, the participating organization in Open Finance Brasil must register the application in the Directory Service through the Software Statement Assertion issue process, and thus have already obtained the Software Statement ID value.
##### 5.2.2.1. Open Finance Brasil Attributes

- serialNumber: National Register of Legal Personnel (CNPJ) of the legal entity holding the certificate and associated with the UID attribute and Software Statement ID, during validation with the Directory Service of Open Finance Brasil;
- organizationIdentifier: Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil; For certificates issued until August 31 the field used for this information is organizationalUnitName .
- UID: Software Statement ID registered in the Directory Service of Open Finance Brasil and belonging to the CNPJ and Participant Code.
The Client Certificate must be issued through the V10 chain, and must contain the following attributes:**Distinguished Name**
- businessCategory (OID 2.5.4.15): Type of business category, which must contain: "Private Organization" or "Government Entity" or "Business Entity" or "Non-Commercial Entity"
- jurisdictionCountryName (OID: 1.3.6.1.4.1.311.60.2.1.3): BR
- serialNumber (OID 2.5.4.5): CNPJ
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): Company Name
- stateOrProvinceName (OID 2.5.4.8): Federation unit of the certificate holder's physical address
- localityName (OID 2.5.4.7): City of the holder's physical address
- organizationIdentifier (OID 2.5.4.97): Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil. *For certificates issued until August 31: organizationalUnitName (OID 2.5.4.11): Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil*
- UID (OID 0.9.2342.19200300.100.1.1): Software Statement ID generated by Open Finance Brasil Directory
- commonName (OID 2.5.4.3): FQDN or Wildcard
**Certificate Extensions**
- keyUsage: critical,digitalSignature,keyEncipherment
- extendedKeyUsage: clientAuth
**Subject Alternative Name**
- dNSName: FQDN or Wildcard

#### 5.2.3. Signature Certificate
Signature Certificates are used to perform payload signature through the use of JWS (JSON Web Signature).
##### 5.2.3.1. Open Finance Brasil Attributes Present in the Certificate

- UID: Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil;
- commonName: Company Name registered in the Directory Service of Open Finance Brasil and belonging to the CNPJ and Participant Code.
The Signature Certificate must be issued through the V5 chain, and must contain the following attributes:**Distinguished Name**
- UID (OID 0.9.2342.19200300.100.1.1): Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brazil
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): ICP-Brasil
- organizationalUnitName (OID 2.5.4.11): Certificate Authority Name
- organizationalUnitName (OID 2.5.4.11): CNPJ of the Registration Authority
- organizationalUnitName (OID 2.5.4.11): Type of identification used (in person, videoconference or digital certificate)
- commonName (OID 2.5.4.3): Company Name
**Certificate Extensions**
- keyUsage: critical,digitalSignature,nonRepudiation
**Subject Alternative Name**
- otherName (OID 2.16.76.1.3.2 - ICP-Brasil): Name of the person responsible for the certificate
- otherName (OID 2.16.76.1.3.3 - ICP-Brasil): National Register of Legal Entities (CNPJ) of the legal entity holding the certificate;
- otherName (OID 2.16.76.1.3.4 - ICP-Brasil): Responsible for the certificate of legal entity holding the certificate (date of birth, CPF, PIS/PASEP/CI, RG);
- otherName (OID 2.16.76.1.3.7 - ICP-Brasil): INSS Specific Registry Number (CEI) of the legal entity holding the certificate.

#### 5.2.4. Front-End Certificates
Front-End certificates are utilized to make services available, generally web pages, using TLS, that are acessible by the end users. Due to their function, and in order to guarantee better interoperability, those certificates must be of the type EV (Extended Validation) and must be generated by a valid certificate authority, following definitions of RFC 5280 e RFC 2818, in conformance with WebTrust principles and criteria.
#### 5.2.5. About certificates for exchanging information between authorized institutions and partners (non-participating)
According to section IV of Joint Resolution No. 1 of May 4, 2020, the establishment of bilateral partnerships between authorized institutions and partners is an arrangement provided for in the regulation which must observe, where applicable, the same standards and certificates requirements that are applicable to exchange of information between participating institutions.In accordance with §2 of Art. 10 of Provisional Measure 2200-2 of August 24, 2001 and with the provisions of item 3.12 in BCB Normative Instruction No. 134, for bilateral communication between institutions and partners, the use is authorized, by mutual agreement between the parties, of a private PKI, provided that the requirements of this *profile for security certificates* are observed, including their formatting, algorithms and established attributes.The values for filling in the attributes required in this specification, but not applicable to the partner, should be defined in common agreement between the authorized institution and the partner, which does not exempt the authorized institution from the responsibility for filling it in properly.
## 6. Acknowledgements
Thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- João Rodolfo Vieira (Itaú)
- José Michael Dias (Grupo Pan)
- Marcos Rodrigues (Itaú)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## 7. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
## 8. Appendix

### 8.1. Configuration Template for Client Certificate - OpenSSL - For certificates issued until August 31, 2022

| [req]
default_bits = 2048
default_md = sha256
encrypt_key = yes
prompt = no
string_mask = nombstr
distinguished_name = client_distinguished_name
req_extensions = req_cert_extensions
 
[ client_distinguished_name ]
businessCategory = <type of organization>
jurisdictionCountryName = BR
serialNumber = <CNPJ>
countryName = BR
organizationName = <Company Name>
stateOrProvinceName = <UF>
localityName = <City>
organizationalUnitName = <Participant Code>
UID = <Software Statement ID issued by the Directory>
commonName = <FQDN|Wildcard>
 
[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth
 
[ alt_name ]
DNS = <FQDN|Wildcard> |

### 8.2. Configuration Template for Client Certificate - OpenSSL - For certificates issued after August 31, 2022

| oid_section = OIDs
 
[req]
default_bits = 2048
default_md = sha256
encrypt_key = yes
prompt = no
string_mask = nombstr
distinguished_name = client_distinguished_name
req_extensions = req_cert_extensions
 
[ OIDs ]
organizationIdentifier = 2.5.4.97
 
[ client_distinguished_name ]
businessCategory = <type of organization>
jurisdictionCountryName = BR
serialNumber = <CNPJ>
countryName = BR
organizationName = <Company Name>
stateOrProvinceName = <UF>
localityName = <City>
organizationIdentifier = OFBBR-<Participant Code>
UID = <Software Statement ID issued by the Directory>
commonName = <FQDN|Wildcard>
 
[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth
 
[ alt_name ]
DNS = <FQDN|Wildcard> |

### 8.3. Configuration Template for Signature Certificate - OpenSSL

| [req]
default_bits = 2048
default_md = sha256
encrypt_key = yes
prompt = no
string_mask = nombstr
distinguished_name = client_distinguished_name
req_extensions = req_cert_extensions
 
[ client_distinguished_name ]
UID = <Participant Code>
countryName = BR
organizationName = ICP-Brasil
0.organizationalUnitName = <Certificate Authority>
1.organizationalUnitName = <CNPJ of the Registration Authority>
2.organizationalUnitName = <Validation type>
commonName = <Company Name>
 
[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,nonRepudiation
 
[ alt_name ]
otherName.0 = 2.16.76.1.3.2;PRINTABLESTRING:<Name of the person responsible for the organization>
otherName.1 = 2.16.76.1.3.3;PRINTABLESTRING:<CNPJ>
otherName.2 = 2.16.76.1.3.4;PRINTABLESTRING:<CPF/PIS/RF of the responsible person>
otherName.3 = 2.16.76.1.3.7;PRINTABLESTRING:<INSS Number> |

### 8.4. Endpoints vs Certificate type and mTLS requirements
Below we present which endpoints can be published utilizing the EV certificate as consent authentication and the endpoints of private/bussiness API authentication using the ICP certificate. You will also be able to check which endpoints must protect its connections using mTLS.ASPSP may choose the certificate that should be adopted for Open Data endpoints, which, by nature, are publicly accessible.
| Table 1 | | | | |
| OFB Phase | group | endpoint | certificate type | mTLS |
| NA | OIDC | .well-known/openid-configuration | EV or ICP WEB SSL | |
| NA | OIDC | jwks_uri | EV or ICP WEB SSL | |
| NA | OIDC | authorization_endpoint | EV | |
| NA | OIDC | token_endpoint | ICP WEB SSL | Required |
| NA | OIDC | userinfo_endpoint | ICP WEB SSL | Required |
| NA | OIDC | pushed_authorization_request_endpoint | ICP WEB SSL | Required |
| NA | DCR | registration_endpoint | ICP WEB SSL | Required |
| NA | OIDC | revocation_endpoint | ICP WEB SSL | Required |
| 2 | Consentimentos | /consents/* | ICP WEB SSL | Required |
| 2 | Resources | /resources/* | ICP WEB SSL | Required |
| 2 | Dados | /customers/* | ICP WEB SSL | Required |
| 2 | Cartão | /credit-cards-accounts/* | ICP WEB SSL | Required |
| 2 | Contas | /accounts/* | ICP WEB SSL | Required |
| 2 | Empréstimos | /loans/* | ICP WEB SSL | Required |
| 2 | Financiamentos | /financings/* | ICP WEB SSL | Required |
| 2 | Adiantamento | /unarranged-accounts-overdraft/* | ICP WEB SSL | Required |
| 2 | Direitos Creditórios | /invoice-financings/* | ICP WEB SSL | Required |
| 3 | Pagamentos | /payments/* | ICP WEB SSL | Required |
| 4 | Câmbio | /exchanges/* | ICP WEB SSL | Required |
| 4 | Investimentos | /credit-fixed-incomes/* | ICP WEB SSL | Required |

## 9. Open Finance Client Certificate Subject DN Pattern - After January 19, 2023 {#subjectDNtemplates}
On January 19, 2023 the sequence and encoding of the Subject DN used in Open Finance Client Certificates was standardized. Below is determined the sequence and coding of how the attributes of the certificates should be presented in the Subject DN.The coexistence period between the different types of Subject DN must be considered, so the participants of the ecosystem should not implement blocking controls that limit the use of only certificates with the Subject DN standardized below. Participants must ensure that the other DN standards already in use continue to function until the end of the coexistence period, a date yet to be determined.Special attention is required from the participants during the Subject DN generation process, as below are presented Subject DN and RDN formats. The Ecosystem expects the use of RDN in compliance with RFC4514.When in doubt:
- check the JWKS of your `software-id` application
- check the KID of the certificate you want the Subject DN for, customize the URL and access: `https://keystore.directory.openbankingbrasil.org.br/<org-id>/<software-ID>/transport.jwks`
`Example: https://keystore.directory.openbankingbrasil.org.br/9c721898-9ce0-50f1-bf85-05075557850b/793c382e-edb1-4a64-b5c5-9e27366099b9/transport.jwks`
- search for the KID of the certificate, then search for Claim: x5dn

### 9.1. Public Key of Certificate Example:
[https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/wdHeYDz0v4m9tzxpNjsfovbl1fKCFAUvsSIs-ljM4xU.pem](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/wdHeYDz0v4m9tzxpNjsfovbl1fKCFAUvsSIs-ljM4xU.pem)
### 9.2. Example Subject Distinguished Name of the Certificate - Human readable:

| subject=businessCategory = Private Organization, jurisdictionC = BR, serialNumber = 43142666000197, C = BR, O = Chicago Advisory Partners, ST = SP, L = Sao Paulo, organizationIdentifier = OFBBR-d7384bd0-842f-43c5-be02-9d2b2d5efc2c, UID = bc97b8f0-cae0-4f2f-9978-d93f0e56a833, CN = web.conftpp.directory.openbankingbrasil.org.br |

### 9.3. Relative Distinguished Name (RDN) - Human readable:

| subject=CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,organizationIdentifier=OFBBR-d7384bd0-842f-43c5-be02-9d2b2d5efc2c,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,serialNumber=43142666000197,jurisdictionC=BR,businessCategory=Private Organization |

### 9.4. Relative Distinguished Name (RDN) using OID - ANS.1:

| subject=2.5.4.3=#0C2E7765622E636F6E667470702E6469726563746F72792E6F70656E62616E6B696E6762726173696C2E6F72672E6272,0.9.2342.19200300.100.1.1=#0C2462633937623866302D636165302D346632662D393937382D643933663065353661383333,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,2.5.4.7=#0C0953616F205061756C6F,2.5.4.8=#0C025350,2.5.4.10=#0C194368696361676F2041647669736F727920506172746E657273,2.5.4.6=#13024252,2.5.4.5=#130E3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C1450726976617465204F7267616E697A6174696F6E |

### 9.5. Subject DN in RDN - According to RFC4514 - Open Finance Brazil Ecosystem Standard:

| CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0c2a4f464242522d64373338346264302d383432662d343363352d626530322d396432623264356566633263,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,2.5.4.5=#130e3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0c1450726976617465204f7267616e697a6174696f6e |

### 9.6. Table with RDN and details of the OIDs and Encodings.

| RDN Order | OID | Attribute | ASN.1 - Bit String | Enconding |
| --- | --- | --- | --- | --- |
| 1 | 2.5.4.3 | CN | #0C | UTF8 |
| 2 | 0.9.2342.19200300.100.1.1 | UID | #0C | UTF8 |
| 3 | 2.5.4.97 | organizationIdentifier | #0C | UTF8 |
| 4 | 2.5.4.7 | L | #0C | UTF8 |
| 5 | 2.5.4.8 | ST | #0C | UTF8 |
| 6 | 2.5.4.10 | O | #0C | UTF8 |
| 7 | 2.5.4.6 | C | #13 | PrintableString |
| 8 | 2.5.4.5 | serialNumber | #13 | PrintableString |
| 9 | 1.3.6.1.4.1.311.60.2.1.3 | jurisdictionCountryName | #13 | PrintableString |
| 10 | 2.5.4.15 | businessCategory | #0C | UTF8 |

---

# Padrão de Certificados > Histórico da página - Padrão de Certificados > [PT] Padrão de Certificados Open Finance Brasil 2.0

---
id: 240650029
title: [PT] Padrão de Certificados Open Finance Brasil 2.0
version: 2
modified: 2023-12-15T14:54:25.404Z
url: /spaces/OF/pages/240650029/PT+Padr+o+de+Certificados+Open+Finance+Brasil+2.0
---

## Prefácio
This document is also available in English.A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. A Estrutura Inicial do Open Finance Brasil não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.
## Objetivo
Especificar o conjunto de certificados necessários que devem ser utilizados pelas entidades participantes do Open Finance Brasil para garantir interoperabilidade para autenticação, confidencialidade, integridade e não repúdio entre os participantes, bem como para os usuários e consumidores destas entidades. O público desta especificação são entidades participantes do Open Finance Brasil que necessitam fazer a emissão de certificados para se autenticar junto a outras entidades, bem como oferecer a seus clientes um canal de autenticação seguro.
## Convenções Notacionais
As palavras-chave "*deve*" (shall), "*não deve*" (shall not), "*deveria*" (should), "*não deveria*" (should not) e "*pode*" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2][ISODIR2] observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 1. Escopo
Este documento especifica os tipos de certificados necessários para:
- Autenticar mutuamente (MTLS - Mutual TLS) as aplicações dos participantes;
- Assinatura de Mensagens (JWS - JSON Web Signature) de aplicações para garantir a autenticidade e não repúdio de mensagens entre os participantes;
- Apresentar um canal seguro e confiável para clientes do Open Finance Brasil;
- Autenticar participantes no Diretório de participantes do Open Finance Brasil.

## 2. Referências Normativas
Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.
- [ISODIR2] - ISO/IEC Directives Part 2 [ISODIR2]: https://www.iso.org/sites/directives/current/part2/index.xhtml
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile: https://datatracker.ietf.org/doc/html/rfc5280
- [RFC7519] - JSON Web Token (JWT) [RFC7519]: https://tools.ietf.org/html/rfc7519
- [RFC7515] - JSON Web Signature (JWS) [RFC7515] : https://datatracker.ietf.org/doc/html/rfc7515
- [RFC7591] - OAuth 2.0 Dynamic Client Registration Protocol [RFC7591]: https://tools.ietf.org/html/rfc7591
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol [RFC7592]: https://tools.ietf.org/html/rfc7592
- [BCP195] - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS) [BCP195]: https://tools.ietf.org/html/bcp195
- [RFC8705] - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens [RFC8705]: https://tools.ietf.org/html/rfc8705
- [OFB-FAPI] - Open Finance Brasil Financial-grade API Security Profile 1.0 [OFB-FAPI]: https://github.com/OpenBanking-Brasil/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html
- [OFB-FAPI-DCR] - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0 [OFB-FAPI-DCR]: [PT] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3
- [DOC-ICP-01] - DECLARAÇÃO DE PRÁTICAS DE CERTIFICAÇÃO DA AUTORIDADE CERTIFICADORA RAIZ DA ICP-BRASIL: https://www.gov.br/iti/pt-br/centrais-de-conteudo/doc-icp-01-v-5-2-dpc-da-ac-raiz-da-icp-brasil-pdf
- [RFC6749] - The OAuth 2.0 Authorization Framework [RFC6749]: https://tools.ietf.org/html/rfc6749
- [BCB-IN134] - Manual de Segurança do Open Finance: https://www.in.gov.br/web/dou/-/instrucao-normativa-bcb-n-134-de-22-de-julho-de-2021-3345585364
- [RFC2818] - HTTP Over TLS: https://datatracker.ietf.org/doc/html/rfc2818
- [RFC5246] - The Transport Layer Security (TLS) Protocol Version 1.2 https://www.rfc-editor.org/rfc/rfc5246.txt

## 3. Termos e Definições
Para o propósito deste documento os termos definidos na [RFC5280], [BCP195], [RFC8705], e ISO29100 são aplicáveis.
## 4. Glossário

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- HTTP - Hyper Text Transfer Protocol
- ICP - Infraestrutura de Chave Públicas Brasileira
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security
- mTLS - Mutual Transport Layer Security
- subjectDN – Subject Distinguished Name
- RDN – Relative Distinguished Name

## 5. Padrão de Certificados Open Finance Brasil

### 5.1. Introdução
O ecossistema do Open Finance Brasil faz uso de cadeias de certificados e protocolo TLS para garantir a confidencialidade, autenticação e integridade do canal de comunicação utilizado pelas APIs das instituições participantes, bem como dos clientes de cada um dos participantes.Os certificados utilizados pelo Open Finance Brasil também são necessários para autenticar as aplicações através do oAuth 2.0 mTLS ou private_key_jwt, além de também servirem para realizar a assinatura de payload pelo uso de JWS. Outra atribuição importante dos certificados é autenticar e apresentar um canal seguro para o usuário final no ato de autenticação e uso dos serviços prestados pela entidade participante.
### 5.2. Certificados ICP-Brasil
Os certificados emitidos pelas Autoridades Certificadoras autorizadas pelo ICP-Brasil são utilizados apenas na comunicação entre as entidades participantes do ecossistema do Open Finance Brasil.Os processos de emissão e revogação dos certificados são de responsabilidade das próprias Autoridades Certificadores, sendo regulamentados por Declarações de Prática de Certificação, e supervisionadas pelo Comitê Gestor da Infraestrutura de Chaves Públicas Brasileira.As práticas, processos, disponibilização e valores praticados pelas Autoridades Certificadoras não são de responsabilidade do Estrutura Inicial do Open Finance Brasil.**Algoritmos**Todos os certificados emitidos junto ao ICP-Brasil devem possuir as seguintes características:
- Tipo A do ICP-Brasil;
- Algoritmo de Chaves: RSA 2048 bits;
- Message Digest: SHA 256 bits.

#### 5.2.1. Certificado Servidor
O Certificado Servidor deve ser emitido para proteger e autenticar o canal TLS utilizado pelas APIs que serão consumidas pelas aplicações cliente de entidades participantes do Open Finance.O padrão de certificado utilizado deve seguir as práticas de emissão de certificados existentes de "CERTIFICADO PARA SERVIDOR WEB - ICP-Brasil".O certificado de servidor precisa ser enviado com a cadeia intermediária, conforme [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/itens%207.4.2).
#### 5.2.2. Certificado Cliente
Os Certificados de Aplicação Cliente (Transporte) são utilizados para autenticar o canal mTLS e para realizar a autenticação da aplicação cliente através de oAuth2.0 mTLS ou private_key_jwt, de acordo com o cadastro da aplicação realizado pelo processo de Dynamic Client Registration junto à entidade transmissora. Sobre o mTLS, o certificado cliente precisa ser enviado com a cadeia intermediária, conforme [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/itens%207.4.2%20e%207.4.6).Para emissão de Certificado Cliente é necessário que a instituição participante do Open Finance Brasil tenha realizado o cadastro da aplicação no Serviço de Diretório, através do processo de emissão de Software Statement Assertion, e com isso já tenha obtido o valor de Software Statement ID.
##### 5.2.2.1. Atributos Open Finance Brasil

- serialNumber: Cadastro Nacional de Pessoal Jurídica (CNPJ) da pessoa jurídica titular do certificado e associado ao atributo UID e Software Statement ID, durante validação junto ao Serviço de Diretório do Open Finance Brasil;
- organizationIdentifier: Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil; Para certificados emitidos até 31 de Agosto de 2022 o campo utilizado para essa informação era o organizationalUnitName.
- UID: Software Statement ID cadastrado no Serviço de Diretório do Open Finance Brasil e pertencente ao CNPJ e Código de Participante.
O Certificado Cliente deve ser emitido através de cadeia V10, e deve obrigatoriamente conter os seguintes atributos:**Distinguished Name**
- businessCategory (OID 2.5.4.15): Tipo de categoria comercial, devendo conter: "Private Organization" ou "Government Entity" ou "Business Entity" ou "Non-Commercial Entity"
- jurisdictionCountryName (OID: 1.3.6.1.4.1.311.60.2.1.3): BR
- serialNumber (OID 2.5.4.5): CNPJ
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): Razão Social
- stateOrProvinceName (OID 2.5.4.8): Unidade da federação do endereço físico do titular do certificado
- localityName (OID 2.5.4.7): Cidade do endereço físico do titular
- organizationIdentifier (OID 2.5.4.97): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil. Para certificados emitidos até 31 Agosto de 2022: organizationalUnitName (OID 2.5.4.11): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil
- UID (OID 0.9.2342.19200300.100.1.1): Software Statement ID gerado pelo Diretório do Open Finance Brasil
- commonName (OID 2.5.4.3): FQDN ou Wildcard
**Certificate Extensions**
- keyUsage: critical,digitalSignature,keyEncipherment
- extendedKeyUsage: clientAuth
**Subject Alternative Name**
- dNSName: FQDN ou Wildcard

#### 5.2.3. Certificado de Assinatura
Os Certificados de Assinatura são utilizados para realizar assinatura do payload através do uso de JWS (JSON Web Signature).
##### 5.2.3.1. Atributos Open Finance Brasil Presentes no Certificado

- UID: Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil;
- commonName: Razão Social cadastrado no Serviço de Diretório do Open Finance Brasil e pertencente ao CNPJ e Código de Participante.
O Certificado de Assinatura deve ser emitido através de cadeia V5, e deve obrigatoriamente conter os seguintes atributos:**Distinguished Name**
- UID (OID 0.9.2342.19200300.100.1.1): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): ICP-Brasil
- organizationalUnitName (OID 2.5.4.11): Nome da Autoridade Certificadora
- organizationalUnitName (OID 2.5.4.11): CNPJ da Autoridade de Registro
- organizationalUnitName (OID 2.5.4.11): Tipo de identificação utilizada (presencial, videoconferência ou certificado digital)
- commonName (OID 2.5.4.3): Nome da Razão Social
**Certificate Extensions**
- keyUsage: critical,digitalSignature,nonRepudiation
**Subject Alternative Name**
- otherName (OID 2.16.76.1.3.2 - ICP-Brasil): Nome do responsável pelo certificado
- otherName (OID 2.16.76.1.3.3 - ICP-Brasil): Cadastro Nacional de Pessoa Jurídica (CNPJ) da pessoa jurídica titular do certificado;
- otherName (OID 2.16.76.1.3.4 - ICP-Brasil): Responsável pelo certificado de pessoa jurídica titular do certificado (data de nascimento, CPF, PIS/PASEP/CI, RG);
- otherName (OID 2.16.76.1.3.7 - ICP-Brasil): Número do Cadastro Especifico do INSS (CEI) da pessoa jurídica titular do certificado.

#### Autoridades Certificadoras Participantes {#AutoridadesCertificadorasParticipantes}
As seguintes autoridades certificadoras realizaram o processo de integração ao Open Finance Brasil e estão habilitadas para realizar a emissão de certificados do Open Finance Brasil utilizando para tal os certificados nível 1 aqui listados:
- CertiSign (Cadeia v5 e v10)
- Serasa (Cadeia v5 e v10)
- Serpro (Cadeia v5 e v10)
- Soluti (Cadeia v5 e v10)
Apenas deverá ser aceito certificados indicados com "`Situação: válido`" nestes repositórios do ITI acima referenciados que são de Cadeia ICP-Brasil v5 e v10.
#### 5.2.4. Certificado para Front-End
Os certificados para Front-End são utilizados para disponibilizar serviços, em geral páginas Web, com uso de TLS, que são acessados pelo usuário final. Dado a sua finalidade, e para garantir maior interoperabilidade, os certificados devem ser do tipo EV (Extended Validation) e devem ser ser gerados através de uma autoridade certificadora válida, seguindo as regras definidas na RFC 5280 e RFC 2818, em conformidade com os princípios e critérios WebTrust.
#### 5.2.5. Sobre certificados para troca de informações entre instituições autorizadas e parceiros
De acordo com a seção IV da Resolução Conjunta nº 1 de 4 de maio de 2020, o estabelecimento de parcerias bilaterais entre instituições autorizadas e parceiros é um arranjo previsto na regulação e que deve observar, no que couber, inclusive os mesmos padrões e certificados de segurança que são aplicáveis para a troca de informações entre as instituições participantes.Em consonância com o §2º do Art. 10 da Medida Provisória 2.200-2 de 24 de agosto de 2001 e com o disposto no item 3.12 na Instrução Normativa BCB Nº 134, para a comunicação bilateral entre as instituições e parceiros fica autorizado o uso, em comum acordo entre as partes, de uma PKI privada desde que observados os requisitos deste *perfil para os certificados segurança*, o que inclui sua formatação, os algoritmos e os atributos estabelecidos.Os valores para o preenchimento dos atributos exigidos nessa especificação, mas não aplicáveis ao parceiro, deveriam ser definidos em comum acordo entre a instituição autorizada e o parceiro, o que não isenta da instituição autorizada a responsabilidade pelo preenchimento.
## 6. Reconhecimento
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro e seguro de dados por meio da formação do Grupo de Trabalho FAPI da OpenID Foundation, o GT-Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- João Rodolfo Vieira (Itaú)
- José Michael Dias (Grupo Pan)
- Marcos Rodrigues (Itaú)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## 7. Informativo
Copyright (c) 2023 Estrutura Inicial do Open Finance Brasil.A Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementações e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do GT-Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
## 8. Apêndice

### 8.1. Modelo de Configuração de Certificado Cliente - OpenSSL *Para certificados emitidos até 31 Agosto de 2022

| [req]
default_bits = 2048
default_md = sha256
encrypt_key = yes
prompt = no
string_mask = nombstr
distinguished_name = client_distinguished_name
req_extensions = req_cert_extensions
 
[ client_distinguished_name ]
businessCategory = <tipo de entidade>
jurisdictionCountryName = BR
serialNumber = <CNPJ>
countryName = BR
organizationName = <Razao Social>
stateOrProvinceName = <UF>
localityName = <Cidade>
organizationalUnitName = <Código de Participante>
UID = <Software Statement ID emitido pelo diretório>
commonName = <FQDN|Wildcard>
 
[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth
 
[ alt_name ]
DNS = <FQDN|Wildcard> |

### 8.2. Modelo de Configuração de Certificado Cliente - OpenSSL *Para certificados emitidos após 31 Agosto 2022

| oid_section = OIDs
 
[req]
default_bits = 2048
default_md = sha256
encrypt_key = yes
prompt = no
string_mask = nombstr
distinguished_name = client_distinguished_name
req_extensions = req_cert_extensions
 
[ OIDs ]
organizationIdentifier = 2.5.4.97
 
[ client_distinguished_name ]
businessCategory = <tipo de entidade>
jurisdictionCountryName = BR
serialNumber = <CNPJ>
countryName = BR
organizationName = <Razao Social>
stateOrProvinceName = <UF>
localityName = <Cidade>
organizationIdentifier = OFBBR-<Código de Participante>
UID = <Software Statement ID emitido pelo diretório>
commonName = <FQDN|Wildcard>
 
[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth
 
[ alt_name ]
DNS = <FQDN|Wildcard> |

### 8.3. Modelo de Configuração de Certificado de Assinatura

| [req]
default_bits = 2048
default_md = sha256
encrypt_key = yes
prompt = no
string_mask = nombstr
distinguished_name = client_distinguished_name
req_extensions = req_cert_extensions
 
[ client_distinguished_name ]
UID = <Código de Participante>
countryName = BR
organizationName = ICP-Brasil
0.organizationalUnitName = <Autoridade Certificadora>
1.organizationalUnitName = <CNPJ da Autoridade Registradora>
2.organizationalUnitName = <Tipo de validação>
commonName = <Razão Social>
 
[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,nonRepudiation
 
[ alt_name ]
otherName.0 = 2.16.76.1.3.2;PRINTABLESTRING:<Nome da pessoal responsável pela entidade>#CNPJ
otherName.1 = 2.16.76.1.3.3;PRINTABLESTRING:<CNPJ>
otherName.2 = 2.16.76.1.3.4;PRINTABLESTRING:<CPF/PIS/RF da Pessoa responsável>
otherName.3 = 2.16.76.1.3.7;PRINTABLESTRING:<Número de INSS> |

### 8.4. Tabela com Endpoints vs Tipo de Certificado e mTLS
Abaixo apresentamos quais endpoints podem ser publicados utilizando certificado EV como autenticação do consentimento e os endpoints de autenticação de APIs privadas/negócios que devem ser publicadas usando certificado ICP. Você também poderá verificar quais endpoints devem proteger suas conexões utilizando mTLS.Fica a critério da instituição a escolha do certificado que deve ser adotado para os endpoints de Dados Abertos, os quais, por natureza, são de acesso público.
| | | | | Table 1 |
| Fase | Grupo | API | Certificado | mTLS |
| NA | OIDC | .well-known/openid-configuration | EV ou ICP WEB SSL | |
| NA | OIDC | jwks_uri | EV ou ICP WEB SSL | |
| NA | OIDC | authorization_endpoint | EV | |
| NA | OIDC | token_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | userinfo_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | pushed_authorization_request_endpoint | ICP WEB SSL | Obrigatório |
| NA | DCR | registration_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | revocation_endpoint | ICP WEB SSL | Obrigatório |
| 2 | Consentimentos | /consents/* | ICP WEB SSL | Obrigatório |
| 2 | Resources | /resources/* | ICP WEB SSL | Obrigatório |
| 2 | Dados | /customers/* | ICP WEB SSL | Obrigatório |
| 2 | Cartão | /credit-cards-accounts/* | ICP WEB SSL | Obrigatório |
| 2 | Contas | /accounts/* | ICP WEB SSL | Obrigatório |
| 2 | Empréstimos | /loans/* | ICP WEB SSL | Obrigatório |
| 2 | Financiamentos | /financings/* | ICP WEB SSL | Obrigatório |
| 2 | Adiantamento | /unarranged-accounts-overdraft/* | ICP WEB SSL | Obrigatório |
| 2 | Direitos Creditórios | /invoice-financings/* | ICP WEB SSL | Obrigatório |
| 3 | Pagamentos | /payments/* | ICP WEB SSL | Obrigatório |
| 4 | Câmbio | /exchanges/* | ICP WEB SSL | Obrigatório |
| 4 | Investimentos | /credit-fixed-incomes/* | ICP WEB SSL | Obrigatório |

## 9. Padrão do Subject DN do Certificado Cliente Open Finance - Após 19 de janeiro de 2023 {#subjectDNtemplates}
Em 19 de Janeiro de 2023 foi padronizado a sequência e codificação do Subject DN utilizado nos Certificados Open Finance Cliente. Abaixo é determinado a sequência e codificação de como os atributos dos certificados devem ser apresentados no Subject DN.Deve ser considerado o período de coexistência entre os diferentes tipos de Subject DN, desta forma os participantes do ecossistema não devem implantar controles de bloqueio que limitem o uso apenas de certificados com o Subject DN padronizado abaixo. Os participantes devem garantir que os outros padrões de DN já utilizados continuem funcionando até o final do período de coexistência, data este ainda a ser determinada.É necessário atenção especial dos participantes durante o processo de geração do Subject DN, pois abaixo são apresentados formatos de Subject DN e RDN. O Ecossistema espera o uso de RDN em conformidade com a RFC4514.Em caso de dúvida:
- consulte o JWKS do seu aplicativo software-id
- verifique qual é o KID do certificado que deseja o Subject DN, customize a URL e acesse: `https://keystore.directory.openbankingbrasil.org.br/<org-id>/<software-ID>/transport.jwks`
`Exemplo: https://keystore.directory.openbankingbrasil.org.br/9c721898-9ce0-50f1-bf85-05075557850b/793c382e-edb1-4a64-b5c5-9e27366099b9/transport.jwks`
- busque pelo KID do certificado, posteriormente busque pela Claim: x5dn

### 9.1. Chave Pública de Certificado Exemplo:
[https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/wdHeYDz0v4m9tzxpNjsfovbl1fKCFAUvsSIs-ljM4xU.pem](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/wdHeYDz0v4m9tzxpNjsfovbl1fKCFAUvsSIs-ljM4xU.pem)
### 9.2. Exemplo Subject Distinguished Name do Certificado - Legível para Humanos:

| subject=businessCategory = Private Organization, jurisdictionC = BR, serialNumber = 43142666000197, C = BR, O = Chicago Advisory Partners, ST = SP, L = Sao Paulo, organizationIdentifier = OFBBR-d7384bd0-842f-43c5-be02-9d2b2d5efc2c, UID = bc97b8f0-cae0-4f2f-9978-d93f0e56a833, CN = web.conftpp.directory.openbankingbrasil.org.br |

### 9.3. Relative Distinguished Name (RDN) - Legível para Humanos

| subject=CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,organizationIdentifier=OFBBR-d7384bd0-842f-43c5-be02-9d2b2d5efc2c,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,serialNumber=43142666000197,jurisdictionC=BR,businessCategory=Private Organization |

### 9.4. Relative Distinguished Name (RDN) usando OID - ANS.1:

| subject=2.5.4.3=#0C2E7765622E636F6E667470702E6469726563746F72792E6F70656E62616E6B696E6762726173696C2E6F72672E6272,0.9.2342.19200300.100.1.1=#0C2462633937623866302D636165302D346632662D393937382D643933663065353661383333,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,2.5.4.7=#0C0953616F205061756C6F,2.5.4.8=#0C025350,2.5.4.10=#0C194368696361676F2041647669736F727920506172746E657273,2.5.4.6=#13024252,2.5.4.5=#130E3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0C1450726976617465204F7267616E697A6174696F6E |

### 9.5. Subject DN em RDN - Conforme RFC4514 - Padrão do Ecossistema Open Finance Brasil:

| CN=web.conftpp.directory.openbankingbrasil.org.br,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0c2a4f464242522d64373338346264302d383432662d343363352d626530322d396432623264356566633263,L=Sao Paulo,ST=SP,O=Chicago Advisory Partners,C=BR,2.5.4.5=#130e3433313432363636303030313937,1.3.6.1.4.1.311.60.2.1.3=#13024252,2.5.4.15=#0c1450726976617465204f7267616e697a6174696f6e |

### 9.6. Tabela com RDN e detalhamento dos OIDs e Codificações.

| Ordem no RDN | OID | Atributo | ASN.1 - Bit String | Codificação |
| --- | --- | --- | --- | --- |
| 1 | 2.5.4.3 | CN | #0C | UTF8 |
| 2 | 0.9.2342.19200300.100.1.1 | UID | #0C | UTF8 |
| 3 | 2.5.4.97 | organizationIdentifier | #0C | UTF8 |
| 4 | 2.5.4.7 | L | #0C | UTF8 |
| 5 | 2.5.4.8 | ST | #0C | UTF8 |
| 6 | 2.5.4.10 | O | #0C | UTF8 |
| 7 | 2.5.4.6 | C | #13 | PrintableString |
| 8 | 2.5.4.5 | serialNumber | #13 | PrintableString |
| 9 | 1.3.6.1.4.1.311.60.2.1.3 | jurisdictionCountryName | #13 | PrintableString |
| 10 | 2.5.4.15 | businessCategory | #0C | UTF8 |

---

# Padrão de Certificados > v2.0 - Padrão de Certificados > [EN] Padrão de Certificados Open Finance Brasil 2.1

---
id: 246054913
title: [EN] Padrão de Certificados Open Finance Brasil 2.1
version: 6
modified: 2024-09-06T15:40:24.596Z
url: /spaces/OF/pages/246054913/EN+Padr+o+de+Certificados+Open+Finance+Brasil+2.1
---

17
## Foreword
Este documento também está disponível em [português](file:///C:/wiki/spaces/DraftOF/pages/76251502).The Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.
## Objective
Specify the set of necessary certificates required by participating organizations in Open Finance Brasil to ensure interoperability for authentication, confidentiality, integrity and non-repudiation among participants, as well as for users and consumers of these entities. The audience of this specification are the entities participating in Open Finance Brasil that will issue certificates to authenticate themselves with other entities, as well as offering their customers a secure authentication channel.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2][ISODIR2]. These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the types of certificates required for:
- Mutually authenticate (MTLS - Mutual TLS) participants' applications;
- Message Signature (JWS - JSON Web Signature) applications to ensure authenticity and non-repudiation of messages between participants;
- Provide a safe and reliable channel for Open Finance Brasil customers;
- Authenticate participants in the Open Finance Brasil Participant Directory.

## 2. Normative refences
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.
- [ISODIR2] - ISO/IEC Directives Part 2 [ISODIR2]: https://www.iso.org/sites/directives/current/part2/index.xhtml
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile: https://datatracker.ietf.org/doc/html/rfc5280
- [RFC7519] - JSON Web Token (JWT) [RFC7519]: https://tools.ietf.org/html/rfc7519
- [RFC7515] - JSON Web Signature (JWS) [RFC7515] : https://datatracker.ietf.org/doc/html/rfc7515
- [RFC7591] - OAuth 2.0 Dynamic Client Registration Protocol [RFC7591]: https://tools.ietf.org/html/rfc7591
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol [RFC7592]: https://tools.ietf.org/html/rfc7592
- [BCP195] - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS) [BCP195]: https://tools.ietf.org/html/bcp195
- [RFC8705] - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens [RFC8705]: https://tools.ietf.org/html/rfc8705
- [OFB-FAPI] - Open Finance Brasil Financial-grade API Security Profile 1.0 [OFB-FAPI]: https://github.com/OpenBanking-Brasil/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html
- [OFB-FAPI-DCR] - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0 [OFB-FAPI-DCR]: [EN] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3
- [DOC-ICP-01] - DECLARAÇÃO DE PRÁTICAS DE CERTIFICAÇÃO DA AUTORIDADE CERTIFICADORA RAIZ DA ICP-BRASIL: https://www.gov.br/iti/pt-br/centrais-de-conteudo/doc-icp-01-v-5-2-dpc-da-ac-raiz-da-icp-brasil-pdf
- [DOC-ICP-04] - REQUISITOS MÍNIMOS PARA AS POLÍTICAS DE CERTIFICADO NA ICP-BRASIL: https://www.gov.br/iti/pt-br/assuntos/legislacao/resolucoes/resolucoes-old/resolucao179_doc-icp-04_compilada.pdf
- [RFC6749] - The OAuth 2.0 Authorization Framework [RFC6749]: https://tools.ietf.org/html/rfc6749
- [BCB-IN134] - Manual de Segurança do Open Finance: https://www.in.gov.br/web/dou/-/instrucao-normativa-bcb-n-134-de-22-de-julho-de-2021-3345585364
- [RFC2818] - HTTP Over TLS: https://datatracker.ietf.org/doc/html/rfc2818
- [RFC5246] - The Transport Layer Security (TLS) Protocol Version 1.2 https://www.rfc-editor.org/rfc/rfc5246.txt

## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC5280], [BCP195], [RFC8705], e ISO29100 apply.
## 4. Glossary

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- HTTP - Hyper Text Transfer Protocol
- ICP - Infraestrutura de Chave Públicas Brasileira
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security
- mTLS - Mutual Transport Layer Security

## 5. Open Finance Brasil Certificate Standards

### 5.1. Introduction
The Open Finance Brazil ecosystem makes use of chains of certificates and TLS protocol to guarantee the confidentiality, authentication and integrity of the communication channel used by the APIs of the participating organizations, as well as the customers of each of the participants.The certificates used by Open Finance Brasil are also required to authenticate applications through private_key_jwt, in addition to being used to perform the payload signature using JWS. Another important attribution of certificates is to authenticate and present a secure channel to the end user in the act of authentication and use of services provided by the participating organizations.
### 5.2. ICP-Brasil Certificates
Certificates issued by Certifying Authorities authorized by ICP-Brasil are only used for communication between entities participating in the Open Finance Brasil ecosystem.The certificate issuing and revocation processes are responsibility of the Certifate Authorities themselves, being regulated by Certification Practice Statements, and supervised by the Management Committee of the Brazilian Public Key Infrastructure (Comitê Gestor da Infraestrutura de Chaves Públicas Brasileira).The practices, processes, availability and values practiced by the Certification Authorities are not responsibility of the Initial Structure of Open Finance Brasil.**Name restrictions**Despite UTF8 support by the certificate attributes, this standard will adhere to name restrictions as outlined in the document: “REQUISITOS MÍNIMOS PARA AS POLÍTICAS DE CERTIFICADO NA ICP-BRASIL”, section 7.1.5, establishing the following name restrictions applicable to all ICP-BRASIL certificates:
- shall not use punctuation signs, umlauts or cedilla;
- in addition to alphanumeric characters, only the following special characters may be used:

| Character | Code NBR9611 (hexadecimal) | Character | Code NBR9611 (hexadecimal) |
| White space | 20 | + | 2B |
| ! | 21 | , | 2C |
| “ | 22 | - | 2D |
| # | 23 | . | 2E |
| $ | 24 | / | 2F |
| % | 25 | : | 3A |
| & | 26 | ; | 3B |
| ‘ | 27 | = | 3D |
| ( | 28 | ? | 3F |
| ) | 29 | @ | 40 |
| * | 2A | \ | 5C |
**Algorithms**All certificates issued by ICP-Brasil must have the following characteristics:
- Type A of ICP-Brasil;
- Key Algorithms: RSA 2048 bits;
- Message Digest: SHA 256 bits.
Participating Certificate AuthoritiesThe following certifying authorities carried out the onboard process for Open Finance Brasil and are authorized to issue Open Finance Brasil certificates using the level 1 certificates listed here:
- CertiSign (Chain v5 e v10)
- Serasa (Chain v5 e v10)
- Serpro (Chain v5 e v10)
- Soluti (Chain v5 e v10)
- Valid (Chain v5 e v10)
Only the certificates indicated with "Situação: válido" (which mean "status: valid") in these ITI repositories referenced above, which are Chain v5 and v10, should be accepted by the servers of the Open Finance Brasil ecosystem.
#### 5.2.1. Server Certificate
The Server Certificate must be issued to protect and authenticate the TLS channel used by the APIs that will be consumed by client applications of organizations participating in Open Finance.The certificate standard used must follow the existing certificate issuing practices of "CERTIFICATE FOR WEB SERVER - ICP-Brasil".The server certificate shall be sent with the intermediate chain, according to [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/items%207.4.2).
#### 5.2.2. Client Certificate
Client Application Certificates (Transport) are used to authenticate the mTLS channel and to authenticate the client application through private_key_jwt, according to the application registration performed by the Dynamic Client Registration process with the transmitting organization. Regarding mTLS, the client certificate shall be sent with the intermediate chain, according to [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/items%207.4.2%20and%207.4.6).To issue a Client Certificate, the participating organization in Open Finance Brasil must register the application in the Directory Service through the Software Statement Assertion issue process, and thus have already obtained the Software Statement ID value.
##### 5.2.2.1. Open Finance Brasil Attributes

- serialNumber: National Register of Legal Personnel (CNPJ) of the legal entity holding the certificate and associated with the UID attribute and Software Statement ID, during validation with the Directory Service of Open Finance Brasil;
- organizationIdentifier: Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil; For certificates issued until August 31 the field used for this information is organizationalUnitName.
- UID: Software Statement ID registered in the Directory Service of Open Finance Brasil and belonging to the CNPJ and Participant Code.
The Client Certificate must be issued through the V10 chain, and must contain the following attributes:Distinguished Name, as per the sequence bellow (details available in section 9.2):
- businessCategory (OID 2.5.4.15): Type of business category, which must contain: "Private Organization" or "Government Entity" or "Business Entity" or "Non-Commercial Entity"
- jurisdictionCountryName (OID: 1.3.6.1.4.1.311.60.2.1.3): BR
- serialNumber (OID 2.5.4.5): CNPJ
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): Company Name
- stateOrProvinceName (OID 2.5.4.8): Federation unit of the certificate holder's physical address
- localityName (OID 2.5.4.7): City of the holder's physical address
- organizationIdentifier (OID 2.5.4.97): Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil. *For certificates issued until August 31: organizationalUnitName (OID 2.5.4.11): Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil*
- UID (OID 0.9.2342.19200300.100.1.1): Software Statement ID generated by Open Finance Brasil Directory
- commonName (OID 2.5.4.3): FQDN or Wildcard
**Certificate Extensions**
- keyUsage: critical,digitalSignature,keyEncipherment
- extendedKeyUsage: clientAuth
**Subject Alternative Name****DNSName:** FQDN or Wildcard
#### 5.2.3. Signature Certificate
Signature Certificates are used to perform payload signature through the use of JWS (JSON Web Signature).
##### 5.2.3.1. Open Finance Brasil Attributes Present in the Certificate

- UID: Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brasil;
- commonName: Company Name registered in the Directory Service of Open Finance Brasil and belonging to the CNPJ and Participant Code.
The Signature Certificate must be issued through the V5 chain, and must contain the following attributes:Distinguished Name
- UID (OID 0.9.2342.19200300.100.1.1): Participant Code associated with the CNPJ listed in the Directory Service of Open Finance Brazil
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): ICP-Brasil
- organizationalUnitName (OID 2.5.4.11): Certificate Authority Name
- organizationalUnitName (OID 2.5.4.11): CNPJ of the Registration Authority
- organizationalUnitName (OID 2.5.4.11): Type of identification used (in person, videoconference or digital certificate)
- commonName (OID 2.5.4.3): Company Name
**Certificate Extensions****keyUsage:** critical,digitalSignature,nonRepudiationSubject Alternative Name
- otherName (OID 2.16.76.1.3.2 - ICP-Brasil): Name of the person responsible for the certificate
- otherName (OID 2.16.76.1.3.3 - ICP-Brasil): National Register of Legal Entities (CNPJ) of the legal entity holding the certificate;
- otherName (OID 2.16.76.1.3.4 - ICP-Brasil): Responsible for the certificate of legal entity holding the certificate (date of birth, CPF, PIS/PASEP/CI, RG);
- otherName (OID 2.16.76.1.3.7 - ICP-Brasil): INSS Specific Registry Number (CEI) of the legal entity holding the certificate.

#### 5.2.4. Front-End Certificates
Front-End certificates are utilized to make services available, generally web pages, using TLS, that are acessible by the end users. Due to their function, and in order to guarantee better interoperability, those certificates must be of the type EV (Extended Validation) and must be generated by a valid certificate authority, following definitions of RFC 5280 e RFC 2818, in conformance with WebTrust principles and criteria.
#### 5.2.5. About certificates for exchanging information between authorized institutions and partners (non-participating)
According to section IV of Joint Resolution No. 1 of May 4, 2020, the establishment of bilateral partnerships between authorized institutions and partners is an arrangement provided for in the regulation which must observe, where applicable, the same standards and certificates requirements that are applicable to exchange of information between participating institutions.In accordance with §2 of Art. 10 of Provisional Measure 2200-2 of August 24, 2001 and with the provisions of item 3.12 in BCB Normative Instruction No. 134, for bilateral communication between institutions and partners, the use is authorized, by mutual agreement between the parties, of a private PKI, provided that the requirements of this profile for security certificates are observed, including their formatting, algorithms and established attributes.The values for filling in the attributes required in this specification, but not applicable to the partner, should be defined in common agreement between the authorized institution and the partner, which does not exempt the authorized institution from the responsibility for filling it in properly.
## 6. Acknowledgements
Thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- João Rodolfo Vieira (Itaú)
- José Michael Dias (Grupo Pan)
- Marcos Rodrigues (Itaú)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## 7. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
## 8. Appendix

### 8.1. Configuration Template for Client Certificate - OpenSSL - For certificates issued until August 31, 2022

jurisdictionCountryName = BR
serialNumber = 
countryName = BR
organizationName = 
stateOrProvinceName = 
localityName = 
organizationalUnitName = 
UID = 
commonName = 

[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth

[ alt_name ]
DNS = ]]>
### 8.2. Configuration Template for Client Certificate - OpenSSL - For certificates issued after August 31, 2022

jurisdictionCountryName = BR
serialNumber = 
countryName = BR
organizationName = 
stateOrProvinceName = 
localityName = 
organizationIdentifier = OFBBR-
UID = 
commonName = 

[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth

[ alt_name ]
DNS = ]]>
### 8.3. Configuration Template for Signature Certificate - OpenSSL

countryName = BR
organizationName = ICP-Brasil
0.organizationalUnitName = 
1.organizationalUnitName = 
2.organizationalUnitName = 
commonName = 

[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,nonRepudiation

[ alt_name ]
otherName.0 = 2.16.76.1.3.2;PRINTABLESTRING:
otherName.1 = 2.16.76.1.3.3;PRINTABLESTRING:
otherName.2 = 2.16.76.1.3.4;PRINTABLESTRING:
otherName.3 = 2.16.76.1.3.7;PRINTABLESTRING:]]>
### 8.4. Endpoints vs Certificate type and mTLS requirements
Below we present which endpoints can be published utilizing the EV certificate as consent authentication and the endpoints of private/bussiness API authentication using the ICP certificate. You will also be able to check which endpoints must protect its connections using mTLS.ASPSP may choose the certificate that should be adopted for Open Data endpoints, which, by nature, are publicly accessible.
| Table 1 | | | | |
| OFB Phase | group | endpoint | certificate type | mTLS |
| NA | OIDC | .well-known/openid-configuration | EV or ICP WEB SSL | |
| NA | OIDC | jwks_uri | EV or ICP WEB SSL | |
| NA | OIDC | authorization_endpoint | EV | |
| NA | OIDC | token_endpoint | ICP WEB SSL | Required |
| NA | OIDC | userinfo_endpoint | ICP WEB SSL | Required |
| NA | OIDC | pushed_authorization_request_endpoint | ICP WEB SSL | Required |
| NA | DCR | registration_endpoint | ICP WEB SSL | Required |
| NA | OIDC | revocation_endpoint | ICP WEB SSL | Required |
| 2 | Consentimentos | /consents/* | ICP WEB SSL | Required |
| 2 | Resources | /resources/* | ICP WEB SSL | Required |
| 2 | Dados | /customers/* | ICP WEB SSL | Required |
| 2 | Cartão | /credit-cards-accounts/* | ICP WEB SSL | Required |
| 2 | Contas | /accounts/* | ICP WEB SSL | Required |
| 2 | Empréstimos | /loans/* | ICP WEB SSL | Required |
| 2 | Financiamentos | /financings/* | ICP WEB SSL | Required |
| 2 | Adiantamento | /unarranged-accounts-overdraft/* | ICP WEB SSL | Required |
| 2 | Direitos Creditórios | /invoice-financings/* | ICP WEB SSL | Required |
| 3 | Pagamentos | /payments/* | ICP WEB SSL | Required |
| 3 | Webhook | /webhook/* | ICP WEB SSL | Required |
| 4 | Câmbio | /exchanges/* | ICP WEB SSL | Required |
| 4 | Investimentos | /credit-fixed-incomes/* | ICP WEB SSL | Required |

### 8.5. Guide for the exchange of Certification Authorities approved in the Open Finance Brazil ecosystem by institutions

#### 8.5.1. Introduction
Open Finance is an initiative of the Brazil Central Bank whose main objectives are to bring innovation to the financial system, promote competition, and improve the offer of financial products and services to the end consumer. This guide aims to assist professionals involved in the management of digital certificates used in the scope of Open Finance services by presenting the necessary technical analyses for migrating from an approved certificate authority (CAs/PKIs) to another certificate authority.An approved certificate issuer is understood to be a certification authority that is linked to ITI/ICP, meeting all requirements and current legislation related to ITI/ICP's public key infrastructure and that is duly registered by the Open Finance ecosystem as a certification authority able to issue digital certificates in ITI/ICP's Brasil (Management Committee of the Brazilian Public Key Infrastructure) V5 and V10 chains,  following all the requirements listed in the Digital Certificate Standard.You can find the list of approved organizations here: [Participating Certificate Authorities](https://openfinancebrasil.atlassian.net/wiki/spaces/OF/pages/246054913/EN+Padr+o+de+Certificados+Open+Finance+Brasil+2.1#5.2.-ICP-Brasil-Certificates).
#### 8.5.2. Responsibilities and Prerequisites

#### 8.5.2.1 Responsibilities:
The participating institutions, when hiring the new certificate issuance service provider, in addition to observing the technical standards and recommendations of the working groups, must observe the rules for contracting technological services and on digital certificates under their responsibility under the terms of the current regulations, especially, in the case of Open Finance, items 2.6 and 3.9 of IN BCB 305/2022:
| Item 2.6 IN BCB 305 |
| Participating institutions, prior to contracting the services required to conduct activities related to Open Finance, must adopt procedures that include the verification of the potential service provider's ability to ensure compliance with current legislation and regulations. |
| Item 3.9 IN BCB 305 |
| For message signing and secure communication with APIs used for the sharing of customer registration and transaction data and the payment transaction initiation service related to the Pix arrangement, valid digital certificates issued by a certification authority participating in ICP-Brasil must be used, in accordance with the standards for digital certification established by the Structure Responsible for the Governance of Open Finance. |

#### 8.5.2.2. Prerequisites:
Prior knowledge of the documents, standards and legislation listed below is recommended for the correct execution and analysis proposed by this guide:
- Normative Instruction BCB n° 305 of 15/9/2022 - https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=305
- Central Directory Operation Guide - Guia de Operação do Diretório Central
- Open Finance Brazil Certificate Standard 2.1 - [PT] Padrão de Certificados Open Finance Brasil 2.1
- [Open Finance Brasil Financial-grade API Security Profile 1.0] - [PT] Open Finance Brasil Financial-grade API Security Profile 1.0
- [Open Finance Brasil Financial-grade API Dynamic Client Registration 2.0 RC1 Implementers Draft 3] - [PT] Open Finance Brasil Financial-grade API Dynamic Client Registration 2.0 RC1 Implementers Draft 3
- [RFC4514] - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names - RFC 4514: Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names (rfc-editor.org)
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol - RFC 7592: OAuth 2.0 Dynamic Client Registration Management Protocol (rfc-editor.org)
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile - RFC 5280: Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile (rfc-editor.org)

### 8.5.3. Digital Certificate Analysis
Changes to the values contained in the "subjectDN*"* attribute of the digital certificate used by the Open Finance client certificate may impact the certificate holder's access to the ecosystem if the participant does not follow the instructions of the OAuth 2.0 Dynamic Client Registration Management Protocol RFC7592.Given the fact that the certificate authority will validate the organization's data registered in the central directory, and if correct, will sign the certificate request (CSR) generated by the participant, the use of lowercase letters, uppercase letters and special characters, may distinguish from the certificate in use, causing differences in the "subjectDN" attribute**as shown in the examples below.It is up to the participant to pay attention during the signature request and when checking the data. For didactic purposes the digital certificates below will be used as examples of changes in the "subjectDN*"*attributes, the divergence of locales, their formatting as uppercase and lowercase characters will change the result of the "subjectDN*".*
| Certificate 1 |
| -----BEGIN CERTIFICATE----- MIIHxzCCBa+gAwIBAgIIB4Faz1mRPo0wDQYJKoZIhvcNAQELBQAwdzELMAkGA1UE BhMCQlIxEzARBgNVBAoMCklDUC1CcmFzaWwxNTAzBgNVBAsMLEF1dG9yaWRhZGUg Q2VydGlmaWNhZG9yYSBSYWl6IEJyYXNpbGVpcmEgdjEwMRwwGgYDVQQDDBNBQyBT RVJBU0EgU1NMIEVWIFY0MB4XDTIzMDczMTExNDgwMFoXDTI0MDczMDExNDc1OVow ggFDMR0wGwYDVQQPDBRQcml2YXRlIE9yZ2FuaXphdGlvbjETMBEGCysGAQQBgjc8 AgEDEwJCUjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxCzAJBgNVBAYTAkJSMSIw IAYDVQQKDBlDaGljYWdvIEFkdmlzb3J5IFBhcnRuZXJzMQswCQYDVQQIDAJTUDES MBAGA1UEBwwJU0FPIFBBVUxPMTMwMQYDVQRhDCpPRkJCUi1kNzM4NGJkMC04NDJm LTQzYzUtYmUwMi05ZDJiMmQ1ZWZjMmMxNDAyBgoJkiaJk/IsZAEBDCRiYzk3Yjhm MC1jYWUwLTRmMmYtOTk3OC1kOTNmMGU1NmE4MzMxNzA1BgNVBAMMLndlYi5jb25m dHBwLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnIwggEiMA0GCSqG SIb3DQEBAQUAA4IBDwAwggEKAoIBAQDM7Q2MgkLsqSusK6CoFpe7idPfW4QN5mMR jK1qiCXJFTlHyot6gDlq48dHq5VDg78zy33Bio/r93KGwQEOKGsr8HOuAou6IOQA 9OPyUNMg9f64scq8lUkNqNoqAKr/I2U6ELE0LtOAwe8SW4uMhkcYBOE+eP5D76M2 n5idrjsKdN/WloUKU9H2ZjraJLOhPQ0MHD8epL7SrU0/wKEShxO5e9i0MByP00ht B74bn3yWc7pFe9TQ8oeyhMmsIky50ixIHKm5Vv/RWCjB/6CmBLyEENoNhNDMEy4k GNGsDcuPGWrRnhNbylAX7luWpSvoOCd7z/ZLZ354zDiMHbn57VAdAgMBAAGjggKH MIICgzAJBgNVHRMEAjAAMB8GA1UdIwQYMBaAFLFWplh4DM49EiNVGKlDGLbQWMUQ MIGjBggrBgEFBQcBAQSBljCBkzBNBggrBgEFBQcwAoZBaHR0cDovL3d3dy5jZXJ0 aWZpY2Fkb2RpZ2l0YWwuY29tLmJyL2NhZGVpYXMvc2VyYXNhc3NsZXZ2MTAtNC5w N2IwQgYIKwYBBQUHMAGGNmh0dHA6Ly9vY3NwLmNlcnRpZmljYWRvZGlnaXRhbC5j b20uYnIvc2VyYXNhc3NsZXZ2MTAtNDA5BgNVHREEMjAwgi53ZWIuY29uZnRwcC5k aXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyMIGFBgNVHSAEfjB8MAkG B2BMAQIBgQAwbwYFZ4EMAQEwZjBkBggrBgEFBQcCARZYaHR0cDovL3B1YmxpY2Fj YW8uY2VydGlmaWNhZG9kaWdpdGFsLmNvbS5ici9yZXBvc2l0b3Jpby9kcGMvZGVj bGFyYWNhby1zZXJhc2Etc3NsLWV2LnBkZjATBgNVHSUEDDAKBggrBgEFBQcDAjCB pwYDVR0fBIGfMIGcME+gTaBLhklodHRwOi8vd3d3LmNlcnRpZmljYWRvZGlnaXRh bC5jb20uYnIvcmVwb3NpdG9yaW8vbGNyL3NlcmFzYXNzbGV2djEwLTQuY3JsMEmg R6BFhkNodHRwOi8vbGNyLmNlcnRpZmljYWRvcy5jb20uYnIvcmVwb3NpdG9yaW8v bGNyL3NlcmFzYXNzbGV2djEwLTQuY3JsMB0GA1UdDgQWBBQ4XEp8dD3mZfBTKm2J n4UgdrMItzAOBgNVHQ8BAf8EBAMCBaAwDQYJKoZIhvcNAQELBQADggIBAJmNLrQL +OeV3DHURcHa2nHzkF+V6WugJRDnlovEed1kuK+knd/us0kmpMZfqw5GJT1ZVYFX wiW2WWfEnswEM+U1pOQCckqhWRfn+jaShj7irR+Boe9aCOw/Z2wLDl5Fk2pqb2Sj hp2JGfBjrDqy5Sw9piVZxHf0oObNsh/S3I402xFyBg7r0D6rOGtMg2JNTc+5w1dZ mZoqOYxY+pLU6c5JgvsvaipJmBav256QywYM1nOZheva6b2OnJ5ddrDqyTe2MX6+ DD4qG9kPouqegrLAxQUcJZsdmmQ59RuiwiHiwR3javX5R71fSDAd4VTdX6KHRtgr /O94a9JSW+7/Sh9jjW+ORN09wSRVM04AB5t86D7YdMlbi/kFtXOjq0IGpPl1UyD/ LUrBtQji4O3uiCwzhVSRX5Hjte5e80GLossLA3HKc0vqpNoDzKKkOj7upzOHOT5O gfVnd7LID1xn/FmyF4O8jlxoI0IZDTRcdfYnUHTUCFIF0NaPImQ2hIHxHTFHwOtO B5pNOHS7PfGpIWpt7OHEdsGh+Q3LG4zXwoCVdiTNSFZWkxN1LZECb1Fhmj+Nwout 4H75JUMdk2CHPVKKOxcNeWXeAyDLmPHl+Pah5zurX6sdaOq0SVnaN8mG1iZdd+KO 0G+Zk0R+t4wxbnGVJ+HR5f4diOF9fxegCldJ -----END CERTIFICATE----- |

| Certificate 2 |
| -----BEGIN CERTIFICATE----- MIIHlzCCBX+gAwIBAgIIEd4jERdackgwDQYJKoZIhvcNAQENBQAwdzELMAkGA1UE BhMCQlIxEzARBgNVBAoTCklDUC1CcmFzaWwxNTAzBgNVBAsTLEF1dG9yaWRhZGUg Q2VydGlmaWNhZG9yYSBSYWl6IEJyYXNpbGVpcmEgdjEwMRwwGgYDVQQDExNBQyBT T0xVVEkgU1NMIEVWIEc0MB4XDTIzMTEyMTE3MzgwMFoXDTI0MTEyMDE3MzgwMFow ggFvMR0wGwYDVQQPDBRQcml2YXRlIE9yZ2FuaXphdGlvbjETMBEGCysGAQQBgjc8 AgEDEwJCUjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxCzAJBgNVBAYTAkJSMUkw RwYDVQQKDEBDSElDQUdPIEFEVklTT1JZIFBBUlRORVJTIENPTlNVTFRPUklBIEVN IEdFU1RBTyBFTVBSRVNBUklBTCBMVERBMQswCQYDVQQIDAJSSjEXMBUGA1UEBwwO UmlvIGRlIEphbmVpcm8xMzAxBgNVBGEMKk9GQkJSLWQ3Mzg0YmQwLTg0MmYtNDNj NS1iZTAyLTlkMmIyZDVlZmMyYzE0MDIGCgmSJomT8ixkAQEMJGJjOTdiOGYwLWNh ZTAtNGYyZi05OTc4LWQ5M2YwZTU2YTgzMzE3MDUGA1UEAwwud2ViLmNvbmZ0cHAu ZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5icjCCASIwDQYJKoZIhvcN AQEBBQADggEPADCCAQoCggEBAK/TbHTlFk94cic91xBGoGAAkRiy1H0WSBIiI6B+ HWDUPN0XW8dnOVGEp/Hk/p8SB2kuIs5mEiECfeEd8/peZqlkFkmNRwYu8e10O7F1 bEx8uwGTkPX/m1s+bbw+b/oA+hDvm+77Bwun04VCtTylpyEyNfcwe7FYK8NWZnz0 A+kOC74KNwXDlpx5fCKYaknLxN40caY8scpSrbPPgk1+6TbjyyUBODDXsgj8qPwh uzSGrQ7gmrfKVd12BqrDDYiPD2g4q832lvm6zoMu5txujujQ+Svxhc3w2wIAPDf6 eFgeRceNhSzzvODYNH52DcM6th6kNKsQNiRmexARvmhNNh0CAwEAAaOCAiswggIn MAkGA1UdEwQCMAAwHwYDVR0jBBgwFoAU/ga5LJV+L+bQuKjxL7fyLoXV18AwgYAG CCsGAQUFBwEBBHQwcjBGBggrBgEFBQcwAoY6aHR0cDovL2NjZC5hY3NvbHV0aS5j b20uYnIvbGNyL2FjLXNvbHV0aS1zc2wtZXYtdjEwLWc0LmNydDAoBggrBgEFBQcw AYYcaHR0cDovL29jc3AzLmFjc29sdXRpLmNvbS5icjA5BgNVHREEMjAwgi53ZWIu Y29uZnRwcC5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyMGQGA1Ud IARdMFswBwYFZ4EMAQEwUAYGYEwBAgFwMEYwRAYIKwYBBQUHAgEWOGh0dHA6Ly9j Y2QuYWNzb2x1dGkuY29tLmJyL2RvY3MvZHBjLWFjLXNvbHV0aS1zc2wtZXYucGRm MBMGA1UdJQQMMAoGCCsGAQUFBwMCMIGQBgNVHR8EgYgwgYUwQKA+oDyGOmh0dHA6 Ly9jY2QuYWNzb2x1dGkuY29tLmJyL2xjci9hYy1zb2x1dGktc3NsLWV2LXYxMC1n NC5jcmwwQaA/oD2GO2h0dHA6Ly9jY2QyLmFjc29sdXRpLmNvbS5ici9sY3IvYWMt c29sdXRpLXNzbC1ldi12MTAtZzQuY3JsMB0GA1UdDgQWBBQ3ZGduKdZRoh8RHnMu lRcGqwTTpDAOBgNVHQ8BAf8EBAMCBaAwDQYJKoZIhvcNAQENBQADggIBAAq9CdAd 9wR+IS5g+eD2x/8wNZjPkFyimCQXuTnkJeDzdLjUv1TJvoPXRg6mByeWy5tX1JRe vU9e29z+q2yCuuoFmqKLCseWabHvhjA7L68whJIuSqPBohbjb4dPcb+cWlIZ69mq hq5G+wT1fC/PRzK+4eDvwstC+gMpP7547MCoVP6g8n5GPe6gbsdG4gufjOJ4c3YQ VWncCeH2psmOlYaXDFgR4zppNZ+Kp6tLott3iz8Q73Bu2t8lQRAekUOUrbsw70z4 3KVDfQt5GircSEiph9rzD3u/JGJjnB+m7URVC8Tg9FIIWhoWsJxqRXwr9B9JECc1 f6EAdLdr82IYhzVmAkfWb1l+YBWSPfYaPoVbjdJw7mZQlk7LUrN+przNyl961VkC INfKap+EYzjfdQ1j9kbARzFJmJ50ruOqbk6lQ21kv15oF7HC09DSuNqfs/mGOpzQ fp1OtIz4vxBO9jkYjRkKzEYW9rpNwrZ9Lsttb7n84PkXO8CAq+7ep5D75CjHDQWx U3EYoQVL5pi84LUw4x11cPrrnSw3Qx0eDyE554A5pBUzFVUIkE8tGM5CQKQ77tDD FfWy75gY8C4ee5MJ7Uhh3JA5RAnMJ4Y3OH9gn6jrlZsiLGnPJh2uZaAV9S5UoixO vd0g7wv04oksqGSykYL5RAp1gu9yJNwkF2Se -----END CERTIFICATE----- |

| Certificate 1 |
| subject= CN=web.conftpp.directory.openbankingbrasil.org.br ,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,L=SAO PAULO,ST=SP,O=Chicago Advisory Partners,C=BR,serialNumber=43142666000197,jurisdictionCountryName=BR,businessCategory=Private Organization |

| Certificate 2 |
| Example 2: subject= CN=web.conftpp.directory.openbankingbrasil.org.br ,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,L=Rio de Janeiro,ST=RJ,O=CHICAGO ADVISORY PARTNERS CONSULTORIA EM GESTAO EMPRESARIAL LTDA,C=BR,serialNumber=43142666000197,jurisdictionCountryName=BR,businessCategory=Private Organization |
Participants who have implemented OAUTH MTLS (RFC 8705), use the "subjectDN*"* of the client certificate in the Client Data Registration process as per item: RFC8705 - 2.1.2. Client Registration Metadata; Considering this fact, if the "subjectDN" of the certificate is changed by March 24, 2024, it will be necessary for the institution issuing the certificate to perform the DCM to update the: tls_client_auth_subject_dn*.*Participants who update their digital customer certificate after March 25, 2024 will be able to use the DCM (Dynamic Client Management) window provided for the migration schedule for the new Open Finance security profile, as reported in the ecosystem’s communication process ([Infoma #480](https://mailchi.mp/c959731bc25f/open-banking-informa-9417760?e=2eb7798bd9)).
## 9. Open Finance Client Certificate Subject DN Pattern - After January 19, 2023 {#subjectDNtemplates}
On January 19, 2023 the sequence and encoding of the Subject DN used in Open Finance Client Certificates was standardized. Below is determined the sequence and coding of how the attributes of the certificates should be presented in the Subject DN.The coexistence period between the different types of Subject DN must be considered, so the participants of the ecosystem should not implement blocking controls that limit the use of only certificates with the Subject DN standardized below. Participants must ensure that the other DN standards already in use continue to function until the end of the coexistence period, a date yet to be determined.Special attention is required from the participants during the Subject DN generation process, as below are presented Subject DN and RDN formats. The Ecosystem expects the use of RDN in compliance with RFC4514.When in doubt:
- check the JWKS of your software-id application
- check the KID of the certificate you want the Subject DN for, customize the URL and access: https://keystore.directory.openbankingbrasil.org.br/<org-id>/<software-ID>/transport.jwks
- search for the certificate’s KID, then search for the Claim: x5dn
**9.1 Example:**
### 9.1.1. JWKS with certificate’s information:

### Example: https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/transport.jwks

### 9.1.2. Public Key Certificate Example:
[https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/wdHeYDz0v4m9tzxpNjsfovbl1fKCFAUvsSIs-ljM4xU.pem](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/wdHeYDz0v4m9tzxpNjsfovbl1fKCFAUvsSIs-ljM4xU.pem)
### 9.2. Example Subject Distinguished Name of the Certificate - Human readable:

### 9.3. Relative Distinguished Name (RDN) - Human readable:

### 9.4. Relative Distinguished Name (RDN) using OID - ANS.1:

### 9.5. Subject DN in RDN - According to RFC4514 - Open Finance Brazil Ecosystem Standard:

### 9.6. Table with RDN and details of the OIDs and Encodings.

### The table below presents the sequence in Relative Distinguished Name as per item 9.5. In order to check the sequential order of the subjectDN, refer to itens 9.2 and 5.2.2.1

| RDN Order | OID | Attribute | ASN.1 - Bit String | Enconding |
| 1 | 2.5.4.3 | CN | #0C | UTF8 |
| 2 | 0.9.2342.19200300.100.1.1 | UID | #0C | UTF8 |
| 3 | 2.5.4.97 | organizationIdentifier | #0C | UTF8 |
| 4 | 2.5.4.7 | L | #0C | UTF8 |
| 5 | 2.5.4.8 | ST | #0C | UTF8 |
| 6 | 2.5.4.10 | O | #0C | UTF8 |
| 7 | 2.5.4.6 | C | #13 | PrintableString |
| 8 | 2.5.4.5 | serialNumber | #13 | PrintableString |
| 9 | 1.3.6.1.4.1.311.60.2.1.3 | jurisdictionCountryName | #13 | PrintableString |
| 10 | 2.5.4.15 | businessCategory | #0C | UTF8 |

---

# Padrão de Certificados > v2.0 - Padrão de Certificados > [PT] Padrão de Certificados Open Finance Brasil 2.1

---
id: 245694518
title: [PT] Padrão de Certificados Open Finance Brasil 2.1
version: 7
modified: 2025-05-09T18:47:51.617Z
url: /spaces/OF/pages/245694518/PT+Padr+o+de+Certificados+Open+Finance+Brasil+2.1
---

17
## Prefácio
This document is also available in English.A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar os padrões e especificações necessários para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos de patente. A Estrutura Inicial do Open Finance Brasil não se responsabiliza pela identificação de qualquer ou todos os direitos de patente.
## Objetivo
Especificar o conjunto de certificados necessários que devem ser utilizados pelas entidades participantes do Open Finance Brasil para garantir interoperabilidade para autenticação, confidencialidade, integridade e não repúdio entre os participantes, bem como para os usuários e consumidores destas entidades. O público desta especificação são entidades participantes do Open Finance Brasil que necessitam fazer a emissão de certificados para se autenticar junto a outras entidades, bem como oferecer a seus clientes um canal de autenticação seguro.
## Convenções Notacionais
As palavras-chave "deve" (shall), "não deve" (shall not), "deveria" (should), "não deveria" (should not) e "pode" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2][ISODIR2] observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 1. Escopo
Este documento especifica os tipos de certificados necessários para:
- Autenticar mutuamente (MTLS - Mutual TLS) as aplicações dos participantes;
- Assinatura de Mensagens (JWS - JSON Web Signature) de aplicações para garantir a autenticidade e não repúdio de mensagens entre os participantes;
- Apresentar um canal seguro e confiável para clientes do Open Finance Brasil;
- Autenticar participantes no Diretório de participantes do Open Finance Brasil.

## 2. Referências Normativas
Os seguintes documentos referenciados são indispensáveis para a aplicação deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, a última edição do documento referenciado (incluindo quaisquer emendas) se aplica.
- [ISODIR2] - ISO/IEC Directives Part 2 [ISODIR2]: https://www.iso.org/sites/directives/current/part2/index.xhtml
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile: https://datatracker.ietf.org/doc/html/rfc5280
- [RFC7519] - JSON Web Token (JWT) [RFC7519]: https://tools.ietf.org/html/rfc7519
- [RFC7515] - JSON Web Signature (JWS) [RFC7515] : https://datatracker.ietf.org/doc/html/rfc7515
- [RFC7591] - OAuth 2.0 Dynamic Client Registration Protocol [RFC7591]: https://tools.ietf.org/html/rfc7591
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol [RFC7592]: https://tools.ietf.org/html/rfc7592
- [BCP195] - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS) [BCP195]: https://tools.ietf.org/html/bcp195
- [RFC8705] - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens [RFC8705]: https://tools.ietf.org/html/rfc8705
- [OFB-FAPI] - Open Finance Brasil Financial-grade API Security Profile 1.0 [OFB-FAPI]: https://github.com/OpenBanking-Brasil/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html
- [OFB-FAPI-DCR] - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0 [OFB-FAPI-DCR]: [PT] Open Finance Brasil Financial-grade API Dynamic Client Registration 1.0 Implementers Draft 3
- [DOC-ICP-01] - DECLARAÇÃO DE PRÁTICAS DE CERTIFICAÇÃO DA AUTORIDADE CERTIFICADORA RAIZ DA ICP-BRASIL: https://www.gov.br/iti/pt-br/centrais-de-conteudo/doc-icp-01-v-5-2-dpc-da-ac-raiz-da-icp-brasil-pdf
- [DOC-ICP-04] - REQUISITOS MÍNIMOS PARA AS POLÍTICAS DE CERTIFICADO NA ICP-BRASIL: https://www.gov.br/iti/pt-br/assuntos/legislacao/resolucoes/resolucoes-old/resolucao179_doc-icp-04_compilada.pdf
- [RFC6749] - The OAuth 2.0 Authorization Framework [RFC6749]: https://tools.ietf.org/html/rfc6749
- [BCB-IN134] - Manual de Segurança do Open Finance: https://www.in.gov.br/web/dou/-/instrucao-normativa-bcb-n-134-de-22-de-julho-de-2021-3345585364
- [RFC2818] - HTTP Over TLS: https://datatracker.ietf.org/doc/html/rfc2818
- [RFC5246] - The Transport Layer Security (TLS) Protocol Version 1.2 https://www.rfc-editor.org/rfc/rfc5246.txt

## 3. Termos e Definições
Para o propósito deste documento os termos definidos na [RFC5280], [BCP195], [RFC8705], e ISO29100 são aplicáveis.
## 4. Glossário

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- HTTP - Hyper Text Transfer Protocol
- ICP - Infraestrutura de Chave Públicas Brasileira
- SS - Software Statement
- SSA - Software Statement Assertion
- TLS - Transport Layer Security
- mTLS - Mutual Transport Layer Security
- subjectDN – Subject Distinguished Name
- RDN – Relative Distinguished Name

## 5. Padrão de Certificados Open Finance Brasil

### 5.1. Introdução
O ecossistema do Open Finance Brasil faz uso de cadeias de certificados e protocolo TLS para garantir a confidencialidade, autenticação e integridade do canal de comunicação utilizado pelas APIs das instituições participantes, bem como dos clientes de cada um dos participantes.Os certificados utilizados pelo Open Finance Brasil também são necessários para autenticar as aplicações através do private_key_jwt, além de também servirem para realizar a assinatura de payload pelo uso de JWS. Outra atribuição importante dos certificados é autenticar e apresentar um canal seguro para o usuário final no ato de autenticação e uso dos serviços prestados pela entidade participante.
### 5.2. Certificados ICP-Brasil
Os certificados emitidos pelas Autoridades Certificadoras autorizadas pelo ICP-Brasil são utilizados apenas na comunicação entre as entidades participantes do ecossistema do Open Finance Brasil.Os processos de emissão e revogação dos certificados são de responsabilidade das próprias Autoridades Certificadores, sendo regulamentados por Declarações de Prática de Certificação, e supervisionadas pelo Comitê Gestor da Infraestrutura de Chaves Públicas Brasileira.As práticas, processos, disponibilização e valores praticados pelas Autoridades Certificadoras não são de responsabilidade do Estrutura Inicial do Open Finance Brasil.**Restrição de nomes**Apesar do suporte ao UTF8 pelos atributos do certificado, este padrão seguirá as restrições de nomes conforme documento: “REQUISITOS MÍNIMOS PARA AS POLÍTICAS DE CERTIFICADO NA ICP-BRASIL”, item 7.1.5, estabelecendo as seguintes restrições para os nomes, aplicáveis a todos os certificados ICP-BRASIL:
- não deverão ser utilizados sinais de acentuação, tremas ou cedilhas; e
- além dos caracteres alfanuméricos, poderão ser utilizados somente os seguintes caracteres especiais:

| Caractere | Código NBR9611 (hexadecimal) | Caractere | Código NBR9611 (hexadecimal) |
| branco | 20 | + | 2B |
| ! | 21 | , | 2C |
| “ | 22 | - | 2D |
| # | 23 | . | 2E |
| $ | 24 | / | 2F |
| % | 25 | : | 3A |
| & | 26 | ; | 3B |
| ‘ | 27 | = | 3D |
| ( | 28 | ? | 3F |
| ) | 29 | @ | 40 |
| * | 2A | \ | 5C |
**Algoritmos**Todos os certificados emitidos junto ao ICP-Brasil devem possuir as seguintes características:
- Tipo A do ICP-Brasil;
- Algoritmo de Chaves: RSA 2048 bits;
- Message Digest: SHA 256 bits.

#### 5.2.1. Certificado Servidor
O Certificado Servidor deve ser emitido para proteger e autenticar o canal TLS utilizado pelas APIs que serão consumidas pelas aplicações cliente de entidades participantes do Open Finance.O padrão de certificado utilizado deve seguir as práticas de emissão de certificados existentes de "CERTIFICADO PARA SERVIDOR WEB - ICP-Brasil".O certificado de servidor precisa ser enviado com a cadeia intermediária, conforme [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/itens%207.4.2).
#### 5.2.2. Certificado Cliente
Os Certificados de Aplicação Cliente (Transporte) são utilizados para autenticar o canal mTLS e para realizar a autenticação da aplicação cliente através de private_key_jwt, de acordo com o cadastro da aplicação realizado pelo processo de Dynamic Client Registration junto à entidade transmissora. Sobre o mTLS, o certificado cliente precisa ser enviado com a cadeia intermediária, conforme [RFC5246](https://openbanking-brasil.github.io/specs-seguranca/itens%207.4.2%20e%207.4.6).Para emissão de Certificado Cliente é necessário que a instituição participante do Open Finance Brasil tenha realizado o cadastro da aplicação no Serviço de Diretório, através do processo de emissão de Software Statement Assertion, e com isso já tenha obtido o valor de Software Statement ID.
##### 5.2.2.1. Atributos Open Finance Brasil

- serialNumber: Cadastro Nacional de Pessoal Jurídica (CNPJ) da pessoa jurídica titular do certificado e associado ao atributo UID e Software Statement ID, durante validação junto ao Serviço de Diretório do Open Finance Brasil;
- organizationIdentifier: Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil; Para certificados emitidos até 31 de Agosto de 2022 o campo utilizado para essa informação era o organizationalUnitName.
- UID: Software Statement ID cadastrado no Serviço de Diretório do Open Finance Brasil e pertencente ao CNPJ e Código de Participante.
O Certificado Cliente deve ser emitido através de cadeia V10, e deve obrigatoriamente conter os seguintes atributos:**Distinguished Name, conforme sequência abaixo, para maiores detalhes, consulte a seção: 9.2**
- businessCategory (OID 2.5.4.15): Tipo de categoria comercial, devendo conter: "Private Organization" ou "Government Entity" ou "Business Entity" ou "Non-Commercial Entity"
- jurisdictionCountryName (OID: 1.3.6.1.4.1.311.60.2.1.3): BR
- serialNumber (OID 2.5.4.5): CNPJ
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): Razão Social
- stateOrProvinceName (OID 2.5.4.8): Unidade da federação do endereço físico do titular do certificado
- localityName (OID 2.5.4.7): Cidade do endereço físico do titular
- organizationIdentifier (OID 2.5.4.97): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil. Para certificados emitidos até 31 Agosto de 2022: organizationalUnitName (OID 2.5.4.11): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil
- UID (OID 0.9.2342.19200300.100.1.1): Software Statement ID gerado pelo Diretório do Open Finance Brasil
- commonName (OID 2.5.4.3): FQDN ou Wildcard
**Certificate Extensions**
- keyUsage: critical,digitalSignature,keyEncipherment
- extendedKeyUsage: clientAuth
**Subject Alternative Name****DNSName:** FQDN ou Wildcard
#### 5.2.3. Certificado de Assinatura
Os Certificados de Assinatura são utilizados para realizar assinatura do payload através do uso de JWS (JSON Web Signature).
##### 5.2.3.1. Atributos Open Finance Brasil Presentes no Certificado

- UID: Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil;
- commonName: Razão Social cadastrado no Serviço de Diretório do Open Finance Brasil e pertencente ao CNPJ e Código de Participante.
O Certificado de Assinatura deve ser emitido através de cadeia V5, e deve obrigatoriamente conter os seguintes atributos:Distinguished Name
- UID (OID 0.9.2342.19200300.100.1.1): Código de Participante associado ao CNPJ listado no Serviço de Diretório do Open Finance Brasil
- countryName (OID 2.5.4.6): BR
- organizationName (OID 2.5.4.10): ICP-Brasil
- organizationalUnitName (OID 2.5.4.11): Nome da Autoridade Certificadora
- organizationalUnitName (OID 2.5.4.11): CNPJ da Autoridade de Registro
- organizationalUnitName (OID 2.5.4.11): Tipo de identificação utilizada (presencial, videoconferência ou certificado digital)
- commonName (OID 2.5.4.3): Nome da Razão Social
**Certificate Extensions****keyUsage:**critical,digitalSignature,nonRepudiation**Subject Alternative Name**
- otherName (OID 2.16.76.1.3.2 - ICP-Brasil): Nome do responsável pelo certificado
- otherName (OID 2.16.76.1.3.3 - ICP-Brasil): Cadastro Nacional de Pessoa Jurídica (CNPJ) da pessoa jurídica titular do certificado;
- otherName (OID 2.16.76.1.3.4 - ICP-Brasil): Responsável pelo certificado de pessoa jurídica titular do certificado (data de nascimento, CPF, PIS/PASEP/CI, RG);
- otherName (OID 2.16.76.1.3.7 - ICP-Brasil): Número do Cadastro Especifico do INSS (CEI) da pessoa jurídica titular do certificado.

#### Autoridades Certificadoras Participantes
As seguintes autoridades certificadoras realizaram o processo de integração ao Open Finance Brasil e estão habilitadas para realizar a emissão de certificados do Open Finance Brasil utilizando para tal os certificados nível 1 aqui listados:
- CertiSign (Cadeia v5 e v10)
- Serasa (Cadeia v5 e v10)
- Serpro (Cadeia v5 e v10)
- Soluti (Cadeia v5 e v10)
- Valid (Cadeia v5 e v10)
Apenas deverá ser aceito certificados indicados com "Situação: válido" nestes repositórios do ITI acima referenciados que são de Cadeia ICP-Brasil v5 e v10.
#### 5.2.4. Certificado para Front-End
Os certificados para Front-End são utilizados para disponibilizar serviços, em geral páginas Web, com uso de TLS, que são acessados pelo usuário final. Dado a sua finalidade, e para garantir maior interoperabilidade, os certificados devem ser do tipo EV (Extended Validation) e devem ser ser gerados através de uma autoridade certificadora válida, seguindo as regras definidas na RFC 5280 e RFC 2818, em conformidade com os princípios e critérios WebTrust.
#### 5.2.5. Sobre certificados para troca de informações entre instituições autorizadas e parceiros
De acordo com a seção IV da Resolução Conjunta nº 1 de 4 de maio de 2020, o estabelecimento de parcerias bilaterais entre instituições autorizadas e parceiros é um arranjo previsto na regulação e que deve observar, no que couber, inclusive os mesmos padrões e certificados de segurança que são aplicáveis para a troca de informações entre as instituições participantes.Em consonância com o §2º do Art. 10 da Medida Provisória 2.200-2 de 24 de agosto de 2001 e com o disposto no item 3.12 na Instrução Normativa BCB Nº 134, para a comunicação bilateral entre as instituições e parceiros fica autorizado o uso, em comum acordo entre as partes, de uma PKI privada desde que observados os requisitos deste perfil para os certificados segurança, o que inclui sua formatação, os algoritmos e os atributos estabelecidos.Os valores para o preenchimento dos atributos exigidos nessa especificação, mas não aplicáveis ao parceiro, deveriam ser definidos em comum acordo entre a instituição autorizada e o parceiro, o que não isenta da instituição autorizada a responsabilidade pelo preenchimento.
## 6. Reconhecimento
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro e seguro de dados por meio da formação do Grupo de Trabalho FAPI da OpenID Foundation, o GT-Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- João Rodolfo Vieira (Itaú)
- José Michael Dias (Grupo Pan)
- Marcos Rodrigues (Itaú)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## 7. Informativo
Copyright (c) 2023 Estrutura Inicial do Open Finance Brasil.A Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementações e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do GT-Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
## 8. Apêndice

### 8.1. Modelo de Configuração de Certificado Cliente - OpenSSL *Para certificados emitidos até 31 Agosto de 2022

jurisdictionCountryName = BR
serialNumber = 
countryName = BR
organizationName = 
stateOrProvinceName = 
localityName = 
organizationalUnitName = 
UID = 
commonName = 

[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth

[ alt_name ]
DNS = ]]>
### 8.2. Modelo de Configuração de Certificado Cliente - OpenSSL *Para certificados emitidos após 31 Agosto 2022

jurisdictionCountryName = BR
serialNumber = 
countryName = BR
organizationName = 
stateOrProvinceName = 
localityName = 
organizationIdentifier = OFBBR-
UID = 
commonName = 

[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,keyEncipherment
extendedKeyUsage = clientAuth

[ alt_name ]
DNS = ]]>
### 8.3. Modelo de Configuração de Certificado de Assinatura

countryName = BR
organizationName = ICP-Brasil
0.organizationalUnitName = 
1.organizationalUnitName = 
2.organizationalUnitName = 
commonName = 

[ req_cert_extensions ]
basicConstraints = CA:FALSE
subjectAltName = @alt_name
keyUsage = critical,digitalSignature,nonRepudiation

[ alt_name ]
otherName.0 = 2.16.76.1.3.2;PRINTABLESTRING:#CNPJ
otherName.1 = 2.16.76.1.3.3;PRINTABLESTRING:
otherName.2 = 2.16.76.1.3.4;PRINTABLESTRING:
otherName.3 = 2.16.76.1.3.7;PRINTABLESTRING:]]>
### 8.4. Tabela com Endpoints vs Tipo de Certificado e mTLS
Abaixo apresentamos quais endpoints podem ser publicados utilizando certificado EV como autenticação do consentimento e os endpoints de autenticação de APIs privadas/negócios que devem ser publicadas usando certificado ICP. Você também poderá verificar quais endpoints devem proteger suas conexões utilizando mTLS.Fica a critério da instituição a escolha do certificado que deve ser adotado para os endpoints de Dados Abertos, os quais, por natureza, são de acesso público.
| | | | | Table 1 |
| Fase | Grupo | API | Certificado | mTLS |
| NA | OIDC | .well-known/openid-configuration | EV ou ICP WEB SSL | |
| NA | OIDC | jwks_uri | EV ou ICP WEB SSL | |
| NA | OIDC | authorization_endpoint | EV | |
| NA | OIDC | token_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | userinfo_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | pushed_authorization_request_endpoint | ICP WEB SSL | Obrigatório |
| NA | DCR | registration_endpoint | ICP WEB SSL | Obrigatório |
| NA | OIDC | revocation_endpoint | ICP WEB SSL | Obrigatório |
| 2 | Consentimentos | /consents/* | ICP WEB SSL | Obrigatório |
| 2 | Resources | /resources/* | ICP WEB SSL | Obrigatório |
| 2 | Dados | /customers/* | ICP WEB SSL | Obrigatório |
| 2 | Cartão | /credit-cards-accounts/* | ICP WEB SSL | Obrigatório |
| 2 | Contas | /accounts/* | ICP WEB SSL | Obrigatório |
| 2 | Empréstimos | /loans/* | ICP WEB SSL | Obrigatório |
| 2 | Financiamentos | /financings/* | ICP WEB SSL | Obrigatório |
| 2 | Adiantamento | /unarranged-accounts-overdraft/* | ICP WEB SSL | Obrigatório |
| 2 | Direitos Creditórios | /invoice-financings/* | ICP WEB SSL | Obrigatório |
| 3 | Pagamentos | /payments/* | ICP WEB SSL | Obrigatório |
| 3 | Webhook | /webhook/* | ICP WEB SSL | Obrigatório |
| 4 | Câmbio | /exchanges/* | ICP WEB SSL | Obrigatório |
| 4 | Investimentos | /credit-fixed-incomes/* | ICP WEB SSL | Obrigatório |

### 8.5. Guia para troca de Autoridades Certificadoras por parte das instituições

1. Introdução
O Open Finance ou Sistema Financeiro Aberto é uma iniciativa do Banco Central do Brasil que tem como principais objetivos trazer inovação ao sistema financeiro, promover a concorrência, e melhorar a oferta de produtos e serviços financeiros ao consumidor final. Este guia tem o objetivo de auxiliar os profissionais envolvidos na gestão de certificados digitais utilizados no escopo de serviços do Open Finance apresentando as análises técnicas necessárias para quando da migração de uma autoridade certificadora (CAs/PKIs) homologada para outra autoridade certificadora.Entende-se como emissor de certificados homologado uma autoridade certificadora que está vinculada ao ITI/ICP, atendendo a todos os requisitos e legislação vigente relacionada a infraestrutura de chaves públicas do ITI/ICP e que é devidamente cadastrada pelo ecossistema Open Finance como autoridade certificadora apta a emitir certificados digitais nas cadeias V5 e V10 do ITI/ICP, seguindo todos os requisitos listados no Padrão de Certificado Digitais. Você poderá encontrar a lista de organizações homologadas aqui: Autoridades Certificadoras Participantes.**2.Responsabilidades e Pré-requisitos****2.1. Responsabilidades:**As instituições participantes, ao contratar o novo prestador de serviço de emissão de certificado, além de observar os padrões técnicos e recomendações dos grupos de trabalho, devem observar as regras para contratação de serviços tecnológicos e sobre certificados digitais sob responsabilidade delas nos termos da regulamentação vigente, especialmente, no caso do Open Finance, os itens 2.6 e 3.9 da IN BCB 305/2022:
| Item 2.6 IN BCB 305 |
| As instituições participantes, previamente à contratação de serviços requeridos para a condução das atividades relativas ao Open Finance, devem adotar procedimentos que contemplem a verificação da capacidade do potencial prestador de serviço de assegurar o cumprimento da legislação e da regulamentação vigente. |
| Item 3.9 IN BCB 305 |
| Para assinatura de mensagens e comunicação segura com APIs usadas para os compartilhamentos de dados de cadastro e de transações de clientes e do serviço de iniciação de transação de pagamento relacionado com o arranjo Pix, devem ser utilizados certificados digitais válidos, emitidos por autoridade certificadora participante da ICP-Brasil, de acordo com os padrões para certificação digital estabelecidos pela Estrutura Responsável pela Governança do Open Finance. |
**2.2. Pré-requisitos:**O conhecimento prévio nos documentos, padrões e legislações listados abaixo são recomendados para a correta execução e análise proposta por este guia:
- Instrução Normativa BCB n° 305 de 15/9/2022 - https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=305
- Guia de Operação do Diretório Central - Guia de Operação do Diretório Central
- Padrão de Certificados Open Finance Brasil 2.1 - [PT] Padrão de Certificados Open Finance Brasil 2.1
- [Open Finance Brasil Financial-grade API Security Profile 1.0] - [PT] Open Finance Brasil Financial-grade API Security Profile 1.0
- [Open Finance Brasil Financial-grade API Dynamic Client Registration 2.0 RC1 Implementers Draft 3] - [PT] Open Finance Brasil Financial-grade API Dynamic Client Registration 2.0 RC1 Implementers Draft 3
- [RFC4514] - Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names - RFC 4514: Lightweight Directory Access Protocol (LDAP): String Representation of Distinguished Names ( http://rfc-editor.org )
- [RFC7592] - OAuth 2.0 Dynamic Client Registration Management Protocol - RFC 7592: OAuth 2.0 Dynamic Client Registration Management Protocol ( http://rfc-editor.org )
- [RFC5280] - Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile - RFC 5280: Internet X.509 Public Key Infrastructure Certificate and Certificate Revocation List (CRL) Profile ( http://rfc-editor.org )

1. Análise do Certificado Digital
Alterações dos valores contidos no atributo “subjectDN” do certificado digital utilizado pelo certificado de cliente Open Finance, podem causar impactos no acesso do portador do certificado ao ecossistema, caso o participante não observe as instruções da RFC7592 - OAuth 2.0 Dynamic Client Registration Management Protocol.Dado ao fato que a autoridade certificadora irá validar os dados da organização cadastrados no diretório central, e se corretos, irá assinar a requisição de certificados (CSR) gerado pelo participante, o uso de letras minúsculas, maiúsculas e caracteres especiais, poderão distinguir do certificado em uso, ocasionando diferenças no atributo “subjectDN” conforme exemplos abaixo.Cabe ao participante se atentar durante o pedido de assinatura e na conferência dos dados. Para efeitos didáticos serão utilizados os certificados digitais abaixo como exemplos de alteração nos atributos “subjectDN”, a divergência de localidades, sua formatação como caracteres maiúsculos e minúsculos irão mudar o resultado do “subjectDN”.
| Certificado 1 |
| -----BEGIN CERTIFICATE----- MIIHxzCCBa+gAwIBAgIIB4Faz1mRPo0wDQYJKoZIhvcNAQELBQAwdzELMAkGA1UE BhMCQlIxEzARBgNVBAoMCklDUC1CcmFzaWwxNTAzBgNVBAsMLEF1dG9yaWRhZGUg Q2VydGlmaWNhZG9yYSBSYWl6IEJyYXNpbGVpcmEgdjEwMRwwGgYDVQQDDBNBQyBT RVJBU0EgU1NMIEVWIFY0MB4XDTIzMDczMTExNDgwMFoXDTI0MDczMDExNDc1OVow ggFDMR0wGwYDVQQPDBRQcml2YXRlIE9yZ2FuaXphdGlvbjETMBEGCysGAQQBgjc8 AgEDEwJCUjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxCzAJBgNVBAYTAkJSMSIw IAYDVQQKDBlDaGljYWdvIEFkdmlzb3J5IFBhcnRuZXJzMQswCQYDVQQIDAJTUDES MBAGA1UEBwwJU0FPIFBBVUxPMTMwMQYDVQRhDCpPRkJCUi1kNzM4NGJkMC04NDJm LTQzYzUtYmUwMi05ZDJiMmQ1ZWZjMmMxNDAyBgoJkiaJk/IsZAEBDCRiYzk3Yjhm MC1jYWUwLTRmMmYtOTk3OC1kOTNmMGU1NmE4MzMxNzA1BgNVBAMMLndlYi5jb25m dHBwLmRpcmVjdG9yeS5vcGVuYmFua2luZ2JyYXNpbC5vcmcuYnIwggEiMA0GCSqG SIb3DQEBAQUAA4IBDwAwggEKAoIBAQDM7Q2MgkLsqSusK6CoFpe7idPfW4QN5mMR jK1qiCXJFTlHyot6gDlq48dHq5VDg78zy33Bio/r93KGwQEOKGsr8HOuAou6IOQA 9OPyUNMg9f64scq8lUkNqNoqAKr/I2U6ELE0LtOAwe8SW4uMhkcYBOE+eP5D76M2 n5idrjsKdN/WloUKU9H2ZjraJLOhPQ0MHD8epL7SrU0/wKEShxO5e9i0MByP00ht B74bn3yWc7pFe9TQ8oeyhMmsIky50ixIHKm5Vv/RWCjB/6CmBLyEENoNhNDMEy4k GNGsDcuPGWrRnhNbylAX7luWpSvoOCd7z/ZLZ354zDiMHbn57VAdAgMBAAGjggKH MIICgzAJBgNVHRMEAjAAMB8GA1UdIwQYMBaAFLFWplh4DM49EiNVGKlDGLbQWMUQ MIGjBggrBgEFBQcBAQSBljCBkzBNBggrBgEFBQcwAoZBaHR0cDovL3d3dy5jZXJ0 aWZpY2Fkb2RpZ2l0YWwuY29tLmJyL2NhZGVpYXMvc2VyYXNhc3NsZXZ2MTAtNC5w N2IwQgYIKwYBBQUHMAGGNmh0dHA6Ly9vY3NwLmNlcnRpZmljYWRvZGlnaXRhbC5j b20uYnIvc2VyYXNhc3NsZXZ2MTAtNDA5BgNVHREEMjAwgi53ZWIuY29uZnRwcC5k aXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyMIGFBgNVHSAEfjB8MAkG B2BMAQIBgQAwbwYFZ4EMAQEwZjBkBggrBgEFBQcCARZYaHR0cDovL3B1YmxpY2Fj YW8uY2VydGlmaWNhZG9kaWdpdGFsLmNvbS5ici9yZXBvc2l0b3Jpby9kcGMvZGVj bGFyYWNhby1zZXJhc2Etc3NsLWV2LnBkZjATBgNVHSUEDDAKBggrBgEFBQcDAjCB pwYDVR0fBIGfMIGcME+gTaBLhklodHRwOi8vd3d3LmNlcnRpZmljYWRvZGlnaXRh bC5jb20uYnIvcmVwb3NpdG9yaW8vbGNyL3NlcmFzYXNzbGV2djEwLTQuY3JsMEmg R6BFhkNodHRwOi8vbGNyLmNlcnRpZmljYWRvcy5jb20uYnIvcmVwb3NpdG9yaW8v bGNyL3NlcmFzYXNzbGV2djEwLTQuY3JsMB0GA1UdDgQWBBQ4XEp8dD3mZfBTKm2J n4UgdrMItzAOBgNVHQ8BAf8EBAMCBaAwDQYJKoZIhvcNAQELBQADggIBAJmNLrQL +OeV3DHURcHa2nHzkF+V6WugJRDnlovEed1kuK+knd/us0kmpMZfqw5GJT1ZVYFX wiW2WWfEnswEM+U1pOQCckqhWRfn+jaShj7irR+Boe9aCOw/Z2wLDl5Fk2pqb2Sj hp2JGfBjrDqy5Sw9piVZxHf0oObNsh/S3I402xFyBg7r0D6rOGtMg2JNTc+5w1dZ mZoqOYxY+pLU6c5JgvsvaipJmBav256QywYM1nOZheva6b2OnJ5ddrDqyTe2MX6+ DD4qG9kPouqegrLAxQUcJZsdmmQ59RuiwiHiwR3javX5R71fSDAd4VTdX6KHRtgr /O94a9JSW+7/Sh9jjW+ORN09wSRVM04AB5t86D7YdMlbi/kFtXOjq0IGpPl1UyD/ LUrBtQji4O3uiCwzhVSRX5Hjte5e80GLossLA3HKc0vqpNoDzKKkOj7upzOHOT5O gfVnd7LID1xn/FmyF4O8jlxoI0IZDTRcdfYnUHTUCFIF0NaPImQ2hIHxHTFHwOtO B5pNOHS7PfGpIWpt7OHEdsGh+Q3LG4zXwoCVdiTNSFZWkxN1LZECb1Fhmj+Nwout 4H75JUMdk2CHPVKKOxcNeWXeAyDLmPHl+Pah5zurX6sdaOq0SVnaN8mG1iZdd+KO 0G+Zk0R+t4wxbnGVJ+HR5f4diOF9fxegCldJ -----END CERTIFICATE----- |

| Certificado 2 |
| -----BEGIN CERTIFICATE----- MIIHlzCCBX+gAwIBAgIIEd4jERdackgwDQYJKoZIhvcNAQENBQAwdzELMAkGA1UE BhMCQlIxEzARBgNVBAoTCklDUC1CcmFzaWwxNTAzBgNVBAsTLEF1dG9yaWRhZGUg Q2VydGlmaWNhZG9yYSBSYWl6IEJyYXNpbGVpcmEgdjEwMRwwGgYDVQQDExNBQyBT T0xVVEkgU1NMIEVWIEc0MB4XDTIzMTEyMTE3MzgwMFoXDTI0MTEyMDE3MzgwMFow ggFvMR0wGwYDVQQPDBRQcml2YXRlIE9yZ2FuaXphdGlvbjETMBEGCysGAQQBgjc8 AgEDEwJCUjEXMBUGA1UEBRMONDMxNDI2NjYwMDAxOTcxCzAJBgNVBAYTAkJSMUkw RwYDVQQKDEBDSElDQUdPIEFEVklTT1JZIFBBUlRORVJTIENPTlNVTFRPUklBIEVN IEdFU1RBTyBFTVBSRVNBUklBTCBMVERBMQswCQYDVQQIDAJSSjEXMBUGA1UEBwwO UmlvIGRlIEphbmVpcm8xMzAxBgNVBGEMKk9GQkJSLWQ3Mzg0YmQwLTg0MmYtNDNj NS1iZTAyLTlkMmIyZDVlZmMyYzE0MDIGCgmSJomT8ixkAQEMJGJjOTdiOGYwLWNh ZTAtNGYyZi05OTc4LWQ5M2YwZTU2YTgzMzE3MDUGA1UEAwwud2ViLmNvbmZ0cHAu ZGlyZWN0b3J5Lm9wZW5iYW5raW5nYnJhc2lsLm9yZy5icjCCASIwDQYJKoZIhvcN AQEBBQADggEPADCCAQoCggEBAK/TbHTlFk94cic91xBGoGAAkRiy1H0WSBIiI6B+ HWDUPN0XW8dnOVGEp/Hk/p8SB2kuIs5mEiECfeEd8/peZqlkFkmNRwYu8e10O7F1 bEx8uwGTkPX/m1s+bbw+b/oA+hDvm+77Bwun04VCtTylpyEyNfcwe7FYK8NWZnz0 A+kOC74KNwXDlpx5fCKYaknLxN40caY8scpSrbPPgk1+6TbjyyUBODDXsgj8qPwh uzSGrQ7gmrfKVd12BqrDDYiPD2g4q832lvm6zoMu5txujujQ+Svxhc3w2wIAPDf6 eFgeRceNhSzzvODYNH52DcM6th6kNKsQNiRmexARvmhNNh0CAwEAAaOCAiswggIn MAkGA1UdEwQCMAAwHwYDVR0jBBgwFoAU/ga5LJV+L+bQuKjxL7fyLoXV18AwgYAG CCsGAQUFBwEBBHQwcjBGBggrBgEFBQcwAoY6aHR0cDovL2NjZC5hY3NvbHV0aS5j b20uYnIvbGNyL2FjLXNvbHV0aS1zc2wtZXYtdjEwLWc0LmNydDAoBggrBgEFBQcw AYYcaHR0cDovL29jc3AzLmFjc29sdXRpLmNvbS5icjA5BgNVHREEMjAwgi53ZWIu Y29uZnRwcC5kaXJlY3Rvcnkub3BlbmJhbmtpbmdicmFzaWwub3JnLmJyMGQGA1Ud IARdMFswBwYFZ4EMAQEwUAYGYEwBAgFwMEYwRAYIKwYBBQUHAgEWOGh0dHA6Ly9j Y2QuYWNzb2x1dGkuY29tLmJyL2RvY3MvZHBjLWFjLXNvbHV0aS1zc2wtZXYucGRm MBMGA1UdJQQMMAoGCCsGAQUFBwMCMIGQBgNVHR8EgYgwgYUwQKA+oDyGOmh0dHA6 Ly9jY2QuYWNzb2x1dGkuY29tLmJyL2xjci9hYy1zb2x1dGktc3NsLWV2LXYxMC1n NC5jcmwwQaA/oD2GO2h0dHA6Ly9jY2QyLmFjc29sdXRpLmNvbS5ici9sY3IvYWMt c29sdXRpLXNzbC1ldi12MTAtZzQuY3JsMB0GA1UdDgQWBBQ3ZGduKdZRoh8RHnMu lRcGqwTTpDAOBgNVHQ8BAf8EBAMCBaAwDQYJKoZIhvcNAQENBQADggIBAAq9CdAd 9wR+IS5g+eD2x/8wNZjPkFyimCQXuTnkJeDzdLjUv1TJvoPXRg6mByeWy5tX1JRe vU9e29z+q2yCuuoFmqKLCseWabHvhjA7L68whJIuSqPBohbjb4dPcb+cWlIZ69mq hq5G+wT1fC/PRzK+4eDvwstC+gMpP7547MCoVP6g8n5GPe6gbsdG4gufjOJ4c3YQ VWncCeH2psmOlYaXDFgR4zppNZ+Kp6tLott3iz8Q73Bu2t8lQRAekUOUrbsw70z4 3KVDfQt5GircSEiph9rzD3u/JGJjnB+m7URVC8Tg9FIIWhoWsJxqRXwr9B9JECc1 f6EAdLdr82IYhzVmAkfWb1l+YBWSPfYaPoVbjdJw7mZQlk7LUrN+przNyl961VkC INfKap+EYzjfdQ1j9kbARzFJmJ50ruOqbk6lQ21kv15oF7HC09DSuNqfs/mGOpzQ fp1OtIz4vxBO9jkYjRkKzEYW9rpNwrZ9Lsttb7n84PkXO8CAq+7ep5D75CjHDQWx U3EYoQVL5pi84LUw4x11cPrrnSw3Qx0eDyE554A5pBUzFVUIkE8tGM5CQKQ77tDD FfWy75gY8C4ee5MJ7Uhh3JA5RAnMJ4Y3OH9gn6jrlZsiLGnPJh2uZaAV9S5UoixO vd0g7wv04oksqGSykYL5RAp1gu9yJNwkF2Se -----END CERTIFICATE----- |

| Certificado 1 |
| subject= CN=web.conftpp.directory.openbankingbrasil.org.br ,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,L=SAO PAULO,ST=SP,O=Chicago Advisory Partners,C=BR,serialNumber=43142666000197,jurisdictionCountryName=BR,businessCategory=Private Organization |

| Certificado 2 |
| Exemplo 2: subject= CN=web.conftpp.directory.openbankingbrasil.org.br ,UID=bc97b8f0-cae0-4f2f-9978-d93f0e56a833,2.5.4.97=#0C2A4F464242522D64373338346264302D383432662D343363352D626530322D396432623264356566633263,L=Rio de Janeiro,ST=RJ,O=CHICAGO ADVISORY PARTNERS CONSULTORIA EM GESTAO EMPRESARIAL LTDA,C=BR,serialNumber=43142666000197,jurisdictionCountryName=BR,businessCategory=Private Organization |
Participantes que implementaram o OAUTH MTLS (RFC 8705), utilizam o “subjectDN” do certificado de cliente no processo de Registro de Dados do Cliente conforme item: RFC8705 - 2.1.2. Client Registration Metadata; considerando esse fato, caso ocorra a mudança do “subjectDN” do certificado até dia 24/março/2024 será necessário que a instituição emissora do certificado, realize o DCM para atualizar o: tls_client_auth_subject_dn.Participantes que fizerem a atualização do certificado digital de cliente após 25/março/2024 poderão utilizar a janela de DCM (Atualização Dinâmica do Cliente) prevista no cronograma de migração para o novo perfil de segurança do Open Finance, conforme informe #480.
## 9. Padrão do Subject DN do Certificado Cliente Open Finance - Após 19 de janeiro de 2023 {#subjectDNtemplates}
Em 19 de Janeiro de 2023 foi padronizado a sequência e codificação do Subject DN utilizado nos Certificados Open Finance Cliente. Abaixo é determinado a sequência e codificação de como os atributos dos certificados devem ser apresentados no Subject DN.Deve ser considerado o período de coexistência entre os diferentes tipos de Subject DN, desta forma os participantes do ecossistema não devem implantar controles de bloqueio que limitem o uso apenas de certificados com o Subject DN padronizado abaixo. Os participantes devem garantir que os outros padrões de DN já utilizados continuem funcionando até o final do período de coexistência, data este ainda a ser determinada.É necessário atenção especial dos participantes durante o processo de geração do Subject DN, pois abaixo são apresentados formatos de Subject DN e RDN. **O Ecossistema espera o uso de RDN em conformidade com a RFC4514.**Em caso de dúvida:
- consulte o JWKS do seu aplicativo `software-id`
- verifique qual é o KID do certificado que deseja o Subject DN, customize a URL e acesse: https://keystore.directory.openbankingbrasil.org.br/<org-id>/<software-ID>/transport.jwks

### Exemplo:

### 9.1. 1. JWKS com informações do certificado:
**Exemplo:**[https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/transport.jwks](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/transport.jwks)
### 9.1. 2. Chave Pública de Certificado Exemplo:
[https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/dr-yip0g21Iv233K5AcuRLGABFQIcEzQZnWnC3vhFtg.pem](https://keystore.directory.openbankingbrasil.org.br/d7384bd0-842f-43c5-be02-9d2b2d5efc2c/bc97b8f0-cae0-4f2f-9978-d93f0e56a833/dr-yip0g21Iv233K5AcuRLGABFQIcEzQZnWnC3vhFtg.pem)**9.1. 1. Exemplo da Claim X5DN:**
### 9.2. Exemplo Subject Distinguished Name do Certificado - Legível para Humanos:

### 9.3. Relative Distinguished Name (RDN) - Legível para Humanos

### 9.4. Relative Distinguished Name (RDN) usando OID - ANS.1:

### 9.5. Subject DN em RDN - Conforme RFC4514 - Padrão do Ecossistema Open Finance Brasil:

### 9.6. Tabela com RDN e detalhamento dos OIDs e Codificações.

### Atenção, a tabela abaixo apresenta a sequência conforme item 9.5 em Relative Distinguished Name, se você precisa entender a ordem sequencial subjectDN, verifique os itens 9.2 e 5.2.2.1.

| Ordem no RDN | OID | Atributo | ASN.1 - Bit String | Codificação |
| 1 | 2.5.4.3 | CN | #0C | UTF8 |
| 2 | 0.9.2342.19200300.100.1.1 | UID | #0C | UTF8 |
| 3 | 2.5.4.97 | organizationIdentifier | #0C | UTF8 |
| 4 | 2.5.4.7 | L | #0C | UTF8 |
| 5 | 2.5.4.8 | ST | #0C | UTF8 |
| 6 | 2.5.4.10 | O | #0C | UTF8 |
| 7 | 2.5.4.6 | C | #13 | PrintableString |
| 8 | 2.5.4.5 | serialNumber | #13 | PrintableString |
| 9 | 1.3.6.1.4.1.311.60.2.1.3 | jurisdictionCountryName | #13 | PrintableString |
| 10 | 2.5.4.15 | businessCategory | #0C | UTF8 |

---

# Perfil de Segurança do Open Finance Brasil > v1.0 - Analise requisitos de criptografia ID_TOKEN

---
id: 240649215
title: v1.0 - Analise requisitos de criptografia ID_TOKEN
version: 2
modified: 2023-12-15T14:52:56.054Z
url: /spaces/OF/pages/240649215/v1.0+-+Analise+requisitos+de+criptografia+ID_TOKEN
---

17
## Sumário
O presente documento analisa os diversos padrões e especificações utilizados no Open Banking Brasil e apresenta as informações passíveis de serem trafegadas que demandem a criptografia do ID_TOKEN, bem como as formas como essa criptografia deve ocorrer.
## Fontes de informações sensíveis
O ID_TOKEN pode possuir Claims que contenham informações pessoais, que devem ser protegidas contra acesso não autorizado. Estas Claims são relacionadas na tabela abaixo com a indicação do documento que as define. Maiores informações podem ser obtidas na seção "Documentação de Referência", ao final desse documento.
| Claim | Definição | Descrição | Observações |
| --- | --- | --- | --- |
| sub | OIDC Core 1.0 - 2 | Identificador unico do usuário final | O AS poderia optar por usar uma PII como identificador, nesse caso a anonimização seria necessária. O sub é um identificador nunca transferido ou alterado para o usuário final |
| id_token_hint | OIDC Core 1.0 - 3.3.2.1, 3.3.2.2 | ID_TOKEN previamente recebido, enviado como dica da identidade que deseja que seja autenticada | Se o ID_TOKEN contiver dados sensíveis o ID_TOKEN_HINT deveria ser criptografado, dado a dificuldade de assegurar a adoção deste critério, recomenda-se que o ID_TOKEN_HINT seja desabilitado no Perfil de Segurança do Open Banking Brasil |
| Claims com PII | OIDC Core 1.0 - 3.3.3.6, Perfil de Segurança OBBr - 5.2.2 | O AS pode optar por retornar menos informações do Endpoint de Autorização, do que no Endpoint de Token, se estas representarem riscos a privacidade | Incluir no perfil de segurança que se o Cliente solicitar Claims com PII como Essenciais, mas não tiver chave de criptografia registrada, a solicitação deverá falhar. Caso estas Claims sejam marcadas como Opcionais, elas somente deverão ser retornadas no Endpoint de Autorização se houver chave de criptografia registrada, caso contrário deverão ser retornadas somente no Endpoint de Token. |
| Standard Claims | OIDC Core 1.0 - 5.1 | O OpenID Connect define uma série de Claims padrão que podem incluir informações sensíveis como datas de nascimento, endereço e telefone | Vale a mesma regra indicada acima. |
| CPF | Perfil de Segurança OBBr - 5.2.2, 5.2.2.2 | Nova claim padrão de acordo com cláusula 5.1 OIDC | Adicionar ao Perfil de Segurança 5.2.2.2, que se o CPF for solicitado como Essencial no Endpoint de Autorização, mas não for possível criptografá-lo, a requisição deverá falhar. |

## Regras para criptografia

| Regra | Documentação | Observações |
| --- | --- | --- |
| ID_TOKENS não devem ser criptografados com base nos cabeçalhos x5u, x5c, jku ou jkw da mensagem JWS ou JW | OIDC Core 1.0 - 2 | Pode-se incluir no Perfil de Segurança que o envio de uma Claim KID? (não cabeçalho) para indicar a chave com a qual deseja receber os dados criptografados, na ausência do parâmetro, qualquer chave de criptografia presente no JWKS poderia ser usada |
| O ID_TOKEN deve ser encriptado com base nas chaves informadas no momento do registro do cliente | OIDC Core 1.0 - 3.3.2.12, 3.3.3.7 | Conforme jwks_uri informado durante do registro dinâmico |
| AS deve suportar assinatura e criptografia de ID_TOKEN | FAPI 1.0 Advanced - 5.2.2.1 | |
| Se o AS for enviar PII no ID_TOKEN, este deve ser criptografado | FAPI 1.0 Advanced - 5.2.2.1, Perfil de Segurança OBBr - 5.2.2.1 | |
| Cliente deve suportar ID_TOKENs assinados e criptografados | FAPI 1.0 Advanced - 5.2.2.1 | |

# Documentação de Referência

## OpenID Connect Core 1.0

### ID Token
id_tokensub REQUIRED. Subject Identifier. A locally unique and never reassigned identifier within the Issuer for the End-User, which is intended to be consumed by the Client, e.g., 24400320 or AItOawmwtWwcT0k51BayewNvutrJUqsvl6qs7A4. It MUST NOT exceed 255 ASCII characters in length. The sub value is a case sensitive string.ID Tokens MUST be signed using JWS [JWS] and optionally both signed and then encrypted using JWS [JWS] and JWE [JWE] respectively, thereby providing authentication, integrity, non-repudiation, and optionally, confidentiality, per Section 16.14. If the ID Token is encrypted, it MUST be signed then encrypted, with the result being a Nested JWT, as defined in [JWT]. ID Tokens MUST NOT use none as the alg value unless the Response Type used returns no ID Token from the Authorization Endpoint (such as when using the Authorization Code Flow) and the Client explicitly requested the use of none at Registration time.ID Tokens SHOULD NOT use the JWS or JWE x5u, x5c, jku, or jwk Header Parameter fields. Instead, references to keys used are communicated in advance using Discovery and Registration parameters, per Section 10.
### Authentication Request (Hybrid Flow)
Authentication Requests are made as defined in next Section (Authentication Request), except that these Authentication Request parameters are used as follows:
#### Authentication Request
This specification also defines the following request parameters: id_token_hint OPTIONAL. ID Token previously issued by the Authorization Server being passed as a hint about the End-User's current or past authenticated session with the Client. If the End-User identified by the ID Token is logged in or is logged in by the request, then the Authorization Server returns a positive response; otherwise, it SHOULD return an error, such as login_required. When possible, an id_token_hint SHOULD be present when prompt=none is used and an invalid_request error MAY be returned if it is not; however, the server SHOULD respond successfully when possible, even if it is not present. The Authorization Server need not be listed as an audience of the ID Token when it is used as an id_token_hint value. If the ID Token received by the RP from the OP is encrypted, to use it as an id_token_hint, the Client MUST decrypt the signed ID Token contained within the encrypted ID Token. The Client MAY re-encrypt the signed ID token to the Authentication Server using a key that enables the server to decrypt the ID Token, and use the re-encrypted ID token as the id_token_hint value.
### Authentication Request Validation (Hybrid Flow)
When using the Hybrid Flow, the Authentication Request is validated in the same manner as for the Authorization Code Flow, as defined in next Section (Authentication Request Validation).
#### Authentication Request Validation
If the sub (subject) Claim is requested with a specific value for the ID Token, the Authorization Server MUST only send a positive response if the End-User identified by that sub value has an active session with the Authorization Server or has been Authenticated as a result of the request. The Authorization Server MUST NOT reply with an ID Token or Access Token for a different user, even if they have an active session with the Authorization Server. Such a request can be made either using an id_token_hint parameter or by requesting a specific Claim Value as described in Section 5.5.1, if the claims parameter is supported by the implementation.
### ID Token Validation
When using the Hybrid Flow, the contents of an ID Token returned from the Authorization Endpoint MUST be validated in the same manner as for the Implicit Flow, as defined in Section below (ID Token Validation).
#### token_valdiation ID Token Validation
When using the Implicit Flow, the contents of the ID Token MUST be validated in the same manner as for the Authorization Code Flow, as defined in next Section (ID Token Validation), with the exception of the differences specified in this section. 
#### ID Token Validation

1. If the ID Token is encrypted, decrypt it using the keys and algorithms that the Client specified during Registration that the OP was to use to encrypt the ID Token. If encryption was negotiated with the OP at Registration time and the ID Token is not encrypted, the RP SHOULD reject it.

### ID Token
When using the Hybrid Flow, the contents of an ID Token returned from the Token Endpoint are the same as for an ID Token returned from the Authorization Endpoint, as defined in next Section (ID Token Validation) , with the exception of the differences specified in this section.If an ID Token is returned from both the Authorization Endpoint and from the Token Endpoint, which is the case for the response_type values code id_token and code id_token token, the iss and sub Claim Values MUST be identical in both ID Tokens. All Claims about the Authentication event present in either SHOULD be present in both. If either ID Token contains Claims about the End-User, any that are present in both SHOULD have the same values in both. Note that the OP MAY choose to return fewer Claims about the End-User from the Authorization Endpoint, for instance, for privacy reasons. The at_hash and c_hash Claims MAY be omitted from the ID Token returned from the Token Endpoint even when these Claims are present in the ID Token returned from the Authorization Endpoint, because the ID Token and Access Token values returned from the Token Endpoint are already cryptographically bound together by the TLS encryption performed by the Token Endpoint.
### ID Token Validation
When using the Hybrid Flow, the contents of an ID Token returned from the Token Endpoint MUST be validated in the same manner as for the Authorization Code Flow, as defined in the Following [Section](#token_valdiation).
### Standard Claims
This specification defines a set of standard Claims. They can be requested to be returned either in the UserInfo Response, per Section 5.3.2, or in the [ID Token](#id_token) Section
| Member | Type | Description |
| --- | --- | --- |
| sub | string | Subject - Identifier for the End-User at the Issuer. |
| name | string | End-User's full name in displayable form including all name parts, possibly including titles and suffixes, ordered according to the End-User's locale and preferences. |
| given_name | string | Given name(s) or first name(s) of the End-User. Note that in some cultures, people can have multiple given names; all can be present, with the names being separated by space characters. |
| family_name | string | Surname(s) or last name(s) of the End-User. Note that in some cultures, people can have multiple family names or no family name; all can be present, with the names being separated by space characters. |
| middle_name | string | Middle name(s) of the End-User. Note that in some cultures, people can have multiple middle names; all can be present, with the names being separated by space characters. Also note that in some cultures, middle names are not used. |
| nickname | string | Casual name of the End-User that may or may not be the same as the given_name. For instance, a nickname value of Mike might be returned alongside a given_name value of Michael. |
| preferred_username | string | Shorthand name by which the End-User wishes to be referred to at the RP, such as janedoe or j.doe. This value MAY be any valid JSON string including special characters such as @, /, or whitespace. The RP MUST NOT rely upon this value being unique, as discussed in Section 5.7. |
| profile | string | URL of the End-User's profile page. The contents of this Web page SHOULD be about the End-User. |
| picture | string | URL of the End-User's profile picture. This URL MUST refer to an image file (for example, a PNG, JPEG, or GIF image file), rather than to a Web page containing an image. Note that this URL SHOULD specifically reference a profile photo of the End-User suitable for displaying when describing the End-User, rather than an arbitrary photo taken by the End-User. |
| website | string | URL of the End-User's Web page or blog. This Web page SHOULD contain information published by the End-User or an organization that the End-User is affiliated with. |
| email | string | End-User's preferred e-mail address. Its value MUST conform to the RFC 5322 [RFC5322] addr-spec syntax. The RP MUST NOT rely upon this value being unique, as discussed in Section 5.7. |
| email_verified | boolean | True if the End-User's e-mail address has been verified; otherwise false. When this Claim Value is true, this means that the OP took affirmative steps to ensure that this e-mail address was controlled by the End-User at the time the verification was performed. The means by which an e-mail address is verified is context-specific, and dependent upon the trust framework or contractual agreements within which the parties are operating. |
| gender | string | End-User's gender. Values defined by this specification are female and male. Other values MAY be used when neither of the defined values are applicable. |
| birthdate | string | End-User's birthday, represented as an ISO 8601:2004 [ISO8601‑2004] YYYY-MM-DD format. The year MAY be 0000, indicating that it is omitted. To represent only the year, YYYY format is allowed. Note that depending on the underlying platform's date related function, providing just year can result in varying month and day, so the implementers need to take this factor into account to correctly process the dates. |
| zoneinfo | string | String from zoneinfo [zoneinfo] time zone database representing the End-User's time zone. For example, Europe/Paris or America/Los_Angeles. |
| locale | string | End-User's locale, represented as a BCP47 [RFC5646] language tag. This is typically an ISO 639-1 Alpha-2 [ISO639‑1] language code in lowercase and an ISO 3166-1 Alpha-2 [ISO3166‑1] country code in uppercase, separated by a dash. For example, en-US or fr-CA. As a compatibility note, some implementations have used an underscore as the separator rather than a dash, for example, en_US; Relying Parties MAY choose to accept this locale syntax as well. |
| phone_number | string | End-User's preferred telephone number. E.164 [E.164] is RECOMMENDED as the format of this Claim, for example, +1 (425) 555-1212 or +56 (2) 687 2400. If the phone number contains an extension, it is RECOMMENDED that the extension be represented using the RFC 3966 [RFC3966] extension syntax, for example, +1 (604) 555-1234;ext=5678. |
| phone_number_verified | boolean | True if the End-User's phone number has been verified; otherwise false. When this Claim Value is true, this means that the OP took affirmative steps to ensure that this phone number was controlled by the End-User at the time the verification was performed. The means by which a phone number is verified is context-specific, and dependent upon the trust framework or contractual agreements within which the parties are operating. When true, the phone_number Claim MUST be in E.164 format and any extensions MUST be represented in RFC 3966 format. |
| address | JSON | object End-User's preferred postal address. The value of the address member is a JSON [RFC4627] structure containing some or all of the members defined in Section 5.1.1. |
| updated_at | number | Time the End-User's information was last updated. Its value is a JSON number representing the number of seconds from 1970-01-01T0:0:0Z as measured in UTC until the date/time. |

## Financial-grade API Security Profile 1.0 - Part 1: Baseline

### Returning authenticated user's identifier

1. shall issue an ID Token in the token response when openid was included in the requested scope as in Section 3.1.3.3 of OIDC with its sub value corresponding to the authenticated user and optional acr value in ID Token.

### Authorization request and response
In this document, the authorization request is not encrypted. Thus, it is possible to leak the information contained if the web browser is compromised. Authorization response can be encrypted as ID Token can be encrypted.
### Privacy considerations

#### Introduction
Privacy threats to OAuth and OpenID Connect implementations include the following:
- (User tracking by RPs) Two or more RPs correlating access tokens or ID Tokens to track users.
- (Attacker observing personal data in authorization request) Authorization request might contain personal data. This can be observed by an attacker. These threats can be mitigated by choosing appropriate options in OAuth or OpenID, or by introducing some operational rules. For example, "Attacker observing personal data in authorization request" can be mitigated by either using authorization request by reference using request_uri or by encrypting the request object. Similarly, "Attacker observing personal data in authorization endpoint response" can be mitigated by encrypting the ID Token or JARM response.

## Financial-grade API Security Profile 1.0 - Part 2: Advanced

### ID Token as detached signature
In addition, if the response_type value code id_token is used, the authorization server 3. should support signed and encrypted ID Tokens; 6. should not return sensitive PII in the ID Token in the authorization response, but if it needs to, then it should encrypt the ID Token. NOTE: The authorization server may return more claims in the ID Token from the token endpoint than in the one from the authorization response
### Confidential client

#### ID Token as detached signature
In addition, if the response_type value code id_token is used, the client 5. shall support both signed and signed & encrypted ID Tokens.
## Open Banking Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3

### Servidor de Autorização

1. deve suportar os parâmetros claims como definido no item 5.5 do OpenID Connect Core
2. deve suportar o atributo claim padrão oidc "cpf" conforme definido no item deste documento

### Token de ID como assinatura separada userInfo

1. não deveria retornar Informação de Identificação Pessoal (PII) confidenciais no token de ID na resposta de autorização, mas se for necessário, então ele deve criptografar o token de ID .

### Solicitando uma "claim" cpf
Este perfil define "cpf" como uma nova claim padrão de acordo com cláusula 5.1 OIDCO número do CPF (Cadastro de Pessoas Físicas, [sepeˈɛfi]; português para "Registro de Pessoas Físicas") é o cadastro de pessoa física brasileira. Este número é atribuído pela Receita Federal Brasileira para brasileiros e estrangeiros residentes que, direta ou indiretamente, pagar impostos no Brasil.No modelo de identidade do Open Banking Brasil, o cpf é uma string composta por números 11 caracteres de comprimento e podem começar com 0.Se a Claim cpf for solicitada como essencial para constar no ID token ou na resposta ao endpoint de UserInfo e na solicitação constar no parâmetro value com determinado CPF exigido, o Authorization Server DEVE retornar no atributo cpf o valor que corresponda ao da solicitação.Se a Claim cpf for solicitada como essencial para constar no ID Token ou na resposta no endpoint de UserInfo, o Authorization Server deve retornar no atributo cpf o valor com o CPF do usuário autenticado.Se a Claim cpf indicada como essencial não puder ser preenchida ou não for compatível com o requisito, o Authorization Server deve tratar a solicitação como uma tentativa de autenticação com falha.Nome: cpf, Tipo: String, Regex: 'd{11}$'

---

# Perfil de Segurança do Open Finance Brasil > FAPI-BR v2.1.0 - Open Finance Brasil Financial-grade API Security Profile > [EN] Open Finance Brasil Financial-grade API Security Profile - v2.1.0

---
id: 1334149240
title: [EN] Open Finance Brasil Financial-grade API Security Profile - v2.1.0
version: 2
modified: 2025-12-02T19:42:44.706Z
url: /spaces/OF/pages/1334149240/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+-+v2.1.0
---

13falsedefaultlisttrue
## Foreword
Este material também está disponível em Português

Associação Open Finance Brasil is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation, as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf) and the National Monetary Council. There is a possibility that some of the elements of this document may be subject to copyright or patent rights. Associação Open Finance Brasil shall not be held responsible for identifying any or all such rights.The Open Finance Brasil Security Profile (FAPI-BR) consists of the following parts:
- Open Finance Brasil Financial-grade API Security Profile - v2.1.0
- Open Finance Brasil Dynamic Client Registration - v2.1.0

## 1. Introduction
The Open Finance Brasil Security Profile is an implementation of the [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) profile that provides specific implementation guidelines for security and interoperability that shall be applied to APIs exposed in the Open Finance Brasil ecosystem. The Open Finance Brasil Security Profile is a subset of the [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html); however, this subset does not refer to the removal of security mechanisms from the original profile, but rather to the mandatory use of certain characteristics of that profile in order to facilitate interoperability among financial institutions.This profile describes the capabilities and security features that shall be provided by servers and clients that are necessary for the Open Finance Brasil ecosystem, defining measures to mitigate or address:
- attacks that address privacy considerations identified in clause 9.1 of FAPI-1-Advanced ;
- the requirement to support fine-grained access to resources, for data minimisation purposes;
- the requirement to convey the Authentication Context Request (acr claim) that was performed by an OpenID Provider, in order to enable appropriate risk management arising from user access.
This profile also specifies the method for applications to:
- obtain the OAuth tokens in an appropriately secure manner for access to critical data in a manner that meets the requirements of Open Finance Brasil ;
- use OpenID Connect to identify the Open Finance user; and
- use OpenID Connect to assert the identity of the client.
Although it is possible to code from scratch an Authorization Server that complies with the Open Finance Brasil Security Profile, the target audience of this specification is providers that already have a certified implementation of [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and wish to make the necessary adjustments to obtain certification for the Open Finance Brasil Security Profile.These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html).
## 2. Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml).These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 3. Normative references
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applies. For undated references, the latest edition of the referenced document (including any amendments) applies.[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[FAPI-LIP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[OIDC-Core](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0[OIDC-Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0[OIDC-Registration](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC8414](https://tools.ietf.org/html/rfc8414) - OAuth 2.0 Authorization Server Metadata[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens
## 4. Symbols and abbreviated terms

- API - Application Programming Interface
- DCR - Dynamic Client Registration
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- MFA - Multi-Factor Authentication
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- TLS - Transport Layer Security

## 5. Open Finance Brasil Security Profile

### 5.1. Authorization Server
To address the privacy considerations identified in Open Finance Brasil, which were not fully addressed in the final [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) specification, and to support client management in the Open Finance Brasil ecosystem, the Open Finance Brasil Security Profile establishes that the Authorization Server shall support the provisions specified in clause 5.2.2 of [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html).In addition, the Authorization Server shall:
1. shall perform client authentication using private_key_jwt;
2. shall require Pushed Authorization Requests (PAR);
3. shall publish discovery metadata (including the authorization endpoint) via the metadata document as specified in OIDC-Discovery and RFC8414 (".well-known");
4. shall support the claims parameter as defined in clause 5.5 of OIDC-Core ;
5. shall support the acr value "urn:brasil:openbanking:loa2" as defined in clause 5.1.1.1;
6. should support the acr value "urn:brasil:openbanking:loa3" as defined in clause 5.1.1.1;
7. shall implement the userinfo endpoint as defined in clause 5.3 of OIDC-Core ;
8. shall support the parameterized scope as defined in clause 6.3.1 of FAPI-LIP ;
9. may support FAPI-CIBA ;
10. shall support refresh tokens;
11. shall issue access tokens with an expiry time between 300 seconds (minimum) and 900 seconds (maximum);
12. shall support the response_type value "code id_token";
13. shall not allow refresh token rotation;
14. shall ensure that, in case of sharing the Authorization Server for other services, in addition to Open Finance, it does not disclose and/or allow the use of non-certified methods in the Open Finance environment;
15. shall ensure that the settings disclosed to other participants through OpenID Discovery (indicated by the Well-Known file registered in the Directory) are restricted to the operating modes to which the institution has certified;
16. shall refuse requests, for the Open Finance environment, that are outside the modes of operation to which the institution has certified its Authorization Server;
17. the minimum expiration time of request_uri must be 60 seconds;
18. shall refuse requests that do not present the x-fapi-interaction-id header on protected resource endpoints;
19. shall require the use of Proof Key for Code Exchange (PKCE);
20. shall require the use of subject_type "public";
21. shall require the use of response_mode "fragment";
22. shall issue refresh_tokens (JWT or opaque) with no expiration time in scenarios where they are required.

#### 5.1.1. ID Token
The Authorization Server shall support the provisions specified in clause 5.2.2.1 of [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and, in addition, in order to meet specific requirements of the Open Finance Brasil Security Profile, it shall:
1. shall encrypt the id_token in callback and token endpoint calls;
2. for the encryption of the id_token, a key of type "enc" available in the JWKS informed in the jwks_uri parameter of the client registration (DCR) must be used. The kid of the key used for the id_token encryption must be indicated in the kid attribute of the JWT header;
3. shall always include the acr claim in the id_token. The value of the acr claim must be one of the allowed values as defined in the section Authentication contexts (acr);
4. The use of other headers to indicate the key used, such as x5u, x5c, jku or jkw, is prohibited as defined in clause 2 of OIDC-Core .

##### 5.1.1.1. Authentication contexts (acr) - "urn:brasil:openbanking:loa2" or "urn:brasil:openbanking:loa3"
This profile defines *urn:brasil:openbanking:loa2 (LoA2)* and *urn:brasil:openbanking:loa3 (LoA3)* as new Authentication Context Request (ACR) classes.
- LoA2: authentication mechanism using a single factor;
- LoA3: authentication mechanism using multiple authentication factors.
The following guidance must be observed for the authentication mechanism of Open Finance Brasil APIs:
- In accordance with Art. 17 of Joint Resolution no. 01, institutions must adopt procedures and controls for client authentication compatible with those applicable to access to their electronic service channels.
- In accordance with the regulation in force, it is suggested that: For user authentication in authorisations to access data sharing APIs, Authorization Servers should adopt, at least, a method compatible with LoA2; and For user authentication in authorisations to access payment initiation or service/product contracting APIs, Authorization Servers should adopt an authentication method compatible with LoA3 or higher.
In all cases, the adoption of a more rigorous authentication mechanism (LoA3 or higher) is at the discretion of the transmitting/account-holding institution, according to its risk assessment and in a manner compatible with the mechanisms usually employed.Additional clarification on authentication factorsAuthentication factors are:
- Something you know, such as a password or secret phrase;
- Something you have, such as a token, smartcard or device;
- Something you are, that is, authentication conditioned on the presentation of a physical characteristic that is exclusively yours, such as biometric validation.
To perform multi-factor authentication (MFA), it is necessary that the user presents at least two different factors from those listed above. A single factor used more than once – for example, presenting two passwords that the user knows – cannot be accepted as MFA.
#### 5.1.2. "sub" Claim clarifications
This profile uses the official definition found at: Analise requisitos de criptografia ID_TOKEN. This means that the sub is an identifier that is never transferred or changed for the end user within the issuer (account-holding/transmitting institution).
#### 5.1.3 Mandatory scopes on the well-known endpoint
The authorization server shall mandatorily declare the scopes below in its well-known endpoint, regardless of whether the institution provides the products related to the scopes listed below:
- invoice-financings
- financings
- loans
- unarranged-accounts-overdraft
- bank-fixed-incomes
- credit-fixed-incomes
- variable-incomes
- treasure-titles
- funds
- exchanges
Scopes not listed above must be declared if the institution provides products related to them (e.g. accounts, payments, etc.).
### 5.2. Cliente confidencial
A confidential client is any client created through a secure method and that has specific access credentials. In the Open Finance Brasil ecosystem, confidential clients are clients that were created through DCR (Dynamic Client Registration). A confidential client shall support the provisions specified in clause 5.2.3 of [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and, in addition, in order to meet specific requirements of the Open Finance Brasil Security Profile, it shall:
1. shall support encrypted request objects;
2. shall support PAR (pushed authorization requests);
3. shall support the parameterized scope as defined in clause 6.3.1 of FAPI-LIP ;
4. shall support refresh tokens;
5. shall not populate the acr claim with required values;
6. shall require the acr claim as an essential claim;
7. shall support the private_key_jwt authentication method;
8. shall not allow the refresh token rotation feature;
9. shall send the x-fapi-interaction-id header on FAPI endpoints.

## 6. Security considerations
Participants shall support all security considerations specified in clause 8 of [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and in the [Manual de Segurança de Banco Central do Brasil](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=305).The Brazilian ICP issues RSA x509 certificates only; therefore, for simplicity, this section removes support for EC algorithms and requires that only encryption algorithms recommended by IANA be used.
### 6.1. Message content signing considerations (JWS)
JWS standard defined in RFC7515 shall be adopted to ensure integrity and non-repudiation of information processed in sensitive API's (message sign requirement is indicated at API's documentation/swagger), which includes:
- Header (JSON Object Signing and Encryption - JOSE Header), which defines the algorithm used and includes information about the public key or certificate that can be used to validate the signature;
- Payload (JWS Payload): the content itself as detailed in the API specification;
- Digital signature (JWS Signature): digital signature, performed according to the header parameters.

1. Each of the elements above must be encoded using the Base64url pattern RFC4648 and, once this is done, the elements must be concatenated with "." (JWS Compact Serialization method, as defined in RFC7515 ).
2. The payload of signed messages (request JWT and response JWT) shall include the following claims as defined in RFC7519 :

- aud (in the JWT request): the Resource Provider (e.g. the institution holding the account) must validate whether the value of the aud field matches the endpoint being triggered;
- aud (in the JWT response): the API client (e.g. initiating institution) shall validate whether the value of the aud field matches its own organisationId listed in the directory;
- iss (in the JWT request and in the JWT response): the receiver of the message shall validate whether the value of the iss field matches the organisationId of the sender;
- jti (in the JWT request and in the JWT response): the value of the jti field shall be filled with the UUID defined by the institution in accordance with [RFC4122] using version 4;
- iat (in the JWT request and in the JWT response): the value of the iat field shall be filled with the message generation time and in accordance with the standard established in RFC7519 for the NumericDate format.
- cty (in the JWT request and in the JWT response): the value of the cty field shall be filled in; in the normal case in which nested signing or encryption operations are not employed, the use of this header parameter is not recommended. In the case that nested signing or encryption is employed, this header parameter must be present; in this case, the value must be "JWT", to indicate that a nested JWT is carried in this JWT. While media type names are not case sensitive, it is recommended that "JWT" always be spelled using uppercase characters for compatibility with legacy implementations.

1. The HTTP content-type of requests and responses with JWS messages shall be defined as: "application/jwt".
2. The JOSE header must contain the following attributes:

- alg - shall be filled with the value PS256";
- kid - shall be filled with the key identifier value used for the signature;
- typ - shall be filled with the value JWT.
- In case of error in signature validation by Resource Provider the API provider shall return HTTP error message with status code 400 and the ResponseError content shall include, in the code property, the content BAD_SIGNATURE.
- Errors in validating the signed messages received by the client application (e.g. payment initiator) must be logged and the Resource Provider (e.g. account-holding institution) must be notified.

1. The receiver shall validate the consistency of the JWS message's digital signature exclusively based on the information obtained from the directory, that is, based on the keys published in the institution's JWKS in the directory.
2. Signatures must be performed using the digital signature certificate specified in the Open Finance Brazil Certificates Standard ;
3. the iat claim must be numeric in Unix Time format GMT+0 with a tolerance of +/- 60 seconds;
4. the jti claim must be unique for a clientId within a time frame of 86,400 seconds (24h), and cannot be reused within this period. In case of reuse, the HTTP error code 403 shall be return. Any other case must follow RFC 6749 instructions in item 5.2.

### 6.2. Signing algorithm considerations
For JWS, both clients and authorization servers shall use the PS256 algorithm.
### 6.3. Encryption algorithm considerations
For JWE, both clients and authorization servers shall use RSA-OAEP with A256GCM.
### 6.4. Secure use of Transport Layer Security considerations
 For TLS, Authentication Server endpoints and Resource Server endpoints used directly by the client:
- shall support TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256;
- shall support TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384;
- The "TLS Session Resumption" and "TLS Renegotiation" features shall be disabled.

## 7. Parameterized scope considerations
Existing mechanisms for appropriately managing access to resources defined in [RFC6749](https://tools.ietf.org/html/rfc6749) are insufficient to meet the requirements of a modern data sharing ecosystem. Using static scope strings does not provide consumers with sufficient control and granularity to manage data sharing or resource management with third parties. Open Finance Brasil has elected to implement the parameterized scope ([FAPI-LIP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md)) associated with consent/binding APIs to manage fine-grained access to resources.
### 7.1. Dynamic Consent Scope Definition
This profile defines OAuth 2.0 dynamic scope "consent" as follows:
- string "consent", "recurring-consent" or "enrollment"; and
- delimiter of a colon ":"; and
- Consent Resource Id returned by a successful creation of the resource to be granted (e.g. consent, recurring-consent, enrollment).
In addition:
- the Consent Resource Id must include url safe characters only;
- the Consent Resource Id must be namespaced;
- the Consent Resource Id must have the properties of a nonce ;
Due to the characteristics of the Consent Resource Id and for ease of implementation, many institutions choose to use a UUIDv4 key as the Consent Resource Id; however, this is not a rule, and each institution may choose other methods provided that the rules presented above and also those defined in each API specification are respected.
#### 7.1.1. Dynamic consent scope example
Considering that the transmitting/account-holding institution is Banco Exemplo and that it is using UUIDv4 as the Consent Resource Id, the consents/recurring consents/device bindings created against this institution would have the following format, respectively:
- consent:urn:bancoexemplo:830ce3c6-e9e7-4800-ae93-3e9b29b470f1
- recurring-consent:urn:bancoexemplo:c9a8a741-39a6-4014-bb75-e05934f9d711
- enrollment:urn:bancoexemplo:eb093d20-ccc5-4242-a271-6658f6663712

## 8. Consent life cycle
Consent is a fundamental business object, strongly linked to security artefacts (refresh and access tokens). However, its life cycle must be managed independently through its own state machine. The functional API specifications published by Open Finance Brasil define the state transitions, expected behaviours and error conditions for REST resources protected by this profile, ensuring appropriate control over the consent life cycle.The following requirements aim to instruct the behaviour of the Authorization Server (AS) in relation to the consent life cycle, ensuring that authorisation practices are aligned with regulatory expectations and the security of the entire ecosystem.
### 8.1. Authorization Server
In addition to the requirements outlined in Open Finance Brasil security provisions the Authorization Server:
1. shall only issue refresh_tokens when linked to an active and valid consent; Must not issue refresh_token when consent status is "CONSUMED" (for payment services); Must issue an access_token through the grant_type client credentials when consent status is "CONSUMED" (for payment services); In an optimised journey, it shall issue refresh_tokens as long as at least one of the linked consents is active and valid.
2. shall only share access to resources when presented access_token linked to an active consent and with the status "AUTHORISED“. For tokens generated with the scope: payments or recurring-payments, the status of the consent will not be validated. In the scenario of receiving an invalid token, status code 401 should be returned.
3. shall revoke refresh tokens and, access tokens where aplicable, when the linked Consent Resource is deleted; In an optimised journey, it shall perform the revocation of refresh_tokens and access_tokens only if both linked consents are revoked.
4. shall ensure access tokens are issued with sufficient scope necessary for access to data specified in the Permission element of a linked Consent Resource object;
5. shall not reject an authorisation request requesting scopes broader than those necessary to access data specified in the Permissions element of a linked Consent Resource object;
6. may reduce requested scope to a level sufficient to enable access to data resources specified in the Permissions element of a linked Consent Resource object;
7. shall retain records on the consent history to allow the appropriate formation of audit trails in accordance with the regulation in force;
8. shall return authentication failure and the return code access_denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 ) if the CPF of the authenticated user is not the same as indicated in the loggedUser element of the related Consent Resource Object;
9. shall return authentication failure and the return code access_denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 ) if the businessEntity element has not been populated in the related Consent Resource Object and the user has selected or authenticated using credentials related to a legal entity (business) account;
10. shall condition the authentication or selection of legal entity (business) accounts to the consistency between the CNPJ related to the account(s) and the value present in the businessEntity element of the Consent Resource Object. In case of divergence, it shall return authentication failure and the return code access_denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 );
11. shall issue a refresh_token with a validity period not shorter than the validity of the consent to which it is related, while respecting the other criteria above.

### 8.2. Confidential client
In addition to the requirements outlined in Open Finance Brasil security provisions, the Confidential Client
1. shall revoke where possible and cease usage of refresh and access tokens that are bound to a Consent Resource that has been deleted;
2. shall delete Consent Resource that are expired;

## Appendix A. Avisos
Copyright (c) 2025 Associação Open Finance BrasilAssociação Open Finance Brasil grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to Associação Open Finance Brasil as the source of the material, but that such attribution does not indicate an endorsement by Associação Open Finance Brasil.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil Security Working Group and others. Although Associação Open Finance Brasil has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. Associação Open Finance Brasil and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. Associação Open Finance Brasil invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
## Author's Address
Associação Open Finance - GT SecurityEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Perfil de Segurança do Open Finance Brasil > FAPI-BR v2.1.0 - Open Finance Brasil Financial-grade API Security Profile > [PT] Open Finance Brasil Financial-grade API Security Profile - v2.1.0

---
id: 1334149137
title: [PT] Open Finance Brasil Financial-grade API Security Profile - v2.1.0
version: 2
modified: 2025-12-02T19:41:19.645Z
url: /spaces/OF/pages/1334149137/PT+Open+Finance+Brasil+Financial-grade+API+Security+Profile+-+v2.1.0
---

13falsedefaultlisttrue
## Prefácio
This document is also avaiable in [English](file:///C:/wiki/spaces/DraftOF/pages/76283925)A Associação Open Finance é responsável por criar padrões e especificações necessárias para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf) e Conselho Monetário Nacional. É possível que alguns dos elementos deste documento estejam sujeitos a direitos autorais ou patenteados. A Associação Open Finance não se responsabiliza pela identificação de qualquer ou todos esses direitos.O Perfil de Segurança do Open Finance Brasil (FAPI-BR) consiste nas seguintes partes:
- Open Finance Brasil Financial-grade API Security Profile 2.1.0
- Open Finance Brasil Dynamic Client Registration Profile 2.1.0

## 1. Introdução
O Perfil de Segurança do Open Finance Brasil é uma implementação do perfil [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) que fornece diretrizes de implementação específicas para segurança e interoperabilidade que devem ser aplicadas as APIs expostas no ecossistema do Open Finance Brasil. O Perfil de Segurança do Open Finance Brasil é um subconjunto do perfil [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html), no entanto esse subconjunto não se refere a retirada de mecanismos de segurança do perfil original e sim a obrigatoriedade de utilização de determinadas características do mesmo visando a facilitação da interoperabilidade entre as instituições financeiras.Este perfil descreve as capacidades e os recursos de segurança que devem ser oferecidos por servidores e clientes que são necessários para o ecossistema do Open Finance Brasil, definindo as medidas para mitigar ou endereçar:
- ataques que abordam considerações de privacidade identificadas na cláusula 9.1 de FAPI-1-Advanced .
- o requisito de concessão de acesso granular a recursos, com vistas à minimização de dados;
- o requisito de informar sobre o contexto da autenticação do usuário (claim Authentication Context Request - acr) que foi realizada por um Provedor OpenID, com vistas a favorecer o adequado gerenciamento do risco decorrente do acesso do usuário;
Este perfil também especifica o método para os aplicativos:
- obterem de maneira segura os tokens OAuth necessários para acesso a dados críticos de acordo com os requisitos do Open Finance Brasil ;
- utilizarem o OpenID Connect para identificação do usuário do Open Finance; e
- utilizarem o OpenID Connect para afirmar a identidade do cliente.
Embora seja possível codificar do início um servidor de autorização que atenda ao Perfil de Segurança do Open Finance Brasil, o público alvo desta especificação são os provedores que já possuem uma implementação certificada do [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e desejam realizar as adequações necessárias para obter a certificação para o Perfil de Segurança do Open Finance Brasil.Estas partes são destinados a serem usados com [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) e [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html).
## 2. Convenções Notacionais
As palavras-chave "deve" (shall), "não deve" (shall not), "deveria" (should), "não deveria" (should not) e "pode" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 3. Referências normativas
Os seguintes documentos referenciados são indispensáveis para a adoção das especificações deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, deve-se aplicar a última edição do documento referenciado (incluindo quaisquer emendas).[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[FAPI-LIP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[OIDC-Core](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0[OIDC-Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0[OIDC-Registration](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC8414](https://tools.ietf.org/html/rfc8414) - OAuth 2.0 Authorization Server Metadata[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens
## 4. Símbolos e termos abreviados

- API - Application Programming Interface (Interface de programação de aplicativo)
- DCR - Registro de cliente dinâmico
- FAPI - Financial-grade API
- HTTP - Protocolo de transferência de hipertexto
- MFA - Multi-Factor Authentication (Autenticação por Múltiplos Fatores)
- OIDF - OpenID Foundation
- REST - Representational State Transfer (Transferência de Estado Representacional)
- TLS - Transport Layer Security (Segurança da Camada de Transporte)

## 5. Perfil de Segurança para o Open Finance Brasil

### 5.1. Servidor de Autorização
Para atender às considerações de privacidade identificadas no Open Finance Brasil, que não foram totalmente abordadas na especificação final [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html), e para suportar o gerenciamento de clientes no ecossistema Open Finance Brasil, o Perfil de Segurança do Open Finance Brasil estabelece que o Servidor de Autorização deve suportar as disposições especificadas na cláusula 5.2.2 de [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html).Além disso, ele deve:
1. deve realizar a autenticação do cliente utilizando private_key_jwt;
2. deve exigir requisições do tipo Pushed Authorization Requests (PAR);
3. deve publicar metadados de descoberta (incluindo a do endpoint de autorização) por meio do documento de metadado especificado em OIDC-Discovery e RFC8414 (".well-known");
4. deve suportar os parâmetros claims como definido no item 5.5 do OIDC-Core ;
5. deve suportar o atributo acr "urn:brasil:openbanking:loa2" como definido no item 5.1.1.1;
6. deveria suportar o atributo acr "urn:brasil:openbanking:loa3" como definido no item 5.1.1.1;
7. deve implementar o endpoint userinfo como definido no item 5.3 do OIDC-Core ;
8. deve suportar o escopo parametrizável ("parameterized scope") como definido no item 6.3.1 de FAPI-LIP ;
9. pode suportar FAPI-CIBA ;
10. deve suportar refresh tokens ;
11. deve emitir access tokens com o tempo de expiração entre 300 (mínimo) e 900 (máximo) segundos;
12. deve suportar o valor “ code id_token ” para o atributo response_type ;
13. não deve permitir o recurso de rotação de refresh tokens ;
14. deve garantir que em caso de compartilhamento do Servidor de Autorização para outros serviços, além do Open Finance, não divulgue e/ou possibilite o uso de métodos não certificados no ambiente do Open Finance;
15. deve garantir que as configurações divulgadas aos demais participantes através do OpenID Discovery (indicado pelo arquivo de Well-Known cadastrado no Diretório) sejam restritos aos modos de operação aos quais a instituição se certificou;
16. deve recusar requisições, para o ambiente do Open Finance, que estejam fora dos modos de operação ao qual a instituição certificou seu Servidor de Autorização;
17. o tempo mínimo de expiração do request_uri deve ser de 60 segundos;
18. deve recusar requisições que não apresentem o cabeçalho x-fapi-interaction-id em endpoints de recursos protegidos;
19. deve exigir a utilização de Proof Key for Code Exchange (PKCE);
20. deve exigir a utilização do subject_type “public”;
21. deve exigir a utilização do response_mode “fragment”;
22. Deve emitir refresh_tokens (JWT ou opaco) sem prazo de validade nos cenários onde o mesmo é necessário.

#### 5.1.1. ID Token
O Servidor de Autorização deve suportar as disposições especificadas na cláusula 5.2.2.1 de [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e além disso, para atender a requisitos específicos do Perfil de Segurança do Open Finance Brasil, ele deve:
1. deve obrigatoriamente criptografar o id token nos momentos de callback e chamada do endpoint de token;
2. para a criptografia do id token deve ser utilizada chave do tipo enc disponível no JWKS informado no parâmetro jwks_uri do registro do cliente (DCR). O kid da chave utilizada para a criptografia do id token deve ser indicada no atributo kid do cabeçalho do documento JWT;
3. deve sempre incluir a claim acr no id token . O valor do claim acr deve ser um dos valores permitidos conforme definido na sessão Contextos de autenticação (acr);
4. O uso de outros cabeçalhos para indicação da chave utilizada, como x5u, x5c, jku ou jkw é vetado conforme definido na cláusula 2 OIDC-Core .

##### 5.1.1.1. Contextos de autenticação (acr) - "urn:brasil:openbanking:loa2" ou "urn:brasil:openbanking:loa3"
Esse perfil define *urn:brasil:openbanking:loa2 (LoA2)* e *urn:brasil:openbanking:loa3* (LoA3) como novas classes de "Authentication Context Request" (ACR)
- LoA2: mecanismo de autenticação com a adoção de um único fator
- LoA3: mecanismo de autenticação com múltiplos fatores de autenticação
A seguinte orientação deve ser observada para o mecanismo de autenticação das APIs do Open Finance Brasil:
- De acordo com o Art. 17 da Resolução Conjunta nº 01, as instituições devem adotar procedimentos e controles para autenticação de cliente compatíveis com os aplicáveis ao acesso a seus canais de atendimento eletrônicos.
- Em observância à regulação em vigor, sugere-se que: Para a autenticação do usuário em autorizações de acessos às APIs de compartilhamento de dados, os servidores de autorização deveriam adotar, no mínimo, método compatível com LoA2; e Para a autenticação do usuário em autorizações de acessos às API's de iniciação de transação de pagamento ou contratação de serviço/produto, os servidores de autorização deveriam adotar método de autenticação compatível com LoA3 ou superior.
Em todos os casos, a adoção de mecanismo de autenticação mais rigoroso (LoA3 ou superior) fica a critério da instituição transmissora/detentora de conta, de acordo com sua avaliação de riscos e de forma compatível com os mecanismos habitualmente utilizados.Esclarecimentos adicionais sobre fatores de autenticaçãoSão fatores de autenticação:
- Aquilo que você conhece, como uma senha ou frase secreta
- Aquilo que você tem, como um token, smartcard ou dispositivo
- Aquilo que "você é", ou seja, autenticação condicionada a apresentação de uma característica física exclusivamente sua, como a validação por biometria
Para realizar autenticação por múltiplos fatores (MFA) é necessário que o usuário apresente, ao menos, dois diferentes fatores dos listados acima. Um mesmo fator usado mais de uma vez - por exemplo, a apresentação de suas senhas que ele conhece - não pode ser aceito como MFA.
#### 5.1.2. Clarificações sobre a "sub" Claim
Este perfil usa a definição oficial encontrada em: Analise requisitos de criptografia ID_TOKEN. Isso significa que o sub é um identificador nunca transferido ou alterado para o usuário final dentro da emissora (detentora/transmissora).
#### 5.1.3 Escopos obrigatórios no endpoint de descoberta (well-known)
O servidor de autorização deve obrigatoriamente declarar os escopos abaixo em seu endpoint de descoberta (well-known), independentemente se a instituição forneça ou não os produtos referentes aos escopos abaixo listados: 
- invoice-financings
- financings
- loans
- unarranged-accounts-overdraft
- bank-fixed-incomes
- credit-fixed-incomes
- variable-incomes
- treasure-titles
- funds
- exchanges
Os escopos não listados acima devem ser declarados caso a instituição forneça produtos referentes aos mesmos (ex: accounts, payments, etc…).
### 5.2. Cliente confidencial
Cliente confidencial é todo cliente criado através de um método seguro e que possua credenciais específicas de acesso. No ecossistema do Open Finance Brasil, clientes confidenciais são cliente que foram criados através do DCR (Dynamic Client Registration). Um cliente confidencial deve atender as disposições especificadas na cláusula 5.2.3 de [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e além disso, para atender a requisitos específicos do Perfil de Segurança do Open Finance Brasil, ele deve:
1. deve suportar objetos de solicitação criptografados;
2. deve suportar solicitações de autorização PAR (pushed authorization requests);
3. deve suportar o escopo parametrizável ("parameterized scope") como definido no item 6.3.1 de FAPI-LIP ;
4. deve suportar refresh tokens ;
5. não deve incluir um valor específico na claim acr ;
6. deve definir a claim acr como essential ;
7. deve suportar o método de autenticação private_key_jwt ;
8. não deve permitir o recurso de rotação de refresh tokens ;
9. deve enviar o cabeçalho x-fapi-interaction-id em endpoints FAPI

## 6. Considerações de segurança
Os participantes devem apoiar todas as considerações de segurança especificadas na cláusula 8 [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e o [Manual de Segurança de Banco Central do Brasil](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=305).O ICP Brasil emite certificados RSA x509 somente, portanto, para simplificar, a seção remove o suporte para algoritmos EC e exige que apenas algoritmos de criptografia recomendados pela IANA sejam usados.
### 6.1. Considerações sobre assinatura do conteúdo de mensagens (JWS)
Para garantir a integridade e o não-repúdio das informações tramitadas em API's sensíveis e que indicam essa necessidade na sua documentação, deve ser adotado a estrutura no padrão JWS definida na [RFC7515](https://tools.ietf.org/html/rfc7515) e que inclui:
- Cabeçalho (JSON Object Signing and Encryption - JOSE Header), onde se define o algoritmo utilizado e inclui informações sobre a chave pública ou certificado que podem ser utilizadas para validar a assinatura;
- Payload (JWS Payload): conteúdo propriamente dito e detalhado na especificação da API;
- Assinatura digital (JWS Signature): assinatura digital, realizada conforme parâmetros do cabeçalho.

1. Cada elemento acima deve ser codificado utilizando o padrão Base64url RFC4648 e, feito isso, os elementos devem ser concatenados com "." (método JWS Compact Serialization, conforme definido na RFC7515 ).
2. O payload das mensagens (requisição JWT e resposta JWT) assinadas devem incluir as seguintes claims presentes na RFC7519 :

- aud (na requisição JWT): o Provedor do Recurso (p. ex. a instituição detentora da conta) deverá validar se o valor do campo aud coincide com o endpoint sendo acionado;
- aud (na resposta JWT): o cliente da API (p. e. instituição iniciadora) deverá validar se o valor do campo aud coincide com o seu próprio organisationId listado no diretório;
- iss (na requisição JWT e na resposta JWT): o receptor da mensagem deverá validar se o valor do campo iss coincide com o organisationId do emissor;
- jti (na requisição JWT e na resposta JWT): o valor do campo jti deverá ser preenchido com o UUID definido pela instituição de acordo com a [RFC4122] usando o versão 4;
- iat (na requisição JWT e na resposta JWT): o valor do campo iat deverá ser preenchido com horário da geração da mensagem e de acordo com o padrão estabelecido na RFC7519 para o formato NumericDate.
- cty (na requisição JWT e na resposta JWT): o valor do campo cty deverá ser preenchido caso as operações de assinatura ou criptografia aninhadas não sejam empregadas, o uso desse parâmetro de cabeçalho não é recomendado. No caso de assinatura aninhada ou criptografia ser empregada, este parâmetro de cabeçalho deve estar presente; neste caso, o valor deve ser "JWT", para indicar que um JWT aninhado é transportado neste JWT. Embora os nomes dos tipos de mídia não diferenciem maiúsculas de minúsculas, é recomendável que "JWT" sempre seja escrito com caracteres maiúsculos para compatibilidade com implementações herdadas.

1. O content-type HTTP das requisições e respostas com mensagens JWS deve ser definido como: "application/jwt".
2. No cabeçalho JOSE deve constar os seguintes atributos:

- alg - deve ser preenchido com o valor PS256";
- kid - deve ser obrigatoriamente preenchido com o valor do identificador da chave utilizado para a assinatura;
- typ - deve ser preenchido com o valor JWT;
- Em caso de erro na validação da assinatura pelo Provedor do Recurso a API deve retornar mensagem de erro HTTP com status code 400 e a resposta deve incluir na propriedade code do objeto de resposta de erro especificado na API (ResponseError) a indicação da falha com o conteúdo BAD_SIGNATURE.
- Erros na validação da mensagem recebida pela aplicação cliente (p. ex. iniciador de pagamento) devem ser registrados e o Provedor do Recurso (p. ex. instituição detentora de conta) deve ser notificado.

1. O receptor deve validar a consistência da assinatura digital da mensagem JWS exclusivamente com base nas informações obtidas do diretório, ou seja, com base nas chaves publicadas no JWKS da instituição no diretório.
2. As assinaturas devem ser realizadas com uso do certificado digital de assinatura especificado no Padrão de Certificados Open Finance Brasil ;
3. A claim iat deve ser numérica no formato Unix Time GMT+0 com tolerância de +/- 60 segundos;
4. A claim do jti deve ser única para um clientId dentro de um intervalo de tempo de 86.400 segundos (24h), não podendo ser reutilizada neste período. Em caso de reutilização, deverá ser retornado o código de erro HTTP 403. Demais casos seguir instrução da RFC 6749, item 5.2;

### 6.2. Considerações sobre algoritmos de assinatura
Para JWS, clientes e servidores de autorização devem usar o algoritmo PS256;
### 6.3. Considerações de algoritmo de criptografia
Para JWE, clientes e servidores de autorização devem usar RSA-OAEP com A256GCM
### 6.4. Considerações sobre o uso seguro do Transport Layer Security
Para TLS, endpoints do Servidor de Autenticação e endpoints do Servidor de Recursos usados diretamente pelo cliente:
1. devem suportar TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
2. devem suportar TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
3. As funcionalidades "TLS Session Resumption" e "TLS Renegotiation" devem ser desabilitadas

## 7. Considerações sobre o escopo parametrizável
Os mecanismos existentes para gerenciar adequadamente o acesso aos recursos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749) são insuficientes para atender aos requisitos de um ecossistema de compartilhamento de dados moderno. Utilizar strings de escopo estático não fornece aos consumidores controle de granularidade suficiente para controlar o compartilhamento de dados ou gerenciamento de recursos com terceiros. O Open Finance Brasil optou por implementar o escopo parametrizável ([FAPI-LIP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md)) associado a APIs de consentimento/vínculo para gerenciar o acesso granular aos recursos.
### 7.1. Definição de Escopo de Consentimento Dinâmico
Este perfil define o escopo dinâmico do OAuth 2.0 da seguinte maneira:
- string “ consent ”, “ recurring-consent ” ou “enrollment”; e
- delimitador de dois pontos “:”; e
- Consent Resource Id retornado por uma criação bem-sucedida do recurso a ser concedido (ex: consent, recurring-consent, enrollment)
O Consent Resource Id:
- deve incluir caracteres seguros para url;
- deve ser “namespaced”;
- deve ter propriedades de um Nonce ;
Devido as características do Consent Resource ID e por facilidade de implementação, muitas instituições optam por utilizar uma chave UUIDv4 como Consent Resource ID, no entanto isso não é uma regra e cada instituição pode optar por outros métodos desde que sejam respeitadas as regras acima apresentadas e também definidas nas especificações de cada API.
#### 7.1.1. Exemplo de escopo de consentimento dinâmico
Considerando que a instituição transmissora/detentora seja o Banco Exemplo e que a mesma esteja utilizando UUIDv4 como Consent Resource ID, os consentimentos/consentimentos recorrentes/vínculos de dispositivo criados contra esta instituição teriam o seguinte formato, respectivamente:
- consent:urn:bancoexemplo:830ce3c6-e9e7-4800-ae93-3e9b29b470f1
- recurring-consent:urn:bancoexemplo:c9a8a741-39a6-4014-bb75-e05934f9d711
- enrollment:urn:bancoexemplo:eb093d20-ccc5-4242-a271-6658f6663712

## 8. Ciclo de vida do consentimento
O consentimento é um objeto de negócio fundamental, fortemente vinculado aos artefatos de segurança (refresh e access tokens). No entanto, seu ciclo de vida deve ser gerenciado de forma independente, através de sua própria máquina de estados. As especificações funcionais da API publicadas pelo Open Finance Brasil definem as transições de estado, os comportamentos esperados e as condições de erro dos recursos REST protegidos por este perfil, garantindo o controle adequado sobre o ciclo de vida do consentimento.Os requisitos a seguir visam instruir sobre o comportamento do Servidor de Autorização (AS) em relação ao ciclo de vida do consentimento, assegurando que as práticas de autorização estejam alinhadas com as expectativas normativas e a segurança de todo o ecossistema.
### 8.1. Servidor de autorização
Além dos requisitos descritos nas disposições de segurança do Open Finance Brasil, o Servidor de Autorização
1. deve apenas emitir refresh_tokens quando vinculados a um consentimento ativo e válido; Não deve emitir refresh_token quando o consentimento estiver no status “CONSUMED” (para serviços de pagamentos); Deve emitir um access_token por meio de um grant_type do tipo client credentials no status “CONSUMED” (para serviços de pagamentos). Em uma jornada otimizada, deve emitir refresh_tokens enquanto ao menos um dos consentimentos vinculados estiver ativo e válido.
2. só deve compartilhar o acesso aos recursos quando apresentado access_token vinculado a um consentimento ativo e com o status "AUTHORISED“. Para tokens gerados com o scope: payments ou recurring-payments , o status do consentimento não será validado; No cenário de recebimento de token inválido, deve ser retornado status code 401.
3. deve revogar os refresh tokens e, quando aplicável, os access tokens quando o Consentimento (Consent Resource) relacionado for apagado; Em uma jornada otimizada, deve realizar a revogação dos refresh_tokens e access_tokens apenas se ambos os consentimentos vinculados forem revogados.
4. deve garantir que os access tokens são emitidos com os scopes necessários para permitir acesso aos dados especificados em elemento Permission do Consentimento (Consent Resource Object) relacionado;
5. não deve rejeitar pedido de autorização com scopes além do necessário para permitir acesso a dados definidos em elemento Permission do Consentimento (Consent Resource Object) relacionado;
6. pode reduzir o escopo solicitado para um nível que seja suficiente para permitir o acesso aos dados definidos em elemento Permission do Consentimento (Consent Resource Object) relacionado;
7. deve manter registros sobre o histórico dos consentimento para permitir a adequada formação de trilhas de auditoria em conformidade com a regulação em vigor;
8. deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da RFC6749 ) caso o CPF do usuário autenticado não seja o mesmo indicado no elemento loggedUser do Consentimento (Consent Resource Object);
9. deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da RFC6749 ) caso o elemento businessEntity não tenha sido preenchido no Consentimento (Consent Resource Object) relacionado e o usuário tenha selecionado ou se autenticado por meio de credencial relacionada à conta do tipo Pessoa Jurídica (PJ);
10. deve condicionar a autenticação ou seleção de contas do tipo PJ à consistência entre o CNPJ relacionado à(s) conta(s) e o valor presente no elemento businessEntity do Consentimento (Consent Resource Object). Em caso de divergência deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da RFC6749 );
11. deve emitir refresh_token com validade não inferior à validade do consentimento ao qual está relacionado, respeitado os demais critérios acima.

### 8.2. Cliente confidencial
Além dos requisitos descritos nas disposições de segurança do Open Finance Brasil, o Cliente Confidencial
1. deve, sempre que possível, revogar e cessar o uso de refresh e de access tokens vinculados a um consentimento (Consent Resource Object) que foi excluído;
2. deve excluir consentimentos (Consent Resource Objects) que estão expirados;

## Appendix A. Avisos
Copyright (c) 2025 Associação Open Finance BrasilA Associação Open Finance concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita à Associação Open Finance como a fonte do material, mas que tal atribuição o faça não indica endosso da Associação Open Finance.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Associação Open Finance tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Associação Open Finance e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Associação Open Finance convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
## Author's Address
Associação Open Finance - GT SegurançaEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Perfil de Segurança do Open Finance Brasil > Histórico de Especificações - FAPI > FAPI-BR v1.0.0 - Open Finance Brasil Financial-grade API Security Profile > [EN] Open Finance Brasil Financial-grade API Security Profile 1.0

---
id: 240649123
title: [EN] Open Finance Brasil Financial-grade API Security Profile 1.0
version: 5
modified: 2024-03-22T16:39:14.971Z
url: /spaces/OF/pages/240649123/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0
---

## Foreword
Este documento também está disponível em PortuguêsThe Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.Open Finance Brasil Financial-grade API Security Profile 1.0 consists of the following parts:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Banking Brasil Dynamic Client Registration Profile 1.0
These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introduction
The Open Finance Brasil Financial-grade API is a highly secured OAuth profile that aims to provide specific implementation guidelines for security and interoperability which can be applied to APIs in the Brasil Open Finance area that require a higher level of privacy than provided by standard [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html). Among other enhancements, this specification addresses privacy considerations identified in [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) that are relevent in the Open Finance Brasil specifications but have not, so far, been required by other jurisdictions.Although it is possible to code an OpenID Provider and Relying Party from first principles using this specification, the main audience for this specification is parties who already have a certified implementation of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and want to achieve certification for the Brasil Open Finance programme.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml).These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the method of
- applications to obtain the OAuth tokens in an appropriately secure manner for higher risk access to data in a manner that meets the requirements of Open Finance Brasil ;
- applications to use OpenID Connect to identify the customer; and
- applications to use OpenID Connect to assert identity of the customer;
This document is applicable to all participants engaging in Open Finance in Brasil.
## 2. Normative references
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md) - Financial-grade API Security Profile 2.0 - Part 1: Baseline[FAPI-2-Advanced](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Advanced_Profile.md) - Financial-grade API Security Profile 2.0 - Part 2: Advanced[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[OFB-FAPI-DCR](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3.html) - Open Banking Brasil Financial-grade API Dynamic Client Registration Profile 1.0[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings
## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) and ISO29100 apply.
## 4. Symbols and Abbreviated terms

- API - Application Programming Interface
- CSRF - Cross Site Request Forgery
- DCR - Dynamic Client Registration
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- MFA - Multi-Factor Autentication
- OFBIS - Open Finance Brasil Initial Structure
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- TLS - Transport Layer Security

## 5. Brasil Open Finance Security Profile

### 5.1. Introduction
The Brasil Open Finance Security profile specifies additional security and identity requirements for high risk API resources protected by the OAuth 2.0 Authorization Framework that consists of [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html), [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and other specifications.This profile describes security and features provisions for a server and client that are necessary for the Brasil Open Finance Programme by defining the measures to mitigate or address:
- attacks that address privacy considerations identified in clause 9.1 of [FAPI1 Advanced]
- the requirement to support fine-grained access to resources for data minimisation purposes
- the requirement to convey the Authentication Context Request that was performed by an OpenID Provider to a Client to enable a appropriate client management of customer conduct risk.
- the requirement for clients to assert a pre-existing customer relationship by asserting a customer identity claim as part of the authorization flow.

### 5.2. Open Finance Brasil security provisions

#### 5.2.1. Introduction
Open Finance Brasil has a requirement to address privacy considerations that were identified but not addressed in the [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) final specification without imposing additional requirements on Authorisation Servers being proposed in [FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md).Participants in this ecosystem have a need for clients to request an openid provider to confirm values of identity claims as part of an authorization request using the mechanism defined in clause 5.5.1 of [OIDC](https://openid.net/specs/openid-connect-core-1_0.html).The use of the claims parameter to request explicit claims values requires clients to ensure that they encrypt the request object to avoid information leakage. This risk is identified in clause 7.4.1 of [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html).In addition this profile describes the specific scope, acr and client management requirements necessary to support the wider Open Finance Brasil ecosystem.As a profile of the OAuth 2.0 Authorization Framework, this document mandates the following for the Brasil Open Finance Security profile.
#### 5.2.2. Authorization server
The Authorization Server shall support the provisions specified in clause 5.2.2 of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)In addition, the Authorization Server
1. shall support a signed and encrypted JWE request object passed by value or shall require pushed authorization requests PAR ;
2. shall distribute discovery metadata (such as the authorization endpoint) via the metadata document as specified in OIDD and [RFC8414] (".well-known");
3. shall support the claims parameter as defined in clause 5.5 OpenID Connect Core ;
4. shall support the oidc standard claim "cpf" as defined in clause "sub" Claim clarifications of this document;
5. shall support the oidc standard claim "cnpj" as defined in clause Requesting the "cpf" Claim of this document if the institution provides accounts for legal person;
6. shall support the acr "urn:brasil:openbanking:loa2" as defined in clause Requesting the "cnpj" Claim of this document;
7. should support the acr "urn:brasil:openbanking:loa3" as defined in clause Requesting the "cnpj" Claim of this document;
8. shall implement the userinfo endpoint as defined in clause 5.3 OpenID Connect Core ;
9. shall support parameterized OAuth 2.0 resource scope consent as defined in clause 6.3.1 OIDF FAPI WG Lodging Intent Pattern ;
10. may support Financial-grade API: Client Initiated Backchannel Authentication Profile ;
11. (withdrawn temporarily);
12. shall support refresh tokens;
13. shall issue access tokens with an expiry no greater than 900 seconds and no less than 300 seconds;
14. shall always include an acr claim in the `id_token` ;
15. shall support the `response_type` value `code id_token` ;
16. may support `response_type` value `code` in conjunction with the `response_mode` value `jwt` ;
17. should offer the possibility to disable the rotation of `refresh token` ;
18. shall ensure that, in case of sharing the Authorization Server for other services, in addition to Open Finance, it does not disclose and/or allow the use of non-certified methods in the Open Finance environment;
19. shall ensure that the settings disclosed to other participants through `OpenID Discovery` (indicated by the `Well-Known` file registered in the Directory) are restricted to the operating modes to which the institution has certified; shall keep in your settings the methods for which there are still active clients; shall update the records that use non-certified methods, through bilateral treatment between the institutions involved;
20. shall refuse requests, for the Open Finance environment, that are outside the modes of operation to which the institution has certified its Authorization Server;
21. must refuse authentication requests that include an id_token_hint, as the id_token held by the requester may contain Personally Identifiable Information, which could be sent unencrypted by the public client;
22. the minimum expiration time of `request_uri` must be 60 seconds;
23. shall deny all requests without header `x-fapi-interaction-id` on FAPI endpoints;

##### 5.2.2.1. ID Token as detached signature
The Authorization Server shall support the provisions specified in clause 5.2.2.1 of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)In addition, if the `response_type` value `code id_token` is used, the Authorization Server:
1. should not return sensitive PII in the ID Token in the authorization response, but if it needs to, then it shall encrypt the ID Token;
2. Personally Identifiable Information may include, but is not limited to,: Claim `sub` if you use information that makes it possible to identify the natural person; The default Claims defined in clause 5.1 OIDC , which may contain data such as date of birth, address or telephone; The new Claim CPF, defined in the next section.
3. If a Claim containing Personally Identifiable Information is requested: If this is marked as essential, if there is no encryption key registered for the Customer, the request must fail if requested at the Authorization Endpoint. There are no impediments if the request is made by the Confidential Client through the Token Endpoint; If this is not marked as essential, the Authorization Server must omit it on the Authorization Endpoint, and it can be answered on the Token Endpoint called by the Confidential Client.
4. For the encryption of the id_token, a key available in the `JWKS` informed in the `jwks_uri` parameter during the client registration must be used, indicated through the `kid` header of the JWT document;
5. The use of other headers to indicate the key used, such as `x5u` , `x5c` , `jku` or `jkw` is prohibited as defined in clause 2 OIDC .

##### 5.2.2.2. "sub" Claim clarifications
This profile uses the official openId definition found at: [Analise requisitos de criptografia ID_TOKEN](/wiki/spaces/OF/pages/240649215). This means the sub is a never reassigned identifier for the end user. The value for a given user should never change within an institution, even across diferents consents.
##### 5.2.2.3. Requesting the "cpf" Claim
This profile defines "cpf" as a new standard claim as per clause 5.1 [OIDC](https://openid.net/specs/openid-connect-core-1_0.html)The **CPF** number (Cadastro de Pessoas Físicas, [sepeˈɛfi]; Portuguese for "Natural Persons Register") is the **Brazilian** individual taxpayer registry identification. This number is attributed by the **Brazilian** Federal Revenue to Brazilians and resident aliens who, directly or indirectly, pay taxes in **Brazil**.In the Brasil Open Finance identity model, the cpf is a string consisting of numbers that is 11 characters long and may start with a 0.If the cpf Claim is requested as an Essential Claim for the ID Token or UserInfo response with a values parameter requesting a specific cpf value, the Authorization Server MUST return a cpf Claim Value that matches the requested value.If the cpf Claim is requested as an Essential Claim for the ID Token or UserInfo response, the Authorization Server shall return a cpf Claim Value with the authenticated user cpf value.If this is an Essential Claim and the requirement cannot be met or is not compatible with the one requested, then the Authorization Server shall treat that outcome as a failed authentication attempt.Name: cpf, Type: String, Regex: 'd{11}$'
##### 5.2.2.4. Requesting the "cnpj" Claim
This profile defines "cnpj" as a new standard claim as per clause 5.1[OIDC](https://openid.net/specs/openid-connect-core-1_0.html)**CNPJ**, short for Cadastro Nacional de Pessoas Jurídicas, is an identification number of **Brazilian** companies issued by the **Brazilian** Ministry of Revenue, **in** Portuguese "Secretaria da Receita Federal" or "Ministério da Fazenda". In the Brasil Open Finance identity model, individuals can associated with 0 or more CNPJs. A CNPJ is a string consisting of numbers that is 14 digits long and may start with a 0, the first eight digits identify the company, the four digits after the slash identify the branch or subsidiary ("0001" defaults to the headquarters), and the last two are checksum digits. For this profile, the cnpj claim must be requested and supplied as the 14 digit number.If the **cnpj** Claim is requested as an Essential Claim for the ID Token or UserInfo response with a values parameter requesting a specific **cnpj** value, the Authorization Server **SHALL** return a **cnpj** Claim Value that contains a **set** of CNPJs one of which must match the requested value.If the **cnpj** Claim is requested as an Essential Claim for the ID Token or UserInfo the Authorization Server MUST return a cnpj Claim Value that contains a **set** of CNPJs one of which must match a CNPJ belonging to the authenticated user's account.If this is an Essential Claim and the requirement cannot be met, then the Authorization Server shall treat that outcome as a failed authentication attempt.Name: cnpj, Type: Array of Strings, Array Element Regex: 'd{14}$'
##### 5.2.2.5. Requesting the "urn:brasil:openbanking:loa2" or "urn:brasil:openbanking:loa3" Authentication Context Request
This profile defines "urn:brasil:openbanking:loa2" and "urn:brasil:openbanking:loa3" as new Authentication Context Request (ACR) classes.
- LoA2: Authentication performed using single factor;
- LoA3: Authentication performed using multi factor (MFA)
The following rules are applicable to the authentication mechanism of Open Finance Brazil API's:
- In accordance to Art. 17 of Joint Resolution nº 01 - Open Banking Brasil , institutions must adopt procedures and controls for client authentication compatible with those applicable in their electronic service channels .
- In accorcdance with the regulation, it is suggested that: For Read-Only APIs (Phase 2) : the Authorization Servers should adopt, at least, an authentication method compatible with `LoA2` ; and For Read-Write API's (subsequent phases) : the Authorization Servers should adopt an authentication method compatible with `LoA3` or higher.
In all cases, the adoption of a more rigorous authentication mechanism (`LoA3` or higher) is at the discretion of the Bank (ASPSP), according to its risk assessment and in a manner compatible with the mechanisms usually employed.**Authentication factors clarification**The authentication methods are:
- Something you know , such as password or phrase
- Something you have , such as token, smartcard or device
- Something you are , meaning an authentication that makes use of physical characteristics, such as biometric validation.
To performe a MFA authentication is necessary that the end user presents at least two different methods as listed above. A unique method used more than once - ie. presenting passwords - is not accepted as MFA.
#### 5.2.3. Confidential client
A confidential client shall support the provisions specified in clause 5.2.3 of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html),In addition, the confidential client
1. shall support encrypted request objects;
2. shall support Pushed Authorisation Requests PAR ;
3. shall use encrypted request objects if not using PAR ;
4. shall support parameterized OAuth 2.0 resource scope consent as defined in clause 6.3.1 OIDF FAPI WG Lodging Intent Pattern ;
5. shall support refresh tokens;
6. shall not populate the `acr` claim with required values;
7. shall require the `acr` claim as an essential claim;
8. shall support all authentication methods specified in clause 5.2.2-14 of Financial-grade API Security Profile 1.0 - Part 2: Advanced including diferent combinations of the methods to send requests (using PAR or not - item 11);
9. shall not allow `refresh tokens` rotation feature;
10. should not request authentication requests that include an id_token_hint, as the id_token to be used may contain Personally Identifiable Information, which could be sent unencrypted through the public client;
11. shall send header `x-fapi-interaction-id` on FAPI endpoints;

## 6. Security considerations
Participants shall support all security considerations specified in clause 8 [Financial-grade API Security Profile 1.0 - Part 1: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and the [Brazilian Central Bank Open Banking Security Manual](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=134). The Brazilian ICP issues RSA x509 certificates only therefor section removes for simplicity support for EC algorithms and requires that only IANA recommended encryption algorithms be used.
### 6.1. Message Content Signing Considerations (JWS)

1. JWS standad defined in RFC7515 shall be adopted to ensure integrity and non-repudiation of information processed in sensitive API's (message sign requirement is indicated at API's documentation/swagger) , which includes: 
- Header ( JSON Object Signing and Encryption - JOSE Header ), which defines the algorithm used and includes information about the public key or certificate that can be used to validate the signature;
- Payload ( JWS Payload ): content itself as detailed in the API specification;
- Digital signature ( JWS Signature ): digital signature, performed according to header parameters.
2. Each of elements above must be encoded using the Base64url pattern RFC4648 and the elements must be concatenated with "." (JWS Compact Serialization method as defined in RFC7515 ).
3. The payload of signed messages (request JWT and response JWT ) shall include the following claims as defined at RFC7519 : 
- aud (in the JWT request): the Resource Provider (eg the institution holding the account) must validate if the value of the aud field matches the endpoint being triggered;
- aud (in JWT response): the API client (eg initiating institution) shall validate if the value of the aud field matches its own `organisationId` listed in the directory;
- iss (in the JWT request and in the JWT response): the receiver of the message shall validate if the value of the iss field matches the `organisationId` of the sender;
- jti (in the JWT request and in the JWT response): the value of the jti field shall be filled with the UUID defined by the institution according to [RFC4122] version 4;
- iat (in the JWT request and in the JWT response): the iat field shall be filled with the message generation time and according to the standard established in RFC7519 to the NumericDate format.
- cty (in the JWT request and in the JWT response): the cty field shall be filled in the normal case in which nested signing or encryption operations are not employed, the use of this Header Parameter is not recommended. In the case that nested signing or encryption is employed, this Header Parameter must be present; in this case, the value must be "JWT", to indicate that a Nested JWT is carried in this JWT. While media type names are not case sensitive, it is recommended that "JWT" always be spelled using uppercase characters for compatibility with legacy implementations.
4. The HTTP content-type of requests and responses with JWS messages shall be defined as: "application/jwt".
5. The JOSE header must contain the following attributes: 
- alg - shall be filled with the value `PS256` ";
- kid - shall be filled with the key identifier value used for the signature;
- typ - shall be filled with the value `JWT` .
- In case of error in signature validation by `Resource Provider` the API provider shall return HTTP error message with `status code` 400 and the `ResponseError` content shall include, in the `code` property, the content `BAD_SIGNATURE` .
- Errors in validating the signed messages received by the client application (eg payment initiator) must be logged and the `Resource Provider` (eg account holding institution) must be notified.
6. The receiver shall validate the consistency of the JWS message's digital signature exclusively based on the information obtained from the directory , that is, based on the keys published in the institution's JWKS in the directory.
7. Signatures must be performed using the digital signature certificate specified in the Open Finance Brazil Certificates Standard ;
8. the iat claim must be numeric in Unix Time format GMT+0 with a tolerance of +/- 60 seconds;
9. the jti claim must be unique for a clientId within a time frame of 86,400 seconds (24h), and cannot be reused within this period. In case of reuse, the HTTP error code 403 shall be return. Any other case must follow RFC 6749 instructions in item 5.2.

### 6.1.1. Signing algorithm considerations
For JWS, both clients and Authorization Servers
1. shall use PS256 algorithm;

#### 6.1.2. Encryption algorithm considerations
For JWE, both clients and Authorization Servers
1. shall use RSA-OAEP with A256GCM

#### 6.1.3. Secure Use of Transport Layer Security considerations
For TLS, Authorization Server endpoints and Resource Server endpoints used directly by the Client
1. shall support `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
2. shall support `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
3. The "TLS Session Resumption" e "TLS Renegotiation" features shall be disabled

## 7. Data Sharing Considerations

### 7.1. Authorisation Mechanism

#### 7.1.1. Introduction
Existing mechanisms for appropriately managing access to resources defined in [RFC6749](https://tools.ietf.org/html/rfc6749) are insufficient to meet the requirements for a modern data sharing ecosystem. Leveraging static scope strings does not provide consumers control of sufficient granularity to share with third parties. Open Finance Brasil have elected to implement a [Consent API](https://openbanking-brasil.github.io/areadesenvolvedor/swagger/swagger_consents_apis.yaml) as a OAuth 2.0 protected resource that can be used to manage fine grain access to resources. The reference to the Consent Resource will be conveyed as part of an OAuth 2.0 dynamic resource scope.
#### 7.1.2. Dynamic Consent Scope Definition
This profile defines OAuth 2.0 dynamic scope "consent" as follows:
- string 'consent'; and
- delimiter of a colon ":"; and
- Consent API REST Resource Id as returned by a successful creation of Open Finance Consent Resource ;
In addition:
- the Consent Resource Id must include url safe characters only;
- the Consent Resource Id must be namespaced;
- the Consent Resource Id must have the properties of a nonce Nonce ;

#### 7.1.3. Dynamic Consent Scope Example
consent:urn:bancoex:C1DD33123
### 7.2. Authorisation Life Cycle

#### 7.2.1. Introduction
The Consent Resource has a life cycle that is managed seperately and distinctly from the OAuth 2.0 Authorisation Framework. The state transitions and expected behaviours and error conditions expected of REST Resources protected with this profile are defined in the functional API specifications published by Open Finance Brasil.
#### 7.2.2. Authorization server
In addition to the requirements outlined in Open Finance Brasil security provisions the Authorization Server
1. shall only issue refresh_tokens when linked to an active and valid consent; Must not issue refresh_token when consent status is "CONSUMED" (for phase 3); Must issue an access_token through the grant_type client credentials when consent status is "CONSUMED"(for phase 3).
2. shall only share access to resources when presented access_token linked to an active consent and with the status "AUTHORISED“. For tokens generated with the scope: payments, the status of the consent will not be validated. In the scenario of receiving an invalid token, status code 401 should be returned.
3. shall revoke refresh tokens and, access tokens where aplicable, when the linked Consent Resource is deleted;
4. shall ensure access tokens are issued with sufficient scope necessary for access to data specified in the Permission element of a linked Consent Resource object;
5. shall not reject an authorisation request requesting scopes broader than those necessary to access data specified in the Permissions element of a linked Consent Resource object;
6. may reduce requested scope to a level sufficient to enable access to data resources specified in the Permissions element of a linked Consent Resource object;
7. shall retain a complete audit history of the consent resource in accordance with current Central Bank brazilian regulation;
8. shall return authentication failure and return code _access denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 ) if the CPF of the authenticated user is not the same as indicated in the loggedUser element of the Consent Resource Object;
9. shall return authentication failure and return code _access denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 ) if the businessEntity element has not been populated in the related Consent Resource Object and the user has selected or authenticated by using a credential related to a business account;
10. an autenticated or selected business account's CNPJ must match the value present in the businessEntity element of the Consent Resource Object. In case of divergence authorization server shall return authentication failure and return code _access denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 );
11. shall ensure _refresh tokens expiration time is at least equal to the linked consent resource expiration time.

#### Confidential Client
In addition to the requirements outlined in Open Finance Brasil security provisions the Confidential Client
1. shall revoke where possible and cease usage of refresh and access tokens that are bound to a Consent Resource that has been deleted;
2. shall delete Consent Resource that are expired;

## 8. Acknowledgements
With thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- Alexandre Siqueira (Mercado Pago)
- Joseph Heenan (Authlete)
- Marcos Rodrigues (Itaú)
- Mário Ginglass (BNDES)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## Appendix A. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
## Author's Address
**OFBIS GT Security**Open Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Perfil de Segurança do Open Finance Brasil > Histórico de Especificações - FAPI > FAPI-BR v1.0.0 - Open Finance Brasil Financial-grade API Security Profile > [PT] Open Finance Brasil Financial-grade API Security Profile 1.0

---
id: 240649033
title: [PT] Open Finance Brasil Financial-grade API Security Profile 1.0
version: 4
modified: 2024-03-19T17:37:16.199Z
url: /spaces/OF/pages/240649033/PT+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0
---

## Prefácio
The normative version in [English](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-financial-api-1_ID3.html)A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar padrões e especificações necessárias para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos autorais ou patenteados. O EIOFB não se responsabiliza pela identificação de qualquer ou todos esses direitos.O Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Finance Brasil Dynamic Client Registration Profile 1.0
Estas partes são destinados a serem usados com [RFC6749], [RFC6750], [RFC7636], [OIDC], [FAPI-1-Baseline] e [FAPI-1-Advanced]
## Introdução
A Financial-grade API do Open Finance Brasil é um perfil OAuth altamente seguro que visa fornecer diretrizes de implementação específicas para segurança e interoperabilidade que podem ser aplicadas a APIs na área de Open Finance do Brasil que requerem um nível de privacidade superior ao fornecido pelo padrão [Financial-grade API Security Profile 1.0 - Part 2: Advanced][FAPI-1-Advanced]. Entre outras melhorias, esta especificação aborda considerações de privacidade identificadas em [FAPI-1-Advanced] que são relevantes nas especificações do Open Finance Brasil, mas não foram, até agora, exigidas por outras jurisdições.Embora seja possível codificar um provedor de OpenID e parte de confiança a partir dos primeiros princípios usando esta especificação, o público principal para esta especificação são as partes que já possuem uma implementação certificada do [Financial-grade API Security Profile 1.0 - Part 2: Advanced][FAPI-1-Advanced] e deseja obter a certificação para o programa Brasil Open Finance.
## Convenções Notacionais
As palavras-chave "*deve*" (shall), "*não deve*" (shall not), "*deveria*" (should), "*não deveria*" (should not) e "*pode*" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2][ISODIR2] observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## Escopo
Este documento especifica o método para os aplicativos
- obterem de maneira segura os tokens OAuth necessários para acesso a dados críticos de acordo com os requisitos do Open Finance Brasil ;
- utilizarem o OpenID Connect para identificação do usuário do Open Finance; e
- utilizarem o OpenID Connect para afirmar a identidade do cliente.
Este documento é aplicável a todos os participantes do Open Finance no Brasil.
## Referências normativas
Os seguintes documentos referenciados são indispensáveis para a adoção das especificações deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, deve-se aplicar a última edição do documento referenciado (incluindo quaisquer emendas).[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md) - Financial-grade API Security Profile 2.0 - Part 1: Baseline[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[OFB-FAPI-DCR](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3.html) - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings
## Termos e definições
Para efeitos deste documento, os termos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e ISO29100 se aplicam.
## Símbolos e termos abreviados

- API - Application Programming Interface (Interface de programação de aplicativo)
- CSRF - Cross Site Request Forgery
- DCR - Registro de cliente dinâmico
- EIOFB - Estrutura Inicial do Open Finance Brasil
- FAPI - Financial-grade API
- HTTP - Protocolo de transferência de hipertexto
- MFA - Multi-Factor Authentication (Autenticação por Múltiplos Fatores)
- OIDF - OpenID Foundation
- REST - Representational State Transfer (Transferência de Estado Representacional)
- TLS - Transport Layer Security (Segurança da Camada de Transporte)

## Profile de Segurança para o Open Finance Brasil

### Introdução
O perfil de segurança do Open Finance Brasil especifica requisitos adicionais de segurança e de identificação para o acesso a API´s com recursos críticos protegidas pelo OAuth 2.0 Authorization Framework, que consiste em [RFC6749], [RFC6750], [RFC7636], [FAPI-1-Baseline], [FAPI-1-Advanced] e outras especificações.Este perfil descreve as capacidades e os recursos de segurança que devem ser oferecidos por servidores e clientes que são necessários para o Programa do Open Finance Brasil, definindo as medidas para mitigar ou endereçar:
- ataques que abordam considerações de privacidade identificadas na cláusula 9.1 de [FAPI-1 Advanced].
- o requisito de concessão de acesso granular a recursos, com vistas à minimização de dados;
- o requisito de informar sobre o contexto da autenticação do usuário (claim Authentication Context Request - acr) que foi realizada por um Provedor OpenID, com vistas a favorecer o adequado gerenciamento do risco decorrente do acesso do usuário;
- o requisito para que os clientes de API declarem um relacionamento prévio com o usuário, afirmando em uma `claim` de identificação do usuário como parte do fluxo de autorização.

### Disposições de segurança do Open Finance Brasil

#### Introdução
O Open Finance Brasil tem um requisito para endereçar considerações de privacidade que foram identificadas, mas não abordadas na especificação final [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html), sem impor requisitos adicionais aos Servidores de Autorização que estão sendo propostos em [FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md).Os participantes desse ecossistema precisam que os clientes de API solicitem a um provedor openid a confirmação dos valores das `claims` de identificação do usuário como parte de uma solicitação de autorização usando o mecanismo definido na cláusula 5.5.1 de [OIDC].O uso do parâmetro `claims` para solicitar a validação de valores de identificação explícitos requer que os clientes de API protejam com criptografia o Request Object para evitar vazamento de informações. Este risco é identificado na cláusula 7.4.1 do [FAPI-1-Baseline].Além disso, este perfil descreve o escopo específico, valores de `acr` e requisitos de gerenciamento de clientes necessários para dar suporte ao ecossistema Open Finance Brasil mais amplo.Como um perfil do OAuth 2.0 Authorization Framework, este documento exige o seguinte para o perfil de segurança do Open Finance Brasil.
#### Servidor de Autorização
O Servidor de Autorização **deve** suportar as disposições especificadas na cláusula 5.2.2 de [Financial-grade API Security Profile 1.0 - Parte 2: Advanced] [FAPI-1-Advanced].Além disso, ele deve:
1. deve suportar Request Objects JWE assinados e criptografados passados por valor ou deve exigir requisições do tipo "pushed authorization requests" [PAR];
2. deve publicar metadados de descoberta (incluindo a do endpoint de autorização) por meio do documento de metadado especificado em [OIDD] e [RFC8414] (".well-known");
3. deve suportar os parâmetros `claims` como definido no item 5.5 do [OpenID Connect Core][OIDC];
4. deve suportar o atributo `claim` padrão oidc "cpf" conforme definido no item 5.2.2.2 deste documento;
5. deve suportar o atributo `claim` padrão oidc "cnpj" conforme definido no item 5.2.2.3 deste documento, se a instituição for detentora de conta para pessoas jurídicas;
6. deve suportar o atributo `acr` "urn:brasil:openbanking:loa2" como definido no item 5.2.2.4 deste documento;
7. deveria suportar o atributo `acr` "urn:brasil:openbanking:loa3" como definido no item 5.2.2.4 deste documento;
8. deve implementar o endpoint "userinfo" como definido no item 5.3 do [OpenID Connect Core][OIDC];
9. deve suportar o escopo parametrizável ("parameterized OAuth 2.0 resource scope") consent como definido no item 6.3.1 de [OIDF FAPI WG Lodging Intent Pattern][LIWP];
10. pode suportar [Financial-grade API: Client Initiated Backchannel Authentication Profile][FAPI-CIBA];
11. (requisito temporariamente retirado);
12. deve suportar `refresh tokens` ;
13. deve emitir `access tokens` com o tempo de expiração entre 300 (mínimo) e 900 (máximo) segundos;
14. deve sempre incluir a claim `acr` no id_token;
15. deve suportar os valores `code` e `id_token` para o atributo `response_type` ;
16. pode suportar o valor `code` para o atributo `response_type` em conjunto com o valor `jwt` para o atributo `response_mode` ;
17. não deve permitir o recurso de rotação de `refresh tokens` ;
18. deve garantir que em caso de compartilhamento do Servidor de Autorização para outros serviços, além do Open Finance, não divulgue e/ou possibilite o uso de métodos não certificados no ambiente do Open Finance;
19. deve garantir que as configurações divulgadas aos demais participantes através do `OpenID Discovery` (indicado pelo arquivo de `Well-Known` cadastrado no Diretório) sejam restritos aos modos de operação aos quais a instituição se certificou; deve manter em suas configurações os métodos para os quais ainda hajam clientes ativos; deve atualizar os cadastros que utilizem métodos não certificados, através de tratamento bilateral entre as instituições envolvidas;
20. deve recusar requisições, para o ambiente do Open Finance, que estejam fora dos modos de operação ao qual a instituição certificou seu Servidor de Autorização;
21. deve recusar requisições de autenticação que incluam um id_token_hint, visto que o id_token em posse do requisitante pode conter Informação de Identificação Pessoal, que poderia ser enviada descriptografada pelo cliente público;
22. o tempo mínimo de expiração do `request_uri` deve ser de 60 segundos;
23. deve recusar requisições que não apresentem o cabeçalho `x-fapi-interaction-id` em endpoints FAPI;

##### Token de ID como assinatura separada
O Servidor de Autorização *deve* suportar as disposições especificadas na cláusula 5.2.2.1 de [Financial-grade API Security Profile 1.0 - Parte 2: Advanced] [FAPI-1-Advanced]Além disso, se o valor `response_type` `code id_token` for usado, o servidor de autorização:
1. não deveria retornar Informação de Identificação Pessoal (PII) confidenciais no token de ID na resposta de autorização, mas se for necessário, então ele deve criptografar o token de ID.
2. Informação de Identificação Pessoal pode incluir, mas não está restrito a: Claim `sub` caso use informação que possibilite a identificação da pessoa natural; As Claims padrões definidas na cláusula 5.1 [OIDC], que podem conter dados como data de nascimento, endereço ou telefone; A nova Claim CPF, definida na próxima seção.
3. Caso seja solicitada alguma Claim contendo Informação de Identificação Pessoal: Se esta for marcada como essencial, em não se havendo chave de criptografia registrada para o Cliente, deverá falhar a requisição se for solicitada no Endpoint de Autorização. Não há impedimentos caso a solicitação seja feita pelo Cliente Confidencial através do Endpoint de Token; Se esta não for marcada como essencial, o Servidor de Autorização deverá omiti-la no Endpoint de Autorização, podendo ser respondida no Endpoint de Token chamado pelo Cliente Confidencial.
4. Para a criptografia do id_token deve ser utilizada chave disponível no `JWKS` informado no parâmetro `jwks_uri` durante o registro do cliente, indicada através do cabeçalho `kid` do documento JWT;
5. O uso de outros cabeçalhos para indicação da chave utilizada, como `x5u` , `x5c` , `jku` ou `jkw` é vetado conforme definido na cláusula 2 [OIDC].

##### Clarificações sobre a "sub" Claim
Este perfil usa a definição oficial encontrada em: [https://github.com/OpenBanking-Brasil/specs-seguranca/tree/main/idtoken_review.](https://github.com/OpenBanking-Brasil/specs-seguranca/tree/main/idtoken_review.) Isso significa que o sub é um identificador nunca transferido ou alterado para o usuário final. O valor para um dado usuário nunca deve mudar dentro de uma instituição, mesmo em diferentes consentimentos.
##### Solicitando uma "claim" cpf
Este perfil define "cpf" como uma nova `claim` padrão de acordo com cláusula 5.1 [OIDC]O número do **CPF** (Cadastro de Pessoas Físicas, [sepeˈɛfi]; português para "Registro de Pessoas Físicas") é o cadastro de pessoa física **brasileira**. Este número é atribuído pela Receita Federal **Brasileira** para brasileiros e estrangeiros residentes que, direta ou indiretamente, pagar impostos no **Brasil**.No modelo de identidade do Open Finance Brasil, o cpf é uma string composta por números 11 caracteres de comprimento e podem começar com 0.Se a Claim **cpf** for solicitada como essencial para constar no ID token ou na resposta ao endpoint de UserInfo e na solicitação constar no parâmetro `value` com determinado **CPF** exigido, o Authorization Server **DEVE** retornar no atributo **cpf**o valor que corresponda ao da solicitação.Se a Claim **cpf** for solicitada como essencial para constar no ID Token ou na resposta no endpoint de UserInfo, o Authorization Server deve retornar no atributo **cpf** o valor com o **CPF** do usuário autenticado.Se a Claim **cpf** indicada como essencial não puder ser preenchida ou não for compatível com o requisito, o Authorization Server deve tratar a solicitação como uma tentativa de autenticação com falha.Se a Claim **cpf** indicada como essencial for solicitada no endpoint de Autorização, deverá seguir as regras definidas na seção 5.2.2.1.Nome: cpf, Tipo: String, Regex: '^\d{11}$'
##### Solicitando a "claim" cnpj
Este perfil define "cnpj" como uma nova reivindicação padrão de acordo com cláusula 5.1 [OIDC]**CNPJ**, abreviação de Cadastro Nacional de Pessoas Jurídicas, é um número de identificação de empresas **brasileiras** emitidas pelo Ministério da Fazenda **brasileira**, **na**"Secretaria da Receita Federal" ou "Ministério da Fazenda" do Brasil. No modelo de identidade do Open Finance Brasil, pessoas físicas podem se associar a 0 ou mais CNPJs. Um CNPJ é uma string que consiste em números de 14 dígitos e pode começar com 0, os primeiros oito dígitos identificam a empresa, os quatro dígitos após a barra identificam a filial ou subsidiária ("0001" padrão para a sede), e os dois últimos são dígitos de soma de verificação. Para este perfil, o pedido de cnpj deve ser solicitado e fornecido como o número de 14 dígitos.Se a Claim **cnpj** for solicitada como essencial para constar no ID Token ou na resposta ao endpoint UserInfo e na solicitação constar, no parâmetro `value`, determinado **CNPJ** exigido, o Authorization Server **DEVE** retornar no atributo **cnpj**um **conjunto** de **CNPJs** relacionado com o usuário, um dos quais deve incluir valor que corresponda ao da solicitação.Se a Claim **cnpj** for solicitada como essencial para constar no ID Token ou na resposta ao endpoint UserInfo, o Authorization Server deve incluir no ID Token ou na resposta ao endpoint UserInfo um **conjunto** que inclua um elemento com o número do **CNPJ** relacionado à conta utilizada na autenticação do usuário.Se a Claim **cnpj** indicada como essencial não puder ser preenchida ou validada, o Authorization Server deve tratar a solicitação como uma tentativa de autenticação com falha.Nome: cnpj, Tipo: Array of Strings, Array Element Regex: '^\d{14}$'
##### Solicitando o "urn:brasil:openbanking:loa2" ou "urn:brasil:openbanking:loa3" Solicitação de contexto de autenticação
Esse perfil define "urn:brasil:openbanking:loa2" e "urn:brasil:openbanking:loa3" como novas classes de "Authentication Context Request" (ACR)
- LoA2 : mecanismo de autenticação com a adoção de um único fator
- LoA3 : mecanismo de autenticação com múltiplos fatores de autenticação
A seguinte orientação deve ser observada para o mecanismo de autenticação das APIs do Open Finance Brasil:
- De acordo com o Art. 17 da Resolução Conjunta nº 01, as instituições devem adotar procedimentos e controles para autenticação de cliente compatíveis com os aplicáveis ao acesso a seus canais de atendimento eletrônicos .
- Em observância à regulação em vigor, sugere-se que: Para a autenticação do usuário em autorizações de acessos às APIs de compartilhamento de dados (Fase 2) , os Authorization Servers deveriam adotar, no mínimo, método compatível com `LoA2` ; e Para a autenticação do usuário em autorizações de acessos às API´s das fases subsequentes , os Authorization Servers deveriam adotar método de autenticação compatível com `LoA3` ou superior.
Em todos os casos, a adoção de mecanismo de autenticação mais rigoroso (`LoA3` ou superior) fica a critério da instituição transmissora ou detentora de conta, de acordo com sua avaliação de riscos e de forma compatível com os mecanismos habitualmente utilizados.
##### Esclarecimentos adicionais sobre fatores de autenticação
São fatores de autenticação:
- Aquilo que você conhece , como uma senha ou frase secreta
- Aquilo que você tem , como um token, smartcard ou dispositivo
- Aquilo que "você é" , ou seja, autenticação condicionada a apresentação de uma característica física exclusivamente sua, como a validação por biometria
Para realizar autenticação por múltiplos fatores (MFA) é necessário que o usuário apresente, ao menos, dois diferentes fatores dos listados acima. Um mesmo fator usado mais de uma vez - por exemplo, a apresentação de suas senhas que ele conhece - não pode ser aceito como MFA.
#### Cliente confidencial
Um cliente confidencial deve apoiar as disposições especificadas na cláusula 5.2.3 de
[Financial-grade API Security Profile 1.0 - Part 2: Advanced][FAPI-1-Advanced],Além disso, o cliente confidencial
1. deve suportar objetos de solicitação encrypted ;
2. deve suportar solicitações de autorização push (pushed authorization requests) [PAR];
3. deve usar objetos de solicitação encrypted se não usar [PAR];
4. deve suportar o escopo de recurso OAuth 2.0 parametrizado consent conforme definido na cláusula 6.3.1 [OIDF FAPI WG Lodging Intent Pattern][LIWP];
5. deve suportar `refresh tokens` ;
6. não deve incluir um valor específico na claim `acr` ;
7. deve definir a claim `acr` como essential ;
8. deve suportar todos os métodos de autenticação especificados no item 14 da seção 5.2.2 da [Financial-grade API Security Profile 1.0 - Part 2: Advanced][FAPI-1-Advanced] incluindo as diferentes combinações de métodos de encaminhamento dos Requests Objects (usando ou não [PAR] - item 11);
9. não deve permitir o recurso de rotação de `refresh tokens` ;
10. não deve solicitar requisições de autenticação que incluam um id_token_hint, visto que o id_token a ser utilizado pode conter Informação de Identificação Pessoal, que poderia ser enviada descriptografada através do cliente público;
11. deve enviar o cabeçalho `x-fapi-interaction-id` em endpoints FAPI;

## Considerações de segurança
Os participantes devem apoiar todas as considerações de segurança especificadas na cláusula 8
 [Financial-grade API Security Profile 1.0 - Parte 2: Advanced] [FAPI-1-Advanced] e o [Manual de Segurança de Banco Central do Brasil] ([https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=134).](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=134).) 
 O ICP Brasil emite certificados RSA x509 somente, portanto, para simplificar, a seção remove o suporte para algoritmos EC
 e exige que apenas algoritmos de criptografia recomendados pela IANA sejam usados.
### Considerações sobre assinatura do conteúdo de mensagens (JWS)

1. Para garantir a integridade e o não-repúdio das informações tramitadas em API´s sensíveis e que indicam essa necessidade na sua documentação , deve ser adotado a estrutura no padrão JWS definida na [RFC7515] e que inclui: 
- Cabeçalho ( JSON Object Signing and Encryption – JOSE Header ), onde se define o algoritmo utilizado e inclui informações sobre a chave pública ou certificado que podem ser utilizadas para validar a assinatura;
- Payload ( JWS Payload ): conteúdo propriamente dito e detalhado na especificação da API;
- Assinatura digital ( JWS Signature ): assinatura digital, realizada conforme parâmetros do cabeçalho.
2. Cada elemento acima deve ser codificado utilizando o padrão Base64url RFC4648 e, feito isso, os elementos devem ser concatenados com “.” (método JWS Compact Serialization, conforme definido na [RFC7515]).
3. O payload das mensagens (requisição JWT e resposta JWT ) assinadas devem incluir as seguintes `claims` presentes na [RFC7519] (JWT): 
- aud (na requisição JWT ): o Provedor do Recurso (p. ex. a instituição detentora da conta) deverá validar se o valor do campo aud coincide com o endpoint sendo acionado;
- aud (na resposta JWT ): o cliente da API (p. e. instituição iniciadora) deverá validar se o valor do campo aud coincide com o seu próprio `organisationId` listado no diretório;
- iss (na requisição JWT e na resposta JWT ): o receptor da mensagem deverá validar se o valor do campo iss coincide com o `organisationId` do emissor;
- jti (na requisição JWT e na resposta JWT ): o valor do campo jti deverá ser preenchido com o UUID definido pela instituição de acordo com a [RFC4122] usando o versão 4;
- iat (na requisição JWT e na resposta JWT ): o valor do campo iat deverá ser preenchido com horário da geração da mensagem e de acordo com o padrão estabelecido na RFC7519 para o formato NumericDate .
- cty (na requisição JWT e na resposta JWT ): o valor do campo cty deverá ser preenchido caso as operações de assinatura ou criptografia aninhadas não sejam empregadas, o uso desse parâmetro de cabeçalho não é recomendado. No caso de assinatura aninhada ou criptografia ser empregada, este parâmetro de cabeçalho deve estar presente; neste caso, o valor deve ser "JWT", para indicar que um JWT aninhado é transportado neste JWT. Embora os nomes dos tipos de mídia não diferenciem maiúsculas de minúsculas, é recomendável que "JWT" sempre seja escrito com caracteres maiúsculos para compatibilidade com implementações herdadas.
4. O content-type HTTP das requisições e respostas com mensagens JWS deve ser definido como: "application/jwt".
5. No cabeçalho JOSE deve constar os seguintes atributos: 
- alg - deve ser preenchido com o valor `PS256` ";
- kid - deve ser obrigatoriamente preenchido com o valor do identificador da chave utilizado para a assinatura;
- typ - deve ser preenchido com o valor `JWT` .

- Em caso de erro na validação da assinatura pelo `Provedor do Recurso` a API deve retornar mensagem de erro HTTP com `status code` 400 e a resposta deve incluir na propriedade `code` do objeto de resposta de erro especificado na API ( `ResponseError` ) a indicação da falha com o conteúdo `BAD_SIGNATURE` .
- Erros na validação da mensagem recebida pela aplicação cliente (p. ex. iniciador de pagamento) devem ser registrados e o `Provedor do Recurso` (p. ex. instituição detentora de conta) deve ser notificado.

1. O receptor deve validar a consistência da assinatura digital da mensagem JWS exclusivamente com base nas informações obtidas do diretório , ou seja, com base nas chaves publicadas no JWKS da instituição no diretório.
2. As assinaturas devem ser realizadas com uso do certificado digital de assinatura especificado no Padrão de Certificados Open Finance Brasil ;
3. A claim iat deve ser numérica no formato Unix Time GMT+0 com tolerância de +/- 60 segundos;
4. A claim do jti deve ser única para um clientId dentro de um intervalo de tempo de 86.400 segundos (24h), não podendo ser reutilizada neste período. Em caso de reutilização, deverá ser retornado o código de erro HTTP 403. Demais casos seguir instrução da RFC 6749, item 5.2;

#### Considerações sobre algoritmos de assinatura
Para JWS, clientes e servidores de autorização
1. devem usar o algoritmo PS256;

#### Considerações de algoritmo de criptografia
Para JWE, clientes e servidores de autorização
1. devem usar RSA-OAEP com A256GCM

#### Considerações sobre o uso seguro do Transport Layer Security
Para TLS, endpoints do Servidor de Autenticação e endpoints do Servidor de Recursos usados diretamente pelo cliente:
1. devem suportar `TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`
2. devem suportar `TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384`
3. As funcionalidades "TLS Session Resumption" e "TLS Renegotiation" devem ser desabilitadas

## Considerações sobre compartilhamento de dados

### Mecanismo de Autorização

#### Introdução
Os mecanismos existentes para gerenciar adequadamente o acesso aos recursos definidos em [RFC6749] são insuficientes para atender aos requisitos de um ecossistema de compartilhamento de dados moderno. Aproveitar strings de escopo estático não fornece aos consumidores controle de granularidade suficiente para compartilhar com terceiros. O Open Finance Brasil optou por implementar uma [API de consentimento](https://openbanking-brasil.github.io/areadesenvolvedor/swagger/swagger_consents_apis.yaml) como um recurso protegido OAuth 2.0 que pode ser usado para gerenciar o acesso granular aos recursos. A referência ao recurso de consentimento será transmitida como parte de um escopo de recurso dinâmico OAuth 2.0.
#### Definição de Escopo de Consentimento Dinâmico
Este perfil define o escopo dinâmico do OAuth 2.0 "consentimento" da seguinte maneira:
- string 'consent'; e
- delimitador de dois pontos ":"; e
- Consent API REST Resource Id retornado por uma criação bem-sucedida de Open Finance Consent Resource ;
Adicionalmente:
- Consent Resource Id deve incluir caracteres seguros para url;
- Consent Resource Id deve ser "namespaced";
- Consent Resource Id deve ter propriedades de um `nonce` Nonce ;

#### Exemplo de escopo de consentimento dinâmico
consent:urn:bancoex:C1DD33123
### Ciclo de vida da autorização

#### Introdução
O recurso de consentimento tem um ciclo de vida gerenciado separada e distintamente da estrutura de autorização OAuth 2.0. As transições de estado e comportamentos esperados e condições de erro esperados dos Recursos REST protegidos com este perfil são definidos nas especificações funcionais da API publicadas pelo Open Finance Brasil.
#### Servidor de autorização
Além dos requisitos descritos nas disposições de segurança do Open Finance Brasil, o Servidor de Autorização
1. deve apenas emitir refresh_tokens quando vinculados a um consentimento ativo e válido; Não deve emitir refresh_token quando o consentimento estiver no status “CONSUMED” (para fase 3); Deve emitir um access_token por meio de um grant_type do tipo client credentials no status “CONSUMED” (para fase 3).
2. só deve compartilhar o acesso aos recursos quando apresentado access_token vinculado a um consentimento ativo e com o status "AUTHORIZED". Para tokens gerados com o scope: payments, o status do consentimento não será validado; No cenário de recebimento de token inválido, deve ser retornado status code 401.
3. deve revogar os refresh tokens e, quando aplicável, os access tokens quando o Consentimento (Consent Resource) relacionado for apagado;
4. deve garantir que os access tokens são emitidos com os scopes necessários para permitir acesso aos dados especificados em elemento Permission do Consentimento (Consent Resource Object) relacionado;
5. não deve rejeitar pedido de autorização com scopes além do necessário para permitir acesso a dados definidos em elemento Permission do Consentimento (Consent Resource Object) relacionado;
6. pode reduzir o escopo solicitado para um nível que seja suficiente para permitir o acesso aos dados definidos em elemento Permission do Consentimento (Consent Resource Object) relacionado;
7. deve manter registros sobre o histórico dos consentimento para permitir a adequada formação de trilhas de auditoria em conformidade com a regulação em vigor;
8. deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da [RFC6749]) caso o CPF do usuário autenticado não seja o mesmo indicado no elemento loggedUser do Consentimento (Consent Resource Object);
9. deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da [RFC6749]) caso o elemento businessEntity não tenha sido preenchido no Consentimento (Consent Resource Object) relacionado e o usuário tenha selecionado ou se autenticado por meio de credencial relacionada à conta do tipo Pessoa Jurídica (PJ);
10. deve condicionar a autenticação ou seleção de contas do tipo PJ à consistência entre o CNPJ relacionado à(s) conta(s) e o valor presente no elemento businessEntity do Consentimento (Consent Resource Object). Em caso de divergência deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da [RFC6749]);
11. deve emitir refresh_token com validade não inferior à validade do consentimento ao qual está relacionado, respeitado os demais critérios acima.

#### Cliente confidencial
Além dos requisitos descritos nas disposições de segurança do Open Finance Brasil, o Cliente Confidencial
1. deve, sempre que possível, revogar e cessar o uso de refresh e de access tokens vinculados a um consentimento (Consent Resource Object) que foi excluído;
2. deve excluir consentimentos (Consent Resource Objects) que estão expirados;

## Reconhecimentos
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro e seguro de dados por meio da formação do Grupo de Trabalho FAPI da OpenID Foundation, o GT de Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- Alexandre Siqueira (Mercado Pago)
- Joseph Heenan (Authlete)
- Marcos Rodrigues (Itaú)
- Mário Ginglass (BNDES)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## Avisos
Copyright (c) 2023 Estrutura Inicial do Open Finance BrasilA Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.

---

# Perfil de Segurança do Open Finance Brasil > Histórico de Especificações - FAPI > FAPI-BR v2.0.0 - Open Finance Brasil Financial-grade API Security Profile > Período de Convivência - FAPI-BR 2.0 (FAPI-Único)

---
id: 346652711
title: Período de Convivência - FAPI-BR 2.0 (FAPI-Único)
version: 2
modified: 2024-03-22T19:31:39.363Z
url: /spaces/OF/pages/346652711/Per+odo+de+Conviv+ncia+-+FAPI-BR+2.0+FAPI-+nico
---

13falsenonelistfalse
## 1. Objetivo
Apoiar as instituições participantes do Open Finance com orientações para a implementação do perfil FAPI único de segurança, especialmente no período de convivência entre os perfis antigos e o novo que ocorrerá entre 25/03/2024 e 14/04/2024.
## 2. Contexto
As especificações de segurança do Open Finance são baseadas no FAPI, da OpenID Foundation, e permitiam que as autenticações fossem realizadas através de oito métodos diferentes, com variantes de Private Key e mTLS, com ou sem PAR, com ou sem JARM. A fim de simplificar a comunicação entre as instituições e melhorar a interoperabilidade, a documentação foi atualizada para criação de um perfil FAPI único que deverá ser implementado por todas as instituições do ecossistema.O cronograma de adequação das instituições prevê um período de três semanas de convivência entre os perfis, para que as iniciadoras de pagamento e receptoras de dados façam os devidos DCMs e ajustes bilaterais com as detentoras de conta e transmissoras de dados, antes da descontinuação dos perfis anteriores. A realização dos DCMs a tempo é necessária para a devida implementação das novas APIs de Consentimento e de Pagamentos.**Resumo de compatibilidade a ser garantida no período de convivência**
- Processo DCR/DCM Atualizações nos registros de clients (software statments), independente da finalidade (troca de certificado, aumento de escopo de produtos, rollbacks pós tentativa de migração para o FAPI-Único)
- Processo FAPI Geração de novo access-token, habilitanto a obtenção de novos consentimentos Renovação de um access-token (refresh-token) para o consumo de dados de consentimentos já existentes
 
## 3. Cronograma

| Data | Iniciadora de pagamento e Receptora de dados | Detentora de conta e transmissora de dados |
| --- | --- | --- |
| Até 24/03/2024 | Obter certificação RP da OIDF | Obter certificações OP DCR/DCR e OP FAPI da OIDF |
| Até 24/03/2024 (23:59) | Publicar o link da certificação de segurança do novo perfil | A partir do momento de recebimento da certificação: Atualizar o well-known e suas implementações com o novo perfil de segurança Publicar o link das certificações de segurança do novo perfil |
| Entre 25/03/2024 e 14/04/2024 | Realizar DCR ou DCM com todas as instituições para atualizar para o novo perfil | Atentar-se aos SLAs diferenciados acerca do atendimento de tickets relacionados aos processos de DCR/DCM, conforme IN BCB 443 |
| Após 15/04/2024 | Parar de fazer chamadas, DCR e DCM com os perfis antigos | Remover o suporte aos perfis antigos |
 
## 4. Principais mudanças no perfil FAPI-Único (FAPI-BR 2.0)

1. Adoção do perfil único private_key  + PAR​
2. Criptografar o  id_token  por padrão, sem a necessidade de validação de PII em seu conteúdo​
3. Tornar o  proof key for code exchange  (PKCE) obrigatório​
4. Remover  claims  CPF e CNPJ​
5. Proibir a rotação de  registration_access_token  no processo de DCR/DCM​
6. Restringir os parâmetros do atributo  response_type ​
7. Restringir os parâmetros do atributo  response_mode ​
8. Restringir os parâmetros do atributo  subject_type ​

### 4.1. Métodos de Autenticação
A principal mudança do FAPI-Único é a adoção de um único método de autenticação, o private-key-jwt. Durante o período de convivência é imprescindível que os participantes mantenham disponíveis todos os métodos de autenticação que ofereciam na primeira versão do FAPI-BR.Na primeira versão do FAPI, os servidores de autenticação eram obrigados a oferecer ao menos uma das seguintes opções de métodos de autenticação private-key-jwt ou mtls que poderiam, ainda, ser combinadas com o uso de PAR.
#### well-know
No JSON retornado pela endpoint de well-know dos servidores de autenticação, os métodos de autenticação aceitos são definidos no parâmetro *token_endpoint_auth_methods_supported*, utilizado para comunicar a url do endpoint que o cliente deve utilizar para obter/renovar um *access-token*.
| Método de Autenticação | well-know ( token_endpoint_auth_methods_supported ) | FABI-BR 1.0 | FAPI-Único |
| --- | --- | --- | --- |
| private-key-jwt | private_key_jwt | Suporta | Obrigatório |
| mtls | tls_client_auth | Suporta | Não suporta |
Além do parâmetro *token_endpoint_auth_methods_supported*, alguns participantes declaram os métodos de autenticação aceitos nos parâmetros *revocation_endpoint_auth_methods_supported*e *introspection_endpoint_auth_methods_supported*que comunicam as urls dos endpoints de revogação de um access-token e de introspecção de um token. Caso o faça o participante deve garantir que todos os parâmetros sejam atualizados conforme a política do FAPI-Único.
#### Cenários

##### Cenário 1: A implementação do FAPI 1.0 da instituição suporta apenas um dos métodos de autenticação

##### Cenário 2: A implementação do FAPI 1.0 da instituição suporta ambos os métodos de autenticação

### 4.2. Pushed Authorization Requests (PAR)
Além de estabelecer como único método de autenticação o private-key-jwt, o perfil de segurança FAPI-Único exige a adoção do PAR para que os parâmetros da requisição de autorização sejam enviados diretamente ao servidor de autorização, sem o intermédio do navegador.O uso do PAR altera o fluxo de chamadas realizados durante o processo de autenticação FAPI, sendo necessário garantir que, durante o período de convivência, instituições transmissoras/detentoras que não exigiam a adoção obrigatória do PAR mantenham a compatibilidade aceitando requisições sem o uso de PAR para os *clients*previamente registrados. Após o término do período de convivência o uso do PAR deverá se tornar obrigatória a todos os *clients*.
#### well-know
No JSON retornado pela endpoint de well-know dos servidores de autenticação, existem dois parâmetros relacionados ao uso do PAR, *pushed_authorization_request_endpoint*que indica a url do endpoint para envio dos parâmetros de autenticação e *require_pushed_authorization_requests*indicando se o uso PAR é opcional ou obrigatório. O não envio destes parâmetros significa que a instituição não suporta o uso de PAR.
| Parâmetro | well-know | FABI-BR 1.0 | FAPI-Único |
| --- | --- | --- | --- |
| Endpoint PAR | pushed_authorization_request_endpoint | Opcional | Obrigatório |
| Obrigatoriedade do PAR | require_pushed_authorization_requests | Opcional | Obrigatório com valor true |

#### Cenários

##### Cenário 1: A implementação do FAPI 1.0 da instituição não suportava PAR
Neste cenário, no período de convivência, o transmissor/detentor precisa garantir que clientes existentes, registrados sem o uso do PAR, continuem funcionando da mesma maneira. Posteriormente, ao término deste período, nenhuma autenticação sem o uso de PAR deverá ser aceita.
##### Cenário 2: A implementação do FAPI 1.0 da instituição suportava PAR de maneira opcional
Neste cenário, no período de convivência, o transmissor/detentor precisa garantir que clientes existentes, registrados, continuem funcionando da mesma maneira podendo escolher se utilizam ou não o PAR. Posteriormente, ao término deste período, nenhuma autenticação sem o uso de PAR deverá ser aceita.
##### Cenário 3: A implementação do FAPI 1.0 da instituição exigia o uso do PAR
Neste cenário não existe distinção entre o FAPI-BR 1.0 e FAPI-Único, sendo exigido que todos os clientes sempre façam a autenticação utilizando o PAR.
### 4.3. Proof Key for Code Exchange (PKCE)
PKCE é um método de segurança utilizado para proteger contra ataques de interceptação de código. Ele funciona gerando uma chave dinâmica que é utilizada para verificar a identidade do aplicativo cliente durante o processo de autorização. Essa chave é temporária e é usada para criar um código de autorização único, o qual é trocado por um token de acesso. O PKCE é utilizado para prevenir ataques de interceptação de código em aplicativos de autenticação que utilizam o fluxo de autorização baseado em código, garantindo uma camada adicional de segurança ao processo de autenticação. No novo perfil FAPI-Único o uso de PKCE se torna obrigatório, dado que no FAPI, quando se utiliza PAR, o uso de PKCE se torna obrigatório.
#### Cenários
**Cenário 1: A implementação do FAPI 1.0 da instituição não suportava PAR ou em que o uso do PAR não era obrigatório**Neste cenário, durante o período de convivência, o servidor de autenticação deve garantir que clientes registrados, sem a obrigatoriedade do uso de PAR, possam continuar realizando o fluxo FAPI sem o uso de PKCE. Já clientes que foram registrados com uso de PAR obrigatório devem ser cobrados do uso do PKCE.**Cenário 2: A implementação do FAPI 1.0 da instituição que obrigava o uso PAR (consequentemente de PKCE)**Neste cenário, todos os clientes previamente registrados exigem o uso do PAR e consequentemente todos já são obrigados a utilizar o PKCE, não havendo impacto durante o processo de migração do FABI-BR 1.0 para o FAPI-Único.
### 4.4. Criptografia do idToken
No contexto do FAPI (Financial-grade API), a encriptação do ID Token é uma prática importante para proteger informações sensíveis transmitidas durante o processo de autenticação e autorização. O ID Token é um token de autenticação que contém informações sobre o usuário autenticado, como seu identificador, tipo de autenticação e outros atributos de perfil. Ao encriptar o ID Token, as informações contidas nele são tornadas ilegíveis para qualquer parte que não possua a chave de desencriptação adequada.No FAPI-BR 1.0 a encriptação do ID Token só era exigida caso informações PII, como CPF e CNPJ, estivessem presentes, sendo opcionais nos demais casos. Já no FAPI-Único a encriptação do ID Token sempre dever ser realizada.Durante o processo de registro do *client,*o servidor de autenticação informa o cliente os algoritmos e tipos de criptografia que poderão ser aplicados e caso não realizasse a encriptação, a informação não era fornecida. Desta forma, os transmissores/detentores devem adotar uma política de convivência para este aspecto.
#### well-know
No JSON retornado pela endpoint de well-know dos servidores de autenticação, existem dois parâmetros relacionados a criptografia do ID Token, *id_token_encryption_alg_values_supported*que lista os algorítimos válidos para a criptografia e id_token_encryption_enc_values_supported que lista os métodos de criptografia suportados.Como no FAPI 1.0 os authorizations servers já deveriam suportar a criptografia para alguns cenários, não deveria haver impactos para a URL de well-know, devendo ambos os atributos estar presentes. Entretanto, existe uma quebra de comportamento, e os clients devem se preparar para sempre receberem os dados criptografados.
### 4.5. Claims CPF e CNPJ
No FAPI-BR 1.0 era obrigatório que os servidores de autorização suportassem as claims CPF e CNPJ durante o pedido de autenticação. No FAPI-Único esta exigência deixa de existir, e de forma contrária, eles devem ignorar o pedido destas claims.
#### well-know
No JSON retornado pela endpoint de well-know dos servidores de autenticação, o parâmetro *claims_supported*indica quais claims podem ser solicitadas durante o processo de autenticação FAPI. Este parametro traz uma lista de todas as claims suportadas para diferentes propósitos.
### 4.6. Rotação de  registration_access_token  no processo de DCR/DCM​
No novo perfil FAPI-Único foi proibida a rotação do registration_access_token o processo de DCR/DCM. Esta mudança não gera problemas de convivência.
### 4.7. Atributo  response_type
O response type no FAPI refere-se aos tipos de resposta permitidos durante o processo de autorização de um software cliente para acessar recursos protegidos por um servidor de autorização. Na especificação FAPI-BR 1.0, os tipos de resposta aceitos eram "code id_token" ou "code" em conjunto com o response_mode jwt (JARM). O primeiro combina o fluxo de autorização com a obtenção de um token de identificação (ID token), fornecendo informações sobre a identidade do usuário autenticado. O segundo envolve a obtenção dos tokens de acesso em uma resposta encapsulada em um JWT assinado. No FAPI-Único, apenas o tipo "code id_token" é permitido. Isso significa que o fluxo de autorização deve obrigatoriamente fornecer tanto um código de autorização quanto um token de identificação.A mudança nas opções de response type impacta os softwares clientes ao exigir ajustes nos fluxos de autorização e possíveis reavaliações nas estratégias de autenticação e segurança, garantindo a conformidade com as novas especificações e uma interação segura e eficaz com os servidores de autorização em transações financeiras. É importante destacar que essa mudança pode exigir a realização de um DCM.
#### well-know
**Cenário 1: A implementação do FAPI 1.0 da instituição suportava os response types “code idtoken” e “code”**Neste cenário, durante o período de convivência, o servidor de autorização deve garantir a compatibilidade mantendo os dois formatos de *response_type*disponíveis. AO término deste período apenas o *response_type*“code id_token” deve ser mantido. **Cenário 2: A implementação do FAPI 1.0 da instituição suportava apenas o response type “code id_token”**Neste cenário, não existe problema de compatibilidade e o servidor de autorização pode manter o suporte apenas do response_type “code id_token” durante o período de convivência.
### 4.8. Atributo  response_mode
O atributo "response_mode" é um parâmetro em solicitações de autorização OAuth 2.0 que especifica o formato e o método de entrega da resposta de autorização do servidor de autorização ao cliente após o consentimento do usuário. Os valores possíveis incluem "query" para retornar a resposta como parâmetros de consulta na URL de redirecionamento, "fragment" para retorná-la como um fragmento na URL e "form_post" para enviá-la em um corpo de mensagem HTML POST, sendo escolhido de acordo com as necessidades de segurança e o contexto de uso do cliente.O uso do "response_mode" jwt em conjunto com o "response_type" "code" permite que a resposta de autorização seja encapsulada em um token JWT (JSON Web Token), fornecendo segurança adicional para as transações OAuth 2.0. Esse método é especialmente útil quando combinado com a técnica JARM (JSON-based Algorithm for Resilient Metrics), onde as características da resposta TLS são utilizadas para calcular uma impressão digital única, fornecendo uma camada adicional de segurança contra ataques como falsificação de resposta de autorização (authorization response spoofing) e manipulação dos parâmetros de resposta.​No FAPI-BR 1.0 era permitido o uso de qualquer um dos response_mode definidos na RFC, ou exigido o uso do response_mode jwt quando se utilizando o response_type code. No perfil FAPI-Único apenas o response_mode fragment é aceito, gerando a necessidade de alterações no processo de autenticação por parte dos softwares clientes. Esta mudança pode exigir a realização do DCM.
#### well-know
**Cenário 1: A implementação do FAPI 1.0 da instituição suportava apenas o response type “code” e consequentemente apenas o response mode “jwt”**Neste cenário, é necessário que durante o período de convivência, o servidor de autorização mantenha a compatibilidade com o modo jwt para caso algum cliente ainda utilize o response type code e adicione suporte ao modo fragment para os softwares clientes que migrarem para o uso do response type “code id_token”.**Cenário 2: A implementação do FAPI 1.0 da instituição não definia os responses modes no well-know**Neste cenário, a omissão no well-know do atributo “response_modes_supported” indica que o servidor de autorização aceita os modos “query” e “fragment”. Desta forma, é necessário que seja garantida a compatibilidade durante o período de convivência.**Cenário 3: A implementação do FAPI 1.0 da instituição suportava múltiplos response modes**Neste cenário, é necessário que durante o período de convivência, o servidor de autorização mantenha a compatibilidade com todos os modos previamente suportados, além de incluir caso ainda não o suportasse, o modo fragment.
### 4.9. Atributo  subject_type ​
No contexto do FAPI (Financial-grade API), os "subject types" "public" e "pairwise" são utilizados para identificar o usuário sobre o qual uma ação está sendo realizada durante o processo de autorização. No FAPI, apenas esses dois tipos de "subject" são aceitos, com o objetivo de garantir um nível adequado de segurança e privacidade nas transações financeiras.O "subject type" "public" permite que o "subject" seja um identificador público e único, como um nome de usuário ou endereço de e-mail, sendo mais simples e direto. Já o "pairwise" cria identificadores únicos para cada cliente, garantindo que o mesmo usuário receba um identificador diferente para cada cliente, protegendo sua privacidade. Essa restrição aos "subject types" "public" e "pairwise" no FAPI visa garantir uma abordagem consistente e segura para a identificação de usuários em transações financeiras, atendendo aos rigorosos requisitos de segurança e privacidade nesse contexto.No FAPI-BR 1.0, ambos os tipos de "subject" eram suportados, porém, no FAPI-Único, apenas o tipo "public" é aceito. Essa diferença pode potencialmente causar problemas de compatibilidade entre as versões, o que deve ser cuidadosamente considerado durante o período de convivência entre elas. Essa mudança requer a execução de um DCM. Além disso, os receptores de dados devem se atentar que o subject utilizado previamente para identificar o usuário pode ser alterado.
#### well-know
Durante o período de convivência é necessário que o servidor de autorização garanta o funcionamento de ambos os modelos.
## 5. FAQ

1. Durante o período de convivência devo aceitar requisições de registro (DCR) para novos clientes que forem solicitadas utilizando FAPI-BR 1.0, por exemplo , utilizando o método de autenticação mtls ou sem o uso de PAR?
Sim. Para garantir o funcionamento durante o período de convivência, todos os transmissores/detentores deverão continuar suportando a realização de novos registros (DCR) utilizando o FABI-BR 1.0. Após o período de convivência apenas requisições que utilizem os padrões do FAPI-Único deverão ser aceitas. 
1. Durante o período de convivência devo aceitar requisições de modificações de clientes existentes (DCM) que forem solicitadas utilizando FAPI-BR 1.0, por exemplo, utilizando o método de autenticação mtls ou sem o uso de PAR?
Sim, manter a compatibilidade com solicitações que utilizam o FAPI-BR 1.0 é importante para garantir a manutenção de clientes existentes e para possibilitar o processo de rollback de uma migração para o FAPI-Único mal sucedida.
1. Após o período de convivência, é obrigatório a remoção do suporte ao método de autenticação mtls?
Sim, após o período de convivência o Open Finance Brasil não suportará nenhum outro método de autenticação além do private-key-jwt, devendo ser recusada a criação de novos clientes ou alteração de clientes existentes utilizando parâmetros incompatíveis com o definido no FAPI-Único.
1. Sou obrigado a declarar os parâmetros revocation_endpoint_auth_methods_supported e introspection_endpoint_auth_methods_supported no JSON retornado no meu endpoint de well-know?
Não. A escolha de determinar um método de autenticação para estes endpoints não é definida no FAPI-Único, ficando a cargo do transmissor/detentor escolher utilizar os valores padrões (quando os parâmetros não são comunicados) ou adotar o formato private-key-jwt definido no FAPI-Único.Entretanto, independentemente da escolha do transmissor/dententor, deve-se garantir que no período de convivência o formato previamente utilizado na sua implementação do FAPI-BR 1.0 seja suportado.

---

# Perfil de Segurança do Open Finance Brasil > Histórico de Especificações - FAPI > FAPI-BR v2.0.0 - Open Finance Brasil Financial-grade API Security Profile > [EN] Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3

---
id: 245760001
title: [EN] Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3
version: 8
modified: 2024-04-05T12:58:58.342Z
url: /spaces/OF/pages/245760001/EN+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3
---

## Foreword
Este documento também está disponível em [Português](file:///C:/wiki/spaces/DraftOF/pages/76251182) The Open Finance Brasil Initial Structure is responsible for creating standards and specifications necessary to meet the requirements and obligations of the Brasil Open Finance Legislation as originally outlined by the [Brasil Central Bank](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). There is a possibility that some of the elements of this document may be the subject to patent rights. OFBIS shall not be held responsible for identifying any or all such patent rights.Open Finance Brasil Financial-grade API Security Profile 1.0 consists of the following parts:
- Open Finance Brasil Financial-grade API Security Profile 1.0
- Open Banking Brasil Dynamic Client Registration Profile 1.0
These parts are intended to be used with [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) and [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introduction
The Open Finance Brasil Financial-grade API is a highly secured OAuth profile that aims to provide specific implementation guidelines for security and interoperability which can be applied to APIs in the Brasil Open Finance area that require a higher level of privacy than provided by standard [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html). Among other enhancements, this specification addresses privacy considerations identified in [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) that are relevent in the Open Finance Brasil specifications but have not, so far, been required by other jurisdictions.Although it is possible to code an OpenID Provider and Relying Party from first principles using this specification, the main audience for this specification is parties who already have a certified implementation of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and want to achieve certification for the Brasil Open Finance programme.
## Notational Conventions
The key words "shall", "shall not", "should", "should not", "may", and "can" in this document are to be interpreted as described in [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml).These key words are not to be used as lexicon terms such that any occurrence of them shall be interpreted as key words and are not to be interpreted with their natural language meanings.
## 1. Scope
This document specifies the method of
- applications to obtain the OAuth tokens in an appropriately secure manner for higher risk access to data in a manner that meets the requirements of Open Finance Brasil ;
- applications to use OpenID Connect to identify the customer; and
- applications to use OpenID Connect to assert identity of the customer;
This document is applicable to all participants engaging in Open Finance in Brasil.
## 2. Normative references
The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applied. For undated references, the latest edition of the referenced document (including any amendments) applies.[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md) - Financial-grade API Security Profile 2.0 - Part 1: Baseline[FAPI-2-Advanced](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Advanced_Profile.md) - Financial-grade API Security Profile 2.0 - Part 2: Advanced[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[OFB-FAPI-DCR](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3.html) - Open Banking Brasil Financial-grade API Dynamic Client Registration Profile 1.0[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings
## 3. Terms and definitions
For the purpose of this document, the terms defined in [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) and ISO29100 apply.
## 4. Symbols and Abbreviated terms

- API - Application Programming Interface
- CSRF - Cross Site Request Forgery
- DCR - Dynamic Client Registration
- FAPI - Financial-grade API
- HTTP - Hyper Text Transfer Protocol
- MFA - Multi-Factor Autentication
- OFBIS - Open Finance Brasil Initial Structure
- OIDF - OpenID Foundation
- REST - Representational State Transfer
- TLS - Transport Layer Security

## 5. Brasil Open Finance Security Profile

### 5.1. Introduction
The Brasil Open Finance Security profile specifies additional security and identity requirements for high risk API resources protected by the OAuth 2.0 Authorization Framework that consists of [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html), [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and other specifications.This profile describes security and features provisions for a server and client that are necessary for the Brasil Open Finance Programme by defining the measures to mitigate or address:
- attacks that address privacy considerations identified in clause 9.1 of [FAPI1 Advanced]
- the requirement to support fine-grained access to resources for data minimisation purposes
- the requirement to convey the Authentication Context Request that was performed by an OpenID Provider to a Client to enable a appropriate client management of customer conduct risk.

### 5.2. Open Finance Brasil security provisions

#### 5.2.1. Introduction
Open Finance Brasil has a requirement to address privacy considerations that were identified but not addressed in the [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) final specification without imposing additional requirements on Authorisation Servers being proposed in [FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md).This profile outlines the client management requirements needed to support the broader Open Finance Brasil ecosystem.As a profile of the OAuth 2.0 Authorization Framework, this document mandates the following for the Brasil Open Finance Security profile.
#### 5.2.2. Authorization server
The Authorization Server shall support the provisions specified in clause 5.2.2 of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)In addition, the Authorization Server
1. shall perform client authentication using private_key_jwt;
2. shall require requests of the type "pushed authorization requests" PAR;
3. shall distribute discovery metadata (such as the authorization endpoint) via the metadata document as specified in OIDD and [RFC8414] (".well-known");
4. shall support the claims parameter as defined in clause 5.5 OpenID Connect Core ;
5. shall support the acr "urn:brasil:openbanking:loa2" as defined in section 5.2.2.3;
6. should support the acr "urn:brasil:openbanking:loa3" as defined in section 5.2.2.3;
7. shall implement the userinfo endpoint as defined in clause 5.3 OpenID Connect Core ;
8. shall support parameterized OAuth 2.0 resource scope consent as defined in clause 6.3.1 OIDF FAPI WG Lodging Intent Pattern ;
9. may support Financial-grade API: Client Initiated Backchannel Authentication Profile ;
10. (withdrawn temporarily);
11. shall support refresh tokens;
12. shall issue access tokens with an expiry no greater than 900 seconds and no less than 300 seconds;
13. shall always include an acr claim in the id_token;
14. shall support the response_type value code id_token;
15. shall not allow refresh token rotation;
16. shall ensure that, in case of sharing the Authorization Server for other services, in addition to Open Finance, it does not disclose and/or allow the use of non-certified methods in the Open Finance environment;
17. shall ensure that the settings disclosed to other participants through OpenID Discovery (indicated by the Well-Known file registered in the Directory) are restricted to the operating modes to which the institution has certified; shall keep in your settings the methods for which there are still active clients; shall update the records that use non-certified methods, through bilateral treatment between the institutions involved;
18. shall refuse requests, for the Open Finance environment, that are outside the modes of operation to which the institution has certified its Authorization Server;
19. the minimum expiration time of request_uri must be 60 seconds;
20. shall deny all requests without header x-fapi-interaction-id on protected resources endpoints;
21. must require the use of Proof Key for Code Exchange (PKCE);
22. must require the use of subject_type “ public ”;
23. must require the use of response_mode “fragment”;
24. shall issue refresh_tokens (JWT or opaque) without an expiration period in scenarios where it is necessary.

##### 5.2.2.1. ID Token as detached signature
The Authorization Server shall support the provisions specified in clause 5.2.2.1 of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
1. Shall encrypt the id_token in callback and token endpoint;
2. For the encryption of the id_token, a key available in the JWKS informed in the jwks_uri parameter, with the attribute “use”:”enc”, during the client registration must be used, indicated through the kid header of the JWT document;
3. The use of other headers to indicate the key used, such as x5u, x5c, jku or jkw is prohibited as defined in clause 2 OIDC .

##### 5.2.2.2. "sub" Claim clarifications
This profile uses the official definition found at: [Analise requisitos de criptografia ID_TOKEN](https://openfinancebrasil.atlassian.net/wiki/spaces/DraftOF/pages/76251250/Analise+requisitos+de+criptografia+ID+TOKEN). This means that the sub is an identifier that is never transferred or changed to the end user within the Account Servicing Payment Service Provider (ASPSP).
##### 5.2.2.3. Requesting the "urn:brasil:openbanking:loa2" or "urn:brasil:openbanking:loa3" Authentication Context Request
This profile defines "urn:brasil:openbanking:loa2" and "urn:brasil:openbanking:loa3" as new Authentication Context Request (ACR) classes.
- LoA2: Authentication performed using single factor;
- LoA3: Authentication performed using multi factor (MFA)
The following rules are applicable to the authentication mechanism of Open Finance Brazil API's:
- In accordance to Art. 17 of Joint Resolution nº 01 - Open Banking Brasil , institutions must adopt procedures and controls for client authentication compatible with those applicable in their electronic service channels.
- In accordance with the regulation, it is suggested that: For Read-Only APIs (Phase 2): the Authorization Servers should adopt, at least, an authentication method compatible with LoA2; and For Read-Write API's (subsequent phases): the Authorization Servers should adopt an authentication method compatible with LoA3 or higher.
In all cases, the adoption of a more rigorous authentication mechanism (LoA3 or higher) is at the discretion of the Bank (ASPSP), according to its risk assessment and in a manner compatible with the mechanisms usually employed.Authentication factors clarificationThe authentication methods are:
- Something you know, such as password or phrase
- Something you have, such as token, smartcard or device
- Something you are, meaning an authentication that makes use of physical characteristics, such as biometric validation.
To performe a MFA authentication is necessary that the end user presents at least two different methods as listed above. A unique method used more than once - ie. presenting passwords - is not accepted as MFA.**5.2.2.4 Mandatory scopes on the well-known endpoint**The authorization server must declare the scopes below in its well-known endpoint, regardless of whether the institution provides the products related to the scopes listed below:
- invoice-financings
- financings
- loans
- unarranged-accounts-overdraft
- bank-fixed-incomes
- credit-fixed-incomes
- variable-incomes
- treasure-titles
- funds
- exchanges
The scopes not listed above must be declared if the institution provides products related to them
 (i.e.: accounts, payments)
#### 5.2.3. Confidential client
A confidential client shall support the provisions specified in clause 5.2.3 of [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html),In addition, the confidential client
1. shall support Pushed Authorisation Requests PAR ;
2. shall support parameterized OAuth 2.0 resource scope consent as defined in clause 6.3.1 OIDF FAPI WG Lodging Intent Pattern ;
3. shall support refresh tokens;
4. shall not populate the acr claim with required values;
5. shall require the acr claim as an essential claim;
6. shall not allow refresh tokens rotation feature;
7. shall send header x-fapi-interaction-id on FAPI endpoints;

## 6. Security considerations
Participants shall support all security considerations specified in clause 8 [Financial-grade API Security Profile 1.0 - Part 1: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) and the [Brazilian Central Bank Open Banking Security Manual](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=134). The Brazilian ICP issues RSA x509 certificates only therefor section removes for simplicity support for EC algorithms and requires that only IANA recommended encryption algorithms be used.
### 6.1. Message Content Signing Considerations (JWS)
JWS standad defined in [RFC7515](https://tools.ietf.org/html/rfc7515) shall be adopted to ensure integrity and non-repudiation of information processed in sensitive API's (message sign requirement is indicated at API's documentation/swagger), which includes:
- Header (JSON Object Signing and Encryption - JOSE Header), which defines the algorithm used and includes information about the public key or certificate that can be used to validate the signature;
- Payload (JWS Payload): content itself as detailed in the API specification;
- Digital signature (JWS Signature): digital signature, performed according to header parameters.

1. Each of elements above must be encoded using the Base64url pattern RFC4648 and the elements must be concatenated with "." (JWS Compact Serialization method as defined in RFC7515 ).
2. The payload of signed messages (request JWT and response JWT) shall include the following claims as defined at RFC7519 :

- aud (in the JWT request): the Resource Provider (eg the institution holding the account) must validate if the value of the aud field matches the endpoint being triggered;
- aud (in JWT response): the API client (eg initiating institution) shall validate if the value of the aud field matches its own organisationId listed in the directory;
- iss (in the JWT request and in the JWT response): the receiver of the message shall validate if the value of the iss field matches the organisationId of the sender;
- jti (in the JWT request and in the JWT response): the value of the jti field shall be filled with the UUID defined by the institution according to [RFC4122] version 4;
- iat (in the JWT request and in the JWT response): the iat field shall be filled with the message generation time and according to the standard established in RFC7519 to the NumericDate format.
- cty (in the JWT request and in the JWT response): the cty field shall be filled in the normal case in which nested signing or encryption operations are not employed, the use of this Header Parameter is not recommended. In the case that nested signing or encryption is employed, this Header Parameter must be present; in this case, the value must be "JWT", to indicate that a Nested JWT is carried in this JWT. While media type names are not case sensitive, it is recommended that "JWT" always be spelled using uppercase characters for compatibility with legacy implementations.

1. The HTTP content-type of requests and responses with JWS messages shall be defined as: "application/jwt".
2. The JOSE header must contain the following attributes:

- alg - shall be filled with the value PS256";
- kid - shall be filled with the key identifier value used for the signature;
- In case of error in signature validation by Resource Provider the API provider shall return HTTP error message with status code 400 and the ResponseError content shall include, in the code property, the content BAD_SIGNATURE.
- Errors in validating the signed messages received by the client application (eg payment initiator) must be logged and the Resource Provider (eg account holding institution) must be notified.

1. The receiver shall validate the consistency of the JWS message's digital signature exclusively based on the information obtained from the directory, that is, based on the keys published in the institution's JWKS in the directory.
2. Signatures must be performed using the digital signature certificate specified in the Open Finance Brazil Certificates Standard ;
3. the iat claim must be numeric in Unix Time format GMT+0 with a tolerance of +/- 60 seconds;
4. the jti claim must be unique for a clientId within a time frame of 86,400 seconds (24h), and cannot be reused within this period. In case of reuse, the HTTP error code 403 shall be return. Any other case must follow RFC 6749 instructions in item 5.2.

### 6.1.1. Signing algorithm considerations
For JWS, both clients and Authorization Serversshall use PS256 algorithm;
#### 6.1.2. Encryption algorithm considerations
For JWE, both clients and Authorization Serversshall use RSA-OAEP with A256GCM
#### 6.1.3. Secure Use of Transport Layer Security considerations
For TLS, Authorization Server endpoints and Resource Server endpoints used directly by the Client
1. shall support TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
2. shall support TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
3. The "TLS Session Resumption" e "TLS Renegotiation" features shall be disabled

## 7. Data Sharing Considerations

### 7.1. Authorisation Mechanism

#### 7.1.1. Introduction
Existing mechanisms for appropriately managing access to resources defined in [RFC6749](https://tools.ietf.org/html/rfc6749) are insufficient to meet the requirements for a modern data sharing ecosystem. Leveraging static scope strings does not provide consumers control of sufficient granularity to share with third parties. Open Finance Brasil have elected to implement a [Consent API](https://openbanking-brasil.github.io/areadesenvolvedor/swagger/swagger_consents_apis.yaml) as a OAuth 2.0 protected resource that can be used to manage fine grain access to resources. The reference to the Consent Resource will be conveyed as part of an OAuth 2.0 dynamic resource scope.
#### 7.1.2. Dynamic Consent Scope Definition
This profile defines OAuth 2.0 dynamic scope "consent" as follows:
- string 'consent' or ‘recurring-consent’ and
- delimiter of a colon ":"; and
- Consent API REST Resource Id as returned by a successful creation of Open Finance Consent Resource ;
In addition:
- the Consent Resource Id must include url safe characters only;
- the Consent Resource Id must be namespaced;
- the Consent Resource Id must have the properties of a nonce Nonce ;

#### 7.1.3. Dynamic Consent Scope Example
consent:urn:bancoex:C1DD33123
### 7.2. Authorisation Life Cycle

#### 7.2.1. Introduction
The Consent Resource has a life cycle that is managed seperately and distinctly from the OAuth 2.0 Authorisation Framework. The state transitions and expected behaviours and error conditions expected of REST Resources protected with this profile are defined in the functional API specifications published by Open Finance Brasil.
#### 7.2.2. Authorization server
In addition to the requirements outlined in Open Finance Brasil security provisions the Authorization Server
1. shall only issue refresh_tokens when linked to an active and valid consent; Must not issue refresh_token when consent status is "CONSUMED" (for phase 3); Must issue an access_token through the grant_type client credentials when consent status is "CONSUMED"(for phase 3).
2. shall only share access to resources when presented access_token linked to an active consent and with the status "AUTHORISED“. For tokens generated with the scope: payments or recurring-payments, the status of the consent will not be validated. In the scenario of receiving an invalid token, status code 401 should be returned.
3. shall revoke refresh tokens and, access tokens where aplicable, when the linked Consent Resource is deleted;
4. shall ensure access tokens are issued with sufficient scope necessary for access to data specified in the Permission element of a linked Consent Resource object;
5. shall not reject an authorisation request requesting scopes broader than those necessary to access data specified in the Permissions element of a linked Consent Resource object;
6. may reduce requested scope to a level sufficient to enable access to data resources specified in the Permissions element of a linked Consent Resource object;
7. shall retain a complete audit history of the consent resource in accordance with current Central Bank brazilian regulation;
8. shall return authentication failure and return code _accessdenied in the error parameter (as specified in section 4.1.2.1 of RFC6749 ) if the CPF of the authenticated user is not the same as indicated in the loggedUser element of the Consent Resource Object;
9. shall return authentication failure and return code _accessdenied in the error parameter (as specified in section 4.1.2.1 of RFC6749 ) if the businessEntity element has not been populated in the related Consent Resource Object and the user has selected or authenticated by using a credential related to a business account;
10. an autenticated or selected business account's CNPJ must match the value present in the businessEntity element of the Consent Resource Object. In case of divergence authorization server shall return authentication failure and return code access_denied in the error parameter (as specified in section 4.1.2.1 of RFC6749 );
11. shall ensure refresh_token expiration time is at least equal to the linked consent resource expiration time.

#### Confidential Client
In addition to the requirements outlined in Open Finance Brasil security provisions the Confidential Client
1. shall revoke where possible and cease usage of refresh and access tokens that are bound to a Consent Resource that has been deleted;
2. shall delete Consent Resource that are expired;

## 8. Acknowledgements
With thanks to all who have set the foundations for secure and safe data sharing through the formation of the OpenID Foundation FAPI Working Group, the Open Finance Brasil GT Security and to the pioneers who will stand on their shoulders.The following people contributed to this document:
- Alexandre Siqueira (Mercado Pago)
- Joseph Heenan (Authlete)
- Marcos Rodrigues (Itaú)
- Mário Ginglass (BNDES)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## Appendix A. Notices
Copyright (c) 2023 Open Finance Brasil Initial Structure.The Open Finance Brasil Initial Structure (OFBIS) grants to any Contributor, developer, implementer, or other interested party a non-exclusive, royalty-free, worldwide copyright license to reproduce, prepare derivative works from, distribute, perform and display, this Implementers Draft or Final Specification solely for the purposes of (i) developing specifications, and (ii) implementing Implementers Drafts and Final Specifications based on such documents, provided that attribution be made to the OFBIS as the source of the material, but that such attribution does not indicate an endorsement by the OFBIS.The technology described in this specification was made available from contributions from various sources, including members of the OpenID Foundation, the Open Finance Brasil GT Security Working Group and others. Although the Open Finance Brasil Initial Structure has taken steps to help ensure that the technology is available for distribution, it takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this specification or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any independent effort to identify any such rights. The Open Finance Brasil Initial Structure and the contributors to this specification make no (and hereby expressly disclaim any) warranties (express, implied, or otherwise), including implied warranties of merchantability, non-infringement, fitness for a particular purpose, or title, related to this specification, and the entire risk as to implementing this specification is assumed by the implementer. The Open Finance Brasil Intellectual Property Rights policy requires contributors to offer a patent promise not to assert certain patent claims against other contributors and against implementers. The Open Finance Brasil Initial Structure invites any interested party to bring to its attention any copyrights, patents, patent applications, or other proprietary rights that may cover technology that may be required to practice this specification.
## Author's Address
OFBIS GT SecurityOpen Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Perfil de Segurança do Open Finance Brasil > Histórico de Especificações - FAPI > FAPI-BR v2.0.0 - Open Finance Brasil Financial-grade API Security Profile > [PT] Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3

---
id: 245694465
title: [PT] Open Finance Brasil Financial-grade API Security Profile 1.0 Implementers Draft 3
version: 8
modified: 2024-11-05T13:43:13.362Z
url: /spaces/OF/pages/245694465/PT+Open+Finance+Brasil+Financial-grade+API+Security+Profile+1.0+Implementers+Draft+3
---

## Prefácio
The normative version in [English](file:///C:/wiki/spaces/DraftOF/pages/76283925)A Estrutura Inicial do Open Finance Brasil (EIOFB) é responsável por criar padrões e especificações necessárias para atender aos requisitos e obrigações da Legislação do Open Finance do Brasil, conforme originalmente delineado pelo [Banco Central do Brasil](https://www.bcb.gov.br/content/config/Documents/BCB_Open_Banking_Communique-April-2019.pdf). É possível que alguns dos elementos deste documento estejam sujeitos a direitos autorais ou patenteados. O EIOFB não se responsabiliza pela identificação de qualquer ou todos esses direitos.O Financial-grade API 1.0 do Open Finance Brasil consiste nas seguintes partes:
- Open Finance Brasil Financial-grade API Security Profile 1.0 ¶
- Open Finance Brasil Dynamic Client Registration Profile 1.0
Estas partes são destinados a serem usados com [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OIDC](https://openid.net/specs/openid-connect-core-1_0.html), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) e [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
## Introdução
A Financial-grade API do Open Finance Brasil é um perfil OAuth altamente seguro que visa fornecer diretrizes de implementação específicas para segurança e interoperabilidade que podem ser aplicadas a APIs na área de Open Finance do Brasil que requerem um nível de privacidade superior ao fornecido pelo padrão [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html). Entre outras melhorias, esta especificação aborda considerações de privacidade identificadas em [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) que são relevantes nas especificações do Open Finance Brasil, mas não foram, até agora, exigidas por outras jurisdições.Embora seja possível codificar um provedor de OpenID e parte de confiança a partir dos primeiros princípios usando esta especificação, o público principal para esta especificação são as partes que já possuem uma implementação certificada do [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e deseja obter a certificação para o programa Brasil Open Finance.
## Convenções Notacionais
As palavras-chave "deve" (shall), "não deve" (shall not), "deveria" (should), "não deveria" (should not) e "pode" (may) presentes nesse documento devem ser interpretadas conforme as diretrizes descritas em [ISO Directive Part 2](https://www.iso.org/sites/directives/current/part2/index.xhtml) observando seguinte equivalência:
- "deve" => equivalente ao termo "shall" e expressa um requerimento definido no documento (nas traduções é similar ao termo "must", que pode denotar um requerimento externo ao documento);
- "não deve" => equivalente ao termo "shall not" e também expressa um requerimento definido no documento;
- "deveria" e "não deveria"=> equivalente ao termo "should" e "should not" e expressa uma recomendação
- "pode" => equivalente ao termo "may" indica uma permissão
Estas palavras-chave não são usadas como termos de dicionário, de modo que qualquer ocorrência deles deve ser interpretada como palavras-chave e não devem ser interpretados com seus significados de linguagem natural.
## 1. Escopo
Este documento especifica o método para os aplicativos
- obterem de maneira segura os tokens OAuth necessários para acesso a dados críticos de acordo com os requisitos do Open Finance Brasil ;
- utilizarem o OpenID Connect para identificação do usuário do Open Finance; e
- utilizarem o OpenID Connect para afirmar a identidade do cliente.
Este documento é aplicável a todos os participantes do Open Finance no Brasil.
## 2. Referências normativas
Os seguintes documentos referenciados são indispensáveis para a adoção das especificações deste documento. Para referências datadas, apenas a edição citada se aplica. Para referências não datadas, deve-se aplicar a última edição do documento referenciado (incluindo quaisquer emendas).[ISODIR2](https://www.iso.org/sites/directives/current/part2/index.xhtml) - ISO/IEC Directives Part 2[RFC6749](https://tools.ietf.org/html/rfc6749) - The OAuth 2.0 Authorization Framework[RFC6750](https://tools.ietf.org/html/rfc6750) - The OAuth 2.0 Authorization Framework: Bearer Token Usage[RFC7636](https://tools.ietf.org/html/rfc7636) - Proof Key for Code Exchange by OAuth Public Clients[RFC6819](https://tools.ietf.org/html/rfc6819) - OAuth 2.0 Threat Model and Security Considerations[RFC7515](https://tools.ietf.org/html/rfc7515) - JSON Web Signature (JWS)[RFC7519](https://tools.ietf.org/html/rfc7519) - JSON Web Token (JWT)[RFC7591](https://tools.ietf.org/html/rfc7591) - OAuth 2.0 Dynamic Client Registration Protocol[RFC7592](https://tools.ietf.org/html/rfc7592) - OAuth 2.0 Dynamic Client Registration Management Protocol[BCP195](https://tools.ietf.org/html/bcp195) - Recommendations for Secure Use of Transport Layer Security (TLS) and Datagram Transport Layer Security (DTLS)[OIDC](https://openid.net/specs/openid-connect-core-1_0.html) - OpenID Connect Core 1.0 incorporating errata set 1[FAPI-CIBA](https://bitbucket.org/openid/fapi/src/master/Financial_API_WD_CIBA.md) - Financial-grade API: Client Initiated Backchannel Authentication Profile[OIDD](https://openid.net/specs/openid-connect-discovery-1_0.html) - OpenID Connect Discovery 1.0 incorporating errata set 1[OIDR](https://openid.net/specs/openid-connect-registration-1_0.html) - OpenID Connect Registration 1.0 incorporating errata set 1[RFC8705](https://tools.ietf.org/html/rfc8705) - OAuth 2.0 Mutual TLS Client Authentication and Certificate Bound Access Tokens[JARM](https://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) - Financial-grade API: JWT Secured Authorization Response Mode for OAuth 2.0 (JARM)[PAR](https://tools.ietf.org/html/draft-ietf-oauth-par) - OAuth 2.0 Pushed Authorization Requests[JAR](https://tools.ietf.org/html/draft-ietf-oauth-jwsreq) - OAuth 2.0 JWT Secured Authorization Request[FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html) - Financial-grade API Security Profile 1.0 - Part 1: Baseline[FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) - Financial-grade API Security Profile 1.0 - Part 2: Advanced[FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md) - Financial-grade API Security Profile 2.0 - Part 1: Baseline[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[LIWP](https://bitbucket.org/openid/fapi/src/master/Financial_API_Lodging_Intent.md) - OIDF FAPI WG Lodging Intent Working Paper[OFB-FAPI-DCR](https://openbanking-brasil.github.io/specs-seguranca/open-banking-brasil-dynamic-client-registration-1_ID3.html) - Open Finance Brasil Financial-grade API Dynamic Client Registration Profile 1.0[RFC4648](https://tools.ietf.org/html/rfc4648) - The Base16, Base32, and Base64 Data Encodings
## 3. Termos e definições
Para efeitos deste documento, os termos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) e ISO29100 se aplicam.
## 4. Símbolos e termos abreviados

- API - Application Programming Interface (Interface de programação de aplicativo)
- CSRF - Cross Site Request Forgery
- DCR - Registro de cliente dinâmico
- EIOFB - Estrutura Inicial do Open Finance Brasil
- FAPI - Financial-grade API
- HTTP - Protocolo de transferência de hipertexto
- MFA - Multi-Factor Authentication (Autenticação por Múltiplos Fatores)
- OIDF - OpenID Foundation
- REST - Representational State Transfer (Transferência de Estado Representacional)
- TLS - Transport Layer Security (Segurança da Camada de Transporte)

## 5. Profile de Segurança para o Open Finance Brasil

### 5.1. Introdução
O perfil de segurança do Open Finance Brasil especifica requisitos adicionais de segurança e de identificação para o acesso a API's com recursos críticos protegidas pelo OAuth 2.0 Authorization Framework, que consiste em [RFC6749](https://tools.ietf.org/html/rfc6749), [RFC6750](https://tools.ietf.org/html/rfc6750), [RFC7636](https://tools.ietf.org/html/rfc7636), [FAPI-1-Baseline](https://openid.net/specs/openid-financial-api-part-1-1_0.html), [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e outras especificações.Este perfil descreve as capacidades e os recursos de segurança que devem ser oferecidos por servidores e clientes que são necessários para o Programa do Open Finance Brasil, definindo as medidas para mitigar ou endereçar:
- ataques que abordam considerações de privacidade identificadas na cláusula 9.1 de [FAPI-1 Advanced].
- o requisito de concessão de acesso granular a recursos, com vistas à minimização de dados;
- o requisito de informar sobre o contexto da autenticação do usuário (claim Authentication Context Request - acr) que foi realizada por um Provedor OpenID, com vistas a favorecer o adequado gerenciamento do risco decorrente do acesso do usuário;

### 5.2. Disposições de segurança do Open Finance Brasil

#### 5.2.1. Introdução
O Open Finance Brasil tem um requisito para endereçar considerações de privacidade que foram identificadas, mas não abordadas na especificação final [FAPI-1-Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html), sem impor requisitos adicionais aos Servidores de Autorização que estão sendo propostos em [FAPI-2-Baseline](https://bitbucket.org/openid/fapi/src/master/FAPI_2_0_Baseline_Profile.md).Este perfil descreve os requisitos de gerenciamento de clientes necessários para dar suporte ao ecossistema Open Finance Brasil mais amplo.Como um perfil do OAuth 2.0 Authorization Framework, este documento exige o seguinte para o perfil de segurança do Open Finance Brasil.
#### 5.2.2. Servidor de Autorização
O Servidor de Autorização deve suportar as disposições especificadas na cláusula 5.2.2 de [Financial-grade API Security Profile 1.0 - Parte 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html).Além disso, ele deve:
1. deve realizar a autenticação do cliente utilizando private_key_jwt;
2. deve exigir requisições do tipo "pushed authorization requests" PAR;
3. deve publicar metadados de descoberta (incluindo a do endpoint de autorização) por meio do documento de metadado especificado em OIDD e [RFC8414] (".well-known");
4. deve suportar os parâmetros claims como definido no item 5.5 do OpenID Connect Core ;
5. deve suportar o atributo acr "urn:brasil:openbanking:loa2" como definido no item 5.2.2.3;
6. deveria suportar o atributo acr "urn:brasil:openbanking:loa3" como definido no item 5.2.2.3;
7. deve implementar o endpoint "userinfo" como definido no item 5.3 do OpenID Connect Core ;
8. deve suportar o escopo parametrizável ("parameterized OAuth 2.0 resource scope") consent como definido no item 6.3.1 de OIDF FAPI WG Lodging Intent Pattern ;
9. pode suportar Financial-grade API: Client Initiated Backchannel Authentication Profile ;
10. (requisito temporariamente retirado);
11. deve suportar refresh tokens;
12. deve emitir access tokens com o tempo de expiração entre 300 (mínimo) e 900 (máximo) segundos;
13. deve sempre incluir a claim acr no id_token;
14. deve suportar os valores code e id_token para o atributo response_type;
15. não deve permitir o recurso de rotação de refresh tokens;
16. deve garantir que em caso de compartilhamento do Servidor de Autorização para outros serviços, além do Open Finance, não divulgue e/ou possibilite o uso de métodos não certificados no ambiente do Open Finance;
17. deve garantir que as configurações divulgadas aos demais participantes através do OpenID Discovery (indicado pelo arquivo de Well-Known cadastrado no Diretório) sejam restritos aos modos de operação aos quais a instituição se certificou; deve manter em suas configurações os métodos para os quais ainda haja clientes ativos; deve atualizar os cadastros que utilizem métodos não certificados, através de tratamento bilateral entre as instituições envolvidas;
18. deve recusar requisições, para o ambiente do Open Finance, que estejam fora dos modos de operação ao qual a instituição certificou seu Servidor de Autorização;
19. o tempo mínimo de expiração do request_uri deve ser de 60 segundos;
20. deve recusar requisições que não apresentem o cabeçalho x-fapi-interaction-id em endpoints de recursos protegidos;
21. deve exigir a utilização de Proof Key for Code Exchange (PKCE);
22. deve exigir a utilização do subject_type “public”;
23. deve exigir a utilização do response_mode “fragment”;
24. Deve emitir refresh_tokens (JWT ou opaco) sem prazo de validade nos cenários onde o mesmo é necessário.

##### 5.2.2.1. Token de ID como assinatura separada
O Servidor de Autorização deve suportar as disposições especificadas na cláusula 5.2.2.1 de [Financial-grade API Security Profile 1.0 - Parte 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html)
1. Deve obrigatoriamente criptografar o id_token nos momentos de call-back e chamada do endpoint de token;
2. Para a criptografia do id_token deve ser utilizada chave disponível no JWKS informado no parâmetro jwks_uri, com o atributo “use”:”enc”, durante o registro do cliente, indicada através do cabeçalho kid do documento JWT;
3. O uso de outros cabeçalhos para indicação da chave utilizada, como x5u, x5c, jku ou jkw é vetado conforme definido na cláusula 2 OIDC .

##### 5.2.2.2. Clarificações sobre a "sub" Claim
Este perfil usa a definição oficial encontrada em: Analise requisitos de criptografia ID_TOKEN. Isso significa que o sub é um identificador nunca transferido ou alterado para o usuário final dentro da emissora (detentora/transmissora).
##### 5.2.2.3. Solicitando o "urn:brasil:openbanking:loa2" ou "urn:brasil:openbanking:loa3" Solicitação de contexto de autenticação
Esse perfil define "urn:brasil:openbanking:loa2" e "urn:brasil:openbanking:loa3" como novas classes de "Authentication Context Request" (ACR)
- LoA2: mecanismo de autenticação com a adoção de um único fator
- LoA3: mecanismo de autenticação com múltiplos fatores de autenticação
A seguinte orientação deve ser observada para o mecanismo de autenticação das APIs do Open Finance Brasil:
- De acordo com o Art. 17 da Resolução Conjunta nº 01, as instituições devem adotar procedimentos e controles para autenticação de cliente compatíveis com os aplicáveis ao acesso a seus canais de atendimento eletrônicos.
- Em observância à regulação em vigor, sugere-se que: Para a autenticação do usuário em autorizações de acessos às APIs de compartilhamento de dados (Fase 2), os Authorization Servers deveriam adotar, no mínimo, método compatível com LoA2; e Para a autenticação do usuário em autorizações de acessos às API's das fases subsequentes, os Authorization Servers deveriam adotar método de autenticação compatível com LoA3 ou superior.
Em todos os casos, a adoção de mecanismo de autenticação mais rigoroso (LoA3 ou superior) fica a critério da instituição transmissora ou detentora de conta, de acordo com sua avaliação de riscos e de forma compatível com os mecanismos habitualmente utilizados.Esclarecimentos adicionais sobre fatores de autenticaçãoSão fatores de autenticação:
- Aquilo que você conhece, como uma senha ou frase secreta
- Aquilo que você tem, como um token, smartcard ou dispositivo
- Aquilo que "você é", ou seja, autenticação condicionada a apresentação de uma característica física exclusivamente sua, como a validação por biometria
Para realizar autenticação por múltiplos fatores (MFA) é necessário que o usuário apresente, ao menos, dois diferentes fatores dos listados acima. Um mesmo fator usado mais de uma vez - por exemplo, a apresentação de suas senhas que ele conhece - não pode ser aceito como MFA.
##### 5.2.2.4 Escopos obrigatórios no endpoint de descoberta (well-known)
O servidor de autorização, contidos em organizações que possuem a role DADOS,  deve obrigatoriamente declarar os escopos abaixo em seu endpoint de descoberta (well-known), independentemente se a instituição forneça ou não os produtos referentes aos escopos abaixo listados: 
- invoice-financings
- financings
- loans
- unarranged-accounts-overdraft
- bank-fixed-incomes
- credit-fixed-incomes
- variable-incomes
- treasure-titles
- funds
- exchanges
Os escopos não listados acima devem ser declarados caso a instituição forneça produtos referentes aos mesmos (ex: accounts, payments).
#### 5.2.3. Cliente confidencial
Um cliente confidencial deve apoiar as disposições especificadas na cláusula 5.2.3 de [Financial-grade API Security Profile 1.0 - Part 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html),Além disso, o cliente confidencial
1. deve suportar objetos de solicitação encrypted;
2. deve suportar solicitações de autorização push (pushed authorization requests) PAR ;
3. deve suportar o escopo de recurso OAuth 2.0 parametrizado consent conforme definido na cláusula 6.3.1 OIDF FAPI WG Lodging Intent Pattern ;
4. deve suportar refresh tokens;
5. não deve incluir um valor específico na claim acr;
6. deve definir a claim acrcomo essential;
7. deve suportar todos os métodos de autenticação especificados no item 14 da seção 5.2.2 da Financial-grade API Security Profile 1.0 - Part 2: Advanced incluindo as diferentes combinações de métodos de encaminhamento dos Requests Objects (usando ou não PAR - item 11);
8. não deve permitir o recurso de rotação de refresh tokens;
9. deve enviar o cabeçalho x-fapi-interaction-id em endpoints FAP

## 6. Considerações de segurança
Os participantes devem apoiar todas as considerações de segurança especificadas na cláusula 8 [Financial-grade API Security Profile 1.0 - Parte 2: Advanced](https://openid.net/specs/openid-financial-api-part-2-1_0.html) e o [Manual de Segurança de Banco Central do Brasil](https://www.bcb.gov.br/estabilidadefinanceira/exibenormativo?tipo=Instru%C3%A7%C3%A3o%20Normativa%20BCB&numero=134). O ICP Brasil emite certificados RSA x509 somente, portanto, para simplificar, a seção remove o suporte para algoritmos EC e exige que apenas algoritmos de criptografia recomendados pela IANA sejam usados.
### 6.1. Considerações sobre assinatura do conteúdo de mensagens (JWS)
Para garantir a integridade e o não-repúdio das informações tramitadas em API's sensíveis e que indicam essa necessidade na sua documentação, deve ser adotado a estrutura no padrão JWS definida na [RFC7515](https://tools.ietf.org/html/rfc7515) e que inclui:
- Cabeçalho (JSON Object Signing and Encryption - JOSE Header), onde se define o algoritmo utilizado e inclui informações sobre a chave pública ou certificado que podem ser utilizadas para validar a assinatura;
- Payload (JWS Payload): conteúdo propriamente dito e detalhado na especificação da API;
- Assinatura digital (JWS Signature): assinatura digital, realizada conforme parâmetros do cabeçalho.

1. Cada elemento acima deve ser codificado utilizando o padrão Base64url RFC4648 e, feito isso, os elementos devem ser concatenados com "." (método JWS Compact Serialization, conforme definido na RFC7515 ).
2. O payload das mensagens (requisição JWT e resposta JWT) assinadas devem incluir as seguintes claims presentes na RFC7519 :

- aud (na requisição JWT): o Provedor do Recurso (p. ex. a instituição detentora da conta) deverá validar se o valor do campo aud coincide com o endpoint sendo acionado;
- aud (na resposta JWT): o cliente da API (p. e. instituição iniciadora) deverá validar se o valor do campo aud coincide com o seu próprio organisationId listado no diretório;
- iss (na requisição JWT e na resposta JWT): o receptor da mensagem deverá validar se o valor do campo iss coincide com o organisationId do emissor;
- jti (na requisição JWT e na resposta JWT): o valor do campo jti deverá ser preenchido com o UUID definido pela instituição de acordo com a [RFC4122] usando o versão 4;
- iat (na requisição JWT e na resposta JWT): o valor do campo iat deverá ser preenchido com horário da geração da mensagem e de acordo com o padrão estabelecido na RFC7519 para o formato NumericDate.
- cty (na requisição JWT e na resposta JWT): o valor do campo cty deverá ser preenchido caso as operações de assinatura ou criptografia aninhadas não sejam empregadas, o uso desse parâmetro de cabeçalho não é recomendado. No caso de assinatura aninhada ou criptografia ser empregada, este parâmetro de cabeçalho deve estar presente; neste caso, o valor deve ser "JWT", para indicar que um JWT aninhado é transportado neste JWT. Embora os nomes dos tipos de mídia não diferenciem maiúsculas de minúsculas, é recomendável que "JWT" sempre seja escrito com caracteres maiúsculos para compatibilidade com implementações herdadas.

1. O content-type HTTP das requisições e respostas com mensagens JWS deve ser definido como: "application/jwt".
2. No cabeçalho JOSE deve constar os seguintes atributos:

- alg - deve ser preenchido com o valor PS256";
- kid - deve ser obrigatoriamente preenchido com o valor do identificador da chave utilizado para a assinatura;
- Em caso de erro na validação da assinatura pelo Provedor do Recurso a API deve retornar mensagem de erro HTTP com status code 400 e a resposta deve incluir na propriedade code do objeto de resposta de erro especificado na API (ResponseError) a indicação da falha com o conteúdo BAD_SIGNATURE.
- Erros na validação da mensagem recebida pela aplicação cliente (p. ex. iniciador de pagamento) devem ser registrados e o Provedor do Recurso (p. ex. instituição detentora de conta) deve ser notificado.

1. O receptor deve validar a consistência da assinatura digital da mensagem JWS exclusivamente com base nas informações obtidas do diretório, ou seja, com base nas chaves publicadas no JWKS da instituição no diretório.
2. As assinaturas devem ser realizadas com uso do certificado digital de assinatura especificado no Padrão de Certificados Open Finance Brasil ;
3. A claim iat deve ser numérica no formato Unix Time GMT+0 com tolerância de +/- 60 segundos;
4. A claim do jti deve ser única para um clientId dentro de um intervalo de tempo de 86.400 segundos (24h), não podendo ser reutilizada neste período. Em caso de reutilização, deverá ser retornado o código de erro HTTP 403. Demais casos seguir instrução da RFC 6749, item 5.2;

#### 6.1.1. Considerações sobre algoritmos de assinatura
Para JWS, clientes e servidores de autorizaçãodevem usar o algoritmo PS256;
#### 6.1.2. Considerações de algoritmo de criptografia
Para JWE, clientes e servidores de autorizaçãodevem usar RSA-OAEP com A256GCM
#### 6.1.3. Considerações sobre o uso seguro do Transport Layer Security
Para TLS, endpoints do Servidor de Autenticação e endpoints do Servidor de Recursos usados diretamente pelo cliente:
1. devem suportar TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256
2. devem suportar TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384
3. As funcionalidades "TLS Session Resumption" e "TLS Renegotiation" devem ser desabilitadas

## 7. Considerações sobre compartilhamento de dados

### 7.1. Mecanismo de Autorização

#### 7.1.1. Introdução
Os mecanismos existentes para gerenciar adequadamente o acesso aos recursos definidos em [RFC6749](https://tools.ietf.org/html/rfc6749) são insuficientes para atender aos requisitos de um ecossistema de compartilhamento de dados moderno. Aproveitar strings de escopo estático não fornece aos consumidores controle de granularidade suficiente para compartilhar com terceiros. O Open Finance Brasil optou por implementar uma [API de consentimento](https://openbanking-brasil.github.io/areadesenvolvedor/swagger/swagger_consents_apis.yaml) como um recurso protegido OAuth 2.0 que pode ser usado para gerenciar o acesso granular aos recursos. A referência ao recurso de consentimento será transmitida como parte de um escopo de recurso dinâmico OAuth 2.0.
#### 7.1.2. Definição de Escopo de Consentimento Dinâmico
Este perfil define o escopo dinâmico do OAuth 2.0 "consentimento" da seguinte maneira:
- string 'consent’ ou ‘recurring-consent’; e
- delimitador de dois pontos ":"; e
- Consent API REST Resource Id retornado por uma criação bem-sucedida de Open Finance Consent Resource ;
Adicionalmente:
- Consent Resource Id deve incluir caracteres seguros para url;
- Consent Resource Id deve ser "namespaced";
- Consent Resource Id deve ter propriedades de um nonce Nonce ;

#### 7.1.3. Exemplo de escopo de consentimento dinâmico
consent:urn:bancoex:C1DD33123
### 7.2. Ciclo de vida da autorização

#### 7.2.1. Introdução
O recurso de consentimento tem um ciclo de vida gerenciado separada e distintamente da estrutura de autorização OAuth 2.0. As transições de estado e comportamentos esperados e condições de erro esperados dos Recursos REST protegidos com este perfil são definidos nas especificações funcionais da API publicadas pelo Open Finance Brasil.
#### 7.2.2. Servidor de autorização
Além dos requisitos descritos nas disposições de segurança do Open Finance Brasil, o Servidor de Autorização
1. deve apenas emitir refresh_tokens quando vinculados a um consentimento ativo e válido; Não deve emitir refresh_token quando o consentimento estiver no status “CONSUMED” (para fase 3); Deve emitir um access_token por meio de um grant_type do tipo client credentials no status “CONSUMED” (para fase 3).
2. só deve compartilhar o acesso aos recursos quando apresentado access_token vinculado a um consentimento ativo e com o status "AUTHORISED“. Para tokens gerados com o scope: payments ou recurring-payments , o status do consentimento não será validado; No cenário de recebimento de token inválido, deve ser retornado status code 401.
3. deve revogar os refresh tokens e, quando aplicável, os access tokens quando o Consentimento (Consent Resource) relacionado for apagado;
4. deve garantir que os access tokens são emitidos com os scopes necessários para permitir acesso aos dados especificados em elemento Permission do Consentimento (Consent Resource Object) relacionado;
5. não deve rejeitar pedido de autorização com scopes além do necessário para permitir acesso a dados definidos em elemento Permission do Consentimento (Consent Resource Object) relacionado;
6. pode reduzir o escopo solicitado para um nível que seja suficiente para permitir o acesso aos dados definidos em elemento Permission do Consentimento (Consent Resource Object) relacionado;
7. deve manter registros sobre o histórico dos consentimento para permitir a adequada formação de trilhas de auditoria em conformidade com a regulação em vigor;
8. deve retornar falha na autenticação e o código de retorno _accessdenied no parâmetro erro (como especificado na seção 4.1.2.1 da RFC6749 ) caso o CPF do usuário autenticado não seja o mesmo indicado no elemento loggedUser do Consentimento (Consent Resource Object);
9. deve retornar falha na autenticação e o código de retorno _accessdenied no parâmetro erro (como especificado na seção 4.1.2.1 da RFC6749 ) caso o elemento businessEntity não tenha sido preenchido no Consentimento (Consent Resource Object) relacionado e o usuário tenha selecionado ou se autenticado por meio de credencial relacionada à conta do tipo Pessoa Jurídica (PJ);
10. deve condicionar a autenticação ou seleção de contas do tipo PJ à consistência entre o CNPJ relacionado à(s) conta(s) e o valor presente no elemento businessEntity do Consentimento (Consent Resource Object). Em caso de divergência deve retornar falha na autenticação e o código de retorno access_denied no parâmetro erro (como especificado na seção 4.1.2.1 da RFC6749 );
11. deve emitir refresh_token com validade não inferior à validade do consentimento ao qual está relacionado, respeitado os demais critérios acima.

#### 7.2.3. Cliente confidencial
Além dos requisitos descritos nas disposições de segurança do Open Finance Brasil, o Cliente Confidencial
1. deve, sempre que possível, revogar e cessar o uso de refresh e de access tokens vinculados a um consentimento (Consent Resource Object) que foi excluído;
2. deve excluir consentimentos (Consent Resource Objects) que estão expirados;

## 8. Reconhecimentos
Agradecemos a todos que estabeleceram as bases para o compartilhamento seguro e seguro de dados por meio da formação do Grupo de Trabalho FAPI da OpenID Foundation, o GT de Segurança do Open Finance Brasil e aos pioneiros que ficarão em seus ombros.As seguintes pessoas contribuíram para este documento:
- Alexandre Siqueira (Mercado Pago)
- Joseph Heenan (Authlete)
- Marcos Rodrigues (Itaú)
- Mário Ginglass (BNDES)
- Nic Marcondes (Quanto)
- Ralph Bragg (Raidiam)

## Appendix A. Avisos
Copyright (c) 2023 Estrutura Inicial do Open Finance BrasilA Estrutura Inicial do Open Finance Brasil (EIOFB) concede a qualquer Colaborador, desenvolvedor, implementador ou outra parte interessada uma licença de direitos autorais mundial não exclusiva, livre de royalties para reproduzir, preparar trabalhos derivados, distribuir, executar e exibir, estes Implementadores Rascunho ou Especificação Final exclusivamente para fins de (i) desenvolver especificações e (ii) implementar Rascunhos de Implementadores e Especificações Finais com base em tais documentos, desde que a atribuição seja feita ao EIOFB como a fonte do material, mas que tal atribuição o faça não indica endosso do EIOFB.A tecnologia descrita nesta especificação foi disponibilizada a partir de contribuições de várias fontes, incluindo membros da OpenID Foundation, do Grupo de Trabalho de Segurança do Open Finance Brasil e outros. Embora a Estrutura Inicial do Open Finance Brasil tenha tomado medidas para ajudar a garantir que a tecnologia esteja disponível para distribuição, ela não toma posição quanto à validade ou escopo de qualquer propriedade intelectual ou outros direitos que possam ser reivindicados como pertencentes à implementação ou uso do tecnologia descrita nesta especificação ou até que ponto qualquer licença sob tais direitos pode ou não estar disponível; nem representa que fez qualquer esforço independente para identificar tais direitos. A Estrutura Inicial do Open Finance Brasil e os contribuidores desta especificação não oferecem (e por meio deste expressamente se isentam de quaisquer) garantias (expressas, implícitas ou de outra forma), incluindo garantias implícitas de comercialização, não violação, adequação a uma finalidade específica ou título, relacionados a esta especificação, e todo o risco quanto à implementação desta especificação é assumido pelo implementador. A política de Direitos de Propriedade Intelectual do Open Finance Brasil exige que os contribuidores ofereçam uma promessa de patente de não fazer valer certas reivindicações de patentes contra outros contribuidores e implementadores. A Estrutura Inicial do Open Finance Brasil convida qualquer parte interessada a trazer à sua atenção quaisquer direitos autorais, patentes, pedidos de patentes ou outros direitos de propriedade que possam abranger a tecnologia que possa ser necessária para praticar esta especificação.
## Author's Address
OFBIS GT SecurityOpen Finance Brasil Initial StructureEmail: [gt-seguranca@openfinancebrasil.org.br](mailto:gt-seguranca@openfinancebrasil.org.br)URI: [https://openfinancebrasil.org.br](https://openfinancebrasil.org.br/)

---

# Política de versionamento (Segurança) > Change log (Segurança)

---
id: 240650712
title: Change log (Segurança)
version: 2
modified: 2023-12-15T14:57:17.572Z
url: /spaces/OF/pages/240650712/Change+log+Seguran+a
---

No Portal do Desenvolvedor, foi criado uma página (Histórico de Segurança), que contém o Change Log, com todas as informações sobre as alterações e histórico das versões anteriores.
O Change log, foi criado com os seguintes requisitos que precisam ser preenchidos, para garantir a rastreabilidade de todos as alterações.**De/Para - Versão**: Informar para qual versão a alteração esta sendo realizado.**Ítem de Trabalho**: Informar qual a proposta que foi realizada a discussão e aprovação da mudança.**Demandante**: Quem solicitou a mudança.**O que foi alterado?**: Informar todas as alterações do documento.**Motivador**: Informar qual o motivador da alteração.

---

# Política de versionamento (Segurança) > Ciclo de Vida (Segurança)

---
id: 240650601
title: Ciclo de Vida (Segurança)
version: 2
modified: 2023-12-15T14:57:01.578Z
url: /spaces/OF/pages/240650601/Ciclo+de+Vida+Seguran+a
---

## Etapas do Ciclo de vida dos Documentos de Segurança

- Design - Etapa em que um dos GTs de Segurança estão construindo uma nova versão da Documentação. Nesta etapa a parte das especificações já desenvolvidas e aprovadas pelo GT serão disponibilizadas no ambiente de Draft na Área do Desenvolvedor no Portal do Open Finance. O início das discussões sobre a evolução da Documentação pelo GT de Segurança marca o início desta etapa;
- Implementing - Etapa em que a nova versão da Documentação (unstable) estará disponível. O evento de publicação da nova versão da Documentação na Área do Desenvolvedor marcará o início desta etapa; Poderá ser usada para reportar possíveis bugs nas especificações;
- Certifying - etapa em que a versão unstable da Documentação estará disponível para implementação. Poderá ser usada para reportar possíveis bugs nas especificações;
- Current - etapa que indica a versão oficial da Documentação que deve estar em produção. Quando uma nova versão da Documentação (x+1) entrar em produção a versão antiga (versão x) sairá da etapa current para deprecated durante o período de convivência e a nova versão (versão x+1) sairá da etapa certifying para current. O evento de entrada em produção marcará o início desta etapa.
- Deprecated - etapa em que a versão atual (versão x) da Documentação está sendo substituída pela próxima versão (x+1) em ambiente produtivo pelos participantes dando início ao período de convivência destas versões. O evento de entrada em produção da próxima versão da Documentaçao marcará o início desta etapa.
- Retired - etapa em que a versão da Documentação se torna indisponível em ambiente produtivo. O evento de remoção desta versão da Documentação do ambiente produtivo marcará o início desta etapa.

## Período de Convivência

- Quando temos a versão x em deprecated, significa que a versão x+1 está em current;
- Este período é utilizado para que tenhamos uma transição mais suave entre a versão que está sendo aposentada (retired) e a versão que está se tornando oficial (current);
- O período de convivência terá no máximo duas versões da mesma Documentação convivendo;
- A duração do período de convivência será definido no GT Segurança, de acordo com a alteração que foi realizada na documentação. Só se aplica em casos de versões Major e Minor.

---

# Política de versionamento (Segurança) > Fluxo de especificação dos documentos (Segurança)

---
id: 240650643
title: Fluxo de especificação dos documentos (Segurança)
version: 2
modified: 2023-12-15T14:57:09.788Z
url: /spaces/OF/pages/240650643/Fluxo+de+especifica+o+dos+documentos+Seguran+a
---

Foi desenhado o fluxo de especificação com o intuito de entender como é o processo de novas alterações nos documentos que causam novos versionamentos. O Fluxo foi detalhado com cada responsável.
### Fluxo de Especificação

#### Responsáveis

- Revisão e aprovação do conteúdo: GT Segurança – Análise das 6 cadeiras  (Aprovação de 4 cadeiras) Conselho Deliberativo – Aprovação do CD

- Abertura de Solicitação e Publicação no Portal: DTO (Fábio Szescsik) – Abertura da Solicitação de alteração ( Portal de Serviços - Abertura de solicitação ) CoE de Qualidade – Atendimento das solicitações de alterações

### Comunicações ao Ecossistema
Sempre que houver um versionamento Major, Minor ou Patch, será necessário encaminhar um Informa ao Ecossistema, a fim de garantir que todos os participantes possam estar de acordo com as alterações e realizarem as correções nos seus produtos, se necessário.**Responsável pelo Informa:**Secretariado - GT Segurança

---

# Política de versionamento (Segurança) > Tipos de Versionamento (Segurança)

---
id: 240650571
title: Tipos de Versionamento (Segurança)
version: 2
modified: 2023-12-15T14:56:55.650Z
url: /spaces/OF/pages/240650571/Tipos+de+Versionamento+Seguran+a
---

O controle de versão dos documentos de Segurança do Open Finance Brasil é composto pelos tipos de versionamento *major*, *minor*e *patch*. Os nomes e o formato de numeração utilizados pelos tipos de versionamento são idênticos aos utilizados no *semantic versioning*, no entanto, a definição utilizada diverge. 
A seguir, as definições para cada um dos tipos de versionamento:
- Major: Deve ser incrementada quando ocorrem mudanças substanciais que afetam significativamente o conteúdo, a estrutura ou o propósito do documento. Por exemplo: Alterações nas políticas ou diretrizes de segurança que têm um impacto substancial nas operações ou no cumprimento das regulamentações; Adição ou remoção de seções importantes no documento; Mudanças que afetam a conformidade com regulamentos ou padrões de segurança e que necessitem de recertificação; Mudanças significativas na abordagem ou estratégia de segurança; v X .0.0

- Minor : Deve ser usada para alterações relativamente pequenas que não impactam drasticamente a estrutura do documento, mas ainda são relevantes para manter a documentação atualizada e precisa. Isso pode incluir: Atualizações de detalhes; Adição de exemplos, ilustrações ou notas explicativas; Pequenas revisões que não impactam a conformidade ou o significado do documento; Mudanças que afetam a conformidade com regulamentos ou padrões de segurança de forma pontual e com baixo impacto nas atuais especificações; v1. X .0

- Versão Patch: Deve ser incrementada quando ocorrem correções de erros, esclarecimentos ou ajustes menores para resolver problemas menores na documentação de segurança. Por exemplo: Correção de erros ortográficos ou gramaticais. Correção de links quebrados Esclarecimentos na redação de procedimentos de registro e rastreamento de acesso. v1.0 .X

---

# Redirecionamento App-to-App > Histórico da página - Redirecionamento App-to-App

---
id: 240650341
title: Histórico da página - Redirecionamento App-to-App
version: 2
modified: 2023-12-15T14:55:23.035Z
url: /spaces/OF/pages/240650341/Hist+rico+da+p+gina+-+Redirecionamento+App-to-App
---

## Change log
 
| De / Para - Versão | Item de trabalho (Conteúdo Motivador) | Demandante | O que foi alterado? | Motivador |
| --- | --- | --- | --- | --- |
| | | | | |
| | | | | |

---

# Redirecionamento App-to-App > v1.0 - Redirecionamento App-to-App

---
id: 240650317
title: v1.0 - Redirecionamento App-to-App
version: 2
modified: 2023-12-15T14:55:17.628Z
url: /spaces/OF/pages/240650317/v1.0+-+Redirecionamento+App-to-App
---

O redirecionamento 'App-to-App' permite que a Instituição Receptora redirecione um usuário do seu aplicativo (em um navegador ou app) para o App da Instituição Transmissora, instalado no dispositivo do usuário. Nesse caso, a receptora é capaz de transmitir detalhes de sua solicitação junto com as preferências do usuário (por exemplo, tipo de produto, *one-step authentication*, etc) e ligar diretamente o seu usuário à tela ou função de login do aplicativo da transmissora, através de um *deep-link*. O usuário é então autenticado no aplicativo usando as mesmas credenciais/métodos normalmente usados quando ele acessa diretamente sua conta. Isso não deve envolver nenhuma etapa adicional (como, por exemplo, ser redirecionado primeiro para uma página da web para selecionar qual aplicativo da instituição transmissora usar) e não deve exigir que o usuário forneça qualquer identificador ou outras credenciais diferentes das já exigidas pela Instituição Transmissora em seu App. Quando o usuário não tem o App da transmissora, eles devem experimentar um fluxo de redirecionamento que também não deve envolver etapas adicionais do que seria o caso quando ele autentica diretamente na transmissora (por exemplo, ser redirecionado para o site *mobile* da transmissora).
### Como funciona o fluxo de redirecionamento
Ao usar um serviço baseado no padrão de APIs Open Finance Brasil para redirecionamento, o usuário será redirecionado duas vezes:
1. Da interface instituição receptora para a interface da transmissora (para autenticar e autorizar). O URI do servidor de autorização é especificado por cada transmissora em seu endpoint conhecido.
2. Na volta da interface da transmissora para a interface da receptora (para completar qualquer operação com a receptora). Este redirecionamento é especificado pela receptora como parte do primeiro redirecionamento.

### Implementação de deep links
Uma jornada perfeita para o usuário, que ignora o navegador integrado (por exemplo, Safari) em seu dispositivo *mobile*, pode ser implementada para qualquer URL, ou seja, ambos: a) para o redirecionamento inicial para o qual a transmissora envia o usuário para os servidores da transmissora, E b) a URL de redirecionamento para o qual a transmissora envia o usuário de volta para a receptora após a autenticação/autorização.Tanto transmissoras quanto receptoras devem seguir as orientações da Apple e do Google abaixo:
- iOS: https://developer.apple.com/ios/universal-links/ (cobre mais de 99% de todos os usuários iOS, que estão no iOS 9 ou superior).
- Android: https://developer.android.com/training/app-links/index.html (cobre 98% de todos os usuários do Android, que estão no Android 6.0 ou posterior).
No caso de um usuário não ter o aplicativo instalado em seu dispositivo, ou se ele tiver um sistema operacional mais antigo ou sem suporte (por exemplo, Windows Mobile), esses métodos permitirão que o usuário seja redirecionado para uma página web *mobile*.

---

# Visão Geral > v2.0 - Visão Geral

---
id: 240648227
title: v2.0 - Visão Geral
version: 2
modified: 2023-12-15T14:50:28.446Z
url: /spaces/OF/pages/240648227/v2.0+-+Vis+o+Geral
---

- 1 Atualização do Perfil de Segurança
- 2 Visão Geral Ecossistema 2.1 Participantes de um Ecossistema de Compartilhamento de Dados 2.2 Princípios de Especificação e Requisitos de Alto Nível
- 3 Principais Padrões de Segurança 3.1 Estrutura de Autorização OAuth 2.0 3.2 OpenID Connect - A Camada de Identidade para a Internet 3.3 OpenID Financial Grade 1.0: Baseline 3.4 OpenID Financial Grade 1.0: Avançado
- 4 Perfil de Segurança do Open Finance Brasil
- 5 Camadas de Segurança Básicas

## Atualização do Perfil de Segurança
O perfil de segurança está em período de transição. O novo perfil será de implementação obrigatória para todos os participantes em 22/05/2024. O perfil anterior continuará vigente até 21/05/2024. Para acessar as documentações do perfil vigente até 21/05/2024, utilize os links da tabela abaixo:
## Visão Geral Ecossistema
Em sua essência, o Open Finance Brasil é um ecossistema de compartilhamento de dados onde os clientes de bancos e outras instituições financeiras desejam compartilhar suas informações de conta ou dar permissão para que os pagamentos sejam executados em seu nome com serviços de terceiros.Há uma série de funções necessárias para vincular qualquer sistema de identificação, autenticação e autorização, independentemente do setor. Todas essas funções são necessárias, mas várias funções podem ser desempenhadas por cada participante. Em geral, o usuário final (“Subject”), está dando a um sistema (“Client”) uma autorização (“Access Token”) para acessar um recurso protegido mantido pelo provedor (“Resource Server”). Isso exige que o Subject e o Client sejam identificados e autenticados e que a autorização seja confirmada.As regras exatas e os requisitos legais para cada função em um setor específico formam um framework de confiança (‘Trust Framework’). Cada ecossistema requer um conjunto padronizado de regras e requisitos legais que abrangem todas as funções e obrigações das interações acima. A combinação de quem fornece qual(is) função(ões), os níveis aos quais eles devem desempenhar essas funções e os padrões pelos quais essas operações devem ser definidas por um framework de confiança específico do setor.Diferentes frameworks de confiança terão diferentes opções de implementação, mas um framework de confiança comum é um pré-requisito para transformar um ‘setor’ em um ‘ecossistema’. Um framework de confiança comum reduz significativamente a complexidade e custos, aumenta a escalabilidade e a interoperabilidade dentro do setor, bem como abre opções para o tipo de padronização intersetorial que o Open Finance Brasil está buscando.Diferentes implementações podem ser definidas para setores, com diferentes prós / contras e custos associados para diferentes participantes. Cada uma das implementações propostas pode ser usada para qualquer setor se os pré-requisitos corretos estiverem em vigor. A solução certa dependerá do apetite e alinhamento de cada conjunto de participantes.A implementação de um mecanismo comum para o Open Finance Brasil exigirá um compromisso com a simetria entre os setores para incluir detalhes específicos do setor nos princípios do framework de confiança.É necessário fazer escolhas técnicas para garantir que qualquer implementação forneça uma base estrita e consistente para ter credibilidade, mas mantenha a flexibilidade para se adaptar às necessidades futuras. Isso implica padrões de código-fonte aberto amplamente disponíveis, amplamente compreendidos e que foram experimentados e testados. Além de habilitar um gama de parceiros e fornecedores que podem apoiar qualquer construção técnica, o que significa que continuará havendo espaço para desenvolvimento comercial de soluções.
### Participantes de um Ecossistema de Compartilhamento de Dados
Nos ecossistemas de Open Finance voltados para o consumidor que estamos considerando, temos três participantes principais:
- o cliente (user)
- a instituição transmissora de dados (provider), que oferece serviços bancários
- a instituição receptora de dados (TPP - Third Party Provider), que oferece uma proposta de Open Finance para o cliente:
Em todos os casos a seguir, assumimos:
- Um cliente possui uma conta para um serviço principal ou conjunto de recursos numa instituição transmissora de dados
- Uma instituição receptora de dados oferece ao cliente uma proposta habilitada por meio do compartilhamento inteligente de dados
- O cliente dá consentimento à instituição receptora de dados para fins de entrega dessa proposta
- A instituição transmissora de dados tem a obrigação de salvaguardar os dados do cliente, mas também de compartilhá-los quando instruído.
O ecossistema também possui provedores de serviços de confiança, que são entidades que fornecem garantia técnica a ambas instituições (transmissoras e receptoras) de que todos estão autorizados a participar do ecossistema.Os padrões técnicos necessários para dar suporte ao framework de confiança devem atender todos os requisitos a seguir:
- Identificação de todos os participantes do ecossistema
- Autenticação quando exigida de todos os participantes entre si
- Confirmação de autorização de todos os participantes em um ecossistema de compartilhamento de dados
Os serviços técnicos necessários para suportar um ecossistema devem habilitar todos os requisitos acima em uma base e modo contínuos, isto é, não apenas em um único ponto de registro.
### Princípios de Especificação e Requisitos de Alto Nível
O Open Finance Brasil adotou os seguintes princípios e requisitos de alto nível no que diz respeito às normas técnicas.
- Consentimento Os clientes devem estar sempre no controle de quem tem acesso aos seus dados e para quais fins eles estão sendo usados.
- Minimização de dados Os clientes devem ser capazes de compartilhar apenas os dados de que precisam, pelo tempo que for necessário.
- Segurança Uma modelagem de ameaças foi produzido avaliando todas as fraquezas potenciais nos processos de comunicação. Todos os pontos fracos identificados foram corrigidos.
- Identificação Todos os participantes devem ter segurança na identificação de todos os atores do ecossistema.
- Autenticação Todos os participantes devem comunicar as etapas que foram executadas para autenticar cada participante no ecossistema e em que nível isso foi executado.
- Integridade e não repúdio Todos os participantes devem ser capazes de provar que as mensagens não foram adulteradas e, na verdade, foram enviadas apenas por um participante legítimo.
Além dos requisitos de alto nível, os seguintes princípios também foram adotados.
- Não reinventar a roda, se existir uma especificação que seja adequada para o propósito, amplamente adotada e publicamente disponível, deve-se adotá-la.
- Envolver-se com outros órgãos de normalização para aprender com experiências anteriores sobre o que funcionou, o que não funcionou, e o que pode ser feito melhor.
- Assegurar o amplo suporte da indústria para garantir o máximo de chances de sucesso e, mais importante, a segurança do cliente.
- Solicitar feedback com antecedência e com frequência, reconhecer que serão necessárias várias iterações para desenvolver um padrão.
- O framework de confiança que sustenta o ecossistema de compartilhamento de dados, que é o Open Finance Brasil, é um framework técnico que precisa ser flexível o suficiente para permitir que os participantes e o ecossistema inovem, cresçam e se desenvolvam, enquanto permanecem interoperáveis.
Todos os participantes devem ter certeza de que todos os atores do ecossistema estão lidando com seus dados com segurança o tempo todo. Isso requer que todos os participantes testem publicamente seus sistemas quanto à conformidade com as especificações e disponibilizem os resultados de seus testes de conformidade para exame público de outros participantes.Este é um requisito aplicável às instituições participantes transmissoras e receptoras de dados.
## Principais Padrões de Segurança

### Estrutura de Autorização OAuth 2.0
O ecossistema de compartilhamento de dados definido pelo Brasil consiste em muitos padrões diferentes, todos girando em torno de conceitos, funções e obrigações que foram tecnicamente definidos no [OAuth 2.0 Authorization Framework.](https://tools.ietf.org/html/rfc6749)A estrutura de autorização OAuth 2.0 permite uma aplicação de terceiros (third-party application) obter acesso limitado a um serviço HTTP, seja em nome do proprietário de recurso (resource owner) por meio da orquestração de uma interação de aprovação entre o proprietário do recurso e o serviço HTTP, ou permitindo a aplicação de terceiros obter acesso em seu próprio nome.A especificação base OAuth 2.0 não fornece, por si só, informações suficientes para atender a todas as necessidades definidas pelo framework de confiança do Open Finance Basil. Mais notavelmente, não possui uma maneira de transmitir informações de identidade do cliente em um formato padronizado de uma instituição transmissora para uma receptora, e os mecanismos de autenticação que foram definidos na especificação original não são seguros o suficiente para atender aos requisitos de uma indústria altamente regulamentada.
### OpenID Connect - A Camada de Identidade para a Internet
[OpenID Connect](https://openid.net/connect/) é um conjunto de especificações simplificadas que fornecem uma estrutura para interações de identidade por meio de APIs do tipo REST. A implementação mais simples do OpenID Connect permite que clients de todos os tipos, incluindo baseados em navegador, celulares e clients javascript, solicitem e recebam informações sobre identidades e sessões atualmente autenticadas. O conjunto de especificações é extensível, permitindo que os participantes também suportem, opcionalmente, criptografia de dados de identidade, descoberta do OpenID Provider e gerenciamento avançado de sessão, incluindo logout*Este perfil herda todas as obrigações do OAuth 2.0*O grupo de trabalho OpenID Foundations Connect tem sido o guardião do Padrão de Identidade “de fato” da Internet por muitos anos, trabalhando em várias especificações que se baseiam no framework de autorização OAuth 2.0, adicionando recursos e requisitos de suporte para melhorar a segurança do framework em si.[Open ID Connect Core:](https://openid.net/specs/openid-connect-core-1_0.html) é um perfil do OAuth 2.0, o que significa que herda todos os requisitos e obrigações do [OAuth 2.0](https://tools.ietf.org/html/rfc6749), mas define o conceito de um id_token e introduz novos mecanismos de autenticação.[Open ID Connect Discovery:](https://openid.net/specs/openid-connect-discovery-1_0.html) apresenta o conceito de um documento de descoberta usado por OpenID Connect (OIDC) Providers para anunciar como os clients OAuth 2.0 podem se comunicar com eles e quais recursos e opções o OIDC Provider oferece suporte.[RFC7591:](https://tools.ietf.org/html/rfc7591) além de definir o processo de registro dinâmico de clients OAuth, esta especificação apresenta o conceito de [Software Statement](https://tools.ietf.org/html/rfc7591#section-2.3) (“Declaração de Software”), que pode ser usada para fornecer informações sobre um client que é atestado por um serviço de terceiros. Outros atributos de metadados também são definidos no [OpenID Connect Registration Specification](https://openid.net/specs/openid-connect-registration-1_0.html)Esta especificação define mecanismos para registrar dinamicamente clients OAuth 2.0 com Authorization Servers (servidores de autorização). Pedidos de registro enviam um conjunto de valores de metadados do client desejado para o Authorization Server. As respostas de registro resultantes retornam um client identifier para ser usado no Authorization Server e os valores de metadados registrados para o client. O client pode então usar esta informação de registro para se comunicar com o Authorization Server usando o protocolo OAuth 2.0. Esta especificação também define um conjunto de campos de metadados do client e valores para os clients usarem durante o registro.[RFC7592:](https://tools.ietf.org/html/rfc7592) Esta especificação define métodos de gerenciamento de dynamic client registration (registros de cliente dinâmico) do OAuth 2.0 para casos de uso em que as propriedades de um client registrado necessitam ser alteradas durante a vida do client.As especificações acima são especificações básicas cuja leitura obrigatória sustenta o framework de confiança do Open Finance Brasil. Entretanto, eles ainda são insuficientes para atender a todos os requisitos e princípios descritos anteriormente.
### OpenID Financial Grade 1.0: Baseline
*Este perfil herda todas as obrigações do OpenID Connect Core*Reconhecendo as ameaças e riscos restantes que não foram tratados pelo OpenID Connect Core, o grupo de trabalho Financial Grade tem como foco criar uma especificação que visa identificar e endereçar os pontos fracos na especificação OpenID Connect, essencialmente criando um perfil para casos de uso que exigem alto nível segurança.O perfil Baseline foi originalmente planejado para ser mais facilmente implementado por clients e OpenID Providers às custas de alguns elementos de segurança e, como tal, não oferece o mesmo grau de proteção contra violação de solicitação e resposta.
### OpenID Financial Grade 1.0: Avançado
*Este perfil herda todas as obrigações do OpenID FAPI 1.0: Baseline*O [FAPI 1.0: Advanced profile](https://openid.net/specs/openid-financial-api-part-2-1_0.html) é atual padrão ouro para API Security, fornecendo um framework de especificação que foi usado como ponto de partida para a criação de uma especificação para o Open Finance Brasil.Este padrão especifica um perfil de segurança avançado do OAuth que é adequado para ser usado na proteção de APIs com alto risco inerente. Os exemplos incluem APIs que dão acesso a dados altamente confidenciais ou que podem ser usados para acionar transações financeiras (por exemplo, início de pagamento). Este padrão especifica os controles contra ataques, como: violação de solicitação de autorização, violação de resposta de autorização, incluindo injeção de código, injeção de estado e phishing de solicitação de token.
## Perfil de Segurança do Open Finance Brasil
 
| Perfil da certificação OIDF |
| BR-OB Adv. OP w/ Private Key, PAR |

## Camadas de Segurança Básicas

| Camada | Descrição | Explicação |
| Física | Firewall | Equipamentos e produtos como filtros, proxys e firewalls direcionados ao controle e segurança da rede física. |
| Transporte | HTTP - TLS 1.2 | Protocolo de criptografia que fornece segurança na comunicação sobre a rede física. |
| Gestão | API Gateway / Manager | Gateway e Manager para gerenciar a publicação da API com controles de throttling, quotas e outros. |

---

# Visão Geral > Histórico de Segurança - Visão Geral > v1.0 - Visão Geral

---
id: 240648318
title: v1.0 - Visão Geral
version: 2
modified: 2023-12-15T14:50:40.094Z
url: /spaces/OF/pages/240648318/v1.0+-+Vis+o+Geral
---

## Visão Geral Ecossistema
Em sua essência, o Open Finance Brasil é um ecossistema de compartilhamento de dados onde os clientes de bancos e outras instituições financeiras desejam compartilhar suas informações de conta ou dar permissão para que os pagamentos sejam executados em seu nome com serviços de terceiros.Há uma série de funções necessárias para vincular qualquer sistema de identificação, autenticação e autorização, independentemente do setor. Todas essas funções são necessárias, mas várias funções podem ser desempenhadas por cada participante. Em geral, o usuário final (“Subject”), está dando a um sistema (“Client”) uma autorização (“Access Token”) para acessar um recurso protegido mantido pelo provedor (“Resource Server”). Isso exige que o *Subject* e o *Client* sejam identificados e autenticados e que a autorização seja confirmada.As regras exatas e os requisitos legais para cada função em um setor específico formam um framework de confiança (‘Trust Framework’). Cada ecossistema requer um conjunto padronizado de regras e requisitos legais que abrangem todas as funções e obrigações das interações acima. A combinação de quem fornece qual(is) função(ões), os níveis aos quais eles devem desempenhar essas funções e os padrões pelos quais essas operações devem ser definidas por um framework de confiança específico do setor.Diferentes frameworks de confiança terão diferentes opções de implementação, mas um framework de confiança comum é um pré-requisito para transformar um ‘setor’ em um ‘ecossistema’. Um framework de confiança comum reduz significativamente a complexidade e custos, aumenta a escalabilidade e a interoperabilidade dentro do setor, bem como abre opções para o tipo de padronização intersetorial que o Open Finance Brasil está buscando.Diferentes implementações podem ser definidas para setores, com diferentes prós / contras e custos associados para diferentes participantes. Cada uma das implementações propostas pode ser usada para qualquer setor se os pré-requisitos corretos estiverem em vigor. A solução certa dependerá do apetite e alinhamento de cada conjunto de participantes.A implementação de um mecanismo comum para o Open Finance Brasil exigirá um compromisso com a simetria entre os setores para incluir detalhes específicos do setor nos princípios do framework de confiança.É necessário fazer escolhas técnicas para garantir que qualquer implementação forneça uma base estrita e consistente para ter credibilidade, mas mantenha a flexibilidade para se adaptar às necessidades futuras. Isso implica padrões de código-fonte aberto amplamente disponíveis, amplamente compreendidos e que foram experimentados e testados. Além de habilitar um gama de parceiros e fornecedores que podem apoiar qualquer construção técnica, o que significa que continuará havendo espaço para desenvolvimento comercial de soluções.
### Participantes de um Ecossistema de Compartilhamento de Dados
Nos ecossistemas de Open Finance voltados para o consumidor que estamos considerando, temos três participantes principais:
- o cliente ( user )
- a instituição transmissora de dados ( provider ), que oferece serviços bancários
- a instituição receptora de dados ( TPP - Third Party Provider ), que oferece uma proposta de Open Finance para o cliente:
Em todos os casos a seguir, assumimos:
- Um cliente possui uma conta para um serviço principal ou conjunto de recursos numa instituição transmissora de dados
- Uma instituição receptora de dados oferece ao cliente uma proposta habilitada por meio do compartilhamento inteligente de dados
- O cliente dá consentimento à instituição receptora de dados para fins de entrega dessa proposta
- A instituição transmissora de dados tem a obrigação de salvaguardar os dados do cliente, mas também de compartilhá-los quando instruído.
O ecossistema também possui provedores de serviços de confiança, que são entidades que fornecem garantia técnica a ambas instituições (transmissoras e receptoras) de que todos estão autorizados a participar do ecossistema.Os **padrões** técnicos necessários para dar suporte ao framework de confiança devem atender todos os requisitos a seguir:
- Identificação de todos os participantes do ecossistema
- Autenticação quando exigida de todos os participantes entre si
- Confirmação de autorização de todos os participantes em um ecossistema de compartilhamento de dados
Os **serviços** técnicos necessários para suportar um ecossistema devem habilitar todos os requisitos acima **em uma base e modo contínuos**, isto é, não apenas em um único ponto de registro.
### Princípios de Especificação e Requisitos de Alto Nível
O Open Finance Brasil adotou os seguintes princípios e requisitos de alto nível no que diz respeito às normas técnicas.
- Consentimento Os clientes devem estar sempre no controle de quem tem acesso aos seus dados e para quais fins eles estão sendo usados.
- Minimização de dados Os clientes devem ser capazes de compartilhar apenas os dados de que precisam, pelo tempo que for necessário.
- Segurança Uma modelagem de ameaças foi produzido avaliando todas as fraquezas potenciais nos processos de comunicação. Todos os pontos fracos identificados foram corrigidos.
- Identificação Todos os participantes devem ter segurança na identificação de todos os atores do ecossistema.
- Autenticação Todos os participantes devem comunicar as etapas que foram executadas para autenticar cada participante no ecossistema e em que nível isso foi executado.
- Integridade e não repúdio Todos os participantes devem ser capazes de provar que as mensagens não foram adulteradas e, na verdade, foram enviadas apenas por um participante legítimo.
Além dos requisitos de alto nível, os seguintes princípios também foram adotados.
- Não reinventar a roda, se existir uma especificação que seja adequada para o propósito, amplamente adotada e publicamente disponível, deve-se adotá-la.
- Envolver-se com outros órgãos de normalização para aprender com experiências anteriores sobre o que funcionou, o que não funcionou, e o que pode ser feito melhor.
- Assegurar o amplo suporte da indústria para garantir o máximo de chances de sucesso e, mais importante, a segurança do cliente.
- Solicitar feedback com antecedência e com frequência, reconhecer que serão necessárias várias iterações para desenvolver um padrão.
- O framework de confiança que sustenta o ecossistema de compartilhamento de dados, que é o Open Finance Brasil, é um framework técnico que precisa ser flexível o suficiente para permitir que os participantes e o ecossistema inovem, cresçam e se desenvolvam, enquanto permanecem interoperáveis.
Todos os participantes devem ter certeza de que todos os atores do ecossistema estão lidando com seus dados com segurança o tempo todo. Isso requer que todos os participantes testem publicamente seus sistemas quanto à conformidade com as especificações e disponibilizem os resultados de seus testes de conformidade para exame público de outros participantes.**Este é um requisito aplicável às instituições participantes transmissoras e receptoras de dados.**
## Principais Padrões de Segurança

### Estrutura de Autorização OAuth 2.0
O ecossistema de compartilhamento de dados definido pelo Brasil consiste em muitos padrões diferentes, todos girando em torno de conceitos, funções e obrigações que foram tecnicamente definidos no [OAuth 2.0 Authorization Framework.](https://tools.ietf.org/html/rfc6749)A estrutura de autorização OAuth 2.0 permite uma aplicação de terceiros (*third-party application*) obter acesso limitado a um serviço HTTP, seja em nome do proprietário de recurso (*resource owner*) por meio da orquestração de uma interação de aprovação entre o proprietário do recurso e o serviço HTTP, ou permitindo a aplicação de terceiros obter acesso em seu próprio nome.A especificação base OAuth 2.0 não fornece, por si só, informações suficientes para atender a todas as necessidades definidas pelo framework de confiança do Open Finance Basil. Mais notavelmente, não possui uma maneira de transmitir informações de identidade do cliente em um formato padronizado de uma instituição transmissora para uma receptora, e os mecanismos de autenticação que foram definidos na especificação original não são seguros o suficiente para atender aos requisitos de uma indústria altamente regulamentada.
### OpenID Connect - A Camada de Identidade para a Internet
[OpenID Connect](https://openid.net/connect/) é um conjunto de especificações simplificadas que fornecem uma estrutura para interações de identidade por meio de APIs do tipo REST. A implementação mais simples do OpenID Connect permite que *clients* de todos os tipos, incluindo baseados em navegador, celulares e *clients* javascript, solicitem e recebam informações sobre identidades e sessões atualmente autenticadas. O conjunto de especificações é extensível, permitindo que os participantes também suportem, opcionalmente, criptografia de dados de identidade, descoberta do *OpenID Provider* e gerenciamento avançado de sessão, incluindo logout***Este perfil herda todas as obrigações do OAuth 2.0***O grupo de trabalho OpenID Foundations Connect tem sido o guardião do Padrão de Identidade “de fato” da Internet por muitos anos, trabalhando em várias especificações que se baseiam no framework de autorização OAuth 2.0, adicionando recursos e requisitos de suporte para melhorar a segurança do framework em si.[Open ID Connect Core:](https://openid.net/specs/openid-connect-core-1_0.html) é um perfil do OAuth 2.0, o que significa que herda todos os requisitos e obrigações do [OAuth 2.0](https://tools.ietf.org/html/rfc6749), mas define o conceito de um `id_token` e introduz novos mecanismos de autenticação.[Open ID Connect Discovery:](https://openid.net/specs/openid-connect-discovery-1_0.html) apresenta o conceito de um documento de descoberta usado por *OpenID Connect (OIDC) Providers* para anunciar como os *clients* OAuth 2.0 podem se comunicar com eles e quais recursos e opções o *OIDC Provider* oferece suporte.[RFC7591:](https://tools.ietf.org/html/rfc7591) além de definir o processo de registro dinâmico de *clients* OAuth, esta especificação apresenta o conceito de [Software Statement](https://tools.ietf.org/html/rfc7591#section-2.3) (“Declaração de Software”), que pode ser usada para fornecer informações sobre um *client* que é atestado por um serviço de terceiros. Outros atributos de metadados também são definidos no [OpenID Connect Registration Specification](https://openid.net/specs/openid-connect-registration-1_0.html)Esta especificação define mecanismos para registrar dinamicamente *clients* OAuth 2.0 com *Authorization Servers* (servidores de autorização). Pedidos de registro enviam um conjunto de valores de metadados do *client* desejado para o *Authorization Server*. As respostas de registro resultantes retornam um *client identifier* para ser usado no *Authorization Server* e os valores de metadados registrados para o *client*. O *client* pode então usar esta informação de registro para se comunicar com o *Authorization Server* usando o protocolo OAuth 2.0. Esta especificação também define um conjunto de campos de metadados do *client* e valores para os *clients* usarem durante o registro.[RFC7592:](https://tools.ietf.org/html/rfc7592) Esta especificação define métodos de gerenciamento de *dynamic client registration* (registros de cliente dinâmico) do OAuth 2.0 para casos de uso em que as propriedades de um *client* registrado necessitam ser alteradas durante a vida do *client*.As especificações acima são especificações básicas cuja leitura obrigatória sustenta o framework de confiança do Open Finance Brasil. Entretanto, eles ainda são insuficientes para atender a todos os requisitos e princípios descritos anteriormente.
### OpenID Financial Grade 1.0: Baseline
***Este perfil herda todas as obrigações do OpenID Connect Core***Reconhecendo as ameaças e riscos restantes que não foram tratados pelo OpenID Connect Core, o grupo de trabalho Financial Grade tem como foco criar uma especificação que visa identificar e endereçar os pontos fracos na especificação OpenID Connect, essencialmente criando um perfil para casos de uso que exigem alto nível segurança.O perfil Baseline foi originalmente planejado para ser mais facilmente implementado por *clients* e *OpenID Providers* às custas de alguns elementos de segurança e, como tal, não oferece o mesmo grau de proteção contra violação de solicitação e resposta.
### OpenID Financial Grade 1.0: Avançado
***Este perfil herda todas as obrigações do OpenID FAPI 1.0: Baseline***O [FAPI 1.0: Advanced profile](https://openid.net/specs/openid-financial-api-part-2-1_0.html) é atual padrão ouro para API Security, fornecendo um **framework de especificação** que foi usado como ponto de partida para a criação de uma especificação para o Open Finance Brasil.Este padrão especifica um perfil de segurança avançado do OAuth que é adequado para ser usado na proteção de APIs com alto risco inerente. Os exemplos incluem APIs que dão acesso a dados altamente confidenciais ou que podem ser usados para acionar transações financeiras (por exemplo, início de pagamento). Este padrão especifica os controles contra ataques, como: violação de solicitação de autorização, violação de resposta de autorização, incluindo injeção de código, injeção de estado e phishing de solicitação de token.
## Sobre o uso de JARM
O suporte ao [JARM](https://openbanking-brasil.github.io/specs-seguranca/%3Chttps://bitbucket.org/openid/fapi/src/master/Financial_API_JWT_Secured_Authorization_Response_Mode.md) é opcional aos transmissores e detentores de contas (ASPSP) e, portanto, as instituições que optarem pelo uso do JARM devem, no processo de certificação de segurança, atestar também o suporte a outro profile que não considere o uso do padrão JARM, ou seja, deve também se certificar com um dos profiles listados na tabela a seguir.
| Perfil da certificação OIDF |
| --- |
| BR-OB Adv. OP w/ MTLS |
| BR-OB Adv. OP w/ Private Key |
| BR-OB Adv. OP w/ MTLS, PAR |
| BR-OB Adv. OP w/ Private Key, PAR |

## Camadas de Segurança Básicas

| Camada | Descrição | Explicação |
| --- | --- | --- |
| Física | Firewall | Equipamentos e produtos como filtros, proxys e firewalls direcionados ao controle e segurança da rede física. |
| Transporte | HTTP - TLS 1.2 | Protocolo de criptografia que fornece segurança na comunicação sobre a rede física. |
| Gestão | API Gateway / Manager | Gateway e Manager para gerenciar a publicação da API com controles de throttling , quotas e outros. |