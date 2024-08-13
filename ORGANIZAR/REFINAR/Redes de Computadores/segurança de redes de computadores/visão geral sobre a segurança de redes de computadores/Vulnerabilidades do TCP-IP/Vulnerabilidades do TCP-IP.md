> [!important]  
> O presenta tópico tem por finalidade apresentar de forma breve o funcionamento da pilha de protocolos TCP/IP e a sua relação com as redes de computadores e, principalmente, apresentar as vulnerabilidades decorrentes de sua arquitetura.  

### **Introdução**

A suíte de protocolos TCP/IP constitui a base para o funcionamento de qualquer tipo de rede de computadores. O acrônimo TCP significa "Protocolo de Controle de Transmissão" e o IP "Protocolo de Internet" e reuni nesses dois protocolos as principais funcionalidades para que existe o transporte rápido e eficiente dentro das redes. De forma mais específica, o protocolo IP fornece as ferramentas necessárias para o transporte por meio do roteamento enquanto que os mecanismos utilizados pelo TCP garantem a entrega confiável.

Durante o seu desenvolvimento, que remonta aos 70 e 80 do século passado, o TCP tinha como objetivo atender as necessidades acadêmicas e em formas baratas e fáceis de compartilhar informações entre si. Não levaram em conta que esses protocolos poderiam ser usados de forma tão ampla por todos nós ao redor da terra, o que acabou de fato acontecendo. Hoje, essa suíte de protocolos é base da Internet.

Com a avanço da internet, as vulnerabilidades do TCP/IP vieram à tona de forma a permitir, por exemplo, a captura de uma conexão TCP que ocorre durante fase de conexão, conhecida como handshake triplo, como será visto mais detalhadamente a frente. Por outro lado, ataques de negação de serviço (DoS) e falsificação de endereços IPs são problema comuns que advém do fato de como essa arquitetura foi desenvolvida. Veja abaixo como ocorreu a evolução da Internet

![[Untitled 85.png|Untitled 85.png]]

### O Modelo TCP/IP

Antes de começarmos a tratar especificamente das vulnerabilidades e ataques em relação a pilha de protocolos TCP/IP, é importante conhecer o próprio modelo e suas subdivisões em camadas. Esta é uma forma bastante intuitiva para o aprendizado, além e facilitar a identificação problemas, organizar os protocolos e estabelecer suas funcionalidades.

O modelo TCP/IP que iremos utilizar é conhecido como modelo híbrido e possui cinco camadas, são elas (De cima para baixo): Aplicação, Transporte, Internet e Enlace de dados e Física (Filippetti, Marco Aurélio, 2017).

![[Untitled 1 49.png|Untitled 1 49.png]]

As principais funções das camadas e os respectivos protocolos são apresentadas abaixo:

**Aplicação:** Define os protocolos de aplicativos TCP/IP, tais como, DNS, FTP, HTTP, SMTP etc,  e como tais programas estabelecem uma interface entre o usuário e a aplicação, assim como uma interface de comunicação com os serviços de camada de transporte.

**Transporte:** Fornece gerenciamento de sessão de comunicação entre computadores host. Define o nível de serviço e o status da conexão usada durante o transporte de dados. Nessa camada encontramos o protocolo TCP, um protocolo confiável que fornece mecanismos  para garantia da integridade e a confiabilidade dos dados transmitidos, além da orientação da conexão. Por outro lado, aplicações que necessitam de agilidade no transporte e não requerem confiabilidade utilizam o protocolo de transporte UDP (Protocolo de datagrama de usuário). Outros protocolos dessa camada são DCCP, RSVP e SCTP.

**Camada de Internet:** O TCP/IP suporta o Protocolo de Internet (IP), que por sua vez pode utilizar outros protocolos, tais como IPv4, IPv6, ICMP, protocolos de roteamento (OSPF, RIP e BGP). O IP trata-se de um protocolo não confiável, que não possui nenhuma verificação de erro, mas, por outro lado, faz o melhor possível para entregar a mensagem ao destinatário. Nessa camada temos também os protocolos RARP e ARP, este último importantíssimo para a operação em redes IPv4.

