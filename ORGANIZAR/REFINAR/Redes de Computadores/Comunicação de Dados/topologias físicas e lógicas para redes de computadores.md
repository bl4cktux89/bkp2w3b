[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/7/2/307287/18430.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/7/2/307287/18430.png)

### **Introdução**

A topologia de uma rede está associada com a forma como os dispositivos de uma rede estão interconectados em termos lógicos e físicos (TANNENBAUM, 2011). Podemos, portanto, classifica-la em:

- Topologia Lógica
- Topologia Física

A Topologia Física corresponde à disposição de computadores e/ou equipamentos de rede, mostrando como os dispositivos estão conectados através dos meios físico (layout da rede). Por outro lado, a topologia Lógica consiste no método de acesso ao meio de transmissão e como os dados são transportados de um dispositivo de origem até um dispositivo de destino.

### **Topologias Físicas**

Existem diversas formas de se interligar fisicamente os dispositivos de uma rede, tais como:

- Topologia em barramento;
- Topologia em estrela;
- Topologia em Anel;
- Topologia Hierárquica;
- Topologia Mista ou Hibrida;
- Topologia em Malha ou Mesh.

**Barramento**

A topologia em barramento consiste de ligar todos os dispositivos da rede a uma única “barra” ou meio de transmissão, neste caso, cabo coaxial. Este tipo de topologia entrou em desuso em virtude do baixo desempenho quando o tráfego da rede é elevado, já que todos os dispositivos compartilham e disputam o mesmo meio de transmissão.

**Funcionamento:** Nesse tipo de rede apenas um dispositivo pode enviar por vez. Quando uma máquina deseja enviar dados na rede, ela deve “escutar” o meio de transmissão, caso ele esteja liberado, os dados são transmitidos da origem para o destino, e nesse instante, nenhum outro dispositivo pode transmitir na rede.  Outra característica dessa topologia, é que os dados são enviados em broadcast, ou seja, todos os computadores da rede recebem esses dados, mas apenas do destinatário poderá receber os dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264102/13402.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264102/13402.png)

Topologia em barramento

**Topologia em estrela**

A topologia em estrela utiliza um dispositivo central conhecido como concentrador, normalmente um HUB ou switch (também conhecido como comutador), e por meio de cabos par-trançados ou fibra óptica, os computadores da rede são conectados (KUROSE,2014). Essa topologia é a mais utilizada, tendo em vista que o dispositivo concentrador controla o envio de dados da origem ao destino, permitindo, dessa forma, que qualquer computador da rede possa enviar dados quando necessário.

A grande vantagem deste tipo de topologia é que se um nó ou cabo falharem, a rede continua em funcionamento. Além disso, o dispositivo centralizador é que estabelecer qual será a velocidade da rede. Por outro lado, a desvantagem está justamente no dispositivo central, já que, caso ele fique inoperante, a rede como um todo não funcionará.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264110/13403.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264110/13403.png)

**Topologia em Anel**

Na rede em Anel os dispositivos da rede são interligados através de um caminho fechado em série. Quando os dados são enviados em uma rede em Anel, eles passam por cada nó, funcionado como repetidores até que o nó de destino ou origem retire-o da rede. Normalmente esse tipo de rede é unidirecional, ou seja, os dados fluem sempre em uma única direção, mas em alguns casos, dependendo do protocolo, ela pode funcionar de forma bidirecional, proporcionado redundância na rede caso uma direção de envio apresente falha.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264100/13400.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264100/13400.png)

**Topologia Hierárquica**

Uma topologia Hierárquica pode ser entendida como uma coleção de redes em estrela ordenada de forma hierárquica. Os nós ou folha dessa árvore, se conectam ao tronco por meio de dispositivos intermediários (galhos). Atualmente, o conceito de hierarquia é bastante empregado em redes, no que é conhecido como Modelo Hierárquico de Rede, que consiste na divisão de uma rede em três camadas, são elas:

- Camada de Acesso: Conecta os dispositivos finais, tais como computadores, tablets, telefones, celulares conectados por meio de switches e pontos de acesso.
- Camada de Distribuição: Faz a conexão entre a camada de acesso e o núcleo da rede. Normalmente é composta por switches de alto desempenho que segmentam o tráfego de rede, criando sub-redes separadas.
- Camada Núcleo: Formada por equipamentos robustos de alto desempenho que proporciona a conectividade entre as camadas de Distribuição. Tais dispositivos como, por exemplo, roteadores ou switches, devem ser capazes de manipular grande quantidade de dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/3/7/343777/26692.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/3/7/343777/26692.jpg)

