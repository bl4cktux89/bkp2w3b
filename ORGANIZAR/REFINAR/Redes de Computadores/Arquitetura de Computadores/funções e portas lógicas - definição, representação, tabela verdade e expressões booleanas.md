**Introdução**

Em 1854, o matemático inglês George Boole apresentou um sistema matemático de análise lógica conhecido como álgebra de Boole. Somente em 1938, um engenheiro americano utilizou as teorias da álgebra de Boole para a solução de problemas de circuitos de telefonia com relés, tendo publicado um artigo que praticamente introduziu na área tecnológica o campo da eletrônica digital.

Os sistemas digitais são formados por circuitos lógicos denominados de portas lógicas que, utilizados de forma conveniente, podem implementar todas as expressões geradas pela álgebra de Boole.

Existem três portas básicas (E, OU e NÃO) que podem ser conectadas de várias maneiras, formando sistemas que vão de simples relógios digitais aos computadores de grande porte.

**Função E ou AND**

A função E é aquela que executa a multiplicação de duas ou mais variáveis booleanas. Sua representação algébrica para duas variáveis é S = A . B, em que se lê: S = A e B.

Para compreender a função E da álgebra booleana, deve-se analisar o circuito da Figura 1, para o qual se adota as seguintes convenções: chave aberta = 0, chave fechada = 1, lâmpada apagada = 0 e lâmpada acesa = 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108643/a07i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108643/a07i01_arco80_100.jpg)

A análise da Figura 1 revela que a lâmpada somente acenderá se ambas as chaves estiverem fechadas e, seguindo a convenção, tem-se: CH A = 1, CH B = 1, que resulta em S = 1.

Pode-se, dessa forma, escrever todas as possíveis combinações de operação das chaves na chamada tabela da verdade, que é definida como um mapa em que se depositam todas as possíveis situações com seus respectivos resultados. O número de combinações possíveis é igual a 2N, em que N é o número de variáveis de entrada.

**Tabela da verdade da função E**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108644/a07i17_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108644/a07i17_arco80_100.jpg)

A porta lógica E é um circuito que executa a função E da álgebra de Boole, sendo representada, na prática, por meio do símbolo visto na Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108645/a07i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108645/a07i02_arco80_100.jpg)

**"A saída da porta E será 1 somente se todas as entradas forem 1."**

**Função OU ou OR**

A função OU é aquela que assume valor 1 quando uma ou mais variáveis de entrada forem iguais a 1, e assume 0 se, e somente se, todas as variáveis de entrada forem iguais a zero. Sua representação algébrica para duas variáveis de entrada é S = A + B, em que se lê: S = A ou B.

Para entender melhor a função OU da álgebra booleana, analise todas as situações possíveis de operação das chaves do circuito da Figura 3 . A convenção é a mesma adotada anteriormente: chave aberta = 0, chave fechada = 1, lâmpada apagada = 0 e lâmpada acesa = 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108646/a07i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108646/a07i03_arco80_100.jpg)

O circuito apresentado mostra que a lâmpada acende quando qualquer uma das chaves estiver fechada e permanece apagada se ambas estiverem abertas, ou seja, CH A = 0, CH B = 0, que resulta em S = 0.

Pode-se, dessa forma, escrever todas as possíveis combinações de operação das chaves na chamada tabela da verdade, que é definida como um mapa em que se depositam todas as possíveis situações com seus respectivos resultados. O número de combinações possíveis é igual a 2N, em que N é o número de variáveis de entrada.

**Tabela da verdade da função OU**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108647/a07i28_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108647/a07i28_arco80_100.jpg)

A figura a seguir ilustra a porta lógica que executa a função **OU** da álgebra de Boole.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108648/a07i04_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108648/a07i04_arco80_100.jpg)

**"A saída de uma porta OU será 1 se uma ou mais entradas forem 1."**

**Função NÃO ou NOT**

A função **NÃO** é aquela que inverte ou complementa o estado da variável de entrada, ou seja, se a variável estiver em 0, a saída vai para 1, e, se estiver em 1, a saída vai para 0. É representada algebricamente da seguinte forma: S = , em que se lê: A barra ou **NÃO** A.

A análise do circuito da Figura 5 ajuda a compreender melhor a função **NÃO** da álgebra booleana. Será utilizada a mesma convenção dos casos anteriores.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108649/a07i05_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108649/a07i05_arco80_100.jpg)

Observando o circuito da Figura 5, pode-se concluir que a lâmpada estará acesa somente se a chave estiver aberta (CH A = 0, S = 1); quando a chave fecha, a corrente desvia por ela e a lâmpada apaga (CH A = 1, S = 0).

O inversor é o bloco lógico que executa a função **NÃO**. Sua representação simbólica é vista na Figura 6.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108650/a07i06_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108650/a07i06_arco80_100.jpg)

**Tabela da verdade da função NÃO**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108651/a07i19_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108651/a07i19_arco80_100.jpg)

**"A saída de uma porta NÃO assume o nível lógico 1 somente quando sua entrada é 0 e vice-versa."**

**Função NÃO E, NE ou NAND**

Essa função é uma composição das funções **E** e **NÃO**, ou seja, é a função **E** invertida. Sua representação algébrica é S =  , em que o traço indica que ocorrerá uma inversão do produto booleano A . B . O circuito da Figura 7 esclarece o comportamento da função **NE**. Observa-se que a lâmpada apaga somente quando ambas as chaves são fechadas, ou seja, CH A = 1, CH B = 1, que implica em S = 0.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108653/a07i07_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108653/a07i07_arco80_100.jpg)

