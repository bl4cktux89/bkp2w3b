### Introdução

O gerenciamento de redes é mantido com um conjunto de comandos e pacotes e, ainda, pelo atendimento protocolar. A família de protocolos TCP/IP tem um conjunto de protocolos que permite o monitoramento e controle de todas as redes. Os mecanismos de gerência de rede são tanto suportados por facilidades e funcionalidades locais, quanto remotas. Portanto, vamos trabalhar bastante com as ferramentas que podem ajudar no gerenciamento local do servidor e, em seguida, ou concomitantemente, aplicar os mesmos conceitos nas redes remotas [1].

A maioria dos mecanismos de verificação de rede faz uso do protocolo ICMP (_**Internet Control Messages Protocol**_). Também existe uma infinidade de possibilidades associadas ao **SNMP (**_**Simple Network Management Protocol**_**)**. Aqui, por questões de eficácia no estudo, não vamos falar muito sobre os protocolos em si, mas sobre as aplicações e ferramentas. Existem muitas formas de conseguir a mesma informação e você deve optar pela forma que melhor se adapte.

### Comandos e dicas

Vou mostrar uma compilação de todas as ferramentas de rede que você deve conhecer para gerenciar corretamente suas redes. Muitas dessas ferramentas de rede existem há algum tempo, mas todas continuam a evoluir e ainda são usadas em ambientes produtivos. Elas são gratuitas, ou pelo menos têm uma versão aberta [2].

Todos os comandos abaixo são na verdade pacotes. Se algum deles não estiver presente, seu próprio Linux avisará para você instalá-lo.

### iftop

Iftop é semelhante ao **top** (para monitorar atividades no desktop), mas em vez de verificar principalmente o uso de CPU, ele escuta o tráfego de rede em interfaces de rede selecionadas e exibe uma tabela de uso instantâneo. Pode ser útil para responder perguntas como "Por que a internet em minha conexão está tão lenta?

**\#iftop -p -i interface**

A opção “**p**” está dizendo para rodar na forma promíscua (ou seja, vai ficar ouvindo o tráfego de toda a rede) e a opção “**i**” diz que é para ouvir pela interface que você colocou em “**interface**”. Veja um print deste comando:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875309/36819.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875309/36819.png)

### jnettop

O **jnettop** visualiza o tráfego de rede da mesma maneira que o **Iftop**. Ele também suporta saída de texto personalizável e um modo amigável para máquina para suportar análises futuras. Além disto mostra as portas e protocolos que estão sendo usados nas conexões.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875311/36820.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875311/36820.png)

### bandwidthd

BandwidthD rastreia o uso de sub-redes de rede TCP / IP e visualiza isso no navegador criando uma página html com gráficos em png. Existe um sistema orientado por banco de dados que suporta pesquisa, filtragem, sensores múltiplos e relatórios personalizados.

Para instalá-lo, primeiro tenha em mente que será importante você ter um servidor WEB para poder visualizar corretamente e adequadamente. O Apache seria ótimo. O **bandwidthd** pode ser instalado como segue:

**\#apt-get install bandwidthd**

Algumas telas de configuração aparecerão para você e todas são extremamente simples e autoexplicativas. Veja-as abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875318/36821.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875318/36821.png)

Escolhida a interface que irá ouvir o tráfego, passe para a próxima onde você escolhe as redes que quer monitorar. Se você está conectado à uma VPN, poderá controlar o tráfego de suas filiais, por exemplo.

Para ver o seu resultado digite bandwidthd na linha de comando tecle enter, abra um browser com a URL abaixo:

[**http://127.0.0.1/bandwidthd/**](http://127.0.0.1/bandwidthd/)

Além de muitas informações, ainda aparecerá um gráfico como o abaixo. Observe que tem pouco gráfico acontecendo, já que eu acabei de configurar o **bandwidthd** para demonstrar neste estudo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875321/36822.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/3/875321/36822.png)

Os dados vão aparecendo da direita para a esquerda.

Veja mais uma tabela com dados recebidos e transmitidos:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875455/36823.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875455/36823.png)

### Iptraf

O iptraf reúne uma variedade de métricas, tais como pacotes de conexão TCP e contagem de bytes, estatísticas de interface e indicadores de atividade, falhas de tráfego TCP / UDP e contagem de pacotes e bytes de estações.

