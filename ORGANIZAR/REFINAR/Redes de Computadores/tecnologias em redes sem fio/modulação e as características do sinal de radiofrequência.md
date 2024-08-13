### Objetivo:

Nesta aula estudaremos o processo de modulação, que em outras palavras significa acondicionar as informações digitais binárias que estão em baixa frequência a uma onda alternada senoidal de alta frequência.

Comparativamente, temos a onda senoidal alternada de alta frequência como sendo o transporte (como exemplo: um ônibus) e as informações digitais como a carga (como exemplo: os passageiros). Vamos entender como isso funciona...

### 1. Introdução

Conforme descrito por Santos Junior (2005, p. III 3) “ O sinais de radiofrequência são correntes de alta frequência que são conduzidas através dos cabos de cobre e então são irradiadas pelo ar como ondas eletromagnéticas pelas as antenas”.

As ondas de rádio propagam-se, afastando da fonte, em todas as direções. Como analogia, podemos comparar as ondas eletromagnéticas às ondas causadas por uma pedra jogada em um lago, As ondas de água neste caso vão se afastando do local de impacto da pedra em ondas circulares e perdendo sua intensidade.

Os sistemas de rádio também são assim, as ondas eletromagnéticas (EM) vão se afastando da fonte até perder totalmente sua intensidade e não poderem ser mais captadas.

As ondas eletromagnéticas são formadas basicamente por dois sinais: sinal elétrico e sinal magnético. Quando conjugados em uma antena transformam-se em ondas eletromagnéticas, sendo irradiadas após este processo pelo ar. Para que este fenômeno possa acontecer é necessário que nos sistemas eletrônicos de rádio existam dois sinais bem distintos: sinal de informação de baixa frequência, que recebe o nome de sinal modulante e, sinal de alta frequência conhecido como portadora ou sinal de transporte. A junção dos dois produz um terceiro sinal chamado de onda modulada conforme mostrado na figura 1.

**Figura 1 – Processo de Modulação**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296962/16634.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296962/16634.jpg)

Figura 1 - Processo de Modulação

Portanto, a modulação é um processo que pode modificar um ou dois parâmetros de um sinal alternado de alta frequência para que o mesmo possa ser transmitido, levando as informações pelo espaço.

Observe que somente o sinal analógico de alta frequência (portadora) poderá induzir a antena e ser transformado em onda eletromagnética. Portanto, o que o modulador faz é imprimir as características do sinal de informação (de baixa frequência), para que modifique a portadora. A mudança nos parâmetros podem ocorrer na fase, na amplitude e na frequência ou em ambos simultaneamente.

Para a mudança realizada na amplitude dá-se o nome de Amplitude Modulada ou AM; Para a mudança realizada na frequência o nome é Frequência Modulada ou FM e ainda pode-se modificar um sinal de portadora tanto em fase quanto em amplitude ao mesmo tempo, sendo esta última a forma mais utilizada nas transmissões dos rádio wireless Lan.

### 2. Modulação Digital

Conforme retratado, o processo de modulação consiste em modificar um ou dois parâmetros de um sinal analógico, de forma a imprimir informações nestas modificações.

Os parâmetros do sinal que podem ser modificados são: a amplitude, a frequência ou a fase, sendo que atualmente nas transmissões digitais modifica-se tanto a amplitude como a fase simultaneamente. Para ocorrer uma transmissão por ondas eletromagnéticas, utilizam-se dois sinais, o primeiro um sinal elétrico de alta frequência denominado portadora e o próprio sinal elétrico da informação chamado sinal modulante. Ao conjugar estes dois temos um terceiro, que é o sinal modulado e este poderá ser de várias formas, dependendo do processo que foi utilizado para criá-lo.

Nas transmissões de rádio e nos enlaces sempre será utilizado um sinal de portadora analógico de alta frequência e a informação que irá imprimir modificações na portadora poderá ser analógicas ou digitais de baixa frequência.

Para as modulações analógicas, temos as de frequência modulada - FM, de amplitude modulada – AM e a de fase modulada – PM.

