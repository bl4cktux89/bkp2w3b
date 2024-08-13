### Multiplexação

Mesmo com o aumento da largura de banda dos meios de comunicações, existe ainda a necessidade de se utilizar de maneira eficiente tais meios de comunicação. O processo de multiplexação visa, justamente, aproveitar de maneira eficiente a largura de banda total de um link por meio de técnicas que permitem a transmissão simultânea de vários sinais por meio do mesmo meio de transmissão. Dessa forma, a capacidade do meio de transmissão que não é utilizada pode ser compartilhada por vários canais. Um **canal** pode ser entendido como parte de um link que transporta um sinal entre origem e destino e o **link** corresponde ao meio de transmissão propriamente dito. Dessa forma, em um link pode existir (n) canais (Forouzan, A. B, 2007), como mostrado na Figura 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/2/224250/7688.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/2/224250/7688.jpg)

Figura 1 - Processo de multiplexação.

Podemos utilizar a analogia de uma autoestrada mostrado na Figura 2 para explicar o processo de modulação. Cada carro (canal) corresponde a um tipo de sinal que trafega pela autoestrada (link).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/9/363921/27219.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/9/363921/27219.png)

Figura 2 - Analogia entre a autoestrada e o processo de modulação

**Categorias de Multiplexação**

Os diferentes métodos de multiplexação podem ser divididos em:

- **Multiplexação por divisão de frequência** (**FDM**), do inglês _Frequency Division Multiplexing;_
- **Multiplexação por divisão de comprimento de onda** (**WDM**), do inglês _Wavelenght Division Multiplexing_, e;
- **Multiplexação por divisão tempo** (TDM), do Inglês _Time Division Multiplexing_.

A multiplexação por FDM e WDM são métodos utilizados quando a transmissão é do tipo analógica, enquanto que a técnica TDM é utilizada em transmissões digitais. Abaixo são descritas em detalhes cada um desses métodos.

### Multiplexação por Divisão de Frequência (FDM)

A técnica analógica FDM combina a largura de banda individual de um conjunto de sinais para transmissão em um link de largura de banda (em Hertz). Segundo Forouzan (2007, v.4, p. 162), "no FDM, os sinais gerados pelo dispositivo emissor vão modular frequências de portadoras diferentes dentro do multiplexador. Esses sinais modulados são transmitidos em um único sinal composto e transmitidos através do link", como mostrado na Figura 3. É importante salientar, que os sinais são separados por faixas não utilizadas, chamadas de **bandas de proteção**, para evitar a sobreposição dos diferentes canais. No destino, um conjunto de filtros são utilizados para separar as componentes individuais através do demultiplexador. Esse processo é mostrado na Figura 3.

Cabe acrescentar que apesar de considerarmos o FDM uma técnica analógica, podemos converter um sinal digital em analógico e depois empregar a técnica FDM para multiplexa-lo no link.O FDM é utilizado pelas operadoras de telefonia para combinar os sinais de voz, também pode ser utilizada por rádios AM e FM analógicos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/8/3/238391/9221.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/8/3/238391/9221.jpg)

Figura 3 - Sinais individuais (a) e (b) são combinados no mesmo canal (c)

**EXEMPLO 1**

Supondo que três canais de uma transmissão qualquer ocupem individualmente 4KHz.Supondo que não exista bandas de proteção. Qual a largura de banda mínima para acomodar esses três canais?

**Resposta:** Neste caso, basta multiplicarmos a quantidade de canais pela frequência: 3 x 4KHz, totalizados 12KHz. Podemos, portanto, utilizar a largura de banda de 60 a 72KHz de um link para acomodar este sinal, como mostrado na Figura 3.(c).

**EXEMPLO 2**

Quatro canais, com largura individual de 20 KHz devem ser transmitidos por meio da multiplexação FDM. Qual deve ser a largura mínima total para essa transmissão, sabendo que a banda de proteção é de 2 KHz?

