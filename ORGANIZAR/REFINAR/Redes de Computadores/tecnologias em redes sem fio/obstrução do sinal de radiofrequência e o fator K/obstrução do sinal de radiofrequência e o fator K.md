### Objetivo:

Nesta aula iremos estudar as barreiras que os sinais de rádio podem sofrem, desde sua irradiação pela antena até sua chegada no receptor e, de como estas obstruções podem danificar a informação digital. Vamos também aprender como evitar ou prevenir estas obstruções em um projeto de sistemas wireless.

### 1. Efeito dos Obstáculos

Um feixe de ondas sofre diversos comportamentos, assim como uma onda de luz sofre ao incidir em um obstáculo. A onda pode refletir, espalhar, refratar, difratar ou ser absorvida através da superfície ou do espaço por onde irá trafegar.

O meio de transmissão de rádio enlace é composto pelo conjunto da superfície terrestre e atmosfera. O comportamento do sinal transmitido depende das condições do relevo do terreno em que o sinal é propagado, bem como das condições atmosféricas na região.

A influência da superfície terrestre é percebida de várias formas, entre elas: obstrução, difração e reflexão. Já no espaço livre, as ondas se propagam em “linha reta”, sem a influência de fenômenos como refração e reflexão.

Conforme retratado na figura 1 as consequências da reflexão das ondas transmitidas sobre a superfície terrestre. Tal fenômeno causa um atraso da onda transmitida e refletida no terreno em relação à onda transmitida diretamente, o que causa interferência no sinal.

Para uma transmissão de rádio enlace, existe sempre um sinal que trafega de forma direta a outra antena e mais um outro sinal que chega à antena refletida pela superfície do terreno.

