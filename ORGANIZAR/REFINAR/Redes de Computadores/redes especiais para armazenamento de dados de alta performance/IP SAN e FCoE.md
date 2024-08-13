### Introdução

Neste tópico serão discutidas as tecnologias de  IP SAN ( Internet Protocol e Storage Area Network) e (Storage Area Network e Fiber Channel over Ethernet) e SAN FCoE (Fibre Channel over Ethernet) , e entenderemos como eles funcionam, e suas características. ambos são arquiteturas de redes de armazenamento, o que faz as duas se assemelham é o fato de ambas usarem a internet como meio de transmissão de dados, porém são duas alternativas com métodos de implementações diferentes.

Uma das principais vantagens dessa metodologia é a possibilidade de acessar sistemas de armazenamento que não estão conectados diretamente na sua rede, o que quebra os limites de uma rede local.

### Internet Protocol Storage Area Network ( IP SAN )

É uma SAN (Storage Area Network, ou rede de área de armazenamento.) que utiliza o protocolo IP para transportar dados a nível block(como dados contidos em HD’s por exemplo), ele encapsula protocolos de block para IP, dessa maneira a infraestrutura do data center muitas vezes pode ser aproveitada, já que essa arquitetura já é existente, e essa solução não sai tão caro quanto uma solução de fibra. Outra vantagem, é que dessa maneira podemos estender a nossa rede para outras áreas geograficamente afastadas, uma vez que se ligam a internet.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/1/0/2821056/43221.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/1/0/2821056/43221.png)

### Principais protocolos

Os principais protocolos usados para IP SAN são: iSCSI e FCIP

**iSCSI(****Internet Small Computer System Interface****)**:  É uma variante do SCSI que serve para enviar comandos e dados em um sistema de armazenamento, o iSCSI serve para transportar comandos SCSI entre um initiator(Iniciador) que seria um sistema computacional, e um target(alvo) que é onde ele deve se conectar, em um sistema de armazenamento. Por trabalhar com SCSI ele não precisa de equipamentos específicos de fibra. Nesse caso o initiator pode ser um sistema computacional, o destino o storage, e a rede uma LAN.

_**iSCSI Initiators:**_ Temos três tipos de Initiators, os

- NIC (Network Interface Card, ou placa de interface de rede) padrões, que são placas de rede normais com softwares para fazer a adaptação para o protocolo iSCSI.
- NIC TOE, TOE significa TCP offload engine, ele diminui um pouco a sobrecarga na rede cuidando da parte do tráfego de rede TCP e deixa apenas às operações SCSI para o processador, diferente dá NIC padrão, onde tudo é feito por software, logo o processador é responsável pelo processamento total.
- HBA iSCSI, que é um adaptador de hardware com funcionalidade iSCSI e descarga de TCP, ou seja, consegue lidar com os dois, dessa forma não gasta processamento do sistema computacional.

Falando sobre os métodos de conectividade de iSCSI temos duas opções:

- iSCSI Nativo ou com Bridge. O nativo são iSCSI initiators que se conectam diretamente ou por uma rede IP ao destino, e por isso não envolvem nenhum componente de FC em sua conectividade.
- iSCSI Bridge é um tipo de conectividade na qual os iniciadores encontram-se em uma rede IP e o armazenamento em FC(Fibre Channel), dessa maneira é possível uma coexistência entre os dois, bridge significa ponte, e é exatamente isso que acontece, uma ponte de um para outro.

Sobre o protocolo iSCSI, ele usa endereços para realizar essa comunicação, esse endereço serve como referência para o iniciador e destino, e é composto com a localização dos dois. Também são usados nomes para a identificação de um iSCSI:

IQN(iSCSI Qualified Name): É preciso ter um nome de domínio para se criar esse tipo de nome, ele é gerado baseado no nome do domínio, data da criação e fabricante, dessa maneira cria-se um nome único, por exemplo iqn.2018-06.br.uninove:num_serie.

EUI(Extended Unique Identifier): É um identificador único(global), ele é criado usando o prefixo EUI por um número hexadecimal de 16 caracteres, como eui.5932A03038D26072.

NAA(Network Address Authority): Funciona como um identificador global também, porém é usado em SAS(SCSI por serial), seu nome é formado por naa e um número hexadecimal, como por exemplo: naa.2678D545600A647B.

