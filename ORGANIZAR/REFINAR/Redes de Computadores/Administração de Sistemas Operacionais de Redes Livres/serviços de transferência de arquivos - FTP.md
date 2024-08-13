### Introdução

Antes de mais nada devemos explorar o sistema de arquivo do Linux para melhor entender como podemos transportar dados de arquivos remotamente.

Como o Windows, um sistema operacional tipo Unix, como o Linux, organiza seus arquivos na chamada estrutura hierárquica de diretórios. Isso significa que eles são organizados em um padrão de árvore de diretórios (às vezes chamados de pastas em outros sistemas), que comportam arquivos e outros diretórios. O primeiro diretório no sistema de arquivos é chamado de diretório raiz. O diretório raiz contém arquivos e subdiretórios, que contêm mais arquivos e subdiretórios e assim por diante e assim por diante.

Observe que, ao contrário do Windows, que possui uma sistema de árvore que separa os arquivos para cada dispositivo de armazenamento, os sistemas como Unix e como o Linux, sempre têm um único sistema de árvores de arquivos, independentemente de como muitas unidades ou dispositivos de armazenamento são conectados ao computador. Os dispositivos de armazenamento são anexados, ou mais corretamente, montados, em vários pontos da árvore, de acordo com os caprichos do administrador de sistema, a pessoa (ou pessoas) responsável pela manutenção do sistema [1].

### File System

Existe uma confusão entre o ‘file system’ que rege a maneira como os diretórios e arquivos são armazenados em termos de hierarquia posicional e o ‘file system’ que é a forma lógica de armazenar dados em dispositivos de armazenamento.

Sistemas de arquivos são uma das coisas que qualquer novato de Linux deve se familiarizar. No mundo da Microsoft você nunca precisa realmente se preocupar, o padrão sendo NTFS. No entanto, o Linux sendo construído em um mundo de código aberto e opiniões diferentes, não é limitado dessa forma e, portanto, o usuário deve ter uma compreensão do que é um sistema de arquivos e como ele afeta o computador.

No núcleo de um computador, é tudo 1s (uns) e 0s (zeros), mas a organização desses dados não é tão simples. Um bit é um 1 ou um 0, um byte é composto de 8 bits, um kilobyte é 1024 (ou seja, 2 ^ 10) bytes, um megabyte é 1024 kilobytes e assim por diante. Todos esses bits e bytes são permanentemente armazenados em um disco rígido. Um disco rígido armazena todos os seus dados, e, a qualquer momento que você salvar um arquivo, você está escrevendo milhares de 1s e 0s para um disco metálico, alterando as propriedades magnéticas que podem ser lidas mais tarde como 1 ou 0. Há tantos dados em um disco rígido que tem que haver alguma maneira de organizá-lo, como uma biblioteca de livros e as gavetas antigas de cartão que indexam todos eles. Sem o índice, nós estaríamos perdidos.

As bibliotecas, em sua maioria, usam o sistema decimal Dewey para organizar seus livros, mas existem outros sistemas para fazê-lo, nenhum dos quais alcançou a mesma fama que a invenção de Dewey. Os sistemas de arquivos são da mesma maneira. Os que a maioria dos usuários estão cientes são aqueles que o Windows usa, os sistemas vFat ou NTFS, estes são os sistemas de arquivos padrão do Windows. Existem vários atributos diferentes que são necessários na definição de sistemas de arquivos, que incluem seu tamanho máximo de arquivo, tamanho máximo de partição, se eles jornalizam ou não.  Estes aspectos que fazem diferença na velocidade com que os arquivos podem ser copiados, espelhados e transferidos[2].

A coisa mais importante sobre a memória, no caso da maioria dos arquivos, dos discos, é: não apenas ser capaz de armazenar informações, mas ser capaz de encontrá-lo mais tarde. Imagine armazenar um prego de ferro magnetizado em uma gaveta de 1,6 milhão de pregos idênticos e, assim, você terá alguma ideia de quanta dificuldade seu computador teria se não usasse uma maneira muito metódica de arquivar e recuperar sua informação[2].

Baseado nestes conjuntos de informações muito básicas de o que envolve o tratamento de arquivo, podemos começar a falar na transferência de arquivos. Portanto, vamos falar de FTP!

### O que é FTP?

