> O principal objetivo desse laboratório é apresentar o funcionamento do protocolo de roteamento BGP em uma rede IPv6. Para tanto, será utilizada a aplicação Quagga, que permite a configuração e utilização de protocolos de roteamento em servidores Linux. Na primeira parte da experiência serão apresentados exemplos de configurações básicas para o funcionamento do protocolo BGP em um cenário composto por roteadores que representaram os Sistemas Autônomos (AS) da Internet, sendo possível observar o estabelecimento das sessões iBGP e eBGP. A segunda parte da experiência apresenta exemplos de configurações relacionadas ao estabelecimento de políticas de roteamento, as quais permitem influenciar o tráfego de entrada e de saída do AS. Para a realização deste exercício será utilizada a topologia descrita no arquivo: 5-02-BGP.imn.Santos, Moreiras (2015)

**COMO OBTER OU TER ACESSO AO LIVRO LABORATÓRIO DE IPV6: APRENDA NA PRÁTICA USANDO UM EMULADOR DE REDES DO NICBR**

Este laboratório faz parte do livro Aprenda na prática usando um emulador de redes do NicBr.

Para a realização deste exercício será utilizada a topologia descrita no arquivo: 5-02-BGP.imn. que está disponível no site do NicBR, gratuitamente.

Siga os procedimentos indicados e vamos praticar !

Para saber mais, acesse faça o Download das máquinas virtuais e do livro em http://ipv6.br/pagina/livro-ipv6/

Ou ainda disponível, na versão física, em uma das Bibliotecas dos Campis da Universidade Uninove ! Confira !Venha nos visitar !

### Introdução

Uma das principais características da internet é sua capacidade de resiliência, resistindo a falhas em seu sistema de comunicação, essa capacidade, se deve ao fato de que existem, caminhos e rotas alternativas entre a origem e o destino das informações. Graças a sua arquitetura descentralizada, interligada por diversas redes, a infraestrutura é capaz de encaminhar os pacotes por caminhos alternativos. As redes interligadas, que fazem parte da internet, são chamadas de Sistemas Autônomos ou AS (Autonomous Systems). Estas redes podem ser formadas por provedores de trânsito, usuários finais, redes de conteúdo ou provedores de serviços. Os ASs utilizam identificadores que são números chamados de ASN (Autonomous System Number), de 16 ou 32 bits que servem para identificá-los. Santos, Moreiras (2015).

### BGP (Border Gateway Protocol)

O BGP (Border Gateway Protocol – protocolo de roteamento de gateway exterior) é o protocolo tradicionalmente utilizado entre sistemas autônomos de roteamento. É necessário um protocolo diferente entre SAs, porque os objetivos de um protocolo de gateway interior e os de um protocolo de gateway exterior não são os mesmos. Tudo o que um protocolo de gateway interior precisa fazer é movimentar pacotes da forma mais eficiente possível, da origem até o destino. Ele não precisa se preocupar com política. Já os protocolos de borda externa precisam se preocupar e muito.Em geral, as políticas são configuradas manualmente em cada roteador BGP (ou incluídas com a utilização de algum tipo de script). Elas não fazem parte do protocolo em si.Do ponto de vista de um roteador BGP, o mundo consiste em SAs e nas linhas que os conectam. Dois SAs são considerados conectados se existe uma linha entre roteadores de borda de cada um deles.O BGP é fundamentalmente um protocolo de vetor de distância, mas é bem diferente da maioria dos outros, como o RIP. Em vez de apenas manter o custo para cada destino, cada roteador BGP tem controle de qual caminho está sendo usado.Da mesma forma, em vez de fornecer periodicamente a cada vizinho seu custo estimado para cada destino possível, o roteador BGP informa a seus vizinhos o caminho exato que está usando (TANENBAUM, 2006).

VIDEO - COMO FUNCIONA A INTERNET NICBR

