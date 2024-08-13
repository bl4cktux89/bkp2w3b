### Introdução

O conceito de Data Center é relacionado a uma instalação dedicada, onde uma organização aloja, opera e mantém a infraestrutura de Tecnologia da Informação de um sistema computacional, refere-se também, a um lugar onde são realizadas as operações fim a fim ou _**back-end**_ (referente às etapas inicial e final de um processo) inclusive as de sistemas computacionais e equipamentos de rede com outras infraestruturas de suporte.

Um Data Center centraliza as operações de equipamento de Tecnologia da Informação e de processamento de dados de uma organização, sendo vital para a realização das operações de negócios das corporações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258529/11945.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/5/258529/11945.jpg)

Definição de Data Center

Um _**Data Center**_ pode ser construído pela própria empresa no mesmo local (internamente) ou em um local mais preparado para os equipamentos (Roteadores, Switches, Servidores de Armazenagem, Configuração automática de IP, de Correio eletrônico, compartilhamento de arquivos), bem como pode ser terceirizado. Grandes organizações normalmente mantêm mais de um _**Data Center,**_ para assim distribuir as cargas de processamento, bem como manter a disponibilidade em casos de ambientes críticos, onde as informações devem estar sempre disponíveis.

Muitas organizações estão também preocupadas com o uso de tecnologias mais eficientes e gerenciáveis, afim de reduzir o consumo de energia, gerados pela infraestrutura de TI, diminuindo assim o impacto no ambiente. A adoção de políticas ecoeficientes e sustentáveis são diretrizes que orientam as estratégias de tecnologia da informação a fim de reduzir o uso de resíduos tóxicos e a contaminantes que podem agredir o meio ambiente. Esse Conceito adotado nas boas práticas de gerenciamento da infraestrutura é chamado de “Data Center verde”.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/4/258461/11943.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/4/258461/11943.jpg)

Principais elementos do Data Center

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/4/258491/11944.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/4/258491/11944.jpg)

Características chave de um Data Center

Principais características de um Data Center

As principais características de um Data Center, levam em consideração alguns parâmetros importantes, entre os quais, podemos destacar:

- **Disponibilidade:** Deve ser garantida a disponibilidade de informações conforme e quando necessárias. A indisponibilidade de informações pode afetar com severidade as operações de negócios, levar a perdas financeiras substanciais e danificar a reputação de uma organização.
- **Segurança:** Políticas e procedimentos devem ser determinados e medidas de controle devem ser implementadas para evitar acesso não autorizado e alteração de informações.
- **Capacidade:** A operações do datacenter exigem recursos adequados para armazenar e processar com bom desempenho volumes grandes e cada vez maiores de dados. Quando as exigências de capacidade aumentam, capacidade adicional deve ser fornecida sem interrupção da disponibilidade ou com interrupção mínima. A capacidade deve ser gerenciada com a inclusão de novos recursos ou com a realocação dos recursos existentes.
- **Escalabilidade:** As organizações precisam implementar recursos adicionais como sistemas computacionais, novos aplicativos e bancos de dados para atender às necessidades crescentes. Os recursos de datacenter devem ser dimensionados para atender às necessidades de mudança sem interromper as operações de negócios.
- **Desempenho:** Os componentes de datacenter devem oferecer desempenho ideal com base nos níveis de serviço necessários.
- **Integridade dos dados:** Integridade de dados se refere a mecanismos, como códigos de correção de erro ou bits de paridade, que garantem que os dados sejam armazenados e recuperados exatamente como foram recebidos.
- **Capacidade de gerenciamento:** Um datacenter deve oferecer gerenciamento fácil, flexível e integrado de todos os seus componentes. A capacidade de gerenciamento eficiente pode ser atingida através da automação para redução de intervenção manual em tarefas comuns e repetíveis.

### Infraestrutura de um Data Center

A Infraestrutura de um Data Center normalmente compreende os seguintes elementos:

- **Instalação:** É o espaço da construção e do solo em que o datacenter está construído, normalmente tem o piso elevado com os dutos que ficam abaixo e que mantêm os cabos de energia e de rede.
- **Equipamento de TI:** Inclui equipamentos como sistemas computacionais, sistemas de armazenamento, equipamento e cabos de rede e gabinetes para alojamento do equipamento de TI.
- **Infraestrutura de suporte:** Inclui todos os equipamentos necessários para manter com segurança o funcionamento do datacenter. Alguns dos principais equipamentos de suporte são equipamentos de energia que incluem fontes de alimentação sem interrupção e geradores de energia; equipamento de controle ambiental inclusive sistemas de detecção de incêndio e de água, sistemas de aquecimento, ventilação e ar condicionado; e sistemas de segurança inclusive sistemas de biometria, cartão de chave e vídeo-vigilância.