FTP é abreviação de _**File Transfer Protocol**_ (Protocolo de Transferência de Arquivos). Um protocolo é um conjunto de regras que os computadores em rede usam para falar uns com os outros. E FTP é a linguagem que os computadores em uma rede TCP / IP (como a Internet) usam para transferir arquivos para e entre eles.Você provavelmente já encontrou FTP lá fora, na net. Você já baixou uma nova compilação do Firefox ou copiou arquivos MP3s do servidor pessoal de algum amigo na Alemanha ou, na Etiópia? Então você provavelmente já usou FTP sem mesmo saber. Hoje navegadores (browsers, como Internet Explorer, Chrome, Firefox) da web permitem que você baixe arquivos via FTP a partir da janela do navegador. É muito conveniente, e é ótimo para aquelas vezes que você precisa para baixar um arquivo ou dois, mas o método de download do navegador não oferece muito em termos de flexibilidade. Você não pode carregar, forçar um determinado modo de transferência ou fazer perguntas ao servidor. Nem sequer preciso falar aqui na questão de segurança. Mas se você estiver fazendo qualquer tipo de desenvolvimento web, ou mesmo, trabalhando com volumes grandes de arquivos, você precisa de toda essa funcionalidade.

A melhor maneira de fazer transferências de arquivos é com um cliente FTP de boa qualidade. Você usa um cliente FTP para efetuar login em um servidor FTP, navegar na estrutura de pastas do servidor e trocar arquivos. Isso, praticamente todos os clientes FTP podem fazer. Ao contrário navegadores da Web, clientes FTP são feitos sob medida para tais deveres. Os mais recentes editores da Web (aqueles usados para desenvolver páginas HTML), como o Dreamweaver e o RapidWeaver, possuem funções de FTP embutidas. No que diz respeito aos clientes autônomos de FTP, existem literalmente centenas à disposição. Alguns são gratuitos e alguns são mais caros do que um computador.

Iremos analisar em profundidade as vantagens de usar um cliente FTP nas páginas que se seguem, mas primeiro, vamos analisar exatamente como funciona uma sessão FTP.

### Logando no Servidor FTP

A conexão a um servidor FTP é muito semelhante à conexão com praticamente qualquer outro servidor na Web. Quando inicia uma sessão/acesso na sua conta do Gmail ou num sistema online de compras seguro (como o da Amazon.com), tem de fornecer um endereço de servidor, um nome de usuário e uma senha para poder trocar informações com o servidor.Vamos dar uma olhada em um exemplo de login definido para um servidor FTP. Vamos usar o servidor que é mantido pelo BIND9 aqui no meu computador.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852193/form-obj-0.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852193/form-obj-0.png)

**Ops!!!!! Nome ou serviço desconhecido!!!**

Simplesmente não há um servidor FTP na minha máquina. Bom, isto é uma ótima oportunidade. Vamos instalar um servidor FTP.

Primeiro observe que mesmo não havendo o servidor, o **comando ftp** mostrou-se existente. Isto quer dizer que o cliente FTP está presente. Eu não fiz nada para isto, então aprenda isto: **O cliente FTP vem nativo na maioria das distribuições Linux.**

### Instalando o Servidor FTP

**Vsftpd** é um **daemon*** FTP disponível no Ubuntu. É fácil de instalar, configurar e manter.

**DAEMON**

**Um daemon é um tipo de programa em sistemas operacionais semelhantes a Unix que funciona de forma discreta em segundo plano/background, em vez de estar sob o controle direto de um usuário, esperando para ser ativado pela ocorrência de um evento ou condição específica[3].**

Para instalar **vsftpd** você pode executar o seguinte comando:

**\#apt install vsftpd**

Por padrão, o **vsftpd** não está configurado para permitir o download anônimo. Se você deseja ativar o download anônimo edite **/etc/vsftpd.conf**.

Veja uma parte do arquivo de configuração.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852194/form-obj-0-1-.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852194/form-obj-0-1-.png)

Vamos deixar o acesso anônimo proibido, como fica claro na opção abaixo.

# Allow anonymous FTP? (Disabled by default).

**anonymous_enable=NO**

Durante a instalação, um usuário ftp é criado com um diretório home **/srv/ftp**. Este é o diretório FTP padrão.