O BGP (Border Gateway Protocol), é o protocolo utilizado na Internet, reponsável pelo roteamento dos pacotes e rotas entre os AS´s. Conhecidos como EGPs (Exterior Gateway Protocol) que anunciam e trocam rotas entre os AS´s. A RFC que define seu funcionamento é a RFC 4271, esse protocolo é do tipo path vector, que faz a melhor escolha entre caminhos, possui como vantagem a alta capacidade de escalabilidade e diversos atributos responsáveis pela política de roteamento. O roteamento entre AS´s é feito através das extensões do BGP, conhecido como Multiprotocolo do BGP ou MP-BGP. Essa extensão foi definida com o objetivo de torná-lo flexível e capaz de carregar as informações de diversos protocolos de roteamento, por exemplo: o IPv6, IPX entre outros protocolos da camada de rede. A extensão é exigida a fim de realizar o roteamento externo IPv6, uma vez que não há versão BGP para essa finalidade. Santos, Moreiras (2015).

A expressão autônoma, representa a natureza do sistema da internet, indicando que um AS possui autonomia para definir suas rotas e políticas de roteamento, estabelecendo e influenciando a forma como o tráfego originado da Internet chega e sai da rede local com destino a outras redes na Internet.

Uma importante definição de tráfego da internet são as políticas de roteamento, que se dividem em políticas de entrada (in) e políticas de saída (out), uma vez que são baseadas nas informações de roteamento trocadas entre os ASs da Internet, ou seja, nos prefixos anunciados e recebidos pelo Sistema Autônomo. Santos, Moreiras (2015)

As políticas (AS-IN), também conhecidas como políticas de entrada, são políticas aplicadas e aprendidas sobre as informações de outros ASs e influenciam diretamente o tráfego de saída do sistema Autônomo, já as políticas (AS-OUT), também chamadas de políticas de saída, são utilizadas de acordo com as informações de roteamento que um AS divulga para a Internet, influenciando o tráfego de entrada do Sistema Autônomo. Santos, Moreiras (2015).

A Figura 5.11 ilustra este fluxo entre as trocas de informações de roteamento e sua influência na direção do tráfego.

![[Untitled 22.png|Untitled 22.png]]

### Roteiro experimental

1. Inicie o CORE e abra o arquivo 5-02-BGP.imn localizado no diretório lab, dentro do Desktop. A topologia de rede, representada pela Figura 5.12, deve aparecer.

![[Untitled 1 14.png|Untitled 1 14.png]]

2. Inicialize a simulação, verifique a configuração de endereços IPv6 e IPv4 nos nós n1Router, n2Router, n3Router, n4Router, n5Router, n6Host, n7Host e n8Host.

3. Verifique a conectividade entre os dispositivos da rede:

(a) Acesse o terminal da máquina n6Host com um duplo-clique e digite o seguinte comando:

# ping6 -c 4 2001:db8:1000:1::20

O resultado do comando é representado pela Figura 5.13.

![[Untitled 2 12.png|Untitled 2 12.png]]

A comunicação entre n6Host, do AS64504, e n8Host, do AS64501, não pode ser estabelecida porque estes dois equipamentos não estão diretamente conectados, dependendo da comunicação entre os roteadores das redes para que haja conectividade. No entanto, não há protocolos de roteamento dinâmico ou rotas estáticas configurados nos roteadores do AS64504.

(b) Abra o terminal do roteador n4Router e digite o seguinte comando:

# ip -6 route show

O resultado do comando é representado pela Figura 5.14.Este comando mostra todas as redes conhecidas pelo roteador n4Router. Como é possível observar, ele também só conhece as redes do próprio AS e por isso não consegue alcançar os dispositivos que estão no AS64501.Repita este teste no roteador n5Router e confirme se ele apresenta o mesmo comportamento

![[Untitled 3 7.png|Untitled 3 7.png]]

Para que haja conectividade entre todos os ASs deste cenário, será preciso trabalhar com o protocolo de roteamento BGP. Por meio deste protocolo, os roteadores dos ASs trocam mensagens entre si, divulgando

as melhores rotas que eles conhecem e informando qualquer mudança na conectividade entre as redes.

Neste cenário, os ASs 64502 e 64503 representam provedores de trânsito, ou seja, são as redes contratadas para fornecer acesso à Internet aos outros ASs e divulgar seus prefixos IP às outras redes. Os roteadoresn2Router e n3Router já estão configurados. É preciso agora configurar os equipamentos do AS64504.

