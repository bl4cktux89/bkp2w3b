A sincronização de relógios está relacionada com a hora atual, bastando que cada nó concorde com uma hora corrente, sem que essa hora seja a mesma que a hora real.

Nos Sistemas Distribuídos os relógios lógicos são responsáveis por identificar as relações causais e cronológicas, utilizando uma classe de algoritmos que se baseiam na sincronização de seus eventos e na consistência interna de seus relógios.

Lamport (1978) entende que a sincronização entre relógios é possível, embora não precisa ser absoluta. E se dois processos não interagirem, não é necessário que seus relógios sejam sincronizados, porque a falta de sincronização não sendo observada, não causaria problemas.

Destaca ainda que, o importante não é que todos os processos concordem com a hora exata, mas com a ordem em que os eventos ocorrem.

Dessa forma, o que importa é se um processo é mais velho ou mais novo que o outro, e não a hora exata em que foram criados.

Os dois principais algoritmos para sincronização de relógios são: os **Relógios de Lamport** e os **Relógios vetoriais**.

**RELÓGIOS LÓGICOS DE LAMPORT**

Para sincronizar relógios lógicos, Lamport definiu uma relação denominada _**“acontece antes**_**”**, onde a expressão _**a**__**-->**__**b**_ (lê-se; **a** acontece antes de **b**) significa que todos os processos concordam que primeiro ocorre o evento **a** e depois o evento **b**.

A relação “_**acontece antes**_” é observada em duas situações:

- Na primeira, se **a** e **b** são eventos do mesmo processo, e **a** ocorre antes de **b**, então _**a**__**-->**__**b**_ é verdadeira.

- Na segunda, se **a** é o evento de uma mensagem enviada por um processo, e **b** é o evento da mensagem recebida por outro processo, então _**a**__**-->**__**b**_ também é verdadeira.

Entretanto, se dois eventos **x** e **y** acontecem em processos diferentes que não trocam mensagens, então os eventos _**x**__**-->**__**y**_ e _**y**__**-->**__**x**_ não são verdadeiros.

Assim, quando acontecem esses tipos de eventos, dizemos que eles são **concorrentes**, onde nada pode ser dito sobre quando esses eventos aconteceram, nem mesmo, para saber qual evento ocorreu em primeiro lugar.

Se analisarmos o algoritmo de Lamport verificamos que os processos P1, P2 e P3 (**a** da figura abaixo) executam em máquinas diferentes, cada um com seu relógio e com velocidade própria.

Cada relógio funciona a uma taxa constante, mas diferentes devido às diferenças nos cristais.

Vejamos o que acontece com o algoritmo de Lamport:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/2/299290/18994.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/2/299290/18994.png)

Relógio Lógico de Lamport

Fonte: Figura 6.9, Pág. 148, do Livro "Sistemas Distribuídos - Princípios e Paradigmas".

Na figura **“a”:**

- no tempo **6**, o processo **P****1** envia a mensagem **m****1** ao processo **P****2**
    
    .
    
- o relógio no processo **P****2** marca **16**, quando a mensagem chega.
- se a mensagem transportar com ela o tempo anterior **6**, o processo **P****2** concluirá que ela levou **10** pulsos para fazer sua jornada (o que é ).
    
    coerente
    
- a mensagem **m****2** do processo **P****2** até **P****3** também leva **16** pulsos ().
    
    coerente
    
- agora considere a mensagem **m****3** que sai do processo **P****3** em **60** e chega em **P****2** em **56** ().
    
    incoerente
    
- o mesmo ocorre com a mensagem mque sai do processo P indo a P que sai de 64 e chega em 54 ().
    
    4
    
    2
    
    1
    
    incoerente
    

É essa situação que deve ser evitada.

Na figura **“b”:**

A solução de Lamport resulta na relação **“acontece antes”**, sendo que se **m****3** saiu em **60**, ele deve chegar em **61**, do mesmo modo que **m****4** chega em **70**.

