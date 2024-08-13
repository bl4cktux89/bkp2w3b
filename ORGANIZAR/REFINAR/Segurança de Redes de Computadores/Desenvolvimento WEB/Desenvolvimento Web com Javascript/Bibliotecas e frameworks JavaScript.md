# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/3a6b9e93-a260-41f4-b8df-6f90ab96878c/original)](https://ampli-images.s3.amazonaws.com/production/3a6b9e93-a260-41f4-b8df-6f90ab96878c/original)

### **Qual é o foco da aula?**

Nesta aula, irá conhecer bibliotecas e _frameworks JavaScript_ e _jQuery_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- examinar como calcular com _JavaScript_;
- interpretar a biblioteca _jQuery_;
- apontar as diferenças entre Bibliotecas e _frameworks_ .

**Situação-problema**

Olá, estudante! Você já pensou se uma empresa automobilística precisasse inventar um novo modelo de roda para cada carro desenvolvido? E se um cozinheiro precisasse redescobrir como fazer fogo antes de preparar cada refeição? O processo de produção de um carro (ou de preparação de um jantar) demoraria muito mais tempo. Considere que você deseja acender o fogão. Você pode saber como fazer isso friccionando duas pedras até que uma faísca acenda, mas seria mais eficaz usar um fósforo. Esses exemplos podem parecer absurdos, mas no desenvolvimento de websites podemos fazer uma analogia parecida. Digamos que temos uma lista com cinco elementos:

40, 123, 12, 84, 0

Qual o maior elemento dessa lista? Obviamente, 123!

