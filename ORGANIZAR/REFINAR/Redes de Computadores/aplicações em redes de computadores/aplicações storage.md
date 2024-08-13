Storage Area Network ou rede de armazenamento de dados é uma rede de alta velocidade dedicada a fornecer benefícios diversos relacionados ao acesso a dados. Vem popularizando-se enormemente no meio corporativo nos últimos anos por trazer vantagens como altas taxas de transferência para o acesso aos dados, redundâncias que garantem a continuidade dos negócios em caso de falhas e facilidade para aumentar o espaço em disco destinado aos servidores integrantes da rede.

Uma SAN é, de modo simplificado, uma rede dedicada ao armazenamento de dados, que conecta dispositivos armazenadores de discos conhecidos por _**storages**_ aos servidores da rede. É uma tecnologia relativamente nova e que vem se popularizando bastante no meio corporativo nos últimos anos, trazendo cada vez mais benefícios para as empresas que a adotam.

Em linhas gerais, pode-se definir SAN como uma infraestrutura que permite que diversos servidores tenham acesso a discos externos de modo rápido e confiável. O conceito de discos externos já é, há algum tempo, uma tendência mundial, e vem sendo cada vez mais adotado. Os discos externos não são limitados em espaço como um disco interno, são mais fáceis de manusear quando necessário e trazem facilidades para o compartilhamento por vários servidores. A figura central de uma SAN, de fato, é o servidor de discos ou, como é popularmente conhecido, o _**storage**_.

A centralização das operações de armazenamento de dados e seu gerenciamento são as razões principais pela popularização das SANs. Administrar todos os recursos de armazenamento em ambientes críticos e de crescimento elevado não é uma tarefa fácil e pode ser muito dispendioso. Imagine, por exemplo, uma empresa com centenas de servidores que possuem importante demanda por espaço em disco. Acompanhar máquina a máquina e gerenciar seus volumes, com certeza não será um tarefa fácil. Com a centralização oferecida pela SAN, tanto o tempo quanto o custo de gerenciamento destes ambientes é muito reduzido. Além disso, uma SAN provê uma série de outras vantagens para o acesso a áreas de discos, como sua alta escalabilidade e confiabilidade.

Uma SAN é implementada utilizando-se componentes de hardware e também importantes softwares, sem os quais a SAN não traria tantos benefícios.

A figura 1, observamos uma SAN, representada por uma nuvem e diversos de seus equipamentos, ao lado de outras redes. A figura nos dá uma ideia de como as tecnologias não são isoladas, mas se integram.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260220/14369.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260220/14369.jpg)

Introdução a redes storage

**Benefícios**

Podemos citar como principais benefícios proporcionados por uma arquitetura de SAN:

- Alta performance no acesso aos dados: as taxas de transferência nas SAN mais modernas podem chegar a até 2 Gb/s. Além disso, dependendo do arranjo dos discos (RAID), pode haver grande ganho de performance na leitura e/ou escrita, como veremos adiante neste trabalho;
- Alta disponibilidade e confiabilidade: uma SAN possui diversas formas de aumentar a disponibilidade dos dados de modo que, mesmo em caso de falha de alguns discos, a produção na seja interrompida. Opções como caminhos redundantes para acesso aos dados e espelhamento de dados em tempo real pode assegurar a disponibilidade dos dados e aplicações.
- Escalabilidade: capacidade de adicionar mais capacidade de armazenamento e outros recursos à infraestrutura já existente. Isto é feito facilmente dentro de uma SAN, frequentemente sem a necessidade de desligar o(s) servidore(s) ou seus clientes de rede;
- Centralizar a administração dos recursos: nos ambientes atuais, cada vez mais complexos, isto pode ser a única solução para a administração dos recursos de discos, trazendo grandes economias para as empresas.
- Descongestionamento da LAN: em muitos casos a rede local é lenta devido ao grande fluxo de informações que trafega por ela. Com uma SAN, este fluxo é bastante reduzido, o que alivia a rede local, beneficiando os usuários. Isto também é muito importante para o backup corporativo, que também pode ser feito sem utilizar a rede local.

Além destes ganhos, há outros que variam um pouco dependendo da solução adotada e dos fornecedores escolhidos, tal como balanceamento de carga e facilidades para backup. Estas facilidades focam em alternativas para aplicações em que não há janela para backup disponível, já que elas exigem disponibilidade integral.

Enfim, as características da SAN podem trazer grandes economias, alta disponibilidade dos dados, fácil expansão do storage, poucas paradas da rede, e redução de seu tráfego.

**Protocolos**

SANs podem ser implementadas utilizando interfaces, de diferentes tipos. Os protocolos suportados por SAN são os seguintes:

- FCP: Fibre Channel Protocol
- FCIP: Fibre Channel sobre TCP/IP
- IFCP: Internet Fibre Channel Protocol
- SCSI: Small Computer System Interface
- ISCSI: Internet Small Computer System Interface
- ISNS: Internet Storage Name Service
- SAS: Serial Attached SCSI

Atualmente, Fibre Channel é o padrão utilizado na maioria das SANs. Fibre Channel é uma interface serial que possui uma alta largura de banda e permite que um grande número de dispositivos que podem ser anexados a ela de uma vez. Os dispositivos Fibre Channel são conectados, principalmente, a um cabo de fibra ótica, mas pode ser utilizado também em cabos de cobre.