4. Inicialmente, configure o protocolo BGP entre os dois roteadores presentes no AS64504. Este tipo de sessão é chamada de iBGP, pois estabelece uma sessão BGP internamente entre roteadores de um mesmo AS. Este procedimento é importante, pois garante que todos os roteadores do AS possuam a mesma versão de tabela de roteamento BGP.(a) Para configurar o BGP será utilizada a aplicação Quagga. Abra o terminal do roteador n4Router e execute os seguintes comandos:

# vtysh# configure terminal# router bgp 64504# bgp router-id 4.4.4.4# neighbor 2001:db8:4000:FFFF::2 remote-as 64504# neighbor 2001:db8:4000:FFFF::2 description iBGP com n5Router# address-family ipv6# neighbor 2001:db8:4000:FFFF::2 activate# neighbor 2001:db8:4000:FFFF::2 next-hop-self# exit# exit# exit# exit# neighbor 2001:db8:4000:FFFF::2 activate# neighbor 2001:db8:4000:FFFF::2 next-hop-self# exit# exit

O resultado dos comandos é representado pela Figura 5.15.

![[Untitled 4 7.png|Untitled 4 7.png]]

Estes comandos realizam as seguintes funções:

vtyshAcessa a interface de configuração do Quagga.configure terminalAcessa o modo de edição do Quagga, interface utilizada para definiras configurações dos protocolos de roteamento.router bgp 64504Indica um processo BGP no AS64504.bgp router-id 4.4.4.4Indica um número de identificação do roteador.neighbor 2001:db8:4000:FFFF::2 remote-as 64504

Especifica o ASN do roteador vizinho.

neighbor 2001:db8:4000:FFFF::2 description iBGP com n5Router

Apresenta algum texto informativo sobre o vizinho. Apesar de não obrigatório, adicionar comentários pode facilitar a detecção de problemas na configuração de sessões BGP.

address-family ipv6Inicia o bloco de comandos específicos de IPv6.neighbor 2001:db8:4000:FFFF::2 activateAtiva o vizinho para a família IPv6.neighbor 2001:db8:4000:FFFF::2 next-hop-selfRepassa aos vizinhos iBGP que o endereço de próximo salto para alcançar as redes que estão sendo anunciadas é o endereço do próprio roteador.(b) Configure também o roteador n5Router. Para isto, abra o terminal do roteador n5Router e digite os seguintes comandos:# vtysh# configure terminal# router bgp 64504# bgp router-id 5.5.5.5# neighbor 2001:db8:4000:FFFF::1 remote-as 64504# neighbor 2001:db8:4000:FFFF::1 description iBGP com n4Router# address-family ipv6# neighbor 2001:db8:4000:FFFF::1 activate# neighbor 2001:db8:4000:FFFF::1 next-hop-self# exit# exit# exit# exitO resultado dos comandos é representado pela Figura 5.16.Os comandos são os mesmos utilizados na configuração do roteador n4Router.

![[Untitled 5 6.png|Untitled 5 6.png]]

(c) Para verificar se as configurações foram feitas corretamente, abra o terminal do roteador n4Router e digite os seguintes comandos:

# vtysh

# show ipv6 bgp summary

# exit

O resultado destes comandos é representado pela Figura 5.17.

Este comando apresenta as informações relacionadas às sessões BGP estabelecidas. Dentre os dados apresentados, há as informações específicas do roteador do AS vizinho como: seu endereço IPv6 (Neighbor); versão do protocolo BGP utilizada por ele (V); número do Sistema Autônomo (AS);

quantidade de mensagens trocadas (MsgRcvd / MsgSent); versão de tabela

(TblVer); se há mensagens nas filas de envio ou recebimento (InQ / OutQ);

há quanto tempo a sessão está estabelecida ou interrompida (Up / Down);

o estado da sessão e o número de prefixos aprendidos (State / PfxRcd).

Repita o mesmo comando no roteador n5Router.

![[Untitled 6 5.png|Untitled 6 5.png]]

5. Em uma sessão iBGP, os roteadores divulgam somente as rotas que aprenderam externamente. Por este motivo no item anterior não havia nenhum prefixo aprendido. Para que o AS64504 conheça as redes de

