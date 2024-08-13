**Introdução**

Olá, bem-vindo à 19ª aula!

A seguir falaremos um pouco da história do IPv6.

**História**

O IPv6, ou Internet Protocol versão 6, foi desenvolvido com o intuito de suprir alguns pontos problemáticos do IPv4 como segurança e qualidade de serviço como também pela falta de disponibilidade de endereços IPv4. O principal órgão que cuida dos IPv4 anunciou em abril de 2011 que os endereços IPv4 acabaram. No Brasil, a previsão para término dos endereços é agosto de 2013 conforme o CGIBR (Comitê Gestor de Internet no Brasil).

O IPv6 foi originado a partir de um protocolo chamado de IPng (Internet Protocol next Gereneration), codinome dado pelo IETF a partir da RFC1550 para desenvolver pesquisas para um novo protocolo IP. Nesta pesquisa, as principais questões abordadas eram: estabilidade, segurança, configuração e administração de rede; suporte a QoS, mobilidade, políticas de roteamento, transição. A partir de então, diversos projetos apareceram para estudar os efeitos do crescimento da Internet.

Os principais são: o CNAT, o IP Encaps, o Nimrod e o Simple CLNP. Destas propostas, surgiram o TUBA (TCP and UDP with Bigger Addresses) — uma evolução do Simple CLNP — e o IPAE (IP Address Encapsulation) — uma evolução do IP Encaps. Após estes outros projetos, foram apresentados: o PIP (Paul?s Internet Protocol), o SIP (Simple Internet Protocol) e o TP/IX. Depois, uma nova versão do SIP englobando funcionalidades do IPAE foi apresentada, pouco antes de agregar-se ao PIP, resultando no SIPP (Simple Internet Protocol Plus). Neste mesmo tempo, o TP/IX teve seu nome alterado para CATNIP (Common Architecture for the Internet).

Na RFC 1752, editada em janeiro de 1995, o IETF apresentou um resumo das três principais propostas:

- **CATNIP**: criado para permitir que qualquer protocolo da camada de transporte pudesse ser executado por qualquer protocolo da camada de rede estabelecendo interoperabilidade entre TCP/IP, OSI e Novell.
- **TUBA**: buscava a não alteração dos protocolos da camada de transporte e aplicação migrando toda a estrutura sem encapsular ou traduzir pacotes ou endereços aumentando o espaço de endereços IPv4 e tornando-o mais hierárquico.
- **SIPP**: buscava a convivência com o IPv4 sem mudanças drásticas, apenas aumentando o espaço de endereçamento de 32 bits para 64 bits. Dessa forma, permitia novas funcionalidades como também permitia uma maior hierarquia na estrutura de endereçamento graças à extensão do cabeçalho e um campo adicional chamado de _flow_.

Apesar de serem as principais propostas, todas as três tinham problemas significativos, assim sendo, uma nova recomendação foi criada a partir do SIPP e do TUBA. O novo protocolo internet incorpora endereços de 128 bits em vez de 64 bits do SIPP e junta elementos de transição e autoconfiguração (NDP — Network Discovery Protocol) do TUBA, além de CIDR e cabeçalhos de extensão.

Após esta definição, a nova versão do protocolo internet passou a ser chamado **oficialmente de IPv6**.

As especificações da IPv6 foram apresentadas inicialmente na RFC 1883 de dezembro de 1995 e, em dezembro de 1998, esta RFC foi substituída pela RFC 2460. Como principais mudanças em relação ao IPv4, destacam-se:

- **Maior capacidade para endereçamento**: 128 bits no total contra 32 bits do IPv4. Definições de endereços multcast para roteamento e adição de um novo tipo de endereço, o ANYCAST.
- **Simplificação do formato do cabeçalho**: há menos campos que no IPv4, como também houve mudanças em alguns campos.
- **Suporte a cabeçalhos de extensão**: o campo "opções" foi removido, permitindo assim um roteamento mais eficiente.
- **Capacidade de identificar fluxos de dados**: foi definido um recurso permitindo identificar a qual fluxo de dados determinado pacote pertence.
- **Suporte a autenticação e privacidade**: foram especificados cabeçalhos de extensão capazes de fornecer mecanismos de validação e garantir a integridade e a confidencialidade dos dados transmitidos.