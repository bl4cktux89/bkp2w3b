Storage Area Network ou rede de armazenamento de dados, como apresentado no capítulo 13,  é uma rede de alta velocidade dedicada a fornecer benefícios diversos relacionados ao acesso a dados que estão armazenados em banco de dados. Vem popularizando-se enormemente no meio corporativo nos últimos anos por trazer vantagens como altas taxas de transferência para o acesso aos dados, principalmente no quesito redundância,  que garantem a continuidade dos negócios em caso de falhas ou recuperação de desasatres e facilidade para aumentar o espaço em disco destinado aos servidores integrantes da rede.

Para descrever um pouco mais de SAN, é necessário rever os conceitos de RAID (Redundance Array Independent Disk)

**RAID**

A maior parte das SANs atuais utiliza sistemas de RAID em seus principais equipamentos de armazenamento de dados. Estes sistemas oferecem proteção dos dados, tolerância a falhas, no caso de um componente ou um caminho de I/O falhar, alto desempenho, capacidade de armazenamento e escalabilidade. Outras características para garantir a confiabilidade dos sistemas de RAID mais modernos incluem redundância de sistemas de refrigeração, fontes de alimentação, controladoras e até de circuitos de monitoramento.

A ideia do RAID é combinar múltiplos discos em uma matriz a fim de obter características que discos isolados não poderiam fornecer, como alto desempenho e tolerância a falhas.

Os computadores conectados a um servidor RAID enxergam suas áreas como um disco físico, que, para o servidor RAID é uma unidade lógica de armazenamento (_**Logical Storage Unit**_ - LUN).

Existem várias maneiras de obter as características de tolerância a falhas, redundância dos dados e alto desempenho, que constituem os chamados níveis de RAID. Existem 6 níveis de RAID, sendo que os principais são:

RAID 0

Os dados são distribuídos através dos discos, método conhecido por _**data striping**_, sem gerar paridade ou redundância. A gravação e a leitura dos dados é feita paralelamente, uma vez que cada disco possui a sua controladora. Com isto, há um grande ganho de desempenho, porém, por não haver redundância alguma, se um dos discos falhar, os dados são perdidos. RAID 0, conforme figura 1, é utilizado quando máximo desempenho é mais importante do que possíveis perdas de dados.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257188/14464.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257188/14464.jpg)

RAID 0

RAID 1

Os discos são divididos em 2 grupos, conforme figura 2. Na escrita, os dados são gravados igualmente nos 2 grupos. Na leitura, os dados podem ser lidos de qualquer um dos grupos. Normalmente, ela é feita alternando-se os discos, processo conhecido por _**round robin**_, mas pode haver um disco preferencial para leitura, no caso de haver um disco mais rápido que outro. Não há geração de paridade, mas sim uma redundância completa dos dados. Este método tem se tornado popular pela sua simplicidade e praticidade em caso de falha de um dos discos. Porém possui as desvantagens de utilizar apenas metade da capacidade total de discos, além de não trazer nenhum aumento de desempenho.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257189/14465.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257189/14465.jpg)

RAID 1

Fonte: o autor

RAID 5

Este nível de RAID, conforme figura 3, também utiliza o conceito de _**data striping**_, mais acrescenta uma forma de obter redundância dos dados, através do gerador de paridade. Para cada escrita, é gerada uma paridade calculada pela operação de ou exclusivo dos bits gravados. A paridade fica espalhada pelos 3 discos, ou seja, a cada gravação ela é gravada em um disco diferente. São necessários, no mínimo, 3 discos para sua implementação, sendo o espaço "desperdiçado" do conjunto devido ao armazenamento da paridade é equivalente ao espaço de um disco. Pode-se, com este esquema, perder até um disco que, a partir dos outros e da paridade, reconstitui-se os dados do disco perdido. Caso mais de um disco falhe ao mesmo tempo, os dados não poderão ser recuperados. É um método muito empregado nos storages atuais, porque alia aumento de desempenho à segurança oferecida pela redundância com um ótimo aproveitamento de recursos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257191/14466.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257191/14466.jpg)

