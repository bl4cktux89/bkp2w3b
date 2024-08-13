**Definição**

O _**Intermediate System to Intermediate System**_ (IS-IS) é um protocolo de roteamento dinâmico que utiliza algoritmo de roteamento baseado em no estado do _**link**_ e que, uma vez habilitado, divulga a(s) rede(s) que consegue acessar a outros roteadores na rede – desde que esses outros roteadores também estejam com o protocolo habilitado.

**Aplicação**

O IS-IS é utilizado em redes de médio e grande porte, de dezenas a centenas de roteadores na topologia, uma vez que, após habilitado, os roteadores trocarão mensagens entre si para atualizarem suas respectivas tabelas de roteamento, de maneira automática e dinâmica. Além disso, o IS-IS é mais utilizado como protocolo de roteamento dentro das redes de provedores de serviço, como os famosos provedores de Internet (_**Internet Service Providers**_ – ISPs), uma vez que esse protocolo foi projetado para operar com endereços de Camada 2 do modelo de referência ISO/OSI, o que facilita as operações típicas de provedores de serviço, dentre elas, o roteamento dinâmico de circuitos virtuais ponto-a-ponto, que são a base para funcionamento de tecnologias de redes de longo alcance (_**Wide Area Networks**_ – WANs), como o _**Frame Relay**_ e o MPLS (_**Multiprotocol Label**_ _**Switching**_).

O estudo de tecnologias WAN não faz parte do escopo desta disciplina, entretanto, uma breve – porém prática introdução às tecnologias de _**Frame Relay**_ e MPLS pode ser acessada nesse link: [**https://under-linux.org/entry.php?b=2286**](https://under-linux.org/entry.php?b=2286)

**Estado do** _**link**_

Segundo Kurose e Ross (2014), protocolos de roteamento que utilizam algoritmos baseados em estado do link possuem como métrica uma função, baseada em informações acerca da rede. No caso do IS-IS, a métrica é um valor numérico inteiro, do tipo inteiro, adimensional (ou seja, que não possui uma unidade de medida para referenciá-lo, como litros ou metros), associado a largura de banda (velocidade nominal) dos links que compõem determinada rota.

Entretanto, diferentemente de outros protocolos baseados em estado do link, no IS-IS essa relação entre esse valor numérico e a largura de banda **deve ser definido manualmente** pelo especialista de redes, para cada interface conectada do roteador, uma vez que não é calculado automaticamente, como é o caso no protocolo OSPF (_**Open Shortest Path First**_), por exemplo. Esse valor tem uma faixa de 1 a 63, sendo que, por padrão, todas as interfaces possuem um valor igual a 10.

Uma vez parametrizada essa relação adequadamente, é utilizado um algoritmo, chamado algoritmo de Dijkstra (em homenagem ao cientista da computação, Edsger Dijkstra, que o desenvolveu), para determinar a melhor rota utilizando, para tal, a métrica descrita anteriormente.

Em termos de protocolos de roteamento, métrica (também chamado de “custo” da rota) é um valor numérico associado a um determinado protocolo, que determina o quão melhor uma rota (caminho que um pacote pode utilizar para atingir o destino) é em relação a outra.

**P****rincípio de funcionamento**

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/5/0/8/0/2508073/42050.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/5/0/8/0/2508073/42050.png)

O IS-IS funciona baseado na troca de pacotes, chamados de “hello”, entre roteadores vizinhos, que também estejam rodando o protocolo IS-IS, entre roteadores com papéis (ou tipos) pré-determinados, por meio de parametrização (configuração). A propósito, os roteadores também são chamados de dispositivos intermediários (_**i**__**ntermediate**_ _**s**__**ystem**__**s – IS**_); como o IS-IS é um protocolo para comunicação entre roteadores, essa é a origem do seu nome: protocolo para Comunicação Entre Roteadores ou, em inglês, _**I**__**ntermediate**_ _**S**__**ystem**_ _**to I**__**ntermediate**_ _**S**__**ystem**_.

Para facilitar o entendimento desses papéis, considere a topologia apresentada na Figura 2.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/5/0/8/0/2508072/41386.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/5/0/8/0/2508072/41386.png)

Em uma rede que esteja com o protocolo IS-IS habilitado, teremos três tipos de roteadores:

1. Roteadores nível 1 **(L1)**: roteadores “internos”; conhecem as rotas apenas das áreas as quais pertencem, e apenas trocam informações entre si.

2. Roteadores nível 2 **(L2)**: roteadores de _**backbone**_ (redes centrais); conhecem as rotas de acesso às outras áreas, e apenas trocam informações entre si.

3. Roteadores nível 1/2 **(L1/2)**: roteadores que possibilitam que as informações de rotas de acesso a outras áreas e rotas internas de uma área específica possam ser acessadas pelos roteadores que compõem a rede. Funcionam como intermediários entre roteadores de nível 1 e roteadores de nível 2.

Além disso, como dissemos, o IS-IS foi projetado para operar com endereços de Camada 2 do modelo de referência ISO/OSI. Dessa forma, o endereçamento não utiliza o padrão TCP/IP, e sim o padrão do extinto protocolo OSI, conhecido como endereço NSAP (_**Network Service Access Point**_).

Saiba que o ISO/OSI não era apenas uma modelo de referência na década de 70, mas um protocolo de comunicação de redes, concorrente do protocolo TCP/IP, sendo que este último acabou por se tornar o padrão utilizado nas redes de computadores.

O NSAP, em linhas gerais, é formado pelo número 49 (indicando que é um endereço privado, de uso interno de uma empresa), por um número de área, uma sequência de, geralmente, 6 bytes (ao menos na maioria dos fabricantes de roteadores) e um identificador do tipo de dispositivo (“00” no caso de roteadores). Assim, um exemplo de endereço NSAP seria _**49.0001.111A.111B.111C.00**_.

**Conclusão**

Neste capítulo apresentamos:

- Os principais conceitos relacionados ao protocolo IS-IS;
- Definição do algoritmo, que é baseado em estado do link;
- Esquema de endereçamento NSAP.