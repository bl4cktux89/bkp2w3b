### **História**

O modelo OSI foi criado em 1970 e formalizado em 1983. É um modelo de referência desenvolvido pela ISO (International Organization for Standardization - Organização Internacional de Padronização). Àquela época, não existia uma padronização quanto aos hardwares e protocolos utilizados e cada fabricante utilizava os seus próprios padrões, dificultando, e, até mesmo, impossibilitando a comunicação entre diferentes fabricantes. Nesse sentido, o modelo OSI surgiu tendo como principais objetivos:

1. Garantir a comunicação fim-a-fim.
2. Permitir a comunicação entre dispositivos de diferentes fabricantes.
3. Definir regras para a construção das redes de computadores independe da tecnologia e do alcance geográfico.
4. Facilitar o aprendizado da arquitetura das redes.
5. Permite que novas tecnologias sejam facilmente implantadas e atualizadas.

### **Estrutura**

A modelo referência OSI é dividido em 7 camadas como ilustrado na figura abaixo. As camadas são independentes. Entretanto, cada camada (N), fornece serviço para a camada N+1, utilizando funções executadas na mesma camada, além de serviços executadas por camadas inferiores, com exceção da camada de Aplicação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/4/0/234036/4626.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/3/4/0/234036/4626.png)

Modelo OSI

**Unidade de Dados de Protocolo (PDU)**

A PDU (Protocol Data Unit, Unidade de Dados de Protocolo) é um processo de encapsulamento que ocorre a partir da camada de aplicação até a camada Física. Esses encapsulamentos contêm informações específicas de cada camada, por exemplo, o endereço IP na camada de Rede, para formar o Pacote IP. A PDU de cada camada é mostrada na figura acima.

### Camada 1 - Física

A camada física do modelo de referência OSI define as especificações elétricas, mecânicas, definindo como será dada a representação dos bits no meio de transmissão por meio de sinais elétricos ou ópticos, além de definir, dentre outros fatores, o que segue:

- A quantidade de pinos de um conector.
- A voltagem necessária para representar o bit 0 ou 1.
- A duração em microssegundos de um bit.
- A distância máxima de transmissão.

Normalmente, dispositivos que estão nessa não tomam decisão, ou seja, são passivos, tais como o HUB e meios de transmissão.

### Camada 2 - Enlace de Dados 

A camada de Enlace de Dados é responsável por controlar o acesso ao meio físico, detectando e opcionalmente corrigir de erros. A camada de Enlace de Dados é dividida em duas subcamadas:

- **Subnível inferior – MAC (Medium Access Control, Controle de Acesso ao Meio).** Este subnível possui alguns protocolos importantes, como o IEEE 802.3 (Ethernet), IEEE 802.4 (Token Bus) e IEEE 802.5 (Token Ring). Por meio desses protocolos é possível controlar o acesso ao meio.
- **Subnível superior - (LLC - Logical Link Control, Controle Lógico do Enlace)** O protocolo LLC pode ser usado sobre o subnível anterior, permitindo que os protocolos utilizados, principalmente em redes, tais como, Ethernet, Token Bus e Token Ring sejam ocultados e dessa forma permitindo a operação entre eles. Normalmente, utiliza-se o subnível LLC quando é necessário controle de fluxo ou comunicação confiável.

Também podemos encontrar nessa camada outros protocolos e padrões definidos por diferentes órgãos de telecomunicações, como mostrado na tabela que segue. Geralmente, tais protocolos são utilizados em redes WAN.

|Organização|Protocolo|
|---|---|
|[[ISO]]|HDLC (High Level Data Link Control)|
|[[ITU]]|Q.922 (Frame Relay Standard),  <br>  <br>Q.921 (ISDN Data Link Standard),HDLC (High Level Data Link Control)|
|[[ANSI]]|3T9.5, ADCCP (Advanced Data Comunications Control Protocol)|

  
  

Dispositivos como switch, bridge e placas de rede estão nessa camada e tomam decisão baseados no endereço físico (MAC).

### Camada 3 - Rede

A camada de Rede do modelo OSI oferece os meios funcionais e procedimentos para que os pacotes com de uma determinada origem cheguem a um destino (figura abaixo). A determinação do melhor caminho pode ser dada por protocolos de roteamento dinâmicos e rotas estáticas. A tomada de decisão é baseada principalmente por meio do endereço IP a partir da consulta de tabelas de rotas.

Outras especificações dessa camada estão associadas com definição das regras de endereçamento IPv4 e IPv6. Além dos protocolos IP (IPv4 e IPv6), outros protocolos pertencem a essa camada, dentre eles: ARP, RARP e NAT.

Resumindo, as principais funções do nível de rede são as seguintes:

- Roteamento dos pacotes entre origem e destino;
- Definição dos campos de endereços IPv4 e IPv6;
- Controle de congestionamento;
- Quantidade de dados enviados e recebidos para fins de tarifação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/6/240641/9223.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/6/240641/9223.jpg)

Diferentes caminhos até o destino.

Dispositivos da camada de rede tomam decisão a partir do endereço lógico, como por exemplo, os roteadores.

### Camada 4 - Transporte

A camada de transporte é uma das principais do modelo de referência OSI, e tem por finalidade garantir o transporte confiável e eficiente entre os dispositivos fins, permitindo que os dados cheguem íntegros e sem erros.

A camada de Transporte pode ser dividida em duas classes de protocolos, o UDP (User Datagram Protocol, Protocolo de Datagrama de usuário) e TCP (Transmission Control Protocol, Protocolo de controle de Transmissão). Em outras palavras, a camada de Transporte é dividida em protocolos orientados a conexão (TCP) e não confiáveis e não  orientados a conexão (UDP). Protocolos do tipo UDP fazem apenas a multiplexação de dados, enquanto que protocolos do tipo TCP efetuam outros mecanismos para abrir, manter e encerrar as sessões.

Abaixo são detalhadas as principais funções da camada de transporte:

- **Segmentação dos dados:** A camada de Transporte recebe os dados da camada de sessão e segmenta-os em pequenas partes (máximo 65525 bytes) para forma o segmento. Isso permite que a largura de banda seja otimizada e compartilhada entre diferentes aplicações.
- **Multiplexação da conversação:** Permite que diversas conversões (aplicações) sejam possíveis simultaneamente, otimizando a largura de banda disponível, como mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268173/13269.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/1/268173/13269.png)

Multiplexação da conversação

- **Controle de Fluxo:** Por meio das janelas móveis, a camada de Transporte especifica a quantidade de segmentos que o dispositivo fim é capaz de receber. Isso permite que diversos clientes se conectem a um determinado serviço, com o objetivo de garantir que todos os clientes tenham a possibilidade de receber dados. Isso quer dizer que, à medida que o número de clientes solicitantes desse serviço aumenta, a janela para cada cliente diminui, o contrário também é verdadeiro.
- **Controle de sequência e controle de erros:** Cada segmento é numerado para que seja reordenado no dispositivo fim, além cada segmento possuí um cabeçalho (header) contento uma soma verificadora (checksum). Essa implementação tem como objetivo garantir que os segmentos cheguem ordenados e livres de erros.

Cabe acrescentar que os protocolos da pilha UDP realizam apenas a multiplexação dos dados. Protocolos UDP deixam a responsabilidade da garantia da integridade dos dados para as camadas superiores. Em contrapartida, o UDP é muito utilizado quando se rapidez no transporte de dados como, por exemplo, uma transmissão de VOIP (voz sobre IP).

### Camada 5 - Sessão

Esta camada tem por finalidade estabelecer o sincronismo entre aplicações, iniciando, mantendo e encerrando sessões. Ela controla, por exemplo, de quem é a vez de falar, “grava” em qual ponto a conversão terminou com o objetivo de reiniciá-la. Exemplos de protocolos dessa camada são: SQL, ASP e RPC.

### Camada 6 - Apresentação

A camada de Apresentação pode executar basicamente três funções:

- **Apresentação dos dados**: Converte o formato de dados vindos da camada de Aplicação em um formato que seja compatível com um dispositivo fim. Um exemplo comum é a conversão do padrão de página quando um transmissor utiliza um padrão diferente do ASCII, como para EBCDIC.
- **Compactação:** Os dados podem também passar pela compressão dos dados com o objetivo de aproveitar de forma eficiente a largura de banda disponível.
- **Criptografia:** Tem o objetivo de aumentar a segurança, fazendo com que o dispositivo transmissor realize a criptografia dos dados, que por sua vez é decodificado na camada 6 do dispositivo receptor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/6/9/306991/21914.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/6/9/306991/21914.png)

Processo de criptografia

### Camada 7 - Aplicação

A camada de Aplicação prover a interface de interação entre o usuário e máquina por meio de programas (aplicações). Algumas das funções que podem ser necessárias são:

- Redirecionamento de dispositivo e o compartilhamento de recursos
- Acesso remoto a arquivos
- Acesso de impressora remota
- Comunicação entre processos
- Gerenciamento de rede
- Serviços de diretório
- Mensagens eletrônicas (como e-mail)
- Terminais de rede virtuais

Protocolos dessa camada: HTTP, SMTP, FTP, SSH, Telnet, SIP, RDP, IRC, SNMP, NNTP, POP3, IMAP, DNS.

Em resumo, cada camada do modelo OSI possui um conjunto de protocolos que pode ser resumido no gráfico abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/9/262975/10829.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/2/9/262975/10829.jpg)

Protocolos por camada