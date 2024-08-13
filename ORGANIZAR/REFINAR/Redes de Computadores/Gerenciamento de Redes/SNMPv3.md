### Introdução

Olá! Seja bem-vindo à décima primeira aula! Nela, vamos falar sobre as mudanças ocorridas no protocolo SNMP apresentando sua última versão: o SNMPv3, lançada em janeiro de 1998 e atualizada em 2002 sobre as RFCs de 3410 a 3415.

### SNMPv3

Essencialmente, esta versão surgiu para corrigir falhas de segurança contidas desde a primeira versão. Ela oferece três serviços, divididos em duas categorias: autenticação e privacidade da categoria USM (User-based Security Model, ou Modelo de segurança baseada em usuário) e controle de acesso da categoria VACM (View-based Access Control Model, ou Modelo de controle de acesso).

O mecanismo de autenticação USM garante que uma mensagem recebida foi transmitida por uma identidade. Uma identidade pode ser um indivíduo, uma aplicação ou o conjunto de indivíduos ou de aplicações. Esse mecanismo também garante que a mensagem transmitida não foi deliberadamente alterada, retardada ou repetida. Dessa forma, o emissor fornece uma autenticação que inclui um código na mensagem SNMP, conhecido como HMAC (HASH-Based Message Authentication Code, ou Código de autenticação de mensagem HASH), que é uma função do conteúdo da mensagem, do tempo de transmissão, da identidade emissora e receptora e da chave que deve ser conhecida pelo emissor e receptor. A chave deve ser configurada e distribuída fora da USM e devem estar carregadas nas MIBs.

O serviço de privacidade USM permite que tanto gerente quanto agente criptografem as mensagens. O algoritmo utilizado para cifrar as mensagens SNMP é o DES (Data Encryption Standard).

O serviço de controle de acesso permite configurar níveis diferentes de acesso às MIBs dos agentes para que se possa restringir parte ou o todo da informação.