outros ASs e divulgue o prefixo da sua rede (2001:db8:4000::/48) é preciso estabelecer as sessões eBGP, ou seja, configurar as sessões BGP com os roteadores dos provedores de trânsito.

(a) Abra o terminal do roteador n4Router e digite os comandos:

# vtysh

# configure terminal

# ipv6 route 2001:db8:4000::/48 Null0

# router bgp 64504

# neighbor 2001:db8:2000:1::1 remote-as 64502

# neighbor 2001:db8:2000:1::1 description eBGP com n2Router

# address-family ipv6

# neighbor 2001:db8:2000:1::1 activate

# network 2001:db8:4000::/48

# exit

# exit

# exit

# exit

O resultado será como o representado pela Figura 5.18.

![[Untitled 7 4.png|Untitled 7 4.png]]

Os comandos são os mesmos utilizados para estabelecer uma sessão iBGP, com a diferença de que agora o vizinho pertence a outro AS e foram utilizados os seguintes comandos adicionais:

ipv6 route 2001:db8:4000::/48 Null0Por padrão, o protocolo BGP só divulga rotas que encontram-se na tabela de rotas do roteador. Então, este comando cria uma rota estática para o prefixo que se pretende divulgar apenas para forçar a sua existência na tabela de rotas.network 2001:db8:4000::/48Declara a rede que se pretende divulgar.(b) Para estabelecer a sessão eBGP entre o roteador n5Router e o n3Router, abra o terminal do roteador n5Router e digite os seguintes comandos:# vtysh# configure terminal# ipv6 route 2001:db8:4000::/48 Null0# router bgp 64504# neighbor 2001:db8:3000:1::1 remote-as 64503# neighbor 2001:db8:3000:1::1 description eBGP com n3Router# address-family ipv6

# neighbor 2001:db8:3000:1::1 activate# network 2001:db8:4000::/48# exit# exit# exit# exitO resultado dos comandos é representado pela Figura 5.19.

![[Untitled 8 4.png|Untitled 8 4.png]]

Os comandos são os mesmos utilizados no n4Router apenas alterando as informações relacionadas ao AS64503.

6. Verifique as configurações e o estabelecimento de sessões eBGP.(a) Abra o terminal do roteador n4Router e digite os comandos:# vtysh# show ipv6 bgp summary

O resultado será similar ao representado pela Figura 5.20.

![[Untitled 9 3.png|Untitled 9 3.png]]

É possível observar que, além do vizinho iBGP configurado anteriormente, também é listado o vizinho eBGP; e que ao final do comando são apresentadas as rotas aprendidas destes vizinhos.

(b) Ainda no terminal do roteador n4Router, digite o seguinte comando paraverificar a tabela de rotas:# vtysh# show ipv6 routeO resultado será similar ao representado pela Figura 5.21.As rotas marcadas com a letra B no início da linha são as aprendidas utilizando o protocolo BGP.Repita os mesmos comandos no roteador n5Router e compare os resultados. Você pode utilizar também o comando show ipv6 bgp para ver apenas o que foi aprendido por BGP e quais os caminhos conhecidospara chegar a cada AS.

Santos, Moreiras (2015)

![[Untitled 10 2.png|Untitled 10 2.png]]

7. Por fim, repita o teste de conectividade feito no passo 3 e, a partir da máquina n6Host, execute um ping6 para a máquina n8Host.

(a) Abra o terminal da máquina n6Host e digite o seguinte comando:# ping6 -c 4 2001:db8:1000:1::20O resultado do comando é representado pela Figura 5.22.

![[Untitled 11 2.png|Untitled 11 2.png]]

Com este teste é possível observar que já existe conectividade entre o AS64504 e o AS64503.

Repita o teste a partir da máquina n7Host e veja se também há conectividade com a máquina n8Host. Faça os mesmos testes com o comando traceroute6 e compare os caminhos feitos, analisando os resultados comas rotas conhecidas pelos roteadores n4Router e n5Router.A seguir, com todas as sessões BGP estabelecidas, inicie a segunda parte do experimento aplicando políticas de roteamento de entrada e de saída para o AS64504. Até este ponto, a configuração do protocolo BGP não interfere na rota de destino a nenhuma rede, sendo que o único atributo avaliado para definir o melhor caminho é a quantidade de saltos. O primeiro passo será criar uma política de saída, AS-OUT, e influenciar omodo como o tráfego dos outros ASs chegam até o AS64504.Essa política de saída irá tratar de acesso à Internet fatores: balanceamento do tráfego de entrada e garantir a redundância entre os dois links com os provedores de trânsito. Para isto, atue da seguinte forma:

