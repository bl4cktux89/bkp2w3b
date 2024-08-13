**1. Introdução**

O crescimento da utilização da Internet nestes últimos anos com cada vez mais pessoas conectadas e com novos escritórios do tipo _**home offices**_, sistemas de videoconferência, telefonia IP e a necessidade da navegação com acesso rápido levaram as atuais tecnologias de acesso de última milha a sua exaustão e colapso, pois, o meio utilizado para esta conexão que são as atuais última milha das redes PSTN não suporta altas velocidades de dados, pois estão atreladas as condições físicas do canal que atualmente ainda são os cabos e fios metálicos.

Em busca de suprir a necessidade da conectividade em alta velocidade, muitas propostas são pesquisas e uma das mais conhecidas é o ADSL, sigla para _**(Assymmetric Digital Subscriber Line)**_ ou, Linha Digital Assimétrica para Assinante. Este padrão é bastante popular em nosso país porque aproveita a infraestrutura de última milha da telefonia fixa, permitindo assim conexões velozes a preços relativamente baixos.

Quando a Internet começou a se popularizar no Brasil, a maioria das pessoas usava a conexões chamada _**dial up**_, ou conexões discadas. Para tanto era necessário conectar o computador a um modem e este, por sua vez, a uma linha telefônica. Em seguida, o usuário tinha que utilizar um programa específico para discar ao número de um provedor de forma a estabelecer a conexão. O problema deste tipo de conexões discadas era a baixa velocidade oferecida, algo em torno de 56Kbits em sua melhor condição (melhor condição significava estar muito próximo fisicamente do DG da concessionária de telecomunicações), e ainda tinham a desvantagem de deixar a linha totalmente ocupada em quanto existisse a conexão com a Internet o que acarretava à tarifação convencional por minuto de uso e como linha dedicada para voz, apresentava instabilidades ocasionando quedas constantes. (ALECRIM, 2012)

A tecnologia ADSL, que surgiu em meados 1989, se mostra como uma alternativa viável porque também utiliza a infraestrutura da telefonia convencional, mas o faz sem deixar a linha ocupada. Além disso, o padrão é capaz de oferecer velocidades de transferência de dados altas e a sua tarifação é feita de maneira distinta das chamadas telefônicas.

Na verdade, o ADSL não é um padrão único, mas sim parte de uma familia de tecnologias chamada DSL _**(Digital Subscriber Line)**_ ou apenas xDSL. Entre as especificações estão padrões como HDSL e VDSL. A letra A do padrão ADSL significa Assimétrico, ou seja, velocidades diferentes de _**downlink**_ e _**uplink**_.

**2. Funcionamento do xDSL**

O funcionamento básico do ADSL está no fato da utilização do canal de frequência do cabo que não são utilizadas pela voz. O que acontece é que, quando o telefone está sendo utilizado para uma chamada telefônica, esta utiliza apenas uma pequena parte da capacidade de transmissão da linha. Isso acontece porque, normalmente, uma chamada de voz utiliza uma frequência de onda entre 300 Hz e 4000 Hz. Trata-se de um intervalo que corresponde a uma faixa muita pequena da capacidade da linha. O restante pode então ser utilizado para aplicações que funcionam em frequências maiores. É neste ponto que as tecnologias DSL entram em cena.

A utilização do espectro livre, isto é, da parte não utilizada para voz, geralmente é feita com a técnica FDM (_**Frequency Division Multiplexing) ou**_ Multiplexação por Divisão de Frequência e com a técnica de _**Echo Cancellation,**_ ou Cancelamento de Eco.

Com o FDM a parte do espectro livre é destinada ao envio de dados _**(upstream)**_ e outra parte ao recebimento de dados _**(downstream),**_ sendo esta última maior e dividida em canais menores mais rápidos para melhor desempenho. Já com o _**Echo Cancellation**_, as partes para _**upstream**_ e _**downstream**_ se sobrepõem no espectro, mas o uso de cancelamento de eco, procedimento que remove a distorção do sinal durante a transmissão a partir de cálculos de subtração, consegue separá-las perfeitamente.

Para que o xDSL possa utilizar a parte da banda não usada pela voz ou seja, depois dos 4KHz, se faz necessário empregar a técnica da modulação, que é um processo de transformar dados e voz em sinais para tráfego em ondas de radiofrequência. Para este fim, o ADSL conta, essencialmente, com duas técnicas: a mais antiga chamada de CAP _**(Carrierless Amplitude Phase)**_ e a mais atual e mais utilizada comercialmente a DMT _**(Discrete Multitone).**_ (TEIXEIRA, 2010)

