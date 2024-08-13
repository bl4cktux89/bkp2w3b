# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/74e82df0-da03-4248-9c9c-6a4a8b2e18d8/original)](https://ampli-images.s3.amazonaws.com/production/74e82df0-da03-4248-9c9c-6a4a8b2e18d8/original)

### **Qual é o foco da aula?**

Nesta aula, você irá conhecer o _Document Object Model_ (DOM).

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- definir vídeos com _JavaScript_;
- empregar geolocalização em mapas interativos.;
- analisar eventos em formulários.

**Situação-problema**

Olá, estudante!

Seja bem-vindo à segunda aula de _JavaScript_. Compreender _JavaScript_ é fundamental para construir páginas dinâmicas e interativas, que poderão atrair mais os usuários.

Nesta aula, você conhecerá o **Modelo de Objetos de Documento** (do inglês _Document Object Model_ ou apenas DOM). O DOM é fundamental para realizar alterações no documento web após o carregamento da página usando _JavaScrip_t. Por meio do DOM é possível selecionar um determinado campo e realizar alterações de forma interativa e sem a necessidade de realizar uma nova requisição ao servidor.

Considere que você deseja construir um formulário de cadastro em um determinado site. Seu formulário tem um campo para inserção de CPF; entretanto, seu site tem recebido muitos cadastros falsos, o que tem comprometido a capacidade de processamento do servidor. Por exemplo, se um usuário digita um CPF inválido, como 000.000.000-00, o formulário é submetido ao servidor, que processará as informações e retornará um aviso indicando que se trata de um CPF inválido. Você poderia utilizar JavaScript para validar esse campo antes de o formulário ser enviado ao servidor. Para isso, deverá utilizar a árvore DOM para buscar os valores digitados no campo input que recebe o CPF. Depois, você deverá utilizar algum “gatilho” para ativar a validação. Chamamos esses gatilhos de **eventos**, que podem ser diversos, como ao clicar em um botão ou ao digitar em um campo.

Você também aprenderá a respeito da manipulação de vídeos com _JavaScript_ e HTML5 e ainda verá como usar geolocalização para criar mapas interativos.

A fim de colocarmos em prática os conhecimentos a serem aprendidos, vamos analisar a seguinte situação-problema: o departamento de marketing da empresa pela qual você foi contratado decidiu que ela precisa ter sua localização transparente, para que os clientes possam visitá-la. Portanto, decidiram adicionar uma seção “como chegar”.

Você foi incumbido de incluir essa funcionalidade e deverá construir um mapa interativo para exibir a localização da empresa. Além disso, um mapa interativo deverá ser adicionado à página criada anteriormente.

A empresa está localizada nas seguintes coordenadas:

- var lat = -20.5.
- var lon = -43.86.

Use o _OpenLayers_ para exibir o mapa. Você pode instalá-lo usando o comando npm:

npm _install_ ol

