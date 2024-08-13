### Introdução

A proteção de redes passa pela adoção de vários mecanismos de segurança, proporcionado níveis diferentes de proteção. Nesse sentido, os Firewalls (Parede de fogo), IDS (Sistemas de Detecção de Intrusão) e os IPS (Sistemas de Prevenção de Intrusão) têm papel fundamental.

Muitas vezes, costumamos chamar de Firewall qualquer mecanismo de proteção de rede, sem levar em consideração as especificidades de cada um deles. Um Firewall, por exemplo, possui um conjunto de regras permissivas, permitindo ou não passagem do tráfego, semelhante ao que acontece com as ACL (Listas de Controle de Acesso). Dessa forma, podem controlar, por exemplo, o tráfego que passa de uma sub-rede para outra.

Por sua vez, os IDS são posicionados em rede, normalmente de forma passiva, analisando e gerando alertas para o administrador do sistema ou encaminhando-o para um firewall. Por outro lado, podemos dizer, de forma simplista, que os IPS são dispositivos que reúnem as funções de Firewall e IDS em um mesmo dispositivo. Isso faz com que ele tenha uma inteligência reativa em caso de violação de segurança, ou seja, detectando e prevenindo a intrusão.

Na figura abaixo são mostrados diversos mecanismos de segurança. O posicionamento de tais dispositivos na rede leva em consideração as características de funcionamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/3/3/3/8333388/60074.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/3/3/3/8333388/60074.jpg)

Posicionamento dos sistemas de proteção

Fonte: Cisco System (Adaptado)

### Firewalls

Os firewalls são sistemas ou grupo de sistemas que reforça a política de controle de acesso entre redes ou sub-redes, sendo muitas vezes utilizado como ponto de central entre a rede pública e a privada, fazendo com que todo o tráfego passe por ele. Dessa forma, o firewall pode autorizar, negar, além de registrar tal tráfego. Basicamente todo firewall possui as seguintes propriedades em comum (Moraes, A. F. 2010):

- Os firewalls são resistes a ataques de rede
- Os firewalls são o único ponto de trânsito entre a rede corporativa e rede externa, já que todo tráfego passa por ele.
- Os firewalls reforçam a política de controle de acesso

No quadro abaixo é apresenta as vantagens e desvantagens dos firewalls (CCNA Cybersecurity Operations, 2020):

![[Untitled 96.png|Untitled 96.png]]

### Tipos de Firewall

Existem basicamente três tipos de firewall de acordo com as suas capacidades e uso em redes (Moraes, A. F. 2010):

- **Firewall filtros de pacote (stateless):** Alguns tipos de roteadores tem a capacidade de verificar o cabeçalho de camada de Rede e da camada de Transporte a partir de regras pré-configuradas, tais como:
    - Endereço IP de origem e destino.
    - Porta de origem e porta de destino.
    - Flags de sincronismo (SYN)
- **Firewall sem estado (stateful):** firewalls do tipo stateful permitem bloquear ou permitir o tráfego baseado no estado, na porta e no protocolo. Isso faz com que ele monitore toda a atividade, desde o início até o encerramento da conexão por meio de regras ou pela característica pertencentes ao fluxo de dados que passa pelo firewall.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259245/15017.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/9/2/259245/15017.PNG)

Console de configuração do firewall do Windows.

Os firewalls podem ser diferenciados de acordo com a sua atuação em relação ao modelo OSI, conforme mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/6/5/6/8365689/60075.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/6/5/6/8365689/60075.jpg)

Firewall de aplicação.

Fonte:

Existem ainda outras implementações de firewall, tais como (Moraes, A. F. 2020):

- **Firewalls baseados em host (****Host-based):** Firewall baseado em software instalado em servidores e desktops, como Windows Firewall, iptables, nftables e TCP Wrapper . Na figura abaixo é mostrado o console de configuração do firewall do Windows.
- **Firewalls de aplicação (proxy firewall):** Filtra informações das camadas de rede, transporte, sessão e aplicação do modelo OSI. Quando um cliente necessita realizar uma conexão com um servidor remoto, o servidor proxy, em nome do cliente, realiza a conexão remota.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835324/36621.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835324/36621.png)

Configuração das informações do servidor proxy no navegador do cliente

- **Firewalls Transparentes:** não possuem endereços IPs em suas interfaces a partir de um par de interface em modo bridge, com a capacidade de bloquear uma conexão ou aplicação.