Na modulação CAP é utiliza a técnica FDM, que divide a linha telefônica em três partes: uma que corresponde às chamadas de voz, outra que é destinada ao envio de dados _**(upstream)**_ e uma terceira que é reservada ao recebimento de dados _**(downstream),**_ sendo que as duas últimas são as responsáveis pela conexão junto a Internet.

Por padrão, a faixa de voz vai de 0 a 4 KHz, enquanto que o _**upload**_ fica com a parte entre 25 e 160 KHz, por sua vez, a faixa do _**download**_, ocupa a maior parte da faixa, começando em 240 KHz e chegando, no máximo, até a 1.550KHz sendo que o valor normal é de 1.100KHz. A figura 1 ilustra esta distribuição.

A modulação DMT é a mais utilizada, podendo usar tanto a técnica FDM quanto a técnica de Cancelamento de Eco. Na DMT a linha telefônica continua sendo utilizada para tráfego tanto para voz quanto de dados, porém, agora o canal todo de aproximadamente 1.100KHz (0 a 1.100KHz) são divididos em até 256 canais, cada uma com largura de 4 KHz e espaçamento entre eles de 4,3125 KHz. A parte inicial do canal os seis primeiros _**slots**_, normalmente são destinados para as ligações de voz, ficando também um grupo responsável pelo _**upstream**_ entre os canais de 6 a 30 e outro grupo maior pelo _**downstream**_. No entanto, havendo uso de Cancelamento de Eco, os canais de _**upstream**_ também podem ser utilizados para _**downstream**_. A técnica DMT ganhou preferência no mercado por oferecer melhor desempenho e maior resistência a ruídos e interferências na transmissão. Um dos motivos para isso é o fato de cada canal ser monitorado. Os canais que estiverem, por algum motivo, operando com baixa qualidade, perdem prioridade na transmissão do sinal, trabalhando com menor quantidade de bits que os canais em melhor situação. (TEIXEIRA, 2010)

**3. Equipamentos ADSL**

Para o acesso a uma conexão ADSL faz-se necessário a utilização de um modem que será conectado entre a linha telefônica e o roteador ou computador do assinante. Tecnicamente a denominação do modem é ATU-R _**(ADSL Terminal Unit – Remote),**_ ou Unidade Terminal ADSL - Remoto. Esta conexão, deverá ser intermediada por um microfiltro de nome _**splitter**_, cuja função é de criar um canal para a ligação com o modem e outro canal para a comunicação com o aparelho telefônico. A não utilização do _**splitter**_ ocasiona no monofone do telefone ruídos (sinais modulados) quando o assinante está realizando uma ligação de voz. A figura 2 ilustra o modem e o _**spliter**_ utilizado nas conexões ADSL.

De um lado da conexão, ou seja, na casa do assinante o modem deve então ser ligado a um computador ou a um equipamento de rede, como um roteador Wi-Fi, para que os equipamentos ligados a estes tenham acesso à internet. O dispositivo modem então, deverá estar conectado à linha telefônica onde este irá executar sua função de organizar o fluxo de dados para que a transmissão ocorra dentro das frequências estabelecidas para _**upstream**_ e _**downstream**_.

Na ponta oposta da conexão está uma central telefônica. Nela, o sinal de cada linha telefônica é separado com a ajuda também de _**splitters**_, de forma que o que é sinal de voz seja enviado a rede PSTN _**(Public Switched Telephone Network)**_ que trata deste tipo de comunicação e o que são dados sigam para um equipamento denominado DSLAM _**(Digital Subscriber Line Access Multiplexer).**_

Na central telefônica, o DSLAM ou, ATU-C (_**ADSL Terminal Unit – Central)**_, tem a função de concentrar os sinais digitais de várias linhas telefônicas que atendem a um bairro, por exemplo como se estas fossem uma só para conectá-las a um link de alta velocidade de acesso à internet. Para isso, cada DSLAM precisa se comunicar com um BRAS _**(Broadband Remote Access Server).**_ Este equipamento tem entre as suas funções concentrar as conexões oriundas de uma ou mais DSLAMs e alocar endereços IP para cada linha que faz parte da rede. Tipicamente, a comunicação entre DSLAM e BRAS é realizada através de uma conexão ATM _**(Asyncronous Transfer Mode)**_ ou por tecnologia Ethernet. Figura 3 ilustra um equipamento DSLAM. (ALECRIM, 2012)

**4. Limites de Distância.**

Há um fator importante que pode limitar ou até mesmo impossibilitar a assinatura de um serviço de ADSL: a distância física entre o modem do usuário e o DSLAM, ou seja, entre o ATU-R e o ATU-C. Quanto mais longe um estiver da outro, menor qualidade e velocidade a conexão terá. A distância máxima viável é de aproximadamente 6 quilômetros, podendo ser um pouco menor dependendo das características da região e da qualidade dos equipamentos. De qualquer forma, o ideal é que este intervalo não supere 4 quilômetros. É por isso que lugares com poucos habitantes ou muito afastados, como áreas rurais, não raramente são desprovidos de acesso à internet via ADSL. (ALECRIM, 2012)

