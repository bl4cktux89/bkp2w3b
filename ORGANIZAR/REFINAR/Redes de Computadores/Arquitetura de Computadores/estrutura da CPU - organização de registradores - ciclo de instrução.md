O processador (CPU) é o componente vital de um sistema de computação, responsável pela realização das operações de processamento (cálculos matemáticos, entre outros) e de controle durante a execução de um programa.

Um programa, para ser efetivamente executado por um processador, deve ser constituído por uma série de instruções (em linguagem de máquina). Essas instruções devem estar armazenadas em posições sucessivas da memória principal. A execução é sequencial, ou seja, se a instrução executada está na posição x, a próxima instrução a ser executada deverá estar na posição x + 1. A sequência de funcionamento de uma CPU é conhecida como ciclo "busca – decodificação – execução" de instruções, e a figura 1 ilustra esse ciclo.

- Um elemento dentro do processador, denominado contador de instruções (PC – _program counter_), contém a posição da próxima instrução a ser executada. Quando uma sequência de execução de instruções tem início, a instrução cujo endereço está no contador de instruções é trazida da memória para uma área chamada registrador de instruções (RI). Esse processo é conhecido como **busca da instrução**.
- A instrução é interpretada por circuitos de decodificação que fazem com que sinais eletrônicos sejam gerados no processador como resultado do valor do campo de operação, isto é, **decodificam** a informação correspondente à operação a ser realizada.
- Esses sinais resultam na **execução da instrução**, isto é, aplicação da função contida pela operação sobre os operandos. Quando a execução de uma instrução é terminada, o contador de instruçõesé atualizado para o endereço da memória da próxima instrução (x + 1).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108842/a16i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108842/a16i01_arco80_100.jpg)

A sequência de instruções pode mudar como resultado de uma instrução que direciona um desvio (também chamado de salto, _**jump**_). Instruções desse tipo contêm no campo operandos o endereço da próxima instrução a ser executada. Elas causam mudanças no fluxo do programa como resultado das condições dos dados. O desvio condicional representado por uma instrução de alto nível _**IF**_ traduz-se em algum tipo de instrução de desvio.

As atividades realizadas pela CPU podem ser divididas em duas grandes categorias funcionais:

- Funções de processamento
- Funções de controle

A função de processamento se encarrega de realizar as atividades relacionadas com a efetiva execução de uma operação, ou seja, processar (executar a instrução) de instruções. O principal componente da CPU que realiza a função de processamento é a ULA (unidade lógica e aritmética), e a ação dela é complementada pelo uso de registradores de processamento. A função de controle é exercida pelos componentes da CPU que se encarregam de atividades de busca, interpretação e controle da execução das instruções, bem como do controle da ação dos demais componentes do sistema de computação (memória, entrada/saída).

O principal componente da CPU responsável pela função de controle é a UC (unidade de controle).

**Componentes**

As funções de controle e processamento necessitam de componentes, constituídos de circuitos digitais, para sua realização. Esses componentes são interligados interna e externamente por meio de barramentos. A figura no link a seguir ilustra os principais componentes de um processador atual:

