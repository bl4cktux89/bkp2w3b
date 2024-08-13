Embora os computadores tenham evoluído no decorrer dos tempos, em tamanho e velocidade, para alguns especialistas das áreas de Engenharia, Ciência e Indústria, entre outras, ela nunca será suficiente.

Podemos ter máquinas que fazem uso do paralelismo para rodar uma única tarefa dividida entre seus processos que serão executados simultaneamente, fazendo com que exista um ganho de velocidade na solução de um problema.

Alguns computadores, em paralelo, são projetados para executar simultaneamente várias tarefas independentes umas das outras, não havendo necessidade de comunicação entre estas tarefas.

Módulos de memória podem ser divididos e operarem independente uns dos outros e em paralelo, permitindo que vários processadores tenham acesso simultâneo às informações armazenadas.

Para enfrentar problemas de diversas naturezas, os arquitetos e/ou projetistas de computadores estão recorrendo cada vez mais a computadores paralelos, para tentar aumentar a potencia computacional cada vez mais.

**NÍVEIS DE PARALELISMO**

**No nível das instruções**:

Pode-se introduzir o paralelismo no **nível das instruções**, na implementação física de um processador, utilizando transistores mais rápidos, ou proporcionando a execução de uma sequencia de instrução de forma mais rápida.

Outra técnica bastante utilizada para alcançar o paralelismo em nível de instruções é o uso de _**pipeline, que**_ tira proveito do fato de que uma instrução de máquina pode ser dividida em uma sequência de etapas intermediárias, aumentando o desempenho do equipamento.

Também pode ser adicionado por meio de palavras longas com paralelismo implícito.

Além disso, características especiais podem ser adicionadas ao processador permitindo que ele manipule diversos Threads de controle ao mesmo tempo.

**PIPELINE**

O processamento em Pipeline trata da divisão de tarefas entre diversas ULA’s, que irão operar sobre a mesma instrução, dividindo-a em várias partes, cada uma tratada por um hardware dedicado exclusivamente.

Dessa forma, todas as partes do computador trabalharão conjuntamente na mesma fase da solução do problema.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/3/294376/18549.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/3/294376/18549.png)

Processamento Pipeline.

Fonte: Figura 12.9 (b) pág. 340 do Livro Sistemas Distribuídos - Princípios e Paradigmas

A premissa é dividir a carga de trabalho, buscando otimizar a utilização de recursos, dentro de um mesmo período de tempo. Com isso, há a melhora do desempenho por meio do aumento do número de instruções executadas e não por meio da diminuição do tempo de execução de uma instrução individual, ele apenas divide o trabalho para otimizar a utilização de recursos dentro de uma mesma unidade de tempo.

Atualmente, é grande o empenho na construção de computadores paralelos, de maneira que eles possam tratar problemas que envolvam uma potência computacional cada vez maior.

**No Nível de Hardware:**

A técnica do paralelismo também pode ser implementada no **nível de hardware**, onde se podem replicar vários processadores (ou parte deles), fazendo com que tudo trabalhe em conjunto e de maneira eficiente.

Processadores com capacidades adicionais podem ser acrescentados ao sistema, fazendo com que tudo isso trabalhe junto, de maneira eficiente.

Quando dois processadores estão perto um do outro, nos deparamos com uma largura de banda mais alta e o atraso entre eles é baixo e próximo em termos computacionais (chamados de fortemente acoplados). Por outro lado, quando estão longe um do outro, temos baixa largura de banda e alto atraso e são remotos em termos computacionais (chamados de fracamente acoplados).

**ASPECTOS DO PROJETO DE MÁQUINAS PARALELAS**

Antes de se iniciar os estudos de uma computação paralela, devemos conhecer a natureza, o tamanho e a quantidade dos elementos de processamento e dos elementos de memória e devemos saber como os elementos de processamento e os elementos de memória estão interconectados. Devemos saber o que precisa rodar em paralelo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294040/18550.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294040/18550.png)

Conhecer os principais aspectos das Máquinas Paralelas.

Alguns computadores paralelos são concebidos para rodar simultaneamente várias tarefas independentes. Essas tarefas nada têm a ver umas com as outras e, portanto não precisam se comunicar. Como por exemplo, os sistemas de caixas eletrônicos ou os servidores Web.

Outro ponto é representado pelas máquinas paralelas usadas para rodar uma única tarefa dividida entre diversos processos que executam simultaneamente. Como por exemplo, um programa para jogar xadrez, que deve ser capaz de analisar a situação no tabuleiro, gerando uma lista das jogadas legais que poderão ser feitas a partir dessa posição particular. Neste caso, o paralelismo não é empregado para acomodar mais usuários no sistema como no exemplo anterior, mas para ganhar velocidade na solução de um único problema.

**MODELOS DE COMUNICAÇÃO**

Em qualquer tipo de sistema de processamento paralelo, os processadores que estiverem trabalhando nas diferentes partes de uma mesma tarefa precisam se comunicar entre si para poder trocar informações. Existem duas filosofias de projeto diferentes e que foram implementados, são os sistemas multiprocessadores e os sistemas multicomputadores.

A diferença entre os dois é a presença ou ausência de memória compartilhada. Nos Multiprocessadores todos os processadores compartilham uma mesma memória física, e nos Multicomputadores cada processador tem sua própria memória, acessível somente pelo processador proprietário e nunca diretamente por qualquer outro processador do sistema.

