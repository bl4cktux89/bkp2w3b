### Introdução

Basicamente vamos trabalhar com duas frentes aqui. Primeiro uma explicação um tanto teórica de como se comportam os arquivos e, principalmente, como eles são organizados. A forma como os arquivos são gravados no disco e a forma como são organizados, influenciam na capacidade dos servidores de arquivos e as suas possibilidades, funcionalidades e características. Quando falarmos em gravação e leitura de arquivos, é bom você ter em mente como isto funciona fisicamente para ter a noção dos tempos e dos movimentos e instruções envolvidos nestas tarefas [1].

### A física dos arquivos

A maioria das pessoas ficam maravilhadas quando descobrem que podem armazenar centenas de CDs de música em um iPod (marca da Apple) de música digital não maior do que uma caixa de fósforos. O iPod original não era muito mais do que um disco rígido: um dispositivo de memória de computador incrivelmente eficiente que usa magnetismo simples para armazenar grandes quantidades de informações. Os discos rígidos foram inventados há mais de 50 anos e têm sido usados em computadores pessoais desde meados da década de 1980. O microprocessador do seu computador é o pequeno cérebro que faz todo o "pensamento" e cálculo - mas é o disco rígido que dá ao seu computador a sua memória prodigiosa e permite armazenar fotos digitais, arquivos de música, bancos de dados e documentos de texto. Como funciona? Vamos dar uma olhada!

A ciência do magnetismo é complexa, mas se você já divertiu às voltas com um ímã e alguns pregos, você saberá que a tecnologia - a ciência em ação - é bastante simples. Pregos de ferro começam desmagnetizados, mas, se você esfregar um ímã para frente e para trás sobre eles, você pode torná-los magnéticos e eles começam a grudar uns aos outros. O magnetismo tem alguns usos simples e práticos. Por exemplo, guindastes que usam eletroímãs (enormes ímãs feitos de bobinas de fios condutores que podem ser ligados e desligados com eletricidade) para pegar e mover metal entre pilhas de sucata.

O magnetismo tem outro uso muito importante. Suponha que você precisa deixar uma mensagem para um amigo e tudo que você tem é um ímã e um prego de ferro desmagnetizado. Suponha que a mensagem seja muito simples: ou você verá seu amigo mais tarde naquele dia ou não. Você poderia arranjar com seu amigo que você deixará um prego em sua caixa de correio (aquelas físicas que se encontram na frente das casas). Se o prego é magnetizado, significa que você vai vê-lo mais tarde; se o prego é desmagnetizado, você não o verá. Seu amigo chega da escola e encontra um prego na caixa de correio. Ele leva para a mesa da cozinha e tentam pegar um clipe. Se o grampo se conectar ao ímã, ele deve estar magnetizado - e isso deve significar que você planeja vê-lo mais tarde. É uma maneira muito estranha de deixar uma mensagem para alguém, mas ilustra algo muito importante: o magnetismo pode ser usado para armazenar informações.Se o seu computador tem um disco rígido de 20 gigabytes (GB), ou você tem um iPod de 20 GB ou MP3 player, é como fosse uma caixa contendo 160 bilhões de pregos de ferro microscopicamente pequenas, cada uma das quais podendo armazenar uma minúscula informação chamada “**bit**”. Um bit é um dígito binário - um número zero ou um número um. Nos computadores, os números são armazenados não como decimal (base-10), mas sim como padrões de dígitos binários. Por exemplo, o número decimal 382 é armazenado como o número binário 101111110. Cartas e outros caracteres também podem ser armazenados como números binários. Assim, os computadores armazenam uma letra maiúscula A como o número decimal 65 ou o número binário 1000001. Suponha que você deseja armazenar o número 1000001 em seu computador naquela grande caixa de pregos de ferro. Você precisa encontrar uma linha de sete pregos não utilizados. Você magnetiza o primeiro (para armazenar um 1), deixa os próximos cinco desmagnetizados (para armazenar cinco zeros) e magnetiza o último (para armazenar um 1). [1]

