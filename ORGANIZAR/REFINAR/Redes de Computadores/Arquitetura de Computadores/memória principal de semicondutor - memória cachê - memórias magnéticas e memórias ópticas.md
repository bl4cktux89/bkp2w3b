**Tecnologias de memória**

O fato de o computador armazenar dados consiste em manter um dado em certo local enquanto ele for necessário. O circuito lógico elementar capaz de armazenar um dado é a célula de memória, que é um dispositivo capaz de assumir um dentre dois estados possíveis e manter-se nesse estado até que alguma ação externa venha a alterá-lo. Um componente essencial de todo computador é sua memória. Sem memória não haveria computadores da maneira como atualmente os conhecemos.

As memórias que estudamos até agora podem ser lidas e escritas. Tais memórias são chamadas RAMs, cujo nome não é apropriado porque todas as pastilhas de memória são acessíveis randomicamente, mas o termo está bem oficializado. Há duas variedades de RAMs: estáticas e dinâmicas. As RAMs são construídas inteiramente usando circuitos similares ao nosso latch tipo d. Essas memórias apresentam a propriedade de ter seus conteúdos retidos enquanto a alimentação é mantida por segundos, minutos, horas ou mesmo dias.

As RAMs dinâmicas, ao contrário, não usam circuitos do tipo latch.

Em vez disso, uma RAM dinâmica é um arranjo de pequenos capacitores, cada um podendo ser carregado ou descarregado, o que permite armazenar 0 ou 1. Como a carga elétrica tende a escoar-se, cada bit na RAM dinâmica precisa ser refrescado por alguns poucos milissegundos para evitar que o dado escape. Como uma lógica externa precisa tomar conta do refrescamento, as RAMs dinâmicas requerem um interfaceamento mais complexo que as estáticas. Entretanto, em muitas aplicações, essa desvantagem é compensada por suas maiores capacidades. Algumas RAMs dinâmicas possuem uma lógica de refrescamento embutida na pastilha, proporcionando tanto alta capacidade quanto interfaceamento simples.

As RAMs não são os únicos tipos de pastilhas de memória. Em muitas aplicações, como brinquedos, eletrodomésticos e carros, o programa e parte dos dados precisam permanecer armazenados mesmo quando a alimentação é desligada. Além disso, uma vez instalados, nem o programa nem os dados serão modificados. Esses processos levaram ao desenvolvimento das ROMs, que não podem ser modificadas ou apagadas, intencionalmente ou não. Os dados das ROMs são inseridos durante sua fabricação, essencialmente expondo um material fotossensível por meio de uma máscara contendo o padrão desejado de bits e então gravando a superfície exposta. O único modo de trocar o programa em uma ROM é substituir a pastilha.

As ROMs são mais baratas que as RAMs quando pedidas em grandes quantidades para custear as despesas de fabricação de máscara. Entretanto, elas são inflexíveis, porque não podem ser modificadas após a fabricação, e o tempo gasto entre o pedido e o reconhecimento das ROMs pode ser de muitas semanas. Para facilitar às empresas o desenvolvimento de novos produtos baseados em ROM, foi inventada a PROM. Essa pastilha é como uma ROM, exceto que ela pode ser programada uma única vez no campo, reduzindo grandemente o tempo de retorno.

O próximo desenvolvimento nessa linha foi a EPOM, que pode não apenas ser programada, como também apagada, no campo. Quando a janela de quartzo de uma EPROM é exposta a uma luz ultravioleta forte de 15 minutos, todos os bits vão para 1.

**Memória ROM (**_**Read Only Memory**_**)**

As ROMs são usadas para guardar instruções e dados que não vão mudar durante o processo de operação do sistema. Uma vez que as ROMs são não voláteis, os dados nelas armazenados não se perdem quando o equipamento é desligado.

Uma das principais aplicações da ROM é o armazenamento de alguns programas do sistema operacional dos microcomputadores, e também de informações em equipamentos controlados por microprocessadores, como caixas registradoras eletrônicas, sistemas de segurança industrial e diversos aparelhos eletrodomésticos.

