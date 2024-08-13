**COMO OBTER OU TER ACESSO AO LIVRO LABORATÓRIO DE IPV6: APRENDA NA PRÁTICA USANDO UM EMULADOR DE REDES DO NICBR**

### Este laboratório faz parte do livro Aprenda na prática usando um emulador de redes do NicBr.

Para a realização deste exercício será utilizada a topologia descrita no arquivo: 5-01-OSPFv3.imn. que está disponível no site do NicBR, gratuitamente.

Siga os procedimentos indicados e vamos praticar !

Para saber mais, acesse faça o Download das máquinas virtuais e do livro em http://ipv6.br/pagina/livro-ipv6/

Ou ainda disponível, na versão física, em uma das Bibliotecas dos Campis da Universidade Uninove ! Confira !Venha nos visitar !

### Introdução

O OSPF é um protocolo de roteamento interno (IGP – Interior Gateway Protocol), que permite aos roteadores a troca de informações sobre as rotas que estes conhecem e sobre os estados dos enlaces aos quais estão conectados. A partir destas informações, o roteador mapeia a rede com o intuito de determinar a árvore de caminhos mais curtos para todas as suas sub-redes, tendo o próprio nó como raiz. Ele utiliza o algoritmo de Dijkstra para a escolha do melhor caminho e permite a construção de topologias de rede hierárquicas, agrupando os roteadores de uma rede em áreas.

A cada uma dessas áreas é atribuído um identificador único (Area-ID) de 32 bits e todos os roteadores de uma mesma área mantêm um banco de dados de estado separado, de modo que a topologia de uma área seja desconhecida fora dela. Isto reduz a quantidade de tráfego de roteamento entre diferentes partes da rede. A área de backbone é a responsável por distribuir as informações de roteamento e tem que ser identificada pelo ID 0 (ou 0.0.0.0). Em uma rede em que não existem tais divisões, a áreade backbone é a única a ser configurada.O OSPFv3 é um protocolo utilizado unicamente em redes IPv6 e foi baseado na versão do OSPFv2, utilizada em redes IPv4. Deste modo, em uma rede com pilha dupla é necessário utilizar tanto OSPFv2, para o roteamento IPv4, quanto o OSPFv3, para o roteamento IPv6.(SANTOS,MOREIRAS, et al., 2015, p. 324).

O principal objetivo deste laboratório é apresentar o funcionamento do protocolo de roteamento OSPFv3 em uma rede IPv6. Para tanto será utilizada a aplicação Quagga, que permite a configuração e utilização de protocolos de roteamento em servidores Linux. Este primeiro laboratório apresenta um cenário simples que nos permitirá conhecer o funcionamento e as configurações básicas do protocolo OSPFv3, trabalhando com uma única área. (SANTOS,MOREIRAS, et al., 2015, p. 324).

### Roteiro experimental

1. Inicie o CORE e abra o arquivo 5-01-OSPFv3.imn localizado no diretório lab, dentro do Desktop. A topologia de rede, representada pela Figura 5.1, deve aparecer. Esta topologia apresenta uma rede local composta por dois nós conectados a sub-redes diferentes e por três roteadores, nos quais será configurado o protocolo de roteamento dinâmico OSPFv3.

2. Conforme descrito nos Apêndices B e C, inicialize a simulação, verifique a configuração de endereços IPv6 e IPv4 nos nós n1Backbone, n2Backbone, n3Backbone, n4HostA, e n5HostB.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 20.png|Untitled 20.png]]

3. Verifique a conectividade entre os dispositivos da rede:

(a) Acesse o terminal da máquina n4HostA com um duplo-clique e digite o seguinte comando:

# ping6 -c 4 2001:db8:3::1

O resultado do comando é representado pela Figura 5.2.

A comunicação pôde ser estabelecida pois o endereço utilizado pertence ao roteador n2Backbone, que está diretamente conectado ao n4HostA.

(b) A seguir, teste a conectividade entre o n4HostA e o n5HostB. Ainda no terminal do n4HostA, digite o seguinte comando:

# ping6 -c 4 2001:db8:4::20

O resultado do comando é representado pela Figura 5.3.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 1 12.png|Untitled 1 12.png]]

![[Untitled 2 10.png|Untitled 2 10.png]]

Como estes dois equipamentos não estão diretamente conectados, eles dependem da comunicação entre os roteadores da rede para que haja conectividade. No entanto, mesmo com os roteadores n2Backbone e n3Backbone interligados fisicamente, não houve comunicação.

(c) Abra o terminal do roteador n2Backbone com um duplo-clique sobre ele e digite o seguinte comando:

# ip -6 route show

O resultado do comando é representado pela Figura 5.4.

Este comando mostra todas as redes conhecidas pelo roteador n2Backbone. Como é possível observar, ele também só conhece as redes que estão diretamente conectadas a ele. Por isso, não consegue alcançar os dispositivos que estão na rede 2001:db8:4::/64. Repita este teste nos outros dois roteadores e confirme se eles apresentam o mesmo comportamento.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 3 6.png|Untitled 3 6.png]]

Para proporcionar conectividade entre todos os dispositivos da rede, uma possibilidade seria configurar rotas estáticas entre os roteadores, ensinando-lhes todos os caminhos necessários. Porém, caso houvesse alguma mudança nos links da rede, seria necessário reconfigurar tudo manualmente.

