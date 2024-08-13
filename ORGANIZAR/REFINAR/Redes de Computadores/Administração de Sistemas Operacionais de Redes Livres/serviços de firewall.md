### Introdução

Para manter seus dados de rede seguros, você deve pensar em introduzir firewalls na sua rede. Este estudo fornece uma visão geral do que são firewalls e quais benefícios eles fornecem, como eles funcionam e tipos de firewall diferentes.

Um firewall é um sistema de hardware ou software (na verdade são ambos) que impede o acesso não autorizado **a, ou a partir de uma** rede (sim, trata-se de cuidar da saída de informações e da entrada de informações). Ele pode ser implementado em hardware e software, ou uma combinação de ambos, como falei. Os firewalls são frequentemente utilizados para impedir que utilizadores não autorizados da Internet acedam a redes privadas ligadas à Internet. Todos os dados que entram ou saem da intranet passam pelo firewall, que examina cada pacote e bloqueia aqueles que não atendem aos critérios de segurança especificados [1].

Geralmente, firewalls são configurados para proteger contra logins interativos não autenticados do mundo exterior. Isso ajuda a impedir que hackers façam login em máquinas em sua rede. Firewalls mais sofisticados bloqueiam o tráfego de fora para dentro, mas permitem que os usuários no interior se comuniquem um pouco mais livremente com o exterior.

Os firewalls são essenciais, pois fornecem um único ponto de bloqueio, onde a segurança e a auditoria podem ser impostas. Os firewalls oferecem uma importante função de registro e auditoria. Frequentemente, fornecem resumos ao administrador sobre que tipo/volume de tráfego foi processado através dele. Este é um benefício importante: Proporcionar este ponto de bloqueio pode servir com o mesmo propósito em sua rede que um guarda armado para assegurar suas instalações físicas [1].

Abaixo uma concepção simbólica para entender melhor qual é a posição do firewall na rede. Olhando esta figura, parece uma arquitetura (você vai entender mais para frente) “**bastion host**”, mas este posicionamento pode ser mudado para outras arquiteturas sem parecer que isto ocorreu fisicamente. O que interessa é a topologia lógica da sua rede. Através dos IPs e do direcionamento do tráfego, a topologia pode ser alterada. Não se preocupe com isto agora, você verá mais detalhadamente em seguida.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/6/9/5/869539/36670.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/6/9/5/869539/36670.png)

### Quais são os diferentes tipos de firewalls?

O Instituto Nacional de Padrões e Tecnologia (**NIST -** _**National Institute of Standards and Technology**_ **- USA**) divide firewalls em três tipos básicos:

- Filtros de pacotes
- Inspeção de estado
- Proxys

Essas três categorias, no entanto, não são mutuamente exclusivas, pois a maioria dos firewalls modernos têm uma mistura de habilidades que podem colocá-los em mais de um dos três.

Uma maneira de comparar firewalls é olhar para as camadas _**Transmission Control Protocol/Internet Protocol**_ (TCP/IP) e ver o que cada uma das camadas é capaz de examinar. As comunicações TCP/IP são compostas de quatro camadas; elas trabalham juntos para transferir dados entre hosts. Quando ocorrem transferências de dados entre redes, os dados passam da camada mais alta para as camadas intermediárias e, depois, para a camada mais baixa; cada camada adiciona mais informações. Em seguida, a camada mais baixa envia os dados acumulados através da rede física; os dados enviados, ao serem recebidos, movem-se para cima, através das camadas, até seu destino, a camada mais alta (Aplicação). Simplificando, os dados produzidos por uma camada são encapsulados em um contêiner maior pela camada abaixo dele. As quatro camadas TCP / IP, da mais alta para a mais baixa, são descritas na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/6/9/5/869581/36672.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/6/9/5/869581/36672.png)

A camada mais alta é a Camada de Aplicação (_**Application Layer**_). Nesta camada as necessidades do usuário final são preparadas para a transmissão. Por exemplo, pode ser um browser requisitando a abertura de uma página “index.html”. Protocolos típicos que trabalham nesta camada são: HTML, DNS, FTP, etc.