Primeiro uma tela para escolher o que você quer fazer, existem muitas opções:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875457/36824.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875457/36824.png)

IP traffic monitor (iptraf):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875459/36825.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875459/36825.png)

General Interface Statistics (iptraf)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875461/36826.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875461/36826.png)

Detailed Interface Statistics (iptraf)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875463/36827.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875463/36827.png)

Statistics Breakdowns (iptraf)

Observe que aqui, se você pedir a estatística classificada por tamanho de pacotes, será criada uma tabela por faixas de tamanhos de pacotes, limitada pelo tamanho do MTU.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875465/36828.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/5/4/875465/36828.png)

A mesma opção (Statistics breakdown) na opção classificada por porta (Veja abaixo):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831630/0-07.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831630/0-07.png)

**Importante**: Ao fazer este exemplo, como você pode ver na figura acima, percebi o seguinte: A porta 53 é usada pelo DNS é normal para uso diário. A porta 443 é HTTPS, ou seja, se você está logado em algo que exige segurança (pode ser até seu e-mail), vai estar cheio de pacotes passando nesta porta. A porta 138 é por conta do SAMBA que roda em meio servidor, então a comunicação **NetBIOS** passa por aí. Bem, o problema é a porta 123. Ela não devia estar aí. A questão é que o protocolo (NTP - _**Network Time Protocol**_) é usado para sincronizar o tempo e isto é uma via gigantesca para ataques. Se você confia no relógio de seu servidor, feche está porta. Você percebeu como é importante usar pacotes como o **iptraf** para vasculhar sua rede?

Lan Station Monitor (iptraf)

Aqui mostra pelo MAC address quantos pacotes estão passando pela interface de todas as possíveis máquinas que estão na rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831632/0-08.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831632/0-08.png)

**tcpdump**

**Tcpdump**, é uma velha ferramenta, mas muito útil.  **Tcpdump** emitirá uma descrição do conteúdo do pacote que acabou de capturar, que corresponde à expressão que você forneceu no comando. Ele fornece o conteúdo e a origem do conteúdo, ou seja, quem está mandando ou recebendo aquele pacote. Você também pode salvar esses dados para análise posterior. Veja abaixo uma tela exemplo, com isto você vê que é preciso filtragem (como o **grep**) pois é muita coisa!

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831636/0-09.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831636/0-09.png)

### NETSTAT

Netstat é um pacote que está embutido na maioria das distribuições Linux. Vamos dedicar um espaço para várias opções do netstat por ser uma das ferramentas mais estáveis e completas do Linux.

**Listar portas TCP e UDP que estão ouvindo (listening)**

Listando todas as portas (TCP e UDP) usando a opção **netstat -a.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831640/0-10.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831640/0-10.png)

**Listar portas UDP**

Para lista apenas as portas UPD: **netstat -au**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831611/0-01.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831611/0-01.png)

### Mostrando estatísticas por protocolo

Exibe estatísticas por protocolo. Por padrão, as estatísticas são mostradas para os protocolos TCP, UDP, ICMP e IP. O parâmetro -s pode ser usado para especificar um conjunto de protocolos.

**netstat -s   (mostrando em forma de texto)**

- **---------------------------------------------------------------------------------------------------------------------------**

**Ip:**

**51041 total packets received**

**4 with invalid addresses**

**0 forwarded**

**0 incoming packets discarded**

**51023 incoming packets delivered**

**48481 requests sent out**

**348 dropped because of missing route**

**Icmp:**

**2086 ICMP messages received**

**1980 input ICMP message failed.**

**Histograma de entrada ICMP:**

**destination unreachable: 2079**

**echo replies: 7**

**2086 ICMP messages sent**

**0 ICMP messages failed**

**Histograma de saída ICMP**

**destination unreachable: 2079**

**echo request: 7**

**IcmpMsg:**

**InType0: 7**

**InType3: 2079**

**OutType3: 2079**

**OutType8: 7**

**Tcp:**

**2973 active connections openings**

**7 passive connection openings**

**10 failed connection attempts**

**34 connection resets received**

**8 connections established**

**40027 segments received**

**37264 segments send out**

**863 segments retransmited**

**9 bad segments received.**

**331 resets sent**

**Udp:**

**8904 packets received**

