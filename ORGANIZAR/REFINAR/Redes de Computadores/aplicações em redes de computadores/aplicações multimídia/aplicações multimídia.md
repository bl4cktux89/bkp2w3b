### **Redes Multimídia**

O protocolo IP e a Internet realmente são um grande sucesso, não só para o tráfego de dados, mas, o que está mesmo dominando o mundo, é o trafego de voz,  áudio, vídeo e jogos interativos.

Percebeu-se que a Internet é de boa qualidade, barata, de alta capilaridade e permite mecanismos de qualidade de serviço e segurança. Porque não utilizar para o trafego de voz e vídeo em tempo real? Sim, as grandes empresas de entretenimento enxergaram esta rede e estão distribuindo milhares ou milhões de conteúdos pela Internet. Obviamente, o núcleo da rede deve estar e está se preparando para este novo mundo de milhões de conteúdos que se espalham pela Internet e são armazenados na nuvem, localmente ou por meio de outras formas de armazenagem.

Para entender como o núcleo da rede e os acessos estão crescendo, basta analisarmos as propriedades de um video.

### **Propriedades de vídeo**

- Talvez a característica mais destacada do vídeo seja sua alta taxa de bits.
- O vídeo distribuído pela Internet costuma variar de 100 kbits/s para videoconferências de baixa qualidade até mais de 3 Mbits/s para os filmes de fluxo de vídeo com alta definição.
- Outra característica importante do vídeo é que ele pode ser compactado, compensando assim a qualidade com a taxa de bits.
- Também podemos usar a compactação para criar múltiplas versões do mesmo vídeo.

Da mesma forma o áudio tem suas propriedades, embora não necessite de tanta taxa de bits como o vídeo.

### **Propriedades de áudio**

- O áudio digital tem requisitos de largura de banda muito menores do que o vídeo.
- Uma técnica de compactação popular para a música estéreo com qualidade quase de CD é MPEG 1 layer 3, mais conhecida como MP3.
- Embora as taxas de bit de áudio sejam em geral muito menores do que as de vídeo, os usuários costumam ser muito mais sensíveis a pequenas falhas de áudio do que de vídeo.

Outro serviço que tem crescido exponencialmente é a distribuição de filmes pela rede pública IP como no caso do Netflix ou vídeo via Youtube, uma vez que são vídeos armazenados que tem as seguintes características:

### **Áudio e vídeo de fluxo contínuo armazenados**

- Muitas empresas de Internet oferecem hoje vídeo de fluxo contínuo, incluindo YouTube (Google), Netflix e Hulu.
- Por algumas estimativas, ele contribui com mais de 50% do tráfego descendente nas redes de acesso à Internet atualmente.
- Ele tem três características distintas importantes:

1. Fluxo contínuo.
2. Interatividade.
3. Reprodução contínua.

Além disso uma série de novos aplicativos tem crescido junto com a Internet como é o caso de soluções de vídeo conferencia e principalmente os jogos multimídia.

### **Voz e vídeo sobre IP interativos**

- A voz interativa em tempo real pela Internet é chamada de telefonia da Internet.
- A maioria dos sistemas interativos por voz e vídeo permite que os usuários criem conferências com três ou mais participantes.
- Voz e vídeo interativos são muito usados na Internet hoje, com as empresas Skype, QQ e Google Talk.
- Aplicações de multimídia interativas são tolerantes à perda.

No caso de vídeo de fluxo contínuo, os mesmos são pré-gravados e armazenados em servidores que são solicitados pelos clientes para assistirem conforme demanda, bem como o usuário interagir com a forma de reprodução do vídeo. Estes vídeos de fluxo continuo podem ser classificados em 3 categorias como se segue:

### **Vídeo de fluxo contínuo armazenado**

1. UDP de fluxo contínuo,
2. HTTP de fluxo contínuo e
3. HTTP de fluxo contínuo adaptativo.

- Uma característica comum de todas as três formas de vídeo de fluxo contínuo é o uso extenso de buffer de aplicação no lado do cliente para aliviar os efeitos de variar os atrasos de fim a fim e variar as quantidades de largura de banda disponível entre servidor e cliente.

