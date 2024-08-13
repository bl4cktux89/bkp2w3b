### **Introdução ao TCP/IP**

O início para o que chamamos de redes de computadores remonta a década de 60 do século passado, durante o período conhecido como “Guerra Fria” entre os EUA e URSS. O nascimento das redes de computadores esteve, portanto, associado com o desenvolvimento tecnológico militar dos EUA. Grande parte dos protocolos e tecnologias de comutações utilizados atualmente teve origem na ARPA (Advanced Research Projects Agency, Agência de Pesquisas em Projetos Avançados que buscava interligar as suas bases militares e departamentos de pesquisas por meio de uma rede chamada de ARPANET. A ARPANET era composta ainda por um grupo de universidades e algumas instituições privadas, grupo este conhecido como "ARPANET Network Working Group".

Em 1969, a rede ARPANET entrou em operação, consistindo inicialmente de quatro nós e utilizando comutação de pacotes para efetuar a comunicação. Tempos depois centenas de universidades e repartições públicas estavam interligada, por meio de linhas telefônicas dedicadas. Com o surgimento das redes de rádio e via satélite, começaram a surgir problemas com os protocolos existentes, o que levou ao desenvolvimento de uma nova arquitetura de referência. Tempos depois essa arquitetura ficou conhecida como **modelo de referência TCP/IP**, em função dos dois principais protocolos, TCP (Transmission Control Protocol, do Inglês: Protocolo de Controle de Transmissão) e IP (Internet Protocol, do Inglês: Protocolo de Internet). Esse modelo foi definido em 1974 por um estudo feito por Vinton Cert e Robert Kahn, que propuseram um grupo de protocolos centrais para satisfazer as seguintes necessidades:

- Permitir o roteamento entre redes diferentes (chamadas subnets ou subredes);
- Independência da tecnologia de redes utilizada para poder conectar as subredes;
- Independência do hardware;
- Possibilidade de recobrar-se de falhas.

Entretanto, inicialmente esses protocolos foram chamados de NCP (Network Control Program, Programa de controle de Rede), mas, em 1978, passaram a ser chamados de TCP/IP. O modelo TCP/IP é mostrado na Figura 1.

![[Untitled 30.png|Untitled 30.png]]

Em 1980, o DARPA começou a implementar o TCP/IP na ARPANET, dando origem à Internet. Em 1983, o DARPA finalizou a conversão de todos seus computadores e exigiu a implementação do TCP/IP em todos os computadores que quisessem se conectar à ARPANET. Além disso, o DARPA também financiou a implementação do TCP/IP como parte integral do sistema operacional Unix, exigindo que este fosse distribuído de forma gratuita. Dessa forma o Unix e, consequentemente, o TCP/IP, se difundiram, cobrindo múltiplas plataformas.

Em termos cronológicos outros marcos importantes para o desenvolvimento do protocolo TCP/IP e das redes de computadores são descritos abaixo:

- **1961** – O Cientista Leonar Kleinrock, através da teoria das filas mostra a efetividade da comutação por pacote.
- **1964** – Paul Baran, engenheiro demonstra pela primeira vez o funcionamento de uma rede comutado por pacote.
- **1967** – A ARPANET é concebida pela ARPA.
- **1969** – O primeiro nó da ARPANET entra em operação.
- **1972** – A ARPANET é demonstrada publicamente. Neste mesmo ano é desenvolvido o primeiro programa de e-mail.
- **1973** – A rede ALOHAnet entra em operação.
- **1973** – Robert _Metcalfe propõe o protocolo Ethernet para redes locais. No mesmo ano Cerf e Kahn propõem o uso do TCP (Protocolo de Controle de Transmissão). Junto com o IP (Protocolo de Internet) proposto em 1978, são os padrões para interconexão em rede._
- **1983** – A ISO (International Organization for Standardization, Organização Internacional para Padronização) formaliza o modelo OSI (Open System Interconnection, modelo para interconexão de sistemas abertos).
- **1988** – Os primórdios da Internet surgem no Brasil, conectando universidades brasileiras à americanas.
- **1990** – É criada a WWW (World Wide Web). A rede mundial disseminada ao redor do mundo.

![[Untitled 1 20.png|Untitled 1 20.png]]

### Modelo OSI

Antes de tratarmos do modelo TCP/IP propriamente dito, é importante, por questões históricas conhecermos modelo OSI. O modelo OSI foi criado em 1970 e formalizado em 1983. É um modelo de referência desenvolvido pela ISO (International Organization for Standardization - Organização Internacional de Padronização). Àquela época, não existia uma padronização quanto aos hardwares e protocolos utilizados e cada fabricante utilizava os seus próprios padrões, dificultando, e, até mesmo, impossibilitando a comunicação entre diferentes fabricantes. Nesse sentido, o modelo OSI surgiu tendo como principais objetivos:

1. Garantir a comunicação fim-a-fim.
2. Permitir a comunicação entre dispositivos de diferentes fabricantes.
3. Definir regras para a construção das redes de computadores independe da tecnologia e do alcance geográfico.
4. Facilitar o aprendizado da arquitetura das redes.
5. Permite que novas tecnologias sejam facilmente implantadas e atualizadas.

O modelo referência OSI é dividido em 7 camadas como ilustrado na figura abaixo. As camadas são independentes. Entretanto, cada camada (N), fornece serviço para a camada N+1, utilizando funções executadas na mesma camada, além de serviços executados por camadas inferiores, com exceção da camada de Aplicação. Na mesma figura é mostrada as PDUs (Unidade de protocolo de dados) de cada camada. As PDUs correspondem ao processo de encapsulamento que ocorre em cada camada, da camada de Aplicação até a física. Nesse processo, a medida em que os dados descem o modelo OSI, eles incorporam cabeçalhos específicos de cada camada, contendo, por exemplo, o endereço IP de origem e destino para formar o que é chamado de pacote (PDU da camada de rede).

![[Untitled 2 18.png|Untitled 2 18.png]]

**Camada 1 - Física**

A camada física do modelo de referência OSI define as especificações elétricas, mecânicas, definindo como será dada a representação dos bits no meio de transmissão por meio de sinais elétricos ou ópticos, além de definir, dentre outros fatores, o que segue:

- A quantidade de pinos de um conector.
- A voltagem necessária para representar o bit 0 ou 1.
- A duração em microssegundos de um bit.
- A distância máxima de transmissão.

Normalmente, dispositivos que estão nessa não tomam decisão, ou seja, são passivos, tais como o HUB e meios de transmissão. O mesmo pode ser relacionado com a camada física do TCP/IP.

**Camada 2 - Enlace de Dados**

A camada de Enlace de Dados é responsável por controlar o acesso ao meio físico, detectando e opcionalmente corrigir de erros. A camada de Enlace de Dados é dividida em duas subcamadas:

- **Subnível inferior – MAC (Medium Access Control, Controle de Acesso ao Meio).** Este subnível possui alguns protocolos importantes, como o IEEE 802.3 (Ethernet), IEEE 802.4 (Token Bus) e IEEE 802.5 (Token Ring). Por meio desses protocolos é possível controlar o acesso ao meio.
- **Subnível superior - (LLC - Logical Link Control, Controle Lógico do Enlace)** O protocolo LLC pode ser usado sobre o subnível anterior, permitindo que os protocolos utilizados, principalmente em redes, tais como, Ethernet, Token Bus e Token Ring sejam ocultados e dessa forma permitindo a operação entre eles. Normalmente, utiliza-se o subnível LLC quando é necessário controle de fluxo ou comunicação confiável.

Dispositivos como switch, bridge e placas de rede estão nessa camada e tomam decisão baseados no endereço físico (MAC). O mesmo pode ser relacionado com a camada enlace de dados do modelo TCP/IP – Híbrido, que veremos a seguir.

**Camada 3 - Rede**

A camada de Rede do modelo OSI oferece os meios funcionais e procedimentos para que os pacotes com de uma determinada origem cheguem a um destino. A determinação do melhor caminho pode ser dada por protocolos de roteamento dinâmicos e rotas estáticas. A tomada de decisão é baseada principalmente por meio do endereço IP a partir da consulta de tabelas de rotas.

Outras especificações dessa camada estão associadas com definição das regras de endereçamento IPv4 e IPv6. Além dos protocolos IP (IPv4 e IPv6), outros protocolos pertencem a essa camada, dentre eles: ARP, RARP e NAT.

Dispositivos que estão nessa camada tomam decisão baseados no endereço IP, como é o caso do roteador. O mesmo pode ser relacionado com a camada Internet do modelo TCP/IP.

**Camada de Transporte**

A camada de transporte é uma das principais do modelo de referência OSI, e tem por finalidade garantir o transporte confiável e eficiente entre os dispositivos fins, permitindo que os dados cheguem íntegros e sem erros.

A camada de Transporte pode ser dividida em duas classes de protocolos, o UDP (User Datagram Protocol, Protocolo de Datagrama de usuário) e TCP (Transmission Control Protocol, Protocolo de controle de Transmissão). Em outras palavras, a camada de Transporte é dividida em protocolos orientados a conexão (TCP) e não confiáveis e não  orientados a conexão (UDP). Protocolos do tipo UDP fazem apenas a multiplexação de dados, enquanto que protocolos do tipo TCP efetuam outros mecanismos para abrir, manter e encerrar as sessões.

Abaixo são detalhadas as principais funções da camada de transporte:

- **Segmentação dos dados:** A camada de Transporte recebe os dados da camada de sessão e segmenta-os em pequenas partes (máximo 65525 bytes) para forma o segmento. Isso permite que a largura de banda seja otimizada e compartilhada entre diferentes aplicações.
- **Multiplexação da conversação:** Permite que diversas conversões (aplicações) sejam possíveis simultaneamente, otimizando a largura de banda disponível, como mostrado na figura abaixo.

![[Untitled 3 12.png|Untitled 3 12.png]]

- **Controle de Fluxo:** Por meio das janelas móveis, a camada de Transporte especifica a quantidade de segmentos que o dispositivo fim é capaz de receber. Isso permite que diversos clientes se conectem a um determinado serviço, com o objetivo de garantir que todos os clientes tenham a possibilidade de receber dados. Isso que dizer que, à medida que o número de clientes solicitantes desse serviço aumenta, a janela para cada cliente diminui, o contrário também é verdadeiro.
- **Controle de sequência e controle de erros:** Cada segmento é numerado para que seja reordenado no dispositivo fim, além cada segmento possuí um cabeçalho (header) contento uma soma verificadora (checksum). Essa implementação tem como objetivo garantir que os segmentos cheguem ordenados e livres de erros, conforme mostrado na figura acima.

**Camada de Sessão**

Esta camada tem por finalidade estabelecer o sincronismo entre aplicações, iniciando, mantendo e encerrando sessões. Ela controla, por exemplo, de quem é a vez de falar, “grava” em qual ponto a conversão terminou com o objetivo de reiniciá-la. Exemplos de protocolos dessa camada são: SQL, ASP e RPC. Essa camada é inexistente no modelo TCP/IP de 4 camadas e de 5 (modelo híbrido).

**Camada de Apresentação**

A camada de Apresentação do modelo OSI não existe no modelo TCP/IP. Tal camada foi projetada para executar basicamente três funções:

- **Apresentação dos dados**: Converte o formato de dados vindos da camada de Aplicação em um formato que seja compatível com um dispositivo fim. Um exemplo comum é a conversão do padrão de página quando um transmissor utiliza um padrão diferente do ASCII, como para EBCDIC.
- **Compactação:** Os dados podem também passar pela compressão dos dados com o objetivo de aproveitar de forma eficiente a largura de banda disponível.
- **Criptografia:** Tem o objetivo de aumentar a segurança, fazendo com que o dispositivo transmissor realize a criptografia dos dados, que por sua vez é decodificado na camada 6 do dispositivo receptor.

**Camada de Aplicação**

A camada de Aplicação possui a mesma funcionalidade da camada Aplicação do modelo TCP/IP, provendo a interface de interação entre o usuário e máquina por meio de programas (aplicações). Algumas das funções que podem ser necessárias são:

- Redirecionamento de dispositivo e o compartilhamento de recursos
- Acesso remoto a arquivos
- Acesso de impressora remota
- Comunicação entre processos
- Gerenciamento de rede
- Serviços de diretório
- Mensagens eletrônicas (como email)
- Terminais de rede virtuais

Protocolos dessa camada: HTTP, SMTP, FTP, SSH, Telnet, SIP, RDP, IRC, SNMP, NNTP, POP3, IMAP, DNS.

### Modelo TCP/IP

O TCP/IP foi desenvolvido seguindo uma arquitetura em pilha, no qual cada camada interage apenas com a camada inferior e superior, sendo responsável por um grupo de tarefas a serem realizadas. O TCP/IP é formado por um conjunto de protocolos hierárquico, compostos por módulos interativos, cada um dos quais provendo funcionalidades específicas, não necessariamente independentes, conforme ilustrado na figura abaixo. O termo hierárquico significa que um protocolo de camada superior necessita de um ou mais protocolos das camadas inferiores.

![[Untitled 4 12.png|Untitled 4 12.png]]

A seguir serão discutidas em resumidamente funcionalidades das 5 camadas TCP/IP com base no modelo híbrido.

**Camada Física e de Enlace:** O modelo TCP/IP não define nenhum protocolo específico para as camadas **Física** e **Enlace**, suportando todos os padrões proprietários. Entretanto, a camada **Física** corresponde as características elétricas e mecânicas associadas aos meios de transmissão (cabo coaxial, fibras óptica, par-trançado ou wireless), enquanto que a camada de **Enlace** está associada com os métodos de acesso ao meio LAN (Redes Locais) e WAN (Redes de Longa Distância).

**Camada de Internet (ou Rede):** O TCP/IP suporta o Protocolo de Internet (IP), que por sua vez pode utilizar outros protocolos, tais como ARP, RARP e ICMP. O IP trata-se de um protocolo não confiável, que não possui nenhuma verificação de erro, mas, por outro lado, faz o melhor possível para entregar a mensagem ao destinatário.

**Transporte:** Fornece gerenciamento de sessão de comunicação entre computadores host. Define o nível de serviço e o status da conexão usada durante o transporte de dados; Garante a integridade e a confiabilidade dos transmitidos.

**Aplicação:** Define os protocolos de aplicativos TCP/IP e como os programas host estabelecem uma interface entre o usuário e a aplicação, assim como uma interface de comunicação com os serviços de camada de transporte, conforme já mostrado na figura acima.

### Comparação entre o Modelo OSI e TCP/IP

- **Semelhanças:** Ambas as camadas de Transporte dos dois modelos desempenham a mesma função. O mesmo acontece com a camada de Internet do TCP/IP e a camada de Rede do modelo OSI.
- **Diferenças:** A camada de Enlace de Dados do modelo TCP/IP reúne as funcionalidades das Camadas de Enlace de Dados e Física. O mesmo acontece com a camada de Aplicação do Modelo TCP/IP, que reuni as funcionalidades das camadas de Aplicação, Apresentação e Sessão do Modelo OSI.
- **Deficiência do OSI:** Padrão extremamente complexo de se implementar devido ao seu nível de detalhamento e baixa eficiência. Além disso, algumas funcionalidades, tais como, correção de erro e controle de fluxo são repetidas em diferentes camadas.
- **Deficiência do TCP/IP:** Não detalha com clareza os conceitos de serviço, interface e protocolo, não diferenciando adequadamente as especificações de implementação. Além disso, o TCP/IP é pouco abrangente, não conseguindo descrever outras pilhas de protocolos que não o TCP/IP como, por exemplo, não é possível descrever o Bluetooth através do TCP/IP. E por fim, a camada de Acesso a rede não é na verdade uma camada, mas é tratada como uma interface, tendo em vista o contexto de protocolos hierarquizados e também não diferencia a camada Física de Enlace.

Por estes motivos, Tanembaum,  propôs o modelo hibrido de 5 camadas, sugerido por que vem a retirar os excessos do modelo OSI e melhorar o modelo TCP/IP, principalmente com relação a camada de Acesso à Rede, dividindo-a nas camadas Física e Enlace de Dados (ou Acesso a Rede), conforme Figura abaixo.

![[Untitled 5 11.png|Untitled 5 11.png]]