Para alguns tipos de ROM, os dados que estão armazenados foram gravados durante o processo de fabricação da memória. Para outros tipos, os dados são gravados eletricamente. O processo de gravação de dados é chamado de programação, ou queima, da ROM. Algumas podem apagar e regravar seus dados quantas vezes forem necessárias.

**Tipos de memória ROM**

**PROM (Programmable ROM – ROM programável)**

Para aplicações mais modestas em termos de quantidades de chips a ser produzidos, a indústria desenvolveu as PROMs a fusível, programáveis pelo usuário, isto é, elas não são programadas durante o processo de fabricação, e sim pelo usuário, de acordo com suas necessidades. Porém, uma vez programada, a PROM torna-se uma MROM, ou seja, não pode ser apagada e novamente programada.

O processo de programação de uma PROM com a consequente verificação dos dados gravados pode ser muito tedioso e demorado, se realizado manualmente. Existe no mercado um sem-número de dispositivos programadores de PROMs que permitem a entrada da programação por teclado, para então ser realizada a queima dos fusíveis e verificação dos dados gravados, sem a intervenção do usuário.

**EPROM (Erasable PROM – programável e apagável)**

Uma EPROM pode ser programada pelo usuário, podendo, além disso, ser apagada e reprogramada quantas vezes forem necessárias. Uma vez programada, a EPROM comporta-se como memória não volátil que reterá os dados nela armazenados indefinidamente.

Uma vez que uma célula da EPROM tenha sido programada, é possível apagá-la expondo-a à radiação ultravioleta, aplicada por meio da janela do chip. Tal processo de apagamento requer uma exposição de 15 a 30 minutos aos raios ultravioletas. Uma vez apagada, a EPROM pode ser reprogramada.

**EEPROM (Electrically EPROM – programável e apagável eletricamente)**

A EEPROM foi desenvolvida no início dos anos 1980, e apresentada ao mercado como um aperfeiçoamento da ideia da PROM. A maior vantagem da EEPROM sobre a EPROM é a possibilidade de apagamento e reprogramação de palavras individuais, em vez da memória toda. Além disso, uma EEPROM pode ser totalmente apagada em 10 minutos, no próprio circuito, contra mais ou menos 30 minutos para uma EPROM que deve ser retirada do circuito para submeter-se à ação da luz ultravioleta.

**EAROM (Electrically-Alterable PROM)**

As memórias EAROM podem ser vistas como um tipo de EEPROM. Sua principal característica é o fato de que os dados gravados podem ser alterados aos poucos, razão pela qual esse tipo é geralmente utilizado em aplicações que exigem apenas reescrita parcial de informações.

**Flash**

As memórias flash também podem ser vistas como um tipo de EEPROM, no entanto, o processo de gravação (e regravação) é muito mais rápido. Além disso, memórias flash são mais duráveis e podem guardar um volume elevado de dados.

**CD-ROM, DVD-ROM e afins**

Essa é uma categoria de discos ópticos em que os dados são gravados apenas uma vez, seja de fábrica, como os CDs de músicas, ou com dados próprios do usuário, quando ele efetua a gravação. Há também uma categoria que pode ser comparada ao tipo EEPROM, pois permite a regravação de dados: CD-RW e DVD-RW e afins.

**Memória RAM** _**(Random Access Memory)**_

O termo RAM é usado para designar uma memória de acesso randômico, ou seja, uma memória com igual facilidade de acesso a todos os endereços,no qual o tempo de acesso a qualquer um deles é constante.

As RAMs são usadas em computadores para armazenamento temporário de programas e dados.

A grande desvantagem reside no fato delas serem voláteis. Algumas RAMs CMOS têm a capacidade de operar em standby, consumindo muito pouca energia quando não estão sendo acessadas, além disso, algumas podem ser alimentadas por baterias, mantendo seus dados armazenados na ocorrência de eventuais interrupções de energia.

**Tecnologias de memórias**

Várias tecnologias de memórias foram (e são) criadas com o passar do tempo. É graças a isso que, periodicamente, encontramos memórias mais rápidas, com maior capacidade e até memórias que exigem cada vez menos energia. Eis uma breve descrição dos principais tipos de memória RAM.

**FPM (Fast-Page Mode)**