Na camada seguinte Camada de Transporte (_**Transport Layer**_) a organização para transmissão é feita. É como se carregassem caminhões para uma viagem com toda nossa carga arrumada. Para garantir a montagem da carga no destino, neste momento eu também número as cargas para que elas cheguem na mesma sequência. Imagine, a bagunça que seria se chegasse antes o caminhão das roupas, talheres e louças e, por último, os caminhões dos móveis (isto é só um exemplo). Os protocolos típicos desta camada são o TCP e o UDP.

A penúltima camada, Camada de Internet (_**Internet Layer**_), também conhecida como **camada de rede**, é o direcionamento da carga, ou solicitação para o endereço de destino correto. No caso de nosso transporte de caminhões, seria como se eu desse para os motoristas o endereço de entrega. O protocolo mais usado nesta camada seria o IP.

E, por fim, a última camada, a Camada Física (_**Physical Network Layer**_), esta camada corresponde a colocar os caminhões na estrada correta para o transporte, depois o acesso à cidade destino, e as ruas até a residência onde a mudança deveria ser entregue. Aqui são utilizados os protocolos Ethernet, ATM, Novell, etc.

O firewall permanece um componente vital em qualquer arquitetura de segurança de rede, e as organizações de hoje têm vários tipos para escolher. É essencial que os profissionais de TI identifiquem o tipo de firewall que melhor atenda às necessidades de segurança da rede da organização.

Uma vez selecionado, uma das perguntas-chave que molda uma estratégia de proteção é "Onde o firewall deve ser colocado?" Existem três topologias de firewall comuns: as arquiteturas: bastion host, “**screened subnet”** e **dual firewall** ou **multi homed**. A segurança da empresa depende da escolha da topologia correta do firewall.

### Bastion Host

A primeira e mais básica opção é o uso de um bastion host. Neste cenário (mostrado na figura abaixo), o firewall é colocado entre a Internet e a rede protegida. Filtra todo o tráfego que entra ou sai da rede.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835380/36674.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835380/36674.png)

A topologia bastion host é bem apropriada para redes relativamente simples (por exemplo aquelas que não oferecem nenhum serviço público na Internet.) O fator chave a manter-se em mente é que oferece somente um único limite. Uma vez que alguém consegue penetrar essa fronteira, ganha acesso irrestrito (pelo menos a partir de uma perspectiva de proteção de perímetro) à rede protegida. Isso pode ser aceitável se você estiver apenas usando o firewall para proteger uma rede corporativa que é usada principalmente para navegar na Internet, mas provavelmente não é suficiente se você hospedar um site ou servidor de e-mail.

### Screened subnet

A segunda arquitetura, o uso de uma sub-rede filtrada, oferece vantagens adicionais sobre a abordagem bastion host. Essa arquitetura usa um único firewall com três placas de rede (comumente referido como um firewall triplo). Um exemplo desta topologia é mostrado na figura abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/4/835405/36676.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/4/835405/36676.png)

A sub-rede exibida fornece uma solução que permite que as organizações ofereçam serviços de forma segura aos usuários da Internet.

Todos os servidores que hospedam serviços públicos são colocados na Zona Desmilitarizada (**DMZ -** _**Demilitarized Zone**_), que é separada da Internet e da rede confiável pelo firewall. Portanto, se um usuário mal-intencionado consegue comprometer o firewall, ele não tem acesso à Intranet (desde que o firewall esteja configurado corretamente).

### Dual Firewalls

A opção mais segura (e mais cara) é implementar uma sub-rede selecionada usando dois firewalls. Neste caso, a **DMZ** (_**Demilitarized Zone**_) é colocada entre os dois firewalls, como mostrado na figura abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/5/835581/36678.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/5/835581/36678.png)

