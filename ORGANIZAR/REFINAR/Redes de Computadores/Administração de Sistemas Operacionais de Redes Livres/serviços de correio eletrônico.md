### Introdução.

Falar em e-mail não é simplesmente criar uma condição de termos arquivos eletrônicos transportados de um computador para outro. Para isto um FTP seria mais que suficiente. A ideia de se ter um mecanismo que se assemelha ao correio “manual”, aquele no qual o carteiro pega um volume de cartas e as entrega no endereço exato para qual elas estão destinadas, passa por uma série de padronizações e protocolos que devem ser compreendidos para que você realmente entenda como funciona um servidor de e-mail e quais as características que são limitadoras e facilitadoras no processo de receber e enviar correspondência eletrônica.

Todos os dias, os usuários da Internet enviam uns aos outros bilhões de mensagens de e-mail. Você mesmo pode enviar uma dúzia ou mais de e-mails a cada dia sem sequer pensar nisso. Obviamente, o e-mail tornou-se uma ferramenta de comunicação extremamente popular.

Alguma vez você já se perguntou como um e-mail consegue ir do seu computador para o computador de um amigo em qualquer lugar do mundo? O que é um servidor POP3 e como ele mantém seu e-mail? As respostas podem surpreendê-lo, porque você descobrirá que o e-mail é um sistema incrivelmente simples no seu núcleo. Neste estudo, vamos dar uma olhada em profundidade no e-mail e como ele funciona.

A primeira mensagem de e-mail foi enviada em 1971 por um engenheiro chamado Ray Tomlinson. Até aquela época, você só poderia enviar mensagens para os usuários em uma única máquina. O avanço de Tomlinson foi a capacidade de enviar mensagens para outras máquinas na Internet, usando o sinal @ para designar a máquina receptora.[1].

Uma mensagem de e-mail sempre foi nada mais do que uma simples mensagem de texto, um pedaço de texto enviado para um destinatário. No início e até hoje, as mensagens de e-mail tendem a ser pequenos pedaços de texto, embora a capacidade de adicionar anexos agora torne muitas mensagens bastante longas. Mesmo com anexos, no entanto, as mensagens de e-mail continuam a ser mensagens de texto, veremos por que, quando chegarmos à seção sobre anexos.

Você provavelmente já recebeu várias mensagens de e-mail hoje. Para olhar para eles, você usa algum tipo de **cliente** de e-mail. Muitas pessoas usam clientes bem conhecidos e autônomos como o Microsoft Outlook, Outlook Express, Eudora ou Pegasus. As pessoas que se inscrevem em serviços de e-mail gratuitos como o Hotmail ou o Yahoo usam um cliente de e-mail que aparece em uma página da Web. Se você é cliente da AOL, usa o leitor de e-mail da AOL. Não importa qual o tipo de cliente que você está usando, ele geralmente faz quatro coisas:

- Mostra uma lista de todas as mensagens na caixa de correio exibindo os cabeçalhos das mensagens. O cabeçalho mostra quem enviou o e-mail, o assunto do e-mail e também pode mostrar a hora e a data da mensagem e o tamanho da mensagem.
- Permite selecionar um cabeçalho de mensagem e ler o corpo da mensagem de e-mail.
- Permite criar novas mensagens e enviá-las. Você digita o endereço de e-mail do destinatário e o assunto da mensagem e, em seguida, digita o corpo da mensagem.
- Permite adicionar anexos às mensagens enviadas e salvar os anexos das mensagens recebidas.

Clientes mais sofisticados de e-mail podem ter todos os tipos de sinais de alerta e lembretes e cores, mas, no cerne, isso é tudo o que um cliente de e-mail faz.

Quando você tem um cliente de e-mail em sua máquina, você está pronto para enviar e receber e-mails. Tudo o que você precisa é um servidor de e-mail para o cliente se conectar. Vamos imaginar o que um servidor de e-mail mais simples possível faria, semelhante a o que fizemos com o cliente, a fim de obter uma compreensão básica do processo. Então vamos olhar para a coisa real.