Se você deseja alterar esse local, para /**srv/files/ftp**, por exemplo, basta criar um diretório em outro local e alterar o diretório inicial do usuário ftp:

**\#mkdir /srv/files/ftp****\#usermod -d /srv/files/ftp ftp**Depois de fazer a alteração, reinicie o vsftpd:**\#restart vsftpd**

**Ou**

**\#service vsftpd restart**

Finalmente, copie todos os arquivos e diretórios que você gostaria de disponibilizar através de FTP anônimo para /srv/files/ftp, ou /srv/ftp se você quiser usar o padrão. Vamos entrar no subdiretório /usr/ftp e criar alguns diretórios e arquivos. Veja no print abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852197/form-obj-0.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852197/form-obj-0.png)

Por padrão, o **vsftpd** é configurado para autenticar os usuários do sistema e permitir que eles baixem arquivos. Se você quiser que os usuários possam fazer **upload** de arquivos, edite **/etc/vsftpd.conf**:**write_enable = YES**Agora reinicie **vsftpd**:**\#restart vsftpd**

**ou**

**\#service vsftpd restart**

Agora, quando os usuários do sistema _**logarem**_ no FTP eles vão entrar em seus diretórios home onde eles podem baixar, fazer upload, criar diretórios, etcDa mesma forma, por padrão, usuários anônimos não podem fazer **upload** de arquivos para o servidor FTP. Para alterar essa configuração, você deve descomentar a seguinte linha e reiniciar **vsftpd**:**anon_upload_enable = YES**

**FTP ANÔNIMO**

A ativação do **upload** FTP anônimo pode ser um **risco extremo** para a segurança. É melhor não ativar o **upload** anônimo em servidores acessados diretamente da Internet.

O arquivo de configuração consiste em muitos parâmetros de configuração. As informações sobre cada parâmetro estão disponíveis no arquivo de configuração. Como alternativa, você pode consultar a página man, **man 5 vsftpd.conf** para obter detalhes de cada parâmetro.

Existem opções no **/etc/vsftpd.conf** para ajudar a tornar o **vsftpd** mais seguro. Por exemplo, os usuários podem ser limitados a seus diretórios pessoais por descomente:

**chroot_local_user = YES**Você também pode limitar uma lista específica de usuários apenas a seus diretórios base:**chroot_list_enable = YES****chroot_list_file = / etc / vsftpd.chroot_list**Depois de descomentar as opções acima, crie uma lista com o nome de arquivo  **/etc/vsftpd.chroot_list** contendo uma lista de usuários. Um usuário por linha. Em seguida, reinicie **vsftpd**:**\#restart vsftpd**

**Ou**

**\#service vsftpd restart**

Além disso, o arquivo /etc/ftpusers é uma lista de usuários que são de acesso FTP não permitido. A lista padrão inclui root, daemon, nobody, etc (carinhas típicos de ataques!!). Para desativar o acesso FTP para usuários adicionais basta incluí-los na lista.FTP também pode ser criptografado usando FTPS. Diferente de SFTP, FTPS é FTP sobre _**Secure Socket Layer**_ (SSL). SFTP é um FTP como sessão sobre uma conexão SSH criptografada. Uma grande diferença é que os usuários do SFTP precisam ter uma conta shell no sistema. Fornecer a todos os usuários um login shell pode não ser ideal para alguns ambientes, como um host compartilhado. No entanto, é possível restringir essas contas apenas para SFTP e desativar a interação com o shell. Consulte sites sobre o OpenSSH-Server para obter mais informações.Para configurar o FTPS, edite /etc/vsftpd.conf e, na parte inferior, adicione:**ssl_enable = yes**Além disso, observe as opções relacionadas ao certificado e à chave:**rsa_cert_file = /etc/ssl/certs/ssl-cert-snakeoil.pem****rsa_private_key_file = /etc/ssl/private/ssl-cert-snakeoil.key**Por padrão, essas opções são definidas para o certificado e a chave fornecidos pelo pacote ssl-cert. Em um ambiente de produção, estes devem ser substituídos por um certificado e uma chave gerados para o host específico. Para obter mais informações sobre certificados, consulte Certificados nos sites especializados.Agora, reinicie o **vsftpd** e os usuários não-anônimos serão forçados a usar o FTPS:**\#restart vsftpd**

**Ou**

**\#service vsftpd restart**

Vamos voltar ao acesso em nosso servidor. Vamos tentar novamente.

**$ ftp LuckyGavNote login:luckygav pass:********* port:20**

A primeira parte no exemplo acima, o endereço do site, é simplesmente o endereço do servidor FTP ao qual estou conectando. Aqui usei o nome da minha máquina, pois acabamos de fazer a instalação do **vsftpd**. Se fosse um site de ftp, apareceria “ftp" no prefixo do URL o identifica como um servidor FTP. Muito simples até agora. A segunda e terceira partes são meu nome de usuário e senha, respectivamente. Neste caso particular, eu já sou o administrador do servidor então não preciso configurar uma conta de login para mim no servidor. Mesmo se eu não tivesse uma conta de logon, eu ainda poderia ser capaz de obter acesso ao servidor, registrando anonimamente. Vamos falar nisso um pouco mais tarde.

