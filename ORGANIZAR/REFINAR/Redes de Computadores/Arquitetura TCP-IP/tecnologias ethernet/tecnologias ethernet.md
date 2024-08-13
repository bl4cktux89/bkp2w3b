### Introdução

As redes LAN Ethernet foram desenvolvidas em meados de 1970 por Bob Metcalfe e David Boggs. Durante a década de 1980 e inicio da década de 1990 ela disputava o mercado com outras tecnologias LAN, como token-ring, FDDI e ATM. Nesse período, usava-se um barramento com cabo coaxial para interconectar os nós e por este motivo, a transmissão ocorre em broadcast e todos os nós recebem os quadros e os processam. No final da década de 1990 a maioria das organizações utilizavam Ethernet, utilizando a topologia estrela baseada em um hub também em modo broadcast. Neste caso, quando uma interface do hub recebe um quadro, o mesmo é propagado por todas as demais interfaces. Cabe acrescentar que, caso duas interfaces recebam um quadro simultaneamente, uma colisão seria detectada, provocando uma interrupção em toda a rede.

No começo dos anos 2000, as redes LAN passaram por uma grande evolução com a substituição dos hubs por comutadores, também conhecidos por switches. Os switches diferentes dos hubs operam na camada 2, enquanto que os hubs na camada 1, tendo como principal vantagem em relação ao hub a eliminação das colisões, além de possuir mecanismos de armazenamento e encaminhamento dos quadros (KUROSE, James F).

O sucesso da Ethernet deve-se aos seguintes fatores, segundo KUROSE, James F:

- Simplicidade e facilidade de manutenção
- Capacidade de introdução de novas tecnologias
- Confiabilidade
- Instalação e atualização econômicas

Em relação ao modelo TCP/IP e o modelo OSI, a Ethernet opera na metade inferior da camada de enlace de dados, conhecida como subcamada MAC e opera também na camada Física, conforme mostrado na Figura abaixo.

![[Untitled 33.png|Untitled 33.png]]

### Estrutura do quadro Ethernet

Quando dois dispositivos dentro de uma rede LAN trocam dados, há na verdade a troca de quadros Ethernets. Dentro do quadro Ethernet existem vários campos, conforme mostrado na abaixo. Um desses campos, **campo de dados**, corresponde aos dados úteis provenientes do datagrama IP da camada de Internet. Outro campo muito importante do quadro ethernet é o campo de endereço MAC de origem e destino. Os demais campos são mostrados na tabela 1, como base nos campos do quadro Ethernet IEEE 802.3 e do Ethernet II utilizado pelo protocolo TCP/IP.

![[Untitled 1 23.png|Untitled 1 23.png]]

![[Untitled 2 21.png|Untitled 2 21.png]]

As primeiras versões de Ethernet eram particularmente lentas, com velocidades que não passavam de 10 Mbps. Atualmente, existem padrões Ethernets de até 100 Gbps, conforme será visto mais a frente.

### Endereço MAC

Um endereço MAC da Ethernet da camada 2 possui 48 bits (6 bits) expresso com 12 dígitos hexadecimais, conforme mostrado na figura abaixo. O IEEE (Instituto de engenharia elétrica e eletrônica) definiu as regras para compor esse endereço:

Os primeiros 3 bytes do endereço devem ser definidos para o OUI (identificador Organizacionalmente exclusivo), em outras palavras, por exemplo, definirá o fabricante da placa de rede, que para o nosso exemplo, pertence a Cisco System.

Os últimos 3 bytes devem receber um valor exclusivo para um mesmo OUI.

![[Untitled 3 15.png|Untitled 3 15.png]]

Processamento do quadro Ethernet

Todos os dispositivos em uma rede Ethernet, tais como, servidores, impressoras, switches e impressoras devem possuir endereços MACs para enviara enviar e receber. Tendo como exemplo a rede da figura abaixo, um dispositivo A que deseja enviar para o dispositivo B deve conhecer o endereço MAC do dispositivo B. supondo que ela já conheça, o dispositivo A encapsulará o quadro e o enviará pela rede e caso a rede esteja interligada por meio de um hub todos os dispositivos receberam o quadro e verificará a correspondência do endereço MAC de destino com o seu próprio endereço, caso não exista a correspondência, os dispositivo descartará o quadro e se houver a correspondência, a placa de rede passará o quadro para as camadas superiores, onde ocorrerá o processo de desencapsulamento.

Por outro lado, se a rede é interconectada por um switch de camada 2, o mesmo procurará uma correspondência do endereço MAC de B com sua tabela de endereços, conhecida como tabela CAM (Content Addressable Memory, Memória endereçável de conteúdo), que mapeia o endereço MAC com a porta no qual o dispositivo está conectado. Caso exista a correspondência, ou seja, caso o endereço MAC de esteja na tabela CAM, o switch enviará o quadro diretamente para o dispositivo correspondente ao endereço MAC de destino, caso contrário, o switch enviará o quadro por todas as suas interfaces, conforme mostrado na figura x.

![[Untitled 4 15.png|Untitled 4 15.png]]

### Tecnologias Ethernet

Tratamos o protocolo Ethernet até agora como se como se fosse um protocolo único. Mas a Ethernet possui diferente versões, com designações como, por exemplo, 100BASE-T. A transmissão em redes Ethernet é realizada em banda base. Isso significa que toda a capacidade do meio de transmissão é utilizada para transmitir bits sem qualquer processo de modulação, ou seja, transportando apenas quadros Ethernet. Algumas tecnologias Ethernet são mostradas na tabela abaixo.

A nomenclatura acima como, por exemplo, 10Base-T, apresentada na tabela para designar as diferentes tecnologias Ethernet, diz respeito a:

**XBase-Y**

- **X:** Corresponde a taxa de transmissão nominal em múltiplos de bits (Mbps – Megabits por segundo e Gbps – gigabits por segundos);
- **Base**: Sinalização Banda Base;
- **Y:** Específica o tipo de cabo e o seu comprimento máximo.

![[Untitled 5 14.png|Untitled 5 14.png]]