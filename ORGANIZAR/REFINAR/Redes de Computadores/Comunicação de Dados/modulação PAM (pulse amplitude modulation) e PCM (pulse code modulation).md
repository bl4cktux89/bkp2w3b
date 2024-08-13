### **Introdução a transmissão digital**

A transmissão de informação em sistemas digitais ocorre através de símbolos. Em contrapartida, a transmissão de informação por meio de sistemas analógicos ocorre a partir da modulação de uma onda portadora pelo sinal que se deseja transmitir. A transmissão analógica ocorre a partir da alteração das características da onda, tais como, amplitude, frequência e fase, e são apropriadas para transmitir informações que já se encontram no formato analógico, como os sinais de áudio ou quando o meio de transmissão não permite o transporte de informação de forma digital. Embora a transmissão de informação possa ser feito de forma analógica, atualmente, um grande número de fontes informação estão no formato digital. Para que os sinais digitais sejam transportados e processados pelos sistemas de transmissão é preciso representa-los através de sinais elétricos. Isso é feito atribuindo valores de tensão para os níveis lógicos 0 e 1, por exemplo, o nível lógico 1 recebe o valor de +V e o nível lógico 0 recebe o valor de tensão –V. Por esse motivo dizemos que a transmissão de informação no formato digital ocorre por meio de símbolos (DEE-UFRN, 2016).

Como já comentado, as informações, muitas vezes, estão no formato analógico, isso não quer dizer que tais sinais não possam ser transmitidos através de sistemas digitais. Na realidade, existem duas vantagens principais em se transmitir informações na forma digital. A primeira delas está associada com o ruído introduzido pelo próprio sistema de transmissão. Quando temos uma transmissão analógica, o receptor analógico trata tanto o ruído quanto o sinal da mesma forma, já que ambos têm a mesma natureza analógica, impedindo que o receptor os diferencie. No caso de sistemas digitais, o receptor consegue distingui o sinal (digital) do ruído, já que o ruído é de natureza analógica. O segundo motivo reside no fato da utilização de técnicas de processamento de digital de sinais por microprocessadores, que permitem que tais sinais sejam manipulados de maneira mais fácil do que em transmissões analógicas (DEE-UFRN, 2016).

A transmissão digital é utilizada em redes locais (LAN) e para interligar centrais telefônicas comutadas, por exemplo. A transmissão digital se alicerça em duas técnicas para transformar sinais analógicos em digitais: Modulação por Amplitude de Pulso -_**PAM (Pulse Amplitude Modulation) e Modulação por código de Pulso (**_Pulse-code modulation), que serão descritas a seguir.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/4/9/14994/i01_963.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/4/9/14994/i01_963.jpg)

Figura 1 - Processo de comunicação

### Amostragem

A amostragem do sinal analógico constitui uma etapa fundamental no processo de conversão analógico-digital. Para entendermos como ocorre o processo de amostragem devemos compreender primeiramente o desenvolvimento matemático elaborado por Harry Nyquist. A teoria de amostragem estabelecida por Harry Nyquis, em 1933, diz que um sinal analógico pode ser reconstituído a partir da retirada de amostras em tempos regulares e igualmente espaçados. Como o sinal analógico possui infinitos valores e muitos deles são redundantes, sendo, portanto, desnecessário transmitir todas as suas componentes (Forouzan, B. A. 2007).

### Digitalização do sinal

O processo de digitalização ou transformação do sinal analógico para digital do sinal ocorre em três fases:

1. **Amostragem:** Consiste em retirar amostras do sinal original a cada T segundos;
2. **Quantização:** consiste em refinar o sinal amostrado, atribuindo valores a cada amostra;
3. **Codificação**: transforma o sinal quantizado em um sinal binário.

**Harry Nyquist** provou que a frequência mínima de amostragem (Fa) deve ser igual a duas vezes a frequência máxima (W) do sinal analógico a ser transmitido: **Fa=2W**

**Exemplo:** No gráfico abaixo são mostrados três sinais com frequências diferentes, F1=250 Hz, F2=750 Hz e F3=1250 Hz, que são amostrados a uma frequência (W) de 1 KHz. Como pode ser observado, a única amostragem bem sucedida que obedece ao teorema de Nyquist é o sinal F1 (250 Hz), já que a frequência de amostragem, de 1 KHz, é igual a 4 vezes a frequência do sinal a ser amostrado. Para F2 e F3, a amostragem não será bem sucedida, tendo em vista que a frequência de amostragem deveria ser de, no mínimo, 1500Hz (Fa= 2xF2 =2x750 = 1500 Hz) para o sinal F2 e de 2500Hz (Fa= 2xF3= 2x1250 = 2500 Hz) para o sinal F3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363168/28981.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363168/28981.png)

Figura 2 - três sinais de frequências diferentes, F1=250Hz, F2=750Hz e F3=1500Hz e a frequência de amostragem é de 1KHz. Apenas F1 terá o sinal amostrado de forma eficiente

