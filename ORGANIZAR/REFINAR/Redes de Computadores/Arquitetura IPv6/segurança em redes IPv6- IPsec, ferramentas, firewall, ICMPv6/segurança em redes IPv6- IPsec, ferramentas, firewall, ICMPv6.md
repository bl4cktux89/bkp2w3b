Esta experiência tem como objetivo de ensinar boas práticas para a configuração de firewalls IPv6, evitando que configurações incorretas atrapalhem o funcionamento do IP. Para tanto, serão seguidas as recomendações da RFC 4890. Também serão alteradas algumas regras deste firewall para entender as consequências de uma configuração de firewall incorreta no funcionamento do IPv6. Este exemplo não faz qualquer tipo de filtro por destinos ou tipos de pacotes que não sejam ICMPv6 e tem por objetivo ser a base para a criação de um firewall que atenda às necessidades da maioria das redes. Para o presente exercício será utilizada a topologia descrita no arquivo: 3-02-firewall-stateful.imn.Santos, Moreiras (2015)

**COMO OBTER OU TER ACESSO AO LIVRO LABORATÓRIO DE IPV6: APRENDA NA PRÁTICA USANDO UM EMULADOR DE REDES DO NICBR**

Este laboratório faz parte do livro Aprenda na prática usando um emulador de redes do NicBr.

Para a realização deste exercício será utilizada a topologia descrita no arquivo: 3-02-firewall-stateful.imn. que está disponível no site do NicBR, gratuitamente.

Siga os procedimentos indicados e vamos praticar !

Para saber mais, acesse faça o Download das máquinas virtuais e do livro em http://ipv6.br/pagina/livro-ipv6/

Ou ainda disponível, na versão física, em uma das Bibliotecas dos Campis da Universidade Uninove ! Confira !Venha nos visitar !

### Introdução teórica

Firewalls são equipamentos de rede ou programas de computador quer meio do bloqueio seletivo de conexões, baseados em uma política de segurança, buscam proteger redes de computadores.Existem dois tipos básicos de firewall:

### Firewall stateful

É um tipo de firewall que guarda o estado das conexões ativas, permitindo apenas a passagem de pacotes que pertençam a essas conexões. Por exemplo, um firewall configurado na rede A permitirá, sem restrições, a passagem de pacotes no sentido da rede A para a rede B. Mas pacotes da rede B para a rede A somente passarão pelo firewall se forem respostas a solicitações feitas pela rede A, descartando os demais pacotes neste sentido.

### Firewall stateless

É um tipo de firewall que não guarda o estado das conexões ativas e a decisão sobre um pacote poder ou não passar pelo firewall é tomada com base em algumas regras. Estas regras podem ser restritivas ou permissivas. Um firewall stateless com regras restritivas bloqueia a passagem de todos os pacotes que estão definidos nas regras. Se o pacote não tiver uma proibição explícita ele passa pelo firewall.Um firewall stateless com regras permissivas tem o comportamento oposto, em que todos os pacotes são bloqueados e somente aqueles que possuem regras permissivas passam pelo firewall.

No firewall IPv4, é bastante comum haver um política de bloquear todos os pacotes ICMPv4. Entretanto esta política não é compatível com o IPv6. O ICMPv6 teve como base o protocolo ICMPv4, porém o ICMPv6 também executa funções que eram exercidas por outros protocolos no IPv4, como o ARP, RARP e IGMP. Esta mudança foi feita com o objetivo de reduzir a quantidade de protocolos utilizados e, assim, aumentar a coerência e facilitar as implementações. No IPv4, os pacotes de ARP, RARP e IGMP não são filtrados por firewall, pois caso fossem, a descoberta de vizinhança não seria possível e as redes não funcionariam. Desta maneira, os mecanismos equivalentes presentes no ICMPv6 não podem ser bloqueados.

(Santos, Moreiras (2015))

### Roteiro experimental

1. Inicie o CORE e abra o arquivo 3-02-firewall-stateful.imn localizado no diretório lab, dentro do Desktop. A topologia de rede, representada pela Figura 3.7, deve aparecer. O objetivo da topologia é representar a estrutura mínima necessária para simular um sistema de firewall. Essa experiência utiliza uma rede interna composta por n1Router, n3Router, n4Host e n5Client e está dividida em duas partes: a configuração de firewall em um servidor ou desktop, seguido da configuração de um firewall em um roteador.

