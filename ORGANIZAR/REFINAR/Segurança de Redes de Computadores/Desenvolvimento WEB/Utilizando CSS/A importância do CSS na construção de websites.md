# **Introdução da Unidade**

[![](https://ampli-images.s3.amazonaws.com/production/fa749297-23c0-4fd1-a738-a555ca67f9cd/original)](https://ampli-images.s3.amazonaws.com/production/fa749297-23c0-4fd1-a738-a555ca67f9cd/original)

Estudante, nesta unidade você se aprofundará nos estudos para se tornar um desenvolvedor web. Com os conhecimentos apresentados nesta unidade, você aprenderá a estilizar as páginas em html, tornando-as visualmente mais amigáveis. Agora, você vai aperfeiçoar o _layout_ de suas páginas. Aqui, veremos as folhas de estilo em cascata.

Na aula 1, veremos uma breve introdução à linguagem CSS (_Cascading Style Sheets_), a inclusão do CSS em um website, as regras e os seletores CSS, além das propriedades de texto, formatação, cores e propriedades _background_ em CSS.

Na aula 2, abordaremos _layouts_ em CSS; aprenderemos os conceitos do _box model_ HTML/CSS, como as propriedades de bordas, preenchimentos e margens; e veremos o posicionamento de elementos em páginas HTML, além de propriedades como largura e altura. Por fim, na aula 3, veremos a formatação em tabelas CSS e em formulários HTML, animações e transição usando-se CSS, além de alguns _frameworks_ CSS.

Vamos lá!

# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/5aab4753-7008-47b0-ae78-f19fa0f7c93e/original)](https://ampli-images.s3.amazonaws.com/production/5aab4753-7008-47b0-ae78-f19fa0f7c93e/original)

### **Qual é o foco da aula?**

Nesta aula, irá conhecer _Cascating Style Sheet_ (CSS)

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- aplicar formas da linguagem CSS;
- empregar construção de códigos HTML;
- examinar formatar textos e imagens em sites..

**Situação-problema**

Olá!

O conhecimento dos fundamentos da linguagem HTML permite a você a construção de seus primeiros websites. Entretanto, as páginas que você pode construir usando apenas os conhecimentos adquiridos nessa linguagem de marcação, possivelmente, não apresentarão uma interface muito amigável.

Isso se deve ao fato de a linguagem HTML ter sido planejada para armazenar e estruturar os conteúdos, enquanto a aparência da página é de responsabilidade das folhas de estilo.

> CSS é a sigla para cascating style sheet (folha de estilo em cascata). CSS é uma linguagem propriamente desenvolvida para configuração de estilo e aparência. Ela é fundamentada na definição de estilos aplicados a seletores (elementos HTML) por meio das propriedades.

Códigos CSS podem ser inseridos de três formas:

- Por meio de declarações inline realizadas diretamente do elemento que se deseja formatar.
- Por meio de declarações na _tag_ de estilos.
- E por meio de arquivos externos.

Aqui, veremos como construir códigos HTML usando-se as três formas e qual delas é considerada mais apropriada.

Nesta aula, você vai conhecer os fundamentos da linguagem CSS, sua sintaxe e principais características. Você verá, ainda, como formatar textos, alterar cores de elementos e adicionar imagens como planos de fundo.

Você foi contratado por uma empresa de provedor de internet que solicitou que você crie a página web do provedor. Assim, você deverá criar a estrutura das páginas e aplicar o estilo (CSS). Dessa vez, você criará uma página de apresentação da empresa (“QUEM SOMOS”), mas enquanto você trabalhava em uma página experimental para a empresa de vendas de planos de internet, você construiu os códigos _index_.html e estilo.css a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/68431265-6319-46c0-a2b6-7013b1817170/original)](https://ampli-images.s3.amazonaws.com/production/68431265-6319-46c0-a2b6-7013b1817170/original)

Index.html. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/4e34d338-43ea-4422-bacc-a23dcc03d37c/original)](https://ampli-images.s3.amazonaws.com/production/4e34d338-43ea-4422-bacc-a23dcc03d37c/original)

Estilo.css. Fonte: Elaborado pelo autor.

Foi sugerido por um dos membros da equipe, a inclusão de uma fonte externa, a fonte “Roboto”: uma fonte gratuita disponível na plataforma de fontes do Google. Você acessou o site, fez o _download_ da fonte e a instalou em seu computador.

Entretanto, ao visualizar a página no navegador de outro computador, você notou que a fonte correta não estava sendo carregada, como pode ser visto na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/25fc82e8-bb4b-4f50-b4e2-60051d57c0c0/original)](https://ampli-images.s3.amazonaws.com/production/25fc82e8-bb4b-4f50-b4e2-60051d57c0c0/original)

Como a página foi exibida. Fonte: Elaborado pelo autor.

Roboto é uma fonte não serifada, o que difere da fonte apresentada. Observe a figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/5c5131c9-03fd-4d46-88bc-92803e0fe6d0/original)](https://ampli-images.s3.amazonaws.com/production/5c5131c9-03fd-4d46-88bc-92803e0fe6d0/original)

Exemplo de texto escrito com a fonte Roboto. Fonte: Captura de tela do Google Fonts adaptada pelo autor.

Explique o que pode ter ocorrido e como você pode resolver esse problema.

Faça o _download_ da fonte Roboto em Google _Font_s.

# **Conceito-Chave**

[![](https://ampli-images.s3.amazonaws.com/production/c0217a13-e584-4824-962a-52e56c45fa54/original)](https://ampli-images.s3.amazonaws.com/production/c0217a13-e584-4824-962a-52e56c45fa54/original)

A estrutura de uma página Web pode ser criada utilizando-se apenas a linguagem HTML, possibilitando a construção de seus primeiros websites, todavia, é possível criar páginas com o visual não tão amigável para o usuário. Na medida em que páginas da internet se tornaram mais complexas, tornou-se necessário melhorar e estruturar o seu desenvolvimento. Isso se deve ao fato de a linguagem HTML ter sido planejada para armazenar e estruturar os conteúdos, porém o visual e a aparência da página devem ser desenvolvidos por meio das folhas de estilo em cascata (ou CSS).

# **Folhas de estilo em cascata**

[![](https://ampli-images.s3.amazonaws.com/production/622b34e8-8d74-4b95-aa0a-2b23195a7861/original)](https://ampli-images.s3.amazonaws.com/production/622b34e8-8d74-4b95-aa0a-2b23195a7861/original)

CSS, do inglês _cascading style sheets_, ou na tradução “folhas de estilos em cascata”, é uma linguagem de estilos utilizada para se definir a aparência de um documento web. CSS surgiu com um dos objetivos de separar códigos relacionados a conteúdo dos códigos relacionados à aparência de uma página. A Figura “Como a página foi exibida” ilustra a estrutura de separação de conteúdo e a aparência de um website. Observe que, para o conteúdo e a estrutura de uma página, é utilizada a linguagem html, e para a aparência (“estilo”) da página, a linguagem CSS. Assim, enquanto a estrutura básica e o conteúdo de uma página, tais como _tags_ estruturais, textos, imagens e vídeos, são construídos em arquivos HTML, os arquivos CSS armazenam os estilos, como fontes, espaçamentos, cores, tamanhos e outros elementos estruturais.

[![](https://ampli-images.s3.amazonaws.com/production/c02106c4-068f-4f67-a3c1-ee2d96c34ef3/original)](https://ampli-images.s3.amazonaws.com/production/c02106c4-068f-4f67-a3c1-ee2d96c34ef3/original)

Separação de conteúdo e aparência para a criação de um website. Fonte: Elaborado pelo autor.

Com o CSS, é possível criar um único arquivo de folhas de estilo e importá-lo em diversas páginas HTML, o que permitirá economizar muito tempo no desenvolvimento e na manutenção de códigos.

______

**⚠️ Atenção**

HTML e CSS **não** são linguagens de programação. Enquanto HTML é uma linguagem de marcação de hipertextos, CSS é uma linguagem de folhas de estilos.

# **Incluindo CSS em uma página HTML**

[![](https://ampli-images.s3.amazonaws.com/production/adcd9c56-f70b-4b4d-927a-19aeb24b9699/original)](https://ampli-images.s3.amazonaws.com/production/adcd9c56-f70b-4b4d-927a-19aeb24b9699/original)

Há três formas de incluir estilos em arquivos HTML:

- Atributo _style_ (inserção _inline_).
- _Tag <style_>.
- Importação de arquivo “.css”.

# **Atributo Style**

[![](https://ampli-images.s3.amazonaws.com/production/762ad354-e5fd-4c09-83c0-cd03b1c89a76/original)](https://ampli-images.s3.amazonaws.com/production/762ad354-e5fd-4c09-83c0-cd03b1c89a76/original)

As configurações de estilo são aplicadas diretamente na tag que se deseja formatar:

[![](https://ampli-images.s3.amazonaws.com/production/25bc798d-c2e9-4694-ba92-968b8b039b7e/original)](https://ampli-images.s3.amazonaws.com/production/25bc798d-c2e9-4694-ba92-968b8b039b7e/original)

No trecho <p _style_= "_color: red_">Olá mundo!</p> , a cor do texto (_color_) é alterada para vermelho (_red_) por meio do atributo de estilos (_style_), que pode ser aplicado a qualquer _tag_ HTML.

# **Tag <style>**

[![](https://ampli-images.s3.amazonaws.com/production/2034f804-4525-43f6-abf1-b17068712319/original)](https://ampli-images.s3.amazonaws.com/production/2034f804-4525-43f6-abf1-b17068712319/original)

As configurações de estilo são inseridas dentro da _tag < style >< /style_ >. Nesse caso, é necessário informar um seletor, que será abordado na próxima seleção.

[![](https://ampli-images.s3.amazonaws.com/production/6cfd5943-dafe-462a-bc87-e519589e82e0/original)](https://ampli-images.s3.amazonaws.com/production/6cfd5943-dafe-462a-bc87-e519589e82e0/original)

Esse código funciona similar ao trecho <p style="_color: red_">Olá mundo!</p>. Porém, a principal diferença é que, enquanto o atributo _style_ utilizado em <p _style_=></p>aplica uma configuração a uma tag específica, a _tag_ <style> aplicará a formatação a todas as ocorrências do seletor, ou seja, todas as ocorrências da tag p, logo, todo conteúdo presente em _tags_ <p> recebe a cor vermelha.

# **Importação de um arquivo CSS**

[![](https://ampli-images.s3.amazonaws.com/production/c867c705-e8e4-47f1-944d-d50997dac610/original)](https://ampli-images.s3.amazonaws.com/production/c867c705-e8e4-47f1-944d-d50997dac610/original)

Outra forma de incluir um código de estilo em um documento Web é importar um arquivo CSS por meio da _tag <link_>. Em geral, essa tag deve ser incluída dentro do cabeçalho da página, isto é, entre as _tags <head></head_>. Um arquivo CSS deve conter apenas códigos escritos no padrão CSS. Observe o exemplo, a seguir, de como é realizada a importação do CSS:

[![](https://ampli-images.s3.amazonaws.com/production/25993b8a-6046-477f-8ad6-6ef8aa67fac9/original)](https://ampli-images.s3.amazonaws.com/production/25993b8a-6046-477f-8ad6-6ef8aa67fac9/original)

Nesse exemplo, a _tag <link_> recebe dois atributos. O primeiro é o atributo _href_, que informa a localização e o nome do arquivo que será ligado à página HTML. O arquivo importado é denominado “estilo.css”, e para esse exemplo, deve estar no mesmo diretório do arquivo HTML que o importou. O segundo é o atributo rel, que informa o tipo do arquivo conectado, que, nesse caso, trata-se de uma folha de estilos (_stylesheet_).

Os dois primeiros métodos para inserção de estilos são realizados internamente, ou seja, no código HTML. Portanto, o uso desses métodos não é considerado uma boa prática, logo, a maneira mais adequada para aplicar estilos na sua página web é por meio da inserção dos códigos relacionados à aparência em um arquivo externo, nomeado com a extensão “.css”.

# **Sintaxe da linguagem CSS**

[![](https://ampli-images.s3.amazonaws.com/production/9f232a6f-8cf2-424c-a0b7-9f58dd44388a/original)](https://ampli-images.s3.amazonaws.com/production/9f232a6f-8cf2-424c-a0b7-9f58dd44388a/original)

A sintaxe básica da linguagem CSS inclui a inserção de um seletor e uma ou várias declarações de estilo dentro de chaves. As declarações devem ser separadas por ponto e vírgula (“ ; ”). Uma declaração é composta por uma propriedade e um valor para essa propriedade, como pode ser observado na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/102a22b3-9b71-440d-8342-4f9ccf9ee61b/original)](https://ampli-images.s3.amazonaws.com/production/102a22b3-9b71-440d-8342-4f9ccf9ee61b/original)

Sintaxe do CSS. Fonte: Adaptado de MDN (2020).

No exemplo da figura acima, o seletor p (parágrafos) receberá a propriedade _color_ (cor) com o valor _red_ (vermelho). Veja como a estrutura de declarações CSS é simples e lógica. Nesse exemplo, nosso seletor escolhido para aplicação das regras de formatação foi p, o que indica que as propriedades serão aplicadas a todas as _tags_ <p>. Como podemos observar, é possível seguir essa regra para todas as _tags_, que também serão consideradas seletores. Todavia, seletores vão muito além de _tags_.

______

🔁 Assimile

**Por que o nome se refere a estilos em cascata?**

O estilo em cascata se refere à forma como os navegadores de internet carregam arquivos de estilos. Uma página HTML pode importar de nenhuma a diversas folhas de estilo. Logo, é natural que possam ocorrer conflitos, isto é, um mesmo seletor pode receber diversas declarações diferentes em partes diferentes do código. Para definir qual declaração deverá ser aplicada na apresentação final da página, CSS utiliza o **efeito cascat****a**, em que declarações realizadas em diferentes níveis possuem prioridade sobre outros níveis, como pode ser observado na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/6a3c1a2c-5549-48c6-a669-5edc5e4d3917/original)](https://ampli-images.s3.amazonaws.com/production/6a3c1a2c-5549-48c6-a669-5edc5e4d3917/original)

Ordem de carregamento do CSS. Fonte: Mariano; de Melo-Minardi (2017, p. 110).

Nesse exemplo, os estilos de maior prioridade são os inseridos com a marcação:

**!important**

E as de menor prioridade são as folhas de estilo do navegador.

Por exemplo, imagine que você acaba de criar uma página e adicionou o seguinte código:

[![](https://ampli-images.s3.amazonaws.com/production/8406801e-0ed9-4da4-8768-a0112c6423e0/original)](https://ampli-images.s3.amazonaws.com/production/8406801e-0ed9-4da4-8768-a0112c6423e0/original)

index.html – Olá mundo!. Fonte: Elaborado pelo autor.

O código apresentado vai gerar a página ilustrada na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/0e28cee7-ba1c-4152-8122-b147930f95f8/original)](https://ampli-images.s3.amazonaws.com/production/0e28cee7-ba1c-4152-8122-b147930f95f8/original)

Exemplo de página. Fonte: Elaborado pelo autor.

Observe que, no código apresentado, não foram especificados a fonte, o tamanho da fonte, a cor do fundo, entre outras coisas. Para a formatação aplicada a essa página, foi considerada as configurações definidas pelo navegador, ou seja, considerou-se um nível de menor importância.

Agora observe as figuras a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/7858eae5-6532-46d3-baf9-3920d958dac2/original)](https://ampli-images.s3.amazonaws.com/production/7858eae5-6532-46d3-baf9-3920d958dac2/original)

Tag <style> com cor de fundo preto e cor da fonte vermelha incorporada ao arquivo index.Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/03667c18-c6cf-47dc-8f33-9802b90120bf/original)](https://ampli-images.s3.amazonaws.com/production/03667c18-c6cf-47dc-8f33-9802b90120bf/original)

Background. Fonte: Elaborado pelo autor.

Dessa vez, os estilos foram aplicados usando-se a _tag <style_>. Veja que foi aplicada ao seletor _body_ a propriedade _background-color_ (cor de fundo) de valor _black_ (preto). Além disso, foi aplicada ao _body_ a propriedade _color_ (cor de texto) de valor _red_ (vermelho). Mesmo assim, o conteúdo da _tag_ <p> recebeu a cor vermelha.

Isso ocorre porque: (1) declarações da _tag_ <_style_> têm prioridade sobre a folha de estilo padrão do navegador (que iria inserir fundo branco e cor de texto preta) e (2) a _tag_ <p> está inserida dentro das _tags_ <_body></body_>; portanto, na ausência de uma declaração para o seletor p, os estilos da _tag_ de nível superior são aplicados à _tag_ em questão.

Agora, veja o que ocorre se você adicionar um atributo _style_ que muda a cor da tag <p> para azul (figura - Atributo style):

[![](https://ampli-images.s3.amazonaws.com/production/69813120-57d4-4082-9658-0259b51c25dc/original)](https://ampli-images.s3.amazonaws.com/production/69813120-57d4-4082-9658-0259b51c25dc/original)

Tag <style> com atributo style que altera a cor da tag <p> para azul. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/cec28796-dc57-44cd-a2cf-4ef5ab45315a/original)](https://ampli-images.s3.amazonaws.com/production/cec28796-dc57-44cd-a2cf-4ef5ab45315a/original)

Atributo style. Fonte: Elaborado pelo autor.

Aqui, observamos que o atributo _style_ tem prioridade sobre a _tag </style_>. A não ser que haja a declaração _**!important**_, que tem prioridades sobre todas as outras, desde que ela seja aplicada diretamente sobre o seletor desejado. Observe a figura “Valor !_important_”:

[![](https://ampli-images.s3.amazonaws.com/production/5d83c64f-3efc-4237-9fdd-98ca3a88bf3e/original)](https://ampli-images.s3.amazonaws.com/production/5d83c64f-3efc-4237-9fdd-98ca3a88bf3e/original)

Declaração !important aplicada ao seletor p, sendo priorizado e sendo aplicada a cor verde ao texto. Fonte; Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/f936cf14-0bf2-4d37-b9ec-175886de0c94/original)](https://ampli-images.s3.amazonaws.com/production/f936cf14-0bf2-4d37-b9ec-175886de0c94/original)

Valor !important. Fonte: Elaborado pelo autor.

Nesse caso, temos três declarações para a propriedade _color_: verde, vermelho e azul. Assim, podemos observar claramente a importância do efeito cascata, que age como camadas sobrepondo estilos declarados em folhas de estilo de menor importância. A figura abaixo ilustra como o navegador reconhece os estilos aplicados e seleciona apenas um deles.

[![](https://ampli-images.s3.amazonaws.com/production/aaadc1a0-a016-4ee8-bce7-e96e01a55650/original)](https://ampli-images.s3.amazonaws.com/production/aaadc1a0-a016-4ee8-bce7-e96e01a55650/original)

Visualização da propriedade inspecionar elemento do navegador Google Chrome. Fonte: Captura de tela da propriedade inspecionar elemento, do Google Chrome, adaptada pelo autor.

Note que a cor azul (_blue_) foi reconhecida, mas o navegador optou pela propriedade _green_ (verde) que é declarada com _**!important**_

# **Regras e seletores em CSS**

[![](https://ampli-images.s3.amazonaws.com/production/c8dec4a8-38f6-435e-b7e5-ff5a38df7a3b/original)](https://ampli-images.s3.amazonaws.com/production/c8dec4a8-38f6-435e-b7e5-ff5a38df7a3b/original)

- **Classes** _**(class)**_ **e identificadores (ID)**

Antes de introduzirmos os seletores CSS, é necessário apresentar dois atributos HTML importantes: _class_ e id. O atributo _class_ (classe) recebe um nome que pode ser aplicado a um ou mais elementos. Já o atributo id deve ser um nome identificador para um único elemento da página.

[![](https://ampli-images.s3.amazonaws.com/production/77b1a27a-6382-46e4-91cc-9d2da5151bd7/original)](https://ampli-images.s3.amazonaws.com/production/77b1a27a-6382-46e4-91cc-9d2da5151bd7/original)

Veja um exemplo simples de uso:

[![](https://ampli-images.s3.amazonaws.com/production/3b67b154-c2e7-4bdd-a29d-9a77ba0c2348/original)](https://ampli-images.s3.amazonaws.com/production/3b67b154-c2e7-4bdd-a29d-9a77ba0c2348/original)

Aqui, temos duas _tags_ <p>, sendo que a primeira recebe a _class_ “vermelho” e a segunda recebe o id “apresentação”.

- **Seletores**

Seletores representam elementos de uma página HTML cujas propriedades CSS serão aplicadas (SILVA, 2018). Como apresentado na seção anterior, _tags_ são simples exemplos de seletores, mas além delas, existem muitos outros, como as classes, os identificadores, os seletores universais e os seletores múltiplos (quando múltiplos elementos são listados). Observe a figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/b7973581-1c8b-444a-928e-827f18d239a4/original)](https://ampli-images.s3.amazonaws.com/production/b7973581-1c8b-444a-928e-827f18d239a4/original)

Tipos de seletores. Fonte: adaptado de W3Schools ([s.d.]).

Observe, a seguir, exemplos de aplicação de seletores. Inicialmente, utilizamos apenas a propriedade que altera a cor da fonte (_color_).

Agora, vamos separar os códigos em dois arquivos diferentes, sendo um arquivo .html (figura “index.html”) e o outro .css (figura “estilo.css”).

[![](https://ampli-images.s3.amazonaws.com/production/4994fe07-f6c6-4247-b1bb-2d3c5aacd7c9/original)](https://ampli-images.s3.amazonaws.com/production/4994fe07-f6c6-4247-b1bb-2d3c5aacd7c9/original)

[![](https://ampli-images.s3.amazonaws.com/production/2d3301fd-b635-4984-aa9e-5168c27be634/original)](https://ampli-images.s3.amazonaws.com/production/2d3301fd-b635-4984-aa9e-5168c27be634/original)

Index.html. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/cc0da81a-5d74-4332-a372-1ffc0d779964/original)](https://ampli-images.s3.amazonaws.com/production/cc0da81a-5d74-4332-a372-1ffc0d779964/original)

[![](https://ampli-images.s3.amazonaws.com/production/6d548bd8-1dca-4e76-bd80-be364ac07b84/original)](https://ampli-images.s3.amazonaws.com/production/6d548bd8-1dca-4e76-bd80-be364ac07b84/original)

Estilo.css. Fonte: Elaborado pelo autor.

Os códigos produzirão a seguinte página (figura “Diferentes tipos de seletores”):

[![](https://ampli-images.s3.amazonaws.com/production/95fdbc32-7f17-4ca9-afb8-cdc6de42e24e/original)](https://ampli-images.s3.amazonaws.com/production/95fdbc32-7f17-4ca9-afb8-cdc6de42e24e/original)

Diferentes tipos de seletores. Fonte: Elaborado pelo autor.

Pode-se observar que classes e IDs só aplicam formatações aos elementos em que foram declarados. Enquanto classes podem ser utilizadas múltiplas vezes, um ID só pode ser usado em um único elemento. Para diferenciar classes e IDs, CSS requer que os seletores sejam declarados usando-se os símbolos “.” e “#”, respectivamente. Logo, a declaração “.texto-verde” representa uma classe, enquanto a declaração “\#azul” representa um ID.

______

**🔁 Assimile**

**Comentários CSS**

Comentários são trechos de códigos que são ignorados durante a interpretação dos comandos. Na prática, eles são utilizados para documentação, i.e., para inserir explicações sobre o funcionamento dos códigos. Em CSS, comentários devem ser inseridos entre os símbolos /* e */. Por exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/611afdc0-6cf4-4680-8c59-0be0a48fbc87/original)](https://ampli-images.s3.amazonaws.com/production/611afdc0-6cf4-4680-8c59-0be0a48fbc87/original)

Você pode realizar declarações múltiplas, separando os seletores por vírgulas:

[![](https://ampli-images.s3.amazonaws.com/production/f4dc1901-f7d8-4bd8-9f0b-9de5410d1a15/original)](https://ampli-images.s3.amazonaws.com/production/f4dc1901-f7d8-4bd8-9f0b-9de5410d1a15/original)

A figura abaixo mostra o resultado da página. Observe que você deve apagar as declarações individuais para os seletores div e _span_ ou, então, as regras definidas posteriormente substituirão essa nova regra. Isso se deve ao efeito em cascata, que será explicado no decorrer desta aula.

[![](https://ampli-images.s3.amazonaws.com/production/80956f73-8a55-4fd6-87b4-17d1ac94b753/original)](https://ampli-images.s3.amazonaws.com/production/80956f73-8a55-4fd6-87b4-17d1ac94b753/original)

Declarações múltiplas. Fonte: Elaborado pelo autor.

Por fim, você deve conhecer o seletor universal “*”. Esse seletor aplica regras a qualquer elemento. Para ilustrar isso, vamos apresentar um exemplo que explora uma regra aplicada por navegadores: a regra de margens. Por padrão, navegadores podem aplicar regras CSS em alguns elementos. Como exemplo, podemos listar as margens aplicadas em elementos. Observe o texto inserido na _tag_ <p>, da figura “Declarações múltiplas”: a _tag_ <p> recebe uma configuração de margem diferente das demais e note que o espaçamento de todas as _tags_ para a margem da página, isso foi realizado por meio da inclusão do asterisco (*) antes de abrir chaves do seletor. Agora, vamos aplicar uma propriedade que remove todas as margens e aplicá-la ao seletor universal:

[![](https://ampli-images.s3.amazonaws.com/production/c796e61e-e6f2-42bb-b198-84684a478b6f/original)](https://ampli-images.s3.amazonaws.com/production/c796e61e-e6f2-42bb-b198-84684a478b6f/original)

Nesse exemplo, a propriedade _margin_ (margem) recebe o valor 0. Aplicada ao seletor universal, ela removerá margens personalizadas de todas as _tags_ que as possuem (figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/3ba796ff-c3d9-4fc7-aee3-38ac19c965c3/original)](https://ampli-images.s3.amazonaws.com/production/3ba796ff-c3d9-4fc7-aee3-38ac19c965c3/original)

Margens removidas. Fonte: Elaborado pelo autor.

Agora, observe que todas as tags possuem a mesma margem. Além disso, a margem para a borda da página foi removida. O seletor universal permite que você reinicie as configurações de estilo de uma página e construa seus estilos sem influência de estilos herdados de outras folhas de estilo, que será abordada na sequência da aula. No próximo tópico, apresentaremos algumas propriedades CSS.

# **Propriedades de textos**

[![](https://ampli-images.s3.amazonaws.com/production/696f8f56-2fa6-45d4-bb82-188422da8f95/original)](https://ampli-images.s3.amazonaws.com/production/696f8f56-2fa6-45d4-bb82-188422da8f95/original)

Agora, falaremos das outras propriedades CSS referentes a fontes. As fontes dizem respeito à forma como são “desenhados” os caracteres usados em textos. A figura abaixo sintetiza algumas propriedades CSS que podem ser aplicadas às fontes.

[![](https://ampli-images.s3.amazonaws.com/production/da0e2317-7a21-4d92-981e-ef99339b6da5/original)](https://ampli-images.s3.amazonaws.com/production/da0e2317-7a21-4d92-981e-ef99339b6da5/original)

[![](https://ampli-images.s3.amazonaws.com/production/8c48a5ff-da02-4755-8d2a-08bda5ee827d/original)](https://ampli-images.s3.amazonaws.com/production/8c48a5ff-da02-4755-8d2a-08bda5ee827d/original)

[![](https://ampli-images.s3.amazonaws.com/production/c25f81fc-04f3-4fe6-8083-1220a0587c34/original)](https://ampli-images.s3.amazonaws.com/production/c25f81fc-04f3-4fe6-8083-1220a0587c34/original)

[![](https://ampli-images.s3.amazonaws.com/production/b9fd2874-3194-473b-8be0-74c422c926f6/original)](https://ampli-images.s3.amazonaws.com/production/b9fd2874-3194-473b-8be0-74c422c926f6/original)

Tipos de propriedades de texto CSS.Fonte: adaptado de Maujor (2016); W3Schools (2020).

A propriedade responsável por alterar o tipo de fonte utilizada em um site é a _font-family._ As fontes, em geral, podem ser classificadas em serifadas e não serifadas (observe a diferença na figura abaixo). No entanto, a propriedade _font-family_ permite alterar as fontes usadas para diversas famílias distintas. Uma das fontes tipográficas mais populares é “_Helvetica_”, seguida por “_Arial_”.

[![](https://ampli-images.s3.amazonaws.com/production/62551720-cc60-4e8a-9450-d6d54e810722/original)](https://ampli-images.s3.amazonaws.com/production/62551720-cc60-4e8a-9450-d6d54e810722/original)

Diferença entre fontes serifadas e não serifadas.Fonte: Elaborado pelo autor.

> As fontes que não possuem serifas são consideradas mais esteticamente agradáveis. Entretanto, as serifas facilitam a percepção da palavra pelo olhar humano. Elas são muito utilizadas em blocos de texto pequenos, como em jornais.

d

Antes de alterar a família da fonte de um website, deve-se avaliar se os leitores daquele site terão as fontes instaladas em suas máquinas, caso contrário, o sistema alterará a exibição para a fonte padrão do navegador (em geral, _Times New Roman_). Para tentar amenizar esse problema, pode-se declarar duas ou mais fontes, que serão carregadas de acordo com a prioridade estabelecida. Assim, se o usuário não possuir a primeira fonte declarada, o sistema tentará carregar a próxima fonte listada. Apesar disso, não é recomendado utilizar fontes incomuns.

Outra propriedade digna de nota é a _font-size_, que altera o tamanho do texto. Em geral, os valores de _font-size_ são inseridos em _pixels_ (ex.: 12px), mas existem outras unidades de medida que podem ser utilizadas, como “em”, “rem”, valores percentuais, entre outros.

Há, ainda, outras propriedades, como _font-style, font-variant, font-weight_ e _font-stretch_. _Font-style_ permite a inserção de texto em itálico. Ela é menos utilizada por trazer o mesmo efeito que as _tags_ <i> e <em>. A _font-variant_ permite variações na fonte usada, como deixar o texto em maiúsculo e com um tamanho menor. Já a propriedade _font-weight_ com valor _bold_ aplica um efeito parecido às _tags_ <b> e <_strong>_, entretanto, essa propriedade permite definir o “peso” da fonte, ou seja, definir quão finos ou grossos serão os caracteres, podendo-se utilizar nomes como normal, _bold_, _bolder_ e _lighter_ ou valores numéricos, que vão de 100 a 900. A propriedade _font_-_stretch_ altera o espaçamento entre caracteres.

______

**📝 Exemplificando**

A seguir, veja um exemplo de implementação das propriedades de fonte. Nele, serão utilizadas as classes para se explorar uma série de propriedades CSS para formatação de fontes.

[![](https://ampli-images.s3.amazonaws.com/production/030235f9-de55-4a9e-84ae-6cdc33f8c733/original)](https://ampli-images.s3.amazonaws.com/production/030235f9-de55-4a9e-84ae-6cdc33f8c733/original)

[![](https://ampli-images.s3.amazonaws.com/production/fe71ba88-2c82-4467-aa06-bca810c981bc/original)](https://ampli-images.s3.amazonaws.com/production/fe71ba88-2c82-4467-aa06-bca810c981bc/original)

Index.html. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/c6f8e26f-10fa-4615-9e78-1273a73c9eb6/original)](https://ampli-images.s3.amazonaws.com/production/c6f8e26f-10fa-4615-9e78-1273a73c9eb6/original)

[![](https://ampli-images.s3.amazonaws.com/production/d1f2f62f-83d5-40c4-8b05-574663110ab8/original)](https://ampli-images.s3.amazonaws.com/production/d1f2f62f-83d5-40c4-8b05-574663110ab8/original)

Estilo.css. Fonte: Elaborado pelo autor.

O resultado do código pode ser visto na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/0d44c18d-bc6e-476b-a5ce-f10225baaceb/original)](https://ampli-images.s3.amazonaws.com/production/0d44c18d-bc6e-476b-a5ce-f10225baaceb/original)

Propriedades de fontes. Fonte: Elaborado pelo autor.

# **Formatação de alinhamento**

[![](https://ampli-images.s3.amazonaws.com/production/75d5b417-f863-47a0-9ad0-048f9a2fb40e/original)](https://ampli-images.s3.amazonaws.com/production/75d5b417-f863-47a0-9ad0-048f9a2fb40e/original)

A propriedade responsável por configurar o alinhamento do texto é _text-alig_n. As propriedades de formatação de texto (_text-*_) se estendem às funcionalidades das propriedades de fontes (_font-_*). Há diversas propriedades de formatação de textos, e a propriedade _text-align_ pode receber os seguintes valores:

- _left_: alinha à esquerda (valor padrão);
- _right_: alinha à direita;
- _center_: alinha ao centro;
- _justify_: alinha o texto justificado;
- _inherit_: herda o valor do alinhamento do elemento pai.

No exemplo a seguir, vamos explorar as propriedades de alinhamento usando classes. Observe as figuras a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/ac9bbc40-bf56-4c6c-ad16-efdece006fc6/original)](https://ampli-images.s3.amazonaws.com/production/ac9bbc40-bf56-4c6c-ad16-efdece006fc6/original)

estilo.css – propriedade de alinhamento utilizando classes. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/c8a60640-4c4a-4467-b9e8-48b4d8be2be0/original)](https://ampli-images.s3.amazonaws.com/production/c8a60640-4c4a-4467-b9e8-48b4d8be2be0/original)

HTML. Fonte: Elaborado pelo autor.

O exemplo gerará a seguinte página:

[![](https://ampli-images.s3.amazonaws.com/production/f352b2b0-f7f8-4bb1-9255-7b077ba49887/original)](https://ampli-images.s3.amazonaws.com/production/f352b2b0-f7f8-4bb1-9255-7b077ba49887/original)

Alinhamento do texto. Fonte: Elaborado pelo autor.

# **Cores**

[![](https://ampli-images.s3.amazonaws.com/production/78c9e59e-b101-49af-86d0-989f8dccd4f5/original)](https://ampli-images.s3.amazonaws.com/production/78c9e59e-b101-49af-86d0-989f8dccd4f5/original)

Anteriormente, apresentamos a propriedade _color_, que altera a cor da fonte, e vimos que ela pode receber os nomes das cores em inglês: _red_ (vermelho), _green_ (verde), _blue_ (azul) etc. Entretanto, existem métodos melhores para definição de cores, usando-se, por exemplo, diferentes sistemas de cores. Podemos alterar cores utilizando as seguintes propriedades (MAUJOR, 2016):

- código hexadecimal: \#ffc6d9.
- código rgb: rgb(255,235,0).
- código rgba: rgb(255,235,0, 0.7).
- código hsl: hsl(210,100%,40%).
- código hsla: hsla(155,80%,35%,0.4).
- palavra-chave: _red, blue, green,_ etc.
- transparente: _transparent_.

Em páginas web, o sistema mais utilizado é o código hexadecimal. Esse sistema é composto por um código de seis dígitos iniciado por “#” (não confunda com os IDs, pois códigos hexadecimais devem ser escritos entre aspas). Os dígitos podem variar de 0-9ABCDEF, em que a letra A representa o número 10, a letra B representa o número 11, a letra C representa o número 12, a letra D representa o número 13, a letra E representa o número 14 e a letra F representa o número 15. Como na cor “\#FF0000”: os dois primeiros dígitos representam a quantidade de vermelho (“FF” representa a quantidade máxima), os dois seguintes representam a quantidade de verde e os dois últimos representam a quantidade de azul (“00” é o valor mínimo). Logo, pode-se concluir que “#FF0000” é o código da cor vermelha.

______

**⭐ Dica**

Acesse o site _Adobe Color_ e use a paleta de cores para selecionar uma cor. A figura abaixo mostra o código hexadecimal da cor e de outras cores que harmonizam com a cor selecionada.

[![](https://ampli-images.s3.amazonaws.com/production/9251b574-70ec-4a87-bf14-c5ea1a8ad6a6/original)](https://ampli-images.s3.amazonaws.com/production/9251b574-70ec-4a87-bf14-c5ea1a8ad6a6/original)

Ferramenta de seleção de cores da Adobe. Fonte: Adobe Color.

A ferramenta de seleção de cores da Adobe é bastante popular entre profissionais da área de web design.

Você não precisa memorizar os códigos hexadecimais. Sempre que precisar escolher uma cor, você pode consultar na web ferramentas que ajudem a selecionar cores HTML para o padrão hexadecimal de cores.

# **Propriedades background em CSS**

[![](https://ampli-images.s3.amazonaws.com/production/62122eb0-d1db-4908-8ed3-d01bf40d5883/original)](https://ampli-images.s3.amazonaws.com/production/62122eb0-d1db-4908-8ed3-d01bf40d5883/original)

As propriedades de _background_ permitem alterar o plano de fundo, alterando as cores ou até mesmo inserindo figuras. Elas são iniciadas com “_background_-*”.

A seguir, veja um exemplo de uso das propriedades que alteram a cor do fundo de uma página; uma propriedade bastante utilizada é a _**background-color**_. Observe os códigos index.html e o estilo.css a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/1010f1f7-031b-45d7-baf0-d86f85eafc9b/original)](https://ampli-images.s3.amazonaws.com/production/1010f1f7-031b-45d7-baf0-d86f85eafc9b/original)

index.html – aplicando ao html a propriedade background-color. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/94e83994-298f-4a0b-9bd9-e76808488c17/original)](https://ampli-images.s3.amazonaws.com/production/94e83994-298f-4a0b-9bd9-e76808488c17/original)

estilo.css - propriedade background-color. Fonte: Elaborado pelo autor.

O código apresentado gerará a página ilustrada a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/6b22fd4a-58b7-4142-92c6-cf1537494ba6/original)](https://ampli-images.s3.amazonaws.com/production/6b22fd4a-58b7-4142-92c6-cf1537494ba6/original)

Alterando a cor de fundo para preto e do texto para branco. Fonte: Elaborado pelo autor.

Ao se alterar a cor de fundo, a cor das fontes deve contrastar com ela. Logo, se alterou a cor do fundo para preto, a cor da fonte deve ser oposta. Entretanto, não é recomendado usar cores escuras como cor de fundo.

# **Imagens como plano de fundo**

[![](https://ampli-images.s3.amazonaws.com/production/ee6008bf-08e5-4425-85d9-5762ae5e7225/original)](https://ampli-images.s3.amazonaws.com/production/ee6008bf-08e5-4425-85d9-5762ae5e7225/original)

CSS possibilita, ainda, usar uma imagem como plano de fundo. Para isso, você pode utilizar a propriedade _**background-image**_. Nesse caso, o nome da imagem deve ser passado entre o valor url (“NOME-DA-IMAGEM.extensão”).

______

**📝 Exemplificando**

Como utilizamos imagens como planos de fundo? Vamos a um exemplo!!

[![](https://ampli-images.s3.amazonaws.com/production/d50ba685-5fb2-49d0-8ddf-d37a406af6d0/original)](https://ampli-images.s3.amazonaws.com/production/d50ba685-5fb2-49d0-8ddf-d37a406af6d0/original)

index.html. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/a3d008d9-2703-4b45-9586-085cebea3e74/original)](https://ampli-images.s3.amazonaws.com/production/a3d008d9-2703-4b45-9586-085cebea3e74/original)

estilo.css – imagem de fundo. Fonte: Elaborado pelo autor.

Nesse caso, a imagem denominada “imagem_fundo.jpg” será inserida como imagem de _background_ da _tag <body>_ (figura abaixo). Perceba que ao se usar a propriedade _background-image_, é possível adicionar textos sobre a imagem, o que não é permitido por padrão ao usar uma imagem usando a _tag_ <img>.

[![](https://ampli-images.s3.amazonaws.com/production/327ede2f-67ba-4e95-baa2-113aca808152/original)](https://ampli-images.s3.amazonaws.com/production/327ede2f-67ba-4e95-baa2-113aca808152/original)

Inserindo uma imagem de background. Fonte: Pixabay.

Observe que, nesse caso, uma propriedade adicional foi inserida: _background-size_, que determina o tamanho da imagem de fundo (nesse caso, 100%). Atente-se, ainda, à extensão da imagem “.jpg”. Muitos erros cometidos ao inserir imagens de fundo ocorrem devido à inserção incorreta da extensão da imagem. Note, também, que a imagem deve estar localizada no mesmo diretório do arquivo “index.html”. Caso não esteja, a imagem não será reconhecida.

No figura abaixo, ilustramos uma série de propriedades utilizadas para configurar o plano de fundo (_background_):

[![](https://ampli-images.s3.amazonaws.com/production/b9003ea3-2843-4f58-a95c-7dd7e5be4d19/original)](https://ampli-images.s3.amazonaws.com/production/b9003ea3-2843-4f58-a95c-7dd7e5be4d19/original)

Propriedades CSS para background. Fonte: adaptado de W3Schools ([s.d.]).

**💭 Reflita**

Suponha que você aplique as propriedades _background-image_ e _background-color_ a um mesmo seletor. Qual propriedade terá prioridade?

______

**➕ Pesquise mais**

**O DINOSSAURO DAS CSS**

O engenheiro carioca Maurício Samy Silva ou, simplesmente, Maujor, aposentou-se no ano de 1999, quando resolveu se aventurar no mundo do desenvolvimento web. Em seu site pessoal, Maujor começou a escrever artigos em língua portuguesa que explicavam conceitos de CSS.

O engenheiro carioca Maurício Samy Silva ou, simplesmente, Maujor, aposentou-se no ano de 1999, quando resolveu se aventurar no mundo do desenvolvimento web. Em seu site pessoal, Maujor começou a escrever artigos em língua portuguesa que explicavam conceitos de CSS.

Por ter sido um pioneiro na divulgação da linguagem CSS no Brasil, seus tutoriais estavam sempre indexados em ferramentas de busca (i.e., Google). Mas o que fez dele a grande referência brasileira quanto a folhas de estilo foi o efeito CSS, que exibia um dinossauro ao passar o mouse sobre os _links_ (efeito que foi, infelizmente, removido das versões mais recentes do seu site). Ele se autointitula: “o dinossauro das CSS”. Com bom humor e uma linguagem simples, o site do Maujor, até hoje, é considerado uma referência na área, contendo uma série de especificações de propriedades CSS. Por exemplo, veja o tutorial de CSS moderno “explicado para dinossauros”:

MAUJOR. **CSS moderno explicado para dinossauros**. 2016.

______

Nesta aula, você aprendeu os fundamentos da linguagem CSS; nas próximas aulas, você aprenderá as propriedades referentes aos espaçamentos de elementos HTML.

Até lá!

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)](https://ampli-images.s3.amazonaws.com/production/c40ee967-950e-497e-b99e-8d606638543e/original)

Como garantir que fontes externas de uma página sejam exibidas corretamente em todos os computadores?

A incorporação de fontes externas possibilita que sua página seja corretamente exibida em computadores que não possuam as fontes desejadas instaladas. O @_font-face_ permite que uma fonte externa possa ser incorporada a uma página HTML.

O que aconteceu é que a fonte utilizada não estava instalada no computador em que o site foi visualizado. Para solucionar esse problema, pode-se utilizar a diretiva @_font-face_.

Essa diretiva do CSS permite que você insira uma fonte diretamente no código fonte de um site.

- Passo 1 - baixando a fonte: acesse o site Google Fonts e faça o _download_ do arquivo “Roboto.zip”.
- Passo 2 - abra o arquivo com algum programa de extração de arquivos compactados (recomendamos o WinRar).

[![](https://ampli-images.s3.amazonaws.com/production/a2a7645e-a557-4d92-837e-234921a45cc8/original)](https://ampli-images.s3.amazonaws.com/production/a2a7645e-a557-4d92-837e-234921a45cc8/original)

Conteúdo do arquivo Roboto.zip. Fonte: Captura de tela do programa de descompactação de arquivos elaborado pelo autor.

- Passo 3 - extraindo os arquivos. Vamos utilizar apenas o arquivo “Roboto-Regular.tff”.

Copie esse arquivo e cole no mesmo diretório do seu site.

- Passo 4 - adicione o seguinte código no arquivo “estilo.css”:

[![](https://ampli-images.s3.amazonaws.com/production/96bf0aaa-eed4-40ea-9d52-a9d566669eea/original)](https://ampli-images.s3.amazonaws.com/production/96bf0aaa-eed4-40ea-9d52-a9d566669eea/original)

O @_font-face_ permite que uma fonte externa possa ser incorporada a uma página HTML. A incorporação de fontes externas possibilita que sua página seja corretamente exibida em computadores que não possuam as fontes desejadas instaladas.

[![](https://ampli-images.s3.amazonaws.com/production/f9f26313-d53f-4e6b-a535-3ec88596c771/original)](https://ampli-images.s3.amazonaws.com/production/f9f26313-d53f-4e6b-a535-3ec88596c771/original)

Página com a fonte externa carregada. Fonte: Elaborado pelo autor.