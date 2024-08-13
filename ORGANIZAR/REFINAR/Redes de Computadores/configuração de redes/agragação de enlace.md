**Definição**

Agregação de enlace é o nome dado ao mecanismo de combinar duas ou mais interfaces físicas de rede em uma única interface lógica, via software (ou seja, através de configuração). Esse mecanismo é muitas vezes referenciado como _**bonding**_.

**Aplicação**

A motivação para combinar interfaces físicas em uma única interface lógica se dá, essencialmente, por três motivos:

- Aumentar a largura de banda (velocidade do _link_) entre os dispositivos conectados, sem custos adicionais;
- Adicionar redundância: caso algum _link_ seja interrompido, seja por uma porta Ethernet queimada ou por um rompimento em um cabo, a conexão continua ativa (desde que tenha restado ao menos uma conexão funcional, é claro);
- Balanceamento de carga entre os links combinados (para não sobrecarregar um único _link_ físico).

**Princípio de funcionamento**

Atualmente, o protocolo mais comumente utilizado para habilitar a agregação de links entre dispositivos de rede é o _**Link Aggregation Control Protocol**_ (LACP), um padrão _**de jure**_ (ou seja, um padrão aberto, não proprietário), definido pelo IEEE 802.3ad. Este é responsável por enviar _**Link Aggregation Control Protocol Data Units**_ (LACPDUs) entre os dispositivos e, assim, possibilitar a criação de _**links**_ virtuais, sendo também responsável pela atualização desses _**links**_ virtuais, quando algum _**link**_ físico fica indisponível (quando do rompimento de um cabo, por exemplo).

**Cenário de exemplo**

A título de exemplo, considere a topologia na Figura 1, abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/4/2389441/40964.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/4/2389441/40964.png)

Fonte:

Percebemos que temos dois _**links**_ de conexão entre os switches SW1 e SW2. Entretanto, como o LACP ainda não foi habilitado, somente um desses _**links**_ está ativo (como podemos observar pela indicação da “bolinha” em vermelho, no _**link**_ inferior, do lado do SW2).

**Configuração do cenário de exemplo**

A Figura 2 mostra a configuração do LACP no SW1:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/4/2389455/40965.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/4/2389455/40965.png)

Fonte:

A configuração do LACP, em linhas gerais, pode ser atingida seguindo as etapas abaixo (DONAHUE, 2011).

Primeiramente, devemos acessar cada uma das interfaces que farão parte do link agregado (em nosso exemplo, através do comando _**interface fastEthernet 0/1**_ e, depois, _**interface fastEthernet 1/1,**_ para definir a qual grupo virtual essa interface fará parte, através do comando _**channel-group 1 mode active**_.

A quantidade de grupos virtuais de interfaces que podem ser criados depende do modelo do switch. No caso do utilizado no Packet Tracer®, poderíamos criar até 6 grupos diferentes. Em nosso exemplo, criamos apenas um grupo, o grupo 1.O modo ativo refere-se a habilitar o protocolo LACP incondicionalmente nessa interface, mesmo que o outro switch não esteja com o protocolo habilitado.

Depois basta ir nas configurações do grupo – através do comando _**interface Portchannel 1**_, em nosso caso, para definirmos como ele operará, através do comando _**switchport mode trunk**_.

_**Trunk**_ significa que será uma porta conectada a outro switch. A outra opção seria _**access**_, que significaria uma porta conectada a dispositivos finais, como PCs e servidores. Entretanto, para que funcionasse, o dispositivo final precisaria dar suporte ao LACP. Esse é o motivo de termos criado a agregação apenas entre os switches.Mas saiba que, dependendo do hardware e sistema operacional, alguns servidores dão suporte a esse protocolo também.

Precisamos habilitar as mesmas configurações no switch que será o “par” do SW1; em nosso caso, o SW2. As configurações são mostradas na Figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/4/2389462/40966.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/4/2389462/40966.png)

Fonte:

Agora, podemos observar que a agregação está habilitada e funcional, através do comando _**show etherchannel summary,**_ tanto no SW1 quanto no SW2, conforme Figura 4:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389794/40967.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/7/2389794/40967.png)

Fonte:

Além disso, agora o próprio simulador mostra que ambos _**links**_ estão habilitados e funcionando, conforme Figura 5:

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/5/2389594/40968.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/3/8/9/5/2389594/40968.png)

Fonte:

**Conclusão**

Neste capítulo apresentamos a definição da agregação de _**link**_, apresentamos os principais benefícios da sua utilização, bem como demonstramos o princípio de funcionamento do LACP no simulador Packet Tracer®, da Cisco.