Se você sabe como funcionam os servidores da Web, então você sabe que as máquinas na Internet podem executar aplicativos de software que atuam como servidores. Existem servidores Web, servidores FTP, servidores telnet e servidores de e-mail rodando em milhões de máquinas na Internet agora. Esses aplicativos são executados o tempo todo na máquina do servidor e eles ouvem portas específicas, aguardando pessoas ou programas para anexar à porta. O servidor de e-mail mais simples possível funcionaria como apresento abaixo:

- Ele teria uma lista de contas de e-mail, com uma conta para cada pessoa que pode receber e-mail no servidor. Para o nome João de Pedro e Silva, o nome da conta poderia ser **jpsilva**, para nome FITAFUSO poderia ser **fitafuso** e assim por diante.
- Teria um arquivo de texto para cada conta na lista. Portanto, o servidor teria um arquivo de texto no diretório, chamado JPSILVA.TXT, outro chamado FITAFUSO.TXT e para outras contas também.
- Se alguém quisesse enviar uma mensagem para o João Pedro da Silva, a pessoa iria compor uma mensagem de texto ("Pedro, você pode me devolver aquele monitor de vídeo que eu emprestei para você no ano passado. Assinado: Fitafuso") em um cliente de e-mail, e indicar que a mensagem deve ir para **jpsilva**. Quando a pessoa pressiona o botão/opção Enviar, o cliente de e-mail se conecta ao servidor de e-mail e passa para o servidor o nome do destinatário (**jpsilva**), o nome do remetente (**fitafuso**) e o corpo da mensagem.
- O servidor formataria essas partes de informações e as anexaria à parte inferior do arquivo FITAFUSO.TXT. A entrada/começo do arquivo teria esta aparência:

**From**: fitafuso **To**: jpsilva Pedro, você pode me devolver aquele monitor de vídeo que eu emprestei para você no ano passado. Assinado: Fitafuso

Existem várias outras informações que o servidor pode salvar no arquivo, como a hora e a data de recebimento e uma linha de assunto; mas, assim como no caso do cliente de email, no geral, você pode ver que este é um processo extremamente simples.

À medida que outras pessoas enviam mensagens para **jpsilva** o servidor simplesmente anexa essas mensagens à parte inferior do arquivo na ordem em que elas chegaram. O arquivo de texto iria acumular uma série de cinco ou 10 mensagens e, eventualmente, Pedro pode entrar para lê-los. Quando ele quer olhar para o seu e-mail, o cliente de e-mail se conectaria à máquina do servidor. Olhando pelo aspecto mais simples possível seria algo como:

- Peça ao servidor para enviar uma cópia do arquivo JPSILVA.TXT
- Peça ao servidor para apagar e redefinir o arquivo JPSILVA.TXT
- Salve o arquivo JPSILVA.TXT na minha máquina local
- Analise o arquivo separando as mensagens usando a palavra **"From:"** como o separador.
- Mostrar todos os cabeçalhos de mensagem em uma lista

Quando ele clica duas vezes em um cabeçalho de mensagem, ele iria ver essa mensagem no arquivo de texto e me mostrar seu corpo.

Como você pode ver, este é um sistema muito simples. Existem protocolos padrões de transmissão de e-mails e protocolos padrões de recepção de email. Surpreendentemente, o verdadeiro sistema de e-mail que você usa todos os dias não é muito mais complicado do que isso. Aliás, com um pouco de experiência em programação, fica fácil fazer um sistema “**servidor de e-mail”** e um sistema “**cliente de email”.** Mas, por que as pessoas não fazem? Porque não fazem!!!! Simples assim.

### Protocolos de Email

**SMTP**

Para a grande maioria das pessoas no momento, o sistema de e-mail real consiste em dois servidores diferentes em execução em uma máquina servidor. Um deles é chamado de servidor **SMTP**, onde **SMTP** significa _**Simple Mail Transfer Protocol**_**.** O servidor **SMTP** processa o correio de saída. O outro é um servidor **POP3** ou um servidor **IMAP**, ambos lidar com o correio recebido. **POP** significa _**Post Office Protocol**_ e **IMAP** significa _**Internet Mail Access Protocol**_. Um servidor de e-mail típico se parece com isto:

O servidor SMTP atende à porta número 25/587 (25 está descontinuada. O uso atual é pela 587), POP3 escuta na porta 110 e IMAP usa a porta 143.

