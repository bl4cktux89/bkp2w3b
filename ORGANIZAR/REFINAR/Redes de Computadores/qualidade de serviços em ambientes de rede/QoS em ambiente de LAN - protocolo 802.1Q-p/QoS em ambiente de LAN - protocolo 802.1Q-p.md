**Explicando a VLAN**

São redes locais independentes com domínios de broadcast separados mesmo utilizando um mesmo switch para conexão das suas estações (hosts ou computadores).

Uma VLAN é um domínio de broadcast que agrupa um conjunto de estações (hosts ou dispositivos de rede local), mesmo que essas estações estejam ligadas a diferentes switches da rede.

Com um ou mais switches podemos especificar grupos independentes de estações, e cada grupo formar uma VLAN independente das demais. As portas dos switches da rede são especificadas e agrupadas logicamente (virtualmente), simulando como se estivessem fisicamente conectadas em um único switch independente, ou seja, podemos, por exemplo, utilizar um único switch para montar três redes locais, especificando um conjunto de portas para a rede 1, um conjunto de portas para a rede 2 e outro conjunto de portas para a rede 3 e, assim, as três redes com três domínios de broadcasting independentes.

Neste exemplo, apesar de as três redes estarem ligadas a um único switch, operam como se cada uma tivesse um switch exclusivo. Dessa forma, evitamos que frames de broadcast de uma rede invadam outra rede. Isso é importante para redes corporativas grandes e com muitas redes locais em um mesmo domínio de colisão, pois permite separar esses domínios de colisão e resolver problemas de sobrecarga de tráfego na rede corporativa.

Portanto, as três redes locais não se comunicam entre si. Para que haja comunicação entre elas, é preciso agregar um roteador à rede com três portas ligadas às portas do switch, sendo uma porta para cada VLAN.

Cada VLAN possui uma tabela com a relação dos computadores que fazem parte dela e com os endereços das portas para chegar a esses computadores. Por exemplo, a VLAN 1 tem uma tabela no switch S1 com a relação dos endereços MAC dos hosts dela e a porta de acesso a ele

![[Screenshot_20220207_222549.png]]

As portas E1, E2 e E9 são Ethernet do switch S1 em que estão ligados os hosts ou outros switches. Se a porta E9, por exemplo, estiver ligada a outro Switch S2, o frame será encaminhado para esse outro switch, que verifica, em sua tabela, para qual porta deve reencaminhar o frame de forma que ele chegue ao host destino.

Dizemos que em um VLAN todos os dispositivos fazem parte de um mesmo domínio de broadcast, chamado, também, de rede plana.

O particionamento de uma grande rede local em várias VLANs por meio de switches basicamente evita que mensagens de broadcast consumam ou ocasionem perdas na largura de banda da rede (bandwidth).

**Definição de um tronco de VLAN**

Tronco é um link ponto a ponto entre dois dispositivos de rede que transporta mais de uma VLAN. Um tronco de VLAN permite estender as VLANs através de uma rede inteira. A Cisco suporta IEEE 802.1Q para coordenar troncos em interfaces Fast Ethernet e Gigabit Ethernet.

Lembre-se de que switches são dispositivos da **camada 2**. Eles só usam as informações de cabeçalho do quadro Ethernet para encaminhar pacotes. O cabeçalho do quadro não contém informações sobre a qual VLAN o quadro deve pertencer. Logo, quando os quadros Ethernet são colocados em um tronco, eles precisam de informações adicionais sobre as VLANs a que pertencem. Isso é feito usando-se o cabeçalho de encapsulamento 802.1Q.

No exemplo da criação de 3 VLANs, observamos que cada VLAN possui um link de acesso ao roteador. Nessa arquitetura, se tivermos um número grande de VLANS, teremos o mesmo número de links de conexão ao roteador. Para evitar um número muito grande de links físicos, podemos criar um único link físico pelo qual passarão todos os links de conexão de uma maneira lógica. Esse link físico, que transporta vários links lógicos, é chamado de trunk-link (tronco), utilizado para interligar switches ou para interligar switches a roteadores.

Os frames que passam pelo trunk-link devem ter uma identificação de frames _**(frame tagging)**_, chamada de VLAN ID e feita pelo switch quando envia um frame a outro switch por meio do trunk-link. Ela pode ser feita de diferentes modos:

- ISL (inter switch link): método proprietário da Cisco.
- IEEE-802.1q: método de etiquetamento de frames criado pelo IEEE, que insere um campo de identificação no frame.
- LANE (LAN emulation): método de comunicação para VLANs sobre ATM.
- IEEE-802.10 (FDDI): método de comunicação para VLANS sobre FDDI que insere um campo no header do frame para identificar a VLAN (campo SAID).

**IEEE, não ISL**

Embora um switch Cisco possa ser configurado para suportar dois tipos de portas de tronco, IEEE 802.1Q e ISL, hoje apenas o 802.1Q é usado. No entanto, redes antigas ainda podem usar ISL, sendo útil obter informações sobre cada tipo de porta de tronco:

- Uma porta de tronco IEEE 802.1Q suporta tráfego com e sem marcação simultaneamente. Ela recebe um PVID padrão e, além disso, todo o tráfego sem marcação percorre no PVID padrão de porta. Pressupõe-se que todo o tráfego com e sem marcação com uma ID de VLAN nula pertença ao PVID padrão de porta e um pacote com uma ID de VLAN igual ao PVID padrão de porta de saída é enviado sem marcação. Todo o tráfego restante é enviado com uma marcação de VLAN.
- Em uma porta de tronco ISL, todos os pacotes recebidos devem ser encapsulados com um cabeçalho ISL e todos os pacotes transmitidos são enviados com um cabeçalho ISL. Os quadros nativos (sem etiqueta) recebidos de uma porta de tronco ISL são descartados. ISL deixa de ser um modo de porta de tronco recomendado, não sendo suportado em vários switches Cisco.

**VLANs recomendados pelos Protocolos IEEE**

- 802.1D – Spanning Tree.
- 802.1w – Fast Spanning Tree.
- 802.1Q – VLAN Trunking.
- 802.1p – QoS nível 2.
- 802.3ad – Link Aggregation.

**Recomendações**

- IEEE 802.1Q: define o funcionamento de VLANs. É um protocolo para interface Trunk.
- IEEE 802.1p: define o uso do campo prioridade.

**Spanning Tree Protocol: STP**

- Quando os switches colocados em cascata formam caminhos com loops fechados, o encaminhamento de quadros pode levar ao congestionamento da rede.
- O STP é um protocolo de camada 2 utilizado para prevenir a ocorrência desses loops.
- O STP utiliza um protocolo chamado BPDU: (BPDU: Padrão IEEE 802.1D – Bridge Protocol Data Unit).
- Mensagens em Multicast (MAC).

**Modos e protocolos de Spanning Tree**

**PVST+**

- Protocolo da Cisco baseado no IEEE 802.1d.
- Usa um algoritmo de STP por VLAN.

**Rapid PVST+: (RSTP)**

- Convergência rápida baseada no IEEE 802.1w.
- Apaga imediatamente as entradas MAC após uma mudança de topologia ao invés de aguardar o aging-time de 5 minutos.

**MSTP**

- Baseado no padrão IEEE 802.1s.
- Permite mapear múltiplas VLANs em uma única instância de STP.
- Executado sobre o RSTP (IEEE 802.1w) (uso obrigatório).

**MSTP – Multiple Spanning-Tree Protocol**

- MSTP: IEEE 802.1s.
- Melhora a tolerância a falhas.
- Múltiplos forwarding paths.
- Permite balanceamento de carga.
- Mais escalabilidade que o PVST.