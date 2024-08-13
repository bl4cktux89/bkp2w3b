### Introdução

Um controlador de domínio (DC) é um servidor que responde a solicitações de autenticação de segurança em um domínio. É um servidor em uma rede Windows ou Unix que é responsável por permitir acesso de host para recursos disponíveis no domínio[1].

Um controlador de domínio é a peça central do serviço diretório de uma rede. Autentica os utilizadores, armazena as informações da conta de usuário e aplica a política de segurança de um domínio.

Um domínio dá acesso a outro domínio em uma relação de confiança para que um usuário logado/registrado em um domínio possa acessar recursos em outro domínio. Se o servidor que executa a função de controlador de domínio é perdido, o domínio ainda pode funcionar. Se o controlador de domínio primário não estiver disponível, o administrador pode designar um controlador de domínio alternativo para assumir a função[1].

Versões anteriores das versões atuais para Linux e Windows, tinham um controlador de domínio por domínio, que era chamado de controlador de domínio primário. Todos os outros controladores de domínio eram controladores de domínio backup ou secundários. Especificamente para o Linux, nunca existiu esta figura isolada de _**Domain Controller**_. O que existem são as funções e ferramentas do sistema operacional que fazem parte do controle de acesso e segurança, associados à programas/aplicações como o SAMBA, por exemplo [2].

No caso do Windows 2000 em diante, não existe mais um controlador de domínio porque o controlador de domínio primário e funções de controlador de domínio backup foram substituídos pelo **Active Directory**. Os controladores de domínio nesses domínios são considerados iguais, já que todos os controladores têm acesso completo à base de dados de contas armazenada em suas máquinas [1].

Se estamos falando em controlador de domínio, primeiro precisamos ter um Domain Name (nome do domínio).

Um nome de domínio é um nome de recurso da Internet que é universalmente compreendido pelos servidores da Web e organizações on-line e fornece todas as informações de destino pertinentes. Para acessar os serviços da Web de uma organização, os usuários do site devem saber o nome de domínio preciso[1].

Os nomes de domínio são usados em todo o mundo, particularmente no mundo das redes e comunicação de dados. Os pontos a seguir explicam como eles funcionam e como eles são usados:

- Os nomes de domínio têm duas partes separadas por um ponto, como uninove.br.
- Um nome de domínio pode ser usado para identificar um único endereço IP ou grupo de endereços IPs
- Um host ou organização pode usar um nome de domínio como um endereço IP alternativo porque os nomes de domínio são alfanuméricos (em oposição a todos os números), tornando-os mais fáceis de memorizar.
- Um nome de domínio é usado como parte de um **URL** para identificar um site. A parte que segue o ponto é o domínio de nível superior (**TLD -Top Level Domain**) ou o grupo ao qual pertence o nome de domínio. Por exemplo, .gov é o TLD para domínios de governo.
- O endereço IP no plano de fundo do nome de domínio é convertido em um nome de domínio alfanumérico reconhecível por um sistema conhecido como sistema de nome de domínio (DNS).

### Sistema de Nome de Domínio (DNS)

Sistema de nome de domínio (DNS) é um sistema de nomeação hierárquica compilado em um banco de dados distribuído. Esse sistema transforma nomes de domínio em endereços IP e torna possível atribuir nomes de domínio a grupos de recursos e usuários da Internet, independentemente da localização física das entidades [4].

O sistema de nomes de domínio inclui uma árvore de nomes de domínio. Cada folha, ou nó, na árvore tem zero ou mais registros de recursos, que incluem informações associadas ao nome de domínio. A árvore ainda se subdivide em zonas, começando na zona de raiz. As zonas DNS podem ter um domínio ou muitos domínios e subdomínios dependendo da autoridade administrativa delegada aos gerentes. O lado do cliente do DNS, o resolvedor DNS, é responsável por iniciar e sequenciar consultas que levam à resolução total dos recursos procurados. Essas consultas são recursivas ou não recursivas[4].

O **DNS** atribui nomes de domínio e mapeia os nomes para endereços IP designando um servidor de nomes autoritativo para cada domínio. Esses servidores são responsáveis por domínios específicos e podem atribuir os servidores de nomes autoritativos a subdomínios. Como resultado desse processo, o DNS é distribuído e tolerante a falhas.O DNS armazena uma lista de servidores de correio que aceitam e-mail para um domínio da Internet. Identificadores como etiquetas de identificação por radiofrequência, códigos de produto universais (**UPCs** - _**Universal Product Codes**_), caracteres internacionais em endereços de e-mail e nomes de host também usam DNS.

