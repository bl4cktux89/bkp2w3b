### Objetivo:

Neste tópico aprenderemos a conhecer e a calcular a 1ª zona de Fresnel, assunto este primordial para os projetos de enlace de rádio. De posse dos conhecimentos aqui apresentados, o aluno terá plena capacidade de projetar uma comunicação em localidades distantes utilizando as técnicas de radiofrequência.

### Introdução

O físico francês Augustin Jean Fresnel (1788 - 1827) contribuiu significativamente na teoria da óptica ondulatória, estudando o comportamento da luz pôde desenvolver originalmente a lente Fresnel para uso em faróis de sinalização marítima; Seu desenho possibilita a construção de lentes de grande abertura e curta distância focal, sem o peso e volume do material que seriam necessários a uma lente convencional.

Comparadas a estas, as Fresnel são bem mais finas, permitindo uma passagem maior de luz e, assim, os faróis com elas equipados são visíveis a distâncias bem maiores.

Também seus estudos mostraram grande aplicação nos sistemas de rádio, pois por suas teorias foi comprovado que um sinal de rádio em linha de visada direta ocupa uma área com forma de elipsoide concêntrica de raio máximo r0 em torno da linha de visada.

Esta área foi chamada de 1ª zona de Fresnel, em homenagem às teorias de seu autor, que comprovaram sua existência e a importância destas para o estudo do rádio enlace.

Essa zona é importante para a integridade dos links de rádio frequência, porque ela define uma área em torno da linha de visada que pode introduzir interferências no sinal, caso ela seja obstruída.

Obstáculos na zona de Fresnel, tais como árvores, topo de colinas e edifícios, podem refratar ou refletir o sinal principal para longe da antena receptora, mudando assim a linha de visada. Os mesmos obstáculos podem absorver ou espalhar o sinal de rádio frequência principal, causando degradação ou a paralisação por completo do enlace.

Os estudos apontam que um bloqueio de até 30% nesta elipsoide de Fresnel introduzirá pouca ou nenhuma interferência no link, mas caso este limite aumente a atenuação da onda recebida passa a ser relevante causando degradação e perda da potência efetiva irradiada na recepção. (MEDEIROS, 2010)

Para livrar a elipsoide de Fresnel a um limite seguro, aumenta-se a altura das antenas pelas torres e matematicamente aplica-se os valores de K-mínimo e K-médio discutidos na aula anterior.

A figura 1 mostra a elipsoide de Fresnel em um sistema ponto a ponto e utilizando a formula para o cálculo de r0 consegue-se o valor do raio em qualquer parte da trajetória do link baseado na sua linha de visada direta.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295048/16871.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295048/16871.png)

Figura 1 - 1ª Zona de Fresnel

Como regra prática, um enlace é considerado com visada direta, ou seja, com fenômeno de difração desprezível, se não existir nenhum obstáculo dentro da primeira zona de Fresnel. Isto é aplicado devido ao fato de que toda a zona de Fresnel somadas resultam em um valor que corresponde à metade do valor de apenas a primeira elipsoide.

O raio da primeira elipsoide de Fresnel em um ponto qualquer entre o transmissor e o receptor é dado pela fórmula:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295049/16872.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295049/16872.jpg)

Equação para cálculo de r0

Onde:

- .r0 = Raio da zona de Fresnel em metros
- .d1 e d2 = Distância a partir de cada uma das antenas, ao ponto onde se quer determinar o raio em quilômetros.
- .d  ou .d = Distância entre as antenas em quilômetros.
    
    link
    
- .f = Frequência de operação em GHz ou MHz

Sendo f a frequência (MHz ou GHz), d1 e d2 as distâncias (km) entre o transmissor e o receptor no ponto em que o raio da elipsoide de Fresnel é calculado, e d a distância total entre transmissor e receptor, têm-se o valor do raio em qualquer distância entre as antenas ilustrado na figura 2 e, com o cálculo de r0 consegue-se precisar as obstruções que poderão existir neste caminho entre as duas antenas

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296885/16874.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296885/16874.png)

1ª Zona de Fresnel

