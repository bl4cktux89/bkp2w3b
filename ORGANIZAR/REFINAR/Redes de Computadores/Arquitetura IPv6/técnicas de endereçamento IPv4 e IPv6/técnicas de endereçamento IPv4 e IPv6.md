### Introdução

### A estrutura do endereço lógico IPV4

Para implementar o endereçamento lógico ou IP foi utilizado um número inteiro com 32 bits, o que a principio permite o endereçamento de 232 equipamentos (próximo de 4 bilhões). Esse endereçamento é representado por meio de quatro conjuntos de 8 bits (octetos), cada um associado a um numero decimal, separados entre si por pontos.

![[Untitled 12.png|Untitled 12.png]]

Considerando-se uma interligação entre redes como uma grande rede.

A diferença é que, nesse caso, a interligação entre redes é uma estrutura virtual, idealizada e totalmente implementada via software. Assim, os projetistas estão livres para determinar formatos e tamanhos de pacotes, endereços, técnicas de entrega e assim por diante.

Para o endereçamento, os projetistas de TCP/IP optaram por um esquema análogo ao endereçamento de rede física, no qual a cada host da interligação é atribuído um endereço com número inteiro de 32 bits, denominando seu endereço IP.

Um detalhe interessante do endereçamento é que os números inteiros são escolhidos cuidadosamente para tornar o roteamento mais eficiente.

Especificamente, um endereço IP codifica a identificação da rede à qual um host se acopla, assim como a identificação de um único host nessa rede.

Resumindo: os bits dos endereços IP para todos os hosts de uma rede compartilham um mesmo prefixo.

