  

### Introdução.

A teoria das filas é um ramo da probabilidade que estuda a formação de filas, através de análises matemáticas precisas e propriedades mensuráveis das filas (PRADO, 2014). Ela provê modelos para demonstrar previamente o comportamento de um sistema que ofereça serviços cuja demanda cresce aleatoriamente (ADAN; RESING, 2015), tornando possível dimensioná-lo de forma a satisfazer os clientes e ser viável economicamente para o provedor do serviço, evitando desperdícios e gargalos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/2/264290/12907.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/2/264290/12907.png)

Formação de filas.

### Por que existem filas?

Segundo Prado (2014) sempre que temos um serviço sendo prestado, os recursos necessários em alguns momentos podem não estar disponíveis devido ao grande volume de requisições e aumento das demandas, não é correto imaginar que teremos recursos infinitos para qualquer tamanho de demanda, ou seja, que cada solicitação disponha de todos os recursos individualmente e exclusivamente, por exemplo uma rua não é exclusiva  para uma única pessoa se movimentar ou ainda que se tenha um supermercado para seu abastecimento exclusivo: **recursos limitados devem ser compartilhados.**Sempre que houver menos recursos que o desejado, haverá uma fila. Exemplo: ao se ter apenas uma impressora para diversos usuários, haverá uma fila para impressão. Com isso, podemos entender que, ao se compartilhar um recurso, pode acontecer que se precise usá-lo e ele esteja ocupado, gerando a necessidade de esperar e, com isso, as filas.

### Aplicações.

Existem diversas aplicações da teoria das filas, que podem ser encontradas na literatura de probabilidade, ou seja, é um ramo da probabilidade que estuda a formação de filas, através de análises matemáticas utilizando  propriedades mensuráveis das filas, sendo assim aplicável à pesquisa operacional e na engenharia (ADAN;.RESING, 2015). Entre elas podemos citar:

- **Fluxo de tráfego** (aviões, carros, pessoas, comunicações).
- **Escalonamento** (pacientes em hospitais, programas em computadores).
- **Prestação de serviços** (bancos, correios, lanchonetes).
- **Processos em comunicação de dados** (Processos esperando para receber a CPU; pacotes que chegam num roteador para serem encaminhados).

### Sistemas de filas.

Uma fila ocorre sempre que a procura por um determinado serviço é maior que a capacidade do sistema de prover este serviço.

Um sistema de filas pode ser definido como clientes chegando, esperando pelo serviço (se não forem atendidos imediatamente) e saindo do sistema após terem sido atendidos. O conceito pode abranger, conforme cita Adan e Reising (2015) por exemplo, processos esperando para receber a CPU; pacotes que chegam a um roteador para serem encaminhados; pessoas esperando no caixa do supermercado, etc.

**DEFINIÇÕES.**

- Redes de Filas.
    - Conjunto de entidades interligadas que oferecem serviços (centros de serviços) e de usuários (clientes).
- Centro de Serviços.
    - Conjunto de entidades interligadas que oferecem serviços (centros de serviços) e de usuários (clientes).
- Fila
    - Representa os clientes que estão esperando pelo serviço, juntamente com os que estão sendo atendidos pelos servidores.
- Fila de Espera
    - Somente os clientes que estão aguardando pelo serviço.

### **Componentes de um sistema de filas.**

Um sistema de filas, segundo Prado (2014) consiste no **processo de chegada**, da **distribuição do tempo de serviço**, do **número de servidores**, da **capacidade do sistema**, da **população de usuários** e da **disciplina de atendimento**.

### **Processo de chegada.**

- O processo de chegada indica qual o padrão de chegada dos clientes no sistema. Apresenta comportamento estocástico, ou seja, as chegadas ocorrem no tempo e no espaço de acordo com as leis da probabilidade; assim, é preciso conhecer qual a distribuição de probabilidade que descreve os tempos entre as chegadas dos clientes.
- **A distribuição mais comum é a de Poisson, ou seja, os tempos entre as chegadas são exponencialmente distribuídos. Entre outras distribuições, estão a de Erlang, hiperexponencial e arbitrária (Haviv, 2013).**
- Clientes podem chegar simultaneamente (chegada em batch). Se for possível, é necessário também saber a distribuição de probabilidade do tamanho do batch. A reação do cliente na fila pode variar. Ele pode esperar independentemente do tamanho da fila, também pode decidir não entrar no sistema caso a fila esteja muito grande (cliente decepcionado), ele pode esperar na fila mas depois de um tempo desistir e sair do sistema, e também pode mudar de uma fila para outra em sistemas com servidores paralelos.
- O padrão de chegada de clientes em função do tempo pode ser permanente; nesse caso o padrão não muda no tempo, ou seja, a distribuição de probabilidade que descreve as chegadas é independente do tempo. Também pode ser não-permanente, isto é, o padrão de chegada muda com o tempo. Por exemplo, a chegada de clientes diminui no horário de almoço.