**Camada de Enlace de dados:** está associada com os métodos de controle de acesso ao meio de transmissão, sejam eles em redes LAN (Redes Locais) e WAN (Redes de Longa Distância). Em redes LAN, o principal protocolo é o Ethernet, enquanto para redes WAN temos Frame-relay, ADSL, MPLS e ATM.

**Camada Física:** O modelo TCP/IP não define nenhum protocolo específico para a camada Física, assim como acontece na camada de Enlace de Dados, e por isso suporta todos os padrões proprietários. Entretanto, a camada Física lida com as características elétricas e mecânicas associadas aos meios de transmissão (cabo coaxial, fibras óptica, par-trançado ou wireless).

### O Modelo TCP/IP e os protocolos de segurança

O conhecimento dos modelos de rede e seus respectivos protocolos é fundamental para compreender a segurança de redes, por exemplo, existem firewalls que são considerados filtros de pacotes e operam na camada de Internet e Transporte, mas também existem Firewalls de camada de Aplicação.

Em relação aos protocolos de segurança, existem, por exemplo, VPNs de camada de Internet que utilizam IPSec para prover integridade e confidencialidade aos dados transmitidos na Internet. Por outro lado, existem também as VPNs de Aplicação, que operam entre a camada de Transporte e Aplicação.

Quando se trata de criptografia, cada camada possui um mecanismo de criptografia associada a ela. Por exemplo, nas redes wireless, a criptografia ocorre principalmente na Camada de Enlace de Dados, mas também existem mecanismos criptográficos que são usados nas outras camadas (Basta, A; Basta, N. Brown, M. 2015).

A figura abaixo exibe os pricipais protocolos e mecanismos de segurança utilizados em redes de computadores.

![[Untitled 2 39.png|Untitled 2 39.png]]

### Processo de Encapsulamento dos dados

Os dados ao serem gerados pelos dispositivos fins (computadores, telefones IP etc) realizam o processo de encapsulamento dos dados à medida que passam por cada uma das camadas. Nesse processo de encapsulamento,  são adicionados cabeçalhos contendo, por exemplo, os endereços IPs de origem e destino na camada de Internet, e o endereços MACs de origem e destino.

![[Untitled 3 25.png|Untitled 3 25.png]]

Para identificar cada encapsulamento em sua respectiva camada é definido o que chamado de PDU (Unidade de Protocolo de Dados), assim cada camada possui sua PDU. Cada camada recebe a PDU da camada superior e adiciona o seu cabeçalho.

Como exemplo, imagine que você está solicitando uma página na web, neste caso, você utiliza o protocolo HTTP ou HTTPs que estão na camada de Aplicação para solicitar a página. A PDU da camada de Aplicação é conhecida como DADOS; na camada de Transporte é adicionado o cabeçalho TCP, formando-se assim a PDU Segmento na camada de Transporte; na sequência, na camada de Internet é adicionado o cabeçalho IP, formando a PDU Pacote; a camada de Enlace de Dados, por sua vez, adiciona o seu cabeçalho, por exemplo, o cabeçalho Ethernet para formar a PDU Quadro, e, finalmente, tudo isso é convertido em bits na camada Física. Por isso sua PDU é conhecida como Bits. Veja a seguir, a sequência cabeçalhos que são adicionados no processo de encapsulamento.

### Funcionamento e Vulnerabilidades do TCP/IP

### Funcionamento

A partir dos anos 90, a segurança tornou-se um problema sério devido as vulnerabilidades do TCP/IP. E desde então, muito se tem trabalho para reforçar a segurança. Várias mudanças foram realizadas no IPv6 para amenizar as vulnerabilidades do IPv4.