Inicialize a simulação, verifique a configuração de endereços IPv6 em todos os nós e a conectividade entre eles.

3. Configure o firewall em n4Host.

![[Untitled 25.png|Untitled 25.png]]

### (a) Abra um terminal de n4Host com um duplo-clique e verifique o conteúdo do arquivo firewall.sh por meio do comando:

# less firewall.shO arquivo firewall.sh deverá conter as linhas:

#!/bin/bashPATH=/sbin:/bin:/usr/sbin:/usr/binIPTABLES=`which ip6tables`GLOBAL='2001:db8:1dea::abcd/128'INTERNET='2000::/3'start() {

${IPTABLES} -X${IPTABLES} -P INPUT DROP${IPTABLES} -F INPUT${IPTABLES} -P OUTPUT DROP${IPTABLES} -F OUTPUT${IPTABLES} -P FORWARD DROP${IPTABLES} -F FORWARDfor CHAIN in INPUT OUTPUT FORWARD; do# Disable Routing Header Type 0 [RFC5095]${IPTABLES} -A ${CHAIN} -m rt --rt-type 0 -j DROP# Disable transit for some prefixes# 6bone [RFC5156] : 3ffe::/16# BMWG [RFC5180] : 2001:2::/48# ORCHID [RFC4843] : 2001:10::/28# Documentation [RFC3849] : 2001:db8::/32# in real life you need to add doc prefix belowfor TARGET in '-s' '-d'; dofor BLOCKED in '3ffe::/16' '2001:2::/48' '2001:10::/28'; do${IPTABLES} -A ${CHAIN} ${TARGET} ${BLOCKED} -j DROPdonedonedone# Accept All Nodes link-local scope multicast prefix [RFC4291]${IPTABLES} -A INPUT -d ff02::1 -j ACCEPT

# Accept Solicited Node link-local scope# multicast prefix [RFC4291]## Modify the line below -- 1 of 3 ##${IPTABLES} -A INPUT -d ff02::1:ff00:0000/104 -j DROP# Accept local scope ICMPv6 packets from# link-local prefix [RFC4890]for IP in 'fe80::/64'; do# Destination Unreachable [All codes] (Type 1)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \destination-unreachable -d ${IP} -j ACCEPT# Packet Too Big (Type 2)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \packet-too-big -d ${IP} -j ACCEPT# Time Exceeded [Code 0] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-transit -d ${IP} -j ACCEPT# Time Exceeded [Code 1] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-reassembly -d ${IP} -j ACCEPT# Parameter Problem [Code 0] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \bad-header -d ${IP} -j ACCEPT# Parameter Problem [Code 1] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-header-type -d ${IP} -j ACCEPT# Parameter Problem [Code 2] (Type 4)

# Packet Too Big (Type 2)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \packet-too-big -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Time Exceeded [Code 0] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-transit -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Time Exceeded [Code 1] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-reassembly -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Parameter Problem [Code 0] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \bad-header -s ${ALLOCATED} -d ${IP} -j ACCEPT# Parameter Problem [Code 1] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-header-type -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Parameter Problem [Code 2] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-option -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Echo Request (Type 128)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-request -s ${ALLOCATED} -d ${IP} -j ACCEPT# Echo Response (Type 129)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-reply -s ${ALLOCATED} -d ${IP} -j ACCEPT

# Router Solicitation (Type 133)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 133 \-d ${IP} -j ACCEPT# Router Advertisement (Type 134)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 134 \-d ${IP} -j ACCEPT# Neighbor Solicitation (Type 135)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 135 \-d ${IP} -j ACCEPT# Neighbor Advertisement (Type 136)## Modify the line below -- 3 of 3 ##${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 136 \-d ${IP} -j DROP# Inverse Neighbor Discovery Solicitation (Type 141)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 141 \-d ${IP} -j ACCEPT# Inverse Neighbor Discovery Advertisement (Type 142)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 142 \-d ${IP} -j ACCEPT# Listener Query (Type 130)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 130 \-d ${IP} -j ACCEPT# Listener Report (Type 131)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 131 \-d ${IP} -j ACCEPT# Listener Done (Type 132)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 132 \-d ${IP} -j ACCEPT# Listener Report v2 (Type 143)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 143 \-d ${IP} -j ACCEPT# Certification Path Solicitation (Type 148)

