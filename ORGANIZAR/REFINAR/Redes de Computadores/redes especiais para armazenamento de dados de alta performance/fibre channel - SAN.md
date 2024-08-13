### Introdução

Uma rede SAN FC é um SAN (_**Storage Area Network**_) que usa fibra óptica em sua infraestrutura. Vale ressaltar que quando falarmos de FC, ao contrário do que muitos pensam, não se trata de _**Fiber Channel**_, que é o tipo de cabeamento em si, mas do protocolo, que significa _**Fibre Channel**_.

Os sistemas de armazenamento em _**block**_ proporciona acesso ao armazenamento, pode ser baseado na arquitetura scale-out ou vertical. Seus principais componentes são o armazenamento, e controladoras.

Uma controladora em um sistema block pode ser dividida em três partes, o front-end, que têm suas portas e controladoras, geralmente mais de uma, por motivos de redundância e balanceamento de carga, os principais protocolos usados são o FC e iSCSI.

Front-End e Back-End são termos que definem de maneira abstrata as partes de processamento de um sistema, por exemplo, aquela “telinha bonita” que você vê quando acessa um site é o front-end, geralmente ela é uma apresentação para o usuário e serve para receber entradas do mesmo,  enquanto o back-end seriam os códigos responsáveis por de fato realizar algum processamento com as informações de entrada, como por exemplo fazer cálculos ou realizar um cadastro.

Segundo Neto (2015), escalabilidade é habilidade de crescimento um sistema computacional, de forma transparente, e com um número crescente de usuários ao mesmo tempo. A escalabilidade em servidores é atingida através da adição de mais processadores. Os métodos de escalabilidade em servidores são: a vertical (scale-up) e a horizontal (escale-out).

(M.V. S. Neto, Virtualização: Tecnologia Central do Datacenter, 2ª Edição, 2015)

O armazenamento em **block** é a interface comum e nativa de armazenamento da maioria das mídias de armazenamento no nível de driver. ... As SANs (Storage Area Networks) sempre expõem a interface de armazenamento em block aos aplicativos client.

Internet Small Computer Systems Interface (iSCSI) [Storage System] é um protocolo da camada de transporte que provê comandos SCSI através da Rede IP sendo padronizada pelo IETF Internet Engineering Task Force e descrito pela RFC 3720.

(Dell Corporation (2015))

**ARMAZENAMENTO EM BLOCK**

### Quem usa esta tecnologia e por quê

O armazenamento em block é a interface comum e nativa de armazenamento da maioria das mídias de armazenamento no nível de driver. Um driver de disco rígido, por exemplo, faz as gravações e leituras em blocks por meio de seu endereço de block no disco formatado.

Muitos aplicativos também usam o armazenamento em block para suas operações persistentes de I/O. Um exemplo notável disso é a maioria dos aplicativos RDBMS (Relational Database Management System), como Oracle, DB2, etc. Os aplicativos que usam outros meios de armazenamento, como file systems, delegam o I/O nativo de armazenamento em block ao file system subjacente que faz a intermediação entre a interface subjacente de armazenamento em block e as operações de I/O de file emitidas pelo aplicativo (por exemplo, HDFS, NFS etc.). As SANs (Storage Area Networks) sempre expõem a interface de armazenamento em block aos aplicativos client. Em muitos casos, dependendo do suporte de HW, o tamanho do block e vários parâmetros podem ser configurados, como colocações de block na mídia real. É a função do aplicativo client fazer o mapeamento entre seus próprios formatos de armazenamento e o sistema de armazenamento em block subjacente.

### Como funciona essa tecnologia

Em muitos casos, dependendo do suporte de HW, o tamanho do block e vários parâmetros podem ser configurados, como colocações de block na mídia real. É a função do aplicativo client fazer o mapeamento entre seus próprios formatos de armazenamento e o sistema de armazenamento em block subjacente.

### Benefícios desta tecnologia

O armazenamento em block oferece melhor desempenho e velocidade do que sistemas de armazenamento em nível de arquivo. Cada volume de block pode ser tratado como uma unidade de disco independente e controlado por SO de servidor externo.

Fonte: EMC Corporation

Disponível em: https://brazil.emc.com/corporate/glossary/block-storage.htm

