[![](https://ampli-images.s3.amazonaws.com/production/fc39e2bb-4e49-42eb-a841-bb17463ba7b2/original)](https://ampli-images.s3.amazonaws.com/production/fc39e2bb-4e49-42eb-a841-bb17463ba7b2/original)

As redes estão por toda parte e servem de base para muitos serviços cotidianos que agora consideramos naturais, por exemplo, a internet e a _World Wide Web_ associada a ela, a pesquisa na web, os jogos on-line, os e-mails, as redes sociais, o e-commerce, etc. (COULOURIS _et al_., 2013). Os sistemas distribuídos podem ser considerados como uma solução mais robusta em resposta aos sistemas puramente de rede, isso graças ao componente conhecido como _middleware_. Ele é um dos fatores principais para o bom funcionamento de aplicações distribuídas.

_Middleware_ é uma camada oculta, um software, o qual se encontra entre os sistemas operacionais e os aplicativos (programas criados) que são executados neles. Portanto, é uma camada central, que permite o gerenciamento e a comunicação de dados para o funcionamento de aplicativos distribuídos. O _middleware_ funciona como uma camada de tradução para interligar o sistema operacional com os programas (COULOURIS _et al_., 2013).

A figura abaixo ilustra as camadas que compõem um sistema distribuído.

[![](https://ampli-images.s3.amazonaws.com/production/993c7fdb-cbfa-499f-8d18-0c4615faa648/original)](https://ampli-images.s3.amazonaws.com/production/993c7fdb-cbfa-499f-8d18-0c4615faa648/original)

Camadas que compõem um sistema distribuído. Fonte: elaborada pelo autor.

Alguns exemplos são: _middlewares_ de banco de dados e servidores WEB e ferramentas de mensageria. As mais diversas redes sociais que utilizamos hoje em dia, com conteúdos multimídias, são exemplos de sistemas distribuídos, assim como sites de pesquisas e plataformas de vídeos on line.

A figura abaixo ilustra um exemplo da atuação da camada _middleware_ perante diferentes computadores (máquinas), aplicações e sistemas operacionais. Podemos observar que ela liga aplicações A, B e C com os sistemas operacionais 1, 2, 3 e 4. Essas aplicações e sistemas operacionais estão em diferentes computadores (1, 2, 3 e 4). Eles interagirão entre si para a execução de um sistema distribuído, e isso só é possível devido à camada do sistema distribuído, chamada _middleware_.

[![](https://ampli-images.s3.amazonaws.com/production/92d32745-e1dd-4871-ac63-25c56ac56c9e/original)](https://ampli-images.s3.amazonaws.com/production/92d32745-e1dd-4871-ac63-25c56ac56c9e/original)

Middleware e sistemas distribuídos. Fonte: elaborada pelo autor.

______

**🔁Assimile**

Em uma aplicação escrita em diferentes máquinas, com sistemas operacionais diferentes, é necessária a comunicação entre essas máquinas. Cada uma delas fornece a própria representação de dados e formas de comunicação e, nesse caso, o _middleware_ atua como uma camada de tradução para que seja possível a comunicação correta entre as máquinas para o funcionamento do sistema.

______

**Computação em** _**cluster**_ **e computação em** _**grid**_

Os sistemas distribuídos podem ser classificados em diferentes categorias, de acordo com sua arquitetura e finalidade, sendo os mais comuns: computação em _cluster_ e computação em _grid_.

_**Cluster**_

Agora, falaremos um pouco sobre algumas características da computação em cluster. Esse tipo de computação é formado por um conjunto de máquinas com hardwares semelhantes, ou seja, as máquinas que compõem o cluster possuem características homogêneas (TANENBAUM; STEEN, 2017). O conjunto de máquinas que compõem o _cluster_ são ligadas por rede local (LAN).

Quando falamos da parte de software da computação em cluster, temos algumas características importantes. Na maioria das vezes, o sistema operacional entre as máquinas que formam o cluster é equivalente. Além disso, é frequente que um único programa funcione de forma paralela, ou seja, um programa é subdividido em partes menores, e cada parte é executada em uma máquina (ou nó) desse cluster, de forma distribuída, a fim de obter um aumento significativo de desempenho e, consequentemente, executar determinada tarefa em menos tempo. Geralmente, as máquinas desse tipo de sistema são fortemente acopladas em suas ligações e, muitas vezes, podem até compartilhar a mesma memória RAM entre várias máquinas.

Há sempre uma das máquinas que chamamos de nó mestre, isto é, a máquina principal que gerencia o funcionamento da aplicação entre todos os nós. O nó mestre faz a interface com o usuário, aloca tarefas e administra a fila de tarefas. A figura abaixo ilustra um _cluster_, que se encontra dentro do círculo pontilhado.

[![](https://ampli-images.s3.amazonaws.com/production/b58b5da8-fc92-4d78-86e9-f9d4d85d21f9/original)](https://ampli-images.s3.amazonaws.com/production/b58b5da8-fc92-4d78-86e9-f9d4d85d21f9/original)

Exemplo de cluster. Fonte: elaborada pelo autor.

_**Grid**_

Agora que já conhecemos a computação em _cluster_, falaremos da computação em _grid_, ou grades, e apontaremos algumas características. Conforme Tanenbaum e Steen (2008), esse tipo de computação é formado por um conjunto de máquinas com características diferentes, podendo o hardware e os sistemas operacionais serem de fabricantes diferentes. Com isso, temos uma característica heterogênea na computação em grid: essencialmente, um sistema de computação em _grid_ interliga vários _clusters_. Um exemplo de _grid_ é o CINEGRID, que trabalha no desenvolvimento de ferramentas colaborativas multimídia (CINEGRID BRASIL, [s.d.]). Na Figura 3.10, vemos uma parte desse _grid_, com as ligações entre _clusters_ no Brasil; mas saiba que o CINEGRID interliga outros centros de pesquisa, em várias partes do mundo.

[![](https://ampli-images.s3.amazonaws.com/production/4fe8a2fc-840f-4cbf-a098-c247671d1e62/original)](https://ampli-images.s3.amazonaws.com/production/4fe8a2fc-840f-4cbf-a098-c247671d1e62/original)

Exemplo de grid - CINEGRID. Fonte: CINEGRID BRASIL ([s.d.], [s.p.]).

**Diferenças entre** _**clusters**_ **e** _**grids**_

Muitas vezes, pode parecer que _clusters_ e _grids_ são a mesma coisa, mas existe uma característica fundamental que difere esses dois tipos de sistemas distribuídos. Para facilitar o entendimento das diferenças entre eles, podemos pensar que _clusters_ são sistemas homogêneos, ou seja, são criados para executarem alguma tarefa específica que, em geral, necessita de um alto poder de processamento e, portanto, levaria muito tempo para ser executada em um computador convencional.

______

**📝****Exemplificando**

Um exemplo de tarefa que leva muito tempo para ser executada é o treinamento de redes neurais artificiais de aprendizagem profunda (_deep learning_) para uso em ferramentas de chat on-line. Nesse tipo de aplicação, os chamados _bots_ – que, nesse caso, são o resultado da rede neural treinada – conversam com e respondem a questionamentos dos clientes (usuários) do serviço de chat on-line de uma determinada empresa. Recentemente, muitos sistemas bancários têm utilizado esse tipo de recurso. Supondo que para executar o treinamento desse tipo de rede em computador convencional seriam necessários dois dias, ao executarmos essa tarefa em um _cluster_, esse treinamento poderia ser realizado em questão de minutos.

______

Para diminuirmos o tempo de processamento, poderíamos executar esse tipo de tarefa (treinamento de redes neurais artificiais de aprendizagem profunda) em um computador com alto poder de processamento, porém o custo desse tipo de computador pode tornar essa opção inviável. Segundo o _Lawrence Livermore National Laboratory_ (2018), o sequoia é utilizado para realizar simulações numéricas referentes à física de armas nucleares. Assim sendo, este computador é um _cluster_ homogêneo, visto que executa uma pesquisa de finalidade específica.

Por sua vez, podemos pensar que os _grids_ têm uma abordagem heterogênea, ou seja, são criados para executarem diferentes tarefas, de certa maneira relacionadas entre si, formando um centro de pesquisas de caráter multidisciplinar. Uma maneira ainda mais simples de entender essa característica é “pensar” em um _grid_ como um conjunto de dois ou mais _clusters_, cada um deles responsável por um certo tipo de pesquisa.