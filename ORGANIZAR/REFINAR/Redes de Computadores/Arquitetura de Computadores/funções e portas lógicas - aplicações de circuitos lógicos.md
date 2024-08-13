**Introdução**

O projeto de um circuito lógico começa na racionalização do problema, por meio das combinações possíveis, para o entendimento do comportamento de um evento. Feito isso, elabora-se a tabela da verdade que expressa esse comportamento. Da tabela da verdade é possível extrair a expressão algébrica booleana que determina o circuito lógico adequado para comandar o evento desejado (TANENBAUM, 2007).

**Aplicações de circuitos lógicos**

**Problema 1:**

Uma pessoa deseja projetar um sistema que acione um alarme contra roubo quando alguém forçar a porta de entrada **ou** janela de sua casa.

Por análise, pode-se determinar que a porta e a janela são responsáveis pela sinalização de **entrada** (A = porta e B = janela), e o alarme é acionado pelo sinal da **saída** quando alguém tenta entrar na casa. As possíveis situações em que as saídas são perturbadas (acionadas), e consequentemente a saída que se deseja, estão descritas na tabela 1, que se segue:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108734/a10i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108734/a10i01_arco80_100.jpg)

Diz-se, então, que a tabela 1 é a **tabela da verdade** para o problema proposto. Como apenas os casos em que a saída é igual a 1 interessam para a solução do problema, temos que os termos dados por cada saída serão expressos da forma como mostra a tabela 2:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108736/a10i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108736/a10i02_arco80_100.jpg)

O termo S =  **•** B significa que A deve ser zero () e B deve ser 1 (**B**), ao mesmo tempo (.), para que o alarme seja acionado (S = 1).

O termo S = A **•**  significa que A deve ser 1 (**A**) e B deve ser 0 (), ao mesmo tempo (.), para que o alarme seja acionado (S = 1).

O termo S = A **•** B significa que A deve ser 1 (**A**) e B deve ser 1 (**B**), ao mesmo tempo (.), para que o alarme seja acionado (S = 1).

Na tabela 2, na situação em que ocorre uma das possibilidades em que o alarme é acionado (S = 1), o primeiro termo (A = 0 e B = 1) indica que a porta não foi forçada, mas a janela sim. O segundo termo (A = 1 e B = 0) mostra que dessa vez a porta foi aberta e a janela não. O terceiro termo (A = 1 e B = 1) acusa que as duas foram forçadas por alguém.

Para o acionamento do alarme, portanto, serve qualquer uma das alternativas apontadas. Representa-se, então, essa possibilidade com o sinal + entre os termos.

A expressão algébrica booleana que ilustra a solução do problema é dada pela soma dos termos:

S =  • B + A •  + A • B

Para a equação apresentada, cada termo pode ser expresso por uma porta:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108733/a10i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108733/a10i03_arco80_100.jpg)

Como mostra a Figura 1, o sinal da entrada **A** foi combinado com o sinal da entrada **B** numa porta **AND**. O sinal (.) indica o tipo de porta usado para essa combinação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108735/a10i04_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108735/a10i04_arco80_100.jpg)

Nesse exemplo da Figura 2, o sinal da entrada **A** foi invertido numa porta **NOT** antes de ser combinado com **B** numa porta **AND**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108737/a10i05_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108737/a10i05_arco80_100.jpg)

Dessa vez, na Figura 3, o sinal da entrada **B** foi invertido por uma porta **NOT** para depois ser combinado com **A** numa porta **AND**.

A somatória dos termos configura a composição das portas, conforme mostrado no esquema a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108738/a10i06_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108738/a10i06_arco80_100.jpg)

Os três termos estão representados pelos seus respectivos conjuntos de portas, dos quais as devidas saídas são ligadas numa porta **OR**, determinando assim a combinação dos três termos, como mostra a equação 1 com o sinal (+).

Para que se possa verificar se o circuito obtido condiz com a expressão proposta pelo problema, procede-se à análise como segue:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108739/a10i07_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108739/a10i07_arco80_100.jpg)

Na saí­da do circuito, ou seja, na saí­da da porta **OR**, o resultado será:

S =  • B + A •  + A • B