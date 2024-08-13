### Introdução

Muitas vezes, os administradores de rede negligenciam os aspectos de segurança que envolve os switches e roteadores da rede. Voltando seus esforços, principalmente, para proteção da rede de ataques externo, esquecendo que, atualmente, muitos ataques podem surgir a partir da sua própria rede interna, até mesmo, sendo executados por funcionários insatisfeitos.

Você pensou na possibilidade de um atacante ter acesso físico aos dispositivos de sua rede, conforme ilutrado na figura abaixo! Caso isso aconteça, ele pode ter acesso as interfaces de configuração dos equipamentos, alterando senhas e o comportamento do equipamento como, por exemplo, realizar o espelhamento de uma porta com objetivo de desviar ou espelhar o tráfego para sua interface.

Ataques desse tipo podem ser facilmente mitigados com boas práticas na configuração e manutenção dos equipamentos de rede.

![[Untitled 88.png|Untitled 88.png]]

### Possíveis vulnerabilidades e ataques

Para ilustrar as possíveis vulnerabilidades dos switches e roteadores vamos pensar no seguinte cenário com base na topologia que segue (Cisco Systems):

1. Os switches e roteadores são configurados por meio da linha vty utilizando o protocolo Telnet.
2. A configuração dos equipamentos também pode ser realizada por interface WEB utilizando protocolo HTTP.
3. Portas não utilizadas nos switches estão ativas. Basta apenas conectar o cabo de rede para ativar a interface.
4. Permite a negociação automática do modo de operação da interface, ou seja, permite que a interface negocie entre trunk e access.
5. Protocolos de descoberta de vizinhos, como CDP (Cisco Discovery Protocol) e o LLDP (Link-Layer Discovery Protocol - IEEE 802.1AB) estão sendo utilizados.
6. Anúncios de protocolos de roteamento estação sendo propagados para rede interna.
7. A comunidade read-write do SNMP está ativada nos equipamentos.

![[Untitled 1 52.png|Untitled 1 52.png]]

O cenário acima pode parecer inofensivo, entretanto, as possíveis vulnerabilidades desse cenário podem ser exploradas pelo atacante e trazer sérios riscos ao funcionamento da rede, indo desde roubo de dados a indisponibilidade total da rede. Vamos entender o porquê de cada item do cenário apresentado:

1. O acesso vty permite a configuração dos equipamentos remotamente, mas, hoje, seu uso não é recomenda pois o Telnet realiza o transporte de dados pela rede de forma não criptografada. Recomenda-se o uso SSH (Secure Socket Shell) no processo de autenticação nos roteadores e switches.

**SAIBA MAIS...**

Para aumentar ainda mais a segurança no acesso aos equipamentos, configure, sempre que possível, mecanismos de autenticação externos, tais como, RADIUS e TACACS+, que além do processo de Autenticação, permite também Autorização e Auditoria (padrão AAA).

1. Pelos mesmos motivos do item anterior, o uso de HTTP para configuração via interface WEB também não é recomendo, opte por HTTPS.  
2.  
Deixar as portas do switch sempre ativas também não é uma boa prática. Pois qualquer usuário pode conectar o cabo e muitas vezes, obter endereço IPs. Além disso, loopings na camada 2 pode ocorrer, dependendo claro, de como os dispositivos estão configurados e interconectados.  
3.  
Permitir que a interface negocie dinamicamente entre trunk e access também pode deixar a sua rede vulnerável a ataques que objetivam mudar o estado da interface para trunk. Se a interface está conectada a dispositivos finais, configure-a em modo access.  
4.  
Protocolos de descoberta de vizinhos tais como CDP e LLDP, por padrão propagam informações aos vizinhos a cada 60 segundos. Apesar de serem úteis no dia-a-dia, por meio deles é possível descobrir informações dos equipamentos e facilitar ataques do tipo salto de VLAN (VLAN hopping). Sempre desativa esse recurso caso não necessário.  
5.  
Por padrão, os roteadores propagam informações de roteamento por todas as interfaces onde o protocolo de roteamento foi ativado. Propagar informações de roteamento para a rede interna podem ser utilizadas pelo atacante como meio de alterar o encaminhamento redirecionando, inclusive, o tráfego para si.  
6.  
Ativar a comunidade read-write do SNMP permite que alterações sejam realizadas no equipamento. Sempre que possível SNMPv3 que permite a criptografia e autenticação.

**SAIBA MAIS...**

