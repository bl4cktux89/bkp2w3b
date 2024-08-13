### Introdução

O NDP (Neighbor Discovery Protocol), em português, Protocolo de descoberta de vizinhança, foi elaborado para evitar conflitos entre interfaces vizinhas em uma rede. Ele é dividido em duas funções fundamentais para o IPv6:

A auto-configuração de interfaces e o encaminhamento de pacotes. A função de auto-configuração de interfaces é dividida em 3 ações distintas:

- Parameter Discovery (permite que a interface extraia informações sobre a rede ou sobre a conexão com a internet),
- Address Autoconfiguration (realiza a auto-configuração em Stateless do nó),
- Duplicate Address Detection (antes de atribuir um endereço a um nó, verifica se este endereço já existe na rede).

Já a função de encaminhamento de pacote, se divide em 6 fases:

- Router Discovery (analisa e detecta roteadores incluídos na rede),
- Prefix Discovery (tem a finalidade de definir se o pacote tem um roteador específico ou um nó como destino),
- Address Resolution (identifica o endereço físico da máquina utilizando o endereço IPv6),
- Neighbor Unreachability Detection (possibilita que o nó verifique a disponibilidade do seu vizinho),
- Redirect (Possibilita que o roteador crie rotas melhores para os pacotes que os nós pretendem enviar e informa elas aos mesmos)
- Next-Hop Determination (Determina o próximo salto a ser feito por um determinado pacote).

![[Untitled 17.png|Untitled 17.png]]

De acordo com o IPV6 (2017 ), funcionamenteo do NDP (Neighbor Discovery Protocol), observa os seguintes passos:

O protocolo de descoberta de vizinhança foi desenvolvido com a finalidade de resolver os problemas de interação entre nós vizinhos em uma rede. Para isso ele atua sobre dois aspectos primordiais na comunicação IPv6, a autoconfiguração de nós e a transmissão de pacotes. No caso da autoconfiguração de nós, o protocolo fornece suporte para a realização de três funcionalidades:

- **Parameter Discovery:** atua na descoberta por um nó de informações sobre o enlace (como MTU) e sobre a Internet(como hop limit).
- **Address Autoconfiguration:** trabalha com a autoconfiguração stateless de endereços nas interfaces de um nó.
- **Duplicate Address Detection:** utilizado para descobrir se o endereço que se deseja atribuir a uma interface já está sendo utilizado por um outro nó na rede.

Já no caso da transmissão de pacotes entre nós, o suporte é dado para a realização de seis funcionalidades:

- **Router Discovery:** trabalha com a descoberta de roteadores pertencentes ao enlace.
- **Prefix Discovery:** implementa a descoberta de prefixos de redes do enlace, cuja a finalidade é decidir para onde os pacotes serão direcionados numa comunicação (se é para um roteador especifico ou direto para um nó do enlace).
- **Address Resolution:** descobre o endereço fisico através de um endereço lógico IPv6.
- **Neighbor Unreachability Detection:** permite que os nós descubram se um vizinho é ou se continua alcançavel, uma vez que problemas podem acontecer tanto nos nós como na rede.
- **Redirect:** permite ao roteador informar ao nó uma rota melhor ao ser utilizada para enviar pacotes a determinado destino.
- **Next-Hop Determination**: algoritmo para mapear um endereço IP de destino em um endereço IP de um vizinho para onde o trafego deve ser enviado.

O NDP foi elaborado com base em mensagens ICMP (Internet Control Message Protocol), utilizando as 5 mensagens seguintes:

- Router Solicitation (ou RS, representada pelo número 133, é uma mensagem que solicita uma resposta “Router Advertisement” dos roteadores, tentando identificar a presença do mesmo na rede para que ele dê as informações das quais o nó necessita).
- Router Advertisement (ou RA, representada pelo número 134, é enviada em determinados espaços de tempo pelo roteador com destino em nós da rede para fornecer informações aos mesmos. Esta mensagem também pode ser concebida como resposta a mensagem Router Solicitation, quando os nós precisam de certas informações entre os espaços de tempo determinados),
- Neighbor Solicitation (ou NS, representada pelo número 135, é enviada a um nó vizinho aguardando uma mensagem Neighbor Advertisement do mesmo. Esta mensagem tem 3 utilidades fundamentais dentro do IPv6: A primeira é aprender um endereço físico ligado a um endereço lógico, informação que será encontrada na mensagem de resposta ao NS; a segunda solicita uma resposta de nós vizinhos, procurando saber se os mesmos estão acessíveis. Para isso uma mensagem NS será enviada ao nó vizinho pretendido com base no endereço lógico do mesmo, aguardando uma resposta de confirmação do mesmo; a terceira forma de uso, tem a finalidade de evitar duplicação de endereços. Sendo assim é enviada uma mensagem contendo o IP pretendido e o questionamento buscando saber se ele já existe ou não),
- Neighbor Advertisement (ou NA, representada pelo número 136, é a mensagem resposta à NS ou uma mensagem espontânea que tem a mesma finalidade dos 3 usos da NS)
- Redirect (representada pelo número 137, envia ao nó que solicitar, uma rota melhor para o encaminhamento de pacotes a um certo destinatário, contendo o endereço do próximo salto pelo qual os pacotes irão passar).

![[Untitled 1 10.png|Untitled 1 10.png]]

Algumas opções extras podem ser associadas à essas mensagens, com o objetivo de torná-las mais eficientes. Entre elas, as mais utilizadas são: Source Link Layer Address (Associa o endereço físico do remetente à mensagem. Usa-se nas mensagens Neighbor Solicitation, Router Solicitation e Router Advertisement), Target Link Layer Address (associa o endereço físico ao destinatário da mensagem, quando solicitado previamente por outra. Usa-se nas mensagens Neighbor Advertisement e Redirect), Prefix Information (Informa ao nó que solicitar, o prefixo de rede ou para que seja realizada a auto-configuração ou a verificação referente ao destinatário de um ou mais pacotes ser do mesmo enlace ou não).

Usa-se nas mensagens Router Advertisement, apenas, MTU (tem como finalidade informar um tamanho de MTU igual e válido a todos nós da rede) e Recursive DNS Server Option (ou RDNSS, dispõe de endereços lógicos de servidores DNS que, quando não tem a informação requerida pelo cliente, busca em outros servidores DNS, ou seja, recursivos).

![[Untitled 2 9.png|Untitled 2 9.png]]

De acordo com STRETCH (2008) o Neighbor Discovery Protocol (NDP) pode ser entedido como uma caixa de ferramentas usada pelos hosts IPv6 para realizar várias operações no link-local. O próprio NDP não descreve um protocolo de nível de camada física ou de estrutura de pacotes, mas sim estabelece instruções para realizar tarefas de rotina usando certos algoritmos e cinco tipos de mensagem ICMPv6.

Muitas funcionalidades fornecidas pelo NDP são muito semelhantes às encontradas no ARP e ICMPv4 do IPv4, enquanto outras são novas implementações disponíveis somente em IPv6. A RFC 4861 descreve as nove funções do NDP em detalhes, outra forma de avaliar as trocas de mensagens, pode ser acompanhada em uma captura de pacotes utilizando o software Wireshark.

### Descoberta do roteador - _Router Discovery_

Enquanto os hosts IPv4 devem contar com configuração manual ou DHCP para fornecer o endereço de um gateway padrão, os hosts IPv6 podem localizar automaticamente roteadores padrão no link. Isso é realizado através do uso de duas mensagens ICMPv6: Solicitação de roteador - _**Router Discovery**_  (tipo 133) e Anuncio do roteador **- Router Advertisement** (tipo 134). Quando o host é adicionado à um link primeira vez, um host IPv6 multiplica uma solicitação de roteador para _**todo**_ o grupo de multicast de _**roteadores**_ e cada roteador ativo no link responde enviando um anuncio de roteador com seu endereço para o grupo de todos os nós(_**all nodes**_ group)_**.**_ STRETCH (2008).

Os anúncios do roteador indicam caminhos fora do link local, mas também especificam informações adicionais necessárias para auxiliar outras operações do NDP.

![[Untitled 3 5.png|Untitled 3 5.png]]

Em seu Blog Packet Life.net, o autor Jeremy Stretch descreve o processo de troca de mensagens NDP conforme abaixo:

### Prefix Discovery - Descoberta de Prefixo

