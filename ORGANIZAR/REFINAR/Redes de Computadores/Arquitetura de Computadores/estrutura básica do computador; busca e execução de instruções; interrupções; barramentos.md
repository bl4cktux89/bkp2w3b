**Barramentos**

Os barramentos são portas pelas quais o processador pode comunicar-se com os demais componentes do micro, como a placa de vídeo. Falando em placa de vídeo, você já percebeu que todas as placas de vídeo modernas são conectadas em slots PCI ou AGP? E que placas de som e modems antigos quase sempre usam slots ISA? Isso acontece porque placas de som e modems são periféricos relativamente lentos, para os quais o lento barramento ISA já é suficiente. Porém, as placas de vídeo necessitam de um barramento muito mais rápido, motivo pelo qual utilizam slots PCI ou AGP. Que tal se agora estudássemos os diferentes tipos de barramento existentes?

**Barramentos antigos**

Os processadores 8088, usados nos micros XT, comunicavam-se com os demais periféricos usando palavras binárias de 8 bits. Para o uso em conjunto com esses processadores, foi criado o ISA de 8 bits. Esse barramento funciona usando palavras binárias de 8 bits e opera a uma frequência de 8 MHz, permitindo uma passagem de dados a uma velocidade de 8 megabytes por segundo, velocidade muito mais do que suficiente para um processador lento como o 8088.

**ISA** _**(Industry Standard Architecture)**_

Os processadores 286 se comunicavam com os demais periféricos usando palavras de 16 bits. Para acompanhar essa melhora por parte do processador, foi criada uma extensão para o barramento ISA de 8 bits, formando o ISA de 16 bits. Esse barramento, assim como o processador 286, trabalha com palavras de 16 bits, a uma frequência de 8 MHz, permitindo um barramento total de 16 MB/s.

Os periféricos ISA vem sendo usados desde a época do 286, mas, na verdade, esse padrão já existe desde 1981, ou seja, quase 40 anos de idade!. O ISA é um bom exemplo de padrão obsoleto que foi ficando, ficando, ficando, mesmo depois de terem sido criados barramentos muito mais rápidos, como o PCI. A verdade é que o ISA durou muito tempo porque o barramento de 16 megabytes por segundo permitido por ele é suficiente para acomodar periféricos lentos como modems e placas de som, fazendo com que os fabricantes desses periféricos se acomodassem, e continuassem produzindo periféricos ISA praticamente até hoje.

**MCA** _**(Micro Channel Architecture)**_

Com o surgimento dos processadores 386, que trabalhavam usando palavras binárias de 32 bits, tornou-se necessária a criação de um barramento mais rápido que o ISA para o uso de periféricos rápidos, como placas de vídeo e discos rígidos. A IBM criou então o MCA, que funcionava com palavras de 32 bits e a uma frequência de 10 MHz, sendo 2,5 vezes mais rápido que o ISA de 16 bits.

Apesar de trazer recursos surpreendentes para a época em que foi lançado, como o bus mastering e suporte ao plug-and-play (foi o primeiro barramento a suportar esses recursos, isso em 1987), o MCA não conseguiu se popularizar por causa de seu alto custo, incompatibilidade com o ISA e, principalmente, por ser uma arquitetura fechada, caindo em desuso com o surgimento do EISA e do VLB.

**EISA** _**(Extended ISA)**_

Esse novo barramento foi uma resposta dos demais fabricantes liderados pela Compac ao MCA, criado e patenteado pela IBM.

Com o objetivo de ser compatível com o ISA, o EISA funciona também a 8 MHz, porém, trabalha com palavras binárias de 32 bits, totalizando 32 MB/s de barramento, sendo duas vezes mais rápido do que seu antecessor. O EISA também oferecia suporte a bus mastering e plug-and-play, com eficiência comparável à do MCA.

Uma das grandes preocupações dos fabricantes durante o desenvolvimento do EISA foi manter a compatibilidade com o ISA. O resultado foi um slot com duas linhas de contatos, capaz de acomodar tanto placas EISA quanto placas ISA de 8 ou 16 bits.

**VLB** _**(VESA Local Bus)**_

