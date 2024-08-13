### **Introdução à codificação**

Em determinadas aplicações como em redes de computadores, transmissões via interface USB e também nos barramentos internos dos computadores, a transmissão de sinais digitais podem ser enviados diretamente em banda base, ou seja, toda a capacidade do canal é utilizada para transmitir dados sem uso de multiplexação. Para representar o sinal digital em pares de condutores é necessário variar de forma discreta a tensão (volts) com valor fixo para cada nível lógico binário, 0 ou 1, conforme Figura 1. O padrão de tensão (volts) e período (tempo) utilizado para representar no meio de transmissão os sinais digitais dos diferentes níveis lógicos é chamado de **código de linha** (Forouzan, B. A. 2007).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223942/7640.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223942/7640.jpg)

Figura 1 - Codificação de linha.

Existem diferentes códigos de linha que são projetados com o objetivo de otimizar a utilização do meio de transmissão e a recepção do sinal. No projeto e escolha de um código de linha, as seguintes características devem ser levadas em consideração:

- O tipo de meio de comunicação a ser utilizado, por exemplo, fibras ópticas e cabos metálicos. As variáveis como: capacitância, interferência e atenuação possuem comportamento diferente em cada meio de transmissão;
- A média do sinal a ser transmitido deve ser iguala zero. Essa média é conhecida com componente DC (componente contínua) e não é possível ser transmitida em longas distâncias, além disso, a componente DC ocasiona uma perturbação nas características elétricas do sinal a ser transmitido, o que pode levar a uma maior probabilidade de erro de bit na recepção do sinal;
- A codificação de linha deve proporcionar o sincronismo do receptor com o objetivo de diferenciar o sinal recebido do sinal transmitido. Se o sincronismo não for adequado, a decodificação do sinal será prejudicada o que levará ao aumento da probabilidade de erro de bits recebidos;
- Deve-se, de preferência, escolher um código de linha que possibilite a correção de erros de bit.

### Classificação da codificação de linha

A codificação de linha é classificada em: unipolar, polar, bipolar, multinível e multilinha (Bezerra, R. M. 2008):

- Unipolar: Neste tipo de codificação utiliza apenas um nível de tensão é utilizado para representar os níveis lógicos. Essa codificação não elimina a componente DC do sinal, além de não possuir um bom sincronismo quando existem cadeias longas de bits;
- Polar: Na polar é utilizado dois níveis de tensão (positivo e negativo) para representar os níveis lógicos. Alguns tipos codificação Polar, como a NRZ-L, possuem componentes DC para longas cadeias de bits. Além disso, o sincronismo pode ser de difícil restabelecimento caso o perca;
- Bipolar: Utiliza três níveis de tensão (zero, positivo e negativo). Elimina o problema da componente DC, mas ainda apresenta problemas de sincronismo para cadeias longas de bits;
- Multinível: Representa dois ou mais bits através de um único nível de tensão. Com essa técnica aumenta-se a taxa de dados, em bps, mantendo ou até diminuindo a largura de banda (em Hz) utilizada.

Abaixo serão descritas as principais codificações de linha de acordo com a classificação acima:

**Unipolar**

- NRZ – (Non-return to zero – Não retorna ao nível): O NRZ tradicionalmente é considerado um esquema unipolar, desenvolvido como um método NRZ (sem retorno ao zero), não retornando a zero no meio do tempo de bit (Figura 2). O bit 1 é representado por uma voltagem positiva e o bit 0 pela voltagem zero. Esse método é muito caro e não é utilizado atualmente

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223943/7642.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223943/7642.jpg)

Figura 2 - Codificação NRZ unipolar

**Esquemas Polares**

- NRZ-L – (Non-return to zero level – Não retorna ao nível zero): A NRZ-L representa os níveis lógicos 1 e 0 por uma voltagem positiva e negativa, respectivamente, não tendo o nível zero de tensão, conforme Figura 3. Atualmente, não muito utilizado devido a problemas autosincronização de da presença da componente DC. A norma RS-232 estabelece o NRZ-L como padrão de codificação de interfaces seriais de switch com velocidade 115 Kbps.
- NRZ-I - (Non-return to zero inverted – Não retorna ao nível zero invertido): No NRZ-I, o bit zero continua sendo representado pela tensão negativa, entretanto, o bit 1 é representado por transições, de positiva para negativa ou de negativa para positiva (Figura 3). Para resolver o problema com longas cadeias de 0 é introduzido um bit 1 após 4 bits zeros. Problemas associados autosincronização e componente DC permanecem.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223944/7643.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223944/7643.jpg)