${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 148 \-d ${IP} -j ACCEPT# Certification Path Advertisement (Type 149)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 149 \-d ${IP} -j ACCEPT# Multicast Router Advertisement (Type 151)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 151 \-d ${IP} -j ACCEPT# Multicast Router Solicitation (Type 152)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 152 \-d ${IP} -j ACCEPT# Multicast Router Termination (Type 153)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 153 \-d ${IP} -j ACCEPT# traceroute${IPTABLES} -A INPUT -p udp -m udp -s ${ALLOCATED} \-d ${IP} --dport 33434:33523 -m state \--state NEW -j REJECT --reject-with \icmp6-port-unreachable# ssh${IPTABLES} -A INPUT -p tcp -s ${ALLOCATED} \-d ${IP} --dport 22 -j ACCEPT# http${IPTABLES} -A INPUT -p tcp -s ${ALLOCATED} \-d ${IP} --dport 80 -j ACCEPTdonedone

${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-option -d ${IP} -j ACCEPT# Echo Request (Type 128)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-request -d ${IP} -j ACCEPT# Echo Response (Type 129)

# Listener Report v2 (Type 143)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 143 \-d ${IP} -j ACCEPT# Certification Path Solicitation (Type 148)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 148 \-d ${IP} -j ACCEPT# Certification Path Advertisement (Type 149)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 149 \-d ${IP} -j ACCEPT# Multicast Router Advertisement (Type 151)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 151 \-d ${IP} -j ACCEPT# Multicast Router Solicitation (Type 152)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 152 \-d ${IP} -j ACCEPT# Multicast Router Termination (Type 153)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 153 \-d ${IP} -j ACCEPTdonefor IP in ${GLOBAL}; dofor ALLOCATED in ${INTERNET}; do# Accept routable ICMPv6 packets from# allocated prefixes [RFC4890]# Destination Unreachable [All codes] (Type 1)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \destination-unreachable -s ${ALLOCATED} \-d ${IP} -j ACCEPT

stop

;;

try|test)

start

sleep 10

stop

;;

restart|reload|force-reload)

stop

sleep 2

start

;;

status)

status

;;

- )

echo "Usage: ${0} {start|stop|restart|status|try}" >&2

exit 1

;;

esac

exit 0

Santos, Moreiras (2015)

Este script foi escrito com base na RFC 4890. Os três trechos destacados em negrito são regras que derrubam (DROP) mensagens ICMPv6 relacionadas a NS e NA. Nos passos seguintes, será verificado o funcionamento do firewall quando essas messagens são bloqueadas.

(b) Inicialize no terminal de n4Host o serviço de firewall com o comando:

# ./firewall.sh start

O resultado do comando é representado pela Figura 3.8.

![[Untitled 1 15.png|Untitled 1 15.png]]

(c) Verifique a conectividade entre n4Host e n7Client. Ainda no terminal de n4Host, execute os seguintes comandos:

# ip -6 neigh flush dev eth0

# ping6 -c 4 2001:db8:c0de::42

O resultado dos comandos é representado pela Figura 3.9.

Observe que não existe conectividade entre n4Host e n7Client. A seguir, será verificada a causa desse fato.

(d) Ainda no terminal de n4Host, execute o comando:

# ip -6 neigh show

O resultado do comando é representado pela Figura 3.10.

![[Untitled 2 13.png|Untitled 2 13.png]]

Apesar de n4Host estar diretamente conectado ao roteador, não foi possível estabelecer uma conexão IPv6, pois n4Host bloqueou as mensagens ICMPv6 NA, que informam os endereços MAC das máquinas do enlace.Note que ao contrário da prática usual de bloquear mensagens ICMP em IPv4, seu bloqueio em IPv6 impossibilita o funcionamento do protocolo, dado seu papel no mapeamento de endereços das camadas de rede e de enlace.(e) Ainda no terminal de n4Host, edite o arquivo firewall.sh de modo a inserir o trecho em **negrito** e remover o trecho neste formato, alterando as três regras destacadas no passo 3....# Accept Solicited Node link-local scope# multicast prefix [RFC4291]**## Modify the line below -- 1 of 3 ##**${IPTABLES} -A INPUT -d ff02::1:ff00:0000/104 -j DROP **ACCEPT**...# Neighbor Advertisement (Type 136)**## Modify the line below -- 2 of 3 ##**${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 136 \-d ${IP} -j DROP **ACCEPT**# Inverse Neighbor Discovery Solicitation (Type 141)...# Neighbor Advertisement (Type 136)**## Modify the line below -- 3 of 3 ##**${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 136 \-d ${IP} -j DROP **ACCEPT**# Inverse Neighbor Discovery Solicitation (Type 141)...Você poderá utilizar alguns editores de texto disponíveis, p. ex. nano.