Além do monitoramento do tráfego entre redes, o firewall também é capaz de desempenhar as seguintes funções (Moraes, A. F. 2010):

- Análise de conteúdo
- Gateway de VPN
- Tradução de endereços de rede (NAT)
- Autenticação de usuários
- Balanceamento de carga

### Atividade 1 - Firewall ASA

A atividade tem por objetivo estabelecer a configuração via CLI do firewall Cisco ASA 5505 no Packet Tracer. Para tanto, baixo o arquivo .pka para execução da atividade e o roteiro em pdf. Para saber mais sobre o firewall ASA, consulte o [[C]] e a documentação do próprio site da [**Cisco**](https://www.cisco.com/c/pt_br/support/security/asa-5505-adaptive-security-appliance/model.html).

### **Sistemas de Detecção de Intrusão (IDS) e prevenção de intrusão (IPS)**

Os firewalls não possuem mecanismos de controles de ataques que ocorrem dentro da rede, pois o tráfego necessita passar por ele para que exista uma tomada de decisão. Nestes casos, a utilização de mecanismos de detecção de intrusão se torna bastante eficiente, gerando alertas de possíveis ataques aos servidores e derrubando a conexão do invasor.

As tecnologias IDS e IPS compartilham várias características. As tecnologias IDS e IPS são implantadas como sensores. Um sensor IDS ou IPS pode ser na forma de vários dispositivos diferentes (CCNA Cybersecurity Operations, 2020):

- Um software devidamente configurado em roteadores
- Appliances IDS ou IPS (Dispositivo dedicado).
- Um módulo de rede instalado em um dispositivo de segurança como, por exemplo, um firewall ASA, switch ou roteador

As tecnologias IDS e IPS usam assinaturas para detectar padrões no tráfego da rede. Uma assinatura é um conjunto de regras que um IDS ou IPS usa para detectar atividades maliciosas. As assinaturas podem ser usadas para detectar violações graves de segurança, detectar ataques de rede comuns, além de coletar informações. As tecnologias IDS e IPS podem detectar padrões de assinatura em um único pacote ou padrões de assinatura em múltiplos pacotes (Moraes, A. F. 2010)..

### Modo de operação dos IDS

Os IDS utilizam os seguintes métodos para detecção de intrusão (Moraes, A. F. 2010):

- **Análise de assinaturas de ataque:** os sistemas são previamente alimentados com as características dos principais tipos de ataque realizados pelos hackers. Se o hacker utiliza um ataque novo que o IDS não possui a assinatura, ele não será reconhecido e o ataque pode ter concretizado.
- **Análise de Protocolo:** verificam as características dos protocolos de aplicação para determinar se existe algo de errado. Por exemplo, ataques de overflow do buffer de servidores DNS podem ser detectados pela análise de protocolo, já que são inseridos bytes extras nesse tipo de ataque.
- **Detecção de anomalias:** Envolve o monitoramento de CPU, memória, disco e logs do sistema operacional com o objetivo de determinar se a anomalia pode ser um ataque ou não.

Temos que ter em mente que os IDS detectam problemas ou anomalias, mas cabe ao administrador de rede determinar esses problemas ou anomalias são realmente provenientes de um ataque. Muitas vezes ocorrem o que é chamada de falsos positivos, levando a crer que realmente está sob ataque, que devem ser minimizados com IDS de última geração.

### Tipos de IDS

Existem ainda outra classificação dos IDS que leva em consideração o seu posicionamento em rede:

- **Sistemas de detecção baseados em rede (NIDS):** atual com análise do tráfego em rede, normalmente posicionados de forma offline em locais estratégicos da rede, antes ou após os firewalls, dentro de uma sub-rede e em DMZ(Zonas Desmilitarizadas). Observe a partir da figura abaixo que o IDS está posicionado offline dentro de uma DMZ enquanto o IPS está posicionado em linha.
- **Sistemas de detecção baseados em host (HIDS):** trabalham verificando arquivos, aplicações e logs de eventos das estações e servidores. A grande vantagem desses do HIDS está na sua capacidade de verificar tráfego criptografado e possibilidade de colocar arquivos e modificações do sistema em quarentena em caso de ações que fogem ao seu funcionamento.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/3/8/8313807/60116.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/3/8/8313807/60116.png)

Posicionamento de IDS e IPS

### Ferramentas de detecção de intrusão