O mais importante do DNS é o fato dele manter toda a internet conectada através de nomes. Nomes de domínio, nomes de páginas, nomes de computadores e não números os endereços de IP. Mas outra importante tarefa do DNS é se auto atualizar com mudança de endereços de domínios e, mais frequentemente, a adição de novos domínios e recursos. Esta tarefa está por conta do atualizador automático do DNS que na verdade é a maneira como o DNS descobre novos domínios através da busca para outros DNS hierarquicamente superiores e a recursividade no caso de um DNS inferior passe a conhecer um novo domínio[4].

### Domínio de Nível Superior - TLD

O domínio de nível superior (**TLD - Top Level Domain**) refere-se ao último segmento de um nome de domínio ou à parte que se segue imediatamente após o símbolo "ponto". Os TLDs são classificados principalmente em duas categorias: TLDs genéricos e TLDs específicos de cada país. Exemplos de alguns dos TLDs populares incluem .com, .org, .net, .gov, .biz e .edu. A Corporação da Internet para Nomes e Números Atribuídos (ICANN - Corporation for Assigned Names and Numbers), é a entidade que coordena domínios e endereços IP para a Internet.

Historicamente, os TLDs representavam a finalidade e o tipo de domínio. Em geral, a ICANN tem sido muito rígida em relação à abertura de novos TLDs, mas em 2010 decidiu permitir a criação de vários novos TLDs genéricos, bem como TLDs para marcas comerciais específicas de empresa. Os domínios de nível superior também são conhecidos como **sufixos** de domínio.

A maioria das empresas grandes têm domínios com IPs fixo. Por outro lado, ocorre, também, de termos servidores de DNS que estão sob uma hierarquia de endereço IP os quais podem mudar a qualquer momento, por exemplo, pelo efeito do DHCP que distribui IPs dinamicamente. Como pode o domínio sob o controle do _**Domain Controller**_ ser encontrado se o seu IP muda. Nesse momento entra o **DDNS** ou **DynDNS**.

DNS dinâmico (**DDNS** ou **DynDNS**) é um mecanismo pelo qual o servidor de nomes no sistema de nomes de domínio (DNS) é atualizado automaticamente com o nome de domínio personalizado e os endereços IP sempre mudando. O método DDNS é útil no caso de endereços IP dinâmicos, onde o endereço IP é mapeado para um domínio personalizado que muda frequentemente. No entanto, no caso de um endereço IP estático mapeado para um domínio personalizado, DDNS não é necessário. Em geral, um endereço IP dinâmico é fornecido a usuários residenciais ou de pequenas empresas. Grandes empresas geralmente usam IP estático com seus nomes de domínio.

Nos primeiros dias do DNS, os bancos de dados eram pequenos e era fácil gerenciá-los manualmente. No entanto, quando o banco de dados de domínio cresceu, tornou-se difícil gerenciar e atualizar globalmente. O sistema DNS e registros de nomes de domínio são distribuídos no planeta, por isso pode levar horas para atualizar. Nesse cenário, o sistema DNS é adequado para endereços IP estáticos mapeados com domínios personalizados.

Mas problemas surgem quando o endereço IP muda com frequência. DNS dinâmico é introduzido para resolver este problema de alterações rápidas IP. Quando um nome de domínio é pesquisado, um endereço IP dinâmico mapeado com esse domínio é retornado. Este IP dinâmico é fornecido pelo provedor de serviços de Internet (**ISP**). Em um momento posterior do tempo em que o mesmo domínio é pesquisado novamente, um endereço IP diferente pode ser retornado, porque o ISP pode ter fornecido um endereço IP diferente do pool de endereços IP. Aqui, o sistema DDNS atualiza o banco de dados DNS toda vez que o IP muda, e sempre o mantém atualizado com o mapeamento de domínio-IP. Dessa forma, o mundo exterior pode acessar o nome de domínio o tempo todo sem se preocupar com as alterações de IP.

Do lado cliente, cada vez que tentamos ?conversar? com algum domínio, por exemplo uma página WEB ou um outro computador de outro domínio, uma ferramenta entra em ação para ?resolver? o nome. Esta ferramenta é o DNS Resolver (em inglês).

