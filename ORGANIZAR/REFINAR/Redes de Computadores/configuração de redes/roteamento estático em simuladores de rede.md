**Definição**

Roteamento estático pode ser definido como a inserção manual de diferentes rotas que um pacote pode seguir em uma determinada topologia de rede. Essa inserção é feita através de comandos específicos, que dependem do sistema operacional no qual se deseja configurar o roteamento. Importante lembrar que, sempre que uma topologia apresentar caminhos alternativos (ou seja, mais de um caminho) para os pacotes, será necessário configurar a chamada tabela de roteamento dos dispositivos envolvidos. O cenário mais comum é quando existirem dois ou mais roteadores na topologia.

Note que dispositivos que podem ser configurados para fazer roteamento (seja estático ou dinâmico; conforme veremos no próximo capítulo) são, necessariamente, dispositivos que conseguem operar na Camada 3 (_**Layer**_ 3) do modelo de referência ISO/OSI como, por exemplo, os chamados roteadores e os switches _**Layer**_ 3.

**Aplicação**

O roteamento estático é utilizado quando queremos ter um maior controle em relação a qual caminho (rota) os pacotes seguirão em uma determinada topologia de rede. Em contrapartida, como a inserção das rotas é feita manualmente pelo especialista, uma a uma, o roteamento estático é recomendado apenas em redes relativamente pequenas, com algumas unidades de roteadores na topologia.

**Cenário** **de exemplo**

A título de exemplo, considere a topologia da Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/2/5/2402545/40657.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/2/5/2402545/40657.png)

No cenário acima, os roteadores A e B; o PC e o Servidor, possuem as configurações apresentadas na Quadro 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/3/9/2403948/1.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/3/9/2403948/1.png)

Cada roteador possui uma tabela de rotas, a chamada tabela de roteamento, das rotas diretamente conectadas às suas interfaces, porém qualquer outra rota que não esteja diretamente conectada as suas interfaces, necessitam ser informadas pelo especialista de redes, no caso do roteamento estático. Veja o Quadro 2 abaixo, referente a tabela de roteamento desses dois roteadores:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/3/3/2403329/2.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/3/3/2403329/2.png)

Note, pelas tabelas de roteamento do Quadro 2, que ambos roteadores sabem encaminhar pacotes para as redes que estejam diretamente conectadas a eles, mas não sabem como encaminhar pacotes para as demais redes. Para tal, se faz necessário configurar as rotas desconhecidas, em cada um dos roteadores. A configuração será mostrada na próxima seção mas, após tal configuração, a tabela de roteamento ficaria completa, conforme Quadro 3:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/3/3/2403331/3.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/0/3/3/2403331/3.png)

**Configuração do cenário de exemplo**

Abaixo são apresentadas imagens da configuração para o cenário de exemplo. Inicialmente, a configuração foi realizada conforme Quadro 1 e, desse modo, a tabela de roteamento dos Roteadores A e B está de acordo com o Quadro 2, conforme podemos ver na Figura 2(a), que apresenta a tabela de roteamento para o Roteador A; e na Figura 2(b), que apresenta a tabela de roteamento para o Roteador B.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/2/2381263/40661.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/2/2381263/40661.png)

Como pode ser visto nas imagens acima, ambos roteadores só conhecem as rotas para as redes diretamente conectadas a eles. Nessa condição, ao tentarmos utilizar o comando “ping” entre o PC e o servidor, a partir do PC, observamos que não há resposta, exatamente pelo fato de que o Roteador A não sabe, nesse ponto, como encaminhar pacotes para a rede 10.1.1.0/24, conforme observamos na Figura 3, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/0/2381029/40662.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/0/2381029/40662.png)

Na Figura 4, mais abaixo, configuramos a rota estática para a rede 10.1.1.0/24 através do comando ip route, conforme segue exemplo para o Roteador A:

_**ip route 10.1.1.0 255.255.255.0 192.168.2.2**_Onde _**10.1.1.0**_ é a rede de destino, _**255.255.255.0**_ é a máscara da rede de destino, e _**192.168.2.2**_ é o endereço IP da interface que têm acesso a essa rede de destino.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/0/2381031/40663.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/0/2381031/40663.png)

Agora basta configurar a outra rede no Roteador B. Importante notar que, quando estamos configurando roteamento, o “caminho de ida” de um pacote não é a mesma coisa que “o caminho da volta”, de maneira que, caso não configurássemos o roteamento estático no Roteador B, nesse exemplo, o comando “ping” ainda não teria sucesso, pois apesar do pacote enviado pelo PC conseguir chegar ao seu destino (no caso, o Servidor com endereço IPv4 10.1.1.200), devido ao Roteador A, agora, saber como acessar a rede do Servidor, o Roteador B não saberia por onde devolver o pacote para a origem (no caso, o PC com endereço IPv4 192.168.1.100), por não saber como acessar a rede 192.168.1.0/24.

Uma vez também configurado o Roteador B (o comando nesse caso seria _**ip route 192.168.1.0 255.255.255.0 192.168.2.1**_), o comando “ping” é executado com sucesso, conforme Figura 5:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/2/2381264/40664.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/1/2/2381264/40664.png)

**Conclusão**

Neste capítulo apresentamos a definição de roteamento estático, explicamos sua utilidade e realizamos a configuração e validação de um cenário de exemplo através do simulador Packet Tracer®, da Cisco.