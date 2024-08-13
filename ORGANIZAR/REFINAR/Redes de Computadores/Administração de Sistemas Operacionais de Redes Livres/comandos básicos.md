### Comandos Básicos

Você precisa conhecer alguns comandos básicos do Linux para configurar, operar e interagir com seu sistema sem problemas **[1]**. Ao lidar com o sistema operacional Linux, os comandos são necessários como entradas para informar ou direcionar um programa de computador para executar uma operação específica. Entender os comandos mais básicos do Linux permitirá navegar com êxito diretórios, manipular arquivos, alterar permissões, exibir informações como espaço em disco e muito mais **[2]**. Obter conhecimento básico dos comandos mais comuns irá ajudá-lo a executar tarefas facilmente através da linha de comando.  Além disso os comandos serão necessários para instalar, configurar e operar sistemas de serviços de rede como  DNS, e-Mail, FTP, Web Servers, etc.

Seguem os comandos, descrição e a imagem de execução em uma máquina Linux para que você possa aprender e testar em sua casa.

### cat [filename]

Imprime o conteúdo de arquivos no dispositivo padrão que usualmente é a console.

### cd /directorypath

Muda o diretório. Use as barras (/) para mudar de um diretório para o outro, mas se você coloca barra no início, o sistema acreditará que você quer partir do diretório raiz. Sem a barra inicial parte-se do diretório corrente. Para voltar para o anterior usa-se dois pontos adjacentes (..) observe no exemplo.

### chown [options] filename

Muda quem é o proprietário do arquivo. Veja no exemplo abaixo.

Observe que troquei o proprietário luckgav para root. Também perceba que tive que usar um usuário privilegiado com o comando “sudo”, isto eu explico mais para frente.

### clear 

Limpa a tela do comando de texto. Uso sempre que vou mostrar outro comando para você. Não há necessidade de mostrar aqui.

### cp [options] source destination

Copia arquivos e diretórios. Existem várias opções que valem a pena serem vistas no manual do comando. Algumas coisas importantes para facilitar sua vida são os pontos (.). Se você quer copiar algo de outro diretório para o diretório onde você está basta colocar no “destination” um ponto enquanto no source, você coloca o caminho completo do diretório onde está o arquivo a ser copiado. No exemplo abaixo vou me localizar no diretório Documentos e vou copiar para este diretório o arquivo testblob.py, que está no diretório home/luckgav.

### date [options]

Mostra ou altera a data e a hora.

### df [options]

Mostra o espaço usado e disponível do disco. Veja abaixo.

Aparece cada disco lógico e os espaços usados e disponíveis. Os espaços estão aparecendo na unidade “bloco” que para um usuário comum não significa muito. Se você quer ver em bytes, uma maneira mais humana (h), então use a opção -h como demonstrado abaixo.

### du [options]

Mostra quanto espaço é usado por cada diretório.

### file [options] filename

Determina que tipo de dados há no arquivo.

### find [pathname] [expression] 

Procura arquivos que sigam o padrão da expressão. Incluindo os subdiretórios.

### grep [options] pattern [filesname]

Procura informações dentro arquivos que tenham um determinado padrão. No exemplo abaixo investigo se existe a palavra “blob” dentro do arquivo “testblob.py”. As listas que contêm o que procuro são listadas.

kill [options] pid

Para um processo que esteja sendo executado. No exemplo eu mostro que o processo do editor de texto está executando e forço ele a terminar com a opção -9.

### less [options] [filename]

Vê o conteúdo de um arquivo página por página. Útil em arquivos muito grandes como a log do sistema.

### ln [options] source [destination]

Cria um atalho ou um link.

### locate filename

Procura um arquivo entre todos os seus diretórios e discos. Para atualizar o banco de dados que contém esta informação, caso você tenha recentemente adicionado arquivos em seu filesystem, use o comando **dbupdate.**

### lpr [options]

Send a print job. Se você estiver no diretório que contém aquele link que acabei de criar no comando anterior (ln), o comando “lpr programa” irá mandar diretamente para sua impressora padrão o conteúdo do arquivo testblob.py, pois o link “programa” aponta para testblob.py.

### ls [options]

Lista o conteúdo do diretório corrente ou o diretório que você desejar. Se você usa apenas o comando “ls”, será mostrado apena o nome dos arquivos e diretórios, mas se usar a opção (-l) “longa”, então aparecerão todas as informações de cada arquivo.

### man [command] 

Mostra o manual de cada comando. A tela abaixo refere-se ao comando “_**man clear**_”

### mkdir [options] directory

Cria um novo diretório. Veja antes e depois no exemplo abaixo.

### mv [options] source destination

Renomeia ou move um arquivo para determinado diretório. É importante colocar corretamente o “path” do diretório.

### passwd [name [password]]

O administrador pode mudar a senha do usuário “name”.

### ps [options]

Mostra os processos que estão ocorrendo no computador. Pode ser filtrado para achar algum específico programa, como fiz no exemplo abaixo.

### pwd

Mostra o “path” do diretório corrente.

### rm [options] directory/file

Deleta o arquivo ou diretório. Com a opção -R deleta os arquivos de subdiretórios também.

### rmdir [options] directory

Deleta diretórios vazios.

### ssh [options] user@machine

Pode ser usado para “logar” em outro computador se você sabe o nome do usuário e senha do usuário do outro computador. A máquina pode ser o nome do computador ou o endereço de rede (IP).

### su [options] [user [arguments]]

Muda para a conta de outro usuário. Sem argumentos, muda para o usuário “root”.

### touch filename

Cria um arquivo vazio com o nome especificado.

### who [options]

Mostra que está logado.