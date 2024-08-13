### Introdução

O DHCP é o serviço contido no roteador que atribui automaticamente um endereço IP às interfaces associadas na rede. Nele a interface encaminha um pacote solicitando uma resposta do servidor DHCP e assim que recebe esta resposta, solicita um endereço IP juntamente com outras informações de rede, como o DNS e o Gateway. Inicialmente, o objetivo do IPv6 era abandonar o uso do DHCP com a auto-configuração independente feita pelas interfaces, porém como a implantação total deste sistema não foi possível, foram feitas algumas mudanças no protocolo, gerando o  DHCPv6, que contém dois tipos diferentes: o Stateful e o Stateless.

![[Untitled 16.png|Untitled 16.png]]

### Stateful e Stateless

No Stateful os endereços IP são atribuídos pelo roteador e registrados em logs que ficam salvos no mesmo, para que todas as vezes as interfaces utilizem o mesmo endereço sempre. Esta forma é a mais semelhante a usada no IPv4 e utiliza muito mais processamento e memória do roteador que o Stateless. Outro fator é que o Stateful não é compatível com todos os roteadores.

![[Untitled 1 9.png|Untitled 1 9.png]]

### NAT64 e DNS64

São serviços que operam em conjunto para que se faça possível o acesso de dispositivos IPv6 à internet IPv4. A função do NAT64 é converter pacotes em IPv4 para pacotes compatíveis com IPv6. Mas para isso ele requer que o DNS64 aponte o servidor DNS e o traduza para o IPv6. Já o DNSv6 é o responsável por traduzir os domínios em endereços IP e vice-versa, na versão 6 do Internet Protocol.

