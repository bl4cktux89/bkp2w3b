**História**

Olá, bem-vindos à quinta aula! Nesta aula, vamos compreender a estrutura da arquitetura SNMP.

O SNMP (Simple Network Management Protocol ou Protocolo Simples para Gerenciamento de Rede) foi criado para servir de ferramenta de gerenciamento para redes, independente do modelo de rede, RM–OSI, Arquitetura TCP/IP, Modelo Internet, ATM ou qualquer outro modelo, desde que opere a estrutura de protocolos da arquitetura TCP/IP. Desde a **Arpanet** se transformar no que conhecemos hoje como **internet**, a rede mundial, com diversos backbones e operadores, houve a necessidade de criar ferramentas capazes de monitorar e controlar a rede mundial.

Em maio de 1990, surge um documento de regras para tratar informações de gerenciamento publicada na RFC 1155 e, com esta publicação, aparece a primeira versão do SNMP (SNMPv1) publicada através da RFC 1157. Nesta primeira versão, o SNMP oferecia uma forma sistemática de monitorar e gerenciar redes de modo que essa estrutura e seu protocolo foi implementado em diversos sistemas comerciais, tornando-se o padrão de gerenciamento utilizado em redes computacionais.

Acompanhando o crescimento das redes computacionais novos serviços de rede surgiram e com a integração dessas redes à internet as limitações e deficiências do SNMPv1 tornam-se evidentes e uma nova versão aprimorada deste protocolo é disponibilizada. Definida nas RFCs 1441 e 1452, surge o SNMPv2 que se torna o padrão utilizado não só em ambientes computacionais como também torna-se o padrão para gerenciamento da estrutura internet.

A partir do momento em que a internet torna-se global no fim da década de 1990, o compartilhamento de informações de forma ágil torna-se um problema porque falta integridade e segurança. Pensando a respeito da segurança, tanto a versão 1 como a versão 2 do SNMP possuíam inúmeras deficiências. Para corrigi-las é lançada a versão 3 do SNMP (SNMPv3) como um conjunto de padrões propostos, publicadas através das RFCs 3410 a 3415 em janeiro de 1998.

**Modelo SNMP**

O modelo consiste em quatro componentes, que são:

- Nós gerenciados: equipamentos ativos de rede como computadores, roteadores, switches, bridges, impressoras, PBX/PABX ou qualquer outro equipamento eletrônico capaz de armazenar/enviar informações de status para a estação de gerenciamento. Os nós gerenciados também são conhecidos como **agente SNMP** ou simplesmente **agente**. Todo agente, para que possa ser gerenciado dentro dessa estrutura, deve ser capaz de executar um processo de gerenciamento SNMP.
- Estação de gerenciamento: são equipamentos, normalmente computadores ou microcomputadores, que executam um software especial chamado de software de gerenciamento. Essas estações contêm um ou mais processos que são utilizados para se comunicar com os agentes, sendo essa comunicação feita por meio de comandos e obtendo respostas. Para que uma estação se comunique com os diversos equipamentos, a natureza das informações mantidas por eles devem ser rigidamente especificadas de modo que essas informações sejam exatas e que contenham um formato específico.
- Informações de gerenciamento: as informações devem seguir uma estrutura chamada de SMI (_Structure of Management Information_) ou Estrutura de Informação de Gerenciamento e cada item dessa estrutura é conhecida como objeto. O conjunto de objetos em uma estrutura de dados é chamado de MIB (_Management Information Base_ ou Base de Informação de Gerenciamento).
- Protocolo de gerenciamento: consiste em um conjunto de regras que especifica como o gerente se comunicará com o agente, bem como o que o gerente coletará do agente.