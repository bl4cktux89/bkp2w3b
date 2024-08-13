### **Introdução**

Em redes LANs, com todas as máquinas conectadas ao mesmo switch e ao mesmo domínio de broadcast, estão susceptíveis a inundação de mensagens de broadcast em sua interface como, por exemplo, solicitações ARP e DHCP, mesmo que o destinatário da mensagem não seja aquela máquina. Esta característica inerente ao funcionamento dos switches pode trazer sérios problemas de desempenho e, por outro lado, trazer consequências danosas no que se refere a segurança das corporações.

O emprego do conceito de LANs Virtuais (VLANs) proporciona a segmentação da rede em domínios de broadcast menores, limitando a propagação de broadcasts somente aquele segmento limitado pela VLAN. Além disso, o uso de VLANs permite a segregação do tráfego de diferentes departamentos de uma organização, fazendo com que o tráfego entre as diferentes VLANs necessite ser roteado por um dispositivo de camada 3 ou um dispositivo multicamadas, conforme ilustrado na figura que segue.

Utilizando-se por sua vez de dispositivos de camada 3, o tráfego pode ser completamente isolado entre as VLANs por meio, por exemplo, de ACLs (listas de controle de Acesso).

![[Untitled 89.png|Untitled 89.png]]

### VLANs e a segurança a rede

As VLANs são identificadas por meio da marcação dos quadros Ethernets. Um switch sabe a qual VLAN pertence o quadro através do frame tag 802.1q (de 4 bytes) é introduzido ao quadro original Ethernet, conforme ilustrado na figura a seguir. Essa marcação é introduzida sempre que o quadro necessita passar por uma interface de transporte (trunk) entre dois switches, por exemplo. Quando o quadro chega à interface do dispositivo final a tag de VLAN é retirada, já que o dispositivo final não consegue ler essa informação adicional.

Por padrão, a maioria dos fabricantes destinam a VLAN 1 como a VLAN Nativa e tem todas as suas interfaces associadas a essa VLAN, conforme ilustrado abaixo na saída do comando s_**how vlan brief**_ aplicada ao SW1. A VLAN Nativa tem por objetivo manter a compatibilidade com dispositivos antigos, já que ela não recebe a marcação de quadro. Por outro lado, a maioria dos equipamentos, padrão, também utiliza a VLAN 1 Nativa para gerenciamento remoto do equipamento. Além disso, é utilizada para transportar os protocolos CDP, LLDP, DTP e BPDUs (Filippetti, Marco Aurélio. 2017).

![[Untitled 1 53.png|Untitled 1 53.png]]

### VLAN hopping

Não modificar as configurações padrão do switch, principalmente, utilizar a VLAN 1 como Nativa pode deixar a sua rede vulnerável a ataques de salto de VLAN (VLAN hopping), conhecido também por double tag (marcação dupla). Neste tipo de ataque, o atacante localizado na VLAN 1 (Nativa) envia quadros com dupla marcação 802.1q: o primeiro deles interna (inner tag),  correspondente a VLAN alvo ao qual ele deseja alcançar; a segunda externa (outter tag), correspondente a VLAN 1. Quando o switch recebe o quadro, remove a marcação externa (tag da VLAN 1) e encaminha-o com a marcação interna (VLAN alvo) pela interface de transporte (trunk) até o switch do dispositivo alvo. No switch de destino, a marcação é retirada e o quadro é encaminhado para o dispositivo de destino (alvo). Na figura a seguir é ilustrado esse processo, sendo que o PC do atacante está na VLAN 1 e o alvo na VLAN 20 (CCNA R&S, 2020).

![[Untitled 2 42.png|Untitled 2 42.png]]

O tráfego gerado no processo apresentando acima é apenas unidirecional, ou seja, sempre da máquina do atacante para o da vítima. Esta é uma maneira de realizar ataques do tipo DoS.

