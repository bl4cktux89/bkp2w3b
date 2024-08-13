**Definição**

O _**Open Shortest Path First**_ (OSPF) é um protocolo de roteamento dinâmico _**de jure**_ (aberto, não proprietário) que utiliza algoritmo de roteamento baseado no estado do _**link**_ e que, uma vez habilitado, divulga a(s) rede(s) que consegue acessar a outros roteadores na rede – desde que esses outros roteadores também estejam com o protocolo habilitado.

**Aplicação**

O OSPF é utilizado em redes de médio e grande porte, de dezenas a centenas de roteadores na topologia, uma vez que, após habilitado, os roteadores trocarão mensagens entre si para atualizarem suas respectivas tabelas de roteamento, de maneira automática e dinâmica. Como veremos a seguir, o OSPF trabalha com muitas informações para atualizar toda a tabela de roteamento, além de executar cálculos (operações matemáticas) para escolha da melhor rota a um destino, o que exige muito do hardware do equipamento de rede, sendo portanto um protocolo de roteamento adequado a redes de médio e grande porte e mais modernas, cujo hardware (essencialmente, processador e memória RAM do equipamento) é mais robusto.

**Estado do** _**link**_

Segundo Kurose e Ross (2014), protocolos de roteamento que utilizam algoritmos baseados em estado do link possuem como métrica uma função, baseada em informações acerca da rede. No caso do OSPF, a métrica é um valor numérico inteiro, associado a largura de banda (velocidade nominal) dos links que compõem determinada rota. Após realizada essa conta, é utilizado um algoritmo, chamado algoritmo de Dijkstra (em homenagem ao cientista da computação, Edsger Dijkstra, que o desenvolveu), para determinar a melhor rota utilizando, para tal, a métrica descrita anteriormente.

Em termos de protocolos de roteamento, métrica (também chamado de “custo” da rota) é um valor numérico associado a um determinado protocolo, que determina o quão melhor uma rota (caminho que um pacote pode utilizar para atingir o destino) é em relação a outra.

Esse tipo de algoritmo é interessante, pois uma rota pode ser mais “longa” e mesmo assim ser melhor, como podemos ver na Figura 1, onde a rota pelos Roteadores A e B, apesar de ter mais roteadores no caminho, é mais rápida (_**links**_ de 1Gbps) do que a rota que passa apenas pelo Roteador C, cujo _**link**_ é de 10Mbps.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/4/9/2394982/41067.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/4/9/2394982/41067.png)

Figura 1 - Escolha da rota em protocolos baseados no estado do link.

O OSPF funciona baseado na troca de pacotes, chamados de “hello”, entre roteadores vizinhos, que também estejam rodando o protocolo OSPF. Mais detalhadamente, o processo de funcionamento de roteadores executando o OSPF segue as seis etapas abaixo:

1) Cada roteador deve estar com o OSPF habilitado e, para tal, precisamos atribuir um número identificador ao processo do OSPF (usualmente, atribuímos o número 1).

2) Definimos um pseudo IP para ser um identificador único, para cada roteador na rede; número este utilizado pelo OSPF. Como esse identificador, chamado _**RouterID**_, precisa ser no formato IPv4, geralmente utilizamos 1.1.1.1 para o primeiro roteador configurado, depois 2.2.2.2 para o segundo, e assim sucessivamente. Importante lembrar que, apesar de o _**RouterID**_ ser no formato IPv4, não precisa ser um IP real, utilizado na rede.

3) Adicionamos as interfaces (portas do roteador) desejadas, para que possam informar aos roteadores vizinhos das rotas conectadas a eles, através do comando _**network**_. Um detalhe que vale atenção aqui é que o OSPF foi projetado para funcionar em redes de grande porte, de forma que, junto ao comando _**network**_, precisamos informar uma área (tipicamente associada a uma região geográfica) na qual esse roteador operará. O padrão é _**area 0**_, em redes grandes, podemos criar mais áreas (a área 0 sempre é necessária), mas essa utilização está fora do escopo dessa disciplina.

4) Agora o roteador, já configurado, tentará formar uma relação de vizinhança com outros roteadores, através das mensagens de _**hello**_, enviadas pelas interfaces configuradas anteriormente.

Essa vizinhança somente será formada caso os seguintes parâmetros sejam idênticos, entre os roteadores:

- _**Hello**_ e _**dead timers**_: esses são os tempos em que atualizações das rotas são enviadas a outros roteadores e tempo para considerar que um vizinho não está mais presente na rede, respectivamente.Máscara da rede: a máscara da rede entre dois vizinhos precisa ser a mesma.Área no qual o roteador funcionará.

5) Um roteador vizinho recebe essa mensagem de _**hello**_, verifica se os parâmetros acima coincidem com os dele, e envia uma resposta a mensagem de _**hello**_.

6) Agora que a vizinhança está formada e as informações sincronizadas (esse estado é chamado de _**full state)**_ o algoritmo de Djsktra entra em ação para verificar qual a melhor rota para acessar uma determinada rede, baseado no custo das rotas.