Sempre que você envia um e-mail, seu cliente de e-mail interage com o servidor SMTP para lidar com o envio. O servidor SMTP no seu host pode ter conversas com outros servidores SMTP para entregar o e-mail.

Vamos supor que eu quero enviar um e-mail. Meu ID de e-mail é **luckygav**, e eu tenho minha conta no **luckygav.net**. Quero enviar e-mail para **mamae@dominiodamae.com**. Estou usando um cliente de e-mail autônomo como o Outlook Express.

Quando eu configurar a minha conta no **luckygav.net**, eu disse ao Outlook Express o nome do servidor de correio - **mail.luckygav.net.** Quando eu componho uma mensagem e pressione o botão Enviar, aqui está o que acontece: [1]

- O Outlook Express conecta-se ao servidor SMTP em mail.luckygav.net usando a porta 587.
- O Outlook Express tem uma conversa com o servidor SMTP, informando ao servidor SMTP o endereço do remetente e o endereço do destinatário, bem como o corpo da mensagem.
- O servidor SMTP recebe o endereço "To (mamae@dominiodamae.com) e divide-o em duas partes: o nome do destinatário (**mamae**) e o nome do domínio (**dominiodamae.com**)). Se o endereço "To" tivesse sido outro usuário no **luckygav.net**, o servidor SMTP simplesmente entregaria a mensagem para o servidor POP3 para **luckygav.net** (usando um pequeno programa chamado o agente de entrega). Como o destinatário está em outro domínio (**dominiodamae.com**), o SMTP precisa se comunicar com esse domínio.
- O servidor SMTP tem uma conversa com um servidor de Domain Names System ou **DNS** (consulte em um tópico específico sobre DNS). Ele diz: "Você pode me dar o endereço IP do servidor SMTP para **dominiodamae.com**)?" O DNS responde com um ou mais endereços IP para o servidor SMTP que o **dominiodamae.com** opera.
- O servidor SMTP em luckygav.net se conecta com o servidor SMTP no **dominiodamae.com** usando a porta 587. Ele tem a mesma conversa de texto simples que meu cliente de e-mail tinha com o servidor SMTP para **luckygav.net** e dá a mensagem para o servidor **dominiodamae.com**. O servidor **dominiodamae** reconhece que o nome de usuário **mamae** está no **dominiodamae.com** por isso entrega a mensagem ao servidor POP3 do **dominiodamae.com**, que coloca a mensagem na caixa de correio da **mamae.**

Se, por algum motivo, o servidor SMTP no **luckygav** não puder se conectar com o servidor SMTP no **dominiodamae**, a mensagem entrará em uma fila. O servidor SMTP na maioria das máquinas usa um programa chamado **sendmail** para fazer o envio real, então essa fila é chamada de fila **sendmail (sendmail queue)**. O **Sendmail** tentará periodicamente reenviar as mensagens em sua fila. Por exemplo, ele pode repetir a cada 15 minutos. Depois de quatro horas, ele normalmente irá enviar-lhe um e-mail que lhe diz que há algum tipo de problema. Após cinco dias, a maioria das configurações do **sendmail** desistem e mandar o e-mail para você com a notícia de “e-mail não entregue”[1].

O servidor SMTP compreende comandos de texto muito simples como HELO, MAIL, RCPT, DATA, etc. Os comandos mais comuns são:

- **HELO** - Apresente-se
- **EHLO** - Apresente-se e solicite o modo estendido.
- **MAIL FROM:** - Remetente
- **RCPT TO:** - Destinatário
- **DATA** - Corpo da Mensagem
- **RSET** - Redefinir!
- **QUIT** - Fecha a sessão
- **HELP** - Ajuda para lista de comandos
- **VRFY** - Verifique um endereço
- **EXPN** - Expanda um endereço
- **VERB** - Detalhe a transação

**POP3**

Nas implementações mais simples do POP3, o servidor realmente mantém uma coleção de arquivos de texto - um para cada conta de e-mail. Quando uma mensagem chega, o servidor POP3 simplesmente o anexa para a parte inferior do arquivo do destinatário.

