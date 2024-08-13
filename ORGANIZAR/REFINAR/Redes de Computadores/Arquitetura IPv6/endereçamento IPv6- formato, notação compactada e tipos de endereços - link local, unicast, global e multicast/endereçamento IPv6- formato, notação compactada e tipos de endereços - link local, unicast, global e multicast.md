### Introdução

O IPv6 é a nova geração do Protocolo Internet. Ele já vem sendo utilizado há algum tempo. Mas agora sua implantação deve ser acelerada. Ela é imprescindível para a continuidade docrescimento e da evolução da Internet. Devido ao grande crescimento das tabelas de roteamento e dos usuários espalhados pelo mundo, o IP versão 4 começou a mostrar seu esgotamento. Diante desse cenário, uma solução era preciso tomar, de imediato. Soluções antes considerada paliativas como o CIDR, o DHCP e o NAT começaram também a se esgotarem.

Pensado nisso, o IETF criou, em meados de 1992, o grupo IPng(IP next generation), para desenvolver uma nova versão de IP visando escalabilidade, segurança, configuração e administração de redes, suporte a QoS, mobilidade, políticas de roteamento e transição.

As especificações da IPv6 foram apresentadas inicialmente na RFC 1883 de dezembro de 1995, depois substituída pela RFC 2460.

Principais mudanças:

- Maior capacidade para endereçamento: no IPv6 o espaço para endereçamento aumentou de 32 bits Identificar uma quantidade muito maior de dispositivos na rede; e implementar mecanismos de autoconfiguração;
- A escalabilidade do roteamento multicast também foi melhorada através da adição do campo "escopo" no endereço multicast. E um novo tipo de endereço, o anycast, foi definido;
- Simplificação do formato do cabeçalho: alguns campos do cabeçalho IPv4 foram removidos outornaram-se opcionais, com o intuito de reduzir o custo do processamento dos pacotes nos roteadores.
- Suporte a cabeçalhos de extensão: as opções não fazem mais parte do cabeçalho base, permitindo um roteamento mais eficaz, limites menos rigorosos em relação ao tamanho e a quantidade de opções, e uma maior flexibilidade para a introdução de novas opções no futuro;
- Capacidade de identificar fluxos de dados: foi adicionado um novo recurso que permite identificar de pacotes que pertençam a determinados tráfegos de fluxos, para os quais podem ser requeridos tratamentos especiais;
- Suporte a autenticação e privacidade: foram especificados cabeçalhos de extensão capazes de fornecer mecanismos de autenticação e garantir a integridade e a confidencialidade dos dados transmitidos (SANTOS, 2010).

### Cabeçalho IPV4

O cabeçalho IPv4 é composto por 12 campos fixos, podendo conter ou não opções, fazendo com que seu tamanho possa variar entre 20 e 60 Bytes.

  

![[Untitled 9.png|Untitled 9.png]]

  

Em comparação ao cabeçalho do IPV4, o cabeçalho IPV6 apresentam as seguintes características:

- Mais simples;
- 40 Bytes (tamanho fixo);
- Apenas duas vezes maior que o da versão anterior;
- Mais flexível;
- Extensão por meio de cabeçalhos adicionais;
- Mais eficiente;
- Minimiza o overhead nos cabeçalhos;
- Reduz o custo do processamento dos pacotes.

**Comparação e alterações ocorridas no cabeçalho do IPV4 para o IPV6**

Os endereços IP são identificadores de dispositivos que estão conectados na internet. Estes endereços servem para localizar estes dispositivos e trocar pacotes de dados com os mesmos. Com a chegada do IPv6 a gama de endereços aumentou muito e, para isso foi necessário mudar o formato do endereço perante o formato do seu antecessor.

  

![[Untitled 1 3.png|Untitled 1 3.png]]

  

![[Untitled 2 4.png|Untitled 2 4.png]]

Dentre as principais alterações, destaca-se a remoção de seis campos do cabeçalho IPv4, visto que suas funções não são mais necessárias ou são implementadas pelos cabeçalhos de extensão. Também é possível observar que quatro campos do IPV4 tiveram seus nomes alterados no cabeçalho do IPV6.

  