Como a Internet foi construída para o tráfego de dados e não para voz e vídeo, ou seja, a internet tem uma característica é elástica, onde existem grandes variações de atraso, também conhecido com _**jitter**_, que não deve exceder aos 50ms,  o que não é bom para o tráfego em tempo real.

Para minimizar os efeitos do jitter, em muitos casos, os pacotes são bufferizados no destino para reprodução da mesma forma que foi gerado, ou seja, na mesma quantidade e no mesmo tempo, como forma de ajustar os efeitos da variação do atraso.

O gráfico da figura 1 apresenta  esta variação de atraso na reprodução do vídeo em um cliente final.

### **Vídeo de fluxo contínuo armazenado**

- Atraso de reprodução do cliente no vídeo de fluxo contínuo

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258859/14792.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258859/14792.jpg)

Atraso de reprodução

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

Já se sabe que para transmitir voz e vídeo em tempo real, o protocolo de transporte utilizado é o UDP uma vez que não existe controle de fluxo e muito menos garantia de entrega. Vale lembrar que a maioria das aplicações em tempo real, permite a perda de pacotes, algo em torno de 5%, para seus fluxos. Da mesma forma, é necessário efetuar extensões do UDP para controlar pontos como o jitter, como é o caso dos protocolos de extensão da camada de transporte RTP ( Real Time Protocol) e o respectivo controle utilizando o protocolo RTCP (Real Time Control Protocol).  O trafego que utiliza o UDP de fluxo continuo tem como característica:

### **UDP de fluxo contínuo**

- Com o UDP de fluxo contínuo, o servidor transmite vídeo a uma taxa que corresponde à taxa de consumo de vídeo do cliente.
- Normalmente usa um pequeno buffer no lado do cliente.
- O UDP de fluxo contínuo com taxa constante pode deixar de oferecer reprodução contínua.
- Ele exige um servidor de controle de mídia.
- Muitos firewalls são configurados para bloquear o tráfego UDP.

No caso de HTTP de fluxo contínuo o video é armazenado em um servidor HTTP ( como um servidor WEB) com uma determinada URL específica. Uma vez que usuário quer acessar o video, acontece o estabelecimento da conexão via TCP, envia-se o comando get-http e o servidor envia pela conexão TCP o fluxo de video. As características do HTTP fluxo contínuo são apresentadas a seguir

### **HTTP de fluxo contínuo**

- No HTTP de fluxo contínuo, o vídeo é apenas armazenado em um servidor HTTP como um arquivo comum com uma URL específica.
- O uso do HTTP sobre TCP também permite ao vídeo atravessar firewalls e NATs mais facilmente.
- Vídeos de fluxo contínuo sobre HTTP também deixam clara a necessidade de um servidor de controle de mídia, tal como um servidor RTSP (Real Time Streaming protocol)

O _**Real Time Streaming Protocol**_ (RTSP) é um protocolo de controle de rede projetado para uso em sistemas de entretenimento e comunicação para controlar streaming de mídia em servidores. O protocolo é usado para estabelecer e controlar sessões de mídia entre os pontos finais. Os clientes acessam os servidores de mídia VCR enviando comandos, como parar, seguir, etc, para facilitar a reprodução em tempo real de  arquivos de mídia a partir do servidor.

A transmissão de streaming de dados em si não é uma tarefa de RTSP. A maioria dos servidores RTSP usam o protocolo _**Real-time Protocol**_ (RTP) em conjunto com o protocolo de controle em tempo real (RTCP) para entrega fluxo de mídia. No entanto, alguns fornecedores implementam protocolos de transporte proprietários. O software do servidor RTSP de Real5 Networks, por exemplo, também usa um software proprietário para transporte dos dados, o (RDT).

### **Buffer de aplicação do cliente e buffers TCP**

