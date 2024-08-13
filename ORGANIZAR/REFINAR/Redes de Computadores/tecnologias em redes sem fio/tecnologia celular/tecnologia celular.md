### Objetivo:

Nosso assunto deste tópico é o atendimento aos assinantes por rede de dados através da telefonia celular. Para tanto, as tecnologias mais utilizadas atualmente são: GSM – _**Global System for Mobile**_ e o GPRS – _**General Packet Radio Service**_ que inicialmente foram desenvolvidas para suportar a comunicação móvel de voz e nos dias atuais são as mais utilizadas para a transmissão de dados em estações móveis.

### Introdução

A tecnologia GSM se tornou mundialmente a mais utilizada, com bilhões de equipamentos celulares em centenas de países. Tal fato ocorreu porque é uma tecnologia puramente digital e apresenta serviços e custos operacionais mais baixos que seus concorrentes híbridos. Por ser digital, ela permite rapidamente a incorporação da transmissão de dados e voz neste sistema único. O GSM é um padrão aberto, desenvolvido pela 3GPP (http://www.3gpp.org), que constantemente sofre atualizações, melhorando o sistema e permitindo maior capacidade na transmissão com melhor qualidade.

### Características Básicas

O GSM opera nas faixas de frequência de 850 e 1900 MHz nas Américas, com exceção do Canadá e nas faixas de 900 e 1900 MHz no restante do mundo. Esta tecnologia usa a combinação do TDMA – Acesso Múltiplo por Divisão de Tempo e do FDMA – Acesso Múltiplo por Divisão de Frequência. As frequências disponíveis são divididas em duas bandas, o _**uplink**_ que é utilizado para a transmissão da unidade móvel (telefone celular) e o _**downlink**_ que é usado para a transmissão da estação base.

O FDMA permite a divisão da banda em canais de 200 MHz com uma taxa de transmissão de dados de até 270 Kbps. Cada canal de 200 MHz é atribuído a cada estação, sendo que este é novamente dividido usando agora a tecnologia TDMA em oito intervalos de tempo conhecido como _**Time Slots**_. Os celulares utilizam um canal para transmitir e outro para receber.

As vantagens do sistema GSM são os serviços de baixo custo, como a troca de mensagens e com respeito à implementação para as operadoras. A principal desvantagem é que o GSM utiliza uma rede TDMA, considerada menos competitiva que sua concorrente o CDMA. O desempenho das duas tecnologias é praticamente muito semelhante, apesar disso o sistema GSM manteve a compatibilidade com os dispositivos originais e hoje é a tecnologia mais utilizada no mundo, permitindo assim um perfeito sistema de _**roaming**_ global. A figura 1 ilustra os equipamentos que inalguraram de fato a telefonia celular para a população. (RAPPAPORT, 2009)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293466/18770.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293466/18770.jpg)

Figura 1 - Aparelhos de tecnologia TDMA e CDMA

### Componentes da Rede GSM

- _**Mobile Station**_ **(MS)**

É o terminal ou estação móvel do assinante (o aparelho celular) dotado de um cartão inteligente conhecido como SIM _**Card**_ ou Módulo de Identidade do Assinante _**(Subscriber Identity Module).**_ Sem o SIM _**Card**_ a Estação Móvel não está associada a um usuário e não pode fazer, nem receber chamadas. O SIM _**Card**_ armazena, entre outras informações, um número de 15 dígitos que identifica unicamente uma dada Estação Móvel, denominado IMSI ou Identidade Internacional do Assinante Móvel _**(International Mobile Subscriber Identity).**_ O IMSI tem o seguinte formato:

IMSI = MCC + MNC + MSIN

Onde:

MCC = _**Mobile Country Code**_ (código do país do celular);

MNC = _**Mobile Network Code**_ (código da rede celular);

MSIN = _**Mobile Station Identification Number**_ (número de identificação do celular).