Como experimentalmente, 50% da potência irradiada está concentrada na 1ª Zona de Fresnel, recomenda-se que ela esteja livre e desimpedida de obstáculos e de qualquer interferência que venha a prejudicar o enlace conforme ilustrado na figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/3/299312/16876.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/3/299312/16876.png)

Figura 3 - Obstrução na 1ª zona de Fresnel

### Análise de Obstrução

A condição de visibilidade elétrica entre as antenas de um rádio enlace depende do valor do fator K da Terra. Os enlaces devem ser dimensionados para desobstrução não apenas em condições normais de propagação, mas também em condições de fator K reduzido.

A condição de visibilidade elétrica difere da de visibilidade geométrica e está associada aos chamados elipsoides de Fresnel. Estes elipsoides correspondem ao lugar geométrico dos pontos, cuja soma das distâncias às antenas é um múltiplo inteiro de meio comprimento de onda.

Considera-se um enlace desobstruído quando não há obstáculos no interior do primeiro elipsoide ou 1ª zona de Fresnel, correspondente a pontos cuja soma das distâncias ao transmissor e receptor é inferior a meio comprimento de onda.

As zonas de Fresnel são anéis circulares delimitados por dois círculos concêntricos adjacentes, que correspondem às seções retas dos elipsoides no plano perpendicular ao plano do enlace.

Segundo Santos Junior (2005) uma regra comumente utilizada como critério de visibilidade é ter 100% da primeira Zona de Fresnel liberada para o valor mediano de K (valor típico K-médio = 4/3 ou considerar 1) e 70% de liberação para o valor de K excedido durante 99,9% do tempo, denominado K mínimo (valor típico K-mínimo = 2/3 ou 0,7). (NASCIMENTO, 1992).

Como o fator K da Terra varia aleatoriamente, podem ocorrer situações extremas em menos de 70% do raio do primeiro elipsoide de Fresnel onde este seja obstruído por algum obstáculo do terreno, aumentando a atenuação do percurso e provocando desvanecimento lento (perdas por difração).

Portanto, para se determinar a altura de antenas em locações de altitudes diferentes e conseguir a verificação se algum obstáculo está interferindo a 1ª Zona de Fresnel, pode-se usar a seguinte equação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296877/16878.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296877/16878.png)

Equação de Obstrução

Onde:

- Δh = Distância do topo do obstáculo à linha de visada, em metros.
- .d1 e d2 = Distância do obstáculo às antenas, em metros.
- .d = d1 + d2 = Distância entre as antenas, em metros.
- .h1 e h2 = Altitude, em relação ao nível do mar, dos pontos de transmissão e recepção, em metros.
- .h0 = Altitude do obstáculo em relação ao nível do mar, em metros
- R = Raio de curvatura da Terra = 6,37 x 10
    
    6
    
- K = Constante que representa o decréscimo do índice de refração da atmosfera com a altitude. O valor deve ser calculado para as duas situações:

1ª – Para obter 70% de desobstrução da 1ª zona de Fresnel (K-mínimo), considerar K = 0,7 (situação mais desfavorável).

2ª – Para obter 100% de desobstrução da 1ª zona de Fresnel (K-médio), considerar o fator K = 1 (situação mais favorável).

Nota:

O valor de Δh deve sempre ser positivo e maior que 60% do raio da Zona de Fresnel a fim de obter desobstrução desta área, conforme ilustrado pela figura 4. (SANTOS JUNIOR 2005, p. VI 16)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299545/16879.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/9/5/299545/16879.png)

Figura 4 - Análise da obstrução

Para ficar bem claro os pontos estudados, vamos resolver uma questão onde envolve o cálculo da 1ª zona de Fresnel e o cálculo de obstrução, no final será possível verificar se o link não se encontra obstruído. A figura a seguir ilustra um cenário onde se deseja construir um enlace de rádio.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/0/1/300108/16880.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/0/1/300108/16880.png)

Figura 5 - Exemplo para cálculo

Como ponto de partida, deve-se calcular o r0 da 1ª zona de Fresnel utilizando uma frequência de 2,4GHz para este enlace.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296886/16881.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/8/296886/16881.jpg)

Cálculo de r0