Quando as informações a serem transmitidas são de ordem digital temos: _**Amplitude Shift Keying**_ – ASK, _**Frequency Shift Keying**_ – FSK e a _**Phase Shift Keying**_ – PSK e destes matizes resultaram suas combinações na intenção da transmissão de maior número de bit (informações) no mesmo período de tempo t.

A combinação de duas características do sinal analógico (amplitude e _**fase) usados simultaneamente resultou nas modulações BPSK – Modulação Bi Phase Shift Keying**_, onde se consegue a transferência de um bit por um código símbolo por período t.

Quando se aplica mais fases do sinal analógico da portadora como 45º, 135º, 225º e 315º temos quatro estados possíveis de uma única senoide da portadora, sendo possível, neste caso, transportar dois bits por fase escolhida do sinal.

Na mesma sequência, temos então os bits “00” para 45º, “01” para 135º, “11” para 225º e “10” para 315º. Este tipo de modulação recebe o nome de QPSK, ou seja, Modulação por _**Quadrature Phase Shift Keying**_, que tem a capacidade de transportar dois bits a cada símbolo t.

Nesta evolução, por necessidade de transferir mais dados em menor espaço de tempo, foi desenvolvida a modulação que mistura no mesmo período ou senoide a combinação da fase e da amplitude (dois parâmetros do sinal elétrico analógico) no mesmo momento t. (MEDEIROS 2010)

Então surge outro membro da família de modulação digital, a _**Quadrature Amplitude Mudulation**_, ou simplesmente QAM, que é a mistura da modulação ASK com a PSK (amplitude e fase). Em QAM temos 16 (dezesseis) estados possíveis para a portadora e quatro bits por símbolo transmitido, logo isso produz maior taxa de transmissão, chegando a 2Mbps por segundo. A modulação QAM permite a codificação de diversas combinações de bits, como exemplo: 4-QAM, 16-QAM, 32-QAM e 64-QAM.

Para superar a limitação de velocidade que a modulação QAM impôs em 2Mbps, uma nova técnica foi desenvolvida, conhecida como: _**Complementary Code Keying**_, ou simplesmente CCK, que utiliza a modulação QPSK, onde os bits originais são mapeados para um símbolo de dados novos correspondendo a um código. O símbolo de dados conseguidos é então aplicado a várias fases da onda senoidal analógica da portadora e a resultante desta modulação consegue-se taxa de 11Mbps disponibilizada nos rádios do padrão IEEE 802.11b. (SANTOS JUNIOR 2005).

### 3. Relação Sinal/Ruído

Para que um enlace de rádio possa funcionar adequadamente o caminho entre as antenas, (entre o transmissor e receptor), deve chegar com intensidade suficiente para que a mensagem seja compreendida corretamente.

Conforme descrito por Medeiros (2005, p. 89) “o ruído é o inimigo número um das comunicações”, pois, na forma elétrica ou eletromagnética tem comportamentos aleatórios, com amplitudes e fases variáveis e se faz presente em todo o espectro de frequências.

Nos sistemas de rádio enlace o ambiente de tráfego deste sinal entre as antenas não estão imunes às interferências, causando atenuação e perda de potência. Portanto, os rádios, necessitam de alta sensibilidade para distinguir o ruído da informação, pois as interferências podem sobrepor-se às ondas eletromagnéticas e causar prejuízo à recepção do sinal.

A força de uma onda eletromagnética é medida em watts ou numa relação logarítmica da força do sinal dividida por um miliwatt. A esta relação logarítmica chamamos de decibéis acima de 1 miliwatt (dBm). A fórmula a seguir descreve esta relação:

**S/N em (dBm) = 10log (potência do sinal / potência do ruído)**

Uma propriedade comum para descrever a força de um sinal é a relação sinal ruído ou simplesmente sinal S/N. A S/N não descreve a potência absoluta do sinal, mas descreve a relação da potência do sinal comparada à potência do ruído de fundo do ambiente por onde a onda eletromagnética irá passar.

Quando a potência do sinal é muitas vezes maior que a potência do ruído, o ruído adicionado ao sinal da informação não será percebido; porém se o ruído tiver potência muito próxima ao sinal da informação, no sinal demodulado pelo rádio será notadamente percebido esta diferença ao sinal original, causando o que é conhecido por estática. (SANTOS JUNIOR 2005, p. III 37)