Exemplo: MCC 311 + MNC 030 + MSIN 000003258 – 311 030 000003258

Uma vez contratado o serviço junto a uma operadora, o usuário passa a dispor de um SIM _**Card**_, que ao ser inserido em qualquer terminal GSM, faz com que este passe a assumir a identidade do proprietário do SIM _**Card**_. No SIM _**Card**_ é gravado um número conhecido como: MSISDN - _**Mobile Service ISDN Number**_ que representa o número discado associado ao assinante. Este número é fornecido para o assinante pela operadora na hora da compra e é gravado no cartão. O MSISDN tem o seguinte formato:

MSISDN = CC + NDC + SN

Onde:

CC = _**Country Code**_ (código do país);

NDC = _**National Destination Code**_ (código nacional);

SN = _**Subscriber Number**_ (número de assinante).

Exemplo: 55 11 99972222 / (CC)=55 (NDC) = 11 (SN)=99972222

- **IMEI -** _**International Mobile Equipment Identity**_

É um número de série único alocado no hardware do móvel. É registrado pela operadora e opcionalmente gravado na AUC (Central de Autenticação da Rede) para propósito de validação.

- _**Base Station System**_ **(BSS)**

É o sistema encarregado da comunicação com as estações móveis em uma determinada área. É formado por várias _**Bases Transceiver Station**_ (BTS) ou ERBs, que constituem uma célula e uma _**Base Station Controller**_ (BSC), que controla estas BTSs.

- _**Mobile-Services Switching Centre**_ **(MSC)**

É a Central de Comutação e Controle (CCC), responsável pelas funções de comutação e sinalização para as estações móveis localizadas em uma área geográfica designada como a área do MSC. A diferença principal entre um MSC e uma central de comutação fixa é que a MSC tem que levar em consideração a mobilidade dos assinantes (locais ou visitantes), inclusive o _**handover**_ da comunicação quando estes assinantes se movem de uma célula para outra. O MSC encarregado de rotear chamadas para outros MSCs é chamado de Gateway MSC.

- _**Home Location Register**_ **(HLR)**

É o Registro de Assinantes Locais que contém a base de dados das informações sobre os assinantes de um sistema celular.

- _**Visitor Location Register**_ **(VLR)**

É o Registro de Assinantes Visitantes que contém a informação sobre os assinantes em visita _**(roaming)**_ a um sistema celular (base de dados).

- _**Authentication Center**_ **(AUC)**

É o Centro de Autenticação, responsável pela autenticação dos assinantes no uso do sistema. O Centro de Autenticação está associado a um HLR e armazena uma chave de identidade para cada assinante móvel registrado naquele HLR, possibilitando a autenticação do IMSI do assinante. É também responsável por gerar a chave para criptografar a comunicação entre MS e BTS.

- _**Equipment Identity Register**_ **(EIR)**

É o Registro de Identidade do Equipamento, uma base de dados que armazena os IMEIs dos terminais móveis de um sistema GSM.

- _**Operational and Maintenance Center**_ **(OMC)**

É o Centro de Operação e Manutenção, a entidade funcional através da qual a operadora monitora e controla o sistema. O grande avanço nas redes GSM tem sido a implantação da tecnologia EDGE - _**Enhanced Data Rates**_ que aliada ao GPRS permite a transmissão de dados em taxas mais elevadas de até 1 GBps.  Outros avanços significativo das comunicações através da tecnologia GSM são as opções do: 2G, 3G onde temos o GRPS, EDGE, UMTS, HSPA e finalmente a versão 4G com o LTE.

### Novas Tecnologias GSM

A tecnologia da telefonia celular surgiu nos Estados Unidos durante os anos 80, com o lançamento da rede de celular AMPS _**(Advanced Mobile Phone Service).**_ Ela usava o FDMA _**(Frequency Division Multiplexing Access)**_ para transmitir voz através do sinal analógico. É considerada a primeira geração móvel (1G) e esta tecnologia não utilizava as técnicas do GSM.

