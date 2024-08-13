### **Introdução a Camada de Internet**

A camada de Internet também é conhecida como camada de Rede. Esta camada proporciona o encaminhamento dos pacotes da origem para o destino por meio de roteadores localizados ao longo do caminho. Esse processo ocorre salto a salto, ou roteador por roteador.

Diferentemente da camada de enlace de dados, que tem por função mover os dados da extremidade de um enlace até a outra, na camada de rede, os roteadores têm que conhecer a rede de uma forma mais abrangente, ou seja, deve conhecer a topologia com precisão para escolher o melhor caminho. Além disso, a camada de rede deve evitar caminhos sobrecarregados em detrimento de um caminho ocioso. Portanto, podemos resumir a as funcionalidades da camada de rede da seguinte forma (Tanenbaum, Andrew S e Wetherall, 2011):

- Identificação lógica de redes por meio de endereços IP (Internet Protocol, Protocolo de Internet) e dos dispositivos a ela conectados.
- Determinação do melhor caminho para um determinado destino com base nesses endereços.
- Roteamento dos pacotes, ou comutação de pacotes de dados de um domínio lógico a outro.
- Garante a compatibilidade entre os diferentes tipos de protocolos definidos na camada de enlace.
- Prove a interface de rede unificada, permitindo que qualquer protocolo de aplicação seja usado nas camadas superiores ou inferiores.
- Proporciona a entrega dos pacotes com o melhor esforço possível.
- Comunicação fim-a-fim.

### Comutação de Pacotes

Um dos principais processos presentes na camada de internet é conhecido como comutação de pacote, que consiste no transporte dos pacotes por um caminho não determinado, já que as condições da rede variam constantemente. Isso quer dizer que um e-mail que você envia na internet é dividido em pequenos fragmentos, chamados pacotes, e cada um desses pacotes pode ser encaminhado por diferentes caminhos, e no final, eles são reorganizados pelos destinatários, conforme mostrado na Figura 1. Esse processo de comutação ocorre nos roteadores e para tanto, ele utiliza o endereço IP de destino contido no pacote para encaminhar para o destinatário, semelhante ao que ocorre com o envio de uma carta pelo correio.

Nenhuma camada do modelo TCP/IP, seja ela superior ou inferior interfere no processo de comutação de pacotes ou de roteamento. Isso quer dizer que o processo de determinar o melhor caminho na internet é exclusivo da camada de internet.

![[Untitled 34.png|Untitled 34.png]]

### Protocolos da camada de Internet

Basicamente, coexistem na camada de internet quatro protocolos. São eles:

- Internet Protocol (IPv4 e IPv6)
- Internet Control Message protocol (ICMP)
- Address Resolution Protocol (ARP)
- Reverse Address Resolution Protocol (RARP)

### O Protocolo IP

O protocolo IP é o mais importante da camada de Internet e define muito bem o funcionamento dessa camada. A importância desse protocolo é tão grande que os demais mais protocolos desta camada existem apenas para suportá-lo. O protocolo IP é utilizado para identificar de maneira lógica os dispositivos da rede, dentre eles, os computadores roteadores, servidores de aplicações, etc., por isso, ele é conhecido como endereço lógico, enquanto que o MAC é chamado de endereço Físico.

O endereço IP não é utilizado apenas para identificação lógica dos equipamentos (hosts), ele também é utilizado para identificar em qual rede o host está. Em outras palavras, quando pensamos no endereçamento IP temos que ter em mente que ele informará quem é o host e em qual rede ele está. Podemos fazes uma analogia com o endereço de um telefone celular, por exemplo ex. 11-95555-5555. Por meio desse endereço conseguimos identificar o número do assinante (95555-5555) e também a rede (11). Essa tarefa é executada pelos roteadores para identificar qual é a rede de destino que deve ser alcançada.

### Cabeçalho do protocolo IP

Quando camada de internet recebe os dados da camada de transporte (segmento), ela encapsula os dados em um pacote que contém várias informações, dentre elas, o endereço IP de origem e destino. Essas informações são importantes para que os dispositivos de rede possam tomar decisão de encaminhamento. Na figura abaixo é mostrado o cabeçalho IPv4 e seus campos (A versão 6 do protocolo IP não será abordada neste tópico). Cabe salientar, que a extensão do cabeçalho IP é de 20 bytes.

![[Untitled 1 24.png|Untitled 1 24.png]]

Cada campo que compõe o cabeçalho IPv4 é detalhado abaixo (Kurose, James F e Ross, W. Keith, 2013):