Como segunda parte do exercício iremos calcular a obstrução pela seguinte equação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297043/16882.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/0/297043/16882.jpg)

Cálculo de Obstrução

Tendo os dois valores (r0 e Δh) pode-se executar uma comparação a fim da verificação de desobstrução da 1ª zona de Fresnel, observe a imagem na sequência:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/0/1/300111/16883.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/0/1/300111/16883.png)

Análise dos valores

Pode-se concluir que a 1ª zona de Fresnel encontra-se 100% livre onde ainda tem-se 2,03 metros de margem de segurança para que o topo do prédio em h0 comece a adentrar a elipsoide de Fresnel.

### Conceito de Banda Estreita e Banda Larga

Grande parte das comunicações que se utilizam de técnicas de rádio frequência como rádio, televisão e radiocomunicação, o faz através da técnica de transmissão por banda estreita.

Esta técnica consiste em comprimir o máximo de informações dentro de uma banda o mais estreita possível, possibilitando assim, que cada estação opere sobre uma determinada e estreita faixa de frequência, sem interferir nas frequências inferiores e superiores onde, provavelmente, deve existir outra estação efetuando transmissões.

Para que o sinal de uma estação em banda estreita seja recebido e a informação possa ser recuperada, ele terá de manter um nível de potência irradiada acima do ruído local, conhecido também como ruído de fundo, que são as interferências causadas por várias fontes de geração de campos magnéticos, perda por deslocamento no espaço entre outros.

Portanto, a técnica de transmissão convencional dotou os equipamentos para produzir uma pequena largura de banda com alto nível de potência irradiada, com a finalidade de eliminar o ruído ambiente pela alta potência e não interferir nas outras frequências pela diminuta banda passante.

Como exemplo de transmissões de banda estreita temos os rádios de comunicação e os transmissores de rádio AM (Amplitude Modulada), com banda de aproximadamente 3KHz, possuindo baixa qualidade de sonorização. Os rádios que transmitem em FM (Frequência Modulada), possuem banda passante de 175KHz, onde a qualidade sonora condiz com o maior espaço de banda. Os canais de televisão necessitam de banda passante maior, chegando a 6MHz por canal, devido à grande quantidade de informações que cada canal necessita transmitir, como por exemplo: sinal de croma (cor); sinal de Y (preto e branco), transmitidos em amplitude modulada, sinal de sincronismo, (vertical e horizontal) e sinal de som - transmitidos em frequência modulada dentro do canal de televisão. (MEDEIROS, 2010)

O sinal de banda estreita, apesar de funcional até os dias de hoje, pode ser facilmente obstruído ou sofrer graves interferências com a transmissão de sinais na mesma frequência e com potência maior. Tal obstrução e/ou interferência pode afetar muito o canal que está sendo irradiado. Devido a isso, todas as emissoras que transmitem em canal estreito, carregam muito a sua potência irradiada com a finalidade de reduzir ao máximo tais problemas.

Os sistemas que operam em banda larga utilizam uma técnica de codificação para a transmissão digital que ao invés de transmitir o sinal continuamente sobre uma banda estreita de frequência, transmite várias partes separadamente através de um amplo canal.

O novo sinal propagado tem uma densidade de potência muito menor se comparado com as transmissões de banda estreita, porém como são transmitidas pequenas quantidades de informação sobre um amplo canal de frequência, a soma de todas as informações será a mesma em relação à potência que uma emissora de banda estreita empregaria para transmitir a mesma informação.

### Revisão:

- A 1ª zona de Fresnel são elipsoides concêntricas que são formatadas entre duas antenas direcionais em condições de visada direta entre elas.
- É importante o cálculo da 1ª zona de Fresnel, dado por r0 para que este permaneça livre de qualquer obstáculo.
- É considerado aceitável que pelo menos 70% do campo calculado por r0 esteja livre de qualquer impedimento ou interferência, seja por árvores, prédios ou montanhas.
- Nas transmissões de rádio digital é utilizado o processo de banda larga ao contrário das transmissões radiofônicas e de televisão que utilizam banda estreita.

Esta técnica de banda larga visa à proteção contra interferências no sinal que poderia paralisar a transmissão por completo.