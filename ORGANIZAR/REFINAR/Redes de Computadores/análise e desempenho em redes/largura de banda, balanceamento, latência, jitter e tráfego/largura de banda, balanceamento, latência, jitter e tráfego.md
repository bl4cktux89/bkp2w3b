### Introdução

No início dos anos 80  as redes existentes eram baseadas na comutação por circuitos.  Comutação por circuitos é caracterizada pela alocação  de um caminho dedicado para comunicação entre duas estações (TANENBAUM, 2003). Este caminho é composto pela concatenação de canais multiplexados nos vários enlaces entre os nós da rede de comunicação, em geral a conexão estabelecida  é full-duplex.  A comutação por circuito tem o potencial de tornar-se ineficiente caso nenhum dado seja transferido no canal alocado à conexão.

O exemplo mais típico da comutação de circuitos é representado pela rede pública de telefonia,  rede esta concebida para transporte do sinal de voz. Deve ser destacado que a comutação por circuitos é a solução adequada no transporte de tráfego como a voz, em função da componente temporal associado ao dado. Na medida em que a comutação por circuito aloca recursos dedicados ao canal não há risco de que a informação de voz se degrade em função, por exemplo, de atrasos ou variações do atraso imprevisíveis. O grande atrativo da comutação por circuitos é o fato que, após o seu estabelecimento, tem-se uma ligação direta entre as estações.

Com a evolução tecnológica as redes por comutação de pacotes avançaram e hoje são as mais usuais, chamadas redes baseadas no protocolo IP (TANENBAUM, 2003). Uma característica básica das redes por pacotes é os canais estabelicidos por duas estações, que podem percorrer caminhos (rotas) diferentes dentro da rede até alcançarem o destino comum (KUROSE,2006). Gerando em muitos casos delay, jitter, sendo assim os conceitos abordados a seguir são importantes para conhecermos melhor o funcionamento da rede e o comportamento de suas aplicações.

Como explicado no inicio, hoje mesmo as redes telefônicas que eram predominantemente baseadas em comutação por circuitos,  hoje são transmitidas em redes por pacotes .

### **Largura de Banda**

Largura de banda, ou bandwidth, é a medida da capacidade de transmissão de um meio físico, conexão ou rede, determinando a velocidade que os dados passam através desta rede específica; é medida em bits, e não em bytes, que determina a medida de capacidade de determinado meio de transmissão por certa unidade de tempo, para Menascé (2002) a correta determinação da capacidade dos links de acesso é fundamental para um correto planejamento de capacidade.

Todas as medidas de largura de banda são, basicamente, feitas em bits por segundo (Kbits/s ou Mbits/s) e em alguns casos, também é relacionada à faixa de frequências, por exemplo, na medida de largura de banda para sinais analógicos.

Fazendo analogia para comparar a um cano de água: se temos muita água para passar pelo cano e o cano for fino, o tempo para a quantidade de água passar será muito grande. Se trocarmos o cano fino por um cano grosso, vai levar muito menos tempo para toda a água passar, ou seja, temos uma limitação da quantidade de água que flui pelo cano por determinada unidade de tempo necessário a este processo.

Um item importante da largura de banda é o throughput, que se refere à largura de banda real medida, em uma hora do dia específica, usando específicas rotas de internet, e durante atransmissão de um conjunto específico de dados na rede. Alguns fatores que determinam esse itemsão:

- Dispositivos de interconexão.
- Tipos de dados sendo transferidos.
- Topologias de rede.
- Número de usuários na rede.
- Computador do usuário.
- Computador servidor.

### Importante lembrar !!!

O desempenho da rede pode ser medido de duas formas:

1. **Vazão (throughput**), utiliza como unidade de medida o bits por segundo.
2. **Latência ou atraso** medida em unidades de tempo, segundos.

A vazão é a taxa de bits efetivamente transportada.

Largura de banda é a máxima taxa de bits que um meio físico pode transmitir em uma unidade de tempo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/0/6/300667/18795.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/0/6/300667/18795.png)

Balanceadores de carga

### Balanceamento.

Quando colocamos as aplicações de uma empresa na internet, devemos saber que alguns problemas podem acontecer, como os de desempenho, incluindo tempos de resposta baixos, congestionamento da rede e interrupção dos serviços, que pode ser causada por sobrecarga normal do sistema ou por ataques de hackers. A solução mais utilizada para minimizar ou resolver esses problemas é o balanceamento de carga, que consiste em dividir a quantidade de trabalho que um computador tem para fazer entre dois ou mais computadores para que mais operações sejam feitas na mesma quantidade de tempo.

O balanceamento de carga pode também ser descrito como o processo de distribuição de solicitações de serviço por um grupo de servidores. Isso resolve uma série de exigências que se têm tornado cada vez mais importantes nas redes, relacionadas a continuidade de negócio ABNT (2013), vejamos:

1. **Escalabilidade**: quando muitas aplicações de conteúdo intensivo crescem para além do ponto em que um único servidor pode fornecer poder de processamento adequado, é cada vez mais importante para ter a flexibilidade de adicionar mais servidores de forma rápida e transparente aos utilizadores finais.
2. **Alto desempenho:** o melhor desempenho é alcançado quando o poder de processamento dos servidores é usado de forma inteligente. Uma infraestrutura avançada de balanceamento de carga pode direcionar as solicitações de serviço ao utilizador final para os servidores que estão menos ocupadas e, portanto, capazes de fornecer o tempo de resposta mais baixo.
3. **Alta disponibilidade e recuperação de desastres:** mais um item importante no balanceamento de carga é a sua capacidade de melhorar a disponibilidade das aplicações. Se uma aplicação ou servidor falha, o balanceamento de carga pode, automaticamente, redistribuir as solicitações de serviço do utilizador final para outros servidores dentro de um cluster de servidores ou para servidores em outro ponto.

