**Entrada e saída**

Outro componente muito importante dentro do sistema computacional é o conjunto de módulos de entrada e saída. Esses módulos estão conectados com o barramento do sistema e são as interfaces com o mundo externo. Sua função principal é permitir a comunicação entre o periférico que ele controla e o barramento. Existem algumas razões para não ligarmos os periféricos diretamente ao barramento do sistema, dentre elas estão:

1. grande variedade de periféricos. Cada um tem sua lógica de operação e, portanto, seria muito difícil dar a um único componente, como o processador, a missão de controlar cada um deles.
2. outro problema é o fato dos dispositivos externos apresentarem uma taxa de transferência de dados muito menor que aquela estabelecida entre CPUe MEM. Logo, seria inadequado usar o barramento do sistema para fazer uma comunicação direta entre CPU e periféricos.
3. o formato dos dados e o tamanho das palavras usados pelos periféricos são diferentes dos utilizados pelo computador.

Portanto, cabe ao módulo de E/S fornecer uma interface com o processador e memória via barramento do sistema por meio de conexões de dados adequadas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108825/a15i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108825/a15i01_arco80_100.jpg)

Conforme podemos observar na Figura 1, os dispositivos externos (periféricos) são conectados ao computador por meio de um módulo de E/S que oferece um meio para a troca de dados entre o mundo e o computador. A conexão estabelecida por intermédio do módulo de E/S é usada para transferência de dados, informações de controle e de estado dos periféricos ou da operação.

Existem diversos tipos de dispositivos externos, e eles podem ser classificados em:

1. voltados para a comunicação com o usuário: teclado, vídeo, impressora etc.
2. voltados para a comunicação com a máquina: discos magnéticos, sensores etc.
3. voltados para a comunicação com dispositivos remotos: modem, placa de rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108826/a15i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108826/a15i02_arco80_100.jpg)

Os sinais de controle indicam o tipo da operação (leitura ou escrita) ou alguma operação de controle, como movimentar a cabeça do disco para uma determinada posição. Os dados são bits a serem enviados ou recebidos do módulo de E/S. Já os sinais de estado indicam o estado propriamente dito do dispositivo, como: ready/not-ready.

O buffer é uma área de armazenamento temporário, e o transdutor é o responsável por converter dados codificados como sinais elétricos para alguma outra forma de energia.

Após essa introdução, podemos listar as funções mais importantes de um módulo de E/S, que são:

- controle e temporização
- comunicação com o processador
- comunicação com dispositivos
- armazenamento temporário de dados
- detecção de erros

As funções de controle e temporização são importantes, pois recursos como barramento e memória são compartilhados para a realização de várias atividades, entre elas E/S de dados. Portanto, é necessário incluir funções de controle e temporização para controlar o fluxo de dados entre o sistema computacional e o meio externo. Na comunicação do dispositivo com o processador, as seguintes etapas estão envolvidas:

- o módulo de E/S é questionado sobre seu estado: ok/not-ok
- o resultado da pergunta é retornado ao processador
- se o dispositivo estiver ok, o processador solicita a transferência dos dados enviando um comando para o módulo de E/S
- uma unidade de dados é obtida pela controladora do dispositivo
- os dados são transferidos para o processador

Cada interação entre processador e módulo de E/S envolve uma ou mais arbitração do barramento.

A detecção de erros é responsável por informar ao processador sobre o mau funcionamento do dispositivo (mecânico ou elétrico), por exemplo: uma falha em uma trilha do disco ou a falta de papel na impressora.

**Estrutura do módulo de E/S**

A quantidade de dispositivos que um módulo consegue controlar e a complexidade dele podem variar significativamente. Conforme podemos ver na Figura 3, os dados transferidos entre o módulo e o computador são armazenados temporariamente em registradores de dados. Além disso, existem registradores de estado para informar o estado atual do dispositivo. Cada um dos módulos de E/S possui um endereço distinto para ser referenciado pelo processador. Dessa forma, o intuito do módulo de E/S é dar ao processador uma visão simplificada da grande variedade de periféricos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108827/a15i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108827/a15i03_arco80_100.jpg)

Ao executar uma operação de E/S em um programa, o processador envia um comando para o módulo de E/S apropriado, solicitando uma operação específica. Para que uma instrução de E/S seja executada, o processador gera um endereço (dizendo qual é o módulo de E/S solicitado) e transmite via barramento esse endereço com a operação requerida. Os tipos de comandos de E/S são:

- controle: ativa um periférico e indica uma ação, por exemplo: eject/dev/cdrom (Linux).
- teste: verifica as condições de estado do dispositivo associado ao módulo de E/S, por exemplo: ready ou not-ready.
- leitura: solicita a leitura de itens de dados do periférico. O módulo de E/S os armazena no registrador de dados interno até que o processador solicite a transferência deles para o barramento de dados.
- gravação: CPU ordena ao módulo de E/S que pegue o dado do barramento de dados e o armazene no periférico.

