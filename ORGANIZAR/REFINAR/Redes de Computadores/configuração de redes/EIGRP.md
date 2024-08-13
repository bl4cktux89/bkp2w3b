**Definição**

O _**Enhanced Interior Gateway Routing Protocol**_ (EIGRP) é um protocolo de roteamento dinâmico atualmente aberto (não proprietário), mas anteriormente era um protocolo proprietário, desenvolvido pela Cisco, que por sua vez se baseou no protocolo IGRP, adicionando melhorias a este – razão do _**enhanced**_ no nome. O EIGRP utiliza algoritmo de roteamento baseado no vetor de distância e que, uma vez habilitado, divulga a(s) rede(s) que consegue acessar a outros roteadores na rede – desde que esses outros roteadores também estejam com o protocolo habilitado.

**Aplicação**

O EIGRP é utilizado em redes de médio e grande porte, de dezenas a centenas de roteadores na topologia, uma vez que, após habilitado, os roteadores trocarão mensagens entre si para atualizarem suas respectivas tabelas de roteamento, de maneira automática e dinâmica. Como veremos a seguir, o EIGRP trabalha com muitas informações para atualizar toda a tabela de roteamento, além de executar cálculos (operações matemáticas) para escolha da melhor rota a um destino, o que exige muito do hardware do equipamento de rede, sendo portanto um protocolo de roteamento adequado a redes de médio e grande porte e mais modernas, cujo hardware (essencialmente, processador e memória RAM do equipamento) é mais robusto.

**Vetor de distância**

O EIGRP utiliza o algoritmo de vetor de distância conhecido como DUAL – _**Diffusing Update Algorithm**_ (KUROSE; ROSS, 2014), o que permite uma convergência muito mais rápida que outros algoritmos também baseados em vetor de distância, como o RIP. Convergência, nesse contexto, refere-se a mudança na topologia, como quando uma rota deixa de existir e um caminho alternativo deve ser utilizado pelo roteador. O motivo dessa rápida convergência é que o algoritmo calcula e define rotas alternativas, de _**backup –**_ denominadas _**Feasible Successor**_ (FS), de forma que, quando uma rota principal, que é a rota que aparece na tabela de roteamento do roteador – denominada _**Successor**_ (S), deixa de existir, a rota alternativa já foi encontrada e está pronta para ser utilizada.

Além disso, o EIGRP utiliza como métrica um cálculo matemático que combina a largura de banda, que é a velocidade (teórica) máxima de transmissão (por exemplo, 100Mbps) e um parâmetro conhecido como _**delay**_ (atraso), que é um tempo associado a cada interface do roteador.

Em termos de protocolos de roteamento, métrica (também chamado de “custo” da rota) é um valor numérico associado a um determinado protocolo, que determina o quão melhor uma rota (caminho que um pacote pode utilizar para atingir o destino) é em relação a outra.

**Princípio de funcionamento**

O EIGRP funciona baseado na troca de pacotes, chamados de “hello”, entre roteadores vizinhos, que também estejam rodando o protocolo EIGRP. Mais detalhadamente, o processo de funcionamento de roteadores executando o EIGRP segue as seis etapas abaixo:

1) Cada roteador deve estar com o EIGRP habilitado e, para tal, precisamos atribuir um número identificador ao grupo no qual esse roteador pertencerá, conhecido como _**Autonomous System**_ (AS), que serve para que o EIGRP saiba quais rotas devem ser propagadas via EIGRP (usualmente atribuímos o número 1).

2) Adicionamos as interfaces (portas do roteador) desejadas, para que possam informar aos roteadores vizinhos das rotas conectadas a eles, através do comando _**network**_.

3) Agora o roteador, já configurado, tentará formar uma relação de vizinhança com outros roteadores, através das mensagens de _**hello**_, enviadas pelas interfaces configuradas anteriormente.

4) Um roteador vizinho recebe essa mensagem de _**hello**_, verifica se os parâmetros acima coincidem com os dele, e envia uma resposta à mensagem de _**hello**_.

5) Agora que a vizinhança está formada e as informações sincronizadas, o algoritmo DUAL entra em ação para verificar qual a melhor rota para acessar uma determinada rede, baseado no custo das rotas.

No EIGRP, a métrica de custo é calculada para cada link que faz parte de uma determinada rota, utilizando a seguinte fórmula: _**256 x ( (10**__**4**_ _**/ largura da banda do link mais lento [em Mbps] ) + (Soma de todos os delays [em μs] / 10) )**_.

6) Os roteadores agora podem enviar mensagens de atualização de rotas (chamadas de mensagens de _**update**_) e de confirmação de recebimento dessas novas rotas (chamadas de _**acknowledgement**_) para outros roteadores que fizerem parte do mesmo _**autonomous system**_, quando ocorrer uma mudança de topologia.

