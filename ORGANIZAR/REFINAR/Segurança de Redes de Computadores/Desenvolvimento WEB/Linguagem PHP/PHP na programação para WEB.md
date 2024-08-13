# **Introdução da Unidade**

[![](https://ampli-images.s3.amazonaws.com/production/0806bc9f-6b76-45bd-af9b-c9d53c1ecf80/original)](https://ampli-images.s3.amazonaws.com/production/0806bc9f-6b76-45bd-af9b-c9d53c1ecf80/original)

Estudante, você já observou como a maioria dos sites hoje em dia muda o seu conteúdo dinamicamente? A estrutura e _layout_ permanecem os mesmos, mas o conteúdo muda constantemente. Sites como o _Facebook_, por exemplo, atualizam o seu conteúdo quase que em tempo real. Plataformas de _e-commerce_ exibem produtos diferentes de acordo com o histórico de navegação e preferências do usuário. É como se houvesse páginas HTML sendo criadas o tempo todo, para que a cada acesso elas estivessem sempre atualizadas para o usuário visualizar novas informações.

Na verdade, a “magia” por trás dessas páginas que são atualizadas constantemente é uma linguagem de programação capaz de processar e criar páginas dinâmicas a cada acesso, as quais são processadas do lado do servidor. Dentre as linguagens de programação para esse fim, uma das mais utilizadas é o PHP, o qual se destaca pela sua facilidade de uso e uma ampla comunidade de desenvolvedores ativos. Estudante, nesta unidade você aprenderá como criar páginas dinâmicas utilizando a linguagem PHP.

Na aula 1 serão apresentados os fundamentos de PHP, incluindo os conceitos de variáveis, funções e estruturas da linguagem, além de apresentar a incorporação do código PHP aos arquivos HTML. Na aula 2 são apresentados conceitos mais aprofundados acerca da linguagem PHP, bem como a manipulação de arquivos, a qual permite o upload, a criação, cópia e leitura de arquivos no servidor. Por fim, a última aula é dedicada a uma utilização de banco de dados dentro de aplicações web com PHP, além da utilização de sessões e _cookies_ para autenticação de usuários.

# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/9ac8f85e-3c69-44c7-b4dd-363a50fb0559/original)](https://ampli-images.s3.amazonaws.com/production/9ac8f85e-3c69-44c7-b4dd-363a50fb0559/original)

### **Qual é o foco da aula?**

Nesta aula, você irá conhecer os conceitos da linguagem PHP.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- empregar a utilização de variáveis do PHP;
- traçar o desenvolvimento de site dinâmico;
- analisar interações em páginas e formulários.

**Situação-problema**

Páginas dinâmicas para internet são muito mais comuns do que você imagina. O fato de ser dinâmica significa que o seu conteúdo é alterado e gerado dinamicamente de acordo com os critérios definidos pelo programador. É assim que sites de _e-commerce_ conseguem apresentar produtos diferentes a cada acesso, também é assim que sites de notícias mantêm seu conteúdo sempre atualizado e redes sociais oferecem ao usuário texto e imagens direcionadas a ele. Para isso, é necessário utilizar uma linguagem de servidor, como o PHP.

Nesta aula será apresentada a linguagem de programação PHP, desde seus conceitos fundamentais até a sua interação com as páginas web e formulários. Será abordada a utilização de variáveis, operadores, constantes e funções, além das expressões e fluxos de controle do PHP. Esses conhecimentos são de suma importância para desenvolvedores de aplicações web, visto que hoje em dia não há como pensar no desenvolvimento de um site sem que haja algum conteúdo dinâmico.

A linguagem PHP conta com muitos desenvolvedores no mundo todo, e diversas empresas estão à procura de profissionais capacitados nessa linguagem para manter e desenvolver desde pequenos sites até mesmo grandes plataformas para internet. Se há alguma dúvida quanto à capacidade e robustez da linguagem PHP, basta observar que a maior rede social do mundo, o _Facebook_, foi desenvolvida utilizando a linguagem PHP como sua base principal, sofrendo alterações na sua infraestrutura, porém mantendo sua relação direta com essa poderosa linguagem de programação.

Devido sua popularidade e facilidade de uso, o PHP se tornou a linguagem de programação com maior número de servidores de hospedagem ativos ao redor do mundo, e é muito fácil encontrar um servidor PHP gratuito para hospedar suas aplicações. Dessa forma, vamos aprender com exemplos práticos como programar páginas web dinâmicas utilizando PHP.

A fim de colocarmos em prática os conhecimentos a serem obtidos, vamos analisar a seguinte situação-problema: você foi contratado por um _startup_ e deseja desenvolver um website capaz de auxiliar as pessoas a decidirem qual é o combustível mais econômico para abastecer um carro _flex_, que aceita tanto etanol quanto gasolina. Assim, você deverá desenvolver uma aplicação PHP no site em que o usuário em questão deverá ser capaz de inserir as informações a respeito da distância que deseja percorrer, o preço do litro de etanol e o preço do litro de gasolina.

O site deverá conter uma aplicação PHP que calcula e exibe qual é o valor gasto na viagem caso abasteça com etanol e o valor gasto caso abasteça com gasolina.

Considerando que o etanol é um combustível que é consumido mais rápido, mas que normalmente costuma ser mais barato. Considere que o veículo em questão faz 9 km com 1 litro de etanol e 11 km com 1 litro de gasolina. Portanto para, por exemplo, saber a quantidade de etanol gasto em uma viagem de 20 km, deve-se efetuar o seguinte cálculo: etanol = 20/11. E para saber a quantidade de gasolina gasta em uma viagem de mesma distância deve-se efetuar o seguinte cálculo: 20/9. Após calcular a quantidade gasta de cada combustível, multiplique essa quantidade pelo preço do litro do combustível digitado pelo usuário no formulário. Com isso, mostre ao usuário qual dos tipos de combustível tem melhor custo-benefício.

Une o que há de melhor no _design_ de páginas web com a programação de conteúdos dinâmicos utilizando PHP. Bons estudos!

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/9d7ceb5b-d8bb-4091-a15a-3e1ad85cd8b3/original)](https://ampli-images.s3.amazonaws.com/production/9d7ceb5b-d8bb-4091-a15a-3e1ad85cd8b3/original)

Estudante, PHP (um acrônimo recursivo para PHP, _Hypertext Preprocessor_) é uma linguagem de script muito utilizada para o desenvolvimento web. Ela é uma linguagem _open source_, ou seja, de código aberto, a qual pode ser utilizada de maneira gratuita até mesmo para a criação de plataformas comerciais.

A primeira versão do PHP foi criada em 1994 por Rasmus Lerdof, o qual liberou o código fonte para o público em 1995 permitindo uma significativa adoção pela comunidade de desenvolvedores. Em 1996 foi lançada a versão 2.0 do PHP, incluindo suporte ao acesso à banco de dados. Em 1998, ainda nos primórdios da internet, já havia mais de 60 mil sites utilizando a linguagem PHP, e no final deste mesmo ano foi lançada a versão 3.0 da linguagem totalmente reescrita e aprimorada. No ano de 2000 foi lançada a versão 4.0 do PHP, ganhando ainda mais apoio da comunidade e aumentando o número de servidores espalhados pelo mundo.

A versão 5.0 foi disponibilizada no ano de 2004, alcançando a marca de centenas de milhões de servidores hospedando páginas PHP. A versão 5.x do PHP foi tão popular que se manteve ativa até o ano de 2019, recebendo diversas atualizações. Sua principal novidade foi ao suporte aprimorado ao paradigma de Programação Orientada a Objetos.

Por se tratar de um software de código aberto, a comunidade de desenvolvedores foi incrementando a linguagem ao longo do tempo, e todas as _features_ (recursos) planejados para o PHP 6.0 acabaram sendo implementados nas ramificações da versão 5.x, chegando ao ponto que não faria mais sentido lançar uma versão 6.0. Portanto, em 2015, a linguagem PHP teve um salto, passando para a versão 7.0 que é mantida até os dias atuais com suas ramificações 7.x.

> O que chama a atenção no PHP é o fato de ser processado do lado do servidor, ou seja, o cliente (usuário final que deve acessar a página utilizando o navegador) não consegue enxergar o código PHP, pois este já foi processado no servidor de hospedagem, diferentemente da linguagem JavaScript, que é interpretada no navegador o usuário.

Na figura a seguir podemos visualizar o funcionamento da Linguagem PHP:

[![](https://ampli-images.s3.amazonaws.com/production/8b0ae64c-6dd6-4869-a6c5-f0750c416edd/original)](https://ampli-images.s3.amazonaws.com/production/8b0ae64c-6dd6-4869-a6c5-f0750c416edd/original)

Processo da Linguagem PHP. Fonte: elaborada pelo autor.

# **Como incorporar um PHP em uma página HTML**

[![](https://ampli-images.s3.amazonaws.com/production/363cbe17-182f-4505-9e4b-055bc89372fa/original)](https://ampli-images.s3.amazonaws.com/production/363cbe17-182f-4505-9e4b-055bc89372fa/original)

O código PHP fica dentro da página HTML, podendo em um mesmo arquivo intercalar entre os código HTML, CSS e _JavaScript_ e o código PHP. Para que isso ocorra é importante demarcar quando o código PHP inicia e quando ele finaliza. Essa marcação é dada por meio das _TAGs_ “<php" para abertura do código php e "?>" para fechamento, conforme este exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/c72fadda-d2d3-44b0-8298-1b85cb6bfaab/original)](https://ampli-images.s3.amazonaws.com/production/c72fadda-d2d3-44b0-8298-1b85cb6bfaab/original)

Neste caso foi utilizado o comando “_echo_”, que é responsável por imprimir um texto diretamente na página html. A forma apresentada é a padrão e mais utilizada de se incorporar código PHP dentro do HTML, porém existem outras formas, sendo que algumas delas dependem da sua configuração e ativação no servidor para que funcionem. As outras formas de se incorporar código PHP ao HTML são as seguintes:

- <? _echo_ “Olá mundo”; ?>
- <_script language_="php"> echo “Olá mundo”; </_script_>
- <% echo “Olá mundo”; %>

Na figura a seguir “Exemplo de código PHP” é apresentado um exemplo de código PHP. Observe o código PHP nas linhas 10 a 16 e o código HTML, que chamamos de conteúdo estático. Neste exemplo o usuário que acessar a página receberá como resultado apenas o código HTML, conforme mostrado na figura “Resultado do código HTML” a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/7eef0aeb-98cf-4bb8-ba6e-06816cecf057/original)](https://ampli-images.s3.amazonaws.com/production/7eef0aeb-98cf-4bb8-ba6e-06816cecf057/original)

Exemplo de código PHP. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/d0780088-e927-400a-8372-43563b3f1ecf/original)](https://ampli-images.s3.amazonaws.com/production/d0780088-e927-400a-8372-43563b3f1ecf/original)

Resultado do código HTML. Fonte: elaborada pelo autor.

**📝 Exemplificando**

Agora, você pode testar o código na ferramenta _on-line_ Paiza.io.

Paiza.io é uma IDE (Ambiente de Desenvolvimento Integrado) _on-line_; logo, não há necessidade de instalar nada no computador. Essa plataforma oferece suporte para mais de 20 linguagens de programação, incluindo o PHP. A interface do Paiza.io é apresentada na figura a seguir. Observe que o ambiente de desenvolvimento Paiza.io permite exibir o resultado em modo Texto, em HTML ou JSON. Observe o exemplo da figura “ Exemplo de código PHP”, configurado para a visualização em html.

[![](https://ampli-images.s3.amazonaws.com/production/72d4aca4-b50d-409f-a769-1d70580bed8c/original)](https://ampli-images.s3.amazonaws.com/production/72d4aca4-b50d-409f-a769-1d70580bed8c/original)

IDE on-line Paiza.io. Fonte: elaborada pelo autor.

Observe o código .php dentro do arquivo .html.

Copie o código da figura “Exemplo de código PHP” e cole na ferramenta [Paiza.io](https://paiza.io/en/projects/new?language=php), inclua a visualização HTML e observe a saída.

______

Assim, podemos observar que o código PHP foi processado do lado do servidor, transferindo para o cliente apenas o resultado desse processamento. Para executar páginas PHP você precisa de um servidor. Existem milhares de servidores na internet compatíveis com PHP, alguns deles são 000_webhost_ (2021) e _Hostinger_ (2021), entre outros. Também existem plataformas em nuvem que oferecem serviço de hospedagem de aplicações PHP, como _Amazon_ (2021), Google _Cloud_ (2021) e Microsoft _Azure_ (2021). Existe ainda a possibilidade de instalar um servidor PHP no seu próprio computador e ter a facilidade de testar suas páginas sem precisar de internet.

Se você utiliza Windows pode instalar o _WampServer_ ([s. d.]), um pacote que inclui o Apache, MariaDB e PHP para Windows. Outra opção de pacote de instalação gratuita e facilitada de servidor local PHP é o BitNami WAMPStack (2021). São tantas opções que é natural, no início, haver dúvidas a respeito de qual servidor usar.

Para aprender uma linguagem de programação é importante que você entenda sua sintaxe. É importante também adicionar comentários nos seus códigos para facilitar a compreensão futura. Para adicionar comentário de uma linha com PHP você pode utilizar os símbolos // ou # no início da linha, ou pode fazer comentários em bloco adicionando o símbolo /* para abrir o comentário e */ para finalizar o comentário.

# **Sintaxe e variáveis em PHP**

[![](https://ampli-images.s3.amazonaws.com/production/b10c44dd-88cb-498a-845a-41cb2cf15d36/original)](https://ampli-images.s3.amazonaws.com/production/b10c44dd-88cb-498a-845a-41cb2cf15d36/original)

A utilização de variáveis é algo fundamental em toda linguagem de programação. PHP é uma linguagem que não define tipos para suas variáveis, bastando colocar o sinal de cifrão **($)** antes do nome da variável. Observe que no código apresentado na figura a seguir são utilizadas duas variáveis, uma capaz de armazenar texto e outra capaz de armazenar número. O texto deve ser envolto em aspas.

[![](https://ampli-images.s3.amazonaws.com/production/a47bc224-d9d7-498c-b510-07865e10c7cf/original)](https://ampli-images.s3.amazonaws.com/production/a47bc224-d9d7-498c-b510-07865e10c7cf/original)

Declaração da sintaxe e variável em PHP. Fonte: elaborada pelo autor.

Execute esse código no Paiza.io e veja o resultado.

Copie o código da figura acima e cole na ferramenta [Paiza.io](https://paiza.io/en/projects/new?language=php), inclua a visualização HTML e observe a saída.

PHP é uma linguagem _case sensitive_, ou seja, faz diferenciação entre letras maiúsculas e minúsculas. Portanto, uma variável com o nome $telefone é diferente da variável $Telefone. Para trabalhar com os nomes de variáveis, você precisa ainda respeitar as seguintes regras:

- Nunca inicie por um número.
- Não utilize caracteres especiais (apenas letras não acentuadas, números e _underscore_ _).
- Não utilize espaços em branco. Se precisar colocar duas ou mais palavras, separe-as com letras maiúsculas ($valorProduto, $telefoneContato) ou com _underscore_ ($valor_produto, $telefone_contato).
- Crie nomes de variáveis significativas, que indiquem o conteúdo armazenado.

Uma característica interessante do PHP é o fato de que se pode utilizar tanto aspas simples como aspas duplas para demarcar textos. Porém, quando se usa aspas duplas, caso exista alguma variável dentro do texto, é impresso o valor desta variável. Já quando se usa aspas simples, é impresso exatamente o valor literal dentro das aspas, incluindo o nome da variável. É possível ainda concatenar um texto, imprimindo uma sequência de caracteres concatenada a uma variável por meio do símbolo de ponto final.

Ao contrário de variáveis, que podem variar o seu valor, existem as constantes, que não podem ter seu valor alterado. As constantes são declaradas pelo comando define, úteis para guardar valores fixos, com o valor de PI. Na figura a seguir é apresentado um exemplo de utilização de variáveis e constantes:

[![](https://ampli-images.s3.amazonaws.com/production/9e9ab1bc-72d3-4574-b143-982358bf1ecc/original)](https://ampli-images.s3.amazonaws.com/production/9e9ab1bc-72d3-4574-b143-982358bf1ecc/original)

Declaração da sintaxe e variável em PHP. Fonte: elaborada pelo autor.

Um tipo de recurso importante em uma linguagem de programação são as variáveis compostas, ou _arrays_. Nesse tipo de variável é possível armazenar um conjunto de valores, os quais são identificados por um índice. Na maioria das linguagens de programação o índice de um _array_ é definido por um número inteiro, porém no PHP pode-se utilizar números ou caracteres para identificar um elemento de um vetor, conforme o exemplo mostrado na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/46d39d68-7e76-42e8-9cdf-474dee7b39c5/original)](https://ampli-images.s3.amazonaws.com/production/46d39d68-7e76-42e8-9cdf-474dee7b39c5/original)

Declaração de um array. Fonte: elaborada pelo autor.

Muitos dos problemas solucionados pela programação envolvem cálculos matemáticos. Em PHP é possível realizar cálculos utilizando os seguintes operadores:

- Adição: +
- Subtração: -
- Multiplicação: *
- Divisão: /
- Módulo (resto da divisão): %

Como exemplo, considere que uma loja dá 10% de desconto para vendas à vista, e que se deseja calcular o valor total de uma compra, o valor de desconto e o valor de troco. No código PHP apresentado na figura a seguir, esse cálculo é realizado com base nos dados do valor unitário, a quantidade e o valor pago por um produto qualquer.

[![](https://ampli-images.s3.amazonaws.com/production/383ba378-37a8-498e-aaa8-9c883a572137/original)](https://ampli-images.s3.amazonaws.com/production/383ba378-37a8-498e-aaa8-9c883a572137/original)

Declaração de variáveis e cálculos. Fonte: elaborada pelo autor.

🔁 **Assimile**

Trabalhar com linguagens de programação para internet não é algo tão simples quando se trata de operações mais complexas. Nós exemplificamos uma situação em que o usuário deseja saber o preço final do produto, valor do desconto e valor do troco. Porém, no exemplo que foi dado, nós colocamos os valores fixos nas variáveis.

Para permitir que o usuário digite os dados de entrada é necessário que você crie duas páginas, uma para o formulário e outra para resposta. O formulário é a principal forma para permitir a entrada de dados pelo usuário, e é formada pela _TAG_ HTML “<_form_>” seguido por dois atributos:

- _action_: determina o nome do arquivo php que receberá os dados digitados pelo usuário.
- _method_: determina o método de envio e pode ser “_post_” ou _“get_”. O método ‘_get_’ expõe os dados digitados pelo usuário na barra de endereços do navegador. O método ‘_post_’, por sua vez, envia os dados no corpo da requisição HTTP, não exibindo os dados enviados na barra de endereços.

Para permitir que o usuário entre com dados é necessário criar dentro do formulário elementos do tipo “_input_”. Esses elementos apresentam o atributo “name”, que faz a identificação do campo para envio dos dados e o atributo “_type_”, que define o tipo de entrada, podendo ser do tipo “_text_” para entrada de texto, “_radio_” para escolha de um valor ou “_checkbox_“ para selecionar um valor, e “_submit_”, que faz um botão capaz de enviar os dados digitados para o servidor, redirecionando para página definida no elemento “_action_”.

Observe o código HTML apresentado na figura a seguir, que contém um formulário em que o usuário pode digitar o valor unitário de um produto, a quantidade e o valor pago:

[![](https://ampli-images.s3.amazonaws.com/production/ec195dff-1059-4a6c-ae3b-f36f99920976/original)](https://ampli-images.s3.amazonaws.com/production/ec195dff-1059-4a6c-ae3b-f36f99920976/original)

Declaração em formulários. Fonte: elaborada pelo autor.

Nesse formulário é importante observar que há um parâmetro _action_ para a página “resposta.php”, a qual enviará os dados via método “_post_” para que estes dados sejam tratados. Nesse tipo de envio de dados, os valores são enviados para o vetor $__POST_. Na figura a seguir apresenta o código da página “resposta.php”, a qual é capaz de calcular o valor total do produto multiplicando a quantidade pelo valor unitário digitado pelo usuário.

Após essa operação é realizado o cálculo de 10% referente ao valor de desconto. Por fim é calculado o valor de troco, subtraindo o valor pago (digitado pelo usuário) pelo valor total menos o valor de desconto.

[![](https://ampli-images.s3.amazonaws.com/production/d0f5c4ca-01fc-4b09-b768-99f0459b65a8/original)](https://ampli-images.s3.amazonaws.com/production/d0f5c4ca-01fc-4b09-b768-99f0459b65a8/original)

Arquivo resposta.php. Fonte: elaborada pelo autor.

Na figura abaixo podemos observar a execução do código apresentado na plataforma _PaizaCloud_ (c2014).

[![](https://ampli-images.s3.amazonaws.com/production/72e693b1-14fd-4c77-bb87-f8c1a5892cd7/original)](https://ampli-images.s3.amazonaws.com/production/72e693b1-14fd-4c77-bb87-f8c1a5892cd7/original)

Exemplo de Formulário. Fonte: elaborada pelo autor.

Note que o método do formulário é do tipo “_post_”. Este tipo de método encapsula os dados que são enviados para a outra página, não os mostrando no endereço da página de resposta, e os seus valores são enviados para o PHP por meio do _array_ $__POST_[“nome_do__input_”]. Dessa forma, o valor total é obtido pela multiplicação dos atributos $__POST_[“valorUnitario”] e $__POST_[“quantidade”].

# **Estruturas condicionais e seus operadores em PHP**

[![](https://ampli-images.s3.amazonaws.com/production/d0546207-8cb6-4f30-b8b4-95eabd439d0e/original)](https://ampli-images.s3.amazonaws.com/production/d0546207-8cb6-4f30-b8b4-95eabd439d0e/original)

Existem situações em que é necessário tomar decisões dentro do algoritmo, permitindo que ele execute um bloco de instruções caso atenda a uma determinada condição. Nesse caso utilizamos uma estrutura condicional, a qual pode ser definida na linguagem PHP com a instrução IF. É possível ainda executar um bloco de instruções caso a sentença seja falsa, adicionando esses comandos na cláusula _ELSE_. Para utilizar uma estrutura condicional é necessário conhecer os operadores relacionais. Em PHP podem ser utilizados os seguintes:

- Igual: ==
- Diferente: != ou <>
- Menor que: <
- Maior que: >
- Menor ou igual que: <=
- Maior ou igual que: >=

Pode-se ainda utilizar os operadores lógicos para combinar condições, como o operador E (**&&** ou _**and**_) que é verdadeira apenas se as duas condições forem verdadeiras, e o operador OU (|| ou _**or)**_, que retorna verdadeiro caso uma das condições forem verdadeiras. Na figura a seguir pode-se observar a utilização da estrutura condicional e seus operadores. No exemplo foram declaradas as variáveis nota = 7 e faltas =30.

[![](https://ampli-images.s3.amazonaws.com/production/2d86061b-d596-4cc7-a17b-f93475a4346c/original)](https://ampli-images.s3.amazonaws.com/production/2d86061b-d596-4cc7-a17b-f93475a4346c/original)

Estruturas condicionais e seus operadores em PHP. Fonte: elaborada pelo autor.

**Execute esse código no Paiza.io e veja o resultado.**

Copie o código da figura “Estruturas condicionais e seus operadores em PHP” e cole na ferramenta [Paiza.io](https://paiza.io/en/projects/new?language=php), inclua a visualização HTML e observe a saída.

Modifique os valores declarados para faltas = 20.

# **Estruturas de repetição em PHP**

[![](https://ampli-images.s3.amazonaws.com/production/a56319f5-71ab-4d95-aefe-ae4df58043b4/original)](https://ampli-images.s3.amazonaws.com/production/a56319f5-71ab-4d95-aefe-ae4df58043b4/original)

Estruturas de repetição são muito úteis quando se deseja repetir um bloco de instruções. Basicamente, esse tipo de estrutura pode ser de dois tipos:

- _While_: permite a repetição de uma instrução enquanto uma condição for verdadeira
- _For_: executa um número predeterminado de repetições, utilizando um índice para contar os loops. Nessa estrutura são passadas três operações separadas por ponto e vírgula: início, condição de término e critério de incremento. Observe o exemplo apresentado na figura a seguir, onde é realizada uma estrutura de repetição em que é impressa a tabuada do número 7, mostrando o resultado da multiplicação de 7 pelos números de 1 a 10. Já na figura abaixo “Estruturas de repetição em PHP” é demonstrada uma estrutura de repetição que mostra todos os números ímpares de 1 a 49.

[![](https://ampli-images.s3.amazonaws.com/production/c38d456a-0788-4a5f-8b9a-a94a85a3da6e/original)](https://ampli-images.s3.amazonaws.com/production/c38d456a-0788-4a5f-8b9a-a94a85a3da6e/original)

Estruturas de repetição em PHP. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/067395f5-0518-4075-9d91-7454c0ba3ca3/original)](https://ampli-images.s3.amazonaws.com/production/067395f5-0518-4075-9d91-7454c0ba3ca3/original)

Estruturas de repetição em PHP. Fonte: elaborada pelo autor.

**💭 Reflita**

PHP é uma linguagem que teve grande evolução ao longo dos anos, com a adição de várias funcionalidades e recursos. Neste material foram apresentadas as seguintes estruturas do código PHP: _if, while_ e for. Mas existem outras estruturas que podem ser utilizadas para determinar condições ou repetições?

______

**⚠️ Atenção**

Até o momento, todos os códigos foram executados em uma única página pela plataforma Paiza.io. Porém, há casos em que desejamos executar uma aplicação web mais complexa, formada por várias páginas. Para isso, pode-se utilizar a plataforma PaizaCloud (c2014), a qual fornece um ambiente mais completo e robusto. Conta com uma licença gratuita e o seu servidor pode ser utilizado por um tempo limitado a 4 horas.

# **Entrada de dados**

[![](https://ampli-images.s3.amazonaws.com/production/f352d19a-68a6-4853-86da-2c70d769709d/original)](https://ampli-images.s3.amazonaws.com/production/f352d19a-68a6-4853-86da-2c70d769709d/original)

**💭 Reflita**

A entrada de dados por parte do usuário se dá por elementos HTML do tipo INPUT. Utilizamos o tipo dos _inputs_ como TEXT. Será que existem outros tipos que _inputs_ que podem ser utilizados com html?

______

Observe na figura abaixo “Exemplo de Formulário no _PaizaCloud_” que foram criados dois arquivos, um para formulário e outro para o processamento e exibição dos dados.

Formulários que utilizam o método “_get_” enviam seus dados para o _array_ do PHP $__GET_[“nome_do__input_”], enquanto formulários que utilizam o método “_post_” enviam seus dados para o array Text$__POST_[“nome_do__input”_]. Nesse exemplo é importante relembrar que o formulário html é composto pela _TAG_ , <form _action_=”segunda.php” _method=”get_"> em que o parâmetro “_action_” determina a página que deverá receber e processar os dados digitados pelo usuário, enquanto o parâmetro “_method_” determina a forma como esses dados serão enviados, podendo ser “_get_” ou “_post_”.

Na figura “Arquivo resposta.php” é mostrado um exemplo utilizando a _tag <input_>, , ao inserir os parâmetros _type=”text_”, indica que será adicionado um elemento de caixa de texto para entrada de dados, e o parâmetro _type=”submit_” indica que será adicionado um botão capaz de executar a ação do formulário, submetendo os dados digitados pelo usuário para a página indicada no parâmetro “_action_” do formulário, conforme pode ser observado na figura “Formulários em HTML” a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/ba02caa6-adfd-47d6-9565-de37b7d5b10d/original)](https://ampli-images.s3.amazonaws.com/production/ba02caa6-adfd-47d6-9565-de37b7d5b10d/original)

Formulários em HTML. Fonte: elaborada pelo autor.

Após o usuário submeter os dados, a página chamada “segunda.php” receberá os dados por meio de um vetor $__GET_, o qual deve-se colocar entre colchetes o nome do elemento _input_ desejado, conforme pode ser observado no código apresentado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/9800ac83-d762-4d84-afe4-18c12bba33a2/original)](https://ampli-images.s3.amazonaws.com/production/9800ac83-d762-4d84-afe4-18c12bba33a2/original)

Submissão de dados em PHP. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/8cf3a94f-8836-499b-bec7-cc4d840bcb40/original)](https://ampli-images.s3.amazonaws.com/production/8cf3a94f-8836-499b-bec7-cc4d840bcb40/original)

Exemplo de Formulário no PaizaCloud. Fonte: elaborada pelo autor.

**📝 Exemplificando**

Linguagens de programação têm a capacidade de automatizar tarefas e cálculos que seriam dispendiosos se realizados manualmente. Considere o seguinte problema: uma nutricionista deseja criar um site em que seus pacientes possam inserir os dados de altura e peso, e o sistema mostrará ao usuário se ele está abaixo do peso (IMC<18,5), com peso normal (IMC entre 18,5 e 24,9) ou com sobrepeso (IMC maior ou igual a 25). O IMC é calculado com a seguinte equação: IMC = peso / (altura * altura).

Nesse caso, teríamos que construir duas páginas no ambiente _paiza.cloud_, uma para o formulário de entrada de dados e outra para calcular e exibir o resultado. A figura abaixo mostra o código para solucionar esse problema. Primeiramente segue o código HTML capaz de permitir o usuário digitar em um formulário a sua altura e o peso. Observe que o método de envio é do tipo “_post_”, de forma que os dados não serão exibidos explicitamente na barra de endereços do navegador; mas poderia ser utilizado o método “_get_” sem nenhum problema:

[![](https://ampli-images.s3.amazonaws.com/production/abf60a53-18f8-4f8b-ab92-3b4b0dbfb28f/original)](https://ampli-images.s3.amazonaws.com/production/abf60a53-18f8-4f8b-ab92-3b4b0dbfb28f/original)

Código .html - Nutricionista on-line. Fonte: elaborada pelo autor.

A página de resposta é capaz de processar os dados enviados pelo usuário. Observe o código e seus devidos comentários:

[![](https://ampli-images.s3.amazonaws.com/production/3781557a-5c09-4182-844c-acc9dbd3fbea/original)](https://ampli-images.s3.amazonaws.com/production/3781557a-5c09-4182-844c-acc9dbd3fbea/original)

Código .php - Nutricionista on-line. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/9fecfcbd-8b7f-42f7-9107-f052eea66b7c/original)](https://ampli-images.s3.amazonaws.com/production/9fecfcbd-8b7f-42f7-9107-f052eea66b7c/original)

Exemplo de calculadora de IMC. Fonte: elaborada pelo autor.

**➕ Pesquise mais**

As instruções de programação PHP são inseridas dentro dos arquivos HTML, podendo conter, além de código HTML puro e simples, um conjunto de instruções CSS e de _JavaScript_. Essa mistura de linguagens pode parecer confusa para quem não está ambientado, portanto justifica-se treinar um pouco essa mescla de tecnologias e deixar bem claro o que cada uma faz. No exemplo a seguir, em um mesmo arquivo são utilizados trechos de código HTML, CSS, _JavaScript_ e PHP:

[![](https://ampli-images.s3.amazonaws.com/production/4a6a6a25-d19a-4242-9cf6-20c918b5957d/original)](https://ampli-images.s3.amazonaws.com/production/4a6a6a25-d19a-4242-9cf6-20c918b5957d/original)

[![](https://ampli-images.s3.amazonaws.com/production/dbdb3d36-744e-4a60-9f8b-b867278ff422/original)](https://ampli-images.s3.amazonaws.com/production/dbdb3d36-744e-4a60-9f8b-b867278ff422/original)

Código PHP dentro do HTML. Fonte: elaborada pelo autor.

Nesta aula, foram apresentados os conceitos fundamentais da linguagem PHP, a utilização de variáveis, operadores aritméticos, estruturas condicionais e de repetição. Também vimos como o PHP se incorpora dentro de páginas HTML, gerando conteúdo dinamicamente. Dessa forma será exibido ao usuário um conteúdo personalizado de acordo com as entradas que ele mesmo fizer utilizando formulários. Nas próximas aulas, serão explorados esses e outros recursos do PHP, essa incrível linguagem de programação!

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Para ampliar sua visão acerca das possibilidades de aplicação dos conhecimentos obtidos até este momento, vamos retomar a situação-problema apresentada no início desta aula. Uma empresa deseja desenvolver um sistema web para facilitar a decisão em relação ao tipo de combustível cujo uso é mais compensatório: etanol ou gasolina.

Sempre que forem apresentados problemas dessa natureza é importante identificar quais são as entradas (dados que o usuário deverá inserir), quais são as saídas (resultados esperados) e quais são os valores internos que serão utilizados para produzir as saídas com base nas entradas. Nesse caso podemos identificar os seguintes elementos:

**Entradas**: distância a ser percorrida, preço do etanol e preço da gasolina.

**Saídas**: valor gasto com etanol, valor gasto com gasolina e qual é o combustível que fica mais barato.

**Valores internos**: o veículo faz 9 km/litro de etanol e 11 km/litro de gasolina.

Depois de identificar esses elementos fica mais fácil codificar o seu site. Observe o código do formulário para entrada de dados:

[![](https://ampli-images.s3.amazonaws.com/production/f07a816c-5a5b-46d5-86b4-00b36b647c54/original)](https://ampli-images.s3.amazonaws.com/production/f07a816c-5a5b-46d5-86b4-00b36b647c54/original)

Código para entrada de dados. Fonte: elaborado pelo autor.

Para processar os dados deve-se primeiramente ler os dados enviados pelo formulário com o vetor $__POST_. Em seguida, deve-se efetuar os cálculos para saber a quantidade de combustível gasto e depois a multiplicação pelo valor de cada combustível, conforme mostrado a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/96c5e043-396a-4ee5-85b9-7c97a791d2ef/original)](https://ampli-images.s3.amazonaws.com/production/96c5e043-396a-4ee5-85b9-7c97a791d2ef/original)

Código para o processamento dos dados apresentados. Fonte: elaborado pelo autor.

Como esse exercício necessita de dois arquivos de código PHP trabalhando em conjunto (um para o formulário e outro para processar a resposta), deve-se executá-lo em um servidor configurado no computador ou, então, na plataforma _on-line PaizaCloud_ (c2014), conforme mostrado na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/ee47e83c-893f-4cc9-8253-292a3dffefec/original)](https://ampli-images.s3.amazonaws.com/production/ee47e83c-893f-4cc9-8253-292a3dffefec/original)

Calculadora de combustível. Fonte: elaborado pelo autor.