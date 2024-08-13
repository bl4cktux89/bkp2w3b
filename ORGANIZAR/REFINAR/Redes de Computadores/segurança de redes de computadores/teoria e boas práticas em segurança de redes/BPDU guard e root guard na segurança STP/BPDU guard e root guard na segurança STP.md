### **Introdução**

O protocolo STP (Spanning Tree Protocol) é de fundamental importância para manter a rede sem loops quando se utiliza comutadores. Para manter a consistência da rede o STP monitora constantemente a rede identificando possíveis conexões redundantes. Caso seja descoberto um caminho redundante, o STP elegerá um desses caminhos como o primário e desativando o caminho secundário, conforme ilustrado na figura que segue. Caso ocorra a inoperância do caminho primário, o caminho secundário torna-se ativo, mantendo assim a conectividade da rede.

Acontece que, dependendo de como se implementa o STP e de como estão configuradas as portas de um switch, o atacante pode explorar o processo de eleição de switch raiz (root-bridge) inserindo um switch falso que encaminha quadros de controle STP, tornando-se o switch raiz da topologia. As implicações desse tipo de ação podem ser catastróficas para uma organização, indo desde a inoperância da rede até o roubo de dados.

Para mitigar tais ataques, recursos como BPDU guard e Root guard são necessários, como será visto no decorrer da presente aula (Filippetti, Marco Aurélio, 2017).

![[Untitled 90.png|Untitled 90.png]]

### **Fundamentos do STP e suas vulnerabilidades**

Dentro de um mesmo domínio de broadcast, o STP necessita eleger um switch como raiz da árvore STP, uma vez eleito, todas as suas portas são denominadas portas designadas, ou seja, enviam e recebem quadros normalmente. Os demais switches são considerados não raiz.

Por outro lado, as portas dos switches da rede recebem uma designação específica, como resumido abaixo (Filippetti, Marco Aurélio, 2017):

- **Porta raiz:** todas as portas dos switches não raiz (non-root bridges) que possuem o menor custo para o switch raiz são denominadas portas raiz (root-port), e encaminham e recebem quadros. Em outras palavras, por tais interfaces se chega mais rapidamente ao switch raiz.
- **Portas designadas:** Todas as portas de um switch raiz são denominadas portas raiz, assim como as portas as demais portas de um switch não raiz que possui portas raiz.
- **Portas bloqueadas:** As portas bloqueadas, também conhecidas como portas não designadas, não recebe frames de dados, mas podem receber frames de controle chamados de BPDU (Bridge Protocol Data Units) do STP, para que, em caso de indisponibilidade de um outro link, a porta pode passar para o estado ativo, enviando e recebendo frames.

### Determinação do switch raiz (root-bridge)

Por meio da troca de BPDUs, em multicast entre os switches, ocorre a eleição do root-bridge e também são propagadas informações do custo das portas até o switch raiz. Na figura abaixo é mostrado o formato da mensagem BPDU e na sequência o significado de cada campo. Neste processo pode ser encaminhado BPDUs de configuração ou TCN (topology change notification). O TCN é utilizado quando há alteração na topologia, como, por exemplo, em momentos de indisponibilidade de um enlace ou switch.

Inicialmente, todos os switches se consideram root-bridge, mas a medida em que eles recebem BPDUs de outros switches, eles comparam o BID recebido dos demais switches com o seu próprio. Ao final desse processo, aquele que possuir o menor BID é eleito o switch raiz.

![[Untitled 1 54.png|Untitled 1 54.png]]

1. Protocol ID: Identifica o algoritmo spanning tree e o protocolo. 2 bytes.
2. Version: Versão do protocolo. 1 byte.
3. Message Type: identifica o tipo de quadro. BPDU de configuração ou TCN. 1 byte.
4. Flags: indica o índice de BPDU em caso de alteração na topologia. São eles: TC (Topology Change Notification), utilizado para reconhecer mudança na topologia, e TCA (Topology CHange Notification Acknowledgment), utilizado para informar que os dados contidos no BPDU foram lidos e salvos pelo switch.
5. Root ID: ID da ponte do switch raiz. 8 bytes.
6. Root Path Cost: Custo acumulado até o switch raiz. 8 bytes.
7. Bridge ID: Identificador da ponte. 4 bytes.
8. Port ID: Identificador da porta. 2 bytes.
9. Max Age: Tempo que o switch espera antes de concluir que a topologia mudou. 2 bytes.
10. Foward Delay: Tempo que a porta leva para mudar de estado. 2 bytes
11. Message Age: Tempo para anunciar o BPDU. 2 bytes
12. Hello Time: Tempo gasto para o switch publicar o BPDU. Corresponde a 2 segundos.

