O presente tópico tem por objetivo apresentar de forma geral como funciona os escâneres de farejados de rede, além de mostrar como funciona algumas ferramentas de escaneamento.

### **Introdução**

Os escâneres, assim como a maioria das ferramentas utilizadas em segurança de rede podem ser utilizadas para fins de diagnostico e resolução de problemas, mas, ao mesmo tempo, podem ser utilizadas por um invasor, de forma ilegal, com objetivo de descobrir vulnerabilidades nos computadores e na rede.

As ferramentas de escaneamento examinam e criam relatórios sobre a vulnerabilidade dos computadores da rede local e até mesmo de computadores em redes remotas. Tais ferramentas são especializadas para o proposito de escanear portas, por isso, muitas vezes são conhecidos escâneres de porta. Porém, podemos encontrá-los como parte de utilitários de rede.

### Escâneres de porta

Os escâneres de porta verificam o status das 65.536 portas, se elas estão abertas ou fechadas, além de verificarem qual aplicação está rodando naquela porta. Antes de começar a tratar dos escâneres de rede, é importante conhecer algumas dessas portas. Elas são reunidas em três grandes grupos: Portas conhecidas, Portas Registradas e Portas Dinâmicas ou Privadas, e são mostradas na tabela que segue (Basta, A; Basta, N. Brown, M. 2015).

|Intervalo de Porta|Grupo de porta|
|---|---|
|[[0 a 1023]]|Portas Conhecidas|
|[[1024 a 49151]]|Portas Registradas|
|[[49152 a 65535]]|Portas Dinâmicas e/ou privadas|

  
  

As portas conhecidas são aquelas reservadas para os serviços e aplicativos mais utilizados e conhecidos como o HTTP (porta TCP 80), FTP (Portas TCP 20/21), DNS (Portas UDP/TCP 53) etc. Por outro lado, as Portas Registradas são utilizadas para aplicações específicas, geralmente aplicações proprietárias, por exemplo, porta TCP/UDP 1433 (MS SQL), porta TCP/UDP 5060 (SIP) e porta TCP 5800 (VNC). Por fim, as portas Dinâmicas, que são normalmente utilizadas para identificar o cliente e são dinamicamente atribuídas pelo cliente para identificá-la na conexão com um servidor que, por sua vez, normalmente, utilizam portas Privadas ou Registradas.

**SAIBA MAIS...**

Para conhecer as Portas Registradas e Conhecidas, acesse [**http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-pt_br-4/ch-ports.html**](http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-pt_br-4/ch-ports.html)

### Funcionamento dos escâneres

Os escâneres podem analisar um único endereço IP ou vários endereços IPs, podendo conectar  e descobrir as suas vulnerabilidades do dispositivo(s) alvo(s). Portanto, os escâneres automatizam o processo de descoberta de pontos fracos da rede a partir de vulnerabilidades já conhecidas, e procuram abrir portas com base nessas vulnerabilidades. De forma geral, os escâneres desempenham as seguintes funções (Basta, A; Basta, N. Brown, M. 2015):

- Escanear o dispositivo alvo para descobrir os serviços que são executados nele;
- Verificar os serviços que estão ativos e as vulnerabilidades a eles associados;
- Conecta-se ao dispositivo alvo.

### Tipos de escaneamento

**Os escaneamentos podem ser dos seguintes tipos (McNab, Chris. 2017):**

- **Escaneamento de Ping:** Demonstra que o dispositivo de destino está ativo na rede caso o escâner receba eco replay do dispositivo alvo. Falso-negativo são comuns nesse tipo de escaneamento, já que o dispositivo alvo pode estar configurado a não responder este tipo de solicitação.
- **Escaneamento do Protocolo IP:** O escâner investiga quais protocolos IP são suportados pelo dispositivo alvo. Neste caso ele envia para o dispositivo alvo pacotes IP para cada protocolo. Se o protocolo no dispositivo alvo responde para o escâner com uma mensagem ICMP do tipo unreachable (inacessível), significa que o dispositivo alvo não esse protocolo.
- **Escaneamento de UDP:** O escâner envia um segmento UDP de 0 byte para a porta ou conjunto de porás do dispositivo alvo. Caso ele receba uma mensagem ICMP do tipo unreachable, isso significa que aporta está fechada. Se a porta estiver ativa ele não recebe uma mensagem como essa.
- **Escaneamento de conexões TCP:** O escâner tenta realizar conexões TCP em todas as portas do dispositivo alvo. Caso o dispositivo alvo responda com uma mensagem do tipo connection-succeeded (conexão bem sucedida) é indicativo que a porta está ativa. Por outro lado, se ele receber uma resposta do tipo host- unreachable (dispositivo inacessível) é indicativo de que a porta está inativa.
- **Escaneamento Semiaberto:** No escaneamento semiaberto, o escâner envia apenas SYN e não responde as mensagens SYN/ACK enviadas pelo dispositivo alvo, indicando que a porta está aberta. Isso é realizado com objetivo de evitar que o dispositivo alvo grave em seus logs a tentativa de conexão.
- **Escaneamento Discreto:** Permite a análise do dispositivo alvo por trás de firewalls e filtros de pacotes.