A segunda geração (2G) surgiu na década de 90, quando as operadoras móveis implantaram dois padrões concorrentes de sinais digitais para voz, o GSM _**(Global System for Mobile Comunications)**_ e o CDMA _**(Code Division Multiple Access).**_ Naquela época no Brasil, o CDMA foi adotado pela Vivo, enquanto que a Oi, Tim, Claro e Brasil Telecom adotaram o GSM.

A terceira geração de telefonia móvel ficou designada como 3G é a que estamos vivenciando hoje em maior número de terminais. Em 1999 foi desenvolvido o IMT-2000, um padrão global para o 3G com o objetivo de facilitar o crescimento desta tecnologia com a perspectiva do aumento da banda e poder fornecer suporte a várias aplicações. Para conseguir esta evolução, as operadoras precisaram realizar grandes _**upgrades**_ em suas redes existentes, o que levou ao estabelecimento de uma família bem distinta da tecnologia 3G: a 3GPP. (HAMMERSCHMIDT, 2008)

A 3GPP _**(3rd Generation Partneship Project)**_ é uma colaboração entre grupos e associações de telecomunicações formada em 1998 para fomentar a implantação de redes 3G que descendem do GSM. Essa tecnologia evoluiu da seguinte forma:

- GPRS – Velocidades de até 144 Kbps;
- EDGE – Velocidade até 384 Kbps;
- UMTS – Velocidade de 384 kbit/s ou 7.2 Mbits/s (down), 384 kbit/s (up);
- HSPA – Velocidade máxima em até 14 Mbps;
- LTE – Velocidade de até 100 Mbps.

A implantação da tecnologia GPRS começou no ano 2000, seguido pela EDGE em 2003. Embora essas duas tecnologias sejam definidas como 3G pelo padrão IMT-2000, às vezes são chamados de “2,5G” porque não trocam uma grande quantidade de dados. A tecnologia EDGE ainda está sendo substituída pela tecnologia HSPDA no Brasil. Você já deve ter reparado que o indicador da conexão oscila entre duas letras: H e E, ou seja, HSPDA (em locais com cobertura 3G) e EDGE (onde ainda permanece a tecnologia 2G). (HAMMERSCHMIDT, 2008)

A tecnologia LTE é o próximo passo na evolução da rede móvel baseada na tecnologia GSM. Uma das várias padronizações da tecnologia 3GPP é o formato multimídia. É por isso que muitos vídeos gravados por celulares são salvos no formato 3GPP (ou apenas 3GP). A figura 2 ilustra um terminal LTE de ultima geração.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293467/18771.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293467/18771.png)

Figura 2 - Equipamento de ultima geração LTE

### Tecnologia GPRS

A tecnologia GPRS – _**General Packet Radio Service**_ - é baseada em comutação de pacote e oferece taxas de transmissão mais elevadas que as tecnologias tradicionais baseadas em comutação de circuitos. A técnica de comutação de pacotes permite que os usuários compartilhem o mesmo canal de comunicação e só ocupem o canal quando têm dados a transmitir. Como a ocupação da banda é aleatória, a mesma só será utilizada quando um usuário tiver algum dado a ser transmitido, permite desta forma um melhor aproveitamento do canal. As redes GPRS são utilizadas para a transmissão de dados, serviços de correio eletrônico, acesso às páginas da Internet e toda e qualquer comunicação que seja baseada na comutação de pacotes. Sendo assim, as companhias de telefonia celular podem prover o acesso à Internet com uma alta taxa de transmissão a baixo custo, pois o parque todo de equipamentos já foi implementado na configuração GSM.