[![](https://img.uninove.br/static/0/0/0/0/0/0/3/1/2/8/8/3128845/16695.png)](https://img.uninove.br/static/0/0/0/0/0/0/3/1/2/8/8/3128845/16695.png)

Figura 1 - Efeito da reflexão de um rádio enlace

### 2. Reflexão do Sinal

A reflexão ocorre quando uma onda eletromagnética atinge um obstáculo que tem dimensões muito maiores do que o comprimento de onda do sinal, ocorrendo na superfície da terra, prédios, muros e outros objetos.

Nas superfícies relativamente regulares, como terrenos sem acidentes de relevo, mares e lagos, o sinal refletido ao se compor com o sinal direto entre as antenas, dependendo da defasagem entre estes, poderá causar grande atenuação no campo resultante conforme ilustrado na figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293076/16696.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/0/293076/16696.png)

Figura 2 - Variações das fases do sinal na reflexão

Fonte: Santos Junior - 2005 - p.III - 43

Conforme relatado, “Após a reflexão, o campo elétrico também varia de fase, ou seja, sobre a superfície refletora há uma variação de fase entre o campo incidente (o sinal primário) e o refletido. Essa variação de fase decorre na modificação da direção do campo refletido em relação ao incidente ocorrendo uma rotação de ângulo Ñ² no espaço.” (SANTOS JUNIOR 2005, p. III 43)

Quando estes dois sinais chegam à antena receptora se encontram defasados, podendo ocasionar atenuação ao sinal e dependendo do ângulo do sinal refletido de 180º há possibilidade de ocorrer o cancelamento total do sinal e a perda de comunicação.

### 3. Desvanecimento ou Fading

Segundo Felice (2005), “uma onda eletromagnética, ao atravessar o meio de propagação, sofre alterações de amplitude e de percurso”. O desvanecimento representa alterações percebidas por atenuações, reforços e distorções no espectro do sinal. O desvanecimento pode ser de dois tipos:

- Plano (ou não seletivo)
- Seletivo

O primeiro ocorre devido a efeitos de propagação como a estratificação da atmosfera (cintilação) e é menos severo que o desvanecimento seletivo, embora este possa ser corrigido pela aplicação de algum tipo de diversidade.

Ainda segundo Felice (2005), “a ocorrência do desvanecimento seletivo se dá devido à existência de um sinal interferente ou o chamado eco”. O receptor não distingue entre o sinal desejado e o indesejado e, então, acontece adição dos sinais, que podem apresentar relações aleatórias de fase e amplitude.

A somatória tem uma larga faixa de valores, que variam com o tempo, principalmente as causadas por refrações atmosféricas. Este desvanecimento seletivo, que é a condição mais severa em enlaces de rádio, é conhecido por múltiplos percursos e é caracterizado por desvanecimentos rápidos e lentos.

Outros tipos de desvanecimentos são ocasionados por múltiplos percursos em atmosfera estável e turbulenta, reflexão pela camada troposfera ou em superfícies, por refração anormal, por _**blackout**_ e por obstrução.

### 4. Espalhamento

O espalhamento ocorre “quando o meio no qual a onda viaja possui obstáculos com dimensões muito menores se comparadas com o comprimento de onda do sinal e o número de obstáculos por unidade de volume é grande. Neste caso, a reflexão é difusa e a onda é refletida em várias direções.” (SANTOS JUNIOR 2005, p. III 46)

### 5. Distorção por Efeito da Chuva

Outra forma de distorção do sinal ocorre por efeito da chuva, sendo este causado pela absorção e espalhamento do feixe de onda pela água. Em situações de chuva mais intensa pode chegar à paralisar por completo um sistema de rádio enlace.

### 6. Refração

A refração de uma onda ocorre quando ela passa de um meio para outro, exceto nos casos em que a direção do raio formar um ângulo reto com a superfície. Este fenômeno é considerado no cálculo de rádio enlace através de um parâmetro chamado de Fator K, que veremos na sequência.

### 7. Considerações sobre Fator K

A refração atmosférica, que se observa nas ondas de rádio ocorre devido a variações no índice de refração do ar com a altura. Como consequência, esta muda de acordo com as condições climáticas, devido as alterações de temperatura, pressão e umidade.

Na atmosfera onde as ondas eletromagnéticas se propagam, classifica-se como sendo padrão onde o índice de refração decresce com a altitude causando assim o encurvamento para baixo das ondas de rádio. Para analisar a propagação das ondas de rádio na atmosfera, utiliza-se um artifício, que é considerar o feixe sem curvatura, ou seja, uma linha reta e, para compensar isso, aumenta-se o raio da Terra, tendo assim um modelo equivalente. (PORTAS 2008)

### 8. Equivalência do Raio da Terra

Devido à refração as ondas de rádio não se propagam em linha reta, sendo assim a trajetória das ondas dependente do gradiente de refratividade em cada ponto ao longo do caminho percorrido pela onda eletromagnética no enlace.

Se for considerado um valor médio do gradiente de refratividade ao longo do caminho, pode-se assumir que o raio segue uma trajetória curva. Considera-se então o raio propagando em um arco cujo raio é “ r ”, sendo inversamente proporcional ao valor médio do gradiente do índice de refração do caminho percorrido.

A superfície da terra pode ser aproximada por um arco com um raio médio de (6,37*106) de quilômetros. Dessa forma, a liberação do feixe de ondas emitido pelo rádio e que se propaga sobre a superfície da terra depende da distância relativa entre duas curvas. Uma análise da liberação do feixe é facilitada se uma das curvas é mapeada como uma linha reta e a outra corrigida com uma curvatura extra como compensação. Na prática, o raio emitido pelo transmissor na direção do receptor é mapeado em uma linha reta relativa a um raio efetivo da terra, ajustado pelo gradiente de refratividade. (PORTAS 2008)

O raio efetivo da terra (ae) e o raio real (a) multiplicado por um fator “K” que é dependente do gradiente de refratividade.

  **ae = K . a**

A tabela 1 mostra a relação entre K e G para algumas situações peculiares. O valor K = 1 corresponderia a uma situação de real propagação em espaço livre, com os raios propagando-se de fato em linha reta. O valor K = 4/3 corresponde à condição padrão da atmosfera. O valor infinito de K representa a propagação sobre terra plana enquanto que valores negativos de K estão associados a um encurvamento dos raios na direção da superfície da terra. (POEYS 2004)

Tabela 1 – Comparativo entre Fator K e Gradiente

Fonte: (POEYS 2004)

![[Untitled 71.png|Untitled 71.png]]

Em resumo, o fator K é uma constante que representa o decréscimo do índice de refração da atmosfera do Planeta Terra devido à altitude. De forma prática, devem-se calcular os enlaces e principalmente as obstruções entre as antenas, considerando o fator K para duas situações:

- Para obter 70% livre de desobstrução da primeira zona de Fresnel, consideram-se o fator K igual a 0,7 que representa a situação mais desfavorável e conseqüentemente as antenas em menor altura para liberação de 70% da 1ª zona de Fresnel. Esta situação de cálculo também é conhecida como K mínimo.
- Para obter 100% livre de desobstrução da primeira zona de Fresnel considera-se o fato K igual a 1, o que representa a situação ideal ou mais favorável. Nesta situação tem-se a liberação total da elipsóide da 1ª zona de Fresnel o que representa antenas em maior altura e consequentemente maiores custos na sua produção. (SANTOS JUNIOR 2005)

Mas o que é 1ª zona de Fresnel?

Esta questão e muitas outras serão respondidas no estudo do próxima assunto, onde aprenderemos a calcular a 1ª zona de Fresnel e a produzir projetos precisos de rádio enlace com a tecnologia wireless.

### Revisão:

- A obstrução do sinal de radiofrequência são perturbações físicas que deformam os sinais prejudicando a sua recepção e consequentemente as comunicações.
- As ondas de radiofrequência podem: refletir, espalhar, refratar, difratar ou ser absorvida através da superfície ou do espaço por onde irão trafegar e com isso prejudicar as transmissões.
- As considerações sobre o fator K dizem respeito à refração atmosférica, que se observa nas ondas de rádio: Ocorre devido às variações no índice de refração do ar com a altura. Como consequência, esta muda de acordo com as condições climáticas devido às alterações de temperatura, pressão e umidade.