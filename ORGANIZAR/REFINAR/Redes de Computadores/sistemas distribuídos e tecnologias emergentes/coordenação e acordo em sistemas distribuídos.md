As gerações de sistemas distribuídos levam em conta que os vários componentes de um sistema são inerentemente distribuídos e que o problema real do desenvolvimento dos sistemas se encontra na coordenação das atividades dos diferentes componentes.

A ênfase passa a ser na coordenação de atividades entre esses componentes. Dessa forma, muitos Sistemas Distribuídos convencionais estão incorporando mecanismos que desempenham papel fundamental em Sistemas Baseados em Coordenação.

Na abordagem dos sistemas baseados em coordenação, veremos que é clara a separação existente entre computação e coordenação. Se considerarmos um sistema distribuído como um conjunto de processos, então a parte de computação de um sistema distribuído é formada pelos processos, sendo cada um preocupado com uma atividade computacional específica, que é executada independentemente das atividades de outros processos.

O que temos é que a parte da coordenação de um sistema distribuído manipula a comunicação e a cooperação entre processos.

Em sistemas distribuídos baseados em coordenação, o foco está no modo como ocorre a coordenação entre os processos. Cabri et al. (2000) fornecem  uma taxonomia de modelos de coordenação para agentes móveis, que também pode ser aplicada a muitos outros tipos de sistemas distribuídos.

Adaptando essa terminologia a sistemas distribuídos em geral, fazemos uma distinção entre modelos conforme duas dimensões diferentes: **temporal e referencial.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314371/20551.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314371/20551.jpg)

Taxonomia de modelos de coordenação.

Fonte: Figura 13.1 - pag. 357 do Livro Sistemas Distribuídos - Princípios e Paradigmas

Quando o acoplamento de processos é temporal e referencial, a coordenação ocorre de modo direto, denominado **coordenação direta**, onde o acoplamento referencial aparece na forma de referenciamento explícito em comunicação, sendo que um processo só pode se comunicar se souber os nomes ou identificadores dos outros processos com os quais quer trocar informações.

O acoplamento temporal significa que ambos os processos em comunicação têm de estar ligados e em funcionamento.

Um tipo diferente de coordenação ocorre quando os processos são desacoplados temporalmente, o que é chamado de **coordenação de caixa postal**, quando não é necessário que os dois processos comunicantes estejam executando ao mesmo tempo para que a comunicação ocorra. Essa comunicação é efetuada por meio da colocação de mensagens em uma caixa postal, mas é necessário endereçar explicitamente a caixa postal que conterá as mensagens que deverão ser trocadas, quando ocorre um acoplamento referencial.

A combinação de sistemas de desacoplamento referencial e sistemas de acoplamento temporal forma o grupo de modelos para **coordenação orientada a reunião**.

Em sistemas de desacoplamento referencial os processos não conhecem uns aos outros explicitamente, ou seja, quando um processo quer coordenar suas atividades com outros processos, ele não pode referenciar outro processo. Em vez disso, há o conceito de uma reunião na qual os processos se agrupam temporariamente para coordenar suas atividades, fazendo co que os processos que se reúnem sejam executados simultaneamente.

Sistemas baseados em reunião costumam ser implementados por meio de eventos, como ocorre com os sistemas suportados por sistemas distribuídos baseados em objetos.

Um aspecto importante de sistemas baseados em coordenação é que a comunicação ocorre pela descrição das características de itens de dados que devem ser trocados, momento em que a nomeação desempenha um papel fundamental, uma vez que em muitos casos os itens de dados não são identificados explicitamente por remetentes e receptores.

Vamos considerar que itens de dados são descritos por uma série de atributos, assim, um item de dados é publicado quando é oferecido para outros processos para leitura. Para isso, é preciso passar para o middleware uma subscrição que contenha uma descrição dos itens de dados nos quais o subscritor está interessado.

Essa descrição normalmente é composta por alguns pares, como: **atributo e valor**, combinados com outros pares, **atributo e faixa**, e neste caso esperasse que o atributo especificado adote valores dentro de uma faixa especificada. Às vezes é possível dar descrições usando todos os tipos de predicados formulados sobre os atributos, o que é semelhante a consultas do tipo SQL.

Existem situações na qual é preciso associar subscrições com itens de dados, como mostra a figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314372/20554.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314372/20554.jpg)

Princípio da troca de itens de dados entre publicadores e subscritores

Fonte: Figura 13.2 - pag. 359 do Livro Sistemas Distribuídos - Princípios e Paradigmas

Quando a associação é bem sucedida, há dois cenários possíveis, no primeiro, o Middleware pode decidir repassar os dados publicados para seu conjunto de subscritores existentes no momento em questão, que contém processos que possuem uma subscrição compatível.

