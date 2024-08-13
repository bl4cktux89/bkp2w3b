**Introdução**

Olá! Seja bem-vindo à décima quarta aula! Nela, vamos aplicar os conceitos de SNMP utilizando a ferramenta MIB browser do software Packet Tracer. Para isso, é necessário que você instale uma versão deste software.

**O Packet Tracer**

É um software com a finalidade do estudo prático de redes em um ambiente virtual. Foi desenvolvido pela empresa Cisco para uso próprio em suas academias espalhadas pelo mundo e não pode ser usado comercialmente, já que possui licença de copyright.

**O ambiente virtual**

Vamos trabalhar um ambiente de rede com um roteador (cisco 1841), um switch (catalyst 2950) e um microcomputador conectados através das interfaces Fast Ethernet.

A ligação dos cabos de rede deve ser feita da seguinte forma:

- A porta Fast Ethernet 0/0 do **roteador** ligada à porta Fast Ethernet 0/1 do **switch**.
- A porta Fast Ethernet do **PC** ligada à porta Fast Ethernet 0/2 do **switch**.

Veja a figura:

![[Untitled 4.png|Untitled 4.png]]

**Configuração do roteador**

Com o ambiente preparado, primeiro vamos à configuração do roteador. Clique sobre o roteador para abrir uma janela no seguinte formato:

Agora, clique na aba "CLI":

![[Untitled 1.png]]

A "CLI" é a interface entre o usuário e o equipamento. Através dela, podemos aplicar os comandos num roteador, switch ou qualquer outro equipamento que a contenha interface. Ao acessar a CLI, deverá aparecer a mensagem: "... Continue with configuration dialog? [yes/no]: ...", coloque "no" e pressione "ENTER", ou pressione as teclas "CTRL" e "C" juntas para sair da caixa de diálogo. Assim que isso for feito, aparecerá a mensagem: "Press RETURN to get started"; tal mensagem é exibida quando acessamos um equipamento, então, basta pressionar "ENTER". para ser exibido o prompt de comando do modo USER e, assim, começarmos.

![[Untitled 2 2.png|Untitled 2 2.png]]

  

A partir daqui, executaremos a seguinte sequência de comandos:

> enable

> configure terminal

> interface fastEthernet 0/0

> ip address 192.168.1.1 255.255.255.0

> no shutdown

> exit

> snmp-server community public ro

> exit

> copy running-config startup-config

![[Untitled 3 2.png|Untitled 3 2.png]]

Quando terminar, é só fechar.

**Configuração do PC**

Para configurar o PC, faça o seguinte: primeiramente clique "sobre" ele; uma janela será aberta. Clique sobre a aba "Desktop" (área de trabalho) e, depois, sobre "IP Configuration" (configuração do IP). Ative a cofiguração estática e coloque o IP: 192.168.1.2, com máscara: 255.255.255.0 e gateway padrão: 192.168.1.1.

![[Untitled 4 2.png|Untitled 4 2.png]]

Agora, feche a IP Configuration e abra o prompt de comando. Após abrir, teste se os ICMPs estão chegando ao roteador com o comando: "ping 192.168.1.1".

![[Untitled 5.png]]

**Acessando dados via SNMP entre o gerente e o agente**

Na topologia configurada, temos 2 atores: o primeiro é o gerente, que é o PC, e o segundo é o agente, que é o roteador. Dessa forma, quando finalizar o teste com o ICMP, feche a janela do prompt de comando e abra MIB browser (navegador MIB). Clique no botão "Avançado" para abrir uma nova janela. No item "Endereço", coloque o IP do roteador: 192.168.1.1, no item "Community string de leitura" coloque a palavra "public", que é o grupo SNMP criado no roteador, no lugar da digitação não aparecerá a comunidade, apenas bolinhas. Altere a versão do SNMP para V2. Não é necessário alterar a porta, tampouco inserir a comunidade de escrita. Clique em "OK".

![[Untitled 6.png]]

Agora, em "MIBs SNMP", expanda: MIB Tree, router_std MIBs, .iso, .org, .dod, .internet, .mgmt, .mib-2, .system, .sysDescr.

Observe que no campo "OID" apareceu um código numérico: esse é o código SMI utilizado pelo SNMP para coletar informação na MIB do AGENTE sobre a "Descrição do Roteador". Feito isso, clique no botão "IR" que está ao lado direito do campo "OPERAÇÕES". Observe que ele trouxe uma informação na "Tabela de Resultados".

![[Untitled 7.png]]