Lançado em 1993 pela Video Electronics Standards Association, o VLB é muito mais rápido que o EISA ou o MCA, sendo utilizado por placas de vídeo e controladoras de disco, as principais prejudicadas pelos barramentos lentos. Com o VLB, os discos rígidos podiam comunicar-se com o processador usando toda a sua velocidade, e se tornou possível a criação de placas de vídeo muito mais rápidas.

Como antes, existiu a preocupação de manter a compatibilidade com o ISA, de modo que os slots VLB são compostos por três conectores. Os dois primeiros são idênticos a um slot ISA comum, podendo ser encaixada neles uma placa ISA, sendo o terceiro destinado às transferências de dados a altas velocidades permitidas pelo VLB.

As desvantagens do VLB são a falta de suporte a bus mastering e a plug-and-play, além de uma alta taxa de utilização do processador e limitações elétricas, que permitem um máximo de 2 ou 3 slots VLB por máquina.

**PCMCIA** _**(Personal Computer Memory Card International Association)**_

O PCMCIA é utilizado principalmente em notebooks e handhelds em que, na maioria das vezes, é o único meio de conectar placas de expansão.

A principal vantagem desses dispositivos é o tamanho: todos possuem dimensões um pouco menores que as de um cartão de crédito, apenas mais espessos.

Atualmente é possível encontrar praticamente qualquer tipo de dispositivo na forma dessas placas: modems, placas de som, placas de rede, placas decodificadoras de DVD, cartões de memórias SRAM e memórias flash e, até mesmo, discos rígidos removíveis.

**AMR** _**(Audio Modem Riser)**_

Esse é um padrão de barramento que permite o encaixe de placas de som e modems controlados via software. O slot AMR se parece com um slot AGP, mas tem apenas 1/3 do tamanho deste. O objetivo é permitir a criação de componentes extremamente baratos para serem usados em micros de baixo custo.

A vantagem é o preço, já que uma placa de som ou modem AMR não custa mais de 5 ou 7 dólares para o fabricante (um pouco mais para o consumidor final, naturalmente). A desvantagem, por sua vez, é o fato desses componentes serem controlados via software, o que consome recursos do processador principal, tornando o micro mais lento.

**ACR** _**(Advanced Communications Riser)**_

O ACR é um padrão desenvolvido por uma associação de vários fabricantes, que inclui a AMD, Lucent, Motorola, 3Com, Nvidia, Texas Instruments e Via. Os slots ACR se parecem com um slot PCI invertido; na verdade os fabricantes optaram por aproveitar o mesmo encaixe para cortar custos, mas as semelhanças param por aí, já que foram mudadas a posição e a sinalização elétrica do slot.

Os slots ACR são risers para a conexão de placas de som e modems de baixo custo, assim como os slots AMR. Muitas placas atuais trazem um slot ACR, mas os fabricantes evitam desenvolver placas com dois ou mais slots ACR para não diminuir o número de slots PCI da placa.

A principal vantagem do ACR sobre o AMR é que, enquanto o AMR permite que o riser inclua apenas modem e placa de som, no ACR o riser pode conter praticamente todos os tipos de dispositivo, desde modems e placas de som baratas,controlados via software, até placas de rede, modems ADSL ou ISDN, placas de som e modems controlados via hardware etc.

**AGP** _**(Accelerated Graphics Port)**_

O AGP é um barramento feito sob medida para as placas de vídeo. O AGP foi criado com base nas especificações do PCI 2.1 e opera ao dobro da velocidaden do PCI, ou seja, 66 MHz, permitindo transferências de dados a 266 MB/s, contra apenas 133 MB/s possíveis pelo barramento PCI.

Além da velocidade, o AGP permite que uma placa de vídeo possa acessar diretamente a memória RAM para armazenar texturas. Esse é um recurso muito utilizado em placas 3D, que usa a memória RAM para armazenar as texturas que são aplicadas sobre os polígonos que compõem a imagem tridimensional.

**Barramentos mais recentes**

Atualmente, os computadores possuem barramentos mais rápidos capazes de suportar vários equipamentos em uma mesma porta. Os principais barramentos utilizados hoje são:

**PCI** _**(Peripheral Component Interconnect)**_