Switch spoonfing (falsificação de switch) também é utilizado como ataque do tipo VLAN hopping, já que o atacante tenta negociar, por meio de pacotes DTP, o entroncamento com os switches que possuem suas interfaces configuradas em modo dinâmico. Uma vez tendo sucesso, a máquina do atacante sua interface em modo tronco e terá acesso a todas as VLANs. Por isso, é recomendado não utilizar a negociação automática de estado de interfaces.

### Boas práticas na criação de VLANs

**As boas práticas a seguir são recomendas durante a criação e manutenção das VLANs**

- **Alterar o número da VLAN Nativa:** O ataque apresentado anteriormente pode ser mitigado com ações simples. A primeira delas, recomenda-se alterar a VLAN 1 Nativa para outro número e não a utilizar para alocar portas. Além disso, a VLAN nativa deve ser marcada na interface tronco.
- **Alterar a VLAN de Gerência:** Uma boa prática que também deve ser adotada é utilizar outra VLAN, não mais a VLAN Nativa e nem a VLAN 1, como VLAN de Gerenciamento do switch, pois elas são bem conhecidas pelos atacantes.
- **Associar interfaces não utilizadas a VLAN Black-hole:** É comum no jargão da área chamar a VLAN que não é roteada (não permitidas no tronco) de Black-hole, e associar as interfaces não utilizadas a ela, além disso, shutdown em todas as interfaces. Isso implica na retirada de todas as interfaces da VLAN padrão (VLAN 1).

### Laboratório de boas práticas

**Vamos praticar tais conceitos na topologia abaixo com a seguinte configuração:**

- 05 VLANs: VLAN-10-FIN, VLAN-20-ADM, VLAN-30-SERVER, VLAN-99-NATIVA E VLAN-999-BLACK-HOLE.
- 01 Switch 2960, tendo as interfaces f0/1, f0/2 e f0/3 destinadas aos servidores DNS, DHCP e HTTP;
- 02 PCs na VLAN-10 (interfaces f0/4 e f0/5) e 02 PCs na VLAN-20 (interfaces f0/6 e f0/7).
- 01 roteador 2900 para roteamento entre as VLANs.
- Interface g0/1 como interface tronco.
- Interfaces não utilizadas ficarão na VLAN BLACK-HOLE e derrubadas. Além disso, a negociação automática do estado da porta também será desativada.
- A configuração de port-sercurity será adicionada em todas as interfaces.
- Os endereços IPs serão obtidos por meio do servidor DHCP localizado na VLAN 30 - SERVER. Faixa de endereçamento:
    - VLAN 10 - 192.168.10.0 /24.
    - VLAN 20 - 192.168.20.0 /24.
    - VLAN 30 - 192.168.30.0 /24.
- Endereços IPs dos servidores:
    - DHCP - 192.168.30.1 /24.
    - DNS - 192.168.30.2 /24.
    - HTTP - 192.168.30.3 /24.