Ao verificar seu e-mail, seu cliente de e-mail se conecta ao servidor POP3 usando a porta 110. O servidor POP3 requer um nome de conta e uma senha. Depois de efetuar login, o servidor POP3 abre o arquivo de texto que permite que você acesse o conteúdo. Tal como o servidor SMTP, o servidor POP3 compreende um conjunto muito simples de comandos de texto. Aqui estão os comandos mais comuns: [2]

- **USER** - Seu login.
- **PASS** - Senha
- **QUIT** - Fecha a sessão
- **LIST** - Lista as mensagens e seus tamanhos
- **RETR** - Recupera a mensagem
- **DELE** - Exclui a mensagem
- **TOP** - Mostra as primeiras “x” linhas de uma mensagem.

Seu cliente de e-mail se conecta ao servidor POP3 e emite uma série de comandos para trazer cópias de suas mensagens de e-mail para sua máquina local. Em geral, ele irá excluir as mensagens do servidor (a menos que você tenha dito ao cliente de e-mail que não quer fazer isto).

Você pode perceber que o servidor POP3 simplesmente atua como uma interface entre o cliente de e-mail e o arquivo de texto que contém suas mensagens (aquele preparado pelo servidor de SMTP). E novamente, você pode ver que o servidor POP3 é extremamente simples. Você pode se conectar a ele através do telnet na porta 110 e emitir os comandos você mesmo se você preferir.

**IMAP**

Como você pode ver, o protocolo POP3 é muito simples. Ele permite que você tenha uma coleção de mensagens armazenadas em um arquivo de texto no servidor. O seu cliente de e-mail (por exemplo, o Outlook Express) pode ligar-se ao servidor de correio eletrônico POP3 e transferir as mensagens do arquivo de texto POP3 para o PC. Isso é tudo o que você pode fazer com POP3.

Muitos usuários querem fazer muito mais do que isso com seu e-mail, e eles querem que seu e-mail permaneça no servidor. A principal razão para manter seu e-mail no servidor é permitir que os usuários se conectem a partir de uma variedade de máquinas. Com o POP3, uma vez que você baixou o seu e-mail, ele fica preso na máquina a qual você baixou. Se você quiser ler seu e-mail tanto em seu desktop ou em seu laptop (dependendo se você está trabalhando no escritório ou na rua), POP3 torna a vida difícil [1].

**IMAP** (_**Internet Mail Access Protocol**_) é um protocolo mais avançado que resolve esses problemas. Com o IMAP, seu e-mail permanece no servidor de e-mail. Você pode organizar seu e-mail em pastas, e todas as pastas ficam online no servidor também. Quando você pesquisa seu e-mail, a pesquisa ocorre na máquina do servidor, em vez de em sua máquina. Esta abordagem torna extremamente fácil para você acessar seu e-mail de qualquer máquina, e independentemente de qual máquina você usa, você tem acesso a todos os seus e-mails e todas as suas pastas [1].

Seu cliente de e-mail se conecta ao servidor **IMAP** usando a porta **143**. O cliente de e-mail emite um conjunto de comandos de texto que permitem fazer coisas como listar todas as pastas no servidor, listar todos os cabeçalhos de mensagem em uma pasta, obter uma mensagem de e-mail específica do servidor, excluir mensagens no servidor ou pesquisar por todos os e-mails no servidor.

Um problema que pode surgir com IMAP envolve esta pergunta simples: "Se todo o meu e-mail estiver armazenado no servidor, como posso ler meu e-mail se não estiver conectado à Internet?" Para resolver esse problema, a maioria dos clientes de e-mail tem alguma maneira de armazenar em cache o e-mail na sua máquina local. Por exemplo, o cliente baixará todas as mensagens e armazenará seu conteúdo completo na máquina local (exatamente como se estivesse falando com um servidor POP3). As mensagens ainda existem no servidor IMAP, mas agora você tem cópias em sua máquina local. Isso permite que você leia e responda a e-mail mesmo se você não tem conexão com a Internet. Na próxima vez que estabelecer uma conexão, você baixará todas as novas mensagens recebidas enquanto estava desconectado e enviará todos os e-mails que você escreveu enquanto estava desconectado.

**Anexos**