No OSPF, a métrica de custo é calculada para cada link que faz parte de uma determinada rota, utilizando a seguinte fórmula: 100 / Largura da Banda (em Mbps).

**Cenário** **de exemplo**

A título de exemplo, considere a topologia da Figura 2, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395019/41068.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395019/41068.png)

Figura 2 - Cenário de exemplo.

No cenário acima, os roteadores A e B; o PC e o Servidor, possuem as configurações apresentadas na Quadro 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/0/9/2420999/41069.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/0/9/2420999/41069.png)

Cada roteador possui uma tabela de roteamento, das rotas diretamente conectadas às suas interfaces. Entretanto, qualquer outra rota que não esteja diretamente conectada as suas interfaces, necessitam ser informadas. Veja o Quadro 2 abaixo, referente a tabela de roteamento desses dois roteadores:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/1/1/2421118/41070.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/1/1/2421118/41070.png)

Note, pelas tabelas de roteamento do Quadro 2, que ambos roteadores sabem encaminhar pacotes para as redes que estejam diretamente conectadas a eles, mas não sabem como encaminhar pacotes para as demais redes.

**Configuração do cenário de exemplo**

Abaixo são apresentadas imagens da configuração para o cenário de exemplo. Inicialmente, a configuração foi realizada conforme Quadro 1 e, desse modo, a tabela de roteamento dos Roteadores A e B está de acordo com o Quadro 2, conforme podemos ver na Figura 3(a), que apresenta a tabela de roteamento para o Roteador A; e na Figura 3(b), que apresenta a tabela de roteamento para o Roteador B.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386534/41071.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386534/41071.png)

Figura 3 - Tabela de roteamento antes do OSPF estar configurado.

Como pode ser visto nas imagens acima, ambos roteadores só conhecem as rotas para as redes diretamente conectadas a eles. Nessa condição, ao tentarmos utilizar o comando _**ping**_ entre o PC e o servidor, a partir do PC, observamos que não há resposta, exatamente pelo fato de que o Roteador A não sabe, nesse ponto, como encaminhar pacotes para a rede 10.1.1.0/24, conforme observamos na Figura 4, abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386542/41072.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386542/41072.png)

Figura 4 - Comando ping no PC antes do OSPF estar configurado.

Primeiramente devemos habilitar o OSPF no roteador A, com o comando _**router ospf 1**_ (o “1” refere-se ao número do processo OSPF que estamos atribuindo neste roteador).

Depois, informamos o _**RouterID**_, através do comando _**router-id 1.1.1.1**_ (o número é arbitário, mas precisa ser único por roteador, e estar no formato de endereço IPv4).

Agora basta informar as redes que desejamos propagar, com o comando _**network**_. Um detalhe é que, com o OSPF, o comando network, precisamos informar também o chamado _**wildcard**_ _**mask**_, que é o contrário da máscara de rede, além da área (conforme explicamos anteriormente). Por exemplo, como queremos informar aos outros roteadores da rede, sobre uma rede que o Roteador A conhece através de sua interface com endereço IPv4 _**192.168.1.**__**1**_, e a máscara de rede _**255.255.255.0**_, o _**wildcard**_ _**mask**_ será _**0.0.0.255**_.

No caso do Roteador A, os comandos seriam: _**network**_ _**192.168.1.0**_ _**0.0.0.255 area 0**_ e _**network**_ _**192.168.**__**2**__**.0**_ _**0.0.0.255 area 0**_; e no Roteador B seriam: _**network**_ _**10.1**__**.1.0**_ _**0.0.0.255 area 0**_ e _**network**_ _**192.168.**__**2**__**.0**_ _**0.0.0.255 area 0**_.

Na Figura 5, abaixo, vemos a configuração do OSPF em cada roteador:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386553/41073.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386553/41073.png)

Figura 5 - Configuração do OSPF nos roteadores.

Na Figura 6, abaixo, percebemos que a vizinhança OSPF foi estabelecida com sucesso, através do comando _**show ip ospf neighbor**_:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/3/2387399/41074.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/3/2387399/41074.png)

Figura 6 - Vizinhanças OSPF estabelecidas.

Na Figura 7, abaixo, vemos a tabela de roteamento dos roteadores, através do comando _**show ip**_ _**route**_, já atualizada:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/4/2387422/41075.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/4/2387422/41075.png)

Figura 7 - Tabelas de roteamento atualizadas.

Percebemos, pela Figura 7, que agora o Roteador A sabe como acessar a rede 10.1.1.0/24, que “aprendeu” via protocolo OSPF. Similarmente, agora o Roteador B sabe como acessar a rede 192.168.1.0/24, que “aprendeu” via protocolo OSPF.

Agora o comando _**ping**_ é executado com sucesso, conforme Figura 8:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/4/2386434/41076.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/4/2386434/41076.png)

Figura 8 - Comando ping no PC depois do OSPF configurado.

**Conclusão**

Neste capítulo apresentamos os principais conceitos relacionados ao protocolo OSPF, realizamos a configuração e validação de um cenário de exemplo através do simulador Packet Tracer®, da Cisco.