`1.` `# Criação das VLANs #` `2.` `switch> enable` `3.` `switch\#conf t` `4.` `switch (config)\#hostname SW1` `5.` `SW1(config)\#vlan 10` `6.` `SW1(config-vlan)\#name FIN` `7.` `SW1(config-vlan)#vlan 20` `8.` `SW1(config-vlan)#name ADM` `9.` `SW1(config-vlan)#vlan 30` `10.` `SW1(config-vlan)#name SERVER` `11.` `SW1(config-vlan)#vlan 99` `12.` `SW1(config-vlan)#name NATIVA` `13.` `SW1(config-vlan)#vlan 999` `14.` `SW1(config-vlan)#name BLACK-HOLE` `15.` `SW1(config-vlan)\#exit` `16.`   `17.` `# Associação das interfaces as VLANs e configuração de segurança de porta #` `18.` `SW1(config)\#int range f0/1-3` `19.` `SW1(config-if-range)# switchport mode access` `20.` `SW1(config-if-range)# switchport access vlan 30` `21.` `SW1(config-if-range)# switchport nonegotiate` `22.` `SW1(config-if-range)# switchport port-security` `23.` `SW1(config-if-range)# switchport port-security maximum 1` `24.` `SW1(config-if-range)# switchport port-security mac-address sticky` `25.` `SW1(config-if-range)# switchport port-security violation shutdown` `26.` `SW1(config-if-range)#exit` `27.` `SW1(config)#int range f0/4-5` `28.` `SW1(config-if-range)# switchport mode access` `29.` `SW1(config-if-range)# switchport access vlan 10` `30.` `SW1(config-if-range)# switchport nonegotiate` `31.` `SW1(config-if-range)# switchport port-security` `32.` `SW1(config-if-range)# switchport port-security maximum 1` `33.` `SW1(config-if-range)# switchport port-security mac-address sticky` `34.` `SW1(config-if-range)# switchport port-security violation shutdown` `35.` `SW1(config-if-range)#exit` `36.` `SW1(config)#int range f0/6-7` `37.` `SW1(config-if-range)# switchport mode access` `38.` `SW1(config-if-range)# switchport access vlan 20` `39.` `SW1(config-if-range)# switchport nonegotiate` `40.` `SW1(config-if-range)# switchport port-security` `41.` `SW1(config-if-range)# switchport port-security maximum 1` `42.` `SW1(config-if-range)# switchport port-security mac-address sticky` `43.` `SW1(config-if-range)# switchport port-security violation shutdown` `44.` `SW1(config-if-range)#exit` `45.`   `46.` `# Associação das interfaces não utilizadas a VLAN BLACK-HOLE e configuração de segurança de porta #` `47.` `SW1(config)#int range f0/8-24` `48.` `SW1(config-if-range)# shutdown` `49.` `SW1(config-if-range)# switchport mode access` `50.` `SW1(config-if-range)# switchport access vlan 999` `51.` `SW1(config-if-range)# switchport nonegotiate` `52.` `SW1(config-if-range)# switchport port-security` `53.` `SW1(config-if-range)# switchport port-security maximum 1` `54.` `SW1(config-if-range)# switchport port-security mac-address sticky` `55.` `SW1(config-if-range)# switchport port-security violation shutdown` `56.` `SW1(config-if-range)#exit` `57.` `SW1(config)#int g0/2` `58.` `SW1(config-if)# switchport access vlan 999` `59.` `SW1(config-if)# switchport mode access` `60.` `SW1(config-if)# switchport nonegotiate` `61.` `SW1(config-if)# shutdown` `62.`   `63.` `# Configuração da interface tronco e permissão de passagem de VLANs pelo tronco #` `64.` `SW1(config)#int g0/1` `65.` `SW1(config-if)# switchport trunk native vlan 99` `66.` `SW1(config-if)# switchport trunk allowed vlan 10,20,30` `67.` `SW1(config-if)# switchport mode trunk` `68.` `SW1(config-if)# switchport nonegotiate` `69.`   `70.` `# Configuração Dot1Q no roteador #` `71.` `router>enable` `72.` `router#conf t` `73.` `router (config)#hostname R1` `74.` `R1(config)\#interface g0/1` `75.` `R1(config-if)\#no shut` `76.` `R1(config-if)#interface g 0/1.10` `77.` `R1(config-subif)\#description VLAN10` `78.` `R1(config-subif)\#encapsulation dot1Q 10` `79.` `R1(config-subif)\#ip address 192.168.10.254 255.255.255.0` `80.` `R1(config-subif)#ip helper-address 192.168.30.1` `81.` `R1(config-subif)#interface g 0/1.20` `82.` `R1(config-subif)#description VLAN20` `83.` `R1(config-subif)#encapsulation dot1Q 20` `84.` `R1(config-subif)#ip address 192.168.20.254 255.255.255.0` `85.` `R1(config-subif)#ip helper-address 192.168.30.1` `86.` `R1(config-subif)#interface g 0/1.30` `87.` `R1(config-subif)#description VLAN30` `88.` `R1(config-subif)#encapsulation dot1Q 30` `89.` `R1(config-subif)#ip address 192.168.30.254 255.255.255.0` `90.` `R1(config-subif)#interface g 0/1.99` `91.` `R1(config-subif)#description VLAN NATIVA` `92.` `R1(config-subif)#encapsulation dot1Q 99 native`

