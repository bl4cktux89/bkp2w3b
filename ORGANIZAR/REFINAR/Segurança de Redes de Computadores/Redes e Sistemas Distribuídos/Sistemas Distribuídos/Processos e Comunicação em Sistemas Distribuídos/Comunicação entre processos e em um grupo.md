[![](https://ampli-images.s3.amazonaws.com/production/9169a109-0cbd-4481-b2b3-edb9b0f770fe/original)](https://ampli-images.s3.amazonaws.com/production/9169a109-0cbd-4481-b2b3-edb9b0f770fe/original)

Após a criação dos processos, eles são executados de forma independente e possuem regiões de memória independentes. Entretanto, há aplicações que necessitam trocar dados (comunicação) entre processos ou entre _threads_. Para haver comunicação entre processos, é necessária a utilização de mecanismos específicos. O sistema operacional implementa “canais” de comunicação entre processos em um mesmo computador (tais canais podem ser implícitos ou explícitos) ou em computadores diferentes.

A figura abaixo ilustra a comunicação entre dois processos, que estão em uma mesma máquina, gerenciados pelo mesmo sistema operacional. A comunicação entre processos através de chamadas de sistema pode ocorrer com o uso de _pipes_ ou alocação de memória compartilhada.

[![](https://ampli-images.s3.amazonaws.com/production/b398f724-309c-456f-b1a2-1cfac90b2056/original)](https://ampli-images.s3.amazonaws.com/production/b398f724-309c-456f-b1a2-1cfac90b2056/original)

Canal de comunicação entre dois processos. Fonte: elaborada pela autora.

A próxima figura ilustra o processo 1 na máquina 1 se comunicando com o processo 2 na máquina 2 através de chamadas a funções de uma biblioteca de passagem de mensagens, como MPI.

[![](https://ampli-images.s3.amazonaws.com/production/af6c6558-bb19-46b2-b639-6b76b6956bc8/original)](https://ampli-images.s3.amazonaws.com/production/af6c6558-bb19-46b2-b639-6b76b6956bc8/original)

Processos em máquinas diferentes se comunicando por passagem de mensagens. Fonte: elaborada pela autora.

O modelo de passagem de mensagens entre processos possui a operação básica send-receive. Outras operações de comunicação, como _broadcast, reduction, scatter e gather_, são derivadas da básica.

A operação _send-receive_ ocorre somente entre dois processos (figura abaixo). Um processo envia o dado e o outro processo recebe o dado.

[![](https://ampli-images.s3.amazonaws.com/production/4caacf73-727f-498f-a619-c5f1375992c2/original)](https://ampli-images.s3.amazonaws.com/production/4caacf73-727f-498f-a619-c5f1375992c2/original)

Operação send-receive. Fonte: elaborada pela autora.

A operação de _broadcast_ é uma operação entre um grupo de processos conhecidos. Consiste no envio de um dado presente em um processo para os demais processos do mesmo grupo.

[![](https://ampli-images.s3.amazonaws.com/production/ada27297-e03e-407e-878a-874c2c38ded4/original)](https://ampli-images.s3.amazonaws.com/production/ada27297-e03e-407e-878a-874c2c38ded4/original)

Operação broadcast. Fonte: elaborada pela autora.

Na figura acima, o processo 1 envia o dado para os demais processos do mesmo grupo de processos. Ao final da comunicação, todos os processos do grupo conhecem o dado.

Para implementar aplicações que utilizem a troca de mensagens entre processos, existem bibliotecas, como _sockets_, sobre as quais trataremos posteriormente, e MPI (_Message Passing Interface_) (OPENMPI, 2021; TANENBAUM; STEEN, 2007).

MPI é um padrão de comunicação que permite a troca de mensagens entre processos pertencentes a um grupo de processos criado no início da execução do programa. Cada processo recebe um identificador único dentro deste grupo, facilitando a comunicação entre pares de processos ou grupo de processos. É possível identificar qual é o processo emitente e o receptor da mensagem. Dentro de um mesmo processo, é possível criar _threads_, que podem se comunicar através de troca de mensagens ou acesso à memória compartilhada.

Na figura abaixo, há quatro _threads_ executando em um mesmo processo. Esses _threads_ compartilham memória e trocam informação através do acesso à memória compartilhada. Para gerenciar o acesso à memória compartilhada, são utilizadas bibliotecas, como OpenMP (OPENMP, 2021) e PosixThreads (BARNEY, 2021).

[![](https://ampli-images.s3.amazonaws.com/production/39654a73-0a1b-45bf-98de-e06e187dccf5/original)](https://ampli-images.s3.amazonaws.com/production/39654a73-0a1b-45bf-98de-e06e187dccf5/original)

Threads de um mesmo processo acessando a memória compartilhada. Fonte: elaborada pela autora.