Um DNS Resolver, mais comumente referido como uma ferramenta de "**DNS lookup - DNS de Pesquisa**", resolve/transforma um nome de host individual para um endereço IP. Esse tipo de comando ajuda a descobrir como os serviços da Web são hospedados, como um nome de domínio é suportado e como vários dispositivos de hardware correspondem a determinados servidores e fornecedores ou a suas empresas clientes.

De certa forma, um DNS Resolver elimina um nível de abstração, retornando o endereço IP do nome de domínio fornecido. Os nomes de domínio são como coisas na Internet que podem ser hospedadas em qualquer lugar. Eles são marcadores de um projeto da Web que possui um local específico, mas o nome de domínio não especifica esse local. O endereço IP fornece muito mais informações sobre onde o hardware é que está operando o projeto da Web e que tem propriedade ou controle do espaço da Web específico. É por isso que ferramentas como DNS Resolvers são importantes na pesquisa na Internet e em tornar a Internet mais transparente para os usuários. Por exemplo, um usuário pode procurar ou "resolver" um DNS que tenha um nome de marca específico para ver se esse site é mantido pela empresa que tem ou não a marca registrada. Esse tipo de transparência também pode ajudar os usuários a evitar certos tipos de fraudes ou golpes na Internet e ajudar a tornar o comércio eletrônico mais acessível a um público mais amplo. Veja abaixo um print de tela e mostra como facilmente pergunto para a internet onde está o domínio **amazon.com.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835600/36694.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835600/36694.png)

Percebe-se facilmente que o domínio está em 174.129.240.167 além de outras informações que não cabe verificarmos agora.

### Criando um Serviço de Domain Controller no Linux

Bem, tudo que foi explicado acima é uma forma de você entender o contexto do trabalha de um controlador de domínios.

O que o _**Domain Controller**_ precisa fazer?

Como não existe um **Active Directory (AD)** (Marca registrada da Microsoft para Windows Server) para Linux, precisamos entender qual o papel, ou o conjunto de tarefas, que que um Active Directory tem ou faz.

Reduzidamente falando, o AD nada mais faz que:

- **Cadastra Usuários**
- **Cadastra Grupos**
- **Cadastra Domínios**
- **Controla o acesso a Diretórios e Arquivos**
- **Controla o acesso a impressoras e outros dispositivos**
- **Distribui diretivas/políticas de segurança**

Sorte que falei reduzidamente acima ou um fanático por Windows poderia ficar nervoso.

**De que maneira poderíamos ter isto em Linux?**

Existe o **BIND** e existe o **SAMBA**. Ambos, pela sua importância têm uma seção específica neste conjunto de estudos.

Vamos partir para a instalação em uma máquina real e, no caminho, veremos como as ?coisas? vão se encaixando.

Com a ajuda do Samba, é possível configurar o servidor Linux como um controlador de domínio. Antes de alguém pensar algo errado, não estou falando sobre um controlador de domínio primário do Active Directory (PDC) completo. Por outro lado, ele pode atuar como um controlador de domínio estilo Windows NT4. Com algumas outras ferramentas, pode-se fazer tudo o que o AD faz. Alguém poderia comentar agora: Ora, então o AD é melhor que todos porque precisam-se de várias ferramentas para fazer o que apenas um software faz. Eu respondo: Não é bem assim. Quem disse que queríamos juntar tudo num bolo só? Você gostaria de um bolo sabor morango, banana, jaca e carambola, tudo junto?

Continuando. Uma grande vantagem da configuração que estamos montando aqui é que ela oferece a capacidade de centralizar as credenciais do usuário e da máquina.

Em outras palavras, se você não precisa de um PDC completo e está procurando simplesmente centralizar o armazenamento de credenciais, só precisa da configuração do Ubuntu Server / Samba será muito mais fácil de trabalhar e economizar com um orçamento considerável.

Com isso dito, vamos começar a trabalhar. Eu quero mostrar-lhe uma parte deste enigma bastante complexo. Essa peça é uma ferramenta interativa do Samba que ajuda a configurar o arquivo **/etc/smb.conf** para sua função de servir como um controlador de domínio.

### Instalação

A primeira coisa que você deve fazer é instalar o Samba e o **winbind**. Abra uma janela de terminal e emita o seguinte comando: (Ser um superusuário ajuda muito aqui)**\#apt install samba libpam-winbind**

