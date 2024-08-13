### Filtrando do Linux

Um dos princípios adicionais do Linux é que cada item deve fazer uma coisa e uma única coisa e que podemos facilmente juntar esses itens em comandos compostos[1] e [2]. Pense nisso como um conjunto de blocos de construção que podemos colocar juntos. Portanto, podemos de construir qualquer coisa que queremos. Neste tópico, vamos aprender sobre alguns desses blocos de construção. Então, veremos como podemos construí-los em criações mais complexas que podem fazer um trabalho útil para nós.

Um filtro, no contexto da linha de comando do Linux, é um programa que aceita dados textuais e depois transforma-o de uma maneira específica. Filtros são uma maneira de tomar dados brutos, produzidos por outro programa, ou armazenados em um arquivo, e manipulá-los para serem exibidos de uma forma mais adequada para o que queremos saber, ou apresentar.

Esses filtros geralmente têm várias opções de linha de comando que modificarão seu comportamento, por isso sempre é bom consultar o manual de cada filtro para ver o que está disponível.

Nos exemplos abaixo estaremos fornecendo entrada para esses programas por um arquivo, mas logo depois, quando tratarmos de Piping e Redirecionamento, veremos que podemos fornecer entrada por outros meios que adicionam muito mais rapidez.

Vamos nos aprofundar e apresentar alguns deles, mas lembre-se: os exemplos aqui só lhe darão uma amostra do que é possível com esses comandos. Certifique-se de explorar e usar sua criatividade para ver o que mais você pode fazer com eles.

Para cada uma das demonstrações abaixo vou usar o seguinte arquivo como um exemplo: exemplofiltro.txt. Este arquivo de exemplo contém uma lista de conteúdo puramente fictício para tornar os exemplos um pouco mais fáceis de entender, mas permitem perceber que eles vão trabalhar do mesmo jeito com, absolutamente, quaisquer outros dados textuais. Além disso, lembre-se que o arquivo é realmente especificado como um caminho e, portanto, você pode usar caminhos absolutos e relativos e também curingas (*). Mais para frente você irá entender bem o que estou querendo dizer.

O arquivo exemplofiltro.txt já está gravado no disco de minha máquina linux. Usando o comando cat é possível visualizá-lo. Procure fazer o mesmo em sua máquina virtual. Aliás, recomendo que você crie uma máquina real linux. O experimento com todas as atividades que faremos com linux será muito mais proveitoso se você o fizer.  Veja abaixo na figura 1 o resultado.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/2/818274/33587.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/1/8/2/818274/33587.png)

### Filtros:

**head**

Head é um programa que imprime as primeiras “x” linhas de seu arquivo (lembre-se, não precisa ser arquivo, pode ser qualquer entrada!). Por padrão, ele irá imprimir as primeiras 10 linhas, mas podemos modificar isso com um argumento de linha de comando.

**head [-number of lines to print] [path]**

Acima, na figura 2 observa-se o comportamento default do comando e, abaixo, na figura 3 pode-se se ver a especificação de quantas linhas queremos mostrar (no caso, 5).

**tail**

_**Tail**_ é o oposto da _**head**_. Cauda é um programa que imprime as últimas tantas linhas de sua entrada. Por padrão, ele irá imprimir as últimas 10 linhas, mas podemos modificar isso com um argumento de linha de comando. Abaixo um exemplo default na figura 4.

**tail [-number of lines to print] [path]**

E abaixo, na figura 5, podemos ver o mesmo comando com a especificação do número de linhas.

Este comando, tail, é muito utilizado pelos administradores de sistemas, pois sempre que ocorre alguma falha, o operador usa o comando rapidamente para ver no console as últimas 10 linhas da log do sistema. Certamente o problema aparecerá lá.

**sort**

Sort classificará sua entrada, sem esforço e extremamente simples. Por padrão, ele irá classificar alfabeticamente, como aparece na figura abaixo, mas existem muitas opções disponíveis para modificar o mecanismo de classificação. Certifique-se de verificar o manual para ver tudo o que pode fazer.

**sort [-options] [path]**

**nl**

Mostra o número da linha de cada item de sua entrada/arquivo

**nl [-options] [path]**

O formato default, como na figura 7 acima já é útil, mas podemos abusar de opções especiais como a da figura 8.

No exemplo acima usamos duas opções de linha de comando. O primeiro, -s, especifica o que deve ser mostrado após o número, enquanto o segundo -w especifica quanto espaços colocar antes dos números. Para o primeiro nó precisamos incluir um espaço como parte do que foi impresso. Como os espaços são normalmente usados como caracteres separadores na linha de comando, precisávamos de uma forma de especificar que o espaço era parte do nosso argumento e não apenas o espaço típico entre argumentos. Fizemos isso, incluindo o argumento cercado por aspas/apóstrofes.

**wc**

