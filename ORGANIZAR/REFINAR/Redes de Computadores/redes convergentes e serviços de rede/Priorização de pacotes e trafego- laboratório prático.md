### Nesse laboratório recomenda-se o uso do software packet tracer para configurar ACL´s (Access Control List) e filtrar o tráfego dos pacotes que possuem o roteamento EIGRP

Siga os passoa abaixo e acompanhe o vídeo disponível nessa aula para executar o exercício.

**1º Passo:**  Configuração para criar a class-map, que marca todos os pacotes EIGRP críticos e solicitamos que todo protocolo eigrp seja marcado com este tráfego:

**2°Passo:**  Criar a política de marcação, com a classe critica, definir a precedência.

**3°Passo:** Concluídas as etapas para configurar uma politica que marca todos os pacotes EIGRP críticos temos também que definir o nível de precedência a 7. Aplicamos a policy criado na interface. A politica será aplicado a S0/0/0 de QoS-Router, portanto, todo o tráfego será marcado.

Observe o vídeo que demonstra a montagem do cenário que deve ser construído no Packet tracer. O modelo do roteador a ser utilizado é o 2811. Não  esqueça de que é necessário adicionar um módulo WIC-2T (duas portas seriais em cada roteador). O cabo serial é o tipo DTE. Insira um switch 2950-24.

**Configuração das máquinas**

`1.` `PC0 --> IP 10.1.1.2. Máscara: 255.0.0.0. Gateway: 10.1.1.1` `2.` `PC1 --> IP 10.1.1.3. Máscara: 255.0.0.0. Gateway: 10.1.1.1` `3.` `PC2 --> IP 10.1.1.4. Máscara: 255.0.0.0. Gateway: 10.1.1.1`

**Configuração do Router QoS**

`1.` `Router>enable` `2.` `Router\#configure terminal` `3.` `Router(config)\#hostname QoS_Router` `4.` `QoS_Router(config)\#ip ssh version 1` `5.` `QoS_Router(config)\#spanning-tree mode pvst` `6.` `QoS_Router(config)\#class-map match-all geral` `7.` `QoS_Router(config-cmap)\#match protocol eigrp` `8.` `QoS_Router(config-cmap)\#exit` `9.` `QoS_Router(config)#class-map match-any participativo` `10.` `QoS_Router(config-cmap)#match protocol telnet` `11.` `QoS_Router(config-cmap)#match protocol ssh` `12.` `QoS_Router(config-cmap)#exit` `13.` `QoS_Router(config)#class-map match-any web` `14.` `QoS_Router(config-cmap)#match protocol http` `15.` `QoS_Router(config-cmap)#exit` `16.` `QoS_Router(config)\#policy-map markingpolicy` `17.` `QoS_Router(config-pmap)#class geral` `18.` `QoS_Router(config-pmap-c)\#set precedence 7` `19.` `QoS_Router(config-pmap-c)#exit` `20.` `QoS_Router(config-pmap)#class participativo` `21.` `QoS_Router(config-pmap-c)#set precedence 5` `22.` `QoS_Router(config-pmap-c)#exit` `23.` `QoS_Router(config-pmap)#class web` `24.` `QoS_Router(config-pmap-c)#set precedence 3` `25.` `QoS_Router(config-pmap-c)#exit` `26.` `QoS_Router(config-pmap)#exit` `27.` `QoS_Router(config)\#interface loopback0` `28.` `QoS_Router(config-if)#ip add 10.0.0.1 255.255.255.255` `29.` `QoS_Router(config-if)#exit` `30.` `QoS_Router(config)#interface fastEthernet 0/0` `31.` `QoS_Router(config-if)#ip add 10.1.1.1 255.255.255.0` `32.` `QoS_Router(config-if)\#duplex auto` `33.` `QoS_Router(config-if)\#speed auto` `34.` `QoS_Router(config-if)\#no shutdown` `35.` `QoS_Router(config-if)#exit` `36.` `QoS_Router(config)#interface serial 0/0/0` `37.` `QoS_Router(config-if)#ip add 172.16.12.1 255.255.255.0` `38.` `QoS_Router(config-if)\#tx-ring-limit 1` `39.` `QoS_Router(config-if)\#service-policy output markingpolicy` `40.` `QoS_Router(config-if)\#hold-queue 1 out` `41.` `QoS_Router(config-if)#no shutdown` `42.` `QoS_Router(config-if)#exit` `43.` `QoS_Router(config)\#router eigrp 1` `44.` `QoS_Router(config-router)\#network 172.16.0.0` `45.` `QoS_Router(config-router)#network 10.0.0.0` `46.` `QoS_Router(config-router)#no auto-summary` `47.` `QoS_Router(config-router)#exit` `48.` `QoS_Router(config)#exit` `49.` `QoS_Router#` `50.` `QoS_Router\#write` `51.` `Building configuration...` `52.` `[OK]` `53.`

