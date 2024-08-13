# **Introdução da Aula**

[![](https://ampli-images.s3.amazonaws.com/production/303cc0de-5cc4-4a2e-ad60-3bf3d1b8e783/original)](https://ampli-images.s3.amazonaws.com/production/303cc0de-5cc4-4a2e-ad60-3bf3d1b8e783/original)

### **Qual é o foco da aula?**

Nesta aula, você irá aprender como desenvolver uma página _web_.

### **Objetivos gerais de aprendizagem**

Ao longo desta aula, você irá:

- nomear as propriedades de elementos CSS;
- definir o _box model_ HTML/ CSS
- traçar o conceito fundamental dos _containers_.

**Situação-problema**

Estudante, conhecer as estruturas de uma página web não é o suficiente para construir uma página WEB amigável. Você deve ter percebido que a maior parte dos websites comerciais possui estilos bem elaborados, que, com apenas HTML, possivelmente, não produziria o mesmo resultado. No HTML, _tags_ estruturais são utilizadas para determinar a semântica dos tipos de conteúdo inseridos. Nesse quesito, CSS pode ser essencial para construir páginas mais atrativas. Você pode posicionar corretamente elementos em determinadas posições.

Um dos conceitos importantes no desenvolvimento de páginas WEB é o _box model_ HTML/CSS ou, na tradução para português, modelo de caixa. O _box model_ visualiza cada elemento de uma página HTML como uma caixa e define algumas propriedades para manipular como os dados serão formatados. O _box model_ permite alterar as margens dos elementos, dividindo a estrutura de uma caixa em três partes: margem externa, borda e margem interna (também conhecida como preenchimento).

Além disso, para desenvolver uma página WEB, é importante conhecer algumas propriedades, como altura e largura, e o posicionamento dos elementos em CSS. As propriedades de posicionamento permitem definir onde um elemento deverá aparecer em uma página WEB, se sua posição será fixa ou baseada em outros elementos da página.

Por fim, veremos alguns estilos que serão aplicados em vídeos exibidos na página. Você também será introduzido a um conceito fundamental para a construção de páginas responsivas: os _containers_.

Você havia sido requisitado a construir uma página de contato para a empresa de provedor de internet, agora, você deve recriar a página de contato. Entretanto, deve construir uma página completa com cabeçalho, menu de navegação, área de conteúdo delimitada por um container e rodapé.

No menu de navegação, você deve incluir _links_ para:

- Página inicial.
- Página “quem somos”.
- Página “produtos”.
- Página “contato”.

______

**⚠️ Atenção**

- Você pode utilizar os códigos construídos anteriormente como base para iniciar o desenvolvimento da sua página.
- Utilize tags estruturais para cada parte do site. Ex.: _header, nav, main, article, div_.
- Chame o logo do site de “logo.png”. Segue abaixo um exemplo:
- NÃO utilize tabelas para colocar _inputs_ em colunas! Utilize a propriedade _float_.
- O botão de enviar deve ter cor de fundo verde e borda verde escura.

[![](https://ampli-images.s3.amazonaws.com/production/7ed6a656-3cc0-4849-8890-58bd61f3c324/original)](https://ampli-images.s3.amazonaws.com/production/7ed6a656-3cc0-4849-8890-58bd61f3c324/original)

Logo do provedor de Internet. Fonte: Elaborado pelo autor.

Bons estudos!

# **Conceito-chave**

[![](https://ampli-images.s3.amazonaws.com/production/57e01678-90aa-463b-a78e-daf00c0a1010/original)](https://ampli-images.s3.amazonaws.com/production/57e01678-90aa-463b-a78e-daf00c0a1010/original)

Estudante, um conceito fundamental para construção de documentos web é o _Box Mode_l. O _Box Model_ é utilizando para a inserção de bordas e margens em elementos HTML, permitindo um adequado posicionamento e ajuste na página construída.

# **Propriedades de bordas, preenchimentos e margens**

[![](https://ampli-images.s3.amazonaws.com/production/9296c65e-664b-4eb8-abea-2b6d8f783696/original)](https://ampli-images.s3.amazonaws.com/production/9296c65e-664b-4eb8-abea-2b6d8f783696/original)

Todas as _tags_ HTML, desde _divs_ a até mesmo blocos de parágrafos, podem ser interpretadas como caixas. A caixa delimitará os espaços que os elementos HTML poderão ocupar e o posicionamento de cada item de um site. Assim, esses elementos podem ser formatados usando-se o chamado modelo de caixa, do inglês _box model_ (W3SCHOOLS, 2020).

A figura abaixo ilustra um exemplo de como o _box model_ funciona na prática. Na divisão da figura, temos (A), (B) e (C). A figura abaixo (A) ilustra a visualização da caixa que envolve o menu de um site. Ao passar o cursor sobre partes de código visualizadas pela ferramenta inspecionar elemento, o navegador destaca a caixa que compõe os elementos. (B-C). Observe que mesmo os elementos de caixas possuem suas próprias caixas quando analisados individualmente.

[![](https://ampli-images.s3.amazonaws.com/production/26b081dc-81c0-4438-807b-2af019a98354/original)](https://ampli-images.s3.amazonaws.com/production/26b081dc-81c0-4438-807b-2af019a98354/original)

Visualizando as caixas usando a ferramenta inspecionar elemento. Fonte: captura de tela da Biblioteca Virtual elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/524067da-d815-4bdc-9c99-e7c47df41c23/original)](https://ampli-images.s3.amazonaws.com/production/524067da-d815-4bdc-9c99-e7c47df41c23/original)

O CSS possibilita a alteração de quatro propriedades principais de uma caixa listadas a seguir:

- Margem externa (_margin_).
- Borda (_border_).
- Margem interna ou preenchimento (_padding_).
- Conteúdo, que pode ser um texto, uma imagem, um vídeo, apenas uma caixa vazia, entre outros.

A figura abaixo ilustra a estrutura do modelo de caixa CSS com suas propriedades. A seguir, será descrita cada uma dessas propriedades.

[![](https://ampli-images.s3.amazonaws.com/production/0755e450-cdfd-4a96-be9a-b49f7eceb573/original)](https://ampli-images.s3.amazonaws.com/production/0755e450-cdfd-4a96-be9a-b49f7eceb573/original)

Modelo de Caixa CSS. Fonte: Mariano; de Melo-Minardi (2017, p. 100).

Para que possamos compreender corretamente o modelo de caixa CSS, vamos começar introduzindo o conceito de bordas. Isso será necessário, uma vez que as margens internas e externas serão aplicadas entre as bordas, que podem ser inseridas com a propriedade border, que deve receber:

- A espessura da borda.
- Um tipo: _solid_ (sólido), _doted_ (pontilhado), _dashed_ (tracejado), _double_ (borda dupla), _groove_ (borda 3D), _none_ (nenhuma borda), entre outros.
- Uma cor (pode ser apresentada no padrão hexadecimal, como \#000000).

A seguir, vamos mostrar uma aplicação de bordas em uma página _index_.html. Para isso, criamos o arquivo estilo.css mostrado a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/5be56949-2f07-48aa-acbb-1a0578f63247/original)](https://ampli-images.s3.amazonaws.com/production/5be56949-2f07-48aa-acbb-1a0578f63247/original)

estilo.css - bordas. Fonte: Elaborado pelo autor.

No arquivo estilo.css, para todas as divs presentes na página (_inde_x.html) mostrada a seguir, será aplicada uma borda com 1 pixel de espessura (1px) (border:1px), tracejada (_dashed_) e na cor preta (_dashed_ \#000), observe que #000 é equivalente a \#000000 ou a _black_).

[![](https://ampli-images.s3.amazonaws.com/production/f6c10c60-fe2e-449d-9fa8-252c2b48b4cd/original)](https://ampli-images.s3.amazonaws.com/production/f6c10c60-fe2e-449d-9fa8-252c2b48b4cd/original)

Index.html. Fonte: Elaborado pelo autor.

A figura abaixo ilustra o resultado da página _index_.html e estilo.css. Observe que a borda foi aplicada diretamente a uma div. Bordas podem ser aplicadas a quaisquer elementos.

[![](https://ampli-images.s3.amazonaws.com/production/f1678ae0-a23d-4f2c-b49f-df63326ece1c/original)](https://ampli-images.s3.amazonaws.com/production/f1678ae0-a23d-4f2c-b49f-df63326ece1c/original)

Borda aplicada a uma div. Fonte: Elaborado pelo autor.

Podemos, também, aplicar uma segunda propriedade border à _tag_ <p>. Observe o trecho de código do arquivo estilo.css a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/cd9aee26-456f-4349-ac5f-bf9f43cb28b4/original)](https://ampli-images.s3.amazonaws.com/production/cd9aee26-456f-4349-ac5f-bf9f43cb28b4/original)

Estilo.css. Fonte: Elaborado pelo autor.

Observe, na figura abaixo, o resultado da aplicação da propriedade border à _tag_ <p>.

[![](https://ampli-images.s3.amazonaws.com/production/0bd8d407-d380-49c5-aec1-4df48a38dc5f/original)](https://ampli-images.s3.amazonaws.com/production/0bd8d407-d380-49c5-aec1-4df48a38dc5f/original)

Borda aplicada à tag <p>. Fonte: Elaborado pelo autor.

Observe que uma segunda borda de cor cinza (\#999), sólida (_solid_) e com 10px de espessura foi inserida entre o texto e a borda da div. Podemos alterar o tamanho das margens usando as propriedades _margin_ e _padding_, conforme a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/e4eabe94-4d29-4679-8363-1290ba358231/original)](https://ampli-images.s3.amazonaws.com/production/e4eabe94-4d29-4679-8363-1290ba358231/original)

[![](https://ampli-images.s3.amazonaws.com/production/b1f12d28-25f5-43e6-b58e-8f2da6b45add/original)](https://ampli-images.s3.amazonaws.com/production/b1f12d28-25f5-43e6-b58e-8f2da6b45add/original)

[![](https://ampli-images.s3.amazonaws.com/production/c1159151-2edf-45e7-a9f2-bdb2a7c9ddfe/original)](https://ampli-images.s3.amazonaws.com/production/c1159151-2edf-45e7-a9f2-bdb2a7c9ddfe/original)

Propriedades margin e padding. Fonte: adaptado de Mariano; de Melo-Minardi (2017).

A seguir, observe como alterar as margens internas da _tag_ <p> usando a propriedade _padding_:

[![](https://ampli-images.s3.amazonaws.com/production/b477ba39-b88c-447b-a0de-32a3fc45f60f/original)](https://ampli-images.s3.amazonaws.com/production/b477ba39-b88c-447b-a0de-32a3fc45f60f/original)

A figura abaixo ilustra o resultado da página do código apresentado:

[![](https://ampli-images.s3.amazonaws.com/production/01e3c346-a9ec-40ce-b47d-a3b2bf6803ca/original)](https://ampli-images.s3.amazonaws.com/production/01e3c346-a9ec-40ce-b47d-a3b2bf6803ca/original)

Margem interna de 30px. Fonte: Elaborado pelo autor.

Agora, veja o que acontece se substituirmos _padding_ por _margin_:

[![](https://ampli-images.s3.amazonaws.com/production/c08ebd54-c1ef-4aa5-a429-8e7852015d5e/original)](https://ampli-images.s3.amazonaws.com/production/c08ebd54-c1ef-4aa5-a429-8e7852015d5e/original)

A figura abaixo ilustra o resultado com a margem externa de 30px.

[![](https://ampli-images.s3.amazonaws.com/production/66a7f72d-10c8-48ad-b43e-c1a7edec8059/original)](https://ampli-images.s3.amazonaws.com/production/66a7f72d-10c8-48ad-b43e-c1a7edec8059/original)

Margem externa de 30px. Fonte: elaborado pelo autor.

Ao passar um único valor para a propriedade _padding_ ou _margin_, esse valor é aplicado para todas as bordas. Você pode especificar os valores desejados das bordas superior, direita, inferior e esquerda, como vemos na figura abaixo.

Há duas formas de especificar as bordas. A primeira é especificando a borda que deseja alterar, como _margin-right_, que altera a margem à direita, ou _margin-bottom_, que altera a margem inferior.

[![](https://ampli-images.s3.amazonaws.com/production/d9abcc77-3aaf-4bdc-9536-732d49d20519/original)](https://ampli-images.s3.amazonaws.com/production/d9abcc77-3aaf-4bdc-9536-732d49d20519/original)

Bordas: superior, direita, inferior e esquerda. Fonte: elaborado pelo autor.

A segunda forma de especificar é determinando a quantidade de valores passados às propriedades _margin_ ou _padding_: você pode passar 1, 2, 3 ou 4 valores, conforme o exemplo a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/314e3654-d7dc-461e-8dbb-ff7a65f4e241/original)](https://ampli-images.s3.amazonaws.com/production/314e3654-d7dc-461e-8dbb-ff7a65f4e241/original)

Nesse exemplo, você aplicou uma margem superior de 10px, direita de 20px, inferior de 5px e nenhuma margem à esquerda.

______

🔁 **Assimile**

Da mesma forma que se pode determinar propriedades _margin_ e _padding_ específicas, é possível alterar as bordas de um elemento. O trecho de código a seguir aplica uma borda única à esquerda com tamanho de 10px.

[![](https://ampli-images.s3.amazonaws.com/production/73223c92-fdb9-4339-9da9-862c631a7803/original)](https://ampli-images.s3.amazonaws.com/production/73223c92-fdb9-4339-9da9-862c631a7803/original)

[![](https://ampli-images.s3.amazonaws.com/production/2a1a281e-57d4-4c9a-8d45-9bc2e545230f/original)](https://ampli-images.s3.amazonaws.com/production/2a1a281e-57d4-4c9a-8d45-9bc2e545230f/original)

Borda única à esquerda. Fonte: elaborado pelo autor.

Note que foi aplicada uma margem interna de 30px (superior e inferior) e 10px (direita e esquerda).

# **Propriedades de largura e altura**

[![](https://ampli-images.s3.amazonaws.com/production/bc5c0e2e-853b-4a8a-86c7-9d4fc299aa18/original)](https://ampli-images.s3.amazonaws.com/production/bc5c0e2e-853b-4a8a-86c7-9d4fc299aa18/original)

Para os casos apresentados até o momento, todas as margens ocupam todo o espaço horizontal disponível, mas a altura depende do conteúdo do bloco. Podemos, então, determinar a altura e a largura utilizando as propriedades altura (_height_) e largura (_width_). Observe a figura abaixo, temos algumas dessas propriedades com as funções e exemplos de cada uma delas.

[![](https://ampli-images.s3.amazonaws.com/production/fff29fd6-df88-45cc-a146-e4a4da9d371f/original)](https://ampli-images.s3.amazonaws.com/production/fff29fd6-df88-45cc-a146-e4a4da9d371f/original)

[![](https://ampli-images.s3.amazonaws.com/production/74a3fa91-91ae-401e-85d7-11aadce067bd/original)](https://ampli-images.s3.amazonaws.com/production/74a3fa91-91ae-401e-85d7-11aadce067bd/original)

Propriedades de altura e largura. Fonte: adaptado de Mariano; de Melo-Minardi (2017).

# **Posicionamento de elementos CSS**

[![](https://ampli-images.s3.amazonaws.com/production/bca06fa5-c463-4cd6-be43-7807d75ea3fe/original)](https://ampli-images.s3.amazonaws.com/production/bca06fa5-c463-4cd6-be43-7807d75ea3fe/original)

A partir dos conceitos de margens e tamanhos, podemos começar a compreender o sistema de posicionamentos do CSS. Para ilustrar esse sistema, vamos criar quatro divs e aplicar cores a elas (utilizaremos a ferramenta _Adobe Color_ para obter dicas de cores complementares). Além disso, vamos definir que o tamanho das divs será de 100px de altura por 100px de largura.

Por padrão, HTML insere novos elementos abaixo de outros elementos já declarados. Podemos resolver isso por meio da propriedade _float_.

A propriedade _float_ (flutuação) altera o fluxo natural de posicionamento de novos elementos HTML, permitindo que sejam adicionados à direita (_right_) ou à esquerda (_left_) (MDN WEB DOCS, 2019).

Vamos adicionar a propriedade _float: left;_ a todos os elementos no arquivo estilo.css. Observe a figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/a94d0781-8f5e-4b76-9937-ce650ee0bea1/original)](https://ampli-images.s3.amazonaws.com/production/a94d0781-8f5e-4b76-9937-ce650ee0bea1/original)

estilo.css. Fonte: elaborado pelo autor.

Observe a seguir o resultado da aplicação de _float:left_; com as divs lado a lado.

[![](https://ampli-images.s3.amazonaws.com/production/94539b5d-ed36-447e-ba7c-425655aebc0b/original)](https://ampli-images.s3.amazonaws.com/production/94539b5d-ed36-447e-ba7c-425655aebc0b/original)

Divs lado a lado. Fonte: elaborado pelo autor.

A propriedade _float left_ permite que o próximo elemento HTML seja inserido ao lado do elemento atual. Nesse caso, isso indica que o elemento que recebe essa propriedade deve ficar à esquerda do próximo elemento. Se no lugar de _left_ utilizássemos a opção _right_, o elemento atual seria posicionado à direita. Observe a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/7819ded8-80a8-417e-a52a-c00a233f34e7/original)](https://ampli-images.s3.amazonaws.com/production/7819ded8-80a8-417e-a52a-c00a233f34e7/original)

Estilo.css. Fonte: elaborado pelo autor.

Observe o resultado da aplicação de _float:right_ a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/c50afb10-3963-4341-8650-2d395b351d99/original)](https://ampli-images.s3.amazonaws.com/production/c50afb10-3963-4341-8650-2d395b351d99/original)

Float right. Fonte: elaborado pelo autor.

Observe que o primeiro bloco (vermelho) foi posicionado no lado direito da tela, passando a ser o último. A propriedade _float: right_ indica que o bloco deve “flutuar à direita”, ou seja, ele deve estar à direita de todos os elementos a seguir.

Agora, suponha que desejemos que os dois últimos quadrados sejam colocados na linha debaixo; se apenas removermos a propriedade _float: left_, nosso código apresentará problemas. Observe o que ocorre ao removermos a propriedade do bloco delta.

[![](https://ampli-images.s3.amazonaws.com/production/dd43acd2-6a68-47c1-bd10-38253a26946b/original)](https://ampli-images.s3.amazonaws.com/production/dd43acd2-6a68-47c1-bd10-38253a26946b/original)

Removendo propriedade do bloco laranja. Fonte: elaborado pelo autor.

Ao utilizarmos a ferramenta de inspeção de elementos, podemos perceber que a div ainda existe. Entretanto, ela foi sobreposta pelas divs anteriores, ou seja, o bloco alaranjado encontra-se abaixo do bloco vermelho com o recurso inspecionar.

[![](https://ampli-images.s3.amazonaws.com/production/3753c054-6110-4f1e-b23e-b256a5110728/original)](https://ampli-images.s3.amazonaws.com/production/3753c054-6110-4f1e-b23e-b256a5110728/original)

Inspecionar elemento. Fonte: elaborado pelo autor.

Para solucionar o problema de sobreposição, pode-se utilizar a propriedade _clear_, que indica se um elemento pode possuir vizinhos à direita ou à esquerda (_right_ e _left_) ou se esses elementos devem ser posicionados na linha seguinte, abaixo (_both_). Todavia, para utilizarmos essa propriedade, devemos reestruturar a forma como o HTML está organizado, criando, assim, duas novas divs que receberão cada uma das linhas. O código ficará organizado da forma a seguir:

Div: 1ª linha

- Div: Alfa
- Div: Beta

Div: 2ª linha

- Div: Gama
- Div: Delta

Como as linhas possuem características idênticas, podemos criar uma classe para representá-las. Aplicaremos a elas a propriedade clear:both; que fará com que sejam posicionadas uma abaixo da outra. Observe as figuras index.html e estilo.css.

[![](https://ampli-images.s3.amazonaws.com/production/45d42736-38b3-48ef-9dcb-dcf87e7ff51a/original)](https://ampli-images.s3.amazonaws.com/production/45d42736-38b3-48ef-9dcb-dcf87e7ff51a/original)

Index.html. Fonte: elaborado pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/0f8d5ff6-04bf-4b87-84dc-f63af03ce981/original)](https://ampli-images.s3.amazonaws.com/production/0f8d5ff6-04bf-4b87-84dc-f63af03ce981/original)

estilo.css. Fonte: elaborado pelo autor.

Perceba que, agora, os blocos estão posicionados corretamente:

[![](https://ampli-images.s3.amazonaws.com/production/e8e60aec-bf99-452a-ac07-e0f3977f3ddb/original)](https://ampli-images.s3.amazonaws.com/production/e8e60aec-bf99-452a-ac07-e0f3977f3ddb/original)

Posicionando blocos corretamente. Fonte: elaborado pelo autor.

**📝 Exemplificando**

Observe, a seguir, um uso da propriedade _clear both_ para um site de notícias. Sites de notícias requerem que imagens sejam exibidas ao redor de textos, entretanto, nem todas as imagens devem ser exibidas com essas configurações, sendo necessário, algumas vezes, que haja uma separação clara entre imagem e texto.

No exemplo a seguir, uma imagem é posicionada ao redor de um texto usando-se a propriedade _float left_ (lado esquerdo). Ao ser aplicada a propriedade _clear both_, é inserida uma linha invisível que determina que todo ponto abaixo dela deve ser alocado na linha abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/7316ec63-6167-4d44-8102-ebab2e5a3b85/original)](https://ampli-images.s3.amazonaws.com/production/7316ec63-6167-4d44-8102-ebab2e5a3b85/original)

Float left e clear both. Fonte: Mariano; de Melo-Minardi (2017, p.99).

_Float left_ usado para posicionar texto ao redor de uma imagem (esquerda). Ao lado, vemos a propriedade _clear both_ aplicada.

# **A importância da delimitação do tamanho de blocos**

[![](https://ampli-images.s3.amazonaws.com/production/152e3063-5030-4e82-a5ee-d932813a88f3/original)](https://ampli-images.s3.amazonaws.com/production/152e3063-5030-4e82-a5ee-d932813a88f3/original)

Agora, suponhamos que queremos adicionar uma margem de 20px separando os blocos. Podemos, simplesmente, adicionar o seguinte código no arquivo “estilo.css”:

[![](https://ampli-images.s3.amazonaws.com/production/8281a8e1-d18d-4d9e-a134-a140bcb19249/original)](https://ampli-images.s3.amazonaws.com/production/8281a8e1-d18d-4d9e-a134-a140bcb19249/original)

Nesse caso, usamos 10px, porque cada bloco aplicará uma distância de 10px em relação ao outro (como cada linha tem dois blocos, logo, a margem será de 20px). Entretanto, ao carregar a página, ela aparecerá conforme mostrado na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/046b0d24-110a-4222-a9a6-fa1d1d5994fd/original)](https://ampli-images.s3.amazonaws.com/production/046b0d24-110a-4222-a9a6-fa1d1d5994fd/original)

Problema na exibição. Fonte: elaborada pelo autor.

O problema ocorre, pois foi delimitado o tamanho máximo de largura e altura. Se cada bloco tem largura e altura de 100px e uma margem de 10px para cada borda, logo ele, ocupará 120px de largura e de altura (100+10+10). Como temos dois blocos por linha (ou seja, 240px) e delimitamos o tamanho da linha para 200px, a interface entrará em colapso e se desestruturará ao atingir o limite da linha. Note que, mesmo adicionando a propriedade de flutuação à esquerda, ao atingir o limite máximo de largura definido, o bloco será empurrado para a linha abaixo.

Há várias formas de resolver esse problema. A mais simples é aumentar o tamanho máximo da classe “linha” para 240px.

[![](https://ampli-images.s3.amazonaws.com/production/71a79501-5cbc-4916-9e7c-96287657275f/original)](https://ampli-images.s3.amazonaws.com/production/71a79501-5cbc-4916-9e7c-96287657275f/original)

Largura de 240px. Fonte: elaborada pelo autor.

# **Position**

[![](https://ampli-images.s3.amazonaws.com/production/c314a800-58b0-4a8c-8999-fa02077dc807/original)](https://ampli-images.s3.amazonaws.com/production/c314a800-58b0-4a8c-8999-fa02077dc807/original)

Uma propriedade fundamental para posicionamento de elementos HTML é a propriedade position, que pode ser absoluta (_absolute_), relativa (_relative_) ou fixa (_fixed_). O valor padrão dessa _tag_ é _relative_, ou seja, a posição dos itens é relativa à posição de itens apresentados anteriormente. Entretanto, os dois outros tipos de posicionamento inserem características interessantes. Vamos começar aprendendo as características da position _absolute_.

Enquanto a _position relative_ determina a posição com base no elemento HTML declarado anteriormente, a _position absolute_ determina a posição com base apenas na página atual, o que permite que itens se sobreponham. Observe o resultado da página web se adicionarmos a propriedade position com valor _absolute_ para todos os nossos blocos:

[![](https://ampli-images.s3.amazonaws.com/production/2e226a8f-159a-4fb4-a00a-3fa516db9a63/original)](https://ampli-images.s3.amazonaws.com/production/2e226a8f-159a-4fb4-a00a-3fa516db9a63/original)

Apenas a div delta é exibida. Fonte: elaborada pelo autor.

Observe que apenas a div da cor alaranjada é exibida. Isso acontece porque ela é a última a ser declarada, logo, ela sobrepõe a todas as outras. Podemos visualizar que as outras divs ainda estão presentes, adicionando propriedades de distância para as margens da página:

[![](https://ampli-images.s3.amazonaws.com/production/de198679-c23e-4d6b-91bb-56d5c4f66210/original)](https://ampli-images.s3.amazonaws.com/production/de198679-c23e-4d6b-91bb-56d5c4f66210/original)

[![](https://ampli-images.s3.amazonaws.com/production/e3d0a106-3490-4f27-a589-f537b4e61806/original)](https://ampli-images.s3.amazonaws.com/production/e3d0a106-3490-4f27-a589-f537b4e61806/original)

estilo.css. Fonte: elaborada pelo autor.

A propriedade _absolute_ atua em conjunto com quatro possíveis propriedades de posicionamento:

- _Top:_ determina a distância do elemento para o topo da página (no exemplo, o valor 0px indica que o elemento deve estar a uma distância de 0px do topo da página).
- _Bottom:_ determina a distância do elemento para o rodapé da página (no exemplo, o valor 0px indica que o elemento deve estar a uma distância de 0px da parte inferior da página).
- _Left:_ determina a distância do elemento para o lado esquerdo da página (no exemplo, o valor 0px indica que o elemento deve estar a uma distância de 0px do lado esquerdo).
- _Right:_ determina a distância do elemento para o lado direito da página (no exemplo, o valor 0px indica que o elemento deve estar a uma distância de 0px do lado direito).

Podemos alterar a prioridade de exibição de itens usando a propriedade z-index (índice do eixo z), que deverá receber um número indicando a ordem de prioridade. Quanto maior o número, maior a prioridade de exibição (ou seja, mais à frente ele estará).

No exemplo a seguir, a propriedade z-index dos blocos é alterada. Observe o resultado na figura abaixo:

- Alfa receberá o valor 4.
- Beta receberá o valor 2.
- Gama receberá o valor 3.
- Delta receberá o valor 4.

[![](https://ampli-images.s3.amazonaws.com/production/b0ba330a-b986-4db1-a955-3c29a5327ce9/original)](https://ampli-images.s3.amazonaws.com/production/b0ba330a-b986-4db1-a955-3c29a5327ce9/original)

O bloco vermelho (alfa) tem a prioridade mais alta (z-index: 4), o bloco beta (azul) tem prioridade 2, enquanto o gama (verde) tem prioridade 3. Logo, o verde deve estar acima do azul e abaixo do vermelho. Delta tem a mais baixa prioridade (1). Fonte: elaborada pelo autor.

**🔁 Assimile**

A prioridade de exibição de conteúdo em uma página é vital para que o _layout_ seja exibido corretamente.

# **Position Fixed**

[![](https://ampli-images.s3.amazonaws.com/production/e30ff1bc-de4b-4d40-8f55-4508687c07bc/original)](https://ampli-images.s3.amazonaws.com/production/e30ff1bc-de4b-4d40-8f55-4508687c07bc/original)

Agora, vamos falar sobre a propriedade _position fixed_. _Fixed_ determina que um item esteja sempre em uma mesma posição, independentemente da quantidade de itens em uma página. No exemplo a seguir, vamos adicionar textos na página e fixar cada imagem em um canto.

[![](https://ampli-images.s3.amazonaws.com/production/1985198d-4c13-4376-aa7b-45858b743cc0/original)](https://ampli-images.s3.amazonaws.com/production/1985198d-4c13-4376-aa7b-45858b743cc0/original)

index.html. Fonte: elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/64c07707-57a9-40ab-bca7-2e1f16b37d33/original)](https://ampli-images.s3.amazonaws.com/production/64c07707-57a9-40ab-bca7-2e1f16b37d33/original)

[![](https://ampli-images.s3.amazonaws.com/production/59905414-b375-469a-8b63-15010444965d/original)](https://ampli-images.s3.amazonaws.com/production/59905414-b375-469a-8b63-15010444965d/original)

[![](https://ampli-images.s3.amazonaws.com/production/8c4e87e0-7e02-44d4-99f5-59442cc4d307/original)](https://ampli-images.s3.amazonaws.com/production/8c4e87e0-7e02-44d4-99f5-59442cc4d307/original)

estilo.css. Fonte: elaborada pelo autor.

À medida que o usuário rolar pela página gerada anteriormente, os quatro blocos coloridos continuarão fixos nos locais delimitados:

[![](https://ampli-images.s3.amazonaws.com/production/9b0334a1-4182-4060-ac0b-4ce77d4d1f50/original)](https://ampli-images.s3.amazonaws.com/production/9b0334a1-4182-4060-ac0b-4ce77d4d1f50/original)

Posição fixed aplicada aos blocos. Fonte: elaborada pelo autor.

# **Manipulação de vídeos em CSS**

[![](https://ampli-images.s3.amazonaws.com/production/ed9c75ec-a091-487a-80ef-6ae3c02d90f8/original)](https://ampli-images.s3.amazonaws.com/production/ed9c75ec-a091-487a-80ef-6ae3c02d90f8/original)

Existe propriedades para a manipulação de áudios e vídeos usando CSS. Para ilustrar este exemplo, utilizaremos o vídeo disponível gratuitamente na plataforma _Pexels_. Para facilitar a análise, vamos renomear o vídeo para “video.mp4”.

A figura a seguir carrega o vídeo em sua página HTML:

[![](https://ampli-images.s3.amazonaws.com/production/6d1a9966-a295-4106-b7ff-f886d7b050bf/original)](https://ampli-images.s3.amazonaws.com/production/6d1a9966-a295-4106-b7ff-f886d7b050bf/original)

index.html – carregando vídeo em sua página HTML. Fonte: elaborada pelo autor.

A figura abaixo  mostra a página web carregada.

[![](https://ampli-images.s3.amazonaws.com/production/eea27a80-543f-4618-8815-6c78d4459337/original)](https://ampli-images.s3.amazonaws.com/production/eea27a80-543f-4618-8815-6c78d4459337/original)

Exibição do vídeo usando HTML. Fonte: elaborada pelo autor.

O trecho de código que realiza o carregamento do vídeo se encontra entre as linhas 9 e 11:

[![](https://ampli-images.s3.amazonaws.com/production/92fe171d-28e4-484c-ae3c-19f36a6a3c7a/original)](https://ampli-images.s3.amazonaws.com/production/92fe171d-28e4-484c-ae3c-19f36a6a3c7a/original)

Observe que a _tag_ vídeo recebe o atributo “_controls_”. Esse atributo será responsável por inserir os botões de início e pause do vídeo, além do volume, maximização e botões de configurações. Neste exemplo, usamos a _tag_  <_source_> para indicar o nome e o tipo do vídeo. Agora, vamos aplicar algumas propriedades de estilo a essa página.

[![](https://ampli-images.s3.amazonaws.com/production/59a40e29-8790-4831-a7fd-808409f8b7c7/original)](https://ampli-images.s3.amazonaws.com/production/59a40e29-8790-4831-a7fd-808409f8b7c7/original)

Estilo.css. Fonte: elaborada pelo autor.

Vamos começar adicionando bordas e sombras ao vídeo:

[![](https://ampli-images.s3.amazonaws.com/production/a03ce3d3-ab1c-418a-b141-b525a2d7da33/original)](https://ampli-images.s3.amazonaws.com/production/a03ce3d3-ab1c-418a-b141-b525a2d7da33/original)

Bordas e sombras. Fonte: elaborada pelo autor.

Até o momento, foi mostrado como inserir bordas, agora, vamos à propriedade CSS para inclusão de sombras. A propriedade CSS responsável por isso é a _box-shadow_, que recebe quatro valores: distância de x | distância de -y | desfoque | cor.

Neste exemplo, foi inserido uma sombra na cor preta com distância para os eixos x e y de 3px e um desfoque de 10px.

Pode-se ainda aplicar as propriedades de tamanho (_width_), como pode ser visto na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/16355f4e-bba3-4e10-8dfb-8ee0f5327021/original)](https://ampli-images.s3.amazonaws.com/production/16355f4e-bba3-4e10-8dfb-8ee0f5327021/original)

estilo.css – propriedades de tamanho. Fonte: elaborada pelo autor.

Esse código utiliza a propriedade width para que o vídeo ocupe todo o espaçamento da página. Note que, por ser um vídeo vertical, a altura do vídeo ultrapassa o tamanho natural da página HTML:

[![](https://ampli-images.s3.amazonaws.com/production/bbdcd6ed-6487-43fe-86b1-3ed2c4e30da6/original)](https://ampli-images.s3.amazonaws.com/production/bbdcd6ed-6487-43fe-86b1-3ed2c4e30da6/original)

Vídeo em largura total. Fonte: elaborada pelo autor.

# **Containers**

[![](https://ampli-images.s3.amazonaws.com/production/54f68d38-8c41-41a9-822e-e4e0469336b8/original)](https://ampli-images.s3.amazonaws.com/production/54f68d38-8c41-41a9-822e-e4e0469336b8/original)

Um conceito importante em CSS e responsividade são os Containers. Os containers delimitam o posicionamento de um conjunto de blocos em uma página, inserindo margens idênticas nos lados direito e esquerdo.

Observe, na figura a seguir, um exemplo da utilidade de containers.

[![](https://ampli-images.s3.amazonaws.com/production/2596e41f-c213-4cd4-b2d1-2fbaab00ddb5/original)](https://ampli-images.s3.amazonaws.com/production/2596e41f-c213-4cd4-b2d1-2fbaab00ddb5/original)

Observe que no exemplo da figura acima, o conteúdo da página é centralizado com margens idênticas tanto para a direita quanto para a esquerda. Isso indica que o conteúdo da página está contido em um container. Essas margens só aparecem em monitores de alta resolução; em monitores de menor resolução, elas não seriam exibidas. Por isso, containers podem ser considerados elementos fundamentais para páginas responsivas.

O conceito de container pode ser aplicado a qualquer elemento HTML. Aqui, vamos introduzi-lo para delimitar margens de exibição do vídeo.

Primeiro, vamos criar uma div container para delimitar todo o conteúdo exibido:

[![](https://ampli-images.s3.amazonaws.com/production/b6c8fa5c-e8f6-4458-9859-2fed7680133e/original)](https://ampli-images.s3.amazonaws.com/production/b6c8fa5c-e8f6-4458-9859-2fed7680133e/original)

index.html – criando uma div container. Fonte: elaborada pelo autor.

O vídeo deve estar entre as _tags_ de abertura e fechamento da div container. Os estilos serão aplicados como uma classe. Agora, vamos configurar o arquivo estilo.css:

[![](https://ampli-images.s3.amazonaws.com/production/98c37817-33e7-4f7c-b40a-dbaa94147b0a/original)](https://ampli-images.s3.amazonaws.com/production/98c37817-33e7-4f7c-b40a-dbaa94147b0a/original)

estilo.css – criando uma div container. Fonte: elaborada pelo autor.

Observe que ao delimitar a largura do nosso container em 960px com margem de 20px (para o topo e o rodapé) e o valor auto (para a esquerda e direita), o valor auto configura os mesmos valores tanto para direita quanto para a esquerda. Por exemplo: imagine que o monitor tem uma resolução de 1280px de largura por 768px de altura; como seu container tem tamanho de 960px, sobram 320px que não serão utilizados. A propriedade auto distribui 160px para cada lado, assim, o container fica centralizado na página (Figura 2.46). Observe como o vídeo será exibido:

[![](https://ampli-images.s3.amazonaws.com/production/229bc7d3-86a6-4b59-8543-6d9dd8b7423f/original)](https://ampli-images.s3.amazonaws.com/production/229bc7d3-86a6-4b59-8543-6d9dd8b7423f/original)

Container centraliza o vídeo. Fonte: elaborada pelo autor.

Um ponto importante a ser ressaltado é que a exibição do vídeo dessa forma se deve à combinação de dois fatores:

- Largura do container (960px).
- Largura aplicada à _tag_ <vídeo> (100%).

Perceba que a _tag_ vídeo está dentro do container, logo, o vídeo terá largura de 100% sobre o tamanho de sua div pai, ou seja, 960px.

______

**💭 Reflita**

Containers permitem que o conteúdo seja corretamente posicionado em uma página, mantendo margens à direita e à esquerda. Se temos outras formas de realizar o posicionamento, por que podemos utilizar containers quando se trata de páginas responsivas? Reflita sobre sua importância para a construção de páginas responsivas.

______

**➕ Pesquise mais**

**Sobre o uso de vídeos em páginas web**

A inserção direta de vídeos em um website pelo HTML não é bastante utilizada por desenvolvedores web, e isso se deve ao fato de o carregamento de vídeos consumir recursos computacionais do servidor, uma vez que vídeos demandam espaço de armazenamento e banda para a transmissão dos dados. Muitas vezes, desenvolvedores optam por inserir os vídeos em plataformas especializadas, como _YouTube, Vimeo_ ou _Twitch_, e, por fim, embutir o vídeo na página por meio de _tags_ de frames.

______

Estudante, nesta aula você aprendeu a posicionar elementos em páginas. Esse conceito é fundamental para a elaboração de páginas web mais completas. Agora, você já está pronto para construir websites mais profissionais. Portanto, na próxima aula, apresentaremos algumas propriedades interessantes para formatação de tabelas e formulários, além de conceitos de frameworks CSS.

Até mais!

# **Conclusão**

[![](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)](https://ampli-images.s3.amazonaws.com/production/4ed6c0a1-d622-4ece-99ce-406bbdc54837/original)

A seguir, apresentaremos uma possível solução para esse problema. É importante salientar que não existe uma resposta perfeita em relação ao estilo. Neste exercício, exigimos apenas que as _tags_ requisitadas sejam apresentadas e corretamente posicionadas na página. Cada desenvolvedor deve adotar o _design_ que achar melhor. Aqui, apresentamos um exemplo básico de modelo de página de contato.

Para facilitar a compreensão do código, as explicações foram inseridas como comentários:

- Em HTML, comentários são códigos em volta dos caracteres <!-- e -->.
- Em CSS, comentários são códigos escritos entre os caracteres /* e */.

Vamos começar apresentando como construir o arquivo HTML:

[![](https://ampli-images.s3.amazonaws.com/production/76d5351d-31b7-48af-a98d-ddfd8df080fc/original)](https://ampli-images.s3.amazonaws.com/production/76d5351d-31b7-48af-a98d-ddfd8df080fc/original)

[![](https://ampli-images.s3.amazonaws.com/production/0660cafa-5eee-447e-b7f5-ad788015250a/original)](https://ampli-images.s3.amazonaws.com/production/0660cafa-5eee-447e-b7f5-ad788015250a/original)

[![](https://ampli-images.s3.amazonaws.com/production/81f50241-5e8e-4e0f-92fc-052fc631db03/original)](https://ampli-images.s3.amazonaws.com/production/81f50241-5e8e-4e0f-92fc-052fc631db03/original)

[![](https://ampli-images.s3.amazonaws.com/production/2d67bd91-0a20-4bf7-9144-c31cf7539751/original)](https://ampli-images.s3.amazonaws.com/production/2d67bd91-0a20-4bf7-9144-c31cf7539751/original)

[![](https://ampli-images.s3.amazonaws.com/production/e0ab050a-c528-440b-b9ae-c0326643d189/original)](https://ampli-images.s3.amazonaws.com/production/e0ab050a-c528-440b-b9ae-c0326643d189/original)

[![](https://ampli-images.s3.amazonaws.com/production/3e1b2d42-6b2e-4496-baca-0964f142a26d/original)](https://ampli-images.s3.amazonaws.com/production/3e1b2d42-6b2e-4496-baca-0964f142a26d/original)

index.html. Fonte: elaborado pelo autor.

Se você analisar o navegador, verá uma página parecida com esta:

[![](https://ampli-images.s3.amazonaws.com/production/4a67d233-8b2a-4777-afb5-26f34d07a562/original)](https://ampli-images.s3.amazonaws.com/production/4a67d233-8b2a-4777-afb5-26f34d07a562/original)

Página HTML visualizada no navegador. Fonte: elaborado pelo autor.

Veja que nossa página ainda não possui nenhum estilo aplicado; vamos configurar cores, posicionamentos e margens usando CSS:

[![](https://ampli-images.s3.amazonaws.com/production/2ed7c606-cff9-4bde-a335-2028643da3f7/original)](https://ampli-images.s3.amazonaws.com/production/2ed7c606-cff9-4bde-a335-2028643da3f7/original)

[![](https://ampli-images.s3.amazonaws.com/production/c51ac69d-ccb8-478b-87e0-c736fa55f0be/original)](https://ampli-images.s3.amazonaws.com/production/c51ac69d-ccb8-478b-87e0-c736fa55f0be/original)

[![](https://ampli-images.s3.amazonaws.com/production/ec120b5e-d208-4584-9de8-5e84a8ac6a50/original)](https://ampli-images.s3.amazonaws.com/production/ec120b5e-d208-4584-9de8-5e84a8ac6a50/original)

[![](https://ampli-images.s3.amazonaws.com/production/23e28273-9519-45ae-9319-7031a80b4774/original)](https://ampli-images.s3.amazonaws.com/production/23e28273-9519-45ae-9319-7031a80b4774/original)

[![](https://ampli-images.s3.amazonaws.com/production/31d68a41-6512-4bf4-ba77-2fd98a091ad3/original)](https://ampli-images.s3.amazonaws.com/production/31d68a41-6512-4bf4-ba77-2fd98a091ad3/original)

[![](https://ampli-images.s3.amazonaws.com/production/a4c43135-b815-4d25-b9a6-4f2e1ee80231/original)](https://ampli-images.s3.amazonaws.com/production/a4c43135-b815-4d25-b9a6-4f2e1ee80231/original)

[![](https://ampli-images.s3.amazonaws.com/production/ea8a32c1-caa5-486a-bc51-8cdfa16cee62/original)](https://ampli-images.s3.amazonaws.com/production/ea8a32c1-caa5-486a-bc51-8cdfa16cee62/original)

[![](https://ampli-images.s3.amazonaws.com/production/604e442a-6a02-4080-a456-f833462e3c4e/original)](https://ampli-images.s3.amazonaws.com/production/604e442a-6a02-4080-a456-f833462e3c4e/original)

estilo.css. Fonte: elaborado pelo autor.

Agora, observe como ficará nossa página web:

[![](https://ampli-images.s3.amazonaws.com/production/a4d287da-6d22-44a5-bb4e-55bec1fc9f4a/original)](https://ampli-images.s3.amazonaws.com/production/a4d287da-6d22-44a5-bb4e-55bec1fc9f4a/original)

Página web finalizada. Fonte: elaborado pelo autor.