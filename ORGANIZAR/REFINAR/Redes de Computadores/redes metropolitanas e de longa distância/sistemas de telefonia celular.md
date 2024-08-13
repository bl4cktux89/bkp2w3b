**1.** **A Digitalização do Sistema de Telefonia**

No início dos anos 60 nem todas as pessoas possuíam um telefone em sua residência ou empresa, mas, o mundo todo já estavainterligado por ele. O que ocorreu nas décadas seguintes foi um processo gradual de digitalização do sistema de telecomunicações, até então, completamente analógico. As centrais locais que estavam interligadas as centrais Tandem e as demais centrais DDD e DDI o faziam por gigantescos cabos de par trançados que podiam chegar até 3600 pares. Estes cabos transitavam de forma subterrânea e era a única forma de interconectar as centrais.

Neste processo, toda a comunicação fim a fim era realizada de forma totalmente analógica, porém, com o aumento substancial de novos assinantes a infraestrutura não suportaria este crescimento, sem mencionar os diversos problemas de se trabalhar com sinais analógicos.

Foram necessários alguns anos de aprimoramento e desenvolvimento até que novas centrais telefônicas do tipo CPA-T, capazes de realizar comutação digital temporal, passassem a ser introduzidas no sistema. Neste novo ambiente, todos os processos são digitais, incluindo os sinais de voz que trafegavam entre as centrais juntamente com os avanços para transmissão digital destes sinais, as redes de telecomunicações seguiram sua jornada rumo a digitalização. Neste contexto então, os gigantescos cabos de par metálico começaram a ser substituídos por finos mas altamente funcionais, cabos de fibra óptica.

A voz humana é, por natureza, um sinal analógico. Para que este sinal possa trafegar em uma rede digital, precisa ser convertido. Para convertê-lo num sinal digital, foi adotado a técnica denominada PCM _**(Pulse CodeModulation)**_ ou Modulação por Código de Pulso. Esta técnica baseia-se no princípio de amostragem do sinal analógico, seguido da quantização (ajuste e definição do valor) e representação na forma binária do sinal amostrado. Evidentemente, quanto maior o número de amostras, maior será a fidelidade na recuperação do sinal original no seu destino. Para o sistema de telefonia foi adotada a taxa de 8.000 amostras por segundo (8 kHz), ou seja, quando falamos ao telefone, nossa voz é medida (amostrada) 8.000 vezes por segundo, sendo que o valor obtido, em cada uma das medições, será convertido em um número binário, sendo então, transmitido digitalmente a uma velocidade de 64.000 bits/s ou simplesmente 64Kbits que é o valor do canal de voz digital.(PINHEIRO, 2004).

**2. O Transporte dos Sinais Digitais**

Uma questão que precisava ser resolvida para viabilizar o transporte das informações agora digitalizadas de um ponto a outro da rede esbarrava no sentido da economia das vias agora por fibras ópticas, por razões práticas e econômicas, vários canais de voz precisariam ser agrupados e transmitidos, utilizando um único par de transmissores e um único meio de transmissão.

A solução encontrada foi a multiplexação que nos sistemas digitais, foi adotada a técnica da Multiplexação por Divisão de Tempo – TDM _**(Time-division Multiplex).**_ Esta técnica reserva para cada canal espaços de tempo pré-definidos chamados de _**(time slots)**_ para serem transmitidos. No Brasil, que adotou o mesmo padrão europeu para multiplexação de sinais digitais, são reunidos grupos de 32 canais dos quais, em geral, 30 transportam voz e 2 canais são reservados para: Um transporta sinais de sinalização e o outro sinais de alinhamento de quadro e sincronismo. (PINHEIRO, 2004).

A taxa de bits necessária para transportar estes 32 canais será então 2048Kbits/s (8.000 amostras por segundo x 8 bits x 32 canais = 2.048.000 bits/s). Na figura 1 observa-se a formação do grupo de primeira ordem TDM utilizado no Brasil e os demais níveis hierárquicos chamados de PDH - _**Hierarquia Digital Plesiócrona**_ de concentração, desenvolvidos para permitir o agrupamento de maiores quantidades de canais.

**3. O PDH**

A tecnologia PDH emprega a multiplexação assíncrona, isso crer dizer que ele é um canal Plesiócrono, ou seja, cada canal conta com um relógio que não é sincronizado com os relógios dos outros canais apesar destes canais serem idênticos. Estas diferenças de valores nos relógios podem ir até um limite estabelecido por normas.

A canalização PDH conta com cinco taxas de concentração de multiplexação conhecidas como hierarquia, cada uma tem sua própria taxa de composição e são reconhecidos dois padrões com diferentes valores, sendo um americano de menor capacidade e um europeu de maior capacidade que também é adotado aqui no Brasil. A tabela 1 ilustra a canalização PDH e seus valores por hierarquia.

