**Definição**

O _**Dynamic Host Configuration Protocol**_ (DHCP) é um protocolo que pode ser habilitado e configurado, tanto em switches ou roteadores (atuando como servidores DHCP), quanto em servidores propriamente ditos (seja com sistema operacional MS-Windows, GNU/Linux, etc.), que atribui endereços IP de maneira automática a qualquer cliente (_**host**_) que solicite esse tipo de serviço, em uma rede de computadores.

**Aplicação**

A necessidade de configurar e utilizar esse tipo de serviço na rede se dá exatamente pelo fato de poupar o trabalho (e eventual erro por falta de atenção, por exemplo) na atribuição individual de endereços IP, em cada cliente na rede (como PCs, _**laptops**_, _**smartphones**_, _**Smart**_ TVs, entre outros), pelo profissional de redes.

Já imaginou você, tendo que ir, de computador em computador, configurando essas informações nas propriedades da placa de rede, em uma empresa com, digamos, 153 computadores? Seria tedioso, para dizer o mínimo.

**Princípio de funcionamento**

O funcionamento do DHCP se baseia na troca de 4 mensagens, entre os clientes e o servidor DHCP, na seguinte ordem cronológica (DONAHUE, 2011):

- _**Di**__**s**__**covery**_: mensagem enviada pelo cliente, em _broadcast_ (para todos os dispositivos na rede), solicitando um endereço IP a um servidor DHCP.
- _**Offer**_: resposta do servidor enviada a um cliente específico (e, portanto, em _unicast_), informando que ele tem um endereço livre para disponibilizar a este cliente.
- _**Request**_: mensagem enviada pelo cliente, em _unicast_, informando que ele aceitar o endereço IP que o servidor tem a ofertar.
- _**A**__**cknowledgement**_: resposta do servidor enviada ao cliente, com o endereço IP (e outras informações adicionais como, por exemplo, por quanto tempo esse endereço IP poderá ser utilizado pelo cliente até que este tenha que fazer uma nova solicitação).

Além disso, é importante que você conheça 5 termos bastante utilizados quando da configuração desse serviço. São eles:

- **Escopo**: refere-se a rede IP (endereço IP + máscara de rede) que o servidor DHCP disponibilizará aos clientes, ou seja, é a faixa de endereços IP que poderão ser disponibilizados pelo servidor DHCP e, assim, poderão ser assumidos pelos clientes (desktops, laptops, smartphones, câmeras de vigilância IP, etc.). É comum vermos esse termo em inglês, nas configurações dos equipamentos: _pool_.
- **Duração** da concessão: refere-se a quanto tempo os endereços IP poderão ser utilizados pelos clientes até que estes tenham que fazer uma nova solicitação. Serve para garantir que computadores que não estejam sendo utilizados (por exemplo, por ficarem dias desligados) não fiquem “ocupando” endereços IP que poderiam ser utilizados por outras máquinas. É comum vermos esse termo em inglês, nas configurações dos equipamentos: _lease_ ou _lease time_.
- **Exclusões**: refere-se a faixas de endereços IP que não desejamos “entregar” aos clientes e serve para organizarmos melhor o endereçamento da rede. Por exemplo, se desejamos que, dentro da rede 192.168.1.0/24, os clientes possuam endereços entre 192.168.1.**100**/24 e 192.168.1.**200**/24 (pois os demais seriam utilizados por outra categoria de equipamentos como, por exemplo, servidores), deveríamos excluir do escopo os endereços que estão fora dessa faixa.
- **Reservas**: refere-se a quando desejamos que algum cliente em específico receba um mesmo endereço IP, sempre. Serve, por exemplo, para não precisarmos reconfigurar a impressora no computador; o que teria de ser feito caso o endereço IP da impressora ficasse mudando de tempos em tempos.
- **Opções**: conjunto de parâmetros adicionais que, eventualmente, são interessantes de serem atribuídos automaticamente aos clientes. Exemplos frequentemente utilizados são: o d_efault-gateway_ (endereço do roteador ou switch Layer 3 da rede, que serve para que as máquinas, em uma a rede local, possam se comunicar com outras redes) e o servidor DNS, para que seja possível traduzir nomes de domínio em endereços IP – a propósito, é graças a configuração do servidor DNS que você pode utilizar um nome no navegador de internet, como _google.com_, em vez de ter que decorar algo como _172.217.29.206_.

**Cenário de exemplo**

A título de exemplo, utilizaremos o roteador como servidor DHCP, e dois PCs como clientes. Considere a topologia na Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/7/5/1/2375195/40714.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/7/5/1/2375195/40714.png)

**Configuração do cenário de exemplo**

Ambos PCs estão com suas placas de rede na configuração padrão, ou seja, para receber um endereço IP automaticamente. Veja, na Figura 2, a configuração do DHCP, realizada no roteador:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/6/0/0/2360068/40715.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/6/0/0/2360068/40715.png)

Primeiro definimos um nome para nosso pool de endereços, através do comando _**ip dhcp pool**_.Em seguida, definimos o escopo, através do comando _**network**_.Então, informamos qual será o _**default-gateway**_ dos clientes, através do comando _**default-router**_.Informamos também qual será o servidor DNS dos clientes, através do comando _**dns-server**_.Por fim, definimos a faixa da nossa reserva, através do comando _**ip dhcp excluded-address**_. No exemplo, como queria que os endereços IP dos clientes fossem de 192.168.1.100 até 192.168.1.254, excluímos a faixa de 192.168.1.1 até 192.168.1.99.

Adicionalmente, com o comando _**show ip dhcp binding,**_ vemos quais endereços foram entregues para quais clientes (identificados através do endereço físico, também conhecido como endereço MAC).

Observe agora, na Figura 3, abaixo, através do comando _**ipconfig /all**_ nos PCs, que os endereços foram, de fato, assumidos pelas máquinas; e que os endereços MAC coincidem com os apresentados pelo comando _**show ip dhcp binding**_, da figura anterior:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/7/2/5/2372592/40716.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/7/2/5/2372592/40716.png)

**Conclusão**

Neste capítulo apresentamos a definição do DHCP, comentamos sobre seu funcionamento e os principais termos associados a esse importante protocolo, bem como demonstramos o princípio de funcionamento do DHCP no simulador Packet Tracer®, da Cisco.