### Introdução

As redes ?classful? ou classe cheia mostrada na tabela abaixo apresenta uma grande deficiência em termos de aproveitamento dos endereços IPv4. Para se ter uma ideia vamos pensar em um link ponto-a-ponto entre dois roteadores na internet, conforme mostrado na figura abaixo.

Nessa simples topologia são necessários apenas dois endereços IPs, um para cada roteador. Se utilizarmos um endereço de rede de classe C como, por exemplo, o endereço IP 200.200.200.0 como máscara padrão igual a 255.255.255.0, teremos um total de 254 (28 ? 2) possíveis endereços, mas só precisamos de 2.

E o que faremos como os demais endereços? Resposta: serão desperdiçados! Imagine agora se tivéssemos que utilizar um endereço de classe B! O desperdício seria ainda maior, já que o endereço de classe B pode fornecer 65.534 (216 ? 2) IPs válidos, desperdiçando desse modo, 65.532 endereços. Agora, imagine um endereço de classe A ? mais de 16 milhões de endereços serão desperdiçados (Filippetti, Marco. A., 2017).

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/4/1632480/38457.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/2/4/1632480/38457.png)

Você deve estar se perguntando: Por que tais endereços serão desperdiçados? Resposta: Não podemos utilizar o mesmo endereço de rede em mais de uma rede. Pegue como exemplo o endereço de classe C 200.200.200.0. Esse endereço só pode ser utilizado para identificar a rede da topologia abaixo. Fazendo uma analogia com a telefonia, o número da rede da cidade de São Paulo é igual a 11. Como você já sabe, esse número não pode ser utilizado por outra localidade, o mesmo ocorre nas redes de computadores.

Com o objetivo de otimizar a utilização de endereços IPs classful, foi criado o conceito de sub-redes. Basicamente, o mecanismo de criar sub-redes consiste de “pegar emprestado” bits 0s do campo de HOST e transforma-los em 1s e dessa forma, podemos criar redes adicionais dentro do endereço classful com os bits que foram pegos emprestados. Além da otimização da utilização dos endereços IPs, ao criarmos sub-redes teremos mais alguns benefícios (Filippetti, Marco. A., 2017):

- **Redução do tráfego de redes:** Ao criarmos sub-redes para criar redes lógicas menores, quebrando a rede em domínios de broadcasts menores. Um domínio de broadcast consiste de um conjunto de dispositivos dentro de uma mesma rede lógica que receberão uma mensagem de broadcast como, por exemplo, o endereço da rede é 200.200.200.0 e o broadcast dessa rede é 200.200.200.255. Esse tipo de mensagem será enviado para todos os dispositivos da rede 200.200.200.0, ou seja, se essa rede tem 254 dispositivos, todos irão receber. Agora se aplicarmos o conceito de sub-redes para criar, por exemplo, 4 sub-redes (sub-redes K, L, M e N), um broadcast gerado na sub-rede K não chegará a sub-rede L e vice-e-versa. Dessa forma, haverá uma significativa redução no tráfego da rede.
- **Gerenciamento simplificado:** Seguindo o mesmo raciocínio anteriormente mostrado, caso ocorra qualquer tipo de problema na sub-rede K, a sub-rede L não será afetada, dessa forma, conseguimos isolar e identificar mais facilmente os problemas na rede.

### Sub-rede

Para compreendermos o mecanismo de criação de sub-redes, primeiramente devemos salientar a importância da máscara de sub-rede. O endereçamento classful é composto por três classes, conforme mostrado na figura abaixo. O que diferencia uma classe da outra é a sua máscara padrão.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/0/4/1630459/38438.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/0/4/1630459/38438.png)

Fonte: Cisco Systens

Para um endereço de classe A temos uma máscara padrão igual a 255.0.0.0 e em termos binários é igual a 11111111.00000000.00000000.00000000. Isso significa que o primeiro octeto da máscara corresponderá a rede do endereço (R), já que esse octeto possui todos os bits ligados. Em contrapartida, os octetos com bits iguais a 0 são destinados aos hosts (H). Portanto, a máscara de padrão funciona como um “filtro”, identificando o que é rede e o que é host. Tal processo é conhecido como AND lógico (multiplicação do endereço IP pela máscara), conforme tabela abaixo para o endereço **200.150.50.2** que possui máscara padrão igual a **255.255.255.0.** O resultado da função AND corresponderá ao endereço de rede igual **200.150.50.0**, sendo o último octeto destinado a host. Note, portanto, que, se quisermos criar sub-redes, precisamos transformar bits 0s em bits 1s.

