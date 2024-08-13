**1. - INTRODUÇÃO**

Conforme aprendemos, o _**Frame Relay**_ é uma das principais redes utilizada para a interconexão das redes locais, com capacidade de transporte, velocidade e rapidez. O único detalhe que as redes _**Frame Relay**_ deixam a desejar é referente ao tratamento do tráfego, isto é, não existe uma prioridade para os dados transportados. Qualquer dado (seja áudio, vídeo ou simples textos) tem a mesma prioridade para a entrega e certas aplicações não suportam atrasos como exemplo, o áudio interativo.

O ATM é uma tecnologia de comunicação de dados de alta velocidade utilizada também para a interconexão das redes LANs, das redes metropolitanas e das redes de longa distância, suportando serviços de dados, voz e vídeo sem garantia de entrega mas com qualidade de serviço.

Qualidade de serviço é um item muito necessário com as aplicações atuais, pois, em uma rede ATM se é possível priorizar o tráfego de certas aplicações que demande maior capacidade de _**link**_, ou que não possam sofrer degradação e atrasos.

Somente a tecnologia ATM consegue fornecer tal característica com abrangência a longas distâncias. Atualmente temos outras tecnologias também com qualidade de serviços como o caso das redes MPLS, porém, a mesma ainda não tem a capilaridade e a abrangência.

De forma resumida, o ATM utiliza o processo de comutação de quadros e não roteamento, portanto, tem-se neste fato um ganho em velocidade de processamento nos comutadores e consequentemente um aumento no desempenho geral da rede.

O ATM é adequado para o envio assíncrono de informações com diferentes requisitos de tempo e funcionalidade, sendo ideal para aplicações que requerem classes de qualidade de serviço diferenciadas.

Os dados quando adentram a rede são classificados de acordo com sua necessidade de QoS e são fragmentados em pequenos quadros que foram classificados como células pelo seu diminuto tamanho. Cada célula recebe então um cabeçalho simples de controle e a partir daí são encaminhados pela rede seguindo as mesmas características das redes até aqui estudadas, características como circuitos virtuais, e orientação à conexão.

**2. - Modelo de Referência ATM**

O protocolo ATM foi criado através de uma estrutura de camadas, porém sem atender ao modelo de referência OSI. Comparativamente pode-se dizer que o modelo ATM encontra-se alocado nas duas primeiras camadas do modelo da OSI, nas camadas físicas e de enlace, porém, seguindo novas funcionalidades de serviços e aplicações.

Na figura 1 é retratado um comparativo entre as duas camadas com destaque na camada ATM, onde todas elas possuem funcionalidades de controle e de serviços para o usuário. A descrição de cada camada é apresentada a seguir:

- Camada Física:

Na Camada Física encontra-se duas subcamadas, a saber:

- Subcamada _Transmission Convergence_ (TC) - responsável por mapear ou delinear as células ATM no formato dos quadros das redes de transmissão de mais baixo nível como as redes SDH, PDH e SONET. Também nesta camada são gerados os bits de controle de erros, bem como a detecção e correção de erros nos cabeçalhos.
- Subcamada _Phisical Medium_ (PM) – nesta subcamada são definidas todas as características elétricas, mecânicas e óticas do meio físico a ser utilizado. Meio ótico é o principal utilizado pelas redes ATM, pois sua abrangência deve-se as redes de longa distância. Outra função é a de temporizar os bits do frame de acordo com o relógio de transmissão das redes de baixo nível.

O ATM Fórum (órgão mundial de controle e normatização desta tecnologia) estabelece quadro padrões diferente para a Camada Física, porém temos dois padrões mais importantes, baseados nos modelos síncronos de transmissão, o modelo _**Synchronous Optical Network**_ (SONET) e o modelo _**Synchronous Digital Hierarchy**_ (SDH).

Nas redes SONET a taxa de transmissão inicia em 51,84 Mbits por segundo conhecida como STS-1 para interface elétrica e OC-1 para interface óptica, existindo ainda frequências maiores, múltiplas da frequência básica STS-1 ou OC-1 podendo chegar ao máximo a 10 Gbits por segundo.