RAID 5

RAID 0 + 1 ou RAID 10:

A combinação de níveis de RAID é uma prática comum hoje em dia. A mais utilizada é a que combina os níveis 1 e 0, o que alia a alta desempenho do RAID 0 com a segurança dos dados do RAID 1.

**Software:**

Um dos componentes indispensáveis para uma SAN são os softwares envolvidos. Normalmente, as empresas fornecedoras de SAN são também produtoras de softwares que gerenciam seus produtos de hardware. Embora não se tenha muitas pesquisas e estatísticas que meçam o estado deste componente, a parte de software é um campo em expansão, como pode ser visto em diversas empresas que vêm ampliando sua infraestrutura de dados.Estes softwares possuem diversas funções, entre elas:

- Organizar o acesso às diferentes áreas do storage por parte dos servidores: muitos storages hoje em dia possuem diferentes áreas de discos, que possuem controladoras diferentes, além, de outras características diferentes, como, por exemplo, o esquema de RAID. O planejamento do local no storage para alocar discos para os servidores, conforme suas necessidades e características é muito importante, e os softwares atuais provém cada vez mais facilidades para este trabalho.
- Prover diversos sistemas de contingência para o caso de falhas: como a maioria dos dados em storage são críticos, há uma preocupação muito grande com um esquema de contingência em caso de falhas. Um dos principais esquemas deste tipo é o chamado failover. O failover é um termo genérico utilizado quando há redundância entre caminhos de acesso e, caso haja falha em um deles, o outro é automaticamente acionado e passa a ser utilizado, o que é controlado pelo software.
- Aumentar a desempenho de acesso aos dados: há algumas ferramentas para aumentar a desempenho de acesso aos dados em um software de um SAN, dependendo da arquitetura utilizada. Uma muito utilizada é o balanceamento de carga (load balance), que utiliza caminhos redundantes de acesso ao storage, e controla por software a melhor maneira de acessa-lo, o que traz um grande aumento de desempenho.
- Prover facilidades para o backup de servidores: quanto mais crítico um servidor, mais complicado é o seu backup. Algumas aplicações não podem parar jamais e possuem uma janela de backup muito pequena. Além disso, o backup não pode interferir na desempenho do servidor, principalmente em casos de aplicações com alto índice de acesso. Com ferramentas de software como o snapshot, é possível gravar imagens da área de discos utilizadas pelo servidor, e fazer o backup em outro horário qualquer, sem impactar em nada a produção. Isto é feito, em geral, guardando-se ponteiros para os dados e utilizando-se áreas extras do storage para guardar dados que sejam modificados após o snapshot, quando os ponteiros que apontavam para a área original, passam a apontar para esta área temporária.

Normalmente, estes softwares possuem duas interfaces, uma gráfica, ou web, e outra por linha de comando, o que é extremamente útil para a confecção de scripts para automatizar alguns processos.

Infelizmente, hoje em dia, os softwares envolvidos em uma SAN estão amarrados aos fabricantes de hardware e não há uma padronização destes produtos. As diferenças entre eles são muito grandes, e o modo de operá-los também, e, assim, as empresas que implantam SAN sempre perdem um grande tempo (e dinheiro) com treinamentos para seus funcionários. Ainda: caso a solução seja migrada, o modo de operação do novo produto, com certeza, será bem diferente do anterior.

Assim, na hora de escolher qual fabricante de storage adotar, é importante procurar saber bem como será o seu gerenciamento, quais serão as facilidades que os softwares proverão, suas compatibilidades e quão fácil será a operação de todo o conjunto.

**Topologias:**

As SANs atuais são todas construídas em uma topologia física de estrela. Um hub ou switch é conectado ao storage e neles conectamos todos os outros servidores da rede. A exceção fica com a ligação ponto-a-ponto,  a seguir.

