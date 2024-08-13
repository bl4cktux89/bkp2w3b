# **Introdução da Unidade**

[![](https://ampli-images.s3.amazonaws.com/production/91390bdd-d072-4702-a920-8f9f48974eb2/original)](https://ampli-images.s3.amazonaws.com/production/91390bdd-d072-4702-a920-8f9f48974eb2/original)

Prezado estudante, nesta unidade, “Desenvolvimento web com _JavaScrip_t”, você vai conhecer e compreender a linguagem de programação JavaScript usada em aplicações _client-side_, além de seus recursos para desenvolvimento web. Para construir boas aplicações web, não é necessário ter um conhecimento profundo em sintaxe e metodologias do _JavaScript_. Entretanto, conhecer os fundamentos básicos dessa linguagem é importante para que você esteja apto a compreender scripts desenvolvidos por outros usuários (como as bibliotecas) e adaptá-los para suas aplicações.

Na aula 1, “A linguagem JavaScript”, você vai conhecer os fundamentos da linguagem JavaScript, aprender a construir seus primeiros scripts, a criar variáveis e a executar funções, além de estruturas condicionais e de repetição.

Na aula 2, “Elementos de aplicações em _JavaScript_”, você vai conhecer o modelo de objetos de documento (DOM), aprender como manipular o estilo de formulários, ver uma introdução às tecnologias AJAX (_Asynchronous JavaScript And XML_) e JSON (_JavaScript Object Notation_) e aprender a utilizar as funcionalidades de geolocalização, além de controlar a execução de vídeos usando HTML5 e JavaScript.

Na aula 3, “Bibliotecas e _frameworks JavaScript_”, você vai ver uma introdução a bibliotecas _JavaScript_, como _Node.js, Create.JS, jQuery, React, D3.js, Glimmer.js, Impact.js, Bootstrap_ e _AngularJS_, bem como entender a fundo como desenvolver códigos usando _jQuery_, além de alguns exemplos usando _Bootstrap JavaScript_.

Bons estudos!

# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/01106b0a-0d9a-4a47-a456-d3f820170779/original)](https://ampli-images.s3.amazonaws.com/production/01106b0a-0d9a-4a47-a456-d3f820170779/original)

### **Qual é o foco da aula?**

Nesta aula, irá aprender sobre códigos _JavaScript_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- aplicar fundamentos do _JavaScript_;
- relatar características do _JavaScript_;
- traçar os usos do _JavaScript_.

**Situação-problema**

Estudante, _JavaScript_ é uma das únicas linguagens de programação executadas em um navegador de internet. Entretanto, o _JavaScript_ também pode ser executado em outros ambientes, sendo possível usá-lo em ambiente de servidor (_Node.js_). Sem _JavaScript_, não seria possível criar páginas interativas, como jogos _online_, serviços de _e-mail_, geolocalização e carregamento de vídeos.

> A melhor forma de aprender a desenvolver códigos usando JavaScript é conhecer os fundamentos da linguagem de programação (que veremos nesta seção) e, a seguir, pesquisar bibliotecas JavaScript existentes e estudar códigos construídos por outros desenvolvedores.

_JavaScript_ possui uma imensa e ativa comunidade de desenvolvedores, por isso, espera-se achar uma grande quantidade de documentação na internet. A melhor maneira de aprender _JavaScript_ na prática é trabalhando com exemplos reais. _JavaScript_ tem se tornado cada vez mais popular, estando presente na grande maioria dos documentos web. Nesta aula, você aprenderá os fundamentos dessa linguagem, como características, sintaxe e possíveis usos.

Agora, para nos aproximarmos da prática, imagine que o setor de marketing e data _science_ da empresa de planos de internet em que você trabalha chegou à conclusão de que, às quartas-feiras, a taxa de vendas de planos tem uma queda significativa. Por isso, decidiram implementar uma promoção: assine na quarta-feira e receba 30 dias grátis.

Você deve, então, implementar uma função que exiba na seção de planos de internet a mensagem:

[![](https://ampli-images.s3.amazonaws.com/production/868e115f-d72e-4936-8719-00401f80e77b/original)](https://ampli-images.s3.amazonaws.com/production/868e115f-d72e-4936-8719-00401f80e77b/original)

Para isso, você deve:

1. Criar um _array_ para armazenar todos os dias da semana (domingo, segunda-feira, [...], sábado).
2. Utilizar JavaScript para detectar o dia da semana atual.
3. Usar um comando condicional para exibir um bloco de código apenas na quarta-feira.

**Dica 1**. Você pode usar o seguinte código para obter o dia atual:

[![](https://ampli-images.s3.amazonaws.com/production/275b1ea3-a939-48df-82f5-2931c975b482/original)](https://ampli-images.s3.amazonaws.com/production/275b1ea3-a939-48df-82f5-2931c975b482/original)

**Dica 2**. Você pode gravar textos na página usando a função:

[![](https://ampli-images.s3.amazonaws.com/production/9d8ec63f-a98a-427a-a61f-353d9f6541d2/original)](https://ampli-images.s3.amazonaws.com/production/9d8ec63f-a98a-427a-a61f-353d9f6541d2/original)

Para solucionar esse desafio, aproveite o conteúdo a seguir. Bons estudos!

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/f404b512-4670-44ee-a030-03081cd79592/original)](https://ampli-images.s3.amazonaws.com/production/f404b512-4670-44ee-a030-03081cd79592/original)

O HTML é uma linguagem estática, isto é, uma vez gerada a página, ela será exibida da forma como foi criada. Entretanto, a manutenção de sites estáticos é complexa: imagine um site de receitas culinárias em que um cozinheiro precisa construir uma página HTML para adicionar cada uma de suas receitas: é inviável! Por isso, tornou-se necessária a construção de páginas dinâmicas. Além disso, sites modernos requerem funcionalidades interativas, como um menu complementar, um botão que carrega uma janela extra ou um painel que troca uma imagem de tempos em tempos. Com CSS, vimos que podemos realizar algumas modificações envolvendo estilos, entretanto, podemos aplicar modificações avançadas usando linguagens de programação, que podem ser _back-end_ ou _front-end_; além disso, para entendermos a diferença entre eles, precisamos voltar ao conceito do paradigma cliente-servidor.

# **Paradigma cliente-servidor**

[![](https://ampli-images.s3.amazonaws.com/production/fa67a519-4e79-4834-81f3-c8a0afe13098/original)](https://ampli-images.s3.amazonaws.com/production/fa67a519-4e79-4834-81f3-c8a0afe13098/original)

As páginas de internet são compostas por documentos estruturados no formato HTML e estilizadas por meio de CSS. A internet é composta por uma série de computadores interligados de forma descentralizada por meio de redes de comunicação. Então, qual o papel do _JavaScript_ em um documento web?

Antes de visualizarmos isso, é necessário entender como funciona o paradigma cliente-servidor. Nesse paradigma, todo dispositivo usado para acessar a internet é denominado cliente (esse nome, muitas vezes, é utilizado para ser referir ao navegador ou ao próprio usuário: sim, você é o cliente). Para que um cliente possa acessar um site na internet, esse site deve estar disponível em um computador. Ao computador que fornece acesso ao site dá-se o nome de servidor. A figura abaixo ilustra o esquema do paradigma cliente-servidor.

[![](https://ampli-images.s3.amazonaws.com/production/e7105a10-247d-4f91-9df6-379157d55fea/original)](https://ampli-images.s3.amazonaws.com/production/e7105a10-247d-4f91-9df6-379157d55fea/original)

Paradigma cliente-servidor. Fonte: Mariano; de Melo-Minardi (2017, p. 29).

Assim, o paradigma cliente-servidor explica como uma página da internet pode ser visualizada:

- O cliente faz uma requisição à internet por meio de um navegador (no caso, fornece um endereço do site).
- Roteadores, servidores DNS e outros dispositivos e serviços indicam a localização do servidor que armazena o site requisitado.
- O servidor envia para o cliente os códigos necessários para renderização da página.

Assim, pode-se afirmar que as linguagens de programação podem ser aplicadas em dois pontos distintos: no cliente ou no servidor. Linguagens que executam no servidor são denominadas _server-side_, também conhecidas como linguagens _back-end_. Linguagens que executam no cliente são denominadas _client-side_, também conhecidas como _front-end_. Cada uma das linguagens executadas em cliente ou servidor tem seu propósito. Linguagens executadas no servidor têm uma maior segurança, uma vez que os códigos não ficarão visíveis para os usuários em geral, que receberão apenas os códigos HTML/CSS. Já as linguagens executadas no cliente utilizam recursos do próprio dispositivo do cliente, ou seja, não é necessário requisitar que o servidor processe mudanças no documento web (o que melhora a performance).

> JavaScript é a linguagem front-end usada para realizar alterações em páginas web; ela é executada diretamente no navegador, proporcionando mudanças interativas na página em tempo real. Essa linguagem é considerada a mais popular para o mercado de trabalho segundo uma pesquisa recente do site Stack Overflow (2019).

# **Fundamentos do Javascript**

[![](https://ampli-images.s3.amazonaws.com/production/bdc7a0f7-842c-47f4-9781-7a9bf62f0ba6/original)](https://ampli-images.s3.amazonaws.com/production/bdc7a0f7-842c-47f4-9781-7a9bf62f0ba6/original)

_JavaScript_ (JS) é uma linguagem de programação de script interpretada, dinâmica e executada em navegadores de internet (MDN WEB DOCS, 2020). Diferentemente do HTML e do CSS, linguagens de marcação e de estilos, respectivamente, o _JavaScript_ permite a entrada de dados, o processamento e o controle do fluxo dos dados diretamente no navegador, bem como o retorno de resultados computados. Tais características fazem do _JavaScript_ uma linguagem de programação _front-end_, isto é, uma linguagem executada no cliente. O _JavaScript_ trabalha em conjunto com HTML e CSS para tornar páginas de internet mais dinâmicas; além disso, ele tem sido usado, por exemplo, para a construção de jogos online, a visualização de dados interativa, a visualização de moléculas, a transmissão assíncrona de dados, entre outros.

______

**📝 Exemplificando**

**Um exemplo do poder da linguagem JavaScript**

Pode-se utilizar a linguagem **JavaScript** para uma grande variedade de funcionalidades que vão desde alterações simples no CSS até a construção de jogos executados diretamente de um navegador. Observe um exemplo de como a linguagem **JavaScript** pode ser usada. A figura abaixo ilustra um exemplo de buscador Google.

[![](https://ampli-images.s3.amazonaws.com/production/608e7200-2a98-4504-bc1d-8fd98a1c60a7/original)](https://ampli-images.s3.amazonaws.com/production/608e7200-2a98-4504-bc1d-8fd98a1c60a7/original)

Uma simples página de internet. Fonte: captura de tela do Google elaborada pelo autor.

A figura abaixo “Abrindo o console” mostra o acesso ao console dessa página, no qual foi digitado o comando:

document.body.style.backgroundColor = 'red';

[![](https://ampli-images.s3.amazonaws.com/production/8b05a757-8b61-440f-890c-e7bf671bbd94/original)](https://ampli-images.s3.amazonaws.com/production/8b05a757-8b61-440f-890c-e7bf671bbd94/original)

Abrindo o console. Fonte: captura de tela do Google adaptada pelo autor.

O resultado do comando é mostrado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/b7ea04df-a1a6-4cd1-9350-8322de9e1474/original)](https://ampli-images.s3.amazonaws.com/production/b7ea04df-a1a6-4cd1-9350-8322de9e1474/original)

Mudando a cor de fundo para vermelho.Fonte: captura de tela do Google adaptada pelo autor.

Nesse exemplo, foi utilizado um comando _JavaScript_ para alterar a cor de fundo. Vamos entender o código parte por parte:

[![](https://ampli-images.s3.amazonaws.com/production/135f0708-2ae0-42e3-94bd-042930da506d/original)](https://ampli-images.s3.amazonaws.com/production/135f0708-2ae0-42e3-94bd-042930da506d/original)

A seguir, será informada a propriedade _background-color_ (propriedade que altera a cor de fundo) a ser alterada. Perceba que _JavaScript_ não permite que se utilize hífen para separar palavras, assim, o hífen é removido e, em seu lugar, a primeira letra da próxima palavra é colocada em maiúsculo. Logo, _backgroundColor_ é equivalente a _background-color_.

document.body.style.backgroundColor = '**red**';

Por fim, foi indicado que essa propriedade deverá receber o valor _red_ (vermelho). O valor poderia tanto ser inserido entre aspas (“) quanto entre apóstrofos (‘), como nesse caso. Veja que a linha é encerrada com ponto e vírgula; isso não é obrigatório, mas sim uma boa prática do _JavaScript_.

Nesse exemplo, foi utilizado o console para fazer alterações no estilo com _JavaScript_. Entretanto, o console é apenas uma maneira interativa de desenvolvedores web analisarem e testarem seus códigos (no Brasil, chamamos isso de depurar o código ou, informalmente, de **debugar o código**), não sendo a forma de se utilizar códigos _JavaScript_ em um site. Para isso, é necessário incorporar o código diretamente no HTML.

# **Acessando o console em diferentes navegadores**

[![](https://ampli-images.s3.amazonaws.com/production/031a1b4d-9b21-460a-bfa5-94cee078a511/original)](https://ampli-images.s3.amazonaws.com/production/031a1b4d-9b21-460a-bfa5-94cee078a511/original)

Navegadores apresentam ferramentas para auxiliar no desenvolvimento web. Uma dessas ferramentas é o console da página (presente nas ferramentas de inspeção de código). A figura abaixo apresenta formas de acesso ao console em dois diferentes navegadores: Chrome e Firefox.

[![](https://ampli-images.s3.amazonaws.com/production/e1eceb36-d4e8-4545-8645-98a5bc50caf8/original)](https://ampli-images.s3.amazonaws.com/production/e1eceb36-d4e8-4545-8645-98a5bc50caf8/original)

[![](https://ampli-images.s3.amazonaws.com/production/375a2948-e64b-4adc-8529-4331cc5cae21/original)](https://ampli-images.s3.amazonaws.com/production/375a2948-e64b-4adc-8529-4331cc5cae21/original)

[![](https://ampli-images.s3.amazonaws.com/production/bc501ff6-3f0c-4e4e-8d1a-19899fcc204a/original)](https://ampli-images.s3.amazonaws.com/production/bc501ff6-3f0c-4e4e-8d1a-19899fcc204a/original)

Em HTML, comandos _JavaScript_ são declarados através da _tag <script_>:

[![](https://ampli-images.s3.amazonaws.com/production/23bab3ec-7a52-42a3-806d-688347e44935/original)](https://ampli-images.s3.amazonaws.com/production/23bab3ec-7a52-42a3-806d-688347e44935/original)

Os comandos em _JavaScript_ devem ser encerrados por ponto e vírgula (apesar de que o uso de ponto e vírgula no final de uma linha não é considerado obrigatório para que um script funcione). Além disso, assim como na linguagem CSS, comentários em _JavaScript_ também são inseridos entre os símbolos de /* e */. Todavia, _JavaScript_ também permite a inserção de comentários de linha única por meio dos símbolos // inseridos no início de uma linha. Observe o exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/05f2bc42-3437-4f7b-afff-09b5880c5650/original)](https://ampli-images.s3.amazonaws.com/production/05f2bc42-3437-4f7b-afff-09b5880c5650/original)

É importante destacar que essa prática de inserção de códigos _JavaScript_ diretamente no arquivo HTML não é uma boa prática. Assim como CSS, o ideal é criar um arquivo externo (de extensão .js) e embuti-lo no código HTML, conforme pode ser visto a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/5eb08f12-450b-46f3-b42b-116f46a726c5/original)](https://ampli-images.s3.amazonaws.com/production/5eb08f12-450b-46f3-b42b-116f46a726c5/original)

[![](https://ampli-images.s3.amazonaws.com/production/decb9927-473f-4e08-b349-5a9d4adedd88/original)](https://ampli-images.s3.amazonaws.com/production/decb9927-473f-4e08-b349-5a9d4adedd88/original)

Meu primeiro script em Javascript - index.html. Fonte: elaborado pelo autor.

Observe que no exemplo apresentado, dividimos a página web em três arquivos:

- _index_.html: arquivo principal que recebe a estrutura e o conteúdo da página.
- _script_.js: recebe os códigos JavaScript que serão executados em index.html.
- _estilo.css_: recebe os estilos que serão aplicados em index.html.

Veja a forma como os dois arquivos são declarados em _index_.html. Enquanto a folha de estilo é referenciada pela _tag_ simples  <_link_> e a propriedade rel, o arquivo fonte do _script_ é inserido com a _tag_ composta <s_cript_> e a propriedade src. Note que, no arquivo _script_.js, não é necessário declarar a _tag_ <s_cript_>.

# **Funções**

[![](https://ampli-images.s3.amazonaws.com/production/5256c1c5-b53b-4739-b0e3-c35c9116ddff/original)](https://ampli-images.s3.amazonaws.com/production/5256c1c5-b53b-4739-b0e3-c35c9116ddff/original)

_JavaScript_ possui recursos nativos (_built-in_), denominados funções. As funções têm o objetivo de receber informações passadas como parâmetros, realizar processamentos e retornar os dados processados por meio de alguma ação. Para chamar uma função, deve-se escrever o nome dessa função seguido de parênteses.

[![](https://ampli-images.s3.amazonaws.com/production/5b1ba9d6-6b1c-488c-84b9-18152355d6d6/original)](https://ampli-images.s3.amazonaws.com/production/5b1ba9d6-6b1c-488c-84b9-18152355d6d6/original)

As funções podem receber de 0 a n argumentos, a depender da função utilizada. Um exemplo simples é a função _alert_(), que exibe uma mensagem de alerta na caixa de diálogo. Adicione o seguinte código dentro do seu arquivo _script_.js:

[![](https://ampli-images.s3.amazonaws.com/production/995700fe-dae2-4f3e-8b63-69c60f1bb685/original)](https://ampli-images.s3.amazonaws.com/production/995700fe-dae2-4f3e-8b63-69c60f1bb685/original)

Agora, observe o resultado mostrado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/6ad9fa53-87be-4b0c-9f70-6fdef6fb4e4f/original)](https://ampli-images.s3.amazonaws.com/production/6ad9fa53-87be-4b0c-9f70-6fdef6fb4e4f/original)

“Olá mundo!” JavaScript. Fonte: captura de tela elaborada pelo autor.

Observe que, até o momento, você está apenas aprendendo a realizar as chamadas de funções; na sequência, você aprenderá a criar suas próprias funções.

# **Variáveis e tipos de dados**

[![](https://ampli-images.s3.amazonaws.com/production/6239aaf9-210f-40a5-9036-1d42764f9454/original)](https://ampli-images.s3.amazonaws.com/production/6239aaf9-210f-40a5-9036-1d42764f9454/original)

Estudante, você já aprendeu a utilizar a função _alert_() para exibir uma mensagem, agora, observe que _alert_ recebeu um conjunto de letras (ou caracteres) declaradas entre aspas. Assim como outras linguagens de programação, _JavaScript_ atribui tipos para os dados recebidos. Por exemplo: conjuntos de caracteres são dados do tipo _string_ e, em geral, são declarados entre “aspas” ou ‘apóstrofos’. Além disso, há diversos outros tipos de dados:

[![](https://ampli-images.s3.amazonaws.com/production/f1ea97d8-fdf2-4f1d-ade0-d67b77ae46fb/original)](https://ampli-images.s3.amazonaws.com/production/f1ea97d8-fdf2-4f1d-ade0-d67b77ae46fb/original)

Tipos de dados em JavaScript. Fonte: adaptado de Mariano; de Melo-Minardi (2017); MDN WEB DOCS (2020).

No exemplo apresentado, foi utilizada a função _alert(_) para imprimir uma _string_ na caixa de diálogo. Assim, sempre que for necessário exibir essa _string_ novamente na tela, esta deverá ser digitada novamente.

Linguagens de programação utilizam o conceito de variáveis para armazenamento de dados na memória e reutilização durante o código. Imagine uma variável como uma caixa na qual você armazena uma informação que poderá ser consultada a qualquer momento. A seguir, observe um exemplo de uma variável:

[![](https://ampli-images.s3.amazonaws.com/production/5cbd88e7-1934-41d5-8294-40592ab204a2/original)](https://ampli-images.s3.amazonaws.com/production/5cbd88e7-1934-41d5-8294-40592ab204a2/original)

No código apresentado a seguir, foi criada uma variável global denominada mensagem, que receberá, como valor, a _string_ Olá mundo. Veja, agora, a declaração de diversos tipos de variáveis:

[![](https://ampli-images.s3.amazonaws.com/production/79d11086-3fa6-4a82-bcb3-ede8f594ea1b/original)](https://ampli-images.s3.amazonaws.com/production/79d11086-3fa6-4a82-bcb3-ede8f594ea1b/original)

script.js – Declaração, exibição e atribuição de variáveis. Fonte: elaborado pelo autor.

Observe que foram evitados acentos em nomes de variáveis. Ainda que muitos navegadores já ofereçam suporte ao uso de acentos em nomes de variáveis, alguns desenvolvedores evitam utilizar os caracteres especiais para evitar possíveis falhas no código (veja que espaços em nomes de variáveis não são aceitáveis e, em geral, são substituídos pelo caractere “_”).

Observe, ainda, que é possível atribuir uma variável à outra. Na linha 15, foi atribuída a variável numero à variável mensagem, logo, mensagem passará a receber o valor de numero. Isso só foi possível porque foram utilizadas as variáveis globais. Além dessas, existem outras formas de se declarar variáveis.

______

🔁 **Assimile**

Variáveis são case sensitive, isto é, letras maiúsculas e minúsculas fazem a diferença no nome da variável. Por exemplo, uma variável chamada “mensagem” é diferente de uma variável chamada “Mensagem”.

______

Em _JavaScript_, variáveis podem, ainda, ser declaradas por meio das palavras reservadas var, const ou let (ou nada, como no exemplo anterior), seguido de um nome, o sinal de atribuição e um valor (opcionais), e encerrado por ponto e vírgula.

[![](https://ampli-images.s3.amazonaws.com/production/09ca4189-0f2a-41ca-afb7-5eaa9fd6b122/original)](https://ampli-images.s3.amazonaws.com/production/09ca4189-0f2a-41ca-afb7-5eaa9fd6b122/original)

Declarando variáveis em JavaScript. Fonte: elaborado pelo autor.

Observe que as quatro variáveis declaradas são do tipo _string_. Entretanto, a diferença entre elas dependerá do “escopo” adotado e das características desejadas. É importante não chamar uma variável antes de sua declaração. Caso isso ocorra, o código será imediatamente interrompido e um erro no console será exibido.

Entretanto, em _JavaScript_, há o conceito de _hoisting_: quando um _script_ é executado, todas as variáveis são elevadas (_hoisting_) ao topo do contexto de execução. Isso pode permitir, por exemplo, que você utilize uma variável antes da declaração.

[![](https://ampli-images.s3.amazonaws.com/production/92ca061b-7049-4b97-8769-b1c7f6e609f3/original)](https://ampli-images.s3.amazonaws.com/production/92ca061b-7049-4b97-8769-b1c7f6e609f3/original)

Ordem de declaração de variáveis para exibição de mensagens em JavaScript. Fonte: elaborado pelo autor.

Na execução desse código, nada foi exibido, uma vez que a mensagem exibida na linha 3 só foi declarada na linha 9, ou seja, ela ainda não existia no momento da chamada (a execução do código é linear). Ao verificar o console da propriedade “Inspecionar”, você verá o seguinte erro, conforme nos é mostrado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/f7989daf-3663-410c-98a5-8bb8803b6496/original)](https://ampli-images.s3.amazonaws.com/production/f7989daf-3663-410c-98a5-8bb8803b6496/original)

Verificando erros no console. Fonte: captura de tela elaborada pelo autor.

Isso indica que a variável mensagem_1 não foi definida antes da execução, logo, há um erro na linha 3 do arquivo **script.js** (vemos isso na figura em **script.js:3**).

Agora, vamos verificar o que acontece com os outros tipos de variáveis. Você pode comentar, separadamente, as linhas 3, 4 e 5 para verificar o que ocorre na execução da próxima linha. Veja que, agora, temos um erro diferente:

[![](https://ampli-images.s3.amazonaws.com/production/c78115a9-0aed-4a72-9c79-d0e2d21433bb/original)](https://ampli-images.s3.amazonaws.com/production/c78115a9-0aed-4a72-9c79-d0e2d21433bb/original)

[![](https://ampli-images.s3.amazonaws.com/production/9e0b71e5-b963-4550-bff4-7ed728463819/original)](https://ampli-images.s3.amazonaws.com/production/9e0b71e5-b963-4550-bff4-7ed728463819/original)

Comparando tipos de variáveis. Fonte: captura de tela elaborada pelo autor.

Pode-se observar que o console retorna um erro, indicando que não é possível acessar a variável antes de sua inicialização. Ao comentar separadamente, é possível verificar que a execução do código é interrompida a cada variável executada antes de sua declaração.

Entretanto, nenhum erro aparece se se realizar o mesmo teste para a variável mensagem_4:

[![](https://ampli-images.s3.amazonaws.com/production/f325cb50-d35b-46f5-a8da-45652c4c4ed0/original)](https://ampli-images.s3.amazonaws.com/production/f325cb50-d35b-46f5-a8da-45652c4c4ed0/original)

Variável indefinida.Fonte: captura de tela elaborada pelo autor.

O sistema apenas imprime a palavra _undefined_ (indefinido). Isso ocorre porque a palavra reservada var possui escopo global, ou seja, ela existirá em qualquer parte do código. Entretanto, o valor só será atribuído depois da declaração (por isso, é exibido que o valor da variável é indefinido).

[![](https://ampli-images.s3.amazonaws.com/production/45b1e25a-a442-4c93-a315-2bfa411fcde7/original)](https://ampli-images.s3.amazonaws.com/production/45b1e25a-a442-4c93-a315-2bfa411fcde7/original)

Declaração de variáveis antes e depois do alert. Fonte: elaborado pelo autor.

Veja o que ocorre ao imprimir essa variável em dois pontos distintos do código:

[![](https://ampli-images.s3.amazonaws.com/production/874b6d04-b488-4df0-a297-0fd5cdd42646/original)](https://ampli-images.s3.amazonaws.com/production/874b6d04-b488-4df0-a297-0fd5cdd42646/original)

[![](https://ampli-images.s3.amazonaws.com/production/ded46562-027a-4f5d-b3be-e689d53d306b/original)](https://ampli-images.s3.amazonaws.com/production/ded46562-027a-4f5d-b3be-e689d53d306b/original)

Imprimindo variáveis declaradas com var antes (A) e depois da declaração (B). Fonte: capturas de tela elaboradas pelo autor.

Essa é uma das principais diferenças entre var e let (recomenda-se criar variáveis usando let). Enquanto var permite que variáveis sejam usadas antes de sua declaração, let restringe a inicialização da variável antes de sua declaração. Variáveis let são restringidas ainda pelo escopo, que pode ser entendido como o contexto de execução, ou seja, uma parte do código. A palavra reservada const, por sua vez, cria variáveis “constantes”, ou seja, que não podem ser modificadas.

Observe as linhas 6 e 9 na imagem abaixo “Mudança de variáveis declaradas como alert (linhas 6 e linha 9)” e o resultado na figura “Constantes”. Pode-se verificar que, ao tentar mudar o valor de uma variável declarada como const, será exibido um erro.

[![](https://ampli-images.s3.amazonaws.com/production/2f617340-2f7f-4aac-8992-f07ca894c257/original)](https://ampli-images.s3.amazonaws.com/production/2f617340-2f7f-4aac-8992-f07ca894c257/original)

Mudança de variáveis declaradas como alert (linhas 6 e linha 9). Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/4ea63c2e-ea2d-4f52-8c89-35d63ee3fb80/original)](https://ampli-images.s3.amazonaws.com/production/4ea63c2e-ea2d-4f52-8c89-35d63ee3fb80/original)

Constantes. Fonte: captura de tela elaborada pelo autor.

Aqui, a variável mensagem_3, por ser do tipo const, não pode ser reatribuída a outro valor.

A figura abaixo apresenta as principais características de cada variável:

[![](https://ampli-images.s3.amazonaws.com/production/6a626f37-e635-4fa5-afce-6439f4066b6f/original)](https://ampli-images.s3.amazonaws.com/production/6a626f37-e635-4fa5-afce-6439f4066b6f/original)

Palavras-chave usadas na declaração de variáveis. Fonte: adaptado de Gordon ([s.d.]).

# **Estruturas de controle**

[![](https://ampli-images.s3.amazonaws.com/production/b7ab2068-beae-48cf-82e7-386d5c19ce39/original)](https://ampli-images.s3.amazonaws.com/production/b7ab2068-beae-48cf-82e7-386d5c19ce39/original)

As linguagens de programação devem restringir que blocos de códigos sejam executados apenas se determinada condição ou conjunto de condições forem alcançadas. Veja a anatomia de um bloco de código:

bloco(condição){

comandos;

}

Entretanto, antes de apresentarmos os dois tipos de estruturas de controle (condicionais e iterativas), é necessário que você conheça os operadores.

### **Operadores matemáticos**

Um exemplo simples de operadores são os denominados operadores matemáticos. Como o próprio nome diz, são os operadores usados para realização de operações matemáticas, como soma (+), divisão (/), multiplicação (*), subtração (-), módulo ou resto da divisão (%), exponenciação (**) e operador de atribuição (=).

Observe um exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/06986067-5d5b-47c6-a1b6-41a6b0d92e84/original)](https://ampli-images.s3.amazonaws.com/production/06986067-5d5b-47c6-a1b6-41a6b0d92e84/original)

Operadores matemáticos em JavaScript. Fonte: elaborado pelo autor.

Dos exemplos apresentados, destaca-se o operador módulo (%), que retorna o resto de uma divisão cujo resultado deve ser um número inteiro (no exemplo, 5 dividido por 2 é igual a 2 com resto 1, e o módulo corresponde ao resto dessa divisão).

Observe que foi destacado o operador “=”, mas ele não é considerado um operador matemático e sim um operador de atribuição. Veja na linha 15 um exemplo de uso do operador de atribuição (não dizemos que a variável soma é IGUAL às variáveis a + b e sim que soma RECEBE as variáveis a + b). Para avaliarmos uma igualdade, temos de utilizar os operadores relacionais.

______

**📝 Exemplificando**

_**Concatenando strings**_

É fácil compreender o que acontece somando-se duas variáveis numéricas, mas se no lugar de uma variável numérica tivesse uma _string_? Quando se utiliza o operador de soma para _strings_, tem-se uma operação de concatenação, _i.e._, junção entre duas palavras. Observe a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/8ce7a814-d7c0-47cd-b019-5aceed94994d/original)](https://ampli-images.s3.amazonaws.com/production/8ce7a814-d7c0-47cd-b019-5aceed94994d/original)

Concatenação de strings. Fonte: elaborado pelo autor.

Console:

script.js:5 Olá mundo!

______

### **Operadores relacionais**

Operadores relacionais permitem a comparação entre dois itens. Por exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/618b1d84-cbf4-48b9-b548-c3f5fa6dc8e9/original)](https://ampli-images.s3.amazonaws.com/production/618b1d84-cbf4-48b9-b548-c3f5fa6dc8e9/original)

Operadores relacionais em JavaScript. Fonte: elaborado pelo autor.

Nesse caso, a linha 4 está avaliando se o valor contido em a é maior do que o valor contido em b. Como a operação exibida no exemplo é verdadeira, a caixa de mensagem exibirá _true_.

Veja alguns outros exemplos de operadores relacionais:

[![](https://ampli-images.s3.amazonaws.com/production/12f9a5ae-a9f1-4615-99bc-67fcd516fdf8/original)](https://ampli-images.s3.amazonaws.com/production/12f9a5ae-a9f1-4615-99bc-67fcd516fdf8/original)

Operadores relacionais. Fonte: adaptado de Mariano; de Melo-Minardi (2017).

### **Operadores lógicos**

Por fim, você deve conhecer os operadores lógicos, que nos permitem avaliar múltiplas condições ou negações. Os operadores lógicos podem ser _and_ (e), _or_ (ou) ou _not_ (negação).

[![](https://ampli-images.s3.amazonaws.com/production/f4923852-5e73-4d95-8df2-112b3b511a0f/original)](https://ampli-images.s3.amazonaws.com/production/f4923852-5e73-4d95-8df2-112b3b511a0f/original)

Operadores lógicos. Fonte: adaptado de Mariano; de Melo-Minardi (2017).

Um exemplo é mostrado a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/0d2f5f0e-a844-4489-867c-fb7708c4aa7f/original)](https://ampli-images.s3.amazonaws.com/production/0d2f5f0e-a844-4489-867c-fb7708c4aa7f/original)

Operadores lógicos em JavaScript. Fonte: elaborado pelo autor.

Observe como os parênteses são utilizados para organizar as condições:

( ( condição 1) e ( condição 2 ) )

Pode-se, ainda, utilizar parênteses para criar condições avançadas:

( ( ( condição 1 ) e ( condição 2) ) ou ( condição 3 ) )

Nesse caso, a expressão será verdadeira se condição 1 e condição 2 forem verdadeiras ou se apenas a condição 3 for verdadeira. No exemplo anterior, colorimos os parênteses de acordo com seus pares. Veja que cada parêntese aberto deve ser fechado, caso contrário, o código apresentará um erro.

# **Console**

[![](https://ampli-images.s3.amazonaws.com/production/06bb8d9e-5546-482a-80ed-3a43b4b62884/original)](https://ampli-images.s3.amazonaws.com/production/06bb8d9e-5546-482a-80ed-3a43b4b62884/original)

Agora, vamos utilizar a função console.log(), que exibe o resultado no console da ferramenta inspecionar elemento. Veja como o código seria exibido:

[![](https://ampli-images.s3.amazonaws.com/production/a2649105-87c0-4cbf-9cb5-1229086d790a/original)](https://ampli-images.s3.amazonaws.com/production/a2649105-87c0-4cbf-9cb5-1229086d790a/original)

console.log() para exibição de resultados. Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/9ee405e4-f5c4-49ce-95dd-7eec0f6d83ea/original)](https://ampli-images.s3.amazonaws.com/production/9ee405e4-f5c4-49ce-95dd-7eec0f6d83ea/original)

Operações matemáticas. Fonte: captura de tela elaborada pelo autor.

Agora que você já conhece os operadores matemáticos, lógicos e relacionais, podemos, então, conhecer as estruturas condicionais.

# **Estruturas condicionais**

[![](https://ampli-images.s3.amazonaws.com/production/37523313-c3d7-4a73-bd1e-9a443746dd3d/original)](https://ampli-images.s3.amazonaws.com/production/37523313-c3d7-4a73-bd1e-9a443746dd3d/original)

Estruturas condicionais permitem o controle de execução de um determinado bloco de código se determinada condição for estabelecida. São exemplos de palavras reservadas utilizadas em comandos condicionais: _if_ (usado para verificar se determinada condição foi estabelecida), _else if_ (usado para verificar se determinada condição foi estabelecida caso a anterior não tenha sido) e _else_ (que executa o bloco caso os códigos acima tenham falhado).

[![](https://ampli-images.s3.amazonaws.com/production/ffa95d4d-4124-4245-a20a-b2027f6fbb7b/original)](https://ampli-images.s3.amazonaws.com/production/ffa95d4d-4124-4245-a20a-b2027f6fbb7b/original)

Exemplo de estruturas condicionais em JavaScript. Fonte: elaborado pelo autor.

Nesse exemplo, na linha 5, estamos verificando se a variável numero (que foi declarada igual a 7 na linha 3), quando dividida por 2, apresentará resultado zero. Como 7 dividido por 2 dá 3,5 ou, se analisarmos apenas valores inteiros, 3 com resto 1, logo, essa condição não foi atendida, portanto, será realizado o teste da próxima condição.

Se você executar esse código, visualizará a mensagem “7 é ímpar”. O único bloco executado nessa série de comandos condicionais corresponde à linha 8. Como as outras condições não foram estabelecidas, os blocos foram ignorados. Se mudarmos o valor da variável numero para 70, veremos que 70 dividido por 2 é igual a 35 com resto 0, logo, esse valor será par e a linha 6 será executada.

Entretanto, se nosso resultado só tem duas opções, par ou ímpar, para que serve a última condição? Imagine que seu site está recebendo dados inseridos por usuários; como os usuários são livres para digitar o que quiserem, eles podem tanto digitar um número válido como qualquer coisa que não seja um número.

[![](https://ampli-images.s3.amazonaws.com/production/8548da62-b07b-40d5-9333-2aff7f718716/original)](https://ampli-images.s3.amazonaws.com/production/8548da62-b07b-40d5-9333-2aff7f718716/original)

Modo de verificar se um número é par ou ímpar com estruturas condicionais if e else. Fonte: elaborado pelo autor.

Nesse caso, a variável numero recebeu a mensagem “olá mundo”. Não é possível fazer operações matemáticas com caracteres, logo, é necessário incluir uma opção que execute algo caso todas as condições anteriores falhem.

Outra estrutura condicional é o comando _switch_, que deve ser utilizado quando há uma série de condições que se deseja avaliar. Observe a figura abaixo, em que foi modificado a figura “Modo de verificar se um número é par ou ímpar com estruturas condicionais if e else” e utilizado o comando _switch_:

[![](https://ampli-images.s3.amazonaws.com/production/06fa4a4e-c728-4005-8bd9-0ce40e93a1d1/original)](https://ampli-images.s3.amazonaws.com/production/06fa4a4e-c728-4005-8bd9-0ce40e93a1d1/original)

Modo de verificar se um número é par ou ímpar com estruturas switch. Fonte: elaborado pelo autor.

O comando _switch_ avalia se uma variável é igual a um determinado valor. Para isso, é utilizada a palavra reservada case seguida do valor avaliado. Ao final de cada case, deve ser inserida a palavra _break_. A condição padrão, caso as outras falhem, é definida pela palavra _default_.

# **Estruturas repetitivas**

[![](https://ampli-images.s3.amazonaws.com/production/5d618597-8e92-432b-96ed-ba349cf1fa9e/original)](https://ampli-images.s3.amazonaws.com/production/5d618597-8e92-432b-96ed-ba349cf1fa9e/original)

As estruturas repetitivas, também conhecidas como estruturas interativas, permitem que um determinado bloco seja repetido até que determinada condição seja atendida (_while_) ou para um conjunto determinado de elementos (_for_).

O comando _while_ executa um bloco enquanto uma determinada condição é válida. Veja o exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/fe80eff4-ee97-4a0a-9b26-e78af2cf11d1/original)](https://ampli-images.s3.amazonaws.com/production/fe80eff4-ee97-4a0a-9b26-e78af2cf11d1/original)

Comando while para determinar se uma condição é válida. Fonte: elaborado pelo autor.

Esse código imprimirá no console os valores 0, 1, 2, 3 e 4. A variável i será inicializada com o valor 0 (usamos i como nome da variável por causa da palavra “iteração”), logo, o laço _while_ será executado enquanto i for menor que 5. Ainda dentro do laço _while_, foi feita uma nova atribuição para a variável i, que passou a receber o valor anterior somado com 1.

______

**💭 Reflita**

A incrementação de variáveis dada, por exemplo, pelo código i=i+1 permite que uma variável receba o seu valor atual somado ao valor 1. Poderíamos aplicar isso com outros operadores matemáticos e outros valores, como:

- i = i–1 (subtração)
- i = i**2 (exponenciação – elevado ao quadrado)
- i = i/3 (divisão por três)
- i = i*4 (multiplicação por quatro)

Com base nisso, você consegue imaginar o que aconteceria se não incluísse a linha i = i+1?

______

Você pode ter o mesmo resultado utilizando o comando _for_. Esse comando executa um laço de repetição por uma condição predeterminada. Veja, a seguir, um código que obtém o mesmo resultado:

[![](https://ampli-images.s3.amazonaws.com/production/0b368383-384b-46c7-8fc8-35c86eaa61c1/original)](https://ampli-images.s3.amazonaws.com/production/0b368383-384b-46c7-8fc8-35c86eaa61c1/original)

Comando for e console.log(). Fonte: elaborado pelo autor.

O comando _for_ recebe:

- O nome da variável e o valor inicial.
- A condição de parada.
- A condição de incrementação.

Observe que i++ é equivalente a i = i+1.

Podemos, ainda, usar o comando _for_ para navegar por _arrays_ (coleções indexadas). A seguir, apresentaremos o comando _for_ usado para navegar pelos índices da variável lista:

[![](https://ampli-images.s3.amazonaws.com/production/6049d522-b906-4fd6-bd69-d5fd2cd50758/original)](https://ampli-images.s3.amazonaws.com/production/6049d522-b906-4fd6-bd69-d5fd2cd50758/original)

Utilizando o comando for para navegar por índices de um array. Fonte: elaborado pelo autor.

Para isso, você deverá informar o nome do _array_ (no exemplo, lista) seguido da posição em que se encontra o valor que se deseja imprimir. O código apresentado utiliza a palavra reservada _in_ para verificar quais os valores presentes no _array_. Observe o resultado que será exibido no console:

[![](https://ampli-images.s3.amazonaws.com/production/9003641f-aba6-44c8-9178-b658ab222b37/original)](https://ampli-images.s3.amazonaws.com/production/9003641f-aba6-44c8-9178-b658ab222b37/original)

Comando for. Fonte: captura de tela elaborada pelo autor.

Você pode, ainda, usar a palavra reservada _of_ no lugar de _in_ para obter os valores específicos de cada elemento do _array_.

______

**⚠️ Atenção**

_JavaScript_ é uma linguagem baseada no paradigma de orientação a objetos. Na prática, um objeto pode ser considerado uma entidade independente, que possui propriedades e tipos (MDN WEB DOCS, 2019). No exemplo a seguir, declaramos um objeto que receberá um conjunto de chaves e valores.

[![](https://ampli-images.s3.amazonaws.com/production/cc33cb6a-b753-4414-a757-3d8338975c4e/original)](https://ampli-images.s3.amazonaws.com/production/cc33cb6a-b753-4414-a757-3d8338975c4e/original)

Declarando um objeto em JavaScript. Fonte: elaborado pelo autor.

A linha 9 retornará à visão geral do objeto, enquanto a linha 11 imprimirá apenas o valor presente na chave “A” .

[![](https://ampli-images.s3.amazonaws.com/production/0631b6b8-b9a2-471d-8ed8-f68bd4aa69dd/original)](https://ampli-images.s3.amazonaws.com/production/0631b6b8-b9a2-471d-8ed8-f68bd4aa69dd/original)

Imprimindo os objetos declarados. Fonte: captura de tela elaborada pelo autor.

# **Criando funções**

[![](https://ampli-images.s3.amazonaws.com/production/53d17dd2-2559-4b5c-8df6-405e776c1b92/original)](https://ampli-images.s3.amazonaws.com/production/53d17dd2-2559-4b5c-8df6-405e776c1b92/original)

Estudante, você já aprendeu duas funções _Javascript: alert_() e console.log. Agora, você pode construir suas próprias funções da seguinte forma:

[![](https://ampli-images.s3.amazonaws.com/production/424481a1-58a3-489c-ae4b-021d23504650/original)](https://ampli-images.s3.amazonaws.com/production/424481a1-58a3-489c-ae4b-021d23504650/original)

Uma função pode executar uma determinada ação com base nos argumentos enviados e, ainda, retornar informações para o fluxo principal do programa. Veja que, ao declarar uma função, o bloco no qual ela se encontra é ignorado na execução do código. Esse bloco só será executado quando a função for chamada.

Para executar a função criada, você deve chamá-la pelo nome seguido dos argumentos que serão usados no processamento. Observe como deve ser realizada a chamada da função criada anteriormente:

[![](https://ampli-images.s3.amazonaws.com/production/54e05bc7-6024-4073-917e-3ec6e95d83c8/original)](https://ampli-images.s3.amazonaws.com/production/54e05bc7-6024-4073-917e-3ec6e95d83c8/original)

No exemplo a seguir, você construirá uma função que recebe dois parâmetros, a e b, e retorna a soma dos dois valores.

[![](https://ampli-images.s3.amazonaws.com/production/9dfb0c90-2d63-4c17-8ea1-603e7d8774d7/original)](https://ampli-images.s3.amazonaws.com/production/9dfb0c90-2d63-4c17-8ea1-603e7d8774d7/original)

Função soma que retorna a soma de dois valores. Fonte: elaborado pelo autor.

______

**➕ Pesquise mais**

_JS Bin_ é uma ferramenta web gratuita e um _software_ para desenvolvimento de websites. No _JS Bi_n, você pode criar e editar seus próprios websites com _JavaScript_ diretamente do seu navegador (JS BIN, [s.d.]).

______

Nesta aula, você aprendeu os fundamentos de programação com a linguagem JavaScript. Agora, você já pode aplicar os seus conhecimentos sobre essa linguagem.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Anteriormente, você foi desafiado a implementar uma função que exiba na seção de planos de internet de um site a seguinte mensagem, apenas às quartas-feiras:

[![](https://ampli-images.s3.amazonaws.com/production/7eb3d7c9-4b3b-4623-a36e-afcbd1aae622/original)](https://ampli-images.s3.amazonaws.com/production/7eb3d7c9-4b3b-4623-a36e-afcbd1aae622/original)

Observe o resultado de como a página ficará em dias diferentes da semana:

[![](https://ampli-images.s3.amazonaws.com/production/5ad3f88e-d646-43e7-8e00-618e5cc9195a/original)](https://ampli-images.s3.amazonaws.com/production/5ad3f88e-d646-43e7-8e00-618e5cc9195a/original)

Domingo, segunda-feira, terça-feira, quinta-feira, sexta-feira e sábado. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/0952c7d6-6039-49af-b854-15e254099659/original)](https://ampli-images.s3.amazonaws.com/production/0952c7d6-6039-49af-b854-15e254099659/original)

Quarta-feira. Fonte: elaborada pelo autor.

Agora observe o código utilizado para realizar isso (as linhas comentadas explicam cada trecho do código):

[![](https://ampli-images.s3.amazonaws.com/production/6523b6e9-c6db-47c9-9480-e97b4a692356/original)](https://ampli-images.s3.amazonaws.com/production/6523b6e9-c6db-47c9-9480-e97b4a692356/original)

Resolução da situação-problema – Página “Planos”. Fonte: elaborada pelo autor.