No disco rígido do computador, não existem realmente pregos de ferro (é óbvio). Há apenas uma grande e brilhante "placa" em formato de disco de material magnético chamado prato, dividido em bilhões de pequenas áreas. Cada uma dessas áreas pode ser magnetizada independentemente (para armazenar um 1) ou desmagnetizada (para armazenar um 0). O magnetismo é usado no armazenamento do computador porque ele continua armazenando informações mesmo quando a energia é desligada. Se você magnetiza um prego, permanece magnetizado até que você o desmagnetiza. Da mesma forma, as informações informatizadas (ou dados) armazenadas no disco rígido do PC ou no iPod permanecem lá mesmo quando você desliga o aparelho.

Os pratos são as partes mais importantes de um disco rígido. Como o nome sugere, eles são discos feitos de um material duro, como vidro ou alumínio, que é revestido com uma fina camada de metal que pode ser magnetizado ou desmagnetizado. Um pequeno disco rígido normalmente tem apenas um prato, mas cada lado dele tem um revestimento magnético. Unidades maiores têm uma série de pratos empilhados em um eixo central, com uma pequena diferença entre eles. Os pratos giram em até 10.000 rotações por minuto (rpm) ou mais para que os cabeçotes de leitura e escrita possam acessar qualquer parte deles [1].

Há duas cabeças de leitura-escrita para cada prato, uma para ler a superfície superior e uma para ler a parte inferior, de modo que um disco rígido que tem cinco pratos (digamos) precisaria de dez cabeças de leitura e gravação separadas. As cabeças de leitura-escrita são montadas num braço controlado eletronicamente que se move do centro do disco para a borda e ao contrário também. Para reduzir o desgaste, eles realmente não tocam no prato: há uma camada de fluido ou ar entre a cabeça e a superfície do prato.

A coisa mais importante sobre a memória  não é apenas ser capaz de armazenar informações, mas ser capaz de encontrá-las mais tarde. Imagine armazenar um prego de ferro magnetizado em uma pilha de 1,6 milhão de pregos idênticos e você terá alguma ideia de quanta dificuldade seu computador teria se não usasse uma maneira muito metódica de arquivar sua informação [1].Quando seu computador armazena dados em seu disco rígido, ele não apenas joga pregos magnetizados em uma caixa, todos misturados juntos. Os dados são armazenados em um padrão muito ordenado em cada prato. Bits de dados são dispostos em caminhos concêntricos, circulares chamados trilhas. Cada faixa é dividida em áreas menores chamadas setores. Parte do disco rígido armazena um mapa de setores que já foram usados ??e outros que ainda estão livres. No Windows, este mapa é chamado de tabela de alocação de arquivos ou FAT, já no Linux podemos ter ext3, ext4, ext2, xfs, ReiserFS, ReiserFS4, mesmo o FAT e o NTFS Quando o computador deseja armazenar novas informações, ele dá uma olhada no mapa para encontrar alguns setores livres. Em seguida, ele instrui a cabeça de leitura e escrita para se mover através do prato para exatamente o local certo e armazenar os dados lá. Para ler informações, o mesmo processo é executado em sentido inverso.Como um computador eletrônico manipula todos os detalhes mecânicos em um disco rígido? Existe uma interface entre eles chamada de **controlador**. Este controlador é um pequeno circuito que opera os atuadores, seleciona faixas específicas para leitura e gravação e converte fluxos paralelos de dados que vem do computador (abra seu computador e veja como existem cabos paralelos ligando os discos à placa principal) em fluxos de dados seriais sendo gravados no disco (e vice-versa). Os controladores são construídos na própria placa de circuito da unidade de disco ou na parte da placa principal do computador (placa-mãe).Com tanta informação armazenada em uma quantidade tão pequena de espaço, um disco rígido é uma peça notável de engenharia. Isso traz benefícios (como ser capaz de armazenar 500 CDs em seu iPod), mas também traz inconvenientes. Um deles é que os discos rígidos podem dar problemas se eles ficam com sujeira ou poeira dentro deles. Um minúsculo grão de poeira pode fazer a cabeça de leitura e gravação saltar para cima e para baixo, colidindo com o prato e danificando seu material magnético. Isso é conhecido como um **crash (aqui tem o significado de acidente ou desastre)** de disco (ou crash de cabeça) e pode, embora nem sempre, causar a perda de todas as informações em um disco rígido. Um crash de disco geralmente ocorre independentemente de qualquer situação especial, sem qualquer aviso. É por isso que você deve sempre manter cópias de backup de seus documentos e arquivos importantes, em outro disco rígido, em um CD ou DVD ou em um pendrive ou nuvem[1].