O PDH utiliza a multiplexação por justificação positiva (inserção de bits). Após a sincronização os canais são multiplexados por intercalamento bit a bit, para compor o quadro (frame) da hierarquia.

Em cada nível de multiplexação é levado em conta o fato de que os relógios dos tributários, além de serem distintos, não são exatamente iguais, mas quase iguais, dentro de uma certa tolerância, por isso chamados sinais plesiócronos (ou seja, plesio, do grego, quase igual). A tabela 2 ilustra a tolerância do relógio a partir do canal primário de 64Kbits.

Cada passo da multiplexação utiliza um equipamento multiplex específico, com posições rígidas para cada tributário (canal). Para extrair tributários de menor hierarquia torna-se necessário demultiplexar os canais de hierarquia até essa hierarquia. A figura 2 ilustra esse processo,usando como exemplo o padrão PDH europeu.(FILHO, 2002).

Quando é necessário o transporte de taxas mais elevada, e por localidades mais distantes, seja esta informação voz ou dados, faz-se uso de outra tecnologia de multiplexação conhecida como SDH.

O SDH é um conjunto de equipamentos e meios físicos de transmissão que compõem um sistema digital síncrono de transporte de informações. Este sistema tem o objetivo de fornecer uma infraestrutura básica para redes de comunicação, principalmente as PSTN.

**4. O SDH**

As tecnologias SDH _**(Synchronous Digital Hierarchy)**_ são utilizadas para multiplexação em TDM com altas taxas de bits, tendo a fibra óptica como meio físico preferencial de transmissão. Sua elevada flexibilidade para transportar diferentes tipos de hierarquias digitais permite oferecer interfaces compatíveis com o padrão PDH europeu (nas taxas de 2 Mbit/s, 8 Mbit/s, 34 Mbit/s e 140 Mbit/s) e americano (nas taxas de 1,5 Mbit/s, 6 Mbit/s e 45 Mbit/s), além do próprio SDH (nas taxas de STM-1 = 155,5 Mbit/s, STM-4 = 622,08 Mbit/s, STM-16 = 2488,32 ou 2,5 Gbit/s e STM-64 = 9953,28 ou 10 Gbit/s).

O SDH também são baseadas em quadros síncronos de 125µs e canais de 64Kbit/s, em função da taxa de amostragem dos sinais de voz ser de 8.000/s e da utilização de 8 bits por codificação de cada amostra. No SDH é definida uma estrutura básica de transporte de informação denominada Módulo de Transporte Síncrono-1 _**(Synchronous Transport Module-1, STM-1)**_, com taxa de 155,5 Mbit/s. Esta estrutura define o primeiro nível de hierarquia. As taxas de bit dos níveis superiores são múltiplos inteiros do STM-1. Atualmente são padronizados quatro módulos de transporte a saber:

STM - 1;

STM - 4;

STM - 16;

STM - 64.

A tecnologia SDH permite ainda implementar mecanismos variados de proteção nos equipamentos e na própria rede, oferecendo serviços com alta disponibilidade e efetiva segurança sendo designada como a rede de transporte de dados.

No início, a multiplexação com elevada taxa de dados foi desenvolvida pela ECSA _**(Exchange Carriers Standards Association)**_ sediada nos Estados Unidos_**.**_ A ECSA então desenvolveu o padrão conhecido como SONET _**(Synchronous Optical Network),**_ que foi adotado nos EUA e entre outros países como o Japão. Após algum tempo o ITU-T europeu envolveu-se no trabalho para criar um único padrão internacional que fosse capaz  e possibilitasse que as redes de telefonia de países distintos pudessem ser interligadas. O resultado desse trabalho foi o conjunto de padrões e recomendações conhecido como SDH _**(Synchronous Digital Hierachy),**_ ou Hierarquia Digital Síncrona.

O desenvolvimento do SDH levou a um ajuste no padrão SONET para que os frames do segundo sistemas pudessem ser compatíveis tanto em tamanho como em taxa de bits, de forma que se pudessem interligar a redes do segundo padrões sem problemas de interface. A tabela 3 ilustra as taxa de dados nos dois sistemas e seus respectivos nomes.

Onde temos:

STS: _**Synchronous Transport Signal**_

STM: _**Synchronous Transport Module**_

OC: _**Optical Carrier**_

ANSI: _**American National Standards Institute**_

A hierarquia SDH foi concebida para uma arquitetura de multiplexação síncrona onde cada canal opera com um relógio sincronizado com os relógios dos outros canais, e é sincronizado com o equipamento multiplex através de um processo de justificação de bit e encapsulamento das informações em _**contêiner**_ de carga.