**0 packets to unknown port received.**

**0 packet receive errors**

**9012 packets sent**

**IgnoredMulti: 1**

**UdpLite:**

**TcpExt:**

**3 resets received for embryonic SYN_RECV sockets**

**510 TCP sockets finished time wait in fast timer**

**18 packets rejects in established connections because of timestamp**

**830 delayed acks sent**

**1 delayed acks further delayed because of locked socket**

**Quick ack mode was activated 383 times**

**4 packets directly queued to recvmsg prequeue.**

**1765 bytes directly received in process context from prequeue**

**19201 packet headers predicted**

**2 packets header predicted and directly queued to user**

**8970 acknowledgments not containing data payload received**

**4398 predicted acknowledgments**

**13 times recovered from packet loss by selective acknowledgements**

**Detected reordering 1 times using SACK**

**Detected reordering 5 times using time stamp**

**7 congestion windows fully recovered without slow start**

**4 congestion windows partially recovered using Hoe heuristic**

**4 congestion windows recovered without slow start by DSACK**

**10 congestion windows recovered without slow start after partial ack**

**15 fast retransmits**

**1 forward retransmits**

**147 other TCP timeouts**

**TCPLossProbes: 160**

**TCPLossProbeRecovery: 1**

**383 DSACKs sent for old packets**

**1 DSACKs sent for out of order packets**

**153 DSACKs received**

**2116 connections reset due to unexpected data**

**13 connections reset due to early user close**

**10 connections aborted due to timeout**

**TCPDSACKIgnoredNoUndo: 13**

**TCPSpuriousRTOs: 1**

**TCPSackShiftFallback: 70**

**TCPDeferAcceptDrop: 3**

**TCPRcvCoalesce: 5429**

**TCPOFOQueue: 828**

**TCPOFOMerge: 1**

**TCPChallengeACK: 9**

**TCPSYNChallenge: 9**

**TCPAutoCorking: 59**

**TCPSynRetrans: 613**

**TCPOrigDataSent: 13057**

**TCPHystartDelayDetect: 5**

**TCPHystartDelayCwnd: 165**

**TCPACKSkippedPAWS: 1**

**TCPKeepAlive: 2672**

**IpExt:**

**InMcastPkts: 139**

**OutMcastPkts: 127**

**InBcastPkts: 73**

**OutBcastPkts: 71**

**InOctets: 22142893**

**OutOctets: 8259509**

**InMcastOctets: 32803**

**OutMcastOctets: 32639**

**InBcastOctets: 11053**

**OutBcastOctets: 10419**

**InNoECTPkts: 51041**

- --------------------------------------------------------------------------------------------------------------------

### Nome do serviço com PID

Mostrando o nome do serviço com seu número PID, usando a opção **netstat -tp** exibirá "PID / Nome do Programa".

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831614/0-02.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831614/0-02.png)

### Mostrando Transações de Interface de Rede

Mostrando transações de pacotes de interface de rede, incluindo pacotes de transferência e recebimento com tamanho MTU.

**netstat -i**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831615/0-03.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831615/0-03.png)

### Encontrando Programas que estão usando portas

Descubra quantos programas de escuta em execução em uma porta.

Ex: quem está usando **http**.

**netstat -ap | grep http**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831617/0-04.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831617/0-04.png)

### Gerenciando Redes Externas

**Scan de Hostname ou IP**

**nmap gavinho.net.br**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831619/0-05.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831619/0-05.png)

Este servidor que hospeda gavinho.net.br está com as portas que interessam para meu site abertas. Algumas podem estar, mas estão escondidas.

Agora vamos ver o mesmo comando contra meu próprio servidor:

**nmap 127.0.0.1**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831628/0-06.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/1/6/831628/0-06.png)

Como tenho serviços de e-mail, DNS, impressão (CUPS) e banco de dados MS SQL-Server, apareceram as portas correspondentes: **25, 53, 631 e 1433/1434** respectivamente.

### Scan de uma rede

Exemplo pegando a rede inteira. Não precisa ser a rede local.

**nmap  192.168.0.***

Veja como ficou no arquivo texto gerado:

- ---------------------------------------------------------------------------------------------------------------------------

