### Introdução

A técnica ou processo NAT (Network Address Translation, Tradução de endereço de rede) foi criada com objetivo de fazer exatamente o que o nome sugere: traduzir um endereço IP para o outro. essa técnica possui várias aplicações, mas a principal delas, seja, certamente, a tradução de um endereço IP privado para um endereço IP público.  Os endereços IPs privados foram definidos pela RFC 1918 e são atribuídos aos dispositivos que estão dentro de uma rede local (LAN), mas que não fazem parte da Internet. Mas para que tais dispositivos acessem a internet é necessário traduzir o seu endereço IP privado para o público, ou roteado globalmente, conforme descrito a seguir a partir da figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/7/5/1637558/38559.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/7/5/1637558/38559.png)

Fonte:

O PC1 que possui o endereço IP privado 192.168.10.10 deseja enviar uma mensagem para o servidor localizado na internet. Para tanto, o endereço IP privados deve ser traduzido para que possa ser roteado na internet. Essa tarefa fica cargo de um dispositivo de borda como, por exemplo, um roteador ou um firewall. O pacote ao chegar ao dispositivo de borda recebe um novo endereço IP (Público) por meio de uma das diferentes técnicas NAT que serão mostradas mais adiante. Na sequência, o pacote pode ser roteado na internet e chegar ao servidor. Quando o servidor responder a requisição, o pacote passará novamente pelo dispositivo de borda que fará o processo contrário, convertendo o endereço IP público para privado.

Possivelmente, muitos de vocês já viram um endereço IP semelhante a 192.168.0.1. Por que esse endereço IP é tão utilizado? A RFC 1918 definiu três faixas de endereços privados, conforme mostrado na tabela abaixo. A faixa compreendida entre 192.168.0.0 a 192.168.255.255 é a mais utilizada, pois fornece, como todo endereço classe C, apenas 254 IPs validos, suficiente para a maioria parte das redes, principalmente as redes residências (Tanenbaum, Andrew S e Wetherall, 2011).

![[Untitled 37.png|Untitled 37.png]]

### Motivação para o desenvolvimento do NAT

A principal motivação está associada, sem dúvida nenhuma, com a escassez de endereços IPv4, que possui um total aproximado de 4,29 bilhões de endereços IPs. Parece muito, mas acabou nos últimos anos. Além disso, proporciona segurança, já que o endereço IP que passou pelo NAT é mascarado para o mundo externo, ou seja, o seu verdadeiro endereço IP não é divulgado. Entretanto, a introdução dessa técnica introduz um delay (atraso) na transmissão e também requer maiores recursos de memória e processamento.

Apesar da implementação bem sucedida do NAT em pequenas redes, a sua implementação em redes com grandes tráfegos de dados é praticamente inviável, em virtude de das grandes tabelas geradas e dos recursos de hardware requeridos. Soma-se a isso, o fim dos endereços IPs públicos disponíveis. Por esses motivos, a criação de uma nova arquitetura de endereço IP (IPv6) tornou-se necessária (Kurose, James F e Ross, W. Keith, 2013).

### Terminologia NAT

O NAT define uma terminologia particular para auxiliar na descrição do processo de tradução.  e que é descrita abaixo (Filippetti, Marco. A., 2017):

- **Endereço interno local:** Endereço IP de um dispositivo localizado dentro do domínio interno, visto como da mesma forma do que qualquer outro dispositivo pertencente a esse domínio.
- **Endereço interno Global:** endereço IP de um dispositivo localizado no domínio interno”, visto por um host localizado no domínio externo.
- **Endereço externo local:** Endereço IP de um dispositivo localizado no domínio externo da forma com que os dispositivos pertencentes ao domínio interno o enxerga.
- **Endereço externo global:** Endereço IP de um dispositivo pertencente ao domínio externo global, da forma com que os outros dispositivos desse mesmo domínio o enxerga.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/7/7/1637714/38561.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/7/7/1637714/38561.png)

### Tipos de NAT

Existem diferente tipos de tradução de endereços de rede, conforme descrito abaixo (Filippetti, Marco. A., 2017):