**Cenário** **de exemplo**

A título de exemplo, considere a topologia da Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/6/2/2396241/41161.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/6/2/2396241/41161.png)

No cenário acima, os roteadores A e B; o PC e o Servidor, possuem as configurações apresentadas na Quadro 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/6/8/2/1/2682159/41162.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/6/8/2/1/2682159/41162.png)

Cada roteador possui uma tabela de roteamento, das rotas diretamente conectadas às suas interfaces. Entretanto, qualquer outra rota que não esteja diretamente conectada as suas interfaces, necessitam ser informadas. Veja o Quadro 2 abaixo, referente a tabela de roteamento desses dois roteadores:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/6/8/2/1/2682168/41163.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/6/8/2/1/2682168/41163.png)

Note, pelas tabelas de roteamento do Quadro 2, que ambos roteadores sabem encaminhar pacotes para as redes que estejam diretamente conectadas a eles, mas não sabem como encaminhar pacotes para as demais redes.

**Configuração do cenário de exemplo**

Abaixo são apresentadas imagens da configuração para o cenário de exemplo. Inicialmente, a configuração foi realizada conforme Quadro 1 e, desse modo, a tabela de roteamento dos Roteadores A e B está de acordo com o Quadro 2, conforme podemos ver na Figura 2(a), que apresenta a tabela de roteamento para o Roteador A; e na Figura 2(b), que apresenta a tabela de roteamento para o Roteador B.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395036/obja.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395036/obja.png)

Fonte:

Como pode ser visto nas imagens acima, ambos roteadores só conhecem as rotas para as redes diretamente conectadas a eles. Nessa condição, ao tentarmos utilizar o comando _**ping**_ entre o PC e o servidor, a partir do PC, observamos que não há resposta, exatamente pelo fato de que o Roteador A não sabe, nesse ponto, como encaminhar pacotes para a rede 10.1.1.0/24, conforme observamos na Figura 3, abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389792/41165.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389792/41165.png)

Fonte:

Primeiramente devemos habilitar o EIGRP no roteador A, com o comando _**router**_ _**eigrp**_ _**1**_ (o “1” refere-se ao _**autonomous system**_ desse roteador).

Depois, utilizamos o comando no auto-summary para que o EIGRP utilize a máscara de rede definida para a rede especificada (_**classless**_), em vez de utilizar a máscara de rede padrão (_**classfull**_).

Agora basta informar as redes que desejamos propagar, com o comando _**network**_. Um detalhe é que, com o EIGRP, no comando network, podemos informar também o chamado _**wildcard**_ _**mask**_, que é o contrário da máscara de rede. Por exemplo, como queremos informar aos outros roteadores da rede, sobre uma rede que o Roteador A conhece através de sua interface com endereço IPv4 _**192.168.1.**__**1**_, e a máscara de rede _**255.255.255.0**_, o _**wildcard**_ _**mask**_ será _**0.0.0.255**_.

No caso do Roteador A, os comandos seriam: _**network**_ _**192.168.1.0**_ _**0.0.0.255**_ e _**network**_ _**192.168.**__**2**__**.0**_ _**0.0.0.255**_; e no Roteador B seriam: _**network**_ _**10.1**__**.1.0**_ _**0.0.0.255**_ e _**network**_ _**192.168.**__**2**__**.0**_ _**0.0.0.255**_.

Na Figura 4, abaixo, vemos a configuração do EIGRP em cada roteador:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395054/obja2.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395054/obja2.png)

Fonte:

Na Figura 5, abaixo, percebemos que a vizinhança EIGRP foi estabelecida com sucesso, através do comando _**show ip**_ _**eigrp**_ _**neighbor**_:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395068/obja3.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395068/obja3.png)

Fonte:

Na Figura 6, abaixo, vemos a tabela de roteamento dos roteadores, através do comando _**show ip**_ _**route**_, já atualizada:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395090/obja4.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/5/0/2395090/obja4.png)

Fonte:

Percebemos, pela Figura 6, que agora o Roteador A sabe como acessar a rede 10.1.1.0/24, que “aprendeu” via protocolo EIGRP. Similarmente, agora o Roteador B sabe como acessar a rede 192.168.1.0/24, que “aprendeu” via protocolo EIGRP.

Agora o comando _**ping**_ é executado com sucesso, conforme Figura 7:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389789/41169.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389789/41169.png)

Fonte:

**Conclusão**

Neste capítulo apresentamos os principais conceitos relacionados ao protocolo EIGRP, realizamos a configuração e validação de um cenário de exemplo através do simulador Packet Tracer®, da Cisco.