**Resposta**: Para quatro canais, precisamos de, pelo menos, três bandas de proteção. Dessa forma a largura de banda total deve ser de no mínimo de 4 x 20 + 3 x 2 = 86 KHz.

### Multiplexação por divisão de comprimento de onda (WDM)

A Multiplexação por divisão de comprimento de onda (WDM), como o próprio nome já diz, permite multiplexar em um único link diferentes comprimentos de onda, ou seja, multiplexar diferentes canais ou frequência, já a frequência é dependente do comprimento de onda (f=C/λ). Conceitualmente a multiplexação por WDM é semelhante a FDM, entretanto, em um sistema WDM utilizamos multiplexadores e demultiplexadores de sinais ópticos de alta frequência. Na Figura 4 mostramos WDM (Entrada) que tem a função multiplexar sinais luminosos com diferentes comprimentos de onda (frequência).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/5/6/5674/i05_536.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/5/6/5674/i05_536.jpg)

Figura 4 - Multiplexador por divisão de onda (WDM)

A ideia básica de funcionamento de um WDM pode ser entendida por meio de prismas (Figura 5), que tem a capacidade de combinar vários canais de luz   na entrada (Multiplexador) acoplado a uma fibra óptica (Link) e um prisma na saída (demultiplexador) faz o processo inverso.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/9/363935/27242.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/9/363935/27242.png)

Figura 5 - Processo de multiplexação por divisão de comprimento de onda utilizando um prisma.

Fonte: Forouzan, Behrouz A. Comunicação de Dados e Redes de Computadores. 4ª Edição. MCGraw-Hill, 2007.

Utilizamos WDM principalmente em redes de alta velocidade e de alta taxa de transferência de dados, como por exemplo redes ópticas metropolitanas e transmissões intercontinentais. As primeiras redes ópticas que utilizam WDM tinham a capacidade de combinar apenas dois canais por fibra óptica. Atualmente, os sistemas conhecidos com DWDM (Multiplexação por divisão de comprimento de onda denso) podem atingir até 200 canais, de 10, 40 e 100 Gbps por canal, agregando em um único par de fibras ópticas até 20 Tbps (Padtec, 2016).

### Multiplexação por divisão tempo (TDM)

A técnica TDM permite aproveitar a largura de banda do link compartilhando o tempo em vez de parte da largura de banda, como visto anteriormente no FDM. Na Figura 5 é mostrado três canais de entrada compartilhando o slot de tempo reservado para cada canal após passar por um MUX. Observa-se que cada canal utiliza a banda disponível de forma sequencial, primeiro o canal 1, na sequencia o canal 2 e por último, o canal 3; a sequência se repete após o slot de tempo reservado para o canal 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/5/6/5675/i06_536.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/5/6/5675/i06_536.jpg)

Figura 6 - Processo de alocação do tempo na técnica TDM

Existem dois tipos de multiplexação TDM: Síncrono e estático.  No **TDM síncrono**, o sincronismo é estabelecido por um relógio. Como mostrado na Figura 7, o ponteiro do relógio tem que passar por cada um dos canais (Sempre no sentido de A para D) para transportar para multiplexa-lo no meio de transmissão. A desvantagem dessa técnica é que o ponteiro pode estar em um canal de entrada que não possui dado a ser transmitido, como mostrado em A1, D1 e A2, levando ao desperdício da banda. Na transmissão **TDM Assíncrona** é necessário utilizar um cabeçalho que identifique cada uma das mensagens que estão sendo transmitidas, além disso, nesse método, a transmissão da mensagem ocorre imediatamente após detectar que o meio de transmissão está disponível, evitando dessa forma que a banda seja desperdiçada (Figura 8).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/9/0/229092/7692.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/9/0/229092/7692.jpg)

Figura 7 - TDM síncrono

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/9/4/229440/7693.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/9/4/229440/7693.jpg)

Figura 8 - TDM assíncrono