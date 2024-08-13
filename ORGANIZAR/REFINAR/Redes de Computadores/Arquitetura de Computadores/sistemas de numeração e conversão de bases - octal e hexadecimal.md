**Sistema octal**

O sistema de numeração de base 8 que utiliza os caracteres de 0 a 7 do sistema de numeração decimal, na respectiva ordem, é chamado de sistema octal. Esse sistema era mais utilizado antigamente, pois é uma simplificação do sistema binário: 3 dígitos binários eram substituídos por 1 dígito no sistema octal, porque o valor máximo de um número de 3 dígitos binários é 111, ou seja, 7, que é o número máximo de caracteres diferentes utilizados pelo sistema octal (base 8). Atualmente, o sistema octal entrou em desuso pela utilização cada vez maior da informática e de circuitos eletrônicos digitais, que empregam somente números binários. Em substituição ao sistema octal, é utilizado o sistema hexadecimal.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108571/a03i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108571/a03i01_arco80_100.jpg)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108572/a03i01b_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108572/a03i01b_arco80_100.jpg)

**Sistema hexadecimal de numeração**

O sistema hexadecimal de numeração pode representar quatro bits do sistema binário por um dígito (o número máximo obtido com quatro dígitos binários é 1610, que é a base do sistema hexadecimal) utilizando os dígitos de 0 a 9 do sistema decimal e representando os números de 10 a 15 pelos caracteres A, B, C, D, E, F. A contagem no sistema hexadecimal se processa da seguinte forma:

0,1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 1A, 1B...

Exemplo de números hexadecimais:

A16 = 1010

99F16 = 246310

BBC16 = 300410

**Conversão do sistema hexadecimal para o sistema decimal**

Uma representação posicional no sistema hexadecimal pode ser desenvolvida numa forma polinomial que envolve um somatório de potências de 16. Executa-se um processo semelhante à conversão dos números binários para decimal.

Para conhecer um pouco mais sobre essa representação, veja o infográfico abaixo. Este infográfico faz parte da sequência desta aula e, portanto, é essencial para a aprendizagem.

[![](https://img.uninove.br/static/0/0/0/0/0/0/7/3/2/8/9/7328902/484489.png)](https://img.uninove.br/static/0/0/0/0/0/0/7/3/2/8/9/7328902/484489.png)

**Exemplo 1**: Conversão do número A0116 hexadecimal para decimal.

1. O primeiro dígito da direita para a esquerda do número hexadecimal multiplica a potência de 16, o segundo dígito da direita para a esquerda multiplica 16, o terceiro dígito à direita multiplica 16, e assim por diante. Caso exista um dígito maior que 9, deve-se convertê-lo para decimal e multiplicar normalmente:
    
    0
    
    1
    
    2
    

1 x 160 = 1 x 1 = 1

0 x 161 = 0 x 16 = 0

A x 162 = A x 256 = 10 x 256 = 2560

1. A soma dessas multiplicações resulta no número decimal:

1 + 0 + 2560 = 2561

Assim: A0116 = 256110

**Exemplo 2**:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108566/a03i04_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108566/a03i04_arco80_100.jpg)

= B x 16

3

+ F x 16

2

+ 2 x 16

1

+ 0 x 16

0

BF2016 = 11 x 4096 + 15 x 256 + 2 x 16 + 0 x 1

BF2016 = 45056 + 3840 + 32 + 0

BF2016 = 4892810

**Exemplo 3**:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108567/a03i05_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108567/a03i05_arco80_100.jpg)

= 6 x 16

4

+ 0 x 16

3

+ 0 x 16

2

+ C x 16

1

+ D x 16

0

600CD16 = 6 x 65536 + 0 x 4096 + 0 x 256 + 12 x 16 + 13 x 1

600CD16 = 39342110

**Conversão do sistema decimal para o sistema hexadecimal**

Utiliza-se o método das divisões sucessivas: divide-se sucessivamente o número decimal por 16 até resultar em um número menor que 16, e os restos dessas divisões com o resultado da última divisão formarão o número hexadecimal.

**Exemplo 1**: Conversão do número decimal 4096 para hexadecimal.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108569/a03i02_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108569/a03i02_arco80_100.jpg)

409610 = 100016

**Exemplo 2**: Conversão do número 3748 decimal para hexadecimal.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108568/a03i03_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/5/108568/a03i03_arco80_100.jpg)

1410 = E16

1010 = A16

374810 = EA416

Para conhecer um pouco mais sobre essa conversão, veja o infográfico abaixo. Este infográfico faz parte da sequência desta aula e, portanto, é essencial para a aprendizagem.

[![](https://img.uninove.br/static/0/0/0/0/0/0/7/3/2/8/2/7328293/484262.png)](https://img.uninove.br/static/0/0/0/0/0/0/7/3/2/8/2/7328293/484262.png)