A esse _**contêiner**_ ou agrupamento de dados é adicionado um cabeçalho denominado POH, que o caracteriza e indica sua localização dentro do frame, e forma-se então um contêiner virtual ou simplesmente um VC _**(Virtual Container)**_ para cada canal. O SDH pode transportar também os diferentes tipos de sinais PDH não síncronos através do frame padronizado denominado STM-N _**(SyncronousTransport Module),**_ e assim adaptar ao SDH os sinais advindos do PDH. Os diversos canais multiplexados (VC's) normalmente são chamados de tributários, e os sinais de transporte gerados (STM-N) são chamados de agregados ou sinais de linha. (FILHO, 2003).

**5. O Frame do SDH**

O frame SDH tem tamanho padrão para cada hierarquia. Cada frame constitui uma unidade para fins de administração e supervisão da transmissão no sistema. Esses frames são transmitidos a uma taxa de 8000 frames por segundo (8KHz).

Na figura 3 é apresentado a estrutura genérica de um quadro STS-n do SONET, em que _**n**_ indica o número de canais básicos multiplexados em cada nível da hierarquia de multiplexação digital, conforme é mostrado na tabela 2 a duração de um quadro STS ou STM é sempre de 125µs, e seu tamanho em octetos varia de acordo com o nível de multiplexação. Tanto o STM como o STS possuem um campo de informação útil chamado de _**Synchronous Transport**_ _**Envelope**_ (SPE), que é inserido de forma variável em relação ao tempo, dentro da estrutura síncrona do STM/STS.

Além do campo de informação útil _**(payload),**_ os quadros STM/STS possuem mais três campos de informação ou cabeçalhos, estes contém informação para cada um dos protocolos dos três níveis da rede síncrona: rota, linha e seção, e que por isso também são chamados de:

- _Section overhead_ (SOH): informações de sincronismo de quadro, entro outras;
- _Line overhead_ (LOH): utilizado para multiplexar e demultiplexar as Unidades Administrativas (utilizado para compatibilizar SDH e PDH)
- _Path overhead_ (POH):

O POH e o _**payload**_ formam o campo do SPE, cujo início pode flutuar em relação à estrutura síncrona fixa do SDH/SONET. Os cabeçalhos LOH e o SOH estão localizados na parte fixa do quadro STM/STS. No nível de linha é feita a multiplexação e por isso os ponteiros (bytes H1, H2, H3), que implementam o mecanismo de adaptação entre o relógio do tributário e o relógio mestre do sistema SDH, estão localizados neste cabeçalho. (ROCHOL, 1999).

O frame SDH para a hierarquia STM-1, como exemplo, tem 2430 bytes, organizados em 9 linhas com 270 colunas de bytes, os quais são transmitidos serialmente linha a linha da esquerda para a direita, e de cima para baixo. Sua estrutura básica é ilustrada na figura 4.

Os campos do cabeçalho são descritos assim:

- RSOH _(RegeneratorSection Overhead) -_ Processado em cada equipamento da rede, contém informações de alinhamento e identificação do frame, monitoração de erro de regeneração, alarmes físicos externos ao equipamento, e supervisão de sistema. Contém também um canal de voz, para comunicação de técnicos entre equipamentos.
- MSOH _(Multiplex Section Overhead) -_ Processado apenas em equipamentos onde existe inserção _(add)_ ou retirada _(drop)_ de canais multiplexados, contém informações de monitoração e indicação de erros de multiplexação, controle de chaveamento de mecanismos de proteção, monitoração desincronismo e gerência de sistema.
- POH _(Path Overhead) -_ Processado em cada equipamento, possui os ponteiros que indicam onde selocaliza o primeiro byte do(s) VC(s) dentro da área de informação útil _(payload)_ do frame, e eventuais bytes provenientes de justificação desse(s) VC(s).

A incorporação dos ponteiros nas estruturas dos VC's do frame SDH permite que mesmos sinais com diferenças de fase e frequência possam ser transportados num mesmo frame, já que essas diferenças são acomodadas em bytes específicos do POH através do processo de justificação. (FILHO, 2002).

**6. Multiplexação SDH**

A figura 5 apresenta o processo de multiplexação dos canais tributários no frame SDH, a cada nível são agrupados novos canais onde aumenta-se substancialmente a quantidade de bits transportados.

O processo de multiplexação dos canais tributários no frame SDH tem os seguintes passos:

- Mapeamento, onde os tributários são sincronizados com o equipamento multiplex (justificação de bit), encapsulados e recebem seus ponteiros (POH) para formar os VC's;
- Alinhamento, onde os VC's recebem novos ponteiros para formarem as unidades TU _(Tributary Unit)_ ou AU _(Administrative Unit),_ para permitir que o primeiro byte do VC seja localizado;
- Multiplexação byte a byte, onde os VC's de baixa ordem são agrupados para compor os VC's de alta ordem ou os VC's de alta ordem são processados para formar os AUG _(Administrative Unit Group);_
- Preenchimento, onde, na falta de tributários configurados ou para completar o espaço restante de tributários de baixa ordem, são adicionados bits sem informação para completar o frame. (FILHO, 2003).

As redes de transporte utilizando as hierarquias PDH, SDH e SONET constituem toda a malha de telecomunicações hoje no mundo, suportando todos os serviços de voz (telefonia) e se adaptando para o tráfego de dados das redes locais e da própria Internet. Por exemplo, a tecnologia SDH tem sido muito amplamente usada principalmente em longas distâncias, expandindo a capacidade de transmissão de sinais e permitindo que cada vez mais, as redes de computadores (LAN’s) sejam mais confiáveis, seguras e com grande capacidade de tráfego de informações.

A tecnologia SDH vem a cada momento ganhando um espaço cada vez maior entre todas as outras tecnologias de transporte de alta capacidade como o ATM, WDM, GIGABIT ETHERNET, fazendo com que o conceito de redes se torne cada vez mais realidade com a sua utilização.

**7. Para refletir**

- Toda rede transmite, sincronamente e em fase, os sinais STM-n. A PDH é plesiócrona;
- Organização em bytes, enquanto que o entrelaçamento em PDH é feito por bits;
- Os comprimentos dos quadros são uniformes (sempre 125µs), o que não ocorre no sistema PDH;
- Uso de ponteiros para indicar o início de cada quadro e processar eventuais justificações. A PDH usa palavras de alinhamento;
- Alta capacidade de gerência (supervisão, operação, manutenção, etc.). Aproximadamente 5% dos bytes SDH são reservados para fins de supervisão e gerência, o que é um índice infinitamente maior que num sistema PDH;
- O sistema SDH pode acomodar os feixes plesiócronos nos quadros STM-n com total compatibilidade;
- Compatibilidade com tecnologias atuais e futuras. O SDH aceita e é capaz de transmitir todos os sinais tributários existentes nas redes atuais. Sua padronização já prevê que possa também ser usado para transportar serviços ainda não existentes;
- Padronização mundial, enquanto que a PDH tem padronização parcial;
- As redes SDH permitem acesso direto aos tributários, o que não é possível em PDH; • A transmissão pode se dar por Cross-Conetions e Add/Drop. Em PDH, só é possível transmitir ponto-a-ponto.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/1/267183/13804.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/1/267183/13804.png)