Um número de dependências pode ser descoberto aqui para esta instalação; permita que eles sejam instalados e esteja pronto para iniciar a configuração. Veja o print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835602/36695.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835602/36695.png)

Você pode observar acima que o samba não foi instalado. Veja a parte grifada **“Novos pacotes serão instalados**”. O fato é que eu já havia instalado o SAMBA, ele está lá! Isto não muda nada.

### Preparação

Antes de executar o samba-tool, você deve certificar-se de que seu arquivo **/etc/hosts** corretamente mapeia para um nome de domínio totalmente qualificado e o endereço IP do DC, como:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835607/36696.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835607/36696.png)

Onde estiver o “192.168.0.10” troque pelo endereço real do seu servidor Samba. Certifique-se de que o acima é editado para atender às necessidades de sua rede. Onde estiver “LuckyGavNote” coloque o hostname de sua máquina que será o servidor. Onde estiver “luckygav.net” coloque o seu domínio. Consulte detalhes sobre DNS no tópico específico para deixar a parte do DNS ok.

Para ver como estão as coisas, digite o comando abaixo:

**\#smbclient -L localhost -U%**

Veja o print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835614/36697.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835614/36697.png)

Para ver onde estão os arquivos importantes do SAMBA, use os comandos abaixo:

**\#smbd -b | grep "CONFIGFILE"**

**\#smbd -b | egrep "LOCKDIR|STATEDIR|CACHEDIR|PRIVATE_DIR"**

As saídas serão como o print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835635/36698.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835635/36698.png)

Ótimo, tudo no lugar.

Agora vamos transformar o SAMBA e, PDC (_**Primary Domain Controller**_):

Antes vamos criar um diretório para os Logons do Windows:

**\#mkdir -p /usr/samba/netlogon**

**\#chmod 775 /usr/samba/netlogon**

**Não se preocupe com a localização. Eu escolhi colocar no /usr por se tratar de tratamento de usuários.**

Altere a seção [**global**] para os dados abaixo e acrescente a seção [**netlogon**].

**[global]**

**workgroup = luckygav.net**

**netbios name = LUCKYGAVNOTE**

**server string = Samba AD**

**domain master = yes**

**domain logons = yes**

**logon script = netlogon.bat**

**security = user**

**encrypt passwords = yes**

**enable privileges = yes**

**passdb backend = tdbsam**

**preferred master = yes**

**local master = yes**

**os level = 100**

**wins support = yes**

**[netlogon]**

**comment = Servico de Logon**

**path = /usr/samba/netlogon**

**read only = yes**

**browseable = no**

Salve isto no /etc/samba/smb.conf

Restart o serviço:

**\#systemctl restart smbd nmbd**

E teste como ficou!

**\#testparm**

Verá uma tela assim:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835646/36699.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835646/36699.png)

Observe a situação acima. **Tudo ficou ok.**

Perceba que existe uma seção Departamento_X. Bem, quando instalei a primeira vez o SAMBA, para demonstrar em outro tópico a implantação de um servidor de arquivos, eu criei um diretório no disco para testes… bem, é esta aí. Olhe também a linha que fala:

**Server role: ROLE_DOMAIN_PDC**

Quer dizer que o “papel” deste servidor passou a ser _**Primary Domain Controller**_**!**!

Se não tivéssemos mudado a configuração do smb.conf o default seria tal que o papel do server seria **STAND ALONE!**

Vou dar uma limpada nos comentários do smb.conf para poder mostrar aqui como ficou tudo lá, mas primeiro vamos ver o status do Samba: Vou mostrar em duas telas para você ver tudo!!!

**\#systemctl status smbd nmbd**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835649/36700.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835649/36700.png)

Olhando para a primeira parte: O daemon **smbd** está rodando (verde) e pronto para conexões (vermelho).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835655/36701.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835655/36701.png)

Segunda parte: O daemon nmbd está rodando (verde) e o SAMBA assumiu o Domain Master Browser (ou seja, toda máquina que logar de qualquer subrede do domínio vai procurar este servidor para checar credenciais) e também assumiu o Local Master Browser (ou seja, toda máquina da mesma subrede que este servidor vai procurar este servidor para checar credenciais).

Agora vamos nos preparar para fazer testes reais. Vamos criar um usuário no Unix e no Samba.

**# adduser usuario1**

**# smbpasswd -a usuario1**

Veja o print das telas para os dois comandos. Observe no final onde usei o comando **\#pdbedit -w -L** para listar os usuários.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835659/36702.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/5/6/835659/36702.png)