[![](https://img.uninove.br/static/0/0/0/0/0/0/3/0/2/3/9/3023965/42907.png)](https://img.uninove.br/static/0/0/0/0/0/0/3/0/2/3/9/3023965/42907.png)

Fonte: Dell Corporation (2015)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260220/14369.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260220/14369.jpg)

Rede SAN

Logo após o _**front-end**_, temos o cache, que é uma memória de alta velocidade, que serve para armazenar os dados temporariamente para um acesso mais rápido, o tempo médio de resposta de memórias cache é menos de 1ms. O cache funciona da seguinte maneira: O sistema verifica no _**cache**_, caso encontre ele retorna, senão busca no storage que demora um pouco mais, porém o cache têm uma função que se chama prefetch que busca os blocos adjacentes e já armazena no cache para futuras buscas. Para gravações, podem ser feitas de duas formas, os dados primeiro são gravados no cache, enviando uma confirmação ao sistema, e depois no armazenamento, o que consome menos tempo(cache de write-back), ou colocados no cache e enviados ao armazenamento, para só depois enviar a confirmação(_**cache write-through**_).

E da mesma forma que ele armazena ele precisa eliminar, fazendo um flush, ele usa algoritmos para analisar quais são mais utilizados(**MRU**), ou menos utilizados(**LRU**) e decidir qual tipo de dados manter, temos alguns tipos de flushing, entre eles o ocioso: que ocorre na utilização média do cache, ou o flushing de limite máximo: que é quando atinge um limite pré-determinado, e por último , o flushing forçado: que é quando o cachê atinge o limite máximo de 100%. Para proteger o cache de perdas por falta de energia, ou acidentes, é comum o espelhamento do cache, ou a compartimentação, que é manter o cache por um tempo sem energia com baterias, e “baixar” ou fazer um dump do conteúdo do cache para outros discos auxiliares.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260252/14482.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/2/260252/14482.jpg)

Switch Fibre Channel

E por fim, temos o back-end da placa, funcionalidade similar ao front-end, porém ao invés de fazer a comunicação com o sistema computacional, ela se comunica com o sistema de armazenamento, possui informações sobre as RAIDs e como deve armazenar os dados. Assim como o front-end, possui múltiplas portas e controladoras, para balanceamento e para oferecer um caminho alternativo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268541/11925.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/5/268541/11925.png)

Topologias iSCSI: iSCSI Bridged.

### Provisionamento

Para prover o armazenamento, o sistema pode operar de duas maneiras, a tradicional ou a virtual. No provisionamento tradicional, quando se cria um volume logic, um LUN é atribuído a esse volume, LUN, ou Logical Unit Number(número da unidade lógica) é um identificador, e no modo tradicional, Esse espaço precisa ser devidamente particionado, diretamente no disco. Já no virtual, o LUN(thin LUN, na verdade, para diferenciar do tradicional) é atribuido ao hipervisor, não ao disco, e conforme necessário, mais espaço pode ser alocado. No thin LUN todos os recursos dentro de um pool lógico compartilham os mesmos recursos. E por ser mais flexível, e aumentar a capacidade de utilização dos discos, o thin LUN é a abordagem mais apropriada para quem pensa em algo escalável.

Outro recurso muito interessante, é o mascaramento de LUN, dando a devida granularidade de cada segmento e permitindo autenticação, dessa forma apenas as pessoas autenticadas com a devida permissão poderão acessar determinado storage.

### Classificação

**LUN - Logical Unit Number**

Os LUNs também podem ser classificados em grupos, dispositivos de alto desempenho como SSD e FC são nível 1, já dispositivos como HD, é nível 2. Essa classificação permite ao administrador do sistema manter os dados mais acessados no nível 1 e os menos acessados no nível 2. Essa tarefa é feita automaticamente, e pode ser feita por nível de LUN, trocando os LUNs inteiros, não trazendo muita vantagem, ou segmentado em partes menores, e vendo quais têm mais movimentação, que seria a classificação por níveis de sub-LUN.

**Cache**

Os caches também podem ser classificados, não temos só o cache primário, que é a DRAM, podemos usar SSDs como caches secundários, e não para por aí, temos também dispositivos com tecnologia cache para server flash, que é uma placa PCIe com memória flash, que pode ser usada no servidor como cache adicional, dessa forma o cache principal fica livre para outras tarefas.

**Recapitulando**

Antes de começarmos a falar mais a fundo de SAN FC, vamos primeiro relembrar os seus conceitos básicos. SAN é uma rede que serve para realizar a conectividade entre sistemas computacionais e armazenamentos e seus sistemas. Como já visto anteriormente, o SAN funciona a nível de block e é bem similar ao funcionamento do ATA E SCSI. E para seu funcionamento é essencial que tenhamos um HBA (adaptador para conectar o armazenamento), as conexões de rede, e os dispositivos de armazenamento. Dessa forma, como tudo é realizado a nível de hardware, temos um desempenho melhor. Porém para fazer esse tráfego de dados, precisamos de algo muito rápido e confiável, e pensando nisso, temos algumas abordagens diferentes que podemos seguir. Entre elas temos: Fibre channel(FC), Internet Protocol(IP), e Fibre channel over Ethernet(FCoE). E claro, pode ser virtualizado também, usando os conceitos de SDN, lembrando que o SDN abstrai Data plane(transfere o tráfego de A para B) e control plane(lógica por trás do data plane), assumindo o controle virtual no lugar da controladora.