Figura 1 - Processo de multiplexação TDM em seus vários níveis hierárquicos de agrupamento

Fonte: (PINHEIRO, 2004)

|Hierarquia Digital Plesiócrona PDH|
|---|
|[[Hierarquia Digital Européia]]|
|[[Designação]]|
|[[Canal B]]|
|[[E1]]|
|[[E2]]|
|[[E3]]|
|[[E4]]|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/sistemas de telefonia celular/Untitled Database/Untitled 2\|Untitled 2]]|
|[[organizar/REFINAR/Redes de Computadores/redes metropolitanas e de longa distância/sistemas de telefonia celular/Untitled Database/Untitled\|Untitled]]|

  
  

|Nível Hierárquico|Taxa de bits nominal [kbits/s]|Freqüência relógio [kHz]|Tolerância do relógio [ppm: partes por milhão]|
|---|---|---|---|
|0|64|64|[[±100]]|
|1|2048|2048|[[±50]]|
|2|8448|8448|[[±30]]|
|3|34368|34368|[[±20]]|
|4|139264|139264|[[±15]]|

  
  

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267240/13810.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267240/13810.png)

Figura 2 - Desmultiplexação PDH

Fonte: Fonte: (FILHO, 2002)

|Hierarquia Digital Síncrona SDH/SONET|
|---|
|[[Designação SONET (ANSI)]]|
|[[STS-1 (OC-1)]]|
|[[STS-3 (OC-3)]]|
|[[STS-9 (OC-9)]]|
|[[STS-12 (OC-12)]]|
|[[STS-18 (OC-18)]]|
|[[STS-24 (OC-24)]]|
|[[STS-36 (OC-36)]]|
|[[STS-48 (OC-48)]]|
|[[OC-192]]|
|[[OC-768]]|

  
  

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267297/13812.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/2/267297/13812.png)

Figura 3 - Quadro SDH genérico

Fonte: Fonte: (ROCHOL, 1999)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268304/13814.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268304/13814.png)

Figura 4 - Frame STM-1 do SDH

Fonte: Fonte: (ROCHOL, 1999)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268371/13815.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/3/268371/13815.png)

Figura 5 - Multiplexação SDH

Fonte: Fonte: (FILHO, 2003)