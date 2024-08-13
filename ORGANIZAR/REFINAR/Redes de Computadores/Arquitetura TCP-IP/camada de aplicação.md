### Introdução

As aplicações de redes são a razão de ser de uma rede de computadores (Kurose, J. F. 2013). Se não existissem as aplicações não haveria a necessidade de se criar protocolos de redes para suporta-los, tais como, o Ethernet e o TCP/IP. Desde os primórdios da internet diversas aplicações foram desenvolvidas com objetivo de facilitar a vida do ser humano como, até mesmo, oferecer diversão. Atualmente, fica difícil imaginar as nossas vidas sem a utilização de algum tipo de aplicação, sejam elas voltadas a diversão ou ao mundo corporativo.

A partir dos anos 2000, a Internet tem passado por uma proliferação vertiginosa de aplicações que oferecem vídeo sob demanda, como o NetFlix; aplicativos de mensagens instantâneas, como o WhatsApp; redes sociais, como Facebook e Linkedin; voz sobre IP oferecidos, inclusive, pelo WhatsApp; além diversas aplicações de jogos on-line. Todas essas aplicações só foram possíveis com a explosão da World Wide Web (WWW) na década de 1990. Entretanto, nos primórdios da Internet, por volta das décadas de 1970 e 1980, as principais aplicações envolviam a utilização de aplicações de edição de texto, correio eletrônico, acesso a computadores remotos e transferência de arquivos (Kurose, J. F. 2013).

Neste tópico estudaremos os aspectos conceituais e de implementação de aplicações de rede, incluindo as aplicações cliente-servidor, a interface com a camada de transporte e API _**socket**_.

### A Camada de aplicação

O Modelo TCP/IP, diferentemente do Modelo de Referência OSI, não tem as camadas de sessão e apresentação. Os criadores da Internet decidiram que os protocolos de mais alto nível, como HTTP, DNS e FTP, deveriam incluir as funcionalidades dessas camadas. Na prática, as camadas de sessão e apresentação seriam pouco utilizadas na maioria das aplicações.

Por esse motivo, logo acima da camada de Transporte, encontramos a camada de aplicação. Na tabela abaixo mostramos os principais protocolos da camada de aplicação do modelo TCP/IP (Tanenbaum, Andrew S, 2011).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/7/240772/9234.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/7/240772/9234.png)

Portas TCP e UDP

### Princípios de Aplicações de Rede

Imagine que você tenha uma grande ideia para uma nova aplicação que irá revolucionar como as irão se comunicar na Internet. Você poderia se perguntar: Eu tenho que me preocupar com todas as camadas do modelo TCP/IP como, por exemplo, a camada de Acesso a Rede e Internet? Uhmm!! Felizmente, Não!

O seu foco deve ser voltado, certamente, em garantir a interoperabilidade em relação aos sistemas heterogêneos, ou seja, garantir que a aplicação rode nos computadores pessoais, smartphones e tablets, assim como se o navegador, seja ele, Internet Explore, Chrome ou Firefox irá suportar a sua aplicação.

Portanto, você precisa se preocupara com a programação ou onde o sistema será criado, por exemplo, Java, C ou Python. Se preocupando apenas em nos sistemas finais e não se preocupara em escrever programas que rodem no núcleo da rede, por exemplo, se preocupar em escrever um programa voltado para o roteador ou para o switch (Kurose, J. F. 2013). Mesmos que você quisesse, não seria possível desenvolver programas para esses dispositivos, já que eles pertencem as camadas inferiores, internet e acesso a rede, respectivamente. Novamente, a sua preocupação deve estar voltada para os sistemas finais, pensando em termos de camada de aplicação para camada de aplicação, conforme mostrado na Figura 1 abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/0/264095/13396.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/4/0/264095/13396.png)

Conexão da camada de Aplicação

### Arquitetura de Aplicações de rede

Voltando ao desenvolvimento do seu aplicativo que irá revolucionar a comunicação entre pessoas, você, agora, terá que escolher um tipo arquitetura de aplicação. Lembrando que, você não precisa se preocupar com arquitetura da rede, pois ela é fixa e sua aplicação não modificará as camadas inferiores. A arquitetura da aplicação envolve a organização nos vários sistemas finais, tablets, smartphones e notebooks. As arquiteturas modernas podem ser classificadas em cliente-servidor e P2P (Kurose, J. F. 2013).