Uma das primeiras tecnologias de memória RAM. Com o FPM, a primeira leitura da memória tem um tempo de acesso maior que as leituras seguintes. Isso porque são feitos, na verdade, quatro operações de leitura seguidas, em vez de apenas uma, em um esquema do tipo x-y-y-y, por exemplo: 3-2-2-2 ou 6-3-3-3. A primeira leitura acaba sendo mais demorada, mas as três seguintes são mais rápidas. Isso porque o controlador de memória trabalha apenas uma vez com o endereço de uma linha (RAS) e, em seguida, trabalha com uma sequência de quatro colunas (CAS), no lugar de trabalhar com um sinal de RAS e um de CAS para cada bit. Memórias FPM utilizavam módulos SIMM, tanto de 30 quanto de 72 vias.

**EDO** _**(Extended Data Output)**_

A sucessora da tecnologia FPM é a EDO, que possui como destaque a capacidade de permitir que um endereço da memória seja acessado ao mesmo tempo em que uma solicitação anterior ainda está em andamento. Esse tipo foi aplicado principalmente em módulos SIMM, mas também chegou a ser encontrado em módulos DIMM de 168 vias. Houve também uma tecnologia semelhante, chamada BEDO (Burst EDO), que trabalhava mais rapidamente por ter tempo de acesso menor, mas quase não foi utilizada, pois tinha custo maior por ser de propriedade da empresa Micron. Além disso, foi "ofuscada" pela chegada da tecnologia SDRAM.

**SDRAM** _**(Synchronous Dynamic Random Access Memory)**_

As memórias FPM e EDO são assíncronas, o que significa que não trabalham de forma sincronizada com o processador. O problema é que, com processadores cada vez mais rápidos, isso começou a se tornar um problema, pois muitas vezes o processador tinha que esperar demais para ter acesso aos dados da memória. As memórias SDRAM, por sua vez, trabalham de forma sincronizada com o processador, evitando os problemas de atraso. A partir dessa tecnologia, passou-se a considerar a frequência com a qual a memória trabalha para medida de velocidade. Surgiam então as memórias SDR SDRAM (Single Data Rate SDRAM), que podiam trabalhar com 66 MHz, 100 MHz e 133 MHz (também chamadas de PC66, PC100 e PC133, respectivamente). Muitas pessoas se referem a essa memória apenas como "memórias SDRAM" ou, ainda, como "memórias DIMM", por causa de seu módulo. No entanto, a denominação SDR é a mais adequada.

**DDR SDRAM** _**(Double Data Rate SDRAM)**_

As memórias DDR apresentam evolução significativa em relação ao padrão SDR, isso porque elas são capazes de lidar com o dobro de dados em cada ciclo de clock (memórias SDR trabalham apenas com uma operação por ciclo). Assim, uma memória DDR que trabalha à frequência de 100 MHz, por exemplo, acaba dobrando seu desempenho, como se trabalhasse à taxa de 200 MHz. Visualmente, é possível identificá-las facilmente em relação aos módulos SDR, porque este último contém duas divisões na parte inferior, onde estão seus contatos, enquanto as memórias DDR2 possuem apenas uma divisão.

**DDR2 SDRAM**

Como o nome indica, as memórias DDR2 são uma evolução das memórias DDR. Sua principal característica é a capacidade de trabalhar com quatro operações por ciclo de clock, portanto, o dobro do padrão anterior. Os módulos DDR2 também contam com apenas uma divisão em sua parte inferior, no entanto, essa abertura é um pouco mais deslocada para o lado.

**DDR3 SDRAM**

As memórias DDR3 são, obviamente, uma evolução das memórias DDR2. Novamente, aqui se dobra a quantidade de operações por ciclo de clock, desta vez, de oito. Uma novidade aqui é a possibilidade de uso de Triple-Channel.

**Rambus** _**(Rambus DRAM)**_

As memórias Rambus recebem esse nome por ser uma criação da empresa Rambus Inc., e chegaram ao mercado com o apoio da Intel. Elas são diferentes do padrão SDRAM, pois trabalham apenas com 16 bits por vez. Em compensação, memórias Rambus trabalham com frequência de 400 MHz e com duas operações por ciclo de clock. Tinham como desvantagens taxas de latência muito altas, aquecimento elevado e maior custo. Memórias Rambus nunca tiveram grande aceitação no mercado, mas também não foram um total fiasco: foram utilizadas, por exemplo, no console de jogos Nintendo 64. Curiosamente, as memórias Rambus trabalham em pares com "módulos vazios" ou "pentes cegos". Isso significa que, para cada módulo Rambus instalado, um "módulo vazio" tem que ser instalado em outro slot. Essa tecnologia acabou perdendo espaço para as memórias DDR.