### **Distribuição do tempo de serviço**

- Assim como no processo de chegada, também é necessário conhecer a distribuição de probabilidade do tempo de serviço, sendo válidas as mesmas distribuições apresentadas (Haviv, 2013).
- Os serviços podem também ser simples ou batch.
- O estado pode ser independente: o processo de atendimento não depende do número de clientes esperando pelo serviço. Em contrapartida, em um estado dependente, o processo de atendimento muda de acordo com o número de clientes na fila. Por exemplo, um servidor pode trabalhar mais rápido quando a fila aumenta ou, ao contrário, ficar confuso e então mais lento.
- Da mesma forma que no processo de chegada, o padrão de serviço pode variar de acordo com o tempo. Por exemplo, a experiência adquirida com o serviço pode aumentar a produtividade; o cansaço, por outro lado, pode diminuí-la. Caso não haja varação o padrão é estacionário.

### **Número de servidores**

- Esse componente é também conhecido como número de canais de serviço. Indica a quantidade de "pontos de atendimento" do sistema, de forma a servir aos clientes paralelamente. Quando um sistema possui mais de um servidor (multiservidor ou multicanal), ele pode apresentar duas variações. Em um sistema de fila única, existe uma única fila para todos os servidores, como em um caixa de banco. Em um sistema de múltiplas filas, existe uma fila para cada servidor, como em um caixa de supermercado.
- Quando existirem infinitos servidores, ou seja, todo cliente que chega é atendido imediatamente, temos um caso especial conhecido como "Centro de atraso".

### **Capacidade do sistema.**

- Representa o número máximo de clientes que o sistema suporta, incluindo os que estão em espera e os que estão sendo atendidos. A capacidade pode ser infinita (mais fácil de analisar) ou finita (por exemplo, número limitado de buffers em um roteador). Se a capacidade for finita, quando o sistema estiver lotado nenhum cliente pode entrar até que um cliente saia do sistema, liberando espaço.

### **População de usuários**

- Esse componente indica o número potencial de clientes que podem chegar a um sistema. Pode ser finita ou infinita.

### **Disciplina de atendimento**

- Descreve a forma como os clientes saem da fila de espera para serem atendidos. Algumas disciplinas são:
    - _**FCFS (FirstCome, FirstServed):**_ Primeiro a Chegar, Primeiro a ser Atendido. Disciplina mais comum, inclusive na vida diária.
    - _**FIFO (FirstIn, FirstOut):**_ Primeiro a Entrar, Primeiro a Sair.
    - _**LCFS (LastCome, FirstServed):**_ Último a chegar, Primeiro a ser Atendido
    - _**LIFO (LastIn, FirstOut):**_ Último a Chegar, Primeiro a Sair. Aplicável em sistemas em que o item mais recente é mais fácil de ser recuperado, como por exemplo em sistemas de controle de estoque.
    - _**Round-Robin**_(algoritmo): cada cliente recebe uma fatia de tempo do servidor (quantum), dentro da qual é atendido. Após o término do quantum, se a atividade não foi completada, o cliente é retirado e outro passa a ser atendido. Posteriormente, o cliente que foi interrompido retorna ao servidor e continua a sua atividade. É muito comum em escalonamento de processos da CPU.
- Fila com prioridade: a cada cliente é atribuída uma prioridade; clientes com maior prioridade têm preferência no atendimento. Pode ser de dois tipos:
    - Preemptivo: o cliente com maior prioridade é atendido imediatamente, interrompendo o atendimento ao cliente com menor prioridade. Ao terminar, o cliente de menor prioridade volta a ser atendido, podendo continuar o processo de onde parou ou então reiniciá-lo.
    - Não-preemptivo: o cliente com maior prioridade é colocado no início da fila, recebendo o serviço somente quando o cliente em atendimento sai do sistema, mesmo se este for de prioridade mais baixa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/4/8/364827/28977.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/4/8/364827/28977.png)