A última parte do login de exemplo é o número da porta que estou conectando no servidor. Uma porta é melhor visualizada como uma pequena porta no servidor. A maioria dos servidores na web tem uma infinidade de tais portas, cada uma com seu próprio propósito. Cada número de porta é dedicado a um aplicativo correspondente no servidor e o tráfego destinado a um aplicativo (como um servidor FTP ou servidor web) passa pela porta dedicada do aplicativo. Cada porta manipula um tipo específico de transação entre o servidor e o cliente. Por exemplo, o protocolo FTP é processado pelas portas 20 e 21 por predefinição. As solicitações HTTP (o protocolo usado para exibir páginas da Web para um navegador) são tratadas pela porta 80.

Muitas vezes, o número da porta será anexado ao final do endereço da Web do servidor, separados por dois pontos, como este:

**ftp.uninove.br:21**

Não é importante que você saiba cada única porta TCP/IP para cada aplicativo de internet em todo lugar, mas você tem que ser capaz de reconhecer um número de porta quando você vê um. Isso se torna especialmente crítico quando você está se conectando a servidores que encaminham conexões de FTP para outras portas mais obscuras.Este dilema traz à tona a questão às vezes confusa de FTP passivo versus FTP ativo, dois modos diferentes de transferência de dados entre um cliente e um servidor. O qual está sendo usado depende de como os firewalls do cliente e do servidor estão configurados. Uma vez que este problema está além do escopo deste tópico, vou apontá-lo para uma discussão detalhada do ativo versus passivo FTP em um tópico específico de segurança. Portanto, não fique alarmado se você notar que sua conexão FTP está saltando para a porta 1410 de repente - isso representa apenas seus dados sendo roteados via FTP passivo.

Vamos ver abaixo como foi o nosso acesso. Observem que, após autenticado, o usuário pode fazer o download (**get**) do arquivo “arquivo1” e salvou em sua “home” com o nome de Novo_arquivo1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/2/852207/36740.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/2/852207/36740.png)

Veja, acima, como o servidor FTP (**vsftpd**) demonstra onde é o local e o remoto, explica que será pelo método passivo, transferência binária com um total de 28 bytes e ainda expõe a resposta do cliente dizendo que recebeu 28 bytes em menos que 1 centésimo de segundos na velocidade média de aproximadamente 223 MB/s (Duzentos e vinte e três megabytes por segundo).

Observe agora no novo print abaixo o que eu fiz. Primeira coisa foi mudar a forma de transferência para texto. Não sei porque alguém faria isto, mas observe que com o comando **ASCII** (este comando é a mesma palavra que designa _**American Standard Code for Information Interchange**_ - Um dos maiores acertos da sociedade da computação que permitiu o desenvolvimento mundial rápido de computadores, comunicações, etc.) forçamos o server a transmitir em texto. Aproveite e perceba que está em destaque o **AS** no comando acima mencionado. Isto é uma forma de falar que o alias do comando é este, ou seja, só precisa digitar “**as**”. Verifique no final da transferência que a velocidade caiu para praticamente a metade.

Esta é uma diferença importante em relação ao modo binário e texto. Você costuma ver isto quando compra um super veloz SSD (Disco em estado sólido) para melhorar a performance de seu computador e quando faz os primeiros testes fica um pouco decepcionado. O problema é exatamente este - A transferência que você precisa medir precisa ser em binário e a maioria dos mecanismos para mover ou copiar arquivos do Windows, por exemplo, se dá no modo ASCII. Aqui neste tópico não vou poder explicar, mas só para você ter uma ideia, se você transmite o número 100.000 (cem mil) em ASCII, vai precisar transferir 6 bytes, mas se usar binário, só precisará usar 4 bytes. Simples assim.

Vamos aproveitar o mesmo print e perceber mais algumas coisas interessantes. Veja como tentei apenas colocar o arquivo fonte/origem no **get**, imaginando que o FTP server iria automaticamente colocar o arquivo como o mesmo nome da origem e no diretório corrente/default. Veja que o FTP não “quis” fazê-lo. Na verdade, ele assume que é o mesmo caminho e fica um tanto atrapalhado. Outra tentativa foi colocar apenas o nome local do diretório, achando que o FTP usaria o mesmo nome original. Também não aceitou.