Você também pode executá-lo sem instalação inserindo o trecho mostrado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/e0ff0a94-cf93-48bb-908a-38eec9bea65a/original)](https://ampli-images.s3.amazonaws.com/production/e0ff0a94-cf93-48bb-908a-38eec9bea65a/original)

Execução do OpenLayers sem instalação. Fonte: elaborado pelo autor.

Outra opção é fazer o download manual dos arquivos para execução local, disponíveis no material suplementar: **v6.5.0-dist.zip**.

Não se esqueça de incluir os seguintes arquivos:

- ol.css.
- ol.js.
- ol.css.map.
- ol.js.map.

Não deixe de praticar o desenvolvimento de scripts usando _JavaScript_. E, sempre que possível, construa páginas completas usando HTML, CSS e JS.

Bons estudos!

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/b7e06684-daca-4d5b-89ec-0425d813c511/original)](https://ampli-images.s3.amazonaws.com/production/b7e06684-daca-4d5b-89ec-0425d813c511/original)

_JavaScript_ é uma linguagem cujo processamento é realizado diretamente no navegador do cliente. Entretanto, muitas vezes um desenvolvedor deseja que alterações sejam realizadas em partes do código que já foram carregadas. Por exemplo, pense em um formulário de cadastro. Deseja-se conferir se o usuário preencheu todos os campos. Entretanto, essa verificação só deverá ser executada depois que o usuário clicar no botão “enviar”. Podemos fazer essas modificações _back-end_, mas isso apenas acarretaria um custo de processamento desnecessário para nosso servidor. Podemos então utilizar o navegador do cliente para realizar esse processamento usando _JavaScript_. Para verificar o estado de elementos de um documento web, podemos utilizar a árvore DOM.

Documentos web são compostos por _tags_ que se conectam a outras _tags_ em uma grande rede. Uma forma de visualizar a estrutura dessas páginas é com base no Modelo de Objetos de Documento (do inglês _Document Object Model_ ou apenas DOM). O DOM representa a estrutura de documentos HTML, SVG ou XML como uma árvore (MDN WEB DOCS, [s.d.]). A figura abaixo mostra a estrutura da Árvore DOM.

[![](https://ampli-images.s3.amazonaws.com/production/4e1d4d5d-de08-48e7-969d-d49ab998ce40/original)](https://ampli-images.s3.amazonaws.com/production/4e1d4d5d-de08-48e7-969d-d49ab998ce40/original)

Árvore DOM. Fonte: adaptada de Mariano; De Melo-Minardi (2017).

Uma das principais vantagens do DOM é a sua capacidade de ser manipulado por meio de linguagens de _script_, como _JavaScript_.

A seguir, as figuras “index.html” e “script.js”, é apresentado um exemplo do uso de _JavaScript_ para manipulação do DOM. Neste exemplo, foram coletadas todas as _tags_ <p> :

[![](https://ampli-images.s3.amazonaws.com/production/d1c0442f-e5c1-41d7-bbd1-46b33c0ac8ad/original)](https://ampli-images.s3.amazonaws.com/production/d1c0442f-e5c1-41d7-bbd1-46b33c0ac8ad/original)

[![](https://ampli-images.s3.amazonaws.com/production/d820d642-345e-4464-a95b-a04caac7be5d/original)](https://ampli-images.s3.amazonaws.com/production/d820d642-345e-4464-a95b-a04caac7be5d/original)

index.html - Exemplo de manipulação do DOM. Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/fcd93983-e294-4d50-8641-20f0dd918215/original)](https://ampli-images.s3.amazonaws.com/production/fcd93983-e294-4d50-8641-20f0dd918215/original)

script.js – Coletando todas as tags <p>. Fonte: elaborado pelo autor.

A figura abaixo ilustra o resultado ao carregar o código dessa página em um navegador.

[![](https://ampli-images.s3.amazonaws.com/production/373c1d65-371e-4a97-bc34-470a86013529/original)](https://ampli-images.s3.amazonaws.com/production/373c1d65-371e-4a97-bc34-470a86013529/original)

Manipulação do DOM usando JavaScript. Fonte: captura de tela de DOM elaborada pelo autor.

Agora, vamos analisar o _script_ linha por linha:

- Na linha 2, temos o comando window.onload = _function_(){}. Ele possibilita que o bloco da função (que engloba todos os comandos na sequência) só seja executado se o evento de carregamento da janela for concluído.
- A seguir é declarada uma constante denominada parágrafos, que recebe o resultado da função que seleciona todos os resultados do seletor <p>.

[![](https://ampli-images.s3.amazonaws.com/production/04107e66-e3e8-4094-9d35-2dde4d366c99/original)](https://ampli-images.s3.amazonaws.com/production/04107e66-e3e8-4094-9d35-2dde4d366c99/original)

- Na linha 8, é exibido no console o conteúdo da constante parágrafos:

[![](https://ampli-images.s3.amazonaws.com/production/f7ea05dc-1f1a-4919-aae0-1b91bcef5395/original)](https://ampli-images.s3.amazonaws.com/production/f7ea05dc-1f1a-4919-aae0-1b91bcef5395/original)

- Observe que ao imprimir o conteúdo do objeto parágrafos pode-se observar uma lista de nós (figura “Manipulação do DOM usando JavaScript”). A página apresenta três parágrafos; logo, pode-se observar três elementos: 0, 1 e 2. Assim, é possível exibir o conteúdo da primeira tag (<p>Parágrafo 1</p>) executando o código:

[![](https://ampli-images.s3.amazonaws.com/production/2da17571-5d4f-4c84-8108-28c8326bfd0c/original)](https://ampli-images.s3.amazonaws.com/production/2da17571-5d4f-4c84-8108-28c8326bfd0c/original)

🔁 **Assimile**

Por que foi necessário usar o comando:

[![](https://ampli-images.s3.amazonaws.com/production/a853861d-3f4d-4508-9026-26d4a454255d/original)](https://ampli-images.s3.amazonaws.com/production/a853861d-3f4d-4508-9026-26d4a454255d/original)

Você pode verificar que, ao abrir o arquivo HTML, as _tags_ serão carregadas linha a linha (note que declaramos o _script_ na linha 8 da figura “index.html - Exemplo de manipulação do DOM”). Logo, o _script_ só poderia analisar o conteúdo que aparece antes dele. Como não há parágrafos antes da declaração do _script_, os códigos _JavaScript_ não conseguiriam coletar informação alguma. Uma solução para isso é incluir a chamada do script no final da página. Entretanto, _JavaScript_ fornece soluções mais robustas por meio de eventos de carregamento, como o evento _onload_. Esse comando executa o bloco de código apenas ao final do carregamento da página, ou seja, garante que todas as _tags_ necessárias já tenham sido carregadas.

# **Modificando a estrutura do HTML usando JavaScript e DOM**

[![](https://ampli-images.s3.amazonaws.com/production/33a5314f-da72-4122-90d8-5e96c723ee77/original)](https://ampli-images.s3.amazonaws.com/production/33a5314f-da72-4122-90d8-5e96c723ee77/original)

Podemos alterar a estrutura de uma página usando o DOM. Observe, a seguir, os métodos _JavaScript_ que podem ser utilizados para essa modificação:

[![](https://ampli-images.s3.amazonaws.com/production/6052ab98-d0ae-4d36-aecb-6792a2219631/original)](https://ampli-images.s3.amazonaws.com/production/6052ab98-d0ae-4d36-aecb-6792a2219631/original)

Métodos de manipulação do documento. Fonte: adaptado de Mariano; De Melo-Minardi (2017, p. 359-360).

Veja a figura abaixo (Console). Ela mostra o preenchimento dessa página usando apenas propriedades de manipulação do DOM no arquivo _JavaScript_.

[![](https://ampli-images.s3.amazonaws.com/production/e3e104da-a674-439c-ad13-abb5161145af/original)](https://ampli-images.s3.amazonaws.com/production/e3e104da-a674-439c-ad13-abb5161145af/original)

[![](https://ampli-images.s3.amazonaws.com/production/44286a75-1b96-408e-a74d-2efcafa73a0e/original)](https://ampli-images.s3.amazonaws.com/production/44286a75-1b96-408e-a74d-2efcafa73a0e/original)

Console. Fonte: captura de tela de DOM. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/441bd02f-679a-4c1a-8b90-0034d910231d/original)](https://ampli-images.s3.amazonaws.com/production/441bd02f-679a-4c1a-8b90-0034d910231d/original)

[![](https://ampli-images.s3.amazonaws.com/production/ee4a216d-cacf-45ee-b31a-1c112cb13004/original)](https://ampli-images.s3.amazonaws.com/production/ee4a216d-cacf-45ee-b31a-1c112cb13004/original)

[![](https://ampli-images.s3.amazonaws.com/production/bd9a7065-6736-4c04-bb00-fcf805276983/original)](https://ampli-images.s3.amazonaws.com/production/bd9a7065-6736-4c04-bb00-fcf805276983/original)

[![](https://ampli-images.s3.amazonaws.com/production/f4e30d73-ff20-4829-af85-f2a8a82fa87e/original)](https://ampli-images.s3.amazonaws.com/production/f4e30d73-ff20-4829-af85-f2a8a82fa87e/original)

index.html e estilo.css – apresentam duas divisões (divs): a div na cor vermelha, com a mensagem “Olá Mundo!”, e a div na cor azul. Fonte: elaborado pelo autor.

A figura abaixo ilustra a página web gerada.

[![](https://ampli-images.s3.amazonaws.com/production/b6c1547a-1a7b-48b5-929b-6da839141814/original)](https://ampli-images.s3.amazonaws.com/production/b6c1547a-1a7b-48b5-929b-6da839141814/original)

Exemplo de uso de JS. Fonte: captura de tela de DOM elaborada pelo autor.

Observe que temos um bloco vermelho ao lado de um bloco azul. Apenas no bloco vermelho foi inserido o texto: “Olá mundo!”.

______

**💭 Reflita**

Na figura “Exemplo de uso de JS”, você pôde observar que as duas _divs_ ocupam todo o espaço disponível na página. As propriedades CSS utilizadas para definição de tamanho e posicionamento são de grande importância, principalmente na construção de páginas com design responsivo.

Você consegue identificar as propriedades CSS usadas para deixar as _divs_ ocupando toda a largura e altura da página? Qual propriedade foi utilizada para posicionar a _div_ azul ao lado da vermelha?

______

Agora, você pode verificar as propriedades _JavaScript_ para mover o conteúdo do bloco vermelho para o bloco azul. Para isso, precisamos da função que navega pelo DOM, além de coletar o elemento com base no seu ID. Esse método é document.getElementById().

[![](https://ampli-images.s3.amazonaws.com/production/82bfd015-e3ef-40c3-b002-380b560ba1d0/original)](https://ampli-images.s3.amazonaws.com/production/82bfd015-e3ef-40c3-b002-380b560ba1d0/original)

Método document.getElementById(). Fonte: elaborado pelo autor.

Observe o resultado na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/2c89b233-1ab5-4dd5-acc3-b6a76d0d93ba/original)](https://ampli-images.s3.amazonaws.com/production/2c89b233-1ab5-4dd5-acc3-b6a76d0d93ba/original)

JavaScript usado para mover o texto de lugar. Fonte: captura de tela do DOM elaborada pelo autor.

Estudante, neste momento veremos o passo a passo do que foi realizado, mais uma vez usando o seguinte comando:

[![](https://ampli-images.s3.amazonaws.com/production/41852bc7-4cde-49e9-9a94-d58e3e549f8f/original)](https://ampli-images.s3.amazonaws.com/production/41852bc7-4cde-49e9-9a94-d58e3e549f8f/original)

Isso para que os códigos presentes na função sejam executados apenas após o carregamento da página, uma vez que optamos em declarar o script no cabeçalho.

[![](https://ampli-images.s3.amazonaws.com/production/f89d8b1a-5573-4f76-8fff-5561037b513c/original)](https://ampli-images.s3.amazonaws.com/production/f89d8b1a-5573-4f76-8fff-5561037b513c/original)

Usamos o método getElementById( ) para coletar o elemento com ID “B”. Observe que o atributo textContent  informa o que se deseja aplicar ao conteúdo do texto. Assim, o operador de atribuição foi utilizando-o para informar que será aplicado ao texto o conteúdo do elemento de ID “A”. Nesse caso, utilizamos o atributo innerHTML. Assim, foi informado qual era o conteúdo do HTML do elemento daquele ID. Então, o conteúdo de A é copiado para B.

[![](https://ampli-images.s3.amazonaws.com/production/d822a893-91fb-4dd3-bf9f-a7d9a26c6af5/original)](https://ampli-images.s3.amazonaws.com/production/d822a893-91fb-4dd3-bf9f-a7d9a26c6af5/original)

Por fim, foi aplicado ao HTML interno do elemento de ID “A” o valor " (vazio). Ou seja, o texto existente é substituído por um valor em branco.

______

**📝 Exemplificando**

**Você sabe qual a diferença entre textContent e innerHTML?**

Neste exemplo, usamos textContent e innerHTML para estimular o debate acerca do uso de cada um. Observe que na div A temos apenas texto. Entretanto, imagine o que aconteceria se tivéssemos o seguinte conteúdo:

[![](https://ampli-images.s3.amazonaws.com/production/81a4c7a8-d7a3-4b4a-a0b9-9759e351703d/original)](https://ampli-images.s3.amazonaws.com/production/81a4c7a8-d7a3-4b4a-a0b9-9759e351703d/original)

Observe que o texto está envolvido por uma _tag_  <p></p>. Será que a _tag_ seria transferida?

Usando _textContent_ não, pois apenas o texto seria coletado. Entretanto, ao usar innerHTML, você consegue coletar todo o conteúdo HTML presente no elemento, logo a _tag_ <p> também seria transferida.

______

Observe a figura a seguir, em que temos uma lista de comandos _JavaScript_ para modificação do DOM.

[![](https://ampli-images.s3.amazonaws.com/production/2de00393-86dd-4e0e-9a0a-216840be91fd/original)](https://ampli-images.s3.amazonaws.com/production/2de00393-86dd-4e0e-9a0a-216840be91fd/original)

Comandos JavaScript. Fonte: adaptado de Mariano; De Melo-Minardi (2017, p. 359).

# **Alterando o estilo**

[![](https://ampli-images.s3.amazonaws.com/production/739c7090-9998-459c-9a4b-d41f8e195507/original)](https://ampli-images.s3.amazonaws.com/production/739c7090-9998-459c-9a4b-d41f8e195507/original)

Você também pode utilizar os comandos _JavaScript_ para alterar os estilos CSS. Para isso, deve-se coletar o objeto pelo ID e, a seguir, aplicar a propriedade desejada com a seguinte sintaxe:

element.style.property

Em que: o _element_ representa o objeto coletado; o style indica que se deseja alterar o estilo; e _property_ deve ser substituído com o nome da propriedade desejada.

Vamos alterar o exemplo anterior, para que seja possível alterar a cor de fundo da div A:

[![](https://ampli-images.s3.amazonaws.com/production/57a317a4-f4de-4f01-a89e-b2af358894fe/original)](https://ampli-images.s3.amazonaws.com/production/57a317a4-f4de-4f01-a89e-b2af358894fe/original)

Observe que a propriedade que altera a cor de fundo é _background-color._ Entretanto, não é permitido o uso de “-” no nome do atributo. Portanto, é necessário remover o traço e utilizar um caractere maiúsculo na próxima palavra: _backgroundColor_. A figura abaixo ilustra o resultado da alteração da cor do fundo da página.

[![](https://ampli-images.s3.amazonaws.com/production/e6293d61-2ec4-4c3d-b0f5-7975e6f6d3a4/original)](https://ampli-images.s3.amazonaws.com/production/e6293d61-2ec4-4c3d-b0f5-7975e6f6d3a4/original)

Alterando a cor. Fonte: captura de tela do DOM elaborada pelo autor.

# **Seleção por Tags e Classes**

[![](https://ampli-images.s3.amazonaws.com/production/bc1a3caf-80c0-4350-ab5d-fe8972353b16/original)](https://ampli-images.s3.amazonaws.com/production/bc1a3caf-80c0-4350-ab5d-fe8972353b16/original)

Você aprendeu que a seleção de elementos pode ser realizada por ID. Outra forma de realizar esse procedimento é utilizando a seleção por classes ou pelas _tags_, caso seja necessário alterar vários elementos.

A seguir, vamos criar uma classe no arquivo estilo.css:

[![](https://ampli-images.s3.amazonaws.com/production/ec965710-2349-4a6e-ae26-e2a26d79d112/original)](https://ampli-images.s3.amazonaws.com/production/ec965710-2349-4a6e-ae26-e2a26d79d112/original)

Essa classe apenas muda a cor do texto para branco. Você pode adicioná-la manualmente no arquivo HTML, mas vamos fazer de uma forma diferente: utilizando JS.

Agora, pode-se editar o arquivo script.js mostrado na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/fc8ff66e-bade-4473-bdd7-41531a76e4ca/original)](https://ampli-images.s3.amazonaws.com/production/fc8ff66e-bade-4473-bdd7-41531a76e4ca/original)

Arquivo script.js. Fonte: elaborado pelo autor.

Como será utilizado o conteúdo do elemento A para este exemplo, você pode comentar a linha que o apaga:

//document.getElementById("A").innerHTML = '';

A seguir, pode-se utilizar uma variável para selecionar nosso elemento desejado:

[![](https://ampli-images.s3.amazonaws.com/production/e953b7c7-3371-4d6b-a98c-e1dfac786f54/original)](https://ampli-images.s3.amazonaws.com/production/e953b7c7-3371-4d6b-a98c-e1dfac786f54/original)

Utilizamos o método _getElementsByTagName(_) no lugar da função _getElementById_() para coletar o elemento. Esse método seleciona elementos com base no nome da _tag_ (no exemplo, foi selecionada a _tag_ <div>).

______

🔁 **Assimile**

Tome cuidado com o nome das funções

- _getElementsByTagName_: o nome fica no plural (_Elements_), pois esse método coleta várias _tags_.
- _getElementByld_: o nome fica no singular (_Element_), pois um ID deve ser único.

Observe o trecho de código a seguir. Há um laço de repetição que vai de 0 ao tamanho do objeto elemento, acrescentando 1 valor a cada iteração. Observe que o tamanho da variável elemento indica a quantidade de _tags_ existentes (no caso temos duas divs) e pode ser obtido com o atributo _length_. Observe que foi utilizado apenas o operador menor (“<”), uma vez que, em computação, a contagem geralmente começa do valor zero (logo, se o array possui dois valores, eles terão índices 0 e 1).

[![](https://ampli-images.s3.amazonaws.com/production/4e048dc2-1ca4-4512-951e-4f62b07152f7/original)](https://ampli-images.s3.amazonaws.com/production/4e048dc2-1ca4-4512-951e-4f62b07152f7/original)

Importa destacar que não podemos aplicar essa classe a todo o objeto elemento, mas a posições específicas [i]. Por isso, foi necessário utilizar um laço de repetição para coletar os valores possíveis da variável i. Note que o laço fará duas iterações. Na primeira, i vale 0, logo o comando executado seria:

[![](https://ampli-images.s3.amazonaws.com/production/f3e91bdb-e552-42c3-92c8-261a19fbc2dd/original)](https://ampli-images.s3.amazonaws.com/production/f3e91bdb-e552-42c3-92c8-261a19fbc2dd/original)

Observe que, ao fazer isso, a nova propriedade CSS sobrepõe as regras apresentadas anteriormente (mesmo que os elementos ainda apresentem a classe texto-branco; neste caso, o texto se tornará amarelo), conforme a figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/1a8f9528-a98e-4a1c-99f9-d82001865f3f/original)](https://ampli-images.s3.amazonaws.com/production/1a8f9528-a98e-4a1c-99f9-d82001865f3f/original)

Efeito cascata. Fonte: captura de tela de DOM elaborada pelo autor.

Isso ocorre devido ao “efeito cascata”: regras aplicadas com o atributo _style_ têm prioridade em relação a regras de estilo obtidas de um arquivo externo.

# **Eventos**

[![](https://ampli-images.s3.amazonaws.com/production/48bf730d-9c94-47c7-8444-5fb6bd1e594c/original)](https://ampli-images.s3.amazonaws.com/production/48bf730d-9c94-47c7-8444-5fb6bd1e594c/original)

Eventos permitem interações entre os elementos de uma página HTML e o arquivo _JavaScript_, possibilitando alterações pelo DOM. Existem diversos tipos de eventos que podem atuar, por exemplo, quando um botão é clicado, quando uma página é carregada (como apresentado anteriormente), quando uma tecla é pressionada, entre muitos outros. A figura a seguir sintetiza uma lista de eventos e suas definições.

[![](https://ampli-images.s3.amazonaws.com/production/a0897932-862c-4bdc-9999-9a7fee71b992/original)](https://ampli-images.s3.amazonaws.com/production/a0897932-862c-4bdc-9999-9a7fee71b992/original)

Tipos de eventos. Fonte: adaptado de Mariano; De Melo-Minardi (2017, p. 349-350).

Como exemplo, vamos explorar o evento _onclick_ (ao clicar em um botão).

Primeiro crie o botão na página HTML:

[![](https://ampli-images.s3.amazonaws.com/production/0863e641-bab0-4dfd-a206-14acce158142/original)](https://ampli-images.s3.amazonaws.com/production/0863e641-bab0-4dfd-a206-14acce158142/original)

Observe que o atributo _onclick_ recebe entre aspas a função clique(). Isso indica que quando o evento _onclick_ for disparado (ou seja, quando o botão for clicado), a página deverá executar a função clique(). Agora, vamos criar essa função no arquivo _JavaScript_:

[![](https://ampli-images.s3.amazonaws.com/production/73cb8449-ec23-48cc-815a-ada71641bc59/original)](https://ampli-images.s3.amazonaws.com/production/73cb8449-ec23-48cc-815a-ada71641bc59/original)

Essa função apenas exibe a mensagem “Olá mundo!”. Observe que não foi necessário utilizar o comando window.onload, uma vez que o evento só será disparado quando o usuário clicar no botão. A figura abaixo apresenta o resultado da aplicação.

[![](https://ampli-images.s3.amazonaws.com/production/145fb99f-515a-40d5-bdf6-9f76dab142d3/original)](https://ampli-images.s3.amazonaws.com/production/145fb99f-515a-40d5-bdf6-9f76dab142d3/original)

Evento onclick. Fonte: captura de tela do DOM elaborada pelo autor.

# **Elementos de formulário**

[![](https://ampli-images.s3.amazonaws.com/production/749ad2dd-24de-42f1-8898-33669face836/original)](https://ampli-images.s3.amazonaws.com/production/749ad2dd-24de-42f1-8898-33669face836/original)

Vamos usar as propriedades JS para analisar formulários. Suponhamos que temos o seguinte formulário e desejamos formatá-lo:

[![](https://ampli-images.s3.amazonaws.com/production/9ec8f00b-7653-470c-bd41-50a79dca7862/original)](https://ampli-images.s3.amazonaws.com/production/9ec8f00b-7653-470c-bd41-50a79dca7862/original)

Formulário com nome e telefone. Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/99699699-197b-4eef-83c2-bc5cdee6c297/original)](https://ampli-images.s3.amazonaws.com/production/99699699-197b-4eef-83c2-bc5cdee6c297/original)

Resultado do código: formulário com nome e telefone. Fonte: captura de tela de DOM elaborada pelo autor.

Vamos aplicar uma propriedade que seja exclusiva para cada campo. Para isso, vamos criar uma função que apresenta parâmetros e recebe argumentos enviados na chamada. Também vamos explorar o evento _onmouseover_ (quando o cursor está sobre o elemento). No arquivo JS, crie a seguinte função:

[![](https://ampli-images.s3.amazonaws.com/production/82e30542-fda3-4155-ac75-9ebea6500dfd/original)](https://ampli-images.s3.amazonaws.com/production/82e30542-fda3-4155-ac75-9ebea6500dfd/original)

Função para formatar os elementos input. Fonte: elaborado pelo autor.

Essa função recebe um ID passado em sua chamada, depois seleciona o elemento, a seguir aplica a propriedade _box-shadow_ (uma sombra azul de 30px de desfoque e 0 de movimentação nos eixos x e y) e altera o atributo _placeholder_.

O atributo _placeholder_ exibe uma mensagem em um campo _input_ que desaparece quando o usuário clica sobre ele. Nos exemplos, exibimos as mensagens “Nome” e “Telefone”. Agora, vamos usar um valor enviado para a função para personalizar a mensagem: ao passar o mouse sobre o campo, a mensagem “Nome” será substituída por “Digite seu nome”, e o mesmo para telefone.

Observe que na declaração da função é adicionada a variável id dentro dos parênteses. Nesse caso, id representa uma variável criada e utilizada especificamente no escopo dessa função. Essa variável será utilizada para buscar o elemento na linha:

[![](https://ampli-images.s3.amazonaws.com/production/1490707c-e2b5-4d6d-bc33-e52cafc0f909/original)](https://ampli-images.s3.amazonaws.com/production/1490707c-e2b5-4d6d-bc33-e52cafc0f909/original)

Vamos então configurar o HTML para realizar a chamada da função quando o evento ocorrer:

[![](https://ampli-images.s3.amazonaws.com/production/339439a2-99a0-45e6-b471-c7c43dc5e91b/original)](https://ampli-images.s3.amazonaws.com/production/339439a2-99a0-45e6-b471-c7c43dc5e91b/original)

input do formulário com evento onmouseover (observe a função formata_input). Fonte: elaborado pelo autor.

No exemplo apresentado, não há qualquer problema em quebrar as linhas dentro da _tag <input_>. Isso facilita a leitura do arquivo.

Observe que o evento utilizado chama a função criada anteriormente e envia um argumento similar ao ID do elemento:

[![](https://ampli-images.s3.amazonaws.com/production/c515b96c-c0f3-42b0-bdaf-3ad89b29ed6b/original)](https://ampli-images.s3.amazonaws.com/production/c515b96c-c0f3-42b0-bdaf-3ad89b29ed6b/original)

Observe o que ocorre ao posicionar o mouse sobre o campo _input:_

[![](https://ampli-images.s3.amazonaws.com/production/72916489-239a-4571-a1bd-2398d57aa7ad/original)](https://ampli-images.s3.amazonaws.com/production/72916489-239a-4571-a1bd-2398d57aa7ad/original)

Evento onmouseover. Fonte: captura de tela de DOM elaborada pelo autor.

Um problema identificado é que ao remover o mouse do campo, o estilo é mantido. O campo deverá normalizar ao mover o cursor para fora. Para fazer isso, podemos utilizar o evento _onmouseout_.

Para isso, você pode criar uma função que volte as configurações ao normal:

[![](https://ampli-images.s3.amazonaws.com/production/021befef-32a0-482c-b4d1-9cebb281d1ef/original)](https://ampli-images.s3.amazonaws.com/production/021befef-32a0-482c-b4d1-9cebb281d1ef/original)

E, depois, vamos adicionar o evento _onmouseout_, mostrado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/6f1b3eed-f79d-4df8-9e48-4cfceb9afabf/original)](https://ampli-images.s3.amazonaws.com/production/6f1b3eed-f79d-4df8-9e48-4cfceb9afabf/original)

Evento onmouseout. Fonte: elaborado pelo autor.

Dessa forma, o campo retorna ao normal ao remover o cursor dele.

Agora, considere que você deseja aplicar um estilo em ambos os campos _input_ ao mesmo tempo. Para isso, você vai aprender a realizar a chamada de uma função dentro de outra função. A seguir, será apresentado um exemplo em que, ao passar o mouse sobre o campo, é adicionada uma margem interna de 5px a todos os campos _input_. Então você pode criar duas funções, _formata_input__geral() e _remove__estilo_geral(), uma para adicionar a margem interna e a outra para removê-la, respectivamente.

[![](https://ampli-images.s3.amazonaws.com/production/dca41a85-ef7c-4a72-8744-e5bc412934ff/original)](https://ampli-images.s3.amazonaws.com/production/dca41a85-ef7c-4a72-8744-e5bc412934ff/original)

[![](https://ampli-images.s3.amazonaws.com/production/5bb9820f-f928-47ff-a01d-41b0452344cb/original)](https://ampli-images.s3.amazonaws.com/production/5bb9820f-f928-47ff-a01d-41b0452344cb/original)

script.js – Funções formata_input_geral() e remove_estilo_geral(). Fonte: elaborado pelo autor.

Pode-se realizar as chamadas dessas funções dentro das funções que criamos anteriormente. Observe a figura abaixo “Trecho de código script.js – Funções formata_input(id) e voltar_normal(id)” contendo duas funções e fazendo a chamada das funções formata_input_geral() e remove_estilo_geral() criadas na figura “script.js – Funções formata_input_geral() e remove_estilo_geral()”

[![](https://ampli-images.s3.amazonaws.com/production/3c8854d5-548e-41ec-881d-7445be423c91/original)](https://ampli-images.s3.amazonaws.com/production/3c8854d5-548e-41ec-881d-7445be423c91/original)

Trecho de código script.js – Funções formata_input(id) e voltar_normal(id). Fonte: elaborado pelo autor.

Agora compare os resultados:

[![](https://ampli-images.s3.amazonaws.com/production/9b32d066-43d2-40e5-b026-0b0328377c66/original)](https://ampli-images.s3.amazonaws.com/production/9b32d066-43d2-40e5-b026-0b0328377c66/original)

[![](https://ampli-images.s3.amazonaws.com/production/a3462e0e-6b0e-46c0-8288-017d00b3246b/original)](https://ampli-images.s3.amazonaws.com/production/a3462e0e-6b0e-46c0-8288-017d00b3246b/original)

# **JSON**

[![](https://ampli-images.s3.amazonaws.com/production/b3b08b79-3e8b-4231-8767-ed5130629b0a/original)](https://ampli-images.s3.amazonaws.com/production/b3b08b79-3e8b-4231-8767-ed5130629b0a/original)

JSON (_JavaScript Object Notation_) é o formato usado para armazenamento e troca de informações em arquivos de texto. JSON foi baseado no _JavaScript,_ mas pode ser usado independentemente da linguagem de programação (ECMA-404 THE JSON DATA INTERCHANGE STANDARD, [s.d.]).

Arquivos JSON são compostos por objetos que apresentam um conjunto de chaves e valores separadas por vírgula. Valores podem receber _strings_ (escritas com aspas), numerais (escritos sem aspas), _arrays_, estruturas lógicas, objetos nulos (_null_) ou até mesmo outros objetos.

Sintaxe do JSON:

[![](https://ampli-images.s3.amazonaws.com/production/1d9bb535-d63c-49c6-8c6a-d7f7b20c948d/original)](https://ampli-images.s3.amazonaws.com/production/1d9bb535-d63c-49c6-8c6a-d7f7b20c948d/original)

### **Manipulando JSON com JS**

Em geral, arquivos JSON são salvos em um arquivo separado na extensão “.json”. Observe o exemplo “**empresa.json**” a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/f41dc629-aa2b-4e35-9396-9acb480fa3bd/original)](https://ampli-images.s3.amazonaws.com/production/f41dc629-aa2b-4e35-9396-9acb480fa3bd/original)

Estudante, veja que para o JS a chave não precisa de aspas, mas ao salvar em arquivo, essas aspas são necessárias. Para ilustrar o exemplo, faremos sua declaração diretamente no código JS como uma _string_. Observe a figura abaixo e o resultado dele ilustrado na figura abaixo “Objetos”:

[![](https://ampli-images.s3.amazonaws.com/production/7977049a-a672-4d95-b35b-575075fe2cac/original)](https://ampli-images.s3.amazonaws.com/production/7977049a-a672-4d95-b35b-575075fe2cac/original)

Trecho JSON - código script.js. Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/1a225e04-2a03-4f7c-b920-10ebc8d04ef2/original)](https://ampli-images.s3.amazonaws.com/production/1a225e04-2a03-4f7c-b920-10ebc8d04ef2/original)

Objetos. Fonte: captura de tela elaborada pelo autor.

Aqui, o objeto funcionários possui um _array_ com três outros objetos constituídos por três pares de chave-valor: nome, sobrenome e idade.

Vamos, então, navegar por esse objeto. Podemos obter o nome e a idade do primeiro funcionário usando o código:

[![](https://ampli-images.s3.amazonaws.com/production/7a8a26cf-9a83-4715-94ac-c82ee2e0ee3d/original)](https://ampli-images.s3.amazonaws.com/production/7a8a26cf-9a83-4715-94ac-c82ee2e0ee3d/original)

[![](https://ampli-images.s3.amazonaws.com/production/788bca48-65f1-457b-8f04-d6f4e37be4f5/original)](https://ampli-images.s3.amazonaws.com/production/788bca48-65f1-457b-8f04-d6f4e37be4f5/original)

Visualizando os objetos. Fonte: captura de tela de DOM elaborada pelo autor.

Observe que para obter as informações do primeiro funcionário usamos o nome do objeto (obj.funcionários) seguido da posição (como queremos a primeira posição, usamos o índice 0) e, por fim, adicionamos qual propriedade queremos: nome e idade.

# **AJAX**

[![](https://ampli-images.s3.amazonaws.com/production/5a48c594-06a7-4a90-8da0-c70987c24634/original)](https://ampli-images.s3.amazonaws.com/production/5a48c594-06a7-4a90-8da0-c70987c24634/original)

AJAX (_Asynchronous JavaScript And XML_ ou, na tradução, _Javascript_ Assíncrono e XML) corresponde ao conjunto de técnicas para realização de requisições assíncronas. Quando uma página dinâmica é processada em um servidor, o navegador faz uma requisição única. Para obter ou enviar dados, tecnicamente é necessário recarregar a página e fazer outra requisição. A ideia do AJAX é que as requisições sejam feitas de forma assíncrona, ou seja, não é necessário recarregar todos os componentes da página.

Por exemplo, há alguns anos muitos sites apresentavam um botão “salvar” para gravar dados de formulários. Você pode verificar que, ao clicar nesse botão, é feito o envio dos dados para o servidor, e a página inteira é recarregada. O problema é que, ao recarregar a página, diversas informações desnecessárias eram transferidas, como a estrutura do cabeçalho, menus, _divs_, imagens e estilos (vamos desconsiderar, por enquanto, que navegadores têm estruturas de cache que podem salvar parte desses componentes). Todas essas informações não alterarão ao clicar o botão salvar. No máximo, o servidor retornará as mesmas informações que você enviou, além de uma mensagem como “dados gravados com sucesso”.

> AJAX permite que apenas parte dos dados sejam enviados para o servidor, sem a necessidade de recarregar toda a página. Com isso, o tempo para envio dos dados será menor, além da redução do fluxo de dados na rede.

AJAX utiliza _JavaScript_ para fazer requisições assíncronas ao servidor remoto por meio da API XMLHttpRequest. É bastante usado com PHP, mas pode ser usado com outras linguagens _back-end_, como _Python_ e Java.

# **Canvas**

[![](https://ampli-images.s3.amazonaws.com/production/fd124d68-b187-466d-b64d-173e7fb5b62d/original)](https://ampli-images.s3.amazonaws.com/production/fd124d68-b187-466d-b64d-173e7fb5b62d/original)

O Canvas é um elemento do HTML5 utilizado para desenhar com o auxílio da linguagem de _script_, e a _JavaScript_ é uma linguagem muito utilizada. Com Canvas, é possível realizar desenhos de gráficos em tempo de execução, além de composição de imagens e animações em uma página web.

A _tag_ <canvas> tem a capacidade de realizar a renderização de imagens em bitmap (bmp) e é compatível com as folhas de estilo CSS.

Para a criação de Canvas deve-se especificar três parâmetros: o ID, a largura (_width_) e a altura (_height_) do elemento a ser desenhado, conforme pode ser visto no exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/b5d8bd9b-131e-4c71-a004-5447a4fde42c/original)](https://ampli-images.s3.amazonaws.com/production/b5d8bd9b-131e-4c71-a004-5447a4fde42c/original)

Importa destacar que, ao desenhar utilizando o elemento <canvas>, deve-se realizar o desenho todo no arquivo _JavaScript_.

Em um arquivo texto, você pode digitar o seguinte código:

[![](https://ampli-images.s3.amazonaws.com/production/e08d1fa5-f4ab-4b92-a937-6ed9b52fc6cb/original)](https://ampli-images.s3.amazonaws.com/production/e08d1fa5-f4ab-4b92-a937-6ed9b52fc6cb/original)

Teste Canvas. Fonte: elaborado pelo autor.

O trecho em JavaScript utiliza o ID para encontrar o elemento Canvas que foi definido na página: var c=document.get_ElementBy_Id("**testecanvas**");.

Na sequência, em var ctx=c._getContext_("2d"); é criado um objeto em contexto.

Será desenhado em um contexto de desenho 2D; logo, o objeto _getContext_("2d") é um objeto interno HTML5. Esse objeto apresenta muitos métodos para desenhar imagens, caixas e círculos, entre outros.

Em ctx._fillStyle="blue_"; é definida a cor azul, e ctx._fillRect_(0,0,200,400); desenha a forma retangular.

Nesse sentido, o atributo _fillStyle_ definiu a cor azul, e o atributo _fillRect_ definiu a posição, o tamanho e a forma geométrica.

Para melhor entendimento do Canvas, é necessário conhecer coordenadas para facilitar a criação dos _scripts_ para o desenho.

# **Geolocalização com JavaScript**

[![](https://ampli-images.s3.amazonaws.com/production/34c69417-87cd-4f99-b3f4-601575d923db/original)](https://ampli-images.s3.amazonaws.com/production/34c69417-87cd-4f99-b3f4-601575d923db/original)

Um exemplo de função que pode ser feita usando JS é a coleta de geolocalização. Geolocalização corresponde à detecção de sua posição geográfica com base no sistema global de linhas imaginárias horizontais e verticais que dividem a superfície da Terra. Latitude corresponde às linhas horizontais, e longitude, às verticais (ENCYCLOPEDIA BRITANNICA, 2020).

Esse posicionamento pode ser obtido de várias formas, com o seu endereço de IP usado para conectar-se à internet, com a triangulação das antenas de telecomunicação ou, ainda, com os dados específicos dos dispositivos GPS (Sistema de Posicionamento Global, ou, em inglês, _Global Positioning System_). De fato, nos dias de hoje tornou-se trivial a utilização de métodos de obtenção de localização do dispositivo de acesso, e tal posicionamento pode ser explorado por scripts construídos com _JavaScript_.

Navegadores modernos apresentam suporte à API de geolocalização. A obtenção do posicionamento pode ser feita através da propriedade global _navigator_ e do objeto _geolocation_.

[![](https://ampli-images.s3.amazonaws.com/production/ef221f53-a1ff-440f-bcd4-695154fede93/original)](https://ampli-images.s3.amazonaws.com/production/ef221f53-a1ff-440f-bcd4-695154fede93/original)

API de geolocalização – navigator.geolocation. Fonte: elaborado pelo autor.

Observe que na linha 4 foi necessário verificar se a variável existe. Isso porque muitos navegadores ainda não oferecem suporte à API de geolocalização. Ao abrir essa página no navegador, se houver suporte será exibida uma caixa de diálogo questionando se você autoriza a divulgação de sua geolocalização. Esse procedimento garante que sua localização seja utilizada apenas quando previamente autorizado.

[![](https://ampli-images.s3.amazonaws.com/production/eab9dbcf-6656-438d-adb1-6c783f1f9cdd/original)](https://ampli-images.s3.amazonaws.com/production/eab9dbcf-6656-438d-adb1-6c783f1f9cdd/original)

Geolocalização. Fonte: captura de tela de DOM elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/1502dff9-7177-4856-8ac5-e272ea37746c/original)](https://ampli-images.s3.amazonaws.com/production/1502dff9-7177-4856-8ac5-e272ea37746c/original)

Após a obtenção da geolocalização ser autorizada, pode-se observar o objeto navigator.geolocation que será impresso na linha 7:

Inspecionando a geolocalização. Fonte: captura de tela de DOM elaborada pelo autor.

Nesse objeto podemos verificar várias informações, como a acurácia, que indica o quão precisa é a posição apresentada (no exemplo, a acurácia é de 10.182 metros), além da latitude e longitude. Vários campos não puderam ser definidos devido a restrições do navegador.

A seguir, serão utilizadas as variáveis declaradas anteriormente para coletar as posições de latitude e longitude (linhas 9 a 12).

[![](https://ampli-images.s3.amazonaws.com/production/17a16cfb-df81-4bb4-a18f-ccd1d23420f7/original)](https://ampli-images.s3.amazonaws.com/production/17a16cfb-df81-4bb4-a18f-ccd1d23420f7/original)

Propriedades do objeto coord. Fonte: adaptado de Pilgrim (2010).

Você pode copiar as posições de latitude e longitude e usar uma ferramenta de mapas para visualizar, como o Google _Maps_, conforme ilustrado na figura abaixo:

[![](https://ampli-images.s3.amazonaws.com/production/4ee4ec72-e534-43fc-8009-a52a23f69184/original)](https://ampli-images.s3.amazonaws.com/production/4ee4ec72-e534-43fc-8009-a52a23f69184/original)

Coordenadas: -19.87, -43.95. Fonte: captura de tela do Google Maps elaborada pelo autor.

Nesse exemplo foram utilizadas apenas duas casas decimais (para facilitar a visualização).

O Google _Maps_ permite ainda o uso de uma API para inclusão de mapas em sites usando _JavaScript_. Entretanto, essa API requer uma chave.

Para ilustrar a exibição de mapas, vamos utilizar uma ferramenta gratuita: o _OpenLayers_. Anteriormente, já apresentamos como executá-la. Relembre:

[![](https://ampli-images.s3.amazonaws.com/production/5801f5e7-1245-4abe-9ea6-a92ab440fc26/original)](https://ampli-images.s3.amazonaws.com/production/5801f5e7-1245-4abe-9ea6-a92ab440fc26/original)

[![](https://ampli-images.s3.amazonaws.com/production/1884075e-e443-41d3-bdcd-445c62868d46/original)](https://ampli-images.s3.amazonaws.com/production/1884075e-e443-41d3-bdcd-445c62868d46/original)

[![](https://ampli-images.s3.amazonaws.com/production/0c263882-c67d-49a4-b490-f3440a0a5c86/original)](https://ampli-images.s3.amazonaws.com/production/0c263882-c67d-49a4-b490-f3440a0a5c86/original)

Para o exemplo a seguir, obtivemos dados da documentação oficial, disponível no site da biblioteca (OPENLAYERS, [s.d.]).

Como está sendo utilizada uma biblioteca JS, não é necessário “decorar” todos os códigos, uma vez que alguns comandos são bastante específicos para essa biblioteca. Você pode adaptar códigos disponíveis na documentação para seus problemas específicos. O importante é compreender os fundamentos e alguns comandos utilizados.

[![](https://ampli-images.s3.amazonaws.com/production/b99bb56d-4c66-4f02-a512-223f7f531708/original)](https://ampli-images.s3.amazonaws.com/production/b99bb56d-4c66-4f02-a512-223f7f531708/original)

[![](https://ampli-images.s3.amazonaws.com/production/fe37e749-c746-4cf0-afdd-1955884177b5/original)](https://ampli-images.s3.amazonaws.com/production/fe37e749-c746-4cf0-afdd-1955884177b5/original)

No arquivo index.html mostrado na figura acima foi necessário adicionar os dois _scripts_ do _OpenLayers_, inserir a div (que deverá ter id=“_map_”) e inserir o _script_ particular no final do arquivo.

[![](https://ampli-images.s3.amazonaws.com/production/5b9f592d-8a26-4fdf-8042-c1af5c7aec76/original)](https://ampli-images.s3.amazonaws.com/production/5b9f592d-8a26-4fdf-8042-c1af5c7aec76/original)

estilo.css. Fonte: elaborado pelo autor.

Na figura acima, o estilo apenas definiu a altura da div que receberá o mapa (no exemplo, 400px) e a largura total (100%).

[![](https://ampli-images.s3.amazonaws.com/production/3b4850e1-39ab-4319-8be7-af1b8edfaf53/original)](https://ampli-images.s3.amazonaws.com/production/3b4850e1-39ab-4319-8be7-af1b8edfaf53/original)

[![](https://ampli-images.s3.amazonaws.com/production/06678cfb-e09a-4251-8085-e7ce0f16ef6f/original)](https://ampli-images.s3.amazonaws.com/production/06678cfb-e09a-4251-8085-e7ce0f16ef6f/original)

script.js – Função gerar mapa. Fonte: elaborado pelo autor.

No _script_ foi criada uma nova função denominada geraMapa(). A análise dela é realizada a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/6ca8840f-9787-49e3-9fd4-2c4490ec3db5/original)](https://ampli-images.s3.amazonaws.com/production/6ca8840f-9787-49e3-9fd4-2c4490ec3db5/original)

Nessa linha foi declarada uma variável denominada _map_ que recebe um novo objeto ol._Map_. No trecho a seguir, temos algumas propriedades desse objeto, como o alvo (_target_) e as camadas (_layers_), que receberão um novo objeto do tipo ol._layer.Tile_:

[![](https://ampli-images.s3.amazonaws.com/production/be1a0edd-5fc0-4874-b3d6-32909a51d0fc/original)](https://ampli-images.s3.amazonaws.com/production/be1a0edd-5fc0-4874-b3d6-32909a51d0fc/original)

Por fim, no trecho a seguir é apresentado um objeto do tipo ol._View_ que definirá propriedades de como o mapa será visualizado e o nível de zoom desejado:

[![](https://ampli-images.s3.amazonaws.com/production/be290ef1-1ca5-4226-933f-a9dc23a429ff/original)](https://ampli-images.s3.amazonaws.com/production/be290ef1-1ca5-4226-933f-a9dc23a429ff/original)

Os códigos dentro dessa função foram coletados diretamente da documentação oficial. De fato, a única linha modificada foi a linha em que definimos as posições da latitude e longitude:

[![](https://ampli-images.s3.amazonaws.com/production/89e1c39b-b9de-4da3-b531-580109a3d411/original)](https://ampli-images.s3.amazonaws.com/production/89e1c39b-b9de-4da3-b531-580109a3d411/original)

Nesse caso, foram inseridos os nomes das variáveis que criamos anteriormente para receber a localização atual. A figura abaixo ilustra o resultado do mapa.

[![](https://ampli-images.s3.amazonaws.com/production/88332e48-84e6-4425-b84b-17580d71b9a9/original)](https://ampli-images.s3.amazonaws.com/production/88332e48-84e6-4425-b84b-17580d71b9a9/original)

Exemplo de mapa. Fonte: captura de tela de DOM elaborada pelo autor.

# **Controlando vídeos com HTML5 e JavaScript**

[![](https://ampli-images.s3.amazonaws.com/production/d5e223a8-7377-447b-8288-7ddb9d7b91ba/original)](https://ampli-images.s3.amazonaws.com/production/d5e223a8-7377-447b-8288-7ddb9d7b91ba/original)

No exemplo a seguir, você poderá controlar a reprodução de um vídeo em HTML5 usando _JavaScript_. Para isso, vamos construir uma página HTML que exibirá um vídeo em tela cheia. Por fim, você pode construir um botão que iniciará o vídeo. Ao ser iniciado, o texto no botão será alterado para **Pausa**r. Ao pausar o vídeo, o texto do botão deverá ser substituído por **Continuar**.

A figura abaixo ilustra a página resultante:

[![](https://ampli-images.s3.amazonaws.com/production/00f282fc-ee3d-4509-9efc-4693bc71c87f/original)](https://ampli-images.s3.amazonaws.com/production/00f282fc-ee3d-4509-9efc-4693bc71c87f/original)

Vídeos. Fonte: captura de tela elaborada pelo autor.

Vamos começar configurando o arquivo “_script._js”:

[![](https://ampli-images.s3.amazonaws.com/production/03c2e194-8bb1-4128-a91e-2406508e2614/original)](https://ampli-images.s3.amazonaws.com/production/03c2e194-8bb1-4128-a91e-2406508e2614/original)

script.js – Função controlarVideo( ). Fonte: elaborado pelo autor.

Nesse arquivo foi construída uma função denominada controlarVideo( ). Ao executar essa função, dois objetos são criados: video e btn. O primeiro deles consulta a árvore DOM pelo elemento de ID meuVideo (usaremos esse ID para o vídeo inserido na página). O segundo objeto (btn) receberá o botão usado para iniciar e pausar o vídeo.

O objeto de vídeo apresenta dois métodos:

- _pause_( ) : interrompe a execução do vídeo.
- _play_( ) : executa o vídeo.

Observe que o comando condicional verifica se o objeto video._paused_ é verdadeiro ou falso (ele contém a informação se o vídeo está executando no momento ou não). Para alterar o texto no botão, atribuímos um novo valor à propriedade btn._inner_HTML.

Agora você pode construir a página HTML. Aqui será utilizado um vídeo genérico no formato MP4 denominado “a.mp4”. O botão deverá ativar a função controlarVideo( ) ao ser clicado (evento _onclick_). Observe o código resultante a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/af5ba43e-e73a-49e9-bba0-193482a6ebdc/original)](https://ampli-images.s3.amazonaws.com/production/af5ba43e-e73a-49e9-bba0-193482a6ebdc/original)

[![](https://ampli-images.s3.amazonaws.com/production/1ef8935a-7d77-4d47-8735-45c02e4bc9cd/original)](https://ampli-images.s3.amazonaws.com/production/1ef8935a-7d77-4d47-8735-45c02e4bc9cd/original)

Manipulação de vídeos com HTML5 e JavaScript. Fonte: elaborado pelo autor.

Por fim, você pode aplicar os estilos usados nessa página:

[![](https://ampli-images.s3.amazonaws.com/production/14f2afb0-6ede-4371-9960-e5f5b22b3069/original)](https://ampli-images.s3.amazonaws.com/production/14f2afb0-6ede-4371-9960-e5f5b22b3069/original)

[![](https://ampli-images.s3.amazonaws.com/production/bfd7a481-e170-43c3-876c-07f0b150d2dc/original)](https://ampli-images.s3.amazonaws.com/production/bfd7a481-e170-43c3-876c-07f0b150d2dc/original)

[![](https://ampli-images.s3.amazonaws.com/production/e6fa7ddd-e738-4607-bebc-7a3d3d0b6879/original)](https://ampli-images.s3.amazonaws.com/production/e6fa7ddd-e738-4607-bebc-7a3d3d0b6879/original)

estilo.css. Fonte: elaborado pelo autor.

Nesta aula, você pôde se aprofundar na linguagem _JavaScript_. Você estudou como navegar pelo DOM e quais são os eventos disponíveis. Ainda aprendeu alguns fundamentos do uso de bibliotecas, que são utilizadas, por exemplo, para geolocalização. Agora você pode aplicar os seus conhecimentos criando aplicações que utilizem as bibliotecas apresentadas. Vamos lá?

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

Para ampliar sua visão acerca das possibilidades de aplicação dos conhecimentos obtidos até o momento, vamos propor uma resolução para a situação-problema apresentada no início desta aula. Sua incumbência foi incluir uma localização transparente em um website para o caso de algum cliente da empresa quiser visitá-la. Você deverá construir um mapa interativo para exibir essa localização. Além disso, deverá adicionar o mapa interativo à página criada anteriormente.

O resultado é apresentado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/e9b43264-4280-4521-bb72-6e9e98451c61/original)](https://ampli-images.s3.amazonaws.com/production/e9b43264-4280-4521-bb72-6e9e98451c61/original)

Resultado da seção “Onde estamos?”. Fonte: captura de tela elaborada pelo autor.

A seguir é apresentado o código-fonte da solução:

[![](https://ampli-images.s3.amazonaws.com/production/dd3c51fa-d50b-4974-9e47-0808448988f7/original)](https://ampli-images.s3.amazonaws.com/production/dd3c51fa-d50b-4974-9e47-0808448988f7/original)

[![](https://ampli-images.s3.amazonaws.com/production/97e9b7a2-b237-4d25-bf1a-cf852d09d10a/original)](https://ampli-images.s3.amazonaws.com/production/97e9b7a2-b237-4d25-bf1a-cf852d09d10a/original)

[![](https://ampli-images.s3.amazonaws.com/production/186dadaf-5a73-4a03-8e02-d0736f2ff442/original)](https://ampli-images.s3.amazonaws.com/production/186dadaf-5a73-4a03-8e02-d0736f2ff442/original)

Observe que criamos a função geraMapa, e foram incluídas as seguintes coordenadas:

[![](https://ampli-images.s3.amazonaws.com/production/c0694ea7-2aa3-4bba-a8b7-68912e1eeaa0/original)](https://ampli-images.s3.amazonaws.com/production/c0694ea7-2aa3-4bba-a8b7-68912e1eeaa0/original)