Wc significa contagem de palavras e faz exatamente isso (assim como caracteres e linhas. Por padrão, ele dará uma contagem de todos os 3, mas usando opções de linha de comando, podemos limitar a apenas o que queremos. Veja a figura 9 abaixo.

**wc [-options] [path]**

Às vezes você apenas quer um destes valores. -l só mostrará as linhas, -w só mostrará as palavras e -m só mostrará os caracteres. O exemplo abaixo nos dá apenas uma contagem de linha. Figura 10.

Você pode combinar as opções com abaixo, na figura 11, queremos as linhas e as palavras.

**cut**

Cut é um bom programa pequeno para usar se o seu conteúdo é separado em campos (colunas) e você só quer certos campos. Figura 12.

**cut [-options] [path]**

Em nosso arquivo de amostra temos os nossos dados em 3 colunas, o primeiro é um nome, o segundo é um fruto e o terceiro uma quantidade. Digamos que só queríamos a primeira coluna.

O cut padrão usar o caractere TAB como um separador para identificar campos. Em nosso arquivo usamos um único espaço em vez disso, então precisamos dizer para cut usar isso o espaço único em vez disso. O caractere separador pode ser qualquer coisa que você queira, por exemplo, em um arquivo CSV o separador é tipicamente uma vírgula (,). Isto é o que a opção -d faz (incluímos o espaço dentro de aspas simples para que ele saiba que isso é parte do argumento). A opção -f nos permite especificar qual campo ou campos gostaríamos. Se queremos 2 ou mais campos, então separá-los com uma vírgula como abaixo. Figura 13.

**sed**

Sed significa “Stream Editor” e efetivamente nos permite fazer uma pesquisa e substituir dados em nossa entrada/arquivo. É um comando bastante poderoso, mas vamos usá-lo aqui no seu formato básico.

**sed [path]**

A expressão básica é no seguinte formato:

- s/search/replace/g

O “s” inicial (substitui) especifica a ação a executar (há outros, mas por enquanto vamos mantê-lo simples). Em seguida, entre a primeira e segunda barras (/) colocamos o que estamos procurando. Em seguida, entre a segunda e terceira barras, o que é que queremos colocar em substituição. O g no final significa global e é opcional. Se o omitimos, ele só irá substituir a primeira instância de pesquisa em cada linha. Com a opção g, vamos substituir todas as instâncias de pesquisa que estão em cada linha. Vejamos um exemplo. Digamos que acabou cevada e queria em vez disso dar feijão para as pessoas. Veja como fica na figura 14.

É importante notar que sed não identifica palavras, mas sequências de caracteres. Tente executar o exemplo acima, mas substituindo feijões com aõs e você verá o que quero dizer. O termo de pesquisa é também algo chamado de expressão regular, que é um meio para definir um padrão (semelhante aos curingas que vimos). Vamos aprender mais sobre expressões regulares na próxima seção e você pode usá-las para tornar o sed ainda mais poderoso.

Observe também que incluímos nossa expressão entre aspas simples. Fizemos isso para que quaisquer caracteres incluídos nela que possam ter um significado especial na linha de comando não sejam interpretados e executados pela linha de comando, mas em vez disso passam por sed.

Um erro comum é esquecer as aspas simples, caso em que você pode obter algum comportamento estranho da linha de comando. Se isso acontecer, talvez seja necessário pressionar CTRL + c para cancelar o programa e voltar para o prompt.

**uniq**

Uniq significa exclusivo e sua função é remover linhas duplicadas dos dados. Contudo, uma limitação é que essas linhas devem ser adjacentes (isto é, uma após a outra). (Às vezes este não é o caso, mas vamos ver uma maneira podemos corrigir isso com Piping e Redirecionamento).

**uniq [options] [path]**

Vamos dizer que o nosso arquivo de amostra foi realmente gerado a partir de outro programa de vendas, mas depois de uma atualização de software que tinha alguma saída bugada. Veja na figura 15.

Com uniq podemos facilmente arrumar este problema. Veja na figura 16 abaixo.

**tac**

Caros, os desenvolvedores do Linux são conhecidos por ter um senso de humor bem avantajado. O programa tac é realmente cat ao contrário. Foi nomeado assim porque faz o oposto do cat. Ele pegará a entrada/arquivo e apresentará na console iniciando pela última linha e terminando na primeira.

**tac [path]**

Talvez nosso arquivo de amostra tenha sido gerado por um sistema que escreve cada nova ordem de vendas, por exemplo, no final do arquivo. Como resultado, as ordens mais recentes estão no final do arquivo. Gostaríamos que as ordens mais recentes apareçam sempre no topo. Então usamos o tac como abaixo na figura 17.

**Awk**

Awk é quase uma linguagem de filtro. Pode-se fazer testes lógicos e mostrar na tela além de filtragens caractere por caractere. Na figura 18 você pode ver um exemplo. Olhando o manual do comando, você pode adquirir muito poder sobre o manuseio de arquivos.

**Awk ‘{if (lógica) print $campo  [path]**

A lógica pode ser como um “if” na linguagem C e o campo é o número da coluna que se quer mostrar. Na lógica pode-se colocar a referência às colunas igualmente, sempre precedido de um $. Tanto no “if” como no “print” podemos usar vários campos referendados.

**Piping**

Todos os comandos do Linux que apresentam qualquer tipo de consulta em entradas e arquivos podem ser filtrados pelo _**pipe**_. Pode-se criar um pipe simplesmente colocando o símbolo de piping após o comando (|). Além disto pode-se juntar vários comandos desta forma. Veja os exemplos abaixo na figura 19, inclusive usando o _**grep**_ um poderoso filtro para pesquisas.

Agora que você aprendeu várias opções sobre filtros podemos mostrar abaixo exemplos de utilização importante na administração de sistemas.

Observe na figura 20 o uso do comando “ls -lh”, ou seja, liste tudo que há no diretório corrente mostrando todos os detalhes e com o tamanho dos arquivos em forma “humanamente” inteligível (em bytes). Em seguida pede-se o mesmo, mas com um filtro para mostrar diretórios que têm mais que duas entradas em seu interior.

Um outro exemplo seria o seguinte: Quero verificar quando foi a última vez que o sistema “deu” para a minha interface de rede os IPs e definiu algumas características de rede. Sei que quem faz isto é o **NetworkManager** e que mostra isto na log do sistema (**syslog**) em umas 8 linhas. Veja na figura 21 como isto seria útil já que uma log de sistema é muito grande e perderia horas procurando isto.

Agora é uma questão de criatividade e necessidade… estes dois elementos somados farão você ficar um expert em filtros no Linux.