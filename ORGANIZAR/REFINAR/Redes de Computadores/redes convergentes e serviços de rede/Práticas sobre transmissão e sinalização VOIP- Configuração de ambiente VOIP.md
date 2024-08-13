A proposta dessa aula é uma atividade prática: construir uma rede VOIP, utilizando os comandos no simulador Packet tracer, e destacar as principais portas e troca de sinalização da tecnologia VOIP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/4/1/324175/21906.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/4/1/324175/21906.png)

Cenário do Laboratório VOIP

Fonte: Elaborado pelo professor conteudista.

### Objetivo geral

Nesse laboratório, o objetivo é construir um cenário com um roteador Cisco 2811, que será o servidor DHCP ( Dynamic Host Configuration Protocol) que distribuirá os números IPs automáticamente.Observe atentamente o cenário Voip. Nesse cenário temos dois switches 2950-T, nos quais vamos configurar as Vlans ( Virtual Lan) de voz, que serão chamadas VLAN VOICE. O objetivo é configurar os telefones Voip 7960 disponíveis em nosso cenário e realizar uma chamada de um ramal para o outro.

Nesse laboratório vamos configurar no Router 2811,um IPBX, habilitado pelo Cisco CallManager (CCM), que é um software gestor de chamadas desenvolvido pela Cisco Systems.

1. Habilitar a licença do (Call Manager Express) em um roteador 2811.
2. Inserção telefones VOIP na rede.
3. Configuração desses equipamentos com dois switches.
4. Conexão desses telefones IP e seus testes na rede.

### Vamos em frente !!!

Outra informação importante, no cenário VOIP, todos os telefones já estão conectados, mas para que você consiga uma configuração eficiente, o correto é inserir um telefone por vez e somente ligar a fonte dos telefones ao final da configuração. A partir do momento que esse telefone já obtiver  adequadamente seu numero IP recebido DHCP e também o seu número de chamada, podemos realizar a conexão física do segundo telefone e assim sucessivamente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/1/3/11331/i16_546.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/1/3/11331/i16_546.jpg)

Telefone IP

**Configuração do Cenário VOIP ( Voice over Internet Protocol )**

1. Configurar a interface FastEthernet 0/0 e o serviço DHCP no Roteador 2811:

`1.` `Router>enable` `2.` `Router\#configure terminal` `3.` `Router(config)# hostname Router_A` `4.` `RouterA(config)\#interface FastEthernet0/0` `5.` `RouterA(config-if)\#ip address 10.0.0.1 255.0.0.0` `6.` `RouterA(config-if)\#no shutdown` `7.` `RouterA(config-if)\#exit` `8.` `RouterA(config)#interface vlan 1` `9.` `RouterA(config-if)#no shutdown` `10.` `RouterA(config-if)#exit` `11.`   `12.` `Obs.: # O Servidor DHCP precisa de um endereço IP e um Servidor de locação TFTP para cada telefone IP conectado na rede.`

`1.` `RouterA(config)\#ip dhcp pool VOICE` `2.` `RouterA(dhcp-config)\#network 10.0.0.0 255.0.0.0` `3.` `RouterA(dhcp-config)\#default-router 10.0.0.1` `4.` `RouterA(dhcp-config)\#option 150 ip 10.0.0.1` `5.` `RouterA(dhcp-config)\#exit` `6.` `RouterA# Write` `7.` `# Após essas configurações acima, aguarde um instante e verifique se o telefone IP recebeu um número IP.` `8.` `# O próprio roteador servirá como servidor DHCP, e para o CME ( Call Manager Express) é preciso que você forneça o IP do servidor TFTP para que os telefones possam buscar seu firmware e arquivos de configuração. Isso é feito com a opção 150 do DHCP.` `9.` `# O comando Ip dhcp pool VOICE \#Para criar DHCP pool chamado VOICE`

2. Configure o "Call Manager Express", serviço de telefone, no RouterA para habilitar o serviço VOIP na Rede.