Agora que você tem uma ideia da dificuldade e tarefas relacionadas com gravar dados em um disco, podemos entrar no aspecto da organização dos arquivos neste sistema físico de armazenamento.

### Introdução aos Sistemas de Arquivos

Existe uma confusão entre o ‘file system’ que rege a maneira como os diretórios e arquivos são armazenados em termos de hierarquia posicional e o ‘file system’ que é a forma lógica de armazenar dados em dispositivos de armazenamento.

Sistemas de arquivos são uma das coisas que qualquer novato de Linux deve se familiarizar. No mundo da Microsoft você nunca precisa realmente se preocupar, o padrão sendo NTFS. No entanto, o Linux sendo construído em um mundo de código aberto e opiniões diferentes, não é limitado dessa forma e, portanto, o usuário deve ter uma compreensão do que é um sistema de arquivos e como ele afeta o computador [1].

No núcleo de um computador, é tudo 1s (uns) e 0s (zeros), mas a organização desses dados não é tão simples. Um bit é um 1 ou um 0, um byte é composto de 8 bits, um kilobyte é 1024 (ou seja, 2 ^ 10) bytes, um megabyte é 1024 kilobytes e assim por diante. Todos esses bits e bytes são permanentemente armazenados em um disco rígido. Um disco rígido armazena todos os seus dados, e, a qualquer momento que você salvar um arquivo, você está escrevendo milhares de 1s e 0s para um disco metálico, alterando as propriedades magnéticas que podem ser lidas mais tarde como 1 ou 0. Há tantos dados em um disco rígido que tem que haver alguma maneira de organizá-lo, como uma biblioteca de livros e as gavetas antigas de cartão que indexam todos eles. Sem o índice, nós estaríamos perdidos. As bibliotecas, em sua maioria, usam o sistema decimal Dewey para organizar seus livros, mas existem outros sistemas para fazê-lo, nenhum dos quais alcançou a mesma fama que a invenção de Dewey. Os sistemas de arquivos são da mesma maneira. Os que a maioria dos usuários estão cientes são aqueles que o Windows usa, os sistemas vFat ou NTFS, estes são os sistemas de arquivos padrão do Windows. Existem vários atributos diferentes que são necessários na definição de sistemas de arquivos, que incluem seu tamanho máximo de arquivo, tamanho máximo de partição, se eles jornalizam ou não.  Estes aspectos que fazem diferença na velocidade com que os arquivos podem ser copiados, espelhados e transferidos [2].

Segue abaixo uma tabela do que os mais variados sistemas de arquivos (**file systems**) são capazes e suas diferenças.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830887/36372.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/8/830887/36372.png)

Um sistema de arquivo com jornalização é mais confiável quando se trata de armazenamento de dados. Os sistemas de arquivos com jornalização não impedem necessariamente a corrupção dos dados, mas impedem a inconsistência e são muito mais rápidos nas verificações do sistema de arquivos do que os sistemas de arquivos não jornalizados. Se ocorrer uma falha de energia enquanto você está salvando um arquivo, o salvamento não será concluído e você acabará com dados corrompidos e um sistema de arquivos inconsistente. Em vez de escrever diretamente na parte do disco onde o arquivo é armazenado, um sistema de arquivo jornalizado primeiro escreve-o em outra parte do disco rígido e anota as alterações necessárias num log e, em segundo plano, passa cada entrada no jornal e começa a concluir a tarefa, e quando a tarefa é concluída, ele verifica na lista. Assim, o sistema de arquivos estará sempre em um estado consistente (ou o arquivo foi salvo, ou o jornal informa que ele não foi completamente salvo ou o jornal é inconsistente (mas pode ser reconstruído a partir do sistema de arquivos)). Alguns sistemas de arquivos jornalizados podem evitar a corrupção, assim como gravar dados duas vezes.