Para aumentar ainda mais a segurança no acesso aos equipamentos, utilize sempre ACL (Listas de Controle de Acesso) para limitar quem realmente pode configurar os equipamentos. Para saber mais sobre ACL, acesse: [**https://www.cisco.com/c/pt_br/support/docs/ip/access-lists/26448-ACLsamples.html**](https://www.cisco.com/c/pt_br/support/docs/ip/access-lists/26448-ACLsamples.html)

### Aplicação de conceitos

Vamos colocar em prática, na topologia abaixo, alguns dos itens apresentados acima.

**# SW1 - Configuração do estado de todas as portas e do port-security#**

`1.` `switch>enable` `2.` `switch\#configure terminal` `3.` `switch(config)\#hostname SW1` `4.` `SW1(config)\#interface range f0/1-24` `5.` `SW1(config-if-range)\#switchport mode access` `6.` `SW1(config-if-range)#switchport port-security` `7.` `SW1(config-if-range)#switchport port-security maximum 1` `8.` `SW1(config-if-range)#switchport port-security mac-address stick` `9.` `SW1(config-if-range)#switchport port-security violation shutdown`

**# SW1 - Portas não utilizas - SHUTDOWN #**

`1.` `SW1(config)\#interface range f0/3-24` `2.` `SW1(config-if-range)\#shutdown`

**# SW1 - Adicionar IP na interface VLAN1 #**

`1.` `SW1(config)# int vlan1` `2.` `SW1(config)\#ip add 192.168.1.251 255.255.255.0`

**# SW1 - Configuração Acesso SSH #**

Na configuração do acesso SSH, é necessário alterar o nome padrão dos roteadores e switches por meio do comando _**hostname**_ (comando já executado anteriormente) assim como definir o nome de domínio (**ip domain-name**). Estas etapas são fundamentais para gerar a chave SSH. A chave SSH para encriptação e decriptação  é gerada na linha 2. Recomenda-se, no mínimo, 1024 bits para a geração de chave. Os comandos _**ssh time-out 60**_  e _**ip ssh authentication-retries 2**_  foram utilizados para definir o tempo máximo da sessão e quantidade máxima de tentativas, respectivamente. Finalmente, o usuário _**francisco**_ foi definido com privilégio máximo (nível 15).

Nas linhas de 7 a 9 é definido que o transporte de entrada é SSH (porta 22/TCP) e não mais Telnet (porta 23/TCP). Nas demais linhas foi configurado o acesso via interface console (_**line consolo 0**_) e definida a senha de modo privilegiado (_**enable secret**_). Por fim, todas as senhas são criptografadas por meio do comando _**service password-encryption**_ (Filippetti, M. A. 2017)_**.**_

`1.` `SW1(config)# ip domain-name uninove.br` `2.` `SW1(config)# crypto key generate rsa` `3.` `--> Escolha a quantidade de bits. Recomenda-se mínimo de 1024 <--` `4.` `SW1(config)# ip ssh time-out 60` `5.` `SW1(config)# ip ssh authentication-retries 2` `6.` `SW1(config)# username francisco priv 15 secret 1234` `7.` `SW1(config)# line vty 0 4` `8.` `SW1(config)\#login local` `9.` `SW1(config-line)# transport input ssh` `10.` `SW1(config-line)\#line console 0` `11.` `SW1(config-line)#login` `12.` `SW1(config-line)\#password` `13.` `SW1(config-line)\#exit` `14.` `SW1(config)\#enable secret uninove` `15.` `SW1(config)\#service password-encryption`

**# SW1 - Configuração da comunidade SNMP somente leitura #**

`1.` `SW1(config)\#snmp-server community SW1 ro`

**# R1 - Configuração IP e roteamento #**

Observe que adicionado o comando **passive-interface FastEthernet0/0** dentro da configuração de roteamento OSPF. Essa opção desativa a propagação de informações de roteamento para a rede interna.

`1.` `router>enable` `2.` `router\#configure terminal` `3.` `router(config)\#hostname R1` `4.` `R1(config)\#interface Loopback0` `5.` `R1(config-if)\#ip address 1.1.1.1 255.255.255.255` `6.` `R1(config-if)#interface FastEthernet0/0` `7.` `R1(config-if)#ip address 192.168.1.254 255.255.255.0` `8.` `R1(config-if)#interface Serial0/0/0` `9.` `R1(config-if)#ip address 200.200.200.2 255.255.255.252` `10.` `R1(config-if)\#exit` `11.` `R1(config)\#router ospf 1` `12.` `R1(config-router)#router router-id 1.1.1.1` `13.` `R1(config-router)\#passive-interface FastEthernet0/0` `14.` `R1(config-router)\#network 200.200.200.0 0.0.0.3 area 0` `15.` `R1(config-router)#network 192.168.1.0 0.0.0.255 area 0` `16.` `R1(config-router)#network 1.1.1.1 0.0.0.0 area 0`

**# R1 - Configuração da comunidade SNMP somente leitura #**

`1.` `R1(config)\#snmp-server community R1 ro`

**# R1 - Configuração Acesso SSH #**

`1.` `R1 (config)\#ip domain-name uninove.br` `2.` `R1 (config)\#crypto key generate rsa` `3.` `--> Escolha a quantidade de bits. Recomenda-se mínimo de 1024 <--` `4.` `R1 (config)#ip ssh time-out 60` `5.` `R1 (config)#ip ssh authentication-retries 2` `6.` `R1 (config)\#username francisco priv 15 secret 1234` `7.` `R1 (config)\#line vty 0 4` `8.` `R1 (config-line)\#login local` `9.` `R1 (config-line)# transport input ssh` `10.` `R1 (config-line)#line console 0` `11.` `R1 (config-line)#login` `12.` `R1 (config-line)\#password` `13.` `R1 (config-line)\#exit` `14.` `R1 (config)\#enable secret uninove` `15.` `R1 (config)\#service password-encryption`

**# R2 - Configuração IP e roteamento #**

`1.` `router>enable` `2.` `router\#configure terminal` `3.` `router(config)\#hostname R2` `4.` `R2(config)\#interface Loopback0` `5.` `R2(config-if)\#ip address 2.2.2.2 255.255.255.255` `6.` `R2(config-if)#interface Serial0/0/0` `7.` `R2(config-if)#ip address 200.200.200.1 255.255.255.252` `8.` `R2(config-if)\#exit` `9.` `R2(config)\#router ospf 1` `10.` `R2(config-router)#router router-id 2.2.2.2` `11.` `R2(config-router)\#network 200.200.200.0 0.0.0.3 area 0` `12.` `R2(config-router)#network 2.2.2.2 0.0.0.0 area 0`

**# R2 - Configuração da comunidade SNMP somente leitura #**

`1.` `R2(config)\#snmp-server community R2 ro`

**# R2 - Configuração Acesso SSH #**

`1.` `R2 (config)\#ip domain-name uninove.br` `2.` `R2 (config)\#crypto key generate rsa` `3.` `Escolha a quantidade de bits. Recomenda-se mínimo de 1024` `4.` `R2 (config)#ip ssh time-out 60` `5.` `R2 (config)#ip ssh authentication-retries 2` `6.` `R2 (config)\#username francisco priv 15 secret 1234` `7.` `R2 (config)\#line vty 0 4` `8.` `R2 (config-line)\#login local` `9.` `R2 (config-line)# transport input ssh` `10.` `R2 (config-line)#line console 0` `11.` `R2 (config-line)#login` `12.` `R2 (config-line)\#password` `13.` `R2 (config-line)\#exit` `14.` `R2 (config)\#enable secret uninove` `15.` `R2 (config)\#service password-encryption`

**Desabilitar anúncios CDP e DTP #**

Os anúncios CDP podem ser desabilitados tanto nos roteadores quanto no switch. No exemplo abaixo, foi executado no  switch SW1. Por outro lado, os anúncios DTP podem ser desabilitados por meio do comando de interface do switch, conforme mostrado abaixo. Lembrando que, os anúncios DTP são utilizados para configurar automaticamente as interfaces (trunk ou access), enquanto as mensagens CDP são utilizadas para descoberta de dispositivos vizinhos.

`1.` `SW1\#conf t` `2.` `SW1(config)\#no cdp run` `3.` `SW1(config)\#int g0/1` `4.` `SW1(config-if)\#switchport nonegotiate`

### Acesso via SSH

Para realizar o acesso via SSH ao dispositivos, acesso o _**command prompt**_ e execute o comando ssh -l [username] [End. IP do Alvo], conforme ilustrado na figura que segue.

![[Untitled 2 41.png|Untitled 2 41.png]]

### **Espelhamento de porta (SPAN)**

Antigamente, com o uso de HUBs em rede, era possível monitorar facilmente o tráfego que da rede, pois todo e qualquer tráfego chegava a todas as interfaces. Entretanto, com a adoção dos switches, dispositivos de camada 2, e a criação de domínios de broadcast separados em cada uma de suas interfaces, este monitoramento não seria mais possível. Para contornar essa característica dos switches foi desenvolvida função SPAN (Switched Port Analyzer) que permite espelhar todo tráfego que passa por uma interface em outra interface, podendo, até mesmo, espelhar o tráfego de toda uma VLAN em outra interface (McNab, Chris. 2020).

A função SPAN é extremamente útil para monitorar o tráfego de uma ou mais interfaces de forma passiva como, por exemplo, fazendo o uso de um Detector de Intrusão (IDS) ligada a porta espelhada, conforme ilustrado na figura que segue.

![[Untitled 3 27.png|Untitled 3 27.png]]

### Configuração SPAN

Para ilustrar o seu funcionamento vamos utilizar a topologia anterior. Perceba que já existe um sniffer ligado a **interface g0/2** do switch com o proposito de monitorar o tráfego, nesse exemplo, da **interface g0/1**_**.**_ Poderíamos monitorar mais de uma interface, bastando, apenas, repetir o comando da linha 2 para a nova interface.

`1.` `SW1# configure terminal` `2.` `SW1 (config)# monitor session 1 source interface g0/1` `3.` `SW1 (config)# monitor session 1 destination interface g0/2` `4.` `SW1 (config)# exit` `5.`   `6.` `# Para visualizar a sessão utilize #` `7.` `SW1# show monitor session`