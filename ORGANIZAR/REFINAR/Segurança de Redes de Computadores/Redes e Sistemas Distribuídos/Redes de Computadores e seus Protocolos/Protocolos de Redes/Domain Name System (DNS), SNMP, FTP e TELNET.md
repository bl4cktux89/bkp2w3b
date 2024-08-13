[![](https://ampli-images.s3.amazonaws.com/production/1292646d-a526-4b0f-8480-f322aee6e9a1/original)](https://ampli-images.s3.amazonaws.com/production/1292646d-a526-4b0f-8480-f322aee6e9a1/original)

Protocolo utilizado para o sistema de nomes de domínio que faz a interconexão de URL, ou seja, nomes de endereços de sites da internet com endereços IP. Para que endereços de camada de Internet IP tenham sua localização em um sistema distribuído mundialmente, é necessário que exista, no mundo, um sistema de nomes de domínios para a organização dos servidores na rede. Esse sistema é chamado _Domain Name System_ (DNS) e seu objetivo é organizar os servidores na internet para que endereços IP sejam convertidos em nomes, como www.iana.org, por exemplo, e vice-versa.

Esse sistema é uma estrutura hierárquica em que, no topo, há um servidor-raiz interligado a servidores de domínios de níveis inferiores, de primeiro e segundo níveis. Os domínios primários são chamados de servidores DNS de domínio de alto nível (TDL), aqueles referenciados por: .com, .gov, .mil, .edu entre outros adicionados das informações dos países, como: .br, .uk .it.

Os domínios de segundo nível, servidores DNS autoritativos, possuem duas partes, designando-se os nomes de primeiro e de segundo nível, como exemplo: empresa.com. Um nome de host designa o computador final, específico na internet, em uma rede privada. O protocolo TCP utiliza as portas 53 e 953 para acessar o DNS, e o protocolo UDP utiliza a porta 53 para seu acesso.

Para tratar da questão da escala, o DNS usa um grande número de servidores, organizados de maneira hierárquica e distribuídos por todo o mundo. Nenhum servidor DNS isolado tem os mapeamentos completos para _hosts_ da Internet. Os mapeamentos são distribuídos pelos servidores DNS por meio de três classes de servidores DNS: raiz, de domínio de alto nível (_Top-Level Domain_ — TLD) e servidores DNS autoritativo, conforme ilustrado na próxima figura.

Por exemplo, considere que um cliente DNS deseja determinar o endereço IP para o nome de host www.amazon.com. Na primeira aproximação, o cliente contatará um dos servidores raiz, que retornará endereços IP dos servidores TLD para o domínio de alto nível com. Em seguida, o cliente contatará um servidor TLD, que retornará o endereço IP de um servidor autoritativo para amazon.com; por fim, o cliente contatará um dos servidores autoritativos para amazon.com, que retornará o endereço IP para o nome de host www.amazon.com (KUROSE; ROSS, 2013).

[![](https://ampli-images.s3.amazonaws.com/production/5ca24454-490c-49c6-93c3-3c10cbbbc08b/original)](https://ampli-images.s3.amazonaws.com/production/5ca24454-490c-49c6-93c3-3c10cbbbc08b/original)

Parte da hierarquia de servidores DNS. Fonte: Kurose; Ross (2013, p. 99).

_**SIMPLE NETWORK MANAGEMENT PROTOCOL (SNMP)**_

Protocolo de gerenciamento de redes simples que realiza coleta e mensuração de performance de rede. Conforme Forouzan (2010), o gerenciamento de redes refere-se a monitoramento, teste, configuração e diagnóstico de componentes de rede para atender a um conjunto de exigências definidas por uma organização. Esse protocolo realiza o gerenciamento de configuração, falhas (reativas, proativas), desempenho (capacidade, tráfego, _throughput_, tempo de resposta), segurança e contabilização. O protocolo UDP utiliza as portas 161 e 162 para acessar o SNMP.

_**FILE TRANSFER PROTOCOL (FTP)**_

Protocolo de transferência de arquivos entre dispositivos em uma rede de computadores. Tanto o HTTP quanto o FTP são protocolos de transferência de arquivos, como afirmam Kurose e Ross (2013).

O protocolo TCP utiliza as portas 20 e 21 para acessar e gerenciar o FTP; ele utiliza duas portas para conexão via camada de transporte, uma é utilizada para conexão de controle e a outra para a conexão de dados. O FTP oferece maior facilidade de comunicação entre computadores para transferência de arquivos com maior velocidade, praticidade e sem necessidade de dispositivos externos. São exemplos de aplicativos que operacionalizam o serviço de transferência de arquivos via protocolo FTP: FileZila, um dos mais conhecidos programas por ser de fácil uso e trazer ferramentas completas; _Classic_ FTP; Fere FTP; e _Cyberduck_ com código aberto e compatibilidade com diversas plataformas.

_**TELEPHONE NETWORK (TELNET)**_

Protocolo de conexão remota utilizado por meio de um terminal, representado por um prompt de comando nos sistemas operacionais. O protocolo TCP utiliza a porta 23 para acessar o Telnet.

A camada de aplicação traz um volume grande de protocolos, alguns mais novos, desenvolvidos, por exemplo, para a realidade da internet atual, em que aplicações em HTTP necessitam de transmissão de streaming de vídeos. Um exemplo é o protocolo _Hypertext Transfer Protocol Live Streaming_ (HLS), que se utiliza das novas tecnologias e velocidades de transmissão em sistemas móveis para protocolos de nível de transporte confiáveis para distribuição de conteúdo de streaming em velocidades compatíveis com as necessidades dos sistemas. Novos protocolos são desenvolvidos constantemente para provisão de segurança em sistemas e adaptação às novas necessidades tecnológicas dos sistemas distribuídos via internet.

______

**💭Reflita**

**HTTPS = HTTP + SSL.**

O protocolo HTTPS é o protocolo HTTP adicionado de serviço de segurança provido pelo protocolo _Secure Socket Layer_ (SSL), implementado sob a camada de transporte e abaixo da camada de aplicação na arquitetura TCP/IP. Esse protocolo oferece recurso de criptografia para as informações transmitidas do servidor até o navegador de internet do host. O HTTPS utiliza a porta 443 via TCP. A versão do SSL3 é denominada _Transport Layer Security_ (TLS). Mesmo com essas tecnologias implementadas para melhorar a segurança nas aplicações em rede, ainda existem fragilidades que podem deixar sua conexão vulnerável, como podemos ver no artigo HTTPs não quer dizer seguro, da empresa de soluções de segurança Kaspersky.