A Fibre Channel pode se comunicar com vários protocolos diferentes, incluindo SCSI, e até mesmo IP. Os dispositivos do Fibre Channel são identificados por um número de ID fisicamente gravado denominado World Wide Name, análogo a um endereço de Ethernet MAC.

**Hardware**

Talvez a parte mais importante para a implantação de uma SAN seja referente ao _**hardware**_. É importante selecionar com cuidado os dispositivos de _**hardware**_ para uma SAN pois há diferenças muito grandes entre os equipamentos fornecidos por diferentes empresas do ramo. Além disso, devido às SANs serem bastante dependentes de alguns _**softwares**_ para funcionar corretamente, é muito importante garantir as atualizações de_**softwares**_, _**firmwares**_ e outras questões ligadas a compatibilidade. Os fabricantes de equipamentos para SAN costumam divulgar matrizes de compatibilidade para seus produtos em seus sites. Nelas há uma quantidade muito grande de informações, contendo diversas combinações de _**hardware**_ e _**software**_, como _**storage**_, _**switch**_, HBA, servidor e sistema operacional, que foram homologados pelo fabricante. Entre as principais empresas do mercado especializadas em projeto de SAN destacam-se: EMC, Sun Microsystems, IBM, HP, Network Appliance e Brocade.

Os principais componentes de _**hardware**_ são:

Servidor de discos:

Servidores de discos, também chamados de _**storages**_ ou _**frames**_, são dispositivos que armazenam discos compartilhados pelos _**hosts**_ da rede. Eles possuem, em geral, diversas áreas diferentes, com esquemas de RAID diferentes ou discos específicos para a realização de espelhamentos para _**backup**_, os chamados BCV (_**business continuance volumes**_). Os BCVs facilitam muito tanto o _**backup**_ quanto a restauração dos dados. O seu conteúdo é sincronizado com o conteúdo do disco principal, até que se faça uma quebra do sincronismo, o chamado split. Neste momento, o BCV guarda uma imagem do disco antes do _**split**_, e pode ser usado para _**backup**_, enquanto o servidor continua trabalhando, sem impactos na produção. Este procedimento pode ser feito com a frequência mais conveniente para o usuário e, em muitos casos, o BCV é utilizado também para restauração de dados perdidos, que é muito mais rápido do que acessar fitas de _**backup**_.

Muitos _**storages**_, além de discos, possuem também uma espécie de processador e memórias nvram e/ou flash, onde é armazenado o _**firmware**_ do equipamento.

Hubs:

Assim como _**hubs**_ de uma rede local, os _**hubs**_ FC permite que todos os dispositivos conectados a ele se enxerguem e possam trocar informações entre si. Possuem as vantagens de possuir baixo preço e baixa complexidade. Permite ainda que dispositivos possam ser inseridos ou removidos sem interrupção alguma, o que torna o ambiente bastante dinâmico. Entretanto, os _**hubs**_ dividem a largura de banda por todos os dispositivos conectados a ele, o que pode representar uma perda muito grande de velocidade.

Os _**hubs**_ podem ser cascateados, a fim de fornecer mais portas para aumentar ainda mais a conectividade. Teoricamente, o _**hub**_ suporta até 127 dispositivos conectados a ele, mas na prática, deve-se restringir o total de dispositivos a 30, no máximo.

Para pequenos grupos de trabalho os _**hubs**_ são mais atrativos, pois fornecem um alto grau de interoperabilidade por um preço menor. Existem _**hubs fibre channel**_ de 4 a 16 portas e possuem uma largura de banda de, no máximo, 100 MB por segundo, compartilhado entre os servidores conectados às suas portas.

Switches:_**Switches fibre channel**_ são bem mais complexos que os _**hubs**_, tanto em seu projeto quanto em funcionalidade. Enquanto os _**hubs**_ são apenas um concentrador de cabos para um segmento compartilhado, um_**switch**_ é um dispositivo de rápido roteamento dos dados e possui uma taxa de transferência de dados exclusiva para cada porta. As taxas de transferência variam bastante dependendo do _**switch**_, que vêm evoluindo rapidamente. Atualmente, a velocidade máxima está em 400 MB/s para cada porta.

Enquanto os _**hubs**_ não participam de atividades no nível do protocolo _**Fibre Channel**_, os _**switches**_ participam ativamente, tanto para fornecer serviços quanto para supervisionar o fluxo de _**frames**_ entre a origem e o destino.

Bridges Fibre Channel-SCSI:

As chamadas _**bridges**_ em uma SAN são equipamentos que realizam a conversão entre dispositivos SCSI e Fibre Channel, interfaces de diferentes padrões elétricos e diferentes protocolos. Isto permite a manutenção dos dispositivos SCSI na SAN, como drives de fita de _**backup**_, integrando-o aos novos ambientes de tecnologia _**Fibre Channel**_.

HBA (_**Host Bus Adapter**_):

Uma HBA é um dispositivo capaz de conectar dispositivos externos a um servidor. Por exemplo: para conectarmos um disco SCSI a um micro (barramento interno PCI), será necessário utilizar uma HBA SCSI-PCI. No caso da SAN, é necessário instalar em todos os servidores participantes dela uma HBA _**Fibre Channel**_, que se encarregará de fazer as conversões dos diferentes meios internos e externos ao servidor.As HBAs FC possuem, ainda, uma espécie de processador (um _**chip**_) capaz de fazer a conversão de protocolos para poupar a CPU do servidor deste trabalho.