Seu cliente de e-mail permite que você adicione anexos a mensagens de e-mail que você envia e também permite que você salve anexos de mensagens que você recebe. Os anexos podem incluir documentos de processamento de texto, planilhas, arquivos de som, instantâneos e partes de softwares. Normalmente, um anexo não é texto (se fosse, você simplesmente iria incluí-lo no corpo da mensagem), embora muitas vezes você precisa que o texto vá em um formato em especial (MS Word por exemplo). Como as mensagens de e-mail podem conter apenas informações de texto e os anexos não são texto, há um problema que precisa ser resolvido.

No começo, quando ainda estávamos começando a usar o e-mail, resolvíamos este problema manualmente, usando um programa chamado **uuencode (era um método de troca de informações Unix-Unix).** O programa **uuencode** assume que o arquivo contém informações binárias. Ele extrai 3 bytes do arquivo binário e os converte em quatro caracteres de texto (ou seja, leva 6 bits de cada vez, adiciona 32 ao valor dos 6 bits e cria um caractere de texto (**não tente entender isto agora!!!**). O que o **uuencode** produz, portanto, é uma versão codificada do arquivo binário original que contém somente caracteres de texto. Nos primeiros servidores e clientes de e-mail, você executaria **uuencode** e colar o arquivo **uuencoded** (codificado em texto) em sua mensagem de e-mail. Depois, o destinatário usaria o uudecode para decodificar [2].

Considerando seu tremendo impacto na sociedade, tendo mudado para sempre a maneira como nos comunicamos, o sistema de e-mail de hoje é uma das coisas mais simples já inventadas! Existem partes do sistema, como as regras de roteamento no **sendmail**, que se complicam, mas o sistema básico é incrivelmente direto.

### Implementando um Servidor de Correio Eletrônico

Vamos instalar no Ubuntu um dos servidores mais usuais para Linux, o **POSTFIX**.

Comece com a instalação do pacote:

**\#apt-get install postfix**

Veja as telas que se surgirão em meio à instalação:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822123/36714.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822123/36714.png)

A primeira tela mostra que ainda não houve qualquer configuração. Apenas coloque OK.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822126/36715.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822126/36715.png)

Se você quer que seu servidor receba e mande e-mails para qualquer outro servidor ou cliente, coloque **Site da Internet.**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822131/36716.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822131/36716.png)

Nesta tela acima o POstfix pede um nome FQDN (_**Full Qualified Domain Name**_), ou seja, um nome de servidor com o domínio oficialmente designado. Veja em um tópico específico de Servidor de DNS.

Desta forma o script do pacote terminará a instalação e configuração:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822137/36717.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822137/36717.png)

Com estes dados já podemos ver que tudo pode ser testado.

Podemos facilmente dar um comando de acesso ao servidor:

**# telnet 192.168.0.10 25**

Na tela abaixo pode-se ver uma conversa simples com aquele comando que mostramos acima:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822143/36718.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822143/36718.png)

**Exemplo com dois usuários.**

Testando agora a criação de um usuário e o envio de mensagem por ele par o meu usuário:

Criamos um usuário com o comando abaixo:

**\#adduser usuario1**

Veja no print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822148/36719.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822148/36719.png)

Lembrando que nosso usuário padrão é o “luckygav”. Podemos produzir a mensagem abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822150/36720.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822150/36720.png)

Usando o mutt, um cliente de e-mail em formato de texto (se você não o tem instalado, instale):

**\#apt-get install mutt**

**\#mutt**

Verá uma tela com as mensagens enviadas. (print abaixo):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822151/36721.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/2/2/1/822151/36721.png)

**Cuidado!** Estamos fazendo tudo como superusuário (#) então se você abrir mutt, mas usou os exemplos de envio pelo Postfix com os usuários normais (como fiz com o usuario1 e o luckygav), não haverá qualquer mensagem. Por default o mutt abre o “inbox” do usuário corrente.

Você pode ir melhorando este e-mail. Usar o Postfix como bases para WEB Mails, etc.

### Conclusão

Existe uma quantidade enorme de servidores de email para Linux, como: Zimbra (um dos melhores), Postfix, Qmail, Sendmail, Spark engine, IBM Lotus Domino, etc. Sempre podemos melhorar as condições de ter pelo menos um servidor para resolver problemas locais e usar os públicos para coisas maiores. O importante é compreender o que é necessário, tanto no servidor quando no cliente para você montar algo dentro das suas necessidades.