![[Untitled 36.png|Untitled 36.png]]

Se observarmos a tabela abaixo, podemos notar que os endereços de classe A são aqueles que possuem mais bits iguais a 0, enquanto que o endereço de classe possui mais bits iguais a 1. Isso significa que conseguimos criar mais sub-redes em um endereço de classe A do que num endereço de classe C.

![[Untitled 1 26.png|Untitled 1 26.png]]

### Notação prefixal

É comum utilizamos a notação “prefixal” ou “barra” para identificarmos a máscara de sub-rede, e, consequentemente, diferenciarmos as porções de rede e de host. Por exemplo, para o endereço IP 200.200.200.56 /24, sabemos que existem 24 bits ligados que corresponde a máscara 255.255.255.0 e que também define a rede, que nesse caso é igual a 200.200.200.0. Por outro lado, já que foram usados 24 dos 32 possíveis para identificar a rede, sobrando 8 bits para hosts.

### Criando sub-redes

Como já comentado, para criarmos sub-redes devemos transformar bits iguais 0 em bits iguais a 1. Para tanto, devemos pegar bits emprestados do campo de host (da esquerda para a direita). Vamos para um exemplo prático: suponha que a sua rede é do tipo classful classe C igual a 192.168.1.0 e desejamos criar duas sub-redes.

Como já sabemos, o endereço de rede 192.168.1.0 possui máscara de padrão igual 255.255.255.0 ou /24. Nessa situação, para criarmos duas sub-rede quantos bits 0s eu preciso transformar em 1s? A resposta será dada pela fórmula abaixo:

**2****X** **≥ SR**

- Onde: **X** é número de bits 0s que deverão ser transformados em 1s do campo de host;
- SR é o número de sub-redes que se deseja criar, no nosso caso necessitamos de 2 SR.

**Solução:**

Para satisfazer a equação **2****X** **≥ 2**, o x deve ser igual 1, pois 21 ≥ 2. O resultado é que apenas o primeiro bit 0 – da esquerda para direita – deverá ser convertido em 1. A partir desse resultado, a nova máscara de sub-rede (em binário) ficará igual a:

![[Untitled 2 24.png|Untitled 2 24.png]]

Ao convertermos para decimal, resultará em uma máscara igual a 255.255.255.128, onde o 128 corresponde ao binário **1**0000000. Em notação prefixal, a nova máscara de sub-rede será /25 (24 da máscara original mais 1 bit emprestado).

Uma vez definido quantos bits devemos pegar emprestados, precisamos agora conhecer quais são as sub-redes obtidas. Para tanto, devemos fazer a combinação de todas as combinações do bit pego emprestados, ou seja, devemos ligar (1) e desligar (0). O resultado para o último octeto será:

- Primeira sub-rede: 00000000 = 0
    
    bin
    
    dec
    
- Segunda sub-rede: 10000000 = 128
    
    bin
    
    dec
    

Agora, portanto, as novas redes são 192.168.1.0 /25 e 192.168.1.128 /25

**Pergunta: Quantos hosts temos por sub-rede?**

**Resposta:** Os hosts, como já dissemos, estão associados com os bits 0s. Assim, basta saber quantos bits 0s sobraram e na sequência aplicarmos a equação abaixo:

**h = 2****Y** **- 2**

Onde:

- **H** ? é o número de hosts possíveis por sub-rede;
- **Y** ? é o número de bits iguais a 0;
- **2** ? corresponde a exclusão do endereço de sub-rede e de broadcast que não podemos utilizar para identificar um dispositivo na rede.

Para o nosso cenário, temos sete ?0s? na máscara, o que nos dá, portanto, 27 ? 2 = 126 hosts por sub-rede. Para terminarmos devemos organizar o resultado em tabela, identificando as sub-redes e a faixa de host por sub-rede, conforme tabela abaixo.

![[Untitled 3 17.png|Untitled 3 17.png]]

**Mais um exemplo**

**Crie 1000 sub-redes para o endereço 160.60.0.0 e responda as seguintes perguntas:**

a-) quantos bits do campo de host devem ser pegos emprestados?

b-) qual nova máscara?

c-) Quantos host por sub-rede serão criados?

d-) Quais são quatro primeiras sub-redes?

**Respostas:**

**a-) Resposta:** Aplicando a fórmula 2X ≥ SR, temos que satisfazer 2X ≥ 1000. Quanto vale x? Para satisfazer a equação temos que fazer 210, tal que  210 ≥ 1000, onde  210 = 1024. Portanto, devemos pegar 10 bits da esquerda para direita.

