**Definição**

O _**Dynamic Host Configuration Protocol**_ (DHCP) é um protocolo que pode ser habilitado e configurado, tanto em switches ou roteadores (atuando como servidores DHCP), quanto em servidores propriamente ditos (seja com sistema operacional MS-Windows, GNU/Linux, etc.), que atribui endereços IP de maneira automática a qualquer cliente (_**host**_) que solicite esse tipo de serviço, em uma rede de computadores.

**Aplicação**

A necessidade de configurar e utilizar esse tipo de serviço na rede se dá exatamente pelo fato de poupar o trabalho (e eventual erro por falta de atenção, por exemplo) na atribuição individual de endereços IP, em cada cliente na rede (como PCs, _**laptops**_, _**smartphones**_, _**Smart**_ TVs, entre outros), pelo profissional de redes.

Já imaginou você, tendo que ir, de computador em computador, configurando essas informações nas propriedades da placa de rede, em uma empresa com, digamos, 153 computadores? Seria tedioso, para dizer o mínimo.

**Princípio de funcionament****o**

Em redes configuradas com IPv6, temos 2 opções de DHCP (MOREIRAS; SANTOS, HARANO et al., 2015):

_**Stateful**_: o servidor DHCP para IPv6 provê as informações do endereço IPv6 do cliente, máscara de rede e do servidor DNS (servidor responsável por traduzir os nomes dos sites em endereços IP). Esse modo é muito parecido com um servidor DHCP para IPv4, com a diferença de que o mesmo não informa o endereço do _**gateway –**_ roteador que encaminha pacotes para redes que não fazem parte da rede do cliente: quem fica responsável por isso é um protocolo incluso na suíte (conjunto) de protocolos IPv6, chamado NDP (_**Neighbor Discovery Protocol**_).

_**Stateless**_: também chamado pelo acrônimo SLAAC (_**Stateless Address Autoconfiguration**_), no qual o servidor DHCP não mantém informações acerca dos endereços que foram atribuídos aos clientes, mas ainda sim possui um papel importante: atribuir o endereço do servidor DNS. As informações do endereço IPv6 do cliente, máscara de rede e _**gateway**_ são atribuídas pelo próprio cliente, através do protocolo NDP.

**Cenário de exemplo**

A título de exemplo, utilizaremos o roteador como servidor DHCPv6 – no modo _**stateful**_ – e dois PCs como clientes. Considere a topologia na Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/5/2/7/6/2527649/41552.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/5/2/7/6/2527649/41552.png)

**Configuração do cenário de exemplo**

Ambos PCs estão com suas placas de rede na configuração padrão, ou seja, para receber um endereço IPv6 automaticamente. Veja, na Figura 2, a configuração do DHCP, realizada no roteador:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/5/2/8/5/2528527/41553.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/5/2/8/5/2528527/41553.png)

Primeiro devemos habilitar o encaminhamento de pacotes IPv6 no roteador, através do comando _**ipv6 unicast-routing**_.

Agora podemos definir um nome para nossa lista de endereços, além do conjunto de endereços (sub-rede) em si, através do comando _**ipv6 local pool**_ _**LISTA**_ _**SUB-REDE MÁSCARA_DA_SUB-REDE**_ _**MÁSCARA_DA_SUB-REDE**_ Note que, no comando do simulador, o prefixo referente a máscara de rede foi, propositadamente, digitado duas vezes; "64 64", significando que os PCs, neste caso, terão o mesmo prefixo da rede. Entretanto, poderíamos utilizar um prefixo mais amplo para a rede, o que significaria uma rede local maior (suportando mais hosts), porém definirmos um prefixo menor, especificamente para ser utilizado pelos clientes DHCP, por exemplo: "64 48".

Em seguida, definimos um nome de um escopo (conjunto de definições) DHCP que utilizará a lista, definida anteriormente, com o comando _**ipv6 dhcp pool**_ _**ESCOPO**_. O comando para informar a esse escopo DHCP que ele deve utilizar a lista definida anteriormente é o _**prefix-delegation pool**_ _**LISTA**_.

Informamos também qual será o servidor DNS dos clientes, através do comando _**dns-server**_.

Na interface que está conectada aos clientes (através do switch), devemos utilizar o comando _**ipv6 nd managed-config-flag**_ (para definir que essa interface funcionará como sservidor DHCP do tipo _**stateful**_) e o comando i_**pv6 dhcp server**_ _**ESCOPO**_ (para que a interface saiba qual escopo deve ser “entregue” aos clientes).

Adicionalmente, com o comando _**show ip**__**v6**_ _**dhcp binding,**_ vemos quais endereços foram entregues para quais clientes (identificados através do endereço físico, também conhecido como endereço MAC).

Observe agora, na Figura 3 abaixo, através do comando _**ip**__**v6**__**config /all**_ nos PCs, que os endereços foram, de fato, assumidos pelas máquinas; e que os endereços MAC coincidem com os apresentados pelo comando _**show ip**__**v6**_ _**dhcp binding**_, da figura anterior:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/5/2/8/5/2528540/41554.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/5/2/8/5/2528540/41554.jpg)

A título de informação adicional, as linhas apresentadas na saída do comando "ipv6config /all" referem-se a:

- _Physical Address_: Endereço da placa de rede, ou MAC address, do PC;
- _Link-local IPv6 Address_: Endereço não roteável na Internet, para ser utilizado entre equipamentos na rede local (LAN);
- _IPv6 Address_: endereço _unicast_, utilizado para identificar o dispositivo de forma única na rede **e** na Internet;
- _Default Gateway_: endereço do roteador ao qual esse PC está conectado, para que este possa enviar mensagens à dispositivos que estejam em redes diferentes;
- _DNS Servers_: endereço do servidor DNS, responsável por traduzir os nomes de sites (domínios) em endereços IP;
- _DHCPv6 IAID_: identificador da interface de rede, utilizado pelo DHCP para associar uma interface de rede específica a um ou mais endereços IPv6 (IAID significa _Interface Association Identifier_);
- _DHCPv6 Client DUID_: conjunto formado pelo identificador do servidor DHCP + endereço físico (MAC) da placa de rede em si, uma vez que cada par de cliente e servidor DHCP precisam ter um único DUID (DUID significa _DHCP Unique IDentifier_).

**Conclusão**

Neste capítulo apresentamos:

- A definição do DHCP;
- Sua utilidade e aplicação;
- O modo de operação _stateful_;
- O modo de operação _stateless_;
- A configuração do modo DHCPv6 no modo _statefull_, através do simulador Packet Tracer, da Cisco.
    
    ®