(f) Ainda no terminal de n4Host, execute os seguintes comandos:

# ./firewall.sh stop# ./firewall.sh start# ping6 -c 4 2001:db8:c0de::42# ip -6 neigh show

O resultado dos comandos é representado pela Figura 3.11.

![[Untitled 3 8.png|Untitled 3 8.png]]

Observe que ping6 funcionou corretamente. Como exercício adicional, estude as regras habilitadas no firewall e verifique que n4Host está apto a receber somente algumas mensagens relacionadas ao ICMPv6, traceroute6, SSH e HTTP. Referente à sintaxe do script, busque informações relacionadas a ip6tables. Quanto as regras utilizadas, verifique a RFC referenciada na introdução teórica desta experiência.

(g) Abra um terminal de n7Client com um duplo-clique e verifique o acesso ao serviço SSH de n4Host:# ssh ipv6br@2001:db8:1dea::abcdComo é o primeiro acesso de n7Client a n4Host no serviço SSH, será solicitado a inclusão da chave pública RSA de n4Host. Aceite-a respondendo **yes** no terminal. Quando solicitada, a senha de acesso é ipv6br.

O resultado do comando é representado pela Figura 3.12.

Após verificar a conectividade por SSH, encerre a sessão com o comando:

# exit

![[Untitled 4 8.png|Untitled 4 8.png]]

4. Configure o firewall em n1Router.

(a) Abra um terminal de n1Router com um duplo-clique e verifique as regras iniciais do firewall. Utilize o seguinte comando:# ip6tables -L

O resultado do comando é representado pela Figura 3.13.

![[Untitled 5 7.png|Untitled 5 7.png]]

Não há nenhum tipo de restrição, uma vez que as políticas de recebimento (INPUT), envio (OUTPUT) e encaminhamento (FORWARD) estão configuradas para aceite (ACCEPT).

(b) Ainda no terminal de n1Router, verifique o conteúdo do arquivo

firewall.sh:

# less firewall.sh

O arquivo firewall.sh deverá conter as linhas:

#!/bin/bashPATH=/sbin:/bin:/usr/sbin:/usr/binIPTABLES=`which ip6tables`GLOBAL='2001:db8:1dea::1/128 2001:db8::2/128'LAN='2001:db8:1dea::/48 2001:db8::2/127'# IANA aggregated prefixes, according to bcp.nic.brIANA_PREFIXES="2800::/12 2001::/32 2001::/16 2600::/12 2610::/232620::/23 2003::/16 2a00::/12 2400::/12 2c00::/122002::/16"start() {${IPTABLES} -X${IPTABLES} -P INPUT DROP${IPTABLES} -F INPUT${IPTABLES} -P OUTPUT DROP${IPTABLES} -F OUTPUT${IPTABLES} -P FORWARD DROP${IPTABLES} -F FORWARDfor CHAIN in INPUT OUTPUT FORWARD; do# Disable Routing Header Type 0 [RFC5095]${IPTABLES} -A ${CHAIN} -m rt --rt-type 0 -j DROP# Disable transit for some prefixes# 6bone [RFC5156] : 3ffe::/16# BMWG [RFC5180] : 2001:2::/48# ORCHID [RFC4843] : 2001:10::/28# Documentation [RFC3849] : 2001:db8::/32# in real life you need to add doc prefix below

for TARGET in '-s' '-d'; dofor BLOCKED in '3ffe::/16' '2001:2::/48' '2001:10::/28'; do${IPTABLES} -A ${CHAIN} ${TARGET} ${BLOCKED} -j DROPdonedonedone# Accept All Nodes link-local scope multicast prefix [RFC4291]${IPTABLES} -A INPUT -d ff02::1 -j ACCEPT# Accept All Routers link-local scope# multicast prefix [RFC4291]${IPTABLES} -A INPUT -d ff02::2 -j ACCEPT# Accept Solicited Node link-local scope# multicast prefix [RFC4291]${IPTABLES} -A INPUT -d ff02::1:ff00:0000/104 -j ACCEPT# Accept local scope ICMPv6 packets from# link-local prefix [RFC4890]for IP in 'fe80::/64'; do# Destination Unreachable [All codes] (Type 1)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \destination-unreachable -d ${IP} -j ACCEPT# Packet Too Big (Type 2)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \packet-too-big -d ${IP} -j ACCEPT