**Exemplo**

No exemplo abaixo todos os switches estão com o mesmo valor de prioridade da bridge (32.768), mas possui o switchA possui o menor endereço MAC tornando-se, portanto, o root-bridge. Por outro lado, suas interfaces ficam no estado Designado (D). Os switches non-root (SwitchB e SwitchC) por sua vez, tem suas interfaces diretamente conectadas a root-bridge configuradas como root-port (R), pois através dessas interfaces o custo é menor.

No entanto, a interface conectada ao switchC fica no estado não-designado (NDP), já que possui o maior endereço MAC do que o switchB, que por sua vez, o switchB fica com sua interface conectada ao switchC no estado Designado, para que, caso ocorra falha entre no link entre o switchC e o root-bridge, a interface no estado NDP passará automaticamente para o estado R.

![[Untitled 2 43.png|Untitled 2 43.png]]

### Vulnerabilidade e ataque ao STP

Existem vulnerabilidades inerentes a arquitetura STP em função da sua simplicidade e da falta de autenticação dos frames trocados durante o processo eleição do root-bridge e das informações de custo de porta.

Imagine o cenário no qual um switch "falso" com prioridade igual a 0 ou até mesmo com mesma prioridade, mas com endereço MAC menor seja inserido na rede, ou seja, menor BID da topologia. Ele pode ser eleito o root-bridge da topologia, afetando complementarmente a forma como os pacotes serão encaminhados, inclusive, podendo ser direcionados para o dispositivo do atacante.

Existe também o cenário no qual um switch não gerenciado, de forma propositada ou não, é adicionado a rede com o objetivo de estender o alcance, sendo eles incapazes de modificar o seu BID, podem vir a afetar a árvore STP (Labcisco, 2020).

**SAIBA MAIS...**

Saiba mais