Vale destacar outras características importantes de um Data Center, assim como seus componentes e alguns fundamentos essenciais de sistemas operacionais e virtualização. Primeiro vamos falar das camadas lógicas de infraestrutura de um Data Center, e as descrever. É importante entender cada parte e seu funcionamento, pois uma camada faz referência e completa a outra, lembrando que, são todos pilares para a existência do Data Center como um todo.

- **Infraestrutura física:** É a base de qualquer Data Center, compreende o hardware, equipamento de armazenamento, rede, sistema operacional, etc...
- **Infraestrutura virtual:** Consiste em “transformar” recursos de hardware em recursos virtuais, dessa forma se cria uma abstração entre as duas partes, criando algo mais maleável, uma vez que podemos manusear mais facilmente esses recursos. Essa camada está logo acima da física, ou seja, a camada de enlace.
- **Infraestrutura por software:** Camada localizada na camada virtual ou física, para permitir uma infraestrutura de ITaaS (Tecnologia da Informação como um serviço), onde, os recursos são agregados em grupos (_pools_), que gerenciam e automatizam os recursos usando políticas.
- **Orquestração:** O orquestrador é um software que cuida do fluxo de trabalho (_workflow_), o papel dele é coordenar, administrar, ajustar a automatização de tarefas. Ele se comunica com outras camadas a fim de alinhar tudo.
- **Serviços:** Essa é a camada onde o usuário/cliente acessa seus serviços, _email, netflix, google apps,_ entre outros…. As exigências dessa camada para cada tipo de fluxo de trabalho são enviadas ao orquestrador.
- **Continuidade de negócios:** Essa camada abrange todas as outras, de maneira que são tomadas medidas reativas e proativas, ou seja, proativas quando são ante de algo acontecer, como _backups_, replicação, entre outros…. Enquanto as reativas envolvem coisas como recuperar dados perdidos, recuperação de desastres e restauração do sistema.
- **Segurança:** Outra função multicamada já que a segurança envolve todas as partes, desde a segurança física do Data Center, os sistemas de alarme, senhas fortes e criptografadas, como também a segurança do software, tanto dos que você usa quanto os que desenvolve, sempre haverá brechas de segurança. Por isso é sempre importante manter tudo atualizado com a última versão, atualizações entre outras coisas servem para corrigir erros e falhas.
- **Gerenciamento:** Assim como a segurança, essa é outra camada que abrange todas as demais, já que se precisa gerenciar todas as camadas e etapas, assim como seus possíveis erros e problemas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/7/3/7/2973765/42493rev1.png)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/7/3/7/2973765/42493rev1.png)

### Sistema computacional e seu funcionamento

Antes de falar de aspectos específicos de armazenamento, precisamos entender algumas coisas sobre o funcionamento do sistema computacional. Um sistema computacional é a união de hardware e software (Sistema operacional). Os principais componentes físicos são: processador, memória RAM e ROM, placa mãe, Chipset e armazenamento.

Processador:  realiza cálculos aritméticos para realizar as tarefas, ele também é conhecido como a CPU ou unidade central de processamento.

RAM: Memória de acesso aleatório, é a memória principal do computador, ela é volátil, nela são executadas as aplicações, apenas o processador tem acesso direto a RAM.

ROM: Memória apenas de leitura, é uma memória não volátil onde ficam guardados microcódigos para coisas básicas, como iniciar e gerenciar energia.

Também temos os componentes lógicos de um sistema, que são: Memória virtual, LVM (Gerenciador de Volume Lógico), SO (Sistema Operacional) e sistema de arquivos.

O sistema operacional é um intermediário entre o usuário e a máquina, as instruções são passadas pelo usuário para a máquina, utilizando o _**system calls**_ (chamadas de sistema). E a memória RAM é utilizada para executar processos e quando é preciso liberar mais memória para ser utilizada em um outro processo, o Sistema Operacional congela o processo que está na memória e o armazena na memória secundária, conhecida como _**swap**_, que é um arquivo armazenado no HDD/SSD. Ele consegue fazer esse acesso, graças ao mapeamento lógico que é feito de maneira rápida, encontrando um processo na memória. A memória virtual é uma abstração da memória física mapeada logicamente.

