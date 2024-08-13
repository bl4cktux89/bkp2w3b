Introdução  
A adoção de um protocolo capaz de garantir a intergridade dos dados, incluindo os endereços de origem e destino por onde trafegam os dados, garantem a confidencialidade dos dados, sendo essa uma das caracteristicas do protocolo IPsec, técnicas de tunelamento, garantem que os nós da Rede, independente da versão de seus protocolos, a entrega é garantida em uma rede fim a fim ou ponto a ponto, faz com que esse protocolo, seja eleito para ser usado como uma técnica de tunelamento.  

De acordo com o Hansem (2013) a arquitetura básica do IPsec é composta por dois protocolos:

AH (Authentication Header): orientado a conexão, é responsável pela autenticação da origem dos dados  
ESP (Encapsulation Security Payload): responsável pela criptografia dos dados.  
Apesar de complementares foram desenvolvidos para atuar de forma independente, suas principais utilizações e operação:  

Modo Transporte: promovem a proteção dos protocolos de camadas superiores

Modo Túnel: responsável pelo tunelamento dos pacotes IP.

Destinado principalmente a interligar redes de pesquisa acadêmicas, o projeto original do IPv4 não apresentava nenhuma grande preocupação com questões relacionadas à segurança das informações transmitidas. No entanto, o aumento da importância da Internet para a realização de transações entre empresas e consumidores, por exemplo, fez com que um nível maior de segurança passasse a ser exigido, como identificação de usuários e criptografia de dados, tornando necessário anexar novos mecanismos ao protocolo original, que garantissem tais serviços. O IPsec foi criado para suprir esta deficiência. Ele é uma suíte de protocolos que atua como extensão do protocolo IP e oferece serviços de segurança para prover autenticidade, integridade e confidencialidade aos pacotes IP. Os serviços são providos na camada de rede e, portanto, também oferecem proteção às camadas superiores.

(Laboratório de IPv6 Aprenda na prática usando um emulador de redes)  
Outro ponto fundamental para o funcionamento do IPsec é o compartilhamento das chaves utilizadas para autenticação e criptografia. Recomendase a utilização do protocolo IKE (Internet Key Exchange) para garantir um meio seguro para a troca das chaves entre os dispositivos que utilizam IPsec e essa troca pode ocorrer de dois modos: mediante o uso de chaves pré-compartilhadas; e da utilização de certificados X.509. O protocolo IKE trabalha em duas fases:  

1. Por meio de uma série de mensagens trocadas, a autenticidade dos dispositivos é verificada e uma chave ISAKMP SA (Internet Security Association Key Management Security Association) é gerada.
2. A partir da chave ISAKMP SA, as chaves para o AH e ESP para esta comunicação são geradas e o IPsec começa a ser utilizado.

(LABORATÓRIO DE IPV6 APRENDA NA PRÁTICA USANDO UM EMULADOR DE REDES)

![[Untitled 29.png|Untitled 29.png]]

### Aplicação prática do IPsec modo Túnel

Imagine uma empresa com diversas unidades espalhadas pelo mundo. Para garantir a privacidade da comunicação, a primeira coisa que nos vem a cabeça é a contratação de um link de comunicação privada, mas imagina o custo para manter um link exclusivo entre São Paulo e Paris por exemplo, é totalmente inviável. A solução está em estabelecer uma VPN (_**Virtual Private Network**_ _**-**_ _**VPN**_) entre a unidade de São Paulo e Paris utilizando a infraestrutura pública da internet, que passa então a ser uma espécie de backbone virtual da empresa, gerando uma redução significativa de custos, bem como a segurança dos dados, garantidas pelo protocolo IPsec.

Implementando a VPN IPsec nos roteadores e criando o tunelamento

![[Untitled 1 19.png|Untitled 1 19.png]]

**Acessando os roteadores R1 e R3 e executando o comando** _**show version**_ **para verificar licencas ativadas no hardware**

### Verificando o Router 1

R1>

R1>enable

R1# show version

### Verificando o Router 3

R3>

R3>enable

R3# show version

![[Untitled 2 17.png|Untitled 2 17.png]]

**Habilitando a licença de  VPN no roteador R1**

`1.` `R1>enable` `2.` `R1\#configure terminal` `3.` `R1(config)#` `4.` `R1(config)# license boot module c2900 technology-package securityk9` `5.` `R1(config)# end` `6.` `R1# copy running-config startup-config` `7.` `R1# reload` `8.` `9.` `\#Os comandos acima ativaram a licença no Roteador R1 e reiniciam o equipamento`

**Habilitando a licença de  VPN no roteador R3**

