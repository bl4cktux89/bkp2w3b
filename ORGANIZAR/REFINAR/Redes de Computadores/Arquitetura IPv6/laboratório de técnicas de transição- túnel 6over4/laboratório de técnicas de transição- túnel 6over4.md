INTRODUÇÃO

Por volta de 30 anos, o endereçamento IPv4 vem sendo utilizado para redes de internet de todo o mundo, tanto corporativas quanto domésticas. Hoje em dia, o protocolo de endereçamento IPv4 está em fase de esgotamento já anunciado dos endereços IPv4, onde mais ou menos em meados dos anos 90 já se sabia que esses endereços iriam acabar, sendo necessário o desenvolvimento do endereçamento IPv6 que surgiu em 1998 para poder suprir a necessidade dos IPs que estavam para se esgotar. Com toda a grandeza da rede mundial, não havia maneira de parar de vez com o protocolo IPv4 e implantar o protocolo IPv6, então foram desenvolvidas técnicas para fazer a “conversação” entre IPv4 e IPv6, desta forma, as empresas conseguiriam mais tempos e gradativamente adequando-se ao novo protocolo de endereçamento.

O IPv4 e o IPv6 não são diretamente compatíveis, pois, o IPv6 foi desenvolvido para substituir o IPv4, onde o protocolo IPv4 trabalha com um tamanho de 32 bits divididos em 4 grupos de 8 bits (4 294.967.296 de endereços possíveis) e o IPv6 possui um tamanho de 128 bits (340 undecilhões de endereços possíveis). Já se sabia que essa mudança teria que ser feita gradativamente, porém, não se sabia que seria tão demorada devido ao atraso tecnológico de alguns países, então foi necessário criar uma solução “temporária” afim de fazer com que ambos os protocolos conversassem em paralelo e com o objetivo de realizar a transição de forma gradual, esse mecanismo é chamado de pilha dupla, ou seja os dispositivos poderiam utilizar o IPV4 e o IPV6 simultaneamente.

A utilização do túnel do túnel se faz necessária quando a aplicação da Pilha Dupla (Dual Stack) não é viável, ou seja quando o sistema operacional ou o dispositivo não suporta a utilização dos dois protocolos em sua configuração. A técnica 6in4 consiste em enviar pacotes IPv6 através de uma rede IPv4, encapsulando os mesmos. Nessa técnica o pacote IPv6 é embutido no pacote IPv4, adaptando o endereço do remetente e destinatário para IPv4, e para a identificação é colocado o tipo 41 no cabeçalho, para que o pacote seja processado de maneira correta. Assim que o pacote chega ao seu destino, ele irá deletar o cabeçalho IPv4 e processar o pacote como um IPv6.

![[Untitled 13.png|Untitled 13.png]]

PILHA DUPLA IPV4/IPV6

Uma das maneiras de  implantação do IPv6 de modo gradativo, está acontecendo nessa fase de transição que o mundo todo está passando, exigindo a adoação de técnicas de transição, sendo o  6over4  uma dessas técnicas, se encaixando na categoria de Tunelamento.

A criação deste túnel é feita de forma manual, o qual é usado pelo 6over4 para encaminhar pacotes IPv6. Existe uma diferença clara entre 6over4 e 6in4. Essa diferença se dá no fato de que o 6over4 é uma técnica para manter uma comunicação entre dois nós IPv6 dentro de uma rede IPv4, utilizando um túnel e a técnica de encapsulamento 6in4. Já o 6in4, pode ser utilizado como uma técnica de transição por várias outras técnicas.

![[Untitled 1 7.png|Untitled 1 7.png]]

Encapsulamento - Transição de IPv4 para IPv6

Quando o uso da pilha dupla não é viável, devido a restrição técnica do adaptador de rede ou ainda do sistema operaciona, é necessário utilizar técnicas de tunelamento IPv6-over-IPv4 (6over4 ou 6in4). Essa técnica faz o encapsulamento de pacotes IPv6 em pacotes IPv4, onde a mesma é conhecida como 6in4, e consiste em alocar o pacote IPv6 dentro do pacote IPv4 ou vice e versa, permitindo assim que haja alterações nos parâmetros de configuração como a capacidade de se adequar o endereço de origem e destino do IPv4 e colocar cabeçalho do tipo 41(29 em hexadecimal), assim, o destino recebe o pacote com tipo 41, remove o cabeçalho IPv4 e tratar o pacote como IPv6.