![[Untitled 3 3.png|Untitled 3 3.png]]

### Endereçamento

De acordo com Santos (2010),comparando a um endereço IPV4, o mesmo possui 32 bits. Já o IPV6 possui 128 bits, podendo ter a seguinte combinação:2128 =340.282.366.920.938.463.463.374.607.431.768.211.45340.282.366.920.938.463.463.374.607.431.768.211.456, ou seja, comparando, temos:? ~ 56 octilhões (5,6x1028) de endereços IP por ser humano.? ~ 79 octilhões (7,9x1028) de vezes a quantidade de endereços IPv4.

A representação dos endereços IPv6, divide o endereço em oito grupos de 16 bits, separando os por “:”, escritos com dígitos hexadecimais.

**2001:0DB8:AD1F:25E2:CADE:CAFE:F0CA:84C1**

Por exemplo, o valor “2001” hexadecimal é representado por 2 bytes (16 bits). Lembre que para cada algarismo hexadecimal, é necessário 4 bits.

Na representação de um endereço IPv6 é permitido:

- Utilizar caracteres maiúsculos ou minúsculos;
- Omitir os zeros à esquerda;
- Representar os zeros contínuos por “::”.

Exemplo:

**2001:0DB8:0000:0000:130F:0000:0000:140B**

**2001:db8:0:0:130f::140b**

Se a seguinte notação for utilizada: **2001:db8::130f::140b**. Ela será inválida, pois gera ambiguidade.

Em endereços IPv6 ela continua, os prefixos continuam sendo escrito do mesmo modo que no IPv4, utilizando a notação CIDR. Esta notação é representada da forma “endereço-IPv6/tamanho do prefixo”, onde “tamanho do prefixo” é um valor decimal que especifica a quantidade de bits contíguos à esquerda do endereço que compreendem o prefixo.

Exemplo:

- Prefixo: 2001:db8:3003:2::/64
- Prefixo global: 2001:db8::/32
- ID da sub-rede: 3003:2

Os endereços IPV6 também podem ser representados em URL´s, utilizando a representação com colchetes, evitando assim ambiguidades. Caso seja necessário, é possível também indicar o número de porta:

- http://[2001:12ff:0:4::22]/index.html
- http://[2001:12ff:0:4::22]:8080

No IPv6 há um aumento considerável no número de bits, passando a ter 128 bits, que ficam dispostos em 8 hexadecatetos (grupos de 16).

Na forma simplificada, cada hexadecateto é convertido em um número hexadecimal que possibilita o uso de caracteres de A a F, sendo eles maiúsculos ou minúsculos e número de 1 a 9. Um exemplo de endereço IP no formato da versão 6: (2791:CAFE:0000:0000:0000:0000:0000:0001), sendo que a simplificação deste endereço é possível quando os zeros em um número hexadecimal se encontram à esquerda.

Quando isso ocorre, basta ocultar os zeros nestas condições. A simplificação do endereço apresentado acima, ficaria da seguinte maneira: (2791:CAFE:0:0:0:0:0:1). Outra forma de abreviar mais ainda o endereço (através da notação compactada), é substituindo uma sequência de zeros por (::), tendo a cautela de não utilizar este método duas vezes no mesmo endereço, pois este ato causaria uma imprecisão no mesmo.

Utilizando o exemplo anterior, o endereço ficaria da seguinte forma: (2791:CAFE::1). Os primeiros 64 bits do endereço localizam a qual rede pertence o destinatário do pacote, com a denominação de Prefixo de rede e os últimos 64 bits: a interface em si, com a denominação de Identificador de interface. Desta forma, com o exemplo utilizado, o endereço da rede seria (2791:CAFE:0:0:) e o da interface (0:0:0:1).

No endereço IPV6, existem 3(três) tipos de endereços fixos:

- Unicast: este tipo de endereço identifica uma única interface, de modo que um pacote enviado a um endereço unicast é entregue a uma única interface;
- Anycast: identifica um conjunto de interfaces. Um pacote encaminhado a um endereço anycast é entregue a interface pertencente a este conjunto mais próxima da origem (de acordo com distância medida pelos protocolos de roteamento). Um endereço anycast é utilizado em comunicações de um-para-um-de-muitos;
- Multicast: também identifica um conjunto de interfaces, entretanto, um pacote enviado a um endereço multicast é entregue a todas as interfaces associadas a esse endereço.
- Um endereço multicast é utilizado em comunicações de um-para-muitos.