Starting Nmap 7.01 (https://nmap.org) at 2017-06-03 13:49 BRT

Nmap scan report for 192.168.0.1

Host is up (0.0042s latency).

Not shown: 990 filtered ports

PORT            STATE  SERVICE

21/tcp   closed ftp

22/tcp   closed ssh

80/tcp   open   http

110/tcp  closed pop3

143/tcp  closed imap

443/tcp  open   https

993/tcp  closed imaps

1723/tcp closed pptp

5900/tcp closed vnc

8080/tcp open   http-proxy

MAC Address: CC:A4:62:E5:18:91 (Arris Group)

Nmap scan report for 192.168.0.9

Host is up (0.0036s latency).

Not shown: 997 filtered ports

PORT STATE SERVICE

135/tcp open  msrpc

139/tcp open  netbios-ssn

445/tcp open  microsoft-ds

MAC Address: 24:0A:64:06:C9:24 (AzureWave Technology)

Nmap scan report for 192.168.0.12

Host is up (0.045s latency).

Not shown: 999 filtered ports

PORT            STATE SERVICE

1688/tcp open  nsjtp-data

MAC Address: C4:E9:84:90:A5:BD (Tp-link Technologies)

Nmap scan report for 192.168.0.5

Host is up (0.0000090s latency).

Not shown: 993 closed ports

PORT            STATE SERVICE

21/tcp   open  ftp

22/tcp   open  ssh

25/tcp   open  smtp

53/tcp   open  domain

80/tcp   open  http

631/tcp  open  ipp

1433/tcp open  ms-sql-s

Nmap done: 4 IP addresses (4 hosts up) scanned in 66.74 seconds

- ---------------------------------------------------------------------------------------------------------------------------

Você pode variar este comando para:

- Todos os seguinte últimos octetos
- **nmap 192.168.0.1,2,3,4,5**
- Todos que estão listados em um arquivo de texto (minhalistadehosts.txt)
- **nmap -iL minhalistadehosts.txt**
- Um range:
- **nmap 192.168.0.1-5**
- Excluindo hosts
- **nmap 192.168.0.1-5 --exclude 192.168.0.4**

### Informações sobre Sistemas Operacionais e Rotas

O comando abaixo é extremamente poderoso. Você pode receber informações importantes para gerenciar uma rede remota.

**nmap  -A gavinho.net.br**

Coloquei o resultado em um arquivo texto e exponho em um print aqui, pois existem muitas informações. Entre elas o Sistema Operacional e a rota completa para chegar no referido servidor. Veja abaixo.

- ---------------------------------------------------------------------------------------------------------------------------

Starting Nmap 7.01 ( https://nmap.org ) at 2017-06-03 13:16 BRT

Nmap scan report for gavinho.net.br (185.28.21.151)

Host is up (0.16s latency).

Not shown: 996 filtered ports

PORT            STATE  SERVICE  VERSION

20/tcp   closed ftp-data

21/tcp   open   ftp    Pure-FTPd

80/tcp   open   http Apache httpd

|_http-server-header: Apache

|_http-title: Site doesn't have a title (text/html; charset=iso-8859-1).

8080/tcp open   http            nginx

|_http-open-proxy: Proxy might be redirecting requests

|_http-server-header: nginx

|_http-title: HTTP OK

Device type: firewall|general purpose|broadband router

Running (JUST GUESSING): Linux 3.X|2.6.X (91%), IPCop 2.X|1.X (91%), D-Link embedded (86%), IPFire 2.X (85%)

OS CPE: cpe:/o:linux:linux_kernel:3.4 cpe:/o:ipcop:ipcop:2 cpe:/o:linux:linux_kernel:2.6.32 cpe:/o:linux:linux_kernel:3.0 cpe:/h:dlink:dsl-2890al cpe:/o:linux:linux_kernel:2.6.25.20 cpe:/o:ipcop:ipcop:1.9.19 cpe:/o:ipfire:ipfire:2.9

Aggressive OS guesses: IPCop 2 firewall (Linux 3.4) (91%), Linux 2.6.32 (87%), IPCop 2.0 (Linux 2.6.32) (87%), Linux 3.0 (87%), D-Link DSL-2890AL ADSL router (86%), OpenWrt Kamikaze 8.09 (Linux 2.6.25.20) (86%), Linux 2.6.36 (86%), IPCop 1.9.19 or IPFire 2.9 firewall (Linux 2.6.32) (85%)

No exact OS matches for host (test conditions non-ideal).

Network Distance: 22 hops

TRACEROUTE (using port 20/tcp)

HOP RTT      ADDRESS

1   8.40 ms   192.168.0.1

2   44.90 ms  10.56.24.1

3   70.28 ms  c9062541.virtua.com.br (201.6.37.65)

4   47.02 ms  c9062825.virtua.com.br (201.6.40.37)

5   49.31 ms  c9062801.virtua.com.br (201.6.40.1)

6   53.64 ms  c9062ad2.virtua.com.br (201.6.42.210)

7   51.41 ms  c9062ad1.virtua.com.br (201.6.42.209)

8   60.28 ms  embratel-T0-4-0-0-uacc04.spoph.embratel.net.br (201.56.189.13)

9   55.96 ms  ebt-T0-13-0-11-tcore01.spo.embratel.net.br (200.230.159.230)

10  139.22 ms ebt-B11551-intl01.atl.embratel.net.br (200.230.230.40)

11  142.59 ms 7-2-4.ear3.Atlanta2.Level3.net (4.14.26.117)

12  ...

13  153.18 ms Charter-level3-250G.Atlanta2.Level3.net (4.35.198.10)

14  ... 18

19  157.51 ms 74.112.174.251

20  ... 21

22  149.69 ms 185.28.21.151

- ---------------------------------------------------------------------------------------------------------------------------

**Encontrar quais hosts estão online na rede**

**nmap -sP 192.168.0.***

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818408/36840.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818408/36840.png)

Fonte:

### Instalação de um Gerenciador de Redes

Vamos instalar o Zabbix, um dos mais respeitáveis gerenciadores de redes para o mundo Linux.

Ubuntu tem Zabbix em seus repositórios, mas está desatualizado. Usaremos um PPA com pacotes mais atualizados.

Edite a lista fonte apt para adicionar o PPA:

**# vim /etc/apt/sources.list**

Digite ou cole as linhas em negrito abaixo:

**# Zabbix Application PPA**

**deb http://ppa.launchpad.net/tbfr/zabbix/ubuntu precise main**

**deb-src http://ppa.launchpad.net/tbfr/zabbix/ubuntu precise main**

Salve e feche o arquivo.

Agora, é preciso incluir o código ou chave de acesso do PPA de forma ao apt-get possa confiar na fonte:

**apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C407E17D5F76A32B**

Agora podemos instalar o Zabbix. Ele também fará a instalação automática dos pacotes LAMP dependentes necessários:

**apt-get update**

**apt-get install zabbix-server-mysql php7.0-mysql zabbix-frontend-php**

No processo de instalação, será pedido uma senha de root do MySQL.

### Configurando o Servidor Zabbix

Em seguida, precisamos configurar os pacotes instalados.

Primeiro, iremos editar o arquivo principal de configuração do servidor Zabbix. Abra o arquivo com privilégios de root:

**vim  /etc/zabbix/zabbix_server.conf**

Procure as propriedades a seguir e defina-as. Entre os parâmetros encontramos aqueles que já está lá e, se não, vamos acrescentar. Escolha uma senha também:

**DBName = zabbix**

**DBUser = zabbix**

**DBPassword = SEU_PASSWORD**

Perceba no print abaixo que no arquivo de configuração mantém o DBPassword comentado. Descomente ele tirando o **“#”.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818410/36841.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818410/36841.png)

Fonte:

Salve e feche o arquivo.

### Configuração do MySQL

Em seguida, entraremos na pasta do pacote e descompactaremos os arquivos SQL que servirão para a importação criando, assim, a nossa estrutura de banco de dados:

**cd /usr/share/zabbix-server-mysql/**

**gunzip * .gz**

É necessário agora usar os arquivos de importação do SQL para o nosso banco de dados. Para isto ter efeito, preciso antes ter a base do MySql preparada, inclusive com o novo banco de dados do zabbix lá dentro, permitindo que estes arquivos da estrutura do zabbix, façam o efeito necessário na criação das tabelas e parâmetros.

Entre no MySQL como usuário root com a senha colocada no processo a instalação:

**mysql -u root -p**

Primeiro, inclua um usuário para o Zabbix que corresponda às informações que inserimos no arquivo "**/etc/zabbix/zabbix_server.conf**". Cuide para trabalhar com as informações corretas:

**use mysql;**

**insert into user (User) values ('zabbix');**

**update user set authentication_string=password('123456’) where user='zabbix’;**

O usuário é o **zabbix,** o password é “123456”**,** pois foi o que eu coloquei na configuração do zabbix.

Em seguida, criaremos o banco de dados Zabbix:

**create database zabbix;**

Dê controle sobre o novo banco de dados para o novo usuário que criamos:

**grant all privileges on zabbix.* to zabbix@localhost;**

A seguinte linha implementar nossas novas permissões:

**flush privileges;**

Agora terminamos com a configuração inicial do MySQL. Sair de volta ao shell:

**exit;**

Agora que temos nossa configuração de banco de dados, podemos importar os arquivos que o Zabbix precisa para funcionar. Digite a senha para o usuário "zabbix" que você configurou quando solicitado:

**mysql -u zabbix -p zabbix < schema.sql**

Faça o mesmo com o arquivo de imagens:

**mysql -u zabbix -p zabbix < images.sql**

E, finalmente, importe o arquivo de dados:

**mysql -u zabbix -p zabbix < data.sql**

### Configuração PHP

Precisamos ajustar alguns valores para o processamento php dos nossos dados de monitoramento. Abra o arquivo de configuração do php:

**vim /etc/php/7.0/apache2/php.ini**

Procure e ajuste as seguintes entradas. Se eles não existem, adicione-os:

**post_max_size = 16M**

**max_execution_time = 300**

**max_input_time = 300**

**date.timezone = UTC**

Salve e feche o arquivo.

Em seguida, copiaremos o arquivo php específico do Zabbix para o diretório de configuração:

**cp /usr/share/doc/zabbix-frontend-php/examples/zabbix.conf.php.example /etc/zabbix/zabbix.conf.php**

Abra o arquivo:

**vim /etc/zabbix/zabbix.conf.php**

Edite os seguintes valores. Use a mesma informação que quando configurou o banco de dados anteriormente:

**$ DB ['DATABASE'] = 'zabbix';**

**$ DB ['USER'] = 'zabbix';**

**$ DB ['PASSWORD'] = '123456’**

Veja como é o arquivo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818412/36842.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818412/36842.png)

Fonte:

Salve e feche o arquivo.

**Prepare o Apache2 para acessar a página do Zabbix.**

**A2enconf alias**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818414/36843.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818414/36843.png)