- **NAT estático:** Consiste no mapeamento de um endereço local para um endereço global. Neste caso o endereço IP sempre será traduzido apenas para o endereço IP definido. Este tipo de NAT é útil quando se deseja acessar, por exemplo, um servidor via SSH que está dentro da rede local por meio de uma rede externa, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/8/4/1638429/38570.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/8/4/1638429/38570.png)

Fonte:

- **NAT dinâmico:** Neste caso, o NAT provê um mapeamento dinâmico de um intervalo de endereços chamados de pool de endereços públicos disponíveis para tradução e os atribui de acordo com a ordem de chegada, conforme mostrado na figura abaixo. Essa técnica exige que exista endereços IPs públicos em número suficiente para satisfazer as solicitações internas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/4/2/3/1642338/38571.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/4/2/3/1642338/38571.png)

Fonte: Cisco Systens

- **NAT dinâmico com overloading:** Essa técnica permite que seja feita a tradução muitos endereços IPs privados para alguns endereços IPs públicos, ou até mesmo, trazendo para um único endereço IP público. Isso é possível em virtude da substituição de endereços IP e do endereço de porta da camada de transporte que identifica cada aplicação de origem e destino. O NAT armazena em sua tabela de traduções o valor da porta de origem juntamente com o endereço IP público que está sendo alterado.
- **PAT (Port Address Translation, Tradução de endereço de Porta):** Além da troca de endereços IPs, a técnica PAT altera também o endereço de porta da camada de transporte.

### Aplicações NAT - Estático

No cenário abaixo temos duas redes internas com o mesmo endereço de rede privada 192.168.0.0 interligadas por meio de roteadores com endereço de rede igual a 10.10.10.0 /30. Precisamos interligar as duas redes, mas é de se observar as redes internas possuem o mesmo endereço de rede. Por definição roteadores não roteiam um pacote para o mesmo endereço de rede da rede de origem. A técnica NAT permite resolver essa questão, já que ela permite a tradução de qualquer endereço, não apenas privado para público, mas também privado para privado. Isso pode acontecer em caso de junção de redes, onde o administrador pode alterar o endereço de rede uma das redes por questões de compatibilidade e migração.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/8/0/1758091/38572.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/5/8/0/1758091/38572.jpg)

**Solução**

A solução para o cenário acima poderia utilizar a técnica NAT com estático. Os comandos para tanto são mostrados abaixo.

O NAT estático, como já comentado é uma tradução de um endereço IP para um único endereço IP. No cenário abaixo, vamos traduzir o endereço 192.168.0.2 (interno local) na rede da esquerda para o endereço IP 40.0.0.40 (interno global). Da mesma forma, o endereço IP 192.168.0.2 (interno local) localizado na rede da direita será traduzido para o interno global 50.0.0.50.

O primeiro passo consiste em definir os endereços IPs nas interfaces (linhas 1 e 8) e indicar como interface interna (Inside) e externa (outside), como mostrado na linha 6 e 10. A tradução é feita pelo comando mostrado na linha 12. O próximo passo é inserir uma rota padrão (linha 13) para que o pacote da rede interna seja roteado para fora. Por exemplo, se um pacote chegar a interface do roteador da direita com destino ao IP 50.0.0.50, ele será enviado para a interface 10.10.10.2. De forma análoga ocorrerá no roteador da direita.

**Configuração do NAT no Roteador A**

`1.` `RouterA> enable` `2.` `RouterA# configure terminal` `3.` `RouterA(config)# interface f0/0` `4.` `RouterA(config-if)\#ip address 192.168.0.1 255.255.255.0` `5.` `RouterA(config-if)\#no shutdown` `6.` `RouterA(config-if)#ip nat inside` `7.` `RouterA(config-if)# interface f1/0` `8.` `RouterA(config-if)# ip address 10.10.10.1 255.255.255.252` `9.` `RouterA(config-if)#no shutdown` `10.` `RouterA(config-if)#ip nat outside` `11.` `RouterA(config-if)\#exit` `12.` `RouterA(config)#ip nat inside source static 192.168.0.2 40.0.0.40` `13.` `RouterA(config)#ip route 50.0.0.0 255.0.0.0 10.10.10.2` `14.` `RouterA(config)\#end` `15.` `RouterA# copy run start`