- **Cliente-servidor:** nessa arquitetura existe sempre um hospedeiro (servidor) de “portas abertas” a espera de uma conexão de outro hospedeiro, denominado cliente. Todas as vezes que você solicita uma página na web, por exemplo, [**www.uninove.br**](http://www.uninove.br/), ele responderá a sua requisição como o objeto solicitado pelo seu navegador (cliente). Nessa arquitetura os clientes não conversam entre si, ou seja, o seu navegador não conversa diretamente com navegador de outro cliente. Outra característica é que o servidor sempre tem o endereço IP fixo e bem conhecido para que sempre que necessário, o cliente saiba encontra-lo facilmente. Aplicações do tipo FTP, Telnet, e-mail e DNS são exemplos de aplicações dessa categoria. A figura 2 (a) ilustra essa arquitetura.
- **P2P:** na arquitetura P2P a confiança dos servidores dedicados é mínima (ou nenhuma). Em vez disso, os hosts clientes podem se comunicar diretamente, estabelecendo uma relação em pares. Os pares se comunicam diretamente sem passar pelo servidor, por isso a chamamos arquitetura par a par (Peer-to-peer – P2P). atualmente, existem diversas aplicações que utilizam essa arquitetura, por exemplo, a telefonia por Internet por meio do Skype e o compartilhamento de arquivo utilizando o BitTorrent. Algumas dessas aplicações podem ser consideradas híbridas, reunindo as funcionalidades do P2P e do cliente-servidor. Neste caso, o servidor pode, por exemplo, rastrear os endereços IPs das mensagens dos clientes, mas tais mensagens são transferidas diretamente entre os clientes. Na figura 2(b) mostramos a comunicação entre os pares da arquitetura P2P.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/8/9/1778939/39780.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/8/9/1778939/39780.png)

Fonte: Kurose, J. F. 2013

### Comunicação entre Processos

Antes de construir a sua aplicação de rede, você precisa conhecer também como os programas que rodam os sistemas finais se comunicam entre si. Na verdade, **são os processos que se comunicam e não os programas.** Esse **processo** pode ser imaginado como um programa que está rodando dentro de um sistema final.

Os processos entre dois sistemas finais diferentes, um cliente e um servidor, por exemplo, se comunicam trocando mensagens por meio da rede de computadores. Um cliente cria um processo e o envia pela rede, enquanto que um processo no servidor a recebe e responde, devolvendo outra mensagem. A Figura 1 mostra que os processos se comunicam utilizando a camada de aplicação da pilha TCP/IP.

Em aplicações com arquitetura P2P podemos utilizar o mesmo conceito acima. Apesar de não definimos exatamente como um cliente e um servidor, nas aplicações P2P, aquele par que inicia a sessão é considerado o cliente, enquanto que aquele que espera ser contatado para iniciar a sessão é o servidor (Kurose, J. F. 2013).

### Interface entre o processo e a rede de computadores

Como dito anteriormente, a maioria das aplicações são realizadas a partir de pares de processos, da parte do cliente e da parte do servidor. Cada um desses processos pode agora enviar mensagens de um para o outro passando pela rede de computadores. Um processo envia uma mensagem pela rede e recebe uma mensagem dela através de uma interface de software denominada _**socket**_ (Kurose, J. F. 2013)_**.**_

Um socket representa uma conexão entre dois nós, de tal modo que a conexão funciona como um canal virtual de transferência de dados em fluxo (stream). Sendo que cada socket possui um canal de entrada e outro de saída, sendo que o que é enviado pelo canal de saída de um nó é recebido pelo canal de entrada do outro nó e vice-versa. Quando o canal é estabelecido, o socket utiliza os endereços IPs para identificar o computador de origem e também o número de porta para diferenciar a requisição (Mendes, D. R. 2010).

Cada nó de uma rede recebe um endereço IP único. E em cada nó, existem 65.536 (216) números de portas, sendo as 1023 primeiras portas destinadas aos serviços-padrão (bem conhecidas, por exemplo, HTTP, TELNET, FTP etc. As demais são mostradas abaixo:

- 1 a 255 – portas públicas
- 256 a 1023 – portas designadas a empresas
- 1024 a 49151 – portas registradas (utilizadas pelos clientes para iniciar uma sessão);
- 49152 a 65535 – Portas dinâmicas ou privadas.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267735/10834.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/7/7/267735/10834.jpg)

Processo de aplicação com socket

Como ilustrado na figura acima, um socket é uma interface entre a camada de aplicação e de transporte dentro de um nó. Essa interface também é denominada Interface de Programação de Aplicação – API (application programming interface) entre a aplicação e a rede. O programador controla tudo o que existe no lado da aplicação do socket, mas tem pouco ou nenhum controle sobre o lado da camada de transporte. O programador pode ter o controle sobre a escolha do protocolo de transporte (TCP, UDP ou SCTP) e dependendo do protocolo, controlar o tamanho do buffer ou do segmento.

A figura abaixo mostra as principais atividades relacionadas ao socket por um cliente e um servidor que se comunicam por meio de UDP.

Vamos fazer uma analogia para entendermos esse processo. Um processo é semelhante a uma casa, e a porta da casa é o seu socket. Quando um processo de origem deseja enviar uma mensagem para outro processo de destino, ele empurra a mensagem pela porta (socket), que chega até a infraestrutura da cidade (rede) até a porta do destinatário. Quando a mensagem chega ao destinatário, a mensagem passa pela porta do destinatário, que então executa alguma ação sobre a mensagem. A figura abaixo ilustra a comunicação entre os dois sockets.

[![](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/5/1779506/39781.png)](https://img.uninove.br/static/0/0/0/0/0/0/1/7/7/9/5/1779506/39781.png)