- Divida o bloco /48 IPv6 em dois prefixos /49 e anuncie cada um deles por um link, isto é, cada /49 será conhecido por apenas um caminho. porém, se neste cenário um dos links ficar indisponível, o /49 anunciado por ele ficará inacessível.
- Para resolver esse problema e ter redundância entre os links, anuncie também o prefixo /48 pelos dois provedores. Com isso, todos os outros ASs conhecerão o /48 pelos dois caminhos.

Como os roteadores dão preferência pelo prefixo mais específico, se os dois links estiverem ativos, os ASs irão preferir os anúncios dos /49, ou seja, o balanceamento estará em operação. Caso um dos links fiqueindisponível, o prefixo /49 divulgado por ele deixará de ser anunciado.No entanto, como esse /49 está contido no /48, mesmo com um dos links desativado, os demais ASes ainda terão a opção do /48 anunciado por meio do outro provedor de trânsito, garantindo assim a redundânciaentre os links.8. Divida o bloco 2001:db8:4000::/48 em dois prefixos /49. Identifique esses dois prefixos:

9. Antes de configurar os roteadores, acesse o roteador do AS64501 apenas para verificar como as rotas do AS64504 são aprendidas por ele. Acesse o roteador n1Router e digite os seguintes comandos:# vtysh# show bgp ipv6 regexp 64504$

O resultado será similar ao representado pela Figura 5.23.

![[Untitled 12 2.png|Untitled 12 2.png]]

Este comando exibe, por meio da utilização de uma expressão regular, todas as rotas conhecidas pelo roteador n1Router cuja origem seja o AS64504. Como se pode observar, o prefixo 2001:db8:4000::/48 é conhecidopor dois caminhos distintos, um por meio do AS64502 (vizinho do roteador n4Router) e outro por meio do AS64503 (vizinho do roteador n5Router).

10. Agora, configure inicialmente as políticas de saída no roteador n4Router, especificando quais prefixos serão anunciados para o AS64502.

(a) O n4Router será configurado para divulgar o /48 e o primeiro prefixo /49. Para isto, abra o terminal do roteador n4Router e digite os seguintes comandos:# vtysh# configure terminal# ipv6 route 2001:db8:4000::/49 Null0# ipv6 prefix-list ANUNCIO-PARA-64502 seq 10 permit 2001:db8:4000::/48# ipv6 prefix-list ANUNCIO-PARA-64502 seq 20 permit 2001:db8:4000::/49# route-map BGP-OUT-64502 permit 10# match ipv6 address prefix-list ANUNCIO-PARA-64502# router bgp 64504# address-family ipv6# network 2001:db8:4000::/49# neighbor 2001:db8:2000:1::1 route-map BGP-OUT-64502 out# exit# exit# exit# clear bgp ipv6 64502 soft out# exitO resultado dos comandos é representado pela Figura 5.24.Estes comandos realizam as seguintes funções:

ipv6 route 2001:db8:4000::/49 Null0

Cria uma rota estática para o prefixo /49 que se pretende divulgar, apenas para forçar a sua existência na tabela de rotas.

ipv6 prefix-list ANUNCIO-PARA-64502 seq 10 permit 2001:db8:4000::/48

Cria uma prefix-list, comando utilizado para listar os prefixos que se pretende tratar. O termo ANUNCIO-PARA-64502 é apenas um nome para identificar a prefix-list. O termo seq 10 indica a ordem em que a prefix-list será executada. Caso haja mais de um prefixo na prefix-list, recomenda-se colocar valores com intervalos grandes entre si, para o caso de se adicionar futuramente novos prefixos intercalados às regras já existentes. O termo permit indica que o prefixo anunciado deve coincidir com os listados na prefix-list. Na sequência, é indicado qual prefixo será analisado. Como pretende-se anunciar pelo roteador n4Router os prefixos 2001:db8:4000::/48 e 2001:db8:4000::/49, foi criada uma prefix-list especificando os dois prefixos.route-map BGP-OUT-64502 permit 10

