### Objetivo:

Neste tópico aprenderemos sobre as antenas utilizadas para irradiar os sinais provenientes dos rádios _**Access Point**_ e os diferentes tipos existentes em conjunto com sua aplicação.

### INTRODUÇÃO

Pela definição de Santos Junior (2005) uma antena é um dispositivo passivo usado para converter um sinal de Radiofrequência (RF) em uma linha de transmissão (um cabo ou guia de onda) em uma onda propagando no ar.

Neste conceito rudimentar, podemos classificar duas ideias fundamentais sobre as antenas:

1º – Antenas convertem energia elétrica em ondas de RF durante a transmissão, ou convertem ondas de RF em energia elétrica quando da recepção.

2º - As dimensões físicas da antena, tais como comprimento e número de elementos estão diretamente relacionados com o comprimento de onda da frequência que a antena pode propagar ou receber.

A forma mais simples de uma antena é conhecida como dipolo de meia onda que consiste de um elemento simples que pode ser construído com fios de cobre ou de alumínio, alimentado no seu centro por um rádio cujo comprimento do dipolo é exatamente igual a meio comprimento de onda do sinal, conforme ilustrado na figura 1. O comprimento de onda é o parâmetro que expressa à distância que a onda percorre em um ciclo completo dado em metros.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295032/18047.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295032/18047.jpg)

Figura 1 - Dipolo simples de meia onda

Como o período da onda senoidal é dado por t sendo o intervalo de tempo em que um ciclo se repete, pode-se afirmar que no período t, a onda terá se deslocado exatamente o seu comprimento, portanto se a velocidade de propagação da onda é dada pela distância percorrida no intervalo de tempo, basta dividir este comprimento de onda que é dado por lambda (λ) pelo tempo t que teremos a velocidade desta onda.

Como a frequência é o inverso do período, podemos reescrever a equação para que se consiga medir o comprimento da onda no espaço pela frequência que a mesma está sendo gerada, conforme ilustra a formula a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295029/18046.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/5/0/295029/18046.jpg)

Formula de lambda

Pelo demonstrado, para que as antenas tenham o melhor desempenho na transmissão e recepção dos sinais de radiofrequência é necessário serem construídas no tamanho exato da onda a ser transmitida por elas ou de meia onda no caso dos dipolos.

### TIPO DE ANTENAS

As antenas podem ser classificadas de acordo com o número de dipolos e por sua construção mecânica. Desta forma podemos classificar as antenas em três tipos básicos:

- Omnidirecionais
- Semidirecionais
- Direcionais

**Antena Omnidirecional**

Antenas omnidirecionais são usadas para aplicações ponto para multiponto em grandes áreas, onde não se tem com exatidão a direção do receptor, irradiando energia em 360º a sua volta de forma horizontal, o que não ocorre com a forma vertical, abrindo a sua transmissão em poucos graus.

A forma que as antenas irradiam seus sinais ou sua abertura de iluminação é determinada por graus e está iluminação possui dois planos diretores, a saber:

- Plano irradiador Horizontal ou Azimute – E
- Plano irradiador Vertical ou Elevação – H

Portanto uma antena omnidirecional possui 360º de plano E (azimute ou vista de cima da antena) e no plano H, vista de corte ela apresenta um ângulo de propagação limitado, que dependendo da antena pode variar de 7 a 90 graus. A figura 2 ilustra uma antena omnidirecional. As antenas omnidirecionais são utilizadas nos pequenos _**rádios Access**_ Point com potências de irradiação de 2dBi a 5dBi.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326914/18048.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326914/18048.png)

Figura 2 - Antena Omnidirecional

Fonte: Santos Junior, 2005 p. VI 31

**Antena Semidirecional**

Conforme definido por Santos Junior (2005, p. VI 35) antenas semidirecionais são também conhecidas como “um conjunto de fase, ou seja, como múltiplas antenas trabalhando juntas para amplificar algumas ondas e cancelar outras, de tal forma que a soma das energias irradiadas tem a forma de um feixe focado”.