O túnel do tipo 6over4 pode ser utilizado para conectar 2 dispositivos IPv6 utilizando a internet IPv4 e para “desviar” de um dispositivo na rede que não suporte o IPv6.

A Técnica de pilha dupla consiste em instalar e operacionalizar dois protocolos, o IPv4 e IPv6 nas máquinas da rede e demais dispositivos da infraestrutura, de maneira gradativa, que implica na existência de duas redes em paralelo. Ao fazê-lo, um nó que esteja operando em pilha-dupla, assim, podendo conversar com os nós que estejam operando somente com o IPv4 ou exclusivamente com o IPv6.

Essa tática promove o processo de mudança até que o resultado seja um ambiente operacional totalmente baseado no IPv6.

### SIMULAÇÃO PRATICA 6OVER4

A simulação da técnica de tunelamento 6in4 ou 6over4 será feita através do programa de simulação de topologias de redes desenvolvido pela Cisco Networks chamado de _**Cisco Packet Tracer,**_ e tem como objetivo mostrar o processo de funcionamento da técnica de tunelamento 6in4.

Nesta simulação os seguintes equipamentos foram utilizados: dois roteadores modelo  2911, dois switchs 2960-24TT e quatro computadores.

![[Untitled 2 7.png|Untitled 2 7.png]]

Fonte: http://labcisco.blogspot.com.br/search?q=6over4

**CONFIGURAÇÃO DOS EQUIPAMENTOS**

**Roteador-SP** `1. enable 2. configure terminal 3. hostname Roteador-SP 4. int serial 0/0/0 5. no shut 6. clock rate 500000 7. ip address 203.0.113.1 255.255.255.252 8. interface g0/0 9. ipv6 enable 10. ipv6 address 2001:db8:cafe:1::1/64 11. no shut 12. int tunnel 0 13. ipv6 address fd00:cafe::0/127 14. tunnel source s0/0/0 15. tunnel destination 203.0.113.2 16. tunnel mode ipv6ip 17. exit 18. ipv6 unicast-routing 19. ipv6 route 2001:db8:cafe:2::/64 fd00:cafe::1 20. router ospf 110 21. router-id 1.1.1.1 22. network 203.0.113.1 0.0.0.3 area 0 23. do write`

**Roteador-RJ** `1. enable 2. configure terminal 3. hostname Roteador-RJ 4. interaface serial 0/0/0 5. ip address 203.0.113.2 255.255.255.252 6. no shutdown 7. interface g0/0 8. ipv6 enable 9. ipv6 address 2001:db8:cafe:2::1/64 10. no shut 11. interface tunnel 0 12. ipv6 address fd00:cafe::1/127 13. tunnel source s0/0/0 14. tunnel destination 203.0.113.1 15. tunnel mode ipv6ip 16. exit 17. ipv6 unicast-routing 18. ipv6 route 2001:db8:cafe:1::/64 fd00:cafe::0 19. router ospf 110 20. router-id 1.1.1.1 21. network 203.0.113.2 0.0.0.3 area 0 22. do write 23. ipv6 router ospf 160 24. router-id 1.1.1.1 25. exit 26. interface g0/0 27. ipv6 enable 28. ipv6 ospf 160 area 0 29. ipv6 ospf authentication ipsec spi 500 md5 fd00:cafe::1 30. do write`

As técnicas de transição foram desenvolvidas para que o novo protocolo de endereçamento IPv6 fosse implementado gradualmente, já que seria impossível a sua implantação imediata, devido a complexidade da rede mundial de computadores.

Os protocolos de endereçamento IPv6 e IPv4, uma que não são diretamente compatíveis, pois ambos protocolos IPV4 e IPV6, possuem estrutura e tamanhos diferentes, e as técnicas 6over4, pilha dupla, entre outras, foram desenvolvidas, com a finalidade de que os dois protocolos consigam se comunicar.

Exemplos dessas técnicas são as técnicas de pilha dupla, a técnica de túnel manual (6over4) que foram executadas nesse laboratório prático, além dessa técnica existem outras, onde devemos analisar a topologia da rede e usar a técnica de transição que mais se adequada a topologia e a estrutura de rede.