[![](https://img.uninove.br/static/0/0/0/0/0/0/7/3/3/3/0/7333064/ucp-completa.png)](https://img.uninove.br/static/0/0/0/0/0/0/7/3/3/3/0/7333064/ucp-completa.png)

A figura  ilustra uma CPU de um microprocessador simples, justamente para facilitar as primeiras explicações sobre o assunto, porém os seguintes componentes, pelo menos, devem fazer-se presentes em um microprocessador:

- UAL: unidade lógica e aritmética (ULA), responsável por efetuar operações matemáticas com os dados. Essas operações podem ser, por exemplo, soma, subtração, multiplicação, divisão, operações lógicas _AND_, _OR_, _XOR_, _NOT_, deslocamento de bits à direita e esquerda, incremento e decremento, comparações.
- ACC: registrador(es) auxiliar(es) sobre o(s) qual(is) a ULA realiza suas operações. Quando é único, todas as instruções o utilizam, como fonte e destino.
- CI (PC): contador de instruções (program counter). Registrador cuja função específica é armazenar o endereço da próxima instrução a ser executada.
- RDM: registrador de dados da memória.
- REM: registrador de endereços da memória.
- MP: memória principal. Local onde ficam dados e instruções já/a serem executadas.
- RI: registrador de instruções: tem a função específica de armazenar a instrução a ser executada.
- Relógio: é o dispositivo gerador de pulsos. A quantidade de vezes em que esse pulso básico se repete define a unidade de medida do relógio chamado frequência, usada também para definir velocidade na CPU.
- UC: unidade de controle. É o dispositivo mais complexo da CPU, pois, além de controlar a ação da ULA, possui a lógica necessária para realizar a movimentação de dados e instruções de e para a CPU, por meio de sinais de controle emitidos em instantes de tempo programados. Os sinais de controle ocorrem em vários instantes durante o período de realização do ciclo de instruções.
- Decodificador de instruções: é um dispositivo utilizado para identificar as operações a serem realizadas relacionadas à instrução a ser executada.
- Barramentos: utilizados para a comunicação entre os dispositivos, são de três tipos específicos: dados, endereços e controle.

**Função processamento**

Processar o dado é executar com ele uma ação que produza algum tipo de resultado. Essa é, pois, a atividade-fim do sistema computacional: ele existe para processar dados.

Entre as tarefas comuns a essa função, podem ser citadas as que realizam:

- Operações aritméticas: somar, subtrair, multiplicar, dividir...
- Operações lógicas: _and_, _or_, _xor_, _not_...
- Movimentação de dados: memória-CPU, CPU-memória, registrador-registrador...
- Desvios: alteração da sequência de execução das instruções
- Operações de entrada ou saída

O principal dispositivo da CPU para a realização das atividades de processamento é a ULA. Ela utiliza os registradores de propósitos gerais (ACC) como auxiliares à função de processamento. A ULA (UAL) é um aglomerado de circuitos lógicos e componentes eletrônicos simples que, integrados, realizam as funções acima citadas. Ela pode ser uma pequena parte da pastilha do processador, usada em pequenos sistemas, ou pode compreender um considerável conjunto de componentes lógicos, ocupando mais espaço na pastilha do processador.

A capacidade de processamento de uma CPU é em grande parte determinada pelas facilidades embutidas no hardware da ULA1 para realizar as operações matemáticas projetadas. Um dos elementos fundamentais é a definição do tamanho da palavra. O valor escolhido no projeto de fabricação da CPU irá determinar o tamanho dos elementos ligados à área de processamento (ULA, barramentos internos e registradores).

Um tamanho maior ou menor de palavra acarreta, sem dúvida, diferenças fundamentais no desempenho da CPU, e, por conseguinte, do sistema como um todo. Os seguintes componentes possuem influência direta do tamanho da palavra:

- Influência no desempenho por causa de maior ou menor tempo de execução com operações matemáticas na ULA.
- Influência no desempenho por causa do tamanho escolhido para o barramento interno e externo da CPU.
- Em geral, obtém-se o máximo de desempenho quando a largura (tamanho em bits) do barramento de dados é, no mínimo, igual ao tamanho da palavra (barramento interno).

O tamanho da palavra tem influência também na implementação física do acesso à memória. Embora atualmente a capacidade das memórias seja medida por bytes (ou conjunto de), o movimento de dados entre CPU e memória é normalmente medido em palavras (barramento externo).

**Função de controle**

A área de controle de uma CPU é a parte funcional que realiza as atividades de (uma de cada vez, geralmente):

1. Busca da instrução que será executada, armazenando-a em um registrador especialmente projetado para essa atividade (RI).
2. Interpretação das ações a serem desencadeadas com a execução da instrução (se é uma soma ou subtração, por exemplo, como realizá-las).
3. Geração de sinais de controle apropriados para realização das atividades requeridas para a execução propriamente dita da instrução identificada. Esses sinais de controle são enviados aos diversos componentes do sistema, sejam internos da CPU (como ULA) ou externos (como a memória).

A área destinada à função de controle é projetada para entender o que fazer, como fazer e comandar quem vai fazer no momento adequado. Uma analogia pode ser feita com os seres humanos, imaginando que a área de controle é o cérebro que comanda o ato de andar, enquanto a área de processamento são os músculos e ossos das pessoas que realizam efetivamente o ato. Os nervos podem ser relacionados com os barramentos entre os diversos elementos envolvidos.

Os dispositivos básicos que fazem parte da área de controle são:

- Unidade de controle (UC)
- Decodificador de instruções
- Registrador de instruções (RI)
- Contador de instruções (_program counter_ – PC)
- Relógio ou _clock_
- Registrador de endereços da memória (REM)
- Registrador de dados da memória (RDM)

O componente vital para as funções de controle é a Unidade de Controle (UC). Ela recebe como entrada o valor do registrador de instruções e decodifica-o (por meio do decodificador de instruções). Para cada código de instruções, ele gera uma sequência de sinais diferentes, ativando os circuitos correspondentes para cada uma das tarefas necessárias para a busca e execução da instrução.

Cada sinal de controle comanda uma microinstrução (que denota uma tarefa a ser executada para uma operação). Uma microinstrução pode ser responsável pela realização de uma carga em um registrador, uma seleção de um dado para entrada em um determinado componente, uma ativação da memória, a seleção de uma operação da ULA ou a habilitação de um circuito lógico, para citar alguns exemplos.

Existem várias formas de implementações (organizações) das unidades de controle. As duas usuais são:

- Organização convencional: a unidade de controle é composta por itens digitais como flip-flops, contadores e decodificadores, que geram, sequencialmente e nos instantes de tempo adequados, todos os sinais de controle necessários à ativação da unidade operacional.
- Organização microprogramada: em uma unidade de controle microprogramada, os sinais de controle estão armazenados numa memória especial chamada memória de controle. Vários sinais de controle são buscados a cada acesso à memória de controle.

**Barramentos internos**

Os barramentos internos interligam os componentes do processador para troca de sinais e valores.Assim como no caso da comunicação processador/memória, são três os barramentos internos:

- Barramento Interno de Dados: usado na transferência de dados entre os registradores e entre os registradores e a ULA. A sua largura define o tamanho da palavra da máquina.
- Barramento Interno de Endereços: permite a transferência de endereços entre os registradores.
- Barramento Interno de Controle: transmite os sinais do bloco de controle que comandam o funcionamento de cada circuito do processador.

**Ciclo de instrução**

Busca, decodificação e execução de instruções são tarefas básicas realizadas por um processador. Caracterizam um ciclo, pois as tarefas são executadas repetidamente, sempre e sempre, até que seja decodificada uma instrução que indique parada ao computador.

O fluxograma do ciclo de instrução anteriormente mostrado ilustra isso de forma simplificada. Um dos pontos omitidos é o incremento do PC, função indispensável ao funcionamento de qualquer sistema de computação.

Outro ponto também apresentado de forma resumida são os acessos à memória. Tanto as instruções como os dados ficam armazenados na memória e, portanto, existem buscas de operandos na memória e cálculo do endereço da próxima instrução a ser executada. A Figura 2 ilustra mais alguns detalhes do ciclo de instrução.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108843/a16i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108843/a16i02_arco80_100.jpg)

Esse ciclo de instrução pode ser descrito em LTR (linguagem de transferência entre registradores), de modo que consigamos acompanhar sua realização com a movimentação de informações entre os componentes da CPU. O algoritmo a seguir ilustra esse funcionamento:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108844/a16i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108844/a16i03_arco80_100.jpg)

