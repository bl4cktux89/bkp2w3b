O WCCP (**Web Cache Communication Protocol**) é um protocolo de roteamento que fornece um mecanismo para redirecionar o fluxo de tráfego em tempo real. Foi construído com mecanismos para permitir o balanceamento de carga, tolerância a falhas e garantia de serviço (failsafe).

Como todo o tráfego da rede passa pelo proxy, o mesmo passa a ter novas funções como verificar os padrões de trafego na rede permitindo que diversos conteúdos sejam atendidos localmente. O fato da taxa de sucesso ou acerto no proxy reduz o tráfego de acesso à Internet e, consequentemente, diminui os custos de transmissão e o tempo de download.

Quando um mecanismo de cache recebe uma solicitação, ele tenta procurar o objeto a partir de seu próprio cache local. Se a informação solicitada não estiver presente, o mecanismo de cache emite seu próprio pedido ao servidor originalmente direcionados para obter as informações necessárias. Quando o mecanismo de cache recupera as informações solicitadas, ele encaminha-o para o cliente solicitante e armazena em cache-local para atender a solicitações futuras, maximizando assim o desempenho de download e reduzindo sensivelmente os custos de transmissão

Para garantir uma boa taxa de sucesso ou acerto no proxy é necessário um estudo na implantação e padrão de uso da internet do usuário, ou seja, objetos maiores podem representar maiores sucesso de cache em detrimento de objetos menores com maior economia no enlace de saída. Por outro lado, se o perfil de busca é de pequenos objetos, o proxy deve ser reconfigurado para conseguir maiores taxas de sucesso, o que deixa a configuração um pouco mais complexa.

De qualquer forma o uso dos proxy-cache são bastante vantajosos em uma rede corporativa, visto que existem muitos recursos na Internet que são utilizados por diversos usuários que podem ser atendidos localmente. Sem o proxy, as mesmas requisições seriam feitas diversas vezes, sempre abrindo uma nova conexão TCP, mesmo que o recurso já tenha sido solicitado minutos atrás.

Neste contexto nasceu o WCCP, que é um protocolo que permite o uso de um _**proxy-cache**_ e tem a função, além das funções de cache, a de manipular o tráfego Web, reduzindo o custo de transmissão e o tempo de _**download**_. Existem basicamente duas versões do protocolo do WCCP, versão 1 e 2. A versão 1 permite que um roteador participe do serviço de _**proxy**_ efetuando o redirecionamento dos pacotes. A figura 1 apresenta os detalhes do WCCPv1

![[pic1.jpg]]

Já a versão 2, WCCPv2 suporta múltiplos roteadores, o que melhora consideravelmente o desempenho do uso do proxy em uma rede, de modo que seja possível efetuar um balanceamento entre os roteadores. A versão 2, também permite diversos recursos de segurança na conexão entre o roteador e o proxy-cache.

![[PIC2.jpg]]

**Módulo ip_wccp nos roteadores** 

O protocolo GRE (_**Generic Routing Encapsulation**_) é um protocolo genérico, usado para encapsular informações de roteamento em pacotes IP. Este protocolo é usado pelo WCCP no roteador para encapsular os pacotes com destino a servidores Web por ele recebido. Este pacote será enviado para um servidor de _**proxy-cache**_ que terá que desencapsular o mesmo antes de enviá-lo aos servidores proxy.

**Configurando o Roteador**

A configuração do roteador consiste basicamente em habilitar o serviço de WCCP conforme os passos abaixo, que mostram os comandos necessários para proceder a essa habilitação:

1. conf t

2. ip wccp version 1

3. ip wccp web-cache

4. int (interface que se deseja habilitar o WCCP. Correntemente, usa-se a interface de acesso à Internet)

5. ip wccp web-cache redirect out

Sugerimos a montagem de um laboratório com GNS3 e roteador 7200 CISCO.

Após essas etapas, o _**proxy**_ transparente já estará funcionando. Para verificar se o _**proxy-cache**_ está se anunciando ao roteador, habilite o modo **debug** para analisar os eventos referentes ao WCCP:

O Web Cache Communication Protocol (WCCP) é uma tecnologia de conteúdo de roteamento desenvolvido que permite integrar web de cache em sua infraestrutura de rede. É possível, desta forma gerenciar clusters do mecanismo de cache (fazendas de cache), principalmente com o uso WCCPv2.

WCCP permite uma série de mecanismos de cache, chamado de cluster de cache, para fornecer conteúdo a um roteador ou vários roteadores. Os administradores de rede podem facilmente escalar seus web de cache para lidar com cargas de tráfego pesado através desses recursos de cluster. Tecnologia de cluster permite que cada membro do cache trabalhe em paralelo, resultando em escalabilidade linear.

_**Clustering**_ web de cache melhora a escalabilidade, redundância e disponibilidade da solução de cache. Algumas soluções permitem agrupar até 32 proxies (web cache) para se adaptar a capacidade desejada.