No padrão SDH, a frequência básica de operação é também 51,84 Mbits por segundo chamada de STM-0. Igualmente ao STS-1 o SDH oferece taxas maiores podendo chegar a 10 Gbits. A tabela 1 ilustra as diferentes taxas de transmissão nas redes SONET e SDH.

**Tabela 1 - Diferentes taxas de transmissão e canalização**

![[Untitled 65.png|Untitled 65.png]]

Estes modelos são equivalentes e surgiram como tentativa de adaptação do _**Time Division Multiplexing**_ (TDM) as grandes frequências de transmissão possibilitadas pelo uso de cabos ópticos. Basicamente as diferenças entre estes dois modelos refere-se à frequência de operação, velocidade, meio físico e estrutura de dados.

- Camada ATM

A camada ATM é responsável pela construção, processamento e transmissão das células e pelo processamento das conexões virtuais.

Na tecnologia ATM existem dois conceitos bastante interessantes sobre os canais virtuais, pois em realidade temos canais virtuais sendo envelopados por outros canais virtuais. Nesta divisão temos o _**Virtual Channel**_ (VC) que é um canal virtual básico de interligação (entre equipamentos adjacentes da rede ATM) e o _**Virtual Patch**_ (VP) que é uma rota virtual configurada entre equipamentos adjacentes da rede ATM.

A tecnologia é baseada no uso de conexões virtuais, sendo implementada usando três conceitos:

- _Transmission Patch_ (TP) - Sendo o _link_ físico como exemplo: circuitos da rede de transmissão SDH ou SONET entre dois equipamentos da rede ATM.
- _Virtual Patch_ (VP) - É a rota virtual entre dois equipamentos adjacentes na rede. O VP usa como infraestrutura os TPs, onde um TP pode ter um ou mais VPs. Cada VP tem um identificador conhecido como _Virtual Patch Identifier_ (VPI) que deve ser único para um dado TP.
- _Virtual Channel_ (VC) – É o canal virtual entre dois equipamentos adjacentes usando como infraestrutura o VP. Um VP pode ter um ou mais VCs e cada VC é identificado por um _Virtual Channel Identifier_ (VCI) que também deve ser único para um dado VP.

A figura 2 ilustra esta canalização (envelopamento) entre os VCs, VPs e o TP.

A partir desta conceituação temos dois tipos de conexões virtuais, sendo:

1. _Virtual Patch Connection_ (VPC) – Que é a conexão de rota virtual definida entre dois equipamentos de acesso ou de usuário. Um VPC é uma coleção de VPs configurados para interligar origem e destino.
2. _Virtual Channel Connection_ (VCC) – É a coleção de canais virtuais definidos entre dois equipamentos de acesso ou de usuário. Um VCC é uma coleção de VCs configurados para interligar origem e destino.

Além destas funções de canalização virtual, a camada ATM ainda é responsável pelo controle de erros das células que são transferidas serialmente e se propagam numa sequencia numérica estrita na rede. Ainda temos as seguintes funções executada pela camada ATM:

- Multiplexação e demultiplexação de células de diferentes conexões (VCI e VPI) em um único fluxo de células.
- Funções de qualificação da classe de QoS e de congestionamento em tráfego de usuário.
- Extração e adição de cabeçalho de células antes e depois da célula ser enviada para a camada de Adaptação do ATM.
- Controle do mecanismo de controle de fluxo na interface de rede do usuário final.
- Translação e identificação das células nas comutações entre _switchs_ ATM onde esta transação poderá ser efetuada sobre o mesmo VCI ou VPI separadamente ou em ambos simultaneamente.
- Camada AAL

A Camada AAL é responsável pelo fornecimento de serviços para a camada de aplicação do usuário, ela é formada por duas subcamadas, a saber:

- Subcamada _Convergence Sublayer_ (CS) - Cuja função é converter e preparar a informação de usuário para o ATM de acordo com o tipo de serviço e ainda controlar as conexões virtuais. Ela recebe os dados de várias aplicações dos usuários e transforma em pacotes de tamanho variável chamados de _Convergence Sublayer Protocol Data Unit_ (CS-PDUS)_._
- Subcamada _Segmentation and Reassembly_ (SAR) - Que tem a função de receber os CS-PDUS e fragmentá-los em um ou mais pacotes de 48 bytes para que sejam diretamente inseridos no _payload_ de transporte de carga da célula ATM.

