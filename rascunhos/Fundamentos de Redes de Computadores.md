## Objetivos de uma rede

- Acesso a dados e serviços: As redes permitem que os usuários acessem dados e serviços de outros dispositivos conectados à rede.
- Compartilhamento de recursos: Os recursos, como impressoras e armazenamento, podem ser compartilhados entre os dispositivos da rede.
- Administração centralizada: Uma rede pode ser administrada centralmente, facilitando o gerenciamento e a manutenção dos dispositivos e serviços.

## Camadas de Rede

- Modelo OSI: é um modelo de referência que divide as funções de rede em sete camadas distintas, cada uma com suas próprias responsabilidades. As camadas do modelo OSI são:
    1. Física
    2. Enlace de dados
    3. Rede
    4. Transporte
    5. Sessão
    6. Apresentação
    7. Aplicação
- Modelo TCP/IP: é outro modelo de referência amplamente utilizado na comunicação em redes. Ele consiste em quatro camadas principais:
    1. Acesso à rede
    2. Internet
    3. Transporte
    4. Aplicação
- Modelo proposto pelo Tanenbaum:
    1. Física
    2. Enlace
    3. Rede
    4. Transporte
    5. Aplicação

## Abrangência das redes

A infraestrutura de rede pode variar em termos de tamanho da área de cobertura, número de usuários, quantidade e tipos de serviços fornecidos e área de responsabilidade. Os principais tipos de redes são:

- PAN (Personal Area Network): É uma rede de área pessoal que conecta dispositivos em torno de uma pessoa
- LAN (Local Area Network): É uma rede local que cobre uma área limitada, como um escritório ou um prédio.
- MAN (Metropolitan Area Network): É uma rede metropolitana que abrange uma cidade ou uma área geográfica maior.
- WAN (Wide Area Network): É uma rede de longa distância que pode abranger uma grande área geográfica, como um país ou até mesmo globalmente.
- SAN (Storage Area Network): É uma rede de armazenamento dedicada para conectar dispositivos de armazenamento, como discos rígidos e unidades de fita.

### Como a internet funciona?

De um modo bem simples, e até grosseiro, a internet é um conjunto de várias redes interconectadas globalmente, permitindo a comunicação e o compartilhamento de informações e serviços em escala global (chora terraplanista).

### Intranets e Extranets

- Intranet: É uma rede privada de LANs e/ou WANs pertencente a uma organização. Ela é acessível apenas aos funcionários e membros autorizados da organização.
- Extranet: É a parte da rede que pode ser acessada por usuários externos à organização, fornecendo acesso controlado a determinados serviços ou informações.

## Arquitetura de Redes

Existem quatro características básicas que os arquitetos de rede devem considerar para atender às expectativas dos usuários:

1. Tolerância a falhas
    - Uma rede deve ser projetada para ser resiliente a falhas, de modo que, mesmo se um componente ou conexão falhar, a rede possa continuar funcionando sem interrupções significativas.
2. Escalabilidade
    - A arquitetura da rede deve ser escalável, ou seja, capaz de lidar com o aumento do número de dispositivos e usuários sem comprometer o desempenho.
3. Qualidade de Serviços (QoS)
    - A QoS refere-se à capacidade da rede de fornecer serviços com diferentes requisitos de desempenho, como largura de banda, latência e confiabilidade, de acordo com as necessidades dos aplicativos e usuários.
4. Segurança:
    - A segurança é uma consideração essencial na arquitetura de rede para proteger os dados e os recursos da rede contra acesso não autorizado, ataques e outras ameaças.

## Modelos de Redes de Computadores

### Centralizada

Mainframe x Terminais

Processamento é realizado no mainframe

### Cliente/Servidor

Cliente x Servidor

### Peer-to-peer

Ponto-a-ponto, P2P, PTP

## Topologias de Rede

xxx

## Serviços

### Tipos de Serviços

Basicamente, existem dois tipos de serviços na internet, orientado a conexão e sem conexão:

- Na comutação de circuitos, há um canal dedicado e uma rota pré-definida
- Na comutação de pacotes, os dados são enviados em blocos discretos e podem tomar rotas diferentes

Existem dois tipos de roteamento: redes de datagrama e circuitos virtuais

- As redes de datagrama seguem o caminho menos congestionado a cada pacote
- Os circuitos virtuais definem uma rota específica antes do envio do pacote

> Datagramas são unidades de transferência básica, associadas a redes de comutação de pacotes. Eles são usados em redes que fornecem um serviço de comunicação sem conexão, sem a necessidade de entrega garantida, hora de chegada ou ordem de chegada.

### Exemplos de Serviços

Email: é um serviço de comunicação eletrônica que permite o envio e recebimento de mensagens por meio da internet.

Terminal:

- Telnet: É um serviço que permite a conexão a um dispositivo remoto para acessar recursos e executar comandos, sem criptografia
- SSH: É um serviço similar ao Telnet, mas com criptografia, garantindo maior segurança nas comunicações.

Nuvem:

- Nuvem pública: É uma infraestrutura de computação em nuvem fornecida por provedores de serviços para uso público geral.
- Nuvem privada: É uma infraestrutura de computação em nuvem que é dedicada a uma única organização e não é compartilhada com outras organizações.