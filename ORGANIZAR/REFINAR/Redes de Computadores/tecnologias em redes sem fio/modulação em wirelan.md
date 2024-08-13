### Objetivo:

Neste tópico iremos juntos fazer um mergulho mais apurado e entender como é feito o processo da modulação. Vamos entender realmente o que significa esta palavra e quais são as tecnologias existentes nos rádios wireless da atualidade.

### INTRODUÇÃO

O processo de modulação consiste em modificar um ou dois parâmetros do sinal elétrico alternado de alta frequência com a finalidade deste poder transportar uma informação. Esta modificação que é realizada no sinal elétrico é chamada de símbolo, e símbolo representa uma informação qualquer.

Somente os sinais elétricos senoidais de alta frequência serão capazes de induzir as antenas e serem transformados em ondas eletromagnéticas a fim de ganhar o espaço. Portanto é necessário que a informação que se deseja transportar imprima modificações neste sinal senoidal para que possa ser representada como um símbolo ou basicamente uma ilustração da informação que se deseja transmitir. Parece bem confuso de se entender, mas podemos exemplificar da seguinte forma ilustrativa:

Imaginemos que um aluno de nome Joãozinho seja nosso sinal elétrico de alta frequência denominado portadora e a informação que Joãozinho tem de transportar a sua classe diz respeito ao seu estado de espírito no dia.

Imaginemos que a mãe de Joãozinho combinou previamente com sua professora que se ele estiver usando uma camiseta vermelha significa que está de mau humor, se estiver usando uma camiseta de cor verde significa que ele está de bom humor. Logo Joãozinho nem precisa dizer nada, basta sua professora observar a cor da sua camiseta que saberá como tratá-lo naquele dia respectivo.

Observe que a camiseta tornou-se um “símbolo” do humor de Joãozinho, ela agora transporta uma informação que diz respeito ao humor do referido aluno.

No caso da modulação é exatamente a mesma coisa que acontece. A informação que pode ser de dados, voz ou vídeo irá modificar ou imprimir certas modificações no sinal senoidal a fim de que o mesmo possa transportar algum tipo de informação. Se tanto o transmissor quanto o receptor montarem simultaneamente um código de transformação poderão a partir desse se comunicar sem problema algum.

Modificar alguns dos parâmetros fundamentais do sinal elétrico senoidal de alta frequência significa alterar a amplitude, a frequência ou a fase e até mesmo modificar dois parâmetros em conjunto, como a fase e a amplitude.

Conforme relatado por Santos Junior (2005), uma onda modulada é composta da mescla de duas ondas distintas: uma é o sinal de alta frequência chamado de onda portadora, que sofreu modificações causados por outra onda, que no caso é um sinal de informação denominada sinal modulante.

Quando a informação modifica os parâmetros da onda portadora, esta então é transformada em sinal modulado, ou seja, sinal modificado que carrega algum tipo de informação. Quando temos a portadora e a informação analógicas, temos dois tipos de modulação que podem ser: Amplitude Modulada – AM ou por Frequência Modulada – FM. Quando se tem a portadora analógica e a informação digital temos três novos tipos de modulação:

- ASK – _Amplitude Shift Keying_ – Modulação por Deslocamento de Amplitude.
- FSK – _Frequency Shift Keying_ – Modulação por Deslocamento de Frequência.
- PSK – _Pulse Shift Keying_ – Modulação por Deslocamento de Fase.

Nos rádios wireless LAN é usado a modulação digital em uma portadora analógica, portanto, vamos conhecer a seguir as modulações do tipo ASK, FSK, PSK, QPSK e QAM.

### Modulação - ASK – _Amplitude Shift Keying_

Na modulação ASK a amplitude do sinal muda em resposta ao sinal da informação: Para as alternâncias de bit 1 temos uma reprodução fiel da portadora e para as alternâncias de bit 0 não temos transmissão da portadora conforme ilustrado na figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305452/17758.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305452/17758.png)

Figura 1 - Modulação ASK

### Modulação - FSK – _Frequency Shift Keying_

Na modulação FSK muda-se a frequência em resposta as variações do estado lógico do sinal modulante. Para sinal de informação de bit 0 a frequência da portadora continuará a mesma, para alternâncias do sinal modulante para bit 1 ocorrerá um pequeno aumento na frequência da portadora conforme ilustrado na figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305468/17760.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/4/305468/17760.png)