- Version: versão do protocolo IP (pode ser 4 ou 6). Mas o cabeçalho IPv6 é completamente diferente e não será abordado no presente tópico
- Comprimento do Cabeçalho (IHL) - Especifica o tamanho efetivo do cabeçalho do pacote.
- Prioridade ou Tipo de Serviço (TOS) - O campo Tipo de Serviço contém um valor binário de 8 bits que é usado para determinar a prioridade de cada pacote. Este valor permite que um pacote receba uma prioridade para que seja processado mais rapidamente. Este mecanismo permite estabelecer Qualidade de Serviço (QoS).Um roteador de rede pode, por exemplo, processar mais rapidamente uma chamada de voz sobre IP (VoIP).
- Comprimento total do Pacote - Este campo fornece o tamanho total do pacote em bytes, incluindo o cabeçalho e o campo de dados da camada de aplicação.
- Identificação - Este campo é usado principalmente para identificar unicamente os fragmentos de um pacote IP original.
- Flag Mais Fragmentos - A flag Mais Fragmentos (MF) é um único bit no campo Flag usado com o Deslocamento de Fragmentos na fragmentação e reconstrução de pacotes. O bit da flag Mais Fragmentos é configurado, o que significa que ele não é o último fragmento de um pacote.
    - MF = 1: Quando um host de destino vê um pacote chegar com MF = 1, ele examina o Deslocamento de Fragmentos para ver onde este fragmento deve ser colocado no pacote reconstruído.
    - MF= 0: Quando um host de destino recebe um quadro com MF = 0 e um valor diferente de zero no Deslocamento de Fragmentos, ele designa este fragmento como a última parte do pacote reconstruído. Um pacote não fragmentado possui todas as informações de fragmentação iguais a zero (MF = 0, deslocamento de fragmentos = 0). 
- Flag Não Fragmentar - A flag Não Fragmentar (DF) também possui apenas um único bit no campo Flag, consequentemente duas possibilidades:
    - Fragmentar: Se definida como 0 a fragmentação do pacote é permitida. O roteador pode fragmentar o pacote e passar para a camada de enlace de dados.
    - Não Fragmentar: Se o Não Fragmentar for configurado, a fragmentação do pacote NÃO será permitida. Se um roteador precisar fragmentar um pacote para permitir que ele passe para a camada de enlace de dados e o bit DF estiver definido como 1, o roteador descartará o pacote.
- Deslocamento de Fragmento – Um roteador pode precisar fragmentar um pacote, ou seja, definir a Flag como 0. Ao realizar o processo de comutação de uma interface física para outra que tenha uma MTU (unidade máxima de transmissão) menor. Quando ocorre essa fragmentação, o pacote IPv4 usa o campo Deslocamento de Fragmento e a flag MF no cabeçalho IP para reconstruir o pacote quando ele chega ao host de destino, identificando cada seguimento fragmentado.
- Tempo de Vida (TTL) - O TTL é um valor binário de 8 bits que indica o "tempo de vida" restante do pacote. O valor TTL diminui em pelo menos um a cada vez que o pacote é processado por um roteador (ou seja, a cada salto ou hop). Quando o valor chega a zero, o roteador descarta ou abandona o pacote e ele é removido do fluxo de dados da rede. Este mecanismo evita que os pacotes que não conseguem chegar a seus destinos sejam encaminhados indefinidamente entre roteadores em um loop de roteamento.
- Protocolo - O valor binário de 8 bits indica o tipo de payload de dados que o pacote está carregando. O campo Protocolo possibilita que a camada de rede passe os dados para o protocolo apropriado das camadas superiores, neste caso para a camada de transporte.Alguns exemplos de valores:
    - 01 ICMP
    - 06 TCP
    - 17 UDP
- Checksum do Cabeçalho - O campo de checksum é usado para a verificação de erros no cabeçalho do pacote. Um roteador ao processar um pacote pode introduzir alguma inconsistência do cabeçalho. Este valor é ajustado e verificado em cada salto
- Endereço IP de Origem - O Endereço IP de Origem contém um valor binário de 32 bits que representa o endereço do host de origem do pacote da camada 3.
- Endereços IP de Destino - O Endereço IP de Destino contém um valor binário de 32 bits que representa o endereço do host de destino do pacote da camada 3.
- Opções - Há uma provisão para campos adicionais no cabeçalho IPv4 para oferecer outros serviços, mas eles raramente são utilizados.

### Protocolo ICMP

O protocolo ICMP (Internet Control Message Protocolo) é definido na camada de Internet e é utilizado pelo protocolo IP como um “mensageiro” e tem como objetivo fornecer relatórios de erros a fonte solicitante da informação. O comando PING é um recurso do ICMP e por meio dele é possível descobrir se um host está ativo na rede ou, até mesmo, o tempo de ida e volta de um pacote, conforme mostrado na figura abaixo.

![[Untitled 2 22.png|Untitled 2 22.png]]

Entre os eventos e mensagens de erro enviadas pelo ICMP mais comuns, podemos destacar (Filippetti, Marco. A., 2017):

- **Tipo 0:** Echo Reply (resposta do PING): O computador envia um echo request (solitação de ping) e espera receber um echo reply, conforme o **ping ava.uninove.br.** Caso não receba, a mensagem de erro "**estotado o tempo limite do pedido**" será motrada, conforme o **ping 10.255.255.254** da figura acima.
- **Tipo 3:** Destination unreachable (destino inalcançável): O destino não pode ser alcançado devido a máquina não está acessível ou a rede não está acessível ou o protocolo não está acessível.
- **Tipo 8:** Echo Request (soliticão PING): Envio da solicitação de ping.
- **Tipo 11**: Time Excced (TTL excedido): O tempo de vida de um datagrama experiou ou tempo de remotangem dos fragmentos expirou ou o campo de um parâmetro está errado.
- **Tipo 30:** Traceroute: Fornece o mapeamento dos saltos (dispositivos de camada 3) da origem até o destino. A figura abaixo mostra uma saída do comando _**tracert**_ (no Windows) para o site ava.uninove.br.