Como resultado dessa configuração no switch, a sua tabela de VLANs e portas ficará da seguinte forma.

![[Untitled 3 28.png|Untitled 3 28.png]]

Observe que o port-security foi adicionada em todas as interfaces, menos a interfaces tronco. O port-security não deve ser adicionado em interface tronco, já que é por ela que o tráfego de diferentes VLANs passa. Observe também, que no roteador o comando ip helper-address 192.168.30.1, que tem a finalidade de encaminhar as requisições DHCP em broadcast das VLANs 10 e 20 diretamente para o servidor DHCP em unicast. Por sua vez a configuração DHCP dos pools de endereços é mostrada na figura que segue.

![[Untitled 4 23.png|Untitled 4 23.png]]

Você sabia que é possível configurar fazer com que dispositivos dentro da mesma VLAN não se conversem?

Sim. É possível! Para isso é utilizado o mecanismo de VLAN privada PVLAN. Neste caso, por exemplo, é possível fazer com que os servidores DHCP, DNS e HTTP do exercício anterior não tenha comunicação direta, apesar de estarem no mesmo domínio de broadcast. Isso aumenta a segurança desses servidores caso um atacante tenha acesso a um deles, ficará mais difícil que ele tenha acesso aos demais servidores. Para saber mais acesse: [**http://labcisco.blogspot.com/2013/09/private-vlan-na-seguranca-e.html**](http://labcisco.blogspot.com/2013/09/private-vlan-na-seguranca-e.html)

### Ataque de falsificação de servidor DHCP (DHCP Spoofing)

O DHCP Spoofing ou falsificação DHCP é um tipo de ataque no o atacante adiciona um servidor DHCP falso na rede, fazendo com que exista duplicidade e causando indisponibilidade do serviço. Por outro lado, o servidor DHCP falso pode distribuir uma faixa de endereçamento completamente diferente daquela do servidor legítimo, podendo, por exemplo, redirecionado o tráfego para outro gateway padrão ou até mesmo para um servidor DNS falso. Já pensou no risco caso isso aconteça??

### Prevênção

Para prevenir este tipo de ataque existe um recurso chamado DHCP snooping em switches de camada 2. Este recurso permite filtrar mensagens DHCP confiáveis/inválidas, a partir da construção e manutenção de uma tabela chamada DHCP Snooping Binding Table. Nesta tabela contém as portas confiáveis e não confiáveis, semelhante a um firewall, mas de camada 2.

Para ilustrar esse recurso vamos utilizar apenas um switch e dois servidores com o serviço DHCP ativo, um falso e o outro verdadeiro, conforme mostrado na figura que segue (CCNA Cybersecurity Operations, 2020) .

![[Untitled 5 20.png|Untitled 5 20.png]]

Ataque DHCP spoofing

`1.` `Switch(config)\#vlan 10` `2.` `Switch(config-vlan)\#exit` `3.` `Switch(config)\#int range f0/1-24` `4.` `Switch(config-if-range)\#switchport access vlan 10` `5.` `Switch(config-if-range)#exit` `6.` `Switch(config)# ip dhcp snooping` `7.` `Switch(config)# ip dhcp snooping vlan 10` `8.` `Switch(config)# interface range f0/2 - 24` `9.` `Switch(config-if-range)# ip dhcp snooping limit rate 5` `10.` `Switch(config-if-range)# interface f0/1` `11.` `Switch(config-if)# ip dhcp snooping trust`

Na configuração acima, foi habilitado o recurso DHCP snooping associada a VLAN 10. Por padrão, após a inserção desse comando todas as interfaces são consideradas não confiáveis. Por isso, não sequência a interface f0/1 ligada ao servidor legítimo foi configurada como confiável (_**ip dhcp snooping trust**_). O Comando _**ip dhcp snooping limit rate 5**_ indica o número de pacotes por segundo (bps) de requisição DHCP que uma interface não confiável pode receber.