**Configuração do NAT no Roteador B**

`1.` `RouterB> enable` `2.` `RouterB# configure terminal` `3.` `RouterB(config)# interface f0/0` `4.` `RouterB(config-if)\#ip address 10.10.10.2 255.255.255.252` `5.` `RouterB(config-if)\#no shutdown` `6.` `RouterB(config-if)#ip nat outside` `7.` `RouterB(config-if)# interface f1/0` `8.` `RouterB(config-if)# ip address 192.168.0.1 255.255.255.0` `9.` `RouterB(config-if)#no shutdown` `10.` `RouterB(config-if)#ip nat inside` `11.` `RouterB(config-if)\#exit` `12.` `RouterB(config)#ip nat inside source static 192.168.0.2 50.0.0.50` `13.` `RouterB(config)#ip route 40.0.0.0 255.0.0.0 10.10.10.1` `14.` `RouterB(config)\#end` `15.` `RouterB# copy run start`

### Aplicações NAT - Overloading

Para mostrar o funcionamento do NAT overloading utilizaremos a topologia abaixo, composta de uma rede interna com endereços 192.168.0.0 /24 conectada à internet por meio de um roteador com IP externo 200.200.200.1. Para testar essa configuração colocaremos um computador na internet.

**Solução**

A primeira coisa que deve ser feita é criar uma lista de controle de acesso ACL. Uma ACL, como o próprio nome diz, controla o acesso de hosts e redes por meio de regras permissivas, negando ou permitindo a passagem do tráfego. No exemplo abaixo, criamos uma ACL que permite _**(permit)**_ apenas a passagem do tráfego da rede 192.168.0.0 /24. o endereço 0.0.0.255 é chamada de máscara curinga ou máscara invertida. A máscara de sub-rede é igual a 255.255.255.0 /24, o que devemos fazer para descobrir a máscara coringa é desligar os bits 1s e ligar os bits 0s da máscara, portanto, desligamos 24 primeiros bits e ligamos os demais, resultando em 0.0.0.255. O próximo passo consiste em criar o NAT propriamente dito por meio do comando da linha x, onde associamos a ACL criada ao NAT. isso permite que apenas os pacotes que passarem pela ACL sejam traduzidos.

`1.` `RouterB> enable` `2.` `RouterB# configure terminal` `3.` `RouterB(config)# interface f0/0` `4.` `RouterB(config-if)\#ip address 10.10.10.2 255.255.255.252` `5.` `RouterB(config-if)\#no shutdown` `6.` `RouterB(config-if)#ip nat outside` `7.` `RouterB(config-if)# interface f1/0` `8.` `RouterB(config-if)# ip address 192.168.0.1 255.255.255.0` `9.` `RouterB(config-if)#no shutdown` `10.` `RouterB(config-if)#ip nat inside` `11.` `RouterB(config-if)\#exit` `12.` `RouterB(config)#ip nat inside source static 192.168.0.2 50.0.0.50` `13.` `RouterB(config)#ip route 40.0.0.0 255.0.0.0 10.10.10.1` `14.` `RouterB(config)\#end` `15.` `RouterB# copy run start`

`1.` `Router> enable` `2.` `Router# configure terminal` `3.` `Router(config)# interface f0/0` `4.` `Router(config-if)\#ip address 192.168.0.1 255.255.255.0` `5.` `Router(config-if)\#no shutdown` `6.` `Router(config-if)#ip nat inside` `7.` `Router(config-if)# interface f1/0` `8.` `Router(config-if)# ip address 200.200.200.1 255.255.255.252` `9.` `Router(config-if)#no shutdown` `10.` `Router(config-if)#ip nat outside` `11.` `Router(config-if)\#exit` `12.` `Router(config)\#access-list 1 permit any` `13.` `Router(config)\#iip nat inside source list 1 interface FastEthernet1/0 overload` `14.` `Router(config)\#end` `15.` `Router# copy run start`

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/4/2/3/1642382/38579.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/4/2/3/1642382/38579.png)