**5. Outros Tipos de DSL**

**5.1 HDSL** _**(High Bit Rate digital Subscriber Line)**_

Trata-se de uma especificação que surgiu como opção na transmissão de dados em linhas telefônicas digitais dos tipos T1 e E1. Entre as suas principais características estão o modo de operação _**full duplex**_ e transmissão simétrica: 784Kb/s para _**downstream**_ e outros 784Kb/s para _**upstream**_, totalizando pouco mais de 1,5Mb/s. Em linhas E1, este total pode chegar a 2Mb/s. Em todos os casos, a distância máxima considerada é de aproximadamente 5 quilômetros. O ADSL por exige o uso de dois pares de fios trançados e até três pares em linhas E1, e não permitir chamadas de voz durante a conexão à Internet.

**5.2 SDSL** _**(Symmetric Digital Subscriber Line)**_

O SDSL é bastante parecido com o HDSL, tipicamente transmite dados de maneira simétrica, possui taxas máximas de 1,5Mb/s (T1) ou 2Mb/s (T2) e não permite o uso de voz e dados ao mesmo tempo. Por outro lado, possui a vantagem de exigir apenas um par de fios da rede telefônica.

**5.3 SHDSL** _**(Single Pair High Speed Digital Subscriber Line)**_

O SHDSL é uma tecnologia que também trabalha de maneira simétrica, se for implementada utilizando apenas um par de fios pode alcançar velocidade de até 2,3 Mb/s e com dois pares, este limite aumenta para até 4,6 Mb/s.

**5.4 VDSL** _**(Very High Bit Rate Digital Subscriber Line)**_

O VSDL é uma tecnologia reconhecida em 2004 que se assemelha ao ADSL, trabalhando, assim como este, de maneira assimétrica, utilizando mais frequentemente a técnica DMT e permitindo uso de voz e dados simultaneamente. Seu diferencial está em sua capacidade de atingir taxas de transferência consideravelmente mais altas de até 52Mb/s no _**downstream**_ e até 16Mb/s no _**upstream.**_ A tecnologia também pode ser ajustada para trabalhar de maneira simétrica.

**5.5 VDSL2** _**(Very High Bit Rate Digital Subscriber Line2)**_

Em 2006 o VDSL2 foi ratificado, recebendo a identificação ITU G.993.2. Esta versão pode atingir até 100Mb/s no _**downstream**_ e 30Mb/s no _**upstream**_. Velocidades tão altas permitem inclusive que tanto o VDSL quanto o VDSL2 sejam utilizados para oferecer comunicação por voz, acesso à Internet e assinatura de TV (IPTV) por meio de uma única linha telefônica.

Taxas tão altas são possíveis graças a uma combinação de fatores, como o uso de frequências maiores na linha telefônica de até 12MHz no VDSL e até 30MHz no VSDL2 e a combinação com outra tecnologia, como fibra óptica. Neste último caso, a estrutura da rede da operadora por estar quase que totalmente coberta por esta tecnologia, ficando apenas as últimas centenas de metros até o local do usuário conectadas pelo tradicional par de fios. A desvantagem das conexões VDSL e VDSL2 está justamente no aspecto da distância entre a central e a localização do usuário, normalmente, o limite suportado é de até 1,5 quilômetro, com o VDSL2 só podendo ter sua velocidade atingida em sua totalidade em um raio máximo de pouco mais de 300 metros.

**6. Para Refletir**

- A tecnologia xDSL veio para suprir as necessidades de alta velocidade para conexão de usuários na última milha.
- Esta tecnologia consegue compartilhar a linha de assinantes para serviços de voz e de dados simultaneamente.
- A distância máxima das conexões ADSL não podem ser superiores a 4Km.
- Nas diversas tecnologias xDSL são utilizados de um a três pares de fios da rede pública de telefonia, a PSTN.
- O ADSL tem seus valores de _downstream_ e de _upstream_ com valores diferentes.
- O VDSL2 consegue atingir velocidades de até 100Mbits, porém não superior a 300 metros em distância.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261481/13867.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261481/13867.png)

Figura 1 - Modulação CAP

Fonte: Fonte: (ALECRIM, 2012)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261482/13870.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261482/13870.jpg)

Figura 2 - Conexões ADSL e Detalhes do Splitter

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261483/13871.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/4/261483/13871.jpg)

Figura 3 - Equipamentos DSLAM

Fonte: Fonte: (http://www.zhone.com/products/)