Aqueles usam um sistema de arquivos do Windows (NTFS, FAT) sabem que normalmente não é possível alterar arquivos enquanto eles estão abertos. Esta restrição não existe em um sistema de arquivos Unix. Isso ocorre porque nos sistemas de arquivos Unix, os arquivos são indexados por um número, chamado inode, e cada inode tem vários atributos associados, como permissões, nome, etc. Quando você exclui um arquivo, o que realmente acontece é que o inode fica desvinculado do nome do arquivo, mas se algum outro programa estiver usando o arquivo, ele ainda tem um link aberto para o sistema operacional e continuará a ser atualizado. Um arquivo não é realmente excluído até que todos os links foram removidos (mesmo assim, os dados ainda estão no disco, mas não indexados de qualquer maneira e, portanto, muito difícil de recuperar). Tudo isso significa que você pode excluir a execução de programas enquanto eles estão executando gravando arquivos antes de eles terem terminado de fechar sem qualquer corrupção [1].

Outra prática comum do Windows que não é necessária no Unix é desfragmentar o disco rígido. Quando NTFS e FAT gravam arquivos no disco rígido, eles nem sempre mantêm as partes (conhecidas como blocos) dos arquivos em conjunto. Portanto, para manter o desempenho do computador, o disco rígido precisa ser "desfragmentado" de vez em quando. Isso é desnecessário nos sistemas Unix devido à maneira como foi projetado. Quando o ext3 foi desenvolvido, ele foi codificado para que ele mantivesse blocos de arquivos juntos ou pelo menos próximos um do outro.

Nenhuma ferramenta de desfragmentação verdadeira existe para o sistema de arquivos ext3, mas as ferramentas para desfragmentação foram incluídas no sistema de arquivos ext4.

Se você está migrando do Windows para o Linux e tem mais de uma partição **ntfs** no mesmo disco, você pode ser tentado a converter uma das partições para ext3 ou 4 e instalar lá os arquivos do Linux, deixando a partição **ntfs** como **/home**. Evite isso! É correto ter duas partições para os arquivos de sistema Linux e outra para arquivos /home no mesmo disco, mas eles devem ter o mesmo sistema de arquivos.

### Files Servers

Talvez uma das funções mais consagradas do Linux seja a capacidade de prestar serviços de servir arquivos. Um servidor de arquivos é muito mais do que um organizador de arquivos, mas sim, uma série de controles de acesso, versões, segurança e, principalmente, um método de criar transparência entre sistemas operacionais diversos como Windows x Linux.  A medida que as redes das empresas crescem, precisamos garantir que os usuários finais, geralmente baseados em Windows, possam ter acesso a um controle estável de arquivos para múltiplos e simultâneos acessos. A estabilidade do Linux é ideal para cumprir com esta função. Atualmente, embora isto já devesse ter acabado, as empresas colocam muito de suas atividades em arquivos departamentais, geralmente planilhas de controle, coisa que deveria estar em um sistema integrado de gestão. Estes arquivos muitas vezes são acessados por muitos usuários e não é incomum quando, sem esperar, o arquivo se corrompe. Isto é muito mais difícil acontecer se o servidor de arquivos fosse Linux. Bem, não queremos falar aqui que seria impossível ter segurança de integridade de dados no Windows, mas com certeza o custo para garantir isto seria empregado em tecnologia de storage e, sem dúvida alguma seria mais custoso que um ambiente Linux [3].

Esta facilidade toda é dada através de um dos mais famosos softwares, que é frequentemente confundido como um protocolo. O SAMBA.

### Configurando um servidor de arquivos Linux usando o Samba

Uma rápida olhada no Google irá mostrar muitas maneiras de configurar um servidor de arquivos Linux rodando Samba, a maioria deles, no entanto não funciona! Alguns deixam de fora pequenos detalhes importantes deixando você preso, além de alguns só funcionarem com uma versão específica de uma distribuição (claro que não vou falar nenhum nome de distribuição aqui). Já tentei várias vezes usar receitas malcuidadas e só perdi meu tempo. Depois de várias tentativas até que fui construindo uma maneira própria e garantida. O que vou passar funciona e foi testado várias vezes em instalações grandes, médias e pequenas. Isso não é para ser uma configuração de alta segurança, todas as pastas são acessíveis a todos para leitura, gravação e exclusão. Se você precisa de segurança para áreas que querem acesso exclusivo à sua própria área no servidor, então você pode usar isso como um ponto de partida e algumas mudanças simples para esse nível de segurança, serão acrescentadas ao final deste estudo.Você poderia, naturalmente, configurar um computador Windows executando o compartilhamento de arquivos, mas existem algumas boas razões para não o fazer. O Windows precisaria de monitoramento constante para garantir que as atualizações sejam instaladas (exigindo muitas reinicializações). O Windows é muito vulnerável a vírus para que o seu software antivírus seja mantido adequadamente atualizado. O Windows é menos estável e o modelo de sistema de arquivos não permite associações adequadas de segurança. Ao fazer um pequeno teste com uma máquina antiga e Linux Ubuntu, surpreendentemente o SAMBA funcionou sem parar por 2,5 anos. Neste tempo vários clientes deste servidor na plataforma Windows, foram atacados por vírus e mesmo assim não precisei fazer nada no SAMBA. Na verdade, os arquivos do Windows armazenados no servidor foram infectados com o vírus, mas o sistema operacional Linux não foi afetado. Ubuntu Server pode ser instalado em qualquer PC antigo que você tem jogado em um canto de sua casa, mesmo um 486 serviria. Vamos começar a instalar [2].