**b-) Resposta:** Sabemos que o endereço 160.60.0.0 é de classe B e, portanto, possui máscara padrão 255.255.0.0 /16. Como pegamos emprestados 10 bits, 16 da máscara padrão mais 10 pegos emprestados, termos agora 26 bits de máscara:

- Bits da máscara padrão classe B: 11111111.11111111.00000000.00000000 /16
- Bits da Nova máscara de sub-rede: 11111111.11111111.**11111111**.**11**000000 /26
- Nova máscara em decimal: 255.255..255.192 /26

**c-) Resposta:** Para descobrirmos a quantidade de hosts por sub-rede devemos aplicar a fórmula h = 2Y - 2. Onde Y é igual quantidade de bits 0s que sobraram - neste caso 6 bits. h = 26 - 2 = 64 - 2 = 62. Portanto, em cada uma das 1024 temos 62 IPs válidos.

**d-) Resposta:** para descobrirmos quais as quatro primeira sub-redes devemos fazer as combinações do último octeto na tabela abaixo:

![[Untitled 4 17.png|Untitled 4 17.png]]

Observação: de acordo com o exercício acima temos 1024 sub-redes, mas mostramos apenas as quatro primeiras. As demais deverão ser compostas a partir da variação do terceiro octeto. Abaixo, por motivos óbvios, mostramos as três primeiras e a última das 1024 sub-redes:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/0/4/1630461/38449.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/0/4/1630461/38449.png)

### VLSM

VLSM (Variable Lenght Subnet Mask - Máscara de sub-rede de tamanho variável) consiste em criar sub-redes dentro de sub-redes. Parece complicado, mas se você entendeu como se cria sub-redes, VLSM é apenas uma extensão desse conceito que permite aproveitar ainda mais os espaços de endereços IPs disponíveis (Kurose, James F e Ross, W. Keith, 2013).

A melhor forma de entender como funciona o conceito de VLSM é aplicar a um exemplo prático. Para tanto, utilizaremos a topologia abaixo que possui três redes internas A, B e C usando o endereço de rede 192.168.0.0. A rede A necessita de 100 host, a B de 60 hosts e a C de 30 hosts.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/3/5/1633514/38490.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/3/5/1633514/38490.png)

Se partimos do conceito de sub-rede tradicional deveríamos aplicar a fórmula 2^x>=SR, sendo, para o nosso exemplo SR = 3, desse modo, 22=4. O que significa que devemos pegar emprestado 2 bits do último octeto, sobrando assim 6 bits para hosts. Para descobrirmos o número de hosts por sub-rede teríamos que fazer 2Y-2 = Hosts/SR, sendo 26-2 = 64-2=62 hosts/SR. Caímos agora num impasse: precisamos criar três sub-redes com 100, 60 e 30 hosts cada, mas ao criamos as sub-redes temos apenas 62 hosts por sub-rede, o que não satisfaz a necessidade da sub-rede A, apenas a da rede B e C.

Você poderia dizer: então por que não pegamos apenas 1 bit emprestado, sobrando assim 7 bits de host? Se fizéssemos isso teríamos 27-2 = 128 -2 =126 hosts/SR. Ok!! Isso satisfazer o número de hosts para a sub-rede A, mas como deixamos apenas 1 bit para criar sub-rede, teríamos 21= 2 SR, ou seja, teríamos apenas 2 sub-redes com 126 hosts cada, mas precisamos de 3 sub-redes. Entendeu o problema? Em suma, devemos satisfazer ambas as necessidades de sub-rede e de hosts por sub-rede. A solução é usar VLSM (Filippetti, Marco. A., 2017).

### Aplicando VLSM

**Sub-rede A:** A primeira coisa a se fazer é identificarmos a sub-rede com maior necessidade de host por sub-rede. Para o nosso exemplo é a sub-rede A com 100 host. Agora basta aplicar a fórmula 2Y - 2 >= Hosts:

- 22 >=100; Portanto Y=7, pois 22= 126, e 126>=100
    
    Y
    
    7
    
- Lembrando que o valor de Y corresponde ao número de bits 0s da máscara padrão
- Máscara padrão: 11111111.11111111.11111111.00000000 = 255.255.255.0 /24
- Nova máscara (A): 11111111.11111111.11111111.10000000 = 255.255.255.128 /25

**Sub-rede B:** Para a sub-rede B devemos executar da mesma forma, só que agora para 60 hosts:

- 2^Y-2 >=60; portanto Y=6, pois 2^6-2= 62, e 62>=60. E a nova máscara fica igual a:
- Nova máscara (B): 11111111.11111111.11111111.11000000 = 255.255.255.192 /26

**Sub-rede C:** De forma análoga também para a sub-rede C, que necessita de 30 hosts:

- 2^Y-2 >=30; portanto Y=5, pois 2^5-2= 30, e 30>=30. E a nova máscara fica igual a:
- Nova máscara (C): 11111111.11111111.11111111.11100000 = 255.255.255.224 /27

Abaixo resumimos esses resultados, mostrando o endereço de sub-rede, hosts válidos e broadcast de cada uma das sub-redes. Observe que, como a máscara é variável, a faixa de endereços de hosts também será. No último octeto, a sub-rede A varia de 1 a 126, sub-rede B de 129 a 190 e a C de 193 a 222.

![[Untitled 5 15.png|Untitled 5 15.png]]

Se continuássemos aplicando a sequência de VLSM, pegando bits emprestados um a um formaríamos a tabela abaixo. Como pode ser observado, quanto mais bits pegamos emprestados menor vai ser quantidade de hosts por sub-rede disponível. O limite é /30, muito utilizado em enlaces ponto a ponto quando precisamos apenas de dois endereços IPs válidos e continuamos ainda com o endereço de sub-rede e broadcast.

![[Untitled 6 10.png|Untitled 6 10.png]]

- A RFC 3021 introduziu também a possibilidade de se utilizar também o /31 em links ponto a ponto.

### CIDR

O CIDR (Classless InterDomain Routing, roteamento sem classe) vai na contramão do que aprendemos até agora. Enquanto que os 32 bits são divididos em classe (A, B, C, D e E). Ao aplicarmos o CIDR desaparecem as classes, o que vai importar agora é o prefixo “/xx”. Com a utilização de CIDR poderemos ter um endereço, que chamávamos de classe C 192.168.1.0 com máscara padrão 255.255.255.0, tendo como máscara, agora, menor do que a padrão, por exemplo, 255.255.252.0 /22. Além disso, os roteadores da internet não precisam ter em sua tabela de roteamento todos os endereços IPs classful, basta ter apena o prefixo que agrega todas as redes (Tanenbaum, Andrew S e Wetherall, 2011).

### Criando CIDR

Imagine que você faz parte de um provedor da internet e necessita ter na sua organização 1000 endereços públicos (roteáveis na Internet). Para tanto, você faz uma solicitação ao NIC.br (órgão responsável pelo endereçamento IP no Brasil) e recebe um endereço 200.200.16.0 /22. Como sabemos, o endereço IP 200.200.16.0 pertence à classe, mas, agora, ele pertence a uma máscara menor do que a padrão, correspondente a /22 = 255.255.252.0. Isso significa que temos agora 11111111.11111111.111111**00**.00000000.

Agora temos 2 bits desligados no terceiro octeto, o que amplia a capacidade de endereços IPs. O que implica que a sua empresa não recebeu apenas uma rede classe C (/24), mas sim 4 redes (22), o dois do expoente correspondente aos 2 bits 0s que foram desligados. E quais são essas redes? Vejamos abaixo.

Para encontrarmos as redes basta fazermos as combinações dos 2 bits que foram desligados a partir do prefixo que foi passado pelo NIC.br. Dessa forma temos uma máscara /22 e queremos criar redes /24, então fica:

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/0/0/0/1600008/38516.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/0/0/0/1600008/38516.png)

Fonte:

A partir dessa tabela temos agora a possibilidade de descobrirmos os hosts válidos e broadcast de cada sub-rede. A lógica é a mesma utiliza anteriormente, o primeiro endereço é de sub-rede e o último é de broadcast, os demais são todos válidos, conforme mostrado na tabela abaixo. Mas quantos hosts válidos existem? O processo é o mesmo executado anteriormente, basta fazer 2Y-2 = H, que nos dá 254 (28-2). Temos agora 4 redes com 254 hosts válidos, totalizando 1016 endereços IPs válidos.

![[Untitled 7 9.png|Untitled 7 9.png]]

Como dito anteriormente, uma das vantagens de se criar CIDR é que os roteadores não precisam manter todos os endereços de rede em sua tabela de roteamento, basta conhecer o prefixo. Para o nosso exemplo acima, basta que o roteador publique a rede 200.200.16.0 /22 que todas as demais redes da sua instituição estão contempladas.