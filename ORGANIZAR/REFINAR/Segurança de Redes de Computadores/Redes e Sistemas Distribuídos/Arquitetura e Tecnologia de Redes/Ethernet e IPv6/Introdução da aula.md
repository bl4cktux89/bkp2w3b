[![](https://ampli-images.s3.amazonaws.com/production/c603dc44-4d14-4fe1-affd-4e200fe31c5a/original)](https://ampli-images.s3.amazonaws.com/production/c603dc44-4d14-4fe1-affd-4e200fe31c5a/original)

### **Qual é o foco da aula?**

Nesta aula, serão tratadas informações a respeito do padrão Ethernet, utilizado nas redes locais com grande intensidade, e sobre o protocolo IPv6, o qual, em conjunto com o IPv4, suportam o endereçamento e o roteamento das redes atuais. Considerando o padrão Ethernet, abordaremos também questões de cabeamento de redes.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- identificar o conceito do padrão Ethernet;
- examinar a estrutura do IPV6;
- analisar as diferenças entre IPV4 e IPV6.

**Introdução da aula**

As tecnologias de comunicação da camada de host de rede do conjunto de protocolos TCP/IP (_Transmission Control Protocol/Internet Protocol_) utilizam o padrão Ethernet para redes cabeadas na maioria dos sistemas de redes locais. Este padrão acompanha o cenário das redes locais desde a década de 1970 e vem sendo modificado, considerando novas tecnologias de materiais para cabeamento, porém ainda mantém a sua essência para transmissão e controle da onda portadora no canal de comunicação.

Já o protocolo IPv6 deverá se tornar o padrão de endereçamento para redes na internet, considerando que o IPv4 possui limitações de volume de endereços disponíveis, mesmo considerando as técnicas de NAT (_Network Address Translator_) e o CDIR (_Classless Inter-Domain Routing_), que levam ao endereçamento alternativo e suportam a imensidão de dispositivos parametrizados dentro de redes locais de computadores.

Após finalizarmos os estudos do projeto de topologia, protocolos de rede, segmentação para a divisão da rede em sub-redes e definição de endereçamento IP mediante uma política estabelecida com endereços e máscaras de sub-rede no projeto de redes para o espaço de coworking, daremos sequência ao estudo de redes.

Convidamos você a estudar estes dois conceitos e dar seguimento ao projeto de redes na empresa de coworking através de uma nova etapa do projeto para implantação de estrutura de cabeamento e dispositivos na rede local com a utilização do protocolo IEEE 802, ou seja, o padrão Ethernet, o que reflete a instalação física de dispositivos e a definição de domínios de colisão e _broadcast_.

Para que a empresa de coworking, para a qual sua consultoria de rede está desempenhando uma consultoria de projeto de redes, tenha documentado toda a estrutura física implantada, é necessário um relatório apresentando os equipamentos, cabos e domínios de colisão e _broadcast_ que serão utilizados para operacionalizar a rede implantada.

A compreensão sobre domínios de colisão e _broadcast_ em uma rede Ethernet, a definição de equipamentos físicos e a definição de um novo padrão de endereçamento IPv6 devem melhorar ainda mais o projeto de rede que está em planejamento e seu desempenho.

Em uma nova fase da consultoria para implantação de um sistema de redes de computadores em uma empresa de espaços compartilhados para trabalho (coworking), houve uma nova solicitação para que a equipe de desenvolvimento do projeto pudesse apresentar informações mais detalhadas sobre os dispositivos que fazem parte da rede, a fim de identificar os equipamentos disponíveis em cada um dos setores do ambiente (Sistemas, Gerência, Clientes1, Reuniões, Clientes2, Visitantes), conforme relatado na figura abaixo, e também possam ser descritos os domínios de colisão e de _broadcast_ da rede.

Esta análise fará com que a rede tenha uma documentação mais completa e deverá definir os domínios da topologia implementada via padrão Ethernet, ou seja, para a parte da rede cabeada.

A análise a ser realizada deverá levar em consideração a segmentação da rede com os dispositivos comutadores, que tem a capacidade de definir domínios de colisão e _broadcast_. O relatório deve apresentar os equipamentos da rede, o número de domínios de colisão e o número de domínios de _broadcast_, de acordo com a topologia proposta a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/18378617-50db-47f6-8c6a-853fa4ab8ea3/original)](https://ampli-images.s3.amazonaws.com/production/18378617-50db-47f6-8c6a-853fa4ab8ea3/original)

Topologia de rede para análise dos domínios de colisão e broadcast. Fonte: elaborada pelo autor.

Deverá ser gerado o **Relatório do projeto de redes: equipamentos de rede e análise de domínios de colisão e** _**broadcast**_.

Reconhecer como são realizadas as operações de acesso ao meio (cabos) e dispositivos de rede no padrão Ethernet é importante para que se possa desenvolver uma rede de computadores com os dispositivos de repetição e gerenciamento de rede dentro de domínios de colisão e broadcast adequados. O endereçamento dentro do padrão IPv6 também contribui para o adequado controle de endereçamento e performance da rede.

As redes locais formam as estruturas chamadas de _Local Area Network_ (LAN), que configuram os ambientes operacionais onde se localizam a maioria dos dispositivos conectados indiretamente à internet.

Em sua essência, a internet é descrita por Kurose e Ross (2013) como uma infraestrutura de redes que fornece serviços para aplicações distribuídas, interconectando centenas de milhões de dispositivos de computação ao redor do mundo. Estas aplicações distribuídas são operacionalizadas dentro de dispositivos dentro de redes local.

A seguir, conheceremos o padrão Ethernet como tecnologia utilizada na interconexão de redes locais, relacionada aos padrões e protocolos definidos na camada de host de rede da arquitetura TCP/IP. Se olharmos para o modelo OSI, estes protocolos atuam na camada de enlace de dados, que define e controla os dados transmitidos via dispositivos da camada física da rede.