  

[![](https://ampli-images.s3.amazonaws.com/production/c12dcfc5-99b9-4711-a51c-fc0da25ad3c0/original)](https://ampli-images.s3.amazonaws.com/production/c12dcfc5-99b9-4711-a51c-fc0da25ad3c0/original)

Os primeiros microcomputadores foram lançados na década de 70, tinham processadores com tecnologia de 8 _bits_ e seu barramento com 8 _bits_, que era o caso do então processador 8080.  Após estes primeiros modelos foram lançados processadores com 16 _bits_ de processamento interno e barramento e, na sequência, os processadores de 32 _bits_, os de 64 _bits_ e, ainda mais recentemente, os processadores passaram a contar também com a possibilidade de terem mais que um núcleo de processamento, como é o exemplo dos processadores Multicore, dos quais fazem parte os modernos i3, i5, i7, entre outros (TECMUNDO, 2015).

Um processador manipula dados executando ações com o objetivo de obter resultados. São ações comuns à execução de operações aritméticas simples, tais como: somar, subtrair, multiplicar e dividir; operações lógicas e, também, as operações de movimentação de dados entre a CPU e a memória. Os componentes do processador são interligados pelos barramentos que permitem esta movimentação entre os dados (MONTEIRO, 2007). Ainda segundo Monteiro (2007), um barramento é o caminho por onde trafegam todas as informações de um computador. Existem três tipos principais de barramentos:

- Barramento de dados.
- Barramento de endereços.
- Barramento de controle.

**Barramento de dados -** Este barramento interliga a CPU à memória, e vice-versa, para a transferência das informações que serão processadas. Ele determina diretamente o desempenho do sistema, pois quanto maior o número de vias de comunicação, maior o número de _bits_ transferidos e, consequentemente, maior a rapidez com que estes dados serão processados. Os primeiros PCs possuíam barramento de 8 vias. Atualmente, dependendo do processador, este número de vias pode ser de 32, 64 e até de 128 vias (FÁVERO, 2011).

**Barramento de endereços -** Interliga a CPU à memória fazendo seu endereçamento e tem o número de vias correspondente à tecnologia de _bits_ do processador, ou seja, nos computadores mais modernos, 32 _bits_ ou 64 _bits_ e conforme já visto por você, permitindo endereçar até 4 GB (_Gigabytes_) de memória em processadores 32 _bits_ e cerca de 16 PB (_Petabytes_), no caso de processadores de 64 _bits_ (SOUZA FILHO, 2014).

**Barramento de controle** - Interliga na CPU à Unidade de Controle aos componentes e dispositivos de um computador, componentes de entrada e saída, memórias auxiliares e de armazenamento, entre outros. Por trabalhar com componentes externos ao processador, pode ser chamado também de barramento externo (MONTEIRO, 2007).

_______

**💭 Reflita**

Em um barramento de dados, o número de vias determina diretamente o desempenho de um sistema, ou seja, quanto maior o número de vias de barramento, mais rápida será a transferência de dados entre o processador e a memória, aproveitando melhor a velocidade de um processador, que como já foi visto por você anteriormente, muitas vezes esta velocidade é superior à capacidade de transferência de dados proporcionada pelos barramentos.

_______

A CPU de um computador é composta por vários elementos e pode ser dividida em duas categorias funcionais, a Unidade Funcional de Controle e Unidade Funcional de Processamento. Na Figura 2.2, pode-se observar o diagrama funcional básico da CPU, no qual a Unidade Funcional de Processamento é composta pelos registradores, ACC e ULA, e a Unidade Funcional de Controle é composta pelos elementos: RDM, REM, CI, RI, Decodificador de Instruções, UC e _Clock_ (relógio) (FÁVERO, 2011).

Um ponto importante que merece ser destacado é a velocidade com que a CPU trabalha, medida por ciclos de _clock_. Ciclo de _clock_ é o tempo gasto pelo processador para executar uma operação ou para transferir um dado entre ele e a memória e que define sua velocidade. Este tempo é medido em Hertz, ou seja, quantos ciclos são processados por segundo. Os processadores atuais trabalham com velocidades na casa dos Gigahertz (PATTERSON, 2014).

[![](https://ampli-images.s3.amazonaws.com/production/e92c5581-5075-4080-9d0c-6c36973edf89/original)](https://ampli-images.s3.amazonaws.com/production/e92c5581-5075-4080-9d0c-6c36973edf89/original)

Diagrama funcional. Fonte: FÁVERO (2011, p. 60).

**➕ Pesquise mais**

Aprofunde seus conhecimentos sobre os componentes do processador, barramentos e outros no [livro](https://drive.google.com/file/d/0B88W4nXfvRcTX2c4WDBLUFFQRW8/view): FÁVERO, Eliane M. B. **Organização e arquitetura de computadores**. Pato Branco: Universidade Tecnológica Federal do Paraná, 2011.

_______

Segundo Monteiro (2007), o que define um projeto de um processador é a quantidade de instruções de máquina que se deseja que ele, processador, execute, quanto menor este conjunto de instruções, mais rápido se torna um processador. Partindo deste princípio, os processadores têm dois tipos de arquiteturas empregadas pelos seus fabricantes:

- A arquitetura CISC (_Complex Instruction Set Computers_) – Sistema com um conjunto de instruções complexo, atualmente utilizado pelos processadores de computadores pessoais;
- A arquitetura RISC (Reduced Instuction Set Computes) – Sistema com um conjunto de instruções reduzido, que é empregado nos processadores ARM utilizados pelos smartphones e tablets atuais (MONTEIRO, 2007).

Estas instruções servem para que o processador execute suas funções, como operações aritméticas, endereçamento de memória, controle de dispositivos e outros (FÁVERO, 2011).

**Processadores CISC (**_**Complex Instruction Set Computers**_**)** - Os processadores com tecnologia CISC são capazes de processar centenas de conjuntos complexos de instruções simples. Isto significa que cada instrução isoladamente é considerada simples, curta e pouco potente, porém várias destas instruções agrupadas formam um conjunto complexo que é executado pelo processador. Inicialmente, existia uma grande tendência a esta tecnologia de processadores, porém havia algumas desvantagens, como o desempenho reduzido justamente pelo excesso de instruções executadas pelo processador e pela velocidade de processamento ter que ser elevada para que o desempenho fosse melhorado. A ideia dos fabricantes era produzir processadores cada vez mais potentes baseados na complexidade destes conjuntos de instruções (BROOKSHEAR, 2013).

**Processadores RISC (**_**Reduced Instuction Set Computes**_**)** - Os processadores com tecnologia RISC têm um conjunto reduzido de instruções, e diferente da tecnologia CISC, estas instruções são consideradas complexas, pois cada uma delas executa várias tarefas conjuntas. Isto permite uma vantagem dos processadores RISC em relação aos processadores CISC, que por ter um número menor de instruções tem menos circuitos internos e assim podem trabalhar com frequências muito maiores sem ter problemas de superaquecimento dos processadores (BROOKSHEAR, 2013).

_______

**🔁 Assimile**

Os processadores podem ser de dois tipos de acordo com sua tecnologia: Processadores CISC, que processam centenas de conjuntos complexos de instruções simples. Isto significa que cada instrução isoladamente é considerada simples, curta e pouco potente, porém várias destas instruções agrupadas formam um conjunto complexo que é executado pelo processador.

Processadores RISC têm um conjunto reduzido de instruções, e diferente da tecnologia CISC, estas instruções são consideradas complexas, pois cada uma delas executa várias tarefas conjuntas.