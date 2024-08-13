### Introdução

Quando verificamos comandos de linha, reunimos um arsenal de ferramentas úteis para operar e gerenciar sistemas. Enquanto essas ferramentas podem resolver muitos tipos de problemas de computação, ainda estamos limitados a usá-los um por um na linha de comando/prompt. Não seria ótimo se pudéssemos utilizar o Shell para fazer mais de um trabalho? Bem, na verdade, podemos. Juntando nossas ferramentas/comandos dentro de programas desenvolvidos por nós mesmos, o shell pode realizar sequências complexas de tarefas por si só. Podemos disponibilizar isto com scripts de shell.

Em termos mais simples, um **script shell** é um arquivo contendo uma série de comandos. O SHELL (bash -**bourne-again shell**, por exemplo) lê este arquivo e executa os comandos como se eles fossem inseridos diretamente/manualmente no prompt/linha de comando. O shell é um tanto único, na medida em que é uma interface de linha de comando poderosa para o operar o sistema operacional e, ao mesmo tempo, um intérprete de linguagem script. Como veremos, a maioria das coisas que podem ser feitas na linha de comando, podem ser feitas em scripts e a maioria das coisas que podem ser feitas em scripts podem ser feitas na linha de comando/prompt. Durante o curso, temos abordado muitos recursos de shell, mas nós nos concentramos nestes recursos usados com mais freqüência diretamente na linha de comando. O shell também fornece um conjunto de recursos normalmente, mas nem sempre, usados para escrever programas. [1]

### Escrevendo um programa Shell Script

Para criar e executar com êxito um script de shell, precisamos fazer três coisas:

- Escrever um script. Os scripts de shell são arquivos de texto comuns. Portanto, precisamos de um editor de texto para escrevê-los. Os melhores editores de texto fornecerão realce de sintaxe, permitindo ter uma visão codificada por diferenciação em cores dos elementos do script. O realce de sintaxe ajudará a acharmos certos tipos de erros comuns. Vim, gedit, kate e muitos outros editores são bons candidatos para escrever scripts.
- Tornar o script executável. O sistema é bastante exagerado sobre não deixar qualquer velho texto ser tratado como um programa, e por uma boa razão! Precisamos definir as permissões do arquivo do script para permitir a execução.
- Colocar o script em algum lugar onde o **shell** possa encontrá-lo. O shell procura automaticamente em determinados diretórios por arquivos executáveis? quando nenhum caminho explícito é especificado. Para melhor conveniência, colocaremos nossos scripts nesses diretórios.

De acordo com a tradição de ensino de programação, criaremos um programa "hello world" para fazermos nosso primeiro script. Então vamos acionar nossos editores de texto (Eu usarei o VIM, mas pode usar o que melhor lhe convier) e digitar o seguinte roteiro:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/6/873678/36624.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/6/873678/36624.png)

A última linha do nosso script é bastante familiar, apenas um comando de **echo** com uma string como argumento. A segunda linha também é familiar. Parece um comentário que vimos usado em muitos dos arquivos de configuração que examinamos e editamos. Uma coisa sobre comentários em shell scripts é que eles também podem aparecer nas extremidades das linhas, assim:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/6/873680/36625.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/6/873680/36625.png)

Tudo a partir do símbolo # para a frente na linha é ignorado. Como muitas outras coisas, isso também funcionou na linha de comando, como você viu acima. Embora os comentários sejam de pouco uso na linha de comando, eles funcionam.A primeira linha do nosso roteiro é um pouco estranha. Parece que deve ser um comentário, uma vez que começa com #, mas você não acha que parece um comando importante. A sequência de caracteres #! É de fato uma construção especial chamada **shebang**. O shebang é usado para dizer, ao sistema, o nome do interpretador que deve ser usado para executar o script a seguir. Cada script shell deve incluir isso como sua primeira linha. Apenas para o leitor não ficar imaginando a simbologia do termo, **shebang** é uma palavra norte-americana do século 19 e basicamente significa: “tudo que interessa para as circunstâncias”

Vamos salvar nosso arquivo de script como hello_world.

Já fizemos o primeiro passo para criar um shell script, agora vamos transformá-lo em um arquivo “executável”. Veja bem, não estamos falando aqui de uma linguagem de alto nível quando, então, tornar executável significaria compilar e linkeditar. Estamos falando de uma sequência de comandos em formato de texto que, para tornar executável, apenas precisamos avisar ao sistema operacional que este arquivo texto tem permissão para ser interpretado pelo shell. Veja abaixo como fazemos isto:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/6/873682/36628.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/6/873682/36628.png)

