[![](https://ampli-images.s3.amazonaws.com/production/441ebbed-9f24-4dc7-8193-c5ee3ef8267e/original)](https://ampli-images.s3.amazonaws.com/production/441ebbed-9f24-4dc7-8193-c5ee3ef8267e/original)

Uma máscara de rede é uma técnica utilizada para definir a porção do número IP que está designada para identificar a rede e a porção utilizada para identificar o host. A Figura 2.7, apresentada a seguir, demonstra que o endereço IPv4 da rede é 192.168.0.12, e sua máscara da rede é 255.255.255.0, de forma que os três primeiros octetos (255.255.255) representam a rede, e o quarto octeto (0) representa o host. Podemos perceber também que há um endereço que identifica o Gateway Padrão (192.168.0.1), que representa o caminho de saída das mensagens da sub-rede. Este endereço é normalmente identificado do IP de um dispositivo concentrador/controlador de rede, representado por um _switch_ ou roteador.

[![](https://ampli-images.s3.amazonaws.com/production/3b112795-f37b-4d71-9652-011a846c9740/original)](https://ampli-images.s3.amazonaws.com/production/3b112795-f37b-4d71-9652-011a846c9740/original)

Exemplo de configuração de número IP, máscara de sub-rede e gateway. Fonte: captura de tela do prompt de comando do sistema operacional elaborada pelo autor.

O quadro abaixo busca complementar as informações anteriores com a distribuição dos octetos do endereço IP em conformidade com as classes de rede.

[![](https://ampli-images.s3.amazonaws.com/production/bb4249fe-9dda-445a-8f50-1ac183b2dccb/original)](https://ampli-images.s3.amazonaws.com/production/bb4249fe-9dda-445a-8f50-1ac183b2dccb/original)

Máscaras de sub-rede. Fonte: elaborado pelo autor.

Observamos que o endereço IP permite que uma rede seja dividida em redes diferentes. A composição de um endereço IP define, conforme vimos, que um host tem sua identidade única e pertence a uma rede. Considerando que uma rede pode ser segmentada, ou seja, dividida em sub-redes, o endereçamento também precisa ser utilizado para formalizar esta identificação. Imagine que uma empresa precise isolar os departamentos X, Y e Z dentro de uma rede interna. Isso é possível por meio da manipulação da máscara de redes.

Conforme apresentam Kurose e Ross (2013), para determinar as sub-redes, cada interface deve ser destacada de seu hospedeiro ou roteador, criando ilhas de redes isoladas com interfaces fechando as terminações das redes isoladas. As sub-redes são o termo técnico destas ilhas isoladas. Além da atribuição de mais endereços dentro das classes A, B e C, que permitem a configuração de sub-redes, outro método também foi criado com o objetivo de melhor aproveitar os endereços IPs dentro das redes, chamado pelos autores de CIDR (_Classless Inter-Domain Routing_). Esta é uma estratégia de atribuição de endereços conhecida como roteamento interdomínio sem classes, a qual generaliza a noção de endereçamento de sub-rede.

Da mesma forma que ocorre com o endereçamento de sub-rede utilizando as classes mencionadas, no CIDR o IP de 32 bits é dividido em duas partes, conservando a notação decimal com quatro grupos de números (octetos) separados por ponto, mas adicionado de um novo número separado pela barra. Como exemplo, um endereço na notação CIDR segue o seguinte formato: **x.x.x.x/y**, onde o **y** identifica o número de bits da primeira parte do endereço que identifica a rede. O restante dos bits identificará os _hosts_.

Em uma rede classe C, por exemplo, temos os três primeiros octetos (formados cada um por 8 bits) definindo a rede, o que daria uma máscara em notação CIDR da seguinte forma: 192.168.15.85/24, onde 24 representa a soma dos bits dos três octetos que identificam a rede. Em uma rede classe B, temos os dois primeiros octetos definindo a rede, o que daria uma máscara de notação CIDR: **172.16.189,85/16**, onde 16 representa a soma dos bits dos dois octetos que identificam a rede. Estas máscaras fazem com que muitos endereços IP dentro das classes não sejam utilizados, o que representa um desperdício de endereços.

O CIDR permite que a notação que define a máscara de rede (/24 ou /16, por exemplo) tenha números diferentes, utilizando um volume maior de bits nos octetos que definem a rede, o que divide o número de hosts para sub-redes e, desta forma, aproveita-se o número de endereços para _hosts_ dentro de uma rede segmentada em sub-redes.

### **Divisão de uma rede em sub-redes**

Uma rede A, B o C pode ser dividida em sub-redes para que uma rede com um número determinado de dispositivos possa ser configurada de forma otimizada. De acordo com Tanenbaum (2011), a segmentação de uma rede, ou divisão em sub-redes, oferece alguns benefícios, como:

1. Reduzir o tráfego da rede, considerando que os hosts de uma sub-rede fazem domínio de _broadcast_.
2. Simplificar o gerenciamento da rede com identificação de falhas através do mapeamento de endereços.
3. Controlar os recursos da rede através de sua segmentação.

Vamos tomar como exemplo uma rede classe C definida como 192.168.123.x. Conforme exemplo apresentado pela Microsoft (2020), se houver uma rede com 150 _hosts_ em uma única rede, podemos apenas atribuir os endereços dentro do intervalo de rede definição (classe C com intervalo de endereços de 192.168.123.1 até 192.168.123.152). Porém, ser tivermos redes separadas fisicamente, divididas em três redes de 50 hosts cada, pode-se utilizar a classe C e um endereço 192.168.123.0, utilizando os endereços úteis de 192.168.123.1 até 192.168.123.254 que comportam os 150 _hosts_, mas precisaremos dividi-la em sub-redes.

Lembre-se das regras de endereçamento que excluem os endereços 192.168.123.0 (primeiro endereço da sub-rede) e 192.168.123.255 (último endereço da sub-rede). Este é o exemplo de endereços que precisam ser desconsiderados para atribuição aos hosts no exemplo da rede 192.168.123.0, pois, como temos três sub-redes, teremos três endereços de rede e três endereços de broadcast.

Para dividir uma rede em quatro sub-redes, por exemplo, utiliza-se uma máscara de sub-rede, que torna o endereço de rede maior (utilizando mais bits emprestados dos bits do endereço da rede) e o número de endereços de hosts menor (pois empresta bits do octeto do host), ou seja, utiliza-se de alguns dos bits utilizados para identificar os hosts para identificar parte da rede. Por exemplo, a máscara de sub-rede 255.255.255.192 (11111111.11111111.11111111.11000000 binário) oferece quatro redes de 62 hosts cada. Os dois primeiros bits do último octeto se tornam endereços de rede e possibilitam que se tenha redes adicionais. Usando uma máscara de rede 255.255.255.192, a rede 192.168.123.0 dispõe de quatro redes, sendo a primeira sub-rede 192.168.123.0, a segunda 192.168.123.64, a terceira 192.168.126.128 e a quarta 192.168.123.192, com 62 hosts endereçáveis em cada uma delas.

Para calcular as sub-redes através de um exemplo adaptado de Nunes (2017) e poder melhor entender a divisão da rede apresentada anteriormente, seguiremos estes passos:

**Passo 1**: fazer a conversão da máscara de rede de 255.255.255.0 para binário, que resulta em 1111111.11111111.11111111.00000000.

______

**📝****Exemplificando**

Na conversão de número binário para decimal, devemos somar os valores numéricos representados pela posição do número binário 1 na posição em seu octeto. Veja a tabela a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/e348e9ea-54ae-40ac-a8bb-a66f2245add2/original)](https://ampli-images.s3.amazonaws.com/production/e348e9ea-54ae-40ac-a8bb-a66f2245add2/original)

Na conversão de números decimais para binário, devemos dividir o número decimal por 2 até que o resultado seja 0 ou 1. O número final e os restos da divisão são posicionados no octeto do byte de forma invertida.

Exemplo de conversão do número 73 decimal para binário:

[![](https://ampli-images.s3.amazonaws.com/production/28a8d602-200c-40d2-8058-c9495aaceb06/original)](https://ampli-images.s3.amazonaws.com/production/28a8d602-200c-40d2-8058-c9495aaceb06/original)

O número 73 em decimal = 1001 0010 em binário (o oitavo bit é naturalmente 0).

______

**Passo 2**: fazer o cálculo da quantidade de hosts para cada uma das sub-redes, considerando o número (n) de bits necessários para:

- A rede: 2n = 22 = 4, ou seja, para fazer quatro sub-redes será necessário alocar dois bits da máscara de rede. Note que podemos ter dois ou quatro (ou mais, desde que sejam números pares), assim como precisamos dividir nossa rede em três sub-redes, utilizaremos o cálculo com quatro sub-redes.
- _Hosts_ de sub-rede: 2n = 26 = 64, com possibilidade de até 64 _hosts_ em cada sub-rede. Considere que, para converter os octetos, são utilizados: 1, 2, 4, 8, 16, 32, 64 e 128. Como foram utilizados dois bits para a definição das redes, sobraram outros seis bits para os _hosts_.

**Passo 3:** elaborar a tabela ou o racional com os endereços da sub-rede. Novamente, lembre-se das regras de endereçamento, que excluem todos os endereços de rede e de _broadcast_, por exemplo, os endereços 192.168.123.0 e 192.168.123.255.

- Sub-rede 1: 192.168.123.0: _hosts_ que variam de 192.168.123.1 até 192.168.123.62, e _broadcast_ 192.168.123.63.
- Sub-rede 2: 192.168.123.64: _hosts_ que variam de 192.168.123.65 até 192.168.123.126, e _broadcast_ 192.168.123.127.
- Sub-rede 3: 192.168.123.128: _hosts_ que variam de 192.168.123.129 até 192.168.123.190, e _broadcast_ 192.168.123.191.
- Sub-rede 4: 192.168.123.192: _hosts_ que variam de 192.168.123.193 até 192.168.123.254, e _broadcast_ 192.168.123.255.

**Passo 4**: identificar a máscara da rede. Considere que a máscara de rede 11111111.11111111.11111111.00000000 binário (255.255.255.0 decimal) utilizou dois bits do octeto do host para adicionar nos octetos da rede (sub-rede), O primeiro bit da máscara representa o número decimal 128, e o segundo bit, 64; desta forma, temos 128 + 64 = 192, ficando a máscara da rede como 11111111.11111111.1111111.11000000 binário (255.255.255.192 decimal). Em notação CIDR, temos a máscara binária 11111111.11111111.11111111.11000000 com 26 bits definindo a máscara da rede, o que resulta em uma notação decimal de um endereço IP como 192.168.123.1/26, onde 192.168.123.1 é um dos endereços da rede e /26 identifica a sub-rede, formada pela somatória dos bits que identificam a rede. A notação para a nova máscara de sub-rede é: 255.255.255.192, ou /26.

______

**🔁Assimile**

Um número binário pode tomar os valores de 0 e 1, ou seja, dois valores numéricos. Um número binário de dois dígitos pode tomar as posições 00, 01, 10, 11, ou seja, quatro valores numéricos. Esta sequência se dará exponencialmente até 256 valores numéricos em um octeto, ou seja, em um número binário de oito dígitos, como um octeto de um endereço IP. Como pode ser visto na representação a seguir, dois bits do octeto que forma o endereço de host de um endereço de classe C foram adicionados aos outros três bits que identificam a rede para a formatação do número a ser utilizado para representar a sub-rede, no quarto octeto da máscara. Perceba que, quando temos o bit 0, o valor decimal representado no octeto é desconsiderado na soma da máscara da rede; quando temos o bit 1, somamos os valores decimais para a composição da máscara da sub-rede.

[![](https://ampli-images.s3.amazonaws.com/production/8d9e02bc-92d0-491f-8158-927e75adb8a8/original)](https://ampli-images.s3.amazonaws.com/production/8d9e02bc-92d0-491f-8158-927e75adb8a8/original)

Os endereços IPs e as máscaras (e sub-rede, se desejado) precisam ser informados em cada _host_ da rede. Segue, na Figura 2.8, um exemplo de configuração de endereço IP e máscara de rede em um sistema Windows.

[![](https://ampli-images.s3.amazonaws.com/production/8aab1393-cf4a-4520-8d72-b301452b5b4e/original)](https://ampli-images.s3.amazonaws.com/production/8aab1393-cf4a-4520-8d72-b301452b5b4e/original)

Exemplo de configuração de endereço IP. Fonte: captura de tela elaborada pelo autor.