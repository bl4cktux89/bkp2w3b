### **Introdução a Interfaces**

Em comunicação de dados temos, ao menos, quatro elementos que estão em qualquer sistema de comunicação, são eles: transmissor, receptor, meio de transmissão e o protocolo. Os transmissores e receptores podem ser chamados também, como interfaces. Tais interfaces possuem protocolos que estabelecem quais serão as regras de acesso ao meio de transmissão, informando, por exemplo, qual é o padrão de codificação e quantidades de bits por segundo que é possível ser transmitido. O IEEE (Institute of Electrical and Eletronics Engineers) e a EIA  (Eletronic Industries Association - Associação das indústrias Eletrônicas) são os principais organismos que definem os parâmetros elétricos e mecânicos das interfaces que devem ser adotados para estabelecimento de uma comunicação. No jargão da área de informática costumamos chamar a interface também como porta.

- **Síncrona ou assíncronas:** As interfaces **síncronas** utilizam um relógio que sincroniza a transmissão entre o transmissor e receptor antes que seja enviado qualquer tipo de dado. Neste tipo de transmissão, o receptor sabe exatamente quando e quanto dados irá receber. Já nas interfaces **assíncrona** não existe um sincronismo entre o transmissor e receptor, como o próprio nome sugere. Nessa transmissão é colocada uma sequência de bits conhecidas como Flags (bandeiras) que mostra para a interface receptora que naquele momento ela está recebendo dados. As transmissões síncronas são capazes de transmitir a velocidades maiores do que a assíncrona, já que não são colocadas cadeias de bits (flags) para identificar o início e fim dos dados. Entretanto, as transmissões síncronas são mais caras e caso perca o sincronismo todo o bloco de dados é perdido.
- **Seriais ou paralela**: As interfaces **seriais** fazem transmissão bit-a-bit utilizando para isso um par de fios. Um exemplo desse tipo de interface é o padrão EIA RS-232, definido como um padrão de comunicação entre dispositivos DCE (_Data Communication equipment -_ Equipamento de comunicação de dados,) e DTE (_Data Terminal equipment – Equipamento de terminal de dados_). Na Figura 1 é mostrada uma conexão via interface RS-232, o PC é considerado DTE, enquanto que o dispositivo conectado ao PC é considerado DCE. Esse padrão ainda é muito utilizado, principalmente, na interconexão de equipamentos industriais e de uso científico, tendo 9 ou 25 pinos, com velocidade típica de 9600 bps. Na **Paralela,** as interfaces paralelas podem transmitir dado muito rápido do que as interfaces seriais, já que podem transmitir, por exemplo, 8 bits simultâneos, enquanto que a serial apenas 1. No passado recente, as interfaces paralelas foram extensivamente utilizadas na interconexão de PC com impressoras e foram substituídas pela interface USB devido a sua baixa taxa de transferência, de aproximadamente 150 Kbps.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/2/0/242046/8510.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/2/0/242046/8510.jpg)

Figura 1 - Conexão entre dispositivos por interfaces seriais.

### Interfaces utilizadas em rede

As interfaces utilizadas em rede de computadores são classificadas em: Interfaces WAN (Rede de longa distância) e Interfaces locais (LAN) :

- **Interfaces WAN:** As interfaces WAN são aquelas que provem acesso aos provedores de serviços de telecomunicações por meio de portas seriais ou qualquer outro padrão. Existem diversos padrões seriais que podem ser utilizados para interliga o roteador a um dispositivo conhecido com CSU (Unidade de Serviço de Canal) ou modens DCE, conforme Figura 2. Na Tabela 1 são mostradas as velocidades de algumas interfaces seriais utilizadas para conexão WAN.

|Interface serial|Taxa de transferência (Mbps)|
|---|---|
|[[EIA-TIA-232]]|Até 8|
|[[EIA-TIA-449]]|Até 2|
|[[V.35]]|Até 2|
|[[X.21]]|Até 2|
|[[EIA-530]]|Até 10|

  
  

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/8/357829/29543.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/8/357829/29543.png)

Figura 2 - Interfaces seriais utilizadas na conexão WAN

