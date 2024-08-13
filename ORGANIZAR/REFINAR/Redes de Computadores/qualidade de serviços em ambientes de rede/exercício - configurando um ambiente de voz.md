**Antes de começar**

Observe atentamente a figura 01, na qual está construído o cenário. Como pode ser observado, agora temos dois switches para configurarmos. A ideia é mantê-los em contato. Iremos utilizar os mesmos processos vistos anteriormente, mas agora repetindo alguns passos para o SwitchA e para o SwitchB.

Também temos um número maior de telefones IP. Isso vai implicar em deliberarmos mais portas de comunicação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/3/119300/a18i01_quasar80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/1/9/3/119300/a18i01_quasar80_100.jpg)

Vale lembrar que nesta aula continuaremos a configurar:

1. Um gerenciador expresso de chamadas (Call Manager Express) em um roteador 2811.
2. Inserção de um número maior de telefones na rede.
3. Configuração desses equipamentos com dois switches.
4. Conexão desses telefones IP e seus testes na rede.

Outra informação importante, na figura 01, todos os telefones já estão conectados, mas para que você consiga uma configuração eficiente, o correto é inserir um telefone por vez. A partir do momento que esse telefone já tiver recebido pelo DHCP seu número IP e também o seu número de chamada, aí você realiza a conexão física do segundo telefone e assim sucessivamente.

**Configurando o ambiente de telefonia IP**

Siga os passos adiante:

1. Configurar a interface Fastethernet 0/0 e o serviço DHCP no roteador 2811:

```Shell
Router>en
Router\#conf t
Router(config)\#hostname RouterA
RouterA(config)\#interface FastEthernet0/0
RouterA(config-if)\#ip address 10.0.0.1 255.0.0.0
RouterA(config-if)\#no shutdown
  
# O Servidor DHCP precisa de um endereço IP e um Servidor de locação TFTP para cada telefone IP conectado na rede.   
RouterA(config-if)\#exit
RouterA(config)\#interface vlan 1
RouterA(config-if)\#no shutdown
RouterA(config-if)\#exit
  
# O próprio roteador servirá como servidor DHCP, e para o CME é preciso que você forneça o IP do servidor TFTP para que os telefones possam buscar seu firmware e arquivos de configuração. Isso é feito com a opção 150 do DHCP. 
RouterA(config)\#ip dhcp pool VOICE \#Para criar  DHCP pool chamado VOICE
RouterA(dhcp-config)\#network 10.0.0.0 255.0.0.0 
RouterA(dhcp-config)\#default-router 10.0.0.1
RouterA(dhcp-config)\#option 150  ip  10.0.0.1
RouterA(dhcp-config)\#exit
# Após essas configurações acima, aguarde um instante e verifique se o telefone IP recebeu um número IP.
```

2. Configurar a interface Fastethernet 0/0 e o serviço DHCP no roteador 2811:

```Shell
RouterA(config)\#telephony-serice \#Configurando o roteador para serviços de telefone
RouterA(config-telephony)\#max-dn 10
RouterA(config-telephony)\#max-ephones 10 \#Define o número máximo de telefones
RouterA(config-telephony)\#ip source-address 10.0.0.1 port 2000
RouterA(config-telephony)\#auto assign 1 to 10
RouterA(config-telephony)\#exit
RouterA(config)\#exit
RouterA#

# Os comandos básicos e obrigatórios para configurar o CME estão dentro do modo de configuração do telephony-service
# O max-dn define o número máximo de linhas que você obterá, jáo max-ephones define o máximo de telefones físicos que você
# terá cada modelo de roteador permite um número máximo de telefones IP para o CME

# O comando "ip source-address 10.0.0.1 port 2000? define
# que o roteador 10.0.0.1 será o responsável pelo registro dos telefones através da porta 2000
```

3. Configurar um VlanVoice no Switch A para separar o sistema de voz em relação ao tráfego de dados. Nesse caso, vamos utilizar apenas a Vlan 1, mas se tivéssemos dados trafegando, aí sim criaríamos também a Vlan 2 para separar esses dois tráfegos.

```Shell

Switch>en
Switch\#conf t
Switch(config)\#hostname SwitchA
SwitchA(config)\#interface vlan 1
SwitchA(config-if)\#no shutdown
SwitchA(config-if)\#exit
SwitchA(config)\#interface range fa0/1 – 7 
SwitchA(config-if-range)\#switchport mode access
SwitchA(config-if-range)\#switchport voice vlan 1
SwitchA(config-if-range)\#exit
SwitchA(config)\#exit
SwitchA#
```

4. Repetir o mesmo processo para o SwitchB.

```Shell

Switch>en
Switch\#conf t
Switch(config)\#hostname SwitchB
SwitchB(config)\#interface vlan 1
SwitchB(config-if)\#no shutdown
SwitchB(config-if)\#exit
SwitchB(config)\#interface range fa0/1 – 7 
SwitchB(config-if-range)\#switchport mode access
SwitchB(config-if-range)\#switchport voice vlan 1
SwitchB(config-if-range)\#exit
SwitchB(config)\#exit
SwitchB#
```

5. Configurar o "phone directory" para o IP Phone 1, necessitando também configurar o CME do RouterA para associar o número do telefone com este outro.

```Shell
RouterA\#conf t
RouterA(config)\#ephone-dn 1 
RouterA(config-ephone-dn)\#number 54001 
RouterA(config-ephone-dn)\#exit 
RouterA(config)\#exit
RouterA#
```

6. Repetir os passos anteriores para que seja possível atribuir um número de telefone para cada equipamento, tanto os que estão interligados no SwitchA como os que estão interligados no SwitchB. Por exemplo:

```Shell
RouterA\#conf t
RouterA(config)\#ephone-dn 2 
RouterA(config-ephone-dn)\#number 54002 
RouterA(config-ephone-dn)\#exit 
RouterA(config)\#exit
RouterA#
# Assim, sucessivamente para todos os telefones.
```

7. Agora é só confirmar a configuração. Certifique-se de que o telefone IP recebeu um IP e o número do telefone 54001, vindo do RouterA (coloque apenas o mouse sobre o telefone IP).  
8. Repita o passo 7 para todos os outros telefones interconectados.