![[Untitled 3 16.png|Untitled 3 16.png]]

### Protocolos ARP e RARP

Apesar dos protocolos ARP e RARP serem definidos como de camada de enlace, é importante tratarmos deles a partir da camada de internet, tendo em vista que eles fornecem suporte para o protocolo IP e ficaria difícil de trata-los de maneira separada.

**Protocolo ARP**

O protocolo ARP (Address Resolution Protocolos, Protocolo de Resolução de Endereços) é utilizado, como o próprio nome diz, para mapear um endereço de rede (por exemplo, IPv4) para um endereço físico, como por exemplo, o endereço MAC. Este protocolo é de fundamental importância para a dinâmica de uma rede, permitindo que o endereço físico e lógico corresponda a exatamente ao dispositivo de destino. Este processo é ilustrado na figura abaixo.

![[Untitled 4 16.png|Untitled 4 16.png]]

O formato do cabeçalho ARP é mostrado abaixo. Em uma solicitação ARP ou RARP (veremos na sequência), preenchem apenas os campos necessários para a sua solicitação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635326/38284.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635326/38284.png)

Campos de uma mensagem ARP e RARP (Tanenbaum, Andrew S e Wetherall, 2011):

- **HardwareType** – Especifica o tipo do hardware. O valor é 1.
- **Protocol Type** – Especifica o tipo do protocolo usado. IP é 0800h, ARP é 0806h.
- **HardwareLen** – Define o comprimento em bytes (6 para ethernet) do endereço de hw (físico).
- **ProtocolLen** – Define o comprimento em bytes (4 para IP) do endereço de protocolo (lógico).
- **Operation** – Tipo da operação. Duas possíveis: 1 – pergunta e 2 – resposta.
- **SenderHardwareAddr** – Endereço físico de quem está enviando o pacote.
- **SenderProtocolAddr** – Endereço lógico de quem está enviando o pacote.
- **TargetHardwareAddr** – Endereço físico desejado. Na operação de request, vai em branco.
- **TargetProtocolAddr** – Endereço lógico desejado preenchido na resposta.

**Funcionamento do ARP**

Quando o PC-A deseja se comunicar com o PC-C, ele precisa do endereço IP e o do endereço MAC. Normalmente as aplicações de rede fornecem o endereço IP, resta agora descobrir o endereço MAC. Para tanto, as seguintes etapas são necessárias:

1. O PC-A verifica a sua tabela ARP para saber se existe o mapeamento do endereço IP para o MAC, conforme mostrado abaixo. Por meio do comando **arp -a** no Windows e Linux é possível observar esse mapeamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635315/38285.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/6/3/5/3/1635315/38285.png)

1. Caso exista o mapeamento, ele encapsula o pacote e envia para o PC-C.
2. Caso contrário, o PC-A envia na rede uma solicitação ARP (ARP Request) contendo as informações de origem e destino, contendo o IP do destinatário e com o endereço MAC de destino definido como FF-FF-FF-FF-FF-FF (broadcast de camada de enlace), já que ele não possui o endereço MAC de PC-C (É exatamente o que ele precisa).
3. O PC-C recebe esta solicitação e a responde para o PC-A com a informação do seu MAC.
4. O PC-A, agora, armazena esse endereço na sua tabela ARP para futuras transmissões.

Cabe acrescentar que este protocolo só faz sentido dentro de um mesmo segmento, e quando uma solicitação ARP chega a interface de um roteador, ele não o encaminha para os demais segmentos. Quando um host necessita envia dados para segmentos de rede para outro, o roteador receberá essa solicitação (já que ele o Gateway Padrão que interliga as diferentes redes) e fornecerá o seu próprio endereço MAC para o dispositivo de origem, num processo conhecido como Proxy ARP.

**Protocolo RARP**

O Protocolo de Resolução Reversa de Endereços (RARP), assim como o ARP, atua na camada de enlace de dados, permitindo conhecer o endereço IP de um dispositivo a partir do endereço MAC. Você deve estar se perguntando quando o RARP é utilizado?

O RARP é utilizado por dispositivos da rede possuem o seu próprio endereço MAC, mas não possuem o próprio endereço IP. Isso ocorre em dispositivos em dispositivos conhecidos como “terminal burro” ou diskless (sem disco). Nesse caso o dispositivo não possui HD e, consequente, não possui endereço IP, como RARP trabalha na camada de enlace, ele faz uma solicitação RARP para o servidor habilitado a responder uma solicitação RARP.

### Simulação

Na simulação a seguir veremos:

- Configuração básica do simulador Packet Tracer;
- Funcionamento do Hub;
- Funcionamento da tabela CAM do switch;
- Protocolo ICMP