### Latência - _Delay_ e _Jitter_

Todos os pacotes da rede sofrem a mesma experiência segundo Kurose (2006), algum atraso entre o momento em que o pacote é enviado a primeira vez e quando chega ao seu destino, esse atraso chamamos de _**delay**_ **ou latência.**

Latência é a medida de tempo para um pacote (ou mensagem) caminhar de uma fonte até um destino.

- Tempo de ida e volta - _round trip time_ - RTT.

O atraso de tempo entre o momento que um evento iniciou e o momento que os efeitos se iniciam. A palavra deriva do fato que, durante o período de latência, os efeitos do evento estão latentes, ou seja, potenciais ou não ainda observados. O significado de latência pode variar dependendo do domínio do problema.

Quando é importante obter uma maior precisão, a latência de ida para um enlace pode ser definida de forma mais restrita, como o tempo do início da transmissão do pacote até o tempo doinício do recebimento do pacote. O tempo do início da recepção do pacote até o fim da recepção do pacote é medido separadamente e denominado atraso de transmissão. Esta definição de latência é independente da vazão do enlace e do tamanho do pacote e é o menor atraso absoluto possível com aquele enlace. Entretanto, em uma rede não trivial, um pacote típico é passado adiante por muitos enlaces através de diversos roteadores, cada um não inicia a passagem adiante de um pacote até recebê-lo completamente. Em tais redes, a latência mínima é a soma da latência mínima de cada enlace com o atraso de transmissão de cada enlace com exceção do último e mais a latência de passagem adiante de cada roteador.

Podemos equacionar a latência, segundo Kurose (2006) como sendo a soma de:

1. **Atrasos de fila,** tempo de espera para chegar a sua vez de ser transmitido, relativo ao processamento nso servidores, ou dispositivos de redes na buferização dos pacotes.
2. **Atrasos de transmissão**, ou seja, tempo de transmissão relativo a vazão do enlace.
3. **Atraso de propagação**, tempo para um pacote propagar de uma fonte até um destino, relativo a velocidade de propagação no meio físico em questão, (ar, fibra ótica, metálico).

### _Jitter_

_**Jitter**_ é a variação no _**delay**_ entre pacotes consecutivos, por isso às vezes é chamado de "variação do _**delay**_."

Esclarecendo, temos _**jitter**_, quando pacotes consecutivos experimentam diferentes tempos de atraso. Em uma rede de pacotes, com componentes de atraso variável, sempre ocorrerá o _**jitter**_. Normalmente, os aplicativos toleram alguma instabilidade e não se degradam. No entanto aplicações, como VoIP ou Vídeo conferencia, requerem que os pacotes sejam transmitidos de uma forma consistente e uniforme, manter o mesmo espaçamento de tempo (_**delay**_) entre eles.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258859/14792.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258859/14792.jpg)

Efeito do delay e Jitter em transmissão de vídeo

### Tráfego.

Quando falamos de tráfego na web, temos que levar em conta alguns aspectos, como o fato de os dados serem transmitidos aleatoriamente, com taxas de pico superiores às taxas médias. Uma característica desse comportamento é que o gerenciamento de websites tem dificuldades para dimensionar a capacidade e a largura de banda do servidor a fim de dar suporte à demanda criada pelos picos de carga, com isso, é notória a degradação no desempenho dos serviços.

**DICAS!!!**

Quando falamos em tamanho de arquivos, sempre utilizamos bytes, lembrando 1 byte possui 8 bits, sendo assim para obtermos o valor de bits, devemos multiplicar por 8.

Outro ponto interessante, que muitas pessoas acabam errando é que quando falamos em tamanho de arquivos sempre utilizamos a quantidade decimal equivalente em bits, ou seja, 1 Kbyte, não são 1000bytes, mas o equivalente binário 1024 bytes. A tabela abaixo ajuda a compreensão:

![[Screenshot_from_2022-03-21_21-23-41.png]]

Quando falamos em velocidades de links, sempre será em bits por segundo - bps, a velocidade realmente é em decimal, a tabela abaixo ajuda a compreensão:

![[Screenshot_from_2022-03-21_21-24-19.png]]

### Aplicando na prática

**Exemplo 1.**

Vamos analisar um cenário para podermos entender melhor os itens citados. Imagine que uma empresa possui um website de publicações eletrônicas que está dimensionando a capacidade do link. Com base nos logs de acesso, observou-se que a média diária é de um milhão de operações HTTP por dia e o tamanho médio de cada operação foi de 10Kbytes. Com base nessas informações, vamos calcular qual largura de banda é necessária:

**1 000 000/ (24x60x60) x (10x2****10****x8) = 948Kbps**

Nesse caso, deve-se calcular o número de operações HTTP por segundo. Em seguida, multiplica-se o tamanho em bytes por 8 para obtermos os bits. Com isso, tem-se o valor aproximado; no nosso caso, uma largura de banda de 1Mbps atenderia a nossa demanda.

**Exemplo 2.**

Calcular a latência na transferência de um arquivo de 1 MBytes  num enlace de fibra óptica com velocidade  de 10Mbps a uma distância de 5000 m, considerar a velocidade de propagação da  luz em fibra sendo 2x108 m/s.

Ignorando fila de espera e atraso de processamento no nó, teremos apenas que calcular a latência na transmissão e a latência na propagação.

**L****tot** **= L****trans** **+ L****prop**

**Latência na transmissão: (1x2****10****x2****10****x8)/10x10****6****= 0.839s**

**Latência na propagação: 5000/2x10****8****= 0.025ms**

**Latência Total = 0.839s.**