### 4. Ganho em Radiofrequência

O ganho é usado para descrever o aumento da potência de um sinal de radiofrequência ou sua amplitude; Este processo poderá ocorrer por duas formas:

1. Por um processo ativo, onde uma fonte de energia externa do tipo amplificador poderá regenerar ou amplificar o sinal dotando-o de maior intensidade.
2. Por um processo passivo, que poderá ocorrer pela combinação do sinal principal a algum refletido onde a onda resultante será um sinal mais forte ou ainda, por um processo passivo de ganho aparente onde é usado um concentrador de sinais para focar numa região de interesse o ganho que seria distribuído para todos os lados. Isso acontece quando se utiliza antenas do tipo direcionais, que tem a propriedade de focar toda a intensidade da onda que poderia propagar-se por 360º em diminutos graus de abertura.

Para se obter o resultado total da irradiação ou EIRP, deve-se somar, a ganho do rádio ao ganho da antena e deduzir da atenuação das linhas de transmissão. A fórmula na sequência ilustra o comentado:

**EIRP (em dB) = (ganho do rádio (dBm) + ganho da antena (dBi)) – atenuação**

### 5. Atenuação em Radiofrequência

A atenuação é conceituada como a perda da intensidade do sinal e pode ocorrer pela resistência existente em um trecho de cabos na linha de transmissão ou quando uma onda é irradiada pelo ar. Os motivos de atenuação podem ser descritos assim:

- Resistência nos cabos, conectores, solda mal feita e o calor aplicado nas linhas de transmissão, todos medidos em dB negativo (- 3,2 dB, por exemplo).
- Nos descasamento de impedância entre conectores, cabos podem causar reflexões do sinal e consequentemente perda na intensidade do mesmo.
- Objetos posicionados diretamente entre as antenas, ou seja, no caminho por onde o sinal de rádio deverá passar.
- Perda pelo sinal trafegado pela atmosfera, que é diferente do vácuo, portanto, causando perdas na intensidade do sinal irradiado conforme o mesmo se afaste da sua antena.

As atenuações são importantes ao estudo das transmissões digitais via rádio, pois sem a devida atenção, os sistemas poderão funcionar com instabilidade ou não funcionar adequadamente, degradando muito o sinal e a taxa de transferência da informação. (MEDEIROS 2010)

Como exemplo de cálculo de um sistema pode observar a figura 2 onde tem-se um esquema de ligação de um rádio com antena e sua linha de atenuação. A pergunta é, qual será a potência efetiva transmitida pela antena?

**Figura 2 – Esquema de um transmissor**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296965/16636.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/9/296965/16636.jpg)

Figura 2 - Esquema de um transmissor

O processo para calcular o EIRP total, ou seja, o valor da potência que irá sair pela antena deve-se iniciar transformando o valor do rádio (que está em mW) para dB.

**dBm do rádio = 10log (ganho do rádio em mW)**

**dBm do rádio = 10log (120)**

**Ganho do rádio = 20,79dBm**

De posse do valor em dB da potência do rádio, pode-se calcular a potência EIRP na saída da antena pela equação a seguir:

**EIRP (em dB) = (ganho do rádio (dBm) + ganho da antena (dBi)) – atenuação**

**EIRP (em dB) = (20,79 + 9) – 4,28**

**EIRP = 25,51dB**

Portanto, a potência total irradiada EIRP pela antena é de 25,51dB.

### Revisão:

- O processo de modulação consiste em modificar um ou dois parâmetros de um sinal analógico, de forma a imprimir informações nestas modificações.
- Na modulação digital temos a informação de baixa frequência, que sendo digital que recebe o nome de sinal MODULANTE e o transporte formado pela onda analógica senoidal de alta frequência que recebe o nome de portadora.
- Na junção destes dois sinais temos um terceiro denominado sinal MODULADO, que será encaminhado à antena pela linha de transmissão e transformado em ondas eletromagnéticas pela antena que por sua vez, irradiará o mesmo no espaço.
- A onda lançada no espaço tem sua potência de irradiação denominada EIRP, que significa Potência Real Isotrópica Irradiada