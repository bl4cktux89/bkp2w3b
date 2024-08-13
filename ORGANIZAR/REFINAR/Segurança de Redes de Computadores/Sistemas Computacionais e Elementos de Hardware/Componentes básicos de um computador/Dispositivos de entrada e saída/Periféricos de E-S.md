[![](https://ampli-images.s3.amazonaws.com/production/b5713155-bcbe-42b5-b938-f8e250fe2320/original)](https://ampli-images.s3.amazonaws.com/production/b5713155-bcbe-42b5-b938-f8e250fe2320/original)

Os periféricos de E/S possuem diferentes velocidades de transmissão e por este motivo não se conectam diretamente à CPU do computador. Dessa forma, os dispositivos são conectados à placa-mãe através de suas interfaces, normalmente placas que contêm diversos componentes, incluindo o _chipset_, responsável pela sincronização entre a velocidade dos dispositivos e a velocidade dos barramentos e da CPU do computador. Para que interfaces de fabricantes diferentes possam funcionar de maneira organizada, estes fabricantes têm procurado por uma padronização na definição de protocolos de funcionamento. Assim, vários tipos diferentes de dispositivos podem funcionar adotando determinado padrão. Por exemplo, temos vários fabricantes de teclado, e todos os teclados funcionam seguindo determinado protocolo, independente do modelo (FÁVERO, 2011).

Dessa forma, foram desenvolvidos vários padrões de barramentos para a conexão de placas de interfaces. Considere a interface uma placa adicional contendo um _chipset_ e que irá proporcionar a sincronização dos dispositivos periféricos de E/S. (DIGERATI, 2009).

O nome barramento neste caso é usado para identificar o tipo de conector de acordo com o número de pinos e números de vias utilizados na comunicação com a placa-mãe. Por este motivo, o termo “Barramento” é mais conhecido como sendo estes padrões de conectores da placa-mãe, porém, você já percebeu que existem vários tipos de barramento e que este termo abrange muito mais conceitos do que isto (ALMEIDA, 2007).

[![](https://ampli-images.s3.amazonaws.com/production/a7e22a2b-2987-462b-9a9b-fc6481d50e57/original)](https://ampli-images.s3.amazonaws.com/production/a7e22a2b-2987-462b-9a9b-fc6481d50e57/original)

Representação de tipos de barramentos de E/S dentro de uma placa-mãe. Fonte: Tanenbaum (2007); Monteiro (2007)

Os tipos mais conhecidos de padrões de barramentos de conectores são:

- **ISA (**_**Industry Standard Adapter**_**)**: um dos primeiros padrões, desenvolvido pela IBM, apresentava uma taxa de transferência muito baixa e não é mais utilizado.
- **PCI (**_**Peripheral Component Interconnect**_**)**: desenvolvido pela Intel, tornando-se quase um padrão para todo o mercado, como barramento de alta velocidade. Permite transferência de dados em 32 ou 64 _bits_ a velocidades de 33 MHz e de 66 MHz. Cada controlador permite cerca de quatro dispositivos.
- **AGP (**_**Accelerated Graphics Port**_**)**: barramento desenvolvido por vários fabricantes liderados pela _Intel_, com o objetivo de acelerar as transferências de dados do vídeo para a memória principal, especialmente dados em 3D, muito utilizados em aplicativos gráficos, como programas CAD e jogos.
- **PCI Express (**_**Peripheral Component Interconnect Express**_**)**: esse barramento foi construído por um grupo de empresas denominado PCI-SIG (_Peripheral Component Interconnect Special Interest Group_), composto por empresas como a _Intel_, AMD, IBM, HP e _Microsoft_. Este barramento veio para atender às demandas por mais velocidade gerada por novos _chips_ gráficos e tecnologias de rede apresentando altas taxas de transferência. Assim, o PCI e o AGP foram substituídos pelo PCI _Express_. Até o momento existiram três versões desse barramento (1.0 – lançado em 2004; 2.0 – lançado em 2007; e o 3.0 – lançado em 2010). Cada barramento possui um protocolo-padrão que é utilizado pela indústria de computadores para a fabricação de todos os dispositivos de entrada e saída a serem conectados nos diferentes tipos de barramentos.
- **USB (**_**Universal Serial Bus**_**)**: tem a característica particular de permitir a conexão de muitos periféricos simultaneamente ao barramento e por uma única porta (conector), conecta-se à placa-mãe. Grande parte dos dispositivos USB é desenvolvida com a característica de eles serem conectados ao computador e utilizados logo em seguida, o que é chamado de plug-and-play (FÁVERO, 2011).

_______

**📝 Exemplificando**

O nome barramento também é usado para identificar o tipo de conector de uma placa de interface de acordo com o número de pinos e números de vias utilizados na comunicação com a placa-mãe do computador. O tipo mais atual deste tipo de conector é o PCI Express.

_______

Além dos barramentos, para que os usuários possam inserir dados no computador e obter as informações nele contidas, são necessários dispositivos / periféricos que permitam a comunicação do usuário com o computador, tanto para dar a entrada de dados e instruções quanto para proporcionar a saída de resultados ao usuário, no formato adequado que foi solicitado.

Esses dispositivos/periféricos devem ser capazes de realizar duas funções:

- Receber ou enviar informações ao meio exterior;
- Converter as informações de entrada para a linguagem da máquina e as de saída para a linguagem usada pelo usuário (MONTEIRO, 2007).

Em um computador há a necessidade de que a CPU se comunique com a memória principal (RAM) e com os dispositivos de E/S para a transferência de dados. Semelhante ao que ocorre com a comunicação entre CPU e memória principal, na qual são definidos endereços para cada posição de memória, os quais são referenciados pela CPU, quando se trata de comunicação entre CPU e dispositivos, torna-se necessário que a CPU indique um endereço que corresponda ao periférico em questão.

Diversas formas de comunicação entre CPU e memória principal foram propostas, as quais sofreram melhorias ao longo do tempo, buscando sempre alcançar uma melhor utilização da CPU e um melhor desempenho para o sistema como um todo. Murdocca (2001) destaca três métodos para gerenciar a entrada e saída:

**Entrada e saída programada**: Neste método, a CPU precisa verificar continuamente se cada um dos dispositivos necessita de atendimento. Este método não é mais utilizado (MURDOCCA 2001).

**Entrada e saída controladas por interrupção**: Este método possibilita que a CPU não fique presa em espera ocupada até que um dispositivo esteja pronto para realizar a transferência de dados propriamente dita. Embora este método tenha sofrido melhorias e não é mais utilizado (MURDOCCA 2001).

**Acesso direto à memória (DMA –** _**Direct Memory Access**_**)**: A função do controlador (ou interface) é controlar seu dispositivo de E/S e manipular para ele o acesso ao barramento. Quando um programa detecta dados do disco, por exemplo, ele envia um comando ao controlador de disco, e este controlador irá emitir comandos de busca e outras operações de transferência entre dispositivo e memória principal. Este é o tipo de acesso utilizado atualmente pelas interfaces de E/S (FÁVERO, 2011).

_______

**➕ Pesquise mais**

Conheça mais sobre barramentos e dispositivos de E/S no [site](http://redeetec.mec.gov.br/images/stories/pdf/eixo_infor_comun/tec_inf/081112_org_arq_comp.pdf).

Conheça mais sobre os novos equipamentos e tecnologias do fabricante Dell acessando o [link](https://www.youtube.com/user/dellnobrasil).

_______

**💪 Faça você mesmo**

Tendo como base os conceitos de barramentos vistos, organize uma pesquisa que possa demonstrar três tipos de dispositivos de E/S, e qual tipo de interface usa para se conectar ao computador. Aponte em sua pesquisa qual é o fabricante destes dispositivos e qual fonte utilizou. Descreva nesta pesquisa em qual tipo de computador estes dispositivos estão conectados, descrevendo:

- Modelo/tipo de dispositivo.
- Modelo de processador usado pelo computador.
- Capacidade de memória RAM.
- Quais dispositivos de armazenamento possui.
- Qual tipo de conexão de rede permite.
- Quais dispositivos já estão presentes na placa-mãe (dispositivos onboard) ou se todos os periféricos são conectados através de interfaces externas, USB ou PCI Express, por exemplo.

_______

**💭 Reflita**

Considerando-se o conceito de “Internet das Coisas”, pode-se dizer que um aparelho que se conecte à internet terá internamente um sistema computacional que permita enviar e receber dados e, em alguns casos, até executar o seu processamento, o que leva à conclusão de que os computadores estão sendo empregados nos mais diversos aparelhos para as mais diversas aplicações. A ideia é que, cada vez mais, o mundo físico e o digital se tornem um só, através dispositivos que se comuniquem com os outros, os data centers e suas nuvens.

Fonte: TECHTUDO.