Criado pela Intel, o PCI é tão rápido quanto o VLB, porém mais barato e muito mais versátil. Outra vantagem é que, ao contrário do VLB, ele não é controlado pelo processador, e sim por uma controladora dedicada, incluída no chipset. Além de diminuir a utilização do processador, isso permite que o PCI seja empregado com qualquer processador, sem qualquer tipo de modificação.

Atualmente, todos os periféricos rápidos, placas de vídeo e controladoras de disco usam quase obrigatoriamente o barramento PCI. Componentes mais lentos, como placas de som e modems, ainda podem ser encontrados em versões ISA, apesar de cada vez mais acharmos esses componentes em versões PCI.

**USB** _**(Universal Serial Bus)**_

O USB é um padrão para a conexão de periféricos externos. Suas principais armas são a facilidade de uso e a possibilidade de se conectar vários periféricos a uma única porta USB.

É o primeiro barramento para micros PC realmente plug-and-play. Podemos conectar periféricos mesmo com o micro ligado, bastando fornecer o driver do dispositivo para que tudo funcione sem ser necessário nem mesmo reinicializar o micro. A controladora USB também é suficientemente inteligente para perceber a desconexão de um periférico.

Podemos conectar até 127 periféricos em filaa uma única saída USB, ou seja, conectando o primeiro periférico à saída USB da placa-mãe e conectando os demais a ele. O USB em sua versão 2.0 possui uma taxa de transferência que pode chegar a 480 Mbps.

**IEEE 1394** _**(FireWire)**_

O FireWire (também conhecido como i.Link, IEEE 1394 ou High Performance Serial Bus/HPSB) é uma interface serial para computadores pessoais e aparelhos digitais de áudio e vídeo que oferece comunicações de alta velocidade e serviços de dados em tempo real. O FireWire pode ser considerado uma tecnologia sucessora da quase obsoleta interface paralela SCSI. Podemos conectar até 63 periféricos em fila a uma única saída FireWire, ou seja, conectando o primeiro periférico à saída FireWire da placa-mãe e conectando os demais a ele. O FireWire é uma tecnologia de entrada/saída de dados em alta velocidade para conexão de dispositivos digitais, desde camcorders e câmeras digitais, até computadores portáteis e desktops. Amplamente adotado por fabricantes de periféricos digitais como Sony, Canon, JVC e Kodak, o FireWire tornou-se um padrão estabelecido na indústria tanto por consumidores como por profissionais. Desde 1995, um grande número de camcorders digitais modernos inclui essa ligação, assim como os computadores Macintosh e PCs da Sony, para uso profissional ou pessoal de áudio/vídeo. O FireWire também foi usado no iPod da Apple durante algum tempo, o que permitia que as novas músicas pudessem ser carregadas em apenas alguns segundos, recarregando simultaneamente a bateria com a utilização de um único cabo. Os modelos mais recentes, porém, como o iPod nano e o novo iPod de quinta geração, já não utilizam uma conexão FireWire (apenas USB 2.0).

**Pedido de interrupção (IRQ)**

Nos micros PC, existe um recurso chamado de pedido de interrupção. A função dos pedidos de interrupção é permitir que os vários dispositivos do micro façam solicitações ao processador. Existem 16 canais de interrupção, chamados de IRQ ("interrupt request", ou "pedido de interrupção"), que são como cordas que um dispositivo pode puxar para dizer que tem algo para o processador.Quando solicitado, o processador para tudo o que estiver fazendo para dar atenção ao periférico que está chamando, continuando seu trabalho após atendê-lo.

Dois dispositivos não podem compartilhar a mesma interrupção, caso contrário teríamos um conflito de hardware. Isso acontece porque, nesse caso, o processador não saberá qual dispositivo o está chamando, causando os mais diversos tipos de mau funcionamento dos dispositivos envolvidos.

Normalmente os endereços IRQ ficam configurados da seguinte maneira:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108782/a12i01_arco80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/8/7/108782/a12i01_arco80_100.jpg)

Caso determinado dispositivo não esteja instalado, a interrupção destinada a ele ficará vaga. É possível também mudar os endereços dos periféricos instalados, por exemplo, instalar uma placa de som em outra interrupção disponível e usar a interrupção cinco para outro dispositivo.