Mas pense em como calcular isso com _JavaScript_. Uma maneira de descobrir qual o maior na lista é analisar um a um usando um laço de repetição e verificar, a cada rodada, qual o maior número atual. Para isso, é necessária uma variável auxiliar para armazenar o maior valor. Agora, observe o trecho de código a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/705f2ef9-99d0-4dbf-8601-09ee9ba4d182/original)](https://ampli-images.s3.amazonaws.com/production/705f2ef9-99d0-4dbf-8601-09ee9ba4d182/original)

Maior valor em uma lista. Fonte: elaborado pelo autor.

Achar o maior número de uma lista é uma tarefa muito simples, mesmo assim foram utilizadas oito linhas. O _JavaScript_ contém uma função para isso na biblioteca nativa:

[![](https://ampli-images.s3.amazonaws.com/production/b9d3e6b0-90e0-4550-a259-e5be9401aab7/original)](https://ampli-images.s3.amazonaws.com/production/b9d3e6b0-90e0-4550-a259-e5be9401aab7/original)

Ao observarmos de forma minuciosa, _Math_ é, na verdade, um objeto embutido com métodos próprios, mas que ilustra bem o conceito de uma biblioteca. Analisar o maior ou o menor número de uma lista é uma tarefa trivial, ou seja, podem existir muitas formas de se fazer, mas isso já está bem estabelecido e não precisamos gastar muitas linhas de código. Uma função já havia sido construída anteriormente; logo, basta chamá-la e assim teremos o maior valor da lista.

Por isso, bibliotecas e _frameworks_ são tão importantes. Eles fornecem soluções que aceleram o desenvolvimento do código, permitindo que os programadores foquem o que realmente importa: construir aplicações mais robustas.

Bibliotecas e _frameworks_ são conjuntos de códigos desenvolvidos por terceiros que facilitam o desenvolvimento de aplicações web. Apesar de existirem tênues diferenças entre esses conceitos, muitas vezes eles têm sido utilizados no mesmo contexto, como no caso do jQuery, que algumas vezes é chamado de biblioteca, e outras, de _framework_.

> Na prática, uma biblioteca é um conjunto de métodos e propriedades predefinidas que pode auxiliar no desenvolvimento de código. Já um framework pode agrupar uma série de bibliotecas ou ainda delimitar a forma como o programador deverá construir o código.

Diferentes bibliotecas e _frameworks_ podem ter diversos objetivos. Por exemplo, _jQuery_ é uma biblioteca construída para simplificar a forma como programamos em _JavaScript_. Já o D3.js é uma biblioteca construída especialmente para construção de gráficos e outros tipos de visualização de dados. Assim, não há empecilho em usar as duas bibliotecas em um mesmo projeto de site.

Usar _frameworks_ e bibliotecas têm muitas vantagens; entre elas, aperfeiçoar a codificação reduzindo o tempo gasto na construção de métodos triviais ou, ainda, no caso dos _frameworks_, criar uma padronização de como os códigos deverão ser construídos. Uma desvantagem é que à medida que o número de bibliotecas usadas em um mesmo site aumenta, o carregamento pode se tornar lento, uma vez que incluirá muitas funções que talvez não sejam usadas pelo programador. Além disso, pode-se ter conflitos relacionados a nomes de funções – mas há uma série de boas práticas para lidar com isso.

A fim de colocarmos em prática os conhecimentos a serem obtidos, vamos analisar a seguinte situação-problema: você foi contratado para criar uma página de planos de um site. Observe que a empresa apresenta quatro valores possíveis de planos. Precisamos implementar um formulário que envie o contato do cliente e qual plano será assinado quando ele clica em “Assine já!”, na seção de planos mostrada na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/1a914368-f485-4465-953e-2dd91175c07a/original)](https://ampli-images.s3.amazonaws.com/production/1a914368-f485-4465-953e-2dd91175c07a/original)

Seção de planos. Fonte: elaborado pelo autor.

Para isso, foi solicitado que você utilize a estrutura de um modal _Bootstrap_ (um componente que usa animações CSS e _JavaScript_, além do efeito _lightbox_ para melhorar a interface de uma caixa de diálogo). Entretanto, você deverá construir um código que utilize um único modal, que deverá receber interativamente o plano escolhido com base na opção escolhida pelo usuário.

Para isso, será preciso implementar essa caixa de diálogo interativa, seguindo as seguintes regras:

1. O modal de assinatura deve ter um formulário que exija nome, telefone, endereço, cidade, estado e CEP.
2. Ao final do formulário deve haver um _checkbox_ com a mensagem “Concordo com os termos de uso” (não se preocupe com os termos de uso, eles serão escritos pelo departamento jurídico da empresa, portanto apenas insira a mensagem).
3. O formulário deve ter um campo PLANO, que deve exibir **apenas** o plano referente ao botão clicado na página principal (exemplo, se o usuário clicou no botão “Assine já!” do Plano Alfa, o formulário exibirá apenas o Plano Alfa e o valor).
4. O formulário deve ter dois botões: cancelar e assinar. O botão “assinar” deve ficar desabilitado por padrão. Ele só será habilitado quando o usuário clicar no _checkbox_ dos termos de uso. Uma vez aceitos os termos de uso, o _checkbox_ deverá ser desabilitado (ou seja, não será possível mais remover a checagem).

**Opcional**: inclua os estados brasileiros em um campo do tipo _select_. Você pode obter uma lista (_select_) dos estados brasileiros em _GitHub_ (c2021).

Observe qual é a versão do _Bootstrap_ utilizada, pois classes podem receber novos nomes. Você pode usar _jQuery_ combinado às classes do _Bootstrap_ para alterar os atributos referentes aos campos selecionados. Por exemplo, o atributo _disabled_ impede que um campo seja clicado (ele é bloqueado).

Diante disso, nesta seção, abordaremos alguns exemplos de bibliotecas _JavaScrip_t, além de apresentar exemplos práticos usando _jQuery_, a mais popular biblioteca/_framework JavaScript_. Vamos lá?

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/14ca32da-0a59-4dbc-8c2e-3dcd7ad92f70/original)](https://ampli-images.s3.amazonaws.com/production/14ca32da-0a59-4dbc-8c2e-3dcd7ad92f70/original)

Nos últimos anos, uma ampla gama de _frameworks JavaScript_ tem sido disponibilizada na internet. Isso traz vantagens, pois dá ao desenvolvedor muitas opções na hora de desenvolver a sua aplicação, porém pode tornar difícil a escolha do framework e a decisão de qual biblioteca utilizar.

Anteriormente citamos um _framework JavaScript_, o _Bootstrap_. Na figura abaixa, podemos ver uma lista de bibliotecas e _frameworks_ populares em _JavaScript_.

[![](https://ampli-images.s3.amazonaws.com/production/b9699ae4-da5e-4e77-bb15-9056303d546f/original)](https://ampli-images.s3.amazonaws.com/production/b9699ae4-da5e-4e77-bb15-9056303d546f/original)

[![](https://ampli-images.s3.amazonaws.com/production/f8995a65-9f5e-42cb-830f-d71c480c0e02/original)](https://ampli-images.s3.amazonaws.com/production/f8995a65-9f5e-42cb-830f-d71c480c0e02/original)

Perceba que cada framework apresenta uma principal motivação. De fato, o que elas têm em comum é o fato de utilizarem uma sintaxe parecida ao _JavaScript_ (usando os padrões do _ECMAScript_). Entretanto, detalhes de como implementar códigos usando cada um desses _frameworks_ devem ser explorados na documentação descrita nos seus respectivos sites. Como dissemos, seria impossível explorar cada um desses _frameworks_; portanto, escolhemos a biblioteca _jQuery_ para ilustrar a seção. Entretanto, recomendamos a você, estudante, que pesquise a fundo as novas bibliotecas/_frameworks JavaScript_, em especial aquelas com foco em arquitetura _single-page_, que podem ser a próxima tendência no desenvolvimento web.

______

**➕ Pesquise mais**

Conheça as 24 bibliotecas _JavaScript_ gratuitas mais populares no ano de 2020, de acordo com o site Colorlib (IVANOVS, 2020).

# **JQUERY**

[![](https://ampli-images.s3.amazonaws.com/production/484b9383-7e32-43f5-9fa4-852d1153feab/original)](https://ampli-images.s3.amazonaws.com/production/484b9383-7e32-43f5-9fa4-852d1153feab/original)

_jQuery_ é uma biblioteca _JavaScript_ simplificada e rica em recursos. Ela permite o desenvolvimento e manipulação de documentos HTML, tratamento de eventos, construção de animações e manipulação de _JavaScript_ de forma assíncrona (AJAX) de uma maneira simples e compatível com diversos navegadores. _jQuery_ pode ser obtido no site da biblioteca (JQUERY, c2021).

### **Início rápido**

Para começar a desenvolver seus primeiros códigos em jQuery, inclua a seguinte linha de código:

[![](https://ampli-images.s3.amazonaws.com/production/13ebb147-fa65-4c8b-84f6-e0c62df94be2/original)](https://ampli-images.s3.amazonaws.com/production/13ebb147-fa65-4c8b-84f6-e0c62df94be2/original)

Esse código carrega a biblioteca _jQuery_ diretamente da CDN (_Content Delivery Network_ ou, na tradução, Rede de Fornecimento de Conteúdo). Entretanto, é recomendado que seja realizado o _download_ do arquivo “_jquery_-[versão].min.js” e que seja salvo no diretório local de sua aplicação. Para testar, abra o _link_ do _script_ no navegador, clique com o botão direito e vá em “salvar como”.

### **Instalação opcional**

Opcionalmente, _jQuery_ pode ser instalado pelo npm usando o seguinte código:

npm install jquery

### **JavaScript versus jQuery**

A principal ideia por trás do _jQuery_ é reduzir a quantidade de código necessário em _JavaScript_ para realizar uma mesma tarefa. Observe, a seguir, um código simples que insere e grava uma mensagem dentro do elemento de ID “conteudo”:

[![](https://ampli-images.s3.amazonaws.com/production/3057106c-0348-4d36-888d-528d0f807204/original)](https://ampli-images.s3.amazonaws.com/production/3057106c-0348-4d36-888d-528d0f807204/original)

Inserindo e gravando uma mensagem. Fonte: elaborado pelo autor.

Esse código gerará a seguinte página:

[![](https://ampli-images.s3.amazonaws.com/production/84ede48c-2ca7-4dce-b92b-1a23aa8b3078/original)](https://ampli-images.s3.amazonaws.com/production/84ede48c-2ca7-4dce-b92b-1a23aa8b3078/original)

“Olá mundo!”. Fonte: elaborado pelo autor.

Perceba que o _jQuery_ foi carregado na linha 13. Ele deve ser declarado antes dos códigos usando a sintaxe _jQuery_, como o código presente na linha 15.

Observe como um código similar seria realizado usando _JavaScript_ quando comparado com a versão em _jQuery_:

[![](https://ampli-images.s3.amazonaws.com/production/fea5a536-cbce-486b-a960-04988b8d4d2a/original)](https://ampli-images.s3.amazonaws.com/production/fea5a536-cbce-486b-a960-04988b8d4d2a/original)

Um seletor precedido por # indica a busca por um ID. Se for precedido por um ponto, será uma classe. Caso desejemos usar uma _tag_, basta colocar o seu nome:

[![](https://ampli-images.s3.amazonaws.com/production/7b2c0f66-b33e-4594-a70b-947962036eac/original)](https://ampli-images.s3.amazonaws.com/production/7b2c0f66-b33e-4594-a70b-947962036eac/original)

No exemplo apresentado, _jQuery_ é usado para buscar o elemento contido pela _tag_ <_body_> na linha 1, todos os elementos com a classe minhaClasse na linha 2 e o elemento de id meuID na linha 3.

______

🔁 **Assimile**

Seletores avançados

Até o momento abordamos apenas seletores simples, como nome da tag, ID e classe. Entretanto, existem seletores que permitem buscas mais eficientes, como selecionar elementos pai e filho, ou elementos que apresentam determinado atributo. Como poderíamos selecionar um elemento que apresenta o atributo abaixo e alterar a sua cor de fundo para vermelho?:

[![](https://ampli-images.s3.amazonaws.com/production/ec064f9c-8e65-4b7c-a670-ae0b77c68a5d/original)](https://ampli-images.s3.amazonaws.com/production/ec064f9c-8e65-4b7c-a670-ae0b77c68a5d/original)

Confira a lista de seletores no site _jQuery_ (c2021b).

### **Verificando se o documento está “pronto**

Caso você utilize um comando _jQuery_ antes do carregamento da biblioteca, você obterá a seguinte mensagem:

_Uncaught ReferenceError:_ _$ is not defined_

Essa frase poderia ser traduzida como “erro de referência não detectado: $ não está definido”. Isso ocorre porque o navegador não consegue reconhecer comandos iniciados com $ nativamente. Apenas quando a biblioteca _jQuery_ é completamente iniciada, esse comando passará a ser reconhecido. Importa destacar que é recomendado que o _script jQuery_ seja declarado dentro da _tag_ <_head_>.

Além disso, antes de executar qualquer script com _jQuery_ é importante verificar se o documento está “pronto”, isto é, se todo o conteúdo foi corretamente carregado. Foi realizado algo similar usando JavaScript puro, quando usamos a função que verificava se a página já havia sido carregada.

Há duas formas de se fazer isso. A primeira envolve uma declaração completa:

[![](https://ampli-images.s3.amazonaws.com/production/c1b151c8-4b8a-4222-806b-027ba4ba849f/original)](https://ampli-images.s3.amazonaws.com/production/c1b151c8-4b8a-4222-806b-027ba4ba849f/original)

Nos exemplos a seguir, usaremos sempre a versão reduzida.

# **Manipulação do CSS e de atributos com jQuery**

[![](https://ampli-images.s3.amazonaws.com/production/ae5e6f37-7746-4114-be3f-484ea7103db7/original)](https://ampli-images.s3.amazonaws.com/production/ae5e6f37-7746-4114-be3f-484ea7103db7/original)

Navegar pelo DOM e alterar propriedades CSS usando _JavaScript_ puro pode requerer que você digite uma grande quantidade de código. A biblioteca _jQuery_ fornece soluções para facilitar isso. Você pode facilmente alterar estilos e atributos de elementos HTML usando os métodos do _jQuery_:

[![](https://ampli-images.s3.amazonaws.com/production/1a1d5aec-ee72-4ace-9a3d-bfc1a4342081/original)](https://ampli-images.s3.amazonaws.com/production/1a1d5aec-ee72-4ace-9a3d-bfc1a4342081/original)

[![](https://ampli-images.s3.amazonaws.com/production/3f4716e5-b01e-4bbf-a8cd-45eb1ebe02f0/original)](https://ampli-images.s3.amazonaws.com/production/3f4716e5-b01e-4bbf-a8cd-45eb1ebe02f0/original)

[![](https://ampli-images.s3.amazonaws.com/production/8678eb8a-aeca-45ad-9d52-11192f95a9e3/original)](https://ampli-images.s3.amazonaws.com/production/8678eb8a-aeca-45ad-9d52-11192f95a9e3/original)

Classes do jQuery usadas para manipulação do CSS. Fonte: adaptado de jQuery (c2021c).

Suponhamos que você deseja usar o _jQuery_ para alterar a cor de fundo de uma página.

[![](https://ampli-images.s3.amazonaws.com/production/95e5de0b-aa37-4669-b74a-65301ae14d6e/original)](https://ampli-images.s3.amazonaws.com/production/95e5de0b-aa37-4669-b74a-65301ae14d6e/original)

Observe que o método .css( ) requer dois parâmetros: a propriedade a ser alterada e o valor que a propriedade receberá. Nesse exemplo, a propriedade alterada foi _background-color_ (note que aqui você pode usar tanto _backgroundColor_ quanto _background-color_). O valor aplicado a essa propriedade foi _black_ (preto).

Podemos ainda alterar altura e largura de um elemento usando as propriedades _height_ e _width_, respectivamente. Observe a implementação a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/f852eb5a-ea83-471c-a704-c8fe6c3b8641/original)](https://ampli-images.s3.amazonaws.com/production/f852eb5a-ea83-471c-a704-c8fe6c3b8641/original)

Alteração da altura (height) e da largura (width). Fonte: elaborado pelo autor.

O código apresentado cria uma divisão div quadrada chamada caixa, que receberá a cor de fundo verde, uma altura de 400px e uma largura de 400px, além disso, a cor de fundo será alterada para preto:

[![](https://ampli-images.s3.amazonaws.com/production/57e4118a-f84c-407e-be98-8432a73346f9/original)](https://ampli-images.s3.amazonaws.com/production/57e4118a-f84c-407e-be98-8432a73346f9/original)

Utilização do CSS para alterar cores e tamanhos de elementos. Fonte: elaborado pelo autor.

Você pode observar o uso dos métodos de alteração de estilo na prática.

Vamos, a seguir, compreender como _jQuery_ trata eventos.

# **Eventos**

[![](https://ampli-images.s3.amazonaws.com/production/4ce2f1f1-3748-4129-a5af-904f5bb9edec/original)](https://ampli-images.s3.amazonaws.com/production/4ce2f1f1-3748-4129-a5af-904f5bb9edec/original)

_jQuery_ também fornece uma série de métodos para facilitar o uso de eventos _JavaScrip_t. Eventos englobam comportamentos relacionados à interação entre usuário e sistema. Na prática podem ser desde um clique do mouse em um determinado botão até quando uma determinada tecla é pressionada. O método _ready_( ), por exemplo, determina que uma função será executada quando o DOM for completamente carregado.

**Eventos de cursor**

Os eventos relacionados ao cursor em geral analisam o posicionamento indicado por um mouse ou _trackpad_. Em geral, esses eventos estão relacionados à movimentação ou clique do mouse sobre um determinado elemento. Confira a seguir alguns eventos relacionados ao cursor:

- ._click_(): ocorre quando se clica em algum elemento.
- ._hover_(): ocorre quando o mouse sobrepõe um elemento.
- ._mousedown_(): ocorre quando algum botão do mouse é pressionado sobre um determinado elemento.
- ._mouseenter_(): ocorre quando o cursor adentra o elemento.
- ._mouseleave_(): evento ativado quando o cursor deixa o elemento.
- ._mouseout_(): ativado quando o cursor não está sobre o determinado elemento.
- ._mouseover(_): evento ocorre quando o mouse está sobre o elemento.
- ._mouseup_(): ocorre quando algum botão do mouse, após ser pressionado, é liberado.

Muitos desses métodos funcionam de maneira similar, porém com pequenas diferenças relacionadas a seu uso. Para verificar, consulte MDN _Web Docs_ ([s.d.]).

**Eventos do teclado**

Esse tipo de evento é acionado quando o teclado é utilizado. No JavaScript temos como exemplo o evento _onkeypress_ (quando uma tecla é pressionada). jQuery também fornece maneiras de manipular eventos (FERREIRA, 2020). Há três principais métodos:

- ._keydown_(): ocorre **no exato momento** em que a tecla é pressionada.
- ._keypress_(): ocorre **enquanto** uma tecla é pressionada.
- ._keyup_(): ocorre **após** a tecla ser pressionada e voltar a sua posição original.

**Eventos de formulário**

Dos eventos relacionados a formulários, destacamos o responsável pela submissão: ._submit_().

Uma lista com todos os eventos pode ser consultada em _jQuery_ (c2021d).

______

**📝 Exemplificando**

Vamos ver na prática como os eventos podem ser utilizados em combinação com as propriedades de alteração do CSS. O código a seguir constrói uma página HTML como um simples botão e um quadrado vermelho logo a seguir. Vamos utilizar _jQuery_ para que identifique um evento de clique no botão e altere a cor do quadrado para azul:

[![](https://ampli-images.s3.amazonaws.com/production/240bb76d-682c-424f-97bf-0325f5ddfab2/original)](https://ampli-images.s3.amazonaws.com/production/240bb76d-682c-424f-97bf-0325f5ddfab2/original)

[![](https://ampli-images.s3.amazonaws.com/production/b6252d95-aa14-40eb-984c-0e7a9efe037d/original)](https://ampli-images.s3.amazonaws.com/production/b6252d95-aa14-40eb-984c-0e7a9efe037d/original)

Identificação de um evento de clique e alteração da cor em jQuery . Fonte: elaborado pelo autor.

Agora observe na prática o que ocorre ao clicar no botão “Clique aqui”:

[![](https://ampli-images.s3.amazonaws.com/production/e557c9ca-c700-40b2-bb32-82f3edc0324c/original)](https://ampli-images.s3.amazonaws.com/production/e557c9ca-c700-40b2-bb32-82f3edc0324c/original)

Entendendo eventos jQuery. Fonte: elaborado pelo autor.

Note o elemento analisado (\#botao) recebe o método relacionado ao evento de clique. Assim, dentro da função criada, é adicionado o comando que fará a modificação em \#caixa.

Perceba que a forma como os parênteses e chaves são adicionados às vezes pode gerar dúvidas. Para tentar melhorar isso, no código a seguir vamos colorir da mesma cor cada elemento relacionado:

[![](https://ampli-images.s3.amazonaws.com/production/432d0a82-8e9e-4477-9a7c-9e5e76650980/original)](https://ampli-images.s3.amazonaws.com/production/432d0a82-8e9e-4477-9a7c-9e5e76650980/original)

Função SELETOR com evento de clique. Fonte: elaborado pelo autor.

Por exemplo, note que a função declarada na linha 2 é fechada na linha 8. Enquanto isso, a função aberta na linha 4 é fechada na linha 6. Observe que o encerramento de parênteses deve ser procedido de ponto e vírgula, mas o fechamento de chaves não. Veja, ainda, que a quebra de linhas dentro de parênteses não interfere na execução do código.

Vamos investigar mais os eventos relacionados ao mouse. Primeiro, vamos adicionar um código que altere a cor da caixa para verde quando o mouse estiver sobre ela:

[![](https://ampli-images.s3.amazonaws.com/production/cf9e6a72-8218-4d9b-997e-37ffacec505e/original)](https://ampli-images.s3.amazonaws.com/production/cf9e6a72-8218-4d9b-997e-37ffacec505e/original)

Neste caso, podemos utilizar a função _hover_. Assim, ao remover o cursor do mouse da caixa, a caixa volta a ser verde. Podemos também adicionar um novo evento que deve colorir a cor da caixa de roxo, caso o cursor do mouse tenha sido colocado sobre ela e depois removido. Veja:

[![](https://ampli-images.s3.amazonaws.com/production/fac764f7-f58e-4fdc-816c-adfa178ad94b/original)](https://ampli-images.s3.amazonaws.com/production/fac764f7-f58e-4fdc-816c-adfa178ad94b/original)

# **Bootstrap JavaScript**

[![](https://ampli-images.s3.amazonaws.com/production/575eaa6f-20c8-4326-8378-893b75099c62/original)](https://ampli-images.s3.amazonaws.com/production/575eaa6f-20c8-4326-8378-893b75099c62/original)

O _framework Bootstrap_ é capaz de aperfeiçoar a interface de websites. Contudo, Bootstrap não é apenas um _framework_ HTML/CSS, dispondo de uma série de recursos que utilizam _JavaScript_ para deixar a navegação mais interativa. Por exemplo, os componentes do _Bootstrap_ utilizam _JavaScript_ para exibição interativa de menus, caixas de aviso e imagens.

Para usar as funcionalidades _JavaScript_ do _Bootstrap_, deve-se incluir o _Bootstrap Bundle_. Observe o código a seguir, em que é apresentada uma estrutura modelo:

[![](https://ampli-images.s3.amazonaws.com/production/75145927-0ba0-4e29-bb19-177b293dfe61/original)](https://ampli-images.s3.amazonaws.com/production/75145927-0ba0-4e29-bb19-177b293dfe61/original)

Estrutura modelo utilizando Bootstrap. Fonte: elaborado pelo autor.

A partir desse modelo, você pode elaborar alguns exemplos de uso para o Bootstrap JavaScript. Aprenda, a seguir, com o exemplo dos menus suspensos.

# **Menu suspenso**

[![](https://ampli-images.s3.amazonaws.com/production/39f959fa-6bb1-4b13-8990-3ecdb5b674f5/original)](https://ampli-images.s3.amazonaws.com/production/39f959fa-6bb1-4b13-8990-3ecdb5b674f5/original)

Muitas vezes, ao construir um menu de um site, você tem uma quantidade maior de _links_ do que o espaço disponível. Uma solução é adicionar um menu suspenso, o qual, quando o usuário clicar no botão, o navegador exibirá abaixo ou acima uma lista com outros _links_. Observe o exemplo de menu suspenso da figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/e3c92ec6-a52e-44c3-a874-946d3fe4928a/original)](https://ampli-images.s3.amazonaws.com/production/e3c92ec6-a52e-44c3-a874-946d3fe4928a/original)

Exemplos de menus suspensos. Fonte: elaborado pelo autor.

Você pode implementar um exemplo de menu suspenso utilizando o _Bootstrap_. Observe o código a seguir e insira-o dentro do <_body_> de sua página:

[![](https://ampli-images.s3.amazonaws.com/production/74efbd53-e8eb-4387-ab4f-2a7fbbf94331/original)](https://ampli-images.s3.amazonaws.com/production/74efbd53-e8eb-4387-ab4f-2a7fbbf94331/original)

Menu suspenso utilizando Bootstrap. Fonte: elaborado pelo autor.

Agora observe o resultado:

[![](https://ampli-images.s3.amazonaws.com/production/b08f3926-ed41-48f4-8e58-a2da2d469832/original)](https://ampli-images.s3.amazonaws.com/production/b08f3926-ed41-48f4-8e58-a2da2d469832/original)

Exemplo de menu suspenso criado com Bootstrap (ao clicar no botão, três outros links são exibidos). Fonte: elaborado pelo autor.

O _Bootstrap_ utiliza classes para indicar ao navegador quais ações serão realizadas. Nesse caso, o botão criado deve ser precedido de uma div, que deve apresentar a classe _dropdown_. Essa classe indica que se trata de um menu suspenso. Observe também que o botão (_tag button_) tem as classes btn e btn-_secondary_ (responsáveis por aplicar o estilo do botão e a cor cinza), além da classe _dropdown-toggle_, que insere a seta que aponta para baixo no final do botão. Para que o menu suspenso funcione, o atributo data-bs-toggle="_dropdown_" é necessário. Já o atributo aria-_expanded_ recebe _false_ quando o menu está oculto e _true_ quando o menu é clicado.

Os links que queremos inserir no menu suspenso devem ser adicionados dentro de um elemento  <ul> que deve receber a classe _dropdown_-_menu_. Cada _link_ deve ser adicionado dentro de um elemento do tipo <li>, e pode ser um <_button_> ou um <a>, desde que receba a classe _dropdown_-item.

# **Modal**

[![](https://ampli-images.s3.amazonaws.com/production/bc8f7cdf-3faf-4f2a-9a18-c689aec247cf/original)](https://ampli-images.s3.amazonaws.com/production/bc8f7cdf-3faf-4f2a-9a18-c689aec247cf/original)

_Modals_ são caixas de diálogos usadas para exibir informações. Sua funcionalidade pode ser comparada às caixas de alertas exibidas ao executar o comando _alert_() do _JavaScript._ Entretanto, elas apresentam um design mais atrativo, em especial devido às animações de entrada e saída e ao efeito _lightbox_, quando o fundo é levemente escurecido dando destaque à caixa de diálogo.

[![](https://ampli-images.s3.amazonaws.com/production/d1c8d1ec-c949-45a1-a81d-6d7dc0ae030a/original)](https://ampli-images.s3.amazonaws.com/production/d1c8d1ec-c949-45a1-a81d-6d7dc0ae030a/original)

Exemplo de uso de um modal (será implementado a seguir). Fonte: elaborado pelo autor.

Para a implementação de um modal, deve-se considerar duas partes: um botão que ativará o modal e a div que receberá as informações do modal. Agora você pode implementar um modal. Observe no código a seguir a parte 1 (ativar o _modal_) e a parte 2 (_modal_).

[![](https://ampli-images.s3.amazonaws.com/production/a3c62ea2-3d73-48c9-b65d-6dc77db20195/original)](https://ampli-images.s3.amazonaws.com/production/a3c62ea2-3d73-48c9-b65d-6dc77db20195/original)

[![](https://ampli-images.s3.amazonaws.com/production/ae4d9874-49d5-4f14-af4f-d6e5982bf93d/original)](https://ampli-images.s3.amazonaws.com/production/ae4d9874-49d5-4f14-af4f-d6e5982bf93d/original)

Modal – Parte 1 (ativar modal) e parte 2 (div principal do modal). Fonte: elaborado pelo autor.

Observe que o botão que ativa o modal requer dois atributos:

[![](https://ampli-images.s3.amazonaws.com/production/2bf6f96c-67c4-40a1-9809-83cc3acbdbfa/original)](https://ampli-images.s3.amazonaws.com/production/2bf6f96c-67c4-40a1-9809-83cc3acbdbfa/original)

O primeiro indica que o botão acionará um modal e o segundo indica qual o ID do elemento que armazena o modal.

O elemento que recebe o modal deve receber a classe:

[![](https://ampli-images.s3.amazonaws.com/production/3f02e4a0-c957-489e-912a-7fc798360342/original)](https://ampli-images.s3.amazonaws.com/production/3f02e4a0-c957-489e-912a-7fc798360342/original)

Ainda, é importante que o id seja o mesmo informado no atributo:

[![](https://ampli-images.s3.amazonaws.com/production/808af05f-5333-46a3-80f0-906d914bd757/original)](https://ampli-images.s3.amazonaws.com/production/808af05f-5333-46a3-80f0-906d914bd757/original)

Além disso, o elemento que receberá o _modal_ pode ser composto por três partes principais:

- O cabeçalho do modal (classe _modal-header_).
- O corpo do modal (classe _modal-content_).
- O rodapé do modal (classe _modal-foote_r).

Esses elementos deverão ser parte de uma div que deve receber a classe _modal-dialog_ e de outra div que deve receber a classe _modal-content_.

______

**💭 Reflita**

Você aprendeu a construir _modals_. Entretanto, é possível enviar informações para um _modal_ diretamente de um elemento que ativa um evento. Como você faria para enviar informações para o _moda_l? Quais as modificações você faria no código a seguir?

Você pode consultar o site do _Bootstrap_ e pensar nas possíveis alterações desse código (BOOTSTRAP, [s.d.]).

# **Carrossel de imagens**

[![](https://ampli-images.s3.amazonaws.com/production/502deb49-a7e6-49e9-bf4e-c8be02d9960b/original)](https://ampli-images.s3.amazonaws.com/production/502deb49-a7e6-49e9-bf4e-c8be02d9960b/original)

_Bootstrap_ ainda apresenta um recurso para exibição de apresentações de imagens denominado carrossel de imagens (_carousel_). O carrossel de imagens utiliza transformações CSS 3D e um pouco de _JavaScript_ para exibir uma série de imagens, textos, indicadores e controles de troca de imagem.

Agora, observe os três possíveis estados do slideshow.

[![](https://ampli-images.s3.amazonaws.com/production/8592c72e-b97e-4483-9e57-96023f915ea0/original)](https://ampli-images.s3.amazonaws.com/production/8592c72e-b97e-4483-9e57-96023f915ea0/original)

Imagens inseridas no slideshow. Fonte: elaborado pelo autor.

Nesse exemplo, você pode clicar nas setas para alterar a imagem atual ou aguardar um tempo até ela ser trocada automaticamente (isso dependerá de o navegador oferecer suporte). É possível ver que a div container, colorida de preto para melhor visualizar os marcadores, tem uma largura maior do que a imagem. Essa escolha foi realizada para incluir o título definido para a imagem e a descrição.

Apresentamos até este momento três modelos em _JavaScript_ do _Bootstrap_ para a construção de páginas interativas: menus suspensos, _modals_ e carrossel de imagens. Entretanto, _Bootstrap_ fornece uma série de recursos e funcionalidades que podem auxiliar no desenvolvimento da sua aplicação.

# **Single-page applications**

[![](https://ampli-images.s3.amazonaws.com/production/852f90d5-1c2a-454c-90bb-ac10bed8d1b4/original)](https://ampli-images.s3.amazonaws.com/production/852f90d5-1c2a-454c-90bb-ac10bed8d1b4/original)

Como já pudemos observar, uma aplicação web pode apresentar muitas páginas. Além disso, as folhas de estilo surgiram para melhorar a performance, separando conteúdo e estilo em arquivos separados. Assim, vários arquivos relacionados a conteúdo podem utilizar um mesmo estilo.

[![](https://ampli-images.s3.amazonaws.com/production/53b8c59a-26fd-4ab5-bc47-8f7f8179ad11/original)](https://ampli-images.s3.amazonaws.com/production/53b8c59a-26fd-4ab5-bc47-8f7f8179ad11/original)

Um mesmo estilo usado para quatro páginas distintas. Fonte: elaborado pelo autor.

Assim, quando o usuário do seu site navegar, por exemplo, da página 1 para a página 2, o sistema não precisa carregar novamente o estilo, reduzindo a necessidade de transferir os códigos de estilo do servidor para o cliente.

______

**📝 Exemplificando**

Observe nas estruturas HTML que, ao navegar da página 1 para a página 2, o estilo utilizado é o mesmo e, além do estilo, as tags utilizadas também são as mesmas. Considere como exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/e2416f7c-ab1e-483e-ad89-2840602ea02f/original)](https://ampli-images.s3.amazonaws.com/production/e2416f7c-ab1e-483e-ad89-2840602ea02f/original)

Compare os dois códigos: a única mudança ocorre na div “conteudo”. Fonte: elaborado pelo autor.

E se o navegador pudesse buscar no servidor apenas as partes que foram modificadas de uma página para outra? Carregar a página levaria menos tempo. Veja na figura acima que o navegador só precisa buscar no servidor uma única linha em vez de oito.

______

O _JavaScript_ permitiu o carregamento de partes de páginas de forma mais elegante. Usando _JavaScrip_t é possível detectar um evento (o clique em um _link_), determinar a região que será alterada (usando o DOM para navegação) e consultar um servidor remoto para buscar o novo conteúdo que será inserido na página. O servidor remoto recebe a requisição e retorna apenas o que foi pedido por meio de uma linguagem back-end, como o PHP e, por fim, o _JavaScript_ remove o conteúdo anterior e adiciona o novo conteúdo sem a necessidade de recarregar a página.

Nesse caso, apenas uma requisição da página completa foi feita ao servidor, logo temos uma única página carregada. Assim, ao navegar por esse site, você não tem uma mudança real de página, mas uma simples troca de parte do conteúdo. Em desenvolvimento web, isso é denominado de _single-page_ _applications_.

______

**💭 Reflita**

Você provavelmente já usou um site que utiliza a tecnologia _single-page applications_. Ao enviar um e-mail pelo _Gmail_, você não precisa recarregar a página: simplesmente ao clicar no botão “escrever _e-mail_”, uma caixa para digitar a mensagem aparece no canto. Ou, então, ao usar o Facebook ou o Instagram, à medida que você desce pelo feed de notícias, novas postagens vão aparecendo, sem a necessidade de recarregar toda a página. Sites de comércio eletrônico também têm se beneficiado muito disso.

Codificar um site que faz esse tipo de requisições pode ser um pouco mais complicado; muitos problemas podem acontecer, por exemplo: se a requisição de parte de uma página falhar, como o usuário vai perceber?

______

Nos últimos anos, _frameworks JavaScript_ têm mudado a maneira pela qual uma aplicação web é estruturada, focando estratégias que melhorem a performance de um site. Um exemplo é o AngularJS, um _framework JavaScript_ proposto pela Google para construção de documentos _web single-page_. Observe a seguir um exemplo retirado do site oficial (ANGULARJS, 2018) demonstrando como o AngularJS funciona.

[![](https://ampli-images.s3.amazonaws.com/production/4034a428-49f3-4495-9e18-eacf0328498d/original)](https://ampli-images.s3.amazonaws.com/production/4034a428-49f3-4495-9e18-eacf0328498d/original)

Exemplo utilizando AngularJS. Fonte: elaborado pelo autor.

Neste momento, não é necessário conhecer os detalhes desse código, pois o _framework AngularJS_ não será aprofundado agora. O objetivo é apenas demonstrar como o _framework age_ em conjunto com os códigos HTML: utilizando atributos para detectar elementos do DOM ( como ng-_model_) e marcações para definir onde os dados serão inseridos (como {{seuNome}}). AngularJS foi encerrado em 2016 (essa versão foi considerada a 1.x) e substituído pelo _framework Angular_ (2021), que utiliza a linguagem _TypeScript_ no lugar de _JavaScript_.

### **Sites de alta performance**

Observe o exemplo de um site de comércio eletrônico que enfrenta uma grande quantidade de acessos em uma determinada data. O que ocorre se as seções de navegação e compra de produto funcionarem perfeitamente, mas o sistema de pagamento não funcionar? De que adiantaria o cliente escolher o produto se, na hora do pagamento, a transação falhar?

Por isso, o uso de estratégias híbridas é fundamental para construção de sites mais robustos e capazes de se manterem _on-line_ por mais tempo mesmo recebendo grandes quantidades de acessos. Nesse caso, diversas tecnologias podem ser combinadas, como _frameworks_ que melhoram a performance ou que reduzam os custos de processamento de servidores ou o tráfego na rede.

Importa destacar que quando falamos em grande quantidade de acessos, não estamos falando em receber entre 1 a 10 mil usuários visitantes ao mesmo tempo, mas, sim, de manter on-line dezenas de milhares a milhões de usuários simultaneamente. Para sites que não necessitam de suporte a tantos acessos em paralelo – ou seja, a grande maioria dos sites na internet –, o modelo tradicional de desenvolvimento, composto de HTML, CSS e _JavaScript_, atende às necessidades.

### **Páginas dinâmicas**

Até o momento foi apresentado o desenvolvimento web em aplicações de páginas estáticas (construídas com HTML + CSS) e aplicações de página única. Entre esses dois modelos de desenvolvimento de websites, não podemos deixar de citar um tipo fundamental: as **páginas dinâmicas**.

______

🔁 **Assimile**

**Formas de construção de websites e suas características**

- Páginas estáticas:

Conteúdo fixo

- Páginas dinâmicas:

Página HTML construída no servidor web.

Conteúdo pode ser armazenado em um banco de dados.

PHP

- _Single-page applications:_

Site carregado em uma página única.

Conteúdo carregado conforme a demanda.

______

Na construção de **páginas dinâmicas**, assim como os estilos armazenados nos arquivos CSS, a estrutura do site é armazenada separadamente em códigos HTML (note que nem sempre os códigos HTML estarão em arquivos de extensão “.html”). O conteúdo, por sua vez, é armazenado em uma estrutura separada, que pode ser em tabelas de bancos de dados (como o MySQL) ou até mesmo em arquivos de diversos tipos e formatos. Note que o documento web correspondente a uma página de internet não existe até o momento em que o usuário faz a requisição ao servidor web.

Este, por sua vez, recebe a requisição e deve “construir” a página: ele detecta, com base na requisição, qual o conteúdo desejado; carrega separadamente cada componente de códigos HTML, CSS e _JavaScript_; busca os dados referentes ao conteúdo em um banco de dados ou arquivo; e, por fim, monta uma página HTML, que será enviada para o navegador do cliente. Por isso dizemos que se trata de uma página dinâmica.

> Para que o servidor web funcione é necessária uma linguagem de programação para realizar os processamentos que construirão essa página dinâmica. Lembre-se de que chamamos de front-end as linguagens que executam no cliente (como JavaScript). Assim, as linguagens que executam no servidor são denominadas back-end.

Estudante, até aqui você conheceu vários _frameworks Javascript_ e agora já pode escolher o seu preferido e desenvolver sua aplicação _Javascript_. Mãos à obra!

______

**➕ Pesquise mais**

Estudante, seguem algumas sugestões de materiais que podem complementar seu aprendizado:

- Sites:

_jQuery_ site official (OPENJS FOUDANTION, [s.d.]).

_Sheet cheat_ jQuery: (ÓSCAR OTERO, [s.d.]).

- Videoaulas:

_Modal (Bootstrap_) (MODAL…, 2017).

Carrossel de imagens (CAROUSEL…, 2017).

- Artigos:

Introdução ao _jQuery_ (MARIANO, 2020a).

_Bootstrap JavaScript_ (MARIANO, 2020b).

_D3.js_ (MARIANO, 2020c).

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

Lembre-se de que, conforme a situação-problema apresentada, você foi contratado para criar uma página de planos de um site. A empresa apresenta quatro valores possíveis de planos. Precisamos implementar um formulário que envie o contato do cliente e qual plano será assinado quando ele clica em “Assine já!”, na seção de planos.

Uma possível visão da interface do formulário é mostrada na figura a seguir. Ao clicar em “Assine já!”, pode ser aberto o formulário com as informações dos planos e com os campos de preenchimento nome, telefone e endereço, juntamente com os termos de uso.

[![](https://ampli-images.s3.amazonaws.com/production/2375e1ae-1916-4c43-8f49-5a12f277fec2/original)](https://ampli-images.s3.amazonaws.com/production/2375e1ae-1916-4c43-8f49-5a12f277fec2/original)

Visão geral da interface do formulário. Fonte: elaborado pelo autor.

Observe a figura abaixo, que apresenta a resolução da situação-problema utilizando modal:

[![](https://ampli-images.s3.amazonaws.com/production/750afb17-c499-4a95-a500-1251eca274ba/original)](https://ampli-images.s3.amazonaws.com/production/750afb17-c499-4a95-a500-1251eca274ba/original)

[![](https://ampli-images.s3.amazonaws.com/production/3c11b9b6-acbe-4f85-adf1-6a41be00bc0e/original)](https://ampli-images.s3.amazonaws.com/production/3c11b9b6-acbe-4f85-adf1-6a41be00bc0e/original)

[![](https://ampli-images.s3.amazonaws.com/production/cd46b80b-f63e-46b9-b711-538f50e63d5e/original)](https://ampli-images.s3.amazonaws.com/production/cd46b80b-f63e-46b9-b711-538f50e63d5e/original)

[![](https://ampli-images.s3.amazonaws.com/production/a85c7e26-70b2-437e-87a6-796fd8c1251c/original)](https://ampli-images.s3.amazonaws.com/production/a85c7e26-70b2-437e-87a6-796fd8c1251c/original)

[![](https://ampli-images.s3.amazonaws.com/production/6436df5f-f696-4448-a0ef-58fa39dd78e9/original)](https://ampli-images.s3.amazonaws.com/production/6436df5f-f696-4448-a0ef-58fa39dd78e9/original)

[![](https://ampli-images.s3.amazonaws.com/production/19c2007e-d44e-4413-8dfe-86f58fa96840/original)](https://ampli-images.s3.amazonaws.com/production/19c2007e-d44e-4413-8dfe-86f58fa96840/original)

Utilização do modal. Fonte: elaborado pelo autor.

Agora observe a figura a seguir. Ele contém os _scripts_ construídos para manipular o estado dos botões e campos de seleção, os quais são detalhados nos comentários dentro do código:

[![](https://ampli-images.s3.amazonaws.com/production/7f559e18-9064-4efe-a48f-e796aa423841/original)](https://ampli-images.s3.amazonaws.com/production/7f559e18-9064-4efe-a48f-e796aa423841/original)

[![](https://ampli-images.s3.amazonaws.com/production/3ab08eb5-08d1-4ebf-b78c-c8590e87bb5b/original)](https://ampli-images.s3.amazonaws.com/production/3ab08eb5-08d1-4ebf-b78c-c8590e87bb5b/original)

[![](https://ampli-images.s3.amazonaws.com/production/95c1af33-e9cc-4f83-b951-fb483e2561be/original)](https://ampli-images.s3.amazonaws.com/production/95c1af33-e9cc-4f83-b951-fb483e2561be/original)

Utilização do modal. Fonte: elaborado pelo autor.

# **Referências**

[![](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)](https://ampli-images.s3.amazonaws.com/production/25daca5e-a68b-4181-a7fc-694b378f89ee/original)

ANGULAR. **Página inicial. Angular**, 2021. Disponível em: <https://angular.io>. Acesso em: 31 jul. 2021.

ANGULARJS. **Página inicial.** AngularJS, 2018. Disponível em: <https://angularjs.org/>. Acesso em: 31 jul. 2021.

BOOTSTRAP. **Modal. Varying modal content.** GetBootstrap, [s.d.]. Disponível em: <https://bit.ly/30Acsft>. Acesso em: 31 jul. 2021.

**CAROUSEL (Bootstrap)**. [S.l., s.n.], 2017. 1 vídeo (10 min. 23 seg.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/3ez7iJ0>. Acesso em: 31 jul. 2021.

ECMA-404 THE JSON DATA INTERCHANGE STANDARD. **Introdução ao JSON. Json.org**, [s.d.]. Disponível em: <https://bit.ly/3evW7AM>. Acesso em: 31 jul. 2021.

ENCYCLOPEDIA BRITANNICA. **Latitude e longitude**. **Britannica Escola**, c2021. Disponível em: <https://bit.ly/3tdcO8h>. Acesso em: 31 jul. 2021.

FERREIRA, A. L. **Como identificar uma tecla pressionada usando a propriedade “keyCode” do Javascript**. Visual Ficas, 26 fev. 2020. Disponível em: <https://bit.ly/30EBvOx>. Acesso em: 31 jul. 2021.

**FUNDAMENTOS do JavaScript**. [S.l., s.n.], 2017. 1 vídeo (3:24 min). Publicado pelo canal Diego Mariano. Disponível em: <https://cutt.ly/WzTb9EM>. Acesso em: 31 jul. 2021.

GITHUB. **Quagliato: select_estados.html**. GitHub Gist, c2021. Disponível em: <https://bit.ly/38Br3fk>. Acesso em: 31 jul. 2021.

GORDON, Z. **Const vs let vs var in JavaScript.** [s.d.]. Disponível em: <https://cutt.ly/CzTnwqP>. Acesso em: 31 jul. 2021.

INTRODUÇÃO ao JavaScript. [S.l., s.n.], 2017. 1 vídeo (4:02 min). Publicado pelo canal Diego Mariano. Disponível em: <https://cutt.ly/vzTnufl>. Acesso em: 31 jul. 2021.

IVANOVS, A. **24 Best Free JavaScript Frameworks for Web Developers 2020**. Colorlib, 27 ago. 2020. Disponível em: <https://bit.ly/3bH10p2>. Acesso em: 31 jul. 2021.

**JAVASCRIPT.COM**. [s.d.]. Disponível em: <https://www.javascript.com/>. Acesso em: 31 jul. 2021.

JQUERY. **Category: CSS**. jQuery, c2021c. Disponível em: <https://bit.ly/30ANdKj>. Acesso em: 31 jul. 2021.

JQUERY. **Category: Events**. jQuery, c2021d. Disponível em: <https://bit.ly/38B7PGq>. Acesso em: 31 jul. 2021.

JQUERY. **Category: Selectors**. jQuery, c2021b. Disponível em: <https://bit.ly/3levNfN>. Acesso em: 31 jul. 2021.

JQUERY. **Página inicial**. jQuery, c2021a. Disponível em: <https://jquery.com/>. Acesso em: 31 jul. 2021.

**JS BIN**. [s.d.]. Disponível em: <http://jsbin.com/>. Acesso em: 31 jul. 2021.

**JSON**. [S.l., s.n.], 11 out. 2017.1 vídeo (5 min. 34 seg.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/38yHKb1>. Acesso em: 31 jul. 2021.

MALAVASI, A. **Afinal, Javascript e ECMAScript são a mesma coisa?** 2017. Disponível em: <https://cutt.ly/gzTnnUX>. Acesso em: 31 jul. 2021.

MARIANO, D. **Bootstrap JavaScript.** Diego Mariano, 15 ago. 2020b. Disponível em: <https://bit.ly/30ClaKh>. Acesso em: 31 jul. 2021.

MARIANO, D. **D3.js.** Diego Mariano, 15 ago. 2020c. Disponível em: <https://bit.ly/3rTIvD6>. Acesso em: 31 jul. 2021.

MARIANO, D. **Fundamentos do Java Script.** Diego Mariano, 15 ago. 2020. Disponível em: <https://bit.ly/3rI7lFZ>. Acesso em: 31 jul. 2021.

MARIANO, D. Fundamentos do JavaScript. Diegomariano, 15 ago. 2020a. Disponível em: <https://cutt.ly/ezTnOJx>. Acesso em: 31 jul. 2021.

MARIANO, D. Introdução ao JavaScript. Diegomariano, 15 ago. 2020b. Disponível em: <https://cutt.ly/WzTmkcw>. Acesso em: 31 jul. 2021.

MARIANO, D. **jQuery.** Diego Mariano, 15 ago. 2020a. Disponível em: <https://bit.ly/3cq7tUf>. Acesso em: 31 jul. 2021.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à Programação Web para Bioinformática: HTML, CSS, PHP and JavaScript.** [S.l.] Independently Published, 2017.

MARIANO, D.; DE MELO-MINARDI, R. **Introdução à Programação Web para Bioinformática: HTML, CSS, PHP and JavaScript.** [S.l.]: Independently Published, 2017.

MDN WEB DOCS. **Elements. Events. MDN Web Docs Mozilla**, [s.d.]. Disponível em: <https://mzl.la/3ey2sMc>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **Introduction to the DOM**. MDN Web Docs Mozilla, [s.d.].Disponível em: <https://mzl.la/30ytWZU>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **JavaScript básico**. 2020. Disponível em: <https://cutt.ly/yzTnVhO>. Acesso em: 31 jul. 2021.

MDN WEB DOCS. **Trabalhando com objetos**. 2019. Disponível em: <https://cutt.ly/xzTn9Wo>. Acesso em: 31 jul. 2021.

**MODAL (Bootstrap)**. [S.l., s.n.], 11 out. 2017. 1 vídeo (8 min. 41 seg.). Publicado pelo canal Diego Mariano. Disponível em: <https://bit.ly/3bClvD8>. Acesso em: 31 jul. 2021.

**O QUE o JavaScript é capaz de fazer?** – Curso JavaScript \#01. [S.l., s.n.], 2019. 1 vídeo (28:49 min). Publicado pelo canal Curso em Vídeo. Disponível em: <https://cutt.ly/VzTn6Wl>. Acesso em: 31 jul. 2021.

OPENJS FOUDANTION. **Página Inicial**. OpenJS Foundation, [s.d.]. Disponível em: <https://jquery.org>. Acesso em: 21 jul. 2021.

OPENLAYERS. **Quick start**. OpenLayers, [s.d.]. Disponível em: <https://bit.ly/3l7b0ee>. Acesso em: 31 jul. 2021.

ÓSCAR OTERO. **jQuery**. Óscar Otero, [s.d.]. Disponível em: <https://bit.ly/3bG484p>. Acesso em: 31 jul. 2021.

PILGRIM, M. **Dive into HTML 5**. [S.l.]: O’Reilly Media, 2010. Disponível em: <https://bit.ly/38wSC9v>. Acesso em: 31 jul. 2021.

STACK OVERFLOW. **Developer Survey Results**. Stack Overflow, 2019. Disponível em: <https://cutt.ly/azTmoso>. Acesso em: 31 jul. 2021.