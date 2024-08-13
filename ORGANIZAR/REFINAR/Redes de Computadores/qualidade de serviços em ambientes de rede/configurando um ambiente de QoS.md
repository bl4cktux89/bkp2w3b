**Uma breve explanação sobre o ambiente QoS**

Nesta aula, você aprenderá como configurar e aplicar uma qualidade de serviço (QoS) em um roteador Cisco com tráfego, utilizando protocolo EIGRP.

Aqui, QoS refere-se a uma extensa coleção de técnicas e tecnologias de internetworking. A função do QoS é prover garantias e habilidades para que a rede consiga entregar os pacotes satisfatoriamente. Elementos de performance de rede juntamente ao QoS incluem tempos de acesso, largura de banda, atrasos e gerência de erros, tudo a fim de proporcionar, de fato, um serviço de qualidade.

QoS envolve priorização de tráfego na rede, pode ser demarcado em uma interface de rede, um servidor ou roteador. É especialmente importante para novas aplicações no ambiente de internet, como VoIP (visto na aula anterior), vídeo sob demandas e outros serviços. Algumas tecnologias intermediárias, como tecnologias Ethernet, não foram desenhados para suportar priorização de tráfego ou garantia de nível de performance, tornando, assim, a implementação de QoS para esses casos muito mais difícil do que no ambiente de internet.

Para configurar um ambiente QoS, é preciso entender, primeiramente, as correlações dos comandos MQC (Modular QoS CLI), ou seja, é a interface em que serão digitados os comandos QoS. Observe a figura a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119277/a15i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119277/a15i01_quasar80_100.jpg)

Figura 1: Comandos MQC e suas relações.Fonte: ODOM; CAVANAUGH (2012).

Um outro ponto fundamental também é você conseguir planejar e identificar as reais necessidades de implementação de políticas QoS. Para isso, três passos são sugeridos:

1. Identificar o tráfego e suas necessidades.
2. Dividir o tráfego em classes.
3. Definir a política QoS para cada classe.

**Inserindo os comandos no Packet Tracer**

Observe na Figura 2 o cenário que deve ser construído no Packet Tracer. O modelo do roteador a ser utilizado é o 1810. Não se esqueça que é necessário adicionar um módulo WIC-2T (duas portas seriais em cada roteador). O cabo serial é o tipo DTE.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119279/a15i02_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/2/119279/a15i02_quasar80_100.jpg)

Cenário a ser construído no packet tracer.Fonte: Autoria própria fazendo uso da ferramenta Packet Tracer.

Na interface "CLI" (ao dar um duplo clique no roteador com o nome "QoS_Router"), deve-se digitar a seguinte sequência de comandos:

```Shell
-->Bloco de divisão do tráfego em classes
Router>enRouter\#conf t
Router(config)\#hostname QoS_Router
QoS_Router(config)\#ip ssh version 1
QoS_Router(config)\#spanning-tree mode pvst
QoS_Router(config)\#class-map match-all critical
QoS_Router(config-cmap)\#match protocol eigrp
QoS_Router(config-cmap)\#exit
QoS_Router(config)\#class-map match-any interactive
QoS_Router(config-cmap)\#match protocol telnet
QoS_Router(config-cmap)\#match protocol ssh
QoS_Router(config-cmap)\#exit
QoS_Router(config)\#class-map match-any web
QoS_Router(config-cmap)\#match protocol http
QoS_Router(config-cmap)\#exit 
-->Bloco de definição da política para cada classe
QoS_Router(config)\#policy-map markingpolicy
QoS_Router(config-pmap)\#class critical
QoS_Router(config-pmap-c)\#set precedence 7
QoS_Router(config-pmap-c)\#exit
QoS_Router(config-pmap)\#class interactive
QoS_Router(config-pmap-c)\#set precedence 5
QoS_Router(config-pmap-c)\#exit
QoS_Router(config-pmap)\#class web
QoS_Router(config-pmap-c)\#set precedence 3
QoS_Router(config-pmap-c)\#exit
QoS_Router(config-pmap)\#exit 
-->Bloco de definição das interfaces
QoS_Router(config)\#interface loopback0
QoS_Router(config-if)\#ip add 10.0.0.1 255.255.255.255
QoS_Router(config-if)\#exit
QoS_Router(config)\#interface fastEthernet 0/0
QoS_Router(config-if)\#ip add 10.1.1.1 255.255.255.0
QoS_Router(config-if)\#duplex auto 
QoS_Router(config-if)\#speed auto 
QoS_Router(config-if)\#no shutdown
QoS_Router(config-if)\#exit
QoS_Router(config)\#interface serial 0/0/0
QoS_Router(config-if)\#ip add 172.16.12.1 255.255.255.0
QoS_Router(config-if)\#tx-ring-limit 1
QoS_Router(config-if)\#service-policy output markingpolicy
QoS_Router(config-if)\#hold-queue 1 out
QoS_Router(config-if)\#no shutdown
QoS_Router(config-if)\#exit
QoS_Router(config)\#router eigrp 1
QoS_Router(config-router)\#network 172.16.0.0
QoS_Router(config-router)\#network 10.0.0.0
QoS_Router(config-router)\#no auto-summary 
QoS_Router(config-router)\#exit
QoS_Router(config)\#exit
QoS_Router#
QoS_Router\#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...[OK]
```