Esses endereços e nomes são usados para identificar outros nós na rede. A detecção inicial é feita enviando uma solicitação de _**SendTargets,**_ que é uma solicitação manual, feita com endereço IP e porta TCP, onde o destino envia sua posição para o iniciador. Ou com iSNS(Internet Storage Name Service), que funciona como um servidor de nomes, dessa forma é possível criar domínios automaticamente, assim sempre que um iniciador pedir o endereço de destino a um servidor iSNS, ele fornece uma lista de possibilidades disponíveis.

**CONCEITO DE AGREGAÇÃO**

Uma técnica muito útil em IP SAN é a agregação de links(ligações entre os switches) e de switches, isso é feito para aumentar o **throughput,** que é a taxa de transferência(velocidade) e quantidade de dados, e pela flexibilidade para manutenção, e oferece maior estabilidade, uma vez que se um link para de funcionar os outros continuarão fazendo o balanceamento entre eles.

Esse recurso útil é criar redes auto-formadoras(reconhece automaticamente os Switches em uma rede.) e agregação de links auto-formadores(reconhece automaticamente links de um switch), a agregação é uma técnica que serve para automatizar tarefas como configurar switches e links.

Para isolar o tráfego de iSCSI do resto da rede é comum o uso de VLAN(Virtual LAN) que é a criação de uma rede local virtual para dividir logicamente a rede física. Assim como na agregação de links e switches, é possível criar um tronco de VLAN, que é o agrupamento de duas ou mais VLAN’s, para que seja possível saber qual o destino/origem correta de cada pacote enviado, é usado uma técnica chamada de marcação de VLAN. VLAN’s também podem ser estendidas, dessa é possível ter duas VLAN’s em locais diferentes ligados por uma rede WAN. Também temos a VSAN, que é a técnica de virtualizar redes SAN.

**FCIP(Fibre Channel over IP):**  Também conhecido como tunelamento de FC ou tunelamento de  armazenamento, é um protocolo de internet IP, que encapsula os quadros do FC e os encaminha para uma rede IP usando TCP/IP, permitindo uma abordagem distribuída geograficamente. Assim pode-se usar FC para compartilhar dados ao redor do mundo, já que eles se ligam na internet.

Para criar essa comunicação entre IP e FC um dispositivo FCIP é usado, geralmente é um gateway que realiza a conexão entre os dois e procede com a “tradução” de quadros FC para pacotes IP. Alguns tipos de implementação de FCIP permitem a agregação de links para redundância e balanceamento.

### FCoE

É uma SAN que transporta dados provenientes de Fibre Channel junto com o tráfego ethernet, que é o conceito de convergência. Atualmente é muito comum ter redes com diferentes tipos de tráfego. Essa convergência entre FC e IP usa equipamentos como adaptadores, cabos e switches multifuncionais, o que facilita o gerenciamento, porém aumenta o custo geral de implementação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/1/0/2821065/43222.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/1/0/2821065/43222.png)

Os principais elementos em uma rede SAN FCoE são cabos (Fibra ou cobre), Switches FCoE (que é um switch que pode lidar com tráfego de ethernet) e FC graças a um componente chamado FCF(Fibre Channel Forwarder), que é um “tradutor” entre os dois, e CNA(Converged Network Adapter), que é um adaptador de rede para convergência de dados, ou seja opera como uma placa de rede normal(NIC), e como um HBA FC.

Uma alternativa para o CNA é um adaptador FCoE por software. Dessa forma é possível ligar uma rede SAN FC à internet, e assim como em SAN IP, podemos usar VLAN’s e VSAN’s para separar os tipos de tráfego.

O FCoE usa algumas portas virtuais para simular portas FC regulares. Às portas são descritas abaixo:

**VN_Port:** É a porta de conexão ao sistema computacional ou de armazenamento.**VF_Port:** Porta no switch que se conecta a uma VN_Port.**VE_Port:** Porta no switch que faz a conexão entre dois switches FCoE.

### Converged Enhanced Ethernet (CEE)

CEE diz respeito a melhorias na convergência de dados por Ethernet, para que uma rede seja capaz de lidar com vários tipos de tráfego sem ter perdas, é preciso um controle de fluxo, e outras técnicas que serão vistas a seguir:

- **Controle de fluxo por prioridade:** No FC tradicional é usado um controle de fluxo baseado em crédito, que é basicamente uma negociação entre às partes em ua transmissão para regular a velocidade de transmissão. Em FCoE é usado um controle PAUSAR dá Ethernet, que é usado para negociação, dessa maneira pode-se controlar o fluxo de envio de dados, e caso o receptor não possa receber algum dado no momento a transmissão é pausada para evitar a perda de dados.
- **Seleção aprimorada de transmissão:** Permite que o administrador determine o quanto de banda deve ser alocada para cada tipo de tráfego na rede. Por exemplo, pode-se destinar 60% da banda de rede para tráfego de LAN(Rede local), e 40% para SAN(Rede de armazenamento).
- **Notificação de congestionamento:** É uma solução para protocolos que não têm por padrão um controle de congestionamento, como por exemplo o FC. Quando existir algum congestionamento em alguma rota, é gerado uma notificação, e outro caminho é fornecido para continuar a transmissão.
- **DCBX: O protocolo DCBX**(Data Center Bridging Exchange) serve para detectar e mudar configurações dos dispositivos de rede, os switches podem negociar parâmetros de configuração, permitindo assim uma configuração consistente em toda rede.

### Arquitetura FCoE

A arquitetura FCoe é similar a FC, porém por enviar tráfego FC por uma rede Ethernet é preciso encapsular esses quadros FC em quadros Ethernet. O processo de comunicação FCoE baseia-se primeiro na detecção, onde dispositivos de rede são localizados por meio de um mecanismo chamado FIP(FCoE Initialization Protocol), que é o protocolo responsável por transmitir os parâmetros de login. Depois temos o login, onde acontecem os logins do FC, existem alguns tipos de logins, mais os principais são de porta e endereço. E por último temos a fase de transferência, após tudo identificado, e devidamente autenticado é possível iniciar a transmissão.

O endereçamento em uma SAN FCoE usa o endereço MAC(Endereço físico da placa de rede) para encaminhar seus quadros, temos suporte a dois tipos de endereçamentos diferentes para às VN_Ports:

- **SPMA(**_**server-provided MAC address)**_**:** São endereços fornecidos pelo MAC do servidor, o SPMA em sistemas computacionais permite o uso de um endereço único para tráfego FCoE, ou pode ter vários endereços, um para cada VN_port disponível.
- **FPMA(**_**fabric-provided MAC address)**_**:** São endereços fornecidos pelo MAC do fabric(Switch), é atribuído a VN_Port pelo switch. O FPMA garante que os endereços sejam únicos em uma rede SAN FCoE.

Em  uma rede SAN FCoE cada nó precisa saber dois endereços diferentes para realizar uma transmissão, fazendo um paralelo podemos imaginar a brincadeira do telefone sem fio, onde você tem dois endereços diferentes, o que te passou a informação primeiro, e o que você passará, ou seja um antes e outro depois, porém falando de SAN FCoE não precisam ser nessa ordem específica. a arquitetura pode variar, mas sempre será preciso de pelo menos duas ligações por nó para que haja um encaminhamento de dados(quadros).

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/1/0/2821078/43223.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/8/2/1/0/2821078/43223.png)

### Resumo

Como podemos ver, ambos os tipos de arquitetura podem nos fornecer um bom desempenho, porém o FCoE por ser fibra, depende de alguns hardwares específicos e sua implementação pode ser mais cara, por outro lado é mais rápido que o IP SAN. O IP  SAN têm como objetivo facilitar esse tipo de armazenamento, sem que se tenha hardwares específicos, dessa forma sai BEM mais barato montar um IP SAN do que um FCoE.

Por mais que o FCoE apresente um desempenho melhor, o IP SAN não fica para trás, pois ele é projetado para trabalhar com um alto **throughput,** que é a taxa de transferência e quantidade de dados. Então na hora que for decidir qual usar, vale a pena analisar alguns pontos, por exemplo, caso já use fibra, a implementação de FCoE não sairá tão caro. Caso não use, talvez valha mais a pena IP SAN, e muitos outros fatores. Sempre analise bem cada caso para ver qual se encaixa melhor a suas necessidades.