O comando route-map é utilizado para determinar qual ação será tomada de acordo com as regras especificadas. Com ele é possível descartar ou aceitar anúncios e alterar atributos. O termo BGP-OUT-64502 é apenas um nome para identificar o route-map. O termo permit indica que os prefixos verificados serão aceitos. O valor 10 indica a ordem em que o route-map será executado. Caso haja mais de uma regra noroute-map, recomenda-se colocar valores com intervalos grandes entre si para o caso de se adicionar futuramente novas regras intercaladas às já existentes.

match ipv6 address prefix-list ANUNCIO-PARA-64502

É a regra a ser verificada. Neste caso, está sendo verificado se o anúncioenviado é igual ao especificado na prefix-list ANUNCIO-PARA-64502. Casoo anuncio coincida, ele será divulgado ao vizinho BGP, se não coincidir, o anúncio será automaticamente descartado.neighbor 2001:db8:2000:1::1 route-map BGP-OUT-64502 outAssocia o route-map BGP-OUT-64502 ao vizinho 2001:db8:2000:1::1. O termo out indica que o route-map será aplicado como uma política de saída, tratando apenas os prefixos que serão anunciados ao vizinho2001:db8:2000:1::1.clear bgp ipv6 64502 soft outReenvia a tabela de roteamento ao AS64502. O protocolo BGP só envia todas as rotas conhecidas a um vizinho, quando a sessão é estabelecida. Como a sessão BGP já estava ativa, foi necessárioreenviar todas as informações novamente, mas agora com a política de saída aplicada.Os demais comandos já foram explicados em exemplos anteriores.

![[Untitled 13 2.png|Untitled 13 2.png]]

(b) Para configurar as políticas de saída no roteador n5Router, abra o terminal do roteador n5Router e digite os seguintes comandos:

# vtysh# configure terminal# ipv6 route 2001:db8:4000:8000::/49 Null0# ipv6 prefix-list ANUNCIO-PARA-64503seq 10 permit 2001:db8:4000::/48# ipv6 prefix-list ANUNCIO-PARA-64503seq 20 permit 2001:db8:4000:8000::/49# route-map BGP-OUT-64503 permit 10# match ipv6 address prefix-list ANUNCIO-PARA-64503# router bgp 64504# address-family ipv6# network 2001:db8:4000:8000::/49# neighbor 2001:db8:3000:1::1 route-map BGP-OUT-64503 out# exit# exit# exit

# clear bgp ipv6 64503 soft out# exitO resultado dos comandos é representado pela Figura 5.25.

Santos, Moreiras (2015)

![[Untitled 14 2.png|Untitled 14 2.png]]

Os comandos são os mesmos utilizados no n4Router, com apenas as informações relacionadas ao AS64503 alteradas.

11. Para verificar se os anúncios foram feitos corretamente, acesse o roteador n1Router novamente e visualize as informações de sua tabela de rotas BGP. Para isto, abra o terminal do roteador n1Router e digite o seguinte comando:

# vtysh

# show bgp ipv6 regexp 64504$

O resultado destes comandos será similar ao representado pela Figura 5.26.

![[Untitled 15 2.png|Untitled 15 2.png]]

É possível observar que os dois prefixos /49 estão sendo divulgados, cada um por um caminho distinto. O primeiro /49 é divulgado pelo AS64502 e o segundo bloco /49 é divulgado apenas pelo link conectado ao AS64503.

O prefixo /48 é divulgado pelos dois links simultaneamente.12. Feita a política de saída, o próximo passo é criar uma política de roteamento de entrada. As políticas de entrada são aplicadas sobre os anúncios aprendidos dos outros ASs e, teoricamente, é possível criar uma política e influenciar individualmente a tomada de decisão de roteamento para cada prefixo da Internet. Neste exercício, a política de entrada será aplicada aos prefixos anunciados pelo AS64501.(a) Inicialmente, verifique como o AS64504 aprendeu os caminhos até as redes do AS64501. Abra o terminal do roteador n4Router e digite o seguinte comando:

# vtysh# show ipv6 route 2001:db8:1000::/48O resultado dos comandos é representado pela Figura 5.27.

![[Untitled 16 2.png|Untitled 16 2.png]]

Este comando mostra as informações existentes na tabela de roteamento sobre a rede 2001:db8:1000::/48. É possível observar que o caminho para chegar até ela é através do AS64502, utilizando a interface eth1.

(b) Outra forma de verificar o caminho até o AS64501 é utilizando o comando traceroute6. Abra o terminal da máquina n6Host e execute o seguinte comando:# traceroute6 2001:db8:1000:1::20O resultado do comando é representado pela Figura 5.28.

![[Untitled 17 2.png|Untitled 17 2.png]]

Este comando traça o caminho do n6Host até o n8Host, localizado no AS64501. É possível observar que caminho até ele passa pelos roteadores n4Router, n3Router e n1Router, até chegar ao destino. Este caminho foi o escolhido por ser o caminho mais curto.

(c) Realize os mesmos testes a partir do roteador n5Router e da máquina n7Host. Abra o terminal do roteador n5Router e digite o seguinte comando:# vtysh# show ipv6 route 2001:db8:1000::/48O resultado dos comandos é representado pela Figura 5.29.

![[Untitled 18 2.png|Untitled 18 2.png]]

Assim como no teste feito no roteador n4Router, este comando mostra as informações existentes na tabela de roteamento sobre a rede 2001:db8:1000::/48. É possível observar que, a partir do roteador n5Router,

o caminho para chegar até ela é através do AS64503, utilizando a interface eth1.(d) Faça o teste com o comando traceroute6 a partir da máquina n7Host. Para tanto, abra o terminal da máquina n7Host e execute o seguinte comando:# traceroute6 2001:db8:1000:1::20O resultado do comando é representado pela Figura 5.30.

![[Untitled 19 2.png|Untitled 19 2.png]]

Como visto anteriormente, este comando traça o caminho do n7Host até o n8Host. É possível observar que, neste caso, o caminho até o n8Host passa pelos roteadores n5Router, n3Router e n1Router até chegar ao destino. Este caminho foi o escolhido por ser o mais curto.

(e) Configure a política de entrada de modo que o tráfego da rede até o AS64501 passe exclusivamente pelo roteador n4Router, aumentando a preferência por este caminho, independente deste ser o melhor ou o pior

caminho. Para tanto, abra o terminal do roteador n4Router e execute os seguintes comandos:

# vtysh

# configure terminal

# ipv6 prefix-list PREFIXO-DO-64501

seq 10 permit 2001:db8:1000::/48

# ip as-path access-list ORIGEM-NO-AS64501 permit 64501$

# route-map BGP-IN-64502 permit 10

# match as-path ORIGEM-NO-AS64501

# match ipv6 address prefix-list PREFIXO-DO-64501

# set local-preference 150

# router bgp 64504

# address-family ipv6

# neighbor 2001:db8:2000:1::1 route-map BGP-IN-64502 in

# exit

# exit

# exit

# clear bgp ipv6 64502 soft in

# exit

O resultado dos comandos é representado pela Figura 5.31.

![[Untitled 20 2.png|Untitled 20 2.png]]

Estes comandos verificam se o anúncio recebido é do prefixo 2001:db8:1000::/48 e se a origem deste anúncio foi o AS64501. Caso estas duas condições sejam preenchidas, aumenta-se o valor do atributo

local-preference. Os comandos possuem as seguintes funções:

ipv6 prefix-list PREFIXO-DO-64501 seq 10 permit 2001:db8:1000::/48

Nesta prefix-list indica-se que será analisado apenas o anúncio do prefixo 2001:db8:1000::/48.

ip as-path access-list ORIGEM-NO-AS64501 permit 64501$

Este comando cria, por meio de expressão regular, regras que analisam o as-path, ou seja, analisam o caminho para chegar a uma determinada rede. Neste exemplo, a expressão regular é validada se a origem doanúncio é o AS64501.

route-map BGP-IN-64502 permit 10

O comando route-map é utilizado para determinar qual ação será tomada, de acordo com as regras especificadas. Neste caso, se o anúncio recebido coincidir com as duas regras, ele será aceito e o valor do atributo local-preference será alterado para 150.