Inicialmente, o conteúdo de memória no endereço da próxima instrução a ser executada (PC) tem seu valor transferido para RI. Logo após, o valor de PC é incrementado para o endereço da próxima instrução a ser executada. O decodificador de instruções irá receber os bits referentes ao Código da Operação e decodificá-lo, dando entrada na UC desse valor. A UC gera os sinais necessários para a execução da instrução.

Detalhando ainda mais, pode-se elencar uma série de passos a serem realizados em cada parte do ciclo. São eles:

**a) Busca**

- Copiar o PC para o registrador de endereços da memória (REM)
- Ler uma instrução da memória
- Copiar o registrador de dados da memória (RDM) para o registrador de instruções (RI)
- Atualizar o contador de programa (PC)

**b) Decodificação**

- Nesta fase é determinada qual instrução deve ser executada

**c) Execução**

- Cálculo de endereço dos operandos (se houver)
- Busca dos operandos na memória (se houver)
- Seleção da operação a ser realizada pela ULA
- Carga de registradores
- Escrita de operandos na memória
- Atualização do PC (somente no caso de as instruções serem desvios)

**Medidas de desempenho**

A medida geral de desempenho de um sistema de computação depende fundamentalmente da capacidade e velocidade de seus diferentes componentes, da velocidade com que esses componentes se comunicam entre si e do grau de compatibilidade entre eles (p. ex., se a velocidade da CPU de um sistema é muito maior que a da memória).

Considerando a existência de tantos fatores que influenciam o desempenho de um sistema de computação, desenvolveram-se diversos meios de medir seu desempenho, entre os principais relacionados exclusivamente com a CPU destacam-se:

- MIPS
- FLOPS

O desempenho dos processadores, em geral, é medido em termos de sua velocidade de trabalho; como o trabalho da CPU é executar instruções, criou-se a unidade MIPS – milhões de instruções por segundo. O MIPS é muito questionado, pois mede apenas a execução de instruções, e existem diferentes instruções, com tempos de execução distintos, por exemplo, multiplicação de números inteiros e multiplicação de números reais (ponto flutuante).

Em contraste com o MIPS, a unidade FLOPS – operações de ponto flutuante por segundo – mede basicamente o desempenho da ULA, analisando apenas as instruções mais complexas (as que envolvem ponto flutuante). Hoje em dia, os microprocessadores estão na faixa de MFLOS (milhões de flops), sendo encontradas máquinas com GFLOPS (supercomputadores). O FLOPS foi inicialmente criado para ser a medida de estações de trabalho e de supercomputadores, mas atualmente também é utilizado em microcomputadores.

Quando se trata da recuperação ou escrita de dados na memória, o tempo de acesso é a unidade de medida apropriada, estando relacionada à velocidade de cada componente e a do canal (barramento(s)) de interligação entre CPU e memória.

**Tempo de resposta** é uma medida ligada ao desempenho global do sistema, e não ao de um ou outro componente. Trata-se do período de tempo gasto entre o instante em que o usuário iniciou uma solicitação e o instante em que o sistema apresentou ao usuário a resposta.