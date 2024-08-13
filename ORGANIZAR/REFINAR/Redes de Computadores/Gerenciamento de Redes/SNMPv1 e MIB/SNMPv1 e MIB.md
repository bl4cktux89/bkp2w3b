**SNMPv1**

Como vimos na aula anterior, o SNMPv1 está definida sobre as RFCs 1155 e 1157, dessa forma, o modelo de gerenciamento SNMP inclui agente, gerente, MIB e protocolo de gerenciamento. Trataremos, agora, mais especificamente, do protocolo SNMPv1. Ele possui as seguintes capacidades:

- GET: permite que o gerente recupere valores dos objetos no agente, ou seja, busque as informações armazenadas nas MIBs dos agentes.
- SET: permite que o gerente defina o valor dos objetos no agente, ou seja, o gerente pode alterar algum objeto ou informação no agente caso seja necessário.
- NOTIFY: permite que um agente envie notificações não solicitadas aos outros gerentes (quando a estrutura é formada por mais de um gerente) sobre eventos importantes.

**Observação:** Todas as versões do protocolo SNMP possuem essas capacidades.

![[Untitled 2.png|Untitled 2.png]]

  

Tais capacidades permitem a comunicação entre gerentes e agentes, seja numa rede centralizada ou distribuída. A ideia deste protocolo é facilitar a coleta de dados permitir que se efetue uma gerência centralizada ou descentralizada, ou seja, com múltiplos gerentes e, além disso, ele possui uma estrutura simples em sua hierarquia de códigos. Esses códigos, ou tipos de dados, são chamados de ASN (_**Abstract Sintaxe Notation**_) e, apesar de parecerem simples, são complexos e não tão eficientes. Em sua atualização (para _**SNMPv2**_), além dos códigos _**ASN**_, novos tipos de dados foram implementados, denominando essa nova estrutura de _**SMI**_ (_**Structure of Management Information**_), que estudaremos em aulas adiante.

Para gerenciar os recursos na rede, cada recurso é representado como um objeto chamado de **OID** (Object IDentifier – identificador de objeto), que possui um código ASN específico e é uma variável de dados que apresenta um aspecto do agente. A coleção de OIDs é chamada de MIB (Management Information Base, ou Base de informações de gerenciamento). Assim, o protocolo SNMP, através de suas capacidades, permite que um gerente realize ações com a MIB, ora recuperando informações, ora mudando o valor de alguma variável específica.

**A MIB**

É dividida em grupos e cada um deles possui um número de objetos que totalizam 175 (na MIB-II). Esses objetos também são chamados OID e são agrupados em 10 categorias divididas da seguinte forma:

- **System:** Refere-se a nome, local e descrição do equipamento. Contém 7 objetos.
- **Interfaces:** Refere-se às interfaces de rede e seu tráfego. Contém 23 objetos.
- **AT:** Refere-se à conversão de endereços na MIB-I, já na MIB-II essas informações foram deslocadas para protocolos específicos com o SNMPv2. Contém 3 objetos.
- **ICMP:** Refere-se às estatísticas sobre mensagens ICMP recebidas. Contém 26 objetos.
- **TCP:** Refere-se aos algoritmos TCP, parâmetros e estatísticas. Contém 19 objetos.
- **UDP:** Refere-se às estatísticas de tráfego UDP. Contém 6 objetos.
- **EGP:** Refere-se às estatísticas de tráfego de protocolos de gateway externo ou protocolos de roteamento externo. Contém 20 objetos.
- **Transmission:** Refere-se a MIBs de meios físicos específicos, como estatísticas específicas relacionadas à ethernet. Contém 0 (zero) objetos: é um grupo vazio.
- **SNMP:** Refere-se a estatísticas de tráfego SNMP. Contém 29 objetos.

> Cada um dos OIDs possui um tipo de dado específico e está descrito na RFC 1213, que está disponível em: <[**http://www.ietf.org/rfc/rfc1213.txt**](http://www.ietf.org/rfc/rfc1213.txt)>.