A metodologia de controle do acesso da rede GPRS é exatamente igual à da rede GSM, ou seja, é baseado em FDMA – _**Frequency Division Multiple Access**_. Quando se deseja executar uma transmissão, o usuário inicia uma sessão e obtém dois canais de frequências, sendo um para a transmissão e outro para a recepção de dados. Estes canais são multiplexados em frequência e inseridos no pacote de dados de um _**Time Slot**_ TDMA da rede GSM. O GPRS suporta o tráfego dos protocolos IP – _**Internet Protocol**_, PPP – _**Point to Point Protocol**_ e de todo o tráfego baseados no IPv4 – _**Internet Protocol Versão 4.**_

### Tecnologia EDGE

A tecnologia EDGE _**(Enhanced Data Rates for GSM Evolution)**_ tem como base a tecnologia GSM, mas se mostra mais sofisticado que o padrão GPRS. As características do EDGE são bastante parecidas com as especificações do GPRS, inclusive na utilização de múltiplos _**slots**_ nas conexões, mas o padrão utiliza um esquema de modulação mais avançado (8-PSK) e novos tipos de codificação de canal, fazendo com que as taxas de transferência de dados aumentem consideravelmente. A velocidade máxima teórica da tecnologia é de 473,6 Kb/s, embora dificilmente ultrapasse 384 Kb/s. O EDGE é referenciado como sendo uma tecnologia "2,5G", se é que ela exista!

### Tecnologia UMTS

A tecnologia UMTS _**(Universal Mobile Telecommunications Service)**_ é considerado como uma evolução do padrão GSM, com a sua implementação podendo inclusive aproveitar a estrutura deste. O UMTS é considerado, de fato, uma tecnologia da terceira geração em si. O UMTS surgiu principalmente como resultado de um trabalho envolvendo empresas e entidades ligadas ao consórcio 3GPP que lidera os esforços para o desenvolvido da tecnologia.

A tecnologia UMTS tem entre as suas principais características a implementação com base no padrão WCDMA e posteriormente com maior velocidade uma versão foi desenvolvida baseada no padrão HSPA. O UMTS baseado no WCDMA consegue desenvolver velocidades máximas de 384Kbits por segundo, enquanto o UMTS baseado em GSM consegue alcançar velocidades de até 7.2Mbits por segundo para _**downlink**_ e 384kbit por segundo para _**uplink.**_

### Tecnologia HSPA

Como evolução o HSPA _**(High Speed Packet Access)**_ tem como base dois protocolos: o HSDPA _**(High Speed Downlink Packet Access)**_ e o HSUPA _**(High Speed Uplink Packet Access).**_ Ambos trabalham utilizando portadoras de 5 MHz, mas o HSDPA se direciona ao _**download**_, enquanto que o HSUPA, é focado no _**upload.**_ O HSDPA pode oferecer taxas de transferência de dados de até 14,4 Mb/s (as demais velocidades são de 1,8 Mb/s, 3,6 Mb/s e 7,2 Mb/s), enquanto que o HSUPA (também conhecido como _**Enhanced Uplink**_ - EUL) oferece velocidade máxima de 5,76Mbits.  Níveis tão altos se devem à redução do TTI _**(Transmission Time Interval)**_, Intervalo de Tempo de Transmissão, que varia entre 1 e 3 milissegundos, enquanto que em outros padrões esta medida gira em torno dos 10 milissegundos. Por serem mais recentes, as especificações HSPA são também chamadas de geração 3,5G.

### Tecnologia LTE

A quarta geração (4G) da telefonia móvel tem início com a tecnologia LTE _**(Long Term Evolution).**_ Em realidade o LTE é mais uma proposta apresentada pela 3GPP. Segundo a visão da ITU _**(International Telecommunication Union),**_ o LTE não cumprir com todas as exigências técnicas necessárias para ser considerada um padrão 4G, porém, comercialmente ele é aceito como uma tecnologia de quarta geração. O padrão LTE chama a atenção pelas velocidades com as quais pode trabalhar, dependendo da combinação de recursos implementados na rede e do aparelho do usuário, pode-se chegar a taxas de 300 Mb/s para download e 75 Mb/s para upload. Para facilitar a assimilação do aspecto de velocidade ao nível de compatibilidade de aparelhos, o LTE é determinado por categorias:

- Categoria 1: download de até 10 Mb/s; upload de até 5 Mb/s;
- Categoria 2: download de até 50 Mb/s; upload de até 25 Mb/s;
- Categoria 3: download de até 100 Mb/s; upload de até 50 Mb/s;
- Categoria 4: download de até 150 Mb/s; upload de até 50 Mb/s;
- Categoria 5: download de até 300 Mb/s; upload de até 75 Mb/s.

Estas velocidades são teóricas, pois, dificilmente são alcançadas em sua totalidade mesmo porque há uma série de fatores que determinam as taxas que uma rede LTE pode atingir. A quantidade de antenas em uso pelas estações Rádio Base ERB, considerando também seu funcionamento com as técnicas MIMO. A frequência do canal do LTE pode ser de 1,4 MHz, 3,5 MHz, 15 MHz ou 20 MHz. Teoricamente, quanto maior a frequência disponível, maior é a taxa de transferência de dados. O LTE também se diferencia pela forma de acesso, enquanto as tecnologias UMTS e HSPA são baseadas no padrão WCDMA, o LTE utiliza as especificações OFDMA _**(Orthogonal Frequency Division Multiple)**_, que distribui as informações da transmissões entre diversos subconjuntos paralelos de portadoras, sendo este item que favorece velocidades maiores para o _**downlink**_. (ALECRIM, 2013)

O OFDM é a mesma técnica utilizada nos rádios WIFI padrão IEEE 802.11g em diante, e com isso consegue aumentar substancialmente a taxa de dados transmitidos. Em relação ao _**uplink**_, o esquema utilizado é o SC-FDMA _**(Single Carrier Frequency Division Multiple Access)**_ que é uma especificação semelhante ao OFDMA, mas que consegue reduzir o consumo de potência, fazendo com que o uso de energia por parte dos dispositivos conectados também diminua. O SC-FDMA também se utiliza de um subconjuntos de portadoras.

Embora o LTE se apresente como um padrão bastante avançado, já há trabalhos em prol de uma versão melhorada, o LTE _**Advanced**_, esta sim totalmente compatível com os requisitos da ITU para uma tecnologia 4G. A expectativa é a de que esta variação possa oferecer taxas de até 1Gbits por segundo para _**download**_ e 500Mbits por segundo para upload. O LTE pode funcionar com várias faixas de frequência. No Brasil, por exemplo, a tecnologia faz uso da frequência de 2,5 GHz. A tabela 1 ilustra um resumo das diferentes tecnologias e suas respectivas velocidades. (ALECRIM, 2013)

Tabela 1 – Comparativo de tecnologias, velocidades e latência

![[Untitled 80.png|Untitled 80.png]]

### Revisão:

A Tecnologia GSM é a mais utilizada no mundo, pois demanda baixos custos para a implementação e gerenciamento das redes instaladas se comparada às outras tecnologias de acesso móvel.

O GSM é uma tecnologia totalmente digital, podendo prover aos seus usuários uma melhor qualidade de serviços.

O GSM utiliza duas técnicas para seu funcionamento básico: o FDMA e o TDMA.

O GPRS é uma tecnologia de transporte de dados que utiliza a estrutura da rede GSM.

Tanto o GSM quanto as demais nomenclaturas para telefonia móvel utiliza dois canais de comunicação, sendo um para a transmissão e outro para a recepção. Ambos os canais são alocados em um _**Time Slot**_ do TDMA. Como a utilização dos canais usados pelos usuários é aleatória, estes podem ser alocados dinamicamente para melhorar o canal de comunicação, aumentando sua taxa de transmissão.

Atualmente temos a tecnologia LTE onde na Categoria 5 consegue-se _**download**_ de até 300 Mb/s e _**upload**_ de até 75 Mb/s.