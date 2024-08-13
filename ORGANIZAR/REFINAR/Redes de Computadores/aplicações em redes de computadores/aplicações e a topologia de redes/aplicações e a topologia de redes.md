A camada de aplicação tem a função de criar um ponto de comunicação das aplicações em rede com o usuário final. É efetivamente a utilização de aplicativos como acesso a páginas web (browser), e-mail, redes sociais, comunicação por voz sobre IP, jogos, multimídia entre outros, desta forma, uma aplicação em uma rede é escrever programas que rodem em sistemas finais diferentes e se comuniquem entre si por meio de uma rede de computadores.

Pode-se observar, conforme figura 1, que na camada de aplicação a comunicação entre entidades de software na rede é totalmente transparente para o usuário.

![[img1.png]]

Vale lembrar que uma aplicação de rede consiste em pares de processos que enviam mensagens uns para os outros por meio de uma rede ou mesmo um processo que envia mensagens para a rede e recebe mensagens dela por meio de uma interface de software denominada _**socket**_.

Para identificar o processo receptor, duas informações devem ser especificadas:

- O endereço da estação de trabalho e
- Um identificador que especifica o processo receptor na estação de trabalho de destino.

### Protocolos de camada de aplicação

Em um modelo de comunicação, como a arquitetura TCP/IP, as camadas mais inferiores têm a função de transmitir os dados enviados pela camada de aplicação de maneira confiável, mas não fornecem serviços diretos aos usuários como é o caso da camada de aplicação. Já, esta camada, fornece diretamente estes serviços, sendo assim, a camada de aplicação é ?a razão de ser de uma rede de computadores?. No modelo TCP/IP não há as camadas de sessão e apresentação, que na maioria das aplicações são pouco usadas. Essas duas camadas estão incluídas na camada de aplicação. Vale lembrar que a camada de apresentação trata basicamente funções de criptografia por meio de softwares que rodam nos sistemas finais e a camada de sessão tem a função de estabelecer uma sessão de comunicação, conexão ou reestabelecimento da conexão.

Um protocolo de camada de aplicação define:

- Os tipos de mensagens trocadas.
- A sintaxe dos vários tipos de mensagens, tais como os campos da mensagem e como os campos são delineados.
- A semântica dos campos, isto é, o significado da informação nos campos.
- Regras para determinar quando e como um processo envia mensagens e responde a mensagens.

Na Internet, as aplicações devem "conversar" entre si, ou seja, o que o usuário deseja deve ser entendido pela outra máquina e respondido. Essa comunicação é feita entre os processos, através da troca de mensagens. O remetente cria mensagens com seus pedidos ao destinatário, que recebe e gera as suas mensagens para responder (ou não) a solicitação.

Por exemplo, em uma comunicação Web, o cliente solicita uma página da Internet, através de um determinado tipo de mensagem (no caso, uma requisição HTTP ou http get). O servidor recebe a requisição, e envia uma mensagem com a página para o cliente (através de uma resposta HTTP). Porém, se ocorre um erro, o servidor envia mensagens dizendo ao cliente que ouve algum erro.

Geralmente, a comunicação consiste em pares de processos, onde um processo em cada lado envia mensagens para o outro. Isso ocorre na rede através dos sockets, que são os "porta-vozes" de cada host para uma determinada aplicação.

Para que haja essa comunicação, é necessário que os hosts se identifiquem. Para isso, usam o endereço IP. Porém, é necessário também identificar qual processo naquela máquina irá levar as mensagens à aplicação, e essa identificação é chamada de número (ou endereço) de porta.

### Topologias de rede

O termo topologia de rede, refere-se à disposição física de elementos de rede, meios físicos e outros componentes da rede. A escolha de uma topologia em detrimento de outra resulta em vários fatores que devem ser considerados, como por exemplo:

- Tipo de equipamento utilizado;
- Capacidade e utilização;
- Crescimento da rede;
- Maneira como a rede é gerida;
- Redundância.