O uso de dois firewalls ainda permite que a organização ofereça serviços aos usuários da Internet através do uso de uma DMZ, mas fornece uma camada adicional de proteção. É muito comum para os arquitetos de segurança implementar esse esquema usando a tecnologia de firewall de dois fornecedores diferentes. Isso fornece um nível adicional de segurança no caso de um indivíduo mal-intencionado descobrir uma vulnerabilidade explorável específica do software.

High-end firewalls permitem algumas variações sobre estes temas também. Embora os modelos de firewall básicos geralmente tenham um limite de três interfaces, firewalls de alto nível permitem um grande número de interfaces físicas e virtuais. Por exemplo, o firewall **Sidewinder G2** da **Secure Computing** permite até 20 interfaces físicas. Interfaces virtuais adicionais podem ser adicionadas através do uso de marcação **VLAN** nas interfaces físicas. O que isso significa para você? Com um maior número de interfaces, você pode implementar muitas zonas de segurança diferentes em sua rede. Por exemplo, você pode ter a seguinte configuração de interface:

- Zona 1: Internet
- Zona 2: Estações de trabalho restritas
- Zona 3: Estações de trabalho gerais
- Zona 4: DMZ pública
- Zona 5: DMZ Interna
- Zona 6: Servidores principais

Este tipo de arquitetura permite que você tome qualquer uma das três topologias descritas acima e adicione um excelente grau de flexibilidade.

Isso é um breve sumário sobre arquiteturas de firewall. Agora que você está familiarizado com os conceitos básicos, você deve ser capaz de selecionar uma arquitetura apropriada para uso em várias situações.

Lembre-se de que as configurações de firewall mudam rapidamente e com frequência, por isso é difícil manter-se a rotina de manutenção do firewall. A atividade de firewall, portanto, deve ser continuamente auditada para ajudar a manter a rede protegida contra ameaças em constante evolução.

### Firewalls de camada de rede

Os firewalls de camada de rede geralmente tomam suas decisões com base no endereço de origem, endereço de destino e portas em pacotes IP individuais. Estes são os mais comuns. Um roteador simples é o firewall de camada de rede tradicional, uma vez que não é capaz de tomar decisões particularmente complicadas sobre o que um pacote está realmente falando ou de onde ele realmente veio [1].

Uma importante distinção que muitos firewalls de camada de rede possuem é que eles encaminham o tráfego diretamente através deles, o que significa que para usar um, você precisa ter um bloco de endereço IP validamente atribuído ou um bloco de endereço de Internet privado. Firewalls de camada de rede tendem a ser muito rápidos e quase transparente para seus usuários.

### Firewalls de camada de aplicação

Os firewalls de camada de aplicação são hosts que executam servidores proxy, que não permitem nenhum tráfego direto entre redes, e executam registros e exames elaborados de tráfego que passam por eles. Desde que aplicações proxy são simplesmente softwares executados no firewall, é um bom lugar para fazer log e controlar de acesso. Os firewalls de camada de aplicação podem ser usados como tradutores de endereços de rede, uma vez que o tráfego passa de um lado para o outro depois de ter passado por um aplicativo que efetivamente máscara a origem da conexão iniciadora [1].

No entanto, firewalls de rede que não são percebidos não podem defender corretamente aplicativos. Como explica Michael Cobb [1], os firewalls de camada de aplicativo oferecem segurança em Layer 7 em um nível mais detalhado e podem até ajudar as organizações a obter mais recursos dos dispositivos de rede existentes.

Em alguns casos, ter um aplicativo no caminho pode afetar o desempenho e tornar o firewall menos transparente. Os firewalls mais antigos da camada de aplicação que ainda estão em uso não são particularmente transparentes para os usuários finais e podem exigir algum treinamento do usuário. No entanto, firewalls de camada de aplicação mais modernos são muitas vezes totalmente transparentes. Os firewalls de camada de aplicação tendem a fornecer relatórios de auditoria mais detalhados e tendem a impor modelos de segurança mais conservadores do que os firewalls de camada de rede.