Uma das opções tipicamente carregadas por um anúncio de roteador é a opção **Informações de prefixo** (tipo 3). Cada opção de informação de prefixo lista um prefixo IPv6 (sub-rede) acessível no link local. Lembre-se de que não é incomum que vários prefixos IPv6 residam no mesmo link, e os roteadores podem incluir mais de um prefixo em cada anúncio. Um host que sabe quais prefixos são acessíveis no link pode se comunicar diretamente com os destinos desses prefixos sem passar pelo seu tráfego através de um roteador.

### Parameter Discovery - Descoberta de Parâmetro

Outra opção incluída nas propagandas do roteador é a opção **MTU** (tipo 5), que informa os hosts do IP MTU para usar.Por exemplo, esse valor normalmente é definido como 1500 para redes Ethernet. No entanto, nem todos os tipos de links têm um tamanho MTU padronizado. Incluindo esta opção, garante que todos os hosts conheçam a MTU correta para usar.

Os anúncios do roteador também especificam o valor padrão que os hosts devem usar para a contagem de saltos IPv6.Esta não é uma opção, mas um campo incorporado no cabeçalho da mensagem de anúncio do roteador.

### Address Autoconfiguration - Autoconfiguração de Endereço

O NDP fornece mecanismos para que um host se configure automaticamente com um endereço de um prefixo aprendido de um roteador local através de descoberta de prefixo. Isso é feito concatenando um prefixo aprendido com o endereço EUI-64 da interface do host. Desta forma, um host pode alcançar a autoconfiguração sem estado (_**stateless autoconfiguration**_).

### Address Resolution - Resolução de endereços

A função de resolução de endereço foi tratada pelo ARP para IPv4, mas é tratada pelo ICMPv6 para IPv6. Em um processo muito semelhante à descoberta do roteador, duas mensagens ICMPv6 são usadas: **Solicitação de vizinho**(tipo 135) e **Anuncio de vizinhança** (tipo 136). Um host que procura o endereço da camada de link de um vizinho multiplica uma solicitação de vizinho e o vizinho (se online) responde com seu endereço de camada de link em uma propagação de vizinhança.

![[Untitled 4 5.png|Untitled 4 5.png]]

### Next-Hop Determination - Determinação de próximo salto

Como no IPv4, a determinação do próximo salto é simplesmente um procedimento para realizar pesquisas de maior duração na tabela de roteamento do host e, para destinos inacessíveis, a seleção de um roteador padrão.

### Detecção de vizinho inacessível - Neighbor Unreachability Detection

O NDP é capaz de determinar a acessibilidade de um vizinho examinando pilhas de protocolos de camada superior (por exemplo, confirmações TCP recebidas), ou por ativação da resolução de endereço (via ICMPv6) quando determinados limites são atingidos.

### Detecção de endereço duplicado - _Duplicate Address Detection_

Quando um host acessa pela primeira vez um link, ele faz solicitações de descoberta da vizinhança para o seu _**próprio**_ endereço IPv6 por um curto período antes de tentar usar esse endereço para se comunicar. Se receber uma propagação de vizinhança em resposta, o host percebe que outro vizinho no link já está usando esse endereço. O host marcará o endereço como uma duplicata e não o usará no link.

Observe que esse processo é semelhante aos pedidos ARP do IPv4, mas o NDP permite a detecção de dois hosts com o mesmo endereço _**antes que os**_ dois hosts estejam ativos e enviando tráfego do endereço.

### Redirecionamento - _Redirection_

Um quinto tipo de mensagem ICMPv6, o **Redirecionamento** (tipo 137), é usado por roteadores para apontar hosts em direção a um roteador mais preferido, ou para indicar que o destino realmente reside no link. ICMPv4 fornece a mesma capacidade com sua própria mensagem de redirecionamento.

![[Untitled 5 4.png|Untitled 5 4.png]]

Algumas opções extras podem ser associadas à essas mensagens, com o objetivo de torná-las mais eficientes. Entre elas, as mais utilizadas são: Source Link Layer Address (Associa o endereço físico do remetente à mensagem. Usa-se nas mensagens Neighbor Solicitation, Router Solicitation e Router Advertisement), Target Link Layer Address (associa o endereço físico ao destinatário da mensagem, quando solicitado previamente por outra. Usa-se nas mensagens Neighbor Advertisement e Redirect), Prefix Information (Informa ao nó que solicitar, o prefixo de rede ou para que seja realizada a auto-configuração ou a verificação referente ao destinatário de um ou mais pacotes ser do mesmo enlace ou não).