**Uma nota muito importante é que no IPV6 NÃO existe mais broadcast.**

### Unicast global

São utilizados para trocar pacotes entre duas interfaces presentes na rede mundial. Os IPs utilizados para este fim são (2000::/3) e (0.0.0.0).

  

![[Untitled 4 3.png|Untitled 4 3.png]]

  

### Anycast

Identifica um conjunto de interfaces. Um pacote encaminhado a um endereço anycast é entregue a interface pertencente a este conjunto mais próxima da origem (de acordo com distância medida pelos protocolos de roteamento). Um endereço anycast é utilizado em comunicações de um-para-um-de-muitos;

  

![[Untitled 5 2.png|Untitled 5 2.png]]

  

![[Untitled 6 2.png|Untitled 6 2.png]]

### Multicast

Os endereços Multicast são aqueles em que uma interface tem a necessidade de enviar pacotes a várias interfaces simultaneamente.

![[Untitled 7 2.png|Untitled 7 2.png]]

### Link Local

Um endereço de link local é um endereço unicast que pode configurado de forma automática ou manual em qualquer interface de um dispositivo. Os endereços de link local começam por FE80 e seus pacotes não são encaminhados para outras redes pelos roteadores. Em uma interface o endereço de link local quando configurado de forma automática reserva 64 bits para a identificação da interface que utiliza o formato IEEE EUI-64 que estudaremos em breve.

![[Untitled 8 2.png|Untitled 8 2.png]]

### Identificadores de interface

De acordo com Santos (2010) os identificadores de interface (IID), utilizados para distinguir as interfaces dentro de um enlace, devem ser únicos dentro do mesmo prefixo de sub-rede.O mesmo IID pode ser usado em múltiplas interfaces em um único nó, porém, elas dever estar associadas a deferentes sub-redes.Normalmente utiliza-se um IID de 64 bits, que pode ser obtido de diversas formas. Ele pode ser configurado manualmente, a partir do mecanismo de autoconfiguração stateless do IPv6, a partir de servidores DHCPv6 (stateful), ou formados a partir de uma chave pública (CGA). Estes métodos serão detalhados no decorrer deste curso. Embora eles possam ser gerados randomicamente e de forma temporária, recomenda-se que o IID seja construído baseado no endereço MAC da interface, no formato EUI-64.

Um IID baseado no formato EUI-64 é criado da seguinte forma:

- Caso a interface possua um endereço MAC de 64 bits (padrão EUI-64), basta complementar o sétimo bit mais a esquerda (chamado de bit U/L – Universal/Local) do endereço MAC, isto é, se for 1, será alterado para 0; se for 0, será alterado para 1. Caso a interface utilize um endereço MAC de 48 bits (padrão IEEE 802), primeiro adiciona-se os dígitos hexadecimais FF-FE entre o terceiro e quarto Byte do endereço MAC (transformando no padrão EUI-64), e em seguida, o bit U/L é complementado. Por exemplo:
    - Se endereço MAC da interface for:
        - 48-1E-C9-21-85-0C
        - adiciona-se os dígitos FF-FE na metade do endereço:
        - 48-1E-C9-FF-FE-21-85-0C
        - complementa-se o bit U/L:
        - 48 = 01001000
        - 01001000 → 01001010
        - 01001010 = 4A
        - IID = 4A-1E-C9-FF-FE-21-85-0C

Um endereço link local atribuído à essa interface seria **FE80::4A1E:C9FF:FE21:850C**.

> [!info] Os endereços IP não são todos iguais - parte 1  
> Vídeo com trilha sonora de fundo, feito em 2014.  
> [https://www.youtube.com/watch?v=jnuHODaLcO8&list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ](https://www.youtube.com/watch?v=jnuHODaLcO8&list=PLQq8-9yVHyOZF5bSWrhUu7aMiwyiAvuhQ)