**Módulos de memória**

Entendemos como módulo ou, ainda, pente, uma pequena placa em que são instalados os encapsulamentos de memória. Essa placa é acoplada na placa-mãe por meio de encaixes (slots) específicos para isso. Eis uma breve descrição dos tipos mais comuns de módulos:

**SIPP** _**(Single In-Line Pins Package)**_

É um dos primeiros tipos de módulos que chegaram ao mercado.É formado por chips com encapsulamento DIP. Em geral, esses móduloseram soldados na placa-mãe.

**SIMM** _**(Single In-Line Memory Module)**_

Módulos deste tipo não eram soldados, mas encaixados na placa-mãe.A primeira versão continha 30 terminais de contato (SIMM de 30 vias) e era formada por um conjunto de 8 chips (ou 9, para paridade). Com isso, podiam transferir um byte por ciclo de clock. Posteriormente, surgiu uma versão com 72 pinos (SIMM de 72 vias), portanto, maior e capaz de transferir 32 bits por vez. Módulos SIMM de 30 viaspodiam ser encontrados com capacidades que iam de 1 MB a 16 MB. Módulos SIMM de 72 vias, por sua vez, eram comumente encontrados com capacidades que iamde 4 MB a 64 MB.

**DIMM** _**(Double In-Line Memory Module)**_

Os módulos DIMM levam esse nome por terem terminais de contatos em ambos os lados do pente. São capazes de transmitir 64 bits por vez. A primeira versão – aplicada em memória SDR SDRAM – tinha 168 pinos. Em seguida, foram lançados módulos de 184 vias, utilizados em memórias DDR, e módulos de 240 vias, utilizados em módulos DDR2 e DDR3. Existe um padrão DIMM de tamanho reduzido chamado SODIMM (Small Outline DIMM), que é utilizado principalmente em computadores portáteis, como notebooks.

**RIMM** _**(Rambus In-Line Memory Module)**_

Formado por 168 vias, esse módulo é utilizado pelas memórias Rambus. Um fato curioso é que para cada pente de memória Rambus instalado no computador é necessário instalar um módulo "vazio", de 184 vias, chamado de C-RIMM (Continuity-RIMM).

**Memórias cache**

A memória cache surgiu quando se percebeu que as memórias não eram mais capazes de acompanhar o processador em velocidade, fazendo com que muitas vezes ele tivesse que ficar "esperando" os dados ser liberados pela memória RAM para poder concluir suas tarefas, perdendo muito em desempenho. Se na época do 386 a velocidade das memórias já era um fator limitante, imagine o quanto esse problema não atrapalharia o desempenho dos processadores que temos atualmente. Para solucionar esse problema, começou a ser usada a memória cache, um tipo ultrarrápido de memória que serve para armazenar os dados mais frequentemente usados pelo processador, evitando na maioria das vezes que ele tenha que recorrer à comparativamente lenta memória RAM. Sem ela, o desempenho do sistema ficaria limitado à velocidade da memória, podendo cair até 95%!

São usados dois tipos de cache, chamados de cache primário, ou cache L1 (level 1), e cache secundário, ou cache L2 (level 2). O cache primário é embutido no próprio processador e é rápido o bastante para acompanhá-lo em velocidade. Sempre que um novo processador é desenvolvido, é preciso desenvolver também um tipo mais rápido de memória cache para acompanhá-lo. Como esse tipo de memóriaé extremamente caro (chega a ser algumas centenas de vezes mais cara que a memória RAM convencional), usamos apenas uma pequena quantidade dela. Para complementar, usamos também um tipo um pouco mais lento de memória cache na forma do cache secundário, que, por ser muito mais barato, permite que seja usada uma quantidade muito maior.

**Memória magnética**

