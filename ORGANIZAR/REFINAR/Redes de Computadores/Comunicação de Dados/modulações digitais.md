### **Introdução a Modulação Digital**

Para transportar dados digitais por meio de ondas eletromagnéticas no espaço livre, como é o caso das redes wireless, é necessário modificar (modular) a onda portadora. Diferentemente da modulação analógica, como AM e FM, que possuem portadoras analógicas e informação analógicas, a Modulação Digital utiliza uma portadora analógica que é modulada por um sinal digital.

Os sistemas puramente analógicos como AM e FM têm sido substituídos por sistemas totalmente digitais, por apresentar maior capacidade de transmissão e confiabilidade. Além disso, em transmissões do tipo banda base toda a capacidade do canal é utilizada para transmitir um único tipo de sinal, impedindo que o canal possa ser multiplexado para transportar informações diferentes. Outro fator importante a ser salientado é impossibilidade de transmissão do tipo banda base em longas distâncias por meio de antenas e cabo par trançado. Lembrando que o alcance máximo do cabo par trançado é de 100 m.

Com a modulação digital podemos ter a capacidade do canal otimizada, reduzindo dessa forma, o custo das transmissões, principalmente quando temos aplicações que utilizam o compartilhamento dos recursos de rede, como é o caso do acesso à Internet por xDSL (acrônimo para Digital Subscriber Line, Linha digital de assinante) e televisão a cabo.

Você deve estar pensando: mas o áudio e vídeo podem ser gerados de forma analógica, como eles podem ser transmitidos de forma digital? Resposta: Tais sinais passam por processos de conversão analógico-digital conhecidos como PAM (modulação por amplitude de pulso) e PCM (modulação por código de pulso).

### Análise de um sinal digital

Antes de passarmos para os diferentes tipos de modulação devemos entender alguns fundamentos sobre o sinal digital. Um sinal digital é caracterizado por apresentar variações discretas (descontinuas) de amplitude com valores padronizados, conforme mostrado na Figura 1. A duração de cada nível é estabelecida em múltiplos de um valor mínimo, conhecido como  (tau).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363510/28905.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363510/28905.png)

Figura 1 - Forma da onda de um sinal digital de dois níveis

**Velocidade de Modulação versus Velocidade de Transmissão**

A Velocidade de Modulação (Vm) e a Velocidade de Transmissão (Vt) são duas grandezas muito utilizadas em transmissão de dados digitais. A **Velocidade de Modulação**, também é conhecida como **taxa de modulação**, indicando quantas vezes por segundo um sinal digital é transmitido (Nascimento, J. 2000). Para indicar a taxa de modulação utilizamos a unidade baud, definida por:

onde: Vm = velocidade de modulação e   é igual a largura da menor transição do sinal digital

**Exemplo 1**

Um sinal digital tem a duração da largura de pulso igual  . Qual sua velocidade de modulação?

**Resposta:** Para começar, devemos converter de microssegundos para segundos.    é igual a 0,0002 segundos ou  segundos. Aplicando a fórmula:

**Velocidade de transmissão**

A velocidade de transmissão indica a quantidade de bits transmitidos por segundo, que por sua vez, é proporcional a taxa de modulação (_**Vm**_) e ao número de bits enviados em cada transição do sinal (_**N**_). O número, _**N**_, transmitido depende do número de níveis do sinal. Por exemplo, um sinal com dois níveis contem um bit de informação em cada nível (Nascimento, J. 2000). A seguinte equação relaciona a velocidade de transmissão (_**Vt**_) com a velocidade de modulação:

Onde: _**Vt**_ = velocidade de transmissão, em bits por segundo (bps);

_**Vm**_ = velocidade de modulação, em baud;

_**N**_ = número de bits por cada nível de sinal digital

**Exemplo 2**

Qual a velocidade de transmissão (Vt) que é transmitido 2000 vezes por segundo (2000 baunds), sabendo que em cada nível existe apenas um bit associado?

**Resposta:** Essa é uma transmissão binária como, por exemplo, nível alto igual a 5V correspondente ao bit 1 e nível baixo igual a 1V correspondente ao bit 0. Aplicando a equação de velocidade de transmissão, temos:

ou ou

Por que é importante sabermos quantos bits por níveis existem? A resposta é que os diferentes tipos de modulação (combinada ou não) utilizam mais de um bit por ciclo para aumentar a taxa de transmissão, como veremos abaixo.

### Tipos de Modulação Digital

Agora que já vimos um pouco da teoria associada à análise de sinais, estudaremos os seguintes tipos de modulação:

- **Modulação por Chaveamento de Amplitude ASK:** A modulação ASK (Amplitude Shift Keying), consiste na modificação da portadora através alteração de sua amplitude em função do sinal digital a ser transmitido, conforme Figura 2. As principais características da ASK são:
    - Facilidade de modular e demodular;
    - Pequena largura de banda;
    - Baixa imunidade a ruídos.Devido a baixa imunidade a ruído, a modulação ASK é utilizada somente em aplicações de baixo custo e sem interferências eletromagnéticas, como em:
        - Transmissão de dados via fibras ópticas, já que são imunes a interferências eletromagnéticas;
        - Transmissão de dados por infravermelho, como usados em algumas calculadoras e aparelhos de TV.
        - Controles remotos por radiofrequência, aqueles utilizados para abrir e fechar portões e alarmes de carro.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305452/17758.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305452/17758.png)

Figura 2 - Modulação ASK

- **Modulação por Chaveamento de Frequência FSK:** A modulação por chaveamento de frequência, FSK (_Frequency Shift Keying_), diferentemente da ASK apresenta boa imunidade a ruído. Entretanto, utiliza maior largura de banda dentre todas as modulações chaveadas. A FSK mantem a amplitude da onda durante o processo de transmissão, mas tem a sua frequência alterada pelo sinal digital a ser transmitido (Nascimento, J. 2000), como mostrado na Figura 3. A modulação FSK é utilizada em:
    - Transmissão via modem de baixa velocidade, igual ou menor a 1200 bps;
    - Transmissões via Rádio, como por exemplo, rádio controle;
    - Em telefonia celular para transmissão de controle entre a estação radio base e o telefone celular.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305468/17760.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305468/17760.png)

Figura 3 - Modulação FSK

- **Modulação por Chaveamento de Fase PSK:** A modulação PSK (_Phase Shift Keying_) consiste na alteração da fase da onda portadora em função do sinal digital a ser transmitido. Em outras palavras, ocorrerá, por exemplo, em sua forma mais simples, utiliza apenas duas fases para codificação do sinal: fase 0 grau para transmitir o bit 1 e fase 180 graus para transmitir o bit 0, conforme Figura 4. Portanto, haverá uma mudança de 180 no sinal da onda portadora em relação a onda anterior. A PSK apresenta a melhor imunidade a ruídos dentre as técnicas de modulação e alta velocidade de transmissão quando combinada com codificação multibit, mantendo a mesma largura de banda utilizada pela modulação ASK. Por esses motivos, a PSK é largamente utiliza em modens de média velocidade e rádios digitais (Nascimento, J. 2000).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/5/305516/17761.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/5/305516/17761.png)

Figura 4 - Modulação PSK

- **Modulação de Amplitude em Quadratura QAM:** A QAM (_Quadrature Amplitude Modulation_) combina as modulações ASK e PSK para modular o sinal da portadora, conforme FIgura 5. A QAM é utilizado em modens analógicos e rádios digitais de alta velocidade. Essa técnica apresenta as seguintes características:
    - A amplitude do sinal QAM é variável;
    - Apresenta uma menor taxa de erro;
    - Atinge maior velocidade de modulação, por permitir maior número de bits por baund.
    - A modulação QAM e suas variações são utilizadas em transmissões do tipo ADSL, WIFI e rádios e TVs digitais.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/2/224258/7689.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/2/224258/7689.jpg)

Figura 5 - Modulação QAM

- A modulação QAM é obtida com modulador em quadratura, como mostrado na Figura x, para formar o que é conhecido como **diagrama de constelação QAM**. No 8-QAM codifica 3 bit por símbolo. Isso significa que sua velocidade de transmissão é 2,67 vezes maior do que a de modulação. Por exemplo, se estivemos transmitindo em 8-QAM, um rádio digital de 16 Mbps, precisará modular a uma velocidade de aproximadamente 6,0 Mbauds (16/2,67 ~ 6,0 Mbauds). A Tabela 1 abaixo mostra os diferentes tipos modulação QAM.

|Abreviação|Bits/símbolo|Número de estados|
|---|---|---|
|[[QPSK]]|2|4|
|[[8-QAM]]|3|8|
|[[16-QAM]]|4|16|
|[[64-QAM]]|6|64|
|[[256-QAM]]|8|2|

  
  

Fonte: Benoit, H. 2008.

- **Multiplexação por Divisão de Frequência Ortogonal – OFDM:** A OFDM (Orthogonal Frequency Division Multiplexing) diferentemente das demais utiliza várias portadoras ou subportadoras, conforme Figura 6. Na OFDM são utilizados fluxos paralelos de dados em subportadoras, com modulação QAM ou PSK, proveniente de um fluxo contínuo de dados para atingir altas taxas de transferências de dados, conforme mostrado na Figura. Como característica a OFDM apresenta eficiência espectral, imunidade a interferência e ao desvanecimento (Pinto, E. L, 2002). A OFDM é empregada principalmente em rede wireless e transmissão de TV digital.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/8/0/8066/i02_572.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/8/0/8066/i02_572.jpg)

Figura 6 - Modulação OFDM