Portanto, cada mensagem transporta o tempo de envio de acordo com o relógio do remetente, assim, quando uma mensagem chega e o relógio do receptor mostra um valor anterior ao tempo que a mensagem foi enviada, o receptor adiante o relógio para ficar uma unidade a mais no tempo de envio.

Para implementar os relógios lógicos de Lamport é importante distinguir as três camadas de software: **a rede**, **a camada de middleware**, e **a camada de aplicação**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/2/299297/18995.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/2/299297/18995.png)

Camadas de software implementadas pelos relógios lógicos.

Fonte: Figura 6.10 - Pág.149 - do Livro "Sistemas Distribuídos - Princípios e Paradigmas".

Uma aplicação prática de relógios de Lamport considera a situação em que um banco de dados foi replicado em vários sites.

Para melhorar o desempenho de consulta, um banco pode colocar cópias de um banco de contas correntes em duas cidades diferentes. Quando uma consulta acontece, é sempre repassada para a cópia mais próxima. Assim, o preço de uma resposta rápida a uma consulta é pago por custos mais elevados de atualização, porque cada operação de atualização deve ser executada em cada réplica.

Se qualquer consulta ou alteração ocorrer em qualquer das cidades onde existe uma cópia do banco, as atualizações devem ser realizadas em ambas as cópias do banco de dados, mas devido a atrasos de comunicação na rede subjacente, as atualizações podem chegar uma antes da outra.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302255/19034.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302255/19034.png)

Banco de dados replicado com inconsistência.

Fonte: Figura 6.11 - pag. 150 - do Livro Sistemas Distribuídos - Princípios e Paradigmas.

O problema enfrentado é que as operações de atualização deveriam ter acontecido ao mesmo tempo em cada cópia. Embora faça diferença se um depósito é processado antes ou depois da atualização dos juros a ordem seguida não é importante do ponto de vista da consistência. O importante é que cada uma das cópias sejam exatamente as mesmas.

Situações como essa requer um **multicast totalmente ordenado**, que garante que todas as mensagens sejam entregues na mesma ordem a cada um dos receptores, o que pode ser implementado pelos relógios lógicos de Lamport que implementam o multicast totalmente ordenado de modo distribuído.

**RELÓGIOS VETORIAIS**

Os relógios lógicos de Lamport resultam em uma situação em que todos os eventos em um Sistema Distribuído são totalmente ordenados, mas nada podemos dizer sobre a relação entre dois eventos pela mera comparação entre seus valores de tempo, o que não significa que um processo **a** tenha ocorrido antes do processo **b**.

Considerando as mensagens enviadas pelos processos P1, P2 e P3, onde o tempo marca o instante em que a mensagem foi enviada e, da mesma maneira pelo tempo em que a mensagem foi recebida, deduzimos qual foi a mensagem que chegou no instante anterior.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302266/19035.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/2/2/302266/19035.png)

Transmissão de mensagens concorrentes com utilização de relógios lógicos

Fonte: Figura 6.12 - pag. 150 - do Livro Sistemas Distribuídos - Princípios e Paradigmas

Nesse caso, a casualidade pode ser capturada por meio dos relógios vetoriais (VC), que se designado a um evento **a** tem a seguinte propriedade: se VC(a) < VC(b) para algum evento **b**, sabe-se que o evento **a** precede por casualidade o evento **b**.

Com o uso de relógios vetoriais é possível garantir que uma mensagem seja entregue somente se todas as mensagens que a precederem por casualidade também tenham sido recebidas.

Para habilitar tal esquema, considere que as mensagens são transmitidas em multicast dentro de um grupo de processos. Esse multicast ordenado por casualidade é mais fraco do que o multicast totalmente ordenado.

Assim, se duas mensagens não estiverem relacionadas uma com a outra, não importa a ordem em que elas são entregues às aplicações. Podendo ser entregues em ordem diferente e em localizações diferentes.