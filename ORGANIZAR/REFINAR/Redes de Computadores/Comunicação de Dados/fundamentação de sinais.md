### **Introdução a dados e sinais**

A função dos meios de transmissão e transportar dados na forma de sinais eletromagnéticos. Existem basicamente duas formas de representar esses dados no meio de transmissão, a representação pode ser Analógica e Digital.  Os dados digitais possuem estados discretos, assumindo valores finitos, enquanto que a os dados analógicos assumem valores contínuos. Da mesma forma, os sinais podem ser analógicos e digitais: os sinais digitais podem ter apenas valores limitados de valores (0 ou); enquanto que os sinais analógicos podem ter infinitos valores (Forouzan, A. B, 2007), conforme mostrado na Figura 1.

Como pode ser observado na figura abaixo, o sinal analógico tem vários níveis de intensidade em relação ao eixo y à medida que o sinal se desloca ao longo do eixo x. Este mesmo sinal analógico pode ter o seu sinal amostrado com o objetivo de transformar em digital. Entretanto, o sinal digital pode assumir diferentes valores, mas que são, geralmente, representados por níveis lógicos 0 e 1 para representar tais diferentes valores.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/3/3/343308/25262.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/3/3/343308/25262.png)

Figura 1 - Sinal analógico e digital.

Um **sinal** é a entidade que carrega a informação e essa entidade pode ser analógica ou digital.

### Sinais analógicos periódicos

De acordo com (Forouzan, A. B, 2007) os sinais analógicos periódicos podem ser divididos em **simples** e **composto**. Um sinal periódico simples, uma **onda senoidal**, não pode ser decomposta em sinais mais simples, enquanto que a composta pode ser decomposta em senoides múltiplas.

A onda senoidal é a forma fundamental para se representar um sinal analógico e periódico. Como pode ser observada na Figura 2, uma onda senoidal (**sin(x)**) é composta por uma curva que oscila de forma consistente e contínua.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/0/5/290586/16807.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/0/5/290586/16807.png)

Figura 2 - Sinal senoidal e cossenoidal. Em transmissão de dados utilizamos uma onda senoidal para representar o sinal

A onda senoidal mostrada na Figura 3 apresenta quatro parâmetros importantes que descrevem totalmente o seu comportamento: Amplitude, comprimento de onda, frequência e fase. Tais parâmetros são descritos abaixo a partir da Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/7/4/1/1/741145/16531.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/7/4/1/1/741145/16531.jpg)

Figura 3 - Onda senoidal, mostrando os parâmetros de Amplitude, Frequência e Fase

- **Amplitude:** A amplitude representa o valor absoluto da máxima intensidade, associado com a energia que a onda transporta. Normalmente, medimos a amplitude máxima de uma onda pela unidade Volts (V). Um típico exemplo do nosso dia-a-dia é a representação do sinal elétrico de nossas residências que possui amplitude de pico entre 155 a 179 Volts. Os valores que conhecemos de 110 e 127 Volts são valores médios eficazes (RMS, do Inglês root mean square).
- **Período e Frequência:** O **Período (T)** de onda corresponde ao tempo (em segundos) necessário para a onda completar 1 ciclo. Por sua vez, a **Frequência** (f) corresponde à quantidade ciclos completados em 1 segundo. Portanto, a Frequência e o período são inversos entre si, conforme equação abaixo:

**Exemplo 1**

A rede elétrica brasileira opera em frequência de 60 Hz. O período dessa onda senoidal pode ser determinado por:

**Resposta:**  

Isso quer dizer que a mudança de ciclo ocorre a cada 16,6 ms. Se fosse utilizado uma câmera de alta velocidade, a lâmpada apareceria "piscando", mas como nossos olhos são capazes 40 ms segundos para processar uma imagem não seria possível a variação de intensidade da lâmpada.

- **Comprimento de onda:** O comprimento de onda (λ), medido em metros (m) corresponde a distância entre dois vales de uma onda ou dois picos, conforme Figura 3. No caso de meios não guiados, como uma transmissão via rádio, o comprimento de onda é de fundamental importância. Para se determinar o comprimento de onda de qualquer transmissão não guiada devemos conhecer a frequência de operação que relaciona com o comprimento de onda (λ) de acordo com as equações abaixo:

Onde c é igual a velocidade da luz no vácuo igual a 300.000.000 de m/s.

**Exemplo 2**

Qual a frequência de uma onda (f)  cujo o comprimento de onda (λ) é igual a 0,1 m?

**Resposta:** Considerando que a propagação da onda é no vácuo a relação fica:

  ou então 3GHz

A Frequência é medida em Hertz (Hz), enquanto que o período em segundos. As unidades de período e frequência são mostradas na Tabela 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/0/361087/28618.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/0/361087/28618.png)

Tabela 1 - Unidades representativas de de período e frequência.

Fonte: Forouzan, A. B, 2007

- **Fase de uma onda:** A fase de uma onda descreve a posição da onda em relação ao instante 0 no eixo dos tempos (Forouzan, A. B, 2007). A fase é medida em graus ou radianos (360º equivale a 2/360 rad e 1 rad equivale a 360/2). A partir da Figura 5 podemos observar:
    - Uma onda senoidal com fase 0º se inicia no instante 0 com amplitude zero. A Amplitude é crescente.
    - Uma onda senoidal com fase 90º se inicia no instante 0 com amplitude máxima. A Amplitude é decrescente.
    - Uma onda senoidal com fase 180º se inicia no instante 0 com amplitude zero. A Amplitude é decrescente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/1/361155/28647.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/1/361155/28647.png)

Figura 5 - Três ondas com a mesma frequência e amplitude, mas defasadas.

Fonte: Forouzan, A. B, 2007