- **Interfaces LAN:** As interfaces LANs permitem que os dispositivos (roteadores ou switches) conectem os computadores da LAN por meio de interfaces do tipo Ethernet para cabos coaxiais, par trançado e fibra óptica, mas podem utilizar também as interfaces do tipo Token Ring e FDDI (_Fiber Distributed Data Interface_ - Interface de Dados Distribuídos na Fibra). As características gerais dessas interfaces são descritas abaixo:
    
    - **Ethernet:** As tecnologias Ethernets existentes são padronizadas pelo IEEE como 802.3, conforme Tabela 2. Cada tecnologia ethernet especificada pelo IEEE estabelece o meio de transmissão a ser utilizado e como serão os mecanismos de acesso ao meio de transmissão.
    
    |Especificação IEEE|Sigla|Denominação|Cabo|Largura de banda (em Mpbs)|Alcance (m)|
    |---|---|---|---|---|---|
    |[[802.3a]]|10Base2|Ethernet(thin Ethernet)|Cabo coaxial|10|185|
    |[[802.5]]|10Base5|Ethernet(thickEthernet)|Cabo coaxial grosso|10|500|
    |[[802.3i]]|10Base-T|Ethernet standard|Par trançado (categoria 3)|10|100|
    |[[802.3u]]|100Base-TX|Ethernet rápido (FastEthernet)|Par-trançado (categoria 5)|100|100|
    |[[802.3u 2]]|100Base-FX|Ethernet rápido(FastEthernet)|Fibra óptica multimodo do tipo (62,5/125)|100|2000|
    |[[802.3z 3]]|1000Base-T|Ethernet Gigabit|Par-trançado (categoria 5)|1000|100|
    |[[802.3z]]|1000Base-LX|Ethernet Gigabit|Fibra óptica monomodo ou multimodo|1000|550|
    |[[802.3z 2]]|1000Base-SX|Ethernet Gigabit|Fibra óptica multimodo|1000|550|
    |[[802.3ae]]|10GBase-SR|Ethernet 10 Gigabit|Fibra óptica multimodo|10.000|500m|
    |[[802.3ak]]|10GBase-LX4|Ethernet 10 Gigabit|Fibra óptica multimodo|10 Gbps|500m|
    
      
      
    
    - **Token Ring**: As interfaces Token Ring são definidas pelo IEEE 802.5. Em termos topológicos, as interfaces Token Ring funcionam em modo determinístico, ou seja, o controle de acesso ao meio não está na interface, mas no dispositivo concentrador chamado de MAU (Multistation Access Unit – Unidade de Acesso de Multiestação), controlando o acesso dos nós à rede por meio da passagem de bastão (token). A taxa de transferência típica de uma interface Token Ring é de 4 a 16 Mbps.
    - **FDDI:** Interfaces FDDI funcionam logicamente como interfaces Token Ring em uma rede estruturada com topologia em anel duplo (duas fibras ópticas), entretanto, utilizam cabos de fibras ópticas. A utilização de fibras ópticas permite as redes FDDI estenderem os limites das redes LAN para formar redes MAN (Redes Metropolitanas), conforme Figura 3, com alcance de até 200 Km e velocidades típicas de 1Gbps.
    
    [![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/8/357852/29544.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/8/357852/29544.png)
    
    Figura 3 - Rede FDDI
    
    - **Interfaces de gerenciamento de equipamento de rede:** Nos equipamentos de rede, tais como roteadores e switches existem interfaces que proporcionam o gerenciamento e a configuração desses dispositivos. As portas de gerenciamento podem ser do tipo Console e Auxiliar. A interface Console é conectada por meio de um cabo par trançado com conector RJ-45 à interface RS-232 ou USB do computador. Essa conexão normalmente utilizada para realizar a configuração inicial do equipamento. Também existe a interface Auxiliar que é utilizada com a mesma finalidade, porém, é utilizado para configurações remotas por meio de um modem conectado ao dispositivo. A Figura 4 mostra as portais existente em um roteador Cisco.
    
    [![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/9/357931/29545.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/7/9/357931/29545.png)
    
    Figura 4 - Interfaces de um roteador
    
    Fonte: Cisco Systems
    
    ### Outras interfaces
    
    - **USB – (Universal Serial Bus – Barramento Serial Universal):** Padrão que substituiu as interfaces seriais e paralelas e PS-2 (Utilizado nos antigos mouses e teclados). Tem por característica de plug and play (plugar e usar), permitindo a interconexão de até 127 dispositivos simultaneamente a uma porta de computador. A taxa de transferência de dados dos diferentes tipos de USB pode varia de acordo com a versão, conforme mostrado na Tabela 1. Na Figura 5 são mostradas as diferentes interfaces USB.
    
    ![[Screenshot_from_2021-12-02_22-45-11.png]]
    
    [![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/3/355384/29546-converted.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/3/355384/29546-converted.jpg)
    
    Figura 5 - Interfaces USB
    
    Fonte: Shutterstock
    
    - **Thunderbolt**: Interface desenvolvida pela Intel em parceria com a Apple, atingindo a taxa de transferência de até 40 Gbps (na versão 3) em modo full-duplex. Inicialmente foi projetado para ser utilizado via cabo de fibra óptica, podendo alcançar, no futuro, taxas de 100 Gbps. Esse padrão tem como característica interconectar diversos equipamentos de dados, áudio e vídeo (Apple, 2016), conforme Figura 6.
    
    [![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/3/355387/thunderbolt-interface-macbook.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/5/3/355387/thunderbolt-interface-macbook.jpg)
    
    Figura 7 - Interface Thunderbolt