As ferramentas [**Snort**](https://www.snort.org/), [**Bro**](https://zeek.org/) e [**Suricata**](https://suricata-ids.org/)) são exemplos de NIDS. Elas são utilizadas em ambiente de Monitoramento de segurança de rede (NMS) como o [**Security Onion.**](https://docs.securityonion.net/en/16.04/introduction.html#analysis-tools) A ferramenta [**OSSEC**](https://www.ossec.net/), também presente no Security Onion, é um exemplo de HIDS.

Ferramentas como [**CapME**](https://docs.securityonion.net/en/latest/capme.html), [**Wireshark**](https://docs.securityonion.net/en/latest/wireshark.html) e [**Sguil**](https://docs.securityonion.net/en/latest/sguil.html)  são utilizadas para reunir informações e analisar dados capturados por vários detectores (sensores) de intrusão, seja ele um NIDS ou HIDS. A imagem abaixo mostra a tela do Sguil.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/9/3/8319390/60117.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/9/3/8319390/60117.jpg)

Painel de controle do Sguil

Fonte: CCNA CyberOps. Cisco System

O alerta (alert) mostrado no Sguil da figura abaixo foi acionado por uma regra (rule) que foi criada no Snort. É importante ser capaz de interpretar o que acionou o alerta para que o alerta possa ser investigado. Por esse motivo, para análise das informações deve-se entender os componentes das regras do Snort.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/9/4/8319404/60118.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/1/9/4/8319404/60118.jpg)

Alertas gerados por regras configuradas no Snort

Fonte: CCNA CyberOps. Cisco System

**SAIBA MAIS...**

Para conhecer um pouco mais as regras do Snort consulte: T[**HE ANATOMY OF A SNORT RULE**](https://snort-org-site.s3.amazonaws.com/production/document_files/files/000/000/116/original/Snort_rule_infographic.pdf?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIXACIED2SPMSC7GA%2F20200814%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20200814T200345Z&X-Amz-Expires=172800&X-Amz-SignedHeaders=host&X-Amz-Signature=0b7c03025f866182c3efb7c46d6cd86eaf20c77afc060b03b4f736644d9af390) e também o próprio site do [**Security Onion**](https://docs.securityonion.net/en/latest/snort.html).

### Prevenção de Intrusão (IPS)

Os Sistemas de Prevenção de Intrusão (IPS) reuni a capacidade de análise de um IDS, gerando alertas a partir de uma tentativa de ataque e a capacidade de bloqueio de um firewall. Como já comentado, normalmente, os IPS são colocados em segmentos específicos da rede, em linha com o tráfego, inspecionando dados de todas as camadas do modelo OSI, inclusive, a varredura profunda das aplicações. Mais especificamente, os IPS são capazes de detectar as seguintes ameaças de rede (Moraes, A. F. 2010):

- Spyware
- Spam e phishing
- Propagação de vírus
- Propagação de worms
- Exploração de vulnerabilidades de redes
- Ataque relacionados a sistemas operacional
- Ataques direcionados a aplicações Web, como SQL Injection e PHP Injections
- Uso da rede por aplicações não permitidas como P2P, torrente, jogos etc.

### Tipos de IPS

Assim como os IDS, os IPS possuem a capacidade de operar em rede (NIPS) e baseados em hosts (HIPS):

- **IPS baseados em host (HIPS):** Os HIPS podem ser entendidos como a combinação de softwares antivírus, antimalwares e firewall instados em host. Eles são capazes de monitorar e proteger o sistema operacional a partir do monitoramento e da detecção de comportamento anormal de processos em curso no host como instalação de programas, mudança no sistema de diretório, alterações no registro do sistema e atividades que podem levar a estouro de buffer. Além disso, os HIPS podem monitorar a atividade de rede para evitar que o host participe de um ataque de negação de serviço (DoS).
- **IPS baseados em rede (NIPS):** Os NIPS podem ser ou não um dispositivo dedicado. Sensores são posicionados em locais estratégicos da rede, detectando atividades maliciosas em tempo real e agindo quando necessário em caso de violação de segurança. É importante mencionar os NIPS, a partir de seus sensores, são capazes de impedir um ataque independentemente da localização do ataque.

### Atividade 2 - Configuração de IPS

A atividade tem por objetivo estabelecer a configuração via CLI do IPS em roteadores Cisco no Packet Tracer. Para tanto, baixo o arquivo .pka para execução da atividade e o roteiro em pdf. Para saber mais sobre o IPS cisco, consulte o site da [**Cisco**](https://www.cisco.com/c/pt_br/support/security/ios-intrusion-prevention-system-ips/series.html).