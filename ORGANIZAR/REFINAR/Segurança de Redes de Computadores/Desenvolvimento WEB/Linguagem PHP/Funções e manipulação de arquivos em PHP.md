# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/b14b5291-00de-4ba9-8701-7ce06d73dc30/original)](https://ampli-images.s3.amazonaws.com/production/b14b5291-00de-4ba9-8701-7ce06d73dc30/original)

### **Qual é o foco da aula?**

Nesta aula, você irá se aprofundar no desenvolvimento de aplicações web com PHP.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- traçar um formulário HTML interativo.;
- aplicar uma página em linguagem PHP;
- empregar o uso de arquivos e o armazenamento no servidor.

**Situação-problema**

Você já deve ter percebido o quanto a linguagem PHP é rica e oferece recursos para desenvolvimento de aplicações web complexas. Mas algo que ainda não foi explorado é a quantidade de funções que o PHP oferece, as quais são extremamente úteis para oferecer ao desenvolvedor atalhos para diversas funcionalidades. Em vez de o programador ter que codificar do zero tudo o que ele precisa, ele pode utilizar funções prontas que facilitam o desenvolvimento e deixam o código mais limpo. Formatar as casas decimais de um número, substituir uma parte de um texto e verificar se uma data é válida são exemplos de funções oferecidas pela linguagem PHP, as quais serão apresentadas juntamente com muitas outras nesta aula.

Contudo, muitas vezes é necessário criar nossas próprias funções, e isso também será apresentado e exemplificado de forma que você será capaz de deixar seu código muito mais organizado. Por fim, outro recurso importante tratado nesta aula é a manipulação de arquivos, a qual permite que você possa armazenar e ler dados do servidor.

Considere, por exemplo, um site de notícias em que há uma área administrativa para os repórteres postarem conteúdo. Nesse caso, as notícias podem ser armazenadas em arquivos para que os visitantes do site possam acessar dinamicamente. Outro exemplo são sites de fórum, em que usuários podem criar tópicos e postar textos, necessitando que esses textos sejam salvos e posteriormente exibidos de alguma maneira. A maioria dos sites que acessamos hoje em dia costumam salvar ou ler dados, os quais podem ser realizados por meio de arquivos.

A fim de colocarmos em prática os conhecimentos a serem obtidos, vamos analisar a seguinte situação-problema: na startup em que você trabalha solicitaram o desenvolvimento de uma página capaz de auxiliar o usuário a decidir qual o melhor combustível para ele abastecer, considerando o preço do litro da gasolina e do etanol, além de efetuar cálculos levando em consideração o consumo do veículo (9 km/litro de etanol e 11 km/litro de gasolina) e a distância a ser percorrida.

Acontece que essa _startup_ começou a ter um número significativo de acessos e muitos usuários estão pedindo para que o site mostre um relatório contendo o histórico de preço da gasolina e do etanol, já que esses dados estão sendo inseridos pelos usuários frequentemente. Também disseram que os valores deveriam ser formatados com duas casas decimais. Para isso, você terá que armazenar todos os dados inseridos pelos usuários em um arquivo e, posteriormente, terá que desenvolver uma página que mostre esse relatório contendo a data, o valor da gasolina e o valor do etanol. Portanto, para resolver essa situação-problema, você terá que desenvolver uma aplicação web com os seguintes requisitos:

- Formulário HTML em que o usuário digitará o preço da gasolina, o preço do etanol e a distância a ser percorrida.
- Página PHP capaz de receber os dados digitados pelo usuário e calcular o valor gasto de etanol e de gasolina, levando em consideração o consumo de cada um desses combustíveis. Os valores deverão ser exibidos formatados com duas casas decimais. Nessa mesma página deverão ser salvos em um arquivo a data atual, o preço da gasolina e o preço do etanol. O arquivo deverá ser salvo no modo “a”, que indica que o novo conteúdo será adicionado ao conteúdo atual do arquivo.
- Página PHP capaz de abrir o arquivo em que foram salvos os dados para leitura, e deverão ser salvos todos os dados salvos nesse arquivo.

