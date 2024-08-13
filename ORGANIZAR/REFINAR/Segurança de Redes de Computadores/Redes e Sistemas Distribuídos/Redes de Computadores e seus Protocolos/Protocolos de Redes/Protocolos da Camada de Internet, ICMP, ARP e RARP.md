[![](https://ampli-images.s3.amazonaws.com/production/6e3147c1-c59a-42d5-a569-e29bd93766bd/original)](https://ampli-images.s3.amazonaws.com/production/6e3147c1-c59a-42d5-a569-e29bd93766bd/original)

De acordo com Tanenbaum (2011, p. 222), a camada de inter-rede ou Internet Layer ou, ainda, Rede, está relacionada à transferência de pacotes da origem para o destino. Ela é responsável por reconhecer a topologia da rede, escolher os caminhos mais apropriados para entrega dos pacotes entre hosts na rede e também pela definição do endereçamento de um host de rede por meio do endereço de rede. A exemplo do endereçamento realizado pelo TSAP na camada de transporte, na camada de inter-rede um endereço de rede é dado pelo chamado NSAP, exemplificados pelo endereço IP (_Internet Protocol_), responsável pelo endereçamento de hosts na rede de forma prática. Os principais protocolos da camada de inter-rede são:

**IP (**_**Internet Protocol**_**)**

Protocolo mais conhecido de camada de inter-rede, uma vez que é o responsável pelo endereçamento lógico dos hosts de rede, informado pelo profissional de tecnologia da informação ou mesmo pelo usuário para identificação única do _host_ dentro de um segmento de rede.

Faz-se importante saber que, para que um computador ou dispositivo possa fazer parte de uma rede, ele, obrigatoriamente, necessita ser configurado recebendo um endereço IP válido no segmento de rede. Esses endereços também podem ser atribuídos de forma automática de rede, com um servidor de endereços IPs ativo em um sistema operacional de rede, como o DHCP.

O protocolo IP é utilizado em duas versões disponíveis: _Internet Protocol 4_ (IPv4) e I_nternet Protocol 6_ (IPv6), ambas ativas e com possibilidades de utilização conforme políticas de atribuição de endereços que serão estudadas na Unidade 2 deste livro. A figura abaixo apresenta a configuração de um endereço de IPv4 estático em um ambiente Windows.

[![](https://ampli-images.s3.amazonaws.com/production/d98f67a7-a50d-4744-a669-0757a34b453c/original)](https://ampli-images.s3.amazonaws.com/production/d98f67a7-a50d-4744-a669-0757a34b453c/original)

Exemplo de configuração de conta em e-mail via protocolo POP3. Fonte: captura de tela elaborada pelo autor.

**ICMP**

Protocolo utilizado para gerenciar os erros de processamento de datagramas do protocolo IP. Esse protocolo é exemplificado por: _buffer full_, que indica se um _buffer_ atingiu sua capacidade máxima de processamento; _hops_, que mostra quantos saltos são necessários para que uma mensagem chegue ao destino; ping, que identifica se a interface de rede é ativa por meio de um teste; e _traceroute_ (Linux) ou _tracert_ (Windows), que mapeia os saltos e traz informações sobre o tempo entre nodos de rede e seus nomes.

Esses são comandos que podem ser utilizados para a operação de testes e análises de rede com o protocolo ICMP. Um exemplo de utilização desse protocolo é a utilização do comando _tracert 8.8.8.8_ apresentado na figura abaixo, em que o endereço IP 8.8.8.8 é do Google e o retorno do comando apresenta dados do rastreamento da rota para o servidor **dns.google**.

[![](https://ampli-images.s3.amazonaws.com/production/0714433b-3fa6-4b4d-8064-ebe0b46d746b/original)](https://ampli-images.s3.amazonaws.com/production/0714433b-3fa6-4b4d-8064-ebe0b46d746b/original)

Exemplo de utilização de tracert. Fonte: captura de tela elaborada pelo autor.

**ARP**

Protocolo que reconhece o endereço físico de uma placa de rede, chamado _Media Access Control_ (MAC) por meio de seu endereço IP. Exemplo: para se verificar o mapeamento dos endereços MAC e IP, é possível digitar arp -a no prompt de comando.

**RARP**

Protocolo que reconhece o endereço lógico de uma rede, ou seja, reconhece o endereço IP por meio de um endereço MAC.

______

**📝****Exemplificando**

As redes de computadores são organizadas em camadas dentro do modelo de referência OSI e/ou TCP/IP. Em cada camada dos modelos de referência, os dados transferidos possuem endereços para que a informação possa ser transmitida de um host de origem para um host de destino. Dispositivos conectados em rede possuem um endereço MAC atribuído à camada do TCP/IP de Host de rede gravado em uma placa de rede como endereço físico e único, formado por uma sequência de seis dígitos em formato hexadecimal. Exemplo: 00-14-CE-5B-3A-93.

Já o endereço IP é um endereço lógico, de camada de inter-rede, atribuído manualmente ao host ou por meio de um servidor DHCP de um serviço de rede. Um IPv4 é um endereço de 32 bits constituído por um conjunto de 4 números decimais que representam quatro números binários de 8 bits cada. Exemplo de IPv4 é 192.168.15.12. Na versão IPv6, ele é representando por um conjunto de 128 bits. Exemplo: 835C:5B9D:BC27:0000:0000:0000:C4B8:1FBB.

______

Outros protocolos de camada de inter-rede são utilizados para o trabalho de roteamento interno e externo de pacotes em rede, operando-se em roteadores. Alguns exemplos desses protocolos são: _Routing Information Protocol_ (RIP), _Open Shortest Path First_ (OSPF), Interior _Gateway Routing Protocol_ (IGRP), _Enhanced Interior Gateway Routing Protocol_ (EIGRP) e _Border Gateway Protocol_ (BGP).