Como alternativa, o Middleware também pode repassar uma notificação, quando então os subscritores podem executar uma operação de leitura para recuperar o item de dados publicado.

Nos casos em que os itens de dados são imediatamente repassados para os subscritores, o middleware não oferecerá armazenamento de dados. O armazenamento ou é manipulado explicitamente por um serviço separado ou fica a cargo dos subscritores, ou seja, temos um sistema de desacoplamento referencial, porém de acoplamento temporal.

Essa situação é diferente quando são enviadas notificações e os subscritores precisam ler explicitamente os dados publicados, e o middleware terá obrigatoriamente de armazenar itens de dados. Nessas situações, há operações adicionais para gerenciamento de dados.

**ACORDO EM SISTEMAS DISTRIBUÍDOS**

Para iniciarmos a discussão sobre acordo em sistemas distribuídos vamos ver alguns conceitos sobre tolerância a falhas.

Um objetivo importante do projeto de sistemas distribuídos é construir o sistema de modo que ele possa se recuperar automaticamente de falhas parciais sem afetar o desempenho global, assim, sempre que ocorrer uma falha, o sistema deve continuar a de maneira aceitável, pois deve tolerar falhas e continuar a funcionar mesmo na presença de uma falha.

Para entender o papel da tolerância a falha em sistemas distribuídos, precisamos entender o que significa tolerar falhas. Nisso há forte relação entre ser tolerante a falha e os denominados sistemas confiáveis. Baseados nessas premissas, podemos analisar os seguintes requisitos;

- Disponibilidade;

- Confiabilidade;

- Segurança; e,

- Capacidade de manutenção.

A **Disponibilidade** é definida como a propriedade de um sistema estar pronto para ser usado imediatamente, refere-se à probabilidade de um sistema estar funcionando corretamente em qualquer momento determinado e estar disponível para executar suas funções em nome de seus usuários. Podemos dizer que um sistema de alta confiabilidade é aquele que mais provavelmente estará funcionando em dado instante no tempo.

A **Confiabilidade** refere-se à propriedade de um sistema poder funcionar continuamente sem falha. Um sistema de alta confiabilidade é aquele que mais provavelmente continuará a funcionar sem interrupção durante um período de tempo relativamente longo.

A **Segurança** trata da situação em que se um sistema deixar de funcionar corretamente durante certo tempo, nada de desastroso acontecerá. Vejamos no caso de um sistema que fará o controle de um foquete que irá levar astronautas ao espaço. Se esse sistema de controle falhar, mesmo que temporariamente, os efeitos poderiam ser catastróficos. A segurança tem a responsabilidade de garantir a construção de sistemas seguros.

A **Capacidade de Manutenção** se refere à facilidade com que um sistema que falhou pode ser consertado. Neste item, se as falhas puderem ser detectadas e reparadas automaticamente, a capacidade de manutenção irá colaborar para se ter um alto grau de disponibilidade.

Muitas vezes sistemas confiáveis também devem oferecer alto grau de segurança, especialmente quando se trata de questões de integridade. Diz-se que um sistema apresenta defeito quando não pode cumprir suas promessas, ou seja, se um sistema distribuído é projetado para oferecer a seus usuários uma série de serviços e esse sistema falha quando um desses serviços não puder ser fornecido.

A construção de sistemas confiáveis está intimamente relacionada com o controle de falhas, o que significa que um sistema pode prover seus serviços mesmo na presença de falhas.

Adotaremos a premissa de que processos não se juntam pra produzir um resultado errado. Mas as coisas se tornam complicadas quando exigirmos que um grupo de processos chegue a um acordo, o que se faz necessário em muitos casos.

Essa dificuldade parte da dificuldade que um grupo de processos terá em eleger um coordenador, decidir a validação ou não de uma transação, repartir tarefas entre operários e realizar a sincronização.

Quando a comunicação e os processos são todos perfeitos, chegar a tal acordo costuma ser direto, mas quando não são, surgem problemas.

O objetivo geral de algoritmos de acordo distribuídos é que todos os processos que não apresentam falha cheguem a um consenso sobre alguma questão e estabeleçam esse consenso dentro de um número finito de etapas.

O problema se torna complicado pelo fato de que premissas diferentes sobre o sistema subjacente requerem soluções diferentes, considerando que existam soluções para elas.

Turek e Sasha (1992) distinguem os seguintes casos:

1- Sistemas síncronos x sistemas assíncronos.

Um sistema é síncrono se, e somente se, sabe-se que os processos funcionam no mesmo passo. Isso significa que deve haver alguma constante c >= 1 tal que, se qualquer processador tiver efetuado c + 1 etapas, cada um dos outros processos terá efetuado no mínimo uma etapa. Caso contrário, é tratado como assíncrono.

2- O atraso de comunicação é limitado ou não.

