**Expressões booleanas obtidas de circuitos lógicos**

Todo circuito lógico executa uma função booleana e, por mais complexo que seja, é formado pela interligação das portas lógicas básicas. Assim, pode-se obter a expressão booleana que é executada por um circuito lógico qualquer.

Para exemplificar, será obtida a expressão que o circuito da Figura 1 executa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108675/a08i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108675/a08i01_arco80_100.jpg)

O exemplo da Figura 2 visa evidenciar um símbolo de negação muito utilizado e que muitas vezes é esquecido e não considerado. Ele pode ser utilizado na saída de uma porta lógica (?), como na porta NÃO E a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/1/5/8311582/a08i02-arco80-100.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/1/5/8311582/a08i02-arco80-100.png)

**Circuitos lógicos obtidos de expressões booleanas**

Será visto neste tópico que é possível desenhar um circuito lógico que executa uma função booleana qualquer, ou seja, pode-se desenhar um circuito a partir de sua expressão característica.

O método para a resolução consiste em se identificar as portas lógicas na expressão e desenhá-las com as respectivas ligações, a partir das variáveis de entrada. Deve-se sempre respeitar a hierarquia das funções da aritmética elementar, ou seja, a solução inicia-se primeiramente pelos parênteses. Para exemplificar, será obtido o circuito que executa a expressão S = (A + B).C.(B + D).

Para o primeiro parêntese, tem-se uma soma booleana A + B, logo o circuito que o executa será uma porta OU. Para o segundo, tem-se outra soma booleana B + D, logo o circuito será uma porta OU. Posteriormente, tem-se a multiplicação booleana de dois parênteses com a variável C, sendo o circuito que executa essa multiplicação uma porta E. Para finalizar, unem-se as respectivas ligações obtendo o circuito completo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108677/a08i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/6/108677/a08i03_arco80_100.jpg)