O protocolo TCP teve suas especificações definidas pela RFC (Request for Comments) 793, definindo, a estrutura do cabeçalho e os procedimentos para funcionamento. Na figura que segue é mostrado a estrutura do cabeçalho TCP (Basta, A; Basta, N. Brown, M. 2015.

![[Untitled 4 22.png|Untitled 4 22.png]]

  

Os principais campos deste cabeçalho são:

- **Porta de origem e destino:** Juntamente com o endereço IP de origem e destino, a porta de origem e destino identifica de forma única uma conexão estabelecida.
- **Número de sequência:** Identifica o pacote de forma única em uma conexão estabelecida.
- **Número de reconhecimento:** informa que o pacote anteriormente enviado foi recebido com sucesso.
- **Bits de código (flags):** Constitui de flags (sinalizadores) que sinalizam status da conexão, são elas: Flag SYN: Sincronização; Flag ACK: Confirmação; Flag FIN: finalização de conexão; RST: Resetar conexão
- **Janela:** controle de fluxo.

### Vulnerabilidades do TCP

**As principais vulnerabilidades do TCP/IP são elencadas abaixo (McNab, Chris, 2017):**

- **IP Spoofing:** Consiste em mascarar o endereço IP da máquina do atacante, enviando pacotes utilizando um endereço IP legítimo da rede.
- **Falsificação TCP/IP:** O invasor, utilizando um endereço IP falso, envia pacotes para o computador da vítima. Como a vítima não tem ideia se o pacote vem de uma origem confiável, ela acaba aceitando a conexão por meio de uma mensagem de confirmação a máquina do invasor. Isso também é conhecido como ataque _**man-in-the-middle (homem no meio).**_ Como o invasor não consegue ver a resposta, ele precisa adivinhar o número de sequenciamento ACK correto como se tivesse vindo de uma origem real. Caso o atacante consiga a sequência correta, ele é capaz de manter a conexão com a máquina da vítima enquanto o seu computador estiver ativo. Para descobrir o número de sequência correta existem dois métodos: Adivinhação de sequenciamento e roteamento do remetente.
- **Sequestro de conexão:** Consiste me derrubar uma conexão TCP bombardeando-a com pacotes TCP/IP dessincronizando uma séria de pacotes entre o computador de origem e destino. O envio de pacotes extras com os mesmos números de sequenciamento de segmentos legítimos pode forçar a máquina de destino escolher segmentos fraudados em vez de segmentos autênticos. Se a vítima aceitar os segmentos fraudulentos, a conexão é sequestrada e a partir desse ponto o invasor se comunicará como se fosse um computador autêntico, fechando a conexão para o computador legítimo.
- **Ataques de ICMP:** O protocolo ICMP é utilizado para devolver diagnósticos do status da rede e alcançabilidade de dispositivos. Como esse protocolo não utiliza autenticação para os pacotes enviados, o seu envio pode ser interceptado e na sequência pacotes ICMPL adulterados podem ser enviados. Outra variante desse ataque ocorre via ICMP Flood, por meio da inundação (flood) de pacotes ICMP marcados como Destino Inalcançável e Tempo de Vida Excedido, fazendo com que as conexões entre origem e destino sejam reiniciadas, tendo em vista que o TCP estabelece a duração de tempo em que um segmento é válido.
- **Ataques TCP SYN:** também conhecidos como SYN Flood, este tipo de ataque se aproveita do processo de estabelecimento de conexão TCP e das mensagens SYN do handshake. Como exemplo, servidores HTTP mantem parcialmente abertas tentativas de conexão SYN em sua fila por um período aproximado de 75 segundos. Como os recursos são limitados, o invasor pode estourar a fila do servidor, impedindo assim que conexões legítimas possam ter acesso a página HTTP.
- **Ataques aos protocolos de roteamento:** As redes de computadores utilizam protocolos de roteamento para prover os melhores caminhos par ao encaminhamento dos pacotes. O atacante pode se aproveitar da falta de autenticação de alguns protocolos de roteamento e da falta de boas práticas na implementação do protocolo como, por exemplo, o RIP e o OSPF. Este ataque faz com que o atacante manipule as métricas destes protocolos fazendo com que o tráfego possa ser redirecionado para a máquina do atacante (Basta, A; Basta, N. Brown, M. 2015.

### Como proteger o TCP/IP?

A arquitetura TCP/IP basicamente não fornece mecanismos de criptografia e autenticação de dados e, principalmente, de seu cabeçalho. E por isso podem ser facilmente coletados por farejadores de pacotes e o seu conteúdo. Para evitar coleta, dados sensíveis normalmente são transportados de forma criptografadas e o processo de autenticação não permite, por exemplo, que as senhas sejam transmitidas em texto claro, entretanto, os cabeçalhos com continuam expostos.

Essas falhas são inerentes ao protocolo TCP/IP e não podem ser extintas sem que houvesse uma alteração em todos os protocolos de sua pilha. Com a adoção de forma massiva do IPv6 muitos desses problemas podem ser minimizados, a partir da adoção de IPSec, inclusive, em redes internas.

Em segurança de rede não existe uma solução única, mas algumas medidas podem ser tomadas para reduzir a vulnerabilidade do TCP/IP (Basta, A; Basta, N. Brown, M. 2015:

- Alterar os valores padrão dos temporizadores para interromper o evitar ataques do tipo TCP SYN.
- Aumentar o número de conexões simultâneas que uma estação ou servidor pode suportar.
- Reduzir o tempo de escuta de SYN/ACK no processo de handshake triplo.
- Utilizar geradores de números aleatórios com o objetivo de gerar números de sequenciamento de conexão aleatório como forma de dificultar processos de adivinhação.
- Implantar regras de firewall que possuam filtrar e evitar pacotes fraudados.
- Utilizar autenticação e criptografias em sessões de switches e roteadores.
- Utilizar VPNs inclusive nas redes internas quando os dados são sensíveis para organização. Como por exemplo as VPNs IPSec. A VPN IPSec fornece os seguintes serviços de segurança aos usuários finais:
    - Criptografia de dados dos usuários, inclusive cabeçalho TCP.
    - Autenticação e integridade da mensagem.
    - Proteção, por exemplo, contra ataques de repetição.
    - Negociação de algoritmos de segurança e de chaves entre os entes autenticados

### Análise de tráfego TCP/IP com Wireshark

O Wireshark é uma ferramenta poderosa para análise de tráfego em redes de computadores que organiza o tráfego por protocolo. Ela faz o mesmo que o tcpdump, mas facilita a organização das informações por meio de uma interface gráfica, conforme mostrado na análise de tráfego HTTP com destaque para o cabeçalho TCP.

Por meio do Wireshark, todo o tráfego que entra e sai da sua interface pode ser monitorado. Se estamos numa rede com HUB, todo o tráfego pode ser monitorado. O mesmo não ocorre em redes com switches. Por outro lado, em redes wireless, como estamos em um ambiente compartilhado, todo tráfego wireless chega a sua interface. Portanto, ela pode ser usada tanto para fins de diagnóstico e resolução de problemas, mas também como uma ferramenta para fins escusos (Bullock, J; Parker, J. T, 2017).

![[Untitled 5 19.png|Untitled 5 19.png]]

### Filtros

Como pode ser visto a partir da figura anterior, o Wireshark permite realizar filtros baseados em protocolos, endereços IPs ou pilhas de protocolos. Alguns exemplos de filtros são mostrados na tabela que segue (Wireshark, 2020).

#### Filtros

|Filtro exemplo|Explicação|
|---|---|
|[[ip.src==192.168.1.2]]|Filtrar por IP de origem|
|[[ip.dst==192.168.1.10]]|Filtrar por IP de destino|
|[[ip.addr == 192.168.15.0-24]]|Filtrar IP por sub-rede|
|[[ip.addr == 192.168.15.145 and ip.addr == 52.109.108.44]]|Apresenta tráfego entre dois dispositivos|
|[[eth.addr = 00-50-7f-c5-b6-78]]|Filtra por MAC|
|[[tcp.port==443]]|Filtrar pela porta TCP|
|[[udp.port==53]]|Filtrar pela porta UDP|
|[[tcp.flags.syn==1]]|Filtrar three way handshake|
|[[tcp.flags.syn == 1 and tcp.flags.ack == 0]]|Detecta SYN Floods|

  
  

> [!important]  
> Para conhecer um pouco mais sobre o Wireshark e seus filtros consulte: https://wiki.wireshark.org/DisplayFilters