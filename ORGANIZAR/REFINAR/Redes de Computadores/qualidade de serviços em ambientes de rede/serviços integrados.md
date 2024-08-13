**Serviços Integrados – IntServ**

Entre 1995 e 1997, a IETF dedicou um grande esforço à criação de uma arquitetura para multimídia de fluxo. Esse trabalho resultou em mais de duas dezenas de RFCs, começando com as RFCs 2205 a 2210.

A proposta do serviço integrado (IntServ) é estender a atual arquitetura internet (baseado no melhor esforço – Best Effort) para que seus recursos sejam alocados (reservados) para cada fluxo de dados. Dessa forma, todos os pacotes pertencentes àquele determinado fluxo usarão os recursos previamente alocados.

Os recursos são reservados em todos os roteadores intermediários e no nó de destino usando protocolos de sinalização (controle). Recursos que foram reservados devem ser atribuídos aos pacotes do seu respectivo fluxo. As características de tráfego negociadas no momento em que os recursos foram alocados devem ser monitoradas, para que seja verificado que as premissas assumidas quanto às características do tráfego foram respeitadas durante o período de execução.

_**Resource reSerVation Protocol**_ **– RSVP**

Trata de uma implementação da arquitetura IntServ e foi desenvolvido com um protocolo de sinalização para reserva de banda. O RSVP estende o protocolo IP de tal forma que os dados são transmitidos sem nenhuma modificação. O protocolo troca sinais de controle (sinalização), descrevendo a qualidade de serviço por meio de um fluxo de dados. O protocolo é orientado ao nó de destino do fluxo, pois é sua função gerar as mensagens contendo os parâmetros de qualidade de serviços a serem alocados.

Propostas de implementação de arquiteturas IntServ são criticadas basicamente por sua limitada aplicação em uma rede IP com vários nós, pois os recursos são alocados para cada fluxo de dados. A implementação de IntServ em uma rede grande, como a internet, com milhões de usuários e com vários fluxos por usuário, implica complexos roteadores com considerável poder de processamento e memória. Cada nó possui um estado para cada fluxo, aumentando a complexidade do sistema. O poder de processamento se fará necessário, pois a tarefa de escalonamento dos pacotes para cada fluxo é complexa e fundamental para a garantia da qualidade de serviço acordada. A outra desvantagem é a perda de padrões para bilhetagem e tarifação, fazendo RSVP e IntServ recomendados apenas para redes pequenas.

**O funcionamento do RSVP**

RSVP utiliza um fluxo de dados simples, isto é, ele solicita recursos somente em uma direção. Por isso, RSVP trata um _**"sender"**_ logicamente diferente de um _**"receiver"**_. RSVP opera no topo do IP (tanto o IPv4 como o IPv6), ocupando o lugar de um protocolo de transporte no _**"protocol stack"**_. Por mais que pareça, RSVP não transporta dados, mas é um _**"Internet control protocol"**_ (protocolo internet de controle), como são o ICMP, IGMP, ou outros protocolos de roteamento. Assim, como a implementação de protocolos de roteamento e de controle, a implementação do RSVP irá tipicamente executar em background.

RSVP não é por si só um protocolo de roteamento; RSVP foi feito para operar com os protocolos de roteamento atuais ou futuros, unicast e muiticast. Um RSVP _**"daemon"**_ consiste de um banco de dados local de rotas para obter rotas. No caso de multicast, por exemplo, um host envia mensagens IGMP para se juntar a um grupo multicast e, então, envia mensagens RSVP para reservar os recursos ao longo do caminho de entrega do grupo. Protocolos de roteamento determinam por onde os pacotes serão enviados; RSVP se concentra apenas na QoS desses pacotes que serão enviados em concordância com os roteadores.

Para acomodar eficientemente grandes grupos, as alterações dinâmicas que esses grupos sofrem, e os requerimentos heterogênios dos _**"receivers"**_, RSVP faz os _**"receivers"**_ responsáveis pela requisição do controle da QoS. O controle da QoS requisitado por um uma aplicação "receiver" host é passada para a implementação local do RSVP.

**RSVP X QoS – decisões**

RSVP interage com as entidades chamadas _**packet classifier e packet scheduler**_, que estão instaladas no host para realizar as decisões a respeito da qualidade dos serviços que estão sendo enviados pelas aplicações. Primeiramente ele pergunta aos módulos locais de decisão para encontrar qual o tipo de QoS que deve ser desenvolvido (isto envolve decisões a respeito de quanto de recurso pode ser gasto e decisões a respeito de controle de policiamento). Após essas considerações, são então atualizados os parâmetros especificados no packet classifier e no packet scheduler. O packet classifier determina a rota que o pacote fará, e o scheduler tentará obter a QoS desejada. No caso da camada de link que se encontra no host ter seu próprio gerenciamento de capacidade de QoS, o packet scheduler negociará com a camada de link para obter a QoS requisitada pelo RSVP. Em outros casos, por exemplo, quando o host está usando um procedimento de concessão, o scheduler por si só aloca a capacidade de transmissão de pacotes. Ele pode também alocar outros recursos do sistema como tempo de processador, buffers etc.

> [!important]  
> Um artigo que recomendamos a leitura, na íntegra, é o descrito por Aluizio Nascimento dos Santos, que explica em maiores detalhes o funcionamento do RSVP. Esse artigo está disponível em: https://www.gta.ufrj.br/grad/09_1/versao-final/mpls/RSVP.html