Fonte:

**a2enconf zabbix.conf**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818415/36845.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818415/36845.png)

Fonte:

**service zabbix-server status**

Veja no print abaixo o status do serviço:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818416/36846.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818416/36846.png)

Fonte:

**Pronto! Server Preparado!**

### Agente Zabbix - Instalação e Configuração

Em seguida, precisamos configurar o agente zabbix que responde para servidor Zabbix. Vou instalar o agente no servidor, que será melhor para os testes.

Primeiro, proceda com a instalação pelos comandos abaixo:

**apt-get update**

**apt-get install zabbix-agent**

Produzir os efeitos necessários nos arquivos de configuração:

**vim  /etc/zabbix/zabbix_agentd.conf**

Edite o parâmetro "**Server**" para coincidir o IP do servidor onde o zabbix será hospedado. Para a definir agente no servidor Zabbix, use o "127.0.0.1", será mais fácil!

**Servier = 127.0.0.1  (já vem assim)**

Ajuste parâmetro "Hostname" para corresponder ao nome do host da máquina que está sendo vista.

**Hostname = LuckyGavNote** (coloquei o nome de meu servidor)

Veja como é o arquivo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818417/36847.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818417/36847.png)

Fonte:

Salve e feche o arquivo.

Reinicie o agente com o comando abaixo:

**service zabbix-agent restart**

Pronto, seu Zabbix está em ordem. Para começar entre em:

[**http://127.0.0.1/zabbix/**](http://127.0.0.1/zabbix/)  no seu browser preferido!

O Usuário é “**admin**” e o password é “**zabbix**”

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818418/36848.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/4/818418/36848.png)

Fonte:

Existem uma infinidade de opções para você monitorar sua rede. O Zabbix é bastante completo, mas você precisa fazer um bom treinamento para usar bem. Como qualquer trabalho profissional que se preste!