O atraso é limitado se, e somente se, soubermos que toda mensagem é entregue dentro de um tempo máximo global e predeterminado.

3- A entrega de mensagens é ordenada ou não.

Distinguimos a situação em que mensagens do mesmo remetente são entregues na ordem em que foram enviadas da situação em que não temos mais garantias.

4- A transmissão de mensagens é feita em Unicast ou Multicast.

Ocorre que chegar a um acordo só é possível para as situações apresentadas na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314374/20555.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314374/20555.jpg)

Circunstâncias sob as quais se pode chegar a um acordo distribuído.

Fonte: Figura 8.3 - pag. 201 do Livro Sistemas Distribuídos - Princípios e Paradigmas

Em todos os outros casos, pode-se mostrar que não existe nenhuma solução, sendo que, na prática, a maioria dos sistemas distribuídos adotam como premissa que os processos se comportam de modo assíncrono, que a comunicação é Unicast e que os atrasos de comunicação não são limitados.

Por isso, precisamos utilizar entrega ordenada e confiável de mensagens, tal como a oferecida por TCP, o que é demonstrado na figura acima que ilustra a natureza não trivial do acordo distribuído quando os processos podem falhar.

O problema foi estudado pela primeira vez por Lamport et al. (1982) e é conhecido como **problema do acordo bizantino**, referindo-se às numerosas guerras em que vários exércitos se envolveram para chegar a um acordo sobre o contingente de tropas para enfrentar generais traidores, tenentes conspiradores e assim por diante.

Lamport et al. (1982), considerou que neste caso, os processos são síncronos, as mensagens são unicast e a ordenação é preservada e o atraso de comunicação é limitado.

Vamos supor que haja **N** processos e que cada processo **i** forneça um valor **v****i** aos outros. O objetivo é permitir que cada processo construa um vetor **V** de comprimento **N** tal que, se o processo **i** não for faltoso, então **V[i] = v****i**. Caso contrário, **V[i]** é indefinido. Consideremos que exista no máximo **k** processos faltosos.

Na figura abaixo ilustramos o funcionamento do algoritmo para o caso de **N = 4** e **k = 1.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314376/20556.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/1/4/3/314376/20556.jpg)

Problema de acordo bizantino para três processos não faltosos e um faltoso

Fonte: Figura 8.4 - pag. 201 do Livro Sistemas Distribuídos - Princípios e Paradigmas

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/1/0/321012/22594.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/1/0/321012/22594.png)

Problema dos Generais Bizantinos

Fonte: Montado a partir do problema bizantino

Na figura:

(a) Cada processo envia seu valor aos outros.

(b) Vetores que cada processo monta com base em (a).

(c) Vetores que cada processo recebe na etapa 3.

O algoritmo funciona em quatro etapas:

Na etapa 1, todo processo sem falha i envia vi a todos os outros processos usando unicast confiável. Os processos faltosos podem enviar qualquer coisa, mas como estamos usando multicast, eles podem enviar valores diferentes a processos diferentes (na figura vemos que o processo 1 reporta 1, o processo 2 reporta 2, o processo 3  mente para todo mundo, dando x, y, z, respectivamente, e o processo 4 reporta um valor de 4).

Na etapa 2, os resultados dos anúncios da etapa 1 são reunidos sob a forma dos vetores indicados no item (b) da figura.

A etapa 3, consiste em cada processo transmitir seu vetor (figura b) para todos os processos. Desse modo, todo processo obtém três vetores um para cada um dos outros processos. Aqui o processo 3 também mente, inventando 12 novos valores, de **a** até **l.**

Por fim, na etapa 4, cada processo examina o i-ésimo elemento de cada um dos vetores que acabou de receber. Se qualquer um dois valores tiver uma maioria, ele é colocado no vetor de resultados, se nenhum valor tiver uma maioria, o elemento correspondente do vetor de resultados é marcado como “desconhecido”.

Em seu artigo, Lamport et al. (1982) provaram que, em um sistema com k processos faltosos, pode-se conseguir um acordo somente se estiverem presentes 2k + 1 processos funcionando corretamente, para um total de 3k + 1.

Expresso em termos diferentes, um acordo só é possível se mais do que dois terços dos processos estiverem funcionando adequadamente.

### Conclusão:

A Importância do problema dos generais bizantinos consiste em que um sistema confiável deve ser capaz de lidar com falhas de um ou mais componentes (Tolerância a falhas).

O objetivo do algoritmo de acordo distribuído é que todos os processos que não apresentam falha cheguem a um acordo sobre alguma questão e estabeleçam esse consenso dentro de um número finito de etapas.

Um algoritmo deve ser criado para estabelecer os limites dessas falhas e não permitir que processos que vierem a falhar causem problemas aos processos que não falham.