# Time Exceeded [Code 0] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-transit -d ${IP} -j ACCEPT# Time Exceeded [Code 1] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-reassembly -d ${IP} -j ACCEPT# Parameter Problem [Code 0] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \bad-header -d ${IP} -j ACCEPT# Parameter Problem [Code 1] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-header-type -d ${IP} -j ACCEPT# Parameter Problem [Code 2] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-option -d ${IP} -j ACCEPT# Echo Request (Type 128)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-request -d ${IP} -j ACCEPT# Echo Response (Type 129)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-reply -d ${IP} -j ACCEPT# Router Solicitation (Type 133)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 133 \-d ${IP} -j ACCEPT# Router Advertisement (Type 134)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 134 \-d ${IP} -j ACCEPT# Neighbor Solicitation (Type 135)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 135 \-d ${IP} -j ACCEPT

# Neighbor Advertisement (Type 136)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 136 \-d ${IP} -j ACCEPT# Inverse Neighbor Discovery Solicitation (Type 141)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 141 \-d ${IP} -j ACCEPT# Inverse Neighbor Discovery Advertisement (Type 142)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 142 \-d ${IP} -j ACCEPT# Listener Query (Type 130)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 130 \-d ${IP} -j ACCEPT# Listener Report (Type 131)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 131 \-d ${IP} -j ACCEPT# Listener Done (Type 132)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 132 \-d ${IP} -j ACCEPT# Listener Report v2 (Type 143)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 143 \-d ${IP} -j ACCEPT# Certification Path Solicitation (Type 148)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 148 \-d ${IP} -j ACCEPT# Certification Path Advertisement (Type 149)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 149 \-d ${IP} -j ACCEPT# Multicast Router Advertisement (Type 151)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 151 \-d ${IP} -j ACCEPT# Multicast Router Solicitation (Type 152)

