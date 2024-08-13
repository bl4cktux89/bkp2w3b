**Inserindo os comandos no Packet Tracer**

Observe na figura 1 abaixo o cenário que deve ser construído no packet tracer. O modelo do roteador a ser utilizado é o 1810. Não se esqueça de que é necessário adicionar um módulo WIC-2T (duas portas seriais em cada roteador).

O cabo serial é o tipo DTE. Insira um switch 2950-24.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/3/119309/a20i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/3/119309/a20i01_quasar80_100.jpg)

Fonte: Desenho construído na ferramenta packet tracer pelo professor.

Para os PC's siga as seguintes configurações recomendadas:

```Shell

1. PC0 --> IP 10.1.1.2. Máscara: 255.0.0.0. Gateway: 10.1.1.1
2. PC1 --> IP 10.1.1.3. Máscara: 255.0.0.0. Gateway: 10.1.1.1
3. PC2 --> IP 10.1.1.4. Máscara: 255.0.0.0. Gateway: 10.1.1.1
```

Na interface "CLI" (ao dar um duplo clique no roteador com o nome "QoS_Router"), digite a seguinte sequência de comandos:

```Shell
->Bloco de divisão do tráfego em classes
Router>enRouter\#conf t
Router(config)\#hostname 
QoS_Router
QoS_Router(config)\#ip ssh version 1
QoS_Router(config)\#spanning-tree mode pvst
QoS_Router(config)\#class-map match-all geral
QoS_Router(config-cmap)\#match protocol eigrp
QoS_Router(config-cmap)\#exit
QoS_Router(config)\#class-map match-any participativo
QoS_Router(config-cmap)\#match protocol telnet
QoS_Router(config-cmap)\#match protocol ssh
QoS_Router(config-cmap)\#exit
QoS_Router(config)\#class-map match-any web
QoS_Router(config-cmap)\#match protocol http
QoS_Router(config-cmap)\#exit 
->Bloco de definição da política para cada classe
QoS_Router(config)\#policy-map markingpolicy
QoS_Router(config-pmap)\#class geral
QoS_Router(config-pmap-c)\#set precedence 7
QoS_Router(config-pmap-c)\#exit
QoS_Router(config-pmap)\#class participativo
QoS_Router(config-pmap-c)\#set precedence 5
QoS_Router(config-pmap-c)\#exit
QoS_Router(config-pmap)\#class web
QoS_Router(config-pmap-c)\#set precedence 3
QoS_Router(config-pmap-c)\#exit
QoS_Router(config-pmap)\#exit 
->Bloco de definição das interfaces
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

Caro aluno, analise cuidadosamente a sequência de comandos acima. Tente interpretar de acordo com o exposto na figura 1, ou seja, tente identificar em que momento você definiu a classe do mapeamento (classificação), a configuração da ação (as políticas) e o momento da configuração da interface.

Agora, vamos configurar o roteador com o nome "R2". Identicamente ao roteador anterior, dê um duplo clique no roteador, direcione para a aba "CLI" e digite a seguinte sequência de comandos a seguir:

```Shell

1. Router>en
2. Router\#conf t
3. Router(config)\#hostname R2
4. R2(config)\#ip ssh version 1
5. R2(config)\#spanning-tree mode pvst
6. R2(config)\#interface loopback0
7. R2(config-if)\#ip add 10.0.0.2 255.255.255.255
8. R2(config-if)\#exit
9. R2(config)\#interface serial 0/0/0
10. R2(config-if)\#ip add 172.16.2.2 255.255.255.0
11. R2(config-if)\#clock rate 800000
12. R2(config-if)\#no shutdown
13. R2(config-if)\#exit
14. R2(config)\#interface serial 0/0/1
15. R2(config-if)\#ip add 172.16.23.2 255.255.255.0
16. R2(config-if)\#no shutdown
17. R2(config-if)\#exit
18. R2(config)\#router eigrp 1
19. R2(config-router)\#network 172.16.0.0
20. R2(config-router)\#no auto-summary 
21. R2(config-router)\#exit
22. R2(config)\#exit
23. R2#
```

Agora falta pouco. Vamos configurar o roteador R3. Dê um clique nele para abrir a tela de configuração, vá para a aba "CLI" para digitar a seguinte sequência de comandos:

```Shell

1. Router>en
2. Router\#conf t
3. Router(config)\#hostname R3
4. R3(config)\#ip ssh  version 1
5. R3(config)\#spanning-tree mode pvst
6. R3(config)\#interface loopback0
7. R3(config-if)\#ip add 10.0.0.3 255.255.255.255
8. R3(config-if)\#exit
9. R3(config)\#interface serial 0/0/1
10. R3(config-if)\#ip add 172.16.23.3 255.255.255.0
11. R3(config-if)\#no shutdown
12. R3(config)\#router eigrp 1
13. R3(config-router)\#network 172.16.0.0
14. R3(config-router)\#no auto-summary
15. R3(config-router)\#exit
16. R3(config)\#exit
17. R3#
```

**Considerações finais**

Você configurou essa rede com as seguintes características: o roteador "QoS_Router" foi configurado para usar QoS, a fim de marcar o serviço de roteamento EIGRP e os tráfegos telnet, SSH e HTTP, que existem na interface serial 0/0/0. A configuração do "policy-map" foi feita com IP precedence nos campos para 7 (pacotes críticos EIGRP), 5 para pacotes "interactive" (telnet e SSH) e 3 para tráfego web (HTTP). Todos os outros tipos de tráfego foram marcados como grupo padrão.

Você também configurou três computadores na mesma rede ethernet do roteador "Qos_Router".