Como os multiprocessadores são difíceis de construir e fáceis de programar, enquanto que os multicomputadores são fáceis de construir e difíceis de programar, pesquisas são realizadas para a construção de sistemas híbridos, relativamente fáceis de construir e relativamente fáceis de programar.

A principal questão é ter projetos que sejam escaláveis, ou seja, que continuem a funcionar bem, mesmo quando o número de processadores do sistema aumente.

Outra possibilidade seria usar o hardware do multicomputador fazendo com que o Sistema Operacional simulasse a memória compartilhada fornecendo aos processos um espaço de endereçamento virtual paginado, compartilhado, espaço esse visualizado por todo o sistema.

**REDES DE INTERCONEXÃO**

Em uma rede de interconexão, vários módulos de memória precisam se comunicar entre si e com os processadores.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294041/18551.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/4/0/294041/18551.png)

Processadores Interconectados.

Para as redes de interconexão a semelhança entre os sistemas multiprocessadores e multicomputadores, está no fato de que, no fim das contas, ambos usam o mecanismo da troca de mensagens para implementar a comunicação entre seus componentes.

Nos sistemas multiprocessadores de grande porte, a comunicação entre processadores e memória remota é efetivada quando o processador envia para a memória uma mensagem explícita (pacote) requisitando um dado, e a memória devolve com outro pacote de resposta.

As redes de interconexão podem ser compostas por até cinco componentes:

1 – processadores

2 – Módulos de memória

3 – Interface

4 – Links

5 – Comutadores

As interfaces são dispositivos que fazem o envio e a recepção de mensagens. Em alguns projetos, a interface é um chip ou uma placa ligada a cada barramento local dos processadores e que pode se comunicar tanto com o processador quanto com a memória local.

Os links são os canais físicos sobre os quais os bits se movimentam, podem ser construídos com fios elétricos ou com fibras óticas, pode ser serial ou paralelo.

Os comutadores são dispositivos com várias portas de entrada e várias portas de saída. Quando um pacote chega à porta de entrada de um computador, alguns de seus bits são usados para selecionar a porta de saída pela qual o pacote deve ser enviado.

Uma característica importante de uma rede de interconexão é a sua capacidade de transmissão, isto é, quantos dados ela pode mover por segundo.

**TOPOLOGIA**

A topologia de uma rede de interconexão descreve a organização de como seus links e seus computadores são organizados.

O projeto da topologia pode ser modelado por meios de grafos, com os links sendo os arcos e os comutadores os nós. Cada nó de uma rede de interconexão (ou grafo) tem um certo número de links ligados a ele.

Uma propriedade de uma rede de interconexão é o seu diâmetro, que mede a distância entre dois nós mais afastados, ou seja, os que tem a maior distância entre eles.

É importante ressaltar quantos dados a rede pode mover por segundo, que é a capacidade de transmissão, que pode existir em uma rede de interconexão.

Redes de interconexão podem ser caracterizadas por sua dimensão, que é determinada pelo número de opções que há para chegar da origem ao destino. Se houver apenas um caminho entre a origem e o destino, a rede tem dimensão zero.

Uma rede é dita unidimensional quando houver apenas um caminho de opção para um pacote percorrer, e é chamada de bidimensional quando existir mais de um caminho de opção ao pacote.

Veja nos exemplos abaixo os modelos de topologia usados em redes de Interconexão:

**Configuração estrela (a)**

Nesta configuração os processadores e as memórias devem estar ligados aos nós da parte de fora, com o nó central sendo usado só para fazer a comutação. Apesar do seu projeto muito simples, esse tipo de rede não pode ser usado em sistemas de grande porte, pois o nó central se transforma em um gargalo muito grande.

**Malha de interconexão completa (b)**

Nesta configuração cada nó tem uma conexão direta com todos os demais nós da rede. Essa topologia maximiza a largura de banda de bisseção e minimiza o diâmetro, e ainda oferece alta tolerância à falha.

**Configuração em árvore (c)**

Nesta configuração a largura de banda dos nós é igual a capacidade do enlace, se o tráfego da rede for muito grande próximo ao topo da árvore os poucos nós do topo se transformarão em gargalos, o que pode ser contornado com o aumento da largura das bisseções dando mais largura de banda aos enlaces que estão mais acima.

**Configuração em anel (d)**

Nesta configuração cada pacote pode escolher entre ir para a direita ou para esquerda, por esse motivo é tratada como unidimensional.

**Configuração em grade (e)**

A topologia em grade ou malha é um projeto de dimensão dois que tem sido usado em diversos sistemas comerciais. É de alta regularidade, fácil de ampliar para tamanhos maiores e tem um diâmetro que aumenta apenas com a raiz quadrada do número de nós.

**Configuração double torus (f)**

É uma configuração variante da topologia em grade que nada mais é que uma topologia em grade com suas bordas conectadas. Além de ser mais tolerante à falha do que a grade, seu diâmetro também é menor, porque as aresta opostas podem se comunicar em somente dois saltos.

**Configuração em cubo (g e h)**

Nesta configuração temos dois tipos de cubos possíveis, um que é um cubo tridimensional regular, e outro construído a partir de dois cubos de três dimensões com os nós das bordas conectados. Muitos computadores paralelos usam esse tipo de topologia, uma vez que o diâmetro cresce linearmente com a dimensão. Podemos conectar os nós de dois cubos com outros dois, o que pode ser feito _**n**_ vezes formando hipercubos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295015/18552.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295015/18552.jpg)