A interação entre o cliente e o servidor, no lado do servidor, é enviado via um socket, quando da abertura da conexão TCP. No caso da figura 2, a parte mais escura é o que falta de informação a ser enviada ou, no caso do buffer, a informação já enviada.

No servidor, depois que passa pela porta do socket, os bytes são colocados no buffer de envio. Os segmentos são enviados via TCP, quando são armazenados no buffer de recepção para serem reproduzidos pela aplicação.

- A figura abaixo ilustra a interação entre o cliente e o servidor para HTTP de fluxo contínuo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258860/14793.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258860/14793.jpg)

Interação cliente-servidor

### **Análise do vídeo de fluxo contínuo**

No exemplo da figura 3, o servidor de vídeo  envia os fluxos via TCP para o buffer de recepção do cliente, a uma taxa x. Eventualmente o buffer do cliente pode encher e começar a perder pacotes. Obviamente que o controle do TCP faz com que a janela diminua, diminuindo assim o fluxo através da internet, impactando a qualidade da reprodução do vídeo, caso efetivamente o armazenamento se esgote (Q).

Q indica o número de bits que têm de ser armazenado no buffer antes que a aplicação cliente comece a exibir o vídeo (Q).

Observe que, quando a taxa disponível na rede for maior que a taxa de vídeo, após um atraso inicial do buffer, o usuário irá desfrutar de uma reprodução contínua até que o vídeo termine.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258866/14794.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258866/14794.jpg)

Analise de buffer de recepção

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Fluxo contínuo adaptativo e DASH**

DASH significa Fluxo contínuo Adaptativo Dinamicamente sobre HTTP, ou seja, o vídeo é codificado com um nível de qualidade diferente para compensar problemas de atraso na Internet, ou seja, existe uma adaptação da qualidade do vídeo em função da qualidade da Internet, ou seja, o usuário, em função da conexão também pode escolher como quer que o vídeo seja reproduzido. O DASH tem as seguintes características:

- Pelo DASH, o vídeo é codificado em muitas versões diferentes, cada qual com uma taxa de bits e um diferente nível de qualidade.
- O cliente seleciona diferentes trechos um de cada vez com mensagens de requisição HTTP GET.
- DASH permite aos clientes com diferentes taxas de acesso à Internet possam fluir em um vídeo por diferentes taxas codificadas.
- Com o DASH, cada versão do vídeo é armazenada em um servidor HTTP, cada um com uma diferente URL.

### **Redes de distribuição de conteúdo**

Uma CDN (Rede de Distribuição de Conteúdo), permite o controle e a gerencia dos vídeos armazenados para distribuição via rede pública IP ou a Internet e tem como característica principal:

- gerencia servidores em múltiplas localidades distribuídas geograficamente,
- armazena cópias dos vídeos em seus servidores, e
- tenta direcionar cada requisição do usuário para uma localidade CDN que proporcionará a melhor experiência para o usuário.

Por exemplo, o Netflix pode ter uma cópia de seus filmes distribuídos pelo mundo e, em função da sua localidade, o acesso ao banco de dados poderá ser quase que local, diminuindo assim, o fluxo pela Internet mundial e melhorando a qualidade de serviço nestas transmissões de multimídia

Esta distribuição pode ser uma CDN privada ou uma CDN de terceiros.

### **Operação da CDN**

A maioria das CDNs utiliza o DNS para interceptar e redirecionar requisições de modo que sempre existe uma procura, como acontece no DNS para baixar o fluxo de mídia. A figura 4 apresenta este fluxo da seguinte forma:

1 - O usuário visita a página da Internet NetCinema e solicita a página para um filme;

2, 3, 4 - O usuário busca a interação com o servidor de DNS, buscando a página do filme, que faz a busca do distribuidor CDN local via DNS;

5 - O servidor DNS retorna o local onde o vídeo está armazenado;

6 - Inicia a transferência de fluxo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258878/14795.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/8/258878/14795.jpg)

Fluxo CDN

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Estratégias de seleção de** _**cluster**_

Como a solicitação de vídeos podem acontecer aos milhares, é importante que a CDN tenha diversos servidores em cluster para atender a demanda de distribuição de vídeo, com as seguintes características:

- A estratégia de seleção de _cluster_ é um mecanismo para direcionamento dinâmico de clientes para um _cluster_ de servidor ou uma central de dados dentro da CDN.
- Uma estratégia simples é associar o cliente ao cluster que está geograficamente mais próximo.

Para determinar o melhor _**cluster**_ para um cliente baseado nas atuais condições de tráfego, as CDNs podem realizar medições em tempo real do atraso e problemas de baixo desempenho entre seus clusters e clientes.

### **Estratégias de seleção de** _**cluster**_

No caso do cluster, existe um mecanismo para direcionamento dinâmico de clientes para um cluster de servidor ou uma central de dados dentro da CDN, que é:

- Uma alternativa para medir as propriedades dos caminhos é usar as características do tráfego mais recente entre os clientes e os servidores da CDN.
- Uma abordagem muito diferente para combinar clientes com servidores CDN é utilizar o IP para qualquer membro do grupo.
- A ideia por trás do IP para qualquer membro do grupo é colocar os roteadores na rota da Internet dos pacotes do cliente para o cluster ?mais próximo?, como determinado pelo BGP.
- Usando o anycast IP para rotear clientes para o cluster da CDN mais próximo

A ideia do uso do anycast IP é a possibilidade que um membro de um grupo (RFC 1546), possa colocar os roteadores na rota da internet dos pacotes do cliente para o cluster mais próximo, determinado pelo BGP, conforme figura 5.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258934/14796.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258934/14796.jpg)

Anycast IP

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

A Internet tem uma função dita como melhor esforço, ou seja, não existe nenhuma garantia que o pacote será entregue e, muito menos com tempos controlados. Esta característica da internet tem:

- **Perda de pacotes** A perda pode ser eliminada enviando os pacotes por TCP, em vez de por UDP.
- **Atraso de fim a fim** é o acúmulo de atrasos de processamento, de transmissão e de formação de filas nos roteadores; atrasos de propagação nos enlaces e atrasos de processamento em sistemas finais.
- **Variação de atraso do pacote (jitter)** o tempo decorrido entre o momento em que um pacote é gerado na fonte e o momento em que é recebido no destinatário pode variar de pacote para pacote.

Existem técnicas que minimizam estes atrasos ou, de certa forma, eliminam a variação de atraso no receptor. Uma destas técnicas, conforme figura 6, é o atraso de reprodução fixa.

### **Atraso por reprodução fixa**

Perda de pacotes para diferentes atrasos por reprodução fixa

Os degraus mais a esquerda do gráfico representam o remetente e a forma como o sinal é gerado, supondo um pacote a cada 20ms. O tempo de propagação pela rede tem o tempo de r. Verifica-se que, em função do _**jitter,**_ os tempos do degrau na recepção são alterados. O sistema compensa a reprodução após um p?.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258936/14797.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258936/14797.jpg)

Atrasos por reprodução fixa

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Recuperação de perda de pacotes**

Para minimizar as perdas de pacotes, existem técnicas para recuperação, muito utilizados em sistemas de telecomunicações e satélite que é a FEC. O contexto para utilização da FEC, remota a estrutura da internet com as características abaixo:

- Um pacote será considerado perdido se nunca chegar ao receptor ou se chegar após o tempo de reprodução programado.
- Aplicações de VoIP frequentemente usam algum tipo de esquema de prevenção de perda.

### **O Forward Error Correction (FEC)**

- A ideia básica da FEC é adicionar informações redundantes ao fluxo de pacotes original.
- Dando carona à informação redundante de qualidade mais baixa

Ou seja, numa perda de pacotes, é possível recuperar a informação por meio do fluxo seguinte, conforme figura 7.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258937/14798.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258937/14798.jpg)

Técnica do FEC

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

Uma outra forma de recuperação de perda de pacotes é a Intercalação.

### **Intercalação**

O áudio é intercalado, onde o remetente rearranja a sequência de unidades de dados de áudio antes da transmissão