Viu acima como ficaram as permissões? Há duas configurações de permissão comuns para scripts; 755 para scripts que todos podem executar, e 700 para scripts que somente o proprietário pode executar. Observe que os scripts devem ser legíveis (readable) para serem executados.

Já criamos o arquivo, tornamo-lo executável e, agora, o terceiro passo garantir que ele está num lugar que pode ser encontrado. Aqui está na área de trabalho do usuário. Vamos executá-lo. Observe abaixo que para executá-lo precisamos colocar um “path”, mesmo que o arquivo estiver localizado no mesmo diretório, o bash exige ver um path antes. Isto poderia ser facilmente modificado no shell (no caso o bash) mas, acho que você já percebeu, o pessoal do Linux gosta de ser tradicionalista, pois o programa poderia primeiro tentar acha no próprio diretório. Então, para evitar problemas com o path, colocamos “./” antes do nome do programa, caso contrário ocorrerá a falha que aparece abaixo, na primeira tentativa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/7/873788/36629.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/7/873788/36629.png)

O que torna nosso script diferente de outros programas? Como pode-se ver, não fizemos nada errado no nosso roteiro. Sua localização é o problema. A questão está na variável de ambiente PATH e seu efeito sobre como a procura de programas no sistema. Para recapitular, o sistema procura numa lista de diretórios cada vez que precisa encontrar um executável, se nenhum caminho explícito for especificado. É assim que o sistema sabe executar o programa “ls”, ou vários outros, quando escrevemos ls na linha de comando. O comando **ls** é um programa que está no diretório /bin que é um dos diretórios conhecidos onde existem executáveis. Esta lista de diretórios é mantida dentro de uma variável de ambiente chamada PATH. A variável PATH contém uma lista de diretórios a serem pesquisados, separada por dois pontos (:). Podemos ver o conteúdo de PATH com o seguinte comando:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/7/873790/36630.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/7/873790/36630.png)

Aqui (acima) nós vemos nossa lista de diretórios. Se o nosso script estiver localizado em qualquer um dos diretórios da, nosso problema seria resolvido. Observe o terceiro diretório na lista, /usr/bin. A maioria das distribuições do Linux configura a variável PATH para **bin** no diretório **usr**, para permitir que os usuários executem seus próprios programas. Então, se colocarmos nosso script dentro dele, ele deve começar a trabalhar como os outros programas, sem precisar o “./”:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/7/873792/36631.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/7/873792/36631.png)

### Melhores localizações para scripts

O diretório ~/bin é um bom lugar para colocar scripts destinados ao uso pessoal. Se escrevemos um script que todo mundo em um sistema tem permissão para usar, o local tradicional seria /usr/local/bin. Os scripts destinados ao administrador do sistema são localizados frequentemente em /usr/local/sbin. Na maioria dos casos, os softwares produzidos localmente, ou seja: scripts ou programas compilados, devem ser colocados no diretório     /usr/ local e não em /bin ou /usr/bin. Esses diretórios são especificados pelo _**Linux Filesystem Hierarchy Standard**_ para conter apenas arquivos fornecidos e mantidos pelo distribuidor Linux.

Algumas dicas de formatação:

- **Comentários**

Um dos principais objetivos da escrita de scripts sérios é a facilidade de manutenção; isto é, a facilidade com que um script pode ser modificado pelo seu autor ou outros para adaptá-lo às necessidades em mudança. Muito do progresso do Linux vem da disseminação e melhoramento contínuo de scripts. Fazer um script fácil de ler e entender é uma maneira de facilitar a manutenção fácil. Abuse de comentários e espaços entre as linhas e grupos de instruções, pois o interpretador não perde qualquer tempo com leitura de comentários ou linhas em branco.

- **Nomes de opções longas**

Muitos dos comandos que estudamos possuem nomes de opções curtos e longos. Por exemplo, o comando **ls** tem muitas opções que podem ser expressas em formato curto ou longo. Por exemplo: **ls -ad é** equivalente a **ls** **--all** **--directory**.

A favor de digitação reduzida, as opções curtas são preferidas no comando de linha, mas, ao escrever scripts, as opções longas podem fornecer melhor legibilidade.

- **Indentação e continuação de linha**

Ao utilizar comandos longos, a legibilidade pode ser melhorada através do espalhamento do comando em várias linhas. Vamos examinar um exemplo particularmente longo de comando:

**find meu_arquivo\( -type f -not -perm 0700 -exec**

**chmod 0700 ‘{}’ ‘;’ \) -or \( -type d -not -perm 0755 -exec chmod**

**0755 ‘{}’ ‘;’ \)**

Olhando assim, numa primeira vista, é difícil entender este comando. Precisamos sempre deixar um script o mais legível possível. Vamos escrevê-lo de outra maneira, como segue:

`1.` `find meu_arquivo \` `2.` `\( \` `3.` `-type f \` `4.` `-not -perm 0600 \` `5.` `-exec chmod 0600 ?{}? ?;? \` `6.` `\) \` `7.` `-or \` `8.` `\( \` `9.` `-type d \` `10.` `-not -perm 0700 \` `11.` `-exec chmod 0700 ?{}? ?;? \` `12.` `\)`

Usando continuações de linha (sequências de backslash(\) + pula linha) e indentação, a lógica deste comando complexo é mais claramente descrita para o leitor. Esta técnica funciona na linha de comando, também, embora raramente seja usada, pois é muito difícil digitar e editar desta maneira diretamente no prompt. Uma diferença entre um script e uma linha de comando é que o script pode usar **tab** para obter indentação, enquanto que a linha de comando não pode, uma vez que os **tab?s** são usadas para ativar a conclusão automática do comando.

- **Automatizando o editor de texto para Scripts Shell.**

Podemos deixar o editor preparado para ser um grande assistente na confecção de scripts. Isto assemelha-se aos estúdios (.NET Studio, Visual Basic Studio,etc.). Basta configurá-lo.

O editor de texto **vim** tem muitas configurações, por tal motivo que eu prefiro usá-lo. Existem várias opções comuns que podem facilitar a escrita de scripts:

**:syntax on**

Ativa o realce de sintaxe. Com esta configuração, diferentes elementos da sintaxe do shell serão exibidos em cores diferentes ao exibir um script. Isso é útil para identificar certos tipos de erros de programação. A aparência é bem legal, também. Note que, para este recurso funcionar, você deve ter uma versão completa do vim instalado e o arquivo que você está editando deve ter um shebang indicando que o arquivo é um script shell. Se você tem dificuldade com o comando acima, tente :**set syntax = sh**.

**: Set hlsearch**

Ativa a opção para realçar os resultados da pesquisa. Digamos que procuremos a palavra "world". Com esta opção ativada, cada instância da palavra será destacada.**: Set tabstop = 4**Define o número de colunas ocupadas por um caractere de tabulação. O padrão é 8 colunas. Definir o valor como 4 (o que é uma prática comum) permite que as linhas longas apareçam facilmente na tela.**: Set autoindent**Ativa o recurso de "indentação automática". Isso faz com que o **vim** gere indentação numa nova linha a mesma quantidade de colunas da linha anterior sem precisar do tab. Isso acelera a digitação em muitos tipos de construções de programas. Para interromper a indentação automática, digite Ctrl-d.

Essas alterações podem ser permanentes adicionando esses comandos sem os dois pontos no arquivo **~ /.vimrc**.

Até aqui, neste tópico sobre scripts shell, examinamos como os scripts são escritos e feitos para serem executados facilmente em nosso sistema. Também vimos como podemos usar várias técnicas de formatação para melhorar a legibilidade e, portanto, a manutenção de nossos scripts.  Agora vamos usar esta facilidade de manutenção repetidas vezes, como um princípio centrado na qualidade de escrita de scripts para produzir programas profissionais.

### Criando um programa completo.

Iniciando com esta etapa, vamos começar a construir um programa. O objetivo deste programa completo é ver como vários recursos do shell são usados para criar programas e, mais importante, criar bons programas.

O programa que vamos escrever é um gerador de relatórios (este exemplo é usado em todos os livros de treinamento em Linux porque pode-se ver todas as possibilidades de uso de scripts com ele). Ele apresentará várias estatísticas sobre nosso sistema e seu status e produzirá este relatório em formato HTML, para que possamos visualizá-lo com um navegador da Web, como o Firefox ou o Chrome.

Os programas serão construídos em uma série de etapas, por questões didáticas, com cada etapa adicionando novos recursos e capacidades. A primeira etapa do nosso programa produzirá um documento HTML mínimo que não contém nenhuma informação do sistema. Isso virá depois.

Primeiro vamos ver um exemplo de um documento html:

`1.` `<HTML>` `2.` `<HEAD>` `3.` `<TITLE>Título da Página</TITLE>` `4.` `</HEAD>` `5.` `<BODY>` `6.` `Corpo da Página.` `7.` `</BODY>` `8.` `</HTML>`

Se você salvar isto em um arquivo, por exemplo teste.html e executar com o firefox, por exemplo, verá que está tudo certo. Veja abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873807/36632.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873807/36632.png)

A primeira etapa do nosso programa será capaz de produzir este arquivo HTML como saída padrão. Podemos escrever um programa para fazer isso muito facilmente. Vamos iniciar o nosso editor de texto e criar um novo, um arquivo chamado “relatorio” e escrever o que está aparecendo abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873811/36633.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873811/36633.png)

Começamos com este programa simples que contém um shebang, um comentário (não esqueça, comentários são fundamentais para programas bem feitos) e uma sequência de comandos de **echo**, um para cada linha de saída. Depois de salvar o arquivo, vamos torná-lo executável e tentar executá-lo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873816/36634.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873816/36634.png)

Mais interessante ainda, podemos direcionar a saída do programa para uma página html.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873822/36635.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/3/8/873822/36635.png)

Ao escrever programas, é sempre uma boa ideia optar por simplicidade e clareza. A manutenção é mais fácil quando um programa é fácil de ler e entender, para não mencionar que pode tornar-se mais fácil de escrever, reduzindo a quantidade de digitação. Nossa versão atual do programa funciona bem, mas poderia ser mais simples. Poderíamos realmente combinar todos os comandos de **echo** em um, o que certamente tornará mais fácil adicionar mais linhas à saída do programa. Então, vamos mudar o nosso programa:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839355/36636.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839355/36636.jpg)

Uma sequência entre aspas pode incluir novas linhas e, portanto, conter várias linhas de texto. O shell continuará a ler o texto até encontrar as aspas de fechamento. Funciona desta forma na linha de comando, também, mas aparece o símbolo “>” na frente das linhas novas. O caractere principal ">" é o prompt do shell contido na variável de shell PS2. Ele aparece sempre que digitamos uma instrução de várias linhas no shell. Este recurso é um pouco estranho agora, mas, mais tarde, quando cobrimos declarações de programação multi-line, ele vai acabar sendo muito útil.

Agora que nosso programa pode gerar um documento mínimo, passemos para a segunda etapa. Vamos colocar alguns dados no relatório. Para fazer isso, já fizemos as seguintes alterações. Adicionamos um título de página e um cabeçalho ao corpo do relatório, como podemos ver abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839356/36637.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839356/36637.jpg)

### Introduzindo variáveis e constantes

Há um problema com o nosso script, no entanto. Observe como a sequência de caracteres "Relatório do Sistema" é repetida? Com o nosso minúsculo script não é um problema, mas vamos imaginar que a nosso script é muito longo e tivemos várias instâncias desta sequência de caracteres. Se quiséssemos mudar o título para outra coisa, teríamos de mudá-lo em vários lugares, o que poderia ser uma semana de trabalho. E se pudéssemos organizar o script para que a sequência só aparecesse uma vez e não várias vezes? Isso tornaria a manutenção futura do script muito mais fácil. Eis como poderíamos fazer isso:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839357/36638.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839357/36638.jpg)

Ao criar uma variável denominada ?**titulo**? e atribuindo-lhe o valor "Relatorio do Sistema", podemos aproveitar a distribuição do parâmetro e colocar a string em vários locais. Então, como criamos uma variável? Simples, nós apenas a usamos. Quando o shell encontra uma variável, ele a cria automaticamente. Isso difere de muitas linguagens de programação nas quais as variáveis devem ser explicitamente declaradas ou definidas antes do uso. O shell é muito ?tranquilo? sobre isso, o que pode levar a alguns problemas. Por exemplo, considere este cenário na linha de comando:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839358/36639.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839358/36639.jpg)

Primeiro atribuímos o valor "Aqui tem um Valor" à variável ?**valo**?, e então exibimos seu valor com **echo**. Em seguida, mostramos o valor do nome da variável mal escrito como "valor" e obtemos um resultado em branco. Este tipo de erro é fácil acontecer, por isso a escolha da palavra **valor**, neste exemplo. O problema ocorre porque o shell felizmente criou a variável ?**valor**? quando você usou, e deu-lhe o valor padrão de nada, ou vazio. A partir disso, aprendemos que devemos prestar muita atenção à nossa ortografia! Também é importante entender o que realmente aconteceu neste exemplo. O **?$?** provoca algo que, em programação de alto nível, é chamado **macrosubstituição,** quer dizer, antes de considera o comando como um todo, o sistema substitui a digitação original pelo comando já substituído pelo valor da variável. Atualmente e especificamente em SHELL SCRIPT, chama-se de **expansions**.

### Regras sobre nomes de variáveis

1. Os nomes das variáveis podem consistir em caracteres alfanuméricos (letras e números) e caracteres de sublinhado/underline.
2. O primeiro caractere de um nome de variável deve ser uma letra ou um sublinhado. (Não pode ser um número)
3. Não são permitidos espaços e símbolos de pontuação.

A palavra "variável" implica em um valor que muda, e em muitas aplicações, as variáveis são usadas dessa maneira. No entanto, a variável em nosso aplicativo, título, é usado como uma constante. Uma constante é exatamente como uma variável em que ela tem um nome e contém um valor. A diferença é que o valor de uma constante não muda. Em um programa podemos definir PI como uma constante, e atribuir-lhe o valor de 3.1415, em vez de usar o número literalmente em todo o nosso programa. O shell não faz distinção entre variáveis e constantes. Eles são deixados para a melhor conveniência do programador. Uma convenção comum é usar letras maiúsculas para designar constantes e letras minúsculas para variáveis propriamente ditas. Vamos alterar o nosso script para cumprir esta convenção. Veja abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839361/36640.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839361/36640.jpg)

Também aproveitamos a oportunidade para aumentar o nosso título ao adicionar o valor da variável de shell HOSTNAME. Este é o nome da rede da máquina/computador.  Variáveis de shell são variáveis pré-estabelecidas pelo sistema, consulte os sites de linux para ver quais são estas variáveis. Logo em seguida mostraremos mais algumas que serão úteis para nosso trabalho.

O shell realmente fornece uma maneira de impor a imutabilidade de constantes, através do uso do comando **declare builtin** com a opção -r (somente leitura). Se tivéssemos atribuído TITULO desta forma:

**declare -r TITULO = "Relatorio do Sistema"** ;

O shell evitará qualquer atribuição subsequente a TITULO. Esse recurso é raramente usado, mas existe para scripts muito formais.

### Atribuindo Valores a Variáveis? e Constantes

Aqui é onde o nosso conhecimento de **expansions** realmente começa a se pagar. Como vimos, as variáveis são atribuídos valores desta forma:                        **variável = valor,**Onde variable é o nome da variável e o valor é uma string. Ao contrário de algumas outras linguagens de programação, o shell não se preocupa com o tipo de dados atribuídos a uma variável; trata-os todos como strings. Você pode forçar o shell a restringir a atribuição a números inteiros usando o comando **declare** com a opção **-i**, mas, como definir variáveis como readonly (**-r**), isso raramente é feito. Observe que em uma atribuição, não deve haver espaços entre o nome da variável, o sinal de igual e o valor. Então, em que consiste o valor? Qualquer coisa que possamos expandir em uma sequência. Veja exemplos abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839363/36641.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839363/36641.jpg)

Olhe calmamente a figura acima. Percebe a flexibilidade e, principalmente, as possibilidades infinitas de combinações que são permitidas para nossa programação? A criatividade e a necessidade são o seu limite em termos de programação shell script.

Aproveitamos esta oportunidade para adicionar alguns dados ao nosso relatório, mostrando a data, a hora em que o relatório foi criado e o nome de usuário proprietário. Veja abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839365/36642.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839365/36642.jpg)

Veja abaixo como ficou:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839368/36643.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839368/36643.jpg)

Agora você pode ver como realmente as variáveis funcionam.

Neste nosso programa usamos duas formas de mandar dados para algum uso, no caso, linhas em formato html. As duas formas usaram o comando **echo**.

Há uma terceira maneira chamada “**here document”** ou “**here script”** (vamos chamar de **heredoc** de agora em diante para facilitar e também porque é o nome usual no meio de programadores). Não há uma tradução boa para heredoc em português, pois o termo vem do tempo de teletipos e terminais tty, mas, para você ficar com algo válido na cabeça, pense como se fosse o equivalente a **“literal”**. Um heredoc é uma forma adicional de redirecionamento de E/S (entrada e saída) em que incorporamos um texto em nosso script e o alimentamos na entrada padrão de um certo comando. Funciona assim:

**comando << símbolo**

**Texto a ser passado para o comando**

**símbolo**

Onde **comando** é o nome do comando que aceita a entrada (**texto**) padrão e **símbolo** é uma sequência de caracteres usada para indicar o começo e o final do texto incorporado. Modificaremos nosso script para usar um heredoc. Veja como ficou abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839370/36646.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839370/36646.jpg)

Em vez de usar o **echo**, nosso script agora usa o **cat** e um **heredoc**. A string _INICIO_FIM_ foi selecionada como **símbolo** e marca o final do texto incorporado. Observe que o símbolo deve aparecer sozinho e que não deve haver espaços à direita na linha (cuidado). Aqui usei o _INICIO_FIM_ para não haver confusões entre palavras reservadas de sistema etc. Quis caracterizar que pode ser qualquer palavra, inclusive o caractere **“_”** (underline) não é necessário. No entanto, o símbolo usualmente utilizado, quase como uma convenção, é o “**_EOF_**”, que significa **End of File**.

Então, qual é a vantagem de usar um **heredoc**?

É principalmente o mesmo que o echo, exceto que, por padrão, aspas simples e duplas dentro de **heredoc’s** perdem seu significado especial para o shell. E, assim, você pode usar aspas para seus próprios textos e comandos. Veja abaixo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839371/36647.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/9/3/839371/36647.jpg)

Como podemos ver, o shell não presta atenção às aspas. Trata-os como personagens comuns. Isso nos permite inserir aspas livremente dentro de um documento aqui. Isso pode vir a ser útil para o nosso programa de relatório.

### Melhorando nosso Script

Nosso script atualmente executa as seguintes etapas para gerar o documento HTML:

1. Abra a página.
2. Abra o cabeçalho da página.
3. Definir o título da página.
4. Fechar o cabeçalho da página.
5. Abra o corpo da página.
6. Cabeçalho da página de saída.
7. Saída timestamp.
8. Fechar corpo da página.
9. Fechar a página.

Para o próximo estágio de desenvolvimento, adicionaremos algumas tarefas entre os passos 7 e 8.  O que será incluído?

- Tempo de funcionamento do sistema e carga (_**System uptime and load**_). Esse é o período de tempo desde o último desligamento ou reinicialização e o número médio de tarefas atualmente em execução no processador em vários intervalos de tempo.
- Espaço em disco (_**Disk space**_). O uso geral do espaço nos dispositivos de armazenamento do sistema.
- Espaço residente por usuário (_**home space**_). A quantidade de espaço de armazenamento que está sendo usado por cada usuário.

Se tivéssemos um comando para cada uma dessas tarefas, poderíamos adicioná-las ao nosso script simplesmente através da substituição de comandos como você pode ver abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840748/36648.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840748/36648.jpg)

Poderíamos criar esses comandos adicionais de duas maneiras. Poderíamos escrever três scripts separados e colocá-los em um diretório listado em nosso PATH, ou no corrente, ou poderíamos incorporar os scripts dentro do nosso programa como **funções** de shell. As funções shell são "mini-scripts" que estão localizados dentro de outros scripts e podem atuar como programas autônomos. As funções do shell têm duas formas sintáticas. Primeiro, a forma mais formal:

`1.` `function nome_da_funçao {` `2.` `Comandos da função` `3.` `return` `4.` `}`

E a forma mais simples, que geralmente é a mais usada:

`1.` `Nome_da_função () {` `2.` `Comandos da função` `3.` `return` `4.` `}`

`1.` `Nome_da_função () {` `2.` `Comandos da função` `3.` `return` `4.` `}`

`1.` `Nome_da_função () {` `2.` `Comandos da função` `3.` `return` `4.` `}`

Onde **nome_da_funçao** é o nome da função (ãh?) e comandos da função são uma série de comandos contidos dentro da função. Ambas as formas são equivalentes e podem ser usadas indistintamente. Abaixo vemos um script que demonstra o uso de uma função shell (chamei este arquivo de “**funcoes**”):

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840751/36649.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840751/36649.jpg)

Agora veja o resultado do script => **NÃO ESQUEÇA DE TORNAR O ARQUIVO EXECUTÁVEL**

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840754/36650.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840754/36650.jpg)

Vamos usar o comando **nl** (mostrar o arquivo com o número da linha na frente) para você ver o que está acontecendo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840766/36651.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/7/840766/36651.jpg)

À medida que o shell lê o script, ele passa sem fazer nada sobre as linhas de 1 a 10, pois essas linhas consistem em comentários e a definição de alguma função. A execução começa na linha 11, com uma chamada de função, a **funcao1**. Na linha 12 chama-se a função de shell **funcao2** e o shell executa ambas as funções exatamente como qualquer outro comando. No momento que tenta executar **funcao1**, o shell pula para a linha 4 e, no caso da **funcao2**, pula para a linha 8.

O controle de programa move-se para os comandos contidos na função e então executa aqueles comandos **echo**.  Em seguida, após o **echo,** as linhas 5 e 9, respectivamente, são executadas.

O comando de retorno (**return**) encerra cada função e retorna o controle ao programa na linha que segue a chamada de cada função (linhas 12 e 13, respectivamente), e o comando de **echo** final é executado (linha 13).

Observe que, para que as chamadas de função sejam reconhecidas como funções de shell e não interpretadas como os nomes de programas externos, as definições de função de shell devem aparecer no script antes de serem chamadas. Vamos adicionar definições mínimas de função de shell ao nosso script de relatório:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840838/36652.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840838/36652.jpg)

Os nomes das funções shell seguem as mesmas regras que as variáveis, além disto, uma função deve conter pelo menos um comando. O comando de **return,** que não é obrigatório, satisfaz uma função completa, conforme visto na figura acima.

### Variáveis Globais e Locais

As variáveis obedecem ao mesmo conceito da maioria das linguagens de programação que possuem funções ou subrotinas, ou seja, se uma variável é definida (um valor é atribuído a ela) no corpo principal do script, o valor atribuído em qualquer momento que a variável for usada no corpo principal do script será o mesmo. Se a variável é definida dentro de alguma função, o valor se manterá apenas dentro da função. Assim que a função terminar de ser executada, mesmo que o nome da variável seja o mesmo que uma variável global, a variável global será sempre mantida. Veja isto mais claro no exemplo abaixo (vamos usar aquele nosso programa “funcoes”).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840845/36653.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840845/36653.jpg)

Como pudemos ver, as variáveis? locais são definidas precedendo o nome da variável com a palavra **local**. Isso cria uma variável que é local para a função de shell na qual ela é definida. Uma vez fora da função shell, a variável não existe mais. Quando executamos esse script, vemos os resultados:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840851/36654.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840851/36654.jpg)

Uma das grandes vantagens do uso de variáveis locais é que a função fica totalmente isolada de interferências do resto do script. Por tal motivo, fica fácil copiar funções completas e introduzi-las em outros programas.

Uma dica para a boa programação e, ainda, para o menor tempo de manutenção de falhas, é sempre executar o programa em cada modificação feita. Com isto podemos pegar uma falha no início absoluto, pois, se ocorrer um erro logo após alguma alteração, temos certeza de onde o problema foi introduzido, ou que parte do programa influenciou o aparecimento do problema. No nosso script “**relatorio**” colocamos as funções para que a chamada das funções não causasse erro e, ao mesmo tempo, a lógica do programa fosse testada. Estas funções vazias são muito úteis para todo tipo de programação e, na linguagem de programadores, chamamos isto de “**stubs**”.

### Completando o SCRIPT

Agora já estamos prontos para criar o código de cada uma daquelas funções. Veja abaixo, quando colocamos cada um dos comandos necessários para o relatório. Veja que acrescentamos cabeçalhos para cada função na página e que se trata de comandos simples de uso corriqueiro.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840861/36655.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840861/36655.jpg)

Vamos ver o resultado abaixo. Podemos executar o programa direcionando a saída para um arquivo (aqui relato.html) e executá-lo direto no firefox.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840862/36656.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840862/36656.jpg)

Este foi, portanto, um programa completo. O leitor pode ver como se programa com qualidade e profissionalismo. Ao mesmo tempo, pode-se vislumbrar com este script, a potencialidade do shell script. Geralmente as pessoas subestimam o shell script e limitam-se a produzir pequenas tarefas representadas por pequenos grupos de comandos para automatizar processos rotineiros, como, por exemplo, trocar a **rota default,** ou montar **VPNs**, mas na verdade, podemos fazer muito mais. [2].

Vamos montar pequenos programas para demonstrar mais opções desta linguagem tão rica.

### Entrada de Dados pelo teclado.

Até agora criamos uma série de linhas de programa, mas as variáveis sempre são produzidas dentro do programa. Como entrar com os valores pelo teclado?

A primeira forma de entrar com dados em um script é através de **“argumentos”**. Para o script são argumentos e para quem está chamando ou executando o script chamam-se opções.  No shell script um argumento que foi entrado/digitado como uma opção do programa é lido através das seguintes tags:

- **$0** – Retorna o nome do script que foi executado
- **$N** – Onde N é um número, corresponde ao argumento passado (1 = primeiro argumento, 2 = segundo argumento, 3 = terceiro argumento, etc)
- **$*** – Retorna todos os argumentos de uma vez.
- **$#** – Retorna à quantidade de argumentos passados para o script. (_argc_)

Vamos direto para um exemplo, assim tudo vai ficar bem claro.

Digamos que queremos automatizar o ato de criar um outro ip na interface eth1. O comando abaixo seria o necessário para criar o novo alias da interface e o ip desejado. A máscara seria a máscara padrão, para aquela classe de ip.

**Ifconfig eth1:nova 10.10.10.1**

Bom, mas não queremos digitar tudo isto cada vez que queremos criar estas novas interfaces. Queremos poder criar o nome/alias da interface simplesmente digitando o alias e o ip. Veja o programa abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840868/36657.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/4/0/8/840868/36657.jpg)

Veja abaixo como o programa faz o que promete:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859728/1-01.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859728/1-01.png)

Agora vamos aproveitar o mesmo programa para demonstrar uma outra forma de entrar com os dados pelo teclado. Vamos usar o **read** que tem a sintaxe abaixo:

**read [-opções] [variável...]**

Veja como alteramos nosso programa:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859730/1-02.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859730/1-02.png)

E veja como é eficiente:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859732/1-03.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859732/1-03.png)

Leia o manual do **bash** e veja como existem muitas opções para o **read**.

### Controle de Fluxo, laços e Lógica em Shell Script

Um programa para realmente atingir os níveis de programação realmente útil e realizar grandes tarefas, precisa ter seu fluxo controla. Para controle de fluxo temos o “**if**” (além do “**case”** que não demonstraremos aqui), para execução de laços temos o “**while**” (além do “**for”** que não demonstraremos aqui).

Vamos demonstrar todas estas opções em apenas um programa.

O **if** tem a seguinte sintaxe:

`1.` `if [ CONDIÇÕES ];` `2.` `then` `3.` `Comandos se CONDIÇÕES resulta em verdadeiro...` `4.` `else` `5.` `Comandos se CONDIÇÕES resulta em falso....` `6.` `fi`

Vamos ver um exemplo simples:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859735/1-04.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859735/1-04.png)

No operador lógico da condição, seguimos a tabela abaixo:

- **n** string1: o comprimento de string1 é diferente de 0;
- **z** string1: o comprimento de string1 é zero;
- string1 **=** string2: string1 e string2 são idênticas;
- string1 **!=** string2: string1 e string2 são diferentes;
- inteiro1 **eq** inteiro2: inteiro1 possui o mesmo valor que inteiro2;
- inteiro1 **ne** inteiro2: inteiro1 não possui o mesmo valor que inteiro2;
- inteiro1 **gt** inteiro2: inteiro1 é maior que inteiro2;
- inteiro1 **ge** inteiro2: inteiro1 é maior ou igual a inteiro2;
- inteiro1 **lt** inteiro2: inteiro1 é menor que inteiro2;
- inteiro1 **le** inteiro2: inteiro1 é menor ou igual a inteiro2;
- **e** nome_do_arquivo: verifica se o arquivo existe;
- **d** nome_do_arquivo: verifica se o arquivo é um diretório;
- **f** nome_do_arquivo: verifica se o arquivo é um arquivo regular.

Já o “**while**” tem a sintaxe como segue:

`1.` `while [ CONDIÇÕES ];` `2.` `do` `3.` `Comandos enquanto CONDIÇÕES continua sendo verdadeiro...` `4.` `done`

Vamos ver um exemplo simples (salvamos este programa com o nome **prog_while**). Abaixo um programa que lê linha a linha o nosso programa “**prog_if**”, o qual foi usado para demonstrar o uso do “**if**”.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859738/1-05.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859738/1-05.png)

Veja o resultado quando executamos este programa.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859740/1-06.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/5/9/7/859740/1-06.png)

Paralelamente você pode aproveitar e ver uma **terceira forma de entrada de dados**, via arquivo.

Com estes laços e o controle de fluxo, pode-se criar um conjunto de poderosas ferramentas feitas por você mesmo. Você pode executar um comando cuja a saída é direcionada para um arquivo texto e através da leitura destes arquivos texto fornecer informações de maneira a ajudar o gerenciamento de toda a infraestrutura de uma empresa, criar inventários de equipamentos, além de tomar decisões e produzir ações automáticas. Como já falei, o limite é sua criatividade somado a suas necessidades.

Procure informações em sites e no manual do bash (man bash). São mais de cinco mil linhas de informação.