**SAIBA MAIS...**

IDS (Sistema Detecção de Intrusão) como o Snort podem ser configurado gravar tentativas de escaneamento Semiaberto e também do Escaneamento Discreto. P que a maiorias dos sistemas operacionais não realiza a gravação de log. Para saber mais sobre o Snort acesse: [**https://www.snort.org**](https://www.snort.org/).

### Tecnologias de Escâneres

Em termos tecnológicos, existe uma grande diversidade de Escâneres, e para melhor nos orientarmos, eles serão divididos de acordo com a fase de processo de teste de invasão, conforme elencado na tabela que segue (Basta, A; Basta, N. Brown, M. 2015).

![[Untitled 86.png|Untitled 86.png]]

### Nmap

Escâner de código aberto poderoso e fácil de usar. Está disponível para uso em código aberto, utilizado para mapeamento de diversas funcionalidades e características, tais como, detecção do Sistema Operacional, detecção da versão do serviço instalado, varredura de porta (Fraga, Bruno. 2019).

O Nmap normalmente trabalha na camada de Internet e Transporte. Entretanto, é possível obter informações de endereços MACs e solicitações ARP, além de obter informações da camada de aplicação com objetivo de identificar os serviços da camada de Aplicação.

Hoje, é possível utilizar uma versão limitada do Nmap Online, por meio do site: [**https://nmap.online**](https://nmap.online/). O exemplo de saída abaixo mostra um escaneamento rápido ao site da Uninove.

![[Untitled 1 50.png|Untitled 1 50.png]]

Na tabela abaixo são mostrados os principais exemplos de escaneamento com Nmap (Nmap, 2020).

|Exemplo|Explicação|
|---|---|
|[[nmap 192.168.1.254]]|Escanear um único endereço|
|[[nmap -F 192.168.1.2]]|Executa uma verificação rápida|
|[[nmap 192.168.1.1 192.168.1.2 192.168.1.3]]|Escanear múltiplos endereços ou sub-redes|
|[[nmap 192.168.1.0-24]]|Escanear uma sub-rede|
|[[nmap -6 2001-db8-cafe-1--2]]|Escanear rede IPv6|
|[[nmap -sP 192.168.1.0-24]]|Escanear para descobrir quais servidores e dispositivos estão funcionando|
|[[nmap --open 192.168.1.2]]|Mostrar apenas as portas abertas|
|[[nmap -p 80 192.168.1.2]]|Especificar uma porta|
|[[nmap -T5 192.168.1.0-24]]|Descobrir todas as portas e computadores em uma rede|
|[[nmap -O 192.168.1.2]]|Detectando um sistema operacional remoto|
|[[nmap -sS 192.168.1.2]]|Descobrir as portas mais utilizadas usando TCP SYN|
|[[nmap -sT 192.168.1.2]]|Descobrir Portas mais utilizadas utilizando TCP connect|
|[[nmap -sA 192.168.1.2]]|Descobrir Portas mais usadas utilizando TCP ACK|
|[[nmap -sU 192.168.1.2]]|Escaner de host utilizando serviços UDP|
|[[nmap 192.168.1.2 saída.txt]]|Salvando a saída em um arquivo de texto|

  
  

**SAIBA MAIS...**

Existe também a versão em modo gráfico e disponível para sistemas operacionais Microsoft. Para saber mais, acesse: [**https://nmap.org/download.html**](https://nmap.org/download.html).