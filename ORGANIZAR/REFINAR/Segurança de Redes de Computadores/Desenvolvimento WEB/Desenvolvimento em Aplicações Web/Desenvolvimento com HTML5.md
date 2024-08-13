# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/3a7eef83-d147-4add-8371-d37de04f7504/original)](https://ampli-images.s3.amazonaws.com/production/3a7eef83-d147-4add-8371-d37de04f7504/original)

### **Qual é o foco da aula?**

Nesta aula, você irá aprender sobre estruturas de páginas HTML.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- transcrever novas _tags_ para aprimorar websites;
- empregar listas e _link_ que conectam páginas;
- usar _iframes_ que adicionam conteúdo externo a uma página.

**Situação-problema**

Olá! Nesta aula, você conhecerá algumas _tags_ utilizadas para se determinar a estrutura de páginas HTML. _Tags_ estruturais agem como containers que delimitam o posicionamento de elementos em páginas. A partir delas, é possível determinar a forma e o posicionamento de cada elemento em um documento web.

A _tag_ estrutural mais utilizada é a div. Essa _tag_ cria um container que permite a aplicação de propriedades de estilo a todas as outras _tags_ posicionadas dentro do bloco. Entretanto, HTML5 trouxe uma série de novas _tags_ que adicionam semântica à estrutura das páginas, apesar de, na prática, possuírem a mesma funcionalidade que a _tag_ div. São exemplos dessas tags estruturais HTML: _section, header, footer, nav, article e aside_.

Além disso, você conhecerá novas _tags_ para aprimorar a tipografia de seus websites usando elementos _inline_, como adicionar textos em negrito, itálico e sublinhado. Você aprenderá, ainda, a criar listas ordenadas e não ordenadas, a inserir links que conectam sua página a outros endereços, a criar _iframes_ que adicionam conteúdo externo a sua página e a adicionar mídias, como imagens, áudios e vídeos, usando HTML5.

Por fim, você será introduzido ao conceito de _design_ responsivo. Responsividade é um conceito recente, que prevê que páginas se comportem de maneira distinta, a depender do dispositivo utilizado para acesso. Por exemplo, um mesmo site responsivo acessado por um _smartphone_, um _table_t e um _noteboo_k deverá apresentar três distintas interfaces, de forma que facilitem a interação dos usuários. Mas não se preocupe com a implementação disso agora.

O importante é que você compreenda os conceitos envolvidos. A responsividade depende de componentes relacionados a folhas de estilo (que veremos nas próximas aulas).

Nesta aula, você será apresentado a uma série de novas _tags_ HTML, por isso, é importante que pratique o que aprender. Reproduza os exemplos apresentados em seu computador e verifique a execução em diferentes navegadores.

Agora, imagine que você acaba de ser contratado para realizar um estágio em uma empresa que vende planos de internet. Em seu primeiro dia de trabalho, seu chefe lhe apresentou as funções que desempenhará. Uma delas envolve prestar manutenção no código-fonte do site de vendas da empresa.

A página de vendas possui, atualmente, um problema relacionado à configuração do _layout_. Um estagiário que também trabalha na empresa era o responsável pela página, entretanto, por algum descuido, enquanto alterava o código-fonte para alteração de preços do site, acabou desconfigurando a estrutura da página.

Veja como a página se encontra atualmente:

[![](https://ampli-images.s3.amazonaws.com/production/a582d751-1b94-4755-a7e0-ea6453761f68/original)](https://ampli-images.s3.amazonaws.com/production/a582d751-1b94-4755-a7e0-ea6453761f68/original)

Estrutura da página. Fonte: Elaborado pelo autor.

Infelizmente, o estagiário teve que se ausentar do trabalho hoje. A cada segundo que a página fica desconfigurada, a empresa perde possíveis vendas. Então, cabe a você corrigir o problema.

Para isso, você deve, inicialmente, observar o código-fonte:

[![](https://ampli-images.s3.amazonaws.com/production/dbf7c11e-6310-4f94-9e37-0cbc4bde27cb/original)](https://ampli-images.s3.amazonaws.com/production/dbf7c11e-6310-4f94-9e37-0cbc4bde27cb/original)

[![](https://ampli-images.s3.amazonaws.com/production/3012a16a-9e81-4b40-8399-09a5ec5f9b04/original)](https://ampli-images.s3.amazonaws.com/production/3012a16a-9e81-4b40-8399-09a5ec5f9b04/original)

Código-fonte. Fonte: Elaborado pelo autor.

Supondo que você não tenha conhecimento das folhas de estilo utilizadas e faça alterações apenas nos códigos HTML, descreva os passos para a resolução do problema.

Pronto para mergulhar a fundo no mundo do desenvolvimento web com HTML5?

Então, vamos lá!

# **Conceito-chave**

[![](https://ampli-images.s3.amazonaws.com/production/c57a12cf-b2a6-4e0f-9a92-536d6ba12f7a/original)](https://ampli-images.s3.amazonaws.com/production/c57a12cf-b2a6-4e0f-9a92-536d6ba12f7a/original)

Para desenvolver websites usando HTML, é importante conhecer as _tags_ de marcação disponíveis. Entretanto, HTML possui um total de mais de 100 elementos de _tags_ definidos na especificação (SILVA, 2018). É claro que não é necessário decorar todas as _tags_, porém é importante conhecer algumas das principais.

Anteriormente, foram apresentadas as _tags_ de definição do documento (html, _head, body_), as _tags_ do cabeçalho do documento (_title_ e _meta_) e as _tags_ relacionadas à inserção de parágrafos (p) e títulos (h1 a h6). Outras _tags_ importantes são as _tags_ estruturais, que são utilizadas para organizar a estrutura de uma página, uma vez que, ao se construir um website, é preciso que determinados elementos fiquem acoplados em posições específicas.

A figura abaixo ilustra um exemplo de estrutura de uma página web. Observe as divisões e os posicionamentos enumerados na página.

[![](https://ampli-images.s3.amazonaws.com/production/34e9cc7b-effb-4141-96ef-3bfa181a95a9/original)](https://ampli-images.s3.amazonaws.com/production/34e9cc7b-effb-4141-96ef-3bfa181a95a9/original)

Exemplo de organização em um site. Há três seções visualmente identificáveis: (1) artigo principal; (2) quatro blocos de artigos secundários (abaixo do principal); e (3) bloco lateral esquerdo com uma lista de textos secundários. Fonte: Elaborado pelo autor.

A princípio, pode ser difícil perceber, mas cada bloco de conteúdo da página está organizado em blocos de códigos (containers) cercados por uma _tag_ HTML, conforme pode ser visto na figura acima. Esses blocos, por sua vez, estão organizados dentro de outros blocos, de forma a construir uma estrutura física para o conteúdo da página. Cada um desses containers, embora não apareça no exemplo, pode ser visualizado se se aplicar os códigos de estilo).

Geralmente, o espaço ocupado pelo conteúdo é delimitado de maneira quadrangular. Observe, na figura a seguir, as possíveis posições das _tags_ estruturais. Perceba que as seções 1 e 2 (_Artigos_) fazem parte de um container maior localizado ao lado da seção 3 (_News_).

[![](https://ampli-images.s3.amazonaws.com/production/9915be7f-34f0-4717-9d83-6448493ade9c/original)](https://ampli-images.s3.amazonaws.com/production/9915be7f-34f0-4717-9d83-6448493ade9c/original)

Delimitação da posição de containers usados na organização de um site. Fonte: Elaborado pelo autor.

Observe, na figura acima, a primeira linha pontilhada (primeiro container), que delimita todo o conteúdo da página. Dentro desse container, temos dois outros containers, que dividem a página em uma seção principal (tópicos 1 e 2, à esquerda) e um menu secundário (tópico 3, à direita). Os textos em _News_ (tópico 3) foram inseridos linearmente, logo, não é necessário adicionar _tags_ estruturais para cada um deles. Por padrão, HTML insere novos elementos abaixo de outros elementos.

A figura acima, na caixa à esquerda, apresenta a seção _Artigos_, em que novas divisórias foram inseridas (representadas pelos retângulos azuis). A primeira delas foi dividida em duas partes. A seguir, um novo bloco foi dividido em quatro containers, que, por sua vez, são divididos em duas partes (imagem/texto). Nesse caso, foi aplicada uma propriedade para que os quatro containers que representam artigos sejam alocados lado a lado, sendo cada um adicionado em seu próprio container.

Cada um desses containers possui uma _tag_ composta, que deve ser corretamente posicionada dentro ou ao lado de outras _tags_. Caso uma dessas _tags_ compostas não seja corretamente fechada, a estrutura da página pode ser corrompida, causando danos no _layout_ do site, como o problema apresentado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/6515c69f-de4e-4727-ab06-b8e739c8856f/original)](https://ampli-images.s3.amazonaws.com/production/6515c69f-de4e-4727-ab06-b8e739c8856f/original)

Estrutura da página corrompida devido a uma tag não fechada. Elaborado pelo autor.

Nesse caso, apenas uma _tag_ em um dos containers não foi fechada, desconfigurando completamente a estrutura da página. Esse é considerado um dos erros mais comuns em programação web e, mesmo assim, ainda pode ser um erro difícil de solucionar, isso porque, em páginas muito grandes, uma _tag_ incorretamente fechada pode ser difícil de ser detectada. Por isso, é sempre importante indentar corretamente o seu código.

______

**📝 Exemplificando**

O código a seguir apresenta um erro que corrompe a estrutura da página. **Você conseguiria dizer onde está o erro?**

[![](https://ampli-images.s3.amazonaws.com/production/4e711a84-07a8-4989-b900-1f24bd55d814/original)](https://ampli-images.s3.amazonaws.com/production/4e711a84-07a8-4989-b900-1f24bd55d814/original)

Código com erro. Fonte: Elaborado pelo autor.

Provavelmente não, pois o código não está corretamente indentado.

Agora, vamos apresentar esse mesmo código indentado. Observe, a seguir, como os blocos de _tags_ compostas estão organizados. A maioria dos editores de código inclui marcadores e linhas que delimitam as declarações de abertura e fechamento de _tags_, logo, observe que o erro pode ser facilmente encontrado: **há uma** _**tag**_ **não fechada na linha 19**.

[![](https://ampli-images.s3.amazonaws.com/production/4c12376c-94ee-49f5-a43c-9fdb6cef70a5/original)](https://ampli-images.s3.amazonaws.com/production/4c12376c-94ee-49f5-a43c-9fdb6cef70a5/original)

Código indentado. Fonte: Elaborado pelo autor.

# **Novidades do HTML5**

[![](https://ampli-images.s3.amazonaws.com/production/f9a2880d-2418-425b-b73e-89f7731bc5d2/original)](https://ampli-images.s3.amazonaws.com/production/f9a2880d-2418-425b-b73e-89f7731bc5d2/original)

Em versões anteriores do HTML, em geral, utiliza-se a _tag_ <div> para construção de containers genéricos. HTML5 trouxe uma série de _tags_ específicas para cada seção da página, como <_article_> para inserção de artigos, <_header_> para o cabeçalho, <nav> para o menu de navegação, entre outras (figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/f662d6cf-7918-4db6-a8c0-321b18cd18ac/original)](https://ampli-images.s3.amazonaws.com/production/f662d6cf-7918-4db6-a8c0-321b18cd18ac/original)

[![](https://ampli-images.s3.amazonaws.com/production/6fd099fe-4949-40d7-82d4-265e8ff4e062/original)](https://ampli-images.s3.amazonaws.com/production/6fd099fe-4949-40d7-82d4-265e8ff4e062/original)

Tags estruturais do HTML5. Fonte: Adaptado de Mariano (2020); W3C (2012).

Na prática, as _tags_ estruturais em HTML têm funcionalidade idêntica; o que as diferencia é o contexto em que são aplicadas. Por exemplo: a _tag_ <_article_> foi construída para armazenar conteúdos de artigos, entretanto, nada impede o desenvolvedor de usar uma _tag_ <div> com o mesmo propósito. HTML5 ainda permite o uso da _tag_ <div>, que é utilizada na maioria dos casos pelos desenvolvedores mais antigos.

______

**📝 Exemplificando**

Observe como a figura anterior seria estruturada em um documento HTML (preste atenção nos níveis de indentação):

[![](https://ampli-images.s3.amazonaws.com/production/1a106dd5-9fc0-46a4-869a-4cf7e27beace/original)](https://ampli-images.s3.amazonaws.com/production/1a106dd5-9fc0-46a4-869a-4cf7e27beace/original)

Estruturação em documento HTML. Fonte: Elaborado pelo autor.

Entretanto, ao implementar esse código, você não verá nada no navegador, uma vez que _tags_ estruturais apenas delimitam o posicionamento em que os itens serão inseridos. Você poderá visualizá-los quando implementar regras de estilo com CSS.

______

A figura abaixo ilustra um exemplo de implementação dessas _tags_ para se estruturar uma página HTML.

[![](https://ampli-images.s3.amazonaws.com/production/535aa24e-f491-4adf-ad24-7dba1d531a01/original)](https://ampli-images.s3.amazonaws.com/production/535aa24e-f491-4adf-ad24-7dba1d531a01/original)

Exemplo de uso de tags estruturais em uma página HTML. Fonte: Mariano; de Melo-Minardi (2017, p. 93).

Nesse exemplo, vemos que a _tag_ <_header_> é usada para delimitar a região do cabeçalho da página (não confunda com o cabeçalho do documento, que apenas mantém os metadados da página e, portanto, não é exibido). Dentro da _tag_ <_header_> está a _tag_ <nav>, utilizada para armazenar menus de navegação. Observe que poderia ser utilizada a _tag_ <_menu_>, a depender do contexto, ou, ainda, inverter a ordem em que <_header_> e <nav> estão descritas.

A seguir, uma <div> delimitará todo o conteúdo central de uma página (figura: Tags estruturais do HTML5). Em geral, essa seção é utilizada para carregar elementos dinâmicos (i.e., elementos que serão alterados em diferentes páginas). Esse container, então, é dividido em duas colunas: (1) <a_rticle_>, região em que será adicionado o texto e que ocupa a maior parte do espaço da div; e (2) <_aside_>, que receberá menus laterais e, portanto, possui uma largura menor.

Dentro de <_article_>, pode-se inserir _tags_ do tipo <_section_>, a fim de se categorizar o conteúdo e facilitar a navegação em páginas muito grandes; por fim, o <_footer_>, também conhecido como rodapé, recebe informações complementares, que, em geral, são repetidas em todas as páginas.

______

**💭 Reflita**

Em versões anteriores ao HTML 4, desenvolvedores costumavam utilizar tabelas para organizar a estrutura da página; hoje em dia, essa prática foi completamente abandonada devido à criação de _tags_ específicas para diversas seções de documentos web.

Você consegue imaginar os motivos que levaram à criação de _tags_ específicas para a estruturação de uma página?

# **Formatação avançada de textos e outros elementos INLINE**

[![](https://ampli-images.s3.amazonaws.com/production/c5a85d60-bfc8-4020-a21d-0bfb77ecd5bc/original)](https://ampli-images.s3.amazonaws.com/production/c5a85d60-bfc8-4020-a21d-0bfb77ecd5bc/original)

Vimos, anteriormente, que a _tag_ <p> permite a inserção de simples estruturas de parágrafos, enquanto as _tags_  <h1> a <h6> permitem a inserção de títulos. Entretanto, a escrita de textos requer uma gama maior de funcionalidades, como adição de trechos em destaque: uso de negrito, itálico e sublinhado (figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/9d3cdd03-544a-4ba7-8c15-c18ebf6c3217/original)](https://ampli-images.s3.amazonaws.com/production/9d3cdd03-544a-4ba7-8c15-c18ebf6c3217/original)

[![](https://ampli-images.s3.amazonaws.com/production/f0006a05-e6f4-4892-be64-27f2a6b97d5f/original)](https://ampli-images.s3.amazonaws.com/production/f0006a05-e6f4-4892-be64-27f2a6b97d5f/original)

Formatação avançada de texto e outros elementos HTML5. Fonte: Adaptado de Mariano (2020); W3C (2012).

Crie um arquivo HTML contendo o código a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/e1ed968e-6fe8-4f25-9ca8-f647ed5d17e0/original)](https://ampli-images.s3.amazonaws.com/production/e1ed968e-6fe8-4f25-9ca8-f647ed5d17e0/original)

Código para criação de arquivo HTML. Fonte: Elaborado pelo autor.

A seguir, abra o arquivo em um navegador; assim, você terá a página da figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/6e96a4b0-03e6-4a0c-8e39-0c6add1aefb5/original)](https://ampli-images.s3.amazonaws.com/production/6e96a4b0-03e6-4a0c-8e39-0c6add1aefb5/original)

Estilos de texto. Fonte: Captura de tela do index.html elaborada pelo autor.

Observe que a _tag_ <_span_> não insere qualquer informação perceptível na página (linha 8 do código acima). Trata-se de uma _tag_ container usada, preferencialmente, para delimitar textos. Em geral, HTML insere novos elementos, um abaixo do outro, entretanto, todas as _tags_ inseridas dentro de <span> são adicionadas na mesma linha. Por esse motivo, são denominadas _tags inline_.

Perceba que as _tags_ <b> e <_strong_> têm o mesmo efeito no texto: a inserção de negrito (linhas 9-10); da mesma forma, <i> e  <em> alteram o texto para itálico (linhas 11-12). Apesar de terem efeitos práticos similares, o motivo de uso dessas _tags_ deve estar relacionado ao contexto empregado. Em geral,  <_strong_> e <em> são indicados para inserção de ênfase, enquanto <b> e <i> são as _tags_ tradicionais usadas para configuração de negrito e itálico.

Outro recurso textual do HTML é o que corresponde à inserção de listas, que podem ser ordenadas (ol) ou não ordenadas (ul). Observe a implementação de listas a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/bf5feb97-f4cf-4d85-a83b-e24f3252a3c4/original)](https://ampli-images.s3.amazonaws.com/production/bf5feb97-f4cf-4d85-a83b-e24f3252a3c4/original)

Inserção de listas. Fonte: Elaborado pelo autor.

Teste em seu navegador para visualizar a saída das listas.

[![](https://ampli-images.s3.amazonaws.com/production/f75c7cf9-1111-4841-b546-a48dea18d4a9/original)](https://ampli-images.s3.amazonaws.com/production/f75c7cf9-1111-4841-b546-a48dea18d4a9/original)

Listas em HTML. Fonte: Captura de tela do index.html elaborada pelo autor.

Ambos os tipos de lista têm o mesmo método para inserção de itens: a _tag_ <li>. Observe que a lista não ordenada insere apenas um ponto (_bullet_) antes do item, já a lista ordenada insere um numeral.

A tag <pre> é utilizada para representar um texto pré-formatado. Observe, a seguir, a comparação de um texto inserido com a _tag_ <p> e um texto inserido com a _tag_ <pre>. A figura abaixo ilustra os exemplos de saída utilizando as _tags_ <p>Texto normal</p><pre>Texto pre</pre>.

[![](https://ampli-images.s3.amazonaws.com/production/f00c8c38-16b2-4156-a927-69af29e07bb3/original)](https://ampli-images.s3.amazonaws.com/production/f00c8c38-16b2-4156-a927-69af29e07bb3/original)

Comparação de tags: <p>Texto normal</p><pre>Texto pre</pre>. Fonte: Captura de tela do index.html elaborada pelo autor.

Uma outra _tag_ que vale a pena mencionar é <_style_>. Essa _tag_ permite alterar os estilos da página, que serão abordados com maior intensidade quando falarmos sobre folhas de estilo em cascata (CSS). Entretanto, aqui, apresentaremos um breve uso dessa _tag_ sem entrar em detalhes.

O código a seguir reproduz a figura acima com a cor de fundo vermelha. Essa configuração foi feita usando-se a propriedade CSS _backgroung-color_ com o valor _red_ (vermelho em inglês) aplicada à _tag_ _body_.

[![](https://ampli-images.s3.amazonaws.com/production/9e6dde4d-edbe-4cdc-9b02-3504259f93ef/original)](https://ampli-images.s3.amazonaws.com/production/9e6dde4d-edbe-4cdc-9b02-3504259f93ef/original)

Reprodução da figura “Comparação de tags: <p>Texto normal</p><pre>Texto pre</pre>” com fundo vermelho. Fonte: Elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/9b8c216a-22a2-427e-baab-328627b187c9/original)](https://ampli-images.s3.amazonaws.com/production/9b8c216a-22a2-427e-baab-328627b187c9/original)

Fundo (background) do corpo da página (body) na cor vermelha (red). Captura de tela do index.html elaborada pelo autor.

A _tag_ <_style_> permite a inserção de códigos CSS diretamente no código fonte HTML, no entanto, o seu uso não é muito recomendado, uma vez que o ideal é separar os códigos de estilo em arquivos diferentes. (Detalhes sobre os códigos apresentados dentro de <_style_> serão apresentados em outra oportunidade.)

# **Links em HTML**

[![](https://ampli-images.s3.amazonaws.com/production/2cf5be31-1793-43ce-a4af-3347548ca947/original)](https://ampli-images.s3.amazonaws.com/production/2cf5be31-1793-43ce-a4af-3347548ca947/original)

A tag <a> é um elemento do tipo _inline_ que permite a inserção de _links_ para outras páginas (SILVA, 2018). Por padrão, o texto em um _link_ é exibido sublinhado e na cor azul, entretanto, essas configurações podem ser alteradas usando-se folhas de estilos.

Um _link_ recebe, no atributo href, o endereço ao qual será direcionado. Além disso, _link_s podem ser absolutos ou relativos. Os _links_ absolutos informam o endereço completo do item a ser acessado. Observe um exemplo de _link_ absoluto:

[![](https://ampli-images.s3.amazonaws.com/production/b670dfe3-4b9f-425f-89d5-498d440e38c4/original)](https://ampli-images.s3.amazonaws.com/production/b670dfe3-4b9f-425f-89d5-498d440e38c4/original)

Os _**links**_ **relativos** devem levar em consideração a posição do arquivo que se deseja acessar. Por exemplo: se o arquivo que deseja está na “_public/views_”, você deve acessá-lo desta forma (figura abaixo):

[![](https://ampli-images.s3.amazonaws.com/production/85d084a1-b6d9-486b-a2fb-46801e8ae551/original)](https://ampli-images.s3.amazonaws.com/production/85d084a1-b6d9-486b-a2fb-46801e8ae551/original)

Criando um link para uma página secundária usando Sublime Text. Fonte: Captura de tela do Sublime Text elaborada pelo autor.

Caso queira criar um _link_ desse outro arquivo, indique que o arquivo se encontra duas pastas antes. Para isso, use a seguinte estrutura:

[![](https://ampli-images.s3.amazonaws.com/production/e38e407c-5069-4960-827d-09f07e08444e/original)](https://ampli-images.s3.amazonaws.com/production/e38e407c-5069-4960-827d-09f07e08444e/original)

Sendo que cada “..” indica que está retornando a uma pasta anterior.

Para abrir o _link_ em uma nova página, use o atributo _target="_blank"_:

[![](https://ampli-images.s3.amazonaws.com/production/2e87a057-0493-49c5-bc90-3603140245db/original)](https://ampli-images.s3.amazonaws.com/production/2e87a057-0493-49c5-bc90-3603140245db/original)

**⚠️ Atenção**

**Não confunda a** _**tag**_ **<a> com a** _**tag <link**_**>!**

A _tag_ <a> cria ligações para outros locais, enquanto a _tag_ <_link_> cria uma ligação entre o documento atual e um conteúdo externo, como quando queremos adicionar um arquivo CSS a nossa página.

# **Imagens, áudios e vídeos**

[![](https://ampli-images.s3.amazonaws.com/production/9c4d6646-8401-4f5e-9234-60d1c9c855ab/original)](https://ampli-images.s3.amazonaws.com/production/9c4d6646-8401-4f5e-9234-60d1c9c855ab/original)

Imagens podem ser inseridas em HTML usando-se a _tag_ <_img_>. Essa _tag_ recebe o atributo src, que receberá o endereço completo da imagem. Nesse caso, as regras utilizadas para se definir o endereço são as mesmas usadas para se inserir _links_ <a>. Observe o uso da _tag_ <_img_>:

[![](https://ampli-images.s3.amazonaws.com/production/06abe2c6-6fb6-4ee8-9c47-b0d8d05b1804/original)](https://ampli-images.s3.amazonaws.com/production/06abe2c6-6fb6-4ee8-9c47-b0d8d05b1804/original)

**📝 Exemplificando**

**Exemplo simples: imagem no mesmo diretório**

No exemplo a seguir, adicionaremos uma imagem denominada “_tag_._png_” a uma página HTML (figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/618d8cc9-effb-4f87-9a12-0a24b56ba3fe/original)](https://ampli-images.s3.amazonaws.com/production/618d8cc9-effb-4f87-9a12-0a24b56ba3fe/original)

Imagem utilizada. Fonte: Captura de tela elaborada pelo autor.

Antes de inserir a imagem, é importante atentar-se à extensão da imagem utilizada. Neste caso, é usada uma imagem no formato PNG (_Portable Network Graphics_).

Se estiver usando _Windows_ e seu sistema não estiver apresentando a extensão do arquivo, clique em “Exibir” e marque a opção “Extensões e nomes de arquivos” (figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/708ac557-3bc3-4ba3-806a-209ffb24d4c3/original)](https://ampli-images.s3.amazonaws.com/production/708ac557-3bc3-4ba3-806a-209ffb24d4c3/original)

Exibindo extensões de arquivo. Fonte: Captura de tela da pasta site elaborada pelo autor.

Agora vamos inserir a imagem usando a _tag_ <_img_>:

Agora vamos inserir a imagem usando a _tag_ <_img_>:

[![](https://ampli-images.s3.amazonaws.com/production/02813dd4-c33d-48b3-9e45-6973a0dbefc8/original)](https://ampli-images.s3.amazonaws.com/production/02813dd4-c33d-48b3-9e45-6973a0dbefc8/original)

Inserindo a imagem. Fonte: Elaborado pelo autor.

Ao abrir esse arquivo no navegador, você verá a seguinte página (figura abaixo):

[![](https://ampli-images.s3.amazonaws.com/production/55256e21-ba9d-47ca-83e2-82229deabb58/original)](https://ampli-images.s3.amazonaws.com/production/55256e21-ba9d-47ca-83e2-82229deabb58/original)

Página web com a imagem. Fonte: Elaborado pelo autor.

Podemos, ainda, incluir imagens da internet em uma página web apesar de não ser uma boa prática inserir o src da imagem diretamente da internet, pois isso mantém seu site dependente de uma página, ou seja, de uma imagem hospedada em outro servidor, e isso pode deixar seu carregamento mais lento.

HTML ainda permite a inserção de arquivos de áudio e vídeo diretamente na página por meio das _tags_ <audio> e <video>, respectivamente. A seguir, mostraremos um exemplo contendo as _tags_ <audio> e <video>.

[![](https://ampli-images.s3.amazonaws.com/production/456df247-7640-4886-beac-ad676d71f401/original)](https://ampli-images.s3.amazonaws.com/production/456df247-7640-4886-beac-ad676d71f401/original)

Código contendo as tags <audio> e <video>. Fonte: Elaborado pelo autor.

Esse exemplo gera a seguinte visualização (figura abaixo):

[![](https://ampli-images.s3.amazonaws.com/production/d389e0bf-7e51-4f94-941a-cf44cee4292b/original)](https://ampli-images.s3.amazonaws.com/production/d389e0bf-7e51-4f94-941a-cf44cee4292b/original)

Inserindo áudio e vídeo. Fonte: Captura de tela da página img elaborada pelo autor.

# **IFRAMES**

[![](https://ampli-images.s3.amazonaws.com/production/bf339917-5ef9-4067-9965-fcdeda220b28/original)](https://ampli-images.s3.amazonaws.com/production/bf339917-5ef9-4067-9965-fcdeda220b28/original)

A _tag_ <_iframe_> permite a inserção de páginas externas diretamente na sua página. O uso mais comum da _tag_ <_iframe_> está na incorporação de vídeos do YouTube. Observe o exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/4830ab3b-13b2-44e8-af3a-76e5667d424b/original)](https://ampli-images.s3.amazonaws.com/production/4830ab3b-13b2-44e8-af3a-76e5667d424b/original)

Nesse exemplo, você só precisa informar o endereço do elemento que será incorporado; a partir do acesso a um servidor externo, o item será inserido e todos os componentes dele serão incluídos na sua página, sem a necessidade de se acrescentar qualquer outro código. O exemplo apresentado gera a seguinte página:

[![](https://ampli-images.s3.amazonaws.com/production/5182b6cc-4e87-4ba8-bef1-7d6906e96358/original)](https://ampli-images.s3.amazonaws.com/production/5182b6cc-4e87-4ba8-bef1-7d6906e96358/original)

Usando um iframe para carregar um vídeo do YouTube. Fonte: Captura de tela da página img elaborada pelo autor.

É possível, ainda, controlar a largura e a altura do iframe por meio dos atributos _width_ e _height_, respectivamente. Esses atributos recebem valores em _pixels_. Por exemplo:

[![](https://ampli-images.s3.amazonaws.com/production/24a94ca1-7461-4143-acf8-b064af572e02/original)](https://ampli-images.s3.amazonaws.com/production/24a94ca1-7461-4143-acf8-b064af572e02/original)

Controlando a dimensão do iframe. Fonte: Elaborado pelo autor

O código apresentado cria um _iframe_ de tamanho 640px de largura por 480px de altura.

# **HTML5 responsivo**

[![](https://ampli-images.s3.amazonaws.com/production/f4416376-bf48-4d01-b417-95676d7b7ca3/original)](https://ampli-images.s3.amazonaws.com/production/f4416376-bf48-4d01-b417-95676d7b7ca3/original)

Nos últimos anos, novos meios de acesso a websites têm se popularizado, como celulares, _tablets, laptops_ e computadores com telas de diversos tamanhos. Assim, um site desenvolvido especificadamente para um dispositivo com tela _FULL HD_ (1920x1080) não pode ser visualizado corretamente em um _smartphone_ cuja resolução é 375x812.

Devido a isso, introduziu-se o conceito de _design_ responsivo. Nessa técnica, o website pode ser exibido de diferentes formas, a depender do dispositivo usado para acesso (figura abaixo).

[![](https://ampli-images.s3.amazonaws.com/production/97139e98-4350-434e-ba0a-4d9c30afd776/original)](https://ampli-images.s3.amazonaws.com/production/97139e98-4350-434e-ba0a-4d9c30afd776/original)

Exemplo de uma página carregada em três diferentes dispositivos: computador desktop, tablet e smartphone. Fonte: Capturas de tela do site da Biblioteca Virtual da Kroton com adaptação do autor.

Atualmente, navegadores fornecem funções nativas para testagem da responsividade de páginas, como a ferramenta de alternância de dispositivo da função inspecionar elemento do Google Chrome (figura abaixo). A ferramenta está disponível por meio do atalho CTRL+SHIFT+I ou clicando com o botão direito e, em seguida, em inspecionar.

[![](https://ampli-images.s3.amazonaws.com/production/18c840e4-6b98-41fe-aff1-f328e259f9a5/original)](https://ampli-images.s3.amazonaws.com/production/18c840e4-6b98-41fe-aff1-f328e259f9a5/original)

Ferramenta de alternância de dispositivo da função inspecionar elemento de um navegador permite simular design responsivo. Fonte: Captura de tela do navegador Google Chrome elaborada pelo autor.

A implementação do design responsivo também requer o uso de folhas de estilos (CSS), que serão apresentadas nas próximas aulas.

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

No início desta aula, você conheceu a uma página com _layout_ desconfigurado e o seu respectivo código-fonte. O seu desafio consiste em consertá-lo.

Para solução do problema, você deve verificar, inicialmente, onde ele ocorreu.

Perceba que o problema de configuração aparece entre o segundo e o terceiro bloco.

[![](https://ampli-images.s3.amazonaws.com/production/89d7b666-3406-4f0e-9ead-3a5bcaba0189/original)](https://ampli-images.s3.amazonaws.com/production/89d7b666-3406-4f0e-9ead-3a5bcaba0189/original)

Estrutura da página com destaque no erro. Fonte: Elaborado pelo autor.

Percebemos que o possível trecho com erro envolve o texto _div class="card mb-4-shadow-sm_". Vamos, então, pesquisar todas as ocorrências desse termo Código-fonte(exposto anteriormente). Observe que esse termo aparece três vezes:

[![](https://ampli-images.s3.amazonaws.com/production/9404647a-6b4e-4ae2-8f2d-41af3a32e8d2/original)](https://ampli-images.s3.amazonaws.com/production/9404647a-6b4e-4ae2-8f2d-41af3a32e8d2/original)

Se estiver utilizando um editor de códigos, o _syntax highlight_ (quando o código é colorido de acordo com sua função) destacará claramente que há um problema na última ocorrência. Ao compararmos os códigos, percebemos que falta um parêntese angular < na abertura da _tag_ <div>, logo, basta inseri-lo para a página voltar ao normal.

[![](https://ampli-images.s3.amazonaws.com/production/da735fde-2154-4b4d-8912-b77365fb2dad/original)](https://ampli-images.s3.amazonaws.com/production/da735fde-2154-4b4d-8912-b77365fb2dad/original)

Estrutura da página ajustada. Fonte: Elaborado pelo autor.

Nesse caso, o estagiário deve ter apagado, inconscientemente, o símbolo da abertura da _tag_. A solução pode parecer simples, entretanto, muitos problemas em codificação de sites ocorrem quando pequenos erros aparecem em códigos muito grandes. É fundamental, portanto, que um programador web saiba identificá-los e corrigi-los.