Começamos com o comando abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830937/36373.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830937/36373.png)

Quando você instalou o SAMBA, trouxe para seu computador dois daemons (aqueles programas que executam em background e não são controlados diretamente pelo usuário). O **smbd** e o **nmbd**.

### Smbd

O daemon, do servidor **samba,** **smbd** fornece serviços de compartilhamento e impressão de arquivos para clientes Windows. Além disso, é responsável pela autenticação do usuário, bloqueio de recursos e compartilhamento de dados através do protocolo SMB. As portas padrão nas quais o servidor escuta o tráfego SMB são portas TCP 139 e 445.O **smbd** daemon é controlado pelo serviço **smb**.

### Nmbd

O daemon, do servidor **samba**, **nmbd** entende e responde às solicitações de serviço de nome **NetBIOS**, como as produzidas pelo SMB/CIFS em sistemas baseados no Windows. Esses sistemas incluem clientes Windows 95/98 / ME, Windows NT, Windows 2000, Windows XP, Windows Vista, Windows 7, Windows 8, Windows 10 e LanManager. Ele também participa dos protocolos de navegação que compõem a visualização **Windows Network Neighborhood (aquela opção quando você procura as máquinas e dispositivos que pode achar na rede)**. A porta padrão que o servidor escuta para o tráfego NMB é a porta UDP 137.

O daemon **nmbd** é controlado pelo serviço **smb**.

O arquivo de configuração mais importante do Samba está localizado no diretório /etc/samba/smb.conf. Este arquivo de configuração padrão tem um número bem elevado de comentários para documentar várias diretivas de configuração. [2]

Nem todas as opções disponíveis estão incluídas no arquivo de configuração padrão. Consulte a página man do smb.conf ou a série HOWTO do Samba para obter mais detalhes.

Abra para edição o arquivo de configuração como segue, mas **antes faça uma cópia de segurança**. Se você cometer erros aqui poderá perder a instalação e ter que começar tudo novamente.

**\#vim /etc/samba/smb.conf**

Você precisa ser um usuário administrador (super usuário) para salvar as alterações quando você terminar de editar.

Agora você vê em sua tela algo como o print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830940/36374.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830940/36374.png)

No Ubuntu qualquer comando que possa alterar a configuração do servidor precisa ser executado pelo usuário admin. Por razões de segurança você não pode fazer login como root (o usuário admin) a alternativa é inserir sudo antes de cada comando, em seguida, fornecer a senha de administrador, isso mantém as coisas seguras ou você pode digitar sudo su (para super usuário), em seguida, a senha e isso dará acesso de administrador até que você digitar um exit, ou fazer logout.Para fazer teste, verifique o nome do grupo de trabalho no seu PC Windows clicando com o botão direito do mouse em Meu Computador, selecione propriedades e Nome do computador. Provavelmente será WORKGROUP ou MSHOME, dependendo da sua versão Windows.

Agora siga as instruções cuidadosamente. Alguns dos comandos já estão no arquivo smb.conf, mas têm um símbolo **#** (símbolo de comentário) na frente deles, remover o símbolo **#** torna o comando ativo.Para fechar o VIM e salvar suas alterações pressione ESC digite **“:”** e pressione enter. O cursor irá para a linha última linha de baixo à esquerda. Digite “wq” e pressione enter.Praticamente tudo no Linux é sensível a maiúsculas e minúsculas, ou seja, se você deu a sua pasta nomes maiúsculas ao criá-los, então você deve usar maiúsculas quando se referindo a eles ou quando estiver navegando pela estrutura do arquivo. O Linux verá o diretório Uninove ou uninove como dois diretórios diferentes [3].