`1.` `RouterA(config)\#telephony-service \#Configurando o roteador para serviços de telefone#` `2.` `RouterA(config-telephony)\#max-dn 10` `3.` `RouterA(config-telephony)\#max-ephones 10 \#Define o número máximo de telefones#` `4.` `RouterA(config-telephony)\#ip source-address 10.0.0.1 port 2000` `5.` `RouterA(config-telephony)\#auto assign 1 to 10` `6.` `RouterA(config-telephony)\#exit` `7.` `RouterA(config)#exit` `8.` `RouterA\#write`

`1.` `# Os comandos básicos e obrigatórios para configurar o CME estão dentro do modo de configuração do telephony-service. O Max-dn define o número máximo de linhas que você obterá, já o max- ephones define o máximo de telefones físicos que você terá. Cada modelo de roteador permite um número máximo de telefones IP para o CME.` `2.` `# O comando "ip source-address 10.0.0.1 port 2000?define que o roteador 10.0.0.1 será o responsável pelo registro dos telefones através da porta 2000.`

`1.` `Configurar um VlanVoice no Switch A para separar o sistema de voz em relação ao tráfego de dados. Nesse caso, vamos utilizar apenas a Vlan 1, mas se tivéssemos dados trafegando, aí sim criaríamos também a Vlan 2 para separar esses dois tráfegos.`

3. Configurar uma Vlan Voice no Switch A para separar o tráfego de voz na Vlan.

`1.` `Switch>enable` `2.` `Switch\#configure terminal` `3.` `Switch(config)\#hostname Switch_A` `4.` `SwitchA(config)\#interface vlan 1` `5.` `SwitchA(config-if)\#no shutdown` `6.` `SwitchA(config-if)\#exit` `7.` `SwitchA(config)#interface range fa0/1 –7` `8.` `SwitchA(config-if-range)\#switchport mode access` `9.` `SwitchA(config-if-range)#switchport voice vlan 1` `10.` `SwitchA(config-if-range)#exit` `11.` `SwitchA(config)#exit` `12.` `SwitchA\#write`

4. Repetir o mesmo processo para o SwitchB.

`1.` `Switch>enable` `2.` `Switch\#configure terminal` `3.` `Switch(config)\#hostname Switch_B` `4.` `SwitchB(config)\#interface vlan 1` `5.` `SwitchB(config-if)\#no shutdown` `6.` `SwitchB(config-if)\#exit` `7.` `SwitchB(config)#interface range fa0/1 –7` `8.` `SwitchB(config-if-range)\#switchport mode access` `9.` `SwitchB(config-if-range)#switchport voice vlan 1` `10.` `SwitchB(config-if-range)#exit` `11.` `SwitchB(config)#exit` `12.` `SwitchB\#write`

5. Configurar o "phone directory" para o IP Phone 1, necessitando também configurar o CME do RouterA para associar o número do telefone com este outro.

`1.` `RouterA\#configure terminal` `2.` `RouterA(config)\#ephone-dn 1` `3.` `RouterA(config-ephone-dn)\#number 54001` `4.` `RouterA(config-ephone-dn)\#exit` `5.` `RouterA(config)#exit` `6.` `RouterA\#write`

6. Repetir os passos anteriores para que seja possível atribuir um número de telefone para cada equipamento, tanto os que estão interligados no SwitchA como os que estão interligados no SwitchB. Por exemplo:

`1.` `RouterA\#conf t` `2.` `RouterA(config)\#ephone-dn 2` `3.` `RouterA(config-ephone-dn)\#number 54002` `4.` `RouterA(config-ephone-dn)\#exit` `5.` `RouterA(config)#exit` `6.` `RouterA#` `7.` `# Assim, sucessivamente para todos os telefones.`

7.Certifique-se que o telefone IP recebeu um número IP e o número do telefone 54001, recebido do Router_A.

8. Repita o passo 7 para todos os outros telefones interconectados.