- É como uma alternativa à transmissão redundante, uma aplicação de VoIP pode enviar áudio intercalado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258945/14799.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258945/14799.jpg)

Recuperação de perda de pacotes

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Protocolo de tempo real (RTP)**

O protocolo que transporte a fluxo de midia é o RTP ou protocolo de tempo real que tem as seguintes características:

- O RTP pode ser usado para transportar formatos comuns como PCM, ACC e MP3 para som e MPEG e H.263 para vídeo.
- O protocolo também pode ser usado para transportar formatos proprietários de som e de vídeo.
- Hoje, o RTP é amplamente implementado em muitos produtos e protótipos de pesquisa.
- Também é complementar a outros importantes protocolos interativos de tempo real, entre eles SIP.
- O RTP comumente roda sobre UDP.
- Se uma aplicação incorporar o RTP, ela interagirá mais facilmente com as outras aplicações de rede multimídia.
- O RTP não fornece nenhum mecanismo que assegure a entrega de dados a tempo nem fornece garantias de qualidade de serviço.
- O RTP permite que seja atribuído a cada origem seu próprio fluxo independente de pacotes RTP.
- Pacotes RTP não são limitados às aplicações individuais.

Os quatro principais campos de cabeçalho do pacote RTP são:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258946/14800.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258946/14800.jpg)

Cabeçalho RTP

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

- Tipos de carga útil de áudio suportados pelo RTP:

![[Untitled 49.png|Untitled 49.png]]

Alguns tipos de carga útil de vídeo suportados pelo RTP:

![[Untitled 1 33.png|Untitled 1 33.png]]

### **SIP**

O Protocolo de Inicialização de Sessão (SIP) é um protocolo aberto e simples, para estabelecimento de sessão de voz,  que faz o seguinte:

- Provê mecanismos para estabelecer chamadas entre dois interlocutores por uma rede IP.
- Provê mecanismos que permitem a quem chama determinar o endereço IP atual de quem é chamado.
- Provê mecanismos para gerenciamento de chamadas.

Segue, na figura 12, um exemplo de estabelecimento de chamada SIP quando Alice conhece o endereço IP de Bob:

{C}Inicialmente a estação de origem envia um INVITE, contendo um protocolo auxiliar conhecido como SDP (protocolo de descrição da sessão) que tem como característica principal o envio da identificação da sessão de mídia, a porta utilizada pelo RTP e o tipo de codificador a ser utilizado;

O usuário Bob envia um 180 ringing alertando Alice que a chamada esta acontecendo

Bob, ao tirar o telefone do gancho, envia um 200 OK também com  a sua descrição da sessão (SDP)

Alice confirma com um ACK

Inicia-se o fluxo RTP

A final, a sessão é encerrada por meio de uma sinalização bye.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259060/14804.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259060/14804.jpg)

Sinalização SIP

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

Quando existe um servidor SIP no processo, que tem a função de controle da sessão e tradução de alias (ramal), existe uma outra sinalização que é o REGISTER, para registrar uma estação no servidor SIP.

É muito comum uma rede de servidores SIP que são interligados via SIP ou IAX, a sinalização entre servidores ou mesmo via Proxy. A figura 13 apresenta esta idéia onde ocorre a inicialização de sessão envolvendo proxies e entidades registradoras SIP:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259063/14804.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/0/259063/14804.jpg)

Registro SIP

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Suporte de rede para multimídia**

No mercado de rede de operadoras, a qualidade de serviço para aplicações multimídia são fornecidas por algumas arquiteturas, entre elas:

IntServ, que utiliza sinalização, em especial, o RSVP (protocolo de reserva de recursos) para criação de circuitos com QoS

DiffServ que utiliza criação de circuitos com QoS por meio de SLA (Nível de Acordo de Serviço) e cria diversos tipos de níveis de serviço como encaminhamento expresso EF e encaminhamento assegurado AF com serviços Ouro, Prata e Bronze. Para garantir estes serviços o campo ToS do protocolo IP, foi substituído pelo campo DSCP (DiffServ Code Point) que pode variar de 0 a 63.

