[![](https://ampli-images.s3.amazonaws.com/production/54331288-90a2-46fe-8eca-199b7d428d95/original)](https://ampli-images.s3.amazonaws.com/production/54331288-90a2-46fe-8eca-199b7d428d95/original)

Os processadores atuais possuem mais de um núcleo de processamento e estão presentes em smartphones, notebooks, desktops, servidores, pulseiras inteligentes, entre outros. A utilização dos núcleos de processamento depende de como o sistema operacional escalona os programas para utilizá-los. Desta forma, a elaboração dos algoritmos precisa ser adaptada de forma que o sistema operacional consiga escalonar parte das computações para mais de um núcleo de processamento ao mesmo tempo e use os recursos de forma mais eficiente. Portanto, os conceitos de processos e _threads_ são importantes para permitir a descrição de algoritmos que funcionem de forma eficiente.

Em sistemas operacionais, um conceito muito importante é o de processo, o qual é definido como um programa em execução, e _threads_ que são fluxos ou linhas de execução dentro de um processo (TANENBAUM; BOS, 2016). Como exemplo de processo, podemos considerar um editor de texto executando em um desktop ou um aplicativo de calendário executado em um smartphone.

Um processo possui um espaço de endereçamento de memória que armazena o código executável, os dados referentes ao programa, a pilha de execução, o valor do contador de programa, o valor do apontador de pilha, os valores dos demais registradores do hardware e outros recursos, como informações sobre processos filhos, arquivos abertos, alarmes pendentes, tratadores de sinais, entre outras informações necessárias para a execução do programa.

Muitas vezes, a construção de software usando um único processo pode não ser eficiente na utilização dos núcleos de processamento disponíveis nos processadores atuais, pois apenas um núcleo de processamento é utilizado. Por isso, existe a necessidade de construir aplicações paralelas e distribuídas, que permitam a execução simultânea de processos e/ou _threads_, deixando o software com execução mais rápida.

O ato de gerenciar e executar múltiplas computações ao mesmo tempo, seja por troca de contexto no uso do núcleo de processamento ou pelo uso de diferentes núcleos de processamento é denominado concorrência. Por exemplo, uma máquina com processador contendo quatro núcleos de processamento executando dez programas diferentes necessita que o sistema operacional escalone fatias de tempo para que todos os programas consigam utilizar os núcleos de processamento por meio de revezamento.

Estes programas estarão executando de forma concorrente, dando ao usuário a impressão de que cada programa está utilizando os recursos do computador de forma dedicada. Quando há execução de computações simultaneamente em diferentes núcleos de processamento, tem-se paralelismo. Assim, processos e _threads_ podem ser executados de forma concorrente e paralela. Por exemplo, um navegador com duas abas abertas, cada aba sendo um _thread_ executado em um núcleo de processamento diferente, representa uma situação de execução paralela.

Um processo pode possuir um ou mais _threads_, permitindo que um programa execute mais de um trecho de código simultaneamente. Cada _thread_ é um fluxo de controle sequencial isolado dentro de um programa capaz de utilizar CPU (_Central Processing Unit_). É composto de identificador (ID) de _thread_, contador de programa, conjunto de registradores e uma pilha de execução. Cada _thread_ pode compartilhar com outros threads pertencentes ao mesmo processo a sua seção de código, seção de dados e outros recursos do sistema operacional, arquivos abertos e sinais.

A figura abaixo ilustra cinco possíveis situações em que existem processos e _threads_ sendo executados em um notebook.

[![](https://ampli-images.s3.amazonaws.com/production/8645ec6a-a731-4d3c-a100-002a85a75398/original)](https://ampli-images.s3.amazonaws.com/production/8645ec6a-a731-4d3c-a100-002a85a75398/original)

(A) Notebook executando um processo com um thread; (B) Notebook executando quatro processos com um thread cada; (C) Notebook executando um processo com quatro threads; (D) Notebook executando quatro processos com dois threads por processo; (E) Sistema distribuído com dois notebooks executando vários processos e threads. Fonte: elaborada pelo autor.

Na imagem (A), há um processo com um único _thread_ executado. O conjunto de instruções desse processo é executado de forma sequencial. Por exemplo, um programa que calcula a soma das notas inseridas pelo professor.

A imagem (B) apresenta quatro processos, cada um com um único _thread_, e os processos podem executar simultaneamente em núcleos de processamento, de acordo com escalonamento do sistema operacional.

Já na imagem (C), há um processo com quatro _threads_, e cada _thread_ possui seu fluxo de controle, que pode ser executado concorrentemente a outros _threads_, pois há um único núcleo de processamento. Por exemplo, um programa que realiza a soma de um conjunto de dados, distribuindo os dados entre cada _thread_ para que haja a soma parcial simultânea da porção de dados recebido e, por fim, realiza a soma total.

Vários processos com vários _threads_ por processo são ilustrados na imagem (D), gerando a execução de vários fluxos de controle ao mesmo tempo e executando em núcleos de processamento diferentes. Por exemplo, vários programas, como navegador e editor de texto, , executando em um computador com quatro núcleos de processamento.

Por último, na imagem (E), tem-se um sistema distribuído composto por máquinas interligadas via um _switch_. Cada máquina pode ter mais de um processo executando mais de um _thread_. Os sistemas distribuídos são construídos sobre sistemas operacionais e utilizam processos e threads para realizar a execução de um programa.

A comunicação entre os processos e/ou _threads_ precisa ser realizada de forma especial, usando bibliotecas específicas. Na paralelização de um programa utilizando _threads_ que executam em uma mesma máquina, podem ser utilizadas bibliotecas, como OpenMP (OPENMP, 2021) ou Pthreads (Posix Threads) (BARNEY, 2021). Os programas podem ser desenvolvidos para serem executados utilizando mais de um processo e em máquinas remotas. A comunicação entre os processos deve utilizar bibliotecas de troca de mensagens, como _Message Passing Interface_ (MPI) (OPENMPI, 2021) e de _sockets_, assunto que será abordado posteriormente.

Você sabia que os programas que coloca para executar no seu notebook, no seu desktop ou mesmo no seu smartphone são processos? Mas, como pode-se criar um novo processo e finalizar (término de um processo)?

A criação de processos pode ocorrer em uma das seguintes situações:

- Pelo usuário, para iniciar a execução de um programa (via linha de comando ou duplo clique no mouse).
- Por funções específicas que independem do usuário (chamadas de serviços (_daemons_) ou executando em _background_ sem intervenção do usuário), por exemplo, na recepção e no envio de e-mails, serviços de impressão, etc.
- Usando chamadas de sistema dentro de um programa.

Nos sistemas operacionais UNIX e Unix-like (como o Linux), os processos são criados utilizando a chamada de sistema fork(). No sistema operacional Windows, a criação ocorre pela chamada `**CreateProcess()**` (TANENBAUM; STEEN, 2007).

O término de processos pode ocorrer de algumas formas. Uma delas é quando o programa termina sua execução pela chamada _exit_ no sistema operacional Unix-like, e ExitProcess no sistema operacional Windows; por algum erro ocorrido que não permitiu que o processo pudesse ser finalizado ou por um erro fatal; causado por algum erro no programa (bug), como divisão por 0 (zero), referência à memória inexistente ou não pertencente ao processo e execução de uma instrução ilegal (TANENBAUM; STEEN, 2007).

Dentro de um processo, poderá existir tarefas que podem ser executadas de forma concorrente utilizando melhor os núcleos de processamento. A execução dessas tarefas pode ser realizada utilizando _threads_, que são escalonadas pelo sistema operacional para utilizarem os núcleos de processamento.

A decisão de quando criar _threads_ dentro de um processo depende de quais características o problema que está sendo resolvido possui, ou seja, suas subtarefas. Assim, podem ser criadas quando há subtarefas que possuem potencial de ficarem bloqueadas por um longo tempo; usam muitos ciclos de CPU; devem responder a eventos assíncronos; tenham importância maior ou menor do que outras tarefas e podem ser executadas em paralelo com outras tarefas.

______

**📝****Exemplificando**

A criação de processo nas linguagens C/C++ é realizada no Linux com a chamada de sistema fork, utilizando duas bibliotecas: _sys/types.h_ e _unistd.h_. Essa chamada de sistema deve ser inserida no código implementado pelo usuário, que, ao ser compilado e executado, gera uma chamada ao sistema operacional, o qual cria um processo filho com um número identificador único. O processo que gerou a execução do programa é denominado processo pai, e o processo criado com a chamada fork() é denominado processo filho.

No momento da criação, o processo filho é uma cópia do pai e possui os mesmos atributos dele (variáveis, descritores de arquivos, dados, etc.). Após a criação do processo filho, ele é executado, e o que acontece em um processo não ocorre no outro, são processos distintos agora, cada um seguindo seu rumo, tornando-se possível mudar o valor de uma variável em um e isso não alterará o valor desta variável no outro processo.

A função `**fork( )**` retorna um número identificador do processo (PID – _Process Identification_). No trecho de código executado pelo processo filho, PID tem valor igual a 0 (zero). Dentro do processo pai, PID tem valor igual ao identificador do processo filho, retornado pelo sistema operacional. A função fork( ) retorna valor menor do que 0, caso ocorra algum erro na criação do processo.

A função `**getpid( )**` retorna o valor do identificador do processo em execução.

A seguir, apresenta-se um código, no qual é criado um processo filho com a chamada fork( ):

[![](https://ampli-images.s3.amazonaws.com/production/a645e52d-aa96-4083-857d-01dff4b76072/original)](https://ampli-images.s3.amazonaws.com/production/a645e52d-aa96-4083-857d-01dff4b76072/original)