**Cenário de exemplo**

A título de exemplo, considere a topologia da Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/5/5/6/2455636/40783.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/5/5/6/2455636/40783.png)

No exemplo da Figura 1, temos um edifício comercial onde uma empresa possui dois andares, e temos PCs do departamento de Engenharia e do departamento de Vendas nos dois andares. Por uma série de questões, o pessoal de Engenharia não pode acessar os mesmos recursos do pessoal de Vendas e vice-versa, motivo pelo qual dividimos as portas de cada um dos switches gerenciáveis SW1 e SW2 (por meio da configuração destes) em dois grupos distintos: Engenharia e Vendas (identificados na configuração das interfaces Fa2/1 e Fa1/1 dos switches como VLAN10 e VLAN 50, respectivamente).

Como os PCs de cada departamento devem estar em uma mesma rede, mas isolados das redes de outros departamentos, precisaremos configurar um link de _**trunking**_ entre os switches de cada andar, ou seja, precisaremos habilitar o protocolo 802.1Q nas interfaces Fa0/1 de cada um dos switches.

**Configuração do cenário de exemplo**

Nesse cenário de exemplo, as máquinas estão configuradas conforme Quadro 1, abaixo:

![[Screenshot_from_2021-10-22_22-44-06.png]]

Note que, sem as VLANs, a configuração acima faz com que todos os PCs se comuniquem, independentemente do departamento a que pertencem. Para atender aos objetivos descritos no cenário de exemplos, precisaremos configurar as VLANs.

A configuração de VLANs, em linhas gerais, pode ser atingida seguindo as etapas abaixo (DONAHUE, 2011):

1. Criar e nomear as VLANs

2. Configurar o tipo de porta e associar as interfaces físicas dos switches a essas VLANs.

- _A__ccess_, para portas conectadas a dispositivos finais.
- _Tr__unking_, para portas conectadas a outros switches.

A Figura 2 mostra os comandos para atingir essa configuração no switch SW1:

`1.` `SW1 (config) \#vlan 10` `2.` `SW1 (config-vlan) \#name ENGENHARIA` `3.` `SW1 (config-vlan) \#exit` `4.` `SW1 (config) #vlan 50` `5.` `SW1 (config-vlan) #name VENDAS` `6.` `SW1 (config-vlan) \#interface fa2/1` `7.` `SW1 (config-if) \#switchport mode access` `8.` `SW1 (config-if) #switchport access vlan 10` `9.` `SW1 (config-if) #exit` `10.` `SW1 (config) #interface fa1/1` `11.` `SW1 (config-if) #switchport mode access` `12.` `SW1 (config-if) #switchport access vlan 50` `13.` `SW1 (config-if) #exit` `14.` `SW1 (config) #interface fa0/1` `15.` `SW1 (config-if) #switchport mode trunk` `16.` `SW1 (config-if) #switchport trunk allow vlan 10,50` `17.` `SW1 (config-if) #exit`

Figura 2 - Configuração do SW1

Primeiramente, criamos a VLAN 10 com o comando _**vlan 10**_, a nomeamos com o comando _**name ENGENHARIA**_; e repetimos o processo para a VLAN 50 (Vendas).

Depois entramos nas interfaces nas quais os PCs de Engenharia estão conectados e configuramos elas com portas de acesso, com o comando _**switchport mode access**_, dando acesso a dados direcionados a VLAN 10, com o comando _**switchport access vlan 10**_; e repetimos o processo para os PCs de Vendas.

Por fim, entramos na interface que está conectado ao switch SW2 para configurarmos ela como uma porta do tipo _**trunk**_, com o comando _**switchport mode trunk**_, e informamos quais VLAN serão permitidas, com o comando _**switchport trunk allow vlan 10,50**_ (permitindo, assim, o tráfego das VLANs 10 e 50 por esse link).

Agora, basta fazermos as mesmas configurações no switch SW2.

Uma vez configurados ambos switches, podemos utilizar comandos para verificar que está tudo configurando corretamente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/3/7/9/2437932/40751.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/3/7/9/2437932/40751.png)

Figura 3: Comandos de verificação de VLANs.

Na Figura 3, acima, temos exemplos desses comandos (digitados no SW2) e suas informações, conforme segue:

(a) Comando _**show vlan brief**_: verificamos quais VLANs estão configuradas e a quais portas estas estão associadas;(b) Comando _**show interfaces fastEthernet 1/1 switchport**_: mostra detalhes da porta _**fastEthernet 1/1**_, indicando neste caso que essa porta está configurada como uma porta de acesso a VLAN 50, e que está, de fato, utilizando o protocolo IEEE 802.1Q;(c) Comando _**show interfaces trunk**_: mostra quais interfaces estão configuradas como _**trunk**_, e quais VLANs podem trafegar por essa porta (no caso, ambas VLANS; 10 e 50).

A Figura 4 mostra o resultado final, onde um comando “ping” para o endereço 192.168.10.20 tem sucesso (pois o PC20 está na mesma VLAN que este PC), mas não consegue “pingar” o endereço 192.168.10.21 (pois o PC21 faz parte de outra VLAN; a VLAN 50 nesse caso).

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/4/3/7/8/2437806/40786.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/4/3/7/8/2437806/40786.png)

Observe que, como as VLANs são implementadas na Camada de Enlace (_**Layer**_ 2) do modelo de referência ISO/OSI, não precisamos definir o default gateway nos PCs, uma vez que, na Camada de Rede (_**Layer**_ 3), os equipamentos estariam em uma mesma rede e, portanto, se comunicariam entre si, como aconteceria no cenário de exemplo se não implementássemos as VLANs.

**Conclusão**

Neste capítulo apresentamos as principais configurações de VLANs, utilizando o simulador do Packet Tracer®, da Cisco.