O quadro da figura 14 apresenta uma tabela destas arquiteturas.

Três técnicas em nível de rede dão suporte a aplicações de multimídia

|Técnica|Granularidade|Garantia|Mecanismos|Complexidade|Implementação no momento|
|---|---|---|---|---|---|
|[[Obtendo o melhor do serviço de melhor esforço]]|todo o tráfego tratado igualmente|nenhuma ou flexível|suporte da camada de aplicação, CDNs, sobreposição, provisão de recurso em nível de rede|mínima|em toda parte|
|[[Serviço diferenciado]]|diferentes classes de tráfego tratadas de formas diferentes|nenhuma ou flexível|marcação, regulamentação e programação de pacotes|média|alguma|
|[[Garantias de qualidade de serviço (QoS) por conexão]]|cada fluxo de origem-destino tratado de forma diferente|flexível ou rígida, uma vez admitido o fluxo|marcação, regulamentação e programação de pacotes; admissão e sinalização de chamadas|leve|pouca|

  
  

### **Dimensionando redes de melhor esforço**

- A questão de como projetar uma topologia de rede para alcançar determinado nível de desempenho de fim a fim é um problema de projeto de redes que muitas vezes é chamado **de dimensionamento de redes**.
- Sabendo que a Internet de melhor esforço de hoje poderia dar suporte para o tráfego de multimídia em um nível de desempenho apropriado, se fosse dimensionada para fazer isso, a questão é por que a Internet de hoje não o faz.
- As respostas são principalmente econômicas e organizacionais.

### **Fornecendo múltiplas classes de serviço**

- Já estamos acostumados com diferentes classes de serviço em nossas vidas diárias.
- É importante observar que esse serviço diferencial é fornecido entre agregações de tráfego, ou seja, entre classes de tráfego, e não entre conexões individuais.
- Até mesmo há três décadas, a visão de fornecer diferentes níveis de serviço a diferentes níveis de tráfego estava evidente.
- No entanto, levou um longo período para que pudéssemos perceber essa visão.

### **Cenários motivadores**

As aplicações competem o acesso ao meio físico. É importante implementar técnicas de como esse acesso deve acontecer. É muito comum a marcação dos pacotes e distribuir estes pacotes em filas com prioridades diferenciadas, permitindo que fluxos que são sensíveis ao atraso tenham prioridades sobre o trafego não sensível como o HTTP que é uma aplicação com característica elástica.

Na figura 15, disputam o enlace de 1,5Mbps  um telefone H1 e uma estação H2. O Roteador R1, neste caso, privilegia o trafego de H1 em detrimento a H2, passando H1 na frente.

- Competindo aplicações de áudio e HTTP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258953/14806.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258953/14806.jpg)

Estudo do fluxo HTTP x áudio

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

- **Princípio 1**: A marcação de pacotes permite que um roteador faça a distinção de pacotes pertencentes a diferentes classes de tráfego.
- **Princípio 2**: É desejável fornecer algum grau de isolamento de tráfego entre as classes, para que uma classe não seja afetada adversamente por outra classe de comportamento inadequado.
- **Princípio 3**: Ao fornecer isolamento de classes ou fluxos, é desejável que se usem os recursos da maneira mais eficiente possível.

Regulação (e marcação) das classes de tráfego de áudio e HTTP. Uma vez que o tráfego é marcado, geralmente no campo ToS ou DSCP da arquitetura DiffServ, é possível regular a passagem dos pacotes pelo roteador, conforme figura 16.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258956/14807.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258956/14807.jpg)

Marcação de pacotes

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

Outra forma, é isolar o tráfego não sensível e sensível e regular este fluxo na saída do roteador, conforme figura 17, ou seja, um tipo de fluxo irá utilizar 1Mbps do enlace enquanto o outro utiliza 500Kbps.

- Isolamento lógico das classes de tráfego de áudio e HTTP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258962/14808.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258962/14808.jpg)