Os firewalls futuros provavelmente combinarão algumas características de firewalls de camada de rede e firewalls de camada de aplicativo. É provável que os firewalls de camada de rede se tornem cada vez mais conscientes da informação passando por eles, e firewalls de camada de aplicativo já se tornaram mais transparentes. O resultado final será um tipo de sistema rápido de rastreamento de pacotes que registra e verifica os dados à medida que passa.

### Firewalls de proxy

Os firewalls de proxy oferecem mais segurança do que outros tipos de firewalls, mas à custa da velocidade e da funcionalidade, pois eles podem limitar quais aplicativos a rede suporta [1].

Por que eles são mais seguros? Ao contrário dos firewalls stateful ou firewalls de camada de aplicativo, que permitem ou bloqueiam pacotes de rede passarem **para, ou de,** uma rede protegida, o tráfego não flui através de um proxy. Em vez disso, os computadores estabelecem uma conexão com o proxy, que serve como um intermediário, e iniciar uma nova conexão de rede em nome do pedido. Isso evita conexões diretas entre sistemas em ambos os lados do firewall e torna mais difícil para um invasor descobrir onde a rede está, porque eles não recebem pacotes criados diretamente pelo sistema de destino.

Os firewalls de proxy também fornecem análises de segurança abrangentes e compatíveis com protocolos para os protocolos que os suportam. Isso lhes permite tomar melhores decisões de segurança do que os produtos que se concentram puramente em informações de cabeçalho de pacote.

### Usando um Firewall no Linux

O kernel do Linux inclui o subsistema chamado **Netfilter**, que é usado para manipular ou decidir o destino do tráfego de rede direcionado para ou através de seu servidor. Todas as modernas soluções de firewall Linux utilizam este sistema para filtragem de pacotes. Veja abaixo um comando para criar **NAT (**_**Network Address Translation**_**)** usando o filtro de pacotes:

**# iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE**

Isto é só para você ter uma ideia de como filtros de pacotes (NetFilter) são montados.

O sistema de filtragem de pacotes do kernel seria de pouca utilidade para administradores sem uma interface de usuário para gerenciá-lo. Esta é a finalidade do **iptables**. Quando um pacote chega ao seu servidor, ele será transferido para o subsistema **Netfilter** para aceitação, manipulação ou rejeição com base nas regras fornecidas a ele pelo usuário através do iptables. Assim, iptables é tudo que você precisa para gerenciar seu firewall, se você estiver familiarizado com ele, mas muitos frontends estão disponíveis para simplificar a tarefa. Vamos ver um deles aqui e implementá-lo.

### Ufw - Firewall não complicado

A ferramenta de configuração de firewall mais usada, e até padrão, para o **Ubuntu** é **ufw Uncomplicated Firewall**. Ele foi desenvolvido para agilizar a configuração do firewall pelo **iptables**, o **ufw** fornece uma maneira fácil de criar um firewall baseado em host IPv4 ou IPv6.

Ufw por padrão é inicialmente desativado. Você pode ver na página do manual ufw (man ufw):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835226/36679.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835226/36679.png)

Ou seja, o ufw não se destina a fornecer uma funcionalidade de firewall completa através de sua interface de comando, mas fornece uma maneira fácil de adicionar ou remover regras simples. Atualmente, é usado principalmente para firewalls baseados em host.

Vamos ver como usar o **ufw**. Todos os exemplos, quando for pertinente, mostrarei a tela com resposta do sistema ao comando.

Primeiro, o **ufw** precisa ser ativado. Em um prompt de terminal, digite:

  **\#ufw enable**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835229/36680.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835229/36680.png)

**Exemplos de comandos do Firewall pelo uwf.**

Para abrir uma porta (SSH por exemplo):

   **\#ufw allow 22**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835234/36681.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835234/36681.png)

As regras também podem ser adicionadas usando um formato enumerado:

 **\#ufw insert 1 allow 80**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835238/36682.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/2/835238/36682.png)

