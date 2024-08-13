### Introdução

O presente tópico tem por objetivo a integração de redes WAN e LAN com as aplicações de rede tendo como base o modelo TCP/IP de cinco camadas para a implementação da topologia. Um dos principais objetivos do modelo TCP/IP é facilitar a implementação e a resolução de problemas de rede. Você pode pensar em construir e configurar uma rede, por exemplo, a partir da camada física, instalando o cabeamento e todos os equipamentos passivos da infraestrutura e, a partir dai, ir subindo o modelo TCP/IP: Acesso a Rede, Internet, etc.

### O cenário

O cenário que devemos implementar consiste de duas redes locais (LAN) interligadas a partir de um link WAN, conforme mostrado abaixo. A LAN 1 necessita de 40 pontos de rede e a LAN-2 150 pontos. Na WAN existe um servidor DNS e dois servidores HTTP, com o serviço FTP habilitados. Outros detalhes serão exibidos abaixo a partir da camada Física em direção a camada de Aplicação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/0/0/1800012/40337.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/8/0/0/0/1800012/40337.jpg)

### Camada Física

A camada de nossa topologia consiste de estabelecer a ligação dos cabeamentos entre os dispositivos: PCs, switches e roteadores. Vamos dividir essa tarefa entre LAN-1, LAN-2 e WAN.

**LAN-1 e LAN-2**

- Todos os PCs serão ligados ao switch a partir de cabeamento par-trançado.
- O servidor da LAN-1 deve ser ligado ao switch por meio de cabo de cabo par trançado.
- Os servidores da WAN e da LAN-2 devem ser ligados aos switches por meio de cabo par trançado.
- A ligação entre os switches da LAN-1 e WAN e os roteadores deve ser por meio de fibra óptica.
- A ligação entre o switch da LAN-2 ao roteador será via cabo par trançado.

**WAN**

- Os roteadores da rede WAN serão interligados por meio de cabo serial.
- O roteador do meio será interligado ao switch por meio de fibra óptica.

### Camada de enlace

Na camada de enlace de nossa topologia temos que definir as tecnologias de acesso ao meio de transmissão e como o switch interligará os PCs da rede, mas detalhes serão exibidos por rede.

**LAN-1**

- Para interligar os PCs ao switch será utilizada a tecnologia Ethernet 100base-T ou Fastethernet.
- A ligação entre o switch e o roteador deverá ser via FastEthernet.
- Todos os computadores estão sob o mesmo domínio de broadcast

**LAN-2**

- A rede será subdivida em 3 VLANs (ADM, INFO e FIN) com 50 computadores por VLAN.
- As VLAN serão configuradas no switch camada 3 (layer 3) e a cada VLAN do switch será conectado ao switch camada 2 (layer 2).
- Para interligar os PCs ao switch será utilizada a tecnologia Ethernet 100base-T ou FastEthernet para cabo par trançado.
- A ligação entre o servidor e switch 1000base-T ou Gigabitethernet para cabo par trançado.
- O switch da VLAN INFO será ligado ao switch core (layer 3) por meio da tecnologia GigabitEthernet par trançado.
- Os demais switches serão interligados ao switch core por meio da tecnologia FastEthernet par trançado.
- O switch será interligado ao roteador por meio da tecnologia FastEthernet.

**WAN**

O protocolo WAN para acesso ao meio de transmissão será HDLC.

### Camada de Internet

Os endereços IPs de rede a serem utilizados são mostrados na tabela abaixo (dividido por rede). O servidor DNS para todos os dispositivos terá endereço 100.100.100.1 /29 e o servidor HTTP terá endereço 100.100.100.2 /29.

![[Untitled 42.png|Untitled 42.png]]

**NAT**

Os computadores das redes locais LAN-1 e LAN-2 para ter acesso a WAN deverão utilizar endereços IPs públicos. Para tanto, o serviço NAT deverá ser configurado nos switches cores. Uma rota padrão também deverá ser configura para alcançar os roteadores da WAN. Os endereços IPs que deverão ser configurados nos switches das redes internas são mostrados na tabela abaixo.

![[Untitled 1 28.png|Untitled 1 28.png]]

**Roteamento**

Para a topologia deve-se configurar um protocolo de roteamento dinâmico do tipo Link State que utiliza como métrica a largura de banda.

### Camada de Transporte e Aplicação

Aplicações de rede que devem ser configuradas são descritas abaixo.

- **HTTP:** O serviço HTTP deverá ser configurado na rede WAN-Server.
- **FTP**: O serviço FTP deverá ser habilitado no mesmo servidor HTTP.
- **E-mail**: Os serviços SMTP e POP3 deverão ser habilitados no servidor de e-mail e os clientes deverão ser configurados nas redes locais LAN-1 e LAN-2.
- **DNS**: O serviço DNS deverá ser configurado no servidor DNS (100.100.100.1 /29) para fazer a resolução de nomes para as seguintes aplicações

![[Untitled 2 25.png|Untitled 2 25.png]]

**DHCP**

- Cada rede local deverá ter o serviço DHCP configurado para atender as necessidades anteriores. Na LAN-1 apenas um pool (escopo) deve ser configurado, enquanto que na LAN-2 são necessários três pools.

**SSH e Telnet**

- A configuração dos switches multicamadas deverá ser a partir do serviço de terminal Telnet, enquanto que os roteadores deverão ser configuras a partir de SSH.