Vamos nos aprofundar ainda mais no mundo do desenvolvimento de aplicações web com PHP. Bons estudos!

# **Funções**

[![](https://ampli-images.s3.amazonaws.com/production/7bcb2a1a-d4d2-4903-a5bc-ade02c328cf6/original)](https://ampli-images.s3.amazonaws.com/production/7bcb2a1a-d4d2-4903-a5bc-ade02c328cf6/original)

A programação de páginas PHP pode incluir desafios na construção do algoritmo, pois envolve uma complexidade no código para satisfazer à lógica desejada. Nesse sentido, é importante organizar o código de forma que o problema seja dividido em partes, as quais chamamos de funções.

Uma função pode ser definida simplesmente como um bloco de código que pode ser executado em diversas partes do seu sistema. Caso o algoritmo apresente partes repetitivas no código, é interessante que se crie uma função, evitando, assim, a duplicidade desse código. Essa técnica é a principal para se fazer a reutilização de código, o que torna o seu sistema mais organizado, com código mais limpo e mais fácil de se dar manutenção.

**Criando uma função**

É possível criar suas próprias funções no PHP definindo o seu nome logo após a palavra reservada _**function**_, além de definir os seus parâmetros e seu valor de retorno. Para o nome de uma função, você deve seguir as mesmas regras das definições de nomes para variáveis:

- Nunca iniciar por um número.
- Não utilizar caracteres especiais (apenas letras não acentuadas, números e _underscore_ _).
- Não utilizar espaços em branco.
- Criar nomes de funções significativas.

A declaração de uma função pode ser realizada conforme na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/7aa2a359-2796-451b-8b54-1e612b7a0d8d/original)](https://ampli-images.s3.amazonaws.com/production/7aa2a359-2796-451b-8b54-1e612b7a0d8d/original)

Funções em PHP. Fonte: elaborado pelo autor.

Logo após definir o nome da função, inserimos os argumentos de **parâmetros**. Esses parâmetros são variáveis que deverão obrigatoriamente ter seu valor passado ao invocar sua função, e esses valores podem ser utilizados dentro do bloco de código da função. Os parâmetros devem ser separados por vírgulas, tanto na declaração da função quanto no momento de executar essa função.

Na figura a seguir podemos observar uma função que recebe dois números, calcula e exibe a média entre esses números. Logo após a definição da função, observe que ela é executada três vezes, permitindo, assim, o reúso do bloco de código da função em questão.

[![](https://ampli-images.s3.amazonaws.com/production/5529ad46-5546-4f79-a4c3-0e7ece1582c9/original)](https://ampli-images.s3.amazonaws.com/production/5529ad46-5546-4f79-a4c3-0e7ece1582c9/original)

Funções em PHP. Fonte: elaborado pelo autor.

**Execute esse código no Paiza.io e veja o resultado.**

Copie o código acima e cole na ferramenta [Paiza.io](https://paiza.io/en/projects/new?language=php), inclua a visualização HTML e observe a saída.

As funções ainda podem apresentar um valor de retorno, o qual poderá ser utilizado no código principal do seu sistema. O retorno de uma função é definido pela palavra reservada return, que ao ser executada encerra o bloco de código da função e leva o resultado de retorno para o fluxo principal do seu código.

Na figura abaixo, observe que a função calcular__media_ tem como retorno o resultado do cálculo da média entre dois números e que logo em seguida esse resultado é passada para a função mostrar_resultado, a qual exibe o resultado, mas não apresenta retorno algum. Primeiramente observe o código que cria a função calcular__media_, a qual recebe os valores por parâmetro das variáveis _$num1_ e _$num2_:

[![](https://ampli-images.s3.amazonaws.com/production/c85339dd-41f0-45bf-8068-b1ae58fe6c24/original)](https://ampli-images.s3.amazonaws.com/production/c85339dd-41f0-45bf-8068-b1ae58fe6c24/original)

Função calcula média em PHP. Fonte: elaborado pelo autor.

Agora observe, na figura abaixo, a declaração da função mostrar_resultado, a qual recebe o valor da variável média por parâmetro e faz uma estrutura condicional para imprimir se o estudante está aprovado ou reprovado:

[![](https://ampli-images.s3.amazonaws.com/production/04eaf2c2-a167-48bd-b989-8b570ad762b8/original)](https://ampli-images.s3.amazonaws.com/production/04eaf2c2-a167-48bd-b989-8b570ad762b8/original)

Função calcula média em PHP. Fonte: elaborado pelo autor.

Por fim, no mesmo arquivo em que foram declaradas as funções é feita a execução delas. Veja que a variável $_media_ recebe o resultado da função **calcular_**_**media**_, e que essa função recebe os valores 7 e 10. Depois disso, é executada a função **mostrar_resultado**, passando essa média como parâmetro. Observe o exemplo na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/60cd3b2f-cf40-4d8c-ae0b-de9ab87cbdd4/original)](https://ampli-images.s3.amazonaws.com/production/60cd3b2f-cf40-4d8c-ae0b-de9ab87cbdd4/original)

Função mostrar resultado no cálculo da média em PHP. Fonte: elaborado pelo autor.

**Funções específicas**

Além das estruturas básicas que toda linguagem de programação apresenta, existem funções prontas e específicas que facilitam a vida dos desenvolvedores. Essas funções costumam prover um conjunto de recursos que até poderiam ser programados manualmente, mas que reduzem a quantidade de linhas de código porque já estão prontas para o uso.

Um exemplo de funções prontas são as relacionadas às validações para datas. Pense se você tivesse que fazer a validação de datas, com a preocupação de a data se referir a um ano bissexto; quantos dias tem aquele mês. Trabalhar com regras e cálculos envolvendo datas geralmente é algo que envolve um conjunto complexo de verificações. Portanto, a linguagem PHP oferece várias funções prontas que facilitam essas tarefas, como a função _**checkdate**_, capaz de validar se uma data é verdadeira ou não.

Toda função pode ter argumentos de parâmetros que são passados para a função dentro de parênteses logo após o seu nome e ela pode apresentar também um valor de retorno. No exemplo da função _**checkdate**_, ela tem três argumentos: mês, dia e ano, e retorna um valor booleano: verdadeiro, caso a data seja válida, ou falsa, caso seja uma data inválida. Dessa forma é possível, por exemplo, dizer ao usuário que a data 31/02/2020 é uma data inválida. A figura abaixo apresenta um exemplo de uso dessa função:

[![](https://ampli-images.s3.amazonaws.com/production/1b22e81a-4b4c-40fb-bcca-375e0a0afeb4/original)](https://ampli-images.s3.amazonaws.com/production/1b22e81a-4b4c-40fb-bcca-375e0a0afeb4/original)

Função predefinida checkdate. Fonte: elaborado pelo autor.

Além da função _checkdate_, existem funções que possibilitam efetuar cálculos e operações entre datas, de maneira que você pode identificar, por exemplo, há quantos dias um boleto está atrasado. Pode-se realizar essa operação com a função _**date_diff**_. Com ela pode-se efetuar o cálculo da diferença entre duas datas, passando por parâmetro duas datas que foram instanciadas pela função _**date_create**_.

O retorno da função _**date_diff**_ é um objeto do tipo _**DateInterval**_. Um objeto é uma espécie de variável que além de possuir um valor atribuído a ela, também apresenta funções que podem ser acessadas com o símbolo de seta (->). Para exibir o valor de diferença entre as datas é necessário utilizar a função _format_, pertencente ao objeto _DateInterval_. Observe a figura a seguir: no código são utilizadas todas essas funções com o objetivo de calcular a diferença entre duas datas.

[![](https://ampli-images.s3.amazonaws.com/production/aa602313-4f87-4eb3-a1b3-a87c6b9d910b/original)](https://ampli-images.s3.amazonaws.com/production/aa602313-4f87-4eb3-a1b3-a87c6b9d910b/original)

Exemplo de aplicação das funções date_create, date_diff e format. Fonte: elaborado pelo autor.

A linguagem PHP dispõe de muitas funções prontas e não é possível, neste momento, explorá-las todas. Mas vale a pena dar uma atenção para algumas funções relacionadas à formatação de números e tratamento de texto. A seguir, são descritas algumas funções com seus devidos parâmetros e valores de retorno:

- Formatar números passando por parâmetro o número que se deseja formatar, a quantidade de casas decimais, o caractere usado para separar as casas decimais e o caractere utilizado para separar os milhares:

[![](https://ampli-images.s3.amazonaws.com/production/50d6a4f8-7bc5-4d19-9a57-e38f1d8ad099/original)](https://ampli-images.s3.amazonaws.com/production/50d6a4f8-7bc5-4d19-9a57-e38f1d8ad099/original)

- Converter um texto para letras maiúsculas passando por parâmetro o texto que se deseja fazer a conversão:

[![](https://ampli-images.s3.amazonaws.com/production/9a278dc5-be70-4925-af3f-93ea25123adc/original)](https://ampli-images.s3.amazonaws.com/production/9a278dc5-be70-4925-af3f-93ea25123adc/original)

- Converter um texto para letras minúsculas passando por parâmetro o texto que se deseja fazer a conversão:

[![](https://ampli-images.s3.amazonaws.com/production/fc10aa66-f20c-4538-8c40-f23b630f6428/original)](https://ampli-images.s3.amazonaws.com/production/fc10aa66-f20c-4538-8c40-f23b630f6428/original)

- Retornar a quantidade de caracteres de um texto passando por parâmetro o texto que se deseja fazer a contagem:

[![](https://ampli-images.s3.amazonaws.com/production/fd2e6f93-4cd3-4ee9-861f-e44cac9590f2/original)](https://ampli-images.s3.amazonaws.com/production/fd2e6f93-4cd3-4ee9-861f-e44cac9590f2/original)

- Substituir parte de um texto por outro passando por parâmetro o texto que deseja ser pesquisado, o texto que deseja ser substituído e o texto que vai receber essa substituição. É possível, ainda, passar um parâmetro opcional informando a quantidade de substituições que se deseja fazer.

[![](https://ampli-images.s3.amazonaws.com/production/8086eabc-bfe0-4248-85d9-2720185a78ff/original)](https://ampli-images.s3.amazonaws.com/production/8086eabc-bfe0-4248-85d9-2720185a78ff/original)

A figura abaixo apresenta alguns exemplos de uso dessas funções:

[![](https://ampli-images.s3.amazonaws.com/production/31473dc5-b474-4a5e-980a-3c842a05ca40/original)](https://ampli-images.s3.amazonaws.com/production/31473dc5-b474-4a5e-980a-3c842a05ca40/original)

Exemplo de aplicação de algumas funções existentes. Fonte: elaborado pelo autor.

Um conjunto importante de funções que merece destaque são aquelas relacionadas ao tratamento de arquivos, pois a capacidade de armazenar e fazer leitura de arquivo torna sua aplicação muito poderosa. Essa função aceita dois argumentos: o nome do arquivo a ser aberto e o modo em que esse arquivo será aberto, aceitando os seguintes modos:

- **‘w’**: abre o arquivo somente para escrita e grava o conteúdo a partir do início do arquivo. Caso o arquivo não exista, ele é criado automaticamente. Caso ele já exista, todo seu conteúdo é perdido, e é substituído pelo novo conteúdo.
- ‘**w+**’: abre o arquivo para leitura e escrita seguindo os mesmo critérios do modo 'w'.
- ‘r’: abre o arquivo somente para leitura. Retorna um erro caso o arquivo não exista.
- **‘r+**’: abre para leitura e escrita; retorna um erro caso o arquivo não exista.
- **‘a**’: abre para somente para escrita somente; coloca o ponteiro do arquivo no final. Caso o arquivo não exista, ele é criado automaticamente. Caso ele já exista, ele adiciona o novo conteúdo ao conteúdo já existente.
- ‘**a+**’: abre o arquivo para leitura e escrita seguindo os mesmo critérios do modo 'a'.
- ‘**x**’: cria e abre o arquivo para escrita somente, porém ele retorna erro caso o arquivo já exista.
- ‘**x+**’: cria e abre um arquivo para escrita e leitura, porém ele retorna erro caso o arquivo já exista.

Outras funções são necessárias para manipular arquivos. A função _**fwrite**_ tem a funcionalidade de escrever em um arquivo que foi anteriormente aberto em algum dos modos de leitura. Ela tem como parâmetro a ponteiro do arquivo aberto, o texto que se deseja gravar e um parâmetro opcional para especificar o tamanho do conteúdo a ser gravado. Já a função _**fclose**_ é capaz de fechar um arquivo aberto, liberando o espaço que ele estava ocupando na memória. Na figura a seguir é apresentado um exemplo de abertura e escrita de conteúdo em um arquivo.

[![](https://ampli-images.s3.amazonaws.com/production/5946ecc9-3537-4bcc-9d99-a012a690406e/original)](https://ampli-images.s3.amazonaws.com/production/5946ecc9-3537-4bcc-9d99-a012a690406e/original)

Funções para escrita de arquivos em PHP. Fonte: elaborado pelo autor.

Estudante, agora que você já sabe gravar um arquivo, vai aprender como se realiza a leitura de um arquivo. A função _**fgets**_ é capaz de ler uma linha de um arquivo. Caso você queira ler o arquivo inteiro, terá que utilizar uma estrutura de repetição lendo linha a linha do arquivo até chegar ao seu fim. A função que verifica se chegou no fim do arquivo é a _**feof**_ e sua utilização pode ser visualizada no exemplo da figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/539697de-938d-456e-a433-0cb34a807a8f/original)](https://ampli-images.s3.amazonaws.com/production/539697de-938d-456e-a433-0cb34a807a8f/original)

Funções fgets, feof e fclose. Fonte: elaborado pelo autor.

Além de abrir arquivos para leitura e escrita, é possível manipular arquivos copiando, movendo ou excluindo-os. As principais funções para manipulação de arquivos são as seguintes:

- Função capaz de copiar um arquivo passando por parâmetro o caminho de origem e o caminho de destino: _copy ( string $source , string $dest) : bool_
- Função capaz de excluir um arquivo passando por parâmetro o nome do arquivo a ser excluído:_unlink ( string $filename) : bool_

Um recurso avançado quando está se trabalhando com arquivos é o bloqueio para múltiplos acessos e suas respectivas configurações de permissão. Para esse controle, pode ser utilizada a função _chmod_, a qual recebe por parâmetro o nome do arquivo seguido pelo número correspondente à permissão desejada. A figura abaixo apresenta um exemplo de código para controle de permissões de arquivos:

[![](https://ampli-images.s3.amazonaws.com/production/59ede984-752c-4340-a82a-7eeb3d973cfb/original)](https://ampli-images.s3.amazonaws.com/production/59ede984-752c-4340-a82a-7eeb3d973cfb/original)

Aplicação da função chmod para controle de permissões de arquivos. Fonte: elaborado pelo autor.

# **Upload de arquivos**

[![](https://ampli-images.s3.amazonaws.com/production/7885c9b1-56b3-47bc-a478-f4493e232c5c/original)](https://ampli-images.s3.amazonaws.com/production/7885c9b1-56b3-47bc-a478-f4493e232c5c/original)

De todas as funcionalidades disponíveis na linguagem PHP para se trabalhar com arquivos, uma das principais é o **upload de arquivos**, que permite que os usuários enviem arquivos para o servidor. Para isso, é necessário que se crie uma página HTML contendo um formulário com o seguinte atributo: _enctype="multipart/form-data_". Dentro desse formulário deve haver um elemento _input_ do tipo _file_. É necessário ainda definir no atributo action o nome do arquivo PHP que processará o upload, conforme mostrado na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/6f63bf2a-e655-4c00-b82f-c136d59b6818/original)](https://ampli-images.s3.amazonaws.com/production/6f63bf2a-e655-4c00-b82f-c136d59b6818/original)

Envio de arquivos para um servidor. Fonte: elaborado pelo autor.

**💭 Reflita**

Funções de armazenamento de arquivos são importantes quando desejamos deixar dados salvos para serem exibidos posteriormente no seu site. Reflita a respeito de como poderia ser desenvolvido um formulário HTML em que o usuário digite dados que, ao serem submetidos para o servidor, possam ser salvos em um arquivo. Depois disso, como fazer uma página capaz de ler e exibir os dados que foram salvos anteriormente?

______

Na página chamada “_upload_.php” são realizados o recebimento e processamento do arquivo enviado pelo usuário, e a variável global $__FILES_ contêm todas as informações desse arquivo. Tais informações podem ser lidas como um array com os seguintes atributos:

[![](https://ampli-images.s3.amazonaws.com/production/18d77b15-af64-4970-8b9c-4c9ccfd1ead0/original)](https://ampli-images.s3.amazonaws.com/production/18d77b15-af64-4970-8b9c-4c9ccfd1ead0/original)

Nesses exemplos deve-se notar que o nome ‘_userfile_’ se refere ao nome do elemento _input_ da página anterior. A figura abaixo apresenta um trecho de código que recebe e salva o arquivo enviado pelo usuário:

[![](https://ampli-images.s3.amazonaws.com/production/c3339a14-eb9b-4e2b-be83-b820db72efd7/original)](https://ampli-images.s3.amazonaws.com/production/c3339a14-eb9b-4e2b-be83-b820db72efd7/original)

Exemplo de código para receber e salvar um arquivo. Fonte: elaborado pelo autor.

🔁 **Assimile**

Uma função definida pelo desenvolvedor pode executar outra e, para isso, basta escrever o nome da função que se deseja executar seguido por parênteses contendo os seus argumentos. Mas o que acontece quando uma função executa a si própria? A esse caso chamamos **recursão**, o qual permite que uma função execute a si, gerando um laço de repetição que tende ao infinito. Para prevenir loops infinitos na utilização de recursão, é importante definir o ponto de parada.

Na figura a seguir é passado por parâmetro o número 24, que é dividido por 2 e executada a mesma função, passando por parâmetro o número 12; depois é executada novamente, passando por parâmetro o número 6. A mesma função vai sendo executada várias vezes até chegar ao ponto de parada, quando o número não é maior do que 2.

[![](https://ampli-images.s3.amazonaws.com/production/a4b8628e-8e72-48db-9e61-549d8d0a2d17/original)](https://ampli-images.s3.amazonaws.com/production/a4b8628e-8e72-48db-9e61-549d8d0a2d17/original)

Exemplo de recursão em PHP. Fonte: elaborado pelo autor.

Outra função importante no PHP é a _**Date**_**,** a qual recebe por parâmetro um formato que se deseja exibir a data atual. Esse formato pode ser expresso utilizando uma combinação de caracteres, destacando-se os seguintes:

**d** - Dia do mês: de 1 até 31.

**m** - mês: de 1 até 12.

**Y** - ano com 4 dígitos.

**y** - ano com 2 dígitos.

**w** - representação numérica do dia da semana: de 0 (domingo) até 6 (sábado).

**h** - hora no formato 12-horas: 01 até 12.

**H** - Hora no formato 24-horas: 00 até 23h

**i** - minutos: 00 até 59.

**s** - segundos: 00 até 59.

É possível, ainda, formatar uma data específica passando um segundo parâmetro referente a essa data, porém, a data tem que ter sido declarada utilizando a função _**strtotime**_, que permite ser enviada como parâmetro uma data no seguinte formato texto: _“__**ano-mês-dia hora:minuto:segundo**__”_. A figura abaixo apresenta alguns exemplos de uso dessas funções.

[![](https://ampli-images.s3.amazonaws.com/production/ae0c1350-cb89-40d1-9b96-536fb06ccbd6/original)](https://ampli-images.s3.amazonaws.com/production/ae0c1350-cb89-40d1-9b96-536fb06ccbd6/original)

Exemplo de uso da função strtotime. Fonte: elaborado pelo autor.

**📝 Exemplificando**

Cálculos envolvendo datas são sempre bastante complexos, pois envolvem muitas verificações. Considere, por exemplo, um caso em que se deseja verificar se um boleto está atrasado e, com base nessa informação, deve-se calcular o valor a ser pago, sabendo-se que são aplicados 2% de multa para boletos atrasados, além de 0,5% de juros por dia de atraso. Dessa maneira teremos que criar variáveis suficientes para a entrada de dados quando à data de vencimento e o valor do boleto. Como saída, o código deverá exibir informações acerca da quantidade de dias de atraso, o valor da multa, o valor de juros e o valor total a ser pago.

Considerando essas informações, uma solução para seria um algoritmo PHP conforme mostrado a seguir. Primeiramente deve-se declarar as variáveis contendo a data de vencimento e valor. Como faremos cálculo com data, a variável _$vencimento_ recebe um valor utilizando a função _**date_create**_. Essa função é capaz de declarar uma variável do tipo data, conforme a figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/74c27450-017b-451e-a976-35f627696dd0/original)](https://ampli-images.s3.amazonaws.com/production/74c27450-017b-451e-a976-35f627696dd0/original)

Função date_create. Fonte: elaborado pelo autor.

Depois deve-se criar uma variável contendo a data atual. Para isso, deve-se criar uma data com a função _**date_create**_ e, em seguida, a data atual com a função _**date(“Y-m-d”)**_. Depois é possível calcular a diferença de dias entre a data de vencimento e a data de hoje com a função _**date_diff**_. Essa função retorna um objeto com vários parâmetros, mas o que nos interessa é apenas a quantidade de dias; portanto, deve-se atribuir a uma variável o valor do atributo _days_, conforme mostrado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/edcf859f-9300-49a2-9be9-ff7d301929b2/original)](https://ampli-images.s3.amazonaws.com/production/edcf859f-9300-49a2-9be9-ff7d301929b2/original)

Exemplos de funções date_diff e date_create. Fonte: elaborado pelo autor.

Por fim, basta fazer uma estrutura de decisão em que, caso a quantidade de dias de atraso for maior que zero, deve-se calcular o valor da multa (2% do valor original), o valor de juros (0,5% por cada dia de atraso) e o valor a pagar, que é a soma do valor original com a multa e os juros. Se a quantidade de dias de atraso não for maior que zero, significa que o boleto não está atrasado, portanto, basta exibir o valor original do boleto, como mostra na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/47c5e8d1-1558-4076-ab68-e104d343b2ac/original)](https://ampli-images.s3.amazonaws.com/production/47c5e8d1-1558-4076-ab68-e104d343b2ac/original)

[![](https://ampli-images.s3.amazonaws.com/production/b3783642-9199-4cd9-b753-71545b076b55/original)](https://ampli-images.s3.amazonaws.com/production/b3783642-9199-4cd9-b753-71545b076b55/original)

**➕ Pesquise mais**

Armazenar dados em arquivos é uma prática muito útil quando queremos manter e recuperar informações na nossa aplicação web. Porém, muitas vezes os dados que desejamos armazenar são complexos e exigem um cuidado maior nas suas tratativas. Nesses casos recomenda-se utilizar um formato de dados que possa ser recuperado posteriormente. Um padrão muito utilizado é o JSON (_JavaScript Object Notation_ – Notação de Objetos _JavaScript_), um formato simples e leve de formatação de dados. Para se trabalhar com JSON, a linguagem PHP disponibiliza duas funções muito importantes:

- json__decode_($json): analise uma _string_ no formato JSON e converte para uma variável de objeto PHP.
- json__encode_($variavel): converte uma variável de objeto PHP para o formato JSON.

A seguir é apresentado um exemplo dessas duas funções, para transformar uma variável em JSON e logo depois salvar em um arquivo. Depois, no mesmo exemplo, é realizada a leitura do conteúdo do arquivo que acabou de ser gravado e feita a conversão de volta do formato JSON para variável do PHP:

[![](https://ampli-images.s3.amazonaws.com/production/4ff79d6f-dfe5-4c29-aa3f-0fa09ebb6ecb/original)](https://ampli-images.s3.amazonaws.com/production/4ff79d6f-dfe5-4c29-aa3f-0fa09ebb6ecb/original)

[![](https://ampli-images.s3.amazonaws.com/production/b0400967-d0e0-4e6f-bc6e-755403dd5ea9/original)](https://ampli-images.s3.amazonaws.com/production/b0400967-d0e0-4e6f-bc6e-755403dd5ea9/original)

[![](https://ampli-images.s3.amazonaws.com/production/26ba6ae3-5462-4eed-a80d-0ae74b715d86/original)](https://ampli-images.s3.amazonaws.com/production/26ba6ae3-5462-4eed-a80d-0ae74b715d86/original)

Armazenar em arquivo. Fonte: elaborado pelo autor.

Nesta aula apresentamos a importância das funções para deixar nosso código mais limpo e organizado. O uso das funções também é favorável para uma maior facilidade na manutenção futura do código. Outro aspecto que merece destaque é o uso das funções já existentes na ampla biblioteca de recursos de linguagem PHP. Na próxima aula, você vai estudar a utilização de banco de dados em página PHP.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

Para ampliar sua visão acerca das possibilidades de aplicação dos conhecimentos obtidos até o momento, vamos propor uma resolução para a situação-problema apresentada no início da aula. Deve-se continuar a aplicação web em que o usuário deverá digitar a distância a ser percorrida, o preço da gasolina e o preço do etanol. Logo depois deverá ser calculado e exibido o valor gasto com cada um dos combustíveis, considerando um consumo de 9 km/litro de etanol e 11 km/litro de gasolina, além de mostrar ao usuário qual o combustível fica mais barato.

Nesta aula foi solicitado que adicionássemos o requisito de armazenar os dados digitados pelo usuário em um arquivo, e depois que criássemos um relatório que exibisse esses dados. A parte de código em que o usuário fará a entrada de dados (_index.html_) não terá nenhuma alteração com a versão anterior, mantendo-se da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/72813635-ae4e-4b98-9d7c-03ac106c93d8/original)](https://ampli-images.s3.amazonaws.com/production/72813635-ae4e-4b98-9d7c-03ac106c93d8/original)

index.html. Fonte: elaborado pelo autor.

Já a página “respostas.php” terá alterações quando à formatação dos números, utilizando a função _number_format_, a captura da data atual com a função _date_ e ao armazenamento dos dados em um arquivo chamado “log.txt”. É adicionado, ainda, um _link_ para o usuário abrir a página chamada “relatório.php”. A seguir, é apresentado o código da página “resposta.php”, dando destaque em negrito para as partes que foram alteradas da figura anterior:

[![](https://ampli-images.s3.amazonaws.com/production/0c286b27-9f88-4a71-8f90-357c63a7047b/original)](https://ampli-images.s3.amazonaws.com/production/0c286b27-9f88-4a71-8f90-357c63a7047b/original)

[![](https://ampli-images.s3.amazonaws.com/production/afd0eb14-b9ef-49bb-8746-8a68a4bef92e/original)](https://ampli-images.s3.amazonaws.com/production/afd0eb14-b9ef-49bb-8746-8a68a4bef92e/original)

[![](https://ampli-images.s3.amazonaws.com/production/a3e762c1-83c2-4c29-8cd3-24e388e2d2d7/original)](https://ampli-images.s3.amazonaws.com/production/a3e762c1-83c2-4c29-8cd3-24e388e2d2d7/original)

Exibir relatório de preços de combustível. Fonte: elaborado pelo autor.

Por fim, deve-se criar uma página de relatório capaz de exibir os dados que foram armazenados no arquivo log.txt, conforme exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/1b1a2747-f20e-4ca0-b06d-a6e1781cff5f/original)](https://ampli-images.s3.amazonaws.com/production/1b1a2747-f20e-4ca0-b06d-a6e1781cff5f/original)

Relatório. Fonte: elaborado pelo autor.