Para automatizar esta tarefa, pode-se trabalhar com protocolos de roteamento dinâmico. Com o uso destes protocolos os roteadores trocam mensagens entre si divulgando as rotas que eles conhecem e informando qualquer mudança de estado dos links da rede.

4. Será utilizado para configurar as rotas entre as redes IPv6 o protocolo de roteamento interno OSPFv3. Configure-o nos três roteadores presentes na topologia.

(a) Abra o terminal do roteador n1Backbone. Será utilizada a aplicação Quagga para configurar o OSPFv3.

Para tanto, digite os seguintes comandos:

# vtysh

# configure terminal

# router ospf6

# router-id 1.1.1.1

# interface eth0 area 0.0.0.0

# interface eth1 area 0.0.0.0

# redistribute connected

# exit

# exit

# exit

O resultado do comando é representado pela Figura 5.5.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 4 6.png|Untitled 4 6.png]]

Estes comandos realizam as seguintes funções:

vtysh

Acessa a interface de configuração do Quagga.

configure terminal

Acessa o modo de edição do Quagga, interface utilizada para definir as configurações dos protocolos de roteamento.

router ospf6

Indica que será configurado o protocolo OSPF para IPv6.

router-id 1.1.1.1

Adiciona um número de 32 bits para identificar o roteador.

redistribute connected

Configura o roteador para informar aos outros roteadores da rede as rotas diretamente conectadas que ele conhece.

interface eth0 area 0.0.0.0

Adiciona a interface eth0 do roteador à área backbone do OSPF, de modo que todas as informações de rotas sejam divulgadas aos roteadores que estiverem conectados a esta interface.

interface eth1 area 0.0.0.0

Do mesmo modo que no item anterior, adiciona a interface eth1 à área backbone do OSPF.

(b) Configure também o roteador n2Backbone. Para isto, abra o terminal do roteador n2Backbone e digite os seguintes comandos:

# vtysh

# configure terminal

# router ospf6

# router-id 2.2.2.2

# interface eth0 area 0.0.0.0

# interface eth1 area 0.0.0.0

# redistribute connected

# exit

# exit

# exit

O resultado do comando é representado pela Figura 5.6.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 5 5.png|Untitled 5 5.png]]

(c) Por fim, configure do mesmo modo o roteador n3Backbone.

Para isto, abra o terminal do roteador n3Backbone com um duplo-clique e digite os seguintes comandos:

# vtysh

# configure terminal

# router ospf6

# router-id 3.3.3.3

# interface eth0 area 0.0.0.0

# interface eth1 area 0.0.0.0

# redistribute connected

# exit

# exit

# exit

O resultado do comando é representado pela Figura 5.7.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 6 4.png|Untitled 6 4.png]]

5. Valide as configurações utilizando inicialmente comandos do Quagga.

(a) Abra o terminal do roteador n2Backbone e digite os seguintes comandos:

# vtysh

# show ipv6 ospf6

# show ipv6 ospf6 neighbor

# show ipv6 route

# exit

O resultado do comando é representado pela Figura 5.8.

Estes comandos apresentam as seguintes informações:

vtysh

Acessa a interface de configuração do Quagga.

show ipv6 ospf6

Mostra um resumo das informações do processo do OSPF. Entre elas, há quanto tempo o processo está rodando, qual o ID, a quais áreas o roteador está conectado e quais interfaces estão conectadas a cada área.

show ipv6 ospf6 neighbor

Mostra um resumo das informações dos vizinhos OSPF. Indica o ID do vizinho, se a sessão está estabelecida, há quanto tempo, etc.

show ipv6 route

Mostra a tabela de roteamento IPv6. As rotas marcadas com a letra “o"são as aprendidas por meio do protocolo OSPF.

(b) Verifique também as rotas que estão presentes no Sistema Operacional do roteador. Ainda no terminal do roteador n2Backbone, digite o seguinte comando:

# ip -6 route show

O resultado do comando é representado pela Figura 5.9.

Compare com o resultado do teste feito no passo 3 deste exercício e veja que agora n2Backbone conhece todas as redes existentes na topologia.

Repita os mesmos comandos nos outros dois roteadores e compare os resultados. Eles devem ser similares, alterando apenas o ID dos vizinhos.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 7 3.png|Untitled 7 3.png]]

![[Untitled 8 3.png|Untitled 8 3.png]]

6. Para finalizar, repita o teste de conectividade entre o n4HostA e o n5HostB e veja se agora é possível realizar a conexão.

(a) Abra o terminal da máquina n4HostA e digite o seguinte comando:

# ping6 -c 4 2001:db8:4::20

O resultado do comando é representado pela Figura 5.10.

(SANTOS,MOREIRAS, et al., 2015)

![[Untitled 9 2.png|Untitled 9 2.png]]

Após a configuração do OSPFv3, a conectividade entre todos os dispositivos da rede pode ser estabelecida.

Analise o funcionamento do protocolo OSPFv3 desabilitando as interfaces dos roteadores e verificando se novos caminhos são aprendidos para se conectarem a determinados segmentos da rede. Por exemplo, desabilite a interface eth0 do roteador n2Backbone e verifique se a conectividade entre as máquinas n4HostA e n5HostB continua ativa. Analise também as tabelas de roteamento para verificar qual caminho passou a ser utilizado no estabelecimento da conexão ou utilize o comando traceroute6 para realizar estes testes e compare os caminhos utilizados.

7. Encerre a simulação

(SANTOS,MOREIRAS, et al., 2015)