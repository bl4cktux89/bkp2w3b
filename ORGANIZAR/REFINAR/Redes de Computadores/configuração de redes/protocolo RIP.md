**Definição**

O _**Routing Information Protocol**_ (RIP) é um protocolo de roteamento dinâmico que utiliza algoritmo de roteamento baseado em vetor de distância e que, uma vez habilitado, divulga a(s) rede(s) que consegue acessar a outros roteadores na rede – desde que esses outros roteadores também estejam com o protocolo habilitado.

**Aplicação**

O RIP é utilizado em redes de pequeno porte, com dezenas de roteadores na topologia, uma vez que, após habilitado, os roteadores trocarão mensagens entre si para atualizarem suas respectivas tabelas de roteamento, de maneira automática e dinâmica. Dentre os protocolos de roteamento, o RIP é um dos mais simples e fáceis de configurar e, como utiliza algoritmo de roteamento baseado em vetor de distância, não exige muito do hardware do equipamento de rede, sendo portanto um protocolo de roteamento adequado a redes relativamente pequenas e mais antigas, cujo hardware (essencialmente, processador e memória RAM do equipamento) é mais modesto.

**Vetor de distância**

Segundo Kurose e Ross (2014), protocolos de roteamento que utilizam algoritmos baseados em vetor de distância possuem como métrica a quantidade de saltos (_**hops**_) que um pacote precisa fazer para atingir seu destino. Esses saltos nada mais são que a quantidade de roteadores pelos quais um pacote “passa”.

Em termos de protocolos de roteamento, métrica (também chamado de “custo” da rota) é um valor numérico associado a um determinado protocolo, que determina o quão melhor uma rota (caminho que um pacote pode utilizar para atingir o destino) é em relação a outra.

Esse tipo de algoritmo não é muito eficiente, pois uma rota pode ser mais “longa” (ter mais saltos) e mesmo assim ser melhor, como podemos ver na Figura 1, onde a rota pelos Roteadores A e B, apesar de ter mais saltos, é mais rápida (_**links**_ de 1Gbps) do que a rota que passa apenas pelo Roteador C, cujo _**link**_ é de 10Mbps.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/4/9/2394943/41000.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/9/4/9/2394943/41000.jpg)

Fonte: O autor.

O RIP envia mensagens a outros roteadores – também com o protocolo RIP habilitado – periodicamente, com a informação das redes que ele conhece e sabe acessar. Por padrão, essas mensagens são enviadas a cada 30 segundos. Isso significa que, se uma rede ficar inacessível (por exemplo, devido ao rompimento do cabo de rede), poderá levar até 30 segundos para que os roteadores “vizinhos” sejam informados que aquela rota no está mais disponível.

Sendo assim, você pode ser motivado a diminuir esse tempo através da configuração do RIP, mas lembre-se que, caso mensagens sejam enviadas com maior frequência, mais poder de processamento será exigido do hardware, o que pode causar uma falha na rede, pelo simples fato de diminuirmos esse tempo padrão de envio de mensagens periódicas!

Por esse motivo que cada rede deve ser ajustada e monitorada, e não existe um valor ideal pré-definido.

**Cenário** **de exemplo**

A título de exemplo, considere a topologia da Figura 2, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389781/41001.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389781/41001.png)

No cenário acima, os roteadores A e B; o PC e o Servidor, possuem as configurações apresentadas na Quadro 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/1/7/9/2417983/41002.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/1/7/9/2417983/41002.jpg)

Fonte:

Cada roteador possui uma tabela de roteamento, das rotas diretamente conectadas às suas interfaces. Entretanto, qualquer outra rota que não esteja diretamente conectada as suas interfaces, necessitam ser informadas. Veja o Quadro 2 abaixo, referente a tabela de roteamento desses dois roteadores:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/1/7/9/2417925/41003.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/1/7/9/2417925/41003.jpg)

Fonte:

Note, pelas tabelas de roteamento do Quadro 2, que ambos roteadores sabem encaminhar pacotes para as redes que estejam diretamente conectadas a eles, mas não sabem como encaminhar pacotes para as demais redes.

**Configuração do cenário de exemplo**

Abaixo são apresentadas imagens da configuração para o cenário de exemplo. Inicialmente, a configuração foi realizada conforme Quadro 1 e, desse modo, a tabela de roteamento dos Roteadores A e B está de acordo com o Quadro 2, conforme podemos ver na Figura 3(a), que apresenta a tabela de roteamento para o Roteador A; e na Figura 3(b), que apresenta a tabela de roteamento para o Roteador B.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386593/41004.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/6/5/2386593/41004.png)

Como pode ser visto nas imagens acima, ambos roteadores só conhecem as rotas para as redes diretamente conectadas a eles. Nessa condição, ao tentarmos utilizar o comando _**ping**_ entre o PC e o servidor, a partir do PC, observamos que não há resposta, exatamente pelo fato de que o Roteador A não sabe, nesse ponto, como encaminhar pacotes para a rede 10.1.1.0/24, conforme observamos na Figura 4, abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/1/2387166/form-obj-0.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/1/2387166/form-obj-0.png)

Primeiramente devemos habilitar o RIP no roteador A, com o comando router rip; depois habilitamos a versão mais atual, com o comando version 2 e utilizar o comando no auto-summary para que o RIP utilize a máscara de rede definida para a rede especificada (_**classless**_), em vez de utilizar a máscara de rede padrão (_**class**__**full**_). Por fim, para que o roteador passe a informar aos demais roteadores da rede (que estejam também com o protocolo RIP habilitado), que ele sabe como acessar a rede 10.1.1.0/24, utilizamos o comando network, para cada rede que desejamos propagar.

No caso do Roteador A, os comandos seriam: network 192.168.1.0 e network 192.168.2.0; e no Roteador B seriam: network 10.1.1.0 e network 192.168.2.0.

Perceba que, no RIP, a estratégia de configuração é a de definirmos quais rotas desejamos que sejam propagadas para os demais roteadores da rede (rotas estas que já são conhecidas pelo roteador que estamos configurando, pelo fato destes estarem diretamente conectados a estas rotas). Fazendo essa configuração em cada roteador, cada um deles propagará suas rotas aos seus vizinhos e, desta forma, após alguns segundos (30 segundos, por padrão), todos os roteadores conseguirão acessar todas as redes propagadas.

Na Figura 5, abaixo, vemos a configuração do RIP em cada roteador:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/0/2387025/41007.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/0/2387025/41007.png)

Na Figura 6, abaixo, temos a tabela de roteamento dos roteadores, já atualizada:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/0/2387081/41009.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/0/2387081/41009.png)

Percebemos, pela Figura 6, que agora o Roteador A sabe como acessar a rede 10.1.1.0/24, que “aprendeu” via protocolo RIP. Similarmente, agora o Roteador B sabe como acessar a rede 192.168.1.0/24, que “aprendeu” via protocolo RIP.

Agora o comando _**ping**_ é executado com sucesso, conforme Figura 7:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/1/2387175/41010.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/7/1/2387175/41010.png)

**Conclusão**

Neste capítulo apresentamos os principais conceitos relacionados ao protocolo RIP, realizamos a configuração e validação de um cenário de exemplo através do simulador Packet Tracer®, da Cisco.