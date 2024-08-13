### Introdução

Quando se fala em mecanismos de segurança, logo se vem a mente os Firewalls, antivírus, IDS e IPS, com vistas a oferecer proteção entre a rede local e a internet e proteção dos serviços contidos nos servidores e estações. Mas, muitas vezes, os administradores de redes negligenciam a segurança na camada 2 (Enlace de dados), não dando a devida importância aos equipamentos da rede interna, principalmente os switches.

Isso se deve, principalmente, a tendência em supor que a maior parte das ameaças tem origem na Internet. Isso não deixa de ser verdade, porém, nos últimos tempos, tem crescido o número de ataques que exploram as vulnerabilidades decorrentes da lógica de funcionamento na camada de Enlace, principalmente dos switches e do modo de aprendizado dos endereços MACs.

Proteger a camada 2 tem impacto direto sobre as camadas superiores, protegendo muitas vezes, os serviços que estão ativos na camada de Aplicação, como será demonstrado no decorrer do presente tópico.

![[Untitled 87.png|Untitled 87.png]]

### Vulnerabilidades na Camada 2

As vulnerabilidades na camada 2 são decorrentes do funcionamento dos switches e da lógica de descobertas de dispositivos dentro da rede. Por isso, devemos entender como esses processos ocorrem para entender as vulnerabilidades (Cisco Systems, 2020).

Vamos começar pelo aprendizado de endereços MACs. Em uma rede de computadores, sempre que um pacote é enviado de um host A para o Host B, é preciso conhecer endereços IPs e MACs de destino. Em redes IPv4 esse processo ocorre por meio do envio, em broadcast, de pacotes ARP (Address Resolution Protocol - Protocolo de Resolução de Endereços), enquanto no IPv6 a descoberta ocorre por meio do envio de mensagens, em multicast, NDP (Neighbor Discovery Protocol - Protocolo de Descoberta de vizinho).

O switch por sua vez, ao receber este tipo de mensagem, propaga por todas as suas interfaces, já que o campo de destino do quadro possui o endereço MAC de destino um endereço MAC de Broadcast/Multicast. Por sua vez, os dispositivos de rede que possui aquele endereço IP de destino, responde a solicitação, por meio de uma mensagem ARP/NDP, em unicast, com o seu próprio endereço MAC. Esse processo é ilustrado na figura que segue, onde o PC com IP 192.168.0.1  envia um ARP Request em broadcast .

![[Untitled 1 51.png|Untitled 1 51.png]]

O switch por sua vez, ao receber este tipo de mensagem, propaga por todas as suas interfaces, já que o campo de destino do quadro possui o endereço MAC de destino um endereço MAC de Broadcast/Multicast. Por sua vez, os dispositivos de rede que possui aquele endereço IP de destino, responde a solicitação, por meio de uma mensagem ARP/NDP, em unicast, com o seu próprio endereço MAC. Esse processo é ilustrado na figura que segue, onde o PC com IP 192.168.0.1  envia um ARP Request em broadcast.

Do ponto de vista da lógica de funcionamento do switch, os endereços MACs de origem são adicionados a sua tabela de endereços MACs, conhecida com  SAT/CAM (Content Addressable Memory - Memória Endereçável de Conteúdo) a medida em que os dispositivos trocam pacotes na rede, conforme ilustrado na figura que segue. Entretanto, quando os switches não possuem em sua tabela SAT/CAM o endereço MAC associado a uma de suas portas, ele realizar um broadcast, enviando estes quadros por todas as suas interfaces.

![[Untitled 2 40.png|Untitled 2 40.png]]

### Ataques na camada 2

A partir dessa lógica de aprendizado de endereços MACs por parte dos dispositivos finais e dos switches, surgem os seguintes ataques (Cisco System, 2020).

- **Falsificação de endereço (MAC Spoofing):** Quando um switch aprende um endereço MAC ele associa esse endereço a respectiva porta, mas se o atacante utiliza esse mesmo endereço MAC em outra porta, o switch atualiza a sua tabela CAM, retirando o endereço MAC associado a interface antiga e associa a nova interface, onde, normalmente, está o atacante.
- **Estouro da tabela MAC (MAC Address Table Overflow):** A tabela CAM é limitada, normalmente, associa até 128 endereços por interface e essa limitação pode ser explorada pelo atacante. Existem uma ferramenta chamada _**Macof**_  que, quando ativada na máquina do atacante, ela inunda a tabela CAM do switch com endereços MACs falsos a uma taxa de 155000 por minuto. O resultado prático disso é que o switch passa a comportar como HUB, já que ele não consegue encontrar o endereço MAC verdadeiro em sua tabela CAM.
- **Ataques de DHCP:** O atacante esgota todos os endereços IPs disponíveis no servidor DHCP a partir do envio do envio de solicitação DHCP com endereços MACs falso. Este ataque é conhecido DHCP Starvation e algumas literatura reporta como ataque de camada 3. Em associação a este tipo de ataque, após levar a inoperância do DHCP legítimo, o atacante insere na rede um servidor DHCP pirata (Rogue DHCP Server) e todas as solicitações DHCP, agora, serão respondidas pelo Rogue DHCP.
- **Ataques de ARP:** É uma técnica utilizada pelo atacante para associa o seu endereço MAC a um endereço IP da rede, geralmente de um gateway padrão. Isso faz com que, por exemplo, o tráfego a uma rede remota seja redirecionado para o computador do ataque. Este tipo de ataque é normalmente utilizado abertura para outros tipos de ataque como, por exemplo, Man-in-the-middle, negação de serviço ou sequestro de conexão.