Outro componente importante é o LVM (Gerenciador de Volume Lógico), ele gerencia o armazenamento lógico e físico, podendo unir e separar discos em partições, por exemplo, podemos ter um volume físico, com dois volumes lógicos, como também, podemos ter quatro volumes físicos, e apenas um lógico.

E para concluir, temos os _**file systems**_, ou sistemas de arquivos. Ele é responsável por organizar e resgatar os dados, sem ele não teria como saber onde começa ou acaba um dado. Temos diversos tipos de sistemas de arquivos, eles são baseados em uma das três categorias: disco, rede ou sistema virtual de arquivos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/2/0/3/20372/i01_1754.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/2/0/3/20372/i01_1754.jpg)

Sala de servidores

### Hardware de servidores

Os três principais tipos de hardwares mais usados em infraestruturas de Data Centers, que são em torre, rack ou blade.

Torre - Gabinete como de desktops, geralmente eles têm sistemas de resfriamento interno, ocupam muito espaço, e demandam muito cabeamento.

Rack - É um compartimento parecido com um “armário de metal”, onde contém os encaixes para as peças do servidor. Geralmente possui um monitor montado com teclado para se acessar o terminal. Os racks são medidos em uma unidade chamada Rack unit (unidade de rack). Uma unidade de rack mede 44,45 mm . Um servidor em rack de 1U tem tipicamente 482,6 mm de largura. Os gabinetes padrão de rack tem 19 polegadas de largura, e os tamanhos do gabinete de rack comum são 42U, 37U e 27U.

Blade - São circuitos eletrônicos que tem os principais componentes de processamento, são compactos, e mais fáceis de configurar, ocupam menos espaço, muitos já possuem sistemas de resfriamento. Um servidor blade é inserido no chassi encaixado no _**slot**_, de maneira bem simples.