${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 152 \-d ${IP} -j ACCEPT# Multicast Router Termination (Type 153)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 153 \-d ${IP} -j ACCEPTdonefor IP in ${GLOBAL}; dofor ALLOCATED in ${IANA_PREFIXES}; do# Accept routable ICMPv6 packets from# IANA allocated prefixes [RFC4890]# Destination Unreachable [All codes] (Type 1)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \destination-unreachable -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Packet Too Big (Type 2)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \packet-too-big -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Time Exceeded [Code 0] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-transit -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Time Exceeded [Code 1] (Type 3)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \ttl-zero-during-reassembly -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Parameter Problem [Code 0] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \bad-header -s ${ALLOCATED} -d ${IP} -j ACCEPT

# Parameter Problem [Code 1] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-header-type -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Parameter Problem [Code 2] (Type 4)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \unknown-option -s ${ALLOCATED} \-d ${IP} -j ACCEPT# Echo Request (Type 128)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-request -s ${ALLOCATED} -d ${IP} -j ACCEPT# Echo Response (Type 129)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type \echo-reply -s ${ALLOCATED} -d ${IP} -j ACCEPT# Router Solicitation (Type 133)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 133 \-d ${IP} -j ACCEPT# Router Advertisement (Type 134)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 134 \-d ${IP} -j ACCEPT# Neighbor Solicitation (Type 135)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 135 \-d ${IP} -j ACCEPT# Neighbor Advertisement (Type 136)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 136 \-d ${IP} -j ACCEPT# Inverse Neighbor Discovery Solicitation (Type 141)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 141 \-d ${IP} -j ACCEPT

# Inverse Neighbor Discovery Advertisement (Type 142)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 142 \-d ${IP} -j ACCEPT# Listener Query (Type 130)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 130 \-d ${IP} -j ACCEPT# Listener Report (Type 131)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 131 \-d ${IP} -j ACCEPT# Listener Done (Type 132)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 132 \-d ${IP} -j ACCEPT# Listener Report v2 (Type 143)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 143 \-d ${IP} -j ACCEPT# Certification Path Solicitation (Type 148)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 148 \-d ${IP} -j ACCEPT# Certification Path Advertisement (Type 149)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 149 \-d ${IP} -j ACCEPT# Multicast Router Advertisement (Type 151)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 151 \-d ${IP} -j ACCEPT# Multicast Router Solicitation (Type 152)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 152 \-d ${IP} -j ACCEPT# Multicast Router Termination (Type 153)${IPTABLES} -A INPUT -p icmpv6 --icmpv6-type 153 \-d ${IP} -j ACCEPT

# traceroute${IPTABLES} -A INPUT -p udp -m udp -s ${ALLOCATED} \-d ${IP} --dport 33434:33523 -m state \--state NEW -j REJECT --reject-with \icmp6-port-unreachabledonedone# Accept incoming packets from IANA allocated prefixes and# connection state is ESTABLISHED or RELATEDfor ALLOCATED in ${IANA_PREFIXES}; do${IPTABLES} -A INPUT -s ${ALLOCATED} -m state \--state RELATED,ESTABLISHED -j ACCEPTdone# Send packets from ::/128, link-local and# global unicast addressesfor IP in '::/128' 'fe80::/64' ${GLOBAL}; do${IPTABLES} -A OUTPUT -s ${IP} -j ACCEPTdone# Accepted ICMPv6 packets for forwarding [RFC4890]for SOURCE in ${LAN} ${IANA_PREFIXES}; do# Echo Request (Type 128)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type echo-request \-s ${SOURCE} -j ACCEPT# Echo Response (Type 129)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type echo-reply \-s ${SOURCE} -j ACCEPT# Destination Unreachable [All codes] (Type 1)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \destination-unreachable -s ${SOURCE} -j ACCEPT# Packet Too Big (Type 2)## Modify the line below -- 1 of 1 ##

${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \packet-too-big -s ${SOURCE} -j DROP# Time Exceeded [Code 0] (Type 3)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \ttl-zero-during-transit -s ${SOURCE} -j ACCEPT# Time Exceeded [Code 1] (Type 3)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \ttl-zero-during-reassembly -s ${SOURCE} -j ACCEPT# Parameter Problem [Code 0] (Type 4)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \bad-header -s ${SOURCE} -j ACCEPT# Parameter Problem [Code 1] (Type 4)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \unknown-header-type -s ${SOURCE} -j ACCEPT# Parameter Problem [Code 2] (Type 4)${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \unknown-option -s ${SOURCE} -j ACCEPTdone# Forward packets which source address belongs to# internal prefix incoming through eth0 interfacefor INTERNAL in ${LAN}; do${IPTABLES} -A FORWARD -s ${INTERNAL} -i eth0 -j ACCEPTdone# Forward packets which source address belongs to# IANA allocated prefixes incoming through eth1 interface and# connection state is ESTABLISHED or RELATEDfor ALLOCATED in ${IANA_PREFIXES}; do${IPTABLES} -A FORWARD -s ${ALLOCATED} -m state \--state RELATED,ESTABLISHED -i eth1 -j ACCEPTdone# Allow external nodes to traceroute into LANfor INTERNAL in ${LAN}; do# traceroute

${IPTABLES} -A FORWARD -p udp -m udp -d ${INTERNAL} \--dport 33434:33523 -j ACCEPTdone}stop () {echo "Cleaning `basename ${IPTABLES}` rules."${IPTABLES} -P INPUT ACCEPT${IPTABLES} -F INPUT${IPTABLES} -P OUTPUT ACCEPT${IPTABLES} -F OUTPUT${IPTABLES} -P FORWARD ACCEPT${IPTABLES} -F FORWARD}status () {${IPTABLES} --list -v}case "${1}" instart)start;;stop)stop;;

try|test)startsleep 10stop;;restart|reload|force-reload)stopsleep 2start;;status)status;;*)echo "Usage: ${0} {start|stop|restart|status|try}" >&2exit 1;;esacexit 0

Este script também foi escrito com base na RFC 4890 Quando comparado ao mostrado no passo 3, destacam-se a escuta do endereço multicast all-routers e as regras referentes ao encaminhamento (FORWARD) dos pacotes permitidos na rede interna de origem local e global, por meio dos prefixos de rede interna, representados pela constante LAN ( 2001:db8:1dea::/48 e 2001:db8::2/127 ).

(c) Ainda no terminal de n1Router, inicialize o serviço de firewall:# ./firewall.sh start

O resultado do comando é representado pela Figura 3.14.

![[Untitled 6 6.png|Untitled 6 6.png]]

(d) Abra um terminal de n4Host com um duplo-clique e verifique o efeito da regra para derrubar mensagem ICMPv6 tipo 2 (packet too big):