**Configuração do Router R2**

`1.` `Router>enable` `2.` `Router\#configure terminal` `3.` `Router(config)\#hostname R2` `4.` `R2(config)\#ip ssh version 1` `5.` `R2(config)\#spanning-tree mode pvst` `6.` `R2(config)\#interface loopback0` `7.` `R2(config-if)#ip add 10.0.0.2 255.255.255.255` `8.` `R2(config-if)\#exit` `9.` `R2(config)#interface serial 0/0/0` `10.` `R2(config-if)#ip add 172.16.2.2 255.255.255.0` `11.` `R2(config-if)\#clock rate 800000` `12.` `R2(config-if)\#no shutdown` `13.` `R2(config-if)#exit` `14.` `R2(config)#interface serial 0/0/1` `15.` `R2(config-if)#ip add 172.16.23.2 255.255.255.0` `16.` `R2(config-if)#no shutdown` `17.` `R2(config-if)#exit` `18.` `R2(config)\#router eigrp 1` `19.` `R2(config-router)\#network 172.16.0.0` `20.` `R2(config-router)#no auto-summary` `21.` `R2(config-router)#exit` `22.` `R2(config)#exit` `23.` `R2#` `24.` `R2\#Write`

**Configuração do Router R3**

`1.` `Router>enable` `2.` `Router\#configure terminal` `3.` `Router(config)\#hostname R3` `4.` `R3(config)\#ip ssh version 1` `5.` `R3(config)\#spanning-tree mode pvst` `6.` `R3(config)\#interface loopback0` `7.` `R3(config-if)#ip add 10.0.0.3 255.255.255.255` `8.` `R3(config-if)\#exit` `9.` `R3(config)#interface serial 0/0/1` `10.` `R3(config-if)#ip add 172.16.23.3 255.255.255.0` `11.` `R3(config-if)\#no shutdown` `12.` `R3(config)\#router eigrp 1` `13.` `R3(config-router)\#network 172.16.0.0` `14.` `R3(config-router)#no auto-summary` `15.` `R3(config-router)#exit` `16.` `R3(config)#exit` `17.` `R3#` `18.` `R3\#write`

**Testando a marcação dos pacotes:**

A fim de assegurar que a configuração aplicada está funcionando, marcando o trafego de saida, é importante testar a rede para Qualidade de Serviço.

Router_Qos# show policy-map interface serial 0/0/0

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/1/9/321959/index.html)

**Considerações finais**

Você configurou essa rede com as seguintes características: o roteador "QoS_Router" foi configurado para usar QoS, a fim de marcar o serviço de roteamento EIGRP e os tráfegos telnet, SSH e HTTP, que existem na interface serial 0/0/0. A configuração do "policy-map" foi feita com IP precedence nos campos para 7 (pacotes críticos EIGRP), 5 para pacotes "interactive" (telnet e SSH) e 3 para tráfego web (HTTP). Todos os outros tipos de tráfego foram marcados como grupo padrão. Você também configurou três computadores na mesma rede ethernet do roteador "Qos_Router" e posteriormente visualizou a saida da interface através do comando: Router_Qos# show policy-map interface serial 0/0/0.