Figura 3 - Codificação NRZ-L e NRZ-I

- **RZ – (Return to zero – Retorna a zero):** O principal problema das codificações anteriores está associado com a falta de sincronismo do clock entre o receptor e transmissor. Para resolver esse problema foi desenvolvido o esquema RZ, que usa três níveis de tensão, positivo, negativo e zero. No RZ muda durante o bit e não entre os bits: o bit 1 é representado por uma transição de positivo para zero, enquanto que o bit 0 é representado por uma transição de negativo para zero, conforme Figura 4.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223950/7644.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223950/7644.jpg)

Figura 4 - Codificação NZ

- **Manchester:** Na codificação Manchester mostrado na Figura 5 ocorre sempre uma transição no meio do tempo de bit para garantir o sincronismo: o bit 1 é representado por uma transição de negativa para positiva no meio do tempo do bit, enquanto que o bit 0 zero é representado por uma transição de positiva para negativa. O esquema Manchester é utilizado em redes Ethernet do tipo 10Base-T

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223962/7645.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223962/7645.jpg)

Figura 5 - Codificação Manchester.

- **Manchester Diferencial:** As transições entre polos são determinadas no início do tempo de bit: se o próximo bit for igual a 1 não ocorre transição na primeira metade do tempo de bit em relação ao bit anterior, enquanto que o bit 0 é representado por uma transição no inicio do tempo de bit, conforme Figura 6. Ambos os métodos Manchester resolvem o problema de componentes DC com a transição no meio do tempo de bit, mas para isso necessita de mais largura de banda. Tal esquema é utilizado em redes Token Ring e também em armazenamento óptico e magnético.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223986/7646.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223986/7646.jpg)

Figura 6 - Codificação Manchester Diferencial

**Esquemas Bipolares**

- **AMI – (Alternate Mark Inversion – Inversão de marca alternada):** O termo _marca_ está associado a telegrafia e significa 1. Isso significa que o bit 1 pode ser representado tanto por uma tensão positiva quanto negativa, ou seja, se tivermos uma sequência de dois bits 1s o primeiro pode ser positivo, mas o segundo obrigatória ser negativo. O bit 0 é representado por zero volts de tensão (Figura 7). Existe também a AMI **pseudoternária**, onde o bit 1 é representado por zero volts e o bit 0 é alternado entre tensões positivas e negativas. O esquema AMI é utilizado principalmente em transmissões de longas distâncias.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224023/7648.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224023/7648.jpg)

Figura 7 - Codificação AMI.

**Esquemas Multiníveis**

- **2B1Q - (dois binários e um quaternário):** Representa dois bits simultâneos por meio de um sinal de quatro níveis de tensão, por isso é chamado de dois binários e um quaternário. Neste esquema temos m=2 elementos de dados, por n=1 elementos de sinal para L=4 níveis de tensão, como mostrado na Figura 8. O 2B1Q é utilizado pela tecnologia de acesso via banda larga conhecida como DSL (Digital Subscriber Line - Linha digital do assinante).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224030/7651.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224030/7651.jpg)

Figura 8 - Codificação 2B1Q

- **8B6T – (oito binários e seis ternários):** Neste padrão podemos ter 256 combinações de binários (2 elevado 8) e 478 (3 elevado a 6) padrões de sinal diferentes. Existem, por exemplo, 222 (478-256) elementos de sinal redundante que permitem o sincronismo e detecção de erro. Este tipo de codificação é utilizada pelas redes 100Base-T4. Na Figura 9 é mostrado um exemplo da codificação 8B6T.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/2/357258/29361.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/2/357258/29361.png)

Figura 9 - Codificação 8B6T

- **4D-PAM5 – (Modulação de Amplitude de Pulso com 5 Níveis e 4 Dimensões).** O 4D significa que ele usa 4 fios simultaneamente, com cinco níveis de voltagem (-2, -1, 0, 1 e 2). Podemos assumir que o 4D-PAM5 utiliza uma codificação similar ao método 8B4Q. Dessa forma, 8 bits podem ser representados por quatro níveis de sinal (Figura 10) e o nível zero é utilizado para detecção de erro. Redes do tipo 1 Gigabit utilizam essa codificação, transmitindo nos quatro pares simultaneamente (Diane B., 2005).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/2/357262/29362.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/2/357262/29362.png)