A Figura 8 ilustra o circuito que executa a função **NE** da álgebra de Boole.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108652/a07i08_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108652/a07i08_arco80_100.jpg)

**Tabela da verdade da função NE**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108654/a07i20_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108654/a07i20_arco80_100.jpg)

**"Essa função é o inverso da função E, ou seja, a saída será 0 somente quando todas as entradas forem 1."**

**Função NÃO OU, NOU ou NOR**

Analogamente à função **NE**, a função **NOU** é a composição da função **OU** com a função **NÃO**, ou seja, é a função **OU** invertida. É representada algebricamente da seguinte forma: S =  , em que o traço indica que ocorrerá uma inversão da soma booleana A + B.

Para melhor compreender a função **NOU** da álgebra de Boole, pode-se analisar o circuito da figura a seguir, em que se observa que a lâmpada fica acesa somente quando as duas chaves estão abertas. Assim, CH A = 0, CHB = 0, que resulta em S = 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108655/a07i09_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108655/a07i09_arco80_100.jpg)

A Figura 10 ilustra o circuito que executa a função **NOU** da álgebra de Boole.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108656/a07i27_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108656/a07i27_arco80_100.jpg)

**Tabela da verdade da função NOU**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108657/a07i21_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108657/a07i21_arco80_100.jpg)

**"Essa função é o inverso da função OU, ou seja, a saída será 0 se uma ou mais entradas forem 1."**

**Função OU EXCLUSIVO ou XOR**

Essa função, como o próprio nome diz, apresenta saída com valor 1 quando as variáveis de entrada forem diferentes entre si. A notação algébrica que representa a função **OU** **EXCLUSIVO** é S = , em que se lê: A **OU EXCLUSIVO** B.

Para entender melhor a função **OU EXCLUSIVO**, analise o circuito da Figura 11. Na condição em que as chaves CH A e CH B ficam abertas (e ficam fechadas), não há caminho para a corrente circular e a lâmpada não acende. A lâmpada continuaapagada quando as chaves CH A e CH B estão fechadas, pois CH  e CH  estão abertas, interrompendo o fluxo de corrente.

Portanto,pode-se concluir que esse bloco só terá nível 1 na saída (lâmpada acesa) quando suas entradasforem diferentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108658/a07i10_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108658/a07i10_arco80_100.jpg)

A Figura 12 simplesmente simboliza o circuito lógico que executa a função **OU EXCLUSIVO**. Na verdade, o circuito que efetivamente realiza a função demonstrada na tabela da verdade está ilustrado na Figura 11.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108659/a07i11_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108659/a07i11_arco80_100.jpg)

A Figura 13 ilustra o símbolo que representa, na prática, a função **XOR**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108660/a07i12_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108660/a07i12_arco80_100.jpg)

**Tabela da verdade da função XOR**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108661/a07i18_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108661/a07i18_arco80_100.jpg)

**Observação importante: esse bloco lógico OU EXCLUSIVO é definido apenas para duas variáveis de entrada.**

**Função COINCIDÊNCIA ou NÃO OU EXCLUSIVO ou XNOR**

Essa função, como seu próprio nome diz, apresenta saída com valor 1 quando houver uma coincidência nos valores das variáveis de entrada. A notação algébrica que representa a função Coincidência é S = A  B, em que se lê: A Coincidência B.

O circuito da Figura 14 ajuda a compreender a operação da função Coincidência. Quando as chaves CH A e CH B estão abertas (CH  e CH  estão fechadas) circula corrente pela lâmpada e ela estará acesa. Quando CH A = 1 e CH B = 0 (CH B=1), não circula corrente pela lâmpada, o que implica em lâmpada apagada.

Na situação inversa, CH A = 0 (CH = 1) e CH B = 1, ocorre a mesma coisa e a lâmpada não acenderá. Com as duas chaves fechadas, ou seja, CH A = CH B = 1 (CH = CH = 0) circulará corrente pela lâmpada e esta estará acesa.

Portanto, pode-se afirmar que a porta Coincidência terá 1 em sua saída (lâmpada acesa) quando as entradas forem idênticas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108662/a07i13_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108662/a07i13_arco80_100.jpg)

A Figura 15 simplesmente representa simbolicamente o circuito lógico que executa a função Coincidência. Na verdade, o circuito capaz de realizar essa função é ilustrado na Figura 14.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108665/a07i14_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108665/a07i14_arco80_100.jpg)

A Figura 16 ilustra o símbolo que representa, na prática, a função **XNOR**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108663/a07i15_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108663/a07i15_arco80_100.jpg)

**Tabela da verdade da função XNOR**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108664/a07i23_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108664/a07i23_arco80_100.jpg)

**Observação importante: Assim como ocorre com o bloco lógico OU EXCLUSIVO, o circuito COINCIDÊNCIA é definido apenas para duas variáveis de entrada.**

Portas lógicas:

- Logic circuit. [**www.logiccircuit.org/**](http://www.logiccircuit.org/)
- Redstone circuits. [**www.minecraftwiki.net/**](http://www.minecraftwiki.net/wiki/Redstone_circuits)
- Simulador de lógica digital. [**bradwarestudios.com/**](http://bradwarestudios.com/downloads/fun/Digital_Logic_Simulator)
- Simulador de porta lógica em Adobe Flex. [**joshblog.net/**](http://joshblog.net/projects/logic-gate-simulator/Logicly.html)
- Simulador de portas lógicas. [**www.neuroproductions.be/**](http://www.neuroproductions.be/logic-lab/index.php?id=52)
- Usando portas lógicas [**knol.google.com/**](http://knol.google.com/k/max-iskram/digital-electronic-design-for-beginners/1f4zs8p9zgq0e/23)