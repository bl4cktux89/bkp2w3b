### **Introdução**

A capacidade de transmissão de dados de um canal pode ser influenciada por diversas variáveis ambientais, tais como **ruído**, **atenuação** e **eco,** que serão descritas a seguir:

### Ruído

O ruído em uma transmissão de dados é de difícil eliminação, na maioria dos casos sempre estará presente junto ao sinal a ser transmitido. O ruído pode ser classificado de diferentes formas:

- **Ruído Térmico:** Também conhecido como **ruído branco**. É o ruído gerado pela agitação dos elétrons nos condutores metálicos e gerados, também, pelos dispositivos eletroeletrônicos, tais como, transmissores e receptores. Este ruído tempo como característica estar presente em todo o espectro de frequência, por essa razão é conhecido como ruído branco. O aumento desse ruído é provocado, principalmente, pelo aumento da temperatura no meio de transmissão e nos dispositivos.
- **Ruído de Intermodulação:** O ruído de intermodulação ocorre quando temos uma transmissão multiplexada. A “mistura” de frequências pode gerar um sinal que interfere na transmissão do sinal contendo informação.
- **Crosstalk:** Este tipo de ruído ocorre, principalmente, devido à proximidade entre os canais com alta potência e frequência de transmissão. Também é conhecido como linha cruzada. Você deve ter se deparado com este tipo de ruído quando conversa ao telefone!
- **Ruído Impulsivo:** O ruído impulsivo ocorre em função de eventos externos decorrentes de falhas em equipamentos e no fornecimento de energia elétrica como, por exemplo, surtos de tensão quando o fornecimento de energia é reestabelecido após a interrupção no fornecimento, ou até mesmo, a retirada de uma lâmpada pode provocar a geração do ruído impulsivo. Este tipo de ruído não afeta de maneira substancial as transmissões analógicas, podendo apenas causar um corte temporário na transmissão de voz em sistemas de telefonia. Entretanto, eles são fatais nas transmissões digitais, sendo uma das principais fontes de erro.

### Atenuação e eco

A **atenuação** e o **eco** são outras fontes de distorções sobre o sinal: A **atenuação (A)** corresponde ao “enfraquecimento” ou perda de potência em função da distância entre o transmissor e o receptor e é medida em dB/m (decibel por metro), conforme equação abaixo; O **eco** ocorre sempre que existe uma alteração na impedância ou descasamento de impedância como, por exemplo, entre o cabo par trançado e seus conectores e placas de rede.

onde:

**dB:** representa a unidade decibel. A unidade básica é o Bel, em homenagem a Alexander Graham Bell, cientista e inventor do telefone.

**Psaída**: representa a potência que chega no receptor ou potência final

**Pentrada**: representar a potência de referência ou inicial, aquela potência de entrada no meio de transmissão

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/7/6/9/76993/if01_2854.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/7/6/9/76993/if01_2854.jpg)

Figura 1 - Processo de comunicação.

Por que utilizamos dB? Empregamos a unidade dB em virtude da grande variação de potência (final / inicial), conforme mostrado na Tabela 1. Outro motivo para o uso da escala logarítmica está associado com a resposta auditiva em função da potência acústica. Na equação abaixo, quando temos valores positivos da potência (P), indica que houve aumento da potência e valores negativos de (P) indicam a atenuação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/6/363664/29038.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/6/363664/29038.png)

Figura 1 - Escala logarítmica da potência.

Fonte:

**Exemplo 1**

A potência do sinal de antena que chega a sua casa é de 1,0 mW (1 milewatt), enquanto que a potência que saiu da antena transmissora é de 10 mW (10 milewatts). Nessa situação qual é a atenuação do sinal?

**Resposta:** Aplicando a fórmula, fica: 

### Relação Sinal/Ruído (SNR):

A **relação Sinal/Ruído (SNR)** É a razão entre a potência do sinal a ser transmitido pela potência do ruído de fundo ou ruído branco. Quanto mais baixa for a relação SNR maior será a dificuldade para os receptores em distingui o sinal do ruído. Portanto, devemos maximiza-lo sempre que possível. Em termos matemáticos a relação sinal/ruído é dada por:

**Exemplo 2**

Um sinal tem potência igual a 1W enquanto que a ordem do ruído brando é igual a 0,1W. Determine a relação sinal ruído:

**Resposta:** Aplicando a fórmula do do SNR:

Você já deve ter percebido que quanto mais afastado de um roteador wireless, menos dados são transmitidos. Isso se deve, principalmente, a relação S/R que diminui à medida que nos afastamos do roteador. Essa capacidade de transmissão será descrita de forma matemática no próximo tópico.

### Largura de Banda versus Banda passante

A banda passante de um sinal corresponde ao intervalo de frequências que compõe o sinal, enquanto que a largura de banda corresponde ao tamanho de sua banda passante. Em transmissão de dados, os meios de transmissão apresentam limites físicos para o transporte de dados. Portanto, a banda passante é o intervalo entre esses limites inferiores () e superiores (), conforme Figura 2. Por exemplo, em transmissão de voz via telefone utilizamos uma faixa de frequência compreendida entre 300 Hz e 3400 Hz. Essa faixa de frequência é conhecida como banda passante, enquanto que a sua largura de banda corresponde à diferença entre a máxima frequência e a mínima (LB=Wmax –Wmin). Neste exemplo, portanto, a largura de banda (LB) é igual a 3100 Hz (3400 – 300 = 3100 Hz).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/7/2/7214/i01_535.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/7/2/7214/i01_535.jpg)

Figura 2 - Largura de banda e banda passante

**Exemplo 3**

Um canal tem largura de banda (W) igual a 4000 Hz. E supondo que este canal esteja utilizando uma modulação dibit (2 bits por baud), qual a capacidade máxima do canal desconsiderando o ruído branco?

**Resposta:** Aplicando o teorema de Nyquist temos: _**C=2.W.Mn=2.4000.2=16000Hz**_ ou _**16KHz**_. Portanto, a capacidade máxima desse canal desconsiderando o ruído branco é de 16KHz.

### Capacidade máxima de um canal

A capacidade máxima de transmissão de dados em canal é dada em bits por segundo (bps). Muitas vezes nos referimos a capacidade máxima de transmissão, principalmente em redes de computadores, como largura de banda (LB) para determinar a largura de banda nominal de uma rede, em bits por segundo. Portanto, cuidado! No presente tópico, nos referimos a Largura de Banda (W) como sendo a diferença entre a maior e a menor frequência utilizada na transmissão, como já comentado no item _**Largura de Banda e Banda Passante**_.

A capacidade máxima de transmissão de um canal é avaliada a partir de dois teoremas: O primeiro deles é conhecido como teorema de Nyquist e é empregado quando desconsideramos o ruído branco e dada por:

Onde: W é a largura de banda do canal, medida em Hz e Mn é o número de níveis do sinal. Podemos ter, por exemplo, 2 bits/baud, 4 bits/baud (00, 01, 10 e 11). Portanto, o monobit representa 1 bit por baud, dibit representa 2 bits por baud e tribit representa 3 bits por baud e assim sucessivamente.

Apesar de apresentar uma aproximação satisfatória para determinar a capacidade do canal, o teorema de Nysquist não leva em consideração o ruído. A partir de estudos baseados no teorema de Nyquist, em 1948, Claude Shannon provou que a capacidade de transmissão de um canal é limitada também pelo ruído introduzido na transmissão, o chamado ruído térmico ou branco. A equação de Nyquist é então modificada para:

Onde: C é a capacidade do canal levando em consideração o ruído; W é a largura de banda do sinal, em Hz; e S/N é a relação sinal ruído (em W), conforme descrita anteriormente.

**Exemplo 4**

Dada uma transmissão em linha telefônica onde a relação S/N é igual a 30 dB ou 1000W e a largura de banda (W) é igual a 3100 Hz, qual a capacidade máxima do canal, considerando a presença de ruído?

Resposta: A relação S/N é dada por: , substituindo os valores, fica: ; aproximadamente **31 Kbps.**