As antenas semidirecionais são largamente usadas para pequenas e médias distâncias principalmente nas transmissões de telefonia celular, onde cada antena instalada numa torre ERB (Estação Rádio Base) tem seu plano diretor E (azimute) com abertura típica de 120º e, utilizando três antenas tem-se a cobertura de 360º, abrangendo com muito mais potência de alcance do que a utilização de uma única antena omnidirecional.

O padrão de radiação do sinal deste tipo de antena é basicamente uma frente de onda em uma direção com maior potência irradiada chamada de frontal e, um pouco do sinal irradiado para trás do elemento principal.

O sinal que escapa para trás, apesar de ser de pouca intensidade, deve ser considerado quando se instala mais de uma antena no mesmo mastro, podendo o lóbulo que escapa para trás saturar a antena que estiver disposta imediatamente atrás do mastro.

Portanto, um cuidado extra deve ser tomado quando da instalação de várias antenas com alturas diferentes no mesmo mastro e aquisição das mesmas com uma relação frente/costa adequada.

Já a relação frente/costa indica a diferença de ganho entre o lóbulo principal (onda que é irradiada pela frente da antena) e o lóbulo posterior (onda que escapa por trás da antena). Esta relação deve ser a maior possível, pois seu valor indica o quanto o sinal posterior é menor do que o frontal.

Como exemplo podemos considerar uma antena de ganho 25dBi (decibel isotrópico) cuja RFC (relação frente costa) é de 40dB, isso significa dizer que o sinal que vai para a frente é de 25dBi e o sinal que vai para trás é de -15dBi pois, (25 – 40 = -15dBi). A figura 3 ilustra uma típica antena semidirecional. SANTOS JUNIOR (2005)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326939/18049.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326939/18049.png)

Figura 3 - Antena Semidirecional.

Fonte: Santos Junior, 2005

**Antena Direcional**

As antenas direcionais ou parabólicas são antenas que transmitem o sinal em uma direção bem definida com a máxima potência neste ponto.

São construídas com a utilização de uma parábola ou prato e sendo instalado o alimentador no seu centro, geralmente um dipolo ou conjunto deles, posicionado no foco desta parábola. Quando da transmissão, o sinal é direcionado para a parábola que age como um elemento refletor e o direciona quase que perfeitamente paralelo. Na antena receptora o sinal que chega é refletido pela parábola e focado no dipolo, sendo posteriormente encaminhado ao rádio receptor pela linha de transmissão.

Este tipo de antena apresenta alto ganho em potência e pode alcançar grandes distâncias, de até 40 quilômetros sem grandes dificuldades, dependendo neste caso das alturas das antenas e da sensibilidade dos rádios empregados.

Esta propriedade de alto valor em ganho das antenas direcionais são devidos à sua diretividade que, segundo Medeiros (2010, p. 198) “é a propriedade de cada tipo de antena de irradiar mais fortemente em algumas direções do que em outras”, ou seja, o ganho da antena é a capacidade de concentrar na direção de interesse a potência que seria irradiada em todas as direções caso fosse utilizado uma antena omnidirecional.

A antena direcional é um elemento passivo, o que significa que ela não aumenta a potência do sinal, mas formata o campo de irradiação, focando-o e obtendo aumento ou diminuição das distâncias que a onda propagante irá viajar. A figura 4 ilustra o comentado. (SANTOS JUNIOR, 2005)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326945/18050.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326945/18050.png)

Figura 4 - Antena Direcional

Fonte: Santos Junior, 2005

Quanto maior for a área do elemento refletor (parábola), maior será o ganho da antena conforme a fórmula demonstra, onde A é a área do refletor em m² e o valor do ganho da antena é expresso em dB (decibel).

Ganho = 10.log.[ (4.π.A) / λ ] ¹/²