Agora vamos fazer um upload, isto é, vamos colocar um arquivo no servidor (**foreign**) em FTP chamados o servidor de “estrangeiro”, traduzindo a palavra grifada. Veja abaixo no print, vamos colocar um arquivo chamado “Teste_upload” no servidor. Veja primeiro uma tentativa frustrada.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852198/form-obj-0-1-.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/1/852198/form-obj-0-1-.png)

Na verdade, se você lembrar, havíamos deixado a opção de upload proibida, por questões de segurança. Bem, só precisamos fazer a operação abaixo e testar novamente.

**write_enable = YES**

Agora reinicie **vsftpd**:**\#restart vsftpd**

**Ou**

**\#service vsftpd restart**

Agora podemos repetir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/2/852201/form-obj-0.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/2/852201/form-obj-0.png)

**Perfeito!!**

Praticamente todos os comandos do sistema operacional Linux que tratam de arquivos e navegação entre diretórios funcionam. São vários e você pode testá-los.

### Acesso Anônimo ao FTP

Muitos servidores públicos na Internet permitem que os usuários façam login e baixem arquivos via FTP, conectando-se anonimamente. Esta é uma prática muito comum no mundo dos softwares de código aberto e livremente distribuídos.

Quando você se conecta anonimamente a um servidor FTP, você não é realmente anônimo no sentido mais verdadeiro. Na maioria das vezes, é necessário inserir "anonimous" como seu nome de usuário e seu endereço de e-mail como sua senha. Este é um gesto de cortesia em relação aos administradores de servidores, para que eles possam ter alguma ideia de quem está registrando e baixando seus arquivos. Mesmo se você estiver se conectando anonimamente, você não é obrigado a dar qualquer informação pessoal durante o processo de conexão, qualquer administrador de sistema vale seu salário está registrando sua sessão. Isso significa que se você fizer algo desagradável ou ilegal, o administrador do servidor terá seu número (literalmente, o domínio do host e o endereço IP). Você pode ser colocado em liberdade condicional, bloqueado ou processado. Então, aqui está uma dica para lembrar: anônimo nunca é realmente anônimo.

### Verificando sua Log

Finalmente, e por último, vamos falar um pouco sobre log. Logs como um todo precisam de um tópico à parte, mas aqui vale apenas alguns comentários. Às vezes, a maneira a mais fácil de envolver sua cabeça em torno de um conceito novo é escavar dentro e examinar os detalhes sem qualquer interface para usuário. Neste caso, podemos aprender muito simplesmente lendo o log de uma sessão FTP.Todos os servidores FTP e clientes irão registar sessões FTP. Um log é basicamente um registro de texto de toda a atividade que acontece durante uma sessão. Seu cliente deve salvar seus logs de FTP localmente, para que você possa abri-los em um editor de texto e ter uma olhada em todos os comandos FTP e ocorrências de transferência.Vamos dar uma olhada em um exemplo de log de FTP.  Vamos abrir a log do servidor que, no Ubuntu, deveria estar em **/var/log/vsftpd.log**. Esse log simplesmente mostra meu cliente conectando-se ao servidor, efetuando login e solicitando a lista de arquivos dentro do diretório padrão no servidor. Isso é tudo que está acontecendo aqui! Veja o print abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/2/852204/form-obj-0-1-.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/2/2/852204/form-obj-0-1-.png)

Veja que o login e nossa transações aparecem neste log.  Explore a log para mais entendimento sobre o FTP.

Bom, existem vários comandos que um cliente pode enviar para um servidor FTP para descobrir informações, alternar diretórios ou solicitar arquivos. Por exemplo, o comando PWD - que deve ser familiar aos usuários Unix - é usado para descobrir o diretório atual no qual você está trabalhando no servidor. Você pode ver uma lista completa de comandos de FTP no site _**Academic Information Systems da Columbia University**_, por exemplo. Estes comandos vão aparecer na log e você pode perceber o que seu cliente está pretendendo.

Mesmo sabendo que seu sistema vai cuidar de todos os comandos do servidor para você, um bom profissional deve ser capaz de olhar para os logs e entender o que está acontecendo.

Por enquanto ficamos aqui. Claro que existe uma infinidade de possibilidades no FTP, além de softwares clientes especiais, além de servidores de FTP mais complexos e sofisticados. Isto fica para você descobrir.