A topologia mais simples é a chamada de SPAN ou topologia unindo somente 2 elementos de rede

![[img2.png]]

Outra topologia muito utilizada, principalmente no núcleo da rede ou backbone, é a topologia em Anel

Uma rede em Anel, conforme figura 3, consiste de estações conectadas por meio de um caminho fechado, onde as estações de trabalhos enviam mensagens em um sentido do anel. Nesta configuração, muitas das estações remotas ao Anel não se comunicam diretamente com o computador central.

![[img3.png]]

É possível que as redes em Anel possam receber informações em qualquer direção, mas as configurações mais usuais são unidirecionais, de forma a tornar menos sofisticado os protocolos de comunicação que asseguram a entrega da mensagem corretamente e em sequência ao destino.

Quando uma mensagem é enviada, ela entra no Anel e circula até ser recebida pelo nó destino, ou então até voltar ao nó fonte, dependendo do protocolo empregado. O último procedimento é mais desejável porque permite o envio simultâneo de um pacote para múltiplas estações. Outra vantagem é a de permitir a determinadas estações receber pacotes enviados por qualquer outra estação da rede, independentemente de qual seja o nó destino.

Nas topologias utilizadas hoje em dia, é muito comum utilização de anéis e proteções com tecnologias como SDH, DWDM e OTN.

Esta configuração requer que cada nó seja capaz de remover seletivamente mensagens da rede ou passá-las adiante para o próximo nó. Nas redes unidirecionais, se uma linha entre dois nos cair, todo sistema sai do ar até que o problema seja resolvido. Se a rede for bidirecional, nenhum ficará inacessível, já que poderá ser atingido pelo outro lado.

### Topologia em Barramento

Nesta configuração, conforme figura 4, todos os nós (estações) se ligam ao mesmo meio de transmissão. A barra é geralmente compartilhada em tempo e freqüência, permitindo transmissão de informação.

Nas redes em barramento, cada nó conectado à barra pode ouvir todas as informações transmitidas.

O desempenho de um sistema em barra comum é determinado pelo meio de transmissão, número de nos conectados, controle de acesso, tipo de tráfego entre outros fatores. O tempo de resposta pode ser altamente dependente do protocolo de acesso utilizado.

![[img4.png]]

### Topologia em Estrela

Neste tipo de topologia, conforme figura 5, os usuários se comunicam por meio de um nó central ou hub e permite que as estações trabalhem de forma fisicamente independente.

![[img5.png]]

O arranjo em estrela é a melhor escolha se o padrão de comunicação da rede for de um conjunto de estações secundárias que se comunicam com o no central. As situações onde isto é mais acontece são aquelas em que o no central está restrito às funções de gerente das comunicações e a operações de diagnósticos.

Outras topologias de rede podem ser obtidas, tais como as apresentadas a seguir.

### Multiponto

Nesta modalidade de ligação existe sempre uma estação controladora que coordena o tráfico de dados das demais estações chamadas subordinadas.

Estas redes podem permitir que estações subordinadas se comuniquem entre si diretamente ou apenas através da estação controladora. A diferença entre estes dois modos de envio de mensagens é a complexidade de controle.

### Estruturas Mistas

As estruturas mistas, conforme figura 6, são tipos de redes que utilizam características dos dois tipos básicos de redes, a ligação ponto-a-ponto e multiponto, para obter redes mais complexas e com maiores recursos. As estruturas mistas podem ser do tipo Estrela, Barramento e Anel.

![[img6.png]]

### Topologia Mesh ou malha

É uma topologia que conecta nós de forma que cada ponto do nó passar ser um ponto consumidor, gerador ou de encaminhamento das informações. Na figura 7 cada nó pode ser um roteador que recebe e encaminha as informações para um nó mestre. Um bom exemplo deste tipo de rede ou topologia é o protocolo Zigbee ou 802.15.4.

![[img7.png]]