### Como se prevenir?

Existem diversos recursos de segurança que tem por objetivo prevenir alguns efeitos causados pelos ataques vistos anteriormente. Cabe acrescentar que estes recursos variam de fabricante para fabricante, e muitas vezes, são até inexistentes, por isso, é importante verificar se o switch permite tais configurações, antes de implantá-los em rede. Veja abaixo algumas possibilidades (Cisco System, 2020):

- **Inspeção dinâmica de ARP (Dynamic ARP inspection):** analisa as características dos hosts conectados as interfaces do switch prevenindo spoofing de camada 2.
- **Inplementar autenticação 802.1x:** O protocolo 802.1x e os servidores de autenticação (RADIUS e Tacacs) permitem que apenas os dispositivos autenticados tenham acesso a rede. O 802.1x será visto em outro tópico.
- **Implementar DHCP snooping:** Este recurso configurado no switch permite filtrar mensagens DHCP, atribuindo status de não confiáveis/inválidas a partir da construção de uma tabela de uma DHCP Snooping Binding Table. A partir dessa tabela, sabe-se quais portas podem responder a solicitações DHCP (portas confiáveis conectadas ao servidor DHCP) e não confiáveis (portas que não deve responder à solicitações DHCP).
- **Implementar Storm control:** limita a quantidade de tráfego broadcast ou multicast enviados pelos switches na rede.
- **Implementar Segurança de porta (Port security):** limita o número de endereços MACs que o switch aprende por interface. Este tipo mecanismo de segurança pode prevenir ataques do tipo MAC flooding. Para exemplificar este mecanismo vamos criar a topologia abaixo no Packet Tracer.

### Laboratório: Configuração do port-security

Para exemplificar este mecanismo vamos criar a topologia abaixo no Packet Tracer. Siga as seguintes etapas.

1. **Etapa:** Crie a topologia conforme figura da esquerda. Utilize o switch genérico ou 2960.

![[Untitled 3 26.png|Untitled 3 26.png]]

1. **Etapa:** Configure os endereços IPs e realize um Ping do PC1 para o PC2, para verificar a conectividade. ATENÇÃO: Não conecte ainda o PC do ATACANTE  
2.  
**Etapa:** Adicione a configuração a seguir nas interfaces do switch. Na configuração abaixo a configuração será aplicada nas interfaces f0/1 a f0/5:

`1.` `Switch(config)# interface range f0/1-5` `2.` `Switch(config-if-range)# switchport mode access` `3.` `Switch(config-if-range)# switchport port-security` `4.` `Switch(config-if-range)# switchport port-security maximum 1` `5.` `Switch(config-if-range)# switchport port-security mac-address stick` `6.` `Switch(config-if-range)# switchport port-security violation shutdown`

**Explicação:**

- switchport mode access: A porta foi configurada em modo acesso, onde são conectados os dispositivos terminais;
- switchport port-security: Ativação da segurança de porta.
- switchport port-security maximum 1: informa ao switch que será aprendido apenas um endereço MAC.
- switchport port-security mac-address stick: mac-address stick permite o aprendizado dinâmico do endereço MAC. Como no comando anterior foi informado o aprendizado de apenas 1 endereço MAC (maximum 1), será aprendido apenas um endereço MAC. Obs: o endereço MAC do dispositivo pode ser adicionado estaticamente por meio do comando )# switchport port-security mac-address "endereço MAC".
- switchport port-security violation shutdown: A opção shutdown indica para o switch desligar a porta caso haja violação. Existem também o modo Protect (Proteger) que ignora os pacotes com endereços MACs desconhecidos ou aumente o número máximo de endereços permitidos. Neste caso não há notificação ao administrador. Outra opção é modo Restrict (Restringir), é semelhante ao anterior, mas você é notificado e contador de violação é incrementado.

1. **Etapa:** Realize novamente um ping entre os PC1 e PC2 para que os endereços MACs dos dispositivos sejam associados as respectivas portas.  
2.  
**Etapa:** Substitua o PC2 pelo PC do ATACANTE (Coloque o PC do ATACANTE na interface f0/1). Na sequência tente realizar um ping para o PC1. A porta agora deve ter sido desligada (shutdown).  
3.  
 **Etapa:** Verifique a situação geral do port-security e da interface por meio dos comandos:

`1.` `Switch# show port-security` `2.` `Switch# show port-security interface f0/1`

1. **Última Etapa:** Para ativar novamente a interface emita o comando shutdown e posteriormente no shutdown.