Esta operação foi descrita no sentido da aplicação descendente no modelo de referência ATM e quando a informação vem em sentido ascendente, o procedimento inverso destas operações também é executado a fim de recompor a informação original.

A camada AAL ainda implementa os respectivos serviços de controle, sinalização e qualidade de serviço ou QoS em todas as conexões de acordo com a necessidade das aplicações que vão adentrando na rede ATM para serem transportadas.

Na próxima aula estudaremos a célula ATM, sua formação e seus campos bem como as classes de serviços que esta tecnologia pode fornecer ao usuário final. Até lá!...

**3. - Para refletir:**

A rede em tecnologia ATM oferece a perfeita interconexão das redes LANs, sendo utilizada para a interligação de redes MANs e WANs.

Esta tecnologia é orientada a conexão e utiliza o mesmo principio das redes X.25 e _**Frame Relay**_, ela utiliza a formação de circuitos virtuais.

A rede ATM ainda fornece qualidade de serviço às aplicações demandando banda necessária para diferentes aplicações como: áudio, vídeo ou dados.

Ela utiliza quadros de pequeno tamanho conhecidos como células.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/7/252791/11294.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/7/252791/11294.jpg)

Figura 1 - Comparativo entre modelo de referencia OSI e ATM

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/8/252805/11347.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/2/8/252805/11347.jpg)

Figura 2 - Envelopamento do ATM

![[Untitled 1 40.png|Untitled 1 40.png]]

Figura 1 - Célula ATM e seus Campos

**1. INTRODUÇÃO**

Um dos grandes pilares do sucesso da tecnologia ATM não é só porque a tecnologia trata os quadros como célula por seu tamanho reduzido, mas sim, pelo fato que as células utilizadas nesta tecnologia tem seu tamanho fixo e, portanto, dispensa maiores tratamentos em quadros com tamanho variado.

A principal dificuldade em tratar quadros está no fato destes serem variáveis em seu tamanho e, consequentemente, os equipamentos deve possuir grande poder de processamento tornando a rede relativamente lenta. Ao se trabalhar com tamanho fixo, como é o caso das células do ATM, a eletrônica é muito mais simples, pois os equipamentos utilizados para juntar ou compartilhar fluxos de informações (chamados multiplexadores) são mais simples, de menor custo e são capazes de manipular células com facilidade e rapidez.

Sendo assim, as células foram definidas possuindo duas partes, uma chamada de Cabeçalho (formado por campos de controle e endereçamento) e a outra parte por um _**container**_ de carga denominado _**payload.**_

A célula ATM é composta de 53 bytes, sendo 5 destinados ao cabeçalho e 48 bytes definidos para o _**container**_ de carga.

A principal vantagem da utilização de células de tamanho fixo está no fato da maior facilidade de tratamento dos dados conforme já discutido, pois todo o _**hardware**_ é baseado em chaveamento e em equipamentos do tipo _**Switch**_. Em contrapartida, sua principal desvantagem está na maior quantidade de cabeçalhos acarretando um enorme _**overhead**_ no meio da transmissão, conhecido com _**cell tax**_ ou imposto do ATM, pois para a mesma capacidade de carga, que um quadro Ethernet pode transportar com apenas um único cabeçalho, são necessárias várias células para a mesma carga, com muitos outros cabeçalhos.

Em conexões de alta velocidade este imposto é pouco relevante, mas ao contrário em circuitos mais lentos, isso torna o ATM impraticável.

A figura 1 ilustra uma célula ATM com todos os seus campos e sua descrição de funcionalidade de cada um deles:

- _Generic Flow Control_ (GFC) - Formado por 4 bits este campo originalmente foi definido para controlar o tráfego, no sentido de limitar o fluxo de dados durante o período de congestionamento, porém, atualmente ele está sem uso. Nas conexões NNI que são aquelas entre _switchs_ no centro da rede ATM, este campo não existe e os 4 bits são acrescentados ao campo VPI.
- _Virtual Patch Identifier_ (VPI) - Formado por 8 bits ou 12 bits dependendo de que tipo de conexão ele se encontra. Nas conexões NNI o campo GFC vira VPI ganhando então mais 4 bits e passando o endereço para 12 no total. Nas conexões UNI que são aquelas entre o usuário final e o primeiro _switch_ ATM o endereço fica então com 8 bits. Então, o campo VPI representa o número da rota virtual até o destinatário da informação útil. E tem significado local apenas para a porta de origem.
- _Virtual Channel Identifier_ (VCI) - Com 16 bits representa o número do canal virtual dentro de uma rota virtual especificada. Também se refere ao destinatário da informação útil e tem significado local apenas para a porta de origem.
- _Payload Type Identifier_ (PTI) - Com 3 bits identifica o tipo de informação que a célula contém que podem ser dados de usuário, sinalização ou manutenção.
- _Cell Loss Priority_ (CLP) - Tem apenas 1 bit e indica a prioridade relativa da célula. Células de menor prioridade são descartadas antes que as células de maior prioridade (durante períodos em que a rede possa estar sofrendo congestionamento).
- _Header Error Check_ (HEC) - Tem 8 bits este campo e sua função é detectar e corrigir erros no cabeçalho apenas.
- _Payload_ (_Container_ de Informação Útil) - Tem uma capacidade de 384 bits ou 48 bytes e carrega a informação do usuário de forma intacta ao longo da rede, sem verificação ou correção de erros se houver. Estas tarefas são consideradas pela rede ATM como função dos aplicativos instalados em cada ponta da conexão e não da rede. A função da rede ATM é a de transportar a informação com segurança e agilidade, bem diferente da antiga tecnologia X.25 que além de transportar os dados, a rede dava garantias da entrega sem erros no conteúdo do _payload._

**2. Qualidade de Serviço – QoS**

Ao se definir a tecnologia ATM pela utilização de células de tamanho fixo se deu principalmente a necessidade da tecnologia suportar voz e vídeo em tempo real e interativo. Estes serviços necessitam de um compromisso com a qualidade da entrega dos dados sem atrasos, pois, de forma contrária os serviços estariam arruinados.

As aplicações de voz em tempo real precisam de pouca largura de banda, porém o atraso entre as células deve variar muito pouco para que tenhamos a qualidade da audibilidade alta. Portanto, células pequenas minimizam o atraso de processamento devido ao fluxo rápido dentro dos equipamentos _**switchs**_, pois temos neste caso o chaveamento e não o roteamento.

No caso de vídeo, a mesma necessidade ocorre apesar de ser menos relevante que no caso do áudio. De qualquer maneira, mesmo em vídeos gravados a garantia da constante continuidade na transmissão e recepção deste tipo de informação garante qualidade superior, viabilizando assim serviços de treinamento e ensino a distância EAD, telemedicina e outros tantos serviços que a tecnologia Ethernet não consegue suprir com a mesma qualidade da ATM.

**3. Classes de Serviços**

O tratamento dos diversos tipos de serviços suportados pela tecnologia ATM é feito na camada AAL. Para tanto foram definidas classes de serviços para as aplicações dependendo da necessidade de cada uma, aplicando em todos os serviços as questões de Qualidade de Serviço (QoS).

As classes de serviços foram então definidas baseando-se nos serviços que deverão ser transportados pela rede ATM e a qualidade de serviços requerida, as classes são: CBR, VBR, ABR e UBR.

**3.1 Classe CBR.**

O serviço _**Constant Bit Rate**_ (CBR), aplica-se a conexões que necessitem de uma banda fixa, sem alterações de velocidade e performance devido aos requisitos de tempo curtos e apertados entre o transmissor e o receptor requeridos pela aplicação. Os serviços típicos desta demanda são: Áudio interativo (telefonia), Distribuição de áudio e vídeo (televisão _**on demand**_).

**3.2 Classe VBR**

O serviço _**Variable Bit Rate**_ (VBR) aplica-se aos serviços que podem ser de tempo real ou não. A classe VBR é dividida em duas subclasses: rtVBR e nrtVBR.