`1.` `R3>enable` `2.` `R3\#configure terminal` `3.` `R3(config)#` `4.` `R3(config)# license boot module c2900 technology-package securityk9` `5.` `R3(config)# end` `6.` `R3# copy running-config startup-config` `7.` `R3# reload` `8.` `\#Os comandos acima ativaram a licença no Roteador R3 e reiniciam o equipamento`

**Ativação da Licença de VPN no Roteador**

![[Untitled 3 11.png|Untitled 3 11.png]]

**Habilitando as configurações de VPN (**_**Virtual Private Net**__**work**_**) no Router 1**

`1.` `R1>enable` `2.` `R1\#configure terminal` `3.` `R1(config)# access-list 110 permit ip 192.168.1.0 0.0.0.255 192.168.3.0 0.0.0.255` `4.` `R1(config)# crypto isakmp policy 10` `5.` `R1(config-isakmp)# encryption aes` `6.` `R1(config-isakmp)# authentication pre-share` `7.` `R1(config-isakmp)# group 2` `8.` `R1(config-isakmp)# exit` `9.` `R1(config)# crypto isakmp key cisco address 10.2.2.2` `10.` `R1(config)# crypto ipsec transform-set VPN-SET esp-3des esp-sha-hmac` `11.` `R1(config)# crypto map VPN-MAP 10 ipsec-isakmp` `12.` `R1(config-crypto-map)# description VPN connection to R3` `13.` `R1(config-crypto-map)# set peer 10.2.2.2` `14.` `R1(config-crypto-map)# set transform-set VPN-SET` `15.` `R1(config-crypto-map)# match address 110` `16.` `R1(config-crypto-map)# exit` `17.` `R1(config)# interface S0/0/0` `18.` `R1(config-if)# crypto map VPN-MAP` `19.` `R1(config-if)# end` `20.` `R1# copy running-config startup-config`

**Habilitando as configurações de VPN (**_**Virtual Private Network**_**) no Router 3**

`1.` `R3>enable` `2.` `R3\#configure terminal` `3.` `R3(config)# access-list 110 permit ip 192.168.3.0 0.0.0.255 192.168.1.0 0.0.0.255` `4.` `R3(config)# crypto isakmp policy 10` `5.` `R3(config-isakmp)# encryption aes` `6.` `R3(config-isakmp)# authentication pre-share` `7.` `R3(config-isakmp)# group 2` `8.` `R3(config-isakmp)# exit` `9.` `R3(config)# crypto isakmp key cisco address 10.1.1.2` `10.` `R3(config)# crypto ipsec transform-set VPN-SET esp-3des esp-sha-hmac` `11.` `R3(config)# crypto map VPN-MAP 10 ipsec-isakmp` `12.` `R3(config-crypto-map)# description VPN connection to R1` `13.` `R3(config-crypto-map)# set peer 10.1.1.2` `14.` `R3(config-crypto-map)# set transform-set VPN-SET` `15.` `R3(config-crypto-map)# match address 110` `16.` `R3(config-crypto-map)# exit` `17.` `R3(config)# interface S0/0/1` `18.` `R3(config-if)# crypto map VPN-MAP` `19.` `R3(config-if)# end` `20.` `R3# copy running-config startup-config`

**Análise e teste da VPN**

![[Untitled 4 11.png|Untitled 4 11.png]]

Análise e teste de traceroute na VPN

Ao utilizarmos o comando _**Tracert**_, para verificar a rota que os pacotes fazem, nota-se um salto referente ao Router 3.

![[Untitled 5 10.png|Untitled 5 10.png]]

Acessando o roteador R1 podemos utilizar o comando: _**show crypto ipsec sa**_, este comando refere-se ao o número de pacotes encapsulados de modo seguro.

O objetivo desse tópico, foi apresentar o funcionamento protocolo IPsec modo túnel, através da interligação entre matriz e filial, de forma teórica e prática, justifica-se ao apresentar um cenário de VPN entre três roteadores suportando IPsec entre os enlaces, onde o tráfego que flui entre dois sites, não é reconhecido pelo roteador central, que transfere de modo transparente o tráfego, uma vez que IPsec proporciona uma configuração segura, já que a confidencialidade dos dados é garantida entre os participantes da topologia _**Site-to-Site**_ pelo IPsec  no modo túnel, atuando nas camadas superiores da rede,melhorando sua performance, protegendo e autenticando o tráfego entre a origem e o destino.

Por meio de uma série de mensagens trocadas, a autenticidade dos dispositivos é verificada e uma chave ISAKMP SA (_**Internet Security Association Key Management Security Association**_) é gerada.