Componentes básicos de uma Fila

### **Tipos de Atendimento em Filas**

- Fila única e atendimento único - exemplo a
- Fila única e atendimento múltiplo em paralelo - exemplo b
- Múltiplas filas em série e atendimentos multiplos em paralelo - exemplo c

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/8/0/8054/i01_874.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/8/0/8054/i01_874.jpg)

Exemplos de tipos de Filas

### **Notação de Kendall**

De uma forma geral afirma Prado (2014), que um modelo de filas pode ser representado utilizando a notação criada por David Kendall, a qual é apresentada abaixo.

**A/B/C/K/m/Z**

**A:** distribuição do tempo entre chegadas.

**B:** distribuição do tempo de serviço.

**Valores para A** **e B**

**Distribuições de probabilidade**

- Determinístico (D)
- Exponencial (M)
- Uniforme (U)
- Arbitrária ou Geral (G)
- Erlang (_E__k_)
- Hiperexponencial (_H__k_)

**C:** número de servidores.

**K:** número máximo de clientes permitidos no sistema.

- K é omitido quando: K = infinito.

**m:** tamanho da população.

- m é omitido quando: m = infinito.

**Z:** disciplina de atendimento.

- Z se omite quando: Z = FIFO

  

![[Screenshot_from_2022-03-21_21-45-57.png]]

![[Screenshot_from_2022-03-21_21-46-20.png]]

![[Screenshot_from_2022-03-21_21-46-36.png]]

![[Screenshot_from_2022-03-21_21-46-47.png]]

![[Screenshot_from_2022-03-21_21-46-57.png]]

![[Screenshot_from_2022-03-21_21-47-10.png]]

![[Screenshot_from_2022-03-21_21-47-20.png]]

### **Exemplos para a notação de Kendall**

### Exemplo 1:

![[Screenshot_from_2022-03-21_21-50-17.png]]

- O intervalo entre chegadas sucessivas é distribuído exponencialmente.
- Os tempos de serviço são exponencialmente distribuídos.
- Há três servidores.
- A fila possui buffers para 10 usuários. Isto é, 3 usuários em atendimento e 7 esperando por serviço. Enquanto o número de usuários estiver em seu valor máximo, 10, todos os usuários que chegarem serão perdidos até que o comprimento da fila diminua.
- Há um total de 1200 usuários que podem ser atendidos.
- A disciplina de atendimento é _first_ _come,_ _first_ _served_.

### Exemplo 2:

![[Screenshot_from_2022-03-21_21-51-14.png]]

- Processo de chegada exponencial (Markoviano)
- Distribuição dos tempos de serviço arbitrária (Geral)
- Oito servidores
- Capacidade para cem clientes
- População de dois mil clientes
- Disciplina de atendimento "Último a Chegar, Primeiro a ser Servido"

### Exemplo 3:

![[Screenshot_from_2022-03-21_21-52-06.png]]

- Processo de chegada determinístico
- Distribuição dos tempos de serviço exponencial (Markoviano)
- Um servidor
- Capacidade ilimitada
- População infinita
- Disciplina de atendimento Round-Robin

Em muitas situações só os três primeiros símbolos são utilizados, de maneira que, é assumido que o sistema tem capacidade ilimitada e possui uma disciplina FCFS.

![[Screenshot_from_2022-03-21_21-52-42.png]]

### Relações básicas sobre filas

Na sequência declaramos alguns termos que serão muito utilizados nos próximos capítulos, que abordão o assunto sobre teoria das filas de uma forma matemática.

- **Número médio de clientes na fila de espera – NF;**
- **Número médio de clientes no sistema – NS;**
- **Número médio de clientes em atendimento – NA;**
- **Tempo médio de permanência no Sistema – TS;**
- **Tempo médio de permanência na Fila de espera – TF;**
- **Tempo Médio de atendimento – TA;**

Duas relações serão muito úteis no estudo de filas, sendo assim são citadas abaixo:

1. **NS = NF + NA**
2. **TS = TF + TA**