Usando WCCPv1, os web cache são configurados com o endereço do único roteador. WCCPv2 exige que cada mecanismo de cache esteja ciente de todos os roteadores no grupo de serviço. Para especificar os endereços de todos os roteadores em um grupo de serviço, deve-se escolher um dos seguintes métodos:

- Unicast - A lista de endereços do roteador para cada um dos roteadores no grupo está configurada em cada web cache. Neste caso, o endereço de cada roteador no grupo deve ser explicitamente especificado para cada mecanismo de cache durante a configuração.
- Multicast - Um único endereço de multicast é configurado em cada web cache. No método endereço de multicast, o mecanismo de cache envia uma notificação de endereço único que oferece cobertura para todos os roteadores no grupo de serviço. Por exemplo, um mecanismo de cache poderia indicar que os pacotes devem ser enviados para um endereço de multicast de 224.0.0.100, que iria enviar um pacote multicast para todos os roteadores no grupo de serviço configurado para escuta em grupo usando WCCP.

A opção de multicast é mais fácil de configurar, porque somente é necessário especificar um único endereço em cada web cache. Esta opção também permite adicionar e remover roteadores de um grupo de serviços de forma dinâmica, sem a necessidade de reconfigurar os web de cache com uma lista diferente de endereços de cada vez.

A seguinte sequência de eventos detalha como configuração WCCPv2 funciona:

1. Cada mecanismo de cache é configurado com uma lista de roteadores.

2. Cada mecanismo de cache anuncia sua presença e uma lista de todos os roteadores com o qual estabeleceu comunicações. Os roteadores respondem com seu ponto de vista (lista) de web de cache do grupo.

3. Uma vez que a visão é consistente em todos os mecanismos de cache em cluster, um mecanismo de cache é designado e define a política que os roteadores precisam implantar no redirecionamento de pacotes.

WCCPv2 fornece os recursos descritos a seguir:

- Suporte para serviços que não sejam HTTP;
- Suporte para vários roteadores;
- Segurança MD5;
- Web Cache pacote de retorno;
- Distribuição de carga;
- Suporte para serviços que não sejam HTTP.

WCCPv2 permite o redirecionamento de tráfego que não seja HTTP (porta TCP 80), incluindo uma variedade de aplicações em UDP, além do tráfego TCP. WCCPv2 suporta o redirecionamento de pacotes destinados a outras portas, incluindo os utilizados para a manipulação proxy cache-web, como o File Transfer Protocol (FTP) caching, manuseio de proxy FTP, cache de web para outras portas 80, áudio em tempo real, bem como aplicações de vídeo e telefonia .

Para acomodar os vários tipos de serviços disponíveis, WCCPv2 introduz o conceito de vários grupos de serviço. As informações de serviço são especificadas na configuração WCCP usando serviços dinâmicos, números de identificação ou palavras-chave pré-definidas de serviços (tais como a "web-cache"). Esta informação é usada para validar que os membros do grupo de serviço estão todos usando ou fornecendo o mesmo serviço.

Os web cache no grupo de serviço especificam o tráfego a ser reencaminhado pelo protocolo (TCP ou UDP) e porta (origem ou destino). Cada grupo de serviço tem um status de prioridade atribuído a ele. Os pacotes são comparados com grupos de serviço em ordem de prioridade.

**Suporte para vários roteadores**

WCCPv2 permite que vários roteadores possam ser anexados a um conjunto de mecanismos de cache. O uso de vários roteadores em um grupo de serviço permite a redundância, a agregação de interface, e distribuição da carga de redirecionamento.

**MD5 Segurança**

WCCPv2 fornece autenticação opcional que permite o controle de quais roteadores e web de cache tornam-se parte do grupo de serviço usando senhas com utilização do padrão HMAC MD5 permindo que mensagens sejam protegidas contra a intercepção, inspeção e replay.

**Retorno Web Cache Packet**

Se um mecanismo de cache é incapaz de fornecer um objeto solicitado que tem em cache devido a erro ou sobrecarga, o mecanismo de cache voltará a solicitação para o roteador para posterior transmissão para o servidor de destino especificado originalmente. WCCPv2 permite verificar os pacotes que determina que os pedidos foram devolvidos a partir do mecanismo de cache unserviced. Usando essa informação, o roteador pode então encaminhar a solicitação para o servidor alvo original (ao invés de tentar reenviar o pedido para o cluster de cache). Isto proporciona transparência aos clientes.

**Distribuição de carga**

WCCPv2 pode ser usado para ajustar a carga que está sendo oferecido para web de cache individuais para proporcionar uma utilização eficaz dos recursos disponíveis, ajudando a garantir uma elevada qualidade de serviço (QoS) para os clientes. WCCPv2 permite o cache designado para ajustar a carga em um cache especial e equilibrar a carga entre os caches em um cluster. WCCPv2 usa três técnicas para realizar a distribuição de carga:

- Hot Spot;

• Balanceamento de carga;

- limitação de carga.

**Restrições para WCCPv2**

As seguintes limitações se aplicam a WCCP v2:

- WCCP só funciona com redes IP.
- Para roteadores atendendo um cluster multicast, o Time to Live (TTL) deve ser fixado em 15 ou menos.
- Como as mensagens podem agora ser multicast IP, os membros podem receber mensagens que não serão relevantes ou são duplicatas. Filtragem apropriada precisa de ser realizada.
- Grupos de serviços pode compreender até 32 web de cache e 32 roteadores.
- Todos os web de cache em um cluster devem ser configurados para se comunicar com todos os roteadores que servem o cluster;
- O endereço de Multicast deve ser de 224.0.0.0 a 239.255.255.255.

**NTP (Network Time Protocol)**

A função do NTP é manter o horário dos equipamentos da rede sincronizados, uma vez que a falta de sincronismo pode causar uma série de problemas, como, por exemplo, receber a resposta de um determinado aplicativo mesmo antes de tê-lo enviado. Uma série de mecanismos de segurança dependem do sincronismo de horário para funcionar adequadamente. Imagine o servidor que hospeda os certificados expirados de uma CA (Certificate Authority) ficar com horário atrasado.

O funcionamento do NTP é bem simples, uma vez que a estação cliente faz a requisição de hora para o servidor NTP. Por outro lado, o cliente calcula o tempo de resposta dessa requisição e consegue determinar qual a hora correta do servidor que passa a ser utilizado como tempo real. Os elementos de rede, normalmente fazem 6 requisições por hora, ou seja, a cada 10 minutos para ajustar o relógio (hora, minuto, segundo, milissegundo) do cliente.

Diversos países possuem entidades que são responsáveis para enviar a hora correta. No Brasil essa responsabilidade é do [**Observatório Nacional**](http://pcdsh01.on.br/HoraLegalBrasileira.asp) que, em parceria com o [**NIC.br**](http://nic.br/), distribuem gratuitamente (via Internet), através do [**NTP.br**](http://www.ntp.br/), a hora certa no Brasil. Abaixo encontra-se a lista de servidores NTP que se pode utilizar:

- a.st1.ntp.br
- b.st1.ntp.br
- c.st1.ntp.br
- d.st1.ntp.br
- a.ntp.br
- b.ntp.br
- c.ntp.br
- gps.ntp.br
- pool.ntp.br

**O Projeto NTP.br**

O acordo entre o ON (Observatório Nacional) e o NIC.br

O projeto **NTP.br** tem por objetivo oferecer condições para que os servidores Internet no Brasil estejam sincronizados com a **Horal Legal Brasileira**. Para isso foi firmado um acordo entre o Observatório Nacional (ON) e o NIC.br.

O ON tem como atribuição legal a geração, conservação e disseminação da Hora Legal Brasileira. Rastreado ao _**Bureau International des Poids et Mesures**_ (BIPM), na França, participa do Tempo Universal Coordenado (TUC ou UTC), juntamente com os órgãos disseminadores de tempo e frequência dos demais países.

Pelos termos do acordo o ON disponibiliza, sem qualquer ônus, ao Núcleo de Informação e Coordenação do Ponto BR – NIC.br, o sincronismo à Hora Legal Brasileira, seguro, confiável, rastreável e auditável, e o NIC.br disponibiliza, sem qualquer ônus, ao ON um conjunto de equipamentos necessários à manutenção da infraestrutura de sincronismo.

A Estrutura do NTP.br

Os **servidores públicos** do NTP.br são:

- **a.ntp.br**
- **b.ntp.br**
- **c.ntp.br**

Cada um desses endereços representa um servidor duplo: duas lâminas numa _**blade**_, cada uma delas com duas placas de rede conectadas a estruturas de rede distintas (routers e switches diferentes). Ou seja, há redundância de _**hardware**_ e de conectividade, com balanceamento automático. Cada um deles está em um datacenter diferente, com ótima conexão à Internet.

Eles são alimentados por servidores primários, **também acessíveis publicamente**:

- **a.st1.ntp.br**
- **b.st1.ntp.br**
- **c.st1.ntp.br**
- **d.st1.ntp.br**

Esses, por sua vez, são sincronizados com relógios atômicos, que são de responsabilidade do Observatório Nacional.

Existe também um servidor utilizado para monitoração do sistema. É um servidor ntp sincronizado com o Sistema de Posicionamento Global (GPS). Ele também pode ser usado:

- **gps.ntp.br**

O servidor de monitoração consulta todos os servidores do NTP.br e através de seus logs são gerados gráficos que podem ser visualizados.

A figura 3 representa a estrutura do NTP.br:

![[PIC3.jpg]]