A ferramenta Yersinia objetiva realizar ataques da camada 2. Ele foi projetado para tirar proveito de algumas fraquezas inerentes aos protocolos de rede, dentre eles, o STP, CDP, DTP, DHCP, HSRP, 802.1q e 802.1x. Ele finge ser um equipamento, por exemplo, um switch para analisar e testar as redes e sistemas implantados. Para ter mais informações acesse: [**https://tools.kali.org/vulnerability-analysis/yersinia**](https://tools.kali.org/vulnerability-analysis/yersinia)

### Como se proteger?

Os recursos disponíveis nos switches podem variar de fabricante para fabricante e também de modelo, mas, geralmente, switches de boa qualidade oferecem os seguintes recursos (Labcisco, 2020):

- **Root Guard:** o recurso Root Guard, habilitado na interface, permite colocar uma interface em blocking (root inconsistent) caso ela receba um BPDU superior, indicando um caminho melhor até o switch root. Nesse caso, a interface só voltará a funcionar se ela parar de receber tais BPDUs. O recurso Root Guard deve ser ativado individualmente em cada uma das interfaces, conforme mostrado abaixo:

`1.` `Sw1(config-if)# spanning-tree guard root`

- **PortFast e BPDU guard:** As portas de um switch com STP habilitado passam por vários estágios antes de passar para o estágio de forwarding (encaminhando). Este pode ser demorado, e para torná-lo mais rápido, ?pulando estágios intermediários?, o recurso PortFast pode ser habilitado em portas de ACESSO (Edged Port), dessa forma, uma porta passa de blocking (bloqueado) para forwarding. Com o PortFast habilitado, o recurso BPDU guard também deve ser habilitado. O BPDU guard coloca uma interface em erro-desativado (errdisabled) caso ela receba BPDU nessas interfaces. Este recurso está associado com o Port Fast epode ser ativado globalmente e por interface, conforme mostrado abaixo.

`1.` `# Ativação do Port Fast #` `2.` `Sw1(config-if)# spanning-tree portfast` `3.` `# Ativação do BPDU Guard - Global #` `4.` `sw1(config)# spanning-tree portfast bpduguard enable` `5.` `# Ativação do BPDU Guard #` `6.` `sw1(config-if)# spanning-tree bpduguard enable`

- **Loop Guard:** Quando um switch não raiz tem caminhos redundantes para o root-bridge, uma de suas portas fica no estado bloqueado, mas continua recebendo BPDU. Caso os anúncios BPDUs, por falha ou algum outro motivo parem de chegar ao switch, ele assume que não mais não há a necessidade de bloquear a porta, já que para ele não existe mais um dispositivo STP do outro lado.Para prevenir tal situação o recurso Loop Guard monitora as interfaces bloqueadas e os anúncios de BPDU. Caso a interface pare de receber os anúncios, o Loop Guard coloca a interface em estado _**loop-inconsistent.**_  Se o recebimento é normalizado a interface volta ao seu estado anterior. Este recurso pode ser ativado por interface ou globalmente por meio dos comandos mostrados abaixo.

`1.` `# Global #` `2.` `Sw1(config)# spanning-tree loopguard default` `3.` `# Por interface #` `4.` `sw1(config-if)# spanning-tree guard loop`

- **Loopback Detection:** Detecta se uma interface recebeu pacotes que ela mesmo gerou como, por exemplo, gerada por um HUB ou um loopback de cabo. Quando isso ocorre, a interface é bloqueada.

`1.` `sw1(config-if)# loopback-detection enable`

### Tempestade de broadcast (Broadcast Storm)

Um dos problemas de segurança que uma rede pode enfrentar está relacionado com a tempestade de broadcast, quando uma quantidade excessiva de tráfego de broadcast ou multicast é gerada. Todos os dispositivos que estiverem no domínio de broadcast sofrerão as consequências, sejam eles, PC, switches e servidores, já que todos os dispositivos precisam parar para responder, por exemplo, uma solicitação ARP, ou mesmo uma solicitação DHCP (Yersinia, 2020).

![[Untitled 3 29.png|Untitled 3 29.png]]

As tempestades de broadcast podem ser provocadas por problemas na placa de rede, switches sem STP configurado e, principalmente, um software malicioso, como o Yersinia.

Para reduzir ou mitigar possíveis ataques que exploram a tempestade de broadcast é necessário, primeiramente, ter uma rede bem estruturada em termos lógicos e físicos e bastante monitoramento. Por outro lado, os switches trazem um recurso interessante que estabelece limites para broadcast, multicast e até mesmo unicast. O exemplo abaixo mostra o processo de configuração do recurso Storm-Control no switch.

Por meio do recurso Storm-Control você pode definir o tipo de tráfego que deseja estabelecer limites (linhas 1 a 5) . É também é possível definir o limite aceitável desse tráfego em uma interface e a ação, conforme abaixo. Os limites podem ser definidos em bps, pps e porcentagem de uso da interface. No exemplo abaixo foi definido o valor de 30%, tendo como ação padrão o descarte do pacote caso ultrapasse esse limite.

`1.` `SW1(config-if)\#storm-control ?` `2.` `action Action to take for storm-control` `3.` `broadcast Broadcast address storm control` `4.` `multicast Multicast address storm control` `5.` `unicast Unicast address storm control` `6.` `SW1(config)\#interface FastEthernet0/1` `7.` `SW1(config-if)#storm-control broadcast level ?` `8.` `<0.00 - 100.00> Enter rising threshold` `9.` `bps Enter suppression level in bits per second` `10.` `pps Enter suppression level in packets per second` `11.` `SW1(config-if)#storm-control broadcast level 30`

### Atividade

A atividade que segue tem por objeto estabelecer qual é o switch root da topologia, prevenir ataques ao STP, além proporcionar a prática na segurança de porta. Para tanto, você deve baixar o arquivo com extensão .pka e executar o que se pede. No arquivo pdf encontra-se o gabarito da atividade.

Para executar essa atividade você deve ter instalado o Packet Tracer 7.3 ou superior.