O hard disk (HD) é um sistema de armazenamento permanente de dados destinado a manter arquivos e programas. Composto por discos de armazenamento magnéticos, é um dos recursos mais importantes e largamente utilizados em diversos tipos de computadores. Dentro do disco rígido, os dados são gravados em discos magnéticos, chamados de platters. Os platters são compostos de duas camadas.

A primeira é chamada de substrato – um disco metálico feito de ligas de alumínio (recentemente, alguns fabricantes passaram a utilizar também vidro). A segunda camada é composta pela superfície magnética nos dois lados do disco.

Como a camada magnética tem apenas alguns mícrons de espessura, ela é recoberta por uma fina camada protetora, que oferece algum isolamento contra pequenos impactos. Essa camada é importante, pois, apesar dos discos serem encapsulados em salas limpas, eles internamente contém ar, com pressão ambiente.

Os HDs mais antigos utilizavam motores de 3.600 rotações por minuto, enquanto atualmente em PCs são utilizados motores de 5.400, 7.200 ou 10.000 RPM. Embora não seja o único, a velocidade de rotação é sem dúvidas o fator que influencia diretamente no desempenho. Para ler e gravar dados no disco, são usadas cabeças de leitura eletromagnéticas (heads) que são presas a um braço móvel, o que permite seu acesso a todo o disco. O braço de leitura é uma peça triangular, também feita de ligas de alumínio, para que seja ao mesmo tempo leve e resistente. O mecanismo que movimenta o braço de leitura é chamado de atuador.

Para que o HD possa posicionar a cabeça de leitura sobre a área exata referente à trilha que vai ser lida, existem sinais de feedback gravados na superfícies do disco, que orientam o posicionamento da cabeça de leitura. Eles são sinais magnéticos especiais, gravados durante a fabricação dos discos (a famosa formatação física), que são protegidos por meio de instruções de bloqueio incluídas no firmware do HD contra alteração posterior. Esses sinais eliminam os problemas de desalinhamento que existiam nos primeiros HDs.

Ao ler um arquivo, a controladora posiciona a cabeça de leitura sobre a trilha em que está o primeiro setor referente a ele e espera que o disco gire até o setor correto. Esse tempo inicial necessário para iniciar a leitura é chamado de tempo de acesso, e mesmo os HDs atuais de 7.200 RPM usam em torno de 12 milésimos de segundo, o que é uma eternidade em se tratando de tempo computacional. O HD é relativamente rápido ao ler setores sequenciais, mas, ao ler vários pequenos arquivos espalhados pelo HD, o desempenho pode cair assustadoramente. É por isso que existem programas desfragmentadores, que procuram reorganizar a ordem dos arquivos, de forma que eles sejam gravados em setores contínuos.

O disco rígido pode trazer impacto no desempenho de um computador. O fato é que o tempo perdido no movimento da cabeça de leitura, na rotação da mídia magnética, entre outros fatores, pode causar a perda de desempenho. Os principais fatores que afetam o desempenho de um disco rígido são:

- velocidade de rotação do disco magnético
- velocidade de deslocamento da cabeça de leitura
- o tempo de busca (seek time): tempo para posicionar o cabeçote na trilha desejada
- o atraso rotacional: tempo para posicionar o cabeçote no início do setor desejado
- o tempo de acesso: tempo de busca + atraso rotacional
- número de setores por trilhas
- a taxa de transferência dos dados
- como os dados estão organizados no disco
- interface usada (PATA/SATA/SCSI/SAS)

**Memória óptica**

Os discos ópticos são tecnologias de armazenamento de dados cuja leitura/escrita é realizada por meio da reflexão de raio laser. Suas características principais são:

- alta capacidade de armazenamento
- o baixo custo por bit armazenado
- durabilidade no armazenamento dos dados

O compact disc recordable (CD-R) é um dos principais representantes dessa categoria, que funciona a partir de uma superfície reflexível. Variações microscópicas nessa superfície alteram a direção de reflexão do raio ou fazem com que ele não seja refletido, impedindo-o de atingir o sensor. Com isso, reproduz-se uma sequência de estados com/sem luz no sensor, que irá compor a série de "0"s/"1"s do sinal digital.

Os discos ópticos podem ser do tipo:

- Somente leitura
- Gravável somente uma vez
- Regraváveis várias vezes