Figura 10 - Codificação 4D-PAM5.

**Esquema Multilinha**

- **MLT-3 – (Multi-Level Transmit – Transmissão multilinha de três níveis):** Tem por característica utiliza menos largura de banda e emitir menos interferência eletromagnética, principalmente, quando a aplicação opera em alta frequência (acima de 32 MHz) Utiliza três níveis de voltagem (-V, 0V e +V) e três regras de transição para representar cada bit no meio de transmissão, conforme Figura 11:

1. Se o próximo bit a ser representado for 0, não haverá transição de nível;  
2.  
Se o próximo bit for 1 e o nível de tensão atual não 0, o próximo nível de tensão será 0;  
3.  
Se o próximo bit for 1 e o nível atual de tensão for 0, o nível de tensão seguinte será oposto do último nível não-zero.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224024/7650.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224024/7650.jpg)

Figura 11 - Codificação MLT-3

### Codificação de Blocos

A codificação de blocos visa melhorar o desempenho da codificação de linha através da redundância para garantir o sincronismo. A codificação de bloco muda um bloco de m bits para um bloco de n bits, sendo n maior que m, e por isso, é conhecida como codificação mB/nB (Forouzan, B. A. 2007). Neste método são utilizadas três etapas para codificação a sequência binária e ilustradas na Figura 12:

1. Primeira etapa - Divisão: Nesta etapa a sequência de bits da informação é dividida em uma sequência de m bits como, por exemplo, a codificação 4B/5B divide a sequência original em grupos de 4 bits;
2. Segunda – Substituição: Após a divisão em grupos de m bits, a sequência de m bits é substituída por uma sequência de n bits. Por exemplo, na codificação 4B/5B, o grupo de 4 bits é substituído por um grupo de 4 bits. Para garantir o sincronismo não é permitido nessa codificação que grupos de três bits 0s ou 1s sejam transmitidos de forma sequencial. Ao acrescentar mais um 1 bit é possível também resolver o problema de detecção de erro.
3. Terceira etapa – Codificação de linha: Após a substituição é utilizado algum esquema de codificação de linha simples descrito anteriormente como, por exemplo, Manchester. A codificação de linha a ser utilizada não precisa ser complexa, já que a complexidade está justamente na substituição do código em blocos. Apesar dessa vantagem, a utilização da codificação de bloco necessita de maior largura de banda devido a introdução de um bit adicional.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/3/361306/29363.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/3/361306/29363.png)

Figura 12 - Codificação de bloco 4B/5B

Abaixo a codificação em bloco 4B/5B será descrita em detalhes, assim como a codificação em bloco 8B/10B

- **4B/5B** **(Quatro binário, cinco binário):** Este código de bloco foi desenvolvido para ser utilizado em conjunto com a codificação NRZ-I, que apresenta baixa largura de banda, mas tem problema de autosincronização. Com vista a corrigir esse problema do NRZ-I, a arquitetura 4B/5B evita que uma grande sequência de 0s seja transmitida através da alteração do fluxo de bits. Isso quer dizer, que no 4B/5B não existe a possibilidade de ter uma sequência de mais de três 0s consecutivos. Para tanto, a saída de 5 bits que substitui a entrada de 4 bits não possuí mais de um bit 0 significativo, a esquerda, e não mais de dois 0s a direita, conforme tabela 1. Apesar disso a componente DC não é eliminada.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/1/224173/7652.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/1/224173/7652.jpg)

Tabela 1 - Mapeamento 4B/5B

- **8B/10B – (oito binário, dez binário):** A entrada de oito bits de dados é substituída por uma saída de dez bits de dados, de forma semelhante ao 4B/5B. Ela é na verdade uma combinação da codificação 5B/6B e da 3B/4B, conforme mostrado na Figura 13. Neste esquema, os 5 bits mais significativos de um grupo de 8 são injetados num codificador 5B/6B e os 3 bits menos significativos são injetados no codificador 3B/4B. Essa técnica geralmente é melhor do que a 4B/5B por apresentar uma melhor detecção de erro e sincronismo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/3/361311/29364.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/1/3/361311/29364.png)

Figura 13 - codificação 8B/10B que combina a codificação 5B/6B e 3B/4B

O resumo da aula é descrito na Tabela 2, mostrando os tipos de codificações, características e aplicações.

![[Screenshot_from_2021-12-02_22-41-42.png]]