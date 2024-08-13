[![](https://ampli-images.s3.amazonaws.com/production/d1aa199d-3dac-4bb7-8bc4-e51e6b2a0419/original)](https://ampli-images.s3.amazonaws.com/production/d1aa199d-3dac-4bb7-8bc4-e51e6b2a0419/original)

Quando entramos com os dados em um computador, ou quando este executa instruções vindas dos programas, o processador busca estes dados em uma memória externa, ou seja, uma memória que não está dentro do próprio processador, chamada de memória principal. Como você já observou em momentos anteriores, a velocidade dos processadores é, em geral, muito maior do que as velocidades das memórias, gerando uma fila de espera entre os dados encontrados na memória e o processador na hora da execução do processamento (FÁVERO, 2011).

Para poder solucionar esta limitação entre a velocidade de processamento em relação à velocidade da memória principal, foi desenvolvida uma técnica que inclui um dispositivo de memória entre eles, denominada de memória cache. Ela tem a função de criar condições que aumentem a velocidade de comunicação entre a memória principal e o processador, aumentando a velocidade final do processamento. Este tipo de memória também é volátil e apaga-se quando o computador é desligado (PATTERSON, 2014).

A memória cache é uma memória dita “estática”, pois, uma vez colocado, o dado permanece enquanto a memória for alimentada. Este tipo de memória é baseado em circuitos do tipo _flip-flop_. Estas memórias são muito rápidas porque os circuitos _flip-flop_ são feitos com transístores, e a leitura é feita simplesmente medindo a tensão de saída, onde 0 (zero) Volt gera um _Bit_ “0” e 5 Volts gera um _bit_ “1”. Apesar de mais rápida, seu ponto fraco é que são necessários muitos transístores e muitos resistores para fazer um _flip-flop_ (1 _bit_), o que torna esse custo desta memória muito alto. (PATTERSON, 2014).

A memória cache é uma memória que, atualmente, se encontra internamente nos processadores, entre a CPU e a memória principal, espelhando parte desta memória e tornando o processamento mais rápido (FÁVERO, 2011). Atualmente, o tamanho desta memória cache pode variar entre 64 KB e 256 KB para cada núcleo de um processador _Multicore_, ou em versões mais atuais, em torno de 8 MB compartilhado por todos os núcleos (INFOWESTER, 2015).

**Memória principal** - Como o próprio nome já diz, esta memória é o elemento principal para o funcionamento de um computador, em conjunto com outro elemento, o processador. Não há computador se não houver um processador, e também não há um se não existir memória (MONTEIRO, 2007).

A memória principal é chamada de memória RAM – _Random Access Memory,_ em português Memória de Acesso Aleatório, que faz o armazenamento dos dados inseridos no computador, dados dos programas e os próprios programas. Ela é chamada de aleatória porque, para preservar os circuitos de deterioração, a cada acesso de escrita um bit aleatório é escolhido, evitando que sempre os mesmos bits sejam usados, o que causaria fadiga no circuito. Além disto, a memória RAM permite ao processador ter acesso às memórias secundárias, disponibilizando os dados gravados nestas memórias e processá-los (PATTERSON, 2014).

A memória RAM é do tipo volátil, ou seja, é apagada quando o computador é desligado. É por este motivo que muitos usuários perdem os trabalhos que estão sendo feitos no computador quando a energia é interrompida de repente, pois enquanto estes trabalhos não são gravados em um disco rígido, por exemplo, eles não serão arquivos, serão apenas dados que estavam naquele momento sendo processados pelo computador (FÁVERO, 2011).

[![](https://ampli-images.s3.amazonaws.com/production/879db114-527b-4e8e-bda8-8bcac1d82f27/original)](https://ampli-images.s3.amazonaws.com/production/879db114-527b-4e8e-bda8-8bcac1d82f27/original)

Pente de memória RAM. Fonte: RAM module SDRAM 1GiB - CC BY-SA 2.5.

Segundo Fávero (2011), a memória RAM é conhecida também por DRAM (_Dynamic RAM_), ou traduzindo RAM dinâmica. É considerada dinâmica porque ela tem a necessidade de refrescamento de memória, um recurso que realimenta de energia as memórias e mantém os dados armazenados enquanto o computador estiver ligado, pois sem este recurso a memória ficaria sem energia e seus dados seriam perdidos.

Isso ocorre porque as memórias dinâmicas, ao contrário das memórias estáticas, são feitas com capacitores. A leitura de um capacitor que esteja descarregado gera o _bit_ “0” (zero). A leitura de um capacitor carregado gera o _bit_ ”1”. Ocorre que o capacitor deve ser recarregado de tempos em tempos para que sua carga não se deteriore e, assim, o _bit_ seja perdido. Esse processo de leitura por descarga de capacitores é lento, o que torna este tipo de memória mais lenta. O ponto a favor deste tipo de memória é que, por ser baseada em capacitores, seu custo torna-se menor (PATTERSON, 2014).

Por serem constantemente refrescadas, as memórias DRAM consomem muitos ciclos de processamento e muito mais energia que outros tipos de memória, o que as tornam mais lentas, mas, em contrapartida, tem seu custo menor e uma maior capacidade de armazenamento de dados (MONTEIRO, 2007).

Conforme você pôde observar na Figura acima, a memória RAM tem o formato de pente, um módulo composto por uma pequena placa com circuitos integrados que determinam sua capacidade e sua taxa de transferência.

Segundo Monteiro (2007), existem diferentes modelos de módulos de memória disponíveis no mercado, sendo que, atualmente, é mais comum o uso dos modelos DIMM – Dual Inline Memory Module, ou traduzindo Módulo de Memória em Linha Dupla, usados nas memórias do tipo DDR, DDR2, DDR3, DDR4 e nas DDR5.

_______

**📝 Exemplificando**

Podemos citar como exemplos de memórias do tipo DDR:

- DDR (_Double Data Rate_): esta memória transfere dois lotes de dados entre processador e memória por ciclo de _clock_.
- DDR-2: transfere quatro lotes de dados por **ciclo de clock** e apresenta um consumo de energia menor do que a DDR.
- DDR-3: transfere oito lotes de dados por ciclo de _clock_, trabalha com clocks que vão de 800 a 2.133 MHz e consome ainda menos energia que a DDR2 (TECMUNDO, 2015).
- DDR-4: trabalha com _clocks_ entre 2.133 até 4.266 MHz. O que representa um ganho enorme de velocidade, já que temos uma quantidade muito maior de transferências num mesmo espaço de tempo, consumindo ainda menos energia que a DDR3 (TECMUNDO, 2015).
- Ainda temos novas tecnologias de memórias sendo desenvolvidas e lançadas no mercado, sempre com o objetivo de aumentar suas velocidades e capacidades, como, as memórias GDDR5.

_______

**➕ Pesquise mais**

Conheça mais sobre as memórias RAM, seus tipos e sobre as diversas tecnologias empregadas através deste artigo do site [Infowester](https://www.infowester.com/memoria.php).

_______

**A memória ROM** – _Ready Only Memory_ – também é uma memória principal do computador, mas com função apenas de leitura, onde seu conteúdo é gravado apenas uma vez e não é alterado. Esta memória também tem como característica ser uma memória não volátil, ou seja, não é apagada quando desligamos o computador. Nela são gravados os programas de inicialização de um computador, que são chamados também de “_Firmware_” (HARDWARE, 2015).

São três os principais programas gravados em uma memória ROM

- **BIOS (**_**Basic Input Output System**_**)**: sistema básico de entrada e saída, é onde ficam gravadas as instruções para que o processador da máquina possa reconhecer e os dispositivos básicos de entrada e saída.

**POST (**_**Power On Self Test**_**)**: programa de autoteste que faz a verificação e teste quando o computador é ligado, realizando diversas ações sobre o _hardware_, reconhecendo e contando a quantidade de memória, os dispositivos de entrada e saída conectados, entre outros.

**SETUP**: programa que altera os parâmetros armazenados na memória de configuração (CMOS).

A memória ROM é classificada de acordo com os dados que são gravados e/ ou regravados nela.

De acordo com Fávero (2011), as memórias ROM podem ser classificadas em:

- **PROM (**_**Programmable Read-Only Memory**_**)**: A gravação de dados neste tipo é feita uma única vez e os dados gravados na memória PROM não podem ser apagados ou alterados.
- **EPROM (**_**Erasable Programmable Read-Only Memory**_**)**: Estas memórias permitem a regravação de dados. Isso é feito através de emissão de luz ultravioleta que apaga por completo os dados que já estão gravados e após isso permite uma nova gravação.
- **EEPROM (**_**Electrically-Erasable Programmable Read-Only Memory**_**)**: Permite a regravação de dados, feitos eletricamente, não sendo necessário mover o dispositivo para que a regravação ocorra.
- **EAROM (**_**Electrically-Alterable Programmable Read-Only Memory**_**)**: Os dados gravados nesta memória ROM podem ser alterados aos poucos, razão pela qual esse tipo é geralmente utilizado em aplicações que exigem apenas reescrita parcial de informações.
- **Flash-ROM**: as memórias Flash-ROM também podem ser vistas como um tipo de EE-PROM; no entanto, o processo de gravação e regravação é muito mais rápido. Neste tipo de memória, os dados têm que ser totalmente apagados e não permite a gravação parcial de dados.

Embora alguns tipos de memória ROM permitam apagar seus dados para que se possam gravar novos dados, ela tem um funcionamento diferente da memória RAM. Em uma memória ROM, o processo de gravação é lento e os dados gravados são basicamente _Firmwares_ ou programas que executam determinadas funções. Na memória RAM, um novo dado é gravado imediatamente na memória e pode ser de qualquer tipo, por exemplo, os dados resultantes do processamento de cálculos (HARDWARE, 2015).

_______

**🔁 Reflita**

Observamos que existem dois tipos de memórias principais, a memória RAM e a memória ROM. A memória RAM é volátil, é apagada quando o computador é desligado e recebe os dados que são inseridos no computador, e permite que seja executado o processamento dos dados. Já a memória ROM é não volátil, ou seja, não é apagada quando o computador é desligado e nela, em geral, são gravados os “_Firmwares_”, que são os programas de inicialização de um computador.

_______

**💪 Faça você mesmo**

Agora que você já conhece mais sobre as memórias, assista ao vídeo e entenda mais sobre como essas memórias funcionam dentro do computador.

Ao final, faça um breve resumo dos tipos mais atuais de memória e suas respectivas capacidades, assistindo o [Vídeo](https://www.dailymotion.com/video/x6ba63z) Memória RAM.