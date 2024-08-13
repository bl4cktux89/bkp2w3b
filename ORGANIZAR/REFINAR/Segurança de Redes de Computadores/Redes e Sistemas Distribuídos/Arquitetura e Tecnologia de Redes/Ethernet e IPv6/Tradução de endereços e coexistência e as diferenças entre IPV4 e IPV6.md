[![](https://ampli-images.s3.amazonaws.com/production/0ebb7093-c4e3-4855-a3bb-14fb43e45ed5/original)](https://ampli-images.s3.amazonaws.com/production/0ebb7093-c4e3-4855-a3bb-14fb43e45ed5/original)

A comunicação entre _hosts_ que operam em um ambiente onde as duas versões do protocolo IP são utilizadas também pode contar com um protocolo de tradução de endereços, como o _Network Address Translation_ (NAT). Este protocolo implementa um mecanismo de tradução de endereços IPv4 em endereços IPv6 com equivalência de valor.

Como exemplo de tradução de endereço IP, tomaremos o número IPv4 192.168.0.1. Para fazer a conversão do endereço, faça as seguintes etapas:

- Converta o endereço IPv4 para notação binária:

192.168.0.1 = 11000000.10101000.00000000.00000001

- Separe os números binários em grupos de quatro dígitos:

1100 0000 . 1010 1000 . 0000 0000 . 0000 0001

- Utilize as bases 8, 4, 2 e 1 para converter os grupos dos números binários:

1100 = 12 e 0000 = 0

1010 = 10 e 1000 = 8

0000 = 0 e 0000 = 0

0000 = 0 e 0001 = 1

- Converta os números encontrados em cada um dos oito grupos para a notação hexadecimal:

1100 = 12 = C e 0000 = 0 ➔ O primeiro duocteto fica C0.

1010 = 10 = A e 1000 = 8 ➔ O segundo duocteto fica A8.

0000 = 0 e 0000 = 0 ➔ O terceiro duocteto fica 00.

0000 = 0 e 0001 = 1 ➔ O quarto duocteto fica 01.

- Desta forma, o endereço IPv4 192.168.0.1 é representado em IPv6:

C0A8:0001.

- Adicione o 0 nos cinco primeiros grupos de 16 bits, seguido de FFFF:

0:0:0:0:0:FFFF:COA8:0001.

- O IPv6 ainda permite a representação de seu endereço de forma reduzida, abstendo-se de apresentar os endereços com 0:

::FFFF:C0A8:0001.

Com os dispositivos configurados nas redes, os hosts devem ter também um mecanismo para que o roteamento das mensagens ocorra. Os hosts configurados com IPv4/IPv6 possuem suporte aos dois protocolos, não necessitando de técnicas de transição. Já um dispositivo configurado apenas com IPv4 ou IPv6 suportará operações de roteamento somente conforme o protocolo configurado.

Outra técnica adotada para a coexistência e interoperabilidade entre as diferentes versões do IP é o mecanismo de 6to4, o qual permite que redes IPv6 tenham a comunicação entre os roteadores de forma automática. Roteadores 6to4 encaminham os dois endereços (Ipv4 e Ipv6) dos _hosts_, e os dispositivos clientes (_hosts_) devem estar configurados com os endereços IPv4. A Figura 2.34 apresenta uma topologia com exemplo de implementação de mecanismo 6to4.

O tunelamento na rede permite que o IPv4 possa encaminhar pacotes ao IPv6 através de algumas possibilidades:

1. Roteador a roteador: o IPv6 é encapsulado dentro de um pacote IPv4 no início da transmissão.
2. Roteador a _host_: um host com IPv4 envia pacotes a um host IPv6, e o pacote utiliza-se da configuração de Pilha Dupla do roteador para alcançar o _host_ de destino através de um túnel entre o roteador e o _host_ destino.
3. _Host_ a _host_: um host configurado com Pilha Dupla se comunica com outro _host_ em uma rede configurada com o protocolo IPv4 via tunelamento entre os _hosts_.

Outro mecanismo, chamado de _Tunel Broker_, encapsula o pacote IPv6 dentro do pacote IPv4 e permite que seja realizado o roteamento do pacote na rede através de um túnel em redes configuradas como IPv4 e necessidade de interoperabilidade com sites IPv4/IPv6.

A última técnica utilizada para interoperabilidade entre o IPv4 e IPv6 é a _Intra-Site Automatic Tunnel Addressing Protocol (ISATAP)_. Ela possibilita utilizar endereços atribuídos pelo servidor DHCP (_Dynamic Host Configuration Protocol_) com IPv4 para dispositivos com tunelamento de IPv6. Interessante observar que o ISATAP é default para sistemas operacionais Windows. Você pode reconhecer o endereço ISATAP com a utilização do comando _ipconfig_ no _prompt_ de comando. A figura a seguir apresenta um exemplo com topologia de túnel 6to4.

[![](https://ampli-images.s3.amazonaws.com/production/3e3b7236-008d-4403-99b6-520a0dd76cc3/original)](https://ampli-images.s3.amazonaws.com/production/3e3b7236-008d-4403-99b6-520a0dd76cc3/original)

Exemplo de topologia para implementação de técnica de túnel 6to4. Fonte: adaptada de LabCisco.

**Diferenças entre IPV4 e IPV6**

As principais diferenças entre os protocolos IPv4 e IPv6 referem-se ao tamanho do endereço, à quantidade de endereços disponíveis para utilização, à representação do endereço, ao roteamento, à segurança e às questões de qualidade de serviço (Quality of Services – QoS). O quadro abaixo apresenta um comparativo de algumas características entre o endereço IPv4 e IPv6.

[![](https://ampli-images.s3.amazonaws.com/production/8fa8ac39-d10b-4436-8f5e-a439d518cf01/original)](https://ampli-images.s3.amazonaws.com/production/8fa8ac39-d10b-4436-8f5e-a439d518cf01/original)

Comparação entre os protocolos IPv4 e IPv6. Fonte: adaptado de Forouzan (2010).

Segundo Tanenbaum (2011), os administradores de redes e os provedores de internet deverão suportar a interoperabilidade entre os dois protocolos, o IPv4 e o IPv6, por algum tempo ainda, porém esta coexistência deverá trazer alguns problemas de gerenciamento. Alguns deles são:

- Falhas: as redes deverão operar com o IPv4 e com o IPv6.
- Contabilização: recalcular limites de utilização de recursos.
- Configuração: pela necessidade de coexistência entre os protocolos.
- Desempenho: necessidade de adaptações para garantia de performance em serviços.
- Segurança: buscar técnica para garantia da interoperabilidade (coexistência) sem riscos à segurança de sistemas.

As informações técnicas apresentadas suportam a configuração de ambientes de rede de computadores com protocolos IPv4, IPv6 e, principalmente, com a coexistência e interoperabilidade dos dois protocolos no mesmo ambiente.

______

**💭Reflita**

Um endereço IPv4 é composto por quatro blocos de oito bits cada, totalizando 32 bits, o que resulta em uma quantidade de endereços para hosts diretamente interligados à internet de aproximadamente 4.3 bilhões, ou seja, 232 endereços. A sua utilização em redes locais privadas, porém, pode incrementar este número de endereços, por serem redes isoladas da internet, através de seus servidores e controles de atribuição de endereços pelos provedores de serviços de conexão à internet.

Já um endereço IPv6 é composto por oito blocos de 16 bits cada, totalizando 128 bits, o que representa uma quantidade de endereços para _hosts_ diretamente interligados à internet de 340 undecilhões. O número é grande, mesmo considerando previsões de termos mais de 10 trilhões de dispositivos de IoT (_Internet of Things_) interconectados até o ano de 2030, conforme previsto por Diamandis e Kotler (2018).

Qual deverá ser a versão de IP para endereçamento de dispositivos de IoT adequado?