Caro aluno, analise cuidadosamente essa sequência de comandos. Tente interpretar, de acordo com o exposto na Figura 1, ou seja, tente identificar em quais momentos você definiu a classe do mapeamento (classificação), a configuração da ação (as políticas) e o momento da configuração da interface.

Agora, vamos configurar o roteador com o nome "R2". Identicamente ao roteador anterior, dá-se um duplo clique no roteador, direciona-se para a aba "CLI" e digita-se a seguinte sequência de comandos:

```Shell

Router>en
Router\#conf t
Router(config)\#hostname R2
R2(config)\#ip ssh version 1
R2(config)\#spanning-tree mode pvst
R2(config)\#interface loopback0
R2(config-if)\#ip add 10.0.0.2 255.255.255.255
R2(config-if)\#exit
R2(config)\#interface serial 0/0/0
R2(config-if)\#ip add 172.16.2.2 255.255.255.0
R2(config-if)\#clock rate 800000
R2(config-if)\#no shutdown
R2(config-if)\#exit
R2(config)\#interface serial 0/0/1
R2(config-if)\#ip add 172.16.23.2 255.255.255.0
R2(config-if)\#no shutdown
R2(config-if)\#exit
R2(config)\#router eigrp 1
R2(config-router)\#network 172.16.0.0
R2(config-router)\#no auto-summary
R2(config-router)\#exit
R2(config)\#exit
R2#
```

Agora falta pouco. Vamos configurar o roteador R3. Clique nele para abrir a tela de configuração e depois vamos para a aba "CLI" para digitar a seguinte sequência de comandos:

```Shell

Router>en
Router\#conf t
Router(config)\#hostname R3
R3(config)\#ip ssh version 1
R3(config)\#spanning-tree mode pvst
R3(config)\#interface loopback0
R3(config-if)\#ip add 10.0.0.3 255.255.255.255
R3(config-if)\#exit
R3(config)\#interface serial 0/0/1
R3(config-if)\#ip add 172.16.23.3 255.255.255.0
R3(config-if)\#no shutdown
R3(config)\#router eigrp 1
R3(config-router)\#network 172.16.0.0
R3(config-router)\#no auto-summary
R3(config-router)\#exit
R3(config)\#exit
R3#
```

**Considerações finais**

Você configurou essa rede com as seguintes características: o roteador "QoS_Router" foi configurado para usar QoS para marcar o serviço de roteamento EIGRP e os tráfegos telnet, SSH e HTTP que existem na interface serial 0/0/0. A configuração do "policy-map" foi feita com IP precedence nos campos para: 7 (pacotes críticos EIGRP), 5 para pacotes "interactive" (telnet e SSH) e 3 para tráfego web (HTTP). Todos os outros tipos de tráfego foram marcados como grupo padrão.