Camadas de núcleo, distribuição e acesso em uma topologia hierárquica.

Fonte: http://4.bp.blogspot.com/-ei1fJr_V5Ps/TqxFXbrL_qI/AAAAAAAAAfg/cpLRhQwzKJ4/s1600/hierarquia.png

**Topologia Mista ou Hibrida**

A topologia mista ou hibrida, como o próprio nome sugere, consiste na utilização de duas ou mais topologia ao mesmo tempo. Esse tipo de topologia vem a atender necessidade específicas, principalmente de grandes redes, tais como custo, flexibilidade e crescimento da rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264114/13404.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/1/264114/13404.png)

Topologia de rede mista

**Topologia em Malha ou Mesh**

A topologia em malha é utilizada quando se deseja a redundância total na rede, isso significa que cada nó estará conectado a todos os dispositivos, formando assim, uma “teia” com múltiplos caminhos até o destino. É comum utilizamos roteadores para formar esse tipo de topologia, que se encarrega de encontrar o melhor caminho por meio dos diferentes nós da rede. Apesar da grande redundância, a topologia em Malha tem como desvantagem o alto custo financeiro e alta complexidade de configuração.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/3/5/343544/26688.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/4/3/5/343544/26688.jpg)

Topologia física em malha ou mesh

### **Topologia Lógica**

Como já comentado anteriormente, as topologias lógicas especificam como os sinais trafegam através das redes e qual será o método de acesso aos meios de transmissão. Basicamente, podemos dividir as topologias lógicas em dois grandes métodos:

- Barramento ou Não-determinística;
- Anel ou Determinística

**Barramento ou não-determinística:** Os nós que pertencem a uma rede do tipo não-determinística detêm o “poder” de enviar quando quiser, ou seja, não existe um dispositivo concentrador que determina quem vai enviar dentro da rede. As redes do tipo Ethernet utilizam esse conceito, os nós da rede podem enviar a qualquer tempo, desde que o meio de transmissão esteja disponível. Topologias lógicas que utilizam esse mecanismo são conhecidas como Topologia lógica em Barramento (não confundir com topologia física em barramento).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/1/297124/SEQUENCIA-Broadcasting--PSD.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/7/1/297124/SEQUENCIA-Broadcasting--PSD.gif)

**Anel ou Determinística:** Diferentemente da topologia lógica Não-determinística, as redes do tipo Determinística movem um quadro pela rede que controla o acesso ao meio de transmissão. Redes Token-Ring utilizam um dispositivo concentrador chamado de MAU (Multistation Access Unit, unidade de acesso de estação). O MAU concentra os dispositivos que fazem parte do anel lógico e, por meio do token ou bastão, é feito o controle do acesso ao meio de transmissão. Somente o dispositivo que possui o bastão poderá enviar na rede por um curto período de tempo. O bastão com a mensagem circula na rede até alcançar o dispositivo de destino, que copia a mensagem para processamento, enquanto isso, o bastão volta a circular pelo no anel. A animação abaixo exemplifica como funciona uma rede do tipo Token-Ring.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/1/5/351564/26685.gif)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/1/5/351564/26685.gif)

Funcionamento da topologia Token-Ring ou Anel

Fonte:

Apesar das redes Token-Ring não apresentar colisão dentro da rede, já que, somente quem possui o bastão pode enviar, atualmente, esse tipo de rede é difícil de se encontrar por apresentar as seguintes desvantagem:

- A rede pode ficar ociosa caso o bastão esteja com um nó que possui dados a serem enviados;
- Não são compatíveis com as redes Ethernet;
- O custo é mais elevado;
- Baixa largura de banda.

Atenção: Em uma rede, existe a possibilidade de se utilizar uma topologia lógica em barramento com em uma topologia física em estrela. Em outras palavras, podemos utilizar o protocolo Ethernet, que utiliza a topologia lógica em barramento, para envio e recebimento. Da mesma forma, podemos utilizar uma topologia lógica em Anel (Protocolo Token-Ring) tanto em uma topologia física em barramento quanto estrela.