[![](https://img.uninove.br/static/0/0/0/0/0/0/2/9/3/0/2/2930291/41959.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/2/9/3/0/2/2930291/41959.jpg)

### Virtualização

A técnica de virtualizar é abstrair o hardware do software, criando um intermediário entre os dois. A seguir veremos algumas dessas tecnologias:

- Hipervisor: Ou Hypervisor (em inglês), é um software que funciona desassociando recursos físicos, como memória, processadores, placas auxiliares, entre outros. Ele é instalado como um sistema operacional. E permite que execute diversos sistemas operacionais. Seus componentes essenciais são:

Kernel (núcleo) - é o componente principal de um sistema operacional.

VMM - Virtual Machine Manager (gerenciador de máquina virtual). Ele é categorizado ou como baremetal (instalado diretamente no hardware) ou como hospedado (não possui acesso direto ao hardware).

- Máquina virtual: É uma aplicação executada no sistema operacional depois de instalada. Depois de instalada ela “cria um computador dentro do seu computador”, virtualizando recursos, como memória, processador, armazenamento, etc... É possível executar qualquer sistema operacional em uma máquina virtual, independente do sistema operacional que estiver usando na máquina hospedeira, a instalação é feita por imagens conhecidas como ISO (arquivos .iso). Onde cada máquina virtual possui sua própria configuração e especificações definidas individualmente.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/2/269276/11973.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/9/2/269276/11973.jpg)

Ambiente de Data Center

Os principais arquivos das máquinas virtuais são os arquivos de:

- Configuração, disco virtual (vdi - imagem de disco virtual);
- Estado da memória (armazena a memória quando suspensa);
- Snapshot (imagem do sistema no momento mais atual dele, para restaurações posteriores);
- Registro (Mantém um log, um registro dos principais eventos e problemas).

Virtualização da área de trabalho: Virtualizar a área de trabalho permite que cada usuário acesse sua conta de qualquer dispositivo, garantindo a proteção de dados. Isso torna as tarefas mais flexíveis, possibilitando que cada funcionário traga seu próprio dispositivo (BYOD - Bring Your Own Device). O sistema é executado remotamente e apenas apresentado para o cliente. Há duas técnicas da virtualização de desktop: serviços de área de trabalho remota (RDS-Remote Desktop Services), que é compartilhado com vários usuários e infraestrutura de área de trabalho virtual (VDI-Virtual Desktop Infrastructure), que é individual para cada usuário, e geralmente são hospedadas em hipervisor baremetal.

Virtualização de aplicativos: Consiste em possibilitar que o aplicativo seja executado sem ser instalado, isso resolve problemas de compatibilidade. Ele roda em um _**container**_, que é a criação de outras instancias dentro de um sistema operacional, virtualizando e entregando para o cliente apenas o acesso a um aplicativo de cliente ou uma interface web, como por exemplo os aplicativos do google docs, presentations, Google Drive, entre outros.

**MODELOS DE NEGÓCIO BASEADOS EM DATA CENTER**

**Infraestrutura como um serviço (IaaS**) - Utiliza a Infraestrtura de  servidores, roteadores, cabeamento como um serviço.

**Plataforma como um serviço (PaaS)** - Utiliza sistemas operacionais ( Windows, Linux) como um serviço.

**Software como um serviço (SaaS)** - Utiliza softwares de gestão, gerenciamento de recursos como um serviço.

**Hardware como um serviço (HaaS)** - Utiliza capacidade computacional como um serviço: processadores, discos rígidos, elemntos que compoem o hardware.

### Evolução do armazenamento

Por padrão, as empresas segmentam seus servidores por departamentos, por exemplo, cada servidor com suas aplicações e serviços, e seu armazenamento, com o avanço da tecnologia, surgiu a SAN (storage area network) que cria uma rede de armazenamento. Ao invés de cada departamento ter seu armazenamento (storage), todos conversam com a mesmo área SAN. A Storage area Network - SAN pode entregar o conteúdo requisitado muito rapidamente,fazendo uso de alguns protocolos para isso, os principais principais protocolos são: Fibre Channel SAN (FC SAN), Internet Protocol SAN (IP SAN) e Fibre Channel over Ethernet SAN (FCoE SAN).

### Outros tipos de armazenamento

Não é só em HD e SSD que se armazenam dados, isso também pode ser feito usando drives ópticos, como CD e DVD, porém não é uma solução adequada para grandes volumes de dados, pode-se também utilizar fitas magnéticas, constituídas por longa fita de filme, feito de bário, o problema dessa solução é para acessar os dados, já que eles são gravados sequencialmente, pode representar uma boa alternativa para grandes volumes de dados, a NASA (sigla em inglês de National Aeronautics and Space Administration – Administração Nacional da Aeronáutica e Espaço), armazena algumas informações de satélites em fita magnética.

### Conectividade

Os dispositivos geralmente se conectam por meio do protocolo IP, por meio do HBA (host bus adapter) que é a interface que se conecta ao SAN (Storage Area Network) ou o armazenamento, um protocolo, para fazer a comunicação, e uma porta, para se conectar.

Assim como a virtualização de hardware, é possível virtualizar equipamentos de rede, como switches, roteadores, LAN, entre outros dispositivos de rede.

### Data Center definido por software

É um tipo de arquitetura na qual todos os recursos são virtualizados, agrupados e automatizados. Seu objetivo é proporcionar ITaaS ( _**IT as a service**_ – Tecnologia da Informação como um serviço)  de maneira segura e escalável. A ideia por trás disso, envolve virtualizar o hardware, rede, e armazenamento, criando uma camada de abstração entre camadas reais, chamado de controlador definido por software.Essa abstração facilita o gerenciamento, uma vez que políticas globais podem ser aplicadas, permitindo o rápido provisionamento de recursos.

A virtualização pode trazer muitas vantagens, entre elas a agilidade, baixo custo, controle, flexibilidade e mais controle das informações armazenadas.

Resumidamente o principal objetivo desta aula é apresentar o ambiente de estrutura de Data Centers, sendo esse ambiente, fundamental para suprirem os níveis de serviços exigidos pelo negócio de seus cliente. Uma organização pode construir um Data Center para oferecer acesso aberto a aplicativos na Internet ou para execução privada de aplicativos de negócios dentro do sistema operacional. Um Data Center pode ser construído internamente e localizado nas instalações próprias de uma organização ou pode ser terceirizado com o equipamento localizado em um local terceirizado. Grandes organizações geralmente mantêm vários Data Centers para distribuir as cargas de trabalho de processamento de dados e para recuperação de desastre.