[https://www.youtube.com/watch?v=HNQD0qJ0TC4&list=PLQq8-9yVHyOYMFAc9v7Yb_cqmNMksEdrk](https://www.youtube.com/watch?v=HNQD0qJ0TC4&list=PLQq8-9yVHyOYMFAc9v7Yb_cqmNMksEdrk)

[https://www.youtube.com/watch?v=C5qNAT_j63M&list=PLQq8-9yVHyOYMFAc9v7Yb_cqmNMksEdrk&index=2](https://www.youtube.com/watch?v=C5qNAT_j63M&list=PLQq8-9yVHyOYMFAc9v7Yb_cqmNMksEdrk&index=2)

O endereçamento é o meio de identificação e localização de dispositivos que utilizam a internet. E este atributo é designado de forma diferente na versão 4 e na versão 6 do IP. No IPv4 este atributo possui 32 bits divididos em 4 octetos (grupos de 8), e é desta forma que o equipamento o interpreta. Para que este endereço fique simples para a interpretação humana e mais organizado, cada octeto é convertido em um número decimal e os quatro números resultantes desta conversão ficam separados por pontos, como no exemplo a seguir: (192.168.0.1).

Conceitualmente, cada endereço é composto por um par formado pelo endereço de rede (_**netid)**_ e pelo endereço de estação _**(hostid**_) naquela rede.

Dado um endereço IP, seu tipo pode ser determinado a partir de três bits de alta ordem, sendo dois bits suficientes para distinguir entre as três classes principais:

- **Endereços da classe A:** usados por redes grandes, dedicam 1 octeto para netid e 3 octetos para hostid.
- **Endereços da classe B:** usados para redes de tamanho médio, alocam 2 octetos para o netid e 2 octetos para o hostid.
- **Endereços da classe C:** usados para redes pequenas, dedicam 3 octetos para netid e somente 1 octeto para hostid.

O endereço IP foi definido de tal modo que é possível extrair as partes do netid ou do hostid rapidamente. Os roteadores usam a parte do netid de um endereço para decidir qual será o encaminhamento de um pacote.

**Classe A**

A Classe A reserva só o primeiro octeto para endereço de rede (netid), os outros 3 octetos são utilizados para endereçar Hosts (hostid).

No primeiro octeto não pode ser utilizado o 1° bit, convencionado como 0 (zero, bit de ordem superior). Os bits restantes (7 bits) possibilitam uma variação de 0 (zero) a 126 (o valor 127 não é utilizado porque está reservado para aplicações de LoopBack, endereço de teste da pilha TCP/IP).

Posição dos bits: **0nnnnnnn.hhhhhhhh.hhhhhhhh.hhhhhhhh**

Observação: notar que restaram 7 bits para endereçar redes (**n** =network, endereço de rede) e 24 bits para endereçar hosts (**h** = host, endereço de host).

![[Untitled 1 6.png|Untitled 1 6.png]]

Faixa de endereços de rede: de 1.0.0.0 a 126.0.0.0

Faixa de endereços de hosts: de 1.0.0.1 a 126.255.255.254

Máscara de rede padrão: 255.0.0.0

Quantidade de redes: (27- 2) = 126

Retiram-se dois endereços, pois não podem ser utilizados o valor 0.X.X.X e o endereço 127.X.X.X.

Quantidade de Hosts por rede: ( 224 - 2) = 16.777.214

Retiram-se dois endereços, pois não podem ser utilizados o primeiro endereço, convencionado como endereço de rede ou subrede, e o último endereço, convencionado como endereço de Broadcast.

Exemplos de redes: 10.0.0.0, 126.0.0.0, 15.0.0.0, 1.0.0.0, 2.0.0.0, etc.

**Classe B**

Na Classe B são reservados os dois primeiros octetos para endereço de rede e os outros dois octetos são utilizados para endereço de Hosts. No primeiro octeto não podem ser utilizados o 1º bit convencionado como 1 (um) e o 2º bit convencionado como 0 (zero), identificados como bits de ordem superior.

Posição dos bits: **10nnnnnn.nnnnnnnn.hhhhhhhh.hhhhhhhh**

Observação: notar que restaram 14 bits para endereçar redes (n = network, endereço de rede) e 16 bits para endereçar hosts ( h = host, endereço de host).

![[Untitled 2 6.png|Untitled 2 6.png]]

Faixa de endereços de rede: 128.0.0.0 a 191.255.0.0

Faixa de endereços de host: 128.0.0.1 a 191.255.255.254

Quantidade de redes: (214) = 16.384

Observação: IANA (Internet Assigned Number Authority) determina o não uso do 1º e do último endereço, logo (214 - 2) = 16.382.

Quantidade de Hosts por rede: (216 - 2) = 65.534

Retiram-se dois endereços, pois não podem ser utilizados o primeiro endereço, convencionado como endereço de rede ou sub-rede e o ultimo endereço convencionado como endereço de Broadcast.

Exemplos de redes: 168.172.0.0, 136.139.0.0,172.77.0.0, 146.119.0.0

**Classe C**

Na Classe C são reservados os três primeiros octetos para endereço de rede e o octeto restante é utilizado para endereço de Hosts. No primeiro octeto não podem ser utilizados o 1º e 2º bits convencionados como 1 (um), e o 3º bit, convencionado como 0 (zero), identificados como bits de ordem superior.

Posição dos bits: **110nnnnn.nnnnnnnn.nnnnnnnn.hhhhhhhh**

Observação: notar que restaram 21 bits para endereçar redes (n = network, endereço de rede) e 8 bits para endereçar hosts (h = host, endereço de host).

![[Untitled 3 4.png|Untitled 3 4.png]]

Faixa de endereços de rede: 192.0.0.0 a 223.255.255.0

Quantidade de redes: (221) = 2.097.152

Observação: IANA (Internet Assigned Number Authority) determina o não uso do 1º e do último endereço, logo (221 - 2) = 2.097.150.

Faixa de endereços de hosts: 192.0.0.1 à 223.255.255.254

Quantidade de Hosts por rede: 254 => (28 - 2)

Exemplos de redes: 192.10.13.0, 192.168.9.0, 201.225.254.0, 209.20.3.0.

**Classe D – Reservado para aplicações Multicast**

Na classe D são utilizados os quatro octetos para endereçamento. Mas no primeiro octeto não podem ser utilizados o 1º, 2º e 3º bits convencionados como 1 (um) e o 4º bit convencionado como 0 (zero), identificados como bits de ordem superior.

Posição dos bits: **110mmmm.mmmmmmmm.mmmmmmmm.mmmmmmmm**

Faixa de endereços: **224.0.0.0 à 239.255.255**

**Classe E – Reservado para utilização experimental**

Na Classe E são utilizados os quatro octetos para endereçamento. Mas no primeiro octeto não podem ser utilizados os 1º, 2º, 3º e 4º bits convencionados como 1 (um), identificados como bits de ordem superior.

Posição dos bits: **1111rrrr.rrrrrrrr.rrrrrrrr.rrrrrrrr**

Faixa de endereços: **240.0.0.0 em diante**

Reservado: **127.0.0.0** **–** **testes de loopback**

**A estrutura do endereço lógico IPV6**

No IPv6 há um aumento considerável no número de bits, passando a ter 128 bits, que ficam dispostos em 8 hexadecatetos (grupos de 16). Na forma simplificada, cada hexadecateto é convertido em um número hexadecimal que possibilita o uso de caracteres de A a F, sendo eles maiúsculos ou minúsculos e número de 1 a 9. Um exemplo de endereço IP no formato da versão 6: (2791:CAFE:0000:0000:0000:0000:0000:0001), sendo que a simplificação deste endereço é possível quando os zeros em um número hexadecimal se encontram à esquerda. Quando isso ocorre, basta ocultar os zeros nestas condições. A simplificação do endereço mostrado acima fica da seguinte maneira: (2791:CAFE:0:0:0:0:0:1). Outra forma de abreviar mais ainda o endereço, é substituindo uma sequência de zeros por (::), tendo a cautela de não utilizar este método duas vezes no mesmo endereço, pois este ato causaria uma imprecisão no mesmo. Utilizando o exemplo anterior, o endereço ficaria da seguinte forma: (2791:CAFE::1). Os primeiros 64 bits do endereço localizam a qual rede pertence o destinatário do pacote, com a denominação de Prefixo de rede e os últimos 64 bits: a interface em si, com a denominação de Identificador de interface. Desta forma, com o exemplo utilizado, o endereço da rede seria (2791:CAFE:0:0:) e o da interface (0:0:0:1).

No IPv4 não existe um padrão que separe a quantidade de bits que representam a rede e a quantidade que representa a interface.

Para construir o prefixo de uma rede basta identificar o IP da rede que tem o identificador de interface com todos os hexadecimais igual a zero e acrescentar uma barra juntamente com o número de bits que contém o prefixo de rede, por exemplo: (2791:CAFE::/64). No IPv4 é feito desta forma: (192.168.0.0/16).

Com o IPv6, no caso de as redes serem maiores, o prefixo pode ser menor, com a finalidade de se ter mais identificadores de interface disponíveis, como nestes casos: (2791:CAFE::/32) ou (2791:CAFE::/48).

### Endereços Unicast

Os endereços Unicast se encaixam no tipo de situação em que se estabelece uma conexão entre duas interfaces/nós. Existem formas diferentes de endereço Unicast, que são:

![[Untitled 4 4.png|Untitled 4 4.png]]

- Loopback: O endereço Loopback é utilizado para trafegar pacotes dentro de uma interface. Este endereço, em hipótese alguma, estará presente em uma rede. No IPv6, o mesmo é representado pelo IP (::1). Já no IPv4 é representado pelo IP: (127.0.0.0/8) ou simplesmente (127.0.0.1).
- Link Local: São utilizados para trafegar pacotes entre duas interfaces ligadas a uma rede. Um exemplo é a conexão entre um microcomputador e uma impressora. A troca de pacotes limita-se aos dois dispositivos. Para este fim é utilizada a faixa de IP (fe80::/64) no IPv6 e 169.254.0.0/16 no IPv4.
- ULA (Unique Local Address): São utilizados para estabelecer uma rede que não requer acesso à internet, mas sim uma comunicação entre as interfaces nela contidas. As faixas de IP utilizadas para este fim são (fdnn:nnnn:nnnn::/48) no IPv6 onde n são números aleatórios. E as faixas (10.0.0.0), (172.16.0.0) e (192.168.0.0) no IPv4.
- Globais: São utilizados para trocar pacotes entre duas interfaces presentes na rede mundial. Os IPs utilizados para este fim são (2000::/3), no IPv6, (0.0.0.0) e (223.255.255.255), no IPv4. Porém, devido ao esgotamento presente no IPv4, usou-se um meio provisório para se gerar mais endereços para o mesmo, que é através da integração entre o IP Privado e o NAT.
- Documentação: São utilizados teste de configurações, para fins educacionais e/ou para documentos relacionados.

### Endereços Multicast

Os endereços Multicast são aqueles em que uma interface tem a necessidade de enviar pacotes a várias interfaces simultaneamente.

![[Untitled 5 3.png|Untitled 5 3.png]]

Para este fim é usada a faixa (ff00::/8) no IPv6 e a faixa 224.0.0.0/4 no IPv4 (só funciona em determinadas redes). Vale ressaltar que se a função Multicast for desabilitada pelo Firewall enquanto se usa o IPv6, a rede local deixará de reconhecer a respectiva interface.

### Endereços Anycast

Estes endereços são utilizados com o fim de equilibrar a demanda de dados. Neste modelo, vários servidores podem ter o mesmo endereço. Caso haja uma falha em um deles, o outro permanecerá funcionando. Por esse motivo, em grandes empresas e instituições, o serviço em hipótese alguma é interrompido ao usuário. E, dependendo da localização da interface, será atendida por um servidor diferente com o fim de reduzir o tempo de encaminhamento do pacote. Os endereços Anycast não possui faixas específicas de endereçamento.

![[Untitled 6 3.png|Untitled 6 3.png]]

[https://www.youtube.com/watch?v=jnuHODaLcO8](https://www.youtube.com/watch?v=jnuHODaLcO8)

[https://www.youtube.com/watch?v=63M61wttuMk](https://www.youtube.com/watch?v=63M61wttuMk)