As vantagens envolvem um controle centralizado, a ótima capacidade para lidar com grandes volumes de dados, backup, recuperação de falhas, e a capacidade de ter data centers geograficamente separados, entre outras.

### SAN Fibre Channel

Agora entraremos no assunto de SAN FC, e posteriormente veremos as outras abordagens comentadas acima. SAN FC é uma SAN que usa o protocolo FC(Fibre Channel) troca de dados, para os cabos, fibra optica, ou  opcionalmente, cabos seriais de cobre. Podem atingir taxas de transmissão de até 16 GB/s, e são muito escaláveis.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/9/6/359643/27329.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/5/9/6/359643/27329.png)

Infraestrutura depois da implementação de FCoE

**DEFINIÇÃO DE SAN - STORAGE AREA NETWORK, SEGUNDO A SNIA (2015)**

Uma rede cujo propósito principal é a transferência de dados entre sistemas computacionais e dispositivos de armazenamento. e entre sistemas de armazenamento

**Seus principais componentes são:**

**HBA:** são adaptadores de rede para FC, e são instalados em cada nó do SAN.

**Cabeamento:** Como dito antes, pode ser fibra (longas distâncias)ou cobre serial (curtas distâncias), mas o que temos que reparar aqui, é em qual é o tipo da fibra! Temos fibras monomodo, e multimodo, a fibra envia dados por feixes de luz,  a multimodo (MMF) envia vários juntos, e isso dá um probleminha chamado de dispersão modal, que é a perda do sinal, por isso é usado em distâncias menores, já a fibra monomodo(SMF) projeta apenas um, resolvendo esse problema. Seus principais conectores são SC e LC.

**Dispositivos de rede:** Temos os HUB FC, Switch FC, Director FC(Switch modular de alto desempenho com mais portas e partes redundantes.) Alguns tipos simples de interconexão serão explicados a seguir:

- _**Ponto a ponto**_: Conexão direta de um dispositivo para outro.
- _**FC-AL**_(arbitrated loop): Cria-se um loop para comunicação entre dispositivos conectados por um HUB, de maneira que dois diferentes sistemas tentando acessar um storage, eles precisam esperar alguém ir primeiro, eles fazer uma arbitragem entre si para decidir de quem é a vez.
- _**FC-SW**_(Switch Fabric): Essa configuração abrange um switch ou uma rede deles, podendo ter fabrics na topologia, diferente do FC-AL, que os sistemas compartilham um loop, cada um têm seu canal dedicado. Esses canais dedicados se chamam ISL, que é a ligação de uma porta para outra de dois switches. As portas de um switch fabric podem ser categorizadas em 4 tipos , temos a N_PORT que é ligada ao sistema(tanto de armazenamento como de sistemas computacionais), usa portas FC ou HBA. A segunda porta é a F_PORT, ela também é chamada de porta de expansão, pois serve apenas para conectar dois switches. A terceira é a F_PORT, que conecta uma N_PORT a um switch, e pode ser chamada de porta fabric. A última porta é a G_PORT , que é a porta genérica, ela é um coringa que pode agir tanto como E ou F port.

### Protocolo Fibre Channel

O protocolo FC, ou Fibre Channel, têm como principal objetivo implementar SCSI por redes FC, ou seja, ligar dispositivos de armazenamento por rede. Essa abordagem fornece alto desempenho e escalabilidade, inclusive para longas distâncias, e tudo isso sem gerar muita sobrecarga na rede. Dispositivos de armazenamento ligados a uma rede SAN FC aparecem como se estivessem conectados localmente. O protocolo FC pode ser dividido em camadas, que vão entre FC-0 e FC-4.

**FC-0:** Camada física, inclui cabos, conectores, etc. É responsável pela transmissão de bits.

**FC-1:** É a camada responsável pela codificação antes da transmissão e pela decodificação no recebimento

**FC-2:** Camada de controle de quadro, ou controle de fluxo, ela é responsável por organizar e endereçar os quadros. Também é responsável pelo roteamento dos quadros, criação da sequência, e controlar todo o fluxo.A sua estrutura é composta por Troca, Sequência, e Quadro.

**FC-3:** Camada auxiliar, ela fornece alguns serviços como multiplicar a capacidade de banda juntando N_PORTS, e outras funções arbitrárias.

**FC-4:** A última camada da pilha, ela cria interfaces com outros protocolos que ajudam encapsular  as outras camadas. Esses protocolos podem ser IP, SCSI, entre outros. Dessa forma pode-se usar diferentes protocolos no FC-4.

### Endereçamento

**WWN(World Wide Names):** Nomes globais, eles são endereços hexadecimais de 16 caracteres, seu formato é 00;00;00;00;00;00;00;00.