Vamos começar observando um pouco abaixo do print acima. Tratam-se das especificações globais => **“Global Settings”** veja algumas no print abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830943/36375.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830943/36375.png)

**Global** representa as configurações que servem em geral, independente se configurarmos qualquer área específica. A primeira observação que fazemos deste print é o workgroup **= WORKGROUP.** Significando: Quem é deste grupo (WORKGROUP), não interessa de qual máquina ou sistema operacional, Windows ou Linux, pode acessar arquivos aqui [3].

“**Server string**” é a descrição da máquina Linux que será exibida no Network Neighborhood em sua máquina Windows. Você pode muito bem nomear qualquer coisa que você deseja, mas tente ter um padrão que seja prático sobre isto.

Agora vamos modificar aquela opção que está comentada: wins support que está “no” para “yes”. Isto fará com que o servidor samba apareça para a rede local como um nome de servidor NetBios, que dizer, para os usuários Windows, este servidor é uma máquina comum Windows. Pelo menos na aparência. Então o print fica:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830945/36376.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830945/36376.png)

Vamos manter a opção acima “**dns proxy = no**” evitando que o daemon NMDB sai por aí procurando todas as máquinas no ambiente NetBios.

Existem muitas opções mas para funcionar com servidor de arquivos e não como Active Directory, assim está bom[4].

Vamos reinicializar o samba:

**# systemctl restart smbd.service nmbd.service**

Agora podemos ver se está tudo ok. Fui até um computador Window ao lado e fiz procura de rede. Olhe o que apareceu!

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830948/36377.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830948/36377.png)

Você está vendo o LUCKYGAVNOTE, bem, esta é a máquina Linux que está rodando o samba. Mas, agora, se você clicar lá no Windows sobre este ícone, irá abrir outra tela e aparecerá apenas uma impressora, que é a impressora conectada diretamente na máquina LInux LuckyGavNote. Aproveitando, está vendo o nome que coloquei agora? Apenas algumas maiúsculas. No Linux o nome verdadeiro é este (hostname) mas para o WINS seguindo o padrão NetBios, as máquinas recebem o nome todo em maiúsculas, por isso aparece LUCKYGAVNOTE na tela do Windows.

Vamos então criar esta área de arquivos para que aquele Windows possa ver uma pasta própria.

**\#vim /etc/samba/smb.conf**

Vamos criar um espaço próprio para aquele usuário do Windows. Lá o usuário é LukeRKnife.

Então vamos digitar o seguinte grupo de diretivas um pouco acima das diretivas **[printers]**.  Não existe uma posição especial para isto, mas é bom seguir um padrão como este.

**[Departamento_X]**

**comment = Acesso Restrito ao Departamento X**

**path = /samba/Departamento_X**

**public = no    \#Acesso com senha, privado**

**writable = yes    \#Permitir alterações no diretório?**

**valid users =  LukeRKnife**

Vai ficar assim:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830951/36378.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830951/36378.png)

Após isto restart o samba:

**# systemctl restart smbd.service nmbd.service**

Para ver se está tudo ok com o Samba, pode fazer o comando abaixo:

**# systemctl status smbd.service nmbd.service**

Aparecerá a tela:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830953/36379.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830953/36379.png)

Qualquer erro apareceria nesta tela de status.

Agora, se formos no Windows, podemos ver na procura de rede o novo Departamento_X.  Veja a tela abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830954/36380.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/0/9/830954/36380.png)

Pode-se ver facilmente que agora temos uma área reservada para acesso do usuário LukeRKnife chamada Departamento_X.

É claro que eu criei um diretório na máquina Linux /samba/Departamento_X antes de tudo.

### Conclusão

Podemos fazer muito como o samba, especialmente se assumirmos o controle de usuários em conjunto com o Active Directory do Windows, mas isto fica para outro tópico.

Aprendemos a montar um servidor de arquivo com área de arquivos especial para um usuário, mas poderia ser um grupo de usuários representando um departamento. Existem mais outras opções e você pode testar em sua máquina virtual muitas outras atividades. Como dica fica um aviso: Antes de cada modificação necessária, faça uma cópia do smb.conf. Isto vai poupar muita dor de cabeça.