Agora vamos criar uma pasta para colocar os perfis de usuários (**profiles**). Isto é importante para duas tarefas. Uma é permitir o Windows gravar os dados de logon. Se não colocarmos o Windows vai reclamar!! A outra tarefa é que podemos usar o Samba para manter o perfil do usuário no sentido de que o usuário pode logar de qualquer lugar e ele sempre vai ver o servidor com as mesmas características. (**Roaming**).

**\#mkdir -p /usr/samba/ADprofile/usuario1**

**\#chown usuario1:WORKGROUP  /usr/samba/ADprofile/usuario1**

Abaixo, algumas razões para o comando acima não funcionar.

Se o grupo não existir então crie:

**\#groupadd WORKGROUP**.

Se o usuário não está cadastrado neste grupo então faça-o com:

**\#usermod -G WORKGROUP usuario1**

Vamos editar novamente o smb.conf e colocar uma seção para os **profiles**.

Copie o conteúdo abaixo para o arquivo de configuração.

**[profiles]**

**path = /usr//samba/ADprofile**

**writeable = yes**

**browseable = no**

**create mask = 0600**

**directory mask = 0700**

**[homes]**

**valid users = %S**

**create mask = 0700**

**directory mask = 0700**

**browseable = no**

Agora vamos criar perfis de máquina. Sim os computadores (**hosts**) devem ter seus nomes (**hostnames**) cadastrados como máquina. No caso usarei um notebook com Windows 10 cujo hostname é **DESKTOP-PDG175J.**

**# useradd -d /dev/null -s /bin/false DESKTOP-PDG175J$**

**\#passwd -l DESKTOP-PDG175J$**

**# smbpasswd -m -a DESKTOP-PDG175J**

O primeiro comando anula cria este usuário/máquina e já o proíbe de usar o Shell, quer dizer, este usuário não pode fazer nada. Observe o $ em algumas posições. Esta opção força a este tipo de usuário não ter “home”. O comando do password está lá para que fique sem senha e, ao Samba estamos informando que é uma máquina.

Bem, como prometi, segue o arquivo de configuração final.

**smb.conf**

#======================= Global Settings =======================

[global]

workgroup = luckygav.net

netbios name = LUCKYGAVNOTE

server string = Samba AD

domain master = yes

domain logons = yes

logon script = netlogon.bat

security = user

encrypt passwords = yes

enable privileges = yes

passdb backend = tdbsam

preferred master = yes

local master = yes

os level = 100

wins support = yes

[netlogon]

comment = Servico de Logon

path = /var/samba/netlogon

read only = yes

browseable = no

[profiles]

path = /var/profiles

writeable = yes

browseable = no

create mask = 0600

directory mask = 0700

[homes]

valid users = %S

create mask = 0700

directory mask = 0700

browseable = no

[Departamento_X]

comment = Acesso Restrito ao Departamento X

path = /samba/Departamento_X

public = no

writable = yes

valid users =  LukeRKnife

[printers]

comment = All Printers

browseable = no

path = /var/spool/samba

printable = yes

guest ok = no

read only = yes

create mask = 0700

# Windows clients look for this share name as a source of downloadable

# printer drivers

[print$]

comment = Printer Drivers

path = /var/lib/samba/printers

browseable = yes

read only = yes

guest ok = no

- -----------------------------------------------------------------------------------------------------------

Tudo pronto!

Nas máquinas Windows você precisa ter os usuários com os mesmos nomes que criou no SAMBA.

Além disto, precisa mudar o grupo, que normalmente está escrito WORKGROUP para **“membro do domínio”**

**Algumas máquinas estarão protegidas e não poderão entrar como membro de domínio. Isto é feito no Windows Register: Se for o caso use estes novos registros e os introduza no Register;**

**[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\LanmanWorkstation\Parameters]**

**"DNSNameResolutionRequired"=dword:00000000**

**"DomainCompatibilityMode"=dword:00000001**

### Conclusão

Muito bem! Você tem um Serviço de Diretórios estável, seguro e infinitamente mais flexível e controlado. Claro você pode incluir muito mais detalhes aqui. Procure consultar os manuais e aumentar seu conhecimento a respeito. Um servidor como este pode controlar empresas grandes e você pode poupar muito investimento se optar por trabalhar com o Linux para este tipo de tarefa.