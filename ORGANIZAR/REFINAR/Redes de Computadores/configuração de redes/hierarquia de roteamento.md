**Definição**

A hierarquia de roteamento refere-se a definição de níveis de prioridade, em uma cadeia hierárquica entre diferentes protocolos de roteamento.

**Aplicação**

É comum, e uma rede de computadores de médio e grande porte (com dezenas a centenas de roteadores), existirem diferentes protocolos de roteamento, por uma série de fatores, principalmente relacionados as características do hardware e de interoperabilidade entre estes. Portanto, é necessário que haja uma hierarquia pré-definida entre os diferentes protocolos para que sejam privilegiados certos protocolos em relação a outros.

**Algoritmos de roteamento**

Segundo Kurose e Ross (2014), existem dois tipos de algoritmos utilizados em protocolos de roteamento: os baseados em vetor de distância (_**Distance Vector**_) e os baseados em estado do enlace (_**Link State**_).

**Vetor de distância**

Protocolos de roteamento que utilizam algoritmos baseados em vetor de distância possuem como métrica a quantidade de saltos (_**hops**_) que um pacote precisa fazer para atingir seu destino. Esses saltos nada mais são que a quantidade de roteadores pelos quais um pacote “passa”.

Em termos de protocolos de roteamento, métrica (também chamado de “custo” da rota) é um valor numérico associado a um determinado protocolo, que determina o quão melhor uma rota (caminho que um pacote pode utilizar para atingir o destino) é em relação a outra.

Esse tipo de algoritmo não é muito eficiente, pois uma rota pode ser mais “longa” (ter mais saltos) e mesmo assim ser melhor, como podemos ver na Figura 1, onde a rota pelos Roteadores A e B, apesar de ter mais saltos, é mais rápida (_**links**_ de 1Gbps) do que a rota que passa apenas pelo Roteador C, cujo _**link**_ é de 10Mbps. Por conta disso, protocolos que utilizam esse tipo de algoritmo, como o RIP (_**Routing Information Protocol**_) são utilizados em redes pequenas (com algumas unidades de roteadores na rede) e com hardware de rede mais modesto, uma vez que esse tipo de algoritmo não exige muito em termos de especificações (processador e memória RAM) do roteador.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/5/2387585/40978.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/5/2387585/40978.png)

**Estado do enlace**

Protocolos de roteamento que utilizam algoritmos baseados no estado do enlace possuem informações sobre os links entre os roteadores de origem e destino, e não apenas em relação a quantidade destes. Protocolos de roteamento baseados nesse tipo de algoritmo, como o OSPF (_**Open Shortest Path First**_), escolheriam a rota pelos Roteadores A e B, apesar de ter mais saltos, pois é mais rápida (_**links**_ de 1Gbps) do que a rota que passa apenas pelo Roteador C, cujo _**link**_ é de 10Mbps, conforme observado na Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/5/2387579/40979.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/5/2387579/40979.png)

A métrica (informações coletadas e cálculos executados) varia de protocolo para protocolo, dentre os protocolos de roteamento que utilizam algoritmos baseados em estado do enlace.

**D****istância administrativa**

Considerando a topologia apresentada na Figura 2 e, conforme mencionamos anteriormente no tópico de Aplicação, é comum termos mais de um protocolo de roteamento ativo em uma rede. Neste caso, o que determinará que a rota de cima (dos Roteadores A e B) seja utilizada para acessar a rede do Servidor, se a métrica do RIP é melhor neste caso (apenas 1 salto em relação aos 2 saltos da rota de cima, que seria escolhida pelo OSPF)? Para auxiliar os roteadores nesta decisão, existe a distância administrativa.

Além da informação do custo da rota, cada tipo de roteamento possui uma outra métrica, chamada de distância administrativa, associada a si; sendo essa distância administrativa um **valor numérico**, do tipo inteiro, **adimensional** (ou seja, que não possui uma unidade de medida para referenciá-lo, como litros ou metros). No Quadro 1 apresentamos valores para os principais tipos de roteamento:

Em contrapartida, como esses protocolos necessitam de coletar mais informações (referentes a cada enlace entre a origem e destino), e executar cálculos baseados nessas informações, são protocolos que exigem mais poder de processamento do hardware do equipamento e, por conta disso, são geralmente utilizados em redes com dezenas ou centenas de roteadores, com equipamentos de rede mais modernos.

Dessa forma, a escolha da rota, adotada pelo roteador, obedecerá aos seguintes critérios, caso exista mais de uma rota para uma mesma rede de destino:

- Se essas rotas forem reportadas por diferentes tipos de roteamento, a escolha será feita de acordo com quem tiver a menor distância administrativa.
- Se essas rotas forem reportadas por um mesmo tipo de roteamento, a escolha será feita de acordo com quem menor custo (lembrando que custo, nesse sentido, refere-se a métrica que varia de acordo com o protocolo de roteamento).

Em nosso exemplo, a distância administrativa que garantirá que a rota informada pelo OSPF seria adotada, em vez da rota informada pelo RIP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/1/7/6/2417622/40980.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/1/7/6/2417622/40980.png)

**Conclusão**

Neste capítulo apresentamos a definição e a motivação da hierarquia de roteamento, bem como o significado de termos importantes, como tipos de algoritmos de roteamento, métricas e distância administrativa.