Existem três técnicas diferentes que podem ser utilizadas durante a realização de operações de E/S, são elas: E/S programada, E/S dirigida por interrupção e acesso direto à memória (DMA). A Figura 4 ilustra o esquema de funcionamento de cada uma dessas técnicas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108828/a15i04_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108828/a15i04_arco80_100.jpg)

**E/S programada**

Neste modo de comunicação, o processador, além de executar o programa, possui controle total sobre as operações de E/S. Esse controle inclui a detecção do estado do dispositivo, o envio de comandos para o módulo de E/S (leitura ou escrita) e a transferência de dados.Por isso, toda vez que o programa em execução realiza alguma operação de I/O, o processador tem que interromper sua execução para tratar

da operação solicitada. Com isso, a execução do programa fica interrompida até que a operação seja finalizada. Nesse intervalo, o CPU fica testando o estado do módulo de E/S. Como podemos imaginar, ocorrerá um desperdício de processamento, pois o processador é muito mais rápido que o módulo de E/S. A transferência dos dados acontece entre o módulo de E/S e o processador.

**E/S dirigida por interrupção**

Neste modo de comunicação, o processador não fica esperando que a operação de I/O seja finalizada para continuar a execução do programa, como acontecia no caso da E/S programada. Em vez disso, ele simplesmente emite um sinal para a controladora (módulo de I/O) com a operação solicitada e continua executando outras instruções do programa. Quando a controladora estiver pronta para trocar informações com a CPU, ela envia um sinal de interrupção avisando seu estado de "pronto". Após esse sinal, o processador realiza a transferência dos dados, como acontecia no modo anterior. Para a CPU, a execução acontece do seguinte modo:

- processador envia um sinal de leitura para o módulo de E/S e continua com a execução do programa.
- sempre ao final de cada ciclo de execução o processador verifica se existe algum sinal de interrupção de um módulo de E/S pendente. Se existir, o contexto do programa é salvo e a interrupção é processada, fazendo a leitura dos dados da controladora e armazenando-os na memória.
- é recuperado o contexto do programa e é continuada sua execução normal.

Devemos ressaltar que tanto na E/S programada quanto na dirigida por interrupção, o processador sempre é o responsável por obter dados da memória principal (operação de saída memória ? dispositivo) ou por armazenar dados na memória principal (operação de entrada dispositivo ? memória).

**Interrupções**

A um sinal ou evento capaz de interromper a sequência normal de execução de instruções, damos o nome de interrupção. Os tipos mais comuns de interrupções estão listados a seguir:

- interrupção de software: ocasionada por alguma condição resultante da execução de uma instrução, por exemplo um overflow ou uma divisão por zero.
- interrupção de relógio: gerada pelo clock do processador, destinada a executar operações periódicas.
- interrupção de E/S: ocasionada por um controlador de E/S para indicar a conclusão de uma operação ou a ocorrência de erros.
- interrupção de falha de hardware: provocada por falha do hardware, como um erro de paridade em memória ou a queda de energia.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108829/a15i05_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108829/a15i05_arco80_100.jpg)

O principal objetivo das interrupções é melhorar o desempenho da CPU ex.: leitura de dado em disco).

**DMA – acesso direto à memória**

Esta técnica é uma opção mais interessante de realizar as operações de E/S, pois a transferência de dados entre o módulo de E/S e a memória principal é feita diretamente sem a necessidade de envolver o processador.

Dentre as principais desvantagens dos métodos anteriores, podemos citar:

- a taxa de transferência de E/S é limitada pela velocidade com que o processador pode servir um dispositivo.
- o processador tem que se ocupar em gerenciar a transferência dos dados.

Para evitar esses problemas, desenvolveu-se um módulo adicional que está conectado ao barramento do sistema. Esse módulo é chamado de DMA. Esse controlador é capaz de imitar o processador e transferir dados diretamente de e para a memória por meio do barramento do sistema. Assim, podemos verificar que esse módulo pode disputar o uso do barramento com a CPU.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108830/a15i06_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/8/108830/a15i06_arco80_100.jpg)

As informações trocadas entre o DMA e a CPU quando esta deseja ler ou escrever um conjunto de dados em um periférico podem ser descritas como segue:

- por meio do barramento de controle a CPU indica o tipo de operação ao DMA.
- nas linhas de dados é passado o endereço do módulo de E/S correspondente.
- o endereço de memória para o DMA armazenar ou ler informações também é passado por meio das linhas de dados.
- a quantidade de palavras que serão lidas ou escritas também vai pela linha de dados.

Portanto, o gerenciamento da operação de I/O fica a cargo do DMA. Suponha que um programa solicite uma leitura de um arquivo em disco. O DMA será o responsável por controlar a operação e armazenar os dados lidos do disco direto na memória principal, no endereço transmitido pela CPU durante a solicitação. Ao finalizar a transferência, o DMA emite um sinal de interrupção ao processador, indicando o término da operação. Nesse instante, o processador busca os dados direto na memória, poupando tempo de acesso à controladora do disco e, consequentemente, melhorando o desempenho do sistema computacional. Dessa forma, o processador só se envolve no início e no fim da operação.