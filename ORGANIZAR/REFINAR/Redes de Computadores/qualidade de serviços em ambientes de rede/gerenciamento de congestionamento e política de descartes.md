**RED**

Trabalha com um descarte randômico assim que o tamanho da fila atinge um limiar pré-definido. É um mecanismo para gerenciar ativamente as filas, atualmente utilizado na internet. Sua indicação é para redes em que o protocolo de transporte é capaz de responder a indicações de congestionamento na rede. Ele assume que as filas de buffers nos roteadores são formadas por pacotes vindos de diferentes conexões e assume que um único pacote marcado ou descartado é suficiente para indicar a presençade congestionamento para a camada de transporte. Ele tem a capacidade de medir e monitorar o tamanho médio da fila de buffer para cada enlace de saída. Os roteadores deste tipo têm a condição de marcar um pacote fazendo o descarte ou inserindo um bit no cabeçalho da mensagem.

Quando o tamanho de uma fila excede seu limite, o RED entra em ação controlando o tamanho médio da fila mesmo na ausência de um protocolo de transporte cooperativo. Além disso, possui a facilidade de trabalhar com o protocolo de transporte que estiver ativo no momento e também **não** exige sua presença em todos os roteadores daquela rede em questão.

Os algoritmos RED podem marcar os pacotes em espaços intercalados para evitar sincronização global e marcar pacotes com frequência suficiente para controlar o tamanho médio da fila de buffer.

**Como trabalha o RED**

O funcionamento do RED leva vantagem ao utilizar-se do mecanismo de controle de congestionamento do TCP. Através do descarte randômico de pacotes em períodos de grande congestionamento, o RED conta com a origem dos pacotes em que deve ocorrer uma diminuição na sua taxa de transmissão. Como o pacote de origem está usando TCP, a fonte irá diminuir sua taxa de transmissão até que todos os pacotes possam alcançar o seu destino, indicando que o congestionamento não ocorre mais. Na verdade, o TCP não para, totalmente, ele adapta-se rapidamente à taxa de transmissão que a rede pode suportar.

Quando não há pacotes na fila, o RED não tem efeito. Quando a fila alcança o limite, ele começa a descartar os pacotes até baixar a taxa. Isso faz os servidores TCP enviarem mais devagar, aliviando o congestionamento. Se a fila continuar a crescer, o RED começa a descartar mais agressivamente.

**WRED** _**(Weighted Random Early Detection)**_

O algoritmo WRED permite evitar congestionamento nas interfaces de rede fornecendo gerenciamento de buffer e permite que o tráfego TCP seja reduzido antes que os buffers sejam esvaziados. Isso ajuda a evitar derivações residuais e problemas de sincronização global, maximizando, desse modo, a utilização de rede e o desempenho de aplicações com base em TCP.

Ele faz a antecipação de detecção de congestionamento possível e provê múltiplas classes de tráfego. Por causa desses fatores o uso do WRED predomina em qualquer interface de saída na qual é esperada uma ocorrência de congestionamento. O WRED utiliza roteadores intermediários ao invés de utilizar roteadores de borda justamente porque os últimos utilizam a marcação de precedência IP (_**IP-Precedence**_). Com essa marcação, o WRED aproveita para determinar como tratar diferentes tráfegos. O WRED provê limites e pesos separados para diferentes _**IP-Precedence**_, permitindo, assim, prover diferentes qualidades de serviços com descarte de pacotes para diferentes tipos de tráfego.

**Como trabalha o WRED**

O WRED avisa a fonte de pacotes de dados para descrever sua taxa de transmissão toda vez que ocorrem períodos de congestionamento quando os pacotes começam a ser descartados. Se a fonte está utilizando TCP, decrescerá a taxa de transmissão até que todos os pacotes atinjam seu destino, indicando, assim, a ausência de congestionamento. Normalmente, o WRED descarta seus pacotes selecionados a partir do _**IP-Precedence**_, ou seja, quanto maior o _**IP-Precedence**_, menor é a proporção de descarte do pacote. Sendo assim, não sendo uma regra, mas uma lógica, grandes usuários com grandes tráfegos acabam tendo maior chance de descarte de pacotes do que os com pequenos tráfegos na rede. Por trabalhar ligado diretamente ao TCP/IP, se, por ventura, um tráfego **não** for IP, sua precedência será zero, ou seja, menor o _**IP-Precedence**_ e maior a probabilidade do descarte do pacote, ou seja, um tráfego que **não** é IP, será descartado pelo WRED.

> [!important]  
> Fábio Ribas Ardeola é autor de uma tese de mestrado de ciências da computação que descreve em detalhes maiores os processos de gerenciamento de tráfego e política de descarte de pacotes. Recomenda-se sua leitura, disponível em: http://www.lume.ufrgs.br/bitstream/handle/10183/2828/000326612.pdf .