**3.2.1 Subclasse rtVBR**

Na modalidade tempo real, o rtVBR é aplicado a conexões que tem requisitos apertados de tempo entre a origem e o destinatário, porém a taxa de bits pode variar. As aplicações típicas destes serviços são voz com taxa variável de bits e vídeo comprimido.

 **3.2.2 Subclasse nrtVBR**

Na modalidade não tempo real, o nrtVBR é aplicado com ou sem conexão, destinado a conexões que, embora criticas e com requisitos de tempo apertados, podem aceitar variações na taxa de bits. As aplicações típicas desta classe de serviços são: _**home banking**_, interligação de redes LANs e interação com outras redes como exemplo a _**Frame Relay**_.

**3.3 Classe ABR**

Os serviços _**Available Bit Rate**_ (ABR) são aplicados a conexões que transportam tráfego em rajadas como exemplo as redes Ethernet que podem prescindir da garantia de banda, variando a taxa de bits de acordo com a disponibilidade da rede ATM, ou seja, se a rede estiver sem congestionamento poderá fornecer melhores condições de banda, caso contrário, as aplicações em ABR sofrerão o congestionamento ou, perda de desempenho na transmissão, porém, sem realmente influenciar negativamente o serviço, pois, os mesmos suportam estas variações.

As aplicações típicas deste serviço são as interligações entre redes que utilizam o protocolo TCP/IP e as conexões entre LANs.

**3.4 Classe UBR**

O serviço _**Unspecified Bit Rate**_ (UBR) é aplicado a conexões que transportam tráfego que não tem requisito de tempo real e cujos requisitos e atrasos ou variações do atraso não prejudicam a aplicação. As aplicações típicas deste serviço são as transferências de arquivos e o serviço de correio eletrônico.

**4. Congestionamento na Rede ATM**

A capacidade de transportar dados em uma rede ATM é limitada por sua banda disponível e seus _**links**_ de acesso. Se o tráfego de dados aumenta, a banda será automaticamente alocada até o limiar da sua capacidade máxima, onde então, não será mais possível receber o tráfego adicional. Quando atinge este limiar a rede é considerada congestionada, embora ainda possa transportar todo o tráfego com algum prejuízo referente a atrasos e latências.

No caso da rede estiver passando por um período de congestionamento e mesmo assim os usuários ainda continuarem a enviar tráfego adicional, a rede é levada ao estado de congestionamento severo, o que poderá provocar a perda de células por falta de banda adequada. Neste caso, os procedimentos de reenvio dos pacotes pertencem aos usuários das pontas, as aplicações e aos protocolos locais e não é responsabilidade da rede ATM.

A tecnologia ATM possui diversos meios de controlar e gerenciar o congestionamento, como por exemplo: Alocação de recursos executando o controle severo do armazenamento nos _**buffers**_ nos equipamentos e de banda, recusando as solicitações de novas conexões.

De forma geral podemos considerar a rede ATM como o intermediário entre as aplicações de redes locais e as redes de transmissão. Ela é a conexão inteligente que fará a melhor alocação de recursos e de banda para o atendimento aos diversos padrões de qualidade de serviços que as aplicações necessitem.

**5. Para refletir**

A rede ATM utiliza frames de pequeno tamanho chamados de células.

Cada célula tem um tamanho de 53 bytes, sendo 5 bytes reservados para o cabeçalho e 48 bytes para o transporte dos dados do usuário.

Em _**links**_ de baixa capacidade podem ocorrer o _**overhead**_, pois, a carga que uma célula carrega é pequena, porém, cada célula tem seu cabeçalho.

Para assegurar a qualidade de serviço (QoS), a tecnologia ATM dispõem de quatro classes de serviços:

CBR – _**Constant Bit Rate**_

VBR – _**Variable Bit Rate**_

ABR – _**Available Bit Rate**_

UBR – _**Unspecified Bit Rate**_

Cada aplicação adentrando a rede ATM será classificada segundo suas necessidades de banda e atraso de bits em uma destas classes a fim da rede ATM preservar a qualidade de serviço requerida.