# ping6 -c 4 2001:db8:c0de::42# ping6 -c 4 2001:db8:c0de::42 -s 1400

O resultado do comando é representado pela Figura 3.15.

![[Untitled 7 5.png|Untitled 7 5.png]]

Note que não há nenhum tipo de restrição, uma vez que as políticas de recebimento (INPUT), envio (OUTPUT) e encaminhamento (FORWARD) estão configuradas para aceite (ACCEPT), e que há conectividade entre n4Host e n7Client, como se pode verificar no resultado do primeiro ping6. Já o segundo ping6 foi mal sucedido pois no script de firewall existe uma regra de bloqueio do encaminhamento de pacotes ICMPv6 do tipo packet too big destinados à rede interna. O envio de tal mensagem é relacionado ao PMTUD e o funcionamento do protocolo relacionado pode ser verificado na Experiência 1.10.

(e) Abra um terminal de n7Client com um duplo-clique e verifique o acesso

aos serviços HTTP e SSH de n4Host. Para isto utilize os seguintes comandos:

# wget http://[2001:db8:1dea::abcd]

# tcptraceroute6 -m 5 2001:db8:1dea::abcd 80

# ssh ipv6br@2001:db8:1dea::abcd# tcptraceroute6 -m 5 2001:db8:1dea::abcd 22

O resultado dos comandos é representado pela Figura 3.16.

![[Untitled 8 5.png|Untitled 8 5.png]]

Verificando as regras atribuídas no ip6tables, nota-se que o acesso às portas 80 e 22 de n4Host (2001:db8:1dea::abcd) não está liberado. Nos próximos passos, edite o firewall em n1Router para resolver essa questão.

Modifique também a regra de bloqueio do encaminhamento de pacotes ICMPv6 packet too big.

(f) Abra um terminal de n1Router e edite o arquivo firewall.sh. Insira otrecho em negrito e remova o trecho neste formato:...# Packet Too Big (Type 2)## Modify the line below -- 1 of 1 ##${IPTABLES} -A FORWARD -p icmpv6 --icmpv6-type \packet-too-big -s ${SOURCE} -j DROP ACCEPT# Time Exceeded [Code 0] (Type 3)...# Allow external nodes to traceroute into LANfor INTERNAL in ${LAN}; do# traceroute${IPTABLES} -A FORWARD -p udp -m udp -d ${INTERNAL} \--dport 33434:33523 -j ACCEPTdone# ssh${IPTABLES} -A FORWARD -p tcp -m tcp \-d 2001:db8:1dea::abcd/128 --dport 22 -j ACCEPT# http${IPTABLES} -A FORWARD -p tcp -m tcp \-d 2001:db8:1dea::abcd/128 --dport 80 -j ACCEPT}stop () {...Note que diversas linhas do script foram quebradas através do caractere de barra invertida (\) usado para escape. Ao digitar os comandos em negrito no script, não deve constar nenhum caractere entre a barra invertida e a quebra de linha, inclusive o de espaço em branco.

(g) Ainda no terminal de n1Router, reinicie o serviço de firewall:

# ./firewall.sh stop# ./firewall.sh start

O resultado dos comandos é representado pela Figura 3.17.

![[Untitled 9 4.png|Untitled 9 4.png]]

(h) Abra um terminal de n7Client e verifique o acesso aos serviços HTTP e SSH de n4Host. Execute os comandos:

# wget http://[2001:db8:1dea::abcd]# ssh ipv6br@2001:db8:1dea::abcd

Quando solicitada, a senha de acesso é ipv6br.

O resultado dos comandos é representado pela Figura 3.18.

![[Untitled 10 3.png|Untitled 10 3.png]]

Após verificar a conectividade por HTTP e SSH, encerre a sessão:

# exit5. Os nós n3Router e n5Client, do prefixo 2001:db8:1dea:cafe::/64, apesar de não serem utilizados efetivamente neste experimento, estão com os respectivos scripts de firewall configurados. Note que o nó n5Client é configurado por meio de mensagens RA enviadas por n3Router e que eles apresentam as seguintes características:

n3RouterNó no meio do caminho que não atua como roteador de borda.n5Client

Cliente que utiliza a autoconfiguração stateless de endereços IPv6.

Estude seus scripts e compare com os deste experimento.

6. Encerre a simulação.

Santos, Moreiras (2015)