match as-path ORIGEM-NO-AS64501A primeira regra a ser verificada é se o anúncio recebido tem origem no AS64501, como definido no as-path ORIGEM-NO-AS64501.match ipv6 address prefix-list PREFIXO-DO-64501A segunda regra analisada verifica se o anúncio recebido é o do prefixo2001:db8:1000::/48, como definido na prefix-list PREFIXO-DO-64501.set local-preference 150Altera o valor do atributo local-preference para 150, caso as condições especificadas sejam validadas. O valor padrão do atributo local-preference é igual a 100 e, quanto maior o valor, maior a preferência.neighbor 2001:db8:2000:1::1 route-map BGP-IN-64502 inAssocia o route-map BGP-IN-64502 ao vizinho 2001:db8:2000:1::1. Otermo in indica que o route-map será aplicado como uma política de entrada, tratando apenas os prefixos recebidos pelo vizinho2001:db8:2000:1::1.clear bgp ipv6 64502 soft inSolicita o reenvio da tabela de roteamento ao AS64502. O protocolo BGP só envia todas as rotas conhecidas a um vizinho, quando a sessão é estabelecida. Como a sessão BGP já estava ativa, foi necessáriosolicitar o reenvio de todas as informações novamente para possibilitar a aplicação da nova política de entrada.Os demais comandos já foram explicados anteriormente.

13. Repita os testes com o comando traceroute6 para verificar se houve alguma mudança no caminho até o AS64501.(a) Abra o terminal da máquina n6Host e execute o seguinte comando:# traceroute6 2001:db8:1000:1::20O resultado do comando é representado pela Figura 5.32.

![[Untitled 21 2.png|Untitled 21 2.png]]

Como foi aumentada a preferência para que o tráfego com destino às redes do AS64501 saísse pelo roteador n4Router e este já era o melhor caminho para estas redes, não houve alteração no caminho do n6Host até o n8Host.

(b) Agora, repita o teste a partir do n7Host. Abra o terminal da máquina n7Host e execute o seguinte comando:# traceroute6 2001:db8:1000:1::20O resultado do comando é representado pela Figura 5.33.

![[Untitled 22 2.png|Untitled 22 2.png]]

Neste caso, comparando com o teste realizado anteriormente, é possível notar que agora, para chegar ao n8Host, o n7Host dá-se um salto a mais, passando pelo roteador n4Router. Isto ocorre porque foi aumentada a preferência do caminho para o AS64501 através do roteador n4Router, aumentando o valor do atributo local-preference.

(c) Acesse o roteador n5Router para verificar se houve alguma alteração em sua tabela de roteamento. Para tanto, abra o terminal do n5Router e execute o seguinte comando:# vtysh# show ipv6 route 2001:db8:1000::/48O resultado dos comandos é representado pela Figura 5.34.

![[Untitled 23.png]]

Veja que agora o caminho escolhido para chegar às redes do AS64501 é passa por n4Router, utilizando a interface eth0, mesmo ele sendo o caminho mais longo. Isto ocorre porque o atributo local-preference tem

um peso maior na escolha do caminho em relação à distância.(d) Verifique também as informações da tabela BGP do roteador n5Router. Ainda no terminal do n5Router, execute o seguinte comando:# vtysh# show bgp ipv6 2001:db8:1000::/48O resultado dos comandos é representado pela Figura 5.35.

![[Untitled 24.png]]

É possível verificar que o roteador n5Router conhece dois caminhos para chegar ao AS64501. Em um deles o valor do atributo local-preference é o valor padrão 100. Na outra opção, o valor do local-preference é 150

tornando essa rota preferencial. Lembre que este valor foi alterado no roteador n4Router e repassado por iBGP ao roteador n5Router.A aplicação de políticas de entrada pode ser utilizada em diversas situações.Neste exercício simplesmente optou-se por enviar os pacotes comdestino ao AS64501 por um único caminho. Esta escolha poderia ter sido justificada pelo fato de um dos links ter maior capacidade, por ser maisbarato, por um ser o link principal e o outro ser um backup, etc.

14. Encerre a simulação.

Santos, Moreiras (2015)