[https://www.youtube.com/watch?v=ZUWcLoK1gSQ&list=PLQq8-9yVHyObGmdqA-aD_QaLrZaC_tkOI&index=14](https://www.youtube.com/watch?v=ZUWcLoK1gSQ&list=PLQq8-9yVHyObGmdqA-aD_QaLrZaC_tkOI&index=14)

Já no Stateless o roteador não armazena os IPs atribuídos anteriormente em um log, mas indica o prefixo da rede e disponibiliza um local para as interfaces consultarem informações sobre a rede e suas configurações. No Stateless a atribuição de endereços é feita através do prefixo de rede e do MAC, juntamente com o EUI-64. O prefixo de rede (64 bits) é o mesmo para todas interfaces da rede e o EUI-64 tem a função de complementar o endereço MAC que contém apenas 48 bits. Essa complementação é feita da seguinte forma: O endereço MAC é dividido em 2 blocos de 24 bits e entre eles são colocados os caracteres hexadecimais FFFE de 16 bits, formando 64 bits, além da mudança do 7º bit para 1, apontando que a gestão deste endereço é feita de forma local.

### ICMPv6

No DHCPv6 o ICMP, atualmente ICMPv6 (Internet Control Message Protocol) assumiu a função de diversos outros protocolos e passou a não somente reportar erros, mas também a encaminhar informações entre a interface e o roteador, se tornando um dos protocolos mais importantes do IPv6.

O cabeçalho do ICMP é composto por 4 campos: Type (contendo 8 bits, determina a mensagem que o campo Data contém. Caso o valor deste campo seja 2, o tipo de mensagem será “Packet Too Big” que é a mensagem que reporta ao remetente que o MTU da rede não suporta o tamanho do pacote e que ele tem que ser fragmentado e reenviado), Code (contendo 8 bits, fornece avisos adicionais sobre a razão da mensagem. O valor 0 mostra que o envio do pacote não é possível por falta de rotas que tenham como objetivo o nó de destino), Checksum (contendo 16 bits, aponta erros no cabeçalho IPv6 ou no próprio cabeçalho do ICMPv6) e Data (podendo conter no máximo 1280 bits, contém a mensagem completa apresentando diagnósticos e informações de erros ou da própria rede).

Acontece que quando pensamos em IPv6 as coisas mudam bastante. Primeiro porque nativamente as redes IPv6 têm suporte ao processo de autoconfiguração stateless em que as próprias máquinas são capazes de formar seu endereço através de duas etapas: (i) a máquina determina seu identificador de host (sufixo) a partir do endereço físico da interface (MAC) e (ii) a máquina determina seu identificador de rede (prefixo) através de anúncios emitidos pelo roteador através de um protocolo de descoberta de vizinhança (NDP).

Por conta disso, via de regra, um servidor DHCP seria algo dispensável em redes IPv6 e agora o roteador da infraestrutura se torna um elemento ainda mais importante. Apesar disso, o DHCPv6 é definido na RFC 3315 e pode existir em duas modalidades: (i) _**stateful**_ e (ii) _**stateless**_.

A modalidade _**stateless**_ é aquela em que o servidor não mantém um registro dos endereços atribuídos aos clientes porque agora as máquinas irão formar automaticamente seu endereço a partir do endereço físico da interface de rede (MAC) e através dos anúncios dos prefixos dos roteadores. Nessa modalidade cabe ao servidor DHCPv6 informar apenas os endereços complementares, tais como: DNS e/ou Opções. Vale destacar que a funcionalidade _**stateless**_ émuito útil para informar automaticamente os servidores DNS da rede, afinal em IPv6 o serviço DNS é fundamental para amenizar a "complexidade" do endereço de 128 bits.

()

### Configuração Servidores DHCPv6 em Redes IPv6

Fonte : BRITO.BLOG LABCISCO. Servidores DHCPv6 em Redes IPv6. Disponível em: . Acesso em: 15 Dez. 2017.

![[Untitled 2 8.png|Untitled 2 8.png]]

**TÉCNICAS DE TRANSIÇÃO IPV6 - PARTE 03 (NAT64, DNS64 E 464XLAT)**

Utilizando mecanismo de tradução, com NAT64 e DNS64 é possível que usuários recebam apenas endereços IPv6 do provedor, mas acessem dispositivos IPv4 na Internet, disponível em: <[**www.youtube.com/watch?v=ZUWcLoK1gSQ**](https://www.youtube.com/watch?v=ZUWcLoK1gSQ)>. Acesso em 26/12/17.

Segundo Brito (2017) "Estamos falando de uma versão bastante simplificada do DHCP que não consome muitos recursos do "servidor" e que utiliza como base o processo de autoconfiguração! Para exemplificar como seria a configuração desse serviço, vamos observar o cenário da figura abaixo que é apenas uma reprodução da figura anterior num ambiente TCP/IPv6 em que temos a rede 2001:DB8:CAFE::/64."

Ainda em Brito (2017)" O processo de configuração do _**DHCPv6 Stateless**_ consiste em criar e configurar o "escopo" (linhas de 1 a 3), destacando que é importante ativar o serviço DHCPv6 na interface conectada à LAN que receberá os endereços dinâmicos (linha 7) e informar aos hosts que as informações complementares devem ser aprendidas pelo serviço DHCPv6 (linha 8), através da ativação da **flag O (**_**other-config-flag**_**)**."

1. 01. Router(config)# ipv6 dhcp pool NOME-ESCOPO
2. 02. Router(config-dhcp)# dns-server 2001:DB8:CAFE::2
3. 03. Router(config-dhcp)# domain-name labcisco.com.br
4. 03. Router(config-dhcp)# exit
5. 04. Router(config)# int f0/0
6. 05. Router(config-if)# ipv6 enable
7. 06. Router(config-if)# ipv6 address 2001:DB8:CAFE::1/64
8. 07. Router(config-if)# ipv6 dhcp server NOME-ESCOPO
9. 08. Router(config-if)# ipv6 nd other-config-flag
10. 09. Router(config-if)# end

De acordo com Brito ( 2017 ) "Embora não seja recomendado pela Cisco e nem todos os roteadores suportem, ainda existe uma versão stateful do DHCPv6 para aqueles que precisam manter o registro dos endereços dinamicamente atribuídos e que querem determinar o escopo explicitamente. Normalmente essa modalidade será empregada em servidores Linux e Windows Server. O processo de configuração do DHCPv6 Stateful no roteador ficaria:"

1. Router> enable
2. Router# configure terminal
3. Router(config)# ipv6 dhcp pool ESCOPO
4. Router(config-dhcp)# dns-server 2001:db8:cafe::2
5. Router(config-dhcp)# domain-name nome.com.br
6. Router(config-dhcp)# prefix-delegation pool ESCOPO lifetime 1800 600
7. Router(config-dhcp)# exit
8. Router(config)# interface fastEthernet 0/0
9. Router(config-if)# ipv6 enable
10. Router(config-if)# ipv6 address 2001:db8:cafe::1/64
11. Router(config-if)# ipv6 dhcp server ESCOPO
12. Router(config-if)# ipv6 nd other-config-flag
13. Router[config-if]\#exit
14. Router[config]# ipv6 local pool ESCOPO 2001:db8:cafe::/64 64
15. Router(config)#

17. Comando poderia ser utilizado para fins de verificação:

19. Router# show ipv6 dhcp pool

Reparem que agora tivemos que configurar na interface (linha 9) uma opção que instrui os clientes a receber todas as configurações de endereço via DHCPv6 (stateful), procedimento feito através da ativação da flag M (managed-config-flag). Além disso, na linha 2 o prefixo é explicitamente configurado