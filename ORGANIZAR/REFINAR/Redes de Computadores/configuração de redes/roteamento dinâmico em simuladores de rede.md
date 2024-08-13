**Definição**

Roteamento dinâmico pode ser definido como a inserção automática de diferentes rotas que um pacote pode seguir em uma determinada topologia de rede. Essa inserção é feita pelos próprios algoritmos de roteamento, que devem ser habilitados em cada equipamento através de comandos específicos, que dependem do sistema operacional no qual se deseja configurar o roteamento. Importante lembrar que, sempre que uma topologia apresentar caminhos alternativos (ou seja, mais de um caminho) para os pacotes, será necessário configurar a chamada tabela de roteamento dos dispositivos envolvidos. O cenário mais comum é quando existirem dois ou mais roteadores na topologia.

Note que dispositivos que podem ser configurados para fazer roteamento são, necessariamente, dispositivos que conseguem operar na Camada 3 (_**Layer**_ 3) do modelo de referência ISO/OSI como, por exemplo, os chamados roteadores e os switches _**Layer**_ 3.

**Aplicação**

O roteamento dinâmico é utilizado em redes de grande porte, com dezena ou centenas de roteadores na topologia uma vez que, após habilitado o algoritmo de roteamento dinâmico, os roteadores trocarão mensagens entre si para atualizarem suas respectivas tabelas de roteamento, de maneira automática e dinâmica. Em contrapartida, o uso desse recurso tem um custo computacional elevado, de forma que é interessante que os hardwares dos equipamentos que farão o roteamento dinâmico possuam configurações adequadas. Os requisitos mínimos para que o recurso possa ser habilitado é geralmente indicado no manual do sistema operacional do equipamento.

**Cenário** **de exemplo**

A título de exemplo, considere a topologia da Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/9/2387940/40702.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/9/2387940/40702.png)

No cenário acima, os roteadores A e B; o PC e o Servidor, possuem as configurações apresentadas no Quadro 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389737/40703.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389737/40703.png)

Cada roteador possui uma tabela de rotas, a chamada tabela de roteamento, das rotas diretamente conectadas às suas interfaces, porém qualquer outra rota que não esteja diretamente conectada as suas interfaces, necessitam ser informadas pelo especialista de redes, no caso do roteamento estático. Veja o Quadro 2 abaixo, referente a tabela de roteamento desses dois roteadores:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/1/0/2421000/40704.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/1/0/2421000/40704.png)

Note, pelas tabelas de roteamento do Quadro 2, que ambos roteadores sabem encaminhar pacotes para as redes que estejam diretamente conectadas a eles, mas não sabem como encaminhar pacotes para as demais redes. Para tal, se faz necessário configurar as rotas desconhecidas, em cada um dos roteadores. A configuração será mostrada na próxima seção mas, após tal configuração, a tabela de roteamento ficaria completa, conforme Quadro 3:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/1/0/2421026/40705.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/2/1/0/2421026/40705.png)

Fonte:

**Configuração do cenário de exemplo**

Abaixo são apresentadas imagens da configuração para o cenário de exemplo. Inicialmente, a configuração foi realizada conforme Quadro 1 e, desse modo, a tabela de roteamento dos Roteadores A e B está de acordo com o Quadro 2, conforme podemos ver na Figura 2(a), que apresenta a tabela de roteamento para o Roteador A; e na Figura 2(b), que apresenta a tabela de roteamento para o Roteador B.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/2/2387249/40706.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/2/2387249/40706.jpg)

Como pode ser visto nas imagens acima, ambos roteadores só conhecem as rotas para as redes diretamente conectadas a eles. Nessa condição, ao tentarmos utilizar o comando “ping” entre o PC e o servidor, a partir do PC, observamos que não há resposta, exatamente pelo fato de que o Roteador A não sabe, nesse ponto, como encaminhar pacotes para a rede 10.1.1.0/24, conforme observamos na Figura 3, abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/2/2387261/40707.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/2/2387261/40707.png)

Podemos escolher habilitar diferentes protocolos de roteamento dinâmicos, conforme seja mais adequado para a situação, levando em conta características como: fabricante do equipamento, quantidade de roteadores na rede, características de memória RAM e CPU dos roteadores, etc.

Na versão do simulador Packet Tracer utilizada (7.1.1), podemos optar pelos seguintes protocolos de roteamento dinâmico:

- _Enhanced Interior Gateway Routing Protocol_ (EIGRP)
- _Routing Information Protocol_ (RIP)
- _Open Shortest Path First_ (OSPF)
- _Border Gateway Protocol_ (BGP)

Nesta aula, utilizaremos o RIP, por ser um dos protocolos de roteamento mais simples de ser configurado.

Primeiramente devemos habilitar o RIP no roteador A, com o comando _**router rip**_; depois habilitamos a versão mais atual, com o comando _**version 2**_ e utilizar o comando _**no auto-summary**_ para que o RIP utilize a máscara de rede definida para a rede especificada (_**classless**_), em vez de utilizar a máscara de rede padrão (_**class**__**full**_). Por fim, para que o roteador passe a informar aos demais roteadores da rede (que estejam também com o protocolo RIP habilitado), que ele sabe como acessar a rede 10.1.1.0/24, utilizamos o comando _**network**_, para cada rede que desejamos propagar, conforme segue:

_**network rede_que_desejamos_propagar**_

No caso do Roteador A, o comando seria _**network 192.168.1.0**_ e _**network 192.168.2.0**_; e no Roteador B seria _**network 10.1.1.0**_ e _**network 192.168.2.0**_.

Perceba que, no roteamento automático, a estratégia de configuração é a de definirmos quais rotas desejamos que sejam propagadas para os demais roteadores da rede (rotas estas que já são conhecidas pelo roteador que estamos configurando, pelo fato destes estarem diretamente conectados a estas rotas). Fazendo essa configuração em cada roteador, cada um deles propagará suas rotas aos seus vizinhos e, desta forma, após alguns segundos, todos os roteadores conseguirão acessar todas as redes propagadas.

Na Figura 4, abaixo, vemos a configuração do RIP em cada roteador:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/2/2387296/40708.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/2/2387296/40708.png)

Na Figura 5, abaixo, temos a tabela de roteamento dos roteadores, atualizada:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/3/2387341/40709.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/3/2387341/40709.png)

Percebemos, pela Figura 5, que agora o Roteador A sabe como acessar a rede 10.1.1.0/24, que “aprendeu” via protocolo RIP. Similarmente, agora o Roteador B sabe como acessar a rede 192.168.1.0/24, que “aprendeu” via protocolo RIP.

Agora o comando “ping” é executado com sucesso, conforme Figura 6:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/3/2387355/40710.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/3/2387355/40710.png)

**Conclusão**

Neste capítulo apresentamos a definição de roteamento dinâmico, explicamos sua utilidade e realizamos a configuração e validação de um cenário de exemplo através do simulador Packet Tracer®, da Cisco.