### POLARIZAÇÃO DAS ANTENAS

As antenas irradiam energia através de ondas eletromagnéticas transversais compostas de um campo elétrico e de um campo magnético. Estes campos são perpendiculares entre si e também perpendiculares à direção de propagação desta onda conforme ilustrado na figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326918/18051.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/6/9/326918/18051.png)

Figura 5 - Polarização de antenas

Fonte: Medeiros, 2010

O campo elétrico da onda eletromagnética é utilizado para determinar sua polarização e demonstram como os campos se orientam no espaço. A onda será verticalmente polarizada quando o campo elétrico é perpendicular à superfície da Terra e ela será horizontalmente polarizada quando o campo elétrico for paralelo à superfície do planeta Terra.

Em um sistema de rádio enlace para a máxima performance e transferência de energia, ambas as antenas devem ter a mesma orientação espacial, ou seja, devem estar com a mesma polarização para evitar perdas do sinal irradiado.

Quando as antenas instaladas não estão polarizadas adequadamente, ou seja, não estão alinhadas perfeitamente, pode acontecer uma perda de potência irradiada chamada “perda por despolarização”, e esta perda pode ser calculada pela expressão:

Perda por desalinhamento (dB) = 20 log (cós Ó¨)

### TORRES E SUSTENTAÇÃO DAS ANTENAS

As torres ou mastros de sustentação são produtos extremamente importantes num sistema de rádio enlace, pois são responsáveis pela elevação das antenas com o objetivo de livrar a linha de visada entre as antenas de qualquer obstáculo.

Devem ser dimensionadas por meio de um estudo de carga, considerando as antenas, guias de onda e cabos a serem instalados, inclusive levando em conta possíveis expansões futuras. Para a situação em que a torre é existente, são necessários cálculos para um estudo de carga, verificando se a torre suporta realmente a antena a ser utilizada no projeto.

Outro detalhe importante na consideração das torres e mastro, diz respeito a sua fixação. As torres não podem sofrer nenhum deslocamento das suas bases, portanto, devem ser extremamente firmes para que possam suportar rajadas de vento e quaisquer outras intempéries do clima. PORTAS (2008)

Existem modelos de torres voltadas para cada tipo de aplicação, altura e solo, a figuras a seguir ilustram as principais torres e mastros utilizados para sustentação das antenas.

**Autoportante:** São projetadas para suportar uma grande quantidade de antenas com altura que pode chegar a mais de 120 metros.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293187/18446.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293187/18446.jpg)

Torre Autoportante.

Fonte: Hit1912 / Shutterstock.com

**Estaiada:** Economicamente mais vantajosas que a autoportante (maior capacidade), tendo como desvantagem a necessidade de um maior espaço devido à utilização dos estaios.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293190/18448.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293190/18448.jpg)

Torre estaiada

**Postes:** São utilizados quando a altura necessária não é muito grande (≈ 40 metros) e o número de antenas é baixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293191/18609.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293191/18609.jpg)

Torre Poste

Fonte:

**Cavaletes:** São estruturas pequenas usadas para suportar antenas a um nível pouco acima do solo ou do topo do prédio.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293192/18610.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/1/293192/18610.jpg)

Torre Cavalete

Fonte:

### Revisão:

Para a irradiação dos sinais de alta frequência originários do sistema de rádio Access Point são utilizadas as antenas que tem a propriedade de transformar sinal de alta frequência em sinal eletromagnético e assim, serem irradiados no espaço.

Existem três tipos de antenas, que são:

- Antenas Omnidirecionais que irradiam para todos os lados.
- Antenas Semidirecionais que irradiam para locais com ângulos mais reduzidos.
- Antenas Direcionais, que irradiam para locais com ângulos bem fechado.

A onda eletromagnética gerada na antena é formada por dois sinais que estão juntos, porém, perpendiculares em 90º, a saber:

- Sinal elétrico
- Sinal magnético