Existem diversas técnicas de amostragem do sinal, a mais comum é a Modulação por Amplitude de Pulso -PAM (Pulse Amplitude Modulation). A PAM é definida de forma semelhante a amostragem natural, definida anteriormente. Neste processo, o sinal contendo informação é multiplicado por um trem de pulso periódico e retangular, conforme mostrado na Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363158/28980.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363158/28980.png)

Figura 3 - Técnica PAM aplicada a conversão de um sinal de telefone.

### Quantização

No processo de amostragem mostrado anteriormente na modulação PAM não é possível atribuir valores ao sinal amostrado. Para resolver isso, utilizamos a modulação PCM, que consiste em atribuir “valores arredondados” aos diversos valores amostrados na modulação PAM, atribuindo a cada pulso uma quantidade predefinida de n bits. Por exemplo, se a quantidade de bits utilizada é igual a 8 bits é possível obtermos 256 possíveis valores (de 0 a 255). Agora, pensando que os pulsos PAM são limitados entre 0 e 255 V e não permite valores fracionados, se tivéssemos um pulso com valor igual 99,56 V, esse valor seria arredondado para 99 ou 100, já que não temos bits suficientes para representar o 99,56. O arredondamento para mais ou para menos depende do que é chamado de **nível de precisão** estabelecido durante o projeto (DEE-UFRN, 2016).

**Você poderia estar se perguntando: Como podemos atribuir valores às componentes negativas do sinal?**

**Resposta**: São destinadas 128 posições para representar o sinal negativo e 128 posições para representar o sinal negativo para n=8 bits. Por exemplo, 0V será representado por 128 (decimal) e 255V por 255 (decimal), isso é feito deslocando o 0 V do sinal para 128. Da mesma forma, os sinais negativos compreendidos entre -1 e -128 recebem os valores de 127 e 0, respectivamente. A Figura 4 abaixo mostra com esse ocorre para uma sinal amostrado pela modulação PAM e codificado pela modulação PCM.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363185/29007.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/1/363185/29007.png)

Figura 4 - Codificação PCM.

Fonte: DEE-UFRN. PCM - PULSE CODE MODULATION. Departamento de Engenharia Elétrica - Sistemas de Telecomunicações. Disponível em: http://www.dee.ufrn.br/pcm.pdf

### Codificação

A próxima etapa no processo de conversão analógico-digital é conhecida como codificação. O processo de codificação consiste em decodificar os valores decimais obtidos na codificação PCM em uma sequência de bits, já que serão transmitidos ou armazenados de forma digital, que só permite apenas dois valores, 0 ou 1. Se este processo de codificação não fosse realizado seria necessário implementar um sistema capaz de identificar dezenas ou centenas de níveis diferentes, tornando-o extremamente complexo. Além disso, se transmitíssemos o sinal PAM sem o processo de codificação, as amplitudes do sinal seriam facilmente distorcidas pelo meio de transmissão.

**Exemplo:** Em PCM para telefonia utilizamos 8bits para representar a magnitude do sinal. Neste caso, o eixo das tensões não é deslocado, como mostrado anteriormente, em vez disso, utilizamos, a esquerda da sequência binária, o bit 0 para representar os sinais negativos e o bit 1 para representar os sinais positivos. Os demais 7 bits (2 elevado 7= 128) serão utilizados para representar as magnitudes do sinal, variando de -127 a +127, conforme mostrado na tabela 1.

Tabela 1 - Codificaçao PCM de um sinal de telefonia.

|Title|Valor decimal|Sinal-magnitude|
|---|---|---|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 4\|Untitled 4]]|127|11111111|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 9\|Untitled 9]]|96|11100000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 6\|Untitled 6]]|64|11000000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 3\|Untitled 3]]|32|10100000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 7\|Untitled 7]]|0|10000000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 2\|Untitled 2]]|0|0|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 10\|Untitled 10]]|-32|100000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 8\|Untitled 8]]|-64|1000000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 11\|Untitled 11]]|-96|1100000|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled 5\|Untitled 5]]|-126|1111110|
|[[ORGANIZAR/REFINAR/Redes de Computadores/Comunicação de Dados/modulação PAM (pulse amplitude modulation) e PCM (pulse code modulation)/Untitled Database/Untitled\|Untitled]]|-127|1111111|

  
  

Existem diversas formas de se representar os valores binários em termos de tensão no meio de transmissão. A representação binária em termos de variação de tensão no meio de transmissão é conhecida como **código de linha**. Um código de linha comum utilizando a codificação Manchester é mostrado Na Figura 5. O bit 0 representado por uma transição positiva para negativa, enquanto que o bit 1 é sempre representado por uma transição negativa para positiva.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223962/7645.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223962/7645.jpg)

Figura 5 - Processo de codificação de linha.