Da mesma forma, para fechar uma porta aberta:

**\#ufw deny 22**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835317/36683.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/3/835317/36683.png)

Para remover uma regra, use **delete** seguido pela regra:

 **\#ufw delete deny 22**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839511/36684.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839511/36684.jpg)

Podemos também usar aquelas regras **enumeradas** e usar o número que demos para a regra de forma a ela ser referendada sem repetir toda a regra. Lembra a regra **ufw inset 1 allow 80**? Por usar o seguinte comando para excluí-la:

**\#ufw delete 1** (neste caso, para garantir que não errei, ele pede confirmação)

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839513/36685.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839513/36685.jpg)

Também é possível permitir o acesso de hosts ou redes específicas a uma porta. O exemplo a seguir permite o acesso pelo SSH do host 192.168.1.23 a qualquer endereço IP neste host:

**\#ufw allow proto tcp from 192.168.1.23 to any port 22**

No lugar de você colocar apenas o IP de uma máquina, pode fazer referência a uma rede completa. Substitua **192.168.1.23** por **192.168.1.0/24** para permitir o acesso por SSH a partir da sub-rede inteira.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839515/36686.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839515/36686.jpg)

Adicionar a opção **--dry-run** ao comando ufw irá produzir as regras resultantes, mas **não** as aplicará. Este comando mostra o que está previsto por regras no filtro de pacotes para a permissão **http**. Por exemplo, o resultado abaixo (regras) é o que seria aplicado se eu abrisse a porta HTTP:

**\#ufw --dry-run allow http**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839516/36687.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839516/36687.jpg)

Continuando...

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839518/36688.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839518/36688.jpg)

Ufw pode ser desativado por:

**\#ufw disable**

Para ver o status do firewall, digite:

  **\#ufw status**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839519/36689.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839519/36689.jpg)

E para obter informações mais detalhadas sobre o status, use:

  **\#ufw status verbose**

Para ver o formato enumerado:

**\#ufw status numbered**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839522/36690.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839522/36690.jpg)

Se a porta que você deseja abrir ou fechar estiver definida em /etc/services pelo nome do serviço, você pode usar o nome do serviço em vez do número. Nos exemplos acima, substitua **22** por **ssh**.

**\#ufw allow ssh**

Aplicativos que abrem portas podem incluir um perfil ufw, que detalha as portas necessárias para o aplicativo funcionar corretamente. Os perfis são mantidos em **/etc/ufw/applications.d** e podem ser editados se as portas padrão tiverem sido alteradas.

Para ver quais aplicativos instalaram um perfil, digite o seguinte em um terminal:

**\#ufw app list**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839524/36691.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839524/36691.jpg)

Semelhante a permitir o tráfego para uma porta, podemos usar o perfil do aplicativo como abaixo:

**\#ufw allow Samba**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839528/36692.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839528/36692.jpg)

Não há necessidade de especificar o protocolo para a aplicação, porque essa informação é detalhada no perfil. Além disso, observe que o nome do aplicativo substitui o número da porta.

Para ver detalhes sobre quais portas, protocolos, etc., são definidos para um aplicativo, digite:

  **\#ufw app info Samba**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839530/36693.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/5/839530/36693.jpg)

Nem todos os aplicativos que exigem a abertura de uma porta de rede vêm com seu perfis **ufw**, mas se você tiver instalado um aplicativo e quiser que o arquivo seja incluído no pacote, por favor, registre um bug no pacote no launchpad ( **https://bugs.launchpad.net/ubuntu/**).

**ubuntu-bug nome_do_pacote**

### Conclusão

Podemos usar muitos tipos de firewalls em nossa rede, mas o importante é saber qual o mais adequado. Importa entender o que queremos filtrar e porque, além disto, precisamos perceber quais as limitações que são forçadas pelo uso do firewall. Também podemos concluir que o Linux pode ser bem controlado com um filtro de pacotes implementado num modelo baseado em host. Aplicamos o **UFW** e pode-se ver como foi simples e útil.