Figura 2 - Modulação FSK

### Modulação - PSK – _Phase Shift Keying_

A modulação por fase é a técnica de modulação escolhida para a utilização nos rádios wireless pela sua eficiência na conversão dos sinais digitais. Nesta modulação a técnica é modificar a fase da portadora senoidal para indicar uma mudança de estado do sinal de informação modulante: Para as alternâncias de estado do sinal modulante de informação de bit 1, a portadora é transmitida regularmente sem modificação de amplitude, frequência ou fase, porém, para as alternâncias de bit 0 para o sinal de informação, a fase é desviada em 180º. O desvio de fase representa a mudança de estado lógico do sinal de informação, conforme ilustrado na figura 3:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/5/305516/17761.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/5/305516/17761.png)

Figura 3 - Modulação PSK

### Modulação - QPSK – Modulação _Quadrature Phase Shift Keying_

Neste tipo de modulação faz-se uso da modulação PSK, ou seja, da modulação por fase e da modulação ASK, modulação por amplitude, para que se possa conseguir a transmissão de um número maior de símbolos no mesmo período senoidal da portadora. Esta modulação é a QPSK conforme descrito.

O termo quadratura significa que a portadora pode ter quatro fases em um dado instante separadas de 90º cada uma. Cada fase então se consegue carregar dois bits aumentando muito a eficiência da transmissão com a diminuição da banda necessária.

Na modulação QPSK tem-se o símbolo S1 com um desvio de fase de 45º e com a transmissão dos bits 0 e 0. No símbolo S2 com deslocamento de fase de 135º temos a transmissão dos bits 0 e 1. Com o símbolo S3 o deslocamento agora é de 225º e temos o transporte dos bits 1 e 1 e finalmente com o símbolo S4 e um deslocamento de fase de 315º chega-se ao transporte dos bits 1 e 0.

Como sabemos, o sinal analógico tem 360º disponíveis, portanto utilizando um número maior de graus consegue-se enviar maior quantidade de símbolos e consequentemente mais bits no mesmo período senoidal da portadora ou espaço de tempo. (MEDEIROS, 2010)

### Modulação – QAM – _Quadrature Amplitude Modulation_

O QAM é a combinação de modulação por amplitude e modulação por fase simultaneamente. Em QAM é possível ter 16 estados possíveis para a portadora, tendo quatro bits por símbolo que são enviados em cada momento t.

Existem modulações QAM para combinações de diversos bits como exemplo: 4-QAM, 16-QAM, 32-QAM e 64-QAM.

Em QAM temos o deslocamento das fases representando combinações de bits com a associação da amplitude, então temos um grupo de fases maior com um número maior de bits e este número dobra quando diminuímos a amplitude a um segundo nível, conforme ilustrado na figura 4.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/5/305513/17764.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/5/5/305513/17764.png)

Figura 4 - Modulação QAM

### Modulação – CCK – _Modulação Complementary Code Keying_

O CCK é uma codificação da modulação QPSK, onde os bits originais gerados por esta modulação são mapeados para um novo símbolo de dados correspondente. Então este novo símbolo de dados é aplicado a várias fases da onda portadora analógica, como se fosse uma modulação por deslocamento de fase. A onda resultante é similar a modulação de 2Mbps que é gerado no QPSK original, porém, a taxa agora conseguida é de 11Mbps, muito maior que seu antecessor.

O CCK usa complexas funções conhecidas como _**Complementary Codes**_ para enviar dados adicionais na forma de onda original que comporta 6 bits, o CCK carrega mais 2 bits formatando o símbolo agora com 8 bits, o que aumenta consideravelmente a taxa de transmissão.

Outra vantagem do CCK sobre outras técnicas de modulação é que ela é menos suscetível a interferências por múltiplas vias do que os sistemas baseados puramente em QPSK. (NASCIMENTO, 1992)

### Revisão:

1. Modulação é o processo de modificar um ou dois parâmetros do sinal analógico de forma senoidal de alta frequência a fim de imprimir nestes símbolos que representarão o sinal de informação original.
2. O sinal analógico de alta frequência é designado sinal de portadora.
3. O sinal de informação é designado sinal modulante.
4. A atuação do sinal de informação (modulante) no sinal de alta frequência (portadora) irá gerar um terceiro sinal designado como sinal modulado.
5. Este sinal modulado será encaminhado à antena e será transformado em onda eletromagnética pela antena que será irradiado no espaço.