**WWNN(World Wide Node Name):** Nome global do nó, é atribuído a um nó na rede de armazenamento, o mesmo WWNN pode identificar múltiplas interfaces, por exemplo se tiver múltiplos HBAs, ou mais de uma interface no mesmo HBA.

**WWPN(World Wide Port Name):** Nome global da porta, é atribuído a cada porta em um nó, HBAs com múltiplas portas terão endereços diferentes, eles são gravados fisicamente pelo fabricante para assegurar que seja único, como o endereço MAC. Este endereço sempre é atribuído tanto no HBA dos sistemas de rede e de computação.

**ALIAS:** Nós criamos um apelido para o longo endereço, por exemplo 00;00;00;00;00;00;00;00 para OLIVIA.

### Serviços do _Switch fabric_

Os serviços  do fabric também são especificados, que são:

Servidor de nome: Responsável pelo gerenciamento de nomes entre switches e nós. Fica no endereço FFFFFC.

Controladora do fabric: Fica localizada em FFFFFD, e controla Notificações Registradas de Alteração de Estado (RSCNs) dos switches, que verifica e controla os switches conectados nessa rede.

Servidor de gerenciamento: todos os dispositivos recebem um servidor de gerenciamento, ele fica no endereço FFFFFA, e ele é responsável por enviar dados para a SAN FC.

login de fabric:  É um processo de autenticação entre os dispositivos, para que consiga estabelecer uma sessão, o servidor de login fica no endereço reservado FFFFFE, os três tipos são:

- FLOGI(Fabric LOGIn): Login do switch(Fabric). Acontece entre uma porta N e F, o nó envia um quadro com os parâmetros WWPN e WWNN, para o servidor de login, que por sua vez aceita, dessa forma o switch pode escolher ou não estabelecer uma sessão com o nó, e armazenar essas informações em um banco de dados.
- PLOGI(Port LOGIn): Login de porta, acontece entre duas portas N. Acontece da mesma maneira que o FLOGI, porém entre as portas.
- PRLI(PRocess LogIn): Login de processo, acontece quando há comunicação com um protocolo de nível mais alto da camada FC-4, essa autenticação também ocorre entre as portas N.

Também temos o controle de fluxo, que é o processo de gerenciar a taxa de transmissão de dois dispositivos. Isso acontece em uma negociação baseada em créditos, um dispositivo “pergunta” para o outro se deve aumentar ou manter a taxa.

### Topologias

A definição de topologia é “estudo e descrição das interligações que compõem uma rede de computadores, tanto do ponto de vista físico, como estrutural”, temos diversas opções como interligar os dispositivos, as principais topologias são switch único, mesh e core-edge, e serão descritas a seguir:

**Switch único:** Como o próprio nome já diz, têm apenas um switch, onde os sistemas computacionais se ligam ao storage.

**Mesh:** Todos os dispositivos são ligados entre si para criar rotas alternativas, podem ser meshes totais ou parciais.

**Core-Edge:** A topologia core-edge se baseia em duas camadas, o núcleo(core), e edges(bordas), onde os sistemas computacionais são ligados a um Switch fabric de borda, e se ligam ao núcleo, que por sua vez comunica-se com o armazenamento.

Quando temos mais de um ISL físico, podemos os juntar em ISLs lógicos, iso se chama agregação de link, dessa forma fornece mais desempenho.

Outra função importante do fabric FC é o zoneamento, que permite segmentar logicamente os grupos de dispositivos em uma rede de armazenamento. Dessa forma podemos criar zonas para que os dispositivos se falem apenas com quem quisermos. Temos 3 tipos de zoneamento, por WWN, porta ou misto.

### Virtualização de SAN FC

Em uma N_PORT física podemos criar várias N_PORTs virtuais, com todos os recursos que teríamos normalmente, se chama VSAN. Primeiro é configurado as portas físicas, depois as VSANs e por último as zonas. Permite a criação de um tronco VSAN(agregação de links), e marcação de VSAN, que seria o processo de literalmente marcar os quadros da rede para saber de onde veio, isso ajuda a isolar o tráfego.

### Resumo

Como foi visto neste capítulo, SAN FC é uma técnica de armazenamento muito flexível, e nos oferece várias possibilidades, como a integração com redes IP, virtualização de SAN’s (VSAN).Também foi visto sobre a infraestrutura de uma SAN FC, como os fabrics funcionam, e como funciona o endereçamento, topologia, camadas e serviços.Outro ponto muito importante é o cache, que como vimos é uma memória de alta velocidade.

**GLOSSÁRIO EMC**

Para entender e aumentar seus conhecimentos em Armazenagem de dados consulte o glossário de termos técnicos da EMC DELL.

Disponível em : https://brazil.emc.com/corporate/glossary/index.htm