Isolamento de classes de tráfego

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Mecanismos de escalonamento**

O roteador trata as filas de pacotes no interior do Buffer, utilizando mecanismos de escalonamento. O mais trivial é o FIFO (primeiro que entra é o primeiro que sai), conforme figura 18.

- _Primeiro a entrar/primeiro a sair (FIFO)_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258971/14810.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258971/14810.jpg)

Escalonamento FIFO

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

Mas o mais utilizado para tráfego sensível e, em tempo real, são o enfileiramento prioritário, onde uma fila de maior prioridade será processada antes de uma fila de baixa prioridade, conforme figura 19.

- _Enfileiramento prioritário_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258973/14811.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258973/14811.jpg)

Enfileiramento Prioritário

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

No caso da voz, é muito comum um esquema de escalonamento baseado em WFQ. O WFQ nasceu da técnica de Round Robin onde uma fila é tratada de cada vez de uma forma cíclica.

O WFQ acaba sendo um Round Robin ponderado para cada fila, conforme figura 20.

- _Varredura cíclica e WQF (enfileiramento justo ponderado)_

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258986/14812.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258986/14812.jpg)

Enfileiramento WFQ

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

Como o tráfego na Internet é em Burst (Rajada), também existem técnicas para suavização do tráfego.

Uma destas técnicas é o Leak Bucket ou balde furado. Esta técnica permite um fluxo constante na saída do roteador, represando o _**burst**_ e suavizando e envio de  pacotes para o interior da Internet, conforme figura 21.

- Balde furado + enfileiramento justo ponderado = máximo atraso provável em uma fila.
- O balde furado com ficha ou permissões controla a emissão de pacotes para rede em função da quantidade de fichas existentes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258990/14813.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258990/14813.jpg)

Balde furado e token

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Diffserv**

É uma das arquiteturas mais utilizadas para implementar QoS que permite:

- Diffserv oferece diferenciação de serviço.
- A arquitetura Diffserv consiste em dois conjuntos de elementos funcionais:

_**Funções de borda**_: classificação de pacotes e condicionamento de tráfego.

_**Função central**_: envio.

Na arquitetura DiffServ, além dos serviços já mencionados, EF e AF, que permitem a classificação, ainda se faz a marcação, tratamento dos pacotes e descarte conforme o caso, para manter o fluxo sensível dentro dos padrões, conforme figura 22 e 23.

Exemplo simples de rede Diffserv

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260853/14814.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/0/8/260853/14814.jpg)

Arquitetura DiffServ

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258994/14815.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258994/14815.jpg)

Fluxo da arquitetura DiffServ

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

### **Garantias de QoS por conexão: reserva de recurso e admissão de chamada**

- Duas aplicações de áudio concorrentes sobrecarregando o enlace de R1 a R2

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258995/14816.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258995/14816.jpg)

Reserva de recurso

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013

- Sabendo que essas duas aplicações não podem ser atendidas simultaneamente, o que a rede deve fazer?
- Um dos fluxos de aplicação deve ser, enquanto o outro deve prosseguir, usando o 1 Mbit/s inteiro necessário pela aplicação.
- O processo de um fluxo declarar seu requisito de QoS e a rede aceitar o fluxo (na QoS solicitada) ou bloqueá-lo é denominado processo de admissão de chamada.
- Se recursos suficientes nem sempre estiverem disponíveis e a QoS tiver de ser garantida, é necessário um processo de admissão de chamada no qual os fluxos declaram seus requisitos de QoS e, então, são admitidos à rede ou bloqueados da rede.
- Nosso exemplo motivador na figura anteriormente apresentada enfatiza a necessidade de diversos novos mecanismos e protocolos de rede, se uma chamada tiver de garantir determinada qualidade de serviço uma vez iniciada:
- Reserva de recurso.
- Admissão de chamada.

Sinalização do estabelecimento de chamada conforme figura 25.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258997/14817.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258997/14817.jpg)

Sinalização QoS

Fonte: KUROSE, James F. Redes de Computadores e a Internet. 2013