Assim, analisaremos as topologias existentes:

- **Ligação ponto-a-ponto (**_**point-to-point**_**):**

Para alguns não é considerada uma topologia de SAN, uma vez que não possui escalabilidade alguma. Neste tipo de ligação, os servidores são ligados diretamente ao storage, sem nenhum equipamento intermediário, como hub ou switch. O número máximo de servidores envolvidos é igual ao número de portas que o storage possui. Comparado com a ligação SCSI, no entanto, esta topologia, que utiliza Fibre Channel (próximo capítulo), apresenta uma desempenho muito melhor e atinge distâncias maiores

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257192/14468.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/7/1/257192/14468.jpg)

RAID com Fibre Channel

-  _**Loops**_ **ou anéis: são chamados de** _**Fibre Channel Arbitrated Loop**_ **(FC-AL)**:

Nesta topologia utiliza-se hub, cuja largura de banda é compartilhada por todos os seus membros. Teoricamente suporta loops com até 126 dispositivos, mas na prática este número é bem menor. Esta topologia está sendo muito pouco utilizada nas SANs modernas. Algumas pessoas comparam esta topologia como uma rede Token Ring, em que a largura de banda é dividida por todos os dispositivos do loop.  Entretanto há equipamentos antigos que não suportam o modo _**fabric**_ e, assim, é utilizado o modo em _**loop**_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260234/14478.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260234/14478.jpg)

Fibre channel com Hub

_**Malha**_ **(**_**Switched fabric**_ **ou apenas** _**fabric**_**)**:

Nesta topologia, utiliza-se switches Fibre Channel, conforme figura 6, o que permite um grande número de dispositivos interconectados. Dedica largura de banda integral a cada uma das portas e permite transferências de dados simultaneamente para um único nó. É a topologia que permite mais escalabilidade e crescimento. Teoricamente, pode conter mais de 7,7 milhões de nós.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260245/14481.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260245/14481.jpg)

Topologia Fibre Channel

**Topologia mista:** Na literatura, encontramos, ainda, a possibilidade de combinar as duas topologias, conforme figura 7, o que não é comum de se fazer:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260252/14482.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260252/14482.jpg)

Topologia Mista de Fibre Channel

**Zoneamento**

Há algumas formas de se implementar uma SAN. Atualmente, a topologia mais utilizada é em malha, e, com isto, a técnica do zoneamento (_**zonning**_) tornou-se bastante popular. Esta técnica consiste em definir grupos de dispositivos que se enxergam, o que chamamos de zona. Isto permite alocar o _**storage**_ adequadamente para cada _**hosts**_, pois as necessidades de espaço em disco, e mesmo de redundâncias, são diferentes entre os membros de uma SAN. Entre as diversas formas de se definir uma zona, a mais comum é utilizando-se os WWNs dos _**hosts**_.

O zoneamento é feito no _**switch**_. Atualmente, a maioria dos _**switches**_ possui algum utilitário gráfico que auxilie a fazer os zoneamentos e outras tarefas próprias de cada um, mas pode-se fazer também se conectando no _**switch**_ via telnet e utilizando o sistema próprio dele.

Storage Área Network _**versus**_ Network Attached Storage

Vale à pena comentar também uma outra tecnologia para compartilhamento de dados que ganhou popularidade: a chamada NAS (Network Attached Storage). Trata-se, basicamente, de um servidor de discos capaz de exportar áreas por protocolos como o NFS, CIFS ou até mesmo o HTTP. Para isto, é utilizada a rede local, o que traz a vantagem de permitir que qualquer host da rede tenha acesso a dados comuns, porém possui as desvantagens de congestionar o tráfego da rede, bem como uma velocidade de acesso pequena, se comparada à de uma SAN.

Uma outra grande vantagem da arquitetura NAS é que os dados podem ser compartilhados entre diversos hosts, inclusive de sistemas operacionais diferentes, enquanto em uma SAN os dados são dependentes do sistema operacional.